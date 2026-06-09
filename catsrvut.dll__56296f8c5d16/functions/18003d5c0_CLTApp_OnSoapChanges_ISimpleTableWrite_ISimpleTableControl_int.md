# CLTApp::OnSoapChanges(ISimpleTableWrite *,ISimpleTableControl *,int)

- ea: `0x18003d5c0`
- end: `0x18003e5ca`
- name: `?OnSoapChanges@CLTApp@@AEAAJPEAUISimpleTableWrite@@PEAUISimpleTableControl@@H@Z`
- size: `4106`
- prototype: `__int64 __fastcall(CLTApp *__hidden this, struct ISimpleTableWrite *, struct ISimpleTableControl *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003ef60`

## callees

- `0x180001e60`
- `0x180007604`
- `0x180014ec8`
- `0x18002b1ac`
- `0x18002cd50`
- `0x18003b088`
- `0x18003b36c`
- `0x18003d5c0`
- `0x18003e5d0`
- `0x180055880`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dcff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e1ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e224`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003dcff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e1ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e224`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003dca7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e15d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003dca7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003e15d`
- `OLEAUT32!__imp_SysFreeString` at `0x18003df80`
- `OLEAUT32!__imp_SysFreeString` at `0x18003dfab`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e01c`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e58b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e5b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18003df80`
- `OLEAUT32!__imp_SysFreeString` at `0x18003dfab`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e01c`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e58b`
- `OLEAUT32!__imp_SysFreeString` at `0x18003e5b7`
- `CLBCatQ!ServerGetApplicationType` at `0x18003ddb5`
- `CLBCatQ!ServerGetApplicationType` at `0x18003ddb5`

## string_xrefs

- `0x18003dba4`: `delete`
- `0x18003df15`: `delete`
- `0x18003e47c`: `delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CLTApp::OnSoapChanges(
        CLTApp *this,
        struct ISimpleTableWrite *a2,
        struct ISimpleTableControl *a3,
        int a4)
{
  __int64 v7; // r15
  char *v8; // rdi
  int Dispenser; // ebx
  __int64 v11; // rdx
  struct ISimpleTableDispenser *v12; // r13
  __int64 v13; // rcx
  int v14; // ecx
  int v15; // esi
  struct ISimpleTableDispenser *v16; // rdi
  __int64 v17; // rdi
  __int64 v18; // rdi
  __int64 v19; // rcx
  unsigned __int64 v20; // rax
  int v21; // eax
  const unsigned __int16 *v22; // rcx
  struct ISimpleTableWrite *v23; // rdx
  CLTApp *v24; // rcx
  struct ISimpleTableControl *v25; // r8
  __int64 v26; // rbx
  unsigned __int64 v27; // rdi
  unsigned __int16 *v28; // rax
  unsigned __int16 *v29; // rsi
  int v30; // eax
  __int64 v31; // rdx
  const unsigned __int16 *v32; // rcx
  int ApplicationType; // eax
  int v34; // ecx
  int v35; // r12d
  __int64 v36; // r15
  unsigned int v37; // edi
  int v38; // eax
  __int64 v39; // rdx
  const unsigned __int16 *v40; // rcx
  unsigned int i; // edi
  __int64 v42; // rdx
  OLECHAR *v43; // rcx
  const unsigned __int16 *v44; // rcx
  unsigned __int16 *v45; // rbx
  unsigned __int64 v46; // rsi
  unsigned __int16 *v47; // rax
  unsigned __int16 *v48; // rdi
  int v49; // eax
  __int64 v50; // rdx
  const unsigned __int16 *v51; // rcx
  __int64 v52; // rsi
  int v53; // eax
  int v54; // eax
  __int64 v55; // rdx
  const unsigned __int16 *v56; // rcx
  const wchar_t *v57; // rax
  unsigned int j; // edi
  unsigned int k; // edi
  struct ISimpleTableRead *v60; // [rsp+20h] [rbp-E0h]
  int v61; // [rsp+50h] [rbp-B0h] BYREF
  struct ISimpleTableWrite *v62; // [rsp+58h] [rbp-A8h] BYREF
  struct ISimpleTableRead *v63; // [rsp+60h] [rbp-A0h] BYREF
  int v64; // [rsp+68h] [rbp-98h] BYREF
  int v65; // [rsp+6Ch] [rbp-94h]
  struct ISimpleTableDispenser *v66; // [rsp+70h] [rbp-90h] BYREF
  int *v67; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID *v68; // [rsp+80h] [rbp-80h] BYREF
  BSTR v69[2]; // [rsp+90h] [rbp-70h] BYREF
  int v70; // [rsp+A0h] [rbp-60h] BYREF
  int v71; // [rsp+A4h] [rbp-5Ch] BYREF
  int v72; // [rsp+A8h] [rbp-58h] BYREF
  int v73; // [rsp+ACh] [rbp-54h] BYREF
  int v74; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v75; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v76; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v77; // [rsp+C8h] [rbp-38h] BYREF
  struct ISimpleTableControl *v78; // [rsp+D0h] [rbp-30h] BYREF
  struct _GUID v79; // [rsp+E0h] [rbp-20h] BYREF
  int v80; // [rsp+F0h] [rbp-10h]
  int v81; // [rsp+F4h] [rbp-Ch]
  unsigned __int16 *v82; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v83; // [rsp+108h] [rbp+8h]
  struct _GUID v84; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v85[4]; // [rsp+120h] [rbp+20h] BYREF
  struct _GUID v86; // [rsp+130h] [rbp+30h] BYREF
  int *v87; // [rsp+140h] [rbp+40h] BYREF
  int v88; // [rsp+148h] [rbp+48h]
  int v89; // [rsp+14Ch] [rbp+4Ch]
  int v90; // [rsp+150h] [rbp+50h]
  int v91; // [rsp+154h] [rbp+54h]
  struct _GUID *v92; // [rsp+158h] [rbp+58h]
  int v93; // [rsp+160h] [rbp+60h]
  int v94; // [rsp+164h] [rbp+64h]
  int v95; // [rsp+168h] [rbp+68h]
  int v96; // [rsp+16Ch] [rbp+6Ch]
  unsigned __int16 *v97[2]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v98; // [rsp+180h] [rbp+80h]
  _DWORD *v99; // [rsp+190h] [rbp+90h] BYREF
  __int64 v100; // [rsp+198h] [rbp+98h]
  __int64 v101; // [rsp+1A0h] [rbp+A0h]
  CLTApp *v102; // [rsp+1A8h] [rbp+A8h]
  BSTR v103[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v104; // [rsp+1C0h] [rbp+C0h]
  BSTR bstrString[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v106; // [rsp+1E0h] [rbp+E0h]
  BSTR v107[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int128 v108; // [rsp+200h] [rbp+100h]

  v78 = a3;
  v102 = this;
  v7 = 0;
  v67 = 0;
  v99 = 0;
  v76 = 0;
  v100 = 0;
  v83 = 0;
  v75 = 0;
  v101 = 0;
  v82 = 0;
  v68 = 0;
  v73 = 0;
  v72 = 0;
  v71 = 0;
  v70 = 0;
  v64 = 0;
  v85[0] = 0;
  v66 = 0;
  v63 = 0;
  v62 = 0;
  v74 = 0;
  v8 = (char *)this + 8;
  Dispenser = (*(__int64 (__fastcall **)(char *, __int64, _DWORD *, _QWORD, _QWORD, _DWORD **))(*((_QWORD *)this + 1)
                                                                                              + 152LL))(
                (char *)this + 8,
                33,
                v85,
                0,
                0,
                &v99);
  if ( Dispenser < 0 )
    goto LABEL_47;
  if ( !v99 )
  {
    Dispenser = -2147418113;
    goto LABEL_47;
  }
  if ( *v99 )
    return 0;
  Dispenser = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, _QWORD, _QWORD, struct _GUID **))(*(_QWORD *)v8 + 152LL))(
                v8,
                0,
                0,
                0,
                0,
                &v68);
  if ( Dispenser >= 0 )
  {
    *(_QWORD *)&v79.Data1 = v68;
    *(_QWORD *)v79.Data4 = 0;
    v80 = 72;
    v81 = 16;
    Dispenser = CLTApp::GetDispenser(this, &v66);
    v12 = v66;
    if ( Dispenser < 0 )
      goto LABEL_45;
    Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int128 *, const struct _GUID *, struct _GUID *, __int64, int, int, struct ISimpleTableRead **))(*(_QWORD *)v66 + 24LL))(
                  v66,
                  &didCOMSERVICES,
                  &TID_APPLICATION,
                  &v79,
                  1,
                  1,
                  131073,
                  &v63);
    if ( Dispenser < 0 )
      goto LABEL_45;
    Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v63 + 24LL))(v63);
    if ( Dispenser < 0 )
      goto LABEL_45;
    Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v63 + 40LL))(v63);
    if ( (int)(Dispenser + 0x80000000) >= 0 && Dispenser != -2146367487 )
      goto LABEL_45;
    v61 = 0;
    v11 = 0;
    *(_QWORD *)&v86.Data1 = 0;
    if ( !Dispenser )
    {
      Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD, _QWORD, int **))(*(_QWORD *)v63 + 64LL))(
                    v63,
                    53,
                    0,
                    0,
                    &v67);
      v11 = 0;
      if ( Dispenser < 0 )
        goto LABEL_45;
      v61 = *v67;
      if ( v61 )
      {
        Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD, _QWORD, unsigned __int16 **))(*(_QWORD *)v63 + 64LL))(
                      v63,
                      54,
                      0,
                      0,
                      &v75);
        if ( Dispenser < 0 )
          goto LABEL_45;
        if ( v75 )
        {
          v7 = -1;
          do
            ++v7;
          while ( v75[v7] );
        }
        Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD))(*(_QWORD *)v63 + 64LL))(
                      v63,
                      55,
                      0);
        if ( Dispenser < 0 )
          goto LABEL_45;
        Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableRead *, __int64, _QWORD))(*(_QWORD *)v63 + 64LL))(
                      v63,
                      56,
                      0);
        v11 = 0;
        if ( Dispenser < 0 )
          goto LABEL_45;
        if ( v82 )
        {
          v13 = -1;
          do
            ++v13;
          while ( v82[v13] );
          *(_QWORD *)&v86.Data1 = v13;
        }
      }
    }
    v14 = 0;
    v65 = 0;
    v15 = 0;
    v16 = 0;
    v66 = 0;
    v77 = 0;
    if ( !a4 )
    {
      Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *, _QWORD, _QWORD, int **))(*(_QWORD *)a2 + 152LL))(
                    a2,
                    53,
                    &v73,
                    0,
                    0,
                    &v67);
      v11 = 0;
      if ( Dispenser < 0 )
        goto LABEL_45;
      v65 = *v67;
      if ( v65 )
      {
        Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *, _QWORD, _QWORD, unsigned __int16 **))(*(_QWORD *)a2 + 152LL))(
                      a2,
                      54,
                      &v72,
                      0,
                      0,
                      &v76);
        v11 = 0;
        if ( Dispenser < 0 )
          goto LABEL_45;
        if ( v76 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v76[v17] );
          v66 = (struct ISimpleTableDispenser *)v17;
        }
        Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *))(*(_QWORD *)a2 + 152LL))(
                      a2,
                      55,
                      &v71);
        v11 = 0;
        if ( Dispenser < 0 )
          goto LABEL_45;
        v18 = 0;
        if ( v100 )
        {
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)(v100 + 2 * v18) );
        }
        Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *))(*(_QWORD *)a2 + 152LL))(
                      a2,
                      56,
                      &v70);
        v11 = 0;
        if ( Dispenser < 0 )
          goto LABEL_45;
        if ( v83 )
        {
          v19 = -1;
          do
            ++v19;
          while ( v83[v19] );
          v77 = (unsigned __int16 *)v19;
        }
        v20 = v18 - 1;
        v16 = v66;
        if ( v20 > 0x102 && (unsigned __int64)v66 - 1 > 0x102 )
        {
          Dispenser = -2147024809;
          goto LABEL_45;
        }
      }
      Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *))(*(_QWORD *)a2 + 152LL))(
                    a2,
                    22,
                    &v64);
      v11 = 0;
      if ( Dispenser < 0 )
        goto LABEL_45;
      if ( (v64 & 2) != 0 )
      {
        v15 = 1;
        v14 = v65;
      }
      else
      {
        Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, int *))(*(_QWORD *)a2 + 152LL))(
                      a2,
                      12,
                      &v64);
        if ( (v64 & 2) != 0 )
          v15 = 1;
        v14 = v65;
        v11 = 0;
      }
    }
    v21 = v61;
    if ( !v61 && !v14 && !v15 )
      goto LABEL_61;
    if ( !a4 && !v15 )
    {
      if ( (((unsigned __int8)v73 | (unsigned __int8)(v72 | v71 | v70)) & 2) == 0 )
        goto LABEL_61;
      v21 = v61;
    }
    if ( !v14 && v21 )
      a4 = 1;
    if ( (v16 || !v7) && (!a4 || !v7) )
    {
      v35 = 0x200000;
      goto LABEL_110;
    }
    v61 = 0;
    Dispenser = CheckIfCLRPresent(v12, &v61);
    if ( Dispenser < 0 )
      goto LABEL_45;
    if ( v61 )
    {
      *(_OWORD *)v103 = xmmword_1800657A8;
      *(_OWORD *)v69 = xmmword_1800657B8;
      if ( !(unsigned int)ExecuteManagedRequestBitnessAware(
                            v22,
                            v11,
                            (struct _GUID *)v69,
                            (struct _GUID *)v103,
                            3u,
                            0,
                            0,
                            0,
                            0) )
      {
        Dispenser = CLTApp::DeleteSoapVRoot(v24, v23, v25, v12, v60, v62, v82, v75, v68);
        goto LABEL_45;
      }
      *(_OWORD *)v107 = 0;
      v108 = 0;
      v103[0] = L"delete";
      v26 = *(_QWORD *)&v86.Data1;
      v27 = v7 + *(_QWORD *)&v86.Data1 + 1LL;
      v28 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v27, 2u));
      v29 = v28;
      if ( !v28 )
        goto LABEL_78;
      if ( v26 )
      {
        Dispenser = StringCchCopyW(v28, v27, v82);
        if ( Dispenser < 0 )
        {
LABEL_84:
          CoTaskMemFree(v29);
          goto LABEL_45;
        }
        v30 = StringCchCatW(v29, v27, v75);
      }
      else
      {
        v30 = StringCchCopyW(v28, v27, v75);
      }
      Dispenser = v30;
      if ( v30 < 0 )
        goto LABEL_84;
      v103[1] = v29;
      UploadSQMData<enum CatalogServerSQMFlags>(4);
      *(GUID *)v69 = IID_IComSoapPublisher;
      v86 = CLSID_ComSoapPublisher;
      ExecuteManagedRequestBitnessAware(v32, v31, &v86, (struct _GUID *)v69, 4u, 2u, v103, 4u, v107);
      v61 = 1;
      v87 = &v61;
      v88 = 0;
      v89 = -268435451;
      v90 = 19;
      v91 = 4;
      v92 = v68;
      v93 = 0;
      v94 = 9;
      v95 = 72;
      v96 = 16;
      ApplicationType = ServerGetApplicationType(v12, v68, &v74);
      v34 = 0x400000;
      if ( v74 == 1 )
        v34 = 0x200000;
      v35 = v34;
      if ( !ApplicationType )
      {
        ApplicationType = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int128 *, const struct _GUID *, int **, __int64, int, int, struct ISimpleTableWrite **))(*(_QWORD *)v12 + 24LL))(
                            v12,
                            &didCOMSERVICES,
                            &tidCOMSERVICES_CLASSES,
                            &v87,
                            2,
                            1,
                            v34,
                            &v62);
        if ( !ApplicationType )
          ApplicationType = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v62 + 24LL))(v62);
      }
      Dispenser = 0;
      if ( ApplicationType != -2146367486 )
        Dispenser = ApplicationType;
      if ( !Dispenser )
        Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v62 + 32LL))(v62);
      v36 = v108;
      while ( 1 )
      {
        v37 = 0;
        if ( Dispenser )
          break;
        v69[0] = 0;
        *(_QWORD *)&v86.Data1 = 0;
        *(_OWORD *)v97 = 0;
        v98 = 0;
        *(_OWORD *)bstrString = 0;
        *(_QWORD *)&v106 = 0;
        v38 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v62 + 40LL))(v62);
        Dispenser = v38;
        if ( v38 == -2146367487 )
        {
          Dispenser = 0;
          break;
        }
        if ( !v38 )
        {
          Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, _QWORD, struct _GUID *))(*(_QWORD *)v62 + 64LL))(
                        v62,
                        3,
                        0,
                        0,
                        &v86);
          if ( !Dispenser )
          {
            Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, _QWORD, BSTR *))(*(_QWORD *)v62 + 64LL))(
                          v62,
                          1,
                          0,
                          0,
                          v69);
            if ( !Dispenser )
            {
              v97[0] = *(unsigned __int16 **)&v86.Data1;
              v97[1] = v69[0];
              *(_QWORD *)&v98 = v36;
              *((_QWORD *)&v98 + 1) = L"delete";
              v84 = IID_IComSoapPublisher;
              v79 = CLSID_ComSoapPublisher;
              ExecuteManagedRequestBitnessAware(v40, v39, &v79, &v84, 8u, 4u, v97, 3u, bstrString);
            }
          }
        }
        do
          SysFreeString(bstrString[v37++]);
        while ( v37 < 3 );
      }
      for ( i = 0; i < 4; ++i )
        SysFreeString(v107[i]);
      v43 = 0;
      v69[0] = 0;
      if ( !Dispenser )
      {
        v79 = IID_IComSoapPublisher;
        v84 = CLSID_ComSoapPublisher;
        ExecuteManagedRequestBitnessAware(0, v42, &v84, &v79, 5u, 2u, v103, 1u, v69);
        v43 = v69[0];
      }
      SysFreeString(v43);
      CoTaskMemFree(v29);
      v16 = v66;
      v14 = v65;
