# BCryptGenSystemPreferredRandom

- ea: `0x18000e104`
- end: `0x18000e1fc`
- name: `BCryptGenSystemPreferredRandom`
- size: `248`
- prototype: `__int64 __fastcall(PUCHAR pbBuffer, ULONG cbBuffer, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000d440`

## callees

- `0x18000d440`
- `0x18000e104`
- `0x18000e204`
- `0x1800123d0`
- `0x18002eb64`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x18000e174`
- `ntoskrnl!ExReleaseResourceLite` at `0x18000e174`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000e180`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000e180`

## string_xrefs

- `0x18000e1c9`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

## pseudocode

```c
__int64 __fastcall BCryptGenSystemPreferredRandom(PUCHAR pbBuffer, ULONG cbBuffer, ULONG dwFlags)
{
  char TrustedEnvironment; // al
  int SystemPreferredRngHandle; // ebx
  __int64 v8; // rcx
  int v9; // edi
  int v10; // edx
  int v11; // r8d
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+78h] [rbp+20h] BYREF

  TrustedEnvironment = g_TrustedEnvironment;
  hAlgorithm = 0;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 1) != 0 )
  {
    SystemPreferredRngHandle = GetSystemPreferredRngHandle(&hAlgorithm);
    if ( SystemPreferredRngHandle < 0 )
      return (unsigned int)SystemPreferredRngHandle;
    v8 = (__int64)hAlgorithm;
    v9 = 1;
  }
  else
  {
    v9 = 0;
    v8 = 129;
  }
  SystemPreferredRngHandle = BCryptGenRandom((BCRYPT_ALG_HANDLE)v8, pbBuffer, cbBuffer, dwFlags);
  if ( SystemPreferredRngHandle < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v10,
        v11,
        (unsigned int)"Status",
        SystemPreferredRngHandle,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\syspref.c",
        50);
  }
  else
  {
    SystemPreferredRngHandle = 0;
  }
  if ( v9 )
  {
    ExReleaseResourceLite(g_pCachedRngRWLock);
    KeLeaveCriticalRegion();
  }
  return (unsigned int)SystemPreferredRngHandle;
}

```

## disassembly

```asm
0x18000e104  mov     [rsp+arg_0], rbx
0x18000e109  mov     [rsp+arg_8], rbp
0x18000e10e  push    rsi
0x18000e10f  push    rdi
0x18000e110  push    r14
0x18000e112  sub     rsp, 40h
0x18000e116  mov     eax, cs:g_TrustedEnvironment
0x18000e11c  mov     esi, r8d
0x18000e11f  mov     [rsp+58h+hAlgorithm], 0
0x18000e128  mov     ebp, edx
0x18000e12a  mov     r14, rcx
0x18000e12d  test    eax, eax
0x18000e12f  jz      loc_18000E1F2
0x18000e135  test    al, 1
0x18000e137  jz      short loc_18000E1A2
0x18000e139  lea     rcx, [rsp+58h+hAlgorithm]
0x18000e13e  call    GetSystemPreferredRngHandle
0x18000e143  mov     ebx, eax
0x18000e145  test    eax, eax
0x18000e147  js      short loc_18000E18C
0x18000e149  mov     rcx, [rsp+58h+hAlgorithm]; hAlgorithm
0x18000e14e  mov     edi, 1
0x18000e153  mov     r9d, esi; dwFlags
0x18000e156  mov     r8d, ebp; cbBuffer
0x18000e159  mov     rdx, r14; pbBuffer
0x18000e15c  call    BCryptGenRandom
0x18000e161  mov     ebx, eax
0x18000e163  test    eax, eax
0x18000e165  js      short loc_18000E1AB
0x18000e167  xor     ebx, ebx
0x18000e169  test    edi, edi
0x18000e16b  jz      short loc_18000E18C
0x18000e16d  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x18000e174  call    cs:__imp_ExReleaseResourceLite
0x18000e17b  nop     dword ptr [rax+rax+00h]
0x18000e180  call    cs:__imp_KeLeaveCriticalRegion
0x18000e187  nop     dword ptr [rax+rax+00h]
0x18000e18c  mov     rbp, [rsp+58h+arg_8]
0x18000e191  mov     eax, ebx
0x18000e193  mov     rbx, [rsp+58h+arg_0]
0x18000e198  add     rsp, 40h
0x18000e19c  pop     r14
0x18000e19e  pop     rdi
0x18000e19f  pop     rsi
0x18000e1a0  retn
0x18000e1a2  xor     edi, edi
0x18000e1a4  mov     ecx, 81h
0x18000e1a9  jmp     short loc_18000E153
0x18000e1ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e1b2  lea     rax, WPP_GLOBAL_Control
0x18000e1b9  cmp     rcx, rax
0x18000e1bc  jz      short loc_18000E169
0x18000e1be  mov     eax, [rcx+2Ch]
0x18000e1c1  test    al, 1
0x18000e1c3  jz      short loc_18000E169
0x18000e1c5  mov     rcx, [rcx+18h]
0x18000e1c9  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e1d0  mov     [rsp+58h+var_28], 232h
0x18000e1d8  lea     r9, aStatus; "Status"
0x18000e1df  mov     [rsp+58h+var_30], rax
0x18000e1e4  mov     [rsp+58h+var_38], ebx
0x18000e1e8  call    WPP_SF_sDsd
0x18000e1ed  jmp     loc_18000E169
0x18000e1f2  call    GetTrustedEnvironment
0x18000e1f7  jmp     loc_18000E135
```
