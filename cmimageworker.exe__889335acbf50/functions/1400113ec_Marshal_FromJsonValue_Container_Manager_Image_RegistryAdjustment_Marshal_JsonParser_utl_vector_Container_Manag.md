# Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(Marshal::JsonParser &,utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)

- ea: `0x1400113ec`
- end: `0x1400115d7`
- name: `??$FromJsonValue@URegistryAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z`
- size: `491`
- prototype: `char __fastcall(Marshal::JsonParser *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140011660`

## callees

- `0x14000c7a8`
- `0x1400111d0`
- `0x1400113ec`
- `0x140013ee8`
- `0x1400140a0`
- `0x1400150dc`
- `0x1400153c4`
- `0x140015b08`
- `0x14001feac`
- `0x14001ffac`

## string_xrefs

- `0x1400115b0`: `onecore\internal\vm\inc\marshaljsonutl.h`
- `0x1400115c2`: `onecore\internal\vm\inc\marshaljsonutl.h`

## pseudocode

```c
char __fastcall Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(
        Marshal::JsonParser *a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v6; // r9
  __int64 v7; // rdx
  int v8; // edi
  __int64 v9; // rdx
  char v10; // si
  __int64 v11; // r9
  __int64 v12; // rcx
  __int64 v13; // r8
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // rdx
  char v17; // al
  char v18; // al
  int v19; // edi
  const char *v20; // r9
  __int128 v22; // [rsp+20h] [rbp-28h] BYREF
  __int64 v23; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  v22 = 0;
  v6 = 0;
  v23 = 0;
  v7 = *a2;
  if ( 0xEEEEEEEEEEEEEEEFuLL * ((a2[1] - v7) >> 3) )
  {
    v8 = 0;
    while ( 1 )
    {
      v9 = 120LL * v8 + v7;
      if ( *((_QWORD *)&v22 + 1) == v6 )
      {
        std::vector<Container::Manager::Image::RegistryAdjustment>::_Emplace_reallocate<Container::Manager::Image::RegistryAdjustment>(
          (__int64 *)&v22,
          *((__int64 *)&v22 + 1),
          v9);
      }
      else
      {
        Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(*((_QWORD *)&v22 + 1), v9);
        *((_QWORD *)&v22 + 1) += 120LL;
      }
      ++v8;
      v7 = *a2;
      if ( v8 >= 0xEEEEEEEEEEEEEEEFuLL * ((a2[1] - *a2) >> 3) )
        break;
      v6 = v23;
    }
  }
  v10 = Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(a1, (__int64 *)&v22, a3);
  if ( v10 )
  {
    v11 = *a2;
    v12 = a2[1];
    a2[1] = *a2;
    utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(
      v12 - v11,
      v11,
      (v12 - v11) / 120 + v12 - v11);
    v13 = v22;
    v14 = 0xEEEEEEEEEEEEEEEFuLL * ((__int64)(*((_QWORD *)&v22 + 1) - v22) >> 3);
    v15 = 0xEEEEEEEEEEEEEEEFuLL * ((a2[2] - *a2) >> 3);
    if ( v14 <= v15 )
      goto LABEL_17;
    v16 = 7 * (v15 >> 2) + 8;
    if ( v16 < v14 )
      v16 = 0xEEEEEEEEEEEEEEEFuLL * ((__int64)(*((_QWORD *)&v22 + 1) - v22) >> 3);
    if ( v16 > 0x111111111111111LL )
      v16 = 0x111111111111111LL;
    if ( v14 <= v16
      && (v17 = utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::_SetCapacity(a2),
          v13 = v22,
          v17) )
    {
LABEL_17:
      v18 = 0;
    }
    else
    {
      v18 = 1;
    }
    if ( v18 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
        (const char *)0x8007000ELL,
        v22);
    v19 = 0;
    if ( 0xEEEEEEEEEEEEEEEFuLL * ((*((_QWORD *)&v22 + 1) - v13) >> 3) )
    {
      do
      {
        if ( !utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::emplace_back<Container::Manager::Image::RegistryAdjustment,0>(
                a2,
                v13 + 120LL * v19) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x7F,
            (unsigned int)"onecore\\internal\\vm\\inc\\marshaljsonutl.h",
            v20);
        ++v19;
        v13 = v22;
      }
      while ( v19 < 0xEEEEEEEEEEEEEEEFuLL * ((__int64)(*((_QWORD *)&v22 + 1) - v22) >> 3) );
    }
  }
  std::vector<Container::Manager::Image::RegistryAdjustment>::~vector<Container::Manager::Image::RegistryAdjustment>(&v22);
  return v10;
}

```

