# CDXGIOutputDuplicationTonemapper::CDXGIOutputDuplicationTonemapper(CDXGIOutput *,DXGI_OUTPUT_DESC1,ATL::CComPtr<IDXGIDevice> const &)

- ea: `0x18008002c`
- end: `0x1800805e9`
- name: `??0CDXGIOutputDuplicationTonemapper@@QEAA@PEAVCDXGIOutput@@UDXGI_OUTPUT_DESC1@@AEBV?$CComPtr@UIDXGIDevice@@@ATL@@@Z`
- size: `1469`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007f55c`

## callees

- `0x180010d40`
- `0x180014750`
- `0x18003ba90`
- `0x180060320`
- `0x180069078`
- `0x18006e284`
- `0x18006e2d0`
- `0x180075fa0`
- `0x18008002c`
- `0x180080e04`
- `0x180080ebc`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800801a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800801a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800801b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800801b7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18008016b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18008016b`

## string_xrefs

- `0x180080164`: `d2d1.dll`
- `0x18008019b`: `D2D1CreateFactory`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CDXGIOutputDuplicationTonemapper::CDXGIOutputDuplicationTonemapper(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  _QWORD *v5; // r15
  ID2D1Effect **v6; // r13
  ID2D1Effect **v7; // r12
  HMODULE *v8; // rdi
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  signed int v12; // eax
  __int64 v13; // rax
  struct wil::details::wnf_subscription_state_base *v14; // rdx
  __int64 v15; // rax
  struct wil::details::wnf_subscription_state_base *v16; // rdx
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rcx
  int v27; // eax
  int v28; // eax
  ID2D1Effect *v29; // rcx
  int v30; // eax
  ID2D1Effect *v31; // rcx
  int v32; // eax
  unsigned int v33; // edx
  int v34; // r9d
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  ID2D1Effect *v40; // rcx
  int v41; // eax
  ID2D1Effect *v42; // rcx
  int v43; // eax
  unsigned int v44; // edx
  int v45; // r9d
  wil::details *v47; // [rsp+30h] [rbp-89h] BYREF
  __int64 (__fastcall ***v48)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-81h] BYREF
  __int64 v49; // [rsp+40h] [rbp-79h] BYREF
  __int64 v50; // [rsp+48h] [rbp-71h] BYREF
  _QWORD *v51; // [rsp+50h] [rbp-69h]
  __int64 v52; // [rsp+58h] [rbp-61h]
  _BYTE v53[8]; // [rsp+60h] [rbp-59h] BYREF
  __int64 (__fastcall **v54)(); // [rsp+68h] [rbp-51h] BYREF
  __int64 v55; // [rsp+70h] [rbp-49h]
  __int64 (__fastcall ***v56)(); // [rsp+D0h] [rbp+17h]

  v51 = a4;
  v52 = a1;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 2;
  *(_OWORD *)(a1 + 48) = 0;
  *(_OWORD *)(a1 + 64) = 0;
  *(_OWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_DWORD *)(a1 + 96) = -1;
  *(_DWORD *)(a1 + 100) = 0;
  *(_DWORD *)(a1 + 104) = 1117782016;
  *(_QWORD *)(a1 + 264) = 0;
  v5 = (_QWORD *)(a1 + 272);
  *(_QWORD *)(a1 + 272) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  v6 = (ID2D1Effect **)(a1 + 288);
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = 0;
  v7 = (ID2D1Effect **)(a1 + 304);
  *(_QWORD *)(a1 + 304) = 0;
  *(_QWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 320) = 0;
  v8 = (HMODULE *)(a1 + 328);
  *(_QWORD *)(a1 + 328) = 0;
  *(_QWORD *)a1 = a2;
  *(_OWORD *)(a1 + 112) = *(_OWORD *)a3;
  *(_OWORD *)(a1 + 128) = *(_OWORD *)(a3 + 16);
  *(_OWORD *)(a1 + 144) = *(_OWORD *)(a3 + 32);
  *(_OWORD *)(a1 + 160) = *(_OWORD *)(a3 + 48);
  *(_OWORD *)(a1 + 176) = *(_OWORD *)(a3 + 64);
  *(_OWORD *)(a1 + 192) = *(_OWORD *)(a3 + 80);
  *(_OWORD *)(a1 + 208) = *(_OWORD *)(a3 + 96);
  *(_OWORD *)(a1 + 224) = *(_OWORD *)(a3 + 112);
  *(_OWORD *)(a1 + 240) = *(_OWORD *)(a3 + 128);
  *(_QWORD *)(a1 + 256) = *(_QWORD *)(a3 + 144);
  LibraryW = LoadLibraryW(L"d2d1.dll");
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    v8,
    LibraryW);
  if ( !*v8 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    DXGIThrowFailure(LastError);
  }
  ProcAddress = GetProcAddress(*v8, "D2D1CreateFactory");
  *(_QWORD *)(a1 + 336) = ProcAddress;
  if ( !ProcAddress )
  {
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    DXGIThrowFailure(v12);
  }
  v54 = off_1800D1790;
  v55 = a1;
  v56 = &v54;
  v13 = wil::make_wnf_subscription_nothrow<wil::details::empty_wnf_state>(&v47, &WNF_DX_SDR_WHITE_LEVEL_CHANGED, v53);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    a1 + 8,
    v13);
  if ( v47 )
    wil::details::delete_wnf_subscription_state(v47, v14);
  wistd::function<void (AUTOHDR_STRENGTH_WNF const &)>::~function<void (AUTOHDR_STRENGTH_WNF const &)>(v53);
  v54 = off_1800D1768;
  v55 = a1;
  v56 = &v54;
  v15 = wil::make_wnf_subscription_nothrow<wil::details::empty_wnf_state>(
          &v47,
          &WNF_DX_DISPLAY_COLORIMETRY_DATA_CHANGED,
          v53);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    a1 + 16,
    v15);
  if ( v47 )
    wil::details::delete_wnf_subscription_state(v47, v16);
  wistd::function<void (AUTOHDR_STRENGTH_WNF const &)>::~function<void (AUTOHDR_STRENGTH_WNF const &)>(v53);
  v50 = 0;
  v17 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v51)(
          *v51,
          &GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c,
          &v50);
  DXGIThrowFailure(v17);
  v18 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD, __int64))(a1 + 336))(
          0,
          &GUID_bdc2bdd3_b96c_4de6_bdf7_99d4745454de,
          0,
          a1 + 264);
  DXGIThrowFailure(v18);
  v49 = 0;
  v19 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a1 + 264))(
          *(_QWORD *)(a1 + 264),
          &GUID_6f72c0a2_6db7_46e9_9b62_b58a23f4928b,
          &v49);
  DXGIThrowFailure(v19);
  v48 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v49 + 120LL))(
          v49,
          8,
          v50,
          &v48);
  DXGIThrowFailure(v20);
  v21 = (**v48)(v48, &GUID_7bfef914_2d75_4bad_be87_e18ddb077b6d, a1 + 280);
  DXGIThrowFailure(v21);
  v22 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD *))(**(_QWORD **)(a1 + 280) + 160LL))(
          *(_QWORD *)(a1 + 280),
          0,
          v5);
  DXGIThrowFailure(v22);
  v23 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64))(*(_QWORD *)*v5 + 504LL))(
          *v5,
          &CLSID_D2D1WhiteLevelAdjustment,
          a1 + 296);
  DXGIThrowFailure(v23);
  v24 = *(_QWORD *)(a1 + 296);
  LODWORD(v47) = 1117782016;
  v25 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, wil::details **, int))(*(_QWORD *)v24 + 72LL))(
          v24,
          1,
          0,
          &v47,
          4);
  DXGIThrowFailure(v25);
  v26 = *(_QWORD *)(a1 + 296);
  LODWORD(v47) = 1117782016;
  v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, wil::details **, int))(*(_QWORD *)v26 + 72LL))(
          v26,
          0,
          0,
          &v47,
          4);
  DXGIThrowFailure(v27);
  v28 = (*(__int64 (__fastcall **)(_QWORD, GUID *, ID2D1Effect **))(*(_QWORD *)*v5 + 504LL))(
          *v5,
          &CLSID_D2D1HdrToneMap,
          v6);
  DXGIThrowFailure(v28);
  v29 = *v6;
  LODWORD(v47) = 1117782016;
  v30 = (*(__int64 (__fastcall **)(ID2D1Effect *, __int64, _QWORD, wil::details **, int))(*(_QWORD *)v29 + 72LL))(
          v29,
          1,
          0,
          &v47,
          4);
  DXGIThrowFailure(v30);
  v31 = *v6;
  LODWORD(v47) = 0;
  v32 = (*(__int64 (__fastcall **)(ID2D1Effect *, __int64, _QWORD, wil::details **, int))(*(_QWORD *)v31 + 72LL))(
          v31,
          2,
          0,
          &v47,
          4);
  DXGIThrowFailure(v32);
  ID2D1Effect::SetInputEffect(*v6, v33, *(struct ID2D1Effect **)(a1 + 296), v34);
  v35 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v5 + 936LL))(*v5, 1, a1 + 312);
  DXGIThrowFailure(v35);
  v36 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*v5 + 936LL))(*v5, 0, a1 + 320);
  DXGIThrowFailure(v36);
  v37 = (*(__int64 (__fastcall **)(_QWORD, GUID *, ID2D1Effect **))(*(_QWORD *)*v5 + 504LL))(
          *v5,
          &CLSID_D2D1ColorManagement,
          v7);
  DXGIThrowFailure(v37);
  v38 = (*(__int64 (__fastcall **)(ID2D1Effect *, __int64, _QWORD, __int64, int))(*(_QWORD *)*v7 + 72LL))(
          *v7,
          2,
          0,
          a1 + 320,
          8);
  DXGIThrowFailure(v38);
  v39 = (*(__int64 (__fastcall **)(ID2D1Effect *, _QWORD, _QWORD, __int64, int))(*(_QWORD *)*v7 + 72LL))(
          *v7,
          0,
          0,
          a1 + 312,
          8);
  DXGIThrowFailure(v39);
  v40 = *v7;
  LODWORD(v47) = 2;
  v41 = (*(__int64 (__fastcall **)(ID2D1Effect *, __int64, _QWORD, wil::details **, int))(*(_QWORD *)v40 + 72LL))(
          v40,
          5,
          0,
          &v47,
          4);
  DXGIThrowFailure(v41);
  v42 = *v7;
  LODWORD(v47) = 3;
  v43 = (*(__int64 (__fastcall **)(ID2D1Effect *, __int64, _QWORD, wil::details **, int))(*(_QWORD *)v42 + 72LL))(
          v42,
          3,
          0,
          &v47,
          4);
  DXGIThrowFailure(v43);
  ID2D1Effect::SetInputEffect(*v7, v44, *v6, v45);
  ATL::CComPtrBase<ID2D1Effect>::~CComPtrBase<ID2D1Effect>(&v48);
  ATL::CComPtrBase<ID2D1Effect>::~CComPtrBase<ID2D1Effect>(&v49);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
  return a1;
}

