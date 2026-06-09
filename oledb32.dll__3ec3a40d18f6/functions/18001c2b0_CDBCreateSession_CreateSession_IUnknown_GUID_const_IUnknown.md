# CDBCreateSession::CreateSession(IUnknown *,_GUID const &,IUnknown * *)

- ea: `0x18001c2b0`
- end: `0x18001cea7`
- name: `?CreateSession@CDBCreateSession@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAU2@@Z`
- size: `3063`
- prototype: `__int64 __fastcall(CDBCreateSession *__hidden this, struct IUnknown *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013870`
- `0x18001c2b0`
- `0x18001ceb0`
- `0x18001d0a4`
- `0x180022bf8`
- `0x180029560`
- `0x18002a93c`
- `0x18002c024`
- `0x18002c060`
- `0x18002ec0c`
- `0x18003c2e8`
- `0x18006e3b0`
- `0x180072cec`
- `0x180073720`
- `0x180078e50`
- `0x180087010`

## string_xrefs

- `0x18001c312`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c382`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c3c1`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c451`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c46f`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c4e5`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c503`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c56c`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c5e5`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c603`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c687`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c709`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c727`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c790`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c803`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c821`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c8d6`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c8f4`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c9af`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c9cd`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001ca9f`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001cabd`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001cb32`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001cb50`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001cc22`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001ccc6`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001cce4`: `<CDBCreateSession::CreateSession|OLEDB|ERR> `
- `0x18001c32d`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001c3dc`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001c48a`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001c51e`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001c587`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001c61e`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001c6a2`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001c742`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001c7ab`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001c83c`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001c90f`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001c9e8`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001cad8`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001cb6b`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001ccff`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001cd8b`: `<CDBCreateSession::CreateSession|Trace|HR> `
- `0x18001ce6b`: `<CDBCreateSession::CreateSession|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CDBCreateSession::CreateSession(
        CDBCreateSession *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        struct IUnknown **a4)
{
  const struct _GUID *v5; // r14
  unsigned int v8; // edi
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // esi
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  int v16; // esi
  struct IUnknown *v17; // rbx
  int v18; // esi
  int v19; // esi
  int v20; // esi
  __int64 Provider; // rax
  __int64 v22; // r14
  int v23; // esi
  int v24; // esi
  int v25; // esi
  int v26; // esi
  struct IUnknown *v27; // rdx
  int v28; // esi
  CDPO *CDPO; // rax
  int inserted; // esi
  struct IUnknownVtbl *lpVtbl; // rcx
  int v32; // esi
  int v33; // esi
  void *ProviderInterface; // rax
  struct CDynamicInterface *DynamicInterface; // rax
  int v36; // esi
  unsigned int v37; // r14d
  unsigned int v38; // ebx
  struct IUnknown *v39; // [rsp+30h] [rbp-A8h] BYREF
  int v40; // [rsp+38h] [rbp-A0h]
  struct IUnknown *v41; // [rsp+40h] [rbp-98h] BYREF
  struct IUnknownVtbl *v42; // [rsp+48h] [rbp-90h] BYREF
  int pExceptionObject; // [rsp+50h] [rbp-88h] BYREF
  int v44; // [rsp+54h] [rbp-84h] BYREF
  int v45; // [rsp+58h] [rbp-80h] BYREF
  int v46; // [rsp+5Ch] [rbp-7Ch] BYREF
  int v47; // [rsp+60h] [rbp-78h] BYREF
  int v48; // [rsp+64h] [rbp-74h] BYREF
  int v49; // [rsp+68h] [rbp-70h] BYREF
  int v50; // [rsp+6Ch] [rbp-6Ch] BYREF
  int v51; // [rsp+70h] [rbp-68h] BYREF
  int v52; // [rsp+74h] [rbp-64h] BYREF
  int v53; // [rsp+78h] [rbp-60h] BYREF
  int v54; // [rsp+7Ch] [rbp-5Ch] BYREF
  int v55; // [rsp+80h] [rbp-58h] BYREF
  unsigned int v56; // [rsp+84h] [rbp-54h] BYREF
  struct _GUID v57; // [rsp+90h] [rbp-48h] BYREF
  __int64 v58; // [rsp+A0h] [rbp-38h]
  __int64 v59; // [rsp+A8h] [rbp-30h] BYREF

  v5 = a3;
  v41 = 0;
  v39 = 0;
  v42 = 0;
  v58 = 0;
  if ( !a4 )
  {
    v8 = -2147024809;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024809, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x31u);
      if ( (bidGblFlags & 2) != 0 )
        return (unsigned int)bidTraceHR(
                               off_1800C84D0[0],
                               50185,
                               L"<CDBCreateSession::CreateSession|Trace|HR> ",
                               2147942487LL);
    }
    return v8;
  }
  *a4 = 0;
  if ( a2 )
  {
    v10 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&IID_IUnknown.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&IID_IUnknown.Data1 )
      v10 = *(_QWORD *)a3->Data4 - *(_QWORD *)IID_IUnknown.Data4;
    if ( v10 )
    {
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(-2147217886, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x37u);
      return 2147749410LL;
    }
  }
  v11 = *((_QWORD *)this + 7);
  if ( !*(_BYTE *)(v11 + 817) )
  {
    v12 = -2147418113;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147418113, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x3Bu);
      if ( (bidGblFlags & 2) != 0 )
        return (unsigned int)bidTraceHR(
                               off_1800C84D0[0],
                               60425,
                               L"<CDBCreateSession::CreateSession|Trace|HR> ",
                               2147549183LL);
    }
    return v12;
  }
  try
  {
    if ( (*(unsigned int (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)(v11 + 184) + 32LL))(v11 + 184, &v41) )
    {
      v18 = NewCM<CSCM>::CoCreateCM(v14, v13, v15, &v41);
      if ( v18 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v18, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x4Cu);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v18, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x4Cu);
            if ( (bidGblFlags & 2) != 0 )
              v18 = bidTraceHR(
                      off_1800C84D0[0],
                      77833,
                      L"<CDBCreateSession::CreateSession|Trace|HR> ",
                      (unsigned int)v18);
          }
        }
        v44 = v18;
        throw (long *)&v44;
      }
      if ( !v41 )
      {
        v19 = -2147418113;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147418113, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", (_DWORD)v41 + 78);
          if ( (bidGblFlags & 2) != 0 )
            v19 = bidTraceHR(off_1800C84D0[0], 79881, L"<CDBCreateSession::CreateSession|Trace|HR> ", 2147549183LL);
        }
        v45 = v19;
        throw (long *)&v45;
      }
      v20 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v41->lpVtbl->QueryInterface)(
              v41,
              &IID_IService,
              &v39);
      if ( v20 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v20, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x51u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v20, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x51u);
            if ( (bidGblFlags & 2) != 0 )
              v20 = bidTraceHR(
                      off_1800C84D0[0],
                      82953,
                      L"<CDBCreateSession::CreateSession|Trace|HR> ",
                      (unsigned int)v20);
          }
        }
        v46 = v20;
        throw (long *)&v46;
      }
      v17 = v39;
      Provider = GetProviderPointer<CDCM>(*((_QWORD *)this + 7), &IID_IDBCreateSession);
      v22 = Provider;
      v58 = Provider;
      if ( !Provider )
      {
        v23 = -2147418113;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147418113, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x5Cu);
          if ( (bidGblFlags & 2) != 0 )
            v23 = bidTraceHR(off_1800C84D0[0], 94217, L"<CDBCreateSession::CreateSession|Trace|HR> ", 2147549183LL);
        }
        v47 = v23;
        throw (long *)&v47;
      }
      v24 = (*(__int64 (__fastcall **)(__int64, struct IUnknown *, GUID *, struct IUnknownVtbl **))(*(_QWORD *)Provider
                                                                                                  + 24LL))(
              Provider,
              v39,
              &IID_IUnknown,
              &v42);
      if ( v24 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v24, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x5Eu);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v24, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x5Eu);
            if ( (bidGblFlags & 2) != 0 )
              v24 = bidTraceHR(
                      off_1800C84D0[0],
                      96265,
                      L"<CDBCreateSession::CreateSession|Trace|HR> ",
                      (unsigned int)v24);
          }
        }
        v48 = v24;
        throw (long *)&v48;
      }
      if ( !v42 )
      {
        v25 = -2147418113;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147418113, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", (_DWORD)v42 + 96);
          if ( (bidGblFlags & 2) != 0 )
            v25 = bidTraceHR(off_1800C84D0[0], 98313, L"<CDBCreateSession::CreateSession|Trace|HR> ", 2147549183LL);
        }
        v49 = v25;
        throw (long *)&v49;
      }
      v26 = ((__int64 (__fastcall *)(struct IUnknown *))v39->lpVtbl[1].QueryInterface)(v39);
      if ( v26 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v26, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x63u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v26, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x63u);
            if ( (bidGblFlags & 2) != 0 )
              v26 = bidTraceHR(
                      off_1800C84D0[0],
                      101385,
                      L"<CDBCreateSession::CreateSession|Trace|HR> ",
                      (unsigned int)v26);
          }
        }
        v50 = v26;
        throw (long *)&v50;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v58 = 0;
      (*((void (__fastcall **)(struct IUnknownVtbl *))v42->QueryInterface + 2))(v42);
      v42 = 0;
      v27 = *(struct IUnknown **)(*((_QWORD *)this + 7) + 464LL);
      if ( v27 )
        CSCM::StoreDPO((CSCM *)v17, v27);
      v28 = CDCM::EnlistSCM(*((CDCM **)this + 7), v39);
      if ( v28 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v28, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x77u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v28, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x77u);
            if ( (bidGblFlags & 2) != 0 )
              v28 = bidTraceHR(
                      off_1800C84D0[0],
                      121865,
                      L"<CDBCreateSession::CreateSession|Trace|HR> ",
                      (unsigned int)v28);
          }
        }
        v51 = v28;
        throw (long *)&v51;
      }
      v5 = a3;
    }
    else
    {
      v16 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v41->lpVtbl->QueryInterface)(
              v41,
              &IID_IService,
              &v39);
      if ( v16 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v16, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x40u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v16, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x40u);
            if ( (bidGblFlags & 2) != 0 )
              v16 = bidTraceHR(
                      off_1800C84D0[0],
                      65545,
                      L"<CDBCreateSession::CreateSession|Trace|HR> ",
                      (unsigned int)v16);
          }
        }
        pExceptionObject = v16;
        throw (long *)&pExceptionObject;
      }
      v17 = v39;
    }
    if ( !LOBYTE(v17[60].lpVtbl) )
    {
      v59 = 0;
      CDPO = CDCM::GetCDPO(*((CDCM **)this + 7));
      if ( (CDPO::GetOLEDBServices(CDPO) & 0xC) == 0xC )
      {
        v57 = IID_IOpenRowset;
        inserted = CAcm::InsertDynamicInterface((CAcm *)v17, &v57);
        if ( inserted < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(inserted, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x91u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(inserted, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x91u);
              if ( (bidGblFlags & 2) != 0 )
                inserted = bidTraceHR(
                             off_1800C84D0[0],
                             148489,
                             L"<CDBCreateSession::CreateSession|Trace|HR> ",
                             (unsigned int)inserted);
            }
          }
          v52 = inserted;
          throw (long *)&v52;
        }
        lpVtbl = v17[20].lpVtbl;
        v42 = lpVtbl;
        if ( lpVtbl )
        {
          if ( (*(int (__fastcall **)(struct IUnknownVtbl *, GUID *, __int64 *))lpVtbl->QueryInterface)(
                 lpVtbl,
                 &IID_IDBCreateCommand,
                 &v59) >= 0 )
          {
            v57 = IID_IDBCreateCommand;
            v32 = CAcm::InsertDynamicInterface((CAcm *)v17, &v57);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
            v42 = 0;
            if ( v32 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v32, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x9Cu);
                if ( (bidGblFlags & 2) != 0 )
                {
                  OLEDBTraceErr(v32, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0x9Cu);
                  if ( (bidGblFlags & 2) != 0 )
                    v32 = bidTraceHR(
                            off_1800C84D0[0],
                            159753,
                            L"<CDBCreateSession::CreateSession|Trace|HR> ",
                            (unsigned int)v32);
                }
              }
              v53 = v32;
              throw (long *)&v53;
            }
          }
        }
      }
      LOBYTE(v17[60].lpVtbl) = 1;
    }
    v33 = CAcm::StoreParentCMUnknown((CAcm *)v17, *((void **)this + 7));
    if ( v33 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v33, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0xA5u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v33, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0xA5u);
          if ( (bidGblFlags & 2) != 0 )
            v33 = bidTraceHR(
                    off_1800C84D0[0],
                    168969,
                    L"<CDBCreateSession::CreateSession|Trace|HR> ",
                    (unsigned int)v33);
        }
      }
      v54 = v33;
      throw (long *)&v54;
    }
    v17[44].lpVtbl = (struct IUnknownVtbl *)(*((_QWORD *)this + 7) + 408LL);
    ProviderInterface = CAcm::GetProviderInterface((CAcm *)v17, &IID_ITransactionJoin);
    if ( ProviderInterface )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ProviderInterface + 16LL))(ProviderInterface);
    }
    else
    {
      DynamicInterface = CAcm::FindDynamicInterface((CAcm *)v17, &IID_ITransactionJoin);
      if ( DynamicInterface )
        *((_BYTE *)DynamicInterface + 24) = 0;
    }
    if ( a2 )
    {
      *(_QWORD *)&v57.Data1 = 0;
      v36 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct _GUID *))v39->lpVtbl->QueryInterface)(
              v39,
              &IID_IOuterUnknown,
              &v57);
      if ( v36 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v36, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0xCAu);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v36, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0xCAu);
            if ( (bidGblFlags & 2) != 0 )
              v36 = bidTraceHR(
                      off_1800C84D0[0],
                      206857,
                      L"<CDBCreateSession::CreateSession|Trace|HR> ",
                      (unsigned int)v36);
          }
        }
        v55 = v36;
        throw (long *)&v55;
      }
      ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->Release)(v39);
      v39 = 0;
      (*(void (__fastcall **)(_QWORD, struct IUnknown *))(**(_QWORD **)&v57.Data1 + 40LL))(*(_QWORD *)&v57.Data1, a2);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v57.Data1 + 16LL))(*(_QWORD *)&v57.Data1);
      *a4 = v41;
    }
    else
    {
      v36 = ((__int64 (__fastcall *)(struct IUnknown *, const struct _GUID *, struct IUnknown **))v39->lpVtbl->QueryInterface)(
              v39,
              v5,
              a4);
      if ( v36 < 0 && (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v36, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0xBEu);
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800C8D18[0] )
            bidTraceA(off_1800C84D0[0], 195584, off_1800C8D18[0], 0);
        }
      }
      ((void (__fastcall *)(struct IUnknown *))v41->lpVtbl->Release)(v41);
      ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->Release)(v39);
    }
  }
  catch ( long v56 )
  {
    v38 = v56;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v56, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0xE2u);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800C8D10[0] )
          bidTraceA(off_1800C84D0[0], 232448, off_1800C8D10[0], v38);
      }
    }
    v40 = v38;
    goto LABEL_118;
  }
  catch ( ... )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147418113, L"<CDBCreateSession::CreateSession|OLEDB|ERR> ", 0xE9u);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800C8D08[0] )
          bidTraceA(off_1800C84D0[0], 239616, off_1800C8D08[0], 0);
      }
    }
    v40 = -2147418113;
