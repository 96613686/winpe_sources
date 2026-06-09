# NlDCLocInitializeGlobalPerformanceCounters(void)

- ea: `0x1800815c4`
- end: `0x1800817bd`
- name: `?NlDCLocInitializeGlobalPerformanceCounters@@YAHXZ`
- size: `505`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18006f490`

## callees

- `0x180018414`
- `0x18001847c`
- `0x1800815c4`
- `0x1800817c4`
- `0x180081928`
- `0x1800819a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008163e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008167e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008172b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008163e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008167e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008172b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18008162c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800816ee`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18008162c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x1800816ee`
- `ntdll!RtlGetNtProductType` at `0x18008160e`
- `ntdll!RtlGetNtProductType` at `0x18008160e`

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
0x1800815c4  mov     [rsp+arg_8], rbx
0x1800815c9  mov     [rsp+arg_10], rsi
0x1800815ce  push    rdi
0x1800815cf  sub     rsp, 30h
0x1800815d3  mov     [rsp+38h+ProductType], 0
0x1800815db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800815e2  lea     rsi, WPP_70d780fdfa843fcc377a8760ff8b51f7_Traceguids
0x1800815e9  mov     dil, 4
0x1800815ec  test    [rcx+1Ch], dil
0x1800815f0  jz      short loc_180081609
0x1800815f2  cmp     [rcx+19h], dil
0x1800815f6  jb      short loc_180081609
0x1800815f8  mov     rcx, [rcx+10h]
0x1800815fc  mov     edx, 10h
0x180081601  mov     r8, rsi
0x180081604  call    WPP_SF_
0x180081609  lea     rcx, [rsp+38h+ProductType]; ProductType
0x18008160e  call    cs:__imp_RtlGetNtProductType
0x180081614  mov     rcx, cs:hDataSource_PerfCntr_1; ProviderHandle
0x18008161b  lea     r8, aTotal; "_Total"
0x180081622  xor     r9d, r9d; Id
0x180081625  lea     rdx, CtrSet_DCLocator_0Guid; CounterSetGuid
0x18008162c  call    cs:__imp_PerfCreateInstance
0x180081632  mov     cs:?gpDCLocatorGlobalPerfCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA, rax; _PERF_COUNTERSET_INSTANCE * gpDCLocatorGlobalPerfCounterInstance
0x180081639  test    rax, rax
0x18008163c  jnz     short loc_180081669
0x18008163e  call    cs:__imp_GetLastError
0x180081644  mov     rcx, cs:WPP_GLOBAL_Control
0x18008164b  test    [rcx+1Ch], dil
0x18008164f  jz      loc_18008175A
0x180081655  cmp     byte ptr [rcx+19h], 2
0x180081659  jb      loc_18008175A
0x18008165f  mov     edx, 11h
0x180081664  jmp     loc_180081747
0x180081669  lea     r8, ?gDCLocatorGlobalPerfCounters@@3U_DCLOCATOR_PERF_COUNTERS@@A; struct _DCLOCATOR_PERF_COUNTERS *
0x180081670  mov     rdx, rax; struct _PERF_COUNTERSET_INSTANCE *
0x180081673  call    ?NlDCLocInitializePerformanceCounterStructure@@YAHPEAXPEAU_PERF_COUNTERSET_INSTANCE@@PEAU_DCLOCATOR_PERF_COUNTERS@@@Z; NlDCLocInitializePerformanceCounterStructure(void *,_PERF_COUNTERSET_INSTANCE *,_DCLOCATOR_PERF_COUNTERS *)
0x180081678  mov     ebx, eax
0x18008167a  test    eax, eax
0x18008167c  jnz     short loc_1800816A7
0x18008167e  call    cs:__imp_GetLastError
0x180081684  mov     rcx, cs:WPP_GLOBAL_Control
0x18008168b  test    [rcx+1Ch], dil
0x18008168f  jz      loc_18008175A
0x180081695  cmp     byte ptr [rcx+19h], 2
0x180081699  jb      loc_18008175A
0x18008169f  lea     edx, [rbx+12h]
0x1800816a2  jmp     loc_180081747
0x1800816a7  cmp     [rsp+38h+ProductType], 2
0x1800816ac  jnz     loc_180081763
0x1800816b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800816b9  test    [rcx+1Ch], dil
0x1800816bd  jz      short loc_1800816D6
0x1800816bf  cmp     [rcx+19h], dil
0x1800816c3  jb      short loc_1800816D6
0x1800816c5  mov     rcx, [rcx+10h]
0x1800816c9  mov     edx, 13h
0x1800816ce  mov     r8, rsi
0x1800816d1  call    WPP_SF_
0x1800816d6  mov     rcx, cs:hDataSource_PerfCntr_1; ProviderHandle
0x1800816dd  lea     r8, aDcLocatorDc; "DC Locator (DC)"
0x1800816e4  xor     r9d, r9d; Id
0x1800816e7  lea     rdx, CtrSet_DCLocator_1Guid; CounterSetGuid
0x1800816ee  call    cs:__imp_PerfCreateInstance
0x1800816f4  mov     cs:?gpDCPingGlobalPerfCounterInstance@@3PEAU_PERF_COUNTERSET_INSTANCE@@EA, rax; _PERF_COUNTERSET_INSTANCE * gpDCPingGlobalPerfCounterInstance
0x1800816fb  test    rax, rax
0x1800816fe  jnz     short loc_180081720
0x180081700  call    cs:__imp_GetLastError
0x180081706  mov     rcx, cs:WPP_GLOBAL_Control
0x18008170d  test    [rcx+1Ch], dil
0x180081711  jz      short loc_18008175A
0x180081713  cmp     byte ptr [rcx+19h], 2
0x180081717  jb      short loc_18008175A
0x180081719  mov     edx, 14h
0x18008171e  jmp     short loc_180081747
0x180081720  call    ?NlDCPingsInitializePerformanceCounterStructure@@YAHPEAXPEAU_PERF_COUNTERSET_INSTANCE@@PEAU_DOMAINCONTROLLER_GLOBAL_PING_COUNTERS@@@Z; NlDCPingsInitializePerformanceCounterStructure(void *,_PERF_COUNTERSET_INSTANCE *,_DOMAINCONTROLLER_GLOBAL_PING_COUNTERS *)
0x180081725  mov     ebx, eax
0x180081727  test    eax, eax
0x180081729  jnz     short loc_180081787
0x18008172b  call    cs:__imp_GetLastError
0x180081731  mov     rcx, cs:WPP_GLOBAL_Control
0x180081738  test    [rcx+1Ch], dil
0x18008173c  jz      short loc_18008175A
0x18008173e  cmp     byte ptr [rcx+19h], 2
0x180081742  jb      short loc_18008175A
0x180081744  lea     edx, [rbx+15h]
0x180081747  mov     rcx, [rcx+10h]
0x18008174b  mov     r9d, eax
0x18008174e  mov     r8, rsi
0x180081751  mov     [rsp+38h+var_18], eax
0x180081755  call    WPP_SF_Dd
0x18008175a  xor     ebx, ebx
0x18008175c  call    ?NlDCLocUninitializeGlobalPerformanceCounters@@YAXXZ; NlDCLocUninitializeGlobalPerformanceCounters(void)
0x180081761  jmp     short loc_1800817AB
0x180081763  mov     rcx, cs:WPP_GLOBAL_Control
0x18008176a  test    [rcx+1Ch], dil
0x18008176e  jz      short loc_1800817AB
0x180081770  cmp     [rcx+19h], dil
0x180081774  jb      short loc_18008178E
0x180081776  mov     rcx, [rcx+10h]
0x18008177a  mov     edx, 16h
0x18008177f  mov     r8, rsi
0x180081782  call    WPP_SF_
0x180081787  mov     rcx, cs:WPP_GLOBAL_Control
0x18008178e  test    [rcx+1Ch], dil
0x180081792  jz      short loc_1800817AB
0x180081794  cmp     [rcx+19h], dil
0x180081798  jb      short loc_1800817AB
0x18008179a  mov     rcx, [rcx+10h]
0x18008179e  mov     edx, 17h
0x1800817a3  mov     r8, rsi
0x1800817a6  call    WPP_SF_
0x1800817ab  mov     rsi, [rsp+38h+arg_10]
0x1800817b0  mov     eax, ebx
0x1800817b2  mov     rbx, [rsp+38h+arg_8]
0x1800817b7  add     rsp, 30h
0x1800817bb  pop     rdi
0x1800817bc  retn
```
