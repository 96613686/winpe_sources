# TupleVariationInterpolator::ReadPackedPoints(array_ref<uchar const>,uint &,std::vector<ushort,std::allocator<ushort>> &)

- ea: `0x140045cb8`
- end: `0x140045e66`
- name: `?ReadPackedPoints@TupleVariationInterpolator@@SAIV?$array_ref@$$CBE@@AEAIAEAV?$vector@GV?$allocator@G@std@@@std@@@Z`
- size: `430`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140044e14`
- `0x140045194`

## callees

- `0x140045cb8`
- `0x140045e6c`
- `0x14007327c`

## pseudocode

```c
__int64 __fastcall TupleVariationInterpolator::ReadPackedPoints(__int64 *a1, _DWORD *a2, _QWORD *a3, __int64 a4)
{
  __int64 v4; // r12
  unsigned __int64 v7; // rbx
  unsigned __int64 v8; // rcx
  __int64 v9; // rdx
  unsigned __int16 v10; // si
  int v11; // ecx
  char v12; // r15
  char v13; // r13
  __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  unsigned __int16 v16; // bp
  int v17; // ecx
  unsigned __int16 *v18; // rdx
  unsigned __int64 v20; // rcx
  unsigned __int8 v21; // r13
  unsigned __int16 v22; // [rsp+70h] [rbp+8h] BYREF

  v4 = *a1;
  v7 = a1[1] - *a1;
  if ( *a3 != a3[1] )
    a3[1] = *a3;
  v8 = (unsigned int)*a2;
  if ( v8 >= v7 )
    CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
      v8,
      a2,
      a3,
      a4);
  v9 = *(unsigned __int8 *)(v8 + v4);
  if ( (v9 & 0x80u) != 0LL )
  {
    if ( v7 - v8 < 2 )
      CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
        v8,
        v9,
        0,
        a4);
    v10 = _byteswap_ushort(*(_WORD *)(v8 + v4)) & 0x7FFF;
    v11 = v8 + 2;
  }
  else
  {
    v10 = *(unsigned __int8 *)(v8 + v4);
    v11 = v8 + 1;
  }
  *a2 = v11;
  if ( v10 )
  {
    v12 = 0;
    v13 = 0;
    v14 = 0;
    while ( (__int64)(a3[1] - *a3) >> 1 < (unsigned __int64)v10 )
    {
      if ( !v12 )
      {
        v20 = (unsigned int)*a2;
        if ( v20 >= v7 )
          CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
            v20,
            v14,
            0,
            a4);
        v21 = *(_BYTE *)(v20 + v4);
        *a2 = v20 + 1;
        v12 = (v21 & 0x7F) + 1;
        v13 = v21 >> 7;
      }
      v15 = (unsigned int)*a2;
      if ( v13 )
      {
        if ( v15 > v7 || v7 - v15 < 2 )
          CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
            v15,
            v14,
            0,
            a4);
        v16 = v14 + _byteswap_ushort(*(_WORD *)(v15 + v4));
        v17 = v15 + 2;
      }
      else
      {
        if ( v15 >= v7 )
          CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
            v15,
            v14,
            0,
            a4);
        v16 = v14 + *(unsigned __int8 *)(v15 + v4);
        v17 = v15 + 1;
      }
      *a2 = v17;
      v18 = (unsigned __int16 *)a3[1];
      v22 = v16;
      if ( v18 == (unsigned __int16 *)a3[2] )
      {
        std::vector<unsigned short>::_Emplace_reallocate<unsigned short>(a3, v18, &v22);
      }
      else
      {
        *v18 = v16;
        a3[1] += 2LL;
      }
      v14 = v16;
      --v12;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x140045cb8  push    rbx
