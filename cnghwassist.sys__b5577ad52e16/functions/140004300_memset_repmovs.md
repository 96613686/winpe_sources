# __memset_repmovs

- ea: `0x140004300`
- end: `0x140004343`
- name: `__memset_repmovs`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400041c0`

## callees

- `0x140004300`
- `0x140004380`

## pseudocode

```c
__int64 __fastcall _memset_repmovs(_OWORD *a1, __int64 a2, __int64 a3)
{
  __int128 v3; // xmm0
  __int64 result; // rax

  if ( (_isa_info & 1) == 0 )
    result = _memset_query();
  *a1 = v3;
  a1[1] = v3;
  a1[2] = v3;
  a1[3] = v3;
  memset(
    (void *)((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL),
    v3,
    (unsigned __int64)a1 + a3 - ((unsigned __int64)(a1 + 4) & 0xFFFFFFFFFFFFFFC0uLL));
  return result;
}

```

## disassembly

```asm
0x140004300  push    rdi
0x140004301  test    cs:__isa_info, 1
0x140004308  jz      short loc_14000433C
0x14000430a  mov     rdi, rcx
0x14000430d  add     r8, rcx
0x140004310  movups  xmmword ptr [rcx], xmm0
0x140004313  add     rdi, 40h ; '@'
0x140004317  movups  xmmword ptr [rcx+10h], xmm0
0x14000431b  and     rdi, 0FFFFFFFFFFFFFFC0h
0x14000431f  movups  xmmword ptr [rcx+20h], xmm0
0x140004323  sub     r8, rdi
0x140004326  movups  xmmword ptr [rcx+30h], xmm0
0x14000432a  mov     rcx, r8
0x14000432d  mov     r9, rax
0x140004330  movq    rax, xmm0
0x140004335  rep stosb
0x140004337  mov     rax, r9
0x14000433a  pop     rdi
0x14000433b  retn
0x14000433c  call    __memset_query
0x140004341  jmp     short loc_14000430A
```
