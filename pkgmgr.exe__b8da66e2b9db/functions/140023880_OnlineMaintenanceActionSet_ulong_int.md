# OnlineMaintenanceActionSet(ulong,int)

- ea: `0x140023880`
- end: `0x1400239bd`
- name: `?OnlineMaintenanceActionSet@@YAJKH@Z`
- size: `317`
- prototype: `__int64 __fastcall(HKEY, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140013288`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x140017b80`
- `0x140018394`
- `0x140023880`

## string_xrefs

- `0x1400238ae`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide`

## pseudocode

```c
__int64 __fastcall OnlineMaintenanceActionSet(HKEY a1, __int64 a2, __int64 a3)
{
  const wchar_t *v3; // rdx
  HKEY v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // r8
  const wchar_t *v7; // r9
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rdx
  signed int v12; // eax
  __int64 v13; // rdx
  BYTE Data[8]; // [rsp+20h] [rbp-38h]
  int v15[2]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v16; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v16 = 0;
  v5 = CbsRegQueryDWORDValue(
         a1,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide",
         a3,
         L"MaintenanceFlags",
         &v16);
  if ( v5 == -2147024894 )
  {
    v8 = 0;
  }
  else
  {
    if ( (v5 & 0x80000000) != 0 )
    {
      v16 = v5;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed getting maintenance flags.");
        *(_QWORD *)v15 = &v16;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v9,
          3,
          (__int64)": {}",
          (__int64)v15);
      }
      v10 = 94;
      goto LABEL_7;
    }
    v8 = v16;
  }
  *(_DWORD *)Data = v8 & 0x7FFEFFFF;
  v12 = CbsRegSetDWORDValue(v4, v3, v6, v7, *(_QWORD *)Data);
  v5 = v12;
  if ( v12 < 0 )
  {
    v16 = v12;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed updating maintenance flags.");
      *(_QWORD *)v15 = &v16;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v13,
        3,
        (__int64)": {}",
        (__int64)v15);
    }
    v10 = 107;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\util\\cbsmaintenanceactions.cpp",
      (const char *)v5,
      *(int *)Data);
    return v5;
  }
  return 0;
}

```

## disassembly

```asm
0x140023880  push    rbx
0x140023882  sub     rsp, 50h
0x140023886  mov     rax, cs:__security_cookie
0x14002388d  xor     rax, rsp
0x140023890  mov     [rsp+58h+var_18], rax
0x140023895  lea     rax, [rsp+58h+var_20]
0x14002389a  mov     [rsp+58h+var_20], 0
0x1400238a2  lea     r9, aMaintenancefla; "MaintenanceFlags"
0x1400238a9  mov     qword ptr [rsp+58h+Data], rax; unsigned int *
0x1400238ae  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400238b5  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x1400238ba  mov     ebx, eax
0x1400238bc  cmp     eax, 80070002h
0x1400238c1  jnz     short loc_1400238C7
0x1400238c3  xor     eax, eax
0x1400238c5  jmp     short loc_14002393B
0x1400238c7  test    ebx, ebx
0x1400238c9  jns     short loc_140023937
0x1400238cb  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400238d2  mov     [rsp+58h+var_20], ebx
0x1400238d6  test    rcx, rcx
0x1400238d9  jz      short loc_14002391A
0x1400238db  xor     edx, edx
0x1400238dd  lea     r9, aFailedGettingM; "Failed getting maintenance flags."
0x1400238e4  lea     r8d, [rdx+3]
0x1400238e8  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400238ed  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400238f4  lea     rax, [rsp+58h+var_20]
0x1400238f9  mov     qword ptr [rsp+58h+var_28], rax
0x1400238fe  lea     r9, asc_14002D4FC; ": {}"
0x140023905  lea     rax, [rsp+58h+var_28]
0x14002390a  mov     r8d, 3
0x140023910  mov     qword ptr [rsp+58h+Data], rax; int
0x140023915  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002391a  mov     edx, 5Eh ; '^'; void *
0x14002391f  mov     rcx, [rsp+58h]; this
0x140023924  lea     r8, aOnecoreBaseCbs_4; "onecore\\base\\cbs\\util\\cbsmaintenanc"...
0x14002392b  mov     r9d, ebx; char *
0x14002392e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140023933  mov     eax, ebx
0x140023935  jmp     short loc_1400239AA
0x140023937  mov     eax, [rsp+58h+var_20]
0x14002393b  and     eax, 7FFEFFFFh
0x140023940  mov     [rsp+58h+Data], eax; Data
0x140023944  call    ?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z; CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)
0x140023949  mov     ebx, eax
0x14002394b  test    eax, eax
0x14002394d  jns     short loc_1400239A8
0x14002394f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023956  mov     [rsp+58h+var_20], eax
0x14002395a  test    rcx, rcx
0x14002395d  jz      short loc_14002399E
0x14002395f  xor     edx, edx
0x140023961  lea     r9, aFailedUpdating; "Failed updating maintenance flags."
0x140023968  lea     r8d, [rdx+3]
0x14002396c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140023971  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140023978  lea     rax, [rsp+58h+var_20]
0x14002397d  mov     qword ptr [rsp+58h+var_28], rax
0x140023982  lea     r9, asc_14002D4FC; ": {}"
0x140023989  lea     rax, [rsp+58h+var_28]
0x14002398e  mov     r8d, 3
0x140023994  mov     qword ptr [rsp+58h+Data], rax
0x140023999  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14002399e  mov     edx, 6Bh ; 'k'
0x1400239a3  jmp     loc_14002391F
0x1400239a8  xor     eax, eax
0x1400239aa  mov     rcx, [rsp+58h+var_18]
0x1400239af  xor     rcx, rsp; StackCookie
0x1400239b2  call    __security_check_cookie
0x1400239b7  add     rsp, 50h
0x1400239bb  pop     rbx
0x1400239bc  retn
```
