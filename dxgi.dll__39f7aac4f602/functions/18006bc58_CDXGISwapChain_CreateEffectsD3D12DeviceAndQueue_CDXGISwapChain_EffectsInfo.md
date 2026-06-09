# CDXGISwapChain::CreateEffectsD3D12DeviceAndQueue(CDXGISwapChain::EffectsInfo &)

- ea: `0x18006bc58`
- end: `0x18006c328`
- name: `?CreateEffectsD3D12DeviceAndQueue@CDXGISwapChain@@AEAAJAEAUEffectsInfo@1@@Z`
- size: `1744`
- prototype: `__int64 __fastcall(CDXGISwapChain *__hidden this, struct CDXGISwapChain::EffectsInfo *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027944`

## callees

- `0x18000c6b0`
- `0x180014750`
- `0x18001b22c`
- `0x18002e5d8`
- `0x18003e5fc`
- `0x180060320`
- `0x180067d2c`
- `0x18006bc58`
- `0x18006c330`
- `0x18006c410`
- `0x180070b2c`
- `0x180075fa0`
- `0x18008ada0`
- `0x180091e70`
- `0x180095550`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006bd24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006bd24`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18006bce0`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18006bce0`

## string_xrefs

- `0x18006bcb4`: `onecoreuap\windows\directx\dxg\dxgi\dll\swapchan.cpp`
- `0x18006bd81`: `onecoreuap\windows\directx\dxg\dxgi\dll\swapchan.cpp`
- `0x18006bd04`: `Failed to load d3d12.dll`
- `0x18006bcd9`: `d3d12.dll`
- `0x18006c2ef`: `D3D12 device already exists`
- `0x18006bd1d`: `D3D12CreateDevice`
- `0x18006bdd4`: `Failed to create 11-12 primary queue`
- `0x18006bd4c`: `Failed to create 11-12 device`
- `0x18006be55`: `Failed to create 11-12 secondary queue`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CDXGISwapChain::CreateEffectsD3D12DeviceAndQueue(
        CDXGISwapChain *this,
        struct CDXGISwapChain::EffectsInfo *a2,
        __int64 a3,
        bool a4)
{
  HMODULE *v6; // rbx
  HMODULE v7; // rcx
  HMODULE LibraryW; // rax
  signed int LastErrorFailHr; // eax
  CModule *v10; // rcx
  bool v11; // r9
  unsigned int v12; // ebx
  FARPROC ProcAddress; // rax
  signed int v15; // eax
  CModule *v16; // rcx
  bool v17; // r9
  int v18; // eax
  signed int v19; // eax
  CModule *v20; // rcx
  bool v21; // r9
  unsigned int v22; // edi
  int v23; // eax
  signed int v24; // eax
  CModule *v25; // rcx
  bool v26; // r9
  int v27; // eax
  CLockOwner *v28; // rax
  CLockOwner *v29; // rdi
  int v30; // eax
  __int64 v31; // rdx
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  void *v36; // rdx
  __int64 v37; // rbx
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  void (__fastcall ***v42)(_QWORD, GUID *, _QWORD *); // rbx
  __int64 v43; // rdx
  void (__fastcall ***v44)(_QWORD, GUID *, _QWORD *); // rbx
  __int64 v45; // rdx
  int v46; // [rsp+20h] [rbp-99h]
  int v47; // [rsp+20h] [rbp-99h]
  __int64 v48; // [rsp+40h] [rbp-79h] BYREF
  void *v49; // [rsp+48h] [rbp-71h] BYREF
  int v50[2]; // [rsp+50h] [rbp-69h] BYREF
  __int64 v51; // [rsp+58h] [rbp-61h] BYREF
  void (__fastcall ***v52)(_QWORD, GUID *, CLockOwner **); // [rsp+60h] [rbp-59h] BYREF
  __int64 (__fastcall ***v53)(_QWORD, GUID *, _QWORD); // [rsp+68h] [rbp-51h] BYREF
  CLockOwner *v54; // [rsp+70h] [rbp-49h] BYREF
  __int64 v55; // [rsp+78h] [rbp-41h] BYREF
  CLockOwner *v56; // [rsp+80h] [rbp-39h] BYREF
  __int64 v57; // [rsp+88h] [rbp-31h] BYREF
  __int64 v58; // [rsp+90h] [rbp-29h] BYREF
  void (__fastcall ***v59)(_QWORD, GUID *, CLockOwner **); // [rsp+98h] [rbp-21h] BYREF
  _QWORD v60[6]; // [rsp+A0h] [rbp-19h] BYREF
  int v61; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v62; // [rsp+D4h] [rbp+1Bh]
  int v63; // [rsp+DCh] [rbp+23h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  if ( *((_QWORD *)this + 32) || *((char *)this + 288) < 0 )
  {
    CModule::RecordJournalImpl(this, 0x8000FFFF, "D3D12 device already exists", a4);
    return 2147549183LL;
  }
  if ( *((_QWORD *)a2 + 55) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3CD6,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\swapchan.cpp",
      (const char *)0x8000FFFFLL,
      v46);
    return 2147549183LL;
  }
  v6 = (HMODULE *)((char *)this + 4472);
  v7 = (HMODULE)*((_QWORD *)this + 559);
  if ( !v7 )
  {
    LibraryW = LoadLibraryW(L"d3d12.dll");
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
      v6,
      LibraryW);
    v7 = *v6;
    if ( !*v6 )
    {
      LastErrorFailHr = wil::details::GetLastErrorFailHr(0);
      v12 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
        CModule::RecordJournalImpl(v10, LastErrorFailHr, "Failed to load d3d12.dll", v11);
      return v12;
    }
  }
  v48 = 0;
  ProcAddress = GetProcAddress(v7, "D3D12CreateDevice");
  v15 = ((__int64 (__fastcall *)(_QWORD, __int64, GUID *, __int64 *))ProcAddress)(
          *((_QWORD *)this + 40),
          45056,
          &GUID_189819f1_1db6_4b57_be54_1821339b85f7,
          &v48);
  v12 = v15;
  if ( v15 < 0 )
  {
    CModule::RecordJournalImpl(v16, v15, "Failed to create 11-12 device", v17);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    return v12;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v48 + 48LL))(v48, L"DXGI Effects 11-12 Device");
  if ( v18 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3CED,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\swapchan.cpp",
      (const char *)(unsigned int)v18,
      v46);
  v55 = 0;
  v62 = 0;
  v63 = 1;
  v61 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, int *, GUID *, __int64 *))(*(_QWORD *)v48 + 64LL))(
          v48,
          &v61,
          &GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed,
          &v55);
  v22 = v19;
  if ( v19 < 0 )
  {
    CModule::RecordJournalImpl(v20, v19, "Failed to create 11-12 primary queue", v21);
LABEL_16:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
    return v22;
  }
  v23 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v55 + 48LL))(
          v55,
          L"DXGI Effects 11-12 Primary Queue");
  if ( v23 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3CFB,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\swapchan.cpp",
      (const char *)(unsigned int)v23,
      v46);
  v57 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64, int *, GUID *, __int64 *))(*(_QWORD *)v48 + 64LL))(
          v48,
          &v61,
          &GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed,
          &v57);
  v22 = v24;
  if ( v24 < 0 )
  {
    CModule::RecordJournalImpl(v25, v24, "Failed to create 11-12 secondary queue", v26);
LABEL_49:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v57);
    goto LABEL_16;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)v57 + 48LL))(
          v57,
          L"DXGI Effects Secondary Queue");
  if ( v27 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3D06,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\swapchan.cpp",
      (const char *)(unsigned int)v27,
      v46);
  v28 = (CLockOwner *)operator new(0x38u);
  v56 = v28;
  if ( v28 )
    v29 = CLockOwner::CLockOwner(v28);
  else
    v29 = 0;
  v54 = v29;
  if ( !v29 )
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D0A,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\swapchan.cpp",
      (const char *)0x8007000ELL,
      v46);
LABEL_48:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
    goto LABEL_49;
  }
  (*(void (__fastcall **)(CLockOwner *))(*(_QWORD *)v29 + 8LL))(v29);
  v49 = 0;
  v60[0] = v29;
  v60[1] = v48;
  v60[2] = v55;
  v60[3] = (char *)this + 200;
  v60[4] = (char *)this + 840;
  v60[5] = *((_QWORD *)this + 115);
  TComObject<CD3D12Device>::CreateInstance((struct CD3D12Device::TConstructorArgs *)v60, &v49);
  if ( !v49 )
  {
    v22 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D15,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\swapchan.cpp",
      (const char *)0x80004005LL,
      v47);
LABEL_47:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
    goto LABEL_48;
  }
  v51 = 0;
  v53 = 0;
  v52 = 0;
  v30 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 30))(
          *((_QWORD *)this + 30),
          &GUID_8ffde202_a0e7_45df_9e01_e837801b5ea0,
          &v51);
  v22 = v30;
  if ( v30 < 0 )
  {
    v31 = 15643;
LABEL_33:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\swapchan.cpp",
      (const char *)(unsigned int)v30,
      v47);
LABEL_46:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
    goto LABEL_47;
  }
  (*(void (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD)))(*(_QWORD *)v51 + 320LL))(
    v51,
    &v53);
  v30 = (**v53)(v53, &GUID_0b6c8dc4_c193_42ea_839c_ed9a2ca408a1, &v52);
  v22 = v30;
  if ( v30 < 0 )
  {
    v31 = 15645;
    goto LABEL_33;
  }
  *(_QWORD *)v50 = 0;
  v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, GUID *))(*(_QWORD *)v48 + 288LL))(
          v48,
          0,
          1,
          &GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76);
  v22 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D21,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\swapchan.cpp",
      (const char *)(unsigned int)v32,
      (int)v50);
LABEL_45:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v50);
    goto LABEL_46;
  }
  v33 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *))(**(_QWORD **)v50 + 48LL))(
          *(_QWORD *)v50,
          L"DXGI Effects 11-12 Fence");
  if ( v33 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3D22,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\swapchan.cpp",
      (const char *)(unsigned int)v33,
      (int)v50);
  v58 = 0;
  v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v48 + 248LL))(
          v48,
          *(_QWORD *)v50,
          0,
          0x10000000);
  v22 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D24,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\swapchan.cpp",
      (const char *)(unsigned int)v34,
      0);
LABEL_44:
    SafeHANDLE::Close((SafeHANDLE *)&v58);
    goto LABEL_45;
  }
  v59 = 0;
  v35 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, void (__fastcall ****)(_QWORD, GUID *, CLockOwner **)))(*(_QWORD *)v51 + 536LL))(
          v51,
          v58,
          &GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80,
          &v59);
  v22 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D26,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\dxgi\\dll\\swapchan.cpp",
      (const char *)(unsigned int)v35,
      0);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v59);
    goto LABEL_44;
  }
  v36 = v49;
  v49 = 0;
  ATL::CComPtrBase<CD3D12Device>::Attach((char *)a2 + 456, v36);
  v37 = v48;
  v48 = 0;
  v38 = *((_QWORD *)a2 + 55);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  *((_QWORD *)a2 + 55) = v37;
  v39 = v55;
  v55 = 0;
  ATL::CComPtrBase<ID3D12Fence>::Attach((char *)a2 + 448, v39);
  v40 = v57;
  v57 = 0;
  ATL::CComPtrBase<ID3D12Fence>::Attach((char *)a2 + 520, v40);
  v41 = *(_QWORD *)v50;
  *(_QWORD *)v50 = 0;
  ATL::CComPtrBase<ID3D12Fence>::Attach((char *)a2 + 464, v41);
  v42 = (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))v52;
  if ( v52 )
  {
    v56 = 0;
    (**v52)(v52, &GUID_9b7e4a01_342c_4106_a19f_4f2704f689f0, &v56);
    (*(void (__fastcall **)(CLockOwner *))(*(_QWORD *)v56 + 24LL))(v56);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v56);
  }
  v43 = *((_QWORD *)a2 + 59);
  *((_QWORD *)a2 + 59) = v42;
  if ( v43 )
    unique_usecntptr_deleter<ID3D11Fence>::operator()();
  v44 = (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))v59;
  if ( v59 )
  {
    v56 = 0;
    (**v59)(v59, &GUID_9b7e4a01_342c_4106_a19f_4f2704f689f0, &v56);
    (*(void (__fastcall **)(CLockOwner *))(*(_QWORD *)v56 + 24LL))(v56);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v56);
  }
  v45 = *((_QWORD *)a2 + 60);
  *((_QWORD *)a2 + 60) = v44;
  if ( v45 )
    unique_usecntptr_deleter<ID3D11Fence>::operator()();
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v59);
  SafeHANDLE::Close((SafeHANDLE *)&v58);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v50);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v52);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v53);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v49);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v54);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v57);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v55);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v48);
  return 0;
}

```

