# CStdPropSetProperties2::Refresh(void *,short,bool)

- ea: `0x18000d530`
- end: `0x18000df49`
- name: `?Refresh@CStdPropSetProperties2@@UEAAJPEAXF_N@Z`
- size: `2585`
- prototype: `__int64 __fastcall(CStdPropSetProperties2 *__hidden this, void *, __int16, bool)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000c670`
- `0x18000c700`
- `0x18000cd80`
- `0x18000d0e0`
- `0x18000d530`
- `0x18000f760`
- `0x18000f7c0`
- `0x180020e20`
- `0x180020fc0`
- `0x180027790`
- `0x180042a04`
- `0x180047610`
- `0x1800530f0`
- `0x180053130`
- `0x180054098`
- `0x1800657d0`
- `0x1800c8f34`
- `0x1800c930c`
- `0x1800cdaea`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000d620`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000ddc8`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000d620`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000ddc8`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000de33`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000dea3`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000de33`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000dea3`
- `MSDART!MpHeapAlloc` at `0x18000d699`
- `MSDART!MpHeapAlloc` at `0x18000d798`
- `MSDART!MpHeapAlloc` at `0x18000d820`
- `MSDART!MpHeapAlloc` at `0x18000d861`
- `MSDART!MpHeapAlloc` at `0x18000d699`
- `MSDART!MpHeapAlloc` at `0x18000d798`
- `MSDART!MpHeapAlloc` at `0x18000d820`
- `MSDART!MpHeapAlloc` at `0x18000d861`
- `KERNEL32!TlsSetValue` at `0x18000d5ca`
- `KERNEL32!TlsSetValue` at `0x18000df18`
- `KERNEL32!TlsSetValue` at `0x18000d5ca`
- `KERNEL32!TlsSetValue` at `0x18000df18`
- `KERNEL32!TlsGetValue` at `0x18000d586`
- `KERNEL32!TlsGetValue` at `0x18000d586`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000d9f1`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000d9f1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d5ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da1f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc00`
- `OLEAUT32!__imp_SysFreeString` at `0x18000debc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d5ff`
- `OLEAUT32!__imp_SysFreeString` at `0x18000da1f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc00`
- `OLEAUT32!__imp_SysFreeString` at `0x18000debc`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d9e0`
- `OLEAUT32!__imp_SysStringLen` at `0x18000d9e0`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000dee2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000dee2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CStdPropSetProperties2::Refresh(
        CStdPropSetProperties2 *this,
        void *a2,
        unsigned __int16 a3,
        char a4)
{
  _QWORD *v7; // rbx
  char *v8; // rdx
  _DWORD *Value; // rax
  char v10; // si
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rax
  void *v16; // rdi
  unsigned int v17; // eax
  __int64 v18; // rax
  __int64 v19; // r12
  int v20; // r13d
  size_t v21; // r15
  void *v22; // rax
  void *v23; // rax
  CPropSetRefInfo *v24; // rcx
  CCollectionList **v25; // r13
  int v26; // eax
  OLECHAR *v27; // r15
  UINT v28; // eax
  __int64 v29; // rcx
  unsigned __int16 *v30; // rdx
  char v31; // r15
  void *v32; // rcx
  _QWORD *v33; // rdx
  __int64 v34; // r9
  __int64 v35; // rdx
  int v36; // eax
  int v37; // r15d
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r15
  __int64 v41; // r13
  __int64 v42; // r8
  unsigned int v43; // ebx
  _DWORD *v45; // rax
  IErrorInfo *v46; // rdx
  void *v47; // [rsp+30h] [rbp-49h] BYREF
  unsigned __int64 v48; // [rsp+38h] [rbp-41h]
  BSTR pbstr; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int64 v50; // [rsp+48h] [rbp-31h]
  BSTR bstrString; // [rsp+50h] [rbp-29h] BYREF
  char v52; // [rsp+58h] [rbp-21h]
  _DWORD *TlsValue; // [rsp+60h] [rbp-19h] BYREF
  int v54; // [rsp+68h] [rbp-11h]
  __int64 v55; // [rsp+70h] [rbp-9h]
  int v56; // [rsp+78h] [rbp-1h]
  __int16 v57; // [rsp+7Ch] [rbp+3h]
  char v58; // [rsp+7Eh] [rbp+5h]
  char *v59; // [rsp+80h] [rbp+7h]
  int v60; // [rsp+88h] [rbp+Fh]
  int v61; // [rsp+8Ch] [rbp+13h]
  __int64 v62; // [rsp+E0h] [rbp+67h] BYREF
  void *v63; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned __int16 v64; // [rsp+F0h] [rbp+77h]
  char v65; // [rsp+F8h] [rbp+7Fh]

  v65 = a4;
  v64 = a3;
  v63 = a2;
  v7 = (_QWORD *)((char *)this + 16);
  v8 = (char *)this + 16;
  if ( !this )
    v8 = 0;
  v59 = v8;
  v61 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v60 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v54 = 1;
    v55 = 0;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  pbstr = 0;
  bstrString = 0;
  v10 = 6;
  v52 = 6;
  v47 = 0;
  if ( !a4 && !*((_DWORD *)this + 25) )
  {
    SysFreeString(0);
    CContext::~CContext((CContext *)&TlsValue);
    return 0;
  }
  CReaderWriterLock3AR::WriteLock((CStdPropSetProperties2 *)((char *)this + 88));
  v12 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v7 + 280LL))(v7, a3);
  v60 = v12;
  if ( v12 < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_112;
    v13 = 1119;
    v14 = 1145865;
LABEL_111:
    bidTraceW(off_18012A1D8[0], v14, L"<CStdPropSetProperties2::Refresh|ADO|ERR>  line %d\n", v13);
    goto LABEL_112;
  }
  if ( v12 == 1 )
  {
    v60 = 0;
    if ( !*((_QWORD *)this + 10) )
    {
      v15 = MpHeapAlloc(g_hHeapHandle, 10485760, 48);
      v16 = (void *)v15;
      v62 = v15;
      if ( v15 )
      {
        *(_DWORD *)v15 = 0;
        *(_QWORD *)(v15 + 8) = 0;
        *(_DWORD *)(v15 + 16) = 0;
        *(_DWORD *)(v15 + 24) = 0;
        *(_QWORD *)(v15 + 32) = 0;
        *(_DWORD *)(v15 + 40) = 0;
        *(_BYTE *)(v15 + 44) = 0;
      }
      else
      {
        v16 = 0;
      }
      if ( (unsigned int)CContext::MemFailed((CContext *)&TlsValue, v16) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_112;
        v13 = 1129;
        v14 = 1156105;
        goto LABEL_111;
      }
      v17 = (*(__int64 (__fastcall **)(_QWORD *))(*v7 + 360LL))(v7);
      LODWORD(v62) = CCollectionList::Reserve((CCollectionList *)v16, v17);
      if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v62) )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceW(off_18012A1D8[0], 1157129, L"<CStdPropSetProperties2::Refresh|ADO|ERR>  line %d\n", 1130);
LABEL_38:
        CStdCollection::DestroyList((CStdCollection *)v7, (struct CCollectionList *)v16);
        goto LABEL_112;
      }
      *((_QWORD *)this + 10) = v16;
    }
    if ( *((_BYTE *)this + 112) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_112;
      v13 = 1134;
      v14 = 1161225;
      goto LABEL_111;
    }
  }
  v18 = MpHeapAlloc(g_hHeapHandle, 10485760, 48);
  v16 = (void *)v18;
  v62 = v18;
  if ( v18 )
  {
    *(_DWORD *)v18 = 0;
    *(_QWORD *)(v18 + 8) = 0;
    *(_DWORD *)(v18 + 16) = 0;
    *(_DWORD *)(v18 + 24) = 0;
    *(_QWORD *)(v18 + 32) = 0;
    *(_DWORD *)(v18 + 40) = 0;
    *(_BYTE *)(v18 + 44) = 0;
    v19 = v18;
  }
  else
  {
    v19 = 0;
    v16 = 0;
    LODWORD(v62) = -2147024882;
    if ( (unsigned int)CContext::FailedPushWarning((CContext *)&TlsValue, (const int *)&v62) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_112;
      v13 = 1138;
      v14 = 1165321;
      goto LABEL_111;
    }
  }
  v20 = (*(__int64 (__fastcall **)(_QWORD *))(*v7 + 360LL))(v7);
  v21 = (unsigned int)(8 * v20);
  v22 = (void *)MpHeapAlloc(g_hHeapHandle, 10485760, v21);
  *(_QWORD *)(v19 + 8) = v22;
  if ( !v22 )
  {
    if ( (bidGblFlags & 2) == 0 )
    {
LABEL_36:
      v60 = -2147024882;
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) != 0 )
        bidTraceW(off_18012A1D8[0], 1166345, L"<CStdPropSetProperties2::Refresh|ADO|ERR>  line %d\n", 1139);
      goto LABEL_38;
    }
LABEL_35:
    bidTraceW(
      off_18012A218[0],
      434185,
      L"<CDynamicArray::Reserve|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      2147942414LL,
      424);
    goto LABEL_36;
  }
  memset_0(v22, 0, v21);
  *(_DWORD *)v19 = v20;
  v23 = (void *)MpHeapAlloc(g_hHeapHandle, 10485760, v21);
  *(_QWORD *)(v19 + 32) = v23;
  if ( !v23 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_36;
    goto LABEL_35;
  }
  memset_0(v23, 0, v21);
  *(_DWORD *)(v19 + 24) = v20;
  v60 = 0;
  v24 = (CPropSetRefInfo *)*((_QWORD *)this + 13);
  if ( v24 )
  {
    CPropSetRefInfo::`vector deleting destructor'(v24, 1u);
    *((_QWORD *)this + 13) = 0;
  }
  v60 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, void **))(*v7 + 288LL))(v7, v64, &v63);
  if ( v60 < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
      bidTraceW(off_18012A1D8[0], 1174537, L"<CStdPropSetProperties2::Refresh|ADO|ERR>  line %d\n", 1147);
    goto LABEL_38;
  }
  v48 = 0;
  v50 = (*(unsigned int (__fastcall **)(_QWORD *))(*v7 + 248LL))(v7);
  v25 = (CCollectionList **)((char *)this + 80);
  v26 = v60;
  while ( v26 != 1 )
  {
    v47 = 0;
    v60 = (*(__int64 (__fastcall **)(_QWORD *, void *, BSTR *))(*v7 + 296LL))(v7, v63, &pbstr);
    if ( v60 < 0 )
    {
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) != 0 )
        bidTraceW(off_18012A1D8[0], 1182729, L"<CStdPropSetProperties2::Refresh|ADO|ERR>  line %d\n", 1155);
      goto LABEL_82;
    }
    v27 = pbstr;
    if ( (v10 & 1) != 0 && pbstr && (v28 = SysStringLen(pbstr), (v27 = SysAllocStringLen(v27, v28)) == 0) )
    {
      v10 &= ~4u;
      v52 = v10;
    }
    else
    {
      v10 |= 4u;
      v52 = v10;
      if ( (v10 & 2) != 0 )
        SysFreeString(0);
      bstrString = v27;
    }
    v25 = (CCollectionList **)((char *)this + 80);
    v29 = *((_QWORD *)this + 10);
    if ( v29 )
    {
      v30 = 0;
      if ( (v10 & 4) != 0 )
        v30 = bstrString;
      LODWORD(v62) = CCollectionMap::LookUp((CCollectionMap *)(v29 + 24), v30, (unsigned __int64 *)&v47);
      if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v62) )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceW(off_18012A1D8[0], 1189897, L"<CStdPropSetProperties2::Refresh|ADO|ERR>  line %d\n", 1162);
        goto LABEL_82;
      }
    }
    if ( !v65 )
      goto LABEL_75;
    if ( !*v25 || (unsigned int)CContext::IsStatusFalse((CContext *)&TlsValue) )
    {
      v31 = 0;
    }
    else
    {
      v31 = 1;
      v32 = v47;
      if ( (unsigned __int64)v47 > v50 )
        goto LABEL_66;
    }
    LODWORD(v62) = (*(__int64 (__fastcall **)(_QWORD *, void *, _QWORD, void **))(*v7 + 304LL))(v7, v63, 0, &v47);
    if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v62) )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceW(off_18012A1D8[0], 1196041, L"<CStdPropSetProperties2::Refresh|ADO|ERR>  line %d\n", 1168);
      goto LABEL_82;
    }
    (*(void (__fastcall **)(_QWORD *, void *))(*v7 + 344LL))(v7, v47);
    v32 = v47;
