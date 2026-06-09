# LsapLsaExtensionLoad(void)

- ea: `0x1800d20d8`
- end: `0x1800d25f2`
- name: `?LsapLsaExtensionLoad@@YAJXZ`
- size: `1306`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800d1db0`

## callees

- `0x180011278`
- `0x180016f70`
- `0x1800ada18`
- `0x1800adbf0`
- `0x1800ae660`
- `0x1800c0da0`
- `0x1800d20d8`
- `0x1800d2bbc`
- `0x1800dbf44`
- `0x1800efca0`
- `0x1800f3600`
- `0x18012d354`
- `0x180143f5c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1800d2211`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x1800d2211`
- `ntdll!RtlInitializeCriticalSection` at `0x1800d21f4`
- `ntdll!RtlInitializeCriticalSection` at `0x1800d21f4`
- `lsass!LsaGetInterface` at `0x1800d227f`
- `lsass!LsaGetInterface` at `0x1800d22d6`
- `lsass!LsaGetInterface` at `0x1800d227f`
- `lsass!LsaGetInterface` at `0x1800d22d6`
- `lsass!LsaRegisterExtension` at `0x1800d2469`
- `lsass!LsaRegisterExtension` at `0x1800d24dc`
- `lsass!LsaRegisterExtension` at `0x1800d254f`
- `lsass!LsaRegisterExtension` at `0x1800d2469`
- `lsass!LsaRegisterExtension` at `0x1800d24dc`
- `lsass!LsaRegisterExtension` at `0x1800d254f`

## string_xrefs

- `0x1800d23d1`: `ServiceInit failed`
- `0x1800d24a1`: `LsaRegisterExtension(LsaRmExtension) failed`
- `0x1800d2514`: `LsaRegisterExtension(LsaSspiRpcExtention) failed`
- `0x1800d2587`: `LsaRegisterExtension(LsaPolicyLookupExtension) failed`

## pseudocode

