# CreateNdrTypeInfoFromTypeInfo(ITypeInfo *,_GUID const &,_GUID const &,ushort,tagMethodInfo const *,NdrTypeInfo * *)

- ea: `0x18003b968`
- end: `0x18003bf94`
- name: `?CreateNdrTypeInfoFromTypeInfo@@YAJPEAUITypeInfo@@AEBU_GUID@@1GPEBUtagMethodInfo@@PEAPEAUNdrTypeInfo@@@Z`
- size: `1580`
- prototype: `HRESULT __fastcall(ITypeInfo *typeInfoForDocumentation, const _GUID *iid, const _GUID *iidBase, unsigned __int16 methodCount, const tagMethodInfo *methodInfo, NdrTypeInfo **ndrTypeInfo)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016114`

## callees

- `0x180014780`
- `0x1800185ec`
- `0x18001a58c`
- `0x18001ddcc`
- `0x180022b88`
- `0x180032250`
- `0x18003b968`
- `0x18003febc`
- `0x180053014`
- `0x18006b1c8`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ba51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003bd03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003bdf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003ba51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003bd03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003bdf6`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003bb7f`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003bbab`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003bd3f`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003beb4`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003bf22`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003bf56`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003bb7f`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003bbab`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003bd3f`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003beb4`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003bf22`
- `RPCRT4!NdrpReleaseTypeGenCookie` at `0x18003bf56`
- `RPCRT4!NdrpGetTypeGenCookie` at `0x18003ba7c`
- `RPCRT4!NdrpGetTypeGenCookie` at `0x18003ba7c`
- `RPCRT4!NdrpGetProcFormatString` at `0x18003bb05`
- `RPCRT4!NdrpGetProcFormatString` at `0x18003bb05`
- `RPCRT4!NdrpGetTypeFormatString` at `0x18003bb4e`
- `RPCRT4!NdrpGetTypeFormatString` at `0x18003bb4e`
- `RPCRT4!NdrpVarVtOfTypeDesc` at `0x18003be34`
- `RPCRT4!NdrpVarVtOfTypeDesc` at `0x18003be34`

## string_xrefs

