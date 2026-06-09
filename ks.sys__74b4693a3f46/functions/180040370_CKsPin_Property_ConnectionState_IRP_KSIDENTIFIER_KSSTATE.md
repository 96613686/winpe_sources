# CKsPin::Property_ConnectionState(_IRP *,KSIDENTIFIER *,KSSTATE *)

- ea: `0x180040370`
- end: `0x180040d30`
- name: `?Property_ConnectionState@CKsPin@@SAJPEAU_IRP@@PEAUKSIDENTIFIER@@PEAW4KSSTATE@@@Z`
- size: `2496`
- prototype: `__int64 __fastcall(struct _IRP *, struct KSIDENTIFIER *, enum KSSTATE *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000a9f0`
- `0x18000b7bc`
- `0x18000c630`
- `0x18000dddc`
- `0x18000ee54`
- `0x180014778`
- `0x180014ffc`
- `0x180015698`
- `0x1800156f8`
- `0x180019c60`
- `0x18003d760`
- `0x18003e2b4`
- `0x180040370`
- `0x180051ec4`
- `0x18006197c`
- `0x18006291c`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1800406d4`
- `ntoskrnl!KeReleaseMutex` at `0x1800406d4`
- `ntoskrnl!PsGetProcessId` at `0x180040968`
- `ntoskrnl!PsGetProcessId` at `0x180040968`
- `ntoskrnl!PsGetThreadProcess` at `0x18004079f`
- `ntoskrnl!PsGetThreadProcess` at `0x18004079f`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040565`
- `ntoskrnl!KeWaitForSingleObject` at `0x180040565`

## pseudocode

