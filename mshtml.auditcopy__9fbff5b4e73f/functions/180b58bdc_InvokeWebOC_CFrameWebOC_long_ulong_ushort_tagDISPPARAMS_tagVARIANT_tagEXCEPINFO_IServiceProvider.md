# InvokeWebOC(CFrameWebOC *,long,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,IServiceProvider *)

- ea: `0x180b58bdc`
- end: `0x180b59d9c`
- name: `?InvokeWebOC@@YAJPEAVCFrameWebOC@@JKGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAUIServiceProvider@@@Z`
- size: `4544`
- prototype: `__int64 __fastcall(struct CFrameWebOC *, int, unsigned int, unsigned __int16, struct tagDISPPARAMS *, VARIANTARG *pvarg, struct tagEXCEPINFO *, struct IServiceProvider *)`
- caller_count: `2`
- callee_count: `59`
- tags: `service_task, broker_com_uri`

## callers

- `0x180b58af0`
- `0x180e5e890`

## callees

- `0x18000a620`
- `0x1800ea428`
- `0x180303f98`
- `0x1807f1950`
- `0x1807ffe90`
- `0x1807fff00`
- `0x180804b40`
- `0x180804cb0`
- `0x18080e270`
- `0x18081e990`
- `0x18081e9d0`
- `0x1808255e0`
- `0x18082c3f0`
- `0x1808332f0`
- `0x180836700`
- `0x18083a1b0`
- `0x180b553c0`
- `0x180b55e60`
- `0x180b55ef0`
- `0x180b55f80`
- `0x180b56680`
- `0x180b569c0`
- `0x180b56b30`
- `0x180b56b80`
- `0x180b56bd0`
- `0x180b56c30`
- `0x180b56d10`
- `0x180b56d60`
- `0x180b56de0`
- `0x180b56e80`
- `0x180b56ef0`
- `0x180b56f40`
- `0x180b56fa0`
- `0x180b56ff0`
- `0x180b57100`
- `0x180b57160`
- `0x180b571a0`
- `0x180b571f0`
- `0x180b57240`
- `0x180b57290`
- `0x180b572d0`
- `0x180b57320`
- `0x180b57370`
- `0x180b573d0`
- `0x180b57430`
- `0x180b57550`
- `0x180b57590`
- `0x180b575d0`
- `0x180b57610`
- `0x180b57650`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x180b58c25`
- `OLEAUT32!__imp_VariantInit` at `0x180b58c73`
- `OLEAUT32!__imp_VariantInit` at `0x180b59419`
- `OLEAUT32!__imp_VariantInit` at `0x180b58c25`
- `OLEAUT32!__imp_VariantInit` at `0x180b58c73`
- `OLEAUT32!__imp_VariantInit` at `0x180b59419`
- `OLEAUT32!__imp_VariantClear` at `0x180b58f45`
- `OLEAUT32!__imp_VariantClear` at `0x180b58f55`
- `OLEAUT32!__imp_VariantClear` at `0x180b58f65`
- `OLEAUT32!__imp_VariantClear` at `0x180b58f76`
- `OLEAUT32!__imp_VariantClear` at `0x180b5989b`
- `OLEAUT32!__imp_VariantClear` at `0x180b59aba`
- `OLEAUT32!__imp_VariantClear` at `0x180b59aca`
- `OLEAUT32!__imp_VariantClear` at `0x180b59ada`
- `OLEAUT32!__imp_VariantClear` at `0x180b58f45`
- `OLEAUT32!__imp_VariantClear` at `0x180b58f55`
- `OLEAUT32!__imp_VariantClear` at `0x180b58f65`
- `OLEAUT32!__imp_VariantClear` at `0x180b58f76`
- `OLEAUT32!__imp_VariantClear` at `0x180b5989b`
- `OLEAUT32!__imp_VariantClear` at `0x180b59aba`
- `OLEAUT32!__imp_VariantClear` at `0x180b59aca`
- `OLEAUT32!__imp_VariantClear` at `0x180b59ada`
- `OLEAUT32!__imp_VariantCopy` at `0x180b58ead`
- `OLEAUT32!__imp_VariantCopy` at `0x180b58ecc`
- `OLEAUT32!__imp_VariantCopy` at `0x180b58eeb`
- `OLEAUT32!__imp_VariantCopy` at `0x180b58f0b`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59868`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59887`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59936`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59a23`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59a42`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59a61`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59a80`
- `OLEAUT32!__imp_VariantCopy` at `0x180b58ead`
- `OLEAUT32!__imp_VariantCopy` at `0x180b58ecc`
- `OLEAUT32!__imp_VariantCopy` at `0x180b58eeb`
- `OLEAUT32!__imp_VariantCopy` at `0x180b58f0b`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59868`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59887`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59936`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59a23`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59a42`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59a61`
- `OLEAUT32!__imp_VariantCopy` at `0x180b59a80`
- `OLEAUT32!__imp_VariantChangeType` at `0x180b58c8d`
- `OLEAUT32!__imp_VariantChangeType` at `0x180b58c8d`

## pseudocode

