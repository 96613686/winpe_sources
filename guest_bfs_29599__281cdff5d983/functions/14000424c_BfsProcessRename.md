# BfsProcessRename

- ea: `0x14000424c`
- end: `0x14000448d`
- name: `BfsProcessRename`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003270`

## callees

- `0x140001008`
- `0x140003340`
- `0x14000424c`
- `0x140005edc`
- `0x140013860`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x140004400`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140004400`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140004411`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x140004411`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000444a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000444a`
- `ntoskrnl!IoGetCurrentProcess` at `0x140004308`
- `ntoskrnl!IoGetCurrentProcess` at `0x140004308`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140004317`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140004317`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400042f1`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400042f1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400042aa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140004437`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400042aa`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140004437`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400042bd`
- `ntoskrnl!ExAcquireRundownProtection` at `0x1400042bd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400042cc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004456`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400042cc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140004456`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140004426`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140004426`
- `FLTMGR!FltParseFileNameInformation` at `0x1400043c3`
- `FLTMGR!FltParseFileNameInformation` at `0x1400043c3`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140004378`
- `FLTMGR!FltGetDestinationFileNameInformation` at `0x140004378`

## pseudocode

```c
__int64 __fastcall BfsProcessRename(PFLT_CALLBACK_DATA Data, __int64 a2)
{
  bool v2; // zf
  unsigned int v6; // ebx
  BOOLEAN v7; // r12
  PACCESS_TOKEN v8; // rdi
  char v9; // r15
  struct _KPROCESS *CurrentProcess; // rax
  NTSTATUS DestinationFileNameInformation; // ecx
  int v12; // r8d
  int v13; // r9d
  int FileNameLength; // [rsp+20h] [rbp-39h]
  unsigned __int8 EffectiveOnly; // [rsp+40h] [rbp-19h] BYREF
  unsigned __int8 CopyOnOpen[3]; // [rsp+41h] [rbp-18h] BYREF
  NTSTATUS v17; // [rsp+44h] [rbp-15h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+48h] [rbp-11h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+58h] [rbp-1h] BYREF
  NTSTATUS *v21; // [rsp+78h] [rbp+1Fh]
  __int64 v22; // [rsp+80h] [rbp+27h]

  v2 = Data->RequestorMode == 0;
  CopyOnOpen[0] = 0;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityAnonymous;
  FileNameInformation = 0;
  if ( v2 )
    return 1;
  v6 = 1;
  KeEnterCriticalRegion();
  v7 = ExAcquireRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( v7 )
  {
    v8 = PsReferenceImpersonationToken(Data->Thread, CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
    if ( v8 )
    {
      v9 = 1;
      if ( ImpersonationLevel < SecurityImpersonation )
        goto LABEL_16;
    }
    else
    {
      v9 = 0;
      CurrentProcess = IoGetCurrentProcess();
      v8 = PsReferencePrimaryToken(CurrentProcess);
    }
    if ( BfsIsApplicableToken(v8, 1) )
    {
      DestinationFileNameInformation = FltGetDestinationFileNameInformation(
                                         *(PFLT_INSTANCE *)(a2 + 24),
                                         Data->Iopb->TargetFileObject,
                                         *((HANDLE *)Data->Iopb->Parameters.Create.EaBuffer + 1),
                                         (PWSTR)Data->Iopb->Parameters.Create.EaBuffer + 10,
                                         *((_DWORD *)Data->Iopb->Parameters.Create.EaBuffer + 4),
                                         0x101u,
                                         &FileNameInformation);
      if ( DestinationFileNameInformation < 0
        || (DestinationFileNameInformation = FltParseFileNameInformation(FileNameInformation),
            DestinationFileNameInformation < 0) )
      {
        if ( (unsigned int)dword_140019000 > 3 )
        {
          v17 = DestinationFileNameInformation;
          v21 = &v17;
          v22 = 4;
          tlgWriteTransfer_EtwWriteTransfer(
            DestinationFileNameInformation,
            (int)&byte_140016D91,
            v12,
            v13,
            FileNameLength,
            &v20);
        }
      }
      else
      {
        v6 = BfsCheckPolicyAndPerformRenameAsUser(
               *(PVOID *)(a2 + 8),
               *(PVOID *)(a2 + 24),
               v8,
               Data,
               (__int64)FileNameInformation);
      }
    }
    if ( !v8 )
      goto LABEL_17;
    if ( !v9 )
    {
      PsDereferencePrimaryToken(v8);
      goto LABEL_17;
    }
LABEL_16:
    PsDereferenceImpersonationToken(v8);
  }
LABEL_17:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  if ( v7 )
  {
    KeEnterCriticalRegion();
    ExReleaseRundownProtection(&gBfsRundownProtection);
    KeLeaveCriticalRegion();
  }
  return v6;
}

```

## disassembly

```asm
0x14000424c  mov     [rsp-8+arg_10], rbx
0x140004251  mov     [rsp-8+arg_18], rsi
0x140004256  push    rbp
0x140004257  push    rdi
0x140004258  push    r12
0x14000425a  push    r14
0x14000425c  push    r15
0x14000425e  lea     rbp, [rsp-37h]
0x140004263  sub     rsp, 90h
0x14000426a  mov     rax, cs:__security_cookie
0x140004271  xor     rax, rsp
0x140004274  mov     [rbp+57h+var_28], rax
0x140004278  cmp     byte ptr [rcx+50h], 0
0x14000427c  mov     r14, rdx
0x14000427f  mov     rsi, rcx
0x140004282  mov     [rbp+57h+CopyOnOpen], 0
0x140004286  mov     [rbp+57h+EffectiveOnly], 0
0x14000428a  mov     [rbp+57h+ImpersonationLevel], 0
0x140004291  mov     [rbp+57h+FileNameInformation], 0
0x140004299  jnz     short loc_1400042A5
0x14000429b  mov     eax, 1
0x1400042a0  jmp     loc_140004464
0x1400042a5  mov     ebx, 1
0x1400042aa  call    cs:__imp_KeEnterCriticalRegion
0x1400042b1  nop     dword ptr [rax+rax+00h]
0x1400042b6  lea     rcx, gBfsRundownProtection; RunRef
0x1400042bd  call    cs:__imp_ExAcquireRundownProtection
0x1400042c4  nop     dword ptr [rax+rax+00h]
0x1400042c9  mov     r12b, al
0x1400042cc  call    cs:__imp_KeLeaveCriticalRegion
0x1400042d3  nop     dword ptr [rax+rax+00h]
0x1400042d8  test    r12b, r12b
0x1400042db  jz      loc_14000441D
0x1400042e1  mov     rcx, [rsi+8]; Thread
0x1400042e5  lea     r9, [rbp+57h+ImpersonationLevel]; ImpersonationLevel
0x1400042e9  lea     r8, [rbp+57h+EffectiveOnly]; EffectiveOnly
0x1400042ed  lea     rdx, [rbp+57h+CopyOnOpen]; CopyOnOpen
0x1400042f1  call    cs:__imp_PsReferenceImpersonationToken
0x1400042f8  nop     dword ptr [rax+rax+00h]
0x1400042fd  mov     rdi, rax
0x140004300  test    rax, rax
0x140004303  jnz     short loc_140004328
0x140004305  xor     r15b, r15b
0x140004308  call    cs:__imp_IoGetCurrentProcess
0x14000430f  nop     dword ptr [rax+rax+00h]
0x140004314  mov     rcx, rax; Process
0x140004317  call    cs:__imp_PsReferencePrimaryToken
0x14000431e  nop     dword ptr [rax+rax+00h]
0x140004323  mov     rdi, rax
0x140004326  jmp     short loc_140004335
0x140004328  cmp     [rbp+57h+ImpersonationLevel], 2
0x14000432c  mov     r15b, bl
0x14000432f  jl      loc_14000440E
0x140004335  mov     dl, bl
0x140004337  mov     rcx, rdi; Object
0x14000433a  call    BfsIsApplicableToken
0x14000433f  test    al, al
0x140004341  jz      loc_1400043F3
0x140004347  mov     rdx, [rsi+10h]
0x14000434b  lea     rax, [rbp+57h+FileNameInformation]
0x14000434f  mov     rcx, [r14+18h]; Instance
0x140004353  mov     [rsp+0B0h+RetFileNameInformation], rax; RetFileNameInformation
0x140004358  mov     [rsp+0B0h+NameOptions], 101h; NameOptions
0x140004360  mov     r8, [rdx+38h]
0x140004364  mov     rdx, [rdx+8]; FileObject
0x140004368  mov     eax, [r8+10h]
0x14000436c  lea     r9, [r8+14h]; FileName
0x140004370  mov     r8, [r8+8]; RootDirectory
0x140004374  mov     [rsp+0B0h+FileNameLength], eax; int
0x140004378  call    cs:__imp_FltGetDestinationFileNameInformation
0x14000437f  nop     dword ptr [rax+rax+00h]
0x140004384  mov     ecx, eax; int
0x140004386  test    eax, eax
0x140004388  jns     short loc_1400043BF
0x14000438a  mov     eax, cs:dword_140019000
0x140004390  cmp     eax, 3
0x140004393  jbe     short loc_1400043F3
0x140004395  lea     rax, [rbp+57h+var_6C]
0x140004399  mov     [rbp+57h+var_6C], ecx
0x14000439c  mov     [rbp+57h+var_38], rax
0x1400043a0  lea     rdx, byte_140016D91; int
0x1400043a7  lea     rax, [rbp+57h+var_58]
0x1400043ab  mov     [rbp+57h+var_30], 4
0x1400043b3  mov     qword ptr [rsp+0B0h+NameOptions], rax; PEVENT_DATA_DESCRIPTOR
0x1400043b8  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400043bd  jmp     short loc_1400043F3
0x1400043bf  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x1400043c3  call    cs:__imp_FltParseFileNameInformation
0x1400043ca  nop     dword ptr [rax+rax+00h]
0x1400043cf  mov     ecx, eax
0x1400043d1  test    eax, eax
0x1400043d3  js      short loc_14000438A
0x1400043d5  mov     rax, [rbp+57h+FileNameInformation]
0x1400043d9  mov     r9, rsi; Data
0x1400043dc  mov     rdx, [r14+18h]; PVOID
0x1400043e0  mov     r8, rdi; Token
0x1400043e3  mov     rcx, [r14+8]; FltObject
0x1400043e7  mov     qword ptr [rsp+0B0h+FileNameLength], rax; __int64
0x1400043ec  call    BfsCheckPolicyAndPerformRenameAsUser
0x1400043f1  mov     ebx, eax
0x1400043f3  test    rdi, rdi
0x1400043f6  jz      short loc_14000441D
0x1400043f8  test    r15b, r15b
0x1400043fb  jnz     short loc_14000440E
0x1400043fd  mov     rcx, rdi; PrimaryToken
0x140004400  call    cs:__imp_PsDereferencePrimaryToken
0x140004407  nop     dword ptr [rax+rax+00h]
0x14000440c  jmp     short loc_14000441D
0x14000440e  mov     rcx, rdi; ImpersonationToken
0x140004411  call    cs:__imp_PsDereferenceImpersonationToken
0x140004418  nop     dword ptr [rax+rax+00h]
0x14000441d  mov     rcx, [rbp+57h+FileNameInformation]; FileNameInformation
0x140004421  test    rcx, rcx
0x140004424  jz      short loc_140004432
0x140004426  call    cs:__imp_FltReleaseFileNameInformation
0x14000442d  nop     dword ptr [rax+rax+00h]
0x140004432  test    r12b, r12b
0x140004435  jz      short loc_140004462
0x140004437  call    cs:__imp_KeEnterCriticalRegion
0x14000443e  nop     dword ptr [rax+rax+00h]
0x140004443  lea     rcx, gBfsRundownProtection; RunRef
0x14000444a  call    cs:__imp_ExReleaseRundownProtection
0x140004451  nop     dword ptr [rax+rax+00h]
0x140004456  call    cs:__imp_KeLeaveCriticalRegion
0x14000445d  nop     dword ptr [rax+rax+00h]
0x140004462  mov     eax, ebx
0x140004464  mov     rcx, [rbp+57h+var_28]
0x140004468  xor     rcx, rsp; StackCookie
0x14000446b  call    __security_check_cookie
0x140004470  lea     r11, [rsp+0B0h+var_20]
0x140004478  mov     rbx, [r11+40h]
0x14000447c  mov     rsi, [r11+48h]
0x140004480  mov     rsp, r11
0x140004483  pop     r15
0x140004485  pop     r14
0x140004487  pop     r12
0x140004489  pop     rdi
0x14000448a  pop     rbp
0x14000448b  retn
```