LABEL_110:
      if ( v14 )
      {
        if ( v16 )
        {
          v61 = 0;
          Dispenser = CheckIfCLRPresent(v12, &v61);
          if ( Dispenser >= 0 )
          {
            if ( !v61 )
            {
              Dispenser = -2147467224;
              goto LABEL_45;
            }
            v79 = (struct _GUID)xmmword_1800657A8;
            v84 = (struct _GUID)xmmword_1800657B8;
            if ( !(unsigned int)ExecuteManagedRequestBitnessAware(v44, v11, &v84, &v79, 3u, 0, 0, 0, 0) )
            {
              UploadSQMData<enum CatalogServerSQMFlags>(4);
              Dispenser = CLTApp::PublishSoapVRoot(v102, a2, v78, v12, v63, v62, v83, v76, v68);
              goto LABEL_45;
            }
            *(_OWORD *)bstrString = 0;
            v106 = 0;
            v103[0] = (BSTR)&Password;
            v45 = v77;
            v46 = (unsigned __int64)v77 + (_QWORD)v16 + 1;
            v47 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v46, 2u));
            v48 = v47;
            if ( !v47 )
            {
LABEL_78:
              Dispenser = -2147024882;
              goto LABEL_45;
            }
            if ( v45 )
            {
              Dispenser = StringCchCopyW(v47, v46, v83);
              if ( Dispenser < 0 )
              {
LABEL_123:
                CoTaskMemFree(v48);
                goto LABEL_45;
              }
              v49 = StringCchCatW(v48, v46, v76);
            }
            else
            {
              v49 = StringCchCopyW(v47, v46, v76);
            }
            Dispenser = v49;
            if ( v49 >= 0 )
            {
              v103[1] = v48;
              UploadSQMData<enum CatalogServerSQMFlags>(4);
              v79 = IID_IComSoapPublisher;
              v84 = CLSID_ComSoapPublisher;
              Dispenser = ExecuteManagedRequestBitnessAware(v51, v50, &v84, &v79, 4u, 2u, v103, 4u, bstrString);
              CoTaskMemFree(v48);
              if ( !Dispenser )
              {
                Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableControl *))(*(_QWORD *)v78 + 80LL))(v78);
                if ( !Dispenser )
                {
                  Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, BSTR))(*(_QWORD *)a2 + 160LL))(
                                a2,
                                56,
                                0,
                                bstrString[0]);
                  if ( !Dispenser )
                  {
                    Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, BSTR))(*(_QWORD *)a2 + 160LL))(
                                  a2,
                                  54,
                                  0,
                                  bstrString[1]);
                    if ( !Dispenser )
                      Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)a2 + 144LL))(a2);
                  }
                }
                v61 = 1;
                v87 = &v61;
                v88 = 0;
                v89 = -268435451;
                v90 = 19;
                v91 = 4;
                v92 = v68;
                v93 = 0;
                v94 = 9;
                v95 = 72;
                v96 = 16;
                if ( !Dispenser )
                {
                  Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableDispenser *, __int128 *, const struct _GUID *, int **, __int64, int, int, struct ISimpleTableWrite **))(*(_QWORD *)v12 + 24LL))(
                                v12,
                                &didCOMSERVICES,
                                &tidCOMSERVICES_CLASSES,
                                &v87,
                                2,
                                1,
                                v35,
                                &v62);
                  if ( !Dispenser )
                  {
                    Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v62 + 24LL))(v62);
                    if ( !Dispenser )
                      Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v62 + 32LL))(v62);
                  }
                }
                v52 = v106;
                while ( !Dispenser )
                {
                  v69[0] = 0;
                  v77 = 0;
                  v78 = 0;
                  *(_OWORD *)v97 = 0;
                  v98 = 0;
                  *(_OWORD *)v103 = 0;
                  v104 = 0;
                  v53 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v62 + 40LL))(v62);
                  Dispenser = v53;
                  if ( v53 == -2146367487 )
                  {
                    Dispenser = 0;
                    break;
                  }
                  if ( !v53 )
                  {
                    Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, _QWORD, unsigned __int16 **))(*(_QWORD *)v62 + 64LL))(
                                  v62,
                                  3,
                                  0,
                                  0,
                                  &v77);
                    if ( !Dispenser )
                    {
                      Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, _QWORD, BSTR *))(*(_QWORD *)v62 + 64LL))(
                                    v62,
                                    1,
                                    0,
                                    0,
                                    v69);
                      if ( !Dispenser )
                      {
                        v54 = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, _QWORD, struct ISimpleTableControl **))(*(_QWORD *)v62 + 64LL))(
                                v62,
                                54,
                                0,
                                0,
                                &v78);
                        Dispenser = v54;
                        v56 = v78 ? (const unsigned __int16 *)*(unsigned int *)v78 : 0LL;
                        if ( !v54 )
                        {
                          v97[0] = v77;
                          v97[1] = v69[0];
                          *(_QWORD *)&v98 = v52;
                          v57 = L"delete";
                          if ( !(_DWORD)v56 )
                            v57 = &Password;
                          *((_QWORD *)&v98 + 1) = v57;
                          v79 = IID_IComSoapPublisher;
                          v84 = CLSID_ComSoapPublisher;
                          Dispenser = ExecuteManagedRequestBitnessAware(v56, v55, &v84, &v79, 8u, 4u, v97, 3u, v103);
                          if ( !Dispenser )
                          {
                            Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v62 + 128LL))(v62);
                            if ( !Dispenser )
                            {
                              Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, BSTR))(*(_QWORD *)v62 + 160LL))(
                                            v62,
                                            55,
                                            0,
                                            v103[0]);
                              if ( !Dispenser )
                              {
                                Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *, __int64, _QWORD, BSTR))(*(_QWORD *)v62 + 160LL))(
                                              v62,
                                              56,
                                              0,
                                              v103[1]);
                                if ( !Dispenser )
                                {
                                  Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v62 + 144LL))(v62);
                                  if ( !Dispenser )
                                    Dispenser = (*(__int64 (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v62 + 96LL))(v62);
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                  for ( j = 0; j < 3; ++j )
                    SysFreeString(v103[j]);
                }
              }
              for ( k = 0; k < 4; ++k )
                SysFreeString(bstrString[k]);
              goto LABEL_45;
            }
            goto LABEL_123;
          }
        }
      }
