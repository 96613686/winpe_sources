# FveInitEphemeralVolume

- ea: `0x1400ccd18`
- end: `0x1400cd707`
- name: `FveInitEphemeralVolume`
- size: `2543`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `29`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400a9488`

## callees

- `0x140005e60`
- `0x140008e80`
- `0x140008f04`
- `0x14000bc14`
- `0x140012d0c`
- `0x1400141bc`
- `0x140014e34`
- `0x140017854`
- `0x140022bf0`
- `0x140023040`
- `0x140024a64`
- `0x1400251b4`
- `0x14002f334`
- `0x140063828`
- `0x140063bd4`
- `0x140064548`
- `0x140065384`
- `0x140097240`
- `0x1400b6f14`
- `0x1400beb8c`
- `0x1400ccd18`
- `0x1400dce00`
- `0x1400dd144`
- `0x1400dd340`
- `0x1400e1690`
- `0x1400e64b4`
- `0x1400e6aa4`
- `0x1400e6f90`
- `0x1400e7934`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x1400cd17f`
- `ntoskrnl!ExUuidCreate` at `0x1400cd17f`
- `ntoskrnl!KeBugCheckEx` at `0x1400cd572`
- `ntoskrnl!KeBugCheckEx` at `0x1400cd572`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd65b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd674`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd65b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cd674`
- `ntoskrnl!ExAllocatePool2` at `0x1400ccee2`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd05d`
- `ntoskrnl!ExAllocatePool2` at `0x1400ccee2`
- `ntoskrnl!ExAllocatePool2` at `0x1400cd05d`

## pseudocode

```c
__int64 __fastcall FveInitEphemeralVolume(__int64 Context)
{
  UUID *Pool2; // r13
  UUID *v3; // r14
  __int64 v4; // r12
  void *v5; // rsi
  __int64 v6; // r15
  __int64 v7; // r9
  __int64 v8; // rcx
  int inited; // ebx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned int v16; // ecx
  unsigned int v17; // r8d
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rcx
  int v21; // edx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rdx
  int v27; // ebx
  __int128 v28; // xmm1
  __int64 v29; // rdx
  void *v30; // rax
  __int64 v31; // r8
  __int128 v32; // xmm0
  __int128 v33; // xmm1
  __int64 v34; // rax
  __int64 *v35; // rax
  __int64 v36; // rcx
  int BugCheckParameter4; // [rsp+20h] [rbp-E0h]
  char v39; // [rsp+40h] [rbp-C0h]
  char v40; // [rsp+41h] [rbp-BFh]
  char v41; // [rsp+42h] [rbp-BEh]
  char v42; // [rsp+43h] [rbp-BDh]
  __int128 v43; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h]
  __int64 v45; // [rsp+60h] [rbp-A0h] BYREF
  void *v46; // [rsp+68h] [rbp-98h]
  int v47[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v48; // [rsp+78h] [rbp-88h] BYREF
  int v49; // [rsp+80h] [rbp-80h]
  __int64 v50; // [rsp+88h] [rbp-78h] BYREF
  void *v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h] BYREF
  _OWORD v53[5]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v54[144]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v55[12]; // [rsp+180h] [rbp+80h] BYREF

  v50 = 0;
  v40 = 0;
  Pool2 = 0;
  v3 = 0;
  memset(v55, 0, 0x5Cu);
  v52 = 0;
  v39 = 0;
  *(_QWORD *)v47 = 0;
  v4 = 0;
  v51 = 0;
  v5 = 0;
  v46 = 0;
  v6 = 0;
  v45 = 0;
  memset(v54, 0, sizeof(v54));
  v42 = 0;
  v41 = 1;
  memset(v53, 0, 0x48u);
  v43 = 0;
  v44 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids);
  }
  v8 = *(_QWORD *)(Context + 8);
  if ( (*(_BYTE *)(v8 + 10592) & 1) == 0 && (*(_DWORD *)(v8 + 9928) & 0x100000) == 0 )
  {
    inited = -1073741637;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_98;
    }
    v11 = 11;
    goto LABEL_11;
  }
  if ( (*(_BYTE *)(Context + 4419) & 8) != 0 )
    FveCleanup((PVOID)Context);
  *(_BYTE *)(Context + 4419) |= 8u;
  FveLockDriver(Context);
  inited = FveWorkerInit(Context);
  if ( inited < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_98;
    }
    v11 = 12;
    goto LABEL_11;
  }
  Pool2 = (UUID *)ExAllocatePool2(64, 112, 809850438);
  if ( !Pool2 )
  {
    inited = -1073741670;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_25;
    }
    v13 = 13;
