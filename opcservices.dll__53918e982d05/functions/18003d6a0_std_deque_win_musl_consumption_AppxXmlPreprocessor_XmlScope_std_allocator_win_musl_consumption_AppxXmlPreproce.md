# std::deque<win_musl::consumption::AppxXmlPreprocessor::XmlScope,std::allocator<win_musl::consumption::AppxXmlPreprocessor::XmlScope>>::_Growmap(unsigned __int64)

- ea: `0x18003d6a0`
- end: `0x18003d880`
- name: `?_Growmap@?$deque@VXmlScope@AppxXmlPreprocessor@consumption@win_musl@@V?$allocator@VXmlScope@AppxXmlPreprocessor@consumption@win_musl@@@std@@@std@@IEAAX_K@Z`
- size: `480`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18003e180`
- `0x18003e2d0`

## callees

- `0x18003d43c`
- `0x18003d6a0`
- `0x18004d108`
- `0x1800cd178`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800d6354`

## import_xrefs

- `msvcrt!memmove_s` at `0x18003d76a`
- `msvcrt!memmove_s` at `0x18003d79c`
- `msvcrt!memmove_s` at `0x18003d76a`
- `msvcrt!memmove_s` at `0x18003d79c`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18003d85c`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18003d85c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::deque<win_musl::consumption::AppxXmlPreprocessor::XmlScope>::_Growmap(_QWORD *a1, const char *a2)
{
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rbp
  char *v8; // rax
  void *v9; // r12
  __int64 v10; // rsi
  char *v11; // r15
  char *v12; // r10
  __int64 v13; // rcx
  __int64 v14; // r14
  char *v15; // r15
  size_t v16; // r8
  void *v17; // rcx
  void *v18; // rcx
  __int64 v19; // rax
  _QWORD pExceptionObject[3]; // [rsp+28h] [rbp-40h] BYREF
  const char *v21; // [rsp+78h] [rbp+10h] BYREF

  v21 = a2;
  v3 = a1[2];
  v4 = 1;
  if ( v3 == 0x2E8BA2E8BA2E8BALL )
    std::deque<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>>::_Xlen(0x2E8BA2E8BA2E8BALL);
  v5 = v3 >> 1;
  if ( v3 >> 1 < 8 )
    v5 = 8;
  if ( v3 <= 0x2E8BA2E8BA2E8BALL - v5 )
    v4 = v5;
  v6 = v4 + v3;
  if ( v6 )
  {
    if ( 0xFFFFFFFFFFFFFFFFuLL / v6 < 8 )
    {
      v21 = 0;
      exception::exception((exception *)pExceptionObject, &v21);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  else
  {
    v6 = 0;
  }
  v7 = a1[3];
  v8 = (char *)operator new(8 * v6);
  v9 = v8;
  v10 = 8 * v7;
  v11 = &v8[8 * v7];
  v12 = (char *)a1[1];
  v13 = (__int64)(8LL * a1[2] - 8 * v7) >> 3;
  v14 = 8 * v13;
  if ( v13 )
  {
    memmove_s(&v8[8 * v7], 8 * v13, &v12[8 * v7], 8 * v13);
    v12 = (char *)a1[1];
  }
  v15 = &v11[v14];
  if ( v7 > v4 )
  {
    std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(
      v12,
      (__int64)&v12[8 * v4],
      v15);
    v19 = std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(
            (void *)(8 * v4 + a1[1]),
            a1[1] + v10,
            v9);
    if ( v4 )
    {
      v16 = 8 * v4;
      v17 = (void *)v19;
      goto LABEL_17;
    }
  }
  else
  {
    if ( v10 >> 3 )
      memmove_s(v15, 8 * (v10 >> 3), v12, 8 * (v10 >> 3));
    if ( v4 != v7 )
      memset_0(&v15[8 * (v10 >> 3)], 0, 8 * (v4 - v7));
    if ( v7 )
    {
      v16 = 8 * v7;
      v17 = v9;
LABEL_17:
      memset_0(v17, 0, v16);
    }
  }
  v18 = (void *)a1[1];
  if ( v18 )
    operator delete(v18);
  a1[1] = v9;
  a1[2] += v4;
}

```

## disassembly

