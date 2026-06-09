# CRsetField::ReleaseAccessors(void)

- ea: `0x18002d370`
- end: `0x18002d98d`
- name: `?ReleaseAccessors@CRsetField@@QEAAJXZ`
- size: `1565`
- prototype: `__int64 __fastcall(CRsetField *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002d044`

## callees

- `0x180001514`
- `0x180020e20`
- `0x180020fc0`
- `0x18002d370`
- `0x18002d994`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapFree` at `0x18002d826`
- `MSDART!MpHeapFree` at `0x18002d826`
- `KERNEL32!TlsSetValue` at `0x18002d3dd`
- `KERNEL32!TlsSetValue` at `0x18002d969`
- `KERNEL32!TlsSetValue` at `0x18002d3dd`
- `KERNEL32!TlsSetValue` at `0x18002d969`
- `KERNEL32!TlsGetValue` at `0x18002d39c`
- `KERNEL32!TlsGetValue` at `0x18002d39c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002d933`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002d933`

## string_xrefs

- `0x18002d4ac`: `<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n`
- `0x18002d55a`: `<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n`
- `0x18002d5ff`: `<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n`
- `0x18002d698`: `<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n`
- `0x18002d738`: `<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n`
- `0x18002d7d8`: `<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n`
- `0x18002d8a8`: `<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n`
- `0x18002d4c5`: `<CRsetField::ReleaseAccessors|ADO|ERR>  line %d\n`
- `0x18002d573`: `<CRsetField::ReleaseAccessors|ADO|ERR>  line %d\n`
- `0x18002d8c6`: `<CRsetField::ReleaseAccessors|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRsetField::ReleaseAccessors(CRsetField *this)
{
  char *v2; // rcx
  _DWORD *Value; // rax
  __int64 v4; // rdx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, struct IAccessor **); // rcx
  int v6; // eax
  unsigned int v7; // eax
  unsigned int BidObjectID; // eax
  unsigned int v9; // eax
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rdx
  unsigned int v13; // eax
  __int64 v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // eax
  __int64 v18; // rdx
  __int64 v19; // rdx
  unsigned int v20; // eax
  unsigned int v21; // ebx
  _DWORD *v23; // rax
  IErrorInfo *v24; // rdx
  _DWORD *TlsValue; // [rsp+30h] [rbp-30h] BYREF
  int v27; // [rsp+38h] [rbp-28h]
  __int64 v28; // [rsp+40h] [rbp-20h]
  int v29; // [rsp+48h] [rbp-18h]
  __int16 v30; // [rsp+4Ch] [rbp-14h]
  char v31; // [rsp+4Eh] [rbp-12h]
  char *v32; // [rsp+50h] [rbp-10h]
  int SetAccessors; // [rsp+58h] [rbp-8h]
  int v34; // [rsp+5Ch] [rbp-4h]
  int v35; // [rsp+80h] [rbp+20h] BYREF
  __int64 (__fastcall ***v36)(_QWORD, GUID *, struct IAccessor **); // [rsp+88h] [rbp+28h] BYREF
  struct IAccessor *v37; // [rsp+90h] [rbp+30h] BYREF

  v2 = (char *)this + 8;
  if ( !this )
    v2 = 0;
  v32 = v2;
  v34 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  SetAccessors = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v27 = 1;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v37 = 0;
  v4 = *((_QWORD *)this + 21);
  if ( v4 )
  {
    v36 = 0;
    if ( (*((_BYTE *)this + 176) & 1) == 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
      v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IAccessor **))*((_QWORD *)this + 21);
LABEL_18:
      v6 = 0;
      v36 = v5;
LABEL_19:
      SetAccessors = v6;
      SetAccessors = (**v5)(v5, &IID_IAccessor, &v37);
      if ( SetAccessors < 0 )
      {
        CContext::PushError((CContext *)&TlsValue);
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) == -1 )
          {
            bidTraceW(off_18012A1F0[0], 1286153, L"<CRsetField::ReleaseAccessors|ADO|ERR>  line %d\n", 1256);
          }
          else
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
            bidTraceW(
              off_18012A1F0[0],
              1286153,
              L"<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n",
              BidObjectID,
              1256);
          }
        }
        if ( v36 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IAccessor **)))(*v36)[2])(v36);
        goto LABEL_68;
      }
      SetAccessors = CRsetField::ReleaseGetSetAccessors(this, v37);
      if ( SetAccessors < 0 )
      {
        CContext::PushError((CContext *)&TlsValue);
        if ( (bidGblFlags & 2) == 0 )
        {
LABEL_62:
          ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v36);
LABEL_66:
          if ( v37 )
            ((void (__fastcall *)(struct IAccessor *))v37->lpVtbl->Release)(v37);
          goto LABEL_68;
        }
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v9 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          bidTraceW(off_18012A1F0[0], 1297417, L"<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n", v9, 1267);
          goto LABEL_62;
        }
        v10 = 1267;
        v11 = 1297417;
LABEL_61:
        bidTraceW(off_18012A1F0[0], v11, L"<CRsetField::ReleaseAccessors|ADO|ERR>  line %d\n", v10);
        goto LABEL_62;
      }
      v12 = *((_QWORD *)this + 27);
      if ( v12 )
      {
        v35 = ((__int64 (__fastcall *)(struct IAccessor *, __int64, _QWORD))v37->lpVtbl->ReleaseAccessor)(v37, v12, 0);
        if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v35) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_62;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
          {
            v13 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
            bidTraceW(off_18012A1F0[0], 1302537, L"<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n", v13, 1272);
            goto LABEL_62;
          }
          v10 = 1272;
          v11 = 1302537;
          goto LABEL_61;
        }
        *((_QWORD *)this + 27) = 0;
      }
      v14 = *((_QWORD *)this + 28);
      if ( v14 )
      {
        v35 = ((__int64 (__fastcall *)(struct IAccessor *, __int64, _QWORD))v37->lpVtbl->ReleaseAccessor)(v37, v14, 0);
        if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v35) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_62;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
          {
            v15 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
            bidTraceW(off_18012A1F0[0], 1309705, L"<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n", v15, 1279);
            goto LABEL_62;
          }
          v10 = 1279;
          v11 = 1309705;
          goto LABEL_61;
        }
        *((_QWORD *)this + 28) = 0;
      }
      v16 = *((_QWORD *)this + 29);
      if ( v16 )
      {
        v35 = ((__int64 (__fastcall *)(struct IAccessor *, __int64, _QWORD))v37->lpVtbl->ReleaseAccessor)(v37, v16, 0);
        if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v35) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_62;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
          {
            v17 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
            bidTraceW(off_18012A1F0[0], 1316873, L"<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n", v17, 1286);
            goto LABEL_62;
          }
          v10 = 1286;
          v11 = 1316873;
          goto LABEL_61;
        }
        *((_QWORD *)this + 29) = 0;
      }
      *((_WORD *)this + 120) = 0;
      *((_QWORD *)this + 32) = 0;
      v18 = *((_QWORD *)this + 31);
      if ( v18 )
      {
        MpHeapFree(g_hHeapHandle, v18);
        *((_QWORD *)this + 31) = 0;
      }
      v19 = *((_QWORD *)this + 20);
      if ( v19 )
      {
        v35 = ((__int64 (__fastcall *)(struct IAccessor *, __int64, _QWORD))v37->lpVtbl->ReleaseAccessor)(v37, v19, 0);
        if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, &v35) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_62;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
          {
            v20 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
            bidTraceW(off_18012A1F0[0], 1336329, L"<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n", v20, 1305);
            goto LABEL_62;
          }
          v10 = 1305;
          v11 = 1336329;
          goto LABEL_61;
        }
        *((_QWORD *)this + 20) = 0;
      }
      if ( v36 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, struct IAccessor **)))(*v36)[2])(v36);
      goto LABEL_66;
    }
    if ( !(_DWORD)v4 )
    {
      v5 = 0;
      goto LABEL_18;
    }
    v36 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, struct IAccessor **)))(**((_QWORD **)g_pStaticGlobals + 10) + 40LL))(
           *((_QWORD *)g_pStaticGlobals + 10),
           v4,
           &IID_IRowset,
           &v36);
    if ( v6 >= 0 )
    {
      v5 = v36;
      goto LABEL_19;
    }
    SetAccessors = v6;
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) == -1 )
      {
        bidTraceW(off_18012A1F0[0], 1282057, L"<CRsetField::ReleaseAccessors|ADO|ERR>  line %d\n", 1252);
      }
      else
      {
        v7 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
        bidTraceW(off_18012A1F0[0], 1282057, L"<CRsetField::ReleaseAccessors|ADO|ERR> %u#, line %d\n", v7, 1252);
      }
    }
    ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v36);
  }
LABEL_68:
  v21 = SetAccessors;
  if ( TlsValue[2]-- == 1 )
  {
    v23 = TlsValue;
    v24 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v24 )
    {
      SetErrorInfo(0, v24);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v23 = TlsValue;
    }
    if ( *((_BYTE *)v23 + 30) )
    {
      *((_QWORD *)v23 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v21;
}

```

