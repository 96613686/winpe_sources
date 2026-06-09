# CKsPin::Property_ConnectionState(_IRP *,KSIDENTIFIER *,KSSTATE *)

- ea: `0x180040360`
- end: `0x180040d2f`
- name: `?Property_ConnectionState@CKsPin@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAW4KSSTATE@@@Z`
- size: `2511`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, enum KSSTATE *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x18000a9f0`
- `0x18000b7bc`
- `0x18000c630`
- `0x18000dddc`
- `0x18000f544`
- `0x180014778`
- `0x180014ffc`
- `0x1800153c0`
- `0x1800156e8`
- `0x180015748`
- `0x180019cb0`
- `0x18003d750`
- `0x18003e2a4`
- `0x180040360`
- `0x180052064`
- `0x180061b1c`
- `0x180062abc`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1800406c4`
- `ntoskrnl!KeReleaseMutex` at `0x1800406c4`
- `ntoskrnl!PsGetProcessId` at `0x180040970`
- `ntoskrnl!PsGetProcessId` at `0x180040970`
- `ntoskrnl!PsGetThreadProcess` at `0x18004078f`
- `ntoskrnl!PsGetThreadProcess` at `0x18004078f`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040555`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040555`

## pseudocode

```c
__int64 __fastcall CKsPin::Property_ConnectionState(struct _IRP *a1, struct KSIDENTIFIER *a2, enum KSSTATE *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rbp
  int PipeSection; // ebx
  enum KSSTATE v9; // edx
  _DWORD *v11; // rsi
  __int64 v12; // rcx
  int v13; // eax
  struct _KTHREAD *Thread; // rcx
  __int64 v15; // rax
  int IsEnabledNoReportingNoInline; // eax
  int v17; // edx
  int v18; // r8d
  PDEVICE_OBJECT v19; // rcx
  int v20; // r9d
  __int64 v21; // rax
  int v22; // r14d
  struct _KPROCESS *v23; // rcx
  unsigned int ProcessId; // eax
  __int64 v25; // rdx
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // r8
  __int64 v28; // r14
  struct IKsDevice *v29; // r9
  struct IKsFilter *v30; // r8
  void *v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // r8

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      2,
      103,
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
  v6 = *(_QWORD *)(*(_QWORD *)a1->Tail.Overlay.CurrentStackLocation->FileObject->FsContext + 112LL);
  v7 = v6 - 128;
  if ( (a2->Flags & 1) != 0 )
  {
    PipeSection = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        2,
        104,
        (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
        v6 + 0x80);
    v9 = *(_DWORD *)(v6 + 248);
    *a3 = v9;
    if ( (*(_DWORD *)(*(_QWORD *)(v6 + 128) + 104LL) & 0x10000) != 0
      && *(_DWORD *)(v6 + 244) == 2
      && v9 == KSSTATE_PAUSE )
    {
      PipeSection = -2147483614;
    }
    goto LABEL_118;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_qdd(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      2,
      105,
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
      v6 + 0x80,
      *(_DWORD *)(v6 + 248),
      *a3);
  if ( *a3 <= (unsigned int)KSSTATE_RUN )
  {
    PipeSection = (*(__int64 (__fastcall **)(_QWORD, __int64, struct _IRP *))(**(_QWORD **)(v6 + 72) + 80LL))(
                    *(_QWORD *)(v6 + 72),
                    v6 + 128,
                    a1);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        2,
        107,
        (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
        PipeSection);
    if ( PipeSection )
      return (unsigned int)PipeSection;
    KeWaitForSingleObject(*(PVOID *)(v6 + 88), Executive, 0, 0, 0);
    if ( *a3 )
    {
      v11 = (_DWORD *)(v6 + 248);
      if ( !*(_DWORD *)(v6 + 248)
        && !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 648) + 32LL))(*(_QWORD *)(v7 + 648)) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            2,
            108,
            (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
            v6 + 0x80,
            *a3);
        PipeSection = -1073741667;
        goto LABEL_39;
      }
    }
    v12 = *(_QWORD *)(v7 + 576);
    if ( v12 )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(v12 + 16) + 24LL))(
              *(_QWORD *)(v12 + 16),
              v6 - 128,
              *(unsigned int *)a3);
      PipeSection = v13;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          0,
          2,
          109,
          (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
          v13);
      v11 = (_DWORD *)(v6 + 248);
      goto LABEL_33;
    }
    if ( !CKsPin::UseStandardTransport((CKsPin *)(v6 - 128)) )
    {
      if ( !*(_QWORD *)(v7 + 1144) )
        goto LABEL_34;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          0,
          2,
          119,
          (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
          v6 + 0x80);
      v11 = (_DWORD *)(v6 + 248);
      v33 = *(unsigned int *)(v6 + 248);
      *(enum KSSTATE *)(v6 + 256) = *a3;
      PipeSection = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v7 + 1144))(
                      v6 + 128,
                      *(unsigned int *)a3,
                      v33);
      if ( PipeSection == 259 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            2,
            120,
            (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
        goto LABEL_34;
      }
      if ( PipeSection >= 0 )
      {
LABEL_34:
        v11 = (_DWORD *)(v6 + 248);
        *(enum KSSTATE *)(v6 + 248) = *a3;
        if ( *(_QWORD *)(v7 + 880) )
          CKsPin::SetPinClockState((CKsPin *)(v6 - 128), *a3);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_D(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            2,
            122,
            (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
            *a3);
        goto LABEL_39;
      }
      *(_DWORD *)(v6 + 256) = *v11;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          0,
          2,
          121,
          (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
          PipeSection);
        goto LABEL_39;
      }
      goto LABEL_33;
    }
    v11 = (_DWORD *)(v6 + 248);
    if ( *(_DWORD *)(v6 + 248) || *a3 == KSSTATE_STOP )
    {
LABEL_98:
      if ( *(int *)a3 > 1 )
      {
        v32 = *(_QWORD *)(v7 + 576);
        if ( v32 )
        {
          PipeSection = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v32 + 16) + 24LL))(
                          *(_QWORD *)(v32 + 16),
                          v6 - 128);
          if ( PipeSection >= 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              WPP_RECORDER_SF_D(
                WPP_GLOBAL_Control->DeviceExtension,
                0,
                2,
                118,
                (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
                *a3);
            }
          }
          else
          {
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(*(_QWORD *)(v7 + 576) + 16LL) + 24LL))(
              *(_QWORD *)(*(_QWORD *)(v7 + 576) + 16LL),
              v6 - 128,
              0);
          }
        }
      }
LABEL_33:
      if ( PipeSection >= 0 )
        goto LABEL_34;
LABEL_39:
      KeReleaseMutex(*(PRKMUTEX *)(v6 + 88), 0);
      if ( PipeSection < 0 )
        (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD))(**(_QWORD **)(v6 + 72) + 80LL))(
          *(_QWORD *)(v6 + 72),
          v6 + 128,
          0,
          (unsigned int)*v11,
          *a3);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)PipeSection;
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          0,
          2,
          123,
          (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
          v6 + 0x80,
          PipeSection);
LABEL_118:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            2,
            124,
            (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
      }
      return (unsigned int)PipeSection;
    }
    Thread = a1->Tail.Overlay.Thread;
    if ( Thread )
    {
      v15 = *(_QWORD *)(v6 + 40);
      if ( v15 )
      {
        if ( !*(_QWORD *)(v15 + 168) )
        {
          *(_QWORD *)(*(_QWORD *)(v6 + 40) + 168LL) = PsGetThreadProcess(Thread);
          *(_BYTE *)(*(_QWORD *)(v6 + 40) + 160LL) = IsImmersiveApp(*(_QWORD *)(*(_QWORD *)(v6 + 40) + 168LL));
        }
      }
    }
    if ( !*(_QWORD *)(v6 + 288) )
      *(_QWORD *)(v6 + 288) = a1->Tail.Overlay.CurrentStackLocation->FileObject;
    PipeSection = KspCreatePipeSection(
                    *(void **)(v7 + 592),
                    (struct IKsPin *)(v6 - 128),
                    *(struct IKsFilter **)(v7 + 648),
                    *(struct IKsDevice **)(v6 + 72));
    IsEnabledNoReportingNoInline = Feature_Servicing_ReportAccurateCameraError__private_IsEnabledNoReportingNoInline();
    if ( PipeSection != -1073741670 )
    {
      if ( IsEnabledNoReportingNoInline )
      {
        if ( PipeSection == -1073741823 || (PipeSection & 0xFFF0000) == 0x1F0000 )
          goto LABEL_57;
      }
      else if ( PipeSection == -1073741823 )
      {
        goto LABEL_57;
      }
      CKsPin::QueryParentThermalStateSyncState((CKsPin *)(v6 - 128));
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v19 = WPP_GLOBAL_Control;
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v20 = 117;
          goto LABEL_96;
        }
      }
LABEL_97:
      if ( PipeSection < 0 )
        goto LABEL_39;
      goto LABEL_98;
    }
LABEL_57:
    if ( (a2->Flags & 0x8000000) != 0
      || *(_BYTE *)(*(_QWORD *)(v6 + 40) + 160LL) && (unsigned __int8)IsCameraStreamingToSameProcess(v6 - 128) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          0,
          2,
          110,
          (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
      v21 = *(_QWORD *)(v6 + 40);
      if ( v21 && *(_BYTE *)(v21 + 160) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            2,
            111,
            (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
        if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
        {
          v22 = *(_DWORD *)(v6 + 152);
          v23 = *(struct _KPROCESS **)(*(_QWORD *)(v6 + 40) + 168LL);
          if ( v23 )
            ProcessId = (unsigned int)PsGetProcessId(v23);
          else
            ProcessId = 0;
          McTemplateK0pqp_EtwWriteTransfer((_DWORD)v23, v17, v18, ProcessId, v22, 0);
        }
        if ( (int)StopActiveVideoStreams(v6 - 128) < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v26 = WPP_GLOBAL_Control;
            if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                0,
                2,
                114,
                (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
          }
        }
        else
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              0,
              2,
              112,
              (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
          }
          v28 = *(_QWORD *)(v6 + 216);
          v29 = *(struct IKsDevice **)(v6 + 72);
          v30 = *(struct IKsFilter **)(v7 + 648);
          v31 = *(void **)(v7 + 592);
          *(_DWORD *)(v6 + 216) = 0x80000000;
          *(_DWORD *)(v6 + 220) = 0x80000000;
          PipeSection = KspCreatePipeSection(v31, (struct IKsPin *)(v6 - 128), v30, v29);
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v26 = WPP_GLOBAL_Control;
            if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
              WPP_RECORDER_SF_D(
                WPP_GLOBAL_Control->DeviceExtension,
                0,
                2,
                113,
                (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids,
                PipeSection);
          }
          *(_QWORD *)(v6 + 216) = v28;
        }
        if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
          McTemplateK0d_EtwWriteTransfer(v26, v25, v27, (unsigned int)PipeSection);
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v19 = WPP_GLOBAL_Control;
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v20 = 115;
          goto LABEL_96;
        }
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v19 = WPP_GLOBAL_Control;
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        v20 = 116;
LABEL_96:
        WPP_RECORDER_SF_(v19->DeviceExtension, 0, 2, v20, (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
        goto LABEL_97;
      }
    }
    goto LABEL_97;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      2,
      106,
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
  return 3221225485LL;
}

```

