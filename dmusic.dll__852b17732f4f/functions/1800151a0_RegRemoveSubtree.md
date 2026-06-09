# RegRemoveSubtree

- ea: `0x1800151a0`
- end: `0x18001524b`
- name: `RegRemoveSubtree`
- size: `171`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800151a0`
- `0x180015630`

## callees

- `0x1800016d0`
- `0x1800151a0`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegEnumKeyA` at `0x180015209`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyA` at `0x180015209`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x180015224`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x180015224`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800151e1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800151e1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015218`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015218`

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
0x1800151a0  mov     [rsp+arg_10], rbx
0x1800151a5  push    rdi
0x1800151a6  sub     rsp, 150h
0x1800151ad  mov     rax, cs:__security_cookie
0x1800151b4  xor     rax, rsp
0x1800151b7  mov     [rsp+158h+var_18], rax
0x1800151bf  lea     rax, [rsp+158h+hKey]
0x1800151c4  mov     [rsp+158h+hKey], 0
0x1800151cd  mov     r9d, 0F003Fh; samDesired
0x1800151d3  mov     [rsp+158h+phkResult], rax; phkResult
0x1800151d8  xor     r8d, r8d; ulOptions
0x1800151db  mov     rdi, rdx
0x1800151de  mov     rbx, rcx
0x1800151e1  call    cs:__imp_RegOpenKeyExA
0x1800151e7  test    eax, eax
0x1800151e9  jnz     short loc_18001522A
0x1800151eb  jmp     short loc_1800151F7
0x1800151ed  lea     rdx, [rsp+158h+Name]
0x1800151f2  call    RegRemoveSubtree
0x1800151f7  mov     rcx, [rsp+158h+hKey]; hKey
0x1800151fc  lea     r8, [rsp+158h+Name]; lpName
0x180015201  mov     r9d, 100h; cchName
0x180015207  xor     edx, edx; dwIndex
0x180015209  call    cs:__imp_RegEnumKeyA
0x18001520f  mov     rcx, [rsp+158h+hKey]; hKey
0x180015214  test    eax, eax
0x180015216  jz      short loc_1800151ED
0x180015218  call    cs:__imp_RegCloseKey
0x18001521e  mov     rdx, rdi; lpSubKey
0x180015221  mov     rcx, rbx; hKey
0x180015224  call    cs:__imp_RegDeleteKeyA
0x18001522a  mov     rcx, [rsp+158h+var_18]
0x180015232  xor     rcx, rsp; StackCookie
0x180015235  call    __security_check_cookie
0x18001523a  mov     rbx, [rsp+158h+arg_10]
0x180015242  add     rsp, 150h
0x180015249  pop     rdi
0x18001524a  retn
```
