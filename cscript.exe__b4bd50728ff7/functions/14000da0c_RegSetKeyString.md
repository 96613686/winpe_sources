# RegSetKeyString

- ea: `0x14000da0c`
- end: `0x14000daa7`
- name: `RegSetKeyString`
- size: `155`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140007c74`
- `0x14000dab0`

## callees

- `0x14000da0c`

## import_xrefs

- `ADVAPI32!RegSetValueExA` at `0x14000da7a`
- `ADVAPI32!RegSetValueExA` at `0x14000da7a`
- `ADVAPI32!RegOpenKeyExA` at `0x14000da38`
- `ADVAPI32!RegOpenKeyExA` at `0x14000da38`
- `ADVAPI32!RegCloseKey` at `0x14000da87`
- `ADVAPI32!RegCloseKey` at `0x14000da87`

## pseudocode

```c
__int64 __fastcall RegSetKeyString(HKEY a1, const CHAR *a2, __int64 a3, const BYTE *a4)
{
  LSTATUS v5; // ebx
  __int64 v6; // rax
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  v5 = RegOpenKeyExA(a1, a2, 0, 0x20006u, &hKey);
  if ( !v5 )
  {
    if ( a4 )
    {
      v6 = -1;
      do
        ++v6;
      while ( a4[v6] );
    }
    else
    {
      LODWORD(v6) = 0;
    }
    v5 = RegSetValueExA(hKey, byte_140019BD0, 0, 1u, a4, v6 + 1);
    RegCloseKey(hKey);
  }
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000da0c  mov     r11, rsp
0x14000da0f  mov     [r11+8], rbx
0x14000da13  mov     [r11+18h], r8
0x14000da17  push    rdi
0x14000da18  sub     rsp, 30h
0x14000da1c  mov     rdi, r9
0x14000da1f  mov     qword ptr [r11+18h], 0
0x14000da27  lea     rax, [r11+18h]
0x14000da2b  mov     r9d, 20006h; samDesired
0x14000da31  xor     r8d, r8d; ulOptions
0x14000da34  mov     [r11-18h], rax
0x14000da38  call    cs:__imp_RegOpenKeyExA
0x14000da3e  mov     ebx, eax
0x14000da40  test    eax, eax
0x14000da42  jnz     short loc_14000DA8D
0x14000da44  test    rdi, rdi
0x14000da47  jz      short loc_14000DA58
0x14000da49  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000da4d  inc     rax
0x14000da50  cmp     byte ptr [rdi+rax], 0
0x14000da54  jnz     short loc_14000DA4D
0x14000da56  jmp     short loc_14000DA5A
0x14000da58  xor     eax, eax
0x14000da5a  mov     rcx, [rsp+38h+hKey]; hKey
0x14000da5f  lea     rdx, byte_140019BD0; lpValueName
0x14000da66  inc     eax
0x14000da68  mov     r9d, 1; dwType
0x14000da6e  mov     [rsp+38h+cbData], eax; cbData
0x14000da72  xor     r8d, r8d; Reserved
0x14000da75  mov     [rsp+38h+lpData], rdi; lpData
0x14000da7a  call    cs:__imp_RegSetValueExA
0x14000da80  mov     rcx, [rsp+38h+hKey]; hKey
0x14000da85  mov     ebx, eax
0x14000da87  call    cs:__imp_RegCloseKey
0x14000da8d  test    ebx, ebx
0x14000da8f  jle     short loc_14000DA9A
0x14000da91  movzx   ebx, bx
0x14000da94  or      ebx, 80070000h
0x14000da9a  mov     eax, ebx
0x14000da9c  mov     rbx, [rsp+38h+arg_0]
0x14000daa1  add     rsp, 30h
0x14000daa5  pop     rdi
0x14000daa6  retn
```
