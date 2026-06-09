# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x18000b1d4`
- end: `0x18000b46a`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `662`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000b0d4`
- `0x18000b484`
- `0x18000ccb8`

## callees

- `0x180009b30`
- `0x18000adb0`
- `0x18000ade0`
- `0x18000af20`
- `0x18000b1d4`
- `0x18000cddc`
- `0x18000ce8c`
- `0x18000d0f8`
- `0x18000dc24`
- `0x18002e230`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18000b291`
- `KERNEL32!GetModuleFileNameW` at `0x18000b291`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000b2ba`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18000b2ba`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000b2e8`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18000b2e8`

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
0x18000b1d4  mov     [rsp-8+arg_10], rbx
0x18000b1d9  push    rbp
0x18000b1da  push    rsi
0x18000b1db  push    rdi
0x18000b1dc  lea     rbp, [rsp-180h]
0x18000b1e4  sub     rsp, 280h
0x18000b1eb  mov     rax, cs:__security_cookie
0x18000b1f2  xor     rax, rsp
0x18000b1f5  mov     [rbp+190h+var_20], rax
0x18000b1fc  mov     esi, edx
0x18000b1fe  mov     rbx, rcx
0x18000b201  cmp     qword ptr [rcx+18h], 0
0x18000b206  jz      short loc_18000B216
0x18000b208  cmp     qword ptr [rcx+28h], 0
0x18000b20d  jz      short loc_18000B216
0x18000b20f  xor     eax, eax
0x18000b211  jmp     loc_18000B448
0x18000b216  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b21d  add     rax, 18h
0x18000b221  mov     [rsp+290h+var_240], rax
0x18000b226  mov     [rsp+290h+var_238], 0
0x18000b22b  lea     rcx, [rsp+290h+var_240]
0x18000b230  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18000b235  mov     edi, eax
0x18000b237  test    eax, eax
0x18000b239  js      loc_18000B43C
0x18000b23f  cmp     qword ptr [rbx+18h], 0
0x18000b244  jnz     loc_18000B420
0x18000b24a  mov     [rsp+290h+pptlib], 0
0x18000b253  mov     rdx, [rbx+8]
0x18000b257  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; _GUID ATL::CAtlModule::m_libid
0x18000b25e  call    InlineIsEqualGUID
0x18000b263  test    eax, eax
0x18000b265  jz      short loc_18000B2CE
0x18000b267  mov     eax, 0FFFFh
0x18000b26c  cmp     [rbx+10h], ax
0x18000b270  jnz     short loc_18000B2CE
0x18000b272  cmp     [rbx+12h], ax
0x18000b276  jnz     short loc_18000B2CE
0x18000b278  mov     edi, 80004005h
0x18000b27d  mov     esi, 104h
0x18000b282  mov     r8d, esi; nSize
0x18000b285  lea     rdx, [rsp+290h+Filename]; lpFilename
0x18000b28a  mov     rcx, cs:hInstance; hModule
0x18000b291  call    cs:__imp_GetModuleFileNameW
0x18000b297  test    eax, eax
0x18000b299  jz      loc_18000B422
0x18000b29f  cmp     eax, esi
0x18000b2a1  jz      loc_18000B422
0x18000b2a7  mov     [rsp+290h+var_258], 0
0x18000b2b0  lea     rdx, [rsp+290h+pptlib]; pptlib
0x18000b2b5  lea     rcx, [rsp+290h+Filename]; szFile
0x18000b2ba  call    cs:__imp_LoadTypeLib
0x18000b2c0  mov     edi, eax
0x18000b2c2  lea     rcx, [rsp+290h+var_258]
0x18000b2c7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000b2cc  jmp     short loc_18000B2F0
0x18000b2ce  lea     rax, [rsp+290h+pptlib]
0x18000b2d3  mov     [rsp+290h+var_270], rax; pptlib
0x18000b2d8  mov     r9d, esi; lcid
0x18000b2db  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x18000b2e0  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x18000b2e4  mov     rcx, [rbx+8]; rguid
0x18000b2e8  call    cs:__imp_LoadRegTypeLib
0x18000b2ee  mov     edi, eax
0x18000b2f0  test    edi, edi
0x18000b2f2  js      loc_18000B422
0x18000b2f8  mov     [rsp+290h+var_258], 0
0x18000b301  mov     rcx, [rsp+290h+pptlib]
0x18000b306  mov     rax, [rcx]
0x18000b309  lea     r8, [rsp+290h+var_258]
0x18000b30e  mov     rdx, [rbx]
0x18000b311  mov     rax, [rax+30h]
0x18000b315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b31a  mov     edi, eax
0x18000b31c  test    eax, eax
0x18000b31e  js      loc_18000B402
0x18000b324  mov     rcx, [rsp+290h+var_258]
0x18000b329  mov     [rsp+290h+var_260], rcx
0x18000b32e  test    rcx, rcx
0x18000b331  jz      short loc_18000B344
0x18000b333  mov     rax, [rcx]
0x18000b336  mov     rax, [rax+8]
0x18000b33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b33f  mov     rcx, [rsp+290h+var_258]
0x18000b344  mov     [rsp+290h+var_250], 0
0x18000b34d  mov     rax, [rcx]
0x18000b350  lea     r8, [rsp+290h+var_250]
0x18000b355  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x18000b35c  mov     rax, [rax]
0x18000b35f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b364  test    eax, eax
0x18000b366  js      short loc_18000B3BE
0x18000b368  mov     rdx, [rsp+290h+var_250]
0x18000b36d  lea     rcx, [rsp+290h+var_260]
0x18000b372  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x18000b377  test    al, al
0x18000b379  jnz     short loc_18000B3BE
0x18000b37b  mov     rcx, [rsp+290h+var_250]
0x18000b380  mov     rsi, [rsp+290h+var_260]
0x18000b385  mov     [rsp+290h+var_260], 0
0x18000b38e  test    rcx, rcx
0x18000b391  jz      short loc_18000B3AA
0x18000b393  mov     rax, [rcx]
0x18000b396  lea     r8, [rsp+290h+var_260]
0x18000b39b  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x18000b3a2  mov     rax, [rax]
0x18000b3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3aa  test    rsi, rsi
0x18000b3ad  jz      short loc_18000B3BE
0x18000b3af  mov     rax, [rsi]
0x18000b3b2  mov     rcx, rsi
0x18000b3b5  mov     rax, [rax+10h]
0x18000b3b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3be  mov     rax, [rsp+290h+var_260]
0x18000b3c3  mov     [rsp+290h+var_260], 0
0x18000b3cc  mov     [rbx+18h], rax
0x18000b3d0  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b3d7  lea     rcx, [rax+8]
0x18000b3db  neg     rax
0x18000b3de  sbb     rdx, rdx; void (*)(unsigned __int64)
0x18000b3e1  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x18000b3e4  mov     r8, rbx; unsigned __int64
0x18000b3e7  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x18000b3ec  nop
0x18000b3ed  lea     rcx, [rsp+290h+var_250]
0x18000b3f2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b3f7  nop
0x18000b3f8  lea     rcx, [rsp+290h+var_260]
0x18000b3fd  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b402  mov     rcx, [rsp+290h+pptlib]
0x18000b407  mov     rax, [rcx]
0x18000b40a  mov     rax, [rax+10h]
0x18000b40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b413  nop
0x18000b414  lea     rcx, [rsp+290h+var_258]
0x18000b419  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000b41e  jmp     short loc_18000B422
0x18000b420  xor     edi, edi
0x18000b422  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x18000b426  test    rdx, rdx
0x18000b429  jz      short loc_18000B43C
0x18000b42b  cmp     qword ptr [rbx+28h], 0
0x18000b430  jnz     short loc_18000B43C
0x18000b432  mov     rcx, rbx; this
0x18000b435  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x18000b43a  mov     edi, eax
0x18000b43c  lea     rcx, [rsp+290h+var_240]
0x18000b441  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18000b446  mov     eax, edi
0x18000b448  mov     rcx, [rbp+190h+var_20]
0x18000b44f  xor     rcx, rsp; StackCookie
0x18000b452  call    __security_check_cookie
0x18000b457  mov     rbx, [rsp+290h+arg_10]
0x18000b45f  add     rsp, 280h
0x18000b466  pop     rdi
0x18000b467  pop     rsi
0x18000b468  pop     rbp
0x18000b469  retn
```
