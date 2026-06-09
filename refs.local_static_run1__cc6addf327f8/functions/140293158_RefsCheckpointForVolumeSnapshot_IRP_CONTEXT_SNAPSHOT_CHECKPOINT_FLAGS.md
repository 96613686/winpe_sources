# RefsCheckpointForVolumeSnapshot(_IRP_CONTEXT *,SNAPSHOT_CHECKPOINT_FLAGS &)

- ea: `0x140293158`
- end: `0x14029355c`
- name: `?RefsCheckpointForVolumeSnapshot@@YAJPEAU_IRP_CONTEXT@@AEAUSNAPSHOT_CHECKPOINT_FLAGS@@@Z`
- size: `1028`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct SNAPSHOT_CHECKPOINT_FLAGS *)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14029d114`

## callees

- `0x140009ecc`
- `0x1400862c0`
- `0x1400cf978`
- `0x1400d0fd8`
- `0x140118e60`
- `0x1401f3fb0`
- `0x14028debc`
- `0x14028e0ec`
- `0x140293158`
- `0x1402d55a4`
- `0x1402e6700`
- `0x1402e7020`
- `0x140302eb0`
- `0x140334b60`
- `0x1403366e0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1402932fa`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402932fa`
- `ntoskrnl!ZwClose` at `0x140293549`
- `ntoskrnl!ZwClose` at `0x140345538`
- `ntoskrnl!ZwClose` at `0x140293549`
- `ntoskrnl!ZwClose` at `0x140345538`
- `ntoskrnl!ZwOpenEvent` at `0x140293349`
- `ntoskrnl!ZwOpenEvent` at `0x140293349`
- `ntoskrnl!KeSetPriorityThread` at `0x1402933b0`
- `ntoskrnl!KeSetPriorityThread` at `0x140293533`
- `ntoskrnl!KeSetPriorityThread` at `0x140345522`
- `ntoskrnl!KeSetPriorityThread` at `0x1402933b0`
- `ntoskrnl!KeSetPriorityThread` at `0x140293533`
- `ntoskrnl!KeSetPriorityThread` at `0x140345522`

## pseudocode

