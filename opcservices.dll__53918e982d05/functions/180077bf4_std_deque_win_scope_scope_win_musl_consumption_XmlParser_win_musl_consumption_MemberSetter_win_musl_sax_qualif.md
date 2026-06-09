# std::deque<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>,std::allocator<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>>>::_Growmap(unsigned __int64)

- ea: `0x180077bf4`
- end: `0x180077db4`
- name: `?_Growmap@?$deque@V?$scope@PEAV?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAV?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@IEAAX_K@Z`
- size: `448`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18000f270`
- `0x18000f714`
- `0x180011b80`

## callees

- `0x18003d43c`
- `0x18004d108`
- `0x180077bf4`
- `0x1800cd178`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800d6354`

## import_xrefs

- `msvcrt!memmove_s` at `0x180077cb0`
- `msvcrt!memmove_s` at `0x180077cb0`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180077d53`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180077d53`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::deque<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>>::_Growmap(
        _QWORD *a1,
        const char *a2)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // r14
  char *v8; // rax
  void *v9; // r12
  __int64 v10; // rsi
  char *v11; // rbp
  __int64 v12; // rdx
  __int64 v13; // r15
  char *v14; // r8
  void *v15; // rcx
  void *v16; // rax
  size_t v17; // r8
  void *v18; // rcx
  void *v19; // rcx
  __int64 v20; // rax
  _QWORD pExceptionObject[3]; // [rsp+28h] [rbp-40h] BYREF
  const char *v22; // [rsp+78h] [rbp+10h] BYREF

  v22 = a2;
  v3 = a1[2];
  v4 = 1;
  if ( v3 == 0xFFFFFFFFFFFFFFFLL )
    std::deque<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>>::_Xlen(0xFFFFFFFFFFFFFFFLL);
  v5 = v3 >> 1;
  if ( v3 >> 1 < 8 )
    v5 = 8;
  if ( v3 <= 0xFFFFFFFFFFFFFFFLL - v5 )
    v4 = v5;
  v6 = v4 + v3;
  if ( v6 && 0xFFFFFFFFFFFFFFFFuLL / v6 < 8 )
  {
    v22 = 0;
    exception::exception((exception *)pExceptionObject, &v22);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  v7 = a1[3];
  v8 = (char *)operator new(8 * v6);
  v9 = v8;
  v10 = 8 * v7;
  v11 = &v8[8 * v7];
  v12 = (__int64)(8LL * a1[2] - 8 * v7) >> 3;
  v13 = 8 * v12;
  if ( v12 )
    memmove_s(&v8[8 * v7], 8 * v12, (const void *const)(a1[1] + 8 * v7), 8 * v12);
  v14 = &v11[v13];
  v15 = (void *)a1[1];
  if ( v7 > v4 )
  {
    std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(
      v15,
      (__int64)v15 + 8 * v4,
      v14);
    v20 = std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(
            (void *)(8 * v4 + a1[1]),
            a1[1] + v10,
            v9);
    if ( v4 )
    {
      v17 = 8 * v4;
      v18 = (void *)v20;
      goto LABEL_15;
    }
  }
  else
  {
    v16 = (void *)std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(
                    v15,
                    (__int64)v15 + v10,
                    v14);
    if ( v4 != v7 )
      memset_0(v16, 0, 8 * (v4 - v7));
    if ( v7 )
    {
      v17 = 8 * v7;
      v18 = v9;
LABEL_15:
      memset_0(v18, 0, v17);
    }
  }
  v19 = (void *)a1[1];
  if ( v19 )
    operator delete(v19);
  a1[1] = v9;
  a1[2] += v4;
}

