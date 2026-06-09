# _AfxOleGetObjectDescriptorData(IOleObject *,wchar_t const *,ulong,_POINTL,tagSIZE *)

- ea: `0x18026b240`
- end: `0x18026b6ac`
- name: `?_AfxOleGetObjectDescriptorData@@YAPEAXPEAUIOleObject@@PEB_WKU_POINTL@@PEAUtagSIZE@@@Z`
- size: `1132`
- prototype: `void *__fastcall(IOleObject *lpOleObj, const wchar_t *lpszSrcOfCopy, unsigned int dwDrawAspect, _POINTL pointl, tagSIZE *lpSizelHim)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180252440`
- `0x180276470`

## callees

- `0x1800033dc`
- `0x18000ddc0`
- `0x1801d62b0`
- `0x180231d70`
- `0x18026b0c8`
- `0x18026b240`
- `0x1802bbce0`
- `0x1802c4640`
- `0x1802c7020`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026b3ea`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026b3f2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026b415`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026b423`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026b47f`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026b3ea`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026b3f2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026b415`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026b423`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18026b47f`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026b3a7`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x18026b3a7`
- `ole32!CoTaskMemAlloc` at `0x18026b3d1`
- `ole32!CoTaskMemAlloc` at `0x18026b3d1`
- `ole32!CreateBindCtx` at `0x18026b521`
- `ole32!CreateBindCtx` at `0x18026b521`
- `ole32!CoTaskMemFree` at `0x18026b492`
- `ole32!CoTaskMemFree` at `0x18026b4a8`
- `ole32!CoTaskMemFree` at `0x18026b60c`
- `ole32!CoTaskMemFree` at `0x18026b65c`
- `ole32!CoTaskMemFree` at `0x18026b492`
- `ole32!CoTaskMemFree` at `0x18026b4a8`
- `ole32!CoTaskMemFree` at `0x18026b60c`
- `ole32!CoTaskMemFree` at `0x18026b65c`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void *__fastcall _AfxOleGetObjectDescriptorData(
        IOleObject *lpOleObj,
        wchar_t *lpszSrcOfCopy,
        unsigned int dwDrawAspect,
        _POINTL pointl,
        tagSIZE *lpSizelHim)
{
  unsigned int v6; // r12d
  tagSIZE *v8; // r15
  int v9; // esi
  IOleLink *p; // rax
  BOOL v11; // ebx
  HINSTANCE__ *StringResourceHandle; // rax
  int v13; // eax
  wchar_t *m_pszData; // rbx
  int v15; // r13d
  IBindCtx *v16; // rsi
  unsigned __int64 v17; // r15
  unsigned int v18; // eax
  IBindCtx *v19; // rax
  wchar_t *v20; // r12
  int v21; // esi
  int *v22; // rax
  unsigned int v23; // ecx
  void *ObjectDescriptorData; // rbx
  ATL::CComHeapPtr<wchar_t> sposzFullUserTypeName; // [rsp+40h] [rbp-71h] BYREF
  unsigned int dwStatus; // [rsp+48h] [rbp-69h] BYREF
  ATL::CComPtr<IBindCtx> spbc; // [rsp+50h] [rbp-61h] BYREF
  tagSIZE sizelHim; // [rsp+58h] [rbp-59h] BYREF
  LPVOID pv; // [rsp+60h] [rbp-51h] BYREF
  ATL::CComQIPtr<IOleLink,&_GUID_0000011d_0000_0000_c000_000000000046> spOleLink; // [rsp+68h] [rbp-49h] BYREF
  ATL::CComQIPtr<IViewObject2,&_GUID_00000127_0000_0000_c000_000000000046> spViewObj2; // [rsp+70h] [rbp-41h] BYREF
  unsigned int v33; // [rsp+78h] [rbp-39h]
  ATL::CComPtr<IMoniker> spSrcMonikerOfCopy; // [rsp+80h] [rbp-31h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > strLinkedTypeFmt; // [rsp+88h] [rbp-29h] BYREF
  _GUID v36; // [rsp+90h] [rbp-21h] BYREF
  _GUID clsid; // [rsp+A0h] [rbp-11h] BYREF

  v6 = dwDrawAspect;
  v33 = dwDrawAspect;
  pv = lpszSrcOfCopy;
  v8 = lpSizelHim;
  *(_QWORD *)&v36.Data1 = lpSizelHim;
  sposzFullUserTypeName.m_pData = 0;
  spSrcMonikerOfCopy.p = 0;
  v9 = 0;
  spViewObj2.p = 0;
  if ( lpOleObj
    && lpOleObj->QueryInterface(lpOleObj, &GUID_00000127_0000_0000_c000_000000000046, (void **)&spViewObj2) < 0 )
  {
    spViewObj2.p = 0;
  }
  p = 0;
  spOleLink.p = 0;
  if ( lpOleObj )
  {
    if ( lpOleObj->QueryInterface(lpOleObj, &GUID_0000011d_0000_0000_c000_000000000046, (void **)&spOleLink) >= 0 )
    {
      p = spOleLink.p;
    }
    else
    {
      p = 0;
      spOleLink.p = 0;
    }
  }
  dwStatus = 0;
  v11 = p != 0;
  if ( lpOleObj->GetUserClassID(lpOleObj, &clsid) )
    clsid = GUID_NULL;
  lpOleObj->GetUserType(lpOleObj, 1u, (wchar_t **)&sposzFullUserTypeName);
  if ( v11 )
  {
    if ( !sposzFullUserTypeName.m_pData )
    {
LABEL_35:
      spOleLink.p->GetSourceDisplayName(spOleLink.p, (wchar_t **)&pv);
      v9 = 1;
      goto LABEL_42;
    }
    strLinkedTypeFmt.m_pszData = (wchar_t *)&afxStringManager.GetNilString(&afxStringManager)[1];
    StringResourceHandle = AfxFindStringResourceHandle(0xF094u);
    if ( !StringResourceHandle
      || !ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(
            &strLinkedTypeFmt,
            StringResourceHandle,
            0xF094u) )
    {
      AfxThrowInvalidArgException();
    }
    if ( sposzFullUserTypeName.m_pData )
      v13 = wcslen(sposzFullUserTypeName.m_pData);
    else
      v13 = 0;
    m_pszData = strLinkedTypeFmt.m_pszData;
    v15 = v13 + *((_DWORD *)strLinkedTypeFmt.m_pszData - 4);
    v16 = 0;
    spbc.p = 0;
    v17 = v15 + 1;
    if ( v15 == -1 )
    {
      v18 = 0;
      goto LABEL_19;
    }
    if ( 0xFFFFFFFFFFFFFFFFuLL / v17 >= 2 )
    {
      v18 = 2 * v17;
      if ( 2 * v17 <= 0x7FFFFFFF )
      {
LABEL_19:
        v19 = (IBindCtx *)CoTaskMemAlloc(v18);
        v16 = v19;
        spbc.p = v19;
        if ( v19 )
        {
          v20 = (wchar_t *)v19;
          v21 = *_errno();
          *_errno() = 0;
          snwprintf_s(v20, v17, v15, m_pszData, sposzFullUserTypeName.m_pData);
          if ( *_errno() )
          {
            v22 = _errno();
            if ( *v22 )
            {
              if ( *v22 == 12 )
                ATL::AtlThrowImpl(-2147024882);
              if ( *v22 == 22 || *v22 == 34 )
                ATL::AtlThrowImpl(-2147024809);
              if ( *v22 != 80 )
                ATL::AtlThrowImpl(-2147467259);
            }
          }
          else
          {
            *_errno() = v21;
          }
          v16 = 0;
          spbc.p = 0;
          CoTaskMemFree(sposzFullUserTypeName.m_pData);
          sposzFullUserTypeName.m_pData = v20;
          v6 = v33;
        }
        goto LABEL_32;
      }
      v16 = 0;
      spbc.p = 0;
    }
LABEL_32:
    CoTaskMemFree(v16);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)m_pszData - 2, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)m_pszData - 3) + 8LL))(*((_QWORD *)m_pszData - 3));
    v8 = *(tagSIZE **)&v36.Data1;
    goto LABEL_35;
  }
  if ( !pv && !lpOleObj->GetMoniker(lpOleObj, 4u, 3u, (IMoniker **)&spSrcMonikerOfCopy) )
  {
    spbc.p = 0;
    if ( CreateBindCtx(0, &spbc.p) >= 0 )
    {
      spSrcMonikerOfCopy.p->GetDisplayName(spSrcMonikerOfCopy.p, spbc.p, 0, (wchar_t **)&pv);
      v9 = 1;
    }
    if ( spbc.p )
      spbc.p->Release(spbc.p);
  }