```asm
0x18003d6a0  mov     rax, rsp
0x18003d6a3  mov     [rax+10h], rdx
0x18003d6a7  push    rsi
0x18003d6a8  push    rdi
0x18003d6a9  push    r12
0x18003d6ab  push    r14
0x18003d6ad  push    r15
0x18003d6af  sub     rsp, 40h
0x18003d6b3  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18003d6bb  mov     [rax+8], rbx
0x18003d6bf  mov     [rax+18h], rbp
0x18003d6c3  mov     rbx, rcx
0x18003d6c6  mov     rcx, [rcx+10h]
0x18003d6ca  mov     rdx, 2E8BA2E8BA2E8BAh
0x18003d6d4  mov     rax, rdx
0x18003d6d7  sub     rax, rcx
0x18003d6da  mov     edi, 1
0x18003d6df  cmp     rax, rdi
0x18003d6e2  jb      loc_18003D83C
0x18003d6e8  mov     rax, rcx
0x18003d6eb  shr     rax, 1
0x18003d6ee  lea     r8d, [rdi+7]
0x18003d6f2  cmp     rax, r8
0x18003d6f5  cmovb   rax, r8
0x18003d6f9  sub     rdx, rax
0x18003d6fc  cmp     rcx, rdx
0x18003d6ff  cmovbe  rdi, rax
0x18003d703  add     rcx, rdi
0x18003d706  jz      loc_18003D842
0x18003d70c  xor     edx, edx
0x18003d70e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003d712  div     rcx
0x18003d715  cmp     rax, r8
0x18003d718  jb      loc_18003D849
0x18003d71e  mov     rbp, [rbx+18h]
0x18003d722  shl     rcx, 3; Size
0x18003d726  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003d72b  mov     r12, rax
0x18003d72e  lea     rsi, ds:0[rbp*8]
0x18003d736  lea     r15, [rsi+rax]
0x18003d73a  mov     r10, [rbx+8]
0x18003d73e  lea     r8, [r10+rsi]; Source
0x18003d742  mov     rcx, [rbx+10h]
0x18003d746  shl     rcx, 3
0x18003d74a  sub     rcx, r8
0x18003d74d  add     rcx, r10
0x18003d750  sar     rcx, 3
0x18003d754  lea     r14, ds:0[rcx*8]
0x18003d75c  test    rcx, rcx
0x18003d75f  jz      short loc_18003D774
0x18003d761  mov     r9, r14; SourceSize
0x18003d764  mov     rdx, r14; DestinationSize
0x18003d767  mov     rcx, r15; Destination
0x18003d76a  call    cs:__imp_memmove_s
0x18003d770  mov     r10, [rbx+8]
0x18003d774  add     r15, r14
0x18003d777  cmp     rbp, rdi
0x18003d77a  ja      short loc_18003D7F9
0x18003d77c  mov     rax, rsi
0x18003d77f  sar     rax, 3
0x18003d783  lea     r14, ds:0[rax*8]
0x18003d78b  test    rax, rax
0x18003d78e  jz      short loc_18003D7A2
0x18003d790  mov     r9, r14; SourceSize
0x18003d793  mov     r8, r10; Source
0x18003d796  mov     rdx, r14; DestinationSize
0x18003d799  mov     rcx, r15; Destination
0x18003d79c  call    cs:__imp_memmove_s
0x18003d7a2  mov     r8, rdi
0x18003d7a5  sub     r8, rbp
0x18003d7a8  lea     rcx, [r14+r15]; void *
0x18003d7ac  jz      short loc_18003D7B9
0x18003d7ae  shl     r8, 3; Size
0x18003d7b2  xor     edx, edx; Val
0x18003d7b4  call    memset_0
0x18003d7b9  test    rbp, rbp
0x18003d7bc  jz      short loc_18003D7CF
0x18003d7be  and     rsi, 0FFFFFFFFFFFFFFF8h
0x18003d7c2  mov     r8, rsi; Size
0x18003d7c5  mov     rcx, r12; void *
0x18003d7c8  xor     edx, edx; Val
0x18003d7ca  call    memset_0
0x18003d7cf  mov     rcx, [rbx+8]; Block
0x18003d7d3  test    rcx, rcx
0x18003d7d6  jnz     short loc_18003D835
0x18003d7d8  mov     [rbx+8], r12
0x18003d7dc  add     [rbx+10h], rdi
0x18003d7e0  lea     r11, [rsp+68h+var_28]
0x18003d7e5  mov     rbx, [r11+30h]
0x18003d7e9  mov     rbp, [r11+40h]
0x18003d7ed  mov     rsp, r11
0x18003d7f0  pop     r15
0x18003d7f2  pop     r14
0x18003d7f4  pop     r12
0x18003d7f6  pop     rdi
0x18003d7f7  pop     rsi
0x18003d7f8  retn
0x18003d7f9  lea     r14, ds:0[rdi*8]
0x18003d801  lea     rdx, [r14+r10]
0x18003d805  mov     r8, r15
0x18003d808  mov     rcx, r10; Source
0x18003d80b  call    ??$_Uninitialized_copy@PEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@V?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@YAPEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@00AEAV?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@0@@Z; std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *> &)
0x18003d810  mov     rax, [rbx+8]
0x18003d814  lea     rdx, [rax+rsi]
0x18003d818  lea     rcx, [r14+rax]; Source
0x18003d81c  mov     r8, r12
0x18003d81f  call    ??$_Uninitialized_copy@PEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@V?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@YAPEAPEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEAPEAV12@00AEAV?$allocator@PEAV?$scope@PEAUreceiver_instance@ZipStreamInflator@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@0@@Z; std::_Uninitialized_copy<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *>>(win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> * *,std::allocator<win_scope::scope<win_musl::ZipStreamInflator::receiver_instance *,win_scope::const_policies<win_scope::shared_policies>> *> &)
0x18003d824  test    rdi, rdi
0x18003d827  jz      short loc_18003D7CF
0x18003d829  and     r14, 0FFFFFFFFFFFFFFF8h
0x18003d82d  mov     r8, r14
0x18003d830  mov     rcx, rax
0x18003d833  jmp     short loc_18003D7C8
0x18003d835  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003d83a  jmp     short loc_18003D7D8
0x18003d83c  call    ?_Xlen@?$deque@V?$scope@PEAV?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@V?$allocator@V?$scope@PEAV?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@std@@@std@@KAXXZ; std::deque<win_scope::scope<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>> *,win_scope::const_policies<win_scope::shared_policies>>>::_Xlen(void)
0x18003d842  xor     ecx, ecx
0x18003d844  jmp     loc_18003D71E
0x18003d849  mov     [rsp+68h+arg_8], 0
0x18003d852  lea     rdx, [rsp+68h+arg_8]
0x18003d857  lea     rcx, [rsp+68h+pExceptionObject]
0x18003d85c  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18003d862  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18003d869  mov     [rsp+68h+pExceptionObject], rax
0x18003d86e  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18003d875  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18003d87a  call    _CxxThrowException_0
```
