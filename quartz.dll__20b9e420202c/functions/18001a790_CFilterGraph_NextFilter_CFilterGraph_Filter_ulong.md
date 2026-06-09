# CFilterGraph::NextFilter(CFilterGraph::Filter &,ulong)

- ea: `0x18001a790`
- end: `0x18001ad47`
- name: `?NextFilter@CFilterGraph@@AEAAXAEAVFilter@1@K@Z`
- size: `1463`
- prototype: `void __fastcall(CFilterGraph *__hidden this, struct Filter *, unsigned int)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001a404`
- `0x180029d8c`

## callees

- `0x18001a790`
- `0x180020d1c`
- `0x1800240d0`
- `0x18002cffc`
- `0x180038458`
- `0x1800388a0`
- `0x1800689c0`
- `0x180068b74`
- `0x180068efc`
- `0x180068fb0`
- `0x18006901c`
- `0x18006a0c8`
- `0x18006b4a4`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001ac0d`
- `KERNEL32!LeaveCriticalSection` at `0x18001ac9c`
- `KERNEL32!LeaveCriticalSection` at `0x18001ac0d`
- `KERNEL32!LeaveCriticalSection` at `0x18001ac9c`
- `KERNEL32!EnterCriticalSection` at `0x18001ab79`
- `KERNEL32!EnterCriticalSection` at `0x18001ab79`
- `ole32!CoTaskMemFree` at `0x18001a944`
- `ole32!CoTaskMemFree` at `0x18001a944`
- `ole32!CLSIDFromString` at `0x18001ab1a`
- `ole32!CLSIDFromString` at `0x18001ab1a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ab2c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ab2c`

## string_xrefs

- `0x18001aae2`: `CLSID`

## pseudocode

```c
void __fastcall CFilterGraph::NextFilter(struct IGraphConfig *this, struct Filter *a2, char a3)
{
  CEnumCachedFilters *v6; // rax
  struct FilterVtbl *v7; // rax
  unsigned int v8; // edx
  struct FilterVtbl *lpVtbl; // rcx
  struct FilterVtbl *v10; // rdx
  HRESULT (__stdcall *QueryInterface)(Filter *, const IID *const, void **); // rcx
  struct FilterVtbl *v12; // rsi
  CEnumCachedFilters *v13; // rcx
  struct FilterVtbl *v14; // rcx
  struct FilterVtbl *v15; // rcx
  struct FilterVtbl *v16; // rcx
  struct FilterVtbl *v17; // rcx
  struct IGraphConfigVtbl *v18; // rcx
  int v19; // edi
  struct FilterVtbl *v20; // rcx
  struct IMoniker *v21; // rcx
  struct IMonikerVtbl *v22; // rax
  HRESULT v23; // edi
  __int64 v24; // rdx
  __int64 v25; // rcx
  _QWORD *i; // rcx
  __int64 v27; // rax
  char *v28; // rax
  int v29; // edi
  __int64 v30; // rcx
  struct IMoniker *v31; // rcx
  struct FilterVtbl *Name; // rax
  __int64 v33; // [rsp+20h] [rbp-99h]
  int v34; // [rsp+90h] [rbp-29h] BYREF
  struct FilterVtbl *v35; // [rsp+98h] [rbp-21h] BYREF
  struct IMoniker *v36; // [rsp+A0h] [rbp-19h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v38; // [rsp+B8h] [rbp-1h]
  void **v39; // [rsp+C0h] [rbp+7h]
  GUID pclsid; // [rsp+C8h] [rbp+Fh] BYREF

  LOBYTE(a2[15].lpVtbl) = 0;
  if ( !LODWORD(a2->lpVtbl) )
  {
    LODWORD(a2->lpVtbl) = 2;
    v34 = 0;
    v6 = (CEnumCachedFilters *)operator new(0x10u);
    if ( !v6 )
    {
      a2[10].lpVtbl = 0;
      goto LABEL_7;
    }
    v7 = (struct FilterVtbl *)CEnumCachedFilters::CEnumCachedFilters(v6, this + 85, &v34);
    a2[10].lpVtbl = v7;
    if ( !v7 )
    {
LABEL_7:
      a2[10].lpVtbl = 0;
      LODWORD(a2->lpVtbl) = 4;
      return;
    }
    if ( v34 < 0 )
    {
      CEnumCachedFilters::`scalar deleting destructor'((CEnumCachedFilters *)v7, v8);
      goto LABEL_7;
    }
  }
  lpVtbl = a2[8].lpVtbl;
  if ( lpVtbl )
  {
    (*((void (__fastcall **)(struct FilterVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
    a2[8].lpVtbl = 0;
  }
  if ( LODWORD(a2->lpVtbl) == 2 )
  {
    v10 = a2[10].lpVtbl;
    QueryInterface = v10->QueryInterface;
    if ( v10->QueryInterface )
    {
      v10->QueryInterface = (HRESULT (__stdcall *)(Filter *, const IID *const, void **))*((_QWORD *)QueryInterface + 1);
      v12 = (struct FilterVtbl *)*((_QWORD *)QueryInterface + 2);
      if ( v12 )
      {
        (*((void (__fastcall **)(_QWORD))v12->QueryInterface + 1))(*((_QWORD *)QueryInterface + 2));
        a2[8].lpVtbl = v12;
        return;
      }
    }
    v13 = (CEnumCachedFilters *)a2[10].lpVtbl;
    if ( v13 )
      CEnumCachedFilters::`scalar deleting destructor'(v13, (unsigned int)v10);
    a2[10].lpVtbl = 0;
    if ( (a3 & 4) != 0 )
      goto LABEL_68;
    LODWORD(a2->lpVtbl) = 1;
    if ( (int)CFilterGraph::EnumFilters((CFilterGraph *)this, (struct IEnumFilters **)&a2[9]) < 0 )
      goto LABEL_68;
  }
  if ( LODWORD(a2->lpVtbl) == 1 )
  {
    v14 = a2[9].lpVtbl;
    v34 = 0;
    v35 = 0;
    (*((void (__fastcall **)(struct FilterVtbl *, __int64, struct FilterVtbl **, int *))v14->QueryInterface + 3))(
      v14,
      1,
      &v35,
      &v34);
    if ( v34 == 1 )
    {
      a2[8].lpVtbl = v35;
      return;
    }
    (*((void (__fastcall **)(struct FilterVtbl *))a2[9].lpVtbl->QueryInterface + 2))(a2[9].lpVtbl);
    a2[9].lpVtbl = 0;
    if ( !LODWORD(a2[4].lpVtbl)
      || (LODWORD(a2->lpVtbl) = 3, (int)CFilterGraph::NextFilterHelper((CFilterGraph *)this, a2) < 0) )
    {
LABEL_68:
      LODWORD(a2->lpVtbl) = 4;
      return;
    }
  }
  v15 = a2[7].lpVtbl;
  v34 = 0;
  v36 = 0;
  if ( v15 )
  {
    CoTaskMemFree(v15);
    a2[7].lpVtbl = 0;
  }
  v16 = a2[1].lpVtbl;
  if ( v16 )
  {
    (*((void (__fastcall **)(struct FilterVtbl *))v16->QueryInterface + 2))(v16);
    a2[1].lpVtbl = 0;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v17 = a2[2].lpVtbl;
        v34 = 0;
        if ( (*((unsigned int (__fastcall **)(struct FilterVtbl *, __int64, struct IMoniker **, int *))v17->QueryInterface
              + 3))(
               v17,
               1,
               &v36,
               &v34) != -2147220989 )
          break;
        (*((void (__fastcall **)(struct FilterVtbl *))a2[2].lpVtbl->QueryInterface + 2))(a2[2].lpVtbl);
        a2[2].lpVtbl = 0;
        v18 = this[54].lpVtbl;
        v35 = 0;
        if ( (*(int (__fastcall **)(struct IGraphConfigVtbl *, GUID *, struct FilterVtbl **))v18->QueryInterface)(
               v18,
               &IID_IFilterMapper2,
               &v35) >= 0 )
        {
          LODWORD(v33) = 2097153;
          v19 = (*((__int64 (__fastcall **)(struct FilterVtbl *, struct Filter *, _QWORD, _QWORD, __int64, _DWORD, _DWORD, struct FilterVtbl *, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD))v35->QueryInterface
                 + 6))(
                  v35,
                  a2 + 2,
                  0,
                  0,
                  v33,
                  a2[3].lpVtbl,
                  a2[6].lpVtbl,
                  a2[5].lpVtbl,
                  0,
                  0,
                  0,
                  HIDWORD(a2[3].lpVtbl),
                  0,
                  0,
                  0,
                  0);
          (*((void (__fastcall **)(struct FilterVtbl *))v35->QueryInterface + 2))(v35);
          if ( v19 >= 0 )
            continue;
        }
        goto LABEL_66;
      }
      if ( v34 )
        break;
      if ( !BYTE1(a2[15].lpVtbl) )
        goto LABEL_68;
      v20 = a2[2].lpVtbl;
      BYTE1(a2[15].lpVtbl) = 0;
      HIDWORD(a2[15].lpVtbl) = 0;
      (*((void (__fastcall **)(struct FilterVtbl *))v20->QueryInterface + 5))(v20);
    }
    if ( v34 != 1 )
      goto LABEL_68;
    v21 = v36;
    ++HIDWORD(a2[15].lpVtbl);
    pclsid = 0;
    v22 = v21->lpVtbl;
    v35 = 0;
    v23 = ((__int64 (__fastcall *)(struct IMoniker *, _QWORD, _QWORD, GUID *, struct FilterVtbl **))v22->BindToStorage)(
            v21,
            0,
            0,
            &IID_IPropertyBag,
            &v35);
    if ( v23 >= 0 )
    {
      v38 = 0;
      lpsz[0] = (LPCOLESTR)8;
      lpsz[1] = 0;
      v23 = (*((__int64 (__fastcall **)(struct FilterVtbl *, const unsigned __int16 *, LPCOLESTR *, _QWORD))v35->QueryInterface
             + 3))(
              v35,
              L"CLSID",
              lpsz,
              0);
      if ( v23 >= 0 )
      {
        v23 = CLSIDFromString(lpsz[1], &pclsid);
        SysFreeString((BSTR)lpsz[1]);
      }
      (*((void (__fastcall **)(struct FilterVtbl *))v35->QueryInterface + 2))(v35);
    }
    if ( v23 < 0 )
      break;
    _InterlockedIncrement(&CBaseObject::m_cObjects);
    lpsz[0] = (LPCOLESTR)&CPluginControl::`vftable'{for `CUnknown'};
    lpsz[1] = (LPCOLESTR)lpsz;
    LODWORD(v38) = 0;
    v39 = &CPluginControl::`vftable'{for `IAMPluginControl'};
    EnterCriticalSection(&g_Plugins);
    if ( !dword_1801A1D18 )
    {
      if ( CPreferredList::InitializeFromRegistry((CPreferredList *)&qword_1801A1CF8) < 0
        || (int)CDisabledList::InitializeFromRegistry((CDisabledList *)&Block) < 0 )
      {
        LeaveCriticalSection(&g_Plugins);
        goto LABEL_52;
      }
      dword_1801A1D18 = 1;
      if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 2) != 0 )
        McTemplateU0qq_EventWriteTransfer(v25, v24, HIDWORD(qword_1801A1D00), HIDWORD(qword_1801A1D10));
    }
    for ( i = (_QWORD *)Block; i; i = (_QWORD *)*i )
    {
      v27 = i[1] - *(_QWORD *)&pclsid.Data1;
      if ( !v27 )
        v27 = i[2] - *(_QWORD *)pclsid.Data4;
      if ( !v27 )
      {
        v29 = 0;
        goto LABEL_60;
      }
    }
    v29 = -2147023728;
