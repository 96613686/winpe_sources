# _PCW_BUFFER::ReserveSpaceVoid(void * *,ulong)

- ea: `0x140008fd0`
- end: `0x140009011`
- name: `?ReserveSpaceVoid@_PCW_BUFFER@@AEAAJPEAPEAXK@Z`
- size: `65`
- prototype: `__int64 __fastcall(_PCW_BUFFER *__hidden this, void **, unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140008224`
- `0x1400082ec`
- `0x1400083e4`
- `0x14000868c`
- `0x140008840`
- `0x140008c48`

## callees

- `0x140008fd0`

## pseudocode

```c
__int64 __fastcall _PCW_BUFFER::ReserveSpaceVoid(_PCW_BUFFER *this, void **a2, unsigned int a3)
{
  unsigned int v6; // edx
  char *v7; // rcx

  *((_DWORD *)this + 3) += a3;
  if ( *((_DWORD *)this + 3) < a3 )
    return 3221225621LL;
  v6 = *((_DWORD *)this + 2);
  if ( v6 >= a3 )
  {
    v7 = *(char **)this;
    *a2 = v7;
    *(_QWORD *)this = &v7[a3];
    *((_DWORD *)this + 2) = v6 - a3;
  }
  else
  {
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x140008fd0  add     [rcx+0Ch], r8d
0x140008fd4  mov     r10, rdx
0x140008fd7  mov     r9, rcx
0x140008fda  cmp     [rcx+0Ch], r8d
0x140008fde  jnb     short loc_140008FE7
0x140008fe0  mov     eax, 0C0000095h
0x140008fe5  retn
0x140008fe7  mov     edx, [rcx+8]
0x140008fea  cmp     edx, r8d
0x140008fed  jnb     short loc_140008FF8
0x140008fef  mov     qword ptr [r10], 0
0x140008ff6  jmp     short loc_14000900E
0x140008ff8  mov     rcx, [rcx]
0x140008ffb  mov     eax, r8d
0x140008ffe  add     rax, rcx
0x140009001  mov     [r10], rcx
0x140009004  sub     edx, r8d
0x140009007  mov     [r9], rax
0x14000900a  mov     [r9+8], edx
0x14000900e  xor     eax, eax
0x140009010  retn
```
