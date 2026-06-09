# RemoveRegistryKey(IIS_SETUP_REGISTRY_ENTRY *)

- ea: `0x1800029c4`
- end: `0x180002b87`
- name: `?RemoveRegistryKey@@YAJPEAUIIS_SETUP_REGISTRY_ENTRY@@@Z`
- size: `451`
- prototype: `__int64 __fastcall(struct IIS_SETUP_REGISTRY_ENTRY *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180001a20`

## callees

- `0x180001ab0`
- `0x1800029c4`
- `0x180003611`
- `0x180003650`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180002ae1`
- `msvcrt!wcsnlen` at `0x180002b40`
- `msvcrt!wcsnlen` at `0x180002ae1`
- `msvcrt!wcsnlen` at `0x180002b40`
- `ADVAPI32!RegDeleteKeyW` at `0x180002b6c`
- `ADVAPI32!RegDeleteKeyW` at `0x180002b6c`
- `ADVAPI32!RegEnumValueW` at `0x180002b2e`
- `ADVAPI32!RegEnumValueW` at `0x180002b2e`
- `ADVAPI32!RegEnumKeyExW` at `0x180002acf`
- `ADVAPI32!RegEnumKeyExW` at `0x180002acf`
- `ADVAPI32!RegOpenKeyExW` at `0x180002a4d`
- `ADVAPI32!RegOpenKeyExW` at `0x180002a4d`
- `ADVAPI32!RegCloseKey` at `0x180002a6e`
- `ADVAPI32!RegCloseKey` at `0x180002b5a`
- `ADVAPI32!RegCloseKey` at `0x180002a6e`
- `ADVAPI32!RegCloseKey` at `0x180002b5a`

## pseudocode

```c
__int64 __fastcall RemoveRegistryKey(struct IIS_SETUP_REGISTRY_ENTRY *a1)
{
  unsigned int v2; // ebx
  HKEY v3; // rsi
  LSTATUS v4; // eax
  LSTATUS v6; // ebx
  LSTATUS v7; // ebx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v12[510]; // [rsp+62h] [rbp-9Eh] BYREF

  hKey = 0;
  cchName = 0;
  memset_0(v12, 0, sizeof(v12));
  Name = 0;
  ftLastWriteTime = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  v3 = ConvertStringToHKey(*((wchar_t **)a1 + 1));
  v4 = RegOpenKeyExW(v3, *((LPCWSTR *)a1 + 2), 0, 0x20019u, &hKey);
  v2 = v4;
  if ( v4 )
  {
    if ( v4 <= 0 )
      goto LABEL_6;
    goto LABEL_5;
  }
  cchName = 256;
  v6 = RegEnumKeyExW(hKey, 0, &Name, &cchName, 0, 0, 0, &ftLastWriteTime);
  wcsnlen(&Name, 0x100u);
  if ( v6 == 259 && (v7 = RegEnumValueW(hKey, 0, &Name, &cchName, 0, 0, 0, 0), wcsnlen(&Name, 0x100u), v7 == 259) )
  {
    v2 = 0;
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v4 = RegDeleteKeyW(v3, *((LPCWSTR *)a1 + 2));
    if ( !v4 )
      goto LABEL_6;
    if ( v4 > 0 )
    {
LABEL_5:
      v2 = (unsigned __int16)v4 | 0x80070000;
      goto LABEL_6;
    }
    v2 = v4;
  }
  else
  {
    v2 = -2147020589;
  }
LABEL_6:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x1800029c4  push    rbp
0x1800029c6  push    rbx
0x1800029c7  push    rsi
0x1800029c8  push    rdi
0x1800029c9  lea     rbp, [rsp-178h]
0x1800029d1  sub     rsp, 278h
0x1800029d8  mov     rax, cs:__security_cookie
0x1800029df  xor     rax, rsp
0x1800029e2  mov     [rbp+190h+var_30], rax
0x1800029e9  mov     rdi, rcx
0x1800029ec  mov     [rsp+290h+hKey], 0
0x1800029f5  lea     rcx, [rsp+290h+var_22E]; void *
0x1800029fa  mov     [rsp+290h+cchName], 0
0x180002a02  xor     edx, edx; Val
0x180002a04  mov     r8d, 1FEh; Size
0x180002a0a  call    memset_0
0x180002a0f  xor     eax, eax
0x180002a11  mov     [rsp+290h+Name], ax
0x180002a16  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], rax
0x180002a1b  test    rdi, rdi
0x180002a1e  jnz     short loc_180002A27
0x180002a20  mov     ebx, 80070057h
0x180002a25  jmp     short loc_180002A74
0x180002a27  mov     rcx, [rdi+8]; String1
0x180002a2b  call    ?ConvertStringToHKey@@YAPEAUHKEY__@@PEAG@Z; ConvertStringToHKey(ushort *)
0x180002a30  mov     rdx, [rdi+10h]; lpSubKey
0x180002a34  mov     rsi, rax
0x180002a37  lea     rax, [rsp+290h+hKey]
0x180002a3c  mov     rcx, rsi; hKey
0x180002a3f  mov     r9d, 20019h; samDesired
0x180002a45  mov     [rsp+290h+phkResult], rax; phkResult
0x180002a4a  xor     r8d, r8d; ulOptions
0x180002a4d  call    cs:__imp_RegOpenKeyExW
0x180002a53  mov     ebx, eax
0x180002a55  test    eax, eax
0x180002a57  jz      short loc_180002A91
0x180002a59  jle     short loc_180002A64
0x180002a5b  movzx   ebx, ax
0x180002a5e  or      ebx, 80070000h
0x180002a64  mov     rcx, [rsp+290h+hKey]; hKey
0x180002a69  test    rcx, rcx
0x180002a6c  jz      short loc_180002A74
0x180002a6e  call    cs:__imp_RegCloseKey
0x180002a74  mov     eax, ebx
0x180002a76  mov     rcx, [rbp+190h+var_30]
0x180002a7d  xor     rcx, rsp; StackCookie
0x180002a80  call    __security_check_cookie
0x180002a85  add     rsp, 278h
0x180002a8c  pop     rdi
0x180002a8d  pop     rsi
0x180002a8e  pop     rbx
0x180002a8f  pop     rbp
0x180002a90  retn
0x180002a91  mov     rcx, [rsp+290h+hKey]; hKey
0x180002a96  lea     rax, [rsp+290h+ftLastWriteTime]
0x180002a9b  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180002aa0  lea     r9, [rsp+290h+cchName]; lpcchName
0x180002aa5  mov     [rsp+290h+lpcchClass], 0; lpcchClass
0x180002aae  lea     r8, [rsp+290h+Name]; lpName
0x180002ab3  mov     [rsp+290h+lpClass], 0; lpClass
0x180002abc  xor     edx, edx; dwIndex
0x180002abe  mov     [rsp+290h+phkResult], 0; lpReserved
0x180002ac7  mov     [rsp+290h+cchName], 100h
0x180002acf  call    cs:__imp_RegEnumKeyExW
0x180002ad5  mov     edx, 100h; MaxCount
0x180002ada  lea     rcx, [rsp+290h+Name]; Source
0x180002adf  mov     ebx, eax
0x180002ae1  call    cs:__imp_wcsnlen
0x180002ae7  cmp     ebx, 103h
0x180002aed  jz      short loc_180002AF9
0x180002aef  mov     ebx, 800710D3h
0x180002af4  jmp     loc_180002A64
0x180002af9  mov     rcx, [rsp+290h+hKey]; hKey
0x180002afe  lea     r9, [rsp+290h+cchName]; lpcchValueName
0x180002b03  mov     [rsp+290h+lpftLastWriteTime], 0; lpcbData
0x180002b0c  lea     r8, [rsp+290h+Name]; lpValueName
0x180002b11  mov     [rsp+290h+lpcchClass], 0; lpData
0x180002b1a  xor     edx, edx; dwIndex
0x180002b1c  mov     [rsp+290h+lpClass], 0; lpType
0x180002b25  mov     [rsp+290h+phkResult], 0; lpReserved
0x180002b2e  call    cs:__imp_RegEnumValueW
0x180002b34  mov     edx, 100h; MaxCount
0x180002b39  lea     rcx, [rsp+290h+Name]; Source
0x180002b3e  mov     ebx, eax
0x180002b40  call    cs:__imp_wcsnlen
0x180002b46  cmp     ebx, 103h
0x180002b4c  jnz     short loc_180002AEF
0x180002b4e  mov     rcx, [rsp+290h+hKey]; hKey
0x180002b53  xor     ebx, ebx
0x180002b55  test    rcx, rcx
0x180002b58  jz      short loc_180002B65
0x180002b5a  call    cs:__imp_RegCloseKey
0x180002b60  mov     [rsp+290h+hKey], rbx
0x180002b65  mov     rdx, [rdi+10h]; lpSubKey
0x180002b69  mov     rcx, rsi; hKey
0x180002b6c  call    cs:__imp_RegDeleteKeyW
0x180002b72  test    eax, eax
0x180002b74  jz      loc_180002A64
0x180002b7a  jg      loc_180002A5B
0x180002b80  mov     ebx, eax
0x180002b82  jmp     loc_180002A64
```
