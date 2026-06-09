# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x1800131d8`
- end: `0x18001344a`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `626`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `12`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800130f4`
- `0x180013450`
- `0x1800134c0`
- `0x180013530`
- `0x1800135a0`
- `0x180013610`
- `0x180013680`
- `0x1800136f0`
- `0x180013760`
- `0x1800137d0`
- `0x180013840`
- `0x180013e38`

## callees

- `0x180010a00`
- `0x180011810`
- `0x1800131d8`
- `0x180014094`
- `0x18001f690`
- `0x180021010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001322d`
- `KERNEL32!EnterCriticalSection` at `0x18001322d`
- `KERNEL32!LeaveCriticalSection` at `0x180013420`
- `KERNEL32!LeaveCriticalSection` at `0x180013420`
- `KERNEL32!GetModuleFileNameW` at `0x1800132a6`
- `KERNEL32!GetModuleFileNameW` at `0x1800132a6`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1800132c9`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1800132c9`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800132ea`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x1800132ea`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  struct _RTL_CRITICAL_SECTION *v5; // rsi
  __int64 v6; // rcx
  WORD *v7; // rdx
  int NameCache; // edi
  DWORD ModuleFileNameW; // eax
  HRESULT v10; // eax
  int (__fastcall ***v11)(_QWORD, GUID *, _QWORD); // rcx
  int (__fastcall ***v12)(_QWORD, GUID *, _QWORD); // rax
  struct ITypeInfo *v13; // rdx
  int (__fastcall ***v14)(_QWORD, GUID *, _QWORD); // [rsp+30h] [rbp-D0h] BYREF
  ITypeLib *pptlib; // [rsp+38h] [rbp-C8h] BYREF
  int (__fastcall ***v16)(_QWORD, GUID *, _QWORD); // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall ***v17[2])(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-B8h] BYREF
  char v18; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)ATL::_pAtlModule + 24);
  v17[1] = (void (__fastcall ***)(_QWORD, GUID *, __int64))((char *)ATL::_pAtlModule + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  v18 = 1;
  if ( *((_QWORD *)this + 3) )
  {
    NameCache = 0;
    goto LABEL_30;
  }
  pptlib = 0;
  v6 = *((_QWORD *)this + 1);
  if ( ATL::CAtlModule::m_libid.Data1 != *(_DWORD *)v6
    || *(_DWORD *)&ATL::CAtlModule::m_libid.Data2 != *(_DWORD *)(v6 + 4)
    || *(_DWORD *)ATL::CAtlModule::m_libid.Data4 != *(_DWORD *)(v6 + 8)
    || *(_DWORD *)&ATL::CAtlModule::m_libid.Data4[4] != *(_DWORD *)(v6 + 12) )
  {
    v7 = (WORD *)((char *)this + 16);
LABEL_15:
    v10 = LoadRegTypeLib((const GUID *const)v6, *v7, *((_WORD *)this + 9), lcid, &pptlib);
LABEL_16:
    NameCache = v10;
    if ( v10 >= 0 )
    {
      v16 = 0;
      NameCache = ((__int64 (__fastcall *)(ITypeLib *, _QWORD, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                    pptlib,
                    *(_QWORD *)this,
                    &v16);
      if ( NameCache >= 0 )
      {
        v11 = v16;
        v14 = v16;
        if ( v16 )
        {
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v16)[1])(v16);
          v11 = v16;
        }
        v17[0] = 0;
        if ( (**v11)(v11, &GUID_00020412_0000_0000_c000_000000000046, v17) >= 0 )
          ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(&v14, v17);
        v12 = v14;
        v14 = 0;
        *((_QWORD *)this + 3) = v12;
        ATL::AtlModuleAddTermFunc(
          (struct ATL::_ATL_MODULE70 *)(((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64)
                                      & ((unsigned __int64)ATL::_pAtlModule + 8)),
          (void (*)(unsigned __int64))((unsigned __int128)-(__int128)(unsigned __int64)ATL::_pAtlModule >> 64),
          (unsigned __int64)this);
        if ( v17[0] )
          (*((void (__fastcall **)(void (__fastcall ***)(_QWORD, GUID *, __int64)))*v17[0] + 2))(v17[0]);
        if ( v14 )
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v14)[2])(v14);
      }
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      if ( v16 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v16)[2])(v16);
    }
    goto LABEL_30;
  }
  v7 = (WORD *)((char *)this + 16);
  if ( *((_WORD *)this + 8) != 0xFFFF || *((_WORD *)this + 9) != 0xFFFF )
    goto LABEL_15;
  NameCache = -2147467259;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( ModuleFileNameW && ModuleFileNameW != 260 )
  {
    v10 = LoadTypeLib(Filename, &pptlib);
    goto LABEL_16;
  }
LABEL_30:
  v13 = (struct ITypeInfo *)*((_QWORD *)this + 3);
  if ( v13 )
  {
    if ( !*((_QWORD *)this + 5) )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v13);
  }
  LeaveCriticalSection(v5);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x1800131d8  mov     [rsp-8+arg_10], rbx
0x1800131dd  push    rbp
0x1800131de  push    rsi
0x1800131df  push    rdi
0x1800131e0  lea     rbp, [rsp-180h]
0x1800131e8  sub     rsp, 280h
0x1800131ef  mov     rax, cs:__security_cookie
0x1800131f6  xor     rax, rsp
0x1800131f9  mov     [rbp+190h+var_20], rax
0x180013200  mov     edi, edx
0x180013202  mov     rbx, rcx
0x180013205  cmp     qword ptr [rcx+18h], 0
0x18001320a  jz      short loc_18001321A
0x18001320c  cmp     qword ptr [rcx+28h], 0
0x180013211  jz      short loc_18001321A
0x180013213  xor     eax, eax
0x180013215  jmp     loc_180013428
0x18001321a  mov     rsi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180013221  add     rsi, 18h
0x180013225  mov     [rsp+290h+var_240], rsi
0x18001322a  mov     rcx, rsi; lpCriticalSection
0x18001322d  call    cs:__imp_EnterCriticalSection
0x180013233  mov     [rsp+290h+var_238], 1
0x180013238  cmp     qword ptr [rbx+18h], 0
0x18001323d  jnz     loc_180013401
0x180013243  mov     [rsp+290h+pptlib], 0
0x18001324c  mov     rcx, [rbx+8]; rguid
0x180013250  mov     eax, [rcx]
0x180013252  cmp     cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, eax; _GUID ATL::CAtlModule::m_libid ...
0x180013258  jnz     short loc_1800132D1
0x18001325a  mov     eax, [rcx+4]
0x18001325d  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data2, eax; _GUID ATL::CAtlModule::m_libid ...
0x180013263  jnz     short loc_1800132D1
0x180013265  mov     eax, [rcx+8]
0x180013268  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4, eax; _GUID ATL::CAtlModule::m_libid ...
0x18001326e  jnz     short loc_1800132D1
0x180013270  mov     eax, [rcx+0Ch]
0x180013273  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4+4, eax; _GUID ATL::CAtlModule::m_libid ...
0x180013279  jnz     short loc_1800132D1
0x18001327b  lea     rdx, [rbx+10h]
0x18001327f  mov     eax, 0FFFFh
0x180013284  cmp     [rdx], ax
0x180013287  jnz     short loc_1800132D5
0x180013289  cmp     [rbx+12h], ax
0x18001328d  jnz     short loc_1800132D5
0x18001328f  mov     edi, 80004005h
0x180013294  mov     r8d, 104h; nSize
0x18001329a  lea     rdx, [rsp+290h+Filename]; lpFilename
0x18001329f  mov     rcx, cs:hModule; hModule
0x1800132a6  call    cs:__imp_GetModuleFileNameW
0x1800132ac  test    eax, eax
0x1800132ae  jz      loc_180013403
0x1800132b4  cmp     eax, 104h
0x1800132b9  jz      loc_180013403
0x1800132bf  lea     rdx, [rsp+290h+pptlib]; pptlib
0x1800132c4  lea     rcx, [rsp+290h+Filename]; szFile
0x1800132c9  call    cs:__imp_LoadTypeLib
0x1800132cf  jmp     short loc_1800132F0
0x1800132d1  lea     rdx, [rbx+10h]
0x1800132d5  lea     rax, [rsp+290h+pptlib]
0x1800132da  mov     [rsp+290h+var_270], rax; pptlib
0x1800132df  mov     r9d, edi; lcid
0x1800132e2  movzx   r8d, word ptr [rbx+12h]; wVerMinor
0x1800132e7  movzx   edx, word ptr [rdx]; wVerMajor
0x1800132ea  call    cs:__imp_LoadRegTypeLib
0x1800132f0  mov     edi, eax
0x1800132f2  test    eax, eax
0x1800132f4  js      loc_180013403
0x1800132fa  mov     [rsp+290h+var_250], 0
0x180013303  mov     rcx, [rsp+290h+pptlib]
0x180013308  mov     rax, [rcx]
0x18001330b  lea     r8, [rsp+290h+var_250]
0x180013310  mov     rdx, [rbx]
0x180013313  mov     rax, [rax+30h]
0x180013317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001331c  mov     edi, eax
0x18001331e  test    eax, eax
0x180013320  js      loc_1800133D6
0x180013326  mov     rcx, [rsp+290h+var_250]
0x18001332b  mov     [rsp+290h+var_260], rcx
0x180013330  test    rcx, rcx
0x180013333  jz      short loc_180013346
0x180013335  mov     rax, [rcx]
0x180013338  mov     rax, [rax+8]
0x18001333c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013341  mov     rcx, [rsp+290h+var_250]
0x180013346  mov     [rsp+290h+var_248], 0
0x18001334f  mov     rax, [rcx]
0x180013352  lea     r8, [rsp+290h+var_248]
0x180013357  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x18001335e  mov     rax, [rax]
0x180013361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013366  test    eax, eax
0x180013368  js      short loc_180013379
0x18001336a  lea     rdx, [rsp+290h+var_248]
0x18001336f  lea     rcx, [rsp+290h+var_260]
0x180013374  call    ??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z; ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)
0x180013379  mov     rax, [rsp+290h+var_260]
0x18001337e  mov     [rsp+290h+var_260], 0
0x180013387  mov     [rbx+18h], rax
0x18001338b  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180013392  lea     rcx, [rax+8]
0x180013396  neg     rax
0x180013399  sbb     rdx, rdx; void (*)(unsigned __int64)
0x18001339c  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x18001339f  mov     r8, rbx; unsigned __int64
0x1800133a2  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x1800133a7  nop
0x1800133a8  mov     rcx, [rsp+290h+var_248]
0x1800133ad  test    rcx, rcx
0x1800133b0  jz      short loc_1800133BF
0x1800133b2  mov     rax, [rcx]
0x1800133b5  mov     rax, [rax+10h]
0x1800133b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133be  nop
0x1800133bf  mov     rcx, [rsp+290h+var_260]
0x1800133c4  test    rcx, rcx
0x1800133c7  jz      short loc_1800133D6
0x1800133c9  mov     rax, [rcx]
0x1800133cc  mov     rax, [rax+10h]
0x1800133d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133d5  nop
0x1800133d6  mov     rcx, [rsp+290h+pptlib]
0x1800133db  mov     rax, [rcx]
0x1800133de  mov     rax, [rax+10h]
0x1800133e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133e7  nop
0x1800133e8  mov     rcx, [rsp+290h+var_250]
0x1800133ed  test    rcx, rcx
0x1800133f0  jz      short loc_1800133FF
0x1800133f2  mov     rax, [rcx]
0x1800133f5  mov     rax, [rax+10h]
0x1800133f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133fe  nop
0x1800133ff  jmp     short loc_180013403
0x180013401  xor     edi, edi
0x180013403  mov     rdx, [rbx+18h]; struct ITypeInfo *
0x180013407  test    rdx, rdx
0x18001340a  jz      short loc_18001341D
0x18001340c  cmp     qword ptr [rbx+28h], 0
0x180013411  jnz     short loc_18001341D
0x180013413  mov     rcx, rbx; this
0x180013416  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x18001341b  mov     edi, eax
0x18001341d  mov     rcx, rsi; lpCriticalSection
0x180013420  call    cs:__imp_LeaveCriticalSection
0x180013426  mov     eax, edi
0x180013428  mov     rcx, [rbp+190h+var_20]
0x18001342f  xor     rcx, rsp; StackCookie
0x180013432  call    __security_check_cookie
0x180013437  mov     rbx, [rsp+290h+arg_10]
0x18001343f  add     rsp, 280h
0x180013446  pop     rdi
0x180013447  pop     rsi
0x180013448  pop     rbp
0x180013449  retn
```
