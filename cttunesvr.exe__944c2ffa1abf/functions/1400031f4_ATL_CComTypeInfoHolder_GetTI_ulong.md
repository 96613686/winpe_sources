# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x1400031f4`
- end: `0x1400034aa`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `694`
- prototype: `int(ATL::CComTypeInfoHolder *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003100`
- `0x1400034b0`
- `0x140003670`

## callees

- `0x140001204`
- `0x140001f68`
- `0x1400031f4`
- `0x14000370c`
- `0x1400065f0`
- `0x140007010`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x1400032cb`
- `KERNEL32!GetModuleFileNameW` at `0x1400032cb`
- `KERNEL32!EnterCriticalSection` at `0x140003245`
- `KERNEL32!EnterCriticalSection` at `0x1400033e7`
- `KERNEL32!EnterCriticalSection` at `0x140003245`
- `KERNEL32!EnterCriticalSection` at `0x1400033e7`
- `KERNEL32!LeaveCriticalSection` at `0x1400033fd`
- `KERNEL32!LeaveCriticalSection` at `0x140003483`
- `KERNEL32!LeaveCriticalSection` at `0x1400033fd`
- `KERNEL32!LeaveCriticalSection` at `0x140003483`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1400032eb`
- `OLEAUT32!__imp_LoadTypeLib` at `0x1400032eb`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x140003300`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x140003300`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID a2)
{
  struct ATL::CAtlModule *v4; // r15
  ATL::CComTypeInfoHolder *v5; // rcx
  int NameCache; // edi
  DWORD ModuleFileNameW; // eax
  HRESULT v8; // eax
  int (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rcx
  struct ITypeInfo *v10; // rcx
  unsigned __int64 v11; // r14
  _QWORD *v12; // rax
  _QWORD *v13; // rsi
  struct ITypeInfo *v14; // [rsp+30h] [rbp-D0h] BYREF
  ITypeLib *pptlib; // [rsp+38h] [rbp-C8h] BYREF
  int (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-B0h] BYREF

  if ( qword_14000B068 && qword_14000B078 )
    return 0;
  v4 = ATL::_pAtlModule;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  if ( qword_14000B068 )
  {
    NameCache = 0;
  }
  else
  {
    pptlib = 0;
    if ( ATL::CAtlModule::m_libid.Data1 != rguid->Data1
      || *(_DWORD *)&ATL::CAtlModule::m_libid.Data2 != *(_DWORD *)&rguid->Data2
      || *(_DWORD *)ATL::CAtlModule::m_libid.Data4 != *(_DWORD *)rguid->Data4
      || *(_DWORD *)&ATL::CAtlModule::m_libid.Data4[4] != *(_DWORD *)&rguid->Data4[4]
      || *(_DWORD *)&wVerMajor != -1 )
    {
      v8 = LoadRegTypeLib(rguid, wVerMajor, *(&wVerMajor + 1), a2, &pptlib);
LABEL_14:
      NameCache = v8;
      if ( v8 >= 0 )
      {
        v16 = 0;
        NameCache = ((__int64 (__fastcall *)(ITypeLib *, GUID *, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                      pptlib,
                      ATL::IDispatchImpl<ICtTuner,&_GUID const IID_ICtTuner,&_GUID const LIBID_cttunesvrLib,1,0,ATL::CComTypeInfoHolder>::_tih[0],
                      &v16);
        if ( NameCache >= 0 )
        {
          v9 = v16;
          v14 = (struct ITypeInfo *)v16;
          if ( v16 )
          {
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v16)[1])(v16);
            v9 = v16;
          }
          v17 = 0;
          if ( (**v9)(v9, &GUID_00020412_0000_0000_c000_000000000046, &v17) >= 0 )
            ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(&v14, &v17);
          v10 = 0;
          qword_14000B068 = v14;
          v14 = 0;
          v11 = ((unsigned __int64)ATL::_pAtlModule + 8) & -(__int64)(ATL::_pAtlModule != 0);
          if ( v11 )
          {
            v12 = operator new(0x18u);
            v13 = v12;
            if ( v12 )
            {
              *v12 = ATL::CComTypeInfoHolder::Cleanup;
              v12[1] = ATL::IDispatchImpl<ICtTuner,&_GUID const IID_ICtTuner,&_GUID const LIBID_cttunesvrLib,1,0,ATL::CComTypeInfoHolder>::_tih;
              EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 16));
              v13[2] = *(_QWORD *)(v11 + 8);
              *(_QWORD *)(v11 + 8) = v13;
              LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 16));
            }
            v10 = v14;
          }
          if ( v17 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
            v10 = v14;
          }
          if ( v10 )
            ((void (__fastcall *)(struct ITypeInfo *))v10->lpVtbl->Release)(v10);
        }
        ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
        v5 = (ATL::CComTypeInfoHolder *)v16;
        if ( v16 )
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v16)[2])(v16);
      }
      goto LABEL_31;
    }
    NameCache = -2147467259;
    ModuleFileNameW = GetModuleFileNameW(hInstance, Filename, 0x104u);
    if ( ModuleFileNameW && ModuleFileNameW != 260 )
    {
      v8 = LoadTypeLib(Filename, &pptlib);
      goto LABEL_14;
    }
  }