LABEL_24:
    WPP_SF_d(v12->AttachedDevice, v13, WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids, 3221225626LL);
LABEL_25:
    HIDWORD(v43) = -1073741670;
    v5 = v51;
LABEL_99:
    v35 = FVE_EPHEMERAL_VOLUME_INIT_FAILED;
    goto LABEL_100;
  }
  inited = FveDeviceControlSynchronousEx(*(PDEVICE_OBJECT *)(Context + 112), 0, (__int64)&v50, 8, (__int64)&v48);
  if ( inited < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_98;
    }
    v11 = 14;
    goto LABEL_11;
  }
  v7 = v50;
  if ( v50 < 0 )
  {
    *(_QWORD *)(Context + 1048) = -1;
    inited = -1073741675;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids,
        v7,
        -1073741675);
    }
    goto LABEL_98;
  }
  *(_QWORD *)(Context + 1048) = v50;
  v14 = 0;
  v15 = 0;
  do
  {
    ++v14;
    *(_QWORD *)((char *)v53 + v15) = 0;
    *(_DWORD *)((char *)v53 + v15 + 8) = 0;
    *(_WORD *)((char *)v53 + v15 + 12) = 0;
    *(_QWORD *)((char *)&v53[1] + v15) = 0;
    v15 += 24;
  }
  while ( v14 != 3 );
  *(_DWORD *)(Context + 1312) = 1;
  _InterlockedIncrement((volatile signed __int32 *)(Context + 880));
  v40 = 1;
  inited = FveRegisterPnpNotifications((PVOID)Context);
  if ( inited < 0 )
    goto LABEL_92;
  v16 = *(_DWORD *)(Context + 1308);
  if ( ((v16 - 1) & v16) != 0 || !v16 )
  {
    v17 = 0x10000;
    if ( 0x10000 % v16 )
      v17 = v16 - 0x10000 % v16 + 0x10000;
  }
  else
  {
    v17 = ~(v16 - 1) & (v16 + 0xFFFF);
  }
  v3 = (UUID *)ExAllocatePool2(256, v17, 809850438);
  if ( !v3 )
  {
    inited = -1073741670;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_25;
    }
    v13 = 16;
    goto LABEL_24;
  }
  LOBYTE(v18) = 1;
  FvepAcquireDevFveLock(Context, v54, v18);
  v42 = 1;
  inited = FveInformationCreate(v3);
  if ( inited < 0 )
    goto LABEL_92;
  inited = FveInitExtendedInfoEx((unsigned int)v55, 0, Context, -1, -1, 1);
  if ( inited < 0 )
    goto LABEL_92;
  v19 = *(_QWORD *)(Context + 120);
  v20 = v55[1] | 0x8000000LL;
  v55[1] |= 0x8000000uLL;
  *(_OWORD *)((char *)&v55[9] + 4) = FVE_GUID_PROV_SCENARIO_EPHEMERAL;
  v21 = *(_DWORD *)(v19 + 48);
  if ( (v21 & 0x100) != 0 )
    v22 = v20 | 4;
  else
    v22 = (v21 & 0x400000) != 0 ? v20 | 0x2000 : v20 | 8;
  v55[1] = v22;
  inited = FveAddVirtualizationInfoToInformation(v3, 0, 0, v55, &v52);
  if ( inited < 0 )
    goto LABEL_92;
  inited = ExUuidCreate(v3 + 5);
  if ( inited < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_98;
    }
    v11 = 17;
    goto LABEL_11;
  }
  *(_DWORD *)&v3->Data4[4] = 262148;
  *(_QWORD *)&v3[1].Data1 = *(_QWORD *)(Context + 1048);
  v23 = v52;
  *(_QWORD *)v3[1].Data4 = 0;
  *(_QWORD *)v3[3].Data4 = 0;
  *Pool2 = *v3;
  Pool2[1] = v3[1];
  Pool2[2] = v3[2];
  Pool2[3] = v3[3];
  Pool2[4] = v3[4];
  Pool2[5] = v3[5];
  Pool2[6] = v3[6];
  *(_QWORD *)(Context + 984) = v3;
  v3 = 0;
  *(_QWORD *)(Context + 1024) = v23;
  inited = FveReadWriteDeviceInit(Context);
  if ( inited < 0 )
  {
LABEL_92:
    HIDWORD(v43) = inited;
    goto LABEL_99;
  }
  if ( *(_QWORD *)(Context + 1008) || *(_QWORD *)(Context + 1016) )
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  inited = FveDatumVmkCreate(&v45);
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids,
        (unsigned int)inited);
    }
