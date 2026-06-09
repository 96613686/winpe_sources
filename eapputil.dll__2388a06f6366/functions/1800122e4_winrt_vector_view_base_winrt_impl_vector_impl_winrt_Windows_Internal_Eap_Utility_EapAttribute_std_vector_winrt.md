# winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::allocator<winrt::Windows::Internal::Eap::Utility::EapAttribute>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Eap::Utility::EapAttribute,winrt::impl::collection_version>::IndexOf(winrt::Windows::Internal::Eap::Utility::EapAttribute const &,uint &)

- ea: `0x1800122e4`
- end: `0x180012371`
- name: `?IndexOf@?$vector_view_base@U?$vector_impl@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$vector@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@V?$allocator@UEapAttribute@Utility@Eap@Internal@Windows@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@6@@impl@winrt@@UEapAttribute@Utility@Eap@Internal@Windows@3@Ucollection_version@23@@winrt@@QEBA_NAEBUEapAttribute@Utility@Eap@Internal@Windows@2@AEAI@Z`
- size: `141`
- prototype: `bool __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180012250`
- `0x1800122a0`

## callees

- `0x1800116ac`
- `0x1800122e4`

## pseudocode

```c
bool __fastcall winrt::vector_view_base<winrt::impl::vector_impl<winrt::Windows::Internal::Eap::Utility::EapAttribute,std::vector<winrt::Windows::Internal::Eap::Utility::EapAttribute>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Internal::Eap::Utility::EapAttribute,winrt::impl::collection_version>::IndexOf(
        __int64 a1,
        __int64 a2,
        _DWORD *a3)
{
  __int64 v3; // r14
  __int64 v4; // r15
  __int64 v8; // rbx
  __int64 v9; // rsi
  __int64 v10; // rax
  __int64 v11; // rbx

  v3 = a1 + 8;
  v4 = a1 + 16;
  if ( !a1 )
    v3 = 48;
  if ( !a1 )
    v4 = 56;
  v8 = *(_QWORD *)v3;
  v9 = *(_QWORD *)v4;
  while ( v8 != v9 && !(unsigned __int8)winrt::Windows::Foundation::operator==(a2, v8) )
    v8 += 8;
  v10 = a1 + 8;
  v11 = (v8 - *(_QWORD *)v3) >> 3;
  *a3 = v11;
  if ( !a1 )
    v10 = 48;
  return (unsigned int)v11 < (unsigned int)((__int64)(*(_QWORD *)v4 - *(_QWORD *)v10) >> 3);
}

```

## disassembly

```asm
0x1800122e4  push    rbx
0x1800122e6  push    rbp
0x1800122e7  push    rsi
0x1800122e8  push    rdi
0x1800122e9  push    r12
0x1800122eb  push    r13
0x1800122ed  push    r14
0x1800122ef  push    r15
0x1800122f1  sub     rsp, 28h
0x1800122f5  mov     r13d, 30h ; '0'
0x1800122fb  lea     r14, [rcx+8]
0x1800122ff  test    rcx, rcx
0x180012302  lea     r15, [rcx+10h]
0x180012306  mov     r12, r8
0x180012309  mov     rbp, rdx
0x18001230c  cmovz   r14, r13
0x180012310  mov     rdi, rcx
0x180012313  lea     eax, [r13+8]
0x180012317  cmovz   r15, rax
0x18001231b  mov     rbx, [r14]
0x18001231e  mov     rsi, [r15]
0x180012321  jmp     short loc_180012336
0x180012323  mov     rdx, rbx
0x180012326  mov     rcx, rbp
0x180012329  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18001232e  test    al, al
0x180012330  jnz     short loc_18001233B
0x180012332  add     rbx, 8
0x180012336  cmp     rbx, rsi
0x180012339  jnz     short loc_180012323
0x18001233b  sub     rbx, [r14]
0x18001233e  lea     rax, [rdi+8]
0x180012342  sar     rbx, 3
0x180012346  test    rdi, rdi
0x180012349  mov     [r12], ebx
0x18001234d  mov     rcx, [r15]
0x180012350  cmovz   rax, r13
0x180012354  sub     rcx, [rax]
0x180012357  sar     rcx, 3
0x18001235b  cmp     ebx, ecx
0x18001235d  setb    al
0x180012360  add     rsp, 28h
0x180012364  pop     r15
0x180012366  pop     r14
0x180012368  pop     r13
0x18001236a  pop     r12
0x18001236c  pop     rdi
0x18001236d  pop     rsi
0x18001236e  pop     rbp
0x18001236f  pop     rbx
0x180012370  retn
```
