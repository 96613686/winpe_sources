# wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *,tagCOWAIT_FLAGS,ulong,bool *)

- ea: `0x1800148a0`
- end: `0x1800149e1`
- name: `??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z`
- size: `321`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180015880`

## callees

- `0x180004dcc`
- `0x1800058a4`
- `0x180014298`
- `0x1800148a0`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180014945`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180014945`

## string_xrefs

- `0x180014907`: `onecore\internal\sdk\inc\wil\opensource\wil\winrt.h`

## pseudocode

```c
__int64 __fastcall wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>(
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
  v4 = ___MakeAndInitialize_VCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAUIPropertySet_Collections_Foundation_Windows_ABI___Foundation_Windows_ABI___details_wil__YAJPEAU__IAsyncOperation_PEAUIPropertySet_Collections_Foundation_Windows_ABI___Foundation_Windows_ABI__W4tagCOWAIT_FLAGS__KPEA_N_Z_V1_1____WaitForCompletion_PEAU__IAsyncOperation_PEAUIPropertySet_Collections_Foundation_Windows_ABI___Foundation_Windows_ABI___23_YAJ01K2_Z___V_Details_WRL_Microsoft__YAJPEAPEAVCompletionDelegate__1____WaitForCompletion_PEAU__IAsyncOperation_PEAUIPropertySet_Collections_Foundation_Windows_ABI___Foundation_Windows_ABI___details_wil__YAJPEAU__IAsyncOperation_PEAUIPropertySet_Collections_Foundation_Windows_ABI___Foundation_Windows_ABI__W4tagCOWAIT_FLAGS__KPEA_N_Z__Z(&v15);
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
0x1800148a0  mov     [rsp-18h+arg_18], r9
0x1800148a5  mov     [rsp-18h+arg_10], r8d
0x1800148aa  mov     [rsp-18h+dwindex], edx
0x1800148ae  push    rbp
0x1800148af  push    rbx
0x1800148b0  push    rdi
0x1800148b1  mov     rbp, rsp
0x1800148b4  sub     rsp, 40h
0x1800148b8  mov     rdi, rcx
0x1800148bb  mov     [rbp+arg_18], 0
0x1800148c3  lea     rcx, [rbp+arg_18]
0x1800148c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800148cc  lea     rcx, [rbp+arg_18]
0x1800148d0  call    ??$MakeAndInitialize@VCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@V1?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@23@YAJ01K2@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVCompletionDelegate@?1???$WaitForCompletion@PEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@W4tagCOWAIT_FLAGS@@KPEA_N@Z@@Z; Microsoft::WRL::Details::MakeAndInitialize<`wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,`wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate,>(`wil::details::WaitForCompletion<ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *>(ABI::Windows::Foundation::IAsyncOperation<ABI::Windows::Foundation::Collections::IPropertySet *> *,tagCOWAIT_FLAGS,ulong,bool *)'::`2'::CompletionDelegate * *)
0x1800148d5  mov     ebx, eax
0x1800148d7  test    eax, eax
0x1800148d9  jns     short loc_1800148E2
0x1800148db  mov     edx, 648h
0x1800148e0  jmp     short loc_180014900
0x1800148e2  mov     rax, [rdi]
0x1800148e5  mov     rdx, [rbp+arg_18]
0x1800148e9  mov     rcx, rdi
0x1800148ec  mov     rax, [rax+30h]
0x1800148f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148f5  mov     ebx, eax
0x1800148f7  test    eax, eax
0x1800148f9  jns     short loc_180014918
0x1800148fb  mov     edx, 649h; void *
0x180014900  mov     rcx, [rbp+18h]; this
0x180014904  mov     r9d, eax; char *
0x180014907  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001490e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014913  jmp     loc_1800149CD
0x180014918  mov     rax, [rbp+arg_18]
0x18001491c  mov     rcx, [rax+38h]
0x180014920  mov     [rbp+pHandles], rcx
0x180014924  mov     [rbp+dwindex], 0
0x18001492b  lea     rax, [rbp+dwindex]
0x18001492f  mov     qword ptr [rsp+40h+lpdwindex], rax; lpdwindex
0x180014934  lea     r9, [rbp+pHandles]; pHandles
0x180014938  mov     r8d, 1; cHandles
0x18001493e  or      edx, 0FFFFFFFFh; dwTimeout
0x180014941  lea     ecx, [r8+7]; dwFlags
0x180014945  call    cs:__imp_CoWaitForMultipleHandles
0x18001494c  nop     dword ptr [rax+rax+00h]
0x180014951  mov     ebx, eax
0x180014953  test    eax, eax
0x180014955  jns     short loc_18001495E
0x180014957  mov     edx, 655h
0x18001495c  jmp     short loc_180014900
0x18001495e  mov     rax, [rbp+arg_18]
0x180014962  mov     ecx, [rax+30h]
0x180014965  cmp     ecx, 1
0x180014968  jz      short loc_1800149CB
0x18001496a  mov     [rbp+var_10], 0
0x180014972  mov     rax, [rdi]
0x180014975  mov     rbx, [rax]
0x180014978  lea     rcx, [rbp+var_10]
0x18001497c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014981  lea     r8, [rbp+var_10]
0x180014985  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x18001498c  mov     rcx, rdi
0x18001498f  mov     rax, rbx
0x180014992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014997  mov     ebx, eax
0x180014999  test    eax, eax
0x18001499b  js      short loc_1800149C0
0x18001499d  mov     [rbp+arg_10], 8000FFFFh
0x1800149a4  mov     rcx, [rbp+var_10]
0x1800149a8  mov     rax, [rcx]
0x1800149ab  lea     rdx, [rbp+arg_10]
0x1800149af  mov     rax, [rax+40h]
0x1800149b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149b8  mov     ebx, eax
0x1800149ba  test    eax, eax
0x1800149bc  cmovns  ebx, [rbp+arg_10]
0x1800149c0  lea     rcx, [rbp+var_10]
0x1800149c4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800149c9  jmp     short loc_1800149CD
0x1800149cb  xor     ebx, ebx
0x1800149cd  lea     rcx, [rbp+arg_18]
0x1800149d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800149d6  mov     eax, ebx
0x1800149d8  add     rsp, 40h
0x1800149dc  pop     rdi
0x1800149dd  pop     rbx
0x1800149de  pop     rbp
0x1800149df  retn
```