```c
__int64 LsapLsaExtensionLoad(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  const wchar_t *v2; // rdx
  int Interface; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  int inited; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  struct _LSA_RM_FUNCTIONS *v13; // [rsp+40h] [rbp+8h] BYREF

  v13 = 0;
  v0 = TlgRegisterAggregateProviderEx();
  if ( v0 < 0
    && WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_fbab38a9e468344a0955481828104e3b_Traceguids, (unsigned int)v0);
  }
  LsaInitializeAutoLoggerSession();
  qword_18019DE10 = 0;
  WPP_MAIN_CB = (__int64)&qword_18019DE28;
  qword_18019DE28 = (__int64)&qword_18019DE50;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_LsaTraceControlGuid;
  qword_18019DE80 = (__int64)WPP_ThisDir_CTLGUID_LsaAuditTraceControlGuid;
  qword_18019DE88 = (__int64)WPP_ThisDir_CTLGUID_LsaDsTraceControlGuid;
  WPP_GLOBAL_Control = (LsaHandleCache *)&WPP_MAIN_CB;
  qword_18019DE18 = 1;
  qword_18019DE38 = 0;
  qword_18019DE40 = 1;
  qword_18019DE60 = 0;
  qword_18019DE50 = 0;
  qword_18019DE68 = 1;
  WppInitUm();
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_fbab38a9e468344a0955481828104e3b_Traceguids);
  RtlInitializeCriticalSection(&g_LsaExtensionTableLsaDbLock);
  LsapSetupTuningParameters();
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  dword_1801A0208 = 0;
  qword_1801A02B0 = LsapAllocate(800);
  if ( !qword_1801A02B0 )
  {
    v1 = -1073741801;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_fbab38a9e468344a0955481828104e3b_Traceguids, 3221225495LL);
    }
    v2 = L"LsapInitializeErrorHistory failed";
LABEL_13:
    LsapSetErrorInfo(v1, v2);
    goto LABEL_74;
  }
  Interface = LsaGetInterface(0, &v13);
  v1 = Interface;
  if ( Interface < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_fbab38a9e468344a0955481828104e3b_Traceguids,
        (unsigned int)Interface);
    }
    v2 = L"LsaGetInterface(LsaResourceManagerInterface) failed";
    goto LABEL_13;
  }
  LsapRmInterface = v13;
  v4 = LsaGetInterface(1, &v13);
  v1 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_fbab38a9e468344a0955481828104e3b_Traceguids,
        (unsigned int)v4);
    }
    v2 = L"LsaGetInterface(LsaCallbackInterface) failed";
    goto LABEL_13;
  }
  LsapCallbackInterface = v13;
  v5 = LsapCheckBootMode();
  v1 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_fbab38a9e468344a0955481828104e3b_Traceguids,
        (unsigned int)v5);
    }
    v2 = L"LsapCheckBootMode failed";
    goto LABEL_13;
  }
  v6 = LsapContainerModeInit();
  v1 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        WPP_fbab38a9e468344a0955481828104e3b_Traceguids,
        (unsigned int)v6);
    }
    v2 = L"LsapContainerModeInit failed";
    goto LABEL_13;
  }
  v7 = ServiceInit();
  v1 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_fbab38a9e468344a0955481828104e3b_Traceguids,
        (unsigned int)v7);
    }
    v2 = L"ServiceInit failed";
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_fbab38a9e468344a0955481828104e3b_Traceguids);
  inited = LsapInitLsa();
  v1 = inited;
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_fbab38a9e468344a0955481828104e3b_Traceguids,
        (unsigned int)inited);
    }
    v2 = L"LsapInitLsa failed";
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_fbab38a9e468344a0955481828104e3b_Traceguids);
  v9 = LsaRegisterExtension(0, &LsapRmExtensionFunctions);
  v1 = v9;
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_fbab38a9e468344a0955481828104e3b_Traceguids,
        (unsigned int)v9);
    }
    v2 = L"LsaRegisterExtension(LsaRmExtension) failed";
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_fbab38a9e468344a0955481828104e3b_Traceguids);
  v10 = LsaRegisterExtension(2, &LsapSspiExtensionFunctions);
  v1 = v10;
  if ( v10 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        WPP_fbab38a9e468344a0955481828104e3b_Traceguids,
        (unsigned int)v10);
    }
    v2 = L"LsaRegisterExtension(LsaSspiRpcExtention) failed";
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_fbab38a9e468344a0955481828104e3b_Traceguids);
  v11 = LsaRegisterExtension(3, &LsapLookupExtensionFunctions);
  v1 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        WPP_fbab38a9e468344a0955481828104e3b_Traceguids,
        (unsigned int)v11);
    }
    v2 = L"LsaRegisterExtension(LsaPolicyLookupExtension) failed";
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control )
    return v1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_fbab38a9e468344a0955481828104e3b_Traceguids);
LABEL_74:
  if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x80) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_fbab38a9e468344a0955481828104e3b_Traceguids, v1);
  return v1;
}

```

## disassembly

