# winrt::impl::get_runtime_activation_factory_impl<1>(winrt::param::hstring const &,winrt::guid const &,void * *)

- ea: `0x18001c314`
- end: `0x18001c552`
- name: `??$get_runtime_activation_factory_impl@$00@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d240`

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
- `0x1800153f8`
- `0x180015acc`
- `0x180015dbc`
- `0x18001c314`
- `0x180028010`

## string_xrefs

- `0x18001c375`: `combase.dll`
- `0x18001c47b`: `DllGetActivationFactory`

## pseudocode

```c
_DWORD *__fastcall winrt::impl::get_runtime_activation_factory_impl<1>(_DWORD *a1, _QWORD *a2, __int64 a3, _QWORD *a4)
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
  __int64 v20; // rax
  __int64 v21; // [rsp+30h] [rbp-48h] BYREF
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp-40h] BYREF
  LPCWSTR lpLibFileName[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v24; // [rsp+50h] [rbp-28h]
  unsigned __int64 v25; // [rsp+58h] [rbp-20h]

  v8 = *a2;
  if ( winrt_activation_handler )
  {
    *a1 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD *))winrt_activation_handler)(v8, a3, a4);
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
    v21 = 0;
    ((void (__fastcall *)(__int64 *))ProcAddress)(&v21);
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
        goto LABEL_23;
      }
      std::wstring::resize(lpLibFileName, v18);
      if ( v25 - v24 < 4 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
          lpLibFileName,
          4);
      }
      else
      {
        v24 += 4;
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(lpLibFileName);
        *(_QWORD *)(v12 + 2 * v13) = 0x6C006C0064002ELL;
        *(_WORD *)(v12 + 2 * v14) = 0;
      }
      v15 = (const WCHAR *)lpLibFileName;
      if ( v25 > 7 )
        v15 = lpLibFileName[0];
      v16 = LoadLibraryExW_0(v15, 0, 0x1000u);
      std::wstring::resize(lpLibFileName, v24 - 4);
    }
    while ( !v16 );
    v17 = WINRT_IMPL_GetProcAddress(v16, "DllGetActivationFactory");
    if ( v17 )
      break;
LABEL_20:
    WINRT_IMPL_FreeLibrary(v16);
  }
  v21 = 0;
  if ( ((unsigned int (__fastcall *)(_QWORD, __int64 *))v17)(*a2, &v21) )
  {
    if ( v21 )
      winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&v21);
    goto LABEL_20;
  }
  v20 = v21;
  v21 = 0;
  *a4 = v20;
  *a1 = 0;
LABEL_23:
  if ( v25 > 7 )
    std::_Deallocate<16>(lpLibFileName[0], 2 * v25 + 2);
  LOWORD(lpLibFileName[0]) = 0;
  v25 = 7;
  v24 = 0;
  if ( pperrinfo )
    winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(&pperrinfo);
  return a1;
}

```

## disassembly

