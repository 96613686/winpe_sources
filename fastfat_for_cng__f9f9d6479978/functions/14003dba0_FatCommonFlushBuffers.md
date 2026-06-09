# FatCommonFlushBuffers

- ea: `0x14003dba0`
- end: `0x14003e01f`
- name: `FatCommonFlushBuffers`
- size: `1151`
- prototype: `__int64 __fastcall(int, PIRP Irp)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14003e9d0`
- `0x1400438e0`

## callees

- `0x140002b30`
- `0x140006dbc`
- `0x140007408`
- `0x14002486c`
- `0x140034054`
- `0x140038eb4`
- `0x14003d880`
- `0x14003dba0`
- `0x14003e4b4`
- `0x14003e870`
- `0x14003e94c`
- `0x1400465f4`
- `0x1400466c8`
- `0x14004a1d4`
- `0x14004a37c`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14003dfe7`
- `ntoskrnl!IofCallDriver` at `0x14005ea73`
- `ntoskrnl!IofCallDriver` at `0x14003dfe7`
- `ntoskrnl!IofCallDriver` at `0x14005ea73`
- `ntoskrnl!KeCancelTimer` at `0x14003dd7c`
- `ntoskrnl!KeCancelTimer` at `0x14003dd7c`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14003dd8f`
- `ntoskrnl!KeRemoveQueueDpc` at `0x14003dd8f`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005e981`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x14005e981`
- `ntoskrnl!PsUpdateDiskCounters` at `0x14003dca0`
- `ntoskrnl!PsUpdateDiskCounters` at `0x14003dca0`
- `ntoskrnl!PsGetThreadProcess` at `0x14003dc7a`
- `ntoskrnl!PsGetThreadProcess` at `0x14003dc7a`
- `ntoskrnl!IoIsSystemThread` at `0x14003dc58`
- `ntoskrnl!IoIsSystemThread` at `0x14003dc58`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003df59`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003df76`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e9be`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e9dc`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003df59`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003df76`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e9be`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005e9dc`
- `ntoskrnl!KeBugCheckEx` at `0x14003dd0a`
- `ntoskrnl!KeBugCheckEx` at `0x14003dd0a`

## pseudocode

