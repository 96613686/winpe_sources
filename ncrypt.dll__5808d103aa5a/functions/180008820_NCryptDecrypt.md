# NCryptDecrypt

- ea: `0x180008820`
- end: `0x180008a8a`
- name: `NCryptDecrypt`
- size: `618`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_KEY_HANDLE hKey, PBYTE pbInput, DWORD cbInput, void *pPaddingInfo, PBYTE pbOutput, DWORD cbOutput, DWORD *pcbResult, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180008820`
- `0x18000a650`
- `0x18000a71c`
- `0x18000c8e0`
- `0x18000d02c`
- `0x180010684`
- `0x1800173c0`
- `0x180020010`

## string_xrefs

- `0x1800089a5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180008a08`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180008a5f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptDecrypt(
        NCRYPT_KEY_HANDLE hKey,
        PBYTE pbInput,
        DWORD cbInput,
        void *pPaddingInfo,
        PBYTE pbOutput,
        DWORD cbOutput,
        DWORD *pcbResult,
        DWORD dwFlags)
{
  DWORD v10; // esi
  NCRYPT_KEY_HANDLE *v11; // rdx
  _QWORD *v12; // rdi
  NCryptKeyName **v13; // r8
  NCryptAlgorithmName **v14; // r9
  __int64 v15; // r10
  DWORD *v16; // r15
  DWORD v17; // ebp
  PBYTE v18; // r14
  unsigned int v19; // eax
  unsigned int v20; // ebx
  NCRYPT_KEY_HANDLE v22; // [rsp+90h] [rbp+8h] BYREF
  PBYTE v23; // [rsp+98h] [rbp+10h]

  v23 = pbInput;
  v22 = hKey;
  v10 = dwFlags;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_PD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_GLOBAL_Control, hKey, dwFlags);
    hKey = v22;
  }
  v12 = (_QWORD *)ValidateClientKeyHandle(hKey);
  if ( v12 )
  {
    v16 = pcbResult;
    v17 = cbOutput;
    v18 = pbOutput;
    while ( 1 )
    {
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, NCRYPT_KEY_HANDLE *, _QWORD, void *, PBYTE, DWORD, DWORD *, DWORD))(v12[1] + 128LL))(
              *(_QWORD *)(v12[1] + 272LL),
              v12[2],
              v11,
              cbInput,
              pPaddingInfo,
              v18,
              v17,
              v16,
              v10);
      v20 = v19;
      if ( v19 != -2146893778 )
      {
        if ( !v19 )
        {
          if ( v18 && v17 && (v10 & 0x10) == 0 )
            CertInUseLog(1, v12 + 5, &v22);
          v20 = 0;
          return NormalizeNteStatus(v20, v11, v13, v14, pbOutput, cbOutput, pcbResult, dwFlags);
        }
LABEL_16:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v11,
            (_DWORD)v13,
            (unsigned int)"Status",
            v20,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
            225);
        EtwLogNCryptOperationFailed(5, *(_QWORD *)(v12[1] + 280LL), v12[3], (_DWORD)v14, v20);
        return NormalizeNteStatus(v20, v11, v13, v14, pbOutput, cbOutput, pcbResult, dwFlags);
      }
      if ( (v10 & 0x40) != 0 )
        break;
      v20 = (*(__int64 (__fastcall **)(_QWORD, NCRYPT_KEY_HANDLE, const wchar_t *, _QWORD))(v12[1] + 192LL))(
              *(_QWORD *)(v12[1] + 272LL),
              v22,
              L"NCryptDecrypt",
              0);
      if ( v20 )
        goto LABEL_16;
      v11 = (NCRYPT_KEY_HANDLE *)v23;
    }
    v20 = -2146893790;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v11,
        (_DWORD)v13,
        (unsigned int)"Status",
        34,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        206);
  }
  else
  {
    v20 = -2146893786;
    if ( (NCryptKeyName **)v15 != v13 && (*(_BYTE *)(v15 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v15 + 16),
        (_DWORD)v11,
        (_DWORD)v13,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        180);
  }
  return NormalizeNteStatus(v20, v11, v13, v14, pbOutput, cbOutput, pcbResult, dwFlags);
}

```

## disassembly

