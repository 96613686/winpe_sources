# dwGetNumberOfRings

- ea: `0x180016498`
- end: `0x180016601`
- name: `dwGetNumberOfRings`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180002e20`

## callees

- `0x180016498`
- `0x1800292b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001658a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001658a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001653a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001653a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800165b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800165b9`
- `rtutils!TracePrintfExA` at `0x18001655b`
- `rtutils!TracePrintfExA` at `0x1800165dc`
- `rtutils!TracePrintfExA` at `0x18001655b`
- `rtutils!TracePrintfExA` at `0x1800165dc`

## string_xrefs

- `0x1800164b8`: `SYSTEM\CurrentControlSet\Services\Rasman\Parameters`
- `0x18001654c`: `dwGetNumberOfRings: failed to open rasman key in registry. 0x%x`

## pseudocode

```c
__int64 dwGetNumberOfRings()
{
  LSTATUS v0; // eax
  unsigned int v1; // ebx
  HKEY hKey; // [rsp+30h] [rbp-39h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-31h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-2Dh] BYREF
  WCHAR SubKey[56]; // [rsp+40h] [rbp-29h] BYREF

  wcscpy(SubKey, L"SYSTEM\\CurrentControlSet\\Services\\Rasman\\Parameters");
  hKey = 0;
  cbData = 4;
  Type = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  v1 = v0;
  if ( v0 )
  {
    TracePrintfExA(dwTraceId, 0x10006u, "dwGetNumberOfRings: failed to open rasman key in registry. 0x%x", v0);
  }
  else
  {
    v1 = RegQueryValueExW(hKey, L"NumberOfRings", 0, &Type, &NumberOfRings, &cbData);
    if ( v1 )
      *(_DWORD *)&NumberOfRings = 2;
    if ( *(_DWORD *)&NumberOfRings > 0x14u )
      *(_DWORD *)&NumberOfRings = 2;
  }
  if ( hKey )
    RegCloseKey(hKey);
  TracePrintfExA(dwTraceId, 0x10006u, "dwGetNumberOfRings: dwRings=%d. lr=0x%x", *(_DWORD *)&NumberOfRings, v1);
  return v1;
}

```

## disassembly

```asm
0x180016498  mov     [rsp-8+arg_0], rbx
0x18001649d  push    rbp
0x18001649e  lea     rbp, [rsp-57h]
0x1800164a3  sub     rsp, 0C0h
0x1800164aa  mov     rax, cs:__security_cookie
0x1800164b1  xor     rax, rsp
0x1800164b4  mov     [rbp+57h+var_10], rax
0x1800164b8  movaps  xmm0, xmmword ptr cs:aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x1800164bf  lea     rax, [rbp+57h+hKey]
0x1800164c3  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+10h; "urrentControlSet\\Services\\Rasman\\Par"...
0x1800164ca  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x1800164ce  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x1800164d2  mov     r9d, 20019h; samDesired
0x1800164d8  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+20h; "ntrolSet\\Services\\Rasman\\Parameters"
0x1800164df  xor     r8d, r8d; ulOptions
0x1800164e2  movaps  [rbp+57h+var_60], xmm0
0x1800164e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800164ed  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+40h; "s\\Rasman\\Parameters"
0x1800164f4  movaps  [rbp+57h+var_70], xmm1
0x1800164f8  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+30h; "\\Services\\Rasman\\Parameters"
0x1800164ff  movaps  [rbp+57h+var_40], xmm0
0x180016503  movsd   xmm0, qword ptr cs:aSystemCurrentc+60h; "ers"
0x18001650b  movaps  [rbp+57h+var_50], xmm1
0x18001650f  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+50h; "\\Parameters"
0x180016516  movsd   [rbp+57h+var_20], xmm0
0x18001651b  mov     [rbp+57h+hKey], 0
0x180016523  mov     [rbp+57h+cbData], 4
0x18001652a  mov     [rbp+57h+Type], 0
0x180016531  movaps  [rbp+57h+var_30], xmm1
0x180016535  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18001653a  call    cs:__imp_RegOpenKeyExW
0x180016540  mov     ebx, eax
0x180016542  test    eax, eax
0x180016544  jz      short loc_180016563
0x180016546  mov     ecx, cs:dwTraceId; dwTraceID
0x18001654c  lea     r8, szFormat; "dwGetNumberOfRings: failed to open rasm"...
0x180016553  mov     r9d, eax
0x180016556  mov     edx, 10006h; dwFlags
0x18001655b  call    cs:__imp_TracePrintfExA
0x180016561  jmp     short loc_1800165B0
0x180016563  mov     rcx, [rbp+57h+hKey]; hKey
0x180016567  lea     rax, [rbp+57h+cbData]
0x18001656b  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x180016570  lea     r9, [rbp+57h+Type]; lpType
0x180016574  lea     rax, NumberOfRings
0x18001657b  xor     r8d, r8d; lpReserved
0x18001657e  lea     rdx, aNumberofrings; "NumberOfRings"
0x180016585  mov     [rsp+0C0h+phkResult], rax; lpData
0x18001658a  call    cs:__imp_RegQueryValueExW
0x180016590  mov     ebx, eax
0x180016592  mov     eax, 2
0x180016597  test    ebx, ebx
0x180016599  jz      short loc_1800165A1
0x18001659b  mov     cs:NumberOfRings, eax
0x1800165a1  cmp     cs:NumberOfRings, 14h
0x1800165a8  jbe     short loc_1800165B0
0x1800165aa  mov     cs:NumberOfRings, eax
0x1800165b0  mov     rcx, [rbp+57h+hKey]; hKey
0x1800165b4  test    rcx, rcx
0x1800165b7  jz      short loc_1800165BF
0x1800165b9  call    cs:__imp_RegCloseKey
0x1800165bf  mov     r9d, cs:NumberOfRings
0x1800165c6  lea     r8, aDwgetnumberofr_0; "dwGetNumberOfRings: dwRings=%d. lr=0x%x"
0x1800165cd  mov     ecx, cs:dwTraceId; dwTraceID
0x1800165d3  mov     edx, 10006h; dwFlags
0x1800165d8  mov     dword ptr [rsp+0C0h+phkResult], ebx
0x1800165dc  call    cs:__imp_TracePrintfExA
0x1800165e2  mov     eax, ebx
0x1800165e4  mov     rcx, [rbp+57h+var_10]
0x1800165e8  xor     rcx, rsp; StackCookie
0x1800165eb  call    __security_check_cookie
0x1800165f0  mov     rbx, [rsp+0C0h+arg_0]
0x1800165f8  add     rsp, 0C0h
0x1800165ff  pop     rbp
0x180016600  retn
```
