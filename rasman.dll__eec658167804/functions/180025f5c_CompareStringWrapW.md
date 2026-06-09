# CompareStringWrapW

- ea: `0x180025f5c`
- end: `0x180025f90`
- name: `CompareStringWrapW`
- size: `52`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180023618`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025f7a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180025f7a`

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
0x180025f5c  push    rbx
0x180025f5e  sub     rsp, 30h
0x180025f62  or      ebx, 0FFFFFFFFh
0x180025f65  mov     r8, rcx; lpString1
0x180025f68  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x180025f6c  mov     r9d, ebx; cchCount1
0x180025f6f  mov     [rsp+38h+lpString2], rdx; lpString2
0x180025f74  lea     edx, [rbx+2]; dwCmpFlags
0x180025f77  lea     ecx, [rdx+7Eh]; Locale
0x180025f7a  call    cs:__imp_CompareStringW
0x180025f80  test    eax, eax
0x180025f82  lea     ecx, [rax-2]
0x180025f85  cmovnz  ebx, ecx
0x180025f88  mov     eax, ebx
0x180025f8a  add     rsp, 30h
0x180025f8e  pop     rbx
0x180025f8f  retn
```
