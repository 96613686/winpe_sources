# __memset_repmovs

- ea: `0x140002a80`
- end: `0x140002ac3`
- name: `__memset_repmovs`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140002940`

## callees

- `0x140002a80`
- `0x140002b00`

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
0x140002a80  push    rdi
0x140002a81  test    cs:__isa_info, 1
0x140002a88  jz      short loc_140002ABC
0x140002a8a  mov     rdi, rcx
0x140002a8d  add     r8, rcx
0x140002a90  movups  xmmword ptr [rcx], xmm0
0x140002a93  add     rdi, 40h ; '@'
0x140002a97  movups  xmmword ptr [rcx+10h], xmm0
0x140002a9b  and     rdi, 0FFFFFFFFFFFFFFC0h
0x140002a9f  movups  xmmword ptr [rcx+20h], xmm0
0x140002aa3  sub     r8, rdi
0x140002aa6  movups  xmmword ptr [rcx+30h], xmm0
0x140002aaa  mov     rcx, r8
0x140002aad  mov     r9, rax
0x140002ab0  movq    rax, xmm0
0x140002ab5  rep stosb
0x140002ab7  mov     rax, r9
0x140002aba  pop     rdi
0x140002abb  retn
0x140002abc  call    __memset_query
0x140002ac1  jmp     short loc_140002A8A
```
