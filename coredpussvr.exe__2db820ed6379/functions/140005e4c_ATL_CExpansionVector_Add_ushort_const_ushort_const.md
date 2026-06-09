# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x140005e4c`
- end: `0x1400060c5`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `633`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140006140`
- `0x140008460`
- `0x14000878c`

## callees

- `0x140001794`
- `0x1400017cc`
- `0x1400059dc`
- `0x140005e4c`
- `0x140006940`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x14000600f`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x140006034`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x14000600f`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x140006034`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  __int64 v14; // rax
  __int64 v15; // rax
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
      v14 = _o__recalloc(*(_QWORD *)v5, *((_DWORD *)v5 + 4) + 1, 8);
      if ( v14 )
      {
        *(_QWORD *)v5 = v14;
        v15 = _o__recalloc(*((_QWORD *)v5 + 1), *((_DWORD *)v5 + 4) + 1, 8);
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
      operator delete(v10);
      operator delete(v19);
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
0x140005e4c  mov     [rsp+arg_10], r8
0x140005e51  mov     [rsp+arg_8], rdx
0x140005e56  mov     [rsp+arg_0], rcx
0x140005e5b  push    rbx
0x140005e5c  push    rsi
0x140005e5d  push    rdi
0x140005e5e  push    r12
0x140005e60  push    r13
0x140005e62  push    r14
0x140005e64  push    r15
0x140005e66  sub     rsp, 40h
0x140005e6a  mov     r13, r8
0x140005e6d  mov     r15, rdx
0x140005e70  mov     r14, rcx
0x140005e73  xor     esi, esi
0x140005e75  test    rdx, rdx
0x140005e78  jz      loc_140006091
0x140005e7e  test    r8, r8
0x140005e81  jz      loc_140006091
0x140005e87  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140005e8b  mov     rax, rbx
0x140005e8e  inc     rax
0x140005e91  cmp     [rdx+rax*2], si
0x140005e95  jnz     short loc_140005E8E
0x140005e97  lea     rcx, ds:2[rax*2]
0x140005e9f  mov     [rsp+78h+SourceSize], rcx
0x140005ea4  mov     [rsp+78h+arg_18], rsi
0x140005eac  mov     eax, 2
0x140005eb1  mul     rcx
0x140005eb4  cmovb   rax, rbx
0x140005eb8  mov     rcx, rax; unsigned __int64
0x140005ebb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140005ec0  mov     r12, rax
0x140005ec3  mov     [rsp+78h+arg_18], rax
0x140005ecb  jmp     short loc_140005EF3
0x140005ecd  xor     esi, esi
0x140005ecf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140005ed3  mov     r14, [rsp+78h+arg_0]
0x140005edb  mov     r13, [rsp+78h+arg_10]
0x140005ee3  mov     r15, [rsp+78h+arg_8]
0x140005eeb  mov     r12, [rsp+78h+arg_18]
0x140005ef3  mov     rdi, r12
0x140005ef6  mov     [rsp+78h+var_48], r12
0x140005efb  mov     rcx, rbx
0x140005efe  inc     rcx
0x140005f01  cmp     [r13+rcx*2+0], si
0x140005f07  jnz     short loc_140005EFE
0x140005f09  inc     ecx
0x140005f0b  movsxd  rcx, ecx
0x140005f0e  add     rcx, rcx
0x140005f11  mov     [rsp+78h+DestinationSize], rcx
0x140005f16  mov     [rsp+78h+var_58], rsi
0x140005f1b  mov     eax, 2
0x140005f20  mul     rcx
0x140005f23  cmovb   rax, rbx
0x140005f27  mov     rcx, rax; unsigned __int64
0x140005f2a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140005f2f  mov     rbx, rax
0x140005f32  mov     [rsp+78h+var_58], rax
0x140005f37  jmp     short loc_140005F65
0x140005f39  xor     esi, esi
0x140005f3b  mov     r14, [rsp+78h+arg_0]
0x140005f43  mov     r13, [rsp+78h+arg_10]
0x140005f4b  mov     r15, [rsp+78h+arg_8]
0x140005f53  mov     r12, [rsp+78h+arg_18]
0x140005f5b  mov     rdi, [rsp+78h+var_48]
0x140005f60  mov     rbx, [rsp+78h+var_58]
0x140005f65  mov     [rsp+78h+arg_8], rbx
0x140005f6d  test    r12, r12
0x140005f70  jz      loc_140006078
0x140005f76  test    rbx, rbx
0x140005f79  jz      loc_140006078
0x140005f7f  mov     rdx, [rsp+78h+SourceSize]; DestinationSize
0x140005f84  mov     r9, rdx; SourceSize
0x140005f87  mov     r8, r15; Source
0x140005f8a  mov     rcx, r12; Destination
0x140005f8d  call    memcpy_s
0x140005f92  test    eax, eax
0x140005f94  jz      short loc_140005FBA
0x140005f96  cmp     eax, 0Ch
0x140005f99  jz      loc_1400060BA
0x140005f9f  cmp     eax, 16h
0x140005fa2  jz      loc_1400060AF
0x140005fa8  cmp     eax, 22h ; '"'
0x140005fab  jz      loc_1400060AF
0x140005fb1  cmp     eax, 50h ; 'P'
0x140005fb4  jnz     loc_1400060A4
0x140005fba  mov     r9, [rsp+78h+DestinationSize]; SourceSize
0x140005fbf  mov     r8, r13; Source
0x140005fc2  mov     rdx, r9; DestinationSize
0x140005fc5  mov     rcx, rbx; Destination
0x140005fc8  call    memcpy_s
0x140005fcd  test    eax, eax
0x140005fcf  jz      short loc_140005FF5
0x140005fd1  cmp     eax, 0Ch
0x140005fd4  jz      loc_1400060BA
0x140005fda  cmp     eax, 16h
0x140005fdd  jz      loc_1400060AF
0x140005fe3  cmp     eax, 22h ; '"'
0x140005fe6  jz      loc_1400060AF
0x140005fec  cmp     eax, 50h ; 'P'
0x140005fef  jnz     loc_1400060A4
0x140005ff5  mov     eax, [r14+10h]
0x140005ff9  mov     r15d, 1
0x140005fff  add     eax, r15d
0x140006002  movsxd  rdx, eax
0x140006005  lea     r13d, [r15+7]
0x140006009  mov     r8d, r13d
0x14000600c  mov     rcx, [r14]
0x14000600f  call    cs:__imp__o__recalloc
0x140006016  nop     dword ptr [rax+rax+00h]
0x14000601b  test    rax, rax
0x14000601e  jz      short loc_140006078
0x140006020  mov     [r14], rax
0x140006023  mov     eax, [r14+10h]
0x140006027  add     eax, r15d
0x14000602a  movsxd  rdx, eax
0x14000602d  mov     r8d, r13d
0x140006030  mov     rcx, [r14+8]
0x140006034  call    cs:__imp__o__recalloc
0x14000603b  nop     dword ptr [rax+rax+00h]
0x140006040  test    rax, rax
0x140006043  jz      short loc_140006078
0x140006045  mov     [r14+8], rax
0x140006049  movsxd  rdx, dword ptr [r14+10h]
0x14000604d  mov     rax, [r14]
0x140006050  lea     rcx, [rax+rdx*8]
0x140006054  test    rcx, rcx
0x140006057  jz      short loc_14000605C
0x140006059  mov     [rcx], r12
0x14000605c  mov     rax, [r14+8]
0x140006060  lea     rcx, [rax+rdx*8]
0x140006064  test    rcx, rcx
0x140006067  jz      short loc_14000606C
0x140006069  mov     [rcx], rbx
0x14000606c  add     [r14+10h], r15d
0x140006070  mov     rdi, rsi
0x140006073  mov     rbx, rsi
0x140006076  jmp     short loc_14000607B
0x140006078  mov     r15d, esi
0x14000607b  mov     rcx, rbx; Block
0x14000607e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006083  nop
0x140006084  mov     rcx, rdi; Block
0x140006087  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000608c  mov     eax, r15d
0x14000608f  jmp     short loc_140006093
0x140006091  xor     eax, eax
0x140006093  add     rsp, 40h
0x140006097  pop     r15
0x140006099  pop     r14
0x14000609b  pop     r13
0x14000609d  pop     r12
0x14000609f  pop     rdi
0x1400060a0  pop     rsi
0x1400060a1  pop     rbx
0x1400060a2  retn
0x1400060a4  mov     ecx, 80004005h; int
0x1400060a9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400060af  mov     ecx, 80070057h; int
0x1400060b4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400060ba  mov     ecx, 8007000Eh; int
0x1400060bf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
