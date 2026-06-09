# CreateNdrTypeInfoFromTypeInfo(ITypeInfo *,_GUID const &,_GUID const &,ushort,tagMethodInfo const *,NdrTypeInfo * *)

- ea: `0x18003fa00`
- end: `0x18003ff84`
- name: `?CreateNdrTypeInfoFromTypeInfo@@YAJPEAUITypeInfo@@AEBU_GUID@@1GPEBUtagMethodInfo@@PEAPEAUNdrTypeInfo@@@Z`
- size: `1412`
- prototype: `HRESULT __fastcall(ITypeInfo *typeInfoForDocumentation, const _GUID *iid, const _GUID *iidBase, unsigned __int16 methodCount, const tagMethodInfo *methodInfo, NdrTypeInfo **ndrTypeInfo)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013414`

## callees

- `0x18001217c`
- `0x180016c0c`
- `0x1800263b8`
- `0x180028100`
- `0x180028908`
- `0x18003586c`
- `0x18003fa00`
- `0x180042e00`
- `0x180047484`
- `0x180060e1c`
- `0x1800d8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fd9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fe68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fae0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fd9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003fe68`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003fc39`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003ff55`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003fc39`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003ff55`
- `RPCRT4!NdrpGetTypeGenCookie` at `0x18003fb30`
- `RPCRT4!NdrpGetTypeGenCookie` at `0x18003fb30`
- `RPCRT4!NdrpGetProcFormatString` at `0x18003fbb4`
- `RPCRT4!NdrpGetProcFormatString` at `0x18003fbb4`
- `RPCRT4!NdrpGetTypeFormatString` at `0x18003fbfb`
- `RPCRT4!NdrpGetTypeFormatString` at `0x18003fbfb`
- `RPCRT4!NdrpVarVtOfTypeDesc` at `0x18003fea6`
- `RPCRT4!NdrpVarVtOfTypeDesc` at `0x18003fea6`

## string_xrefs

- `0x18003fa53`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18003fb4e`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18003fc1d`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18003fd4c`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18003ff18`: `com\ole32\com\txf\callframe\typeinfo.cpp`

## pseudocode

