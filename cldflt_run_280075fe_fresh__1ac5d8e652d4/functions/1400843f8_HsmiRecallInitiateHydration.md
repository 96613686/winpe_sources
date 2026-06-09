# HsmiRecallInitiateHydration

- ea: `0x1400843f8`
- end: `0x140084ea9`
- name: `HsmiRecallInitiateHydration`
- size: `2737`
- prototype: `char __fastcall(__int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140002aec`
- `0x140084eb0`

## callees

- `0x140003c50`
- `0x14000a44c`
- `0x14000cd0c`
- `0x140017c28`
- `0x14001826c`
- `0x14001e220`
- `0x140044de4`
- `0x140058cbc`
- `0x140059618`
- `0x1400697c0`
- `0x14006f16c`
- `0x1400702c4`
- `0x14007446c`
- `0x140076810`
- `0x140084390`
- `0x1400843f8`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140084a67`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140084a67`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140084614`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140084614`
- `ntoskrnl!KeSetEvent` at `0x140084e68`
- `ntoskrnl!KeSetEvent` at `0x140084e68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084e85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140084e85`
- `FLTMGR!FltLockUserBuffer` at `0x14008450c`
- `FLTMGR!FltLockUserBuffer` at `0x14008450c`
- `FLTMGR!FltReleasePushLockEx` at `0x140084e41`
- `FLTMGR!FltReleasePushLockEx` at `0x140084e41`

## pseudocode

