# CStdCollection::Refresh(void *,short)

- ea: `0x18000bbc0`
- end: `0x18000c5d4`
- name: `?Refresh@CStdCollection@@UEAAJPEAXF@Z`
- size: `2580`
- prototype: `__int64 __fastcall(CStdCollection *__hidden this, void *, __int16)`
- caller_count: `10`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001c470`
- `0x180056260`
- `0x18005a234`
- `0x18005a3d4`
- `0x18009d5f0`
- `0x18009f2d0`
- `0x18009fbb0`
- `0x1800a1e10`
- `0x1800a2e40`
- `0x1800a3490`

## callees

- `0x18000bbc0`
- `0x18000c700`
- `0x18000cd80`
- `0x18000d0e0`
- `0x18000f760`
- `0x18000f7c0`
- `0x180020e20`
- `0x180020fc0`
- `0x180042a04`
- `0x180047610`
- `0x1800530f0`
- `0x180053130`
- `0x180054098`
- `0x1800c8f34`
- `0x1800c930c`
- `0x1800cdaea`
- `0x1800d0010`

## import_xrefs

- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000bc6d`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000bfee`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000c14a`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000c47d`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000bc6d`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000bfee`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000c14a`
- `MSDART!?WriteLock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000c47d`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000c017`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000c030`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000c017`
- `MSDART!?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ` at `0x18000c030`
- `MSDART!MpHeapAlloc` at `0x18000bcb5`
- `MSDART!MpHeapAlloc` at `0x18000bd1c`
- `MSDART!MpHeapAlloc` at `0x18000bd5c`
- `MSDART!MpHeapAlloc` at `0x18000bfaf`
- `MSDART!MpHeapAlloc` at `0x18000bcb5`
- `MSDART!MpHeapAlloc` at `0x18000bd1c`
- `MSDART!MpHeapAlloc` at `0x18000bd5c`
- `MSDART!MpHeapAlloc` at `0x18000bfaf`
- `KERNEL32!TlsSetValue` at `0x18000bc3b`
- `KERNEL32!TlsSetValue` at `0x18000c087`
- `KERNEL32!TlsSetValue` at `0x18000bc3b`
- `KERNEL32!TlsSetValue` at `0x18000c087`
- `KERNEL32!TlsGetValue` at `0x18000bbf8`
- `KERNEL32!TlsGetValue` at `0x18000bbf8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000c108`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000c108`
- `OLEAUT32!__imp_SysFreeString` at `0x18000be10`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf18`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c049`
- `OLEAUT32!__imp_SysFreeString` at `0x18000be10`
- `OLEAUT32!__imp_SysFreeString` at `0x18000bf18`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c049`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c0f7`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c0f7`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000c1a3`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000c1a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CStdCollection::Refresh(CCollectionList **this, void *a2, unsigned __int16 a3)
{
  _DWORD *Value; // rax
  char v6; // di
  CReaderWriterLock3AR *v7; // r14
  int v8; // eax
  __int64 v9; // rax
  CCollectionList *v10; // r12
  __int64 v11; // r14
  int v12; // r15d
  unsigned int v13; // esi
  void *v14; // rax
  void *v15; // rax
  int v16; // eax
  OLECHAR *v17; // rsi
  CCollectionList *v18; // rcx
  CStdCollection *v19; // rdx
  unsigned __int64 v20; // r15
  unsigned int v21; // r12d
  int v22; // eax
  int v23; // esi
  int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rdx
  unsigned int v27; // ebx
  _DWORD *v29; // rax
  IErrorInfo *v30; // rdx
  UINT v32; // eax
  __int64 v33; // rsi
  __int64 v34; // r8
  unsigned int v35; // eax
  unsigned __int16 *v36; // rdx
  __int64 v37; // [rsp+30h] [rbp-39h] BYREF
  CCollectionMap *v38; // [rsp+38h] [rbp-31h]
  BSTR pbstr; // [rsp+40h] [rbp-29h] BYREF
  __int64 v40; // [rsp+48h] [rbp-21h]
  BSTR bstrString; // [rsp+50h] [rbp-19h] BYREF
  char v42; // [rsp+58h] [rbp-11h]
  _DWORD *TlsValue; // [rsp+60h] [rbp-9h] BYREF
  int v44; // [rsp+68h] [rbp-1h]
  __int64 v45; // [rsp+70h] [rbp+7h]
  int v46; // [rsp+78h] [rbp+Fh]
  __int16 v47; // [rsp+7Ch] [rbp+13h]
  char v48; // [rsp+7Eh] [rbp+15h]
  CCollectionList **v49; // [rsp+80h] [rbp+17h]
  int v50; // [rsp+88h] [rbp+1Fh]
  int v51; // [rsp+8Ch] [rbp+23h]
  __int64 v52; // [rsp+D0h] [rbp+67h] BYREF
  unsigned __int64 v53; // [rsp+E8h] [rbp+7Fh] BYREF

  v49 = this;
  v51 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v50 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v44 = 1;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v37 = 0;
  pbstr = 0;
  bstrString = 0;
  v6 = 6;
  v42 = 6;
  v53 = 0;
  v7 = (CReaderWriterLock3AR *)(this + 9);
  CReaderWriterLock3AR::WriteLock((CReaderWriterLock3AR *)(this + 9));
  v8 = (*((__int64 (__fastcall **)(CCollectionList **, _QWORD))*this + 35))(this, a3);
  v50 = v8;
  if ( v8 < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
      bidTraceW(off_18012A1B8[0], 172041, L"<CStdCollection::Refresh|ADO|ERR>  line %d\n", 168);
    goto LABEL_39;
  }
  if ( v8 != 1 )
  {
    v9 = MpHeapAlloc(g_hHeapHandle, 10485760, 48);
    v10 = (CCollectionList *)v9;
    v52 = v9;
    if ( v9 )
    {
      *(_DWORD *)v9 = 0;
      *(_QWORD *)(v9 + 8) = 0;
      *(_DWORD *)(v9 + 16) = 0;
      *(_DWORD *)(v9 + 24) = 0;
      *(_QWORD *)(v9 + 32) = 0;
      *(_DWORD *)(v9 + 40) = 0;
      *(_BYTE *)(v9 + 44) = 0;
      v11 = v9;
    }
    else
    {
      v11 = 0;
      v10 = 0;
      LODWORD(v52) = -2147024882;
      if ( (unsigned int)CContext::FailedPushWarning((CContext *)&TlsValue, (const int *)&v52) )
      {
        if ( (bidGblFlags & 2) != 0 )
          bidTraceW(off_18012A1B8[0], 190473, L"<CStdCollection::Refresh|ADO|ERR>  line %d\n", 186);
LABEL_65:
        v7 = (CReaderWriterLock3AR *)(this + 9);
        goto LABEL_39;
      }
    }
    v12 = (*((__int64 (__fastcall **)(CCollectionList **))*this + 45))(this);
    v13 = 8 * v12;
    v14 = (void *)MpHeapAlloc(g_hHeapHandle, 10485760, (unsigned int)(8 * v12));
    *(_QWORD *)(v11 + 8) = v14;
    if ( v14 )
    {
      memset_0(v14, 0, v13);
      *(_DWORD *)v11 = v12;
      v38 = (CCollectionMap *)(v11 + 24);
      v15 = (void *)MpHeapAlloc(g_hHeapHandle, 10485760, v13);
      *(_QWORD *)(v11 + 32) = v15;
      if ( v15 )
      {
        memset_0(v15, 0, v13);
        *(_DWORD *)v38 = v12;
        v50 = 0;
        v16 = (*((__int64 (__fastcall **)(CCollectionList **, _QWORD, __int64 *))*this + 36))(this, a3, &v37);
        v50 = v16;
        if ( v16 < 0 )
        {
          CContext::PushError((CContext *)&TlsValue);
          if ( (bidGblFlags & 2) != 0 )
            bidTraceW(off_18012A1B8[0], 194569, L"<CStdCollection::Refresh|ADO|ERR>  line %d\n", 190);
          v7 = (CReaderWriterLock3AR *)(this + 9);
          CReaderWriterLock3AR::WriteLock((CReaderWriterLock3AR *)(this + 9));
        }
        else
        {
          v40 = (__int64)v10;
          while ( 1 )
          {
            if ( v16 == 1 )
            {
              v50 = 0;
              CStdCollection::DestroyList((CStdCollection *)this, 0);
              this[8] = (CCollectionList *)v11;
              (*((void (__fastcall **)(CCollectionList **))*this + 46))(this);
              goto LABEL_65;
            }
            v53 = 0;
            v50 = (*((__int64 (__fastcall **)(CCollectionList **, __int64, BSTR *))*this + 37))(this, v37, &pbstr);
            if ( v50 < 0 )
              break;
            v17 = pbstr;
            if ( (v6 & 1) != 0 && pbstr && (v32 = SysStringLen(pbstr), (v17 = SysAllocStringLen(v17, v32)) == 0) )
            {
              v6 &= ~4u;
              v42 = v6;
            }
            else
            {
              v6 |= 4u;
              v42 = v6;
              if ( (v6 & 2) != 0 )
                SysFreeString(0);
              bstrString = v17;
            }
            v18 = this[8];
            if ( v18 )
            {
              v36 = 0;
              if ( (v6 & 4) != 0 )
                v36 = bstrString;
              LODWORD(v52) = CCollectionMap::LookUp((CCollectionList *)((char *)v18 + 24), v36, &v53);
              if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v52) )
              {
                if ( (bidGblFlags & 2) != 0 )
                  bidTraceW(off_18012A1B8[0], 211977, L"<CStdCollection::Refresh|ADO|ERR>  line %d\n", 207);
                goto LABEL_96;
              }
            }
            if ( !this[8] || (unsigned int)CContext::IsStatusFalse((CContext *)&TlsValue) )
            {
              v50 = (*((__int64 (__fastcall **)(CCollectionList **, __int64, _QWORD, unsigned __int64 *))*this + 38))(
                      this,
                      v37,
                      0,
                      &v53);
              if ( v50 < 0 )
              {
                CContext::PushError((CContext *)&TlsValue);
                if ( (bidGblFlags & 2) != 0 )
                  bidTraceW(off_18012A1B8[0], 218121, L"<CStdCollection::Refresh|ADO|ERR>  line %d\n", 213);
                goto LABEL_96;
              }
              LODWORD(v52) = 0;
              (*((void (__fastcall **)(CCollectionList **, unsigned __int64))*this + 43))(this, v53);
            }
            else
            {
              LODWORD(v52) = 1;
            }
            if ( v53 )
            {
              v19 = this[4];
              if ( this == (CCollectionList **)v19 )
                v19 = 0;
              (*(void (__fastcall **)(unsigned __int64, CStdCollection *))(*(_QWORD *)v53 + 152LL))(v53, v19);
              v50 = (*((__int64 (__fastcall **)(CCollectionList **, __int64, unsigned __int64))*this + 39))(
                      this,
                      v37,
                      v53);
              if ( v50 < 0 )
              {
                CContext::PushError((CContext *)&TlsValue);
                if ( (bidGblFlags & 2) != 0 )
                  bidTraceW(off_18012A1B8[0], 231433, L"<CStdCollection::Refresh|ADO|ERR>  line %d\n", 226);
                goto LABEL_96;
              }
              v20 = v53;
              v21 = *(_DWORD *)(v11 + 16);
              v22 = CCollectionArray::Insert((CCollectionArray *)v11, v21, v53);
              v23 = v22;
              if ( v22 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                  bidTraceW(
                    off_18012A218[0],
                    1380361,
                    L"<CCollectionList::Insert|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                    (unsigned int)v22,
                    1348);
                goto LABEL_100;
              }
              v24 = CCollectionMap::Insert(v38, (const struct CSysString *)&bstrString, v20);
              v23 = v24;
              if ( v24 < 0 )
              {
                CCollectionArray::Delete((CCollectionArray *)v11, v21);
                v6 = v42;
LABEL_100:
                v50 = v23;
                CContext::PushError((CContext *)&TlsValue);
                if ( (bidGblFlags & 2) != 0 )
                  bidTraceW(off_18012A1B8[0], 234505, L"<CStdCollection::Refresh|ADO|ERR>  line %d\n", 229);
                goto LABEL_96;
              }
              v50 = v24;
              if ( (_DWORD)v52 )
              {
                LODWORD(v52) = CCollectionList::DeleteByKey(this[8], (const struct CSysString *)&bstrString);
                if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v52) )
                {
                  if ( (bidGblFlags & 2) != 0 )
                    bidTraceW(off_18012A1B8[0], 239625, L"<CStdCollection::Refresh|ADO|ERR>  line %d\n", 234);
                  v6 = v42;
                  goto LABEL_96;
                }
              }
              v6 = v42;
            }
            SysFreeString(bstrString);
            bstrString = 0;
            v16 = (*((__int64 (__fastcall **)(CCollectionList **, __int64, _QWORD))*this + 40))(this, v37, a3);
            v50 = v16;
            if ( v16 < 0 )
            {
              CContext::PushError((CContext *)&TlsValue);
              if ( (bidGblFlags & 2) != 0 )
                bidTraceW(off_18012A1B8[0], 247817, L"<CStdCollection::Refresh|ADO|ERR>  line %d\n", 242);
              goto LABEL_96;
            }
          }
          CContext::PushError((CContext *)&TlsValue);
          if ( (bidGblFlags & 2) != 0 )
            bidTraceW(off_18012A1B8[0], 202761, L"<CStdCollection::Refresh|ADO|ERR>  line %d\n", 198);
LABEL_96:
          (*((void (__fastcall **)(CCollectionList **, __int64))*this + 41))(this, v37);
          v7 = (CReaderWriterLock3AR *)(this + 9);
          CReaderWriterLock3AR::WriteLock((CReaderWriterLock3AR *)(this + 9));
          v10 = (CCollectionList *)v40;
        }
        goto LABEL_57;
      }
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_82;
    }
    else if ( (bidGblFlags & 2) == 0 )
    {
      goto LABEL_82;
    }
    bidTraceW(
      off_18012A218[0],
      434185,
      L"<CDynamicArray::Reserve|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      2147942414LL,
      424);
