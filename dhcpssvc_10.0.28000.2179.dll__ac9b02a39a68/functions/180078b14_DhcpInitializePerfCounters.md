# DhcpInitializePerfCounters

- ea: `0x180078b14`
- end: `0x180078f3f`
- name: `DhcpInitializePerfCounters`
- size: `1067`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800660dc`

## callees

- `0x18000282c`
- `0x180078b14`

## import_xrefs

- `ADVAPI32!PerfCreateInstance` at `0x180078bfa`
- `ADVAPI32!PerfCreateInstance` at `0x180078d4c`
- `ADVAPI32!PerfCreateInstance` at `0x180078bfa`
- `ADVAPI32!PerfCreateInstance` at `0x180078d4c`
- `ADVAPI32!PerfStopProvider` at `0x180078b94`
- `ADVAPI32!PerfStopProvider` at `0x180078c33`
- `ADVAPI32!PerfStopProvider` at `0x180078d85`
- `ADVAPI32!PerfStopProvider` at `0x180078b94`
- `ADVAPI32!PerfStopProvider` at `0x180078c33`
- `ADVAPI32!PerfStopProvider` at `0x180078d85`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x180078b55`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x180078b7b`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x180078b55`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x180078b7b`
- `ADVAPI32!PerfStartProvider` at `0x180078b2f`
- `ADVAPI32!PerfStartProvider` at `0x180078b2f`
- `KERNEL32!GetLastError` at `0x180078c15`
- `KERNEL32!GetLastError` at `0x180078d67`
- `KERNEL32!GetLastError` at `0x180078c15`
- `KERNEL32!GetLastError` at `0x180078d67`

## pseudocode

```c
__int64 DhcpInitializePerfCounters()
{
  ULONG started; // ebx
  struct _PERF_COUNTERSET_INSTANCE *Instance; // rax
  DWORD LastError; // eax
  HANDLE v3; // rcx
  struct _PERF_COUNTERSET_INSTANCE *v4; // rax

  started = PerfStartProvider(
              &ProviderGuid_dhcpserverperf_1,
              ControlCallback_dhcpserverperf_1,
              &hDataSource_dhcpserverperf_1);
  if ( started
    || (started = PerfSetCounterSetInfo(hDataSource_dhcpserverperf_1, &CtrSet_dhcpserverperf_1_1, 0x208u)) != 0
    || (started = PerfSetCounterSetInfo(hDataSource_dhcpserverperf_1, &CtrSet_dhcpserverperf_1_2, 0x368u)) != 0 )
  {
    PerfStopProvider(hDataSource_dhcpserverperf_1);
  }
  if ( started )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_d6d1a441a6de31f9f69a4e12ffa36757_Traceguids, started);
    return started;
  }
  Instance = PerfCreateInstance(hDataSource_dhcpserverperf_1, &CtrSetGuid_dhcpserverperf_1_1, L"_Default", 0);
  pPerfInstCounterV6 = Instance;
  if ( Instance )
  {
    Dhcpv6PerfCounters = (__int64)Instance + (unsigned int)dword_1800FB3D4;
    qword_1801570E8 = (__int64)Instance + (unsigned int)dword_1800FB3F4;
    qword_1801570F0 = (__int64)Instance + (unsigned int)dword_1800FB414;
    qword_1801570F8 = (__int64)Instance + (unsigned int)dword_1800FB434;
    qword_180157100 = (__int64)Instance + (unsigned int)dword_1800FB454;
    qword_180157108 = (__int64)Instance + (unsigned int)dword_1800FB474;
    qword_180157110 = (__int64)Instance + (unsigned int)dword_1800FB494;
    qword_180157118 = (__int64)Instance + (unsigned int)dword_1800FB4B4;
    qword_180157120 = (__int64)Instance + (unsigned int)dword_1800FB4D4;
    qword_180157128 = (__int64)Instance + (unsigned int)dword_1800FB4F4;
    qword_180157130 = (__int64)Instance + (unsigned int)dword_1800FB514;
    qword_180157138 = (__int64)Instance + (unsigned int)dword_1800FB534;
    qword_180157140 = (__int64)Instance + (unsigned int)dword_1800FB554;
    qword_180157148 = (__int64)Instance + (unsigned int)dword_1800FB574;
    qword_180157150 = (__int64)Instance + (unsigned int)dword_1800FB594;
  }
  else
  {
    LastError = GetLastError();
    v3 = hDataSource_dhcpserverperf_1;
    started = LastError;
    if ( !hDataSource_dhcpserverperf_1 )
      goto LABEL_14;
    PerfStopProvider(hDataSource_dhcpserverperf_1);
  }
  v3 = hDataSource_dhcpserverperf_1;
