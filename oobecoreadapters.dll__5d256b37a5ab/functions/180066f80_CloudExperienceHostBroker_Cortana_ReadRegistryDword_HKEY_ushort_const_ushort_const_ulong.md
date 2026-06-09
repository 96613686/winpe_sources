# CloudExperienceHostBroker::Cortana::ReadRegistryDword(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x180066f80`
- end: `0x180067050`
- name: `?ReadRegistryDword@Cortana@CloudExperienceHostBroker@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `208`
- prototype: `int(CloudExperienceHostBroker::Cortana *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800676f0`
- `0x180067970`
- `0x1800679e0`
- `0x180067b30`

## callees

- `0x180009834`
- `0x18000b254`
- `0x180066f80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006701d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006701d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066fd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066fd5`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostBroker::Cortana::ReadRegistryDword(
        CloudExperienceHostBroker::Cortana *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  LSTATUS v6; // eax
  bool v7; // sf
  LSTATUS Value; // eax
  bool v9; // sf
  CloudExperienceHostBroker::Cortana *cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY Data; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+20h] BYREF

  Data = a2;
  cbData = this;
  *(_DWORD *)a4 = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Speech_OneCore\\AudioPolicy", 0, 0x20019u, &hKey);
  v7 = v6 < 0;
  if ( v6 > 0 )
    v7 = 1;
  if ( !v7 )
  {
    LODWORD(Data) = 0;
    LODWORD(cbData) = 4;
    Value = RegQueryValueExW(hKey, a3, 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData);
    v9 = Value < 0;
    if ( Value > 0 )
      v9 = 1;
    if ( !v9 )
      *(_DWORD *)a4 = (_DWORD)Data;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return 0;
}

```

## disassembly

```asm
0x180066f80  mov     rax, rsp
0x180066f83  mov     [rax+18h], rbx
0x180066f87  mov     [rax+10h], rdx
0x180066f8b  mov     [rax+8], rcx
0x180066f8f  push    rdi
0x180066f90  sub     rsp, 30h
0x180066f94  xor     edx, edx
0x180066f96  mov     dword ptr [r9], 0
0x180066f9d  lea     rcx, [rax+20h]
0x180066fa1  mov     qword ptr [rax+20h], 0
0x180066fa9  mov     rbx, r9
0x180066fac  mov     rdi, r8
0x180066faf  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180066fb4  lea     rax, [rsp+38h+hKey]
0x180066fb9  mov     r9d, 20019h; samDesired
0x180066fbf  xor     r8d, r8d; ulOptions
0x180066fc2  mov     [rsp+38h+phkResult], rax; phkResult
0x180066fc7  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Speech_OneCore\\Au"...
0x180066fce  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180066fd5  call    cs:__imp_RegOpenKeyExW
0x180066fdb  test    eax, eax
0x180066fdd  jle     short loc_180066FE9
0x180066fdf  movzx   eax, ax
0x180066fe2  or      eax, 80070000h
0x180066fe7  test    eax, eax
0x180066fe9  js      short loc_180067039
0x180066feb  mov     rcx, [rsp+38h+hKey]; hKey
0x180066ff0  lea     rax, [rsp+38h+cbData]
0x180066ff5  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180066ffa  xor     r9d, r9d; lpType
0x180066ffd  lea     rax, [rsp+38h+Data]
0x180067002  mov     dword ptr [rsp+38h+Data], 0
0x18006700a  xor     r8d, r8d; lpReserved
0x18006700d  mov     [rsp+38h+phkResult], rax; lpData
0x180067012  mov     rdx, rdi; lpValueName
0x180067015  mov     dword ptr [rsp+38h+cbData], 4
0x18006701d  call    cs:__imp_RegQueryValueExW
0x180067023  test    eax, eax
0x180067025  jle     short loc_180067031
0x180067027  movzx   eax, ax
0x18006702a  or      eax, 80070000h
0x18006702f  test    eax, eax
0x180067031  js      short loc_180067039
0x180067033  mov     eax, dword ptr [rsp+38h+Data]
0x180067037  mov     [rbx], eax
0x180067039  lea     rcx, [rsp+38h+hKey]
0x18006703e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180067043  mov     rbx, [rsp+38h+arg_10]
0x180067048  xor     eax, eax
0x18006704a  add     rsp, 30h
0x18006704e  pop     rdi
0x18006704f  retn
```
