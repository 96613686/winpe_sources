# MdmLogCollector::CollectWifiLogs(void)

- ea: `0x18010f3c4`
- end: `0x18010f603`
- name: `?CollectWifiLogs@MdmLogCollector@@AEAAJXZ`
- size: `575`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18010ba4c`

## callees

- `0x180019080`
- `0x18001a130`
- `0x1800e68b0`
- `0x1800ed44c`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x18010f3c4`
- `0x18011153c`
- `0x180111c9c`
- `0x18011224c`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18010f432`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18010f432`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010f5a0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18010f5a0`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18010f4df`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18010f4df`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18010f44f`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18010f44f`

## string_xrefs

- `0x18010f4fb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f576`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f5bb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010f486`: `"%s\logman.exe" update WiFiSession -fd -ets`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MdmLogCollector::CollectWifiLogs(MdmLogCollector *this)
{
  HRESULT updated; // eax
  unsigned int LastError; // ebx
  __int64 v4; // rdx
  const WCHAR *v5; // rax
  HRESULT v6; // eax
  const char *v7; // r9
  int v9; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-D8h] BYREF
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v12[3]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[32]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  memset(v12, 0, sizeof(v12));
  ppszPath = 0;
  v9 = 0;
  v11 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v9, &v11);
  updated = SHGetKnownFolderPath(&FOLDERID_System, 0, 0, &ppszPath);
  LastError = updated;
  if ( updated < 0 )
  {
    v4 = 1871;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)updated,
      v9);
    goto LABEL_18;
  }
  if ( v9 == 16 || v9 == 10 )
  {
    updated = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                v12,
                L"\"%s\\tracelog.exe\" -capturestate -systemrundown -flush WifiSession",
                ppszPath);
    LastError = updated;
    if ( updated < 0 )
    {
      v4 = 1878;
      goto LABEL_14;
    }
    if ( !ExpandEnvironmentStringsW(L"%OSDataDrive%\\systemdata\\etw\\WiFi.etl*", pszPath, 0x104u) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x759,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                    v7);
      goto LABEL_18;
    }
LABEL_10:
    wprintf(L"Collecting Wifi Session information.  This may take up to two minutes...\n");
    updated = MdmLogCollector::UpdateWifiEtl(this, v12[0], pszPath);
    LastError = updated;
    if ( updated >= 0 )
    {
      LastError = 0;
      goto LABEL_18;
    }
    v4 = 1896;
    goto LABEL_14;
  }
  updated = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              v12,
              L"\"%s\\logman.exe\" update WiFiSession -fd -ets",
              ppszPath);
  LastError = updated;
  if ( updated < 0 )
  {
    v4 = 1888;
    goto LABEL_14;
  }
  std::wstring::wstring(v13, ppszPath);
  std::wstring::append(v13, L"\\logfiles\\wmi\\WiFi.etl");
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
  v6 = PathCchAppend(pszPath, 0x104u, v5);
  LastError = v6;
  if ( v6 >= 0 )
  {
    std::wstring::_Tidy_deallocate(v13);
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x764,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
    (const char *)(unsigned int)v6,
    v9);
  std::wstring::_Tidy_deallocate(v13);
LABEL_18:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v12);
  return LastError;
}

