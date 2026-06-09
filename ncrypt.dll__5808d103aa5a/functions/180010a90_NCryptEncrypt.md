# NCryptEncrypt

- ea: `0x180010a90`
- end: `0x180010c85`
- name: `NCryptEncrypt`
- size: `501`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_KEY_HANDLE hKey, PBYTE pbInput, DWORD cbInput, void *pPaddingInfo, PBYTE pbOutput, DWORD cbOutput, DWORD *pcbResult, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000a650`
- `0x18000a71c`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180010684`
- `0x180010a90`
- `0x180020010`

## string_xrefs

- `0x180010bc7`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180010c30`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180010c63`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptEncrypt(
        NCRYPT_KEY_HANDLE hKey,
        PBYTE pbInput,
        DWORD cbInput,
        void *pPaddingInfo,
        PBYTE pbOutput,
        DWORD cbOutput,
        DWORD *pcbResult,
        DWORD dwFlags)
{
  NCRYPT_KEY_HANDLE *v10; // rdx
  _QWORD *v11; // rdi
  NCryptKeyName **v12; // r8
  NCryptAlgorithmName **v13; // r9
  __int64 v14; // r10
  unsigned int v15; // eax
  unsigned int v16; // ebx
  int v18; // r9d

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PD(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, cbInput, hKey, dwFlags);
  v11 = (_QWORD *)ValidateClientKeyHandle(hKey);
  if ( v11 )
  {
    while ( 1 )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, NCRYPT_KEY_HANDLE *, _QWORD, void *, PBYTE, DWORD, DWORD *, DWORD))(v11[1] + 120LL))(
              *(_QWORD *)(v11[1] + 272LL),
              v11[2],
              v10,
              (unsigned int)v12,
              pPaddingInfo,
              pbOutput,
              cbOutput,
              pcbResult,
              dwFlags);
      v16 = v15;
      if ( v15 != -2146893778 )
      {
        if ( !v15 )
          return NormalizeNteStatus(v16, v10, v12, v13, pbOutput, cbOutput, pcbResult, dwFlags);
LABEL_10:
        DebugTraceError(v16, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 2436);
        EtwLogNCryptOperationFailed(4, *(_QWORD *)(v11[1] + 280LL), v11[3], v18, v16);
        return NormalizeNteStatus(v16, v10, v12, v13, pbOutput, cbOutput, pcbResult, dwFlags);
      }
      if ( (dwFlags & 0x40) != 0 )
        break;
      v16 = (*(__int64 (__fastcall **)(_QWORD, NCRYPT_KEY_HANDLE, const wchar_t *, _QWORD))(v11[1] + 192LL))(
              *(_QWORD *)(v11[1] + 272LL),
              hKey,
              L"NCryptEncrypt",
              0);
      if ( v16 )
        goto LABEL_10;
      LODWORD(v12) = cbInput;
      v10 = (NCRYPT_KEY_HANDLE *)pbInput;
    }
    v16 = -2146893790;
    DebugTraceError(2148073506LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", 2418);
  }
  else
  {
    v16 = -2146893786;
    if ( (PVOID *)v14 != &WPP_GLOBAL_Control && (*(_BYTE *)(v14 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v14 + 16),
        (_DWORD)v10,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        88);
  }
  return NormalizeNteStatus(v16, v10, v12, v13, pbOutput, cbOutput, pcbResult, dwFlags);
}

