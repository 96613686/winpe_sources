# InitOneTimeGlobals(void)

- ea: `0x18001f110`
- end: `0x18001f2c1`
- name: `?InitOneTimeGlobals@@YAJXZ`
- size: `433`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180018d50`

## callees

- `0x1800089c8`
- `0x18000e488`
- `0x18001487c`
- `0x18001f110`
- `0x180026b94`

## import_xrefs

- `KERNEL32!CreateSemaphoreA` at `0x18001f249`
- `KERNEL32!CreateSemaphoreA` at `0x18001f249`
- `KERNEL32!GetLastError` at `0x18001f25b`
- `KERNEL32!GetLastError` at `0x18001f25b`
- `IisRTL!IISInitializeCriticalSection` at `0x18001f22d`
- `IisRTL!IISInitializeCriticalSection` at `0x18001f22d`
- `IisRTL!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18001f184`
- `IisRTL!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18001f1f2`
- `IisRTL!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18001f184`
- `IisRTL!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18001f1f2`

## pseudocode

```c
__int64 InitOneTimeGlobals(void)
{
  CLKRHashTable *v0; // rax
  CLKRHashTable *v1; // rbx
  CLKRHashTable *v2; // rax
  CLKRHashTable *v3; // rbx
  CIdToPointerMapper *v4; // rax
  unsigned int v5; // edx
  unsigned int v6; // r8d
  signed int LastError; // eax
  signed int RegistryData; // ebx

  v0 = (CLKRHashTable *)operator new(0x48u);
  v1 = v0;
  if ( !v0 )
  {
    g_phtChildren = 0;
    goto LABEL_16;
  }
  CLKRHashTable::CLKRHashTable(
    v0,
    "MDBaseO",
    (unsigned __int64 (*)(const void *))CTypedHashTable<CChildNodeHashTable,CMDBaseObject,CMDKeyBuffer *,CLKRHashTable>::_ExtractKey,
    (unsigned int (*)(unsigned __int64))CTypedHashTable<CChildNodeHashTable,CMDBaseObject,CMDKeyBuffer *,CLKRHashTable>::_CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<CChildNodeHashTable,CMDBaseObject,CMDKeyBuffer *,CLKRHashTable>::_EqualKeys,
    (void (*)(const void *, int))CTypedHashTable<CHandleTable,CMDHandle,unsigned long,CLKRHashTable>::_AddRefRecord,
    4.0,
    3u,
    0,
    0);
  g_phtChildren = v1;
  v2 = (CLKRHashTable *)operator new(0x48u);
  v3 = v2;
  if ( !v2 )
  {
    g_phtData = 0;
    goto LABEL_16;
  }
  CLKRHashTable::CLKRHashTable(
    v2,
    "MDBaseD",
    (unsigned __int64 (*)(const void *))CTypedHashTable<CBaseDataHashTable,CMDBaseData,BASEDATA_KEY *,CLKRHashTable>::_ExtractKey,
    (unsigned int (*)(unsigned __int64))CTypedHashTable<CBaseDataHashTable,CMDBaseData,BASEDATA_KEY *,CLKRHashTable>::_CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<CBaseDataHashTable,CMDBaseData,BASEDATA_KEY *,CLKRHashTable>::_EqualKeys,
    (void (*)(const void *, int))CTypedHashTable<CHandleTable,CMDHandle,unsigned long,CLKRHashTable>::_AddRefRecord,
    4.0,
    3u,
    0,
    0);
  g_phtData = v3;
  v4 = (CIdToPointerMapper *)operator new(0x30u);
  if ( !v4 )
  {
    g_PointerMapper = 0;
LABEL_16:
    RegistryData = -2147024882;
    goto LABEL_17;
  }
  g_PointerMapper = CIdToPointerMapper::CIdToPointerMapper(v4, v5, v6);
  if ( !g_PointerMapper )
    goto LABEL_16;
  g_fcsEditWhileRunningInitialized = IISInitializeCriticalSection(&g_csEditWhileRunning);
  if ( !g_fcsEditWhileRunningInitialized )
    goto LABEL_16;
  g_hReadSaveSemaphore = CreateSemaphoreA(0, 1, 1, 0);
  if ( g_hReadSaveSemaphore )
  {
    RegistryData = CFileListener::ReadRegistryData();
    if ( RegistryData >= 0 )
      return 0;
LABEL_17:
    TerminateOneTimeGlobals();
    return (unsigned int)RegistryData;
  }
  LastError = GetLastError();
  RegistryData = LastError;
  if ( LastError > 0 )
    RegistryData = (unsigned __int16)LastError | 0x80070000;
  if ( RegistryData < 0 )
    goto LABEL_17;
  return (unsigned int)RegistryData;
}

