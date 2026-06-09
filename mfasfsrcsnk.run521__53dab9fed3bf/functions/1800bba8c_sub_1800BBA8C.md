# sub_1800BBA8C

- ea: `0x1800bba8c`
- end: `0x1800bc689`
- name: `sub_1800BBA8C`
- size: `3069`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800bb020`

## callees

- `0x180001870`
- `0x180005880`
- `0x18000a580`
- `0x18003d740`
- `0x18004f390`
- `0x18007fdd0`
- `0x1800ace08`
- `0x1800bba8c`
- `0x1800bc8b4`
- `0x1800c4bb0`
- `0x180134e94`
- `0x1801361cc`
- `0x18013e2e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bc652`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bc652`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bbb09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bbb09`
- `MFPlat!MFCreateMediaEvent` at `0x1800bc3e7`
- `MFPlat!MFCreateMediaEvent` at `0x1800bc3e7`
- `MFPlat!DestroyPropVariant` at `0x1800bc649`
- `MFPlat!DestroyPropVariant` at `0x1800bc649`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbb24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbbd3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbc84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbd35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbde3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbe91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbf3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbff1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc0be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc18c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc26f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc34c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc403`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc4e9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbb24`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbbd3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbc84`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbd35`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbde3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbe91`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbf3f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bbff1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc0be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc18c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc26f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc34c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc403`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800bc4e9`

## pseudocode

