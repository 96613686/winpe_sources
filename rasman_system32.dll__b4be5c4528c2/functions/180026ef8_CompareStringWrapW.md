# CompareStringWrapW

- ea: `0x180026ef8`
- end: `0x180026f33`
- name: `CompareStringWrapW`
- size: `59`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180024290`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026f16`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026f16`

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
0x180026ef8  push    rbx
0x180026efa  sub     rsp, 30h
0x180026efe  or      ebx, 0FFFFFFFFh
0x180026f01  mov     r8, rcx; lpString1
0x180026f04  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x180026f08  mov     r9d, ebx; cchCount1
0x180026f0b  mov     [rsp+38h+lpString2], rdx; lpString2
0x180026f10  lea     edx, [rbx+2]; dwCmpFlags
0x180026f13  lea     ecx, [rdx+7Eh]; Locale
0x180026f16  call    cs:__imp_CompareStringW
0x180026f1d  nop     dword ptr [rax+rax+00h]
0x180026f22  test    eax, eax
0x180026f24  lea     ecx, [rax-2]
0x180026f27  cmovnz  ebx, ecx
0x180026f2a  mov     eax, ebx
0x180026f2c  add     rsp, 30h
0x180026f30  pop     rbx
0x180026f31  retn
```
