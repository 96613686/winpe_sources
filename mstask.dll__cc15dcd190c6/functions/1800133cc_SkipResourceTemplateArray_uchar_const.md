# SkipResourceTemplateArray(uchar const *)

- ea: `0x1800133cc`
- end: `0x1800133fc`
- name: `?SkipResourceTemplateArray@@YAPEBEPEBE@Z`
- size: `48`
- prototype: `const unsigned __int8 *__fastcall(const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012fe8`

## callees

- `0x1800133cc`

## pseudocode

```c
const unsigned __int8 *__fastcall SkipResourceTemplateArray(const unsigned __int8 *a1)
{
  __int64 v2; // rax

  if ( !*(_WORD *)a1 )
    return a1 + 2;
  if ( *(_WORD *)a1 != 0xFFFF )
  {
    v2 = -1;
    do
      ++v2;
    while ( *(_WORD *)&a1[2 * v2] );
    a1 += 2 * v2;
    return a1 + 2;
  }
  return a1 + 4;
}

```

## disassembly

```asm
0x1800133cc  cmp     word ptr [rcx], 0
0x1800133d0  jz      short loc_1800133F4
0x1800133d2  mov     eax, 0FFFFh
0x1800133d7  cmp     [rcx], ax
0x1800133da  jnz     short loc_1800133E2
0x1800133dc  add     rcx, 4
0x1800133e0  jmp     short loc_1800133F8
0x1800133e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800133e6  inc     rax
0x1800133e9  cmp     word ptr [rcx+rax*2], 0
0x1800133ee  jnz     short loc_1800133E6
0x1800133f0  lea     rcx, [rcx+rax*2]
0x1800133f4  add     rcx, 2
0x1800133f8  mov     rax, rcx
0x1800133fb  retn
```
