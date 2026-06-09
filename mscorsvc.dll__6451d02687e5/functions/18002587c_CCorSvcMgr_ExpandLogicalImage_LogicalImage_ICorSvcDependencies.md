# CCorSvcMgr::ExpandLogicalImage(LogicalImage *,ICorSvcDependencies *)

- ea: `0x18002587c`
- end: `0x180026438`
- name: `?ExpandLogicalImage@CCorSvcMgr@@AEAAXPEAVLogicalImage@@PEAUICorSvcDependencies@@@Z`
- size: `3004`
- prototype: `void(CCorSvcMgr *__hidden this, struct LogicalImage *, struct ICorSvcDependencies *)`
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800249b0`
- `0x18002587c`

## callees

- `0x180001e8c`
- `0x180002504`
- `0x180006488`
- `0x18000af58`
- `0x18000b610`
- `0x18000b8dc`
- `0x18000c8a8`
- `0x18000ce84`
- `0x180013e2c`
- `0x180025110`
- `0x1800252ac`
- `0x18002587c`
- `0x18002bfe8`
- `0x18002c874`
- `0x18002db88`
- `0x18002dc24`
- `0x18002e418`
- `0x1800304ec`
- `0x180030568`
- `0x180030ab8`
- `0x180030d84`
- `0x180032654`
- `0x180034fd4`
- `0x1800350c4`
- `0x180035228`
- `0x18003dc30`
- `0x18003f280`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180025c1c`
- `KERNEL32!HeapFree` at `0x180025ddb`
- `KERNEL32!HeapFree` at `0x180025c1c`
- `KERNEL32!HeapFree` at `0x180025ddb`
- `KERNEL32!GetProcessHeap` at `0x180025c07`
- `KERNEL32!GetProcessHeap` at `0x180025dc6`
- `KERNEL32!GetProcessHeap` at `0x180025c07`
- `KERNEL32!GetProcessHeap` at `0x180025dc6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800258e3`
- `OLEAUT32!__imp_SysAllocString` at `0x1800258e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800259b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800259dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180025df1`
- `OLEAUT32!__imp_SysFreeString` at `0x180025e07`
- `OLEAUT32!__imp_SysFreeString` at `0x180025e5f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800261cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800262ae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800262c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002630e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800259b2`
- `OLEAUT32!__imp_SysFreeString` at `0x1800259dc`
- `OLEAUT32!__imp_SysFreeString` at `0x180025df1`
- `OLEAUT32!__imp_SysFreeString` at `0x180025e07`
- `OLEAUT32!__imp_SysFreeString` at `0x180025e5f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800261cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800262ae`
- `OLEAUT32!__imp_SysFreeString` at `0x1800262c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002630e`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025967`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002598a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025a07`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025e1c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025e30`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025e46`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800262d5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800262e7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800262fb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025967`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18002598a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025a07`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025e1c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025e30`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180025e46`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800262d5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800262e7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800262fb`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180025ef4`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180025ef4`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180025f3c`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180025f6c`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180025f86`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180025f3c`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180025f6c`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180025f86`

## string_xrefs

- `0x180025d0a`: `Failed to compile %s because this image is not a valid Win32 application`
- `0x180025cd5`: `Failed to compile %s because this image is a 64bit assembly; try using 64bit ngen instead`
- `0x180025caf`: `Failed to compile %s because this image is a 32bit assembly; try using 32bit ngen instead`
- `0x180025bd2`: `Failed to compile %s because of the following error: %s`
- `0x1800263aa`: `Hardbound dependency "%s" not yet compiled, cannot compile "%s".\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=83
void __fastcall CCorSvcMgr::ExpandLogicalImage(
        CCorSvcMgr *this,
        struct LogicalImage *a2,
        struct ICorSvcDependencies *a3)
{
  _DWORD *v6; // rdi
  __int64 v7; // rbx
  const OLECHAR *v8; // rcx
  OLECHAR *v9; // rbx
  _DWORD *v10; // r12
  struct LogicalImage *LogicalImage; // rdi
  int v12; // ebx
  int v13; // ecx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  unsigned int v17; // r13d
  int v18; // eax
  int v19; // r8d
  LPVOID v20; // r12
  __int64 v21; // rdi
  __int64 v22; // r8
  void *v23; // rdi
  HANDLE ProcessHeap; // rax
  unsigned int v25; // r14d
  __int64 v26; // rdi
  NGENService *v27; // rcx
  __int64 v28; // rdi
  __int64 v29; // r8
  __int64 v30; // rdi
  __int64 v31; // r8
  __int64 v32; // rdi
  __int64 v33; // r8
  int v34; // edi
  int v35; // eax
  void *v36; // rbx
  HANDLE v37; // rax
  SAFEARRAY **v38; // rbx
  const unsigned __int16 *v39; // rdx
  HRESULT UBound; // eax
  LONG v41; // eax
  int v42; // r13d
  HRESULT Element; // eax
  int v44; // eax
  HRESULT v45; // eax
  HRESULT v46; // eax
  int v47; // r12d
  SString *v48; // rax
  SString *v49; // rbx
  const unsigned __int16 *v50; // rdx
  unsigned int v51; // ebx
  Configuration *v52; // rcx
  __int64 v53; // rcx
  const struct SString *v54; // rdx
  int v55; // r8d
  BOOL v56; // ebx
  SString *v57; // rbx
  const unsigned __int16 *v58; // rcx
  SBuffer *v59; // r8
  const wchar_t *v60; // r9
  SString *v61; // rax
  __int64 v62; // rbx
  const unsigned __int16 *v63; // rdx
  Image *ManagedImage; // rax
  const unsigned __int16 *Path; // rbx
  Image *v66; // rax
  const unsigned __int16 *v67; // rax
  const unsigned __int16 *v68; // rax
  unsigned __int16 *v69; // [rsp+20h] [rbp-E0h]
  BSTR v70; // [rsp+58h] [rbp-A8h] BYREF
  int v71; // [rsp+60h] [rbp-A0h]
  SAFEARRAY *v72; // [rsp+68h] [rbp-98h] BYREF
  int v73; // [rsp+70h] [rbp-90h]
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  int v75; // [rsp+80h] [rbp-80h]
  SAFEARRAY *psa; // [rsp+88h] [rbp-78h] BYREF
  int v77; // [rsp+90h] [rbp-70h]
  SAFEARRAY *v78; // [rsp+98h] [rbp-68h] BYREF
  int v79; // [rsp+A0h] [rbp-60h]
  LONG plUbound; // [rsp+A8h] [rbp-58h] BYREF
  int v81; // [rsp+ACh] [rbp-54h]
  BOOL v82; // [rsp+B0h] [rbp-50h]
  Configuration *v83; // [rsp+B8h] [rbp-48h]
  BSTR pv; // [rsp+C0h] [rbp-40h] BYREF
  int v85; // [rsp+C8h] [rbp-38h]
  LONG rgIndices[2]; // [rsp+D0h] [rbp-30h] BYREF
  BSTR *p_bstrString; // [rsp+D8h] [rbp-28h] BYREF
  SAFEARRAY **p_psa; // [rsp+E0h] [rbp-20h]
  _DWORD *v89; // [rsp+E8h] [rbp-18h]
  SAFEARRAY **v90; // [rsp+F0h] [rbp-10h] BYREF
  BOOL v91; // [rsp+F8h] [rbp-8h]
  SAFEARRAY **v92; // [rsp+100h] [rbp+0h] BYREF
  SString *v93; // [rsp+108h] [rbp+8h] BYREF
  BOOL v94; // [rsp+110h] [rbp+10h]
  BSTR v95; // [rsp+118h] [rbp+18h]
  BOOL v96; // [rsp+120h] [rbp+20h]
  SAFEARRAY **p_pv; // [rsp+128h] [rbp+28h]
  char v98[8]; // [rsp+130h] [rbp+30h] BYREF
  struct ICorSvcDependencies *v99; // [rsp+138h] [rbp+38h]
  SString *v100; // [rsp+140h] [rbp+40h]
  SString *v101; // [rsp+148h] [rbp+48h]
  _DWORD *v102; // [rsp+150h] [rbp+50h]
  int v103; // [rsp+158h] [rbp+58h]
  _BYTE v104[16]; // [rsp+160h] [rbp+60h] BYREF
  void *v105; // [rsp+170h] [rbp+70h]
  int v106; // [rsp+380h] [rbp+280h] BYREF
  __int64 v107; // [rsp+384h] [rbp+284h]
  LPVOID lpMem; // [rsp+390h] [rbp+290h]
  _WORD v109[260]; // [rsp+398h] [rbp+298h] BYREF
  int v110; // [rsp+5A0h] [rbp+4A0h] BYREF
  __int64 v111; // [rsp+5A4h] [rbp+4A4h]
  LPVOID v112; // [rsp+5B0h] [rbp+4B0h]
  __int16 v113; // [rsp+5B8h] [rbp+4B8h] BYREF

