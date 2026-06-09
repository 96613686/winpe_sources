# __memset_repmovs

- ea: `0x140005300`
- end: `0x140005343`
- name: `__memset_repmovs`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400051c0`

## callees

- `0x140005300`
- `0x140005380`

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
0x140005300  push    rdi
0x140005301  test    cs:__isa_info, 1
0x140005308  jz      short loc_14000533C
0x14000530a  mov     rdi, rcx
0x14000530d  add     r8, rcx
0x140005310  movups  xmmword ptr [rcx], xmm0
0x140005313  add     rdi, 40h ; '@'
0x140005317  movups  xmmword ptr [rcx+10h], xmm0
0x14000531b  and     rdi, 0FFFFFFFFFFFFFFC0h
0x14000531f  movups  xmmword ptr [rcx+20h], xmm0
0x140005323  sub     r8, rdi
0x140005326  movups  xmmword ptr [rcx+30h], xmm0
0x14000532a  mov     rcx, r8
0x14000532d  mov     r9, rax
0x140005330  movq    rax, xmm0
0x140005335  rep stosb
0x140005337  mov     rax, r9
0x14000533a  pop     rdi
0x14000533b  retn
0x14000533c  call    __memset_query
0x140005341  jmp     short loc_14000530A
```
