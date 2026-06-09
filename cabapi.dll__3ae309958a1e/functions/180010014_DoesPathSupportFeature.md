# DoesPathSupportFeature

- ea: `0x180010014`
- end: `0x18001011e`
- name: `DoesPathSupportFeature`
- size: `266`
- prototype: `int __fastcall(void *, __int64, __int64, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800109d4`

## callees

- `0x180001540`
- `0x18000c030`
- `0x18000fa80`
- `0x18000fc8c`
- `0x180010014`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010073`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010073`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x180010065`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationByHandleW` at `0x180010065`

## string_xrefs

- `0x1800100e0`: `onecore\base\cbs\mobile\iucommon\iuutils.cpp`
- `0x18001008a`: `Failed to GetVolumeInformation for path {0}`

## pseudocode

```c
int __fastcall DoesPathSupportFeature(void *a1, __int64 a2, __int64 a3, bool *a4)
{
  __int64 v6; // rdx
  signed int LastError; // ebx
  __int64 v8; // rdx
  unsigned int v9; // eax
  unsigned int *v11; // [rsp+20h] [rbp-48h]
  unsigned int v12; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v13[2]; // [rsp+48h] [rbp-20h] BYREF
  DWORD v14; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v14 = 0;
  if ( GetVolumeInformationByHandleW(a1, 0, 0, 0, 0, &v14, 0, 0) )
  {
    *a4 = (v14 & 8) != 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogPartial<wil::basic_zstring_view<wchar_t>>(
        LogAdapter::g_Logger,
        v6,
        "Failed to GetVolumeInformation for path {0}",
        a2);
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      else
        v9 = LastError;
      v12 = v9;
      *(_QWORD *)v13 = &v12;
      v11 = v13;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        LogAdapter::g_Logger,
        v8,
        3,
        ": {0}");
    }
    if ( LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xED7,
               (unsigned int)"onecore\\base\\cbs\\mobile\\iucommon\\iuutils.cpp",
               (const char *)(unsigned int)LastError,
               (unsigned int)v11);
  }
  return 0;
}

```

## disassembly

```asm
0x180010014  mov     r11, rsp
0x180010017  mov     [r11+18h], rbx
0x18001001b  push    rdi
0x18001001c  sub     rsp, 60h
0x180010020  mov     rax, cs:__security_cookie
0x180010027  xor     rax, rsp
0x18001002a  mov     [rsp+68h+var_10], rax
0x18001002f  mov     [rsp+68h+nFileSystemNameSize], 0; nFileSystemNameSize
0x180010037  lea     rax, [r11-18h]
0x18001003b  mov     qword ptr [r11-38h], 0
0x180010043  mov     rbx, r9
0x180010046  mov     rdi, rdx
0x180010049  mov     [r11-40h], rax
0x18001004d  xor     r9d, r9d; lpVolumeSerialNumber
0x180010050  mov     qword ptr [r11-48h], 0
0x180010058  xor     r8d, r8d; nVolumeNameSize
0x18001005b  mov     [rsp+68h+var_18], 0
0x180010063  xor     edx, edx; lpVolumeNameBuffer
0x180010065  call    cs:__imp_GetVolumeInformationByHandleW
0x18001006b  test    eax, eax
0x18001006d  jnz     loc_1800100F6
0x180010073  call    cs:__imp_GetLastError
0x180010079  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180010080  mov     ebx, eax
0x180010082  test    rcx, rcx
0x180010085  jz      short loc_1800100D7
0x180010087  mov     r9, rdi
0x18001008a  lea     r8, aFailedToGetvol; "Failed to GetVolumeInformation for path"...
0x180010091  call    ??$LogPartial@V?$basic_zstring_view@_W@wil@@@Logger@LogAdapter@@QEAAJW4LogLevel@1@QEBDAEBV?$basic_zstring_view@_W@wil@@@Z; LogAdapter::Logger::LogPartial<wil::basic_zstring_view<wchar_t>>(LogAdapter::LogLevel,char const * const,wil::basic_zstring_view<wchar_t> const &)
0x180010096  test    ebx, ebx
0x180010098  jg      short loc_18001009E
0x18001009a  mov     eax, ebx
0x18001009c  jmp     short loc_1800100A6
0x18001009e  movzx   eax, bx
0x1800100a1  or      eax, 80070000h
0x1800100a6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800100ad  lea     r9, a0; ": {0}"
0x1800100b4  mov     [rsp+68h+var_28], eax
0x1800100b8  mov     r8d, 3
0x1800100be  lea     rax, [rsp+68h+var_28]
0x1800100c3  mov     qword ptr [rsp+68h+var_20], rax
0x1800100c8  lea     rax, [rsp+68h+var_20]
0x1800100cd  mov     qword ptr [rsp+68h+var_48], rax; unsigned int
0x1800100d2  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800100d7  test    ebx, ebx
0x1800100d9  jz      short loc_180010101
0x1800100db  mov     rcx, [rsp+68h]; this
0x1800100e0  lea     r8, aOnecoreBaseCbs_1; "onecore\\base\\cbs\\mobile\\iucommon\\i"...
0x1800100e7  mov     r9d, ebx; char *
0x1800100ea  mov     edx, 0ED7h; void *
0x1800100ef  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800100f4  jmp     short loc_180010103
0x1800100f6  mov     eax, [rsp+68h+var_18]
0x1800100fa  shr     eax, 3
0x1800100fd  and     al, 1
0x1800100ff  mov     [rbx], al
0x180010101  xor     eax, eax
0x180010103  mov     rcx, [rsp+68h+var_10]
0x180010108  xor     rcx, rsp; StackCookie
0x18001010b  call    __security_check_cookie
0x180010110  mov     rbx, [rsp+68h+arg_10]
0x180010118  add     rsp, 60h
0x18001011c  pop     rdi
0x18001011d  retn
```
