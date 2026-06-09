# Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(Marshal::JsonParser &,utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)

- ea: `0x140010448`
- end: `0x1400106c1`
- name: `??$FromJsonValue@UCommandAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@utl@@@utl@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140011630`

## callees

- `0x140002344`
- `0x14000c7a8`
- `0x140010274`
- `0x140010448`
- `0x140013914`
- `0x140014ffc`
- `0x14001596c`
- `0x14001f9f8`
- `0x14001ffac`

## string_xrefs

- `0x14001069a`: `onecore\internal\vm\inc\marshaljsonutl.h`
- `0x1400106ac`: `onecore\internal\vm\inc\marshaljsonutl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(
        __int64 a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v6; // r9
  int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // rdx
  _DWORD *v10; // r8
  _QWORD *v11; // rcx
  _OWORD *v12; // r8
  _OWORD *v13; // r9
  char v14; // r14
  __int64 v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rbx
  void *v18; // rcx
  __int64 v19; // r8
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rdx
  char v23; // al
  char v24; // al
  int v25; // ebx
  const char *v26; // r9
  __int128 v28; // [rsp+20h] [rbp-28h] BYREF
  __int64 v29; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  v28 = 0;
  v6 = 0;
  v29 = 0;
  v7 = 0;
  v8 = *a2;
  if ( 0xCCCCCCCCCCCCCCCDuLL * ((a2[1] - *a2) >> 3) )
  {
    v9 = *((_QWORD *)&v28 + 1);
    while ( 1 )
    {
      v10 = (_DWORD *)(v8 + 40LL * v7);
      if ( v9 == v6 )
      {
        std::vector<Container::Manager::Image::CommandAdjustment>::_Emplace_reallocate<Container::Manager::Image::CommandAdjustment>(
          &v28,
          v9,
          v10);
        v9 = *((_QWORD *)&v28 + 1);
      }
      else
      {
        *(_DWORD *)v9 = *v10;
        v11 = v10 + 2;
        v12 = v10 + 6;
        v13 = (_OWORD *)(v9 + 24);
        if ( (_OWORD *)*v11 == v12 )
        {
          *(_QWORD *)(v9 + 8) = v13;
          *(_QWORD *)(v9 + 16) = v9 + 2 * (((v11[1] - (_QWORD)v11 - 16LL) >> 1) + 12);
          *v13 = *v12;
        }
        else
        {
          *(_QWORD *)(v9 + 8) = *v11;
          *(_QWORD *)(v9 + 16) = v11[1];
          *(_QWORD *)v13 = *(_QWORD *)v12;
        }
        *v11 = v12;
        v11[1] = v12;
        *(_WORD *)v12 = 0;
        v9 = *((_QWORD *)&v28 + 1) + 40LL;
        *((_QWORD *)&v28 + 1) += 40LL;
      }
      ++v7;
      v8 = *a2;
      if ( v7 >= 0xCCCCCCCCCCCCCCCDuLL * ((a2[1] - *a2) >> 3) )
        break;
      v6 = v29;
    }
  }
  v14 = Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(a1, &v28, a3);
  if ( v14 )
  {
    v15 = *a2;
    v16 = a2[1];
    a2[1] = *a2;
    v17 = (v16 - v15) / 40;
    while ( v17 )
    {
      --v17;
      v18 = *(void **)(v15 + 40 * v17 + 8);
      if ( v18 != (void *)(v15 + 8 * (5 * v17 + 3)) )
        operator delete(v18, (const struct std::nothrow_t *)&std::nothrow);
    }
    v19 = v28;
    v20 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v28 + 1) - v28) >> 3);
    v21 = 0xCCCCCCCCCCCCCCCDuLL * ((a2[2] - *a2) >> 3);
    if ( v20 <= v21 )
      goto LABEL_24;
    v22 = 7 * (v21 >> 2) + 8;
    if ( v22 < v20 )
      v22 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v28 + 1) - v28) >> 3);
    if ( v22 > 0x333333333333333LL )
      v22 = 0x333333333333333LL;
    if ( v20 <= v22
      && (v23 = utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::_SetCapacity(a2),
          v19 = v28,
          v23) )
    {
LABEL_24:
      v24 = 0;
    }
    else
    {
      v24 = 1;
    }
    if ( v24 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
        (const char *)0x8007000ELL,
        v28);
    v25 = 0;
    if ( 0xCCCCCCCCCCCCCCCDuLL * ((*((_QWORD *)&v28 + 1) - v19) >> 3) )
    {
      do
      {
        if ( !(unsigned __int8)utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::emplace_back<Container::Manager::Image::CommandAdjustment,0>(
                                 a2,
                                 v19 + 40LL * v25) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x7F,
            (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
            v26);
        ++v25;
        v19 = v28;
      }
      while ( v25 < 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)&v28 + 1) - v28) >> 3) );
    }
  }
  std::vector<Container::Manager::Image::CommandAdjustment>::~vector<Container::Manager::Image::CommandAdjustment>(&v28);
  return v14;
}

```

