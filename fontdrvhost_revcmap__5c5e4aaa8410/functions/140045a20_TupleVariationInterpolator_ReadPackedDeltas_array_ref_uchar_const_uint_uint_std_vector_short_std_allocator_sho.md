# TupleVariationInterpolator::ReadPackedDeltas(array_ref<uchar const>,uint &,uint,std::vector<short,std::allocator<short>> &)

- ea: `0x140045a20`
- end: `0x140045b77`
- name: `?ReadPackedDeltas@TupleVariationInterpolator@@SAXV?$array_ref@$$CBE@@AEAIIAEAV?$vector@FV?$allocator@F@std@@@std@@@Z`
- size: `343`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140044004`
- `0x1400456ec`

## callees

- `0x140045a20`
- `0x140045b80`
- `0x14007327c`

## pseudocode

```c
unsigned __int64 __fastcall TupleVariationInterpolator::ReadPackedDeltas(
        __int64 *a1,
        unsigned int *a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v4; // r15
  unsigned __int64 v7; // rsi
  unsigned int v8; // edi
  char v9; // bp
  unsigned __int64 v10; // rcx
  char v11; // r13
  bool v12; // r14
  unsigned __int16 *v13; // r9
  unsigned __int64 result; // rax
  unsigned __int16 v15; // cx
  __int64 v16; // rdx
  char v17; // r14
  unsigned __int64 v18; // [rsp+60h] [rbp+8h]
  unsigned __int16 v19; // [rsp+70h] [rbp+18h] BYREF

  v4 = *a1;
  v7 = a1[1] - *a1;
  v8 = *a2;
  if ( *a4 != a4[1] )
    a4[1] = *a4;
  v9 = 0;
  v10 = (unsigned int)a3;
  v11 = 0;
  v18 = (unsigned int)a3;
  v12 = 0;
  while ( 1 )
  {
    v13 = (unsigned __int16 *)a4[1];
    result = ((__int64)v13 - *a4) >> 1;
    if ( result >= v10 )
      break;
    v15 = 0;
    v19 = 0;
    if ( !v9 )
    {
      v16 = v8;
      if ( v8 >= v7 )
        CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
          0,
          v8,
          a3,
          v13);
      v17 = *(_BYTE *)(v8++ + v4);
      v11 = *(_BYTE *)(v16 + v4) >> 7;
      v9 = (v17 & 0x3F) + 1;
      v12 = (v17 & 0x40) != 0;
    }
    if ( !v11 )
    {
      if ( v12 )
      {
        if ( v8 > v7 || v7 - v8 < 2 )
          CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
            0,
            v8,
            a3,
            v13);
        v15 = _byteswap_ushort(*(_WORD *)(v8 + v4));
        v8 += 2;
      }
      else
      {
        if ( v8 >= v7 )
          CheckedPtr<unsigned char const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(
            0,
            v8,
            a3,
            v13);
        v15 = *(char *)(v8++ + v4);
      }
      v19 = v15;
    }
    if ( v13 == (unsigned __int16 *)a4[2] )
    {
      std::vector<short>::_Emplace_reallocate<short const &>(a4, v13, &v19);
    }
    else
    {
      *v13 = v15;
      a4[1] += 2LL;
    }
    v10 = v18;
    --v9;
  }
  *a2 = v8;
  return result;
}

