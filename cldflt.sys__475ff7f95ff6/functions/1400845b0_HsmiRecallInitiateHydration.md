# HsmiRecallInitiateHydration

- ea: `0x1400845b0`
- end: `0x140085065`
- name: `HsmiRecallInitiateHydration`
- size: `2741`
- prototype: `char __fastcall(__int64)`
- caller_count: `2`
- callee_count: `16`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140002aec`
- `0x14008506c`

## callees

- `0x140003c50`
- `0x14000a44c`
- `0x14000cd0c`
- `0x140017ca8`
- `0x1400182ec`
- `0x14001e2a0`
- `0x140044ed4`
- `0x140058ddc`
- `0x140059738`
- `0x1400698e0`
- `0x14006f28c`
- `0x1400703e4`
- `0x14007458c`
- `0x140076948`
- `0x140084550`
- `0x1400845b0`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140084c25`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140084c25`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400847d0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400847d0`
- `ntoskrnl!KeSetEvent` at `0x140085024`
- `ntoskrnl!KeSetEvent` at `0x140085024`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085041`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085041`
- `FLTMGR!FltLockUserBuffer` at `0x1400846c5`
- `FLTMGR!FltLockUserBuffer` at `0x1400846c5`
- `FLTMGR!FltReleasePushLockEx` at `0x140084ffc`
- `FLTMGR!FltReleasePushLockEx` at `0x140084ffc`

## pseudocode

