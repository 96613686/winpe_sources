# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x18000dc5c`
- end: `0x18000decc`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `624`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e050`
- `0x18001217c`
- `0x18001249c`

## callees

- `0x180001cf0`
- `0x18000d98c`
- `0x18000dc5c`
- `0x18000f208`

## import_xrefs

- `msvcrt!free` at `0x18000de84`
- `msvcrt!free` at `0x18000de8e`
- `msvcrt!free` at `0x18000de84`
- `msvcrt!free` at `0x18000de8e`
- `msvcrt!memcpy_s` at `0x18000dd9d`
- `msvcrt!memcpy_s` at `0x18000ddd9`
- `msvcrt!memcpy_s` at `0x18000dd9d`
- `msvcrt!memcpy_s` at `0x18000ddd9`

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
  size_t v7; // rax
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
      v8 = operator new(v7);
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
      v10 = operator new(saturated_mul(DestinationSize, 2u));
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
      free(v10);
      free(v19);
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
0x18000dc5c  mov     [rsp+arg_10], r8
0x18000dc61  mov     [rsp+arg_8], rdx
0x18000dc66  mov     [rsp+arg_0], rcx
0x18000dc6b  push    rbx
0x18000dc6c  push    rsi
0x18000dc6d  push    rdi
0x18000dc6e  push    r12
0x18000dc70  push    r13
0x18000dc72  push    r14
0x18000dc74  push    r15
0x18000dc76  sub     rsp, 40h
0x18000dc7a  mov     r13, r8
0x18000dc7d  mov     r15, rdx
0x18000dc80  mov     r14, rcx
0x18000dc83  xor     esi, esi
0x18000dc85  test    rdx, rdx
0x18000dc88  jz      loc_18000DE99
0x18000dc8e  test    r8, r8
0x18000dc91  jz      loc_18000DE99
0x18000dc97  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000dc9b  mov     rax, rbx
0x18000dc9e  inc     rax
0x18000dca1  cmp     [rdx+rax*2], si
0x18000dca5  jnz     short loc_18000DC9E
0x18000dca7  lea     rcx, ds:2[rax*2]
0x18000dcaf  mov     [rsp+78h+SourceSize], rcx
0x18000dcb4  mov     [rsp+78h+arg_18], rsi
0x18000dcbc  mov     eax, 2
0x18000dcc1  mul     rcx
0x18000dcc4  cmovb   rax, rbx
0x18000dcc8  mov     rcx, rax; Size
0x18000dccb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dcd0  mov     r12, rax
0x18000dcd3  mov     [rsp+78h+arg_18], rax
0x18000dcdb  jmp     short loc_18000DD03
0x18000dcdd  xor     esi, esi
0x18000dcdf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000dce3  mov     r14, [rsp+78h+arg_0]
0x18000dceb  mov     r13, [rsp+78h+arg_10]
0x18000dcf3  mov     r15, [rsp+78h+arg_8]
0x18000dcfb  mov     r12, [rsp+78h+arg_18]
0x18000dd03  mov     rdi, r12
0x18000dd06  mov     [rsp+78h+var_48], r12
0x18000dd0b  mov     rcx, rbx
0x18000dd0e  inc     rcx
0x18000dd11  cmp     [r13+rcx*2+0], si
0x18000dd17  jnz     short loc_18000DD0E
0x18000dd19  inc     ecx
0x18000dd1b  movsxd  rcx, ecx
0x18000dd1e  add     rcx, rcx
0x18000dd21  mov     [rsp+78h+DestinationSize], rcx
0x18000dd26  mov     [rsp+78h+var_58], rsi
0x18000dd2b  mov     eax, 2
0x18000dd30  mul     rcx
0x18000dd33  cmovb   rax, rbx
0x18000dd37  mov     rcx, rax; Size
0x18000dd3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000dd3f  mov     rbx, rax
0x18000dd42  mov     [rsp+78h+var_58], rax
0x18000dd47  jmp     short loc_18000DD75
0x18000dd49  xor     esi, esi
0x18000dd4b  mov     r14, [rsp+78h+arg_0]
0x18000dd53  mov     r13, [rsp+78h+arg_10]
0x18000dd5b  mov     r15, [rsp+78h+arg_8]
0x18000dd63  mov     r12, [rsp+78h+arg_18]
0x18000dd6b  mov     rdi, [rsp+78h+var_48]
0x18000dd70  mov     rbx, [rsp+78h+var_58]
0x18000dd75  mov     [rsp+78h+arg_8], rbx
0x18000dd7d  test    r12, r12
0x18000dd80  jz      loc_18000DE7E
0x18000dd86  test    rbx, rbx
0x18000dd89  jz      loc_18000DE7E
0x18000dd8f  mov     rdx, [rsp+78h+SourceSize]; DestinationSize
0x18000dd94  mov     r9, rdx; SourceSize
0x18000dd97  mov     r8, r15; Source
0x18000dd9a  mov     rcx, r12; Destination
0x18000dd9d  call    cs:__imp_memcpy_s
0x18000dda3  test    eax, eax
0x18000dda5  jz      short loc_18000DDCB
0x18000dda7  cmp     eax, 0Ch
0x18000ddaa  jz      loc_18000DEC1
0x18000ddb0  cmp     eax, 16h
0x18000ddb3  jz      loc_18000DEB6
0x18000ddb9  cmp     eax, 22h ; '"'
0x18000ddbc  jz      loc_18000DEB6
0x18000ddc2  cmp     eax, 50h ; 'P'
0x18000ddc5  jnz     loc_18000DEAB
0x18000ddcb  mov     r9, [rsp+78h+DestinationSize]; SourceSize
0x18000ddd0  mov     r8, r13; Source
0x18000ddd3  mov     rdx, r9; DestinationSize
0x18000ddd6  mov     rcx, rbx; Destination
0x18000ddd9  call    cs:__imp_memcpy_s
0x18000dddf  test    eax, eax
0x18000dde1  jz      short loc_18000DE07
0x18000dde3  cmp     eax, 0Ch
0x18000dde6  jz      loc_18000DEC1
0x18000ddec  cmp     eax, 16h
0x18000ddef  jz      loc_18000DEB6
0x18000ddf5  cmp     eax, 22h ; '"'
0x18000ddf8  jz      loc_18000DEB6
0x18000ddfe  cmp     eax, 50h ; 'P'
0x18000de01  jnz     loc_18000DEAB
0x18000de07  mov     eax, [r14+10h]
0x18000de0b  mov     r15d, 1
0x18000de11  add     eax, r15d
0x18000de14  movsxd  rdx, eax; Count
0x18000de17  lea     r13d, [r15+7]
0x18000de1b  mov     r8d, r13d; Size
0x18000de1e  mov     rcx, [r14]; Block
0x18000de21  call    cs:__imp__recalloc
0x18000de27  test    rax, rax
0x18000de2a  jz      short loc_18000DE7E
0x18000de2c  mov     [r14], rax
0x18000de2f  mov     eax, [r14+10h]
0x18000de33  add     eax, r15d
0x18000de36  movsxd  rdx, eax; Count
0x18000de39  mov     r8d, r13d; Size
0x18000de3c  mov     rcx, [r14+8]; Block
0x18000de40  call    cs:__imp__recalloc
0x18000de46  test    rax, rax
0x18000de49  jz      short loc_18000DE7E
0x18000de4b  mov     [r14+8], rax
0x18000de4f  movsxd  rdx, dword ptr [r14+10h]
0x18000de53  mov     rax, [r14]
0x18000de56  lea     rcx, [rax+rdx*8]
0x18000de5a  test    rcx, rcx
0x18000de5d  jz      short loc_18000DE62
0x18000de5f  mov     [rcx], r12
0x18000de62  mov     rax, [r14+8]
0x18000de66  lea     rcx, [rax+rdx*8]
0x18000de6a  test    rcx, rcx
0x18000de6d  jz      short loc_18000DE72
0x18000de6f  mov     [rcx], rbx
0x18000de72  add     [r14+10h], r15d
0x18000de76  mov     rdi, rsi
0x18000de79  mov     rbx, rsi
0x18000de7c  jmp     short loc_18000DE81
0x18000de7e  mov     r15d, esi
0x18000de81  mov     rcx, rbx; Block
0x18000de84  call    cs:__imp_free
0x18000de8a  nop
0x18000de8b  mov     rcx, rdi; Block
0x18000de8e  call    cs:__imp_free
0x18000de94  mov     eax, r15d
0x18000de97  jmp     short loc_18000DE9B
0x18000de99  xor     eax, eax
0x18000de9b  add     rsp, 40h
0x18000de9f  pop     r15
0x18000dea1  pop     r14
0x18000dea3  pop     r13
0x18000dea5  pop     r12
0x18000dea7  pop     rdi
0x18000dea8  pop     rsi
0x18000dea9  pop     rbx
0x18000deaa  retn
0x18000deab  mov     ecx, 80004005h; int
0x18000deb0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000deb6  mov     ecx, 80070057h; int
0x18000debb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000dec1  mov     ecx, 8007000Eh; int
0x18000dec6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
