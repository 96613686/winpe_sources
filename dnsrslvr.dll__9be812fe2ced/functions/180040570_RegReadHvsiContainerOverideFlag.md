# RegReadHvsiContainerOverideFlag

- ea: `0x180040570`
- end: `0x18004062c`
- name: `RegReadHvsiContainerOverideFlag`
- size: `188`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x1800495c0`

## callees

- `0x180040570`
- `0x180046ec0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040611`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180040611`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800405c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800405c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800405f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800405f6`

## string_xrefs

- `0x180040596`: `SYSTEM\CurrentControlSet\Services\Dnscache\Parameters\dnscache`

## pseudocode

```c
__int64 RegReadHvsiContainerOverideFlag()
{
  unsigned int v0; // ebx
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-1Ch] BYREF
  DWORD Type; // [rsp+40h] [rbp-18h] BYREF

  *(_DWORD *)Data = 0;
  cbData = 4;
  Type = 4;
  v0 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\Dnscache\\Parameters\\dnscache",
          0,
          1u,
          &hKey)
    && !RegQueryValueExW(hKey, L"IsHvsiContainerOverride", 0, &Type, Data, &cbData) )
  {
    LOBYTE(v0) = *(_DWORD *)Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180040570  push    rbx
0x180040572  sub     rsp, 50h
0x180040576  mov     rax, cs:__security_cookie
0x18004057d  xor     rax, rsp
0x180040580  mov     [rsp+58h+var_10], rax
0x180040585  mov     eax, 4
0x18004058a  mov     dword ptr [rsp+58h+Data], 0
0x180040592  mov     [rsp+58h+cbData], eax
0x180040596  lea     rdx, aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18004059d  mov     [rsp+58h+Type], eax
0x1800405a1  xor     ebx, ebx
0x1800405a3  lea     rax, [rsp+58h+hKey]
0x1800405a8  mov     [rsp+58h+hKey], 0
0x1800405b1  xor     r8d, r8d; ulOptions
0x1800405b4  mov     [rsp+58h+phkResult], rax; phkResult
0x1800405b9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800405c0  lea     r9d, [rbx+1]; samDesired
0x1800405c4  call    cs:__imp_RegOpenKeyExW
0x1800405ca  test    eax, eax
0x1800405cc  jnz     short loc_180040607
0x1800405ce  mov     rcx, [rsp+58h+hKey]; hKey
0x1800405d3  lea     rax, [rsp+58h+cbData]
0x1800405d8  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800405dd  lea     r9, [rsp+58h+Type]; lpType
0x1800405e2  lea     rax, [rsp+58h+Data]
0x1800405e7  xor     r8d, r8d; lpReserved
0x1800405ea  lea     rdx, aIshvsicontaine; "IsHvsiContainerOverride"
0x1800405f1  mov     [rsp+58h+phkResult], rax; lpData
0x1800405f6  call    cs:__imp_RegQueryValueExW
0x1800405fc  test    eax, eax
0x1800405fe  jnz     short loc_180040607
0x180040600  cmp     dword ptr [rsp+58h+Data], ebx
0x180040604  setnz   bl
0x180040607  mov     rcx, [rsp+58h+hKey]; hKey
0x18004060c  test    rcx, rcx
0x18004060f  jz      short loc_180040617
0x180040611  call    cs:__imp_RegCloseKey
0x180040617  mov     eax, ebx
0x180040619  mov     rcx, [rsp+58h+var_10]
0x18004061e  xor     rcx, rsp; StackCookie
0x180040621  call    __security_check_cookie
0x180040626  add     rsp, 50h
0x18004062a  pop     rbx
0x18004062b  retn
```