```

## disassembly

```asm
0x18008002c  mov     [rsp-8+arg_8], rbx
0x180080031  push    rbp
0x180080032  push    rsi
0x180080033  push    rdi
0x180080034  push    r12
0x180080036  push    r13
0x180080038  push    r14
0x18008003a  push    r15
0x18008003c  lea     rbp, [rsp-27h]
0x180080041  sub     rsp, 0E0h
0x180080048  mov     rax, cs:__security_cookie
0x18008004f  xor     rax, rsp
0x180080052  mov     [rbp+57h+var_38], rax
0x180080056  mov     [rbp+57h+var_C0], r9
0x18008005a  mov     rbx, rcx
0x18008005d  mov     [rbp+57h+var_B8], rcx
0x180080061  xor     ecx, ecx
0x180080063  mov     [rbx+8], rcx
0x180080067  mov     [rbx+10h], rcx
0x18008006b  mov     qword ptr [rbx+18h], 2
0x180080073  xorps   xmm0, xmm0
0x180080076  movups  xmmword ptr [rbx+30h], xmm0
0x18008007a  movups  xmmword ptr [rbx+40h], xmm0
0x18008007e  movups  xmmword ptr [rbx+50h], xmm0
0x180080082  mov     [rbx+20h], rcx
0x180080086  mov     [rbx+28h], rcx
0x18008008a  mov     dword ptr [rbx+60h], 0FFFFFFFFh
0x180080091  mov     [rbx+64h], ecx
0x180080094  mov     dword ptr [rbx+68h], 42A00000h
0x18008009b  mov     [rbx+108h], rcx
0x1800800a2  lea     r15, [rbx+110h]
0x1800800a9  mov     [r15], rcx
0x1800800ac  mov     [rbx+118h], rcx
0x1800800b3  lea     r13, [rbx+120h]
0x1800800ba  mov     [r13+0], rcx
0x1800800be  mov     [rbx+128h], rcx
0x1800800c5  lea     r12, [rbx+130h]
0x1800800cc  mov     [r12], rcx
0x1800800d0  mov     [rbx+138h], rcx
0x1800800d7  mov     [rbx+140h], rcx
0x1800800de  lea     rdi, [rbx+148h]
0x1800800e5  mov     [rdi], rcx
0x1800800e8  mov     [rbx], rdx
0x1800800eb  movups  xmm0, xmmword ptr [r8]
0x1800800ef  movups  xmmword ptr [rbx+70h], xmm0
0x1800800f3  movups  xmm1, xmmword ptr [r8+10h]
0x1800800f8  movups  xmmword ptr [rbx+80h], xmm1
0x1800800ff  movups  xmm0, xmmword ptr [r8+20h]
0x180080104  movups  xmmword ptr [rbx+90h], xmm0
0x18008010b  movups  xmm1, xmmword ptr [r8+30h]
0x180080110  movups  xmmword ptr [rbx+0A0h], xmm1
0x180080117  movups  xmm0, xmmword ptr [r8+40h]
0x18008011c  movups  xmmword ptr [rbx+0B0h], xmm0
0x180080123  movups  xmm1, xmmword ptr [r8+50h]
0x180080128  movups  xmmword ptr [rbx+0C0h], xmm1
0x18008012f  movups  xmm0, xmmword ptr [r8+60h]
0x180080134  movups  xmmword ptr [rbx+0D0h], xmm0
0x18008013b  movups  xmm1, xmmword ptr [r8+70h]
0x180080140  movups  xmmword ptr [rbx+0E0h], xmm1
0x180080147  movups  xmm0, xmmword ptr [r8+80h]
0x18008014f  movups  xmmword ptr [rbx+0F0h], xmm0
0x180080156  mov     rax, [r8+90h]
0x18008015d  mov     [rbx+100h], rax
0x180080164  lea     rcx, aD2d1Dll; "d2d1.dll"
0x18008016b  call    cs:__imp_LoadLibraryW
0x180080171  mov     rdx, rax
0x180080174  mov     rcx, rdi
0x180080177  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18008017c  cmp     qword ptr [rdi], 0
0x180080180  jnz     short loc_18008019B
0x180080182  call    cs:__imp_GetLastError
0x180080188  test    eax, eax
0x18008018a  jle     short loc_180080194
0x18008018c  movzx   eax, ax
0x18008018f  or      eax, 80070000h
0x180080194  mov     ecx, eax; int
0x180080196  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x18008019b  lea     rdx, aD2d1createfact; "D2D1CreateFactory"
0x1800801a2  mov     rcx, [rdi]; hModule
0x1800801a5  call    cs:__imp_GetProcAddress
0x1800801ab  mov     [rbx+150h], rax
0x1800801b2  test    rax, rax
0x1800801b5  jnz     short loc_1800801D0
0x1800801b7  call    cs:__imp_GetLastError
0x1800801bd  test    eax, eax
0x1800801bf  jle     short loc_1800801C9
0x1800801c1  movzx   eax, ax
0x1800801c4  or      eax, 80070000h
0x1800801c9  mov     ecx, eax; int
0x1800801cb  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x1800801d0  lea     rax, off_1800D1790
0x1800801d7  mov     [rbp+57h+var_A8], rax
0x1800801db  mov     [rbp+57h+var_A0], rbx
0x1800801df  lea     rax, [rbp+57h+var_A8]
0x1800801e3  mov     [rbp+57h+var_40], rax
0x1800801e7  lea     r8, [rbp+57h+var_B0]
0x1800801eb  lea     rdx, WNF_DX_SDR_WHITE_LEVEL_CHANGED
0x1800801f2  lea     rcx, [rsp+110h+var_E0]
0x1800801f7  call    ??$make_wnf_subscription_nothrow@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription_nothrow<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x1800801fc  mov     rdx, rax
0x1800801ff  lea     rcx, [rbx+8]
0x180080203  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x180080208  mov     rcx, [rsp+110h+var_E0]; this
0x18008020d  test    rcx, rcx
0x180080210  jz      short loc_180080217
0x180080212  call    ?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z; wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)
0x180080217  lea     rcx, [rbp+57h+var_B0]
0x18008021b  call    ??1?$function@$$A6AXAEBUAUTOHDR_STRENGTH_WNF@@@Z@wistd@@QEAA@XZ; wistd::function<void (AUTOHDR_STRENGTH_WNF const &)>::~function<void (AUTOHDR_STRENGTH_WNF const &)>(void)
0x180080220  lea     rax, off_1800D1768
0x180080227  mov     [rbp+57h+var_A8], rax
0x18008022b  mov     [rbp+57h+var_A0], rbx
0x18008022f  lea     rax, [rbp+57h+var_A8]
0x180080233  mov     [rbp+57h+var_40], rax
0x180080237  lea     r8, [rbp+57h+var_B0]
0x18008023b  lea     rdx, WNF_DX_DISPLAY_COLORIMETRY_DATA_CHANGED
0x180080242  lea     rcx, [rsp+110h+var_E0]
0x180080247  call    ??$make_wnf_subscription_nothrow@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription_nothrow<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x18008024c  mov     rdx, rax
0x18008024f  lea     rcx, [rbx+10h]
0x180080253  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x180080258  mov     rcx, [rsp+110h+var_E0]; this
0x18008025d  test    rcx, rcx
0x180080260  jz      short loc_180080267
0x180080262  call    ?delete_wnf_subscription_state@details@wil@@YAXPEAUwnf_subscription_state_base@12@@Z; wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *)
0x180080267  lea     rcx, [rbp+57h+var_B0]
0x18008026b  call    ??1?$function@$$A6AXAEBUAUTOHDR_STRENGTH_WNF@@@Z@wistd@@QEAA@XZ; wistd::function<void (AUTOHDR_STRENGTH_WNF const &)>::~function<void (AUTOHDR_STRENGTH_WNF const &)>(void)
0x180080270  mov     [rbp+57h+var_C8], 0
0x180080278  mov     rcx, [rbp+57h+var_C0]
0x18008027c  mov     rcx, [rcx]
0x18008027f  mov     rax, [rcx]
0x180080282  lea     r8, [rbp+57h+var_C8]
0x180080286  lea     rdx, _GUID_54ec77fa_1377_44e6_8c32_88fd5f44c84c
0x18008028d  mov     rax, [rax]
0x180080290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080295  nop
0x180080296  mov     ecx, eax; int
0x180080298  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x18008029d  lea     rdi, [rbx+108h]
0x1800802a4  mov     r9, rdi
0x1800802a7  xor     r8d, r8d
0x1800802aa  lea     rdx, _GUID_bdc2bdd3_b96c_4de6_bdf7_99d4745454de
0x1800802b1  xor     ecx, ecx
0x1800802b3  mov     rax, [rbx+150h]
0x1800802ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800802bf  mov     ecx, eax; int
0x1800802c1  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x1800802c6  mov     [rbp+57h+var_D0], 0
0x1800802ce  mov     rcx, [rdi]
0x1800802d1  mov     rax, [rcx]
0x1800802d4  lea     r8, [rbp+57h+var_D0]
0x1800802d8  lea     rdx, _GUID_6f72c0a2_6db7_46e9_9b62_b58a23f4928b
0x1800802df  mov     rax, [rax]
0x1800802e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800802e7  nop
0x1800802e8  mov     ecx, eax; int
0x1800802ea  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x1800802ef  mov     [rsp+110h+var_D8], 0
0x1800802f8  mov     rcx, [rbp+57h+var_D0]
0x1800802fc  mov     rax, [rcx]
0x1800802ff  lea     r9, [rsp+110h+var_D8]
0x180080304  mov     r8, [rbp+57h+var_C8]
0x180080308  mov     edx, 8
0x18008030d  mov     rax, [rax+78h]
0x180080311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080316  mov     ecx, eax; int
0x180080318  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x18008031d  nop
0x18008031e  mov     rcx, [rsp+110h+var_D8]
0x180080323  mov     rax, [rcx]
0x180080326  lea     rdi, [rbx+118h]
0x18008032d  mov     r8, rdi
0x180080330  lea     rdx, _GUID_7bfef914_2d75_4bad_be87_e18ddb077b6d
0x180080337  mov     rax, [rax]
0x18008033a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008033f  nop
0x180080340  mov     ecx, eax; int
0x180080342  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x180080347  mov     rcx, [rdi]
0x18008034a  mov     rax, [rcx]
0x18008034d  mov     r8, r15
0x180080350  xor     edx, edx
0x180080352  mov     rax, [rax+0A0h]
0x180080359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008035e  mov     ecx, eax; int
0x180080360  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x180080365  mov     rcx, [r15]
0x180080368  mov     rax, [rcx]
0x18008036b  lea     rdi, [rbx+128h]
0x180080372  mov     r8, rdi
0x180080375  lea     rdx, CLSID_D2D1WhiteLevelAdjustment
0x18008037c  mov     rax, [rax+1F8h]
0x180080383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080388  mov     ecx, eax; int
0x18008038a  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x18008038f  mov     rcx, [rdi]
0x180080392  mov     dword ptr [rsp+110h+var_E0], 42A00000h
0x18008039a  mov     rax, [rcx]
0x18008039d  mov     r14d, 4
0x1800803a3  mov     [rsp+110h+var_F0], r14d
0x1800803a8  lea     r9, [rsp+110h+var_E0]
0x1800803ad  xor     r8d, r8d
0x1800803b0  lea     esi, [r14-3]
0x1800803b4  mov     edx, esi
0x1800803b6  mov     rax, [rax+48h]
0x1800803ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800803bf  mov     ecx, eax; int
0x1800803c1  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x1800803c6  mov     rcx, [rdi]
0x1800803c9  mov     dword ptr [rsp+110h+var_E0], 42A00000h
0x1800803d1  mov     rax, [rcx]
0x1800803d4  mov     [rsp+110h+var_F0], r14d
0x1800803d9  lea     r9, [rsp+110h+var_E0]
0x1800803de  xor     r8d, r8d
0x1800803e1  xor     edx, edx
0x1800803e3  mov     rax, [rax+48h]
0x1800803e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800803ec  mov     ecx, eax; int
0x1800803ee  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x1800803f3  mov     rcx, [r15]
0x1800803f6  mov     rax, [rcx]
0x1800803f9  mov     r8, r13
0x1800803fc  lea     rdx, CLSID_D2D1HdrToneMap
0x180080403  mov     rax, [rax+1F8h]
0x18008040a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008040f  mov     ecx, eax; int
0x180080411  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x180080416  mov     rcx, [r13+0]
0x18008041a  mov     dword ptr [rsp+110h+var_E0], 42A00000h
0x180080422  mov     rax, [rcx]
0x180080425  mov     [rsp+110h+var_F0], r14d
0x18008042a  lea     r9, [rsp+110h+var_E0]
0x18008042f  xor     r8d, r8d
0x180080432  mov     edx, esi
0x180080434  mov     rax, [rax+48h]
0x180080438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008043d  mov     ecx, eax; int
0x18008043f  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x180080444  mov     rcx, [r13+0]
0x180080448  mov     dword ptr [rsp+110h+var_E0], 0
0x180080450  mov     rax, [rcx]
0x180080453  mov     [rsp+110h+var_F0], r14d
0x180080458  lea     r9, [rsp+110h+var_E0]
0x18008045d  xor     r8d, r8d
0x180080460  lea     edx, [rsi+1]
0x180080463  mov     rax, [rax+48h]
0x180080467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008046c  mov     ecx, eax; int
0x18008046e  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x180080473  mov     r8, [rdi]; struct ID2D1Effect *
0x180080476  mov     rcx, [r13+0]; this
0x18008047a  call    ?SetInputEffect@ID2D1Effect@@QEAAXIPEAU1@H@Z; ID2D1Effect::SetInputEffect(uint,ID2D1Effect *,int)
0x18008047f  mov     rcx, [r15]
0x180080482  mov     rax, [rcx]
0x180080485  lea     rdi, [rbx+138h]
0x18008048c  mov     r8, rdi
0x18008048f  mov     edx, esi
0x180080491  mov     rax, [rax+3A8h]
0x180080498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008049d  mov     ecx, eax; int
0x18008049f  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x1800804a4  mov     rcx, [r15]
0x1800804a7  mov     rax, [rcx]
0x1800804aa  lea     rsi, [rbx+140h]
0x1800804b1  mov     r8, rsi
0x1800804b4  xor     edx, edx
0x1800804b6  mov     rax, [rax+3A8h]
0x1800804bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800804c2  mov     ecx, eax; int
0x1800804c4  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x1800804c9  mov     rcx, [r15]
0x1800804cc  mov     rax, [rcx]
0x1800804cf  mov     r8, r12
0x1800804d2  lea     rdx, CLSID_D2D1ColorManagement
0x1800804d9  mov     rax, [rax+1F8h]
0x1800804e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800804e5  mov     ecx, eax; int
0x1800804e7  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x1800804ec  mov     rcx, [r12]
0x1800804f0  mov     rax, [rcx]
0x1800804f3  lea     r15d, [r14+4]
0x1800804f7  mov     [rsp+110h+var_F0], r15d
0x1800804fc  mov     r9, rsi
0x1800804ff  xor     r8d, r8d
0x180080502  lea     esi, [r14-2]
0x180080506  mov     edx, esi
0x180080508  mov     rax, [rax+48h]
0x18008050c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080511  mov     ecx, eax; int
0x180080513  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x180080518  mov     rcx, [r12]
0x18008051c  mov     rax, [rcx]
0x18008051f  mov     [rsp+110h+var_F0], r15d
0x180080524  mov     r9, rdi
0x180080527  xor     r8d, r8d
0x18008052a  xor     edx, edx
0x18008052c  mov     rax, [rax+48h]
0x180080530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080535  mov     ecx, eax; int
0x180080537  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x18008053c  mov     rcx, [r12]
  ... truncated ...
```
