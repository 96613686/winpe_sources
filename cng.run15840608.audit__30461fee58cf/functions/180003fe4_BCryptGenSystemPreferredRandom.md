# BCryptGenSystemPreferredRandom

- ea: `0x180003fe4`
- end: `0x1800040dc`
- name: `BCryptGenSystemPreferredRandom`
- size: `248`
- prototype: `__int64 __fastcall(PUCHAR pbBuffer, ULONG cbBuffer, ULONG dwFlags)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180003320`

## callees

- `0x180003320`
- `0x180003fe4`
- `0x1800040e4`
- `0x1800082b0`
- `0x180024a34`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x180004054`
- `ntoskrnl!ExReleaseResourceLite` at `0x180004054`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180004060`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180004060`

## string_xrefs

- `0x1800040a9`: `onecore\ds\security\cryptoapi\ncrypt\common\syspref.c`

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
0x180003fe4  mov     [rsp+arg_0], rbx
0x180003fe9  mov     [rsp+arg_8], rbp
0x180003fee  push    rsi
0x180003fef  push    rdi
0x180003ff0  push    r14
0x180003ff2  sub     rsp, 40h
0x180003ff6  mov     eax, cs:g_TrustedEnvironment
0x180003ffc  mov     esi, r8d
0x180003fff  mov     [rsp+58h+hAlgorithm], 0
0x180004008  mov     ebp, edx
0x18000400a  mov     r14, rcx
0x18000400d  test    eax, eax
0x18000400f  jz      loc_1800040D2
0x180004015  test    al, 1
0x180004017  jz      short loc_180004082
0x180004019  lea     rcx, [rsp+58h+hAlgorithm]
0x18000401e  call    GetSystemPreferredRngHandle
0x180004023  mov     ebx, eax
0x180004025  test    eax, eax
0x180004027  js      short loc_18000406C
0x180004029  mov     rcx, [rsp+58h+hAlgorithm]; hAlgorithm
0x18000402e  mov     edi, 1
0x180004033  mov     r9d, esi; dwFlags
0x180004036  mov     r8d, ebp; cbBuffer
0x180004039  mov     rdx, r14; pbBuffer
0x18000403c  call    BCryptGenRandom
0x180004041  mov     ebx, eax
0x180004043  test    eax, eax
0x180004045  js      short loc_18000408B
0x180004047  xor     ebx, ebx
0x180004049  test    edi, edi
0x18000404b  jz      short loc_18000406C
0x18000404d  mov     rcx, cs:g_pCachedRngRWLock; Resource
0x180004054  call    cs:__imp_ExReleaseResourceLite
0x18000405b  nop     dword ptr [rax+rax+00h]
0x180004060  call    cs:__imp_KeLeaveCriticalRegion
0x180004067  nop     dword ptr [rax+rax+00h]
0x18000406c  mov     rbp, [rsp+58h+arg_8]
0x180004071  mov     eax, ebx
0x180004073  mov     rbx, [rsp+58h+arg_0]
0x180004078  add     rsp, 40h
0x18000407c  pop     r14
0x18000407e  pop     rdi
0x18000407f  pop     rsi
0x180004080  retn
0x180004082  xor     edi, edi
0x180004084  mov     ecx, 81h
0x180004089  jmp     short loc_180004033
0x18000408b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004092  lea     rax, WPP_GLOBAL_Control
0x180004099  cmp     rcx, rax
0x18000409c  jz      short loc_180004049
0x18000409e  mov     eax, [rcx+2Ch]
0x1800040a1  test    al, 1
0x1800040a3  jz      short loc_180004049
0x1800040a5  mov     rcx, [rcx+18h]
0x1800040a9  lea     rax, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800040b0  mov     [rsp+58h+var_28], 232h
0x1800040b8  lea     r9, aStatus; "Status"
0x1800040bf  mov     [rsp+58h+var_30], rax
0x1800040c4  mov     [rsp+58h+var_38], ebx
0x1800040c8  call    WPP_SF_sDsd
0x1800040cd  jmp     loc_180004049
0x1800040d2  call    GetTrustedEnvironment
0x1800040d7  jmp     loc_180004015
```
