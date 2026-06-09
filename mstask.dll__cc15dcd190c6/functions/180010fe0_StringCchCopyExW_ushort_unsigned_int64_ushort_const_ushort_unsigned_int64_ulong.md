# StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x180010fe0`
- end: `0x1800110bc`
- name: `?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `220`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011fc0`

## callees

- `0x180010fe0`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  unsigned __int64 v6; // r10
  unsigned __int16 *v7; // r11
  unsigned int v8; // r8d
  const WCHAR *v9; // rax
  __int64 v10; // rcx
  unsigned __int64 v11; // r8
  unsigned __int16 *v12; // r9
  __int64 v13; // rbx
  __int64 v14; // rdx
  unsigned __int16 *v15; // rcx

  v6 = a2;
  v7 = a1;
  if ( (a1 || !a2) && a2 <= 0x7FFFFFFF )
  {
    v9 = &String;
    if ( a3 )
      v9 = a3;
    if ( a2 )
    {
      v10 = 2147483646;
      v11 = a2;
      v12 = v7;
      v13 = 0;
      do
      {
        if ( !v10 )
          break;
        if ( !*v9 )
          break;
        *v12++ = *v9++;
        --v10;
        ++v13;
        --v11;
      }
      while ( v11 );
      v14 = v13 - 1;
      v15 = v12 - 1;
      if ( v11 )
      {
        v14 = v13;
        v15 = v12;
      }
      *v15 = 0;
      v8 = v11 != 0 ? 0 : 0x8007007A;
      v7 += v14;
      v6 -= v14;
    }
    else
    {
      v8 = 0;
      if ( *v9 )
      {
        if ( !a1 )
          return (unsigned int)-2147024809;
        v8 = -2147024774;
      }
    }
    if ( a4 )
      *a4 = v7;
    if ( a5 )
      *a5 = v6;
  }
  else
  {
    v8 = -2147024809;
    *a1 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x180010fe0  push    rbx
0x180010fe2  push    rsi
0x180010fe3  push    rdi
0x180010fe4  xor     esi, esi
0x180010fe6  mov     rdi, r9
0x180010fe9  mov     r10, rdx
0x180010fec  mov     r11, rcx
0x180010fef  test    rcx, rcx
0x180010ff2  jnz     short loc_180010FF9
0x180010ff4  test    rdx, rdx
0x180010ff7  jnz     short loc_180011002
0x180010ff9  cmp     r10, 7FFFFFFFh
0x180011000  jbe     short loc_180011010
0x180011002  mov     r8d, 80070057h
0x180011008  mov     [rcx], si
0x18001100b  jmp     loc_1800110B5
0x180011010  test    r8, r8
0x180011013  lea     rax, String
0x18001101a  cmovnz  rax, r8
0x18001101e  test    r10, r10
0x180011021  jnz     short loc_180011040
0x180011023  mov     r8d, esi
0x180011026  cmp     [rax], si
0x180011029  jz      short loc_1800110A0
0x18001102b  test    r11, r11
0x18001102e  jnz     short loc_180011038
0x180011030  mov     r8d, 80070057h
0x180011036  jmp     short loc_1800110B5
0x180011038  mov     r8d, 8007007Ah
0x18001103e  jmp     short loc_1800110A0
0x180011040  mov     ecx, 7FFFFFFEh
0x180011045  mov     r8, r10
0x180011048  mov     r9, r11
0x18001104b  mov     rbx, rsi
0x18001104e  test    rcx, rcx
0x180011051  jz      short loc_180011073
0x180011053  movzx   edx, word ptr [rax]
0x180011056  test    dx, dx
0x180011059  jz      short loc_180011073
0x18001105b  mov     [r9], dx
0x18001105f  add     rax, 2
0x180011063  add     r9, 2
0x180011067  dec     rcx
0x18001106a  inc     rbx
0x18001106d  sub     r8, 1
0x180011071  jnz     short loc_18001104E
0x180011073  test    r8, r8
0x180011076  lea     rdx, [rbx-1]
0x18001107a  lea     rcx, [r9-2]
0x18001107e  cmovnz  rdx, rbx
0x180011082  cmovnz  rcx, r9
0x180011086  neg     r8
0x180011089  mov     r8d, 8007007Ah
0x18001108f  sbb     eax, eax
0x180011091  not     eax
0x180011093  mov     [rcx], si
0x180011096  and     r8d, eax
0x180011099  lea     r11, [r11+rdx*2]
0x18001109d  sub     r10, rdx
0x1800110a0  test    rdi, rdi
0x1800110a3  jz      short loc_1800110A8
0x1800110a5  mov     [rdi], r11
0x1800110a8  mov     rax, [rsp+18h+arg_20]
0x1800110ad  test    rax, rax
0x1800110b0  jz      short loc_1800110B5
0x1800110b2  mov     [rax], r10
0x1800110b5  mov     eax, r8d
0x1800110b8  pop     rdi
0x1800110b9  pop     rsi
0x1800110ba  pop     rbx
0x1800110bb  retn
```
