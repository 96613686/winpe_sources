# NlDCLocInitializeGlobalPerformanceCounters(void)

- ea: `0x1800875b8`
- end: `0x1800877dc`
- name: `?NlDCLocInitializeGlobalPerformanceCounters@@YAHXZ`
- size: `548`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800747cc`

## callees

- `0x180018f38`
- `0x180018fac`
- `0x1800875b8`
- `0x1800877e4`
- `0x180087968`
- `0x1800879ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008763e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008763e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180087743`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180087626`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800876fa`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180087626`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800876fa`
- `ntdll!RtlGetNtProductType` at `0x180087602`
- `ntdll!RtlGetNtProductType` at `0x180087602`

## pseudocode

```c
__int64 NlDCLocInitializeGlobalPerformanceCounters(void)
{
  struct _PERF_COUNTERSET_INSTANCE *Instance; // rax
  void *v1; // rcx
  DWORD LastError; // eax
  ScannerInfoNameMappings *v3; // rcx
  __int64 v4; // rdx
  unsigned int v5; // ebx
  struct _PERF_COUNTERSET_INSTANCE *v6; // rdx
  void *v7; // rcx
  struct _DOMAINCONTROLLER_GLOBAL_PING_COUNTERS *v8; // r8
  ScannerInfoNameMappings *v9; // rcx
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+40h] [rbp+8h] BYREF

  ProductType = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_70d780fdfa843fcc377a8760ff8b51f7_Traceguids);
  RtlGetNtProductType(&ProductType);
  Instance = PerfCreateInstance(hDataSource_PerfCntr_1, &CtrSet_DCLocator_0Guid, L"_Total", 0);
  gpDCLocatorGlobalPerfCounterInstance = Instance;
  if ( !Instance )
  {
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_25;
    v4 = 17;
LABEL_24:
    WPP_SF_Dd(*((_QWORD *)v3 + 2), v4, &WPP_70d780fdfa843fcc377a8760ff8b51f7_Traceguids, LastError, LastError);
LABEL_25:
    v5 = 0;
    NlDCLocUninitializeGlobalPerformanceCounters();
    return v5;
  }
  v5 = NlDCLocInitializePerformanceCounterStructure(
         v1,
         Instance,
         (struct _DCLOCATOR_PERF_COUNTERS *)&gDCLocatorGlobalPerfCounters);
  if ( !v5 )
  {
    LastError = GetLastError();
    v3 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      goto LABEL_25;
    v4 = 18;
    goto LABEL_24;
  }
  if ( ProductType == NtProductLanManNt )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_70d780fdfa843fcc377a8760ff8b51f7_Traceguids);
    gpDCPingGlobalPerfCounterInstance = PerfCreateInstance(
                                          hDataSource_PerfCntr_1,
                                          &CtrSet_DCLocator_1Guid,
                                          L"DC Locator (DC)",
                                          0);
    if ( !gpDCPingGlobalPerfCounterInstance )
    {
      LastError = GetLastError();
      v3 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_25;
      v4 = 20;
      goto LABEL_24;
    }
    v5 = NlDCPingsInitializePerformanceCounterStructure(v7, v6, v8);
    if ( !v5 )
    {
      LastError = GetLastError();
      v3 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_25;
      v4 = 21;
      goto LABEL_24;
    }
  }
  else
  {
    v9 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return v5;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      goto LABEL_30;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_70d780fdfa843fcc377a8760ff8b51f7_Traceguids);
  }
  v9 = WPP_GLOBAL_Control;
LABEL_30:
  if ( (*((_BYTE *)v9 + 28) & 4) != 0 && *((_BYTE *)v9 + 25) >= 4u )
    WPP_SF_(*((_QWORD *)v9 + 2), 23, &WPP_70d780fdfa843fcc377a8760ff8b51f7_Traceguids);
  return v5;
}