LABEL_14:
  v4 = PerfCreateInstance(v3, &CtrSetGuid_dhcpserverperf_1_2, L"_Default", 0);
  pPerfInstCounterV4 = v4;
  if ( v4 )
  {
    Dhcpv4PerfCounters = (__int64)v4 + (unsigned int)dword_1800FB064;
    qword_180157168 = (__int64)v4 + (unsigned int)dword_1800FB084;
    qword_180157170 = (__int64)v4 + (unsigned int)dword_1800FB0A4;
    qword_180157178 = (__int64)v4 + (unsigned int)dword_1800FB0C4;
    qword_180157180 = (__int64)v4 + (unsigned int)dword_1800FB0E4;
    qword_180157188 = (__int64)v4 + (unsigned int)dword_1800FB104;
    qword_180157190 = (__int64)v4 + (unsigned int)dword_1800FB124;
    qword_180157198 = (__int64)v4 + (unsigned int)dword_1800FB144;
    qword_1801571A0 = (__int64)v4 + (unsigned int)dword_1800FB164;
    qword_1801571A8 = (__int64)v4 + (unsigned int)dword_1800FB184;
    qword_1801571B0 = (__int64)v4 + (unsigned int)dword_1800FB1A4;
    qword_1801571B8 = (__int64)v4 + (unsigned int)dword_1800FB1C4;
    qword_1801571C0 = (__int64)v4 + (unsigned int)dword_1800FB1E4;
    qword_1801571C8 = (__int64)v4 + (unsigned int)dword_1800FB204;
    qword_1801571D0 = (__int64)v4 + (unsigned int)dword_1800FB224;
    qword_1801571D8 = (__int64)v4 + (unsigned int)dword_1800FB244;
    qword_1801571E0 = (__int64)v4 + (unsigned int)dword_1800FB264;
    qword_1801571E8 = (__int64)v4 + (unsigned int)dword_1800FB284;
    qword_1801571F0 = (__int64)v4 + (unsigned int)dword_1800FB2A4;
    qword_1801571F8 = (__int64)v4 + (unsigned int)dword_1800FB2C4;
    qword_180157200 = (__int64)v4 + (unsigned int)dword_1800FB2E4;
    qword_180157208 = (__int64)v4 + (unsigned int)dword_1800FB304;
    qword_180157210 = (__int64)v4 + (unsigned int)dword_1800FB324;
    qword_180157218 = (__int64)v4 + (unsigned int)dword_1800FB344;
    qword_180157220 = (__int64)v4 + (unsigned int)dword_1800FB364;
    qword_180157228 = (__int64)v4 + (unsigned int)dword_1800FB384;
  }
  else
  {
    started = GetLastError();
    if ( hDataSource_dhcpserverperf_1 )
      PerfStopProvider(hDataSource_dhcpserverperf_1);
  }
  return started;
}

