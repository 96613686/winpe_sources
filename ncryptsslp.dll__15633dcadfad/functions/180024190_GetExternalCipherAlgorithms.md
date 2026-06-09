# GetExternalCipherAlgorithms

- ea: `0x180024190`
- end: `0x18002444a`
- name: `GetExternalCipherAlgorithms`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012578`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x1800126f0`
- `0x180012d6c`
- `0x180014660`
- `0x180023d58`
- `0x1800240f0`
- `0x180024190`
- `0x1800244f0`
- `0x180024ef0`
- `0x180025660`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002430b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18002430b`
- `bcrypt!BCryptGetProperty` at `0x18002433e`
- `bcrypt!BCryptGetProperty` at `0x18002433e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002434f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002435a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002434f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18002435a`
- `ntdll!NtEnumerateKey` at `0x180024253`
- `ntdll!NtEnumerateKey` at `0x180024253`

## string_xrefs

- `0x180024200`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Cipher`
- `0x180024297`: `\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider\Cipher`

## pseudocode

```c
__int64 GetExternalCipherAlgorithms()
{
  __int64 result; // rax
  ULONG i; // edi
  unsigned __int64 v2; // rdx
  unsigned __int64 v3; // r9
  HANDLE v4; // rbx
  _OWORD *v5; // rax
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  wchar_t *v9; // rcx
  int v10; // ecx
  UCHAR pbOutput[8]; // [rsp+30h] [rbp-D0h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v13; // [rsp+40h] [rbp-C0h] BYREF
  ULONG ResultLength; // [rsp+48h] [rbp-B8h] BYREF
  ULONG pcbResult; // [rsp+4Ch] [rbp-B4h] BYREF
  HANDLE KeyHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszAlgId[128]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD KeyInformation[136]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR v19[64]; // [rsp+380h] [rbp+280h] BYREF

  KeyHandle[0] = 0;
  v13 = 0;
  memset(v19, 0, sizeof(v19));
  *(_DWORD *)pbOutput = 0;
  phAlgorithm = 0;
  pcbResult = 0;
  result = FreeExternalCipherAlgorithms();
  if ( (unsigned int)g_dwCipherInfoTotalCount < 0x10 )
  {
    result = TlsOpenRegKey(
               L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Protocol "
                "Provider\\Cipher",
               0,
               KeyHandle);
    if ( (int)result >= 0 )
    {
      ResultLength = 0;
      for ( i = 0; ; ++i )
      {
        if ( (unsigned int)g_dwCipherInfoTotalCount >= 0x10 )
          return TlsCloseRegKey(KeyHandle);
        memset(KeyInformation, 0, 536);
        if ( NtEnumerateKey(KeyHandle[0], i, KeyBasicInformation, KeyInformation, 0x218u, &ResultLength) < 0 )
          return TlsCloseRegKey(KeyHandle);
        v3 = -1;
        do
          ++v3;
        while ( *((_WORD *)&KeyInformation[4] + v3) );
        if ( (int)RtlStringCchCopyNW(v19, v2, (const unsigned __int16 *)&KeyInformation[4], v3) >= 0
          && (int)TlsOpenRegKey(
                    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft SSL Prot"
                     "ocol Provider\\Cipher",
                    v19,
                    &v13) >= 0 )
        {
          memset(pszAlgId, 0, sizeof(pszAlgId));
          v4 = v13;
          if ( (int)GetSslStringFromRegistry(v13, L"CngAlgorithm", pszAlgId) < 0 )
          {
            TlsCloseRegKey(&v13);
          }
          else
          {
            GetSslStringFromRegistry(v4, L"CipherMode", &pszAlgId[64]);
            TlsCloseRegKey(&v13);
            if ( BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0) < 0 )
              continue;
            if ( BCryptGetProperty(phAlgorithm, L"BlockLength", pbOutput, 4u, &pcbResult, 0) < 0 )
            {
              BCryptCloseAlgorithmProvider(phAlgorithm, 0);
              continue;
            }
            BCryptCloseAlgorithmProvider(phAlgorithm, 0);
            v5 = (_OWORD *)SafeAllocaAllocateFromHeap(32);
            v6 = (__int64)v5;
            if ( v5 )
            {
              *v5 = 0;
              v5[1] = 0;
              v7 = SafeAllocaAllocateFromHeap(128);
              *(_QWORD *)v6 = v7;
              if ( !v7 )
                goto LABEL_15;
              v8 = SafeAllocaAllocateFromHeap(128);
              v9 = *(wchar_t **)v6;
              *(_QWORD *)(v6 + 24) = v8;
              if ( !v8 )
              {
                MSCryptFree(v9);
LABEL_15:
                MSCryptFree(v6);
                continue;
              }
              wcscpy_s(v9, 0x40u, pszAlgId);
              wcscpy_s(*(wchar_t **)(v6 + 24), 0x40u, &pszAlgId[64]);
              v10 = g_dwCipherInfoTotalCount++;
              *(_DWORD *)(v6 + 12) = v10 - 1073741830;
              *(_DWORD *)(v6 + 16) = v10 + 28665;
              *(_DWORD *)(v6 + 8) = *(_DWORD *)pbOutput;
              g_pCipherInfo[v10] = v6;
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024190  push    rbp
0x180024192  push    rbx
0x180024193  push    rsi
0x180024194  push    rdi
0x180024195  push    r14
0x180024197  lea     rbp, [rsp-310h]
0x18002419f  sub     rsp, 410h
0x1800241a6  mov     rax, cs:__security_cookie
0x1800241ad  xor     rax, rsp
0x1800241b0  mov     [rbp+330h+var_30], rax
0x1800241b7  xor     esi, esi
0x1800241b9  lea     rcx, [rbp+330h+var_B0]; void *
0x1800241c0  mov     r14d, 80h
0x1800241c6  mov     [rsp+430h+KeyHandle], rsi
0x1800241cb  mov     r8d, r14d; Size
0x1800241ce  mov     [rsp+430h+var_3F0], rsi
0x1800241d3  xor     edx, edx; Val
0x1800241d5  call    memset
0x1800241da  mov     dword ptr [rsp+430h+pbOutput], esi
0x1800241de  mov     [rsp+430h+phAlgorithm], rsi
0x1800241e3  mov     [rsp+430h+pcbResult], esi
0x1800241e7  call    FreeExternalCipherAlgorithms
0x1800241ec  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x1800241f3  jnb     loc_18002442D
0x1800241f9  lea     r8, [rsp+430h+KeyHandle]; KeyHandle
0x1800241fe  xor     edx, edx; PCWSTR
0x180024200  lea     rcx, aRegistryMachin_2; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x180024207  call    TlsOpenRegKey
0x18002420c  test    eax, eax
0x18002420e  js      loc_18002442D
0x180024214  mov     [rsp+430h+var_3E8], esi
0x180024218  mov     edi, esi
0x18002421a  jmp     loc_180024416
0x18002421f  xor     edx, edx; Val
0x180024221  mov     [rbp+330h+KeyInformation], esi
0x180024224  mov     r8d, 214h; Size
0x18002422a  lea     rcx, [rbp+330h+var_2CC]; void *
0x18002422e  call    memset
0x180024233  mov     rcx, [rsp+430h+KeyHandle]; KeyHandle
0x180024238  lea     rax, [rsp+430h+var_3E8]
0x18002423d  mov     [rsp+430h+ResultLength], rax; ResultLength
0x180024242  lea     r9, [rbp+330h+KeyInformation]; KeyInformation
0x180024246  xor     r8d, r8d; KeyInformationClass
0x180024249  mov     [rsp+430h+Length], 218h; Length
0x180024251  mov     edx, edi; Index
0x180024253  call    cs:__imp_NtEnumerateKey
0x180024259  test    eax, eax
0x18002425b  js      loc_180024423
0x180024261  lea     rax, [rbp+330h+var_2C0]
0x180024265  or      r9, 0FFFFFFFFFFFFFFFFh
0x180024269  inc     r9; unsigned __int64
0x18002426c  cmp     [rax+r9*2], si
0x180024271  jnz     short loc_180024269
0x180024273  lea     r8, [rbp+330h+var_2C0]; unsigned __int16 *
0x180024277  lea     rcx, [rbp+330h+var_B0]; unsigned __int16 *
0x18002427e  call    ?RtlStringCchCopyNW@@YAJPEAG_KPEBG1@Z; RtlStringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180024283  test    eax, eax
0x180024285  js      loc_180024414
0x18002428b  lea     r8, [rsp+430h+var_3F0]; KeyHandle
0x180024290  lea     rdx, [rbp+330h+var_B0]; PCWSTR
0x180024297  lea     rcx, aRegistryMachin_2; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18002429e  call    TlsOpenRegKey
0x1800242a3  test    eax, eax
0x1800242a5  js      loc_180024414
0x1800242ab  xor     edx, edx; Val
0x1800242ad  lea     rcx, [rsp+430h+pszAlgId]; void *
0x1800242b2  mov     r8d, 100h; Size
0x1800242b8  call    memset
0x1800242bd  mov     rbx, [rsp+430h+var_3F0]
0x1800242c2  lea     r8, [rsp+430h+pszAlgId]; unsigned __int16 *
0x1800242c7  mov     rcx, rbx; KeyHandle
0x1800242ca  lea     rdx, aCngalgorithm; "CngAlgorithm"
0x1800242d1  call    GetSslStringFromRegistry
0x1800242d6  test    eax, eax
0x1800242d8  js      loc_18002440A
0x1800242de  lea     r8, [rbp+330h+Source]; unsigned __int16 *
0x1800242e2  mov     rcx, rbx; KeyHandle
0x1800242e5  lea     rdx, aCiphermode; "CipherMode"
0x1800242ec  call    GetSslStringFromRegistry
0x1800242f1  lea     rcx, [rsp+430h+var_3F0]
0x1800242f6  call    TlsCloseRegKey
0x1800242fb  xor     r9d, r9d; dwFlags
0x1800242fe  lea     rdx, [rsp+430h+pszAlgId]; pszAlgId
0x180024303  xor     r8d, r8d; pszImplementation
0x180024306  lea     rcx, [rsp+430h+phAlgorithm]; phAlgorithm
0x18002430b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180024311  test    eax, eax
0x180024313  js      loc_180024414
0x180024319  mov     rcx, [rsp+430h+phAlgorithm]; hObject
0x18002431e  lea     rax, [rsp+430h+pcbResult]
0x180024323  mov     dword ptr [rsp+430h+ResultLength], esi; dwFlags
0x180024327  lea     r8, [rsp+430h+pbOutput]; pbOutput
0x18002432c  mov     r9d, 4; cbOutput
0x180024332  mov     qword ptr [rsp+430h+Length], rax; pcbResult
0x180024337  lea     rdx, aBlocklength; "BlockLength"
0x18002433e  call    cs:__imp_BCryptGetProperty
0x180024344  mov     rcx, [rsp+430h+phAlgorithm]; hAlgorithm
0x180024349  xor     edx, edx; dwFlags
0x18002434b  test    eax, eax
0x18002434d  jns     short loc_18002435A
0x18002434f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180024355  jmp     loc_180024414
0x18002435a  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180024360  mov     ecx, 20h ; ' '
0x180024365  call    SafeAllocaAllocateFromHeap
0x18002436a  mov     rbx, rax
0x18002436d  test    rax, rax
0x180024370  jz      loc_180024414
0x180024376  xorps   xmm0, xmm0
0x180024379  mov     rcx, r14
0x18002437c  movups  xmmword ptr [rax], xmm0
0x18002437f  movups  xmmword ptr [rax+10h], xmm0
0x180024383  call    SafeAllocaAllocateFromHeap
0x180024388  mov     [rbx], rax
0x18002438b  test    rax, rax
0x18002438e  jnz     short loc_18002439A
0x180024390  mov     rcx, rbx
0x180024393  call    MSCryptFree
0x180024398  jmp     short loc_180024414
0x18002439a  mov     rcx, r14
0x18002439d  call    SafeAllocaAllocateFromHeap
0x1800243a2  mov     rcx, [rbx]; Destination
0x1800243a5  mov     [rbx+18h], rax
0x1800243a9  test    rax, rax
0x1800243ac  jnz     short loc_1800243B5
0x1800243ae  call    MSCryptFree
0x1800243b3  jmp     short loc_180024390
0x1800243b5  lea     r8, [rsp+430h+pszAlgId]; Source
0x1800243ba  mov     edx, 40h ; '@'; SizeInWords
0x1800243bf  call    wcscpy_s
0x1800243c4  mov     rcx, [rbx+18h]; Destination
0x1800243c8  lea     r8, [rbp+330h+Source]; Source
0x1800243cc  mov     edx, 40h ; '@'; SizeInWords
0x1800243d1  call    wcscpy_s
0x1800243d6  mov     ecx, cs:g_dwCipherInfoTotalCount
0x1800243dc  inc     cs:g_dwCipherInfoTotalCount
0x1800243e2  lea     eax, [rcx-40000006h]
0x1800243e8  mov     [rbx+0Ch], eax
0x1800243eb  lea     eax, [rcx+6FF9h]
0x1800243f1  mov     [rbx+10h], eax
0x1800243f4  mov     eax, dword ptr [rsp+430h+pbOutput]
0x1800243f8  mov     [rbx+8], eax
0x1800243fb  mov     eax, ecx
0x1800243fd  lea     rcx, g_pCipherInfo
0x180024404  mov     [rcx+rax*8], rbx
0x180024408  jmp     short loc_180024414
0x18002440a  lea     rcx, [rsp+430h+var_3F0]
0x18002440f  call    TlsCloseRegKey
0x180024414  inc     edi
0x180024416  cmp     cs:g_dwCipherInfoTotalCount, 10h
0x18002441d  jb      loc_18002421F
0x180024423  lea     rcx, [rsp+430h+KeyHandle]
0x180024428  call    TlsCloseRegKey
0x18002442d  mov     rcx, [rbp+330h+var_30]
0x180024434  xor     rcx, rsp; StackCookie
0x180024437  call    __security_check_cookie
0x18002443c  add     rsp, 410h
0x180024443  pop     r14
0x180024445  pop     rdi
0x180024446  pop     rsi
0x180024447  pop     rbx
0x180024448  pop     rbp
0x180024449  retn
```
