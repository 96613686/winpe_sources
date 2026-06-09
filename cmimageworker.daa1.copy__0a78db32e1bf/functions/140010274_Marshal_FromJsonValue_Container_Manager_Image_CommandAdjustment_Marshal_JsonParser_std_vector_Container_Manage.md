# Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(Marshal::JsonParser &,std::vector<Container::Manager::Image::CommandAdjustment,std::allocator<Container::Manager::Image::CommandAdjustment>> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)

- ea: `0x140010274`
- end: `0x140010440`
- name: `??$FromJsonValue@UCommandAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z`
- size: `460`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140010448`

## callees

- `0x140002344`
- `0x140010218`
- `0x140010274`
- `0x140012ec4`
- `0x140014754`
- `0x140018068`
- `0x14001a31c`
- `0x14001b8a8`
- `0x14001dadc`

## pseudocode

```c
char __fastcall Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rbx
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  __int64 v11; // rbp
  __int64 j; // rsi
  void *v13; // rcx
  __int64 v14; // rdx
  _WORD *v15; // rax
  bool v17; // bl
  char i; // al
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rax
  void *v22; // rcx

  if ( (unsigned int)Marshal::JsonParser::PeekValueType(a1) == 2 )
  {
    LOBYTE(v7) = 93;
    LOBYTE(v6) = 91;
    v17 = 1;
    for ( i = Marshal::JsonParser::BeginAggregate(a1, v6, v7, 7); i; i = Marshal::JsonParser::NextElement(a1, v20, 8) )
    {
      v19 = a2[1];
      if ( v19 == a2[2] )
      {
        std::vector<Container::Manager::Image::CommandAdjustment>::_Emplace_reallocate<>(a2);
      }
      else
      {
        *(_QWORD *)v19 = 0;
        *(_QWORD *)(v19 + 26) = 0;
        *(_DWORD *)(v19 + 34) = 0;
        *(_WORD *)(v19 + 38) = 0;
        *(_QWORD *)(v19 + 8) = v19 + 24;
        *(_QWORD *)(v19 + 16) = v19 + 24;
        *(_WORD *)(v19 + 24) = 0;
        a2[1] += 40LL;
      }
      if ( !(unsigned __int8)Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(a1, a2[1] - 40LL, a3) )
      {
        v21 = a2[1];
        v22 = *(void **)(v21 - 32);
        if ( v22 != (void *)(v21 - 16) )
          operator delete(v22, (const struct std::nothrow_t *)&std::nothrow);
        a2[1] -= 40LL;
        v17 = (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 4) == 0;
      }
      LOBYTE(v20) = 93;
    }
    return v17;
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
          v14 = 1;
          do
          {
            *(_QWORD *)v8 = 0;
            v15 = (_WORD *)(v8 + 24);
            *(_QWORD *)(v8 + 26) = 0;
            *(_DWORD *)(v8 + 34) = 0;
            *(_WORD *)(v8 + 38) = 0;
            *(_QWORD *)(v8 + 8) = v8 + 24;
            *(_QWORD *)(v8 + 16) = v8 + 24;
            v8 += 40;
            *v15 = 0;
            --v14;
          }
          while ( v14 );
          a2[1] = v8;
        }
        else
        {
          std::vector<Container::Manager::Image::CommandAdjustment>::_Resize_reallocate<std::_Value_init_tag>(a2);
        }
      }
    }
    else
    {
      v11 = v9 + 40;
      for ( j = v9 + 40; j != v8; j += 40 )
      {
        v13 = *(void **)(j + 8);
        if ( v13 != (void *)(j + 24) )
          operator delete(v13, (const struct std::nothrow_t *)&std::nothrow);
      }
      a2[1] = v11;
    }
    return Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(a1, *a2, a3);
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
0x140010274  push    rbx
0x140010276  push    rbp
0x140010277  push    rsi
0x140010278  push    rdi
0x140010279  push    r14
0x14001027b  push    r15
0x14001027d  sub     rsp, 28h
0x140010281  mov     r14, r8
0x140010284  mov     rdi, rdx
0x140010287  mov     r15, rcx
0x14001028a  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x14001028f  cmp     eax, 2
0x140010292  jz      loc_14001037E
0x140010298  mov     rax, [r14+8]
0x14001029c  test    byte ptr [rax+18h], 1
0x1400102a0  jz      loc_14001036A
0x1400102a6  mov     rbx, [rdi+8]
0x1400102aa  mov     r8, 0CCCCCCCCCCCCCCCDh
0x1400102b4  mov     rdx, [rdi]
0x1400102b7  mov     rcx, rbx
0x1400102ba  sub     rcx, rdx
0x1400102bd  sar     rcx, 3
0x1400102c1  imul    rcx, r8
0x1400102c5  cmp     rcx, 1
0x1400102c9  jbe     short loc_1400102FF
0x1400102cb  lea     rbp, [rdx+28h]
0x1400102cf  mov     rsi, rbp
0x1400102d2  cmp     rbp, rbx
0x1400102d5  jz      short loc_1400102F9
0x1400102d7  mov     rcx, [rsi+8]; void *
0x1400102db  lea     rax, [rsi+18h]
0x1400102df  cmp     rcx, rax
0x1400102e2  jz      short loc_1400102F0
0x1400102e4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400102eb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400102f0  add     rsi, 28h ; '('
0x1400102f4  cmp     rsi, rbx
0x1400102f7  jnz     short loc_1400102D7
0x1400102f9  mov     [rdi+8], rbp
0x1400102fd  jmp     short loc_140010357
0x1400102ff  jnb     short loc_140010357
0x140010301  mov     rax, [rdi+10h]
0x140010305  sub     rax, rdx
0x140010308  sar     rax, 3
0x14001030c  imul    rax, r8
0x140010310  cmp     rax, 1
0x140010314  jnb     short loc_140010320
0x140010316  mov     rcx, rdi
0x140010319  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Container::Manager::Image::CommandAdjustment>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x14001031e  jmp     short loc_140010357
0x140010320  mov     edx, 1
0x140010325  sub     rdx, rcx
0x140010328  jz      short loc_140010353
0x14001032a  xor     esi, esi
0x14001032c  mov     [rbx], rsi
0x14001032f  lea     rax, [rbx+18h]
0x140010333  mov     [rbx+1Ah], rsi
0x140010337  mov     [rbx+22h], esi
0x14001033a  mov     [rbx+26h], si
0x14001033e  mov     [rbx+8], rax
0x140010342  mov     [rbx+10h], rax
0x140010346  add     rbx, 28h ; '('
0x14001034a  mov     [rax], si
0x14001034d  sub     rdx, 1
0x140010351  jnz     short loc_14001032C
0x140010353  mov     [rdi+8], rbx
0x140010357  mov     rdx, [rdi]
0x14001035a  mov     r8, r14
0x14001035d  mov     rcx, r15
0x140010360  call    ??$FromJsonValue@UCommandAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAUCommandAdjustment@Image@Manager@Container@@AEBVUnmarshalContext@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(Marshal::JsonParser &,Container::Manager::Image::CommandAdjustment *,Marshal::UnmarshalContext const &)
0x140010365  jmp     loc_140010432
0x14001036a  mov     edx, 6
0x14001036f  mov     rcx, r14
0x140010372  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x140010377  xor     al, al
0x140010379  jmp     loc_140010432
0x14001037e  mov     r9d, 7
0x140010384  mov     r8b, 5Dh ; ']'
0x140010387  mov     dl, 5Bh ; '['
0x140010389  mov     rcx, r15
0x14001038c  mov     bl, 1
0x14001038e  call    ?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z; Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)
0x140010393  xor     esi, esi
0x140010395  jmp     loc_140010428
0x14001039a  mov     rdx, [rdi+8]
0x14001039e  cmp     rdx, [rdi+10h]
0x1400103a2  jz      short loc_1400103C8
0x1400103a4  mov     [rdx], rsi
0x1400103a7  lea     rax, [rdx+18h]
0x1400103ab  mov     [rdx+1Ah], rsi
0x1400103af  mov     [rdx+22h], esi
0x1400103b2  mov     [rdx+26h], si
0x1400103b6  mov     [rdx+8], rax
0x1400103ba  mov     [rdx+10h], rax
0x1400103be  mov     [rax], si
0x1400103c1  add     qword ptr [rdi+8], 28h ; '('
0x1400103c6  jmp     short loc_1400103D0
0x1400103c8  mov     rcx, rdi
0x1400103cb  call    ??$_Emplace_reallocate@$$V@?$vector@UCommandAdjustment@Image@Manager@Container@@V?$allocator@UCommandAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAUCommandAdjustment@Image@Manager@Container@@QEAU2345@@Z; std::vector<Container::Manager::Image::CommandAdjustment>::_Emplace_reallocate<>(Container::Manager::Image::CommandAdjustment * const)
0x1400103d0  mov     rdx, [rdi+8]
0x1400103d4  mov     r8, r14
0x1400103d7  sub     rdx, 28h ; '('
0x1400103db  mov     rcx, r15
0x1400103de  call    ??$FromJsonValue@UCommandAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAUCommandAdjustment@Image@Manager@Container@@AEBVUnmarshalContext@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::CommandAdjustment,>(Marshal::JsonParser &,Container::Manager::Image::CommandAdjustment *,Marshal::UnmarshalContext const &)
0x1400103e3  test    al, al
0x1400103e5  jnz     short loc_140010418
0x1400103e7  mov     rax, [rdi+8]
0x1400103eb  mov     rcx, [rax-20h]; void *
0x1400103ef  add     rax, 0FFFFFFFFFFFFFFF0h
0x1400103f3  cmp     rcx, rax
0x1400103f6  jz      short loc_140010404
0x1400103f8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400103ff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140010404  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFD8h
0x140010409  mov     rax, [r14+8]
0x14001040d  mov     bl, [rax+18h]
0x140010410  shr     bl, 2
0x140010413  not     bl
0x140010415  and     bl, 1
0x140010418  mov     r8d, 8
0x14001041e  mov     dl, 5Dh ; ']'
0x140010420  mov     rcx, r15
0x140010423  call    ?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z; Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)
0x140010428  test    al, al
0x14001042a  jnz     loc_14001039A
0x140010430  mov     al, bl
0x140010432  add     rsp, 28h
0x140010436  pop     r15
0x140010438  pop     r14
0x14001043a  pop     rdi
0x14001043b  pop     rsi
0x14001043c  pop     rbp
0x14001043d  pop     rbx
0x14001043e  retn
```
