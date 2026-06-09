# CreateDCM(_GUID const &,IUnknown *,ulong,ushort *,CDPO *,CACMComPolyObject<CDCM> * *)

- ea: `0x180063e3c`
- end: `0x180064714`
- name: `?CreateDCM@@YAJAEBU_GUID@@PEAUIUnknown@@KPEAGPEAVCDPO@@PEAPEAV?$CACMComPolyObject@VCDCM@@@@@Z`
- size: `2264`
- prototype: `__int64 __usercall@<rax>(IID *rclsid@<rcx>, CDPO *, __int64)`
- caller_count: `4`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005bd4c`
- `0x18005c2ac`
- `0x180064720`
- `0x18006c5f0`

## callees

- `0x1800130d0`
- `0x180013870`
- `0x180014674`
- `0x180029560`
- `0x18002c060`
- `0x18002ec0c`
- `0x18005640c`
- `0x180063e3c`
- `0x180066770`
- `0x18006e3b0`
- `0x180073fc0`
- `0x18007e6ca`
- `0x18007e700`
- `0x180087010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180064193`
- `ole32!CoCreateInstance` at `0x180064193`

## string_xrefs

- `0x180063ecd`: `<CreateDCM|OLEDB|ERR> `
- `0x180063eeb`: `<CreateDCM|OLEDB|ERR> `
- `0x180063f6c`: `<CreateDCM|OLEDB|ERR> `
- `0x180063f8a`: `<CreateDCM|OLEDB|ERR> `
- `0x180064002`: `<CreateDCM|OLEDB|ERR> `
- `0x180064020`: `<CreateDCM|OLEDB|ERR> `
- `0x180064093`: `<CreateDCM|OLEDB|ERR> `
- `0x18006410f`: `<CreateDCM|OLEDB|ERR> `
- `0x18006412d`: `<CreateDCM|OLEDB|ERR> `
- `0x1800641b1`: `<CreateDCM|OLEDB|ERR> `
- `0x1800641cf`: `<CreateDCM|OLEDB|ERR> `
- `0x18006424b`: `<CreateDCM|OLEDB|ERR> `
- `0x180064269`: `<CreateDCM|OLEDB|ERR> `
- `0x1800642e1`: `<CreateDCM|OLEDB|ERR> `
- `0x1800642ff`: `<CreateDCM|OLEDB|ERR> `
- `0x1800643a3`: `<CreateDCM|OLEDB|ERR> `
- `0x1800643c1`: `<CreateDCM|OLEDB|ERR> `
- `0x1800644b5`: `<CreateDCM|OLEDB|ERR> `
- `0x18006453f`: `<CreateDCM|OLEDB|ERR> `
- `0x1800645c9`: `<CreateDCM|OLEDB|ERR> `
- `0x180063f06`: `<CreateDCM|Trace|HR> `
- `0x180063fa5`: `<CreateDCM|Trace|HR> `
- `0x18006403b`: `<CreateDCM|Trace|HR> `
- `0x1800640ae`: `<CreateDCM|Trace|HR> `
- `0x180064148`: `<CreateDCM|Trace|HR> `
- `0x1800641ea`: `<CreateDCM|Trace|HR> `
- `0x180064284`: `<CreateDCM|Trace|HR> `
- `0x18006431a`: `<CreateDCM|Trace|HR> `
- `0x1800643dc`: `<CreateDCM|Trace|HR> `
- `0x1800644d0`: `<CreateDCM|Trace|HR> `
- `0x18006455a`: `<CreateDCM|Trace|HR> `
- `0x1800645e4`: `<CreateDCM|Trace|HR> `
- `0x1800646d0`: `<CreateDCM|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CreateDCM(IID *rclsid, __int64 a2, DWORD a3, __int64 a4, CDPO *a5, _QWORD *a6)
{
  int DCM; // edi
  __int64 v9; // rbx
  int v10; // edi
  int v11; // edi
  CCMProviderInfo *v12; // rcx
  int v13; // edi
  int v14; // edi
  HRESULT v15; // edi
  int v16; // edi
  int inited; // edi
  int v18; // edi
  int v19; // edi
  int v20; // edi
  unsigned int v22; // ebx
  LPUNKNOWN pUnkOuter; // [rsp+30h] [rbp-F8h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-F0h] BYREF
  __int64 v25; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v26; // [rsp+48h] [rbp-E0h] BYREF
  struct _GUID v27; // [rsp+50h] [rbp-D8h] BYREF
  int pExceptionObject; // [rsp+60h] [rbp-C8h] BYREF
  int v29; // [rsp+64h] [rbp-C4h] BYREF
  int v30; // [rsp+68h] [rbp-C0h] BYREF
  int v31; // [rsp+6Ch] [rbp-BCh] BYREF
  int v32; // [rsp+70h] [rbp-B8h] BYREF
  HRESULT v33; // [rsp+74h] [rbp-B4h] BYREF
  int v34; // [rsp+78h] [rbp-B0h] BYREF
  int v35; // [rsp+7Ch] [rbp-ACh] BYREF
  int v36; // [rsp+80h] [rbp-A8h] BYREF
  int v37; // [rsp+84h] [rbp-A4h] BYREF
  int v38; // [rsp+88h] [rbp-A0h] BYREF
  int v39; // [rsp+8Ch] [rbp-9Ch] BYREF
  unsigned int v40; // [rsp+90h] [rbp-98h] BYREF
  CCMProviderInfo *v41; // [rsp+98h] [rbp-90h] BYREF
  struct tagDBPROP v42; // [rsp+A0h] [rbp-88h] BYREF

  *(_QWORD *)&v27.Data1 = 0;
  v25 = 0;
  pUnkOuter = 0;
  ppv = 0;
  v26 = 0;
  try
  {
    DCM = CreateDCM();
    if ( DCM < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(DCM, L"<CreateDCM|OLEDB|ERR> ", 0x5FBu);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(DCM, L"<CreateDCM|OLEDB|ERR> ", 0x5FBu);
          if ( (bidGblFlags & 2) != 0 )
            DCM = bidTraceHR(off_1800C8440[0], 1567753, L"<CreateDCM|Trace|HR> ", (unsigned int)DCM);
        }
      }
      pExceptionObject = DCM;
      throw (long *)&pExceptionObject;
    }
    v9 = *(_QWORD *)&v27.Data1;
    v10 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&v27.Data1)(
            *(_QWORD *)&v27.Data1,
            &IID_IOuterUnknown,
            &v25);
    if ( v10 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v10, L"<CreateDCM|OLEDB|ERR> ", 0x601u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v10, L"<CreateDCM|OLEDB|ERR> ", 0x601u);
          if ( (bidGblFlags & 2) != 0 )
            v10 = bidTraceHR(off_1800C8440[0], 1573897, L"<CreateDCM|Trace|HR> ", (unsigned int)v10);
        }
      }
      v29 = v10;
      throw (long *)&v29;
    }
    v11 = (*(__int64 (__fastcall **)(__int64, LPUNKNOWN *))(*(_QWORD *)v25 + 24LL))(v25, &pUnkOuter);
    if ( v11 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v11, L"<CreateDCM|OLEDB|ERR> ", 0x603u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v11, L"<CreateDCM|OLEDB|ERR> ", 0x603u);
          if ( (bidGblFlags & 2) != 0 )
            v11 = bidTraceHR(off_1800C8440[0], 1575945, L"<CreateDCM|Trace|HR> ", (unsigned int)v11);
        }
      }
      v30 = v11;
      throw (long *)&v30;
    }
    if ( a5 )
    {
      v12 = (CCMProviderInfo *)*((_QWORD *)a5 + 15);
      if ( !v12 )
      {
        v13 = -2147418113;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147418113, L"<CreateDCM|OLEDB|ERR> ", 0x60Eu);
          if ( (bidGblFlags & 2) != 0 )
            v13 = bidTraceHR(off_1800C8440[0], 1587209, L"<CreateDCM|Trace|HR> ", 2147549183LL);
        }
        v31 = v13;
        throw (long *)&v31;
      }
      v14 = CCMProviderInfo::CreateProvider(v12, pUnkOuter, &IID_IUnknown, &ppv);
      if ( v14 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v14, L"<CreateDCM|OLEDB|ERR> ", 0x612u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v14, L"<CreateDCM|OLEDB|ERR> ", 0x612u);
            if ( (bidGblFlags & 2) != 0 )
              v14 = bidTraceHR(off_1800C8440[0], 1591305, L"<CreateDCM|Trace|HR> ", (unsigned int)v14);
          }
        }
        v32 = v14;
        throw (long *)&v32;
      }
    }
    else
    {
      v15 = CoCreateInstance(rclsid, pUnkOuter, a3, &IID_IUnknown, &ppv);
      if ( v15 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v15, L"<CreateDCM|OLEDB|ERR> ", 0x61Au);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v15, L"<CreateDCM|OLEDB|ERR> ", 0x61Au);
            if ( (bidGblFlags & 2) != 0 )
              v15 = bidTraceHR(off_1800C8440[0], 1599497, L"<CreateDCM|Trace|HR> ", (unsigned int)v15);
          }
        }
        v33 = v15;
        throw (long *)&v33;
      }
    }
    v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v9)(v9, &IID_IService, &v26);
    if ( v16 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v16, L"<CreateDCM|OLEDB|ERR> ", 0x620u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v16, L"<CreateDCM|OLEDB|ERR> ", 0x620u);
          if ( (bidGblFlags & 2) != 0 )
            v16 = bidTraceHR(off_1800C8440[0], 1605641, L"<CreateDCM|Trace|HR> ", (unsigned int)v16);
        }
      }
      v34 = v16;
      throw (long *)&v34;
    }
    inited = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v26 + 24LL))(v26, ppv);
    if ( inited < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(inited, L"<CreateDCM|OLEDB|ERR> ", 0x621u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(inited, L"<CreateDCM|OLEDB|ERR> ", 0x621u);
          if ( (bidGblFlags & 2) != 0 )
            inited = bidTraceHR(off_1800C8440[0], 1606665, L"<CreateDCM|Trace|HR> ", (unsigned int)inited);
        }
      }
      v35 = inited;
      throw (long *)&v35;
    }
    if ( a5 )
    {
      v41 = 0;
      (*(void (__fastcall **)(char *, CCMProviderInfo **))(*((_QWORD *)a5 + 4) + 40LL))((char *)a5 + 32, &v41);
      inited = CDCM::StoreProviderInitInfo((CDCM *)(v9 + 24), v41);
      if ( inited < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(inited, L"<CreateDCM|OLEDB|ERR> ", 0x62Bu);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(inited, L"<CreateDCM|OLEDB|ERR> ", 0x62Bu);
            if ( (bidGblFlags & 2) != 0 )
              inited = bidTraceHR(off_1800C8440[0], 1616905, L"<CreateDCM|Trace|HR> ", (unsigned int)inited);
          }
        }
        v36 = inited;
        throw (long *)&v36;
      }
      memset_0(&v42, 0, sizeof(v42));
      v42.dwPropertyID = 248;
      v42.dwOptions = 1;
      v42.colid = DB_NULLID;
      v42.vValue.vt = 3;
      v42.vValue.lVal = CDPO::GetOLEDBServices(a5);
      if ( (unsigned int)CDBPROPContainer::SetProperty((CDBPROPContainer *)(v9 + 744), &DBPROPSET_DBINIT, &v42, 0, 0) )
      {
        v18 = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147024882, L"<CreateDCM|OLEDB|ERR> ", 0x637u);
          if ( (bidGblFlags & 2) != 0 )
            v18 = bidTraceHR(off_1800C8440[0], 1629193, L"<CreateDCM|Trace|HR> ", 2147942414LL);
        }
        v37 = v18;
        throw (long *)&v37;
      }
      if ( (unsigned int)CDBPROPContainer::SetProperty((CDBPROPContainer *)(v9 + 544), &DBPROPSET_DBINIT, &v42, 0, 0) )
      {
        v19 = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147024882, L"<CreateDCM|OLEDB|ERR> ", 0x63Au);
          if ( (bidGblFlags & 2) != 0 )
            v19 = bidTraceHR(off_1800C8440[0], 1632265, L"<CreateDCM|Trace|HR> ", 2147942414LL);
        }
        v38 = v19;
        throw (long *)&v38;
      }
      if ( (unsigned int)CDBPROPContainer::SetProperty((CDBPROPContainer *)(v9 + 648), &DBPROPSET_DBINIT, &v42, 0, 0) )
      {
        v20 = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147024882, L"<CreateDCM|OLEDB|ERR> ", 0x63Du);
          if ( (bidGblFlags & 2) != 0 )
            v20 = bidTraceHR(off_1800C8440[0], 1635337, L"<CreateDCM|Trace|HR> ", 2147942414LL);
        }
        v39 = v20;
        throw (long *)&v39;
      }
      if ( (v42.vValue.bVal & 4) != 0 )
      {
        v27 = IID_IDBProperties;
        CAcm::InsertDynamicInterface((CAcm *)(v9 + 24), &v27);
      }
      if ( v41 )
        CCMProviderInfo::Release(v41);
    }
    *(_QWORD *)(v9 + 488) = a5;
    *a6 = v9;
    *(_QWORD *)&v27.Data1 = 0;
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( pUnkOuter )
      ((void (__fastcall *)(LPUNKNOWN))pUnkOuter->lpVtbl->Release)(pUnkOuter);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  catch ( long v40 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1800C8958[0] )
    {
      v22 = v40;
      bidTraceA(off_1800C8440[0], 1677312, off_1800C8958[0], v40);
    }
    else
    {
      v22 = v40;
    }
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( pUnkOuter )
      ((void (__fastcall *)(LPUNKNOWN))pUnkOuter->lpVtbl->Release)(pUnkOuter);
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    if ( *(_QWORD *)&v27.Data1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v27.Data1 + 16LL))(*(_QWORD *)&v27.Data1);
    v27.Data1 = v22;
    inited = v22;
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C8440[0], 1701897, L"<CreateDCM|Trace|HR> ", (unsigned int)inited);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180063e3c  mov     [rsp+arg_18], rbx
0x180063e41  push    rsi
0x180063e42  push    rdi
0x180063e43  push    r12
0x180063e45  push    r14
0x180063e47  push    r15
0x180063e49  sub     rsp, 100h
0x180063e50  mov     rax, cs:__security_cookie
0x180063e57  xor     rax, rsp
0x180063e5a  mov     [rsp+128h+var_38], rax
0x180063e62  mov     r15d, r8d
0x180063e65  mov     rax, rdx
0x180063e68  mov     r14, rcx
0x180063e6b  mov     rsi, [rsp+128h+arg_20]
0x180063e73  mov     r12, [rsp+128h+arg_28]
0x180063e7b  mov     qword ptr [rsp+128h+var_D8.Data1], 0
0x180063e84  mov     [rsp+128h+var_E8], 0
0x180063e8d  mov     [rsp+128h+pUnkOuter], 0
0x180063e96  mov     [rsp+128h+var_F0], 0
0x180063e9f  mov     [rsp+128h+var_E0], 0
0x180063ea8  lea     rdx, [rsp+128h+var_D8]
0x180063ead  mov     rcx, rax
0x180063eb0  call    _CreateDCM
0x180063eb5  mov     edi, eax
0x180063eb7  test    eax, eax
0x180063eb9  jns     short loc_180063F35
0x180063ebb  mov     eax, cs:_bidGblFlags
0x180063ec1  mov     bl, 2
0x180063ec3  test    bl, al
0x180063ec5  jz      short loc_180063F20
0x180063ec7  mov     r8d, 5FBh; unsigned int
0x180063ecd  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x180063ed4  mov     ecx, edi; int
0x180063ed6  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180063edb  mov     eax, cs:_bidGblFlags
0x180063ee1  test    bl, al
0x180063ee3  jz      short loc_180063F20
0x180063ee5  mov     r8d, 5FBh; unsigned int
0x180063eeb  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x180063ef2  mov     ecx, edi; int
0x180063ef4  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180063ef9  mov     eax, cs:_bidGblFlags
0x180063eff  test    bl, al
0x180063f01  jz      short loc_180063F20
0x180063f03  mov     r9d, edi
0x180063f06  lea     r8, aCreatedcmTrace; "<CreateDCM|Trace|HR> "
0x180063f0d  mov     edx, 17EC09h
0x180063f12  mov     rcx, cs:off_1800C8440; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180063f19  call    _bidTraceHR
0x180063f1e  mov     edi, eax
0x180063f20  mov     [rsp+128h+pExceptionObject], edi
0x180063f24  lea     rdx, _TI1J; pThrowInfo
0x180063f2b  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x180063f30  call    _CxxThrowException_0
0x180063f35  mov     rbx, qword ptr [rsp+128h+var_D8.Data1]
0x180063f3a  mov     rax, [rbx]
0x180063f3d  lea     r8, [rsp+128h+var_E8]
0x180063f42  lea     rdx, IID_IOuterUnknown
0x180063f49  mov     rcx, rbx
0x180063f4c  mov     rax, [rax]
0x180063f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f54  mov     edi, eax
0x180063f56  test    eax, eax
0x180063f58  jns     short loc_180063FD4
0x180063f5a  mov     eax, cs:_bidGblFlags
0x180063f60  mov     bl, 2
0x180063f62  test    bl, al
0x180063f64  jz      short loc_180063FBF
0x180063f66  mov     r8d, 601h; unsigned int
0x180063f6c  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x180063f73  mov     ecx, edi; int
0x180063f75  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180063f7a  mov     eax, cs:_bidGblFlags
0x180063f80  test    bl, al
0x180063f82  jz      short loc_180063FBF
0x180063f84  mov     r8d, 601h; unsigned int
0x180063f8a  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x180063f91  mov     ecx, edi; int
0x180063f93  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180063f98  mov     eax, cs:_bidGblFlags
0x180063f9e  test    bl, al
0x180063fa0  jz      short loc_180063FBF
0x180063fa2  mov     r9d, edi
0x180063fa5  lea     r8, aCreatedcmTrace; "<CreateDCM|Trace|HR> "
0x180063fac  mov     edx, 180409h
0x180063fb1  mov     rcx, cs:off_1800C8440; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180063fb8  call    _bidTraceHR
0x180063fbd  mov     edi, eax
0x180063fbf  mov     [rsp+128h+var_C4], edi
0x180063fc3  lea     rdx, _TI1J; pThrowInfo
0x180063fca  lea     rcx, [rsp+128h+var_C4]; pExceptionObject
0x180063fcf  call    _CxxThrowException_0
0x180063fd4  mov     rcx, [rsp+128h+var_E8]
0x180063fd9  mov     rax, [rcx]
0x180063fdc  lea     rdx, [rsp+128h+pUnkOuter]
0x180063fe1  mov     rax, [rax+18h]
0x180063fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063fea  mov     edi, eax
0x180063fec  test    eax, eax
0x180063fee  jns     short loc_18006406A
0x180063ff0  mov     eax, cs:_bidGblFlags
0x180063ff6  mov     bl, 2
0x180063ff8  test    bl, al
0x180063ffa  jz      short loc_180064055
0x180063ffc  mov     r8d, 603h; unsigned int
0x180064002  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x180064009  mov     ecx, edi; int
0x18006400b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180064010  mov     eax, cs:_bidGblFlags
0x180064016  test    bl, al
0x180064018  jz      short loc_180064055
0x18006401a  mov     r8d, 603h; unsigned int
0x180064020  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x180064027  mov     ecx, edi; int
0x180064029  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006402e  mov     eax, cs:_bidGblFlags
0x180064034  test    bl, al
0x180064036  jz      short loc_180064055
0x180064038  mov     r9d, edi
0x18006403b  lea     r8, aCreatedcmTrace; "<CreateDCM|Trace|HR> "
0x180064042  mov     edx, 180C09h
0x180064047  mov     rcx, cs:off_1800C8440; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006404e  call    _bidTraceHR
0x180064053  mov     edi, eax
0x180064055  mov     [rsp+128h+var_C0], edi
0x180064059  lea     rdx, _TI1J; pThrowInfo
0x180064060  lea     rcx, [rsp+128h+var_C0]; pExceptionObject
0x180064065  call    _CxxThrowException_0
0x18006406a  test    rsi, rsi
0x18006406d  jz      loc_180064177
0x180064073  mov     rcx, [rsi+78h]; this
0x180064077  test    rcx, rcx
0x18006407a  jnz     short loc_1800640DD
0x18006407c  mov     eax, cs:_bidGblFlags
0x180064082  mov     bl, 2
0x180064084  mov     edi, 8000FFFFh
0x180064089  test    bl, al
0x18006408b  jz      short loc_1800640C8
0x18006408d  mov     r8d, 60Eh; unsigned int
0x180064093  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x18006409a  mov     ecx, edi; int
0x18006409c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800640a1  mov     eax, cs:_bidGblFlags
0x1800640a7  test    bl, al
0x1800640a9  jz      short loc_1800640C8
0x1800640ab  mov     r9d, edi
0x1800640ae  lea     r8, aCreatedcmTrace; "<CreateDCM|Trace|HR> "
0x1800640b5  mov     edx, 183809h
0x1800640ba  mov     rcx, cs:off_1800C8440; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800640c1  call    _bidTraceHR
0x1800640c6  mov     edi, eax
0x1800640c8  mov     [rsp+128h+var_BC], edi
0x1800640cc  lea     rdx, _TI1J; pThrowInfo
0x1800640d3  lea     rcx, [rsp+128h+var_BC]; pExceptionObject
0x1800640d8  call    _CxxThrowException_0
0x1800640dd  lea     r9, [rsp+128h+var_F0]; ppv
0x1800640e2  lea     r8, IID_IUnknown; riid
0x1800640e9  mov     rdx, [rsp+128h+pUnkOuter]; pUnkOuter
0x1800640ee  call    ?CreateProvider@CCMProviderInfo@@QEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z; CCMProviderInfo::CreateProvider(IUnknown *,_GUID const &,void * *)
0x1800640f3  mov     edi, eax
0x1800640f5  test    eax, eax
0x1800640f7  jns     loc_180064219
0x1800640fd  mov     eax, cs:_bidGblFlags
0x180064103  mov     bl, 2
0x180064105  test    bl, al
0x180064107  jz      short loc_180064162
0x180064109  mov     r8d, 612h; unsigned int
0x18006410f  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x180064116  mov     ecx, edi; int
0x180064118  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006411d  mov     eax, cs:_bidGblFlags
0x180064123  test    bl, al
0x180064125  jz      short loc_180064162
0x180064127  mov     r8d, 612h; unsigned int
0x18006412d  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x180064134  mov     ecx, edi; int
0x180064136  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006413b  mov     eax, cs:_bidGblFlags
0x180064141  test    bl, al
0x180064143  jz      short loc_180064162
0x180064145  mov     r9d, edi
0x180064148  lea     r8, aCreatedcmTrace; "<CreateDCM|Trace|HR> "
0x18006414f  mov     edx, 184809h
0x180064154  mov     rcx, cs:off_1800C8440; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006415b  call    _bidTraceHR
0x180064160  mov     edi, eax
0x180064162  mov     [rsp+128h+var_B8], edi
0x180064166  lea     rdx, _TI1J; pThrowInfo
0x18006416d  lea     rcx, [rsp+128h+var_B8]; pExceptionObject
0x180064172  call    _CxxThrowException_0
0x180064177  lea     rax, [rsp+128h+var_F0]
0x18006417c  mov     [rsp+128h+ppv], rax; ppv
0x180064181  lea     r9, IID_IUnknown; riid
0x180064188  mov     r8d, r15d; dwClsContext
0x18006418b  mov     rdx, [rsp+128h+pUnkOuter]; pUnkOuter
0x180064190  mov     rcx, r14; rclsid
0x180064193  call    cs:__imp_CoCreateInstance
0x180064199  mov     edi, eax
0x18006419b  test    eax, eax
0x18006419d  jns     short loc_180064219
0x18006419f  mov     eax, cs:_bidGblFlags
0x1800641a5  mov     bl, 2
0x1800641a7  test    bl, al
0x1800641a9  jz      short loc_180064204
0x1800641ab  mov     r8d, 61Ah; unsigned int
0x1800641b1  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x1800641b8  mov     ecx, edi; int
0x1800641ba  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800641bf  mov     eax, cs:_bidGblFlags
0x1800641c5  test    bl, al
0x1800641c7  jz      short loc_180064204
0x1800641c9  mov     r8d, 61Ah; unsigned int
0x1800641cf  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x1800641d6  mov     ecx, edi; int
0x1800641d8  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800641dd  mov     eax, cs:_bidGblFlags
0x1800641e3  test    bl, al
0x1800641e5  jz      short loc_180064204
0x1800641e7  mov     r9d, edi
0x1800641ea  lea     r8, aCreatedcmTrace; "<CreateDCM|Trace|HR> "
0x1800641f1  mov     edx, 186809h
0x1800641f6  mov     rcx, cs:off_1800C8440; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800641fd  call    _bidTraceHR
0x180064202  mov     edi, eax
0x180064204  mov     [rsp+128h+var_B4], edi
0x180064208  lea     rdx, _TI1J; pThrowInfo
0x18006420f  lea     rcx, [rsp+128h+var_B4]; pExceptionObject
0x180064214  call    _CxxThrowException_0
0x180064219  mov     rax, [rbx]
0x18006421c  lea     r8, [rsp+128h+var_E0]
0x180064221  lea     rdx, IID_IService
0x180064228  mov     rcx, rbx
0x18006422b  mov     rax, [rax]
0x18006422e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064233  mov     edi, eax
0x180064235  test    eax, eax
0x180064237  jns     short loc_1800642B3
0x180064239  mov     eax, cs:_bidGblFlags
0x18006423f  mov     bl, 2
0x180064241  test    bl, al
0x180064243  jz      short loc_18006429E
0x180064245  mov     r8d, 620h; unsigned int
0x18006424b  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x180064252  mov     ecx, edi; int
0x180064254  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180064259  mov     eax, cs:_bidGblFlags
0x18006425f  test    bl, al
0x180064261  jz      short loc_18006429E
0x180064263  mov     r8d, 620h; unsigned int
0x180064269  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x180064270  mov     ecx, edi; int
0x180064272  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180064277  mov     eax, cs:_bidGblFlags
0x18006427d  test    bl, al
0x18006427f  jz      short loc_18006429E
0x180064281  mov     r9d, edi
0x180064284  lea     r8, aCreatedcmTrace; "<CreateDCM|Trace|HR> "
0x18006428b  mov     edx, 188009h
0x180064290  mov     rcx, cs:off_1800C8440; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180064297  call    _bidTraceHR
0x18006429c  mov     edi, eax
0x18006429e  mov     [rsp+128h+var_B0], edi
0x1800642a2  lea     rdx, _TI1J; pThrowInfo
0x1800642a9  lea     rcx, [rsp+128h+var_B0]; pExceptionObject
0x1800642ae  call    _CxxThrowException_0
0x1800642b3  mov     rcx, [rsp+128h+var_E0]
0x1800642b8  mov     rax, [rcx]
0x1800642bb  mov     rdx, [rsp+128h+var_F0]
0x1800642c0  mov     rax, [rax+18h]
0x1800642c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800642c9  mov     edi, eax
0x1800642cb  test    eax, eax
0x1800642cd  jns     short loc_180064349
0x1800642cf  mov     eax, cs:_bidGblFlags
0x1800642d5  mov     bl, 2
0x1800642d7  test    bl, al
0x1800642d9  jz      short loc_180064334
0x1800642db  mov     r8d, 621h; unsigned int
0x1800642e1  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x1800642e8  mov     ecx, edi; int
0x1800642ea  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800642ef  mov     eax, cs:_bidGblFlags
0x1800642f5  test    bl, al
0x1800642f7  jz      short loc_180064334
0x1800642f9  mov     r8d, 621h; unsigned int
0x1800642ff  lea     rdx, aCreatedcmOledb_0; "<CreateDCM|OLEDB|ERR> "
0x180064306  mov     ecx, edi; int
0x180064308  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006430d  mov     eax, cs:_bidGblFlags
0x180064313  test    bl, al
0x180064315  jz      short loc_180064334
0x180064317  mov     r9d, edi
0x18006431a  lea     r8, aCreatedcmTrace; "<CreateDCM|Trace|HR> "
0x180064321  mov     edx, 188409h
0x180064326  mov     rcx, cs:off_1800C8440; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006432d  call    _bidTraceHR
0x180064332  mov     edi, eax
0x180064334  mov     [rsp+128h+var_AC], edi
0x180064338  lea     rdx, _TI1J; pThrowInfo
0x18006433f  lea     rcx, [rsp+128h+var_AC]; pExceptionObject
  ... truncated ...
```
