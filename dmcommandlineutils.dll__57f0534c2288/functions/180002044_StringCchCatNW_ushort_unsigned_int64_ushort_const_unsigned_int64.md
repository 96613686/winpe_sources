# StringCchCatNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180002044`
- end: `0x180002104`
- name: `?StringCchCatNW@@YAJPEAG_KPEBG1@Z`
- size: `192`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800018d8`
- `0x180001e10`

## callees

- `0x180002044`

## pseudocode

```c
__int64 __fastcall StringCchCatNW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3, unsigned __int64 a4)
{
  __int64 v6; // r11
  unsigned __int16 *v7; // rax
  unsigned int v8; // edx
  __int64 v9; // rax
  __int64 v10; // r10
  unsigned __int16 *i; // rax
  unsigned __int16 *v12; // rcx

  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v6 = a2;
    v7 = a1;
    do
    {
      if ( !*v7 )
        break;
      ++v7;
      --v6;
    }
    while ( v6 );
    v8 = -2147024809;
    v9 = (a2 - v6) & -(__int64)(v6 != 0);
    if ( v6 )
    {
      if ( a4 <= 0x7FFFFFFE )
      {
        v10 = a2 - v9;
        for ( i = &a1[v9]; v10; --v10 )
        {
          if ( !a4 )
            break;
          if ( !*a3 )
            break;
          *i++ = *a3++;
          --a4;
        }
        v12 = i - 1;
        if ( v10 )
          v12 = i;
        v8 = v10 == 0 ? 0x8007007A : 0;
        *v12 = 0;
      }
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180002044  push    rbx
0x180002046  push    rsi
0x180002047  push    rdi
0x180002048  lea     rax, [rdx-1]
0x18000204c  mov     rbx, r8
0x18000204f  mov     r10, rdx
0x180002052  mov     rdi, rcx
0x180002055  cmp     rax, 7FFFFFFEh
0x18000205b  ja      loc_1800020F8
0x180002061  mov     r11, rdx
0x180002064  mov     rax, rcx
0x180002067  xor     esi, esi
0x180002069  cmp     [rax], si
0x18000206c  jz      short loc_180002078
0x18000206e  add     rax, 2
0x180002072  sub     r11, 1
0x180002076  jnz     short loc_180002069
0x180002078  mov     rax, r11
0x18000207b  mov     edx, 80070057h
0x180002080  neg     rax
0x180002083  mov     rcx, r10
0x180002086  mov     rax, r11
0x180002089  sbb     r8d, r8d
0x18000208c  sub     rcx, r11
0x18000208f  not     r8d
0x180002092  and     r8d, edx
0x180002095  neg     rax
0x180002098  sbb     rax, rax
0x18000209b  and     rax, rcx
0x18000209e  test    r11, r11
0x1800020a1  jz      short loc_1800020F3
0x1800020a3  cmp     r9, 7FFFFFFEh
0x1800020aa  ja      short loc_1800020FD
0x1800020ac  sub     r10, rax
0x1800020af  lea     rax, [rdi+rax*2]
0x1800020b3  jz      short loc_1800020D6
0x1800020b5  test    r9, r9
0x1800020b8  jz      short loc_1800020D6
0x1800020ba  movzx   ecx, word ptr [rbx]
0x1800020bd  test    cx, cx
0x1800020c0  jz      short loc_1800020D6
0x1800020c2  mov     [rax], cx
0x1800020c5  add     rbx, 2
0x1800020c9  add     rax, 2
0x1800020cd  dec     r9
0x1800020d0  sub     r10, 1
0x1800020d4  jnz     short loc_1800020B5
0x1800020d6  test    r10, r10
0x1800020d9  lea     rcx, [rax-2]
0x1800020dd  cmovnz  rcx, rax
0x1800020e1  neg     r10
0x1800020e4  sbb     edx, edx
0x1800020e6  not     edx
0x1800020e8  and     edx, 8007007Ah
0x1800020ee  mov     [rcx], si
0x1800020f1  jmp     short loc_1800020FD
0x1800020f3  mov     edx, r8d
0x1800020f6  jmp     short loc_1800020FD
0x1800020f8  mov     edx, 80070057h
0x1800020fd  mov     eax, edx
0x1800020ff  pop     rdi
0x180002100  pop     rsi
0x180002101  pop     rbx
0x180002102  retn
```
