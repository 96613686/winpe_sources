# RefsCheckpointForVolumeSnapshot(_IRP_CONTEXT *,SNAPSHOT_CHECKPOINT_FLAGS &)

- ea: `0x14028c1bc`
- end: `0x14028c5c0`
- name: `?RefsCheckpointForVolumeSnapshot@@YAJPEAU_IRP_CONTEXT@@AEAUSNAPSHOT_CHECKPOINT_FLAGS@@@Z`
- size: `1028`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, struct SNAPSHOT_CHECKPOINT_FLAGS *)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1402961f4`

## callees

- `0x14003d4cc`
- `0x14008dbd0`
- `0x1400c91d0`
- `0x1400ca788`
- `0x140113aec`
- `0x1401e9ce0`
- `0x140286ebc`
- `0x1402870ec`
- `0x14028c1bc`
- `0x1402d0664`
- `0x1402e2510`
- `0x1402e2e30`
- `0x1402fed30`
- `0x140332ea0`
- `0x140334a20`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14028c35e`
- `ntoskrnl!RtlInitUnicodeString` at `0x14028c35e`
- `ntoskrnl!ZwClose` at `0x14028c5ad`
- `ntoskrnl!ZwClose` at `0x14034275f`
- `ntoskrnl!ZwClose` at `0x14028c5ad`
- `ntoskrnl!ZwClose` at `0x14034275f`
- `ntoskrnl!ZwOpenEvent` at `0x14028c3ad`
- `ntoskrnl!ZwOpenEvent` at `0x14028c3ad`
- `ntoskrnl!KeSetPriorityThread` at `0x14028c414`
- `ntoskrnl!KeSetPriorityThread` at `0x14028c597`
- `ntoskrnl!KeSetPriorityThread` at `0x140342749`
- `ntoskrnl!KeSetPriorityThread` at `0x14028c414`
- `ntoskrnl!KeSetPriorityThread` at `0x14028c597`
- `ntoskrnl!KeSetPriorityThread` at `0x140342749`

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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_6a619e697057341a7b882d2e9e9e4084_Traceguids, 3221226094LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_37;
    v10 = 637;
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_6a619e697057341a7b882d2e9e9e4084_Traceguids, 3221226535LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v10 = 751;
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
0x14028c1bc  mov     r11, rsp
0x14028c1bf  mov     [r11+18h], rbx
0x14028c1c3  mov     [r11+20h], rsi
0x14028c1c7  push    rdi
0x14028c1c8  push    r12
0x14028c1ca  push    r13
0x14028c1cc  push    r14
0x14028c1ce  push    r15
0x14028c1d0  sub     rsp, 130h
0x14028c1d7  mov     rax, cs:__security_cookie
0x14028c1de  xor     rax, rsp
0x14028c1e1  mov     [rsp+158h+var_38], rax
0x14028c1e9  mov     r14, rdx
0x14028c1ec  mov     rdi, rcx
0x14028c1ef  mov     [rsp+158h+var_100], rcx
0x14028c1f4  mov     [rsp+158h+var_F8], rdx
0x14028c1f9  xor     ebx, ebx
0x14028c1fb  mov     [rsp+158h+var_114], ebx
0x14028c1ff  mov     r12d, ebx
0x14028c202  mov     [rsp+158h+var_110], ebx
0x14028c206  movzx   r15d, bl
0x14028c20a  mov     [rsp+158h+var_117], r15b
0x14028c20f  mov     r13b, bl
0x14028c212  mov     [rsp+158h+var_118], bl
0x14028c216  movaps  xmm0, xmmword ptr cs:aBasenamedobjec; "\\BaseNamedObjects\\Microsoft.ReFS.Leak"...
0x14028c21d  movaps  xmmword ptr [rsp+158h+SourceString], xmm0
0x14028c225  movaps  xmm1, xmmword ptr cs:aBasenamedobjec+10h; "edObjects\\Microsoft.ReFS.LeakDetection"...
0x14028c22c  movaps  [rsp+158h+var_98], xmm1
0x14028c234  movaps  xmm0, xmmword ptr cs:aBasenamedobjec+20h; "s\\Microsoft.ReFS.LeakDetection.Event.X"
0x14028c23b  movaps  [rsp+158h+var_88], xmm0
0x14028c243  movaps  xmm1, xmmword ptr cs:aBasenamedobjec+30h; "oft.ReFS.LeakDetection.Event.X"
0x14028c24a  movaps  xmmword ptr [r11-78h], xmm1
0x14028c24f  movaps  xmm0, xmmword ptr cs:aBasenamedobjec+40h; ".LeakDetection.Event.X"
0x14028c256  movaps  xmmword ptr [r11-68h], xmm0
0x14028c25b  movaps  xmm1, xmmword ptr cs:aBasenamedobjec+50h; "ection.Event.X"
0x14028c262  movaps  xmmword ptr [r11-58h], xmm1
0x14028c267  movups  xmm0, xmmword ptr cs:aBasenamedobjec+5Eh; "Event.X"
0x14028c26e  movups  xmmword ptr [r11-4Ah], xmm0
0x14028c273  xorps   xmm1, xmm1
0x14028c276  movups  xmmword ptr [rsp+158h+ObjectAttributes.Length], xmm1
0x14028c27b  movups  xmmword ptr [rsp+158h+ObjectAttributes.ObjectName], xmm1
0x14028c283  movups  xmmword ptr [rsp+158h+ObjectAttributes.SecurityDescriptor], xmm1
0x14028c28b  xorps   xmm0, xmm0
0x14028c28e  movups  xmmword ptr [rsp+158h+DestinationString.Length], xmm0
0x14028c293  mov     [rsp+158h+EventHandle], rbx
0x14028c298  mov     rsi, [rcx+40h]
0x14028c29c  mov     [rdx], ebx
0x14028c29e  mov     eax, [rsi+18h]
0x14028c2a1  bt      eax, 19h
0x14028c2a5  jnb     short loc_14028C2D7
0x14028c2a7  xor     eax, eax
0x14028c2a9  mov     rcx, [rsp+158h+var_38]
0x14028c2b1  xor     rcx, rsp; StackCookie
0x14028c2b4  call    __security_check_cookie
0x14028c2b9  lea     r11, [rsp+158h+var_28]
0x14028c2c1  mov     rbx, [r11+40h]
0x14028c2c5  mov     rsi, [r11+48h]
0x14028c2c9  mov     rsp, r11
0x14028c2cc  pop     r15
0x14028c2ce  pop     r14
0x14028c2d0  pop     r13
0x14028c2d2  pop     r12
0x14028c2d4  pop     rdi
0x14028c2d5  retn
0x14028c2d7  mov     r8b, 1; unsigned __int8
0x14028c2da  mov     rdx, rsi; struct _VCB *
0x14028c2dd  call    ?RefsAcquireExclusiveVcb@@YAEPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsAcquireExclusiveVcb(_IRP_CONTEXT *,_VCB *,uchar)
0x14028c2e2  mov     ecx, 1
0x14028c2e7  mov     [r14+1], cl
0x14028c2eb  mov     eax, [rsi+18h]
0x14028c2ee  test    cl, al
0x14028c2f0  jnz     short loc_14028C351
0x14028c2f2  lea     rax, WPP_GLOBAL_Control
0x14028c2f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14028c300  cmp     rcx, rax
0x14028c303  jz      short loc_14028C333
0x14028c305  mov     eax, [rcx+2Ch]
0x14028c308  bt      eax, 8
0x14028c30c  jnb     short loc_14028C333
0x14028c30e  cmp     byte ptr [rcx+29h], 4
0x14028c312  jb      short loc_14028C333
0x14028c314  mov     edx, 10h
0x14028c319  mov     ebx, 0C000026Eh
0x14028c31e  mov     r9d, ebx
0x14028c321  lea     r8, WPP_6a619e697057341a7b882d2e9e9e4084_Traceguids
0x14028c328  mov     rcx, [rcx+18h]
0x14028c32c  call    WPP_SF_d
0x14028c331  jmp     short loc_14028C338
0x14028c333  mov     ebx, 0C000026Eh
0x14028c338  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14028c33e  test    al, al
0x14028c340  jz      loc_14028C557
0x14028c346  mov     r9d, 27Dh
0x14028c34c  jmp     loc_14028C547
0x14028c351  lea     rdx, [rsp+158h+SourceString]; SourceString
0x14028c359  lea     rcx, [rsp+158h+DestinationString]; DestinationString
0x14028c35e  call    cs:__imp_RtlInitUnicodeString
0x14028c365  nop     dword ptr [rax+rax+00h]
0x14028c36a  mov     [rsp+158h+ObjectAttributes.Length], 30h ; '0'
0x14028c372  mov     [rsp+158h+ObjectAttributes.RootDirectory], rbx
0x14028c37a  mov     [rsp+158h+ObjectAttributes.Attributes], 200h
0x14028c385  lea     rax, [rsp+158h+DestinationString]
0x14028c38a  mov     [rsp+158h+ObjectAttributes.ObjectName], rax
0x14028c392  xorps   xmm0, xmm0
0x14028c395  movdqu  xmmword ptr [rsp+158h+ObjectAttributes.SecurityDescriptor], xmm0
0x14028c39e  lea     r8, [rsp+158h+ObjectAttributes]; ObjectAttributes
0x14028c3a3  mov     edx, 1F0003h; DesiredAccess
0x14028c3a8  lea     rcx, [rsp+158h+EventHandle]; EventHandle
0x14028c3ad  call    cs:__imp_ZwOpenEvent
0x14028c3b4  nop     dword ptr [rax+rax+00h]
0x14028c3b9  mov     ebx, eax
0x14028c3bb  mov     [rsp+158h+var_114], eax
0x14028c3bf  test    eax, eax
0x14028c3c1  js      short loc_14028C3C8
0x14028c3c3  mov     r13b, 1
0x14028c3c6  jmp     short loc_14028C3DC
0x14028c3c8  cmp     eax, 0C000003Ah
0x14028c3cd  jz      short loc_14028C3D6
0x14028c3cf  cmp     eax, 0C0000034h
0x14028c3d4  jnz     short loc_14028C3DC
0x14028c3d6  xor     ebx, ebx
0x14028c3d8  mov     [rsp+158h+var_114], ebx
0x14028c3dc  test    ebx, ebx
0x14028c3de  js      loc_14028C55B
0x14028c3e4  mov     al, cs:?RefsUseFlushVolumeParallel@@3EC; uchar volatile RefsUseFlushVolumeParallel
0x14028c3ea  mov     r8d, 41h ; 'A'
0x14028c3f0  mov     rdx, rsi
0x14028c3f3  mov     rcx, rdi
0x14028c3f6  test    al, al
0x14028c3f8  jz      short loc_14028C401
0x14028c3fa  call    ?RefsFlushVolumeParallel@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@@Z; RefsFlushVolumeParallel(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS)
0x14028c3ff  jmp     short loc_14028C406
0x14028c401  call    ?RefsFlushVolumeOriginal@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@@Z; RefsFlushVolumeOriginal(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS)
0x14028c406  mov     rcx, gs:188h; Thread
0x14028c40f  mov     edx, 10h; Priority
0x14028c414  call    cs:__imp_KeSetPriorityThread
0x14028c41b  nop     dword ptr [rax+rax+00h]
0x14028c420  mov     r12d, eax
0x14028c423  mov     [rsp+158h+var_110], eax
0x14028c427  cmp     eax, 10h
0x14028c42a  mov     eax, 1
0x14028c42f  cmovnz  r15d, eax
0x14028c433  mov     [rsp+158h+var_117], r15b
0x14028c438  mov     edx, eax
0x14028c43a  mov     rcx, [rsi+70h]; this
0x14028c43e  call    MsPauseAndFlushBackgroundActivity
0x14028c443  mov     ebx, eax
0x14028c445  mov     [rsp+158h+var_114], eax
0x14028c449  mov     byte ptr [r14+3], 1
0x14028c44e  test    eax, eax
0x14028c450  js      loc_14028C55B
0x14028c456  mov     r8d, 1Eh
0x14028c45c  mov     rdx, rsi
0x14028c45f  mov     rcx, rdi
0x14028c462  call    ?RefsAcquireAllFiles@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@W4_REFS_ACQUIRE_ALL_FILES_FLAGS@@@Z; RefsAcquireAllFiles(_IRP_CONTEXT *,_VCB *,_REFS_ACQUIRE_ALL_FILES_FLAGS)
0x14028c467  mov     byte ptr [r14], 1
0x14028c46b  mov     al, cs:?RefsUseFlushVolumeParallel@@3EC; uchar volatile RefsUseFlushVolumeParallel
0x14028c471  mov     r8d, 6C2h
0x14028c477  mov     rdx, rsi
0x14028c47a  mov     rcx, rdi
0x14028c47d  test    al, al
0x14028c47f  jz      short loc_14028C488
0x14028c481  call    ?RefsFlushVolumeParallel@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@@Z; RefsFlushVolumeParallel(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS)
0x14028c486  jmp     short loc_14028C48D
0x14028c488  call    ?RefsFlushVolumeOriginal@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@W4REFS_FLUSH_VOLUME_FLAGS@@@Z; RefsFlushVolumeOriginal(_IRP_CONTEXT *,_VCB *,REFS_FLUSH_VOLUME_FLAGS)
0x14028c48d  mov     ebx, eax
0x14028c48f  mov     [rsp+158h+var_114], eax
0x14028c493  test    eax, eax
0x14028c495  js      loc_14028C55B
0x14028c49b  mov     rcx, [rsi+70h]
0x14028c49f  call    MsDrainLWQueue
0x14028c4a4  mov     dword ptr [rdi+298h], 0Ah
0x14028c4ae  lea     rax, [r14+2]
0x14028c4b2  lea     rcx, [rsp+158h+var_118]
0x14028c4b7  mov     [rsp+158h+var_128], rcx; bool *
0x14028c4bc  mov     [rsp+158h+var_130], rax; bool *
0x14028c4c1  mov     eax, 1
0x14028c4c6  mov     [rsp+158h+var_138], al; char
0x14028c4ca  xor     r9d, r9d; unsigned __int8
0x14028c4cd  mov     r8b, al; unsigned __int8
0x14028c4d0  mov     rdx, rsi; struct _VCB *
0x14028c4d3  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14028c4d6  call    ?RefsCheckpointVolume@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@EEEPEA_N2@Z; RefsCheckpointVolume(_IRP_CONTEXT *,_VCB *,uchar,uchar,uchar,bool *,bool *)
0x14028c4db  xor     edx, edx; unsigned __int8
0x14028c4dd  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14028c4e0  call    ?RefsCommitCurrentTransaction@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsCommitCurrentTransaction(_IRP_CONTEXT *,uchar)
0x14028c4e5  test    r13b, r13b
0x14028c4e8  jz      short loc_14028C55B
0x14028c4ea  cmp     [rsp+158h+var_118], 0
0x14028c4ef  jnz     short loc_14028C55B
0x14028c4f1  lea     rax, WPP_GLOBAL_Control
0x14028c4f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14028c4ff  cmp     rcx, rax
0x14028c502  jz      short loc_14028C532
0x14028c504  mov     eax, [rcx+2Ch]
0x14028c507  bt      eax, 8
0x14028c50b  jnb     short loc_14028C532
0x14028c50d  cmp     byte ptr [rcx+29h], 4
0x14028c511  jb      short loc_14028C532
0x14028c513  mov     edx, 11h
0x14028c518  mov     ebx, 0C0000427h
0x14028c51d  mov     r9d, ebx
0x14028c520  lea     r8, WPP_6a619e697057341a7b882d2e9e9e4084_Traceguids
0x14028c527  mov     rcx, [rcx+18h]
0x14028c52b  call    WPP_SF_d
0x14028c530  jmp     short loc_14028C537
0x14028c532  mov     ebx, 0C0000427h
0x14028c537  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14028c53d  test    al, al
0x14028c53f  jz      short loc_14028C557
0x14028c541  mov     r9d, 2EFh; unsigned int
0x14028c547  lea     r8, aTranssupC; "TransSup.c"
0x14028c54e  xor     edx, edx; struct _IRP_CONTEXT *
0x14028c550  mov     ecx, ebx; Status
0x14028c552  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14028c557  mov     [rsp+158h+var_114], ebx
0x14028c55b  test    ebx, ebx
0x14028c55d  jns     short loc_14028C586
0x14028c55f  mov     dl, 1; unsigned __int8
0x14028c561  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14028c564  call    ?RefsRestoreScbSnapshots@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsRestoreScbSnapshots(_IRP_CONTEXT *,uchar)
0x14028c569  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14028c56c  call    ?RefsAbortTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsAbortTransaction(_IRP_CONTEXT *)
0x14028c571  xor     edx, edx; unsigned __int8
0x14028c573  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14028c576  call    ?RefsRestoreScbSnapshots@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsRestoreScbSnapshots(_IRP_CONTEXT *,uchar)
0x14028c57b  mov     rdx, r14; struct SNAPSHOT_CHECKPOINT_FLAGS *
0x14028c57e  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14028c581  call    ?RefsCleanupCheckpointForSnapshot@@YAXAEAU_IRP_CONTEXT@@AEAUSNAPSHOT_CHECKPOINT_FLAGS@@@Z; RefsCleanupCheckpointForSnapshot(_IRP_CONTEXT &,SNAPSHOT_CHECKPOINT_FLAGS &)
0x14028c586  test    r15b, r15b
0x14028c589  jz      short loc_14028C5A3
0x14028c58b  mov     rcx, gs:188h; Thread
0x14028c594  mov     edx, r12d; Priority
0x14028c597  call    cs:__imp_KeSetPriorityThread
0x14028c59e  nop     dword ptr [rax+rax+00h]
0x14028c5a3  mov     rcx, [rsp+158h+EventHandle]; Handle
0x14028c5a8  test    rcx, rcx
0x14028c5ab  jz      short loc_14028C5B9
0x14028c5ad  call    cs:__imp_ZwClose
0x14028c5b4  nop     dword ptr [rax+rax+00h]
0x14028c5b9  mov     eax, ebx
0x14028c5bb  jmp     loc_14028C2A9
0x1403426f3  push    rbx
0x1403426f5  push    rbp
0x1403426f6  sub     rsp, 48h
0x1403426fa  mov     rbp, rdx
0x1403426fd  cmp     dword ptr [rbp+44h], 0
0x140342701  jl      short loc_14034270A
0x140342703  movzx   eax, cl
0x140342706  test    cl, cl
0x140342708  jz      short loc_140342737
0x14034270a  mov     dl, 1; unsigned __int8
0x14034270c  mov     rbx, [rbp+58h]
0x140342710  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140342713  call    ?RefsRestoreScbSnapshots@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsRestoreScbSnapshots(_IRP_CONTEXT *,uchar)
0x140342718  mov     rcx, rbx; struct _IRP_CONTEXT *
0x14034271b  call    ?RefsAbortTransaction@@YAXPEAU_IRP_CONTEXT@@@Z; RefsAbortTransaction(_IRP_CONTEXT *)
0x140342720  xor     edx, edx; unsigned __int8
0x140342722  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140342725  call    ?RefsRestoreScbSnapshots@@YAXPEAU_IRP_CONTEXT@@E@Z; RefsRestoreScbSnapshots(_IRP_CONTEXT *,uchar)
0x14034272a  mov     rdx, [rbp+60h]; struct SNAPSHOT_CHECKPOINT_FLAGS *
0x14034272e  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140342731  call    ?RefsCleanupCheckpointForSnapshot@@YAXAEAU_IRP_CONTEXT@@AEAUSNAPSHOT_CHECKPOINT_FLAGS@@@Z; RefsCleanupCheckpointForSnapshot(_IRP_CONTEXT &,SNAPSHOT_CHECKPOINT_FLAGS &)
0x140342736  nop
0x140342737  cmp     byte ptr [rbp+41h], 0
0x14034273b  jz      short loc_140342756
0x14034273d  mov     rcx, gs:188h; Thread
0x140342746  mov     edx, [rbp+48h]; Priority
0x140342749  call    cs:__imp_KeSetPriorityThread
0x140342750  nop     dword ptr [rax+rax+00h]
0x140342755  nop
0x140342756  mov     rcx, [rbp+50h]; Handle
0x14034275a  test    rcx, rcx
0x14034275d  jz      short loc_14034276C
0x14034275f  call    cs:__imp_ZwClose
0x140342766  nop     dword ptr [rax+rax+00h]
0x14034276b  nop
0x14034276c  add     rsp, 48h
0x140342770  pop     rbp
0x140342771  pop     rbx
0x140342772  retn
```
