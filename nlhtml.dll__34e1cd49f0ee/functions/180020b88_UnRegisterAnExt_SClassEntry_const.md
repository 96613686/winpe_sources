# UnRegisterAnExt(SClassEntry const &)

- ea: `0x180020b88`
- end: `0x180020bed`
- name: `?UnRegisterAnExt@@YAJAEBUSClassEntry@@@Z`
- size: `101`
- prototype: `__int64 __fastcall(const struct SClassEntry *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callers

- `0x18002122c`

## callees

- `0x180020b88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020bdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020bdf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020bb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020bb4`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180020bcc`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180020bcc`

## pseudocode

```c
__int64 __fastcall UnRegisterAnExt(const WCHAR **a1)
{
  const WCHAR *v1; // rdx
  unsigned int v2; // ebx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = *a1;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v2 = RegOpenKeyExW(HKEY_CLASSES_ROOT, v1, 0, 0x2001Fu, &hKey);
  if ( !v2 )
    v2 = RegDeleteKeyW(hKey, L"PersistentHandler");
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x180020b88  push    rbx
0x180020b8a  sub     rsp, 30h
0x180020b8e  mov     rdx, [rcx]; lpSubKey
0x180020b91  lea     rax, [rsp+38h+hKey]
0x180020b96  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180020b9d  mov     [rsp+38h+phkResult], rax; phkResult
0x180020ba2  mov     r9d, 2001Fh; samDesired
0x180020ba8  mov     [rsp+38h+hKey], 0FFFFFFFFFFFFFFFFh
0x180020bb1  xor     r8d, r8d; ulOptions
0x180020bb4  call    cs:__imp_RegOpenKeyExW
0x180020bba  mov     ebx, eax
0x180020bbc  test    eax, eax
0x180020bbe  jnz     short loc_180020BD4
0x180020bc0  mov     rcx, [rsp+38h+hKey]; hKey
0x180020bc5  lea     rdx, SubKey; "PersistentHandler"
0x180020bcc  call    cs:__imp_RegDeleteKeyW
0x180020bd2  mov     ebx, eax
0x180020bd4  mov     rcx, [rsp+38h+hKey]; hKey
0x180020bd9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180020bdd  jz      short loc_180020BE5
0x180020bdf  call    cs:__imp_RegCloseKey
0x180020be5  mov     eax, ebx
0x180020be7  add     rsp, 30h
0x180020beb  pop     rbx
0x180020bec  retn
```
