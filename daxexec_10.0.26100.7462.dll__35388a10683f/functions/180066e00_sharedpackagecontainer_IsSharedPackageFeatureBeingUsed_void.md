# sharedpackagecontainer::IsSharedPackageFeatureBeingUsed(void)

- ea: `0x180066e00`
- end: `0x180066fd1`
- name: `?IsSharedPackageFeatureBeingUsed@sharedpackagecontainer@@YA_NXZ`
- size: `465`
- prototype: `bool __fastcall(sharedpackagecontainer *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180066bd4`
- `0x180067e48`

## callees

- `0x180010a84`
- `0x180065f8c`
- `0x180066e00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066edb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066f0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066edb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180066f0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066ebf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180066ebf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180066e51`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180066e51`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180066f5c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180066f5c`
- `AppXAllUserStore!GetProvisionedSharedPackageContainersFromRegistryStore` at `0x180066ef0`
- `AppXAllUserStore!GetProvisionedSharedPackageContainersFromRegistryStore` at `0x180066ef0`

## string_xrefs

- `0x180066faa`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180066fbe`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
bool __fastcall sharedpackagecontainer::IsSharedPackageFeatureBeingUsed(sharedpackagecontainer *this)
{
  LSTATUS ValueW; // eax
  sharedpackagecontainer *v2; // rcx
  unsigned __int64 v3; // r9
  char v4; // bl
  bool v5; // di
  int v6; // ecx
  bool result; // al
  int v8; // eax
  int phkResult; // [rsp+20h] [rbp-28h]
  int phkResulta; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int Data; // [rsp+50h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+10h] BYREF

  Data = 0;
  LODWORD(hKey) = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx-SharedPackageContainer",
             L"IsSpcBeingUsed",
             0x10u,
             0,
             &Data,
             (LPDWORD)&hKey);
  v3 = (unsigned int)ValueW;
  if ( ValueW > 0 )
    v3 = (unsigned __int16)ValueW | 0x80070000;
  try
  {
    if ( (v3 & 0x80000000) == 0LL )
      return Data == 1;
    if ( (unsigned int)(v3 + 2147024894) > 1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C60,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)v3,
        phkResult);
    if ( !sharedpackagecontainer::DoesAnySpcExist(v2) )
    {
      v4 = 0;
      Data = 0;
      hKey = 0;
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20019u, &hKey) )
      {
        v4 = 1;
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_12;
      }
      GetProvisionedSharedPackageContainersFromRegistryStore(hKey, 0, &Data);
      v5 = Data != 0;
      if ( hKey )
        RegCloseKey(hKey);
      if ( !v5 )
      {
LABEL_12:
        v6 = 0;
        if ( v4 )
          return 1;
        goto LABEL_15;
      }
    }
    v6 = 1;
LABEL_15:
    Data = v6;
    v8 = RegSetKeyValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx-SharedPackageContainer",
           L"IsSpcBeingUsed",
           4u,
           &Data,
           4u);
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1C60,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v8,
        phkResulta);
    result = Data != 0;
  }
  catch ( ... )
  {
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180066e00  mov     r11, rsp
0x180066e03  mov     [r11+18h], rbx
0x180066e07  mov     [r11+20h], rdi
0x180066e0b  push    r14
0x180066e0d  sub     rsp, 40h
0x180066e11  and     [rsp+48h+Data], 0
0x180066e16  mov     dword ptr [rsp+48h+hKey], 4
0x180066e1e  lea     rax, [r11+10h]
0x180066e22  mov     [r11-18h], rax
0x180066e26  lea     rax, [r11+8]
0x180066e2a  mov     [r11-20h], rax
0x180066e2e  and     qword ptr [r11-28h], 0
0x180066e33  mov     r9d, 10h; dwFlags
0x180066e39  lea     r8, aIsspcbeingused; "IsSpcBeingUsed"
0x180066e40  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180066e47  mov     r14, 0FFFFFFFF80000002h
0x180066e4e  mov     rcx, r14; hkey
0x180066e51  call    cs:__imp_RegGetValueW
0x180066e58  nop     dword ptr [rax+rax+00h]
0x180066e5d  mov     r9d, eax
0x180066e60  test    eax, eax
0x180066e62  jle     short loc_180066E6F
0x180066e64  movzx   r9d, ax
0x180066e68  or      r9d, 80070000h; char *
0x180066e6f  test    r9d, r9d
0x180066e72  jns     loc_180066F87
0x180066e78  lea     eax, [r9+7FF8FFFEh]
0x180066e7f  cmp     eax, 1
0x180066e82  ja      loc_180066FA5
0x180066e88  call    ?DoesAnySpcExist@sharedpackagecontainer@@YA_NXZ; sharedpackagecontainer::DoesAnySpcExist(void)
0x180066e8d  test    al, al
0x180066e8f  jnz     loc_180066F2A
0x180066e95  xor     bl, bl
0x180066e97  and     [rsp+48h+Data], 0
0x180066e9c  and     [rsp+48h+hKey], 0
0x180066ea2  lea     rax, [rsp+48h+hKey]
0x180066ea7  mov     [rsp+48h+phkResult], rax; phkResult
0x180066eac  mov     r9d, 20019h; samDesired
0x180066eb2  xor     r8d, r8d; ulOptions
0x180066eb5  lea     rdx, aSoftware_1; "Software"
0x180066ebc  mov     rcx, r14; hKey
0x180066ebf  call    cs:__imp_RegOpenKeyExW
0x180066ec6  nop     dword ptr [rax+rax+00h]
0x180066ecb  mov     rcx, [rsp+48h+hKey]; hKey
0x180066ed0  test    eax, eax
0x180066ed2  jz      short loc_180066EE9
0x180066ed4  mov     bl, 1
0x180066ed6  test    rcx, rcx
0x180066ed9  jz      short loc_180066F20
0x180066edb  call    cs:__imp_RegCloseKey
0x180066ee2  nop     dword ptr [rax+rax+00h]
0x180066ee7  jmp     short loc_180066F20
0x180066ee9  lea     r8, [rsp+48h+Data]
0x180066eee  xor     edx, edx
0x180066ef0  call    cs:__imp_GetProvisionedSharedPackageContainersFromRegistryStore
0x180066ef7  nop     dword ptr [rax+rax+00h]
0x180066efc  cmp     [rsp+48h+Data], 0
0x180066f01  setnbe  dil
0x180066f05  mov     rcx, [rsp+48h+hKey]; hKey
0x180066f0a  test    rcx, rcx
0x180066f0d  jz      short loc_180066F1B
0x180066f0f  call    cs:__imp_RegCloseKey
0x180066f16  nop     dword ptr [rax+rax+00h]
0x180066f1b  test    dil, dil
0x180066f1e  jnz     short loc_180066F2A
0x180066f20  xor     ecx, ecx
0x180066f22  test    bl, bl
0x180066f24  jz      short loc_180066F2F
0x180066f26  mov     al, 1
0x180066f28  jmp     short loc_180066F93
0x180066f2a  mov     ecx, 1
0x180066f2f  mov     [rsp+48h+Data], ecx
0x180066f33  mov     [rsp+48h+cbData], 4; cbData
0x180066f3b  lea     rax, [rsp+48h+Data]
0x180066f40  mov     [rsp+48h+phkResult], rax; int
0x180066f45  mov     r9d, 4; dwType
0x180066f4b  lea     r8, aIsspcbeingused; "IsSpcBeingUsed"
0x180066f52  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180066f59  mov     rcx, r14; hKey
0x180066f5c  call    cs:__imp_RegSetKeyValueW
0x180066f63  nop     dword ptr [rax+rax+00h]
0x180066f68  test    eax, eax
0x180066f6a  jle     short loc_180066F74
0x180066f6c  movzx   eax, ax
0x180066f6f  or      eax, 80070000h
0x180066f74  mov     rcx, [rsp+48h]; this
0x180066f79  test    eax, eax
0x180066f7b  js      short loc_180066FBB
0x180066f7d  cmp     [rsp+48h+Data], 0
0x180066f82  setnz   al
0x180066f85  jmp     short loc_180066F93
0x180066f87  cmp     [rsp+48h+Data], 1
0x180066f8c  setz    al
0x180066f8f  jmp     short loc_180066F93
0x180066f91  mov     al, 1
0x180066f93  mov     rbx, [rsp+48h+arg_10]
0x180066f98  mov     rdi, [rsp+48h+arg_18]
0x180066f9d  add     rsp, 40h
0x180066fa1  pop     r14
0x180066fa3  retn
0x180066fa5  mov     rcx, [rsp+48h]; this
0x180066faa  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180066fb1  mov     edx, 1C60h; void *
0x180066fb6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180066fbb  mov     r9d, eax; char *
0x180066fbe  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180066fc5  mov     edx, 1C60h; void *
0x180066fca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