```

## disassembly

```asm
0x180077bf4  mov     rax, rsp
0x180077bf7  mov     [rax+10h], rdx
0x180077bfb  push    rsi
0x180077bfc  push    rdi
0x180077bfd  push    r12
0x180077bff  push    r14
0x180077c01  push    r15
0x180077c03  sub     rsp, 40h
0x180077c07  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180077c0f  mov     [rax+8], rbx
0x180077c13  mov     [rax+18h], rbp
0x180077c17  mov     rbx, rcx
0x180077c1a  mov     rcx, [rcx+10h]
0x180077c1e  mov     rdx, 0FFFFFFFFFFFFFFFh
0x180077c28  mov     rax, rdx
0x180077c2b  sub     rax, rcx
0x180077c2e  mov     edi, 1
0x180077c33  cmp     rax, rdi
0x180077c36  jnb     short loc_180077C3E
0x180077c38  call    ?_Xlen@?$deque@V?$scope@PEAV?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAV?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@KAXXZ; std::deque<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>>::_Xlen(void)
0x180077c3e  mov     rax, rcx
0x180077c41  shr     rax, 1
0x180077c44  mov     r8d, 8
0x180077c4a  cmp     rax, r8
0x180077c4d  cmovb   rax, r8
0x180077c51  sub     rdx, rax
0x180077c54  cmp     rcx, rdx
0x180077c57  cmovbe  rdi, rax
0x180077c5b  add     rcx, rdi
0x180077c5e  jnz     loc_180077D2E
0x180077c64  mov     r14, [rbx+18h]
0x180077c68  shl     rcx, 3; Size
0x180077c6c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180077c71  mov     r12, rax
0x180077c74  lea     rsi, ds:0[r14*8]
0x180077c7c  lea     rbp, [rsi+rax]
0x180077c80  mov     rcx, [rbx+8]
0x180077c84  lea     r8, [rcx+rsi]; Source
0x180077c88  mov     rdx, [rbx+10h]
0x180077c8c  shl     rdx, 3
0x180077c90  sub     rdx, r8
0x180077c93  add     rdx, rcx
0x180077c96  sar     rdx, 3
0x180077c9a  lea     r15, ds:0[rdx*8]
0x180077ca2  test    rdx, rdx
0x180077ca5  jz      short loc_180077CB6
0x180077ca7  mov     r9, r15; SourceSize
0x180077caa  mov     rdx, r15; DestinationSize
0x180077cad  mov     rcx, rbp; Destination
0x180077cb0  call    cs:__imp_memmove_s
0x180077cb6  lea     r8, [r15+rbp]
0x180077cba  mov     rcx, [rbx+8]; Source
0x180077cbe  cmp     r14, rdi
0x180077cc1  ja      loc_180077D77
0x180077cc7  mov     rbp, rdi
0x180077cca  lea     rdx, [rcx+rsi]
0x180077cce  call    ??$_Uninitialized_copy@PEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@V?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@YAPEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@00AEAV?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@0@@Z; std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *> &)
0x180077cd3  sub     rbp, r14
0x180077cd6  jz      short loc_180077CE9
0x180077cd8  shl     rbp, 3
0x180077cdc  mov     r8, rbp; Size
0x180077cdf  xor     edx, edx; Val
0x180077ce1  mov     rcx, rax; void *
0x180077ce4  call    memset_0
0x180077ce9  test    r14, r14
0x180077cec  jz      short loc_180077CFF
0x180077cee  and     rsi, 0FFFFFFFFFFFFFFF8h
0x180077cf2  mov     r8, rsi; Size
0x180077cf5  mov     rcx, r12; void *
0x180077cf8  xor     edx, edx; Val
0x180077cfa  call    memset_0
0x180077cff  mov     rcx, [rbx+8]; Block
0x180077d03  test    rcx, rcx
0x180077d06  jz      short loc_180077D0D
0x180077d08  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180077d0d  mov     [rbx+8], r12
0x180077d11  add     [rbx+10h], rdi
0x180077d15  lea     r11, [rsp+68h+var_28]
0x180077d1a  mov     rbx, [r11+30h]
0x180077d1e  mov     rbp, [r11+40h]
0x180077d22  mov     rsp, r11
0x180077d25  pop     r15
0x180077d27  pop     r14
0x180077d29  pop     r12
0x180077d2b  pop     rdi
0x180077d2c  pop     rsi
0x180077d2d  retn
0x180077d2e  xor     edx, edx
0x180077d30  or      rax, 0FFFFFFFFFFFFFFFFh
0x180077d34  div     rcx
0x180077d37  cmp     rax, r8
0x180077d3a  jnb     loc_180077C64
0x180077d40  mov     [rsp+68h+arg_8], 0
0x180077d49  lea     rdx, [rsp+68h+arg_8]
0x180077d4e  lea     rcx, [rsp+68h+pExceptionObject]
0x180077d53  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180077d59  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180077d60  mov     [rsp+68h+pExceptionObject], rax
0x180077d65  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180077d6c  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180077d71  call    _CxxThrowException_0
0x180077d77  lea     r14, ds:0[rdi*8]
0x180077d7f  lea     rdx, [r14+rcx]
0x180077d83  call    ??$_Uninitialized_copy@PEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@V?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@YAPEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@00AEAV?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@0@@Z; std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *> &)
0x180077d88  mov     rax, [rbx+8]
0x180077d8c  lea     rdx, [rax+rsi]
0x180077d90  lea     rcx, [r14+rax]; Source
0x180077d94  mov     r8, r12
0x180077d97  call    ??$_Uninitialized_copy@PEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@V?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@YAPEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@00AEAV?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@0@@Z; std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *> &)
0x180077d9c  test    rdi, rdi
0x180077d9f  jz      loc_180077CFF
0x180077da5  and     r14, 0FFFFFFFFFFFFFFF8h
0x180077da9  mov     r8, r14
0x180077dac  mov     rcx, rax
0x180077daf  jmp     loc_180077CF8
```
