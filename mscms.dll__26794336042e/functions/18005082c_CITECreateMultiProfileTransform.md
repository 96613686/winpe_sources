# CITECreateMultiProfileTransform

- ea: `0x18005082c`
- end: `0x180051477`
- name: `CITECreateMultiProfileTransform`
- size: `3147`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int *, int, int)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003dd20`
- `0x180051480`

## callees

- `0x180006e34`
- `0x1800181d0`
- `0x180018eb0`
- `0x1800223b8`
- `0x18002e5f0`
- `0x18002e670`
- `0x18002ea84`
- `0x18002f2dc`
- `0x18002f2f4`
- `0x18004e278`
- `0x18004e544`
- `0x18004ec30`
- `0x18004f4a4`
- `0x18004f504`
- `0x18004f694`
- `0x18004f6d8`
- `0x18004fad8`
- `0x1800502b4`
- `0x1800502f8`
- `0x18005082c`
- `0x180066b18`
- `0x180067004`
- `0x180084010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180050e34`
- `ntdll!EtwEventWrite` at `0x1800512e2`
- `ntdll!EtwEventWrite` at `0x180050e34`
- `ntdll!EtwEventWrite` at `0x1800512e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005143b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005143b`

## pseudocode

```c
__int64 __fastcall CITECreateMultiProfileTransform(__int64 a1, unsigned int a2, unsigned int *a3, int a4, int a5)
{
  CmmModels *v8; // r13
  int IDeviceModel; // ebx
  struct IGamutDistanceFinder *v10; // rsi
  unsigned int v11; // edi
  struct IColorAppearanceModel *v12; // r14
  float v13; // xmm7_4
  float v14; // xmm6_4
  __int64 v15; // r8
  __int64 v16; // rcx
  unsigned int *v17; // rdi
  struct IColorAppearanceModel *v18; // r15
  struct IDeviceModel *v19; // rdi
  struct IGamutBoundaryDescription *v20; // rsi
  struct IDeviceModelData *v21; // r12
  CmmModels *v22; // rax
  CmmModels *v23; // r14
  CmmModels *v24; // rax
  CmmModels *v25; // rax
  __int64 v26; // rdx
  int v27; // esi
  int v28; // edi
  struct IDeviceModelPlugIn *v29; // rsi
  struct IDeviceModelPlugIn *v30; // r12
  unsigned int v31; // edx
  int DeviceModelType; // edi
  CmmModels *v33; // rcx
  struct IDeviceModel *v34; // r14
  __int64 v35; // rax
  __int64 j; // rcx
  struct IDeviceModelData *v37; // rsi
  __int64 v38; // rax
  __int64 v39; // rax
  unsigned int v40; // r9d
  unsigned int v41; // r8d
  struct IDeviceModelData *v42; // r10
  unsigned int k; // edi
  __int64 v44; // rcx
  float v45; // xmm1_4
  float v46; // xmm0_4
  __int64 v47; // r8
  unsigned int v48; // edi
  __int64 v49; // rdx
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // r13
  struct IDeviceModel *v53; // r15
  struct IDeviceModel *v54; // r12
  struct IColorAppearanceModel *v55; // rdi
  _OWORD *v56; // rdi
  CmmModels *v57; // rcx
  struct IDeviceModelData *v58; // rdi
  __int64 v59; // rdx
  __int64 i; // rcx
  int v61; // eax
  unsigned int v62; // eax
  unsigned int v63; // esi
  float *v64; // rdi
  __int64 v65; // rax
  unsigned int v66; // r15d
  __int64 m; // rdi
  __int64 v68; // rcx
  struct IXMLDOMDocument2 **v70; // [rsp+28h] [rbp-E0h]
  struct IXMLDOMDocument2 **v71; // [rsp+30h] [rbp-D8h]
  int v72[2]; // [rsp+68h] [rbp-A0h] BYREF
  struct IDeviceModelData *v73; // [rsp+70h] [rbp-98h] BYREF
  struct IDeviceModel *v74; // [rsp+78h] [rbp-90h] BYREF
  CmmModels *v75; // [rsp+80h] [rbp-88h]
  struct IGamutBoundaryDescription *v76; // [rsp+88h] [rbp-80h] BYREF
  unsigned int v77; // [rsp+90h] [rbp-78h]
  int v78; // [rsp+94h] [rbp-74h] BYREF
  struct IColorAppearanceModel *v79; // [rsp+98h] [rbp-70h] BYREF
  float v80; // [rsp+A0h] [rbp-68h] BYREF
  float v81; // [rsp+A4h] [rbp-64h] BYREF
  int v82[2]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned int v83; // [rsp+B0h] [rbp-58h]
  int v84; // [rsp+B4h] [rbp-54h]
  struct IDeviceModelPlugIn *v85; // [rsp+B8h] [rbp-50h] BYREF
  struct IDeviceModel *v86; // [rsp+C0h] [rbp-48h]
  int v87; // [rsp+C8h] [rbp-40h]
  int v88; // [rsp+CCh] [rbp-3Ch]
  int v89; // [rsp+D0h] [rbp-38h] BYREF
  struct IDeviceModelData *v90; // [rsp+D8h] [rbp-30h]
  struct IDeviceModel *v91; // [rsp+E0h] [rbp-28h] BYREF
  struct IColorAppearanceModel *v92; // [rsp+E8h] [rbp-20h] BYREF
  struct IGamutDistanceFinder *v93; // [rsp+F0h] [rbp-18h] BYREF
  struct IDeviceModel *v94; // [rsp+F8h] [rbp-10h]
  struct IDeviceModelPlugIn *v95; // [rsp+100h] [rbp-8h] BYREF
  __int64 HeapObject; // [rsp+108h] [rbp+0h]
  __int64 v97; // [rsp+110h] [rbp+8h]
  _BYTE v98[112]; // [rsp+118h] [rbp+10h] BYREF
  _BYTE v99[112]; // [rsp+188h] [rbp+80h] BYREF
  struct IDeviceModelData *v100; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v101; // [rsp+200h] [rbp+F8h]
  float *v102; // [rsp+208h] [rbp+100h]
  __int64 v103; // [rsp+210h] [rbp+108h]
  unsigned int v104[12]; // [rsp+218h] [rbp+110h] BYREF
  _QWORD v105[10]; // [rsp+248h] [rbp+140h] BYREF
  _QWORD v106[12]; // [rsp+298h] [rbp+190h] BYREF

  v83 = a2;
  v97 = a1;
  if ( a2 - 2 <= 8 && (v8 = 0, a1) && a3 && a4 && (a4 == a2 || a4 == a2 - 1 || a4 == 1) )
  {
    HeapObject = 0;
    v89 = 0;
    IDeviceModel = COMInit::CoInitialize((COMInit *)&v89);
    if ( IDeviceModel < 0 )
      goto LABEL_160;
    memset_0(v105, 0, 0x48u);
    v10 = 0;
    v86 = 0;
    v11 = a2 - 1;
    v79 = 0;
    v90 = 0;
    v94 = 0;
    v92 = 0;
    v12 = 0;
    v77 = v11;
    v93 = 0;
    memset_0(v98, 0, 0x64u);
    memset_0(v99, 0, 0x64u);
    v84 = 0;
    v13 = 0.0;
    v80 = 0.0;
    v14 = 0.0;
    v81 = 0.0;
    v87 = 1;
    v88 = 1;
    if ( v11 )
    {
      v15 = v11;
      v16 = v11;
      v17 = v104;
      while ( v16 )
      {
        *v17++ = 1;
        --v16;
      }
      memset_0(v105, 0, 8 * v15);
      v11 = v77;
    }
    if ( a4 == 1 )
    {
      v104[0] = *a3;
    }
    else if ( v11 )
    {
      v26 = 0;
      if ( a4 == v83 )
        v26 = 1;
      memcpy_0(v104, &a3[v26], 4LL * v11);
      v72[0] = 0;
      goto LABEL_18;
    }
    v72[0] = 0;
    if ( v11 )
    {
      LODWORD(v12) = 0;
LABEL_18:
      v18 = v79;
      while ( 1 )
      {
        v19 = 0;
        v91 = 0;
        v20 = 0;
        v74 = 0;
        v21 = 0;
        v95 = 0;
        v85 = 0;
        v73 = 0;
        v76 = 0;
        *(float *)&v78 = 0.0;
        v72[1] = 0;
        if ( !v8 )
        {
          v22 = (CmmModels *)operator new(0xE0u);
          v8 = CmmModels::CmmModels(v22);
          if ( !v8 )
          {
            v12 = v92;
            IDeviceModel = -2147024882;
            v10 = v93;
            goto LABEL_138;
          }
          IDeviceModel = CmmModels::Initialize(
                           v8,
                           *(void **)(v97 + 8LL * (unsigned int)v12),
                           v83,
                           (unsigned int)v12,
                           0,
                           0,
                           0);
        }
        v23 = 0;
        if ( IDeviceModel < 0 )
          goto LABEL_92;
        v24 = (CmmModels *)operator new(0xE0u);
        v25 = CmmModels::CmmModels(v24);
        v75 = v25;
        v23 = v25;
        if ( v25 )
        {
          IDeviceModel = CmmModels::Initialize(
                           v25,
                           *(void **)(v97 + 8LL * (unsigned int)(v72[0] + 1)),
                           v83,
                           v72[0] + 1,
                           0,
                           0,
                           0);
          if ( IDeviceModel >= 0 )
          {
            IDeviceModel = CmmModels::GetIDeviceModel(v8, &v78, &v91);
            if ( IDeviceModel < 0 )
            {
LABEL_80:
              if ( v91 )
                (*(void (__fastcall **)(struct IDeviceModel *))(*(_QWORD *)v91 + 16LL))(v91);
              if ( v19 )
                (*(void (__fastcall **)(struct IDeviceModel *))(*(_QWORD *)v19 + 16LL))(v19);
              if ( v95 )
                ((void (__fastcall *)(struct IDeviceModelPlugIn *))v95->lpVtbl->Release)(v95);
              if ( v85 )
                ((void (__fastcall *)(struct IDeviceModelPlugIn *))v85->lpVtbl->Release)(v85);
              if ( v21 )
                (*(void (__fastcall **)(struct IDeviceModelData *))(*(_QWORD *)v21 + 16LL))(v21);
              if ( v20 )
                (*(void (__fastcall **)(struct IGamutBoundaryDescription *))(*(_QWORD *)v20 + 16LL))(v20);
              goto LABEL_92;
            }
            v27 = v78;
            if ( *(float *)&v78 != 0.0 )
            {
              IDeviceModel = CmmModels::GetIDeviceModelPlugIn(v8, &v95);
              if ( IDeviceModel < 0 )
              {
LABEL_33:
                v20 = v76;
                goto LABEL_80;
              }
            }
            IDeviceModel = CmmModels::GetIGamutBoundaryDescription(v8, &v73);
            if ( IDeviceModel < 0 )
            {
              v21 = v73;
              goto LABEL_33;
            }
            IDeviceModel = CmmModels::GetIDeviceModel(v23, &v72[1], &v74);
            if ( IDeviceModel < 0
              || (v28 = v72[1]) != 0 && (IDeviceModel = CmmModels::GetIDeviceModelPlugIn(v23, &v85), IDeviceModel < 0)
              || (IDeviceModel = CmmModels::GetIGamutBoundaryDescription(v23, &v76), IDeviceModel < 0)
              || v27
              && v28
              && ((v29 = v95,
                   v30 = v85,
                   IDeviceModel = ((__int64 (__fastcall *)(struct IDeviceModelPlugIn *, _QWORD, struct IDeviceModelPlugIn *))v95->lpVtbl->SetTransformDeviceModelInfo)(
                                    v95,
                                    (unsigned int)(v72[0] + 1),
                                    v85),
                   IDeviceModel < 0)
               || (IDeviceModel = ((__int64 (__fastcall *)(struct IDeviceModelPlugIn *, _QWORD, struct IDeviceModelPlugIn *))v30->lpVtbl->SetTransformDeviceModelInfo)(
                                    v30,
                                    (unsigned int)v72[0],
                                    v29),
                   IDeviceModel < 0)) )
            {
              v21 = v73;
              v20 = v76;
LABEL_44:
              v19 = v74;
              goto LABEL_80;
            }
            v20 = v76;
            v19 = v74;
            v21 = v73;
            v31 = v104[v72[0]];
            v82[0] = 0;
            IDeviceModel = CmmModels::CreateGamutMapModel(
                             v23,
                             v31,
                             v91,
                             v74,
                             (struct IDeviceModelPlugIn *)v70,
                             (struct IDeviceModelPlugIn *)v71,
                             v73,
                             v76,
                             (struct IGamutMapModel **)&v105[v72[0]],
                             v82);
            if ( IDeviceModel < 0 )
              goto LABEL_80;
            v82[0] = 0;
            if ( v72[0] )
            {
              v34 = v86;
LABEL_104:
              if ( v72[0] == v77 - 1 )
              {
                if ( (unsigned int)CmmModels::GetDeviceModelType(v75) == 7 )
                {
                  v100 = 0;
                  LODWORD(v73) = 0;
                  v72[1] = 0;
                  IDeviceModel = CmmModels::GetIDeviceModelData(v57, &v100);
                  if ( IDeviceModel < 0 )
                    goto LABEL_79;
                  v58 = v100;
                  IDeviceModel = (*(__int64 (__fastcall **)(struct IDeviceModelData *, struct IDeviceModelData **, int *))(*(_QWORD *)v100 + 88LL))(
                                   v100,
                                   &v73,
                                   &v72[1]);
                  if ( IDeviceModel >= 0 && (*(float *)&v73 != 0.0 || *(float *)&v72[1] != 1.0) )
                    v88 = 0;
                  (*(void (__fastcall **)(struct IDeviceModelData *))(*(_QWORD *)v58 + 16LL))(v58);
                  if ( IDeviceModel < 0 )
                    goto LABEL_78;
                  v57 = v75;
                }
                IDeviceModel = CmmModels::GetColorChannelInfo(v57, (struct ColorChannelInfo *)v99);
                if ( IDeviceModel < 0 )
                  goto LABEL_78;
                v59 = 0;
                for ( i = 0; (unsigned int)i < 8; i = (unsigned int)(i + 1) )
                {
                  if ( *(_DWORD *)&v99[4 * i + 4] == 7 )
                  {
                    v59 = 1;
                    break;
                  }
                }
                if ( (a5 & 0x100000) != 0 && (!(_DWORD)v59 || !v82[0]) )
                {
                  IDeviceModel = -2147024809;
                  goto LABEL_78;
                }
                v19 = v74;
                v94 = v74;
                (*(void (__fastcall **)(struct IDeviceModel *, __int64))(*(_QWORD *)v74 + 8LL))(v74, v59);
                IDeviceModel = CmmModels::GetIColorAppearanceModel(v75, &v92);
                if ( IDeviceModel >= 0 )
                {
                  if ( (a5 & 0x10000) == 0
                    || (IDeviceModel = CreateGamutDistanceFinder(v34, v18, v20, v84, &v93), IDeviceModel >= 0) )
                  {
                    *(_QWORD *)v82 = 0;
                    v61 = (*(__int64 (__fastcall **)(struct IGamutBoundaryDescription *, int *))(*(_QWORD *)v20 + 48LL))(
                            v20,
                            v82);
                    IDeviceModel = v61;
                    if ( v61 < 0 )
                    {
                      if ( v61 == -2147022884 )
                      {
                        v62 = (*(__int64 (__fastcall **)(struct IGamutBoundaryDescription *))(*(_QWORD *)v20 + 32LL))(v20);
                        v63 = v62;
                        if ( v62 < 2 )
                        {
                          v20 = v76;
                          goto LABEL_79;
                        }
                        v64 = (float *)operator new(saturated_mul(v62, 0xCu));
                        IDeviceModel = (*(__int64 (__fastcall **)(struct IGamutBoundaryDescription *, _QWORD, float *))(*(_QWORD *)v76 + 40LL))(
                                         v76,
                                         v63,
                                         v64);
                        if ( IDeviceModel >= 0 )
                        {
                          v80 = *v64;
                          v81 = v64[3 * v63 - 3];
                        }
                        operator delete(v64);
                        v20 = v76;
                        v19 = v74;
                      }
                    }
                    else
                    {
                      v80 = (*(float (__fastcall **)(_QWORD))(**(_QWORD **)v82 + 24LL))(*(_QWORD *)v82);
                      v81 = (*(float (__fastcall **)(_QWORD))(**(_QWORD **)v82 + 32LL))(*(_QWORD *)v82);
                      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v82 + 16LL))(*(_QWORD *)v82);
                    }
                    if ( IDeviceModel >= 0 )
                    {
                      v100 = (struct IDeviceModelData *)&v80;
                      v101 = 4;
                      v102 = &v81;
                      v103 = 4;
                      EtwEventWrite(g_etwHandle, LIGHTNESS_RANGE, 2, &v100);
                    }
                  }
                }
              }
            }
            else
            {
              DeviceModelType = CmmModels::GetDeviceModelType(v8);
              IDeviceModel = CmmModels::GetColorChannelInfo(v33, (struct ColorChannelInfo *)v98);
              if ( IDeviceModel < 0 )
                goto LABEL_44;
              v34 = v91;
              v86 = v91;
              (*(void (__fastcall **)(struct IDeviceModel *))(*(_QWORD *)v91 + 8LL))(v91);
              v35 = *(_QWORD *)v21;
              v90 = v21;
              (*(void (__fastcall **)(struct IDeviceModelData *))(v35 + 8))(v21);
              IDeviceModel = CmmModels::GetIColorAppearanceModel(v8, &v79);
              if ( IDeviceModel >= 0 )
              {
                for ( j = 0; (unsigned int)j < 8; j = (unsigned int)(j + 1) )
                {
                  if ( *(_DWORD *)&v98[4 * j + 4] == 7 )
                  {
                    v82[0] = 1;
                    break;
                  }
                }
                if ( DeviceModelType != 7 )
                  goto LABEL_76;
                v73 = 0;
                IDeviceModel = CmmModels::GetIDeviceModelData(v8, &v73);
                if ( IDeviceModel >= 0 )
                {
                  v37 = v73;
                  v72[1] = 0;
                  *(float *)&v78 = 0.0;
                  v86 = v34;
                  v38 = *(_QWORD *)v73;
                  v90 = v21;
                  IDeviceModel = (*(__int64 (__fastcall **)(struct IDeviceModelData *, int *, int *))(v38 + 88))(
                                   v73,
                                   &v72[1],
                                   &v78);
                  if ( IDeviceModel >= 0 )
                  {
                    if ( *(float *)&v72[1] == 0.0 && *(float *)&v78 == 1.0 )
                      goto LABEL_71;
                    LODWORD(v73) = 0;
                    v100 = 0;
                    v39 = *(_QWORD *)v37;
                    v87 = 0;
                    IDeviceModel = (*(__int64 (__fastcall **)(struct IDeviceModelData *, struct IDeviceModelData **, struct IDeviceModelData **))(v39 + 80))(
                                     v37,
                                     &v73,
                                     &v100);
                    if ( IDeviceModel >= 0 )
                    {
                      v40 = (unsigned int)v73;
                      v41 = 0;
                      v42 = v100;
                      do
                      {
                        for ( k = 0; k < v40; ++k )
                        {
                          v44 = k + v41 + 2 * k;
                          v45 = *((float *)v42 + v44);
                          if ( *(float *)&v98[4 * v41 + 36] > v45 )
                            *(float *)&v98[4 * v41 + 36] = v45;
                          v46 = *((float *)v42 + v44);
                          if ( v46 > *(float *)&v98[4 * v41 + 68] )
                            *(float *)&v98[4 * v41 + 68] = v46;
                        }
                        if ( *(float *)&v98[4 * v41 + 36] != 0.0 || 1.0 != *(float *)&v98[4 * v41 + 68] )
                          v84 = 1;
                        ++v41;
                      }
                      while ( v41 < 3 );
LABEL_71:
                      if ( v84 )
                      {
                        LODWORD(v47) = 0;
                        v48 = 0;
                        do
                        {
                          v49 = v48++;
                          v50 = 2LL * (int)v47;
                          v106[v50] = &v98[4 * v49 + 36];
                          v106[v50 + 1] = 4;
                          v51 = (int)v47;
                          v47 = (unsigned int)(v47 + 2);
                          v51 *= 2;
                          v106[v51 + 2] = &v98[4 * v49 + 68];
                          v106[v51 + 3] = 4;
                        }
                        while ( v48 < 3 );
                        EtwEventWrite(g_etwHandle, EXTENDED_RANGE, v47, v106);
                      }
                    }
                  }
                  (*(void (__fastcall **)(struct IDeviceModelData *))(*(_QWORD *)v37 + 16LL))(v37);
                  if ( IDeviceModel >= 0 )
                  {
LABEL_76:
                    v18 = v79;
                    v20 = v76;
                    v19 = v74;
                    goto LABEL_104;
                  }
                }
              }
              v18 = v79;
              v20 = v76;
LABEL_78:
              v19 = v74;
            }
LABEL_79:
            v23 = v75;
            goto LABEL_80;
          }
        }
        else
        {
          IDeviceModel = -2147024882;
        }
LABEL_92:
        (**(void (__fastcall ***)(CmmModels *, __int64))v8)(v8, 1);
        v11 = v77;
        v8 = v23;
        if ( IDeviceModel >= 0 )
        {
          LODWORD(v12) = v72[0] + 1;
          v72[0] = (int)v12;
          if ( (unsigned int)v12 < v77 )
            continue;
        }
        if ( v8 )
          (**(void (__fastcall ***)(CmmModels *, __int64))v8)(v8, 1);
        v12 = v92;
        v10 = v93;
        if ( IDeviceModel >= 0 )
        {
          v13 = v80;
          v14 = v81;
          break;
        }
LABEL_138:
        v53 = v86;
        v54 = v94;
        v52 = (__int64)v90;
LABEL_142:
        v55 = v79;
        goto LABEL_143;
      }
    }
    v52 = (__int64)v90;
    v53 = v86;
    v54 = v94;
    v101 = (__int64)v105;
    v100 = (struct IDeviceModelData *)v11;
    v55 = v79;
    v85 = 0;
    IDeviceModel = CreateCITEColorTransform(
                     (_DWORD)v86,
                     (_DWORD)v79,
                     (unsigned int)&v100,
                     (_DWORD)v12,
                     (__int64)v94,
                     a5,
                     (__int64)v98,
                     (__int64)v99,
                     (__int64)v90,
                     LODWORD(v13),
                     LODWORD(v14),
                     (__int64)&v85);
    if ( IDeviceModel >= 0 )
    {
      v56 = operator new(0x20u);
      *v56 = 0;
      v56[1] = 0;
      HeapObject = AllocateHeapObject(1129599565);
      if ( HeapObject )
      {
        if ( v10 )
        {
          (*(void (__fastcall **)(struct IGamutDistanceFinder *))(*(_QWORD *)v10 + 8LL))(v10);
          *((_DWORD *)v56 + 4) = 1;
          *((_QWORD *)v56 + 1) = v10;
        }
        *(_QWORD *)v56 = v85;
        *((_DWORD *)v56 + 5) = v87;
        *((_DWORD *)v56 + 6) = v88;
        v65 = HeapObject ^ 0x49434D20;
        *(_QWORD *)(v65 + 24) = v56;
        *(_DWORD *)(v65 + 4) = 1;
      }
      else
      {
        operator delete(v56);
        if ( v85 )
          ((void (__fastcall *)(struct IDeviceModelPlugIn *))v85->lpVtbl->Release)(v85);
        IDeviceModel = -2147024882;
      }
      goto LABEL_142;
    }