0x140045cba  push    rbp
0x140045cbb  push    rsi
0x140045cbc  push    rdi
0x140045cbd  push    r12
0x140045cbf  push    r13
0x140045cc1  push    r14
0x140045cc3  push    r15
0x140045cc5  sub     rsp, 28h
0x140045cc9  mov     r12, [rcx]
0x140045ccc  mov     rdi, r8
0x140045ccf  mov     rbx, [rcx+8]
0x140045cd3  mov     r14, rdx
0x140045cd6  mov     rax, [r8]
0x140045cd9  sub     rbx, r12
0x140045cdc  cmp     rax, [r8+8]
0x140045ce0  jnz     loc_140045E08
0x140045ce6  mov     ecx, [rdx]
0x140045ce8  cmp     rcx, rbx
0x140045ceb  ja      loc_140045DFC
0x140045cf1  mov     rax, rbx
0x140045cf4  sub     rax, rcx
0x140045cf7  cmp     rax, 1
0x140045cfb  jb      loc_140045DFC
0x140045d01  movzx   edx, byte ptr [rcx+r12]
0x140045d06  xor     r8d, r8d
0x140045d09  test    dl, dl
0x140045d0b  js      loc_140045E11
0x140045d11  movzx   esi, dx
0x140045d14  inc     ecx
0x140045d16  mov     [r14], ecx
0x140045d19  test    si, si
0x140045d1c  jz      loc_140045DA6
0x140045d22  mov     r15b, r8b
0x140045d25  mov     r13b, r8b
0x140045d28  mov     edx, r8d
0x140045d2b  mov     rax, [rdi+8]
0x140045d2f  sub     rax, [rdi]
0x140045d32  sar     rax, 1
0x140045d35  movzx   ecx, si
0x140045d38  cmp     rax, rcx
0x140045d3b  jnb     short loc_140045DA6
0x140045d3d  test    r15b, r15b
0x140045d40  jz      short loc_140045DBA
0x140045d42  mov     ecx, [r14]
0x140045d45  test    r13b, r13b
0x140045d48  jnz     loc_140045DF1
0x140045d4e  cmp     rcx, rbx
0x140045d51  ja      loc_140045DEB
0x140045d57  mov     rax, rbx
0x140045d5a  sub     rax, rcx
0x140045d5d  cmp     rax, 1
0x140045d61  jb      loc_140045DEB
0x140045d67  movzx   ebp, byte ptr [rcx+r12]
0x140045d6c  add     bp, dx
0x140045d6f  inc     ecx
0x140045d71  mov     [r14], ecx
0x140045d74  mov     rdx, [rdi+8]
0x140045d78  mov     [rsp+68h+arg_0], bp
0x140045d7d  cmp     rdx, [rdi+10h]
0x140045d81  jnz     short loc_140045D9C
0x140045d83  lea     r8, [rsp+68h+arg_0]
0x140045d88  mov     rcx, rdi
0x140045d8b  call    ??$_Emplace_reallocate@G@?$vector@GV?$allocator@G@std@@@std@@AEAAPEAGQEAG$$QEAG@Z; std::vector<ushort>::_Emplace_reallocate<ushort>(ushort * const,ushort &&)
0x140045d90  xor     r8d, r8d
0x140045d93  movzx   edx, bp
0x140045d96  add     r15b, 0FFh
0x140045d9a  jmp     short loc_140045D2B
0x140045d9c  mov     [rdx], bp
0x140045d9f  add     qword ptr [rdi+8], 2
0x140045da4  jmp     short loc_140045D93
0x140045da6  movzx   eax, si
0x140045da9  add     rsp, 28h
0x140045dad  pop     r15
0x140045daf  pop     r14
0x140045db1  pop     r13
0x140045db3  pop     r12
0x140045db5  pop     rdi
0x140045db6  pop     rsi
0x140045db7  pop     rbp
0x140045db8  pop     rbx
0x140045db9  retn
0x140045dba  mov     ecx, [r14]
0x140045dbd  cmp     rcx, rbx
0x140045dc0  ja      short loc_140045E02
0x140045dc2  mov     rax, rbx
0x140045dc5  sub     rax, rcx
0x140045dc8  cmp     rax, 1
0x140045dcc  jb      short loc_140045E02
0x140045dce  mov     r13b, [rcx+r12]
0x140045dd2  lea     eax, [rcx+1]
0x140045dd5  mov     r15b, r13b
0x140045dd8  mov     [r14], eax
0x140045ddb  and     r15b, 7Fh
0x140045ddf  inc     r15b
0x140045de2  shr     r13b, 7
0x140045de6  jmp     loc_140045D42
0x140045deb  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
0x140045df1  cmp     rcx, rbx
0x140045df4  jbe     short loc_140045E3D
0x140045df6  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
0x140045dfc  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
0x140045e02  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
0x140045e08  mov     [r8+8], rax
0x140045e0c  jmp     loc_140045CE6
0x140045e11  cmp     rax, 2
0x140045e15  jb      short loc_140045E37
0x140045e17  movzx   esi, byte ptr [rcx+r12+1]
0x140045e1d  movzx   eax, dx
0x140045e20  shl     ax, 8
0x140045e24  or      si, ax
0x140045e27  mov     eax, 7FFFh
0x140045e2c  and     si, ax
0x140045e2f  add     ecx, 2
0x140045e32  jmp     loc_140045D16
0x140045e37  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
0x140045e3d  mov     rax, rbx
0x140045e40  sub     rax, rcx
0x140045e43  cmp     rax, 2
0x140045e47  jb      short loc_140045DF6
0x140045e49  movzx   eax, byte ptr [rcx+r12]
0x140045e4e  movzx   ebp, byte ptr [rcx+r12+1]
0x140045e54  shl     ax, 8
0x140045e58  or      bp, ax
0x140045e5b  add     bp, dx
0x140045e5e  add     ecx, 2
0x140045e61  jmp     loc_140045D71
```
