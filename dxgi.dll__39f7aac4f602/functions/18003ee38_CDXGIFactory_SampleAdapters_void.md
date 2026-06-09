# CDXGIFactory::SampleAdapters(void)

- ea: `0x18003ee38`
- end: `0x18003f046`
- name: `?SampleAdapters@CDXGIFactory@@QEAAJXZ`
- size: `526`
- prototype: `__int64 __fastcall(CDXGIFactory *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004f008`
- `0x180096470`

## callees

- `0x180010d40`
- `0x18001713c`
- `0x1800174f4`
- `0x18003ee38`
- `0x18003f04c`
- `0x1800405a4`
- `0x1800ab9fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ee89`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ee9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003eeaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003eec2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003eedd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ee89`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ee9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003eeaf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003eec2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003eedd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003efc1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003efc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ee68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ee68`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18003ee52`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18003ee52`
- `api-ms-win-dx-d3dkmt-l1-1-0!GdiEntry13` at `0x18003eef7`
- `api-ms-win-dx-d3dkmt-l1-1-0!GdiEntry13` at `0x18003ef55`
- `api-ms-win-dx-d3dkmt-l1-1-0!GdiEntry13` at `0x18003eef7`
- `api-ms-win-dx-d3dkmt-l1-1-0!GdiEntry13` at `0x18003ef55`
- `api-ms-win-dx-d3dkmt-l1-1-0!__imp_DrvQueryAdapterPopulationUniqueness` at `0x18003ef18`
- `api-ms-win-dx-d3dkmt-l1-1-0!__imp_DrvQueryAdapterPopulationUniqueness` at `0x18003ef65`
- `api-ms-win-dx-d3dkmt-l1-1-0!__imp_DrvQueryAdapterPopulationUniqueness` at `0x18003ef18`
- `api-ms-win-dx-d3dkmt-l1-1-0!__imp_DrvQueryAdapterPopulationUniqueness` at `0x18003ef65`
- `api-ms-win-dx-d3dkmt-l1-1-3!__imp_DrvQueryPrivateDisplayChangeUniqueness` at `0x18003ef0c`
- `api-ms-win-dx-d3dkmt-l1-1-3!__imp_DrvQueryPrivateDisplayChangeUniqueness` at `0x18003ef0c`

## string_xrefs

