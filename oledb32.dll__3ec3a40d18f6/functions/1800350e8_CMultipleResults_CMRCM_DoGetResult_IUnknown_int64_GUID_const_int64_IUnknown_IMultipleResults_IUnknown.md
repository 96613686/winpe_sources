# CMultipleResults<CMRCM>::DoGetResult(IUnknown *,__int64,_GUID const &,__int64 *,IUnknown * *,IMultipleResults *,IUnknown *)

- ea: `0x1800350e8`
- end: `0x180035aed`
- name: `?DoGetResult@?$CMultipleResults@VCMRCM@@@@QEAAJPEAUIUnknown@@_JAEBU_GUID@@PEA_JPEAPEAU2@PEAUIMultipleResults@@0@Z`
- size: `2565`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, struct IUnknown **, __int64, struct IUnknown *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002ccb0`

## callees

- `0x1800100c4`
- `0x180013870`
- `0x180029560`
- `0x18002bc80`
- `0x18002ced8`
- `0x18002ec0c`
- `0x1800324c8`
- `0x1800350e8`
- `0x180061814`
- `0x18006e3b0`
- `0x180087010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x180035727`
- `OLEAUT32!__imp_GetErrorInfo` at `0x180035727`
- `ole32!CoCreateInstance` at `0x1800352e4`
- `ole32!CoCreateInstance` at `0x1800352e4`

## pseudocode

```c
__int64 __fastcall CMultipleResults<CMRCM>::DoGetResult(
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
        OLEDBTraceErr(-2147418113, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0xBBu);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147418113, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0xBBu);
          if ( (bidGblFlags & 2) != 0 )
            v10 = bidTraceHR(
                    `CMultipleResults<CMRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                    191497,
                    L"<CMultipleResults<class CMRCM>::DoGetResult|Trace|HR> ",
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
        SetupCM<CMRCM,CRCM>::SetupNewCM(*(void **)(a1 + 56), (__int64)&pUnkOuter);
        v16 = CoCreateInstance(&CLSID_FoxRowset, pUnkOuter, 1u, &IID_IUnknown, &ppv);
        if ( v16 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v16, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0xC8u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v16, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0xC8u);
              if ( (bidGblFlags & 2) != 0 )
                v16 = bidTraceHR(
                        `CMultipleResults<CMRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                        204809,
                        L"<CMultipleResults<class CMRCM>::DoGetResult|Trace|HR> ",
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
            OLEDBTraceErr(v17, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0xCAu);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v17, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0xCAu);
              if ( (bidGblFlags & 2) != 0 )
                v17 = bidTraceHR(
                        `CMultipleResults<CMRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                        206857,
                        L"<CMultipleResults<class CMRCM>::DoGetResult|Trace|HR> ",
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
            OLEDBTraceErr(v18, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0xCCu);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v18, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0xCCu);
              if ( (bidGblFlags & 2) != 0 )
                v18 = bidTraceHR(
                        `CMultipleResults<CMRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                        208905,
                        L"<CMultipleResults<class CMRCM>::DoGetResult|Trace|HR> ",
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
            OLEDBTraceErr(v19, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0xCEu);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v19, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0xCEu);
              if ( (bidGblFlags & 2) != 0 )
                v19 = bidTraceHR(
                        `CMultipleResults<CMRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                        210953,
                        L"<CMultipleResults<class CMRCM>::DoGetResult|Trace|HR> ",
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
            OLEDBTraceErr(-2147217887, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0xEAu);
            if ( (bidGblFlags & 2) != 0 )
              v22 = bidTraceHR(
                      `CMultipleResults<CMRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                      239625,
                      L"<CMultipleResults<class CMRCM>::DoGetResult|Trace|HR> ",
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
                OLEDBTraceErr(-2147217887, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0x10Fu);
                if ( (bidGblFlags & 2) != 0 )
                  v22 = bidTraceHR(
                          `CMultipleResults<CMRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                          277513,
                          L"<CMultipleResults<class CMRCM>::DoGetResult|Trace|HR> ",
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
            OLEDBTraceErr(v32, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0x12Cu);
            if ( (bidGblFlags & 2) != 0 )
              v32 = bidTraceHR(
                      `CMultipleResults<CMRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                      307209,
                      L"<CMultipleResults<class CMRCM>::DoGetResult|Trace|HR> ",
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
          OLEDBTraceErr(inserted, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0x13Eu);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(inserted, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0x13Eu);
            if ( (bidGblFlags & 2) != 0 )
              inserted = bidTraceHR(
                           `CMultipleResults<CMRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                           325641,
                           L"<CMultipleResults<class CMRCM>::DoGetResult|Trace|HR> ",
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
            OLEDBTraceErr(inserted, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0x144u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(inserted, L"<CMultipleResults<class CMRCM>::DoGetResult|OLEDB|ERR> ", 0x144u);
              if ( (bidGblFlags & 2) != 0 )
                inserted = bidTraceHR(
                             `CMultipleResults<CMRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                             331785,
                             L"<CMultipleResults<class CMRCM>::DoGetResult|Trace|HR> ",
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
    if ( (bidGblFlags & 2) != 0 && `CMultipleResults<CMRCM>::DoGetResult'[::G]::_bidPtrSA_030_330[0] )
    {
      v34 = v54;
      bidTraceA(
        `CMultipleResults<CMRCM>::DoGetResult'[::G]::_bidSrcFileA[0],
        337920,
        `CMultipleResults<CMRCM>::DoGetResult'[::G]::_bidPtrSA_030_330[0],
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
    if ( (bidGblFlags & 2) != 0 && `CMultipleResults<CMRCM>::DoGetResult'[::O]::_bidPtrSA_030_335[0] )
      bidTraceA(
        `CMultipleResults<CMRCM>::DoGetResult'[::O]::_bidSrcFileA[0],
        343040,
        `CMultipleResults<CMRCM>::DoGetResult'[::O]::_bidPtrSA_030_335[0],
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
                           `CMultipleResults<CMRCM>::DoGetResult'::`2'::_bidSrcFile2A[0],
                           367625,
                           L"<CMultipleResults<class CMRCM>::DoGetResult|Trace|HR> ",
                           (unsigned int)inserted);
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x1800350e8  mov     rax, rsp
0x1800350eb  mov     [rax+20h], r9
0x1800350ef  mov     [rax+18h], r8
0x1800350f3  mov     [rax+10h], rdx
0x1800350f7  mov     [rax+8], rcx
0x1800350fb  push    rbx
0x1800350fc  push    rsi
0x1800350fd  push    rdi
0x1800350fe  push    r12
0x180035100  push    r13
0x180035102  push    r14
0x180035104  push    r15
0x180035106  sub     rsp, 0D0h
0x18003510d  mov     r15, rcx
0x180035110  xor     ebx, ebx
0x180035112  mov     edi, ebx
0x180035114  mov     esi, 8000FFFFh
0x180035119  mov     [rsp+108h+var_B0], esi
0x18003511d  mov     [rsp+108h+var_C0], rbx
0x180035122  mov     [rsp+108h+var_A0], rbx
0x180035127  mov     [rsp+108h+pUnkOuter], rbx
0x18003512c  mov     r14d, ebx
0x18003512f  mov     [rsp+108h+var_90], rbx
0x180035134  mov     [rax-88h], rbx
0x18003513b  mov     r12, [rsp+108h+arg_30]
0x180035143  mov     rax, [r12]
0x180035147  mov     rcx, r12
0x18003514a  mov     rax, [rax+8]
0x18003514e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035153  mov     rcx, [rsp+108h+arg_38]
0x18003515b  mov     rax, [rcx]
0x18003515e  lea     r8, [rsp+108h+var_C0]
0x180035163  lea     rdx, IID_IService
0x18003516a  mov     rax, [rax]
0x18003516d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035172  mov     r13, [rsp+108h+var_C0]
0x180035177  mov     r15, [r15+38h]
0x18003517b  mov     rax, [r12]
0x18003517f  lea     rcx, [rsp+108h+var_A0]
0x180035184  mov     [rsp+108h+var_E0], rcx
0x180035189  mov     rcx, [rsp+108h+arg_20]
0x180035191  mov     [rsp+108h+ppv], rcx
0x180035196  lea     r9, IID_IUnknown
0x18003519d  mov     r8, [rsp+108h+arg_10]
0x1800351a5  mov     rdx, r13
0x1800351a8  mov     rcx, r12
0x1800351ab  mov     rax, [rax+18h]
0x1800351af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351b4  mov     [rsp+108h+var_C8], eax
0x1800351b8  mov     [rsp+108h+var_B0], eax
0x1800351bc  cmp     [rsp+108h+var_A0], rbx
0x1800351c1  jz      loc_1800359AD
0x1800351c7  lea     rdx, [r13+0B8h]; struct CDBPROPContainer *
0x1800351ce  lea     rcx, [r15+0B8h]; this
0x1800351d5  call    ?CreateCopy@CDBPROPContainer@@QEAAJAEAV1@@Z; CDBPROPContainer::CreateCopy(CDBPROPContainer &)
0x1800351da  mov     rcx, [rsp+108h+var_C0]
0x1800351df  mov     rax, [rcx]
0x1800351e2  mov     rdx, [rsp+108h+var_A0]
0x1800351e7  mov     rax, [rax+18h]
0x1800351eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351f0  mov     edi, eax
0x1800351f2  test    eax, eax
0x1800351f4  jns     loc_18003527A
0x1800351fa  mov     eax, cs:_bidGblFlags
0x180035200  mov     bl, 2
0x180035202  test    bl, al
0x180035204  jz      short loc_18003525F
0x180035206  mov     r8d, 0BBh; unsigned int
0x18003520c  lea     rdx, aCmultipleresul_9; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x180035213  mov     ecx, esi; int
0x180035215  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003521a  mov     eax, cs:_bidGblFlags
0x180035220  test    bl, al
0x180035222  jz      short loc_18003525F
0x180035224  mov     r8d, 0BBh; unsigned int
0x18003522a  lea     rdx, aCmultipleresul_9; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x180035231  mov     ecx, esi; int
0x180035233  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035238  mov     eax, cs:_bidGblFlags
0x18003523e  test    bl, al
0x180035240  jz      short loc_18003525F
0x180035242  mov     r9d, esi
0x180035245  lea     r8, aCmultipleresul; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x18003524c  mov     edx, 2EC09h
0x180035251  mov     rcx, cs:?_bidSrcFile2A@?1??DoGetResult@?$CMultipleResults@VCMRCM@@@@QEAAJPEAUIUnknown@@_JAEBU_GUID@@PEA_JPEAPEAU3@PEAUIMultipleResults@@0@Z@4REBDEB; char const * const `CMultipleResults<CMRCM>::DoGetResult(IUnknown *,__int64,_GUID const &,__int64 *,IUnknown * *,IMultipleResults *,IUnknown *)'::`2'::_bidSrcFile2A
0x180035258  call    _bidTraceHR
0x18003525d  mov     esi, eax
0x18003525f  mov     [rsp+108h+pExceptionObject], esi
0x180035266  lea     rdx, _TI1J; pThrowInfo
0x18003526d  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x180035275  call    _CxxThrowException_0
0x18003527a  cmp     [r15+160h], bl
0x180035281  jz      loc_1800358F5
0x180035287  cmp     [r15+161h], bl
0x18003528e  jz      loc_180035822
0x180035294  mov     [rsp+108h+var_A8], rbx
0x180035299  mov     qword ptr [rsp+108h+var_48.Data1], rbx
0x1800352a1  lea     rax, [rsp+108h+pUnkOuter]
0x1800352a6  mov     [rsp+108h+ppv], rax; __int64
0x1800352ab  lea     r9, [rsp+108h+var_90]
0x1800352b0  mov     rcx, [rsp+108h+arg_0]
0x1800352b8  mov     rcx, [rcx+38h]; void *
0x1800352bc  call    ?SetupNewCM@?$SetupCM@VCMRCM@@VCRCM@@@@SAJPEAV?$CComObject@VCMRCM@@@ATL@@PEAUIUnknown@@AEBU_GUID@@PEAPEAU4@PEAPEAUIService@@@Z; SetupCM<CMRCM,CRCM>::SetupNewCM(ATL::CComObject<CMRCM> *,IUnknown *,_GUID const &,IUnknown * *,IService * *)
0x1800352c1  lea     rax, [rsp+108h+var_A8]
0x1800352c6  mov     [rsp+108h+ppv], rax; ppv
0x1800352cb  lea     r9, IID_IUnknown; riid
0x1800352d2  mov     r8d, 1; dwClsContext
0x1800352d8  mov     rdx, [rsp+108h+pUnkOuter]; pUnkOuter
0x1800352dd  lea     rcx, ?CLSID_FoxRowset@@3U_GUID@@B; rclsid
0x1800352e4  call    cs:__imp_CoCreateInstance
0x1800352ea  mov     edi, eax
0x1800352ec  test    eax, eax
0x1800352ee  jns     loc_180035374
0x1800352f4  mov     eax, cs:_bidGblFlags
0x1800352fa  mov     bl, 2
0x1800352fc  test    bl, al
0x1800352fe  jz      short loc_180035359
0x180035300  mov     r8d, 0C8h; unsigned int
0x180035306  lea     rdx, aCmultipleresul_9; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x18003530d  mov     ecx, edi; int
0x18003530f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035314  mov     eax, cs:_bidGblFlags
0x18003531a  test    bl, al
0x18003531c  jz      short loc_180035359
0x18003531e  mov     r8d, 0C8h; unsigned int
0x180035324  lea     rdx, aCmultipleresul_9; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x18003532b  mov     ecx, edi; int
0x18003532d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035332  mov     eax, cs:_bidGblFlags
0x180035338  test    bl, al
0x18003533a  jz      short loc_180035359
0x18003533c  mov     r9d, edi
0x18003533f  lea     r8, aCmultipleresul; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x180035346  mov     edx, 32009h
0x18003534b  mov     rcx, cs:?_bidSrcFile2A@?1??DoGetResult@?$CMultipleResults@VCMRCM@@@@QEAAJPEAUIUnknown@@_JAEBU_GUID@@PEA_JPEAPEAU3@PEAUIMultipleResults@@0@Z@4REBDEB; char const * const `CMultipleResults<CMRCM>::DoGetResult(IUnknown *,__int64,_GUID const &,__int64 *,IUnknown * *,IMultipleResults *,IUnknown *)'::`2'::_bidSrcFile2A
0x180035352  call    _bidTraceHR
0x180035357  mov     edi, eax
0x180035359  mov     [rsp+108h+var_7C], edi
0x180035360  lea     rdx, _TI1J; pThrowInfo
0x180035367  lea     rcx, [rsp+108h+var_7C]; pExceptionObject
0x18003536f  call    _CxxThrowException_0
0x180035374  mov     rcx, [rsp+108h+pUnkOuter]
0x180035379  mov     rax, [rcx]
0x18003537c  mov     rdx, [rsp+108h+var_A8]
0x180035381  mov     rax, [rax+18h]
0x180035385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003538a  mov     edi, eax
0x18003538c  test    eax, eax
0x18003538e  jns     loc_180035414
0x180035394  mov     eax, cs:_bidGblFlags
0x18003539a  mov     bl, 2
0x18003539c  test    bl, al
0x18003539e  jz      short loc_1800353F9
0x1800353a0  mov     r8d, 0CAh; unsigned int
0x1800353a6  lea     rdx, aCmultipleresul_9; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x1800353ad  mov     ecx, edi; int
0x1800353af  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800353b4  mov     eax, cs:_bidGblFlags
0x1800353ba  test    bl, al
0x1800353bc  jz      short loc_1800353F9
0x1800353be  mov     r8d, 0CAh; unsigned int
0x1800353c4  lea     rdx, aCmultipleresul_9; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x1800353cb  mov     ecx, edi; int
0x1800353cd  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800353d2  mov     eax, cs:_bidGblFlags
0x1800353d8  test    bl, al
0x1800353da  jz      short loc_1800353F9
0x1800353dc  mov     r9d, edi
0x1800353df  lea     r8, aCmultipleresul; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x1800353e6  mov     edx, 32809h
0x1800353eb  mov     rcx, cs:?_bidSrcFile2A@?1??DoGetResult@?$CMultipleResults@VCMRCM@@@@QEAAJPEAUIUnknown@@_JAEBU_GUID@@PEA_JPEAPEAU3@PEAUIMultipleResults@@0@Z@4REBDEB; char const * const `CMultipleResults<CMRCM>::DoGetResult(IUnknown *,__int64,_GUID const &,__int64 *,IUnknown * *,IMultipleResults *,IUnknown *)'::`2'::_bidSrcFile2A
0x1800353f2  call    _bidTraceHR
0x1800353f7  mov     edi, eax
0x1800353f9  mov     [rsp+108h+var_78], edi
0x180035400  lea     rdx, _TI1J; pThrowInfo
0x180035407  lea     rcx, [rsp+108h+var_78]; pExceptionObject
0x18003540f  call    _CxxThrowException_0
0x180035414  mov     rcx, [rsp+108h+var_A8]
0x180035419  mov     rax, [rcx]
0x18003541c  lea     r8, [rsp+108h+var_48]
0x180035424  lea     rdx, ?IID_IRDSServiceProperties@@3U_GUID@@B; _GUID const IID_IRDSServiceProperties
0x18003542b  mov     rax, [rax]
0x18003542e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035433  mov     edi, eax
0x180035435  test    eax, eax
0x180035437  jns     loc_1800354BD
0x18003543d  mov     eax, cs:_bidGblFlags
0x180035443  mov     bl, 2
0x180035445  test    bl, al
0x180035447  jz      short loc_1800354A2
0x180035449  mov     r8d, 0CCh; unsigned int
0x18003544f  lea     rdx, aCmultipleresul_9; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x180035456  mov     ecx, edi; int
0x180035458  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003545d  mov     eax, cs:_bidGblFlags
0x180035463  test    bl, al
0x180035465  jz      short loc_1800354A2
0x180035467  mov     r8d, 0CCh; unsigned int
0x18003546d  lea     rdx, aCmultipleresul_9; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x180035474  mov     ecx, edi; int
0x180035476  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003547b  mov     eax, cs:_bidGblFlags
0x180035481  test    bl, al
0x180035483  jz      short loc_1800354A2
0x180035485  mov     r9d, edi
0x180035488  lea     r8, aCmultipleresul; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x18003548f  mov     edx, 33009h
0x180035494  mov     rcx, cs:?_bidSrcFile2A@?1??DoGetResult@?$CMultipleResults@VCMRCM@@@@QEAAJPEAUIUnknown@@_JAEBU_GUID@@PEA_JPEAPEAU3@PEAUIMultipleResults@@0@Z@4REBDEB; char const * const `CMultipleResults<CMRCM>::DoGetResult(IUnknown *,__int64,_GUID const &,__int64 *,IUnknown * *,IMultipleResults *,IUnknown *)'::`2'::_bidSrcFile2A
0x18003549b  call    _bidTraceHR
0x1800354a0  mov     edi, eax
0x1800354a2  mov     [rsp+108h+var_74], edi
0x1800354a9  lea     rdx, _TI1J; pThrowInfo
0x1800354b0  lea     rcx, [rsp+108h+var_74]; pExceptionObject
0x1800354b8  call    _CxxThrowException_0
0x1800354bd  mov     rcx, [rsp+108h+var_A8]
0x1800354c2  mov     rax, [rcx]
0x1800354c5  lea     r8, [rsp+108h+var_88]
0x1800354cd  lea     rdx, ?IID_IRDSService@@3U_GUID@@B; _GUID const IID_IRDSService
0x1800354d4  mov     rax, [rax]
0x1800354d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354dc  mov     edi, eax
0x1800354de  test    eax, eax
0x1800354e0  jns     loc_180035566
0x1800354e6  mov     eax, cs:_bidGblFlags
0x1800354ec  mov     bl, 2
0x1800354ee  test    bl, al
0x1800354f0  jz      short loc_18003554B
0x1800354f2  mov     r8d, 0CEh; unsigned int
0x1800354f8  lea     rdx, aCmultipleresul_9; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x1800354ff  mov     ecx, edi; int
0x180035501  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035506  mov     eax, cs:_bidGblFlags
0x18003550c  test    bl, al
0x18003550e  jz      short loc_18003554B
0x180035510  mov     r8d, 0CEh; unsigned int
0x180035516  lea     rdx, aCmultipleresul_9; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x18003551d  mov     ecx, edi; int
0x18003551f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180035524  mov     eax, cs:_bidGblFlags
0x18003552a  test    bl, al
0x18003552c  jz      short loc_18003554B
0x18003552e  mov     r9d, edi
0x180035531  lea     r8, aCmultipleresul; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x180035538  mov     edx, 33809h
0x18003553d  mov     rcx, cs:?_bidSrcFile2A@?1??DoGetResult@?$CMultipleResults@VCMRCM@@@@QEAAJPEAUIUnknown@@_JAEBU_GUID@@PEA_JPEAPEAU3@PEAUIMultipleResults@@0@Z@4REBDEB; char const * const `CMultipleResults<CMRCM>::DoGetResult(IUnknown *,__int64,_GUID const &,__int64 *,IUnknown * *,IMultipleResults *,IUnknown *)'::`2'::_bidSrcFile2A
0x180035544  call    _bidTraceHR
0x180035549  mov     edi, eax
0x18003554b  mov     [rsp+108h+var_70], edi
0x180035552  lea     rdx, _TI1J; pThrowInfo
0x180035559  lea     rcx, [rsp+108h+var_70]; pExceptionObject
0x180035561  call    _CxxThrowException_0
0x180035566  mov     r13d, [r15+0F8h]
0x18003556d  mov     r14, [r15+0F0h]
0x180035574  mov     [rsp+108h+pperrinfo], rbx
0x180035579  lea     r8, [rsp+108h+pperrinfo]; struct tagDBPROP **
0x18003557e  mov     edx, 0D9h; unsigned int
0x180035583  mov     rcx, r14; struct tagDBPROPSET *
0x180035586  call    ?FindProperty@@YAKPEAUtagDBPROPSET@@KPEAPEAUtagDBPROP@@@Z; FindProperty(tagDBPROPSET *,ulong,tagDBPROP * *)
0x18003558b  or      edi, 0FFFFFFFFh
0x18003558e  cmp     eax, edi
0x180035590  jz      short loc_18003559D
0x180035592  mov     rax, [rsp+108h+pperrinfo]
0x180035597  mov     dword ptr [rax], 79h ; 'y'
0x18003559d  lea     r8, [rsp+108h+pperrinfo]; struct tagDBPROP **
0x1800355a2  mov     r15d, 104h
0x1800355a8  mov     edx, r15d; unsigned int
0x1800355ab  mov     rcx, r14; struct tagDBPROPSET *
0x1800355ae  call    ?FindProperty@@YAKPEAUtagDBPROPSET@@KPEAPEAUtagDBPROP@@@Z; FindProperty(tagDBPROPSET *,ulong,tagDBPROP * *)
0x1800355b3  cmp     eax, edi
0x1800355b5  jz      short loc_1800355C2
0x1800355b7  mov     rax, [rsp+108h+pperrinfo]
0x1800355bc  mov     dword ptr [rax], 7Eh ; '~'
0x1800355c2  mov     rcx, qword ptr [rsp+108h+var_48.Data1]
0x1800355ca  mov     rax, [rcx]
0x1800355cd  mov     r8, r14
0x1800355d0  mov     edx, r13d
0x1800355d3  mov     rax, [rax+28h]
0x1800355d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355dc  mov     edi, eax
0x1800355de  mov     rcx, qword ptr [rsp+108h+var_48.Data1]
0x1800355e6  mov     rax, [rcx]
0x1800355e9  mov     rax, [rax+10h]
0x1800355ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800355f2  mov     rcx, [rsp+108h+var_A8]
0x1800355f7  mov     rax, [rcx]
0x1800355fa  mov     rax, [rax+10h]
0x1800355fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035603  mov     esi, 80040E21h
0x180035608  cmp     edi, esi
0x18003560a  jnz     short loc_18003566E
0x18003560c  mov     eax, cs:_bidGblFlags
0x180035612  mov     bl, 2
0x180035614  test    bl, al
0x180035616  jz      short loc_180035653
0x180035618  mov     r8d, 0EAh; unsigned int
0x18003561e  lea     rdx, aCmultipleresul_9; "<CMultipleResults<class CMRCM>::DoGetRe"...
0x180035625  mov     ecx, esi; int
0x180035627  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18003562c  mov     eax, cs:_bidGblFlags
0x180035632  test    bl, al
  ... truncated ...
```