## disassembly

```asm
0x18006bc58  mov     [rsp-8+arg_10], rbx
0x18006bc5d  push    rbp
0x18006bc5e  push    rsi
0x18006bc5f  push    rdi
0x18006bc60  push    r14
0x18006bc62  push    r15
0x18006bc64  lea     rbp, [rsp-37h]
0x18006bc69  sub     rsp, 0F0h
0x18006bc70  mov     rax, cs:__security_cookie
0x18006bc77  xor     rax, rsp
0x18006bc7a  mov     [rbp+57h+var_30], rax
0x18006bc7e  mov     rsi, rdx
0x18006bc81  mov     r14, rcx
0x18006bc84  xor     r15d, r15d
0x18006bc87  cmp     [rcx+100h], r15
0x18006bc8e  jnz     loc_18006C2EF
0x18006bc94  test    byte ptr [rcx+120h], 80h
0x18006bc9b  jnz     loc_18006C2EF
0x18006bca1  cmp     [rdx+1B8h], r15
0x18006bca8  jz      short loc_18006BCCA
0x18006bcaa  mov     rcx, [rbp+5Fh]; this
0x18006bcae  mov     r9d, 8000FFFFh; char *
0x18006bcb4  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x18006bcbb  mov     edx, 3CD6h; void *
0x18006bcc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bcc5  jmp     loc_18006C300
0x18006bcca  lea     rbx, [rcx+1178h]
0x18006bcd1  mov     rcx, [rbx]; hModule
0x18006bcd4  test    rcx, rcx
0x18006bcd7  jnz     short loc_18006BD19
0x18006bcd9  lea     rcx, aD3d12Dll_0; "d3d12.dll"
0x18006bce0  call    cs:__imp_LoadLibraryW
0x18006bce6  mov     rdx, rax
0x18006bce9  mov     rcx, rbx
0x18006bcec  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18006bcf1  mov     rcx, [rbx]; this
0x18006bcf4  test    rcx, rcx
0x18006bcf7  jnz     short loc_18006BD19
0x18006bcf9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18006bcfe  mov     ebx, eax
0x18006bd00  test    eax, eax
0x18006bd02  jns     short loc_18006BD12
0x18006bd04  lea     r8, aFailedToLoadD3; "Failed to load d3d12.dll"
0x18006bd0b  mov     edx, eax; unsigned int
0x18006bd0d  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18006bd12  mov     eax, ebx
0x18006bd14  jmp     loc_18006C305
0x18006bd19  mov     [rbp+57h+var_D0], r15
0x18006bd1d  lea     rdx, aD3d12createdev; "D3D12CreateDevice"
0x18006bd24  call    cs:__imp_GetProcAddress
0x18006bd2a  lea     r9, [rbp+57h+var_D0]
0x18006bd2e  lea     r8, _GUID_189819f1_1db6_4b57_be54_1821339b85f7
0x18006bd35  mov     edx, 0B000h
0x18006bd3a  mov     rcx, [r14+140h]
0x18006bd41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bd46  mov     ebx, eax
0x18006bd48  test    eax, eax
0x18006bd4a  jns     short loc_18006BD66
0x18006bd4c  lea     r8, aFailedToCreate_4; "Failed to create 11-12 device"
0x18006bd53  mov     edx, eax; unsigned int
0x18006bd55  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18006bd5a  nop
0x18006bd5b  lea     rcx, [rbp+57h+var_D0]
0x18006bd5f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006bd64  jmp     short loc_18006BD12
0x18006bd66  mov     rcx, [rbp+57h+var_D0]
0x18006bd6a  mov     rax, [rcx]
0x18006bd6d  lea     rdx, aDxgiEffects111; "DXGI Effects 11-12 Device"
0x18006bd74  mov     rax, [rax+30h]
0x18006bd78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bd7d  mov     rcx, [rbp+5Fh]; this
0x18006bd81  lea     rbx, aOnecoreuapWind_3; "onecoreuap\\windows\\directx\\dxg\\dxgi"...
0x18006bd88  test    eax, eax
0x18006bd8a  jns     short loc_18006BD9C
0x18006bd8c  mov     r9d, eax; char *
0x18006bd8f  mov     r8, rbx; unsigned int
0x18006bd92  mov     edx, 3CEDh; void *
0x18006bd97  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006bd9c  mov     [rbp+57h+var_98], r15
0x18006bda0  mov     [rbp+57h+var_3C], r15
0x18006bda4  mov     [rbp+57h+var_34], 1
0x18006bdab  mov     [rbp+57h+var_40], r15d
0x18006bdaf  mov     rcx, [rbp+57h+var_D0]
0x18006bdb3  mov     rax, [rcx]
0x18006bdb6  lea     r9, [rbp+57h+var_98]
0x18006bdba  lea     r8, _GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed
0x18006bdc1  lea     rdx, [rbp+57h+var_40]
0x18006bdc5  mov     rax, [rax+40h]
0x18006bdc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bdce  mov     edi, eax
0x18006bdd0  test    eax, eax
0x18006bdd2  jns     short loc_18006BDFD
0x18006bdd4  lea     r8, aFailedToCreate_2; "Failed to create 11-12 primary queue"
0x18006bddb  mov     edx, eax; unsigned int
0x18006bddd  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18006bde2  nop
0x18006bde3  lea     rcx, [rbp+57h+var_98]
0x18006bde7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006bdec  nop
0x18006bded  lea     rcx, [rbp+57h+var_D0]
0x18006bdf1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006bdf6  mov     eax, edi
0x18006bdf8  jmp     loc_18006C305
0x18006bdfd  mov     rcx, [rbp+57h+var_98]
0x18006be01  mov     rax, [rcx]
0x18006be04  lea     rdx, aDxgiEffects111_0; "DXGI Effects 11-12 Primary Queue"
0x18006be0b  mov     rax, [rax+30h]
0x18006be0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be14  mov     rcx, [rbp+5Fh]; this
0x18006be18  test    eax, eax
0x18006be1a  jns     short loc_18006BE2C
0x18006be1c  mov     r9d, eax; char *
0x18006be1f  mov     r8, rbx; unsigned int
0x18006be22  mov     edx, 3CFBh; void *
0x18006be27  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006be2c  mov     [rbp+57h+var_88], r15
0x18006be30  mov     rcx, [rbp+57h+var_D0]
0x18006be34  mov     rax, [rcx]
0x18006be37  lea     r9, [rbp+57h+var_88]
0x18006be3b  lea     r8, _GUID_0ec870a6_5d7e_4c22_8cfc_5baae07616ed
0x18006be42  lea     rdx, [rbp+57h+var_40]
0x18006be46  mov     rax, [rax+40h]
0x18006be4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be4f  mov     edi, eax
0x18006be51  test    eax, eax
0x18006be53  jns     short loc_18006BE68
0x18006be55  lea     r8, aFailedToCreate; "Failed to create 11-12 secondary queue"
0x18006be5c  mov     edx, eax; unsigned int
0x18006be5e  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x18006be63  jmp     loc_18006C145
0x18006be68  mov     rcx, [rbp+57h+var_88]
0x18006be6c  mov     rax, [rcx]
0x18006be6f  lea     rdx, aDxgiEffectsSec; "DXGI Effects Secondary Queue"
0x18006be76  mov     rax, [rax+30h]
0x18006be7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006be7f  mov     rcx, [rbp+5Fh]; this
0x18006be83  test    eax, eax
0x18006be85  jns     short loc_18006BE97
0x18006be87  mov     r9d, eax; char *
0x18006be8a  mov     r8, rbx; unsigned int
0x18006be8d  mov     edx, 3D06h; void *
0x18006be92  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006be97  mov     ecx, 38h ; '8'; dwBytes
0x18006be9c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006bea1  mov     [rbp+57h+var_90], rax
0x18006bea5  test    rax, rax
0x18006bea8  jz      short loc_18006BEB7
0x18006beaa  mov     rcx, rax; this
0x18006bead  call    ??0CLockOwner@@QEAA@XZ; CLockOwner::CLockOwner(void)
0x18006beb2  mov     rdi, rax
0x18006beb5  jmp     short loc_18006BEBA
0x18006beb7  mov     rdi, r15
0x18006beba  mov     [rbp+57h+var_A0], rdi
0x18006bebe  test    rdi, rdi
0x18006bec1  jz      short loc_18006BED3
0x18006bec3  mov     rax, [rdi]
0x18006bec6  mov     rcx, rdi
0x18006bec9  mov     rax, [rax+8]
0x18006becd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bed2  nop
0x18006bed3  test    rdi, rdi
0x18006bed6  jnz     short loc_18006BEF6
0x18006bed8  mov     rcx, [rbp+5Fh]; this
0x18006bedc  mov     edi, 8007000Eh
0x18006bee1  mov     r9d, edi; char *
0x18006bee4  mov     r8, rbx; unsigned int
0x18006bee7  mov     edx, 3D0Ah; void *
0x18006beec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bef1  jmp     loc_18006C13B
0x18006bef6  mov     [rbp+57h+var_C8], r15
0x18006befa  mov     [rbp+57h+var_70], rdi
0x18006befe  mov     rax, [rbp+57h+var_D0]
0x18006bf02  mov     [rbp+57h+var_68], rax
0x18006bf06  mov     rax, [rbp+57h+var_98]
0x18006bf0a  mov     [rbp+57h+var_60], rax
0x18006bf0e  lea     rax, [r14+0C8h]
0x18006bf15  mov     [rbp+57h+var_58], rax
0x18006bf19  lea     rax, [r14+348h]
0x18006bf20  mov     [rbp+57h+var_50], rax
0x18006bf24  mov     rax, [r14+398h]
0x18006bf2b  mov     [rbp+57h+var_48], rax
0x18006bf2f  lea     rax, [rbp+57h+var_C8]
0x18006bf33  mov     [rsp+110h+var_F0], rax; int
0x18006bf38  lea     rcx, [rbp+57h+var_70]; struct CD3D12Device::TConstructorArgs *
0x18006bf3c  call    ?CreateInstance@?$TComObject@VCD3D12Device@@@@SAXAEBUTConstructorArgs@CD3D12Device@@PEAX1AEBU_GUID@@PEAPEAX@Z; TComObject<CD3D12Device>::CreateInstance(CD3D12Device::TConstructorArgs const &,void *,void *,_GUID const &,void * *)
0x18006bf41  cmp     [rbp+57h+var_C8], r15
0x18006bf45  jnz     short loc_18006BF65
0x18006bf47  mov     rcx, [rbp+5Fh]; this
0x18006bf4b  mov     edi, 80004005h
0x18006bf50  mov     r9d, edi; char *
0x18006bf53  mov     r8, rbx; unsigned int
0x18006bf56  mov     edx, 3D15h; void *
0x18006bf5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bf60  jmp     loc_18006C131
0x18006bf65  mov     [rbp+57h+var_B8], r15
0x18006bf69  mov     [rbp+57h+var_A8], r15
0x18006bf6d  mov     [rbp+57h+var_B0], r15
0x18006bf71  mov     rcx, [r14+0F0h]
0x18006bf78  mov     rax, [rcx]
0x18006bf7b  lea     r8, [rbp+57h+var_B8]
0x18006bf7f  lea     rdx, _GUID_8ffde202_a0e7_45df_9e01_e837801b5ea0
0x18006bf86  mov     rax, [rax]
0x18006bf89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf8e  mov     edi, eax
0x18006bf90  test    eax, eax
0x18006bf92  jns     short loc_18006BFAD
0x18006bf94  mov     edx, 3D1Bh; void *
0x18006bf99  mov     r8, rbx; unsigned int
0x18006bf9c  mov     r9d, eax; char *
0x18006bf9f  mov     rcx, [rbp+5Fh]; this
0x18006bfa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006bfa8  jmp     loc_18006C113
0x18006bfad  mov     rcx, [rbp+57h+var_B8]
0x18006bfb1  mov     rax, [rcx]
0x18006bfb4  lea     rdx, [rbp+57h+var_A8]
0x18006bfb8  mov     rax, [rax+140h]
0x18006bfbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bfc4  mov     rcx, [rbp+57h+var_A8]
0x18006bfc8  mov     rax, [rcx]
0x18006bfcb  lea     r8, [rbp+57h+var_B0]
0x18006bfcf  lea     rdx, _GUID_0b6c8dc4_c193_42ea_839c_ed9a2ca408a1
0x18006bfd6  mov     rax, [rax]
0x18006bfd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bfde  mov     edi, eax
0x18006bfe0  test    eax, eax
0x18006bfe2  jns     short loc_18006BFEB
0x18006bfe4  mov     edx, 3D1Dh
0x18006bfe9  jmp     short loc_18006BF99
0x18006bfeb  mov     qword ptr [rbp+57h+var_C0], r15
0x18006bfef  mov     rcx, [rbp+57h+var_D0]
0x18006bff3  mov     rax, [rcx]
0x18006bff6  lea     rdx, [rbp+57h+var_C0]
0x18006bffa  mov     [rsp+110h+var_F0], rdx; int
0x18006bfff  lea     r9, _GUID_0a753dcf_c4d8_4b91_adf6_be5a60d95a76
0x18006c006  xor     edx, edx
0x18006c008  lea     r8d, [rdx+1]
0x18006c00c  mov     rax, [rax+120h]
0x18006c013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c018  mov     edi, eax
0x18006c01a  test    eax, eax
0x18006c01c  jns     short loc_18006C037
0x18006c01e  mov     rcx, [rbp+5Fh]; this
0x18006c022  mov     r9d, eax; char *
0x18006c025  mov     r8, rbx; unsigned int
0x18006c028  mov     edx, 3D21h; void *
0x18006c02d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c032  jmp     loc_18006C109
0x18006c037  mov     rcx, qword ptr [rbp+57h+var_C0]
0x18006c03b  mov     rax, [rcx]
0x18006c03e  lea     rdx, aDxgiEffects111_1; "DXGI Effects 11-12 Fence"
0x18006c045  mov     rax, [rax+30h]
0x18006c049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c04e  mov     rcx, [rbp+5Fh]; this
0x18006c052  test    eax, eax
0x18006c054  jns     short loc_18006C066
0x18006c056  mov     r9d, eax; char *
0x18006c059  mov     r8, rbx; unsigned int
0x18006c05c  mov     edx, 3D22h; void *
0x18006c061  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c066  mov     [rbp+57h+var_80], r15
0x18006c06a  mov     rcx, [rbp+57h+var_D0]
0x18006c06e  mov     rax, [rcx]
0x18006c071  lea     rdx, [rbp+57h+var_80]
0x18006c075  mov     [rsp+110h+var_E8], rdx
0x18006c07a  mov     [rsp+110h+var_F0], r15; int
0x18006c07f  mov     r9d, 10000000h
0x18006c085  xor     r8d, r8d
0x18006c088  mov     rdx, qword ptr [rbp+57h+var_C0]
0x18006c08c  mov     rax, [rax+0F8h]
0x18006c093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c098  mov     edi, eax
0x18006c09a  test    eax, eax
0x18006c09c  jns     short loc_18006C0B4
0x18006c09e  mov     rcx, [rbp+5Fh]; this
0x18006c0a2  mov     r9d, eax; char *
0x18006c0a5  mov     r8, rbx; unsigned int
0x18006c0a8  mov     edx, 3D24h; void *
0x18006c0ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c0b2  jmp     short loc_18006C0FF
0x18006c0b4  mov     [rbp+57h+var_78], r15
0x18006c0b8  mov     rcx, [rbp+57h+var_B8]
0x18006c0bc  mov     rax, [rcx]
0x18006c0bf  lea     r9, [rbp+57h+var_78]
0x18006c0c3  lea     r8, _GUID_affde9d1_1df7_4bb7_8a34_0f46251dab80
0x18006c0ca  mov     rdx, [rbp+57h+var_80]
0x18006c0ce  mov     rax, [rax+218h]
0x18006c0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c0da  mov     edi, eax
0x18006c0dc  test    eax, eax
0x18006c0de  jns     short loc_18006C153
0x18006c0e0  mov     rcx, [rbp+5Fh]; this
0x18006c0e4  mov     r9d, eax; char *
0x18006c0e7  mov     r8, rbx; unsigned int
0x18006c0ea  mov     edx, 3D26h; void *
0x18006c0ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c0f4  nop
0x18006c0f5  lea     rcx, [rbp+57h+var_78]
0x18006c0f9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18006c0fe  nop
0x18006c0ff  lea     rcx, [rbp+57h+var_80]; this
  ... truncated ...
```
