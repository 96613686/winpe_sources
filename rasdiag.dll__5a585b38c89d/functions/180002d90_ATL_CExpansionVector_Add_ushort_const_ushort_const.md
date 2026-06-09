# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180002d90`
- end: `0x180003025`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `661`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003070`
- `0x18000596c`

## callees

- `0x1800011d0`
- `0x180002150`
- `0x180002d90`
- `0x18000418c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002ed1`
- `msvcrt!memcpy_s` at `0x180002f13`
- `msvcrt!memcpy_s` at `0x180002ed1`
- `msvcrt!memcpy_s` at `0x180002f13`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002fd0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002fe0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002fd0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180002fe0`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // r13
  const unsigned __int16 *v4; // r15
  ATL::CExpansionVector *v5; // r14
  __int64 v6; // rax
  unsigned __int64 v7; // rax
  void *v8; // r12
  __int64 v9; // rcx
  void *v10; // rbx
  errno_t v11; // eax
  errno_t v12; // eax
  unsigned int v13; // r15d
  void *v14; // rax
  void *v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  _QWORD *v18; // rcx
  void *v19; // rdi
  void *v21; // [rsp+20h] [rbp-58h]
  rsize_t DestinationSize; // [rsp+28h] [rbp-50h]
  void *v24; // [rsp+30h] [rbp-48h]
  rsize_t SourceSize; // [rsp+38h] [rbp-40h]
  void *v36; // [rsp+98h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = this;
  if ( a2 && a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    SourceSize = 2 * v6 + 2;
    v7 = 2 * SourceSize;
    if ( !is_mul_ok(SourceSize, 2u) )
      v7 = -1;
    try
    {
      v8 = operator new[](v7);
      v36 = v8;
    }
    catch ( ... )
    {
      v5 = this;
      v3 = a3;
      v4 = a2;
      v8 = v36;
    }
    try
    {
      v19 = v8;
      v24 = v8;
      v9 = -1;
      do
        ++v9;
      while ( v3[v9] );
      DestinationSize = 2LL * ((int)v9 + 1);
      v10 = operator new[](saturated_mul(DestinationSize, 2u));
      v21 = v10;
    }
    catch ( ... )
    {
      v5 = this;
      v3 = a3;
      v4 = a2;
      v8 = v36;
      v19 = v24;
      v10 = v21;
    }
    if ( !v8 || !v10 )
      goto LABEL_28;
    v11 = memcpy_s(v8, SourceSize, v4, SourceSize);
    if ( v11 )
    {
      if ( v11 == 12 )
        goto LABEL_33;
      if ( v11 == 22 || v11 == 34 )
        goto LABEL_32;
      if ( v11 != 80 )
        goto LABEL_31;
    }
    v12 = memcpy_s(v10, DestinationSize, v3, DestinationSize);
    if ( !v12 )
    {
LABEL_21:
      v13 = 1;
      v14 = _recalloc(*(void **)v5, *((_DWORD *)v5 + 4) + 1, 8u);
      if ( v14 )
      {
        *(_QWORD *)v5 = v14;
        v15 = _recalloc(*((void **)v5 + 1), *((_DWORD *)v5 + 4) + 1, 8u);
        if ( v15 )
        {
          *((_QWORD *)v5 + 1) = v15;
          v16 = *((int *)v5 + 4);
          v17 = (_QWORD *)(*(_QWORD *)v5 + 8 * v16);
          if ( v17 )
            *v17 = v8;
          v18 = (_QWORD *)(*((_QWORD *)v5 + 1) + 8 * v16);
          if ( v18 )
            *v18 = v10;
          ++*((_DWORD *)v5 + 4);
          v19 = 0;
          v10 = 0;
          goto LABEL_29;
        }
      }
LABEL_28:
      v13 = 0;
LABEL_29:
      operator delete[](v10);
      operator delete[](v19);
      return v13;
    }
    if ( v12 != 12 )
    {
      if ( v12 != 22 && v12 != 34 )
      {
        if ( v12 == 80 )
          goto LABEL_21;
LABEL_31:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_32:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_33:
    ATL::AtlThrowImpl(-2147024882);
  }
  return 0;
}

```

## disassembly

```asm
0x180002d90  mov     [rsp+arg_10], r8
0x180002d95  mov     [rsp+arg_8], rdx
0x180002d9a  mov     [rsp+arg_0], rcx
0x180002d9f  push    rbx
0x180002da0  push    rsi
0x180002da1  push    rdi
0x180002da2  push    r12
0x180002da4  push    r13
0x180002da6  push    r14
0x180002da8  push    r15
0x180002daa  sub     rsp, 40h
0x180002dae  mov     r13, r8
0x180002db1  mov     r15, rdx
0x180002db4  mov     r14, rcx
0x180002db7  xor     esi, esi
0x180002db9  test    rdx, rdx
0x180002dbc  jz      loc_180002FF1
0x180002dc2  test    r8, r8
0x180002dc5  jz      loc_180002FF1
0x180002dcb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002dcf  mov     rax, rbx
0x180002dd2  inc     rax
0x180002dd5  cmp     [rdx+rax*2], si
0x180002dd9  jnz     short loc_180002DD2
0x180002ddb  lea     rcx, ds:2[rax*2]
0x180002de3  mov     [rsp+78h+SourceSize], rcx
0x180002de8  mov     [rsp+78h+arg_18], rsi
0x180002df0  mov     eax, 2
0x180002df5  mul     rcx
0x180002df8  cmovb   rax, rbx
0x180002dfc  mov     rcx, rax; unsigned __int64
0x180002dff  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002e04  mov     r12, rax
0x180002e07  mov     [rsp+78h+arg_18], rax
0x180002e0f  jmp     short loc_180002E37
0x180002e11  xor     esi, esi
0x180002e13  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002e17  mov     r14, [rsp+78h+arg_0]
0x180002e1f  mov     r13, [rsp+78h+arg_10]
0x180002e27  mov     r15, [rsp+78h+arg_8]
0x180002e2f  mov     r12, [rsp+78h+arg_18]
0x180002e37  mov     rdi, r12
0x180002e3a  mov     [rsp+78h+var_48], r12
0x180002e3f  mov     rcx, rbx
0x180002e42  inc     rcx
0x180002e45  cmp     [r13+rcx*2+0], si
0x180002e4b  jnz     short loc_180002E42
0x180002e4d  inc     ecx
0x180002e4f  movsxd  rcx, ecx
0x180002e52  add     rcx, rcx
0x180002e55  mov     [rsp+78h+DestinationSize], rcx
0x180002e5a  mov     [rsp+78h+var_58], rsi
0x180002e5f  mov     eax, 2
0x180002e64  mul     rcx
0x180002e67  cmovb   rax, rbx
0x180002e6b  mov     rcx, rax; unsigned __int64
0x180002e6e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002e73  mov     rbx, rax
0x180002e76  mov     [rsp+78h+var_58], rax
0x180002e7b  jmp     short loc_180002EA9
0x180002e7d  xor     esi, esi
0x180002e7f  mov     r14, [rsp+78h+arg_0]
0x180002e87  mov     r13, [rsp+78h+arg_10]
0x180002e8f  mov     r15, [rsp+78h+arg_8]
0x180002e97  mov     r12, [rsp+78h+arg_18]
0x180002e9f  mov     rdi, [rsp+78h+var_48]
0x180002ea4  mov     rbx, [rsp+78h+var_58]
0x180002ea9  mov     [rsp+78h+arg_8], rbx
0x180002eb1  test    r12, r12
0x180002eb4  jz      loc_180002FCA
0x180002eba  test    rbx, rbx
0x180002ebd  jz      loc_180002FCA
0x180002ec3  mov     rdx, [rsp+78h+SourceSize]; DestinationSize
0x180002ec8  mov     r9, rdx; SourceSize
0x180002ecb  mov     r8, r15; Source
0x180002ece  mov     rcx, r12; Destination
0x180002ed1  call    cs:__imp_memcpy_s
0x180002ed8  nop     dword ptr [rax+rax+00h]
0x180002edd  test    eax, eax
0x180002edf  jz      short loc_180002F05
0x180002ee1  cmp     eax, 0Ch
0x180002ee4  jz      loc_18000301A
0x180002eea  cmp     eax, 16h
0x180002eed  jz      loc_18000300F
0x180002ef3  cmp     eax, 22h ; '"'
0x180002ef6  jz      loc_18000300F
0x180002efc  cmp     eax, 50h ; 'P'
0x180002eff  jnz     loc_180003004
0x180002f05  mov     r9, [rsp+78h+DestinationSize]; SourceSize
0x180002f0a  mov     r8, r13; Source
0x180002f0d  mov     rdx, r9; DestinationSize
0x180002f10  mov     rcx, rbx; Destination
0x180002f13  call    cs:__imp_memcpy_s
0x180002f1a  nop     dword ptr [rax+rax+00h]
0x180002f1f  test    eax, eax
0x180002f21  jz      short loc_180002F47
0x180002f23  cmp     eax, 0Ch
0x180002f26  jz      loc_18000301A
0x180002f2c  cmp     eax, 16h
0x180002f2f  jz      loc_18000300F
0x180002f35  cmp     eax, 22h ; '"'
0x180002f38  jz      loc_18000300F
0x180002f3e  cmp     eax, 50h ; 'P'
0x180002f41  jnz     loc_180003004
0x180002f47  mov     eax, [r14+10h]
0x180002f4b  mov     r15d, 1
0x180002f51  add     eax, r15d
0x180002f54  movsxd  rdx, eax; Count
0x180002f57  lea     r13d, [r15+7]
0x180002f5b  mov     r8d, r13d; Size
0x180002f5e  mov     rcx, [r14]; Block
0x180002f61  call    cs:__imp__recalloc
0x180002f68  nop     dword ptr [rax+rax+00h]
0x180002f6d  test    rax, rax
0x180002f70  jz      short loc_180002FCA
0x180002f72  mov     [r14], rax
0x180002f75  mov     eax, [r14+10h]
0x180002f79  add     eax, r15d
0x180002f7c  movsxd  rdx, eax; Count
0x180002f7f  mov     r8d, r13d; Size
0x180002f82  mov     rcx, [r14+8]; Block
0x180002f86  call    cs:__imp__recalloc
0x180002f8d  nop     dword ptr [rax+rax+00h]
0x180002f92  test    rax, rax
0x180002f95  jz      short loc_180002FCA
0x180002f97  mov     [r14+8], rax
0x180002f9b  movsxd  rdx, dword ptr [r14+10h]
0x180002f9f  mov     rax, [r14]
0x180002fa2  lea     rcx, [rax+rdx*8]
0x180002fa6  test    rcx, rcx
0x180002fa9  jz      short loc_180002FAE
0x180002fab  mov     [rcx], r12
0x180002fae  mov     rax, [r14+8]
0x180002fb2  lea     rcx, [rax+rdx*8]
0x180002fb6  test    rcx, rcx
0x180002fb9  jz      short loc_180002FBE
0x180002fbb  mov     [rcx], rbx
0x180002fbe  add     [r14+10h], r15d
0x180002fc2  mov     rdi, rsi
0x180002fc5  mov     rbx, rsi
0x180002fc8  jmp     short loc_180002FCD
0x180002fca  mov     r15d, esi
0x180002fcd  mov     rcx, rbx
0x180002fd0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002fd7  nop     dword ptr [rax+rax+00h]
0x180002fdc  nop
0x180002fdd  mov     rcx, rdi
0x180002fe0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180002fe7  nop     dword ptr [rax+rax+00h]
0x180002fec  mov     eax, r15d
0x180002fef  jmp     short loc_180002FF3
0x180002ff1  xor     eax, eax
0x180002ff3  add     rsp, 40h
0x180002ff7  pop     r15
0x180002ff9  pop     r14
0x180002ffb  pop     r13
0x180002ffd  pop     r12
0x180002fff  pop     rdi
0x180003000  pop     rsi
0x180003001  pop     rbx
0x180003002  retn
0x180003004  mov     ecx, 80004005h; int
0x180003009  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000300f  mov     ecx, 80070057h; int
0x180003014  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000301a  mov     ecx, 8007000Eh; int
0x18000301f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