```

## disassembly

```asm
0x180078b14  push    rbx
0x180078b16  sub     rsp, 20h
0x180078b1a  lea     r8, hDataSource_dhcpserverperf_1; phProvider
0x180078b21  lea     rdx, ControlCallback_dhcpserverperf_1; ControlCallback
0x180078b28  lea     rcx, ProviderGuid_dhcpserverperf_1; ProviderGuid
0x180078b2f  call    cs:__imp_PerfStartProvider
0x180078b36  nop     dword ptr [rax+rax+00h]
0x180078b3b  mov     ebx, eax
0x180078b3d  test    eax, eax
0x180078b3f  jnz     short loc_180078B8D
0x180078b41  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078b48  lea     rdx, CtrSet_dhcpserverperf_1_1; Template
0x180078b4f  mov     r8d, 208h; TemplateSize
0x180078b55  call    cs:__imp_PerfSetCounterSetInfo
0x180078b5c  nop     dword ptr [rax+rax+00h]
0x180078b61  mov     ebx, eax
0x180078b63  test    eax, eax
0x180078b65  jnz     short loc_180078B8D
0x180078b67  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078b6e  lea     rdx, CtrSet_dhcpserverperf_1_2; Template
0x180078b75  mov     r8d, 368h; TemplateSize
0x180078b7b  call    cs:__imp_PerfSetCounterSetInfo
0x180078b82  nop     dword ptr [rax+rax+00h]
0x180078b87  mov     ebx, eax
0x180078b89  test    eax, eax
0x180078b8b  jz      short loc_180078BA0
0x180078b8d  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078b94  call    cs:__imp_PerfStopProvider
0x180078b9b  nop     dword ptr [rax+rax+00h]
0x180078ba0  test    ebx, ebx
0x180078ba2  jz      short loc_180078BE2
0x180078ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180078bab  lea     rax, WPP_GLOBAL_Control
0x180078bb2  cmp     rcx, rax
0x180078bb5  jz      loc_180078F36
0x180078bbb  test    byte ptr [rcx+1Ch], 10h
0x180078bbf  jz      loc_180078F36
0x180078bc5  mov     rcx, [rcx+10h]
0x180078bc9  lea     r8, WPP_d6d1a441a6de31f9f69a4e12ffa36757_Traceguids
0x180078bd0  mov     edx, 0Ah
0x180078bd5  mov     r9d, ebx
0x180078bd8  call    WPP_SF_D
0x180078bdd  jmp     loc_180078F36
0x180078be2  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078be9  lea     r8, Name; "_Default"
0x180078bf0  xor     r9d, r9d; Id
0x180078bf3  lea     rdx, CtrSetGuid_dhcpserverperf_1_1; CounterSetGuid
0x180078bfa  call    cs:__imp_PerfCreateInstance
0x180078c01  nop     dword ptr [rax+rax+00h]
0x180078c06  mov     cs:pPerfInstCounterV6, rax
0x180078c0d  mov     rcx, rax
0x180078c10  test    rax, rax
0x180078c13  jnz     short loc_180078C44
0x180078c15  call    cs:__imp_GetLastError
0x180078c1c  nop     dword ptr [rax+rax+00h]
0x180078c21  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078c28  mov     ebx, eax
0x180078c2a  test    rcx, rcx
0x180078c2d  jz      loc_180078D3B
0x180078c33  call    cs:__imp_PerfStopProvider
0x180078c3a  nop     dword ptr [rax+rax+00h]
0x180078c3f  jmp     loc_180078D34
0x180078c44  mov     eax, cs:dword_1800FB3D4
0x180078c4a  add     rax, rcx
0x180078c4d  mov     cs:Dhcpv6PerfCounters, rax
0x180078c54  mov     eax, cs:dword_1800FB3F4
0x180078c5a  add     rax, rcx
0x180078c5d  mov     cs:qword_1801570E8, rax
0x180078c64  mov     eax, cs:dword_1800FB414
0x180078c6a  add     rax, rcx
0x180078c6d  mov     cs:qword_1801570F0, rax
0x180078c74  mov     eax, cs:dword_1800FB434
0x180078c7a  add     rax, rcx
0x180078c7d  mov     cs:qword_1801570F8, rax
0x180078c84  mov     eax, cs:dword_1800FB454
0x180078c8a  add     rax, rcx
0x180078c8d  mov     cs:qword_180157100, rax
0x180078c94  mov     eax, cs:dword_1800FB474
0x180078c9a  add     rax, rcx
0x180078c9d  mov     cs:qword_180157108, rax
0x180078ca4  mov     eax, cs:dword_1800FB494
0x180078caa  add     rax, rcx
0x180078cad  mov     cs:qword_180157110, rax
0x180078cb4  mov     eax, cs:dword_1800FB4B4
0x180078cba  add     rax, rcx
0x180078cbd  mov     cs:qword_180157118, rax
0x180078cc4  mov     eax, cs:dword_1800FB4D4
0x180078cca  add     rax, rcx
0x180078ccd  mov     cs:qword_180157120, rax
0x180078cd4  mov     eax, cs:dword_1800FB4F4
0x180078cda  add     rax, rcx
0x180078cdd  mov     cs:qword_180157128, rax
0x180078ce4  mov     eax, cs:dword_1800FB514
0x180078cea  add     rax, rcx
0x180078ced  mov     cs:qword_180157130, rax
0x180078cf4  mov     eax, cs:dword_1800FB534
0x180078cfa  add     rax, rcx
0x180078cfd  mov     cs:qword_180157138, rax
0x180078d04  mov     eax, cs:dword_1800FB554
0x180078d0a  add     rax, rcx
0x180078d0d  mov     cs:qword_180157140, rax
0x180078d14  mov     eax, cs:dword_1800FB574
0x180078d1a  add     rax, rcx
0x180078d1d  mov     cs:qword_180157148, rax
0x180078d24  mov     eax, cs:dword_1800FB594
0x180078d2a  add     rax, rcx
0x180078d2d  mov     cs:qword_180157150, rax
0x180078d34  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078d3b  xor     r9d, r9d; Id
0x180078d3e  lea     r8, Name; "_Default"
0x180078d45  lea     rdx, CtrSetGuid_dhcpserverperf_1_2; CounterSetGuid
0x180078d4c  call    cs:__imp_PerfCreateInstance
0x180078d53  nop     dword ptr [rax+rax+00h]
0x180078d58  mov     cs:pPerfInstCounterV4, rax
0x180078d5f  mov     rcx, rax
0x180078d62  test    rax, rax
0x180078d65  jnz     short loc_180078D96
0x180078d67  call    cs:__imp_GetLastError
0x180078d6e  nop     dword ptr [rax+rax+00h]
0x180078d73  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078d7a  mov     ebx, eax
0x180078d7c  test    rcx, rcx
0x180078d7f  jz      loc_180078F36
0x180078d85  call    cs:__imp_PerfStopProvider
0x180078d8c  nop     dword ptr [rax+rax+00h]
0x180078d91  jmp     loc_180078F36
0x180078d96  mov     eax, cs:dword_1800FB064
0x180078d9c  add     rax, rcx
0x180078d9f  mov     cs:Dhcpv4PerfCounters, rax
0x180078da6  mov     eax, cs:dword_1800FB084
0x180078dac  add     rax, rcx
0x180078daf  mov     cs:qword_180157168, rax
0x180078db6  mov     eax, cs:dword_1800FB0A4
0x180078dbc  add     rax, rcx
0x180078dbf  mov     cs:qword_180157170, rax
0x180078dc6  mov     eax, cs:dword_1800FB0C4
0x180078dcc  add     rax, rcx
0x180078dcf  mov     cs:qword_180157178, rax
0x180078dd6  mov     eax, cs:dword_1800FB0E4
0x180078ddc  add     rax, rcx
0x180078ddf  mov     cs:qword_180157180, rax
0x180078de6  mov     eax, cs:dword_1800FB104
0x180078dec  add     rax, rcx
0x180078def  mov     cs:qword_180157188, rax
0x180078df6  mov     eax, cs:dword_1800FB124
0x180078dfc  add     rax, rcx
0x180078dff  mov     cs:qword_180157190, rax
0x180078e06  mov     eax, cs:dword_1800FB144
0x180078e0c  add     rax, rcx
0x180078e0f  mov     cs:qword_180157198, rax
0x180078e16  mov     eax, cs:dword_1800FB164
0x180078e1c  add     rax, rcx
0x180078e1f  mov     cs:qword_1801571A0, rax
0x180078e26  mov     eax, cs:dword_1800FB184
0x180078e2c  add     rax, rcx
0x180078e2f  mov     cs:qword_1801571A8, rax
0x180078e36  mov     eax, cs:dword_1800FB1A4
0x180078e3c  add     rax, rcx
0x180078e3f  mov     cs:qword_1801571B0, rax
0x180078e46  mov     eax, cs:dword_1800FB1C4
0x180078e4c  add     rax, rcx
0x180078e4f  mov     cs:qword_1801571B8, rax
0x180078e56  mov     eax, cs:dword_1800FB1E4
0x180078e5c  add     rax, rcx
0x180078e5f  mov     cs:qword_1801571C0, rax
0x180078e66  mov     eax, cs:dword_1800FB204
0x180078e6c  add     rax, rcx
0x180078e6f  mov     cs:qword_1801571C8, rax
0x180078e76  mov     eax, cs:dword_1800FB224
0x180078e7c  add     rax, rcx
0x180078e7f  mov     cs:qword_1801571D0, rax
0x180078e86  mov     eax, cs:dword_1800FB244
0x180078e8c  add     rax, rcx
0x180078e8f  mov     cs:qword_1801571D8, rax
0x180078e96  mov     eax, cs:dword_1800FB264
0x180078e9c  add     rax, rcx
0x180078e9f  mov     cs:qword_1801571E0, rax
0x180078ea6  mov     eax, cs:dword_1800FB284
0x180078eac  add     rax, rcx
0x180078eaf  mov     cs:qword_1801571E8, rax
0x180078eb6  mov     eax, cs:dword_1800FB2A4
0x180078ebc  add     rax, rcx
0x180078ebf  mov     cs:qword_1801571F0, rax
0x180078ec6  mov     eax, cs:dword_1800FB2C4
0x180078ecc  add     rax, rcx
0x180078ecf  mov     cs:qword_1801571F8, rax
0x180078ed6  mov     eax, cs:dword_1800FB2E4
0x180078edc  add     rax, rcx
0x180078edf  mov     cs:qword_180157200, rax
0x180078ee6  mov     eax, cs:dword_1800FB304
0x180078eec  add     rax, rcx
0x180078eef  mov     cs:qword_180157208, rax
0x180078ef6  mov     eax, cs:dword_1800FB324
0x180078efc  add     rax, rcx
0x180078eff  mov     cs:qword_180157210, rax
0x180078f06  mov     eax, cs:dword_1800FB344
0x180078f0c  add     rax, rcx
0x180078f0f  mov     cs:qword_180157218, rax
0x180078f16  mov     eax, cs:dword_1800FB364
0x180078f1c  add     rax, rcx
0x180078f1f  mov     cs:qword_180157220, rax
0x180078f26  mov     eax, cs:dword_1800FB384
0x180078f2c  add     rax, rcx
0x180078f2f  mov     cs:qword_180157228, rax
0x180078f36  mov     eax, ebx
0x180078f38  add     rsp, 20h
0x180078f3c  pop     rbx
0x180078f3d  retn
```
