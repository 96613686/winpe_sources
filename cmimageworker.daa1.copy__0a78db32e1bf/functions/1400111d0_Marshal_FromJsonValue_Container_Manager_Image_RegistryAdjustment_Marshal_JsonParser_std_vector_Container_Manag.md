# Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(Marshal::JsonParser &,std::vector<Container::Manager::Image::RegistryAdjustment,std::allocator<Container::Manager::Image::RegistryAdjustment>> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)

- ea: `0x1400111d0`
- end: `0x1400113e5`
- name: `??$FromJsonValue@URegistryAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x1400113ec`

## callees

- `0x140002344`
- `0x140002b2c`
- `0x140011174`
- `0x1400111d0`
- `0x140012e48`
- `0x1400133e4`
- `0x140014bbc`
- `0x140018068`
- `0x14001a31c`
- `0x14001b8a8`
- `0x14001dadc`

## pseudocode

```c
char __fastcall Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(
        __int64 a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v6; // rdx
  __int64 v7; // r8
  _QWORD *v8; // rdi
  __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rbx
  bool v14; // di
  char i; // al
  _QWORD *v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // rbx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx

  if ( (unsigned int)Marshal::JsonParser::PeekValueType(a1) == 2 )
  {
    LOBYTE(v7) = 93;
    LOBYTE(v6) = 91;
    v14 = 1;
    for ( i = Marshal::JsonParser::BeginAggregate(a1, v6, v7, 7); i; i = Marshal::JsonParser::NextElement(a1, v17, 8) )
    {
      v16 = (_QWORD *)a2[1];
      if ( v16 == (_QWORD *)a2[2] )
      {
        std::vector<Container::Manager::Image::RegistryAdjustment>::_Emplace_reallocate<>(a2, a2[1]);
      }
      else
      {
        memset_0((void *)a2[1], 0, 0x78u);
        v16[1] = v16 + 3;
        v16[2] = v16 + 3;
        v16[5] = v16 + 7;
        v16[6] = v16 + 7;
        v16[9] = v16 + 11;
        v16[10] = v16 + 11;
        a2[1] += 120;
      }
      if ( !(unsigned __int8)Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(a1, a2[1] - 120, a3) )
      {
        v18 = a2[1];
        v19 = *(void **)(v18 - 48);
        if ( v19 != (void *)(v18 - 32) )
          operator delete(v19, (const struct std::nothrow_t *)&std::nothrow);
        v20 = *(void **)(v18 - 80);
        if ( v20 != (void *)(v18 - 64) )
          operator delete(v20, (const struct std::nothrow_t *)&std::nothrow);
        v21 = *(void **)(v18 - 112);
        if ( v21 != (void *)(v18 - 96) )
          operator delete(v21, (const struct std::nothrow_t *)&std::nothrow);
        a2[1] -= 120;
        v14 = (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 4) == 0;
      }
      LOBYTE(v17) = 93;
    }
    return v14;
  }
  else if ( (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 1) != 0 )
  {
    v8 = (_QWORD *)a2[1];
    v9 = *a2;
    v10 = 0xEEEEEEEEEEEEEEEFuLL * (((__int64)v8 - *a2) >> 3);
    if ( v10 <= 1 )
    {
      if ( !v10 )
      {
        if ( 0xEEEEEEEEEEEEEEEFuLL * ((a2[2] - v9) >> 3) )
        {
          v12 = 1;
          do
          {
            memset_0(v8, 0, 0x78u);
            v8[1] = v8 + 3;
            v8[2] = v8 + 3;
            v8[5] = v8 + 7;
            v8[6] = v8 + 7;
            v8[9] = v8 + 11;
            v8[10] = v8 + 11;
            v8 += 15;
            --v12;
          }
          while ( v12 );
          std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(v8, v8);
          a2[1] = (__int64)v8;
        }
        else
        {
          std::vector<Container::Manager::Image::RegistryAdjustment>::_Resize_reallocate<std::_Value_init_tag>(a2);
        }
      }
    }
    else
    {
      v11 = v9 + 120;
      std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(v9 + 120, a2[1]);
      a2[1] = v11;
    }
    return Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(a1, *a2, a3);
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
0x1400111d0  push    rbx
0x1400111d2  push    rbp
0x1400111d3  push    rsi
0x1400111d4  push    rdi
0x1400111d5  push    r14
0x1400111d7  sub     rsp, 20h
0x1400111db  mov     rbp, r8
0x1400111de  mov     rsi, rdx
0x1400111e1  mov     r14, rcx
0x1400111e4  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x1400111e9  cmp     eax, 2
0x1400111ec  jz      loc_1400112D7
0x1400111f2  mov     rax, [rbp+8]
0x1400111f6  test    byte ptr [rax+18h], 1
0x1400111fa  jz      loc_1400112C3
0x140011200  mov     rdi, [rsi+8]
0x140011204  mov     r8, 0EEEEEEEEEEEEEEEFh
0x14001120e  mov     rdx, [rsi]
0x140011211  mov     rcx, rdi
0x140011214  sub     rcx, rdx
0x140011217  sar     rcx, 3
0x14001121b  imul    rcx, r8
0x14001121f  cmp     rcx, 1
0x140011223  jbe     short loc_14001123A
0x140011225  lea     rbx, [rdx+78h]
0x140011229  mov     rdx, rdi
0x14001122c  mov     rcx, rbx
0x14001122f  call    ??$_Destroy_range@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@YAXPEAURegistryAdjustment@Image@Manager@Container@@QEAU1234@AEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@@Z; std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(Container::Manager::Image::RegistryAdjustment *,Container::Manager::Image::RegistryAdjustment * const,std::allocator<Container::Manager::Image::RegistryAdjustment> &)
0x140011234  mov     [rsi+8], rbx
0x140011238  jmp     short loc_1400112B0
0x14001123a  jnb     short loc_1400112B0
0x14001123c  mov     rax, [rsi+10h]
0x140011240  sub     rax, rdx
0x140011243  sar     rax, 3
0x140011247  imul    rax, r8
0x14001124b  cmp     rax, 1
0x14001124f  jnb     short loc_14001125B
0x140011251  mov     rcx, rsi
0x140011254  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Container::Manager::Image::RegistryAdjustment>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140011259  jmp     short loc_1400112B0
0x14001125b  mov     ebx, 1
0x140011260  sub     rbx, rcx
0x140011263  jz      short loc_1400112A1
0x140011265  xor     edx, edx; Val
0x140011267  mov     rcx, rdi; void *
0x14001126a  lea     r8d, [rdx+78h]; Size
0x14001126e  call    memset_0
0x140011273  lea     rax, [rdi+18h]
0x140011277  mov     [rdi+8], rax
0x14001127b  mov     [rdi+10h], rax
0x14001127f  lea     rax, [rdi+38h]
0x140011283  mov     [rdi+28h], rax
0x140011287  mov     [rdi+30h], rax
0x14001128b  lea     rax, [rdi+58h]
0x14001128f  mov     [rdi+48h], rax
0x140011293  mov     [rdi+50h], rax
0x140011297  add     rdi, 78h ; 'x'
0x14001129b  sub     rbx, 1
0x14001129f  jnz     short loc_140011265
0x1400112a1  mov     rdx, rdi
0x1400112a4  mov     rcx, rdi
0x1400112a7  call    ??$_Destroy_range@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@YAXPEAURegistryAdjustment@Image@Manager@Container@@QEAU1234@AEAV?$allocator@URegistryAdjustment@Image@Manager@Container@@@0@@Z; std::_Destroy_range<std::allocator<Container::Manager::Image::RegistryAdjustment>>(Container::Manager::Image::RegistryAdjustment *,Container::Manager::Image::RegistryAdjustment * const,std::allocator<Container::Manager::Image::RegistryAdjustment> &)
0x1400112ac  mov     [rsi+8], rdi
0x1400112b0  mov     rdx, [rsi]
0x1400112b3  mov     r8, rbp
0x1400112b6  mov     rcx, r14
0x1400112b9  call    ??$FromJsonValue@URegistryAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAURegistryAdjustment@Image@Manager@Container@@AEBVUnmarshalContext@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(Marshal::JsonParser &,Container::Manager::Image::RegistryAdjustment *,Marshal::UnmarshalContext const &)
0x1400112be  jmp     loc_1400113D9
0x1400112c3  mov     edx, 6
0x1400112c8  mov     rcx, rbp
0x1400112cb  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x1400112d0  xor     al, al
0x1400112d2  jmp     loc_1400113D9
0x1400112d7  mov     r9d, 7
0x1400112dd  mov     r8b, 5Dh ; ']'
0x1400112e0  mov     dl, 5Bh ; '['
0x1400112e2  mov     rcx, r14
0x1400112e5  mov     dil, 1
0x1400112e8  call    ?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z; Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)
0x1400112ed  jmp     loc_1400113CE
0x1400112f2  mov     rbx, [rsi+8]
0x1400112f6  cmp     rbx, [rsi+10h]
0x1400112fa  jz      short loc_140011335
0x1400112fc  xor     edx, edx; Val
0x1400112fe  mov     rcx, rbx; void *
0x140011301  lea     r8d, [rdx+78h]; Size
0x140011305  call    memset_0
0x14001130a  lea     rax, [rbx+18h]
0x14001130e  mov     [rbx+8], rax
0x140011312  mov     [rbx+10h], rax
0x140011316  lea     rax, [rbx+38h]
0x14001131a  mov     [rbx+28h], rax
0x14001131e  mov     [rbx+30h], rax
0x140011322  lea     rax, [rbx+58h]
0x140011326  mov     [rbx+48h], rax
0x14001132a  mov     [rbx+50h], rax
0x14001132e  add     qword ptr [rsi+8], 78h ; 'x'
0x140011333  jmp     short loc_140011340
0x140011335  mov     rdx, rbx
0x140011338  mov     rcx, rsi
0x14001133b  call    ??$_Emplace_reallocate@$$V@?$vector@URegistryAdjustment@Image@Manager@Container@@V?$allocator@URegistryAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAURegistryAdjustment@Image@Manager@Container@@QEAU2345@@Z; std::vector<Container::Manager::Image::RegistryAdjustment>::_Emplace_reallocate<>(Container::Manager::Image::RegistryAdjustment * const)
0x140011340  mov     rdx, [rsi+8]
0x140011344  mov     r8, rbp
0x140011347  sub     rdx, 78h ; 'x'
0x14001134b  mov     rcx, r14
0x14001134e  call    ??$FromJsonValue@URegistryAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAURegistryAdjustment@Image@Manager@Container@@AEBVUnmarshalContext@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::RegistryAdjustment,>(Marshal::JsonParser &,Container::Manager::Image::RegistryAdjustment *,Marshal::UnmarshalContext const &)
0x140011353  test    al, al
0x140011355  jnz     short loc_1400113BE
0x140011357  mov     rbx, [rsi+8]
0x14001135b  mov     rcx, [rbx-30h]; void *
0x14001135f  lea     rax, [rbx-20h]
0x140011363  cmp     rcx, rax
0x140011366  jz      short loc_140011374
0x140011368  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001136f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140011374  mov     rcx, [rbx-50h]; void *
0x140011378  lea     rax, [rbx-40h]
0x14001137c  cmp     rcx, rax
0x14001137f  jz      short loc_14001138D
0x140011381  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140011388  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001138d  mov     rcx, [rbx-70h]; void *
0x140011391  lea     rax, [rbx-60h]
0x140011395  cmp     rcx, rax
0x140011398  jz      short loc_1400113A6
0x14001139a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400113a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400113a6  add     qword ptr [rsi+8], 0FFFFFFFFFFFFFF88h
0x1400113ab  mov     rax, [rbp+8]
0x1400113af  mov     dil, [rax+18h]
0x1400113b3  shr     dil, 2
0x1400113b7  not     dil
0x1400113ba  and     dil, 1
0x1400113be  mov     r8d, 8
0x1400113c4  mov     dl, 5Dh ; ']'
0x1400113c6  mov     rcx, r14
0x1400113c9  call    ?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z; Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)
0x1400113ce  test    al, al
0x1400113d0  jnz     loc_1400112F2
0x1400113d6  mov     al, dil
0x1400113d9  add     rsp, 20h
0x1400113dd  pop     r14
0x1400113df  pop     rdi
0x1400113e0  pop     rsi
0x1400113e1  pop     rbp
0x1400113e2  pop     rbx
0x1400113e3  retn
```
