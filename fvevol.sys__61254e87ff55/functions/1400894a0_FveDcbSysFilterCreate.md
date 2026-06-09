# FveDcbSysFilterCreate

- ea: `0x1400894a0`
- end: `0x140089921`
- name: `FveDcbSysFilterCreate`
- size: `1153`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140008f04`
- `0x14000a210`
- `0x14000e0c4`
- `0x140088d8c`
- `0x1400894a0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x1400896e7`
- `ntoskrnl!IofCompleteRequest` at `0x1400896e7`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140089583`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140089583`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140089683`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140089683`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14008979e`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14008979e`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400897df`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400897df`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14008965f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14008965f`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14008964f`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14008964f`
- `ntoskrnl!SeAccessCheck` at `0x14008963d`
- `ntoskrnl!SeAccessCheck` at `0x14008963d`
- `ntoskrnl!SeLockSubjectContext` at `0x1400895e0`
- `ntoskrnl!SeLockSubjectContext` at `0x1400895e0`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400895d0`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400895d0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400895fc`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400895fc`

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
  __int64 v22; // rax
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
      v22 = BlDcbRef(a1);
      if ( v22 )
      {
        FileObject->FsContext2 = 0;
        FileObject->FsContext = (PVOID)(v20 | v22 & 0xFFFFFFFFFFFFFFFCuLL);
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
0x1400894a0  mov     [rsp-38h+arg_10], rbx
0x1400894a5  push    rbp
0x1400894a6  push    rsi
0x1400894a7  push    rdi
0x1400894a8  push    r12
0x1400894aa  push    r13
0x1400894ac  push    r14
0x1400894ae  push    r15
0x1400894b0  mov     rbp, rsp
0x1400894b3  sub     rsp, 70h
0x1400894b7  mov     r9, [rdx+0B8h]
0x1400894be  xor     edi, edi
0x1400894c0  mov     [rbp+arg_8], edi
0x1400894c3  xorps   xmm0, xmm0
0x1400894c6  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x1400894ca  mov     [rbp+arg_0], edi
0x1400894cd  mov     rbx, r8
0x1400894d0  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x1400894d4  mov     rax, [r9+8]
0x1400894d8  mov     r12, rdx
0x1400894db  mov     r13, [r9+30h]
0x1400894df  mov     rsi, rcx
0x1400894e2  mov     eax, [rax+10h]
0x1400894e5  mov     [rbp+DesiredAccess], eax
0x1400894e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400894ef  lea     rax, WPP_GLOBAL_Control
0x1400894f6  cmp     rcx, rax
0x1400894f9  jnz     loc_14008969C
0x1400894ff  test    rsi, rsi
0x140089502  jz      loc_1400896D0
0x140089508  mov     r14, [rsi+0C8h]
0x14008950f  test    r14, r14
0x140089512  jz      loc_1400896D0
0x140089518  cmp     dword ptr [rsi+0B0h], 3
0x14008951f  jnz     loc_140089849
0x140089525  cmp     dword ptr [r14+8], 1
0x14008952a  jnz     loc_1400896D0
0x140089530  mov     rax, [rsi+8]
0x140089534  test    rax, rax
0x140089537  jz      loc_1400896D0
0x14008953d  mov     r15, [rax+0C8h]
0x140089544  test    r15, r15
0x140089547  jz      loc_1400896D0
0x14008954d  mov     rcx, [rax+8]
0x140089551  test    rcx, rcx
0x140089554  jz      loc_1400896D0
0x14008955a  cmp     [rcx+0C8h], rdi
0x140089561  jz      loc_1400896D0
0x140089567  lea     rcx, [r15+8]; RemoveLock
0x14008956b  mov     [rsp+70h+RemlockSize], 20h ; ' '; RemlockSize
0x140089573  mov     r9d, 1; Line
0x140089579  lea     r8, File; File
0x140089580  mov     rdx, r15; Tag
0x140089583  call    cs:__imp_IoAcquireRemoveLockEx
0x14008958a  nop     dword ptr [rax+rax+00h]
0x14008958f  mov     [rbp+arg_0], eax
0x140089592  mov     ecx, eax
0x140089594  test    eax, eax
0x140089596  js      loc_140089692
0x14008959c  mov     rax, [r15]
0x14008959f  test    rax, rax
0x1400895a2  jz      loc_140089856
0x1400895a8  mov     rax, [r15]
0x1400895ab  test    rbx, rbx
0x1400895ae  jnz     loc_140089863
0x1400895b4  test    r13, r13
0x1400895b7  jz      loc_140089915
0x1400895bd  mov     rax, [rsi+8]
0x1400895c1  mov     rcx, [rax+8]
0x1400895c5  mov     rbx, [rcx+0C8h]
0x1400895cc  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400895d0  call    cs:__imp_SeCaptureSubjectContext
0x1400895d7  nop     dword ptr [rax+rax+00h]
0x1400895dc  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x1400895e0  call    cs:__imp_SeLockSubjectContext
0x1400895e7  nop     dword ptr [rax+rax+00h]
0x1400895ec  mov     dil, [r12+40h]
0x1400895f1  mov     [rbp+arg_0], 0C0000022h
0x1400895f8  mov     rbx, [rbx+8]
0x1400895fc  call    cs:__imp_IoGetFileObjectGenericMapping
0x140089603  nop     dword ptr [rax+rax+00h]
0x140089608  mov     r9d, [rbp+DesiredAccess]; DesiredAccess
0x14008960c  lea     rcx, [rbp+arg_0]
0x140089610  mov     [rsp+70h+AccessStatus], rcx; AccessStatus
0x140089615  lea     rdx, [rbp+SubjectContext]; SubjectSecurityContext
0x140089619  lea     rcx, [rbp+arg_8]
0x14008961d  mov     r8b, 1; SubjectContextLocked
0x140089620  mov     [rsp+70h+GrantedAccess], rcx; GrantedAccess
0x140089625  mov     rcx, rbx; SecurityDescriptor
0x140089628  mov     [rsp+70h+AccessMode], dil; AccessMode
0x14008962d  xor     edi, edi
0x14008962f  mov     [rsp+70h+GenericMapping], rax; GenericMapping
0x140089634  mov     [rsp+70h+Privileges], rdi; Privileges
0x140089639  mov     [rsp+70h+RemlockSize], edi; PreviouslyGrantedAccess
0x14008963d  call    cs:__imp_SeAccessCheck
0x140089644  nop     dword ptr [rax+rax+00h]
0x140089649  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14008964d  mov     bl, al
0x14008964f  call    cs:__imp_SeUnlockSubjectContext
0x140089656  nop     dword ptr [rax+rax+00h]
0x14008965b  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14008965f  call    cs:__imp_SeReleaseSubjectContext
0x140089666  nop     dword ptr [rax+rax+00h]
0x14008966b  mov     ecx, [rbp+arg_0]
0x14008966e  test    ecx, ecx
0x140089670  jns     loc_140089752
0x140089676  mov     r8d, 20h ; ' '; RemlockSize
0x14008967c  lea     rcx, [r15+8]; RemoveLock
0x140089680  mov     rdx, r15; Tag
0x140089683  call    cs:__imp_IoReleaseRemoveLockEx
0x14008968a  nop     dword ptr [rax+rax+00h]
0x14008968f  mov     ecx, [rbp+arg_0]
0x140089692  cmp     ecx, 0C0000002h
0x140089698  jz      short loc_1400896F6
0x14008969a  jmp     short loc_1400896D8
0x14008969c  test    dword ptr [rcx+2Ch], 400h
0x1400896a3  jz      loc_1400894FF
0x1400896a9  cmp     byte ptr [rcx+29h], 5
0x1400896ad  jb      loc_1400894FF
0x1400896b3  mov     rcx, [rcx+18h]
0x1400896b7  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x1400896be  mov     edx, 32h ; '2'
0x1400896c3  mov     r9, r13
0x1400896c6  call    WPP_SF_q
0x1400896cb  jmp     loc_1400894FF
0x1400896d0  mov     ecx, 0C000000Dh
0x1400896d5  mov     [rbp+arg_0], ecx
0x1400896d8  mov     [r12+30h], ecx
0x1400896dd  xor     edx, edx; PriorityBoost
0x1400896df  mov     rcx, r12; Irp
0x1400896e2  mov     [r12+38h], rdi
0x1400896e7  call    cs:__imp_IofCompleteRequest
0x1400896ee  nop     dword ptr [rax+rax+00h]
0x1400896f3  mov     ecx, [rbp+arg_0]
0x1400896f6  mov     r10, cs:WPP_GLOBAL_Control
0x1400896fd  lea     rax, WPP_GLOBAL_Control
0x140089704  cmp     r10, rax
0x140089707  jnz     short loc_140089724
0x140089709  mov     rbx, [rsp+70h+arg_10]
0x140089711  mov     eax, ecx
0x140089713  add     rsp, 70h
0x140089717  pop     r15
0x140089719  pop     r14
0x14008971b  pop     r13
0x14008971d  pop     r12
0x14008971f  pop     rdi
0x140089720  pop     rsi
0x140089721  pop     rbp
0x140089722  retn
0x140089724  test    dword ptr [r10+2Ch], 400h
0x14008972c  jz      short loc_140089709
0x14008972e  cmp     byte ptr [r10+29h], 5
0x140089733  jb      short loc_140089709
0x140089735  mov     r9d, ecx
0x140089738  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x14008973f  mov     rcx, [r10+18h]
0x140089743  mov     edx, 36h ; '6'
0x140089748  call    WPP_SF_d
0x14008974d  mov     ecx, [rbp+arg_0]
0x140089750  jmp     short loc_140089709
0x140089752  test    bl, bl
0x140089754  jnz     short loc_14008975E
0x140089756  mov     ecx, 0C0000022h
0x14008975b  mov     [rbp+arg_0], ecx
0x14008975e  test    ecx, ecx
0x140089760  js      loc_140089676
0x140089766  test    bl, bl
0x140089768  jz      loc_140089676
0x14008976e  mov     eax, [rbp+arg_8]
0x140089771  and     eax, 102h
0x140089776  neg     eax
0x140089778  sbb     ecx, ecx
0x14008977a  and     ecx, 3
0x14008977d  mov     ebx, ecx
0x14008977f  or      ebx, 1
0x140089782  test    byte ptr [rbp+arg_8], 81h
0x140089786  cmovz   ebx, ecx
0x140089789  test    ebx, ebx
0x14008978b  jz      loc_140089878
0x140089791  test    bl, 2
0x140089794  jz      loc_14008981B
0x14008979a  lea     rcx, [rsi+50h]; Mutex
0x14008979e  call    cs:__imp_KeAcquireGuardedMutex
0x1400897a5  nop     dword ptr [rax+rax+00h]
0x1400897aa  cmp     [r14], rdi
0x1400897ad  jnz     loc_1400898A2
0x1400897b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400897ba  lea     rax, WPP_GLOBAL_Control
0x1400897c1  cmp     rcx, rax
0x1400897c4  jz      short loc_1400897D3
0x1400897c6  test    dword ptr [rcx+2Ch], 400h
0x1400897cd  jnz     loc_1400898EA
0x1400897d3  mov     [r14], r13
0x1400897d6  xor     eax, eax
0x1400897d8  lea     rcx, [rsi+50h]; Mutex
0x1400897dc  mov     [rbp+arg_0], eax
0x1400897df  call    cs:__imp_KeReleaseGuardedMutex
0x1400897e6  nop     dword ptr [rax+rax+00h]
0x1400897eb  cmp     [rbp+arg_0], edi
0x1400897ee  jl      loc_140089676
0x1400897f4  mov     rcx, rsi
0x1400897f7  call    BlDcbRef
0x1400897fc  test    rax, rax
0x1400897ff  jz      loc_140089915
0x140089805  and     rax, 0FFFFFFFFFFFFFFFCh
0x140089809  mov     ecx, ebx
0x14008980b  or      rax, rcx
0x14008980e  mov     [r13+20h], rdi
0x140089812  mov     [r13+18h], rax
0x140089816  jmp     loc_140089676
0x14008981b  mov     rcx, cs:WPP_GLOBAL_Control
0x140089822  lea     rax, WPP_GLOBAL_Control
0x140089829  cmp     rcx, rax
0x14008982c  jz      short loc_14008983D
0x14008982e  test    dword ptr [rcx+2Ch], 400h
0x140089835  jz      short loc_14008983D
0x140089837  cmp     byte ptr [rcx+29h], 5
0x14008983b  jnb     short loc_140089884
0x14008983d  mov     [rbp+arg_0], 0C0000002h
0x140089844  jmp     loc_140089676
0x140089849  mov     ecx, 0C0000002h
0x14008984e  mov     [rbp+arg_0], ecx
0x140089851  jmp     loc_1400896F6
0x140089856  mov     ecx, 0C000000Dh
0x14008985b  mov     [rbp+arg_0], ecx
0x14008985e  jmp     loc_140089676
0x140089863  cmp     [rbx], di
0x140089866  jbe     loc_1400895B4
0x14008986c  mov     [rbp+arg_0], 0C0000034h
0x140089873  jmp     loc_140089676
0x140089878  mov     [rbp+arg_0], 0C0000022h
0x14008987f  jmp     loc_140089676
0x140089884  mov     r9, [rsi+98h]
0x14008988b  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140089892  mov     rcx, [rcx+18h]
0x140089896  mov     edx, 33h ; '3'
0x14008989b  call    WPP_SF_S
0x1400898a0  jmp     short loc_14008983D
0x1400898a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400898a9  lea     rax, WPP_GLOBAL_Control
0x1400898b0  cmp     rcx, rax
0x1400898b3  jz      short loc_1400898E0
0x1400898b5  test    dword ptr [rcx+2Ch], 400h
0x1400898bc  jz      short loc_1400898E0
0x1400898be  cmp     byte ptr [rcx+29h], 3
0x1400898c2  jb      short loc_1400898E0
0x1400898c4  mov     r9, [rsi+98h]
0x1400898cb  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x1400898d2  mov     rcx, [rcx+18h]
0x1400898d6  mov     edx, 34h ; '4'
0x1400898db  call    WPP_SF_S
0x1400898e0  mov     eax, 0C0000043h
0x1400898e5  jmp     loc_1400897D8
0x1400898ea  cmp     byte ptr [rcx+29h], 5
0x1400898ee  jb      loc_1400897D3
0x1400898f4  mov     r9, [rsi+98h]
0x1400898fb  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140089902  mov     rcx, [rcx+18h]
0x140089906  mov     edx, 35h ; '5'
0x14008990b  call    WPP_SF_S
0x140089910  jmp     loc_1400897D3
0x140089915  mov     [rbp+arg_0], 0C0000001h
0x14008991c  jmp     loc_140089676
```
