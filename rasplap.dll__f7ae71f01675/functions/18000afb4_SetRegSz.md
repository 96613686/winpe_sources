# SetRegSz

- ea: `0x18000afb4`
- end: `0x18000b018`
- name: `SetRegSz`
- size: `100`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180009eac`
- `0x18000a4f0`

## import_xrefs

- `KERNEL32!RegSetValueExW` at `0x18000b002`
- `KERNEL32!RegSetValueExW` at `0x18000b002`
- `KERNEL32!lstrlenW` at `0x18000afdd`
- `KERNEL32!lstrlenW` at `0x18000afdd`

## pseudocode

```c
LSTATUS __fastcall SetRegSz(HKEY hKey, LPCWSTR lpValueName, const WCHAR *a3)
{
  const WCHAR *lpData; // rbx
  int v6; // eax

  lpData = a3;
  if ( !a3 )
    lpData = &Data;
  v6 = lstrlenW(lpData);
  return RegSetValueExW(hKey, lpValueName, 0, 1u, (const BYTE *)lpData, 2 * v6 + 2);
}

```

## disassembly

```asm
0x18000afb4  mov     [rsp+arg_0], rbx
0x18000afb9  mov     [rsp+arg_8], rsi
0x18000afbe  push    rdi
0x18000afbf  sub     rsp, 30h
0x18000afc3  test    r8, r8
0x18000afc6  lea     rax, Data
0x18000afcd  mov     rbx, r8
0x18000afd0  mov     rsi, rcx
0x18000afd3  cmovz   rbx, rax
0x18000afd7  mov     rdi, rdx
0x18000afda  mov     rcx, rbx; lpString
0x18000afdd  call    cs:__imp_lstrlenW
0x18000afe3  mov     r9d, 1; dwType
0x18000afe9  xor     r8d, r8d; Reserved
0x18000afec  mov     rdx, rdi; lpValueName
0x18000afef  mov     rcx, rsi; hKey
0x18000aff2  lea     eax, ds:2[rax*2]
0x18000aff9  mov     [rsp+38h+cbData], eax; cbData
0x18000affd  mov     [rsp+38h+lpData], rbx; lpData
0x18000b002  call    cs:__imp_RegSetValueExW
0x18000b008  mov     rbx, [rsp+38h+arg_0]
0x18000b00d  mov     rsi, [rsp+38h+arg_8]
0x18000b012  add     rsp, 30h
0x18000b016  pop     rdi
0x18000b017  retn
```