```c
char __fastcall HsmiRecallInitiateHydration(__int64 a1)
{
  bool v2; // zf
  __int64 FileRangeNoLock; // rsi
  struct _FLT_CALLBACK_DATA *v4; // r12
  __int64 v5; // rax
  __int64 v6; // r14
  __int64 v7; // r15
  __int64 v8; // r13
  __int64 v9; // rcx
  void *v10; // rax
  __int64 v11; // rcx
  __int64 StreamSize; // rax
  signed __int64 v13; // rbx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  PFLT_IO_PARAMETER_BLOCK v15; // rcx
  int v16; // eax
  LARGE_INTEGER ByteOffset; // rax
  struct _MDL *MdlAddress; // rcx
  char *MappedSystemVa; // rbx
  __int64 v20; // r8
  char v21; // r15
  int v22; // edx
  __int64 v23; // rcx
  signed __int64 v24; // r8
  signed __int64 v25; // rcx
  unsigned int v26; // r15d
  int v27; // r9d
  __int64 v28; // r8
  __int64 v29; // r13
  signed __int64 v30; // r11
  bool v31; // cf
  __int64 v32; // r13
  signed __int64 v33; // rcx
  int v34; // edx
  __int64 v35; // r8
  char *v36; // rbx
  LARGE_INTEGER v37; // rcx
  signed __int64 v38; // rdx
  signed __int64 v39; // r9
  signed __int64 v40; // rdx
  __int64 v41; // rax
  __int64 v42; // r8
  int v43; // eax
  int v44; // ecx
  unsigned int v45; // eax
  char v46; // al
  __int64 *v47; // rax
  __int64 *v48; // r15
  PRKEVENT *p_Event; // r8
  __int64 v50; // rbx
  __int64 v51; // rcx
  __int64 v52; // rdx
  int Bitmap; // eax
  int v54; // r8d
  __int64 v55; // r10
  int v56; // r11d
  PDEVICE_OBJECT v57; // rcx
  __int64 v58; // rdx
  __int64 v60; // [rsp+48h] [rbp-E8h]
  __int64 v61; // [rsp+50h] [rbp-E0h]
  __int64 v62; // [rsp+B0h] [rbp-80h] BYREF
  int v63; // [rsp+B8h] [rbp-78h]
  int v64; // [rsp+BCh] [rbp-74h]
  signed __int64 v65; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v66; // [rsp+C8h] [rbp-68h]
  unsigned int v67; // [rsp+D0h] [rbp-60h]
  __int64 v68; // [rsp+D8h] [rbp-58h]
  char *v69; // [rsp+E0h] [rbp-50h]
  __int64 v70; // [rsp+E8h] [rbp-48h]
  __int64 v71; // [rsp+F0h] [rbp-40h]
  __int64 v72; // [rsp+F8h] [rbp-38h] BYREF
  PVOID v73; // [rsp+100h] [rbp-30h]
  signed __int64 v74; // [rsp+108h] [rbp-28h]
  __int64 v75; // [rsp+110h] [rbp-20h]
  signed __int64 QuadPart; // [rsp+118h] [rbp-18h]
  signed __int64 v77; // [rsp+120h] [rbp-10h]
  signed __int64 v78; // [rsp+128h] [rbp-8h]
  signed __int64 v79; // [rsp+130h] [rbp+0h]
  signed __int64 v80; // [rsp+138h] [rbp+8h]
  PRKEVENT Event; // [rsp+140h] [rbp+10h] BYREF
  PVOID P; // [rsp+148h] [rbp+18h]
  __int64 v83; // [rsp+150h] [rbp+20h]
  char v84; // [rsp+1B0h] [rbp+80h] BYREF
  char v85; // [rsp+1B8h] [rbp+88h]
  char v86; // [rsp+1C0h] [rbp+90h]
  char v87; // [rsp+1C8h] [rbp+98h]

  v2 = (*(_DWORD *)(a1 + 48) & 0x200) == 0;
  LODWORD(FileRangeNoLock) = 0;
  P = 0;
  v4 = 0;
  v69 = 0;
  QuadPart = 0;
  v67 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v62 = 0;
  v64 = 0;
  Event = 0;
  if ( v2 )
    v4 = *(struct _FLT_CALLBACK_DATA **)(a1 + 24);
  v5 = *(_QWORD *)(a1 + 112);
  v6 = *(_QWORD *)(a1 + 120);
  v71 = v5;
  v7 = *(_QWORD *)(v6 + 16);
  v75 = v7;
  v8 = *(_QWORD *)(v7 + 32);
  v9 = *(_QWORD *)(v7 + 16);
  v66 = v8;
  v68 = v9;
  if ( v5 )
    v10 = *(void **)(v5 + 72);
  else
    v10 = 0;
  v11 = *(_QWORD *)(a1 + 104);
  v83 = v11;
  v73 = v10;
  if ( !v10 && v4 )
  {
    P = (PVOID)HsmpCreateProcessInfo(v11);
    v73 = P;
  }
  HsmpAcquireReparseUpdateLock(v6, 0);
  HsmpAcquireBitmapLock(v6, 0);
  StreamSize = HsmpGetStreamSize(v6);
  v62 = StreamSize;
  v13 = StreamSize;
  ++*(_DWORD *)(a1 + 52);
  if ( *(_QWORD *)(a1 + 72) >= StreamSize )
    goto LABEL_30;
  if ( v4 )
  {
    Iopb = v4->Iopb;
    if ( (unsigned __int8)(Iopb->MajorFunction - 3) <= 1u && Iopb->MinorFunction != 2 )
    {
      FileRangeNoLock = (unsigned int)FltLockUserBuffer(v4);
      HsmDbgBreakOnStatus(FileRangeNoLock);
      if ( (int)FileRangeNoLock >= 0 )
      {
        v15 = v4->Iopb;
        if ( v15->MajorFunction == 3 && v15->MinorFunction != 2 )
        {
          v16 = *(_DWORD *)(a1 + 40);
          if ( (v16 & 0x100) == 0 && (v16 & 0xFu) < 3 )
          {
            ByteOffset = v15->Parameters.Read.ByteOffset;
            MdlAddress = v15->Parameters.Read.MdlAddress;
            QuadPart = ByteOffset.QuadPart;
            v85 = 1;
            if ( (MdlAddress->MdlFlags & 5) != 0 )
              MappedSystemVa = (char *)MdlAddress->MappedSystemVa;
            else
              MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
            v69 = MappedSystemVa;
            if ( !MappedSystemVa )
            {
              LODWORD(FileRangeNoLock) = -1073741670;
              HsmDbgBreakOnStatus(3221225626LL);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_qqqqLiqid(
                  WPP_GLOBAL_Control->AttachedDevice,
                  33,
                  v20,
                  a1,
                  v4,
                  v68,
                  v6,
                  *(_DWORD *)(v6 + 28),
                  v62,
                  v7,
                  v8,
                  -1073741670);
              }
              goto LABEL_30;
            }
            v67 = *((_DWORD *)v4->Iopb->Parameters.Create.EaBuffer + 10);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqqLiqid(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          WPP_GLOBAL_Control,
          a1,
          v4,
          v68,
          v6,
          *(_DWORD *)(v6 + 28),
          v62,
          v7,
          v8,
          FileRangeNoLock);
        v13 = v62;
        goto LABEL_51;
      }
      v13 = v62;
      goto LABEL_51;
    }
  }
  do
  {
LABEL_51:
    v26 = *(_DWORD *)(a1 + 48);
    v27 = (v26 >> 6) & 7;
    v63 = v27;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qqllcclqqLiqiii(
        WPP_GLOBAL_Control->AttachedDevice,
        34,
        *(_QWORD *)(a1 + 72),
        a1,
        *(_QWORD *)(a1 + 24),
        v26 & 0x1F,
        *(_DWORD *)(a1 + 40) & 0xF,
        (v26 & 0x200) != 0,
        BYTE1(*(_DWORD *)(a1 + 40)) & 1,
        v63,
        v68,
        v6,
        *(_DWORD *)(v6 + 28),
        v13,
        v75,
        v66,
        *(_QWORD *)(a1 + 72),
        *(_QWORD *)(a1 + 72) + *(_BYTE *)(a1 + 80));
      v27 = v63;
      v26 = *(_DWORD *)(a1 + 48);
      v13 = v62;
    }
    v28 = *(_QWORD *)(a1 + 72);
    v29 = *(_QWORD *)(a1 + 80);
    v30 = v28 & -(__int64)((*(_DWORD *)(v6 + 28) & 2) == 0) & 0xFFFFFFFFFFFFF000uLL;
    v31 = (*(_DWORD *)(v6 + 28) & 2) != 0;
    v80 = v30;
    v65 = v30;
    *(_DWORD *)(a1 + 48) = v26 & 0xFFFFFFDF;
    v32 = -(__int64)(v31 ? 0 : 0x1000) & ((v31 ? 0 : 0x1000) + v28 + v29 - 1);
    v79 = v32;
    if ( v30 < v32 )
    {
      v33 = v30;
      while ( v33 < v13 )
      {
        v34 = 16964;
        v84 = 0;
        v72 = 0;
        if ( v27 != 1 )
          v34 = 16982;
        FileRangeNoLock = (unsigned int)HsmiQueryFileRangeNoLock(
                                          v6,
                                          v34,
                                          (unsigned int)&v65,
                                          (unsigned int)&v62,
                                          (__int64)&v84,
                                          (__int64)&v72);
        HsmDbgBreakOnStatus(FileRangeNoLock);
        if ( (int)FileRangeNoLock < 0 )
        {
          v57 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v58 = 35;
            goto LABEL_126;
          }
          goto LABEL_31;
        }
        v32 = v72;
        if ( v79 < v72 )
          v32 = v79;
        if ( v84 )
        {
          v86 = 1;
          goto LABEL_103;
        }
        v77 = 0;
        v87 = 1;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qqllcclqqLiqiii(
            WPP_GLOBAL_Control->AttachedDevice,
            36,
            *(_QWORD *)(a1 + 72),
            a1,
            *(_QWORD *)(a1 + 24),
            *(_DWORD *)(a1 + 48) & 0x1F,
            *(_DWORD *)(a1 + 40) & 0xF,
            (*(_DWORD *)(a1 + 48) & 0x200) != 0,
            BYTE1(*(_DWORD *)(a1 + 40)) & 1,
            v63,
            v68,
            v6,
            *(_DWORD *)(v6 + 28),
            v62,
            v75,
            v66,
            *(_QWORD *)(a1 + 72),
            *(_QWORD *)(a1 + 72) + *(_BYTE *)(a1 + 80));
        }
        v36 = v69;
        if ( v69 )
        {
          v37 = v4->Iopb->Parameters.Read.ByteOffset;
          v38 = v37.QuadPart;
          if ( v65 > v37.QuadPart )
            v38 = v65;
          v77 = v38 - v37.QuadPart;
        }
        if ( (*(_DWORD *)(a1 + 40) & 0x100) != 0 && IoGetTopLevelIrp() && v4->Iopb->MajorFunction != 0xFF )
        {
          LODWORD(FileRangeNoLock) = -1073741595;
          HsmDbgBreakOnStatus(3221225701LL);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            LODWORD(v61) = -1073741595;
            WPP_SF_qqLiqiqd(
              WPP_GLOBAL_Control->AttachedDevice,
              37,
              (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
              v68,
              v6,
              *(_DWORD *)(v6 + 28),
              v62,
              v75,
              v66,
              v4,
              v61);
          }
          goto LABEL_31;
        }
        _InterlockedAdd((volatile signed __int32 *)(a1 + 52), 1u);
        v39 = v65;
        v78 = v65;
        if ( v36 )
        {
          v40 = QuadPart;
          if ( v65 > QuadPart )
            v40 = v65;
          v74 = v40;
          v41 = v32;
          if ( v67 + QuadPart < v32 )
            v41 = v67 + QuadPart;
        }
        else
        {
          v74 = 0;
          v41 = 0;
        }
        v42 = v71;
        v70 = v41;
        if ( v71 )
        {
          TlmInitializeCorrelationVector(v71, 0);
          v39 = v65;
          v42 = v71;
          v78 = v65;
        }
        v43 = *(_DWORD *)(a1 + 44);
        if ( v63 == 1 )
        {
          v44 = 0;
          v45 = v43 & 0xFFFFFF9F | 0x20;
        }
        else
        {
          v44 = v64;
          if ( (v43 & 0x20) == 0 )
            v44 = 1;
          v45 = v43 | 0x40;
        }
        *(_DWORD *)(a1 + 44) = v45;
        v46 = *(_DWORD *)(a1 + 48) & 0x1F;
        v64 = v44;
        if ( v46 == 4 )
          goto LABEL_93;
        if ( !v42 )
          goto LABEL_95;
        if ( (*(_DWORD *)(v42 + 40) & 0x400) != 0 )
        {
LABEL_93:
          v64 = v44 | 2;
          if ( !v42 )
          {
LABEL_95:
            v47 = *(__int64 **)(v6 + 104);
            goto LABEL_96;
          }
        }
        v47 = *(__int64 **)(v42 + 96);
LABEL_96:
        v48 = qword_1400294D0;
        p_Event = &Event;
        if ( v47 )
          v48 = v47;
        if ( (*(_DWORD *)(a1 + 40) & 0xFu) < 3 )
          p_Event = 0;
        v50 = 0;
        if ( v72 > v32 )
          v50 = v32;
        LODWORD(v70) = v70 - v74;
        LODWORD(v60) = *(_DWORD *)(a1 + 44);
        ((void (__fastcall *)(__int64, struct _FLT_CALLBACK_DATA *, _QWORD, __int64, int, signed __int64, __int64, __int64, __int64, __int64, char *, signed __int64, _DWORD, __int64 (__fastcall *)(_QWORD, _QWORD, _QWORD), _QWORD, _DWORD, __int64, PRKEVENT *, PVOID, __int64 *))qword_140029730)(
          v83,
          v4,
          *(_QWORD *)(v6 + 8),
          a1 + 88,
          v64,
          v78,
          v32 - v39,
          v50,
          v72 - v32,
          v60,
          &v69[v77],
          v74,
          v70,
          HsmiRecallHydrationCompletionCallback,
          *(_QWORD *)(a1 + 160),
          *(_DWORD *)(a1 + 168),
          a1,
          p_Event,
          v73,
          v48);
        *(_DWORD *)(a1 + 48) |= 0x20u;
LABEL_103:
        v51 = v32 - 1;
        LODWORD(v32) = v79;
        v33 = (-2048LL * (~(unsigned __int8)*(_DWORD *)(v6 + 28) & 2))
            & (((unsigned __int64)(~(unsigned __int8)*(_DWORD *)(v6 + 28) & 2) << 11) + v51);
        v65 = v33;
        if ( v33 >= v79 )
          break;
        v13 = v62;
        v27 = v63;
      }
    }
    if ( v85 && v86 && v87 )
    {
      v52 = 16964;
      if ( v63 != 1 )
        v52 = 16982;
      Bitmap = HsmiGetBitmap(v6, v52, 0);
      FileRangeNoLock = (unsigned int)HsmpBitmapCreateSnapshot(v56, v32, v54, Bitmap, v55);
      HsmDbgBreakOnStatus(FileRangeNoLock);
      if ( (int)FileRangeNoLock < 0 )
      {
        v57 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v58 = 38;
LABEL_126:
          WPP_SF_qqqqLiqid(
            v57->AttachedDevice,
            v58,
            v35,
            v66,
            v4,
            v71,
            v6,
            *(_DWORD *)(v6 + 28),
            v62,
            *(_QWORD *)(a1 + 72),
            *(_QWORD *)(a1 + 80),
            FileRangeNoLock);
        }
LABEL_31:
        v21 = 0;
        goto LABEL_32;
      }
    }
    else
    {
LABEL_30:
      if ( (int)FileRangeNoLock < 0 )
        goto LABEL_31;
    }
    if ( (*(_DWORD *)(a1 + 48) & 0x20) == 0 )
      goto LABEL_31;
    v21 = 1;
LABEL_32:
    if ( (int)FileRangeNoLock < 0
      || (*(_DWORD *)(a1 + 40) & 0xF) != 2
      || (*(_DWORD *)(a1 + 48) & 0x200) == 0
      || *(_DWORD *)(a1 + 52) != 1 )
    {
      break;
    }
    v22 = *(_DWORD *)(a1 + 48);
    v13 = v62;
    if ( (v22 & 0x1C0) == 0x40 && (*(_DWORD *)(a1 + 40) & 0x100) != 0 )
    {
      *(_DWORD *)(a1 + 48) = v22 ^ ((unsigned __int16)v22 ^ (unsigned __int16)(v22 + 64)) & 0x1C0;
    }
    else
    {
      v23 = *(_QWORD *)(a1 + 72);
      if ( v23 < v62 || (v22 & 0x400) != 0 )
      {
        v24 = v23 + *(_QWORD *)(a1 + 80);
      }
      else
      {
        v22 |= 0x400u;
        *(_DWORD *)(a1 + 48) = v22;
        v24 = 0;
      }
      *(_QWORD *)(a1 + 72) = v24;
      v25 = v13;
      if ( v24 + 4096 < v13 )
        v25 = v24 + 4096;
      *(_QWORD *)(a1 + 80) = v25 - v24;
      if ( v24 < v13 )
      {
        *(_DWORD *)(a1 + 44) &= ~0x20u;
        *(_DWORD *)(a1 + 48) = v22 & 0xFFFFFE3F | 0x40;
      }
    }
  }
  while ( *(_QWORD *)(a1 + 72) < v13 );
  HsmpReleaseBitmapLock(v6);
  FltReleasePushLockEx(*(_QWORD *)(v6 + 16) + 24LL, 0);
  HsmiRecallHydrationCompletionCallback(a1, (unsigned int)FileRangeNoLock, 0);
  if ( Event )
    KeSetEvent(Event, 0, 0);
  if ( P )
    ExFreePoolWithTag(P, 0x69507348u);
  return v21;
}

```