```

## disassembly

```asm
0x18001f110  push    rbx
0x18001f112  sub     rsp, 60h
0x18001f116  mov     ecx, 48h ; 'H'; Size
0x18001f11b  movaps  [rsp+68h+var_18], xmm6
0x18001f120  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f125  mov     rbx, rax
0x18001f128  test    rax, rax
0x18001f12b  jz      loc_18001F29F
0x18001f131  movsd   xmm6, cs:__real@4010000000000000
0x18001f139  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VCHandleTable@@VCMDHandle@@KVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<CHandleTable,CMDHandle,ulong,CLKRHashTable>::_AddRefRecord(void const *,int)
0x18001f140  mov     [rsp+68h+var_20], 0
0x18001f145  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VCChildNodeHashTable@@VCMDBaseObject@@PEAVCMDKeyBuffer@@VCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<CChildNodeHashTable,CMDBaseObject,CMDKeyBuffer *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x18001f14c  mov     [rsp+68h+var_28], 0
0x18001f154  lea     r8, ?_ExtractKey@?$CTypedHashTable@VCChildNodeHashTable@@VCMDBaseObject@@PEAVCMDKeyBuffer@@VCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<CChildNodeHashTable,CMDBaseObject,CMDKeyBuffer *,CLKRHashTable>::_ExtractKey(void const *)
0x18001f15b  mov     [rsp+68h+var_30], 3
0x18001f163  lea     rdx, aMdbaseo; "MDBaseO"
0x18001f16a  movsd   [rsp+68h+var_38], xmm6
0x18001f170  mov     rcx, rbx
0x18001f173  mov     [rsp+68h+var_40], rax
0x18001f178  lea     rax, ?_EqualKeys@?$CTypedHashTable@VCChildNodeHashTable@@VCMDBaseObject@@PEAVCMDKeyBuffer@@VCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<CChildNodeHashTable,CMDBaseObject,CMDKeyBuffer *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x18001f17f  mov     [rsp+68h+var_48], rax
0x18001f184  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18001f18a  mov     ecx, 48h ; 'H'; Size
0x18001f18f  mov     cs:?g_phtChildren@@3PEAVCChildNodeHashTable@@EA, rbx; CChildNodeHashTable * g_phtChildren
0x18001f196  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f19b  mov     rbx, rax
0x18001f19e  test    rax, rax
0x18001f1a1  jz      loc_18001F292
0x18001f1a7  mov     [rsp+68h+var_20], 0
0x18001f1ac  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VCHandleTable@@VCMDHandle@@KVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<CHandleTable,CMDHandle,ulong,CLKRHashTable>::_AddRefRecord(void const *,int)
0x18001f1b3  mov     [rsp+68h+var_28], 0
0x18001f1bb  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VCBaseDataHashTable@@VCMDBaseData@@PEAUBASEDATA_KEY@@VCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<CBaseDataHashTable,CMDBaseData,BASEDATA_KEY *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x18001f1c2  mov     [rsp+68h+var_30], 3
0x18001f1ca  lea     r8, ?_ExtractKey@?$CTypedHashTable@VCBaseDataHashTable@@VCMDBaseData@@PEAUBASEDATA_KEY@@VCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<CBaseDataHashTable,CMDBaseData,BASEDATA_KEY *,CLKRHashTable>::_ExtractKey(void const *)
0x18001f1d1  movsd   [rsp+68h+var_38], xmm6
0x18001f1d7  lea     rdx, aMdbased; "MDBaseD"
0x18001f1de  mov     [rsp+68h+var_40], rax
0x18001f1e3  mov     rcx, rbx
0x18001f1e6  lea     rax, ?_EqualKeys@?$CTypedHashTable@VCBaseDataHashTable@@VCMDBaseData@@PEAUBASEDATA_KEY@@VCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<CBaseDataHashTable,CMDBaseData,BASEDATA_KEY *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x18001f1ed  mov     [rsp+68h+var_48], rax
0x18001f1f2  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18001f1f8  mov     ecx, 30h ; '0'; Size
0x18001f1fd  mov     cs:?g_phtData@@3PEAVCBaseDataHashTable@@EA, rbx; CBaseDataHashTable * g_phtData
0x18001f204  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f209  test    rax, rax
0x18001f20c  jz      short loc_18001F285
0x18001f20e  mov     rcx, rax; this
0x18001f211  call    ??0CIdToPointerMapper@@QEAA@KK@Z; CIdToPointerMapper::CIdToPointerMapper(ulong,ulong)
0x18001f216  mov     cs:?g_PointerMapper@@3PEAVCIdToPointerMapper@@EA, rax; CIdToPointerMapper * g_PointerMapper
0x18001f21d  test    rax, rax
0x18001f220  jz      loc_18001F2AA
0x18001f226  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csEditWhileRunning
0x18001f22d  call    cs:__imp_IISInitializeCriticalSection
0x18001f233  mov     cs:?g_fcsEditWhileRunningInitialized@@3HA, eax; int g_fcsEditWhileRunningInitialized
0x18001f239  test    eax, eax
0x18001f23b  jz      short loc_18001F2AA
0x18001f23d  xor     r9d, r9d; lpName
0x18001f240  xor     ecx, ecx; lpSemaphoreAttributes
0x18001f242  lea     edx, [r9+1]; lInitialCount
0x18001f246  mov     r8d, edx; lMaximumCount
0x18001f249  call    cs:__imp_CreateSemaphoreA
0x18001f24f  mov     cs:?g_hReadSaveSemaphore@@3PEAXEA, rax; void * g_hReadSaveSemaphore
0x18001f256  test    rax, rax
0x18001f259  jnz     short loc_18001F276
0x18001f25b  call    cs:__imp_GetLastError
0x18001f261  mov     ebx, eax
0x18001f263  test    eax, eax
0x18001f265  jle     short loc_18001F270
0x18001f267  movzx   ebx, ax
0x18001f26a  or      ebx, 80070000h
0x18001f270  test    ebx, ebx
0x18001f272  jns     short loc_18001F2B4
0x18001f274  jmp     short loc_18001F2AF
0x18001f276  call    ?ReadRegistryData@CFileListener@@SAJXZ; CFileListener::ReadRegistryData(void)
0x18001f27b  mov     ebx, eax
0x18001f27d  test    eax, eax
0x18001f27f  js      short loc_18001F2AF
0x18001f281  xor     ebx, ebx
0x18001f283  jmp     short loc_18001F2B4
0x18001f285  mov     cs:?g_PointerMapper@@3PEAVCIdToPointerMapper@@EA, 0; CIdToPointerMapper * g_PointerMapper
0x18001f290  jmp     short loc_18001F2AA
0x18001f292  mov     cs:?g_phtData@@3PEAVCBaseDataHashTable@@EA, 0; CBaseDataHashTable * g_phtData
0x18001f29d  jmp     short loc_18001F2AA
0x18001f29f  mov     cs:?g_phtChildren@@3PEAVCChildNodeHashTable@@EA, 0; CChildNodeHashTable * g_phtChildren
0x18001f2aa  mov     ebx, 8007000Eh
0x18001f2af  call    ?TerminateOneTimeGlobals@@YAXXZ; TerminateOneTimeGlobals(void)
0x18001f2b4  movaps  xmm6, [rsp+68h+var_18]
0x18001f2b9  mov     eax, ebx
0x18001f2bb  add     rsp, 60h
0x18001f2bf  pop     rbx
0x18001f2c0  retn
```
