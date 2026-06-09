# FveDcbXeiFilterCreate

- ea: `0x140086e00`
- end: `0x1400873ee`
- name: `FveDcbXeiFilterCreate`
- size: `1518`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140008e44`
- `0x14000a150`
- `0x14000de4c`
- `0x14000dedc`
- `0x140086cec`
- `0x140086e00`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14008707c`
- `ntoskrnl!IofCompleteRequest` at `0x14008707c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140086efa`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140086efa`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140087055`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140087055`
- `ntoskrnl!ObGetObjectSecurity` at `0x140086f5e`
- `ntoskrnl!ObGetObjectSecurity` at `0x140086f5e`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1400870ee`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140087225`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1400870ee`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x140087225`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140087198`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140087198`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400871d1`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1400871d1`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14008700d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14008700d`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140086ffd`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140086ffd`
- `ntoskrnl!SeAccessCheck` at `0x140086feb`
- `ntoskrnl!SeAccessCheck` at `0x140086feb`
- `ntoskrnl!SeLockSubjectContext` at `0x140086f8e`
- `ntoskrnl!SeLockSubjectContext` at `0x140086f8e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140086f7e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140086f7e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140086fa5`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140086fa5`

## pseudocode

```c
__int64 __fastcall FveDcbXeiFilterCreate(__int64 a1, IRP *a2, _WORD *a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r9
  PIO_SECURITY_CONTEXT SecurityContext; // rax
  PFILE_OBJECT FileObject; // r15
  ACCESS_MASK DesiredAccess; // r12d
  __int64 v10; // rsi
  __int64 v11; // rbx
  __int64 *v12; // rbx
  int v13; // r14d
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // r14
  KPROCESSOR_MODE AccessMode; // bl
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v19; // bl
  unsigned int v21; // ebx
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rax
  DWORD GrantedAccess; // [rsp+50h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-11h] BYREF
  PVOID Tag; // [rsp+60h] [rbp-9h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int8 MemoryAllocated; // [rsp+D0h] [rbp+67h] BYREF
  int AccessStatus; // [rsp+D8h] [rbp+6Fh] BYREF
  int v31; // [rsp+E8h] [rbp+7Fh]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  GrantedAccess = 0;
  SecurityDescriptor = 0;
  MemoryAllocated = 0;
  AccessStatus = 0;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  FileObject = CurrentStackLocation->FileObject;
  Tag = 0;
  v31 = 0;
  DesiredAccess = SecurityContext->DesiredAccess;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, FileObject);
  }
  if ( !a1 )
    goto LABEL_44;
  v10 = *(_QWORD *)(a1 + 200);
  if ( !v10 )
    goto LABEL_44;
  if ( *(_DWORD *)(a1 + 176) != 3 )
  {
    v14 = -1073741822;
    goto LABEL_42;
  }
  if ( (*(_DWORD *)(v10 + 8) & 0xFFFFFFFD) != 0
    || (v11 = *(_QWORD *)(a1 + 8)) == 0
    || (v12 = *(__int64 **)(v11 + 200)) == 0 )
  {
LABEL_44:
    v14 = -1073741811;
    goto LABEL_42;
  }
  if ( a3 && *a3 )
  {
    v14 = -1073741772;
    goto LABEL_42;
  }
  v13 = 1;
  Tag = v12;
  AccessStatus = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v12 + 1), v12, File, 1u, 0x20u);
  v14 = AccessStatus;
  if ( AccessStatus < 0 )
    goto LABEL_17;
  v15 = *v12;
  v31 = 1;
  if ( !v15 )
  {
    v14 = -1073741811;
    goto LABEL_43;
  }
  v16 = *v12;
  if ( !FileObject )
  {
    v14 = -1073741823;
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_LS(
      WPP_GLOBAL_Control->AttachedDevice,
      44,
      (unsigned int)WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
      *((_DWORD *)v12 + 10),
      *(_QWORD *)(a1 + 152));
  }
  AccessStatus = ObGetObjectSecurity(*(PVOID *)(v16 + 120), &SecurityDescriptor, &MemoryAllocated);
  v14 = AccessStatus;
  if ( AccessStatus < 0 )
    goto LABEL_17;
  SeCaptureSubjectContext(&SubjectContext);
  SeLockSubjectContext(&SubjectContext);
  AccessMode = a2->RequestorMode;
  AccessStatus = -1073741790;
  GenericMapping = IoGetFileObjectGenericMapping();
  v19 = SeAccessCheck(
          SecurityDescriptor,
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
  v14 = AccessStatus;
  if ( AccessStatus < 0 )
    goto LABEL_17;
  if ( !v19 )
  {
    v14 = -1073741790;
    AccessStatus = -1073741790;
  }
  if ( v14 < 0 || !v19 )
    goto LABEL_17;
  if ( SecurityDescriptor )
  {
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated);
    SecurityDescriptor = 0;
  }
  v21 = ((GrantedAccess & 0x102) != 0 ? 2 : 0) | 1;
  if ( (GrantedAccess & 0x81) == 0 )
    v21 = (GrantedAccess & 0x102) != 0 ? 3 : 0;
  if ( !v21 )
  {
    v14 = -1073741790;
LABEL_42:
    v13 = v31;
    goto LABEL_43;
  }
  if ( (v21 & 2) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_S(
        WPP_GLOBAL_Control->AttachedDevice,
        45,
        WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
        *(_QWORD *)(a1 + 152));
    }
    v14 = -1073741822;
