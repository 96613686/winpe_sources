# RefsFsdCreate(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x140309ae0`
- end: `0x14030a195`
- name: `?RefsFsdCreate@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `1717`
- prototype: `__int64 __fastcall(struct _VOLUME_DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140039b60`
- `0x14003a520`
- `0x14003ec10`
- `0x140041b40`
- `0x14007dd30`
- `0x14008dbd0`
- `0x1400a648c`
- `0x1400ca788`
- `0x1401e9ce0`
- `0x1401e9dc0`
- `0x1401ea140`
- `0x1402959ec`
- `0x140296094`
- `0x14029f6ec`
- `0x140308620`
- `0x1403094f0`
- `0x140309ae0`
- `0x14030a1a0`
- `0x1403389e4`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140309f45`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140309f45`
- `ntoskrnl!IofCompleteRequest` at `0x14030a038`
- `ntoskrnl!IofCompleteRequest` at `0x14030a038`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140309c3a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140309f5c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140349d4b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140309c3a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140309f5c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140349d4b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140309bd5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14030a118`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140309bd5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14030a118`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140309bf4`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140309bf4`
- `ntoskrnl!IoGetStackLimits` at `0x140309e07`
- `ntoskrnl!IoGetStackLimits` at `0x140309e07`
- `ntoskrnl!IoClearActivityIdThread` at `0x14030a173`
- `ntoskrnl!IoClearActivityIdThread` at `0x14030a173`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140309f70`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14030a184`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140309f70`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14030a184`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140309ba9`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140309ba9`
- `ntoskrnl!KeInitializeEvent` at `0x140309c89`
- `ntoskrnl!KeInitializeEvent` at `0x140309c89`
- `HAL!KeQueryPerformanceCounter` at `0x140309c5f`
- `HAL!KeQueryPerformanceCounter` at `0x140309c5f`

## string_xrefs

- `0x140349dc7`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsFsdCreate(struct _VOLUME_DEVICE_OBJECT *a1, PIRP Irp)
{
  __int64 v5; // rbx
  struct _TOP_LEVEL_CONTEXT *v6; // rdi
  NTSTATUS v7; // eax
  int Status; // esi
  struct _IRP_CONTEXT **v9; // r12
  struct _IRP_CONTEXT *v10; // rdi
  int v11; // edx
  int v12; // eax
  struct _IRP_CONTEXT *v13; // rcx
  int v14; // r12d
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *v15; // r13
  PIRP TopLevelIrp; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  NTSTATUS v18; // r13d
  char v19; // bl
  __int64 v21; // rdx
  _QWORD *FsContext; // rax
  struct _IRP_CONTEXT **v23; // r15
  IRP *v24; // rcx
  bool v25; // [rsp+50h] [rbp-298h]
  struct _IRP_CONTEXT *v26; // [rsp+58h] [rbp-290h] BYREF
  int v27; // [rsp+60h] [rbp-288h]
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // [rsp+68h] [rbp-280h]
  unsigned __int64 HighLimit; // [rsp+70h] [rbp-278h] BYREF
  unsigned __int64 LowLimit; // [rsp+78h] [rbp-270h] BYREF
  PIRP Irpa; // [rsp+80h] [rbp-268h]
  _QWORD v32[4]; // [rsp+88h] [rbp-260h] BYREF
  struct _IRP_CONTEXT **v33; // [rsp+A8h] [rbp-240h]
  _QWORD Event[4]; // [rsp+B0h] [rbp-238h] BYREF
  _OWORD v35[14]; // [rsp+D0h] [rbp-218h] BYREF
  __int128 v36; // [rsp+1B0h] [rbp-138h] BYREF
  __int64 v37; // [rsp+1C0h] [rbp-128h]
  _BYTE v38[216]; // [rsp+1C8h] [rbp-120h] BYREF
  __int128 v39; // [rsp+2A0h] [rbp-48h] BYREF

  v32[3] = a1;
  v32[1] = Irp;
  v36 = 0;
  v37 = 0;
  v5 = 0;
  v26 = 0;
  memset(v35, 0, 0xD8u);
  memset(Event, 0, sizeof(Event));
  v39 = 0;
  v32[0] = 0;
  if ( *((_WORD *)a1 + 1) != 336 )
  {
    v6 = RefsInitializeTopLevelIrp((struct _TOP_LEVEL_CONTEXT *)&v36, 0, 0);
    Irpa = (PIRP)v6;
    IoIsOperationSynchronous(Irp);
    v7 = RefsInitializeIrpContext(Irp, 1u, 0, &v26);
    Status = v7;
    if ( v7 < 0 )
    {
      RefsCompleteRequest(0, Irp, v7);
      return (unsigned int)Status;
    }
    KeEnterCriticalRegion();
    v27 = IoPropagateActivityIdToThread(Irp, &v39, v32);
    v9 = (struct _IRP_CONTEXT **)((char *)v6 + 16);
    v33 = (struct _IRP_CONTEXT **)((char *)v6 + 16);
    if ( *((_QWORD *)v6 + 2) )
    {
      v10 = v26;
    }
    else
    {
      *((_DWORD *)v6 + 1) = 1397140410;
      v10 = v26;
      *v9 = v26;
      *((_QWORD *)v10 + 1) |= 0x100000uLL;
      IoSetTopLevelIrp(Irpa);
    }
    *((_QWORD *)v10 + 13) = *v9;
    if ( *(_BYTE *)(*((_QWORD *)v10 + 8) + 10496LL) )
    {
      *((LARGE_INTEGER *)v10 + 86) = KeQueryPerformanceCounter(0);
      *((_DWORD *)v10 + 175) = 26;
    }
    KeInitializeEvent((PRKEVENT)&Event[1], NotificationEvent, 0);
    do
    {
      memset(v38, 0, sizeof(v38));
      v35[0] = *(_OWORD *)v38;
      v35[1] = *(_OWORD *)&v38[16];
      v35[2] = *(_OWORD *)&v38[32];
      v35[3] = *(_OWORD *)&v38[48];
      v35[4] = *(_OWORD *)&v38[64];
      v35[5] = *(_OWORD *)&v38[80];
      v35[6] = *(_OWORD *)&v38[96];
      v35[7] = *(_OWORD *)&v38[112];
      v35[8] = *(_OWORD *)&v38[128];
      v35[9] = *(_OWORD *)&v38[144];
      v35[10] = *(_OWORD *)&v38[160];
      v35[11] = *(_OWORD *)&v38[176];
      v35[12] = *(_OWORD *)&v38[192];
      *(_QWORD *)&v35[13] = *(_QWORD *)&v38[208];
      p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&Irp->Tail.Overlay.CurrentStackLocation;
      *(_QWORD *)&v35[10] = Irp->Tail.Overlay.CurrentStackLocation;
      if ( Status == -1073741432 )
        RefsCheckpointForLogFileFull(v10);
      if ( v10 )
        RefsPreRequestProcessingExtend(v10, v11);
      *((_QWORD *)&v35[3] + 1) = Event;
      *((_QWORD *)v10 + 1) |= 0x10002uLL;
      v25 = (Irp->Tail.Overlay.CurrentStackLocation->Flags & 0x10) != 0;
      if ( (*((_DWORD *)v10 + 2) & 0x200LL) != 0 )
      {
        Status = RefsCommonVolumeOpen(v10, Irp, (struct _CREATE_CONTEXT *)v35);
      }
      else
      {
        HighLimit = 0;
        LowLimit = 0;
        IoGetStackLimits(&LowLimit, &HighLimit);
        if ( (unsigned __int64)&HighLimit - LowLimit <= 0x4800 )
          v12 = RefsCommonCreateOnNewStack(v10, Irp);
        else
          v12 = RefsCommonCreate(v10, Irp, (struct _CREATE_CONTEXT *)v35);
        Status = v12;
        if ( v12 == 871 )
        {
          *((_DWORD *)v10 + 1) |= 0x400u;
          RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v10, 0, 871);
          RefsWaitForCreateEvent(Irp);
          *(_BYTE *)(*(_QWORD *)&v35[10] + 3LL) &= ~1u;
        }
      }
    }
    while ( Status == -1073741608 || Status == 871 || Status == -1073741400 || Status == -1073741432 );
    v14 = 1;
    if ( Status == 259 )
    {
      RefsWaitForCreateEvent(Irp);
      Status = Irp->IoStatus.Status;
      v15 = p_CurrentStackLocation;
      *(union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&v35[10] = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9)p_CurrentStackLocation->CurrentStackLocation;
      *(_BYTE *)(*(_QWORD *)&v35[10] + 3LL) &= ~1u;
    }
    else
    {
      v15 = p_CurrentStackLocation;
    }
    if ( (_QWORD)xmmword_140261318 )
    {
      if ( (*((_DWORD *)v10 + 2) & 0x100000) != 0 )
      {
        TopLevelIrp = IoGetTopLevelIrp();
        *(_DWORD *)(&TopLevelIrp->Size + 1) = 0;
        *(_QWORD *)&TopLevelIrp->Flags = 0;
        IoSetTopLevelIrp((PIRP)TopLevelIrp->MdlAddress);
        *((_QWORD *)v10 + 1) &= ~0x100000uLL;
      }
      KeLeaveCriticalRegion();
      v14 = 0;
    }
    CurrentStackLocation = v15->CurrentStackLocation;
    *(union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&v35[10] = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9)v15->CurrentStackLocation;
    if ( *((_QWORD *)&v35[9] + 1) )
    {
      v21 = 0;
      FsContext = CurrentStackLocation->FileObject->FsContext;
      if ( FsContext )
        v21 = FsContext[18];
      if ( v21 )
        v5 = *(_QWORD *)(v21 + 192);
      v18 = ((__int64 (__fastcall *)(struct _VOLUME_DEVICE_OBJECT *, __int64, PIRP))xmmword_140261318)(a1, v5, Irp);
    }
    else
    {
      v18 = Status;
    }
    if ( v25 && ((unsigned int)dword_1402612AC & 0x10000000) != 0 )
    {
      if ( Status < 0 )
        goto LABEL_34;
      if ( Status != 260 )
        RefsSetupPagingFileEncryption(v13, *((struct _VCB **)v10 + 8), *((struct _SCB **)&v35[6] + 1), Irp, a1);
    }
    if ( Status >= 0 && v18 < 0 )
    {
      v19 = 1;
LABEL_54:
      if ( !v14 )
      {
        KeEnterCriticalRegion();
        v14 = 1;
      }
      v23 = v33;
      if ( !*v33 )
      {
        v24 = Irpa;
        *(_DWORD *)(&Irpa->Size + 1) = 1397140410;
        *v23 = v10;
        *((_QWORD *)v10 + 1) |= 0x100000uLL;
        IoSetTopLevelIrp(v24);
      }
      *((_QWORD *)v10 + 13) = *v23;
      if ( Status >= 0 && Status != 260 )
        RefsPostProcessEncryptedCreate(v10, p_CurrentStackLocation->CurrentStackLocation->FileObject);
LABEL_35:
      if ( !v19 )
      {
LABEL_36:
        *((_QWORD *)v10 + 1) &= 0xFFFFFFFFFFFEFFBFuLL;
        RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v10, Irp, Status);
        if ( v27 >= 0 )
          IoClearActivityIdThread(v32[0]);
        if ( v14 )
          KeLeaveCriticalRegion();
        return (unsigned int)Status;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        if ( v18 >= 0 )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
            goto LABEL_69;
          goto LABEL_68;
        }
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
LABEL_68:
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
            (unsigned int)v18);
      }
LABEL_69:
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(v18, 0, "Create.c", 0x517u);
      Status = v18;
      goto LABEL_36;
    }
LABEL_34:
    v19 = 0;
    if ( (BYTE4(v35[9]) & 5) == 0 )
      goto LABEL_35;
    goto LABEL_54;
  }
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = 1;
  IofCompleteRequest(Irp, 1);
  return 0;
}

```

## disassembly

```asm
0x140309ae0  mov     [rsp+arg_10], rbx
0x140309ae5  mov     [rsp+arg_18], rsi
0x140309aea  push    rdi
0x140309aeb  push    r12
0x140309aed  push    r13
0x140309aef  push    r14
0x140309af1  push    r15
0x140309af3  sub     rsp, 2C0h
0x140309afa  mov     rax, cs:__security_cookie
0x140309b01  xor     rax, rsp
0x140309b04  mov     [rsp+2E8h+var_38], rax
0x140309b0c  mov     r14, rdx
0x140309b0f  mov     r15, rcx
0x140309b12  mov     [rsp+2E8h+var_248], rcx
0x140309b1a  mov     [rsp+2E8h+var_258], rdx
0x140309b22  mov     r13, rdx
0x140309b25  xorps   xmm0, xmm0
0x140309b28  xor     eax, eax
0x140309b2a  movups  [rsp+2E8h+var_138], xmm0
0x140309b32  mov     [rsp+2E8h+var_128], rax
0x140309b3a  xor     ebx, ebx
0x140309b3c  mov     [rsp+2E8h+var_290], rbx
0x140309b41  xor     edx, edx; Val
0x140309b43  mov     r8d, 0D8h; Size
0x140309b49  lea     rcx, [rsp+2E8h+var_218]; void *
0x140309b51  call    memset
0x140309b56  xorps   xmm0, xmm0
0x140309b59  movups  xmmword ptr [rsp+2E8h+Event], xmm0
0x140309b61  movups  xmmword ptr [rsp+2E8h+Event+10h], xmm0
0x140309b69  movups  [rsp+2E8h+var_48], xmm0
0x140309b71  mov     [rsp+2E8h+var_260], rbx
0x140309b79  mov     eax, 150h
0x140309b7e  cmp     [r15+2], ax
0x140309b83  jz      loc_14030A027
0x140309b89  xor     r8d, r8d; unsigned __int8
0x140309b8c  xor     edx, edx; unsigned __int8
0x140309b8e  lea     rcx, [rsp+2E8h+var_138]; struct _TOP_LEVEL_CONTEXT *
0x140309b96  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x140309b9b  mov     rdi, rax
0x140309b9e  mov     [rsp+2E8h+Irp], rax
0x140309ba6  mov     rcx, r13; Irp
0x140309ba9  call    cs:__imp_IoIsOperationSynchronous
0x140309bb0  nop     dword ptr [rax+rax+00h]
0x140309bb5  lea     r9, [rsp+2E8h+var_290]; struct _IRP_CONTEXT **
0x140309bba  xor     r8d, r8d; unsigned __int8
0x140309bbd  mov     dl, 1; unsigned __int8
0x140309bbf  mov     rcx, r13; Irp
0x140309bc2  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x140309bc7  mov     esi, eax
0x140309bc9  test    eax, eax
0x140309bcb  js      loc_14030A0CD
0x140309bd1  mov     [rsp+2E8h+var_298], bl
0x140309bd5  call    cs:__imp_KeEnterCriticalRegion
0x140309bdc  nop     dword ptr [rax+rax+00h]
0x140309be1  lea     r8, [rsp+2E8h+var_260]
0x140309be9  lea     rdx, [rsp+2E8h+var_48]
0x140309bf1  mov     rcx, r13
0x140309bf4  call    cs:__imp_IoPropagateActivityIdToThread
0x140309bfb  nop     dword ptr [rax+rax+00h]
0x140309c00  mov     [rsp+2E8h+var_288], eax
0x140309c04  lea     r12, [rdi+10h]
0x140309c08  mov     [rsp+2E8h+var_240], r12
0x140309c10  cmp     [r12], rbx
0x140309c14  jnz     loc_14030A048
0x140309c1a  mov     dword ptr [rdi+4], 5346ABBAh
0x140309c21  mov     rdi, [rsp+2E8h+var_290]
0x140309c26  mov     [r12], rdi
0x140309c2a  or      qword ptr [rdi+8], 100000h
0x140309c32  mov     rcx, [rsp+2E8h+Irp]; Irp
0x140309c3a  call    cs:__imp_IoSetTopLevelIrp
0x140309c41  nop     dword ptr [rax+rax+00h]
0x140309c46  mov     rax, [r12]
0x140309c4a  mov     [rdi+68h], rax
0x140309c4e  mov     rax, [rdi+40h]
0x140309c52  movzx   ecx, byte ptr [rax+2900h]
0x140309c59  test    cl, cl
0x140309c5b  jz      short loc_140309C7C
0x140309c5d  xor     ecx, ecx; PerformanceFrequency
0x140309c5f  call    cs:__imp_KeQueryPerformanceCounter
0x140309c66  nop     dword ptr [rax+rax+00h]
0x140309c6b  mov     [rdi+2B0h], rax
0x140309c72  mov     dword ptr [rdi+2BCh], 1Ah
0x140309c7c  xor     r8d, r8d; State
0x140309c7f  xor     edx, edx; Type
0x140309c81  lea     rcx, [rsp+2E8h+Event+8]; Event
0x140309c89  call    cs:__imp_KeInitializeEvent
0x140309c90  nop     dword ptr [rax+rax+00h]
0x140309c95  xor     edx, edx; Val
0x140309c97  mov     r8d, 0D8h; Size
0x140309c9d  lea     rcx, [rsp+2E8h+var_120]; void *
0x140309ca5  call    memset
0x140309caa  movups  xmm0, [rsp+2E8h+var_120]
0x140309cb2  movups  [rsp+2E8h+var_218], xmm0
0x140309cba  movups  xmm1, [rsp+2E8h+var_110]
0x140309cc2  movups  [rsp+2E8h+var_208], xmm1
0x140309cca  movups  xmm0, [rsp+2E8h+var_100]
0x140309cd2  movups  [rsp+2E8h+var_1F8], xmm0
0x140309cda  movups  xmm1, [rsp+2E8h+var_F0]
0x140309ce2  movups  [rsp+2E8h+var_1E8], xmm1
0x140309cea  movups  xmm0, [rsp+2E8h+var_E0]
0x140309cf2  movups  [rsp+2E8h+var_1D8], xmm0
0x140309cfa  movups  xmm1, [rsp+2E8h+var_D0]
0x140309d02  movups  [rsp+2E8h+var_1C8], xmm1
0x140309d0a  movups  xmm0, [rsp+2E8h+var_C0]
0x140309d12  movups  xmmword ptr [rsp+2E8h+var_1B8], xmm0
0x140309d1a  movups  xmm1, [rsp+2E8h+var_B0]
0x140309d22  movups  [rsp+2E8h+var_1A8], xmm1
0x140309d2a  movups  xmm0, [rsp+2E8h+var_A0]
0x140309d32  movups  [rsp+2E8h+var_198], xmm0
0x140309d3a  movups  xmm1, [rsp+2E8h+var_90]
0x140309d42  movups  [rsp+2E8h+var_188], xmm1
0x140309d4a  movups  xmm0, [rsp+2E8h+var_80]
0x140309d52  movups  [rsp+2E8h+var_178], xmm0
0x140309d5a  movups  xmm1, [rsp+2E8h+var_70]
0x140309d62  movups  [rsp+2E8h+var_168], xmm1
0x140309d6a  movups  xmm0, [rsp+2E8h+var_60]
0x140309d72  movups  [rsp+2E8h+var_158], xmm0
0x140309d7a  mov     rax, [rsp+2E8h+var_50]
0x140309d82  mov     [rsp+2E8h+var_148], rax
0x140309d8a  lea     r12, [r13+0B8h]
0x140309d91  mov     [rsp+2E8h+var_280], r12
0x140309d96  mov     rax, [r12]
0x140309d9a  mov     qword ptr [rsp+2E8h+var_178], rax
0x140309da2  cmp     esi, 0C0000188h
0x140309da8  jz      loc_140309E99
0x140309dae  test    rdi, rdi
0x140309db1  jz      short loc_140309DBB
0x140309db3  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140309db6  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x140309dbb  lea     rax, [rsp+2E8h+Event]
0x140309dc3  mov     qword ptr [rsp+2E8h+var_1E8+8], rax
0x140309dcb  or      qword ptr [rdi+8], 10002h
0x140309dd3  mov     rax, [r12]
0x140309dd7  movzx   ecx, byte ptr [rax+2]
0x140309ddb  shr     cl, 4
0x140309dde  and     cl, 1
0x140309de1  mov     [rsp+2E8h+var_298], cl
0x140309de5  mov     eax, [rdi+8]
0x140309de8  bt      rax, 9
0x140309ded  jb      loc_140309E7E
0x140309df3  mov     [rsp+2E8h+HighLimit], rbx
0x140309df8  mov     [rsp+2E8h+LowLimit], rbx
0x140309dfd  lea     rdx, [rsp+2E8h+HighLimit]; HighLimit
0x140309e02  lea     rcx, [rsp+2E8h+LowLimit]; LowLimit
0x140309e07  call    cs:__imp_IoGetStackLimits
0x140309e0e  nop     dword ptr [rax+rax+00h]
0x140309e13  lea     rax, [rsp+2E8h+HighLimit]
0x140309e18  sub     rax, [rsp+2E8h+LowLimit]
0x140309e1d  lea     r8, [rsp+2E8h+var_218]; struct _CREATE_CONTEXT *
0x140309e25  mov     rdx, r14; Irp
0x140309e28  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140309e2b  cmp     rax, 4800h
0x140309e31  jbe     short loc_140309E77
0x140309e33  call    ?RefsCommonCreate@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z; RefsCommonCreate(_IRP_CONTEXT *,_IRP *,_CREATE_CONTEXT *)
0x140309e38  mov     [rsp+2E8h+var_294], eax
0x140309e3c  mov     esi, eax
0x140309e3e  cmp     eax, 367h
0x140309e43  jnz     short loc_140309EA6
0x140309e45  or      dword ptr [rdi+4], 400h
0x140309e4c  xor     edx, edx; Irp
0x140309e4e  mov     r8d, eax; Status
0x140309e51  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140309e54  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140309e59  mov     rdx, qword ptr [rsp+2E8h+var_1E8+8]
0x140309e61  mov     rcx, r14; Irp
0x140309e64  call    RefsWaitForCreateEvent
0x140309e69  mov     rax, qword ptr [rsp+2E8h+var_178]
0x140309e71  and     byte ptr [rax+3], 0FEh
0x140309e75  jmp     short loc_140309EA6
0x140309e77  call    RefsCommonCreateOnNewStack
0x140309e7c  jmp     short loc_140309E38
0x140309e7e  lea     r8, [rsp+2E8h+var_218]; struct _CREATE_CONTEXT *
0x140309e86  mov     rdx, r14; struct _IRP *
0x140309e89  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140309e8c  call    ?RefsCommonVolumeOpen@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z; RefsCommonVolumeOpen(_IRP_CONTEXT *,_IRP *,_CREATE_CONTEXT *)
0x140309e91  mov     esi, eax
0x140309e93  mov     [rsp+2E8h+var_294], eax
0x140309e97  jmp     short loc_140309EA6
0x140309e99  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140309e9c  call    ?RefsCheckpointForLogFileFull@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointForLogFileFull(_IRP_CONTEXT *)
0x140309ea1  jmp     loc_140309DAE
0x140309ea6  jmp     short loc_140309EEA
0x140309ea8  mov     rdi, [rsp+2E8h+var_290]
0x140309ead  test    rdi, rdi
0x140309eb0  jz      short loc_140309EC1
0x140309eb2  lea     rcx, [rsp+2E8h+var_218]
0x140309eba  mov     [rdi+90h], rcx
0x140309ec1  mov     r8d, eax; int
0x140309ec4  mov     r14, [rsp+2E8h+var_258]
0x140309ecc  mov     rdx, r14; struct _IRP *
0x140309ecf  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140309ed2  call    ?RefsProcessException@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsProcessException(_IRP_CONTEXT *,_IRP *,long)
0x140309ed7  mov     esi, eax
0x140309ed9  mov     [rsp+2E8h+var_294], eax
0x140309edd  xor     ebx, ebx
0x140309edf  mov     r13, r14
0x140309ee2  mov     r15, [rsp+2E8h+var_248]
0x140309eea  cmp     esi, 0C00000D8h
0x140309ef0  jz      loc_140309C95
0x140309ef6  cmp     esi, 367h
0x140309efc  jz      loc_140309C95
0x140309f02  cmp     esi, 0C00001A8h
0x140309f08  jz      loc_140309C95
0x140309f0e  cmp     esi, 0C0000188h
0x140309f14  jz      loc_140309C95
0x140309f1a  mov     r12d, 1
0x140309f20  cmp     esi, 103h
0x140309f26  jz      loc_14030A0DF
0x140309f2c  mov     r13, [rsp+2E8h+var_280]
0x140309f31  cmp     qword ptr cs:xmmword_140261318, 0
0x140309f39  jz      short loc_140309F7F
0x140309f3b  mov     eax, [rdi+8]
0x140309f3e  bt      rax, 14h
0x140309f43  jnb     short loc_140309F70
0x140309f45  call    cs:__imp_IoGetTopLevelIrp
0x140309f4c  nop     dword ptr [rax+rax+00h]
0x140309f51  mov     [rax+4], ebx
0x140309f54  mov     [rax+10h], rbx
0x140309f58  mov     rcx, [rax+8]; Irp
0x140309f5c  call    cs:__imp_IoSetTopLevelIrp
0x140309f63  nop     dword ptr [rax+rax+00h]
0x140309f68  and     qword ptr [rdi+8], 0FFFFFFFFFFEFFFFFh
0x140309f70  call    cs:__imp_KeLeaveCriticalRegion
0x140309f77  nop     dword ptr [rax+rax+00h]
0x140309f7c  mov     r12d, ebx
0x140309f7f  mov     rax, [r13+0]
0x140309f83  mov     qword ptr [rsp+2E8h+var_178], rax
0x140309f8b  cmp     qword ptr [rsp+2E8h+var_188+8], 0
0x140309f94  jnz     loc_14030A052
0x140309f9a  mov     r13d, esi
0x140309f9d  cmp     [rsp+2E8h+var_298], 0
0x140309fa2  jnz     loc_14030A08B
0x140309fa8  test    esi, esi
0x140309faa  js      short loc_140309FB5
0x140309fac  test    r13d, r13d
0x140309faf  js      loc_14030A10D
0x140309fb5  xor     bl, bl
0x140309fb7  test    byte ptr [rsp+2E8h+var_188+4], 5
0x140309fbf  jnz     loc_14030A10F
0x140309fc5  test    bl, bl
0x140309fc7  jnz     loc_14030A12F
0x140309fcd  and     qword ptr [rdi+8], 0FFFFFFFFFFFEFFBFh
0x140309fd5  mov     r8d, esi; Status
0x140309fd8  mov     rdx, r14; Irp
0x140309fdb  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140309fde  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140309fe3  cmp     [rsp+2E8h+var_288], 0
0x140309fe8  jge     loc_14030A16B
0x140309fee  test    r12d, r12d
0x140309ff1  jnz     loc_14030A184
0x140309ff7  mov     eax, esi
0x140309ff9  mov     rcx, [rsp+2E8h+var_38]
0x14030a001  xor     rcx, rsp; StackCookie
0x14030a004  call    __security_check_cookie
0x14030a009  lea     r11, [rsp+2E8h+var_28]
0x14030a011  mov     rbx, [r11+40h]
0x14030a015  mov     rsi, [r11+48h]
0x14030a019  mov     rsp, r11
0x14030a01c  pop     r15
0x14030a01e  pop     r14
0x14030a020  pop     r13
0x14030a022  pop     r12
0x14030a024  pop     rdi
0x14030a025  retn
0x14030a027  mov     [r14+30h], ebx
0x14030a02b  mov     qword ptr [r14+38h], 1
0x14030a033  mov     dl, 1; PriorityBoost
0x14030a035  mov     rcx, r14; Irp
0x14030a038  call    cs:__imp_IofCompleteRequest
0x14030a03f  nop     dword ptr [rax+rax+00h]
0x14030a044  xor     eax, eax
0x14030a046  jmp     short loc_140309FF9
0x14030a048  mov     rdi, [rsp+2E8h+var_290]
0x14030a04d  jmp     loc_140309C46
0x14030a052  mov     rdx, rbx
0x14030a055  mov     r9, [rax+30h]
0x14030a059  mov     rax, [r9+18h]
0x14030a05d  test    rax, rax
0x14030a060  jz      short loc_14030A069
0x14030a062  mov     rdx, [rax+90h]
0x14030a069  test    rdx, rdx
0x14030a06c  jz      loc_140349CD8
0x14030a072  mov     rbx, [rdx+0C0h]
0x14030a079  movzx   r8d, byte ptr [rdx+1Ch]
0x14030a07e  shr     r8d, 4
0x14030a082  and     r8d, 1
0x14030a086  jmp     loc_140349CDB
0x14030a08b  test    cs:dword_1402612AC, 10000000h
0x14030a095  jz      loc_140309FA8
0x14030a09b  test    esi, esi
0x14030a09d  js      loc_140309FB5
0x14030a0a3  cmp     esi, 104h
0x14030a0a9  jz      loc_140309FA8
0x14030a0af  mov     [rsp+2E8h+var_2C8], r15; struct _VOLUME_DEVICE_OBJECT *
0x14030a0b4  mov     r9, r14; struct _IRP *
0x14030a0b7  mov     r8, [rsp+2E8h+var_1B8+8]; struct _SCB *
0x14030a0bf  mov     rdx, [rdi+40h]; struct _VCB *
0x14030a0c3  call    ?RefsSetupPagingFileEncryption@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAU_SCB@@PEAU_IRP@@PEAU_VOLUME_DEVICE_OBJECT@@@Z; RefsSetupPagingFileEncryption(_IRP_CONTEXT *,_VCB *,_SCB *,_IRP *,_VOLUME_DEVICE_OBJECT *)
0x14030a0c8  jmp     loc_140309FA8
0x14030a0cd  mov     r8d, esi; Status
  ... truncated ...
```
