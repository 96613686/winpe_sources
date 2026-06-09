# CompareUnicodeStrings

- ea: `0x1800442a4`
- end: `0x1800442f6`
- name: `CompareUnicodeStrings`
- size: `82`
- prototype: `__int64 __fastcall(PCNZWCH lpString2, PCNZWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800455b0`

## callees

- `0x1800442a4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800442cc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800442cc`

## pseudocode

```c
__int64 __fastcall CompareUnicodeStrings(PCNZWCH lpString2, PCNZWCH lpString1, int a3)
{
  unsigned int v3; // ebx
  int v4; // eax

  v3 = -1;
  v4 = CompareStringW(0x7Fu, a3 != 0, lpString1, -1, lpString2, -1) - 1;
  if ( v4 )
    return v4 == 2;
  return v3;
}

```

## disassembly

```asm
0x1800442a4  push    rbx
0x1800442a6  sub     rsp, 30h
0x1800442aa  mov     rax, rdx
0x1800442ad  xor     edx, edx
0x1800442af  test    r8d, r8d
0x1800442b2  mov     r8, rax; lpString1
0x1800442b5  setnz   dl; dwCmpFlags
0x1800442b8  or      ebx, 0FFFFFFFFh
0x1800442bb  mov     [rsp+38h+cchCount2], ebx; cchCount2
0x1800442bf  mov     r9d, ebx; cchCount1
0x1800442c2  mov     [rsp+38h+lpString2], rcx; lpString2
0x1800442c7  mov     ecx, 7Fh; Locale
0x1800442cc  call    cs:__imp_CompareStringW
0x1800442d3  nop     dword ptr [rax+rax+00h]
0x1800442d8  sub     eax, 1
0x1800442db  jz      short loc_1800442ED
0x1800442dd  sub     eax, 1
0x1800442e0  jz      short loc_1800442EB
0x1800442e2  cmp     eax, 1
0x1800442e5  jnz     short loc_1800442EB
0x1800442e7  mov     ebx, eax
0x1800442e9  jmp     short loc_1800442ED
0x1800442eb  xor     ebx, ebx
0x1800442ed  mov     eax, ebx
0x1800442ef  add     rsp, 30h
0x1800442f3  pop     rbx
0x1800442f4  retn
```