LABEL_82:
    v50 = -2147024882;
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
      bidTraceW(off_18012A1B8[0], 191497, L"<CStdCollection::Refresh|ADO|ERR>  line %d\n", 187);
    v7 = (CReaderWriterLock3AR *)(this + 9);
    goto LABEL_36;
  }
  v50 = 0;
  if ( this[8] )
    goto LABEL_41;
  v25 = MpHeapAlloc(g_hHeapHandle, 10485760, 48);
  v10 = (CCollectionList *)v25;
  v40 = v25;
  if ( v25 )
  {
    *(_DWORD *)v25 = 0;
    *(_QWORD *)(v25 + 8) = 0;
    *(_DWORD *)(v25 + 16) = 0;
    *(_DWORD *)(v25 + 24) = 0;
    *(_QWORD *)(v25 + 32) = 0;
    *(_DWORD *)(v25 + 40) = 0;
    *(_BYTE *)(v25 + 44) = 0;
  }
  else
  {
    v10 = 0;
  }
  if ( (unsigned int)CContext::MemFailed((CContext *)&TlsValue, v10) )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceW(off_18012A1B8[0], 182281, L"<CStdCollection::Refresh|ADO|ERR>  line %d\n", 178);
    goto LABEL_39;
  }
  v35 = (*((__int64 (__fastcall **)(CCollectionList **))*this + 45))(this);
  LODWORD(v52) = CCollectionList::Reserve(v10, v35);
  if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v52) )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceW(off_18012A1B8[0], 183305, L"<CStdCollection::Refresh|ADO|ERR>  line %d\n", 179);