## disassembly

```asm
0x1400113ec  push    rbp
0x1400113ee  push    rbx
0x1400113ef  push    rsi
0x1400113f0  push    rdi
0x1400113f1  push    r14
0x1400113f3  push    r15
0x1400113f5  mov     rbp, rsp
0x1400113f8  sub     rsp, 48h
0x1400113fc  mov     rsi, r8
0x1400113ff  mov     rbx, rdx
0x140011402  mov     r14, rcx
0x140011405  xorps   xmm0, xmm0
0x140011408  movdqu  [rbp+var_28], xmm0
0x14001140d  xor     r9d, r9d
0x140011410  mov     [rbp+var_18], r9
0x140011414  mov     rdx, [rdx]
0x140011417  mov     rax, [rbx+8]
0x14001141b  sub     rax, rdx
0x14001141e  sar     rax, 3
0x140011422  mov     r15, 0EEEEEEEEEEEEEEEFh
0x14001142c  imul    rax, r15
0x140011430  test    rax, rax
0x140011433  jz      short loc_140011487
0x140011435  xor     edi, edi
0x140011437  movsxd  rax, edi
0x14001143a  imul    rcx, rax, 78h ; 'x'
0x14001143e  add     rdx, rcx
0x140011441  mov     rcx, qword ptr [rbp+var_28+8]
0x140011445  cmp     rcx, r9
0x140011448  jz      short loc_140011456
0x14001144a  call    ??0RegistryAdjustment@Image@Manager@Container@@QEAA@$$QEAU0123@@Z; Container::Manager::Image::RegistryAdjustment::RegistryAdjustment(Container::Manager::Image::RegistryAdjustment &&)
0x14001144f  add     qword ptr [rbp+var_28+8], 78h ; 'x'
0x140011454  jmp     short loc_140011465
0x140011456  mov     r8, rdx
0x140011459  mov     rdx, rcx
0x14001145c  lea     rcx, [rbp+var_28]
0x140011460  call    ??$_Emplace_reallocate@URegistryAdjustment@Image@Manager@Container@@@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAURegistryAdjustment@Image@Manager@Container@@QEAU2345@$$QEAU2345@@Z; std::vector<Container::Manager::Image::RegistryAdjustment>::_Emplace_reallocate<Container::Manager::Image::RegistryAdjustment>(Container::Manager::Image::RegistryAdjustment * const,Container::Manager::Image::RegistryAdjustment &&)
0x140011465  inc     edi
0x140011467  mov     rdx, [rbx]
0x14001146a  mov     rcx, [rbx+8]
0x14001146e  sub     rcx, rdx
0x140011471  sar     rcx, 3
0x140011475  imul    rcx, r15
0x140011479  movsxd  rax, edi
0x14001147c  cmp     rax, rcx
0x14001147f  jnb     short loc_140011487
0x140011481  mov     r9, [rbp+var_18]
0x140011485  jmp     short loc_140011437
0x140011487  mov     r8, rsi
0x14001148a  lea     rdx, [rbp+var_28]
0x14001148e  mov     rcx, r14
0x140011491  call    ??$FromJsonValue@URegistryAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(Marshal::JsonParser &,std::vector<Container::Manager::Image::RegistryAdjustment> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)
0x140011496  mov     sil, al
0x140011499  test    al, al
0x14001149b  jz      loc_140011590
0x1400114a1  mov     r9, [rbx]
0x1400114a4  mov     rcx, [rbx+8]
0x1400114a8  mov     [rbx+8], r9
0x1400114ac  sub     rcx, r9
0x1400114af  mov     rax, 8888888888888889h
0x1400114b9  imul    rcx
0x1400114bc  add     rdx, rcx
0x1400114bf  sar     rdx, 6
0x1400114c3  mov     r8, rdx
0x1400114c6  shr     r8, 3Fh
0x1400114ca  add     r8, rdx
0x1400114cd  mov     rdx, r9
0x1400114d0  call    ??$_RangeDestroyApc@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@YAXAEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@PEAURegistryAdjustment@Image@Manager@Container@@_K@Z; utl::_RangeDestroyApc<utl::allocator<Container::Manager::Image::RegistryAdjustment>>(utl::allocator<Container::Manager::Image::RegistryAdjustment> &,Container::Manager::Image::RegistryAdjustment *,unsigned __int64)
0x1400114d5  mov     rcx, qword ptr [rbp+var_28+8]
0x1400114d9  mov     r8, qword ptr [rbp+var_28]
0x1400114dd  sub     rcx, r8
0x1400114e0  sar     rcx, 3
0x1400114e4  imul    rcx, r15
0x1400114e8  mov     rax, [rbx+10h]
0x1400114ec  sub     rax, [rbx]
0x1400114ef  sar     rax, 3
0x1400114f3  imul    rax, r15
0x1400114f7  cmp     rcx, rax
0x1400114fa  jbe     short loc_140011539
0x1400114fc  shr     rax, 2
0x140011500  imul    rdx, rax, 7
0x140011504  add     rdx, 8
0x140011508  cmp     rdx, rcx
0x14001150b  cmovb   rdx, rcx
0x14001150f  mov     rax, 111111111111111h
0x140011519  cmp     rdx, rax
0x14001151c  cmova   rdx, rax
0x140011520  cmp     rcx, rdx
0x140011523  ja      short loc_140011535
0x140011525  mov     rcx, rbx
0x140011528  call    ?_SetCapacity@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::_SetCapacity(unsigned __int64)
0x14001152d  mov     r8, qword ptr [rbp+var_28]
0x140011531  test    al, al
0x140011533  jnz     short loc_140011539
0x140011535  mov     al, 1
0x140011537  jmp     short loc_14001153B
0x140011539  xor     al, al
0x14001153b  mov     rcx, [rbp+30h]; this
0x14001153f  test    al, al
0x140011541  jnz     short loc_1400115AA
0x140011543  xor     edi, edi
0x140011545  mov     rax, qword ptr [rbp+var_28+8]
0x140011549  sub     rax, r8
0x14001154c  sar     rax, 3
0x140011550  imul    rax, r15
0x140011554  test    rax, rax
0x140011557  jz      short loc_140011590
0x140011559  mov     r14, [rbp+30h]
0x14001155d  movsxd  rax, edi
0x140011560  imul    rdx, rax, 78h ; 'x'
0x140011564  add     rdx, r8
0x140011567  mov     rcx, rbx
0x14001156a  call    ??$emplace_back@URegistryAdjustment@Image@Manager@Container@@$0A@@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@utl@@@utl@@QEAA_N$$QEAURegistryAdjustment@Image@Manager@Container@@@Z; utl::vector<Container::Manager::Image::RegistryAdjustment,utl::allocator<Container::Manager::Image::RegistryAdjustment>>::emplace_back<Container::Manager::Image::RegistryAdjustment,0>(Container::Manager::Image::RegistryAdjustment &&)
0x14001156f  test    al, al
0x140011571  jz      short loc_1400115C2
0x140011573  inc     edi
0x140011575  mov     rcx, qword ptr [rbp+var_28+8]
0x140011579  mov     r8, qword ptr [rbp+var_28]
0x14001157d  sub     rcx, r8
0x140011580  sar     rcx, 3
0x140011584  imul    rcx, r15
0x140011588  movsxd  rax, edi
0x14001158b  cmp     rax, rcx
0x14001158e  jb      short loc_140011559
0x140011590  lea     rcx, [rbp+var_28]
0x140011594  call    ??1?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@QEAA@XZ; std::vector<Container::Manager::Image::RegistryAdjustment>::~vector<Container::Manager::Image::RegistryAdjustment>(void)
0x140011599  mov     al, sil
0x14001159c  add     rsp, 48h
0x1400115a0  pop     r15
0x1400115a2  pop     r14
0x1400115a4  pop     rdi
0x1400115a5  pop     rsi
0x1400115a6  pop     rbx
0x1400115a7  pop     rbp
0x1400115a8  retn
0x1400115aa  mov     r9d, 8007000Eh; char *
0x1400115b0  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\marshaljson"...
0x1400115b7  mov     edx, 78h ; 'x'; void *
0x1400115bc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400115c2  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\marshaljson"...
0x1400115c9  mov     edx, 7Fh; void *
0x1400115ce  mov     rcx, r14; this
0x1400115d1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
