# DhcpInitializePerfCounters

- ea: `0x180078c00`
- end: `0x18007902b`
- name: `DhcpInitializePerfCounters`
- size: `1067`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006632c`

## callees

- `0x180002854`
- `0x180078c00`

## import_xrefs

- `ADVAPI32!PerfCreateInstance` at `0x180078ce6`
- `ADVAPI32!PerfCreateInstance` at `0x180078e38`
- `ADVAPI32!PerfCreateInstance` at `0x180078ce6`
- `ADVAPI32!PerfCreateInstance` at `0x180078e38`
- `ADVAPI32!PerfStopProvider` at `0x180078c80`
- `ADVAPI32!PerfStopProvider` at `0x180078d1f`
- `ADVAPI32!PerfStopProvider` at `0x180078e71`
- `ADVAPI32!PerfStopProvider` at `0x180078c80`
- `ADVAPI32!PerfStopProvider` at `0x180078d1f`
- `ADVAPI32!PerfStopProvider` at `0x180078e71`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x180078c41`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x180078c67`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x180078c41`
- `ADVAPI32!PerfSetCounterSetInfo` at `0x180078c67`
- `ADVAPI32!PerfStartProvider` at `0x180078c1b`
- `ADVAPI32!PerfStartProvider` at `0x180078c1b`
- `KERNEL32!GetLastError` at `0x180078d01`
- `KERNEL32!GetLastError` at `0x180078e53`
- `KERNEL32!GetLastError` at `0x180078d01`
- `KERNEL32!GetLastError` at `0x180078e53`

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
    Dhcpv6PerfCounters = (__int64)Instance + (unsigned int)dword_1800F93D4;
    qword_180155148 = (__int64)Instance + (unsigned int)dword_1800F93F4;
    qword_180155150 = (__int64)Instance + (unsigned int)dword_1800F9414;
    qword_180155158 = (__int64)Instance + (unsigned int)dword_1800F9434;
    qword_180155160 = (__int64)Instance + (unsigned int)dword_1800F9454;
    qword_180155168 = (__int64)Instance + (unsigned int)dword_1800F9474;
    qword_180155170 = (__int64)Instance + (unsigned int)dword_1800F9494;
    qword_180155178 = (__int64)Instance + (unsigned int)dword_1800F94B4;
    qword_180155180 = (__int64)Instance + (unsigned int)dword_1800F94D4;
    qword_180155188 = (__int64)Instance + (unsigned int)dword_1800F94F4;
    qword_180155190 = (__int64)Instance + (unsigned int)dword_1800F9514;
    qword_180155198 = (__int64)Instance + (unsigned int)dword_1800F9534;
    qword_1801551A0 = (__int64)Instance + (unsigned int)dword_1800F9554;
    qword_1801551A8 = (__int64)Instance + (unsigned int)dword_1800F9574;
    qword_1801551B0 = (__int64)Instance + (unsigned int)dword_1800F9594;
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
    Dhcpv4PerfCounters = (__int64)v4 + (unsigned int)dword_1800F9064;
    qword_1801551C8 = (__int64)v4 + (unsigned int)dword_1800F9084;
    qword_1801551D0 = (__int64)v4 + (unsigned int)dword_1800F90A4;
    qword_1801551D8 = (__int64)v4 + (unsigned int)dword_1800F90C4;
    qword_1801551E0 = (__int64)v4 + (unsigned int)dword_1800F90E4;
    qword_1801551E8 = (__int64)v4 + (unsigned int)dword_1800F9104;
    qword_1801551F0 = (__int64)v4 + (unsigned int)dword_1800F9124;
    qword_1801551F8 = (__int64)v4 + (unsigned int)dword_1800F9144;
    qword_180155200 = (__int64)v4 + (unsigned int)dword_1800F9164;
    qword_180155208 = (__int64)v4 + (unsigned int)dword_1800F9184;
    qword_180155210 = (__int64)v4 + (unsigned int)dword_1800F91A4;
    qword_180155218 = (__int64)v4 + (unsigned int)dword_1800F91C4;
    qword_180155220 = (__int64)v4 + (unsigned int)dword_1800F91E4;
    qword_180155228 = (__int64)v4 + (unsigned int)dword_1800F9204;
    qword_180155230 = (__int64)v4 + (unsigned int)dword_1800F9224;
    qword_180155238 = (__int64)v4 + (unsigned int)dword_1800F9244;
    qword_180155240 = (__int64)v4 + (unsigned int)dword_1800F9264;
    qword_180155248 = (__int64)v4 + (unsigned int)dword_1800F9284;
    qword_180155250 = (__int64)v4 + (unsigned int)dword_1800F92A4;
    qword_180155258 = (__int64)v4 + (unsigned int)dword_1800F92C4;
    qword_180155260 = (__int64)v4 + (unsigned int)dword_1800F92E4;
    qword_180155268 = (__int64)v4 + (unsigned int)dword_1800F9304;
    qword_180155270 = (__int64)v4 + (unsigned int)dword_1800F9324;
    qword_180155278 = (__int64)v4 + (unsigned int)dword_1800F9344;
    qword_180155280 = (__int64)v4 + (unsigned int)dword_1800F9364;
    qword_180155288 = (__int64)v4 + (unsigned int)dword_1800F9384;
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
0x180078c00  push    rbx
0x180078c02  sub     rsp, 20h
0x180078c06  lea     r8, hDataSource_dhcpserverperf_1; phProvider
0x180078c0d  lea     rdx, ControlCallback_dhcpserverperf_1; ControlCallback
0x180078c14  lea     rcx, ProviderGuid_dhcpserverperf_1; ProviderGuid
0x180078c1b  call    cs:__imp_PerfStartProvider
0x180078c22  nop     dword ptr [rax+rax+00h]
0x180078c27  mov     ebx, eax
0x180078c29  test    eax, eax
0x180078c2b  jnz     short loc_180078C79
0x180078c2d  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078c34  lea     rdx, CtrSet_dhcpserverperf_1_1; Template
0x180078c3b  mov     r8d, 208h; TemplateSize
0x180078c41  call    cs:__imp_PerfSetCounterSetInfo
0x180078c48  nop     dword ptr [rax+rax+00h]
0x180078c4d  mov     ebx, eax
0x180078c4f  test    eax, eax
0x180078c51  jnz     short loc_180078C79
0x180078c53  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078c5a  lea     rdx, CtrSet_dhcpserverperf_1_2; Template
0x180078c61  mov     r8d, 368h; TemplateSize
0x180078c67  call    cs:__imp_PerfSetCounterSetInfo
0x180078c6e  nop     dword ptr [rax+rax+00h]
0x180078c73  mov     ebx, eax
0x180078c75  test    eax, eax
0x180078c77  jz      short loc_180078C8C
0x180078c79  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078c80  call    cs:__imp_PerfStopProvider
0x180078c87  nop     dword ptr [rax+rax+00h]
0x180078c8c  test    ebx, ebx
0x180078c8e  jz      short loc_180078CCE
0x180078c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180078c97  lea     rax, WPP_GLOBAL_Control
0x180078c9e  cmp     rcx, rax
0x180078ca1  jz      loc_180079022
0x180078ca7  test    byte ptr [rcx+1Ch], 10h
0x180078cab  jz      loc_180079022
0x180078cb1  mov     rcx, [rcx+10h]
0x180078cb5  lea     r8, WPP_d6d1a441a6de31f9f69a4e12ffa36757_Traceguids
0x180078cbc  mov     edx, 0Ah
0x180078cc1  mov     r9d, ebx
0x180078cc4  call    WPP_SF_D
0x180078cc9  jmp     loc_180079022
0x180078cce  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078cd5  lea     r8, Name; "_Default"
0x180078cdc  xor     r9d, r9d; Id
0x180078cdf  lea     rdx, CtrSetGuid_dhcpserverperf_1_1; CounterSetGuid
0x180078ce6  call    cs:__imp_PerfCreateInstance
0x180078ced  nop     dword ptr [rax+rax+00h]
0x180078cf2  mov     cs:pPerfInstCounterV6, rax
0x180078cf9  mov     rcx, rax
0x180078cfc  test    rax, rax
0x180078cff  jnz     short loc_180078D30
0x180078d01  call    cs:__imp_GetLastError
0x180078d08  nop     dword ptr [rax+rax+00h]
0x180078d0d  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078d14  mov     ebx, eax
0x180078d16  test    rcx, rcx
0x180078d19  jz      loc_180078E27
0x180078d1f  call    cs:__imp_PerfStopProvider
0x180078d26  nop     dword ptr [rax+rax+00h]
0x180078d2b  jmp     loc_180078E20
0x180078d30  mov     eax, cs:dword_1800F93D4
0x180078d36  add     rax, rcx
0x180078d39  mov     cs:Dhcpv6PerfCounters, rax
0x180078d40  mov     eax, cs:dword_1800F93F4
0x180078d46  add     rax, rcx
0x180078d49  mov     cs:qword_180155148, rax
0x180078d50  mov     eax, cs:dword_1800F9414
0x180078d56  add     rax, rcx
0x180078d59  mov     cs:qword_180155150, rax
0x180078d60  mov     eax, cs:dword_1800F9434
0x180078d66  add     rax, rcx
0x180078d69  mov     cs:qword_180155158, rax
0x180078d70  mov     eax, cs:dword_1800F9454
0x180078d76  add     rax, rcx
0x180078d79  mov     cs:qword_180155160, rax
0x180078d80  mov     eax, cs:dword_1800F9474
0x180078d86  add     rax, rcx
0x180078d89  mov     cs:qword_180155168, rax
0x180078d90  mov     eax, cs:dword_1800F9494
0x180078d96  add     rax, rcx
0x180078d99  mov     cs:qword_180155170, rax
0x180078da0  mov     eax, cs:dword_1800F94B4
0x180078da6  add     rax, rcx
0x180078da9  mov     cs:qword_180155178, rax
0x180078db0  mov     eax, cs:dword_1800F94D4
0x180078db6  add     rax, rcx
0x180078db9  mov     cs:qword_180155180, rax
0x180078dc0  mov     eax, cs:dword_1800F94F4
0x180078dc6  add     rax, rcx
0x180078dc9  mov     cs:qword_180155188, rax
0x180078dd0  mov     eax, cs:dword_1800F9514
0x180078dd6  add     rax, rcx
0x180078dd9  mov     cs:qword_180155190, rax
0x180078de0  mov     eax, cs:dword_1800F9534
0x180078de6  add     rax, rcx
0x180078de9  mov     cs:qword_180155198, rax
0x180078df0  mov     eax, cs:dword_1800F9554
0x180078df6  add     rax, rcx
0x180078df9  mov     cs:qword_1801551A0, rax
0x180078e00  mov     eax, cs:dword_1800F9574
0x180078e06  add     rax, rcx
0x180078e09  mov     cs:qword_1801551A8, rax
0x180078e10  mov     eax, cs:dword_1800F9594
0x180078e16  add     rax, rcx
0x180078e19  mov     cs:qword_1801551B0, rax
0x180078e20  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078e27  xor     r9d, r9d; Id
0x180078e2a  lea     r8, Name; "_Default"
0x180078e31  lea     rdx, CtrSetGuid_dhcpserverperf_1_2; CounterSetGuid
0x180078e38  call    cs:__imp_PerfCreateInstance
0x180078e3f  nop     dword ptr [rax+rax+00h]
0x180078e44  mov     cs:pPerfInstCounterV4, rax
0x180078e4b  mov     rcx, rax
0x180078e4e  test    rax, rax
0x180078e51  jnz     short loc_180078E82
0x180078e53  call    cs:__imp_GetLastError
0x180078e5a  nop     dword ptr [rax+rax+00h]
0x180078e5f  mov     rcx, cs:hDataSource_dhcpserverperf_1; ProviderHandle
0x180078e66  mov     ebx, eax
0x180078e68  test    rcx, rcx
0x180078e6b  jz      loc_180079022
0x180078e71  call    cs:__imp_PerfStopProvider
0x180078e78  nop     dword ptr [rax+rax+00h]
0x180078e7d  jmp     loc_180079022
0x180078e82  mov     eax, cs:dword_1800F9064
0x180078e88  add     rax, rcx
0x180078e8b  mov     cs:Dhcpv4PerfCounters, rax
0x180078e92  mov     eax, cs:dword_1800F9084
0x180078e98  add     rax, rcx
0x180078e9b  mov     cs:qword_1801551C8, rax
0x180078ea2  mov     eax, cs:dword_1800F90A4
0x180078ea8  add     rax, rcx
0x180078eab  mov     cs:qword_1801551D0, rax
0x180078eb2  mov     eax, cs:dword_1800F90C4
0x180078eb8  add     rax, rcx
0x180078ebb  mov     cs:qword_1801551D8, rax
0x180078ec2  mov     eax, cs:dword_1800F90E4
0x180078ec8  add     rax, rcx
0x180078ecb  mov     cs:qword_1801551E0, rax
0x180078ed2  mov     eax, cs:dword_1800F9104
0x180078ed8  add     rax, rcx
0x180078edb  mov     cs:qword_1801551E8, rax
0x180078ee2  mov     eax, cs:dword_1800F9124
0x180078ee8  add     rax, rcx
0x180078eeb  mov     cs:qword_1801551F0, rax
0x180078ef2  mov     eax, cs:dword_1800F9144
0x180078ef8  add     rax, rcx
0x180078efb  mov     cs:qword_1801551F8, rax
0x180078f02  mov     eax, cs:dword_1800F9164
0x180078f08  add     rax, rcx
0x180078f0b  mov     cs:qword_180155200, rax
0x180078f12  mov     eax, cs:dword_1800F9184
0x180078f18  add     rax, rcx
0x180078f1b  mov     cs:qword_180155208, rax
0x180078f22  mov     eax, cs:dword_1800F91A4
0x180078f28  add     rax, rcx
0x180078f2b  mov     cs:qword_180155210, rax
0x180078f32  mov     eax, cs:dword_1800F91C4
0x180078f38  add     rax, rcx
0x180078f3b  mov     cs:qword_180155218, rax
0x180078f42  mov     eax, cs:dword_1800F91E4
0x180078f48  add     rax, rcx
0x180078f4b  mov     cs:qword_180155220, rax
0x180078f52  mov     eax, cs:dword_1800F9204
0x180078f58  add     rax, rcx
0x180078f5b  mov     cs:qword_180155228, rax
0x180078f62  mov     eax, cs:dword_1800F9224
0x180078f68  add     rax, rcx
0x180078f6b  mov     cs:qword_180155230, rax
0x180078f72  mov     eax, cs:dword_1800F9244
0x180078f78  add     rax, rcx
0x180078f7b  mov     cs:qword_180155238, rax
0x180078f82  mov     eax, cs:dword_1800F9264
0x180078f88  add     rax, rcx
0x180078f8b  mov     cs:qword_180155240, rax
0x180078f92  mov     eax, cs:dword_1800F9284
0x180078f98  add     rax, rcx
0x180078f9b  mov     cs:qword_180155248, rax
0x180078fa2  mov     eax, cs:dword_1800F92A4
0x180078fa8  add     rax, rcx
0x180078fab  mov     cs:qword_180155250, rax
0x180078fb2  mov     eax, cs:dword_1800F92C4
0x180078fb8  add     rax, rcx
0x180078fbb  mov     cs:qword_180155258, rax
0x180078fc2  mov     eax, cs:dword_1800F92E4
0x180078fc8  add     rax, rcx
0x180078fcb  mov     cs:qword_180155260, rax
0x180078fd2  mov     eax, cs:dword_1800F9304
0x180078fd8  add     rax, rcx
0x180078fdb  mov     cs:qword_180155268, rax
0x180078fe2  mov     eax, cs:dword_1800F9324
0x180078fe8  add     rax, rcx
0x180078feb  mov     cs:qword_180155270, rax
0x180078ff2  mov     eax, cs:dword_1800F9344
0x180078ff8  add     rax, rcx
0x180078ffb  mov     cs:qword_180155278, rax
0x180079002  mov     eax, cs:dword_1800F9364
0x180079008  add     rax, rcx
0x18007900b  mov     cs:qword_180155280, rax
0x180079012  mov     eax, cs:dword_1800F9384
0x180079018  add     rax, rcx
0x18007901b  mov     cs:qword_180155288, rax
0x180079022  mov     eax, ebx
0x180079024  add     rsp, 20h
0x180079028  pop     rbx
0x180079029  retn
```
