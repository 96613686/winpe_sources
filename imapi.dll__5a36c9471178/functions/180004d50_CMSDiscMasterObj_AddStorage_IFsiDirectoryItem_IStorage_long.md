# CMSDiscMasterObj::AddStorage(IFsiDirectoryItem *,IStorage *,long)

- ea: `0x180004d50`
- end: `0x1800056e0`
- name: `?AddStorage@CMSDiscMasterObj@@AEAAJPEAUIFsiDirectoryItem@@PEAUIStorage@@J@Z`
- size: `2448`
- prototype: `__int64 __fastcall(CMSDiscMasterObj *__hidden this, struct IFsiDirectoryItem *, struct IStorage *, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180004a40`
- `0x180004d50`

## callees

- `0x180002ac4`
- `0x180004848`
- `0x180004d50`
- `0x180007bac`
- `0x180007bd4`
- `0x180010aac`
- `0x1800127ec`
- `0x180017178`
- `0x1800184ce`
- `0x180018500`
- `0x180019010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005603`
- `ole32!CoTaskMemFree` at `0x180005603`
- `OLEAUT32!__imp_SysAllocString` at `0x18000510d`
- `OLEAUT32!__imp_SysAllocString` at `0x180005361`
- `OLEAUT32!__imp_SysAllocString` at `0x18000510d`
- `OLEAUT32!__imp_SysAllocString` at `0x180005361`
- `OLEAUT32!__imp_SysFreeString` at `0x180004fde`
- `OLEAUT32!__imp_SysFreeString` at `0x1800050fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000527a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005351`
- `OLEAUT32!__imp_SysFreeString` at `0x180005694`
- `OLEAUT32!__imp_SysFreeString` at `0x18000569f`
- `OLEAUT32!__imp_SysFreeString` at `0x180004fde`
- `OLEAUT32!__imp_SysFreeString` at `0x1800050fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000527a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005351`
- `OLEAUT32!__imp_SysFreeString` at `0x180005694`
- `OLEAUT32!__imp_SysFreeString` at `0x18000569f`
- `KERNEL32!WaitForSingleObject` at `0x180004e20`
- `KERNEL32!WaitForSingleObject` at `0x180004e20`

## pseudocode

