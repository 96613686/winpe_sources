# BCryptDeriveKey

- ea: `0x1800587a0`
- end: `0x180058956`
- name: `BCryptDeriveKey`
- size: `438`
- prototype: `NTSTATUS __stdcall(BCRYPT_SECRET_HANDLE hSharedSecret, LPCWSTR pwszKDF, BCryptBufferDesc *pParameterList, PUCHAR pbDerivedKey, ULONG cbDerivedKey, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180006470`
- `0x18000743c`
- `0x1800587a0`
- `0x18005b1a0`
- `0x18005bcd4`
- `0x18005c59c`
- `0x18009f6d0`

## string_xrefs

- `0x180058836`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180058899`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18005890a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
  v19 = ProcessBufferDescParameters(pParameterList, P);
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
0x1800587a0  mov     r11, rsp
0x1800587a3  push    rbx
0x1800587a4  push    rbp
0x1800587a5  push    rsi
0x1800587a6  push    rdi
0x1800587a7  push    r12
0x1800587a9  push    r13
0x1800587ab  push    r14
0x1800587ad  push    r15
0x1800587af  sub     rsp, 68h
0x1800587b3  xor     ebx, ebx
0x1800587b5  mov     r12, r9
0x1800587b8  mov     [r11-58h], rbx
0x1800587bc  mov     rsi, r8
0x1800587bf  mov     r13, rdx
0x1800587c2  mov     rdi, rcx
0x1800587c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800587cc  lea     rax, WPP_GLOBAL_Control
0x1800587d3  mov     r14, [rsp+0A8h+pcbResult]
0x1800587db  cmp     rcx, rax
0x1800587de  jz      short loc_18005881A
0x1800587e0  mov     eax, [rcx+2Ch]
0x1800587e3  test    al, 4
0x1800587e5  jz      short loc_18005881A
0x1800587e7  mov     eax, [rsp+0A8h+dwFlags]
0x1800587ee  mov     rcx, [rcx+18h]
0x1800587f2  mov     [rsp+0A8h+var_60], eax
0x1800587f6  mov     eax, [rsp+0A8h+cbDerivedKey]
0x1800587fd  mov     [r11-68h], r14
0x180058801  mov     [rsp+0A8h+var_70], eax
0x180058805  mov     [r11-78h], r9
0x180058809  mov     r9, rdi
0x18005880c  mov     [r11-80h], r8
0x180058810  mov     [rsp+0A8h+var_88], rdx
0x180058815  call    WPP_SF_qSqqDqD
0x18005881a  test    r14, r14
0x18005881d  jnz     short loc_180058847
0x18005881f  mov     edi, 0C000000Dh
0x180058824  mov     r9d, 14ECh
0x18005882a  mov     ecx, 0C000000Dh
0x18005882f  lea     rdx, aStatus; "Status"
0x180058836  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005883d  call    DebugTraceError
0x180058842  jmp     loc_180058942
0x180058847  mov     rcx, rdi
0x18005884a  call    ValidateBaseSecretHandle
0x18005884f  mov     rbp, rax
0x180058852  test    rax, rax
0x180058855  jnz     short loc_180058869
0x180058857  mov     edi, 0C0000008h
0x18005885c  mov     r9d, 14F4h
0x180058862  mov     ecx, 0C0000008h
0x180058867  jmp     short loc_18005882F
0x180058869  mov     rax, [rax+8]
0x18005886d  cmp     dword ptr [rax+24h], 4
0x180058871  jnz     loc_1800588FA
0x180058877  mov     r15, [rax+60h]
0x18005887b  test    rsi, rsi
0x18005887e  jz      short loc_1800588BA
0x180058880  lea     rdx, [rsp+0A8h+P]
0x180058885  mov     rcx, rsi
0x180058888  call    _ProcessBufferDescParameters
0x18005888d  mov     edi, eax
0x18005888f  test    eax, eax
0x180058891  jz      short loc_1800588B5
0x180058893  mov     r9d, 150Eh
0x180058899  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800588a0  lea     rdx, aStatus; "Status"
0x1800588a7  mov     ecx, eax
0x1800588a9  call    DebugTraceError
0x1800588ae  mov     rbx, [rsp+0A8h+P]
0x1800588b3  jmp     short loc_18005891D
0x1800588b5  mov     rbx, [rsp+0A8h+P]
0x1800588ba  mov     eax, [rsp+0A8h+dwFlags]
0x1800588c1  mov     r9, r12
0x1800588c4  mov     rcx, [rbp+10h]
0x1800588c8  mov     r8, rbx
0x1800588cb  mov     [rsp+0A8h+var_78], eax
0x1800588cf  mov     rdx, r13
0x1800588d2  mov     eax, [rsp+0A8h+cbDerivedKey]
0x1800588d9  mov     [rsp+0A8h+var_80], r14
0x1800588de  mov     dword ptr [rsp+0A8h+var_88], eax
0x1800588e2  mov     rax, r15
0x1800588e5  call    _guard_dispatch_icall
0x1800588ea  mov     edi, eax
0x1800588ec  test    eax, eax
0x1800588ee  jns     short loc_18005891D
0x1800588f0  mov     r9d, 151Ch
0x1800588f6  mov     ecx, eax
0x1800588f8  jmp     short loc_18005890A
0x1800588fa  mov     edi, 0C00000BBh
0x1800588ff  mov     r9d, 1502h
0x180058905  mov     ecx, 0C00000BBh
0x18005890a  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180058911  lea     rdx, aStatus; "Status"
0x180058918  call    DebugTraceError
0x18005891d  test    rbx, rbx
0x180058920  jz      short loc_180058942
0x180058922  cmp     rsi, rbx
0x180058925  jz      short loc_180058942
0x180058927  test    rbx, rbx
0x18005892a  jz      short loc_180058942
0x18005892c  mov     rcx, [rbx+8]; P
0x180058930  test    rcx, rcx
0x180058933  jz      short loc_18005893A
0x180058935  call    MSCryptFree
0x18005893a  mov     rcx, rbx; P
0x18005893d  call    MSCryptFree
0x180058942  mov     eax, edi
0x180058944  add     rsp, 68h
0x180058948  pop     r15
0x18005894a  pop     r14
0x18005894c  pop     r13
0x18005894e  pop     r12
0x180058950  pop     rdi
0x180058951  pop     rsi
0x180058952  pop     rbp
0x180058953  pop     rbx
0x180058954  retn
```
