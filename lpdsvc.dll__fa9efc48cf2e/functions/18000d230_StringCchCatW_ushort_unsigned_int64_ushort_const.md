# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000d230`
- end: `0x18000d2d9`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b940`
- `0x18000d36c`

## callees

- `0x18000d230`

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
0x18000d230  mov     [rsp+arg_0], rbx
0x18000d235  mov     [rsp+arg_8], rdi
0x18000d23a  mov     r9d, 104h
0x18000d240  mov     rbx, rcx
0x18000d243  mov     r10d, r9d
0x18000d246  mov     rax, rcx
0x18000d249  xor     edi, edi
0x18000d24b  cmp     [rax], di
0x18000d24e  jz      short loc_18000D25A
0x18000d250  add     rax, 2
0x18000d254  sub     r10, 1
0x18000d258  jnz     short loc_18000D24B
0x18000d25a  mov     rax, r10
0x18000d25d  mov     rcx, r9
0x18000d260  neg     rax
0x18000d263  mov     rax, r10
0x18000d266  sbb     edx, edx
0x18000d268  sub     rcx, r10
0x18000d26b  not     edx
0x18000d26d  and     edx, 80070057h
0x18000d273  neg     rax
0x18000d276  sbb     r11, r11
0x18000d279  and     r11, rcx
0x18000d27c  test    r10, r10
0x18000d27f  jz      short loc_18000D2CC
0x18000d281  lea     rax, [rbx+r11*2]
0x18000d285  mov     ecx, 7FFFFFFEh
0x18000d28a  sub     r9, r11
0x18000d28d  jz      short loc_18000D2B1
0x18000d28f  test    rcx, rcx
0x18000d292  jz      short loc_18000D2B1
0x18000d294  movzx   edx, word ptr [r8]
0x18000d298  test    dx, dx
0x18000d29b  jz      short loc_18000D2B1
0x18000d29d  mov     [rax], dx
0x18000d2a0  add     r8, 2
0x18000d2a4  add     rax, 2
0x18000d2a8  dec     rcx
0x18000d2ab  sub     r9, 1
0x18000d2af  jnz     short loc_18000D28F
0x18000d2b1  test    r9, r9
0x18000d2b4  lea     rcx, [rax-2]
0x18000d2b8  cmovnz  rcx, rax
0x18000d2bc  neg     r9
0x18000d2bf  sbb     edx, edx
0x18000d2c1  not     edx
0x18000d2c3  and     edx, 8007007Ah
0x18000d2c9  mov     [rcx], di
0x18000d2cc  mov     rbx, [rsp+arg_0]
0x18000d2d1  mov     eax, edx
0x18000d2d3  mov     rdi, [rsp+arg_8]
0x18000d2d8  retn
```
