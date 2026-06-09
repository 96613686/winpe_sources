# GetServerOverrideVersion(ulong &)

- ea: `0x180045764`
- end: `0x18004582d`
- name: `?GetServerOverrideVersion@@YA_NAEAK@Z`
- size: `201`
- prototype: `bool __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180043754`

## callees

- `0x1800071c0`
- `0x180045764`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800457aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800457aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800457ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800457ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004580b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004581e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004580b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004581e`

## pseudocode

```c
char __fastcall GetServerOverrideVersion(unsigned int *a1)
{
  HKEY v2; // rcx
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  *a1 = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Enrollment", 0, 0x20019u, &hKey) >= 0
    && (Type = 0,
        Data = 0,
        cbData = 4,
        RegQueryValueExW(hKey, L"OverrideServerVersion", 0, &Type, (LPBYTE)&Data, &cbData) >= 0)
    && Type == 4 )
  {
    v2 = hKey;
    *a1 = Data;
    if ( v2 )
      RegCloseKey(v2);
    return 1;
  }
  else
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
}

```

## disassembly

```asm
0x180045764  push    rbp
0x180045766  push    rbx
0x180045767  mov     rbp, rsp
0x18004576a  sub     rsp, 38h
0x18004576e  mov     rbx, rcx
0x180045771  mov     dword ptr [rcx], 0
0x180045777  lea     rcx, [rbp+hKey]
0x18004577b  mov     [rbp+hKey], 0
0x180045783  xor     edx, edx
0x180045785  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004578a  lea     rax, [rbp+hKey]
0x18004578e  mov     r9d, 20019h; samDesired
0x180045794  xor     r8d, r8d; ulOptions
0x180045797  mov     [rsp+38h+phkResult], rax; phkResult
0x18004579c  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Enrollment"
0x1800457a3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800457aa  call    cs:__imp_RegOpenKeyExW
0x1800457b0  test    eax, eax
0x1800457b2  js      short loc_180045815
0x1800457b4  mov     rcx, [rbp+hKey]; hKey
0x1800457b8  lea     rax, [rbp+cbData]
0x1800457bc  mov     [rsp+38h+lpcbData], rax; lpcbData
0x1800457c1  lea     r9, [rbp+Type]; lpType
0x1800457c5  lea     rax, [rbp+Data]
0x1800457c9  mov     [rbp+Type], 0
0x1800457d0  xor     r8d, r8d; lpReserved
0x1800457d3  mov     [rsp+38h+phkResult], rax; lpData
0x1800457d8  lea     rdx, aOverrideserver; "OverrideServerVersion"
0x1800457df  mov     [rbp+Data], 0
0x1800457e6  mov     [rbp+cbData], 4
0x1800457ed  call    cs:__imp_RegQueryValueExW
0x1800457f3  test    eax, eax
0x1800457f5  js      short loc_180045815
0x1800457f7  cmp     [rbp+Type], 4
0x1800457fb  jnz     short loc_180045815
0x1800457fd  mov     rcx, [rbp+hKey]; hKey
0x180045801  mov     eax, [rbp+Data]
0x180045804  mov     [rbx], eax
0x180045806  test    rcx, rcx
0x180045809  jz      short loc_180045811
0x18004580b  call    cs:__imp_RegCloseKey
0x180045811  mov     al, 1
0x180045813  jmp     short loc_180045826
0x180045815  mov     rcx, [rbp+hKey]; hKey
0x180045819  test    rcx, rcx
0x18004581c  jz      short loc_180045824
0x18004581e  call    cs:__imp_RegCloseKey
0x180045824  xor     al, al
0x180045826  add     rsp, 38h
0x18004582a  pop     rbx
0x18004582b  pop     rbp
0x18004582c  retn
```
