# UninitializeCNGProv

- ea: `0x18002247c`
- end: `0x18002259b`
- name: `UninitializeCNGProv`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021fc4`
- `0x1800222fc`

## callees

- `0x18001810c`
- `0x180018514`
- `0x18001d350`
- `0x18002247c`
- `0x180024af4`
- `0x180025f84`
- `0x180028a98`
- `0x180046740`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x180022537`
- `ntdll!RtlDeleteCriticalSection` at `0x180022537`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800224fe`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800224fe`

## pseudocode

```c
__int64 UninitializeCNGProv()
{
  int v0; // edx
  int v1; // r8d
  __int64 v2; // rcx
  __int64 i; // rbx
  void *v4; // rcx
  char v5; // cl
  __int64 result; // rax

  BCryptIsoUninitialize();
  if ( IsInLSAProcess() )
    BCryptIsoUntrackKeyguardRegistryData();
  v2 = (unsigned int)dword_180079D20;
  if ( (dword_180079D20 & 4) != 0 )
  {
    _InterlockedCompareExchange(&dword_18007A670, 0, 1);
    v2 = dword_180079D20 & 0xFFFFFFFB;
    dword_180079D20 &= ~4u;
  }
  if ( (v2 & 2) != 0 )
  {
    MSProvModuleUninit();
    v2 = dword_180079D20 & 0xFFFFFFFD;
    dword_180079D20 &= ~2u;
  }
  if ( (v2 & 8) != 0 )
  {
    SKCacheUninit(v2, v0, v1);
    dword_180079D20 &= ~8u;
  }
  for ( i = 0; i != 43; ++i )
  {
    v4 = (void *)qword_180079F90[i];
    if ( v4 )
    {
      BCryptCloseAlgorithmProvider(v4, 0);
      qword_180079F90[i] = 0;
    }
  }
  v5 = dword_180079D20;
  if ( (dword_180079D20 & 1) != 0 )
  {
    if ( dword_18007A0E8 )
    {
      RtlDeleteCriticalSection(&stru_18007A1C0);
      dword_18007A0E8 = 0;
    }
    v5 = dword_180079D20 & 0xFE;
    dword_180079D20 &= ~1u;
  }
  if ( (v5 & 0x10) != 0 )
  {
    EphemeralKeyTableUninit();
    dword_180079D20 &= ~0x10u;
  }
  TlgUnregisterAggregateProvider(&dword_180079068);
  result = TlgUnregisterAggregateProvider(&dword_1800790F0);
  g_fLoadCNGDone = 0;
  return result;
}

```

## disassembly

```asm
0x18002247c  mov     [rsp+arg_0], rbx
0x180022481  push    rsi
0x180022482  sub     rsp, 20h
0x180022486  call    BCryptIsoUninitialize
0x18002248b  call    IsInLSAProcess
0x180022490  test    eax, eax
0x180022492  jz      short loc_180022499
0x180022494  call    BCryptIsoUntrackKeyguardRegistryData
0x180022499  mov     ecx, cs:dword_180079D20
0x18002249f  test    cl, 4
0x1800224a2  jz      short loc_1800224C0
0x1800224a4  xor     ecx, ecx
0x1800224a6  lea     eax, [rcx+1]
0x1800224a9  lock cmpxchg cs:dword_18007A670, ecx
0x1800224b1  mov     ecx, cs:dword_180079D20
0x1800224b7  and     ecx, 0FFFFFFFBh
0x1800224ba  mov     cs:dword_180079D20, ecx
0x1800224c0  test    cl, 2
0x1800224c3  jz      short loc_1800224D9
0x1800224c5  call    MSProvModuleUninit
0x1800224ca  mov     ecx, cs:dword_180079D20
0x1800224d0  and     ecx, 0FFFFFFFDh
0x1800224d3  mov     cs:dword_180079D20, ecx
0x1800224d9  test    cl, 8
0x1800224dc  jz      short loc_1800224EA
0x1800224de  call    SKCacheUninit
0x1800224e3  and     cs:dword_180079D20, 0FFFFFFF7h
0x1800224ea  xor     ebx, ebx
0x1800224ec  lea     rsi, qword_180079F90
0x1800224f3  mov     rcx, [rsi+rbx*8]; hAlgorithm
0x1800224f7  test    rcx, rcx
0x1800224fa  jz      short loc_180022512
0x1800224fc  xor     edx, edx; dwFlags
0x1800224fe  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180022505  nop     dword ptr [rax+rax+00h]
0x18002250a  mov     qword ptr [rsi+rbx*8], 0
0x180022512  inc     rbx
0x180022515  cmp     rbx, 2Bh ; '+'
0x180022519  jnz     short loc_1800224EC
0x18002251b  mov     ecx, cs:dword_180079D20
0x180022521  test    cl, 1
0x180022524  jz      short loc_18002255C
0x180022526  mov     eax, cs:dword_18007A0E8
0x18002252c  test    eax, eax
0x18002252e  jz      short loc_18002254D
0x180022530  lea     rcx, stru_18007A1C0; CriticalSection
0x180022537  call    cs:__imp_RtlDeleteCriticalSection
0x18002253e  nop     dword ptr [rax+rax+00h]
0x180022543  mov     cs:dword_18007A0E8, 0
0x18002254d  mov     ecx, cs:dword_180079D20
0x180022553  and     ecx, 0FFFFFFFEh
0x180022556  mov     cs:dword_180079D20, ecx
0x18002255c  test    cl, 10h
0x18002255f  jz      short loc_18002256D
0x180022561  call    EphemeralKeyTableUninit
0x180022566  and     cs:dword_180079D20, 0FFFFFFEFh
0x18002256d  lea     rcx, dword_180079068
0x180022574  call    TlgUnregisterAggregateProvider
0x180022579  lea     rcx, dword_1800790F0
0x180022580  call    TlgUnregisterAggregateProvider
0x180022585  mov     rbx, [rsp+28h+arg_0]
0x18002258a  mov     cs:g_fLoadCNGDone, 0
0x180022594  add     rsp, 20h
0x180022598  pop     rsi
0x180022599  retn
```
