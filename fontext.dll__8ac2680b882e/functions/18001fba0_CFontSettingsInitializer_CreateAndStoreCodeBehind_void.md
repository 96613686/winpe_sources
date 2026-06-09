# CFontSettingsInitializer::_CreateAndStoreCodeBehind(void)

- ea: `0x18001fba0`
- end: `0x18001fcc4`
- name: `?_CreateAndStoreCodeBehind@CFontSettingsInitializer@@IEAAJXZ`
- size: `292`
- prototype: `__int64 __fastcall(CFontSettingsInitializer *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001fad0`

## callees

- `0x18001c0d0`
- `0x18001f98c`
- `0x18001f9cc`
- `0x18001fa30`
- `0x18001fba0`
- `0x180032010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001fbd6`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001fbd6`
- `OLEAUT32!__imp_VariantClear` at `0x18001fc91`
- `OLEAUT32!__imp_VariantClear` at `0x18001fc91`

## pseudocode

```c
__int64 __fastcall CFontSettingsInitializer::_CreateAndStoreCodeBehind(CFontSettingsInitializer *this)
{
  void **RasterFont; // rax
  __int64 v2; // r10
  unsigned __int64 v3; // rdx
  HRESULT Service; // edi
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  VARIANTARG pvarg; // [rsp+20h] [rbp-28h] BYREF
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  ATL::CComPtr<IPropertyBag>::CComPtr<IPropertyBag>(&v9);
  RasterFont = (void **)CFontRegValue_Raster::QueryRasterFont((CFontRegValue_Raster *)&v9);
  Service = IUnknown_QueryService(
              *(IUnknown **)(v2 + 16),
              (const GUID *const)&SID_PerNamespaceIDPropertyBag,
              &GUID_55272a00_42cb_11ce_8135_00aa004bb851,
              RasterFont);
  if ( Service >= 0 )
  {
    v5 = DirectUI::HAllocAndZero((DirectUI *)0x30, v3);
    v6 = v5;
    if ( v5 )
    {
      v5[1] = 0;
      *v5 = &CFontSettingsCore::`vftable';
      v5[2] = 0;
      v5[3] = 0;
      v5[4] = 0;
      *((_DWORD *)v5 + 10) = 1;
      _InterlockedIncrement(&g_cRefCount);
      memset(&pvarg, 0, sizeof(pvarg));
      pvarg.vt = 13;
      Service = (*(__int64 (__fastcall **)(_QWORD *, GUID *, CY *))*v5)(
                  v5,
                  &GUID_00000000_0000_0000_c000_000000000046,
                  &pvarg.cyVal);
      if ( Service >= 0 )
      {
        Service = (*(__int64 (__fastcall **)(__int64, const WCHAR *, VARIANTARG *))(*(_QWORD *)v9 + 32LL))(
                    v9,
                    L"FontSettingsCore",
                    &pvarg);
        VariantClear(&pvarg);
      }
      (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
    }
    else
    {
      Service = -2147024882;
    }
  }
  ATL::CComPtr<IPropertyBag>::~CComPtr<IPropertyBag>(&v9);
  return (unsigned int)Service;
}

```

## disassembly

```asm
0x18001fba0  mov     [rsp+arg_8], rbx
0x18001fba5  push    rdi
0x18001fba6  sub     rsp, 40h
0x18001fbaa  mov     r10, rcx
0x18001fbad  lea     rcx, [rsp+48h+arg_0]
0x18001fbb2  call    ??0?$CComPtr@UIPropertyBag@@@ATL@@QEAA@XZ; ATL::CComPtr<IPropertyBag>::CComPtr<IPropertyBag>(void)
0x18001fbb7  lea     rcx, [rsp+48h+arg_0]; this
0x18001fbbc  call    ?QueryRasterFont@CFontRegValue_Raster@@UEAAPEAV1@XZ; CFontRegValue_Raster::QueryRasterFont(void)
0x18001fbc1  mov     rcx, [r10+10h]; punk
0x18001fbc5  lea     r8, _GUID_55272a00_42cb_11ce_8135_00aa004bb851; riid
0x18001fbcc  mov     r9, rax; ppvOut
0x18001fbcf  lea     rdx, SID_PerNamespaceIDPropertyBag; guidService
0x18001fbd6  call    cs:__imp_IUnknown_QueryService
0x18001fbdc  mov     edi, eax
0x18001fbde  test    eax, eax
0x18001fbe0  js      loc_18001FCAD
0x18001fbe6  mov     ecx, 30h ; '0'; this
0x18001fbeb  call    ?HAllocAndZero@DirectUI@@YAPEAX_K@Z; DirectUI::HAllocAndZero(unsigned __int64)
0x18001fbf0  mov     rbx, rax
0x18001fbf3  test    rax, rax
0x18001fbf6  jz      loc_18001FCA8
0x18001fbfc  lea     rax, ??_7CFontSettingsCore@@6B@; const CFontSettingsCore::`vftable'
0x18001fc03  mov     qword ptr [rbx+8], 0
0x18001fc0b  mov     [rbx], rax
0x18001fc0e  mov     qword ptr [rbx+10h], 0
0x18001fc16  mov     qword ptr [rbx+18h], 0
0x18001fc1e  mov     qword ptr [rbx+20h], 0
0x18001fc26  mov     dword ptr [rbx+28h], 1
0x18001fc2d  lock inc cs:?g_cRefCount@@3JA; long g_cRefCount
0x18001fc34  xor     eax, eax
0x18001fc36  lea     r8, [rsp+48h+pvarg+8]
0x18001fc3b  mov     qword ptr [rsp+48h+pvarg+10h], rax
0x18001fc40  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001fc47  xorps   xmm0, xmm0
0x18001fc4a  mov     eax, 0Dh
0x18001fc4f  movups  xmmword ptr [rsp+20h], xmm0
0x18001fc54  mov     word ptr [rsp+48h+pvarg], ax
0x18001fc59  mov     rcx, rbx
0x18001fc5c  mov     rax, [rbx]
0x18001fc5f  mov     rax, [rax]
0x18001fc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc67  mov     edi, eax
0x18001fc69  test    eax, eax
0x18001fc6b  js      short loc_18001FC97
0x18001fc6d  mov     rcx, [rsp+48h+arg_0]
0x18001fc72  lea     r8, [rsp+48h+pvarg]
0x18001fc77  lea     rdx, propName; "FontSettingsCore"
0x18001fc7e  mov     rax, [rcx]
0x18001fc81  mov     rax, [rax+20h]
0x18001fc85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc8a  lea     rcx, [rsp+48h+pvarg]; pvarg
0x18001fc8f  mov     edi, eax
0x18001fc91  call    cs:__imp_VariantClear
0x18001fc97  mov     rax, [rbx]
0x18001fc9a  mov     rcx, rbx
0x18001fc9d  mov     rax, [rax+10h]
0x18001fca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fca6  jmp     short loc_18001FCAD
0x18001fca8  mov     edi, 8007000Eh
0x18001fcad  lea     rcx, [rsp+48h+arg_0]
0x18001fcb2  call    ??1?$CComPtr@UIPropertyBag@@@ATL@@QEAA@XZ; ATL::CComPtr<IPropertyBag>::~CComPtr<IPropertyBag>(void)
0x18001fcb7  mov     rbx, [rsp+48h+arg_8]
0x18001fcbc  mov     eax, edi
0x18001fcbe  add     rsp, 40h
0x18001fcc2  pop     rdi
0x18001fcc3  retn
```