LABEL_45:
      if ( v12 )
        (*(void (__fastcall **)(struct ISimpleTableDispenser *, __int64))(*(_QWORD *)v12 + 16LL))(v12, v11);
      goto LABEL_47;
    }
LABEL_61:
    Dispenser = 0;
    goto LABEL_45;
  }
LABEL_47:
  if ( v63 )
  {
    (*(void (__fastcall **)(struct ISimpleTableRead *))(*(_QWORD *)v63 + 16LL))(v63);
    v63 = 0;
  }
  if ( v62 )
    (*(void (__fastcall **)(struct ISimpleTableWrite *))(*(_QWORD *)v62 + 16LL))(v62);
  return (unsigned int)Dispenser;
}

```

## disassembly

```asm
0x18003d5c0  mov     [rsp-8+arg_18], rbx
0x18003d5c5  push    rbp
0x18003d5c6  push    rsi
0x18003d5c7  push    rdi
0x18003d5c8  push    r12
0x18003d5ca  push    r13
0x18003d5cc  push    r14
0x18003d5ce  push    r15
0x18003d5d0  lea     rbp, [rsp-120h]
0x18003d5d8  sub     rsp, 220h
0x18003d5df  mov     rax, cs:__security_cookie
0x18003d5e6  xor     rax, rsp
0x18003d5e9  mov     [rbp+150h+var_40], rax
0x18003d5f0  mov     r12d, r9d
0x18003d5f3  mov     [rbp+150h+var_180], r8
0x18003d5f7  mov     r14, rdx
0x18003d5fa  mov     rsi, rcx
0x18003d5fd  mov     [rbp+150h+var_A8], rcx
0x18003d604  xor     r15d, r15d
0x18003d607  mov     [rsp+250h+var_1D8], r15
0x18003d60c  mov     [rbp+150h+var_C0], r15
0x18003d613  mov     [rbp+150h+var_190], r15
0x18003d617  mov     [rbp+150h+var_B8], r15
0x18003d61e  mov     [rbp+150h+var_148], r15
0x18003d622  mov     [rbp+150h+var_198], r15
0x18003d626  mov     [rbp+150h+var_B0], r15
0x18003d62d  mov     [rbp+150h+var_150], r15
0x18003d631  mov     [rbp+150h+var_1D0], r15
0x18003d635  mov     [rbp+150h+var_1A4], r15d
0x18003d639  mov     [rbp+150h+var_1A8], r15d
0x18003d63d  mov     [rbp+150h+var_1AC], r15d
0x18003d641  mov     [rbp+150h+var_1B0], r15d
0x18003d645  mov     [rsp+250h+var_1E8], r15d
0x18003d64a  mov     [rbp+150h+var_130], r15d
0x18003d64e  mov     [rsp+250h+var_1E0], r15
0x18003d653  mov     [rsp+250h+var_1F0], r15
0x18003d658  mov     [rsp+250h+var_1F8], r15
0x18003d65d  mov     [rbp+150h+var_1A0], r15d
0x18003d661  lea     rdi, [rcx+8]
0x18003d665  mov     rax, [rdi]
0x18003d668  lea     rcx, [rbp+150h+var_C0]
0x18003d66f  mov     [rsp+250h+var_228], rcx
0x18003d674  mov     [rsp+250h+var_230], r15
0x18003d679  xor     r9d, r9d
0x18003d67c  lea     r8, [rbp+150h+var_130]
0x18003d680  lea     edx, [r15+21h]
0x18003d684  mov     rcx, rdi
0x18003d687  mov     rax, [rax+98h]
0x18003d68e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d693  mov     ebx, eax
0x18003d695  test    eax, eax
0x18003d697  js      loc_18003DA6C
0x18003d69d  mov     rax, [rbp+150h+var_C0]
0x18003d6a4  test    rax, rax
0x18003d6a7  jnz     short loc_18003D6B3
0x18003d6a9  mov     ebx, 8000FFFFh
0x18003d6ae  jmp     loc_18003DA6C
0x18003d6b3  cmp     [rax], r15d
0x18003d6b6  jz      short loc_18003D6BF
0x18003d6b8  xor     eax, eax
0x18003d6ba  jmp     loc_18003DA9F
0x18003d6bf  mov     rax, [rdi]
0x18003d6c2  lea     rcx, [rbp+150h+var_1D0]
0x18003d6c6  mov     [rsp+250h+var_228], rcx
0x18003d6cb  mov     [rsp+250h+var_230], r15
0x18003d6d0  xor     r9d, r9d
0x18003d6d3  xor     r8d, r8d
0x18003d6d6  xor     edx, edx
0x18003d6d8  mov     rcx, rdi
0x18003d6db  mov     rax, [rax+98h]
0x18003d6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6e7  mov     ebx, eax
0x18003d6e9  test    eax, eax
0x18003d6eb  js      loc_18003DA6C
0x18003d6f1  mov     rax, [rbp+150h+var_1D0]
0x18003d6f5  mov     qword ptr [rbp+150h+var_170.Data1], rax
0x18003d6f9  mov     qword ptr [rbp+150h+var_170.Data4], r15
0x18003d6fd  mov     [rbp+150h+var_160], 48h ; 'H'
0x18003d704  mov     [rbp+150h+var_15C], 10h
0x18003d70b  lea     rdx, [rsp+250h+var_1E0]; struct ISimpleTableDispenser **
0x18003d710  mov     rcx, rsi; this
0x18003d713  call    ?GetDispenser@CLTApp@@AEAAJPEAPEAUISimpleTableDispenser@@@Z; CLTApp::GetDispenser(ISimpleTableDispenser * *)
0x18003d718  mov     ebx, eax
0x18003d71a  mov     r13, [rsp+250h+var_1E0]
0x18003d71f  test    eax, eax
0x18003d721  js      loc_18003DA57
0x18003d727  mov     rax, [r13+0]
0x18003d72b  lea     rcx, [rsp+250h+var_1F0]
0x18003d730  mov     [rsp+250h+var_218], rcx
0x18003d735  mov     dword ptr [rsp+250h+var_220], 20001h
0x18003d73d  mov     ecx, 1
0x18003d742  mov     dword ptr [rsp+250h+var_228], ecx
0x18003d746  mov     [rsp+250h+var_230], rcx
0x18003d74b  lea     r9, [rbp+150h+var_170]
0x18003d74f  lea     r8, TID_APPLICATION
0x18003d756  lea     rdx, didCOMSERVICES
0x18003d75d  mov     rcx, r13
0x18003d760  mov     rax, [rax+18h]
0x18003d764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d769  mov     ebx, eax
0x18003d76b  test    eax, eax
0x18003d76d  js      loc_18003DA57
0x18003d773  mov     rcx, [rsp+250h+var_1F0]
0x18003d778  mov     rax, [rcx]
0x18003d77b  mov     rax, [rax+18h]
0x18003d77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d784  mov     ebx, eax
0x18003d786  test    eax, eax
0x18003d788  js      loc_18003DA57
0x18003d78e  mov     rcx, [rsp+250h+var_1F0]
0x18003d793  mov     rax, [rcx]
0x18003d796  mov     rax, [rax+28h]
0x18003d79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d79f  mov     ebx, eax
0x18003d7a1  mov     ecx, 80000000h
0x18003d7a6  add     eax, ecx
0x18003d7a8  test    ecx, eax
0x18003d7aa  jnz     short loc_18003D7B8
0x18003d7ac  cmp     ebx, 80110801h
0x18003d7b2  jnz     loc_18003DA57
0x18003d7b8  mov     [rsp+250h+var_200], r15d
0x18003d7bd  xor     edx, edx
0x18003d7bf  mov     qword ptr [rbp+150h+var_120.Data1], rdx
0x18003d7c3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003d7c7  test    ebx, ebx
0x18003d7c9  jnz     loc_18003D8D1
0x18003d7cf  mov     rcx, [rsp+250h+var_1F0]
0x18003d7d4  mov     rax, [rcx]
0x18003d7d7  lea     rdx, [rsp+250h+var_1D8]
0x18003d7dc  mov     [rsp+250h+var_230], rdx
0x18003d7e1  xor     r9d, r9d
0x18003d7e4  xor     r8d, r8d
0x18003d7e7  lea     edx, [rsi+36h]
0x18003d7ea  mov     rax, [rax+40h]
0x18003d7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d7f3  mov     ebx, eax
0x18003d7f5  xor     edx, edx
0x18003d7f7  test    eax, eax
0x18003d7f9  js      loc_18003DA57
0x18003d7ff  mov     rax, [rsp+250h+var_1D8]
0x18003d804  mov     eax, [rax]
0x18003d806  mov     [rsp+250h+var_200], eax
0x18003d80a  test    eax, eax
0x18003d80c  jz      loc_18003D8D1
0x18003d812  mov     rcx, [rsp+250h+var_1F0]
0x18003d817  mov     rax, [rcx]
0x18003d81a  lea     rdx, [rbp+150h+var_198]
0x18003d81e  mov     [rsp+250h+var_230], rdx
0x18003d823  xor     r9d, r9d
0x18003d826  xor     r8d, r8d
0x18003d829  lea     edx, [rsi+37h]
0x18003d82c  mov     rax, [rax+40h]
0x18003d830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d835  mov     ebx, eax
0x18003d837  xor     edi, edi
0x18003d839  test    eax, eax
0x18003d83b  js      loc_18003DA57
0x18003d841  mov     rax, [rbp+150h+var_198]
0x18003d845  test    rax, rax
0x18003d848  jz      short loc_18003D857
0x18003d84a  mov     r15, rsi
0x18003d84d  inc     r15
0x18003d850  cmp     [rax+r15*2], di
0x18003d855  jnz     short loc_18003D84D
0x18003d857  mov     rcx, [rsp+250h+var_1F0]
0x18003d85c  mov     rax, [rcx]
0x18003d85f  lea     rdx, [rbp+150h+var_B0]
0x18003d866  mov     [rsp+250h+var_230], rdx
0x18003d86b  xor     r9d, r9d
0x18003d86e  xor     r8d, r8d
0x18003d871  lea     edx, [r9+37h]
0x18003d875  mov     rax, [rax+40h]
0x18003d879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d87e  mov     ebx, eax
0x18003d880  test    eax, eax
0x18003d882  js      loc_18003DA54
0x18003d888  mov     rcx, [rsp+250h+var_1F0]
0x18003d88d  mov     rax, [rcx]
0x18003d890  lea     rdx, [rbp+150h+var_150]
0x18003d894  mov     [rsp+250h+var_230], rdx
0x18003d899  xor     r9d, r9d
0x18003d89c  xor     r8d, r8d
0x18003d89f  lea     edx, [r9+38h]
0x18003d8a3  mov     rax, [rax+40h]
0x18003d8a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d8ac  mov     ebx, eax
0x18003d8ae  xor     edx, edx
0x18003d8b0  test    eax, eax
0x18003d8b2  js      loc_18003DA54
0x18003d8b8  mov     rax, [rbp+150h+var_150]
0x18003d8bc  test    rax, rax
0x18003d8bf  jz      short loc_18003D8D1
0x18003d8c1  mov     rcx, rsi
0x18003d8c4  inc     rcx
0x18003d8c7  cmp     [rax+rcx*2], dx
0x18003d8cb  jnz     short loc_18003D8C4
0x18003d8cd  mov     qword ptr [rbp+150h+var_120.Data1], rcx
0x18003d8d1  mov     ecx, edx
0x18003d8d3  mov     [rsp+250h+var_1E4], edx
0x18003d8d7  mov     esi, edx
0x18003d8d9  mov     rdi, rdx
0x18003d8dc  mov     [rsp+250h+var_1E0], rdx
0x18003d8e1  mov     [rbp+150h+var_188], rdx
0x18003d8e5  test    r12d, r12d
0x18003d8e8  jnz     loc_18003DB5C
0x18003d8ee  mov     rax, [r14]
0x18003d8f1  lea     rcx, [rsp+250h+var_1D8]
0x18003d8f6  mov     [rsp+250h+var_228], rcx
0x18003d8fb  mov     [rsp+250h+var_230], rdx
0x18003d900  xor     r9d, r9d
0x18003d903  lea     r8, [rbp+150h+var_1A4]
0x18003d907  lea     edx, [r12+35h]
0x18003d90c  mov     rcx, r14
0x18003d90f  mov     rax, [rax+98h]
0x18003d916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d91b  mov     ebx, eax
0x18003d91d  xor     edx, edx
0x18003d91f  test    eax, eax
0x18003d921  js      loc_18003DA54
0x18003d927  mov     rax, [rsp+250h+var_1D8]
0x18003d92c  mov     ecx, [rax]
0x18003d92e  mov     [rsp+250h+var_1E4], ecx
0x18003d932  test    ecx, ecx
0x18003d934  jz      loc_18003DAC9
0x18003d93a  mov     rax, [r14]
0x18003d93d  lea     rcx, [rbp+150h+var_190]
0x18003d941  mov     [rsp+250h+var_228], rcx
0x18003d946  mov     [rsp+250h+var_230], rdx
0x18003d94b  xor     r9d, r9d
0x18003d94e  lea     r8, [rbp+150h+var_1A8]
0x18003d952  lea     edx, [r12+36h]
0x18003d957  mov     rcx, r14
0x18003d95a  mov     rax, [rax+98h]
0x18003d961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d966  mov     ebx, eax
0x18003d968  xor     edx, edx
0x18003d96a  test    eax, eax
0x18003d96c  js      loc_18003DA54
0x18003d972  mov     rax, [rbp+150h+var_190]
0x18003d976  test    rax, rax
0x18003d979  jz      short loc_18003D98D
0x18003d97b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003d97f  inc     rdi
0x18003d982  cmp     [rax+rdi*2], dx
0x18003d986  jnz     short loc_18003D97F
0x18003d988  mov     [rsp+250h+var_1E0], rdi
0x18003d98d  mov     rax, [r14]
0x18003d990  lea     rcx, [rbp+150h+var_B8]
0x18003d997  mov     [rsp+250h+var_228], rcx
0x18003d99c  mov     [rsp+250h+var_230], rdx
0x18003d9a1  xor     r9d, r9d
0x18003d9a4  lea     r8, [rbp+150h+var_1AC]
0x18003d9a8  lea     edx, [r9+37h]
0x18003d9ac  mov     rcx, r14
0x18003d9af  mov     rax, [rax+98h]
0x18003d9b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d9bb  mov     ebx, eax
0x18003d9bd  xor     edx, edx
0x18003d9bf  test    eax, eax
0x18003d9c1  js      loc_18003DA54
0x18003d9c7  mov     edi, edx
0x18003d9c9  mov     rax, [rbp+150h+var_B8]
0x18003d9d0  test    rax, rax
0x18003d9d3  jz      short loc_18003D9E2
0x18003d9d5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003d9d9  inc     rdi
0x18003d9dc  cmp     [rax+rdi*2], dx
0x18003d9e0  jnz     short loc_18003D9D9
0x18003d9e2  mov     rax, [r14]
0x18003d9e5  lea     rcx, [rbp+150h+var_148]
0x18003d9e9  mov     [rsp+250h+var_228], rcx
0x18003d9ee  mov     [rsp+250h+var_230], rdx
0x18003d9f3  xor     r9d, r9d
0x18003d9f6  lea     r8, [rbp+150h+var_1B0]
0x18003d9fa  lea     edx, [r9+38h]
0x18003d9fe  mov     rcx, r14
0x18003da01  mov     rax, [rax+98h]
0x18003da08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003da0d  mov     ebx, eax
0x18003da0f  xor     edx, edx
0x18003da11  test    eax, eax
0x18003da13  js      short loc_18003DA54
0x18003da15  mov     rax, [rbp+150h+var_148]
0x18003da19  test    rax, rax
0x18003da1c  jz      short loc_18003DA2F
0x18003da1e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003da22  inc     rcx
0x18003da25  cmp     [rax+rcx*2], dx
0x18003da29  jnz     short loc_18003DA22
0x18003da2b  mov     [rbp+150h+var_188], rcx
0x18003da2f  lea     rax, [rdi-1]
0x18003da33  mov     ecx, 102h
0x18003da38  mov     rdi, [rsp+250h+var_1E0]
0x18003da3d  cmp     rax, rcx
0x18003da40  jbe     loc_18003DAC9
0x18003da46  lea     rax, [rdi-1]
0x18003da4a  cmp     rax, rcx
0x18003da4d  jbe     short loc_18003DAC9
0x18003da4f  mov     ebx, 80070057h
0x18003da54  xor     r15d, r15d
  ... truncated ...
```
