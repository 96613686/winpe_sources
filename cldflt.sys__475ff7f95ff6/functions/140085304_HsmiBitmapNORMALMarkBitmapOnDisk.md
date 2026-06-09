# HsmiBitmapNORMALMarkBitmapOnDisk

- ea: `0x140085304`
- end: `0x140086898`
- name: `HsmiBitmapNORMALMarkBitmapOnDisk`
- size: `5524`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, unsigned int, _QWORD *, PUCHAR Buffer, __int64 *, __int64 *, char)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140065da4`
- `0x140085304`

## callees

- `0x140003c50`
- `0x140008b74`
- `0x140009c7c`
- `0x14000a120`
- `0x140018cfc`
- `0x140018f10`
- `0x140019110`
- `0x14001984c`
- `0x140019954`
- `0x140019d84`
- `0x14001a1b4`
- `0x14001a2a0`
- `0x14001a460`
- `0x14001a60c`
- `0x14001b8dc`
- `0x140036400`
- `0x140071cd8`
- `0x14007300c`
- `0x140076054`
- `0x140085304`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x1400867b2`
- `ntoskrnl!RtlComputeCrc32` at `0x1400867b2`

## pseudocode

```c
__int64 __fastcall HsmiBitmapNORMALMarkBitmapOnDisk(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        _QWORD *a6,
        PUCHAR Buffer,
        __int64 *a8,
        __int64 *a9,
        char a10)
{
  int v11; // edi
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rax
  PDEVICE_OBJECT v16; // rcx
  int v17; // edx
  char v18; // r10
  int v19; // ebx
  __int64 v20; // r10
  char v21; // r9
  signed __int64 v22; // rcx
  __int64 v23; // r11
  __int64 v24; // r10
  int v25; // r9d
  int v26; // edx
  __int64 v27; // rcx
  int v28; // ecx
  int v29; // r8d
  __int64 v30; // r10
  __int64 v31; // rax
  char v32; // dl
  char v33; // r9
  __int64 v34; // r10
  __int64 *v35; // rax
  unsigned __int8 v36; // cl
  int v37; // r8d
  PDEVICE_OBJECT v38; // rcx
  int v39; // edx
  __int64 *v40; // rcx
  int v41; // r8d
  PDEVICE_OBJECT v42; // rcx
  int v43; // edx
  __int64 v44; // rcx
  __int64 v45; // r9
  int v46; // r8d
  __int64 v47; // r8
  __int64 v48; // r11
  __int64 v49; // rdx
  char v50; // cl
  int v51; // r8d
  char v52; // dl
  char v53; // r8
  __int64 *v54; // rax
  char v55; // dl
  unsigned __int8 v56; // cl
  __int64 v57; // rcx
  __int64 v58; // r9
  bool v60; // [rsp+60h] [rbp-158h]
  char v61; // [rsp+62h] [rbp-156h] BYREF
  char v62; // [rsp+63h] [rbp-155h]
  char v63; // [rsp+64h] [rbp-154h]
  int v64; // [rsp+68h] [rbp-150h]
  int v65; // [rsp+6Ch] [rbp-14Ch]
  int v66; // [rsp+70h] [rbp-148h]
  char v67; // [rsp+74h] [rbp-144h]
  unsigned int v68; // [rsp+78h] [rbp-140h]
  int v69; // [rsp+7Ch] [rbp-13Ch]
  __int64 v70; // [rsp+80h] [rbp-138h] BYREF
  __int64 v71; // [rsp+88h] [rbp-130h] BYREF
  __int64 v72; // [rsp+90h] [rbp-128h]
  int v73; // [rsp+98h] [rbp-120h]
  unsigned __int64 v74; // [rsp+A0h] [rbp-118h]
  __int64 v75; // [rsp+A8h] [rbp-110h] BYREF
  __int64 v76; // [rsp+B0h] [rbp-108h] BYREF
  int v77; // [rsp+B8h] [rbp-100h]
  __int64 v78; // [rsp+C0h] [rbp-F8h] BYREF
  __int64 v79; // [rsp+C8h] [rbp-F0h] BYREF
  __int64 v80; // [rsp+D0h] [rbp-E8h] BYREF
  unsigned int v81; // [rsp+D8h] [rbp-E0h]
  __int64 v82; // [rsp+E0h] [rbp-D8h] BYREF
  unsigned int v83; // [rsp+E8h] [rbp-D0h]
  PVOID Address; // [rsp+F0h] [rbp-C8h] BYREF
  __int64 v85; // [rsp+F8h] [rbp-C0h] BYREF
  __int128 v86; // [rsp+100h] [rbp-B8h] BYREF
  __int64 *v87; // [rsp+110h] [rbp-A8h]
  signed __int64 v88; // [rsp+118h] [rbp-A0h]
  __int128 v89; // [rsp+120h] [rbp-98h] BYREF
  __int64 v90; // [rsp+130h] [rbp-88h]
  __int64 v91; // [rsp+138h] [rbp-80h]
  __int64 *v92; // [rsp+140h] [rbp-78h]
  __int64 *v93; // [rsp+148h] [rbp-70h]
  char *v94; // [rsp+150h] [rbp-68h]
  __int64 *v95; // [rsp+158h] [rbp-60h]
  __int64 Parameter; // [rsp+160h] [rbp-58h] BYREF
  __int64 v97; // [rsp+168h] [rbp-50h]
  __int64 v98; // [rsp+170h] [rbp-48h]
  int v99; // [rsp+1C8h] [rbp+10h]

  v99 = a2;
  v11 = 0;
  v64 = 0;
  v78 = 0;
  v79 = 0;
  v75 = 0;
  v80 = 0;
  v70 = 0;
  v69 = 0;
  v86 = 0u;
  Address = 0;
  if ( a5 > 1 )
    goto LABEL_164;
  v78 = *a8;
  v12 = *a9;
  v79 = *a9;
  v13 = (unsigned int)((1 << ((*(_DWORD *)(a1 + 16) >> 6) & 0x3F)) - 1);
  if ( (v13 & v78) != 0 || (v13 & v12) != 0 && v12 != *(_QWORD *)(a1 + 8) )
    goto LABEL_164;
  _mm_lfence();
  v14 = *(_QWORD *)(a2 + 8LL * a5);
  v72 = v14;
  v98 = v14;
  v75 = v14 + v78 - 1 - (v14 + v78 - 1) % v14;
  v15 = v12 - v12 % v14;
  v80 = v15;
  if ( !a5 && v12 == *(_QWORD *)(a1 + 8) && v12 != v15 )
    v80 = v14 + v15;
  if ( v78 == v14 + v78 - 1 - (v14 + v78 - 1) % v14 )
    goto LABEL_24;
  v61 = 0;
  v82 = 0;
  v85 = v78 - v78 % v14;
  v91 = 6;
  Parameter = 0;
  v90 = a1;
  v92 = &v85;
  v93 = &v78;
  v94 = &v61;
  v95 = &v82;
  v11 = HsmExpandKernelStackAndCallout(HsmIBitmapNORMALQueryRangeExCallout, (NTSTATUS *)&Parameter);
  v64 = v11;
  HsmDbgBreakOnStatus(v11);
  if ( v11 < 0 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v17 = 39;
LABEL_15:
      WPP_SF_qisid(v16->AttachedDevice, v17, a1 + 32, a1, *(_QWORD *)a1, a1 + 32, v78, v11);
      goto LABEL_166;
    }
    goto LABEL_166;
  }
  v14 = v72;
  if ( v61 != a10 || v82 < v78 )
  {
LABEL_24:
    v19 = 4;
  }
  else
  {
    v18 = v75 - v72;
    v75 -= v72;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    {
      v19 = 4;
    }
    else
    {
      v19 = 4;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qisiic(WPP_GLOBAL_Control->AttachedDevice, 40, v72, a1, *(_QWORD *)a1, a1 + 32, v78, v18, a10);
        v14 = v72;
      }
    }
    v78 = v75;
  }
  v20 = *(_QWORD *)(a1 + 8);
  if ( v79 == v20 || v79 == v80 )
  {
LABEL_42:
    v61 = a10;
    v83 = a5;
    v76 = a1;
    v22 = (-(__int64)(a5 != 0) & 0xFFFFFFFFFFFFC010uLL) + 32736;
    v74 = v22;
    v88 = v22;
    *(_QWORD *)&v89 = v78 / v14;
    v23 = v75 / v14 % v22;
    v71 = v23;
    v69 = v23;
    if ( v80 <= v75 )
      goto LABEL_58;
    v68 = a5 != 0 ? 4 : 8;
    LODWORD(v87) = v68;
    v65 = 4 * v68;
    v85 = 4 * v68;
    LODWORD(v97) = 4 * v68;
    v24 = (v80 - v75) / v14;
    v82 = v24;
    v66 = v24;
    if ( (unsigned int)v24 < v74 )
    {
      v25 = v65;
      v73 = v65;
      v26 = 0;
      v77 = 0;
      while ( v26 < (int)v24 )
      {
        v27 = (unsigned int)v85 - 1LL;
        if ( ((unsigned int)v27 & (unsigned int)v23) != 0 || (v81 = v25 + v26, v25 + v26 > (int)v24) )
        {
          LOBYTE(v27) = v83 == 0;
          HsmiBitmapNORMALSetNextLevelBlockState(v27, Buffer, (unsigned int)v23, a10 != 0 ? 3 : 0);
          v23 = (unsigned int)(v71 + 1);
          v69 = v71 + 1;
          ++v77;
          v25 = v65;
          LODWORD(v24) = v82;
        }
        else
        {
          *(_DWORD *)&Buffer[(unsigned int)v23 / v68] = -(a10 != 0);
          v23 = (unsigned int)(v25 + v23);
          v69 = v23;
          v77 = v81;
        }
        v71 = v23;
        LOBYTE(v14) = v72;
        v26 = v77;
      }
      if ( v26
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qisdiic(
          WPP_GLOBAL_Control->AttachedDevice,
          44,
          a1 + 32,
          a1,
          *(_QWORD *)a1,
          a1 + 32,
          a5,
          v75,
          v75 + v14 * v26,
          a10);
      }
      v22 = v74;
LABEL_58:
      v85 = v22;
      v60 = 0;
      v62 = 0;
      v63 = 0;
      if ( v78 >= v75 )
        goto LABEL_112;
      v72 = (__int64)v89 % v22;
      v81 = (__int64)v89 % v22;
      v29 = 4;
      v68 = 4;
      v65 = 4;
      v30 = *a6 * v22 + v81;
      v70 = v30;
      v31 = a5 - 1;
      v66 = a5 - 1;
      v82 = v31;
      v87 = (__int64 *)(a3 + 8 * v31);
      if ( *v87 == v30 )
      {
        v32 = *(_BYTE *)(v31 + a4);
        v60 = v32;
        v62 = 1;
        v63 = 1;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
        {
          goto LABEL_83;
        }
        WPP_SF_qisdil(WPP_GLOBAL_Control->AttachedDevice, 45, a1 + 32, a1, *(_QWORD *)a1, a1 + 32, a5, v30, v32);
        v29 = 4;
        goto LABEL_81;
      }
      if ( a5 )
      {
        v73 = 0;
        v33 = 0;
      }
      else
      {
        v73 = 1;
        v33 = 1;
      }
      v34 = v81 & ((1 << (v33 + 2)) - 1);
      v35 = &`HsmBitmapGetNextLevelBlockState'::`2'::level0Masks;
      if ( !v33 )
        v35 = &`HsmBitmapGetNextLevelBlockState'::`2'::levelnMasks;
      v36 = Buffer[(unsigned __int64)(unsigned int)v72 >> (v33 + 2)] & *((_BYTE *)v35 + v34);
      if ( v36 == *((_BYTE *)v35 + v34) )
      {
        v29 = 3;
LABEL_75:
        v68 = v29;
        goto LABEL_76;
      }
      if ( v36 )
      {
        v29 = 4;
        v68 = 4;
        if ( !v33 )
        {
          v29 = (*((_BYTE *)&`HsmBitmapGetNextLevelBlockState'::`2'::levelnStates + v34) < v36) + 1;
          goto LABEL_75;
        }
      }
      else
      {
        v29 = 0;
        v68 = 0;
      }
LABEL_76:
      v65 = v29;
      if ( v29 != (a10 != 0 ? 3 : 0) )
      {
        v32 = v29 == 1;
        v60 = v29 == 1;
        v62 = 0;
        v63 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
          {
LABEL_82:
            LODWORD(v30) = v70;
LABEL_83:
            if ( v29 != (a10 != 0 ? 3 : 0) )
            {
              v65 = v32;
              v11 = HsmiBitmapNORMALPrepareBlockForWrite(a1, v66, v30, v32, v29, (__int64)&Address, (__int64)&v86);
              HsmDbgBreakOnStatus(v11);
              if ( v11 < 0 )
              {
                v38 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_166;
                }
                v39 = 48;
                goto LABEL_89;
              }
              v40 = &v75;
              if ( v75 >= v79 )
                v40 = &v79;
              v11 = HsmiBitmapNORMALMarkBitmapOnDisk(
                      a1,
                      v99,
                      a3,
                      a4,
                      v66,
                      (__int64)&v70,
                      (PUCHAR)Address,
                      (__int64)&v78,
                      (__int64)v40,
                      a10);
              HsmDbgBreakOnStatus(v11);
              if ( v11 < 0 )
              {
                v38 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_166;
                }
                v39 = 49;
                goto LABEL_89;
              }
              v11 = HsmpFileCacheSetAddressRangeModified(Address);
              v64 = v11;
              HsmDbgBreakOnStatus(v11);
              if ( v11 < 0 )
              {
                v42 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_51;
                }
                v43 = 50;
LABEL_102:
                WPP_SF_qisdd(v42->AttachedDevice, v43, v41, a1, *(_QWORD *)a1, a1 + 32, a5, v11);
LABEL_51:
                v11 = HsmiBitmapTranslateIOStatus(v42, (unsigned int)v11);
                v28 = v11;
LABEL_165:
                HsmDbgBreakOnStatus(v28);
                goto LABEL_166;
              }
              v89 = v86;
              HsmIBitmapNORMALUnpinBlock(&v89);
              LODWORD(v86) = 0;
              Address = 0;
              if ( !v62 )
              {
                v45 = 2;
                if ( v68 != 1 )
                  v45 = 1;
                LOBYTE(v44) = v83 == 0;
                HsmiBitmapNORMALSetNextLevelBlockState(v44, Buffer, v81, v45);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                {
                  WPP_SF_qisdDiD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    a1 + 32,
                    v46,
                    a1,
                    *(_QWORD *)a1,
                    a1 + 32,
                    a5,
                    v72,
                    v70,
                    v65);
                }
              }
              *v87 = v70;
              v47 = a4;
              *(_BYTE *)(v82 + a4) = v60;
              v22 = v74;
LABEL_113:
              if ( v75 > v80 || v80 >= v79 )
                goto LABEL_163;
              v65 = 4;
              *(_QWORD *)&v89 = (unsigned int)v71;
              v48 = *a6 * v22 + (unsigned int)v71;
              v70 = v48;
              v49 = a5 - 1;
              v66 = a5 - 1;
              v82 = v49;
              v87 = (__int64 *)(a3 + 8 * v49);
              if ( *v87 == v48 )
              {
                v50 = *(_BYTE *)(v49 + v47);
                v60 = v50;
                v62 = 1;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
                {
LABEL_123:
                  if ( v19 != (a10 != 0 ? 3 : 0) )
                  {
                    v65 = v50;
                    v11 = HsmiBitmapNORMALPrepareBlockForWrite(a1, v49, v48, v50, v19, (__int64)&Address, (__int64)&v86);
                    HsmDbgBreakOnStatus(v11);
                    if ( v11 < 0 )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                      {
                        WPP_SF_qisdiDcd(
                          WPP_GLOBAL_Control->AttachedDevice,
                          a1 + 32,
                          v51,
                          a1,
                          *(_QWORD *)a1,
                          a1 + 32,
                          a5,
                          v70,
                          v65,
                          v19,
                          v11);
                      }
                      goto LABEL_166;
                    }
                    v11 = HsmiBitmapNORMALMarkBitmapOnDisk(
                            a1,
                            v99,
                            a3,
                            a4,
                            v66,
                            (__int64)&v70,
                            (PUCHAR)Address,
                            (__int64)&v80,
                            (__int64)&v79,
                            a10);
                    HsmDbgBreakOnStatus(v11);
                    if ( v11 < 0 )
                    {
                      v38 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                      {
                        goto LABEL_166;
                      }
                      v39 = 57;
LABEL_89:
                      WPP_SF_qisdd(v38->AttachedDevice, v39, v37, a1, *(_QWORD *)a1, a1 + 32, a5, v11);
                      goto LABEL_166;
                    }
                    v11 = HsmpFileCacheSetAddressRangeModified(Address);
                    v64 = v11;
                    HsmDbgBreakOnStatus(v11);
                    if ( v11 < 0 )
                    {
                      v42 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                      {
                        goto LABEL_51;
                      }
                      v43 = 58;
                      goto LABEL_102;
                    }
                    v89 = v86;
                    HsmIBitmapNORMALUnpinBlock(&v89);
                    LODWORD(v86) = 0;
                    if ( !v62 )
                    {
                      v58 = 2;
                      if ( v19 != 1 )
                        v58 = 1;
                      LOBYTE(v57) = v83 == 0;
                      HsmiBitmapNORMALSetNextLevelBlockState(v57, Buffer, v71, v58);
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
                      {
                        WPP_SF_qisdil(
                          WPP_GLOBAL_Control->AttachedDevice,
                          60,
                          a1 + 32,
                          a1,
                          *(_QWORD *)a1,
                          a1 + 32,
                          a5,
                          v70,
                          v65);
                      }
                    }
                    *v87 = v70;
                    *(_BYTE *)(v82 + a4) = v60;
                  }
LABEL_163:
                  *((_DWORD *)Buffer + 1023) = RtlComputeCrc32(0, Buffer, 0xFFCu);
                  goto LABEL_166;
                }
                WPP_SF_qisdil(WPP_GLOBAL_Control->AttachedDevice, 53, a1 + 32, a1, *(_QWORD *)a1, a1 + 32, a5, v48, v50);
              }
              else
              {
                if ( a5 )
                {
                  v73 = 0;
                  v52 = 0;
                }
                else
                {
                  v73 = 1;
                  v52 = 1;
                }
                v67 = v52;
                v53 = v52 + 2;
                v88 = (unsigned int)v71 & ((1 << (v52 + 2)) - 1);
                v54 = &`HsmBitmapGetNextLevelBlockState'::`2'::level0Masks;
                if ( !v52 )
                  v54 = &`HsmBitmapGetNextLevelBlockState'::`2'::levelnMasks;
                v55 = *((_BYTE *)v54 + ((unsigned int)v71 & ((1 << (v52 + 2)) - 1)));
                v56 = Buffer[(unsigned __int64)v89 >> v53] & v55;
                if ( v56 == v55 )
                {
                  v19 = 3;
                }
                else if ( v56 )
                {
                  if ( !v67 )
                    v19 = (*((_BYTE *)&`HsmBitmapGetNextLevelBlockState'::`2'::levelnStates + v88) < v56) + 1;
                }
                else
                {
                  v19 = 0;
                }
                v65 = v19;
                if ( v19 == (a10 != 0 ? 3 : 0) )
                  goto LABEL_121;
                v50 = v19 == 1;
                v60 = v19 == 1;
                v62 = 0;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
                {
                  goto LABEL_122;
                }
                WPP_SF_qisdiDc(
                  WPP_GLOBAL_Control->AttachedDevice,
                  55,
                  (unsigned __int8)v50,
                  a1,
                  *(_QWORD *)a1,
                  a1 + 32,
                  a5,
                  v48,
                  v50,
                  (unsigned int)(v19 - 1) <= 1);
              }
              LODWORD(v48) = v70;
LABEL_121:
              v50 = v60;
LABEL_122:
              LODWORD(v49) = v66;
              goto LABEL_123;
            }
            v22 = v74;
LABEL_112:
            v47 = a4;
            goto LABEL_113;
          }
          WPP_SF_qisdiDc(
            WPP_GLOBAL_Control->AttachedDevice,
            47,
            (unsigned __int8)v32,
            a1,
            *(_QWORD *)a1,
            a1 + 32,
            a5,
            v70,
            v32,
            (unsigned int)(v29 - 1) <= 1);
          v29 = v68;
        }
      }
