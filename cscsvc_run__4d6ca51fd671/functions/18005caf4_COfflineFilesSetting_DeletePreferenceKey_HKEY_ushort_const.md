# COfflineFilesSetting::_DeletePreferenceKey(HKEY__ *,ushort const *)

- ea: `0x18005caf4`
- end: `0x18005cb7c`
- name: `?_DeletePreferenceKey@COfflineFilesSetting@@AEAAJPEAUHKEY__@@PEBG@Z`
- size: `136`
- prototype: `__int64 __fastcall(COfflineFilesSetting *this, HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18005bd80`

## callees

- `0x18005caf4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18005cb20`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18005cb20`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cb57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005cb57`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005cb46`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005cb46`

## pseudocode

```c
__int64 __fastcall COfflineFilesSetting::_DeletePreferenceKey(
        COfflineFilesSetting *this,
        HKEY a2,
        const unsigned __int16 *a3)
{
  HKEY v4; // rax
  LSTATUS v5; // ebx
  int v6; // edi
  HKEY hKey; // [rsp+38h] [rbp+10h] BYREF

  hKey = a2;
  v4 = a2;
  if ( a2 == HKEY_CURRENT_USER )
  {
    v5 = RegOpenCurrentUser(0x20006u, &hKey);
    v6 = 1;
    if ( v5 )
      goto LABEL_7;
    v4 = hKey;
  }
  else
  {
    v6 = 0;
  }
  v5 = RegDeleteKeyExW(v4, a3, 0, 0);
  if ( v6 )
    RegCloseKey(hKey);
LABEL_7:
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005caf4  mov     r11, rsp
0x18005caf7  mov     [r11+8], rbx
0x18005cafb  mov     [r11+18h], rsi
0x18005caff  mov     [r11+10h], rdx
0x18005cb03  push    rdi
0x18005cb04  sub     rsp, 20h
0x18005cb08  mov     rsi, r8
0x18005cb0b  mov     rax, rdx
0x18005cb0e  cmp     rdx, 0FFFFFFFF80000001h
0x18005cb15  jnz     short loc_18005CB38
0x18005cb17  lea     rdx, [r11+10h]; phkResult
0x18005cb1b  mov     ecx, 20006h; samDesired
0x18005cb20  call    cs:__imp_RegOpenCurrentUser
0x18005cb26  mov     ebx, eax
0x18005cb28  mov     edi, 1
0x18005cb2d  test    eax, eax
0x18005cb2f  jnz     short loc_18005CB5D
0x18005cb31  mov     rax, [rsp+28h+hKey]
0x18005cb36  jmp     short loc_18005CB3A
0x18005cb38  xor     edi, edi
0x18005cb3a  xor     r9d, r9d; Reserved
0x18005cb3d  xor     r8d, r8d; samDesired
0x18005cb40  mov     rdx, rsi; lpSubKey
0x18005cb43  mov     rcx, rax; hKey
0x18005cb46  call    cs:__imp_RegDeleteKeyExW
0x18005cb4c  mov     ebx, eax
0x18005cb4e  test    edi, edi
0x18005cb50  jz      short loc_18005CB5D
0x18005cb52  mov     rcx, [rsp+28h+hKey]; hKey
0x18005cb57  call    cs:__imp_RegCloseKey
0x18005cb5d  test    ebx, ebx
0x18005cb5f  jle     short loc_18005CB6A
0x18005cb61  movzx   ebx, bx
0x18005cb64  or      ebx, 80070000h
0x18005cb6a  mov     rsi, [rsp+28h+arg_10]
0x18005cb6f  mov     eax, ebx
0x18005cb71  mov     rbx, [rsp+28h+arg_0]
0x18005cb76  add     rsp, 20h
0x18005cb7a  pop     rdi
0x18005cb7b  retn
```
