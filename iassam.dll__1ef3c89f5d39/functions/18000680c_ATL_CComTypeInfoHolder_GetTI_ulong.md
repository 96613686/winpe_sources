# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x18000680c`
- end: `0x180006aa2`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `662`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800066f4`
- `0x180006ae4`
- `0x180006ec8`

## callees

- `0x180002b00`
- `0x180002b9c`
- `0x1800030b8`
- `0x1800047a0`
- `0x18000680c`
- `0x180006f6c`
- `0x180007000`
- `0x18000726c`
- `0x18000a138`
- `0x18002b4a0`
- `0x18002e010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1800068c9`
- `KERNEL32!GetModuleFileNameW` at `0x1800068c9`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1800068f2`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1800068f2`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180006920`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180006920`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // edi
  DWORD ModuleFileNameW; // eax
  int (__fastcall ***v7)(_QWORD, GUID *, _QWORD); // rcx
  int (__fastcall ***v8)(_QWORD, GUID *, _QWORD); // rsi
  int (__fastcall ***v9)(_QWORD, GUID *, _QWORD); // rax
  struct ITypeInfo *v10; // rdx
  int (__fastcall ***v11)(_QWORD, GUID *, _QWORD); // [rsp+30h] [rbp-D0h] BYREF
  int (__fastcall ***v12)(_QWORD, GUID *, _QWORD); // [rsp+38h] [rbp-C8h] BYREF
  void (__fastcall ***v13)(_QWORD, GUID *, _QWORD *); // [rsp+40h] [rbp-C0h] BYREF
  ITypeLib *pptlib; // [rsp+48h] [rbp-B8h] BYREF
  char *v15; // [rsp+50h] [rbp-B0h] BYREF
  char v16; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v15 = (char *)ATL::_pAtlModule + 24;
  v16 = 0;
  NameCache = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v15);
  if ( NameCache >= 0 )
  {
    if ( *((_QWORD *)this + 3) )
    {
      NameCache = 0;
    }
    else
    {
      pptlib = 0;
      if ( !(unsigned int)InlineIsEqualGUID(&ATL::CAtlModule::m_libid, *((_QWORD *)this + 1))
        || *((_WORD *)this + 8) != 0xFFFF
        || *((_WORD *)this + 9) != 0xFFFF )
      {
        NameCache = LoadRegTypeLib(
                      *((const GUID *const *)this + 1),
                      *((_WORD *)this + 8),
                      *((_WORD *)this + 9),
                      lcid,
                      &pptlib);
LABEL_13:
        if ( NameCache >= 0 )
        {
          v12 = 0;
          NameCache = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                        pptlib,
                        *(_QWORD *)this,
                        &v12);
          if ( NameCache >= 0 )
          {
            v7 = v12;
            v11 = v12;
            if ( v12 )
            {
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v12)[1])(v12);
              v7 = v12;
            }
            v13 = 0;
            if ( (**v7)(v7, &GUID_00020412_0000_0000_c000_000000000046, &v13) >= 0
              && !(unsigned __int8)ATL::CComPtrBase<ITypeInfo>::IsEqualObject(&v11, v13) )
            {
              v8 = v11;
              v11 = 0;
              if ( v13 )
                (**v13)(v13, &GUID_00020401_0000_0000_c000_000000000046, &v11);
              if ( v8 )
                ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v8)[2])(v8);
            }
            v9 = v11;
            v11 = 0;
            *((_QWORD *)this + 3) = v9;
            ATL::AtlModuleAddTermFunc(
              (struct ATL::_ATL_MODULE70 *)(((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64)
                                          & ((unsigned __int64)ATL::_pAtlModule + 8)),
              (void (*)(unsigned __int64))((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64),
              (unsigned __int64)this);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v13);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v11);
          }
          ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
        }
        goto LABEL_26;
      }
      NameCache = -2147467259;
      ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
      if ( ModuleFileNameW && ModuleFileNameW != 260 )
      {
        v12 = 0;
        NameCache = LoadTypeLib(Filename, &pptlib);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v12);
        goto LABEL_13;
      }
    }
LABEL_26:
    v10 = (struct ITypeInfo *)*((_QWORD *)this + 3);
    if ( v10 )
    {
      if ( !*((_QWORD *)this + 5) )
        NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v10);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v15);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x18000680c  mov     [rsp-8+arg_10], rbx
0x180006811  push    rbp
0x180006812  push    rsi
0x180006813  push    rdi
0x180006814  lea     rbp, [rsp-180h]
0x18000681c  sub     rsp, 280h
0x180006823  mov     rax, cs:__security_cookie
0x18000682a  xor     rax, rsp
0x18000682d  mov     [rbp+190h+var_20], rax
0x180006834  mov     esi, edx
0x180006836  mov     rbx, rcx
0x180006839  cmp     qword ptr [rcx+18h], 0
0x18000683e  jz      short loc_18000684E
0x180006840  cmp     qword ptr [rcx+28h], 0
0x180006845  jz      short loc_18000684E
0x180006847  xor     eax, eax
0x180006849  jmp     loc_180006A80
0x18000684e  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006855  add     rax, 18h
0x180006859  mov     [rsp+290h+var_240], rax
0x18000685e  mov     [rsp+290h+var_238], 0
0x180006863  lea     rcx, [rsp+290h+var_240]
0x180006868  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000686d  mov     edi, eax
0x18000686f  test    eax, eax
0x180006871  js      loc_180006A74
0x180006877  cmp     qword ptr [rbx+18h], 0
0x18000687c  jnz     loc_180006A58
0x180006882  mov     [rsp+290h+pptlib], 0
0x18000688b  mov     rdx, [rbx+8]
0x18000688f  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; _GUID ATL::CAtlModule::m_libid
0x180006896  call    InlineIsEqualGUID
0x18000689b  test    eax, eax
0x18000689d  jz      short loc_180006906
0x18000689f  mov     eax, 0FFFFh
0x1800068a4  cmp     [rbx+10h], ax
0x1800068a8  jnz     short loc_180006906
0x1800068aa  cmp     [rbx+12h], ax
0x1800068ae  jnz     short loc_180006906
0x1800068b0  mov     edi, 80004005h
0x1800068b5  mov     esi, 104h
0x1800068ba  mov     r8d, esi; nSize
0x1800068bd  lea     rdx, [rsp+290h+Filename]; lpFilename
0x1800068c2  mov     rcx, cs:hInstance; hModule
0x1800068c9  call    cs:__imp_GetModuleFileNameW
0x1800068cf  test    eax, eax
0x1800068d1  jz      loc_180006A5A
0x1800068d7  cmp     eax, esi
0x1800068d9  jz      loc_180006A5A
0x1800068df  mov     [rsp+290h+var_258], 0
0x1800068e8  lea     rdx, [rsp+290h+pptlib]; pptlib
0x1800068ed  lea     rcx, [rsp+290h+Filename]; szFile
0x1800068f2  call    cs:__imp_LoadTypeLib
0x1800068f8  mov     edi, eax
0x1800068fa  lea     rcx, [rsp+290h+var_258]
0x1800068ff  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006904  jmp     short loc_180006928
0x180006906  lea     rax, [rsp+290h+pptlib]
0x18000690b  mov     [rsp+290h+var_270], rax; pptlib
0x180006910  mov     r9d, esi; lcid
0x180006913  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x180006918  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x18000691c  mov     rcx, [rbx+8]; rguid
0x180006920  call    cs:__imp_LoadRegTypeLib
0x180006926  mov     edi, eax
0x180006928  test    edi, edi
0x18000692a  js      loc_180006A5A
0x180006930  mov     [rsp+290h+var_258], 0
0x180006939  mov     rcx, [rsp+290h+pptlib]
0x18000693e  mov     rax, [rcx]
0x180006941  lea     r8, [rsp+290h+var_258]
0x180006946  mov     rdx, [rbx]
0x180006949  mov     rax, [rax+30h]
0x18000694d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006952  mov     edi, eax
0x180006954  test    eax, eax
0x180006956  js      loc_180006A3A
0x18000695c  mov     rcx, [rsp+290h+var_258]
0x180006961  mov     [rsp+290h+var_260], rcx
0x180006966  test    rcx, rcx
0x180006969  jz      short loc_18000697C
0x18000696b  mov     rax, [rcx]
0x18000696e  mov     rax, [rax+8]
0x180006972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006977  mov     rcx, [rsp+290h+var_258]
0x18000697c  mov     [rsp+290h+var_250], 0
0x180006985  mov     rax, [rcx]
0x180006988  lea     r8, [rsp+290h+var_250]
0x18000698d  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x180006994  mov     rax, [rax]
0x180006997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000699c  test    eax, eax
0x18000699e  js      short loc_1800069F6
0x1800069a0  mov     rdx, [rsp+290h+var_250]
0x1800069a5  lea     rcx, [rsp+290h+var_260]
0x1800069aa  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x1800069af  test    al, al
0x1800069b1  jnz     short loc_1800069F6
0x1800069b3  mov     rcx, [rsp+290h+var_250]
0x1800069b8  mov     rsi, [rsp+290h+var_260]
0x1800069bd  mov     [rsp+290h+var_260], 0
0x1800069c6  test    rcx, rcx
0x1800069c9  jz      short loc_1800069E2
0x1800069cb  mov     rax, [rcx]
0x1800069ce  lea     r8, [rsp+290h+var_260]
0x1800069d3  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x1800069da  mov     rax, [rax]
0x1800069dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069e2  test    rsi, rsi
0x1800069e5  jz      short loc_1800069F6
0x1800069e7  mov     rax, [rsi]
0x1800069ea  mov     rcx, rsi
0x1800069ed  mov     rax, [rax+10h]
0x1800069f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069f6  mov     rax, [rsp+290h+var_260]
0x1800069fb  mov     [rsp+290h+var_260], 0
0x180006a04  mov     [rbx+18h], rax
0x180006a08  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006a0f  lea     rcx, [rax+8]
0x180006a13  neg     rax
0x180006a16  sbb     rdx, rdx; void (*)(unsigned __int64)
0x180006a19  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x180006a1c  mov     r8, rbx; unsigned __int64
0x180006a1f  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x180006a24  nop
0x180006a25  lea     rcx, [rsp+290h+var_250]
0x180006a2a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006a2f  nop
0x180006a30  lea     rcx, [rsp+290h+var_260]
0x180006a35  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006a3a  mov     rcx, [rsp+290h+pptlib]
0x180006a3f  mov     rax, [rcx]
0x180006a42  mov     rax, [rax+10h]
0x180006a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a4b  nop
0x180006a4c  lea     rcx, [rsp+290h+var_258]
0x180006a51  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006a56  jmp     short loc_180006A5A
0x180006a58  xor     edi, edi
0x180006a5a  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x180006a5e  test    rdx, rdx
0x180006a61  jz      short loc_180006A74
0x180006a63  cmp     qword ptr [rbx+28h], 0
0x180006a68  jnz     short loc_180006A74
0x180006a6a  mov     rcx, rbx; this
0x180006a6d  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x180006a72  mov     edi, eax
0x180006a74  lea     rcx, [rsp+290h+var_240]
0x180006a79  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180006a7e  mov     eax, edi
0x180006a80  mov     rcx, [rbp+190h+var_20]
0x180006a87  xor     rcx, rsp; StackCookie
0x180006a8a  call    __security_check_cookie
0x180006a8f  mov     rbx, [rsp+290h+arg_10]
0x180006a97  add     rsp, 280h
0x180006a9e  pop     rdi
0x180006a9f  pop     rsi
0x180006aa0  pop     rbp
0x180006aa1  retn
```