LABEL_143:
    if ( v53 )
      (*(void (__fastcall **)(struct IDeviceModel *))(*(_QWORD *)v53 + 16LL))(v53);
    if ( v55 )
      (*(void (__fastcall **)(struct IColorAppearanceModel *))(*(_QWORD *)v55 + 16LL))(v55);
    if ( v52 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v54 )
      (*(void (__fastcall **)(struct IDeviceModel *))(*(_QWORD *)v54 + 16LL))(v54);
    if ( v12 )
      (*(void (__fastcall **)(struct IColorAppearanceModel *))(*(_QWORD *)v12 + 16LL))(v12);
    v66 = v77;
    for ( m = 0; (unsigned int)m < v66; m = (unsigned int)(m + 1) )
    {
      v68 = v105[m];
      if ( v68 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
        v105[m] = 0;
      }
    }
    if ( v10 )
      (*(void (__fastcall **)(struct IGamutDistanceFinder *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( IDeviceModel < 0 )
LABEL_160:
      SetLastErrorFromHRESULT((unsigned int)IDeviceModel, 2011);
    COMInit::~COMInit((COMInit *)&v89);
    return HeapObject;
  }
  else
  {
    SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x18005082c  mov     rax, rsp
0x18005082f  mov     [rax+18h], rbx
0x180050833  push    rbp
0x180050834  push    rsi
0x180050835  push    rdi
0x180050836  push    r12
0x180050838  push    r13
0x18005083a  push    r14
0x18005083c  push    r15
0x18005083e  lea     rbp, [rax-258h]
0x180050845  sub     rsp, 320h
0x18005084c  movaps  xmmword ptr [rax-48h], xmm6
0x180050850  movaps  xmmword ptr [rax-58h], xmm7
0x180050854  mov     rax, cs:__security_cookie
0x18005085b  xor     rax, rsp
0x18005085e  mov     [rbp+250h+var_60], rax
0x180050865  lea     eax, [rdx-2]
0x180050868  mov     [rbp+250h+var_2A8], edx
0x18005086b  mov     [rbp+250h+var_248], rcx
0x18005086f  mov     r15d, r9d
0x180050872  mov     r12, r8
0x180050875  mov     edi, edx
0x180050877  cmp     eax, 8
0x18005087a  ja      loc_180051436
0x180050880  xor     r13d, r13d
0x180050883  test    rcx, rcx
0x180050886  jz      loc_180051436
0x18005088c  test    r8, r8
0x18005088f  jz      loc_180051436
0x180050895  test    r9d, r9d
0x180050898  jz      loc_180051436
0x18005089e  cmp     r9d, edx
0x1800508a1  jz      short loc_1800508B5
0x1800508a3  lea     eax, [rdx-1]
0x1800508a6  cmp     r9d, eax
0x1800508a9  jz      short loc_1800508B5
0x1800508ab  cmp     r9d, 1
0x1800508af  jnz     loc_180051436
0x1800508b5  lea     rcx, [rbp+250h+var_288]; this
0x1800508b9  mov     [rbp+250h+var_250], r13
0x1800508bd  mov     [rbp+250h+var_288], r13d
0x1800508c1  call    ?CoInitialize@COMInit@@QEAAJXZ; COMInit::CoInitialize(void)
0x1800508c6  mov     ebx, eax
0x1800508c8  test    eax, eax
0x1800508ca  js      loc_18005141B
0x1800508d0  xor     edx, edx; Val
0x1800508d2  lea     rcx, [rbp+250h+var_110]; void *
0x1800508d9  lea     r8d, [rdx+48h]; Size
0x1800508dd  call    memset_0
0x1800508e2  xor     esi, esi
0x1800508e4  mov     [rbp+250h+var_298], r13
0x1800508e8  dec     edi
0x1800508ea  mov     [rbp+250h+var_2C0], r13
0x1800508ee  xor     edx, edx; Val
0x1800508f0  mov     [rbp+250h+var_280], r13
0x1800508f4  lea     rcx, [rbp+250h+var_240]; void *
0x1800508f8  mov     [rbp+250h+var_260], r13
0x1800508fc  lea     r8d, [rsi+64h]; Size
0x180050900  mov     [rbp+250h+var_270], r13
0x180050904  mov     r14, r13
0x180050907  mov     [rbp+250h+var_2C8], edi
0x18005090a  mov     [rbp+250h+var_268], rsi
0x18005090e  call    memset_0
0x180050913  xor     edx, edx; Val
0x180050915  lea     r8d, [rsi+64h]; Size
0x180050919  lea     rcx, [rbp+250h+var_1D0]; void *
0x180050920  call    memset_0
0x180050925  mov     [rbp+250h+var_2A4], esi
0x180050928  xorps   xmm7, xmm7
0x18005092b  movss   [rbp+250h+var_2B8], xmm7
0x180050930  xorps   xmm6, xmm6
0x180050933  movss   [rbp+250h+var_2B4], xmm6
0x180050938  mov     [rbp+250h+var_290], 1
0x18005093f  mov     [rbp+250h+var_28C], 1
0x180050946  test    edi, edi
0x180050948  jz      short loc_180050971
0x18005094a  mov     r8d, edi
0x18005094d  lea     eax, [rsi+1]
0x180050950  mov     ecx, r8d
0x180050953  lea     rdi, [rbp+250h+var_140]
0x18005095a  rep stosd
0x18005095c  lea     rcx, [rbp+250h+var_110]; void *
0x180050963  shl     r8, 3; Size
0x180050967  xor     edx, edx; Val
0x180050969  call    memset_0
0x18005096e  mov     edi, [rbp+250h+var_2C8]
0x180050971  mov     eax, 4
0x180050976  cmp     r15d, 1
0x18005097a  jnz     loc_180050A53
0x180050980  mov     eax, [r12]
0x180050984  mov     [rbp+250h+var_140], eax
0x18005098a  mov     [rsp+350h+var_2F0], esi
0x18005098e  test    edi, edi
0x180050990  jz      loc_180050F59
0x180050996  mov     r14d, esi
0x180050999  movss   xmm6, cs:__real@3f800000
0x1800509a1  mov     r15, [rbp+250h+var_2C0]
0x1800509a5  xor     edi, edi
0x1800509a7  mov     [rbp+250h+var_278], 0
0x1800509af  xor     esi, esi
0x1800509b1  mov     [rsp+350h+var_2E0], rdi
0x1800509b6  xor     r12d, r12d
0x1800509b9  mov     [rbp+250h+var_258], rdi
0x1800509bd  mov     [rbp+250h+var_2A0], rdi
0x1800509c1  mov     [rsp+350h+var_2E8], r12
0x1800509c6  mov     [rbp+250h+var_2D0], rsi
0x1800509ca  mov     [rbp+250h+var_2C4], esi
0x1800509cd  mov     [rsp+350h+var_2F0+4], esi
0x1800509d1  test    r13, r13
0x1800509d4  jnz     short loc_180050A1F
0x1800509d6  mov     ecx, 0E0h; Size
0x1800509db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800509e0  mov     rcx, rax; this
0x1800509e3  call    ??0CmmModels@@QEAA@XZ; CmmModels::CmmModels(void)
0x1800509e8  mov     r13, rax
0x1800509eb  test    rax, rax
0x1800509ee  jz      loc_180051300
0x1800509f4  mov     rax, [rbp+250h+var_248]
0x1800509f8  mov     r9d, r14d; unsigned int
0x1800509fb  mov     r8d, [rbp+250h+var_2A8]; unsigned int
0x1800509ff  mov     rcx, r13; this
0x180050a02  mov     [rsp+350h+var_320], rsi; struct IXMLDOMDocument2 **
0x180050a07  mov     edx, r14d
0x180050a0a  mov     [rsp+350h+var_328], rsi; struct IXMLDOMDocument2 **
0x180050a0f  mov     [rsp+350h+var_330], rsi; struct IXMLDOMDocument2 **
0x180050a14  mov     rdx, [rax+rdx*8]; void *
0x180050a18  call    ?Initialize@CmmModels@@QEAAJPEAXIIPEAPEAUIXMLDOMDocument2@@11@Z; CmmModels::Initialize(void *,uint,uint,IXMLDOMDocument2 * *,IXMLDOMDocument2 * *,IXMLDOMDocument2 * *)
0x180050a1d  mov     ebx, eax
0x180050a1f  xor     r14d, r14d
0x180050a22  test    ebx, ebx
0x180050a24  js      loc_180050EF2
0x180050a2a  mov     ecx, 0E0h; Size
0x180050a2f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180050a34  mov     rcx, rax; this
0x180050a37  call    ??0CmmModels@@QEAA@XZ; CmmModels::CmmModels(void)
0x180050a3c  mov     [rsp+350h+var_2D8], rax
0x180050a41  mov     r14, rax
0x180050a44  test    rax, rax
0x180050a47  jnz     short loc_180050A85
0x180050a49  mov     ebx, 8007000Eh
0x180050a4e  jmp     loc_180050EED
0x180050a53  test    edi, edi
0x180050a55  jz      loc_18005098A
0x180050a5b  xor     edx, edx
0x180050a5d  mov     r8d, edi
0x180050a60  shl     r8, 2; Size
0x180050a64  lea     rcx, [rbp+250h+var_140]; void *
0x180050a6b  cmp     r15d, [rbp+250h+var_2A8]
0x180050a6f  cmovz   rdx, rax
0x180050a73  add     rdx, r12; Src
0x180050a76  call    memcpy_0
0x180050a7b  mov     [rsp+350h+var_2F0], r14d
0x180050a80  jmp     loc_180050999
0x180050a85  mov     r9d, [rsp+350h+var_2F0]
0x180050a8a  mov     rcx, r14; this
0x180050a8d  mov     rax, [rbp+250h+var_248]
0x180050a91  inc     r9d; unsigned int
0x180050a94  mov     r8d, [rbp+250h+var_2A8]; unsigned int
0x180050a98  mov     [rsp+350h+var_320], rsi; struct IXMLDOMDocument2 **
0x180050a9d  mov     [rsp+350h+var_328], rsi; struct IDeviceModelPlugIn *
0x180050aa2  mov     rdx, [rax+r9*8]; void *
0x180050aa6  mov     [rsp+350h+var_330], rsi; struct IDeviceModelPlugIn *
0x180050aab  call    ?Initialize@CmmModels@@QEAAJPEAXIIPEAPEAUIXMLDOMDocument2@@11@Z; CmmModels::Initialize(void *,uint,uint,IXMLDOMDocument2 * *,IXMLDOMDocument2 * *,IXMLDOMDocument2 * *)
0x180050ab0  mov     ebx, eax
0x180050ab2  test    eax, eax
0x180050ab4  js      loc_180050EED
0x180050aba  lea     r8, [rbp+250h+var_278]; struct IDeviceModel **
0x180050abe  mov     rcx, r13; this
0x180050ac1  lea     rdx, [rbp+250h+var_2C4]; int *
0x180050ac5  call    ?GetIDeviceModel@CmmModels@@QEAAJPEAHPEAPEAVIDeviceModel@@@Z; CmmModels::GetIDeviceModel(int *,IDeviceModel * *)
0x180050aca  mov     ebx, eax
0x180050acc  test    eax, eax
0x180050ace  js      loc_180050E71
0x180050ad4  mov     esi, [rbp+250h+var_2C4]
0x180050ad7  test    esi, esi
0x180050ad9  jz      short loc_180050AF6
0x180050adb  lea     rdx, [rbp+250h+var_258]; struct IDeviceModelPlugIn **
0x180050adf  mov     rcx, r13; this
0x180050ae2  call    ?GetIDeviceModelPlugIn@CmmModels@@QEAAJPEAPEAUIDeviceModelPlugIn@@@Z; CmmModels::GetIDeviceModelPlugIn(IDeviceModelPlugIn * *)
0x180050ae7  mov     ebx, eax
0x180050ae9  test    eax, eax
0x180050aeb  jns     short loc_180050AF6
0x180050aed  mov     rsi, [rbp+250h+var_2D0]
0x180050af1  jmp     loc_180050E71
0x180050af6  lea     rdx, [rsp+350h+var_2E8]; struct IGamutBoundaryDescription **
0x180050afb  mov     rcx, r13; this
0x180050afe  call    ?GetIGamutBoundaryDescription@CmmModels@@QEAAJPEAPEAVIGamutBoundaryDescription@@@Z; CmmModels::GetIGamutBoundaryDescription(IGamutBoundaryDescription * *)
0x180050b03  mov     ebx, eax
0x180050b05  test    eax, eax
0x180050b07  js      loc_1800512ED
0x180050b0d  lea     r8, [rsp+350h+var_2E0]; struct IDeviceModel **
0x180050b12  mov     rcx, r14; this
0x180050b15  lea     rdx, [rsp+350h+var_2F0+4]; int *
0x180050b1a  call    ?GetIDeviceModel@CmmModels@@QEAAJPEAHPEAPEAVIDeviceModel@@@Z; CmmModels::GetIDeviceModel(int *,IDeviceModel * *)
0x180050b1f  mov     ebx, eax
0x180050b21  test    eax, eax
0x180050b23  js      short loc_180050B9B
0x180050b25  mov     edi, [rsp+350h+var_2F0+4]
0x180050b29  test    edi, edi
0x180050b2b  jz      short loc_180050B3F
0x180050b2d  lea     rdx, [rbp+250h+var_2A0]; struct IDeviceModelPlugIn **
0x180050b31  mov     rcx, r14; this
0x180050b34  call    ?GetIDeviceModelPlugIn@CmmModels@@QEAAJPEAPEAUIDeviceModelPlugIn@@@Z; CmmModels::GetIDeviceModelPlugIn(IDeviceModelPlugIn * *)
0x180050b39  mov     ebx, eax
0x180050b3b  test    eax, eax
0x180050b3d  js      short loc_180050B9B
0x180050b3f  lea     rdx, [rbp+250h+var_2D0]; struct IGamutBoundaryDescription **
0x180050b43  mov     rcx, r14; this
0x180050b46  call    ?GetIGamutBoundaryDescription@CmmModels@@QEAAJPEAPEAVIGamutBoundaryDescription@@@Z; CmmModels::GetIGamutBoundaryDescription(IGamutBoundaryDescription * *)
0x180050b4b  mov     ebx, eax
0x180050b4d  test    eax, eax
0x180050b4f  js      short loc_180050B9B
0x180050b51  test    esi, esi
0x180050b53  jz      short loc_180050BAE
0x180050b55  test    edi, edi
0x180050b57  jz      short loc_180050BAE
0x180050b59  mov     rsi, [rbp+250h+var_258]
0x180050b5d  mov     edi, [rsp+350h+var_2F0]
0x180050b61  mov     rcx, rsi
0x180050b64  mov     r12, [rbp+250h+var_2A0]
0x180050b68  mov     r8, r12
0x180050b6b  mov     rax, [rsi]
0x180050b6e  lea     edx, [rdi+1]
0x180050b71  mov     rax, [rax+40h]
0x180050b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b7a  mov     ebx, eax
0x180050b7c  test    eax, eax
0x180050b7e  js      short loc_180050B9B
0x180050b80  mov     rax, [r12]
0x180050b84  mov     r8, rsi
0x180050b87  mov     edx, edi
0x180050b89  mov     rcx, r12
0x180050b8c  mov     rax, [rax+40h]
0x180050b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b95  mov     ebx, eax
0x180050b97  test    eax, eax
0x180050b99  jns     short loc_180050BAE
0x180050b9b  mov     r12, [rsp+350h+var_2E8]
0x180050ba0  mov     rsi, [rbp+250h+var_2D0]
0x180050ba4  mov     rdi, [rsp+350h+var_2E0]
0x180050ba9  jmp     loc_180050E71
0x180050bae  mov     edx, [rsp+350h+var_2F0]
0x180050bb2  lea     rcx, [rbp+250h+var_2B0]
0x180050bb6  mov     rsi, [rbp+250h+var_2D0]
0x180050bba  lea     rax, [rbp+250h+var_110]
0x180050bc1  mov     rdi, [rsp+350h+var_2E0]
0x180050bc6  mov     r12, [rsp+350h+var_2E8]
0x180050bcb  mov     r9, rdi; struct IDeviceModel *
0x180050bce  mov     r8, [rbp+250h+var_278]; struct IDeviceModel *
0x180050bd2  lea     rax, [rax+rdx*8]
0x180050bd6  mov     edx, [rbp+rdx*4+250h+var_140]; unsigned int
0x180050bdd  mov     [rsp+350h+var_308], rcx; int *
0x180050be2  mov     rcx, r14; this
0x180050be5  mov     [rsp+350h+var_310], rax; struct IGamutMapModel **
0x180050bea  mov     [rsp+350h+var_318], rsi; struct IGamutBoundaryDescription *
0x180050bef  mov     [rsp+350h+var_320], r12; struct IGamutBoundaryDescription *
0x180050bf4  mov     [rbp+250h+var_2B0], 0
0x180050bfb  call    ?CreateGamutMapModel@CmmModels@@QEAAJKPEAVIDeviceModel@@0PEAUIDeviceModelPlugIn@@1PEAVIGamutBoundaryDescription@@2PEAPEAVIGamutMapModel@@PEAH@Z; CmmModels::CreateGamutMapModel(ulong,IDeviceModel *,IDeviceModel *,IDeviceModelPlugIn *,IDeviceModelPlugIn *,IGamutBoundaryDescription *,IGamutBoundaryDescription *,IGamutMapModel * *,int *)
0x180050c00  mov     ebx, eax
0x180050c02  test    eax, eax
0x180050c04  js      loc_180050E71
0x180050c0a  cmp     [rsp+350h+var_2F0], 0
0x180050c0f  mov     [rbp+250h+var_2B0], 0
0x180050c16  jnz     loc_180051041
0x180050c1c  mov     rcx, r13
0x180050c1f  call    ?GetDeviceModelType@CmmModels@@QEAA?AW4Enum@CdmpBaselineDeviceType@@XZ; CmmModels::GetDeviceModelType(void)
0x180050c24  lea     rdx, [rbp+250h+var_240]; struct ColorChannelInfo *
0x180050c28  mov     edi, eax
0x180050c2a  call    ?GetColorChannelInfo@CmmModels@@QEAAJPEAUColorChannelInfo@@@Z; CmmModels::GetColorChannelInfo(ColorChannelInfo *)
0x180050c2f  mov     ebx, eax
0x180050c31  test    eax, eax
0x180050c33  js      loc_180050BA4
0x180050c39  mov     r14, [rbp+250h+var_278]
0x180050c3d  mov     rcx, r14
0x180050c40  mov     [rbp+250h+var_298], r14
0x180050c44  mov     rax, [r14]
0x180050c47  mov     rax, [rax+8]
0x180050c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c50  mov     rax, [r12]
0x180050c54  mov     rcx, r12
0x180050c57  mov     [rbp+250h+var_280], r12
0x180050c5b  mov     rax, [rax+8]
0x180050c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c64  lea     rdx, [rbp+250h+var_2C0]; struct IColorAppearanceModel **
0x180050c68  mov     rcx, r13; this
0x180050c6b  call    ?GetIColorAppearanceModel@CmmModels@@QEAAJPEAPEAVIColorAppearanceModel@@@Z; CmmModels::GetIColorAppearanceModel(IColorAppearanceModel * *)
0x180050c70  mov     ebx, eax
0x180050c72  test    eax, eax
0x180050c74  js      loc_180050E5F
0x180050c7a  xor     ecx, ecx
0x180050c7c  cmp     ecx, 8
0x180050c7f  jnb     short loc_180050C93
0x180050c81  cmp     [rbp+rcx*4+250h+var_23C], 7
0x180050c86  jz      short loc_180050C8C
0x180050c88  inc     ecx
0x180050c8a  jmp     short loc_180050C7C
0x180050c8c  mov     [rbp+250h+var_2B0], 1
0x180050c93  cmp     edi, 7
0x180050c96  jnz     loc_180050E4D
0x180050c9c  lea     rdx, [rsp+350h+var_2E8]; struct IDeviceModelData **
  ... truncated ...
```
