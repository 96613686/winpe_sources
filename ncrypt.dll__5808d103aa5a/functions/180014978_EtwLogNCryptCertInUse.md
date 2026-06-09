# EtwLogNCryptCertInUse

- ea: `0x180014978`
- end: `0x180014c15`
- name: `EtwLogNCryptCertInUse`
- size: `669`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c700`
- `0x180014940`
- `0x1800173c0`

## callees

- `0x180014978`
- `0x180015a40`
- `0x180018e48`
- `0x180019770`
- `0x1800198c4`
- `0x18001e2f4`
- `0x18001e3ac`
- `0x18001e8a4`
- `0x18001e8e8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014bfa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014bfa`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014ada`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014b18`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014ada`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180014b18`

## string_xrefs

- `0x180014a22`: `{"procStart":"%s", "procPath":"%s", "serviceName":"%s", "provider":"%s", "keyId":"%s", "sign":%d, "decrypt":%d, "ephemeral":%d, "firstUse":"%s", "lastUse":"%s"}`
- `0x180014ba2`: `{"procStart":"%s", "procPath":"%s", "serviceName":"%s", "provider":"%s", "keyId":"%s", "sign":%d, "decrypt":%d, "ephemeral":%d, "firstUse":"%s", "lastUse":"%s"}`

## pseudocode

```c
__int64 __fastcall EtwLogNCryptCertInUse(__int64 a1)
{
  const wchar_t *ProcessName_0; // rax
  size_t v4; // rdx
  const wchar_t *v5; // rbx
  size_t v6; // rdx
  HRESULT v7; // r15d
  size_t v8; // rdi
  size_t v9; // rdx
  const size_t *v10; // r12
  int v11; // ebx
  int v12; // r14d
  int v13; // edi
  __int64 v14; // rax
  STRSAFE_LPWSTR v15; // rbx
  HRESULT v16; // eax
  __int64 v17; // rcx
  int v18; // [rsp+60h] [rbp-29h]
  size_t cchDest; // [rsp+80h] [rbp-9h] BYREF
  const wchar_t *v20; // [rsp+88h] [rbp-1h]
  _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp+7h] BYREF
  size_t pcchLength; // [rsp+F0h] [rbp+67h] BYREF
  __int64 v23; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v24; // [rsp+100h] [rbp+77h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+108h] [rbp+7Fh] BYREF

  v23 = 0;
  v24 = 0;
  pszDest = 0;
  if ( !a1 || !*(_DWORD *)(a1 + 36) && !*(_DWORD *)(a1 + 40) && !*(_DWORD *)(a1 + 44) )
    return 0;
  pcchLength = 0;
  ProcessName_0 = (const wchar_t *)I_GetProcessName_0();
  v5 = (const wchar_t *)(a1 + 48);
  v7 = StringCchLengthW(ProcessName_0, v4, &pcchLength);
  v20 = (const wchar_t *)(a1 + 48);
  if ( v7 >= 0 )
  {
    v8 = pcchLength + g_stServiceNameLen;
    pcchLength = 0;
    v7 = StringCchLengthW((STRSAFE_PCNZWCH)(a1 + 48), v6, &pcchLength);
    if ( v7 >= 0 )
    {
      cchDest = 0;
      v7 = StringCchLengthW(
             L"{\"procStart\":\"%s\", \"procPath\":\"%s\", \"serviceName\":\"%s\", \"provider\":\"%s\", \"keyId\":\"%s\", "
              "\"sign\":%d, \"decrypt\":%d, \"ephemeral\":%d, \"firstUse\":\"%s\", \"lastUse\":\"%s\"}",
             v9,
             &cchDest);
      if ( v7 >= 0 )
      {
        v7 = FiletimeToString(*(_QWORD *)(a1 + 20), &v23);
        if ( !v7 )
        {
          v7 = FiletimeToString(*(_QWORD *)(a1 + 28), &v24);
          if ( !v7 )
          {
            cchDest += v8 + pcchLength + 157;
            pszDest = (STRSAFE_LPWSTR)CertInUseNonzeroAlloc(2 * cchDest);
            if ( pszDest )
            {
              InitOnceExecuteOnce(&InitOnce, ProcessInfoInitOnceCallback, 0, 0);
              if ( !g_pCertInUseProcessInfo || (pcchLength = *(_QWORD *)(g_pCertInUseProcessInfo + 16)) == 0 )
                pcchLength = (size_t)&LocaleName;
              InitOnceExecuteOnce(&InitOnce, ProcessInfoInitOnceCallback, 0, 0);
              if ( !g_pCertInUseProcessInfo || (v10 = *(const size_t **)(g_pCertInUseProcessInfo + 8)) == 0 )
                v10 = &LocaleName;
              v11 = *(_DWORD *)(a1 + 40) + *(_DWORD *)(a1 + 44);
              v12 = *(_DWORD *)(a1 + 16);
              v13 = *(_DWORD *)(a1 + 36);
              v14 = I_GetProcessName_0();
              v18 = v11;
              v15 = pszDest;
              v16 = StringCchPrintfExW(
                      pszDest,
                      cchDest,
                      0,
                      &pcchLength,
                      0,
                      L"{\"procStart\":\"%s\", \"procPath\":\"%s\", \"serviceName\":\"%s\", \"provider\":\"%s\", \"keyId\""
                       ":\"%s\", \"sign\":%d, \"decrypt\":%d, \"ephemeral\":%d, \"firstUse\":\"%s\", \"lastUse\":\"%s\"}",
                      v10,
                      v14,
                      pcchLength,
                      a1 + 48,
                      a1 + 176,
                      v13,
                      v18,
                      v12,
                      v23,
                      v24);
              if ( v16 >= 0 )
              {
                if ( (Microsoft_Windows_Crypto_NCryptEnableBits & 0x20) == 0
                  || (v16 = McTemplateU0z_EventWriteTransfer(v17, ETW_NCRYPT_CERT_IN_USE_EVENT, v15), v16 >= 0) )
                {
                  SystemTimeAsFileTime = 0;
                  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
                  *(_FILETIME *)(a1 + 20) = SystemTimeAsFileTime;
                  *(_QWORD *)(a1 + 40) = 0;
                  *(_DWORD *)(a1 + 36) = 0;
                  goto LABEL_14;
                }
              }
              v5 = v20;
              v7 = v16;
            }
            else
            {
              v7 = -2146893810;
            }
          }
        }
      }
    }
  }
  EtwErrorNCryptCertInUse(L"Failed to Log CertInUse ETW Event", v5);
