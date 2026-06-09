# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006bd4`
- end: `0x180006c8f`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a78`
- `0x180006d7c`
- `0x180012b58`
- `0x180012d2c`
- `0x180017734`
- `0x1800178d4`
- `0x18001bb10`
- `0x18001bc64`

## callees

- `0x180006bd4`

## pseudocode

```c
__int64 __fastcall StringCchCatW(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 v3; // r10
  __int64 v5; // r11
  unsigned __int16 *v6; // rax
  unsigned int v7; // edx
  __int64 v8; // rax
  __int64 v9; // r9
  unsigned __int16 *i; // rax
  unsigned __int16 *v11; // rcx

  v3 = 2147483646;
  if ( (unsigned __int64)(a2 - 1) > 0x7FFFFFFE )
  {
    return (unsigned int)-2147024809;
  }
  else
  {
    v5 = a2;
    v6 = a1;
    do
    {
      if ( !*v6 )
        break;
      ++v6;
      --v5;
    }
    while ( v5 );
    v7 = v5 == 0 ? 0x80070057 : 0;
    v8 = (a2 - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      v9 = a2 - v8;
      for ( i = &a1[v8]; v9; --v9 )
      {
        if ( !v3 )
          break;
        if ( !*a3 )
          break;
        *i++ = *a3++;
        --v3;
      }
      v11 = i - 1;
      if ( v9 )
        v11 = i;
      v7 = v9 == 0 ? 0x8007007A : 0;
      *v11 = 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180006bd4  mov     [rsp+arg_0], rbx
0x180006bd9  mov     [rsp+arg_8], rdi
0x180006bde  lea     rax, [rdx-1]
0x180006be2  mov     r10d, 7FFFFFFEh
0x180006be8  mov     r9, rdx
0x180006beb  mov     rbx, rcx
0x180006bee  cmp     rax, r10
0x180006bf1  ja      loc_180006C7D
0x180006bf7  mov     r11, rdx
0x180006bfa  mov     rax, rcx
0x180006bfd  xor     edi, edi
0x180006bff  cmp     [rax], di
0x180006c02  jz      short loc_180006C0E
0x180006c04  add     rax, 2
0x180006c08  sub     r11, 1
0x180006c0c  jnz     short loc_180006BFF
0x180006c0e  mov     rax, r11
0x180006c11  mov     rcx, r9
0x180006c14  neg     rax
0x180006c17  mov     rax, r11
0x180006c1a  sbb     edx, edx
0x180006c1c  sub     rcx, r11
0x180006c1f  not     edx
0x180006c21  and     edx, 80070057h
0x180006c27  neg     rax
0x180006c2a  sbb     rax, rax
0x180006c2d  and     rax, rcx
0x180006c30  test    r11, r11
0x180006c33  jz      short loc_180006C82
0x180006c35  sub     r9, rax
0x180006c38  lea     rax, [rbx+rax*2]
0x180006c3c  jz      short loc_180006C60
0x180006c3e  test    r10, r10
0x180006c41  jz      short loc_180006C60
0x180006c43  movzx   ecx, word ptr [r8]
0x180006c47  test    cx, cx
0x180006c4a  jz      short loc_180006C60
0x180006c4c  mov     [rax], cx
0x180006c4f  add     r8, 2
0x180006c53  add     rax, 2
0x180006c57  dec     r10
0x180006c5a  sub     r9, 1
0x180006c5e  jnz     short loc_180006C3E
0x180006c60  test    r9, r9
0x180006c63  lea     rcx, [rax-2]
0x180006c67  cmovnz  rcx, rax
0x180006c6b  neg     r9
0x180006c6e  sbb     edx, edx
0x180006c70  not     edx
0x180006c72  and     edx, 8007007Ah
0x180006c78  mov     [rcx], di
0x180006c7b  jmp     short loc_180006C82
0x180006c7d  mov     edx, 80070057h
0x180006c82  mov     rbx, [rsp+arg_0]
0x180006c87  mov     eax, edx
0x180006c89  mov     rdi, [rsp+arg_8]
0x180006c8e  retn
```