LABEL_40:
    v13 = v31;
LABEL_43:
    AccessStatus = v14;
    goto LABEL_18;
  }
  if ( *(_DWORD *)(v16 + 16) == 2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_S(
        WPP_GLOBAL_Control->AttachedDevice,
        46,
        WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
        *(_QWORD *)(a1 + 152));
    }
    v14 = -1071579084;
    goto LABEL_40;
  }
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a1 + 80));
  if ( *(_QWORD *)v10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      WPP_SF_S(
        WPP_GLOBAL_Control->AttachedDevice,
        47,
        WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
        *(_QWORD *)(a1 + 152));
    }
    v22 = -1073741757;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_S(
        WPP_GLOBAL_Control->AttachedDevice,
        48,
        WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids,
        *(_QWORD *)(a1 + 152));
    }
    *(_QWORD *)v10 = FileObject;
    v22 = 0;
  }
  AccessStatus = v22;
  KeReleaseGuardedMutex((PKGUARDED_MUTEX)(a1 + 80));
  v14 = AccessStatus;
  if ( AccessStatus < 0 )
  {
LABEL_17:
    v13 = v31;
    goto LABEL_18;
  }
  v24 = BlDcbRef(a1, v23, 0);
  v13 = v31;
  if ( !v24 )
  {
    v14 = -1073741823;
    goto LABEL_43;
  }
  FileObject->FsContext2 = 0;
  FileObject->FsContext = (PVOID)(v21 | v24 & 0xFFFFFFFFFFFFFFFCuLL);
  v14 = AccessStatus;
LABEL_18:
  if ( SecurityDescriptor )
  {
    ObReleaseObjectSecurity(SecurityDescriptor, MemoryAllocated);
    v14 = AccessStatus;
    SecurityDescriptor = 0;
  }
  if ( v13 )
  {
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)Tag + 8), Tag, 0x20u);
    v14 = AccessStatus;
  }
  if ( v14 != -1073741822 )
  {
    a2->IoStatus.Status = v14;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
    v14 = AccessStatus;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids, (unsigned int)v14);
    return (unsigned int)AccessStatus;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140086e00  mov     [rsp-8+arg_10], rbx
