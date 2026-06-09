# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006a90`
- end: `0x180006b39`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003bb4`
- `0x180006bfc`

## callees

- `0x180006a90`

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
0x180006a90  mov     [rsp+arg_0], rbx
0x180006a95  mov     [rsp+arg_8], rdi
0x180006a9a  mov     r9d, 104h
0x180006aa0  mov     rbx, rcx
0x180006aa3  mov     r10d, r9d
0x180006aa6  mov     rax, rcx
0x180006aa9  xor     edi, edi
0x180006aab  cmp     [rax], di
0x180006aae  jz      short loc_180006ABA
0x180006ab0  add     rax, 2
0x180006ab4  sub     r10, 1
0x180006ab8  jnz     short loc_180006AAB
0x180006aba  mov     rax, r10
0x180006abd  mov     rcx, r9
0x180006ac0  neg     rax
0x180006ac3  mov     rax, r10
0x180006ac6  sbb     edx, edx
0x180006ac8  sub     rcx, r10
0x180006acb  not     edx
0x180006acd  and     edx, 80070057h
0x180006ad3  neg     rax
0x180006ad6  sbb     r11, r11
0x180006ad9  and     r11, rcx
0x180006adc  test    r10, r10
0x180006adf  jz      short loc_180006B2C
0x180006ae1  lea     rax, [rbx+r11*2]
0x180006ae5  mov     ecx, 7FFFFFFEh
0x180006aea  sub     r9, r11
0x180006aed  jz      short loc_180006B11
0x180006aef  test    rcx, rcx
0x180006af2  jz      short loc_180006B11
0x180006af4  movzx   edx, word ptr [r8]
0x180006af8  test    dx, dx
0x180006afb  jz      short loc_180006B11
0x180006afd  mov     [rax], dx
0x180006b00  add     r8, 2
0x180006b04  add     rax, 2
0x180006b08  dec     rcx
0x180006b0b  sub     r9, 1
0x180006b0f  jnz     short loc_180006AEF
0x180006b11  test    r9, r9
0x180006b14  lea     rcx, [rax-2]
0x180006b18  cmovnz  rcx, rax
0x180006b1c  neg     r9
0x180006b1f  sbb     edx, edx
0x180006b21  not     edx
0x180006b23  and     edx, 8007007Ah
0x180006b29  mov     [rcx], di
0x180006b2c  mov     rbx, [rsp+arg_0]
0x180006b31  mov     eax, edx
0x180006b33  mov     rdi, [rsp+arg_8]
0x180006b38  retn
```