- `0x18003b9bf`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18003ba8c`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18003bb5e`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18003bb8e`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18003bcb0`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18003bd1b`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18003be85`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18003becf`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18003bef3`: `com\ole32\com\txf\callframe\typeinfo.cpp`
- `0x18003bf64`: `com\ole32\com\txf\callframe\typeinfo.cpp`

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
  unsigned __int16 v6; // r12
  __int64 v7; // r15
  const _GUID *v8; // rdi
  unsigned __int16 v9; // r14
  unsigned int v10; // ebx
  const tagMethodInfo *v12; // r13
  unsigned int v13; // r8d
  unsigned __int16 v14; // dx
  tagFUNCDESC *pFuncDesc; // rcx
  NdrTypeInfo *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rsi
  HRESULT TypeGenCookie; // eax
  unsigned __int16 v20; // bx
  wchar_t *m_ptr; // rcx
  HRESULT ProcFormatString; // eax
  HRESULT v23; // edi
  HRESULT v24; // eax
  OLEAUTOMATION_FUNCTIONS *v25; // rcx
  __int128 v26; // xmm0
  wchar_t *v27; // rdx
  __int64 v28; // rbx
  struct IUnknownVtbl *lpVtbl; // rax
  HRESULT v30; // eax
  char *v31; // rax
  unsigned int v32; // edx
  void *v33; // rax
  tagFUNCDESC *v34; // r13
  __int64 v35; // rdi
  __int64 memid; // rdx
  HRESULT v37; // eax
  HRESULT v38; // r12d
  wchar_t *v39; // rax
  __int16 v40; // r12
  __int64 cParams; // rax
  LPVOID v42; // rax
  HRESULT v43; // eax
  unsigned int v44; // edx
  __int64 vt; // [rsp+48h] [rbp-49h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > bstrInterfaceName; // [rsp+50h] [rbp-41h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > bstrMethodName; // [rsp+58h] [rbp-39h] BYREF
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > typeFormatStringLength; // [rsp+60h] [rbp-31h] BYREF
  _WORD v49[2]; // [rsp+68h] [rbp-29h] BYREF
  int v50; // [rsp+6Ch] [rbp-25h] BYREF
  const unsigned __int8 *typeFormatString; // [rsp+70h] [rbp-21h]
  __int64 v52; // [rsp+78h] [rbp-19h] BYREF
  ITypeInfo *pTypeInfo; // [rsp+80h] [rbp-11h]
  __int64 v54; // [rsp+88h] [rbp-9h]
  void *retaddr; // [rsp+E0h] [rbp+4Fh]
  unsigned __int16 lengthOfProc; // [rsp+100h] [rbp+6Fh] BYREF

  v6 = 0;
  v7 = methodCount;
  v8 = iid;
  v9 = 3;
  *ndrTypeInfo = 0;
  if ( methodCount < 3u )
  {
    v10 = -2147418113;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x2E0u,
      "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp",
      -2147418113,
      "Fewer methods than IUnknown");
    return v10;
  }
  v12 = methodInfo;
  v13 = 0;
  v14 = 3;
  if ( methodCount > 3u )
  {
    do
    {
      pFuncDesc = methodInfo[v14].pFuncDesc;
      if ( pFuncDesc )
        v13 += 6 * pFuncDesc->cParams + 32;
      ++v14;
    }
    while ( v14 < methodCount );
    if ( v13 > 0xFFFF )
    {
      v10 = -2147467259;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x2F8u,
        "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp",
        -2147467259,
        "Format string too large");
      return v10;
    }
  }
  v16 = (NdrTypeInfo *)CoTaskMemAlloc(v13 + 2 * methodCount - 2 + 400LL);
  if ( v16 && (NdrTypeInfo::NdrTypeInfo(v16), (v18 = v17) != 0) )
  {
    vt = 0;
    TypeGenCookie = NdrpGetTypeGenCookie(&vt);
    v10 = TypeGenCookie;
    if ( TypeGenCookie < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x306u, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", TypeGenCookie);
      goto LABEL_60;
    }
    v20 = 3;
    m_ptr = (wchar_t *)(v18 + 2 * (v7 + 196));
    typeFormatStringLength.m_ptr = m_ptr;
    if ( (unsigned __int16)v7 > 3u )
    {
      while ( 1 )
      {
        if ( v12[v20].pFuncDesc )
        {
          *(_WORD *)(v18 + 2LL * v20 + 392) = v6;
          lengthOfProc = 0;
          ProcFormatString = NdrpGetProcFormatString(
                               vt,
                               v12[v20].pTypeInfo,
                               v12[v20].pFuncDesc,
                               v20,
                               (char *)m_ptr + v6,
                               &lengthOfProc);
          v23 = ProcFormatString;
          if ( ProcFormatString < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              0x319u,
              "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp",
              ProcFormatString);
LABEL_25:
            if ( vt )
              NdrpReleaseTypeGenCookie();
            v10 = v23;
            goto LABEL_60;
          }
          v6 += lengthOfProc;
          m_ptr = typeFormatStringLength.m_ptr;
        }
        else
        {
          *(_WORD *)(v18 + 2LL * v20 + 392) = -1;
        }
        if ( ++v20 >= (unsigned __int16)v7 )
        {
          v8 = iid;
          break;
        }
      }
    }
    v52 = 0;
    v49[0] = 0;
    v24 = NdrpGetTypeFormatString(vt, &v52, v49);
    v10 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x326u, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v24);
      if ( vt )
        NdrpReleaseTypeGenCookie();
      goto LABEL_60;
    }
    *(_GUID *)(v18 + 28) = *v8;
    v26 = (__int128)*iidBase;
    *(_QWORD *)(v18 + 88) = _LocalAlloc;
    *(_QWORD *)(v18 + 96) = _LocalFree;
    *(_OWORD *)(v18 + 64) = v26;
    *(_QWORD *)(v18 + 144) = v52;
    *(_DWORD *)(v18 + 156) = 327682;
    *(_DWORD *)(v18 + 168) = 50331692;
    OLEAUTOMATION_FUNCTIONS::Load(v25);
    v27 = typeFormatStringLength.m_ptr;
    *(wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *)(v18 + 248) = typeFormatStringLength;
    *(_QWORD *)(v18 + 184) = g_oa.UserMarshalRoutines;
    *(_QWORD *)(v18 + 336) = v27;
    *(_QWORD *)(v18 + 232) = v18 + 80;
    *(_QWORD *)(v18 + 304) = v18 + 232;
    *(_QWORD *)(v18 + 256) = v18 + 392;
    *(_QWORD *)(v18 + 328) = v18 + 80;
    v28 = -1;
    *(_QWORD *)(v18 + 344) = v18 + 392;
    *(_QWORD *)(v18 + 376) = v18 + 328;
    *(_QWORD *)(v18 + 296) = v18 + 28;
    *(_DWORD *)(v18 + 312) = v7;
    *(_QWORD *)(v18 + 384) = v18 + 28;
    lpVtbl = typeInfoForDocumentation->lpVtbl;
    bstrMethodName.m_ptr = 0;
    v30 = ((__int64 (__fastcall *)(ITypeInfo *, __int64, wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > > *, _QWORD, _QWORD, _QWORD))lpVtbl[4].QueryInterface)(
            typeInfoForDocumentation,
            0xFFFFFFFFLL,
            &bstrMethodName,
            0,
            0,
            0);
    v23 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, 0x34Du, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v30);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrMethodName);
      goto LABEL_25;
    }
    do
      ++v28;
    while ( bstrMethodName.m_ptr[v28] );
    v31 = ToUtf8(bstrMethodName.m_ptr, v28);
    *(_QWORD *)(v18 + 48) = v31;
    if ( !v31 )
    {
      v32 = 852;
LABEL_35:
      wil::details::in1diag3::Return_Hr(retaddr, v32, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", -2147024882);
LABEL_36:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrMethodName);
      if ( vt )
        NdrpReleaseTypeGenCookie();
      v10 = -2147024882;
LABEL_60:
      CALLFRAME_CACHE_ENTRY<NdrTypeInfo>::Release((CALLFRAME_CACHE_ENTRY<NdrTypeInfo> *)v18, 1);
      return v10;
    }
    v33 = CoTaskMemAlloc((unsigned int)(24 * v7));
    *(_QWORD *)(v18 + 56) = v33;
    if ( !v33 )
    {
      v32 = 857;
      goto LABEL_35;
    }
    memset_0(v33, 0, (unsigned int)(24 * v7));
    if ( (unsigned __int16)v7 > 3u )
    {
      while ( 1 )
      {
        v34 = v12[v9].pFuncDesc;
        if ( v34 )
        {
          v35 = *(_QWORD *)(v18 + 56);
          typeFormatStringLength.m_ptr = 0;
          v50 = 0;
          memid = (unsigned int)v34->memid;
          pTypeInfo = methodInfo[v9].pTypeInfo;
          v37 = ((__int64 (__fastcall *)(ITypeInfo *, __int64, wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (__cdecl*)(unsigned short *),&SysFreeString,wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t> > *, __int64, int *))pTypeInfo->lpVtbl[2].AddRef)(
                  pTypeInfo,
                  memid,
                  &typeFormatStringLength,
                  1,
                  &v50);
          v38 = v37;
          if ( v37 < 0 )
          {
            wil::details::in1diag3::Return_Hr(retaddr, 0x367u, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v37);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&typeFormatStringLength);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrMethodName);
            if ( vt )
              NdrpReleaseTypeGenCookie();
            v10 = v38;
            goto LABEL_60;
          }
          v39 = CopyString(typeFormatStringLength.m_ptr);
          v40 = 0;
          *(_QWORD *)(v35 + 24LL * v9) = v39;
          if ( !v39 )
          {
            v44 = 874;
            goto LABEL_56;
          }
          cParams = v34->cParams;
          *(_WORD *)(v35 + 24LL * v9 + 8) = cParams;
          if ( (_WORD)cParams )
          {
            v42 = CoTaskMemAlloc(2 * cParams);
            *(_QWORD *)(v35 + 24LL * v9 + 16) = v42;
            if ( !v42 )
            {
              v44 = 880;
LABEL_56:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                v44,
                "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp",
                -2147024882);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&typeFormatStringLength);
              goto LABEL_36;
            }
            if ( *(__int16 *)(v35 + 24LL * v9 + 8) > 0 )
            {
              while ( 1 )
              {
                LOWORD(bstrInterfaceName.m_ptr) = 0;
                v54 = v40;
                v43 = NdrpVarVtOfTypeDesc(pTypeInfo, &v34->lprgelemdescParam[v40], &bstrInterfaceName);
                LODWORD(typeFormatString) = v43;
                if ( v43 < 0 )
                  break;
                ++v40;
                *(_WORD *)(*(_QWORD *)(v35 + 24LL * v9 + 16) + 2 * v54) = bstrInterfaceName.m_ptr;
                if ( v40 >= *(__int16 *)(v35 + 24LL * v9 + 8) )
                  goto LABEL_48;
              }
              wil::details::in1diag3::Return_Hr(retaddr, 0x375u, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", v43);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&typeFormatStringLength);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrMethodName);
              if ( vt )
                NdrpReleaseTypeGenCookie();
              v10 = (unsigned int)typeFormatString;
              goto LABEL_60;
            }
          }
