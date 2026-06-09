# CSteelhead::IsIpv6TransportInstalled(void)

- ea: `0x180036e4c`
- end: `0x180036f10`
- name: `?IsIpv6TransportInstalled@CSteelhead@@AEAAHXZ`
- size: `196`
- prototype: `_BOOL8 __fastcall(CSteelhead *this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180036660`
- `0x180036a0c`
- `0x180036c94`

## callees

- `0x180036e4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036ee7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036ee7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036e97`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036e97`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036ecf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036ecf`

## string_xrefs

- `0x180036e90`: `System\CurrentControlSet\Services\Tcpip6\Parameters`
- `0x180036ec3`: `DisabledComponents`

## pseudocode

```c
_BOOL8 __fastcall CSteelhead::IsIpv6TransportInstalled(CSteelhead *this)
{
  BOOL v2; // ebx
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  int Data; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters", 0, 0x20019u, &hKey) )
    return 0;
  v2 = 1;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"DisabledComponents", 0, &Type, (LPBYTE)&Data, &cbData) )
    v2 = Data != 255;
  RegCloseKey(hKey);
  return *((_QWORD *)this + 11) && *((_DWORD *)this + 285) && v2;
}

```

## disassembly

```asm
0x180036e4c  push    rbp
0x180036e4e  push    rbx
0x180036e4f  push    rdi
0x180036e50  mov     rbp, rsp
0x180036e53  sub     rsp, 40h
0x180036e57  mov     rdi, rcx
0x180036e5a  mov     [rbp+hKey], 0
0x180036e62  lea     rax, [rbp+hKey]
0x180036e66  mov     [rbp+Type], 0
0x180036e6d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180036e74  mov     [rsp+40h+phkResult], rax; phkResult
0x180036e79  mov     r9d, 20019h; samDesired
0x180036e7f  mov     [rbp+Data], 0
0x180036e86  xor     r8d, r8d; ulOptions
0x180036e89  mov     [rbp+cbData], 0
0x180036e90  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Tc"...
0x180036e97  call    cs:__imp_RegOpenKeyExW
0x180036e9d  test    eax, eax
0x180036e9f  jnz     short loc_180036F06
0x180036ea1  mov     rcx, [rbp+hKey]; hKey
0x180036ea5  lea     ebx, [rax+1]
0x180036ea8  lea     rax, [rbp+cbData]
0x180036eac  mov     [rbp+cbData], 4
0x180036eb3  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180036eb8  lea     r9, [rbp+Type]; lpType
0x180036ebc  lea     rax, [rbp+Data]
0x180036ec0  xor     r8d, r8d; lpReserved
0x180036ec3  lea     rdx, aDisabledcompon; "DisabledComponents"
0x180036eca  mov     [rsp+40h+phkResult], rax; lpData
0x180036ecf  call    cs:__imp_RegQueryValueExW
0x180036ed5  test    eax, eax
0x180036ed7  jnz     short loc_180036EE3
0x180036ed9  cmp     [rbp+Data], 0FFh
0x180036ee0  cmovz   ebx, eax
0x180036ee3  mov     rcx, [rbp+hKey]; hKey
0x180036ee7  call    cs:__imp_RegCloseKey
0x180036eed  cmp     qword ptr [rdi+58h], 0
0x180036ef2  jz      short loc_180036F06
0x180036ef4  cmp     dword ptr [rdi+474h], 0
0x180036efb  jz      short loc_180036F06
0x180036efd  xor     eax, eax
0x180036eff  test    ebx, ebx
0x180036f01  setnz   al
0x180036f04  jmp     short loc_180036F08
0x180036f06  xor     eax, eax
0x180036f08  add     rsp, 40h
0x180036f0c  pop     rdi
0x180036f0d  pop     rbx
0x180036f0e  pop     rbp
0x180036f0f  retn
```
