# CAppImport::UpdateSubscriptionTableAndPropertyBags(_GUID const &,_GUID,ushort *)

- ea: `0x180041ae4`
- end: `0x1800426ad`
- name: `?UpdateSubscriptionTableAndPropertyBags@CAppImport@@AEAAJAEBU_GUID@@U2@PEAG@Z`
- size: `3017`
- prototype: `__int64 __fastcall(CAppImport *__hidden this, const struct _GUID *, struct _GUID *__struct_ptr, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180011d74`

## callees

- `0x180041ae4`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041f77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800422db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800425ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800425f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041f77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800422db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800425ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800425f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180041d2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800421b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042491`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180041d2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800421b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180042491`

## pseudocode

```c
__int64 __fastcall CAppImport::UpdateSubscriptionTableAndPropertyBags(
        CAppImport *this,
        const struct _GUID *a2,
        struct _GUID *a3,
        unsigned __int16 *a4)
{
  __int64 v5; // rcx
  __int64 v9; // rax
  int v10; // ebx
  __int64 v11; // rcx
  _QWORD *v12; // rsi
  int v13; // eax
  unsigned int i; // edi
  _QWORD *v15; // r14
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r8
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // eax
  unsigned int j; // edi
  const struct _GUID **v24; // r14
  const struct _GUID *v25; // r9
  __int64 v26; // r8
  __int64 v27; // rcx
  int v28; // eax
  unsigned int k; // edi
  const struct _GUID **v30; // r14
  const struct _GUID *v31; // r9
  __int64 v32; // r8
  int v33; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v34; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v35; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+70h] [rbp-90h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h] BYREF
  int v42; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID *v43; // [rsp+98h] [rbp-68h] BYREF
  __int64 v44; // [rsp+A0h] [rbp-60h]
  int v45; // [rsp+A8h] [rbp-58h]
  int v46; // [rsp+ACh] [rbp-54h]
  struct _GUID *v47; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD *v48; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD *v49; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v50; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD *v51; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v52; // [rsp+D8h] [rbp-28h] BYREF
  int v53; // [rsp+E0h] [rbp-20h]
  int v54; // [rsp+E4h] [rbp-1Ch]
  int v55; // [rsp+E8h] [rbp-18h]
  int v56; // [rsp+ECh] [rbp-14h]
  __int128 v57; // [rsp+F0h] [rbp-10h]
  __int64 v58; // [rsp+100h] [rbp+0h]

  v5 = *((_QWORD *)this + 9);
  v47 = 0;
  v34 = 0;
  v33 = 0;
  v35 = 0;
  v42 = 0;
  v49 = 0;
  v48 = 0;
  v51 = 0;
  v50 = 0;
  v36 = 0;
  v37 = 0;
  v39 = 0;
  v38 = 0;
  v40 = 0;
  v41 = 0;
  if ( !v5 )
    return 2147549183LL;
  v58 = 0;
  v52 = a4;
  v57 = 0;
  v9 = -1;
  v53 = 0;
  v54 = -268435455;
  v55 = 130;
  do
    ++v9;
  while ( a4[v9] );
  v56 = v9 + 1;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64 *, __int64 *, unsigned __int16 **, __int64, int, int, __int64 *))(*(_QWORD *)v5 + 24LL))(
         v5,
         didCOMSERVICES,
         tidCOMSERVICES_SUBSCRIPTIONS_EXPORT,
         &v52,
         1,
         1,
         3,
         &v36) )
  {
LABEL_6:
    v10 = -2146368504;
    goto LABEL_112;
  }
  v11 = *((_QWORD *)this + 9);
  v43 = a3;
  v44 = 0x400000000LL;
  v45 = 72;
  v46 = 16;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, struct _GUID **, __int64, int, int, __int64 *))(*(_QWORD *)v11 + 24LL))(
          v11,
          didCOMSERVICES,
          tidSUBSCRIPTIONS,
          &v43,
          1,
          1,
          8,
          &v37);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 24LL))(v36);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 32LL))(v36);
      if ( v10 >= 0 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 24LL))(v37);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v36 + 72LL))(
                  v36,
                  0,
                  0,
                  0,
                  0,
                  0,
                  0,
                  0,
                  &v35);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int *))(*(_QWORD *)v37 + 72LL))(
                    v37,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    &v42);
            if ( v10 >= 0 )
            {
              v12 = CoTaskMemAlloc(saturated_mul(v35, 8u));
              if ( !v12 )
              {
LABEL_14:
                v10 = -2147024882;
                goto LABEL_112;
              }
LABEL_15:
              v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 40LL))(v36);
              v10 = v13;
              if ( v13 != -2146367487 )
              {
                if ( v13 < 0
                  || (v10 = (*(__int64 (__fastcall **)(__int64, __int64, int *, unsigned int *, _QWORD **))(*(_QWORD *)v36 + 64LL))(
                              v36,
                              19,
                              &v33,
                              &v34,
                              &v51),
                      v10 < 0)
                  || (v10 = (*(__int64 (__fastcall **)(__int64, __int64, int *, unsigned int *, _QWORD **))(*(_QWORD *)v36 + 64LL))(
                              v36,
                              20,
                              &v33,
                              &v34,
                              &v49),
                      v10 < 0)
                  || (v10 = (*(__int64 (__fastcall **)(__int64, __int64, int *, unsigned int *, _QWORD **))(*(_QWORD *)v36 + 64LL))(
                              v36,
                              17,
                              &v33,
                              &v34,
                              &v50),
                      v10 < 0)
                  || (v10 = (*(__int64 (__fastcall **)(__int64, __int64, int *, unsigned int *, _QWORD **))(*(_QWORD *)v36 + 64LL))(
                              v36,
                              18,
                              &v33,
                              &v34,
                              &v48),
                      v10 < 0)
                  || (v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 120LL))(v37), v10 < 0) )
                {
LABEL_111:
                  CoTaskMemFree(v12);
                  goto LABEL_112;
                }
                for ( i = 0; ; ++i )
                {
                  if ( i >= v35 )
                  {
                    v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 144LL))(v37);
                    if ( v10 < 0 )
                      goto LABEL_111;
                    goto LABEL_15;
                  }
                  v15 = &v12[i];
                  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, unsigned int *, _QWORD *))(*(_QWORD *)v36 + 64LL))(
                          v36,
                          i,
                          &v33,
                          &v34,
                          v15);
                  if ( v10 < 0 )
                    goto LABEL_111;
                  if ( i == 18 )
                  {
                    v16 = *v48 - *v49;
                    if ( *v48 == *v49 )
                      v16 = v48[1] - v49[1];
                    if ( !v16 )
                    {
                      *v15 = a2;
LABEL_30:
                      if ( i == 20 )
                      {
                        *v15 = a2;
                        goto LABEL_39;
                      }
LABEL_37:
                      if ( i == 19 )
                        v12[19] = (char *)this + 96;
                    }
                  }
                  else
                  {
                    if ( i != 17 )
                      goto LABEL_30;
                    v17 = *v50 - *v51;
                    if ( *v50 == *v51 )
                      v17 = v50[1] - v51[1];
                    if ( !v17 )
                    {
                      *v15 = (char *)this + 96;
                      goto LABEL_37;
                    }
                  }
LABEL_39:
                  v18 = 0;
                  if ( v33 == 128 )
                    v18 = v34;
                  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v37 + 160LL))(
                          v37,
                          i,
                          v18,
                          v12[i]);
                  if ( v10 < 0 )
                    goto LABEL_111;
                }
              }
              v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 96LL))(v37);
              if ( v10 < 0 )
                goto LABEL_111;
              CoTaskMemFree(v12);
              if ( v37 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
                v37 = 0;
              }
              v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 32LL))(v36);
              if ( v10 >= 0 )
              {
                while ( 1 )
                {
                  v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 40LL))(v36);
                  v10 = v19;
                  if ( v19 == -2146367487 )
                    break;
                  if ( v19 < 0 )
                    goto LABEL_112;
                  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, struct _GUID **))(*(_QWORD *)v36 + 64LL))(
                          v36,
                          0,
                          0,
                          0,
                          &v47);
                  if ( v10 < 0 )
                    goto LABEL_112;
                  v20 = *((_QWORD *)this + 9);
                  v57 = (unsigned __int64)v47;
                  v58 = 0x1000000048LL;
                  if ( (*(unsigned int (__fastcall **)(__int64, __int64 *, __int64 *, unsigned __int16 **, __int64, int, int, __int64 *))(*(_QWORD *)v20 + 24LL))(
                         v20,
                         didCOMSERVICES,
                         tidCOMSERVICES_PUBLISHERPROPERTIES_EXPORT,
                         &v52,
                         2,
                         1,
                         3,
                         &v39) )
                  {
                    goto LABEL_6;
                  }
                  v21 = *((_QWORD *)this + 9);
                  v43 = v47;
                  v44 = 0;
                  v45 = 72;
                  v46 = 16;
                  v10 = (*(__int64 (__fastcall **)(__int64, __int64 *, const struct _GUID *, struct _GUID **, __int64, int, int, __int64 *))(*(_QWORD *)v21 + 24LL))(
                          v21,
                          didCOMSERVICES,
                          &tidPUBLISHERPROPERTIES,
                          &v43,
                          1,
                          1,
                          8,
                          &v38);
                  if ( v10 < 0 )
                    goto LABEL_112;
                  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 24LL))(v39);
                  if ( v10 < 0 )
                    goto LABEL_112;
                  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 32LL))(v39);
                  if ( v10 < 0 )
                    goto LABEL_112;
                  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 24LL))(v38);
                  if ( v10 < 0 )
                    goto LABEL_112;
                  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v39 + 72LL))(
                          v39,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          &v35);
                  if ( v10 < 0 )
                    goto LABEL_112;
                  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int *))(*(_QWORD *)v38 + 72LL))(
                          v38,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          &v42);
                  if ( v10 < 0 )
                    goto LABEL_112;
                  v12 = CoTaskMemAlloc(saturated_mul(v35, 8u));
                  if ( !v12 )
                    goto LABEL_14;
                  while ( 1 )
                  {
                    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 40LL))(v39);
                    v10 = v22;
                    if ( v22 == -2146367487 )
                      break;
                    if ( v22 >= 0 )
                    {
                      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 120LL))(v38);
                      if ( v10 >= 0 )
                      {
                        for ( j = 0; j < v35; ++j )
                        {
                          v24 = (const struct _GUID **)&v12[j];
                          v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, unsigned int *, const struct _GUID **))(*(_QWORD *)v39 + 64LL))(
                                  v39,
                                  j,
                                  &v33,
                                  &v34,
                                  v24);
                          if ( v10 < 0 )
                            goto LABEL_111;
                          if ( j == 2 )
                          {
                            *v24 = a2;
                            v25 = a2;
                          }
                          else
                          {
                            v25 = *v24;
                            if ( j == 1 )
                            {
                              v25 = (const struct _GUID *)((char *)this + 96);
                              *v24 = (const struct _GUID *)((char *)this + 96);
                            }
                          }
                          v26 = 0;
                          if ( v33 == 128 )
                            v26 = v34;
                          v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, const struct _GUID *))(*(_QWORD *)v38 + 160LL))(
                                  v38,
                                  j,
                                  v26,
                                  v25);
                          if ( v10 < 0 )
                            goto LABEL_111;
                        }
                        v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 144LL))(v38);
                        if ( v10 >= 0 )
                          continue;
                      }
                    }
                    goto LABEL_111;
                  }
                  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 96LL))(v38);
                  if ( v10 < 0 )
                    goto LABEL_111;
                  CoTaskMemFree(v12);
                  if ( v39 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
                    v39 = 0;
                  }
                  if ( v38 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
                    v38 = 0;
                  }
                  v27 = *((_QWORD *)this + 9);
                  HIDWORD(v57) = 0;
                  if ( (*(unsigned int (__fastcall **)(__int64, __int64 *, __int64 *, unsigned __int16 **, __int64, int, int, __int64 *))(*(_QWORD *)v27 + 24LL))(
                         v27,
                         didCOMSERVICES,
                         tidCOMSERVICES_SUBSCRIBERPROPERTIES_EXPORT,
                         &v52,
                         2,
                         1,
                         3,
                         &v40) )
                  {
                    goto LABEL_6;
                  }
                  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, const struct _GUID *, struct _GUID **, __int64, int, int, __int64 *))(**((_QWORD **)this + 9) + 24LL))(
                          *((_QWORD *)this + 9),
                          didCOMSERVICES,
                          &tidSUBSCRIBERPROPERTIES,
                          &v43,
                          1,
                          1,
                          8,
                          &v41);
                  if ( v10 < 0 )
                    goto LABEL_112;
                  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 24LL))(v40);
                  if ( v10 < 0 )
                    goto LABEL_112;
                  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 32LL))(v40);
                  if ( v10 < 0 )
                    goto LABEL_112;
                  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 24LL))(v41);
                  if ( v10 < 0 )
                    goto LABEL_112;
                  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v40 + 72LL))(
                          v40,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          &v35);
                  if ( v10 < 0 )
                    goto LABEL_112;
                  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, int *))(*(_QWORD *)v41 + 72LL))(
                          v41,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          0,
                          &v42);
                  if ( v10 < 0 )
                    goto LABEL_112;
                  v12 = CoTaskMemAlloc(saturated_mul(v35, 8u));
                  if ( !v12 )
                    goto LABEL_14;
                  while ( 1 )
                  {
                    v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v40 + 40LL))(v40);
                    v10 = v28;
                    if ( v28 == -2146367487 )
                      break;
                    if ( v28 >= 0 )
                    {
                      v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 120LL))(v41);
                      if ( v10 >= 0 )
                      {
                        for ( k = 0; k < v35; ++k )
                        {
                          v30 = (const struct _GUID **)&v12[k];
                          v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, unsigned int *, const struct _GUID **))(*(_QWORD *)v40 + 64LL))(
                                  v40,
                                  k,
                                  &v33,
                                  &v34,
                                  v30);
                          if ( v10 < 0 )
                            goto LABEL_111;
                          if ( k == 2 )
                          {
                            *v30 = a2;
                            v31 = a2;
                          }
                          else
                          {
                            v31 = *v30;
                            if ( k == 1 )
                            {
                              v31 = (const struct _GUID *)((char *)this + 96);
                              *v30 = (const struct _GUID *)((char *)this + 96);
                            }
                          }
                          v32 = 0;
                          if ( v33 == 128 )
                            v32 = v34;
                          v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, const struct _GUID *))(*(_QWORD *)v41 + 160LL))(
                                  v41,
                                  k,
                                  v32,
                                  v31);
                          if ( v10 < 0 )
                            goto LABEL_111;
                        }
                        v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 144LL))(v41);
                        if ( v10 >= 0 )
                          continue;
                      }
                    }
                    goto LABEL_111;
                  }
                  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v41 + 96LL))(v41);
                  if ( v10 < 0 )
                    goto LABEL_111;
                  CoTaskMemFree(v12);
                  if ( v40 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
                    v40 = 0;
                  }
                  if ( v41 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                    v41 = 0;
                  }
                }
                v10 = 0;
              }
            }
          }
        }
      }
    }
  }
LABEL_112:
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v36 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v39 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v39 = 0;
  }
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
  }
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180041ae4  push    rbp
0x180041ae6  push    rbx
0x180041ae7  push    rsi
0x180041ae8  push    rdi
0x180041ae9  push    r12
0x180041aeb  push    r13
0x180041aed  push    r14
0x180041aef  push    r15
0x180041af1  lea     rbp, [rsp-18h]
0x180041af6  sub     rsp, 118h
0x180041afd  xor     r15d, r15d
0x180041b00  mov     r13, rcx
0x180041b03  mov     rcx, [rcx+48h]
0x180041b07  mov     rbx, r8
0x180041b0a  mov     [rbp+50h+var_A0], r15
0x180041b0e  mov     r12, rdx
0x180041b11  mov     [rsp+150h+var_FC], r15d
0x180041b16  mov     [rsp+150h+var_100], r15d
0x180041b1b  mov     [rsp+150h+var_F8], r15d
0x180041b20  mov     [rbp+50h+var_C0], r15d
0x180041b24  mov     [rbp+50h+var_90], r15
0x180041b28  mov     [rbp+50h+var_98], r15
0x180041b2c  mov     [rbp+50h+var_80], r15
0x180041b30  mov     [rbp+50h+var_88], r15
0x180041b34  mov     [rsp+150h+var_F0], r15
0x180041b39  mov     [rsp+150h+var_E8], r15
0x180041b3e  mov     [rsp+150h+var_D8], r15
0x180041b43  mov     [rsp+150h+var_E0], r15
0x180041b48  mov     [rbp+50h+var_D0], r15
0x180041b4c  mov     [rbp+50h+var_C8], r15
0x180041b50  test    rcx, rcx
0x180041b53  jnz     short loc_180041B5F
0x180041b55  mov     eax, 8000FFFFh
0x180041b5a  jmp     loc_180042699
0x180041b5f  xorps   xmm0, xmm0
0x180041b62  mov     [rbp+50h+var_50], r15
0x180041b66  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180041b6a  mov     [rbp+50h+var_78], r9
0x180041b6e  movdqu  [rbp+50h+var_60], xmm0
0x180041b73  mov     rax, rsi
0x180041b76  mov     [rbp+50h+var_70], r15d
0x180041b7a  mov     [rbp+50h+var_6C], 0F0000001h
0x180041b81  mov     [rbp+50h+var_68], 82h
0x180041b88  inc     rax
0x180041b8b  cmp     [r9+rax*2], r15w
0x180041b90  jnz     short loc_180041B88
0x180041b92  inc     eax
0x180041b94  lea     rdx, [rsp+150h+var_F0]
0x180041b99  mov     [rsp+150h+var_118], rdx
0x180041b9e  lea     r9, [rbp+50h+var_78]
0x180041ba2  mov     [rbp+50h+var_64], eax
0x180041ba5  lea     r8, tidCOMSERVICES_SUBSCRIPTIONS_EXPORT
0x180041bac  mov     rax, [rcx]
0x180041baf  lea     rdx, didCOMSERVICES
0x180041bb6  mov     edi, 1
0x180041bbb  mov     dword ptr [rsp+150h+var_120], 3
0x180041bc3  mov     dword ptr [rsp+150h+var_128], edi
0x180041bc7  mov     [rsp+150h+var_130], rdi
0x180041bcc  mov     rax, [rax+18h]
0x180041bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041bd5  test    eax, eax
0x180041bd7  jz      short loc_180041BE3
0x180041bd9  mov     ebx, 80110408h
0x180041bde  jmp     loc_1800425FD
0x180041be3  mov     rcx, [r13+48h]
0x180041be7  lea     rdx, [rsp+150h+var_E8]
0x180041bec  mov     [rsp+150h+var_118], rdx
0x180041bf1  lea     r9, [rbp+50h+var_B8]
0x180041bf5  mov     [rbp+50h+var_B8], rbx
0x180041bf9  lea     r8, tidSUBSCRIPTIONS
0x180041c00  mov     dword ptr [rbp+50h+var_B0], r15d
0x180041c04  lea     rdx, didCOMSERVICES
0x180041c0b  mov     dword ptr [rbp+50h+var_B0+4], 4
0x180041c12  mov     r14d, 8
0x180041c18  mov     [rbp+50h+var_A8], 48h ; 'H'
0x180041c1f  mov     [rbp+50h+var_A4], 10h
0x180041c26  mov     rax, [rcx]
0x180041c29  mov     dword ptr [rsp+150h+var_120], r14d
0x180041c2e  mov     dword ptr [rsp+150h+var_128], edi
0x180041c32  mov     [rsp+150h+var_130], rdi
0x180041c37  mov     rax, [rax+18h]
0x180041c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c40  mov     ebx, eax
0x180041c42  test    eax, eax
0x180041c44  js      loc_1800425FD
0x180041c4a  mov     rcx, [rsp+150h+var_F0]
0x180041c4f  mov     rax, [rcx]
0x180041c52  mov     rax, [rax+18h]
0x180041c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c5b  mov     ebx, eax
0x180041c5d  test    eax, eax
0x180041c5f  js      loc_1800425FD
0x180041c65  mov     rcx, [rsp+150h+var_F0]
0x180041c6a  mov     rax, [rcx]
0x180041c6d  mov     rax, [rax+20h]
0x180041c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c76  mov     ebx, eax
0x180041c78  test    eax, eax
0x180041c7a  js      loc_1800425FD
0x180041c80  mov     rcx, [rsp+150h+var_E8]
0x180041c85  mov     rax, [rcx]
0x180041c88  mov     rax, [rax+18h]
0x180041c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041c91  mov     ebx, eax
0x180041c93  test    eax, eax
0x180041c95  js      loc_1800425FD
0x180041c9b  mov     rcx, [rsp+150h+var_F0]
0x180041ca0  lea     rdx, [rsp+150h+var_F8]
0x180041ca5  mov     [rsp+150h+var_110], rdx
0x180041caa  xor     r9d, r9d
0x180041cad  mov     [rsp+150h+var_118], r15
0x180041cb2  xor     r8d, r8d
0x180041cb5  mov     [rsp+150h+var_120], r15
0x180041cba  xor     edx, edx
0x180041cbc  mov     rax, [rcx]
0x180041cbf  mov     [rsp+150h+var_128], r15
0x180041cc4  mov     [rsp+150h+var_130], r15
0x180041cc9  mov     rax, [rax+48h]
0x180041ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041cd2  mov     ebx, eax
0x180041cd4  test    eax, eax
0x180041cd6  js      loc_1800425FD
0x180041cdc  mov     rcx, [rsp+150h+var_E8]
0x180041ce1  lea     rdx, [rbp+50h+var_C0]
0x180041ce5  mov     [rsp+150h+var_110], rdx
0x180041cea  xor     r9d, r9d
0x180041ced  mov     [rsp+150h+var_118], r15
0x180041cf2  xor     r8d, r8d
0x180041cf5  mov     [rsp+150h+var_120], r15
0x180041cfa  xor     edx, edx
0x180041cfc  mov     rax, [rcx]
0x180041cff  mov     [rsp+150h+var_128], r15
0x180041d04  mov     [rsp+150h+var_130], r15
0x180041d09  mov     rax, [rax+48h]
0x180041d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d12  mov     ebx, eax
0x180041d14  test    eax, eax
0x180041d16  js      loc_1800425FD
0x180041d1c  mov     ecx, [rsp+150h+var_F8]
0x180041d20  mov     eax, r14d
0x180041d23  mul     rcx
0x180041d26  cmovb   rax, rsi
0x180041d2a  mov     rcx, rax; cb
0x180041d2d  call    cs:__imp_CoTaskMemAlloc
0x180041d33  mov     rsi, rax
0x180041d36  test    rax, rax
0x180041d39  jnz     short loc_180041D45
0x180041d3b  mov     ebx, 8007000Eh
0x180041d40  jmp     loc_1800425FD
0x180041d45  mov     rcx, [rsp+150h+var_F0]
0x180041d4a  mov     rax, [rcx]
0x180041d4d  mov     rax, [rax+28h]
0x180041d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d56  mov     ebx, eax
0x180041d58  cmp     eax, 80110801h
0x180041d5d  jz      loc_180041F59
0x180041d63  test    eax, eax
0x180041d65  js      loc_1800425F4
0x180041d6b  mov     rcx, [rsp+150h+var_F0]
0x180041d70  lea     rdx, [rbp+50h+var_80]
0x180041d74  mov     [rsp+150h+var_130], rdx
0x180041d79  lea     r9, [rsp+150h+var_FC]
0x180041d7e  lea     r8, [rsp+150h+var_100]
0x180041d83  mov     edx, 13h
0x180041d88  mov     rax, [rcx]
0x180041d8b  mov     rax, [rax+40h]
0x180041d8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d94  mov     ebx, eax
0x180041d96  test    eax, eax
0x180041d98  js      loc_1800425F4
0x180041d9e  mov     rcx, [rsp+150h+var_F0]
0x180041da3  lea     rdx, [rbp+50h+var_90]
0x180041da7  mov     [rsp+150h+var_130], rdx
0x180041dac  lea     r9, [rsp+150h+var_FC]
0x180041db1  lea     r8, [rsp+150h+var_100]
0x180041db6  mov     edx, 14h
0x180041dbb  mov     rax, [rcx]
0x180041dbe  mov     rax, [rax+40h]
0x180041dc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041dc7  mov     ebx, eax
0x180041dc9  test    eax, eax
0x180041dcb  js      loc_1800425F4
0x180041dd1  mov     rcx, [rsp+150h+var_F0]
0x180041dd6  lea     rdx, [rbp+50h+var_88]
0x180041dda  mov     [rsp+150h+var_130], rdx
0x180041ddf  lea     r9, [rsp+150h+var_FC]
0x180041de4  lea     r8, [rsp+150h+var_100]
0x180041de9  mov     edx, 11h
0x180041dee  mov     rax, [rcx]
0x180041df1  mov     rax, [rax+40h]
0x180041df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041dfa  mov     ebx, eax
0x180041dfc  test    eax, eax
0x180041dfe  js      loc_1800425F4
0x180041e04  mov     rcx, [rsp+150h+var_F0]
0x180041e09  lea     rdx, [rbp+50h+var_98]
0x180041e0d  mov     [rsp+150h+var_130], rdx
0x180041e12  lea     r9, [rsp+150h+var_FC]
0x180041e17  lea     r8, [rsp+150h+var_100]
0x180041e1c  mov     edx, 12h
0x180041e21  mov     rax, [rcx]
0x180041e24  mov     rax, [rax+40h]
0x180041e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e2d  mov     ebx, eax
0x180041e2f  test    eax, eax
0x180041e31  js      loc_1800425F4
0x180041e37  mov     rcx, [rsp+150h+var_E8]
0x180041e3c  mov     rax, [rcx]
0x180041e3f  mov     rax, [rax+78h]
0x180041e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e48  mov     ebx, eax
0x180041e4a  test    eax, eax
0x180041e4c  js      loc_1800425F4
0x180041e52  mov     edi, r15d
0x180041e55  cmp     edi, [rsp+150h+var_F8]
0x180041e59  jnb     loc_180041F36
0x180041e5f  mov     rcx, [rsp+150h+var_F0]
0x180041e64  lea     r9, [rsp+150h+var_FC]
0x180041e69  mov     r15d, edi
0x180041e6c  lea     r8, [rsp+150h+var_100]
0x180041e71  mov     edx, edi
0x180041e73  mov     rax, [rcx]
0x180041e76  lea     r14, [rsi+r15*8]
0x180041e7a  mov     [rsp+150h+var_130], r14
0x180041e7f  mov     rax, [rax+40h]
0x180041e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041e88  mov     ebx, eax
0x180041e8a  test    eax, eax
0x180041e8c  js      loc_1800425F1
0x180041e92  cmp     edi, 12h
0x180041e95  jnz     short loc_180041EC1
0x180041e97  mov     rcx, [rbp+50h+var_98]
0x180041e9b  mov     rdx, [rbp+50h+var_90]
0x180041e9f  mov     rax, [rcx]
0x180041ea2  sub     rax, [rdx]
0x180041ea5  jnz     short loc_180041EAF
0x180041ea7  mov     rax, [rcx+8]
0x180041eab  sub     rax, [rdx+8]
0x180041eaf  test    rax, rax
0x180041eb2  jnz     short loc_180041EF7
0x180041eb4  mov     [r14], r12
0x180041eb7  cmp     edi, 14h
0x180041eba  jnz     short loc_180041EEA
0x180041ebc  mov     [r14], r12
0x180041ebf  jmp     short loc_180041EF7
0x180041ec1  cmp     edi, 11h
0x180041ec4  jnz     short loc_180041EB7
0x180041ec6  mov     rcx, [rbp+50h+var_88]
0x180041eca  mov     rdx, [rbp+50h+var_80]
0x180041ece  mov     rax, [rcx]
0x180041ed1  sub     rax, [rdx]
0x180041ed4  jnz     short loc_180041EDE
0x180041ed6  mov     rax, [rcx+8]
0x180041eda  sub     rax, [rdx+8]
0x180041ede  test    rax, rax
0x180041ee1  jnz     short loc_180041EF7
0x180041ee3  lea     rax, [r13+60h]
0x180041ee7  mov     [r14], rax
0x180041eea  cmp     edi, 13h
0x180041eed  jnz     short loc_180041EF7
0x180041eef  lea     rax, [r13+60h]
0x180041ef3  mov     [rsi+r15*8], rax
0x180041ef7  mov     rcx, [rsp+150h+var_E8]
0x180041efc  xor     r8d, r8d
0x180041eff  cmp     [rsp+150h+var_100], 80h
0x180041f07  mov     edx, edi
0x180041f09  mov     r9, [rsi+r15*8]
0x180041f0d  cmovz   r8d, [rsp+150h+var_FC]
0x180041f13  mov     rax, [rcx]
0x180041f16  mov     rax, [rax+0A0h]
0x180041f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f22  xor     r15d, r15d
0x180041f25  mov     ebx, eax
0x180041f27  test    eax, eax
0x180041f29  js      loc_1800425F4
0x180041f2f  inc     edi
0x180041f31  jmp     loc_180041E55
0x180041f36  mov     rcx, [rsp+150h+var_E8]
0x180041f3b  mov     rax, [rcx]
0x180041f3e  mov     rax, [rax+90h]
0x180041f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f4a  mov     ebx, eax
0x180041f4c  test    eax, eax
0x180041f4e  jns     loc_180041D45
0x180041f54  jmp     loc_1800425F4
0x180041f59  mov     rcx, [rsp+150h+var_E8]
0x180041f5e  mov     rax, [rcx]
0x180041f61  mov     rax, [rax+60h]
0x180041f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041f6a  mov     ebx, eax
0x180041f6c  test    eax, eax
0x180041f6e  js      loc_1800425F4
0x180041f74  mov     rcx, rsi; pv
0x180041f77  call    cs:__imp_CoTaskMemFree
0x180041f7d  mov     rcx, [rsp+150h+var_E8]
0x180041f82  test    rcx, rcx
0x180041f85  jz      short loc_180041F98
0x180041f87  mov     rax, [rcx]
0x180041f8a  mov     rax, [rax+10h]
0x180041f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
