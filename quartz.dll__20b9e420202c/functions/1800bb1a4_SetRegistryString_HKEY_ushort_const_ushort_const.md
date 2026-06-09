# SetRegistryString(HKEY__ *,ushort const *,ushort const *)

- ea: `0x1800bb1a4`
- end: `0x1800bb24b`
- name: `?SetRegistryString@@YAJPEAUHKEY__@@PEBG1@Z`
- size: `167`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800baf30`

## callees

- `0x1800bb1a4`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x1800bb1e6`
- `KERNEL32!lstrlenW` at `0x1800bb1e6`
- `ADVAPI32!RegSetValueExW` at `0x1800bb210`
- `ADVAPI32!RegSetValueExW` at `0x1800bb210`
- `ADVAPI32!RegCreateKeyW` at `0x1800bb1d1`
- `ADVAPI32!RegCreateKeyW` at `0x1800bb1d1`
- `ADVAPI32!RegCloseKey` at `0x1800bb223`
- `ADVAPI32!RegCloseKey` at `0x1800bb223`

## pseudocode

```c
__int64 __fastcall SetRegistryString(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  LSTATUS v4; // ebx
  int v5; // eax
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v4 = RegCreateKeyW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Multimedia\\ActiveMovie Filters\\Video Mixing Renderer",
         &hKey);
  if ( v4 )
    return v4 | 0x80070000;
  v5 = lstrlenW(a3);
  v4 = RegSetValueExW(hKey, L"DDraw Connection Device GUID", 0, 1u, (const BYTE *)a3, 2 * v5);
  RegCloseKey(hKey);
  if ( v4 )
    return v4 | 0x80070000;
  else
    return 0;
}

```

## disassembly

```asm
0x1800bb1a4  mov     rax, rsp
0x1800bb1a7  mov     [rax+8], rbx
0x1800bb1ab  mov     [rax+10h], rdx
0x1800bb1af  push    rdi
0x1800bb1b0  sub     rsp, 30h
0x1800bb1b4  mov     rdi, r8
0x1800bb1b7  mov     qword ptr [rax+10h], 0
0x1800bb1bf  lea     r8, [rax+10h]; phkResult
0x1800bb1c3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bb1ca  lea     rdx, chRegistryKey; "Software\\Microsoft\\Multimedia\\Active"...
0x1800bb1d1  call    cs:__imp_RegCreateKeyW
0x1800bb1d8  nop     dword ptr [rax+rax+00h]
0x1800bb1dd  mov     ebx, eax
0x1800bb1df  test    eax, eax
0x1800bb1e1  jnz     short loc_1800BB237
0x1800bb1e3  mov     rcx, rdi; lpString
0x1800bb1e6  call    cs:__imp_lstrlenW
0x1800bb1ed  nop     dword ptr [rax+rax+00h]
0x1800bb1f2  mov     rcx, [rsp+38h+hKey]; hKey
0x1800bb1f7  lea     r9d, [rbx+1]; dwType
0x1800bb1fb  add     eax, eax
0x1800bb1fd  lea     rdx, aDdrawConnectio; "DDraw Connection Device GUID"
0x1800bb204  mov     [rsp+38h+cbData], eax; cbData
0x1800bb208  xor     r8d, r8d; Reserved
0x1800bb20b  mov     [rsp+38h+lpData], rdi; lpData
0x1800bb210  call    cs:__imp_RegSetValueExW
0x1800bb217  nop     dword ptr [rax+rax+00h]
0x1800bb21c  mov     rcx, [rsp+38h+hKey]; hKey
0x1800bb221  mov     ebx, eax
0x1800bb223  call    cs:__imp_RegCloseKey
0x1800bb22a  nop     dword ptr [rax+rax+00h]
0x1800bb22f  test    ebx, ebx
0x1800bb231  jnz     short loc_1800BB237
0x1800bb233  xor     eax, eax
0x1800bb235  jmp     short loc_1800BB23F
0x1800bb237  or      ebx, 80070000h
0x1800bb23d  mov     eax, ebx
0x1800bb23f  mov     rbx, [rsp+38h+arg_0]
0x1800bb244  add     rsp, 30h
0x1800bb248  pop     rdi
0x1800bb249  retn
```