LABEL_66:
    if ( v32 )
    {
      v33 = (_QWORD *)v7[4];
      if ( v7 == v33 )
        v33 = 0;
      (*(void (__fastcall **)(void *, _QWORD *))(*(_QWORD *)v32 + 152LL))(v32, v33);
      LODWORD(v62) = (*(__int64 (__fastcall **)(_QWORD *, void *, void *))(*v7 + 312LL))(v7, v63, v47);
      if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v62) )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceW(off_18012A1D8[0], 1208329, L"<CStdPropSetProperties2::Refresh|ADO|ERR>  line %d\n", 1180);
        goto LABEL_82;
      }
      if ( v31 )
      {
        LODWORD(v62) = CCollectionList::DeleteByKey(*v25, (const struct CSysString *)&bstrString);
        if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v62) )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            v34 = 1185;
            v35 = 1213449;
            goto LABEL_85;
          }
LABEL_86:
          v10 = v52;
LABEL_82:
          (*(void (__fastcall **)(_QWORD *, void *))(*v7 + 328LL))(v7, v63);
          *((_BYTE *)this + 112) = 0;
          goto LABEL_38;
        }
      }
      LODWORD(v62) = CCollectionList::AppendNew((CCollectionList *)v19, (const struct CSysString *)&bstrString, v47);
      if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v62) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v34 = 1188;
          v35 = 1216521;
          goto LABEL_85;
        }
        goto LABEL_86;
      }
      goto LABEL_78;
    }
