# IsV3Property(ushort const *)

- ea: `0x18000e480`
- end: `0x18000e4ee`
- name: `?IsV3Property@@YAHPEBG@Z`
- size: `110`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800315b4`

## callees

- `0x18000e480`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e4c6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e4c6`

## pseudocode

```c
__int64 __fastcall IsV3Property(PCNZWCH lpString1)
{
  unsigned int i; // ebx

  for ( i = 0; ; ++i )
  {
    if ( i >= 6 )
      return 0;
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, (PCNZWCH)*(&g_CTV3Properties + 2 * i), -1) == 2 )
      break;
  }
  return 1;
}

```

## disassembly

```asm
0x18000e480  push    rbx
0x18000e482  push    rbp
0x18000e483  push    rsi
0x18000e484  push    rdi
0x18000e485  sub     rsp, 38h
0x18000e489  xor     esi, esi
0x18000e48b  lea     rbp, ?g_CTV3Properties@@3PAU_CERT_TYPE_PROP_INFO@@A; _CERT_TYPE_PROP_INFO near * g_CTV3Properties
0x18000e492  xor     ebx, ebx
0x18000e494  mov     rdi, rcx
0x18000e497  cmp     ebx, 6
0x18000e49a  jnb     short loc_18000E4D5
0x18000e49c  mov     eax, ebx
0x18000e49e  mov     r9d, 0FFFFFFFFh; cchCount1
0x18000e4a4  add     rax, rax
0x18000e4a7  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000e4af  mov     r8, rdi; lpString1
0x18000e4b2  mov     edx, 1; dwCmpFlags
0x18000e4b7  mov     ecx, 7Fh; Locale
0x18000e4bc  mov     rax, [rbp+rax*8+0]
0x18000e4c1  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e4c6  call    cs:__imp_CompareStringW
0x18000e4cc  cmp     eax, 2
0x18000e4cf  jz      short loc_18000E4E0
0x18000e4d1  inc     ebx
0x18000e4d3  jmp     short loc_18000E497
0x18000e4d5  mov     eax, esi
0x18000e4d7  add     rsp, 38h
0x18000e4db  pop     rdi
0x18000e4dc  pop     rsi
0x18000e4dd  pop     rbp
0x18000e4de  pop     rbx
0x18000e4df  retn
0x18000e4e0  mov     eax, 1
0x18000e4e5  add     rsp, 38h
0x18000e4e9  pop     rdi
0x18000e4ea  pop     rsi
0x18000e4eb  pop     rbp
0x18000e4ec  pop     rbx
0x18000e4ed  retn
```
