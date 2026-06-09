# Windows::Compat::Inventory::InstallMonApi::InitializeApis(void)

- ea: `0x1800c6eac`
- end: `0x1800c700a`
- name: `?InitializeApis@InstallMonApi@Inventory@Compat@Windows@@QEAAJXZ`
- size: `350`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InstallMonApi *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800c6bd0`
- `0x1800c6d60`

## callees

- `0x180010b74`
- `0x1800152d0`
- `0x1800c6eac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6f59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6f6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6f81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6f95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6fa9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6fbd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6f59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6f6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6f81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6f95`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6fa9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c6fbd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c6f1c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c6f1c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c6f38`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c6f38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c6f40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c6f40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6f2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6f2d`

## string_xrefs

- `0x1800c6f15`: `installmon.dll`
- `0x1800c6ed7`: `Install Monitoring - Feature_InstallTracingV2 is not enabled.`
- `0x1800c6ee4`: `Windows::Compat::Inventory::InstallMonApi::InitializeApis`
- `0x1800c6f8b`: `StopInstallMonitoring`
- `0x1800c6f9f`: `FreeInstallMonitoringCallback`
- `0x1800c6f77`: `StartInstallMonitoring`
- `0x1800c6fb3`: `UpdateInstallerInventoryCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::InstallMonApi::InitializeApis(
        Windows::Compat::Inventory::InstallMonApi *this)
{
  unsigned int v3; // esi
  HMODULE Library; // rbp
  HMODULE v5; // r14
  DWORD LastError; // ebx

  if ( *((_BYTE *)this + 56) )
    return 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl'::`2'::impl) )
  {
    if ( *(_QWORD *)this )
      return 0;
    v3 = -2147467263;
    Library = LoadLibraryExW(L"installmon.dll", 0, 0x800u);
    v5 = *(HMODULE *)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      FreeLibrary(v5);
      SetLastError(LastError);
    }
    *(_QWORD *)this = Library;
    if ( Library )
    {
      *((_QWORD *)this + 1) = GetProcAddress(Library, "IsEnabled");
      *((_QWORD *)this + 2) = GetProcAddress(*(HMODULE *)this, "IsTestModeEnabled");
      *((_QWORD *)this + 3) = GetProcAddress(*(HMODULE *)this, "StartInstallMonitoring");
      *((_QWORD *)this + 4) = GetProcAddress(*(HMODULE *)this, "StopInstallMonitoring");
      *((_QWORD *)this + 5) = GetProcAddress(*(HMODULE *)this, "FreeInstallMonitoringCallback");
      *((_QWORD *)this + 6) = GetProcAddress(*(HMODULE *)this, "UpdateInstallerInventoryCache");
      *((_BYTE *)this + 56) = 1;
    }
    if ( *((_BYTE *)this + 56)
      && *((_QWORD *)this + 3)
      && *((_QWORD *)this + 4)
      && *((_QWORD *)this + 5)
      && *((_QWORD *)this + 6)
      && *((_QWORD *)this + 1)
      && *((_QWORD *)this + 2) )
    {
      return 0;
    }
    return v3;
  }
  else
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::InstallMonApi::InitializeApis",
      53,
      "Install Monitoring - Feature_InstallTracingV2 is not enabled.");
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800c6eac  push    rbx
0x1800c6eae  push    rbp
0x1800c6eaf  push    rsi
0x1800c6eb0  push    rdi
0x1800c6eb1  push    r14
0x1800c6eb3  sub     rsp, 20h
0x1800c6eb7  mov     rdi, rcx
0x1800c6eba  cmp     byte ptr [rcx+38h], 0
0x1800c6ebe  jz      short loc_1800C6EC7
0x1800c6ec0  xor     eax, eax
0x1800c6ec2  jmp     loc_1800C6FFF
0x1800c6ec7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallTracingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2> `wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl(void)'::`2'::impl
0x1800c6ece  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(void)
0x1800c6ed3  test    al, al
0x1800c6ed5  jnz     short loc_1800C6EFE
0x1800c6ed7  lea     r9, aInstallMonitor; "Install Monitoring - Feature_InstallTra"...
0x1800c6ede  mov     r8d, 35h ; '5'
0x1800c6ee4  lea     rdx, aWindowsCompatI_51; "Windows::Compat::Inventory::InstallMonA"...
0x1800c6eeb  lea     ecx, [r8-32h]
0x1800c6eef  call    AslLogCallPrintf
0x1800c6ef4  mov     eax, 80004001h
0x1800c6ef9  jmp     loc_1800C6FFF
0x1800c6efe  cmp     qword ptr [rdi], 0
0x1800c6f02  jnz     loc_1800C6FFB
0x1800c6f08  mov     esi, 80004001h
0x1800c6f0d  xor     edx, edx; hFile
0x1800c6f0f  mov     r8d, 800h; dwFlags
0x1800c6f15  lea     rcx, aInstallmonDll; "installmon.dll"
0x1800c6f1c  call    cs:__imp_LoadLibraryExW
0x1800c6f22  mov     rbp, rax
0x1800c6f25  mov     r14, [rdi]
0x1800c6f28  test    r14, r14
0x1800c6f2b  jz      short loc_1800C6F47
0x1800c6f2d  call    cs:__imp_GetLastError
0x1800c6f33  mov     ebx, eax
0x1800c6f35  mov     rcx, r14; hLibModule
0x1800c6f38  call    cs:__imp_FreeLibrary
0x1800c6f3e  mov     ecx, ebx; dwErrCode
0x1800c6f40  call    cs:__imp_SetLastError
0x1800c6f46  nop
0x1800c6f47  mov     [rdi], rbp
0x1800c6f4a  test    rbp, rbp
0x1800c6f4d  jz      short loc_1800C6FCB
0x1800c6f4f  lea     rdx, aIsenabled; "IsEnabled"
0x1800c6f56  mov     rcx, rbp; hModule
0x1800c6f59  call    cs:__imp_GetProcAddress
0x1800c6f5f  mov     [rdi+8], rax
0x1800c6f63  lea     rdx, aIstestmodeenab; "IsTestModeEnabled"
0x1800c6f6a  mov     rcx, [rdi]; hModule
0x1800c6f6d  call    cs:__imp_GetProcAddress
0x1800c6f73  mov     [rdi+10h], rax
0x1800c6f77  lea     rdx, aStartinstallmo; "StartInstallMonitoring"
0x1800c6f7e  mov     rcx, [rdi]; hModule
0x1800c6f81  call    cs:__imp_GetProcAddress
0x1800c6f87  mov     [rdi+18h], rax
0x1800c6f8b  lea     rdx, aStopinstallmon; "StopInstallMonitoring"
0x1800c6f92  mov     rcx, [rdi]; hModule
0x1800c6f95  call    cs:__imp_GetProcAddress
0x1800c6f9b  mov     [rdi+20h], rax
0x1800c6f9f  lea     rdx, aFreeinstallmon_0; "FreeInstallMonitoringCallback"
0x1800c6fa6  mov     rcx, [rdi]; hModule
0x1800c6fa9  call    cs:__imp_GetProcAddress
0x1800c6faf  mov     [rdi+28h], rax
0x1800c6fb3  lea     rdx, aUpdateinstalle; "UpdateInstallerInventoryCache"
0x1800c6fba  mov     rcx, [rdi]; hModule
0x1800c6fbd  call    cs:__imp_GetProcAddress
0x1800c6fc3  mov     [rdi+30h], rax
0x1800c6fc7  mov     byte ptr [rdi+38h], 1
0x1800c6fcb  cmp     byte ptr [rdi+38h], 0
0x1800c6fcf  jz      short loc_1800C6FFD
0x1800c6fd1  cmp     qword ptr [rdi+18h], 0
0x1800c6fd6  jz      short loc_1800C6FFD
0x1800c6fd8  cmp     qword ptr [rdi+20h], 0
0x1800c6fdd  jz      short loc_1800C6FFD
0x1800c6fdf  cmp     qword ptr [rdi+28h], 0
0x1800c6fe4  jz      short loc_1800C6FFD
0x1800c6fe6  cmp     qword ptr [rdi+30h], 0
0x1800c6feb  jz      short loc_1800C6FFD
0x1800c6fed  cmp     qword ptr [rdi+8], 0
0x1800c6ff2  jz      short loc_1800C6FFD
0x1800c6ff4  cmp     qword ptr [rdi+10h], 0
0x1800c6ff9  jz      short loc_1800C6FFD
0x1800c6ffb  xor     esi, esi
0x1800c6ffd  mov     eax, esi
0x1800c6fff  add     rsp, 20h
0x1800c7003  pop     r14
0x1800c7005  pop     rdi
0x1800c7006  pop     rsi
0x1800c7007  pop     rbp
0x1800c7008  pop     rbx
0x1800c7009  retn
```
