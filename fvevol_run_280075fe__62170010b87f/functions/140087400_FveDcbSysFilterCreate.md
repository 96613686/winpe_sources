# FveDcbSysFilterCreate

- ea: `0x140087400`
- end: `0x140087881`
- name: `FveDcbSysFilterCreate`
- size: `1153`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140008e44`
- `0x14000a150`
- `0x14000dedc`
- `0x140086cec`
- `0x140087400`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140087647`
- `ntoskrnl!IofCompleteRequest` at `0x140087647`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400874e3`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400874e3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400875e3`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400875e3`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400876fe`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1400876fe`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14008773f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14008773f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400875bf`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400875bf`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400875af`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400875af`
- `ntoskrnl!SeAccessCheck` at `0x14008759d`
- `ntoskrnl!SeAccessCheck` at `0x14008759d`
- `ntoskrnl!SeLockSubjectContext` at `0x140087540`
- `ntoskrnl!SeLockSubjectContext` at `0x140087540`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140087530`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140087530`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008755c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008755c`

## pseudocode

```c
__int64 __fastcall FveDcbSysFilterCreate(__int64 a1, IRP *a2, _WORD *a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r9
  PFILE_OBJECT FileObject; // r13
  __int64 v8; // r14
  __int64 v9; // rax
  _QWORD *v10; // r15
  __int64 v11; // rcx
  unsigned int v12; // ecx
  __int64 v13; // rbx
  KPROCESSOR_MODE AccessMode; // di
  void *v15; // rbx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v17; // bl
  int v18; // ecx
  unsigned int v20; // ebx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rax
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-20h] BYREF
  int AccessStatus; // [rsp+B0h] [rbp+40h] BYREF
  DWORD GrantedAccess; // [rsp+B8h] [rbp+48h] BYREF
  ACCESS_MASK DesiredAccess; // [rsp+C8h] [rbp+58h]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  GrantedAccess = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  AccessStatus = 0;
  FileObject = CurrentStackLocation->FileObject;
  DesiredAccess = *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 16);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, FileObject);
  }
  if ( !a1 )
    goto LABEL_21;
  v8 = *(_QWORD *)(a1 + 200);
  if ( !v8 )
    goto LABEL_21;
  if ( *(_DWORD *)(a1 + 176) != 3 )
  {
    v12 = -1073741822;
    AccessStatus = -1073741822;
    goto LABEL_23;
  }
  if ( *(_DWORD *)(v8 + 8) != 1
    || (v9 = *(_QWORD *)(a1 + 8)) == 0
    || (v10 = *(_QWORD **)(v9 + 200)) == 0
    || (v11 = *(_QWORD *)(v9 + 8)) == 0
    || !*(_QWORD *)(v11 + 200) )
  {
LABEL_21:
    v12 = -1073741811;
    AccessStatus = -1073741811;
LABEL_22:
    a2->IoStatus.Status = v12;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
    v12 = AccessStatus;
    goto LABEL_23;
  }
  AccessStatus = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v10 + 1), v10, File, 1u, 0x20u);
  v12 = AccessStatus;
  if ( AccessStatus >= 0 )
  {
    if ( !*v10 )
    {
      AccessStatus = -1073741811;
      goto LABEL_15;
    }
    if ( a3 && *a3 )
    {
      AccessStatus = -1073741772;
      goto LABEL_15;
    }
    if ( FileObject )
    {
      v13 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 200LL);
      SeCaptureSubjectContext(&SubjectContext);
      SeLockSubjectContext(&SubjectContext);
      AccessMode = a2->RequestorMode;
      AccessStatus = -1073741790;
      v15 = *(void **)(v13 + 8);
      GenericMapping = IoGetFileObjectGenericMapping();
      v17 = SeAccessCheck(
              v15,
              &SubjectContext,
              1u,
              DesiredAccess,
              0,
              0,
              GenericMapping,
              AccessMode,
              &GrantedAccess,
              &AccessStatus);
      SeUnlockSubjectContext(&SubjectContext);
      SeReleaseSubjectContext(&SubjectContext);
      v18 = AccessStatus;
      if ( AccessStatus < 0 )
        goto LABEL_15;
      if ( !v17 )
      {
        v18 = -1073741790;
        AccessStatus = -1073741790;
      }
      if ( v18 < 0 || !v17 )
        goto LABEL_15;
      v20 = ((GrantedAccess & 0x102) != 0 ? 2 : 0) | 1;
      if ( (GrantedAccess & 0x81) == 0 )
        v20 = (GrantedAccess & 0x102) != 0 ? 3 : 0;
      if ( !v20 )
      {
        AccessStatus = -1073741790;
        goto LABEL_15;
      }
      if ( (v20 & 2) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_S(
            WPP_GLOBAL_Control->AttachedDevice,
            51,
            WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
            *(_QWORD *)(a1 + 152));
        }
        AccessStatus = -1073741822;
        goto LABEL_15;
      }
      KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a1 + 80));
      if ( *(_QWORD *)v8 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_S(
            WPP_GLOBAL_Control->AttachedDevice,
            52,
            WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
            *(_QWORD *)(a1 + 152));
        }
        v21 = -1073741757;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_S(
            WPP_GLOBAL_Control->AttachedDevice,
            53,
            WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
            *(_QWORD *)(a1 + 152));
        }
        *(_QWORD *)v8 = FileObject;
        v21 = 0;
      }
      AccessStatus = v21;
      KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a1 + 80));
      if ( AccessStatus < 0 )
      {
LABEL_15:
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v10 + 1), v10, 0x20u);
        v12 = AccessStatus;
        goto LABEL_16;
      }
      v24 = BlDcbRef(a1, v22, v23);
      if ( v24 )
      {
        FileObject->FsContext2 = 0;
        FileObject->FsContext = (PVOID)(v20 | v24 & 0xFFFFFFFFFFFFFFFCuLL);
        goto LABEL_15;
      }
    }
    AccessStatus = -1073741823;
    goto LABEL_15;
  }
LABEL_16:
  if ( v12 != -1073741822 )
    goto LABEL_22;
LABEL_23:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, v12);
    return (unsigned int)AccessStatus;
  }
  return v12;
}

```