- `0x18003ee4b`: `gdi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
signed int __fastcall CDXGIFactory::SampleAdapters(CDXGIFactory *this)
{
  HMODULE LibraryA; // rax
  HMODULE v3; // rbx
  signed int result; // eax
  int (*ProcAddress)(const struct _D3DKMT_CLOSEADAPTER *); // r15
  int (*v6)(const struct _D3DKMT_ENUMADAPTERS2 *); // r12
  int (*v7)(const struct _D3DKMT_QUERYADAPTERINFO *); // r13
  int (*v8)(struct _D3DKMT_QUERYVIDEOMEMORYINFO *); // rdi
  int (*v9)(struct _D3DKMT_ISFEATUREENABLED *); // r14
  ULONG v10; // eax
  int v11; // r14d
  int v12; // edi
  int v13; // edi
  int (*v14)(struct _D3DKMT_ISFEATUREENABLED *); // [rsp+40h] [rbp-48h]
  _com_error *v15; // [rsp+48h] [rbp-40h] BYREF
  int (*v16)(struct _D3DKMT_QUERYVIDEOMEMORYINFO *); // [rsp+98h] [rbp+10h]
  int v17; // [rsp+98h] [rbp+10h]
  void *v18; // [rsp+A0h] [rbp+18h] BYREF
  HMODULE v19; // [rsp+A8h] [rbp+20h] BYREF

  LibraryA = LoadLibraryA("gdi32.dll");
  v3 = LibraryA;
  v19 = LibraryA;
  if ( !LibraryA )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  ProcAddress = (int (*)(const struct _D3DKMT_CLOSEADAPTER *))GetProcAddress(LibraryA, "D3DKMTCloseAdapter");
  v6 = (int (*)(const struct _D3DKMT_ENUMADAPTERS2 *))GetProcAddress(v3, "D3DKMTEnumAdapters2");
  v7 = (int (*)(const struct _D3DKMT_QUERYADAPTERINFO *))GetProcAddress(v3, "D3DKMTQueryAdapterInfo");
  v8 = (int (*)(struct _D3DKMT_QUERYVIDEOMEMORYINFO *))GetProcAddress(v3, "D3DKMTQueryVideoMemoryInfo");
  v16 = v8;
  v9 = (int (*)(struct _D3DKMT_ISFEATUREENABLED *))GetProcAddress(v3, "D3DKMTIsFeatureEnabled");
  v14 = v9;
  v18 = 0;
  try
  {
    while ( 1 )
    {
      v10 = GdiEntry13();
      *((_DWORD *)this + 187) = v10;
      if ( HIDWORD(qword_180109A08) )
        v10 = DrvQueryPrivateDisplayChangeUniqueness();
      *((_DWORD *)this + 188) = v10;
      *((_DWORD *)this + 189) = DrvQueryAdapterPopulationUniqueness();
      v11 = CDXGIFactory::SampleAdaptersWorker(this, ProcAddress, v6, v7, v8, v9, &v18);
      v12 = *((_DWORD *)this + 187);
      if ( v12 == GdiEntry13() )
      {
        v13 = *((_DWORD *)this + 189);
        if ( v13 == (unsigned int)DrvQueryAdapterPopulationUniqueness() )
          break;
      }
      CDXGIFactory::ClearAdapters(this, ProcAddress);
      v8 = v16;
      v9 = v14;
    }
    DXGIThrowFailure(v11);
    std::_Sort_unchecked<SAdapterDesc *,std::less<void>>(
      *((_QWORD *)this + 35),
      *((_QWORD *)this + 36),
      0xF0B7672A07A44C6BuLL * ((__int64)(*((_QWORD *)this + 36) - *((_QWORD *)this + 35)) >> 3),
      0);
  }
  catch ( std::bad_alloc )
  {
    if ( v18 )
      SdbReleaseDatabase();
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v19);
    return -2147024882;
  }
  catch ( _com_error *v15 )
  {
    v17 = *((_DWORD *)v15 + 2);
    if ( v18 )
      SdbReleaseDatabase();
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v19);
    return v17;
  }
  if ( v18 )
    SdbReleaseDatabase();
  if ( v3 )
    FreeLibrary(v3);
  return 0;
}

```

## disassembly