0x140086e05  push    rbp
0x140086e06  push    rsi
0x140086e07  push    rdi
0x140086e08  push    r12
0x140086e0a  push    r13
0x140086e0c  push    r14
0x140086e0e  push    r15
0x140086e10  lea     rbp, [rsp-27h]
0x140086e15  sub     rsp, 90h
0x140086e1c  mov     r9, [rdx+0B8h]
0x140086e23  xorps   xmm0, xmm0
0x140086e26  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x140086e2a  mov     r14, r8
0x140086e2d  xor     r8d, r8d
0x140086e30  mov     [rbp+57h+var_70], r8d
0x140086e34  mov     r13, rdx
0x140086e37  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x140086e3b  mov     [rbp+57h+SecurityDescriptor], r8
0x140086e3f  mov     rdi, rcx
0x140086e42  mov     [rbp+57h+MemoryAllocated], r8b
0x140086e46  mov     [rbp+57h+arg_8], r8d
0x140086e4a  mov     rax, [r9+8]
0x140086e4e  mov     r15, [r9+30h]
0x140086e52  mov     [rbp+57h+Tag], r8
0x140086e56  mov     [rbp+57h+arg_18], r8d
0x140086e5a  mov     r12d, [rax+10h]
0x140086e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140086e65  lea     rax, WPP_GLOBAL_Control
0x140086e6c  cmp     rcx, rax
0x140086e6f  jz      short loc_140086E7E
0x140086e71  test    dword ptr [rcx+2Ch], 400h
0x140086e78  jnz     loc_140087240
0x140086e7e  test    rdi, rdi
0x140086e81  jz      loc_140087168
0x140086e87  mov     rsi, [rdi+0C8h]
0x140086e8e  test    rsi, rsi
0x140086e91  jz      loc_140087168
0x140086e97  cmp     dword ptr [rdi+0B0h], 3
0x140086e9e  jnz     loc_14008726A
0x140086ea4  test    dword ptr [rsi+8], 0FFFFFFFDh
0x140086eab  jnz     loc_140087168
0x140086eb1  mov     rbx, [rdi+8]
0x140086eb5  test    rbx, rbx
0x140086eb8  jz      loc_140087168
0x140086ebe  mov     rbx, [rbx+0C8h]
0x140086ec5  test    rbx, rbx
0x140086ec8  jz      loc_140087168
0x140086ece  test    r14, r14
0x140086ed1  jnz     loc_140087274
0x140086ed7  mov     r14d, 1
0x140086edd  mov     [rbp+57h+Tag], rbx
0x140086ee1  mov     r9d, r14d; Line
0x140086ee4  mov     [rsp+0C0h+RemlockSize], 20h ; ' '; RemlockSize
0x140086eec  lea     rcx, [rbx+8]; RemoveLock
0x140086ef0  mov     rdx, rbx; Tag
0x140086ef3  lea     r8, File; File
0x140086efa  call    cs:__imp_IoAcquireRemoveLockEx
0x140086f01  nop     dword ptr [rax+rax+00h]
0x140086f06  xor     r8d, r8d
0x140086f09  mov     [rbp+57h+arg_8], eax
0x140086f0c  mov     ecx, eax
0x140086f0e  test    eax, eax
0x140086f10  js      loc_140087027
0x140086f16  mov     rax, [rbx]
0x140086f19  mov     [rbp+57h+arg_18], r14d
0x140086f1d  test    rax, rax
0x140086f20  jz      loc_140087288
0x140086f26  mov     r14, [rbx]
0x140086f29  test    r15, r15
0x140086f2c  jz      loc_140087292
0x140086f32  mov     rcx, cs:WPP_GLOBAL_Control
0x140086f39  lea     rax, WPP_GLOBAL_Control
0x140086f40  cmp     rcx, rax
0x140086f43  jz      short loc_140086F52
0x140086f45  test    dword ptr [rcx+2Ch], 400h
0x140086f4c  jnz     loc_14008729C
0x140086f52  mov     rcx, [r14+78h]; Object
0x140086f56  lea     r8, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x140086f5a  lea     rdx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140086f5e  call    cs:__imp_ObGetObjectSecurity
0x140086f65  nop     dword ptr [rax+rax+00h]
0x140086f6a  xor     r8d, r8d
0x140086f6d  mov     [rbp+57h+arg_8], eax
0x140086f70  mov     ecx, eax
0x140086f72  test    eax, eax
0x140086f74  js      loc_140087027
0x140086f7a  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140086f7e  call    cs:__imp_SeCaptureSubjectContext
0x140086f85  nop     dword ptr [rax+rax+00h]
0x140086f8a  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140086f8e  call    cs:__imp_SeLockSubjectContext
0x140086f95  nop     dword ptr [rax+rax+00h]
0x140086f9a  mov     bl, [r13+40h]
0x140086f9e  mov     [rbp+57h+arg_8], 0C0000022h
0x140086fa5  call    cs:__imp_IoGetFileObjectGenericMapping
0x140086fac  nop     dword ptr [rax+rax+00h]
0x140086fb1  lea     rcx, [rbp+57h+arg_8]
0x140086fb5  mov     r9d, r12d; DesiredAccess
0x140086fb8  mov     [rsp+0C0h+AccessStatus], rcx; AccessStatus
0x140086fbd  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x140086fc1  lea     rcx, [rbp+57h+var_70]
0x140086fc5  mov     r8b, 1; SubjectContextLocked
0x140086fc8  mov     [rsp+0C0h+GrantedAccess], rcx; GrantedAccess
0x140086fcd  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140086fd1  mov     [rsp+0C0h+AccessMode], bl; AccessMode
0x140086fd5  mov     [rsp+0C0h+GenericMapping], rax; GenericMapping
0x140086fda  mov     [rsp+0C0h+Privileges], 0; Privileges
0x140086fe3  mov     [rsp+0C0h+RemlockSize], 0; PreviouslyGrantedAccess
0x140086feb  call    cs:__imp_SeAccessCheck
0x140086ff2  nop     dword ptr [rax+rax+00h]
0x140086ff7  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140086ffb  mov     bl, al
0x140086ffd  call    cs:__imp_SeUnlockSubjectContext
0x140087004  nop     dword ptr [rax+rax+00h]
0x140087009  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14008700d  call    cs:__imp_SeReleaseSubjectContext
0x140087014  nop     dword ptr [rax+rax+00h]
0x140087019  mov     ecx, [rbp+57h+arg_8]
0x14008701c  xor     r8d, r8d
0x14008701f  test    ecx, ecx
0x140087021  jns     loc_1400870C3
0x140087027  mov     r14d, [rbp+57h+arg_18]
0x14008702b  lea     rbx, WPP_GLOBAL_Control
0x140087032  mov     rax, [rbp+57h+SecurityDescriptor]
0x140087036  test    rax, rax
0x140087039  jnz     loc_14008721F
0x14008703f  test    r14d, r14d
0x140087042  jz      short loc_140087067
0x140087044  mov     rax, [rbp+57h+Tag]
0x140087048  mov     r8d, 20h ; ' '; RemlockSize
0x14008704e  mov     rdx, rax; Tag
0x140087051  lea     rcx, [rax+8]; RemoveLock
0x140087055  call    cs:__imp_IoReleaseRemoveLockEx
0x14008705c  nop     dword ptr [rax+rax+00h]
0x140087061  mov     ecx, [rbp+57h+arg_8]
0x140087064  xor     r8d, r8d
0x140087067  cmp     ecx, 0C0000002h
0x14008706d  jz      short loc_14008708B
0x14008706f  mov     [r13+30h], ecx
0x140087073  xor     edx, edx; PriorityBoost
0x140087075  mov     rcx, r13; Irp
0x140087078  mov     [r13+38h], r8
0x14008707c  call    cs:__imp_IofCompleteRequest
0x140087083  nop     dword ptr [rax+rax+00h]
0x140087088  mov     ecx, [rbp+57h+arg_8]
0x14008708b  mov     r10, cs:WPP_GLOBAL_Control
0x140087092  cmp     r10, rbx
0x140087095  jz      short loc_1400870A5
0x140087097  test    dword ptr [r10+2Ch], 400h
0x14008709f  jnz     loc_1400873C3
0x1400870a5  mov     rbx, [rsp+0C0h+arg_10]
0x1400870ad  mov     eax, ecx
0x1400870af  add     rsp, 90h
0x1400870b6  pop     r15
0x1400870b8  pop     r14
0x1400870ba  pop     r13
0x1400870bc  pop     r12
0x1400870be  pop     rdi
0x1400870bf  pop     rsi
0x1400870c0  pop     rbp
0x1400870c1  retn
0x1400870c3  test    bl, bl
0x1400870c5  jnz     short loc_1400870CF
0x1400870c7  mov     ecx, 0C0000022h
0x1400870cc  mov     [rbp+57h+arg_8], ecx
0x1400870cf  test    ecx, ecx
0x1400870d1  js      loc_140087027
0x1400870d7  test    bl, bl
0x1400870d9  jz      loc_140087027
0x1400870df  mov     rax, [rbp+57h+SecurityDescriptor]
0x1400870e3  test    rax, rax
0x1400870e6  jz      short loc_140087101
0x1400870e8  mov     dl, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x1400870eb  mov     rcx, rax; SecurityDescriptor
0x1400870ee  call    cs:__imp_ObReleaseObjectSecurity
0x1400870f5  nop     dword ptr [rax+rax+00h]
0x1400870fa  xor     r8d, r8d
0x1400870fd  mov     [rbp+57h+SecurityDescriptor], r8
0x140087101  mov     eax, [rbp+57h+var_70]
0x140087104  and     eax, 102h
0x140087109  neg     eax
0x14008710b  sbb     ecx, ecx
0x14008710d  and     ecx, 3
0x140087110  mov     ebx, ecx
0x140087112  or      ebx, 1
0x140087115  test    byte ptr [rbp+57h+var_70], 81h
0x140087119  cmovz   ebx, ecx
0x14008711c  test    ebx, ebx
0x14008711e  jz      short loc_140087150
0x140087120  test    bl, 2
0x140087123  jnz     short loc_14008716F
0x140087125  mov     rcx, cs:WPP_GLOBAL_Control
0x14008712c  lea     rbx, WPP_GLOBAL_Control
0x140087133  cmp     rcx, rbx
0x140087136  jz      short loc_140087145
0x140087138  test    dword ptr [rcx+2Ch], 400h
0x14008713f  jnz     loc_1400872D0
0x140087145  mov     ecx, 0C0000002h
0x14008714a  mov     r14d, [rbp+57h+arg_18]
0x14008714e  jmp     short loc_140087160
0x140087150  mov     ecx, 0C0000022h
0x140087155  mov     r14d, [rbp+57h+arg_18]
0x140087159  lea     rbx, WPP_GLOBAL_Control
0x140087160  mov     [rbp+57h+arg_8], ecx
0x140087163  jmp     loc_140087032
0x140087168  mov     ecx, 0C000000Dh
0x14008716d  jmp     short loc_140087155
0x14008716f  cmp     dword ptr [r14+10h], 2
0x140087174  jnz     short loc_140087194
0x140087176  mov     rcx, cs:WPP_GLOBAL_Control
0x14008717d  lea     rbx, WPP_GLOBAL_Control
0x140087184  cmp     rcx, rbx
0x140087187  jnz     loc_1400872FE
0x14008718d  mov     ecx, 0C0210034h
0x140087192  jmp     short loc_14008714A
0x140087194  lea     rcx, [rdi+50h]; Mutex
0x140087198  call    cs:__imp_KeAcquireGuardedMutex
0x14008719f  nop     dword ptr [rax+rax+00h]
0x1400871a4  cmp     qword ptr [rsi], 0
0x1400871a8  jz      loc_140087371
0x1400871ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1400871b5  lea     rax, WPP_GLOBAL_Control
0x1400871bc  cmp     rcx, rax
0x1400871bf  jnz     loc_140087339
0x1400871c5  mov     eax, 0C0000043h
0x1400871ca  lea     rcx, [rdi+50h]; Mutex
0x1400871ce  mov     [rbp+57h+arg_8], eax
0x1400871d1  call    cs:__imp_KeReleaseGuardedMutex
0x1400871d8  nop     dword ptr [rax+rax+00h]
0x1400871dd  mov     ecx, [rbp+57h+arg_8]
0x1400871e0  xor     r8d, r8d
0x1400871e3  test    ecx, ecx
0x1400871e5  js      loc_140087027
0x1400871eb  mov     rcx, rdi
0x1400871ee  call    BlDcbRef
0x1400871f3  mov     r14d, [rbp+57h+arg_18]
0x1400871f7  xor     r8d, r8d
0x1400871fa  mov     rcx, rax
0x1400871fd  test    rax, rax
0x140087200  jz      loc_1400873B9
0x140087206  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14008720a  mov     eax, ebx
0x14008720c  or      rcx, rax
0x14008720f  mov     [r15+20h], r8
0x140087213  mov     [r15+18h], rcx
0x140087217  mov     ecx, [rbp+57h+arg_8]
0x14008721a  jmp     loc_14008702B
0x14008721f  mov     dl, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x140087222  mov     rcx, rax; SecurityDescriptor
0x140087225  call    cs:__imp_ObReleaseObjectSecurity
0x14008722c  nop     dword ptr [rax+rax+00h]
0x140087231  mov     ecx, [rbp+57h+arg_8]
0x140087234  xor     r8d, r8d
0x140087237  mov     [rbp+57h+SecurityDescriptor], r8
0x14008723b  jmp     loc_14008703F
0x140087240  cmp     byte ptr [rcx+29h], 5
0x140087244  jb      loc_140086E7E
0x14008724a  mov     rcx, [rcx+18h]
0x14008724e  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140087255  mov     edx, 2Bh ; '+'
0x14008725a  mov     r9, r15
0x14008725d  call    WPP_SF_q
0x140087262  xor     r8d, r8d
0x140087265  jmp     loc_140086E7E
0x14008726a  mov     ecx, 0C0000002h
0x14008726f  jmp     loc_140087155
0x140087274  cmp     [r14], r8w
0x140087278  jbe     loc_140086ED7
0x14008727e  mov     ecx, 0C0000034h
0x140087283  jmp     loc_140087155
0x140087288  mov     ecx, 0C000000Dh
0x14008728d  jmp     loc_140087159
0x140087292  mov     ecx, 0C0000001h
0x140087297  jmp     loc_140087155
0x14008729c  cmp     byte ptr [rcx+29h], 5
0x1400872a0  jb      loc_140086F52
0x1400872a6  mov     rax, [rdi+98h]
0x1400872ad  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x1400872b4  mov     r9d, [rbx+28h]
0x1400872b8  mov     edx, 2Ch ; ','
0x1400872bd  mov     rcx, [rcx+18h]
0x1400872c1  mov     qword ptr [rsp+0C0h+RemlockSize], rax
0x1400872c6  call    WPP_SF_LS
0x1400872cb  jmp     loc_140086F52
0x1400872d0  cmp     byte ptr [rcx+29h], 5
0x1400872d4  jb      loc_140087145
0x1400872da  mov     r9, [rdi+98h]
0x1400872e1  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x1400872e8  mov     rcx, [rcx+18h]
0x1400872ec  mov     edx, 2Dh ; '-'
0x1400872f1  call    WPP_SF_S
0x1400872f6  xor     r8d, r8d
0x1400872f9  jmp     loc_140087145
0x1400872fe  test    dword ptr [rcx+2Ch], 400h
0x140087305  jz      loc_14008718D
0x14008730b  cmp     byte ptr [rcx+29h], 2
0x14008730f  jb      loc_14008718D
0x140087315  mov     r9, [rdi+98h]
0x14008731c  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
  ... truncated ...
```