## disassembly

```asm
0x140087400  mov     [rsp-38h+arg_10], rbx
0x140087405  push    rbp
0x140087406  push    rsi
0x140087407  push    rdi
0x140087408  push    r12
0x14008740a  push    r13
0x14008740c  push    r14
0x14008740e  push    r15
0x140087410  mov     rbp, rsp
0x140087413  sub     rsp, 70h
0x140087417  mov     r9, [rdx+0B8h]
0x14008741e  xor     edi, edi
0x140087420  mov     [rbp+arg_8], edi
0x140087423  xorps   xmm0, xmm0
0x140087426  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14008742a  mov     [rbp+arg_0], edi
0x14008742d  mov     rbx, r8
0x140087430  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x140087434  mov     rax, [r9+8]
0x140087438  mov     r12, rdx
0x14008743b  mov     r13, [r9+30h]
0x14008743f  mov     rsi, rcx
0x140087442  mov     eax, [rax+10h]
0x140087445  mov     [rbp+DesiredAccess], eax
0x140087448  mov     rcx, cs:WPP_GLOBAL_Control
0x14008744f  lea     rax, WPP_GLOBAL_Control
0x140087456  cmp     rcx, rax
0x140087459  jnz     loc_1400875FC
0x14008745f  test    rsi, rsi
0x140087462  jz      loc_140087630
0x140087468  mov     r14, [rsi+0C8h]
0x14008746f  test    r14, r14
0x140087472  jz      loc_140087630
0x140087478  cmp     dword ptr [rsi+0B0h], 3
0x14008747f  jnz     loc_1400877A9
0x140087485  cmp     dword ptr [r14+8], 1
0x14008748a  jnz     loc_140087630
0x140087490  mov     rax, [rsi+8]
0x140087494  test    rax, rax
0x140087497  jz      loc_140087630
0x14008749d  mov     r15, [rax+0C8h]
0x1400874a4  test    r15, r15
0x1400874a7  jz      loc_140087630
0x1400874ad  mov     rcx, [rax+8]
0x1400874b1  test    rcx, rcx
0x1400874b4  jz      loc_140087630
0x1400874ba  cmp     [rcx+0C8h], rdi
0x1400874c1  jz      loc_140087630
0x1400874c7  lea     rcx, [r15+8]; RemoveLock
0x1400874cb  mov     [rsp+70h+RemlockSize], 20h ; ' '; RemlockSize
0x1400874d3  mov     r9d, 1; Line
0x1400874d9  lea     r8, File; File
0x1400874e0  mov     rdx, r15; Tag
0x1400874e3  call    cs:__imp_IoAcquireRemoveLockEx
0x1400874ea  nop     dword ptr [rax+rax+00h]
0x1400874ef  mov     [rbp+arg_0], eax
0x1400874f2  mov     ecx, eax
0x1400874f4  test    eax, eax
0x1400874f6  js      loc_1400875F2
0x1400874fc  mov     rax, [r15]
0x1400874ff  test    rax, rax
0x140087502  jz      loc_1400877B6
0x140087508  mov     rax, [r15]
0x14008750b  test    rbx, rbx
0x14008750e  jnz     loc_1400877C3
0x140087514  test    r13, r13
0x140087517  jz      loc_140087875
0x14008751d  mov     rax, [rsi+8]
0x140087521  mov     rcx, [rax+8]
0x140087525  mov     rbx, [rcx+0C8h]
0x14008752c  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140087530  call    cs:__imp_SeCaptureSubjectContext
0x140087537  nop     dword ptr [rax+rax+00h]
0x14008753c  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x140087540  call    cs:__imp_SeLockSubjectContext
0x140087547  nop     dword ptr [rax+rax+00h]
0x14008754c  mov     dil, [r12+40h]
0x140087551  mov     [rbp+arg_0], 0C0000022h
0x140087558  mov     rbx, [rbx+8]
0x14008755c  call    cs:__imp_IoGetFileObjectGenericMapping
0x140087563  nop     dword ptr [rax+rax+00h]
0x140087568  mov     r9d, [rbp+DesiredAccess]; DesiredAccess
0x14008756c  lea     rcx, [rbp+arg_0]
0x140087570  mov     [rsp+70h+AccessStatus], rcx; AccessStatus
0x140087575  lea     rdx, [rbp+SubjectContext]; SubjectSecurityContext
0x140087579  lea     rcx, [rbp+arg_8]
0x14008757d  mov     r8b, 1; SubjectContextLocked
0x140087580  mov     [rsp+70h+GrantedAccess], rcx; GrantedAccess
0x140087585  mov     rcx, rbx; SecurityDescriptor
0x140087588  mov     [rsp+70h+AccessMode], dil; AccessMode
0x14008758d  xor     edi, edi
0x14008758f  mov     [rsp+70h+GenericMapping], rax; GenericMapping
0x140087594  mov     [rsp+70h+Privileges], rdi; Privileges
0x140087599  mov     [rsp+70h+RemlockSize], edi; PreviouslyGrantedAccess
0x14008759d  call    cs:__imp_SeAccessCheck
0x1400875a4  nop     dword ptr [rax+rax+00h]
0x1400875a9  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400875ad  mov     bl, al
0x1400875af  call    cs:__imp_SeUnlockSubjectContext
0x1400875b6  nop     dword ptr [rax+rax+00h]
0x1400875bb  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400875bf  call    cs:__imp_SeReleaseSubjectContext
0x1400875c6  nop     dword ptr [rax+rax+00h]
0x1400875cb  mov     ecx, [rbp+arg_0]
0x1400875ce  test    ecx, ecx
0x1400875d0  jns     loc_1400876B2
0x1400875d6  mov     r8d, 20h ; ' '; RemlockSize
0x1400875dc  lea     rcx, [r15+8]; RemoveLock
0x1400875e0  mov     rdx, r15; Tag
0x1400875e3  call    cs:__imp_IoReleaseRemoveLockEx
0x1400875ea  nop     dword ptr [rax+rax+00h]
0x1400875ef  mov     ecx, [rbp+arg_0]
0x1400875f2  cmp     ecx, 0C0000002h
0x1400875f8  jz      short loc_140087656
0x1400875fa  jmp     short loc_140087638
0x1400875fc  test    dword ptr [rcx+2Ch], 400h
0x140087603  jz      loc_14008745F
0x140087609  cmp     byte ptr [rcx+29h], 5
0x14008760d  jb      loc_14008745F
0x140087613  mov     rcx, [rcx+18h]
0x140087617  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008761e  mov     edx, 32h ; '2'
0x140087623  mov     r9, r13
0x140087626  call    WPP_SF_q
0x14008762b  jmp     loc_14008745F
0x140087630  mov     ecx, 0C000000Dh
0x140087635  mov     [rbp+arg_0], ecx
0x140087638  mov     [r12+30h], ecx
0x14008763d  xor     edx, edx; PriorityBoost
0x14008763f  mov     rcx, r12; Irp
0x140087642  mov     [r12+38h], rdi
0x140087647  call    cs:__imp_IofCompleteRequest
0x14008764e  nop     dword ptr [rax+rax+00h]
0x140087653  mov     ecx, [rbp+arg_0]
0x140087656  mov     r10, cs:WPP_GLOBAL_Control
0x14008765d  lea     rax, WPP_GLOBAL_Control
0x140087664  cmp     r10, rax
0x140087667  jnz     short loc_140087684
0x140087669  mov     rbx, [rsp+70h+arg_10]
0x140087671  mov     eax, ecx
0x140087673  add     rsp, 70h
0x140087677  pop     r15
0x140087679  pop     r14
0x14008767b  pop     r13
0x14008767d  pop     r12
0x14008767f  pop     rdi
0x140087680  pop     rsi
0x140087681  pop     rbp
0x140087682  retn
0x140087684  test    dword ptr [r10+2Ch], 400h
0x14008768c  jz      short loc_140087669
0x14008768e  cmp     byte ptr [r10+29h], 5
0x140087693  jb      short loc_140087669
0x140087695  mov     r9d, ecx
0x140087698  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008769f  mov     rcx, [r10+18h]
0x1400876a3  mov     edx, 36h ; '6'
0x1400876a8  call    WPP_SF_d
0x1400876ad  mov     ecx, [rbp+arg_0]
0x1400876b0  jmp     short loc_140087669
0x1400876b2  test    bl, bl
0x1400876b4  jnz     short loc_1400876BE
0x1400876b6  mov     ecx, 0C0000022h
0x1400876bb  mov     [rbp+arg_0], ecx
0x1400876be  test    ecx, ecx
0x1400876c0  js      loc_1400875D6
0x1400876c6  test    bl, bl
0x1400876c8  jz      loc_1400875D6
0x1400876ce  mov     eax, [rbp+arg_8]
0x1400876d1  and     eax, 102h
0x1400876d6  neg     eax
0x1400876d8  sbb     ecx, ecx
0x1400876da  and     ecx, 3
0x1400876dd  mov     ebx, ecx
0x1400876df  or      ebx, 1
0x1400876e2  test    byte ptr [rbp+arg_8], 81h
0x1400876e6  cmovz   ebx, ecx
0x1400876e9  test    ebx, ebx
0x1400876eb  jz      loc_1400877D8
0x1400876f1  test    bl, 2
0x1400876f4  jz      loc_14008777B
0x1400876fa  lea     rcx, [rsi+50h]; Mutex
0x1400876fe  call    cs:__imp_KeAcquireGuardedMutex
0x140087705  nop     dword ptr [rax+rax+00h]
0x14008770a  cmp     [r14], rdi
0x14008770d  jnz     loc_140087802
0x140087713  mov     rcx, cs:WPP_GLOBAL_Control
0x14008771a  lea     rax, WPP_GLOBAL_Control
0x140087721  cmp     rcx, rax
0x140087724  jz      short loc_140087733
0x140087726  test    dword ptr [rcx+2Ch], 400h
0x14008772d  jnz     loc_14008784A
0x140087733  mov     [r14], r13
0x140087736  xor     eax, eax
0x140087738  lea     rcx, [rsi+50h]; Mutex
0x14008773c  mov     [rbp+arg_0], eax
0x14008773f  call    cs:__imp_KeReleaseGuardedMutex
0x140087746  nop     dword ptr [rax+rax+00h]
0x14008774b  cmp     [rbp+arg_0], edi
0x14008774e  jl      loc_1400875D6
0x140087754  mov     rcx, rsi
0x140087757  call    BlDcbRef
0x14008775c  test    rax, rax
0x14008775f  jz      loc_140087875
0x140087765  and     rax, 0FFFFFFFFFFFFFFFCh
0x140087769  mov     ecx, ebx
0x14008776b  or      rax, rcx
0x14008776e  mov     [r13+20h], rdi
0x140087772  mov     [r13+18h], rax
0x140087776  jmp     loc_1400875D6
0x14008777b  mov     rcx, cs:WPP_GLOBAL_Control
0x140087782  lea     rax, WPP_GLOBAL_Control
0x140087789  cmp     rcx, rax
0x14008778c  jz      short loc_14008779D
0x14008778e  test    dword ptr [rcx+2Ch], 400h
0x140087795  jz      short loc_14008779D
0x140087797  cmp     byte ptr [rcx+29h], 5
0x14008779b  jnb     short loc_1400877E4
0x14008779d  mov     [rbp+arg_0], 0C0000002h
0x1400877a4  jmp     loc_1400875D6
0x1400877a9  mov     ecx, 0C0000002h
0x1400877ae  mov     [rbp+arg_0], ecx
0x1400877b1  jmp     loc_140087656
0x1400877b6  mov     ecx, 0C000000Dh
0x1400877bb  mov     [rbp+arg_0], ecx
0x1400877be  jmp     loc_1400875D6
0x1400877c3  cmp     [rbx], di
0x1400877c6  jbe     loc_140087514
0x1400877cc  mov     [rbp+arg_0], 0C0000034h
0x1400877d3  jmp     loc_1400875D6
0x1400877d8  mov     [rbp+arg_0], 0C0000022h
0x1400877df  jmp     loc_1400875D6
0x1400877e4  mov     r9, [rsi+98h]
0x1400877eb  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x1400877f2  mov     rcx, [rcx+18h]
0x1400877f6  mov     edx, 33h ; '3'
0x1400877fb  call    WPP_SF_S
0x140087800  jmp     short loc_14008779D
0x140087802  mov     rcx, cs:WPP_GLOBAL_Control
0x140087809  lea     rax, WPP_GLOBAL_Control
0x140087810  cmp     rcx, rax
0x140087813  jz      short loc_140087840
0x140087815  test    dword ptr [rcx+2Ch], 400h
0x14008781c  jz      short loc_140087840
0x14008781e  cmp     byte ptr [rcx+29h], 3
0x140087822  jb      short loc_140087840
0x140087824  mov     r9, [rsi+98h]
0x14008782b  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140087832  mov     rcx, [rcx+18h]
0x140087836  mov     edx, 34h ; '4'
0x14008783b  call    WPP_SF_S
0x140087840  mov     eax, 0C0000043h
0x140087845  jmp     loc_140087738
0x14008784a  cmp     byte ptr [rcx+29h], 5
0x14008784e  jb      loc_140087733
0x140087854  mov     r9, [rsi+98h]
0x14008785b  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140087862  mov     rcx, [rcx+18h]
0x140087866  mov     edx, 35h ; '5'
0x14008786b  call    WPP_SF_S
0x140087870  jmp     loc_140087733
0x140087875  mov     [rbp+arg_0], 0C0000001h
0x14008787c  jmp     loc_1400875D6
```