LABEL_66:
    v6 = v45;
    goto LABEL_98;
  }
  inited = FveCreateNewFvek(v24, v47);
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        19,
        WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids,
        (unsigned int)inited);
    }
    v4 = *(_QWORD *)v47;
    goto LABEL_66;
  }
  v4 = *(_QWORD *)v47;
  inited = FveFvekDataFromFvekDatum(*(_DWORD *)(Context + 1308), v47[0]);
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        20,
        WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids,
        (unsigned int)inited);
    }
    v5 = v46;
    goto LABEL_66;
  }
  v6 = v45;
  v25 = v45;
  *(_WORD *)(*(_QWORD *)(Context + 984) + 100LL) = -32763;
  v26 = *(_QWORD *)(Context + 984);
  v48 = MEMORY[0xFFFFF78000000014];
  v49 = *(_DWORD *)(v26 + 96);
  inited = FveDatasetVmkStoreFvek(&v48, v26 + 64, v25, v4);
  if ( inited < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids,
        (unsigned int)inited);
    }
    v5 = v46;
    goto LABEL_98;
  }
  v27 = v49;
  *(_DWORD *)(*(_QWORD *)(Context + 984) + 96LL) = v49;
  FveRundownAllReadsAndWrites(Context);
  v28 = v53[1];
  v29 = v6;
  v30 = v46;
  v6 = 0;
  v31 = *(_QWORD *)(Context + 984);
  *(_QWORD *)(Context + 992) = v48;
  *(_OWORD *)(Context + 1056) = v53[0];
  *(_QWORD *)(Context + 976) = Pool2;
  Pool2 = 0;
  v32 = v53[2];
  *(_OWORD *)(Context + 1072) = v28;
  *(_QWORD *)(Context + 1008) = v30;
  v33 = v53[3];
  v34 = *(_QWORD *)(Context + 1048);
  *(_OWORD *)(Context + 1088) = v32;
  *(_QWORD *)(Context + 1176) = 0;
  *(_QWORD *)&v32 = *(_QWORD *)&v53[4];
  *(_QWORD *)(Context + 1192) = 0;
  *(_DWORD *)(Context + 1200) = 0;
  *(_OWORD *)(Context + 1104) = v33;
  *(_DWORD *)(Context + 1000) = v27;
  *(_QWORD *)(Context + 1120) = v32;
  *(_QWORD *)(Context + 1016) = v29;
  *(_QWORD *)(Context + 1040) = v34;
  inited = UpdateDynamicContext(Context, v29, v31 + 64);
  if ( inited < 0 )
  {
    v39 = 1;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_98;
    }
    v11 = 22;