```

## disassembly

```asm
0x18010f3c4  mov     [rsp-8+arg_8], rbx
0x18010f3c9  mov     [rsp-8+arg_10], rdi
0x18010f3ce  push    rbp
0x18010f3cf  lea     rbp, [rsp-190h]
0x18010f3d7  sub     rsp, 290h
0x18010f3de  mov     rax, cs:__security_cookie
0x18010f3e5  xor     rax, rsp
0x18010f3e8  mov     [rbp+190h+var_10], rax
0x18010f3ef  mov     rdi, rcx
0x18010f3f2  mov     [rsp+290h+var_258], 0
0x18010f3fb  mov     [rsp+290h+var_250], 0
0x18010f404  mov     [rsp+290h+var_248], 0
0x18010f40d  mov     [rsp+290h+ppszPath], 0
0x18010f416  mov     [rsp+290h+var_270], 0; int
0x18010f41e  mov     [rsp+290h+var_260], 0
0x18010f426  lea     r8, [rsp+290h+var_260]
0x18010f42b  lea     rdx, [rsp+290h+var_270]
0x18010f430  xor     ecx, ecx
0x18010f432  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18010f439  nop     dword ptr [rax+rax+00h]
0x18010f43e  lea     r9, [rsp+290h+ppszPath]; ppszPath
0x18010f443  xor     r8d, r8d; hToken
0x18010f446  xor     edx, edx; dwFlags
0x18010f448  lea     rcx, FOLDERID_System; rfid
0x18010f44f  call    cs:__imp_SHGetKnownFolderPath
0x18010f456  nop     dword ptr [rax+rax+00h]
0x18010f45b  mov     ebx, eax
0x18010f45d  test    eax, eax
0x18010f45f  jns     short loc_18010F46B
0x18010f461  mov     edx, 74Fh
0x18010f466  jmp     loc_18010F576
0x18010f46b  cmp     [rsp+290h+var_270], 10h
0x18010f470  jz      loc_18010F555
0x18010f476  cmp     [rsp+290h+var_270], 0Ah
0x18010f47b  jz      loc_18010F555
0x18010f481  mov     r8, [rsp+290h+ppszPath]
0x18010f486  lea     rdx, aSLogmanExeUpda; "\"%s\\logman.exe\" update WiFiSession -"...
0x18010f48d  lea     rcx, [rsp+290h+var_258]
0x18010f492  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18010f497  mov     ebx, eax
0x18010f499  test    eax, eax
0x18010f49b  jns     short loc_18010F4A7
0x18010f49d  mov     edx, 760h
0x18010f4a2  jmp     loc_18010F576
0x18010f4a7  mov     rdx, [rsp+290h+ppszPath]
0x18010f4ac  lea     rcx, [rsp+290h+var_240]
0x18010f4b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010f4b6  nop
0x18010f4b7  lea     rdx, aLogfilesWmiWif; "\\logfiles\\wmi\\WiFi.etl"
0x18010f4be  lea     rcx, [rsp+290h+var_240]
0x18010f4c3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010f4c8  lea     rcx, [rsp+290h+var_240]
0x18010f4cd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010f4d2  mov     r8, rax; pszMore
0x18010f4d5  mov     edx, 104h; cchPath
0x18010f4da  lea     rcx, [rsp+290h+pszPath]; pszPath
0x18010f4df  call    cs:__imp_PathCchAppend
0x18010f4e6  nop     dword ptr [rax+rax+00h]
0x18010f4eb  mov     ebx, eax
0x18010f4ed  test    eax, eax
0x18010f4ef  jns     short loc_18010F51C
0x18010f4f1  mov     rcx, [rbp+198h]; this
0x18010f4f8  mov     r9d, eax; char *
0x18010f4fb  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f502  mov     edx, 764h; void *
0x18010f507  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f50c  nop
0x18010f50d  lea     rcx, [rsp+290h+var_240]
0x18010f512  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f517  jmp     loc_18010F5D2
0x18010f51c  lea     rcx, [rsp+290h+var_240]
0x18010f521  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010f526  lea     rcx, aCollectingWifi; "Collecting Wifi Session information.  T"...
0x18010f52d  call    wprintf
0x18010f532  lea     r8, [rsp+290h+pszPath]; unsigned __int16 *
0x18010f537  mov     rdx, [rsp+290h+var_258]; unsigned __int16 *
0x18010f53c  mov     rcx, rdi; this
0x18010f53f  call    ?UpdateWifiEtl@MdmLogCollector@@AEAAJPEAGPEBG@Z; MdmLogCollector::UpdateWifiEtl(ushort *,ushort const *)
0x18010f544  mov     ebx, eax
0x18010f546  test    eax, eax
0x18010f548  jns     loc_18010F5D0
0x18010f54e  mov     edx, 768h
0x18010f553  jmp     short loc_18010F576
0x18010f555  mov     r8, [rsp+290h+ppszPath]
0x18010f55a  lea     rdx, aSTracelogExeCa; "\"%s\\tracelog.exe\" -capturestate -sys"...
0x18010f561  lea     rcx, [rsp+290h+var_258]
0x18010f566  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18010f56b  mov     ebx, eax
0x18010f56d  test    eax, eax
0x18010f56f  jns     short loc_18010F58E
0x18010f571  mov     edx, 756h; void *
0x18010f576  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f57d  mov     r9d, eax; char *
0x18010f580  mov     rcx, [rbp+198h]; this
0x18010f587  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010f58c  jmp     short loc_18010F5D2
0x18010f58e  mov     r8d, 104h; nSize
0x18010f594  lea     rdx, [rsp+290h+pszPath]; lpDst
0x18010f599  lea     rcx, aOsdatadriveSys; "%OSDataDrive%\\systemdata\\etw\\WiFi.et"...
0x18010f5a0  call    cs:__imp_ExpandEnvironmentStringsW
0x18010f5a7  nop     dword ptr [rax+rax+00h]
0x18010f5ac  test    eax, eax
0x18010f5ae  jnz     loc_18010F526
0x18010f5b4  mov     rcx, [rbp+198h]; this
0x18010f5bb  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010f5c2  mov     edx, 759h; void *
0x18010f5c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18010f5cc  mov     ebx, eax
0x18010f5ce  jmp     short loc_18010F5D2
0x18010f5d0  xor     ebx, ebx
0x18010f5d2  lea     rcx, [rsp+290h+var_258]
0x18010f5d7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18010f5dc  mov     eax, ebx
0x18010f5de  mov     rcx, [rbp+190h+var_10]
0x18010f5e5  xor     rcx, rsp; StackCookie
0x18010f5e8  call    __security_check_cookie
0x18010f5ed  lea     r11, [rsp+290h+var_s0]
0x18010f5f5  mov     rbx, [r11+18h]
0x18010f5f9  mov     rdi, [r11+20h]
0x18010f5fd  mov     rsp, r11
0x18010f600  pop     rbp
0x18010f601  retn
```
