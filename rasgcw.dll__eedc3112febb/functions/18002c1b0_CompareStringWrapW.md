# CompareStringWrapW

- ea: `0x18002c1b0`
- end: `0x18002c1e4`
- name: `CompareStringWrapW`
- size: `52`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180010884`
- `0x180013330`
- `0x18001a480`
- `0x18001d51c`
- `0x18001dabc`
- `0x180026b30`
- `0x180026d60`
- `0x1800290a0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c1ce`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002c1ce`

## pseudocode

```c
__int64 __fastcall CompareStringWrapW(PCNZWCH lpString1, PCNZWCH lpString2)
{
  unsigned int v2; // ebx
  int v3; // eax

  v2 = -1;
  v3 = CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1);
  if ( v3 )
    return (unsigned int)(v3 - 2);
  return v2;
}

```

## disassembly

```asm
0x18002c1b0  push    rbx
0x18002c1b2  sub     rsp, 30h
0x18002c1b6  or      ebx, 0FFFFFFFFh
0x18002c1b9  mov     r8, rcx; lpString1
0x18002c1bc  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x18002c1c0  mov     r9d, ebx; cchCount1
0x18002c1c3  mov     [rsp+38h+lpString2], rdx; lpString2
0x18002c1c8  lea     edx, [rbx+2]; dwCmpFlags
0x18002c1cb  lea     ecx, [rdx+7Eh]; Locale
0x18002c1ce  call    cs:__imp_CompareStringW
0x18002c1d4  test    eax, eax
0x18002c1d6  lea     ecx, [rax-2]
0x18002c1d9  cmovnz  ebx, ecx
0x18002c1dc  mov     eax, ebx
0x18002c1de  add     rsp, 30h
0x18002c1e2  pop     rbx
0x18002c1e3  retn
```
