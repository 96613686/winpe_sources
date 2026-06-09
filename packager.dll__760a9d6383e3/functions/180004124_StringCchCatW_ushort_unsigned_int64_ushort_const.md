# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180004124`
- end: `0x1800041cd`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002878`
- `0x1800042d4`
- `0x1800089f8`

## callees

- `0x180004124`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  unsigned __int16 *v4; // rax
  unsigned int v5; // edx
  __int64 v6; // r11
  unsigned __int16 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r9
  unsigned __int16 *v10; // rcx

  v3 = 260;
  v4 = a1;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0x80070057 : 0;
  v6 = (260 - v3) & -(__int64)(v3 != 0);
  if ( v3 )
  {
    v7 = &a1[v6];
    v8 = 2147483646;
    v9 = 260 - v6;
    if ( 260 != v6 )
    {
      do
      {
        if ( !v8 )
          break;
        if ( !*a3 )
          break;
        *v7++ = *a3++;
        --v8;
        --v9;
      }
      while ( v9 );
    }
    v10 = v7 - 1;
    if ( v9 )
      v10 = v7;
    v5 = v9 == 0 ? 0x8007007A : 0;
    *v10 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180004124  mov     [rsp+arg_0], rbx
0x180004129  mov     [rsp+arg_8], rdi
0x18000412e  mov     r9d, 104h
0x180004134  mov     rbx, rcx
0x180004137  mov     r10d, r9d
0x18000413a  mov     rax, rcx
0x18000413d  xor     edi, edi
0x18000413f  cmp     [rax], di
0x180004142  jz      short loc_18000414E
0x180004144  add     rax, 2
0x180004148  sub     r10, 1
0x18000414c  jnz     short loc_18000413F
0x18000414e  mov     rax, r10
0x180004151  mov     rcx, r9
0x180004154  neg     rax
0x180004157  mov     rax, r10
0x18000415a  sbb     edx, edx
0x18000415c  sub     rcx, r10
0x18000415f  not     edx
0x180004161  and     edx, 80070057h
0x180004167  neg     rax
0x18000416a  sbb     r11, r11
0x18000416d  and     r11, rcx
0x180004170  test    r10, r10
0x180004173  jz      short loc_1800041C0
0x180004175  lea     rax, [rbx+r11*2]
0x180004179  mov     ecx, 7FFFFFFEh
0x18000417e  sub     r9, r11
0x180004181  jz      short loc_1800041A5
0x180004183  test    rcx, rcx
0x180004186  jz      short loc_1800041A5
0x180004188  movzx   edx, word ptr [r8]
0x18000418c  test    dx, dx
0x18000418f  jz      short loc_1800041A5
0x180004191  mov     [rax], dx
0x180004194  add     r8, 2
0x180004198  add     rax, 2
0x18000419c  dec     rcx
0x18000419f  sub     r9, 1
0x1800041a3  jnz     short loc_180004183
0x1800041a5  test    r9, r9
0x1800041a8  lea     rcx, [rax-2]
0x1800041ac  cmovnz  rcx, rax
0x1800041b0  neg     r9
0x1800041b3  sbb     edx, edx
0x1800041b5  not     edx
0x1800041b7  and     edx, 8007007Ah
0x1800041bd  mov     [rcx], di
0x1800041c0  mov     rbx, [rsp+arg_0]
0x1800041c5  mov     eax, edx
0x1800041c7  mov     rdi, [rsp+arg_8]
0x1800041cc  retn
```