  v99 = a3;
  v6 = (_DWORD *)*((_QWORD *)a2 + 1);
  v83 = (Configuration *)v6;
  v7 = *((_QWORD *)a2 + 11);
  if ( v7 )
  {
    SString::ConvertToUnicode(*((SString **)a2 + 11));
    v8 = *(const OLECHAR **)(v7 + 16);
  }
  else
  {
    v8 = 0;
  }
  v9 = SysAllocString(v8);
  v95 = v9;
  v82 = v9 != 0;
  v96 = v82;
  v72 = 0;
  v73 = 0;
  v78 = 0;
  v79 = 0;
  psa = 0;
  v77 = 0;
  v70 = 0;
  v71 = 0;
  bstrString = 0;
  v75 = 0;
  v10 = v6 + 161;
  v89 = v10;
  v81 = v6[161];
  v103 = v81;
  v102 = v6 + 161;
  LogicalImage = 0;
  *v10 = 0;
  p_psa = &psa;
  if ( v77 )
  {
    SafeArrayDestroy(psa);
    v77 = 0;
  }
  psa = 0;
  v92 = &v78;
  if ( v79 )
  {
    SafeArrayDestroy(v78);
    v79 = 0;
  }
  v78 = 0;
  p_bstrString = &bstrString;
  if ( v75 )
  {
    SysFreeString(bstrString);
    v75 = 0;
  }
  bstrString = 0;
  *(_QWORD *)rgIndices = &v70;
  if ( v71 )
  {
    SysFreeString(v70);
    v71 = 0;
  }
  v70 = 0;
  p_pv = &v72;
  if ( v73 )
  {
    SafeArrayDestroy(v72);
    v73 = 0;
  }
  v72 = 0;
  v12 = (*(__int64 (__fastcall **)(struct ICorSvcDependencies *, OLECHAR *, SAFEARRAY **, char *, BSTR *, BSTR *, SAFEARRAY **, SAFEARRAY **))(*(_QWORD *)a3 + 24LL))(
          a3,
          v9,
          &v72,
          v98,
          &v70,
          &bstrString,
          &v78,
          &psa);
  v13 = v73;
  if ( v72 )
    v13 = 1;
  v73 = v13;
  v14 = v71;
  if ( v70 )
    v14 = 1;
  v71 = v14;
  v15 = v75;
  if ( bstrString )
    v15 = 1;
  v75 = v15;
  v16 = v79;
  if ( v78 )
    v16 = 1;
  v79 = v16;
  v17 = 0;
  v18 = v77;
  if ( psa )
    v18 = 1;
  v77 = v18;
  if ( v12 < 0 )
  {
    if ( (unsigned int)CCorSvcMgr::IsInterruptRequested(this) )
      ThrowHR(-2146230784);
    v111 = 512;
    v112 = &v113;
    v110 = 2;
    v113 = 0;
    switch ( v12 )
    {
      case -2147024885:
        v32 = *((_QWORD *)a2 + 11);
        if ( v32 )
        {
          SString::ConvertToUnicode(*((SString **)a2 + 11));
          v33 = *(_QWORD *)(v32 + 16);
        }
        else
        {
          v33 = 0;
        }
        SString::Printf(
          (SString *)&v110,
          L"Failed to compile %s because this image is not a valid Win32 application",
          v33);
        break;
      case -2146231038:
        v30 = *((_QWORD *)a2 + 11);
        if ( v30 )
        {
          SString::ConvertToUnicode(*((SString **)a2 + 11));
          v31 = *(_QWORD *)(v30 + 16);
        }
        else
        {
          v31 = 0;
        }
        SString::Printf(
          (SString *)&v110,
          L"Failed to compile %s because this image is a 64bit assembly; try using 64bit ngen instead",
          v31);
        break;
      case -2146231029:
        v28 = *((_QWORD *)a2 + 11);
        if ( v28 )
        {
          SString::ConvertToUnicode(*((SString **)a2 + 11));
          v29 = *(_QWORD *)(v28 + 16);
        }
        else
        {
          v29 = 0;
        }
        SString::Printf(
          (SString *)&v110,
          L"Failed to compile %s because this image is a 32bit assembly; try using 32bit ngen instead",
          v29);
        break;
      default:
        v107 = 512;
        lpMem = v109;
        v106 = 2;
        v109[0] = 0;
        GetHRMsg(v12, (struct SString *)&v106, v19);
        SString::ConvertToUnicode((SString *)&v106);
        v20 = lpMem;
        v21 = *((_QWORD *)a2 + 11);
        if ( v21 )
        {
          SString::ConvertToUnicode(*((SString **)a2 + 11));
          v22 = *(_QWORD *)(v21 + 16);
        }
        else
        {
          v22 = 0;
        }
        SString::Printf((SString *)&v110, L"Failed to compile %s because of the following error: %s", v22, v20);
        if ( (v107 & 0x800000000LL) != 0 )
        {
          v23 = lpMem;
          if ( lpMem )
          {
            ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
            if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
            {
              ProcessHeap = GetProcessHeap();
              `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
            }
            HeapFree(ProcessHeap, 0, v23);
          }
        }
        v10 = v89;
        break;
    }
    InlineSString<512>::InlineSString<512>(v104, &v110);
    SString::Append((SString *)v104, L".\n");
    SString::ConvertToUnicode((SString *)v104);
    Logger::Log((char *)this + 208, v105, 2);
    if ( NGENService::g_bProcessNGENService )
    {
      SString::ConvertToUnicode((SString *)v104);
      v25 = (unsigned int)v105;
      v26 = *((_QWORD *)a2 + 11);
      if ( v26 )
      {
        SString::ConvertToUnicode(*((SString **)a2 + 11));
        v27 = *(NGENService **)(v26 + 16);
      }
      else
      {
        v27 = 0;
      }
      NGENService::EventLog(v27, (const unsigned __int16 *)1, 0x44Du, v25, v69);
    }
    v34 = v81;
    *v10 = v81;
    Node::SetStatus(a2, 4);
    v35 = *((_DWORD *)this + 316);
    if ( v35 >= 0 )
    {
      *((_DWORD *)this + 316) = v12;
      v35 = v12;
    }
    if ( v35 == -2147467260 )
      *((_DWORD *)this + 316) = v12;
    if ( v12 == -2147024784 )
      *((_DWORD *)this + 316) = -2147024784;
    if ( !*((_DWORD *)this + 317) )
      ThrowHR(v12, (const struct SString *)&v110);
    if ( *((int *)this + 321) >= 0 )
      *((_DWORD *)this + 321) = v12;
    if ( (v104[8] & 8) != 0 )
      operator delete(v105);
    if ( (v111 & 0x800000000LL) != 0 )
    {
      v36 = v112;
      if ( v112 )
      {
        v37 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v37 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v37;
        }
        HeapFree(v37, 0, v36);
      }
    }
    *v10 = v34;
    if ( v75 )
    {
      SysFreeString(bstrString);
      v75 = 0;
    }
    if ( v71 )
    {
      SysFreeString(v70);
      v71 = 0;
    }
    if ( v77 )
    {
      SafeArrayDestroy(psa);
      v77 = 0;
    }
    if ( v79 )
    {
      SafeArrayDestroy(v78);
      v79 = 0;
    }
    if ( v73 )
    {
      SafeArrayDestroy(v72);
      v73 = 0;
    }
    if ( v82 )
    {
      SysFreeString(v95);
      v96 = 0;
    }
    return;
  }
  v38 = (SAFEARRAY **)operator new(0x18u);
  p_pv = v38;
  if ( v38 )
  {
    v39 = bstrString;
    p_psa = v38;
    *(_DWORD *)v38 = 2;
    *((_DWORD *)v38 + 1) = 2;
    *((_DWORD *)v38 + 2) = 16;
    v38[2] = (SAFEARRAY *)&SString::s_EmptyBuffer;
    if ( !v39 )
      ThrowHR(-2147024736);
    SString::Set((SString *)v38, v39);
  }
  else
  {
    v38 = 0;
  }
  v90 = v38;
  v91 = v38 != 0;
  LogicalImage::SetDisplayName(a2, &v90);
  plUbound = 0;
  UBound = SafeArrayGetUBound(v72, 1u, &plUbound);
  if ( UBound < 0 )
    ThrowHR(UBound);
  v41 = 0;
  LODWORD(p_psa) = 0;
  if ( plUbound >= 0 )
  {
    while ( 1 )
    {
      v85 = 0;
      rgIndices[0] = v41;
      p_pv = (SAFEARRAY **)&pv;
      pv = 0;
      v42 = v17 | 0x20;
      Element = SafeArrayGetElement(v72, rgIndices, &pv);
      if ( Element < 0 )
        ThrowHR(Element);
      v17 = v42 & 0xFFFFFFDF;
      v44 = v85;
      if ( pv )
        v44 = 1;
      v85 = v44;
      v45 = SafeArrayGetElement(v78, rgIndices, &v92);
      if ( v45 < 0 )
        ThrowHR(v45);
      v46 = SafeArrayGetElement(psa, rgIndices, &p_bstrString);
      if ( v46 < 0 )
        ThrowHR(v46);
      v47 = (int)v92;
      if ( (_DWORD)v92 == 1 )
      {
        if ( (_DWORD)p_bstrString == 3 )
          v47 = 2;
      }
      else if ( !(_DWORD)v92 )
      {
        v47 = 2;
      }
      v48 = (SString *)operator new(0x18u);
      v49 = v48;
      v100 = v48;
      if ( v48 )
      {
        v50 = pv;
        v101 = v48;
        *(_DWORD *)v48 = 2;
        *((_DWORD *)v48 + 1) = 2;
        *((_DWORD *)v48 + 2) = 16;
        *((_QWORD *)v48 + 2) = &SString::s_EmptyBuffer;
        if ( !v50 )
          ThrowHR(-2147024736);
        SString::Set(v48, v50);
      }
      else
      {
        v49 = 0;
      }
      v93 = v49;
      v94 = v49 != 0;
      v51 = 0;
      v52 = v83;
      if ( (*((_DWORD *)v83 + 8) & 0xFFFFFFF8) != 0 )
      {
        while ( !(unsigned int)SString::EqualsCaseInsensitive(
                                 v93,
                                 *(const struct SString **)(*(_QWORD *)(*((_QWORD *)v52 + 6) + 8LL * v51) + 88LL)) )
        {
          v53 = *(_QWORD *)(*((_QWORD *)v83 + 6) + 8LL * v51);
          v54 = *(const struct SString **)(v53 + 104);
          if ( !v54 )
            v54 = *(const struct SString **)(v53 + 88);
          if ( (unsigned int)SString::EqualsCaseInsensitive(v93, v54) )
            break;
          ++v51;
          v52 = v83;
          if ( v51 >= *((_DWORD *)v83 + 8) >> 3 )
            goto LABEL_112;
        }
        v52 = v83;
        LogicalImage = *(struct LogicalImage **)(*((_QWORD *)v83 + 6) + 8LL * v51);
      }
      v55 = 0;
      if ( !LogicalImage )
      {
LABEL_112:
        LogicalImage = (struct LogicalImage *)Configuration::CreateLogicalImage(v52, (__int64 *)&v93);
        v55 = 1;
      }
      if ( (_DWORD)v92 )
      {
        if ( (_DWORD)v92 == 1 )
        {
          v56 = (_DWORD)p_bstrString != 3;
          if ( (_DWORD)p_bstrString == 3 )
            goto LABEL_117;
          goto LABEL_130;
        }
        if ( (_DWORD)v92 != 2 )
          goto LABEL_116;
      }
      if ( (_DWORD)p_bstrString != 1 && ((_DWORD)p_bstrString || ((*((_DWORD *)v83 + 6) >> 5) & 1) != 0) )
      {
LABEL_116:
        v56 = 0;
        goto LABEL_117;
      }
      v56 = 1;
LABEL_130:
      if ( *((_DWORD *)LogicalImage + 4) == 1 )
      {
        Node::SetStatus(LogicalImage, 2);
LABEL_118:
        if ( v56 )
        {
          CCorSvcMgr::ExpandLogicalImage(this, LogicalImage, v99);
          if ( *((_QWORD *)this + 39) && !*((_QWORD *)LogicalImage + 9) )
          {
            v57 = (SString *)*((_QWORD *)LogicalImage + 13);
            if ( v57 || (v57 = (SString *)*((_QWORD *)LogicalImage + 11)) != 0 )
            {
              SString::ConvertToUnicode(v57);
              v58 = (const unsigned __int16 *)*((_QWORD *)v57 + 2);
            }
            else
            {
              v58 = 0;
            }
            if ( IsFrameworkAssemblyName(v58) )
            {
              v107 = 512;
              lpMem = v109;
              v106 = 2;
              v109[0] = 0;
              ManagedImage = (Image *)LogicalImage::GetManagedImage(a2);
              Path = Image::GetPath(ManagedImage);
              v66 = (Image *)LogicalImage::GetManagedImage(LogicalImage);
              v67 = Image::GetPath(v66);
              SString::Printf(
                (SString *)&v106,
                L"Hardbound dependency \"%s\" not yet compiled, cannot compile \"%s\".\n",
                v67,
                Path);
              v68 = Image::GetPath((Image *)&v106);
              CCorSvcMgr::Log(this, v68, 1);
              ThrowHR(-2146230519);
            }
          }
        }
        else
        {
          Node::SetStatus(LogicalImage, 1);
        }
        goto LABEL_136;
      }
LABEL_117:
      if ( v55 )
        goto LABEL_118;
LABEL_136:
      if ( v47 == 1 )
      {
        v59 = (struct LogicalImage *)((char *)a2 + 48);
        v60 = L"Hard";
      }
      else
      {
        v59 = (struct LogicalImage *)((char *)a2 + 24);
        v60 = L"Soft";
      }
      LogicalImage::CreateDependency((int)a2, (__int64)LogicalImage, v59, (int)v60);
      Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>::~Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>((__int64 *)&v93);
      LogicalImage = 0;
      if ( v85 )
      {
        SysFreeString(pv);
        v85 = 0;
      }
      v41 = (_DWORD)p_psa + 1;
      LODWORD(p_psa) = v41;
      if ( v41 > plUbound )
      {
        v10 = v89;
        break;
      }
    }
  }
  Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>::~Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>((__int64 *)&v90);
  *v10 = v81;
  if ( v70 )
  {
    v61 = (SString *)operator new(0x18u);
    v62 = (__int64)v61;
    v101 = v61;
    if ( v61 )
    {
      v63 = v70;
      v100 = v61;
      *(_DWORD *)v61 = 2;
      *((_DWORD *)v61 + 1) = 2;
      *((_DWORD *)v61 + 2) = 16;
      *((_QWORD *)v61 + 2) = &SString::s_EmptyBuffer;
      if ( !v63 )
        ThrowHR(-2147024736);
      SString::Set(v61, v63);
    }
    else
    {
      v62 = 0;
    }
    v90 = (SAFEARRAY **)v62;
    v91 = v62 != 0;
    LogicalImage::SetNativeImage(a2, &v90);
    Node::SetStatus(a2, 5);
    Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>::~Wrapper<Image *,&void DoNothing<Image *>(Image *),&void Delete<Image>(Image *),0,&int CompareDefault<Image *>(Image *,Image *),2,1>((__int64 *)&v90);
  }
  else
  {
    Node::SetStatus(a2, 3);
  }
  if ( v75 )
  {
    SysFreeString(bstrString);
    v75 = 0;
  }
  if ( v71 )
  {
    SysFreeString(v70);
    v71 = 0;
  }
  if ( v77 )
  {
    SafeArrayDestroy(psa);
    v77 = 0;
  }
  if ( v79 )
  {
    SafeArrayDestroy(v78);
    v79 = 0;
  }
  if ( v73 )
  {
    SafeArrayDestroy(v72);
    v73 = 0;
  }
  if ( v82 )
  {
    SysFreeString(v95);
    v96 = 0;
  }
}

```

## disassembly

```asm
0x18002587c  mov     [rsp-8+arg_18], rbx
0x180025881  push    rbp
0x180025882  push    rsi
0x180025883  push    rdi
0x180025884  push    r12
0x180025886  push    r13
0x180025888  push    r14
0x18002588a  push    r15
0x18002588c  lea     rbp, [rsp-6D0h]
0x180025894  sub     rsp, 7D0h
0x18002589b  mov     rax, cs:__security_cookie
0x1800258a2  xor     rax, rsp
0x1800258a5  mov     [rbp+700h+var_40], rax
0x1800258ac  mov     r14, r8
0x1800258af  mov     [rbp+700h+var_6C8], r8
0x1800258b3  mov     rsi, rdx
0x1800258b6  mov     r15, rcx
0x1800258b9  xor     r12d, r12d
0x1800258bc  mov     [rsp+800h+var_7B0], r12d
0x1800258c1  mov     rdi, [rdx+8]
0x1800258c5  mov     [rbp+700h+var_748], rdi
0x1800258c9  mov     rbx, [rdx+58h]
0x1800258cd  test    rbx, rbx
0x1800258d0  jnz     short loc_1800258D7
0x1800258d2  mov     ecx, r12d
0x1800258d5  jmp     short loc_1800258E3
0x1800258d7  mov     rcx, rbx; this
0x1800258da  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x1800258df  mov     rcx, [rbx+10h]; psz
0x1800258e3  call    cs:__imp_SysAllocString
0x1800258e9  mov     rbx, rax
0x1800258ec  mov     [rbp+700h+var_6E8], rax
0x1800258f0  mov     [rbp+700h+var_6E0], r12d
0x1800258f4  mov     eax, r12d
0x1800258f7  mov     r13d, 1
0x1800258fd  test    rbx, rbx
0x180025900  cmovnz  eax, r13d
0x180025904  mov     [rbp+700h+var_750], eax
0x180025907  mov     [rbp+700h+var_6E0], eax
0x18002590a  mov     [rsp+800h+var_798], r12
0x18002590f  mov     [rsp+800h+var_790], r12d
0x180025914  mov     [rbp+700h+var_768], r12
0x180025918  mov     [rbp+700h+var_760], r12d
0x18002591c  mov     [rbp+700h+psa], r12
0x180025920  mov     [rbp+700h+var_770], r12d
0x180025924  mov     [rsp+800h+var_7A8], r12
0x180025929  mov     [rsp+800h+var_7A0], r12d
0x18002592e  mov     [rsp+800h+bstrString], r12
0x180025933  mov     [rbp+700h+var_780], r12d
0x180025937  lea     r12, [rdi+284h]
0x18002593e  mov     [rbp+700h+var_718], r12
0x180025942  mov     eax, [r12]
0x180025946  mov     [rbp+700h+var_754], eax
0x180025949  mov     [rbp+700h+var_6A8], eax
0x18002594c  mov     [rbp+700h+var_6B0], r12
0x180025950  xor     edi, edi
0x180025952  mov     [r12], edi
0x180025956  lea     rax, [rbp+700h+psa]
0x18002595a  mov     [rbp+700h+var_720], rax
0x18002595e  cmp     [rbp+700h+var_770], edi
0x180025961  jz      short loc_180025970
0x180025963  mov     rcx, [rbp+700h+psa]; psa
0x180025967  call    cs:__imp_SafeArrayDestroy
0x18002596d  mov     [rbp+700h+var_770], edi
0x180025970  mov     [rbp+700h+psa], rdi
0x180025974  mov     [rsp+800h+var_7B0], r13d
0x180025979  lea     rax, [rbp+700h+var_768]
0x18002597d  mov     [rbp+700h+var_700], rax
0x180025981  cmp     [rbp+700h+var_760], edi
0x180025984  jz      short loc_180025993
0x180025986  mov     rcx, [rbp+700h+var_768]; psa
0x18002598a  call    cs:__imp_SafeArrayDestroy
0x180025990  mov     [rbp+700h+var_760], edi
0x180025993  mov     [rbp+700h+var_768], rdi
0x180025997  mov     [rsp+800h+var_7B0], 3
0x18002599f  lea     rax, [rsp+800h+bstrString]
0x1800259a4  mov     [rbp+700h+var_728], rax
0x1800259a8  cmp     [rbp+700h+var_780], edi
0x1800259ab  jz      short loc_1800259BB
0x1800259ad  mov     rcx, [rsp+800h+bstrString]; bstrString
0x1800259b2  call    cs:__imp_SysFreeString
0x1800259b8  mov     [rbp+700h+var_780], edi
0x1800259bb  mov     [rsp+800h+bstrString], rdi
0x1800259c0  mov     [rsp+800h+var_7B0], 7
0x1800259c8  lea     rax, [rsp+800h+var_7A8]
0x1800259cd  mov     qword ptr [rbp+700h+rgIndices], rax
0x1800259d1  cmp     [rsp+800h+var_7A0], edi
0x1800259d5  jz      short loc_1800259E6
0x1800259d7  mov     rcx, [rsp+800h+var_7A8]; bstrString
0x1800259dc  call    cs:__imp_SysFreeString
0x1800259e2  mov     [rsp+800h+var_7A0], edi
0x1800259e6  mov     [rsp+800h+var_7A8], rdi
0x1800259eb  mov     [rsp+800h+var_7B0], 0Fh
0x1800259f3  lea     rax, [rsp+800h+var_798]
0x1800259f8  mov     [rbp+700h+var_6D8], rax
0x1800259fc  cmp     [rsp+800h+var_790], edi
0x180025a00  jz      short loc_180025A11
0x180025a02  mov     rcx, [rsp+800h+var_798]; psa
0x180025a07  call    cs:__imp_SafeArrayDestroy
0x180025a0d  mov     [rsp+800h+var_790], edi
0x180025a11  mov     [rsp+800h+var_798], rdi
0x180025a16  mov     r13d, 1Fh
0x180025a1c  mov     [rsp+800h+var_7B0], r13d
0x180025a21  mov     rax, [r14]
0x180025a24  lea     rcx, [rbp+700h+psa]
0x180025a28  mov     [rsp+800h+var_7C8], rcx
0x180025a2d  lea     rcx, [rbp+700h+var_768]
0x180025a31  mov     [rsp+800h+var_7D0], rcx
0x180025a36  lea     rcx, [rsp+800h+bstrString]
0x180025a3b  mov     [rsp+800h+var_7D8], rcx
0x180025a40  lea     rcx, [rsp+800h+var_7A8]
0x180025a45  mov     [rsp+800h+var_7E0], rcx; unsigned __int16 *
0x180025a4a  lea     r9, [rbp+700h+var_6D0]
0x180025a4e  lea     r8, [rsp+800h+var_798]
0x180025a53  mov     rdx, rbx
0x180025a56  mov     rcx, r14
0x180025a59  mov     rax, [rax+18h]
0x180025a5d  call    cs:__guard_dispatch_icall_fptr
0x180025a63  mov     ebx, eax
0x180025a65  and     r13d, 0FFFFFFEFh
0x180025a69  mov     [rsp+800h+var_7B0], r13d
0x180025a6e  mov     ecx, [rsp+800h+var_790]
0x180025a72  cmp     [rsp+800h+var_798], rdi
0x180025a77  mov     edx, 1
0x180025a7c  cmovnz  ecx, edx
0x180025a7f  mov     [rsp+800h+var_790], ecx
0x180025a83  and     r13d, 0FFFFFFF7h
0x180025a87  mov     [rsp+800h+var_7B0], r13d
0x180025a8c  mov     eax, [rsp+800h+var_7A0]
0x180025a90  cmp     [rsp+800h+var_7A8], rdi
0x180025a95  cmovnz  eax, edx
0x180025a98  mov     [rsp+800h+var_7A0], eax
0x180025a9c  and     r13d, 0FFFFFFFBh
0x180025aa0  mov     [rsp+800h+var_7B0], r13d
0x180025aa5  mov     eax, [rbp+700h+var_780]
0x180025aa8  cmp     [rsp+800h+bstrString], rdi
0x180025aad  cmovnz  eax, edx
0x180025ab0  mov     [rbp+700h+var_780], eax
0x180025ab3  and     r13d, 0FFFFFFFDh
0x180025ab7  mov     [rsp+800h+var_7B0], r13d
0x180025abc  mov     eax, [rbp+700h+var_760]
0x180025abf  cmp     [rbp+700h+var_768], rdi
0x180025ac3  cmovnz  eax, edx
0x180025ac6  mov     [rbp+700h+var_760], eax
0x180025ac9  and     r13d, 0FFFFFFFEh
0x180025acd  mov     [rsp+800h+var_7B0], r13d
0x180025ad2  mov     eax, [rbp+700h+var_770]
0x180025ad5  cmp     [rbp+700h+psa], rdi
0x180025ad9  cmovnz  eax, edx
0x180025adc  mov     [rbp+700h+var_770], eax
0x180025adf  test    ebx, ebx
0x180025ae1  jns     loc_180025E6E
0x180025ae7  mov     rcx, r15; this
0x180025aea  call    ?IsInterruptRequested@CCorSvcMgr@@AEAAHXZ; CCorSvcMgr::IsInterruptRequested(void)
0x180025aef  test    eax, eax
0x180025af1  jnz     loc_1800263E5
0x180025af7  mov     [rbp+700h+var_260], rdi
0x180025afe  mov     [rbp+700h+var_260+4], 200h
0x180025b09  mov     [rbp+700h+var_250], rdi
0x180025b10  lea     rax, [rbp+700h+var_248]
0x180025b17  mov     [rbp+700h+var_250], rax
0x180025b1e  mov     r14d, 2
0x180025b24  mov     dword ptr [rbp+700h+var_260], r14d
0x180025b2b  mov     rax, [rbp+700h+var_250]
0x180025b32  mov     [rax], di
0x180025b35  cmp     ebx, 8007000Bh
0x180025b3b  jz      loc_180025CED
0x180025b41  cmp     ebx, 80131D02h
0x180025b47  jz      loc_180025CB8
0x180025b4d  cmp     ebx, 80131D0Bh
0x180025b53  jz      loc_180025C92
0x180025b59  mov     qword ptr [rbp+700h+var_480], rdi
0x180025b60  mov     qword ptr [rbp+700h+var_480+4], 200h
0x180025b6b  mov     [rbp+700h+lpMem], rdi
0x180025b72  lea     rax, [rbp+700h+var_468]
0x180025b79  mov     [rbp+700h+lpMem], rax
0x180025b80  mov     dword ptr [rbp+700h+var_480], r14d
0x180025b87  mov     rax, [rbp+700h+lpMem]
0x180025b8e  mov     [rax], di
0x180025b91  lea     rdx, [rbp+700h+var_480]; this
0x180025b98  mov     ecx, ebx; unsigned int
0x180025b9a  call    ?GetHRMsg@@YAXJAEAVSString@@H@Z; GetHRMsg(long,SString &,int)
0x180025b9f  lea     rcx, [rbp+700h+var_480]; this
0x180025ba6  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180025bab  mov     r12, [rbp+700h+lpMem]
0x180025bb2  mov     rdi, [rsi+58h]
0x180025bb6  xor     r13d, r13d
0x180025bb9  test    rdi, rdi
0x180025bbc  jnz     short loc_180025BC3
0x180025bbe  mov     r8d, r13d
0x180025bc1  jmp     short loc_180025BCF
0x180025bc3  mov     rcx, rdi; this
0x180025bc6  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180025bcb  mov     r8, [rdi+10h]
0x180025bcf  mov     r9, r12
0x180025bd2  lea     rdx, aFailedToCompil_0; "Failed to compile %s because of the fol"...
0x180025bd9  lea     rcx, [rbp+700h+var_260]; this
0x180025be0  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180025be5  nop
0x180025be6  test    [rbp+700h+var_478], 8
0x180025bed  jz      short loc_180025C22
0x180025bef  mov     rdi, [rbp+700h+lpMem]
0x180025bf6  test    rdi, rdi
0x180025bf9  jz      short loc_180025C22
0x180025bfb  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180025c02  test    rax, rax
0x180025c05  jnz     short loc_180025C14
0x180025c07  call    cs:__imp_GetProcessHeap
0x180025c0d  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x180025c14  mov     r8, rdi; lpMem
0x180025c17  xor     edx, edx; dwFlags
0x180025c19  mov     rcx, rax; hHeap
0x180025c1c  call    cs:__imp_HeapFree
0x180025c22  mov     r12, [rbp+700h+var_718]
0x180025c26  lea     rdx, [rbp+700h+var_260]
0x180025c2d  lea     rcx, [rbp+700h+var_6A0]
0x180025c31  call    ??0?$InlineSString@$0CAA@@@QEAA@AEBV0@@Z; InlineSString<512>::InlineSString<512>(InlineSString<512> const &)
0x180025c36  nop
0x180025c37  lea     rdx, asc_18005AE70; ".\n"
0x180025c3e  lea     rcx, [rbp+700h+var_6A0]; this
0x180025c42  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x180025c47  lea     rcx, [rbp+700h+var_6A0]; this
0x180025c4b  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180025c50  lea     rcx, [r15+0D0h]
0x180025c57  mov     r8d, r14d
0x180025c5a  mov     rdx, [rbp+700h+var_690]
0x180025c5e  call    ?Log@Logger@@QEAAXPEBGW4CorSvcLogLevel@@@Z; Logger::Log(ushort const *,CorSvcLogLevel)
0x180025c63  cmp     cs:?g_bProcessNGENService@NGENService@@3_NA, r13b; bool NGENService::g_bProcessNGENService
0x180025c6a  jz      loc_180025D32
0x180025c70  lea     rcx, [rbp+700h+var_6A0]; this
0x180025c74  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180025c79  mov     r14, [rbp+700h+var_690]
0x180025c7d  mov     rdi, [rsi+58h]
0x180025c81  test    rdi, rdi
0x180025c84  jnz     loc_180025D13
0x180025c8a  mov     rcx, r13
0x180025c8d  jmp     loc_180025D1F
0x180025c92  mov     rdi, [rsi+58h]
0x180025c96  xor     r13d, r13d
0x180025c99  test    rdi, rdi
0x180025c9c  jnz     short loc_180025CA3
0x180025c9e  mov     r8d, r13d
0x180025ca1  jmp     short loc_180025CAF
0x180025ca3  mov     rcx, rdi; this
0x180025ca6  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180025cab  mov     r8, [rdi+10h]
0x180025caf  lea     rdx, aFailedToCompil_1; "Failed to compile %s because this image"...
0x180025cb6  jmp     short loc_180025CDC
0x180025cb8  mov     rdi, [rsi+58h]
0x180025cbc  xor     r13d, r13d
0x180025cbf  test    rdi, rdi
0x180025cc2  jnz     short loc_180025CC9
0x180025cc4  mov     r8d, r13d
0x180025cc7  jmp     short loc_180025CD5
0x180025cc9  mov     rcx, rdi; this
0x180025ccc  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180025cd1  mov     r8, [rdi+10h]
0x180025cd5  lea     rdx, aFailedToCompil_3; "Failed to compile %s because this image"...
0x180025cdc  lea     rcx, [rbp+700h+var_260]; this
0x180025ce3  call    ?Printf@SString@@QEAAXPEBGZZ; SString::Printf(ushort const *,...)
0x180025ce8  jmp     loc_180025C26
0x180025ced  mov     rdi, [rsi+58h]
0x180025cf1  xor     r13d, r13d
0x180025cf4  test    rdi, rdi
0x180025cf7  jnz     short loc_180025CFE
0x180025cf9  mov     r8d, r13d
0x180025cfc  jmp     short loc_180025D0A
0x180025cfe  mov     rcx, rdi; this
0x180025d01  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180025d06  mov     r8, [rdi+10h]
0x180025d0a  lea     rdx, aFailedToCompil_2; "Failed to compile %s because this image"...
0x180025d11  jmp     short loc_180025CDC
0x180025d13  mov     rcx, rdi; this
0x180025d16  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x180025d1b  mov     rcx, [rdi+10h]; this
0x180025d1f  mov     r9, r14; unsigned int
0x180025d22  mov     edx, 1; unsigned __int16 *
0x180025d27  mov     r8d, 44Dh; unsigned __int16
0x180025d2d  call    ?EventLog@NGENService@@YAXPEBGGK0ZZ; NGENService::EventLog(ushort const *,ushort,ulong,ushort const *,...)
0x180025d32  mov     edi, [rbp+700h+var_754]
0x180025d35  mov     [r12], edi
0x180025d39  mov     edx, 4
0x180025d3e  mov     rcx, rsi
0x180025d41  call    ?SetStatus@Node@@QEAAXW4EntryStatus@@@Z; Node::SetStatus(EntryStatus)
0x180025d46  mov     eax, [r15+4F0h]
0x180025d4d  test    eax, eax
0x180025d4f  js      short loc_180025D5A
0x180025d51  mov     [r15+4F0h], ebx
0x180025d58  mov     eax, ebx
0x180025d5a  cmp     eax, 80004004h
0x180025d5f  jnz     short loc_180025D68
0x180025d61  mov     [r15+4F0h], ebx
0x180025d68  mov     eax, 80070070h
0x180025d6d  cmp     ebx, eax
0x180025d6f  jnz     short loc_180025D78
0x180025d71  mov     [r15+4F0h], eax
0x180025d78  cmp     [r15+4F4h], r13d
0x180025d7f  jz      loc_1800263F0
0x180025d85  cmp     [r15+504h], r13d
0x180025d8c  jl      short loc_180025D95
  ... truncated ...
```