LABEL_75:
    ++v48;
    LODWORD(v62) = *(_DWORD *)(v19 + 16);
    v36 = CCollectionArray::Insert((CCollectionArray *)v19, v62, v48);
    v37 = v36;
    if ( v36 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceW(
          off_18012A218[0],
          1380361,
          L"<CCollectionList::Insert|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)v36,
          1348);
      goto LABEL_96;
    }
    v38 = CCollectionMap::Insert((CCollectionMap *)(v19 + 24), (const struct CSysString *)&bstrString, v48);
    v37 = v38;
    if ( v38 < 0 )
    {
      CCollectionArray::Delete((CCollectionArray *)v19, v62);
      v10 = v52;
LABEL_96:
      v60 = v37;
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) != 0 )
        bidTraceW(off_18012A1D8[0], 1220617, L"<CStdPropSetProperties2::Refresh|ADO|ERR>  line %d\n", 1192);
      goto LABEL_82;
    }
    v60 = v38;
LABEL_78:
    SysFreeString(bstrString);
    bstrString = 0;
    v26 = (*(__int64 (__fastcall **)(_QWORD *, void *, _QWORD))(*v7 + 320LL))(v7, v63, v64);
    v60 = v26;
    if ( v26 < 0 )
    {
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) != 0 )
      {
        v34 = 1198;
        v35 = 1226761;
LABEL_85:
        bidTraceW(off_18012A1D8[0], v35, L"<CStdPropSetProperties2::Refresh|ADO|ERR>  line %d\n", v34);
      }
      goto LABEL_86;
    }
    v10 = v52;
  }
  v60 = 0;
  CReaderWriterLock3AR::WriteLock((CReaderWriterLock3AR *)(v7 + 9));
  v40 = v7[8];
  v7[8] = 0;
  if ( v40 )
  {
    LODWORD(v41) = *(_DWORD *)(v40 + 16);
    while ( (_DWORD)v41 )
    {
      v42 = (unsigned int)v41;
      v41 = (unsigned int)(v41 - 1);
      if ( (unsigned int)v41 < *(_DWORD *)(v40 + 16) )
      {
        v39 = *(_QWORD *)(*(_QWORD *)(v40 + 8) + 8 * v41);
        if ( v39 )
        {
          if ( v39 != v42 )
            (*(void (__fastcall **)(_QWORD *))(*v7 + 352LL))(v7);
        }
      }
    }
    CCollectionList::`scalar deleting destructor'((CCollectionList *)v40, v39);
    v25 = (CCollectionList **)((char *)this + 80);
  }
  CReaderWriterLock3AR::WriteUnlock((CReaderWriterLock3AR *)(v7 + 9));
  *v25 = (CCollectionList *)v19;
  (*(void (__fastcall **)(_QWORD *))(*v7 + 368LL))(v7);
  *((_BYTE *)this + 112) = v65;
  *((_QWORD *)this + 13) = v63;
LABEL_112:
  *((_DWORD *)this + 25) = v60 < 0;
  CReaderWriterLock3AR::WriteUnlock((CStdPropSetProperties2 *)((char *)this + 88));
  v43 = v60;
  if ( (v10 & 2) != 0 )
    SysFreeString(bstrString);
  if ( TlsValue[2]-- == 1 )
  {
    v45 = TlsValue;
    v46 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v46 )
    {
      SetErrorInfo(0, v46);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v45 = TlsValue;
    }
    if ( *((_BYTE *)v45 + 30) )
    {
      *((_QWORD *)v45 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v43;
}

```

## disassembly

```asm
0x18000d530  mov     [rsp-8+arg_18], r9b
0x18000d535  mov     [rsp-8+arg_10], r8w
0x18000d53b  mov     [rsp-8+arg_8], rdx
0x18000d540  push    rbp
0x18000d541  push    rbx
0x18000d542  push    rsi
0x18000d543  push    rdi
0x18000d544  push    r12
0x18000d546  push    r13
0x18000d548  push    r14
0x18000d54a  push    r15
0x18000d54c  lea     rbp, [rsp-1Fh]
0x18000d551  sub     rsp, 98h
0x18000d558  movzx   edi, r9b
0x18000d55c  movzx   r15d, r8w
0x18000d560  mov     r14, rcx
0x18000d563  lea     rbx, [rcx+10h]
0x18000d567  mov     rdx, rbx
0x18000d56a  xor     r13d, r13d
0x18000d56d  test    rcx, rcx
0x18000d570  cmovz   rdx, r13
0x18000d574  mov     [rbp+57h+var_50], rdx
0x18000d578  mov     [rbp+57h+var_44], r13d
0x18000d57c  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000d583  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000d586  call    cs:__imp_TlsGetValue
0x18000d58d  nop     dword ptr [rax+rax+00h]
0x18000d592  mov     [rbp+57h+TlsValue], rax
0x18000d596  mov     [rbp+57h+var_48], r13d
0x18000d59a  test    rax, rax
0x18000d59d  jz      short loc_18000D5A4
0x18000d59f  inc     dword ptr [rax+8]
0x18000d5a2  jmp     short loc_18000D5DE
0x18000d5a4  mov     [rbp+57h+var_68], 1
0x18000d5ab  mov     [rbp+57h+var_60], r13
0x18000d5af  mov     [rbp+57h+var_58], r13d
0x18000d5b3  mov     [rbp+57h+var_54], r13w
0x18000d5b8  mov     [rbp+57h+var_52], r13b
0x18000d5bc  lea     rdx, [rbp+57h+TlsValue]; lpTlsValue
0x18000d5c0  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000d5c7  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000d5ca  call    cs:__imp_TlsSetValue
0x18000d5d1  nop     dword ptr [rax+rax+00h]
0x18000d5d6  lea     rax, [rbp+57h+TlsValue]
0x18000d5da  mov     [rbp+57h+TlsValue], rax
0x18000d5de  mov     [rbp+57h+pbstr], r13
0x18000d5e2  mov     [rbp+57h+bstrString], r13
0x18000d5e6  mov     sil, 6
0x18000d5e9  mov     [rbp+57h+var_78], sil
0x18000d5ed  mov     [rbp+57h+var_A0], r13
0x18000d5f1  test    dil, dil
0x18000d5f4  jnz     short loc_18000D61C
0x18000d5f6  cmp     dword ptr [r14+64h], 0
0x18000d5fb  jnz     short loc_18000D61C
0x18000d5fd  xor     ecx, ecx; bstrString
0x18000d5ff  call    cs:__imp_SysFreeString
0x18000d606  nop     dword ptr [rax+rax+00h]
0x18000d60b  nop
0x18000d60c  lea     rcx, [rbp+57h+TlsValue]; this
0x18000d610  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x18000d615  xor     eax, eax
0x18000d617  jmp     loc_18000DF34
0x18000d61c  lea     rcx, [r14+58h]
0x18000d620  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x18000d627  nop     dword ptr [rax+rax+00h]
0x18000d62c  mov     rax, [rbx]
0x18000d62f  movzx   edx, r15w
0x18000d633  mov     rcx, rbx
0x18000d636  mov     rax, [rax+118h]
0x18000d63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d642  mov     [rbp+57h+var_48], eax
0x18000d645  test    eax, eax
0x18000d647  jns     short loc_18000D66F
0x18000d649  lea     rcx, [rbp+57h+TlsValue]; this
0x18000d64d  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000d652  test    byte ptr cs:_bidGblFlags, 2
0x18000d659  jz      loc_18000DE91
0x18000d65f  mov     r9d, 45Fh
0x18000d665  mov     edx, 117C09h
0x18000d66a  jmp     loc_18000DE7E
0x18000d66f  cmp     eax, 1
0x18000d672  jnz     loc_18000D786
0x18000d678  mov     [rbp+57h+var_48], r13d
0x18000d67c  cmp     qword ptr [r14+50h], 0
0x18000d681  jnz     loc_18000D762
0x18000d687  mov     edx, 0A00000h
0x18000d68c  mov     r8d, 30h ; '0'
0x18000d692  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000d699  call    cs:__imp_MpHeapAlloc
0x18000d6a0  nop     dword ptr [rax+rax+00h]
0x18000d6a5  mov     rdi, rax
0x18000d6a8  mov     [rbp+57h+arg_0], rax
0x18000d6ac  test    rax, rax
0x18000d6af  jz      short loc_18000D6CE
0x18000d6b1  mov     [rax], r13d
0x18000d6b4  mov     [rax+8], r13
0x18000d6b8  mov     [rax+10h], r13d
0x18000d6bc  mov     [rax+18h], r13d
0x18000d6c0  mov     [rax+20h], r13
0x18000d6c4  mov     [rax+28h], r13d
0x18000d6c8  mov     byte ptr [rax+2Ch], 0
0x18000d6cc  jmp     short loc_18000D6D1
0x18000d6ce  mov     rdi, r13
0x18000d6d1  mov     rdx, rdi; void *
0x18000d6d4  lea     rcx, [rbp+57h+TlsValue]; this
0x18000d6d8  call    ?MemFailed@CContext@@QEAAHPEAX@Z; CContext::MemFailed(void *)
0x18000d6dd  test    eax, eax
0x18000d6df  jz      short loc_18000D6FE
0x18000d6e1  test    byte ptr cs:_bidGblFlags, 2
0x18000d6e8  jz      loc_18000DE91
0x18000d6ee  mov     r9d, 469h
0x18000d6f4  mov     edx, 11A409h
0x18000d6f9  jmp     loc_18000DE7E
0x18000d6fe  mov     rax, [rbx]
0x18000d701  mov     rcx, rbx
0x18000d704  mov     rax, [rax+168h]
0x18000d70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d710  mov     edx, eax; unsigned int
0x18000d712  mov     rcx, rdi; this
0x18000d715  call    ?Reserve@CCollectionList@@QEAAJK@Z; CCollectionList::Reserve(ulong)
0x18000d71a  mov     dword ptr [rbp+57h+arg_0], eax
0x18000d71d  lea     rdx, [rbp+57h+arg_0]; int *
0x18000d721  lea     rcx, [rbp+57h+TlsValue]; this
0x18000d725  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18000d72a  test    eax, eax
0x18000d72c  jz      short loc_18000D75E
0x18000d72e  test    byte ptr cs:_bidGblFlags, 2
0x18000d735  jz      loc_18000D8E0
0x18000d73b  mov     r9d, 46Ah
0x18000d741  lea     r8, aCstdpropsetpro_5; "<CStdPropSetProperties2::Refresh|ADO|ER"...
0x18000d748  mov     edx, 11A809h
0x18000d74d  mov     rcx, cs:off_18012A1D8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000d754  call    _bidTraceW
0x18000d759  jmp     loc_18000D8E0
0x18000d75e  mov     [r14+50h], rdi
0x18000d762  cmp     byte ptr [r14+70h], 0
0x18000d767  jz      short loc_18000D786
0x18000d769  test    byte ptr cs:_bidGblFlags, 2
0x18000d770  jz      loc_18000DE91
0x18000d776  mov     r9d, 46Eh
0x18000d77c  mov     edx, 11B809h
0x18000d781  jmp     loc_18000DE7E
0x18000d786  mov     edx, 0A00000h
0x18000d78b  mov     r8d, 30h ; '0'
0x18000d791  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000d798  call    cs:__imp_MpHeapAlloc
0x18000d79f  nop     dword ptr [rax+rax+00h]
0x18000d7a4  mov     rdi, rax
0x18000d7a7  mov     [rbp+57h+arg_0], rax
0x18000d7ab  test    rax, rax
0x18000d7ae  jz      short loc_18000D7D0
0x18000d7b0  mov     [rax], r13d
0x18000d7b3  mov     [rax+8], r13
0x18000d7b7  mov     [rax+10h], r13d
0x18000d7bb  mov     [rax+18h], r13d
0x18000d7bf  mov     [rax+20h], r13
0x18000d7c3  mov     [rax+28h], r13d
0x18000d7c7  mov     byte ptr [rax+2Ch], 0
0x18000d7cb  mov     r12, rax
0x18000d7ce  jmp     short loc_18000D7F2
0x18000d7d0  mov     r12, r13
0x18000d7d3  mov     rdi, r13
0x18000d7d6  mov     dword ptr [rbp+57h+arg_0], 8007000Eh
0x18000d7dd  lea     rdx, [rbp+57h+arg_0]; int *
0x18000d7e1  lea     rcx, [rbp+57h+TlsValue]; this
0x18000d7e5  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x18000d7ea  test    eax, eax
0x18000d7ec  jnz     loc_18000DE6A
0x18000d7f2  mov     rax, [rbx]
0x18000d7f5  mov     rcx, rbx
0x18000d7f8  mov     rax, [rax+168h]
0x18000d7ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d804  mov     r13d, eax
0x18000d807  lea     ecx, ds:0[rax*8]
0x18000d80e  mov     r15d, ecx
0x18000d811  mov     r8d, ecx
0x18000d814  mov     edx, 0A00000h
0x18000d819  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000d820  call    cs:__imp_MpHeapAlloc
0x18000d827  nop     dword ptr [rax+rax+00h]
0x18000d82c  mov     [r12+8], rax
0x18000d831  test    rax, rax
0x18000d834  jnz     short loc_18000D841
0x18000d836  test    byte ptr cs:_bidGblFlags, 2
0x18000d83d  jnz     short loc_18000D880
0x18000d83f  jmp     short loc_18000D8A6
0x18000d841  mov     r8, r15; Size
0x18000d844  xor     edx, edx; Val
0x18000d846  mov     rcx, rax; void *
0x18000d849  call    memset_0
0x18000d84e  mov     [r12], r13d
0x18000d852  mov     r8, r15
0x18000d855  mov     edx, 0A00000h
0x18000d85a  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000d861  call    cs:__imp_MpHeapAlloc
0x18000d868  nop     dword ptr [rax+rax+00h]
0x18000d86d  mov     [r12+20h], rax
0x18000d872  test    rax, rax
0x18000d875  jnz     short loc_18000D8F0
0x18000d877  test    byte ptr cs:_bidGblFlags, 2
0x18000d87e  jz      short loc_18000D8A6
0x18000d880  mov     [rsp+0D0h+var_B0], 1A8h
0x18000d888  mov     r9d, 8007000Eh
0x18000d88e  lea     r8, aCdynamicarrayR; "<CDynamicArray::Reserve|ADO|ERR> 0x%08x"...
0x18000d895  mov     edx, 6A009h
0x18000d89a  mov     rcx, cs:off_18012A218; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000d8a1  call    _bidTraceW
0x18000d8a6  mov     [rbp+57h+var_48], 8007000Eh
0x18000d8ad  lea     rcx, [rbp+57h+TlsValue]; this
0x18000d8b1  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000d8b6  test    byte ptr cs:_bidGblFlags, 2
0x18000d8bd  jz      short loc_18000D8DD
0x18000d8bf  mov     r9d, 473h
0x18000d8c5  lea     r8, aCstdpropsetpro_5; "<CStdPropSetProperties2::Refresh|ADO|ER"...
0x18000d8cc  mov     edx, 11CC09h
0x18000d8d1  mov     rcx, cs:off_18012A1D8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000d8d8  call    _bidTraceW
0x18000d8dd  xor     r13d, r13d
0x18000d8e0  mov     rdx, rdi; struct CCollectionList *
0x18000d8e3  mov     rcx, rbx; this
0x18000d8e6  call    ?DestroyList@CStdCollection@@QEAAXPEAVCCollectionList@@@Z; CStdCollection::DestroyList(CCollectionList *)
0x18000d8eb  jmp     loc_18000DE91
0x18000d8f0  mov     r8, r15; Size
0x18000d8f3  xor     edx, edx; Val
0x18000d8f5  mov     rcx, rax; void *
0x18000d8f8  call    memset_0
0x18000d8fd  mov     [r12+18h], r13d
0x18000d902  xor     r13d, r13d
0x18000d905  mov     [rbp+57h+var_48], r13d
0x18000d909  mov     rcx, [r14+68h]; this
0x18000d90d  test    rcx, rcx
0x18000d910  jz      short loc_18000D920
0x18000d912  mov     edx, 1; unsigned int
0x18000d917  call    ??_ECPropSetRefInfo@@UEAAPEAXI@Z; CPropSetRefInfo::`vector deleting destructor'(uint)
0x18000d91c  mov     [r14+68h], r13
0x18000d920  mov     rax, [rbx]
0x18000d923  lea     r8, [rbp+57h+arg_8]
0x18000d927  movzx   edx, [rbp+57h+arg_10]
0x18000d92b  mov     rcx, rbx
0x18000d92e  mov     rax, [rax+120h]
0x18000d935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d93a  mov     [rbp+57h+var_48], eax
0x18000d93d  test    eax, eax
0x18000d93f  jns     short loc_18000D976
0x18000d941  lea     rcx, [rbp+57h+TlsValue]; this
0x18000d945  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000d94a  test    byte ptr cs:_bidGblFlags, 2
0x18000d951  jz      short loc_18000D8E0
0x18000d953  mov     r9d, 47Bh
0x18000d959  lea     r8, aCstdpropsetpro_5; "<CStdPropSetProperties2::Refresh|ADO|ER"...
0x18000d960  mov     edx, 11EC09h
0x18000d965  mov     rcx, cs:off_18012A1D8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000d96c  call    _bidTraceW
0x18000d971  jmp     loc_18000D8E0
0x18000d976  mov     [rbp+57h+var_98], r13
0x18000d97a  mov     rax, [rbx]
0x18000d97d  mov     rcx, rbx
0x18000d980  mov     rax, [rax+0F8h]
0x18000d987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d98c  mov     eax, eax
0x18000d98e  mov     [rbp+57h+var_88], rax
0x18000d992  lea     r13, [r14+50h]
0x18000d996  mov     eax, [rbp+57h+var_48]
0x18000d999  cmp     eax, 1
0x18000d99c  jz      loc_18000DDBD
0x18000d9a2  xor     r13d, r13d
0x18000d9a5  mov     [rbp+57h+var_A0], r13
0x18000d9a9  mov     rax, [rbx]
0x18000d9ac  lea     r8, [rbp+57h+pbstr]
0x18000d9b0  mov     rdx, [rbp+57h+arg_8]
0x18000d9b4  mov     rcx, rbx
0x18000d9b7  mov     rax, [rax+128h]
0x18000d9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9c3  mov     [rbp+57h+var_48], eax
0x18000d9c6  test    eax, eax
0x18000d9c8  js      loc_18000DD84
0x18000d9ce  mov     r15, [rbp+57h+pbstr]
0x18000d9d2  test    sil, 1
0x18000d9d6  jz      short loc_18000DA0F
0x18000d9d8  test    r15, r15
0x18000d9db  jz      short loc_18000DA0F
0x18000d9dd  mov     rcx, r15; pbstr
0x18000d9e0  call    cs:__imp_SysStringLen
0x18000d9e7  nop     dword ptr [rax+rax+00h]
0x18000d9ec  mov     edx, eax; ui
0x18000d9ee  mov     rcx, r15; strIn
0x18000d9f1  call    cs:__imp_SysAllocStringLen
0x18000d9f8  nop     dword ptr [rax+rax+00h]
0x18000d9fd  mov     r15, rax
0x18000da00  test    rax, rax
0x18000da03  jnz     short loc_18000DA0F
0x18000da05  and     sil, 0FBh
0x18000da09  mov     [rbp+57h+var_78], sil
0x18000da0d  jmp     short loc_18000DA2F
0x18000da0f  or      sil, 4
0x18000da13  mov     [rbp+57h+var_78], sil
0x18000da17  test    sil, 2
0x18000da1b  jz      short loc_18000DA2B
0x18000da1d  xor     ecx, ecx; bstrString
0x18000da1f  call    cs:__imp_SysFreeString
  ... truncated ...
```