```c
char __fastcall HsmiRecallInitiateHydration(__int64 a1)
{
  bool v2; // zf
  NTSTATUS FileRangeNoLock; // r14d
  struct _FLT_CALLBACK_DATA *v4; // r12
  __int64 v5; // rax
  __int64 v6; // r15
  __int64 v7; // rsi
  __int64 v8; // r13
  __int64 v9; // rcx
  void *v10; // rax
  signed __int64 v11; // rbx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  PFLT_IO_PARAMETER_BLOCK v13; // rcx
  int v14; // eax
  signed __int64 QuadPart; // rax
  struct _MDL *MdlAddress; // rcx
  char *MappedSystemVa; // rax
  __int64 v18; // r8
  char v19; // si
  int v20; // edx
  __int64 v21; // rcx
  signed __int64 v22; // r8
  signed __int64 v23; // rcx
  unsigned int v24; // esi
  int v25; // r12d
  __int64 v26; // r8
  __int64 v27; // r11
  __int64 v28; // r13
  bool v29; // cf
  signed __int64 v30; // rcx
  int v31; // edx
  __int64 v32; // r8
  signed __int64 v33; // r12
  signed __int64 v34; // r11
  char *v35; // rsi
  struct _FLT_CALLBACK_DATA *v36; // rbx
  signed __int64 v37; // rcx
  signed __int64 v38; // rdx
  signed __int64 v39; // r9
  signed __int64 v40; // rdx
  signed __int64 v41; // rax
  __int64 v42; // rcx
  int v43; // eax
  int v44; // edx
  unsigned int v45; // eax
  char v46; // al
  __int64 *v47; // rax
  __int64 *v48; // rsi
  PRKEVENT *p_Event; // r8
  signed __int64 v50; // rbx
  signed __int64 v51; // rcx
  __int64 v52; // rdx
  int Bitmap; // eax
  int v54; // r8d
  __int64 v55; // r10
  int v56; // r11d
  PDEVICE_OBJECT v57; // rcx
  __int64 v58; // rdx
  __int64 v60; // [rsp+48h] [rbp-E8h]
  __int64 v61; // [rsp+50h] [rbp-E0h]
  __int64 StreamSize; // [rsp+B0h] [rbp-80h] BYREF
  int v63; // [rsp+B8h] [rbp-78h]
  int v64; // [rsp+BCh] [rbp-74h]
  signed __int64 v65; // [rsp+C0h] [rbp-70h] BYREF
  struct _FLT_CALLBACK_DATA *v66; // [rsp+C8h] [rbp-68h]
  __int64 v67; // [rsp+D0h] [rbp-60h]
  unsigned int v68; // [rsp+D8h] [rbp-58h]
  __int64 v69; // [rsp+E0h] [rbp-50h]
  char *v70; // [rsp+E8h] [rbp-48h]
  signed __int64 v71; // [rsp+F0h] [rbp-40h]
  __int64 v72; // [rsp+F8h] [rbp-38h]
  __int64 v73; // [rsp+100h] [rbp-30h] BYREF
  PVOID v74; // [rsp+108h] [rbp-28h]
  signed __int64 v75; // [rsp+110h] [rbp-20h]
  __int64 v76; // [rsp+118h] [rbp-18h]
  signed __int64 v77; // [rsp+120h] [rbp-10h]
  signed __int64 v78; // [rsp+128h] [rbp-8h]
  signed __int64 v79; // [rsp+130h] [rbp+0h]
  __int64 v80; // [rsp+138h] [rbp+8h]
  PRKEVENT Event; // [rsp+140h] [rbp+10h] BYREF
  PVOID P; // [rsp+148h] [rbp+18h]
  __int64 v83; // [rsp+150h] [rbp+20h]
  char v84; // [rsp+1B0h] [rbp+80h] BYREF
  char v85; // [rsp+1B8h] [rbp+88h]
  char v86; // [rsp+1C0h] [rbp+90h]
  char v87; // [rsp+1C8h] [rbp+98h]

  v2 = (*(_DWORD *)(a1 + 48) & 0x200) == 0;
  FileRangeNoLock = 0;
  P = 0;
  v4 = 0;
  v70 = 0;
  v77 = 0;
  v68 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  StreamSize = 0;
  v63 = 0;
  Event = 0;
  if ( v2 )
    v4 = *(struct _FLT_CALLBACK_DATA **)(a1 + 24);
  v5 = *(_QWORD *)(a1 + 112);
  v6 = *(_QWORD *)(a1 + 120);
  v66 = v4;
  v72 = v5;
  v7 = *(_QWORD *)(v6 + 16);
  v76 = v7;
  v8 = *(_QWORD *)(v7 + 32);
  v9 = *(_QWORD *)(v7 + 16);
  v67 = v8;
  v69 = v9;
  if ( v5 )
    v10 = *(void **)(v5 + 72);
  else
    v10 = 0;
  v83 = *(_QWORD *)(a1 + 104);
  v74 = v10;
  if ( !v10 && v4 )
  {
    P = (PVOID)HsmpCreateProcessInfo();
    v74 = P;
  }
  HsmpAcquireReparseUpdateLock(v6, 0);
  HsmpAcquireBitmapLock(v6, 0);
  StreamSize = HsmpGetStreamSize(v6);
  _InterlockedAdd((volatile signed __int32 *)(a1 + 52), 1u);
  v11 = StreamSize;
  if ( *(_QWORD *)(a1 + 72) >= StreamSize )
    goto LABEL_30;
  if ( v4 )
  {
    Iopb = v4->Iopb;
    if ( (unsigned __int8)(Iopb->MajorFunction - 3) <= 1u && Iopb->MinorFunction != 2 )
    {
      FileRangeNoLock = FltLockUserBuffer(v4);
      HsmDbgBreakOnStatus(FileRangeNoLock);
      if ( FileRangeNoLock >= 0 )
      {
        v13 = v4->Iopb;
        if ( v13->MajorFunction == 3 && v13->MinorFunction != 2 )
        {
          v14 = *(_DWORD *)(a1 + 40);
          if ( (v14 & 0x100) == 0 && (v14 & 0xFu) < 3 )
          {
            QuadPart = v13->Parameters.Read.ByteOffset.QuadPart;
            MdlAddress = v13->Parameters.Read.MdlAddress;
            v77 = QuadPart;
            v85 = 1;
            if ( (MdlAddress->MdlFlags & 5) != 0 )
              MappedSystemVa = (char *)MdlAddress->MappedSystemVa;
            else
              MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
            v70 = MappedSystemVa;
            if ( !MappedSystemVa )
            {
              FileRangeNoLock = -1073741670;
              HsmDbgBreakOnStatus(-1073741670);
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_qqqqLiqid(
                  WPP_GLOBAL_Control->AttachedDevice,
                  33,
                  v18,
                  a1,
                  v4,
                  v69,
                  v6,
                  *(_DWORD *)(v6 + 28),
                  StreamSize,
                  v7,
                  v8,
                  -1073741670);
              }
              goto LABEL_30;
            }
            v68 = *((_DWORD *)v4->Iopb->Parameters.Create.EaBuffer + 10);
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
          v69,
          v6,
          *(_DWORD *)(v6 + 28),
          StreamSize,
          v7,
          v8,
          FileRangeNoLock);
        v11 = StreamSize;
        goto LABEL_51;
      }
      v11 = StreamSize;
      goto LABEL_51;
    }
  }
  do
  {
LABEL_51:
    v24 = *(_DWORD *)(a1 + 48);
    v25 = (v24 >> 6) & 7;
    v64 = v25;
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
        v24 & 0x1F,
        *(_DWORD *)(a1 + 40) & 0xF,
        (v24 & 0x200) != 0,
        BYTE1(*(_DWORD *)(a1 + 40)) & 1,
        v25,
        v69,
        v6,
        *(_DWORD *)(v6 + 28),
        v11,
        v76,
        v67,
        *(_QWORD *)(a1 + 72),
        *(_QWORD *)(a1 + 72) + *(_BYTE *)(a1 + 80));
      v24 = *(_DWORD *)(a1 + 48);
      v11 = StreamSize;
    }
    v26 = *(_QWORD *)(a1 + 72);
    v27 = *(_QWORD *)(a1 + 80);
    v29 = (*(_DWORD *)(v6 + 28) & 2) != 0;
    v65 = v26 & -(__int64)((*(_DWORD *)(v6 + 28) & 2) == 0) & 0xFFFFFFFFFFFFF000uLL;
    v28 = v65;
    *(_DWORD *)(a1 + 48) = v24 & 0xFFFFFFDF;
    v80 = -(__int64)(v29 ? 0 : 0x1000) & ((v29 ? 0 : 0x1000) + v26 + v27 - 1);
    if ( v28 < v80 )
    {
      v30 = v28;
      while ( v30 < v11 )
      {
        v31 = 16964;
        v84 = 0;
        v73 = 0;
        if ( v25 != 1 )
          v31 = 16982;
        FileRangeNoLock = HsmiQueryFileRangeNoLock(
                            v6,
                            v31,
                            (unsigned int)&v65,
                            (unsigned int)&StreamSize,
                            (__int64)&v84,
                            (__int64)&v73);
        HsmDbgBreakOnStatus(FileRangeNoLock);
        if ( FileRangeNoLock < 0 )
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
        v33 = v73;
        v34 = v80;
        if ( v80 < v73 )
          v33 = v80;
        if ( v84 )
        {
          v86 = 1;
          goto LABEL_103;
        }
        v78 = 0;
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
            v64,
            v69,
            v6,
            *(_DWORD *)(v6 + 28),
            StreamSize,
            v76,
            v67,
            *(_QWORD *)(a1 + 72),
            *(_QWORD *)(a1 + 72) + *(_BYTE *)(a1 + 80));
        }
        v35 = v70;
        v36 = v66;
        if ( v70 )
        {
          v37 = v66->Iopb->Parameters.Read.ByteOffset.QuadPart;
          v38 = v37;
          if ( v65 > v37 )
            v38 = v65;
          v78 = v38 - v37;
        }
        if ( (*(_DWORD *)(a1 + 40) & 0x100) != 0 && IoGetTopLevelIrp() && v36->Iopb->MajorFunction != 0xFF )
        {
          FileRangeNoLock = -1073741595;
          HsmDbgBreakOnStatus(-1073741595);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            LODWORD(v61) = -1073741595;
            WPP_SF_qqLiqiqd(
              WPP_GLOBAL_Control->AttachedDevice,
              37,
              (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
              v69,
              v6,
              *(_DWORD *)(v6 + 28),
              StreamSize,
              v76,
              v67,
              v36,
              v61);
          }
          goto LABEL_31;
        }
        _InterlockedAdd((volatile signed __int32 *)(a1 + 52), 1u);
        v39 = v65;
        v79 = v65;
        if ( v35 )
        {
          v40 = v77;
          if ( v65 > v77 )
            v40 = v65;
          v75 = v40;
          v41 = v33;
          if ( v68 + v77 < v33 )
            v41 = v68 + v77;
        }
        else
        {
          v75 = 0;
          v41 = 0;
        }
        v42 = v72;
        v71 = v41;
        if ( v72 )
        {
          TlmInitializeCorrelationVector(v72, 0);
          v39 = v65;
          v42 = v72;
          v79 = v65;
        }
        v43 = *(_DWORD *)(a1 + 44);
        if ( v64 == 1 )
        {
          v44 = 0;
          v45 = v43 & 0xFFFFFF9F | 0x20;
        }
        else
        {
          v44 = v63;
          if ( (v43 & 0x20) == 0 )
            v44 = 1;
          v45 = v43 | 0x40;
        }
        *(_DWORD *)(a1 + 44) = v45;
        v46 = *(_DWORD *)(a1 + 48) & 0x1F;
        v63 = v44;
        if ( v46 == 4 )
          goto LABEL_93;
        if ( !v42 )
          goto LABEL_95;
        if ( (*(_DWORD *)(v42 + 40) & 0x400) != 0 )
        {
LABEL_93:
          v63 = v44 | 2;
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
        if ( v73 > v33 )
          v50 = v33;
        LODWORD(v71) = v71 - v75;
        LODWORD(v60) = *(_DWORD *)(a1 + 44);
        ((void (__fastcall *)(__int64, struct _FLT_CALLBACK_DATA *, _QWORD, __int64, int, signed __int64, signed __int64, signed __int64, __int64, __int64, char *, signed __int64, _DWORD, __int64 (__fastcall *)(__int64, int), _QWORD, _DWORD, __int64, PRKEVENT *, PVOID, __int64 *))qword_140029730)(
          v83,
          v66,
          *(_QWORD *)(v6 + 8),
          a1 + 88,
          v63,
          v79,
          v33 - v39,
          v50,
          v73 - v33,
          v60,
          &v70[v78],
          v75,
          v71,
          HsmiRecallHydrationCompletionCallback,
          *(_QWORD *)(a1 + 160),
          *(_DWORD *)(a1 + 168),
          a1,
          p_Event,
          v74,
          v48);
        *(_DWORD *)(a1 + 48) |= 0x20u;
        v34 = v80;
LABEL_103:
        v51 = v33 - 1;
        v25 = v64;
        v30 = (-2048LL * (~(unsigned __int8)*(_DWORD *)(v6 + 28) & 2))
            & (((unsigned __int64)(~(unsigned __int8)*(_DWORD *)(v6 + 28) & 2) << 11) + v51);
        v65 = v30;
        if ( v30 >= v34 )
          break;
        v11 = StreamSize;
      }
    }
    if ( v85 && v86 && v87 )
    {
      v52 = 16964;
      if ( v25 != 1 )
        v52 = 16982;
      Bitmap = HsmiGetBitmap(v6, v52, 0);
      FileRangeNoLock = HsmpBitmapCreateSnapshot(v28, v56, v54, Bitmap, v55);
      HsmDbgBreakOnStatus(FileRangeNoLock);
      if ( FileRangeNoLock < 0 )
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
            v32,
            v67,
            v66,
            v72,
            v6,
            *(_DWORD *)(v6 + 28),
            StreamSize,
            *(_QWORD *)(a1 + 72),
            *(_QWORD *)(a1 + 80),
            FileRangeNoLock);
        }
LABEL_31:
        v19 = 0;
        goto LABEL_32;
      }
    }
    else
    {
LABEL_30:
      if ( FileRangeNoLock < 0 )
        goto LABEL_31;
    }
    if ( (*(_DWORD *)(a1 + 48) & 0x20) == 0 )
      goto LABEL_31;
    v19 = 1;
LABEL_32:
    if ( FileRangeNoLock < 0
      || (*(_DWORD *)(a1 + 40) & 0xF) != 2
      || (*(_DWORD *)(a1 + 48) & 0x200) == 0
      || _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 52), 0, 0) != 1 )
    {
      break;
    }
    v20 = *(_DWORD *)(a1 + 48);
    v11 = StreamSize;
    if ( (v20 & 0x1C0) == 0x40 && (*(_DWORD *)(a1 + 40) & 0x100) != 0 )
    {
      *(_DWORD *)(a1 + 48) = v20 ^ ((unsigned __int16)v20 ^ (unsigned __int16)(v20 + 64)) & 0x1C0;
    }
    else
    {
      v21 = *(_QWORD *)(a1 + 72);
      if ( v21 < StreamSize || (v20 & 0x400) != 0 )
      {
        v22 = v21 + *(_QWORD *)(a1 + 80);
      }
      else
      {
        v20 |= 0x400u;
        *(_DWORD *)(a1 + 48) = v20;
        v22 = 0;
      }
      *(_QWORD *)(a1 + 72) = v22;
      v23 = v11;
      if ( v22 + 4096 < v11 )
        v23 = v22 + 4096;
      *(_QWORD *)(a1 + 80) = v23 - v22;
      if ( v22 < v11 )
      {
        *(_DWORD *)(a1 + 44) &= ~0x20u;
        *(_DWORD *)(a1 + 48) = v20 & 0xFFFFFE3F | 0x40;
      }
    }
  }
  while ( *(_QWORD *)(a1 + 72) < v11 );
  HsmpReleaseBitmapLock(v6);
  FltReleasePushLockEx(*(_QWORD *)(v6 + 16) + 24LL, 0);
  HsmiRecallHydrationCompletionCallback(a1, FileRangeNoLock);
  if ( Event )
    KeSetEvent(Event, 0, 0);
  if ( P )
    ExFreePoolWithTag(P, 0x69507348u);
  return v19;
}

```