LABEL_14:
  CertInUseFree(&v23);
  CertInUseFree(&v24);
  CertInUseFree(&pszDest);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180014978  push    rbp
0x18001497a  push    rbx
0x18001497b  push    rsi
0x18001497c  push    rdi
0x18001497d  push    r12
0x18001497f  push    r13
0x180014981  push    r14
0x180014983  push    r15
0x180014985  lea     rbp, [rsp-1Fh]
0x18001498a  sub     rsp, 0A8h
0x180014991  xor     esi, esi
0x180014993  mov     r13, rcx
0x180014996  mov     [rbp+57h+arg_8], rsi
0x18001499a  mov     [rbp+57h+arg_10], rsi
0x18001499e  mov     [rbp+57h+pszDest], rsi
0x1800149a2  test    rcx, rcx
0x1800149a5  jnz     short loc_1800149BD
0x1800149a7  xor     eax, eax
0x1800149a9  add     rsp, 0A8h
0x1800149b0  pop     r15
0x1800149b2  pop     r14
0x1800149b4  pop     r13
0x1800149b6  pop     r12
0x1800149b8  pop     rdi
0x1800149b9  pop     rsi
0x1800149ba  pop     rbx
0x1800149bb  pop     rbp
0x1800149bc  retn
0x1800149bd  cmp     [rcx+24h], esi
0x1800149c0  jnz     short loc_1800149CC
0x1800149c2  cmp     [rcx+28h], esi
0x1800149c5  jnz     short loc_1800149CC
0x1800149c7  cmp     [rcx+2Ch], esi
0x1800149ca  jz      short loc_1800149A7
0x1800149cc  mov     [rbp+57h+pcchLength], rsi
0x1800149d0  call    I_GetProcessName_0
0x1800149d5  mov     rcx, rax; psz
0x1800149d8  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x1800149dc  call    StringCchLengthW
0x1800149e1  lea     rbx, [r13+30h]
0x1800149e5  mov     r15d, eax
0x1800149e8  mov     [rbp+57h+var_58], rbx
0x1800149ec  test    eax, eax
0x1800149ee  js      loc_180014BE4
0x1800149f4  mov     rdi, cs:g_stServiceNameLen
0x1800149fb  lea     r8, [rbp+57h+pcchLength]; pcchLength
0x1800149ff  add     rdi, [rbp+57h+pcchLength]
0x180014a03  mov     rcx, rbx; psz
0x180014a06  mov     [rbp+57h+pcchLength], rsi
0x180014a0a  call    StringCchLengthW
0x180014a0f  mov     r15d, eax
0x180014a12  test    eax, eax
0x180014a14  js      loc_180014BE4
0x180014a1a  lea     r8, [rbp+57h+cchDest]; pcchLength
0x180014a1e  mov     [rbp+57h+cchDest], rsi
0x180014a22  lea     rcx, aProcstartSProc; "{\"procStart\":\"%s\", \"procPath\":\"%"...
0x180014a29  call    StringCchLengthW
0x180014a2e  mov     r15d, eax
0x180014a31  test    eax, eax
0x180014a33  js      loc_180014BE4
0x180014a39  mov     rcx, [r13+14h]
0x180014a3d  lea     rdx, [rbp+57h+arg_8]
0x180014a41  call    FiletimeToString
0x180014a46  mov     r15d, eax
0x180014a49  test    eax, eax
0x180014a4b  jnz     short loc_180014A91
0x180014a4d  mov     rcx, [r13+1Ch]
0x180014a51  lea     rdx, [rbp+57h+arg_10]
0x180014a55  call    FiletimeToString
0x180014a5a  mov     r15d, eax
0x180014a5d  test    eax, eax
0x180014a5f  jnz     short loc_180014A91
0x180014a61  mov     rcx, [rbp+57h+cchDest]
0x180014a65  mov     rax, [rbp+57h+pcchLength]
0x180014a69  add     rcx, rdi
0x180014a6c  add     rax, 9Dh
0x180014a72  add     rax, rcx
0x180014a75  mov     [rbp+57h+cchDest], rax
0x180014a79  lea     rcx, [rax+rax]
0x180014a7d  call    CertInUseNonzeroAlloc
0x180014a82  mov     [rbp+57h+pszDest], rax
0x180014a86  test    rax, rax
0x180014a89  jnz     short loc_180014AC6
0x180014a8b  mov     r15d, 8009000Eh
0x180014a91  mov     r8d, r15d
0x180014a94  lea     rcx, aFailedToLogCer; "Failed to Log CertInUse ETW Event"
0x180014a9b  mov     rdx, rbx; STRSAFE_PCNZWCH
0x180014a9e  call    EtwErrorNCryptCertInUse
0x180014aa3  lea     rcx, [rbp+57h+arg_8]
0x180014aa7  call    CertInUseFree
0x180014aac  lea     rcx, [rbp+57h+arg_10]
0x180014ab0  call    CertInUseFree
0x180014ab5  lea     rcx, [rbp+57h+pszDest]
0x180014ab9  call    CertInUseFree
0x180014abe  mov     eax, r15d
0x180014ac1  jmp     loc_1800149A9
0x180014ac6  xor     r9d, r9d; Context
0x180014ac9  lea     rdx, _ProcessInfoInitOnceCallback; InitFn
0x180014ad0  xor     r8d, r8d; Parameter
0x180014ad3  lea     rcx, InitOnce; InitOnce
0x180014ada  call    cs:__imp_InitOnceExecuteOnce
0x180014ae0  mov     rbx, cs:g_pCertInUseProcessInfo
0x180014ae7  lea     rdi, LocaleName
0x180014aee  test    rbx, rbx
0x180014af1  jz      short loc_180014B00
0x180014af3  mov     rbx, [rbx+10h]
0x180014af7  mov     [rbp+57h+pcchLength], rbx
0x180014afb  test    rbx, rbx
0x180014afe  jnz     short loc_180014B04
0x180014b00  mov     [rbp+57h+pcchLength], rdi
0x180014b04  xor     r9d, r9d; Context
0x180014b07  lea     rdx, _ProcessInfoInitOnceCallback; InitFn
0x180014b0e  xor     r8d, r8d; Parameter
0x180014b11  lea     rcx, InitOnce; InitOnce
0x180014b18  call    cs:__imp_InitOnceExecuteOnce
0x180014b1e  mov     r12, cs:g_pCertInUseProcessInfo
0x180014b25  test    r12, r12
0x180014b28  jz      short loc_180014B34
0x180014b2a  mov     r12, [r12+8]
0x180014b2f  test    r12, r12
0x180014b32  jnz     short loc_180014B37
0x180014b34  mov     r12, rdi
0x180014b37  mov     ebx, [r13+2Ch]
0x180014b3b  lea     rsi, [r13+0B0h]
0x180014b42  add     ebx, [r13+28h]
0x180014b46  mov     r14d, [r13+10h]
0x180014b4a  mov     edi, [r13+24h]
0x180014b4e  call    I_GetProcessName_0
0x180014b53  mov     rcx, [rbp+57h+arg_10]
0x180014b57  lea     r9, [rbp+57h+pcchLength]; pcchRemaining
0x180014b5b  mov     rdx, [rbp+57h+cchDest]; cchDest
0x180014b5f  xor     r8d, r8d; ppszDestEnd
0x180014b62  mov     [rsp+0E0h+var_68], rcx
0x180014b67  mov     rcx, [rbp+57h+arg_8]
0x180014b6b  mov     [rsp+0E0h+var_70], rcx
0x180014b70  lea     rcx, [r13+30h]
0x180014b74  mov     [rsp+0E0h+var_78], r14d
0x180014b79  mov     [rsp+0E0h+var_80], ebx
0x180014b7d  mov     rbx, [rbp+57h+pszDest]
0x180014b81  mov     [rsp+0E0h+var_88], edi
0x180014b85  mov     [rsp+0E0h+var_90], rsi
0x180014b8a  xor     esi, esi
0x180014b8c  mov     [rsp+0E0h+var_98], rcx
0x180014b91  mov     rcx, [rbp+57h+pcchLength]
0x180014b95  mov     [rsp+0E0h+var_A0], rcx
0x180014b9a  mov     rcx, rbx; pszDest
0x180014b9d  mov     [rsp+0E0h+var_A8], rax
0x180014ba2  lea     rax, aProcstartSProc; "{\"procStart\":\"%s\", \"procPath\":\"%"...
0x180014ba9  mov     [rsp+0E0h+var_B0], r12
0x180014bae  mov     [rsp+0E0h+pszFormat], rax; pszFormat
0x180014bb3  mov     qword ptr [rsp+0E0h+dwFlags], rsi; dwFlags
0x180014bb8  call    StringCchPrintfExW
0x180014bbd  test    eax, eax
0x180014bbf  js      short loc_180014BDD
0x180014bc1  test    cs:Microsoft_Windows_Crypto_NCryptEnableBits, 20h
0x180014bc8  jz      short loc_180014BF2
0x180014bca  mov     r8, rbx
0x180014bcd  lea     rdx, ETW_NCRYPT_CERT_IN_USE_EVENT
0x180014bd4  call    McTemplateU0z_EventWriteTransfer
0x180014bd9  test    eax, eax
0x180014bdb  jns     short loc_180014BF2
0x180014bdd  mov     rbx, [rbp+57h+var_58]
0x180014be1  mov     r15d, eax
0x180014be4  test    r15d, r15d
0x180014be7  jnz     loc_180014A91
0x180014bed  jmp     loc_180014AA3
0x180014bf2  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180014bf6  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180014bfa  call    cs:__imp_GetSystemTimeAsFileTime
0x180014c00  mov     rax, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180014c04  mov     [r13+14h], rax
0x180014c08  mov     [r13+28h], rsi
0x180014c0c  mov     [r13+24h], esi
0x180014c10  jmp     loc_180014AA3
```
