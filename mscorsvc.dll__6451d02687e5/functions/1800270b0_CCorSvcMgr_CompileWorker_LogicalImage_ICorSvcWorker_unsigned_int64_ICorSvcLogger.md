# CCorSvcMgr::CompileWorker(LogicalImage *,ICorSvcWorker *,unsigned __int64,ICorSvcLogger *)

- ea: `0x1800270b0`
- end: `0x180027ea8`
- name: `?CompileWorker@CCorSvcMgr@@QEAAXPEAVLogicalImage@@PEAUICorSvcWorker@@_KPEAUICorSvcLogger@@@Z`
- size: `3576`
- prototype: `void __fastcall(CCorSvcMgr *this, OLECHAR *, struct ICorSvcWorker *, __int64, struct ICorSvcLogger *)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180023bcc`
- `0x180026ad0`

## callees

- `0x180002468`
- `0x180002504`
- `0x1800093d8`
- `0x18000af58`
- `0x18000ba88`
- `0x18000bb00`
- `0x18000c8a8`
- `0x180025110`
- `0x1800270b0`
- `0x18002bc14`
- `0x18002c49c`
- `0x1800304ec`
- `0x180030568`
- `0x180030d84`
- `0x180032654`
- `0x180032f44`
- `0x180032fe8`
- `0x18003303c`
- `0x1800330c4`
- `0x180034fd4`
- `0x1800350c4`
- `0x1800351e8`
- `0x180035228`
- `0x18003dc30`
- `0x18003dc50`
- `0x18003f280`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180027128`
- `KERNEL32!EnterCriticalSection` at `0x1800277ae`
- `KERNEL32!EnterCriticalSection` at `0x180027128`
- `KERNEL32!EnterCriticalSection` at `0x1800277ae`
- `KERNEL32!LeaveCriticalSection` at `0x18002770e`
- `KERNEL32!LeaveCriticalSection` at `0x180027e17`
- `KERNEL32!LeaveCriticalSection` at `0x18002770e`
- `KERNEL32!LeaveCriticalSection` at `0x180027e17`
- `KERNEL32!HeapFree` at `0x1800276bc`
- `KERNEL32!HeapFree` at `0x1800276f9`
- `KERNEL32!HeapFree` at `0x1800276bc`
- `KERNEL32!HeapFree` at `0x1800276f9`
- `KERNEL32!GetProcessHeap` at `0x1800276a7`
- `KERNEL32!GetProcessHeap` at `0x1800276e4`
- `KERNEL32!GetProcessHeap` at `0x1800276a7`
- `KERNEL32!GetProcessHeap` at `0x1800276e4`
- `ucrtbase_clr0400!wcscpy_s` at `0x1800278cb`
- `ucrtbase_clr0400!wcscpy_s` at `0x1800278cb`
- `OLEAUT32!__imp_SysAllocString` at `0x180027170`
- `OLEAUT32!__imp_SysAllocString` at `0x1800271ab`
- `OLEAUT32!__imp_SysAllocString` at `0x180027406`
- `OLEAUT32!__imp_SysAllocString` at `0x1800274b8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002760d`
- `OLEAUT32!__imp_SysAllocString` at `0x180027a77`
- `OLEAUT32!__imp_SysAllocString` at `0x180027b0d`
- `OLEAUT32!__imp_SysAllocString` at `0x180027bd9`
- `OLEAUT32!__imp_SysAllocString` at `0x180027d28`
- `OLEAUT32!__imp_SysAllocString` at `0x180027170`
- `OLEAUT32!__imp_SysAllocString` at `0x1800271ab`
- `OLEAUT32!__imp_SysAllocString` at `0x180027406`
- `OLEAUT32!__imp_SysAllocString` at `0x1800274b8`
- `OLEAUT32!__imp_SysAllocString` at `0x18002760d`
- `OLEAUT32!__imp_SysAllocString` at `0x180027a77`
- `OLEAUT32!__imp_SysAllocString` at `0x180027b0d`
- `OLEAUT32!__imp_SysAllocString` at `0x180027bd9`
- `OLEAUT32!__imp_SysAllocString` at `0x180027d28`
- `OLEAUT32!__imp_SysFreeString` at `0x180027452`
- `OLEAUT32!__imp_SysFreeString` at `0x180027501`
- `OLEAUT32!__imp_SysFreeString` at `0x18002767e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002773f`
- `OLEAUT32!__imp_SysFreeString` at `0x180027ab9`
- `OLEAUT32!__imp_SysFreeString` at `0x180027b53`
- `OLEAUT32!__imp_SysFreeString` at `0x180027c1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180027d69`
- `OLEAUT32!__imp_SysFreeString` at `0x180027de2`
- `OLEAUT32!__imp_SysFreeString` at `0x180027df6`
- `OLEAUT32!__imp_SysFreeString` at `0x180027e0a`
- `OLEAUT32!__imp_SysFreeString` at `0x180027452`
- `OLEAUT32!__imp_SysFreeString` at `0x180027501`
- `OLEAUT32!__imp_SysFreeString` at `0x18002767e`
- `OLEAUT32!__imp_SysFreeString` at `0x18002773f`
- `OLEAUT32!__imp_SysFreeString` at `0x180027ab9`
- `OLEAUT32!__imp_SysFreeString` at `0x180027b53`
- `OLEAUT32!__imp_SysFreeString` at `0x180027c1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180027d69`
- `OLEAUT32!__imp_SysFreeString` at `0x180027de2`
- `OLEAUT32!__imp_SysFreeString` at `0x180027df6`
- `OLEAUT32!__imp_SysFreeString` at `0x180027e0a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180027dbb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180027dce`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180027dbb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180027dce`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180027437`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800274e9`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180027437`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x1800274e9`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002737c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800273aa`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18002737c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800273aa`

## string_xrefs