```

## disassembly

```asm
0x140045a20  mov     [rsp+arg_8], rbx
0x140045a25  push    rbp
0x140045a26  push    rsi
0x140045a27  push    rdi
0x140045a28  push    r12
0x140045a2a  push    r13
0x140045a2c  push    r14
0x140045a2e  push    r15
0x140045a30  sub     rsp, 20h
0x140045a34  mov     r15, [rcx]
0x140045a37  mov     rbx, r9
0x140045a3a  mov     rsi, [rcx+8]
0x140045a3e  mov     r12, rdx
0x140045a41  mov     rax, [r9]
0x140045a44  sub     rsi, r15
0x140045a47  mov     edi, [rdx]
0x140045a49  cmp     rax, [r9+8]
0x140045a4d  jnz     loc_140045B40
0x140045a53  xor     bpl, bpl
0x140045a56  mov     ecx, r8d
0x140045a59  xor     r13b, r13b
0x140045a5c  mov     [rsp+58h+arg_0], rcx
0x140045a61  xor     r14b, r14b
0x140045a64  mov     r9, [rbx+8]
0x140045a68  mov     rax, r9
0x140045a6b  sub     rax, [rbx]
0x140045a6e  sar     rax, 1
0x140045a71  cmp     rax, rcx
0x140045a74  jnb     loc_140045B27
0x140045a7a  xor     ecx, ecx
0x140045a7c  mov     [rsp+58h+arg_10], cx
0x140045a81  test    bpl, bpl
0x140045a84  jz      short loc_140045AD9
0x140045a86  test    r13b, r13b
0x140045a89  jnz     short loc_140045AAD
0x140045a8b  mov     edx, edi
0x140045a8d  test    r14b, r14b
0x140045a90  jnz     short loc_140045B10
0x140045a92  cmp     rdx, rsi
0x140045a95  ja      short loc_140045AA7
0x140045a97  mov     rax, rsi
0x140045a9a  sub     rax, rdx
0x140045a9d  cmp     rax, 1
0x140045aa1  jnb     loc_140045B66
0x140045aa7  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
0x140045aad  cmp     r9, [rbx+10h]
0x140045ab1  jz      short loc_140045AC7
0x140045ab3  mov     [r9], cx
0x140045ab7  add     qword ptr [rbx+8], 2
0x140045abc  mov     rcx, [rsp+58h+arg_0]
0x140045ac1  add     bpl, 0FFh
0x140045ac5  jmp     short loc_140045A64
0x140045ac7  lea     r8, [rsp+58h+arg_10]
0x140045acc  mov     rdx, r9
0x140045acf  mov     rcx, rbx
0x140045ad2  call    ??$_Emplace_reallocate@AEBF@?$vector@FV?$allocator@F@std@@@std@@AEAAPEAFQEAFAEBF@Z; std::vector<short>::_Emplace_reallocate<short const &>(short * const,short const &)
0x140045ad7  jmp     short loc_140045ABC
0x140045ad9  mov     edx, edi
0x140045adb  cmp     rdx, rsi
0x140045ade  ja      short loc_140045B49
0x140045ae0  mov     rax, rsi
0x140045ae3  sub     rax, rdx
0x140045ae6  cmp     rax, 1
0x140045aea  jb      short loc_140045B49
0x140045aec  mov     r14b, [rdx+r15]
0x140045af0  inc     edi
0x140045af2  mov     bpl, r14b
0x140045af5  mov     r13b, r14b
0x140045af8  and     bpl, 3Fh
0x140045afc  shr     r13b, 7
0x140045b00  inc     bpl
0x140045b03  shr     r14b, 6
0x140045b07  and     r14b, 1
0x140045b0b  jmp     loc_140045A86
0x140045b10  cmp     rdx, rsi
0x140045b13  ja      short loc_140045B21
0x140045b15  mov     rax, rsi
0x140045b18  sub     rax, rdx
0x140045b1b  cmp     rax, 2
0x140045b1f  jnb     short loc_140045B4F
0x140045b21  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
0x140045b27  mov     rbx, [rsp+58h+arg_8]
0x140045b2c  mov     [r12], edi
0x140045b30  add     rsp, 20h
0x140045b34  pop     r15
0x140045b36  pop     r14
0x140045b38  pop     r13
0x140045b3a  pop     r12
0x140045b3c  pop     rdi
0x140045b3d  pop     rsi
0x140045b3e  pop     rbp
0x140045b3f  retn
0x140045b40  mov     [r9+8], rax
0x140045b44  jmp     loc_140045A53
0x140045b49  call    ?FailOutOfRange@?$CheckedPtr@$$CBEV?$FailAsExceptionPolicy@VFileFormatException@@@@_K@@QEBAXXZ; CheckedPtr<uchar const,FailAsExceptionPolicy<FileFormatException>,unsigned __int64>::FailOutOfRange(void)
0x140045b4f  movzx   eax, byte ptr [rdx+r15]
0x140045b54  movzx   ecx, byte ptr [rdx+r15+1]
0x140045b5a  shl     ax, 8
0x140045b5e  or      cx, ax
0x140045b61  add     edi, 2
0x140045b64  jmp     short loc_140045B6D
0x140045b66  movsx   ecx, byte ptr [rdx+r15]
0x140045b6b  inc     edi
0x140045b6d  mov     [rsp+58h+arg_10], cx
0x140045b72  jmp     loc_140045AAD
```
