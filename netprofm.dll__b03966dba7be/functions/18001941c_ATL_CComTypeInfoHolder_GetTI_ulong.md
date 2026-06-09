# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x18001941c`
- end: `0x1800196b2`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `662`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000ac78`
- `0x1800192c4`
- `0x1800197b4`

## callees

- `0x180006b20`
- `0x1800086b0`
- `0x18000a83c`
- `0x18000a9a4`
- `0x18000aed8`
- `0x18000bd54`
- `0x1800120d0`
- `0x180015730`
- `0x180016848`
- `0x18001941c`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800194d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800194d9`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180019502`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180019502`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180019530`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180019530`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  HRESULT NameCache; // edi
  __int64 v6; // r8
  __int64 v7; // r9
  DWORD ModuleFileNameW; // eax
  int (__fastcall ***v9)(_QWORD, GUID *, _QWORD); // rcx
  __int64 v10; // rsi
  __int64 v11; // rax
  struct ITypeInfo *v12; // rdx
  char *v13; // [rsp+30h] [rbp-D0h] BYREF
  char v14; // [rsp+38h] [rbp-C8h]
  ITypeLib *pptlib; // [rsp+40h] [rbp-C0h] BYREF
  int (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // [rsp+48h] [rbp-B8h] BYREF
  int (__fastcall ***v17)(_QWORD, GUID *, _QWORD); // [rsp+50h] [rbp-B0h] BYREF
  void (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v13 = (char *)ATL::_pAtlModule + 24;
  v14 = 0;
  NameCache = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v13);
  if ( NameCache >= 0 )
  {
    if ( *((_QWORD *)this + 3) )
    {
      NameCache = 0;
    }
    else
    {
      pptlib = 0;
      if ( !(unsigned int)InlineIsEqualGUID(&ATL::CAtlModule::m_libid, *((_QWORD *)this + 1), v6, v7)
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
          v17 = 0;
          NameCache = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                        pptlib,
                        *(_QWORD *)this,
                        &v17);
          if ( NameCache >= 0 )
          {
            v9 = v17;
            v16 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v17;
            if ( v17 )
            {
              ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v17)[1])(v17);
              v9 = v17;
            }
            v18 = 0;
            if ( (**v9)(v9, &GUID_00020412_0000_0000_c000_000000000046, &v18) >= 0
              && !(unsigned __int8)ATL::CComPtrBase<ITypeInfo>::IsEqualObject(&v16, v18) )
            {
              v10 = (__int64)v16;
              v16 = 0;
              if ( v18 )
                (**v18)(v18, &GUID_00020401_0000_0000_c000_000000000046, (__int64 *)&v16);
              if ( v10 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
            }
            v11 = (__int64)v16;
            v16 = 0;
            *((_QWORD *)this + 3) = v11;
            ATL::AtlModuleAddTermFunc(
              (struct ATL::_ATL_MODULE70 *)(((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64)
                                          & ((unsigned __int64)ATL::_pAtlModule + 8)),
              (void (*)(unsigned __int64))((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64),
              (unsigned __int64)this);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v18);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v16);
          }
          ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v17);
        }
        goto LABEL_26;
      }
      NameCache = -2147467259;
      ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
      if ( ModuleFileNameW && ModuleFileNameW != 260 )
      {
        v17 = 0;
        NameCache = LoadTypeLib(Filename, &pptlib);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v17);
        goto LABEL_13;
      }
    }
LABEL_26:
    v12 = (struct ITypeInfo *)*((_QWORD *)this + 3);
    if ( v12 )
    {
      if ( !*((_QWORD *)this + 5) )
        NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v12);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v13);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x18001941c  mov     [rsp-8+arg_10], rbx