## disassembly

```asm
0x18002d370  push    rbp
0x18002d372  push    rbx
0x18002d373  push    rdi
0x18002d374  mov     rbp, rsp
0x18002d377  sub     rsp, 60h
0x18002d37b  mov     rbx, rcx
0x18002d37e  add     rcx, 8
0x18002d382  xor     edi, edi
0x18002d384  test    rbx, rbx
0x18002d387  cmovz   rcx, rdi
0x18002d38b  mov     [rbp+var_10], rcx
0x18002d38f  mov     [rbp+var_4], edi
0x18002d392  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002d399  mov     ecx, [rcx+14h]; dwTlsIndex
0x18002d39c  call    cs:__imp_TlsGetValue
0x18002d3a3  nop     dword ptr [rax+rax+00h]
0x18002d3a8  mov     [rbp+TlsValue], rax
0x18002d3ac  mov     [rbp+var_8], edi
0x18002d3af  test    rax, rax
0x18002d3b2  jz      short loc_18002D3B9
0x18002d3b4  inc     dword ptr [rax+8]
0x18002d3b7  jmp     short loc_18002D3F1
0x18002d3b9  mov     [rbp+var_28], 1
0x18002d3c0  mov     [rbp+var_20], rdi
0x18002d3c4  mov     [rbp+var_18], edi
0x18002d3c7  mov     [rbp+var_14], di
0x18002d3cb  mov     [rbp+var_12], dil
0x18002d3cf  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x18002d3d3  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002d3da  mov     ecx, [rcx+14h]; dwTlsIndex
0x18002d3dd  call    cs:__imp_TlsSetValue
0x18002d3e4  nop     dword ptr [rax+rax+00h]
0x18002d3e9  lea     rax, [rbp+TlsValue]
0x18002d3ed  mov     [rbp+TlsValue], rax
0x18002d3f1  mov     [rbp+arg_10], rdi
0x18002d3f5  mov     rdx, [rbx+0A8h]
0x18002d3fc  test    rdx, rdx
0x18002d3ff  jz      loc_18002D917
0x18002d405  mov     [rbp+arg_8], rdi
0x18002d409  test    byte ptr [rbx+0B0h], 1
0x18002d410  jnz     short loc_18002D42D
0x18002d412  mov     rax, [rdx]
0x18002d415  mov     rcx, rdx
0x18002d418  mov     rax, [rax+8]
0x18002d41c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d421  mov     rcx, [rbx+0A8h]
0x18002d428  jmp     loc_18002D4EF
0x18002d42d  test    edx, edx
0x18002d42f  jz      loc_18002D4EC
0x18002d435  mov     [rbp+arg_8], rdi
0x18002d439  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002d440  mov     rcx, [rax+50h]
0x18002d444  mov     rax, [rcx]
0x18002d447  lea     r9, [rbp+arg_8]
0x18002d44b  lea     r8, IID_IRowset
0x18002d452  mov     rax, [rax+28h]
0x18002d456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d45b  test    eax, eax
0x18002d45d  js      short loc_18002D468
0x18002d45f  mov     rcx, [rbp+arg_8]
0x18002d463  jmp     loc_18002D4F5
0x18002d468  mov     [rbp+var_8], eax
0x18002d46b  lea     rcx, [rbp+TlsValue]; this
0x18002d46f  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18002d474  test    byte ptr cs:_bidGblFlags, 2
0x18002d47b  jz      short loc_18002D4DE
0x18002d47d  lea     rcx, [rbx+138h]; this
0x18002d484  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d489  cmp     eax, 0FFFFFFFFh
0x18002d48c  jz      short loc_18002D4BF
0x18002d48e  lea     rcx, [rbx+138h]; this
0x18002d495  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d49a  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002d4a1  mov     [rsp+60h+var_40], 4E4h
0x18002d4a9  mov     r9d, eax
0x18002d4ac  lea     r8, aCrsetfieldRele_4; "<CRsetField::ReleaseAccessors|ADO|ERR> "...
0x18002d4b3  mov     edx, 139009h
0x18002d4b8  call    _bidTraceW
0x18002d4bd  jmp     short loc_18002D4DE
0x18002d4bf  mov     r9d, 4E4h
0x18002d4c5  lea     r8, aCrsetfieldRele_1; "<CRsetField::ReleaseAccessors|ADO|ERR> "...
0x18002d4cc  mov     edx, 139009h
0x18002d4d1  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002d4d8  call    _bidTraceW
0x18002d4dd  nop
0x18002d4de  lea     rcx, [rbp+arg_8]
0x18002d4e2  call    ??1?$CComPtr@UIDBCreateSession@@@ATL@@QEAA@XZ; ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(void)
0x18002d4e7  jmp     loc_18002D917
0x18002d4ec  mov     rcx, rdi
0x18002d4ef  mov     eax, edi
0x18002d4f1  mov     [rbp+arg_8], rcx
0x18002d4f5  mov     [rbp+var_8], eax
0x18002d4f8  mov     rax, [rcx]
0x18002d4fb  lea     r8, [rbp+arg_10]
0x18002d4ff  lea     rdx, IID_IAccessor
0x18002d506  mov     rax, [rax]
0x18002d509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d50e  mov     [rbp+var_8], eax
0x18002d511  test    eax, eax
0x18002d513  jns     loc_18002D5A7
0x18002d519  lea     rcx, [rbp+TlsValue]; this
0x18002d51d  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18002d522  test    byte ptr cs:_bidGblFlags, 2
0x18002d529  jz      short loc_18002D58C
0x18002d52b  lea     rcx, [rbx+138h]; this
0x18002d532  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d537  cmp     eax, 0FFFFFFFFh
0x18002d53a  jz      short loc_18002D56D
0x18002d53c  lea     rcx, [rbx+138h]; this
0x18002d543  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d548  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002d54f  mov     [rsp+60h+var_40], 4E8h
0x18002d557  mov     r9d, eax
0x18002d55a  lea     r8, aCrsetfieldRele_4; "<CRsetField::ReleaseAccessors|ADO|ERR> "...
0x18002d561  mov     edx, 13A009h
0x18002d566  call    _bidTraceW
0x18002d56b  jmp     short loc_18002D58C
0x18002d56d  mov     r9d, 4E8h
0x18002d573  lea     r8, aCrsetfieldRele_1; "<CRsetField::ReleaseAccessors|ADO|ERR> "...
0x18002d57a  mov     edx, 13A009h
0x18002d57f  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002d586  call    _bidTraceW
0x18002d58b  nop
0x18002d58c  mov     rcx, [rbp+arg_8]
0x18002d590  test    rcx, rcx
0x18002d593  jz      short loc_18002D5A2
0x18002d595  mov     rax, [rcx]
0x18002d598  mov     rax, [rax+10h]
0x18002d59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5a1  nop
0x18002d5a2  jmp     loc_18002D917
0x18002d5a7  mov     rdx, [rbp+arg_10]; struct IAccessor *
0x18002d5ab  mov     rcx, rbx; this
0x18002d5ae  call    ?ReleaseGetSetAccessors@CRsetField@@AEAAJPEAUIAccessor@@@Z; CRsetField::ReleaseGetSetAccessors(IAccessor *)
0x18002d5b3  mov     [rbp+var_8], eax
0x18002d5b6  test    eax, eax
0x18002d5b8  jns     short loc_18002D625
0x18002d5ba  lea     rcx, [rbp+TlsValue]; this
0x18002d5be  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18002d5c3  test    byte ptr cs:_bidGblFlags, 2
0x18002d5ca  jz      loc_18002D8DA
0x18002d5d0  lea     rcx, [rbx+138h]; this
0x18002d5d7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d5dc  cmp     eax, 0FFFFFFFFh
0x18002d5df  jz      short loc_18002D615
0x18002d5e1  lea     rcx, [rbx+138h]; this
0x18002d5e8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d5ed  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002d5f4  mov     [rsp+60h+var_40], 4F3h
0x18002d5fc  mov     r9d, eax
0x18002d5ff  lea     r8, aCrsetfieldRele_4; "<CRsetField::ReleaseAccessors|ADO|ERR> "...
0x18002d606  mov     edx, 13CC09h
0x18002d60b  call    _bidTraceW
0x18002d610  jmp     loc_18002D8DA
0x18002d615  mov     r9d, 4F3h
0x18002d61b  mov     edx, 13CC09h
0x18002d620  jmp     loc_18002D8C6
0x18002d625  mov     rdx, [rbx+0D8h]
0x18002d62c  test    rdx, rdx
0x18002d62f  jz      loc_18002D6C5
0x18002d635  mov     rcx, [rbp+arg_10]
0x18002d639  mov     rax, [rcx]
0x18002d63c  xor     r8d, r8d
0x18002d63f  mov     rax, [rax+30h]
0x18002d643  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d648  mov     [rbp+arg_0], eax
0x18002d64b  lea     rdx, [rbp+arg_0]; int *
0x18002d64f  lea     rcx, [rbp+TlsValue]; this
0x18002d653  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18002d658  test    eax, eax
0x18002d65a  jz      short loc_18002D6BE
0x18002d65c  test    byte ptr cs:_bidGblFlags, 2
0x18002d663  jz      loc_18002D8DA
0x18002d669  lea     rcx, [rbx+138h]; this
0x18002d670  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d675  cmp     eax, 0FFFFFFFFh
0x18002d678  jz      short loc_18002D6AE
0x18002d67a  lea     rcx, [rbx+138h]; this
0x18002d681  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d686  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002d68d  mov     [rsp+60h+var_40], 4F8h
0x18002d695  mov     r9d, eax
0x18002d698  lea     r8, aCrsetfieldRele_4; "<CRsetField::ReleaseAccessors|ADO|ERR> "...
0x18002d69f  mov     edx, 13E009h
0x18002d6a4  call    _bidTraceW
0x18002d6a9  jmp     loc_18002D8DA
0x18002d6ae  mov     r9d, 4F8h
0x18002d6b4  mov     edx, 13E009h
0x18002d6b9  jmp     loc_18002D8C6
0x18002d6be  mov     [rbx+0D8h], rdi
0x18002d6c5  mov     rdx, [rbx+0E0h]
0x18002d6cc  test    rdx, rdx
0x18002d6cf  jz      loc_18002D765
0x18002d6d5  mov     rcx, [rbp+arg_10]
0x18002d6d9  mov     rax, [rcx]
0x18002d6dc  xor     r8d, r8d
0x18002d6df  mov     rax, [rax+30h]
0x18002d6e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d6e8  mov     [rbp+arg_0], eax
0x18002d6eb  lea     rdx, [rbp+arg_0]; int *
0x18002d6ef  lea     rcx, [rbp+TlsValue]; this
0x18002d6f3  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18002d6f8  test    eax, eax
0x18002d6fa  jz      short loc_18002D75E
0x18002d6fc  test    byte ptr cs:_bidGblFlags, 2
0x18002d703  jz      loc_18002D8DA
0x18002d709  lea     rcx, [rbx+138h]; this
0x18002d710  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d715  cmp     eax, 0FFFFFFFFh
0x18002d718  jz      short loc_18002D74E
0x18002d71a  lea     rcx, [rbx+138h]; this
0x18002d721  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d726  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002d72d  mov     [rsp+60h+var_40], 4FFh
0x18002d735  mov     r9d, eax
0x18002d738  lea     r8, aCrsetfieldRele_4; "<CRsetField::ReleaseAccessors|ADO|ERR> "...
0x18002d73f  mov     edx, 13FC09h
0x18002d744  call    _bidTraceW
0x18002d749  jmp     loc_18002D8DA
0x18002d74e  mov     r9d, 4FFh
0x18002d754  mov     edx, 13FC09h
0x18002d759  jmp     loc_18002D8C6
0x18002d75e  mov     [rbx+0E0h], rdi
0x18002d765  mov     rdx, [rbx+0E8h]
0x18002d76c  test    rdx, rdx
0x18002d76f  jz      loc_18002D805
0x18002d775  mov     rcx, [rbp+arg_10]
0x18002d779  mov     rax, [rcx]
0x18002d77c  xor     r8d, r8d
0x18002d77f  mov     rax, [rax+30h]
0x18002d783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d788  mov     [rbp+arg_0], eax
0x18002d78b  lea     rdx, [rbp+arg_0]; int *
0x18002d78f  lea     rcx, [rbp+TlsValue]; this
0x18002d793  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18002d798  test    eax, eax
0x18002d79a  jz      short loc_18002D7FE
0x18002d79c  test    byte ptr cs:_bidGblFlags, 2
0x18002d7a3  jz      loc_18002D8DA
0x18002d7a9  lea     rcx, [rbx+138h]; this
0x18002d7b0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d7b5  cmp     eax, 0FFFFFFFFh
0x18002d7b8  jz      short loc_18002D7EE
0x18002d7ba  lea     rcx, [rbx+138h]; this
0x18002d7c1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d7c6  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002d7cd  mov     [rsp+60h+var_40], 506h
0x18002d7d5  mov     r9d, eax
0x18002d7d8  lea     r8, aCrsetfieldRele_4; "<CRsetField::ReleaseAccessors|ADO|ERR> "...
0x18002d7df  mov     edx, 141809h
0x18002d7e4  call    _bidTraceW
0x18002d7e9  jmp     loc_18002D8DA
0x18002d7ee  mov     r9d, 506h
0x18002d7f4  mov     edx, 141809h
0x18002d7f9  jmp     loc_18002D8C6
0x18002d7fe  mov     [rbx+0E8h], rdi
0x18002d805  mov     [rbx+0F0h], di
0x18002d80c  mov     [rbx+100h], rdi
0x18002d813  mov     rdx, [rbx+0F8h]
0x18002d81a  test    rdx, rdx
0x18002d81d  jz      short loc_18002D839
0x18002d81f  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18002d826  call    cs:__imp_MpHeapFree
0x18002d82d  nop     dword ptr [rax+rax+00h]
0x18002d832  mov     [rbx+0F8h], rdi
0x18002d839  mov     rdx, [rbx+0A0h]
0x18002d840  test    rdx, rdx
0x18002d843  jz      loc_18002D8EC
0x18002d849  mov     rcx, [rbp+arg_10]
0x18002d84d  mov     rax, [rcx]
0x18002d850  xor     r8d, r8d
0x18002d853  mov     rax, [rax+30h]
0x18002d857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d85c  mov     [rbp+arg_0], eax
0x18002d85f  lea     rdx, [rbp+arg_0]; int *
0x18002d863  lea     rcx, [rbp+TlsValue]; this
0x18002d867  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18002d86c  test    eax, eax
0x18002d86e  jz      short loc_18002D8E5
0x18002d870  test    byte ptr cs:_bidGblFlags, 2
0x18002d877  jz      short loc_18002D8DA
0x18002d879  lea     rcx, [rbx+138h]; this
0x18002d880  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d885  cmp     eax, 0FFFFFFFFh
0x18002d888  jz      short loc_18002D8BB
0x18002d88a  lea     rcx, [rbx+138h]; this
0x18002d891  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d896  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002d89d  mov     [rsp+60h+var_40], 519h
0x18002d8a5  mov     r9d, eax
0x18002d8a8  lea     r8, aCrsetfieldRele_4; "<CRsetField::ReleaseAccessors|ADO|ERR> "...
0x18002d8af  mov     edx, 146409h
0x18002d8b4  call    _bidTraceW
0x18002d8b9  jmp     short loc_18002D8DA
0x18002d8bb  mov     r9d, 519h
0x18002d8c1  mov     edx, 146409h
0x18002d8c6  lea     r8, aCrsetfieldRele_1; "<CRsetField::ReleaseAccessors|ADO|ERR> "...
0x18002d8cd  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002d8d4  call    _bidTraceW
0x18002d8d9  nop
  ... truncated ...
```
