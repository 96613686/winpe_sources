# InitializeCNGProv

- ea: `0x1800222fc`
- end: `0x18002243d`
- name: `InitializeCNGProv`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021fc4`

## callees

- `0x18000af80`
- `0x18001810c`
- `0x18001b184`
- `0x18001d44c`
- `0x18001e6b0`
- `0x180021d90`
- `0x1800222fc`
- `0x18002247c`
- `0x180024c18`

## import_xrefs

- `ntdll!RtlInitializeSRWLock` at `0x18002236f`
- `ntdll!RtlInitializeSRWLock` at `0x180022395`
- `ntdll!RtlInitializeSRWLock` at `0x18002236f`
- `ntdll!RtlInitializeSRWLock` at `0x180022395`
- `ntdll!RtlInitializeCriticalSection` at `0x18002232d`
- `ntdll!RtlInitializeCriticalSection` at `0x18002232d`
- `ntdll!RtlDllShutdownInProgress` at `0x1800223e8`
- `ntdll!RtlDllShutdownInProgress` at `0x1800223e8`

## string_xrefs

- `0x1800223c5`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncryptprov\init.c`

## pseudocode

```c
__int64 InitializeCNGProv()
{
  __int64 i; // rcx
  _QWORD *v1; // rax
  NTSTATUS v2; // ebx
  __int64 v3; // r9

  for ( i = 0; i != 3; ++i )
  {
    v1 = *(&g_rgKSPBuffes + i);
    v1[1] = v1;
    *v1 = v1;
  }
  v2 = RtlInitializeCriticalSection(&stru_18007A1C0);
  if ( v2 >= 0 )
    dword_18007A0E8 = 1;
  if ( v2 )
  {
    v3 = 173;
LABEL_13:
    DebugTraceError(
      (unsigned int)v2,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncryptprov\\init.c",
      v3);
    UninitializeCNGProv();
    return (unsigned int)v2;
  }
  dword_180079D20 |= 1u;
  SymCryptInitEnvWindowsUsermodeWin8_1nLater();
  if ( !_InterlockedCompareExchange(&dword_18007A5FC, 1, 0) )
    RtlInitializeSRWLock(&qword_18007A5F0);
  dword_180079D20 |= 2u;
  if ( !_InterlockedCompareExchange(&dword_18007A670, 1, 0) )
    RtlInitializeSRWLock(&qword_180079000);
  dword_180079D20 |= 4u;
  SKCacheInit();
  dword_180079D20 |= 8u;
  v2 = EphemeralKeyTableInit();
  if ( v2 )
  {
    v3 = 203;
    goto LABEL_13;
  }
  dword_180079D20 |= 0x10u;
  if ( !RtlDllShutdownInProgress() )
  {
    TlgRegisterAggregateProviderEx(&dword_180079068);
    TlgRegisterAggregateProviderEx(&dword_1800790F0);
  }
  if ( IsInLSAProcess() )
    BCryptIsoTrackKeyguardRegistryData();
  g_fLoadCNGDone = 1;
  return 0;
}

```

## disassembly

```asm
0x1800222fc  mov     [rsp+arg_0], rbx
0x180022301  push    rdi
0x180022302  sub     rsp, 20h
0x180022306  xor     ecx, ecx
0x180022308  lea     edi, [rcx+1]
0x18002230b  lea     rax, g_rgKSPBuffes
0x180022312  mov     rax, [rax+rcx*8]
0x180022316  add     rcx, rdi
0x180022319  mov     [rax+8], rax
0x18002231d  mov     [rax], rax
0x180022320  cmp     rcx, 3
0x180022324  jnz     short loc_18002230B
0x180022326  lea     rcx, stru_18007A1C0; CriticalSection
0x18002232d  call    cs:__imp_RtlInitializeCriticalSection
0x180022334  nop     dword ptr [rax+rax+00h]
0x180022339  mov     ebx, eax
0x18002233b  test    eax, eax
0x18002233d  js      short loc_180022345
0x18002233f  mov     cs:dword_18007A0E8, edi
0x180022345  test    ebx, ebx
0x180022347  jz      short loc_180022351
0x180022349  mov     r9d, 0ADh
0x18002234f  jmp     short loc_1800223C5
0x180022351  or      cs:dword_180079D20, edi
0x180022357  call    SymCryptInitEnvWindowsUsermodeWin8_1nLater
0x18002235c  xor     eax, eax
0x18002235e  lock cmpxchg cs:dword_18007A5FC, edi
0x180022366  jnz     short loc_18002237B
0x180022368  lea     rcx, qword_18007A5F0
0x18002236f  call    cs:__imp_RtlInitializeSRWLock
0x180022376  nop     dword ptr [rax+rax+00h]
0x18002237b  or      cs:dword_180079D20, 2
0x180022382  xor     eax, eax
0x180022384  lock cmpxchg cs:dword_18007A670, edi
0x18002238c  jnz     short loc_1800223A1
0x18002238e  lea     rcx, qword_180079000
0x180022395  call    cs:__imp_RtlInitializeSRWLock
0x18002239c  nop     dword ptr [rax+rax+00h]
0x1800223a1  or      cs:dword_180079D20, 4
0x1800223a8  call    SKCacheInit
0x1800223ad  or      cs:dword_180079D20, 8
0x1800223b4  call    EphemeralKeyTableInit
0x1800223b9  mov     ebx, eax
0x1800223bb  test    eax, eax
0x1800223bd  jz      short loc_1800223E1
0x1800223bf  mov     r9d, 0CBh
0x1800223c5  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800223cc  mov     ecx, ebx
0x1800223ce  lea     rdx, aStatus; "Status"
0x1800223d5  call    DebugTraceError
0x1800223da  call    UninitializeCNGProv
0x1800223df  jmp     short loc_18002242F
0x1800223e1  or      cs:dword_180079D20, 10h
0x1800223e8  call    cs:__imp_RtlDllShutdownInProgress
0x1800223ef  nop     dword ptr [rax+rax+00h]
0x1800223f4  test    al, al
0x1800223f6  jnz     short loc_180022419
0x1800223f8  mov     r9d, edi
0x1800223fb  lea     rcx, dword_180079068; CallbackContext
0x180022402  call    TlgRegisterAggregateProviderEx
0x180022407  mov     r9d, 2
0x18002240d  lea     rcx, dword_1800790F0; CallbackContext
0x180022414  call    TlgRegisterAggregateProviderEx
0x180022419  call    IsInLSAProcess
0x18002241e  test    eax, eax
0x180022420  jz      short loc_180022427
0x180022422  call    BCryptIsoTrackKeyguardRegistryData
0x180022427  mov     cs:g_fLoadCNGDone, edi
0x18002242d  xor     ebx, ebx
0x18002242f  mov     eax, ebx
0x180022431  mov     rbx, [rsp+28h+arg_0]
0x180022436  add     rsp, 20h
0x18002243a  pop     rdi
0x18002243b  retn
```