```c
__int64 __fastcall CMSDiscMasterObj::AddStorage(
        CMSDiscMasterObj *this,
        struct IFsiDirectoryItem *a2,
        struct IStorage *a3,
        int a4)
{
  struct IStorage *v4; // rdi
  OLECHAR *v6; // rbx
  int v7; // esi
  void *v8; // rcx
  struct IFsiDirectoryItem *v9; // rsi
  int v10; // eax
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  const struct _FILETIME *v15; // rdx
  void (__fastcall *v16)(__int64); // rdi
  void (__fastcall *v17)(__int64); // rdi
  const struct _FILETIME *v18; // rdx
  void (__fastcall *v19)(__int64); // rdi
  const struct _FILETIME *v20; // rdx
  struct IFsiDirectoryItem *v21; // rsi
  int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  int v26; // esi
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  int v29; // eax
  const struct _FILETIME *v30; // rdx
  void (__fastcall *v31)(__int64); // rdi
  void (__fastcall *v32)(__int64); // rdi
  const struct _FILETIME *v33; // rdx
  void (__fastcall *v34)(__int64); // rdi
  const struct _FILETIME *v35; // rdx
  int v36; // edx
  int v37; // eax
  __int64 v39; // [rsp+28h] [rbp-D8h]
  __int64 v40; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR *psz; // [rsp+58h] [rbp-A8h]
  int v44; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+68h] [rbp-98h] BYREF
  int v46; // [rsp+70h] [rbp-90h] BYREF
  int v47; // [rsp+74h] [rbp-8Ch]
  struct IStorage *v48; // [rsp+78h] [rbp-88h] BYREF
  struct IFsiDirectoryItem *v49; // [rsp+80h] [rbp-80h] BYREF
  __int64 v50; // [rsp+88h] [rbp-78h] BYREF
  struct IFsiDirectoryItem *v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h] BYREF
  struct IStorage *v53; // [rsp+A0h] [rbp-60h]
  LPVOID pv; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v55; // [rsp+B8h] [rbp-48h]
  _BYTE v56[24]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v57[8]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v58[8]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v59[40]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v60[24]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v61[8]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v62[8]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v63[40]; // [rsp+178h] [rbp+78h] BYREF

  v53 = a3;
  v4 = a3;
  v51 = a2;
  v47 = a4;
  v49 = 0;
  v40 = 0;
  v50 = 0;
  v52 = 0;
  memset_0(&pv, 0, 0x50u);
  v42 = 0;
  v6 = 0;
  v48 = 0;
  v46 = 0;
  bstrString = 0;
  v44 = 0;
  if ( !v4 )
  {
    v7 = -2147467261;
    goto LABEL_113;
  }
  v7 = ((__int64 (__fastcall *)(struct IStorage *, GUID *, __int64 *))v4->lpVtbl->QueryInterface)(
         v4,
         &IID_IStorage,
         &v52);
  if ( v7 >= 0 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    v8 = (void *)*((_QWORD *)this + 53);
    if ( v8 && !WaitForSingleObject(v8, 0) )
    {
      v7 = -2147220979;
      goto LABEL_107;
    }
    v7 = ((__int64 (__fastcall *)(struct IStorage *, _QWORD, _QWORD, _QWORD, __int64 *))v4->lpVtbl->EnumElements)(
           v4,
           0,
           0,
           0,
           &v50);
    if ( v7 < 0 )
      goto LABEL_107;
    if ( !v50 )
    {
      v7 = -2147220978;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 32, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
      goto LABEL_107;
    }
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 40LL))(v50);
    if ( v7 < 0 )
    {
LABEL_104:
      if ( *((_DWORD *)this + 51) )
      {
        v36 = ++*((_DWORD *)this + 67);
        v37 = *((_DWORD *)this + 66);
        *((_DWORD *)this + 73) |= 2u;
        *((_DWORD *)this + 78) = v36;
        *((_DWORD *)this + 79) = v37;
      }
      CMyUpdateList::UpdateAll((CMSDiscMasterObj *)((char *)this + 192));
      goto LABEL_107;
    }
    while ( 1 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, int *))(*(_QWORD *)v50 + 24LL))(v50, 1, &pv, &v46);
      if ( v7 < 0 )
        goto LABEL_104;
      v7 = 0;
      if ( !v46 )
        goto LABEL_104;
      if ( v55 == 1 )
        break;
      if ( v55 == 2 )
      {
        if ( ((int (__fastcall *)(struct IStorage *, LPVOID, _QWORD, _QWORD, _DWORD, __int64 *))v4->lpVtbl->OpenStream)(
               v4,
               pv,
               0,
               0,
               0,
               &v42) >= 0
          || (v7 = ((__int64 (__fastcall *)(struct IStorage *, LPVOID, _QWORD, __int64, _DWORD, __int64 *))v4->lpVtbl->OpenStream)(
                     v4,
                     pv,
                     0,
                     16,
                     0,
                     &v42),
              v7 >= 0) )
        {
          SysFreeString(bstrString);
          bstrString = 0;
          v9 = v51;
          v10 = ((__int64 (__fastcall *)(struct IFsiDirectoryItem *, BSTR *))v51->lpVtbl->get_FullPath)(
                  v51,
                  &bstrString);
          LODWORD(psz) = v10;
          if ( v10 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                40,
                &WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
                (unsigned int)v10);
              v10 = (int)psz;
            }
            v11 = (unsigned int)v10;
LABEL_32:
            v7 = TranslateIMAPI2Error(v11);
LABEL_33:
            if ( v42 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
              v42 = 0;
            }
            goto LABEL_101;
          }
          ATL::CComBSTR::operator+=(&bstrString, L"\\");
          ATL::CComBSTR::operator+=(&bstrString, pv);
          if ( !v47 )
          {
            v7 = (*(__int64 (__fastcall **)(_QWORD, BSTR, int *))(**((_QWORD **)this + 61) + 320LL))(
                   *((_QWORD *)this + 61),
                   bstrString,
                   &v44);
            if ( v7 < 0 )
            {
              v12 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              {
                v13 = 41;
                goto LABEL_40;
              }
              goto LABEL_41;
            }
            if ( v44 )
              goto LABEL_33;
            v9 = v51;
          }
          psz = (OLECHAR *)pv;
          if ( pv != v6 )
          {
            SysFreeString(v6);
            if ( psz )
            {
              v6 = SysAllocString(psz);
              if ( !v6 )
                ATL::AtlThrowImpl(-2147024882);
            }
            else
            {
              v6 = 0;
            }
          }
          v7 = ((__int64 (__fastcall *)(struct IFsiDirectoryItem *, OLECHAR *, __int64))v9->lpVtbl->AddFile)(
                 v9,
                 v6,
                 v42);
          if ( v7 >= 0 )
          {
            memset_0(v56, 0, 0x50u);
            v45 = 0;
            v14 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)v42 + 96LL))(v42, v56, 1);
            if ( v14 >= 0 )
            {
              if ( ((int (__fastcall *)(struct IFsiDirectoryItem *, OLECHAR *, __int64 *))v51->lpVtbl->get_Item)(
                     v51,
                     v6,
                     &v45) >= 0 )
              {
                v16 = *(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 80LL);
                Imapi2Utility::ConvertFileTimeToVariantTime((Imapi2Utility *)v58, v15);
                v16(v45);
                v17 = *(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 112LL);
                Imapi2Utility::ConvertFileTimeToVariantTime((Imapi2Utility *)v57, v18);
                v17(v45);
                v19 = *(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 96LL);
                Imapi2Utility::ConvertFileTimeToVariantTime((Imapi2Utility *)v59, v20);
                v19(v45);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
                v4 = v53;
              }
            }
            else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                43,
                &WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
                (unsigned int)v14);
            }
            goto LABEL_33;
          }
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            v13 = 42;
LABEL_40:
            WPP_SF_d(v12[7], v13, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids, (unsigned int)v7);
          }
LABEL_41:
          v11 = (unsigned int)v7;
          goto LABEL_32;
        }
      }
      else
      {
        if ( v55 - 3 < 2 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 33, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids);
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 44, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids, v55);
        }
        v7 = -2147024809;
      }
LABEL_101:
      if ( pv )
        CoTaskMemFree(pv);
      if ( v7 < 0 )
        goto LABEL_104;
    }
    SysFreeString(bstrString);
    bstrString = 0;
    v21 = v51;
    v22 = ((__int64 (__fastcall *)(struct IFsiDirectoryItem *, BSTR *))v51->lpVtbl->get_FullPath)(v51, &bstrString);
    LODWORD(psz) = v22;
    if ( v22 < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_64;
      v24 = 34;
LABEL_63:
      WPP_SF_d(v23[7], v24, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids, (unsigned int)v22);
      v22 = (int)psz;
LABEL_64:
      v25 = (unsigned int)v22;
LABEL_65:
      v7 = TranslateIMAPI2Error(v25);
      goto LABEL_101;
    }
    ATL::CComBSTR::operator+=(&bstrString, L"\\");
    ATL::CComBSTR::operator+=(&bstrString, pv);
    v22 = (*(__int64 (__fastcall **)(_QWORD, BSTR, int *))(**((_QWORD **)this + 61) + 320LL))(
            *((_QWORD *)this + 61),
            bstrString,
            &v44);
    LODWORD(psz) = v22;
    if ( v22 < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_64;
      v24 = 35;
      goto LABEL_63;
    }
    psz = (OLECHAR *)pv;
    if ( pv != v6 )
    {
      SysFreeString(v6);
      if ( psz )
      {
        v6 = SysAllocString(psz);
        if ( !v6 )
          ATL::AtlThrowImpl(-2147024882);
      }
      else
      {
        v6 = 0;
      }
    }
    if ( !v44 )
    {
      v22 = ((__int64 (__fastcall *)(struct IFsiDirectoryItem *, OLECHAR *))v21->lpVtbl->AddDirectory)(v21, v6);
      LODWORD(psz) = v22;
      if ( v22 < 0 )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          goto LABEL_64;
        v24 = 36;
        goto LABEL_63;
      }
    }
    v26 = ((__int64 (__fastcall *)(struct IFsiDirectoryItem *, OLECHAR *, __int64 *))v21->lpVtbl->get_Item)(
            v21,
            v6,
            &v40);
    if ( v26 >= 0 )
    {
      v26 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IFsiDirectoryItem **))v40)(
              v40,
              &GUID_2c941fdc_975b_59be_a960_9a2a262853a5,
              &v49);
      if ( v26 >= 0 )
      {
        LODWORD(v39) = 0;
        if ( ((int (__fastcall *)(struct IStorage *, LPVOID, _QWORD, _QWORD, _QWORD, __int64, struct IStorage **))v4->lpVtbl->OpenStorage)(
               v4,
               pv,
               0,
               0,
               0,
               v39,
               &v48) >= 0
          || (v7 = ((__int64 (__fastcall *)(struct IStorage *, LPVOID, _QWORD, __int64, _QWORD, _DWORD, struct IStorage **))v4->lpVtbl->OpenStorage)(
                     v4,
                     pv,
                     0,
                     16,
                     0,
                     0,
                     &v48),
              v7 >= 0) )
        {
          memset_0(v60, 0, 0x50u);
          v29 = ((__int64 (__fastcall *)(struct IStorage *, _BYTE *, __int64))v48->lpVtbl->Stat)(v48, v60, 1);
          if ( v29 >= 0 )
          {
            v31 = *(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 80LL);
            Imapi2Utility::ConvertFileTimeToVariantTime((Imapi2Utility *)v62, v30);
            v31(v40);
            v32 = *(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 112LL);
            Imapi2Utility::ConvertFileTimeToVariantTime((Imapi2Utility *)v61, v33);
            v32(v40);
            v34 = *(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 96LL);
            Imapi2Utility::ConvertFileTimeToVariantTime((Imapi2Utility *)v63, v35);
            v34(v40);
            v4 = v53;
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              39,
              &WPP_91009cdf2d793e26fab877c81345f591_Traceguids,
              (unsigned int)v29);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
          v40 = 0;
          v7 = CMSDiscMasterObj::AddStorage(this, v49, v48, v47);
          if ( v7 >= 0 )
          {
            ((void (__fastcall *)(struct IFsiDirectoryItem *))v49->lpVtbl->Release)(v49);
            v49 = 0;
          }
          else
          {
            ((void (__fastcall *)(struct IStorage *))v48->lpVtbl->Release)(v48);
          }
        }
        else
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
          v40 = 0;
        }
        goto LABEL_101;
      }
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_85;
      v28 = 38;
    }
    else
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
        goto LABEL_85;
      v28 = 37;
    }
    WPP_SF_d(v27[7], v28, &WPP_91009cdf2d793e26fab877c81345f591_Traceguids, (unsigned int)v26);
LABEL_85:
    v25 = (unsigned int)v26;
    goto LABEL_65;
  }
LABEL_107:
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v49 )
    ((void (__fastcall *)(struct IFsiDirectoryItem *))v49->lpVtbl->Release)(v49);
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
LABEL_113:
  SysFreeString(v6);
  SysFreeString(bstrString);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004d50  push    rbp
0x180004d52  push    rbx
0x180004d53  push    rsi
0x180004d54  push    rdi
0x180004d55  push    r12
0x180004d57  push    r13
0x180004d59  push    r14
0x180004d5b  push    r15
0x180004d5d  lea     rbp, [rsp-0B8h]
0x180004d65  sub     rsp, 1B8h
0x180004d6c  mov     rax, cs:__security_cookie
0x180004d73  xor     rax, rsp
0x180004d76  mov     [rbp+0F0h+var_50], rax
0x180004d7d  xor     r12d, r12d
0x180004d80  mov     [rbp+0F0h+var_150], r8
0x180004d84  mov     rdi, r8
0x180004d87  mov     [rbp+0F0h+var_160], rdx
0x180004d8b  mov     r13, rcx
0x180004d8e  mov     [rsp+1F0h+var_17C], r9d
0x180004d93  xor     edx, edx; Val
0x180004d95  mov     [rbp+0F0h+var_170], r12
0x180004d99  lea     r8d, [r12+50h]; Size
0x180004d9e  mov     [rsp+1F0h+var_1B0], r12
0x180004da3  lea     rcx, [rbp+0F0h+pv]; void *
0x180004da7  mov     [rbp+0F0h+var_168], r12
0x180004dab  mov     [rbp+0F0h+var_158], r12
0x180004daf  call    memset_0
0x180004db4  mov     [rsp+1F0h+var_1A0], r12
0x180004db9  mov     ebx, r12d
0x180004dbc  mov     [rsp+1F0h+var_178], r12
0x180004dc1  mov     [rsp+1F0h+var_180], r12d
0x180004dc6  mov     [rsp+1F0h+bstrString], r12
0x180004dcb  mov     [rsp+1F0h+var_190], r12d
0x180004dd0  test    rdi, rdi
0x180004dd3  jnz     short loc_180004DDF
0x180004dd5  mov     esi, 80004003h
0x180004dda  jmp     loc_180005691
0x180004ddf  mov     rax, [rdi]
0x180004de2  lea     r8, [rbp+0F0h+var_158]
0x180004de6  lea     rdx, IID_IStorage
0x180004ded  mov     rcx, rdi
0x180004df0  mov     rax, [rax]
0x180004df3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004df8  mov     esi, eax
0x180004dfa  test    eax, eax
0x180004dfc  js      loc_180005651
0x180004e02  mov     rcx, [rbp+0F0h+var_158]
0x180004e06  mov     rax, [rcx]
0x180004e09  mov     rax, [rax+10h]
0x180004e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e12  mov     rcx, [r13+1A8h]; hHandle
0x180004e19  test    rcx, rcx
0x180004e1c  jz      short loc_180004E34
0x180004e1e  xor     edx, edx; dwMilliseconds
0x180004e20  call    cs:__imp_WaitForSingleObject
0x180004e26  test    eax, eax
0x180004e28  jnz     short loc_180004E34
0x180004e2a  mov     esi, 8004020Dh
0x180004e2f  jmp     loc_180005651
0x180004e34  mov     rax, [rdi]
0x180004e37  lea     rcx, [rbp+0F0h+var_168]
0x180004e3b  mov     [rsp+1F0h+var_1D0], rcx
0x180004e40  xor     r9d, r9d
0x180004e43  xor     r8d, r8d
0x180004e46  xor     edx, edx
0x180004e48  mov     rcx, rdi
0x180004e4b  mov     rax, [rax+58h]
0x180004e4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e54  mov     esi, eax
0x180004e56  test    eax, eax
0x180004e58  js      loc_180005651
0x180004e5e  cmp     [rbp+0F0h+var_168], r12
0x180004e62  jnz     short loc_180004EA9
0x180004e64  mov     esi, 8004020Eh
0x180004e69  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e70  lea     r15, WPP_GLOBAL_Control
0x180004e77  cmp     rcx, r15
0x180004e7a  jz      loc_180005651
0x180004e80  mov     r14d, 1
0x180004e86  test    [rcx+44h], r14b
0x180004e8a  jz      loc_180005651
0x180004e90  mov     rcx, [rcx+38h]
0x180004e94  lea     edx, [r14+1Fh]
0x180004e98  lea     r8, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180004e9f  call    WPP_SF_
0x180004ea4  jmp     loc_180005651
0x180004ea9  mov     rcx, [rbp+0F0h+var_168]
0x180004ead  mov     rax, [rcx]
0x180004eb0  mov     rax, [rax+28h]
0x180004eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eb9  mov     esi, eax
0x180004ebb  mov     r14d, 1
0x180004ec1  test    eax, eax
0x180004ec3  js      loc_180005614
0x180004ec9  lea     r15, WPP_GLOBAL_Control
0x180004ed0  lea     r12, WPP_91009cdf2d793e26fab877c81345f591_Traceguids
0x180004ed7  mov     rcx, [rbp+0F0h+var_168]
0x180004edb  lea     r9, [rsp+1F0h+var_180]
0x180004ee0  lea     r8, [rbp+0F0h+pv]
0x180004ee4  mov     edx, r14d
0x180004ee7  mov     rax, [rcx]
0x180004eea  mov     rax, [rax+18h]
0x180004eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ef3  mov     esi, eax
0x180004ef5  test    eax, eax
0x180004ef7  js      loc_180005611
0x180004efd  xor     esi, esi
0x180004eff  cmp     [rsp+1F0h+var_180], esi
0x180004f03  jz      loc_180005611
0x180004f09  mov     r9d, [rbp+0F0h+var_138]
0x180004f0d  mov     eax, r9d
0x180004f10  sub     eax, r14d
0x180004f13  jz      loc_180005275
0x180004f19  sub     eax, r14d
0x180004f1c  jz      short loc_180004F78
0x180004f1e  sub     eax, r14d
0x180004f21  jz      short loc_180004F4B
0x180004f23  cmp     eax, r14d
0x180004f26  jz      short loc_180004F4B
0x180004f28  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f2f  cmp     rcx, r15
0x180004f32  jz      short loc_180004F6E
0x180004f34  test    [rcx+44h], r14b
0x180004f38  jz      short loc_180004F6E
0x180004f3a  mov     rcx, [rcx+38h]
0x180004f3e  lea     edx, [rsi+2Ch]
0x180004f41  mov     r8, r12
0x180004f44  call    WPP_SF_d
0x180004f49  jmp     short loc_180004F6E
0x180004f4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f52  cmp     rcx, r15
0x180004f55  jz      short loc_180004F6E
0x180004f57  test    [rcx+44h], r14b
0x180004f5b  jz      short loc_180004F6E
0x180004f5d  mov     rcx, [rcx+38h]
0x180004f61  mov     edx, 21h ; '!'
0x180004f66  mov     r8, r12
0x180004f69  call    WPP_SF_
0x180004f6e  mov     esi, 80070057h
0x180004f73  jmp     loc_1800055FA
0x180004f78  mov     rax, [rdi]
0x180004f7b  lea     rcx, [rsp+1F0h+var_1A0]
0x180004f80  mov     rdx, [rbp+0F0h+pv]
0x180004f84  xor     r9d, r9d
0x180004f87  mov     [rsp+1F0h+var_1C8], rcx
0x180004f8c  xor     r8d, r8d
0x180004f8f  mov     rcx, rdi
0x180004f92  mov     dword ptr [rsp+1F0h+var_1D0], esi
0x180004f96  mov     rax, [rax+20h]
0x180004f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f9f  test    eax, eax
0x180004fa1  jns     short loc_180004FD9
0x180004fa3  mov     rax, [rdi]
0x180004fa6  lea     rcx, [rsp+1F0h+var_1A0]
0x180004fab  mov     rdx, [rbp+0F0h+pv]
0x180004faf  mov     r9d, 10h
0x180004fb5  mov     [rsp+1F0h+var_1C8], rcx
0x180004fba  xor     r8d, r8d
0x180004fbd  mov     rcx, rdi
0x180004fc0  mov     dword ptr [rsp+1F0h+var_1D0], esi
0x180004fc4  mov     rax, [rax+20h]
0x180004fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fcd  mov     esi, eax
0x180004fcf  test    eax, eax
0x180004fd1  js      loc_1800055FA
0x180004fd7  xor     esi, esi
0x180004fd9  mov     rcx, [rsp+1F0h+bstrString]; bstrString
0x180004fde  call    cs:__imp_SysFreeString
0x180004fe4  mov     [rsp+1F0h+bstrString], rsi
0x180004fe9  lea     rdx, [rsp+1F0h+bstrString]
0x180004fee  mov     rsi, [rbp+0F0h+var_160]
0x180004ff2  mov     rcx, rsi
0x180004ff5  mov     rax, [rsi]
0x180004ff8  mov     rax, [rax+40h]
0x180004ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005001  mov     dword ptr [rsp+1F0h+psz], eax
0x180005005  test    eax, eax
0x180005007  jns     short loc_180005064
0x180005009  mov     rcx, cs:WPP_GLOBAL_Control
0x180005010  cmp     rcx, r15
0x180005013  jz      short loc_180005033
0x180005015  test    [rcx+44h], r14b
0x180005019  jz      short loc_180005033
0x18000501b  mov     rcx, [rcx+38h]
0x18000501f  mov     edx, 28h ; '('
0x180005024  mov     r9d, eax
0x180005027  mov     r8, r12
0x18000502a  call    WPP_SF_d
0x18000502f  mov     eax, dword ptr [rsp+1F0h+psz]
0x180005033  mov     ecx, eax
0x180005035  call    TranslateIMAPI2Error
0x18000503a  mov     esi, eax
0x18000503c  mov     rcx, [rsp+1F0h+var_1A0]
0x180005041  test    rcx, rcx
0x180005044  jz      loc_1800055FA
0x18000504a  mov     rax, [rcx]
0x18000504d  mov     rax, [rax+10h]
0x180005051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005056  mov     [rsp+1F0h+var_1A0], 0
0x18000505f  jmp     loc_1800055FA
0x180005064  lea     rdx, asc_18001BC84; "\\"
0x18000506b  lea     rcx, [rsp+1F0h+bstrString]
0x180005070  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x180005075  mov     rdx, [rbp+0F0h+pv]
0x180005079  lea     rcx, [rsp+1F0h+bstrString]
0x18000507e  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x180005083  cmp     [rsp+1F0h+var_17C], 0
0x180005088  jnz     short loc_1800050EC
0x18000508a  mov     rcx, [r13+1E8h]
0x180005091  lea     r8, [rsp+1F0h+var_190]
0x180005096  mov     rdx, [rsp+1F0h+bstrString]
0x18000509b  mov     rax, [rcx]
0x18000509e  mov     rax, [rax+140h]
0x1800050a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050aa  mov     esi, eax
0x1800050ac  test    eax, eax
0x1800050ae  jns     short loc_1800050DD
0x1800050b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050b7  cmp     rcx, r15
0x1800050ba  jz      short loc_1800050D6
0x1800050bc  test    [rcx+44h], r14b
0x1800050c0  jz      short loc_1800050D6
0x1800050c2  mov     edx, 29h ; ')'
0x1800050c7  mov     rcx, [rcx+38h]
0x1800050cb  mov     r9d, esi
0x1800050ce  mov     r8, r12
0x1800050d1  call    WPP_SF_d
0x1800050d6  mov     ecx, esi
0x1800050d8  jmp     loc_180005035
0x1800050dd  cmp     [rsp+1F0h+var_190], 0
0x1800050e2  jnz     loc_18000503C
0x1800050e8  mov     rsi, [rbp+0F0h+var_160]
0x1800050ec  mov     rax, [rbp+0F0h+pv]
0x1800050f0  mov     [rsp+1F0h+psz], rax
0x1800050f5  cmp     rax, rbx
0x1800050f8  jz      short loc_180005123
0x1800050fa  mov     rcx, rbx; bstrString
0x1800050fd  call    cs:__imp_SysFreeString
0x180005103  mov     rcx, [rsp+1F0h+psz]; psz
0x180005108  test    rcx, rcx
0x18000510b  jz      short loc_180005121
0x18000510d  call    cs:__imp_SysAllocString
0x180005113  mov     rbx, rax
0x180005116  test    rax, rax
0x180005119  jz      loc_1800056CA
0x18000511f  jmp     short loc_180005123
0x180005121  xor     ebx, ebx
0x180005123  mov     rax, [rsi]
0x180005126  mov     rdx, rbx
0x180005129  mov     r8, [rsp+1F0h+var_1A0]
0x18000512e  mov     rcx, rsi
0x180005131  mov     rax, [rax+0C0h]
0x180005138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000513d  mov     esi, eax
0x18000513f  test    eax, eax
0x180005141  jns     short loc_18000515F
0x180005143  mov     rcx, cs:WPP_GLOBAL_Control
0x18000514a  cmp     rcx, r15
0x18000514d  jz      short loc_1800050D6
0x18000514f  test    [rcx+44h], r14b
0x180005153  jz      short loc_1800050D6
0x180005155  mov     edx, 2Ah ; '*'
0x18000515a  jmp     loc_1800050C7
0x18000515f  xor     edx, edx; Val
0x180005161  lea     rcx, [rbp+0F0h+var_F0]; void *
0x180005165  lea     r8d, [rdx+50h]; Size
0x180005169  call    memset_0
0x18000516e  mov     rcx, [rsp+1F0h+var_1A0]
0x180005173  lea     rdx, [rbp+0F0h+var_F0]
0x180005177  mov     [rsp+1F0h+var_188], 0
0x180005180  mov     r8d, r14d
0x180005183  mov     rax, [rcx]
0x180005186  mov     rax, [rax+60h]
0x18000518a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518f  test    eax, eax
0x180005191  jns     short loc_1800051C6
0x180005193  mov     rcx, cs:WPP_GLOBAL_Control
0x18000519a  cmp     rcx, r15
0x18000519d  jz      loc_18000503C
0x1800051a3  test    [rcx+44h], r14b
0x1800051a7  jz      loc_18000503C
0x1800051ad  mov     rcx, [rcx+38h]
0x1800051b1  mov     edx, 2Bh ; '+'
0x1800051b6  mov     r9d, eax
0x1800051b9  mov     r8, r12
0x1800051bc  call    WPP_SF_d
0x1800051c1  jmp     loc_18000503C
0x1800051c6  mov     r10, [rbp+0F0h+var_160]
0x1800051ca  lea     r8, [rsp+1F0h+var_188]
0x1800051cf  mov     rdx, rbx
0x1800051d2  mov     rcx, r10
0x1800051d5  mov     rax, [r10]
0x1800051d8  mov     rax, [rax+0A0h]
0x1800051df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051e4  test    eax, eax
0x1800051e6  js      loc_18000503C
0x1800051ec  mov     rax, [rsp+1F0h+var_188]
0x1800051f1  mov     rcx, [rax]
0x1800051f4  mov     rdi, [rcx+50h]
0x1800051f8  lea     rcx, [rbp+0F0h+var_D0]; this
  ... truncated ...
```
