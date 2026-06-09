# LogAdapter::TraceAtLevelHr<long,wchar_t const *>(LogAdapter::LogLevel,long,char const * const,wchar_t const * const &)

- ea: `0x140016ac4`
- end: `0x140016b3d`
- name: `??$TraceAtLevelHr@JPEB_W@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBQEB_W@Z`
- size: `121`
- prototype: `__int64 __fastcall(__int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140016bc8`

## callees

- `0x140002360`
- `0x140006984`
- `0x140006c50`
- `0x140016ac4`

## string_xrefs

- `0x140016aee`: `Failed NTFS compressing file {}`

## pseudocode

```c
__int64 __fastcall LogAdapter::TraceAtLevelHr<long,wchar_t const *>(__int64 a1, int a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rdx
  __int64 result; // rax
  int *v6; // [rsp+30h] [rbp-28h] BYREF
  int v7; // [rsp+38h] [rbp-20h] BYREF

  v7 = a2;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<wchar_t const *>(
      (__int64)LogAdapter::g_Logger,
      0,
      1,
      (__int64)"Failed NTFS compressing file {}",
      a4);
    v6 = &v7;
    return LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
             (__int64)LogAdapter::g_Logger,
             v4,
             1,
             (__int64)": {0}",
             (__int64)&v6);
  }
  return result;
}

```

## disassembly

```asm
0x140016ac4  sub     rsp, 58h
0x140016ac8  mov     rax, cs:__security_cookie
0x140016acf  xor     rax, rsp
0x140016ad2  mov     [rsp+58h+var_18], rax
0x140016ad7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016ade  mov     [rsp+58h+var_20], edx
0x140016ae2  test    rcx, rcx
0x140016ae5  jz      short loc_140016B2B
0x140016ae7  xor     edx, edx
0x140016ae9  mov     [rsp+58h+var_38], r9
0x140016aee  lea     r9, aFailedNtfsComp; "Failed NTFS compressing file {}"
0x140016af5  lea     r8d, [rdx+1]
0x140016af9  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x140016afe  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140016b05  lea     rax, [rsp+58h+var_20]
0x140016b0a  mov     [rsp+58h+var_28], rax
0x140016b0f  lea     r9, a0; ": {0}"
0x140016b16  lea     rax, [rsp+58h+var_28]
0x140016b1b  mov     r8d, 1
0x140016b21  mov     [rsp+58h+var_38], rax
0x140016b26  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140016b2b  mov     rcx, [rsp+58h+var_18]
0x140016b30  xor     rcx, rsp; StackCookie
0x140016b33  call    __security_check_cookie
0x140016b38  add     rsp, 58h
0x140016b3c  retn
```
