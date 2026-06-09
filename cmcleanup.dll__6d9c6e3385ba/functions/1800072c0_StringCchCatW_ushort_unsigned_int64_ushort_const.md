# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1800072c0`
- end: `0x180007369`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003964`
- `0x18000742c`

## callees

- `0x1800072c0`

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
0x1800072c0  mov     [rsp+arg_0], rbx
0x1800072c5  mov     [rsp+arg_8], rdi
0x1800072ca  mov     r9d, 104h
0x1800072d0  mov     rbx, rcx
0x1800072d3  mov     r10d, r9d
0x1800072d6  mov     rax, rcx
0x1800072d9  xor     edi, edi
0x1800072db  cmp     [rax], di
0x1800072de  jz      short loc_1800072EA
0x1800072e0  add     rax, 2
0x1800072e4  sub     r10, 1
0x1800072e8  jnz     short loc_1800072DB
0x1800072ea  mov     rax, r10
0x1800072ed  mov     rcx, r9
0x1800072f0  neg     rax
0x1800072f3  mov     rax, r10
0x1800072f6  sbb     edx, edx
0x1800072f8  sub     rcx, r10
0x1800072fb  not     edx
0x1800072fd  and     edx, 80070057h
0x180007303  neg     rax
0x180007306  sbb     r11, r11
0x180007309  and     r11, rcx
0x18000730c  test    r10, r10
0x18000730f  jz      short loc_18000735C
0x180007311  lea     rax, [rbx+r11*2]
0x180007315  mov     ecx, 7FFFFFFEh
0x18000731a  sub     r9, r11
0x18000731d  jz      short loc_180007341
0x18000731f  test    rcx, rcx
0x180007322  jz      short loc_180007341
0x180007324  movzx   edx, word ptr [r8]
0x180007328  test    dx, dx
0x18000732b  jz      short loc_180007341
0x18000732d  mov     [rax], dx
0x180007330  add     r8, 2
0x180007334  add     rax, 2
0x180007338  dec     rcx
0x18000733b  sub     r9, 1
0x18000733f  jnz     short loc_18000731F
0x180007341  test    r9, r9
0x180007344  lea     rcx, [rax-2]
0x180007348  cmovnz  rcx, rax
0x18000734c  neg     r9
0x18000734f  sbb     edx, edx
0x180007351  not     edx
0x180007353  and     edx, 8007007Ah
0x180007359  mov     [rcx], di
0x18000735c  mov     rbx, [rsp+arg_0]
0x180007361  mov     eax, edx
0x180007363  mov     rdi, [rsp+arg_8]
0x180007368  retn
```
