# CSDTIMetaData::PopulateCache(void)

- ea: `0x180040470`
- end: `0x180041915`
- name: `?PopulateCache@CSDTIMetaData@@UEAAJXZ`
- size: `5285`
- prototype: `__int64 __fastcall(CSDTIMetaData *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001e60`
- `0x18000717c`
- `0x180015594`
- `0x180040470`
- `0x180055822`
- `0x180055880`
- `0x180055940`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800405c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800405c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800418b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800418da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800418e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041764`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800418b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800418da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800418e9`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180041269`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180041269`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800414ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180041504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800415cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800414ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180041504`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800415cf`
- `OLEAUT32!__imp_VariantClear` at `0x18004160a`
- `OLEAUT32!__imp_VariantClear` at `0x1800418cc`
- `OLEAUT32!__imp_VariantClear` at `0x18004160a`
- `OLEAUT32!__imp_VariantClear` at `0x1800418cc`

## string_xrefs

- `0x1800414c8`: `Allow_Access_%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSDTIMetaData::PopulateCache(CSDTIMetaData *this)
{
  unsigned int v2; // r15d
  unsigned __int16 *v4; // r13
  unsigned __int16 *v5; // rsi
  HRESULT v6; // ebx
  __int64 *v7; // rcx
  __int16 v8; // r10
  unsigned int v9; // eax
  unsigned int i; // r14d
  _QWORD *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  int *v15; // r9
  __int64 (__fastcall *v16)(__int64, __int64, _QWORD, int *); // rax
  __int64 v17; // rax
  unsigned int v18; // eax
  unsigned int j; // esi
  __int64 v20; // rax
  unsigned int v21; // eax
  unsigned int k; // esi
  __int64 v23; // rax
  unsigned int v24; // eax
  unsigned int m; // esi
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  unsigned int v29; // eax
  __int64 v30; // rax
  _QWORD *v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  unsigned int v35; // eax
  unsigned int n; // esi
  unsigned __int64 v37; // rbx
  void *v38; // rax
  unsigned __int64 v39; // rbx
  __int64 v40; // r10
  SIZE_T v41; // rax
  unsigned __int16 *v42; // rax
  int v43; // ebx
  unsigned int v44; // ebx
  __int64 v45; // r10
  SIZE_T v46; // rax
  unsigned __int16 *v47; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-100h]
  __int64 v49; // [rsp+30h] [rbp-F0h]
  __int64 v50; // [rsp+30h] [rbp-F0h]
  __int64 v51; // [rsp+48h] [rbp-D8h]
  __int64 *v52; // [rsp+A0h] [rbp-80h] BYREF
  unsigned __int16 *v53; // [rsp+A8h] [rbp-78h]
  unsigned int v54; // [rsp+B0h] [rbp-70h] BYREF
  int v55; // [rsp+B4h] [rbp-6Ch] BYREF
  int v56; // [rsp+B8h] [rbp-68h] BYREF
  int v57; // [rsp+BCh] [rbp-64h] BYREF
  unsigned int v58; // [rsp+C0h] [rbp-60h]
  __int64 v59; // [rsp+C8h] [rbp-58h] BYREF
  int v60; // [rsp+D0h] [rbp-50h] BYREF
  unsigned int v61; // [rsp+D4h] [rbp-4Ch] BYREF
  unsigned int v62; // [rsp+D8h] [rbp-48h] BYREF
  int v63; // [rsp+DCh] [rbp-44h] BYREF
  unsigned int v64; // [rsp+E0h] [rbp-40h] BYREF
  int v65; // [rsp+E4h] [rbp-3Ch] BYREF
  int v66; // [rsp+E8h] [rbp-38h] BYREF
  int v67; // [rsp+ECh] [rbp-34h] BYREF
  int v68; // [rsp+F0h] [rbp-30h] BYREF
  int v69; // [rsp+F4h] [rbp-2Ch] BYREF
  unsigned int v70; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v71; // [rsp+100h] [rbp-20h] BYREF
  __int64 v72; // [rsp+108h] [rbp-18h] BYREF
  __int64 v73; // [rsp+110h] [rbp-10h] BYREF
  int v74; // [rsp+118h] [rbp-8h] BYREF
  int v75; // [rsp+11Ch] [rbp-4h] BYREF
  int v76; // [rsp+120h] [rbp+0h] BYREF
  int v77; // [rsp+124h] [rbp+4h] BYREF
  int v78; // [rsp+128h] [rbp+8h] BYREF
  int v79; // [rsp+12Ch] [rbp+Ch] BYREF
  int v80; // [rsp+130h] [rbp+10h] BYREF
  int v81; // [rsp+134h] [rbp+14h] BYREF
  int v82; // [rsp+138h] [rbp+18h] BYREF
  int v83; // [rsp+13Ch] [rbp+1Ch] BYREF
  unsigned __int64 v84; // [rsp+140h] [rbp+20h] BYREF
  int v85; // [rsp+148h] [rbp+28h] BYREF
  int v86; // [rsp+14Ch] [rbp+2Ch] BYREF
  int v87; // [rsp+150h] [rbp+30h] BYREF
  int v88; // [rsp+154h] [rbp+34h] BYREF
  int v89; // [rsp+158h] [rbp+38h] BYREF
  VARIANTARG *pvarg; // [rsp+160h] [rbp+40h] BYREF
  LPVOID v91; // [rsp+168h] [rbp+48h] BYREF
  int v92; // [rsp+170h] [rbp+50h] BYREF
  int v93; // [rsp+174h] [rbp+54h] BYREF
  int v94; // [rsp+178h] [rbp+58h] BYREF
  __int64 v95; // [rsp+180h] [rbp+60h] BYREF
  LPVOID pv; // [rsp+188h] [rbp+68h]
  __int64 v97; // [rsp+190h] [rbp+70h] BYREF
  __int64 v98; // [rsp+198h] [rbp+78h] BYREF
  __int64 v99; // [rsp+1A0h] [rbp+80h] BYREF
  _WORD *v100; // [rsp+1A8h] [rbp+88h] BYREF
  __int64 v101; // [rsp+1B0h] [rbp+90h] BYREF
  GUID Buf2; // [rsp+1B8h] [rbp+98h] BYREF
  __int128 v103; // [rsp+1C8h] [rbp+A8h] BYREF
  _QWORD v104[10]; // [rsp+1E0h] [rbp+C0h] BYREF
  _QWORD v105[10]; // [rsp+230h] [rbp+110h] BYREF
  _QWORD v106[10]; // [rsp+280h] [rbp+160h] BYREF
  _QWORD v107[10]; // [rsp+2D0h] [rbp+1B0h] BYREF
  _QWORD v108[10]; // [rsp+320h] [rbp+200h] BYREF
  _BYTE v109[12]; // [rsp+370h] [rbp+250h] BYREF
  OLECHAR sz[42]; // [rsp+37Ch] [rbp+25Ch] BYREF
  _WORD v111[256]; // [rsp+3D0h] [rbp+2B0h] BYREF
  _WORD v112[256]; // [rsp+5D0h] [rbp+4B0h] BYREF
  _WORD v113[256]; // [rsp+7D0h] [rbp+6B0h] BYREF
  _BYTE v114[512]; // [rsp+9D0h] [rbp+8B0h] BYREF
  _BYTE v115[512]; // [rsp+BD0h] [rbp+AB0h] BYREF
  _BYTE v116[512]; // [rsp+DD0h] [rbp+CB0h] BYREF
  _BYTE v117[512]; // [rsp+FD0h] [rbp+EB0h] BYREF

  v2 = 0;
  v91 = 0;
  v52 = 0;
  v70 = 0;
  v95 = 0;
  v61 = 0;
  v71 = 0;
  v62 = 0;
  v72 = 0;
  v54 = 0;
  v59 = 0;
  v63 = 0;
  v81 = 0;
  v64 = 0;
  v73 = 0;
  v101 = 0;
  v97 = 0;
  v80 = 0;
  v98 = 0;
  pvarg = 0;
  v83 = 0;
  v82 = 0;
  v99 = 0;
  v100 = 0;
  v69 = 0;
  v94 = 0;
  v93 = 0;
  v103 = 0;
  v84 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v74 = 0;
  v85 = 0;
  v68 = 0;
  v86 = 0;
  v67 = 0;
  v112[0] = 0;
  v78 = 0;
  v113[0] = 0;
  v79 = 0;
  v75 = 0;
  v60 = 0;
  v76 = 0;
  v65 = 0;
  v55 = 0;
  v57 = 0;
  v56 = 0;
  v66 = 1;
  v77 = 0;
  if ( !*((_DWORD *)this + 6) )
    return 2147549183LL;
  pv = 0;
  v4 = 0;
  v5 = 0;
  v53 = 0;
  v6 = CoCreateInstance(&CLSID_ServicesMetaDataDispenser, 0, 1u, &IID_IMetaDataDispenser, &v91);
  if ( v6 < 0 )
    goto LABEL_224;
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, GUID *, __int64 **))(*(_QWORD *)v91 + 32LL))(
         v91,
         *((_QWORD *)this + 6),
         0,
         &IID_IMetaDataRegImport,
         &v52);
  if ( v6 < 0 )
    goto LABEL_224;
  v7 = v52;
  if ( v52 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 5) + 32LL))(*((_QWORD *)this + 5), 0);
    if ( v6 >= 0 )
    {
LABEL_8:
      if ( (*(int (__fastcall **)(__int64 *, __int64 *, _QWORD *, __int64, unsigned int *))(*v52 + 48))(
             v52,
             &v95,
             v104,
             10,
             &v70) >= 0 )
      {
        v9 = v70;
        if ( v70 )
        {
          for ( i = 0; ; ++i )
          {
            v58 = i;
            if ( i >= v9 )
              goto LABEL_8;
            v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _BYTE *, __int64, int *, _BYTE *, int, int *, __int128 *, unsigned __int64 *, int *, _QWORD, _QWORD))(*v52 + 168))(
                   v52,
                   v104[i],
                   v117,
                   255,
                   &v93,
                   v116,
                   255,
                   &v94,
                   &v103,
                   &v84,
                   &v85,
                   0,
                   0);
            if ( v6 < 0 )
              goto LABEL_224;
            if ( (v85 & 0x200) == 0 )
            {
              v11 = (_QWORD *)*((_QWORD *)this + 9);
              if ( !v11 )
                goto LABEL_18;
              v12 = v103 - *v11;
              if ( (_QWORD)v103 == *v11 )
                v12 = *((_QWORD *)&v103 + 1) - v11[1];
              if ( !v12 )
              {
LABEL_18:
                LODWORD(v51) = 0;
                LODWORD(v49) = 255;
                v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _BYTE *, __int64, int *, _BYTE *, __int64, int *, _QWORD, __int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))(*v52 + 224))(
                       v52,
                       v104[i],
                       v114,
                       255,
                       &v68,
                       v115,
                       v49,
                       &v86,
                       0,
                       v51,
                       0,
                       0,
                       0,
                       0,
                       0,
                       0,
                       0,
                       0,
                       0);
                if ( v6 < 0 )
                  goto LABEL_224;
                v13 = *(_QWORD *)&tidCOMSERVICES_CLASSES.Data1 - *((_QWORD *)this + 7);
                if ( *(_QWORD *)&tidCOMSERVICES_CLASSES.Data1 == *((_QWORD *)this + 7) )
                  v13 = *(_QWORD *)tidCOMSERVICES_CLASSES.Data4 - *((_QWORD *)this + 8);
                if ( !v13 )
                {
                  v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 120LL))(*((_QWORD *)this + 4));
                  if ( v6 < 0 )
                    goto LABEL_224;
                  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int128 *))(**((_QWORD **)this + 4) + 160LL))(
                         *((_QWORD *)this + 4),
                         0,
                         0,
                         &v103);
                  if ( v6 < 0 )
                    goto LABEL_224;
                  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 160LL))(
                         *((_QWORD *)this + 4),
                         1,
                         0,
                         *((_QWORD *)this + 6));
                  if ( v6 < 0 )
                    goto LABEL_224;
                  if ( v68 )
                  {
                    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _BYTE *))(**((_QWORD **)this + 4) + 160LL))(
                           *((_QWORD *)this + 4),
                           3,
                           0,
                           v114);
                    if ( v6 < 0 )
                      goto LABEL_224;
                  }
                  if ( v86 )
                  {
                    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _BYTE *))(**((_QWORD **)this + 4) + 160LL))(
                           *((_QWORD *)this + 4),
                           5,
                           0,
                           v115);
                    if ( v6 < 0 )
                      goto LABEL_224;
                  }
                  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _BYTE *))(**((_QWORD **)this + 4) + 160LL))(
                         *((_QWORD *)this + 4),
                         4,
                         0,
                         v116);
                  if ( v6 < 0 )
                    goto LABEL_224;
                  v87 = HIWORD(v84);
                  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 4) + 160LL))(
                         *((_QWORD *)this + 4),
                         11,
                         0,
                         &v87);
                  if ( v6 < 0 )
                    goto LABEL_224;
                  v88 = WORD2(v84);
                  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 4) + 160LL))(
                         *((_QWORD *)this + 4),
                         12,
                         0,
                         &v88);
                  if ( v6 < 0 )
                    goto LABEL_224;
                  v89 = WORD1(v84);
                  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 4) + 160LL))(
                         *((_QWORD *)this + 4),
                         13,
                         0,
                         &v89);
                  if ( v6 < 0 )
                    goto LABEL_224;
                  v74 = (unsigned __int16)v84;
                  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 4) + 160LL))(
                         *((_QWORD *)this + 4),
                         14,
                         0,
                         &v74);
                  if ( v6 < 0 )
                    goto LABEL_224;
                  v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, int *, int *, int *, int *))(*v52 + 176))(
                         v52,
                         v104[i],
                         &v65,
                         &v75,
                         &v60,
                         &v76);
                  if ( v6 < 0 )
                    goto LABEL_224;
                  if ( (v75 & 1) != 0 )
                  {
                    v55 = 2;
                  }
                  else if ( (v75 & 2) != 0 )
                  {
                    v55 = 0;
                  }
                  else if ( (v75 & 4) != 0 )
                  {
                    v55 = 1;
                  }
                  else if ( (v75 & 8) != 0 )
                  {
                    v55 = 4;
                  }
                  else
                  {
                    v55 = (v75 & 0x10) != 0 ? 3 : 5;
                  }
                  if ( (v75 & 0x16) == 0x16 )
                    v55 = 3;
                  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 4) + 160LL))(
                         *((_QWORD *)this + 4),
                         2,
                         0,
                         &v55);
                  if ( v6 < 0 )
                    goto LABEL_224;
                  if ( (v76 & 1) != 0 )
                  {
                    v56 = 2;
                  }
                  else if ( (v76 & 2) != 0 )
                  {
                    v56 = 3;
                  }
                  else
                  {
                    v56 = (v76 & 4) != 0 ? 4 : ((unsigned __int8)v76 >> 3) & 1;
                  }
                  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 4) + 160LL))(
                         *((_QWORD *)this + 4),
                         18,
                         0,
                         &v56);
                  if ( v6 < 0 )
                    goto LABEL_224;
                  if ( (v60 & 1) != 0 )
                  {
                    v57 = 2;
                  }
                  else if ( (v60 & 2) != 0 )
                  {
                    v57 = 3;
                  }
                  else
                  {
                    v57 = (v60 & 4) != 0 ? 4 : ((unsigned __int8)v60 >> 3) & 1;
                  }
                  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 4) + 160LL))(
                         *((_QWORD *)this + 4),
                         17,
                         0,
                         &v57);
                  if ( v6 < 0 )
                    goto LABEL_224;
                  if ( (v60 & 7) != 0 && (v60 & 0x10) != 0 )
                  {
                    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 4) + 160LL))(
                           *((_QWORD *)this + 4),
                           32,
                           0,
                           &v66);
                    if ( v6 < 0 )
                      goto LABEL_224;
                  }
                  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 4) + 160LL))(
                         *((_QWORD *)this + 4),
                         30,
                         0,
                         &v65);
                  if ( v6 < 0 )
                    goto LABEL_224;
                  v14 = *((_QWORD *)this + 4);
                  if ( (v65 & 0xC000) == 0x8000 )
                  {
                    v15 = &v66;
                    goto LABEL_73;
                  }
                  if ( (v65 & 0xC000) != 0 )
                  {
                    v15 = &v77;
LABEL_73:
                    v16 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL);
                  }
                  else
                  {
                    v16 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v14 + 160LL);
                    if ( (unsigned int)(v56 - 3) <= 1 )
                      v15 = &v66;
                    else
                      v15 = &v77;
                  }
                  v6 = v16(v14, 22, 0, v15);
                  if ( v6 < 0 )
                    goto LABEL_224;
                  v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 144LL))(*((_QWORD *)this + 4));
                  if ( v6 < 0 )
                    goto LABEL_224;
                  goto LABEL_100;
                }
                v17 = tidCOMCLASSIC_FILEEXT - *((_QWORD *)this + 7);
                if ( tidCOMCLASSIC_FILEEXT == *((_QWORD *)this + 7) )
                  v17 = 0x24A9D74FC000938BLL - *((_QWORD *)this + 8);
                if ( !v17 )
                {
                  v61 = 0;
                  v71 = 0;
                  while ( 1 )
                  {
                    LODWORD(ppv) = 10;
                    if ( (*(int (__fastcall **)(__int64 *, __int64 *, _QWORD, _QWORD *, LPVOID *, unsigned int *))(*v52 + 112))(
                           v52,
                           &v71,
                           v104[i],
                           v107,
                           ppv,
                           &v61) < 0 )
                      break;
                    v18 = v61;
                    if ( !v61 )
                      break;
                    for ( j = 0; j < v18; ++j )
                    {
                      v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, _QWORD, int *))(*v52 + 272))(
                             v52,
                             v107[j],
                             0,
                             0,
                             0,
                             &v67);
                      if ( v6 < 0 )
                        goto LABEL_223;
                      if ( (v67 & 5) != 0 )
                      {
                        v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _WORD *, __int64, int *, int *))(*v52 + 272))(
                               v52,
                               v107[j],
                               v112,
                               255,
                               &v78,
                               &v67);
                        if ( v6 < 0 )
                          goto LABEL_223;
                        if ( v78 && v112[0] )
                        {
                          v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 120LL))(*((_QWORD *)this + 4));
                          if ( v6 < 0 )
                            goto LABEL_223;
                          v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _WORD *))(**((_QWORD **)this + 4)
                                                                                          + 160LL))(
                                 *((_QWORD *)this + 4),
                                 0,
                                 0,
                                 v112);
                          if ( v6 < 0 )
                            goto LABEL_223;
                          if ( v68 )
                          {
                            v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _BYTE *))(**((_QWORD **)this + 4)
                                                                                             + 160LL))(
                                   *((_QWORD *)this + 4),
                                   1,
                                   0,
                                   v114);
                            if ( v6 < 0 )
                              goto LABEL_223;
                          }
                          v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 144LL))(*((_QWORD *)this + 4));
                          if ( v6 < 0 )
                            goto LABEL_223;
                        }
                      }
                      v18 = v61;
                    }
                  }
                  if ( v71 )
                  {
                    (*(void (__fastcall **)(__int64 *))(*v52 + 24))(v52);
                    v71 = 0;
                  }
                  v5 = v53;
                  goto LABEL_99;
                }
                v20 = tidCOMCLASSIC_MIMETYPE - *((_QWORD *)this + 7);
                if ( tidCOMCLASSIC_MIMETYPE == *((_QWORD *)this + 7) )
                  v20 = 0x24A9D74FC000938BLL - *((_QWORD *)this + 8);
                if ( !v20 )
                {
                  v62 = 0;
                  v72 = 0;
                  while ( 1 )
                  {
                    LODWORD(ppv) = 10;
                    if ( (*(int (__fastcall **)(__int64 *, __int64 *, _QWORD, _QWORD *, LPVOID *, unsigned int *))(*v52 + 104))(
                           v52,
                           &v72,
                           v104[i],
                           v108,
                           ppv,
                           &v62) < 0 )
                      break;
                    v21 = v62;
                    if ( !v62 )
                      break;
                    for ( k = 0; k < v21; ++k )
                    {
                      v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _WORD *, __int64, int *))(*v52 + 264))(
                             v52,
                             v108[k],
                             v113,
                             255,
                             &v79);
                      if ( v6 < 0 )
                        goto LABEL_223;
                      if ( v79 )
                      {
                        if ( v113[0] )
                        {
                          v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 120LL))(*((_QWORD *)this + 4));
                          if ( v6 < 0 )
                            goto LABEL_223;
                          v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _WORD *))(**((_QWORD **)this + 4)
                                                                                          + 160LL))(
                                 *((_QWORD *)this + 4),
                                 0,
                                 0,
                                 v113);
                          if ( v6 < 0 )
                            goto LABEL_223;
                          v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int128 *))(**((_QWORD **)this + 4)
                                                                                              + 160LL))(
                                 *((_QWORD *)this + 4),
                                 1,
                                 0,
                                 &v103);
                          if ( v6 < 0 )
                            goto LABEL_223;
                          v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 144LL))(*((_QWORD *)this + 4));
                          if ( v6 < 0 )
                            goto LABEL_223;
                        }
                      }
                      v21 = v62;
                    }
                  }
                  if ( v72 )
                  {
                    (*(void (__fastcall **)(__int64 *))(*v52 + 24))(v52);
                    v72 = 0;
                  }
LABEL_136:
                  v5 = v53;
                  goto LABEL_100;
                }
                v23 = tidAPPDU_CLASSROLES - *((_QWORD *)this + 7);
                if ( tidAPPDU_CLASSROLES == *((_QWORD *)this + 7) )
                  v23 = 0x24A9D74FC000938BLL - *((_QWORD *)this + 8);
                if ( !v23 )
                {
                  v54 = 0;
                  v59 = 0;
                  while ( 1 )
                  {
                    LODWORD(ppv) = 10;
                    if ( (*(int (__fastcall **)(__int64 *, __int64 *, _QWORD, _QWORD *, LPVOID *, unsigned int *))(*v52 + 120))(
                           v52,
                           &v59,
                           v104[i],
                           v106,
                           ppv,
                           &v54) < 0 )
                      break;
                    v24 = v54;
                    if ( !v54 )
                      break;
                    for ( m = 0; m < v24; ++m )
                    {
                      v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _WORD *, __int64, int *, int *))(*v52 + 280))(
                             v52,
                             v106[m],
                             v111,
                             255,
                             &v63,
                             &v81);
                      if ( v6 < 0
                        || v63
                        && v111[0]
                        && ((v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 120LL))(*((_QWORD *)this + 4)),
                             v6 < 0)
                         || (v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _WORD *))(**((_QWORD **)this + 4)
                                                                                             + 160LL))(
                                    *((_QWORD *)this + 4),
                                    0,
                                    0,
                                    v111),
                             v6 < 0)
                         || (v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 144LL))(*((_QWORD *)this + 4)),
                             v6 < 0)) )
                      {
LABEL_223:
                        v5 = v53;
                        goto LABEL_224;
                      }
                      v24 = v54;
                    }
                  }
                  if ( v59 )
                  {
                    (*(void (__fastcall **)(__int64 *))(*v52 + 24))(v52);
                    v59 = 0;
                  }
                  goto LABEL_136;
                }
                v26 = tidAPPDU_INTERFACEROLES - *((_QWORD *)this + 7);
                if ( tidAPPDU_INTERFACEROLES == *((_QWORD *)this + 7) )
                  v26 = 0x24A9D74FC000938BLL - *((_QWORD *)this + 8);
                if ( !v26 )
                  goto LABEL_146;
                v27 = tidAPPDU_INTERFACEPROP - *((_QWORD *)this + 7);
                if ( tidAPPDU_INTERFACEPROP == *((_QWORD *)this + 7) )
                  v27 = 0x24A9D74FC0009A8BLL - *((_QWORD *)this + 8);
                if ( !v27 )
                  goto LABEL_146;
                v28 = tidAPPDU_METHOD - *((_QWORD *)this + 7);
                if ( tidAPPDU_METHOD == *((_QWORD *)this + 7) )
                  v28 = 0x24A9D74FC000938BLL - *((_QWORD *)this + 8);
                if ( !v28 )
                {
LABEL_146:
                  Buf2 = 0;
                  v92 = 0;
                  v64 = 0;
                  v73 = 0;
                  while ( 2 )
                  {
                    LODWORD(ppv) = 10;
                    if ( (*(int (__fastcall **)(__int64 *, __int64 *, _QWORD, _QWORD *, LPVOID *, unsigned int *))(*v52 + 56))(
                           v52,
                           &v73,
                           v104[i],
                           v105,
                           ppv,
                           &v64) < 0
                      || (v29 = v64) == 0 )
                    {
                      if ( v73 )
                      {
                        (*(void (__fastcall **)(__int64 *))(*v52 + 24))(v52);
                        v73 = 0;
                      }
LABEL_99:
                      i = v58;
                      goto LABEL_100;
                    }
LABEL_149:
                    if ( v2 >= v29 )
                    {
                      v2 = 0;
                      continue;
                    }
                    break;
                  }
                  v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *, __int64 *, int *))(*v52 + 184))(
                         v52,
                         v105[v2],
                         &v101,
                         &v97,
                         &v80);
                  v8 = 0;
                  if ( v6 < 0 )
                    goto LABEL_225;
                  if ( v80 )
                    goto LABEL_183;
                  v30 = *v52;
                  if ( (v97 & 0xFF000000) != 0 )
                  {
                    if ( (*(int (__fastcall **)(__int64 *, __int64, _BYTE *, __int64, int *, GUID *, _QWORD))(v30 + 208))(
                           v52,
                           v97,
                           v109,
                           45,
                           &v92,
                           &Buf2,
                           0) >= 0
                      && (memcmp_0(&GUID_NULL, &Buf2, 0x10u) || IIDFromString(sz, &Buf2) >= 0) )
                    {
                      goto LABEL_158;
                    }
                    goto LABEL_183;
                  }
                  LODWORD(v50) = 0;
                  v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD, _QWORD, _QWORD, _QWORD, __int64, _QWORD, GUID *, _QWORD, _QWORD, _QWORD, _QWORD))(v30 + 168))(
                         v52,
                         v97,
                         0,
                         0,
                         0,
                         0,
                         v50,
                         0,
                         &Buf2,
                         0,
                         0,
                         0,
                         0);
                  v8 = 0;
                  if ( v6 < 0 )
                    goto LABEL_225;
LABEL_158:
                  v31 = (_QWORD *)*((_QWORD *)this + 10);
                  if ( v31 )
                  {
                    v32 = *v31 - *(_QWORD *)&Buf2.Data1;
                    if ( *v31 == *(_QWORD *)&Buf2.Data1 )
                      v32 = v31[1] - *(_QWORD *)Buf2.Data4;
                    if ( v32 )
                      goto LABEL_183;
                  }
                  v33 = tidAPPDU_INTERFACEPROP - *((_QWORD *)this + 7);
                  if ( tidAPPDU_INTERFACEPROP == *((_QWORD *)this + 7) )
                    v33 = 0x24A9D74FC0009A8BLL - *((_QWORD *)this + 8);
                  if ( !v33 )
                  {
LABEL_183:
                    ++v2;
                    v29 = v64;
                    goto LABEL_149;
                  }
                  v34 = tidAPPDU_INTERFACEROLES - *((_QWORD *)this + 7);
                  if ( tidAPPDU_INTERFACEROLES == *((_QWORD *)this + 7) )
                    v34 = 0x24A9D74FC000938BLL - *((_QWORD *)this + 8);
                  if ( !v34 )
                  {
                    v54 = 0;
                    v59 = 0;
                    while ( 1 )
                    {
                      LODWORD(ppv) = 10;
                      if ( (*(int (__fastcall **)(__int64 *, __int64 *, _QWORD, _QWORD *, LPVOID *, unsigned int *))(*v52 + 120))(
                             v52,
                             &v59,
                             v105[v2],
                             v106,
                             ppv,
                             &v54) < 0 )
                        break;
                      v35 = v54;
                      if ( !v54 )
                        break;
                      for ( n = 0; n < v35; ++n )
                      {
                        v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _WORD *, __int64, int *, int *))(*v52 + 280))(
                               v52,
                               v106[n],
                               v111,
                               255,
                               &v63,
                               &v81);
                        v8 = 0;
                        if ( v6 < 0
                          || v63
                          && v111[0]
                          && ((v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 120LL))(*((_QWORD *)this + 4)),
                               v8 = 0,
                               v6 < 0)
                           || (v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _WORD *))(**((_QWORD **)this + 4)
                                                                                               + 160LL))(
                                      *((_QWORD *)this + 4),
                                      0,
                                      0,
                                      v111),
                               v8 = 0,
                               v6 < 0)
                           || (v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 144LL))(*((_QWORD *)this + 4)),
                               v8 = 0,
                               v6 < 0)) )
                        {
                          v5 = v53;
                          goto LABEL_225;
                        }
                        v35 = v54;
                      }
                    }
                    if ( v59 )
                    {
                      (*(void (__fastcall **)(__int64 *))(*v52 + 24))(v52);
                      v59 = 0;
                    }
                    v5 = v53;
                    goto LABEL_183;
                  }
                  v69 = 0;
                  v37 = (unsigned int)safe_lstrlenW(*((const unsigned __int16 **)this + 11)) + 14;
                  v38 = CoTaskMemAlloc(saturated_mul(v37, 2u));
                  pv = v38;
                  v8 = 0;
                  if ( !v38 )
                    goto LABEL_218;
                  v6 = StringCchPrintfW(
                         (unsigned __int16 *)v38,
                         (unsigned int)v37,
                         L"Allow_Access_%s",
                         *((_QWORD *)this + 11));
                  v8 = 0;
                  if ( v6 < 0 )
                    goto LABEL_225;
                  v39 = (unsigned int)safe_lstrlenW(*((const unsigned __int16 **)this + 11)) + 11;
                  v41 = v39 * (unsigned int)(v40 + 2);
                  if ( !is_mul_ok(v39, (unsigned int)(v40 + 2)) )
                    v41 = v40 - 1;
                  v42 = (unsigned __int16 *)CoTaskMemAlloc(v41);
                  v5 = v42;
                  v53 = v42;
                  v8 = 0;
                  if ( !v42 )
                  {
LABEL_218:
                    v6 = -2147024882;
                    goto LABEL_225;
                  }
                  v6 = StringCchPrintfW(v42, (unsigned int)v39, L"Auto_Done_%s", *((_QWORD *)this + 11));
                  v8 = 0;
                  if ( v6 < 0 )
                    goto LABEL_225;
                  v43 = 0;
                  if ( !(*(unsigned int (__fastcall **)(__int64 *, _QWORD, LPVOID, __int64 *, int *))(*v52 + 144))(
                          v52,
                          v105[v2],
                          pv,
                          &v98,
                          &v82) )
                  {
                    v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, VARIANTARG **, int *))(*v52 + 200))(
                           v52,
                           v98,
                           &pvarg,
                           &v83);
                    v8 = 0;
                    if ( v6 < 0 )
                      goto LABEL_225;
                    if ( pvarg && pvarg->vt == 8 )
                    {
                      v44 = safe_lstrlenW(pvarg->bstrVal) + 1;
                      v46 = v44 * (unsigned __int64)(unsigned int)(v45 + 2);
                      if ( !is_mul_ok(v44, (unsigned int)(v45 + 2)) )
                        v46 = v45 - 1;
                      v47 = (unsigned __int16 *)CoTaskMemAlloc(v46);
                      v4 = v47;
                      v8 = 0;
                      if ( !v47 )
                        goto LABEL_218;
                      v6 = StringCchCopyW(v47, v44, pvarg->bstrVal);
                      if ( v6 < 0 )
                        goto LABEL_225;
                      if ( v8 != pvarg->vt )
                        VariantClear(pvarg);
                    }
                    v43 = 1;
                  }
                  if ( !(*(unsigned int (__fastcall **)(__int64 *, _QWORD, unsigned __int16 *, __int64 *, int *))(*v52 + 144))(
                          v52,
                          v105[v2],
                          v5,
                          &v99,
                          &v82) )
                  {
                    v6 = (*(__int64 (__fastcall **)(__int64 *, __int64, _WORD **, int *))(*v52 + 200))(
                           v52,
                           v99,
                           &v100,
                           &v83);
                    v8 = 0;
                    if ( v6 < 0 )
                      goto LABEL_225;
                    if ( v100 && !*v100 )
                      v69 = 1;
                    goto LABEL_207;
                  }
                  if ( v43 )
                  {
LABEL_207:
                    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 120LL))(*((_QWORD *)this + 4));
                    v8 = 0;
                    if ( v6 < 0 )
                      goto LABEL_225;
                    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 160LL))(
                           *((_QWORD *)this + 4),
                           0,
                           0,
                           *((_QWORD *)this + 11));
                    v8 = 0;
                    if ( v6 < 0 )
                      goto LABEL_225;
                    if ( v4 )
                    {
                      v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 4)
                                                                                                  + 160LL))(
                             *((_QWORD *)this + 4),
                             1,
                             0,
                             v4);
                      v8 = 0;
                      if ( v6 < 0 )
                        goto LABEL_225;
                    }
                    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, int *))(**((_QWORD **)this + 4) + 160LL))(
                           *((_QWORD *)this + 4),
                           2,
                           0,
                           &v69);
                    v8 = 0;
                    if ( v6 < 0 )
                      goto LABEL_225;
                    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 144LL))(*((_QWORD *)this + 4));
                    v8 = 0;
                    if ( v6 < 0 )
                      goto LABEL_225;
                  }
                  if ( v4 )
                  {
                    CoTaskMemFree(v4);
                    v4 = 0;
                  }
                  goto LABEL_183;
                }
              }
            }
LABEL_100:
            v9 = v70;
          }
        }
      }
      v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 40LL))(*((_QWORD *)this + 5));
      if ( v6 >= 0 )
        v6 = 0;
    }
LABEL_224:
    v8 = 0;
LABEL_225:
    v7 = v52;
    goto LABEL_226;
  }
  v6 = -2147418113;
  v8 = 0;
LABEL_226:
  if ( v71 )
  {
    (*(void (__fastcall **)(__int64 *))(*v7 + 24))(v7);
    v8 = 0;
    v71 = 0;
    v7 = v52;
  }
  if ( v72 )
  {
    (*(void (__fastcall **)(__int64 *))(*v7 + 24))(v7);
    v8 = 0;
    v72 = 0;
    v7 = v52;
  }
  if ( v59 )
  {
    (*(void (__fastcall **)(__int64 *))(*v7 + 24))(v7);
    v8 = 0;
    v59 = 0;
    v7 = v52;
  }
  if ( v73 )
  {
    (*(void (__fastcall **)(__int64 *))(*v7 + 24))(v7);
    v8 = 0;
    v73 = 0;
    v7 = v52;
  }
  if ( v95 )
  {
    (*(void (__fastcall **)(__int64 *))(*v7 + 24))(v7);
    v8 = 0;
    v95 = 0;
    v7 = v52;
  }
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64 *))(*v7 + 16))(v7);
    v8 = 0;
    v52 = 0;
  }
  if ( v91 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v91 + 16LL))(v91);
    v8 = 0;
    v91 = 0;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    v8 = 0;
  }
  if ( pvarg && v8 != pvarg->vt )
    VariantClear(pvarg);
  if ( v4 )
    CoTaskMemFree(v4);
  if ( v5 )
    CoTaskMemFree(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180040470  push    rbp
0x180040472  push    rbx
0x180040473  push    rsi
0x180040474  push    rdi
0x180040475  push    r12
0x180040477  push    r13
0x180040479  push    r14
0x18004047b  push    r15
0x18004047d  lea     rbp, [rsp-10C8h]
0x180040485  mov     eax, 11E8h
0x18004048a  call    _alloca_probe
0x18004048f  sub     rsp, rax
0x180040492  mov     rax, cs:__security_cookie
0x180040499  xor     rax, rsp
0x18004049c  mov     [rbp+1100h+var_50], rax
0x1800404a3  mov     rdi, rcx
0x1800404a6  xor     r15d, r15d
0x1800404a9  mov     [rbp+1100h+var_10B8], r15
0x1800404ad  mov     [rbp+1100h+var_1180], r15
0x1800404b1  mov     [rbp+1100h+var_1128], r15d
0x1800404b5  mov     [rbp+1100h+var_10A0], r15
0x1800404b9  mov     [rbp+1100h+var_114C], r15d
0x1800404bd  mov     [rbp+1100h+var_1120], r15
0x1800404c1  mov     [rbp+1100h+var_1148], r15d
0x1800404c5  mov     [rbp+1100h+var_1118], r15
0x1800404c9  mov     [rbp+1100h+var_1170], r15d
0x1800404cd  mov     [rbp+1100h+var_1158], r15
0x1800404d1  mov     [rbp+1100h+var_1144], r15d
0x1800404d5  mov     [rbp+1100h+var_10EC], r15d
0x1800404d9  mov     [rbp+1100h+var_1140], r15d
0x1800404dd  mov     [rbp+1100h+var_1110], r15
0x1800404e1  mov     [rbp+1100h+var_1070], r15
0x1800404e8  mov     [rbp+1100h+var_1090], r15
0x1800404ec  mov     [rbp+1100h+var_10F0], r15d
0x1800404f0  mov     [rbp+1100h+var_1088], r15
0x1800404f4  mov     [rbp+1100h+pvarg], r15
0x1800404f8  mov     [rbp+1100h+var_10E4], r15d
0x1800404fc  mov     [rbp+1100h+var_10E8], r15d
0x180040500  mov     [rbp+1100h+var_1080], r15
0x180040507  mov     [rbp+1100h+var_1078], r15
0x18004050e  mov     [rbp+1100h+var_112C], r15d
0x180040512  mov     [rbp+1100h+var_10A8], r15d
0x180040516  mov     [rbp+1100h+var_10AC], r15d
0x18004051a  xorps   xmm0, xmm0
0x18004051d  movups  [rbp+1100h+var_1058], xmm0
0x180040524  mov     [rbp+1100h+var_10E0], r15
0x180040528  mov     [rbp+1100h+var_10D0], r15d
0x18004052c  mov     [rbp+1100h+var_10CC], r15d
0x180040530  mov     [rbp+1100h+var_10C8], r15d
0x180040534  mov     [rbp+1100h+var_1108], r15d
0x180040538  mov     [rbp+1100h+var_10D8], r15d
0x18004053c  mov     [rbp+1100h+var_1130], r15d
0x180040540  mov     [rbp+1100h+var_10D4], r15d
0x180040544  mov     [rbp+1100h+var_1134], r15d
0x180040548  mov     [rbp+1100h+var_C50], r15w
0x180040550  mov     [rbp+1100h+var_10F8], r15d
0x180040554  mov     [rbp+1100h+var_A50], r15w
0x18004055c  mov     [rbp+1100h+var_10F4], r15d
0x180040560  mov     [rbp+1100h+var_1104], r15d
0x180040564  mov     [rbp+1100h+var_1150], r15d
0x180040568  mov     [rbp+1100h+var_1100], r15d
0x18004056c  mov     [rbp+1100h+var_113C], r15d
0x180040570  mov     [rbp+1100h+var_116C], r15d
0x180040574  mov     [rbp+1100h+var_1164], r15d
0x180040578  mov     [rbp+1100h+var_1168], r15d
0x18004057c  lea     ecx, [r15+1]
0x180040580  mov     [rbp+1100h+var_1138], ecx
0x180040583  mov     [rbp+1100h+var_10FC], r15d
0x180040587  cmp     [rdi+18h], r15d
0x18004058b  jnz     short loc_180040597
0x18004058d  mov     eax, 8000FFFFh
0x180040592  jmp     loc_1800418F2
0x180040597  mov     [rbp+1100h+pv], r15
0x18004059b  mov     r13, r15
0x18004059e  mov     rsi, r15
0x1800405a1  mov     [rbp+1100h+var_1178], r15
0x1800405a5  lea     rax, [rbp+1100h+var_10B8]
0x1800405a9  mov     [rsp+1220h+ppv], rax; ppv
0x1800405ae  lea     r9, IID_IMetaDataDispenser; riid
0x1800405b5  mov     r8d, ecx; dwClsContext
0x1800405b8  xor     edx, edx; pUnkOuter
0x1800405ba  lea     rcx, ?CLSID_ServicesMetaDataDispenser@@3U_GUID@@B; rclsid
0x1800405c1  call    cs:__imp_CoCreateInstance
0x1800405c7  mov     ebx, eax
0x1800405c9  test    eax, eax
0x1800405cb  js      loc_1800417CC
0x1800405d1  mov     rcx, [rbp+1100h+var_10B8]
0x1800405d5  mov     rax, [rcx]
0x1800405d8  lea     rdx, [rbp+1100h+var_1180]
0x1800405dc  mov     [rsp+1220h+ppv], rdx
0x1800405e1  lea     r9, IID_IMetaDataRegImport
0x1800405e8  xor     r8d, r8d
0x1800405eb  mov     rdx, [rdi+30h]
0x1800405ef  mov     rax, [rax+20h]
0x1800405f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800405f8  mov     ebx, eax
0x1800405fa  test    eax, eax
0x1800405fc  js      loc_1800417CC
0x180040602  mov     rcx, [rbp+1100h+var_1180]
0x180040606  test    rcx, rcx
0x180040609  jnz     short loc_180040618
0x18004060b  mov     ebx, 8000FFFFh
0x180040610  xor     r10d, r10d
0x180040613  jmp     loc_1800417D3
0x180040618  mov     rcx, [rdi+28h]
0x18004061c  mov     rax, [rcx]
0x18004061f  xor     edx, edx
0x180040621  mov     rax, [rax+20h]
0x180040625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004062a  mov     ebx, eax
0x18004062c  test    eax, eax
0x18004062e  js      loc_1800417CC
0x180040634  mov     rcx, [rbp+1100h+var_1180]
0x180040638  mov     rax, [rcx]
0x18004063b  lea     rdx, [rbp+1100h+var_1128]
0x18004063f  mov     [rsp+1220h+ppv], rdx
0x180040644  mov     r9d, 0Ah
0x18004064a  lea     r8, [rbp+1100h+var_1040]
0x180040651  lea     rdx, [rbp+1100h+var_10A0]
0x180040655  mov     rax, [rax+30h]
0x180040659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004065e  test    eax, eax
0x180040660  js      loc_1800417A8
0x180040666  mov     eax, [rbp+1100h+var_1128]
0x180040669  test    eax, eax
0x18004066b  jz      loc_1800417A8
0x180040671  mov     r14d, r15d
0x180040674  mov     [rbp+1100h+var_1160], r14d
0x180040678  cmp     r14d, eax
0x18004067b  jnb     short loc_180040634
0x18004067d  mov     r12d, r14d
0x180040680  mov     rcx, [rbp+1100h+var_1180]
0x180040684  mov     rax, [rcx]
0x180040687  mov     [rsp+1220h+var_11C0], r15
0x18004068c  mov     [rsp+1220h+var_11C8], r15
0x180040691  lea     rdx, [rbp+1100h+var_10D8]
0x180040695  mov     [rsp+1220h+var_11D0], rdx
0x18004069a  lea     rdx, [rbp+1100h+var_10E0]
0x18004069e  mov     [rsp+1220h+var_11D8], rdx
0x1800406a3  lea     rdx, [rbp+1100h+var_1058]
0x1800406aa  mov     [rsp+1220h+var_11E0], rdx
0x1800406af  lea     rdx, [rbp+1100h+var_10A8]
0x1800406b3  mov     [rsp+1220h+var_11E8], rdx
0x1800406b8  mov     dword ptr [rsp+1220h+var_11F0], 0FFh
0x1800406c0  lea     rdx, [rbp+1100h+var_450]
0x1800406c7  mov     [rsp+1220h+var_11F8], rdx
0x1800406cc  lea     rdx, [rbp+1100h+var_10AC]
0x1800406d0  mov     [rsp+1220h+ppv], rdx
0x1800406d5  mov     r9d, 0FFh
0x1800406db  lea     r8, [rbp+1100h+var_250]
0x1800406e2  mov     rdx, [rbp+r12*8+1100h+var_1040]
0x1800406ea  mov     rax, [rax+0A8h]
0x1800406f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406f6  mov     ebx, eax
0x1800406f8  test    eax, eax
0x1800406fa  js      loc_1800417CC
0x180040700  test    [rbp+1100h+var_10D8], 200h
0x180040707  jnz     loc_180040DF4
0x18004070d  mov     rcx, [rdi+48h]
0x180040711  test    rcx, rcx
0x180040714  jz      short loc_180040736
0x180040716  mov     rax, qword ptr [rbp+1100h+var_1058]
0x18004071d  sub     rax, [rcx]
0x180040720  jnz     short loc_18004072D
0x180040722  mov     rax, qword ptr [rbp+1100h+var_1058+8]
0x180040729  sub     rax, [rcx+8]
0x18004072d  test    rax, rax
0x180040730  jnz     loc_180040DF4
0x180040736  mov     rcx, [rbp+1100h+var_1180]
0x18004073a  mov     rax, [rcx]
0x18004073d  mov     [rsp+1220h+var_1190], r15
0x180040745  mov     [rsp+1220h+var_1198], r15d
0x18004074d  mov     [rsp+1220h+var_11A0], r15
0x180040755  mov     [rsp+1220h+var_11A8], r15
0x18004075a  mov     [rsp+1220h+var_11B0], r15
0x18004075f  mov     [rsp+1220h+var_11B8], r15d
0x180040764  mov     [rsp+1220h+var_11C0], r15
0x180040769  mov     [rsp+1220h+var_11C8], r15
0x18004076e  mov     [rsp+1220h+var_11D0], r15
0x180040773  mov     dword ptr [rsp+1220h+var_11D8], r15d
0x180040778  mov     [rsp+1220h+var_11E0], r15
0x18004077d  lea     rdx, [rbp+1100h+var_10D4]
0x180040781  mov     [rsp+1220h+var_11E8], rdx
0x180040786  mov     r8d, 0FFh
0x18004078c  mov     dword ptr [rsp+1220h+var_11F0], r8d
0x180040791  lea     rdx, [rbp+1100h+var_650]
0x180040798  mov     [rsp+1220h+var_11F8], rdx
0x18004079d  lea     rdx, [rbp+1100h+var_1130]
0x1800407a1  mov     [rsp+1220h+ppv], rdx
0x1800407a6  mov     r9d, r8d
0x1800407a9  lea     r8, [rbp+1100h+var_850]
0x1800407b0  mov     rdx, [rbp+r12*8+1100h+var_1040]
0x1800407b8  mov     rax, [rax+0E0h]
0x1800407bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407c4  mov     ebx, eax
0x1800407c6  test    eax, eax
0x1800407c8  js      loc_1800417CC
0x1800407ce  mov     rax, qword ptr cs:tidCOMSERVICES_CLASSES.Data1
0x1800407d5  sub     rax, [rdi+38h]
0x1800407d9  jnz     short loc_1800407E6
0x1800407db  mov     rax, qword ptr cs:tidCOMSERVICES_CLASSES.Data4
0x1800407e2  sub     rax, [rdi+40h]
0x1800407e6  test    rax, rax
0x1800407e9  jnz     loc_180040C1B
0x1800407ef  mov     rcx, [rdi+20h]
0x1800407f3  mov     rax, [rcx]
0x1800407f6  mov     rax, [rax+78h]
0x1800407fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800407ff  mov     ebx, eax
0x180040801  test    eax, eax
0x180040803  js      loc_1800417CC
0x180040809  mov     rcx, [rdi+20h]
0x18004080d  mov     rax, [rcx]
0x180040810  lea     r9, [rbp+1100h+var_1058]
0x180040817  xor     r8d, r8d
0x18004081a  xor     edx, edx
0x18004081c  mov     rax, [rax+0A0h]
0x180040823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040828  mov     ebx, eax
0x18004082a  test    eax, eax
0x18004082c  js      loc_1800417CC
0x180040832  mov     rcx, [rdi+20h]
0x180040836  mov     rax, [rcx]
0x180040839  mov     r9, [rdi+30h]
0x18004083d  xor     r8d, r8d
0x180040840  lea     edx, [r8+1]
0x180040844  mov     rax, [rax+0A0h]
0x18004084b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040850  mov     ebx, eax
0x180040852  test    eax, eax
0x180040854  js      loc_1800417CC
0x18004085a  cmp     [rbp+1100h+var_1130], r15d
0x18004085e  jz      short loc_18004088B
0x180040860  mov     rcx, [rdi+20h]
0x180040864  mov     rax, [rcx]
0x180040867  lea     r9, [rbp+1100h+var_850]
0x18004086e  xor     r8d, r8d
0x180040871  lea     edx, [r8+3]
0x180040875  mov     rax, [rax+0A0h]
0x18004087c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040881  mov     ebx, eax
0x180040883  test    eax, eax
0x180040885  js      loc_1800417CC
0x18004088b  cmp     [rbp+1100h+var_10D4], r15d
0x18004088f  jz      short loc_1800408BC
0x180040891  mov     rcx, [rdi+20h]
0x180040895  mov     rax, [rcx]
0x180040898  lea     r9, [rbp+1100h+var_650]
0x18004089f  xor     r8d, r8d
0x1800408a2  lea     edx, [r8+5]
0x1800408a6  mov     rax, [rax+0A0h]
0x1800408ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800408b2  mov     ebx, eax
0x1800408b4  test    eax, eax
0x1800408b6  js      loc_1800417CC
0x1800408bc  mov     rcx, [rdi+20h]
0x1800408c0  mov     rax, [rcx]
0x1800408c3  lea     r9, [rbp+1100h+var_450]
0x1800408ca  xor     r8d, r8d
0x1800408cd  lea     edx, [r8+4]
0x1800408d1  mov     rax, [rax+0A0h]
0x1800408d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800408dd  mov     ebx, eax
0x1800408df  test    eax, eax
0x1800408e1  js      loc_1800417CC
0x1800408e7  mov     rax, [rbp+1100h+var_10E0]
0x1800408eb  shr     rax, 30h
0x1800408ef  mov     [rbp+1100h+var_10D0], eax
0x1800408f2  mov     rcx, [rdi+20h]
0x1800408f6  mov     rax, [rcx]
0x1800408f9  lea     r9, [rbp+1100h+var_10D0]
0x1800408fd  xor     r8d, r8d
0x180040900  lea     edx, [r8+0Bh]
0x180040904  mov     rax, [rax+0A0h]
0x18004090b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040910  mov     ebx, eax
0x180040912  test    eax, eax
0x180040914  js      loc_1800417CC
0x18004091a  mov     rax, [rbp+1100h+var_10E0]
0x18004091e  shr     rax, 20h
0x180040922  movzx   eax, ax
0x180040925  mov     [rbp+1100h+var_10CC], eax
0x180040928  mov     rcx, [rdi+20h]
0x18004092c  mov     rax, [rcx]
0x18004092f  lea     r9, [rbp+1100h+var_10CC]
0x180040933  xor     r8d, r8d
0x180040936  lea     edx, [r8+0Ch]
0x18004093a  mov     rax, [rax+0A0h]
0x180040941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040946  mov     ebx, eax
0x180040948  test    eax, eax
0x18004094a  js      loc_1800417CC
0x180040950  mov     rax, [rbp+1100h+var_10E0]
0x180040954  shr     rax, 10h
0x180040958  movzx   eax, ax
0x18004095b  mov     [rbp+1100h+var_10C8], eax
0x18004095e  mov     rcx, [rdi+20h]
0x180040962  mov     rax, [rcx]
0x180040965  lea     r9, [rbp+1100h+var_10C8]
0x180040969  xor     r8d, r8d
  ... truncated ...
```
