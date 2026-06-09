# MidlCopyString(ushort const *,ushort * *)

- ea: `0x140019db0`
- end: `0x140019e0a`
- name: `?MidlCopyString@@YAJPEBGPEAPEAG@Z`
- size: `90`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int8 **)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000da80`
- `0x14000f074`
- `0x14000faa8`
- `0x140019b20`
- `0x14001a0e0`
- `0x14001a208`

## callees

- `0x140019ac8`
- `0x140019db0`

## pseudocode

```c
__int64 __fastcall MidlCopyString(unsigned __int8 *a1, unsigned __int8 **a2)
{
  unsigned __int8 *v2; // rax
  __int64 v3; // r8
  __int64 result; // rax

  if ( !a1 )
    return 2147942487LL;
  v2 = a1;
  v3 = 0x7FFFFFFF;
  do
  {
    if ( !*(_WORD *)v2 )
      break;
    v2 += 2;
    --v3;
  }
  while ( v3 );
  result = v3 == 0 ? 0x80070057 : 0;
  if ( v3 )
    return MidlCopyBuffer(a1, ((2 * (0x7FFFFFFF - v3)) & -(__int64)(v3 != 0)) + 2, a2);
  return result;
}

```

## disassembly

```asm
0x140019db0  mov     r10, rdx
0x140019db3  xor     edx, edx
0x140019db5  test    rcx, rcx
0x140019db8  jz      short loc_140019E04
0x140019dba  mov     r9d, 7FFFFFFFh
0x140019dc0  mov     rax, rcx
0x140019dc3  mov     r8d, r9d
0x140019dc6  cmp     [rax], dx
0x140019dc9  jz      short loc_140019DD5
0x140019dcb  add     rax, 2
0x140019dcf  sub     r8, 1
0x140019dd3  jnz     short loc_140019DC6
0x140019dd5  mov     rax, r8
0x140019dd8  neg     rax
0x140019ddb  sbb     eax, eax
0x140019ddd  not     eax
0x140019ddf  and     eax, 80070057h
0x140019de4  test    r8, r8
0x140019de7  jz      short locret_140019E09
0x140019de9  sub     r9, r8
0x140019dec  add     r9, r9
0x140019def  neg     r8
0x140019df2  mov     r8, r10; unsigned __int8 **
0x140019df5  sbb     rdx, rdx
0x140019df8  and     rdx, r9
0x140019dfb  add     rdx, 2; Size
0x140019dff  jmp     ?MidlCopyBuffer@@YAJPEAE_KPEAPEAE@Z; MidlCopyBuffer(uchar *,unsigned __int64,uchar * *)
0x140019e04  mov     eax, 80070057h
0x140019e09  retn
```