LABEL_36:
    CReaderWriterLock3AR::WriteLock(v7);
    if ( !v10 )
    {
      v10 = this[8];
      this[8] = 0;
      if ( !v10 )
      {
LABEL_38:
        CReaderWriterLock3AR::WriteUnlock(v7);
        goto LABEL_39;
      }
    }
LABEL_57:
    LODWORD(v33) = *((_DWORD *)v10 + 4);
    while ( (_DWORD)v33 )
    {
      v34 = (unsigned int)v33;
      v33 = (unsigned int)(v33 - 1);
      if ( (unsigned int)v33 < *((_DWORD *)v10 + 4) )
      {
        v26 = *(_QWORD *)(*((_QWORD *)v10 + 1) + 8 * v33);
        if ( v26 )
        {
          if ( v26 != v34 )
            (*((void (__fastcall **)(CCollectionList **))*this + 44))(this);
        }
      }
    }
    CCollectionList::`scalar deleting destructor'(v10, v26);
    goto LABEL_38;
  }
  this[8] = v10;
LABEL_39:
  if ( v50 < 0 )
    *((_DWORD *)this + 21) = 1;
LABEL_41:
  CReaderWriterLock3AR::WriteUnlock(v7);
  v27 = v50;
  if ( (v6 & 2) != 0 )
    SysFreeString(bstrString);
  if ( TlsValue[2]-- == 1 )
  {
    v29 = TlsValue;
    v30 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v30 )
    {
      SetErrorInfo(0, v30);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v29 = TlsValue;
    }
    if ( *((_BYTE *)v29 + 30) )
    {
      *((_QWORD *)v29 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v27;
}

```

