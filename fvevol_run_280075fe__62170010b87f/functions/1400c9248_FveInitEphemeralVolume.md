# FveInitEphemeralVolume

- ea: `0x1400c9248`
- end: `0x1400c9c37`
- name: `FveInitEphemeralVolume`
- size: `2543`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `29`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400a8530`

## callees

- `0x140005e50`
- `0x140008dc0`
- `0x140008e44`
- `0x14000ba88`
- `0x140012354`
- `0x140013804`
- `0x14001447c`
- `0x140016e44`
- `0x1400218c0`
- `0x140021d00`
- `0x140023a64`
- `0x1400241b4`
- `0x14002e334`
- `0x1400617a8`
- `0x140061b54`
- `0x1400624c8`
- `0x140063304`
- `0x140095190`
- `0x1400b5c18`
- `0x1400bb39c`
- `0x1400c9248`
- `0x1400da590`
- `0x1400da8d4`
- `0x1400daad0`
- `0x1400def70`
- `0x1400e39d8`
- `0x1400e3eec`
- `0x1400e43d8`
- `0x1400e9244`

## import_xrefs

- `ntoskrnl!ExUuidCreate` at `0x1400c96af`
- `ntoskrnl!ExUuidCreate` at `0x1400c96af`
- `ntoskrnl!KeBugCheckEx` at `0x1400c9aa2`
- `ntoskrnl!KeBugCheckEx` at `0x1400c9aa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9b8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9ba4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9b8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c9ba4`
- `ntoskrnl!ExAllocatePool2` at `0x1400c9412`
- `ntoskrnl!ExAllocatePool2` at `0x1400c958d`
- `ntoskrnl!ExAllocatePool2` at `0x1400c9412`
- `ntoskrnl!ExAllocatePool2` at `0x1400c958d`

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
  if ( (*(_BYTE *)(v8 + 10344) & 1) == 0 && (*(_DWORD *)(v8 + 9680) & 0x100000) == 0 )
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
  if ( (*(_BYTE *)(Context + 4403) & 8) != 0 )
    FveCleanup((PVOID)Context);
  *(_BYTE *)(Context + 4403) |= 8u;
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
0x1400c9248  push    rbp
0x1400c924a  push    rbx
0x1400c924b  push    rsi
0x1400c924c  push    rdi
0x1400c924d  push    r12
0x1400c924f  push    r13
0x1400c9251  push    r14
0x1400c9253  push    r15
0x1400c9255  lea     rbp, [rsp-0F8h]
0x1400c925d  sub     rsp, 1F8h
0x1400c9264  mov     rax, cs:__security_cookie
0x1400c926b  xor     rax, rsp
0x1400c926e  mov     [rbp+130h+var_50], rax
0x1400c9275  xor     ebx, ebx
0x1400c9277  mov     rdi, rcx
0x1400c927a  xor     edx, edx; Val
0x1400c927c  mov     [rbp+130h+var_1A8], rbx
0x1400c9280  lea     rcx, [rbp+130h+var_B0]; void *
0x1400c9287  mov     [rsp+230h+var_1EF], bl
0x1400c928b  mov     r13d, ebx
0x1400c928e  mov     r14d, ebx
0x1400c9291  lea     r8d, [rbx+5Ch]; Size
0x1400c9295  call    memset
0x1400c929a  xor     edx, edx; Val
0x1400c929c  mov     [rbp+130h+var_198], rbx
0x1400c92a0  mov     r8d, 90h; Size
0x1400c92a6  mov     [rsp+230h+var_1F0], bl
0x1400c92aa  lea     rcx, [rbp+130h+var_140]; void *
0x1400c92ae  mov     qword ptr [rsp+230h+var_1C0], rbx
0x1400c92b3  mov     r12d, ebx
0x1400c92b6  mov     [rbp+130h+var_1A0], rbx
0x1400c92ba  mov     esi, ebx
0x1400c92bc  mov     [rsp+230h+var_1C8], rbx
0x1400c92c1  mov     r15d, ebx
0x1400c92c4  mov     [rsp+230h+var_1D0], rbx
0x1400c92c9  call    memset
0x1400c92ce  xor     edx, edx; Val
0x1400c92d0  mov     [rsp+230h+var_1ED], bl
0x1400c92d4  lea     r8d, [rbx+48h]; Size
0x1400c92d8  mov     [rsp+230h+var_1EE], 1
0x1400c92dd  lea     rcx, [rbp+130h+var_190]; void *
0x1400c92e1  call    memset
0x1400c92e6  xorps   xmm0, xmm0
0x1400c92e9  xor     eax, eax
0x1400c92eb  movups  [rsp+230h+var_1E8], xmm0
0x1400c92f0  mov     [rsp+230h+var_1D8], rax
0x1400c92f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c92fc  lea     rdx, WPP_GLOBAL_Control
0x1400c9303  cmp     rcx, rdx
0x1400c9306  jz      short loc_1400C9331
0x1400c9308  test    dword ptr [rcx+2Ch], 200000h
0x1400c930f  jz      short loc_1400C9331
0x1400c9311  cmp     byte ptr [rcx+29h], 5
0x1400c9315  jb      short loc_1400C9331
0x1400c9317  mov     rcx, [rcx+18h]
0x1400c931b  lea     edx, [rbx+0Ah]
0x1400c931e  lea     r8, WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids
0x1400c9325  call    WPP_SF_
0x1400c932a  lea     rdx, WPP_GLOBAL_Control
0x1400c9331  mov     rcx, [rdi+8]
0x1400c9335  test    byte ptr [rcx+2868h], 1
0x1400c933c  jnz     short loc_1400C9393
0x1400c933e  test    dword ptr [rcx+25D0h], 100000h
0x1400c9348  jnz     short loc_1400C9393
0x1400c934a  mov     ebx, 0C00000BBh
0x1400c934f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9356  cmp     rcx, rdx
0x1400c9359  jz      loc_1400C9B0B
0x1400c935f  test    dword ptr [rcx+2Ch], 200000h
0x1400c9366  jz      loc_1400C9B0B
0x1400c936c  cmp     byte ptr [rcx+29h], 2
0x1400c9370  jb      loc_1400C9B0B
0x1400c9376  mov     edx, 0Bh
0x1400c937b  mov     rcx, [rcx+18h]
0x1400c937f  lea     r8, WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids
0x1400c9386  mov     r9d, ebx
0x1400c9389  call    WPP_SF_d
0x1400c938e  jmp     loc_1400C9B0B
0x1400c9393  test    byte ptr [rdi+1133h], 8
0x1400c939a  jz      short loc_1400C93AF
0x1400c939c  mov     r9d, 3Fh ; '?'
0x1400c93a2  xor     r8d, r8d
0x1400c93a5  xor     edx, edx
0x1400c93a7  mov     rcx, rdi; Context
0x1400c93aa  call    FveCleanup
0x1400c93af  or      byte ptr [rdi+1133h], 8
0x1400c93b6  mov     rcx, rdi
0x1400c93b9  call    FveLockDriver
0x1400c93be  mov     rcx, rdi
0x1400c93c1  call    FveWorkerInit
0x1400c93c6  mov     ebx, eax
0x1400c93c8  test    eax, eax
0x1400c93ca  jns     short loc_1400C9404
0x1400c93cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c93d3  lea     rax, WPP_GLOBAL_Control
0x1400c93da  cmp     rcx, rax
0x1400c93dd  jz      loc_1400C9B0B
0x1400c93e3  test    dword ptr [rcx+2Ch], 200000h
0x1400c93ea  jz      loc_1400C9B0B
0x1400c93f0  cmp     byte ptr [rcx+29h], 2
0x1400c93f4  jb      loc_1400C9B0B
0x1400c93fa  mov     edx, 0Ch
0x1400c93ff  jmp     loc_1400C937B
0x1400c9404  mov     edx, 70h ; 'p'
0x1400c9409  mov     r8d, 30455646h
0x1400c940f  lea     ecx, [rdx-30h]
0x1400c9412  call    cs:__imp_ExAllocatePool2
0x1400c9419  nop     dword ptr [rax+rax+00h]
0x1400c941e  mov     r13, rax
0x1400c9421  test    rax, rax
0x1400c9424  jnz     short loc_1400C9473
0x1400c9426  mov     esi, 0C000009Ah
0x1400c942b  mov     ebx, esi
0x1400c942d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c9434  lea     rax, WPP_GLOBAL_Control
0x1400c943b  cmp     rcx, rax
0x1400c943e  jz      short loc_1400C9466
0x1400c9440  test    dword ptr [rcx+2Ch], 200000h
0x1400c9447  jz      short loc_1400C9466
0x1400c9449  cmp     byte ptr [rcx+29h], 2
0x1400c944d  jb      short loc_1400C9466
0x1400c944f  lea     edx, [r13+0Dh]
0x1400c9453  mov     rcx, [rcx+18h]
0x1400c9457  lea     r8, WPP_80c2fdb01bc33c51d6eb389ac93617fc_Traceguids
0x1400c945e  mov     r9d, esi
0x1400c9461  call    WPP_SF_d
0x1400c9466  mov     dword ptr [rsp+230h+var_1E8+0Ch], esi
0x1400c946a  mov     rsi, [rbp+130h+var_1A0]
0x1400c946e  jmp     loc_1400C9B0F
0x1400c9473  mov     rcx, [rdi+70h]; DeviceObject
0x1400c9477  lea     rax, [rsp+230h+var_1B8]
0x1400c947c  mov     [rsp+230h+var_1F8], rax; __int64
0x1400c9481  xor     r9d, r9d
0x1400c9484  lea     rax, [rbp+130h+var_1A8]
0x1400c9488  mov     [rsp+230h+var_200], 8; int
0x1400c9490  mov     [rsp+230h+var_208], rax; __int64
0x1400c9495  xor     r8d, r8d
0x1400c9498  mov     edx, 7405Ch
0x1400c949d  mov     dword ptr [rsp+230h+BugCheckParameter4], esi; int
0x1400c94a1  call    FveDeviceControlSynchronousEx
0x1400c94a6  xor     edx, edx
0x1400c94a8  mov     ebx, eax
0x1400c94aa  test    eax, eax
0x1400c94ac  jns     short loc_1400C94E6
0x1400c94ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c94b5  lea     rax, WPP_GLOBAL_Control
0x1400c94bc  cmp     rcx, rax
0x1400c94bf  jz      loc_1400C9B0B
0x1400c94c5  test    dword ptr [rcx+2Ch], 200000h
0x1400c94cc  jz      loc_1400C9B0B
0x1400c94d2  cmp     byte ptr [rcx+29h], 2
0x1400c94d6  jb      loc_1400C9B0B
0x1400c94dc  mov     edx, 0Eh
0x1400c94e1  jmp     loc_1400C937B
0x1400c94e6  mov     r9, [rbp+130h+var_1A8]
0x1400c94ea  test    r9, r9
0x1400c94ed  js      loc_1400C9AC0
0x1400c94f3  mov     [rdi+418h], r9
0x1400c94fa  mov     rcx, rdx
0x1400c94fd  mov     rax, rdx
0x1400c9500  inc     rcx
0x1400c9503  mov     qword ptr [rbp+rax+130h+var_190], rdx
0x1400c9508  mov     dword ptr [rbp+rax+130h+var_190+8], edx
0x1400c950c  mov     word ptr [rbp+rax+130h+var_190+0Ch], dx
0x1400c9511  mov     qword ptr [rbp+rax+130h+var_180], rdx
0x1400c9516  lea     rax, [rax+18h]
0x1400c951a  cmp     rcx, 3
0x1400c951e  jnz     short loc_1400C9500
0x1400c9520  mov     dword ptr [rdi+520h], 1
0x1400c952a  lock inc dword ptr [rdi+370h]
0x1400c9531  mov     rcx, rdi; Context
0x1400c9534  mov     [rsp+230h+var_1EF], 1
0x1400c9539  call    FveRegisterPnpNotifications
0x1400c953e  mov     ebx, eax
0x1400c9540  test    eax, eax
0x1400c9542  js      loc_1400C9AAF
0x1400c9548  mov     ecx, [rdi+51Ch]
0x1400c954e  lea     eax, [rcx-1]
0x1400c9551  test    ecx, eax
0x1400c9553  jnz     short loc_1400C9567
0x1400c9555  test    ecx, ecx
0x1400c9557  jz      short loc_1400C9567
0x1400c9559  lea     r8d, [rcx+0FFFFh]
0x1400c9560  not     eax
0x1400c9562  and     r8d, eax
0x1400c9565  jmp     short loc_1400C957D
0x1400c9567  xor     edx, edx
0x1400c9569  mov     r8d, 10000h
0x1400c956f  mov     eax, r8d
0x1400c9572  div     ecx
0x1400c9574  test    edx, edx
0x1400c9576  jz      short loc_1400C957D
0x1400c9578  sub     ecx, edx
0x1400c957a  add     r8d, ecx
0x1400c957d  mov     ebx, r8d
0x1400c9580  mov     ecx, 100h
0x1400c9585  mov     edx, ebx
0x1400c9587  mov     r8d, 30455646h
0x1400c958d  call    cs:__imp_ExAllocatePool2
0x1400c9594  nop     dword ptr [rax+rax+00h]
0x1400c9599  mov     r14, rax
0x1400c959c  test    rax, rax
0x1400c959f  jnz     short loc_1400C95DF
0x1400c95a1  mov     esi, 0C000009Ah
0x1400c95a6  mov     ebx, esi
0x1400c95a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c95af  lea     rax, WPP_GLOBAL_Control
0x1400c95b6  cmp     rcx, rax
0x1400c95b9  jz      loc_1400C9466
0x1400c95bf  test    dword ptr [rcx+2Ch], 200000h
0x1400c95c6  jz      loc_1400C9466
0x1400c95cc  cmp     byte ptr [rcx+29h], 2
0x1400c95d0  jb      loc_1400C9466
0x1400c95d6  lea     edx, [r14+10h]
0x1400c95da  jmp     loc_1400C9453
0x1400c95df  mov     r8b, 1
0x1400c95e2  lea     rdx, [rbp+130h+var_140]
0x1400c95e6  mov     rcx, rdi
0x1400c95e9  call    FvepAcquireDevFveLock
0x1400c95ee  xor     r9d, r9d
0x1400c95f1  mov     [rsp+230h+var_1ED], 1
0x1400c95f6  mov     rdx, rbx
0x1400c95f9  mov     rcx, r14; void *
0x1400c95fc  call    FveInformationCreate
0x1400c9601  mov     ebx, eax
0x1400c9603  test    eax, eax
0x1400c9605  js      loc_1400C9AAF
0x1400c960b  mov     byte ptr [rsp+230h+var_208], 1
0x1400c9610  lea     rcx, [rbp+130h+var_B0]
0x1400c9617  or      r9, 0FFFFFFFFFFFFFFFFh
0x1400c961b  mov     dword ptr [rsp+230h+BugCheckParameter4], 0FFFFFFFFh
0x1400c9623  mov     r8, rdi
0x1400c9626  xor     edx, edx
0x1400c9628  call    FveInitExtendedInfoEx
0x1400c962d  mov     ebx, eax
0x1400c962f  test    eax, eax
0x1400c9631  js      loc_1400C9AAF
0x1400c9637  mov     rcx, [rbp+130h+var_A8]
0x1400c963e  movups  xmm0, cs:FVE_GUID_PROV_SCENARIO_EPHEMERAL
0x1400c9645  mov     rax, [rdi+78h]
0x1400c9649  bts     rcx, 1Bh
0x1400c964e  mov     [rbp+130h+var_A8], rcx
0x1400c9655  movdqu  [rbp+130h+var_64], xmm0
0x1400c965d  mov     edx, [rax+30h]
0x1400c9660  bt      edx, 8
0x1400c9664  jnb     short loc_1400C966C
0x1400c9666  or      rcx, 4
0x1400c966a  jmp     short loc_1400C967D
0x1400c966c  bt      edx, 16h
0x1400c9670  jnb     short loc_1400C9679
0x1400c9672  bts     rcx, 0Dh
0x1400c9677  jmp     short loc_1400C967D
0x1400c9679  or      rcx, 8
0x1400c967d  mov     [rbp+130h+var_A8], rcx
0x1400c9684  lea     rax, [rbp+130h+var_198]
0x1400c9688  mov     rcx, r14
0x1400c968b  mov     [rsp+230h+BugCheckParameter4], rax
0x1400c9690  lea     r9, [rbp+130h+var_B0]
0x1400c9697  xor     r8d, r8d
0x1400c969a  xor     edx, edx
0x1400c969c  call    FveAddVirtualizationInfoToInformation
0x1400c96a1  mov     ebx, eax
0x1400c96a3  test    eax, eax
0x1400c96a5  js      loc_1400C9AAF
0x1400c96ab  lea     rcx, [r14+50h]; Uuid
0x1400c96af  call    cs:__imp_ExUuidCreate
0x1400c96b6  nop     dword ptr [rax+rax+00h]
0x1400c96bb  mov     ebx, eax
0x1400c96bd  test    eax, eax
0x1400c96bf  jns     short loc_1400C96F9
0x1400c96c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c96c8  lea     rax, WPP_GLOBAL_Control
0x1400c96cf  cmp     rcx, rax
0x1400c96d2  jz      loc_1400C9B0B
0x1400c96d8  test    dword ptr [rcx+2Ch], 200000h
0x1400c96df  jz      loc_1400C9B0B
0x1400c96e5  cmp     byte ptr [rcx+29h], 2
0x1400c96e9  jb      loc_1400C9B0B
0x1400c96ef  mov     edx, 11h
0x1400c96f4  jmp     loc_1400C937B
0x1400c96f9  mov     dword ptr [r14+0Ch], 40004h
0x1400c9701  mov     rcx, rdi
0x1400c9704  mov     rax, [rdi+418h]
0x1400c970b  mov     [r14+10h], rax
0x1400c970f  mov     rax, [rbp+130h+var_198]
0x1400c9713  mov     [r14+18h], rsi
0x1400c9717  mov     [r14+38h], rsi
0x1400c971b  movups  xmm0, xmmword ptr [r14]
0x1400c971f  movups  xmmword ptr [r13+0], xmm0
0x1400c9724  movups  xmm1, xmmword ptr [r14+10h]
0x1400c9729  movups  xmmword ptr [r13+10h], xmm1
0x1400c972e  movups  xmm0, xmmword ptr [r14+20h]
0x1400c9733  movups  xmmword ptr [r13+20h], xmm0
0x1400c9738  movups  xmm1, xmmword ptr [r14+30h]
0x1400c973d  movups  xmmword ptr [r13+30h], xmm1
0x1400c9742  movups  xmm0, xmmword ptr [r14+40h]
0x1400c9747  movups  xmmword ptr [r13+40h], xmm0
0x1400c974c  movups  xmm1, xmmword ptr [r14+50h]
0x1400c9751  movups  xmmword ptr [r13+50h], xmm1
0x1400c9756  movups  xmm0, xmmword ptr [r14+60h]
  ... truncated ...
```
