# _UnicodeStringStringHijack

- ea: `0x180005648`
- end: `0x180005679`
- name: `_UnicodeStringStringHijack`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e74`
- `0x180005068`

## callees

- `0x180005648`

## pseudocode

```c
__int64 __fastcall UnicodeStringStringHijack(__int64 a1, __int64 a2)
{
  unsigned __int64 v2; // rax
  __int16 v3; // ax

  v2 = -1;
  do
    ++v2;
  while ( *(_WORD *)(a1 + 2 * v2) );
  if ( v2 > 0x7FFF )
    return 2147942934LL;
  v3 = 2 * v2;
  *(_QWORD *)(a2 + 8) = a1;
  *(_WORD *)a2 = v3;
  *(_WORD *)(a2 + 2) = v3;
  return 0;
}

```

## disassembly

```asm
0x180005648  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000564c  xor     r8d, r8d
0x18000564f  inc     rax
0x180005652  cmp     [rcx+rax*2], r8w
0x180005657  jnz     short loc_18000564F
0x180005659  cmp     rax, 7FFFh
0x18000565f  ja      short loc_180005673
0x180005661  add     ax, ax
0x180005664  mov     [rdx+8], rcx
0x180005668  mov     [rdx], ax
0x18000566b  mov     [rdx+2], ax
0x18000566f  mov     eax, r8d
0x180005672  retn
0x180005673  mov     eax, 80070216h
0x180005678  retn
```