```c
__int64 __fastcall InvokeWebOC(
        struct CFrameWebOC *a1,
        int a2,
        unsigned int a3,
        unsigned __int16 a4,
        struct tagDISPPARAMS *a5,
        VARIANTARG *pvarg,
        struct tagEXCEPINFO *a7,
        struct IServiceProvider *a8)
{
  struct tagVARIANT *v8; // r14
  UINT cArgs; // eax
  HRESULT v10; // eax
  VARIANTARG *p_pvargDest; // rcx
  int Busy; // eax
  unsigned int v13; // ebx
  UINT v14; // edx
  VARIANTARG *rgvarg; // rbx
  UINT v16; // edx
  UINT v17; // edx
  UINT v18; // edx
  const VARIANTARG *v19; // rax
  const VARIANTARG *v20; // rax
  const VARIANTARG *v21; // rax
  const VARIANTARG *v22; // rax
  VARIANTARG *v23; // rcx
  unsigned int Application; // eax
  bool v25; // zf
  CMarkup **v26; // rcx
  struct CFrameSite *FrameSite; // rax
  __int64 v28; // rax
  __int16 v29; // cx
  UINT v30; // eax
  UINT v31; // ecx
  VARIANTARG *v32; // rbx
  UINT v33; // ecx
  const VARIANTARG *v34; // rax
  const VARIANTARG *v35; // rax
  UINT v36; // edx
  struct tagVARIANT *v37; // rax
  int v38; // edx
  struct tagVARIANT *v39; // r9
  enum OLECMDID v40; // edi
  enum OLECMDEXECOPT v41; // r14d
  struct tagVARIANT *v42; // rbx
  const VARIANTARG *v43; // rax
  enum OLECMDID lVal; // edx
  UINT v45; // ecx
  VARIANTARG *v46; // rbx
  UINT v47; // ecx
  UINT v48; // ecx
  UINT v49; // ecx
  const VARIANTARG *v50; // rax
  const VARIANTARG *v51; // rax
  const VARIANTARG *v52; // rax
  const VARIANTARG *v53; // rax
  VARIANTARG v55; // [rsp+40h] [rbp-89h] BYREF
  __int64 v56; // [rsp+58h] [rbp-71h]
  VARIANTARG v57; // [rsp+60h] [rbp-69h] BYREF
  VARIANTARG v58; // [rsp+78h] [rbp-51h] BYREF
  VARIANTARG v59; // [rsp+90h] [rbp-39h] BYREF
  VARIANTARG pvargDest; // [rsp+A8h] [rbp-21h] BYREF

  v8 = 0;
  memset(&pvargDest, 0, sizeof(pvargDest));
  if ( pvarg )
    VariantInit(pvarg);
  *((_BYTE *)a1 + 77) |= 2u;
  if ( a5 )
  {
    cArgs = a5->cArgs;
    if ( cArgs )
    {
      v8 = DerefVariant(&a5->rgvarg[cArgs - 1]);
      if ( v8->vt == 2 )
      {
        VariantInit(&pvargDest);
        v10 = VariantChangeType(&pvargDest, v8, 0, 3u);
        p_pvargDest = &pvargDest;
        if ( v10 )
          p_pvargDest = v8;
        v8 = p_pvargDest;
      }
    }
  }
  if ( a2 <= 212 )
  {
    if ( a2 == 212 )
    {
      if ( (a4 & 2) == 0 )
        goto LABEL_341;
      if ( pvarg )
      {
        pvarg->vt = 11;
        Busy = CFrameWebOC::get_Busy((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->iVal);
        goto LABEL_334;
      }
      goto LABEL_340;
    }
    if ( a2 <= 200 )
    {
      if ( a2 != 200 )
      {
        if ( a2 <= 101 )
        {
          switch ( a2 )
          {
            case 101:
              if ( (a4 & 1) != 0 )
              {
                Busy = CFrameWebOC::GoForward((struct CFrameWebOC *)((char *)a1 + 48));
                goto LABEL_334;
              }
              goto LABEL_341;
            case -550:
              if ( (a4 & 1) != 0 )
              {
                Busy = CFrameWebOC::Refresh((struct CFrameWebOC *)((char *)a1 + 48));
                goto LABEL_334;
              }
              goto LABEL_341;
            case -525:
              if ( (a4 & 2) == 0 )
                goto LABEL_341;
              if ( pvarg )
              {
                pvarg->vt = 3;
                Busy = CFrameWebOC::get_ReadyState(
                         (struct CFrameWebOC *)((char *)a1 + 48),
                         (enum tagREADYSTATE *)&pvarg->lVal);
                goto LABEL_334;
              }
              goto LABEL_340;
          }
          if ( a2 != -515 )
          {
            if ( a2 )
            {
              if ( a2 == 100 )
              {
                if ( (a4 & 1) != 0 )
                {
                  Busy = CFrameWebOC::GoBack((struct CFrameWebOC *)((char *)a1 + 48));
LABEL_334:
                  v13 = Busy;
                  goto LABEL_342;
                }
LABEL_341:
                v13 = -2147352573;
                goto LABEL_342;
              }
LABEL_299:
              Busy = CDocument::InvokeEx(*(CDocument **)(*((_QWORD *)a1 + 7) + 120LL), a2, a3, a4, a5, pvarg, a7, a8);
              goto LABEL_334;
            }
            if ( (a4 & 2) == 0 )
              goto LABEL_341;
            if ( pvarg )
            {
              pvarg->vt = 8;
              Busy = CFrameWebOC::get_Name((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->bstrVal);
              goto LABEL_334;
            }
            goto LABEL_340;
          }
          if ( (a4 & 2) == 0 )
            goto LABEL_341;
          if ( !pvarg )
            goto LABEL_340;
          pvarg->vt = 20;
          pvarg->llVal = 0;
          goto LABEL_28;
        }
        if ( a2 == 102 )
        {
          if ( (a4 & 1) != 0 )
          {
            Busy = CFrameWebOC::GoHome((struct CFrameWebOC *)((char *)a1 + 48));
            goto LABEL_334;
          }
          goto LABEL_341;
        }
        if ( a2 == 103 )
        {
          if ( (a4 & 1) != 0 )
          {
            Busy = CFrameWebOC::GoSearch((struct CFrameWebOC *)((char *)a1 + 48));
            goto LABEL_334;
          }
          goto LABEL_341;
        }
        if ( a2 != 104 )
        {
          if ( a2 == 105 )
          {
            if ( (a4 & 1) != 0 )
            {
              Busy = CFrameWebOC::Refresh2((struct CFrameWebOC *)((char *)a1 + 48), v8);
              goto LABEL_334;
            }
            goto LABEL_341;
          }
          if ( a2 == 106 )
          {
            if ( (a4 & 1) != 0 )
            {
              Busy = CFrameWebOC::Stop((struct CFrameWebOC *)((char *)a1 + 48));
              goto LABEL_334;
            }
            goto LABEL_341;
          }
          goto LABEL_299;
        }
        if ( (a4 & 1) == 0 )
          goto LABEL_341;
        if ( a5 )
        {
          v14 = a5->cArgs;
          if ( v14 )
          {
            if ( v8->vt )
            {
              if ( v8->vt != 8 )
              {
LABEL_50:
                v13 = -2147352568;
                goto LABEL_342;
              }
              rgvarg = a5->rgvarg;
              v56 = 0;
              *(_OWORD *)&v55.decVal.Lo32 = 0;
              memset(&v57, 0, sizeof(v57));
              memset(&v59, 0, sizeof(v59));
              memset(&v58, 0, sizeof(v58));
              v16 = v14 - 2;
              if ( v16 )
              {
                v17 = v16 - 1;
                if ( v17 )
                {
                  v18 = v17 - 1;
                  if ( v18 )
                  {
                    if ( v18 != 1 )
                    {
LABEL_59:
                      v13 = CFrameWebOC::Navigate(
                              (struct CFrameWebOC *)((char *)a1 + 48),
                              v8->bstrVal,
                              (struct tagVARIANT *)&v55.decVal.8,
                              &v57,
                              &v59,
                              &v58);
                      VariantClear(&v58);
                      VariantClear(&v59);
                      VariantClear(&v57);
LABEL_60:
                      v23 = (VARIANTARG *)&v55.decVal.8;
LABEL_61:
                      VariantClear(v23);
                      goto LABEL_342;
                    }
                    v19 = DerefVariant(rgvarg);
                    VariantCopy(&v58, v19);
                    ++rgvarg;
                  }
                  v20 = DerefVariant(rgvarg);
                  VariantCopy(&v59, v20);
                  ++rgvarg;
                }
                v21 = DerefVariant(rgvarg);
                VariantCopy(&v57, v21);
                ++rgvarg;
              }
              v22 = DerefVariant(rgvarg);
              VariantCopy((VARIANTARG *)&v55.decVal.8, v22);
              goto LABEL_59;
            }
          }
        }
LABEL_340:
        v13 = -2147352561;
        goto LABEL_342;
      }
      if ( (a4 & 2) == 0 )
        goto LABEL_341;
      if ( !pvarg )
        goto LABEL_340;
      Application = CFrameWebOC::get_Application((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->pdispVal);
      goto LABEL_69;
    }
    if ( a2 > 206 )
    {
      if ( a2 == 207 )
      {
        if ( (a4 & 2) != 0 )
        {
          if ( pvarg )
          {
            pvarg->vt = 3;
            Busy = CFrameWebOC::get_Top((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->lVal);
            goto LABEL_334;
          }
          goto LABEL_340;
        }
        if ( (a4 & 4) == 0 )
          goto LABEL_341;
        if ( a5 && a5->cArgs )
        {
          if ( v8->vt == 3 )
          {
            Busy = CFrameWebOC::put_Top((struct CFrameWebOC *)((char *)a1 + 48), v8->iVal);
            goto LABEL_334;
          }
          goto LABEL_50;
        }
      }
      else if ( a2 == 208 )
      {
        if ( (a4 & 2) != 0 )
        {
          if ( pvarg )
          {
            pvarg->vt = 3;
            Busy = CFrameWebOC::get_Width((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->lVal);
            goto LABEL_334;
          }
          goto LABEL_340;
        }
        if ( (a4 & 4) == 0 )
          goto LABEL_341;
        if ( a5 && a5->cArgs )
        {
          if ( v8->vt == 3 )
          {
            Busy = CFrameWebOC::put_Width((struct CFrameWebOC *)((char *)a1 + 48), v8->iVal);
            goto LABEL_334;
          }
          goto LABEL_50;
        }
      }
      else
      {
        if ( a2 != 209 )
        {
          if ( a2 == 210 )
          {
            if ( (a4 & 2) == 0 )
              goto LABEL_341;
            if ( pvarg )
            {
              pvarg->vt = 8;
              Busy = CFrameWebOC::get_LocationName((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->bstrVal);
              goto LABEL_334;
            }
          }
          else
          {
            if ( a2 != 211 )
              goto LABEL_299;
            if ( (a4 & 2) == 0 )
              goto LABEL_341;
            if ( pvarg )
            {
              pvarg->vt = 8;
              Busy = CFrameWebOC::get_LocationURL((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->bstrVal);
              goto LABEL_334;
            }
          }
          goto LABEL_340;
        }
        if ( (a4 & 2) != 0 )
        {
          if ( pvarg )
          {
            pvarg->vt = 3;
            Busy = CFrameWebOC::get_Height((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->lVal);
            goto LABEL_334;
          }
          goto LABEL_340;
        }
        if ( (a4 & 4) == 0 )
          goto LABEL_341;
        if ( a5 && a5->cArgs )
        {
          if ( v8->vt == 3 )
          {
            Busy = CFrameWebOC::put_Height((struct CFrameWebOC *)((char *)a1 + 48), v8->lVal);
            goto LABEL_334;
          }
          goto LABEL_50;
        }
      }
      goto LABEL_340;
    }
    if ( a2 == 206 )
    {
      if ( (a4 & 2) != 0 )
      {
        if ( pvarg )
        {
          pvarg->vt = 3;
          Busy = CFrameWebOC::get_Left((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->lVal);
          goto LABEL_334;
        }
        goto LABEL_340;
      }
      if ( (a4 & 4) == 0 )
        goto LABEL_341;
      if ( a5 && a5->cArgs )
      {
        if ( v8->vt == 3 )
        {
          Busy = CFrameWebOC::put_Left((struct CFrameWebOC *)((char *)a1 + 48), v8->lVal);
          goto LABEL_334;
        }
        goto LABEL_50;
      }
      goto LABEL_340;
    }
    if ( a2 == 201 )
    {
      if ( (a4 & 2) == 0 )
        goto LABEL_341;
      if ( !pvarg )
        goto LABEL_340;
      Application = CFrameWebOC::get_Parent((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->pdispVal);
    }
    else
    {
      if ( a2 != 202 )
      {
        if ( a2 != 203 )
        {
          if ( a2 == 204 )
          {
            if ( (a4 & 2) == 0 )
              goto LABEL_341;
            if ( pvarg )
            {
              pvarg->vt = 11;
              Busy = CFrameWebOC::get_TopLevelContainer((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->iVal);
              goto LABEL_334;
            }
          }
          else
          {
            if ( a2 != 205 )
              goto LABEL_299;
            if ( (a4 & 2) == 0 )
              goto LABEL_341;
            if ( pvarg )
            {
              pvarg->vt = 8;
              Busy = CFrameWebOC::get_Type((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->bstrVal);
              goto LABEL_334;
            }
          }
          goto LABEL_340;
        }
        if ( (a4 & 2) == 0 )
          goto LABEL_341;
        if ( !pvarg )
          goto LABEL_340;
        pvarg->llVal = 0;
        if ( (*((_BYTE *)a1 + 16) & 1) == 0 && (*((_BYTE *)a1 + 16) & 2) == 0 )
        {
          v26 = (CMarkup **)*((_QWORD *)a1 + 7);
          if ( v26 )
          {
            v13 = 0;
            FrameSite = CWindow::GetFrameSite(v26);
            if ( FrameSite )
            {
              v28 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)FrameSite + 11) + 8LL))((__int64)FrameSite + 88);
              v13 = (*(__int64 (__fastcall **)(__int64, CY *))(*(_QWORD *)v28 + 8LL))(v28, &pvarg->cyVal);
            }
            ReleaseInterface(0);
            v25 = v13 == 0;
            goto LABEL_70;
          }
        }
LABEL_28:
        v13 = -2147467259;
        goto LABEL_342;
      }
      if ( (a4 & 2) == 0 )
        goto LABEL_341;
      if ( !pvarg )
        goto LABEL_340;
      Application = CFrameWebOC::get_Container((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->pdispVal);
    }
LABEL_69:
    v13 = Application;
    v25 = Application == 0;
LABEL_70:
    if ( v25 )
      pvarg->vt = 9;
    goto LABEL_342;
  }
  if ( a2 <= 407 )
  {
    if ( a2 == 407 )
    {
      if ( (a4 & 2) != 0 )
      {
        if ( pvarg )
        {
          pvarg->vt = 11;
          Busy = CFrameWebOC::get_FullScreen((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->iVal);
          goto LABEL_334;
        }
        goto LABEL_340;
      }
      if ( (a4 & 4) == 0 )
        goto LABEL_341;
      if ( a5 && a5->cArgs )
      {
        if ( v8->vt == 11 )
        {
          Busy = CFrameWebOC::put_FullScreen((struct CFrameWebOC *)((char *)a1 + 48), v8->iVal);
          goto LABEL_334;
        }
        goto LABEL_50;
      }
      goto LABEL_340;
    }
    if ( a2 > 401 )
    {
      if ( a2 == 402 )
      {
        if ( (a4 & 2) != 0 )
        {
          if ( pvarg )
          {
            pvarg->vt = 11;
            Busy = CFrameWebOC::get_Visible((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->iVal);
            goto LABEL_334;
          }
          goto LABEL_340;
        }
        if ( (a4 & 4) == 0 )
          goto LABEL_341;
        if ( a5 && a5->cArgs )
        {
          if ( v8->vt == 11 )
          {
            Busy = CFrameWebOC::put_Visible((struct CFrameWebOC *)((char *)a1 + 48), v8->iVal);
            goto LABEL_334;
          }
          goto LABEL_50;
        }
        goto LABEL_340;
      }
      if ( a2 == 403 )
      {
        if ( (a4 & 2) != 0 )
        {
          if ( pvarg )
          {
            pvarg->vt = 11;
            Busy = CFrameWebOC::get_StatusBar((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->iVal);
            goto LABEL_334;
          }
          goto LABEL_340;
        }
        if ( (a4 & 4) == 0 )
          goto LABEL_341;
        if ( a5 && a5->cArgs )
        {
          if ( v8->vt == 11 )
          {
            Busy = CFrameWebOC::put_StatusBar((struct CFrameWebOC *)((char *)a1 + 48), v8->iVal);
            goto LABEL_334;
          }
          goto LABEL_50;
        }
        goto LABEL_340;
      }
      if ( a2 != 404 )
      {
        if ( a2 == 405 )
        {
          if ( (a4 & 2) != 0 )
          {
            if ( pvarg )
            {
              pvarg->vt = 3;
              Busy = CFrameWebOC::get_ToolBar((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->lVal);
              goto LABEL_334;
            }
            goto LABEL_340;
          }
          if ( (a4 & 4) == 0 )
            goto LABEL_341;
          if ( a5 && a5->cArgs )
          {
            if ( v8->vt == 3 )
            {
              Busy = CFrameWebOC::put_ToolBar((struct CFrameWebOC *)((char *)a1 + 48), v8->lVal);
              goto LABEL_334;
            }
            goto LABEL_50;
          }
        }
        else
        {
          if ( a2 != 406 )
            goto LABEL_299;
          if ( (a4 & 2) != 0 )
          {
            if ( pvarg )
            {
              pvarg->vt = 11;
              Busy = CFrameWebOC::get_MenuBar((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->iVal);
              goto LABEL_334;
            }
            goto LABEL_340;
          }
          if ( (a4 & 4) == 0 )
            goto LABEL_341;
          if ( a5 && a5->cArgs )
          {
            if ( v8->vt == 11 )
            {
              Busy = CFrameWebOC::put_MenuBar((struct CFrameWebOC *)((char *)a1 + 48), v8->iVal);
              goto LABEL_334;
            }
            goto LABEL_50;
          }
        }
        goto LABEL_340;
      }
      if ( (a4 & 2) != 0 )
      {
        if ( pvarg )
        {
          pvarg->vt = 8;
          Busy = CFrameWebOC::get_StatusText((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->bstrVal);
          goto LABEL_334;
        }
        goto LABEL_340;
      }
      if ( (a4 & 4) == 0 )
        goto LABEL_341;
      if ( !a5 || !a5->cArgs )
        goto LABEL_340;
      Busy = -2147467259;
    }
    else
    {
      switch ( a2 )
      {
        case 401:
          if ( (a4 & 2) == 0 )
            goto LABEL_341;
          if ( !pvarg )
            goto LABEL_340;
          goto LABEL_156;
        case 300:
          v13 = (a4 & 1) != 0 ? -2147467259 : -2147352573;
          goto LABEL_342;
        case 301:
          if ( (a4 & 1) == 0 )
            goto LABEL_341;
          if ( !a5 )
            goto LABEL_340;
          v30 = a5->cArgs;
          if ( v30 < 2 )
            goto LABEL_340;
          if ( DerefVariant(&a5->rgvarg[v30 - 2])->vt != 3 && v8->vt != 3 )
            goto LABEL_50;
          goto LABEL_28;
      }
      if ( a2 != 302 )
      {
        if ( a2 == 303 )
        {
          if ( (a4 & 1) == 0 )
            goto LABEL_341;
          if ( !pvarg || !a5 || !a5->cArgs )
            goto LABEL_340;
          if ( v8->vt == 8 )
          {
            VariantInit(pvarg);
            v13 = -2147024891;
            goto LABEL_342;
          }
          goto LABEL_50;
        }
        if ( a2 != 400 )
          goto LABEL_299;
        if ( (a4 & 2) == 0 )
          goto LABEL_341;
        if ( !pvarg )
          goto LABEL_340;
LABEL_156:
        pvarg->vt = 8;
        Busy = CFrameWebOC::get_FullName((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->bstrVal);
        goto LABEL_334;
      }
      if ( (a4 & 1) == 0 )
        goto LABEL_341;
      if ( !a5 || a5->cArgs < 2 )
        goto LABEL_340;
      Busy = -2147024891;
    }
    v29 = 8;
LABEL_168:
    if ( v8->vt != v29 )
      Busy = -2147352568;
    goto LABEL_334;
  }
  if ( a2 <= 551 )
  {
    if ( a2 == 551 )
    {
      if ( (a4 & 2) != 0 )
      {
        if ( pvarg )
        {
          pvarg->vt = 11;
          Busy = CFrameWebOC::get_Silent((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->iVal);
          goto LABEL_334;
        }
        goto LABEL_340;
      }
      if ( (a4 & 4) == 0 )
        goto LABEL_341;
      if ( a5 && a5->cArgs )
      {
        if ( v8->vt == 11 )
        {
          Busy = CFrameWebOC::put_Silent((struct CFrameWebOC *)((char *)a1 + 48), v8->iVal);
          goto LABEL_334;
        }
        goto LABEL_50;
      }
      goto LABEL_340;
    }
    if ( a2 != 500 )
    {
      if ( a2 == 501 )
      {
        if ( (a4 & 1) == 0 )
          goto LABEL_341;
        if ( !pvarg || !a5 || !a5->cArgs )
          goto LABEL_340;
        if ( v8->vt == 3 )
        {
          lVal = v8->lVal;
          pvarg->vt = 3;
          Busy = CFrameWebOC::QueryStatusWB((struct CFrameWebOC *)((char *)a1 + 48), lVal, (enum OLECMDF *)&pvarg->lVal);
          goto LABEL_334;
        }
        goto LABEL_50;
      }
      if ( a2 != 502 )
      {
        if ( a2 != 503 )
        {
          if ( a2 != 550 )
            goto LABEL_299;
          if ( (a4 & 2) != 0 )
          {
            if ( pvarg )
            {
              pvarg->vt = 11;
              Busy = CFrameWebOC::get_Offline((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->iVal);
              goto LABEL_334;
            }
            goto LABEL_340;
          }
          if ( (a4 & 4) == 0 )
            goto LABEL_341;
          if ( a5 && a5->cArgs )
          {
            if ( v8->vt == 11 )
            {
              Busy = CFrameWebOC::put_Offline((struct CFrameWebOC *)((char *)a1 + 48), v8->iVal);
              goto LABEL_334;
            }
            goto LABEL_50;
          }
          goto LABEL_340;
        }
        if ( (a4 & 1) == 0 )
          goto LABEL_341;
        if ( !a5 )
          goto LABEL_340;
        v31 = a5->cArgs;
        if ( !v31 || !v8->vt )
          goto LABEL_340;
        v32 = a5->rgvarg;
        v56 = 0;
        memset(&v57, 0, sizeof(v57));
        *(_OWORD *)&v55.decVal.Lo32 = 0;
        v33 = v31 - 2;
        if ( v33 )
        {
          if ( v33 != 1 )
          {
LABEL_256:
            v13 = 0;
            VariantClear((VARIANTARG *)&v55.decVal.8);
            v23 = &v57;
            goto LABEL_61;
          }
          v34 = DerefVariant(v32);
          VariantCopy((VARIANTARG *)&v55.decVal.8, v34);
          ++v32;
        }
        v35 = DerefVariant(v32);
        VariantCopy(&v57, v35);
        goto LABEL_256;
      }
      if ( (a4 & 1) == 0 )
        goto LABEL_341;
      if ( !a5 )
        goto LABEL_340;
      v36 = a5->cArgs;
      if ( v36 < 2 )
        goto LABEL_340;
      v37 = DerefVariant(&a5->rgvarg[v36 - 2]);
      if ( v8->vt != 3 || v37->vt != 3 )
        goto LABEL_50;
      v40 = v8->lVal;
      v41 = v37->lVal;
      v56 = 0;
      v42 = 0;
      *(_OWORD *)&v55.decVal.Lo32 = 0;
      if ( v38 != 3 )
      {
        if ( v38 != 4 )
        {
LABEL_266:
          v13 = CFrameWebOC::ExecWB(
                  (struct CFrameWebOC *)((char *)a1 + 48),
                  v40,
                  v41,
                  (struct tagVARIANT *)&v55.decVal.8,
                  v42);
          goto LABEL_60;
        }
        v42 = v39;
      }
      v43 = DerefVariant(&v39[v38 - 3]);
      VariantCopy((VARIANTARG *)&v55.decVal.8, v43);
      goto LABEL_266;
    }
    if ( (a4 & 1) == 0 )
      goto LABEL_341;
    if ( !a5 )
      goto LABEL_340;
    v45 = a5->cArgs;
    if ( !v45 || !v8->vt )
      goto LABEL_340;
    v46 = a5->rgvarg;
    v56 = 0;
    memset(&v58, 0, sizeof(v58));
    memset(&v59, 0, sizeof(v59));
    memset(&v57, 0, sizeof(v57));
    *(_OWORD *)&v55.decVal.Lo32 = 0;
    v47 = v45 - 2;
    if ( v47 )
    {
      v48 = v47 - 1;
      if ( v48 )
      {
        v49 = v48 - 1;
        if ( v49 )
        {
          if ( v49 != 1 )
          {
LABEL_285:
            v13 = CFrameWebOC::Navigate2(
                    (struct CFrameWebOC *)((char *)a1 + 48),
                    v8,
                    &v58,
                    &v59,
                    &v57,
                    (struct tagVARIANT *)&v55.decVal.8);
            VariantClear((VARIANTARG *)&v55.decVal.8);
            VariantClear(&v57);
            VariantClear(&v59);
            v23 = &v58;
            goto LABEL_61;
          }
          v50 = DerefVariant(v46);
          VariantCopy((VARIANTARG *)&v55.decVal.8, v50);
          ++v46;
        }
        v51 = DerefVariant(v46);
        VariantCopy(&v57, v51);
        ++v46;
      }
      v52 = DerefVariant(v46);
      VariantCopy(&v59, v52);
      ++v46;
    }
    v53 = DerefVariant(v46);
    VariantCopy(&v58, v53);
    goto LABEL_285;
  }
  switch ( a2 )
  {
    case 552:
      if ( (a4 & 2) != 0 )
      {
        if ( pvarg )
        {
          pvarg->vt = 11;
          Busy = CFrameWebOC::get_RegisterAsBrowser((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->iVal);
          goto LABEL_334;
        }
        goto LABEL_340;
      }
      if ( (a4 & 4) == 0 )
        goto LABEL_341;
      if ( a5 && a5->cArgs )
      {
        if ( v8->vt == 11 )
        {
          Busy = CFrameWebOC::put_RegisterAsBrowser((struct CFrameWebOC *)((char *)a1 + 48), v8->iVal);
          goto LABEL_334;
        }
        goto LABEL_50;
      }
      goto LABEL_340;
    case 553:
      if ( (a4 & 2) != 0 )
      {
        if ( pvarg )
        {
          pvarg->vt = 11;
          Busy = CFrameWebOC::get_RegisterAsDropTarget((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->iVal);
          goto LABEL_334;
        }
        goto LABEL_340;
      }
      if ( (a4 & 4) == 0 )
        goto LABEL_341;
      if ( a5 && a5->cArgs )
      {
        if ( v8->vt == 11 )
        {
          Busy = CFrameWebOC::put_RegisterAsDropTarget((struct CFrameWebOC *)((char *)a1 + 48), v8->iVal);
          goto LABEL_334;
        }
        goto LABEL_50;
      }
      goto LABEL_340;
    case 554:
      if ( (a4 & 2) != 0 )
      {
        if ( pvarg )
        {
          pvarg->vt = 11;
          Busy = CFrameWebOC::get_TheaterMode((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->iVal);
          goto LABEL_334;
        }
        goto LABEL_340;
      }
      if ( (a4 & 4) == 0 )
        goto LABEL_341;
      if ( a5 && a5->cArgs )
      {
        if ( v8->vt == 11 )
        {
          Busy = CFrameWebOC::put_TheaterMode((struct CFrameWebOC *)((char *)a1 + 48), v8->iVal);
          goto LABEL_334;
        }
        goto LABEL_50;
      }
      goto LABEL_340;
    case 555:
      if ( (a4 & 2) != 0 )
      {
        if ( pvarg )
        {
          pvarg->vt = 11;
          Busy = CFrameWebOC::get_AddressBar((struct CFrameWebOC *)((char *)a1 + 48), &pvarg->iVal);
          goto LABEL_334;
        }
        goto LABEL_340;
      }
      if ( (a4 & 4) == 0 )
        goto LABEL_341;
      if ( a5 && a5->cArgs )
      {
        if ( v8->vt == 11 )
        {
          Busy = CFrameWebOC::put_AddressBar((struct CFrameWebOC *)((char *)a1 + 48), v8->iVal);
          goto LABEL_334;
        }
        goto LABEL_50;
      }
      goto LABEL_340;
  }
  if ( a2 != 556 )
    goto LABEL_299;
  if ( (a4 & 2) == 0 )
  {
    if ( (a4 & 4) == 0 )
      goto LABEL_341;
    if ( !a5 || !a5->cArgs )
      goto LABEL_340;
    Busy = -2147467263;
    v29 = 11;
    goto LABEL_168;
  }
  if ( !pvarg )
    goto LABEL_340;
  pvarg->vt = 11;
  v13 = -2147467263;
LABEL_342:
  *((_BYTE *)a1 + 77) &= ~2u;
  return v13;
}

```

