# ATL::CComTypeInfoHolder::GetTI(ulong)

- ea: `0x180010020`
- end: `0x1800102a5`
- name: `?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z`
- size: `645`
- prototype: `__int64 __fastcall(ATL::CComTypeInfoHolder *this, LCID)`
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000fee0`
- `0x1800102b0`
- `0x1800104a0`

## callees

- `0x18000d450`
- `0x18000eab8`
- `0x180010020`
- `0x18001053c`
- `0x1800181e0`
- `0x180019010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18001007b`
- `KERNEL32!EnterCriticalSection` at `0x18001007b`
- `KERNEL32!GetModuleFileNameW` at `0x180010104`
- `KERNEL32!GetModuleFileNameW` at `0x180010104`
- `KERNEL32!LeaveCriticalSection` at `0x180010279`
- `KERNEL32!LeaveCriticalSection` at `0x180010279`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180010127`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180010127`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18001013c`
- `OLEAUT32!__imp_LoadRegTypeLib` at `0x18001013c`

## pseudocode

```c
__int64 __fastcall ATL::CComTypeInfoHolder::GetTI(ATL::CComTypeInfoHolder *this, LCID a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  ATL::CComTypeInfoHolder *v5; // rcx
  int NameCache; // ebx
  DWORD ModuleFileNameW; // eax
  HRESULT v8; // eax
  int (__fastcall ***v9)(_QWORD, GUID *, _QWORD); // rcx
  unsigned __int64 v10; // r8
  struct ITypeInfo *v11; // rax
  struct ITypeInfo *v12; // [rsp+30h] [rbp-D0h] BYREF
  ITypeLib *pptlib; // [rsp+38h] [rbp-C8h] BYREF
  int (__fastcall ***v14)(_QWORD, GUID *, _QWORD); // [rsp+40h] [rbp-C0h] BYREF
  void (__fastcall ***v15[2])(_QWORD, GUID *, __int64); // [rsp+48h] [rbp-B8h] BYREF
  char v16; // [rsp+58h] [rbp-A8h]
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  if ( qword_1800242B8 && qword_1800242C8 )
    return 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)ATL::_pAtlModule + 24);
  v15[1] = (void (__fastcall ***)(_QWORD, GUID *, __int64))((char *)ATL::_pAtlModule + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  v16 = 1;
  if ( qword_1800242B8 )
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
        v14 = 0;
        NameCache = ((__int64 (__fastcall *)(ITypeLib *, GUID *, _QWORD))pptlib->lpVtbl->GetTypeInfoOfGuid)(
                      pptlib,
                      ATL::IDispatchImpl<IIasComponent,&__s_GUID const _GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d,&__s_GUID const _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,1,0,ATL::CComTypeInfoHolder>::_tih[0],
                      &v14);
        if ( NameCache >= 0 )
        {
          v9 = v14;
          v12 = (struct ITypeInfo *)v14;
          if ( v14 )
          {
            ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v14)[1])(v14);
            v9 = v14;
          }
          v15[0] = 0;
          if ( (**v9)(v9, &GUID_00020412_0000_0000_c000_000000000046, v15) >= 0 )
            ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(&v12, v15);
          v11 = v12;
          v12 = 0;
          qword_1800242B8 = v11;
          ATL::AtlModuleAddTermFunc(
            (struct ATL::_ATL_MODULE70 *)(((unsigned __int64)ATL::_pAtlModule + 8) & -(__int64)(ATL::_pAtlModule != 0)),
            (void (*)(unsigned __int64))((char *)ATL::_pAtlModule + 8),
            v10);
          if ( v15[0] )
            (*((void (__fastcall **)(void (__fastcall ***)(_QWORD, GUID *, __int64)))*v15[0] + 2))(v15[0]);
          if ( v12 )
            ((void (__fastcall *)(struct ITypeInfo *))v12->lpVtbl->Release)(v12);
        }
        ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
        v5 = (ATL::CComTypeInfoHolder *)v14;
        if ( v14 )
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, _QWORD)))(*v14)[2])(v14);
      }
      goto LABEL_28;
    }
    NameCache = -2147467259;
    ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
    if ( ModuleFileNameW && ModuleFileNameW != 260 )
    {
      v8 = LoadTypeLib(Filename, &pptlib);
      goto LABEL_14;
    }
  }
LABEL_28:
  if ( qword_1800242B8 )
  {
    if ( !qword_1800242C8 )
      NameCache = ATL::CComTypeInfoHolder::LoadNameCache(v5, qword_1800242B8);
  }
  LeaveCriticalSection(v4);
  return (unsigned int)NameCache;
}

```

## disassembly

