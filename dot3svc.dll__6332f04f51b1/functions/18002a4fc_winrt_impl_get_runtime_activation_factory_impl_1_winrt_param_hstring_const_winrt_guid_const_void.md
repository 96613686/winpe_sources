# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18002a4fc`
- end: `0x18002a775`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `633`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a31c`

## callees

- `0x180002190`
- `0x1800025f0`
- `0x180003a62`
- `0x180003a7a`
- `0x180003fb9`
- `0x180003fd7`
- `0x18000402b`
- `0x180004037`
- `0x18000a00c`
- `0x18002836c`
- `0x180029a20`
- `0x18002a4fc`
- `0x18002f140`
- `0x18002f388`
- `0x1800303b0`
- `0x180040010`

## string_xrefs

- `0x18002a560`: `combase.dll`
- `0x18002a6ce`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // r8
  __int64 v15; // r14
  unsigned __int64 v16; // rcx
  __int64 v17; // rbx
  __int64 last_trivial_2; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // rdx
  const WCHAR *v23; // rax
  HMODULE v24; // rbx
  FARPROC v25; // rax
  __int64 v26; // rax
  __int64 v28; // [rsp+30h] [rbp-40h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-38h] BYREF
  _BYTE Src[16]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v31; // [rsp+50h] [rbp-20h]
  __int64 v32; // [rsp+58h] [rbp-18h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD *))winrt_activation_handler)(v8, a3, a4);
  }
  else
  {
    ActivationFactory_0 = RoGetActivationFactory_0(v8, a3, a4);
    if ( ActivationFactory_0 == -2147221008 )
    {
      Library = LoadLibraryExW_0(L"combase.dll", 0, 0x1000u);
      ProcAddress = WINRT_IMPL_GetProcAddress(Library, "CoIncrementMTAUsage");
      if ( !ProcAddress )
      {
        *a1 = -2147221008;
        return a1;
      }
      v28 = 0;
      ((void (__fastcall *)(__int64 *))ProcAddress)(&v28);
      ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
    }
    if ( ActivationFactory_0 )
    {
      pperrinfo = 0;
      GetErrorInfo_0(0, &pperrinfo);
      std::wstring::wstring(Src, a2);
      while ( 1 )
      {
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
        v15 = v12;
        if ( !v13 )
          break;
        v16 = v13 - 1;
        if ( v13 - 1 >= v14 )
          v16 = v14;
        v17 = v12 + 2 + 2 * v16;
        last_trivial_2 = _std_find_last_trivial_2(v12, v17, 46);
        if ( last_trivial_2 == v17 )
          break;
        v19 = (last_trivial_2 - v15) >> 1;
        if ( v19 == -1 )
          break;
        std::wstring::resize(Src, v19);
        if ( (unsigned __int64)(v32 - v31) < 4 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
            Src,
            4);
        }
        else
        {
          v31 += 4;
          v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
          *(_QWORD *)(v20 + 2 * v21) = 0x6C006C0064002ELL;
          *(_WORD *)(v20 + 2 * v22) = 0;
        }
        v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
        v24 = LoadLibraryExW_0(v23, 0, 0x1000u);
        std::wstring::resize(Src, v31 - 4);
        if ( v24 )
        {
          v25 = WINRT_IMPL_GetProcAddress(v24, "DllGetActivationFactory");
          if ( v25 )
          {
            v28 = 0;
            if ( !((unsigned int (__fastcall *)(_QWORD, __int64 *))v25)(*a2, &v28) )
            {
              v26 = v28;
              v28 = 0;
              *a4 = v26;
              *a1 = 0;
              goto LABEL_26;
            }
            if ( v28 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
          }
          WINRT_IMPL_FreeLibrary(v24);
        }
      }
      SetErrorInfo_0(0, pperrinfo);
      *a1 = ActivationFactory_0;
LABEL_26:
      std::wstring::_Tidy_deallocate(Src);
      if ( pperrinfo )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
    }
    else
    {
      *a1 = 0;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18002a4fc  push    rbp
0x18002a4fe  push    rbx
0x18002a4ff  push    rsi
0x18002a500  push    rdi
0x18002a501  push    r12
0x18002a503  push    r14
0x18002a505  push    r15
0x18002a507  mov     rbp, rsp
0x18002a50a  sub     rsp, 70h
0x18002a50e  mov     rax, cs:__security_cookie
0x18002a515  xor     rax, rsp
0x18002a518  mov     [rbp+var_10], rax
0x18002a51c  mov     r15, r9
0x18002a51f  mov     rbx, r8
0x18002a522  mov     r12, rdx
0x18002a525  mov     rsi, rcx
0x18002a528  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18002a52f  mov     r8, r9
0x18002a532  mov     rdx, rbx
0x18002a535  mov     rcx, [r12]
0x18002a539  test    rax, rax
0x18002a53c  jz      short loc_18002A54A
0x18002a53e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a543  mov     [rsi], eax
0x18002a545  jmp     loc_18002A757
0x18002a54a  call    RoGetActivationFactory_0
0x18002a54f  mov     edi, eax
0x18002a551  cmp     eax, 800401F0h
0x18002a556  jnz     short loc_18002A5AD
0x18002a558  xor     edx, edx; hFile
0x18002a55a  mov     r8d, 1000h; dwFlags
0x18002a560  lea     rcx, LibFileName; "combase.dll"
0x18002a567  call    LoadLibraryExW_0
0x18002a56c  lea     rdx, ProcName; "CoIncrementMTAUsage"
0x18002a573  mov     rcx, rax; hModule
0x18002a576  call    WINRT_IMPL_GetProcAddress
0x18002a57b  test    rax, rax
0x18002a57e  jnz     short loc_18002A58B
0x18002a580  mov     dword ptr [rsi], 800401F0h
0x18002a586  jmp     loc_18002A757
0x18002a58b  mov     [rbp+var_40], 0
0x18002a593  lea     rcx, [rbp+var_40]
0x18002a597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a59c  mov     r8, r15
0x18002a59f  mov     rdx, rbx
0x18002a5a2  mov     rcx, [r12]
0x18002a5a6  call    RoGetActivationFactory_0
0x18002a5ab  mov     edi, eax
0x18002a5ad  test    edi, edi
0x18002a5af  jnz     short loc_18002A5B8
0x18002a5b1  mov     [rsi], edi
0x18002a5b3  jmp     loc_18002A757
0x18002a5b8  mov     [rbp+pperrinfo], 0
0x18002a5c0  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18002a5c4  xor     ecx, ecx; dwReserved
0x18002a5c6  call    GetErrorInfo_0
0x18002a5cb  mov     rdx, r12
0x18002a5ce  lea     rcx, [rbp+Src]
0x18002a5d2  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x18002a5d7  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a5db  mov     rdx, [rbp+var_20]
0x18002a5df  lea     rcx, [rbp+Src]
0x18002a5e3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a5e8  mov     r14, rax
0x18002a5eb  test    rdx, rdx
0x18002a5ee  jz      loc_18002A731
0x18002a5f4  lea     rcx, [rdx-1]
0x18002a5f8  cmp     rcx, r8
0x18002a5fb  cmovnb  rcx, r8
0x18002a5ff  add     rax, 2
0x18002a603  lea     rbx, [rax+rcx*2]
0x18002a607  mov     r8d, 2Eh ; '.'
0x18002a60d  mov     rdx, rbx
0x18002a610  mov     rcx, r14
0x18002a613  call    __std_find_last_trivial_2
0x18002a618  cmp     rax, rbx
0x18002a61b  jz      loc_18002A731
0x18002a621  sub     rax, r14
0x18002a624  sar     rax, 1
0x18002a627  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a62b  jz      loc_18002A731
0x18002a631  mov     rdx, rax
0x18002a634  lea     rcx, [rbp+Src]
0x18002a638  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18002a63d  mov     r8, [rbp+var_20]
0x18002a641  mov     rax, [rbp+var_18]
0x18002a645  sub     rax, r8
0x18002a648  mov     ecx, 4
0x18002a64d  cmp     rax, rcx
0x18002a650  jb      short loc_18002A679
0x18002a652  lea     rdx, [r8+4]
0x18002a656  mov     [rbp+var_20], rdx
0x18002a65a  lea     rcx, [rbp+Src]
0x18002a65e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a663  mov     rcx, 6C006C0064002Eh
0x18002a66d  mov     [rax+r8*2], rcx
0x18002a671  xor     ecx, ecx
0x18002a673  mov     [rax+rdx*2], cx
0x18002a677  jmp     short loc_18002A691
0x18002a679  mov     [rsp+70h+var_50], rcx; __int64
0x18002a67e  lea     r9, aDll; ".dll"
0x18002a685  mov     rdx, rcx
0x18002a688  lea     rcx, [rbp+Src]; Src
0x18002a68c  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18002a691  lea     rcx, [rbp+Src]
0x18002a695  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a69a  mov     rcx, rax; lpLibFileName
0x18002a69d  xor     edx, edx; hFile
0x18002a69f  mov     r8d, 1000h; dwFlags
0x18002a6a5  call    LoadLibraryExW_0
0x18002a6aa  mov     rbx, rax
0x18002a6ad  mov     rdx, [rbp+var_20]
0x18002a6b1  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18002a6b5  lea     rcx, [rbp+Src]
0x18002a6b9  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18002a6be  test    rbx, rbx
0x18002a6c1  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18002a6c8  jz      loc_18002A5DB
0x18002a6ce  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18002a6d5  mov     rcx, rbx; hModule
0x18002a6d8  call    WINRT_IMPL_GetProcAddress
0x18002a6dd  test    rax, rax
0x18002a6e0  jnz     short loc_18002A6EF
0x18002a6e2  mov     rcx, rbx; hLibModule
0x18002a6e5  call    WINRT_IMPL_FreeLibrary
0x18002a6ea  jmp     loc_18002A5D7
0x18002a6ef  mov     [rbp+var_40], 0
0x18002a6f7  lea     rdx, [rbp+var_40]
0x18002a6fb  mov     rcx, [r12]
0x18002a6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a704  test    eax, eax
0x18002a706  jz      short loc_18002A71A
0x18002a708  cmp     [rbp+var_40], 0
0x18002a70d  jz      short loc_18002A6E2
0x18002a70f  lea     rcx, [rbp+var_40]
0x18002a713  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002a718  jmp     short loc_18002A6E2
0x18002a71a  mov     rax, [rbp+var_40]
0x18002a71e  mov     [rbp+var_40], 0
0x18002a726  mov     [r15], rax
0x18002a729  mov     dword ptr [rsi], 0
0x18002a72f  jmp     short loc_18002A73E
0x18002a731  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18002a735  xor     ecx, ecx; dwReserved
0x18002a737  call    SetErrorInfo_0
0x18002a73c  mov     [rsi], edi
0x18002a73e  lea     rcx, [rbp+Src]
0x18002a742  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a747  cmp     [rbp+pperrinfo], 0
0x18002a74c  jz      short loc_18002A757
0x18002a74e  lea     rcx, [rbp+pperrinfo]
0x18002a752  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002a757  mov     rax, rsi
0x18002a75a  mov     rcx, [rbp+var_10]
0x18002a75e  xor     rcx, rsp; StackCookie
0x18002a761  call    __security_check_cookie
0x18002a766  add     rsp, 70h
0x18002a76a  pop     r15
0x18002a76c  pop     r14
0x18002a76e  pop     r12
0x18002a770  pop     rdi
0x18002a771  pop     rsi
0x18002a772  pop     rbx
0x18002a773  pop     rbp
0x18002a774  retn
```
