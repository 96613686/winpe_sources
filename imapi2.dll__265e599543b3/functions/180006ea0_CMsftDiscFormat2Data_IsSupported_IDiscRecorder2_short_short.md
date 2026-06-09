# CMsftDiscFormat2Data::IsSupported(IDiscRecorder2 *,short *,short)

- ea: `0x180006ea0`
- end: `0x180007df2`
- name: `?IsSupported@CMsftDiscFormat2Data@@AEAAJPEAUIDiscRecorder2@@PEAFF@Z`
- size: `3922`
- prototype: `int(CMsftDiscFormat2Data *__hidden this, struct IDiscRecorder2 *, __int16 *, __int16)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180006e90`
- `0x18001c020`

## callees

- `0x180006ea0`
- `0x180007df8`
- `0x18000a5f0`
- `0x18000a86c`
- `0x1800140f4`
- `0x180016778`
- `0x180023790`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800070b6`
- `ole32!CoTaskMemFree` at `0x1800071fe`
- `ole32!CoTaskMemFree` at `0x18000733c`
- `ole32!CoTaskMemFree` at `0x180007497`
- `ole32!CoTaskMemFree` at `0x1800075f9`
- `ole32!CoTaskMemFree` at `0x18000775b`
- `ole32!CoTaskMemFree` at `0x1800078d0`
- `ole32!CoTaskMemFree` at `0x180007a6a`
- `ole32!CoTaskMemFree` at `0x180007da3`
- `ole32!CoTaskMemFree` at `0x1800070b6`
- `ole32!CoTaskMemFree` at `0x1800071fe`
- `ole32!CoTaskMemFree` at `0x18000733c`
- `ole32!CoTaskMemFree` at `0x180007497`
- `ole32!CoTaskMemFree` at `0x1800075f9`
- `ole32!CoTaskMemFree` at `0x18000775b`
- `ole32!CoTaskMemFree` at `0x1800078d0`
- `ole32!CoTaskMemFree` at `0x180007a6a`
- `ole32!CoTaskMemFree` at `0x180007da3`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2Data::IsSupported(
        struct IDiscRecorder2Vtbl *this,
        struct IDiscRecorder2 *a2,
        unsigned __int8 *a3,
        __int16 a4)
{
  __int16 v4; // si
  unsigned __int8 *v5; // r13
  int v7; // ebx
  PVOID *v8; // rcx
  __int64 result; // rax
  __int16 v10; // r14
  __int16 v11; // r15
  int v12; // eax
  unsigned int v13; // edi
  __int16 v14; // r12
  struct IDiscRecorder2ExVtbl *lpVtbl; // rax
  PVOID *v16; // rcx
  PVOID *v17; // rcx
  _BYTE *v18; // rdi
  PVOID *v19; // rcx
  _BYTE *v20; // rdi
  PVOID *v21; // rcx
  _BYTE *v22; // rdi
  PVOID *v23; // rcx
  unsigned int i; // ecx
  PVOID *v25; // rcx
  __int64 v26; // rdx
  PVOID *v27; // rcx
  __int16 v28; // r13
  __int64 v29; // r9
  unsigned __int64 v30; // rax
  __int64 v31; // rdx
  int v32; // eax
  PVOID *v33; // rcx
  int v34; // eax
  _QWORD *v35; // rcx
  __int64 v36; // rdx
  LPVOID v37[2]; // [rsp+30h] [rbp-38h] BYREF
  struct IDiscRecorder2Ex *v38; // [rsp+40h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-20h] BYREF
  __int64 v40; // [rsp+50h] [rbp-18h]
  IDiscRecorder2 v41; // [rsp+B0h] [rbp+48h] BYREF
  int v42; // [rsp+B8h] [rbp+50h]
  unsigned __int8 *v43; // [rsp+C0h] [rbp+58h] BYREF
  __int16 v44; // [rsp+C8h] [rbp+60h]

  v44 = a4;
  v43 = a3;
  v41.lpVtbl = this;
  v38 = 0;
  v4 = a4;
  v5 = a3;
  v7 = 0;
  if ( a2 )
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v8 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 37), 191, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    v7 = -2147467261;
  }
  if ( v5 )
  {
    *(_WORD *)v5 = 0;
    if ( v7 >= 0 )
    {
      LOBYTE(v41.lpVtbl) = 0;
      result = Imapi2Utility::IsRecorderSupported((Imapi2Utility *)a2, &v41, a3);
      v7 = result;
      if ( (int)result >= 0 && !LOBYTE(v41.lpVtbl) )
      {
        *(_WORD *)v5 = 0;
        return result;
      }
    }
    v10 = 0;
    v11 = 0;
    if ( v7 < 0 )
    {
      v13 = 0;
    }
    else
    {
      v12 = ((__int64 (__fastcall *)(struct IDiscRecorder2 *, GUID *, struct IDiscRecorder2Ex **))a2->lpVtbl->QueryInterface)(
              a2,
              &GUID_27354132_7f64_5b0f_8f00_5d77afbe261e,
              &v38);
      v13 = 0;
      v7 = v12;
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            193,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)v12);
        }
        v7 = 0;
        goto LABEL_246;
      }
    }
    if ( v7 < 0 )
      goto LABEL_249;
    pv = 0;
    LODWORD(v41.lpVtbl) = 0;
    v14 = 0;
    lpVtbl = v38->lpVtbl;
    v42 = 0;
    v7 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, _QWORD, _QWORD, LPVOID *, IDiscRecorder2 *))lpVtbl->GetFeaturePage)(
           v38,
           0,
           0,
           &pv,
           &v41);
    if ( ((v7 + 1062600182) & 0xFFFFFFFD) != 0 )
    {
      if ( v7 >= 0 )
      {
        v14 = -1;
        v42 = 0xFFFF;
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          194,
          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
          (unsigned int)v7);
      }
    }
    else
    {
      v7 = 0;
    }
    CoTaskMemFree(pv);
    if ( v7 < 0 )
      goto LABEL_249;
    if ( v14 )
    {
      pv = 0;
      LODWORD(v41.lpVtbl) = 0;
      v7 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, IDiscRecorder2 *))v38->lpVtbl->GetFeaturePage)(
             v38,
             45,
             0,
             &pv,
             &v41);
      if ( ((v7 + 1062600182) & 0xFFFFFFFD) != 0 )
      {
        if ( v7 >= 0 )
        {
          v16 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 37), 196, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 45);
            v16 = (PVOID *)WPP_GLOBAL_Control;
          }
          v10 = -1;
          if ( (*((_BYTE *)pv + 2) & 1) != 0 )
          {
            if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 308) & 4) != 0 && *((_BYTE *)v16 + 305) >= 4u )
              WPP_SF_d(v16[37], 197, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 45);
            v11 = -1;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            195,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)v7);
        }
      }
      else
      {
        v7 = 0;
      }
      CoTaskMemFree(pv);
      if ( v7 < 0 )
        goto LABEL_249;
      pv = 0;
      LODWORD(v41.lpVtbl) = 0;
      v7 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, IDiscRecorder2 *))v38->lpVtbl->GetFeaturePage)(
             v38,
             47,
             0,
             &pv,
             &v41);
      if ( ((v7 + 1062600182) & 0xFFFFFFFD) != 0 )
      {
        if ( v7 >= 0 )
        {
          v17 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 37), 199, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 47);
            v17 = (PVOID *)WPP_GLOBAL_Control;
          }
          v10 = -1;
          if ( (*((_BYTE *)pv + 2) & 1) != 0 )
          {
            if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 308) & 4) != 0 && *((_BYTE *)v17 + 305) >= 4u )
              WPP_SF_d(v17[37], 200, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 47);
            v11 = -1;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            198,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)v7);
        }
      }
      else
      {
        v7 = 0;
      }
      CoTaskMemFree(pv);
      if ( v7 < 0 )
        goto LABEL_249;
      v37[0] = 0;
      LODWORD(v41.lpVtbl) = 0;
      v7 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, IDiscRecorder2 *))v38->lpVtbl->GetFeaturePage)(
             v38,
             43,
             0,
             v37,
             &v41);
      if ( ((v7 + 1062600182) & 0xFFFFFFFD) != 0 )
      {
        if ( v7 >= 0 )
        {
          v18 = v37[0];
          v19 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 37), 202, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 43);
            v19 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( *((_BYTE *)v37[0] + 3) )
          {
            if ( LODWORD(v41.lpVtbl) >= 5 && (v18[4] & 1) != 0 )
            {
              v10 = -1;
              if ( (*((_BYTE *)v37[0] + 2) & 1) != 0 )
              {
                if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 308) & 4) != 0 && *((_BYTE *)v19 + 305) >= 4u )
                  WPP_SF_d(v19[37], 203, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 43);
                v11 = -1;
              }
            }
          }
          v13 = 0;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            201,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)v7);
        }
      }
      else
      {
        v7 = 0;
      }
      CoTaskMemFree(v37[0]);
      if ( v7 < 0 )
        goto LABEL_249;
      v37[0] = 0;
      LODWORD(v41.lpVtbl) = 0;
      v7 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, IDiscRecorder2 *))v38->lpVtbl->GetFeaturePage)(
             v38,
             42,
             0,
             v37,
             &v41);
      if ( ((v7 + 1062600182) & 0xFFFFFFFD) != 0 )
      {
        if ( v7 >= 0 )
        {
          v20 = v37[0];
          v21 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 37), 205, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 42);
            v21 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( *((_BYTE *)v37[0] + 3) )
          {
            if ( LODWORD(v41.lpVtbl) >= 5 && (v20[4] & 1) != 0 )
            {
              v10 = -1;
              if ( (*((_BYTE *)v37[0] + 2) & 1) != 0 )
              {
                if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 308) & 4) != 0 && *((_BYTE *)v21 + 305) >= 4u )
                  WPP_SF_d(v21[37], 206, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 42);
                v11 = -1;
              }
            }
          }
          v13 = 0;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            204,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)v7);
        }
      }
      else
      {
        v7 = 0;
      }
      CoTaskMemFree(v37[0]);
      if ( v7 < 0 )
        goto LABEL_249;
      v37[0] = 0;
      LODWORD(v41.lpVtbl) = 0;
      v7 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, IDiscRecorder2 *))v38->lpVtbl->GetFeaturePage)(
             v38,
             59,
             0,
             v37,
             &v41);
      if ( ((v7 + 1062600182) & 0xFFFFFFFD) != 0 )
      {
        if ( v7 >= 0 )
        {
          v22 = v37[0];
          v23 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 37), 208, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 59);
            v23 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( *((_BYTE *)v37[0] + 3) )
          {
            if ( LODWORD(v41.lpVtbl) >= 5 && (v22[4] & 1) != 0 )
            {
              v10 = -1;
              if ( (*((_BYTE *)v37[0] + 2) & 1) != 0 )
              {
                if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 308) & 4) != 0 && *((_BYTE *)v23 + 305) >= 4u )
                  WPP_SF_d(v23[37], 209, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 59);
                v11 = -1;
              }
            }
          }
          v13 = 0;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            207,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)v7);
        }
      }
      else
      {
        v7 = 0;
      }
      CoTaskMemFree(v37[0]);
      if ( v7 < 0 )
        goto LABEL_249;
      v37[0] = 0;
      LODWORD(v41.lpVtbl) = 0;
      v7 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, LPVOID *, IDiscRecorder2 *))v38->lpVtbl->GetFeaturePage)(
             v38,
             65,
             0,
             v37,
             &v41);
      if ( ((v7 + 1062600182) & 0xFFFFFFFD) != 0 )
      {
        if ( v7 >= 0 )
        {
          if ( *((_BYTE *)v37[0] + 3) >= 0x14u )
          {
            for ( i = 8; i <= 0x17; ++i )
            {
              if ( *((_BYTE *)v37[0] + i) )
              {
                v10 = -1;
                v25 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 37),
                    211,
                    &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                    65);
                  v25 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( (*((_BYTE *)v37[0] + 2) & 1) != 0 )
                {
                  v11 = -1;
                  if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 308) & 4) != 0 && *((_BYTE *)v25 + 305) >= 4u )
                    WPP_SF_d(v25[37], 212, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 65);
                }
                break;
              }
            }
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            210,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)v7);
        }
      }
      else
      {
        v7 = 0;
      }
      CoTaskMemFree(v37[0]);
      if ( v7 < 0 )
        goto LABEL_249;
      pv = 0;
      LODWORD(v41.lpVtbl) = 0;
      LOBYTE(v26) = v4 != 0;
      v7 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, LPVOID *, IDiscRecorder2 *))v38->lpVtbl->GetSupportedProfiles)(
             v38,
             v26,
             &pv,
             &v41);
      LODWORD(v37[0]) = v7;
      if ( ((v7 + 1062600182) & 0xFFFFFFFD) != 0 )
      {
        if ( v7 >= 0 )
        {
          if ( LODWORD(v41.lpVtbl) )
          {
            v27 = (PVOID *)WPP_GLOBAL_Control;
            v28 = v44;
            do
            {
              v29 = *((unsigned int *)pv + v13);
              if ( (_DWORD)v29 == 2
                || (v30 = (unsigned int)(v29 - 17), (unsigned int)v30 <= 0x32)
                && (v31 = 0x7000000000007LL, _bittest64(&v31, v30)) )
              {
                if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 308) & 4) != 0 && *((_BYTE *)v27 + 305) >= 4u )
                {
                  WPP_SF_d(v27[37], 214, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, v29);
                  v27 = (PVOID *)WPP_GLOBAL_Control;
                }
                v10 = -1;
                if ( v28 )
                {
                  if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 308) & 4) != 0 && *((_BYTE *)v27 + 305) >= 4u )
                  {
                    WPP_SF_d(
                      v27[37],
                      215,
                      &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
                      *((unsigned int *)pv + v13));
                    v27 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  v11 = -1;
                }
              }
              ++v13;
            }
            while ( v13 < LODWORD(v41.lpVtbl) );
            v7 = (int)v37[0];
            v14 = v42;
            v5 = v43;
            v4 = v44;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            213,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)v7);
        }
      }
      else
      {
        v7 = 0;
      }
      CoTaskMemFree(pv);
      if ( v7 < 0 )
        goto LABEL_249;
      if ( v14 )
      {
LABEL_246:
        if ( v4 )
          v10 = v11;
        *(_WORD *)v5 = v10;
        goto LABEL_251;
      }
    }
    v41.lpVtbl = 0;
    LODWORD(v43) = 0;
    v32 = ((__int64 (__fastcall *)(struct IDiscRecorder2Ex *, __int64, _QWORD, IDiscRecorder2 *, unsigned __int8 **))v38->lpVtbl->GetModePage)(
            v38,
            42,
            0,
            &v41,
            &v43);
    v7 = v32;
    if ( v32 == -1062600191 )
      goto LABEL_245;
    if ( v32 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          216,
          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
          (unsigned int)v32);
      }
      goto LABEL_245;
    }
    if ( (unsigned int)v43 < 6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          217,
          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
          (unsigned int)v43);
      }
      v7 = -2147467259;
      goto LABEL_245;
    }
    if ( (BYTE3(v41.lpVtbl->QueryInterface) & 1) != 0 )
    {
      v33 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 37), 218, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 42);
        v33 = (PVOID *)WPP_GLOBAL_Control;
      }
      v10 = -1;
    }
    else
    {
      v33 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (BYTE3(v41.lpVtbl->QueryInterface) & 2) != 0 )
    {
      if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 308) & 4) != 0 && *((_BYTE *)v33 + 305) >= 4u )
        WPP_SF_d(v33[37], 219, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, 42);
      v10 = -1;
    }
    else if ( !v10 )
    {
      goto LABEL_245;
    }
    if ( !v4 )
    {
LABEL_245:
      CoTaskMemFree(v41.lpVtbl);
      if ( v7 >= 0 )
        goto LABEL_246;
LABEL_249:
      if ( v7 != -2147467261 )
        v7 = 1;
      goto LABEL_251;
    }
    pv = 0;
    v40 = 0;
    v34 = CMsftDiscInformation::Init((CMsftDiscInformation *)&pv, v38);
    if ( v34 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          220,
          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
          (unsigned int)v34);
      }
      goto LABEL_244;
    }
    if ( (*((_BYTE *)pv + 2) & 3) != 0 )
    {
      if ( (*((_BYTE *)pv + 2) & 3) == 1 )
      {
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
        {
          goto LABEL_237;
        }
        v36 = 222;
      }
      else
      {
        if ( (*((_BYTE *)pv + 2) & 0x10) == 0 || (BYTE3(v41.lpVtbl->QueryInterface) & 2) == 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 4u )
          {
            v37[0] = (LPVOID)0x7FFF;
            v37[1] = pv;
            if ( (unsigned int)v40 <= 0x7FFF )
              LOWORD(v37[0]) = v40;
            WPP_SF__HEX_(
              *((_QWORD *)WPP_GLOBAL_Control + 37),
              224,
              &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
              v37);
          }
          goto LABEL_244;
        }
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
        {
          goto LABEL_237;
        }
        v36 = 223;
      }
    }
    else
    {
      v35 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 4u )
      {
        goto LABEL_237;
      }
      v36 = 221;
    }
    WPP_SF_(v35[37], v36, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
LABEL_237:
    v11 = -1;
LABEL_244:
    CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)&pv);
    goto LABEL_245;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 308) & 4) != 0 && *((_BYTE *)v8 + 305) >= 3u )
    WPP_SF_(v8[37], 192, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
  v7 = -2147467261;
LABEL_251:
  if ( v38 )
    ((void (__fastcall *)(struct IDiscRecorder2Ex *))v38->lpVtbl->Release)(v38);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180006ea0  mov     [rsp-40h+arg_18], r9w
0x180006ea6  mov     [rsp-40h+arg_10], r8
0x180006eab  mov     [rsp-40h+arg_0.lpVtbl], rcx
0x180006eb0  push    rbp
0x180006eb1  push    rbx
0x180006eb2  push    rsi
0x180006eb3  push    rdi
0x180006eb4  push    r12
0x180006eb6  push    r13
0x180006eb8  push    r14
0x180006eba  push    r15
0x180006ebc  mov     rbp, rsp
0x180006ebf  sub     rsp, 68h
0x180006ec3  xor     r12d, r12d
0x180006ec6  lea     rax, WPP_GLOBAL_Control
0x180006ecd  mov     [rbp+var_28], r12
0x180006ed1  movzx   esi, r9w
0x180006ed5  mov     r13, r8
0x180006ed8  mov     rdi, rdx
0x180006edb  mov     ebx, r12d
0x180006ede  mov     r14d, 80004003h
0x180006ee4  test    rdx, rdx
0x180006ee7  jnz     short loc_180006F32
0x180006ee9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ef0  cmp     rcx, rax
0x180006ef3  jz      short loc_180006F2D
0x180006ef5  test    byte ptr [rcx+134h], 4
0x180006efc  jz      short loc_180006F2D
0x180006efe  cmp     byte ptr [rcx+131h], 3
0x180006f05  jb      short loc_180006F2D
0x180006f07  mov     rcx, [rcx+128h]
0x180006f0e  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180006f15  mov     edx, 0BFh
0x180006f1a  call    WPP_SF_
0x180006f1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f26  lea     rax, WPP_GLOBAL_Control
0x180006f2d  mov     ebx, r14d
0x180006f30  jmp     short loc_180006F39
0x180006f32  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f39  test    r13, r13
0x180006f3c  jnz     short loc_180006F75
0x180006f3e  cmp     rcx, rax
0x180006f41  jz      short loc_180006F6D
0x180006f43  test    byte ptr [rcx+134h], 4
0x180006f4a  jz      short loc_180006F6D
0x180006f4c  cmp     byte ptr [rcx+131h], 3
0x180006f53  jb      short loc_180006F6D
0x180006f55  mov     rcx, [rcx+128h]
0x180006f5c  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180006f63  mov     edx, 0C0h
0x180006f68  call    WPP_SF_
0x180006f6d  mov     ebx, r14d
0x180006f70  jmp     loc_180007DCA
0x180006f75  mov     [r13+0], r12w
0x180006f7a  test    ebx, ebx
0x180006f7c  js      short loc_180006FA4
0x180006f7e  lea     rdx, [rbp+arg_0]; struct IDiscRecorder2 *
0x180006f82  mov     byte ptr [rbp+arg_0.lpVtbl], r12b
0x180006f86  mov     rcx, rdi; this
0x180006f89  call    ?IsRecorderSupported@Imapi2Utility@@YAJPEAUIDiscRecorder2@@PEAE@Z; Imapi2Utility::IsRecorderSupported(IDiscRecorder2 *,uchar *)
0x180006f8e  mov     ebx, eax
0x180006f90  test    eax, eax
0x180006f92  js      short loc_180006FA4
0x180006f94  cmp     byte ptr [rbp+arg_0.lpVtbl], r12b
0x180006f98  jnz     short loc_180006FA4
0x180006f9a  mov     [r13+0], r12w
0x180006f9f  jmp     loc_180007DE1
0x180006fa4  mov     r14d, r12d
0x180006fa7  mov     r15d, r12d
0x180006faa  test    ebx, ebx
0x180006fac  js      short loc_180007016
0x180006fae  mov     rax, [rdi]
0x180006fb1  lea     r8, [rbp+var_28]
0x180006fb5  lea     rdx, _GUID_27354132_7f64_5b0f_8f00_5d77afbe261e
0x180006fbc  mov     rcx, rdi
0x180006fbf  mov     rax, [rax]
0x180006fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc7  xor     edi, edi
0x180006fc9  mov     ebx, eax
0x180006fcb  test    eax, eax
0x180006fcd  jns     short loc_180007018
0x180006fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180006fd6  lea     rax, WPP_GLOBAL_Control
0x180006fdd  cmp     rcx, rax
0x180006fe0  jz      short loc_18000700F
0x180006fe2  test    byte ptr [rcx+134h], 4
0x180006fe9  jz      short loc_18000700F
0x180006feb  cmp     byte ptr [rcx+131h], 3
0x180006ff2  jb      short loc_18000700F
0x180006ff4  mov     rcx, [rcx+128h]
0x180006ffb  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180007002  mov     edx, 0C1h
0x180007007  mov     r9d, ebx
0x18000700a  call    WPP_SF_d
0x18000700f  mov     ebx, edi
0x180007011  jmp     loc_180007DAD
0x180007016  xor     edi, edi
0x180007018  test    ebx, ebx
0x18000701a  js      loc_180007DBC
0x180007020  mov     rcx, [rbp+var_28]
0x180007024  lea     rdx, [rbp+arg_0]
0x180007028  mov     [rbp+pv], rdi
0x18000702c  lea     r9, [rbp+pv]
0x180007030  mov     dword ptr [rbp+arg_0.lpVtbl], edi
0x180007033  xor     r8d, r8d
0x180007036  mov     [rsp+68h+var_48], rdx
0x18000703b  mov     r12d, edi
0x18000703e  mov     rax, [rcx]
0x180007041  xor     edx, edx
0x180007043  mov     [rbp+arg_8], edi
0x180007046  mov     rax, [rax+60h]
0x18000704a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000704f  mov     ebx, eax
0x180007051  or      ecx, 0FFFFFFFFh
0x180007054  add     eax, 3F55FDF6h
0x180007059  test    eax, 0FFFFFFFDh
0x18000705e  jz      short loc_1800070B0
0x180007060  test    ebx, ebx
0x180007062  jns     short loc_1800070A6
0x180007064  mov     rcx, cs:WPP_GLOBAL_Control
0x18000706b  lea     rax, WPP_GLOBAL_Control
0x180007072  cmp     rcx, rax
0x180007075  jz      short loc_1800070B2
0x180007077  test    byte ptr [rcx+134h], 4
0x18000707e  jz      short loc_1800070B2
0x180007080  cmp     byte ptr [rcx+131h], 3
0x180007087  jb      short loc_1800070B2
0x180007089  mov     rcx, [rcx+128h]
0x180007090  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180007097  mov     edx, 0C2h
0x18000709c  mov     r9d, ebx
0x18000709f  call    WPP_SF_d
0x1800070a4  jmp     short loc_1800070B2
0x1800070a6  movzx   r12d, cx
0x1800070aa  mov     [rbp+arg_8], r12d
0x1800070ae  jmp     short loc_1800070B2
0x1800070b0  mov     ebx, edi
0x1800070b2  mov     rcx, [rbp+pv]; pv
0x1800070b6  call    cs:__imp_CoTaskMemFree
0x1800070bc  test    ebx, ebx
0x1800070be  js      loc_180007DBC
0x1800070c4  test    r12w, r12w
0x1800070c8  jz      loc_180007A82
0x1800070ce  mov     rcx, [rbp+var_28]
0x1800070d2  lea     rdx, [rbp+arg_0]
0x1800070d6  mov     [rbp+pv], rdi
0x1800070da  lea     r9, [rbp+pv]
0x1800070de  mov     dword ptr [rbp+arg_0.lpVtbl], edi
0x1800070e1  xor     r8d, r8d
0x1800070e4  mov     [rsp+68h+var_48], rdx
0x1800070e9  mov     rax, [rcx]
0x1800070ec  lea     edx, [r8+2Dh]
0x1800070f0  mov     rax, [rax+60h]
0x1800070f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070f9  mov     ebx, eax
0x1800070fb  add     eax, 3F55FDF6h
0x180007100  test    eax, 0FFFFFFFDh
0x180007105  jz      loc_1800071F8
0x18000710b  test    ebx, ebx
0x18000710d  jns     short loc_180007160
0x18000710f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007116  lea     rax, WPP_GLOBAL_Control
0x18000711d  cmp     rcx, rax
0x180007120  jz      loc_1800071FA
0x180007126  test    byte ptr [rcx+134h], 4
0x18000712d  jz      loc_1800071FA
0x180007133  cmp     byte ptr [rcx+131h], 3
0x18000713a  jb      loc_1800071FA
0x180007140  mov     rcx, [rcx+128h]
0x180007147  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x18000714e  mov     edx, 0C3h
0x180007153  mov     r9d, ebx
0x180007156  call    WPP_SF_d
0x18000715b  jmp     loc_1800071FA
0x180007160  mov     rcx, cs:WPP_GLOBAL_Control
0x180007167  lea     rdx, WPP_GLOBAL_Control
0x18000716e  cmp     rcx, rdx
0x180007171  jz      short loc_1800071B1
0x180007173  test    byte ptr [rcx+134h], 4
0x18000717a  jz      short loc_1800071B1
0x18000717c  cmp     byte ptr [rcx+131h], 4
0x180007183  jb      short loc_1800071B1
0x180007185  mov     rcx, [rcx+128h]
0x18000718c  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x180007193  mov     edx, 0C4h
0x180007198  mov     r9d, 2Dh ; '-'
0x18000719e  call    WPP_SF_d
0x1800071a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071aa  lea     rdx, WPP_GLOBAL_Control
0x1800071b1  mov     rax, [rbp+pv]
0x1800071b5  or      r14d, 0FFFFFFFFh
0x1800071b9  test    byte ptr [rax+2], 1
0x1800071bd  jz      short loc_1800071FA
0x1800071bf  cmp     rcx, rdx
0x1800071c2  jz      short loc_1800071F2
0x1800071c4  test    byte ptr [rcx+134h], 4
0x1800071cb  jz      short loc_1800071F2
0x1800071cd  cmp     byte ptr [rcx+131h], 4
0x1800071d4  jb      short loc_1800071F2
0x1800071d6  mov     rcx, [rcx+128h]
0x1800071dd  lea     r9d, [r14+2Eh]
0x1800071e1  mov     edx, 0C5h
0x1800071e6  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x1800071ed  call    WPP_SF_d
0x1800071f2  or      r15d, 0FFFFFFFFh
0x1800071f6  jmp     short loc_1800071FA
0x1800071f8  mov     ebx, edi
0x1800071fa  mov     rcx, [rbp+pv]; pv
0x1800071fe  call    cs:__imp_CoTaskMemFree
0x180007204  test    ebx, ebx
0x180007206  js      loc_180007DBC
0x18000720c  mov     rcx, [rbp+var_28]
0x180007210  lea     rdx, [rbp+arg_0]
0x180007214  mov     [rbp+pv], rdi
0x180007218  lea     r9, [rbp+pv]
0x18000721c  mov     dword ptr [rbp+arg_0.lpVtbl], edi
0x18000721f  xor     r8d, r8d
0x180007222  mov     [rsp+68h+var_48], rdx
0x180007227  mov     rax, [rcx]
0x18000722a  lea     edx, [r8+2Fh]
0x18000722e  mov     rax, [rax+60h]
0x180007232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007237  mov     ebx, eax
0x180007239  add     eax, 3F55FDF6h
0x18000723e  test    eax, 0FFFFFFFDh
0x180007243  jz      loc_180007336
0x180007249  test    ebx, ebx
0x18000724b  jns     short loc_18000729E
0x18000724d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007254  lea     rax, WPP_GLOBAL_Control
0x18000725b  cmp     rcx, rax
0x18000725e  jz      loc_180007338
0x180007264  test    byte ptr [rcx+134h], 4
0x18000726b  jz      loc_180007338
0x180007271  cmp     byte ptr [rcx+131h], 3
0x180007278  jb      loc_180007338
0x18000727e  mov     rcx, [rcx+128h]
0x180007285  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x18000728c  mov     edx, 0C6h
0x180007291  mov     r9d, ebx
0x180007294  call    WPP_SF_d
0x180007299  jmp     loc_180007338
0x18000729e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072a5  lea     rdx, WPP_GLOBAL_Control
0x1800072ac  cmp     rcx, rdx
0x1800072af  jz      short loc_1800072EF
0x1800072b1  test    byte ptr [rcx+134h], 4
0x1800072b8  jz      short loc_1800072EF
0x1800072ba  cmp     byte ptr [rcx+131h], 4
0x1800072c1  jb      short loc_1800072EF
0x1800072c3  mov     rcx, [rcx+128h]
0x1800072ca  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x1800072d1  mov     edx, 0C7h
0x1800072d6  mov     r9d, 2Fh ; '/'
0x1800072dc  call    WPP_SF_d
0x1800072e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800072e8  lea     rdx, WPP_GLOBAL_Control
0x1800072ef  mov     rax, [rbp+pv]
0x1800072f3  or      r14d, 0FFFFFFFFh
0x1800072f7  test    byte ptr [rax+2], 1
0x1800072fb  jz      short loc_180007338
0x1800072fd  cmp     rcx, rdx
0x180007300  jz      short loc_180007330
0x180007302  test    byte ptr [rcx+134h], 4
0x180007309  jz      short loc_180007330
0x18000730b  cmp     byte ptr [rcx+131h], 4
0x180007312  jb      short loc_180007330
0x180007314  mov     rcx, [rcx+128h]
0x18000731b  lea     r9d, [r14+30h]
0x18000731f  mov     edx, 0C8h
0x180007324  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x18000732b  call    WPP_SF_d
0x180007330  or      r15d, 0FFFFFFFFh
0x180007334  jmp     short loc_180007338
0x180007336  mov     ebx, edi
0x180007338  mov     rcx, [rbp+pv]; pv
0x18000733c  call    cs:__imp_CoTaskMemFree
0x180007342  test    ebx, ebx
0x180007344  js      loc_180007DBC
0x18000734a  mov     rcx, [rbp+var_28]
0x18000734e  lea     rdx, [rbp+arg_0]
0x180007352  mov     [rbp+var_38], rdi
0x180007356  lea     r9, [rbp+var_38]
0x18000735a  mov     dword ptr [rbp+arg_0.lpVtbl], edi
0x18000735d  xor     r8d, r8d
0x180007360  mov     [rsp+68h+var_48], rdx
0x180007365  mov     rax, [rcx]
0x180007368  lea     edx, [r8+2Bh]
0x18000736c  mov     rax, [rax+60h]
0x180007370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007375  mov     ebx, eax
0x180007377  add     eax, 3F55FDF6h
0x18000737c  test    eax, 0FFFFFFFDh
0x180007381  jz      loc_180007537
0x180007387  test    ebx, ebx
0x180007389  jns     short loc_1800073DC
0x18000738b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007392  lea     rax, WPP_GLOBAL_Control
0x180007399  cmp     rcx, rax
0x18000739c  jz      loc_180007493
  ... truncated ...
```
