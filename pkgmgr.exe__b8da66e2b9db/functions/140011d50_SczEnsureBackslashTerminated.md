# SczEnsureBackslashTerminated

- ea: `0x140011d50`
- end: `0x140011e83`
- name: `SczEnsureBackslashTerminated`
- size: `307`
- prototype: `__int64 __fastcall(const void **, __int64, __int64, size_t)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x14000aca8`
- `0x14000b454`
- `0x140013288`
- `0x140016328`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x140011100`
- `0x140011d50`

## string_xrefs

- `0x140011d8a`: `No path result specified`

## pseudocode

```c
__int64 __fastcall SczEnsureBackslashTerminated(const void **a1, __int64 a2, __int64 a3, size_t a4)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  _WORD *v8; // rdx
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rdx
  int v12[2]; // [rsp+30h] [rbp-28h] BYREF
  int v13; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a1 )
  {
    v4 = -2147467261;
    v13 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No path result specified");
      *(_QWORD *)v12 = &v13;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v5,
        3,
        (__int64)": {}",
        (__int64)v12);
    }
    v6 = 604;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (int)"onecore\\base\\cbs\\util\\cbsstr.cpp",
      (const char *)v4);
    return v4;
  }
  v8 = *a1;
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  if ( v8[v9 - 1] != 92 )
  {
    v10 = SczAllocConcatSz(a1, L"\\", a3, a4);
    v4 = v10;
    if ( v10 < 0 )
    {
      v13 = v10;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to concat backslash onto string.");
        *(_QWORD *)v12 = &v13;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v11,
          3,
          (__int64)": {}",
          (__int64)v12);
      }
      v6 = 610;
      goto LABEL_5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140011d50  mov     [rsp+arg_8], rbx
0x140011d55  push    rdi
0x140011d56  sub     rsp, 50h
0x140011d5a  mov     rax, cs:__security_cookie
0x140011d61  xor     rax, rsp
0x140011d64  mov     [rsp+58h+var_18], rax
0x140011d69  xor     edi, edi
0x140011d6b  test    rcx, rcx
0x140011d6e  jnz     short loc_140011DE5
0x140011d70  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011d77  mov     ebx, 80004003h
0x140011d7c  mov     [rsp+58h+var_20], ebx
0x140011d80  test    rcx, rcx
0x140011d83  jz      short loc_140011DC5
0x140011d85  mov     edi, 3
0x140011d8a  lea     r9, aNoPathResultSp; "No path result specified"
0x140011d91  mov     r8d, edi
0x140011d94  xor     edx, edx
0x140011d96  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140011d9b  lea     rcx, [rsp+58h+var_28]
0x140011da0  mov     r8d, edi
0x140011da3  mov     qword ptr [rsp+58h+var_38], rcx; int
0x140011da8  lea     rax, [rsp+58h+var_20]
0x140011dad  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011db4  lea     r9, asc_14002D4FC; ": {}"
0x140011dbb  mov     qword ptr [rsp+58h+var_28], rax
0x140011dc0  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011dc5  mov     edx, 25Ch; void *
0x140011dca  mov     rcx, [rsp+58h]; this
0x140011dcf  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\util\\cbsstr.cpp"
0x140011dd6  mov     r9d, ebx; char *
0x140011dd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140011dde  mov     eax, ebx
0x140011de0  jmp     loc_140011E6B
0x140011de5  mov     rdx, [rcx]
0x140011de8  or      rax, 0FFFFFFFFFFFFFFFFh
0x140011dec  inc     rax
0x140011def  cmp     [rdx+rax*2], di
0x140011df3  jnz     short loc_140011DEC
0x140011df5  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x140011dfb  jz      short loc_140011E69
0x140011dfd  lea     rdx, asc_14002D1C4; "\\"
0x140011e04  call    SczAllocConcatSz
0x140011e09  mov     ebx, eax
0x140011e0b  test    eax, eax
0x140011e0d  jns     short loc_140011E69
0x140011e0f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011e16  mov     [rsp+58h+var_20], eax
0x140011e1a  test    rcx, rcx
0x140011e1d  jz      short loc_140011E5F
0x140011e1f  mov     edi, 3
0x140011e24  lea     r9, aFailedToConcat_1; "Failed to concat backslash onto string."
0x140011e2b  mov     r8d, edi
0x140011e2e  xor     edx, edx
0x140011e30  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140011e35  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140011e3c  lea     rax, [rsp+58h+var_20]
0x140011e41  mov     qword ptr [rsp+58h+var_28], rax
0x140011e46  lea     r9, asc_14002D4FC; ": {}"
0x140011e4d  lea     rax, [rsp+58h+var_28]
0x140011e52  mov     r8d, edi
0x140011e55  mov     qword ptr [rsp+58h+var_38], rax
0x140011e5a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140011e5f  mov     edx, 262h
0x140011e64  jmp     loc_140011DCA
0x140011e69  xor     eax, eax
0x140011e6b  mov     rcx, [rsp+58h+var_18]
0x140011e70  xor     rcx, rsp; StackCookie
0x140011e73  call    __security_check_cookie
0x140011e78  mov     rbx, [rsp+58h+arg_8]
0x140011e7d  add     rsp, 50h
0x140011e81  pop     rdi
0x140011e82  retn
```
