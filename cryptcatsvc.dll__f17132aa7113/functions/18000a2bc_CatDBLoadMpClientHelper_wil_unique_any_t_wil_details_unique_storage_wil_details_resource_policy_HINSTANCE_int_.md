# CatDBLoadMpClientHelper(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> &)

- ea: `0x18000a2bc`
- end: `0x18000a484`
- name: `?CatDBLoadMpClientHelper@@YAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `456`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180009b30`

## callees

- `0x18000a2bc`
- `0x18000a57c`
- `0x18000a59c`
- `0x18000a790`
- `0x18000be40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000a3e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000a3e0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a34d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a390`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a34d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000a390`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000a3f9`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000a3f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a39f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a43a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a39f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a43a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a330`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a330`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000a366`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x18000a366`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000a3b7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000a41e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000a3b7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000a41e`

## string_xrefs

- `0x18000a308`: `InstallLocation`
- `0x18000a33f`: `MpClient.dll`
- `0x18000a381`: `\Windows Defender\MpClient.dll`

## pseudocode

```c
__int64 __fastcall CatDBLoadMpClientHelper(__int64 a1)
{
  unsigned int v2; // edx
  unsigned __int16 *v3; // rcx
  unsigned int v4; // r8d
  unsigned int v5; // ebx
  HMODULE LibraryW; // rax
  unsigned int v7; // eax
  unsigned int v8; // edx
  unsigned __int16 *v9; // rcx
  HMODULE v10; // rax
  int pvData; // [rsp+28h] [rbp-250h]
  DWORD pcbData[4]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-228h] BYREF

  pcbData[0] = 520;
  if ( !byte_1800312D9 )
  {
    SetLastError(0x32u);
    v4 = 400;
    goto LABEL_14;
  }
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows Defender",
         L"InstallLocation",
         2u,
         0,
         Buffer,
         pcbData)
    || (unsigned int)_o_wcscat_s(Buffer, 260, L"MpClient.dll") )
  {
    if ( !GetEnvironmentVariableW(L"ProgramFiles", Buffer, 0x104u) )
    {
      byte_1800312D9 = 0;
      v4 = 364;
LABEL_14:
      ErrLog_LogError(v3, v2, v4, 0, 0, pvData);
      return _CatDBGetNonzeroLastError();
    }
    if ( (unsigned int)_o_wcscat_s(Buffer, 260, L"\\Windows Defender\\MpClient.dll") )
    {
      SetLastError(0x32u);
      v4 = 374;
      goto LABEL_14;
    }
  }
  v5 = 0;
  LibraryW = LoadLibraryW(Buffer);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    a1,
    LibraryW);
  if ( !hLibModule || (unsigned int)_o__wcsnicmp(qword_180032800, Buffer, 260) )
  {
    v7 = _o_wcscpy_s(qword_180032800, 260, Buffer);
    if ( v7 )
      ErrLog_LogError(v9, v8, 0x187u, v7, 1, pvData);
    v10 = LoadLibraryW(Buffer);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      &hLibModule,
      v10);
  }
  return v5;
}

