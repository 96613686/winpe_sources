# MyRegDeleteTree

- ea: `0x18002884c`
- end: `0x18002888f`
- name: `MyRegDeleteTree`
- size: `67`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180023e40`
- `0x180025cb0`
- `0x180028100`

## callees

- `0x18002884c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002887e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002887e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002885c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18002885c`

## pseudocode

```c
LSTATUS __fastcall MyRegDeleteTree(HKEY hKey, LPCWSTR lpSubKey)
{
  LSTATUS result; // eax

  result = RegDeleteTreeW(hKey, lpSubKey);
  if ( !result && (!lpSubKey || !*lpSubKey) )
    return RegDeleteKeyExW(hKey, lpSubKey, 0, 0);
  return result;
}

```

## disassembly

```asm
0x18002884c  mov     [rsp+arg_0], rbx
0x180028851  push    rdi
0x180028852  sub     rsp, 20h
0x180028856  mov     rbx, rdx
0x180028859  mov     rdi, rcx
0x18002885c  call    cs:__imp_RegDeleteTreeW
0x180028862  xor     ecx, ecx
0x180028864  test    eax, eax
0x180028866  jnz     short loc_180028884
0x180028868  test    rbx, rbx
0x18002886b  jz      short loc_180028872
0x18002886d  cmp     [rbx], cx
0x180028870  jnz     short loc_180028884
0x180028872  xor     r9d, r9d; Reserved
0x180028875  xor     r8d, r8d; samDesired
0x180028878  mov     rdx, rbx; lpSubKey
0x18002887b  mov     rcx, rdi; hKey
0x18002887e  call    cs:__imp_RegDeleteKeyExW
0x180028884  mov     rbx, [rsp+28h+arg_0]
0x180028889  add     rsp, 20h
0x18002888d  pop     rdi
0x18002888e  retn
```
