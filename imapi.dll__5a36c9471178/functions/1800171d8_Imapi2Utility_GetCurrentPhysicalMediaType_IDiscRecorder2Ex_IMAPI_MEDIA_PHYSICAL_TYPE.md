# Imapi2Utility::GetCurrentPhysicalMediaType(IDiscRecorder2Ex *,_IMAPI_MEDIA_PHYSICAL_TYPE *)

- ea: `0x1800171d8`
- end: `0x180017c5a`
- name: `?GetCurrentPhysicalMediaType@Imapi2Utility@@YAJPEAUIDiscRecorder2Ex@@PEAW4_IMAPI_MEDIA_PHYSICAL_TYPE@@@Z`
- size: `2690`
- prototype: `__int64 __fastcall(struct IDiscRecorder2Ex *this, struct IDiscRecorder2Ex *, enum _IMAPI_MEDIA_PHYSICAL_TYPE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180014288`

## callees

- `0x180007bac`
- `0x180007bd4`
- `0x1800171d8`
- `0x180017c60`
- `0x180017e00`
- `0x180017e54`
- `0x180017f24`
- `0x180017f58`
- `0x180019010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180017393`
- `ole32!CoTaskMemFree` at `0x180017433`
- `ole32!CoTaskMemFree` at `0x1800175c7`
- `ole32!CoTaskMemFree` at `0x1800176ed`
- `ole32!CoTaskMemFree` at `0x180017813`
- `ole32!CoTaskMemFree` at `0x18001788f`
- `ole32!CoTaskMemFree` at `0x1800179e7`
- `ole32!CoTaskMemFree` at `0x180017393`
- `ole32!CoTaskMemFree` at `0x180017433`
- `ole32!CoTaskMemFree` at `0x1800175c7`
- `ole32!CoTaskMemFree` at `0x1800176ed`
- `ole32!CoTaskMemFree` at `0x180017813`
- `ole32!CoTaskMemFree` at `0x18001788f`
- `ole32!CoTaskMemFree` at `0x1800179e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Imapi2Utility::GetCurrentPhysicalMediaType(
        struct IDiscRecorder2Ex *this,
        struct IDiscRecorder2Ex *a2,
        enum _IMAPI_MEDIA_PHYSICAL_TYPE *a3)
{
  int v4; // eax
  int v5; // ebx
  _QWORD *v6; // rcx
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
  unsigned int v18; // r15d
  char v19; // r14
  int v20; // eax
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // r8
  int v24; // eax
  __int64 v25; // rdx
  unsigned int *v26; // r9
  int PhysicalDvdStructure; // eax
  void *v28; // r15
  char v29; // al
  int v30; // eax
  _QWORD *v31; // r8
  __int64 v32; // rdx
  _QWORD v34[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int8 *v35; // [rsp+80h] [rbp+40h] BYREF
  struct IDiscRecorder2Ex *v36; // [rsp+88h] [rbp+48h]
  LPVOID pv; // [rsp+90h] [rbp+50h] BYREF

  v36 = a2;
  v4 = 0;
  v34[0] = 0;
  v34[1] = 0;
  v5 = -2147467261;
  if ( this )
  {
    v6 = WPP_GLOBAL_Control;
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
      v6 = WPP_GLOBAL_Control;
      a2 = v36;
    }
    v4 = -2147467261;
  }
  if ( !a2 )
  {
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 4) != 0 && *((_BYTE *)v6 + 25) >= 3u )
      WPP_SF_(v6[2], 15, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
    goto LABEL_200;
  }
  v5 = v4;
  LODWORD(a2->lpVtbl) = 0;
  if ( v4 >= 0 )
  {
    v7 = CMsftDiscInformation::Init((CMsftDiscInformation *)v34, this);
    v5 = v7;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
          (unsigned int)v7);
      }
      goto LABEL_200;
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
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
        if ( (*(_BYTE *)(v34[0] + 2LL) & 3) == 2 && (*(_BYTE *)(v34[0] + 2LL) & 0x10) == 0 )
        {
          if ( v10 )
            v17 = 17;
          else
            v17 = v8 != 0 ? 4 : 1;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, v17);
          }
          goto LABEL_199;
        }
        v18 = 0;
        v17 = 0;
        v19 = 0;
        pv = 0;
        LODWORD(v35) = 0;
        LOBYTE(v16) = 1;
        v20 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, __int64, LPVOID *, unsigned __int8 **))this->lpVtbl->GetFeaturePage)(
                this,
                42,
                v16,
                &pv,
                &v35);
        v5 = v20;
        if ( v20 != -1062600180 )
        {
          if ( (unsigned int)(v20 + 1062600182) > 1 )
          {
            if ( v20 >= 0 )
            {
              v19 = 1;
              v17 = 7;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids, 7);
              }
            }
            else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                21,
                &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                (unsigned int)v20);
            }
LABEL_63:
            CoTaskMemFree(pv);
            if ( v19 )
              goto LABEL_198;
            if ( v5 < 0 )
              goto LABEL_200;
            pv = 0;
            LODWORD(v35) = 0;
            LOBYTE(v21) = 1;
            v22 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, __int64, LPVOID *, unsigned __int8 **))this->lpVtbl->GetFeaturePage)(
                    this,
                    59,
                    v21,
                    &pv,
                    &v35);
            v5 = v22;
            if ( v22 != -1062600180 )
            {
              if ( (unsigned int)(v22 + 1062600182) > 1 )
              {
                if ( v22 >= 0 )
                {
                  v19 = 1;
                  v17 = 8;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
                else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                       && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                       && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    24,
                    &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                    (unsigned int)v22);
                }
LABEL_81:
                CoTaskMemFree(pv);
                if ( v19 )
                  goto LABEL_198;
                if ( v5 < 0 )
                  goto LABEL_200;
                pv = 0;
                LODWORD(v35) = 0;
                LOBYTE(v23) = 1;
                v24 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, __int64, LPVOID *, unsigned __int8 **))this->lpVtbl->GetFeaturePage)(
                        this,
                        43,
                        v23,
                        &pv,
                        &v35);
                v5 = v24;
                if ( v24 != -1062600180 )
                {
                  if ( (unsigned int)(v24 + 1062600182) > 1 )
                  {
                    if ( v24 >= 0 )
                    {
                      v19 = 1;
                      v17 = 6;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
                    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        27,
                        &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                        (unsigned int)v24);
                    }
LABEL_99:
                    CoTaskMemFree(pv);
                    if ( v19 )
                      goto LABEL_198;
                    if ( v5 < 0 )
                      goto LABEL_200;
                    if ( !v9 )
                      goto LABEL_133;
                    pv = 0;
                    PhysicalDvdStructure = Imapi2Utility::GetPhysicalDvdStructure(
                                             (Imapi2Utility *)this,
                                             (struct IDiscRecorder2Ex *)&pv,
                                             &v35,
                                             v26);
                    v28 = pv;
                    if ( PhysicalDvdStructure < 0 )
                    {
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
                    v29 = *(_BYTE *)pv >> 4;
                    if ( v29 )
                    {
                      switch ( v29 )
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
                          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                          {
                            WPP_SF_dD(*((_QWORD *)WPP_GLOBAL_Control + 2));
                          }
LABEL_107:
                          CoTaskMemFree(v28);
                          v18 = 0;
                          if ( v19 )
                            goto LABEL_199;
LABEL_133:
                          pv = 0;
                          LODWORD(v35) = 0;
                          LOBYTE(v25) = 1;
                          v30 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, LPVOID *, unsigned __int8 **))this->lpVtbl->GetSupportedProfiles)(
                                  this,
                                  v25,
                                  &pv,
                                  &v35);
                          v5 = v30;
                          if ( v30 == -1062600180 )
                          {
                            v11 = 0;
                            v5 = 0;
                            goto LABEL_135;
                          }
                          if ( (unsigned int)(v30 + 1062600182) <= 1 )
                          {
                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
                            if ( !v19 && !v11 )
                            {
                              if ( v5 < 0 )
                                goto LABEL_200;
                              if ( (*(_BYTE *)(v34[0] + 2LL) & 0x10) != 0 )
                              {
                                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
                                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
LABEL_199:
                              LODWORD(v36->lpVtbl) = v17;
                              goto LABEL_200;
                            }
LABEL_198:
                            if ( v5 < 0 )
                              goto LABEL_200;
                            goto LABEL_199;
                          }
                          if ( v30 < 0 )
                          {
                            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
                            {
                              WPP_SF_d(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                33,
                                &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids,
                                (unsigned int)v30);
                            }
                            goto LABEL_135;
                          }
                          v31 = WPP_GLOBAL_Control;
                          while ( 1 )
                          {
                            if ( v18 >= (unsigned int)v35 )
                              goto LABEL_135;
                            v32 = *((unsigned int *)pv + v18);
                            if ( (int)v32 > 19 )
                            {
                              switch ( (_DWORD)v32 )
                              {
                                case 0x14:
LABEL_183:
                                  v17 = 10;
                                  goto LABEL_184;
                                case 0x1A:
                                  v17 = 7;
                                  goto LABEL_184;
                                case 0x1B:
                                  v17 = 6;
                                  goto LABEL_184;
                                case 0x40:
                                  v17 = 17;
                                  goto LABEL_184;
                                case 0x41:
                                case 0x42:
                                  v17 = 18;
                                  goto LABEL_184;
                                case 0x43:
                                  v17 = 19;
                                  goto LABEL_184;
                              }
                            }
                            else
                            {
                              switch ( (_DWORD)v32 )
                              {
                                case 0x13:
                                  goto LABEL_183;
                                case 1:
                                case 2:
                                  v17 = 12;
                                  goto LABEL_184;
                                case 8:
                                  v17 = 1;
                                  goto LABEL_184;
                                case 9:
                                  v17 = 2;
                                  goto LABEL_184;
                                case 0xA:
                                  v17 = 3;
                                  goto LABEL_184;
                                case 0x10:
                                  v17 = 4;
                                  goto LABEL_184;
                                case 0x11:
                                  v17 = 9;
                                  goto LABEL_184;
                                case 0x12:
                                  v17 = 5;
LABEL_184:
                                  v19 = 1;
                                  if ( v31 != &WPP_GLOBAL_Control
                                    && (*((_BYTE *)v31 + 28) & 4) != 0
                                    && *((_BYTE *)v31 + 25) >= 4u )
                                  {
                                    WPP_SF_LL(v31[2], v32, v31, v17, *((_DWORD *)pv + v18));
                                    v31 = WPP_GLOBAL_Control;
                                  }
                                  break;
                              }
                            }
                            ++v18;
                            if ( v19 )
                              goto LABEL_135;
                          }
                      }
                    }
                    else
                    {
                      v17 = 4;
                    }
                    v19 = 1;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
                  }
                }
                v5 = 0;
                goto LABEL_99;
              }
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids);
              }
            }
            v5 = 0;
            goto LABEL_81;
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
LABEL_200:
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)v34);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800171d8  mov     [rsp-38h+arg_18], rbx
0x1800171dd  mov     [rsp-38h+arg_8], rdx
0x1800171e2  push    rbp
0x1800171e3  push    rsi
0x1800171e4  push    rdi
0x1800171e5  push    r12
0x1800171e7  push    r13
0x1800171e9  push    r14
0x1800171eb  push    r15
0x1800171ed  mov     rbp, rsp
0x1800171f0  sub     rsp, 40h
0x1800171f4  mov     r12, rcx
0x1800171f7  xor     r14d, r14d
0x1800171fa  mov     eax, r14d
0x1800171fd  mov     [rbp+var_10], r14
0x180017201  mov     [rbp+var_8], r14
0x180017205  lea     rdi, WPP_GLOBAL_Control
0x18001720c  lea     rsi, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180017213  mov     ebx, 80004003h
0x180017218  test    rcx, rcx
0x18001721b  jnz     short loc_180017255
0x18001721d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017224  cmp     rcx, rdi
0x180017227  jz      short loc_180017251
0x180017229  test    byte ptr [rcx+1Ch], 4
0x18001722d  jz      short loc_180017251
0x18001722f  cmp     byte ptr [rcx+19h], 3
0x180017233  jb      short loc_180017251
0x180017235  lea     edx, [r12+0Eh]
0x18001723a  mov     r8, rsi
0x18001723d  mov     rcx, [rcx+10h]
0x180017241  call    WPP_SF_
0x180017246  mov     rcx, cs:WPP_GLOBAL_Control
0x18001724d  mov     rdx, [rbp+arg_8]
0x180017251  mov     eax, ebx
0x180017253  jmp     short loc_18001725C
0x180017255  mov     rcx, cs:WPP_GLOBAL_Control
0x18001725c  test    rdx, rdx
0x18001725f  jnz     short loc_180017294
0x180017261  cmp     rcx, rdi
0x180017264  jz      loc_180017C37
0x18001726a  test    byte ptr [rcx+1Ch], 4
0x18001726e  jz      loc_180017C37
0x180017274  cmp     byte ptr [rcx+19h], 3
0x180017278  jb      loc_180017C37
0x18001727e  mov     edx, 0Fh
0x180017283  mov     r8, rsi
0x180017286  mov     rcx, [rcx+10h]
0x18001728a  call    WPP_SF_
0x18001728f  jmp     loc_180017C37
0x180017294  mov     ebx, eax
0x180017296  mov     [rdx], r14d
0x180017299  test    eax, eax
0x18001729b  js      short loc_1800172F3
0x18001729d  mov     rdx, r12; struct IDiscRecorder2Ex *
0x1800172a0  lea     rcx, [rbp+var_10]; this
0x1800172a4  call    ?Init@CMsftDiscInformation@@QEAAJPEAUIDiscRecorder2Ex@@@Z; CMsftDiscInformation::Init(IDiscRecorder2Ex *)
0x1800172a9  mov     ebx, eax
0x1800172ab  test    eax, eax
0x1800172ad  jns     short loc_1800172EC
0x1800172af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800172b6  cmp     rcx, rdi
0x1800172b9  jz      loc_180017C37
0x1800172bf  test    byte ptr [rcx+1Ch], 4
0x1800172c3  jz      loc_180017C37
0x1800172c9  cmp     byte ptr [rcx+19h], 3
0x1800172cd  jb      loc_180017C37
0x1800172d3  mov     edx, 10h
0x1800172d8  mov     r9d, eax
0x1800172db  mov     r8, rsi
0x1800172de  mov     rcx, [rcx+10h]
0x1800172e2  call    WPP_SF_d
0x1800172e7  jmp     loc_180017C37
0x1800172ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800172f3  mov     dil, r14b
0x1800172f6  mov     r13b, r14b
0x1800172f9  mov     r15b, r14b
0x1800172fc  mov     esi, 1
0x180017301  test    ebx, ebx
0x180017303  js      loc_180017C37
0x180017309  mov     [rbp+pv], r14
0x18001730d  mov     dword ptr [rbp+arg_0], r14d
0x180017311  mov     rax, [r12]
0x180017315  lea     rcx, [rbp+arg_0]
0x180017319  mov     [rsp+40h+var_20], rcx
0x18001731e  lea     r9, [rbp+pv]
0x180017322  xor     r8d, r8d
0x180017325  lea     edx, [rsi+1Eh]
0x180017328  mov     rcx, r12
0x18001732b  mov     rax, [rax+60h]
0x18001732f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017334  mov     r14d, eax
0x180017337  test    eax, eax
0x180017339  js      short loc_18001734B
0x18001733b  mov     r13b, sil
0x18001733e  mov     rax, [rbp+pv]
0x180017342  mov     dil, [rax+2]
0x180017346  and     dil, sil
0x180017349  jmp     short loc_18001738F
0x18001734b  add     eax, 3F55FDF6h
0x180017350  cmp     eax, 2
0x180017353  jbe     short loc_18001738F
0x180017355  mov     rcx, cs:WPP_GLOBAL_Control
0x18001735c  lea     rax, WPP_GLOBAL_Control
0x180017363  cmp     rcx, rax
0x180017366  jz      short loc_18001738C
0x180017368  test    byte ptr [rcx+1Ch], 4
0x18001736c  jz      short loc_18001738C
0x18001736e  cmp     byte ptr [rcx+19h], 3
0x180017372  jb      short loc_18001738C
0x180017374  mov     edx, 11h
0x180017379  mov     r9d, r14d
0x18001737c  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180017383  mov     rcx, [rcx+10h]
0x180017387  call    WPP_SF_d
0x18001738c  mov     ebx, r14d
0x18001738f  mov     rcx, [rbp+pv]; pv
0x180017393  call    cs:__imp_CoTaskMemFree
0x180017399  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173a0  xor     r14d, r14d
0x1800173a3  test    ebx, ebx
0x1800173a5  js      loc_180017C37
0x1800173ab  mov     [rbp+pv], r14
0x1800173af  mov     dword ptr [rbp+arg_0], r14d
0x1800173b3  mov     rax, [r12]
0x1800173b7  lea     rcx, [rbp+arg_0]
0x1800173bb  mov     [rsp+40h+var_20], rcx
0x1800173c0  lea     r9, [rbp+pv]
0x1800173c4  xor     r8d, r8d
0x1800173c7  lea     edx, [r14+40h]
0x1800173cb  mov     rcx, r12
0x1800173ce  mov     rax, [rax+60h]
0x1800173d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173d7  mov     r14d, eax
0x1800173da  test    eax, eax
0x1800173dc  js      short loc_1800173EB
0x1800173de  mov     rax, [rbp+pv]
0x1800173e2  mov     r15b, [rax+2]
0x1800173e6  and     r15b, sil
0x1800173e9  jmp     short loc_18001742F
0x1800173eb  add     eax, 3F55FDF6h
0x1800173f0  cmp     eax, 2
0x1800173f3  jbe     short loc_18001742F
0x1800173f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800173fc  lea     rax, WPP_GLOBAL_Control
0x180017403  cmp     rcx, rax
0x180017406  jz      short loc_18001742C
0x180017408  test    byte ptr [rcx+1Ch], 4
0x18001740c  jz      short loc_18001742C
0x18001740e  cmp     byte ptr [rcx+19h], 3
0x180017412  jb      short loc_18001742C
0x180017414  mov     edx, 12h
0x180017419  mov     r9d, r14d
0x18001741c  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180017423  mov     rcx, [rcx+10h]
0x180017427  call    WPP_SF_d
0x18001742c  mov     ebx, r14d
0x18001742f  mov     rcx, [rbp+pv]; pv
0x180017433  call    cs:__imp_CoTaskMemFree
0x180017439  mov     rcx, cs:WPP_GLOBAL_Control
0x180017440  test    ebx, ebx
0x180017442  js      loc_180017C37
0x180017448  mov     rdx, [rbp+var_10]
0x18001744c  mov     al, [rdx+2]
0x18001744f  and     al, 3
0x180017451  cmp     al, 2
0x180017453  jnz     short loc_1800174B2
0x180017455  test    byte ptr [rdx+2], 10h
0x180017459  jnz     short loc_1800174B2
0x18001745b  test    r15b, r15b
0x18001745e  jz      short loc_180017467
0x180017460  mov     edi, 11h
0x180017465  jmp     short loc_180017471
0x180017467  neg     dil
0x18001746a  sbb     edi, edi
0x18001746c  and     edi, 3
0x18001746f  add     edi, esi
0x180017471  lea     rax, WPP_GLOBAL_Control
0x180017478  cmp     rcx, rax
0x18001747b  jz      loc_180017C31
0x180017481  test    byte ptr [rcx+1Ch], 4
0x180017485  jz      loc_180017C31
0x18001748b  cmp     byte ptr [rcx+19h], 4
0x18001748f  jb      loc_180017C31
0x180017495  mov     edx, 13h
0x18001749a  mov     r9d, edi
0x18001749d  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800174a4  mov     rcx, [rcx+10h]
0x1800174a8  call    WPP_SF_d
0x1800174ad  jmp     loc_180017C31
0x1800174b2  xor     r15d, r15d
0x1800174b5  mov     edi, r15d
0x1800174b8  mov     r14b, r15b
0x1800174bb  mov     [rbp+pv], r15
0x1800174bf  mov     dword ptr [rbp+arg_0], r15d
0x1800174c3  mov     rax, [r12]
0x1800174c7  lea     rcx, [rbp+arg_0]
0x1800174cb  mov     [rsp+40h+var_20], rcx
0x1800174d0  lea     r9, [rbp+pv]
0x1800174d4  mov     r8b, sil
0x1800174d7  lea     edx, [r15+2Ah]
0x1800174db  mov     rcx, r12
0x1800174de  mov     rax, [rax+60h]
0x1800174e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174e7  mov     ebx, eax
0x1800174e9  lea     r8d, [r15+7]
0x1800174ed  cmp     eax, 0C0AA020Ch
0x1800174f2  jz      loc_1800175C0
0x1800174f8  add     eax, 3F55FDF6h
0x1800174fd  cmp     eax, esi
0x1800174ff  jbe     loc_18001758C
0x180017505  test    ebx, ebx
0x180017507  jns     short loc_18001754D
0x180017509  mov     rcx, cs:WPP_GLOBAL_Control
0x180017510  lea     rax, WPP_GLOBAL_Control
0x180017517  cmp     rcx, rax
0x18001751a  jz      loc_1800175C3
0x180017520  test    byte ptr [rcx+1Ch], 4
0x180017524  jz      loc_1800175C3
0x18001752a  cmp     byte ptr [rcx+19h], 3
0x18001752e  jb      loc_1800175C3
0x180017534  lea     edx, [r15+15h]
0x180017538  mov     r9d, ebx
0x18001753b  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180017542  mov     rcx, [rcx+10h]
0x180017546  call    WPP_SF_d
0x18001754b  jmp     short loc_1800175C3
0x18001754d  mov     r14b, sil
0x180017550  mov     edi, r8d
0x180017553  mov     rcx, cs:WPP_GLOBAL_Control
0x18001755a  lea     rax, WPP_GLOBAL_Control
0x180017561  cmp     rcx, rax
0x180017564  jz      short loc_1800175C3
0x180017566  test    byte ptr [rcx+1Ch], 4
0x18001756a  jz      short loc_1800175C3
0x18001756c  cmp     byte ptr [rcx+19h], 4
0x180017570  jb      short loc_1800175C3
0x180017572  mov     edx, 16h
0x180017577  mov     r9d, r8d
0x18001757a  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180017581  mov     rcx, [rcx+10h]
0x180017585  call    WPP_SF_d
0x18001758a  jmp     short loc_1800175C3
0x18001758c  mov     rcx, cs:WPP_GLOBAL_Control
0x180017593  lea     rax, WPP_GLOBAL_Control
0x18001759a  cmp     rcx, rax
0x18001759d  jz      short loc_1800175C0
0x18001759f  test    byte ptr [rcx+1Ch], 4
0x1800175a3  jz      short loc_1800175C0
0x1800175a5  cmp     byte ptr [rcx+19h], 5
0x1800175a9  jb      short loc_1800175C0
0x1800175ab  mov     edx, 14h
0x1800175b0  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x1800175b7  mov     rcx, [rcx+10h]
0x1800175bb  call    WPP_SF_
0x1800175c0  mov     ebx, r15d
0x1800175c3  mov     rcx, [rbp+pv]; pv
0x1800175c7  call    cs:__imp_CoTaskMemFree
0x1800175cd  test    r14b, r14b
0x1800175d0  jnz     loc_180017C2D
0x1800175d6  test    ebx, ebx
0x1800175d8  js      loc_180017C37
0x1800175de  mov     [rbp+pv], r15
0x1800175e2  mov     dword ptr [rbp+arg_0], r15d
0x1800175e6  mov     rax, [r12]
0x1800175ea  lea     rcx, [rbp+arg_0]
0x1800175ee  mov     [rsp+40h+var_20], rcx
0x1800175f3  lea     r9, [rbp+pv]
0x1800175f7  mov     r8b, sil
0x1800175fa  mov     edx, 3Bh ; ';'
0x1800175ff  mov     rcx, r12
0x180017602  mov     rax, [rax+60h]
0x180017606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001760b  mov     ebx, eax
0x18001760d  mov     r8d, 8
0x180017613  cmp     eax, 0C0AA020Ch
0x180017618  jz      loc_1800176E6
0x18001761e  add     eax, 3F55FDF6h
0x180017623  cmp     eax, esi
0x180017625  jbe     loc_1800176B2
0x18001762b  test    ebx, ebx
0x18001762d  jns     short loc_180017673
0x18001762f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017636  lea     rax, WPP_GLOBAL_Control
0x18001763d  cmp     rcx, rax
0x180017640  jz      loc_1800176E9
0x180017646  test    byte ptr [rcx+1Ch], 4
0x18001764a  jz      loc_1800176E9
0x180017650  cmp     byte ptr [rcx+19h], 3
0x180017654  jb      loc_1800176E9
0x18001765a  lea     edx, [r8+10h]
0x18001765e  mov     r9d, ebx
0x180017661  lea     r8, WPP_fbd3da4e46e53232108cc4e5406ff1b8_Traceguids
0x180017668  mov     rcx, [rcx+10h]
0x18001766c  call    WPP_SF_d
0x180017671  jmp     short loc_1800176E9
0x180017673  mov     r14b, sil
0x180017676  mov     edi, r8d
0x180017679  mov     rcx, cs:WPP_GLOBAL_Control
0x180017680  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