```asm
0x180008820  mov     rax, rsp
0x180008823  mov     [rax+18h], rbx
0x180008827  mov     [rax+10h], rdx
0x18000882b  mov     [rax+8], rcx
0x18000882f  push    rbp
0x180008830  push    rsi
0x180008831  push    rdi
0x180008832  push    r12
0x180008834  push    r13
0x180008836  push    r14
0x180008838  push    r15
0x18000883a  sub     rsp, 50h
0x18000883e  mov     r12, r9
0x180008841  mov     r13d, r8d
0x180008844  mov     r10, cs:WPP_GLOBAL_Control
0x18000884b  lea     r8, WPP_GLOBAL_Control
0x180008852  mov     esi, [rsp+88h+dwFlags]
0x180008859  cmp     r10, r8
0x18000885c  jz      short loc_180008897
0x18000885e  test    byte ptr [r10+1Ch], 4
0x180008863  jz      short loc_180008897
0x180008865  mov     r9, rcx
0x180008868  mov     [rax-68h], esi
0x18000886b  mov     rcx, [r10+10h]
0x18000886f  mov     edx, 17h
0x180008874  call    WPP_SF_PD
0x180008879  mov     rcx, [rsp+88h+arg_0]
0x180008881  lea     r8, WPP_GLOBAL_Control
0x180008888  mov     r10, cs:WPP_GLOBAL_Control
0x18000888f  mov     rdx, [rsp+88h+arg_8]
0x180008897  call    ValidateClientKeyHandle
0x18000889c  mov     rdi, rax
0x18000889f  test    rax, rax
0x1800088a2  jz      loc_1800089EB
0x1800088a8  mov     r15, [rsp+88h+pcbResult]
0x1800088b0  mov     ebp, [rsp+88h+cbOutput]
0x1800088b7  mov     r14, [rsp+88h+pbOutput]
0x1800088bf  mov     rcx, [rdi+8]
0x1800088c3  mov     r8, rdx
0x1800088c6  mov     rdx, [rdi+10h]
0x1800088ca  mov     r9d, r13d
0x1800088cd  mov     [rsp+88h+var_48], esi
0x1800088d1  mov     [rsp+88h+var_50], r15
0x1800088d6  mov     rax, [rcx+80h]
0x1800088dd  mov     rcx, [rcx+110h]
0x1800088e4  mov     [rsp+88h+var_58], ebp
0x1800088e8  mov     [rsp+88h+var_60], r14
0x1800088ed  mov     [rsp+88h+var_68], r12
0x1800088f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088f7  mov     ebx, eax
0x1800088f9  cmp     eax, 8009002Eh
0x1800088fe  jz      short loc_18000894B
0x180008900  test    eax, eax
0x180008902  jnz     loc_180008988
0x180008908  test    r14, r14
0x18000890b  jz      short loc_18000892B
0x18000890d  test    ebp, ebp
0x18000890f  jz      short loc_18000892B
0x180008911  test    sil, 10h
0x180008915  jnz     short loc_18000892B
0x180008917  lea     rdx, [rdi+28h]
0x18000891b  lea     r8, [rsp+88h+arg_0]
0x180008923  lea     ecx, [rax+1]
0x180008926  call    CertInUseLog
0x18000892b  xor     ebx, ebx
0x18000892d  mov     ecx, ebx
0x18000892f  mov     rbx, [rsp+88h+arg_10]
0x180008937  add     rsp, 50h
0x18000893b  pop     r15
0x18000893d  pop     r14
0x18000893f  pop     r13
0x180008941  pop     r12
0x180008943  pop     rdi
0x180008944  pop     rsi
0x180008945  pop     rbp
0x180008946  jmp     NormalizeNteStatus
0x18000894b  test    sil, 40h
0x18000894f  jnz     loc_180008A35
0x180008955  mov     rcx, [rdi+8]
0x180008959  lea     r8, aNcryptdecrypt_0; "NCryptDecrypt"
0x180008960  mov     rdx, [rsp+88h+arg_0]
0x180008968  xor     r9d, r9d
0x18000896b  mov     rax, [rcx+0C0h]
0x180008972  mov     rcx, [rcx+110h]
0x180008979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000897e  mov     ebx, eax
0x180008980  test    eax, eax
0x180008982  jz      loc_180008A7D
0x180008988  mov     rcx, cs:WPP_GLOBAL_Control
0x18000898f  lea     rax, WPP_GLOBAL_Control
0x180008996  cmp     rcx, rax
0x180008999  jz      short loc_1800089C9
0x18000899b  test    byte ptr [rcx+1Ch], 1
0x18000899f  jz      short loc_1800089C9
0x1800089a1  mov     rcx, [rcx+10h]
0x1800089a5  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800089ac  mov     [rsp+88h+var_58], 9E1h
0x1800089b4  lea     r9, aStatus; "Status"
0x1800089bb  mov     [rsp+88h+var_60], rax
0x1800089c0  mov     dword ptr [rsp+88h+var_68], ebx
0x1800089c4  call    WPP_SF_sDsd
0x1800089c9  mov     rdx, [rdi+8]
0x1800089cd  mov     ecx, 5
0x1800089d2  mov     r8, [rdi+18h]
0x1800089d6  mov     dword ptr [rsp+88h+var_68], ebx
0x1800089da  mov     rdx, [rdx+118h]
0x1800089e1  call    EtwLogNCryptOperationFailed
0x1800089e6  jmp     loc_18000892D
0x1800089eb  mov     ebx, 80090026h
0x1800089f0  cmp     r10, r8
0x1800089f3  jz      loc_18000892D
0x1800089f9  test    byte ptr [r10+1Ch], 1
0x1800089fe  jz      loc_18000892D
0x180008a04  mov     rcx, [r10+10h]
0x180008a08  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008a0f  mov     [rsp+88h+var_58], 9B4h
0x180008a17  mov     [rsp+88h+var_60], rax
0x180008a1c  mov     dword ptr [rsp+88h+var_68], 80090026h
0x180008a24  lea     r9, aStatus; "Status"
0x180008a2b  call    WPP_SF_sDsd
0x180008a30  jmp     loc_18000892D
0x180008a35  mov     ebx, 80090022h
0x180008a3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a41  lea     rax, WPP_GLOBAL_Control
0x180008a48  cmp     rcx, rax
0x180008a4b  jz      loc_18000892D
0x180008a51  test    byte ptr [rcx+1Ch], 1
0x180008a55  jz      loc_18000892D
0x180008a5b  mov     rcx, [rcx+10h]
0x180008a5f  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008a66  mov     [rsp+88h+var_58], 9CEh
0x180008a6e  mov     [rsp+88h+var_60], rax
0x180008a73  mov     dword ptr [rsp+88h+var_68], 80090022h
0x180008a7b  jmp     short loc_180008A24
0x180008a7d  mov     rdx, [rsp+88h+arg_8]
0x180008a85  jmp     loc_1800088BF
```
