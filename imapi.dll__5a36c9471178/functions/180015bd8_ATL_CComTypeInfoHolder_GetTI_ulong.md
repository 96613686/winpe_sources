# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x180015bd8`
- end: `0x180015e8d`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `693`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *__hidden this, LCID lcid)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800159b0`
- `0x180015af4`
- `0x180015ea0`
- `0x180015f10`
- `0x180016180`

## callees

- `0x18000115c`
- `0x180014fc8`
- `0x180015bd8`
- `0x1800163e0`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_LoadTypeLib` at `0x180015cc6`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180015cc6`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180015ce7`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x180015ce7`
- `KERNEL32!LeaveCriticalSection` at `0x180015dd6`
- `KERNEL32!LeaveCriticalSection` at `0x180015e5a`
- `KERNEL32!LeaveCriticalSection` at `0x180015dd6`
- `KERNEL32!LeaveCriticalSection` at `0x180015e5a`
- `KERNEL32!GetModuleFileNameW` at `0x180015ca6`
- `KERNEL32!GetModuleFileNameW` at `0x180015ca6`
- `KERNEL32!EnterCriticalSection` at `0x180015c30`
- `KERNEL32!EnterCriticalSection` at `0x180015dc0`
- `KERNEL32!EnterCriticalSection` at `0x180015c30`
- `KERNEL32!EnterCriticalSection` at `0x180015dc0`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID lcid)
{
  ATL::CAtlModule *v5; // r12
  __int64 v6; // rcx
  WORD *v7; // rdx
  int NameCache; // esi
  DWORD ModuleFileNameW; // eax
  HRESULT v10; // eax
  __int64 v11; // rdx
  int (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rcx
  int (__fastcall ***v13)(_QWORD, GUID *, _QWORD *); // rcx
  unsigned __int64 v14; // r15
  _QWORD *v15; // r14
  struct ITypeInfo *v16; // rdx
  int (__fastcall ***v17)(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp-D0h] BYREF
  ITypeLib *pptlib; // [rsp+38h] [rbp-C8h] BYREF
  int (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( *((_QWORD *)this + 3) && *((_QWORD *)this + 5) )
    return 0;
  v5 = ATL::_pAtlModule;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  if ( *((_QWORD *)this + 3) )
  {
    NameCache = 0;
    goto LABEL_33;
  }
  v6 = *((_QWORD *)this + 1);
  pptlib = 0;
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
      v11 = *(_QWORD *)this;
      v19 = 0;
      NameCache = ((__int64 (__fastcall *)(ITypeLib *, __int64, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                    pptlib,
                    v11,
                    &v19);
      if ( NameCache >= 0 )
      {
        v12 = v19;
        v17 = v19;
        if ( v19 )
        {
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v19)[1])(v19);
          v12 = v19;
        }
        v20 = 0;
        if ( (**v12)(v12, &GUID_00020412_0000_0000_c000_000000000046, &v20) >= 0 )
          ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(&v17, &v20);
        v13 = 0;
        *((_QWORD *)this + 3) = v17;
        v17 = 0;
        v14 = ((unsigned __int64)ATL::_pAtlModule + 8) & -(__int64)(ATL::_pAtlModule != 0);
        if ( v14 )
        {
          v15 = operator new(0x18u);
          if ( v15 )
          {
            v15[1] = this;
            *v15 = ATL::CComTypeInfoHolder::Cleanup;
            EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 16));
            v15[2] = *(_QWORD *)(v14 + 8);
            *(_QWORD *)(v14 + 8) = v15;
            LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 16));
          }
          v13 = v17;
        }
        if ( v20 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          v13 = v17;
        }
        if ( v13 )
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v13)[2])(v13);
      }
      ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
      if ( v19 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v19)[2])(v19);
    }
    goto LABEL_33;
  }
  v7 = (WORD *)((char *)this + 16);
  if ( *((_WORD *)this + 8) != 0xFFFF || *((_WORD *)this + 9) != 0xFFFF )
    goto LABEL_15;
  NameCache = -2147467259;
  ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
  if ( ModuleFileNameW && ModuleFileNameW != 260 )
  {
    v10 = LoadTypeLib(Filename, &pptlib);
    goto LABEL_16;
  }
LABEL_33:
  v16 = (struct ITypeInfo *)*((_QWORD *)this + 3);
  if ( v16 )
  {
    if ( !*((_QWORD *)this + 5) )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(this, v16);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v5 + 24));
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x180015bd8  mov     [rsp-8+arg_10], rbx
0x180015bdd  mov     [rsp-8+arg_18], rsi
0x180015be2  push    rbp
0x180015be3  push    rdi
0x180015be4  push    r12
0x180015be6  push    r14
0x180015be8  push    r15
0x180015bea  lea     rbp, [rsp-170h]
0x180015bf2  sub     rsp, 270h
0x180015bf9  mov     rax, cs:__security_cookie
0x180015c00  xor     rax, rsp
0x180015c03  mov     [rbp+190h+var_30], rax
0x180015c0a  cmp     qword ptr [rcx+18h], 0
0x180015c0f  mov     ebx, edx
0x180015c11  mov     rdi, rcx
0x180015c14  jz      short loc_180015C24
0x180015c16  cmp     qword ptr [rcx+28h], 0
0x180015c1b  jz      short loc_180015C24
0x180015c1d  xor     eax, eax
0x180015c1f  jmp     loc_180015E62
0x180015c24  mov     r12, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180015c2b  lea     rcx, [r12+18h]; lpCriticalSection
0x180015c30  call    cs:__imp_EnterCriticalSection
0x180015c36  cmp     qword ptr [rdi+18h], 0
0x180015c3b  jnz     loc_180015E39
0x180015c41  mov     rcx, [rdi+8]; rguid
0x180015c45  mov     [rsp+290h+pptlib], 0
0x180015c4e  mov     eax, [rcx]
0x180015c50  cmp     cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, eax; _GUID ATL::CAtlModule::m_libid ...
0x180015c56  jnz     short loc_180015CCE
0x180015c58  mov     eax, [rcx+4]
0x180015c5b  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data2, eax; _GUID ATL::CAtlModule::m_libid ...
0x180015c61  jnz     short loc_180015CCE
0x180015c63  mov     eax, [rcx+8]
0x180015c66  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4, eax; _GUID ATL::CAtlModule::m_libid ...
0x180015c6c  jnz     short loc_180015CCE
0x180015c6e  mov     eax, [rcx+0Ch]
0x180015c71  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4+4, eax; _GUID ATL::CAtlModule::m_libid ...
0x180015c77  jnz     short loc_180015CCE
0x180015c79  lea     rdx, [rdi+10h]
0x180015c7d  mov     eax, 0FFFFh
0x180015c82  cmp     [rdx], ax
0x180015c85  jnz     short loc_180015CD2
0x180015c87  cmp     [rdi+12h], ax
0x180015c8b  jnz     short loc_180015CD2
0x180015c8d  mov     rcx, cs:hInstance; hModule
0x180015c94  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180015c99  mov     ebx, 104h
0x180015c9e  mov     esi, 80004005h
0x180015ca3  mov     r8d, ebx; nSize
0x180015ca6  call    cs:__imp_GetModuleFileNameW
0x180015cac  test    eax, eax
0x180015cae  jz      loc_180015E3B
0x180015cb4  cmp     eax, ebx
0x180015cb6  jz      loc_180015E3B
0x180015cbc  lea     rdx, [rsp+290h+pptlib]; pptlib
0x180015cc1  lea     rcx, [rsp+290h+Filename]; szFile
0x180015cc6  call    cs:__imp_LoadTypeLib
0x180015ccc  jmp     short loc_180015CED
0x180015cce  lea     rdx, [rdi+10h]
0x180015cd2  movzx   r8d, word ptr [rdi+12h]; wVerMinor
0x180015cd7  lea     rax, [rsp+290h+pptlib]
0x180015cdc  movzx   edx, word ptr [rdx]; wVerMajor
0x180015cdf  mov     r9d, ebx; lcid
0x180015ce2  mov     [rsp+290h+var_270], rax; pptlib
0x180015ce7  call    cs:__imp_LoadRegTypeLib
0x180015ced  mov     esi, eax
0x180015cef  test    eax, eax
0x180015cf1  js      loc_180015E3B
0x180015cf7  mov     rcx, [rsp+290h+pptlib]
0x180015cfc  lea     r8, [rsp+290h+var_250]
0x180015d01  mov     rdx, [rdi]
0x180015d04  mov     [rsp+290h+var_250], 0
0x180015d0d  mov     rax, [rcx]
0x180015d10  mov     rax, [rax+30h]
0x180015d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d19  mov     esi, eax
0x180015d1b  test    eax, eax
0x180015d1d  js      loc_180015E10
0x180015d23  mov     rcx, [rsp+290h+var_250]
0x180015d28  mov     [rsp+290h+var_260], rcx
0x180015d2d  test    rcx, rcx
0x180015d30  jz      short loc_180015D43
0x180015d32  mov     rax, [rcx]
0x180015d35  mov     rax, [rax+8]
0x180015d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d3e  mov     rcx, [rsp+290h+var_250]
0x180015d43  mov     [rsp+290h+var_248], 0
0x180015d4c  lea     r8, [rsp+290h+var_248]
0x180015d51  mov     rax, [rcx]
0x180015d54  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x180015d5b  mov     rax, [rax]
0x180015d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d63  test    eax, eax
0x180015d65  js      short loc_180015D76
0x180015d67  lea     rdx, [rsp+290h+var_248]
0x180015d6c  lea     rcx, [rsp+290h+var_260]
0x180015d71  call    ??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z; ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)
0x180015d76  mov     rax, [rsp+290h+var_260]
0x180015d7b  xor     ecx, ecx
0x180015d7d  mov     [rdi+18h], rax
0x180015d81  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180015d88  mov     [rsp+290h+var_260], rcx
0x180015d8d  lea     rdx, [rax+8]
0x180015d91  neg     rax
0x180015d94  sbb     r15, r15
0x180015d97  and     r15, rdx
0x180015d9a  jz      short loc_180015DE1
0x180015d9c  mov     ecx, 18h; Size
0x180015da1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015da6  mov     r14, rax
0x180015da9  test    rax, rax
0x180015dac  jz      short loc_180015DDC
0x180015dae  lea     rax, ?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z; ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)
0x180015db5  mov     [r14+8], rdi
0x180015db9  lea     rcx, [r15+10h]; lpCriticalSection
0x180015dbd  mov     [r14], rax
0x180015dc0  call    cs:__imp_EnterCriticalSection
0x180015dc6  mov     rcx, [r15+8]
0x180015dca  mov     [r14+10h], rcx
0x180015dce  lea     rcx, [r15+10h]; lpCriticalSection
0x180015dd2  mov     [r15+8], r14
0x180015dd6  call    cs:__imp_LeaveCriticalSection
0x180015ddc  mov     rcx, [rsp+290h+var_260]
0x180015de1  mov     rdx, [rsp+290h+var_248]
0x180015de6  test    rdx, rdx
0x180015de9  jz      short loc_180015DFF
0x180015deb  mov     rax, [rdx]
0x180015dee  mov     rcx, rdx
0x180015df1  mov     rax, [rax+10h]
0x180015df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dfa  mov     rcx, [rsp+290h+var_260]
0x180015dff  test    rcx, rcx
0x180015e02  jz      short loc_180015E10
0x180015e04  mov     rax, [rcx]
0x180015e07  mov     rax, [rax+10h]
0x180015e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e10  mov     rcx, [rsp+290h+pptlib]
0x180015e15  mov     rax, [rcx]
0x180015e18  mov     rax, [rax+10h]
0x180015e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e21  mov     rcx, [rsp+290h+var_250]
0x180015e26  test    rcx, rcx
0x180015e29  jz      short loc_180015E3B
0x180015e2b  mov     rax, [rcx]
0x180015e2e  mov     rax, [rax+10h]
0x180015e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e37  jmp     short loc_180015E3B
0x180015e39  xor     esi, esi
0x180015e3b  mov     rdx, [rdi+18h]; struct ITypeInfo *
0x180015e3f  test    rdx, rdx
0x180015e42  jz      short loc_180015E55
0x180015e44  cmp     qword ptr [rdi+28h], 0
0x180015e49  jnz     short loc_180015E55
0x180015e4b  mov     rcx, rdi; this
0x180015e4e  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x180015e53  mov     esi, eax
0x180015e55  lea     rcx, [r12+18h]; lpCriticalSection
0x180015e5a  call    cs:__imp_LeaveCriticalSection
0x180015e60  mov     eax, esi
0x180015e62  mov     rcx, [rbp+190h+var_30]
0x180015e69  xor     rcx, rsp; StackCookie
0x180015e6c  call    __security_check_cookie
0x180015e71  lea     r11, [rsp+290h+var_20]
0x180015e79  mov     rbx, [r11+40h]
0x180015e7d  mov     rsi, [r11+48h]
0x180015e81  mov     rsp, r11
0x180015e84  pop     r15
0x180015e86  pop     r14
0x180015e88  pop     r12
0x180015e8a  pop     rdi
0x180015e8b  pop     rbp
0x180015e8c  retn
```