```

## disassembly

```asm
0x180010a90  mov     rax, rsp
0x180010a93  mov     [rax+8], rbx
0x180010a97  mov     [rax+18h], r8d
0x180010a9b  mov     [rax+10h], rdx
0x180010a9f  push    rbp
0x180010aa0  push    rsi
0x180010aa1  push    rdi
0x180010aa2  push    r12
0x180010aa4  push    r13
0x180010aa6  push    r14
0x180010aa8  push    r15
0x180010aaa  sub     rsp, 50h
0x180010aae  mov     r13, r9
0x180010ab1  mov     rsi, rcx
0x180010ab4  mov     r10, cs:WPP_GLOBAL_Control
0x180010abb  lea     r14, WPP_GLOBAL_Control
0x180010ac2  mov     ebp, [rsp+88h+dwFlags]
0x180010ac9  cmp     r10, r14
0x180010acc  jz      short loc_180010B00
0x180010ace  test    byte ptr [r10+1Ch], 4
0x180010ad3  jz      short loc_180010B00
0x180010ad5  mov     r9, rcx
0x180010ad8  mov     [rax-68h], ebp
0x180010adb  mov     rcx, [r10+10h]
0x180010adf  mov     edx, 16h
0x180010ae4  call    WPP_SF_PD
0x180010ae9  mov     r10, cs:WPP_GLOBAL_Control
0x180010af0  mov     r8d, [rsp+88h+arg_10]
0x180010af8  mov     rdx, [rsp+88h+arg_8]
0x180010b00  mov     rcx, rsi
0x180010b03  call    ValidateClientKeyHandle
0x180010b08  mov     rdi, rax
0x180010b0b  test    rax, rax
0x180010b0e  jz      loc_180010C13
0x180010b14  mov     r14, [rsp+88h+pcbResult]
0x180010b1c  mov     r15d, [rsp+88h+cbOutput]
0x180010b24  mov     r12, [rsp+88h+pbOutput]
0x180010b2c  mov     rcx, [rdi+8]
0x180010b30  mov     r9d, r8d
0x180010b33  mov     [rsp+88h+var_48], ebp
0x180010b37  mov     r8, rdx
0x180010b3a  mov     rdx, [rdi+10h]
0x180010b3e  mov     [rsp+88h+var_50], r14
0x180010b43  mov     rax, [rcx+78h]
0x180010b47  mov     rcx, [rcx+110h]
0x180010b4e  mov     [rsp+88h+var_58], r15d
0x180010b53  mov     [rsp+88h+var_60], r12
0x180010b58  mov     [rsp+88h+var_68], r13
0x180010b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b62  mov     ebx, eax
0x180010b64  cmp     eax, 8009002Eh
0x180010b69  jz      short loc_180010B8D
0x180010b6b  test    eax, eax
0x180010b6d  jnz     short loc_180010BC1
0x180010b6f  mov     ecx, ebx
0x180010b71  mov     rbx, [rsp+88h+arg_0]
0x180010b79  add     rsp, 50h
0x180010b7d  pop     r15
0x180010b7f  pop     r14
0x180010b81  pop     r13
0x180010b83  pop     r12
0x180010b85  pop     rdi
0x180010b86  pop     rsi
0x180010b87  pop     rbp
0x180010b88  jmp     NormalizeNteStatus
0x180010b8d  test    bpl, 40h
0x180010b91  jnz     loc_180010C5D
0x180010b97  mov     rcx, [rdi+8]
0x180010b9b  lea     r8, aNcryptencrypt_0; "NCryptEncrypt"
0x180010ba2  xor     r9d, r9d
0x180010ba5  mov     rdx, rsi
0x180010ba8  mov     rax, [rcx+0C0h]
0x180010baf  mov     rcx, [rcx+110h]
0x180010bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bbb  mov     ebx, eax
0x180010bbd  test    eax, eax
0x180010bbf  jz      short loc_180010BFE
0x180010bc1  mov     r9d, 984h
0x180010bc7  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010bce  lea     rdx, aStatus; "Status"
0x180010bd5  mov     ecx, ebx
0x180010bd7  call    DebugTraceError
0x180010bdc  mov     rdx, [rdi+8]
0x180010be0  mov     ecx, 4
0x180010be5  mov     r8, [rdi+18h]
0x180010be9  mov     dword ptr [rsp+88h+var_68], ebx
0x180010bed  mov     rdx, [rdx+118h]
0x180010bf4  call    EtwLogNCryptOperationFailed
0x180010bf9  jmp     loc_180010B6F
0x180010bfe  mov     r8d, [rsp+88h+arg_10]
0x180010c06  mov     rdx, [rsp+88h+arg_8]
0x180010c0e  jmp     loc_180010B2C
0x180010c13  mov     ebx, 80090026h
0x180010c18  cmp     r10, r14
0x180010c1b  jz      loc_180010B6F
0x180010c21  test    byte ptr [r10+1Ch], 1
0x180010c26  jz      loc_180010B6F
0x180010c2c  mov     rcx, [r10+10h]
0x180010c30  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010c37  mov     [rsp+88h+var_58], 958h
0x180010c3f  lea     r9, aStatus; "Status"
0x180010c46  mov     [rsp+88h+var_60], r8
0x180010c4b  mov     dword ptr [rsp+88h+var_68], 80090026h
0x180010c53  call    WPP_SF_sDsd
0x180010c58  jmp     loc_180010B6F
0x180010c5d  mov     r9d, 972h
0x180010c63  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010c6a  lea     rdx, aStatus; "Status"
0x180010c71  mov     ecx, 80090022h
0x180010c76  mov     ebx, 80090022h
0x180010c7b  call    DebugTraceError
0x180010c80  jmp     loc_180010B6F
```
