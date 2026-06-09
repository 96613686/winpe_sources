# CNG_EncryptAndAllocate

- ea: `0x180003ce4`
- end: `0x180003f14`
- name: `CNG_EncryptAndAllocate`
- size: `560`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800050d0`

## callees

- `0x180003ce4`
- `0x18000d02c`
- `0x18000e120`
- `0x18001f15d`
- `0x180020010`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x180003d5c`
- `bcrypt!BCryptEncrypt` at `0x180003dd3`
- `bcrypt!BCryptEncrypt` at `0x180003d5c`
- `bcrypt!BCryptEncrypt` at `0x180003dd3`

## string_xrefs

- `0x180003e58`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x180003ea8`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`
- `0x180003ef2`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptcms\util.c`

## pseudocode

```c
__int64 __fastcall CNG_EncryptAndAllocate(__int64 a1, UCHAR *a2, ULONG a3, UCHAR **a4, _DWORD *a5)
{
  _DWORD *v5; // r15
  bool v8; // zf
  const void *v11; // rbp
  unsigned int v12; // esi
  int v13; // edx
  unsigned int cbIV; // ebx
  int v15; // r8d
  UCHAR *v16; // rax
  __int64 v18; // rax
  _QWORD *v19; // rcx
  char pbOutput; // [rsp+30h] [rbp-68h]
  ULONG pcbResult; // [rsp+A0h] [rbp+8h] BYREF

  v5 = a5;
  v8 = (*(_DWORD *)(a1 + 112) & 0x10000000) == 0;
  pcbResult = 0;
  *a5 = 0;
  v11 = 0;
  v12 = 0;
  *a4 = 0;
  if ( v8 )
  {
LABEL_2:
    cbIV = BCryptEncrypt(
             *(BCRYPT_KEY_HANDLE *)(a1 + 16),
             a2,
             a3,
             *(void **)(a1 + 72),
             0,
             0,
             0,
             0,
             &pcbResult,
             *(_DWORD *)(*(_QWORD *)(a1 + 24) + 72LL));
    if ( cbIV )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return cbIV;
      pbOutput = 112;
    }
    else
    {
      v16 = (UCHAR *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)a1 + 8LL))(v12 + pcbResult);
      *a4 = v16;
      if ( !v16 )
      {
        cbIV = -2146893810;
        DebugTraceError(
          2148073486LL,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
          1144);
        return cbIV;
      }
      cbIV = BCryptEncrypt(
               *(BCRYPT_KEY_HANDLE *)(a1 + 16),
               a2,
               a3,
               *(void **)(a1 + 72),
               0,
               cbIV,
               v16,
               pcbResult,
               &pcbResult,
               *(_DWORD *)(*(_QWORD *)(a1 + 24) + 72LL));
      if ( !cbIV )
      {
        if ( v11 && v12 )
          memcpy_0(&(*a4)[pcbResult], v11, v12);
        *v5 = v12 + pcbResult;
        return 0;
      }
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return cbIV;
      pbOutput = -118;
    }
    WPP_SF_sDsd(
      v19[2],
      v13,
      v15,
      (unsigned int)"Status",
      cbIV,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
      pbOutput);
    return cbIV;
  }
  if ( *(_DWORD *)(a1 + 64) >= 0x98u )
  {
    v18 = *(_QWORD *)(a1 + 72);
    v11 = *(const void **)(v18 + 40);
    v12 = *(_DWORD *)(v18 + 48);
    goto LABEL_2;
  }
  cbIV = -2146893779;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      0,
      a3,
      (unsigned int)"Status",
      45,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptcms\\util.c",
      88);
  return cbIV;
}

