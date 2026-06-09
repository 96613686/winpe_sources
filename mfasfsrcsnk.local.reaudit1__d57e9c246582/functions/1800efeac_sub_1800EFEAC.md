# sub_1800EFEAC

- ea: `0x1800efeac`
- end: `0x1800f0e4b`
- name: `sub_1800EFEAC`
- size: `3999`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180023ca8`

## callees

- `0x1800018b0`
- `0x180005d20`
- `0x18000ae10`
- `0x18003f940`
- `0x180051d3c`
- `0x180051e44`
- `0x1800620b4`
- `0x180083a48`
- `0x1800efeac`
- `0x180146950`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800effd0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800effd0`
- `MFPlat!MFCalculateImageSize` at `0x1800f094b`
- `MFPlat!MFCalculateImageSize` at `0x1800f094b`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800f0a07`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800f0a07`
- `MFPlat!MFCreateSample` at `0x1800f0ac2`
- `MFPlat!MFCreateSample` at `0x1800f0ac2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800efff2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f011e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f01df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f02a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f035d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0428`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f04ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f05ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0672`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0738`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f07f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f08b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f096d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0a29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0ae4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0b9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0c6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0d32`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800efff2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f011e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f01df`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f02a0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f035d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0428`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f04ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f05ae`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0672`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0738`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f07f7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f08b1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f096d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0a29`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0ae4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0b9d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0c6b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800f0d32`

## pseudocode