```c
__int64 __fastcall CreateNdrTypeInfoFromTypeInfo(
        ITypeInfo *typeInfoForDocumentation,
        const _GUID *iid,
        const _GUID *iidBase,
        unsigned __int16 methodCount,
        const tagMethodInfo *methodInfo,
        NdrTypeInfo **ndrTypeInfo)
{
  __int64 v6; // r14
  unsigned __int16 v7; // si
  HRESULT v8; // ebx
  const tagMethodInfo *v9; // r13
  unsigned int v10; // edx
  const tagMethodInfo *v11; // r8
  __int64 v12; // r9
  NdrTypeInfo *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdi
  unsigned int v16; // edx
  HRESULT v17; // r9d
  int TypeGenCookie; // eax
  unsigned __int16 v19; // r12
  unsigned __int16 i; // r15
  tagFUNCDESC *pFuncDesc; // r8
  ITypeInfo *pTypeInfo; // rdx
  HRESULT ProcFormatString; // eax
  OLEAUTOMATION_FUNCTIONS *v24; // rcx
  unsigned int v25; // edx
  wchar_t *m_ptr; // r8
  __int64 v27; // r15
  unsigned int v28; // edx
  char *v29; // rax
  void *v30; // rax
  tagFUNCDESC *v31; // r13
  ITypeInfo *v32; // rcx
  __int64 v33; // r12
  struct IUnknownVtbl *lpVtbl; // rax
  wchar_t *v35; // rax
  __int64 cParams; // rax
  LPVOID v37; // rax
  __int16 v38; // r13
  __int64 v39; // rdx
  __int64 v40; // rdx
  unsigned int v41; // edx
  __int64 vt; // [rsp+48h] [rbp-49h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > bstrInterfaceName; // [rsp+50h] [rbp-41h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > bstrMethodName; // [rsp+58h] [rbp-39h] BYREF
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > typeFormatStringLength; // [rsp+60h] [rbp-31h] BYREF
  const unsigned __int8 *typeFormatString; // [rsp+68h] [rbp-29h] BYREF
  wil::com_ptr_t<NdrTypeInfo,wil::err_returncode_policy> localNdrTypeInfo; // [rsp+70h] [rbp-21h] BYREF
  wil::com_ptr_t<NdrTypeInfo,wil::err_returncode_policy> v49; // [rsp+78h] [rbp-19h] BYREF
  tagFUNCDESC *v50; // [rsp+80h] [rbp-11h]
  ITypeInfo *v51; // [rsp+88h] [rbp-9h]
  void *retaddr; // [rsp+E0h] [rbp+4Fh]
  unsigned __int16 lengthOfProc; // [rsp+100h] [rbp+6Fh] BYREF

  v6 = methodCount;
  v7 = 3;
  *ndrTypeInfo = 0;
  if ( methodCount < 3u )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x2E0u,
      "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp",
      -2147418113,
      "Fewer methods than IUnknown");
    return (unsigned int)v8;
  }
  v9 = methodInfo;
  v10 = 0;
  if ( methodCount > 3u )
  {
    v11 = methodInfo + 3;
    v12 = (unsigned __int16)(methodCount - 3);
    do
    {
      if ( v11->pFuncDesc )
        v10 += 6 * v11->pFuncDesc->cParams + 32;
      ++v11;
      --v12;
    }
    while ( v12 );
    if ( v10 > 0xFFFF )
    {
      v8 = -2147467259;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x2F8u,
        "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp",
        -2147467259,
        "Format string too large");
      return (unsigned int)v8;
    }
  }
  v13 = (NdrTypeInfo *)CoTaskMemAlloc(v10 + 2 * (_DWORD)v6 - 2 + 400LL);
  if ( v13 )
  {
    NdrTypeInfo::NdrTypeInfo(v13);
    v15 = v14;
  }
  else
  {
    v15 = 0;
  }
  v49.m_ptr = (NdrTypeInfo *)v15;
  if ( !v15 )
  {
    v8 = -2147024882;
    v16 = 767;
    v17 = -2147024882;
LABEL_17:
    wil::details::in1diag3::Return_Hr(retaddr, v16, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v17);
    goto LABEL_61;
  }
  vt = 0;
  typeFormatStringLength.m_ptr = (wchar_t *)(v15 + 2 * (v6 + 196));
  TypeGenCookie = NdrpGetTypeGenCookie(&vt);
  v8 = TypeGenCookie;
  if ( TypeGenCookie < 0 )
  {
    v17 = TypeGenCookie;
    v16 = 774;
    goto LABEL_17;
  }
  v19 = 0;
  for ( i = 3; i < (unsigned __int16)v6; ++i )
  {
    if ( v9[i].pFuncDesc )
    {
      *(_WORD *)(v15 + 2LL * i + 392) = v19;
      pFuncDesc = v9[i].pFuncDesc;
      pTypeInfo = v9[i].pTypeInfo;
      lengthOfProc = 0;
      ProcFormatString = NdrpGetProcFormatString(
                           vt,
                           pTypeInfo,
                           pFuncDesc,
                           i,
                           (char *)typeFormatStringLength.m_ptr + v19,
                           &lengthOfProc);
      v8 = ProcFormatString;
      if ( ProcFormatString < 0 )
      {
        v25 = 793;
        goto LABEL_27;
      }
      v19 += lengthOfProc;
    }
    else
    {
      *(_WORD *)(v15 + 2LL * i + 392) = -1;
    }
  }
  localNdrTypeInfo.m_ptr = 0;
  LOWORD(typeFormatString) = 0;
  ProcFormatString = NdrpGetTypeFormatString(vt, &localNdrTypeInfo, &typeFormatString);
  v8 = ProcFormatString;
  if ( ProcFormatString < 0 )
  {
    v25 = 806;
LABEL_27:
    wil::details::in1diag3::Return_Hr(retaddr, v25, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", ProcFormatString);
    goto LABEL_28;
  }
  *(_GUID *)(v15 + 28) = *iid;
  *(_GUID *)(v15 + 64) = *iidBase;
  *(_QWORD *)(v15 + 88) = _LocalAlloc;
  *(_QWORD *)(v15 + 96) = _LocalFree;
  *(wil::com_ptr_t<NdrTypeInfo,wil::err_returncode_policy> *)(v15 + 144) = localNdrTypeInfo;
  *(_DWORD *)(v15 + 156) = 327682;
  *(_DWORD *)(v15 + 168) = 50331692;
  OLEAUTOMATION_FUNCTIONS::Load(v24);
  m_ptr = typeFormatStringLength.m_ptr;
  *(_QWORD *)(v15 + 184) = g_oa.UserMarshalRoutines;
  *(_QWORD *)(v15 + 232) = v15 + 80;
  *(_QWORD *)(v15 + 248) = m_ptr;
  *(_QWORD *)(v15 + 256) = v15 + 392;
  *(_QWORD *)(v15 + 296) = v15 + 28;
  *(_QWORD *)(v15 + 304) = v15 + 232;
  *(_DWORD *)(v15 + 312) = v6;
  *(_QWORD *)(v15 + 328) = v15 + 80;
  *(_QWORD *)(v15 + 336) = m_ptr;
  *(_QWORD *)(v15 + 344) = v15 + 392;
  *(_QWORD *)(v15 + 376) = v15 + 328;
  *(_QWORD *)(v15 + 384) = v15 + 28;
  bstrMethodName.m_ptr = 0;
  v27 = -1;
  v8 = ((__int64 (__fastcall *)(ITypeInfo *, __int64, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *, _QWORD, _QWORD, _QWORD))typeInfoForDocumentation->lpVtbl[4].QueryInterface)(
         typeInfoForDocumentation,
         0xFFFFFFFFLL,
         &bstrMethodName,
         0,
         0,
         0);
  if ( v8 < 0 )
  {
    v28 = 845;
LABEL_32:
    wil::details::in1diag3::Return_Hr(retaddr, v28, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v8);
    goto LABEL_33;
  }
  do
    ++v27;
  while ( bstrMethodName.m_ptr[v27] );
  v29 = ToUtf8(bstrMethodName.m_ptr, v27);
  *(_QWORD *)(v15 + 48) = v29;
  if ( !v29 )
  {
    v28 = 852;
LABEL_39:
    v8 = -2147024882;
    goto LABEL_32;
  }
  v30 = CoTaskMemAlloc((unsigned int)(24 * v6));
  *(_QWORD *)(v15 + 56) = v30;
  if ( !v30 )
  {
    v28 = 857;
    goto LABEL_39;
  }
  memset_0(v30, 0, (unsigned int)(24 * v6));
  if ( (unsigned __int16)v6 <= 3u )
  {
LABEL_58:
    v49.m_ptr = 0;
    *ndrTypeInfo = (NdrTypeInfo *)v15;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrMethodName);
    if ( vt )
      NdrpReleaseTypeGenCookie();
    v8 = 0;
    goto LABEL_61;
  }
  while ( 1 )
  {
    v31 = v9[v7].pFuncDesc;
    v32 = methodInfo[v7].pTypeInfo;
    v50 = v31;
    v51 = v32;
    if ( !v31 )
      goto LABEL_50;
    v33 = *(_QWORD *)(v15 + 56);
    HIDWORD(typeFormatString) = 0;
    lpVtbl = v32->lpVtbl;
    typeFormatStringLength.m_ptr = 0;
    v8 = ((__int64 (__fastcall *)(ITypeInfo *, _QWORD, wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *, __int64, char *))lpVtbl[2].AddRef)(
           v32,
           (unsigned int)v31->memid,
           &typeFormatStringLength,
           1,
           (char *)&typeFormatString + 4);
    if ( v8 < 0 )
    {
      v41 = 871;
      goto LABEL_57;
    }
    v35 = CopyString(typeFormatStringLength.m_ptr);
    *(_QWORD *)(v33 + 24LL * v7) = v35;
    if ( !v35 )
    {
      v41 = 874;
      goto LABEL_55;
    }
    cParams = v31->cParams;
    *(_WORD *)(v33 + 24LL * v7 + 8) = cParams;
    if ( (_WORD)cParams )
    {
      v37 = CoTaskMemAlloc(2 * cParams);
      *(_QWORD *)(v33 + 24LL * v7 + 16) = v37;
      if ( !v37 )
      {
        v41 = 880;
LABEL_55:
        v8 = -2147024882;
        goto LABEL_57;
      }
      v38 = 0;
      if ( *(__int16 *)(v33 + 24LL * v7 + 8) > 0 )
        break;
    }
LABEL_49:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&typeFormatStringLength);
LABEL_50:
    if ( ++v7 >= (unsigned __int16)v6 )
      goto LABEL_58;
    v9 = methodInfo;
  }
  while ( 1 )
  {
    v39 = (__int64)&v50->lprgelemdescParam[v38];
    LOWORD(bstrInterfaceName.m_ptr) = 0;
    v8 = NdrpVarVtOfTypeDesc(v51, v39, &bstrInterfaceName);
    if ( v8 < 0 )
      break;
    v40 = v38++;
    *(_WORD *)(*(_QWORD *)(v33 + 24LL * v7 + 16) + 2 * v40) = bstrInterfaceName.m_ptr;
    if ( v38 >= *(__int16 *)(v33 + 24LL * v7 + 8) )
      goto LABEL_49;
  }
  v41 = 885;
LABEL_57:
  wil::details::in1diag3::Return_Hr(retaddr, v41, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v8);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&typeFormatStringLength);
LABEL_33:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrMethodName);
LABEL_28:
  if ( vt )
    NdrpReleaseTypeGenCookie();
LABEL_61:
  wil::com_ptr_t<NdrTypeInfo,wil::err_returncode_policy>::~com_ptr_t<NdrTypeInfo,wil::err_returncode_policy>(&v49);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003fa00  mov     rax, rsp
0x18003fa03  mov     [rax+18h], iidBase
0x18003fa07  mov     [rax+10h], iid
0x18003fa0b  mov     [rax+8], typeInfoForDocumentation
0x18003fa0f  push    rbp
0x18003fa10  push    rbx
0x18003fa11  push    rsi
0x18003fa12  push    rdi
0x18003fa13  push    r12
0x18003fa15  push    r13
0x18003fa17  push    r14
0x18003fa19  push    r15
0x18003fa1b  lea     rbp, [rax-4Fh]
0x18003fa1f  sub     rsp, 98h
0x18003fa26  mov     rax, [rbp+47h+arg_28]
0x18003fa2a  xor     r15d, r15d
0x18003fa2d  movzx   r14d, methodCount
0x18003fa31  lea     esi, [r15+3]
0x18003fa35  mov     [rax], r15
0x18003fa38  cmp     r14w, si
0x18003fa3c  jnb     short loc_18003FA6C
0x18003fa3e  lea     rax, aFewerMethodsTh; "Fewer methods than IUnknown"
0x18003fa45  mov     ebx, 8000FFFFh
0x18003fa4a  mov     edx, 2E0h; lineNumber
0x18003fa4f  mov     typeInfoForDocumentation, [rbp+4Fh]; callerReturnAddress
0x18003fa53  lea     iidBase, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x18003fa5a  mov     r9d, ebx; hr
0x18003fa5d  mov     [rsp+0D0h+formatString], rax; formatString
0x18003fa62  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003fa67  jmp     loc_18003FF6D
0x18003fa6c  mov     r13, [rbp+47h+arg_20]
0x18003fa70  mov     edx, r15d
0x18003fa73  mov     ebx, 0FFFFh
0x18003fa78  mov     r11d, 1
0x18003fa7e  jbe     short loc_18003FAC6
0x18003fa80  movzx   eax, r14w
0x18003fa84  lea     iidBase, [r13+30h]
0x18003fa88  sub     ax, si
0x18003fa8b  movzx   r9d, ax
0x18003fa8f  mov     rax, [iidBase]
0x18003fa92  test    rax, rax
0x18003fa95  jz      short loc_18003FAA4
0x18003fa97  movsx   eax, word ptr [rax+24h]
0x18003fa9b  lea     ecx, [rax+rax*2]
0x18003fa9e  lea     edx, [iid+typeInfoForDocumentation*2]
0x18003faa1  add     edx, 20h ; ' '
0x18003faa4  add     iidBase, 10h
0x18003faa8  mov     eax, edx
0x18003faaa  sub     r9, r11
0x18003faad  jnz     short loc_18003FA8F
0x18003faaf  cmp     eax, ebx
0x18003fab1  jbe     short loc_18003FAC6
0x18003fab3  lea     rax, aFormatStringTo; "Format string too large"
0x18003faba  mov     ebx, 80004005h
0x18003fabf  mov     edx, 2F8h
0x18003fac4  jmp     short loc_18003FA4F
0x18003fac6  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[r14*2]
0x18003face  add     ecx, edx
0x18003fad0  add     typeInfoForDocumentation, 190h; cb
0x18003fad7  cmp     typeInfoForDocumentation, 190h
0x18003fade  jb      short loc_18003FAFE
0x18003fae0  call    cs:__imp_CoTaskMemAlloc
0x18003fae7  nop     dword ptr [rax+rax+00h]
0x18003faec  test    rax, rax
0x18003faef  jz      short loc_18003FAFE
0x18003faf1  mov     typeInfoForDocumentation, rax; this
0x18003faf4  call    ??0NdrTypeInfo@@QEAA@XZ; NdrTypeInfo::NdrTypeInfo(void)
0x18003faf9  mov     rdi, rax
0x18003fafc  jmp     short loc_18003FB01
0x18003fafe  mov     rdi, r15
0x18003fb01  mov     [rbp+47h+var_60.m_ptr], rdi
0x18003fb05  test    rdi, rdi
0x18003fb08  jnz     short loc_18003FB19
0x18003fb0a  mov     ebx, 8007000Eh
0x18003fb0f  mov     edx, 2FFh
0x18003fb14  mov     r9d, ebx
0x18003fb17  jmp     short loc_18003FB4A
0x18003fb19  lea     rax, [r14+0C4h]
0x18003fb20  mov     [rbp+47h+vt], r15
0x18003fb24  lea     rax, [rdi+rax*2]
0x18003fb28  lea     typeInfoForDocumentation, [rbp+47h+vt]
0x18003fb2c  mov     [rbp+47h+typeFormatStringLength], rax
0x18003fb30  call    cs:__imp_NdrpGetTypeGenCookie
0x18003fb37  nop     dword ptr [rax+rax+00h]
0x18003fb3c  mov     ebx, eax
0x18003fb3e  test    eax, eax
0x18003fb40  jns     short loc_18003FB5F
0x18003fb42  mov     r9d, eax; hr
0x18003fb45  mov     edx, 306h; lineNumber
0x18003fb4a  mov     typeInfoForDocumentation, [rbp+4Fh]; callerReturnAddress
0x18003fb4e  lea     iidBase, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x18003fb55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fb5a  jmp     loc_18003FF64
0x18003fb5f  movzx   r12d, r15w
0x18003fb63  movzx   r15d, si
0x18003fb67  cmp     si, r14w
0x18003fb6b  jnb     short loc_18003FBE3
0x18003fb6d  xor     ecx, ecx
0x18003fb6f  movzx   eax, r15w
0x18003fb73  mov     edx, eax
0x18003fb75  add     iid, iid
0x18003fb78  cmp     [r13+iid*8+0], typeInfoForDocumentation
0x18003fb7d  jz      short loc_18003FBCF
0x18003fb7f  mov     [rdi+rax*2+188h], r12w
0x18003fb88  movzx   r9d, r15w
0x18003fb8c  mov     iidBase, [r13+iid*8+0]
0x18003fb91  mov     iid, [r13+iid*8+8]
0x18003fb96  mov     [rbp+47h+lengthOfProc], cx
0x18003fb9a  lea     typeInfoForDocumentation, [rbp+47h+lengthOfProc]
0x18003fb9e  mov     [rsp+28h], typeInfoForDocumentation
0x18003fba3  mov     typeInfoForDocumentation, [rbp+47h+vt]
0x18003fba7  movzx   eax, r12w
0x18003fbab  add     rax, [rbp+47h+typeFormatStringLength]
0x18003fbaf  mov     [rsp+0D0h+formatString], rax
0x18003fbb4  call    cs:__imp_NdrpGetProcFormatString
0x18003fbbb  nop     dword ptr [rax+rax+00h]
0x18003fbc0  xor     ecx, ecx
0x18003fbc2  mov     ebx, eax
0x18003fbc4  test    eax, eax
0x18003fbc6  js      short loc_18003FC14
0x18003fbc8  add     r12w, [rbp+47h+lengthOfProc]
0x18003fbcd  jmp     short loc_18003FBD9
0x18003fbcf  or      word ptr [rdi+rax*2+188h], 0FFFFh
0x18003fbd9  inc     r15w
0x18003fbdd  cmp     r15w, r14w
0x18003fbe1  jb      short loc_18003FB6F
0x18003fbe3  mov     typeInfoForDocumentation, [rbp+47h+vt]
0x18003fbe7  lea     iidBase, [rbp+47h+typeFormatString]
0x18003fbeb  xor     r15d, r15d
0x18003fbee  lea     iid, [rbp+47h+localNdrTypeInfo]
0x18003fbf2  mov     [rbp+47h+localNdrTypeInfo.m_ptr], r15
0x18003fbf6  mov     word ptr [rbp+47h+typeFormatString], r15w
0x18003fbfb  call    cs:__imp_NdrpGetTypeFormatString
0x18003fc02  nop     dword ptr [rax+rax+00h]
0x18003fc07  mov     ebx, eax
0x18003fc09  test    eax, eax
0x18003fc0b  jns     short loc_18003FC4A
0x18003fc0d  mov     edx, 326h
0x18003fc12  jmp     short loc_18003FC19
0x18003fc14  mov     edx, 319h; lineNumber
0x18003fc19  mov     typeInfoForDocumentation, [rbp+4Fh]; callerReturnAddress
0x18003fc1d  lea     iidBase, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x18003fc24  mov     r9d, eax; hr
0x18003fc27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fc2c  mov     typeInfoForDocumentation, [rbp+47h+vt]
0x18003fc30  test    typeInfoForDocumentation, typeInfoForDocumentation
0x18003fc33  jz      loc_18003FF64
0x18003fc39  call    cs:__imp_NdrpReleaseTypeGenCookie
0x18003fc40  nop     dword ptr [rax+rax+00h]
0x18003fc45  jmp     loc_18003FF64
0x18003fc4a  mov     rax, [rbp+47h+arg_8]
0x18003fc4e  lea     rbx, [rdi+1Ch]
0x18003fc52  movups  xmm0, xmmword ptr [rax]
0x18003fc55  mov     rax, [rbp+47h+arg_10]
0x18003fc59  movdqu  xmmword ptr [rbx], xmm0
0x18003fc5d  movups  xmm0, xmmword ptr [rax]
0x18003fc60  lea     rax, ?_LocalAlloc@@YAPEAX_K@Z; _LocalAlloc(unsigned __int64)
0x18003fc67  movdqu  xmmword ptr [rdi+40h], xmm0
0x18003fc6c  mov     [rdi+58h], rax
0x18003fc70  lea     rax, ?_LocalFree@@YAXPEAX@Z; _LocalFree(void *)
0x18003fc77  mov     [rdi+60h], rax
0x18003fc7b  mov     rax, [rbp+47h+localNdrTypeInfo.m_ptr]
0x18003fc7f  mov     [rdi+90h], rax
0x18003fc86  mov     dword ptr [rdi+9Ch], 50002h
0x18003fc90  mov     dword ptr [rdi+0A8h], 300002Ch
0x18003fc9a  call    ?Load@OLEAUTOMATION_FUNCTIONS@@AEAAXXZ; OLEAUTOMATION_FUNCTIONS::Load(void)
0x18003fc9f  mov     iidBase, [rbp+47h+typeFormatStringLength]
0x18003fca3  lea     iid, [rdi+50h]
0x18003fca7  lea     typeInfoForDocumentation, [rdi+188h]
0x18003fcae  mov     [rsp+28h], r15
0x18003fcb3  lea     rax, ?g_oa@@3UOLEAUTOMATION_FUNCTIONS@@A.UserMarshalRoutines; OLEAUTOMATION_FUNCTIONS g_oa ...
0x18003fcba  mov     [rsp+0D0h+formatString], r15
0x18003fcbf  mov     [rdi+0B8h], rax
0x18003fcc6  xor     r9d, r9d
0x18003fcc9  lea     rax, [rdi+0E8h]
0x18003fcd0  mov     [rax], iid
0x18003fcd3  mov     [rdi+0F8h], iidBase
0x18003fcda  mov     [rdi+100h], typeInfoForDocumentation
0x18003fce1  mov     [rdi+128h], rbx
0x18003fce8  mov     [rdi+130h], rax
0x18003fcef  lea     rax, [rdi+148h]
0x18003fcf6  mov     [rdi+138h], r14d
0x18003fcfd  mov     [rax], iid
0x18003fd00  mov     [rdi+150h], iidBase
0x18003fd07  lea     iidBase, [rbp+47h+bstrMethodName]
0x18003fd0b  mov     [rdi+158h], typeInfoForDocumentation
0x18003fd12  mov     typeInfoForDocumentation, [rbp+47h+arg_0]
0x18003fd16  mov     [rdi+178h], rax
0x18003fd1d  mov     [rdi+180h], rbx
0x18003fd24  mov     [rbp+47h+bstrMethodName.m_ptr], r15
0x18003fd28  or      r15, 0FFFFFFFFFFFFFFFFh
0x18003fd2c  mov     rax, [typeInfoForDocumentation]
0x18003fd2f  mov     edx, r15d
0x18003fd32  mov     rax, [rax+60h]
0x18003fd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd3b  mov     ebx, eax
0x18003fd3d  xor     eax, eax
0x18003fd3f  test    ebx, ebx
0x18003fd41  jns     short loc_18003FD69
0x18003fd43  mov     edx, 34Dh; lineNumber
0x18003fd48  mov     typeInfoForDocumentation, [rbp+4Fh]; callerReturnAddress
0x18003fd4c  lea     iidBase, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x18003fd53  mov     r9d, ebx; hr
0x18003fd56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fd5b  lea     typeInfoForDocumentation, [rbp+47h+bstrMethodName]; this
0x18003fd5f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003fd64  jmp     loc_18003FC2C
0x18003fd69  mov     typeInfoForDocumentation, [rbp+47h+bstrMethodName.m_ptr]; wsz
0x18003fd6d  inc     r15
0x18003fd70  cmp     [typeInfoForDocumentation+r15*2], ax
0x18003fd75  jnz     short loc_18003FD6D
0x18003fd77  mov     iid, r15; cch
0x18003fd7a  call    ?ToUtf8@@YAPEADPEBGK@Z; ToUtf8(ushort const *,ulong)
0x18003fd7f  xor     r15d, r15d
0x18003fd82  mov     [rdi+30h], rax
0x18003fd86  test    rax, rax
0x18003fd89  jnz     short loc_18003FD92
0x18003fd8b  mov     edx, 354h
0x18003fd90  jmp     short loc_18003FDB7
0x18003fd92  lea     eax, [r14+r14*2]
0x18003fd96  shl     eax, 3
0x18003fd99  mov     ecx, eax; cb
0x18003fd9b  mov     ebx, eax
0x18003fd9d  call    cs:__imp_CoTaskMemAlloc
0x18003fda4  nop     dword ptr [rax+rax+00h]
0x18003fda9  mov     [rdi+38h], rax
0x18003fdad  test    rax, rax
0x18003fdb0  jnz     short loc_18003FDBE
0x18003fdb2  mov     edx, 359h
0x18003fdb7  mov     ebx, 8007000Eh
0x18003fdbc  jmp     short loc_18003FD48
0x18003fdbe  mov     iidBase, rbx; Size
0x18003fdc1  xor     edx, edx; Val
0x18003fdc3  mov     typeInfoForDocumentation, rax; void *
0x18003fdc6  call    memset_0
0x18003fdcb  cmp     si, r14w
0x18003fdcf  jnb     loc_18003FF38
0x18003fdd5  xor     ebx, ebx
0x18003fdd7  mov     typeInfoForDocumentation, [rbp+47h+arg_20]
0x18003fddb  movzx   edx, si
0x18003fdde  mov     eax, edx
0x18003fde0  add     rax, rax
0x18003fde3  mov     r13, [r13+rax*8+0]
0x18003fde8  mov     typeInfoForDocumentation, [typeInfoForDocumentation+rax*8+8]
0x18003fded  mov     [rbp+47h+var_58], r13
0x18003fdf1  mov     [rbp+47h+var_50], typeInfoForDocumentation
0x18003fdf5  test    r13, r13
0x18003fdf8  jz      loc_18003FEE3
0x18003fdfe  mov     r12, [rdi+38h]
0x18003fe02  lea     r15, [iid+iid*2]
0x18003fe06  mov     dword ptr [rbp+47h+typeFormatString+4], ebx
0x18003fe09  lea     iid, [rbp+47h+typeFormatString+4]
0x18003fe0d  mov     rax, [typeInfoForDocumentation]
0x18003fe10  lea     iidBase, [rbp+47h+typeFormatStringLength]
0x18003fe14  mov     [rbp+47h+typeFormatStringLength], rbx
0x18003fe18  mov     r9d, 1
0x18003fe1e  mov     [rsp+0D0h+formatString], iid
0x18003fe23  mov     edx, [r13+0]
0x18003fe27  mov     rax, [rax+38h]
0x18003fe2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe30  mov     ebx, eax
0x18003fe32  test    eax, eax
0x18003fe34  js      loc_18003FF0F
0x18003fe3a  mov     typeInfoForDocumentation, [rbp+47h+typeFormatStringLength]; wszFrom
0x18003fe3e  call    ?CopyString@@YAPEAGPEBG@Z; CopyString(ushort const *)
0x18003fe43  xor     ebx, ebx
0x18003fe45  mov     [r12+r15*8], rax
0x18003fe49  test    rax, rax
0x18003fe4c  jz      loc_18003FF03
0x18003fe52  movsx   rax, word ptr [r13+24h]
0x18003fe57  mov     [r12+r15*8+8], ax
0x18003fe5d  test    ax, ax
0x18003fe60  jz      short loc_18003FEDA
0x18003fe62  mov     typeInfoForDocumentation, rax
0x18003fe65  add     typeInfoForDocumentation, typeInfoForDocumentation; cb
0x18003fe68  call    cs:__imp_CoTaskMemAlloc
0x18003fe6f  nop     dword ptr [rax+rax+00h]
0x18003fe74  mov     [r12+r15*8+10h], rax
0x18003fe79  test    rax, rax
0x18003fe7c  jz      short loc_18003FEFC
0x18003fe7e  movzx   r13d, bx
0x18003fe82  cmp     bx, [r12+r15*8+8]
0x18003fe88  jge     short loc_18003FEDA
0x18003fe8a  mov     rax, [rbp+47h+var_58]
0x18003fe8e  lea     iidBase, [rbp+47h+bstrInterfaceName]
0x18003fe92  mov     typeInfoForDocumentation, [rbp+47h+var_50]
0x18003fe96  movsx   iid, r13w
0x18003fe9a  shl     iid, 5
0x18003fe9e  add     iid, [rax+10h]
0x18003fea2  mov     word ptr [rbp+47h+bstrInterfaceName.m_ptr], bx
0x18003fea6  call    cs:__imp_NdrpVarVtOfTypeDesc
0x18003fead  nop     dword ptr [rax+rax+00h]
0x18003feb2  mov     ebx, eax
0x18003feb4  test    eax, eax
0x18003feb6  js      short loc_18003FEF5
0x18003feb8  mov     typeInfoForDocumentation, [r12+r15*8+10h]
0x18003febd  mov     ebx, 0
0x18003fec2  movzx   eax, word ptr [rbp+47h+bstrInterfaceName.m_ptr]
0x18003fec6  movsx   iid, r13w
0x18003feca  inc     r13w
  ... truncated ...
```