```asm
0x1800d20d8  mov     [rsp+arg_8], rbx
0x1800d20dd  mov     [rsp+arg_10], rbp
0x1800d20e2  push    rsi
0x1800d20e3  push    rdi
0x1800d20e4  push    r14
0x1800d20e6  sub     rsp, 20h
0x1800d20ea  xor     esi, esi
0x1800d20ec  mov     [rsp+38h+arg_0], rsi
0x1800d20f1  call    TlgRegisterAggregateProviderEx
0x1800d20f6  lea     r14, WPP_fbab38a9e468344a0955481828104e3b_Traceguids
0x1800d20fd  lea     rdi, WPP_GLOBAL_Control
0x1800d2104  test    eax, eax
0x1800d2106  jns     short loc_1800D212C
0x1800d2108  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d210f  cmp     rcx, rdi
0x1800d2112  jz      short loc_1800D212C
0x1800d2114  test    byte ptr [rcx+1Ch], 2
0x1800d2118  jz      short loc_1800D212C
0x1800d211a  mov     rcx, [rcx+10h]
0x1800d211e  lea     edx, [rsi+0Eh]
0x1800d2121  mov     r9d, eax
0x1800d2124  mov     r8, r14
0x1800d2127  call    WPP_SF_d
0x1800d212c  call    ?LsaInitializeAutoLoggerSession@@YAXXZ; LsaInitializeAutoLoggerSession(void)
0x1800d2131  lea     rax, qword_18019DE28
0x1800d2138  mov     cs:qword_18019DE10, rsi
0x1800d213f  mov     cs:WPP_MAIN_CB, rax
0x1800d2146  lea     rax, qword_18019DE50
0x1800d214d  mov     cs:qword_18019DE28, rax
0x1800d2154  lea     rax, WPP_ThisDir_CTLGUID_LsaTraceControlGuid
0x1800d215b  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x1800d2162  lea     rax, WPP_ThisDir_CTLGUID_LsaAuditTraceControlGuid
0x1800d2169  mov     cs:qword_18019DE80, rax
0x1800d2170  lea     rax, WPP_ThisDir_CTLGUID_LsaDsTraceControlGuid
0x1800d2177  mov     cs:qword_18019DE88, rax
0x1800d217e  lea     rax, WPP_MAIN_CB
0x1800d2185  mov     cs:WPP_GLOBAL_Control, rax
0x1800d218c  mov     cs:qword_18019DE18, 1
0x1800d2197  mov     cs:qword_18019DE38, rsi
0x1800d219e  mov     cs:qword_18019DE40, 1
0x1800d21a9  mov     cs:qword_18019DE60, rsi
0x1800d21b0  mov     cs:qword_18019DE50, rsi
0x1800d21b7  mov     cs:qword_18019DE68, 1
0x1800d21c2  call    WppInitUm
0x1800d21c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d21ce  mov     bpl, 80h
0x1800d21d1  cmp     rcx, rdi
0x1800d21d4  jz      short loc_1800D21ED
0x1800d21d6  test    [rcx+1Ch], bpl
0x1800d21da  jz      short loc_1800D21ED
0x1800d21dc  mov     rcx, [rcx+10h]
0x1800d21e0  mov     edx, 0Fh
0x1800d21e5  mov     r8, r14
0x1800d21e8  call    WPP_SF_
0x1800d21ed  lea     rcx, ?g_LsaExtensionTableLsaDbLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800d21f4  call    cs:__imp_RtlInitializeCriticalSection
0x1800d21fb  nop     dword ptr [rax+rax+00h]
0x1800d2200  call    ?LsapSetupTuningParameters@@YAXXZ; LsapSetupTuningParameters(void)
0x1800d2205  xor     r9d, r9d; HeapInformationLength
0x1800d2208  xor     r8d, r8d; HeapInformation
0x1800d220b  xor     ecx, ecx; HeapHandle
0x1800d220d  lea     edx, [r9+1]; HeapInformationClass
0x1800d2211  call    cs:__imp_HeapSetInformation
0x1800d2218  nop     dword ptr [rax+rax+00h]
0x1800d221d  mov     ecx, 320h
0x1800d2222  mov     cs:dword_1801A0208, esi
0x1800d2228  call    LsapAllocate
0x1800d222d  mov     cs:qword_1801A02B0, rax
0x1800d2234  test    rax, rax
0x1800d2237  jnz     short loc_1800D2278
0x1800d2239  mov     ebx, 0C0000017h
0x1800d223e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2245  cmp     rcx, rdi
0x1800d2248  jz      short loc_1800D2265
0x1800d224a  test    [rcx+1Ch], bpl
0x1800d224e  jz      short loc_1800D2265
0x1800d2250  mov     rcx, [rcx+10h]
0x1800d2254  lea     edx, [rax+10h]
0x1800d2257  mov     r9d, 0C0000017h
0x1800d225d  mov     r8, r14
0x1800d2260  call    WPP_SF_d
0x1800d2265  lea     rdx, aLsapinitialize_0; "LsapInitializeErrorHistory failed"
0x1800d226c  mov     ecx, ebx
0x1800d226e  call    LsapSetErrorInfo
0x1800d2273  jmp     loc_1800D25B6
0x1800d2278  lea     rdx, [rsp+38h+arg_0]
0x1800d227d  xor     ecx, ecx
0x1800d227f  call    cs:__imp_LsaGetInterface
0x1800d2286  nop     dword ptr [rax+rax+00h]
0x1800d228b  mov     ebx, eax
0x1800d228d  test    eax, eax
0x1800d228f  jns     short loc_1800D22C0
0x1800d2291  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2298  cmp     rcx, rdi
0x1800d229b  jz      short loc_1800D22B7
0x1800d229d  test    [rcx+1Ch], bpl
0x1800d22a1  jz      short loc_1800D22B7
0x1800d22a3  mov     rcx, [rcx+10h]
0x1800d22a7  mov     edx, 11h
0x1800d22ac  mov     r9d, eax
0x1800d22af  mov     r8, r14
0x1800d22b2  call    WPP_SF_d
0x1800d22b7  lea     rdx, aLsagetinterfac_1; "LsaGetInterface(LsaResourceManagerInter"...
0x1800d22be  jmp     short loc_1800D226C
0x1800d22c0  mov     rax, [rsp+38h+arg_0]
0x1800d22c5  lea     rdx, [rsp+38h+arg_0]
0x1800d22ca  mov     ecx, 1
0x1800d22cf  mov     cs:?LsapRmInterface@@3PEAU_LSA_RM_FUNCTIONS@@EA, rax; _LSA_RM_FUNCTIONS * LsapRmInterface
0x1800d22d6  call    cs:__imp_LsaGetInterface
0x1800d22dd  nop     dword ptr [rax+rax+00h]
0x1800d22e2  mov     ebx, eax
0x1800d22e4  test    eax, eax
0x1800d22e6  jns     short loc_1800D231A
0x1800d22e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d22ef  cmp     rcx, rdi
0x1800d22f2  jz      short loc_1800D230E
0x1800d22f4  test    [rcx+1Ch], bpl
0x1800d22f8  jz      short loc_1800D230E
0x1800d22fa  mov     rcx, [rcx+10h]
0x1800d22fe  mov     edx, 12h
0x1800d2303  mov     r9d, eax
0x1800d2306  mov     r8, r14
0x1800d2309  call    WPP_SF_d
0x1800d230e  lea     rdx, aLsagetinterfac_2; "LsaGetInterface(LsaCallbackInterface) f"...
0x1800d2315  jmp     loc_1800D226C
0x1800d231a  mov     rax, [rsp+38h+arg_0]
0x1800d231f  mov     cs:?LsapCallbackInterface@@3PEAU_LSA_CALLBACK_FUNCTIONS@@EA, rax; _LSA_CALLBACK_FUNCTIONS * LsapCallbackInterface
0x1800d2326  call    LsapCheckBootMode
0x1800d232b  mov     ebx, eax
0x1800d232d  test    eax, eax
0x1800d232f  jns     short loc_1800D2363
0x1800d2331  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2338  cmp     rcx, rdi
0x1800d233b  jz      short loc_1800D2357
0x1800d233d  test    [rcx+1Ch], bpl
0x1800d2341  jz      short loc_1800D2357
0x1800d2343  mov     rcx, [rcx+10h]
0x1800d2347  mov     edx, 13h
0x1800d234c  mov     r9d, eax
0x1800d234f  mov     r8, r14
0x1800d2352  call    WPP_SF_d
0x1800d2357  lea     rdx, aLsapcheckbootm_0; "LsapCheckBootMode failed"
0x1800d235e  jmp     loc_1800D226C
0x1800d2363  call    ?LsapContainerModeInit@@YAJXZ; LsapContainerModeInit(void)
0x1800d2368  mov     ebx, eax
0x1800d236a  test    eax, eax
0x1800d236c  jns     short loc_1800D23A0
0x1800d236e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2375  cmp     rcx, rdi
0x1800d2378  jz      short loc_1800D2394
0x1800d237a  test    [rcx+1Ch], bpl
0x1800d237e  jz      short loc_1800D2394
0x1800d2380  mov     rcx, [rcx+10h]
0x1800d2384  mov     edx, 14h
0x1800d2389  mov     r9d, eax
0x1800d238c  mov     r8, r14
0x1800d238f  call    WPP_SF_d
0x1800d2394  lea     rdx, aLsapcontainerm; "LsapContainerModeInit failed"
0x1800d239b  jmp     loc_1800D226C
0x1800d23a0  call    ServiceInit
0x1800d23a5  mov     ebx, eax
0x1800d23a7  test    eax, eax
0x1800d23a9  jns     short loc_1800D23DD
0x1800d23ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d23b2  cmp     rcx, rdi
0x1800d23b5  jz      short loc_1800D23D1
0x1800d23b7  test    [rcx+1Ch], bpl
0x1800d23bb  jz      short loc_1800D23D1
0x1800d23bd  mov     rcx, [rcx+10h]
0x1800d23c1  mov     edx, 15h
0x1800d23c6  mov     r9d, eax
0x1800d23c9  mov     r8, r14
0x1800d23cc  call    WPP_SF_d
0x1800d23d1  lea     rdx, aServiceinitFai; "ServiceInit failed"
0x1800d23d8  jmp     loc_1800D226C
0x1800d23dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d23e4  cmp     rcx, rdi
0x1800d23e7  jz      short loc_1800D2400
0x1800d23e9  test    [rcx+1Ch], bpl
0x1800d23ed  jz      short loc_1800D2400
0x1800d23ef  mov     rcx, [rcx+10h]
0x1800d23f3  mov     edx, 16h
0x1800d23f8  mov     r8, r14
0x1800d23fb  call    WPP_SF_
0x1800d2400  call    LsapInitLsa
0x1800d2405  mov     ebx, eax
0x1800d2407  test    eax, eax
0x1800d2409  jns     short loc_1800D243D
0x1800d240b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2412  cmp     rcx, rdi
0x1800d2415  jz      short loc_1800D2431
0x1800d2417  test    [rcx+1Ch], bpl
0x1800d241b  jz      short loc_1800D2431
0x1800d241d  mov     rcx, [rcx+10h]
0x1800d2421  mov     edx, 17h
0x1800d2426  mov     r9d, eax
0x1800d2429  mov     r8, r14
0x1800d242c  call    WPP_SF_d
0x1800d2431  lea     rdx, aLsapinitlsaFai; "LsapInitLsa failed"
0x1800d2438  jmp     loc_1800D226C
0x1800d243d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2444  cmp     rcx, rdi
0x1800d2447  jz      short loc_1800D2460
0x1800d2449  test    [rcx+1Ch], bpl
0x1800d244d  jz      short loc_1800D2460
0x1800d244f  mov     rcx, [rcx+10h]
0x1800d2453  mov     edx, 18h
0x1800d2458  mov     r8, r14
0x1800d245b  call    WPP_SF_
0x1800d2460  lea     rdx, ?LsapRmExtensionFunctions@@3U_LSA_RM_EX_FUNCTIONS@@A; _LSA_RM_EX_FUNCTIONS LsapRmExtensionFunctions
0x1800d2467  xor     ecx, ecx
0x1800d2469  call    cs:__imp_LsaRegisterExtension
0x1800d2470  nop     dword ptr [rax+rax+00h]
0x1800d2475  mov     ebx, eax
0x1800d2477  test    eax, eax
0x1800d2479  jns     short loc_1800D24AD
0x1800d247b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2482  cmp     rcx, rdi
0x1800d2485  jz      short loc_1800D24A1
0x1800d2487  test    [rcx+1Ch], bpl
0x1800d248b  jz      short loc_1800D24A1
0x1800d248d  mov     rcx, [rcx+10h]
0x1800d2491  mov     edx, 19h
0x1800d2496  mov     r9d, eax
0x1800d2499  mov     r8, r14
0x1800d249c  call    WPP_SF_d
0x1800d24a1  lea     rdx, aLsaregisterext_0; "LsaRegisterExtension(LsaRmExtension) fa"...
0x1800d24a8  jmp     loc_1800D226C
0x1800d24ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d24b4  cmp     rcx, rdi
0x1800d24b7  jz      short loc_1800D24D0
0x1800d24b9  test    [rcx+1Ch], bpl
0x1800d24bd  jz      short loc_1800D24D0
0x1800d24bf  mov     rcx, [rcx+10h]
0x1800d24c3  mov     edx, 1Ah
0x1800d24c8  mov     r8, r14
0x1800d24cb  call    WPP_SF_
0x1800d24d0  lea     rdx, ?LsapSspiExtensionFunctions@@3U_LSA_SSPI_EX_RPC_FUNCTIONS@@A; _LSA_SSPI_EX_RPC_FUNCTIONS LsapSspiExtensionFunctions
0x1800d24d7  mov     ecx, 2
0x1800d24dc  call    cs:__imp_LsaRegisterExtension
0x1800d24e3  nop     dword ptr [rax+rax+00h]
0x1800d24e8  mov     ebx, eax
0x1800d24ea  test    eax, eax
0x1800d24ec  jns     short loc_1800D2520
0x1800d24ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d24f5  cmp     rcx, rdi
0x1800d24f8  jz      short loc_1800D2514
0x1800d24fa  test    [rcx+1Ch], bpl
0x1800d24fe  jz      short loc_1800D2514
0x1800d2500  mov     rcx, [rcx+10h]
0x1800d2504  mov     edx, 1Bh
0x1800d2509  mov     r9d, eax
0x1800d250c  mov     r8, r14
0x1800d250f  call    WPP_SF_d
0x1800d2514  lea     rdx, aLsaregisterext_2; "LsaRegisterExtension(LsaSspiRpcExtentio"...
0x1800d251b  jmp     loc_1800D226C
0x1800d2520  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2527  cmp     rcx, rdi
0x1800d252a  jz      short loc_1800D2543
0x1800d252c  test    [rcx+1Ch], bpl
0x1800d2530  jz      short loc_1800D2543
0x1800d2532  mov     rcx, [rcx+10h]
0x1800d2536  mov     edx, 1Ch
0x1800d253b  mov     r8, r14
0x1800d253e  call    WPP_SF_
0x1800d2543  lea     rdx, ?LsapLookupExtensionFunctions@@3U_LSA_LOOKUP_EX_FUNCTIONS@@A; _LSA_LOOKUP_EX_FUNCTIONS LsapLookupExtensionFunctions
0x1800d254a  mov     ecx, 3
0x1800d254f  call    cs:__imp_LsaRegisterExtension
0x1800d2556  nop     dword ptr [rax+rax+00h]
0x1800d255b  mov     ebx, eax
0x1800d255d  test    eax, eax
0x1800d255f  jns     short loc_1800D2593
0x1800d2561  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d2568  cmp     rcx, rdi
0x1800d256b  jz      short loc_1800D2587
0x1800d256d  test    [rcx+1Ch], bpl
0x1800d2571  jz      short loc_1800D2587
0x1800d2573  mov     rcx, [rcx+10h]
0x1800d2577  mov     edx, 1Dh
0x1800d257c  mov     r9d, eax
0x1800d257f  mov     r8, r14
0x1800d2582  call    WPP_SF_d
0x1800d2587  lea     rdx, aLsaregisterext_1; "LsaRegisterExtension(LsaPolicyLookupExt"...
0x1800d258e  jmp     loc_1800D226C
0x1800d2593  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d259a  cmp     rcx, rdi
0x1800d259d  jz      short loc_1800D25DC
0x1800d259f  test    [rcx+1Ch], bpl
0x1800d25a3  jz      short loc_1800D25B6
0x1800d25a5  mov     rcx, [rcx+10h]
0x1800d25a9  mov     edx, 1Eh
0x1800d25ae  mov     r8, r14
0x1800d25b1  call    WPP_SF_
0x1800d25b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d25bd  cmp     rcx, rdi
0x1800d25c0  jz      short loc_1800D25DC
0x1800d25c2  test    [rcx+1Ch], bpl
0x1800d25c6  jz      short loc_1800D25DC
0x1800d25c8  mov     rcx, [rcx+10h]
0x1800d25cc  mov     edx, 1Fh
  ... truncated ...
```