```c
__int64 __fastcall sub_1800BBA8C(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 (__fastcall ***v5)(); // rcx
  __int64 v6; // rax
  HRESULT v7; // edi
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 (__fastcall ***v11)(); // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 (__fastcall ***v15)(); // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 (__fastcall ***v19)(); // rcx
  __int64 v20; // rax
  __int64 v21; // rax
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
  __int64 v38; // rdx
  __int64 (__fastcall ***v39)(); // rcx
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rdx
  __int64 (__fastcall ***v43)(); // rcx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rcx
  unsigned int v47; // esi
  __int64 v48; // rdx
  __int64 (__fastcall ***v49)(); // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  __int16 v52; // dx
  int v53; // ecx
  unsigned int v54; // eax
  int v55; // ecx
  __int64 v56; // rdx
  __int64 (__fastcall ***v57)(); // rcx
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 (__fastcall ***v61)(); // rcx
  __int64 v62; // rax
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 (__fastcall ***v65)(); // rcx
  __int64 v66; // rax
  __int64 v67; // rax
  __int64 v68; // rax
  _BYTE v70[8]; // [rsp+30h] [rbp-29h] BYREF
  __int64 v71; // [rsp+38h] [rbp-21h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+40h] [rbp-19h] BYREF
  __int64 v73; // [rsp+48h] [rbp-11h] BYREF
  __int64 v74; // [rsp+50h] [rbp-9h] BYREF
  __int64 v75; // [rsp+58h] [rbp-1h] BYREF
  int v76; // [rsp+60h] [rbp+7h] BYREF
  unsigned int v77; // [rsp+64h] [rbp+Bh] BYREF
  int v78; // [rsp+68h] [rbp+Fh] BYREF
  __int128 v79; // [rsp+70h] [rbp+17h] BYREF
  __int64 v80; // [rsp+80h] [rbp+27h]

  sub_18000A580(v70, "CASFBytewiseMediaSource::OnByteStreamEvent", 5130);
  v77 = 0;
  v73 = 0;
  v80 = 0;
  v79 = 0;
  v74 = 0;
  v75 = 0;
  v71 = 0;
  ppEvent = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 704));
  if ( a2 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 24LL))(a2, &v75);
    if ( v7 >= 0 )
    {
      v7 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v75)(v75, &qword_18014E790, &v74);
      if ( v7 >= 0 )
      {
        v7 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v74)(v74, &qword_18014E780, &v73);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v73 + 40LL))(v73, a2, &v71);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v71 + 264LL))(v71, &v77);
            if ( v7 >= 0 )
            {
              v7 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v71 + 288LL))(v71, &v79);
              if ( v7 >= 0 )
              {
                v76 = 0;
                v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v71 + 280LL))(v71, &v76);
                if ( v7 >= 0 )
                {
                  if ( (unsigned __int8)byte_1801692CB >= 8u )
                    sub_1801361CC(1, v34, v71);
                  if ( *(_DWORD *)(a1 + 700) )
                    goto LABEL_174;
                  v7 = sub_1800ACE08(a1, v77, (unsigned int)v76, &v79);
                  if ( v7 >= 0 )
                  {
                    if ( v76 >= 0 )
                    {
                      switch ( v77 )
                      {
                        case 0x7Au:
                          *(_DWORD *)(a1 + 916) = 1;
                          break;
                        case 0x7Bu:
                          if ( *(_DWORD *)(a1 + 916) )
                          {
                            *(_DWORD *)(a1 + 916) = 0;
                            if ( *(_DWORD *)(a1 + 920) )
                            {
                              v45 = *(_QWORD *)(a1 + 760);
                              *(_DWORD *)(a1 + 920) = 0;
                              if ( v45 )
                              {
                                if ( *(_DWORD *)(v45 + 16) == 2 && *(_QWORD *)(a1 + 1240) )
                                  sub_1800BC8B4(a1);
                              }
                            }
                          }
                          break;
                        case 0x2BCu:
                          v46 = *(_QWORD *)(a1 + 1200);
                          v47 = *(_DWORD *)(a1 + 908);
                          v78 = 0;
                          v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 24LL))(v46, &v78);
                          if ( v7 < 0 )
                          {
                            v49 = (__int64 (__fastcall ***)())qword_180169350;
                            if ( !qword_180169350 )
                            {
                              v50 = MFGetCallStackTracingWeakReference(0, v48);
                              qword_180169350 = v50;
                              if ( v50
                                && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
                              {
                                v49 = (__int64 (__fastcall ***)())qword_180169350;
                              }
                              else
                              {
                                v49 = &off_1801683B0;
                                qword_180169350 = (__int64)&off_1801683B0;
                              }
                            }
                            if ( *((_BYTE *)v49 + 8) )
                            {
                              v51 = sub_180001870(v49);
                              if ( *(_DWORD *)(v51 + 1996) != v7 )
                                sub_18007FDD0(v51, "CASFBytewiseMediaSource::OnByteStreamEvent", 5219, (unsigned int)v7);
                            }
                            if ( byte_1801692C8 )
                            {
                              v9 = 435;
                              goto LABEL_173;
                            }
                            goto LABEL_174;
                          }
                          v52 = v78;
                          if ( *(_DWORD *)(a1 + 912) != v78 )
                          {
                            v53 = *(_DWORD *)(a1 + 908);
                            v54 = v53 & 0xFFFFFF7F;
                            *(_DWORD *)(a1 + 912) = v78;
                            v55 = v53 | 0x80;
                            if ( (v52 & 0x800) == 0 )
                              v55 = v54;
                            *(_DWORD *)(a1 + 908) = v55;
                            if ( *(_QWORD *)(a1 + 1016) )
                            {
                              v7 = sub_1800C4BB0(a1);
                              if ( v7 < 0 )
                              {
                                v57 = (__int64 (__fastcall ***)())qword_180169350;
                                if ( !qword_180169350 )
                                {
                                  v58 = MFGetCallStackTracingWeakReference(0, v56);
                                  qword_180169350 = v58;
                                  if ( v58
                                    && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v58 + 8LL))(
                                         v58,
                                         2032) )
                                  {
                                    v57 = (__int64 (__fastcall ***)())qword_180169350;
                                  }
                                  else
                                  {
                                    v57 = &off_1801683B0;
                                    qword_180169350 = (__int64)&off_1801683B0;
                                  }
                                }
                                if ( *((_BYTE *)v57 + 8) )
                                {
                                  v59 = sub_180001870(v57);
                                  if ( *(_DWORD *)(v59 + 1996) != v7 )
                                    sub_18007FDD0(
                                      v59,
                                      "CASFBytewiseMediaSource::OnByteStreamEvent",
                                      5236,
                                      (unsigned int)v7);
                                }
                                if ( byte_1801692C8 )
                                {
                                  v9 = 436;
                                  goto LABEL_173;
                                }
                                goto LABEL_174;
                              }
                            }
                            v7 = MFCreateMediaEvent(0xDBu, &Buf1, 0, 0, &ppEvent);
                            if ( v7 < 0 )
                            {
                              v61 = (__int64 (__fastcall ***)())qword_180169350;
                              if ( !qword_180169350 )
                              {
                                v62 = MFGetCallStackTracingWeakReference(0, v60);
                                qword_180169350 = v62;
                                if ( v62
                                  && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v62 + 8LL))(
                                       v62,
                                       2032) )
                                {
                                  v61 = (__int64 (__fastcall ***)())qword_180169350;
                                }
                                else
                                {
                                  v61 = &off_1801683B0;
                                  qword_180169350 = (__int64)&off_1801683B0;
                                }
                              }
                              if ( *((_BYTE *)v61 + 8) )
                              {
                                v63 = sub_180001870(v61);
                                if ( *(_DWORD *)(v63 + 1996) != v7 )
                                  sub_18007FDD0(
                                    v63,
                                    "CASFBytewiseMediaSource::OnByteStreamEvent",
                                    5248,
                                    (unsigned int)v7);
                              }
                              if ( byte_1801692C8 )
                              {
                                v9 = 437;
                                goto LABEL_173;
                              }
                              goto LABEL_174;
                            }
                            ((void (__fastcall *)(IMFMediaEvent *, __int64 *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
                              ppEvent,
                              qword_18014E8F0,
                              *(unsigned int *)(a1 + 908));
                            ((void (__fastcall *)(IMFMediaEvent *, __int64 *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
                              ppEvent,
                              qword_18014E900,
                              v47);
                            v7 = sub_180134E94(a1 + 768, ppEvent);
                            if ( v7 < 0 )
                            {
                              v65 = (__int64 (__fastcall ***)())qword_180169350;
                              if ( !qword_180169350 )
                              {
                                v66 = MFGetCallStackTracingWeakReference(0, v64);
                                qword_180169350 = v66;
                                if ( v66
                                  && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v66 + 8LL))(
                                       v66,
                                       2032) )
                                {
                                  v65 = (__int64 (__fastcall ***)())qword_180169350;
                                }
                                else
                                {
                                  v65 = &off_1801683B0;
                                  qword_180169350 = (__int64)&off_1801683B0;
                                }
                              }
                              if ( *((_BYTE *)v65 + 8) )
                              {
                                v67 = sub_180001870(v65);
                                if ( *(_DWORD *)(v67 + 1996) != v7 )
                                  sub_18007FDD0(
                                    v67,
                                    "CASFBytewiseMediaSource::OnByteStreamEvent",
                                    5255,
                                    (unsigned int)v7);
                              }
                              if ( byte_1801692C8 )
                              {
                                v9 = 438;
                                goto LABEL_173;
                              }
                              goto LABEL_174;
                            }
                          }
                          break;
                      }
                    }
                    v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v73 + 32LL))(
                           v73,
                           a1 + 640,
                           v74);
                    if ( v7 < 0 )
                    {
                      v43 = (__int64 (__fastcall ***)())qword_180169350;
                      if ( !qword_180169350 )
                      {
                        v44 = MFGetCallStackTracingWeakReference(0, v42);
                        qword_180169350 = v44;
                        if ( v44 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
                        {
                          v43 = (__int64 (__fastcall ***)())qword_180169350;
                        }
                        else
                        {
                          v43 = &off_1801683B0;
                          qword_180169350 = (__int64)&off_1801683B0;
                        }
                      }
                      if ( *((_BYTE *)v43 + 8) )
                      {
                        v68 = sub_180001870(v43);
                        if ( *(_DWORD *)(v68 + 1996) != v7 )
                          sub_18007FDD0(v68, "CASFBytewiseMediaSource::OnByteStreamEvent", 5261, (unsigned int)v7);
                      }
                      if ( byte_1801692C8 )
                      {
                        v9 = 439;
                        goto LABEL_173;
                      }
                    }
                    goto LABEL_174;
                  }
                  v39 = (__int64 (__fastcall ***)())qword_180169350;
                  if ( !qword_180169350 )
                  {
                    v40 = MFGetCallStackTracingWeakReference(0, v38);
                    qword_180169350 = v40;
                    if ( v40 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
                    {
                      v39 = (__int64 (__fastcall ***)())qword_180169350;
                    }
                    else
                    {
                      v39 = &off_1801683B0;
                      qword_180169350 = (__int64)&off_1801683B0;
                    }
                  }
                  if ( *((_BYTE *)v39 + 8) )
                  {
                    v41 = sub_180001870(v39);
                    if ( *(_DWORD *)(v41 + 1996) != v7 )
                      sub_18007FDD0(v41, "CASFBytewiseMediaSource::OnByteStreamEvent", 5176, (unsigned int)v7);
                  }
                  if ( byte_1801692C8 )
                  {
                    v9 = 434;
                    goto LABEL_173;
                  }
                }
                else
                {
                  v35 = (__int64 (__fastcall ***)())qword_180169350;
                  if ( !qword_180169350 )
                  {
                    v36 = MFGetCallStackTracingWeakReference(0, v34);
                    qword_180169350 = v36;
                    if ( v36 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
                    {
                      v35 = (__int64 (__fastcall ***)())qword_180169350;
                    }
                    else
                    {
                      v35 = &off_1801683B0;
                      qword_180169350 = (__int64)&off_1801683B0;
                    }
                  }
                  if ( *((_BYTE *)v35 + 8) )
                  {
                    v37 = sub_180001870(v35);
                    if ( *(_DWORD *)(v37 + 1996) != v7 )
                      sub_18007FDD0(v37, "CASFBytewiseMediaSource::OnByteStreamEvent", 5166, (unsigned int)v7);
                  }
                  if ( byte_1801692C8 )
                  {
                    v9 = 433;
                    goto LABEL_173;
                  }
                }
              }
              else
              {
                v31 = (__int64 (__fastcall ***)())qword_180169350;
                if ( !qword_180169350 )
                {
                  v32 = MFGetCallStackTracingWeakReference(0, v30);
                  qword_180169350 = v32;
                  if ( v32 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
                  {
                    v31 = (__int64 (__fastcall ***)())qword_180169350;
                  }
                  else
                  {
                    v31 = &off_1801683B0;
                    qword_180169350 = (__int64)&off_1801683B0;
                  }
                }
                if ( *((_BYTE *)v31 + 8) )
                {
                  v33 = sub_180001870(v31);
                  if ( *(_DWORD *)(v33 + 1996) != v7 )
                    sub_18007FDD0(v33, "CASFBytewiseMediaSource::OnByteStreamEvent", 5162, (unsigned int)v7);
                }
                if ( byte_1801692C8 )
                {
                  v9 = 432;
                  goto LABEL_173;
                }
              }
            }
            else
            {
              v27 = (__int64 (__fastcall ***)())qword_180169350;
              if ( !qword_180169350 )
              {
                v28 = MFGetCallStackTracingWeakReference(0, v26);
                qword_180169350 = v28;
                if ( v28 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
                {
                  v27 = (__int64 (__fastcall ***)())qword_180169350;
                }
                else
                {
                  v27 = &off_1801683B0;
                  qword_180169350 = (__int64)&off_1801683B0;
                }
              }
              if ( *((_BYTE *)v27 + 8) )
              {
                v29 = sub_180001870(v27);
                if ( *(_DWORD *)(v29 + 1996) != v7 )
                  sub_18007FDD0(v29, "CASFBytewiseMediaSource::OnByteStreamEvent", 5159, (unsigned int)v7);
              }
              if ( byte_1801692C8 )
              {
                v9 = 431;
                goto LABEL_173;
              }
            }
          }
          else
          {
            v23 = (__int64 (__fastcall ***)())qword_180169350;
            if ( !qword_180169350 )
            {
              v24 = MFGetCallStackTracingWeakReference(0, v22);
              qword_180169350 = v24;
              if ( v24 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
              {
                v23 = (__int64 (__fastcall ***)())qword_180169350;
              }
              else
              {
                v23 = &off_1801683B0;
                qword_180169350 = (__int64)&off_1801683B0;
              }
            }
            if ( *((_BYTE *)v23 + 8) )
            {
              v25 = sub_180001870(v23);
              if ( *(_DWORD *)(v25 + 1996) != v7 )
                sub_18007FDD0(v25, "CASFBytewiseMediaSource::OnByteStreamEvent", 5156, (unsigned int)v7);
            }
            if ( byte_1801692C8 )
            {
              v9 = 430;
              goto LABEL_173;
            }
          }
        }
        else
        {
          v19 = (__int64 (__fastcall ***)())qword_180169350;
          if ( !qword_180169350 )
          {
            v20 = MFGetCallStackTracingWeakReference(0, v18);
            qword_180169350 = v20;
            if ( v20 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
            {
              v19 = (__int64 (__fastcall ***)())qword_180169350;
            }
            else
            {
              v19 = &off_1801683B0;
              qword_180169350 = (__int64)&off_1801683B0;
            }
          }
          if ( *((_BYTE *)v19 + 8) )
          {
            v21 = sub_180001870(v19);
            if ( *(_DWORD *)(v21 + 1996) != v7 )
              sub_18007FDD0(v21, "CASFBytewiseMediaSource::OnByteStreamEvent", 5153, (unsigned int)v7);
          }
          if ( byte_1801692C8 )
          {
            v9 = 429;
            goto LABEL_173;
          }
        }
      }
      else
      {
        v15 = (__int64 (__fastcall ***)())qword_180169350;
        if ( !qword_180169350 )
        {
          v16 = MFGetCallStackTracingWeakReference(0, v14);
          qword_180169350 = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 (__fastcall ***)())qword_180169350;
          }
          else
          {
            v15 = &off_1801683B0;
            qword_180169350 = (__int64)&off_1801683B0;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = sub_180001870(v15);
          if ( *(_DWORD *)(v17 + 1996) != v7 )
            sub_18007FDD0(v17, "CASFBytewiseMediaSource::OnByteStreamEvent", 5150, (unsigned int)v7);
        }
        if ( byte_1801692C8 )
        {
          v9 = 428;
          goto LABEL_173;
        }
      }
    }
    else
    {
      v11 = (__int64 (__fastcall ***)())qword_180169350;
      if ( !qword_180169350 )
      {
        v12 = MFGetCallStackTracingWeakReference(0, v10);
        qword_180169350 = v12;
        if ( v12 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
        {
          v11 = (__int64 (__fastcall ***)())qword_180169350;
        }
        else
        {
          v11 = &off_1801683B0;
          qword_180169350 = (__int64)&off_1801683B0;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v13 = sub_180001870(v11);
        if ( *(_DWORD *)(v13 + 1996) != v7 )
          sub_18007FDD0(v13, "CASFBytewiseMediaSource::OnByteStreamEvent", 5147, (unsigned int)v7);
      }
      if ( byte_1801692C8 )
      {
        v9 = 427;
        goto LABEL_173;
      }
    }
  }
  else
  {
    v5 = (__int64 (__fastcall ***)())qword_180169350;
    if ( !qword_180169350 )
    {
      v6 = MFGetCallStackTracingWeakReference(0, v4);
      qword_180169350 = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 (__fastcall ***)())qword_180169350;
      }
      else
      {
        v5 = &off_1801683B0;
        qword_180169350 = (__int64)&off_1801683B0;
      }
    }
    v7 = -2147024809;
    if ( *((_BYTE *)v5 + 8) )
    {
      v8 = sub_180001870(v5);
      if ( *(_DWORD *)(v8 + 1996) != -2147024809 )
        sub_18007FDD0(v8, "CASFBytewiseMediaSource::OnByteStreamEvent", 5144, 2147942487LL);
    }
    if ( byte_1801692C8 )
    {
      v9 = 426;
LABEL_173:
      sub_18004F390(*((_QWORD *)RequestContext + 2), v9, &stru_180156148, a1, v7);
    }
  }
LABEL_174:
  if ( ppEvent )
  {
    ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
    ppEvent = 0;
  }
  if ( v71 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
    v71 = 0;
  }
  if ( v73 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
    v73 = 0;
  }
  if ( v74 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    v74 = 0;
  }
  if ( v75 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    v75 = 0;
  }
  DestroyPropVariant(&v79);
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 704));
  return sub_180005880(v70);
}

```