## disassembly

```asm
0x180b58bdc  mov     rax, rsp
0x180b58bdf  mov     [rax+20h], r9w
0x180b58be4  mov     [rax+18h], r8d
0x180b58be8  mov     [rax+10h], edx
0x180b58beb  mov     [rax+8], rcx
0x180b58bef  push    rbp
0x180b58bf0  push    rbx
0x180b58bf1  push    rsi
0x180b58bf2  push    rdi
0x180b58bf3  push    r12
0x180b58bf5  push    r13
0x180b58bf7  push    r14
0x180b58bf9  push    r15
0x180b58bfb  lea     rbp, [rax-47h]
0x180b58bff  sub     rsp, 0C8h
0x180b58c06  mov     rdi, [rbp+3Fh+pvarg]
0x180b58c0a  xor     r15d, r15d
0x180b58c0d  xor     eax, eax
0x180b58c0f  xorps   xmm0, xmm0
0x180b58c12  mov     qword ptr [rbp+3Fh+pvargDest+10h], rax
0x180b58c16  mov     r14d, r15d
0x180b58c19  movups  xmmword ptr [rbp+3Fh+pvargDest], xmm0
0x180b58c1d  test    rdi, rdi
0x180b58c20  jz      short loc_180B58C31
0x180b58c22  mov     rcx, rdi; pvarg
0x180b58c25  call    cs:__imp_VariantInit
0x180b58c2c  nop     dword ptr [rax+rax+00h]
0x180b58c31  mov     rsi, [rbp+3Fh+arg_0]
0x180b58c35  mov     r12d, 2
0x180b58c3b  mov     rbx, [rbp+3Fh+arg_20]
0x180b58c3f  or      [rsi+4Dh], r12b
0x180b58c43  lea     r13d, [r12+1]
0x180b58c48  test    rbx, rbx
0x180b58c4b  jz      short loc_180B58CA6
0x180b58c4d  mov     eax, [rbx+10h]
0x180b58c50  test    eax, eax
0x180b58c52  jz      short loc_180B58CA6
0x180b58c54  dec     eax
0x180b58c56  lea     rdx, [rax+rax*2]
0x180b58c5a  mov     rax, [rbx]
0x180b58c5d  lea     rcx, [rax+rdx*8]; struct tagVARIANT *
0x180b58c61  call    ?DerefVariant@@YAPEAUtagVARIANT@@PEAU1@@Z; DerefVariant(tagVARIANT *)
0x180b58c66  mov     r14, rax
0x180b58c69  cmp     r12w, [rax]
0x180b58c6d  jnz     short loc_180B58CA6
0x180b58c6f  lea     rcx, [rbp+3Fh+pvargDest]; pvarg
0x180b58c73  call    cs:__imp_VariantInit
0x180b58c7a  nop     dword ptr [rax+rax+00h]
0x180b58c7f  movzx   r9d, r13w; vt
0x180b58c83  lea     rcx, [rbp+3Fh+pvargDest]; pvargDest
0x180b58c87  xor     r8d, r8d; wFlags
0x180b58c8a  mov     rdx, r14; pvarSrc
0x180b58c8d  call    cs:__imp_VariantChangeType
0x180b58c94  nop     dword ptr [rax+rax+00h]
0x180b58c99  test    eax, eax
0x180b58c9b  lea     rcx, [rbp+3Fh+pvargDest]
0x180b58c9f  cmovnz  rcx, r14
0x180b58ca3  mov     r14, rcx
0x180b58ca6  mov     edx, [rbp+3Fh+arg_8]; int
0x180b58ca9  mov     eax, 0D4h
0x180b58cae  cmp     edx, eax
0x180b58cb0  jg      loc_180B59363
0x180b58cb6  jz      loc_180B59339
0x180b58cbc  mov     eax, 0C8h
0x180b58cc1  cmp     edx, eax
0x180b58cc3  jg      loc_180B58FEB
0x180b58cc9  jz      loc_180B58FB7
0x180b58ccf  cmp     edx, 65h ; 'e'
0x180b58cd2  jg      loc_180B58DC8
0x180b58cd8  jz      loc_180B58DB0
0x180b58cde  cmp     edx, 0FFFFFDDAh
0x180b58ce4  jz      loc_180B58D98
0x180b58cea  cmp     edx, 0FFFFFDF3h
0x180b58cf0  jz      short loc_180B58D6F
0x180b58cf2  cmp     edx, 0FFFFFDFDh
0x180b58cf8  jz      short loc_180B58D49
0x180b58cfa  test    edx, edx
0x180b58cfc  jz      short loc_180B58D1F
0x180b58cfe  cmp     edx, 64h ; 'd'
0x180b58d01  jnz     loc_180B59B82
0x180b58d07  test    byte ptr [rbp+3Fh+arg_18], 1
0x180b58d0b  jz      loc_180B59D7C
0x180b58d11  lea     rcx, [rsi+30h]; this
0x180b58d15  call    ?GoBack@CFrameWebOC@@UEAAJXZ; CFrameWebOC::GoBack(void)
0x180b58d1a  jmp     loc_180B59D41
0x180b58d1f  test    byte ptr [rbp+3Fh+arg_18], r12b
0x180b58d23  jz      loc_180B59D7C
0x180b58d29  test    rdi, rdi
0x180b58d2c  jz      loc_180B59D75
0x180b58d32  lea     rdx, [rdi+8]; unsigned __int16 **
0x180b58d36  mov     word ptr [rdi], 8
0x180b58d3b  lea     rcx, [rsi+30h]; this
0x180b58d3f  call    ?get_Name@CFrameWebOC@@UEAAJPEAPEAG@Z; CFrameWebOC::get_Name(ushort * *)
0x180b58d44  jmp     loc_180B59D41
0x180b58d49  test    byte ptr [rbp+3Fh+arg_18], r12b
0x180b58d4d  jz      loc_180B59D7C
0x180b58d53  test    rdi, rdi
0x180b58d56  jz      loc_180B59D75
0x180b58d5c  mov     word ptr [rdi], 14h
0x180b58d61  mov     [rdi+8], r15
0x180b58d65  mov     ebx, 80004005h
0x180b58d6a  jmp     loc_180B59D81
0x180b58d6f  test    byte ptr [rbp+3Fh+arg_18], r12b
0x180b58d73  jz      loc_180B59D7C
0x180b58d79  test    rdi, rdi
0x180b58d7c  jz      loc_180B59D75
0x180b58d82  lea     rdx, [rdi+8]; enum tagREADYSTATE *
0x180b58d86  mov     [rdi], r13w
0x180b58d8a  lea     rcx, [rsi+30h]; this
0x180b58d8e  call    ?get_ReadyState@CFrameWebOC@@UEAAJPEAW4tagREADYSTATE@@@Z; CFrameWebOC::get_ReadyState(tagREADYSTATE *)
0x180b58d93  jmp     loc_180B59D41
0x180b58d98  test    byte ptr [rbp+3Fh+arg_18], 1
0x180b58d9c  jz      loc_180B59D7C
0x180b58da2  lea     rcx, [rsi+30h]; this
0x180b58da6  call    ?Refresh@CFrameWebOC@@UEAAJXZ; CFrameWebOC::Refresh(void)
0x180b58dab  jmp     loc_180B59D41
0x180b58db0  test    byte ptr [rbp+3Fh+arg_18], 1
0x180b58db4  jz      loc_180B59D7C
0x180b58dba  lea     rcx, [rsi+30h]; this
0x180b58dbe  call    ?GoForward@CFrameWebOC@@UEAAJXZ; CFrameWebOC::GoForward(void)
0x180b58dc3  jmp     loc_180B59D41
0x180b58dc8  mov     ecx, edx
0x180b58dca  sub     ecx, 66h ; 'f'
0x180b58dcd  jz      loc_180B58F9F
0x180b58dd3  sub     ecx, 1
0x180b58dd6  jz      loc_180B58F87
0x180b58ddc  sub     ecx, 1
0x180b58ddf  jz      short loc_180B58E21
0x180b58de1  sub     ecx, 1
0x180b58de4  jz      short loc_180B58E06
0x180b58de6  cmp     ecx, 1
0x180b58de9  jnz     loc_180B59B82
0x180b58def  test    byte ptr [rbp+3Fh+arg_18], cl
0x180b58df2  jz      loc_180B59D7C
0x180b58df8  lea     rcx, [rsi+30h]; this
0x180b58dfc  call    ?Stop@CFrameWebOC@@UEAAJXZ; CFrameWebOC::Stop(void)
0x180b58e01  jmp     loc_180B59D41
0x180b58e06  test    byte ptr [rbp+3Fh+arg_18], 1
0x180b58e0a  jz      loc_180B59D7C
0x180b58e10  lea     rcx, [rsi+30h]; this
0x180b58e14  mov     rdx, r14; struct tagVARIANT *
0x180b58e17  call    ?Refresh2@CFrameWebOC@@UEAAJPEAUtagVARIANT@@@Z; CFrameWebOC::Refresh2(tagVARIANT *)
0x180b58e1c  jmp     loc_180B59D41
0x180b58e21  test    byte ptr [rbp+3Fh+arg_18], 1
0x180b58e25  jz      loc_180B59D7C
0x180b58e2b  test    rbx, rbx
0x180b58e2e  jz      loc_180B59D75
0x180b58e34  mov     edx, [rbx+10h]
0x180b58e37  test    edx, edx
0x180b58e39  jz      loc_180B59D75
0x180b58e3f  cmp     r15w, [r14]
0x180b58e43  jz      loc_180B59D75
0x180b58e49  mov     ecx, 8
0x180b58e4e  cmp     [r14], cx
0x180b58e52  jz      short loc_180B58E5E
0x180b58e54  mov     ebx, 80020008h
0x180b58e59  jmp     loc_180B59D81
0x180b58e5e  mov     rbx, [rbx]
0x180b58e61  xor     eax, eax
0x180b58e63  mov     [rbp+3Fh+var_B0], rax
0x180b58e67  xorps   xmm0, xmm0
0x180b58e6a  mov     qword ptr [rbp+3Fh+var_A8+10h], rax
0x180b58e6e  xorps   xmm1, xmm1
0x180b58e71  mov     qword ptr [rbp+3Fh+var_78+10h], rax
0x180b58e75  mov     qword ptr [rbp+3Fh+var_90+10h], rax
0x180b58e79  movups  xmmword ptr [rsp+100h+var_C8+8], xmm0
0x180b58e7e  movups  xmmword ptr [rbp+3Fh+var_A8], xmm1
0x180b58e82  movups  xmmword ptr [rbp+3Fh+var_78], xmm0
0x180b58e86  movups  xmmword ptr [rbp+3Fh+var_90], xmm1
0x180b58e8a  sub     edx, r12d
0x180b58e8d  jz      short loc_180B58EFB
0x180b58e8f  sub     edx, 1
0x180b58e92  jz      short loc_180B58EDC
0x180b58e94  sub     edx, 1
0x180b58e97  jz      short loc_180B58EBD
0x180b58e99  cmp     edx, 1
0x180b58e9c  jnz     short loc_180B58F17
0x180b58e9e  mov     rcx, rbx; struct tagVARIANT *
0x180b58ea1  call    ?DerefVariant@@YAPEAUtagVARIANT@@PEAU1@@Z; DerefVariant(tagVARIANT *)
0x180b58ea6  mov     rdx, rax; pvargSrc
0x180b58ea9  lea     rcx, [rbp+3Fh+var_90]; pvargDest
0x180b58ead  call    cs:__imp_VariantCopy
0x180b58eb4  nop     dword ptr [rax+rax+00h]
0x180b58eb9  add     rbx, 18h
0x180b58ebd  mov     rcx, rbx; struct tagVARIANT *
0x180b58ec0  call    ?DerefVariant@@YAPEAUtagVARIANT@@PEAU1@@Z; DerefVariant(tagVARIANT *)
0x180b58ec5  mov     rdx, rax; pvargSrc
0x180b58ec8  lea     rcx, [rbp+3Fh+var_78]; pvargDest
0x180b58ecc  call    cs:__imp_VariantCopy
0x180b58ed3  nop     dword ptr [rax+rax+00h]
0x180b58ed8  add     rbx, 18h
0x180b58edc  mov     rcx, rbx; struct tagVARIANT *
0x180b58edf  call    ?DerefVariant@@YAPEAUtagVARIANT@@PEAU1@@Z; DerefVariant(tagVARIANT *)
0x180b58ee4  mov     rdx, rax; pvargSrc
0x180b58ee7  lea     rcx, [rbp+3Fh+var_A8]; pvargDest
0x180b58eeb  call    cs:__imp_VariantCopy
0x180b58ef2  nop     dword ptr [rax+rax+00h]
0x180b58ef7  add     rbx, 18h
0x180b58efb  mov     rcx, rbx; struct tagVARIANT *
0x180b58efe  call    ?DerefVariant@@YAPEAUtagVARIANT@@PEAU1@@Z; DerefVariant(tagVARIANT *)
0x180b58f03  mov     rdx, rax; pvargSrc
0x180b58f06  lea     rcx, [rsp+100h+var_C8+8]; pvargDest
0x180b58f0b  call    cs:__imp_VariantCopy
0x180b58f12  nop     dword ptr [rax+rax+00h]
0x180b58f17  mov     rdx, [r14+8]; unsigned __int16 *
0x180b58f1b  lea     rax, [rbp+3Fh+var_90]
0x180b58f1f  mov     [rsp+100h+var_D8], rax; struct tagVARIANT *
0x180b58f24  lea     rcx, [rsi+30h]; this
0x180b58f28  lea     rax, [rbp+3Fh+var_78]
0x180b58f2c  lea     r9, [rbp+3Fh+var_A8]; struct tagVARIANT *
0x180b58f30  mov     [rsp+100h+var_E0], rax; struct tagVARIANT *
0x180b58f35  lea     r8, [rsp+100h+var_C8+8]; struct tagVARIANT *
0x180b58f3a  call    ?Navigate@CFrameWebOC@@UEAAJPEAGPEAUtagVARIANT@@111@Z; CFrameWebOC::Navigate(ushort *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *)
0x180b58f3f  lea     rcx, [rbp+3Fh+var_90]; pvarg
0x180b58f43  mov     ebx, eax
0x180b58f45  call    cs:__imp_VariantClear
0x180b58f4c  nop     dword ptr [rax+rax+00h]
0x180b58f51  lea     rcx, [rbp+3Fh+var_78]; pvarg
0x180b58f55  call    cs:__imp_VariantClear
0x180b58f5c  nop     dword ptr [rax+rax+00h]
0x180b58f61  lea     rcx, [rbp+3Fh+var_A8]; pvarg
0x180b58f65  call    cs:__imp_VariantClear
0x180b58f6c  nop     dword ptr [rax+rax+00h]
0x180b58f71  lea     rcx, [rsp+100h+var_C8+8]; pvarg
0x180b58f76  call    cs:__imp_VariantClear
0x180b58f7d  nop     dword ptr [rax+rax+00h]
0x180b58f82  jmp     loc_180B59D81
0x180b58f87  test    byte ptr [rbp+3Fh+arg_18], 1
0x180b58f8b  jz      loc_180B59D7C
0x180b58f91  lea     rcx, [rsi+30h]; this
0x180b58f95  call    ?GoSearch@CFrameWebOC@@UEAAJXZ; CFrameWebOC::GoSearch(void)
0x180b58f9a  jmp     loc_180B59D41
0x180b58f9f  test    byte ptr [rbp+3Fh+arg_18], 1
0x180b58fa3  jz      loc_180B59D7C
0x180b58fa9  lea     rcx, [rsi+30h]; this
0x180b58fad  call    ?GoHome@CFrameWebOC@@UEAAJXZ; CFrameWebOC::GoHome(void)
0x180b58fb2  jmp     loc_180B59D41
0x180b58fb7  test    byte ptr [rbp+3Fh+arg_18], r12b
0x180b58fbb  jz      loc_180B59D7C
0x180b58fc1  test    rdi, rdi
0x180b58fc4  jz      loc_180B59D75
0x180b58fca  lea     rdx, [rdi+8]; struct IDispatch **
0x180b58fce  lea     rcx, [rsi+30h]; this
0x180b58fd2  call    ?get_Application@CFrameWebOC@@UEAAJPEAPEAUIDispatch@@@Z; CFrameWebOC::get_Application(IDispatch * *)
0x180b58fd7  mov     ebx, eax
0x180b58fd9  test    eax, eax
0x180b58fdb  jnz     loc_180B59D81
0x180b58fe1  mov     word ptr [rdi], 9
0x180b58fe6  jmp     loc_180B59D81
0x180b58feb  mov     eax, 0CEh
0x180b58ff0  cmp     edx, eax
0x180b58ff2  jg      loc_180B5919F
0x180b58ff8  jz      loc_180B59141
0x180b58ffe  mov     ecx, edx
0x180b59000  sub     ecx, 0C9h
0x180b59006  jz      loc_180B5911C
0x180b5900c  sub     ecx, 1
0x180b5900f  jz      loc_180B590F7
0x180b59015  sub     ecx, 1
0x180b59018  jz      short loc_180B5907C
0x180b5901a  sub     ecx, 1
0x180b5901d  jz      short loc_180B59052
0x180b5901f  cmp     ecx, 1
0x180b59022  jnz     loc_180B59B82
0x180b59028  test    byte ptr [rbp+3Fh+arg_18], r12b
0x180b5902c  jz      loc_180B59D7C
0x180b59032  test    rdi, rdi
0x180b59035  jz      loc_180B59D75
0x180b5903b  lea     rdx, [rdi+8]; unsigned __int16 **
0x180b5903f  mov     word ptr [rdi], 8
0x180b59044  lea     rcx, [rsi+30h]; this
0x180b59048  call    ?get_Type@CFrameWebOC@@UEAAJPEAPEAG@Z; CFrameWebOC::get_Type(ushort * *)
0x180b5904d  jmp     loc_180B59D41
0x180b59052  test    byte ptr [rbp+3Fh+arg_18], r12b
0x180b59056  jz      loc_180B59D7C
0x180b5905c  test    rdi, rdi
0x180b5905f  jz      loc_180B59D75
0x180b59065  lea     rdx, [rdi+8]; __int16 *
0x180b59069  mov     word ptr [rdi], 0Bh
0x180b5906e  lea     rcx, [rsi+30h]; this
0x180b59072  call    ?get_TopLevelContainer@CFrameWebOC@@UEAAJPEAF@Z; CFrameWebOC::get_TopLevelContainer(short *)
0x180b59077  jmp     loc_180B59D41
0x180b5907c  test    byte ptr [rbp+3Fh+arg_18], r12b
0x180b59080  jz      loc_180B59D7C
0x180b59086  test    rdi, rdi
0x180b59089  jz      loc_180B59D75
0x180b5908f  mov     [rdi+8], r15
0x180b59093  test    byte ptr [rsi+10h], 1
0x180b59097  jnz     loc_180B58D65
0x180b5909d  test    [rsi+10h], r12b
0x180b590a1  jnz     loc_180B58D65
0x180b590a7  mov     rcx, [rsi+38h]; this
0x180b590ab  test    rcx, rcx
0x180b590ae  jz      loc_180B58D65
0x180b590b4  mov     ebx, r15d
0x180b590b7  call    ?GetFrameSite@CWindow@@QEAAPEAVCFrameSite@@XZ; CWindow::GetFrameSite(void)
0x180b590bc  test    rax, rax
0x180b590bf  jz      short loc_180B590E9
0x180b590c1  lea     rcx, [rax+58h]
0x180b590c5  mov     rax, [rcx]
  ... truncated ...
```
