# Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(Marshal::JsonParser &,std::vector<Container::Manager::Image::PackageAdjustment,std::allocator<Container::Manager::Image::PackageAdjustment>> *,Marshal::UnmarshalContext const &,Marshal::ModifierList<>)

- ea: `0x140010c74`
- end: `0x140010e3f`
- name: `??$FromJsonValue@UPackageAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@std@@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@@Z`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config`

## callers

- `0x140010e48`

## callees

- `0x140002344`
- `0x140010c18`
- `0x140010c74`
- `0x140013230`
- `0x140014a44`
- `0x140018068`
- `0x14001a31c`
- `0x14001b8a8`
- `0x14001dadc`

## pseudocode

```c
char __fastcall Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(
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
        std::vector<Container::Manager::Image::PackageAdjustment>::_Emplace_reallocate<>(a2);
      }
      else
      {
        *(_QWORD *)(v18 + 18) = 0;
        *(_DWORD *)(v18 + 26) = 0;
        *(_WORD *)(v18 + 30) = 0;
        *(_QWORD *)v18 = v18 + 16;
        *(_QWORD *)(v18 + 8) = v18 + 16;
        *(_WORD *)(v18 + 16) = 0;
        *(_QWORD *)(v18 + 32) = 0;
        a2[1] += 40LL;
      }
      if ( !(unsigned __int8)Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(a1, a2[1] - 40LL, a3) )
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
            *(_QWORD *)v8 = v8 + 16;
            *(_QWORD *)(v8 + 8) = v8 + 16;
            *(_QWORD *)(v8 + 32) = 0;
            v8 += 40;
            *v14 = 0;
            --v13;
          }
          while ( v13 );
          a2[1] = v8;
        }
        else
        {
          std::vector<Container::Manager::Image::PackageAdjustment>::_Resize_reallocate<std::_Value_init_tag>(a2);
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
    return Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(a1, *a2, a3);
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
0x140010c74  push    rbx
0x140010c76  push    rbp
0x140010c77  push    rsi
0x140010c78  push    rdi
0x140010c79  push    r14
0x140010c7b  push    r15
0x140010c7d  sub     rsp, 28h
0x140010c81  mov     rbp, r8
0x140010c84  mov     rdi, rdx
0x140010c87  mov     r15, rcx
0x140010c8a  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x140010c8f  cmp     eax, 2
0x140010c92  jz      loc_140010D7D
0x140010c98  mov     rax, [rbp+8]
0x140010c9c  test    byte ptr [rax+18h], 1
0x140010ca0  jz      loc_140010D69
0x140010ca6  mov     rbx, [rdi+8]
0x140010caa  mov     r8, 0CCCCCCCCCCCCCCCDh
0x140010cb4  mov     rdx, [rdi]
0x140010cb7  mov     rcx, rbx
0x140010cba  sub     rcx, rdx
0x140010cbd  sar     rcx, 3
0x140010cc1  imul    rcx, r8
0x140010cc5  cmp     rcx, 1
0x140010cc9  jbe     short loc_140010CFE
0x140010ccb  lea     r14, [rdx+28h]
0x140010ccf  mov     rsi, r14
0x140010cd2  cmp     r14, rbx
0x140010cd5  jz      short loc_140010CF8
0x140010cd7  lea     rax, [rsi+10h]
0x140010cdb  cmp     [rsi], rax
0x140010cde  jz      short loc_140010CEF
0x140010ce0  mov     rcx, [rsi]; void *
0x140010ce3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010cea  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140010cef  add     rsi, 28h ; '('
0x140010cf3  cmp     rsi, rbx
0x140010cf6  jnz     short loc_140010CD7
0x140010cf8  mov     [rdi+8], r14
0x140010cfc  jmp     short loc_140010D56
0x140010cfe  jnb     short loc_140010D56
0x140010d00  mov     rax, [rdi+10h]
0x140010d04  sub     rax, rdx
0x140010d07  sar     rax, 3
0x140010d0b  imul    rax, r8
0x140010d0f  cmp     rax, 1
0x140010d13  jnb     short loc_140010D1F
0x140010d15  mov     rcx, rdi
0x140010d18  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Container::Manager::Image::PackageAdjustment>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x140010d1d  jmp     short loc_140010D56
0x140010d1f  mov     edx, 1
0x140010d24  sub     rdx, rcx
0x140010d27  jz      short loc_140010D52
0x140010d29  xor     esi, esi
0x140010d2b  mov     [rbx+12h], rsi
0x140010d2f  lea     rax, [rbx+10h]
0x140010d33  mov     [rbx+1Ah], esi
0x140010d36  mov     [rbx+1Eh], si
0x140010d3a  mov     [rbx], rax
0x140010d3d  mov     [rbx+8], rax
0x140010d41  mov     [rbx+20h], rsi
0x140010d45  add     rbx, 28h ; '('
0x140010d49  mov     [rax], si
0x140010d4c  sub     rdx, 1
0x140010d50  jnz     short loc_140010D2B
0x140010d52  mov     [rdi+8], rbx
0x140010d56  mov     rdx, [rdi]
0x140010d59  mov     r8, rbp
0x140010d5c  mov     rcx, r15
0x140010d5f  call    ??$FromJsonValue@UPackageAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAUPackageAdjustment@Image@Manager@Container@@AEBVUnmarshalContext@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(Marshal::JsonParser &,Container::Manager::Image::PackageAdjustment *,Marshal::UnmarshalContext const &)
0x140010d64  jmp     loc_140010E31
0x140010d69  mov     edx, 6
0x140010d6e  mov     rcx, rbp
0x140010d71  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x140010d76  xor     al, al
0x140010d78  jmp     loc_140010E31
0x140010d7d  mov     r9d, 7
0x140010d83  mov     r8b, 5Dh ; ']'
0x140010d86  mov     dl, 5Bh ; '['
0x140010d88  mov     rcx, r15
0x140010d8b  mov     bl, 1
0x140010d8d  call    ?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z; Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)
0x140010d92  xor     esi, esi
0x140010d94  jmp     loc_140010E27
0x140010d99  mov     rdx, [rdi+8]
0x140010d9d  cmp     rdx, [rdi+10h]
0x140010da1  jz      short loc_140010DC7
0x140010da3  mov     [rdx+12h], rsi
0x140010da7  lea     rax, [rdx+10h]
0x140010dab  mov     [rdx+1Ah], esi
0x140010dae  mov     [rdx+1Eh], si
0x140010db2  mov     [rdx], rax
0x140010db5  mov     [rdx+8], rax
0x140010db9  mov     [rax], si
0x140010dbc  mov     [rdx+20h], rsi
0x140010dc0  add     qword ptr [rdi+8], 28h ; '('
0x140010dc5  jmp     short loc_140010DCF
0x140010dc7  mov     rcx, rdi
0x140010dca  call    ??$_Emplace_reallocate@$$V@?$vector@UPackageAdjustment@Image@Manager@Container@@V?$allocator@UPackageAdjustment@Image@Manager@Container@@@std@@@std@@AEAAPEAUPackageAdjustment@Image@Manager@Container@@QEAU2345@@Z; std::vector<Container::Manager::Image::PackageAdjustment>::_Emplace_reallocate<>(Container::Manager::Image::PackageAdjustment * const)
0x140010dcf  mov     rdx, [rdi+8]
0x140010dd3  mov     r8, rbp
0x140010dd6  sub     rdx, 28h ; '('
0x140010dda  mov     rcx, r15
0x140010ddd  call    ??$FromJsonValue@UPackageAdjustment@Image@Manager@Container@@$$V@Marshal@@YA_NAEAVJsonParser@0@PEAUPackageAdjustment@Image@Manager@Container@@AEBVUnmarshalContext@0@@Z; Marshal::FromJsonValue<Container::Manager::Image::PackageAdjustment,>(Marshal::JsonParser &,Container::Manager::Image::PackageAdjustment *,Marshal::UnmarshalContext const &)
0x140010de2  test    al, al
0x140010de4  jnz     short loc_140010E17
0x140010de6  mov     rax, [rdi+8]
0x140010dea  mov     rcx, [rax-28h]; void *
0x140010dee  add     rax, 0FFFFFFFFFFFFFFE8h
0x140010df2  cmp     rcx, rax
0x140010df5  jz      short loc_140010E03
0x140010df7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010dfe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140010e03  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFD8h
0x140010e08  mov     rax, [rbp+8]
0x140010e0c  mov     bl, [rax+18h]
0x140010e0f  shr     bl, 2
0x140010e12  not     bl
0x140010e14  and     bl, 1
0x140010e17  mov     r8d, 8
0x140010e1d  mov     dl, 5Dh ; ']'
0x140010e1f  mov     rcx, r15
0x140010e22  call    ?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z; Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)
0x140010e27  test    al, al
0x140010e29  jnz     loc_140010D99
0x140010e2f  mov     al, bl
0x140010e31  add     rsp, 28h
0x140010e35  pop     r15
0x140010e37  pop     r14
0x140010e39  pop     rdi
0x140010e3a  pop     rsi
0x140010e3b  pop     rbp
0x140010e3c  pop     rbx
0x140010e3d  retn
```
