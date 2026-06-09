# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)

- ea: `0x140003bb4`
- end: `0x140003cd1`
- name: `?IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z`
- size: `285`
- prototype: `char __fastcall()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400039d0`

## callees

- `0x14000233f`
- `0x140003bb4`
- `0x1400115f0`

## import_xrefs

- `ntdll!VerSetConditionMask` at `0x140003c0d`
- `ntdll!VerSetConditionMask` at `0x140003c1e`
- `ntdll!VerSetConditionMask` at `0x140003c2f`
- `ntdll!VerSetConditionMask` at `0x140003c0d`
- `ntdll!VerSetConditionMask` at `0x140003c1e`
- `ntdll!VerSetConditionMask` at `0x140003c2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003c9d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140003c9d`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x140003c4f`
- `api-ms-win-core-kernel32-legacy-l1-1-1!VerifyVersionInfoW` at `0x140003c4f`

## string_xrefs

- `0x140003c5d`: `CommercialDataOptIn`

## pseudocode

```c
char __fastcall Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial()
{
  ULONGLONG v0; // rax
  ULONGLONG v1; // rax
  ULONGLONG v2; // rax
  int pvData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData[3]; // [rsp+44h] [rbp-BCh] BYREF
  _OSVERSIONINFOEXW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF

  if ( !`Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial'::`2'::AlreadyChecked )
  {
    VersionInformation.dwOSVersionInfoSize = 284;
    *(_OWORD *)&VersionInformation.dwMajorVersion = 0;
    memset_0(VersionInformation.szCSDVersion, 0, sizeof(VersionInformation.szCSDVersion));
    *(_QWORD *)&VersionInformation.wServicePackMajor = 0;
    v0 = VerSetConditionMask(0, 2u, 3u);
    v1 = VerSetConditionMask(v0, 1u, 3u);
    v2 = VerSetConditionMask(v1, 0x20u, 3u);
    *(_QWORD *)&VersionInformation.dwMajorVersion = 10;
    VersionInformation.wServicePackMajor = 0;
    if ( !VerifyVersionInfoW(&VersionInformation, 0x23u, v2) )
    {
      pvData = 0;
      pcbData[0] = 4;
      RegGetValueW(
        HKEY_LOCAL_MACHINE,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection",
        L"CommercialDataOptIn",
        0x20000018u,
        0,
        &pvData,
        pcbData);
      `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial'::`2'::IsOptedIn = pvData != 0;
    }
    `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial'::`2'::AlreadyChecked = 1;
  }
  return `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial'::`2'::IsOptedIn;
}

```

## disassembly

```asm
0x140003bb4  push    rbp
0x140003bb6  lea     rbp, [rsp-80h]
0x140003bbb  sub     rsp, 180h
0x140003bc2  mov     rax, cs:__security_cookie
0x140003bc9  xor     rax, rsp
0x140003bcc  mov     [rbp+80h+var_10], rax
0x140003bd0  cmp     cs:?AlreadyChecked@?1??IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, 0; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)'::`2'::AlreadyChecked
0x140003bd7  jnz     loc_140003CB6
0x140003bdd  xorps   xmm0, xmm0
0x140003be0  mov     [rsp+180h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140003be8  xor     edx, edx; Val
0x140003bea  lea     rcx, [rsp+180h+VersionInformation.szCSDVersion]; void *
0x140003bef  mov     r8d, 100h; Size
0x140003bf5  movups  xmmword ptr [rsp+180h+VersionInformation.dwMajorVersion], xmm0
0x140003bfa  call    memset_0
0x140003bff  xor     eax, eax
0x140003c01  mov     r8b, 3; Condition
0x140003c04  xor     ecx, ecx; ConditionMask
0x140003c06  mov     qword ptr [rbp+80h+VersionInformation.wServicePackMajor], rax
0x140003c0a  lea     edx, [rax+2]; TypeMask
0x140003c0d  call    cs:__imp_VerSetConditionMask
0x140003c13  mov     r8b, 3; Condition
0x140003c16  mov     edx, 1; TypeMask
0x140003c1b  mov     rcx, rax; ConditionMask
0x140003c1e  call    cs:__imp_VerSetConditionMask
0x140003c24  mov     r8b, 3; Condition
0x140003c27  mov     edx, 20h ; ' '; TypeMask
0x140003c2c  mov     rcx, rax; ConditionMask
0x140003c2f  call    cs:__imp_VerSetConditionMask
0x140003c35  xor     ecx, ecx
0x140003c37  mov     qword ptr [rsp+180h+VersionInformation.dwMajorVersion], 0Ah
0x140003c40  mov     [rbp+80h+VersionInformation.wServicePackMajor], cx
0x140003c44  mov     r8, rax; dwlConditionMask
0x140003c47  lea     edx, [rcx+23h]; dwTypeMask
0x140003c4a  lea     rcx, [rsp+180h+VersionInformation]; lpVersionInformation
0x140003c4f  call    cs:__imp_VerifyVersionInfoW
0x140003c55  test    eax, eax
0x140003c57  jnz     short loc_140003CAF
0x140003c59  mov     [rsp+180h+var_140], eax
0x140003c5d  lea     r8, aCommercialdata; "CommercialDataOptIn"
0x140003c64  lea     rax, [rsp+180h+var_13C]
0x140003c69  mov     [rsp+180h+var_13C], 4
0x140003c71  mov     [rsp+180h+pcbData], rax; pcbData
0x140003c76  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140003c7d  lea     rax, [rsp+180h+var_140]
0x140003c82  mov     r9d, 20000018h; dwFlags
0x140003c88  mov     [rsp+180h+pvData], rax; pvData
0x140003c8d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140003c94  mov     [rsp+180h+pdwType], 0; pdwType
0x140003c9d  call    cs:__imp_RegGetValueW
0x140003ca3  cmp     [rsp+180h+var_140], 0
0x140003ca8  setnz   cs:?IsOptedIn@?1??IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)'::`2'::IsOptedIn
0x140003caf  mov     cs:?AlreadyChecked@?1??IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA, 1; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)'::`2'::AlreadyChecked
0x140003cb6  mov     al, cs:?IsOptedIn@?1??IsOptedIntoCommercial@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z@4_NA; bool `Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCommercial(bool)'::`2'::IsOptedIn
0x140003cbc  mov     rcx, [rbp+80h+var_10]
0x140003cc0  xor     rcx, rsp; StackCookie
0x140003cc3  call    __security_check_cookie
0x140003cc8  add     rsp, 180h
0x140003ccf  pop     rbp
0x140003cd0  retn
```
