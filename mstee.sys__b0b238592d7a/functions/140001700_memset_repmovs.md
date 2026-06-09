# __memset_repmovs

- ea: `0x140001700`
- end: `0x140001743`
- name: `__memset_repmovs`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400015c0`

## callees

- `0x140001700`
- `0x140001780`

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
0x140001700  push    rdi
0x140001701  test    cs:__isa_info, 1
0x140001708  jz      short loc_14000173C
0x14000170a  mov     rdi, rcx
0x14000170d  add     r8, rcx
0x140001710  movups  xmmword ptr [rcx], xmm0
0x140001713  add     rdi, 40h ; '@'
0x140001717  movups  xmmword ptr [rcx+10h], xmm0
0x14000171b  and     rdi, 0FFFFFFFFFFFFFFC0h
0x14000171f  movups  xmmword ptr [rcx+20h], xmm0
0x140001723  sub     r8, rdi
0x140001726  movups  xmmword ptr [rcx+30h], xmm0
0x14000172a  mov     rcx, r8
0x14000172d  mov     r9, rax
0x140001730  movq    rax, xmm0
0x140001735  rep stosb
0x140001737  mov     rax, r9
0x14000173a  pop     rdi
0x14000173b  retn
0x14000173c  call    __memset_query
0x140001741  jmp     short loc_14000170A
```
