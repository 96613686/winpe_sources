# Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(Marshal::JsonParser &,utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)

- ea: `0x140010e48`
- end: `0x14001116c`
- name: `??$FromJsonValue@UPackageAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@utl@@@utl@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z`
- size: `804`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x140011650`

## callees

- `0x140002344`
- `0x14000c7a8`
- `0x140010c74`
- `0x140010e48`
- `0x140013cf4`
- `0x140015a38`
- `0x14001fd1c`
- `0x14001ffac`

## string_xrefs

- `0x140011148`: `onecore\internal\vm\inc\marshaljsonutl.h`
- `0x14001115a`: `onecore\internal\vm\inc\marshaljsonutl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(
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
        std::vector<Container::Manager::Image::PackageAdjustment>::_Emplace_reallocate<Container::Manager::Image::PackageAdjustment>(
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
        *(_DWORD *)(v9 + 36) = *(_DWORD *)(v10 + 36);
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
  v14 = Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(a1, &v33, a3);
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
      && (unsigned __int8)utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>>::_SetCapacity(a2) )
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
        && (unsigned __int8)utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>>::_SetCapacity(a2) )
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
        *(_DWORD *)(v29 + 36) = *(_DWORD *)(v24 + 36);
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
0x140010e48  push    rbp
0x140010e4a  push    rbx
0x140010e4b  push    rsi
0x140010e4c  push    rdi
0x140010e4d  push    r12
0x140010e4f  push    r14
0x140010e51  push    r15
0x140010e53  mov     rbp, rsp
0x140010e56  sub     rsp, 40h
0x140010e5a  mov     rsi, r8
0x140010e5d  mov     rdi, rdx
0x140010e60  mov     r14, rcx
0x140010e63  xorps   xmm0, xmm0
0x140010e66  movdqu  [rbp+var_20], xmm0
0x140010e6b  xor     r9d, r9d
0x140010e6e  mov     [rbp+var_10], r9
0x140010e72  xor     ebx, ebx
0x140010e74  mov     r8, [rdx]
0x140010e77  mov     rax, [rdx+8]
0x140010e7b  sub     rax, r8
0x140010e7e  sar     rax, 3
0x140010e82  mov     r15, 0CCCCCCCCCCCCCCCDh
0x140010e8c  imul    rax, r15
0x140010e90  test    rax, rax
0x140010e93  jz      loc_140010F4F
0x140010e99  mov     rdx, qword ptr [rbp+var_20+8]
0x140010e9d  movsxd  rax, ebx
0x140010ea0  lea     rcx, [rax+rax*4]
0x140010ea4  lea     r8, [r8+rcx*8]
0x140010ea8  cmp     rdx, r9
0x140010eab  jz      short loc_140010F1D
0x140010ead  lea     rcx, [r8+10h]
0x140010eb1  mov     rax, [r8]
0x140010eb4  lea     r9, [rdx+10h]
0x140010eb8  cmp     rax, rcx
0x140010ebb  jnz     short loc_140010EE4
0x140010ebd  mov     [rdx], r9
0x140010ec0  mov     rax, [r8+8]
0x140010ec4  sub     rax, r8
0x140010ec7  sub     rax, 10h
0x140010ecb  sar     rax, 1
0x140010ece  add     rax, 8
0x140010ed2  lea     rax, [rdx+rax*2]
0x140010ed6  mov     [rdx+8], rax
0x140010eda  movups  xmm0, xmmword ptr [rcx]
0x140010edd  movdqu  xmmword ptr [r9], xmm0
0x140010ee2  jmp     short loc_140010EF5
0x140010ee4  mov     [rdx], rax
0x140010ee7  mov     rax, [r8+8]
0x140010eeb  mov     [rdx+8], rax
0x140010eef  mov     rax, [rcx]
0x140010ef2  mov     [r9], rax
0x140010ef5  mov     [r8], rcx
0x140010ef8  mov     [r8+8], rcx
0x140010efc  xor     eax, eax
0x140010efe  mov     [rcx], ax
0x140010f01  mov     eax, [r8+20h]
0x140010f05  mov     [rdx+20h], eax
0x140010f08  mov     eax, [r8+24h]
0x140010f0c  mov     [rdx+24h], eax
0x140010f0f  mov     rdx, qword ptr [rbp+var_20+8]
0x140010f13  add     rdx, 28h ; '('
0x140010f17  mov     qword ptr [rbp+var_20+8], rdx
0x140010f1b  jmp     short loc_140010F2A
0x140010f1d  lea     rcx, [rbp+var_20]
0x140010f21  call    ??$_Emplace_reallocate@UPackageAdjustment@Image@Manager@Container@@@?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAUPackageAdjustment@Image@Manager@Container@@QEAU2345@$$QEAU2345@@Z; std::vector<Container::Manager::Image::PackageAdjustment>::_Emplace_reallocate<Container::Manager::Image::PackageAdjustment>(Container::Manager::Image::PackageAdjustment * const,Container::Manager::Image::PackageAdjustment &&)
0x140010f26  mov     rdx, qword ptr [rbp+var_20+8]
0x140010f2a  inc     ebx
0x140010f2c  mov     r8, [rdi]
0x140010f2f  mov     rcx, [rdi+8]
0x140010f33  sub     rcx, r8
0x140010f36  sar     rcx, 3
0x140010f3a  imul    rcx, r15
0x140010f3e  movsxd  rax, ebx
0x140010f41  cmp     rax, rcx
0x140010f44  jnb     short loc_140010F4F
0x140010f46  mov     r9, [rbp+var_10]
0x140010f4a  jmp     loc_140010E9D
0x140010f4f  mov     r8, rsi
0x140010f52  lea     rdx, [rbp+var_20]
0x140010f56  mov     rcx, r14
0x140010f59  call    ??$FromJsonValue@UPackageAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@std@@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(Marshal::JsonParser &,std::vector<Container::Manager::Image::PackageAdjustment> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)
0x140010f5e  mov     r14b, al
0x140010f61  test    al, al
0x140010f63  jz      loc_140011126
0x140010f69  mov     rsi, [rdi]
0x140010f6c  mov     rcx, [rdi+8]
0x140010f70  mov     [rdi+8], rsi
0x140010f74  sub     rcx, rsi
0x140010f77  mov     rax, 6666666666666667h
0x140010f81  imul    rcx
0x140010f84  mov     rbx, rdx
0x140010f87  sar     rbx, 4
0x140010f8b  mov     rcx, rbx
0x140010f8e  shr     rcx, 3Fh
0x140010f92  add     rbx, rcx
0x140010f95  jz      short loc_140010FC0
0x140010f97  dec     rbx
0x140010f9a  lea     rax, [rbx+rbx*4]
0x140010f9e  mov     rcx, [rsi+rax*8]; void *
0x140010fa2  lea     rax, [rax+2]
0x140010fa6  lea     rax, [rsi+rax*8]
0x140010faa  cmp     rcx, rax
0x140010fad  jz      short loc_140010FBB
0x140010faf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010fb6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140010fbb  test    rbx, rbx
0x140010fbe  jnz     short loc_140010F97
0x140010fc0  mov     rcx, qword ptr [rbp+var_20+8]
0x140010fc4  sub     rcx, qword ptr [rbp+var_20]
0x140010fc8  sar     rcx, 3
0x140010fcc  imul    rcx, r15
0x140010fd0  mov     rax, [rdi+10h]
0x140010fd4  sub     rax, [rdi]
0x140010fd7  sar     rax, 3
0x140010fdb  imul    rax, r15
0x140010fdf  mov     r12, 333333333333333h
0x140010fe9  cmp     rcx, rax
0x140010fec  jbe     short loc_14001101D
0x140010fee  shr     rax, 2
0x140010ff2  imul    rdx, rax, 7
0x140010ff6  add     rdx, 8
0x140010ffa  cmp     rdx, rcx
0x140010ffd  cmovb   rdx, rcx
0x140011001  cmp     rdx, r12
0x140011004  cmova   rdx, r12
0x140011008  cmp     rcx, rdx
0x14001100b  ja      short loc_140011019
0x14001100d  mov     rcx, rdi
0x140011010  call    ?_SetCapacity@?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>>::_SetCapacity(unsigned __int64)
0x140011015  test    al, al
0x140011017  jnz     short loc_14001101D
0x140011019  mov     al, 1
0x14001101b  jmp     short loc_14001101F
0x14001101d  xor     al, al
0x14001101f  mov     rcx, [rbp+38h]; this
0x140011023  test    al, al
0x140011025  jnz     loc_140011142
0x14001102b  xor     esi, esi
0x14001102d  mov     rax, qword ptr [rbp+var_20+8]
0x140011031  sub     rax, qword ptr [rbp+var_20]
0x140011035  sar     rax, 3
0x140011039  imul    rax, r15
0x14001103d  test    rax, rax
0x140011040  jz      loc_140011126
0x140011046  movsxd  rax, esi
0x140011049  lea     rcx, [rax+rax*4]
0x14001104d  mov     rax, qword ptr [rbp+var_20]
0x140011051  lea     rbx, [rax+rcx*8]
0x140011055  mov     rcx, [rdi+10h]
0x140011059  cmp     [rdi+8], rcx
0x14001105d  jnz     short loc_140011095
0x14001105f  sub     rcx, [rdi]
0x140011062  sar     rcx, 3
0x140011066  imul    rcx, r15
0x14001106a  mov     rax, rcx
0x14001106d  shr     rax, 2
0x140011071  imul    rdx, rax, 7
0x140011075  add     rdx, 8
0x140011079  cmp     rdx, r12
0x14001107c  cmova   rdx, r12
0x140011080  cmp     rcx, rdx
0x140011083  jnb     short loc_140011091
0x140011085  mov     rcx, rdi
0x140011088  call    ?_SetCapacity@?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Image::PackageAdjustment,utl::allocator<Container::Manager::Image::PackageAdjustment>>::_SetCapacity(unsigned __int64)
0x14001108d  test    al, al
0x14001108f  jnz     short loc_140011095
0x140011091  mov     al, 1
0x140011093  jmp     short loc_140011100
0x140011095  mov     rcx, [rdi+8]
0x140011099  lea     rdx, [rbx+10h]
0x14001109d  mov     rax, [rbx]
0x1400110a0  lea     r8, [rcx+10h]
0x1400110a4  cmp     rax, rdx
0x1400110a7  jnz     short loc_1400110D0
0x1400110a9  mov     [rcx], r8
0x1400110ac  mov     rax, [rbx+8]
0x1400110b0  sub     rax, rbx
0x1400110b3  sub     rax, 10h
0x1400110b7  sar     rax, 1
0x1400110ba  add     rax, 8
0x1400110be  lea     rax, [rcx+rax*2]
0x1400110c2  mov     [rcx+8], rax
0x1400110c6  movups  xmm0, xmmword ptr [rdx]
0x1400110c9  movdqu  xmmword ptr [r8], xmm0
0x1400110ce  jmp     short loc_1400110E1
0x1400110d0  mov     [rcx], rax
0x1400110d3  mov     rax, [rbx+8]
0x1400110d7  mov     [rcx+8], rax
0x1400110db  mov     rax, [rdx]
0x1400110de  mov     [r8], rax
0x1400110e1  mov     [rbx], rdx
0x1400110e4  mov     [rbx+8], rdx
0x1400110e8  xor     eax, eax
0x1400110ea  mov     [rdx], ax
0x1400110ed  mov     eax, [rbx+20h]
0x1400110f0  mov     [rcx+20h], eax
0x1400110f3  mov     eax, [rbx+24h]
0x1400110f6  mov     [rcx+24h], eax
0x1400110f9  add     qword ptr [rdi+8], 28h ; '('
0x1400110fe  xor     al, al
0x140011100  mov     rcx, [rbp+38h]; this
0x140011104  test    al, al
0x140011106  jnz     short loc_14001115A
0x140011108  inc     esi
0x14001110a  mov     rcx, qword ptr [rbp+var_20+8]
0x14001110e  sub     rcx, qword ptr [rbp+var_20]
0x140011112  sar     rcx, 3
0x140011116  imul    rcx, r15
0x14001111a  movsxd  rax, esi
0x14001111d  cmp     rax, rcx
0x140011120  jb      loc_140011046
0x140011126  lea     rcx, [rbp+var_20]
0x14001112a  call    ??1?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ; std::vector<Container::Manager::Image::PackageAdjustment>::~vector<Container::Manager::Image::PackageAdjustment>(void)
0x14001112f  mov     al, r14b
0x140011132  add     rsp, 40h
0x140011136  pop     r15
0x140011138  pop     r14
0x14001113a  pop     r12
0x14001113c  pop     rdi
0x14001113d  pop     rsi
0x14001113e  pop     rbx
0x14001113f  pop     rbp
0x140011140  retn
0x140011142  mov     r9d, 8007000Eh; char *
0x140011148  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\marshaljson"...
0x14001114f  mov     edx, 78h ; 'x'; void *
0x140011154  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14001115a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\marshaljson"...
0x140011161  mov     edx, 7Fh; void *
0x140011166  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