```c
__int64 __fastcall CKsPin::Property_ConnectionState(struct _IRP *a1, struct KSIDENTIFIER *a2, enum KSSTATE *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rbp
  int v8; // ebx
  enum KSSTATE v9; // edx
  _DWORD *v11; // rsi
  __int64 v12; // rcx
  int v13; // eax
  PDEVICE_OBJECT v14; // rcx
  int v15; // r9d
  struct _KTHREAD *Thread; // rcx
  __int64 v17; // rax
  int PipeSection; // eax
  int v19; // edx
  int v20; // r8d
  PDEVICE_OBJECT v21; // rcx
  int v22; // r9d
  __int64 v23; // rax
  int v24; // r15d
  struct _KPROCESS *v25; // rcx
  unsigned int ProcessId; // eax
  __int64 v27; // rdx
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r15
  struct IKsDevice *v31; // r9
  struct IKsFilter *v32; // r8
  void *v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // [rsp+28h] [rbp-60h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      2,
      103,
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
  v6 = *(_QWORD *)(*(_QWORD *)a1->Tail.Overlay.CurrentStackLocation->FileObject->FsContext + 112LL);
  v7 = v6 - 128;
  if ( (a2->Flags & 1) != 0 )
  {
    v8 = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        2,
        104,
        (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
        v6 + 0x80);
    v9 = *(_DWORD *)(v6 + 248);
    *a3 = v9;
    if ( (*(_DWORD *)(*(_QWORD *)(v6 + 128) + 104LL) & 0x10000) != 0
      && *(_DWORD *)(v6 + 244) == 2
      && v9 == KSSTATE_PAUSE )
    {
      v8 = -2147483614;
    }
    goto LABEL_117;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_qdd(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      2,
      105,
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
      v6 + 0x80,
      *(_DWORD *)(v6 + 248),
      *a3);
  if ( *a3 <= (unsigned int)KSSTATE_RUN )
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct _IRP *))(**(_QWORD **)(v6 + 72) + 80LL))(
           *(_QWORD *)(v6 + 72),
           v6 + 128,
           a1);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LODWORD(v36) = v8;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        2,
        107,
        (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
        v36);
    }
    if ( v8 )
      return (unsigned int)v8;
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
            (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
            v6 + 0x80,
            *a3);
        v8 = -1073741667;
        goto LABEL_40;
      }
    }
    v12 = *(_QWORD *)(v7 + 576);
    if ( v12 )
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(v12 + 16) + 24LL))(
              *(_QWORD *)(v12 + 16),
              v6 - 128,
              *(unsigned int *)a3);
      v8 = v13;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        LODWORD(v36) = v13;
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          0,
          2,
          109,
          (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
          v36);
      }
      v11 = (_DWORD *)(v6 + 248);
      goto LABEL_33;
    }
    if ( !CKsPin::UseStandardTransport((CKsPin *)(v6 - 128)) )
    {
      if ( *(_QWORD *)(v7 + 1144) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_q(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            2,
            119,
            (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
            v6 + 0x80);
        v11 = (_DWORD *)(v6 + 248);
        v35 = *(unsigned int *)(v6 + 248);
        *(enum KSSTATE *)(v6 + 256) = *a3;
        v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(v7 + 1144))(v6 + 128, *(unsigned int *)a3, v35);
        if ( v8 == 259 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              0,
              2,
              120,
              (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
          }
        }
        else if ( v8 < 0 )
        {
          *(_DWORD *)(v6 + 256) = *v11;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v14 = WPP_GLOBAL_Control;
            if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              v15 = 121;
              LODWORD(v36) = v8;
LABEL_39:
              WPP_RECORDER_SF_D(
                v14->DeviceExtension,
                0,
                2,
                v15,
                (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
                v36);
              goto LABEL_40;
            }
          }
          goto LABEL_33;
        }
      }
LABEL_34:
      v11 = (_DWORD *)(v6 + 248);
      *(enum KSSTATE *)(v6 + 248) = *a3;
      if ( *(_QWORD *)(v7 + 880) )
        CKsPin::SetPinClockState((CKsPin *)(v6 - 128), *a3);
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_40;
      v14 = WPP_GLOBAL_Control;
      if ( !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_40;
      v15 = 122;
      SLODWORD(v36) = *a3;
      goto LABEL_39;
    }
    v11 = (_DWORD *)(v6 + 248);
    if ( *(_DWORD *)(v6 + 248) || *a3 == KSSTATE_STOP )
    {
LABEL_97:
      if ( *(int *)a3 > 1 )
      {
        v34 = *(_QWORD *)(v7 + 576);
        if ( v34 )
        {
          v8 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v34 + 16) + 24LL))(
                 *(_QWORD *)(v34 + 16),
                 v6 - 128);
          if ( v8 >= 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              SLODWORD(v36) = *a3;
              WPP_RECORDER_SF_D(
                WPP_GLOBAL_Control->DeviceExtension,
                0,
                2,
                118,
                (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
                v36);
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
      if ( v8 < 0 )
      {
LABEL_40:
        KeReleaseMutex(*(PRKMUTEX *)(v6 + 88), 0);
        if ( v8 < 0 )
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD))(**(_QWORD **)(v6 + 72) + 80LL))(
            *(_QWORD *)(v6 + 72),
            v6 + 128,
            0,
            (unsigned int)*v11,
            *a3);
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return (unsigned int)v8;
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            2,
            123,
            (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
            v6 + 0x80,
            v8);
LABEL_117:
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              0,
              2,
              124,
              (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
        }
        return (unsigned int)v8;
      }
      goto LABEL_34;
    }
    Thread = a1->Tail.Overlay.Thread;
    if ( Thread )
    {
      v17 = *(_QWORD *)(v6 + 40);
      if ( v17 )
      {
        if ( !*(_QWORD *)(v17 + 168) )
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
    v8 = PipeSection;
    if ( PipeSection == -1073741670 || PipeSection == -1073741823 || (PipeSection & 0xFFF0000) == 0x1F0000 )
    {
      if ( (a2->Flags & 0x8000000) != 0
        || *(_BYTE *)(*(_QWORD *)(v6 + 40) + 160LL) && (unsigned __int8)IsCameraStreamingToSameProcess(v6 - 128) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            0,
            2,
            110,
            (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
        v23 = *(_QWORD *)(v6 + 40);
        if ( v23 && *(_BYTE *)(v23 + 160) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              0,
              2,
              111,
              (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
          }
          if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
          {
            v24 = *(_DWORD *)(v6 + 152);
            v25 = *(struct _KPROCESS **)(*(_QWORD *)(v6 + 40) + 168LL);
            if ( v25 )
              ProcessId = (unsigned int)PsGetProcessId(v25);
            else
              ProcessId = 0;
            McTemplateK0pqp_EtwWriteTransfer((_DWORD)v25, v19, v20, ProcessId, v24, 0);
          }
          if ( (int)StopActiveVideoStreams(v6 - 128) < 0 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v28 = WPP_GLOBAL_Control;
              if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
                WPP_RECORDER_SF_(
                  WPP_GLOBAL_Control->DeviceExtension,
                  0,
                  2,
                  114,
                  (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
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
                (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
            }
            v30 = *(_QWORD *)(v6 + 216);
            v31 = *(struct IKsDevice **)(v6 + 72);
            v32 = *(struct IKsFilter **)(v7 + 648);
            v33 = *(void **)(v7 + 592);
            *(_DWORD *)(v6 + 216) = 0x80000000;
            *(_DWORD *)(v6 + 220) = 0x80000000;
            v8 = KspCreatePipeSection(v33, (struct IKsPin *)(v6 - 128), v32, v31);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              v28 = WPP_GLOBAL_Control;
              if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
              {
                LODWORD(v36) = v8;
                WPP_RECORDER_SF_D(
                  WPP_GLOBAL_Control->DeviceExtension,
                  0,
                  2,
                  113,
                  (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids,
                  v36);
              }
            }
            *(_QWORD *)(v6 + 216) = v30;
          }
          if ( ((__int64)WPP_MAIN_CB.Dpc.SystemArgument1 & 1) != 0 )
            McTemplateK0d_EtwWriteTransfer(v28, v27, v29, (unsigned int)v8);
        }
        else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v21 = WPP_GLOBAL_Control;
          if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            v22 = 115;
            goto LABEL_95;
          }
        }
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v21 = WPP_GLOBAL_Control;
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v22 = 116;
          goto LABEL_95;
        }
      }
    }
    else
    {
      CKsPin::QueryParentThermalStateSyncState((CKsPin *)(v6 - 128));
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v21 = WPP_GLOBAL_Control;
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v22 = 117;
LABEL_95:
          WPP_RECORDER_SF_(v21->DeviceExtension, 0, 2, v22, (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
        }
      }
    }
    if ( v8 < 0 )
      goto LABEL_40;
    goto LABEL_97;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      2,
      106,
      (__int64)WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids);
  return 3221225485LL;
}

```

