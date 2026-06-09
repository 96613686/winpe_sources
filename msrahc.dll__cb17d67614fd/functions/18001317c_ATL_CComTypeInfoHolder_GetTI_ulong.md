# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x18001317c`
- end: `0x18001342d`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `689`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *this, LCID)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180013094`
- `0x180013440`

## callees

- `0x18000882c`
- `0x180008884`
- `0x180008924`
- `0x18000a994`
- `0x18000a9f0`
- `0x1800128b0`
- `0x18001317c`
- `0x18001369c`
- `0x180013844`
- `0x18001a5e0`
- `0x18001c010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLib` at `0x18001327e`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18001327e`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800132a2`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800132a2`
- `KERNEL32!GetModuleFileNameW` at `0x180013255`
- `KERNEL32!GetModuleFileNameW` at `0x180013255`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID a2)
{
  ATL::CComTypeInfoHolder *v4; // rcx
  HRESULT NameCache; // ebx
  const GUID *v6; // r10
  DWORD ModuleFileNameW; // eax
  struct ITypeInfo *v8; // rcx
  unsigned __int64 v9; // r8
  __int64 v10; // rdi
  struct ITypeInfo *v11; // rax
  struct ITypeInfo *v12; // [rsp+30h] [rbp-D0h] BYREF
  struct ITypeInfo *v13; // [rsp+38h] [rbp-C8h] BYREF
  void (__fastcall ***v14)(_QWORD, GUID *, struct ITypeInfo **); // [rsp+40h] [rbp-C0h] BYREF
  ITypeLib *pptlib; // [rsp+48h] [rbp-B8h] BYREF
  char *v16; // [rsp+50h] [rbp-B0h] BYREF
  char v17; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( qword_1800270F8 && qword_180027108 )
    return 0;
  v16 = (char *)ATL::_pAtlModule + 24;
  v17 = 0;
  NameCache = ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(&v16);
  if ( NameCache >= 0 )
  {
    if ( qword_1800270F8 )
    {
      NameCache = 0;
    }
    else
    {
      pptlib = 0;
      if ( !(unsigned int)InlineIsEqualGUID(&ATL::CAtlModule::m_libid, off_1800270E8) || *(_DWORD *)&wVerMajor != -1 )
      {
        NameCache = LoadRegTypeLib(v6, wVerMajor, *(&wVerMajor + 1), a2, &pptlib);
LABEL_12:
        if ( NameCache >= 0 )
        {
          v13 = 0;
          NameCache = ((__int64 (__fastcall *)(ITypeLib *, GUID *, struct ITypeInfo **))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                        pptlib,
                        CRASMapi::m_typeInfo[0],
                        &v13);
          if ( NameCache >= 0 )
          {
            v8 = v13;
            v12 = v13;
            if ( v13 )
            {
              ((void (__fastcall *)(struct ITypeInfo *))v13->lpVtbl->AddRef)(v13);
              v8 = v13;
            }
            v14 = 0;
            if ( ((__int64 (__fastcall *)(struct ITypeInfo *, GUID *, _QWORD))v8->lpVtbl->QueryInterface)(
                   v8,
                   &GUID_00020412_0000_0000_c000_000000000046,
                   &v14) >= 0
              && !(unsigned __int8)ATL::CComPtrBase<ITypeInfo>::IsEqualObject(&v12, v14) )
            {
              v10 = (__int64)v12;
              v12 = 0;
              if ( v14 )
                (**v14)(v14, &GUID_00020401_0000_0000_c000_000000000046, &v12);
              if ( v10 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
            }
            v11 = v12;
            v12 = 0;
            qword_1800270F8 = v11;
            ATL::AtlModuleAddTermFunc(
              (struct ATL::_ATL_MODULE70 *)(((unsigned __int64)ATL::_pAtlModule + 8) & -(__int64)(ATL::_pAtlModule != 0)),
              (void (*)(unsigned __int64))((char *)ATL::_pAtlModule + 8),
              v9);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
            ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v12);
          }
          ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v13);
        }
        goto LABEL_25;
      }
      NameCache = -2147467259;
      ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
      if ( ModuleFileNameW && ModuleFileNameW != 260 )
      {
        v13 = 0;
        NameCache = LoadTypeLib(Filename, &pptlib);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v13);
        goto LABEL_12;
      }
    }