## disassembly

```asm
0x1400843f8  push    rbp
0x1400843fa  push    rbx
0x1400843fb  push    rsi
0x1400843fc  push    rdi
0x1400843fd  push    r12
0x1400843ff  push    r13
0x140084401  push    r14
0x140084403  push    r15
0x140084405  lea     rbp, [rsp-38h]
0x14008440a  sub     rsp, 168h
0x140084411  xor     edx, edx
0x140084413  mov     rdi, rcx
0x140084416  test    dword ptr [rcx+30h], 200h
0x14008441d  mov     esi, edx
0x14008441f  mov     [rbp+70h+P], rdx
0x140084423  mov     r12d, edx
0x140084426  mov     [rbp+70h+var_C0], rdx
0x14008442a  mov     [rbp+70h+var_88], rdx
0x14008442e  mov     [rbp+70h+var_D0], edx
0x140084431  mov     [rbp+70h+arg_8], dl
0x140084437  mov     [rbp+70h+arg_10], dl
0x14008443d  mov     [rbp+70h+arg_18], dl
0x140084443  mov     [rbp+70h+var_F0], rdx
0x140084447  mov     [rbp+70h+var_E4], edx
0x14008444a  mov     [rbp+70h+Event], rdx
0x14008444e  jnz     short loc_140084454
0x140084450  mov     r12, [rcx+18h]
0x140084454  mov     rax, [rcx+70h]
0x140084458  mov     r14, [rcx+78h]
0x14008445c  mov     [rbp+70h+var_B0], rax
0x140084460  mov     r15, [r14+10h]
0x140084464  mov     [rbp+70h+var_90], r15
0x140084468  mov     r13, [r15+20h]
0x14008446c  mov     rcx, [r15+10h]
0x140084470  mov     [rbp+70h+var_D8], r13
0x140084474  mov     [rbp+70h+var_C8], rcx
0x140084478  test    rax, rax
0x14008447b  jz      short loc_140084483
0x14008447d  mov     rax, [rax+48h]
0x140084481  jmp     short loc_140084486
0x140084483  mov     rax, rdx
0x140084486  mov     rcx, [rdi+68h]
0x14008448a  mov     [rbp+70h+var_50], rcx
0x14008448e  mov     [rbp+70h+var_A0], rax
0x140084492  test    rax, rax
0x140084495  jnz     short loc_1400844A9
0x140084497  test    r12, r12
0x14008449a  jz      short loc_1400844A9
0x14008449c  call    HsmpCreateProcessInfo
0x1400844a1  mov     [rbp+70h+P], rax
0x1400844a5  mov     [rbp+70h+var_A0], rax
0x1400844a9  xor     edx, edx
0x1400844ab  mov     rcx, r14
0x1400844ae  call    HsmpAcquireReparseUpdateLock
0x1400844b3  xor     edx, edx
0x1400844b5  mov     rcx, r14
0x1400844b8  call    HsmpAcquireBitmapLock
0x1400844bd  mov     rcx, r14
0x1400844c0  call    HsmpGetStreamSize
0x1400844c5  mov     [rbp+70h+var_F0], rax
0x1400844c9  mov     edx, 1
0x1400844ce  mov     eax, [rdi+34h]
0x1400844d1  mov     rbx, [rbp+70h+var_F0]
0x1400844d5  add     eax, edx
0x1400844d7  mov     [rdi+34h], eax
0x1400844da  cmp     [rdi+48h], rbx
0x1400844de  jge     loc_1400846AA
0x1400844e4  test    r12, r12
0x1400844e7  jz      loc_14008478D
0x1400844ed  mov     rcx, [r12+10h]
0x1400844f2  mov     al, [rcx+4]
0x1400844f5  sub     al, 3
0x1400844f7  cmp     al, dl
0x1400844f9  ja      loc_14008478D
0x1400844ff  cmp     byte ptr [rcx+5], 2
0x140084503  jz      loc_14008478D
0x140084509  mov     rcx, r12; CallbackData
0x14008450c  call    cs:__imp_FltLockUserBuffer
0x140084513  nop     dword ptr [rax+rax+00h]
0x140084518  mov     ecx, eax
0x14008451a  mov     esi, eax
0x14008451c  call    HsmDbgBreakOnStatus
0x140084521  test    esi, esi
0x140084523  jns     short loc_1400845A4
0x140084525  mov     r8, cs:WPP_GLOBAL_Control
0x14008452c  lea     rax, WPP_GLOBAL_Control
0x140084533  mov     edx, 1
0x140084538  cmp     r8, rax
0x14008453b  jz      loc_14008471E
0x140084541  mov     ecx, [r8+2Ch]
0x140084545  test    dl, cl
0x140084547  jz      loc_14008471E
0x14008454d  cmp     byte ptr [r8+29h], 2
0x140084552  jb      loc_14008471E
0x140084558  mov     rax, [rbp+70h+var_F0]
0x14008455c  mov     edx, 20h ; ' '
0x140084561  mov     rcx, [r8+18h]
0x140084565  mov     r9, rdi
0x140084568  mov     dword ptr [rsp+1A0h+var_148], esi
0x14008456c  mov     [rsp+1A0h+var_150], r13
0x140084571  mov     [rsp+1A0h+var_158], r15
0x140084576  mov     [rsp+1A0h+var_160], rax
0x14008457b  mov     eax, [r14+1Ch]
0x14008457f  mov     dword ptr [rsp+1A0h+var_168], eax
0x140084583  mov     rax, [rbp+70h+var_C8]
0x140084587  mov     [rsp+1A0h+var_170], r14
0x14008458c  mov     qword ptr [rsp+1A0h+Priority], rax
0x140084591  mov     qword ptr [rsp+1A0h+BugCheckOnFailure], r12
0x140084596  call    WPP_SF_qqqqLiqid
0x14008459b  mov     rbx, [rbp+70h+var_F0]
0x14008459f  jmp     loc_140084788
0x1400845a4  mov     rcx, [r12+10h]
0x1400845a9  cmp     byte ptr [rcx+4], 3
0x1400845ad  jnz     loc_140084724
0x1400845b3  cmp     byte ptr [rcx+5], 2
0x1400845b7  jz      loc_140084724
0x1400845bd  mov     eax, [rdi+28h]
0x1400845c0  bt      eax, 8
0x1400845c4  jb      loc_140084724
0x1400845ca  and     eax, 0Fh
0x1400845cd  mov     edx, 1
0x1400845d2  cmp     al, 3
0x1400845d4  jnb     loc_14008471E
0x1400845da  mov     rax, [rcx+28h]
0x1400845de  mov     rcx, [rcx+38h]; MemoryDescriptorList
0x1400845e2  mov     [rbp+70h+var_88], rax
0x1400845e6  mov     [rbp+70h+arg_8], dl
0x1400845ec  test    byte ptr [rcx+0Ah], 5
0x1400845f0  jz      short loc_1400845FC
0x1400845f2  mov     rbx, [rcx+18h]
0x1400845f6  mov     [rbp+70h+var_C0], rbx
0x1400845fa  jmp     short loc_14008462C
0x1400845fc  mov     r8d, edx; CacheType
0x1400845ff  mov     [rsp+1A0h+Priority], 40000010h; Priority
0x140084607  xor     edx, edx; AccessMode
0x140084609  mov     [rsp+1A0h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140084611  xor     r9d, r9d; RequestedAddress
0x140084614  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14008461b  nop     dword ptr [rax+rax+00h]
0x140084620  mov     rbx, rax
0x140084623  mov     [rbp+70h+var_C0], rax
0x140084627  mov     edx, 1
0x14008462c  test    rbx, rbx
0x14008462f  jnz     loc_14008470F
0x140084635  mov     esi, 0C000009Ah
0x14008463a  mov     ecx, esi
0x14008463c  call    HsmDbgBreakOnStatus
0x140084641  mov     rcx, cs:WPP_GLOBAL_Control
0x140084648  lea     rax, WPP_GLOBAL_Control
0x14008464f  lea     edx, [rbx+1]
0x140084652  cmp     rcx, rax
0x140084655  jz      short loc_1400846AA
0x140084657  mov     eax, [rcx+2Ch]
0x14008465a  test    dl, al
0x14008465c  jz      short loc_1400846AA
0x14008465e  cmp     byte ptr [rcx+29h], 2
0x140084662  jb      short loc_1400846AA
0x140084664  mov     rax, [rbp+70h+var_F0]
0x140084668  lea     edx, [rbx+21h]
0x14008466b  mov     rcx, [rcx+18h]
0x14008466f  mov     r9, rdi
0x140084672  mov     dword ptr [rsp+1A0h+var_148], esi
0x140084676  mov     [rsp+1A0h+var_150], r13
0x14008467b  mov     [rsp+1A0h+var_158], r15
0x140084680  mov     [rsp+1A0h+var_160], rax
0x140084685  mov     eax, [r14+1Ch]
0x140084689  mov     dword ptr [rsp+1A0h+var_168], eax
0x14008468d  mov     rax, [rbp+70h+var_C8]
0x140084691  mov     [rsp+1A0h+var_170], r14
0x140084696  mov     qword ptr [rsp+1A0h+Priority], rax
0x14008469b  mov     qword ptr [rsp+1A0h+BugCheckOnFailure], r12
0x1400846a0  call    WPP_SF_qqqqLiqid
0x1400846a5  mov     edx, 1
0x1400846aa  test    esi, esi
0x1400846ac  jns     loc_140084CCE
0x1400846b2  xor     r15b, r15b
0x1400846b5  test    esi, esi
0x1400846b7  js      loc_140084E2F
0x1400846bd  mov     eax, [rdi+28h]
0x1400846c0  and     al, 0Fh
0x1400846c2  cmp     al, 2
0x1400846c4  jnz     loc_140084E2F
0x1400846ca  test    dword ptr [rdi+30h], 200h
0x1400846d1  jz      loc_140084E2F
0x1400846d7  mov     eax, [rdi+34h]
0x1400846da  cmp     eax, edx
0x1400846dc  jnz     loc_140084E2F
0x1400846e2  mov     edx, [rdi+30h]
0x1400846e5  mov     eax, edx
0x1400846e7  mov     rbx, [rbp+70h+var_F0]
0x1400846eb  and     eax, 1C0h
0x1400846f0  cmp     eax, 40h ; '@'
0x1400846f3  jnz     short loc_14008472B
0x1400846f5  test    dword ptr [rdi+28h], 100h
0x1400846fc  jz      short loc_14008472B
0x1400846fe  lea     eax, [rdx+40h]
0x140084701  xor     eax, edx
0x140084703  and     eax, 1C0h
0x140084708  xor     eax, edx
0x14008470a  mov     [rdi+30h], eax
0x14008470d  jmp     short loc_14008477E
0x14008470f  mov     rax, [r12+10h]
0x140084714  mov     rcx, [rax+38h]
0x140084718  mov     eax, [rcx+28h]
0x14008471b  mov     [rbp+70h+var_D0], eax
0x14008471e  mov     rbx, [rbp+70h+var_F0]
0x140084722  jmp     short loc_14008478D
0x140084724  mov     edx, 1
0x140084729  jmp     short loc_14008471E
0x14008472b  mov     rcx, [rdi+48h]
0x14008472f  cmp     rcx, rbx
0x140084732  jl      short loc_140084746
0x140084734  bt      edx, 0Ah
0x140084738  jb      short loc_140084746
0x14008473a  bts     edx, 0Ah
0x14008473e  mov     [rdi+30h], edx
0x140084741  xor     r8d, r8d
0x140084744  jmp     short loc_14008474D
0x140084746  mov     r8, [rdi+50h]
0x14008474a  add     r8, rcx
0x14008474d  lea     rax, [r8+1000h]
0x140084754  mov     [rdi+48h], r8
0x140084758  cmp     rax, rbx
0x14008475b  mov     rcx, rbx
0x14008475e  cmovl   rcx, rax
0x140084762  sub     rcx, r8
0x140084765  mov     [rdi+50h], rcx
0x140084769  cmp     r8, rbx
0x14008476c  jge     short loc_14008477E
0x14008476e  and     edx, 0FFFFFE7Fh
0x140084774  or      edx, 40h
0x140084777  and     dword ptr [rdi+2Ch], 0FFFFFFDFh
0x14008477b  mov     [rdi+30h], edx
0x14008477e  cmp     [rdi+48h], rbx
0x140084782  jge     loc_140084E2F
0x140084788  mov     edx, 1
0x14008478d  mov     r15d, [rdi+30h]
0x140084791  mov     r9d, r15d
0x140084794  shr     r9d, 6
0x140084798  and     r9d, 7
0x14008479c  mov     [rbp+70h+var_E8], r9d
0x1400847a0  mov     r13, cs:WPP_GLOBAL_Control
0x1400847a7  lea     rax, WPP_GLOBAL_Control
0x1400847ae  cmp     r13, rax
0x1400847b1  jz      loc_140084877
0x1400847b7  mov     eax, [r13+2Ch]
0x1400847bb  test    dl, al
0x1400847bd  jz      loc_140084877
0x1400847c3  cmp     byte ptr [r13+29h], 4
0x1400847c8  jb      loc_140084877
0x1400847ce  mov     r8, [rdi+48h]
0x1400847d2  mov     r9d, r15d
0x1400847d5  mov     r11d, [rdi+28h]
0x1400847d9  and     r15d, 1Fh
0x1400847dd  mov     rcx, [rdi+50h]
0x1400847e1  mov     r10d, r11d
0x1400847e4  mov     rax, [rbp+70h+var_D8]
0x1400847e8  add     rcx, r8
0x1400847eb  mov     [rsp+1A0h+var_118], rcx
0x1400847f3  and     r11d, 0Fh
0x1400847f7  mov     ecx, [rbp+70h+var_E8]
0x1400847fa  mov     [rsp+1A0h+var_120], r8
0x140084802  mov     [rsp+1A0h+var_128], rax
0x140084807  mov     rax, [rbp+70h+var_90]
0x14008480b  mov     [rsp+1A0h+var_130], rax
0x140084810  mov     eax, [r14+1Ch]
0x140084814  mov     [rsp+1A0h+var_138], rbx
0x140084819  mov     [rsp+1A0h+var_140], eax
0x14008481d  mov     rax, [rbp+70h+var_C8]
0x140084821  mov     [rsp+1A0h+var_148], r14
0x140084826  mov     [rsp+1A0h+var_150], rax
0x14008482b  mov     rax, [rdi+18h]
0x14008482f  mov     dword ptr [rsp+1A0h+var_158], ecx
0x140084833  mov     rcx, [r13+18h]
0x140084837  shr     r9d, 9
0x14008483b  and     r9b, dl
0x14008483e  shr     r10d, 8
0x140084842  and     r10b, dl
0x140084845  mov     edx, 22h ; '"'
0x14008484a  mov     byte ptr [rsp+1A0h+var_160], r10b
0x14008484f  mov     byte ptr [rsp+1A0h+var_168], r9b
0x140084854  mov     r9, rdi
0x140084857  mov     dword ptr [rsp+1A0h+var_170], r11d
0x14008485c  mov     [rsp+1A0h+Priority], r15d
0x140084861  mov     qword ptr [rsp+1A0h+BugCheckOnFailure], rax
0x140084866  call    WPP_SF_qqllcclqqLiqiii
0x14008486b  mov     r9d, [rbp+70h+var_E8]
0x14008486f  mov     r15d, [rdi+30h]
0x140084873  mov     rbx, [rbp+70h+var_F0]
0x140084877  mov     ecx, [r14+1Ch]
0x14008487b  mov     r8, [rdi+48h]
0x14008487f  and     ecx, 2
0x140084882  mov     r13, [rdi+50h]
0x140084886  mov     eax, ecx
0x140084888  neg     eax
0x14008488a  sbb     r11, r11
0x14008488d  not     r11
0x140084890  and     r11, 0FFFFFFFFFFFFF000h
0x140084897  and     r11, r8
0x14008489a  neg     ecx
  ... truncated ...
```
