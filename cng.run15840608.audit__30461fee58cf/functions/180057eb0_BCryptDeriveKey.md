# BCryptDeriveKey

- ea: `0x180057eb0`
- end: `0x180058066`
- name: `BCryptDeriveKey`
- size: `438`
- prototype: `NTSTATUS __stdcall(BCRYPT_SECRET_HANDLE hSharedSecret, LPCWSTR pwszKDF, BCryptBufferDesc *pParameterList, PUCHAR pbDerivedKey, ULONG cbDerivedKey, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180006470`
- `0x18000743c`
- `0x180057eb0`
- `0x18005a8b0`
- `0x18005b3e4`
- `0x18005bcac`
- `0x18009d860`

## string_xrefs

- `0x180057f46`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180057fa9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005801a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
NTSTATUS __stdcall BCryptDeriveKey(
        BCRYPT_SECRET_HANDLE hSharedSecret,
        LPCWSTR pwszKDF,
        BCryptBufferDesc *pParameterList,
        PUCHAR pbDerivedKey,
        ULONG cbDerivedKey,
        ULONG *pcbResult,
        ULONG dwFlags)
{
  BCryptBufferDesc *v7; // rbx
  NTSTATUS v12; // edi
  __int64 v13; // r9
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rbp
  __int64 v17; // rax
  __int64 (__fastcall *v18)(_QWORD, LPCWSTR, BCryptBufferDesc *, PUCHAR, ULONG, ULONG *, ULONG); // r15
  unsigned int v19; // eax
  int v20; // eax
  __int64 v21; // r9
  __int64 v22; // rcx
  PBCryptBuffer pBuffers; // rcx
  PVOID P[11]; // [rsp+50h] [rbp-58h] BYREF

  v7 = 0;
  P[0] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 4) != 0 )
    WPP_SF_qSqqDqD(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      (_DWORD)pwszKDF,
      (_DWORD)pParameterList,
      (_DWORD)hSharedSecret,
      (__int64)pwszKDF,
      (char)pParameterList,
      (char)pbDerivedKey,
      cbDerivedKey,
      (char)pcbResult,
      dwFlags);
  if ( !pcbResult )
  {
    v12 = -1073741811;
    v13 = 5356;
    v14 = 3221225485LL;
LABEL_6:
    DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v13);
    return v12;
  }
  v15 = ValidateBaseSecretHandle(hSharedSecret);
  v16 = v15;
  if ( !v15 )
  {
    v12 = -1073741816;
    v13 = 5364;
    v14 = 3221225480LL;
    goto LABEL_6;
  }
  v17 = *(_QWORD *)(v15 + 8);
  if ( *(_DWORD *)(v17 + 36) != 4 )
  {
    v12 = -1073741637;
    v21 = 5378;
    v22 = 3221225659LL;
    goto LABEL_17;
  }
  v18 = *(__int64 (__fastcall **)(_QWORD, LPCWSTR, BCryptBufferDesc *, PUCHAR, ULONG, ULONG *, ULONG))(v17 + 96);
  if ( !pParameterList )
  {
LABEL_14:
    v20 = v18(*(_QWORD *)(v16 + 16), pwszKDF, v7, pbDerivedKey, cbDerivedKey, pcbResult, dwFlags);
    v12 = v20;
    if ( v20 >= 0 )
      goto LABEL_18;
    v21 = 5404;
    v22 = (unsigned int)v20;
LABEL_17:
    DebugTraceError(v22, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", v21);
    goto LABEL_18;
  }
  v19 = ProcessBufferDescParameters((__int64)pParameterList, (__int64 *)P);
  v12 = v19;
  if ( !v19 )
  {
    v7 = (BCryptBufferDesc *)P[0];
    goto LABEL_14;
  }
  DebugTraceError(v19, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c", 5390);
  v7 = (BCryptBufferDesc *)P[0];
LABEL_18:
  if ( v7 && pParameterList != v7 )
  {
    pBuffers = v7->pBuffers;
    if ( pBuffers )
      MSCryptFree(pBuffers);
    MSCryptFree(v7);
  }
  return v12;
}

```

## disassembly

```asm
0x180057eb0  mov     r11, rsp
0x180057eb3  push    rbx
0x180057eb4  push    rbp
0x180057eb5  push    rsi
0x180057eb6  push    rdi
0x180057eb7  push    r12
0x180057eb9  push    r13
0x180057ebb  push    r14
0x180057ebd  push    r15
0x180057ebf  sub     rsp, 68h
0x180057ec3  xor     ebx, ebx
0x180057ec5  mov     r12, r9
0x180057ec8  mov     [r11-58h], rbx
0x180057ecc  mov     rsi, r8
0x180057ecf  mov     r13, rdx
0x180057ed2  mov     rdi, rcx
0x180057ed5  mov     rcx, cs:WPP_GLOBAL_Control
0x180057edc  lea     rax, WPP_GLOBAL_Control
0x180057ee3  mov     r14, [rsp+0A8h+pcbResult]
0x180057eeb  cmp     rcx, rax
0x180057eee  jz      short loc_180057F2A
0x180057ef0  mov     eax, [rcx+2Ch]
0x180057ef3  test    al, 4
0x180057ef5  jz      short loc_180057F2A
0x180057ef7  mov     eax, [rsp+0A8h+dwFlags]
0x180057efe  mov     rcx, [rcx+18h]
0x180057f02  mov     [rsp+0A8h+var_60], eax
0x180057f06  mov     eax, [rsp+0A8h+cbDerivedKey]
0x180057f0d  mov     [r11-68h], r14
0x180057f11  mov     [rsp+0A8h+var_70], eax
0x180057f15  mov     [r11-78h], r9
0x180057f19  mov     r9, rdi
0x180057f1c  mov     [r11-80h], r8
0x180057f20  mov     [rsp+0A8h+var_88], rdx
0x180057f25  call    WPP_SF_qSqqDqD
0x180057f2a  test    r14, r14
0x180057f2d  jnz     short loc_180057F57
0x180057f2f  mov     edi, 0C000000Dh
0x180057f34  mov     r9d, 14ECh
0x180057f3a  mov     ecx, 0C000000Dh
0x180057f3f  lea     rdx, aStatus; "Status"
0x180057f46  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180057f4d  call    DebugTraceError
0x180057f52  jmp     loc_180058052
0x180057f57  mov     rcx, rdi
0x180057f5a  call    ValidateBaseSecretHandle
0x180057f5f  mov     rbp, rax
0x180057f62  test    rax, rax
0x180057f65  jnz     short loc_180057F79
0x180057f67  mov     edi, 0C0000008h
0x180057f6c  mov     r9d, 14F4h
0x180057f72  mov     ecx, 0C0000008h
0x180057f77  jmp     short loc_180057F3F
0x180057f79  mov     rax, [rax+8]
0x180057f7d  cmp     dword ptr [rax+24h], 4
0x180057f81  jnz     loc_18005800A
0x180057f87  mov     r15, [rax+60h]
0x180057f8b  test    rsi, rsi
0x180057f8e  jz      short loc_180057FCA
0x180057f90  lea     rdx, [rsp+0A8h+P]
0x180057f95  mov     rcx, rsi
0x180057f98  call    _ProcessBufferDescParameters
0x180057f9d  mov     edi, eax
0x180057f9f  test    eax, eax
0x180057fa1  jz      short loc_180057FC5
0x180057fa3  mov     r9d, 150Eh
0x180057fa9  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180057fb0  lea     rdx, aStatus; "Status"
0x180057fb7  mov     ecx, eax
0x180057fb9  call    DebugTraceError
0x180057fbe  mov     rbx, [rsp+0A8h+P]
0x180057fc3  jmp     short loc_18005802D
0x180057fc5  mov     rbx, [rsp+0A8h+P]
0x180057fca  mov     eax, [rsp+0A8h+dwFlags]
0x180057fd1  mov     r9, r12
0x180057fd4  mov     rcx, [rbp+10h]
0x180057fd8  mov     r8, rbx
0x180057fdb  mov     [rsp+0A8h+var_78], eax
0x180057fdf  mov     rdx, r13
0x180057fe2  mov     eax, [rsp+0A8h+cbDerivedKey]
0x180057fe9  mov     [rsp+0A8h+var_80], r14
0x180057fee  mov     dword ptr [rsp+0A8h+var_88], eax
0x180057ff2  mov     rax, r15
0x180057ff5  call    _guard_dispatch_icall
0x180057ffa  mov     edi, eax
0x180057ffc  test    eax, eax
0x180057ffe  jns     short loc_18005802D
0x180058000  mov     r9d, 151Ch
0x180058006  mov     ecx, eax
0x180058008  jmp     short loc_18005801A
0x18005800a  mov     edi, 0C00000BBh
0x18005800f  mov     r9d, 1502h
0x180058015  mov     ecx, 0C00000BBh
0x18005801a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058021  lea     rdx, aStatus; "Status"
0x180058028  call    DebugTraceError
0x18005802d  test    rbx, rbx
0x180058030  jz      short loc_180058052
0x180058032  cmp     rsi, rbx
0x180058035  jz      short loc_180058052
0x180058037  test    rbx, rbx
0x18005803a  jz      short loc_180058052
0x18005803c  mov     rcx, [rbx+8]; P
0x180058040  test    rcx, rcx
0x180058043  jz      short loc_18005804A
0x180058045  call    MSCryptFree
0x18005804a  mov     rcx, rbx; P
0x18005804d  call    MSCryptFree
0x180058052  mov     eax, edi
0x180058054  add     rsp, 68h
0x180058058  pop     r15
0x18005805a  pop     r14
0x18005805c  pop     r13
0x18005805e  pop     r12
0x180058060  pop     rdi
0x180058061  pop     rsi
0x180058062  pop     rbp
0x180058063  pop     rbx
0x180058064  retn
```
