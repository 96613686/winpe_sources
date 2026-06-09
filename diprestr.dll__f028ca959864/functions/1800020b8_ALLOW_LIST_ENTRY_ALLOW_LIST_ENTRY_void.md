# ALLOW_LIST_ENTRY::~ALLOW_LIST_ENTRY(void)

- ea: `0x1800020b8`
- end: `0x180002146`
- name: `??1ALLOW_LIST_ENTRY@@UEAA@XZ`
- size: `142`
- prototype: `void __fastcall(ALLOW_LIST_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002190`

## callees

- `0x1800020b8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800020ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000211e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800020ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000211e`

## pseudocode

```c
void __fastcall ALLOW_LIST_ENTRY::~ALLOW_LIST_ENTRY(ALLOW_LIST_ENTRY *this)
{
  char *v1; // rdi
  char *v3; // rcx
  char *v4; // rcx

  v1 = (char *)this + 140;
  *(_QWORD *)this = &ALLOW_LIST_ENTRY::`vftable';
  *((_QWORD *)this + 14) = &STBUFF::`vftable';
  v3 = (char *)*((_QWORD *)this + 15);
  if ( v3 != v1 )
  {
    LocalFree(v3);
    *((_QWORD *)this + 15) = v1;
    *((_DWORD *)this + 33) = 64;
  }
  *((_DWORD *)this + 32) = 0;
  v4 = (char *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 2) = &STBUFF::`vftable';
  if ( v4 != (char *)this + 44 )
  {
    LocalFree(v4);
    *((_QWORD *)this + 3) = (char *)this + 44;
    *((_DWORD *)this + 9) = 64;
  }
  *((_DWORD *)this + 8) = 0;
}

```

## disassembly

```asm
0x1800020b8  mov     [rsp+arg_0], rbx
0x1800020bd  mov     [rsp+arg_8], rbp
0x1800020c2  push    rdi
0x1800020c3  sub     rsp, 20h
0x1800020c7  lea     rdi, [rcx+8Ch]
0x1800020ce  mov     rbx, rcx
0x1800020d1  lea     rax, ??_7ALLOW_LIST_ENTRY@@6B@; const ALLOW_LIST_ENTRY::`vftable'
0x1800020d8  lea     rbp, ??_7STBUFF@@6B@; const STBUFF::`vftable'
0x1800020df  mov     [rcx], rax
0x1800020e2  mov     [rcx+70h], rbp
0x1800020e6  mov     rcx, [rcx+78h]; hMem
0x1800020ea  cmp     rcx, rdi
0x1800020ed  jz      short loc_180002103
0x1800020ef  call    cs:__imp_LocalFree
0x1800020f5  mov     [rbx+78h], rdi
0x1800020f9  mov     dword ptr [rbx+84h], 40h ; '@'
0x180002103  mov     dword ptr [rbx+80h], 0
0x18000210d  lea     rdi, [rbx+2Ch]
0x180002111  mov     rcx, [rbx+18h]; hMem
0x180002115  mov     [rbx+10h], rbp
0x180002119  cmp     rcx, rdi
0x18000211c  jz      short loc_18000212F
0x18000211e  call    cs:__imp_LocalFree
0x180002124  mov     [rbx+18h], rdi
0x180002128  mov     dword ptr [rbx+24h], 40h ; '@'
0x18000212f  mov     rbp, [rsp+28h+arg_8]
0x180002134  mov     dword ptr [rbx+20h], 0
0x18000213b  mov     rbx, [rsp+28h+arg_0]
0x180002140  add     rsp, 20h
0x180002144  pop     rdi
0x180002145  retn
```
