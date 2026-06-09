# CFontContextMenu::_InstallAsLinkEnabled(void)

- ea: `0x1800112e4`
- end: `0x18001137e`
- name: `?_InstallAsLinkEnabled@CFontContextMenu@@AEAAHXZ`
- size: `154`
- prototype: `__int64 __fastcall(CFontContextMenu *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180011140`
- `0x18001fd50`
- `0x18001ff78`

## callees

- `0x1800112e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001136e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001136e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011354`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180011354`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011319`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011319`

## string_xrefs

- `0x180011343`: `InstallAsLink`

## pseudocode

```c
_BOOL8 __fastcall CFontContextMenu::_InstallAsLinkEnabled(CFontContextMenu *this)
{
  BOOL v1; // ebx
  CFontContextMenu *Type; // [rsp+50h] [rbp+20h] BYREF
  int Data; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  Type = this;
  v1 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Font Management",
          0,
          1u,
          &hKey) )
  {
    Data = 0;
    cbData = 4;
    LODWORD(Type) = 0;
    if ( !RegQueryValueExW(hKey, L"InstallAsLink", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData) && (_DWORD)Type == 4 )
      v1 = Data == 1;
    RegCloseKey(hKey);
  }
  return v1;
}

```

## disassembly

```asm
0x1800112e4  mov     [rsp-18h+Type], rcx
0x1800112e9  push    rbp
0x1800112ea  push    rbx
0x1800112eb  push    rsi
0x1800112ec  mov     rbp, rsp
0x1800112ef  sub     rsp, 30h
0x1800112f3  xor     ebx, ebx
0x1800112f5  lea     rax, [rbp+hKey]
0x1800112f9  xor     r8d, r8d; ulOptions
0x1800112fc  mov     [rbp+hKey], rbx
0x180011300  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180011307  mov     [rsp+30h+phkResult], rax; phkResult
0x18001130c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180011313  lea     esi, [rbx+1]
0x180011316  mov     r9d, esi; samDesired
0x180011319  call    cs:__imp_RegOpenKeyExW
0x18001131f  test    eax, eax
0x180011321  jnz     short loc_180011374
0x180011323  mov     rcx, [rbp+hKey]; hKey
0x180011327  lea     rax, [rbp+cbData]
0x18001132b  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180011330  lea     r9, [rbp+Type]; lpType
0x180011334  lea     rax, [rbp+Data]
0x180011338  mov     [rbp+Data], ebx
0x18001133b  xor     r8d, r8d; lpReserved
0x18001133e  mov     [rsp+30h+phkResult], rax; lpData
0x180011343  lea     rdx, ValueName; "InstallAsLink"
0x18001134a  mov     [rbp+cbData], 4
0x180011351  mov     dword ptr [rbp+Type], ebx
0x180011354  call    cs:__imp_RegQueryValueExW
0x18001135a  test    eax, eax
0x18001135c  jnz     short loc_18001136A
0x18001135e  cmp     dword ptr [rbp+Type], 4
0x180011362  jnz     short loc_18001136A
0x180011364  cmp     [rbp+Data], esi
0x180011367  cmovz   ebx, esi
0x18001136a  mov     rcx, [rbp+hKey]; hKey
0x18001136e  call    cs:__imp_RegCloseKey
0x180011374  mov     eax, ebx
0x180011376  add     rsp, 30h
0x18001137a  pop     rsi
0x18001137b  pop     rbx
0x18001137c  pop     rbp
0x18001137d  retn
```
