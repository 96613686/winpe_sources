# RefsFsdCreate(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x14030d160`
- end: `0x14030d815`
- name: `?RefsFsdCreate@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `1717`
- prototype: `__int64 __fastcall(struct _VOLUME_DEVICE_OBJECT *, PIRP Irp)`
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000b1b0`
- `0x14000e0e0`
- `0x140050ba0`
- `0x140075660`
- `0x1400862c0`
- `0x14009a130`
- `0x1400a069c`
- `0x1400d0fd8`
- `0x1401f3fb0`
- `0x1401f4090`
- `0x1401f4400`
- `0x14029c90c`
- `0x14029cfb4`
- `0x1402a6454`
- `0x14030bca0`
- `0x14030cb70`
- `0x14030d160`
- `0x14030d820`
- `0x14033a7a8`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x14030d5c5`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14030d5c5`
- `ntoskrnl!IofCompleteRequest` at `0x14030d6b8`
- `ntoskrnl!IofCompleteRequest` at `0x14030d6b8`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14030d2ba`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14030d5dc`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14034ccd7`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14030d2ba`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14030d5dc`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14034ccd7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14030d255`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14030d798`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14030d255`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14030d798`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14030d274`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x14030d274`
- `ntoskrnl!IoGetStackLimits` at `0x14030d487`
- `ntoskrnl!IoGetStackLimits` at `0x14030d487`
- `ntoskrnl!IoClearActivityIdThread` at `0x14030d7f3`
- `ntoskrnl!IoClearActivityIdThread` at `0x14030d7f3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14030d5f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14030d804`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14030d5f0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14030d804`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14030d229`
- `ntoskrnl!IoIsOperationSynchronous` at `0x14030d229`
- `ntoskrnl!KeInitializeEvent` at `0x14030d309`
- `ntoskrnl!KeInitializeEvent` at `0x14030d309`
- `HAL!KeQueryPerformanceCounter` at `0x14030d2df`
- `HAL!KeQueryPerformanceCounter` at `0x14030d2df`

## string_xrefs

- `0x14034cd53`: `Create.c`

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
    if ( *(_BYTE *)(*((_QWORD *)v10 + 8) + 10304LL) )
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
    if ( (_QWORD)xmmword_140268358 )
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
      v18 = ((__int64 (__fastcall *)(struct _VOLUME_DEVICE_OBJECT *, __int64, PIRP))xmmword_140268358)(a1, v5, Irp);
    }
    else
    {
      v18 = Status;
    }
    if ( v25 && ((unsigned int)dword_1402682EC & 0x10000000) != 0 )
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
            WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
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
0x14030d160  mov     [rsp+arg_10], rbx
0x14030d165  mov     [rsp+arg_18], rsi
0x14030d16a  push    rdi
0x14030d16b  push    r12
0x14030d16d  push    r13
0x14030d16f  push    r14
0x14030d171  push    r15
0x14030d173  sub     rsp, 2C0h
0x14030d17a  mov     rax, cs:__security_cookie
0x14030d181  xor     rax, rsp
0x14030d184  mov     [rsp+2E8h+var_38], rax
0x14030d18c  mov     r14, rdx
0x14030d18f  mov     r15, rcx
0x14030d192  mov     [rsp+2E8h+var_248], rcx
0x14030d19a  mov     [rsp+2E8h+var_258], rdx
0x14030d1a2  mov     r13, rdx
0x14030d1a5  xorps   xmm0, xmm0
0x14030d1a8  xor     eax, eax
0x14030d1aa  movups  [rsp+2E8h+var_138], xmm0
0x14030d1b2  mov     [rsp+2E8h+var_128], rax
0x14030d1ba  xor     ebx, ebx
0x14030d1bc  mov     [rsp+2E8h+var_290], rbx
0x14030d1c1  xor     edx, edx; Val
0x14030d1c3  mov     r8d, 0D8h; Size
0x14030d1c9  lea     rcx, [rsp+2E8h+var_218]; void *
0x14030d1d1  call    memset
0x14030d1d6  xorps   xmm0, xmm0
0x14030d1d9  movups  xmmword ptr [rsp+2E8h+Event], xmm0
0x14030d1e1  movups  xmmword ptr [rsp+2E8h+Event+10h], xmm0
0x14030d1e9  movups  [rsp+2E8h+var_48], xmm0
0x14030d1f1  mov     [rsp+2E8h+var_260], rbx
0x14030d1f9  mov     eax, 150h
0x14030d1fe  cmp     [r15+2], ax
0x14030d203  jz      loc_14030D6A7
0x14030d209  xor     r8d, r8d; unsigned __int8
0x14030d20c  xor     edx, edx; unsigned __int8
0x14030d20e  lea     rcx, [rsp+2E8h+var_138]; struct _TOP_LEVEL_CONTEXT *
0x14030d216  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x14030d21b  mov     rdi, rax
0x14030d21e  mov     [rsp+2E8h+Irp], rax
0x14030d226  mov     rcx, r13; Irp
0x14030d229  call    cs:__imp_IoIsOperationSynchronous
0x14030d230  nop     dword ptr [rax+rax+00h]
0x14030d235  lea     r9, [rsp+2E8h+var_290]; struct _IRP_CONTEXT **
0x14030d23a  xor     r8d, r8d; unsigned __int8
0x14030d23d  mov     dl, 1; unsigned __int8
0x14030d23f  mov     rcx, r13; Irp
0x14030d242  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x14030d247  mov     esi, eax
0x14030d249  test    eax, eax
0x14030d24b  js      loc_14030D74D
0x14030d251  mov     [rsp+2E8h+var_298], bl
0x14030d255  call    cs:__imp_KeEnterCriticalRegion
0x14030d25c  nop     dword ptr [rax+rax+00h]
0x14030d261  lea     r8, [rsp+2E8h+var_260]
0x14030d269  lea     rdx, [rsp+2E8h+var_48]
0x14030d271  mov     rcx, r13
0x14030d274  call    cs:__imp_IoPropagateActivityIdToThread
0x14030d27b  nop     dword ptr [rax+rax+00h]
0x14030d280  mov     [rsp+2E8h+var_288], eax
0x14030d284  lea     r12, [rdi+10h]
0x14030d288  mov     [rsp+2E8h+var_240], r12
0x14030d290  cmp     [r12], rbx
0x14030d294  jnz     loc_14030D6C8
0x14030d29a  mov     dword ptr [rdi+4], 5346ABBAh
0x14030d2a1  mov     rdi, [rsp+2E8h+var_290]
0x14030d2a6  mov     [r12], rdi
0x14030d2aa  or      qword ptr [rdi+8], 100000h
0x14030d2b2  mov     rcx, [rsp+2E8h+Irp]; Irp
0x14030d2ba  call    cs:__imp_IoSetTopLevelIrp
0x14030d2c1  nop     dword ptr [rax+rax+00h]
0x14030d2c6  mov     rax, [r12]
0x14030d2ca  mov     [rdi+68h], rax
0x14030d2ce  mov     rax, [rdi+40h]
0x14030d2d2  movzx   ecx, byte ptr [rax+2840h]
0x14030d2d9  test    cl, cl
0x14030d2db  jz      short loc_14030D2FC
0x14030d2dd  xor     ecx, ecx; PerformanceFrequency
0x14030d2df  call    cs:__imp_KeQueryPerformanceCounter
0x14030d2e6  nop     dword ptr [rax+rax+00h]
0x14030d2eb  mov     [rdi+2B0h], rax
0x14030d2f2  mov     dword ptr [rdi+2BCh], 1Ah
0x14030d2fc  xor     r8d, r8d; State
0x14030d2ff  xor     edx, edx; Type
0x14030d301  lea     rcx, [rsp+2E8h+Event+8]; Event
0x14030d309  call    cs:__imp_KeInitializeEvent
0x14030d310  nop     dword ptr [rax+rax+00h]
0x14030d315  xor     edx, edx; Val
0x14030d317  mov     r8d, 0D8h; Size
0x14030d31d  lea     rcx, [rsp+2E8h+var_120]; void *
0x14030d325  call    memset
0x14030d32a  movups  xmm0, [rsp+2E8h+var_120]
0x14030d332  movups  [rsp+2E8h+var_218], xmm0
0x14030d33a  movups  xmm1, [rsp+2E8h+var_110]
0x14030d342  movups  [rsp+2E8h+var_208], xmm1
0x14030d34a  movups  xmm0, [rsp+2E8h+var_100]
0x14030d352  movups  [rsp+2E8h+var_1F8], xmm0
0x14030d35a  movups  xmm1, [rsp+2E8h+var_F0]
0x14030d362  movups  [rsp+2E8h+var_1E8], xmm1
0x14030d36a  movups  xmm0, [rsp+2E8h+var_E0]
0x14030d372  movups  [rsp+2E8h+var_1D8], xmm0
0x14030d37a  movups  xmm1, [rsp+2E8h+var_D0]
0x14030d382  movups  [rsp+2E8h+var_1C8], xmm1
0x14030d38a  movups  xmm0, [rsp+2E8h+var_C0]
0x14030d392  movups  xmmword ptr [rsp+2E8h+var_1B8], xmm0
0x14030d39a  movups  xmm1, [rsp+2E8h+var_B0]
0x14030d3a2  movups  [rsp+2E8h+var_1A8], xmm1
0x14030d3aa  movups  xmm0, [rsp+2E8h+var_A0]
0x14030d3b2  movups  [rsp+2E8h+var_198], xmm0
0x14030d3ba  movups  xmm1, [rsp+2E8h+var_90]
0x14030d3c2  movups  [rsp+2E8h+var_188], xmm1
0x14030d3ca  movups  xmm0, [rsp+2E8h+var_80]
0x14030d3d2  movups  [rsp+2E8h+var_178], xmm0
0x14030d3da  movups  xmm1, [rsp+2E8h+var_70]
0x14030d3e2  movups  [rsp+2E8h+var_168], xmm1
0x14030d3ea  movups  xmm0, [rsp+2E8h+var_60]
0x14030d3f2  movups  [rsp+2E8h+var_158], xmm0
0x14030d3fa  mov     rax, [rsp+2E8h+var_50]
0x14030d402  mov     [rsp+2E8h+var_148], rax
0x14030d40a  lea     r12, [r13+0B8h]
0x14030d411  mov     [rsp+2E8h+var_280], r12
0x14030d416  mov     rax, [r12]
0x14030d41a  mov     qword ptr [rsp+2E8h+var_178], rax
0x14030d422  cmp     esi, 0C0000188h
0x14030d428  jz      loc_14030D519
0x14030d42e  test    rdi, rdi
0x14030d431  jz      short loc_14030D43B
0x14030d433  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14030d436  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x14030d43b  lea     rax, [rsp+2E8h+Event]
0x14030d443  mov     qword ptr [rsp+2E8h+var_1E8+8], rax
0x14030d44b  or      qword ptr [rdi+8], 10002h
0x14030d453  mov     rax, [r12]
0x14030d457  movzx   ecx, byte ptr [rax+2]
0x14030d45b  shr     cl, 4
0x14030d45e  and     cl, 1
0x14030d461  mov     [rsp+2E8h+var_298], cl
0x14030d465  mov     eax, [rdi+8]
0x14030d468  bt      rax, 9
0x14030d46d  jb      loc_14030D4FE
0x14030d473  mov     [rsp+2E8h+HighLimit], rbx
0x14030d478  mov     [rsp+2E8h+LowLimit], rbx
0x14030d47d  lea     rdx, [rsp+2E8h+HighLimit]; HighLimit
0x14030d482  lea     rcx, [rsp+2E8h+LowLimit]; LowLimit
0x14030d487  call    cs:__imp_IoGetStackLimits
0x14030d48e  nop     dword ptr [rax+rax+00h]
0x14030d493  lea     rax, [rsp+2E8h+HighLimit]
0x14030d498  sub     rax, [rsp+2E8h+LowLimit]
0x14030d49d  lea     r8, [rsp+2E8h+var_218]; struct _CREATE_CONTEXT *
0x14030d4a5  mov     rdx, r14; Irp
0x14030d4a8  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14030d4ab  cmp     rax, 4800h
0x14030d4b1  jbe     short loc_14030D4F7
0x14030d4b3  call    ?RefsCommonCreate@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z; RefsCommonCreate(_IRP_CONTEXT *,_IRP *,_CREATE_CONTEXT *)
0x14030d4b8  mov     [rsp+2E8h+var_294], eax
0x14030d4bc  mov     esi, eax
0x14030d4be  cmp     eax, 367h
0x14030d4c3  jnz     short loc_14030D526
0x14030d4c5  or      dword ptr [rdi+4], 400h
0x14030d4cc  xor     edx, edx; Irp
0x14030d4ce  mov     r8d, eax; Status
0x14030d4d1  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14030d4d4  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x14030d4d9  mov     rdx, qword ptr [rsp+2E8h+var_1E8+8]
0x14030d4e1  mov     rcx, r14; Irp
0x14030d4e4  call    RefsWaitForCreateEvent
0x14030d4e9  mov     rax, qword ptr [rsp+2E8h+var_178]
0x14030d4f1  and     byte ptr [rax+3], 0FEh
0x14030d4f5  jmp     short loc_14030D526
0x14030d4f7  call    RefsCommonCreateOnNewStack
0x14030d4fc  jmp     short loc_14030D4B8
0x14030d4fe  lea     r8, [rsp+2E8h+var_218]; struct _CREATE_CONTEXT *
0x14030d506  mov     rdx, r14; struct _IRP *
0x14030d509  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14030d50c  call    ?RefsCommonVolumeOpen@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z; RefsCommonVolumeOpen(_IRP_CONTEXT *,_IRP *,_CREATE_CONTEXT *)
0x14030d511  mov     esi, eax
0x14030d513  mov     [rsp+2E8h+var_294], eax
0x14030d517  jmp     short loc_14030D526
0x14030d519  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14030d51c  call    ?RefsCheckpointForLogFileFull@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointForLogFileFull(_IRP_CONTEXT *)
0x14030d521  jmp     loc_14030D42E
0x14030d526  jmp     short loc_14030D56A
0x14030d528  mov     rdi, [rsp+2E8h+var_290]
0x14030d52d  test    rdi, rdi
0x14030d530  jz      short loc_14030D541
0x14030d532  lea     rcx, [rsp+2E8h+var_218]
0x14030d53a  mov     [rdi+90h], rcx
0x14030d541  mov     r8d, eax; int
0x14030d544  mov     r14, [rsp+2E8h+var_258]
0x14030d54c  mov     rdx, r14; struct _IRP *
0x14030d54f  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14030d552  call    ?RefsProcessException@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsProcessException(_IRP_CONTEXT *,_IRP *,long)
0x14030d557  mov     esi, eax
0x14030d559  mov     [rsp+2E8h+var_294], eax
0x14030d55d  xor     ebx, ebx
0x14030d55f  mov     r13, r14
0x14030d562  mov     r15, [rsp+2E8h+var_248]
0x14030d56a  cmp     esi, 0C00000D8h
0x14030d570  jz      loc_14030D315
0x14030d576  cmp     esi, 367h
0x14030d57c  jz      loc_14030D315
0x14030d582  cmp     esi, 0C00001A8h
0x14030d588  jz      loc_14030D315
0x14030d58e  cmp     esi, 0C0000188h
0x14030d594  jz      loc_14030D315
0x14030d59a  mov     r12d, 1
0x14030d5a0  cmp     esi, 103h
0x14030d5a6  jz      loc_14030D75F
0x14030d5ac  mov     r13, [rsp+2E8h+var_280]
0x14030d5b1  cmp     qword ptr cs:xmmword_140268358, 0
0x14030d5b9  jz      short loc_14030D5FF
0x14030d5bb  mov     eax, [rdi+8]
0x14030d5be  bt      rax, 14h
0x14030d5c3  jnb     short loc_14030D5F0
0x14030d5c5  call    cs:__imp_IoGetTopLevelIrp
0x14030d5cc  nop     dword ptr [rax+rax+00h]
0x14030d5d1  mov     [rax+4], ebx
0x14030d5d4  mov     [rax+10h], rbx
0x14030d5d8  mov     rcx, [rax+8]; Irp
0x14030d5dc  call    cs:__imp_IoSetTopLevelIrp
0x14030d5e3  nop     dword ptr [rax+rax+00h]
0x14030d5e8  and     qword ptr [rdi+8], 0FFFFFFFFFFEFFFFFh
0x14030d5f0  call    cs:__imp_KeLeaveCriticalRegion
0x14030d5f7  nop     dword ptr [rax+rax+00h]
0x14030d5fc  mov     r12d, ebx
0x14030d5ff  mov     rax, [r13+0]
0x14030d603  mov     qword ptr [rsp+2E8h+var_178], rax
0x14030d60b  cmp     qword ptr [rsp+2E8h+var_188+8], 0
0x14030d614  jnz     loc_14030D6D2
0x14030d61a  mov     r13d, esi
0x14030d61d  cmp     [rsp+2E8h+var_298], 0
0x14030d622  jnz     loc_14030D70B
0x14030d628  test    esi, esi
0x14030d62a  js      short loc_14030D635
0x14030d62c  test    r13d, r13d
0x14030d62f  js      loc_14030D78D
0x14030d635  xor     bl, bl
0x14030d637  test    byte ptr [rsp+2E8h+var_188+4], 5
0x14030d63f  jnz     loc_14030D78F
0x14030d645  test    bl, bl
0x14030d647  jnz     loc_14030D7AF
0x14030d64d  and     qword ptr [rdi+8], 0FFFFFFFFFFFEFFBFh
0x14030d655  mov     r8d, esi; Status
0x14030d658  mov     rdx, r14; Irp
0x14030d65b  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14030d65e  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x14030d663  cmp     [rsp+2E8h+var_288], 0
0x14030d668  jge     loc_14030D7EB
0x14030d66e  test    r12d, r12d
0x14030d671  jnz     loc_14030D804
0x14030d677  mov     eax, esi
0x14030d679  mov     rcx, [rsp+2E8h+var_38]
0x14030d681  xor     rcx, rsp; StackCookie
0x14030d684  call    __security_check_cookie
0x14030d689  lea     r11, [rsp+2E8h+var_28]
0x14030d691  mov     rbx, [r11+40h]
0x14030d695  mov     rsi, [r11+48h]
0x14030d699  mov     rsp, r11
0x14030d69c  pop     r15
0x14030d69e  pop     r14
0x14030d6a0  pop     r13
0x14030d6a2  pop     r12
0x14030d6a4  pop     rdi
0x14030d6a5  retn
0x14030d6a7  mov     [r14+30h], ebx
0x14030d6ab  mov     qword ptr [r14+38h], 1
0x14030d6b3  mov     dl, 1; PriorityBoost
0x14030d6b5  mov     rcx, r14; Irp
0x14030d6b8  call    cs:__imp_IofCompleteRequest
0x14030d6bf  nop     dword ptr [rax+rax+00h]
0x14030d6c4  xor     eax, eax
0x14030d6c6  jmp     short loc_14030D679
0x14030d6c8  mov     rdi, [rsp+2E8h+var_290]
0x14030d6cd  jmp     loc_14030D2C6
0x14030d6d2  mov     rdx, rbx
0x14030d6d5  mov     r9, [rax+30h]
0x14030d6d9  mov     rax, [r9+18h]
0x14030d6dd  test    rax, rax
0x14030d6e0  jz      short loc_14030D6E9
0x14030d6e2  mov     rdx, [rax+90h]
0x14030d6e9  test    rdx, rdx
0x14030d6ec  jz      loc_14034CC64
0x14030d6f2  mov     rbx, [rdx+0C0h]
0x14030d6f9  movzx   r8d, byte ptr [rdx+1Ch]
0x14030d6fe  shr     r8d, 4
0x14030d702  and     r8d, 1
0x14030d706  jmp     loc_14034CC67
0x14030d70b  test    cs:dword_1402682EC, 10000000h
0x14030d715  jz      loc_14030D628
0x14030d71b  test    esi, esi
0x14030d71d  js      loc_14030D635
0x14030d723  cmp     esi, 104h
0x14030d729  jz      loc_14030D628
0x14030d72f  mov     [rsp+2E8h+var_2C8], r15; struct _VOLUME_DEVICE_OBJECT *
0x14030d734  mov     r9, r14; struct _IRP *
0x14030d737  mov     r8, [rsp+2E8h+var_1B8+8]; struct _SCB *
0x14030d73f  mov     rdx, [rdi+40h]; struct _VCB *
0x14030d743  call    ?RefsSetupPagingFileEncryption@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAU_SCB@@PEAU_IRP@@PEAU_VOLUME_DEVICE_OBJECT@@@Z; RefsSetupPagingFileEncryption(_IRP_CONTEXT *,_VCB *,_SCB *,_IRP *,_VOLUME_DEVICE_OBJECT *)
0x14030d748  jmp     loc_14030D628
0x14030d74d  mov     r8d, esi; Status
  ... truncated ...
```
