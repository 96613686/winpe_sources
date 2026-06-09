# CbsRegSetDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong)

- ea: `0x140018394`
- end: `0x140018559`
- name: `?CbsRegSetDWORDValue@@YAJPEAUHKEY__@@PEB_WK1K@Z`
- size: `453`
- prototype: `__int64(HKEY, const wchar_t *, __int64, const wchar_t *, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140023880`

## callees

- `0x140002360`
- `0x140006984`
- `0x140006c50`
- `0x14000952c`
- `0x140012a2c`
- `0x140017af0`
- `0x140018394`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400184c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1400184c9`

## string_xrefs

- `0x140018439`: `Failed to open key: {}`
- `0x1400184f6`: `Failed to set registry value: {}`
- `0x1400183c2`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SideBySide`

## pseudocode

```c
__int64 CbsRegSetDWORDValue(HKEY a1, const wchar_t *a2, __int64 a3, const wchar_t *a4, ...)
{
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  unsigned int v6; // ebx
  __int64 v8; // rdx
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int lpData; // [rsp+20h] [rbp-50h]
  unsigned int v14; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v15[2]; // [rsp+38h] [rbp-38h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v17; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  va_list va; // [rsp+A0h] [rbp+30h] BYREF

  va_start(va, a4);
  hKey = 0;
  lpValueName[0] = L"MaintenanceFlags";
  v17 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide";
  v4 = CbsRegOpenKeyExW(a1, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SideBySide", a3, 2u, &hKey);
  v5 = v4;
  if ( v4 == 2 || v4 == 3 )
  {
    v6 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    if ( v4 )
    {
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to open key: {}",
          (__int64)&v17);
        if ( v5 > 0 )
          v9 = (unsigned __int16)v5 | 0x80070000;
        else
          v9 = v5;
        v14 = v9;
        *(_QWORD *)v15 = &v14;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v8,
          3,
          (__int64)": {0}",
          (__int64)v15);
      }
      v10 = 669;
    }
    else
    {
      v5 = RegSetValueExW(hKey, lpValueName[0], 0, 4u, (const BYTE *)va, 4u);
      if ( v5 == 2 )
      {
        v6 = -2147024894;
        goto LABEL_4;
      }
      if ( !v5 )
      {
        v6 = 0;
        goto LABEL_4;
      }
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Failed to set registry value: {}",
          (__int64)lpValueName);
        if ( v5 > 0 )
          v12 = (unsigned __int16)v5 | 0x80070000;
        else
          v12 = v5;
        v14 = v12;
        *(_QWORD *)v15 = &v14;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          v11,
          3,
          (__int64)": {0}",
          (__int64)v15);
      }
      v10 = 686;
    }
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v10,
           (unsigned int)"onecore\\base\\cbs\\util\\cbsreg.cpp",
           (const char *)(unsigned int)v5,
           lpData);
  }
LABEL_4:
  Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(&hKey);
  return v6;
}

```

## disassembly

