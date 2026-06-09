# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x18001b910`
- end: `0x18001bba3`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `659`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18001a314`
- `0x18001bc44`
- `0x18001bf78`

## callees

- `0x180006d40`
- `0x18000e198`
- `0x18000ea20`
- `0x18000f928`
- `0x180011024`
- `0x1800171ac`
- `0x18001b910`
- `0x18001c030`
- `0x18001c0c4`
- `0x180049880`
- `0x18004a010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLib` at `0x18001b9f6`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18001b9f6`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18001ba24`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18001ba24`
- `KERNEL32!GetModuleFileNameW` at `0x18001b9cd`
- `KERNEL32!GetModuleFileNameW` at `0x18001b9cd`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // edi
  const struct _GUID *v6; // rdx
  DWORD ModuleFileNameW; // eax
  __int64 v8; // rdx
  int (__fastcall ***v9)(_QWORD, GUID *, _QWORD); // rcx
  __int64 v10; // rsi
  struct ITypeInfo *v11; // rdx
  int (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // [rsp+30h] [rbp-D0h] BYREF
  int (__fastcall ***v13)(_QWORD, GUID *, _QWORD); // [rsp+38h] [rbp-C8h] BYREF
  void (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
  ITypeLib *pptlib; // [rsp+48h] [rbp-B8h] BYREF
  char *v16; // [rsp+50h] [rbp-B0h] BYREF
  char v17; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v17 = 0;
  v16 = (char *)ATL::_pAtlModule + 24;
  NameCache = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v16);
  if ( NameCache >= 0 )
  {
    if ( *((_QWORD *)this + 3) )
    {
      NameCache = 0;
    }
    else
    {
      v6 = (const struct _GUID *)*((_QWORD *)this + 1);
      pptlib = 0;
      if ( !(unsigned int)InlineIsEqualGUID(&ATL::CAtlModule::m_libid, v6)
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
          v8 = *(_QWORD *)this;
          v13 = 0;
          NameCache = ((__int64 (__fastcall *)(ITypeLib *, __int64, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                        pptlib,
                        v8,
                        &v13);
          if ( NameCache >= 0 )
          {
            v9 = v13;
            v12 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v13;
            if ( v13 )
            {
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v13)[1])(v13);
              v9 = v13;
            }
            v14 = 0;
            if ( (**v9)(v9, &GUID_00020412_0000_0000_c000_000000000046, &v14) >= 0
              && !(unsigned __int8)ATL::CComPtrBase<ITypeInfo>::IsEqualObject(&v12, v14) )
            {
              v10 = (__int64)v12;
              v12 = 0;
              if ( v14 )
                (**v14)(v14, &GUID_00020401_0000_0000_c000_000000000046, (__int64 *)&v12);
              if ( v10 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
            }
            *((_QWORD *)this + 3) = v12;
            v12 = 0;
            ATL::AtlModuleAddTermFunc(
              (struct ATL::_ATL_MODULE70 *)(((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64)
                                          & ((unsigned __int64)ATL::_pAtlModule + 8)),
              (void (*)(unsigned __int64))((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64),
              (unsigned __int64)this);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v12);
          }
          ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
        }
        goto LABEL_26;
      }
      NameCache = -2147467259;
      ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
      if ( ModuleFileNameW && ModuleFileNameW != 260 )
      {
        v13 = 0;
        NameCache = LoadTypeLib(Filename, &pptlib);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v13);
        goto LABEL_13;
      }
    }
LABEL_26:
    v11 = (struct ITypeInfo *)*((_QWORD *)this + 3);
    if ( v11 )
    {
      if ( !*((_QWORD *)this + 5) )
        NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v11);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(&v16);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x18001b910  mov     [rsp-8+arg_10], rbx
0x18001b915  push    rbp
0x18001b916  push    rsi
0x18001b917  push    rdi
0x18001b918  lea     rbp, [rsp-180h]
0x18001b920  sub     rsp, 280h
0x18001b927  mov     rax, cs:__security_cookie
0x18001b92e  xor     rax, rsp
0x18001b931  mov     [rbp+190h+var_20], rax
0x18001b938  cmp     qword ptr [rcx+18h], 0
0x18001b93d  mov     esi, edx
0x18001b93f  mov     rbx, rcx
0x18001b942  jz      short loc_18001B952
0x18001b944  cmp     qword ptr [rcx+28h], 0
0x18001b949  jz      short loc_18001B952
0x18001b94b  xor     eax, eax
0x18001b94d  jmp     loc_18001BB81
0x18001b952  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001b959  lea     rcx, [rsp+290h+var_240]
0x18001b95e  add     rax, 18h
0x18001b962  mov     [rsp+290h+var_238], 0
0x18001b967  mov     [rsp+290h+var_240], rax
0x18001b96c  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18001b971  mov     edi, eax
0x18001b973  test    eax, eax
0x18001b975  js      loc_18001BB75
0x18001b97b  cmp     qword ptr [rbx+18h], 0
0x18001b980  jnz     loc_18001BB59
0x18001b986  mov     rdx, [rbx+8]; struct _GUID *
0x18001b98a  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; struct _GUID *
0x18001b991  mov     [rsp+290h+pptlib], 0
0x18001b99a  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18001b99f  test    eax, eax
0x18001b9a1  jz      short loc_18001BA0A
0x18001b9a3  mov     eax, 0FFFFh
0x18001b9a8  cmp     [rbx+10h], ax
0x18001b9ac  jnz     short loc_18001BA0A
0x18001b9ae  cmp     [rbx+12h], ax
0x18001b9b2  jnz     short loc_18001BA0A
0x18001b9b4  mov     rcx, cs:hModule; hModule
0x18001b9bb  lea     rdx, [rsp+290h+Filename]; lpFilename
0x18001b9c0  mov     esi, 104h
0x18001b9c5  mov     edi, 80004005h
0x18001b9ca  mov     r8d, esi; nSize
0x18001b9cd  call    cs:__imp_GetModuleFileNameW
0x18001b9d3  test    eax, eax
0x18001b9d5  jz      loc_18001BB5B
0x18001b9db  cmp     eax, esi
0x18001b9dd  jz      loc_18001BB5B
0x18001b9e3  lea     rdx, [rsp+290h+pptlib]; pptlib
0x18001b9e8  mov     [rsp+290h+var_258], 0
0x18001b9f1  lea     rcx, [rsp+290h+Filename]; szFile
0x18001b9f6  call    cs:__imp_LoadTypeLib
0x18001b9fc  lea     rcx, [rsp+290h+var_258]
0x18001ba01  mov     edi, eax
0x18001ba03  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001ba08  jmp     short loc_18001BA2C
0x18001ba0a  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x18001ba0f  lea     rax, [rsp+290h+pptlib]
0x18001ba14  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x18001ba18  mov     r9d, esi; lcid
0x18001ba1b  mov     rcx, [rbx+8]; rguid
0x18001ba1f  mov     [rsp+290h+var_270], rax; pptlib
0x18001ba24  call    cs:__imp_LoadRegTypeLib
0x18001ba2a  mov     edi, eax
0x18001ba2c  test    edi, edi
0x18001ba2e  js      loc_18001BB5B
0x18001ba34  mov     rcx, [rsp+290h+pptlib]
0x18001ba39  lea     r8, [rsp+290h+var_258]
0x18001ba3e  mov     rdx, [rbx]
0x18001ba41  mov     [rsp+290h+var_258], 0
0x18001ba4a  mov     rax, [rcx]
0x18001ba4d  mov     rax, [rax+30h]
0x18001ba51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba56  mov     edi, eax
0x18001ba58  test    eax, eax
0x18001ba5a  js      loc_18001BB3C
0x18001ba60  mov     rcx, [rsp+290h+var_258]
0x18001ba65  mov     [rsp+290h+var_260], rcx
0x18001ba6a  test    rcx, rcx
0x18001ba6d  jz      short loc_18001BA80
0x18001ba6f  mov     rax, [rcx]
0x18001ba72  mov     rax, [rax+8]
0x18001ba76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba7b  mov     rcx, [rsp+290h+var_258]
0x18001ba80  mov     [rsp+290h+var_250], 0
0x18001ba89  lea     r8, [rsp+290h+var_250]
0x18001ba8e  mov     rax, [rcx]
0x18001ba91  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x18001ba98  mov     rax, [rax]
0x18001ba9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001baa0  test    eax, eax
0x18001baa2  js      short loc_18001BAFA
0x18001baa4  mov     rdx, [rsp+290h+var_250]
0x18001baa9  lea     rcx, [rsp+290h+var_260]
0x18001baae  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x18001bab3  test    al, al
0x18001bab5  jnz     short loc_18001BAFA
0x18001bab7  mov     rcx, [rsp+290h+var_250]
0x18001babc  mov     rsi, [rsp+290h+var_260]
0x18001bac1  mov     [rsp+290h+var_260], 0
0x18001baca  test    rcx, rcx
0x18001bacd  jz      short loc_18001BAE6
0x18001bacf  mov     rax, [rcx]
0x18001bad2  lea     r8, [rsp+290h+var_260]
0x18001bad7  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x18001bade  mov     rax, [rax]
0x18001bae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bae6  test    rsi, rsi
0x18001bae9  jz      short loc_18001BAFA
0x18001baeb  mov     rax, [rsi]
0x18001baee  mov     rcx, rsi
0x18001baf1  mov     rax, [rax+10h]
0x18001baf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bafa  mov     rax, [rsp+290h+var_260]
0x18001baff  mov     r8, rbx; unsigned __int64
0x18001bb02  mov     [rbx+18h], rax
0x18001bb06  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001bb0d  mov     [rsp+290h+var_260], 0
0x18001bb16  lea     rcx, [rax+8]
0x18001bb1a  neg     rax
0x18001bb1d  sbb     rdx, rdx; void (*)(unsigned __int64)
0x18001bb20  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x18001bb23  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x18001bb28  lea     rcx, [rsp+290h+var_250]
0x18001bb2d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001bb32  lea     rcx, [rsp+290h+var_260]
0x18001bb37  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001bb3c  mov     rcx, [rsp+290h+pptlib]
0x18001bb41  mov     rax, [rcx]
0x18001bb44  mov     rax, [rax+10h]
0x18001bb48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bb4d  lea     rcx, [rsp+290h+var_258]
0x18001bb52  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001bb57  jmp     short loc_18001BB5B
0x18001bb59  xor     edi, edi
0x18001bb5b  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x18001bb5f  test    rdx, rdx
0x18001bb62  jz      short loc_18001BB75
0x18001bb64  cmp     qword ptr [rbx+28h], 0
0x18001bb69  jnz     short loc_18001BB75
0x18001bb6b  mov     rcx, rbx; this
0x18001bb6e  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x18001bb73  mov     edi, eax
0x18001bb75  lea     rcx, [rsp+290h+var_240]
0x18001bb7a  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001bb7f  mov     eax, edi
0x18001bb81  mov     rcx, [rbp+190h+var_20]
0x18001bb88  xor     rcx, rsp; StackCookie
0x18001bb8b  call    __security_check_cookie
0x18001bb90  mov     rbx, [rsp+290h+arg_10]
0x18001bb98  add     rsp, 280h
0x18001bb9f  pop     rdi
0x18001bba0  pop     rsi
0x18001bba1  pop     rbp
0x18001bba2  retn
```
