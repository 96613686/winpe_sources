# StringToHstringVectorParser(ushort const *)

- ea: `0x180182980`
- end: `0x180182ac0`
- name: `?StringToHstringVectorParser@@YA?AV?$com_ptr_t@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@PEBG@Z`
- size: `320`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18003c1b0`
- `0x180069f90`
- `0x180140c64`
- `0x18017b8a0`
- `0x180182980`
- `0x180184110`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182a3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182a92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182a3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180182a92`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HSTRING __fastcall StringToHstringVectorParser(HSTRING a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 v5; // r12
  __int64 v6; // r15
  __int64 i; // rbx
  __int64 v8; // rax
  const unsigned __int16 *v9; // rdx
  unsigned int v10; // r8d
  __int64 v11; // rax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // r8d
  _QWORD v15[2]; // [rsp+28h] [rbp-28h] BYREF
  _BYTE v16[24]; // [rsp+38h] [rbp-18h] BYREF
  HSTRING string; // [rsp+90h] [rbp+40h] BYREF
  HSTRING v18; // [rsp+98h] [rbp+48h] BYREF
  __int64 v19; // [rsp+A0h] [rbp+50h] BYREF

  string = a1;
  v19 = 0;
  Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
    a1,
    &v19);
  v15[0] = a2;
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(a2 + 2 * v4) );
  v15[1] = v4;
  v5 = 0;
  v6 = std::_Traits_find_ch<std::char_traits<unsigned short>>(a2, v4, 0);
  for ( i = v19; v6 != -1; string = 0 )
  {
    v8 = std::basic_string_view<unsigned short>::substr(v15, v16, v5, v6 - v5);
    v9 = *(const unsigned __int16 **)v8;
    v10 = *(_DWORD *)(v8 + 8);
    string = 0;
    Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v9, v10);
    (*(void (__fastcall **)(__int64, HSTRING))(*(_QWORD *)i + 104LL))(i, string);
    v5 = v6 + 1;
    v6 = std::_Traits_find_ch<std::char_traits<unsigned short>>(a2, v4, v6 + 1);
    WindowsDeleteString(string);
  }
  v11 = std::basic_string_view<unsigned short>::substr(v15, v16, v5, -1);
  v12 = *(const unsigned __int16 **)v11;
  v13 = *(_DWORD *)(v11 + 8);
  v18 = 0;
  Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v18, v12, v13);
  (*(void (__fastcall **)(__int64, HSTRING))(*(_QWORD *)i + 104LL))(i, v18);
  v19 = 0;
  *(_QWORD *)a1 = i;
  WindowsDeleteString(v18);
  v18 = 0;
  wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v19);
  return a1;
}

```

## disassembly

```asm
0x180182980  mov     [rsp-38h+arg_18], rbx
0x180182985  mov     [rsp-38h+string], rcx
0x18018298a  push    rbp
0x18018298b  push    rsi
0x18018298c  push    rdi
0x18018298d  push    r12
0x18018298f  push    r13
0x180182991  push    r14
0x180182993  push    r15
0x180182995  mov     rbp, rsp
0x180182998  sub     rsp, 50h
0x18018299c  mov     rsi, rdx
0x18018299f  mov     r14, rcx
0x1801829a2  xor     r13d, r13d
0x1801829a5  mov     [rbp+arg_10], r13
0x1801829a9  lea     rdx, [rbp+arg_10]
0x1801829ad  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x1801829b2  mov     [rbp+var_28], rsi
0x1801829b6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801829ba  inc     rdi
0x1801829bd  cmp     [rsi+rdi*2], r13w
0x1801829c2  jnz     short loc_1801829BA
0x1801829c4  mov     [rbp+var_20], rdi
0x1801829c8  mov     r12, r13
0x1801829cb  xor     r8d, r8d
0x1801829ce  mov     rdx, rdi
0x1801829d1  mov     rcx, rsi
0x1801829d4  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1801829d9  mov     r15, rax
0x1801829dc  mov     rbx, [rbp+arg_10]
0x1801829e0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801829e4  jz      short loc_180182A4C
0x1801829e6  mov     r9, r15
0x1801829e9  sub     r9, r12
0x1801829ec  mov     r8, r12
0x1801829ef  lea     rdx, [rbp+var_18]
0x1801829f3  lea     rcx, [rbp+var_28]
0x1801829f7  call    ?substr@?$basic_string_view@GU?$char_traits@G@std@@@std@@QEBA?AV12@_K_K@Z; std::basic_string_view<ushort>::substr(unsigned __int64,unsigned __int64)
0x1801829fc  mov     rdx, [rax]; unsigned __int16 *
0x1801829ff  mov     r8d, [rax+8]; unsigned int
0x180182a03  mov     [rbp+string], r13
0x180182a07  lea     rcx, [rbp+string]; this
0x180182a0b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180182a10  mov     rax, [rbx]
0x180182a13  mov     rdx, [rbp+string]
0x180182a17  mov     rcx, rbx
0x180182a1a  mov     rax, [rax+68h]
0x180182a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182a23  lea     r12, [r15+1]
0x180182a27  mov     r8, r12
0x180182a2a  mov     rdx, rdi
0x180182a2d  mov     rcx, rsi
0x180182a30  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180182a35  mov     r15, rax
0x180182a38  mov     rcx, [rbp+string]; string
0x180182a3c  call    cs:__imp_WindowsDeleteString
0x180182a42  mov     [rbp+string], r13
0x180182a46  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180182a4a  jnz     short loc_1801829E6
0x180182a4c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180182a50  mov     r8, r12
0x180182a53  lea     rdx, [rbp+var_18]
0x180182a57  lea     rcx, [rbp+var_28]
0x180182a5b  call    ?substr@?$basic_string_view@GU?$char_traits@G@std@@@std@@QEBA?AV12@_K_K@Z; std::basic_string_view<ushort>::substr(unsigned __int64,unsigned __int64)
0x180182a60  mov     rdx, [rax]; unsigned __int16 *
0x180182a63  mov     r8d, [rax+8]; unsigned int
0x180182a67  mov     [rbp+arg_8], r13
0x180182a6b  lea     rcx, [rbp+arg_8]; this
0x180182a6f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180182a74  mov     rax, [rbx]
0x180182a77  mov     rdx, [rbp+arg_8]
0x180182a7b  mov     rcx, rbx
0x180182a7e  mov     rax, [rax+68h]
0x180182a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180182a87  mov     [rbp+arg_10], r13
0x180182a8b  mov     [r14], rbx
0x180182a8e  mov     rcx, [rbp+arg_8]; string
0x180182a92  call    cs:__imp_WindowsDeleteString
0x180182a98  mov     [rbp+arg_8], r13
0x180182a9c  lea     rcx, [rbp+arg_10]
0x180182aa0  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x180182aa5  mov     rax, r14
0x180182aa8  mov     rbx, [rsp+50h+arg_18]
0x180182ab0  add     rsp, 50h
0x180182ab4  pop     r15
0x180182ab6  pop     r14
0x180182ab8  pop     r13
0x180182aba  pop     r12
0x180182abc  pop     rdi
0x180182abd  pop     rsi
0x180182abe  pop     rbp
0x180182abf  retn
```
