# BCryptDeriveKey

- ea: `0x180062080`
- end: `0x180062236`
- name: `BCryptDeriveKey`
- size: `438`
- prototype: `NTSTATUS __stdcall(BCRYPT_SECRET_HANDLE hSharedSecret, LPCWSTR pwszKDF, BCryptBufferDesc *pParameterList, PUCHAR pbDerivedKey, ULONG cbDerivedKey, ULONG *pcbResult, ULONG dwFlags)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180010590`
- `0x18001155c`
- `0x180062080`
- `0x180064a80`
- `0x1800655b4`
- `0x180065e7c`
- `0x1800a4300`

## string_xrefs

- `0x180062116`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x180062179`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x1800621ea`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

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
0x180062080  mov     r11, rsp
0x180062083  push    rbx
0x180062084  push    rbp
0x180062085  push    rsi
0x180062086  push    rdi
0x180062087  push    r12
0x180062089  push    r13
0x18006208b  push    r14
0x18006208d  push    r15
0x18006208f  sub     rsp, 68h
0x180062093  xor     ebx, ebx
0x180062095  mov     r12, r9
0x180062098  mov     [r11-58h], rbx
0x18006209c  mov     rsi, r8
0x18006209f  mov     r13, rdx
0x1800620a2  mov     rdi, rcx
0x1800620a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800620ac  lea     rax, WPP_GLOBAL_Control
0x1800620b3  mov     r14, [rsp+0A8h+pcbResult]
0x1800620bb  cmp     rcx, rax
0x1800620be  jz      short loc_1800620FA
0x1800620c0  mov     eax, [rcx+2Ch]
0x1800620c3  test    al, 4
0x1800620c5  jz      short loc_1800620FA
0x1800620c7  mov     eax, [rsp+0A8h+dwFlags]
0x1800620ce  mov     rcx, [rcx+18h]
0x1800620d2  mov     [rsp+0A8h+var_60], eax
0x1800620d6  mov     eax, [rsp+0A8h+cbDerivedKey]
0x1800620dd  mov     [r11-68h], r14
0x1800620e1  mov     [rsp+0A8h+var_70], eax
0x1800620e5  mov     [r11-78h], r9
0x1800620e9  mov     r9, rdi
0x1800620ec  mov     [r11-80h], r8
0x1800620f0  mov     [rsp+0A8h+var_88], rdx
0x1800620f5  call    WPP_SF_qSqqDqD
0x1800620fa  test    r14, r14
0x1800620fd  jnz     short loc_180062127
0x1800620ff  mov     edi, 0C000000Dh
0x180062104  mov     r9d, 14ECh
0x18006210a  mov     ecx, 0C000000Dh
0x18006210f  lea     rdx, aStatus; "Status"
0x180062116  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006211d  call    DebugTraceError
0x180062122  jmp     loc_180062222
0x180062127  mov     rcx, rdi
0x18006212a  call    ValidateBaseSecretHandle
0x18006212f  mov     rbp, rax
0x180062132  test    rax, rax
0x180062135  jnz     short loc_180062149
0x180062137  mov     edi, 0C0000008h
0x18006213c  mov     r9d, 14F4h
0x180062142  mov     ecx, 0C0000008h
0x180062147  jmp     short loc_18006210F
0x180062149  mov     rax, [rax+8]
0x18006214d  cmp     dword ptr [rax+24h], 4
0x180062151  jnz     loc_1800621DA
0x180062157  mov     r15, [rax+60h]
0x18006215b  test    rsi, rsi
0x18006215e  jz      short loc_18006219A
0x180062160  lea     rdx, [rsp+0A8h+P]
0x180062165  mov     rcx, rsi
0x180062168  call    _ProcessBufferDescParameters
0x18006216d  mov     edi, eax
0x18006216f  test    eax, eax
0x180062171  jz      short loc_180062195
0x180062173  mov     r9d, 150Eh
0x180062179  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180062180  lea     rdx, aStatus; "Status"
0x180062187  mov     ecx, eax
0x180062189  call    DebugTraceError
0x18006218e  mov     rbx, [rsp+0A8h+P]
0x180062193  jmp     short loc_1800621FD
0x180062195  mov     rbx, [rsp+0A8h+P]
0x18006219a  mov     eax, [rsp+0A8h+dwFlags]
0x1800621a1  mov     r9, r12
0x1800621a4  mov     rcx, [rbp+10h]
0x1800621a8  mov     r8, rbx
0x1800621ab  mov     [rsp+0A8h+var_78], eax
0x1800621af  mov     rdx, r13
0x1800621b2  mov     eax, [rsp+0A8h+cbDerivedKey]
0x1800621b9  mov     [rsp+0A8h+var_80], r14
0x1800621be  mov     dword ptr [rsp+0A8h+var_88], eax
0x1800621c2  mov     rax, r15
0x1800621c5  call    _guard_dispatch_icall
0x1800621ca  mov     edi, eax
0x1800621cc  test    eax, eax
0x1800621ce  jns     short loc_1800621FD
0x1800621d0  mov     r9d, 151Ch
0x1800621d6  mov     ecx, eax
0x1800621d8  jmp     short loc_1800621EA
0x1800621da  mov     edi, 0C00000BBh
0x1800621df  mov     r9d, 1502h
0x1800621e5  mov     ecx, 0C00000BBh
0x1800621ea  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800621f1  lea     rdx, aStatus; "Status"
0x1800621f8  call    DebugTraceError
0x1800621fd  test    rbx, rbx
0x180062200  jz      short loc_180062222
0x180062202  cmp     rsi, rbx
0x180062205  jz      short loc_180062222
0x180062207  test    rbx, rbx
0x18006220a  jz      short loc_180062222
0x18006220c  mov     rcx, [rbx+8]; P
0x180062210  test    rcx, rcx
0x180062213  jz      short loc_18006221A
0x180062215  call    MSCryptFree
0x18006221a  mov     rcx, rbx; P
0x18006221d  call    MSCryptFree
0x180062222  mov     eax, edi
0x180062224  add     rsp, 68h
0x180062228  pop     r15
0x18006222a  pop     r14
0x18006222c  pop     r13
0x18006222e  pop     r12
0x180062230  pop     rdi
0x180062231  pop     rsi
0x180062232  pop     rbp
0x180062233  pop     rbx
0x180062234  retn
```