## disassembly

```asm
0x18000bbc0  mov     [rsp-8+arg_8], rbx
0x18000bbc5  push    rbp
0x18000bbc6  push    rsi
0x18000bbc7  push    rdi
0x18000bbc8  push    r12
0x18000bbca  push    r13
0x18000bbcc  push    r14
0x18000bbce  push    r15
0x18000bbd0  lea     rbp, [rsp-27h]
0x18000bbd5  sub     rsp, 90h
0x18000bbdc  movzx   r13d, r8w
0x18000bbe0  mov     rbx, rcx
0x18000bbe3  mov     [rbp+57h+var_40], rcx
0x18000bbe7  xor     r15d, r15d
0x18000bbea  mov     [rbp+57h+var_34], r15d
0x18000bbee  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000bbf5  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000bbf8  call    cs:__imp_TlsGetValue
0x18000bbff  nop     dword ptr [rax+rax+00h]
0x18000bc04  mov     [rbp+57h+TlsValue], rax
0x18000bc08  mov     [rbp+57h+var_38], r15d
0x18000bc0c  test    rax, rax
0x18000bc0f  jnz     loc_18000BF86
0x18000bc15  mov     [rbp+57h+var_58], 1
0x18000bc1c  mov     [rbp+57h+var_50], r15
0x18000bc20  mov     [rbp+57h+var_48], r15d
0x18000bc24  mov     [rbp+57h+var_44], r15w
0x18000bc29  mov     [rbp+57h+var_42], r15b
0x18000bc2d  lea     rdx, [rbp+57h+TlsValue]; lpTlsValue
0x18000bc31  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000bc38  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000bc3b  call    cs:__imp_TlsSetValue
0x18000bc42  nop     dword ptr [rax+rax+00h]
0x18000bc47  lea     rax, [rbp+57h+TlsValue]
0x18000bc4b  mov     [rbp+57h+TlsValue], rax
0x18000bc4f  mov     [rbp+57h+var_90], r15
0x18000bc53  mov     [rbp+57h+pbstr], r15
0x18000bc57  mov     [rbp+57h+bstrString], r15
0x18000bc5b  mov     dil, 6
0x18000bc5e  mov     [rbp+57h+var_68], dil
0x18000bc62  mov     [rbp+57h+arg_18], r15
0x18000bc66  lea     r14, [rbx+48h]
0x18000bc6a  mov     rcx, r14
0x18000bc6d  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x18000bc74  nop     dword ptr [rax+rax+00h]
0x18000bc79  mov     rax, [rbx]
0x18000bc7c  movzx   edx, r13w
0x18000bc80  mov     rcx, rbx
0x18000bc83  mov     rax, [rax+118h]
0x18000bc8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc8f  mov     [rbp+57h+var_38], eax
0x18000bc92  test    eax, eax
0x18000bc94  js      loc_18000C0B2
0x18000bc9a  cmp     eax, 1
0x18000bc9d  jz      loc_18000BF8E
0x18000bca3  mov     edx, 0A00000h
0x18000bca8  mov     r8d, 30h ; '0'
0x18000bcae  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000bcb5  call    cs:__imp_MpHeapAlloc
0x18000bcbc  nop     dword ptr [rax+rax+00h]
0x18000bcc1  mov     r12, rax
0x18000bcc4  mov     [rbp+57h+arg_0], rax
0x18000bcc8  test    rax, rax
0x18000bccb  jz      loc_18000C2CB
0x18000bcd1  mov     [rax], r15d
0x18000bcd4  mov     [rax+8], r15
0x18000bcd8  mov     [rax+10h], r15d
0x18000bcdc  mov     [rax+18h], r15d
0x18000bce0  mov     [rax+20h], r15
0x18000bce4  mov     [rax+28h], r15d
0x18000bce8  mov     byte ptr [rax+2Ch], 0
0x18000bcec  mov     r14, rax
0x18000bcef  mov     rax, [rbx]
0x18000bcf2  mov     rcx, rbx
0x18000bcf5  mov     rax, [rax+168h]
0x18000bcfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd01  mov     r15d, eax
0x18000bd04  lea     ecx, ds:0[rax*8]
0x18000bd0b  mov     esi, ecx
0x18000bd0d  mov     r8d, ecx
0x18000bd10  mov     edx, 0A00000h
0x18000bd15  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000bd1c  call    cs:__imp_MpHeapAlloc
0x18000bd23  nop     dword ptr [rax+rax+00h]
0x18000bd28  mov     [r14+8], rax
0x18000bd2c  test    rax, rax
0x18000bd2f  jz      loc_18000C2F2
0x18000bd35  mov     r8d, esi; Size
0x18000bd38  xor     edx, edx; Val
0x18000bd3a  mov     rcx, rax; void *
0x18000bd3d  call    memset_0
0x18000bd42  mov     [r14], r15d
0x18000bd45  lea     rax, [r14+18h]
0x18000bd49  mov     [rbp+57h+var_88], rax
0x18000bd4d  mov     r8d, esi
0x18000bd50  mov     edx, 0A00000h
0x18000bd55  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000bd5c  call    cs:__imp_MpHeapAlloc
0x18000bd63  nop     dword ptr [rax+rax+00h]
0x18000bd68  mov     rcx, [rbp+57h+var_88]
0x18000bd6c  mov     [rcx+8], rax
0x18000bd70  test    rax, rax
0x18000bd73  jz      loc_18000C2FD
0x18000bd79  mov     r8d, esi; Size
0x18000bd7c  xor     edx, edx; Val
0x18000bd7e  mov     rcx, rax; void *
0x18000bd81  call    memset_0
0x18000bd86  mov     rax, [rbp+57h+var_88]
0x18000bd8a  mov     [rax], r15d
0x18000bd8d  xor     r15d, r15d
0x18000bd90  mov     [rbp+57h+var_38], r15d
0x18000bd94  mov     rax, [rbx]
0x18000bd97  lea     r8, [rbp+57h+var_90]
0x18000bd9b  movzx   edx, r13w
0x18000bd9f  mov     rcx, rbx
0x18000bda2  mov     rax, [rax+120h]
0x18000bda9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdae  mov     [rbp+57h+var_38], eax
0x18000bdb1  test    eax, eax
0x18000bdb3  js      loc_18000C12D
0x18000bdb9  mov     [rbp+57h+var_78], r12
0x18000bdbd  nop     dword ptr [rax]
0x18000bdc0  mov     rcx, rbx; this
0x18000bdc3  cmp     eax, 1
0x18000bdc6  jz      loc_18000C1CC
0x18000bdcc  mov     [rbp+57h+arg_18], r15
0x18000bdd0  mov     rax, [rbx]
0x18000bdd3  lea     r8, [rbp+57h+pbstr]
0x18000bdd7  mov     rdx, [rbp+57h+var_90]
0x18000bddb  mov     rax, [rax+128h]
0x18000bde2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bde7  mov     [rbp+57h+var_38], eax
0x18000bdea  test    eax, eax
0x18000bdec  js      loc_18000C57D
0x18000bdf2  mov     rsi, [rbp+57h+pbstr]
0x18000bdf6  test    dil, 1
0x18000bdfa  jnz     loc_18000C0EB
0x18000be00  or      dil, 4
0x18000be04  mov     [rbp+57h+var_68], dil
0x18000be08  test    dil, 2
0x18000be0c  jz      short loc_18000BE1C
0x18000be0e  xor     ecx, ecx; bstrString
0x18000be10  call    cs:__imp_SysFreeString
0x18000be17  nop     dword ptr [rax+rax+00h]
0x18000be1c  mov     [rbp+57h+bstrString], rsi
0x18000be20  mov     rcx, [rbx+40h]
0x18000be24  test    rcx, rcx
0x18000be27  jnz     loc_18000C392
0x18000be2d  cmp     qword ptr [rbx+40h], 0
0x18000be32  jnz     loc_18000C3F0
0x18000be38  mov     rax, [rbx]
0x18000be3b  lea     r9, [rbp+57h+arg_18]
0x18000be3f  xor     r8d, r8d
0x18000be42  mov     rdx, [rbp+57h+var_90]
0x18000be46  mov     rcx, rbx
0x18000be49  mov     rax, [rax+130h]
0x18000be50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be55  mov     [rbp+57h+var_38], eax
0x18000be58  test    eax, eax
0x18000be5a  js      loc_18000C544
0x18000be60  mov     dword ptr [rbp+57h+arg_0], r15d
0x18000be64  mov     rax, [rbx]
0x18000be67  mov     rdx, [rbp+57h+arg_18]
0x18000be6b  mov     rcx, rbx
0x18000be6e  mov     rax, [rax+158h]
0x18000be75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be7a  mov     rcx, [rbp+57h+arg_18]
0x18000be7e  test    rcx, rcx
0x18000be81  jz      loc_18000BF14
0x18000be87  mov     rax, [rcx]
0x18000be8a  mov     rdx, [rbx+20h]
0x18000be8e  cmp     rbx, rdx
0x18000be91  cmovz   rdx, r15
0x18000be95  mov     rax, [rax+98h]
0x18000be9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bea1  mov     rax, [rbx]
0x18000bea4  mov     r8, [rbp+57h+arg_18]
0x18000bea8  mov     rdx, [rbp+57h+var_90]
0x18000beac  mov     rcx, rbx
0x18000beaf  mov     rax, [rax+138h]
0x18000beb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bebb  mov     [rbp+57h+var_38], eax
0x18000bebe  test    eax, eax
0x18000bec0  js      loc_18000C50B
0x18000bec6  mov     r15, [rbp+57h+arg_18]
0x18000beca  mov     r12d, [r14+10h]
0x18000bece  mov     r8, r15; unsigned __int64
0x18000bed1  mov     edx, r12d; unsigned int
0x18000bed4  mov     rcx, r14; this
0x18000bed7  call    ?Insert@CCollectionArray@@QEAAJK_K@Z; CCollectionArray::Insert(ulong,unsigned __int64)
0x18000bedc  mov     esi, eax
0x18000bede  test    eax, eax
0x18000bee0  js      loc_18000C4A3
0x18000bee6  mov     r8, r15; unsigned __int64
0x18000bee9  lea     rdx, [rbp+57h+bstrString]; struct CSysString *
0x18000beed  mov     rcx, [rbp+57h+var_88]; this
0x18000bef1  call    ?Insert@CCollectionMap@@QEAAJAEBVCSysString@@_K@Z; CCollectionMap::Insert(CSysString const &,unsigned __int64)
0x18000bef6  mov     esi, eax
0x18000bef8  test    eax, eax
0x18000befa  js      loc_18000C492
0x18000bf00  mov     [rbp+57h+var_38], eax
0x18000bf03  cmp     dword ptr [rbp+57h+arg_0], 0
0x18000bf07  jnz     loc_18000C40D
0x18000bf0d  xor     r15d, r15d
0x18000bf10  movzx   edi, [rbp+57h+var_68]
0x18000bf14  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000bf18  call    cs:__imp_SysFreeString
0x18000bf1f  nop     dword ptr [rax+rax+00h]
0x18000bf24  mov     [rbp+57h+bstrString], r15
0x18000bf28  mov     rax, [rbx]
0x18000bf2b  movzx   r8d, r13w
0x18000bf2f  mov     rdx, [rbp+57h+var_90]
0x18000bf33  mov     rcx, rbx
0x18000bf36  mov     rax, [rax+140h]
0x18000bf3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf42  mov     [rbp+57h+var_38], eax
0x18000bf45  test    eax, eax
0x18000bf47  jns     loc_18000BDC0
0x18000bf4d  lea     rcx, [rbp+57h+TlsValue]; this
0x18000bf51  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000bf56  test    byte ptr cs:_bidGblFlags, 2
0x18000bf5d  jz      loc_18000C460
0x18000bf63  mov     r9d, 0F2h
0x18000bf69  lea     r8, aCstdcollection_2; "<CStdCollection::Refresh|ADO|ERR>  line"...
0x18000bf70  mov     edx, 3C809h
0x18000bf75  mov     rcx, cs:off_18012A1B8; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000bf7c  call    _bidTraceW
0x18000bf81  jmp     loc_18000C460
0x18000bf86  inc     dword ptr [rax+8]
0x18000bf89  jmp     loc_18000BC4F
0x18000bf8e  mov     [rbp+57h+var_38], r15d
0x18000bf92  cmp     qword ptr [rbx+40h], 0
0x18000bf97  jnz     loc_18000C02D
0x18000bf9d  mov     edx, 0A00000h
0x18000bfa2  mov     r8d, 30h ; '0'
0x18000bfa8  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000bfaf  call    cs:__imp_MpHeapAlloc
0x18000bfb6  nop     dword ptr [rax+rax+00h]
0x18000bfbb  mov     r12, rax
0x18000bfbe  mov     [rbp+57h+var_78], rax
0x18000bfc2  test    rax, rax
0x18000bfc5  jz      loc_18000C21F
0x18000bfcb  mov     [rax], r15d
0x18000bfce  mov     [rax+8], r15
0x18000bfd2  mov     [rax+10h], r15d
0x18000bfd6  mov     [rax+18h], r15d
0x18000bfda  mov     [rax+20h], r15
0x18000bfde  mov     [rax+28h], r15d
0x18000bfe2  mov     byte ptr [rax+2Ch], 0
0x18000bfe6  jmp     loc_18000C222
0x18000bfeb  mov     rcx, r14
0x18000bfee  call    cs:__imp_?WriteLock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteLock(void)
0x18000bff5  nop     dword ptr [rax+rax+00h]
0x18000bffa  test    r12, r12
0x18000bffd  jnz     loc_18000C156
0x18000c003  mov     r12, [rbx+40h]
0x18000c007  mov     [rbx+40h], r15
0x18000c00b  test    r12, r12
0x18000c00e  jnz     loc_18000C156
0x18000c014  mov     rcx, r14
0x18000c017  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x18000c01e  nop     dword ptr [rax+rax+00h]
0x18000c023  cmp     [rbp+57h+var_38], 0
0x18000c027  jl      loc_18000C5B6
0x18000c02d  mov     rcx, r14
0x18000c030  call    cs:__imp_?WriteUnlock@CReaderWriterLock3AR@@QEAAXXZ; CReaderWriterLock3AR::WriteUnlock(void)
0x18000c037  nop     dword ptr [rax+rax+00h]
0x18000c03c  mov     ebx, [rbp+57h+var_38]
0x18000c03f  test    dil, 2
0x18000c043  jz      short loc_18000C056
0x18000c045  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000c049  call    cs:__imp_SysFreeString
0x18000c050  nop     dword ptr [rax+rax+00h]
0x18000c055  nop
0x18000c056  mov     rax, [rbp+57h+TlsValue]
0x18000c05a  add     dword ptr [rax+8], 0FFFFFFFFh
0x18000c05e  jnz     short loc_18000C094
0x18000c060  mov     rax, [rbp+57h+TlsValue]
0x18000c064  mov     rdx, [rax+10h]; perrinfo
0x18000c068  test    rdx, rdx
0x18000c06b  jnz     loc_18000C1A1
0x18000c071  cmp     byte ptr [rax+1Eh], 0
0x18000c075  jnz     loc_18000C5C2
0x18000c07b  xor     edx, edx; lpTlsValue
0x18000c07d  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000c084  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000c087  call    cs:__imp_TlsSetValue
0x18000c08e  nop     dword ptr [rax+rax+00h]
0x18000c093  nop
0x18000c094  mov     eax, ebx
0x18000c096  mov     rbx, [rsp+0C0h+arg_8]
0x18000c09e  add     rsp, 90h
0x18000c0a5  pop     r15
0x18000c0a7  pop     r14
0x18000c0a9  pop     r13
0x18000c0ab  pop     r12
0x18000c0ad  pop     rdi
0x18000c0ae  pop     rsi
0x18000c0af  pop     rbp
0x18000c0b0  retn
  ... truncated ...
```
