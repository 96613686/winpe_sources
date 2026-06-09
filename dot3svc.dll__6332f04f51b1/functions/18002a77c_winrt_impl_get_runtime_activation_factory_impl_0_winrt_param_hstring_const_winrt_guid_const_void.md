# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18002a77c`
- end: `0x18002aa13`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `663`
- prototype: `_DWORD *__fastcall(_DWORD *, _QWORD *, __int64, __int64)`
- caller_count: `4`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a37c`
- `0x18002a3dc`
- `0x18002a43c`
- `0x18002a49c`

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
- `0x18002a77c`
- `0x18002f140`
- `0x18002f388`
- `0x1800303b0`
- `0x180040010`

## string_xrefs

- `0x18002a7e4`: `combase.dll`
- `0x18002a94f`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
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
  bool v26; // zf
  unsigned int (__fastcall ***v28)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  _BYTE Src[16]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v31; // [rsp+50h] [rbp-28h]
  __int64 v32; // [rsp+58h] [rbp-20h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, __int64))winrt_activation_handler)(v8, a3, a4);
    return a1;
  }
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
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v28);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  std::wstring::wstring(Src, a2);
  while ( 1 )
  {
    do
    {
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      v15 = v12;
      if ( !v13 )
        goto LABEL_28;
      v16 = v13 - 1;
      if ( v13 - 1 >= v14 )
        v16 = v14;
      v17 = v12 + 2 + 2 * v16;
      last_trivial_2 = _std_find_last_trivial_2(v12, v17, 46);
      if ( last_trivial_2 == v17 || (v19 = (last_trivial_2 - v15) >> 1, v19 == -1) )
      {
LABEL_28:
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        std::wstring::_Tidy_deallocate(Src);
        v26 = pperrinfo == 0;
        goto LABEL_29;
      }
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
    }
    while ( !v24 );
    v25 = WINRT_IMPL_GetProcAddress(v24, "DllGetActivationFactory");
    if ( v25 )
      break;
LABEL_24:
    WINRT_IMPL_FreeLibrary(v24);
  }
  v28 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v25)(*a2, &v28)
    || (**v28)(v28, a3, a4) )
  {
    if ( v28 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
    goto LABEL_24;
  }
  *a1 = 0;
  if ( v28 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v28);
  std::wstring::_Tidy_deallocate(Src);
  v26 = pperrinfo == 0;
LABEL_29:
  if ( !v26 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18002a77c  push    rbp
0x18002a77e  push    rbx
0x18002a77f  push    rsi
0x18002a780  push    rdi
0x18002a781  push    r12
0x18002a783  push    r13
0x18002a785  push    r14
0x18002a787  push    r15
0x18002a789  mov     rbp, rsp
0x18002a78c  sub     rsp, 78h
0x18002a790  mov     rax, cs:__security_cookie
0x18002a797  xor     rax, rsp
0x18002a79a  mov     [rbp+var_18], rax
0x18002a79e  mov     r13, r9
0x18002a7a1  mov     r12, r8
0x18002a7a4  mov     r15, rdx
0x18002a7a7  mov     rsi, rcx
0x18002a7aa  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18002a7b1  xor     r14d, r14d
0x18002a7b4  mov     r8, r9
0x18002a7b7  mov     rdx, r12
0x18002a7ba  mov     rcx, [r15]
0x18002a7bd  test    rax, rax
0x18002a7c0  jz      short loc_18002A7CE
0x18002a7c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7c7  mov     [rsi], eax
0x18002a7c9  jmp     loc_18002A9F3
0x18002a7ce  call    RoGetActivationFactory_0
0x18002a7d3  mov     edi, eax
0x18002a7d5  cmp     eax, 800401F0h
0x18002a7da  jnz     short loc_18002A82C
0x18002a7dc  xor     edx, edx; hFile
0x18002a7de  mov     r8d, 1000h; dwFlags
0x18002a7e4  lea     rcx, LibFileName; "combase.dll"
0x18002a7eb  call    LoadLibraryExW_0
0x18002a7f0  lea     rdx, ProcName; "CoIncrementMTAUsage"
0x18002a7f7  mov     rcx, rax; hModule
0x18002a7fa  call    WINRT_IMPL_GetProcAddress
0x18002a7ff  test    rax, rax
0x18002a802  jnz     short loc_18002A80F
0x18002a804  mov     dword ptr [rsi], 800401F0h
0x18002a80a  jmp     loc_18002A9F3
0x18002a80f  mov     [rbp+var_48], r14
0x18002a813  lea     rcx, [rbp+var_48]
0x18002a817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a81c  mov     r8, r13
0x18002a81f  mov     rdx, r12
0x18002a822  mov     rcx, [r15]
0x18002a825  call    RoGetActivationFactory_0
0x18002a82a  mov     edi, eax
0x18002a82c  test    edi, edi
0x18002a82e  jnz     short loc_18002A838
0x18002a830  mov     [rsi], r14d
0x18002a833  jmp     loc_18002A9F3
0x18002a838  mov     [rbp+pperrinfo], r14
0x18002a83c  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18002a840  xor     ecx, ecx; dwReserved
0x18002a842  call    GetErrorInfo_0
0x18002a847  mov     rdx, r15
0x18002a84a  lea     rcx, [rbp+Src]
0x18002a84e  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x18002a853  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002a857  mov     rdx, [rbp+var_28]
0x18002a85b  lea     rcx, [rbp+Src]
0x18002a85f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a864  mov     r14, rax
0x18002a867  test    rdx, rdx
0x18002a86a  jz      loc_18002A9CD
0x18002a870  lea     rcx, [rdx-1]
0x18002a874  cmp     rcx, r8
0x18002a877  cmovnb  rcx, r8
0x18002a87b  add     rax, 2
0x18002a87f  lea     rbx, [rax+rcx*2]
0x18002a883  mov     r8d, 2Eh ; '.'
0x18002a889  mov     rdx, rbx
0x18002a88c  mov     rcx, r14
0x18002a88f  call    __std_find_last_trivial_2
0x18002a894  cmp     rax, rbx
0x18002a897  jz      loc_18002A9CD
0x18002a89d  sub     rax, r14
0x18002a8a0  sar     rax, 1
0x18002a8a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a8a7  jz      loc_18002A9CD
0x18002a8ad  mov     rdx, rax
0x18002a8b0  lea     rcx, [rbp+Src]
0x18002a8b4  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18002a8b9  mov     r8, [rbp+var_28]
0x18002a8bd  mov     rax, [rbp+var_20]
0x18002a8c1  sub     rax, r8
0x18002a8c4  mov     ecx, 4
0x18002a8c9  cmp     rax, rcx
0x18002a8cc  jb      short loc_18002A8F7
0x18002a8ce  lea     rdx, [r8+4]
0x18002a8d2  mov     [rbp+var_28], rdx
0x18002a8d6  lea     rcx, [rbp+Src]
0x18002a8da  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a8df  mov     rcx, 6C006C0064002Eh
0x18002a8e9  mov     [rax+r8*2], rcx
0x18002a8ed  xor     r14d, r14d
0x18002a8f0  mov     [rax+rdx*2], r14w
0x18002a8f5  jmp     short loc_18002A912
0x18002a8f7  mov     [rsp+78h+var_58], rcx; __int64
0x18002a8fc  lea     r9, aDll; ".dll"
0x18002a903  mov     rdx, rcx
0x18002a906  lea     rcx, [rbp+Src]; Src
0x18002a90a  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18002a90f  xor     r14d, r14d
0x18002a912  lea     rcx, [rbp+Src]
0x18002a916  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002a91b  mov     rcx, rax; lpLibFileName
0x18002a91e  xor     edx, edx; hFile
0x18002a920  mov     r8d, 1000h; dwFlags
0x18002a926  call    LoadLibraryExW_0
0x18002a92b  mov     rbx, rax
0x18002a92e  mov     rdx, [rbp+var_28]
0x18002a932  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18002a936  lea     rcx, [rbp+Src]
0x18002a93a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18002a93f  test    rbx, rbx
0x18002a942  mov     r8, 0FFFFFFFFFFFFFFFFh
0x18002a949  jz      loc_18002A857
0x18002a94f  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x18002a956  mov     rcx, rbx; hModule
0x18002a959  call    WINRT_IMPL_GetProcAddress
0x18002a95e  test    rax, rax
0x18002a961  jz      short loc_18002A99F
0x18002a963  mov     [rbp+var_48], r14
0x18002a967  lea     rdx, [rbp+var_48]
0x18002a96b  mov     rcx, [r15]
0x18002a96e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a973  test    eax, eax
0x18002a975  jnz     short loc_18002A990
0x18002a977  mov     rcx, [rbp+var_48]
0x18002a97b  mov     rax, [rcx]
0x18002a97e  mov     r8, r13
0x18002a981  mov     rdx, r12
0x18002a984  mov     rax, [rax]
0x18002a987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a98c  test    eax, eax
0x18002a98e  jz      short loc_18002A9AC
0x18002a990  cmp     [rbp+var_48], r14
0x18002a994  jz      short loc_18002A99F
0x18002a996  lea     rcx, [rbp+var_48]
0x18002a99a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002a99f  mov     rcx, rbx; hLibModule
0x18002a9a2  call    WINRT_IMPL_FreeLibrary
0x18002a9a7  jmp     loc_18002A853
0x18002a9ac  mov     [rsi], r14d
0x18002a9af  cmp     [rbp+var_48], r14
0x18002a9b3  jz      short loc_18002A9BE
0x18002a9b5  lea     rcx, [rbp+var_48]
0x18002a9b9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002a9be  lea     rcx, [rbp+Src]
0x18002a9c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a9c7  cmp     [rbp+pperrinfo], r14
0x18002a9cb  jmp     short loc_18002A9E8
0x18002a9cd  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18002a9d1  xor     ecx, ecx; dwReserved
0x18002a9d3  call    SetErrorInfo_0
0x18002a9d8  mov     [rsi], edi
0x18002a9da  lea     rcx, [rbp+Src]
0x18002a9de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a9e3  cmp     [rbp+pperrinfo], 0
0x18002a9e8  jz      short loc_18002A9F3
0x18002a9ea  lea     rcx, [rbp+pperrinfo]
0x18002a9ee  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002a9f3  mov     rax, rsi
0x18002a9f6  mov     rcx, [rbp+var_18]
0x18002a9fa  xor     rcx, rsp; StackCookie
0x18002a9fd  call    __security_check_cookie
0x18002aa02  add     rsp, 78h
0x18002aa06  pop     r15
0x18002aa08  pop     r14
0x18002aa0a  pop     r13
0x18002aa0c  pop     r12
0x18002aa0e  pop     rdi
0x18002aa0f  pop     rsi
0x18002aa10  pop     rbx
0x18002aa11  pop     rbp
0x18002aa12  retn
```