```

## disassembly

```asm
0x180003ce4  mov     rax, rsp
0x180003ce7  push    rbx
0x180003ce8  push    rbp
0x180003ce9  push    rsi
0x180003cea  push    rdi
0x180003ceb  push    r12
0x180003ced  push    r13
0x180003cef  push    r14
0x180003cf1  push    r15
0x180003cf3  sub     rsp, 58h
0x180003cf7  mov     r15, [rsp+98h+arg_20]
0x180003cff  mov     r13, rdx
0x180003d02  xor     edx, edx
0x180003d04  mov     r14, r9
0x180003d07  test    dword ptr [rcx+70h], 10000000h
0x180003d0e  mov     r12d, r8d
0x180003d11  mov     rdi, rcx
0x180003d14  mov     [rax+8], edx
0x180003d17  mov     [r15], edx
0x180003d1a  mov     ebp, edx
0x180003d1c  mov     esi, edx
0x180003d1e  mov     [r9], rdx
0x180003d21  jnz     loc_180003E1E
0x180003d27  mov     rax, [rcx+18h]
0x180003d2b  mov     r9, [rdi+48h]; pPaddingInfo
0x180003d2f  mov     ecx, [rax+48h]
0x180003d32  lea     rax, [rsp+98h+arg_0]
0x180003d3a  mov     [rsp+98h+dwFlags], ecx; dwFlags
0x180003d3e  mov     rcx, [rdi+10h]; hKey
0x180003d42  mov     [rsp+98h+pcbResult], rax; pcbResult
0x180003d47  mov     [rsp+98h+cbOutput], edx; cbOutput
0x180003d4b  mov     [rsp+98h+pbOutput], rdx; pbOutput
0x180003d50  mov     [rsp+98h+cbIV], edx; cbIV
0x180003d54  mov     [rsp+98h+pbIV], rdx; pbIV
0x180003d59  mov     rdx, r13; pbInput
0x180003d5c  call    cs:__imp_BCryptEncrypt
0x180003d62  mov     ebx, eax
0x180003d64  test    eax, eax
0x180003d66  jnz     loc_180003EBE
0x180003d6c  mov     rdx, [rdi]
0x180003d6f  mov     ecx, [rsp+98h+arg_0]
0x180003d76  add     ecx, esi
0x180003d78  mov     rax, [rdx+8]
0x180003d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d81  mov     [r14], rax
0x180003d84  mov     rdx, rax
0x180003d87  test    rax, rax
0x180003d8a  jz      loc_180003EEC
0x180003d90  mov     rax, [rdi+18h]
0x180003d94  mov     r8d, r12d; cbInput
0x180003d97  mov     r9, [rdi+48h]; pPaddingInfo
0x180003d9b  mov     ecx, [rax+48h]
0x180003d9e  lea     rax, [rsp+98h+arg_0]
0x180003da6  mov     [rsp+98h+dwFlags], ecx; dwFlags
0x180003daa  mov     rcx, [rdi+10h]; hKey
0x180003dae  mov     [rsp+98h+pcbResult], rax; pcbResult
0x180003db3  mov     eax, [rsp+98h+arg_0]
0x180003dba  mov     [rsp+98h+cbOutput], eax; cbOutput
0x180003dbe  mov     [rsp+98h+pbOutput], rdx; pbOutput
0x180003dc3  mov     rdx, r13; pbInput
0x180003dc6  mov     [rsp+98h+cbIV], ebx; cbIV
0x180003dca  mov     [rsp+98h+pbIV], 0; pbIV
0x180003dd3  call    cs:__imp_BCryptEncrypt
0x180003dd9  mov     ebx, eax
0x180003ddb  test    eax, eax
0x180003ddd  jnz     short loc_180003E37
0x180003ddf  test    rbp, rbp
0x180003de2  jz      short loc_180003DFD
0x180003de4  test    esi, esi
0x180003de6  jz      short loc_180003DFD
0x180003de8  mov     ecx, [rsp+98h+arg_0]
0x180003def  mov     rdx, rbp; Src
0x180003df2  add     rcx, [r14]; void *
0x180003df5  mov     r8d, esi; Size
0x180003df8  call    memcpy_0
0x180003dfd  mov     ecx, [rsp+98h+arg_0]
0x180003e04  add     ecx, esi
0x180003e06  mov     [r15], ecx
0x180003e09  xor     ebx, ebx
0x180003e0b  mov     eax, ebx
0x180003e0d  add     rsp, 58h
0x180003e11  pop     r15
0x180003e13  pop     r14
0x180003e15  pop     r13
0x180003e17  pop     r12
0x180003e19  pop     rdi
0x180003e1a  pop     rsi
0x180003e1b  pop     rbp
0x180003e1c  pop     rbx
0x180003e1d  retn
0x180003e1e  cmp     dword ptr [rcx+40h], 98h
0x180003e25  jb      short loc_180003E7A
0x180003e27  mov     rax, [rcx+48h]
0x180003e2b  mov     rbp, [rax+28h]
0x180003e2f  mov     esi, [rax+30h]
0x180003e32  jmp     loc_180003D27
0x180003e37  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e3e  lea     rax, WPP_GLOBAL_Control
0x180003e45  cmp     rcx, rax
0x180003e48  jz      short loc_180003E0B
0x180003e4a  test    byte ptr [rcx+1Ch], 1
0x180003e4e  jz      short loc_180003E0B
0x180003e50  mov     dword ptr [rsp+98h+pbOutput], 48Ah
0x180003e58  lea     rax, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003e5f  mov     qword ptr [rsp+98h+cbIV], rax
0x180003e64  mov     dword ptr [rsp+98h+pbIV], ebx
0x180003e68  mov     rcx, [rcx+10h]
0x180003e6c  lea     r9, aStatus; "Status"
0x180003e73  call    WPP_SF_sDsd
0x180003e78  jmp     short loc_180003E0B
0x180003e7a  mov     ebx, 8009002Dh
0x180003e7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e86  lea     rax, WPP_GLOBAL_Control
0x180003e8d  cmp     rcx, rax
0x180003e90  jz      loc_180003E0B
0x180003e96  test    byte ptr [rcx+1Ch], 1
0x180003e9a  jz      loc_180003E0B
0x180003ea0  mov     dword ptr [rsp+98h+pbOutput], 458h
0x180003ea8  lea     rax, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003eaf  mov     qword ptr [rsp+98h+cbIV], rax
0x180003eb4  mov     dword ptr [rsp+98h+pbIV], 8009002Dh
0x180003ebc  jmp     short loc_180003E68
0x180003ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ec5  lea     rax, WPP_GLOBAL_Control
0x180003ecc  cmp     rcx, rax
0x180003ecf  jz      loc_180003E0B
0x180003ed5  test    byte ptr [rcx+1Ch], 1
0x180003ed9  jz      loc_180003E0B
0x180003edf  mov     dword ptr [rsp+98h+pbOutput], 470h
0x180003ee7  jmp     loc_180003E58
0x180003eec  mov     r9d, 478h
0x180003ef2  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003ef9  lea     rdx, aStatus; "Status"
0x180003f00  mov     ecx, 8009000Eh
0x180003f05  mov     ebx, 8009000Eh
0x180003f0a  call    DebugTraceError
0x180003f0f  jmp     loc_180003E0B
```
