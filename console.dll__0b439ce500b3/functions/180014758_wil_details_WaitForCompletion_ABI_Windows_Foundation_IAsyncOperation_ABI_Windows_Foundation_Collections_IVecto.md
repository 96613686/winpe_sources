# wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x180014758`
- end: `0x180014899`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015880`

## callees

- `0x180004dcc`
- `0x1800058a4`
- `0x180014164`
- `0x180014758`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800147fd`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x1800147fd`

## string_xrefs

- `0x1800147bf`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        DWORD a2,
        int a3)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rdx
  __int64 (__fastcall *v7)(_QWORD, GUID *, __int64 *); // rbx
  int lpdwindex; // [rsp+20h] [rbp-20h]
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  HANDLE pHandles; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD dwindex; // [rsp+68h] [rbp+28h] BYREF
  int v14; // [rsp+70h] [rbp+30h] BYREF
  __int64 v15; // [rsp+78h] [rbp+38h] BYREF

  v14 = a3;
  dwindex = a2;
  v15 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  v4 = ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppExtension_AppExtensions_ApplicationModel_Windows_ABI___Collections_Foundation_Windows_ABI___Foundation_Windows_ABI___details_wil__YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppExtension_AppExtensions_ApplicationModel_Windows_ABI___Collections_Foundation_Windows_ABI___Foundation_Windows_ABI__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppExtension_AppExtensions_ApplicationModel_Windows_ABI___Collections_Foundation_Windows_ABI___Foundation_Windows_ABI___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppExtension_AppExtensions_ApplicationModel_Windows_ABI___Collections_Foundation_Windows_ABI___Foundation_Windows_ABI___details_wil__YAJPEAU__IAsyncOperation_PEAU__IVectorView_PEAVAppExtension_AppExtensions_ApplicationModel_Windows_ABI___Collections_Foundation_Windows_ABI___Foundation_Windows_ABI__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(&v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1608;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\winrt.h",
      (const char *)(unsigned int)v4,
      lpdwindex);
    goto LABEL_14;
  }
  v4 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*a1)[6])(a1, v15);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1609;
    goto LABEL_5;
  }
  pHandles = *(HANDLE *)(v15 + 56);
  dwindex = 0;
  v4 = CoWaitForMultipleHandles(8u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
  v5 = v4;
  if ( v4 < 0 )
  {
    v6 = 1621;
    goto LABEL_5;
  }
  if ( *(_DWORD *)(v15 + 48) == 1 )
  {
    v5 = 0;
  }
  else
  {
    v10 = 0;
    v7 = **a1;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
    v5 = v7(a1, &GUID_00000036_0000_0000_c000_000000000046, &v10);
    if ( v5 >= 0 )
    {
      v14 = -2147418113;
      v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 64LL))(v10, &v14);
      if ( v5 >= 0 )
        v5 = v14;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  }
LABEL_14:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180014758  mov     [rsp-18h+arg_18], r9
0x18001475d  mov     [rsp-18h+arg_10], r8d
0x180014762  mov     [rsp-18h+dwindex], edx
0x180014766  push    rbp
0x180014767  push    rbx
0x180014768  push    rdi
0x180014769  mov     rbp, rsp
0x18001476c  sub     rsp, 40h
0x180014770  mov     rdi, rcx
0x180014773  mov     [rbp+arg_18], 0
0x18001477b  lea     rcx, [rbp+arg_18]
0x18001477f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014784  lea     rcx, [rbp+arg_18]
0x180014788  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x18001478d  mov     ebx, eax
0x18001478f  test    eax, eax
0x180014791  jns     short loc_18001479A
0x180014793  mov     edx, 648h
0x180014798  jmp     short loc_1800147B8
0x18001479a  mov     rax, [rdi]
0x18001479d  mov     rdx, [rbp+arg_18]
0x1800147a1  mov     rcx, rdi
0x1800147a4  mov     rax, [rax+30h]
0x1800147a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800147ad  mov     ebx, eax
0x1800147af  test    eax, eax
0x1800147b1  jns     short loc_1800147D0
0x1800147b3  mov     edx, 649h; void *
0x1800147b8  mov     rcx, [rbp+18h]; this
0x1800147bc  mov     r9d, eax; char *
0x1800147bf  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800147c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800147cb  jmp     loc_180014885
0x1800147d0  mov     rax, [rbp+arg_18]
0x1800147d4  mov     rcx, [rax+38h]
0x1800147d8  mov     [rbp+pHandles], rcx
0x1800147dc  mov     [rbp+dwindex], 0
0x1800147e3  lea     rax, [rbp+dwindex]
0x1800147e7  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x1800147ec  lea     r9, [rbp+pHandles]; pHandles
0x1800147f0  mov     r8d, 1; cHandles
0x1800147f6  or      edx, 0FFFFFFFFh; dwTimeout
0x1800147f9  lea     ecx, [r8+7]; dwFlags
0x1800147fd  call    cs:__imp_CoWaitForMultipleHandles
0x180014804  nop     dword ptr [rax+rax+00h]
0x180014809  mov     ebx, eax
0x18001480b  test    eax, eax
0x18001480d  jns     short loc_180014816
0x18001480f  mov     edx, 655h
0x180014814  jmp     short loc_1800147B8
0x180014816  mov     rax, [rbp+arg_18]
0x18001481a  mov     ecx, [rax+30h]
0x18001481d  cmp     ecx, 1
0x180014820  jz      short loc_180014883
0x180014822  mov     [rbp+var_10], 0
0x18001482a  mov     rax, [rdi]
0x18001482d  mov     rbx, [rax]
0x180014830  lea     rcx, [rbp+var_10]
0x180014834  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014839  lea     r8, [rbp+var_10]
0x18001483d  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180014844  mov     rcx, rdi
0x180014847  mov     rax, rbx
0x18001484a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001484f  mov     ebx, eax
0x180014851  test    eax, eax
0x180014853  js      short loc_180014878
0x180014855  mov     [rbp+arg_10], 8000FFFFh
0x18001485c  mov     rcx, [rbp+var_10]
0x180014860  mov     rax, [rcx]
0x180014863  lea     rdx, [rbp+arg_10]
0x180014867  mov     rax, [rax+40h]
0x18001486b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014870  mov     ebx, eax
0x180014872  test    eax, eax
0x180014874  cmovns  ebx, [rbp+arg_10]
0x180014878  lea     rcx, [rbp+var_10]
0x18001487c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014881  jmp     short loc_180014885
0x180014883  xor     ebx, ebx
0x180014885  lea     rcx, [rbp+arg_18]
0x180014889  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001488e  mov     eax, ebx
0x180014890  add     rsp, 40h
0x180014894  pop     rdi
0x180014895  pop     rbx
0x180014896  pop     rbp
0x180014897  retn
```
