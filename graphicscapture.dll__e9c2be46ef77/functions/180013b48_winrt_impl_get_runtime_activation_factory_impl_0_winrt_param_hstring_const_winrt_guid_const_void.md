# winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x180013b48`
- end: `0x180013d9c`
- name: `??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `596`
- prototype: ``
- caller_count: `3`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013a88`
- `0x180013ae8`
- `0x18001b5c0`

## callees

- `0x180001640`
- `0x1800023a8`
- `0x1800023d5`
- `0x1800023f9`
- `0x18000247d`
- `0x180002489`
- `0x180002495`
- `0x180002720`
- `0x1800065f0`
- `0x1800133b8`
- `0x180013638`
- `0x180013b48`
- `0x1800153f8`
- `0x180015acc`
- `0x180015dbc`
- `0x180028010`

## string_xrefs

- `0x180013bb1`: `combase.dll`
- `0x180013cb0`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<0>(_DWORD *a1, _QWORD *a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rcx
  int ActivationFactory_0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  const WCHAR *v15; // rcx
  HMODULE v16; // rdi
  FARPROC v17; // rax
  __int64 v18; // rax
  unsigned int (__fastcall ***v20)(_QWORD, __int64, __int64); // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v23; // [rsp+50h] [rbp-28h]
  unsigned __int64 v24; // [rsp+58h] [rbp-20h]

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
    v20 = 0;
    ((void (__fastcall *)(unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))ProcAddress)(&v20);
    ActivationFactory_0 = RoGetActivationFactory_0(*a2, a3, a4);
  }
  if ( !ActivationFactory_0 )
  {
    *a1 = 0;
    return a1;
  }
  pperrinfo = 0;
  GetErrorInfo_0(0, &pperrinfo);
  std::wstring::wstring(lpLibFileName, a2);
  while ( 1 )
  {
    do
    {
      v18 = std::wstring::rfind(lpLibFileName);
      if ( v18 == -1 )
      {
        SetErrorInfo_0(0, pperrinfo);
        *a1 = ActivationFactory_0;
        goto LABEL_24;
      }
      std::wstring::resize(lpLibFileName, v18);
      if ( v24 - v23 < 4 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          lpLibFileName,
          4);
      }
      else
      {
        v23 += 4;
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(lpLibFileName);
        *(_QWORD *)(v12 + 2 * v13) = 0x6C006C0064002ELL;
        *(_WORD *)(v12 + 2 * v14) = 0;
      }
      v15 = (const WCHAR *)lpLibFileName;
      if ( v24 > 7 )
        v15 = lpLibFileName[0];
      v16 = LoadLibraryExW_0(v15, 0, 0x1000u);
      std::wstring::resize(lpLibFileName, v23 - 4);
    }
    while ( !v16 );
    v17 = WINRT_IMPL_GetProcAddress(v16, "DllGetActivationFactory");
    if ( v17 )
      break;
LABEL_21:
    WINRT_IMPL_FreeLibrary(v16);
  }
  v20 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, unsigned int (__fastcall ****)(_QWORD, __int64, __int64)))v17)(*a2, &v20)
    || (**v20)(v20, a3, a4) )
  {
    if ( v20 )
      winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v20);
    goto LABEL_21;
  }
  *a1 = 0;
  if ( v20 )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v20);
LABEL_24:
  if ( v24 > 7 )
    std::_Deallocate<16>(lpLibFileName[0], 2 * v24 + 2);
  LOWORD(lpLibFileName[0]) = 0;
  v24 = 7;
  v23 = 0;
  if ( pperrinfo )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x180013b48  push    rbp