LABEL_25:
    if ( qword_1800270F8 )
    {
      if ( !qword_180027108 )
        NameCache = ATL::CComTypeInfoHolder::LoadNameCache(v4, qword_1800270F8);
    }
  }
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>((__int64)&v16);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x18001317c  mov     [rsp-8+arg_0], rbx
0x180013181  mov     [rsp-8+arg_10], rdi
0x180013186  push    rbp
0x180013187  lea     rbp, [rsp-180h]
0x18001318f  sub     rsp, 280h
0x180013196  mov     rax, cs:__security_cookie
0x18001319d  xor     rax, rsp
0x1800131a0  mov     [rbp+180h+var_10], rax
0x1800131a7  mov     edi, edx
0x1800131a9  cmp     cs:qword_1800270F8, 0
0x1800131b1  jz      short loc_1800131C4
0x1800131b3  cmp     cs:qword_180027108, 0
0x1800131bb  jz      short loc_1800131C4
0x1800131bd  xor     eax, eax
0x1800131bf  jmp     loc_180013409
0x1800131c4  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800131cb  add     rax, 18h
0x1800131cf  mov     [rsp+280h+var_230], rax
0x1800131d4  mov     [rsp+280h+var_228], 0
0x1800131d9  lea     rcx, [rsp+280h+var_230]
0x1800131de  call    ?Lock@?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAAJXZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::Lock(void)
0x1800131e3  mov     ebx, eax
0x1800131e5  test    eax, eax
0x1800131e7  js      loc_1800133FD
0x1800131ed  cmp     cs:qword_1800270F8, 0
0x1800131f5  jnz     loc_1800133DE
0x1800131fb  mov     [rsp+280h+pptlib], 0
0x180013204  mov     r10, cs:off_1800270E8
0x18001320b  mov     rdx, r10; struct _GUID *
0x18001320e  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; struct _GUID *
0x180013215  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18001321a  mov     r8, cs:wVerMajor+2; wVerMinor
0x180013221  mov     rdx, cs:wVerMajor; wVerMajor
0x180013228  test    eax, eax
0x18001322a  jz      short loc_180013292
0x18001322c  mov     eax, 0FFFFh
0x180013231  cmp     dx, ax
0x180013234  jnz     short loc_180013292
0x180013236  cmp     r8w, ax
0x18001323a  jnz     short loc_180013292
0x18001323c  mov     ebx, 80004005h
0x180013241  mov     edi, 104h
0x180013246  mov     r8d, edi; nSize
0x180013249  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18001324e  mov     rcx, cs:hModule; hModule
0x180013255  call    cs:__imp_GetModuleFileNameW
0x18001325b  test    eax, eax
0x18001325d  jz      loc_1800133E0
0x180013263  cmp     eax, edi
0x180013265  jz      loc_1800133E0
0x18001326b  mov     [rsp+280h+var_248], 0
0x180013274  lea     rdx, [rsp+280h+pptlib]; pptlib
0x180013279  lea     rcx, [rsp+280h+Filename]; szFile
0x18001327e  call    cs:__imp_LoadTypeLib
0x180013284  mov     ebx, eax
0x180013286  lea     rcx, [rsp+280h+var_248]
0x18001328b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180013290  jmp     short loc_1800132AA
0x180013292  lea     rax, [rsp+280h+pptlib]
0x180013297  mov     [rsp+280h+var_260], rax; pptlib
0x18001329c  mov     r9d, edi; lcid
0x18001329f  mov     rcx, r10; rguid
0x1800132a2  call    cs:__imp_LoadRegTypeLib
0x1800132a8  mov     ebx, eax
0x1800132aa  test    ebx, ebx
0x1800132ac  js      loc_1800133E0
0x1800132b2  mov     [rsp+280h+var_248], 0
0x1800132bb  mov     rcx, [rsp+280h+pptlib]
0x1800132c0  mov     rax, [rcx]
0x1800132c3  lea     r8, [rsp+280h+var_248]
0x1800132c8  mov     rdx, cs:?m_typeInfo@CRASMapi@@0VCComTypeInfoHolder@ATL@@A; ATL::CComTypeInfoHolder CRASMapi::m_typeInfo
0x1800132cf  mov     rax, [rax+30h]
0x1800132d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132d8  mov     ebx, eax
0x1800132da  test    eax, eax
0x1800132dc  js      loc_1800133C0
0x1800132e2  mov     rcx, [rsp+280h+var_248]
0x1800132e7  mov     [rsp+280h+var_250], rcx
0x1800132ec  test    rcx, rcx
0x1800132ef  jz      short loc_180013302
0x1800132f1  mov     rax, [rcx]
0x1800132f4  mov     rax, [rax+8]
0x1800132f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132fd  mov     rcx, [rsp+280h+var_248]
0x180013302  mov     [rsp+280h+var_240], 0
0x18001330b  mov     rax, [rcx]
0x18001330e  lea     r8, [rsp+280h+var_240]
0x180013313  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x18001331a  mov     rax, [rax]
0x18001331d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013322  test    eax, eax
0x180013324  js      short loc_18001337C
0x180013326  mov     rdx, [rsp+280h+var_240]
0x18001332b  lea     rcx, [rsp+280h+var_250]
0x180013330  call    ?IsEqualObject@?$CComPtrBase@UITypeInfo@@@ATL@@QEAA_NPEAUIUnknown@@@Z; ATL::CComPtrBase<ITypeInfo>::IsEqualObject(IUnknown *)
0x180013335  test    al, al
0x180013337  jnz     short loc_18001337C
0x180013339  mov     rcx, [rsp+280h+var_240]
0x18001333e  mov     rdi, [rsp+280h+var_250]
0x180013343  mov     [rsp+280h+var_250], 0
0x18001334c  test    rcx, rcx
0x18001334f  jz      short loc_180013368
0x180013351  mov     rax, [rcx]
0x180013354  lea     r8, [rsp+280h+var_250]
0x180013359  lea     rdx, _GUID_00020401_0000_0000_c000_000000000046
0x180013360  mov     rax, [rax]
0x180013363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013368  test    rdi, rdi
0x18001336b  jz      short loc_18001337C
0x18001336d  mov     rax, [rdi]
0x180013370  mov     rcx, rdi
0x180013373  mov     rax, [rax+10h]
0x180013377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001337c  mov     rax, [rsp+280h+var_250]
0x180013381  mov     [rsp+280h+var_250], 0
0x18001338a  mov     cs:qword_1800270F8, rax
0x180013391  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180013398  lea     rdx, [rax+8]; void (*)(unsigned __int64)
0x18001339c  neg     rax
0x18001339f  sbb     rcx, rcx
0x1800133a2  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x1800133a5  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x1800133aa  nop
0x1800133ab  lea     rcx, [rsp+280h+var_240]
0x1800133b0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800133b5  nop
0x1800133b6  lea     rcx, [rsp+280h+var_250]
0x1800133bb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800133c0  mov     rcx, [rsp+280h+pptlib]
0x1800133c5  mov     rax, [rcx]
0x1800133c8  mov     rax, [rax+10h]
0x1800133cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133d1  nop
0x1800133d2  lea     rcx, [rsp+280h+var_248]
0x1800133d7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800133dc  jmp     short loc_1800133E0
0x1800133de  xor     ebx, ebx
0x1800133e0  mov     rdx, cs:qword_1800270F8; struct ITypeInfo *
0x1800133e7  test    rdx, rdx
0x1800133ea  jz      short loc_1800133FD
0x1800133ec  cmp     cs:qword_180027108, 0
0x1800133f4  jnz     short loc_1800133FD
0x1800133f6  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x1800133fb  mov     ebx, eax
0x1800133fd  lea     rcx, [rsp+280h+var_230]
0x180013402  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x180013407  mov     eax, ebx
0x180013409  mov     rcx, [rbp+180h+var_10]
0x180013410  xor     rcx, rsp; StackCookie
0x180013413  call    __security_check_cookie
0x180013418  lea     r11, [rsp+280h+var_s0]
0x180013420  mov     rbx, [r11+10h]
0x180013424  mov     rdi, [r11+20h]
0x180013428  mov     rsp, r11
0x18001342b  pop     rbp
0x18001342c  retn
```