LABEL_118:
    v37 = v40;
    if ( v40 >= 0 )
      v37 = -2147418113;
    try
    {
      v40 = v37;
      if ( v58 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      if ( a4 )
      {
        if ( *a4 )
          ((void (__fastcall *)(_QWORD))(*a4)->lpVtbl->Release)(*a4);
        *a4 = 0;
      }
      if ( v39 )
      {
        ((void (__fastcall *)(struct IUnknown *))v39->lpVtbl->Release)(v39);
        v39 = 0;
      }
      if ( v41 )
      {
        ((void (__fastcall *)(struct IUnknown *))v41->lpVtbl->Release)(v41);
        v41 = 0;
      }
      if ( v42 )
      {
        (*((void (__fastcall **)(struct IUnknownVtbl *))v42->QueryInterface + 2))(v42);
        v42 = 0;
      }
      *a4 = 0;
    }
    catch ( ... )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800C8D00[0] )
        bidTraceA(off_1800C84D0[0], 291840, off_1800C8D00[0], 0);
      v37 = v40;
    }
    if ( (bidGblFlags & 2) != 0 )
      return (unsigned int)bidTraceHR(off_1800C84D0[0], 293897, L"<CDBCreateSession::CreateSession|Trace|HR> ", v37);
    return v37;
  }
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(
                           off_1800C84D0[0],
                           244745,
                           L"<CDBCreateSession::CreateSession|Trace|HR> ",
                           (unsigned int)v36);
  return (unsigned int)v36;
}

