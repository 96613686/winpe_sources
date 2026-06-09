# CMultipleResults<CRCM>::DoGetResult(IUnknown *,__int64,_GUID const &,__int64 *,IUnknown * *,IMultipleResults *,IUnknown *)

- ea: `0x180035af4`
- end: `0x1800364f9`
- name: `?DoGetResult@?$CMultipleResults@VCRCM@@@@QEAAJPEAUIUnknown@@_JAEBU_GUID@@PEA_JPEAPEAU2@PEAUIMultipleResults@@0@Z`
- size: `2565`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, struct IUnknown **, __int64, struct IUnknown *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002d190`

## callees

- `0x1800100c4`
- `0x180013870`
- `0x180029560`
- `0x18002bc80`
- `0x18002d3bc`
- `0x18002ec0c`
- `0x1800324c8`
- `0x180035af4`
- `0x180061814`
- `0x18006e3b0`
- `0x180087010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x180036133`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180036133`
- `ole32!CoCreateInstance` at `0x180035cf0`
- `ole32!CoCreateInstance` at `0x180035cf0`

## pseudocode

```c
__int64 __fastcall CMultipleResults<CRCM>::DoGetResult(
        __int64 a1,
        struct IUnknown *a2,
        __int64 a3,
        const struct _GUID *a4,
        __int64 a5,
        struct IUnknown **a6,
        __int64 a7,
        struct IUnknown *a8)
{
  int inserted; // edi
  int v10; // esi
  __int64 v11; // r14
  __int64 v12; // r12
  struct IUnknown *v13; // r13
  __int64 v14; // r15
  int v15; // eax
  HRESULT v16; // edi
  int v17; // edi
  int v18; // edi
  int v19; // edi
  unsigned int v20; // r13d
  struct tagDBPROPSET *v21; // r14
  int v22; // esi
  char v23; // cl
  char v24; // r9
  char v25; // r10
  unsigned int v26; // r8d
  DBPROP *rgProperties; // rax
  ULONG i; // edx
  struct IUnknown **v29; // rsi
  const struct _GUID *v30; // r15
  int v31; // eax
  unsigned int v32; // r14d
  int v34; // ebx
  int v35; // [rsp+40h] [rbp-C8h]
  struct IUnknown *v36; // [rsp+48h] [rbp-C0h] BYREF
  IErrorInfo *pperrinfo; // [rsp+50h] [rbp-B8h] BYREF
  int v38; // [rsp+58h] [rbp-B0h]
  LPVOID ppv; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+68h] [rbp-A0h] BYREF
  LPUNKNOWN pUnkOuter; // [rsp+70h] [rbp-98h] BYREF
  __int64 v42; // [rsp+78h] [rbp-90h]
  __int64 v43; // [rsp+80h] [rbp-88h] BYREF
  int pExceptionObject; // [rsp+88h] [rbp-80h] BYREF
  HRESULT v45; // [rsp+8Ch] [rbp-7Ch] BYREF
  int v46; // [rsp+90h] [rbp-78h] BYREF
  int v47; // [rsp+94h] [rbp-74h] BYREF
  int v48; // [rsp+98h] [rbp-70h] BYREF
  int v49; // [rsp+9Ch] [rbp-6Ch] BYREF
  int v50; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v51; // [rsp+A4h] [rbp-64h] BYREF
  int v52; // [rsp+A8h] [rbp-60h] BYREF
  int v53; // [rsp+ACh] [rbp-5Ch] BYREF
  unsigned int v54; // [rsp+B0h] [rbp-58h] BYREF
  struct _GUID v55; // [rsp+C0h] [rbp-48h] BYREF

  inserted = 0;
  v10 = -2147418113;
  v38 = -2147418113;
  v36 = 0;
  v40 = 0;
  pUnkOuter = 0;
  v11 = 0;
  v42 = 0;
  v43 = 0;
  v12 = a7;
  try
  {
    (*(void (**)(void))(*(_QWORD *)a7 + 8LL))();
    ((void (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))a8->lpVtbl->QueryInterface)(
      a8,
      &IID_IService,
      &v36);
    v13 = v36;
    v14 = *(_QWORD *)(a1 + 56);
    v15 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, __int64, GUID *, __int64, __int64 *))(*(_QWORD *)a7 + 24LL))(
            a7,
            v36,
            a3,
            &IID_IUnknown,
            a5,
            &v40);
    v35 = v15;
    v38 = v15;
    if ( !v40 )
    {
      v29 = a6;
      goto LABEL_123;
    }
    CDBPROPContainer::CreateCopy((CDBPROPContainer *)(v14 + 184), (struct CDBPROPContainer *)&v13[23]);
    inserted = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v36->lpVtbl[1].QueryInterface)(v36, v40);
    if ( inserted < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147418113, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0xBBu);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147418113, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0xBBu);
          if ( (bidGblFlags & 2) != 0 )
            v10 = bidTraceHR(
                    `CMultipleResults<CRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                    191497,
                    L"<CMultipleResults<class CRCM>::DoGetResult|Trace|HR> ",
                    2147549183LL);
        }
      }
      pExceptionObject = v10;
      throw (long *)&pExceptionObject;
    }
    if ( *(_BYTE *)(v14 + 352) )
    {
      if ( *(_BYTE *)(v14 + 353) )
      {
        ppv = 0;
        *(_QWORD *)&v55.Data1 = 0;
        SetupCM<CRCM,CRCM>::SetupNewCM(*(void **)(a1 + 56), (__int64)&pUnkOuter);
        v16 = CoCreateInstance(&CLSID_FoxRowset, pUnkOuter, 1u, &IID_IUnknown, &ppv);
        if ( v16 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v16, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0xC8u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v16, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0xC8u);
              if ( (bidGblFlags & 2) != 0 )
                v16 = bidTraceHR(
                        `CMultipleResults<CRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                        204809,
                        L"<CMultipleResults<class CRCM>::DoGetResult|Trace|HR> ",
                        (unsigned int)v16);
            }
          }
          v45 = v16;
          throw (long *)&v45;
        }
        v17 = ((__int64 (__fastcall *)(LPUNKNOWN, LPVOID))pUnkOuter->lpVtbl[1].QueryInterface)(pUnkOuter, ppv);
        if ( v17 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v17, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0xCAu);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v17, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0xCAu);
              if ( (bidGblFlags & 2) != 0 )
                v17 = bidTraceHR(
                        `CMultipleResults<CRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                        206857,
                        L"<CMultipleResults<class CRCM>::DoGetResult|Trace|HR> ",
                        (unsigned int)v17);
            }
          }
          v46 = v17;
          throw (long *)&v46;
        }
        v18 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct _GUID *))ppv)(ppv, &IID_IRDSServiceProperties, &v55);
        if ( v18 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v18, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0xCCu);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v18, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0xCCu);
              if ( (bidGblFlags & 2) != 0 )
                v18 = bidTraceHR(
                        `CMultipleResults<CRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                        208905,
                        L"<CMultipleResults<class CRCM>::DoGetResult|Trace|HR> ",
                        (unsigned int)v18);
            }
          }
          v47 = v18;
          throw (long *)&v47;
        }
        v19 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IRDSService, &v43);
        if ( v19 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v19, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0xCEu);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v19, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0xCEu);
              if ( (bidGblFlags & 2) != 0 )
                v19 = bidTraceHR(
                        `CMultipleResults<CRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                        210953,
                        L"<CMultipleResults<class CRCM>::DoGetResult|Trace|HR> ",
                        (unsigned int)v19);
            }
          }
          v48 = v19;
          throw (long *)&v48;
        }
        v20 = *(_DWORD *)(v14 + 248);
        v21 = *(struct tagDBPROPSET **)(v14 + 240);
        pperrinfo = 0;
        if ( FindProperty(v21, 0xD9u, (struct tagDBPROP **)&pperrinfo) != -1 )
          LODWORD(pperrinfo->lpVtbl) = 121;
        if ( FindProperty(v21, 0x104u, (struct tagDBPROP **)&pperrinfo) != -1 )
          LODWORD(pperrinfo->lpVtbl) = 126;
        inserted = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagDBPROPSET *))(**(_QWORD **)&v55.Data1 + 40LL))(
                     *(_QWORD *)&v55.Data1,
                     v20,
                     v21);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v55.Data1 + 16LL))(*(_QWORD *)&v55.Data1);
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        v22 = -2147217887;
        if ( inserted == -2147217887 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147217887, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0xEAu);
            if ( (bidGblFlags & 2) != 0 )
              v22 = bidTraceHR(
                      `CMultipleResults<CRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                      239625,
                      L"<CMultipleResults<class CRCM>::DoGetResult|Trace|HR> ",
                      2147749409LL);
          }
          v49 = v22;
          throw (long *)&v49;
        }
        if ( inserted == 265946 )
        {
          v23 = 0;
          v24 = 0;
          v25 = 0;
          v26 = 0;
          if ( v20 )
          {
            do
            {
              if ( v23 )
                goto LABEL_70;
              rgProperties = v21->rgProperties;
              for ( i = 0; i < v21->cProperties; ++i )
              {
                if ( rgProperties->dwStatus )
                {
                  if ( rgProperties->dwPropertyID == 260 )
                  {
                    v24 = 1;
                  }
                  else
                  {
                    if ( !rgProperties->dwOptions )
                    {
                      v23 = 1;
                      break;
                    }
                    v25 = 1;
                  }
                }
                ++rgProperties;
              }
              ++v26;
              ++v21;
            }
            while ( v26 < v20 );
            if ( v23 )
            {
LABEL_70:
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(-2147217887, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0x10Fu);
                if ( (bidGblFlags & 2) != 0 )
                  v22 = bidTraceHR(
                          `CMultipleResults<CRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                          277513,
                          L"<CMultipleResults<class CRCM>::DoGetResult|Trace|HR> ",
                          2147749409LL);
              }
              v50 = v22;
              throw (long *)&v50;
            }
            if ( v24 && !v25 )
              inserted = 0;
          }
        }
        v29 = a6;
        v30 = a4;
        v31 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, struct IUnknown *, struct IUnknown **))(*(_QWORD *)v43 + 32LL))(
                v43,
                a4,
                v36,
                a6);
        v32 = v31;
        if ( v31 < 0 )
        {
          if ( v31 == -2147024809 )
          {
            pperrinfo = 0;
            GetErrorInfo(0, &pperrinfo);
            if ( pperrinfo )
              ((void (__fastcall *)(IErrorInfo *))pperrinfo->lpVtbl->Release)(pperrinfo);
            v32 = -2147467262;
            PostHResult(-2147467262, a4);
          }
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v32, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0x12Cu);
            if ( (bidGblFlags & 2) != 0 )
              v32 = bidTraceHR(
                      `CMultipleResults<CRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                      307209,
                      L"<CMultipleResults<class CRCM>::DoGetResult|Trace|HR> ",
                      v32);
          }
          v51 = v32;
          throw (long *)&v51;
        }
        v11 = v42;
        goto LABEL_77;
      }
      inserted = 265946;
    }
    else if ( (*(_BYTE *)(v14 + 356) & 4) != 0 )
    {
      v55 = IID_IRowsetInfo;
      inserted = CAcm::InsertDynamicInterface((CAcm *)v13, &v55);
      if ( inserted < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(inserted, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0x13Eu);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(inserted, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0x13Eu);
            if ( (bidGblFlags & 2) != 0 )
              inserted = bidTraceHR(
                           `CMultipleResults<CRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                           325641,
                           L"<CMultipleResults<class CRCM>::DoGetResult|Trace|HR> ",
                           (unsigned int)inserted);
          }
        }
        v52 = inserted;
        throw (long *)&v52;
      }
    }
    v29 = a6;
    v30 = a4;
