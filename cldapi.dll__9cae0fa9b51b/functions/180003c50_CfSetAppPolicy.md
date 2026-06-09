# CfSetAppPolicy

- ea: `0x180003c50`
- end: `0x180003cf2`
- name: `CfSetAppPolicy`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003c50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003cb8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003cb8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003c75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003c75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003cdd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003cdd`

## pseudocode

```c
__int64 __fastcall CfSetAppPolicy(HKEY a1, const WCHAR *a2, int a3)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  LSTATUS v5; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF
  int Data; // [rsp+50h] [rbp+18h] BYREF

  Data = a3;
  hKey = 0;
  v3 = RegOpenKeyExW(a1, a2, 0, 0x20006u, &hKey);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    v5 = RegSetValueExW(hKey, L"Enabled", 0, 4u, (const BYTE *)&Data, 4u);
    v4 = v5;
    if ( v5 > 0 )
      v4 = (unsigned __int16)v5 | 0x80070000;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180003c50  mov     r11, rsp
0x180003c53  mov     [r11+18h], r8d
0x180003c57  push    rbx
0x180003c58  sub     rsp, 30h
0x180003c5c  lea     rax, [r11+8]
0x180003c60  mov     qword ptr [r11+8], 0
0x180003c68  mov     r9d, 20006h; samDesired
0x180003c6e  mov     [r11-18h], rax
0x180003c72  xor     r8d, r8d; ulOptions
0x180003c75  call    cs:__imp_RegOpenKeyExW
0x180003c7c  nop     dword ptr [rax+rax+00h]
0x180003c81  mov     ebx, eax
0x180003c83  test    eax, eax
0x180003c85  jle     short loc_180003C90
0x180003c87  movzx   ebx, ax
0x180003c8a  or      ebx, 80070000h
0x180003c90  test    ebx, ebx
0x180003c92  js      short loc_180003CD3
0x180003c94  mov     rcx, [rsp+38h+hKey]; hKey
0x180003c99  lea     rax, [rsp+38h+Data]
0x180003c9e  mov     r9d, 4; dwType
0x180003ca4  lea     rdx, ValueName; "Enabled"
0x180003cab  mov     [rsp+38h+cbData], r9d; cbData
0x180003cb0  xor     r8d, r8d; Reserved
0x180003cb3  mov     [rsp+38h+lpData], rax; lpData
0x180003cb8  call    cs:__imp_RegSetValueExW
0x180003cbf  nop     dword ptr [rax+rax+00h]
0x180003cc4  mov     ebx, eax
0x180003cc6  test    eax, eax
0x180003cc8  jle     short loc_180003CD3
0x180003cca  movzx   ebx, ax
0x180003ccd  or      ebx, 80070000h
0x180003cd3  mov     rcx, [rsp+38h+hKey]; hKey
0x180003cd8  test    rcx, rcx
0x180003cdb  jz      short loc_180003CE9
0x180003cdd  call    cs:__imp_RegCloseKey
0x180003ce4  nop     dword ptr [rax+rax+00h]
0x180003ce9  mov     eax, ebx
0x180003ceb  add     rsp, 30h
0x180003cef  pop     rbx
0x180003cf0  retn
```