LABEL_42:
  if ( v8 )
  {
    sizelHim = *v8;
  }
  else if ( !spViewObj2.p || spViewObj2.p->GetExtent(spViewObj2.p, v6, -1, 0, &sizelHim) )
  {
    sizelHim = 0;
  }
  if ( lpOleObj->GetMiscStatus(lpOleObj, v6, &dwStatus) )
  {
    v23 = 0;
    dwStatus = 0;
  }
  else
  {
    v23 = dwStatus;
  }
  v36 = clsid;
  ObjectDescriptorData = _AfxOleGetObjectDescriptorData(
                           &v36,
                           v6,
                           sizelHim,
                           pointl,
                           v23,
                           sposzFullUserTypeName.m_pData,
                           (const wchar_t *)pv);
  if ( v9 )
    CoTaskMemFree(pv);
  if ( spOleLink.p )
    spOleLink.p->Release(spOleLink.p);
  if ( spViewObj2.p )
    spViewObj2.p->Release(spViewObj2.p);
  if ( spSrcMonikerOfCopy.p )
    spSrcMonikerOfCopy.p->Release(spSrcMonikerOfCopy.p);
  CoTaskMemFree(sposzFullUserTypeName.m_pData);
  return ObjectDescriptorData;
}

```

## disassembly

```asm
0x18026b240  push    rbp
0x18026b242  push    rbx
0x18026b243  push    rsi
0x18026b244  push    rdi
0x18026b245  push    r12
0x18026b247  push    r13
0x18026b249  push    r14
0x18026b24b  push    r15
0x18026b24d  lea     rbp, [rsp-17h]
0x18026b252  sub     rsp, 0C8h
0x18026b259  mov     rax, cs:__security_cookie
0x18026b260  xor     rax, rsp
0x18026b263  mov     [rbp+4Fh+var_50], rax
0x18026b267  mov     rdi, pointl
0x18026b26a  mov     r12d, dwDrawAspect
0x18026b26d  mov     [rbp+4Fh+var_88], dwDrawAspect
0x18026b271  mov     r14, lpOleObj
0x18026b274  mov     [rbp+4Fh+pv], lpszSrcOfCopy
0x18026b278  mov     r15, [rbp+4Fh+arg_20]
0x18026b27c  mov     qword ptr [rbp+4Fh+var_70], r15
0x18026b280  xor     r13d, r13d
0x18026b283  mov     [rbp+4Fh+sposzFullUserTypeName.m_pData], r13
0x18026b287  mov     [rbp+4Fh+spSrcMonikerOfCopy.p], r13
0x18026b28b  mov     esi, r13d
0x18026b28e  mov     [rbp+4Fh+spViewObj2.p], r13
0x18026b292  test    lpOleObj, lpOleObj
0x18026b295  jz      short loc_18026B2B6
0x18026b297  mov     rax, [lpOleObj]
0x18026b29a  lea     r8, [rbp+4Fh+spViewObj2]
0x18026b29e  lea     lpszSrcOfCopy, _GUID_00000127_0000_0000_c000_000000000046
0x18026b2a5  mov     rax, [rax]
0x18026b2a8  call    cs:__guard_dispatch_icall_fptr
0x18026b2ae  test    eax, eax
0x18026b2b0  jns     short loc_18026B2B6
0x18026b2b2  mov     [rbp+4Fh+spViewObj2.p], r13
0x18026b2b6  mov     rax, r13
0x18026b2b9  mov     [rbp+4Fh+spOleLink.p], rax
0x18026b2bd  test    r14, r14
0x18026b2c0  jz      short loc_18026B2ED
0x18026b2c2  mov     rax, [r14]
0x18026b2c5  lea     r8, [rbp+4Fh+spOleLink]
0x18026b2c9  lea     lpszSrcOfCopy, _GUID_0000011d_0000_0000_c000_000000000046
0x18026b2d0  mov     lpOleObj, r14
0x18026b2d3  mov     rax, [rax]
0x18026b2d6  call    cs:__guard_dispatch_icall_fptr
0x18026b2dc  test    eax, eax
0x18026b2de  jns     short loc_18026B2E9
0x18026b2e0  mov     rax, r13
0x18026b2e3  mov     [rbp+4Fh+spOleLink.p], rax
0x18026b2e7  jmp     short loc_18026B2ED
0x18026b2e9  mov     rax, [rbp+4Fh+spOleLink.p]
0x18026b2ed  mov     [rbp+4Fh+dwStatus], r13d
0x18026b2f1  mov     ebx, r13d
0x18026b2f4  test    rax, rax
0x18026b2f7  setnz   bl
0x18026b2fa  mov     rax, [r14]
0x18026b2fd  lea     lpszSrcOfCopy, [rbp+4Fh+clsid]
0x18026b301  mov     lpOleObj, r14
0x18026b304  mov     rax, [rax+78h]
0x18026b308  call    cs:__guard_dispatch_icall_fptr
0x18026b30e  test    eax, eax
0x18026b310  jz      short loc_18026B31E
0x18026b312  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18026b319  movdqu  xmmword ptr [rbp+4Fh+clsid.Data1], xmm0
0x18026b31e  mov     rax, [r14]
0x18026b321  lea     r8, [rbp+4Fh+sposzFullUserTypeName]
0x18026b325  mov     edx, 1
0x18026b32a  mov     lpOleObj, r14
0x18026b32d  mov     rax, [rax+80h]
0x18026b334  call    cs:__guard_dispatch_icall_fptr
0x18026b33a  test    ebx, ebx
0x18026b33c  jz      loc_18026B4F0
0x18026b342  cmp     [rbp+4Fh+sposzFullUserTypeName.m_pData], r13
0x18026b346  jz      loc_18026B4D4
0x18026b34c  mov     rax, cs:?afxStringManager@@3VCAfxStringMgr@@A.__vftable; CAfxStringMgr afxStringManager ...
0x18026b353  lea     lpOleObj, ?afxStringManager@@3VCAfxStringMgr@@A; CAfxStringMgr afxStringManager
0x18026b35a  mov     rax, [rax+18h]
0x18026b35e  call    cs:__guard_dispatch_icall_fptr
0x18026b364  add     rax, 18h
0x18026b368  mov     [rbp+4Fh+strLinkedTypeFmt.m_pszData], rax
0x18026b36c  mov     ebx, 0F094h
0x18026b371  mov     ecx, ebx; nID
0x18026b373  call    ?AfxFindStringResourceHandle@@YAPEAUHINSTANCE__@@I@Z; AfxFindStringResourceHandle(uint)
0x18026b378  nop
0x18026b379  test    rax, rax
0x18026b37c  jz      loc_18026B685
0x18026b382  mov     dwDrawAspect, ebx; nID
0x18026b385  mov     lpszSrcOfCopy, rax; hInstance
0x18026b388  lea     lpOleObj, [rbp+4Fh+strLinkedTypeFmt]; this
0x18026b38c  call    ?LoadStringW@?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::LoadStringW(HINSTANCE__ *,uint)
0x18026b391  test    eax, eax
0x18026b393  jz      loc_18026B685
0x18026b399  mov     lpOleObj, [rbp+4Fh+sposzFullUserTypeName.m_pData]; String
0x18026b39d  test    lpOleObj, lpOleObj
0x18026b3a0  jnz     short loc_18026B3A7
0x18026b3a2  mov     eax, r13d
0x18026b3a5  jmp     short loc_18026B3AD
0x18026b3a7  call    cs:__imp_wcslen
0x18026b3ad  mov     rbx, [rbp+4Fh+strLinkedTypeFmt.m_pszData]
0x18026b3b1  mov     r13d, [rbx-10h]
0x18026b3b5  add     r13d, eax
0x18026b3b8  lea     eax, [r13+1]
0x18026b3bc  xor     esi, esi
0x18026b3be  mov     [rbp+4Fh+spbc.p], rsi
0x18026b3c2  movsxd  r15, eax
0x18026b3c5  test    eax, eax
0x18026b3c7  jnz     loc_18026B454
0x18026b3cd  xor     eax, eax
0x18026b3cf  mov     ecx, eax; cb
0x18026b3d1  call    cs:__imp_CoTaskMemAlloc
0x18026b3d7  mov     rsi, rax
0x18026b3da  mov     [rbp+4Fh+spbc.p], rax
0x18026b3de  test    rax, rax
0x18026b3e1  jz      loc_18026B4A2
0x18026b3e7  mov     r12, rax
0x18026b3ea  call    cs:__imp__errno
0x18026b3f0  mov     esi, [rax]
0x18026b3f2  call    cs:__imp__errno
0x18026b3f8  and     dword ptr [rax], 0
0x18026b3fb  movsxd  r8, r13d; _MaxCount
0x18026b3fe  mov     rax, [rbp+4Fh+sposzFullUserTypeName.m_pData]
0x18026b402  mov     [rsp+100h+var_E0], rax
0x18026b407  mov     pointl, rbx; _Format
0x18026b40a  mov     lpszSrcOfCopy, r15; _BufferCount
0x18026b40d  mov     lpOleObj, r12; _Buffer
0x18026b410  call    _snwprintf_s
0x18026b415  call    cs:__imp__errno
0x18026b41b  xor     r13d, r13d
0x18026b41e  cmp     [rax], r13d
0x18026b421  jz      short loc_18026B47F
0x18026b423  call    cs:__imp__errno
0x18026b429  cmp     [rax], r13d
0x18026b42c  jz      short loc_18026B487
0x18026b42e  cmp     dword ptr [rax], 0Ch
0x18026b431  jz      loc_18026B6A1
0x18026b437  cmp     dword ptr [rax], 16h
0x18026b43a  jz      loc_18026B696
0x18026b440  cmp     dword ptr [rax], 22h ; '"'
0x18026b443  jz      loc_18026B696
0x18026b449  cmp     dword ptr [rax], 50h ; 'P'
0x18026b44c  jnz     loc_18026B68B
0x18026b452  jmp     short loc_18026B487
0x18026b454  xor     edx, edx
0x18026b456  or      rax, 0FFFFFFFFFFFFFFFFh
0x18026b45a  div     r15
0x18026b45d  cmp     rax, 2
0x18026b461  jb      short loc_18026B4A2
0x18026b463  lea     rax, [r15+r15]
0x18026b467  cmp     rax, 7FFFFFFFh
0x18026b46d  jbe     loc_18026B3CF
0x18026b473  xor     r13d, r13d
0x18026b476  mov     esi, r13d
0x18026b479  mov     [rbp+4Fh+spbc.p], r13
0x18026b47d  jmp     short loc_18026B4A5
0x18026b47f  call    cs:__imp__errno
0x18026b485  mov     [rax], esi
0x18026b487  mov     rsi, r13
0x18026b48a  mov     [rbp+4Fh+spbc.p], r13
0x18026b48e  mov     lpOleObj, [rbp+4Fh+sposzFullUserTypeName.m_pData]; pv
0x18026b492  call    cs:__imp_CoTaskMemFree
0x18026b498  mov     [rbp+4Fh+sposzFullUserTypeName.m_pData], r12
0x18026b49c  mov     r12d, [rbp+4Fh+var_88]
0x18026b4a0  jmp     short loc_18026B4A5
0x18026b4a2  xor     r13d, r13d
0x18026b4a5  mov     lpOleObj, rsi; pv
0x18026b4a8  call    cs:__imp_CoTaskMemFree
0x18026b4ae  nop
0x18026b4af  lea     lpszSrcOfCopy, [rbx-18h]
0x18026b4b3  or      eax, 0FFFFFFFFh
0x18026b4b6  lock xadd [lpszSrcOfCopy+10h], eax
0x18026b4bb  sub     eax, 1
0x18026b4be  jg      short loc_18026B4D0
0x18026b4c0  mov     lpOleObj, [lpszSrcOfCopy]
0x18026b4c3  mov     rax, [lpOleObj]
0x18026b4c6  mov     rax, [rax+8]
0x18026b4ca  call    cs:__guard_dispatch_icall_fptr
0x18026b4d0  mov     r15, qword ptr [rbp+4Fh+var_70]
0x18026b4d4  mov     lpOleObj, [rbp+4Fh+spOleLink.p]
0x18026b4d8  mov     rax, [lpOleObj]
0x18026b4db  lea     lpszSrcOfCopy, [rbp+4Fh+pv]
0x18026b4df  mov     rax, [rax+40h]
0x18026b4e3  call    cs:__guard_dispatch_icall_fptr
0x18026b4e9  mov     esi, 1
0x18026b4ee  jmp     short loc_18026B566
0x18026b4f0  cmp     [rbp+4Fh+pv], r13
0x18026b4f4  jnz     short loc_18026B566
0x18026b4f6  mov     rax, [r14]
0x18026b4f9  lea     pointl, [rbp+4Fh+spSrcMonikerOfCopy]
0x18026b4fd  mov     edx, 4
0x18026b502  lea     dwDrawAspect, [lpszSrcOfCopy-1]
0x18026b506  mov     lpOleObj, r14
0x18026b509  mov     rax, [rax+40h]
0x18026b50d  call    cs:__guard_dispatch_icall_fptr
0x18026b513  test    eax, eax
0x18026b515  jnz     short loc_18026B566
0x18026b517  mov     [rbp+4Fh+spbc.p], r13
0x18026b51b  lea     lpszSrcOfCopy, [rbp+4Fh+spbc]; ppbc
0x18026b51f  xor     ecx, ecx; reserved
0x18026b521  call    cs:__imp_CreateBindCtx
0x18026b527  test    eax, eax
0x18026b529  js      short loc_18026B54F
0x18026b52b  mov     lpOleObj, [rbp+4Fh+spSrcMonikerOfCopy.p]
0x18026b52f  mov     rax, [lpOleObj]
0x18026b532  lea     pointl, [rbp+4Fh+pv]
0x18026b536  xor     dwDrawAspect, dwDrawAspect
0x18026b539  mov     lpszSrcOfCopy, [rbp+4Fh+spbc.p]
0x18026b53d  mov     rax, [rax+0A0h]
0x18026b544  call    cs:__guard_dispatch_icall_fptr
0x18026b54a  mov     esi, 1
0x18026b54f  mov     lpOleObj, [rbp+4Fh+spbc.p]
0x18026b553  test    lpOleObj, lpOleObj
0x18026b556  jz      short loc_18026B566
0x18026b558  mov     rax, [lpOleObj]
0x18026b55b  mov     rax, [rax+10h]
0x18026b55f  call    cs:__guard_dispatch_icall_fptr
0x18026b565  nop
0x18026b566  test    r15, r15
0x18026b569  jz      short loc_18026B574
0x18026b56b  mov     rax, [r15]
0x18026b56e  mov     qword ptr [rbp+4Fh+sizelHim.cx], rax
0x18026b572  jmp     short loc_18026B5A6
0x18026b574  mov     lpOleObj, [rbp+4Fh+spViewObj2.p]
0x18026b578  test    lpOleObj, lpOleObj
0x18026b57b  jz      short loc_18026B5A1
0x18026b57d  mov     rax, [lpOleObj]
0x18026b580  lea     lpszSrcOfCopy, [rbp+4Fh+sizelHim]
0x18026b584  mov     [rsp+100h+var_E0], lpszSrcOfCopy
0x18026b589  xor     r9d, r9d
0x18026b58c  or      dwDrawAspect, 0FFFFFFFFh
0x18026b590  mov     edx, r12d
0x18026b593  mov     rax, [rax+48h]
0x18026b597  call    cs:__guard_dispatch_icall_fptr
0x18026b59d  test    eax, eax
0x18026b59f  jz      short loc_18026B5A6
0x18026b5a1  and     qword ptr [rbp+4Fh+sizelHim.cx], 0
0x18026b5a6  mov     rax, [r14]
0x18026b5a9  lea     r8, [rbp+4Fh+dwStatus]
0x18026b5ad  mov     edx, r12d
0x18026b5b0  mov     lpOleObj, r14
0x18026b5b3  mov     rax, [rax+0B0h]
0x18026b5ba  call    cs:__guard_dispatch_icall_fptr
0x18026b5c0  test    eax, eax
0x18026b5c2  jz      short loc_18026B5CC
0x18026b5c4  mov     ecx, r13d
0x18026b5c7  mov     [rbp+4Fh+dwStatus], ecx
0x18026b5ca  jmp     short loc_18026B5CF
0x18026b5cc  mov     ecx, [rbp+4Fh+dwStatus]
0x18026b5cf  movaps  xmm0, xmmword ptr [rbp+4Fh+clsid.Data1]
0x18026b5d3  movdqa  [rbp+4Fh+var_70], xmm0
0x18026b5d8  mov     rax, [rbp+4Fh+pv]
0x18026b5dc  mov     [rsp+100h+var_D0], rax
0x18026b5e1  mov     rax, [rbp+4Fh+sposzFullUserTypeName.m_pData]
0x18026b5e5  mov     [rsp+100h+var_D8], rax
0x18026b5ea  mov     dword ptr [rsp+100h+var_E0], ecx
0x18026b5ee  mov     pointl, rdi
0x18026b5f1  mov     r8, qword ptr [rbp+4Fh+sizelHim.cx]
0x18026b5f5  mov     edx, r12d
0x18026b5f8  lea     lpOleObj, [rbp+4Fh+var_70]
0x18026b5fc  call    ?_AfxOleGetObjectDescriptorData@@YAPEAXU_GUID@@KUtagSIZE@@U_POINTL@@KPEB_W3@Z; _AfxOleGetObjectDescriptorData(_GUID,ulong,tagSIZE,_POINTL,ulong,wchar_t const *,wchar_t const *)
0x18026b601  mov     rbx, rax
0x18026b604  test    esi, esi
0x18026b606  jz      short loc_18026B613
0x18026b608  mov     lpOleObj, [rbp+4Fh+pv]; pv
0x18026b60c  call    cs:__imp_CoTaskMemFree
0x18026b612  nop
0x18026b613  mov     lpOleObj, [rbp+4Fh+spOleLink.p]
0x18026b617  test    lpOleObj, lpOleObj
0x18026b61a  jz      short loc_18026B62A
0x18026b61c  mov     rax, [lpOleObj]
0x18026b61f  mov     rax, [rax+10h]
0x18026b623  call    cs:__guard_dispatch_icall_fptr
0x18026b629  nop
0x18026b62a  mov     lpOleObj, [rbp+4Fh+spViewObj2.p]
0x18026b62e  test    lpOleObj, lpOleObj
0x18026b631  jz      short loc_18026B641
0x18026b633  mov     rax, [lpOleObj]
0x18026b636  mov     rax, [rax+10h]
0x18026b63a  call    cs:__guard_dispatch_icall_fptr
0x18026b640  nop
0x18026b641  mov     lpOleObj, [rbp+4Fh+spSrcMonikerOfCopy.p]
0x18026b645  test    lpOleObj, lpOleObj
0x18026b648  jz      short loc_18026B658
0x18026b64a  mov     rax, [lpOleObj]
0x18026b64d  mov     rax, [rax+10h]
0x18026b651  call    cs:__guard_dispatch_icall_fptr
0x18026b657  nop
0x18026b658  mov     lpOleObj, [rbp+4Fh+sposzFullUserTypeName.m_pData]; pv
0x18026b65c  call    cs:__imp_CoTaskMemFree
0x18026b662  mov     rax, rbx
0x18026b665  mov     lpOleObj, [rbp+4Fh+var_50]
0x18026b669  xor     lpOleObj, rsp; StackCookie
0x18026b66c  call    __security_check_cookie
0x18026b671  add     rsp, 0C8h
0x18026b678  pop     r15
0x18026b67a  pop     r14
0x18026b67c  pop     r13
0x18026b67e  pop     r12
0x18026b680  pop     rdi
0x18026b681  pop     rsi
0x18026b682  pop     rbx
  ... truncated ...
```
