# FveDcbXeiFilterCreate

- ea: `0x140088ea0`
- end: `0x14008948e`
- name: `FveDcbXeiFilterCreate`
- size: `1518`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140008f04`
- `0x14000a210`
- `0x14000e034`
- `0x14000e0c4`
- `0x140088d8c`
- `0x140088ea0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14008911c`
- `ntoskrnl!IofCompleteRequest` at `0x14008911c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140088f9a`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140088f9a`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400890f5`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400890f5`
- `ntoskrnl!ObGetObjectSecurity` at `0x140088ffe`
- `ntoskrnl!ObGetObjectSecurity` at `0x140088ffe`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14008918e`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1400892c5`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x14008918e`
- `ntoskrnl!ObReleaseObjectSecurity` at `0x1400892c5`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140089238`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x140089238`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140089271`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x140089271`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400890ad`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400890ad`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14008909d`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14008909d`
- `ntoskrnl!SeAccessCheck` at `0x14008908b`
- `ntoskrnl!SeAccessCheck` at `0x14008908b`
- `ntoskrnl!SeLockSubjectContext` at `0x14008902e`
- `ntoskrnl!SeLockSubjectContext` at `0x14008902e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14008901e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14008901e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140089045`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140089045`

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
  __int64 v23; // rax
  DWORD GrantedAccess; // [rsp+50h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-11h] BYREF
  PVOID Tag; // [rsp+60h] [rbp-9h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int8 MemoryAllocated; // [rsp+D0h] [rbp+67h] BYREF
  int AccessStatus; // [rsp+D8h] [rbp+6Fh] BYREF
  int v30; // [rsp+E8h] [rbp+7Fh]

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  GrantedAccess = 0;
  SecurityDescriptor = 0;
  MemoryAllocated = 0;
  AccessStatus = 0;
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  FileObject = CurrentStackLocation->FileObject;
  Tag = 0;
  v30 = 0;
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
  v30 = 1;
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
    v13 = v30;
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
    v13 = v30;
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
    v13 = v30;
    goto LABEL_18;
  }
  v23 = BlDcbRef(a1);
  v13 = v30;
  if ( !v23 )
  {
    v14 = -1073741823;
    goto LABEL_43;
  }
  FileObject->FsContext2 = 0;
  FileObject->FsContext = (PVOID)(v21 | v23 & 0xFFFFFFFFFFFFFFFCuLL);
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
0x140088ea0  mov     [rsp-8+arg_10], rbx
0x140088ea5  push    rbp
0x140088ea6  push    rsi
0x140088ea7  push    rdi
0x140088ea8  push    r12
0x140088eaa  push    r13
0x140088eac  push    r14
0x140088eae  push    r15
0x140088eb0  lea     rbp, [rsp-27h]
0x140088eb5  sub     rsp, 90h
0x140088ebc  mov     r9, [rdx+0B8h]
0x140088ec3  xorps   xmm0, xmm0
0x140088ec6  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x140088eca  mov     r14, r8
0x140088ecd  xor     r8d, r8d
0x140088ed0  mov     [rbp+57h+var_70], r8d
0x140088ed4  mov     r13, rdx
0x140088ed7  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x140088edb  mov     [rbp+57h+SecurityDescriptor], r8
0x140088edf  mov     rdi, rcx
0x140088ee2  mov     [rbp+57h+MemoryAllocated], r8b
0x140088ee6  mov     [rbp+57h+arg_8], r8d
0x140088eea  mov     rax, [r9+8]
0x140088eee  mov     r15, [r9+30h]
0x140088ef2  mov     [rbp+57h+Tag], r8
0x140088ef6  mov     [rbp+57h+arg_18], r8d
0x140088efa  mov     r12d, [rax+10h]
0x140088efe  mov     rcx, cs:WPP_GLOBAL_Control
0x140088f05  lea     rax, WPP_GLOBAL_Control
0x140088f0c  cmp     rcx, rax
0x140088f0f  jz      short loc_140088F1E
0x140088f11  test    dword ptr [rcx+2Ch], 400h
0x140088f18  jnz     loc_1400892E0
0x140088f1e  test    rdi, rdi
0x140088f21  jz      loc_140089208
0x140088f27  mov     rsi, [rdi+0C8h]
0x140088f2e  test    rsi, rsi
0x140088f31  jz      loc_140089208
0x140088f37  cmp     dword ptr [rdi+0B0h], 3
0x140088f3e  jnz     loc_14008930A
0x140088f44  test    dword ptr [rsi+8], 0FFFFFFFDh
0x140088f4b  jnz     loc_140089208
0x140088f51  mov     rbx, [rdi+8]
0x140088f55  test    rbx, rbx
0x140088f58  jz      loc_140089208
0x140088f5e  mov     rbx, [rbx+0C8h]
0x140088f65  test    rbx, rbx
0x140088f68  jz      loc_140089208
0x140088f6e  test    r14, r14
0x140088f71  jnz     loc_140089314
0x140088f77  mov     r14d, 1
0x140088f7d  mov     [rbp+57h+Tag], rbx
0x140088f81  mov     r9d, r14d; Line
0x140088f84  mov     [rsp+0C0h+RemlockSize], 20h ; ' '; RemlockSize
0x140088f8c  lea     rcx, [rbx+8]; RemoveLock
0x140088f90  mov     rdx, rbx; Tag
0x140088f93  lea     r8, File; File
0x140088f9a  call    cs:__imp_IoAcquireRemoveLockEx
0x140088fa1  nop     dword ptr [rax+rax+00h]
0x140088fa6  xor     r8d, r8d
0x140088fa9  mov     [rbp+57h+arg_8], eax
0x140088fac  mov     ecx, eax
0x140088fae  test    eax, eax
0x140088fb0  js      loc_1400890C7
0x140088fb6  mov     rax, [rbx]
0x140088fb9  mov     [rbp+57h+arg_18], r14d
0x140088fbd  test    rax, rax
0x140088fc0  jz      loc_140089328
0x140088fc6  mov     r14, [rbx]
0x140088fc9  test    r15, r15
0x140088fcc  jz      loc_140089332
0x140088fd2  mov     rcx, cs:WPP_GLOBAL_Control
0x140088fd9  lea     rax, WPP_GLOBAL_Control
0x140088fe0  cmp     rcx, rax
0x140088fe3  jz      short loc_140088FF2
0x140088fe5  test    dword ptr [rcx+2Ch], 400h
0x140088fec  jnz     loc_14008933C
0x140088ff2  mov     rcx, [r14+78h]; Object
0x140088ff6  lea     r8, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x140088ffa  lea     rdx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140088ffe  call    cs:__imp_ObGetObjectSecurity
0x140089005  nop     dword ptr [rax+rax+00h]
0x14008900a  xor     r8d, r8d
0x14008900d  mov     [rbp+57h+arg_8], eax
0x140089010  mov     ecx, eax
0x140089012  test    eax, eax
0x140089014  js      loc_1400890C7
0x14008901a  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14008901e  call    cs:__imp_SeCaptureSubjectContext
0x140089025  nop     dword ptr [rax+rax+00h]
0x14008902a  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14008902e  call    cs:__imp_SeLockSubjectContext
0x140089035  nop     dword ptr [rax+rax+00h]
0x14008903a  mov     bl, [r13+40h]
0x14008903e  mov     [rbp+57h+arg_8], 0C0000022h
0x140089045  call    cs:__imp_IoGetFileObjectGenericMapping
0x14008904c  nop     dword ptr [rax+rax+00h]
0x140089051  lea     rcx, [rbp+57h+arg_8]
0x140089055  mov     r9d, r12d; DesiredAccess
0x140089058  mov     [rsp+0C0h+AccessStatus], rcx; AccessStatus
0x14008905d  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x140089061  lea     rcx, [rbp+57h+var_70]
0x140089065  mov     r8b, 1; SubjectContextLocked
0x140089068  mov     [rsp+0C0h+GrantedAccess], rcx; GrantedAccess
0x14008906d  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x140089071  mov     [rsp+0C0h+AccessMode], bl; AccessMode
0x140089075  mov     [rsp+0C0h+GenericMapping], rax; GenericMapping
0x14008907a  mov     [rsp+0C0h+Privileges], 0; Privileges
0x140089083  mov     [rsp+0C0h+RemlockSize], 0; PreviouslyGrantedAccess
0x14008908b  call    cs:__imp_SeAccessCheck
0x140089092  nop     dword ptr [rax+rax+00h]
0x140089097  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14008909b  mov     bl, al
0x14008909d  call    cs:__imp_SeUnlockSubjectContext
0x1400890a4  nop     dword ptr [rax+rax+00h]
0x1400890a9  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400890ad  call    cs:__imp_SeReleaseSubjectContext
0x1400890b4  nop     dword ptr [rax+rax+00h]
0x1400890b9  mov     ecx, [rbp+57h+arg_8]
0x1400890bc  xor     r8d, r8d
0x1400890bf  test    ecx, ecx
0x1400890c1  jns     loc_140089163
0x1400890c7  mov     r14d, [rbp+57h+arg_18]
0x1400890cb  lea     rbx, WPP_GLOBAL_Control
0x1400890d2  mov     rax, [rbp+57h+SecurityDescriptor]
0x1400890d6  test    rax, rax
0x1400890d9  jnz     loc_1400892BF
0x1400890df  test    r14d, r14d
0x1400890e2  jz      short loc_140089107
0x1400890e4  mov     rax, [rbp+57h+Tag]
0x1400890e8  mov     r8d, 20h ; ' '; RemlockSize
0x1400890ee  mov     rdx, rax; Tag
0x1400890f1  lea     rcx, [rax+8]; RemoveLock
0x1400890f5  call    cs:__imp_IoReleaseRemoveLockEx
0x1400890fc  nop     dword ptr [rax+rax+00h]
0x140089101  mov     ecx, [rbp+57h+arg_8]
0x140089104  xor     r8d, r8d
0x140089107  cmp     ecx, 0C0000002h
0x14008910d  jz      short loc_14008912B
0x14008910f  mov     [r13+30h], ecx
0x140089113  xor     edx, edx; PriorityBoost
0x140089115  mov     rcx, r13; Irp
0x140089118  mov     [r13+38h], r8
0x14008911c  call    cs:__imp_IofCompleteRequest
0x140089123  nop     dword ptr [rax+rax+00h]
0x140089128  mov     ecx, [rbp+57h+arg_8]
0x14008912b  mov     r10, cs:WPP_GLOBAL_Control
0x140089132  cmp     r10, rbx
0x140089135  jz      short loc_140089145
0x140089137  test    dword ptr [r10+2Ch], 400h
0x14008913f  jnz     loc_140089463
0x140089145  mov     rbx, [rsp+0C0h+arg_10]
0x14008914d  mov     eax, ecx
0x14008914f  add     rsp, 90h
0x140089156  pop     r15
0x140089158  pop     r14
0x14008915a  pop     r13
0x14008915c  pop     r12
0x14008915e  pop     rdi
0x14008915f  pop     rsi
0x140089160  pop     rbp
0x140089161  retn
0x140089163  test    bl, bl
0x140089165  jnz     short loc_14008916F
0x140089167  mov     ecx, 0C0000022h
0x14008916c  mov     [rbp+57h+arg_8], ecx
0x14008916f  test    ecx, ecx
0x140089171  js      loc_1400890C7
0x140089177  test    bl, bl
0x140089179  jz      loc_1400890C7
0x14008917f  mov     rax, [rbp+57h+SecurityDescriptor]
0x140089183  test    rax, rax
0x140089186  jz      short loc_1400891A1
0x140089188  mov     dl, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x14008918b  mov     rcx, rax; SecurityDescriptor
0x14008918e  call    cs:__imp_ObReleaseObjectSecurity
0x140089195  nop     dword ptr [rax+rax+00h]
0x14008919a  xor     r8d, r8d
0x14008919d  mov     [rbp+57h+SecurityDescriptor], r8
0x1400891a1  mov     eax, [rbp+57h+var_70]
0x1400891a4  and     eax, 102h
0x1400891a9  neg     eax
0x1400891ab  sbb     ecx, ecx
0x1400891ad  and     ecx, 3
0x1400891b0  mov     ebx, ecx
0x1400891b2  or      ebx, 1
0x1400891b5  test    byte ptr [rbp+57h+var_70], 81h
0x1400891b9  cmovz   ebx, ecx
0x1400891bc  test    ebx, ebx
0x1400891be  jz      short loc_1400891F0
0x1400891c0  test    bl, 2
0x1400891c3  jnz     short loc_14008920F
0x1400891c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400891cc  lea     rbx, WPP_GLOBAL_Control
0x1400891d3  cmp     rcx, rbx
0x1400891d6  jz      short loc_1400891E5
0x1400891d8  test    dword ptr [rcx+2Ch], 400h
0x1400891df  jnz     loc_140089370
0x1400891e5  mov     ecx, 0C0000002h
0x1400891ea  mov     r14d, [rbp+57h+arg_18]
0x1400891ee  jmp     short loc_140089200
0x1400891f0  mov     ecx, 0C0000022h
0x1400891f5  mov     r14d, [rbp+57h+arg_18]
0x1400891f9  lea     rbx, WPP_GLOBAL_Control
0x140089200  mov     [rbp+57h+arg_8], ecx
0x140089203  jmp     loc_1400890D2
0x140089208  mov     ecx, 0C000000Dh
0x14008920d  jmp     short loc_1400891F5
0x14008920f  cmp     dword ptr [r14+10h], 2
0x140089214  jnz     short loc_140089234
0x140089216  mov     rcx, cs:WPP_GLOBAL_Control
0x14008921d  lea     rbx, WPP_GLOBAL_Control
0x140089224  cmp     rcx, rbx
0x140089227  jnz     loc_14008939E
0x14008922d  mov     ecx, 0C0210034h
0x140089232  jmp     short loc_1400891EA
0x140089234  lea     rcx, [rdi+50h]; Mutex
0x140089238  call    cs:__imp_KeAcquireGuardedMutex
0x14008923f  nop     dword ptr [rax+rax+00h]
0x140089244  cmp     qword ptr [rsi], 0
0x140089248  jz      loc_140089411
0x14008924e  mov     rcx, cs:WPP_GLOBAL_Control
0x140089255  lea     rax, WPP_GLOBAL_Control
0x14008925c  cmp     rcx, rax
0x14008925f  jnz     loc_1400893D9
0x140089265  mov     eax, 0C0000043h
0x14008926a  lea     rcx, [rdi+50h]; Mutex
0x14008926e  mov     [rbp+57h+arg_8], eax
0x140089271  call    cs:__imp_KeReleaseGuardedMutex
0x140089278  nop     dword ptr [rax+rax+00h]
0x14008927d  mov     ecx, [rbp+57h+arg_8]
0x140089280  xor     r8d, r8d
0x140089283  test    ecx, ecx
0x140089285  js      loc_1400890C7
0x14008928b  mov     rcx, rdi
0x14008928e  call    BlDcbRef
0x140089293  mov     r14d, [rbp+57h+arg_18]
0x140089297  xor     r8d, r8d
0x14008929a  mov     rcx, rax
0x14008929d  test    rax, rax
0x1400892a0  jz      loc_140089459
0x1400892a6  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400892aa  mov     eax, ebx
0x1400892ac  or      rcx, rax
0x1400892af  mov     [r15+20h], r8
0x1400892b3  mov     [r15+18h], rcx
0x1400892b7  mov     ecx, [rbp+57h+arg_8]
0x1400892ba  jmp     loc_1400890CB
0x1400892bf  mov     dl, [rbp+57h+MemoryAllocated]; MemoryAllocated
0x1400892c2  mov     rcx, rax; SecurityDescriptor
0x1400892c5  call    cs:__imp_ObReleaseObjectSecurity
0x1400892cc  nop     dword ptr [rax+rax+00h]
0x1400892d1  mov     ecx, [rbp+57h+arg_8]
0x1400892d4  xor     r8d, r8d
0x1400892d7  mov     [rbp+57h+SecurityDescriptor], r8
0x1400892db  jmp     loc_1400890DF
0x1400892e0  cmp     byte ptr [rcx+29h], 5
0x1400892e4  jb      loc_140088F1E
0x1400892ea  mov     rcx, [rcx+18h]
0x1400892ee  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x1400892f5  mov     edx, 2Bh ; '+'
0x1400892fa  mov     r9, r15
0x1400892fd  call    WPP_SF_q
0x140089302  xor     r8d, r8d
0x140089305  jmp     loc_140088F1E
0x14008930a  mov     ecx, 0C0000002h
0x14008930f  jmp     loc_1400891F5
0x140089314  cmp     [r14], r8w
0x140089318  jbe     loc_140088F77
0x14008931e  mov     ecx, 0C0000034h
0x140089323  jmp     loc_1400891F5
0x140089328  mov     ecx, 0C000000Dh
0x14008932d  jmp     loc_1400891F9
0x140089332  mov     ecx, 0C0000001h
0x140089337  jmp     loc_1400891F5
0x14008933c  cmp     byte ptr [rcx+29h], 5
0x140089340  jb      loc_140088FF2
0x140089346  mov     rax, [rdi+98h]
0x14008934d  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140089354  mov     r9d, [rbx+28h]
0x140089358  mov     edx, 2Ch ; ','
0x14008935d  mov     rcx, [rcx+18h]
0x140089361  mov     qword ptr [rsp+0C0h+RemlockSize], rax
0x140089366  call    WPP_SF_LS
0x14008936b  jmp     loc_140088FF2
0x140089370  cmp     byte ptr [rcx+29h], 5
0x140089374  jb      loc_1400891E5
0x14008937a  mov     r9, [rdi+98h]
0x140089381  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
0x140089388  mov     rcx, [rcx+18h]
0x14008938c  mov     edx, 2Dh ; '-'
0x140089391  call    WPP_SF_S
0x140089396  xor     r8d, r8d
0x140089399  jmp     loc_1400891E5
0x14008939e  test    dword ptr [rcx+2Ch], 400h
0x1400893a5  jz      loc_14008922D
0x1400893ab  cmp     byte ptr [rcx+29h], 2
0x1400893af  jb      loc_14008922D
0x1400893b5  mov     r9, [rdi+98h]
0x1400893bc  lea     r8, WPP_22aa0f615fb53ee3aba7a5db0248a908_Traceguids
  ... truncated ...
```