## disassembly

```asm
0x180040370  push    rbx
0x180040372  push    rbp
0x180040373  push    rsi
0x180040374  push    rdi
0x180040375  push    r12
0x180040377  push    r13
0x180040379  push    r14
0x18004037b  push    r15
0x18004037d  sub     rsp, 48h
0x180040381  mov     r14, r8
0x180040384  mov     r13, rdx
0x180040387  mov     r15, rcx
0x18004038a  xor     esi, esi
0x18004038c  lea     rdx, WPP_RECORDER_INITIALIZED
0x180040393  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x18004039a  lea     r8, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x1800403a1  lea     r12d, [rsi+2]
0x1800403a5  jz      short loc_1800403D9
0x1800403a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800403ae  cmp     [rcx+48h], si
0x1800403b2  jz      short loc_1800403D9
0x1800403b4  mov     rcx, [rcx+40h]
0x1800403b8  lea     r9d, [rsi+67h]
0x1800403bc  mov     [rsp+88h+Timeout], r8
0x1800403c1  xor     edx, edx
0x1800403c3  mov     r8d, r12d
0x1800403c6  call    WPP_RECORDER_SF_
0x1800403cb  lea     rdx, WPP_RECORDER_INITIALIZED
0x1800403d2  lea     r8, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x1800403d9  mov     rax, [r15+0B8h]
0x1800403e0  mov     rcx, [rax+30h]
0x1800403e4  mov     rax, [rcx+18h]
0x1800403e8  mov     rcx, [rax]
0x1800403eb  mov     eax, [r13+14h]
0x1800403ef  mov     rdi, [rcx+70h]
0x1800403f3  lea     rbp, [rdi-80h]
0x1800403f7  test    al, 1
0x1800403f9  jz      loc_180040483
0x1800403ff  xor     r13d, r13d
0x180040402  mov     ebx, r13d
0x180040405  lea     r15, WPP_RECORDER_INITIALIZED
0x18004040c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180040413  jz      short loc_18004043F
0x180040415  mov     rcx, cs:WPP_GLOBAL_Control
0x18004041c  cmp     [rcx+48h], r13w
0x180040421  jz      short loc_18004043F
0x180040423  mov     rcx, [rcx+40h]
0x180040427  lea     r9d, [r13+68h]
0x18004042b  mov     [rsp+88h+var_60], rbp
0x180040430  xor     edx, edx
0x180040432  mov     [rsp+88h+Timeout], r8
0x180040437  mov     r8d, r12d
0x18004043a  call    WPP_RECORDER_SF_q
0x18004043f  mov     edx, [rdi+0F8h]
0x180040445  mov     [r14], edx
0x180040448  mov     rax, [rdi+80h]
0x18004044f  test    dword ptr [rax+68h], 10000h
0x180040456  jz      loc_180040C9F
0x18004045c  cmp     [rdi+0F4h], r12d
0x180040463  jnz     loc_180040C9F
0x180040469  lea     rdi, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x180040470  cmp     edx, r12d
0x180040473  jnz     loc_180040CA6
0x180040479  mov     ebx, 80000022h
0x18004047e  jmp     loc_180040CA6
0x180040483  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x18004048a  jz      short loc_1800404CF
0x18004048c  mov     rcx, cs:WPP_GLOBAL_Control
0x180040493  cmp     [rcx+48h], si
0x180040497  jz      short loc_1800404CF
0x180040499  mov     eax, [r14]
0x18004049c  mov     r9d, 69h ; 'i'
0x1800404a2  mov     rcx, [rcx+40h]
0x1800404a6  xor     edx, edx
0x1800404a8  mov     [rsp+88h+var_50], eax
0x1800404ac  mov     eax, [rdi+0F8h]
0x1800404b2  mov     [rsp+88h+var_58], eax
0x1800404b6  mov     [rsp+88h+var_60], rbp
0x1800404bb  mov     [rsp+88h+Timeout], r8
0x1800404c0  mov     r8d, r12d
0x1800404c3  call    WPP_RECORDER_SF_qdd
0x1800404c8  lea     rdx, WPP_RECORDER_INITIALIZED
0x1800404cf  mov     r9d, [r14]
0x1800404d2  cmp     r9d, 3
0x1800404d6  ja      loc_180040CE3
0x1800404dc  mov     rcx, [rdi+48h]
0x1800404e0  lea     r12, [rdi+80h]
0x1800404e7  mov     r8, r15
0x1800404ea  mov     rdx, r12
0x1800404ed  mov     rax, [rcx]
0x1800404f0  mov     r10, [rax+50h]
0x1800404f4  mov     eax, [r12+78h]
0x1800404f9  mov     dword ptr [rsp+88h+Timeout], eax
0x1800404fd  mov     rax, r10
0x180040500  call    _guard_dispatch_icall
0x180040505  mov     ebx, eax
0x180040507  lea     rax, WPP_RECORDER_INITIALIZED
0x18004050e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180040515  jz      short loc_180040549
0x180040517  mov     rcx, cs:WPP_GLOBAL_Control
0x18004051e  cmp     [rcx+48h], si
0x180040522  jz      short loc_180040549
0x180040524  mov     rcx, [rcx+40h]
0x180040528  lea     rax, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x18004052f  mov     r9d, 6Bh ; 'k'
0x180040535  mov     dword ptr [rsp+88h+var_60], ebx
0x180040539  xor     edx, edx
0x18004053b  mov     [rsp+88h+Timeout], rax
0x180040540  lea     r8d, [r9-69h]
0x180040544  call    WPP_RECORDER_SF_D
0x180040549  test    ebx, ebx
0x18004054b  jz      short loc_180040554
0x18004054d  mov     eax, ebx
0x18004054f  jmp     loc_180040D1E
0x180040554  mov     rcx, [rdi+58h]; Object
0x180040558  xor     r9d, r9d; Alertable
0x18004055b  xor     r8d, r8d; WaitMode
0x18004055e  mov     [rsp+88h+Timeout], rsi; Timeout
0x180040563  xor     edx, edx; WaitReason
0x180040565  call    cs:__imp_KeWaitForSingleObject
0x18004056c  nop     dword ptr [rax+rax+00h]
0x180040571  cmp     [r14], esi
0x180040574  jz      short loc_1800405EF
0x180040576  lea     rsi, [rdi+0F8h]
0x18004057d  cmp     dword ptr [rsi], 0
0x180040580  jnz     short loc_1800405EF
0x180040582  mov     rcx, [rbp+288h]
0x180040589  mov     rax, [rcx]
0x18004058c  mov     rax, [rax+20h]
0x180040590  call    _guard_dispatch_icall
0x180040595  test    al, al
0x180040597  jnz     short loc_1800405EF
0x180040599  lea     r15, WPP_RECORDER_INITIALIZED
0x1800405a0  xor     r13d, r13d
0x1800405a3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800405aa  jz      short loc_1800405E5
0x1800405ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800405b3  cmp     [rcx+48h], r13w
0x1800405b8  jz      short loc_1800405E5
0x1800405ba  mov     eax, [r14]
0x1800405bd  lea     r9d, [r13+6Ch]
0x1800405c1  mov     rcx, [rcx+40h]
0x1800405c5  lea     r8d, [r13+2]
0x1800405c9  mov     [rsp+88h+var_58], eax
0x1800405cd  xor     edx, edx
0x1800405cf  lea     rax, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x1800405d6  mov     [rsp+88h+var_60], rbp
0x1800405db  mov     [rsp+88h+Timeout], rax
0x1800405e0  call    WPP_RECORDER_SF_qD
0x1800405e5  mov     ebx, 0C000009Dh
0x1800405ea  jmp     loc_1800406CE
0x1800405ef  mov     rcx, [rbp+240h]
0x1800405f6  test    rcx, rcx
0x1800405f9  jz      loc_180040757
0x1800405ff  mov     rcx, [rcx+10h]
0x180040603  mov     rdx, rbp
0x180040606  mov     r8d, [r14]
0x180040609  mov     rax, [rcx]
0x18004060c  mov     rax, [rax+18h]
0x180040610  call    _guard_dispatch_icall
0x180040615  mov     ebx, eax
0x180040617  lea     r15, WPP_RECORDER_INITIALIZED
0x18004061e  xor     r13d, r13d
0x180040621  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180040628  jz      short loc_18004065B
0x18004062a  mov     rcx, cs:WPP_GLOBAL_Control
0x180040631  cmp     [rcx+48h], r13w
0x180040636  jz      short loc_18004065B
0x180040638  mov     rcx, [rcx+40h]
0x18004063c  lea     r9d, [r13+6Dh]
0x180040640  mov     dword ptr [rsp+88h+var_60], eax
0x180040644  lea     r8d, [r13+2]
0x180040648  lea     rax, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x18004064f  xor     edx, edx
0x180040651  mov     [rsp+88h+Timeout], rax
0x180040656  call    WPP_RECORDER_SF_D
0x18004065b  lea     rsi, [rdi+0F8h]
0x180040662  test    ebx, ebx
0x180040664  js      short loc_1800406CE
0x180040666  lea     rsi, [rdi+0F8h]
0x18004066d  mov     eax, [r14]
0x180040670  mov     [rsi], eax
0x180040672  cmp     [rbp+370h], r13
0x180040679  jz      short loc_180040686
0x18004067b  mov     edx, [r14]; enum KSSTATE
0x18004067e  mov     rcx, rbp; this
0x180040681  call    ?SetPinClockState@CKsPin@@QEAAXW4KSSTATE@@@Z; CKsPin::SetPinClockState(KSSTATE)
0x180040686  lea     r15, WPP_RECORDER_INITIALIZED
0x18004068d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180040694  jz      short loc_1800406CE
0x180040696  mov     rcx, cs:WPP_GLOBAL_Control
0x18004069d  cmp     [rcx+48h], r13w
0x1800406a2  jz      short loc_1800406CE
0x1800406a4  mov     eax, [r14]
0x1800406a7  mov     r9d, 7Ah ; 'z'
0x1800406ad  mov     dword ptr [rsp+88h+var_60], eax
0x1800406b1  mov     rcx, [rcx+40h]
0x1800406b5  lea     rax, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x1800406bc  mov     r8d, 2
0x1800406c2  mov     [rsp+88h+Timeout], rax
0x1800406c7  xor     edx, edx
0x1800406c9  call    WPP_RECORDER_SF_D
0x1800406ce  mov     rcx, [rdi+58h]; Mutex
0x1800406d2  xor     edx, edx; Wait
0x1800406d4  call    cs:__imp_KeReleaseMutex
0x1800406db  nop     dword ptr [rax+rax+00h]
0x1800406e0  test    ebx, ebx
0x1800406e2  jns     short loc_180040705
0x1800406e4  mov     r8d, [r14]
0x1800406e7  mov     rdx, r12
0x1800406ea  mov     rcx, [rdi+48h]
0x1800406ee  mov     r9d, [rsi]
0x1800406f1  mov     dword ptr [rsp+88h+Timeout], r8d
0x1800406f6  xor     r8d, r8d
0x1800406f9  mov     rax, [rcx]
0x1800406fc  mov     rax, [rax+50h]
0x180040700  call    _guard_dispatch_icall
0x180040705  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18004070c  jz      loc_18004054D
0x180040712  mov     rcx, cs:WPP_GLOBAL_Control
0x180040719  lea     rdi, WPP_a6ecdf8dfd443675814f995f5d4f1b17_Traceguids
0x180040720  mov     r12d, 2
0x180040726  cmp     [rcx+48h], r13w
0x18004072b  jz      loc_180040CA6
0x180040731  mov     rcx, [rcx+40h]
0x180040735  lea     r9d, [r12+79h]
0x18004073a  mov     [rsp+88h+var_58], ebx
0x18004073e  mov     r8d, r12d
0x180040741  mov     [rsp+88h+var_60], rbp
0x180040746  xor     edx, edx
0x180040748  mov     [rsp+88h+Timeout], rdi
0x18004074d  call    WPP_RECORDER_SF_qD
0x180040752  jmp     loc_180040CA6
0x180040757  mov     rcx, rbp; this
0x18004075a  call    ?UseStandardTransport@CKsPin@@AEAAEXZ; CKsPin::UseStandardTransport(void)
0x18004075f  test    al, al
0x180040761  jz      loc_180040B9C
0x180040767  lea     rsi, [rdi+0F8h]
0x18004076e  xor     edx, edx
0x180040770  cmp     [rsi], edx
0x180040772  jnz     loc_180040AEF
0x180040778  cmp     [r14], edx
0x18004077b  jz      loc_180040AEF
0x180040781  mov     rcx, [r15+98h]; Thread
0x180040788  test    rcx, rcx
0x18004078b  jz      short loc_1800407D2
0x18004078d  mov     rax, [rdi+28h]
0x180040791  test    rax, rax
0x180040794  jz      short loc_1800407D2
0x180040796  cmp     [rax+0A8h], rdx
0x18004079d  jnz     short loc_1800407D2
0x18004079f  call    cs:__imp_PsGetThreadProcess
0x1800407a6  nop     dword ptr [rax+rax+00h]
0x1800407ab  mov     rcx, [rdi+28h]
0x1800407af  mov     [rcx+0A8h], rax
0x1800407b6  mov     rcx, [rdi+28h]
0x1800407ba  mov     rcx, [rcx+0A8h]
0x1800407c1  call    IsImmersiveApp
0x1800407c6  mov     rcx, [rdi+28h]
0x1800407ca  xor     edx, edx
0x1800407cc  mov     [rcx+0A0h], al
0x1800407d2  cmp     [rdi+120h], rdx
0x1800407d9  jnz     short loc_1800407ED
0x1800407db  mov     rax, [r15+0B8h]
0x1800407e2  mov     rcx, [rax+30h]
0x1800407e6  mov     [rdi+120h], rcx
0x1800407ed  mov     r9, [rdi+48h]; struct IKsDevice *
0x1800407f1  mov     rdx, rbp; struct IKsPin *
0x1800407f4  mov     r8, [rbp+288h]; struct IKsFilter *
0x1800407fb  mov     rcx, [rbp+250h]; void *
0x180040802  call    KspCreatePipeSection
0x180040807  mov     ebx, eax
0x180040809  cmp     eax, 0C000009Ah
0x18004080e  jz      short loc_18004085D
0x180040810  cmp     eax, 0C0000001h
0x180040815  jz      short loc_18004085D
0x180040817  and     eax, 0FFF0000h
0x18004081c  cmp     eax, 1F0000h
0x180040821  jz      short loc_18004085D
0x180040823  mov     rcx, rbp; this
0x180040826  call    ?QueryParentThermalStateSyncState@CKsPin@@QEAAXXZ; CKsPin::QueryParentThermalStateSyncState(void)
0x18004082b  lea     r15, WPP_RECORDER_INITIALIZED
0x180040832  xor     r13d, r13d
0x180040835  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18004083c  jz      loc_180040AE6
0x180040842  mov     rcx, cs:WPP_GLOBAL_Control
0x180040849  cmp     [rcx+48h], r13w
0x18004084e  jz      loc_180040AE6
0x180040854  lea     r9d, [r13+75h]
0x180040858  jmp     loc_180040AC9
0x18004085d  test    dword ptr [r13+14h], 8000000h
0x180040865  jnz     short loc_1800408B4
0x180040867  mov     rax, [rdi+28h]
0x18004086b  xor     r13d, r13d
0x18004086e  cmp     [rax+0A0h], r13b
0x180040875  jz      short loc_180040883
0x180040877  mov     rcx, rbp
0x18004087a  call    IsCameraStreamingToSameProcess
0x18004087f  test    al, al
0x180040881  jnz     short loc_1800408B7
  ... truncated ...
```
