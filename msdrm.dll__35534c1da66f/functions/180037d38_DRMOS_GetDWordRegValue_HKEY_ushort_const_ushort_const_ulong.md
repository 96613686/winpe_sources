# DRMOS::GetDWordRegValue(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x180037d38`
- end: `0x180037e10`
- name: `?GetDWordRegValue@DRMOS@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `216`
- prototype: `__int64 __fastcall(DRMOS *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044088`

## callees

- `0x180037d38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037e01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037e01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037d90`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037d90`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037dd4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037dd4`

## pseudocode

```c
__int64 __fastcall DRMOS::GetDWordRegValue(
        DRMOS *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  bool v6; // cc
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+20h] BYREF
  int v10; // [rsp+5Ch] [rbp+24h]
  DWORD Type; // [rsp+60h] [rbp+28h] BYREF
  int v12; // [rsp+64h] [rbp+2Ch]
  DWORD cbData; // [rsp+68h] [rbp+30h] BYREF
  int v14; // [rsp+6Ch] [rbp+34h]

  v14 = HIDWORD(a4);
  v12 = HIDWORD(a3);
  v10 = HIDWORD(a2);
  hKey = 0;
  Type = 0;
  cbData = 0;
  Data = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\MSDRM\\Federation", 0, 0x20019u, &hKey);
  v5 = v4;
  v6 = v4 <= 0;
  if ( v4
    || (cbData = 4,
        v4 = RegQueryValueExW(hKey, L"EnableBrowser", 0, &Type, (LPBYTE)&Data, &cbData),
        v5 = v4,
        v6 = v4 <= 0,
        v4) )
  {
    if ( !v6 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  else if ( Type == 4 )
  {
    v5 = 0;
    g_dwBrowserEnabled = Data;
  }
  else
  {
    v5 = -2147024809;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v5;
}

```

## disassembly

```asm
0x180037d38  mov     r11, rsp
0x180037d3b  mov     [r11+20h], r9
0x180037d3f  mov     [r11+18h], r8
0x180037d43  mov     [r11+10h], rdx
0x180037d47  mov     [r11+8], rcx
0x180037d4b  push    rbp
0x180037d4c  push    rbx
0x180037d4d  mov     rbp, rsp
0x180037d50  sub     rsp, 38h
0x180037d54  lea     rax, [rbp+hKey]
0x180037d58  mov     [rbp+hKey], 0
0x180037d60  mov     r9d, 20019h; samDesired
0x180037d66  mov     [r11-28h], rax
0x180037d6a  xor     r8d, r8d; ulOptions
0x180037d6d  mov     [rbp+Type], 0
0x180037d74  lea     rdx, ?g_wszMSDRMFederationKey@@3QBGB; "SOFTWARE\\Microsoft\\MSDRM\\Federation"
0x180037d7b  mov     [rbp+cbData], 0
0x180037d82  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037d89  mov     [rbp+Data], 0
0x180037d90  call    cs:__imp_RegOpenKeyExW
0x180037d96  mov     ebx, eax
0x180037d98  test    eax, eax
0x180037d9a  jz      short loc_180037DA9
0x180037d9c  jle     short loc_180037DF8
0x180037d9e  movzx   ebx, ax
0x180037da1  or      ebx, 80070000h
0x180037da7  jmp     short loc_180037DF8
0x180037da9  mov     rcx, [rbp+hKey]; hKey
0x180037dad  lea     rax, [rbp+cbData]
0x180037db1  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180037db6  lea     r9, [rbp+Type]; lpType
0x180037dba  lea     rax, [rbp+Data]
0x180037dbe  mov     [rbp+cbData], 4
0x180037dc5  xor     r8d, r8d; lpReserved
0x180037dc8  mov     [rsp+38h+lpData], rax; lpData
0x180037dcd  lea     rdx, ?g_wszBrowserEnabledKey@@3QBGB; "EnableBrowser"
0x180037dd4  call    cs:__imp_RegQueryValueExW
0x180037dda  mov     ebx, eax
0x180037ddc  test    eax, eax
0x180037dde  jnz     short loc_180037D9C
0x180037de0  cmp     [rbp+Type], 4
0x180037de4  jz      short loc_180037DED
0x180037de6  mov     ebx, 80070057h
0x180037deb  jmp     short loc_180037DF8
0x180037ded  mov     ecx, [rbp+Data]
0x180037df0  xor     ebx, ebx
0x180037df2  mov     cs:?g_dwBrowserEnabled@@3KA, ecx; ulong g_dwBrowserEnabled
0x180037df8  mov     rcx, [rbp+hKey]; hKey
0x180037dfc  test    rcx, rcx
0x180037dff  jz      short loc_180037E07
0x180037e01  call    cs:__imp_RegCloseKey
0x180037e07  mov     eax, ebx
0x180037e09  add     rsp, 38h
0x180037e0d  pop     rbx
0x180037e0e  pop     rbp
0x180037e0f  retn
```