LABEL_11:
    WPP_SF_d(v10->AttachedDevice, v11, WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids, (unsigned int)inited);
LABEL_98:
    HIDWORD(v43) = inited;
    goto LABEL_99;
  }
  LOBYTE(BugCheckParameter4) = 1;
  SetFveStateEx(Context, 1, *(_QWORD *)(Context + 1040), 0, BugCheckParameter4, 62);
  FveResumeAllReadsAndWrites(Context);
  _InterlockedDecrement((volatile signed __int32 *)(Context + 880));
  v39 = 0;
  v40 = 0;
  FveRaiseStatusChangedEvent(Context, 1);
  FveRaiseStatusChangedEvent(Context, 13);
  v41 = 0;
  HIDWORD(v43) = inited;
  v35 = FVE_EPHEMERAL_VOLUME_INIT_SUCCEEDED;
LABEL_100:
  v36 = *(_QWORD *)Context;
  LOBYTE(v7) = 1;
  *(_QWORD *)&v43 = v35;
  v44 = 0;
  FveLogEventEx(v36, &v43, 0, v7);
  if ( v39 )
    FveResumeAllReadsAndWrites(Context);
  if ( v41 )
    FveCleanup((PVOID)Context);
  if ( v42 )
    FvepReleaseDevFveLock(v54);
  if ( v40 )
    _InterlockedDecrement((volatile signed __int32 *)(Context + 880));
  if ( v3 )
    ExFreePoolWithTag(v3, 0x30455646u);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x30455646u);
  if ( v4 )
    FveDatumFree(v4);
  if ( v5 )
    DeleteKey(v5);
  if ( v6 )
    FveDatumFree(v6);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      23,
      WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids,
      (unsigned int)inited);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1400ccd18  push    rbp