```asm
0x18001c314  push    rbp
0x18001c316  push    rbx
0x18001c317  push    rsi
0x18001c318  push    rdi
0x18001c319  push    r14
0x18001c31b  push    r15
0x18001c31d  mov     rbp, rsp
0x18001c320  sub     rsp, 78h
0x18001c324  mov     rax, cs:__security_cookie
0x18001c32b  xor     rax, rsp
0x18001c32e  mov     [rbp+var_18], rax
0x18001c332  mov     r14, r9
0x18001c335  mov     rdi, r8
0x18001c338  mov     r15, rdx
0x18001c33b  mov     rsi, rcx
0x18001c33e  mov     rax, cs:?winrt_activation_handler@@3P6AHPEAXAEBUguid@winrt@@PEAPEAX@_EEA
0x18001c345  mov     r8, r9
0x18001c348  mov     rdx, rdi
0x18001c34b  mov     rcx, [r15]
0x18001c34e  test    rax, rax
0x18001c351  jz      short loc_18001C35F
0x18001c353  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c358  mov     [rsi], eax
0x18001c35a  jmp     loc_18001C51F
0x18001c35f  call    RoGetActivationFactory_0
0x18001c364  mov     ebx, eax
0x18001c366  cmp     eax, 800401F0h
0x18001c36b  jnz     short loc_18001C3C1
0x18001c36d  xor     edx, edx; hFile
0x18001c36f  mov     r8d, 1000h; dwFlags
0x18001c375  lea     rcx, LibFileName; "combase.dll"
0x18001c37c  call    LoadLibraryExW_0
0x18001c381  lea     rdx, ProcName; "CoIncrementMTAUsage"
0x18001c388  mov     rcx, rax; hModule
0x18001c38b  call    WINRT_IMPL_GetProcAddress
0x18001c390  test    rax, rax
0x18001c393  jnz     short loc_18001C3A0
0x18001c395  mov     dword ptr [rsi], 800401F0h
0x18001c39b  jmp     loc_18001C51F
0x18001c3a0  mov     [rbp+var_48], 0
0x18001c3a8  lea     rcx, [rbp+var_48]
0x18001c3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3b1  mov     r8, r14
0x18001c3b4  mov     rdx, rdi
0x18001c3b7  mov     rcx, [r15]
0x18001c3ba  call    RoGetActivationFactory_0
0x18001c3bf  mov     ebx, eax
0x18001c3c1  test    ebx, ebx
0x18001c3c3  jnz     short loc_18001C3CC
0x18001c3c5  mov     [rsi], ebx
0x18001c3c7  jmp     loc_18001C51F
0x18001c3cc  mov     [rbp+pperrinfo], 0
0x18001c3d4  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18001c3d8  xor     ecx, ecx; dwReserved
0x18001c3da  call    GetErrorInfo_0
0x18001c3df  mov     rdx, r15
0x18001c3e2  lea     rcx, [rbp+lpLibFileName]
0x18001c3e6  call    ??$?0Uhstring@winrt@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBUhstring@winrt@@AEBV?$allocator@G@1@@Z; std::wstring::wstring(winrt::hstring const &,std::allocator<ushort> const &)
0x18001c3eb  jmp     loc_18001C4C3
0x18001c3f0  mov     rdx, rax
0x18001c3f3  lea     rcx, [rbp+lpLibFileName]
0x18001c3f7  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001c3fc  mov     r8, [rbp+var_28]
0x18001c400  mov     rax, [rbp+var_20]
0x18001c404  sub     rax, r8
0x18001c407  lea     rcx, [rbp+lpLibFileName]; Src
0x18001c40b  cmp     rax, 4
0x18001c40f  jb      short loc_18001C434
0x18001c411  lea     rdx, [r8+4]
0x18001c415  mov     [rbp+var_28], rdx
0x18001c419  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEAAPEAGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c41e  mov     rcx, 6C006C0064002Eh
0x18001c428  mov     [rax+r8*2], rcx
0x18001c42c  xor     ecx, ecx
0x18001c42e  mov     [rax+rdx*2], cx
0x18001c432  jmp     short loc_18001C447
0x18001c434  mov     [rsp+78h+var_58], 4; __int64
0x18001c43d  mov     edx, 4
0x18001c442  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18001c447  lea     rcx, [rbp+lpLibFileName]
0x18001c44b  cmp     [rbp+var_20], 7
0x18001c450  cmova   rcx, [rbp+lpLibFileName]; lpLibFileName
0x18001c455  xor     edx, edx; hFile
0x18001c457  mov     r8d, 1000h; dwFlags
0x18001c45d  call    LoadLibraryExW_0
0x18001c462  mov     rdi, rax
0x18001c465  mov     rdx, [rbp+var_28]
0x18001c469  add     rdx, 0FFFFFFFFFFFFFFFCh
0x18001c46d  lea     rcx, [rbp+lpLibFileName]
0x18001c471  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001c476  test    rdi, rdi
0x18001c479  jz      short loc_18001C4C3
0x18001c47b  lea     rdx, aDllgetactivati_0; "DllGetActivationFactory"
0x18001c482  mov     rcx, rdi; hModule
0x18001c485  call    WINRT_IMPL_GetProcAddress
0x18001c48a  test    rax, rax
0x18001c48d  jz      short loc_18001C4BB
0x18001c48f  mov     [rbp+var_48], 0
0x18001c497  lea     rdx, [rbp+var_48]
0x18001c49b  mov     rcx, [r15]
0x18001c49e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4a3  test    eax, eax
0x18001c4a5  jz      loc_18001C53B
0x18001c4ab  cmp     [rbp+var_48], 0
0x18001c4b0  jz      short loc_18001C4BB
0x18001c4b2  lea     rcx, [rbp+var_48]
0x18001c4b6  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001c4bb  mov     rcx, rdi; hLibModule
0x18001c4be  call    WINRT_IMPL_FreeLibrary
0x18001c4c3  lea     rcx, [rbp+lpLibFileName]
0x18001c4c7  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::rfind(ushort,unsigned __int64)
0x18001c4cc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c4d0  jnz     loc_18001C3F0
0x18001c4d6  mov     rdx, [rbp+pperrinfo]; perrinfo
0x18001c4da  xor     ecx, ecx; dwReserved
0x18001c4dc  call    SetErrorInfo_0
0x18001c4e1  mov     [rsi], ebx
0x18001c4e3  mov     rdx, [rbp+var_20]
0x18001c4e7  cmp     rdx, 7
0x18001c4eb  jbe     short loc_18001C4FE
0x18001c4ed  lea     rdx, ds:2[rdx*2]
0x18001c4f5  mov     rcx, [rbp+lpLibFileName]
0x18001c4f9  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c4fe  xor     eax, eax
0x18001c500  cmp     [rbp+pperrinfo], rax
0x18001c504  mov     word ptr [rbp+lpLibFileName], ax
0x18001c508  mov     [rbp+var_20], 7
0x18001c510  mov     [rbp+var_28], rax
0x18001c514  jz      short loc_18001C51F
0x18001c516  lea     rcx, [rbp+pperrinfo]
0x18001c51a  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18001c51f  mov     rax, rsi
0x18001c522  mov     rcx, [rbp+var_18]
0x18001c526  xor     rcx, rsp; StackCookie
0x18001c529  call    __security_check_cookie
0x18001c52e  add     rsp, 78h
0x18001c532  pop     r15
0x18001c534  pop     r14
0x18001c536  pop     rdi
0x18001c537  pop     rsi
0x18001c538  pop     rbx
0x18001c539  pop     rbp
0x18001c53a  retn
0x18001c53b  mov     rax, [rbp+var_48]
0x18001c53f  mov     [rbp+var_48], 0
0x18001c547  mov     [r14], rax
0x18001c54a  mov     dword ptr [rsi], 0
0x18001c550  jmp     short loc_18001C4E3
```
