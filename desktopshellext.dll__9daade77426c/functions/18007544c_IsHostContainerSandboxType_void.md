# IsHostContainerSandboxType(void)

- ea: `0x18007544c`
- end: `0x180075506`
- name: `?IsHostContainerSandboxType@@YA_NXZ`
- size: `186`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18007571c`

## callees

- `0x1800108cc`
- `0x18007544c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800754c8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800754c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800754e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800754f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800754e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800754f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075481`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180075481`

## pseudocode

```c
bool IsHostContainerSandboxType(void)
{
  HKEY *phkResult; // rax
  bool v1; // bl
  int pvData; // [rsp+50h] [rbp+8h] BYREF
  DWORD pcbData; // [rsp+58h] [rbp+10h] BYREF
  HKEY hkey; // [rsp+60h] [rbp+18h] BYREF

  hkey = 0;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hkey);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\ControlSet001\\Control", 0, 0x20019u, phkResult)
    || (pvData = 0, pcbData = 4, RegGetValueW(hkey, 0, L"ContainerType", 0x18u, 0, &pvData, &pcbData)) )
  {
    if ( hkey )
      RegCloseKey(hkey);
    return 0;
  }
  else
  {
    v1 = pvData == 4;
    if ( hkey )
      RegCloseKey(hkey);
    return v1;
  }
}

```

## disassembly

```asm
0x18007544c  push    rbx
0x18007544e  sub     rsp, 40h
0x180075452  lea     rcx, [rsp+48h+hkey]
0x180075457  mov     [rsp+48h+hkey], 0
0x180075460  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180075465  mov     r9d, 20019h; samDesired
0x18007546b  mov     [rsp+48h+phkResult], rax; phkResult
0x180075470  xor     r8d, r8d; ulOptions
0x180075473  lea     rdx, aSystemControls; "System\\ControlSet001\\Control"
0x18007547a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180075481  call    cs:__imp_RegOpenKeyExW
0x180075487  test    eax, eax
0x180075489  jnz     short loc_1800754EE
0x18007548b  mov     rcx, [rsp+48h+hkey]; hkey
0x180075490  lea     r8, aContainertype; "ContainerType"
0x180075497  mov     [rsp+48h+arg_0], eax
0x18007549b  mov     r9d, 18h; dwFlags
0x1800754a1  lea     rax, [rsp+48h+arg_8]
0x1800754a6  mov     [rsp+48h+arg_8], 4
0x1800754ae  mov     [rsp+48h+pcbData], rax; pcbData
0x1800754b3  xor     edx, edx; lpSubKey
0x1800754b5  lea     rax, [rsp+48h+arg_0]
0x1800754ba  mov     [rsp+48h+pvData], rax; pvData
0x1800754bf  mov     [rsp+48h+phkResult], 0; pdwType
0x1800754c8  call    cs:__imp_RegGetValueW
0x1800754ce  test    eax, eax
0x1800754d0  jnz     short loc_1800754EE
0x1800754d2  cmp     [rsp+48h+arg_0], 4
0x1800754d7  mov     rcx, [rsp+48h+hkey]; hKey
0x1800754dc  setz    bl
0x1800754df  test    rcx, rcx
0x1800754e2  jz      short loc_1800754EA
0x1800754e4  call    cs:__imp_RegCloseKey
0x1800754ea  mov     al, bl
0x1800754ec  jmp     short loc_180075500
0x1800754ee  mov     rcx, [rsp+48h+hkey]; hKey
0x1800754f3  test    rcx, rcx
0x1800754f6  jz      short loc_1800754FE
0x1800754f8  call    cs:__imp_RegCloseKey
0x1800754fe  xor     al, al
0x180075500  add     rsp, 40h
0x180075504  pop     rbx
0x180075505  retn
```
