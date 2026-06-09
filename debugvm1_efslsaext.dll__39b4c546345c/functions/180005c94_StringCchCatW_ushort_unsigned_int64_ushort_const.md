# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005c94`
- end: `0x180005d4f`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f9c`
- `0x180005f2c`
- `0x180008544`
- `0x18000ac60`
- `0x18000d41c`

## callees

- `0x180005c94`

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
0x180005c94  mov     [rsp+arg_0], rbx
0x180005c99  mov     [rsp+arg_8], rdi
0x180005c9e  lea     rax, [rdx-1]
0x180005ca2  mov     r10d, 7FFFFFFEh
0x180005ca8  mov     r9, rdx
0x180005cab  mov     rbx, rcx
0x180005cae  cmp     rax, r10
0x180005cb1  ja      loc_180005D3D
0x180005cb7  mov     r11, rdx
0x180005cba  mov     rax, rcx
0x180005cbd  xor     edi, edi
0x180005cbf  cmp     [rax], di
0x180005cc2  jz      short loc_180005CCE
0x180005cc4  add     rax, 2
0x180005cc8  sub     r11, 1
0x180005ccc  jnz     short loc_180005CBF
0x180005cce  mov     rax, r11
0x180005cd1  mov     rcx, r9
0x180005cd4  neg     rax
0x180005cd7  mov     rax, r11
0x180005cda  sbb     edx, edx
0x180005cdc  sub     rcx, r11
0x180005cdf  not     edx
0x180005ce1  and     edx, 80070057h
0x180005ce7  neg     rax
0x180005cea  sbb     rax, rax
0x180005ced  and     rax, rcx
0x180005cf0  test    r11, r11
0x180005cf3  jz      short loc_180005D42
0x180005cf5  sub     r9, rax
0x180005cf8  lea     rax, [rbx+rax*2]
0x180005cfc  jz      short loc_180005D20
0x180005cfe  test    r10, r10
0x180005d01  jz      short loc_180005D20
0x180005d03  movzx   ecx, word ptr [r8]
0x180005d07  test    cx, cx
0x180005d0a  jz      short loc_180005D20
0x180005d0c  mov     [rax], cx
0x180005d0f  add     r8, 2
0x180005d13  add     rax, 2
0x180005d17  dec     r10
0x180005d1a  sub     r9, 1
0x180005d1e  jnz     short loc_180005CFE
0x180005d20  test    r9, r9
0x180005d23  lea     rcx, [rax-2]
0x180005d27  cmovnz  rcx, rax
0x180005d2b  neg     r9
0x180005d2e  sbb     edx, edx
0x180005d30  not     edx
0x180005d32  and     edx, 8007007Ah
0x180005d38  mov     [rcx], di
0x180005d3b  jmp     short loc_180005D42
0x180005d3d  mov     edx, 80070057h
0x180005d42  mov     rbx, [rsp+arg_0]
0x180005d47  mov     eax, edx
0x180005d49  mov     rdi, [rsp+arg_8]
0x180005d4e  retn
```