```c
__int64 __fastcall FatCommonFlushBuffers(_DWORD *a1, PIRP Irp)
{
  PIRP v2; // r13
  __int64 v4; // rdx
  ULONG_PTR v5; // rdi
  __int64 v6; // r8
  __int64 v7; // r9
  char v9; // r12
  int v10; // esi
  struct _KTHREAD *Thread; // rcx
  struct _KTHREAD *CurrentThread; // rcx
  PEPROCESS ThreadProcess; // rax
  __int64 v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rcx
  bool v18; // r12
  __int64 v19; // rdi
  __int64 v20; // rcx
  int v21; // eax
  char v22; // al
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *v23; // rcx
  struct _IO_STACK_LOCATION *v24; // rax
  struct _IO_STACK_LOCATION *v25; // rcx
  NTSTATUS v26; // eax
  char v27; // [rsp+30h] [rbp-78h]
  __int64 v28; // [rsp+38h] [rbp-70h] BYREF
  __int64 v29; // [rsp+40h] [rbp-68h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+48h] [rbp-60h]
  struct _IO_STACK_LOCATION *v31; // [rsp+50h] [rbp-58h]
  PFILE_OBJECT FileObject; // [rsp+58h] [rbp-50h]
  _DWORD *v33; // [rsp+60h] [rbp-48h]
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // [rsp+68h] [rbp-40h]
  __int64 v35; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v36; // [rsp+C8h] [rbp+20h] BYREF

  v2 = Irp;
  v35 = 0;
  v36 = 0;
  v28 = 0;
  p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v31 = CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  v5 = (int)FatDecodeFileObject(FileObject, &v35, &v36, &v28);
  v33 = a1 + 17;
  if ( (a1[17] & 2) == 0 )
    return FatFsdPostRequest(a1, v2);
  v27 = 0;
  v9 = 0;
  v10 = 0;
  if ( FatDiskAccountingEnabled )
  {
    Thread = v2->Tail.Overlay.Thread;
    if ( !Thread || IoIsSystemThread(Thread) )
      CurrentThread = KeGetCurrentThread();
    else
      CurrentThread = v2->Tail.Overlay.Thread;
    ThreadProcess = PsGetThreadProcess(CurrentThread);
    PsUpdateDiskCounters(ThreadProcess, 0, 0, 0, 0, 1);
  }
  switch ( (_DWORD)v5 )
  {
    case 2:
      goto LABEL_25;
    case 3:
      if ( *(_WORD *)v36 != 1284 )
        goto LABEL_38;
LABEL_19:
      v14 = v35;
      FatAcquireExclusiveVcb_Real(a1, v35, 0, v7);
      v27 = 1;
      FatVerifyVcb(a1, v14);
      v10 = FatFlushVolume(a1, v14, 1);
      if ( (*(_DWORD *)(v14 + 200) & 4) != 0 )
      {
        KeCancelTimer((PKTIMER)(v14 + 952));
        KeRemoveQueueDpc((PRKDPC)(v14 + 888));
        v15 = *(unsigned int *)(v14 + 200);
        if ( (v15 & 0x10) == 0 )
        {
          FatMarkVolume(a1, v14, 0);
          _InterlockedAnd((volatile signed __int32 *)(v14 + 200), 0xFFFFFFFB);
        }
        if ( (*(_DWORD *)(v35 + 200) & 2) != 0 && (*(_DWORD *)(v35 + 200) & 0x800) == 0 )
          FatToggleMediaEjectDisable(v15, v35, 0);
      }
      goto LABEL_38;
    case 4:
      goto LABEL_19;
  }
  if ( (_DWORD)v5 != 5 && (_DWORD)v5 != 6 && (_DWORD)v5 != 7 && (_DWORD)v5 != 8 )
  {
    if ( (_DWORD)v5 != 9 )
      KeBugCheckEx(0x23u, 0x1201DCu, v5, 0, 0);
LABEL_25:
    v16 = v36;
    FatAcquireExclusiveFcb(a1, v36, v6, v7);
    v9 = 1;
    FatVerifyFcb(a1, v16);
    v10 = FatFlushFile(v17, v16, 1);
    if ( v10 >= 0 )
    {
      FileObject->Flags |= 0x2000u;
      FatUpdateDirentFromFcb((int)a1, 0);
      v18 = (*(_BYTE *)(v16 + 192) & 0x10) != 0;
      v19 = *(_QWORD *)(v16 + 176);
      v29 = v19;
      while ( v19 )
      {
        FatVerifyFcb(a1, v19);
        if ( *(_DWORD *)(v19 + 196) == 1 )
        {
          v21 = FatFlushFile(v20, v19, 1);
          if ( v21 < 0 )
            v10 = v21;
          v22 = v18;
          if ( (*(_BYTE *)(v19 + 192) & 0x10) != 0 )
            v22 = 1;
          v18 = v22;
        }
        v19 = *(_QWORD *)(v19 + 176);
        v29 = v19;
      }
      if ( v18 )
      {
        v10 = FatFlushFat(a1, v35);
        *(_DWORD *)(v36 + 192) &= ~0x10u;
      }
      *v33 |= 4u;
      v9 = 1;
    }
  }
LABEL_38:
  FatUnpinRepinnedBcbs(a1, v4, v6, v7);
  if ( v27 )
    ExReleaseResourceLite((PERESOURCE)(v35 + 520));
  if ( v9 )
    ExReleaseResourceLite(*(PERESOURCE *)(v36 + 8));
  if ( (unsigned __int8)(CurrentStackLocation->MinorFunction - 2) > 1u )
  {
    v23 = p_CurrentStackLocation;
    v24 = p_CurrentStackLocation->CurrentStackLocation;
    *(_OWORD *)&v24[-1].MajorFunction = *(_OWORD *)&p_CurrentStackLocation->CurrentStackLocation->MajorFunction;
    *(_OWORD *)&v24[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v24->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v24[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v24->Parameters.SetQuota + 6);
    v24[-1].FileObject = v24->FileObject;
    v24[-1].Control = 0;
    v25 = v23->CurrentStackLocation;
    v25[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)FatFlushCompletionRoutine;
    v25[-1].Context = (PVOID)(unsigned int)v10;
    v25[-1].Control = -32;
    v26 = IofCallDriver(*(PDEVICE_OBJECT *)(v35 + 136), v2);
    if ( v26 == 259 || v26 < 0 && v26 != -1073741808 )
      v10 = v26;
    v2 = 0;
  }
  FatCompleteRequest_Real(a1, v2);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14003dba0  mov     r11, rsp
0x14003dba3  mov     [r11+10h], rdx
0x14003dba7  mov     [r11+8], rcx
0x14003dbab  push    rbx
0x14003dbac  push    rsi
0x14003dbad  push    rdi
0x14003dbae  push    r12
0x14003dbb0  push    r13
0x14003dbb2  push    r14
0x14003dbb4  push    r15
0x14003dbb6  sub     rsp, 70h
0x14003dbba  mov     r13, rdx
0x14003dbbd  mov     r14, rcx
0x14003dbc0  xor     ebx, ebx
0x14003dbc2  mov     [r11+18h], rbx
0x14003dbc6  mov     [r11+20h], rbx
0x14003dbca  mov     [r11-70h], rbx
0x14003dbce  lea     rax, [rdx+0B8h]
0x14003dbd5  mov     [rsp+0A8h+var_40], rax
0x14003dbda  mov     rax, [rax]
0x14003dbdd  mov     [rsp+0A8h+var_60], rax
0x14003dbe2  mov     [rsp+0A8h+var_58], rax
0x14003dbe7  mov     rax, [rax+30h]
0x14003dbeb  mov     [rsp+0A8h+var_50], rax
0x14003dbf0  lea     r9, [r11-70h]
0x14003dbf4  lea     r8, [r11+20h]
0x14003dbf8  lea     rdx, [r11+18h]
0x14003dbfc  mov     rcx, rax
0x14003dbff  call    FatDecodeFileObject
0x14003dc04  movsxd  rdi, eax
0x14003dc07  lea     rax, [r14+44h]
0x14003dc0b  mov     [rsp+0A8h+var_48], rax
0x14003dc10  mov     eax, [rax]
0x14003dc12  test    al, 2
0x14003dc14  jnz     short loc_14003DC32
0x14003dc16  mov     rdx, r13; Context2
0x14003dc19  mov     rcx, r14; Context1
0x14003dc1c  call    FatFsdPostRequest
0x14003dc21  add     rsp, 70h
0x14003dc25  pop     r15
0x14003dc27  pop     r14
0x14003dc29  pop     r13
0x14003dc2b  pop     r12
0x14003dc2d  pop     rdi
0x14003dc2e  pop     rsi
0x14003dc2f  pop     rbx
0x14003dc30  retn
0x14003dc32  mov     [rsp+0A8h+var_78], bl
0x14003dc36  mov     r12b, bl
0x14003dc39  mov     [rsp+0A8h+var_77], bl
0x14003dc3d  mov     esi, ebx
0x14003dc3f  mov     [rsp+0A8h+var_74], ebx
0x14003dc43  cmp     cs:FatDiskAccountingEnabled, 0
0x14003dc4a  jz      short loc_14003DCAE
0x14003dc4c  mov     rcx, [r13+98h]; Thread
0x14003dc53  test    rcx, rcx
0x14003dc56  jz      short loc_14003DC71
0x14003dc58  call    cs:__imp_IoIsSystemThread
0x14003dc5f  nop     dword ptr [rax+rax+00h]
0x14003dc64  test    al, al
0x14003dc66  jnz     short loc_14003DC71
0x14003dc68  mov     rcx, [r13+98h]
0x14003dc6f  jmp     short loc_14003DC7A
0x14003dc71  mov     rcx, gs:188h; Thread
0x14003dc7a  call    cs:__imp_PsGetThreadProcess
0x14003dc81  nop     dword ptr [rax+rax+00h]
0x14003dc86  mov     rcx, rax
0x14003dc89  mov     r15d, 1
0x14003dc8f  mov     [rsp+0A8h+var_80], r15d
0x14003dc94  mov     dword ptr [rsp+0A8h+BugCheckParameter4], ebx
0x14003dc98  xor     r9d, r9d
0x14003dc9b  xor     r8d, r8d
0x14003dc9e  xor     edx, edx
0x14003dca0  call    cs:__imp_PsUpdateDiskCounters
0x14003dca7  nop     dword ptr [rax+rax+00h]
0x14003dcac  jmp     short loc_14003DCB4
0x14003dcae  mov     r15d, 1
0x14003dcb4  mov     ecx, edi
0x14003dcb6  sub     ecx, 2
0x14003dcb9  jz      loc_14003DDF2
0x14003dcbf  sub     ecx, 1
0x14003dcc2  jz      short loc_14003DD16
0x14003dcc4  sub     ecx, 1
0x14003dcc7  jz      short loc_14003DD2C
0x14003dcc9  sub     ecx, 1
0x14003dccc  jz      loc_14003DF3B
0x14003dcd2  sub     ecx, 1
0x14003dcd5  jz      loc_14003DF3B
0x14003dcdb  sub     ecx, 1
0x14003dcde  jz      loc_14003DF3B
0x14003dce4  sub     ecx, 1
0x14003dce7  jz      loc_14003DF3B
0x14003dced  cmp     ecx, 1
0x14003dcf0  jz      loc_14003DDF2
0x14003dcf6  mov     r8, rdi; BugCheckParameter2
0x14003dcf9  mov     [rsp+0A8h+BugCheckParameter4], rbx; BugCheckParameter4
0x14003dcfe  xor     r9d, r9d; BugCheckParameter3
0x14003dd01  mov     edx, 1201DCh; BugCheckParameter1
0x14003dd06  lea     ecx, [r9+23h]; BugCheckCode
0x14003dd0a  call    cs:__imp_KeBugCheckEx
0x14003dd16  mov     ecx, 504h
0x14003dd1b  mov     rax, [rsp+0A8h+arg_18]
0x14003dd23  cmp     [rax], cx
0x14003dd26  jnz     loc_14003DF3B
0x14003dd2c  xor     r8d, r8d
0x14003dd2f  mov     rdi, [rsp+0A8h+arg_10]
0x14003dd37  mov     rdx, rdi
0x14003dd3a  mov     rcx, r14
0x14003dd3d  call    FatAcquireExclusiveVcb_Real
0x14003dd42  mov     [rsp+0A8h+var_78], r15b
0x14003dd47  mov     rdx, rdi
0x14003dd4a  mov     rcx, r14
0x14003dd4d  call    FatVerifyVcb
0x14003dd52  mov     r8d, r15d
0x14003dd55  mov     rdx, rdi
0x14003dd58  mov     rcx, r14
0x14003dd5b  call    FatFlushVolume
0x14003dd60  mov     esi, eax
0x14003dd62  mov     [rsp+0A8h+var_74], eax
0x14003dd66  mov     ecx, [rdi+0C8h]
0x14003dd6c  test    cl, 4
0x14003dd6f  jz      loc_14003DF3B
0x14003dd75  lea     rcx, [rdi+3B8h]; PKTIMER
0x14003dd7c  call    cs:__imp_KeCancelTimer
0x14003dd83  nop     dword ptr [rax+rax+00h]
0x14003dd88  lea     rcx, [rdi+378h]; Dpc
0x14003dd8f  call    cs:__imp_KeRemoveQueueDpc
0x14003dd96  nop     dword ptr [rax+rax+00h]
0x14003dd9b  mov     ecx, [rdi+0C8h]
0x14003dda1  test    cl, 10h
0x14003dda4  jnz     short loc_14003DDBC
0x14003dda6  xor     r8d, r8d
0x14003dda9  mov     rdx, rdi
0x14003ddac  mov     rcx, r14
0x14003ddaf  call    FatMarkVolume
0x14003ddb4  lock and dword ptr [rdi+0C8h], 0FFFFFFFBh
0x14003ddbc  mov     rdi, [rsp+0A8h+arg_10]
0x14003ddc4  mov     eax, [rdi+0C8h]
0x14003ddca  test    al, 2
0x14003ddcc  jz      loc_14003DF3B
0x14003ddd2  mov     eax, [rdi+0C8h]
0x14003ddd8  bt      eax, 0Bh
0x14003dddc  jb      loc_14003DF3B
0x14003dde2  xor     r8d, r8d
0x14003dde5  mov     rdx, rdi
0x14003dde8  call    FatToggleMediaEjectDisable
0x14003dded  jmp     loc_14003DF3B
0x14003ddf2  mov     rdi, [rsp+0A8h+arg_18]
0x14003ddfa  mov     rdx, rdi
0x14003ddfd  mov     rcx, r14
0x14003de00  call    FatAcquireExclusiveFcb
0x14003de05  mov     r12b, r15b
0x14003de08  mov     [rsp+0A8h+var_77], r15b
0x14003de0d  mov     rdx, rdi
0x14003de10  mov     rcx, r14
0x14003de13  call    FatVerifyFcb
0x14003de18  mov     r8d, r15d
0x14003de1b  mov     rdx, rdi
0x14003de1e  call    FatFlushFile
0x14003de23  mov     esi, eax
0x14003de25  mov     [rsp+0A8h+var_74], eax
0x14003de29  test    eax, eax
0x14003de2b  js      loc_14003DF3B
0x14003de31  mov     rdx, [rsp+0A8h+var_50]
0x14003de36  mov     eax, [rdx+50h]
0x14003de39  bts     eax, 0Dh
0x14003de3d  mov     [rdx+50h], eax
0x14003de40  mov     byte ptr [rsp+0A8h+BugCheckParameter4], bl; char
0x14003de44  mov     r9, [rsp+0A8h+var_70]
0x14003de49  mov     r8, rdi
0x14003de4c  mov     rcx, r14; int
0x14003de4f  call    FatUpdateDirentFromFcb
0x14003de54  test    byte ptr [rdi+0C0h], 10h
0x14003de5b  movzx   r12d, bl
0x14003de5f  cmovnz  r12d, r15d
0x14003de63  mov     [rsp+0A8h+var_76], r12b
0x14003de68  mov     rdi, [rdi+0B0h]
0x14003de6f  mov     [rsp+0A8h+var_68], rdi
0x14003de74  test    rdi, rdi
0x14003de77  jz      loc_14003DF04
0x14003de7d  mov     rdx, rdi
0x14003de80  mov     rcx, r14
0x14003de83  call    FatVerifyFcb
0x14003de88  jmp     short loc_14003DEC0
0x14003de8a  mov     r14, [rsp+0A8h+arg_0]
0x14003de92  mov     dword ptr [r14+48h], 0
0x14003de9a  xor     ebx, ebx
0x14003de9c  lea     r15d, [rbx+1]
0x14003dea0  mov     r13, [rsp+0A8h+arg_8]
0x14003dea8  mov     esi, [rsp+0A8h+var_74]
0x14003deac  mov     rax, [rsp+0A8h+var_58]
0x14003deb1  mov     [rsp+0A8h+var_60], rax
0x14003deb6  mov     rdi, [rsp+0A8h+var_68]
0x14003debb  mov     r12b, [rsp+0A8h+var_76]
0x14003dec0  cmp     [rdi+0C4h], r15d
0x14003dec7  jnz     short loc_14003DEF3
0x14003dec9  mov     r8d, r15d
0x14003decc  mov     rdx, rdi
0x14003decf  call    FatFlushFile
0x14003ded4  test    eax, eax
0x14003ded6  cmovs   esi, eax
0x14003ded9  mov     [rsp+0A8h+var_74], esi
0x14003dedd  test    byte ptr [rdi+0C0h], 10h
0x14003dee4  movzx   eax, r12b
0x14003dee8  cmovnz  eax, r15d
0x14003deec  mov     r12b, al
0x14003deef  mov     [rsp+0A8h+var_76], al
0x14003def3  mov     rdi, [rdi+0B0h]
0x14003defa  mov     [rsp+0A8h+var_68], rdi
0x14003deff  jmp     loc_14003DE74
0x14003df04  test    r12b, r12b
0x14003df07  jz      short loc_14003DF2E
0x14003df09  mov     rdx, [rsp+0A8h+arg_10]
0x14003df11  mov     rcx, r14
0x14003df14  call    FatFlushFat
0x14003df19  mov     esi, eax
0x14003df1b  mov     [rsp+0A8h+var_74], eax
0x14003df1f  mov     rax, [rsp+0A8h+arg_18]
0x14003df27  and     dword ptr [rax+0C0h], 0FFFFFFEFh
0x14003df2e  mov     rax, [rsp+0A8h+var_48]
0x14003df33  or      dword ptr [rax], 4
0x14003df36  mov     r12b, [rsp+0A8h+var_77]
0x14003df3b  mov     rcx, r14
0x14003df3e  call    FatUnpinRepinnedBcbs
0x14003df43  nop
0x14003df44  cmp     [rsp+0A8h+var_78], bl
0x14003df48  jz      short loc_14003DF65
0x14003df4a  mov     rcx, [rsp+0A8h+arg_10]
0x14003df52  add     rcx, 208h; Resource
0x14003df59  call    cs:__imp_ExReleaseResourceLite
0x14003df60  nop     dword ptr [rax+rax+00h]
0x14003df65  test    r12b, r12b
0x14003df68  jz      short loc_14003DF82
0x14003df6a  mov     rcx, [rsp+0A8h+arg_18]
0x14003df72  mov     rcx, [rcx+8]; Resource
0x14003df76  call    cs:__imp_ExReleaseResourceLite
0x14003df7d  nop     dword ptr [rax+rax+00h]
0x14003df82  mov     rax, [rsp+0A8h+var_60]
0x14003df87  mov     al, [rax+1]
0x14003df8a  sub     al, 2
0x14003df8c  cmp     al, r15b
0x14003df8f  jbe     short loc_14003E00A
0x14003df91  mov     rcx, [rsp+0A8h+var_40]
0x14003df96  mov     rax, [rcx]
0x14003df99  movups  xmm0, xmmword ptr [rax]
0x14003df9c  movups  xmmword ptr [rax-48h], xmm0
0x14003dfa0  movups  xmm1, xmmword ptr [rax+10h]
0x14003dfa4  movups  xmmword ptr [rax-38h], xmm1
0x14003dfa8  movups  xmm0, xmmword ptr [rax+20h]
0x14003dfac  movups  xmmword ptr [rax-28h], xmm0
0x14003dfb0  movsd   xmm1, qword ptr [rax+30h]
0x14003dfb5  movsd   qword ptr [rax-18h], xmm1
0x14003dfba  mov     [rax-45h], bl
0x14003dfbd  mov     rcx, [rcx]
0x14003dfc0  lea     rax, FatFlushCompletionRoutine
0x14003dfc7  mov     [rcx-10h], rax
0x14003dfcb  mov     eax, esi
0x14003dfcd  mov     [rcx-8], rax
0x14003dfd1  mov     byte ptr [rcx-45h], 0E0h
0x14003dfd5  mov     rdx, r13; Irp
0x14003dfd8  mov     rcx, [rsp+0A8h+arg_10]
0x14003dfe0  mov     rcx, [rcx+88h]; DeviceObject
0x14003dfe7  call    cs:__imp_IofCallDriver
0x14003dfee  nop     dword ptr [rax+rax+00h]
0x14003dff3  cmp     eax, 103h
0x14003dff8  jz      short loc_14003E005
0x14003dffa  test    eax, eax
0x14003dffc  jns     short loc_14003E007
0x14003dffe  cmp     eax, 0C0000010h
0x14003e003  jz      short loc_14003E007
0x14003e005  mov     esi, eax
0x14003e007  mov     r13, rbx
0x14003e00a  mov     r8d, esi
0x14003e00d  mov     rdx, r13; Irp
0x14003e010  mov     rcx, r14; Entry
0x14003e013  call    FatCompleteRequest_Real
0x14003e018  mov     eax, esi
0x14003e01a  jmp     loc_14003DC21
0x14005e973  push    rbp
0x14005e975  sub     rsp, 30h
0x14005e979  mov     rbp, rdx
0x14005e97c  mov     rcx, [rcx]
0x14005e97f  mov     ecx, [rcx]; Exception
0x14005e981  call    cs:__imp_FsRtlIsNtstatusExpected
0x14005e988  nop     dword ptr [rax+rax+00h]
0x14005e98d  xor     ecx, ecx
0x14005e98f  test    al, al
0x14005e991  setnz   cl
0x14005e994  mov     eax, ecx
0x14005e996  add     rsp, 30h
0x14005e99a  pop     rbp
0x14005e99b  retn
0x14005e99d  push    rbx
0x14005e99f  push    rbp
0x14005e9a0  sub     rsp, 38h
0x14005e9a4  mov     rbp, rdx
0x14005e9a7  movzx   ebx, cl
0x14005e9aa  cmp     byte ptr [rbp+30h], 0
0x14005e9ae  jz      short loc_14005E9CB
0x14005e9b0  mov     rcx, [rbp+0C0h]
  ... truncated ...
```