```c
__int64 __fastcall RefsCheckpointForVolumeSnapshot(struct _IRP_CONTEXT *a1, struct SNAPSHOT_CHECKPOINT_FLAGS *a2)
{
  KPRIORITY v4; // r12d
  char v5; // r15
  char v6; // r13
  __int64 v7; // rsi
  NTSTATUS v9; // ebx
  unsigned int v10; // r9d
  NTSTATUS v11; // eax
  int v12; // eax
  bool v13; // [rsp+40h] [rbp-118h] BYREF
  char v14; // [rsp+41h] [rbp-117h]
  NTSTATUS v15; // [rsp+44h] [rbp-114h]
  KPRIORITY v16; // [rsp+48h] [rbp-110h]
  void *EventHandle[3]; // [rsp+50h] [rbp-108h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-F0h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-E0h] BYREF
  WCHAR SourceString[56]; // [rsp+B0h] [rbp-A8h] BYREF

  EventHandle[1] = a1;
  EventHandle[2] = a2;
  v15 = 0;
  v4 = 0;
  v16 = 0;
  v5 = 0;
  v14 = 0;
  v6 = 0;
  v13 = 0;
  wcscpy(SourceString, L"\\BaseNamedObjects\\Microsoft.ReFS.LeakDetectionEvent.X");
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  EventHandle[0] = 0;
  v7 = *((_QWORD *)a1 + 8);
  *(_DWORD *)a2 = 0;
  if ( (*(_DWORD *)(v7 + 24) & 0x2000000) != 0 )
    return 0;
  RefsAcquireExclusiveVcb(a1, (struct _VCB *)v7, 1u);
  *((_BYTE *)a2 + 1) = 1;
  if ( (*(_DWORD *)(v7 + 24) & 1) == 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v9 = -1073741202;
    }
    else
    {
      v9 = -1073741202;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_ca3360bb7e82316d71ea529aa669e6e2_Traceguids, 3221226094LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_37;
    v10 = 635;
    goto LABEL_36;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 512;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = ZwOpenEvent(EventHandle, 0x1F0003u, &ObjectAttributes);
  v9 = v11;
  v15 = v11;
  if ( v11 < 0 )
  {
    if ( v11 == -1073741766 || v11 == -1073741772 )
    {
      v9 = 0;
      v15 = 0;
    }
  }
  else
  {
    v6 = 1;
  }
  if ( v9 < 0 )
    goto LABEL_38;
  if ( RefsUseFlushVolumeParallel )
    RefsFlushVolumeParallel(a1, v7, 65);
  else
    RefsFlushVolumeOriginal(a1, v7, 65);
  v4 = KeSetPriorityThread(KeGetCurrentThread(), 16);
  v16 = v4;
  if ( v4 != 16 )
    v5 = 1;
  v14 = v5;
  v9 = MsPauseAndFlushBackgroundActivity(*(CmsVolume **)(v7 + 112));
  v15 = v9;
  *((_BYTE *)a2 + 3) = 1;
  if ( v9 < 0 )
    goto LABEL_38;
  RefsAcquireAllFiles(a1, v7, 30);
  *(_BYTE *)a2 = 1;
  v12 = RefsUseFlushVolumeParallel ? RefsFlushVolumeParallel(a1, v7, 1730) : RefsFlushVolumeOriginal(a1, v7, 1730);
  v9 = v12;
  v15 = v12;
  if ( v12 < 0 )
    goto LABEL_38;
  MsDrainLWQueue(*(_QWORD *)(v7 + 112));
  *((_DWORD *)a1 + 166) = 10;
  RefsCheckpointVolume(a1, (struct _VCB *)v7, 1u, 0, 1, (bool *)a2 + 2, &v13);
  RefsCommitCurrentTransaction(a1, 0);
  if ( !v6 || v13 )
    goto LABEL_38;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v9 = -1073740761;
  }
  else
  {
    v9 = -1073740761;
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_ca3360bb7e82316d71ea529aa669e6e2_Traceguids, 3221226535LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v10 = 747;
LABEL_36:
    RefsStatusDebug(v9, 0, "TransSup.c", v10);
  }
LABEL_37:
  v15 = v9;
LABEL_38:
  if ( v9 < 0 )
  {
    RefsRestoreScbSnapshots(a1, 1u);
    RefsAbortTransaction(a1);
    RefsRestoreScbSnapshots(a1, 0);
    RefsCleanupCheckpointForSnapshot(a1, a2);
  }
  if ( v5 )
    KeSetPriorityThread(KeGetCurrentThread(), v4);
  if ( EventHandle[0] )
    ZwClose(EventHandle[0]);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140293158  mov     r11, rsp
0x14029315b  mov     [r11+18h], rbx
0x14029315f  mov     [r11+20h], rsi
0x140293163  push    rdi
0x140293164  push    r12
0x140293166  push    r13
0x140293168  push    r14
0x14029316a  push    r15
0x14029316c  sub     rsp, 130h
0x140293173  mov     rax, cs:__security_cookie
0x14029317a  xor     rax, rsp
0x14029317d  mov     [rsp+158h+var_38], rax
0x140293185  mov     r14, rdx
0x140293188  mov     rdi, rcx
0x14029318b  mov     [rsp+158h+var_100], rcx
0x140293190  mov     [rsp+158h+var_F8], rdx
0x140293195  xor     ebx, ebx
0x140293197  mov     [rsp+158h+var_114], ebx
0x14029319b  mov     r12d, ebx
0x14029319e  mov     [rsp+158h+var_110], ebx
0x1402931a2  movzx   r15d, bl
0x1402931a6  mov     [rsp+158h+var_117], r15b
0x1402931ab  mov     r13b, bl
0x1402931ae  mov     [rsp+158h+var_118], bl
0x1402931b2  movaps  xmm0, xmmword ptr cs:aBasenamedobjec; "\\BaseNamedObjects\\Microsoft.ReFS.Leak"...
0x1402931b9  movaps  xmmword ptr [rsp+158h+SourceString], xmm0
0x1402931c1  movaps  xmm1, xmmword ptr cs:aBasenamedobjec+10h; "edObjects\\Microsoft.ReFS.LeakDetection"...
0x1402931c8  movaps  [rsp+158h+var_98], xmm1
0x1402931d0  movaps  xmm0, xmmword ptr cs:aBasenamedobjec+20h; "s\\Microsoft.ReFS.LeakDetection.Event.X"
0x1402931d7  movaps  [rsp+158h+var_88], xmm0
0x1402931df  movaps  xmm1, xmmword ptr cs:aBasenamedobjec+30h; "oft.ReFS.LeakDetection.Event.X"
0x1402931e6  movaps  xmmword ptr [r11-78h], xmm1
0x1402931eb  movaps  xmm0, xmmword ptr cs:aBasenamedobjec+40h; ".LeakDetection.Event.X"
0x1402931f2  movaps  xmmword ptr [r11-68h], xmm0
0x1402931f7  movaps  xmm1, xmmword ptr cs:aBasenamedobjec+50h; "ection.Event.X"
0x1402931fe  movaps  xmmword ptr [r11-58h], xmm1
0x140293203  movups  xmm0, xmmword ptr cs:aBasenamedobjec+5Eh; "Event.X"
0x14029320a  movups  xmmword ptr [r11-4Ah], xmm0
0x14029320f  xorps   xmm1, xmm1
0x140293212  movups  xmmword ptr [rsp+158h+ObjectAttributes.Length], xmm1
0x140293217  movups  xmmword ptr [rsp+158h+ObjectAttributes.ObjectName], xmm1
0x14029321f  movups  xmmword ptr [rsp+158h+ObjectAttributes.SecurityDescriptor], xmm1
0x140293227  xorps   xmm0, xmm0
0x14029322a  movups  xmmword ptr [rsp+158h+DestinationString.Length], xmm0
0x14029322f  mov     [rsp+158h+EventHandle], rbx
0x140293234  mov     rsi, [rcx+40h]
0x140293238  mov     [rdx], ebx
0x14029323a  mov     eax, [rsi+18h]
0x14029323d  bt      eax, 19h
0x140293241  jnb     short loc_140293273
0x140293243  xor     eax, eax
0x140293245  mov     rcx, [rsp+158h+var_38]
0x14029324d  xor     rcx, rsp; StackCookie
0x140293250  call    __security_check_cookie
0x140293255  lea     r11, [rsp+158h+var_28]
0x14029325d  mov     rbx, [r11+40h]
0x140293261  mov     rsi, [r11+48h]
0x140293265  mov     rsp, r11
0x140293268  pop     r15
0x14029326a  pop     r14
0x14029326c  pop     r13
0x14029326e  pop     r12
0x140293270  pop     rdi
0x140293271  retn
0x140293273  mov     r8b, 1; unsigned __int8
0x140293276  mov     rdx, rsi; struct _VCB *
0x140293279  call    ?RefsAcquireExclusiveVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireExclusiveVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x14029327e  mov     ecx, 1
0x140293283  mov     [r14+1], cl
0x140293287  mov     eax, [rsi+18h]
0x14029328a  test    cl, al
0x14029328c  jnz     short loc_1402932ED
0x14029328e  lea     rax, WPP_GLOBAL_Control
0x140293295  mov     rcx, cs:WPP_GLOBAL_Control
0x14029329c  cmp     rcx, rax
0x14029329f  jz      short loc_1402932CF
0x1402932a1  mov     eax, [rcx+2Ch]
0x1402932a4  bt      eax, 8
0x1402932a8  jnb     short loc_1402932CF
0x1402932aa  cmp     byte ptr [rcx+29h], 4
0x1402932ae  jb      short loc_1402932CF
0x1402932b0  mov     edx, 10h
0x1402932b5  mov     ebx, 0C000026Eh
0x1402932ba  mov     r9d, ebx
0x1402932bd  lea     r8, WPP_ca3360bb7e82316d71ea529aa669e6e2_Traceguids
0x1402932c4  mov     rcx, [rcx+18h]
0x1402932c8  call    WPP_SF_d
0x1402932cd  jmp     short loc_1402932D4
0x1402932cf  mov     ebx, 0C000026Eh
0x1402932d4  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402932da  test    al, al
0x1402932dc  jz      loc_1402934F3
0x1402932e2  mov     r9d, 27Bh
0x1402932e8  jmp     loc_1402934E3
0x1402932ed  lea     rdx, [rsp+158h+SourceString]; SourceString
0x1402932f5  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x1402932fa  call    cs:__imp_RtlInitUnicodeString
0x140293301  nop     dword ptr [rax+rax+00h]
0x140293306  mov     [rsp+158h+ObjectAttributes.Length], 30h ; '0'
0x14029330e  mov     [rsp+158h+ObjectAttributes.RootDirectory], rbx
0x140293316  mov     [rsp+158h+ObjectAttributes.Attributes], 200h
0x140293321  lea     rax, [rsp+158h+DestinationString]
0x140293326  mov     [rsp+158h+ObjectAttributes.ObjectName], rax
0x14029332e  xorps   xmm0, xmm0
0x140293331  movdqu  xmmword ptr [rsp+158h+ObjectAttributes.SecurityDescriptor], xmm0
0x14029333a  lea     r8, [rsp+158h+ObjectAttributes]; ObjectAttributes
0x14029333f  mov     edx, 1F0003h; DesiredAccess
0x140293344  lea     rcx, [rsp+158h+EventHandle]; EventHandle
0x140293349  call    cs:__imp_ZwOpenEvent
0x140293350  nop     dword ptr [rax+rax+00h]
0x140293355  mov     ebx, eax
0x140293357  mov     [rsp+158h+var_114], eax
0x14029335b  test    eax, eax
0x14029335d  js      short loc_140293364
0x14029335f  mov     r13b, 1
0x140293362  jmp     short loc_140293378
0x140293364  cmp     eax, 0C000003Ah
0x140293369  jz      short loc_140293372
0x14029336b  cmp     eax, 0C0000034h
0x140293370  jnz     short loc_140293378
0x140293372  xor     ebx, ebx
0x140293374  mov     [rsp+158h+var_114], ebx
0x140293378  test    ebx, ebx
0x14029337a  js      loc_1402934F7
0x140293380  mov     al, cs:?RefsUseFlushVolumeParallel@@3EC; uchar volatile RefsUseFlushVolumeParallel
0x140293386  mov     r8d, 41h ; 'A'
0x14029338c  mov     rdx, rsi
0x14029338f  mov     rcx, rdi
0x140293392  test    al, al
0x140293394  jz      short loc_14029339D
0x140293396  call    ?RefsFlushVolumeParallel@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@@Z; RefsFlushVolumeParallel(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS)
0x14029339b  jmp     short loc_1402933A2
0x14029339d  call    ?RefsFlushVolumeOriginal@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@@Z; RefsFlushVolumeOriginal(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS)
0x1402933a2  mov     rcx, gs:188h; Thread
0x1402933ab  mov     edx, 10h; Priority
0x1402933b0  call    cs:__imp_KeSetPriorityThread
0x1402933b7  nop     dword ptr [rax+rax+00h]
0x1402933bc  mov     r12d, eax
0x1402933bf  mov     [rsp+158h+var_110], eax
0x1402933c3  cmp     eax, 10h
0x1402933c6  mov     eax, 1
0x1402933cb  cmovnz  r15d, eax
0x1402933cf  mov     [rsp+158h+var_117], r15b
0x1402933d4  mov     edx, eax
0x1402933d6  mov     rcx, [rsi+70h]; this
0x1402933da  call    MsPauseAndFlushBackgroundActivity
0x1402933df  mov     ebx, eax
0x1402933e1  mov     [rsp+158h+var_114], eax
0x1402933e5  mov     byte ptr [r14+3], 1
0x1402933ea  test    eax, eax
0x1402933ec  js      loc_1402934F7
0x1402933f2  mov     r8d, 1Eh
0x1402933f8  mov     rdx, rsi
0x1402933fb  mov     rcx, rdi
0x1402933fe  call    ?RefsAcquireAllFiles@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@W4_REFS_ACQUIRE_ALL_FILES_FLAGS@@@Z; RefsAcquireAllFiles(_IRP_CONTEXT *,_VCB *,_REFS_ACQUIRE_ALL_FILES_FLAGS)
0x140293403  mov     byte ptr [r14], 1
0x140293407  mov     al, cs:?RefsUseFlushVolumeParallel@@3EC; uchar volatile RefsUseFlushVolumeParallel
0x14029340d  mov     r8d, 6C2h
0x140293413  mov     rdx, rsi
0x140293416  mov     rcx, rdi
0x140293419  test    al, al
0x14029341b  jz      short loc_140293424
0x14029341d  call    ?RefsFlushVolumeParallel@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@@Z; RefsFlushVolumeParallel(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS)
0x140293422  jmp     short loc_140293429
0x140293424  call    ?RefsFlushVolumeOriginal@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@@Z; RefsFlushVolumeOriginal(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS)
0x140293429  mov     ebx, eax
0x14029342b  mov     [rsp+158h+var_114], eax
0x14029342f  test    eax, eax
0x140293431  js      loc_1402934F7
0x140293437  mov     rcx, [rsi+70h]
0x14029343b  call    MsDrainLWQueue
0x140293440  mov     dword ptr [rdi+298h], 0Ah
0x14029344a  lea     rax, [r14+2]
0x14029344e  lea     rcx, [rsp+158h+var_118]
0x140293453  mov     [rsp+158h+var_128], rcx; bool *
0x140293458  mov     [rsp+158h+var_130], rax; bool *
0x14029345d  mov     eax, 1
0x140293462  mov     [rsp+158h+var_138], al; char
0x140293466  xor     r9d, r9d; unsigned __int8
0x140293469  mov     r8b, al; unsigned __int8
0x14029346c  mov     rdx, rsi; struct _VCB *
0x14029346f  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140293472  call    ?RefsCheckpointVolume@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@EEEPEA_N2@Z; RefsCheckpointVolume(_IRP_CONTEXT *,_VCB *,uchar,uchar,uchar,bool *,bool *)
0x140293477  xor     edx, edx; unsigned __int8
0x140293479  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14029347c  call    ?RefsCommitCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsCommitCurrentTransaction(_IRP_CONTEXT *,uchar)
0x140293481  test    r13b, r13b
0x140293484  jz      short loc_1402934F7
0x140293486  cmp     [rsp+158h+var_118], 0
0x14029348b  jnz     short loc_1402934F7
0x14029348d  lea     rax, WPP_GLOBAL_Control
0x140293494  mov     rcx, cs:WPP_GLOBAL_Control
0x14029349b  cmp     rcx, rax
0x14029349e  jz      short loc_1402934CE
0x1402934a0  mov     eax, [rcx+2Ch]
0x1402934a3  bt      eax, 8
0x1402934a7  jnb     short loc_1402934CE
0x1402934a9  cmp     byte ptr [rcx+29h], 4
0x1402934ad  jb      short loc_1402934CE
0x1402934af  mov     edx, 11h
0x1402934b4  mov     ebx, 0C0000427h
0x1402934b9  mov     r9d, ebx
0x1402934bc  lea     r8, WPP_ca3360bb7e82316d71ea529aa669e6e2_Traceguids
0x1402934c3  mov     rcx, [rcx+18h]
0x1402934c7  call    WPP_SF_d
0x1402934cc  jmp     short loc_1402934D3
0x1402934ce  mov     ebx, 0C0000427h
0x1402934d3  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1402934d9  test    al, al
0x1402934db  jz      short loc_1402934F3
0x1402934dd  mov     r9d, 2EBh; unsigned int
0x1402934e3  lea     r8, aTranssupC; "TransSup.c"
0x1402934ea  xor     edx, edx; struct _IRP_CONTEXT *
0x1402934ec  mov     ecx, ebx; Status
0x1402934ee  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1402934f3  mov     [rsp+158h+var_114], ebx
0x1402934f7  test    ebx, ebx
0x1402934f9  jns     short loc_140293522
0x1402934fb  mov     dl, 1; unsigned __int8
0x1402934fd  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140293500  call    ?RefsRestoreScbSnapshots@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsRestoreScbSnapshots(_IRP_CONTEXT *,uchar)
0x140293505  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140293508  call    ?RefsAbortTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsAbortTransaction(_IRP_CONTEXT *)
0x14029350d  xor     edx, edx; unsigned __int8
0x14029350f  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140293512  call    ?RefsRestoreScbSnapshots@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsRestoreScbSnapshots(_IRP_CONTEXT *,uchar)
0x140293517  mov     rdx, r14; struct SNAPSHOT_CHECKPOINT_FLAGS *
0x14029351a  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14029351d  call    ?RefsCleanupCheckpointForSnapshot@@YAXAEAU_IRP_CONTEXT@@AEAUSNAPSHOT_CHECKPOINT_FLAGS@@@Z; RefsCleanupCheckpointForSnapshot(_IRP_CONTEXT &,SNAPSHOT_CHECKPOINT_FLAGS &)
0x140293522  test    r15b, r15b
0x140293525  jz      short loc_14029353F
0x140293527  mov     rcx, gs:188h; Thread
0x140293530  mov     edx, r12d; Priority
0x140293533  call    cs:__imp_KeSetPriorityThread
0x14029353a  nop     dword ptr [rax+rax+00h]
0x14029353f  mov     rcx, [rsp+158h+EventHandle]; Handle
0x140293544  test    rcx, rcx
0x140293547  jz      short loc_140293555
0x140293549  call    cs:__imp_ZwClose
0x140293550  nop     dword ptr [rax+rax+00h]
0x140293555  mov     eax, ebx
0x140293557  jmp     loc_140293245
0x1403454cc  push    rbx
0x1403454ce  push    rbp
0x1403454cf  sub     rsp, 48h
0x1403454d3  mov     rbp, rdx
0x1403454d6  cmp     dword ptr [rbp+44h], 0
0x1403454da  jl      short loc_1403454E3
0x1403454dc  movzx   eax, cl
0x1403454df  test    cl, cl
0x1403454e1  jz      short loc_140345510
0x1403454e3  mov     dl, 1; unsigned __int8
0x1403454e5  mov     rbx, [rbp+58h]
0x1403454e9  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1403454ec  call    ?RefsRestoreScbSnapshots@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsRestoreScbSnapshots(_IRP_CONTEXT *,uchar)
0x1403454f1  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1403454f4  call    ?RefsAbortTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsAbortTransaction(_IRP_CONTEXT *)
0x1403454f9  xor     edx, edx; unsigned __int8
0x1403454fb  mov     rcx, rbx; struct _IRP_CONTEXT *
0x1403454fe  call    ?RefsRestoreScbSnapshots@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsRestoreScbSnapshots(_IRP_CONTEXT *,uchar)
0x140345503  mov     rdx, [rbp+60h]; struct SNAPSHOT_CHECKPOINT_FLAGS *
0x140345507  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14034550a  call    ?RefsCleanupCheckpointForSnapshot@@YAXAEAU_IRP_CONTEXT@@AEAUSNAPSHOT_CHECKPOINT_FLAGS@@@Z; RefsCleanupCheckpointForSnapshot(_IRP_CONTEXT &,SNAPSHOT_CHECKPOINT_FLAGS &)
0x14034550f  nop
0x140345510  cmp     byte ptr [rbp+41h], 0
0x140345514  jz      short loc_14034552F
0x140345516  mov     rcx, gs:188h; Thread
0x14034551f  mov     edx, [rbp+48h]; Priority
0x140345522  call    cs:__imp_KeSetPriorityThread
0x140345529  nop     dword ptr [rax+rax+00h]
0x14034552e  nop
0x14034552f  mov     rcx, [rbp+50h]; Handle
0x140345533  test    rcx, rcx
0x140345536  jz      short loc_140345545
0x140345538  call    cs:__imp_ZwClose
0x14034553f  nop     dword ptr [rax+rax+00h]
0x140345544  nop
0x140345545  add     rsp, 48h
0x140345549  pop     rbp
0x14034554a  pop     rbx
0x14034554b  retn
```
