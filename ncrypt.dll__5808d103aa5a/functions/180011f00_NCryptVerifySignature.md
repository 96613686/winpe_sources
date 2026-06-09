# NCryptVerifySignature

- ea: `0x180011f00`
- end: `0x180012119`
- name: `NCryptVerifySignature`
- size: `537`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_KEY_HANDLE hKey, void *pPaddingInfo, PBYTE pbHashValue, DWORD cbHashValue, PBYTE pbSignature, DWORD cbSignature, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000a650`
- `0x18000a71c`
- `0x18000c8e0`
- `0x18000d02c`
- `0x180010684`
- `0x180011f00`
- `0x180020010`

## string_xrefs

- `0x180011f8f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180012040`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x1800120b6`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
SECURITY_STATUS __stdcall NCryptVerifySignature(
        NCRYPT_KEY_HANDLE hKey,
        void *pPaddingInfo,
        PBYTE pbHashValue,
        DWORD cbHashValue,
        PBYTE pbSignature,
        DWORD cbSignature,
        DWORD dwFlags)
{
  NCRYPT_KEY_HANDLE *v10; // rdx
  _QWORD *v11; // rdi
  NCryptKeyName **v12; // r8
  NCryptAlgorithmName **v13; // r9
  __int64 v14; // r10
  unsigned int v15; // ebx
  unsigned int v17; // eax

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PD(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_GLOBAL_Control, hKey, dwFlags);
  v11 = (_QWORD *)ValidateClientKeyHandle(hKey);
  if ( v11 )
  {
    while ( 1 )
    {
      v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, NCRYPT_KEY_HANDLE *, PBYTE, DWORD, PBYTE, DWORD, DWORD))(v11[1] + 184LL))(
              *(_QWORD *)(v11[1] + 272LL),
              v11[2],
              v10,
              pbHashValue,
              cbHashValue,
              pbSignature,
              cbSignature,
              dwFlags);
      v15 = v17;
      if ( v17 != -2146893778 )
      {
        if ( !v17 )
        {
          v15 = 0;
          return NormalizeNteStatus(v15, v10, v12, v13, pbSignature, cbSignature, *(DWORD **)&dwFlags);
        }
LABEL_11:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v10,
            (_DWORD)v12,
            (unsigned int)"Status",
            v15,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
            88);
        EtwLogNCryptOperationFailed(7, *(_QWORD *)(v11[1] + 280LL), v11[3], (_DWORD)v13, v15);
        return NormalizeNteStatus(v15, v10, v12, v13, pbSignature, cbSignature, *(DWORD **)&dwFlags);
      }
      if ( (dwFlags & 0x40) != 0 )
        break;
      v15 = (*(__int64 (__fastcall **)(_QWORD, NCRYPT_KEY_HANDLE, const wchar_t *, _QWORD))(v11[1] + 192LL))(
              *(_QWORD *)(v11[1] + 272LL),
              hKey,
              L"NCryptVerifySignature",
              0);
      if ( v15 )
        goto LABEL_11;
      v10 = (NCRYPT_KEY_HANDLE *)pPaddingInfo;
    }
    v15 = -2146893790;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v10,
        (_DWORD)v12,
        (unsigned int)"Status",
        34,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        69);
  }
  else
  {
    v15 = -2146893786;
    if ( (NCryptKeyName **)v14 != v12 && (*(_BYTE *)(v14 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(v14 + 16),
        (_DWORD)v10,
        (_DWORD)v12,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        44);
  }
  return NormalizeNteStatus(v15, v10, v12, v13, pbSignature, cbSignature, *(DWORD **)&dwFlags);
}

```

## disassembly

```asm
0x180011f00  mov     [rsp+arg_8], rdx
0x180011f05  push    rbx
0x180011f06  push    rbp
0x180011f07  push    rsi
0x180011f08  push    rdi
0x180011f09  push    r12
0x180011f0b  push    r13
0x180011f0d  push    r14
0x180011f0f  push    r15
0x180011f11  sub     rsp, 58h
0x180011f15  mov     r12d, r9d
0x180011f18  mov     r13, r8
0x180011f1b  mov     rsi, rcx
0x180011f1e  mov     r10, cs:WPP_GLOBAL_Control
0x180011f25  lea     r8, WPP_GLOBAL_Control
0x180011f2c  mov     ebp, [rsp+98h+dwFlags]
0x180011f33  cmp     r10, r8
0x180011f36  jz      short loc_180011F6A
0x180011f38  test    byte ptr [r10+1Ch], 4
0x180011f3d  jz      short loc_180011F6A
0x180011f3f  mov     r9, rcx
0x180011f42  mov     [rsp+98h+var_78], ebp
0x180011f46  mov     rcx, [r10+10h]
0x180011f4a  mov     edx, 1Eh
0x180011f4f  call    WPP_SF_PD
0x180011f54  mov     r10, cs:WPP_GLOBAL_Control
0x180011f5b  lea     r8, WPP_GLOBAL_Control
0x180011f62  mov     rdx, [rsp+98h+arg_8]
0x180011f6a  mov     rcx, rsi
0x180011f6d  call    ValidateClientKeyHandle
0x180011f72  mov     rdi, rax
0x180011f75  test    rax, rax
0x180011f78  jnz     short loc_180011FCE
0x180011f7a  mov     ebx, 80090026h
0x180011f7f  cmp     r10, r8
0x180011f82  jz      short loc_180011FB7
0x180011f84  test    byte ptr [r10+1Ch], 1
0x180011f89  jz      short loc_180011FB7
0x180011f8b  mov     rcx, [r10+10h]
0x180011f8f  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011f96  mov     [rsp+98h+var_68], 0E2Ch
0x180011f9e  mov     [rsp+98h+var_70], rax
0x180011fa3  mov     [rsp+98h+var_78], 80090026h
0x180011fab  lea     r9, aStatus; "Status"
0x180011fb2  call    WPP_SF_sDsd
0x180011fb7  mov     ecx, ebx
0x180011fb9  add     rsp, 58h
0x180011fbd  pop     r15
0x180011fbf  pop     r14
0x180011fc1  pop     r13
0x180011fc3  pop     r12
0x180011fc5  pop     rdi
0x180011fc6  pop     rsi
0x180011fc7  pop     rbp
0x180011fc8  pop     rbx
0x180011fc9  jmp     NormalizeNteStatus
0x180011fce  mov     r14d, [rsp+98h+cbSignature]
0x180011fd6  mov     r15, [rsp+98h+pbSignature]
0x180011fde  mov     rcx, [rdi+8]
0x180011fe2  mov     r8, rdx
0x180011fe5  mov     rdx, [rdi+10h]
0x180011fe9  mov     r9, r13
0x180011fec  mov     [rsp+98h+var_60], ebp
0x180011ff0  mov     [rsp+98h+var_68], r14d
0x180011ff5  mov     rax, [rcx+0B8h]
0x180011ffc  mov     rcx, [rcx+110h]
0x180012003  mov     [rsp+98h+var_70], r15
0x180012008  mov     [rsp+98h+var_78], r12d
0x18001200d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012012  mov     ebx, eax
0x180012014  cmp     eax, 8009002Eh
0x180012019  jz      short loc_180012086
0x18001201b  test    eax, eax
0x18001201d  jz      loc_180012112
0x180012023  mov     rcx, cs:WPP_GLOBAL_Control
0x18001202a  lea     rax, WPP_GLOBAL_Control
0x180012031  cmp     rcx, rax
0x180012034  jz      short loc_180012064
0x180012036  test    byte ptr [rcx+1Ch], 1
0x18001203a  jz      short loc_180012064
0x18001203c  mov     rcx, [rcx+10h]
0x180012040  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012047  mov     [rsp+98h+var_68], 0E58h
0x18001204f  lea     r9, aStatus; "Status"
0x180012056  mov     [rsp+98h+var_70], rax
0x18001205b  mov     [rsp+98h+var_78], ebx
0x18001205f  call    WPP_SF_sDsd
0x180012064  mov     rdx, [rdi+8]
0x180012068  mov     ecx, 7
0x18001206d  mov     r8, [rdi+18h]
0x180012071  mov     [rsp+98h+var_78], ebx
0x180012075  mov     rdx, [rdx+118h]
0x18001207c  call    EtwLogNCryptOperationFailed
0x180012081  jmp     loc_180011FB7
0x180012086  test    bpl, 40h
0x18001208a  jz      short loc_1800120D7
0x18001208c  mov     ebx, 80090022h
0x180012091  mov     rcx, cs:WPP_GLOBAL_Control
0x180012098  lea     rax, WPP_GLOBAL_Control
0x18001209f  cmp     rcx, rax
0x1800120a2  jz      loc_180011FB7
0x1800120a8  test    byte ptr [rcx+1Ch], 1
0x1800120ac  jz      loc_180011FB7
0x1800120b2  mov     rcx, [rcx+10h]
0x1800120b6  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800120bd  mov     [rsp+98h+var_68], 0E45h
0x1800120c5  mov     [rsp+98h+var_70], rax
0x1800120ca  mov     [rsp+98h+var_78], 80090022h
0x1800120d2  jmp     loc_180011FAB
0x1800120d7  mov     rcx, [rdi+8]
0x1800120db  lea     r8, aNcryptverifysi_0; "NCryptVerifySignature"
0x1800120e2  xor     r9d, r9d
0x1800120e5  mov     rdx, rsi
0x1800120e8  mov     rax, [rcx+0C0h]
0x1800120ef  mov     rcx, [rcx+110h]
0x1800120f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120fb  mov     ebx, eax
0x1800120fd  test    eax, eax
0x1800120ff  jnz     loc_180012023
0x180012105  mov     rdx, [rsp+98h+arg_8]
0x18001210d  jmp     loc_180011FDE
0x180012112  xor     ebx, ebx
0x180012114  jmp     loc_180011FB7
```