```

## disassembly

```asm
0x18000a2bc  mov     [rsp+arg_8], rbx
0x18000a2c1  mov     [rsp+arg_10], rbp
0x18000a2c6  push    rdi
0x18000a2c7  sub     rsp, 270h
0x18000a2ce  mov     rax, cs:__security_cookie
0x18000a2d5  xor     rax, rsp
0x18000a2d8  mov     [rsp+278h+var_18], rax
0x18000a2e0  cmp     cs:byte_1800312D9, 0
0x18000a2e7  mov     rdi, rcx
0x18000a2ea  mov     [rsp+278h+var_238], 208h
0x18000a2f2  jz      loc_18000A435
0x18000a2f8  lea     rax, [rsp+278h+var_238]
0x18000a2fd  mov     r9d, 2; dwFlags
0x18000a303  mov     [rsp+278h+pcbData], rax; pcbData
0x18000a308  lea     r8, Value; "InstallLocation"
0x18000a30f  lea     rax, [rsp+278h+Buffer]
0x18000a314  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000a31b  mov     [rsp+278h+pvData], rax; int
0x18000a320  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows Defender"
0x18000a327  mov     [rsp+278h+pdwType], 0; pdwType
0x18000a330  call    cs:__imp_RegGetValueW
0x18000a336  mov     ebp, 104h
0x18000a33b  test    eax, eax
0x18000a33d  jnz     short loc_18000A357
0x18000a33f  lea     r8, aMpclientDll; "MpClient.dll"
0x18000a346  mov     edx, ebp
0x18000a348  lea     rcx, [rsp+278h+Buffer]
0x18000a34d  call    cs:__imp__o_wcscat_s
0x18000a353  test    eax, eax
0x18000a355  jz      short loc_18000A3B0
0x18000a357  mov     r8d, ebp; nSize
0x18000a35a  lea     rdx, [rsp+278h+Buffer]; lpBuffer
0x18000a35f  lea     rcx, Name; "ProgramFiles"
0x18000a366  call    cs:__imp_GetEnvironmentVariableW
0x18000a36c  test    eax, eax
0x18000a36e  jnz     short loc_18000A381
0x18000a370  mov     cs:byte_1800312D9, al
0x18000a376  mov     r8d, 16Ch
0x18000a37c  jmp     loc_18000A446
0x18000a381  lea     r8, aWindowsDefende; "\\Windows Defender\\MpClient.dll"
0x18000a388  mov     rdx, rbp
0x18000a38b  lea     rcx, [rsp+278h+Buffer]
0x18000a390  call    cs:__imp__o_wcscat_s
0x18000a396  test    eax, eax
0x18000a398  jz      short loc_18000A3B0
0x18000a39a  mov     ecx, 32h ; '2'; dwErrCode
0x18000a39f  call    cs:__imp_SetLastError
0x18000a3a5  mov     r8d, 176h
0x18000a3ab  jmp     loc_18000A446
0x18000a3b0  lea     rcx, [rsp+278h+Buffer]; lpLibFileName
0x18000a3b5  xor     ebx, ebx
0x18000a3b7  call    cs:__imp_LoadLibraryW
0x18000a3bd  mov     rdx, rax
0x18000a3c0  mov     rcx, rdi
0x18000a3c3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18000a3c8  cmp     cs:hLibModule, rbx
0x18000a3cf  jz      short loc_18000A3EA
0x18000a3d1  mov     r8, rbp
0x18000a3d4  lea     rdx, [rsp+278h+Buffer]
0x18000a3d9  lea     rcx, qword_180032800
0x18000a3e0  call    cs:__imp__o__wcsnicmp
0x18000a3e6  test    eax, eax
0x18000a3e8  jz      short loc_18000A45D
0x18000a3ea  lea     r8, [rsp+278h+Buffer]
0x18000a3ef  mov     rdx, rbp
0x18000a3f2  lea     rcx, qword_180032800
0x18000a3f9  call    cs:__imp__o_wcscpy_s
0x18000a3ff  test    eax, eax
0x18000a401  jz      short loc_18000A419
0x18000a403  mov     r9d, eax; unsigned int
0x18000a406  mov     dword ptr [rsp+278h+pdwType], 1; int
0x18000a40e  mov     r8d, 187h; unsigned int
0x18000a414  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18000a419  lea     rcx, [rsp+278h+Buffer]; lpLibFileName
0x18000a41e  call    cs:__imp_LoadLibraryW
0x18000a424  mov     rdx, rax
0x18000a427  lea     rcx, hLibModule
0x18000a42e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18000a433  jmp     short loc_18000A45D
0x18000a435  mov     ecx, 32h ; '2'; dwErrCode
0x18000a43a  call    cs:__imp_SetLastError
0x18000a440  mov     r8d, 190h; unsigned int
0x18000a446  xor     r9d, r9d; unsigned int
0x18000a449  mov     dword ptr [rsp+278h+pdwType], 0; int
0x18000a451  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18000a456  call    ?_CatDBGetNonzeroLastError@@YAKXZ; _CatDBGetNonzeroLastError(void)
0x18000a45b  mov     ebx, eax
0x18000a45d  mov     eax, ebx
0x18000a45f  mov     rcx, [rsp+278h+var_18]
0x18000a467  xor     rcx, rsp; StackCookie
0x18000a46a  call    __security_check_cookie
0x18000a46f  lea     r11, [rsp+278h+var_8]
0x18000a477  mov     rbx, [r11+18h]
0x18000a47b  mov     rbp, [r11+20h]
0x18000a47f  mov     rsp, r11
0x18000a482  pop     rdi
0x18000a483  retn
```
