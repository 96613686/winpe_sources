# UninitializeCNG

- ea: `0x180012838`
- end: `0x1800128e9`
- name: `UninitializeCNG`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012220`

## callees

- `0x180003ef0`
- `0x180012838`
- `0x1800128f0`
- `0x180012978`
- `0x18001d6c0`
- `0x180023dbc`
- `0x1800240f0`
- `0x1800245d8`
- `0x1800249c4`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x1800128b1`
- `ntdll!RtlDeleteResource` at `0x1800128b1`

## pseudocode

```c
void UninitializeCNG()
{
  if ( _InterlockedCompareExchange(&dword_18003EFA8, 0, 1) == 1 )
  {
    InternalFreeCachedHandles(l_PagedCipherEntryCache, &l_PagedHashEntryCache);
    InternalFreeCachedHandles(l_NonPagedCipherEntryCache, &l_NonPagedHashEntryCache);
    SslEmptyNCryptProvCache(qword_18003F460);
    SslEmptyNCryptProvCache(qword_18003F3E0);
    if ( g_EccCurves )
      MSCryptFree(g_EccCurves);
    g_EccCurves = 0;
    g_EccCurvesCount = 0;
    RtlDeleteResource(&g_EccCurvesRWLock);
    if ( dword_18003EF90 )
    {
      FreeExternalCipherSuites();
      FreeExternalHashAlgorithms();
      FreeExternalSignatureAlgorithms();
      FreeExternalKeyExchangeAlgorithms();
      FreeExternalCipherAlgorithms();
    }
  }
}

```

## disassembly

```asm
0x180012838  sub     rsp, 28h
0x18001283c  xor     ecx, ecx
0x18001283e  lea     eax, [rcx+1]
0x180012841  lock cmpxchg cs:dword_18003EFA8, ecx
0x180012849  jnz     short loc_1800128C0
0x18001284b  lea     rdx, l_PagedHashEntryCache
0x180012852  lea     rcx, l_PagedCipherEntryCache
0x180012859  call    InternalFreeCachedHandles
0x18001285e  lea     rdx, l_NonPagedHashEntryCache
0x180012865  lea     rcx, l_NonPagedCipherEntryCache
0x18001286c  call    InternalFreeCachedHandles
0x180012871  lea     rcx, qword_18003F460
0x180012878  call    SslEmptyNCryptProvCache
0x18001287d  lea     rcx, qword_18003F3E0
0x180012884  call    SslEmptyNCryptProvCache
0x180012889  mov     rcx, cs:g_EccCurves
0x180012890  test    rcx, rcx
0x180012893  jnz     short loc_1800128C5
0x180012895  lea     rcx, g_EccCurvesRWLock; Resource
0x18001289c  mov     cs:g_EccCurves, 0
0x1800128a7  mov     cs:g_EccCurvesCount, 0
0x1800128b1  call    cs:__imp_RtlDeleteResource
0x1800128b7  cmp     cs:dword_18003EF90, 0
0x1800128be  jnz     short loc_1800128CC
0x1800128c0  add     rsp, 28h
0x1800128c4  retn
0x1800128c5  call    MSCryptFree
0x1800128ca  jmp     short loc_180012895
0x1800128cc  call    FreeExternalCipherSuites
0x1800128d1  call    FreeExternalHashAlgorithms
0x1800128d6  call    FreeExternalSignatureAlgorithms
0x1800128db  call    FreeExternalKeyExchangeAlgorithms
0x1800128e0  add     rsp, 28h
0x1800128e4  jmp     FreeExternalCipherAlgorithms
```