## disassembly

```asm
0x180040360  push    rbx
0x180040362  push    rbp
0x180040363  push    rsi
0x180040364  push    rdi
0x180040365  push    r12
0x180040367  push    r13
0x180040369  push    r14
0x18004036b  push    r15
0x18004036d  sub     rsp, 48h
0x180040371  mov     r15, r8
0x180040374  mov     r13, rdx
0x180040377  mov     r14, rcx
0x18004037a  xor     esi, esi
0x18004037c  lea     rdx, WPP_RECORDER_INITIALIZED
0x180040383  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x18004038a  lea     r8, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x180040391  lea     r12d, [rsi+2]
0x180040395  jz      short loc_1800403C9
0x180040397  mov     rcx, cs:WPP_GLOBAL_Control
0x18004039e  cmp     [rcx+48h], si
0x1800403a2  jz      short loc_1800403C9
0x1800403a4  mov     rcx, [rcx+40h]
0x1800403a8  lea     r9d, [rsi+67h]
0x1800403ac  mov     [rsp+88h+Timeout], r8
0x1800403b1  xor     edx, edx
0x1800403b3  mov     r8d, r12d
0x1800403b6  call    WPP_RECORDER_SF_
0x1800403bb  lea     rdx, WPP_RECORDER_INITIALIZED
0x1800403c2  lea     r8, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x1800403c9  mov     rax, [r14+0B8h]
0x1800403d0  mov     rcx, [rax+30h]
0x1800403d4  mov     rax, [rcx+18h]
0x1800403d8  mov     rcx, [rax]
0x1800403db  mov     eax, [r13+14h]
0x1800403df  mov     rdi, [rcx+70h]
0x1800403e3  lea     rbp, [rdi-80h]
0x1800403e7  test    al, 1
0x1800403e9  jz      loc_180040473
0x1800403ef  xor     r14d, r14d
0x1800403f2  mov     ebx, r14d
0x1800403f5  lea     r13, WPP_RECORDER_INITIALIZED
0x1800403fc  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180040403  jz      short loc_18004042F
0x180040405  mov     rcx, cs:WPP_GLOBAL_Control
0x18004040c  cmp     [rcx+48h], r14w
0x180040411  jz      short loc_18004042F
0x180040413  mov     rcx, [rcx+40h]
0x180040417  lea     r9d, [r14+68h]
0x18004041b  mov     [rsp+88h+var_60], rbp
0x180040420  xor     edx, edx
0x180040422  mov     [rsp+88h+Timeout], r8
0x180040427  mov     r8d, r12d
0x18004042a  call    WPP_RECORDER_SF_q
0x18004042f  mov     edx, [rdi+0F8h]
0x180040435  mov     [r15], edx
0x180040438  mov     rax, [rdi+80h]
0x18004043f  test    dword ptr [rax+68h], 10000h
0x180040446  jz      loc_180040C9E
0x18004044c  cmp     [rdi+0F4h], r12d
0x180040453  jnz     loc_180040C9E
0x180040459  lea     rdi, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x180040460  cmp     edx, r12d
0x180040463  jnz     loc_180040CA5
0x180040469  mov     ebx, 80000022h
0x18004046e  jmp     loc_180040CA5
0x180040473  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x18004047a  jz      short loc_1800404BF
0x18004047c  mov     rcx, cs:WPP_GLOBAL_Control
0x180040483  cmp     [rcx+48h], si
0x180040487  jz      short loc_1800404BF
0x180040489  mov     eax, [r15]
0x18004048c  mov     r9d, 69h ; 'i'
0x180040492  mov     rcx, [rcx+40h]
0x180040496  xor     edx, edx
0x180040498  mov     [rsp+88h+var_50], eax
0x18004049c  mov     eax, [rdi+0F8h]
0x1800404a2  mov     [rsp+88h+var_58], eax
0x1800404a6  mov     [rsp+88h+var_60], rbp
0x1800404ab  mov     [rsp+88h+Timeout], r8
0x1800404b0  mov     r8d, r12d
0x1800404b3  call    WPP_RECORDER_SF_qdd
0x1800404b8  lea     rdx, WPP_RECORDER_INITIALIZED
0x1800404bf  mov     r9d, [r15]
0x1800404c2  cmp     r9d, 3
0x1800404c6  ja      loc_180040CE2
0x1800404cc  mov     rcx, [rdi+48h]
0x1800404d0  lea     r12, [rdi+80h]
0x1800404d7  mov     r8, r14
0x1800404da  mov     rdx, r12
0x1800404dd  mov     rax, [rcx]
0x1800404e0  mov     r10, [rax+50h]
0x1800404e4  mov     eax, [r12+78h]
0x1800404e9  mov     dword ptr [rsp+88h+Timeout], eax
0x1800404ed  mov     rax, r10
0x1800404f0  call    _guard_dispatch_icall
0x1800404f5  mov     ebx, eax
0x1800404f7  lea     rax, WPP_RECORDER_INITIALIZED
0x1800404fe  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180040505  jz      short loc_180040539
0x180040507  mov     rcx, cs:WPP_GLOBAL_Control
0x18004050e  cmp     [rcx+48h], si
0x180040512  jz      short loc_180040539
0x180040514  mov     rcx, [rcx+40h]
0x180040518  lea     rax, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x18004051f  mov     r9d, 6Bh ; 'k'
0x180040525  mov     dword ptr [rsp+88h+var_60], ebx
0x180040529  xor     edx, edx
0x18004052b  mov     [rsp+88h+Timeout], rax
0x180040530  lea     r8d, [r9-69h]
0x180040534  call    WPP_RECORDER_SF_D
0x180040539  test    ebx, ebx
0x18004053b  jz      short loc_180040544
0x18004053d  mov     eax, ebx
0x18004053f  jmp     loc_180040D1D
0x180040544  mov     rcx, [rdi+58h]; Object
0x180040548  xor     r9d, r9d; Alertable
0x18004054b  xor     r8d, r8d; WaitMode
0x18004054e  mov     [rsp+88h+Timeout], rsi; Timeout
0x180040553  xor     edx, edx; WaitReason
0x180040555  call    cs:__imp_KeWaitForSingleObject
0x18004055c  nop     dword ptr [rax+rax+00h]
0x180040561  cmp     [r15], esi
0x180040564  jz      short loc_1800405DF
0x180040566  lea     rsi, [rdi+0F8h]
0x18004056d  cmp     dword ptr [rsi], 0
0x180040570  jnz     short loc_1800405DF
0x180040572  mov     rcx, [rbp+288h]
0x180040579  mov     rax, [rcx]
0x18004057c  mov     rax, [rax+20h]
0x180040580  call    _guard_dispatch_icall
0x180040585  test    al, al
0x180040587  jnz     short loc_1800405DF
0x180040589  lea     r13, WPP_RECORDER_INITIALIZED
0x180040590  xor     r14d, r14d
0x180040593  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18004059a  jz      short loc_1800405D5
0x18004059c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800405a3  cmp     [rcx+48h], r14w
0x1800405a8  jz      short loc_1800405D5
0x1800405aa  mov     eax, [r15]
0x1800405ad  lea     r9d, [r14+6Ch]
0x1800405b1  mov     rcx, [rcx+40h]
0x1800405b5  lea     r8d, [r14+2]
0x1800405b9  mov     [rsp+88h+var_58], eax
0x1800405bd  xor     edx, edx
0x1800405bf  lea     rax, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x1800405c6  mov     [rsp+88h+var_60], rbp
0x1800405cb  mov     [rsp+88h+Timeout], rax
0x1800405d0  call    WPP_RECORDER_SF_qD
0x1800405d5  mov     ebx, 0C000009Dh
0x1800405da  jmp     loc_1800406BE
0x1800405df  mov     rcx, [rbp+240h]
0x1800405e6  test    rcx, rcx
0x1800405e9  jz      loc_180040747
0x1800405ef  mov     rcx, [rcx+10h]
0x1800405f3  mov     rdx, rbp
0x1800405f6  mov     r8d, [r15]
0x1800405f9  mov     rax, [rcx]
0x1800405fc  mov     rax, [rax+18h]
0x180040600  call    _guard_dispatch_icall
0x180040605  mov     ebx, eax
0x180040607  lea     r13, WPP_RECORDER_INITIALIZED
0x18004060e  xor     r14d, r14d
0x180040611  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180040618  jz      short loc_18004064B
0x18004061a  mov     rcx, cs:WPP_GLOBAL_Control
0x180040621  cmp     [rcx+48h], r14w
0x180040626  jz      short loc_18004064B
0x180040628  mov     rcx, [rcx+40h]
0x18004062c  lea     r9d, [r14+6Dh]
0x180040630  mov     dword ptr [rsp+88h+var_60], eax
0x180040634  lea     r8d, [r14+2]
0x180040638  lea     rax, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x18004063f  xor     edx, edx
0x180040641  mov     [rsp+88h+Timeout], rax
0x180040646  call    WPP_RECORDER_SF_D
0x18004064b  lea     rsi, [rdi+0F8h]
0x180040652  test    ebx, ebx
0x180040654  js      short loc_1800406BE
0x180040656  lea     rsi, [rdi+0F8h]
0x18004065d  mov     eax, [r15]
0x180040660  mov     [rsi], eax
0x180040662  cmp     [rbp+370h], r14
0x180040669  jz      short loc_180040676
0x18004066b  mov     edx, [r15]; enum KSSTATE
0x18004066e  mov     rcx, rbp; this
0x180040671  call    ?SetPinClockState@CKsPin@@QEAAXW4KSSTATE@@@Z; CKsPin::SetPinClockState(KSSTATE)
0x180040676  lea     r13, WPP_RECORDER_INITIALIZED
0x18004067d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180040684  jz      short loc_1800406BE
0x180040686  mov     rcx, cs:WPP_GLOBAL_Control
0x18004068d  cmp     [rcx+48h], r14w
0x180040692  jz      short loc_1800406BE
0x180040694  mov     eax, [r15]
0x180040697  mov     r9d, 7Ah ; 'z'
0x18004069d  mov     dword ptr [rsp+88h+var_60], eax
0x1800406a1  mov     rcx, [rcx+40h]
0x1800406a5  lea     rax, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x1800406ac  mov     r8d, 2
0x1800406b2  mov     [rsp+88h+Timeout], rax
0x1800406b7  xor     edx, edx
0x1800406b9  call    WPP_RECORDER_SF_D
0x1800406be  mov     rcx, [rdi+58h]; Mutex
0x1800406c2  xor     edx, edx; Wait
0x1800406c4  call    cs:__imp_KeReleaseMutex
0x1800406cb  nop     dword ptr [rax+rax+00h]
0x1800406d0  test    ebx, ebx
0x1800406d2  jns     short loc_1800406F5
0x1800406d4  mov     r8d, [r15]
0x1800406d7  mov     rdx, r12
0x1800406da  mov     rcx, [rdi+48h]
0x1800406de  mov     r9d, [rsi]
0x1800406e1  mov     dword ptr [rsp+88h+Timeout], r8d
0x1800406e6  xor     r8d, r8d
0x1800406e9  mov     rax, [rcx]
0x1800406ec  mov     rax, [rax+50h]
0x1800406f0  call    _guard_dispatch_icall
0x1800406f5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800406fc  jz      loc_18004053D
0x180040702  mov     rcx, cs:WPP_GLOBAL_Control
0x180040709  lea     rdi, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x180040710  mov     r12d, 2
0x180040716  cmp     [rcx+48h], r14w
0x18004071b  jz      loc_180040CA5
0x180040721  mov     rcx, [rcx+40h]
0x180040725  lea     r9d, [r12+79h]
0x18004072a  mov     [rsp+88h+var_58], ebx
0x18004072e  mov     r8d, r12d
0x180040731  mov     [rsp+88h+var_60], rbp
0x180040736  xor     edx, edx
0x180040738  mov     [rsp+88h+Timeout], rdi
0x18004073d  call    WPP_RECORDER_SF_qD
0x180040742  jmp     loc_180040CA5
0x180040747  mov     rcx, rbp; this
0x18004074a  call    ?UseStandardTransport@CKsPin@@AEAAEXZ; CKsPin::UseStandardTransport(void)
0x18004074f  test    al, al
0x180040751  jz      loc_180040B9B
0x180040757  lea     rsi, [rdi+0F8h]
0x18004075e  xor     edx, edx
0x180040760  cmp     [rsi], edx
0x180040762  jnz     loc_180040AEE
0x180040768  cmp     [r15], edx
0x18004076b  jz      loc_180040AEE
0x180040771  mov     rcx, [r14+98h]; Thread
0x180040778  test    rcx, rcx
0x18004077b  jz      short loc_1800407C2
0x18004077d  mov     rax, [rdi+28h]
0x180040781  test    rax, rax
0x180040784  jz      short loc_1800407C2
0x180040786  cmp     [rax+0A8h], rdx
0x18004078d  jnz     short loc_1800407C2
0x18004078f  call    cs:__imp_PsGetThreadProcess
0x180040796  nop     dword ptr [rax+rax+00h]
0x18004079b  mov     rcx, [rdi+28h]
0x18004079f  mov     [rcx+0A8h], rax
0x1800407a6  mov     rcx, [rdi+28h]
0x1800407aa  mov     rcx, [rcx+0A8h]
0x1800407b1  call    IsImmersiveApp
0x1800407b6  mov     rcx, [rdi+28h]
0x1800407ba  xor     edx, edx
0x1800407bc  mov     [rcx+0A0h], al
0x1800407c2  cmp     [rdi+120h], rdx
0x1800407c9  jnz     short loc_1800407DD
0x1800407cb  mov     rax, [r14+0B8h]
0x1800407d2  mov     rcx, [rax+30h]
0x1800407d6  mov     [rdi+120h], rcx
0x1800407dd  mov     r9, [rdi+48h]; struct IKsDevice *
0x1800407e1  mov     rdx, rbp; struct IKsPin *
0x1800407e4  mov     r8, [rbp+288h]; struct IKsFilter *
0x1800407eb  mov     rcx, [rbp+250h]; void *
0x1800407f2  call    KspCreatePipeSection
0x1800407f7  mov     ebx, eax
0x1800407f9  call    Feature_Servicing_ReportAccurateCameraError__private_IsEnabledNoReportingNoInline
0x1800407fe  xor     r14d, r14d
0x180040801  cmp     ebx, 0C000009Ah
0x180040807  jz      short loc_180040823
0x180040809  test    eax, eax
0x18004080b  jz      short loc_18004087B
0x18004080d  cmp     ebx, 0C0000001h
0x180040813  jz      short loc_180040823
0x180040815  mov     eax, ebx
0x180040817  and     eax, 0FFF0000h
0x18004081c  cmp     eax, 1F0000h
0x180040821  jnz     short loc_180040883
0x180040823  test    dword ptr [r13+14h], 8000000h
0x18004082b  jnz     loc_1800408BC
0x180040831  mov     rax, [rdi+28h]
0x180040835  cmp     [rax+0A0h], r14b
0x18004083c  jz      short loc_18004084A
0x18004083e  mov     rcx, rbp
0x180040841  call    IsCameraStreamingToSameProcess
0x180040846  test    al, al
0x180040848  jnz     short loc_1800408BC
0x18004084a  lea     r13, WPP_RECORDER_INITIALIZED
0x180040851  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180040858  jz      loc_180040AE5
0x18004085e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040865  cmp     [rcx+48h], r14w
0x18004086a  jz      loc_180040AE5
0x180040870  mov     r9d, 74h ; 't'
  ... truncated ...
```