0x1400ccd1a  push    rbx
0x1400ccd1b  push    rsi
0x1400ccd1c  push    rdi
0x1400ccd1d  push    r12
0x1400ccd1f  push    r13
0x1400ccd21  push    r14
0x1400ccd23  push    r15
0x1400ccd25  lea     rbp, [rsp-0F8h]
0x1400ccd2d  sub     rsp, 1F8h
0x1400ccd34  mov     rax, cs:__security_cookie
0x1400ccd3b  xor     rax, rsp
0x1400ccd3e  mov     [rbp+130h+var_50], rax
0x1400ccd45  xor     ebx, ebx
0x1400ccd47  mov     rdi, rcx
0x1400ccd4a  xor     edx, edx; Val
0x1400ccd4c  mov     [rbp+130h+var_1A8], rbx
0x1400ccd50  lea     rcx, [rbp+130h+var_B0]; void *
0x1400ccd57  mov     [rsp+230h+var_1EF], bl
0x1400ccd5b  mov     r13d, ebx
0x1400ccd5e  mov     r14d, ebx
0x1400ccd61  lea     r8d, [rbx+5Ch]; Size
0x1400ccd65  call    memset
0x1400ccd6a  xor     edx, edx; Val
0x1400ccd6c  mov     [rbp+130h+var_198], rbx
0x1400ccd70  mov     r8d, 90h; Size
0x1400ccd76  mov     [rsp+230h+var_1F0], bl
0x1400ccd7a  lea     rcx, [rbp+130h+var_140]; void *
0x1400ccd7e  mov     qword ptr [rsp+230h+var_1C0], rbx
0x1400ccd83  mov     r12d, ebx
0x1400ccd86  mov     [rbp+130h+var_1A0], rbx
0x1400ccd8a  mov     esi, ebx
0x1400ccd8c  mov     [rsp+230h+var_1C8], rbx
0x1400ccd91  mov     r15d, ebx
0x1400ccd94  mov     [rsp+230h+var_1D0], rbx
0x1400ccd99  call    memset
0x1400ccd9e  xor     edx, edx; Val
0x1400ccda0  mov     [rsp+230h+var_1ED], bl
0x1400ccda4  lea     r8d, [rbx+48h]; Size
0x1400ccda8  mov     [rsp+230h+var_1EE], 1
0x1400ccdad  lea     rcx, [rbp+130h+var_190]; void *
0x1400ccdb1  call    memset
0x1400ccdb6  xorps   xmm0, xmm0
0x1400ccdb9  xor     eax, eax
0x1400ccdbb  movups  [rsp+230h+var_1E8], xmm0
0x1400ccdc0  mov     [rsp+230h+var_1D8], rax
0x1400ccdc5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ccdcc  lea     rdx, WPP_GLOBAL_Control
0x1400ccdd3  cmp     rcx, rdx
0x1400ccdd6  jz      short loc_1400CCE01
0x1400ccdd8  test    dword ptr [rcx+2Ch], 200000h
0x1400ccddf  jz      short loc_1400CCE01
0x1400ccde1  cmp     byte ptr [rcx+29h], 5
0x1400ccde5  jb      short loc_1400CCE01
0x1400ccde7  mov     rcx, [rcx+18h]
0x1400ccdeb  lea     edx, [rbx+0Ah]
0x1400ccdee  lea     r8, WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids
0x1400ccdf5  call    WPP_SF_
0x1400ccdfa  lea     rdx, WPP_GLOBAL_Control
0x1400cce01  mov     rcx, [rdi+8]
0x1400cce05  test    byte ptr [rcx+2960h], 1
0x1400cce0c  jnz     short loc_1400CCE63
0x1400cce0e  test    dword ptr [rcx+26C8h], 100000h
0x1400cce18  jnz     short loc_1400CCE63
0x1400cce1a  mov     ebx, 0C00000BBh
0x1400cce1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cce26  cmp     rcx, rdx
0x1400cce29  jz      loc_1400CD5DB
0x1400cce2f  test    dword ptr [rcx+2Ch], 200000h
0x1400cce36  jz      loc_1400CD5DB
0x1400cce3c  cmp     byte ptr [rcx+29h], 2
0x1400cce40  jb      loc_1400CD5DB
0x1400cce46  mov     edx, 0Bh
0x1400cce4b  mov     rcx, [rcx+18h]
0x1400cce4f  lea     r8, WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids
0x1400cce56  mov     r9d, ebx
0x1400cce59  call    WPP_SF_d
0x1400cce5e  jmp     loc_1400CD5DB
0x1400cce63  test    byte ptr [rdi+1143h], 8
0x1400cce6a  jz      short loc_1400CCE7F
0x1400cce6c  mov     r9d, 3Fh ; '?'
0x1400cce72  xor     r8d, r8d
0x1400cce75  xor     edx, edx
0x1400cce77  mov     rcx, rdi; Context
0x1400cce7a  call    FveCleanup
0x1400cce7f  or      byte ptr [rdi+1143h], 8
0x1400cce86  mov     rcx, rdi
0x1400cce89  call    FveLockDriver
0x1400cce8e  mov     rcx, rdi
0x1400cce91  call    FveWorkerInit
0x1400cce96  mov     ebx, eax
0x1400cce98  test    eax, eax
0x1400cce9a  jns     short loc_1400CCED4
0x1400cce9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ccea3  lea     rax, WPP_GLOBAL_Control
0x1400cceaa  cmp     rcx, rax
0x1400ccead  jz      loc_1400CD5DB
0x1400cceb3  test    dword ptr [rcx+2Ch], 200000h
0x1400cceba  jz      loc_1400CD5DB
0x1400ccec0  cmp     byte ptr [rcx+29h], 2
0x1400ccec4  jb      loc_1400CD5DB
0x1400cceca  mov     edx, 0Ch
0x1400ccecf  jmp     loc_1400CCE4B
0x1400cced4  mov     edx, 70h ; 'p'
0x1400cced9  mov     r8d, 30455646h
0x1400ccedf  lea     ecx, [rdx-30h]
0x1400ccee2  call    cs:__imp_ExAllocatePool2
0x1400ccee9  nop     dword ptr [rax+rax+00h]
0x1400cceee  mov     r13, rax
0x1400ccef1  test    rax, rax
0x1400ccef4  jnz     short loc_1400CCF43
0x1400ccef6  mov     esi, 0C000009Ah
0x1400ccefb  mov     ebx, esi
0x1400ccefd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ccf04  lea     rax, WPP_GLOBAL_Control
0x1400ccf0b  cmp     rcx, rax
0x1400ccf0e  jz      short loc_1400CCF36
0x1400ccf10  test    dword ptr [rcx+2Ch], 200000h
0x1400ccf17  jz      short loc_1400CCF36
0x1400ccf19  cmp     byte ptr [rcx+29h], 2
0x1400ccf1d  jb      short loc_1400CCF36
0x1400ccf1f  lea     edx, [r13+0Dh]
0x1400ccf23  mov     rcx, [rcx+18h]
0x1400ccf27  lea     r8, WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids
0x1400ccf2e  mov     r9d, esi
0x1400ccf31  call    WPP_SF_d
0x1400ccf36  mov     dword ptr [rsp+230h+var_1E8+0Ch], esi
0x1400ccf3a  mov     rsi, [rbp+130h+var_1A0]
0x1400ccf3e  jmp     loc_1400CD5DF
0x1400ccf43  mov     rcx, [rdi+70h]; DeviceObject
0x1400ccf47  lea     rax, [rsp+230h+var_1B8]
0x1400ccf4c  mov     [rsp+230h+var_1F8], rax; __int64
0x1400ccf51  xor     r9d, r9d
0x1400ccf54  lea     rax, [rbp+130h+var_1A8]
0x1400ccf58  mov     [rsp+230h+var_200], 8; int
0x1400ccf60  mov     [rsp+230h+var_208], rax; __int64
0x1400ccf65  xor     r8d, r8d
0x1400ccf68  mov     edx, 7405Ch
0x1400ccf6d  mov     dword ptr [rsp+230h+BugCheckParameter4], esi; int
0x1400ccf71  call    FveDeviceControlSynchronousEx
0x1400ccf76  xor     edx, edx
0x1400ccf78  mov     ebx, eax
0x1400ccf7a  test    eax, eax
0x1400ccf7c  jns     short loc_1400CCFB6
0x1400ccf7e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ccf85  lea     rax, WPP_GLOBAL_Control
0x1400ccf8c  cmp     rcx, rax
0x1400ccf8f  jz      loc_1400CD5DB
0x1400ccf95  test    dword ptr [rcx+2Ch], 200000h
0x1400ccf9c  jz      loc_1400CD5DB
0x1400ccfa2  cmp     byte ptr [rcx+29h], 2
0x1400ccfa6  jb      loc_1400CD5DB
0x1400ccfac  mov     edx, 0Eh
0x1400ccfb1  jmp     loc_1400CCE4B
0x1400ccfb6  mov     r9, [rbp+130h+var_1A8]
0x1400ccfba  test    r9, r9
0x1400ccfbd  js      loc_1400CD590
0x1400ccfc3  mov     [rdi+418h], r9
0x1400ccfca  mov     rcx, rdx
0x1400ccfcd  mov     rax, rdx
0x1400ccfd0  inc     rcx
0x1400ccfd3  mov     qword ptr [rbp+rax+130h+var_190], rdx
0x1400ccfd8  mov     dword ptr [rbp+rax+130h+var_190+8], edx
0x1400ccfdc  mov     word ptr [rbp+rax+130h+var_190+0Ch], dx
0x1400ccfe1  mov     qword ptr [rbp+rax+130h+var_180], rdx
0x1400ccfe6  lea     rax, [rax+18h]
0x1400ccfea  cmp     rcx, 3
0x1400ccfee  jnz     short loc_1400CCFD0
0x1400ccff0  mov     dword ptr [rdi+520h], 1
0x1400ccffa  lock inc dword ptr [rdi+370h]
0x1400cd001  mov     rcx, rdi; Context
0x1400cd004  mov     [rsp+230h+var_1EF], 1
0x1400cd009  call    FveRegisterPnpNotifications
0x1400cd00e  mov     ebx, eax
0x1400cd010  test    eax, eax
0x1400cd012  js      loc_1400CD57F
0x1400cd018  mov     ecx, [rdi+51Ch]
0x1400cd01e  lea     eax, [rcx-1]
0x1400cd021  test    ecx, eax
0x1400cd023  jnz     short loc_1400CD037
0x1400cd025  test    ecx, ecx
0x1400cd027  jz      short loc_1400CD037
0x1400cd029  lea     r8d, [rcx+0FFFFh]
0x1400cd030  not     eax
0x1400cd032  and     r8d, eax
0x1400cd035  jmp     short loc_1400CD04D
0x1400cd037  xor     edx, edx
0x1400cd039  mov     r8d, 10000h
0x1400cd03f  mov     eax, r8d
0x1400cd042  div     ecx
0x1400cd044  test    edx, edx
0x1400cd046  jz      short loc_1400CD04D
0x1400cd048  sub     ecx, edx
0x1400cd04a  add     r8d, ecx
0x1400cd04d  mov     ebx, r8d
0x1400cd050  mov     ecx, 100h
0x1400cd055  mov     edx, ebx
0x1400cd057  mov     r8d, 30455646h
0x1400cd05d  call    cs:__imp_ExAllocatePool2
0x1400cd064  nop     dword ptr [rax+rax+00h]
0x1400cd069  mov     r14, rax
0x1400cd06c  test    rax, rax
0x1400cd06f  jnz     short loc_1400CD0AF
0x1400cd071  mov     esi, 0C000009Ah
0x1400cd076  mov     ebx, esi
0x1400cd078  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd07f  lea     rax, WPP_GLOBAL_Control
0x1400cd086  cmp     rcx, rax
0x1400cd089  jz      loc_1400CCF36
0x1400cd08f  test    dword ptr [rcx+2Ch], 200000h
0x1400cd096  jz      loc_1400CCF36
0x1400cd09c  cmp     byte ptr [rcx+29h], 2
0x1400cd0a0  jb      loc_1400CCF36
0x1400cd0a6  lea     edx, [r14+10h]
0x1400cd0aa  jmp     loc_1400CCF23
0x1400cd0af  mov     r8b, 1
0x1400cd0b2  lea     rdx, [rbp+130h+var_140]
0x1400cd0b6  mov     rcx, rdi
0x1400cd0b9  call    FvepAcquireDevFveLock
0x1400cd0be  xor     r9d, r9d
0x1400cd0c1  mov     [rsp+230h+var_1ED], 1
0x1400cd0c6  mov     rdx, rbx
0x1400cd0c9  mov     rcx, r14; void *
0x1400cd0cc  call    FveInformationCreate
0x1400cd0d1  mov     ebx, eax
0x1400cd0d3  test    eax, eax
0x1400cd0d5  js      loc_1400CD57F
0x1400cd0db  mov     byte ptr [rsp+230h+var_208], 1
0x1400cd0e0  lea     rcx, [rbp+130h+var_B0]
0x1400cd0e7  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400cd0eb  mov     dword ptr [rsp+230h+BugCheckParameter4], 0FFFFFFFFh
0x1400cd0f3  mov     r8, rdi
0x1400cd0f6  xor     edx, edx
0x1400cd0f8  call    FveInitExtendedInfoEx
0x1400cd0fd  mov     ebx, eax
0x1400cd0ff  test    eax, eax
0x1400cd101  js      loc_1400CD57F
0x1400cd107  mov     rcx, [rbp+130h+var_A8]
0x1400cd10e  movups  xmm0, cs:FVE_GUID_PROV_SCENARIO_EPHEMERAL
0x1400cd115  mov     rax, [rdi+78h]
0x1400cd119  bts     rcx, 1Bh
0x1400cd11e  mov     [rbp+130h+var_A8], rcx
0x1400cd125  movdqu  [rbp+130h+var_64], xmm0
0x1400cd12d  mov     edx, [rax+30h]
0x1400cd130  bt      edx, 8
0x1400cd134  jnb     short loc_1400CD13C
0x1400cd136  or      rcx, 4
0x1400cd13a  jmp     short loc_1400CD14D
0x1400cd13c  bt      edx, 16h
0x1400cd140  jnb     short loc_1400CD149
0x1400cd142  bts     rcx, 0Dh
0x1400cd147  jmp     short loc_1400CD14D
0x1400cd149  or      rcx, 8
0x1400cd14d  mov     [rbp+130h+var_A8], rcx
0x1400cd154  lea     rax, [rbp+130h+var_198]
0x1400cd158  mov     rcx, r14
0x1400cd15b  mov     [rsp+230h+BugCheckParameter4], rax
0x1400cd160  lea     r9, [rbp+130h+var_B0]
0x1400cd167  xor     r8d, r8d
0x1400cd16a  xor     edx, edx
0x1400cd16c  call    FveAddVirtualizationInfoToInformation
0x1400cd171  mov     ebx, eax
0x1400cd173  test    eax, eax
0x1400cd175  js      loc_1400CD57F
0x1400cd17b  lea     rcx, [r14+50h]; Uuid
0x1400cd17f  call    cs:__imp_ExUuidCreate
0x1400cd186  nop     dword ptr [rax+rax+00h]
0x1400cd18b  mov     ebx, eax
0x1400cd18d  test    eax, eax
0x1400cd18f  jns     short loc_1400CD1C9
0x1400cd191  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cd198  lea     rax, WPP_GLOBAL_Control
0x1400cd19f  cmp     rcx, rax
0x1400cd1a2  jz      loc_1400CD5DB
0x1400cd1a8  test    dword ptr [rcx+2Ch], 200000h
0x1400cd1af  jz      loc_1400CD5DB
0x1400cd1b5  cmp     byte ptr [rcx+29h], 2
0x1400cd1b9  jb      loc_1400CD5DB
0x1400cd1bf  mov     edx, 11h
0x1400cd1c4  jmp     loc_1400CCE4B
0x1400cd1c9  mov     dword ptr [r14+0Ch], 40004h
0x1400cd1d1  mov     rcx, rdi
0x1400cd1d4  mov     rax, [rdi+418h]
0x1400cd1db  mov     [r14+10h], rax
0x1400cd1df  mov     rax, [rbp+130h+var_198]
0x1400cd1e3  mov     [r14+18h], rsi
0x1400cd1e7  mov     [r14+38h], rsi
0x1400cd1eb  movups  xmm0, xmmword ptr [r14]
0x1400cd1ef  movups  xmmword ptr [r13+0], xmm0
0x1400cd1f4  movups  xmm1, xmmword ptr [r14+10h]
0x1400cd1f9  movups  xmmword ptr [r13+10h], xmm1
0x1400cd1fe  movups  xmm0, xmmword ptr [r14+20h]
0x1400cd203  movups  xmmword ptr [r13+20h], xmm0
0x1400cd208  movups  xmm1, xmmword ptr [r14+30h]
0x1400cd20d  movups  xmmword ptr [r13+30h], xmm1
0x1400cd212  movups  xmm0, xmmword ptr [r14+40h]
0x1400cd217  movups  xmmword ptr [r13+40h], xmm0
0x1400cd21c  movups  xmm1, xmmword ptr [r14+50h]
0x1400cd221  movups  xmmword ptr [r13+50h], xmm1
0x1400cd226  movups  xmm0, xmmword ptr [r14+60h]
  ... truncated ...
```