LABEL_60:
    if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 8) != 0 )
      McTemplateU0jt_EventWriteTransfer(i, QueryDisabledEventDesc, &pclsid, v29 >= 0);
    LeaveCriticalSection(&g_Plugins);
    if ( v29 < 0 )
    {
LABEL_52:
      _InterlockedDecrement(&CBaseObject::m_cObjects);
      if ( !BYTE1(a2[15].lpVtbl) )
        break;
      v28 = (char *)a2[11].lpVtbl - *(_QWORD *)&pclsid.Data1;
      if ( !v28 )
        v28 = (char *)a2[12].lpVtbl - *(_QWORD *)pclsid.Data4;
      if ( !v28 )
      {
        LOBYTE(a2[15].lpVtbl) = 1;
        break;
      }
      if ( !HIDWORD(a2[3].lpVtbl) )
        break;
      ((void (__fastcall *)(struct IMoniker *))v36->lpVtbl->Release)(v36);
      v36 = 0;
    }
    else
    {
      _InterlockedDecrement(&CBaseObject::m_cObjects);
      ((void (__fastcall *)(struct IMoniker *))v36->lpVtbl->Release)(v36);
      v36 = 0;
      if ( (Microsoft_Windows_DirectShow_CoreEnableBits & 4) != 0 )
        McTemplateU0j_EventWriteTransfer(v30, UseDontUseEventDesc, &pclsid);
    }
  }