## disassembly

```asm
0x1400845b0  push    rbp
0x1400845b2  push    rbx
0x1400845b3  push    rsi
0x1400845b4  push    rdi
0x1400845b5  push    r12
0x1400845b7  push    r13
0x1400845b9  push    r14
0x1400845bb  push    r15
0x1400845bd  lea     rbp, [rsp-38h]
0x1400845c2  sub     rsp, 168h
0x1400845c9  xor     edx, edx
0x1400845cb  mov     rdi, rcx
0x1400845ce  test    dword ptr [rcx+30h], 200h
0x1400845d5  mov     r14d, edx
0x1400845d8  mov     [rbp+70h+P], rdx
0x1400845dc  mov     r12d, edx
0x1400845df  mov     [rbp+70h+var_B8], rdx
0x1400845e3  mov     [rbp+70h+var_80], rdx
0x1400845e7  mov     [rbp+70h+var_C8], edx
0x1400845ea  mov     [rbp+70h+arg_8], dl
0x1400845f0  mov     [rbp+70h+arg_10], dl
0x1400845f6  mov     [rbp+70h+arg_18], dl
0x1400845fc  mov     [rbp+70h+var_F0], rdx
0x140084600  mov     [rbp+70h+var_E8], edx
0x140084603  mov     [rbp+70h+Event], rdx
0x140084607  jnz     short loc_14008460D
0x140084609  mov     r12, [rcx+18h]
0x14008460d  mov     rax, [rcx+70h]
0x140084611  mov     r15, [rcx+78h]
0x140084615  mov     [rbp+70h+var_D8], r12
0x140084619  mov     [rbp+70h+var_A8], rax
0x14008461d  mov     rsi, [r15+10h]
0x140084621  mov     [rbp+70h+var_88], rsi
0x140084625  mov     r13, [rsi+20h]
0x140084629  mov     rcx, [rsi+10h]
0x14008462d  mov     [rbp+70h+var_D0], r13
0x140084631  mov     [rbp+70h+var_C0], rcx
0x140084635  test    rax, rax
0x140084638  jz      short loc_140084640
0x14008463a  mov     rax, [rax+48h]
0x14008463e  jmp     short loc_140084643
0x140084640  mov     rax, rdx
0x140084643  mov     rcx, [rdi+68h]
0x140084647  mov     [rbp+70h+var_50], rcx
0x14008464b  mov     [rbp+70h+var_98], rax
0x14008464f  test    rax, rax
0x140084652  jnz     short loc_140084666
0x140084654  test    r12, r12
0x140084657  jz      short loc_140084666
0x140084659  call    HsmpCreateProcessInfo
0x14008465e  mov     [rbp+70h+P], rax
0x140084662  mov     [rbp+70h+var_98], rax
0x140084666  xor     edx, edx
0x140084668  mov     rcx, r15
0x14008466b  call    HsmpAcquireReparseUpdateLock
0x140084670  xor     edx, edx
0x140084672  mov     rcx, r15
0x140084675  call    HsmpAcquireBitmapLock
0x14008467a  mov     rcx, r15
0x14008467d  call    HsmpGetStreamSize
0x140084682  mov     [rbp+70h+var_F0], rax
0x140084686  mov     edx, 1
0x14008468b  lock add [rdi+34h], edx
0x14008468f  mov     rbx, [rbp+70h+var_F0]
0x140084693  cmp     [rdi+48h], rbx
0x140084697  jge     loc_14008486A
0x14008469d  test    r12, r12
0x1400846a0  jz      loc_140084955
0x1400846a6  mov     rcx, [r12+10h]
0x1400846ab  mov     al, [rcx+4]
0x1400846ae  sub     al, 3
0x1400846b0  cmp     al, dl
0x1400846b2  ja      loc_140084955
0x1400846b8  cmp     byte ptr [rcx+5], 2
0x1400846bc  jz      loc_140084955
0x1400846c2  mov     rcx, r12; CallbackData
0x1400846c5  call    cs:__imp_FltLockUserBuffer
0x1400846cc  nop     dword ptr [rax+rax+00h]
0x1400846d1  mov     ecx, eax
0x1400846d3  mov     r14d, eax
0x1400846d6  call    HsmDbgBreakOnStatus
0x1400846db  test    r14d, r14d
0x1400846de  jns     loc_140084764
0x1400846e4  mov     r8, cs:WPP_GLOBAL_Control
0x1400846eb  lea     rax, WPP_GLOBAL_Control
0x1400846f2  mov     edx, 1
0x1400846f7  cmp     r8, rax
0x1400846fa  jz      loc_1400848E6
0x140084700  mov     ecx, [r8+2Ch]
0x140084704  test    dl, cl
0x140084706  jz      loc_1400848E6
0x14008470c  cmp     byte ptr [r8+29h], 2
0x140084711  jb      loc_1400848E6
0x140084717  mov     rax, [rbp+70h+var_F0]
0x14008471b  mov     edx, 20h ; ' '
0x140084720  mov     rcx, [r8+18h]
0x140084724  mov     r9, rdi
0x140084727  mov     dword ptr [rsp+1A0h+var_148], r14d
0x14008472c  mov     [rsp+1A0h+var_150], r13
0x140084731  mov     [rsp+1A0h+var_158], rsi
0x140084736  mov     [rsp+1A0h+var_160], rax
0x14008473b  mov     eax, [r15+1Ch]
0x14008473f  mov     dword ptr [rsp+1A0h+var_168], eax
0x140084743  mov     rax, [rbp+70h+var_C0]
0x140084747  mov     [rsp+1A0h+var_170], r15
0x14008474c  mov     qword ptr [rsp+1A0h+Priority], rax
0x140084751  mov     qword ptr [rsp+1A0h+BugCheckOnFailure], r12
0x140084756  call    WPP_SF_qqqqLiqid
0x14008475b  mov     rbx, [rbp+70h+var_F0]
0x14008475f  jmp     loc_140084950
0x140084764  mov     rcx, [r12+10h]
0x140084769  cmp     byte ptr [rcx+4], 3
0x14008476d  jnz     loc_1400848EC
0x140084773  cmp     byte ptr [rcx+5], 2
0x140084777  jz      loc_1400848EC
0x14008477d  mov     eax, [rdi+28h]
0x140084780  bt      eax, 8
0x140084784  jb      loc_1400848EC
0x14008478a  and     eax, 0Fh
0x14008478d  mov     edx, 1
0x140084792  cmp     al, 3
0x140084794  jnb     loc_1400848E6
0x14008479a  mov     rax, [rcx+28h]
0x14008479e  mov     rcx, [rcx+38h]; MemoryDescriptorList
0x1400847a2  mov     [rbp+70h+var_80], rax
0x1400847a6  mov     [rbp+70h+arg_8], dl
0x1400847ac  test    byte ptr [rcx+0Ah], 5
0x1400847b0  jz      short loc_1400847B8
0x1400847b2  mov     rax, [rcx+18h]
0x1400847b6  jmp     short loc_1400847E1
0x1400847b8  mov     r8d, edx; CacheType
0x1400847bb  mov     [rsp+1A0h+Priority], 40000010h; Priority
0x1400847c3  xor     edx, edx; AccessMode
0x1400847c5  mov     [rsp+1A0h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400847cd  xor     r9d, r9d; RequestedAddress
0x1400847d0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400847d7  nop     dword ptr [rax+rax+00h]
0x1400847dc  mov     edx, 1
0x1400847e1  mov     [rbp+70h+var_B8], rax
0x1400847e5  test    rax, rax
0x1400847e8  jnz     loc_1400848D7
0x1400847ee  mov     r14d, 0C000009Ah
0x1400847f4  mov     ecx, r14d
0x1400847f7  call    HsmDbgBreakOnStatus
0x1400847fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140084803  lea     rax, WPP_GLOBAL_Control
0x14008480a  mov     edx, 1
0x14008480f  cmp     rcx, rax
0x140084812  jz      short loc_14008486A
0x140084814  mov     eax, [rcx+2Ch]
0x140084817  test    dl, al
0x140084819  jz      short loc_14008486A
0x14008481b  cmp     byte ptr [rcx+29h], 2
0x14008481f  jb      short loc_14008486A
0x140084821  mov     rax, [rbp+70h+var_F0]
0x140084825  mov     edx, 21h ; '!'
0x14008482a  mov     rcx, [rcx+18h]
0x14008482e  mov     r9, rdi
0x140084831  mov     dword ptr [rsp+1A0h+var_148], r14d
0x140084836  mov     [rsp+1A0h+var_150], r13
0x14008483b  mov     [rsp+1A0h+var_158], rsi
0x140084840  mov     [rsp+1A0h+var_160], rax
0x140084845  mov     eax, [r15+1Ch]
0x140084849  mov     dword ptr [rsp+1A0h+var_168], eax
0x14008484d  mov     rax, [rbp+70h+var_C0]
0x140084851  mov     [rsp+1A0h+var_170], r15
0x140084856  mov     qword ptr [rsp+1A0h+Priority], rax
0x14008485b  mov     qword ptr [rsp+1A0h+BugCheckOnFailure], r12
0x140084860  call    WPP_SF_qqqqLiqid
0x140084865  mov     edx, 1
0x14008486a  test    r14d, r14d
0x14008486d  jns     loc_140084E83
0x140084873  xor     sil, sil
0x140084876  test    r14d, r14d
0x140084879  js      loc_140084FEA
0x14008487f  mov     eax, [rdi+28h]
0x140084882  and     al, 0Fh
0x140084884  cmp     al, 2
0x140084886  jnz     loc_140084FEA
0x14008488c  test    dword ptr [rdi+30h], 200h
0x140084893  jz      loc_140084FEA
0x140084899  xor     ecx, ecx
0x14008489b  xor     eax, eax
0x14008489d  lock cmpxchg [rdi+34h], ecx
0x1400848a2  cmp     eax, edx
0x1400848a4  jnz     loc_140084FEA
0x1400848aa  mov     edx, [rdi+30h]
0x1400848ad  mov     eax, edx
0x1400848af  mov     rbx, [rbp+70h+var_F0]
0x1400848b3  and     eax, 1C0h
0x1400848b8  cmp     eax, 40h ; '@'
0x1400848bb  jnz     short loc_1400848F3
0x1400848bd  test    dword ptr [rdi+28h], 100h
0x1400848c4  jz      short loc_1400848F3
0x1400848c6  lea     eax, [rdx+40h]
0x1400848c9  xor     eax, edx
0x1400848cb  and     eax, 1C0h
0x1400848d0  xor     eax, edx
0x1400848d2  mov     [rdi+30h], eax
0x1400848d5  jmp     short loc_140084946
0x1400848d7  mov     rax, [r12+10h]
0x1400848dc  mov     rcx, [rax+38h]
0x1400848e0  mov     eax, [rcx+28h]
0x1400848e3  mov     [rbp+70h+var_C8], eax
0x1400848e6  mov     rbx, [rbp+70h+var_F0]
0x1400848ea  jmp     short loc_140084955
0x1400848ec  mov     edx, 1
0x1400848f1  jmp     short loc_1400848E6
0x1400848f3  mov     rcx, [rdi+48h]
0x1400848f7  cmp     rcx, rbx
0x1400848fa  jl      short loc_14008490E
0x1400848fc  bt      edx, 0Ah
0x140084900  jb      short loc_14008490E
0x140084902  bts     edx, 0Ah
0x140084906  mov     [rdi+30h], edx
0x140084909  xor     r8d, r8d
0x14008490c  jmp     short loc_140084915
0x14008490e  mov     r8, [rdi+50h]
0x140084912  add     r8, rcx
0x140084915  lea     rax, [r8+1000h]
0x14008491c  mov     [rdi+48h], r8
0x140084920  cmp     rax, rbx
0x140084923  mov     rcx, rbx
0x140084926  cmovl   rcx, rax
0x14008492a  sub     rcx, r8
0x14008492d  mov     [rdi+50h], rcx
0x140084931  cmp     r8, rbx
0x140084934  jge     short loc_140084946
0x140084936  and     edx, 0FFFFFE7Fh
0x14008493c  or      edx, 40h
0x14008493f  and     dword ptr [rdi+2Ch], 0FFFFFFDFh
0x140084943  mov     [rdi+30h], edx
0x140084946  cmp     [rdi+48h], rbx
0x14008494a  jge     loc_140084FEA
0x140084950  mov     edx, 1
0x140084955  mov     esi, [rdi+30h]
0x140084958  mov     r12d, esi
0x14008495b  shr     r12d, 6
0x14008495f  and     r12d, 7
0x140084963  mov     [rbp+70h+var_E4], r12d
0x140084967  mov     r13, cs:WPP_GLOBAL_Control
0x14008496e  lea     rax, WPP_GLOBAL_Control
0x140084975  cmp     r13, rax
0x140084978  jz      loc_140084A35
0x14008497e  mov     eax, [r13+2Ch]
0x140084982  test    dl, al
0x140084984  jz      loc_140084A35
0x14008498a  cmp     byte ptr [r13+29h], 4
0x14008498f  jb      loc_140084A35
0x140084995  mov     r8, [rdi+48h]
0x140084999  mov     r9d, esi
0x14008499c  mov     r11d, [rdi+28h]
0x1400849a0  and     esi, 1Fh
0x1400849a3  mov     rcx, [rdi+50h]
0x1400849a7  mov     r10d, r11d
0x1400849aa  mov     rax, [rbp+70h+var_D0]
0x1400849ae  add     rcx, r8
0x1400849b1  mov     [rsp+1A0h+var_118], rcx
0x1400849b9  and     r11d, 0Fh
0x1400849bd  mov     rcx, [r13+18h]
0x1400849c1  mov     [rsp+1A0h+var_120], r8
0x1400849c9  mov     [rsp+1A0h+var_128], rax
0x1400849ce  mov     rax, [rbp+70h+var_88]
0x1400849d2  mov     [rsp+1A0h+var_130], rax
0x1400849d7  mov     eax, [r15+1Ch]
0x1400849db  mov     [rsp+1A0h+var_138], rbx
0x1400849e0  mov     [rsp+1A0h+var_140], eax
0x1400849e4  mov     rax, [rbp+70h+var_C0]
0x1400849e8  mov     [rsp+1A0h+var_148], r15
0x1400849ed  mov     [rsp+1A0h+var_150], rax
0x1400849f2  mov     rax, [rdi+18h]
0x1400849f6  mov     dword ptr [rsp+1A0h+var_158], r12d
0x1400849fb  shr     r9d, 9
0x1400849ff  and     r9b, dl
0x140084a02  shr     r10d, 8
0x140084a06  and     r10b, dl
0x140084a09  mov     edx, 22h ; '"'
0x140084a0e  mov     byte ptr [rsp+1A0h+var_160], r10b
0x140084a13  mov     byte ptr [rsp+1A0h+var_168], r9b
0x140084a18  mov     r9, rdi
0x140084a1b  mov     dword ptr [rsp+1A0h+var_170], r11d
0x140084a20  mov     [rsp+1A0h+Priority], esi
0x140084a24  mov     qword ptr [rsp+1A0h+BugCheckOnFailure], rax
0x140084a29  call    WPP_SF_qqllcclqqLiqiii
0x140084a2e  mov     esi, [rdi+30h]
0x140084a31  mov     rbx, [rbp+70h+var_F0]
0x140084a35  mov     ecx, [r15+1Ch]
0x140084a39  mov     r8, [rdi+48h]
0x140084a3d  and     ecx, 2
0x140084a40  mov     r11, [rdi+50h]
0x140084a44  mov     eax, ecx
0x140084a46  neg     eax
0x140084a48  sbb     r13, r13
0x140084a4b  not     r13
0x140084a4e  and     r13, 0FFFFFFFFFFFFF000h
0x140084a55  and     r13, r8
0x140084a58  neg     ecx
0x140084a5a  mov     [rbp+70h+var_E0], r13
0x140084a5e  sbb     rdx, rdx
0x140084a61  dec     r11
  ... truncated ...
```