```c
__int64 __fastcall sub_1800EFEAC(__int64 a1, __int64 a2, __int64 a3, IMFSample **a4, _QWORD *a5)
{
  __int64 v9; // rdi
  int v10; // ebx
  __int128 v11; // xmm0
  __int64 v12; // rdx
  HRESULT v13; // ebx
  __int64 (__fastcall ***v14)(); // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  LPVOID v18; // rbx
  int (__fastcall *v19)(LPVOID, __int64 *, __int64 *); // rdi
  LPVOID v20; // rdi
  __int64 (__fastcall *v21)(LPVOID, __int64 *); // rbx
  __int64 v22; // rdx
  __int64 (__fastcall ***v23)(); // rcx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 (__fastcall ***v27)(); // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 (__fastcall ***v31)(); // rcx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 (__fastcall ***v35)(); // rcx
  __int64 v36; // rax
  __int64 v37; // rax
  LPVOID v38; // rdi
  __int64 (__fastcall *v39)(LPVOID, __int64 *, __int64 *); // rbx
  __int64 v40; // rdx
  __int64 (__fastcall ***v41)(); // rcx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdi
  __int64 (__fastcall *v45)(__int64, __int64 *); // rbx
  __int64 v46; // rdx
  __int64 (__fastcall ***v47)(); // rcx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 (__fastcall ***v51)(); // rcx
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 (__fastcall ***v55)(); // rcx
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 (__fastcall ***v59)(); // rcx
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 (__fastcall ***v63)(); // rcx
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 (__fastcall ***v67)(); // rcx
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rdx
  __int64 (__fastcall ***v71)(); // rcx
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rdx
  __int64 (__fastcall ***v75)(); // rcx
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rdx
  __int64 (__fastcall ***v79)(); // rcx
  __int64 v80; // rax
  __int64 v81; // rax
  __int64 v82; // rdx
  __int64 (__fastcall ***v83)(); // rcx
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // rdx
  __int64 (__fastcall ***v87)(); // rcx
  __int64 v88; // rax
  __int64 v89; // rax
  __int64 v90; // rdx
  __int64 (__fastcall ***v91)(); // rcx
  __int64 v92; // rax
  __int64 v93; // rax
  _BYTE v95[8]; // [rsp+30h] [rbp-A1h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-99h] BYREF
  __int64 v97; // [rsp+40h] [rbp-91h] BYREF
  IMFSample *ppIMFSample; // [rsp+48h] [rbp-89h] BYREF
  UINT32 unHeight; // [rsp+50h] [rbp-81h] BYREF
  UINT32 unWidth; // [rsp+54h] [rbp-7Dh] BYREF
  UINT32 pcbImageSize; // [rsp+58h] [rbp-79h] BYREF
  __int64 v102; // [rsp+60h] [rbp-71h] BYREF
  __int64 v103; // [rsp+68h] [rbp-69h] BYREF
  __int64 v104; // [rsp+70h] [rbp-61h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+78h] [rbp-59h] BYREF
  int v106; // [rsp+80h] [rbp-51h] BYREF
  __int64 v107; // [rsp+88h] [rbp-49h] BYREF
  __int128 v108; // [rsp+90h] [rbp-41h] BYREF
  __int128 v109; // [rsp+A0h] [rbp-31h]
  GUID guidSubtype; // [rsp+B0h] [rbp-21h] BYREF
  _BYTE v111[16]; // [rsp+C0h] [rbp-11h] BYREF

  ppBuffer = 0;
  v108 = 0;
  v109 = 0;
  ppIMFSample = 0;
  v107 = 0;
  guidSubtype = (GUID)xmmword_1801568F0;
  v97 = 0;
  pcbImageSize = 0;
  v106 = 0;
  ppv = 0;
  v104 = 0;
  v102 = 0;
  unWidth = 0;
  unHeight = 0;
  v103 = 0;
  sub_18000AE10(v95, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1574);
  if ( *(_BYTE *)(qword_180171350 + 8) && *(_QWORD *)(a1 + 400) )
  {
    v9 = sub_1800018B0(qword_180171350);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 400) + 296LL))(*(_QWORD *)(a1 + 400));
    v11 = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 400) + 280LL))(
                       *(_QWORD *)(a1 + 400),
                       v111);
    *(_DWORD *)(v9 + 2016) = v10;
    *(_OWORD *)(v9 + 2000) = v11;
  }
  sub_1800620B4(&ppv);
  v13 = CoCreateInstance(&stru_180159158, 0, 1u, &stru_1801626B8, &ppv);
  if ( v13 >= 0 )
  {
    v18 = ppv;
    v19 = **(int (__fastcall ***)(LPVOID, __int64 *, __int64 *))ppv;
    sub_1800620B4(&v103);
    if ( v19(v18, qword_180162678, &v103) >= 0 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v103 + 32LL))(v103, *(_QWORD *)(a1 + 400));
    v20 = ppv;
    v21 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 64LL);
    sub_1800620B4(&v102);
    v13 = v21(v20, &v102);
    if ( v13 >= 0 )
    {
      v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v102 + 168LL))(v102, qword_180158E90, 1);
      if ( v13 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v102 + 168LL))(
                v102,
                qword_1801626A8,
                1);
        if ( v13 >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, _QWORD))(*(_QWORD *)ppv + 120LL))(ppv, 0, a3, 0);
          if ( v13 >= 0 )
          {
            v38 = ppv;
            v39 = **(__int64 (__fastcall ***)(LPVOID, __int64 *, __int64 *))ppv;
            sub_1800620B4(&v104);
            v13 = v39(v38, qword_180162698, &v104);
            if ( v13 >= 0 )
            {
              v44 = v104;
              v45 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v104 + 96LL);
              sub_1800620B4(&v97);
              v13 = v45(v44, &v97);
              if ( v13 >= 0 )
              {
                v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, GUID *))(*(_QWORD *)v97 + 192LL))(
                        v97,
                        qword_180156A20,
                        &guidSubtype);
                if ( v13 >= 0 )
                {
                  v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v97 + 168LL))(
                          v97,
                          qword_180156B80,
                          1);
                  if ( v13 >= 0 )
                  {
                    v13 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v97 + 176LL))(
                            v97,
                            qword_180156B20,
                            0x100000001LL);
                    if ( v13 >= 0 )
                    {
                      v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, _QWORD))(*(_QWORD *)ppv + 128LL))(
                              ppv,
                              0,
                              v97,
                              0);
                      if ( v13 >= 0 )
                      {
                        v13 = sub_180051D3C(v97, qword_180156B00, &unWidth, &unHeight);
                        if ( v13 >= 0 )
                        {
                          v13 = MFCalculateImageSize(&guidSubtype, unWidth, unHeight, &pcbImageSize);
                          if ( v13 >= 0 )
                          {
                            sub_1800620B4(&ppBuffer);
                            v13 = MFCreateMemoryBuffer(pcbImageSize, &ppBuffer);
                            if ( v13 >= 0 )
                            {
                              sub_1800620B4(&ppIMFSample);
                              v13 = MFCreateSample(&ppIMFSample);
                              if ( v13 >= 0 )
                              {
                                v13 = ((__int64 (__fastcall *)(IMFSample *, IMFMediaBuffer *))ppIMFSample->lpVtbl->AddBuffer)(
                                        ppIMFSample,
                                        ppBuffer);
                                if ( v13 >= 0 )
                                {
                                  *((_QWORD *)&v108 + 1) = ppIMFSample;
                                  LODWORD(v109) = 0;
                                  LODWORD(v108) = 0;
                                  v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, _QWORD))(*(_QWORD *)ppv + 192LL))(
                                          ppv,
                                          0,
                                          a2,
                                          0);
                                  if ( v13 >= 0 )
                                  {
                                    v13 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, __int128 *, int *))(*(_QWORD *)ppv + 200LL))(
                                            ppv,
                                            0,
                                            1,
                                            &v108,
                                            &v106);
                                    if ( v13 >= 0 )
                                    {
                                      *a4 = ppIMFSample;
                                      *a5 = v97;
                                      ppIMFSample = 0;
                                      v97 = 0;
                                      goto LABEL_206;
                                    }
                                    v91 = (__int64 (__fastcall ***)())qword_180171350;
                                    if ( !qword_180171350 )
                                    {
                                      v92 = MFGetCallStackTracingWeakReference(0, v90);
                                      qword_180171350 = v92;
                                      if ( v92
                                        && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v92 + 8LL))(
                                             v92,
                                             2032) )
                                      {
                                        v91 = (__int64 (__fastcall ***)())qword_180171350;
                                      }
                                      else
                                      {
                                        v91 = &off_1801703B0;
                                        qword_180171350 = (__int64)&off_1801703B0;
                                      }
                                    }
                                    if ( *((_BYTE *)v91 + 8) )
                                    {
                                      v93 = sub_1800018B0(v91);
                                      if ( *(_DWORD *)(v93 + 1996) != v13 )
                                        sub_180083A48(
                                          v93,
                                          "CMFVideoThumbnail::ConvertYUVtoRGB32",
                                          1610,
                                          (unsigned int)v13);
                                    }
                                    if ( byte_1801712C8 )
                                    {
                                      v17 = 143;
                                      goto LABEL_15;
                                    }
                                  }
                                  else
                                  {
                                    v87 = (__int64 (__fastcall ***)())qword_180171350;
                                    if ( !qword_180171350 )
                                    {
                                      v88 = MFGetCallStackTracingWeakReference(0, v86);
                                      qword_180171350 = v88;
                                      if ( v88
                                        && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v88 + 8LL))(
                                             v88,
                                             2032) )
                                      {
                                        v87 = (__int64 (__fastcall ***)())qword_180171350;
                                      }
                                      else
                                      {
                                        v87 = &off_1801703B0;
                                        qword_180171350 = (__int64)&off_1801703B0;
                                      }
                                    }
                                    if ( *((_BYTE *)v87 + 8) )
                                    {
                                      v89 = sub_1800018B0(v87);
                                      if ( *(_DWORD *)(v89 + 1996) != v13 )
                                        sub_180083A48(
                                          v89,
                                          "CMFVideoThumbnail::ConvertYUVtoRGB32",
                                          1609,
                                          (unsigned int)v13);
                                    }
                                    if ( byte_1801712C8 )
                                    {
                                      v17 = 142;
                                      goto LABEL_15;
                                    }
                                  }
                                }
                                else
                                {
                                  v83 = (__int64 (__fastcall ***)())qword_180171350;
                                  if ( !qword_180171350 )
                                  {
                                    v84 = MFGetCallStackTracingWeakReference(0, v82);
                                    qword_180171350 = v84;
                                    if ( v84
                                      && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v84 + 8LL))(
                                           v84,
                                           2032) )
                                    {
                                      v83 = (__int64 (__fastcall ***)())qword_180171350;
                                    }
                                    else
                                    {
                                      v83 = &off_1801703B0;
                                      qword_180171350 = (__int64)&off_1801703B0;
                                    }
                                  }
                                  if ( *((_BYTE *)v83 + 8) )
                                  {
                                    v85 = sub_1800018B0(v83);
                                    if ( *(_DWORD *)(v85 + 1996) != v13 )
                                      sub_180083A48(
                                        v85,
                                        "CMFVideoThumbnail::ConvertYUVtoRGB32",
                                        1603,
                                        (unsigned int)v13);
                                  }
                                  if ( byte_1801712C8 )
                                  {
                                    v17 = 141;
                                    goto LABEL_15;
                                  }
                                }
                              }
                              else
                              {
                                v79 = (__int64 (__fastcall ***)())qword_180171350;
                                if ( !qword_180171350 )
                                {
                                  v80 = MFGetCallStackTracingWeakReference(0, v78);
                                  qword_180171350 = v80;
                                  if ( v80
                                    && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v80 + 8LL))(
                                         v80,
                                         2032) )
                                  {
                                    v79 = (__int64 (__fastcall ***)())qword_180171350;
                                  }
                                  else
                                  {
                                    v79 = &off_1801703B0;
                                    qword_180171350 = (__int64)&off_1801703B0;
                                  }
                                }
                                if ( *((_BYTE *)v79 + 8) )
                                {
                                  v81 = sub_1800018B0(v79);
                                  if ( *(_DWORD *)(v81 + 1996) != v13 )
                                    sub_180083A48(v81, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1602, (unsigned int)v13);
                                }
                                if ( byte_1801712C8 )
                                {
                                  v17 = 140;
                                  goto LABEL_15;
                                }
                              }
                            }
                            else
                            {
                              v75 = (__int64 (__fastcall ***)())qword_180171350;
                              if ( !qword_180171350 )
                              {
                                v76 = MFGetCallStackTracingWeakReference(0, v74);
                                qword_180171350 = v76;
                                if ( v76
                                  && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v76 + 8LL))(
                                       v76,
                                       2032) )
                                {
                                  v75 = (__int64 (__fastcall ***)())qword_180171350;
                                }
                                else
                                {
                                  v75 = &off_1801703B0;
                                  qword_180171350 = (__int64)&off_1801703B0;
                                }
                              }
                              if ( *((_BYTE *)v75 + 8) )
                              {
                                v77 = sub_1800018B0(v75);
                                if ( *(_DWORD *)(v77 + 1996) != v13 )
                                  sub_180083A48(v77, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1601, (unsigned int)v13);
                              }
                              if ( byte_1801712C8 )
                              {
                                v17 = 139;
                                goto LABEL_15;
                              }
                            }
                          }
                          else
                          {
                            v71 = (__int64 (__fastcall ***)())qword_180171350;
                            if ( !qword_180171350 )
                            {
                              v72 = MFGetCallStackTracingWeakReference(0, v70);
                              qword_180171350 = v72;
                              if ( v72
                                && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v72 + 8LL))(v72, 2032) )
                              {
                                v71 = (__int64 (__fastcall ***)())qword_180171350;
                              }
                              else
                              {
                                v71 = &off_1801703B0;
                                qword_180171350 = (__int64)&off_1801703B0;
                              }
                            }
                            if ( *((_BYTE *)v71 + 8) )
                            {
                              v73 = sub_1800018B0(v71);
                              if ( *(_DWORD *)(v73 + 1996) != v13 )
                                sub_180083A48(v73, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1600, (unsigned int)v13);
                            }
                            if ( byte_1801712C8 )
                            {
                              v17 = 138;
                              goto LABEL_15;
                            }
                          }
                        }
                        else
                        {
                          v67 = (__int64 (__fastcall ***)())qword_180171350;
                          if ( !qword_180171350 )
                          {
                            v68 = MFGetCallStackTracingWeakReference(0, v66);
                            qword_180171350 = v68;
                            if ( v68
                              && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 8LL))(v68, 2032) )
                            {
                              v67 = (__int64 (__fastcall ***)())qword_180171350;
                            }
                            else
                            {
                              v67 = &off_1801703B0;
                              qword_180171350 = (__int64)&off_1801703B0;
                            }
                          }
                          if ( *((_BYTE *)v67 + 8) )
                          {
                            v69 = sub_1800018B0(v67);
                            if ( *(_DWORD *)(v69 + 1996) != v13 )
                              sub_180083A48(v69, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1596, (unsigned int)v13);
                          }
                          if ( byte_1801712C8 )
                          {
                            v17 = 137;
                            goto LABEL_15;
                          }
                        }
                      }
                      else
                      {
                        v63 = (__int64 (__fastcall ***)())qword_180171350;
                        if ( !qword_180171350 )
                        {
                          v64 = MFGetCallStackTracingWeakReference(0, v62);
                          qword_180171350 = v64;
                          if ( v64
                            && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v64 + 8LL))(v64, 2032) )
                          {
                            v63 = (__int64 (__fastcall ***)())qword_180171350;
                          }
                          else
                          {
                            v63 = &off_1801703B0;
                            qword_180171350 = (__int64)&off_1801703B0;
                          }
                        }
                        if ( *((_BYTE *)v63 + 8) )
                        {
                          v65 = sub_1800018B0(v63);
                          if ( *(_DWORD *)(v65 + 1996) != v13 )
                            sub_180083A48(v65, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1594, (unsigned int)v13);
                        }
                        if ( byte_1801712C8 )
                        {
                          v17 = 136;
                          goto LABEL_15;
                        }
                      }
                    }
                    else
                    {
                      v59 = (__int64 (__fastcall ***)())qword_180171350;
                      if ( !qword_180171350 )
                      {
                        v60 = MFGetCallStackTracingWeakReference(0, v58);
                        qword_180171350 = v60;
                        if ( v60 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v60 + 8LL))(v60, 2032) )
                        {
                          v59 = (__int64 (__fastcall ***)())qword_180171350;
                        }
                        else
                        {
                          v59 = &off_1801703B0;
                          qword_180171350 = (__int64)&off_1801703B0;
                        }
                      }
                      if ( *((_BYTE *)v59 + 8) )
                      {
                        v61 = sub_1800018B0(v59);
                        if ( *(_DWORD *)(v61 + 1996) != v13 )
                          sub_180083A48(v61, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1593, (unsigned int)v13);
                      }
                      if ( byte_1801712C8 )
                      {
                        v17 = 135;
                        goto LABEL_15;
                      }
                    }
                  }
                  else
                  {
                    v55 = (__int64 (__fastcall ***)())qword_180171350;
                    if ( !qword_180171350 )
                    {
                      v56 = MFGetCallStackTracingWeakReference(0, v54);
                      qword_180171350 = v56;
                      if ( v56 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v56 + 8LL))(v56, 2032) )
                      {
                        v55 = (__int64 (__fastcall ***)())qword_180171350;
                      }
                      else
                      {
                        v55 = &off_1801703B0;
                        qword_180171350 = (__int64)&off_1801703B0;
                      }
                    }
                    if ( *((_BYTE *)v55 + 8) )
                    {
                      v57 = sub_1800018B0(v55);
                      if ( *(_DWORD *)(v57 + 1996) != v13 )
                        sub_180083A48(v57, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1592, (unsigned int)v13);
                    }
                    if ( byte_1801712C8 )
                    {
                      v17 = 134;
                      goto LABEL_15;
                    }
                  }
                }
                else
                {
                  v51 = (__int64 (__fastcall ***)())qword_180171350;
                  if ( !qword_180171350 )
                  {
                    v52 = MFGetCallStackTracingWeakReference(0, v50);
                    qword_180171350 = v52;
                    if ( v52 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
                    {
                      v51 = (__int64 (__fastcall ***)())qword_180171350;
                    }
                    else
                    {
                      v51 = &off_1801703B0;
                      qword_180171350 = (__int64)&off_1801703B0;
                    }
                  }
                  if ( *((_BYTE *)v51 + 8) )
                  {
                    v53 = sub_1800018B0(v51);
                    if ( *(_DWORD *)(v53 + 1996) != v13 )
                      sub_180083A48(v53, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1591, (unsigned int)v13);
                  }
                  if ( byte_1801712C8 )
                  {
                    v17 = 133;
                    goto LABEL_15;
                  }
                }
              }
              else
              {
                v47 = (__int64 (__fastcall ***)())qword_180171350;
                if ( !qword_180171350 )
                {
                  v48 = MFGetCallStackTracingWeakReference(0, v46);
                  qword_180171350 = v48;
                  if ( v48 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 8LL))(v48, 2032) )
                  {
                    v47 = (__int64 (__fastcall ***)())qword_180171350;
                  }
                  else
                  {
                    v47 = &off_1801703B0;
                    qword_180171350 = (__int64)&off_1801703B0;
                  }
                }
                if ( *((_BYTE *)v47 + 8) )
                {
                  v49 = sub_1800018B0(v47);
                  if ( *(_DWORD *)(v49 + 1996) != v13 )
                    sub_180083A48(v49, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1590, (unsigned int)v13);
                }
                if ( byte_1801712C8 )
                {
                  v17 = 132;
                  goto LABEL_15;
                }
              }
            }
            else
            {
              v41 = (__int64 (__fastcall ***)())qword_180171350;
              if ( !qword_180171350 )
              {
                v42 = MFGetCallStackTracingWeakReference(0, v40);
                qword_180171350 = v42;
                if ( v42 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 8LL))(v42, 2032) )
                {
                  v41 = (__int64 (__fastcall ***)())qword_180171350;
                }
                else
                {
                  v41 = &off_1801703B0;
                  qword_180171350 = (__int64)&off_1801703B0;
                }
              }
              if ( *((_BYTE *)v41 + 8) )
              {
                v43 = sub_1800018B0(v41);
                if ( *(_DWORD *)(v43 + 1996) != v13 )
                  sub_180083A48(v43, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1584, (unsigned int)v13);
              }
              if ( byte_1801712C8 )
              {
                v17 = 131;
                goto LABEL_15;
              }
            }
          }
          else
          {
            v35 = (__int64 (__fastcall ***)())qword_180171350;
            if ( !qword_180171350 )
            {
              v36 = MFGetCallStackTracingWeakReference(0, v34);
              qword_180171350 = v36;
              if ( v36 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
              {
                v35 = (__int64 (__fastcall ***)())qword_180171350;
              }
              else
              {
                v35 = &off_1801703B0;
                qword_180171350 = (__int64)&off_1801703B0;
              }
            }
            if ( *((_BYTE *)v35 + 8) )
            {
              v37 = sub_1800018B0(v35);
              if ( *(_DWORD *)(v37 + 1996) != v13 )
                sub_180083A48(v37, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1583, (unsigned int)v13);
            }
            if ( byte_1801712C8 )
            {
              v17 = 130;
              goto LABEL_15;
            }
          }
        }
        else
        {
          v31 = (__int64 (__fastcall ***)())qword_180171350;
          if ( !qword_180171350 )
          {
            v32 = MFGetCallStackTracingWeakReference(0, v30);
            qword_180171350 = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = (__int64 (__fastcall ***)())qword_180171350;
            }
            else
            {
              v31 = &off_1801703B0;
              qword_180171350 = (__int64)&off_1801703B0;
            }
          }
          if ( *((_BYTE *)v31 + 8) )
          {
            v33 = sub_1800018B0(v31);
            if ( *(_DWORD *)(v33 + 1996) != v13 )
              sub_180083A48(v33, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1581, (unsigned int)v13);
          }
          if ( byte_1801712C8 )
          {
            v17 = 129;
            goto LABEL_15;
          }
        }
      }
      else
      {
        v27 = (__int64 (__fastcall ***)())qword_180171350;
        if ( !qword_180171350 )
        {
          v28 = MFGetCallStackTracingWeakReference(0, v26);
          qword_180171350 = v28;
          if ( v28 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
          {
            v27 = (__int64 (__fastcall ***)())qword_180171350;
          }
          else
          {
            v27 = &off_1801703B0;
            qword_180171350 = (__int64)&off_1801703B0;
          }
        }
        if ( *((_BYTE *)v27 + 8) )
        {
          v29 = sub_1800018B0(v27);
          if ( *(_DWORD *)(v29 + 1996) != v13 )
            sub_180083A48(v29, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1580, (unsigned int)v13);
        }
        if ( byte_1801712C8 )
        {
          v17 = 128;
          goto LABEL_15;
        }
      }
    }
    else
    {
      v23 = (__int64 (__fastcall ***)())qword_180171350;
      if ( !qword_180171350 )
      {
        v24 = MFGetCallStackTracingWeakReference(0, v22);
        qword_180171350 = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v23 = (__int64 (__fastcall ***)())qword_180171350;
        }
        else
        {
          v23 = &off_1801703B0;
          qword_180171350 = (__int64)&off_1801703B0;
        }
      }
      if ( *((_BYTE *)v23 + 8) )
      {
        v25 = sub_1800018B0(v23);
        if ( *(_DWORD *)(v25 + 1996) != v13 )
          sub_180083A48(v25, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1579, (unsigned int)v13);
      }
      if ( byte_1801712C8 )
      {
        v17 = 127;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v14 = (__int64 (__fastcall ***)())qword_180171350;
    if ( !qword_180171350 )
    {
      v15 = MFGetCallStackTracingWeakReference(0, v12);
      qword_180171350 = v15;
      if ( v15 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
      {
        v14 = (__int64 (__fastcall ***)())qword_180171350;
      }
      else
      {
        v14 = &off_1801703B0;
        qword_180171350 = (__int64)&off_1801703B0;
      }
    }
    if ( *((_BYTE *)v14 + 8) )
    {
      v16 = sub_1800018B0(v14);
      if ( *(_DWORD *)(v16 + 1996) != v13 )
        sub_180083A48(v16, "CMFVideoThumbnail::ConvertYUVtoRGB32", 1574, (unsigned int)v13);
    }
    if ( byte_1801712C8 )
    {
      v17 = 126;
LABEL_15:
      sub_180051E44(*((_QWORD *)RequestContext + 2), v17, &stru_1801626E8, a1, v13);
    }
  }
LABEL_206:
  sub_180005D20(v95);
  sub_1800620B4(&v103);
  sub_1800620B4(&v102);
  sub_1800620B4(&v104);
  sub_1800620B4(&ppv);
  sub_1800620B4(&v97);
  sub_1800620B4(&v107);
  sub_1800620B4(&ppIMFSample);
  sub_1800620B4(&ppBuffer);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800efeac  push    rbp
0x1800efeae  push    rbx
0x1800efeaf  push    rsi
0x1800efeb0  push    rdi
0x1800efeb1  push    r12
0x1800efeb3  push    r13
0x1800efeb5  push    r14
0x1800efeb7  push    r15
0x1800efeb9  lea     rbp, [rsp-17h]
0x1800efebe  sub     rsp, 0E8h
0x1800efec5  mov     rax, cs:__security_cookie
0x1800efecc  xor     rax, rsp
0x1800efecf  mov     [rbp+4Fh+var_50], rax
0x1800efed3  mov     r12, [rbp+4Fh+arg_20]
0x1800efed7  xor     edi, edi
0x1800efed9  xorps   xmm0, xmm0
0x1800efedc  mov     [rbp+4Fh+ppBuffer], rdi
0x1800efee0  movups  [rbp+4Fh+var_90], xmm0
0x1800efee4  mov     r14, r8
0x1800efee7  mov     r13, rdx
0x1800efeea  movups  [rbp+4Fh+var_80], xmm0
0x1800efeee  mov     rsi, rcx
0x1800efef1  mov     r8d, 626h
0x1800efef7  movups  xmm0, cs:xmmword_1801568F0
0x1800efefe  lea     rdx, aCmfvideothumbn_2; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800eff05  mov     [rsp+120h+ppIMFSample], rdi
0x1800eff0a  lea     rcx, [rsp+120h+var_F0]
0x1800eff0f  mov     [rbp+4Fh+var_98], rdi
0x1800eff13  movdqu  xmmword ptr [rbp+4Fh+guidSubtype.Data1], xmm0
0x1800eff18  mov     r15, r9
0x1800eff1b  mov     [rsp+120h+var_E0], rdi
0x1800eff20  mov     [rbp+4Fh+pcbImageSize], edi
0x1800eff23  mov     [rbp+4Fh+var_A0], edi
0x1800eff26  mov     [rsp+120h+var_E8], rdi
0x1800eff2b  mov     [rbp+4Fh+var_B0], rdi
0x1800eff2f  mov     [rbp+4Fh+var_C0], rdi
0x1800eff33  mov     [rbp+4Fh+unWidth], edi
0x1800eff36  mov     [rsp+120h+unHeight], edi
0x1800eff3a  mov     [rbp+4Fh+var_B8], rdi
0x1800eff3e  call    sub_18000AE10
0x1800eff43  mov     rcx, cs:qword_180171350
0x1800eff4a  cmp     [rcx+8], dil
0x1800eff4e  jz      short loc_1800EFFA8
0x1800eff50  cmp     [rsi+190h], rdi
0x1800eff57  jz      short loc_1800EFFA8
0x1800eff59  call    sub_1800018B0
0x1800eff5e  mov     rcx, [rsi+190h]
0x1800eff65  mov     rdi, rax
0x1800eff68  mov     rdx, [rcx]
0x1800eff6b  mov     rax, [rdx+128h]
0x1800eff72  call    cs:__guard_dispatch_icall_fptr
0x1800eff78  mov     rcx, [rsi+190h]
0x1800eff7f  mov     ebx, eax
0x1800eff81  mov     rdx, [rcx]
0x1800eff84  mov     rax, [rdx+118h]
0x1800eff8b  lea     rdx, [rbp+4Fh+var_60]
0x1800eff8f  call    cs:__guard_dispatch_icall_fptr
0x1800eff95  movups  xmm0, xmmword ptr [rax]
0x1800eff98  mov     [rdi+7E0h], ebx
0x1800eff9e  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800effa6  xor     edi, edi
0x1800effa8  lea     rcx, [rsp+120h+var_E8]
0x1800effad  call    sub_1800620B4
0x1800effb2  xor     edx, edx; pUnkOuter
0x1800effb4  lea     rax, [rsp+120h+var_E8]
0x1800effb9  lea     r9, stru_1801626B8; riid
0x1800effc0  mov     [rsp+120h+ppv], rax; ppv
0x1800effc5  lea     rcx, stru_180159158; rclsid
0x1800effcc  lea     r8d, [rdx+1]; dwClsContext
0x1800effd0  call    cs:CoCreateInstance
0x1800effd7  nop     dword ptr [rax+rax+00h]
0x1800effdc  mov     ebx, eax
0x1800effde  test    eax, eax
0x1800effe0  jns     loc_1800F009A
0x1800effe6  mov     rcx, cs:qword_180171350
0x1800effed  test    rcx, rcx
0x1800efff0  jnz     short loc_1800F003A
0x1800efff2  call    cs:MFGetCallStackTracingWeakReference
0x1800efff9  nop     dword ptr [rax+rax+00h]
0x1800efffe  mov     cs:qword_180171350, rax
0x1800f0005  mov     rcx, rax
0x1800f0008  test    rax, rax
0x1800f000b  jz      short loc_1800F002C
0x1800f000d  mov     rax, [rax]
0x1800f0010  mov     edx, 7F0h
0x1800f0015  mov     rax, [rax+8]
0x1800f0019  call    cs:__guard_dispatch_icall_fptr
0x1800f001f  test    eax, eax
0x1800f0021  jz      short loc_1800F002C
0x1800f0023  mov     rcx, cs:qword_180171350
0x1800f002a  jmp     short loc_1800F003A
0x1800f002c  lea     rcx, off_1801703B0
0x1800f0033  mov     cs:qword_180171350, rcx
0x1800f003a  cmp     [rcx+8], dil
0x1800f003e  jz      short loc_1800F0065
0x1800f0040  call    sub_1800018B0
0x1800f0045  cmp     [rax+7CCh], ebx
0x1800f004b  jz      short loc_1800F0065
0x1800f004d  mov     r9d, ebx
0x1800f0050  lea     rdx, aCmfvideothumbn_2; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800f0057  mov     r8d, 626h
0x1800f005d  mov     rcx, rax
0x1800f0060  call    sub_180083A48
0x1800f0065  cmp     cs:byte_1801712C8, 1
0x1800f006c  jb      loc_1800F0DD3
0x1800f0072  mov     edx, 7Eh ; '~'
0x1800f0077  mov     rcx, cs:RequestContext
0x1800f007e  lea     r8, stru_1801626E8
0x1800f0085  mov     r9, rsi
0x1800f0088  mov     dword ptr [rsp+120h+ppv], ebx
0x1800f008c  mov     rcx, [rcx+10h]
0x1800f0090  call    sub_180051E44
0x1800f0095  jmp     loc_1800F0DD3
0x1800f009a  mov     rbx, [rsp+120h+var_E8]
0x1800f009f  lea     rcx, [rbp+4Fh+var_B8]
0x1800f00a3  mov     rax, [rbx]
0x1800f00a6  mov     rdi, [rax]
0x1800f00a9  call    sub_1800620B4
0x1800f00ae  lea     r8, [rbp+4Fh+var_B8]
0x1800f00b2  mov     rcx, rbx
0x1800f00b5  lea     rdx, qword_180162678
0x1800f00bc  mov     rax, rdi
0x1800f00bf  call    cs:__guard_dispatch_icall_fptr
0x1800f00c5  test    eax, eax
0x1800f00c7  js      short loc_1800F00E1
0x1800f00c9  mov     rcx, [rbp+4Fh+var_B8]
0x1800f00cd  mov     rdx, [rsi+190h]
0x1800f00d4  mov     rax, [rcx]
0x1800f00d7  mov     rax, [rax+20h]
0x1800f00db  call    cs:__guard_dispatch_icall_fptr
0x1800f00e1  mov     rdi, [rsp+120h+var_E8]
0x1800f00e6  lea     rcx, [rbp+4Fh+var_C0]
0x1800f00ea  mov     rax, [rdi]
0x1800f00ed  mov     rbx, [rax+40h]
0x1800f00f1  call    sub_1800620B4
0x1800f00f6  lea     rdx, [rbp+4Fh+var_C0]
0x1800f00fa  mov     rcx, rdi
0x1800f00fd  mov     rax, rbx
0x1800f0100  call    cs:__guard_dispatch_icall_fptr
0x1800f0106  xor     edi, edi
0x1800f0108  mov     ebx, eax
0x1800f010a  test    eax, eax
0x1800f010c  jns     loc_1800F01A8
0x1800f0112  mov     rcx, cs:qword_180171350
0x1800f0119  test    rcx, rcx
0x1800f011c  jnz     short loc_1800F0166
0x1800f011e  call    cs:MFGetCallStackTracingWeakReference
0x1800f0125  nop     dword ptr [rax+rax+00h]
0x1800f012a  mov     cs:qword_180171350, rax
0x1800f0131  mov     rcx, rax
0x1800f0134  test    rax, rax
0x1800f0137  jz      short loc_1800F0158
0x1800f0139  mov     rax, [rax]
0x1800f013c  mov     edx, 7F0h
0x1800f0141  mov     rax, [rax+8]
0x1800f0145  call    cs:__guard_dispatch_icall_fptr
0x1800f014b  test    eax, eax
0x1800f014d  jz      short loc_1800F0158
0x1800f014f  mov     rcx, cs:qword_180171350
0x1800f0156  jmp     short loc_1800F0166
0x1800f0158  lea     rcx, off_1801703B0
0x1800f015f  mov     cs:qword_180171350, rcx
0x1800f0166  cmp     [rcx+8], dil
0x1800f016a  jz      short loc_1800F0191
0x1800f016c  call    sub_1800018B0
0x1800f0171  cmp     [rax+7CCh], ebx
0x1800f0177  jz      short loc_1800F0191
0x1800f0179  mov     r9d, ebx
0x1800f017c  lea     rdx, aCmfvideothumbn_2; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800f0183  mov     r8d, 62Bh
0x1800f0189  mov     rcx, rax
0x1800f018c  call    sub_180083A48
0x1800f0191  cmp     cs:byte_1801712C8, 1
0x1800f0198  jb      loc_1800F0DD3
0x1800f019e  mov     edx, 7Fh
0x1800f01a3  jmp     loc_1800F0077
0x1800f01a8  mov     rcx, [rbp+4Fh+var_C0]
0x1800f01ac  lea     rdx, qword_180158E90
0x1800f01b3  mov     r8d, 1
0x1800f01b9  mov     rax, [rcx]
0x1800f01bc  mov     rax, [rax+0A8h]
0x1800f01c3  call    cs:__guard_dispatch_icall_fptr
0x1800f01c9  mov     ebx, eax
0x1800f01cb  test    eax, eax
0x1800f01cd  jns     loc_1800F0269
0x1800f01d3  mov     rcx, cs:qword_180171350
0x1800f01da  test    rcx, rcx
0x1800f01dd  jnz     short loc_1800F0227
0x1800f01df  call    cs:MFGetCallStackTracingWeakReference
0x1800f01e6  nop     dword ptr [rax+rax+00h]
0x1800f01eb  mov     cs:qword_180171350, rax
0x1800f01f2  mov     rcx, rax
0x1800f01f5  test    rax, rax
0x1800f01f8  jz      short loc_1800F0219
0x1800f01fa  mov     rax, [rax]
0x1800f01fd  mov     edx, 7F0h
0x1800f0202  mov     rax, [rax+8]
0x1800f0206  call    cs:__guard_dispatch_icall_fptr
0x1800f020c  test    eax, eax
0x1800f020e  jz      short loc_1800F0219
0x1800f0210  mov     rcx, cs:qword_180171350
0x1800f0217  jmp     short loc_1800F0227
0x1800f0219  lea     rcx, off_1801703B0
0x1800f0220  mov     cs:qword_180171350, rcx
0x1800f0227  cmp     [rcx+8], dil
0x1800f022b  jz      short loc_1800F0252
0x1800f022d  call    sub_1800018B0
0x1800f0232  cmp     [rax+7CCh], ebx
0x1800f0238  jz      short loc_1800F0252
0x1800f023a  mov     r9d, ebx
0x1800f023d  lea     rdx, aCmfvideothumbn_2; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800f0244  mov     r8d, 62Ch
0x1800f024a  mov     rcx, rax
0x1800f024d  call    sub_180083A48
0x1800f0252  cmp     cs:byte_1801712C8, 1
0x1800f0259  jb      loc_1800F0DD3
0x1800f025f  mov     edx, 80h
0x1800f0264  jmp     loc_1800F0077
0x1800f0269  mov     rcx, [rbp+4Fh+var_C0]
0x1800f026d  lea     rdx, qword_1801626A8
0x1800f0274  mov     r8d, 1
0x1800f027a  mov     rax, [rcx]
0x1800f027d  mov     rax, [rax+0A8h]
0x1800f0284  call    cs:__guard_dispatch_icall_fptr
0x1800f028a  mov     ebx, eax
0x1800f028c  test    eax, eax
0x1800f028e  jns     loc_1800F032A
0x1800f0294  mov     rcx, cs:qword_180171350
0x1800f029b  test    rcx, rcx
0x1800f029e  jnz     short loc_1800F02E8
0x1800f02a0  call    cs:MFGetCallStackTracingWeakReference
0x1800f02a7  nop     dword ptr [rax+rax+00h]
0x1800f02ac  mov     cs:qword_180171350, rax
0x1800f02b3  mov     rcx, rax
0x1800f02b6  test    rax, rax
0x1800f02b9  jz      short loc_1800F02DA
0x1800f02bb  mov     rax, [rax]
0x1800f02be  mov     edx, 7F0h
0x1800f02c3  mov     rax, [rax+8]
0x1800f02c7  call    cs:__guard_dispatch_icall_fptr
0x1800f02cd  test    eax, eax
0x1800f02cf  jz      short loc_1800F02DA
0x1800f02d1  mov     rcx, cs:qword_180171350
0x1800f02d8  jmp     short loc_1800F02E8
0x1800f02da  lea     rcx, off_1801703B0
0x1800f02e1  mov     cs:qword_180171350, rcx
0x1800f02e8  cmp     [rcx+8], dil
0x1800f02ec  jz      short loc_1800F0313
0x1800f02ee  call    sub_1800018B0
0x1800f02f3  cmp     [rax+7CCh], ebx
0x1800f02f9  jz      short loc_1800F0313
0x1800f02fb  mov     r9d, ebx
0x1800f02fe  lea     rdx, aCmfvideothumbn_2; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800f0305  mov     r8d, 62Dh
0x1800f030b  mov     rcx, rax
0x1800f030e  call    sub_180083A48
0x1800f0313  cmp     cs:byte_1801712C8, 1
0x1800f031a  jb      loc_1800F0DD3
0x1800f0320  mov     edx, 81h
0x1800f0325  jmp     loc_1800F0077
0x1800f032a  mov     rcx, [rsp+120h+var_E8]
0x1800f032f  xor     r9d, r9d
0x1800f0332  mov     r8, r14
0x1800f0335  xor     edx, edx
0x1800f0337  mov     rax, [rcx]
0x1800f033a  mov     rax, [rax+78h]
0x1800f033e  call    cs:__guard_dispatch_icall_fptr
0x1800f0344  xor     r14d, r14d
0x1800f0347  mov     ebx, eax
0x1800f0349  test    eax, eax
0x1800f034b  jns     loc_1800F03E7
0x1800f0351  mov     rcx, cs:qword_180171350
0x1800f0358  test    rcx, rcx
0x1800f035b  jnz     short loc_1800F03A5
0x1800f035d  call    cs:MFGetCallStackTracingWeakReference
0x1800f0364  nop     dword ptr [rax+rax+00h]
0x1800f0369  mov     cs:qword_180171350, rax
0x1800f0370  mov     rcx, rax
0x1800f0373  test    rax, rax
0x1800f0376  jz      short loc_1800F0397
0x1800f0378  mov     rax, [rax]
0x1800f037b  mov     edx, 7F0h
0x1800f0380  mov     rax, [rax+8]
0x1800f0384  call    cs:__guard_dispatch_icall_fptr
0x1800f038a  test    eax, eax
0x1800f038c  jz      short loc_1800F0397
0x1800f038e  mov     rcx, cs:qword_180171350
0x1800f0395  jmp     short loc_1800F03A5
0x1800f0397  lea     rcx, off_1801703B0
0x1800f039e  mov     cs:qword_180171350, rcx
0x1800f03a5  cmp     [rcx+8], r14b
0x1800f03a9  jz      short loc_1800F03D0
0x1800f03ab  call    sub_1800018B0
0x1800f03b0  cmp     [rax+7CCh], ebx
0x1800f03b6  jz      short loc_1800F03D0
0x1800f03b8  mov     r9d, ebx
0x1800f03bb  lea     rdx, aCmfvideothumbn_2; "CMFVideoThumbnail::ConvertYUVtoRGB32"
0x1800f03c2  mov     r8d, 62Fh
0x1800f03c8  mov     rcx, rax
0x1800f03cb  call    sub_180083A48
  ... truncated ...
```