LABEL_66:
  if ( v34 != 1 )
    goto LABEL_68;
  v31 = v36;
  a2[1].lpVtbl = (struct FilterVtbl *)v36;
  Name = (struct FilterVtbl *)MonGetName(v31);
  a2[7].lpVtbl = Name;
  if ( !Name )
    goto LABEL_68;
}

```

## disassembly

```asm
0x18001a790  push    rbp
0x18001a792  push    rbx
0x18001a793  push    rdi
0x18001a794  push    r14
0x18001a796  push    r15
0x18001a798  lea     rbp, [rsp-37h]
0x18001a79d  sub     rsp, 0F0h
0x18001a7a4  mov     rax, cs:__security_cookie
0x18001a7ab  xor     rax, rsp
0x18001a7ae  mov     [rbp+57h+var_38], rax
0x18001a7b2  xor     r15d, r15d
0x18001a7b5  mov     byte ptr [rdx+78h], 0
0x18001a7b9  mov     edi, r8d
0x18001a7bc  mov     rbx, rdx
0x18001a7bf  mov     r14, rcx
0x18001a7c2  cmp     [rdx], r15d
0x18001a7c5  jnz     short loc_18001A81F
0x18001a7c7  mov     ecx, 10h; Size
0x18001a7cc  mov     dword ptr [rdx], 2
0x18001a7d2  mov     [rbp+57h+var_80], r15d
0x18001a7d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001a7db  test    rax, rax
0x18001a7de  jz      short loc_18001A80C
0x18001a7e0  lea     rdx, [r14+2A8h]; struct IGraphConfig *
0x18001a7e7  mov     rcx, rax; this
0x18001a7ea  lea     r8, [rbp+57h+var_80]; int *
0x18001a7ee  call    ??0CEnumCachedFilters@@QEAA@PEAUIGraphConfig@@PEAJ@Z; CEnumCachedFilters::CEnumCachedFilters(IGraphConfig *,long *)
0x18001a7f3  mov     [rbx+50h], rax
0x18001a7f7  test    rax, rax
0x18001a7fa  jz      short loc_18001A810
0x18001a7fc  cmp     [rbp+57h+var_80], r15d
0x18001a800  jge     short loc_18001A81F
0x18001a802  mov     rcx, rax; this
0x18001a805  call    ??_GCEnumCachedFilters@@QEAAPEAXI@Z; CEnumCachedFilters::`scalar deleting destructor'(uint)
0x18001a80a  jmp     short loc_18001A810
0x18001a80c  mov     [rbx+50h], r15
0x18001a810  mov     [rbx+50h], r15
0x18001a814  mov     dword ptr [rbx], 4
0x18001a81a  jmp     loc_18001AD2B
0x18001a81f  mov     rcx, [rbx+40h]
0x18001a823  test    rcx, rcx
0x18001a826  jz      short loc_18001A838
0x18001a828  mov     rax, [rcx]
0x18001a82b  mov     rax, [rax+10h]
0x18001a82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a834  mov     [rbx+40h], r15
0x18001a838  cmp     dword ptr [rbx], 2
0x18001a83b  mov     [rsp+110h+arg_10], rsi
0x18001a843  mov     [rsp+110h+var_28], r12
0x18001a84b  mov     [rsp+110h+var_30], r13
0x18001a853  jnz     short loc_18001A8BF
0x18001a855  mov     rdx, [rbx+50h]; unsigned int
0x18001a859  mov     rcx, [rdx]
0x18001a85c  test    rcx, rcx
0x18001a85f  jz      short loc_18001A889
0x18001a861  mov     rax, [rcx+8]
0x18001a865  mov     [rdx], rax
0x18001a868  mov     rsi, [rcx+10h]
0x18001a86c  test    rsi, rsi
0x18001a86f  jz      short loc_18001A889
0x18001a871  mov     rax, [rsi]
0x18001a874  mov     rcx, rsi
0x18001a877  mov     rax, [rax+8]
0x18001a87b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a880  mov     [rbx+40h], rsi
0x18001a884  jmp     loc_18001AD13
0x18001a889  mov     rcx, [rbx+50h]; this
0x18001a88d  test    rcx, rcx
0x18001a890  jz      short loc_18001A897
0x18001a892  call    ??_GCEnumCachedFilters@@QEAAPEAXI@Z; CEnumCachedFilters::`scalar deleting destructor'(uint)
0x18001a897  mov     [rbx+50h], r15
0x18001a89b  test    dil, 4
0x18001a89f  jnz     loc_18001AD0D
0x18001a8a5  lea     rdx, [rbx+48h]; struct IEnumFilters **
0x18001a8a9  mov     dword ptr [rbx], 1
0x18001a8af  mov     rcx, r14; this
0x18001a8b2  call    ?EnumFilters@CFilterGraph@@UEAAJPEAPEAUIEnumFilters@@@Z; CFilterGraph::EnumFilters(IEnumFilters * *)
0x18001a8b7  test    eax, eax
0x18001a8b9  js      loc_18001AD0D
0x18001a8bf  cmp     dword ptr [rbx], 1
0x18001a8c2  jnz     short loc_18001A933
0x18001a8c4  mov     rcx, [rbx+48h]
0x18001a8c8  lea     r9, [rbp+57h+var_80]
0x18001a8cc  mov     [rbp+57h+var_80], r15d
0x18001a8d0  lea     r8, [rbp+57h+var_78]
0x18001a8d4  mov     [rbp+57h+var_78], r15
0x18001a8d8  mov     edx, 1
0x18001a8dd  mov     rax, [rcx]
0x18001a8e0  mov     rax, [rax+18h]
0x18001a8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8e9  cmp     [rbp+57h+var_80], 1
0x18001a8ed  jnz     short loc_18001A8FC
0x18001a8ef  mov     rax, [rbp+57h+var_78]
0x18001a8f3  mov     [rbx+40h], rax
0x18001a8f7  jmp     loc_18001AD13
0x18001a8fc  mov     rcx, [rbx+48h]
0x18001a900  mov     rax, [rcx]
0x18001a903  mov     rax, [rax+10h]
0x18001a907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a90c  mov     [rbx+48h], r15
0x18001a910  cmp     [rbx+20h], r15d
0x18001a914  jz      loc_18001AD0D
0x18001a91a  mov     rdx, rbx; struct Filter *
0x18001a91d  mov     dword ptr [rbx], 3
0x18001a923  mov     rcx, r14; this
0x18001a926  call    ?NextFilterHelper@CFilterGraph@@AEAAJAEAVFilter@1@@Z; CFilterGraph::NextFilterHelper(CFilterGraph::Filter &)
0x18001a92b  test    eax, eax
0x18001a92d  js      loc_18001AD0D
0x18001a933  mov     rcx, [rbx+38h]; pv
0x18001a937  mov     [rbp+57h+var_80], r15d
0x18001a93b  mov     [rbp+57h+var_70], r15
0x18001a93f  test    rcx, rcx
0x18001a942  jz      short loc_18001A954
0x18001a944  call    cs:__imp_CoTaskMemFree
0x18001a94b  nop     dword ptr [rax+rax+00h]
0x18001a950  mov     [rbx+38h], r15
0x18001a954  mov     rcx, [rbx+8]
0x18001a958  test    rcx, rcx
0x18001a95b  jz      short loc_18001A96D
0x18001a95d  mov     rax, [rcx]
0x18001a960  mov     rax, [rax+10h]
0x18001a964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a969  mov     [rbx+8], r15
0x18001a96d  mov     r12d, 8
0x18001a973  lea     r13, ??_7CPluginControl@@6BCUnknown@@@; const CPluginControl::`vftable'{for `CUnknown'}
0x18001a97a  mov     rcx, [rbx+10h]
0x18001a97e  lea     r9, [rbp+57h+var_80]
0x18001a982  mov     [rbp+57h+var_80], r15d
0x18001a986  lea     r8, [rbp+57h+var_70]
0x18001a98a  mov     edx, 1
0x18001a98f  mov     rax, [rcx]
0x18001a992  mov     rax, [rax+18h]
0x18001a996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a99b  cmp     eax, 80040203h
0x18001a9a0  jnz     loc_18001AA68
0x18001a9a6  mov     rcx, [rbx+10h]
0x18001a9aa  mov     rax, [rcx]
0x18001a9ad  mov     rax, [rax+10h]
0x18001a9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9b6  mov     [rbx+10h], r15
0x18001a9ba  lea     r8, [rbp+57h+var_78]
0x18001a9be  mov     rcx, [r14+1B0h]
0x18001a9c5  lea     rdx, IID_IFilterMapper2
0x18001a9cc  mov     [rbp+57h+var_78], r15
0x18001a9d0  mov     rax, [rcx]
0x18001a9d3  mov     rax, [rax]
0x18001a9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9db  test    eax, eax
0x18001a9dd  js      loc_18001ACF1
0x18001a9e3  mov     rdx, [rbx+28h]
0x18001a9e7  xor     r9d, r9d
0x18001a9ea  mov     rcx, [rbp+57h+var_78]
0x18001a9ee  xor     r8d, r8d
0x18001a9f1  mov     [rsp+110h+var_98], r15
0x18001a9f6  mov     [rsp+110h+var_A0], r15
0x18001a9fb  mov     [rsp+110h+var_A8], r15
0x18001aa00  mov     rax, [rcx]
0x18001aa03  mov     [rsp+110h+var_B0], r15d
0x18001aa08  mov     r10, [rax+30h]
0x18001aa0c  mov     eax, [rbx+1Ch]
0x18001aa0f  mov     [rsp+110h+var_B8], eax
0x18001aa13  mov     rax, r10
0x18001aa16  mov     [rsp+110h+var_C0], r15d
0x18001aa1b  mov     [rsp+110h+var_C8], r15
0x18001aa20  mov     [rsp+110h+var_D0], r15
0x18001aa25  mov     [rsp+110h+var_D8], rdx
0x18001aa2a  mov     edx, [rbx+30h]
0x18001aa2d  mov     [rsp+110h+var_E0], edx
0x18001aa31  mov     edx, [rbx+18h]
0x18001aa34  mov     [rsp+110h+var_E8], edx
0x18001aa38  lea     rdx, [rbx+10h]
0x18001aa3c  mov     dword ptr [rsp+110h+var_F0], 200001h
0x18001aa44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa49  mov     rcx, [rbp+57h+var_78]
0x18001aa4d  mov     edi, eax
0x18001aa4f  mov     rdx, [rcx]
0x18001aa52  mov     rax, [rdx+10h]
0x18001aa56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa5b  test    edi, edi
0x18001aa5d  jns     loc_18001A97A
0x18001aa63  jmp     loc_18001ACF1
0x18001aa68  mov     eax, [rbp+57h+var_80]
0x18001aa6b  test    eax, eax
0x18001aa6d  jnz     short loc_18001AA96
0x18001aa6f  cmp     [rbx+79h], r15b
0x18001aa73  jz      loc_18001AD0D
0x18001aa79  mov     rcx, [rbx+10h]
0x18001aa7d  mov     [rbx+79h], r15b
0x18001aa81  mov     [rbx+7Ch], r15d
0x18001aa85  mov     rax, [rcx]
0x18001aa88  mov     rax, [rax+28h]
0x18001aa8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aa91  jmp     loc_18001A97A
0x18001aa96  cmp     eax, 1
0x18001aa99  jnz     loc_18001AD0D
0x18001aa9f  mov     rcx, [rbp+57h+var_70]
0x18001aaa3  lea     rdx, [rbp+57h+var_78]
0x18001aaa7  inc     dword ptr [rbx+7Ch]
0x18001aaaa  lea     r9, IID_IPropertyBag
0x18001aab1  xorps   xmm0, xmm0
0x18001aab4  mov     [rsp+110h+var_F0], rdx
0x18001aab9  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18001aabd  mov     rax, [rcx]
0x18001aac0  xor     r8d, r8d
0x18001aac3  xor     edx, edx
0x18001aac5  mov     [rbp+57h+var_78], r15
0x18001aac9  mov     rax, [rax+48h]
0x18001aacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aad2  mov     edi, eax
0x18001aad4  test    eax, eax
0x18001aad6  js      short loc_18001AB48
0x18001aad8  mov     rcx, [rbp+57h+var_78]
0x18001aadc  lea     r8, [rbp+57h+lpsz]
0x18001aae0  xor     eax, eax
0x18001aae2  lea     rdx, aClsid; "CLSID"
0x18001aae9  mov     [rbp+57h+var_58], rax
0x18001aaed  xorps   xmm0, xmm0
0x18001aaf0  movups  xmmword ptr [rbp+57h+lpsz], xmm0
0x18001aaf4  mov     word ptr [rbp+57h+lpsz], r12w
0x18001aaf9  xor     r9d, r9d
0x18001aafc  mov     [rbp+57h+lpsz+8], r15
0x18001ab00  mov     rax, [rcx]
0x18001ab03  mov     rax, [rax+18h]
0x18001ab07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab0c  mov     edi, eax
0x18001ab0e  test    eax, eax
0x18001ab10  js      short loc_18001AB38
0x18001ab12  mov     rcx, [rbp+57h+lpsz+8]; lpsz
0x18001ab16  lea     rdx, [rbp+57h+pclsid]; pclsid
0x18001ab1a  call    cs:__imp_CLSIDFromString
0x18001ab21  nop     dword ptr [rax+rax+00h]
0x18001ab26  mov     rcx, [rbp+57h+lpsz+8]; bstrString
0x18001ab2a  mov     edi, eax
0x18001ab2c  call    cs:__imp_SysFreeString
0x18001ab33  nop     dword ptr [rax+rax+00h]
0x18001ab38  mov     rcx, [rbp+57h+var_78]
0x18001ab3c  mov     rax, [rcx]
0x18001ab3f  mov     rax, [rax+10h]
0x18001ab43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ab48  test    edi, edi
0x18001ab4a  js      loc_18001ACF1
0x18001ab50  lock inc cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18001ab57  lea     rax, [rbp+57h+lpsz]
0x18001ab5b  mov     [rbp+57h+lpsz], r13
0x18001ab5f  mov     [rbp+57h+lpsz+8], rax
0x18001ab63  lea     rcx, ?g_Plugins@@3VCPlugins@@A; lpCriticalSection
0x18001ab6a  lea     rax, ??_7CPluginControl@@6BIAMPluginControl@@@; const CPluginControl::`vftable'{for `IAMPluginControl'}
0x18001ab71  mov     dword ptr [rbp+57h+var_58], r15d
0x18001ab75  mov     [rbp+57h+var_50], rax
0x18001ab79  call    cs:__imp_EnterCriticalSection
0x18001ab80  nop     dword ptr [rax+rax+00h]
0x18001ab85  cmp     cs:dword_1801A1D18, r15d
0x18001ab8c  jnz     short loc_18001ABD4
0x18001ab8e  lea     rcx, qword_1801A1CF8; this
0x18001ab95  call    ?InitializeFromRegistry@CPreferredList@@QEAAJXZ; CPreferredList::InitializeFromRegistry(void)
0x18001ab9a  test    eax, eax
0x18001ab9c  js      short loc_18001AC06
0x18001ab9e  lea     rcx, Block; this
0x18001aba5  call    ?InitializeFromRegistry@CDisabledList@@QEAAJXZ; CDisabledList::InitializeFromRegistry(void)
0x18001abaa  test    eax, eax
0x18001abac  js      short loc_18001AC06
0x18001abae  test    cs:Microsoft_Windows_DirectShow_CoreEnableBits, 2
0x18001abb5  mov     cs:dword_1801A1D18, 1
0x18001abbf  jz      short loc_18001ABD4
0x18001abc1  mov     r9d, dword ptr cs:qword_1801A1D10+4
0x18001abc8  mov     r8d, dword ptr cs:qword_1801A1D00+4
0x18001abcf  call    McTemplateU0qq_EventWriteTransfer
0x18001abd4  mov     rcx, cs:Block
0x18001abdb  mov     r8, qword ptr [rbp+57h+pclsid.Data4]
0x18001abdf  mov     rdx, qword ptr [rbp+57h+pclsid.Data1]
0x18001abe3  test    rcx, rcx
0x18001abe6  jz      loc_18001AC6D
0x18001abec  mov     rax, [rcx+8]
0x18001abf0  sub     rax, rdx
0x18001abf3  jnz     short loc_18001ABFC
0x18001abf5  mov     rax, [rcx+10h]
0x18001abf9  sub     rax, r8
0x18001abfc  test    rax, rax
0x18001abff  jz      short loc_18001AC68
0x18001ac01  mov     rcx, [rcx]
0x18001ac04  jmp     short loc_18001ABE3
0x18001ac06  lea     rcx, ?g_Plugins@@3VCPlugins@@A; lpCriticalSection
0x18001ac0d  call    cs:__imp_LeaveCriticalSection
0x18001ac14  nop     dword ptr [rax+rax+00h]
0x18001ac19  lock dec cs:?m_cObjects@CBaseObject@@0JA; long CBaseObject::m_cObjects
0x18001ac20  cmp     [rbx+79h], r15b
0x18001ac24  jz      loc_18001ACF1
0x18001ac2a  mov     rax, [rbx+58h]
0x18001ac2e  sub     rax, qword ptr [rbp+57h+pclsid.Data1]
0x18001ac32  jnz     short loc_18001AC3C
0x18001ac34  mov     rax, [rbx+60h]
0x18001ac38  sub     rax, qword ptr [rbp+57h+pclsid.Data4]
0x18001ac3c  test    rax, rax
0x18001ac3f  jz      loc_18001ACED
0x18001ac45  cmp     [rbx+1Ch], r15d
0x18001ac49  jz      loc_18001ACF1
0x18001ac4f  mov     rcx, [rbp+57h+var_70]
0x18001ac53  mov     rax, [rcx]
0x18001ac56  mov     rax, [rax+10h]
0x18001ac5a  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
