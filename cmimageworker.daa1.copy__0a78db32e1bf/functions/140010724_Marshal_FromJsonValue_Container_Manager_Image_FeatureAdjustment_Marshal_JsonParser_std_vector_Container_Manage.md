# Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(Marshal::JsonParser &,std::vector<Container::Manager::Image::FeatureAdjustment,std::allocator<Container::Manager::Image::FeatureAdjustment>> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)

- ea: `0x140010724`
- end: `0x1400108ef`
- name: `??$FromJsonValue@UFeatureAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@std@@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x1400108f8`

## callees

- `0x140002344`
- `0x1400106c8`
- `0x140010724`
- `0x14001307c`
- `0x1400148cc`
- `0x140018068`
- `0x14001a31c`
- `0x14001b8a8`
- `0x14001dadc`

## pseudocode

```c
char __fastcall Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rbx
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  __int64 v11; // r14
  void **j; // rsi
  __int64 v13; // rdx
  _WORD *v14; // rax
  bool v16; // bl
  char i; // al
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rax
  void *v21; // rcx

  if ( (unsigned int)Marshal::JsonParser::PeekValueType(a1) == 2 )
  {
    LOBYTE(v7) = 93;
    LOBYTE(v6) = 91;
    v16 = 1;
    for ( i = Marshal::JsonParser::BeginAggregate(a1, v6, v7, 7); i; i = Marshal::JsonParser::NextElement(a1, v19, 8) )
    {
      v18 = a2[1];
      if ( v18 == a2[2] )
      {
        std::vector<Container::Manager::Image::FeatureAdjustment>::_Emplace_reallocate<>(a2);
      }
      else
      {
        *(_QWORD *)(v18 + 18) = 0;
        *(_DWORD *)(v18 + 26) = 0;
        *(_WORD *)(v18 + 30) = 0;
        *(_QWORD *)(v18 + 32) = 0;
        *(_QWORD *)v18 = v18 + 16;
        *(_QWORD *)(v18 + 8) = v18 + 16;
        *(_WORD *)(v18 + 16) = 0;
        a2[1] += 40LL;
      }
      if ( !(unsigned __int8)Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(a1, a2[1] - 40LL, a3) )
      {
        v20 = a2[1];
        v21 = *(void **)(v20 - 40);
        if ( v21 != (void *)(v20 - 24) )
          operator delete(v21, (const struct std::nothrow_t *)&std::nothrow);
        a2[1] -= 40LL;
        v16 = (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 4) == 0;
      }
      LOBYTE(v19) = 93;
    }
    return v16;
  }
  else if ( (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 1) != 0 )
  {
    v8 = a2[1];
    v9 = *a2;
    v10 = 0xCCCCCCCCCCCCCCCDuLL * ((v8 - *a2) >> 3);
    if ( v10 <= 1 )
    {
      if ( !v10 )
      {
        if ( 0xCCCCCCCCCCCCCCCDuLL * ((a2[2] - v9) >> 3) )
        {
          v13 = 1;
          do
          {
            *(_QWORD *)(v8 + 18) = 0;
            v14 = (_WORD *)(v8 + 16);
            *(_DWORD *)(v8 + 26) = 0;
            *(_WORD *)(v8 + 30) = 0;
            *(_QWORD *)(v8 + 32) = 0;
            *(_QWORD *)v8 = v8 + 16;
            *(_QWORD *)(v8 + 8) = v8 + 16;
            v8 += 40;
            *v14 = 0;
            --v13;
          }
          while ( v13 );
          a2[1] = v8;
        }
        else
        {
          std::vector<Container::Manager::Image::FeatureAdjustment>::_Resize_reallocate<std::_Value_init_tag>(a2);
        }
      }
    }
    else
    {
      v11 = v9 + 40;
      for ( j = (void **)(v9 + 40); j != (void **)v8; j += 5 )
      {
        if ( *j != j + 2 )
          operator delete(*j, (const struct std::nothrow_t *)&std::nothrow);
      }
      a2[1] = v11;
    }
    return Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(a1, *a2, a3);
  }
  else
  {
    Marshal::UnmarshalContext::ReportError(a3, 6);
    return 0;
  }
}

```

## disassembly