```

## disassembly

```asm
0x1800875b8  mov     [rsp+arg_8], rbx
0x1800875bd  mov     [rsp+arg_10], rsi
0x1800875c2  push    rdi
0x1800875c3  sub     rsp, 30h
0x1800875c7  mov     [rsp+38h+ProductType], 0
0x1800875cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800875d6  lea     rsi, WPP_70d780fdfa843fcc377a8760ff8b51f7_Traceguids
0x1800875dd  mov     dil, 4
0x1800875e0  test    [rcx+1Ch], dil
0x1800875e4  jz      short loc_1800875FD
0x1800875e6  cmp     [rcx+19h], dil
0x1800875ea  jb      short loc_1800875FD
0x1800875ec  mov     rcx, [rcx+10h]
0x1800875f0  mov     edx, 10h
0x1800875f5  mov     r8, rsi
0x1800875f8  call    WPP_SF_
0x1800875fd  lea     rcx, [rsp+38h+ProductType]; ProductType
0x180087602  call    cs:__imp_RtlGetNtProductType
0x180087609  nop     dword ptr [rax+rax+00h]
0x18008760e  mov     rcx, cs:hDataSource_PerfCntr_1; ProviderHandle
0x180087615  lea     r8, aTotal; "_Total"
0x18008761c  xor     r9d, r9d; Id
0x18008761f  lea     rdx, CtrSet_DCLocator_0Guid; CounterSetGuid
0x180087626  call    cs:__imp_PerfCreateInstance
0x18008762d  nop     dword ptr [rax+rax+00h]
0x180087632  mov     cs:?gpDCLocatorGlobalPerfCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA, rax; _PERF_COUNTERSET_INSTANCE * gpDCLocatorGlobalPerfCounterInstance
0x180087639  test    rax, rax
0x18008763c  jnz     short loc_18008766F
0x18008763e  call    cs:__imp_GetLastError
0x180087645  nop     dword ptr [rax+rax+00h]
0x18008764a  mov     rcx, cs:WPP_GLOBAL_Control
0x180087651  test    [rcx+1Ch], dil
0x180087655  jz      loc_180087778
0x18008765b  cmp     byte ptr [rcx+19h], 2
0x18008765f  jb      loc_180087778
0x180087665  mov     edx, 11h
0x18008766a  jmp     loc_180087765
0x18008766f  lea     r8, ?gDCLocatorGlobalPerfCounters@@3U_DCLOCATOR_PERF_COUNTERS@@A; struct _DCLOCATOR_PERF_COUNTERS *
0x180087676  mov     rdx, rax; struct _PERF_COUNTERSET_INSTANCE *
0x180087679  call    ?NlDCLocInitializePerformanceCounterStructure@@YAHPEAXPEAU_PERF_COUNTERSET_INSTANCE@@PEAU_DCLOCATOR_PERF_COUNTERS@@@Z; NlDCLocInitializePerformanceCounterStructure(void *,_PERF_COUNTERSET_INSTANCE *,_DCLOCATOR_PERF_COUNTERS *)
0x18008767e  mov     ebx, eax
0x180087680  test    eax, eax
0x180087682  jnz     short loc_1800876B3
0x180087684  call    cs:__imp_GetLastError
0x18008768b  nop     dword ptr [rax+rax+00h]
0x180087690  mov     rcx, cs:WPP_GLOBAL_Control
0x180087697  test    [rcx+1Ch], dil
0x18008769b  jz      loc_180087778
0x1800876a1  cmp     byte ptr [rcx+19h], 2
0x1800876a5  jb      loc_180087778
0x1800876ab  lea     edx, [rbx+12h]
0x1800876ae  jmp     loc_180087765
0x1800876b3  cmp     [rsp+38h+ProductType], 2
0x1800876b8  jnz     loc_180087781
0x1800876be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800876c5  test    [rcx+1Ch], dil
0x1800876c9  jz      short loc_1800876E2
0x1800876cb  cmp     [rcx+19h], dil
0x1800876cf  jb      short loc_1800876E2
0x1800876d1  mov     rcx, [rcx+10h]
0x1800876d5  mov     edx, 13h
0x1800876da  mov     r8, rsi
0x1800876dd  call    WPP_SF_
0x1800876e2  mov     rcx, cs:hDataSource_PerfCntr_1; ProviderHandle
0x1800876e9  lea     r8, aDcLocatorDc; "DC Locator (DC)"
0x1800876f0  xor     r9d, r9d; Id
0x1800876f3  lea     rdx, CtrSet_DCLocator_1Guid; CounterSetGuid
0x1800876fa  call    cs:__imp_PerfCreateInstance
0x180087701  nop     dword ptr [rax+rax+00h]
0x180087706  mov     cs:?gpDCPingGlobalPerfCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA, rax; _PERF_COUNTERSET_INSTANCE * gpDCPingGlobalPerfCounterInstance
0x18008770d  test    rax, rax
0x180087710  jnz     short loc_180087738
0x180087712  call    cs:__imp_GetLastError
0x180087719  nop     dword ptr [rax+rax+00h]
0x18008771e  mov     rcx, cs:WPP_GLOBAL_Control
0x180087725  test    [rcx+1Ch], dil
0x180087729  jz      short loc_180087778
0x18008772b  cmp     byte ptr [rcx+19h], 2
0x18008772f  jb      short loc_180087778
0x180087731  mov     edx, 14h
0x180087736  jmp     short loc_180087765
0x180087738  call    ?NlDCPingsInitializePerformanceCounterStructure@@YAHPEAXPEAU_PERF_COUNTERSET_INSTANCE@@PEAU_DOMAINCONTROLLER_GLOBAL_PING_COUNTERS@@@Z; NlDCPingsInitializePerformanceCounterStructure(void *,_PERF_COUNTERSET_INSTANCE *,_DOMAINCONTROLLER_GLOBAL_PING_COUNTERS *)
0x18008773d  mov     ebx, eax
0x18008773f  test    eax, eax
0x180087741  jnz     short loc_1800877A5
0x180087743  call    cs:__imp_GetLastError
0x18008774a  nop     dword ptr [rax+rax+00h]
0x18008774f  mov     rcx, cs:WPP_GLOBAL_Control
0x180087756  test    [rcx+1Ch], dil
0x18008775a  jz      short loc_180087778
0x18008775c  cmp     byte ptr [rcx+19h], 2
0x180087760  jb      short loc_180087778
0x180087762  lea     edx, [rbx+15h]
0x180087765  mov     rcx, [rcx+10h]
0x180087769  mov     r9d, eax
0x18008776c  mov     r8, rsi
0x18008776f  mov     [rsp+38h+var_18], eax
0x180087773  call    WPP_SF_Dd
0x180087778  xor     ebx, ebx
0x18008777a  call    ?NlDCLocUninitializeGlobalPerformanceCounters@@YAXXZ; NlDCLocUninitializeGlobalPerformanceCounters(void)
0x18008777f  jmp     short loc_1800877C9
0x180087781  mov     rcx, cs:WPP_GLOBAL_Control
0x180087788  test    [rcx+1Ch], dil
0x18008778c  jz      short loc_1800877C9
0x18008778e  cmp     [rcx+19h], dil
0x180087792  jb      short loc_1800877AC
0x180087794  mov     rcx, [rcx+10h]
0x180087798  mov     edx, 16h
0x18008779d  mov     r8, rsi
0x1800877a0  call    WPP_SF_
0x1800877a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800877ac  test    [rcx+1Ch], dil
0x1800877b0  jz      short loc_1800877C9
0x1800877b2  cmp     [rcx+19h], dil
0x1800877b6  jb      short loc_1800877C9
0x1800877b8  mov     rcx, [rcx+10h]
0x1800877bc  mov     edx, 17h
0x1800877c1  mov     r8, rsi
0x1800877c4  call    WPP_SF_
0x1800877c9  mov     rsi, [rsp+38h+arg_10]
0x1800877ce  mov     eax, ebx
0x1800877d0  mov     rbx, [rsp+38h+arg_8]
0x1800877d5  add     rsp, 30h
0x1800877d9  pop     rdi
0x1800877da  retn
```
