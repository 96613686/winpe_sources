# Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(Marshal::JsonParser &,utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)

- ea: `0x1400108f8`
- end: `0x140010c0f`
- name: `??$FromJsonValue@UFeatureAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@utl@@@utl@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z`
- size: `791`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x140011640`

## callees

- `0x140002344`
- `0x14000c7a8`
- `0x140010724`
- `0x1400108f8`
- `0x140013b08`
- `0x140015a38`
- `0x14001fb90`
- `0x14001ffac`

## string_xrefs

- `0x140010beb`: `onecore\internal\vm\inc\marshaljsonutl.h`
- `0x140010bfd`: `onecore\internal\vm\inc\marshaljsonutl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(
        __int64 a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v6; // r9
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  _OWORD *v11; // rcx
  _OWORD *v12; // r9
  const char *v13; // r9
  char v14; // r14
  __int64 v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rbx
  void *v18; // rcx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rax
  unsigned __int64 v21; // rdx
  char v22; // al
  int i; // esi
  __int64 v24; // rbx
  __int64 v25; // rcx
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  char v28; // al
  __int64 v29; // rcx
  _OWORD *v30; // rdx
  _OWORD *v31; // r8
  __int128 v33; // [rsp+20h] [rbp-20h] BYREF
  __int64 v34; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]

  v33 = 0;
  v6 = 0;
  v34 = 0;
  v7 = 0;
  v8 = *a2;
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((a2[1] - *a2) >> 3) )
  {
    v9 = *((_QWORD *)&v33 + 1);
    while ( 1 )
    {
      v10 = v8 + 40LL * v7;
      if ( v9 == v6 )
      {
        std::vector<Container::Manager::Image::FeatureAdjustment>::_Emplace_reallocate<Container::Manager::Image::FeatureAdjustment>(
          &v33,
          v9,
          v10);
        v9 = *((_QWORD *)&v33 + 1);
      }
      else
      {
        v11 = (_OWORD *)(v10 + 16);
        v12 = (_OWORD *)(v9 + 16);
        if ( *(_QWORD *)v10 == v10 + 16 )
        {
          *(_QWORD *)v9 = v12;
          *(_QWORD *)(v9 + 8) = v9 + 2 * (((*(_QWORD *)(v10 + 8) - v10 - 16) >> 1) + 8);
          *v12 = *v11;
        }
        else
        {
          *(_QWORD *)v9 = *(_QWORD *)v10;
          *(_QWORD *)(v9 + 8) = *(_QWORD *)(v10 + 8);
          *(_QWORD *)v12 = *(_QWORD *)v11;
        }
        *(_QWORD *)v10 = v11;
        *(_QWORD *)(v10 + 8) = v11;
        *(_WORD *)v11 = 0;
        *(_DWORD *)(v9 + 32) = *(_DWORD *)(v10 + 32);
        v9 = *((_QWORD *)&v33 + 1) + 40LL;
        *((_QWORD *)&v33 + 1) += 40LL;
      }
      ++v7;
      v8 = *a2;
      if ( v7 >= 0xCCCCCCCCCCCCCCCDuLL * ((a2[1] - *a2) >> 3) )
        break;
      v6 = v34;
    }
  }
  v14 = Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(a1, &v33, a3);
  if ( v14 )
  {
    v15 = *a2;
    v16 = a2[1];
    a2[1] = *a2;
    v17 = (v16 - v15) / 40;
    while ( v17 )
    {
      --v17;
      v18 = *(void **)(v15 + 40 * v17);
      if ( v18 != (void *)(v15 + 8 * (5 * v17 + 2)) )
        operator delete(v18, (const struct std::nothrow_t *)&std::nothrow);
    }
    v19 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v33 + 1) - v33) >> 3);
    v20 = 0xCCCCCCCCCCCCCCCDuLL * ((a2[2] - *a2) >> 3);
    if ( v19 <= v20 )
      goto LABEL_24;
    v21 = 7 * (v20 >> 2) + 8;
    if ( v21 < v19 )
      v21 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v33 + 1) - v33) >> 3);
    if ( v21 > 0x333333333333333LL )
      v21 = 0x333333333333333LL;
    if ( v19 <= v21
      && (unsigned __int8)utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>>::_SetCapacity(a2) )
    {
LABEL_24:
      v22 = 0;
    }
    else
    {
      v22 = 1;
    }
    if ( v22 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
        (const char *)0x8007000ELL,
        v33);
    for ( i = 0; i < 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v33 + 1) - v33) >> 3); ++i )
    {
      v24 = v33 + 40LL * i;
      v25 = a2[2];
      if ( a2[1] != v25 )
        goto LABEL_33;
      v26 = 0xCCCCCCCCCCCCCCCDuLL * ((v25 - *a2) >> 3);
      v27 = 7 * (v26 >> 2) + 8;
      if ( v27 > 0x333333333333333LL )
        v27 = 0x333333333333333LL;
      if ( v26 < v27
        && (unsigned __int8)utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>>::_SetCapacity(a2) )
      {
LABEL_33:
        v29 = a2[1];
        v30 = (_OWORD *)(v24 + 16);
        v31 = (_OWORD *)(v29 + 16);
        if ( *(_QWORD *)v24 == v24 + 16 )
        {
          *(_QWORD *)v29 = v31;
          *(_QWORD *)(v29 + 8) = v29 + 2 * (((*(_QWORD *)(v24 + 8) - v24 - 16) >> 1) + 8);
          *v31 = *v30;
        }
        else
        {
          *(_QWORD *)v29 = *(_QWORD *)v24;
          *(_QWORD *)(v29 + 8) = *(_QWORD *)(v24 + 8);
          *(_QWORD *)v31 = *(_QWORD *)v30;
        }
        *(_QWORD *)v24 = v30;
        *(_QWORD *)(v24 + 8) = v30;
        *(_WORD *)v30 = 0;
        *(_DWORD *)(v29 + 32) = *(_DWORD *)(v24 + 32);
        a2[1] += 40;
        v28 = 0;
      }
      else
      {
        v28 = 1;
      }
      if ( v28 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x7F,
          (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
          v13);
    }
  }
  std::vector<Container::Manager::Image::PackageAdjustment>::~vector<Container::Manager::Image::PackageAdjustment>(&v33);
  return v14;
}