```asm
0x18003ee38  push    rbx
0x18003ee3a  push    rsi
0x18003ee3b  push    rdi
0x18003ee3c  push    r12
0x18003ee3e  push    r13
0x18003ee40  push    r14
0x18003ee42  push    r15
0x18003ee44  sub     rsp, 50h
0x18003ee48  mov     rsi, rcx
0x18003ee4b  lea     rcx, ModuleName; "gdi32.dll"
0x18003ee52  call    cs:__imp_LoadLibraryA
0x18003ee58  mov     rbx, rax
0x18003ee5b  mov     [rsp+88h+arg_18], rax
0x18003ee63  test    rax, rax
0x18003ee66  jnz     short loc_18003EE7F
0x18003ee68  call    cs:__imp_GetLastError
0x18003ee6e  test    eax, eax
0x18003ee70  jle     short loc_18003EE7A
0x18003ee72  movzx   eax, ax
0x18003ee75  or      eax, 80070000h
0x18003ee7a  jmp     loc_18003F036
0x18003ee7f  lea     rdx, aD3dkmtcloseada; "D3DKMTCloseAdapter"
0x18003ee86  mov     rcx, rbx; hModule
0x18003ee89  call    cs:__imp_GetProcAddress
0x18003ee8f  mov     r15, rax
0x18003ee92  lea     rdx, aD3dkmtenumadap; "D3DKMTEnumAdapters2"
0x18003ee99  mov     rcx, rbx; hModule
0x18003ee9c  call    cs:__imp_GetProcAddress
0x18003eea2  mov     r12, rax
0x18003eea5  lea     rdx, aD3dkmtqueryada_0; "D3DKMTQueryAdapterInfo"
0x18003eeac  mov     rcx, rbx; hModule
0x18003eeaf  call    cs:__imp_GetProcAddress
0x18003eeb5  mov     r13, rax
0x18003eeb8  lea     rdx, aD3dkmtqueryvid_1; "D3DKMTQueryVideoMemoryInfo"
0x18003eebf  mov     rcx, rbx; hModule
0x18003eec2  call    cs:__imp_GetProcAddress
0x18003eec8  mov     rdi, rax
0x18003eecb  mov     [rsp+88h+arg_8], rax
0x18003eed3  lea     rdx, aD3dkmtisfeatur; "D3DKMTIsFeatureEnabled"
0x18003eeda  mov     rcx, rbx; hModule
0x18003eedd  call    cs:__imp_GetProcAddress
0x18003eee3  mov     r14, rax
0x18003eee6  mov     [rsp+88h+var_48], rax
0x18003eeeb  mov     [rsp+88h+arg_10], 0
0x18003eef7  call    cs:__imp_GdiEntry13
0x18003eefd  mov     [rsi+2ECh], eax
0x18003ef03  cmp     dword ptr cs:qword_180109A08+4, 0
0x18003ef0a  jz      short loc_18003EF12
0x18003ef0c  call    cs:__imp_DrvQueryPrivateDisplayChangeUniqueness
0x18003ef12  mov     [rsi+2F0h], eax
0x18003ef18  call    cs:__imp_DrvQueryAdapterPopulationUniqueness
0x18003ef1e  mov     [rsi+2F4h], eax
0x18003ef24  lea     rax, [rsp+88h+arg_10]
0x18003ef2c  mov     [rsp+88h+var_58], rax; void **
0x18003ef31  mov     [rsp+88h+var_60], r14; int (*)(struct _D3DKMT_ISFEATUREENABLED *)
0x18003ef36  mov     [rsp+88h+var_68], rdi; int (*)(struct _D3DKMT_QUERYVIDEOMEMORYINFO *)
0x18003ef3b  mov     r9, r13; int (*)(const struct _D3DKMT_QUERYADAPTERINFO *)
0x18003ef3e  mov     r8, r12; int (*)(const struct _D3DKMT_ENUMADAPTERS2 *)
0x18003ef41  mov     rdx, r15; int (*)(const struct _D3DKMT_CLOSEADAPTER *)
0x18003ef44  mov     rcx, rsi; this
0x18003ef47  call    ?SampleAdaptersWorker@CDXGIFactory@@AEAAJP6AJPEBU_D3DKMT_CLOSEADAPTER@@@ZP6AJPEBU_D3DKMT_ENUMADAPTERS2@@@ZP6AJPEBU_D3DKMT_QUERYADAPTERINFO@@@ZP6AJPEAU_D3DKMT_QUERYVIDEOMEMORYINFO@@@ZP6AJPEAU_D3DKMT_ISFEATUREENABLED@@@ZPEAPEAX@Z; CDXGIFactory::SampleAdaptersWorker(long (*)(_D3DKMT_CLOSEADAPTER const *),long (*)(_D3DKMT_ENUMADAPTERS2 const *),long (*)(_D3DKMT_QUERYADAPTERINFO const *),long (*)(_D3DKMT_QUERYVIDEOMEMORYINFO *),long (*)(_D3DKMT_ISFEATUREENABLED *),void * *)
0x18003ef4c  mov     r14d, eax
0x18003ef4f  mov     edi, [rsi+2ECh]
0x18003ef55  call    cs:__imp_GdiEntry13
0x18003ef5b  cmp     edi, eax
0x18003ef5d  jnz     short loc_18003EFCB
0x18003ef5f  mov     edi, [rsi+2F4h]
0x18003ef65  call    cs:__imp_DrvQueryAdapterPopulationUniqueness
0x18003ef6b  cmp     edi, eax
0x18003ef6d  jnz     short loc_18003EFCB
0x18003ef6f  mov     ecx, r14d; int
0x18003ef72  call    ?DXGIThrowFailure@@YAXJ@Z; DXGIThrowFailure(long)
0x18003ef77  mov     rdx, [rsi+120h]
0x18003ef7e  mov     rcx, [rsi+118h]
0x18003ef85  mov     r8, rdx
0x18003ef88  sub     r8, rcx
0x18003ef8b  sar     r8, 3
0x18003ef8f  mov     rax, 0F0B7672A07A44C6Bh
0x18003ef99  imul    r8, rax
0x18003ef9d  xor     r9d, r9d
0x18003efa0  call    ??$_Sort_unchecked@PEAUSAdapterDesc@@U?$less@X@std@@@std@@YAXPEAUSAdapterDesc@@0_JU?$less@X@0@@Z; std::_Sort_unchecked<SAdapterDesc *,std::less<void>>(SAdapterDesc *,SAdapterDesc *,__int64,std::less<void>)
0x18003efa5  nop
0x18003efa6  mov     rcx, [rsp+88h+arg_10]
0x18003efae  test    rcx, rcx
0x18003efb1  jz      short loc_18003EFB9
0x18003efb3  call    SdbReleaseDatabase
0x18003efb8  nop
0x18003efb9  test    rbx, rbx
0x18003efbc  jz      short loc_18003EFC7
0x18003efbe  mov     rcx, rbx; hLibModule
0x18003efc1  call    cs:__imp_FreeLibrary
0x18003efc7  xor     eax, eax
0x18003efc9  jmp     short loc_18003F036
0x18003efcb  mov     rdx, r15; int (*)(const struct _D3DKMT_CLOSEADAPTER *)
0x18003efce  mov     rcx, rsi; this
0x18003efd1  call    ?ClearAdapters@CDXGIFactory@@AEAAXP6AJPEBU_D3DKMT_CLOSEADAPTER@@@Z@Z; CDXGIFactory::ClearAdapters(long (*)(_D3DKMT_CLOSEADAPTER const *))
0x18003efd6  mov     rdi, [rsp+88h+arg_8]
0x18003efde  mov     r14, [rsp+88h+var_48]
0x18003efe3  jmp     loc_18003EEF7
0x18003efe8  mov     rcx, [rsp+88h+arg_10]
0x18003eff0  test    rcx, rcx
0x18003eff3  jz      short loc_18003EFFB
0x18003eff5  call    SdbReleaseDatabase
0x18003effa  nop
0x18003effb  lea     rcx, [rsp+88h+arg_18]
0x18003f003  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18003f008  mov     eax, 8007000Eh
0x18003f00d  jmp     short loc_18003F036
0x18003f00f  mov     rcx, [rsp+88h+arg_10]
0x18003f017  test    rcx, rcx
0x18003f01a  jz      short loc_18003F022
0x18003f01c  call    SdbReleaseDatabase
0x18003f021  nop
0x18003f022  lea     rcx, [rsp+88h+arg_18]
0x18003f02a  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18003f02f  mov     eax, dword ptr [rsp+88h+arg_8]
0x18003f036  add     rsp, 50h
0x18003f03a  pop     r15
0x18003f03c  pop     r14
0x18003f03e  pop     r13
0x18003f040  pop     r12
0x18003f042  pop     rdi
0x18003f043  pop     rsi
0x18003f044  pop     rbx
0x18003f045  retn
```