## disassembly

```asm
0x1800bba8c  mov     [rsp-8+arg_10], rbx
0x1800bba91  mov     [rsp-8+arg_18], rsi
0x1800bba96  push    rbp
0x1800bba97  push    rdi
0x1800bba98  push    r12
0x1800bba9a  push    r14
0x1800bba9c  push    r15
0x1800bba9e  lea     rbp, [rsp-37h]
0x1800bbaa3  sub     rsp, 90h
0x1800bbaaa  mov     rax, cs:__security_cookie
0x1800bbab1  xor     rax, rsp
0x1800bbab4  mov     [rbp+57h+var_28], rax
0x1800bbab8  mov     rsi, rdx
0x1800bbabb  lea     r12, aCasfbytewiseme_77; "CASFBytewiseMediaSource::OnByteStreamEv"...
0x1800bbac2  mov     rbx, rcx
0x1800bbac5  mov     rdx, r12
0x1800bbac8  mov     r8d, 140Ah
0x1800bbace  lea     rcx, [rbp+57h+var_80]
0x1800bbad2  call    sub_18000A580
0x1800bbad7  xor     r15d, r15d
0x1800bbada  lea     r14, [rbx+2C0h]
0x1800bbae1  xorps   xmm0, xmm0
0x1800bbae4  mov     [rbp+57h+var_4C], r15d
0x1800bbae8  xor     eax, eax
0x1800bbaea  mov     [rbp+57h+var_68], r15
0x1800bbaee  mov     rcx, r14; lpCriticalSection
0x1800bbaf1  mov     [rbp+57h+var_30], rax
0x1800bbaf5  movups  [rbp+57h+var_40], xmm0
0x1800bbaf9  mov     [rbp+57h+var_60], r15
0x1800bbafd  mov     [rbp+57h+var_58], r15
0x1800bbb01  mov     [rbp+57h+var_78], r15
0x1800bbb05  mov     [rbp+57h+var_70], r15
0x1800bbb09  call    cs:EnterCriticalSection
0x1800bbb0f  test    rsi, rsi
0x1800bbb12  jnz     loc_1800BBBA9
0x1800bbb18  mov     rcx, cs:qword_180169350
0x1800bbb1f  test    rcx, rcx
0x1800bbb22  jnz     short loc_1800BBB66
0x1800bbb24  call    cs:MFGetCallStackTracingWeakReference
0x1800bbb2a  mov     cs:qword_180169350, rax
0x1800bbb31  mov     rcx, rax
0x1800bbb34  test    rax, rax
0x1800bbb37  jz      short loc_1800BBB58
0x1800bbb39  mov     rax, [rax]
0x1800bbb3c  mov     edx, 7F0h
0x1800bbb41  mov     rax, [rax+8]
0x1800bbb45  call    cs:__guard_dispatch_icall_fptr
0x1800bbb4b  test    eax, eax
0x1800bbb4d  jz      short loc_1800BBB58
0x1800bbb4f  mov     rcx, cs:qword_180169350
0x1800bbb56  jmp     short loc_1800BBB66
0x1800bbb58  lea     rcx, off_1801683B0
0x1800bbb5f  mov     cs:qword_180169350, rcx
0x1800bbb66  mov     edi, 80070057h
0x1800bbb6b  cmp     [rcx+8], r15b
0x1800bbb6f  jz      short loc_1800BBB92
0x1800bbb71  call    sub_180001870
0x1800bbb76  cmp     [rax+7CCh], edi
0x1800bbb7c  jz      short loc_1800BBB92
0x1800bbb7e  mov     r9d, edi
0x1800bbb81  mov     r8d, 1418h
0x1800bbb87  mov     rdx, r12
0x1800bbb8a  mov     rcx, rax
0x1800bbb8d  call    sub_18007FDD0
0x1800bbb92  cmp     cs:byte_1801692C8, 1
0x1800bbb99  jb      loc_1800BC5C3
0x1800bbb9f  mov     edx, 1AAh
0x1800bbba4  jmp     loc_1800BC5A5
0x1800bbba9  mov     rax, [rsi]
0x1800bbbac  lea     rdx, [rbp+57h+var_58]
0x1800bbbb0  mov     rcx, rsi
0x1800bbbb3  mov     rax, [rax+18h]
0x1800bbbb7  call    cs:__guard_dispatch_icall_fptr
0x1800bbbbd  mov     edi, eax
0x1800bbbbf  test    eax, eax
0x1800bbbc1  jns     loc_1800BBC53
0x1800bbbc7  mov     rcx, cs:qword_180169350
0x1800bbbce  test    rcx, rcx
0x1800bbbd1  jnz     short loc_1800BBC15
0x1800bbbd3  call    cs:MFGetCallStackTracingWeakReference
0x1800bbbd9  mov     cs:qword_180169350, rax
0x1800bbbe0  mov     rcx, rax
0x1800bbbe3  test    rax, rax
0x1800bbbe6  jz      short loc_1800BBC07
0x1800bbbe8  mov     rax, [rax]
0x1800bbbeb  mov     edx, 7F0h
0x1800bbbf0  mov     rax, [rax+8]
0x1800bbbf4  call    cs:__guard_dispatch_icall_fptr
0x1800bbbfa  test    eax, eax
0x1800bbbfc  jz      short loc_1800BBC07
0x1800bbbfe  mov     rcx, cs:qword_180169350
0x1800bbc05  jmp     short loc_1800BBC15
0x1800bbc07  lea     rcx, off_1801683B0
0x1800bbc0e  mov     cs:qword_180169350, rcx
0x1800bbc15  cmp     [rcx+8], r15b
0x1800bbc19  jz      short loc_1800BBC3C
0x1800bbc1b  call    sub_180001870
0x1800bbc20  cmp     [rax+7CCh], edi
0x1800bbc26  jz      short loc_1800BBC3C
0x1800bbc28  mov     r9d, edi
0x1800bbc2b  mov     r8d, 141Bh
0x1800bbc31  mov     rdx, r12
0x1800bbc34  mov     rcx, rax
0x1800bbc37  call    sub_18007FDD0
0x1800bbc3c  cmp     cs:byte_1801692C8, 1
0x1800bbc43  jb      loc_1800BC5C3
0x1800bbc49  mov     edx, 1ABh
0x1800bbc4e  jmp     loc_1800BC5A5
0x1800bbc53  mov     rcx, [rbp+57h+var_58]
0x1800bbc57  lea     r8, [rbp+57h+var_60]
0x1800bbc5b  lea     rdx, qword_18014E790
0x1800bbc62  mov     rax, [rcx]
0x1800bbc65  mov     rax, [rax]
0x1800bbc68  call    cs:__guard_dispatch_icall_fptr
0x1800bbc6e  mov     edi, eax
0x1800bbc70  test    eax, eax
0x1800bbc72  jns     loc_1800BBD04
0x1800bbc78  mov     rcx, cs:qword_180169350
0x1800bbc7f  test    rcx, rcx
0x1800bbc82  jnz     short loc_1800BBCC6
0x1800bbc84  call    cs:MFGetCallStackTracingWeakReference
0x1800bbc8a  mov     cs:qword_180169350, rax
0x1800bbc91  mov     rcx, rax
0x1800bbc94  test    rax, rax
0x1800bbc97  jz      short loc_1800BBCB8
0x1800bbc99  mov     rax, [rax]
0x1800bbc9c  mov     edx, 7F0h
0x1800bbca1  mov     rax, [rax+8]
0x1800bbca5  call    cs:__guard_dispatch_icall_fptr
0x1800bbcab  test    eax, eax
0x1800bbcad  jz      short loc_1800BBCB8
0x1800bbcaf  mov     rcx, cs:qword_180169350
0x1800bbcb6  jmp     short loc_1800BBCC6
0x1800bbcb8  lea     rcx, off_1801683B0
0x1800bbcbf  mov     cs:qword_180169350, rcx
0x1800bbcc6  cmp     [rcx+8], r15b
0x1800bbcca  jz      short loc_1800BBCED
0x1800bbccc  call    sub_180001870
0x1800bbcd1  cmp     [rax+7CCh], edi
0x1800bbcd7  jz      short loc_1800BBCED
0x1800bbcd9  mov     r9d, edi
0x1800bbcdc  mov     r8d, 141Eh
0x1800bbce2  mov     rdx, r12
0x1800bbce5  mov     rcx, rax
0x1800bbce8  call    sub_18007FDD0
0x1800bbced  cmp     cs:byte_1801692C8, 1
0x1800bbcf4  jb      loc_1800BC5C3
0x1800bbcfa  mov     edx, 1ACh
0x1800bbcff  jmp     loc_1800BC5A5
0x1800bbd04  mov     rcx, [rbp+57h+var_60]
0x1800bbd08  lea     r8, [rbp+57h+var_68]
0x1800bbd0c  lea     rdx, qword_18014E780
0x1800bbd13  mov     rax, [rcx]
0x1800bbd16  mov     rax, [rax]
0x1800bbd19  call    cs:__guard_dispatch_icall_fptr
0x1800bbd1f  mov     edi, eax
0x1800bbd21  test    eax, eax
0x1800bbd23  jns     loc_1800BBDB5
0x1800bbd29  mov     rcx, cs:qword_180169350
0x1800bbd30  test    rcx, rcx
0x1800bbd33  jnz     short loc_1800BBD77
0x1800bbd35  call    cs:MFGetCallStackTracingWeakReference
0x1800bbd3b  mov     cs:qword_180169350, rax
0x1800bbd42  mov     rcx, rax
0x1800bbd45  test    rax, rax
0x1800bbd48  jz      short loc_1800BBD69
0x1800bbd4a  mov     rax, [rax]
0x1800bbd4d  mov     edx, 7F0h
0x1800bbd52  mov     rax, [rax+8]
0x1800bbd56  call    cs:__guard_dispatch_icall_fptr
0x1800bbd5c  test    eax, eax
0x1800bbd5e  jz      short loc_1800BBD69
0x1800bbd60  mov     rcx, cs:qword_180169350
0x1800bbd67  jmp     short loc_1800BBD77
0x1800bbd69  lea     rcx, off_1801683B0
0x1800bbd70  mov     cs:qword_180169350, rcx
0x1800bbd77  cmp     [rcx+8], r15b
0x1800bbd7b  jz      short loc_1800BBD9E
0x1800bbd7d  call    sub_180001870
0x1800bbd82  cmp     [rax+7CCh], edi
0x1800bbd88  jz      short loc_1800BBD9E
0x1800bbd8a  mov     r9d, edi
0x1800bbd8d  mov     r8d, 1421h
0x1800bbd93  mov     rdx, r12
0x1800bbd96  mov     rcx, rax
0x1800bbd99  call    sub_18007FDD0
0x1800bbd9e  cmp     cs:byte_1801692C8, 1
0x1800bbda5  jb      loc_1800BC5C3
0x1800bbdab  mov     edx, 1ADh
0x1800bbdb0  jmp     loc_1800BC5A5
0x1800bbdb5  mov     rcx, [rbp+57h+var_68]
0x1800bbdb9  lea     r8, [rbp+57h+var_78]
0x1800bbdbd  mov     rdx, rsi
0x1800bbdc0  mov     rax, [rcx]
0x1800bbdc3  mov     rax, [rax+28h]
0x1800bbdc7  call    cs:__guard_dispatch_icall_fptr
0x1800bbdcd  mov     edi, eax
0x1800bbdcf  test    eax, eax
0x1800bbdd1  jns     loc_1800BBE63
0x1800bbdd7  mov     rcx, cs:qword_180169350
0x1800bbdde  test    rcx, rcx
0x1800bbde1  jnz     short loc_1800BBE25
0x1800bbde3  call    cs:MFGetCallStackTracingWeakReference
0x1800bbde9  mov     cs:qword_180169350, rax
0x1800bbdf0  mov     rcx, rax
0x1800bbdf3  test    rax, rax
0x1800bbdf6  jz      short loc_1800BBE17
0x1800bbdf8  mov     rax, [rax]
0x1800bbdfb  mov     edx, 7F0h
0x1800bbe00  mov     rax, [rax+8]
0x1800bbe04  call    cs:__guard_dispatch_icall_fptr
0x1800bbe0a  test    eax, eax
0x1800bbe0c  jz      short loc_1800BBE17
0x1800bbe0e  mov     rcx, cs:qword_180169350
0x1800bbe15  jmp     short loc_1800BBE25
0x1800bbe17  lea     rcx, off_1801683B0
0x1800bbe1e  mov     cs:qword_180169350, rcx
0x1800bbe25  cmp     [rcx+8], r15b
0x1800bbe29  jz      short loc_1800BBE4C
0x1800bbe2b  call    sub_180001870
0x1800bbe30  cmp     [rax+7CCh], edi
0x1800bbe36  jz      short loc_1800BBE4C
0x1800bbe38  mov     r9d, edi
0x1800bbe3b  mov     r8d, 1424h
0x1800bbe41  mov     rdx, r12
0x1800bbe44  mov     rcx, rax
0x1800bbe47  call    sub_18007FDD0
0x1800bbe4c  cmp     cs:byte_1801692C8, 1
0x1800bbe53  jb      loc_1800BC5C3
0x1800bbe59  mov     edx, 1AEh
0x1800bbe5e  jmp     loc_1800BC5A5
0x1800bbe63  mov     rcx, [rbp+57h+var_78]
0x1800bbe67  lea     rdx, [rbp+57h+var_4C]
0x1800bbe6b  mov     rax, [rcx]
0x1800bbe6e  mov     rax, [rax+108h]
0x1800bbe75  call    cs:__guard_dispatch_icall_fptr
0x1800bbe7b  mov     edi, eax
0x1800bbe7d  test    eax, eax
0x1800bbe7f  jns     loc_1800BBF11
0x1800bbe85  mov     rcx, cs:qword_180169350
0x1800bbe8c  test    rcx, rcx
0x1800bbe8f  jnz     short loc_1800BBED3
0x1800bbe91  call    cs:MFGetCallStackTracingWeakReference
0x1800bbe97  mov     cs:qword_180169350, rax
0x1800bbe9e  mov     rcx, rax
0x1800bbea1  test    rax, rax
0x1800bbea4  jz      short loc_1800BBEC5
0x1800bbea6  mov     rax, [rax]
0x1800bbea9  mov     edx, 7F0h
0x1800bbeae  mov     rax, [rax+8]
0x1800bbeb2  call    cs:__guard_dispatch_icall_fptr
0x1800bbeb8  test    eax, eax
0x1800bbeba  jz      short loc_1800BBEC5
0x1800bbebc  mov     rcx, cs:qword_180169350
0x1800bbec3  jmp     short loc_1800BBED3
0x1800bbec5  lea     rcx, off_1801683B0
0x1800bbecc  mov     cs:qword_180169350, rcx
0x1800bbed3  cmp     [rcx+8], r15b
0x1800bbed7  jz      short loc_1800BBEFA
0x1800bbed9  call    sub_180001870
0x1800bbede  cmp     [rax+7CCh], edi
0x1800bbee4  jz      short loc_1800BBEFA
0x1800bbee6  mov     r9d, edi
0x1800bbee9  mov     r8d, 1427h
0x1800bbeef  mov     rdx, r12
0x1800bbef2  mov     rcx, rax
0x1800bbef5  call    sub_18007FDD0
0x1800bbefa  cmp     cs:byte_1801692C8, 1
0x1800bbf01  jb      loc_1800BC5C3
0x1800bbf07  mov     edx, 1AFh
0x1800bbf0c  jmp     loc_1800BC5A5
0x1800bbf11  mov     rcx, [rbp+57h+var_78]
0x1800bbf15  lea     rdx, [rbp+57h+var_40]
0x1800bbf19  mov     rax, [rcx]
0x1800bbf1c  mov     rax, [rax+120h]
0x1800bbf23  call    cs:__guard_dispatch_icall_fptr
0x1800bbf29  mov     edi, eax
0x1800bbf2b  test    eax, eax
0x1800bbf2d  jns     loc_1800BBFBF
0x1800bbf33  mov     rcx, cs:qword_180169350
0x1800bbf3a  test    rcx, rcx
0x1800bbf3d  jnz     short loc_1800BBF81
0x1800bbf3f  call    cs:MFGetCallStackTracingWeakReference
0x1800bbf45  mov     cs:qword_180169350, rax
0x1800bbf4c  mov     rcx, rax
0x1800bbf4f  test    rax, rax
0x1800bbf52  jz      short loc_1800BBF73
0x1800bbf54  mov     rax, [rax]
0x1800bbf57  mov     edx, 7F0h
0x1800bbf5c  mov     rax, [rax+8]
0x1800bbf60  call    cs:__guard_dispatch_icall_fptr
0x1800bbf66  test    eax, eax
0x1800bbf68  jz      short loc_1800BBF73
0x1800bbf6a  mov     rcx, cs:qword_180169350
0x1800bbf71  jmp     short loc_1800BBF81
0x1800bbf73  lea     rcx, off_1801683B0
0x1800bbf7a  mov     cs:qword_180169350, rcx
0x1800bbf81  cmp     [rcx+8], r15b
0x1800bbf85  jz      short loc_1800BBFA8
0x1800bbf87  call    sub_180001870
  ... truncated ...
```