LABEL_81:
      v32 = v60;
      goto LABEL_82;
    }
LABEL_164:
    v11 = -1073741595;
    v28 = -1073741595;
    goto LABEL_165;
  }
  v61 = 0;
  v71 = 0;
  v76 = v14 + v79 - 1 - (v14 + v79 - 1) % v14;
  if ( v79 >= v20 )
  {
    v61 = 1;
    v71 = v76;
    goto LABEL_35;
  }
  v91 = 6;
  Parameter = 0;
  v90 = a1;
  v92 = &v79;
  v93 = &v76;
  v94 = &v61;
  v95 = &v71;
  v11 = HsmExpandKernelStackAndCallout(HsmIBitmapNORMALQueryRangeExCallout, (NTSTATUS *)&Parameter);
  v64 = v11;
  HsmDbgBreakOnStatus(v11);
  if ( v11 >= 0 )
  {
    v14 = v72;
LABEL_35:
    if ( v61 == a10 && v71 >= v76 )
    {
      v21 = v14 + v80;
      v80 += v14;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qisiic(WPP_GLOBAL_Control->AttachedDevice, 42, a1 + 32, a1, *(_QWORD *)a1, a1 + 32, v79, v21, a10);
        v14 = v72;
      }
      v79 = v80;
    }
    goto LABEL_42;
  }
  v16 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v17 = 41;
    goto LABEL_15;
  }
