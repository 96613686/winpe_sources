# DhcpCheckIfSystemUpgraded

- ea: `0x18001d2bc`
- end: `0x18001d3d1`
- name: `DhcpCheckIfSystemUpgraded`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180025bf4`

## callees

- `0x180002854`
- `0x18000323c`
- `0x18001d2bc`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001d3b7`
- `ADVAPI32!RegCloseKey` at `0x18001d3b7`
- `ADVAPI32!RegOpenKeyExW` at `0x18001d2eb`
- `ADVAPI32!RegOpenKeyExW` at `0x18001d2eb`
- `ADVAPI32!RegQueryValueExW` at `0x18001d328`
- `ADVAPI32!RegQueryValueExW` at `0x18001d328`
- `ADVAPI32!RegDeleteValueW` at `0x18001d373`
- `ADVAPI32!RegDeleteValueW` at `0x18001d373`

## string_xrefs

- `0x18001d2d5`: `SYSTEM\CurrentControlSet\Services\DHCPServer\Parameters\Configuration`

## pseudocode

```c
__int64 DhcpCheckIfSystemUpgraded()
{
  unsigned int v0; // ebx
  unsigned int v2; // eax
  DWORD Type; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v0 = 0;
  hKey = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\DHCPServer\\Parameters\\Configuration",
         0,
         0xFu,
         &hKey) )
  {
    return 0;
  }
  Type = 4;
  if ( !RegQueryValueExW(hKey, L"UpgradeDone", 0, &Type, 0, 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids);
    v2 = RegDeleteValueW(hKey, L"UpgradeDone");
    if ( v2
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids, v2);
    }
    v0 = 1;
  }
  RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18001d2bc  mov     r11, rsp
0x18001d2bf  mov     [r11+18h], rbx
0x18001d2c3  push    rdi
0x18001d2c4  sub     rsp, 30h
0x18001d2c8  xor     ebx, ebx
0x18001d2ca  lea     rax, [r11+10h]
0x18001d2ce  xor     r8d, r8d; ulOptions
0x18001d2d1  mov     [r11+10h], rbx
0x18001d2d5  lea     rdx, aSystemCurrentc_5; "SYSTEM\\CurrentControlSet\\Services\\DH"...
0x18001d2dc  mov     [r11-18h], rax
0x18001d2e0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d2e7  lea     r9d, [rbx+0Fh]; samDesired
0x18001d2eb  call    cs:__imp_RegOpenKeyExW
0x18001d2f2  nop     dword ptr [rax+rax+00h]
0x18001d2f7  test    eax, eax
0x18001d2f9  jz      short loc_18001D302
0x18001d2fb  xor     eax, eax
0x18001d2fd  jmp     loc_18001D3C5
0x18001d302  mov     rcx, [rsp+38h+hKey]; hKey
0x18001d307  lea     r9, [rsp+38h+Type]; lpType
0x18001d30c  mov     [rsp+38h+lpcbData], rbx; lpcbData
0x18001d311  lea     rdx, aUpgradedone; "UpgradeDone"
0x18001d318  xor     r8d, r8d; lpReserved
0x18001d31b  mov     [rsp+38h+lpData], rbx; lpData
0x18001d320  mov     [rsp+38h+Type], 4
0x18001d328  call    cs:__imp_RegQueryValueExW
0x18001d32f  nop     dword ptr [rax+rax+00h]
0x18001d334  test    eax, eax
0x18001d336  jnz     short loc_18001D3B2
0x18001d338  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d33f  lea     rdi, WPP_GLOBAL_Control
0x18001d346  cmp     rcx, rdi
0x18001d349  jz      short loc_18001D367
0x18001d34b  test    dword ptr [rcx+1Ch], 8000h
0x18001d352  jz      short loc_18001D367
0x18001d354  mov     rcx, [rcx+10h]
0x18001d358  lea     edx, [rax+2Dh]
0x18001d35b  lea     r8, WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids
0x18001d362  call    WPP_SF_
0x18001d367  mov     rcx, [rsp+38h+hKey]; hKey
0x18001d36c  lea     rdx, aUpgradedone; "UpgradeDone"
0x18001d373  call    cs:__imp_RegDeleteValueW
0x18001d37a  nop     dword ptr [rax+rax+00h]
0x18001d37f  test    eax, eax
0x18001d381  jz      short loc_18001D3AD
0x18001d383  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d38a  cmp     rcx, rdi
0x18001d38d  jz      short loc_18001D3AD
0x18001d38f  test    byte ptr [rcx+1Ch], 10h
0x18001d393  jz      short loc_18001D3AD
0x18001d395  mov     rcx, [rcx+10h]
0x18001d399  lea     r8, WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids
0x18001d3a0  mov     edx, 2Eh ; '.'
0x18001d3a5  mov     r9d, eax
0x18001d3a8  call    WPP_SF_D
0x18001d3ad  mov     ebx, 1
0x18001d3b2  mov     rcx, [rsp+38h+hKey]; hKey
0x18001d3b7  call    cs:__imp_RegCloseKey
0x18001d3be  nop     dword ptr [rax+rax+00h]
0x18001d3c3  mov     eax, ebx
0x18001d3c5  mov     rbx, [rsp+38h+arg_10]
0x18001d3ca  add     rsp, 30h
0x18001d3ce  pop     rdi
0x18001d3cf  retn
```
