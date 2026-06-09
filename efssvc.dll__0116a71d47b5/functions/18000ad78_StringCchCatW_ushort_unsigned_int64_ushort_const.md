# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000ad78`
- end: `0x18000ae21`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000936c`
- `0x18000aeb4`

## callees

- `0x18000ad78`

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
0x18000ad78  mov     [rsp+arg_0], rbx
0x18000ad7d  mov     [rsp+arg_8], rdi
0x18000ad82  mov     r9d, 104h
0x18000ad88  mov     rbx, rcx
0x18000ad8b  mov     r10d, r9d
0x18000ad8e  mov     rax, rcx
0x18000ad91  xor     edi, edi
0x18000ad93  cmp     [rax], di
0x18000ad96  jz      short loc_18000ADA2
0x18000ad98  add     rax, 2
0x18000ad9c  sub     r10, 1
0x18000ada0  jnz     short loc_18000AD93
0x18000ada2  mov     rax, r10
0x18000ada5  mov     rcx, r9
0x18000ada8  neg     rax
0x18000adab  mov     rax, r10
0x18000adae  sbb     edx, edx
0x18000adb0  sub     rcx, r10
0x18000adb3  not     edx
0x18000adb5  and     edx, 80070057h
0x18000adbb  neg     rax
0x18000adbe  sbb     r11, r11
0x18000adc1  and     r11, rcx
0x18000adc4  test    r10, r10
0x18000adc7  jz      short loc_18000AE14
0x18000adc9  lea     rax, [rbx+r11*2]
0x18000adcd  mov     ecx, 7FFFFFFEh
0x18000add2  sub     r9, r11
0x18000add5  jz      short loc_18000ADF9
0x18000add7  test    rcx, rcx
0x18000adda  jz      short loc_18000ADF9
0x18000addc  movzx   edx, word ptr [r8]
0x18000ade0  test    dx, dx
0x18000ade3  jz      short loc_18000ADF9
0x18000ade5  mov     [rax], dx
0x18000ade8  add     r8, 2
0x18000adec  add     rax, 2
0x18000adf0  dec     rcx
0x18000adf3  sub     r9, 1
0x18000adf7  jnz     short loc_18000ADD7
0x18000adf9  test    r9, r9
0x18000adfc  lea     rcx, [rax-2]
0x18000ae00  cmovnz  rcx, rax
0x18000ae04  neg     r9
0x18000ae07  sbb     edx, edx
0x18000ae09  not     edx
0x18000ae0b  and     edx, 8007007Ah
0x18000ae11  mov     [rcx], di
0x18000ae14  mov     rbx, [rsp+arg_0]
0x18000ae19  mov     eax, edx
0x18000ae1b  mov     rdi, [rsp+arg_8]
0x18000ae20  retn
```