LABEL_166:
  if ( (_DWORD)v86 )
    HsmIBitmapNORMALUnpinBlock(&v86);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140085304  mov     r11, rsp
0x140085307  mov     [r11+20h], r9
0x14008530b  mov     [r11+18h], r8
0x14008530f  mov     [r11+10h], rdx
0x140085313  mov     [r11+8], rcx
0x140085317  push    rbx
0x140085318  push    rsi
0x140085319  push    rdi
0x14008531a  push    r12
0x14008531c  push    r13
0x14008531e  push    r14
0x140085320  push    r15
0x140085322  sub     rsp, 180h
0x140085329  mov     rsi, rcx
0x14008532c  xor     r14d, r14d
0x14008532f  mov     edi, r14d
0x140085332  mov     [rsp+1B8h+var_150], r14d
0x140085337  mov     [r11-0F8h], r14
0x14008533e  mov     [r11-0F0h], r14
0x140085345  mov     [r11-110h], r14
0x14008534c  mov     [r11-0E8h], r14
0x140085353  mov     [r11-138h], r14
0x14008535a  mov     [rsp+1B8h+var_13C], r14d
0x14008535f  mov     [r11-0B8h], r14
0x140085366  xor     eax, eax
0x140085368  mov     [r11-0B0h], rax
0x14008536f  mov     [r11-0C8h], r14
0x140085376  mov     r13d, [rsp+1B8h+arg_20]
0x14008537e  cmp     r13d, 1
0x140085382  ja      loc_14008684E
0x140085388  mov     rax, [rsp+1B8h+arg_38]
0x140085390  mov     r10, [rax]
0x140085393  mov     [r11-0F8h], r10
0x14008539a  mov     rax, [rsp+1B8h+arg_40]
0x1400853a2  mov     r9, [rax]
0x1400853a5  mov     [r11-0F0h], r9
0x1400853ac  mov     ecx, [rcx+10h]
0x1400853af  shr     ecx, 6
0x1400853b2  and     ecx, 3Fh
0x1400853b5  lea     eax, [r14+1]
0x1400853b9  shl     eax, cl
0x1400853bb  lea     ecx, [rax-1]
0x1400853be  test    r10, rcx
0x1400853c1  jnz     loc_14008684E
0x1400853c7  test    r9, rcx
0x1400853ca  jz      short loc_1400853D6
0x1400853cc  cmp     r9, [rsi+8]
0x1400853d0  jnz     loc_14008684E
0x1400853d6  lfence
0x1400853d9  mov     rax, qword ptr [rsp+1B8h+arg_8]
0x1400853e1  mov     r8, [rax+r13*8]
0x1400853e5  mov     [rsp+1B8h+var_128], r8
0x1400853ed  mov     [rsp+1B8h+var_48], r8
0x1400853f5  lea     rcx, [r10-1]
0x1400853f9  add     rcx, r8
0x1400853fc  mov     rax, rcx
0x1400853ff  cqo
0x140085401  idiv    r8
0x140085404  sub     rcx, rdx
0x140085407  mov     [rsp+1B8h+var_110], rcx
0x14008540f  mov     rax, r9
0x140085412  cqo
0x140085414  idiv    r8
0x140085417  mov     rax, r9
0x14008541a  sub     rax, rdx
0x14008541d  mov     [rsp+1B8h+var_E8], rax
0x140085425  test    r13d, r13d
0x140085428  jnz     short loc_140085440
0x14008542a  cmp     r9, [rsi+8]
0x14008542e  jnz     short loc_140085440
0x140085430  cmp     r9, rax
0x140085433  jz      short loc_140085440
0x140085435  add     rax, r8
0x140085438  mov     [rsp+1B8h+var_E8], rax
0x140085440  cmp     r10, rcx
0x140085443  jz      loc_140085603
0x140085449  mov     [rsp+1B8h+var_156], r14b
0x14008544e  mov     [rsp+1B8h+var_D8], r14
0x140085456  mov     rax, r10
0x140085459  cqo
0x14008545b  idiv    r8
0x14008545e  sub     r10, rdx
0x140085461  mov     [rsp+1B8h+var_C0], r10
0x140085469  mov     [rsp+1B8h+var_80], 6
0x140085475  mov     [rsp+1B8h+Parameter], r14
0x14008547d  mov     [rsp+1B8h+var_88], rsi
0x140085485  lea     rax, [rsp+1B8h+var_C0]
0x14008548d  mov     [rsp+1B8h+var_78], rax
0x140085495  lea     rax, [rsp+1B8h+var_F8]
0x14008549d  mov     [rsp+1B8h+var_70], rax
0x1400854a5  lea     rax, [rsp+1B8h+var_156]
0x1400854aa  mov     [rsp+1B8h+var_68], rax
0x1400854b2  lea     rax, [rsp+1B8h+var_D8]
0x1400854ba  mov     [rsp+1B8h+var_60], rax
0x1400854c2  lea     rdx, [rsp+1B8h+Parameter]; Parameter
0x1400854ca  lea     rcx, HsmIBitmapNORMALQueryRangeExCallout; Callout
0x1400854d1  call    HsmExpandKernelStackAndCallout
0x1400854d6  mov     edi, eax
0x1400854d8  mov     [rsp+1B8h+var_150], eax
0x1400854dc  mov     ecx, eax
0x1400854de  call    HsmDbgBreakOnStatus
0x1400854e3  test    edi, edi
0x1400854e5  jns     short loc_14008554B
0x1400854e7  lea     r15, WPP_GLOBAL_Control
0x1400854ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1400854f5  cmp     rcx, r15
0x1400854f8  jz      loc_14008685A
0x1400854fe  mov     eax, [rcx+2Ch]
0x140085501  test    al, 1
0x140085503  jz      loc_14008685A
0x140085509  cmp     byte ptr [rcx+29h], 2
0x14008550d  jb      loc_14008685A
0x140085513  mov     edx, 27h ; '''
0x140085518  lea     r8, [rsi+20h]
0x14008551c  mov     dword ptr [rsp+1B8h+var_180], edi
0x140085520  mov     rax, [rsp+1B8h+var_F8]
0x140085528  mov     [rsp+1B8h+var_188], rax
0x14008552d  mov     [rsp+1B8h+var_190], r8
0x140085532  mov     rax, [rsi]
0x140085535  mov     qword ptr [rsp+1B8h+var_198], rax
0x14008553a  mov     r9, rsi
0x14008553d  mov     rcx, [rcx+18h]
0x140085541  call    WPP_SF_qisid
0x140085546  jmp     loc_14008685A
0x14008554b  mov     r11b, [rsp+1B8h+arg_48]
0x140085553  mov     r8, [rsp+1B8h+var_128]
0x14008555b  cmp     [rsp+1B8h+var_156], r11b
0x140085560  jnz     loc_140085603
0x140085566  mov     r9, [rsp+1B8h+var_F8]
0x14008556e  cmp     [rsp+1B8h+var_D8], r9
0x140085576  jl      loc_140085603
0x14008557c  mov     r10, [rsp+1B8h+var_110]
0x140085584  sub     r10, r8
0x140085587  mov     [rsp+1B8h+var_110], r10
0x14008558f  lea     r15, WPP_GLOBAL_Control
0x140085596  mov     rcx, cs:WPP_GLOBAL_Control
0x14008559d  cmp     rcx, r15
0x1400855a0  jz      short loc_1400855EC
0x1400855a2  mov     eax, [rcx+2Ch]
0x1400855a5  test    al, 1
0x1400855a7  jz      short loc_1400855EC
0x1400855a9  mov     ebx, 4
0x1400855ae  cmp     [rcx+29h], bl
0x1400855b1  jb      short loc_1400855F1
0x1400855b3  lea     rax, [rsi+20h]
0x1400855b7  lea     edx, [rbx+24h]
0x1400855ba  mov     byte ptr [rsp+1B8h+var_178], r11b
0x1400855bf  mov     [rsp+1B8h+var_180], r10
0x1400855c4  mov     [rsp+1B8h+var_188], r9
0x1400855c9  mov     [rsp+1B8h+var_190], rax
0x1400855ce  mov     rax, [rsi]
0x1400855d1  mov     qword ptr [rsp+1B8h+var_198], rax
0x1400855d6  mov     r9, rsi
0x1400855d9  mov     rcx, [rcx+18h]
0x1400855dd  call    WPP_SF_qisiic
0x1400855e2  mov     r8, [rsp+1B8h+var_128]
0x1400855ea  jmp     short loc_1400855F1
0x1400855ec  mov     ebx, 4
0x1400855f1  mov     rax, [rsp+1B8h+var_110]
0x1400855f9  mov     [rsp+1B8h+var_F8], rax
0x140085601  jmp     short loc_14008560F
0x140085603  lea     r15, WPP_GLOBAL_Control
0x14008560a  mov     ebx, 4
0x14008560f  mov     r10, [rsi+8]
0x140085613  mov     r9, [rsp+1B8h+var_F0]
0x14008561b  cmp     r9, r10
0x14008561e  jz      loc_1400857CF
0x140085624  cmp     r9, [rsp+1B8h+var_E8]
0x14008562c  jz      loc_1400857CF
0x140085632  mov     [rsp+1B8h+var_156], r14b
0x140085637  mov     [rsp+1B8h+var_130], r14
0x14008563f  lea     rcx, [r9-1]
0x140085643  add     rcx, r8
0x140085646  mov     rax, rcx
0x140085649  cqo
0x14008564b  idiv    r8
0x14008564e  sub     rcx, rdx
0x140085651  mov     [rsp+1B8h+var_108], rcx
0x140085659  cmp     r9, r10
0x14008565c  jge     loc_140085719
0x140085662  mov     [rsp+1B8h+var_80], 6
0x14008566e  mov     [rsp+1B8h+Parameter], r14
0x140085676  mov     [rsp+1B8h+var_88], rsi
0x14008567e  lea     rax, [rsp+1B8h+var_F0]
0x140085686  mov     [rsp+1B8h+var_78], rax
0x14008568e  lea     rax, [rsp+1B8h+var_108]
0x140085696  mov     [rsp+1B8h+var_70], rax
0x14008569e  lea     rax, [rsp+1B8h+var_156]
0x1400856a3  mov     [rsp+1B8h+var_68], rax
0x1400856ab  lea     rax, [rsp+1B8h+var_130]
0x1400856b3  mov     [rsp+1B8h+var_60], rax
0x1400856bb  lea     rdx, [rsp+1B8h+Parameter]; Parameter
0x1400856c3  lea     rcx, HsmIBitmapNORMALQueryRangeExCallout; Callout
0x1400856ca  call    HsmExpandKernelStackAndCallout
0x1400856cf  mov     edi, eax
0x1400856d1  mov     [rsp+1B8h+var_150], eax
0x1400856d5  mov     ecx, eax
0x1400856d7  call    HsmDbgBreakOnStatus
0x1400856dc  test    edi, edi
0x1400856de  jns     short loc_14008570F
0x1400856e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400856e7  cmp     rcx, r15
0x1400856ea  jz      loc_14008685A
0x1400856f0  mov     eax, [rcx+2Ch]
0x1400856f3  test    al, 1
0x1400856f5  jz      loc_14008685A
0x1400856fb  cmp     byte ptr [rcx+29h], 2
0x1400856ff  jb      loc_14008685A
0x140085705  mov     edx, 29h ; ')'
0x14008570a  jmp     loc_140085518
0x14008570f  mov     r8, [rsp+1B8h+var_128]
0x140085717  jmp     short loc_14008572E
0x140085719  mov     [rsp+1B8h+var_156], 1
0x14008571e  mov     rax, [rsp+1B8h+var_108]
0x140085726  mov     [rsp+1B8h+var_130], rax
0x14008572e  mov     r11b, [rsp+1B8h+arg_48]
0x140085736  cmp     [rsp+1B8h+var_156], r11b
0x14008573b  jnz     loc_1400857CF
0x140085741  mov     rax, [rsp+1B8h+var_108]
0x140085749  cmp     [rsp+1B8h+var_130], rax
0x140085751  jl      short loc_1400857CF
0x140085753  mov     r9, [rsp+1B8h+var_E8]
0x14008575b  add     r9, r8
0x14008575e  mov     [rsp+1B8h+var_E8], r9
0x140085766  mov     rcx, cs:WPP_GLOBAL_Control
0x14008576d  cmp     rcx, r15
0x140085770  jz      short loc_1400857BF
0x140085772  mov     eax, [rcx+2Ch]
0x140085775  test    al, 1
0x140085777  jz      short loc_1400857BF
0x140085779  cmp     [rcx+29h], bl
0x14008577c  jb      short loc_1400857BF
0x14008577e  lea     r8, [rsi+20h]
0x140085782  mov     edx, 2Ah ; '*'
0x140085787  mov     byte ptr [rsp+1B8h+var_178], r11b
0x14008578c  mov     [rsp+1B8h+var_180], r9
0x140085791  mov     rax, [rsp+1B8h+var_F0]
0x140085799  mov     [rsp+1B8h+var_188], rax
0x14008579e  mov     [rsp+1B8h+var_190], r8
0x1400857a3  mov     rax, [rsi]
0x1400857a6  mov     qword ptr [rsp+1B8h+var_198], rax
0x1400857ab  mov     r9, rsi
0x1400857ae  mov     rcx, [rcx+18h]
0x1400857b2  call    WPP_SF_qisiic
0x1400857b7  mov     r8, [rsp+1B8h+var_128]
0x1400857bf  mov     rax, [rsp+1B8h+var_E8]
0x1400857c7  mov     [rsp+1B8h+var_F0], rax
0x1400857cf  mov     al, [rsp+1B8h+arg_48]
0x1400857d6  mov     [rsp+1B8h+var_157], al
0x1400857da  mov     [rsp+1B8h+var_156], al
0x1400857de  mov     [rsp+1B8h+var_D0], r13d
0x1400857e6  mov     r12, rsi
0x1400857e9  mov     [rsp+1B8h+var_108], rsi
0x1400857f1  mov     eax, r13d
0x1400857f4  neg     eax
0x1400857f6  sbb     rcx, rcx
0x1400857f9  and     rcx, 0FFFFFFFFFFFFC010h
0x140085800  add     rcx, 7FE0h
0x140085807  mov     [rsp+1B8h+var_118], rcx
0x14008580f  mov     [rsp+1B8h+var_A0], rcx
0x140085817  mov     rax, [rsp+1B8h+var_F8]
0x14008581f  cqo
0x140085821  idiv    r8
0x140085824  mov     qword ptr [rsp+1B8h+var_98], rax
0x14008582c  mov     r10, [rsp+1B8h+var_110]
0x140085834  mov     rax, r10
0x140085837  cqo
0x140085839  idiv    r8
0x14008583c  cqo
0x14008583e  idiv    rcx
0x140085841  mov     r11, rdx
0x140085844  mov     [rsp+1B8h+var_130], rdx
0x14008584c  mov     [rsp+1B8h+var_13C], edx
0x140085850  mov     r9, [rsp+1B8h+var_E8]
0x140085858  cmp     r9, r10
0x14008585b  jle     loc_140085B15
0x140085861  mov     ecx, r13d
0x140085864  neg     ecx
0x140085866  sbb     eax, eax
0x140085868  and     eax, 0FFFFFFFCh
0x14008586b  add     eax, 8
0x14008586e  mov     [rsp+1B8h+var_140], eax
0x140085872  mov     dword ptr [rsp+1B8h+var_A8], eax
0x140085879  shl     eax, 2
0x14008587c  mov     [rsp+1B8h+var_14C], eax
0x140085880  mov     [rsp+1B8h+var_C0], rax
0x140085888  mov     dword ptr [rsp+1B8h+var_50], eax
0x14008588f  sub     r9, r10
0x140085892  mov     rax, r9
0x140085895  cqo
0x140085897  idiv    r8
0x14008589a  mov     r10, rax
0x14008589d  mov     [rsp+1B8h+var_D8], rax
0x1400858a5  mov     [rsp+1B8h+var_148], eax
0x1400858a9  mov     ecx, eax
0x1400858ab  cmp     rcx, [rsp+1B8h+var_118]
0x1400858b3  jnb     loc_14008684E
0x1400858b9  mov     r9d, [rsp+1B8h+var_14C]
0x1400858be  mov     [rsp+1B8h+var_120], r9d
0x1400858c6  mov     edx, r14d
  ... truncated ...
```