```

## disassembly

```asm
0x1400108f8  push    rbp
0x1400108fa  push    rbx
0x1400108fb  push    rsi
0x1400108fc  push    rdi
0x1400108fd  push    r12
0x1400108ff  push    r14
0x140010901  push    r15
0x140010903  mov     rbp, rsp
0x140010906  sub     rsp, 40h
0x14001090a  mov     rsi, r8
0x14001090d  mov     rdi, rdx
0x140010910  mov     r14, rcx
0x140010913  xorps   xmm0, xmm0
0x140010916  movdqu  [rbp+var_20], xmm0
0x14001091b  xor     r9d, r9d
0x14001091e  mov     [rbp+var_10], r9
0x140010922  xor     ebx, ebx
0x140010924  mov     r8, [rdx]
0x140010927  mov     rax, [rdx+8]
0x14001092b  sub     rax, r8
0x14001092e  sar     rax, 3
0x140010932  mov     r15, 0CCCCCCCCCCCCCCCDh
0x14001093c  imul    rax, r15
0x140010940  test    rax, rax
0x140010943  jz      loc_1400109F8
0x140010949  mov     rdx, qword ptr [rbp+var_20+8]
0x14001094d  movsxd  rax, ebx
0x140010950  lea     rcx, [rax+rax*4]
0x140010954  lea     r8, [r8+rcx*8]
0x140010958  cmp     rdx, r9
0x14001095b  jz      short loc_1400109C6
0x14001095d  lea     rcx, [r8+10h]
0x140010961  mov     rax, [r8]
0x140010964  lea     r9, [rdx+10h]
0x140010968  cmp     rax, rcx
0x14001096b  jnz     short loc_140010994
0x14001096d  mov     [rdx], r9
0x140010970  mov     rax, [r8+8]
0x140010974  sub     rax, r8
0x140010977  sub     rax, 10h
0x14001097b  sar     rax, 1
0x14001097e  add     rax, 8
0x140010982  lea     rax, [rdx+rax*2]
0x140010986  mov     [rdx+8], rax
0x14001098a  movups  xmm0, xmmword ptr [rcx]
0x14001098d  movdqu  xmmword ptr [r9], xmm0
0x140010992  jmp     short loc_1400109A5
0x140010994  mov     [rdx], rax
0x140010997  mov     rax, [r8+8]
0x14001099b  mov     [rdx+8], rax
0x14001099f  mov     rax, [rcx]
0x1400109a2  mov     [r9], rax
0x1400109a5  mov     [r8], rcx
0x1400109a8  mov     [r8+8], rcx
0x1400109ac  xor     eax, eax
0x1400109ae  mov     [rcx], ax
0x1400109b1  mov     eax, [r8+20h]
0x1400109b5  mov     [rdx+20h], eax
0x1400109b8  mov     rdx, qword ptr [rbp+var_20+8]
0x1400109bc  add     rdx, 28h ; '('
0x1400109c0  mov     qword ptr [rbp+var_20+8], rdx
0x1400109c4  jmp     short loc_1400109D3
0x1400109c6  lea     rcx, [rbp+var_20]
0x1400109ca  call    ??$_Emplace_reallocate@UFeatureAdjustment@Image@Manager@Container@@@?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAUFeatureAdjustment@Image@Manager@Container@@QEAU2345@$$QEAU2345@@Z; std::vector<Container::Manager::Image::FeatureAdjustment>::_Emplace_reallocate<Container::Manager::Image::FeatureAdjustment>(Container::Manager::Image::FeatureAdjustment * const,Container::Manager::Image::FeatureAdjustment &&)
0x1400109cf  mov     rdx, qword ptr [rbp+var_20+8]
0x1400109d3  inc     ebx
0x1400109d5  mov     r8, [rdi]
0x1400109d8  mov     rcx, [rdi+8]
0x1400109dc  sub     rcx, r8
0x1400109df  sar     rcx, 3
0x1400109e3  imul    rcx, r15
0x1400109e7  movsxd  rax, ebx
0x1400109ea  cmp     rax, rcx
0x1400109ed  jnb     short loc_1400109F8
0x1400109ef  mov     r9, [rbp+var_10]
0x1400109f3  jmp     loc_14001094D
0x1400109f8  mov     r8, rsi
0x1400109fb  lea     rdx, [rbp+var_20]
0x1400109ff  mov     rcx, r14
0x140010a02  call    ??$FromJsonValue@UFeatureAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@std@@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(Marshal::JsonParser &,std::vector<Container::Manager::Image::FeatureAdjustment> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)
0x140010a07  mov     r14b, al
0x140010a0a  test    al, al
0x140010a0c  jz      loc_140010BC9
0x140010a12  mov     rsi, [rdi]
0x140010a15  mov     rcx, [rdi+8]
0x140010a19  mov     [rdi+8], rsi
0x140010a1d  sub     rcx, rsi
0x140010a20  mov     rax, 6666666666666667h
0x140010a2a  imul    rcx
0x140010a2d  mov     rbx, rdx
0x140010a30  sar     rbx, 4
0x140010a34  mov     rcx, rbx
0x140010a37  shr     rcx, 3Fh
0x140010a3b  add     rbx, rcx
0x140010a3e  jz      short loc_140010A69
0x140010a40  dec     rbx
0x140010a43  lea     rax, [rbx+rbx*4]
0x140010a47  mov     rcx, [rsi+rax*8]; void *
0x140010a4b  lea     rax, [rax+2]
0x140010a4f  lea     rax, [rsi+rax*8]
0x140010a53  cmp     rcx, rax
0x140010a56  jz      short loc_140010A64
0x140010a58  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010a5f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140010a64  test    rbx, rbx
0x140010a67  jnz     short loc_140010A40
0x140010a69  mov     rcx, qword ptr [rbp+var_20+8]
0x140010a6d  sub     rcx, qword ptr [rbp+var_20]
0x140010a71  sar     rcx, 3
0x140010a75  imul    rcx, r15
0x140010a79  mov     rax, [rdi+10h]
0x140010a7d  sub     rax, [rdi]
0x140010a80  sar     rax, 3
0x140010a84  imul    rax, r15
0x140010a88  mov     r12, 333333333333333h
0x140010a92  cmp     rcx, rax
0x140010a95  jbe     short loc_140010AC6
0x140010a97  shr     rax, 2
0x140010a9b  imul    rdx, rax, 7
0x140010a9f  add     rdx, 8
0x140010aa3  cmp     rdx, rcx
0x140010aa6  cmovb   rdx, rcx
0x140010aaa  cmp     rdx, r12
0x140010aad  cmova   rdx, r12
0x140010ab1  cmp     rcx, rdx
0x140010ab4  ja      short loc_140010AC2
0x140010ab6  mov     rcx, rdi
0x140010ab9  call    ?_SetCapacity@?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>>::_SetCapacity(unsigned __int64)
0x140010abe  test    al, al
0x140010ac0  jnz     short loc_140010AC6
0x140010ac2  mov     al, 1
0x140010ac4  jmp     short loc_140010AC8
0x140010ac6  xor     al, al
0x140010ac8  mov     rcx, [rbp+38h]; this
0x140010acc  test    al, al
0x140010ace  jnz     loc_140010BE5
0x140010ad4  xor     esi, esi
0x140010ad6  mov     rax, qword ptr [rbp+var_20+8]
0x140010ada  sub     rax, qword ptr [rbp+var_20]
0x140010ade  sar     rax, 3
0x140010ae2  imul    rax, r15
0x140010ae6  test    rax, rax
0x140010ae9  jz      loc_140010BC9
0x140010aef  movsxd  rax, esi
0x140010af2  lea     rcx, [rax+rax*4]
0x140010af6  mov     rax, qword ptr [rbp+var_20]
0x140010afa  lea     rbx, [rax+rcx*8]
0x140010afe  mov     rcx, [rdi+10h]
0x140010b02  cmp     [rdi+8], rcx
0x140010b06  jnz     short loc_140010B3E
0x140010b08  sub     rcx, [rdi]
0x140010b0b  sar     rcx, 3
0x140010b0f  imul    rcx, r15
0x140010b13  mov     rax, rcx
0x140010b16  shr     rax, 2
0x140010b1a  imul    rdx, rax, 7
0x140010b1e  add     rdx, 8
0x140010b22  cmp     rdx, r12
0x140010b25  cmova   rdx, r12
0x140010b29  cmp     rcx, rdx
0x140010b2c  jnb     short loc_140010B3A
0x140010b2e  mov     rcx, rdi
0x140010b31  call    ?_SetCapacity@?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Image::FeatureAdjustment,utl::allocator<Container::Manager::Image::FeatureAdjustment>>::_SetCapacity(unsigned __int64)
0x140010b36  test    al, al
0x140010b38  jnz     short loc_140010B3E
0x140010b3a  mov     al, 1
0x140010b3c  jmp     short loc_140010BA3
0x140010b3e  mov     rcx, [rdi+8]
0x140010b42  lea     rdx, [rbx+10h]
0x140010b46  mov     rax, [rbx]
0x140010b49  lea     r8, [rcx+10h]
0x140010b4d  cmp     rax, rdx
0x140010b50  jnz     short loc_140010B79
0x140010b52  mov     [rcx], r8
0x140010b55  mov     rax, [rbx+8]
0x140010b59  sub     rax, rbx
0x140010b5c  sub     rax, 10h
0x140010b60  sar     rax, 1
0x140010b63  add     rax, 8
0x140010b67  lea     rax, [rcx+rax*2]
0x140010b6b  mov     [rcx+8], rax
0x140010b6f  movups  xmm0, xmmword ptr [rdx]
0x140010b72  movdqu  xmmword ptr [r8], xmm0
0x140010b77  jmp     short loc_140010B8A
0x140010b79  mov     [rcx], rax
0x140010b7c  mov     rax, [rbx+8]
0x140010b80  mov     [rcx+8], rax
0x140010b84  mov     rax, [rdx]
0x140010b87  mov     [r8], rax
0x140010b8a  mov     [rbx], rdx
0x140010b8d  mov     [rbx+8], rdx
0x140010b91  xor     eax, eax
0x140010b93  mov     [rdx], ax
0x140010b96  mov     eax, [rbx+20h]
0x140010b99  mov     [rcx+20h], eax
0x140010b9c  add     qword ptr [rdi+8], 28h ; '('
0x140010ba1  xor     al, al
0x140010ba3  mov     rcx, [rbp+38h]; this
0x140010ba7  test    al, al
0x140010ba9  jnz     short loc_140010BFD
0x140010bab  inc     esi
0x140010bad  mov     rcx, qword ptr [rbp+var_20+8]
0x140010bb1  sub     rcx, qword ptr [rbp+var_20]
0x140010bb5  sar     rcx, 3
0x140010bb9  imul    rcx, r15
0x140010bbd  movsxd  rax, esi
0x140010bc0  cmp     rax, rcx
0x140010bc3  jb      loc_140010AEF
0x140010bc9  lea     rcx, [rbp+var_20]
0x140010bcd  call    ??1?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ; std::vector<Container::Manager::Image::PackageAdjustment>::~vector<Container::Manager::Image::PackageAdjustment>(void)
0x140010bd2  mov     al, r14b
0x140010bd5  add     rsp, 40h
0x140010bd9  pop     r15
0x140010bdb  pop     r14
0x140010bdd  pop     r12
0x140010bdf  pop     rdi
0x140010be0  pop     rsi
0x140010be1  pop     rbx
0x140010be2  pop     rbp
0x140010be3  retn
0x140010be5  mov     r9d, 8007000Eh; char *
0x140010beb  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\marshaljson"...
0x140010bf2  mov     edx, 78h ; 'x'; void *
0x140010bf7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140010bfd  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\marshaljson"...
0x140010c04  mov     edx, 7Fh; void *
0x140010c09  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