## disassembly

```asm
0x140010448  push    rbp
0x14001044a  push    rbx
0x14001044b  push    rsi
0x14001044c  push    rdi
0x14001044d  push    r14
0x14001044f  push    r15
0x140010451  mov     rbp, rsp
0x140010454  sub     rsp, 48h
0x140010458  mov     rsi, r8
0x14001045b  mov     rdi, rdx
0x14001045e  mov     r14, rcx
0x140010461  xorps   xmm0, xmm0
0x140010464  movdqu  [rbp+var_28], xmm0
0x140010469  xor     r9d, r9d
0x14001046c  mov     [rbp+var_18], r9
0x140010470  xor     ebx, ebx
0x140010472  mov     r8, [rdx]
0x140010475  mov     rax, [rdx+8]
0x140010479  sub     rax, r8
0x14001047c  sar     rax, 3
0x140010480  mov     r15, 0CCCCCCCCCCCCCCCDh
0x14001048a  imul    rax, r15
0x14001048e  test    rax, rax
0x140010491  jz      loc_14001054C
0x140010497  mov     rdx, qword ptr [rbp+var_28+8]
0x14001049b  movsxd  rax, ebx
0x14001049e  lea     rcx, [rax+rax*4]
0x1400104a2  lea     r8, [r8+rcx*8]
0x1400104a6  cmp     rdx, r9
0x1400104a9  jz      short loc_14001051A
0x1400104ab  mov     eax, [r8]
0x1400104ae  mov     [rdx], eax
0x1400104b0  lea     rcx, [r8+8]
0x1400104b4  lea     r8, [rcx+10h]
0x1400104b8  mov     rax, [rcx]
0x1400104bb  lea     r9, [rdx+18h]
0x1400104bf  cmp     rax, r8
0x1400104c2  jnz     short loc_1400104ED
0x1400104c4  mov     [rdx+8], r9
0x1400104c8  mov     rax, [rcx+8]
0x1400104cc  sub     rax, rcx
0x1400104cf  sub     rax, 10h
0x1400104d3  sar     rax, 1
0x1400104d6  add     rax, 0Ch
0x1400104da  lea     rax, [rdx+rax*2]
0x1400104de  mov     [rdx+10h], rax
0x1400104e2  movups  xmm0, xmmword ptr [r8]
0x1400104e6  movdqu  xmmword ptr [r9], xmm0
0x1400104eb  jmp     short loc_1400104FF
0x1400104ed  mov     [rdx+8], rax
0x1400104f1  mov     rax, [rcx+8]
0x1400104f5  mov     [rdx+10h], rax
0x1400104f9  mov     rax, [r8]
0x1400104fc  mov     [r9], rax
0x1400104ff  mov     [rcx], r8
0x140010502  mov     [rcx+8], r8
0x140010506  xor     eax, eax
0x140010508  mov     [r8], ax
0x14001050c  mov     rdx, qword ptr [rbp+var_28+8]
0x140010510  add     rdx, 28h ; '('
0x140010514  mov     qword ptr [rbp+var_28+8], rdx
0x140010518  jmp     short loc_140010527
0x14001051a  lea     rcx, [rbp+var_28]
0x14001051e  call    ??$_Emplace_reallocate@UCommandAdjustment@Image@Manager@Container@@@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAUCommandAdjustment@Image@Manager@Container@@QEAU2345@$$QEAU2345@@Z; std::vector<Container::Manager::Image::CommandAdjustment>::_Emplace_reallocate<Container::Manager::Image::CommandAdjustment>(Container::Manager::Image::CommandAdjustment * const,Container::Manager::Image::CommandAdjustment &&)
0x140010523  mov     rdx, qword ptr [rbp+var_28+8]
0x140010527  inc     ebx
0x140010529  mov     r8, [rdi]
0x14001052c  mov     rcx, [rdi+8]
0x140010530  sub     rcx, r8
0x140010533  sar     rcx, 3
0x140010537  imul    rcx, r15
0x14001053b  movsxd  rax, ebx
0x14001053e  cmp     rax, rcx
0x140010541  jnb     short loc_14001054C
0x140010543  mov     r9, [rbp+var_18]
0x140010547  jmp     loc_14001049B
0x14001054c  mov     r8, rsi
0x14001054f  lea     rdx, [rbp+var_28]
0x140010553  mov     rcx, r14
0x140010556  call    ??$FromJsonValue@UCommandAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(Marshal::JsonParser &,std::vector<Container::Manager::Image::CommandAdjustment> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)
0x14001055b  mov     r14b, al
0x14001055e  test    al, al
0x140010560  jz      loc_14001067A
0x140010566  mov     rsi, [rdi]
0x140010569  mov     rcx, [rdi+8]
0x14001056d  mov     [rdi+8], rsi
0x140010571  sub     rcx, rsi
0x140010574  mov     rax, 6666666666666667h
0x14001057e  imul    rcx
0x140010581  mov     rbx, rdx
0x140010584  sar     rbx, 4
0x140010588  mov     rax, rbx
0x14001058b  shr     rax, 3Fh
0x14001058f  add     rbx, rax
0x140010592  jz      short loc_1400105BE
0x140010594  dec     rbx
0x140010597  lea     rax, [rbx+rbx*4]
0x14001059b  mov     rcx, [rsi+rax*8+8]; void *
0x1400105a0  lea     rax, [rax+3]
0x1400105a4  lea     rax, [rsi+rax*8]
0x1400105a8  cmp     rcx, rax
0x1400105ab  jz      short loc_1400105B9
0x1400105ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400105b4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400105b9  test    rbx, rbx
0x1400105bc  jnz     short loc_140010594
0x1400105be  mov     rcx, qword ptr [rbp+var_28+8]
0x1400105c2  mov     r8, qword ptr [rbp+var_28]
0x1400105c6  sub     rcx, r8
0x1400105c9  sar     rcx, 3
0x1400105cd  imul    rcx, r15
0x1400105d1  mov     rax, [rdi+10h]
0x1400105d5  sub     rax, [rdi]
0x1400105d8  sar     rax, 3
0x1400105dc  imul    rax, r15
0x1400105e0  cmp     rcx, rax
0x1400105e3  jbe     short loc_140010622
0x1400105e5  shr     rax, 2
0x1400105e9  imul    rdx, rax, 7
0x1400105ed  add     rdx, 8
0x1400105f1  cmp     rdx, rcx
0x1400105f4  cmovb   rdx, rcx
0x1400105f8  mov     rax, 333333333333333h
0x140010602  cmp     rdx, rax
0x140010605  cmova   rdx, rax
0x140010609  cmp     rcx, rdx
0x14001060c  ja      short loc_14001061E
0x14001060e  mov     rcx, rdi
0x140010611  call    ?_SetCapacity@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::_SetCapacity(unsigned __int64)
0x140010616  mov     r8, qword ptr [rbp+var_28]
0x14001061a  test    al, al
0x14001061c  jnz     short loc_140010622
0x14001061e  mov     al, 1
0x140010620  jmp     short loc_140010624
0x140010622  xor     al, al
0x140010624  mov     rcx, [rbp+30h]; this
0x140010628  test    al, al
0x14001062a  jnz     short loc_140010694
0x14001062c  xor     ebx, ebx
0x14001062e  mov     rax, qword ptr [rbp+var_28+8]
0x140010632  sub     rax, r8
0x140010635  sar     rax, 3
0x140010639  imul    rax, r15
0x14001063d  test    rax, rax
0x140010640  jz      short loc_14001067A
0x140010642  mov     rsi, [rbp+30h]
0x140010646  movsxd  rax, ebx
0x140010649  lea     rcx, [rax+rax*4]
0x14001064d  lea     rdx, [r8+rcx*8]
0x140010651  mov     rcx, rdi
0x140010654  call    ??$emplace_back@UCommandAdjustment@Image@Manager@Container@@$0A@@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@utl@@@utl@@QEAA_N$$QEAUCommandAdjustment@Image@Manager@Container@@@Z; utl::vector<Container::Manager::Image::CommandAdjustment,utl::allocator<Container::Manager::Image::CommandAdjustment>>::emplace_back<Container::Manager::Image::CommandAdjustment,0>(Container::Manager::Image::CommandAdjustment &&)
0x140010659  test    al, al
0x14001065b  jz      short loc_1400106AC
0x14001065d  inc     ebx
0x14001065f  mov     rcx, qword ptr [rbp+var_28+8]
0x140010663  mov     r8, qword ptr [rbp+var_28]
0x140010667  sub     rcx, r8
0x14001066a  sar     rcx, 3
0x14001066e  imul    rcx, r15
0x140010672  movsxd  rax, ebx
0x140010675  cmp     rax, rcx
0x140010678  jb      short loc_140010642
0x14001067a  lea     rcx, [rbp+var_28]
0x14001067e  call    ??1?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ; std::vector<Container::Manager::Image::CommandAdjustment>::~vector<Container::Manager::Image::CommandAdjustment>(void)
0x140010683  mov     al, r14b
0x140010686  add     rsp, 48h
0x14001068a  pop     r15
0x14001068c  pop     r14
0x14001068e  pop     rdi
0x14001068f  pop     rsi
0x140010690  pop     rbx
0x140010691  pop     rbp
0x140010692  retn
0x140010694  mov     r9d, 8007000Eh; char *
0x14001069a  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\marshaljson"...
0x1400106a1  mov     edx, 78h ; 'x'; void *
0x1400106a6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400106ac  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\marshaljson"...
0x1400106b3  mov     edx, 7Fh; void *
0x1400106b8  mov     rcx, rsi; this
0x1400106bb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