- `0x180027ae7`: `Ngen will retry compilation of image %s\n`
- `0x180027bb7`: `Uninstalling assembly %s because of an error during compilation: %s\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=37
void __fastcall CCorSvcMgr::CompileWorker(
        CCorSvcMgr *this,
        OLECHAR *a2,
        struct ICorSvcWorker *a3,
        __int64 a4,
        struct ICorSvcLogger *a5)
{
  BSTR v5; // rsi
  CCorSvcMgr *v6; // r14
  struct ICorSvcLogger *v7; // rbx
  int v8; // eax
  void **v9; // rcx
  const OLECHAR *RootPath; // rax
  __int64 v11; // rdi
  const OLECHAR *v12; // rcx
  BSTR v13; // rdi
  BSTR v14; // r15
  unsigned int v15; // r14d
  __int64 v16; // rsi
  unsigned int v17; // r13d
  BSTR *v18; // r12
  unsigned int v19; // ecx
  unsigned int v20; // edx
  __int64 v21; // rdx
  unsigned int v22; // r12d
  unsigned int v23; // ecx
  SAFEARRAY *Vector; // r13
  SAFEARRAY *v25; // r12
  unsigned int v26; // r12d
  __int64 v27; // rdx
  SString *v28; // r13
  const OLECHAR *v29; // rcx
  BOOL v30; // r13d
  HRESULT v31; // eax
  unsigned int v32; // r12d
  __int64 v33; // rdx
  SString *v34; // rdi
  const OLECHAR *v35; // rcx
  OLECHAR *v36; // r13
  HRESULT v37; // eax
  __int64 v38; // rdi
  OLECHAR *v39; // r15
  OLECHAR *v40; // rdi
  HANDLE ProcessHeap; // rax
  void *v42; // rdi
  HANDLE v43; // rax
  struct _RTL_CRITICAL_SECTION *v44; // r15
  unsigned int v45; // edi
  int v46; // r12d
  int v47; // ecx
  struct ICompileProgressNotification *v48; // rdx
  __int64 v49; // rdi
  int v50; // eax
  _DWORD *v51; // rax
  wchar_t **v52; // rbx
  const wchar_t *v53; // rdi
  __int64 v54; // rdx
  struct ICorSvcWorker *v55; // rdi
  int v56; // ebx
  void *v57; // rbx
  int v58; // r8d
  LPVOID v59; // r14
  __int64 v60; // rdi
  __int64 v61; // r8
  BSTR v62; // r14
  __int64 v63; // rdi
  __int64 v64; // r8
  BSTR v65; // rsi
  LPVOID v66; // r15
  __int64 v67; // rdi
  __int64 v68; // r8
  BSTR v69; // r15
  __int64 v70; // rdi
  unsigned int v71; // esi
  SBuffer *v72; // r15
  __int64 v73; // r13
  _QWORD *i; // rbx
  LPVOID v75; // r15
  __int64 v76; // rdi
  __int64 v77; // r8
  BSTR v78; // rsi
  unsigned __int16 *v79; // [rsp+30h] [rbp-D0h]
  LONG rgIndices; // [rsp+50h] [rbp-B0h] BYREF
  void *v81; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v82; // [rsp+60h] [rbp-A0h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-90h]
  BOOL v84; // [rsp+78h] [rbp-88h]
  BSTR Source; // [rsp+80h] [rbp-80h] BYREF
  int v86; // [rsp+88h] [rbp-78h]
  int v87; // [rsp+90h] [rbp-70h]
  SAFEARRAY *v88[2]; // [rsp+A0h] [rbp-60h]
  SAFEARRAY *psa[2]; // [rsp+B0h] [rbp-50h] BYREF
  BOOL v90; // [rsp+D0h] [rbp-30h]
  BOOL v91; // [rsp+D4h] [rbp-2Ch]
  unsigned int v92[2]; // [rsp+D8h] [rbp-28h]
  BSTR v93; // [rsp+E0h] [rbp-20h]
  BOOL v94; // [rsp+E8h] [rbp-18h]
  CCorSvcMgr *v95; // [rsp+F0h] [rbp-10h]
  BSTR *p_Source; // [rsp+F8h] [rbp-8h]
  struct _RTL_CRITICAL_SECTION *v97; // [rsp+100h] [rbp+0h]
  char v98; // [rsp+108h] [rbp+8h]
  BSTR v99; // [rsp+110h] [rbp+10h]
  BOOL v100; // [rsp+118h] [rbp+18h]
  struct ICorSvcWorker *v101; // [rsp+120h] [rbp+20h]
  int v102; // [rsp+128h] [rbp+28h]
  _BYTE v103[8]; // [rsp+130h] [rbp+30h] BYREF
  __int128 v104; // [rsp+138h] [rbp+38h] BYREF
  int v105; // [rsp+150h] [rbp+50h] BYREF
  __int64 v106; // [rsp+154h] [rbp+54h]
  OLECHAR *psz; // [rsp+160h] [rbp+60h]
  _WORD v108[260]; // [rsp+168h] [rbp+68h] BYREF
  int v109; // [rsp+370h] [rbp+270h] BYREF
  __int64 v110; // [rsp+374h] [rbp+274h]
  LPVOID lpMem; // [rsp+380h] [rbp+280h]
  _WORD v112[260]; // [rsp+388h] [rbp+288h] BYREF

  *(_QWORD *)v92 = a4;
  v101 = a3;
  v5 = a2;
  bstrString = a2;
  v6 = this;
  v95 = this;
  v7 = a5;
  v87 = 0;
  if ( !a5 )
  {
    v7 = (CCorSvcMgr *)((char *)this + 24);
    if ( !this )
      v7 = 0;
  }
  v97 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 152);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  v98 = 1;
  v8 = *((_DWORD *)v6 + 316);
  if ( v8 < 0 && !*((_DWORD *)v6 + 317) || v8 == -2147024784 )
    ThrowHR(-2147467260);
  v9 = (void **)*((_QWORD *)v5 + 1);
  v81 = v9[1];
  RootPath = Configuration::GetRootPath((Configuration *)v9);
  v99 = SysAllocString(RootPath);
  v91 = v99 != 0;
  v100 = v91;
  v11 = *((_QWORD *)v5 + 11);
  if ( v11 )
  {
    SString::ConvertToUnicode(*((SString **)v5 + 11));
    v12 = *(const OLECHAR **)(v11 + 16);
  }
  else
  {
    v12 = 0;
  }
  v93 = SysAllocString(v12);
  v90 = v93 != 0;
  v94 = v90;
  Source = 0;
  v86 = 0;
  v13 = v5 + 24;
  v14 = v5 + 12;
  rgIndices = 0;
  if ( (*((_DWORD *)v5 + 12) & 0xFFFFFFF8) != 0 )
  {
    v15 = 0;
    do
    {
      v16 = *(_QWORD *)(*((_QWORD *)v13 + 2) + 8LL * v15);
      v17 = 0;
      if ( (*(_DWORD *)(v16 + 48) & 0xFFFFFFF8) != 0 )
      {
        do
        {
          v18 = *(BSTR **)(*(_QWORD *)(v16 + 64) + 8LL * v17);
          p_Source = v18;
          v19 = 0;
          v20 = *(_DWORD *)v13 >> 3;
          if ( v20 )
          {
            while ( *(BSTR **)(*((_QWORD *)v13 + 2) + 8LL * v19) != v18 )
            {
              if ( ++v19 >= v20 )
                goto LABEL_16;
            }
          }
          else
          {
LABEL_16:
            if ( *((_DWORD *)v13 + 1) >> 3 == v20 )
            {
              v21 = 16 * v20;
              if ( (unsigned int)v21 > *((_DWORD *)v13 + 1) )
                SBuffer::ReallocateBuffer(v13, v21, 1);
            }
            SArray<LogicalImage *,1>::End(v13, psa);
            SBuffer::Replace((SBuffer *)v13, (const struct SBuffer::Iterator *)&psa[1], 0, 8u);
            *(_QWORD *)psa[1] = v18;
            v22 = 0;
            v23 = *(_DWORD *)v14 >> 3;
            if ( v23 )
            {
              while ( *(BSTR **)(*((_QWORD *)v14 + 2) + 8LL * v22) != p_Source )
              {
                if ( ++v22 >= v23 )
                  goto LABEL_26;
              }
              if ( (v14[4] & 0x10) != 0 )
                SBuffer::ReallocateBuffer(v14, *((unsigned int *)v14 + 1), 1);
              v88[0] = *((SAFEARRAY **)v14 + 2);
              psa[1] = v88[1];
              psa[0] = (SAFEARRAY *)((char *)v88[0] + (int)(8 * v22));
              v104 = *(_OWORD *)psa;
              SBuffer::Replace((SBuffer *)v14, (const struct SBuffer::Iterator *)&v104, 8u, 0);
            }
          }
LABEL_26:
          ++v17;
        }
        while ( v17 < *(_DWORD *)(v16 + 48) >> 3 );
        v15 = rgIndices;
      }
      rgIndices = ++v15;
    }
    while ( v15 < *(_DWORD *)v13 >> 3 );
    v5 = bstrString;
    v6 = v95;
  }
  Vector = 0;
  psa[0] = 0;
  LODWORD(psa[1]) = 0;
  v25 = 0;
  v88[0] = 0;
  LODWORD(v88[1]) = 0;
  if ( *(_DWORD *)(*((_QWORD *)v5 + 1) + 24LL) != 0x200000 )
  {
    Vector = SafeArrayCreateVector(8u, 0, *(_DWORD *)v13 >> 3);
    psa[0] = Vector;
    if ( !Vector || (LODWORD(psa[1]) = 1, (v88[0] = SafeArrayCreateVector(8u, 0, *(_DWORD *)v14 >> 3)) == 0) )
      ThrowLastError();
    LODWORD(v88[1]) = 1;
    v26 = 0;
    if ( (*(_DWORD *)v13 & 0xFFFFFFF8) != 0 )
    {
      do
      {
        rgIndices = v26;
        v27 = *(_QWORD *)(*((_QWORD *)v13 + 2) + 8LL * v26);
        v28 = *(SString **)(v27 + 104);
        if ( v28 || (v28 = *(SString **)(v27 + 88)) != 0 )
        {
          SString::ConvertToUnicode(v28);
          v29 = (const OLECHAR *)*((_QWORD *)v28 + 2);
        }
        else
        {
          v29 = 0;
        }
        bstrString = SysAllocString(v29);
        v30 = bstrString != 0;
        v84 = v30;
        v31 = SafeArrayPutElement(psa[0], &rgIndices, bstrString);
        if ( v31 < 0 )
          ThrowHR(v31);
        if ( v30 )
        {
          SysFreeString(bstrString);
          v84 = 0;
        }
        ++v26;
      }
      while ( v26 < *(_DWORD *)v13 >> 3 );
      Vector = psa[0];
    }
    v32 = 0;
    if ( (*(_DWORD *)v14 & 0xFFFFFFF8) != 0 )
    {
      do
      {
        rgIndices = v32;
        v33 = *(_QWORD *)(*((_QWORD *)v14 + 2) + 8LL * v32);
        v34 = *(SString **)(v33 + 104);
        if ( v34 || (v34 = *(SString **)(v33 + 88)) != 0 )
        {
          SString::ConvertToUnicode(v34);
          v35 = (const OLECHAR *)*((_QWORD *)v34 + 2);
        }
        else
        {
          v35 = 0;
        }
        v36 = SysAllocString(v35);
        bstrString = v36;
        v84 = v36 != 0;
        v37 = SafeArrayPutElement(v88[0], &rgIndices, v36);
        if ( v37 < 0 )
          ThrowHR(v37);
        if ( v36 )
        {
          SysFreeString(v36);
          v84 = 0;
        }
        ++v32;
      }
      while ( v32 < *(_DWORD *)v14 >> 3 );
      Vector = psa[0];
    }
    v25 = v88[0];
  }
  if ( *((_QWORD *)v6 + 24) )
  {
    v110 = 512;
    lpMem = v112;
    v109 = 2;
    v112[0] = 0;
    v106 = 512;
    psz = v108;
    v105 = 2;
    v108[0] = 0;
    v38 = *((_QWORD *)v5 + 1);
    SBuffer::Set((SBuffer *)&v109, (const struct SBuffer *)(v38 + 616));
    HIDWORD(v110) = HIDWORD(v110) & 0xFFFFFFF8 | *(_DWORD *)(v38 + 624) & 7;
    HIDWORD(v110) &= ~0x100u;
    SString::ConvertToUnicode((SString *)&v109);
    SString::Printf((SString *)&v105, L"%s (CLR %s)", v93, lpMem);
    SString::ConvertToUnicode((SString *)&v105);
    v39 = SysAllocString(psz);
    bstrString = v39;
    v84 = v39 != 0;
    CCorSvcMgr::NotifyProgressNotification(
      (CCorSvcMgr *)(unsigned int)(3 * ((**((_DWORD **)v6 + 16) >> 3) + 1)),
      *((struct ICompileProgressNotification **)v6 + 24),
      *((_DWORD *)v6 + 54) - (**((_DWORD **)v6 + 16) >> 3),
      v39,
      1,
      0,
      v79,
      3 * ((**((_DWORD **)v6 + 16) >> 3) + 1),
      v92[0]);
    if ( v39 )
    {
      SysFreeString(v39);
      v84 = 0;
    }
    if ( (v106 & 0x800000000LL) != 0 )
    {
      v40 = psz;
      if ( psz )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v40);
      }
    }
    if ( (v110 & 0x800000000LL) != 0 )
    {
      v42 = lpMem;
      if ( lpMem )
      {
        v43 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v43 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v43;
        }
        HeapFree(v43, 0, v42);
      }
    }
  }
  v44 = (struct _RTL_CRITICAL_SECTION *)((char *)v6 + 152);
  bstrString = (BSTR)((char *)v6 + 152);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 152));
  v45 = *(_DWORD *)(*((_QWORD *)v5 + 1) + 24LL) | 0x10000;
  if ( !*((_BYTE *)v5 + 120) )
    v45 = *(_DWORD *)(*((_QWORD *)v5 + 1) + 24LL);
  p_Source = &Source;
  if ( v86 )
  {
    SysFreeString(Source);
    v86 = 0;
  }
  Source = 0;
  v87 = 1;
  v46 = (*(__int64 (__fastcall **)(struct ICorSvcWorker *, BSTR, BSTR, _QWORD, SAFEARRAY *, SAFEARRAY *))(*(_QWORD *)v101 + 32LL))(
          v101,
          v93,
          v99,
          v45,
          Vector,
          v25);
  v87 = 0;
  v47 = v86;
  if ( Source )
    v47 = 1;
  v86 = v47;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 152));
  if ( (unsigned int)CCorSvcMgr::IsInterruptRequested(v6) )
    ThrowHR(-2146230784);
  v48 = (struct ICompileProgressNotification *)*((_QWORD *)v6 + 24);
  v49 = *(_QWORD *)v92;
  if ( v48 )
    CCorSvcMgr::NotifyProgressNotification(
      (CCorSvcMgr *)(unsigned int)(3 * ((**((_DWORD **)v6 + 16) >> 3) + 1)),
      v48,
      *((_DWORD *)v6 + 54) - (**((_DWORD **)v6 + 16) >> 3),
      v93,
      0,
      v46,
      0,
      3 * ((**((_DWORD **)v6 + 16) >> 3) + 1),
      v92[0]);
  v50 = *((_DWORD *)v6 + 316);
  if ( v50 < 0 && !*((_DWORD *)v6 + 317) || v50 == -2147024784 )
    ThrowHR(-2147467260);
  if ( v46 < 0 )
  {
    Node::SetStatus(v5, 4);
    v110 = 512;
    lpMem = v112;
    v109 = 2;
    v112[0] = 0;
    GetHRMsg(v46, (struct SString *)&v109, v58);
    v106 = 512;
    psz = v108;
    v105 = 2;
    v108[0] = 0;
    if ( v46 == -2147024784 )
    {
      Node::SetStatus(v5, 3);
      ThrowHR(-2147024784, (const struct SString *)&v109);
    }
    if ( *((_DWORD *)v6 + 320) && !*((_BYTE *)v5 + 120) && v49 )
    {
      SString::ConvertToUnicode((SString *)&v109);
      v59 = lpMem;
      v60 = *((_QWORD *)v5 + 11);
      if ( v60 )
      {
        SString::ConvertToUnicode(*((SString **)v5 + 11));
        v61 = *(_QWORD *)(v60 + 16);
      }
      else
      {
        v61 = 0;
      }
      SString::Printf(
        (SString *)&v105,
        L"Ngen failed to generate native code for image %s because of the following error: %s\n",
        v61,
        v59);
      SString::ConvertToUnicode((SString *)&v105);
      if ( v7 )
      {
        v62 = SysAllocString(psz);
        v81 = v62;
        LODWORD(v82) = v62 != 0;
        (*(void (__fastcall **)(struct ICorSvcLogger *, __int64, BSTR))(*(_QWORD *)v7 + 24LL))(v7, 1, v62);
        if ( v62 )
        {
          SysFreeString(v62);
          LODWORD(v82) = 0;
        }
      }
      SString::Clear((SString *)&v105);
      v63 = *((_QWORD *)v5 + 11);
      if ( v63 )
      {
        SString::ConvertToUnicode(*((SString **)v5 + 11));
        v64 = *(_QWORD *)(v63 + 16);
      }
      else
      {
        v64 = 0;
      }
      SString::Printf((SString *)&v105, L"Ngen will retry compilation of image %s\n", v64);
      SString::ConvertToUnicode((SString *)&v105);
      if ( v7 )
      {
        v65 = SysAllocString(psz);
        v81 = v65;
        LODWORD(v82) = v65 != 0;
        (*(void (__fastcall **)(struct ICorSvcLogger *, __int64, BSTR))(*(_QWORD *)v7 + 24LL))(v7, 1, v65);
        if ( v65 )
        {
          SysFreeString(v65);
          LODWORD(v82) = 0;
        }
      }
    }
    else
    {
      if ( (unsigned int)SString::EqualsCaseInsensitive(
                           *(SString **)(*(_QWORD *)(*((_QWORD *)v5 + 1) + 8LL) + 24LL),
                           *((const struct SString **)v5 + 11)) )
      {
        SString::ConvertToUnicode((SString *)&v109);
        v66 = lpMem;
        v67 = *((_QWORD *)v81 + 3);
        if ( v67 )
        {
          SString::ConvertToUnicode(*((SString **)v81 + 3));
          v68 = *(_QWORD *)(v67 + 16);
        }
        else
        {
          v68 = 0;
        }
        SString::Printf(
          (SString *)&v105,
          L"Uninstalling assembly %s because of an error during compilation: %s\n",
          v68,
          v66);
        SString::ConvertToUnicode((SString *)&v105);
        if ( v7 )
        {
          v69 = SysAllocString(psz);
          v81 = v69;
          LODWORD(v82) = v69 != 0;
          (*(void (__fastcall **)(struct ICorSvcLogger *, __int64, BSTR))(*(_QWORD *)v7 + 24LL))(v7, 1, v69);
          LODWORD(v7) = 0;
          if ( v69 )
          {
            SysFreeString(v69);
            LODWORD(v82) = 0;
          }
        }
        Node::SetStatus(*((_QWORD *)v5 + 1), 0);
        v70 = *((_QWORD *)v5 + 1);
        v71 = (unsigned int)v7;
        if ( (*(_DWORD *)(v70 + 32) & 0xFFFFFFF8) != 0 )
        {
          v72 = (CCorSvcMgr *)((char *)v6 + 104);
          do
          {
            v73 = *(_QWORD *)(*(_QWORD *)(v70 + 48) + 8LL * v71);
            if ( *(_DWORD *)v72 >= 8u )
            {
              SArray<SString,0>::Begin(v72, &v81);
              for ( i = v82;
                    (unsigned int)((unsigned __int64)((int)i - *(_DWORD *)(SArray<LogicalImage *,1>::End(v72, v103) + 8)) >> 3);
                    v82 = i )
              {
                if ( v73 == *i )
                {
                  SBuffer::Replace(v72, (const struct SBuffer::Iterator *)&v82, 8u, 0);
                  break;
                }
                ++i;
              }
            }
            ++v71;
          }
          while ( v71 < *(_DWORD *)(v70 + 32) >> 3 );
          v6 = v95;
          Vector = psa[0];
        }
        CCorSvcMgr::HandleCompileFailure(v6, v46, (struct SString *)&v105);
      }
      else
      {
        SString::ConvertToUnicode((SString *)&v109);
        v75 = lpMem;
        v76 = *((_QWORD *)v5 + 11);
        if ( v76 )
        {
          SString::ConvertToUnicode(*((SString **)v5 + 11));
          v77 = *(_QWORD *)(v76 + 16);
        }
        else
        {
          v77 = 0;
        }
        SString::Printf(
          (SString *)&v105,
          L"Failed to generate native code for dependent image %s because of the following error: %s\n",
          v77,
          v75);
        SString::ConvertToUnicode((SString *)&v105);
        if ( v7 )
        {
          v78 = SysAllocString(psz);
          v81 = v78;
          LODWORD(v82) = v78 != 0;
          (*(void (__fastcall **)(struct ICorSvcLogger *, __int64, BSTR))(*(_QWORD *)v7 + 24LL))(v7, 1, v78);
          if ( v78 )
          {
            SysFreeString(v78);
            LODWORD(v82) = 0;
          }
        }
        if ( *((int *)v6 + 322) >= 0 )
          *((_DWORD *)v6 + 322) = v46;
      }
      v44 = v97;
    }
    if ( (v106 & 0x800000000LL) != 0 )
      operator delete(psz);
    if ( (v110 & 0x800000000LL) != 0 )
      operator delete(lpMem);
  }
  else if ( Source )
  {
    v51 = operator new(0x18u);
    v52 = (wchar_t **)v51;
    v81 = v51;
    if ( v51 )
    {
      v53 = Source;
      v101 = (struct ICorSvcWorker *)v51;
      *v51 = 2;
      v51[1] = 2;
      v51[2] = 16;
      *((_QWORD *)v51 + 2) = &SString::s_EmptyBuffer;
      if ( !v53 )
        ThrowHR(-2147024736);
      if ( *v53 )
      {
        v54 = -1;
        do
          ++v54;
        while ( v53[v54] );
        SString::Resize(v51, v54, 4);
        wcscpy_s(v52[2], (unsigned __int64)*(unsigned int *)v52 >> (((_DWORD)v52[1] & 1) == 0), v53);
      }
      else
      {
        SString::Clear((SString *)v51);
      }
    }
    else
    {
      v52 = 0;
    }
    v81 = v52;
    LODWORD(v82) = v52 != 0;
    v55 = (struct ICorSvcWorker *)(*((_QWORD *)v5 + 1) + 644LL);
    v102 = *(_DWORD *)v55;
    v56 = v102;
    v101 = v55;
    *(_DWORD *)v55 = 0;
    LogicalImage::SetNativeImage(v5, &v81);
    *(_DWORD *)v55 = v56;
    Node::SetStatus(v5, 5);
    if ( (_DWORD)v82 )
    {
      v57 = v81;
      if ( v81 )
      {
        if ( (*((_BYTE *)v81 + 8) & 8) != 0 )
          operator delete(*((void **)v81 + 2));
        operator delete(v57);
      }
      LODWORD(v82) = 0;
    }
  }
  if ( LODWORD(v88[1]) )
  {
    SafeArrayDestroy(v88[0]);
    LODWORD(v88[1]) = 0;
  }
  if ( LODWORD(psa[1]) )
  {
    SafeArrayDestroy(Vector);
    LODWORD(psa[1]) = 0;
  }
  if ( v86 )
  {
    SysFreeString(Source);
    v86 = 0;
  }
  if ( v90 )
  {
    SysFreeString(v93);
    v94 = 0;
  }
  if ( v91 )
  {
    SysFreeString(v99);
    v100 = 0;
  }
  LeaveCriticalSection(v44);
}

```

