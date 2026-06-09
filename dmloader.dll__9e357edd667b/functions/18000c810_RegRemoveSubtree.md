# RegRemoveSubtree

- ea: `0x18000c810`
- end: `0x18000c8bb`
- name: `RegRemoveSubtree`
- size: `171`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000c810`
- `0x18000cca0`

## callees

- `0x1800015d0`
- `0x18000c810`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c888`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c888`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000c851`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18000c851`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyA` at `0x18000c879`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyA` at `0x18000c879`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x18000c894`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x18000c894`

## pseudocode

```c
LSTATUS __fastcall RegRemoveSubtree(HKEY a1, const CHAR *a2)
{
  LSTATUS result; // eax
  HKEY hKey; // [rsp+30h] [rbp-128h] BYREF
  CHAR Name[256]; // [rsp+40h] [rbp-118h] BYREF

  hKey = 0;
  result = RegOpenKeyExA(a1, a2, 0, 0xF003Fu, &hKey);
  if ( !result )
  {
    while ( !RegEnumKeyA(hKey, 0, Name, 0x100u) )
      RegRemoveSubtree(hKey, Name);
    RegCloseKey(hKey);
    return RegDeleteKeyA(a1, a2);
  }
  return result;
}

```

## disassembly

```asm
0x18000c810  mov     [rsp+arg_10], rbx
0x18000c815  push    rdi
0x18000c816  sub     rsp, 150h
0x18000c81d  mov     rax, cs:__security_cookie
0x18000c824  xor     rax, rsp
0x18000c827  mov     [rsp+158h+var_18], rax
0x18000c82f  lea     rax, [rsp+158h+hKey]
0x18000c834  mov     [rsp+158h+hKey], 0
0x18000c83d  mov     r9d, 0F003Fh; samDesired
0x18000c843  mov     [rsp+158h+phkResult], rax; phkResult
0x18000c848  xor     r8d, r8d; ulOptions
0x18000c84b  mov     rdi, rdx
0x18000c84e  mov     rbx, rcx
0x18000c851  call    cs:__imp_RegOpenKeyExA
0x18000c857  test    eax, eax
0x18000c859  jnz     short loc_18000C89A
0x18000c85b  jmp     short loc_18000C867
0x18000c85d  lea     rdx, [rsp+158h+Name]
0x18000c862  call    RegRemoveSubtree
0x18000c867  mov     rcx, [rsp+158h+hKey]; hKey
0x18000c86c  lea     r8, [rsp+158h+Name]; lpName
0x18000c871  mov     r9d, 100h; cchName
0x18000c877  xor     edx, edx; dwIndex
0x18000c879  call    cs:__imp_RegEnumKeyA
0x18000c87f  mov     rcx, [rsp+158h+hKey]; hKey
0x18000c884  test    eax, eax
0x18000c886  jz      short loc_18000C85D
0x18000c888  call    cs:__imp_RegCloseKey
0x18000c88e  mov     rdx, rdi; lpSubKey
0x18000c891  mov     rcx, rbx; hKey
0x18000c894  call    cs:__imp_RegDeleteKeyA
0x18000c89a  mov     rcx, [rsp+158h+var_18]
0x18000c8a2  xor     rcx, rsp; StackCookie
0x18000c8a5  call    __security_check_cookie
0x18000c8aa  mov     rbx, [rsp+158h+arg_10]
0x18000c8b2  add     rsp, 150h
0x18000c8b9  pop     rdi
0x18000c8ba  retn
```