LABEL_48:
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&typeFormatStringLength);
        }
        if ( ++v9 >= (unsigned __int16)v7 )
          break;
        v12 = methodInfo;
      }
    }
    *ndrTypeInfo = (NdrTypeInfo *)v18;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&bstrMethodName);
    if ( vt )
      NdrpReleaseTypeGenCookie();
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, 0x2FFu, "com\\ole32\\com\\txf\\callframe\\typeinfo.cpp", -2147024882);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18003b968  mov     rax, rsp
0x18003b96b  mov     [rax+18h], iidBase
0x18003b96f  mov     [rax+10h], iid
0x18003b973  mov     [rax+8], typeInfoForDocumentation
0x18003b977  push    rbp
0x18003b978  push    rbx
0x18003b979  push    rsi
0x18003b97a  push    rdi
0x18003b97b  push    r12
0x18003b97d  push    r13
0x18003b97f  push    r14
0x18003b981  push    r15
0x18003b983  lea     rbp, [rax-4Fh]
0x18003b987  sub     rsp, 98h
0x18003b98e  mov     rax, [rbp+47h+arg_28]
0x18003b992  xor     r12d, r12d
0x18003b995  movzx   r15d, methodCount
0x18003b999  mov     rdi, iid
0x18003b99c  lea     r14d, [r12+3]
0x18003b9a1  mov     [rax], r12
0x18003b9a4  cmp     r15w, r14w
0x18003b9a8  jnb     short loc_18003B9DA
0x18003b9aa  lea     rax, aFewerMethodsTh; "Fewer methods than IUnknown"
0x18003b9b1  mov     ebx, 8000FFFFh
0x18003b9b6  mov     edx, 2E0h; lineNumber
0x18003b9bb  mov     typeInfoForDocumentation, [rbp+4Fh]; callerReturnAddress
0x18003b9bf  lea     iidBase, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x18003b9c6  mov     r9d, ebx; hr
0x18003b9c9  mov     [rsp+0D0h+formatString], rax; formatString
0x18003b9ce  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003b9d3  mov     eax, ebx
0x18003b9d5  jmp     loc_18003BF80
0x18003b9da  mov     r13, [rbp+47h+arg_20]
0x18003b9de  mov     r8d, r12d
0x18003b9e1  movzx   edx, r14w
0x18003b9e5  mov     r10d, 1
0x18003b9eb  jbe     short loc_18003BA32
0x18003b9ed  movzx   eax, dx
0x18003b9f0  add     rax, rax
0x18003b9f3  mov     typeInfoForDocumentation, [r13+rax*8+0]
0x18003b9f8  test    typeInfoForDocumentation, typeInfoForDocumentation
0x18003b9fb  jz      short loc_18003BA0C
0x18003b9fd  movsx   eax, word ptr [typeInfoForDocumentation+24h]
0x18003ba01  lea     ecx, [rax+rax*2]
0x18003ba04  lea     r8d, [iidBase+typeInfoForDocumentation*2]
0x18003ba08  add     r8d, 20h ; ' '
0x18003ba0c  add     dx, r10w
0x18003ba10  cmp     dx, r15w
0x18003ba14  jb      short loc_18003B9ED
0x18003ba16  cmp     r8d, 0FFFFh
0x18003ba1d  jbe     short loc_18003BA32
0x18003ba1f  lea     rax, aFormatStringTo; "Format string too large"
0x18003ba26  mov     ebx, 80004005h
0x18003ba2b  mov     edx, 2F8h
0x18003ba30  jmp     short loc_18003B9BB
0x18003ba32  lea     ecx, ds:0FFFFFFFFFFFFFFFEh[r15*2]
0x18003ba3a  add     ecx, r8d
0x18003ba3d  add     typeInfoForDocumentation, 190h; cb
0x18003ba44  cmp     typeInfoForDocumentation, 190h
0x18003ba4b  jb      loc_18003BF60
0x18003ba51  call    cs:__imp_CoTaskMemAlloc
0x18003ba57  test    rax, rax
0x18003ba5a  jz      loc_18003BF60
0x18003ba60  mov     typeInfoForDocumentation, rax; this
0x18003ba63  call    ??0NdrTypeInfo@@QEAA@XZ; NdrTypeInfo::NdrTypeInfo(void)
0x18003ba68  mov     rsi, rax
0x18003ba6b  test    rax, rax
0x18003ba6e  jz      loc_18003BF60
0x18003ba74  lea     typeInfoForDocumentation, [rbp+47h+vt]
0x18003ba78  mov     [rbp+47h+vt], r12
0x18003ba7c  call    cs:__imp_NdrpGetTypeGenCookie
0x18003ba82  mov     ebx, eax
0x18003ba84  test    eax, eax
0x18003ba86  jns     short loc_18003BAA5
0x18003ba88  mov     typeInfoForDocumentation, [rbp+4Fh]; callerReturnAddress
0x18003ba8c  lea     iidBase, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x18003ba93  mov     r9d, eax; hr
0x18003ba96  mov     edx, 306h; lineNumber
0x18003ba9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003baa0  jmp     loc_18003BF2B
0x18003baa5  lea     typeInfoForDocumentation, [r15+0C4h]
0x18003baac  movzx   ebx, r14w
0x18003bab0  lea     typeInfoForDocumentation, [rsi+typeInfoForDocumentation*2]
0x18003bab4  mov     [rbp+47h+typeFormatStringLength], typeInfoForDocumentation
0x18003bab8  cmp     r14w, r15w
0x18003babc  jnb     short loc_18003BB36
0x18003babe  xor     r8d, r8d
0x18003bac1  movzx   eax, bx
0x18003bac4  mov     edx, eax
0x18003bac6  add     iid, iid
0x18003bac9  cmp     [r13+iid*8+0], iidBase
0x18003bace  jz      short loc_18003BB1F
0x18003bad0  mov     [rsi+rax*2+188h], r12w
0x18003bad9  movzx   r9d, bx
0x18003badd  mov     [rbp+47h+lengthOfProc], r8w
0x18003bae2  mov     iidBase, [r13+iid*8+0]
0x18003bae7  mov     iid, [r13+iid*8+8]
0x18003baec  movzx   eax, r12w
0x18003baf0  add     rax, typeInfoForDocumentation
0x18003baf3  lea     typeInfoForDocumentation, [rbp+47h+lengthOfProc]
0x18003baf7  mov     [rsp+28h], typeInfoForDocumentation
0x18003bafc  mov     typeInfoForDocumentation, [rbp+47h+vt]
0x18003bb00  mov     [rsp+0D0h+formatString], rax
0x18003bb05  call    cs:__imp_NdrpGetProcFormatString
0x18003bb0b  xor     r8d, r8d
0x18003bb0e  mov     edi, eax
0x18003bb10  test    eax, eax
0x18003bb12  js      short loc_18003BB8A
0x18003bb14  add     r12w, [rbp+47h+lengthOfProc]
0x18003bb19  mov     typeInfoForDocumentation, [rbp+47h+typeFormatStringLength]
0x18003bb1d  jmp     short loc_18003BB29
0x18003bb1f  mov     word ptr [rsi+rax*2+188h], 0FFFFh
0x18003bb29  inc     bx
0x18003bb2c  cmp     bx, r15w
0x18003bb30  jb      short loc_18003BAC1
0x18003bb32  mov     rdi, [rbp+47h+arg_8]
0x18003bb36  mov     typeInfoForDocumentation, [rbp+47h+vt]
0x18003bb3a  lea     iidBase, [rbp+47h+var_70]
0x18003bb3e  xor     r12d, r12d
0x18003bb41  lea     iid, [rbp+47h+var_60]
0x18003bb45  mov     [rbp+47h+var_60], r12
0x18003bb49  mov     [rbp+47h+var_70], r12w
0x18003bb4e  call    cs:__imp_NdrpGetTypeFormatString
0x18003bb54  mov     ebx, eax
0x18003bb56  test    eax, eax
0x18003bb58  jns     short loc_18003BBB8
0x18003bb5a  mov     typeInfoForDocumentation, [rbp+4Fh]; callerReturnAddress
0x18003bb5e  lea     iidBase, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x18003bb65  mov     r9d, eax; hr
0x18003bb68  mov     edx, 326h; lineNumber
0x18003bb6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bb72  mov     typeInfoForDocumentation, [rbp+47h+vt]
0x18003bb76  test    typeInfoForDocumentation, typeInfoForDocumentation
0x18003bb79  jz      loc_18003BF2B
0x18003bb7f  call    cs:__imp_NdrpReleaseTypeGenCookie
0x18003bb85  jmp     loc_18003BF2B
0x18003bb8a  mov     typeInfoForDocumentation, [rbp+4Fh]; callerReturnAddress
0x18003bb8e  lea     iidBase, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x18003bb95  mov     r9d, edi; hr
0x18003bb98  mov     edx, 319h; lineNumber
0x18003bb9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bba2  mov     typeInfoForDocumentation, [rbp+47h+vt]
0x18003bba6  test    typeInfoForDocumentation, typeInfoForDocumentation
0x18003bba9  jz      short loc_18003BBB1
0x18003bbab  call    cs:__imp_NdrpReleaseTypeGenCookie
0x18003bbb1  mov     ebx, edi
0x18003bbb3  jmp     loc_18003BF2B
0x18003bbb8  movups  xmm0, xmmword ptr [rdi]
0x18003bbbb  mov     rax, [rbp+47h+arg_10]
0x18003bbbf  lea     rdi, [rsi+1Ch]
0x18003bbc3  lea     rbx, [rsi+50h]
0x18003bbc7  movdqu  xmmword ptr [rdi], xmm0
0x18003bbcb  movups  xmm0, xmmword ptr [rax]
0x18003bbce  lea     rax, ?_LocalAlloc@@YAPEAX_K@Z; _LocalAlloc(unsigned __int64)
0x18003bbd5  mov     [rbx+8], rax
0x18003bbd9  lea     rax, ?_LocalFree@@YAXPEAX@Z; _LocalFree(void *)
0x18003bbe0  mov     [rsi+60h], rax
0x18003bbe4  movdqu  xmmword ptr [rsi+40h], xmm0
0x18003bbe9  mov     rax, [rbp+47h+var_60]
0x18003bbed  mov     [rsi+90h], rax
0x18003bbf4  mov     dword ptr [rsi+9Ch], 50002h
0x18003bbfe  mov     dword ptr [rsi+0A8h], 300002Ch
0x18003bc08  call    ?Load@OLEAUTOMATION_FUNCTIONS@@AEAAXXZ; OLEAUTOMATION_FUNCTIONS::Load(void)
0x18003bc0d  mov     iid, [rbp+47h+typeFormatStringLength]
0x18003bc11  lea     typeInfoForDocumentation, [rsi+188h]
0x18003bc18  mov     [rsi+0F8h], iid
0x18003bc1f  lea     rax, ?g_oa@@3UOLEAUTOMATION_FUNCTIONS@@A.UserMarshalRoutines; OLEAUTOMATION_FUNCTIONS g_oa ...
0x18003bc26  mov     [rsi+0B8h], rax
0x18003bc2d  lea     iidBase, [rbp+47h+bstrMethodName]
0x18003bc31  mov     [rsi+150h], iid
0x18003bc38  lea     rax, [rsi+0E8h]
0x18003bc3f  mov     [rax], rbx
0x18003bc42  xor     edx, edx
0x18003bc44  mov     [rsi+130h], rax
0x18003bc4b  xor     r9d, r9d
0x18003bc4e  mov     [rsi+100h], typeInfoForDocumentation
0x18003bc55  lea     rax, [rsi+148h]
0x18003bc5c  mov     [rax], rbx
0x18003bc5f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003bc63  mov     [rsi+158h], typeInfoForDocumentation
0x18003bc6a  mov     typeInfoForDocumentation, [rbp+47h+arg_0]
0x18003bc6e  mov     [rsi+178h], rax
0x18003bc75  mov     [rsi+128h], rdi
0x18003bc7c  mov     [rsi+138h], r15d
0x18003bc83  mov     [rsi+180h], rdi
0x18003bc8a  mov     rax, [typeInfoForDocumentation]
0x18003bc8d  mov     [rsp+28h], iid
0x18003bc92  mov     [rbp+47h+bstrMethodName.m_ptr], iid
0x18003bc96  mov     [rsp+0D0h+formatString], iid
0x18003bc9b  mov     edx, ebx
0x18003bc9d  mov     rax, [rax+60h]
0x18003bca1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bca6  mov     edi, eax
0x18003bca8  test    eax, eax
0x18003bcaa  jns     short loc_18003BCD2
0x18003bcac  mov     typeInfoForDocumentation, [rbp+4Fh]; callerReturnAddress
0x18003bcb0  lea     iidBase, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x18003bcb7  mov     r9d, eax; hr
0x18003bcba  mov     edx, 34Dh; lineNumber
0x18003bcbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bcc4  lea     typeInfoForDocumentation, [rbp+47h+bstrMethodName]; this
0x18003bcc8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003bccd  jmp     loc_18003BBA2
0x18003bcd2  mov     typeInfoForDocumentation, [rbp+47h+bstrMethodName.m_ptr]; wsz
0x18003bcd6  xor     edi, edi
0x18003bcd8  inc     rbx
0x18003bcdb  cmp     [typeInfoForDocumentation+rbx*2], di
0x18003bcdf  jnz     short loc_18003BCD8
0x18003bce1  mov     edx, ebx; cch
0x18003bce3  call    ?ToUtf8@@YAPEADPEBGK@Z; ToUtf8(ushort const *,ulong)
0x18003bce8  mov     [rsi+30h], rax
0x18003bcec  test    rax, rax
0x18003bcef  jnz     short loc_18003BCF8
0x18003bcf1  mov     edx, 354h
0x18003bcf6  jmp     short loc_18003BD17
0x18003bcf8  lea     eax, [r15+r15*2]
0x18003bcfc  shl     eax, 3
0x18003bcff  mov     ecx, eax; cb
0x18003bd01  mov     ebx, eax
0x18003bd03  call    cs:__imp_CoTaskMemAlloc
0x18003bd09  mov     [rsi+38h], rax
0x18003bd0d  test    rax, rax
0x18003bd10  jnz     short loc_18003BD4F
0x18003bd12  mov     edx, 359h; lineNumber
0x18003bd17  mov     typeInfoForDocumentation, [rbp+4Fh]; callerReturnAddress
0x18003bd1b  lea     iidBase, aComOle32ComTxf_3; "com\\ole32\\com\\txf\\callframe\\typein"...
0x18003bd22  mov     r9d, 8007000Eh; hr
0x18003bd28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bd2d  lea     typeInfoForDocumentation, [rbp+47h+bstrMethodName]; this
0x18003bd31  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003bd36  mov     typeInfoForDocumentation, [rbp+47h+vt]
0x18003bd3a  test    typeInfoForDocumentation, typeInfoForDocumentation
0x18003bd3d  jz      short loc_18003BD45
0x18003bd3f  call    cs:__imp_NdrpReleaseTypeGenCookie
0x18003bd45  mov     ebx, 8007000Eh
0x18003bd4a  jmp     loc_18003BF2B
0x18003bd4f  mov     iidBase, rbx; Size
0x18003bd52  xor     edx, edx; Val
0x18003bd54  mov     typeInfoForDocumentation, rax; void *
0x18003bd57  call    memset_0
0x18003bd5c  cmp     r14w, r15w
0x18003bd60  jnb     loc_18003BF3D
0x18003bd66  movzx   ebx, r14w
0x18003bd6a  mov     eax, ebx
0x18003bd6c  add     rax, rax
0x18003bd6f  mov     r13, [r13+rax*8+0]
0x18003bd74  test    r13, r13
0x18003bd77  jz      loc_18003BE6A
0x18003bd7d  mov     typeInfoForDocumentation, [rbp+47h+arg_20]
0x18003bd81  lea     iid, [rbp+47h+var_6C]
0x18003bd85  mov     rdi, [rsi+38h]
0x18003bd89  lea     iidBase, [rbp+47h+typeFormatStringLength]
0x18003bd8d  mov     [rbp+47h+typeFormatStringLength], r12
0x18003bd91  mov     r9d, 1
0x18003bd97  mov     [rbp+47h+var_6C], r12d
0x18003bd9b  mov     typeInfoForDocumentation, [typeInfoForDocumentation+rax*8+8]
0x18003bda0  mov     [rsp+0D0h+formatString], iid
0x18003bda5  mov     edx, [r13+0]
0x18003bda9  mov     [rbp+47h+var_58], typeInfoForDocumentation
0x18003bdad  mov     rax, [typeInfoForDocumentation]
0x18003bdb0  mov     rax, [rax+38h]
0x18003bdb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdb9  mov     r12d, eax
0x18003bdbc  test    eax, eax
0x18003bdbe  js      loc_18003BEEF
0x18003bdc4  mov     typeInfoForDocumentation, [rbp+47h+typeFormatStringLength]; wszFrom
0x18003bdc8  lea     rbx, [rbx+rbx*2]
0x18003bdcc  call    ?CopyString@@YAPEAGPEBG@Z; CopyString(ushort const *)
0x18003bdd1  xor     r12d, r12d
0x18003bdd4  mov     [rdi+rbx*8], rax
0x18003bdd8  test    rax, rax
0x18003bddb  jz      loc_18003BEC6
0x18003bde1  movsx   rax, word ptr [r13+24h]
0x18003bde6  mov     [rdi+rbx*8+8], ax
0x18003bdeb  test    ax, ax
0x18003bdee  jz      short loc_18003BE61
0x18003bdf0  mov     typeInfoForDocumentation, rax
0x18003bdf3  add     typeInfoForDocumentation, typeInfoForDocumentation; cb
0x18003bdf6  call    cs:__imp_CoTaskMemAlloc
0x18003bdfc  mov     [rdi+rbx*8+10h], rax
0x18003be01  test    rax, rax
0x18003be04  jz      loc_18003BEBF
0x18003be0a  xor     eax, eax
0x18003be0c  cmp     ax, [rdi+rbx*8+8]
0x18003be11  jge     short loc_18003BE61
0x18003be13  mov     typeInfoForDocumentation, [rbp+47h+var_58]
0x18003be17  lea     iidBase, [rbp+47h+bstrInterfaceName]
0x18003be1b  xor     eax, eax
0x18003be1d  mov     word ptr [rbp+47h+bstrInterfaceName.m_ptr], ax
0x18003be21  movsx   rax, r12w
0x18003be25  mov     iid, rax
0x18003be28  mov     [rbp+47h+var_50], rax
0x18003be2c  shl     iid, 5
0x18003be30  add     iid, [r13+10h]
0x18003be34  call    cs:__imp_NdrpVarVtOfTypeDesc
0x18003be3a  mov     dword ptr [rbp+47h+typeFormatString], eax
0x18003be3d  test    eax, eax
0x18003be3f  js      short loc_18003BE81
0x18003be41  mov     typeInfoForDocumentation, [rdi+rbx*8+10h]
0x18003be46  inc     r12w
  ... truncated ...
```