```asm
0x140010724  push    rbx
0x140010726  push    rbp
0x140010727  push    rsi
0x140010728  push    rdi
0x140010729  push    r14
0x14001072b  push    r15
0x14001072d  sub     rsp, 28h
0x140010731  mov     rbp, r8
0x140010734  mov     rdi, rdx
0x140010737  mov     r15, rcx
0x14001073a  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x14001073f  cmp     eax, 2
0x140010742  jz      loc_14001082D
0x140010748  mov     rax, [rbp+8]
0x14001074c  test    byte ptr [rax+18h], 1
0x140010750  jz      loc_140010819
0x140010756  mov     rbx, [rdi+8]
0x14001075a  mov     r8, 0CCCCCCCCCCCCCCCDh
0x140010764  mov     rdx, [rdi]
0x140010767  mov     rcx, rbx
0x14001076a  sub     rcx, rdx
0x14001076d  sar     rcx, 3
0x140010771  imul    rcx, r8
0x140010775  cmp     rcx, 1
0x140010779  jbe     short loc_1400107AE
0x14001077b  lea     r14, [rdx+28h]
0x14001077f  mov     rsi, r14
0x140010782  cmp     r14, rbx
0x140010785  jz      short loc_1400107A8
0x140010787  lea     rax, [rsi+10h]
0x14001078b  cmp     [rsi], rax
0x14001078e  jz      short loc_14001079F
0x140010790  mov     rcx, [rsi]; void *
0x140010793  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001079a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001079f  add     rsi, 28h ; '('
0x1400107a3  cmp     rsi, rbx
0x1400107a6  jnz     short loc_140010787
0x1400107a8  mov     [rdi+8], r14
0x1400107ac  jmp     short loc_140010806
0x1400107ae  jnb     short loc_140010806
0x1400107b0  mov     rax, [rdi+10h]
0x1400107b4  sub     rax, rdx
0x1400107b7  sar     rax, 3
0x1400107bb  imul    rax, r8
0x1400107bf  cmp     rax, 1
0x1400107c3  jnb     short loc_1400107CF
0x1400107c5  mov     rcx, rdi
0x1400107c8  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Container::Manager::Image::FeatureAdjustment>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1400107cd  jmp     short loc_140010806
0x1400107cf  mov     edx, 1
0x1400107d4  sub     rdx, rcx
0x1400107d7  jz      short loc_140010802
0x1400107d9  xor     esi, esi
0x1400107db  mov     [rbx+12h], rsi
0x1400107df  lea     rax, [rbx+10h]
0x1400107e3  mov     [rbx+1Ah], esi
0x1400107e6  mov     [rbx+1Eh], si
0x1400107ea  mov     [rbx+20h], rsi
0x1400107ee  mov     [rbx], rax
0x1400107f1  mov     [rbx+8], rax
0x1400107f5  add     rbx, 28h ; '('
0x1400107f9  mov     [rax], si
0x1400107fc  sub     rdx, 1
0x140010800  jnz     short loc_1400107DB
0x140010802  mov     [rdi+8], rbx
0x140010806  mov     rdx, [rdi]
0x140010809  mov     r8, rbp
0x14001080c  mov     rcx, r15
0x14001080f  call    ??$FromJsonValue@UFeatureAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAUFeatureAdjustment@Image@Manager@Container@@AEBVUnmarshalContext@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(Marshal::JsonParser &,Container::Manager::Image::FeatureAdjustment *,Marshal::UnmarshalContext const &)
0x140010814  jmp     loc_1400108E1
0x140010819  mov     edx, 6
0x14001081e  mov     rcx, rbp
0x140010821  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x140010826  xor     al, al
0x140010828  jmp     loc_1400108E1
0x14001082d  mov     r9d, 7
0x140010833  mov     r8b, 5Dh ; ']'
0x140010836  mov     dl, 5Bh ; '['
0x140010838  mov     rcx, r15
0x14001083b  mov     bl, 1
0x14001083d  call    ?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z; Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)
0x140010842  xor     esi, esi
0x140010844  jmp     loc_1400108D7
0x140010849  mov     rdx, [rdi+8]
0x14001084d  cmp     rdx, [rdi+10h]
0x140010851  jz      short loc_140010877
0x140010853  mov     [rdx+12h], rsi
0x140010857  lea     rax, [rdx+10h]
0x14001085b  mov     [rdx+1Ah], esi
0x14001085e  mov     [rdx+1Eh], si
0x140010862  mov     [rdx+20h], rsi
0x140010866  mov     [rdx], rax
0x140010869  mov     [rdx+8], rax
0x14001086d  mov     [rax], si
0x140010870  add     qword ptr [rdi+8], 28h ; '('
0x140010875  jmp     short loc_14001087F
0x140010877  mov     rcx, rdi
0x14001087a  call    ??$_Emplace_reallocate@$$V@?$vector@UFeatureAdjustment@Image@Manager@Container@@V?$allocator@UFeatureAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAUFeatureAdjustment@Image@Manager@Container@@QEAU2345@@Z; std::vector<Container::Manager::Image::FeatureAdjustment>::_Emplace_reallocate<>(Container::Manager::Image::FeatureAdjustment * const)
0x14001087f  mov     rdx, [rdi+8]
0x140010883  mov     r8, rbp
0x140010886  sub     rdx, 28h ; '('
0x14001088a  mov     rcx, r15
0x14001088d  call    ??$FromJsonValue@UFeatureAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAUFeatureAdjustment@Image@Manager@Container@@AEBVUnmarshalContext@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::FeatureAdjustment,>(Marshal::JsonParser &,Container::Manager::Image::FeatureAdjustment *,Marshal::UnmarshalContext const &)
0x140010892  test    al, al
0x140010894  jnz     short loc_1400108C7
0x140010896  mov     rax, [rdi+8]
0x14001089a  mov     rcx, [rax-28h]; void *
0x14001089e  add     rax, 0FFFFFFFFFFFFFFE8h
0x1400108a2  cmp     rcx, rax
0x1400108a5  jz      short loc_1400108B3
0x1400108a7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400108ae  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400108b3  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFD8h
0x1400108b8  mov     rax, [rbp+8]
0x1400108bc  mov     bl, [rax+18h]
0x1400108bf  shr     bl, 2
0x1400108c2  not     bl
0x1400108c4  and     bl, 1
0x1400108c7  mov     r8d, 8
0x1400108cd  mov     dl, 5Dh ; ']'
0x1400108cf  mov     rcx, r15
0x1400108d2  call    ?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z; Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)
0x1400108d7  test    al, al
0x1400108d9  jnz     loc_140010849
0x1400108df  mov     al, bl
0x1400108e1  add     rsp, 28h
0x1400108e5  pop     r15
0x1400108e7  pop     r14
0x1400108e9  pop     rdi
0x1400108ea  pop     rsi
0x1400108eb  pop     rbp
0x1400108ec  pop     rbx
0x1400108ed  retn
```
