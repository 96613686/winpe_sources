# HsmiBitmapNORMALMarkBitmapOnDisk

- ea: `0x140085144`
- end: `0x1400866d8`
- name: `HsmiBitmapNORMALMarkBitmapOnDisk`
- size: `5524`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, PUCHAR Buffer, __int64, __int64, char)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140065c84`
- `0x140085144`

## callees

- `0x140003c50`
- `0x140008b74`
- `0x140009c7c`
- `0x14000a120`
- `0x140018c7c`
- `0x140018e90`
- `0x140019090`
- `0x1400197cc`
- `0x1400198d4`
- `0x140019d04`
- `0x14001a134`
- `0x14001a220`
- `0x14001a3e0`
- `0x14001a58c`
- `0x14001b85c`
- `0x140036400`
- `0x140071bb8`
- `0x140072eec`
- `0x140075f34`
- `0x140085144`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x1400865f2`
- `ntoskrnl!RtlComputeCrc32` at `0x1400865f2`

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
  __int64 v28; // rcx
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
  v11 = HsmExpandKernelStackAndCallout(HsmIBitmapNORMALQueryRangeExCallout, &Parameter);
  v64 = v11;
  HsmDbgBreakOnStatus((unsigned int)v11);
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
        v35 = (__int64 *)&`HsmBitmapGetNextLevelBlockState'::`2'::levelnMasks;
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
          v29 = ((unsigned __int8)`HsmBitmapGetNextLevelBlockState'::`2'::levelnStates[v34] < v36) + 1;
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
              HsmDbgBreakOnStatus((unsigned int)v11);
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
              HsmDbgBreakOnStatus((unsigned int)v11);
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
              HsmDbgBreakOnStatus((unsigned int)v11);
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
                v28 = (unsigned int)v11;
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
                    HsmDbgBreakOnStatus((unsigned int)v11);
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
                    HsmDbgBreakOnStatus((unsigned int)v11);
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
                    HsmDbgBreakOnStatus((unsigned int)v11);
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
                  v54 = (__int64 *)&`HsmBitmapGetNextLevelBlockState'::`2'::levelnMasks;
                v55 = *((_BYTE *)v54 + ((unsigned int)v71 & ((1 << (v52 + 2)) - 1)));
                v56 = Buffer[(unsigned __int64)v89 >> v53] & v55;
                if ( v56 == v55 )
                {
                  v19 = 3;
                }
                else if ( v56 )
                {
                  if ( !v67 )
                    v19 = ((unsigned __int8)`HsmBitmapGetNextLevelBlockState'::`2'::levelnStates[v88] < v56) + 1;
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
    v28 = 3221225701LL;
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
  v11 = HsmExpandKernelStackAndCallout(HsmIBitmapNORMALQueryRangeExCallout, &Parameter);
  v64 = v11;
  HsmDbgBreakOnStatus((unsigned int)v11);
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
0x140085144  mov     r11, rsp
0x140085147  mov     [r11+20h], r9
0x14008514b  mov     [r11+18h], r8
0x14008514f  mov     [r11+10h], rdx
0x140085153  mov     [r11+8], rcx
0x140085157  push    rbx
0x140085158  push    rsi
0x140085159  push    rdi
0x14008515a  push    r12
0x14008515c  push    r13
0x14008515e  push    r14
0x140085160  push    r15
0x140085162  sub     rsp, 180h
0x140085169  mov     rsi, rcx
0x14008516c  xor     r14d, r14d
0x14008516f  mov     edi, r14d
0x140085172  mov     [rsp+1B8h+var_150], r14d
0x140085177  mov     [r11-0F8h], r14
0x14008517e  mov     [r11-0F0h], r14
0x140085185  mov     [r11-110h], r14
0x14008518c  mov     [r11-0E8h], r14
0x140085193  mov     [r11-138h], r14
0x14008519a  mov     [rsp+1B8h+var_13C], r14d
0x14008519f  mov     [r11-0B8h], r14
0x1400851a6  xor     eax, eax
0x1400851a8  mov     [r11-0B0h], rax
0x1400851af  mov     [r11-0C8h], r14
0x1400851b6  mov     r13d, [rsp+1B8h+arg_20]
0x1400851be  cmp     r13d, 1
0x1400851c2  ja      loc_14008668E
0x1400851c8  mov     rax, [rsp+1B8h+arg_38]
0x1400851d0  mov     r10, [rax]
0x1400851d3  mov     [r11-0F8h], r10
0x1400851da  mov     rax, [rsp+1B8h+arg_40]
0x1400851e2  mov     r9, [rax]
0x1400851e5  mov     [r11-0F0h], r9
0x1400851ec  mov     ecx, [rcx+10h]
0x1400851ef  shr     ecx, 6
0x1400851f2  and     ecx, 3Fh
0x1400851f5  lea     eax, [r14+1]
0x1400851f9  shl     eax, cl
0x1400851fb  lea     ecx, [rax-1]
0x1400851fe  test    r10, rcx
0x140085201  jnz     loc_14008668E
0x140085207  test    r9, rcx
0x14008520a  jz      short loc_140085216
0x14008520c  cmp     r9, [rsi+8]
0x140085210  jnz     loc_14008668E
0x140085216  lfence
0x140085219  mov     rax, qword ptr [rsp+1B8h+arg_8]
0x140085221  mov     r8, [rax+r13*8]
0x140085225  mov     [rsp+1B8h+var_128], r8
0x14008522d  mov     [rsp+1B8h+var_48], r8
0x140085235  lea     rcx, [r10-1]
0x140085239  add     rcx, r8
0x14008523c  mov     rax, rcx
0x14008523f  cqo
0x140085241  idiv    r8
0x140085244  sub     rcx, rdx
0x140085247  mov     [rsp+1B8h+var_110], rcx
0x14008524f  mov     rax, r9
0x140085252  cqo
0x140085254  idiv    r8
0x140085257  mov     rax, r9
0x14008525a  sub     rax, rdx
0x14008525d  mov     [rsp+1B8h+var_E8], rax
0x140085265  test    r13d, r13d
0x140085268  jnz     short loc_140085280
0x14008526a  cmp     r9, [rsi+8]
0x14008526e  jnz     short loc_140085280
0x140085270  cmp     r9, rax
0x140085273  jz      short loc_140085280
0x140085275  add     rax, r8
0x140085278  mov     [rsp+1B8h+var_E8], rax
0x140085280  cmp     r10, rcx
0x140085283  jz      loc_140085443
0x140085289  mov     [rsp+1B8h+var_156], r14b
0x14008528e  mov     [rsp+1B8h+var_D8], r14
0x140085296  mov     rax, r10
0x140085299  cqo
0x14008529b  idiv    r8
0x14008529e  sub     r10, rdx
0x1400852a1  mov     [rsp+1B8h+var_C0], r10
0x1400852a9  mov     [rsp+1B8h+var_80], 6
0x1400852b5  mov     [rsp+1B8h+Parameter], r14
0x1400852bd  mov     [rsp+1B8h+var_88], rsi
0x1400852c5  lea     rax, [rsp+1B8h+var_C0]
0x1400852cd  mov     [rsp+1B8h+var_78], rax
0x1400852d5  lea     rax, [rsp+1B8h+var_F8]
0x1400852dd  mov     [rsp+1B8h+var_70], rax
0x1400852e5  lea     rax, [rsp+1B8h+var_156]
0x1400852ea  mov     [rsp+1B8h+var_68], rax
0x1400852f2  lea     rax, [rsp+1B8h+var_D8]
0x1400852fa  mov     [rsp+1B8h+var_60], rax
0x140085302  lea     rdx, [rsp+1B8h+Parameter]; Parameter
0x14008530a  lea     rcx, HsmIBitmapNORMALQueryRangeExCallout; Callout
0x140085311  call    HsmExpandKernelStackAndCallout
0x140085316  mov     edi, eax
0x140085318  mov     [rsp+1B8h+var_150], eax
0x14008531c  mov     ecx, eax
0x14008531e  call    HsmDbgBreakOnStatus
0x140085323  test    edi, edi
0x140085325  jns     short loc_14008538B
0x140085327  lea     r15, WPP_GLOBAL_Control
0x14008532e  mov     rcx, cs:WPP_GLOBAL_Control
0x140085335  cmp     rcx, r15
0x140085338  jz      loc_14008669A
0x14008533e  mov     eax, [rcx+2Ch]
0x140085341  test    al, 1
0x140085343  jz      loc_14008669A
0x140085349  cmp     byte ptr [rcx+29h], 2
0x14008534d  jb      loc_14008669A
0x140085353  mov     edx, 27h ; '''
0x140085358  lea     r8, [rsi+20h]
0x14008535c  mov     dword ptr [rsp+1B8h+var_180], edi
0x140085360  mov     rax, [rsp+1B8h+var_F8]
0x140085368  mov     [rsp+1B8h+var_188], rax
0x14008536d  mov     [rsp+1B8h+var_190], r8
0x140085372  mov     rax, [rsi]
0x140085375  mov     qword ptr [rsp+1B8h+var_198], rax
0x14008537a  mov     r9, rsi
0x14008537d  mov     rcx, [rcx+18h]
0x140085381  call    WPP_SF_qisid
0x140085386  jmp     loc_14008669A
0x14008538b  mov     r11b, [rsp+1B8h+arg_48]
0x140085393  mov     r8, [rsp+1B8h+var_128]
0x14008539b  cmp     [rsp+1B8h+var_156], r11b
0x1400853a0  jnz     loc_140085443
0x1400853a6  mov     r9, [rsp+1B8h+var_F8]
0x1400853ae  cmp     [rsp+1B8h+var_D8], r9
0x1400853b6  jl      loc_140085443
0x1400853bc  mov     r10, [rsp+1B8h+var_110]
0x1400853c4  sub     r10, r8
0x1400853c7  mov     [rsp+1B8h+var_110], r10
0x1400853cf  lea     r15, WPP_GLOBAL_Control
0x1400853d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400853dd  cmp     rcx, r15
0x1400853e0  jz      short loc_14008542C
0x1400853e2  mov     eax, [rcx+2Ch]
0x1400853e5  test    al, 1
0x1400853e7  jz      short loc_14008542C
0x1400853e9  mov     ebx, 4
0x1400853ee  cmp     [rcx+29h], bl
0x1400853f1  jb      short loc_140085431
0x1400853f3  lea     rax, [rsi+20h]
0x1400853f7  lea     edx, [rbx+24h]
0x1400853fa  mov     byte ptr [rsp+1B8h+var_178], r11b
0x1400853ff  mov     [rsp+1B8h+var_180], r10
0x140085404  mov     [rsp+1B8h+var_188], r9
0x140085409  mov     [rsp+1B8h+var_190], rax
0x14008540e  mov     rax, [rsi]
0x140085411  mov     qword ptr [rsp+1B8h+var_198], rax
0x140085416  mov     r9, rsi
0x140085419  mov     rcx, [rcx+18h]
0x14008541d  call    WPP_SF_qisiic
0x140085422  mov     r8, [rsp+1B8h+var_128]
0x14008542a  jmp     short loc_140085431
0x14008542c  mov     ebx, 4
0x140085431  mov     rax, [rsp+1B8h+var_110]
0x140085439  mov     [rsp+1B8h+var_F8], rax
0x140085441  jmp     short loc_14008544F
0x140085443  lea     r15, WPP_GLOBAL_Control
0x14008544a  mov     ebx, 4
0x14008544f  mov     r10, [rsi+8]
0x140085453  mov     r9, [rsp+1B8h+var_F0]
0x14008545b  cmp     r9, r10
0x14008545e  jz      loc_14008560F
0x140085464  cmp     r9, [rsp+1B8h+var_E8]
0x14008546c  jz      loc_14008560F
0x140085472  mov     [rsp+1B8h+var_156], r14b
0x140085477  mov     [rsp+1B8h+var_130], r14
0x14008547f  lea     rcx, [r9-1]
0x140085483  add     rcx, r8
0x140085486  mov     rax, rcx
0x140085489  cqo
0x14008548b  idiv    r8
0x14008548e  sub     rcx, rdx
0x140085491  mov     [rsp+1B8h+var_108], rcx
0x140085499  cmp     r9, r10
0x14008549c  jge     loc_140085559
0x1400854a2  mov     [rsp+1B8h+var_80], 6
0x1400854ae  mov     [rsp+1B8h+Parameter], r14
0x1400854b6  mov     [rsp+1B8h+var_88], rsi
0x1400854be  lea     rax, [rsp+1B8h+var_F0]
0x1400854c6  mov     [rsp+1B8h+var_78], rax
0x1400854ce  lea     rax, [rsp+1B8h+var_108]
0x1400854d6  mov     [rsp+1B8h+var_70], rax
0x1400854de  lea     rax, [rsp+1B8h+var_156]
0x1400854e3  mov     [rsp+1B8h+var_68], rax
0x1400854eb  lea     rax, [rsp+1B8h+var_130]
0x1400854f3  mov     [rsp+1B8h+var_60], rax
0x1400854fb  lea     rdx, [rsp+1B8h+Parameter]; Parameter
0x140085503  lea     rcx, HsmIBitmapNORMALQueryRangeExCallout; Callout
0x14008550a  call    HsmExpandKernelStackAndCallout
0x14008550f  mov     edi, eax
0x140085511  mov     [rsp+1B8h+var_150], eax
0x140085515  mov     ecx, eax
0x140085517  call    HsmDbgBreakOnStatus
0x14008551c  test    edi, edi
0x14008551e  jns     short loc_14008554F
0x140085520  mov     rcx, cs:WPP_GLOBAL_Control
0x140085527  cmp     rcx, r15
0x14008552a  jz      loc_14008669A
0x140085530  mov     eax, [rcx+2Ch]
0x140085533  test    al, 1
0x140085535  jz      loc_14008669A
0x14008553b  cmp     byte ptr [rcx+29h], 2
0x14008553f  jb      loc_14008669A
0x140085545  mov     edx, 29h ; ')'
0x14008554a  jmp     loc_140085358
0x14008554f  mov     r8, [rsp+1B8h+var_128]
0x140085557  jmp     short loc_14008556E
0x140085559  mov     [rsp+1B8h+var_156], 1
0x14008555e  mov     rax, [rsp+1B8h+var_108]
0x140085566  mov     [rsp+1B8h+var_130], rax
0x14008556e  mov     r11b, [rsp+1B8h+arg_48]
0x140085576  cmp     [rsp+1B8h+var_156], r11b
0x14008557b  jnz     loc_14008560F
0x140085581  mov     rax, [rsp+1B8h+var_108]
0x140085589  cmp     [rsp+1B8h+var_130], rax
0x140085591  jl      short loc_14008560F
0x140085593  mov     r9, [rsp+1B8h+var_E8]
0x14008559b  add     r9, r8
0x14008559e  mov     [rsp+1B8h+var_E8], r9
0x1400855a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400855ad  cmp     rcx, r15
0x1400855b0  jz      short loc_1400855FF
0x1400855b2  mov     eax, [rcx+2Ch]
0x1400855b5  test    al, 1
0x1400855b7  jz      short loc_1400855FF
0x1400855b9  cmp     [rcx+29h], bl
0x1400855bc  jb      short loc_1400855FF
0x1400855be  lea     r8, [rsi+20h]
0x1400855c2  mov     edx, 2Ah ; '*'
0x1400855c7  mov     byte ptr [rsp+1B8h+var_178], r11b
0x1400855cc  mov     [rsp+1B8h+var_180], r9
0x1400855d1  mov     rax, [rsp+1B8h+var_F0]
0x1400855d9  mov     [rsp+1B8h+var_188], rax
0x1400855de  mov     [rsp+1B8h+var_190], r8
0x1400855e3  mov     rax, [rsi]
0x1400855e6  mov     qword ptr [rsp+1B8h+var_198], rax
0x1400855eb  mov     r9, rsi
0x1400855ee  mov     rcx, [rcx+18h]
0x1400855f2  call    WPP_SF_qisiic
0x1400855f7  mov     r8, [rsp+1B8h+var_128]
0x1400855ff  mov     rax, [rsp+1B8h+var_E8]
0x140085607  mov     [rsp+1B8h+var_F0], rax
0x14008560f  mov     al, [rsp+1B8h+arg_48]
0x140085616  mov     [rsp+1B8h+var_157], al
0x14008561a  mov     [rsp+1B8h+var_156], al
0x14008561e  mov     [rsp+1B8h+var_D0], r13d
0x140085626  mov     r12, rsi
0x140085629  mov     [rsp+1B8h+var_108], rsi
0x140085631  mov     eax, r13d
0x140085634  neg     eax
0x140085636  sbb     rcx, rcx
0x140085639  and     rcx, 0FFFFFFFFFFFFC010h
0x140085640  add     rcx, 7FE0h
0x140085647  mov     [rsp+1B8h+var_118], rcx
0x14008564f  mov     [rsp+1B8h+var_A0], rcx
0x140085657  mov     rax, [rsp+1B8h+var_F8]
0x14008565f  cqo
0x140085661  idiv    r8
0x140085664  mov     qword ptr [rsp+1B8h+var_98], rax
0x14008566c  mov     r10, [rsp+1B8h+var_110]
0x140085674  mov     rax, r10
0x140085677  cqo
0x140085679  idiv    r8
0x14008567c  cqo
0x14008567e  idiv    rcx
0x140085681  mov     r11, rdx
0x140085684  mov     [rsp+1B8h+var_130], rdx
0x14008568c  mov     [rsp+1B8h+var_13C], edx
0x140085690  mov     r9, [rsp+1B8h+var_E8]
0x140085698  cmp     r9, r10
0x14008569b  jle     loc_140085955
0x1400856a1  mov     ecx, r13d
0x1400856a4  neg     ecx
0x1400856a6  sbb     eax, eax
0x1400856a8  and     eax, 0FFFFFFFCh
0x1400856ab  add     eax, 8
0x1400856ae  mov     [rsp+1B8h+var_140], eax
0x1400856b2  mov     dword ptr [rsp+1B8h+var_A8], eax
0x1400856b9  shl     eax, 2
0x1400856bc  mov     [rsp+1B8h+var_14C], eax
0x1400856c0  mov     [rsp+1B8h+var_C0], rax
0x1400856c8  mov     dword ptr [rsp+1B8h+var_50], eax
0x1400856cf  sub     r9, r10
0x1400856d2  mov     rax, r9
0x1400856d5  cqo
0x1400856d7  idiv    r8
0x1400856da  mov     r10, rax
0x1400856dd  mov     [rsp+1B8h+var_D8], rax
0x1400856e5  mov     [rsp+1B8h+var_148], eax
0x1400856e9  mov     ecx, eax
0x1400856eb  cmp     rcx, [rsp+1B8h+var_118]
0x1400856f3  jnb     loc_14008668E
0x1400856f9  mov     r9d, [rsp+1B8h+var_14C]
0x1400856fe  mov     [rsp+1B8h+var_120], r9d
0x140085706  mov     edx, r14d
  ... truncated ...
```