0x180013b4a  push    rbx
0x180013b4b  push    rsi
0x180013b4c  push    rdi
0x180013b4d  push    r12
0x180013b4f  push    r13
0x180013b51  push    r14
0x180013b53  push    r15
0x180013b55  mov     rbp, rsp
0x180013b58  sub     rsp, 78h
0x180013b5c  mov     rax, cs:__security_cookie
0x180013b63  xor     rax, rsp
0x180013b66  mov     [rbp+var_18], rax
0x180013b6a  mov     r15, r9
0x180013b6d  mov     r14, r8
0x180013b70  mov     r12, rdx
0x180013b73  mov     rsi, rcx
0x180013b76  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x180013b7d  xor     r13d, r13d
0x180013b80  mov     r8, r9
0x180013b83  mov     rdx, r14
0x180013b86  mov     rcx, [r12]
0x180013b8a  test    rax, rax
0x180013b8d  jz      short loc_180013B9B
0x180013b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b94  mov     [rsi], eax
0x180013b96  jmp     loc_180013D68
0x180013b9b  call    RoGetActivationFactory_0
0x180013ba0  mov     ebx, eax
0x180013ba2  cmp     eax, 800401F0h
0x180013ba7  jnz     short loc_180013BFA
0x180013ba9  xor     edx, edx; hFile
0x180013bab  mov     r8d, 1000h; dwFlags
0x180013bb1  lea     rcx, LibFileName; "combase.dll"
0x180013bb8  call    LoadLibraryExW_0
0x180013bbd  lea     rdx, ProcName; "CoIncrementMTAUsage"
0x180013bc4  mov     rcx, rax; hModule
0x180013bc7  call    WINRT_IMPL_GetProcAddress
0x180013bcc  test    rax, rax
0x180013bcf  jnz     short loc_180013BDC
0x180013bd1  mov     dword ptr [rsi], 800401F0h
0x180013bd7  jmp     loc_180013D68
0x180013bdc  mov     [rbp+var_48], r13
0x180013be0  lea     rcx, [rbp+var_48]
0x180013be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013be9  mov     r8, r15
0x180013bec  mov     rdx, r14
0x180013bef  mov     rcx, [r12]
0x180013bf3  call    RoGetActivationFactory_0
0x180013bf8  mov     ebx, eax
0x180013bfa  test    ebx, ebx
0x180013bfc  jnz     short loc_180013C06
0x180013bfe  mov     [rsi], r13d
0x180013c01  jmp     loc_180013D68
0x180013c06  mov     [rbp+pperrinfo], r13
0x180013c0a  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x180013c0e  xor     ecx, ecx; dwReserved
0x180013c10  call    GetErrorInfo_0
0x180013c15  mov     rdx, r12
0x180013c18  lea     rcx, [rbp+lpLibFileName]
0x180013c1c  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x180013c21  jmp     loc_180013D0D
0x180013c26  mov     rdx, rax
0x180013c29  lea     rcx, [rbp+lpLibFileName]
0x180013c2d  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180013c32  mov     r8, [rbp+var_28]
0x180013c36  mov     rax, [rbp+var_20]
0x180013c3a  sub     rax, r8
0x180013c3d  lea     rcx, [rbp+lpLibFileName]; Src
0x180013c41  cmp     rax, 4
0x180013c45  jb      short loc_180013C69
0x180013c47  lea     rdx, [r8+4]
0x180013c4b  mov     [rbp+var_28], rdx
0x180013c4f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEAAPEAGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013c54  mov     rcx, 6C006C0064002Eh
0x180013c5e  mov     [rax+r8*2], rcx
0x180013c62  mov     [rax+rdx*2], r13w
0x180013c67  jmp     short loc_180013C7C
0x180013c69  mov     [rsp+78h+var_58], 4; __int64
0x180013c72  mov     edx, 4
0x180013c77  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x180013c7c  lea     rcx, [rbp+lpLibFileName]
0x180013c80  cmp     [rbp+var_20], 7
0x180013c85  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x180013c8a  xor     edx, edx; hFile
0x180013c8c  mov     r8d, 1000h; dwFlags
0x180013c92  call    LoadLibraryExW_0
0x180013c97  mov     rdi, rax
0x180013c9a  mov     rdx, [rbp+var_28]
0x180013c9e  add     rdx, 0FFFFFFFFFFFFFFFCh
0x180013ca2  lea     rcx, [rbp+lpLibFileName]
0x180013ca6  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180013cab  test    rdi, rdi
0x180013cae  jz      short loc_180013D0D
0x180013cb0  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x180013cb7  mov     rcx, rdi; hModule
0x180013cba  call    WINRT_IMPL_GetProcAddress
0x180013cbf  test    rax, rax
0x180013cc2  jz      short loc_180013D05
0x180013cc4  mov     [rbp+var_48], r13
0x180013cc8  lea     rdx, [rbp+var_48]
0x180013ccc  mov     rcx, [r12]
0x180013cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cd5  test    eax, eax
0x180013cd7  jnz     short loc_180013CF6
0x180013cd9  mov     rcx, [rbp+var_48]
0x180013cdd  mov     rax, [rcx]
0x180013ce0  mov     r8, r15
0x180013ce3  mov     rdx, r14
0x180013ce6  mov     rax, [rax]
0x180013ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013cee  test    eax, eax
0x180013cf0  jz      loc_180013D88
0x180013cf6  cmp     [rbp+var_48], r13
0x180013cfa  jz      short loc_180013D05
0x180013cfc  lea     rcx, [rbp+var_48]
0x180013d00  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180013d05  mov     rcx, rdi; hLibModule
0x180013d08  call    WINRT_IMPL_FreeLibrary
0x180013d0d  lea     rcx, [rbp+lpLibFileName]
0x180013d11  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x180013d16  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013d1a  jnz     loc_180013C26
0x180013d20  mov     rdx, [rbp+pperrinfo]; perrinfo
0x180013d24  xor     ecx, ecx; dwReserved
0x180013d26  call    SetErrorInfo_0
0x180013d2b  mov     [rsi], ebx
0x180013d2d  mov     rdx, [rbp+var_20]
0x180013d31  cmp     rdx, 7
0x180013d35  jbe     short loc_180013D48
0x180013d37  lea     rdx, ds:2[rdx*2]
0x180013d3f  mov     rcx, [rbp+lpLibFileName]
0x180013d43  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180013d48  cmp     [rbp+pperrinfo], r13
0x180013d4c  mov     word ptr [rbp+lpLibFileName], r13w
0x180013d51  mov     [rbp+var_20], 7
0x180013d59  mov     [rbp+var_28], r13
0x180013d5d  jz      short loc_180013D68
0x180013d5f  lea     rcx, [rbp+pperrinfo]
0x180013d63  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180013d68  mov     rax, rsi
0x180013d6b  mov     rcx, [rbp+var_18]
0x180013d6f  xor     rcx, rsp; StackCookie
0x180013d72  call    __security_check_cookie
0x180013d77  add     rsp, 78h
0x180013d7b  pop     r15
0x180013d7d  pop     r14
0x180013d7f  pop     r13
0x180013d81  pop     r12
0x180013d83  pop     rdi
0x180013d84  pop     rsi
0x180013d85  pop     rbx
0x180013d86  pop     rbp
0x180013d87  retn
0x180013d88  mov     [rsi], r13d
0x180013d8b  cmp     [rbp+var_48], r13
0x180013d8f  jz      short loc_180013D2D
0x180013d91  lea     rcx, [rbp+var_48]
0x180013d95  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x180013d9a  jmp     short loc_180013D2D
```
