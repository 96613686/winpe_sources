# CClass::GetPath(ushort *)

- ea: `0x18000ad9c`
- end: `0x18000ae6d`
- name: `?GetPath@CClass@@QEAAJPEAG@Z`
- size: `209`
- prototype: `__int64 __fastcall(CClass *__hidden this, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ae74`
- `0x18000b45c`
- `0x18000bbc4`

## callees

- `0x18000ad9c`

## pseudocode

```c
__int64 __fastcall CClass::GetPath(CClass *this, unsigned __int16 *a2)
{
  unsigned __int16 *v2; // rax
  __int64 result; // rax
  __int64 v4; // r8
  unsigned int v5; // r9d
  unsigned __int16 *v6; // r10
  __int64 v7; // rdx
  unsigned __int16 *v8; // rcx
  __int64 v9; // rcx
  unsigned __int16 *v10; // rcx
  unsigned __int16 *v11; // rcx
  const unsigned __int16 *v12; // rcx
  unsigned __int16 *v13; // rdx

  v2 = a2;
  if ( !a2 )
    return 2147500035LL;
  v4 = 260;
  v5 = 1;
  if ( (*((_BYTE *)this + 16) & 0x10) != 0 )
  {
    v6 = (unsigned __int16 *)*((_QWORD *)this + 11);
    v7 = 520;
    do
    {
      if ( !v4 )
        break;
      if ( !*v6 )
        break;
      *v2++ = *v6++;
      --v4;
      --v7;
    }
    while ( v7 );
    v8 = v2 - 1;
    if ( v7 )
      v8 = v2;
    result = 0;
    *v8 = 0;
  }
  else
  {
    v9 = *((_QWORD *)this + 23);
    if ( *(_DWORD *)(v9 + 552) )
    {
      v10 = (unsigned __int16 *)(v9 + 32);
      do
      {
        if ( !*v10 )
          break;
        *v2++ = *v10++;
        --v4;
      }
      while ( v4 );
      v11 = v2 - 1;
      v5 = 0;
      if ( v4 )
        v11 = v2;
      *v11 = 0;
    }
    else
    {
      v12 = &qword_180012188;
      do
      {
        if ( !*v12 )
          break;
        *v2++ = *v12++;
        --v4;
      }
      while ( v4 );
      v13 = v2 - 1;
      if ( v4 )
        v13 = v2;
      *v13 = 0;
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18000ad9c  xor     r11d, r11d
0x18000ad9f  mov     rax, rdx
0x18000ada2  test    rdx, rdx
0x18000ada5  jnz     short loc_18000ADAD
0x18000ada7  mov     eax, 80004003h
0x18000adac  retn
0x18000adad  test    byte ptr [rcx+10h], 10h
0x18000adb1  mov     r8d, 104h
0x18000adb7  mov     r9d, 1
0x18000adbd  jz      short loc_18000ADFB
0x18000adbf  mov     r10, [rcx+58h]
0x18000adc3  mov     edx, 208h
0x18000adc8  test    r8, r8
0x18000adcb  jz      short loc_18000ADE9
0x18000adcd  movzx   ecx, word ptr [r10]
0x18000add1  test    cx, cx
0x18000add4  jz      short loc_18000ADE9
0x18000add6  mov     [rax], cx
0x18000add9  add     r10, 2
0x18000addd  add     rax, 2
0x18000ade1  sub     r8, r9
0x18000ade4  sub     rdx, r9
0x18000ade7  jnz     short loc_18000ADC8
0x18000ade9  test    rdx, rdx
0x18000adec  lea     rcx, [rax-2]
0x18000adf0  cmovnz  rcx, rax
0x18000adf4  xor     eax, eax
0x18000adf6  mov     [rcx], r11w
0x18000adfa  retn
0x18000adfb  mov     rcx, [rcx+0B8h]
0x18000ae02  cmp     [rcx+228h], r11d
0x18000ae09  jz      short loc_18000AE3B
0x18000ae0b  add     rcx, 20h ; ' '
0x18000ae0f  movzx   edx, word ptr [rcx]
0x18000ae12  test    dx, dx
0x18000ae15  jz      short loc_18000AE27
0x18000ae17  mov     [rax], dx
0x18000ae1a  add     rcx, 2
0x18000ae1e  add     rax, 2
0x18000ae22  sub     r8, r9
0x18000ae25  jnz     short loc_18000AE0F
0x18000ae27  test    r8, r8
0x18000ae2a  lea     rcx, [rax-2]
0x18000ae2e  mov     r9d, r11d
0x18000ae31  cmovnz  rcx, rax
0x18000ae35  mov     [rcx], r11w
0x18000ae39  jmp     short loc_18000AE69
0x18000ae3b  lea     rcx, qword_180012188
0x18000ae42  movzx   edx, word ptr [rcx]
0x18000ae45  test    dx, dx
0x18000ae48  jz      short loc_18000AE5A
0x18000ae4a  mov     [rax], dx
0x18000ae4d  add     rcx, 2
0x18000ae51  add     rax, 2
0x18000ae55  sub     r8, r9
0x18000ae58  jnz     short loc_18000AE42
0x18000ae5a  test    r8, r8
0x18000ae5d  lea     rdx, [rax-2]
0x18000ae61  cmovnz  rdx, rax
0x18000ae65  mov     [rdx], r11w
0x18000ae69  mov     eax, r9d
0x18000ae6c  retn
```