LABEL_77:
    if ( v29 )
    {
      if ( !*v29 )
      {
        inserted = CMQI(v30, a2, v36, a8, v29);
        if ( inserted < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(inserted, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0x144u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(inserted, L"<CMultipleResults<class CRCM>::DoGetResult|OLEDB|ERR> ", 0x144u);
              if ( (bidGblFlags & 2) != 0 )
                inserted = bidTraceHR(
                             `CMultipleResults<CRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                             331785,
                             L"<CMultipleResults<class CRCM>::DoGetResult|Trace|HR> ",
                             (unsigned int)inserted);
            }
          }
          v53 = inserted;
          throw (long *)&v53;
        }
      }
    }
    v15 = v35;
  }
  catch ( long v54 )
  {
    if ( (bidGblFlags & 2) != 0 && `CMultipleResults<CRCM>::DoGetResult'[::G]::_bidPtrSA_030_330[0] )
    {
      v34 = v54;
      bidTraceA(
        `CMultipleResults<CRCM>::DoGetResult'[::G]::_bidSrcFileA[0],
        337920,
        `CMultipleResults<CRCM>::DoGetResult'[::G]::_bidPtrSA_030_330[0],
        v54);
    }
    else
    {
      v34 = v54;
    }
    v12 = a7;
    v29 = a6;
    inserted = v34;
    v15 = v38;
    v11 = v42;
  }
  catch ( ... )
  {
    if ( (bidGblFlags & 2) != 0 && `CMultipleResults<CRCM>::DoGetResult'[::O]::_bidPtrSA_030_335[0] )
      bidTraceA(
        `CMultipleResults<CRCM>::DoGetResult'[::O]::_bidSrcFileA[0],
        343040,
        `CMultipleResults<CRCM>::DoGetResult'[::O]::_bidPtrSA_030_335[0],
        0);
    v12 = a7;
    v29 = a6;
    inserted = -2147418113;
    v11 = v42;
    goto LABEL_96;
  }
LABEL_123:
  if ( inserted < 0 )
  {
LABEL_96:
    if ( v29 && *v29 )
    {
      ((void (__fastcall *)(struct IUnknown *))(*v29)->lpVtbl->Release)(*v29);
      *v29 = 0;
    }
  }
  else
  {
    inserted = v15;
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v36 )
  {
    ((void (__fastcall *)(struct IUnknown *))v36->lpVtbl->Release)(v36);
    v36 = 0;
  }
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
  }
  if ( pUnkOuter )
  {
    ((void (__fastcall *)(LPUNKNOWN))pUnkOuter->lpVtbl->Release)(pUnkOuter);
    pUnkOuter = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           `CMultipleResults<CRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                           367625,
                           L"<CMultipleResults<class CRCM>::DoGetResult|Trace|HR> ",
                           (unsigned int)inserted);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180035af4  mov     rax, rsp
0x180035af7  mov     [rax+20h], r9
0x180035afb  mov     [rax+18h], r8
0x180035aff  mov     [rax+10h], rdx
0x180035b03  mov     [rax+8], rcx
0x180035b07  push    rbx
0x180035b08  push    rsi
0x180035b09  push    rdi
0x180035b0a  push    r12
0x180035b0c  push    r13
0x180035b0e  push    r14
0x180035b10  push    r15
0x180035b12  sub     rsp, 0D0h
0x180035b19  mov     r15, rcx
0x180035b1c  xor     ebx, ebx
0x180035b1e  mov     edi, ebx
0x180035b20  mov     esi, 8000FFFFh
0x180035b25  mov     [rsp+108h+var_B0], esi
0x180035b29  mov     [rsp+108h+var_C0], rbx
0x180035b2e  mov     [rsp+108h+var_A0], rbx
0x180035b33  mov     [rsp+108h+pUnkOuter], rbx
0x180035b38  mov     r14d, ebx
0x180035b3b  mov     [rsp+108h+var_90], rbx
0x180035b40  mov     [rax-88h], rbx
0x180035b47  mov     r12, [rsp+108h+arg_30]
0x180035b4f  mov     rax, [r12]
0x180035b53  mov     rcx, r12
0x180035b56  mov     rax, [rax+8]
0x180035b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b5f  mov     rcx, [rsp+108h+arg_38]
0x180035b67  mov     rax, [rcx]
0x180035b6a  lea     r8, [rsp+108h+var_C0]
0x180035b6f  lea     rdx, IID_IService
0x180035b76  mov     rax, [rax]
0x180035b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b7e  mov     r13, [rsp+108h+var_C0]
0x180035b83  mov     r15, [r15+38h]
0x180035b87  mov     rax, [r12]
0x180035b8b  lea     rcx, [rsp+108h+var_A0]
0x180035b90  mov     [rsp+108h+var_E0], rcx
0x180035b95  mov     rcx, [rsp+108h+arg_20]
0x180035b9d  mov     [rsp+108h+ppv], rcx
0x180035ba2  lea     r9, IID_IUnknown
0x180035ba9  mov     r8, [rsp+108h+arg_10]
0x180035bb1  mov     rdx, r13
0x180035bb4  mov     rcx, r12
0x180035bb7  mov     rax, [rax+18h]
0x180035bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bc0  mov     [rsp+108h+var_C8], eax
0x180035bc4  mov     [rsp+108h+var_B0], eax
0x180035bc8  cmp     [rsp+108h+var_A0], rbx
0x180035bcd  jz      loc_1800363B9
0x180035bd3  lea     rdx, [r13+0B8h]; struct CDBPROPContainer *
0x180035bda  lea     rcx, [r15+0B8h]; this
0x180035be1  call    ?CreateCopy@CDBPROPContainer@@QEAAJAEAV1@@Z; CDBPROPContainer::CreateCopy(CDBPROPContainer &)
0x180035be6  mov     rcx, [rsp+108h+var_C0]
0x180035beb  mov     rax, [rcx]
0x180035bee  mov     rdx, [rsp+108h+var_A0]
0x180035bf3  mov     rax, [rax+18h]
0x180035bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bfc  mov     edi, eax
0x180035bfe  test    eax, eax
0x180035c00  jns     loc_180035C86
0x180035c06  mov     eax, cs:_bidGblFlags
0x180035c0c  mov     bl, 2
0x180035c0e  test    bl, al
0x180035c10  jz      short loc_180035C6B
0x180035c12  mov     r8d, 0BBh; unsigned int
0x180035c18  lea     rdx, aCmultipleresul_4; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035c1f  mov     ecx, esi; int
0x180035c21  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035c26  mov     eax, cs:_bidGblFlags
0x180035c2c  test    bl, al
0x180035c2e  jz      short loc_180035C6B
0x180035c30  mov     r8d, 0BBh; unsigned int
0x180035c36  lea     rdx, aCmultipleresul_4; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035c3d  mov     ecx, esi; int
0x180035c3f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035c44  mov     eax, cs:_bidGblFlags
0x180035c4a  test    bl, al
0x180035c4c  jz      short loc_180035C6B
0x180035c4e  mov     r9d, esi
0x180035c51  lea     r8, aCmultipleresul_2; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035c58  mov     edx, 2EC09h
0x180035c5d  mov     rcx, cs:?_bidSrcFile2A@?1??DoGetResult@?$CMultipleResults@VCRCM@@@@QEAAJPEAUIUnknown@@_JAEBU_GUID@@PEA_JPEAPEAU3@PEAUIMultipleResults@@0@Z@4REBDEB; char const * const `CMultipleResults<CRCM>::DoGetResult(IUnknown *,__int64,_GUID const &,__int64 *,IUnknown * *,IMultipleResults *,IUnknown *)'::`2'::_bidSrcFile2A
0x180035c64  call    _bidTraceHR
0x180035c69  mov     esi, eax
0x180035c6b  mov     [rsp+108h+pExceptionObject], esi
0x180035c72  lea     rdx, _TI1J; pThrowInfo
0x180035c79  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180035c81  call    _CxxThrowException_0
0x180035c86  cmp     [r15+160h], bl
0x180035c8d  jz      loc_180036301
0x180035c93  cmp     [r15+161h], bl
0x180035c9a  jz      loc_18003622E
0x180035ca0  mov     [rsp+108h+var_A8], rbx
0x180035ca5  mov     qword ptr [rsp+108h+var_48.Data1], rbx
0x180035cad  lea     rax, [rsp+108h+pUnkOuter]
0x180035cb2  mov     [rsp+108h+ppv], rax; __int64
0x180035cb7  lea     r9, [rsp+108h+var_90]
0x180035cbc  mov     rcx, [rsp+108h+arg_0]
0x180035cc4  mov     rcx, [rcx+38h]; void *
0x180035cc8  call    ?SetupNewCM@?$SetupCM@VCRCM@@V1@@@SAJPEAV?$CComObject@VCRCM@@@ATL@@PEAUIUnknown@@AEBU_GUID@@PEAPEAU4@PEAPEAUIService@@@Z; SetupCM<CRCM,CRCM>::SetupNewCM(ATL::CComObject<CRCM> *,IUnknown *,_GUID const &,IUnknown * *,IService * *)
0x180035ccd  lea     rax, [rsp+108h+var_A8]
0x180035cd2  mov     [rsp+108h+ppv], rax; ppv
0x180035cd7  lea     r9, IID_IUnknown; riid
0x180035cde  mov     r8d, 1; dwClsContext
0x180035ce4  mov     rdx, [rsp+108h+pUnkOuter]; pUnkOuter
0x180035ce9  lea     rcx, ?CLSID_FoxRowset@@3U_GUID@@B; rclsid
0x180035cf0  call    cs:__imp_CoCreateInstance
0x180035cf6  mov     edi, eax
0x180035cf8  test    eax, eax
0x180035cfa  jns     loc_180035D80
0x180035d00  mov     eax, cs:_bidGblFlags
0x180035d06  mov     bl, 2
0x180035d08  test    bl, al
0x180035d0a  jz      short loc_180035D65
0x180035d0c  mov     r8d, 0C8h; unsigned int
0x180035d12  lea     rdx, aCmultipleresul_4; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035d19  mov     ecx, edi; int
0x180035d1b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035d20  mov     eax, cs:_bidGblFlags
0x180035d26  test    bl, al
0x180035d28  jz      short loc_180035D65
0x180035d2a  mov     r8d, 0C8h; unsigned int
0x180035d30  lea     rdx, aCmultipleresul_4; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035d37  mov     ecx, edi; int
0x180035d39  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035d3e  mov     eax, cs:_bidGblFlags
0x180035d44  test    bl, al
0x180035d46  jz      short loc_180035D65
0x180035d48  mov     r9d, edi
0x180035d4b  lea     r8, aCmultipleresul_2; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035d52  mov     edx, 32009h
0x180035d57  mov     rcx, cs:?_bidSrcFile2A@?1??DoGetResult@?$CMultipleResults@VCRCM@@@@QEAAJPEAUIUnknown@@_JAEBU_GUID@@PEA_JPEAPEAU3@PEAUIMultipleResults@@0@Z@4REBDEB; char const * const `CMultipleResults<CRCM>::DoGetResult(IUnknown *,__int64,_GUID const &,__int64 *,IUnknown * *,IMultipleResults *,IUnknown *)'::`2'::_bidSrcFile2A
0x180035d5e  call    _bidTraceHR
0x180035d63  mov     edi, eax
0x180035d65  mov     [rsp+108h+var_7C], edi
0x180035d6c  lea     rdx, _TI1J; pThrowInfo
0x180035d73  lea     rcx, [rsp+108h+var_7C]; pExceptionObject
0x180035d7b  call    _CxxThrowException_0
0x180035d80  mov     rcx, [rsp+108h+pUnkOuter]
0x180035d85  mov     rax, [rcx]
0x180035d88  mov     rdx, [rsp+108h+var_A8]
0x180035d8d  mov     rax, [rax+18h]
0x180035d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d96  mov     edi, eax
0x180035d98  test    eax, eax
0x180035d9a  jns     loc_180035E20
0x180035da0  mov     eax, cs:_bidGblFlags
0x180035da6  mov     bl, 2
0x180035da8  test    bl, al
0x180035daa  jz      short loc_180035E05
0x180035dac  mov     r8d, 0CAh; unsigned int
0x180035db2  lea     rdx, aCmultipleresul_4; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035db9  mov     ecx, edi; int
0x180035dbb  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035dc0  mov     eax, cs:_bidGblFlags
0x180035dc6  test    bl, al
0x180035dc8  jz      short loc_180035E05
0x180035dca  mov     r8d, 0CAh; unsigned int
0x180035dd0  lea     rdx, aCmultipleresul_4; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035dd7  mov     ecx, edi; int
0x180035dd9  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035dde  mov     eax, cs:_bidGblFlags
0x180035de4  test    bl, al
0x180035de6  jz      short loc_180035E05
0x180035de8  mov     r9d, edi
0x180035deb  lea     r8, aCmultipleresul_2; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035df2  mov     edx, 32809h
0x180035df7  mov     rcx, cs:?_bidSrcFile2A@?1??DoGetResult@?$CMultipleResults@VCRCM@@@@QEAAJPEAUIUnknown@@_JAEBU_GUID@@PEA_JPEAPEAU3@PEAUIMultipleResults@@0@Z@4REBDEB; char const * const `CMultipleResults<CRCM>::DoGetResult(IUnknown *,__int64,_GUID const &,__int64 *,IUnknown * *,IMultipleResults *,IUnknown *)'::`2'::_bidSrcFile2A
0x180035dfe  call    _bidTraceHR
0x180035e03  mov     edi, eax
0x180035e05  mov     [rsp+108h+var_78], edi
0x180035e0c  lea     rdx, _TI1J; pThrowInfo
0x180035e13  lea     rcx, [rsp+108h+var_78]; pExceptionObject
0x180035e1b  call    _CxxThrowException_0
0x180035e20  mov     rcx, [rsp+108h+var_A8]
0x180035e25  mov     rax, [rcx]
0x180035e28  lea     r8, [rsp+108h+var_48]
0x180035e30  lea     rdx, ?IID_IRDSServiceProperties@@3U_GUID@@B; _GUID const IID_IRDSServiceProperties
0x180035e37  mov     rax, [rax]
0x180035e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e3f  mov     edi, eax
0x180035e41  test    eax, eax
0x180035e43  jns     loc_180035EC9
0x180035e49  mov     eax, cs:_bidGblFlags
0x180035e4f  mov     bl, 2
0x180035e51  test    bl, al
0x180035e53  jz      short loc_180035EAE
0x180035e55  mov     r8d, 0CCh; unsigned int
0x180035e5b  lea     rdx, aCmultipleresul_4; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035e62  mov     ecx, edi; int
0x180035e64  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035e69  mov     eax, cs:_bidGblFlags
0x180035e6f  test    bl, al
0x180035e71  jz      short loc_180035EAE
0x180035e73  mov     r8d, 0CCh; unsigned int
0x180035e79  lea     rdx, aCmultipleresul_4; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035e80  mov     ecx, edi; int
0x180035e82  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035e87  mov     eax, cs:_bidGblFlags
0x180035e8d  test    bl, al
0x180035e8f  jz      short loc_180035EAE
0x180035e91  mov     r9d, edi
0x180035e94  lea     r8, aCmultipleresul_2; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035e9b  mov     edx, 33009h
0x180035ea0  mov     rcx, cs:?_bidSrcFile2A@?1??DoGetResult@?$CMultipleResults@VCRCM@@@@QEAAJPEAUIUnknown@@_JAEBU_GUID@@PEA_JPEAPEAU3@PEAUIMultipleResults@@0@Z@4REBDEB; char const * const `CMultipleResults<CRCM>::DoGetResult(IUnknown *,__int64,_GUID const &,__int64 *,IUnknown * *,IMultipleResults *,IUnknown *)'::`2'::_bidSrcFile2A
0x180035ea7  call    _bidTraceHR
0x180035eac  mov     edi, eax
0x180035eae  mov     [rsp+108h+var_74], edi
0x180035eb5  lea     rdx, _TI1J; pThrowInfo
0x180035ebc  lea     rcx, [rsp+108h+var_74]; pExceptionObject
0x180035ec4  call    _CxxThrowException_0
0x180035ec9  mov     rcx, [rsp+108h+var_A8]
0x180035ece  mov     rax, [rcx]
0x180035ed1  lea     r8, [rsp+108h+var_88]
0x180035ed9  lea     rdx, ?IID_IRDSService@@3U_GUID@@B; _GUID const IID_IRDSService
0x180035ee0  mov     rax, [rax]
0x180035ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ee8  mov     edi, eax
0x180035eea  test    eax, eax
0x180035eec  jns     loc_180035F72
0x180035ef2  mov     eax, cs:_bidGblFlags
0x180035ef8  mov     bl, 2
0x180035efa  test    bl, al
0x180035efc  jz      short loc_180035F57
0x180035efe  mov     r8d, 0CEh; unsigned int
0x180035f04  lea     rdx, aCmultipleresul_4; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035f0b  mov     ecx, edi; int
0x180035f0d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035f12  mov     eax, cs:_bidGblFlags
0x180035f18  test    bl, al
0x180035f1a  jz      short loc_180035F57
0x180035f1c  mov     r8d, 0CEh; unsigned int
0x180035f22  lea     rdx, aCmultipleresul_4; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035f29  mov     ecx, edi; int
0x180035f2b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035f30  mov     eax, cs:_bidGblFlags
0x180035f36  test    bl, al
0x180035f38  jz      short loc_180035F57
0x180035f3a  mov     r9d, edi
0x180035f3d  lea     r8, aCmultipleresul_2; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180035f44  mov     edx, 33809h
0x180035f49  mov     rcx, cs:?_bidSrcFile2A@?1??DoGetResult@?$CMultipleResults@VCRCM@@@@QEAAJPEAUIUnknown@@_JAEBU_GUID@@PEA_JPEAPEAU3@PEAUIMultipleResults@@0@Z@4REBDEB; char const * const `CMultipleResults<CRCM>::DoGetResult(IUnknown *,__int64,_GUID const &,__int64 *,IUnknown * *,IMultipleResults *,IUnknown *)'::`2'::_bidSrcFile2A
0x180035f50  call    _bidTraceHR
0x180035f55  mov     edi, eax
0x180035f57  mov     [rsp+108h+var_70], edi
0x180035f5e  lea     rdx, _TI1J; pThrowInfo
0x180035f65  lea     rcx, [rsp+108h+var_70]; pExceptionObject
0x180035f6d  call    _CxxThrowException_0
0x180035f72  mov     r13d, [r15+0F8h]
0x180035f79  mov     r14, [r15+0F0h]
0x180035f80  mov     [rsp+108h+pperrinfo], rbx
0x180035f85  lea     r8, [rsp+108h+pperrinfo]; struct tagDBPROP **
0x180035f8a  mov     edx, 0D9h; unsigned int
0x180035f8f  mov     rcx, r14; struct tagDBPROPSET *
0x180035f92  call    ?FindProperty@@YAKPEAUtagDBPROPSET@@KPEAPEAUtagDBPROP@@@Z; FindProperty(tagDBPROPSET *,ulong,tagDBPROP * *)
0x180035f97  or      edi, 0FFFFFFFFh
0x180035f9a  cmp     eax, edi
0x180035f9c  jz      short loc_180035FA9
0x180035f9e  mov     rax, [rsp+108h+pperrinfo]
0x180035fa3  mov     dword ptr [rax], 79h ; 'y'
0x180035fa9  lea     r8, [rsp+108h+pperrinfo]; struct tagDBPROP **
0x180035fae  mov     r15d, 104h
0x180035fb4  mov     edx, r15d; unsigned int
0x180035fb7  mov     rcx, r14; struct tagDBPROPSET *
0x180035fba  call    ?FindProperty@@YAKPEAUtagDBPROPSET@@KPEAPEAUtagDBPROP@@@Z; FindProperty(tagDBPROPSET *,ulong,tagDBPROP * *)
0x180035fbf  cmp     eax, edi
0x180035fc1  jz      short loc_180035FCE
0x180035fc3  mov     rax, [rsp+108h+pperrinfo]
0x180035fc8  mov     dword ptr [rax], 7Eh ; '~'
0x180035fce  mov     rcx, qword ptr [rsp+108h+var_48.Data1]
0x180035fd6  mov     rax, [rcx]
0x180035fd9  mov     r8, r14
0x180035fdc  mov     edx, r13d
0x180035fdf  mov     rax, [rax+28h]
0x180035fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fe8  mov     edi, eax
0x180035fea  mov     rcx, qword ptr [rsp+108h+var_48.Data1]
0x180035ff2  mov     rax, [rcx]
0x180035ff5  mov     rax, [rax+10h]
0x180035ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ffe  mov     rcx, [rsp+108h+var_A8]
0x180036003  mov     rax, [rcx]
0x180036006  mov     rax, [rax+10h]
0x18003600a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003600f  mov     esi, 80040E21h
0x180036014  cmp     edi, esi
0x180036016  jnz     short loc_18003607A
0x180036018  mov     eax, cs:_bidGblFlags
0x18003601e  mov     bl, 2
0x180036020  test    bl, al
0x180036022  jz      short loc_18003605F
0x180036024  mov     r8d, 0EAh; unsigned int
0x18003602a  lea     rdx, aCmultipleresul_4; "<CMultipleResults<class CRCM>::DoGetRes"...
0x180036031  mov     ecx, esi; int
0x180036033  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180036038  mov     eax, cs:_bidGblFlags
0x18003603e  test    bl, al
  ... truncated ...
```
