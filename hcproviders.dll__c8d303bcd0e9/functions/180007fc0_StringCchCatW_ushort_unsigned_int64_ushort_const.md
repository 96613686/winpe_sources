# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180007fc0`
- end: `0x180008037`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `119`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000692c`
- `0x180008098`

## callees

- `0x180007fc0`
- `0x180008040`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  __int64 v4; // r9
  unsigned __int16 *v5; // rax
  size_t *v6; // r8
  __int64 v7; // r10
  size_t v9; // [rsp+20h] [rbp-18h]

  v4 = 260;
  v5 = a1;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  v6 = v4 == 0 ? (size_t *)0x80070057LL : 0LL;
  if ( v4 )
  {
    v7 = (260 - v4) & -(__int64)(v4 != 0);
    LODWORD(v6) = StringCopyWorkerW(&a1[v7], 260 - v7, v6, a3, v9);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180007fc0  mov     [rsp+arg_0], rbx
0x180007fc5  push    rdi
0x180007fc6  sub     rsp, 30h
0x180007fca  mov     edx, 104h
0x180007fcf  mov     rbx, r8
0x180007fd2  mov     r9d, edx
0x180007fd5  mov     r11, rcx
0x180007fd8  mov     rax, rcx
0x180007fdb  xor     edi, edi
0x180007fdd  cmp     [rax], di
0x180007fe0  jz      short loc_180007FEC
0x180007fe2  add     rax, 2
0x180007fe6  sub     r9, 1
0x180007fea  jnz     short loc_180007FDD
0x180007fec  mov     rax, r9
0x180007fef  mov     rcx, rdx
0x180007ff2  neg     rax
0x180007ff5  mov     rax, r9
0x180007ff8  sbb     r8d, r8d
0x180007ffb  sub     rcx, r9
0x180007ffe  not     r8d
0x180008001  and     r8d, 80070057h; pcchNewDestLength
0x180008008  neg     rax
0x18000800b  sbb     r10, r10
0x18000800e  and     r10, rcx
0x180008011  test    r9, r9
0x180008014  jz      short loc_180008028
0x180008016  sub     rdx, r10; cchDest
0x180008019  lea     rcx, [r11+r10*2]; pszDest
0x18000801d  mov     r9, rbx; pszSrc
0x180008020  call    StringCopyWorkerW
0x180008025  mov     r8d, eax
0x180008028  mov     rbx, [rsp+38h+arg_0]
0x18000802d  mov     eax, r8d
0x180008030  add     rsp, 30h
0x180008034  pop     rdi
0x180008035  retn
```