0x180019421  push    rbp
0x180019422  push    rsi
0x180019423  push    rdi
0x180019424  lea     rbp, [rsp-180h]
0x18001942c  sub     rsp, 280h
0x180019433  mov     rax, cs:__security_cookie
0x18001943a  xor     rax, rsp
0x18001943d  mov     [rbp+190h+var_20], rax
0x180019444  mov     esi, edx
0x180019446  mov     rbx, rcx
0x180019449  cmp     qword ptr [rcx+18h], 0
0x18001944e  jz      short loc_18001945E
0x180019450  cmp     qword ptr [rcx+28h], 0
0x180019455  jz      short loc_18001945E
0x180019457  xor     eax, eax
0x180019459  jmp     loc_180019690
0x18001945e  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180019465  add     rax, 18h
0x180019469  mov     [rsp+290h+var_260], rax
0x18001946e  mov     [rsp+290h+var_258], 0
0x180019473  lea     rcx, [rsp+290h+var_260]
0x180019478  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x18001947d  mov     edi, eax
0x18001947f  test    eax, eax
0x180019481  js      loc_180019684
0x180019487  cmp     qword ptr [rbx+18h], 0
0x18001948c  jnz     loc_180019668
0x180019492  mov     [rsp+290h+pptlib], 0
0x18001949b  mov     rdx, [rbx+8]
0x18001949f  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; _GUID ATL::CAtlModule::m_libid
0x1800194a6  call    InlineIsEqualGUID
0x1800194ab  test    eax, eax
0x1800194ad  jz      short loc_180019516
0x1800194af  mov     eax, 0FFFFh
0x1800194b4  cmp     [rbx+10h], ax
0x1800194b8  jnz     short loc_180019516
0x1800194ba  cmp     [rbx+12h], ax
0x1800194be  jnz     short loc_180019516
0x1800194c0  mov     edi, 80004005h
0x1800194c5  mov     esi, 104h
0x1800194ca  mov     r8d, esi; nSize
0x1800194cd  lea     rdx, [rsp+290h+Filename]; lpFilename
0x1800194d2  mov     rcx, cs:hModule; hModule
0x1800194d9  call    cs:__imp_GetModuleFileNameW
0x1800194df  test    eax, eax
0x1800194e1  jz      loc_18001966A
0x1800194e7  cmp     eax, esi
0x1800194e9  jz      loc_18001966A
0x1800194ef  mov     [rsp+290h+var_240], 0
0x1800194f8  lea     rdx, [rsp+290h+pptlib]; pptlib
0x1800194fd  lea     rcx, [rsp+290h+Filename]; szFile
0x180019502  call    cs:__imp_LoadTypeLib
0x180019508  mov     edi, eax
0x18001950a  lea     rcx, [rsp+290h+var_240]
0x18001950f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180019514  jmp     short loc_180019538
0x180019516  lea     rax, [rsp+290h+pptlib]
0x18001951b  mov     [rsp+290h+var_270], rax; pptlib
0x180019520  mov     r9d, esi; lcid
0x180019523  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x180019528  movzx   edx, word ptr [rbx+10h]; wVerMajor
0x18001952c  mov     rcx, [rbx+8]; rguid
0x180019530  call    cs:__imp_LoadRegTypeLib
0x180019536  mov     edi, eax
0x180019538  test    edi, edi
0x18001953a  js      loc_18001966A
0x180019540  mov     [rsp+290h+var_240], 0
0x180019549  mov     rcx, [rsp+290h+pptlib]
0x18001954e  mov     rax, [rcx]
0x180019551  lea     r8, [rsp+290h+var_240]
0x180019556  mov     rdx, [rbx]
0x180019559  mov     rax, [rax+30h]
0x18001955d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019562  mov     edi, eax
0x180019564  test    eax, eax
0x180019566  js      loc_18001964A
0x18001956c  mov     rcx, [rsp+290h+var_240]
0x180019571  mov     [rsp+290h+var_248], rcx
0x180019576  test    rcx, rcx
0x180019579  jz      short loc_18001958C
0x18001957b  mov     rax, [rcx]
0x18001957e  mov     rax, [rax+8]
0x180019582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019587  mov     rcx, [rsp+290h+var_240]
0x18001958c  mov     [rsp+290h+var_238], 0
0x180019595  mov     rax, [rcx]
0x180019598  lea     r8, [rsp+290h+var_238]
0x18001959d  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x1800195a4  mov     rax, [rax]
0x1800195a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195ac  test    eax, eax
0x1800195ae  js      short loc_180019606
0x1800195b0  mov     rdx, [rsp+290h+var_238]
0x1800195b5  lea     rcx, [rsp+290h+var_248]
0x1800195ba  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x1800195bf  test    al, al
0x1800195c1  jnz     short loc_180019606
0x1800195c3  mov     rcx, [rsp+290h+var_238]
0x1800195c8  mov     rsi, [rsp+290h+var_248]
0x1800195cd  mov     [rsp+290h+var_248], 0
0x1800195d6  test    rcx, rcx
0x1800195d9  jz      short loc_1800195F2
0x1800195db  mov     rax, [rcx]
0x1800195de  lea     r8, [rsp+290h+var_248]
0x1800195e3  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x1800195ea  mov     rax, [rax]
0x1800195ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195f2  test    rsi, rsi
0x1800195f5  jz      short loc_180019606
0x1800195f7  mov     rax, [rsi]
0x1800195fa  mov     rcx, rsi
0x1800195fd  mov     rax, [rax+10h]
0x180019601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019606  mov     rax, [rsp+290h+var_248]
0x18001960b  mov     [rsp+290h+var_248], 0
0x180019614  mov     [rbx+18h], rax
0x180019618  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001961f  lea     rcx, [rax+8]
0x180019623  neg     rax
0x180019626  sbb     rdx, rdx; void (*)(unsigned __int64)
0x180019629  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x18001962c  mov     r8, rbx; unsigned __int64
0x18001962f  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x180019634  nop
0x180019635  lea     rcx, [rsp+290h+var_238]
0x18001963a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001963f  nop
0x180019640  lea     rcx, [rsp+290h+var_248]
0x180019645  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001964a  mov     rcx, [rsp+290h+pptlib]
0x18001964f  mov     rax, [rcx]
0x180019652  mov     rax, [rax+10h]
0x180019656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001965b  nop
0x18001965c  lea     rcx, [rsp+290h+var_240]
0x180019661  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180019666  jmp     short loc_18001966A
0x180019668  xor     edi, edi
0x18001966a  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x18001966e  test    rdx, rdx
0x180019671  jz      short loc_180019684
0x180019673  cmp     qword ptr [rbx+28h], 0
0x180019678  jnz     short loc_180019684
0x18001967a  mov     rcx, rbx; this
0x18001967d  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x180019682  mov     edi, eax
0x180019684  lea     rcx, [rsp+290h+var_260]
0x180019689  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x18001968e  mov     eax, edi
0x180019690  mov     rcx, [rbp+190h+var_20]
0x180019697  xor     rcx, rsp; StackCookie
0x18001969a  call    __security_check_cookie
0x18001969f  mov     rbx, [rsp+290h+arg_10]
0x1800196a7  add     rsp, 280h
0x1800196ae  pop     rdi
0x1800196af  pop     rsi
0x1800196b0  pop     rbp
0x1800196b1  retn
```