```asm
0x140018394  mov     [rsp-8+arg_0], rbx
0x140018399  push    rbp
0x14001839a  mov     rbp, rsp
0x14001839d  sub     rsp, 70h
0x1400183a1  mov     rax, cs:__security_cookie
0x1400183a8  xor     rax, rsp
0x1400183ab  mov     [rbp+var_8], rax
0x1400183af  lea     rax, aMaintenancefla; "MaintenanceFlags"
0x1400183b6  mov     [rbp+hKey], 0
0x1400183be  mov     [rbp+lpValueName], rax
0x1400183c2  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400183c9  lea     rax, [rbp+hKey]
0x1400183cd  mov     [rbp+var_20], rdx
0x1400183d1  mov     r9d, 2; unsigned int
0x1400183d7  mov     [rsp+70h+lpData], rax; HKEY *
0x1400183dc  call    ?CbsRegOpenKeyExW@@YAKPEAUHKEY__@@PEB_WKKPEAPEAU1@@Z; CbsRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,ulong,HKEY__ * *)
0x1400183e1  mov     ebx, eax
0x1400183e3  cmp     eax, 2
0x1400183e6  jz      short loc_1400183F1
0x1400183e8  cmp     eax, 3
0x1400183eb  jnz     short loc_14001841F
0x1400183ed  test    eax, eax
0x1400183ef  jle     short loc_1400183FA
0x1400183f1  movzx   ebx, bx
0x1400183f4  or      ebx, 80070000h
0x1400183fa  lea     rcx, [rbp+hKey]
0x1400183fe  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x140018403  mov     eax, ebx
0x140018405  mov     rcx, [rbp+var_8]
0x140018409  xor     rcx, rsp; StackCookie
0x14001840c  call    __security_check_cookie
0x140018411  mov     rbx, [rsp+70h+arg_0]
0x140018419  add     rsp, 70h
0x14001841d  pop     rbp
0x14001841e  retn
0x14001841f  test    ebx, ebx
0x140018421  jz      loc_1400184AA
0x140018427  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x14001842e  test    rcx, rcx
0x140018431  jz      short loc_14001848B
0x140018433  xor     edx, edx
0x140018435  lea     rax, [rbp+var_20]
0x140018439  lea     r9, aFailedToOpenKe; "Failed to open key: {}"
0x140018440  mov     [rsp+70h+lpData], rax
0x140018445  lea     r8d, [rdx+3]
0x140018449  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001844e  test    ebx, ebx
0x140018450  jg      short loc_140018456
0x140018452  mov     eax, ebx
0x140018454  jmp     short loc_14001845E
0x140018456  movzx   eax, bx
0x140018459  or      eax, 80070000h
0x14001845e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018465  lea     r9, a0; ": {0}"
0x14001846c  mov     [rbp+var_40], eax
0x14001846f  mov     r8d, 3
0x140018475  lea     rax, [rbp+var_40]
0x140018479  mov     qword ptr [rbp+var_38], rax
0x14001847d  lea     rax, [rbp+var_38]
0x140018481  mov     [rsp+70h+lpData], rax; unsigned int
0x140018486  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x14001848b  mov     edx, 29Dh; void *
0x140018490  mov     rcx, [rbp+8]; this
0x140018494  lea     r8, aOnecoreBaseCbs_3; "onecore\\base\\cbs\\util\\cbsreg.cpp"
0x14001849b  mov     r9d, ebx; char *
0x14001849e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400184a3  mov     ebx, eax
0x1400184a5  jmp     loc_1400183FA
0x1400184aa  mov     rdx, [rbp+lpValueName]; lpValueName
0x1400184ae  lea     rax, [rbp+Data]
0x1400184b2  mov     rcx, [rbp+hKey]; hKey
0x1400184b6  mov     r9d, 4; dwType
0x1400184bc  mov     [rsp+70h+cbData], r9d; cbData
0x1400184c1  xor     r8d, r8d; Reserved
0x1400184c4  mov     [rsp+70h+lpData], rax; lpData
0x1400184c9  call    cs:__imp_RegSetValueExW
0x1400184cf  mov     ebx, eax
0x1400184d1  cmp     eax, 2
0x1400184d4  jnz     short loc_1400184E0
0x1400184d6  mov     ebx, 80070002h
0x1400184db  jmp     loc_1400183FA
0x1400184e0  test    ebx, ebx
0x1400184e2  jz      short loc_140018552
0x1400184e4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400184eb  test    rcx, rcx
0x1400184ee  jz      short loc_140018548
0x1400184f0  xor     edx, edx
0x1400184f2  lea     rax, [rbp+lpValueName]
0x1400184f6  lea     r9, aFailedToSetReg; "Failed to set registry value: {}"
0x1400184fd  mov     [rsp+70h+lpData], rax
0x140018502  lea     r8d, [rdx+3]
0x140018506  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x14001850b  test    ebx, ebx
0x14001850d  jg      short loc_140018513
0x14001850f  mov     eax, ebx
0x140018511  jmp     short loc_14001851B
0x140018513  movzx   eax, bx
0x140018516  or      eax, 80070000h
0x14001851b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140018522  lea     r9, a0; ": {0}"
0x140018529  mov     [rbp+var_40], eax
0x14001852c  mov     r8d, 3
0x140018532  lea     rax, [rbp+var_40]
0x140018536  mov     qword ptr [rbp+var_38], rax
0x14001853a  lea     rax, [rbp+var_38]
0x14001853e  mov     [rsp+70h+lpData], rax
0x140018543  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140018548  mov     edx, 2AEh
0x14001854d  jmp     loc_140018490
0x140018552  xor     ebx, ebx
0x140018554  jmp     loc_1400183FA
```
