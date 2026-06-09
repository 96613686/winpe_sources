# Imapi2Utility::GetCurrentPhysicalMediaType(IDiscRecorder2Ex *,_IMAPI_MEDIA_PHYSICAL_TYPE *)

- ea: `0x180009b80`
- end: `0x18000a5e8`
- name: `?GetCurrentPhysicalMediaType@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAW4_IMAPI_MEDIA_PHYSICAL_TYPE@@@Z`
- size: `2664`
- prototype: `__int64 __fastcall(Imapi2Utility *__hidden this, struct IDiscRecorder2Ex *, enum _IMAPI_MEDIA_PHYSICAL_TYPE *)`
- caller_count: `16`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180009120`
- `0x180009640`
- `0x180009984`
- `0x180009ab8`
- `0x18000cc20`
- `0x18001dd30`
- `0x180021bc0`
- `0x180022550`
- `0x180022e8c`
- `0x180025dd0`
- `0x1800278b0`
- `0x1800301a8`
- `0x180031480`
- `0x1800389f0`
- `0x18003ab00`
- `0x180046bf4`

## callees

- `0x180009b80`
- `0x18000a5f0`
- `0x18000d604`
- `0x1800140f4`
- `0x180014134`
- `0x180016778`
- `0x180048f88`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180009d38`
- `ole32!CoTaskMemFree` at `0x180009dd5`
- `ole32!CoTaskMemFree` at `0x180009f6b`
- `ole32!CoTaskMemFree` at `0x18000a07e`
- `ole32!CoTaskMemFree` at `0x18000a191`
- `ole32!CoTaskMemFree` at `0x18000a211`
- `ole32!CoTaskMemFree` at `0x18000a378`
- `ole32!CoTaskMemFree` at `0x180009d38`
- `ole32!CoTaskMemFree` at `0x180009dd5`
- `ole32!CoTaskMemFree` at `0x180009f6b`
- `ole32!CoTaskMemFree` at `0x18000a07e`
- `ole32!CoTaskMemFree` at `0x18000a191`
- `ole32!CoTaskMemFree` at `0x18000a211`
- `ole32!CoTaskMemFree` at `0x18000a378`
- `KERNEL32!LocalFree` at `0x18000a5c7`
- `KERNEL32!LocalFree` at `0x18000a5c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Imapi2Utility::GetCurrentPhysicalMediaType(
        struct IDiscRecorder2Ex *this,
        struct IDiscRecorder2Ex *a2,
        enum _IMAPI_MEDIA_PHYSICAL_TYPE *a3)
{
  int v4; // eax
  int v5; // ebx
  PVOID *v6; // rcx
  int v7; // eax
  char v8; // di
  char v9; // r13
  char v10; // r15
  char v11; // si
  int v12; // eax
  int v13; // r14d
  int v14; // eax
  int v15; // r14d
  __int64 v16; // r8
  unsigned int v17; // edi
  char v18; // r14
  int v19; // eax
  __int64 v20; // r8
  int v21; // eax
  __int64 v22; // r8
  int v23; // eax
  __int64 v24; // rdx
  unsigned int *v25; // r9
  int PhysicalDvdStructure; // eax
  void *v27; // r15
  char v28; // al
  int v29; // eax
  __int64 v30; // r15
  PVOID *v31; // r8
  __int64 v32; // rdx
  HLOCAL hMem[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int8 *v35; // [rsp+80h] [rbp+40h] BYREF
  struct IDiscRecorder2Ex *v36; // [rsp+88h] [rbp+48h]
  LPVOID pv; // [rsp+90h] [rbp+50h] BYREF

  v36 = a2;
  v4 = 0;
  hMem[0] = 0;
  hMem[1] = 0;
  v5 = -2147467261;
  if ( this )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
      a2 = v36;
    }
    v4 = -2147467261;
  }
  if ( !a2 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 3u )
      WPP_SF_(v6[2], 15, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
    goto LABEL_201;
  }
  v5 = v4;
  LODWORD(a2->lpVtbl) = 0;
  if ( v4 >= 0 )
  {
    v7 = CMsftDiscInformation::Init((CMsftDiscInformation *)hMem, this);
    v5 = v7;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
          (unsigned int)v7);
      }
      goto LABEL_201;
    }
  }
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 1;
  if ( v5 >= 0 )
  {
    pv = 0;
    LODWORD(v35) = 0;
    v12 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, unsigned __int8 **))this->lpVtbl->GetFeaturePage)(
            this,
            31,
            0,
            &pv,
            &v35);
    v13 = v12;
    if ( v12 < 0 )
    {
      if ( (unsigned int)(v12 + 1062600182) > 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
            (unsigned int)v12);
        }
        v5 = v13;
      }
    }
    else
    {
      v9 = 1;
      v8 = *((_BYTE *)pv + 2) & 1;
    }
    CoTaskMemFree(pv);
    if ( v5 >= 0 )
    {
      pv = 0;
      LODWORD(v35) = 0;
      v14 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, unsigned __int8 **))this->lpVtbl->GetFeaturePage)(
              this,
              64,
              0,
              &pv,
              &v35);
      v15 = v14;
      if ( v14 < 0 )
      {
        if ( (unsigned int)(v14 + 1062600182) > 2 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
              (unsigned int)v14);
          }
          v5 = v15;
        }
      }
      else
      {
        v10 = *((_BYTE *)pv + 2) & 1;
      }
      CoTaskMemFree(pv);
      if ( v5 >= 0 )
      {
        if ( (*((_BYTE *)hMem[0] + 2) & 3) == 2 && (*((_BYTE *)hMem[0] + 2) & 0x10) == 0 )
        {
          if ( v10 )
            v17 = 17;
          else
            v17 = v8 != 0 ? 4 : 1;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v17);
          }
          goto LABEL_200;
        }
        v17 = 0;
        v18 = 0;
        pv = 0;
        LODWORD(v35) = 0;
        LOBYTE(v16) = 1;
        v19 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, __int64, LPVOID *, unsigned __int8 **))this->lpVtbl->GetFeaturePage)(
                this,
                42,
                v16,
                &pv,
                &v35);
        v5 = v19;
        if ( v19 != -1062600180 )
        {
          if ( (unsigned int)(v19 + 1062600182) > 1 )
          {
            if ( v19 >= 0 )
            {
              v18 = 1;
              v17 = 7;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, 7);
              }
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                21,
                &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                (unsigned int)v19);
            }
LABEL_63:
            CoTaskMemFree(pv);
            if ( v18 )
              goto LABEL_199;
            if ( v5 < 0 )
              goto LABEL_201;
            pv = 0;
            LODWORD(v35) = 0;
            LOBYTE(v20) = 1;
            v21 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, __int64, LPVOID *, unsigned __int8 **))this->lpVtbl->GetFeaturePage)(
                    this,
                    59,
                    v20,
                    &pv,
                    &v35);
            v5 = v21;
            if ( v21 != -1062600180 )
            {
              if ( (unsigned int)(v21 + 1062600182) > 1 )
              {
                if ( v21 >= 0 )
                {
                  v18 = 1;
                  v17 = 8;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      25,
                      &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                      8);
                  }
                }
                else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    24,
                    &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                    (unsigned int)v21);
                }
LABEL_81:
                CoTaskMemFree(pv);
                if ( v18 )
                  goto LABEL_199;
                if ( v5 < 0 )
                  goto LABEL_201;
                pv = 0;
                LODWORD(v35) = 0;
                LOBYTE(v22) = 1;
                v23 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, __int64, LPVOID *, unsigned __int8 **))this->lpVtbl->GetFeaturePage)(
                        this,
                        43,
                        v22,
                        &pv,
                        &v35);
                v5 = v23;
                if ( v23 != -1062600180 )
                {
                  if ( (unsigned int)(v23 + 1062600182) > 1 )
                  {
                    if ( v23 >= 0 )
                    {
                      v18 = 1;
                      v17 = 6;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          28,
                          &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                          6);
                      }
                    }
                    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        27,
                        &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                        (unsigned int)v23);
                    }
LABEL_99:
                    CoTaskMemFree(pv);
                    if ( v18 )
                      goto LABEL_199;
                    if ( v5 < 0 )
                      goto LABEL_201;
                    if ( !v9 )
                      goto LABEL_133;
                    pv = 0;
                    PhysicalDvdStructure = Imapi2Utility::GetPhysicalDvdStructure(
                                             (Imapi2Utility *)this,
                                             (struct IDiscRecorder2Ex *)&pv,
                                             &v35,
                                             v25);
                    v27 = pv;
                    if ( PhysicalDvdStructure < 0 )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          29,
                          &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                          (unsigned int)PhysicalDvdStructure);
                      }
                      goto LABEL_107;
                    }
                    v28 = *(_BYTE *)pv >> 4;
                    if ( v28 )
                    {
                      switch ( v28 )
                      {
                        case 1:
                          v17 = 5;
                          break;
                        case 2:
                          v17 = 11;
                          if ( (*((_BYTE *)pv + 2) & 0x60) != 0x20 )
                            v17 = 9;
                          break;
                        case 3:
                          v17 = 10;
                          break;
                        case 9:
                          v17 = 7;
                          break;
                        case 10:
                          v17 = 6;
                          break;
                        case 14:
                          v17 = 8;
                          break;
                        default:
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                          {
                            WPP_SF_Dd(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              30,
                              &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                              *(unsigned __int8 *)pv >> 4,
                              *(unsigned __int8 *)pv >> 4);
                          }
LABEL_107:
                          CoTaskMemFree(v27);
                          if ( v18 )
                          {
LABEL_200:
                            LODWORD(v36->lpVtbl) = v17;
                            goto LABEL_201;
                          }
LABEL_133:
                          pv = 0;
                          LODWORD(v35) = 0;
                          LOBYTE(v24) = 1;
                          v29 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, LPVOID *, unsigned __int8 **))this->lpVtbl->GetSupportedProfiles)(
                                  this,
                                  v24,
                                  &pv,
                                  &v35);
                          v5 = v29;
                          if ( v29 == -1062600180 )
                          {
                            v11 = 0;
                            v5 = 0;
                            goto LABEL_135;
                          }
                          if ( (unsigned int)(v29 + 1062600182) <= 1 )
                          {
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                            {
                              WPP_SF_(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                32,
                                &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
                            }
                            v5 = 0;
LABEL_135:
                            CoTaskMemFree(pv);
                            if ( !v18 && !v11 )
                            {
                              if ( v5 < 0 )
                                goto LABEL_201;
                              if ( (*((_BYTE *)hMem[0] + 2) & 0x10) != 0 )
                              {
                                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                                {
                                  WPP_SF_(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    35,
                                    &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
                                }
                                v17 = 3;
                              }
                              else
                              {
                                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                                {
                                  WPP_SF_(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    36,
                                    &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
                                }
                                v17 = 2;
                              }
                              goto LABEL_200;
                            }
LABEL_199:
                            if ( v5 < 0 )
                              goto LABEL_201;
                            goto LABEL_200;
                          }
                          if ( v29 < 0 )
                          {
                            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                33,
                                &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                                (unsigned int)v29);
                            }
                            goto LABEL_135;
                          }
                          v30 = 0;
                          v31 = (PVOID *)WPP_GLOBAL_Control;
                          while ( 1 )
                          {
                            if ( (unsigned int)v30 >= (unsigned int)v35 )
                              goto LABEL_135;
                            v32 = *((unsigned int *)pv + v30);
                            if ( (int)v32 > 19 )
                            {
                              switch ( (_DWORD)v32 )
                              {
                                case 0x14:
LABEL_182:
                                  v17 = 10;
                                  goto LABEL_183;
                                case 0x1A:
                                  v17 = 7;
                                  goto LABEL_183;
                                case 0x1B:
                                  v17 = 6;
                                  goto LABEL_183;
                                case 0x40:
                                  v17 = 17;
                                  goto LABEL_183;
                                case 0x41:
                                case 0x42:
                                  v17 = 18;
                                  goto LABEL_183;
                                case 0x43:
                                  v17 = 19;
                                  goto LABEL_183;
                              }
                            }
                            else
                            {
                              switch ( (_DWORD)v32 )
                              {
                                case 0x13:
                                  goto LABEL_182;
                                case 1:
                                case 2:
                                  v17 = 12;
                                  goto LABEL_183;
                                case 8:
                                  v17 = 1;
                                  goto LABEL_183;
                                case 9:
                                  v17 = 2;
                                  goto LABEL_183;
                                case 0xA:
                                  v17 = 3;
                                  goto LABEL_183;
                                case 0x10:
                                  v17 = 4;
                                  goto LABEL_183;
                                case 0x11:
                                  v17 = 9;
                                  goto LABEL_183;
                                case 0x12:
                                  v17 = 5;
LABEL_183:
                                  v18 = 1;
                                  if ( v31 != &WPP_GLOBAL_Control
                                    && (*((_BYTE *)v31 + 28) & 4) != 0
                                    && *((_BYTE *)v31 + 25) >= 4u )
                                  {
                                    WPP_SF_LL(v31[2], v32, v31, v17, *((_DWORD *)pv + v30));
                                    v31 = (PVOID *)WPP_GLOBAL_Control;
                                  }
                                  break;
                              }
                            }
                            v30 = (unsigned int)(v30 + 1);
                            if ( v18 )
                              goto LABEL_135;
                          }
                      }
                    }
                    else
                    {
                      v17 = 4;
                    }
                    v18 = 1;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        31,
                        &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                        v17);
                    }
                    goto LABEL_107;
                  }
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
                  }
                }
                v5 = 0;
                goto LABEL_99;
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
              }
            }
            v5 = 0;
            goto LABEL_81;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
          }
        }
        v5 = 0;
        goto LABEL_63;
      }
    }
  }
LABEL_201:
  if ( hMem[0] )
    LocalFree(hMem[0]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009b80  mov     [rsp-38h+arg_18], rbx
0x180009b85  mov     [rsp-38h+arg_8], rdx
0x180009b8a  push    rbp
0x180009b8b  push    rsi
0x180009b8c  push    rdi
0x180009b8d  push    r12
0x180009b8f  push    r13
0x180009b91  push    r14
0x180009b93  push    r15
0x180009b95  mov     rbp, rsp
0x180009b98  sub     rsp, 40h
0x180009b9c  mov     r12, rcx
0x180009b9f  xor     eax, eax
0x180009ba1  mov     [rbp+hMem], rax
0x180009ba5  mov     [rbp+var_8], rax
0x180009ba9  lea     rdi, WPP_GLOBAL_Control
0x180009bb0  lea     rsi, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180009bb7  mov     ebx, 80004003h
0x180009bbc  test    rcx, rcx
0x180009bbf  jnz     short loc_180009BF7
0x180009bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bc8  cmp     rcx, rdi
0x180009bcb  jz      short loc_180009BF3
0x180009bcd  test    byte ptr [rcx+1Ch], 4
0x180009bd1  jz      short loc_180009BF3
0x180009bd3  cmp     byte ptr [rcx+19h], 3
0x180009bd7  jb      short loc_180009BF3
0x180009bd9  lea     edx, [rax+0Eh]
0x180009bdc  mov     r8, rsi
0x180009bdf  mov     rcx, [rcx+10h]
0x180009be3  call    WPP_SF_
0x180009be8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bef  mov     rdx, [rbp+arg_8]
0x180009bf3  mov     eax, ebx
0x180009bf5  jmp     short loc_180009BFE
0x180009bf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bfe  test    rdx, rdx
0x180009c01  jnz     short loc_180009C36
0x180009c03  cmp     rcx, rdi
0x180009c06  jz      loc_18000A5BB
0x180009c0c  test    byte ptr [rcx+1Ch], 4
0x180009c10  jz      loc_18000A5BB
0x180009c16  cmp     byte ptr [rcx+19h], 3
0x180009c1a  jb      loc_18000A5BB
0x180009c20  mov     edx, 0Fh
0x180009c25  mov     r8, rsi
0x180009c28  mov     rcx, [rcx+10h]
0x180009c2c  call    WPP_SF_
0x180009c31  jmp     loc_18000A5BB
0x180009c36  mov     ebx, eax
0x180009c38  mov     dword ptr [rdx], 0
0x180009c3e  test    eax, eax
0x180009c40  js      short loc_180009C91
0x180009c42  mov     rdx, r12; struct IDiscRecorder2Ex *
0x180009c45  lea     rcx, [rbp+hMem]; this
0x180009c49  call    ?Init@CMsftDiscInformation@@QEAAJPEAUIDiscRecorder2Ex@@@Z; CMsftDiscInformation::Init(IDiscRecorder2Ex *)
0x180009c4e  mov     ebx, eax
0x180009c50  test    eax, eax
0x180009c52  jns     short loc_180009C91
0x180009c54  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c5b  cmp     rcx, rdi
0x180009c5e  jz      loc_18000A5BB
0x180009c64  test    byte ptr [rcx+1Ch], 4
0x180009c68  jz      loc_18000A5BB
0x180009c6e  cmp     byte ptr [rcx+19h], 3
0x180009c72  jb      loc_18000A5BB
0x180009c78  mov     edx, 10h
0x180009c7d  mov     r9d, eax
0x180009c80  mov     r8, rsi
0x180009c83  mov     rcx, [rcx+10h]
0x180009c87  call    WPP_SF_d
0x180009c8c  jmp     loc_18000A5BB
0x180009c91  xor     dil, dil
0x180009c94  xor     r13b, r13b
0x180009c97  xor     r15b, r15b
0x180009c9a  mov     esi, 1
0x180009c9f  test    ebx, ebx
0x180009ca1  js      loc_18000A5BB
0x180009ca7  mov     [rbp+pv], 0
0x180009caf  mov     dword ptr [rbp+arg_0], 0
0x180009cb6  mov     rax, [r12]
0x180009cba  lea     rcx, [rbp+arg_0]
0x180009cbe  mov     [rsp+40h+var_20], rcx
0x180009cc3  lea     r9, [rbp+pv]
0x180009cc7  xor     r8d, r8d
0x180009cca  lea     edx, [rsi+1Eh]
0x180009ccd  mov     rcx, r12
0x180009cd0  mov     rax, [rax+60h]
0x180009cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cd9  mov     r14d, eax
0x180009cdc  test    eax, eax
0x180009cde  js      short loc_180009CF0
0x180009ce0  mov     r13b, sil
0x180009ce3  mov     rax, [rbp+pv]
0x180009ce7  mov     dil, [rax+2]
0x180009ceb  and     dil, sil
0x180009cee  jmp     short loc_180009D34
0x180009cf0  add     eax, 3F55FDF6h
0x180009cf5  cmp     eax, 2
0x180009cf8  jbe     short loc_180009D34
0x180009cfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d01  lea     rdx, WPP_GLOBAL_Control
0x180009d08  cmp     rcx, rdx
0x180009d0b  jz      short loc_180009D31
0x180009d0d  test    byte ptr [rcx+1Ch], 4
0x180009d11  jz      short loc_180009D31
0x180009d13  cmp     byte ptr [rcx+19h], 3
0x180009d17  jb      short loc_180009D31
0x180009d19  mov     edx, 11h
0x180009d1e  mov     r9d, r14d
0x180009d21  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180009d28  mov     rcx, [rcx+10h]
0x180009d2c  call    WPP_SF_d
0x180009d31  mov     ebx, r14d
0x180009d34  mov     rcx, [rbp+pv]; pv
0x180009d38  call    cs:__imp_CoTaskMemFree
0x180009d3e  test    ebx, ebx
0x180009d40  js      loc_18000A5BB
0x180009d46  mov     [rbp+pv], 0
0x180009d4e  mov     dword ptr [rbp+arg_0], 0
0x180009d55  mov     rax, [r12]
0x180009d59  lea     rcx, [rbp+arg_0]
0x180009d5d  mov     [rsp+40h+var_20], rcx
0x180009d62  lea     r9, [rbp+pv]
0x180009d66  xor     r8d, r8d
0x180009d69  lea     edx, [r8+40h]
0x180009d6d  mov     rcx, r12
0x180009d70  mov     rax, [rax+60h]
0x180009d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d79  mov     r14d, eax
0x180009d7c  test    eax, eax
0x180009d7e  js      short loc_180009D8D
0x180009d80  mov     rax, [rbp+pv]
0x180009d84  mov     r15b, [rax+2]
0x180009d88  and     r15b, sil
0x180009d8b  jmp     short loc_180009DD1
0x180009d8d  add     eax, 3F55FDF6h
0x180009d92  cmp     eax, 2
0x180009d95  jbe     short loc_180009DD1
0x180009d97  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d9e  lea     rax, WPP_GLOBAL_Control
0x180009da5  cmp     rcx, rax
0x180009da8  jz      short loc_180009DCE
0x180009daa  test    byte ptr [rcx+1Ch], 4
0x180009dae  jz      short loc_180009DCE
0x180009db0  cmp     byte ptr [rcx+19h], 3
0x180009db4  jb      short loc_180009DCE
0x180009db6  mov     edx, 12h
0x180009dbb  mov     r9d, r14d
0x180009dbe  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180009dc5  mov     rcx, [rcx+10h]
0x180009dc9  call    WPP_SF_d
0x180009dce  mov     ebx, r14d
0x180009dd1  mov     rcx, [rbp+pv]; pv
0x180009dd5  call    cs:__imp_CoTaskMemFree
0x180009ddb  test    ebx, ebx
0x180009ddd  js      loc_18000A5BB
0x180009de3  mov     rcx, [rbp+hMem]
0x180009de7  mov     al, [rcx+2]
0x180009dea  and     al, 3
0x180009dec  cmp     al, 2
0x180009dee  jnz     short loc_180009E54
0x180009df0  test    byte ptr [rcx+2], 10h
0x180009df4  jnz     short loc_180009E54
0x180009df6  test    r15b, r15b
0x180009df9  jz      short loc_180009E02
0x180009dfb  mov     edi, 11h
0x180009e00  jmp     short loc_180009E0C
0x180009e02  neg     dil
0x180009e05  sbb     edi, edi
0x180009e07  and     edi, 3
0x180009e0a  add     edi, esi
0x180009e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e13  lea     rax, WPP_GLOBAL_Control
0x180009e1a  cmp     rcx, rax
0x180009e1d  jz      loc_18000A5B5
0x180009e23  test    byte ptr [rcx+1Ch], 4
0x180009e27  jz      loc_18000A5B5
0x180009e2d  cmp     byte ptr [rcx+19h], 4
0x180009e31  jb      loc_18000A5B5
0x180009e37  mov     edx, 13h
0x180009e3c  mov     r9d, edi
0x180009e3f  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180009e46  mov     rcx, [rcx+10h]
0x180009e4a  call    WPP_SF_d
0x180009e4f  jmp     loc_18000A5B5
0x180009e54  xor     edi, edi
0x180009e56  xor     r14b, r14b
0x180009e59  mov     [rbp+pv], rdi
0x180009e5d  mov     dword ptr [rbp+arg_0], edi
0x180009e60  mov     rax, [r12]
0x180009e64  lea     rcx, [rbp+arg_0]
0x180009e68  mov     [rsp+40h+var_20], rcx
0x180009e6d  lea     r9, [rbp+pv]
0x180009e71  mov     r8b, sil
0x180009e74  lea     edx, [rdi+2Ah]
0x180009e77  mov     rcx, r12
0x180009e7a  mov     rax, [rax+60h]
0x180009e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e83  mov     ebx, eax
0x180009e85  lea     r8d, [rdi+7]
0x180009e89  cmp     eax, 0C0AA020Ch
0x180009e8e  jnz     short loc_180009E9C
0x180009e90  lea     r15, WPP_GLOBAL_Control
0x180009e97  jmp     loc_180009F65
0x180009e9c  add     eax, 3F55FDF6h
0x180009ea1  cmp     eax, esi
0x180009ea3  jbe     loc_180009F31
0x180009ea9  test    ebx, ebx
0x180009eab  jns     short loc_180009EF2
0x180009ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180009eb4  lea     r15, WPP_GLOBAL_Control
0x180009ebb  cmp     rcx, r15
0x180009ebe  jz      loc_180009F67
0x180009ec4  test    byte ptr [rcx+1Ch], 4
0x180009ec8  jz      loc_180009F67
0x180009ece  cmp     byte ptr [rcx+19h], 3
0x180009ed2  jb      loc_180009F67
0x180009ed8  mov     edx, 15h
0x180009edd  mov     r9d, ebx
0x180009ee0  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180009ee7  mov     rcx, [rcx+10h]
0x180009eeb  call    WPP_SF_d
0x180009ef0  jmp     short loc_180009F67
0x180009ef2  mov     r14b, sil
0x180009ef5  mov     edi, r8d
0x180009ef8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009eff  lea     r15, WPP_GLOBAL_Control
0x180009f06  cmp     rcx, r15
0x180009f09  jz      short loc_180009F67
0x180009f0b  test    byte ptr [rcx+1Ch], 4
0x180009f0f  jz      short loc_180009F67
0x180009f11  cmp     byte ptr [rcx+19h], 4
0x180009f15  jb      short loc_180009F67
0x180009f17  mov     edx, 16h
0x180009f1c  mov     r9d, r8d
0x180009f1f  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180009f26  mov     rcx, [rcx+10h]
0x180009f2a  call    WPP_SF_d
0x180009f2f  jmp     short loc_180009F67
0x180009f31  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f38  lea     r15, WPP_GLOBAL_Control
0x180009f3f  cmp     rcx, r15
0x180009f42  jz      short loc_180009F65
0x180009f44  test    byte ptr [rcx+1Ch], 4
0x180009f48  jz      short loc_180009F65
0x180009f4a  cmp     byte ptr [rcx+19h], 5
0x180009f4e  jb      short loc_180009F65
0x180009f50  mov     edx, 14h
0x180009f55  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180009f5c  mov     rcx, [rcx+10h]
0x180009f60  call    WPP_SF_
0x180009f65  xor     ebx, ebx
0x180009f67  mov     rcx, [rbp+pv]; pv
0x180009f6b  call    cs:__imp_CoTaskMemFree
0x180009f71  test    r14b, r14b
0x180009f74  jnz     loc_18000A5B1
0x180009f7a  test    ebx, ebx
0x180009f7c  js      loc_18000A5BB
0x180009f82  mov     [rbp+pv], 0
0x180009f8a  mov     dword ptr [rbp+arg_0], 0
0x180009f91  mov     rax, [r12]
0x180009f95  lea     rcx, [rbp+arg_0]
0x180009f99  mov     [rsp+40h+var_20], rcx
0x180009f9e  lea     r9, [rbp+pv]
0x180009fa2  mov     r8b, sil
0x180009fa5  mov     edx, 3Bh ; ';'
0x180009faa  mov     rcx, r12
0x180009fad  mov     rax, [rax+60h]
0x180009fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fb6  mov     ebx, eax
0x180009fb8  mov     r8d, 8
0x180009fbe  cmp     eax, 0C0AA020Ch
0x180009fc3  jz      loc_18000A078
0x180009fc9  add     eax, 3F55FDF6h
0x180009fce  cmp     eax, esi
0x180009fd0  jbe     short loc_18000A04B
0x180009fd2  test    ebx, ebx
0x180009fd4  jns     short loc_18000A013
0x180009fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180009fdd  cmp     rcx, r15
0x180009fe0  jz      loc_18000A07A
0x180009fe6  test    byte ptr [rcx+1Ch], 4
0x180009fea  jz      loc_18000A07A
0x180009ff0  cmp     byte ptr [rcx+19h], 3
0x180009ff4  jb      loc_18000A07A
0x180009ffa  lea     edx, [r8+10h]
0x180009ffe  mov     r9d, ebx
0x18000a001  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x18000a008  mov     rcx, [rcx+10h]
0x18000a00c  call    WPP_SF_d
0x18000a011  jmp     short loc_18000A07A
0x18000a013  mov     r14b, sil
0x18000a016  mov     edi, r8d
0x18000a019  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a020  cmp     rcx, r15
0x18000a023  jz      short loc_18000A07A
0x18000a025  test    byte ptr [rcx+1Ch], 4
0x18000a029  jz      short loc_18000A07A
0x18000a02b  cmp     byte ptr [rcx+19h], 4
  ... truncated ...
```