LABEL_31:
  if ( qword_14000B068 )
  {
    if ( !qword_14000B078 )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(v5, qword_14000B068);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v4 + 24));
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x1400031f4  push    rbp
0x1400031f6  push    rbx
0x1400031f7  push    rsi
0x1400031f8  push    rdi
0x1400031f9  push    r14
0x1400031fb  push    r15
0x1400031fd  lea     rbp, [rsp-178h]
0x140003205  sub     rsp, 278h
0x14000320c  mov     rax, cs:__security_cookie
0x140003213  xor     rax, rsp
0x140003216  mov     [rbp+1A0h+var_40], rax
0x14000321d  cmp     cs:qword_14000B068, 0
0x140003225  mov     ebx, edx
0x140003227  jz      short loc_14000323A
0x140003229  cmp     cs:qword_14000B078, 0
0x140003231  jz      short loc_14000323A
0x140003233  xor     eax, eax
0x140003235  jmp     loc_14000348B
0x14000323a  mov     r15, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003241  lea     rcx, [r15+18h]; lpCriticalSection
0x140003245  call    cs:__imp_EnterCriticalSection
0x14000324b  cmp     cs:qword_14000B068, 0
0x140003253  jnz     loc_140003460
0x140003259  mov     rcx, cs:rguid; rguid
0x140003260  mov     r8, cs:wVerMajor+2; wVerMinor
0x140003267  mov     rdx, cs:wVerMajor; wVerMajor
0x14000326e  mov     [rsp+2A0h+pptlib], 0
0x140003277  mov     eax, [rcx]
0x140003279  cmp     cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, eax; _GUID ATL::CAtlModule::m_libid ...
0x14000327f  jnz     short loc_1400032F3
0x140003281  mov     eax, [rcx+4]
0x140003284  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data2, eax; _GUID ATL::CAtlModule::m_libid ...
0x14000328a  jnz     short loc_1400032F3
0x14000328c  mov     eax, [rcx+8]
0x14000328f  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4, eax; _GUID ATL::CAtlModule::m_libid ...
0x140003295  jnz     short loc_1400032F3
0x140003297  mov     eax, [rcx+0Ch]
0x14000329a  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4+4, eax; _GUID ATL::CAtlModule::m_libid ...
0x1400032a0  jnz     short loc_1400032F3
0x1400032a2  mov     eax, 0FFFFh
0x1400032a7  cmp     dx, ax
0x1400032aa  jnz     short loc_1400032F3
0x1400032ac  cmp     r8w, ax
0x1400032b0  jnz     short loc_1400032F3
0x1400032b2  mov     rcx, cs:hInstance; hModule
0x1400032b9  lea     rdx, [rsp+2A0h+Filename]; lpFilename
0x1400032be  mov     ebx, 104h
0x1400032c3  mov     edi, 80004005h
0x1400032c8  mov     r8d, ebx; nSize
0x1400032cb  call    cs:__imp_GetModuleFileNameW
0x1400032d1  test    eax, eax
0x1400032d3  jz      loc_140003462
0x1400032d9  cmp     eax, ebx
0x1400032db  jz      loc_140003462
0x1400032e1  lea     rdx, [rsp+2A0h+pptlib]; pptlib
0x1400032e6  lea     rcx, [rsp+2A0h+Filename]; szFile
0x1400032eb  call    cs:__imp_LoadTypeLib
0x1400032f1  jmp     short loc_140003306
0x1400032f3  lea     rax, [rsp+2A0h+pptlib]
0x1400032f8  mov     r9d, ebx; lcid
0x1400032fb  mov     [rsp+2A0h+var_280], rax; pptlib
0x140003300  call    cs:__imp_LoadRegTypeLib
0x140003306  mov     edi, eax
0x140003308  test    eax, eax
0x14000330a  js      loc_140003462
0x140003310  mov     rcx, [rsp+2A0h+pptlib]
0x140003315  lea     r8, [rsp+2A0h+var_260]
0x14000331a  mov     rdx, cs:?_tih@?$IDispatchImpl@UICtTuner@@$1?IID_ICtTuner@@3U_GUID@@B$1?LIBID_cttunesvrLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; ATL::CComTypeInfoHolder ATL::IDispatchImpl<ICtTuner,&_GUID const IID_ICtTuner,&_GUID const LIBID_cttunesvrLib,1,0,ATL::CComTypeInfoHolder>::_tih
0x140003321  mov     [rsp+2A0h+var_260], 0
0x14000332a  mov     rax, [rcx]
0x14000332d  mov     rax, [rax+30h]
0x140003331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003336  mov     edi, eax
0x140003338  test    eax, eax
0x14000333a  js      loc_140003437
0x140003340  mov     rcx, [rsp+2A0h+var_260]
0x140003345  mov     [rsp+2A0h+var_270], rcx
0x14000334a  test    rcx, rcx
0x14000334d  jz      short loc_140003360
0x14000334f  mov     rax, [rcx]
0x140003352  mov     rax, [rax+8]
0x140003356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000335b  mov     rcx, [rsp+2A0h+var_260]
0x140003360  mov     [rsp+2A0h+var_258], 0
0x140003369  lea     r8, [rsp+2A0h+var_258]
0x14000336e  mov     rax, [rcx]
0x140003371  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x140003378  mov     rax, [rax]
0x14000337b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003380  test    eax, eax
0x140003382  js      short loc_140003393
0x140003384  lea     rdx, [rsp+2A0h+var_258]
0x140003389  lea     rcx, [rsp+2A0h+var_270]
0x14000338e  call    ??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z; ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)
0x140003393  mov     rax, [rsp+2A0h+var_270]
0x140003398  xor     ecx, ecx
0x14000339a  mov     cs:qword_14000B068, rax
0x1400033a1  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400033a8  mov     [rsp+2A0h+var_270], rcx
0x1400033ad  lea     rdx, [rax+8]
0x1400033b1  neg     rax
0x1400033b4  sbb     r14, r14
0x1400033b7  and     r14, rdx
0x1400033ba  jz      short loc_140003408
0x1400033bc  mov     ecx, 18h; Size
0x1400033c1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400033c6  mov     rsi, rax
0x1400033c9  test    rax, rax
0x1400033cc  jz      short loc_140003403
0x1400033ce  lea     rax, ?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z; ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)
0x1400033d5  mov     [rsi], rax
0x1400033d8  lea     rcx, [r14+10h]; lpCriticalSection
0x1400033dc  lea     rax, ?_tih@?$IDispatchImpl@UICtTuner@@$1?IID_ICtTuner@@3U_GUID@@B$1?LIBID_cttunesvrLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; ATL::CComTypeInfoHolder ATL::IDispatchImpl<ICtTuner,&_GUID const IID_ICtTuner,&_GUID const LIBID_cttunesvrLib,1,0,ATL::CComTypeInfoHolder>::_tih
0x1400033e3  mov     [rsi+8], rax
0x1400033e7  call    cs:__imp_EnterCriticalSection
0x1400033ed  mov     rcx, [r14+8]
0x1400033f1  mov     [rsi+10h], rcx
0x1400033f5  lea     rcx, [r14+10h]; lpCriticalSection
0x1400033f9  mov     [r14+8], rsi
0x1400033fd  call    cs:__imp_LeaveCriticalSection
0x140003403  mov     rcx, [rsp+2A0h+var_270]
0x140003408  mov     rdx, [rsp+2A0h+var_258]
0x14000340d  test    rdx, rdx
0x140003410  jz      short loc_140003426
0x140003412  mov     rax, [rdx]
0x140003415  mov     rcx, rdx
0x140003418  mov     rax, [rax+10h]
0x14000341c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003421  mov     rcx, [rsp+2A0h+var_270]
0x140003426  test    rcx, rcx
0x140003429  jz      short loc_140003437
0x14000342b  mov     rax, [rcx]
0x14000342e  mov     rax, [rax+10h]
0x140003432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003437  mov     rcx, [rsp+2A0h+pptlib]
0x14000343c  mov     rax, [rcx]
0x14000343f  mov     rax, [rax+10h]
0x140003443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003448  mov     rcx, [rsp+2A0h+var_260]
0x14000344d  test    rcx, rcx
0x140003450  jz      short loc_140003462
0x140003452  mov     rax, [rcx]
0x140003455  mov     rax, [rax+10h]
0x140003459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000345e  jmp     short loc_140003462
0x140003460  xor     edi, edi
0x140003462  mov     rdx, cs:qword_14000B068; struct ITypeInfo *
0x140003469  test    rdx, rdx
0x14000346c  jz      short loc_14000347F
0x14000346e  cmp     cs:qword_14000B078, 0
0x140003476  jnz     short loc_14000347F
0x140003478  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x14000347d  mov     edi, eax
0x14000347f  lea     rcx, [r15+18h]; lpCriticalSection
0x140003483  call    cs:__imp_LeaveCriticalSection
0x140003489  mov     eax, edi
0x14000348b  mov     rcx, [rbp+1A0h+var_40]
0x140003492  xor     rcx, rsp; StackCookie
0x140003495  call    __security_check_cookie
0x14000349a  add     rsp, 278h
0x1400034a1  pop     r15
0x1400034a3  pop     r14
0x1400034a5  pop     rdi
0x1400034a6  pop     rsi
0x1400034a7  pop     rbx
0x1400034a8  pop     rbp
0x1400034a9  retn
```