```

## disassembly

```asm
0x18001c2b0  mov     rax, rsp
0x18001c2b3  mov     [rax+8], rbx
0x18001c2b7  mov     [rax+10h], rsi
0x18001c2bb  mov     [rax+20h], r9
0x18001c2bf  mov     [rax+18h], r8
0x18001c2c3  push    rdi
0x18001c2c4  push    r12
0x18001c2c6  push    r13
0x18001c2c8  push    r14
0x18001c2ca  push    r15
0x18001c2cc  sub     rsp, 0B0h
0x18001c2d3  mov     r12, r9
0x18001c2d6  mov     r14, r8
0x18001c2d9  mov     r13, rdx
0x18001c2dc  mov     r15, rcx
0x18001c2df  xor     edi, edi
0x18001c2e1  mov     [rsp+0D8h+var_98], rdi
0x18001c2e6  mov     [rsp+0D8h+var_A8], rdi
0x18001c2eb  mov     [rsp+0D8h+var_90], rdi
0x18001c2f0  mov     [rsp+0D8h+var_38], rdi
0x18001c2f8  test    r9, r9
0x18001c2fb  jnz     short loc_18001C34E
0x18001c2fd  mov     eax, cs:_bidGblFlags
0x18001c303  mov     bl, 2
0x18001c305  mov     edi, 80070057h
0x18001c30a  test    bl, al
0x18001c30c  jz      short loc_18001C347
0x18001c30e  lea     r8d, [r9+31h]; unsigned int
0x18001c312  lea     rdx, aCdbcreatesessi_2; "<CDBCreateSession::CreateSession|OLEDB|"...
0x18001c319  mov     ecx, edi; int
0x18001c31b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001c320  mov     eax, cs:_bidGblFlags
0x18001c326  test    bl, al
0x18001c328  jz      short loc_18001C347
0x18001c32a  mov     r9d, edi
0x18001c32d  lea     r8, aCdbcreatesessi_0; "<CDBCreateSession::CreateSession|Trace|"...
0x18001c334  mov     edx, 0C409h
0x18001c339  mov     rcx, cs:off_1800C84D0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001c340  call    _bidTraceHR
0x18001c345  mov     edi, eax
0x18001c347  mov     eax, edi
0x18001c349  jmp     loc_18001CE89
0x18001c34e  mov     [r9], rdi
0x18001c351  test    r13, r13
0x18001c354  jz      short loc_18001C39D
0x18001c356  mov     rax, [r8]
0x18001c359  sub     rax, qword ptr cs:IID_IUnknown.Data1
0x18001c360  jnz     short loc_18001C36D
0x18001c362  mov     rax, [r8+8]
0x18001c366  sub     rax, qword ptr cs:IID_IUnknown.Data4
0x18001c36d  test    rax, rax
0x18001c370  jz      short loc_18001C39D
0x18001c372  mov     bl, 2
0x18001c374  test    byte ptr cs:_bidGblFlags, bl
0x18001c37a  jz      short loc_18001C393
0x18001c37c  mov     r8d, 37h ; '7'; unsigned int
0x18001c382  lea     rdx, aCdbcreatesessi_2; "<CDBCreateSession::CreateSession|OLEDB|"...
0x18001c389  mov     ecx, 80040E22h; int
0x18001c38e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001c393  mov     eax, 80040E22h
0x18001c398  jmp     loc_18001CE89
0x18001c39d  mov     rcx, [rcx+38h]
0x18001c3a1  cmp     [rcx+331h], dil
0x18001c3a8  jnz     short loc_18001C3FD
0x18001c3aa  mov     eax, cs:_bidGblFlags
0x18001c3b0  mov     bl, 2
0x18001c3b2  mov     esi, 8000FFFFh
0x18001c3b7  test    bl, al
0x18001c3b9  jz      short loc_18001C3F6
0x18001c3bb  mov     r8d, 3Bh ; ';'; unsigned int
0x18001c3c1  lea     rdx, aCdbcreatesessi_2; "<CDBCreateSession::CreateSession|OLEDB|"...
0x18001c3c8  mov     ecx, esi; int
0x18001c3ca  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001c3cf  mov     eax, cs:_bidGblFlags
0x18001c3d5  test    bl, al
0x18001c3d7  jz      short loc_18001C3F6
0x18001c3d9  mov     r9d, esi
0x18001c3dc  lea     r8, aCdbcreatesessi_0; "<CDBCreateSession::CreateSession|Trace|"...
0x18001c3e3  mov     edx, 0EC09h
0x18001c3e8  mov     rcx, cs:off_1800C84D0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001c3ef  call    _bidTraceHR
0x18001c3f4  mov     esi, eax
0x18001c3f6  mov     eax, esi
0x18001c3f8  jmp     loc_18001CE89
0x18001c3fd  add     rcx, 0B8h
0x18001c404  mov     rax, [rcx]
0x18001c407  lea     rdx, [rsp+0D8h+var_98]
0x18001c40c  mov     rax, [rax+20h]
0x18001c410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c415  test    eax, eax
0x18001c417  jnz     loc_18001C4C3
0x18001c41d  mov     rcx, [rsp+0D8h+var_98]
0x18001c422  mov     rax, [rcx]
0x18001c425  lea     r8, [rsp+0D8h+var_A8]
0x18001c42a  lea     rdx, IID_IService
0x18001c431  mov     rax, [rax]
0x18001c434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c439  mov     esi, eax
0x18001c43b  test    eax, eax
0x18001c43d  jns     short loc_18001C4B9
0x18001c43f  mov     eax, cs:_bidGblFlags
0x18001c445  mov     bl, 2
0x18001c447  test    bl, al
0x18001c449  jz      short loc_18001C4A4
0x18001c44b  mov     r8d, 40h ; '@'; unsigned int
0x18001c451  lea     rdx, aCdbcreatesessi_2; "<CDBCreateSession::CreateSession|OLEDB|"...
0x18001c458  mov     ecx, esi; int
0x18001c45a  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001c45f  mov     eax, cs:_bidGblFlags
0x18001c465  test    bl, al
0x18001c467  jz      short loc_18001C4A4
0x18001c469  mov     r8d, 40h ; '@'; unsigned int
0x18001c46f  lea     rdx, aCdbcreatesessi_2; "<CDBCreateSession::CreateSession|OLEDB|"...
0x18001c476  mov     ecx, esi; int
0x18001c478  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001c47d  mov     eax, cs:_bidGblFlags
0x18001c483  test    bl, al
0x18001c485  jz      short loc_18001C4A4
0x18001c487  mov     r9d, esi
0x18001c48a  lea     r8, aCdbcreatesessi_0; "<CDBCreateSession::CreateSession|Trace|"...
0x18001c491  mov     edx, 10009h
0x18001c496  mov     rcx, cs:off_1800C84D0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001c49d  call    _bidTraceHR
0x18001c4a2  mov     esi, eax
0x18001c4a4  mov     [rsp+0D8h+pExceptionObject], esi
0x18001c4a8  lea     rdx, _TI1J; pThrowInfo
0x18001c4af  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x18001c4b4  call    _CxxThrowException_0
0x18001c4b9  mov     rbx, [rsp+0D8h+var_A8]
0x18001c4be  jmp     loc_18001C946
0x18001c4c3  lea     r9, [rsp+0D8h+var_98]
0x18001c4c8  call    ?CoCreateCM@?$NewCM@VCSCM@@@@SAJPEAUIUnknown@@KAEBU_GUID@@PEAPEAX@Z; NewCM<CSCM>::CoCreateCM(IUnknown *,ulong,_GUID const &,void * *)
0x18001c4cd  mov     esi, eax
0x18001c4cf  test    eax, eax
0x18001c4d1  jns     short loc_18001C54D
0x18001c4d3  mov     eax, cs:_bidGblFlags
0x18001c4d9  mov     bl, 2
0x18001c4db  test    bl, al
0x18001c4dd  jz      short loc_18001C538
0x18001c4df  mov     r8d, 4Ch ; 'L'; unsigned int
0x18001c4e5  lea     rdx, aCdbcreatesessi_2; "<CDBCreateSession::CreateSession|OLEDB|"...
0x18001c4ec  mov     ecx, esi; int
0x18001c4ee  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001c4f3  mov     eax, cs:_bidGblFlags
0x18001c4f9  test    bl, al
0x18001c4fb  jz      short loc_18001C538
0x18001c4fd  mov     r8d, 4Ch ; 'L'; unsigned int
0x18001c503  lea     rdx, aCdbcreatesessi_2; "<CDBCreateSession::CreateSession|OLEDB|"...
0x18001c50a  mov     ecx, esi; int
0x18001c50c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001c511  mov     eax, cs:_bidGblFlags
0x18001c517  test    bl, al
0x18001c519  jz      short loc_18001C538
0x18001c51b  mov     r9d, esi
0x18001c51e  lea     r8, aCdbcreatesessi_0; "<CDBCreateSession::CreateSession|Trace|"...
0x18001c525  mov     edx, 13009h
0x18001c52a  mov     rcx, cs:off_1800C84D0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001c531  call    _bidTraceHR
0x18001c536  mov     esi, eax
0x18001c538  mov     [rsp+0D8h+var_84], esi
0x18001c53c  lea     rdx, _TI1J; pThrowInfo
0x18001c543  lea     rcx, [rsp+0D8h+var_84]; pExceptionObject
0x18001c548  call    _CxxThrowException_0
0x18001c54d  mov     rcx, [rsp+0D8h+var_98]
0x18001c552  test    rcx, rcx
0x18001c555  jnz     short loc_18001C5B6
0x18001c557  mov     eax, cs:_bidGblFlags
0x18001c55d  mov     bl, 2
0x18001c55f  mov     esi, 8000FFFFh
0x18001c564  test    bl, al
0x18001c566  jz      short loc_18001C5A1
0x18001c568  lea     r8d, [rcx+4Eh]; unsigned int
0x18001c56c  lea     rdx, aCdbcreatesessi_2; "<CDBCreateSession::CreateSession|OLEDB|"...
0x18001c573  mov     ecx, esi; int
0x18001c575  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001c57a  mov     eax, cs:_bidGblFlags
0x18001c580  test    bl, al
0x18001c582  jz      short loc_18001C5A1
0x18001c584  mov     r9d, esi
0x18001c587  lea     r8, aCdbcreatesessi_0; "<CDBCreateSession::CreateSession|Trace|"...
0x18001c58e  mov     edx, 13809h
0x18001c593  mov     rcx, cs:off_1800C84D0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001c59a  call    _bidTraceHR
0x18001c59f  mov     esi, eax
0x18001c5a1  mov     [rsp+0D8h+var_80], esi
0x18001c5a5  lea     rdx, _TI1J; pThrowInfo
0x18001c5ac  lea     rcx, [rsp+0D8h+var_80]; pExceptionObject
0x18001c5b1  call    _CxxThrowException_0
0x18001c5b6  mov     rax, [rcx]
0x18001c5b9  lea     r8, [rsp+0D8h+var_A8]
0x18001c5be  lea     rdx, IID_IService
0x18001c5c5  mov     rax, [rax]
0x18001c5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5cd  mov     esi, eax
0x18001c5cf  test    eax, eax
0x18001c5d1  jns     short loc_18001C64D
0x18001c5d3  mov     eax, cs:_bidGblFlags
0x18001c5d9  mov     bl, 2
0x18001c5db  test    bl, al
0x18001c5dd  jz      short loc_18001C638
0x18001c5df  mov     r8d, 51h ; 'Q'; unsigned int
0x18001c5e5  lea     rdx, aCdbcreatesessi_2; "<CDBCreateSession::CreateSession|OLEDB|"...
0x18001c5ec  mov     ecx, esi; int
0x18001c5ee  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001c5f3  mov     eax, cs:_bidGblFlags
0x18001c5f9  test    bl, al
0x18001c5fb  jz      short loc_18001C638
0x18001c5fd  mov     r8d, 51h ; 'Q'; unsigned int
0x18001c603  lea     rdx, aCdbcreatesessi_2; "<CDBCreateSession::CreateSession|OLEDB|"...
0x18001c60a  mov     ecx, esi; int
0x18001c60c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001c611  mov     eax, cs:_bidGblFlags
0x18001c617  test    bl, al
0x18001c619  jz      short loc_18001C638
0x18001c61b  mov     r9d, esi
0x18001c61e  lea     r8, aCdbcreatesessi_0; "<CDBCreateSession::CreateSession|Trace|"...
0x18001c625  mov     edx, 14409h
0x18001c62a  mov     rcx, cs:off_1800C84D0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001c631  call    _bidTraceHR
0x18001c636  mov     esi, eax
0x18001c638  mov     [rsp+0D8h+var_7C], esi
0x18001c63c  lea     rdx, _TI1J; pThrowInfo
0x18001c643  lea     rcx, [rsp+0D8h+var_7C]; pExceptionObject
0x18001c648  call    _CxxThrowException_0
0x18001c64d  mov     rbx, [rsp+0D8h+var_A8]
0x18001c652  lea     rdx, IID_IDBCreateSession
0x18001c659  mov     rcx, [r15+38h]
0x18001c65d  call    ??$GetProviderPointer@VCDCM@@@@YAPEAXPEAV?$CComObject@VCDCM@@@ATL@@AEBU_GUID@@@Z; GetProviderPointer<CDCM>(ATL::CComObject<CDCM> *,_GUID const &)
0x18001c662  mov     r14, rax
0x18001c665  mov     [rsp+0D8h+var_38], rax
0x18001c66d  test    rax, rax
0x18001c670  jnz     short loc_18001C6D1
0x18001c672  mov     eax, cs:_bidGblFlags
0x18001c678  mov     bl, 2
0x18001c67a  mov     esi, 8000FFFFh
0x18001c67f  test    bl, al
0x18001c681  jz      short loc_18001C6BC
0x18001c683  lea     r8d, [r14+5Ch]; unsigned int
0x18001c687  lea     rdx, aCdbcreatesessi_2; "<CDBCreateSession::CreateSession|OLEDB|"...
0x18001c68e  mov     ecx, esi; int
0x18001c690  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001c695  mov     eax, cs:_bidGblFlags
0x18001c69b  test    bl, al
0x18001c69d  jz      short loc_18001C6BC
0x18001c69f  mov     r9d, esi
0x18001c6a2  lea     r8, aCdbcreatesessi_0; "<CDBCreateSession::CreateSession|Trace|"...
0x18001c6a9  mov     edx, 17009h
0x18001c6ae  mov     rcx, cs:off_1800C84D0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001c6b5  call    _bidTraceHR
0x18001c6ba  mov     esi, eax
0x18001c6bc  mov     [rsp+0D8h+var_78], esi
0x18001c6c0  lea     rdx, _TI1J; pThrowInfo
0x18001c6c7  lea     rcx, [rsp+0D8h+var_78]; pExceptionObject
0x18001c6cc  call    _CxxThrowException_0
0x18001c6d1  mov     rax, [rax]
0x18001c6d4  lea     r9, [rsp+0D8h+var_90]
0x18001c6d9  lea     r8, IID_IUnknown
0x18001c6e0  mov     rdx, [rsp+0D8h+var_A8]
0x18001c6e5  mov     rcx, r14
0x18001c6e8  mov     rax, [rax+18h]
0x18001c6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6f1  mov     esi, eax
0x18001c6f3  test    eax, eax
0x18001c6f5  jns     short loc_18001C771
0x18001c6f7  mov     eax, cs:_bidGblFlags
0x18001c6fd  mov     bl, 2
0x18001c6ff  test    bl, al
0x18001c701  jz      short loc_18001C75C
0x18001c703  mov     r8d, 5Eh ; '^'; unsigned int
0x18001c709  lea     rdx, aCdbcreatesessi_2; "<CDBCreateSession::CreateSession|OLEDB|"...
0x18001c710  mov     ecx, esi; int
0x18001c712  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001c717  mov     eax, cs:_bidGblFlags
0x18001c71d  test    bl, al
0x18001c71f  jz      short loc_18001C75C
0x18001c721  mov     r8d, 5Eh ; '^'; unsigned int
0x18001c727  lea     rdx, aCdbcreatesessi_2; "<CDBCreateSession::CreateSession|OLEDB|"...
0x18001c72e  mov     ecx, esi; int
0x18001c730  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001c735  mov     eax, cs:_bidGblFlags
0x18001c73b  test    bl, al
0x18001c73d  jz      short loc_18001C75C
0x18001c73f  mov     r9d, esi
0x18001c742  lea     r8, aCdbcreatesessi_0; "<CDBCreateSession::CreateSession|Trace|"...
0x18001c749  mov     edx, 17809h
0x18001c74e  mov     rcx, cs:off_1800C84D0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001c755  call    _bidTraceHR
0x18001c75a  mov     esi, eax
0x18001c75c  mov     [rsp+0D8h+var_74], esi
0x18001c760  lea     rdx, _TI1J; pThrowInfo
0x18001c767  lea     rcx, [rsp+0D8h+var_74]; pExceptionObject
0x18001c76c  call    _CxxThrowException_0
0x18001c771  mov     rdx, [rsp+0D8h+var_90]
0x18001c776  test    rdx, rdx
0x18001c779  jnz     short loc_18001C7DA
0x18001c77b  mov     eax, cs:_bidGblFlags
0x18001c781  mov     bl, 2
0x18001c783  mov     esi, 8000FFFFh
0x18001c788  test    bl, al
0x18001c78a  jz      short loc_18001C7C5
  ... truncated ...
```
