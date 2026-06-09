# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x1800299e0`
- end: `0x180029c76`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `662`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180029914`
- `0x180029ce4`
- `0x180029ed8`

## callees

- `0x18001f27c`
- `0x180025934`
- `0x180025988`
- `0x180026edc`
- `0x180028538`
- `0x18002926c`
- `0x1800299e0`
- `0x180029f7c`
- `0x18002a068`
- `0x180081750`
- `0x180088010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLib` at `0x180029ac6`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180029ac6`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180029af4`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180029af4`
- `KERNEL32!GetModuleFileNameW` at `0x180029a9d`
- `KERNEL32!GetModuleFileNameW` at `0x180029a9d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // edi
  DWORD ModuleFileNameW; // eax
  int (__fastcall ***v7)(_QWORD, GUID *, _QWORD); // rcx
  __int64 v8; // rsi
  __int64 v9; // rax
  struct ITypeInfo *v10; // rdx
  int (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // [rsp+30h] [rbp-D0h] BYREF
  int (__fastcall ***v12)(_QWORD, GUID *, _QWORD); // [rsp+38h] [rbp-C8h] BYREF
  void (__fastcall ***v13)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
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
            v11 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v12;
            if ( v12 )
            {
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v12)[1])(v12);
              v7 = v12;
            }
            v13 = 0;
            if ( (**v7)(v7, &GUID_00020412_0000_0000_c000_000000000046, &v13) >= 0
              && !(unsigned __int8)ATL::CComPtrBase<ITypeInfo>::IsEqualObject(&v11, v13) )
            {
              v8 = (__int64)v11;
              v11 = 0;
              if ( v13 )
                (**v13)(v13, &GUID_00020401_0000_0000_c000_000000000046, (__int64 *)&v11);
              if ( v8 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            }
            v9 = (__int64)v11;
            v11 = 0;
            *((_QWORD *)this + 3) = v9;
            ATL::AtlModuleAddTermFunc(
              (struct ATL::_ATL_MODULE70 *)(((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64)
                                          & ((unsigned __int64)ATL::_pAtlModule + 8)),
              (void (*)(unsigned __int64))((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64),
              (unsigned __int64)this);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
          }
          ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v12);
        }
        goto LABEL_26;
      }
      NameCache = -2147467259;
      ModuleFileNameW = GetModuleFileNameW((HMODULE)hInstance, Filename, 0x104u);
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
0x1800299e0  mov     [rsp-8+arg_10], rbx
0x1800299e5  push    rbp
0x1800299e6  push    rsi
0x1800299e7  push    rdi
0x1800299e8  lea     rbp, [rsp-180h]
0x1800299f0  sub     rsp, 280h
0x1800299f7  mov     rax, cs:__security_cookie
0x1800299fe  xor     rax, rsp
0x180029a01  mov     [rbp+190h+var_20], rax
0x180029a08  mov     esi, edx
0x180029a0a  mov     rbx, rcx
0x180029a0d  cmp     qword ptr [rcx+18h], 0
0x180029a12  jz      short loc_180029A22
0x180029a14  cmp     qword ptr [rcx+28h], 0
0x180029a19  jz      short loc_180029A22
0x180029a1b  xor     eax, eax
0x180029a1d  jmp     loc_180029C54
0x180029a22  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180029a29  add     rax, 18h
0x180029a2d  mov     [rsp+290h+var_240], rax
0x180029a32  mov     [rsp+290h+var_238], 0
0x180029a37  lea     rcx, [rsp+290h+var_240]
0x180029a3c  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x180029a41  mov     edi, eax
0x180029a43  test    eax, eax
0x180029a45  js      loc_180029C48
0x180029a4b  cmp     qword ptr [rbx+18h], 0
0x180029a50  jnz     loc_180029C2C
0x180029a56  mov     [rsp+290h+pptlib], 0
0x180029a5f  mov     rdx, [rbx+8]
0x180029a63  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; _GUID ATL::CAtlModule::m_libid
0x180029a6a  call    InlineIsEqualGUID
0x180029a6f  test    eax, eax
0x180029a71  jz      short loc_180029ADA
0x180029a73  mov     eax, 0FFFFh
0x180029a78  cmp     [rbx+10h], ax
0x180029a7c  jnz     short loc_180029ADA
0x180029a7e  cmp     [rbx+12h], ax
0x180029a82  jnz     short loc_180029ADA
0x180029a84  mov     edi, 80004005h
0x180029a89  mov     esi, 104h
0x180029a8e  mov     r8d, esi; nSize
0x180029a91  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180029a96  mov     rcx, cs:hInstance; hModule
0x180029a9d  call    cs:__imp_GetModuleFileNameW
0x180029aa3  test    eax, eax
0x180029aa5  jz      loc_180029C2E
0x180029aab  cmp     eax, esi
0x180029aad  jz      loc_180029C2E
0x180029ab3  mov     [rsp+290h+var_258], 0
0x180029abc  lea     rdx, [rsp+290h+pptlib]; pptlib
0x180029ac1  lea     rcx, [rsp+290h+Filename]; szFile
0x180029ac6  call    cs:__imp_LoadTypeLib
0x180029acc  mov     edi, eax
0x180029ace  lea     rcx, [rsp+290h+var_258]
0x180029ad3  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180029ad8  jmp     short loc_180029AFC
0x180029ada  lea     rax, [rsp+290h+pptlib]
0x180029adf  mov     [rsp+290h+var_270], rax; pptlib
0x180029ae4  mov     r9d, esi; lcid
0x180029ae7  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x180029aec  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x180029af0  mov     rcx, [rbx+8]; rguid
0x180029af4  call    cs:__imp_LoadRegTypeLib
0x180029afa  mov     edi, eax
0x180029afc  test    edi, edi
0x180029afe  js      loc_180029C2E
0x180029b04  mov     [rsp+290h+var_258], 0
0x180029b0d  mov     rcx, [rsp+290h+pptlib]
0x180029b12  mov     rax, [rcx]
0x180029b15  lea     r8, [rsp+290h+var_258]
0x180029b1a  mov     rdx, [rbx]
0x180029b1d  mov     rax, [rax+30h]
0x180029b21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b26  mov     edi, eax
0x180029b28  test    eax, eax
0x180029b2a  js      loc_180029C0E
0x180029b30  mov     rcx, [rsp+290h+var_258]
0x180029b35  mov     [rsp+290h+var_260], rcx
0x180029b3a  test    rcx, rcx
0x180029b3d  jz      short loc_180029B50
0x180029b3f  mov     rax, [rcx]
0x180029b42  mov     rax, [rax+8]
0x180029b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b4b  mov     rcx, [rsp+290h+var_258]
0x180029b50  mov     [rsp+290h+var_250], 0
0x180029b59  mov     rax, [rcx]
0x180029b5c  lea     r8, [rsp+290h+var_250]
0x180029b61  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x180029b68  mov     rax, [rax]
0x180029b6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b70  test    eax, eax
0x180029b72  js      short loc_180029BCA
0x180029b74  mov     rdx, [rsp+290h+var_250]
0x180029b79  lea     rcx, [rsp+290h+var_260]
0x180029b7e  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x180029b83  test    al, al
0x180029b85  jnz     short loc_180029BCA
0x180029b87  mov     rcx, [rsp+290h+var_250]
0x180029b8c  mov     rsi, [rsp+290h+var_260]
0x180029b91  mov     [rsp+290h+var_260], 0
0x180029b9a  test    rcx, rcx
0x180029b9d  jz      short loc_180029BB6
0x180029b9f  mov     rax, [rcx]
0x180029ba2  lea     r8, [rsp+290h+var_260]
0x180029ba7  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x180029bae  mov     rax, [rax]
0x180029bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bb6  test    rsi, rsi
0x180029bb9  jz      short loc_180029BCA
0x180029bbb  mov     rax, [rsi]
0x180029bbe  mov     rcx, rsi
0x180029bc1  mov     rax, [rax+10h]
0x180029bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bca  mov     rax, [rsp+290h+var_260]
0x180029bcf  mov     [rsp+290h+var_260], 0
0x180029bd8  mov     [rbx+18h], rax
0x180029bdc  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180029be3  lea     rcx, [rax+8]
0x180029be7  neg     rax
0x180029bea  sbb     rdx, rdx; void (*)(unsigned __int64)
0x180029bed  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x180029bf0  mov     r8, rbx; unsigned __int64
0x180029bf3  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x180029bf8  nop
0x180029bf9  lea     rcx, [rsp+290h+var_250]
0x180029bfe  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180029c03  nop
0x180029c04  lea     rcx, [rsp+290h+var_260]
0x180029c09  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180029c0e  mov     rcx, [rsp+290h+pptlib]
0x180029c13  mov     rax, [rcx]
0x180029c16  mov     rax, [rax+10h]
0x180029c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c1f  nop
0x180029c20  lea     rcx, [rsp+290h+var_258]
0x180029c25  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180029c2a  jmp     short loc_180029C2E
0x180029c2c  xor     edi, edi
0x180029c2e  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x180029c32  test    rdx, rdx
0x180029c35  jz      short loc_180029C48
0x180029c37  cmp     qword ptr [rbx+28h], 0
0x180029c3c  jnz     short loc_180029C48
0x180029c3e  mov     rcx, rbx; this
0x180029c41  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x180029c46  mov     edi, eax
0x180029c48  lea     rcx, [rsp+290h+var_240]
0x180029c4d  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180029c52  mov     eax, edi
0x180029c54  mov     rcx, [rbp+190h+var_20]
0x180029c5b  xor     rcx, rsp; StackCookie
0x180029c5e  call    __security_check_cookie
0x180029c63  mov     rbx, [rsp+290h+arg_10]
0x180029c6b  add     rsp, 280h
0x180029c72  pop     rdi
0x180029c73  pop     rsi
0x180029c74  pop     rbp
0x180029c75  retn
```