## disassembly

```asm
0x1800270b0  mov     [rsp-8+arg_18], rbx
0x1800270b5  push    rbp
0x1800270b6  push    rsi
0x1800270b7  push    rdi
0x1800270b8  push    r12
0x1800270ba  push    r13
0x1800270bc  push    r14
0x1800270be  push    r15
0x1800270c0  lea     rbp, [rsp-4A0h]
0x1800270c8  sub     rsp, 5A0h
0x1800270cf  mov     rax, cs:__security_cookie
0x1800270d6  xor     rax, rsp
0x1800270d9  mov     [rbp+4D0h+var_40], rax
0x1800270e0  mov     qword ptr [rbp+4D0h+var_4F8], r9
0x1800270e4  mov     [rbp+4D0h+var_4B0], r8
0x1800270e8  mov     rsi, rdx
0x1800270eb  mov     [rsp+5D0h+bstrString], rdx
0x1800270f0  mov     r14, rcx
0x1800270f3  mov     [rbp+4D0h+var_4E0], rcx
0x1800270f7  mov     rbx, [rbp+4D0h+arg_20]
0x1800270fe  xor     r15d, r15d
0x180027101  mov     [rbp+4D0h+var_540], r15d
0x180027105  test    rbx, rbx
0x180027108  jnz     short loc_180027116
0x18002710a  test    rcx, rcx
0x18002710d  lea     rbx, [rcx+18h]
0x180027111  jnz     short loc_180027116
0x180027113  mov     ebx, r15d
0x180027116  lea     rax, [rcx+98h]
0x18002711d  mov     [rbp+4D0h+var_4D0], rax
0x180027121  mov     [rbp+4D0h+var_4C8], r15b
0x180027125  mov     rcx, rax; lpCriticalSection
0x180027128  call    cs:__imp_EnterCriticalSection
0x18002712e  mov     r12d, 1
0x180027134  mov     [rbp+4D0h+var_4C8], r12b
0x180027138  mov     eax, [r14+4F0h]
0x18002713f  test    eax, eax
0x180027141  jns     short loc_180027150
0x180027143  cmp     [r14+4F4h], r15d
0x18002714a  jz      loc_180027E52
0x180027150  cmp     eax, 80070070h
0x180027155  jz      loc_180027E52
0x18002715b  mov     rcx, [rsi+8]; this
0x18002715f  mov     rax, [rcx+8]
0x180027163  mov     [rsp+5D0h+var_578], rax
0x180027168  call    ?GetRootPath@Configuration@@QEAAPEBGXZ; Configuration::GetRootPath(void)
0x18002716d  mov     rcx, rax; psz
0x180027170  call    cs:__imp_SysAllocString
0x180027176  mov     rcx, rax
0x180027179  mov     [rbp+4D0h+var_4C0], rax
0x18002717d  mov     [rbp+4D0h+var_4B8], r15d
0x180027181  mov     eax, r15d
0x180027184  test    rcx, rcx
0x180027187  cmovnz  eax, r12d
0x18002718b  mov     [rbp+4D0h+var_4FC], eax
0x18002718e  mov     [rbp+4D0h+var_4B8], eax
0x180027191  mov     rdi, [rsi+58h]
0x180027195  test    rdi, rdi
0x180027198  jnz     short loc_18002719F
0x18002719a  mov     rcx, r15
0x18002719d  jmp     short loc_1800271AB
0x18002719f  mov     rcx, rdi; this
0x1800271a2  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800271a7  mov     rcx, [rdi+10h]; psz
0x1800271ab  call    cs:__imp_SysAllocString
0x1800271b1  mov     [rbp+4D0h+var_4F0], rax
0x1800271b5  xor     r8d, r8d
0x1800271b8  mov     [rbp+4D0h+var_4E8], r8d
0x1800271bc  mov     ecx, r8d
0x1800271bf  test    rax, rax
0x1800271c2  cmovnz  ecx, r12d
0x1800271c6  mov     [rbp+4D0h+var_500], ecx
0x1800271c9  mov     [rbp+4D0h+var_4E8], ecx
0x1800271cc  mov     [rbp+4D0h+Source], r8
0x1800271d0  mov     [rbp+4D0h+var_548], r8d
0x1800271d4  lea     rdi, [rsi+30h]
0x1800271d8  lea     r15, [rsi+18h]
0x1800271dc  mov     [rsp+5D0h+rgIndices], r8d
0x1800271e1  test    dword ptr [rdi], 0FFFFFFF8h
0x1800271e7  jbe     loc_180027347
0x1800271ed  mov     r14d, r8d
0x1800271f0  mov     ecx, r14d
0x1800271f3  mov     rax, [rdi+10h]
0x1800271f7  mov     rsi, [rax+rcx*8]
0x1800271fb  mov     r13d, r8d
0x1800271fe  test    dword ptr [rsi+30h], 0FFFFFFF8h
0x180027205  jbe     loc_180027328
0x18002720b  mov     r14d, 1
0x180027211  mov     ecx, r13d
0x180027214  mov     rax, [rsi+40h]
0x180027218  mov     r12, [rax+rcx*8]
0x18002721c  mov     [rbp+4D0h+var_4D8], r12
0x180027220  mov     ecx, r8d
0x180027223  mov     edx, [rdi]
0x180027225  shr     edx, 3
0x180027228  test    edx, edx
0x18002722a  jz      short loc_180027243
0x18002722c  mov     r8, [rdi+10h]
0x180027230  mov     eax, ecx
0x180027232  cmp     [r8+rax*8], r12
0x180027236  jz      loc_180027308
0x18002723c  add     ecx, r14d
0x18002723f  cmp     ecx, edx
0x180027241  jb      short loc_180027230
0x180027243  mov     eax, [rdi+4]
0x180027246  shr     eax, 3
0x180027249  cmp     eax, edx
0x18002724b  jnz     short loc_180027260
0x18002724d  shl     edx, 4
0x180027250  cmp     edx, [rdi+4]
0x180027253  jbe     short loc_180027260
0x180027255  mov     r8d, r14d
0x180027258  mov     rcx, rdi
0x18002725b  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x180027260  lea     rdx, [rbp+4D0h+psa]
0x180027264  mov     rcx, rdi
0x180027267  call    ?End@?$SArray@PEAVLogicalImage@@$00@@QEAA?AVIterator@1@XZ; SArray<LogicalImage *,1>::End(void)
0x18002726c  mov     r9d, 8; unsigned int
0x180027272  xor     r8d, r8d; unsigned int
0x180027275  lea     rdx, [rbp+4D0h+psa+8]; struct SBuffer::Iterator *
0x180027279  mov     rcx, rdi; this
0x18002727c  call    ?Replace@SBuffer@@QEAAXAEBVIterator@1@II@Z; SBuffer::Replace(SBuffer::Iterator const &,uint,uint)
0x180027281  mov     rax, [rbp+4D0h+psa+8]
0x180027285  mov     [rax], r12
0x180027288  xor     r8d, r8d
0x18002728b  mov     r12d, r8d
0x18002728e  mov     ecx, [r15]
0x180027291  shr     ecx, 3
0x180027294  test    ecx, ecx
0x180027296  jz      short loc_18002730B
0x180027298  mov     r8, [r15+10h]
0x18002729c  mov     rdx, [rbp+4D0h+var_4D8]
0x1800272a0  mov     eax, r12d
0x1800272a3  cmp     [r8+rax*8], rdx
0x1800272a7  jz      short loc_1800272B3
0x1800272a9  add     r12d, r14d
0x1800272ac  cmp     r12d, ecx
0x1800272af  jb      short loc_1800272A0
0x1800272b1  jmp     short loc_180027308
0x1800272b3  test    byte ptr [r15+8], 10h
0x1800272b8  jz      short loc_1800272C9
0x1800272ba  mov     r8d, r14d
0x1800272bd  mov     edx, [r15+4]
0x1800272c1  mov     rcx, r15
0x1800272c4  call    ?ReallocateBuffer@SBuffer@@IEAAXIW4Preserve@1@@Z; SBuffer::ReallocateBuffer(uint,SBuffer::Preserve)
0x1800272c9  mov     rdx, [r15+10h]
0x1800272cd  mov     [rbp+4D0h+var_530], rdx
0x1800272d1  movaps  xmm0, xmmword ptr [rbp+4D0h+var_530]
0x1800272d5  movdqa  xmmword ptr [rbp+4D0h+psa], xmm0
0x1800272da  lea     eax, ds:0[r12*8]
0x1800272e2  movsxd  rcx, eax
0x1800272e5  add     rcx, rdx
0x1800272e8  mov     [rbp+4D0h+psa], rcx
0x1800272ec  movaps  xmm0, xmmword ptr [rbp+4D0h+psa]
0x1800272f0  movdqu  [rbp+4D0h+var_498], xmm0
0x1800272f5  xor     r9d, r9d; unsigned int
0x1800272f8  lea     r8d, [r9+8]; unsigned int
0x1800272fc  lea     rdx, [rbp+4D0h+var_498]; struct SBuffer::Iterator *
0x180027300  mov     rcx, r15; this
0x180027303  call    ?Replace@SBuffer@@QEAAXAEBVIterator@1@II@Z; SBuffer::Replace(SBuffer::Iterator const &,uint,uint)
0x180027308  xor     r8d, r8d
0x18002730b  add     r13d, r14d
0x18002730e  mov     eax, [rsi+30h]
0x180027311  shr     eax, 3
0x180027314  cmp     r13d, eax
0x180027317  jb      loc_180027211
0x18002731d  mov     r14d, [rsp+5D0h+rgIndices]
0x180027322  mov     r12d, 1
0x180027328  add     r14d, r12d
0x18002732b  mov     [rsp+5D0h+rgIndices], r14d
0x180027330  mov     eax, [rdi]
0x180027332  shr     eax, 3
0x180027335  cmp     r14d, eax
0x180027338  jb      loc_1800271F0
0x18002733e  mov     rsi, [rsp+5D0h+bstrString]
0x180027343  mov     r14, [rbp+4D0h+var_4E0]
0x180027347  mov     r13, r8
0x18002734a  mov     [rbp+4D0h+psa], r8
0x18002734e  mov     dword ptr [rbp+4D0h+psa+8], r8d
0x180027352  mov     r12, r8
0x180027355  mov     [rbp+4D0h+var_530], r8
0x180027359  mov     dword ptr [rbp+4D0h+var_530+8], r8d
0x18002735d  mov     rax, [rsi+8]
0x180027361  cmp     dword ptr [rax+18h], 200000h
0x180027368  jz      loc_180027529
0x18002736e  mov     r8d, [rdi]
0x180027371  shr     r8d, 3; cElements
0x180027375  mov     ecx, 8; vt
0x18002737a  xor     edx, edx; lLbound
0x18002737c  call    cs:__imp_SafeArrayCreateVector
0x180027382  mov     r13, rax
0x180027385  mov     [rbp+4D0h+psa], rax
0x180027389  test    rax, rax
0x18002738c  jz      loc_180027E78
0x180027392  mov     r12d, 1
0x180027398  mov     dword ptr [rbp+4D0h+psa+8], r12d
0x18002739c  mov     r8d, [r15]
0x18002739f  shr     r8d, 3; cElements
0x1800273a3  lea     ecx, [r12+7]; vt
0x1800273a8  xor     edx, edx; lLbound
0x1800273aa  call    cs:__imp_SafeArrayCreateVector
0x1800273b0  mov     [rbp+4D0h+var_530], rax
0x1800273b4  xor     r8d, r8d
0x1800273b7  test    rax, rax
0x1800273ba  jz      loc_180027E78
0x1800273c0  mov     dword ptr [rbp+4D0h+var_530+8], r12d
0x1800273c4  mov     r12d, r8d
0x1800273c7  test    dword ptr [rdi], 0FFFFFFF8h
0x1800273cd  jbe     loc_180027475
0x1800273d3  mov     [rsp+5D0h+rgIndices], r12d
0x1800273d8  mov     ecx, r12d
0x1800273db  mov     rax, [rdi+10h]
0x1800273df  mov     rdx, [rax+rcx*8]
0x1800273e3  mov     r13, [rdx+68h]
0x1800273e7  test    r13, r13
0x1800273ea  jnz     short loc_1800273FA
0x1800273ec  mov     r13, [rdx+58h]
0x1800273f0  test    r13, r13
0x1800273f3  jnz     short loc_1800273FA
0x1800273f5  mov     rcx, r8
0x1800273f8  jmp     short loc_180027406
0x1800273fa  mov     rcx, r13; this
0x1800273fd  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180027402  mov     rcx, [r13+10h]; psz
0x180027406  call    cs:__imp_SysAllocString
0x18002740c  mov     [rsp+5D0h+bstrString], rax
0x180027411  xor     ecx, ecx
0x180027413  mov     [rsp+5D0h+var_558], ecx
0x180027417  mov     r13d, ecx
0x18002741a  test    rax, rax
0x18002741d  mov     ecx, 1
0x180027422  cmovnz  r13d, ecx
0x180027426  mov     [rsp+5D0h+var_558], r13d
0x18002742b  mov     r8, rax; pv
0x18002742e  lea     rdx, [rsp+5D0h+rgIndices]; rgIndices
0x180027433  mov     rcx, [rbp+4D0h+psa]; psa
0x180027437  call    cs:__imp_SafeArrayPutElement
0x18002743d  xor     r8d, r8d
0x180027440  test    eax, eax
0x180027442  js      loc_180027E5D
0x180027448  test    r13d, r13d
0x18002744b  jz      short loc_180027460
0x18002744d  mov     rcx, [rsp+5D0h+bstrString]; bstrString
0x180027452  call    cs:__imp_SysFreeString
0x180027458  xor     r8d, r8d
0x18002745b  mov     [rsp+5D0h+var_558], r8d
0x180027460  inc     r12d
0x180027463  mov     eax, [rdi]
0x180027465  shr     eax, 3
0x180027468  cmp     r12d, eax
0x18002746b  jb      loc_1800273D3
0x180027471  mov     r13, [rbp+4D0h+psa]
0x180027475  mov     r12d, r8d
0x180027478  test    dword ptr [r15], 0FFFFFFF8h
0x18002747f  jbe     loc_180027525
0x180027485  mov     [rsp+5D0h+rgIndices], r12d
0x18002748a  mov     ecx, r12d
0x18002748d  mov     rax, [r15+10h]
0x180027491  mov     rdx, [rax+rcx*8]
0x180027495  mov     rdi, [rdx+68h]
0x180027499  test    rdi, rdi
0x18002749c  jnz     short loc_1800274AC
0x18002749e  mov     rdi, [rdx+58h]
0x1800274a2  test    rdi, rdi
0x1800274a5  jnz     short loc_1800274AC
0x1800274a7  mov     rcx, r8
0x1800274aa  jmp     short loc_1800274B8
0x1800274ac  mov     rcx, rdi; this
0x1800274af  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800274b4  mov     rcx, [rdi+10h]; psz
0x1800274b8  call    cs:__imp_SysAllocString
0x1800274be  mov     r13, rax
0x1800274c1  mov     [rsp+5D0h+bstrString], rax
0x1800274c6  xor     eax, eax
0x1800274c8  mov     [rsp+5D0h+var_558], eax
0x1800274cc  mov     edi, eax
0x1800274ce  test    r13, r13
0x1800274d1  mov     eax, 1
0x1800274d6  cmovnz  edi, eax
0x1800274d9  mov     [rsp+5D0h+var_558], edi
0x1800274dd  mov     r8, r13; pv
0x1800274e0  lea     rdx, [rsp+5D0h+rgIndices]; rgIndices
0x1800274e5  mov     rcx, [rbp+4D0h+var_530]; psa
0x1800274e9  call    cs:__imp_SafeArrayPutElement
0x1800274ef  xor     r8d, r8d
0x1800274f2  test    eax, eax
0x1800274f4  js      loc_180027E70
0x1800274fa  test    edi, edi
0x1800274fc  jz      short loc_18002750F
0x1800274fe  mov     rcx, r13; bstrString
0x180027501  call    cs:__imp_SysFreeString
0x180027507  xor     r8d, r8d
0x18002750a  mov     [rsp+5D0h+var_558], r8d
0x18002750f  inc     r12d
0x180027512  mov     eax, [r15]
0x180027515  shr     eax, 3
0x180027518  cmp     r12d, eax
0x18002751b  jb      loc_180027485
0x180027521  mov     r13, [rbp+4D0h+psa]
0x180027525  mov     r12, [rbp+4D0h+var_530]
  ... truncated ...
```