```asm
0x180010020  mov     [rsp-8+arg_0], rbx
0x180010025  mov     [rsp-8+arg_10], rdi
0x18001002a  push    rbp
0x18001002b  lea     rbp, [rsp-180h]
0x180010033  sub     rsp, 280h
0x18001003a  mov     rax, cs:__security_cookie
0x180010041  xor     rax, rsp
0x180010044  mov     [rbp+180h+var_10], rax
0x18001004b  mov     ebx, edx
0x18001004d  cmp     cs:qword_1800242B8, 0
0x180010055  jz      short loc_180010068
0x180010057  cmp     cs:qword_1800242C8, 0
0x18001005f  jz      short loc_180010068
0x180010061  xor     eax, eax
0x180010063  jmp     loc_180010281
0x180010068  mov     rdi, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001006f  add     rdi, 18h
0x180010073  mov     [rsp+280h+var_230], rdi
0x180010078  mov     rcx, rdi; lpCriticalSection
0x18001007b  call    cs:__imp_EnterCriticalSection
0x180010081  mov     [rsp+280h+var_228], 1
0x180010086  cmp     cs:qword_1800242B8, 0
0x18001008e  jnz     loc_180010257
0x180010094  mov     [rsp+280h+pptlib], 0
0x18001009d  mov     r8, cs:wVerMajor+2; wVerMinor
0x1800100a4  mov     rdx, cs:wVerMajor; wVerMajor
0x1800100ab  mov     rcx, cs:rguid; rguid
0x1800100b2  mov     eax, [rcx]
0x1800100b4  cmp     cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data1, eax; _GUID ATL::CAtlModule::m_libid ...
0x1800100ba  jnz     short loc_18001012F
0x1800100bc  mov     eax, [rcx+4]
0x1800100bf  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data2, eax; _GUID ATL::CAtlModule::m_libid ...
0x1800100c5  jnz     short loc_18001012F
0x1800100c7  mov     eax, [rcx+8]
0x1800100ca  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4, eax; _GUID ATL::CAtlModule::m_libid ...
0x1800100d0  jnz     short loc_18001012F
0x1800100d2  mov     eax, [rcx+0Ch]
0x1800100d5  cmp     dword ptr cs:?m_libid@CAtlModule@ATL@@2U_GUID@@A.Data4+4, eax; _GUID ATL::CAtlModule::m_libid ...
0x1800100db  jnz     short loc_18001012F
0x1800100dd  mov     eax, 0FFFFh
0x1800100e2  cmp     dx, ax
0x1800100e5  jnz     short loc_18001012F
0x1800100e7  cmp     r8w, ax
0x1800100eb  jnz     short loc_18001012F
0x1800100ed  mov     ebx, 80004005h
0x1800100f2  mov     r8d, 104h; nSize
0x1800100f8  lea     rdx, [rsp+280h+Filename]; lpFilename
0x1800100fd  mov     rcx, cs:hModule; hModule
0x180010104  call    cs:__imp_GetModuleFileNameW
0x18001010a  test    eax, eax
0x18001010c  jz      loc_180010259
0x180010112  cmp     eax, 104h
0x180010117  jz      loc_180010259
0x18001011d  lea     rdx, [rsp+280h+pptlib]; pptlib
0x180010122  lea     rcx, [rsp+280h+Filename]; szFile
0x180010127  call    cs:__imp_LoadTypeLib
0x18001012d  jmp     short loc_180010142
0x18001012f  lea     rax, [rsp+280h+pptlib]
0x180010134  mov     [rsp+280h+var_260], rax; pptlib
0x180010139  mov     r9d, ebx; lcid
0x18001013c  call    cs:__imp_LoadRegTypeLib
0x180010142  mov     ebx, eax
0x180010144  test    eax, eax
0x180010146  js      loc_180010259
0x18001014c  mov     [rsp+280h+var_240], 0
0x180010155  mov     rcx, [rsp+280h+pptlib]
0x18001015a  mov     rax, [rcx]
0x18001015d  lea     r8, [rsp+280h+var_240]
0x180010162  mov     rdx, cs:?_tih@?$IDispatchImpl@UIIasComponent@@$1?_GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d@@3U__s_GUID@@B$1?_GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; ATL::CComTypeInfoHolder ATL::IDispatchImpl<IIasComponent,&__s_GUID const _GUID_6bc096b4_0ce6_11d1_baae_00c04fc2e20d,&__s_GUID const _GUID_6bc09690_0ce6_11d1_baae_00c04fc2e20d,1,0,ATL::CComTypeInfoHolder>::_tih
0x180010169  mov     rax, [rax+30h]
0x18001016d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010172  mov     ebx, eax
0x180010174  test    eax, eax
0x180010176  js      loc_18001022C
0x18001017c  mov     rcx, [rsp+280h+var_240]
0x180010181  mov     [rsp+280h+var_250], rcx
0x180010186  test    rcx, rcx
0x180010189  jz      short loc_18001019C
0x18001018b  mov     rax, [rcx]
0x18001018e  mov     rax, [rax+8]
0x180010192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010197  mov     rcx, [rsp+280h+var_240]
0x18001019c  mov     [rsp+280h+var_238], 0
0x1800101a5  mov     rax, [rcx]
0x1800101a8  lea     r8, [rsp+280h+var_238]
0x1800101ad  lea     rdx, _GUID_00020412_0000_0000_c000_000000000046
0x1800101b4  mov     rax, [rax]
0x1800101b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101bc  test    eax, eax
0x1800101be  js      short loc_1800101CF
0x1800101c0  lea     rdx, [rsp+280h+var_238]
0x1800101c5  lea     rcx, [rsp+280h+var_250]
0x1800101ca  call    ??$?4UITypeInfo2@@@?$CComPtr@UITypeInfo@@@ATL@@QEAAPEAUITypeInfo@@AEBV?$CComPtr@UITypeInfo2@@@1@@Z; ATL::CComPtr<ITypeInfo>::operator=<ITypeInfo2>(ATL::CComPtr<ITypeInfo2> const &)
0x1800101cf  mov     rax, [rsp+280h+var_250]
0x1800101d4  mov     [rsp+280h+var_250], 0
0x1800101dd  mov     cs:qword_1800242B8, rax
0x1800101e4  mov     rax, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800101eb  lea     rdx, [rax+8]; void (*)(unsigned __int64)
0x1800101ef  neg     rax
0x1800101f2  sbb     rcx, rcx
0x1800101f5  and     rcx, rdx; struct ATL::_ATL_MODULE70 *
0x1800101f8  call    ?AtlModuleAddTermFunc@ATL@@YAJPEAU_ATL_MODULE70@1@P6AX_K@Z1@Z; ATL::AtlModuleAddTermFunc(ATL::_ATL_MODULE70 *,void (*)(unsigned __int64),unsigned __int64)
0x1800101fd  nop
0x1800101fe  mov     rcx, [rsp+280h+var_238]
0x180010203  test    rcx, rcx
0x180010206  jz      short loc_180010215
0x180010208  mov     rax, [rcx]
0x18001020b  mov     rax, [rax+10h]
0x18001020f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010214  nop
0x180010215  mov     rcx, [rsp+280h+var_250]
0x18001021a  test    rcx, rcx
0x18001021d  jz      short loc_18001022C
0x18001021f  mov     rax, [rcx]
0x180010222  mov     rax, [rax+10h]
0x180010226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001022b  nop
0x18001022c  mov     rcx, [rsp+280h+pptlib]
0x180010231  mov     rax, [rcx]
0x180010234  mov     rax, [rax+10h]
0x180010238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001023d  nop
0x18001023e  mov     rcx, [rsp+280h+var_240]
0x180010243  test    rcx, rcx
0x180010246  jz      short loc_180010255
0x180010248  mov     rax, [rcx]
0x18001024b  mov     rax, [rax+10h]
0x18001024f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010254  nop
0x180010255  jmp     short loc_180010259
0x180010257  xor     ebx, ebx
0x180010259  mov     rdx, cs:qword_1800242B8; struct ITypeInfo *
0x180010260  test    rdx, rdx
0x180010263  jz      short loc_180010276
0x180010265  cmp     cs:qword_1800242C8, 0
0x18001026d  jnz     short loc_180010276
0x18001026f  call    ?LoadNameCache@CComTypeInfoHolder@ATL@@QEAAJPEAUITypeInfo@@@Z; ATL::CComTypeInfoHolder::LoadNameCache(ITypeInfo *)
0x180010274  mov     ebx, eax
0x180010276  mov     rcx, rdi; lpCriticalSection
0x180010279  call    cs:__imp_LeaveCriticalSection
0x18001027f  mov     eax, ebx
0x180010281  mov     rcx, [rbp+180h+var_10]
0x180010288  xor     rcx, rsp; StackCookie
0x18001028b  call    __security_check_cookie
0x180010290  lea     r11, [rsp+280h+var_s0]
0x180010298  mov     rbx, [r11+10h]
0x18001029c  mov     rdi, [r11+20h]
0x1800102a0  mov     rsp, r11
0x1800102a3  pop     rbp
0x1800102a4  retn
```
