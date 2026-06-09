# FveDcbVolTypeFilterCreate

- ea: `0x14008f1b0`
- end: `0x14008f3e0`
- name: `FveDcbVolTypeFilterCreate`
- size: `560`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140088d8c`
- `0x140088dd0`
- `0x14008f1b0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14008f261`
- `ntoskrnl!IofCompleteRequest` at `0x14008f261`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14008f360`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14008f360`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14008f350`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14008f350`
- `ntoskrnl!SeAccessCheck` at `0x14008f33e`
- `ntoskrnl!SeAccessCheck` at `0x14008f33e`
- `ntoskrnl!SeLockSubjectContext` at `0x14008f2de`
- `ntoskrnl!SeLockSubjectContext` at `0x14008f2de`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14008f2ce`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14008f2ce`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008f273`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008f2f8`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008f273`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008f2f8`
- `ntoskrnl!RtlMapGenericMask` at `0x14008f286`
- `ntoskrnl!RtlMapGenericMask` at `0x14008f286`

## pseudocode

```c
__int64 __fastcall FveDcbVolTypeFilterCreate(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  int v4; // r8d
  __int64 v6; // rdi
  PFILE_OBJECT FileObject; // r15
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  __int16 v10; // dx
  unsigned int v11; // ebx
  KPROCESSOR_MODE AccessMode; // bl
  void *v13; // rdi
  struct _GENERIC_MAPPING *GenericMapping; // rax
  BOOLEAN v15; // bl
  __int64 v16; // rax
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-20h] BYREF
  int AccessStatus; // [rsp+A0h] [rbp+30h] BYREF
  DWORD AccessMask; // [rsp+A8h] [rbp+38h] BYREF
  DWORD GrantedAccess; // [rsp+B8h] [rbp+48h] BYREF

  AccessMask = 0;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  GrantedAccess = 0;
  v4 = -1073741822;
  AccessStatus = -1073741822;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  AccessMask = *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 16);
  if ( !a1 || (v6 = *(_QWORD *)(a1 + 200)) == 0 )
  {
    v4 = -1073741811;
    AccessStatus = -1073741811;
    goto LABEL_7;
  }
  FileObject = CurrentStackLocation->FileObject;
  if ( !FileObject )
  {
LABEL_25:
    v4 = -1073741823;
    goto LABEL_22;
  }
  if ( *(_DWORD *)(a1 + 176) == 1 )
  {
    FileObjectGenericMapping = IoGetFileObjectGenericMapping();
    RtlMapGenericMask(&AccessMask, FileObjectGenericMapping);
    v10 = AccessMask;
    if ( (AccessMask & 0x102) == 0 )
      goto LABEL_10;
    SeCaptureSubjectContext(&SubjectContext);
    SeLockSubjectContext(&SubjectContext);
    AccessMode = a2->RequestorMode;
    AccessStatus = -1073741790;
    v13 = *(void **)(v6 + 16);
    GenericMapping = IoGetFileObjectGenericMapping();
    v15 = SeAccessCheck(
            v13,
            &SubjectContext,
            1u,
            AccessMask,
            0,
            0,
            GenericMapping,
            AccessMode,
            &GrantedAccess,
            &AccessStatus);
    SeUnlockSubjectContext(&SubjectContext);
    SeReleaseSubjectContext(&SubjectContext);
    v4 = AccessStatus;
    if ( AccessStatus >= 0 )
    {
      if ( !v15 )
      {
        v4 = -1073741790;
        AccessStatus = -1073741790;
      }
      if ( v4 >= 0 && v15 )
      {
        if ( (GrantedAccess & 0x102) == 0 )
        {
          v4 = -1073741811;
          goto LABEL_22;
        }
        v10 = AccessMask;
LABEL_10:
        v11 = ((v10 & 0x102) != 0 ? 2 : 0) | 1;
        if ( (v10 & 0x81) == 0 )
          v11 = (v10 & 0x102) != 0 ? 3 : 0;
        if ( (v11 & 2) == 0 )
          return (unsigned int)-1073741822;
        v16 = BlDcbRef(a1);
        if ( !v16 )
          goto LABEL_25;
        BlAttachFileObject(v16, FileObject, v11);
        v4 = 0;
LABEL_22:
        AccessStatus = v4;
        goto LABEL_8;
      }
    }
LABEL_7:
    if ( v4 == -1073741822 )
      return (unsigned int)v4;
LABEL_8:
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = v4;
    IofCompleteRequest(a2, 0);
    return (unsigned int)AccessStatus;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14008f1b0  mov     [rsp-28h+arg_10], rbx
0x14008f1b5  push    rbp
0x14008f1b6  push    rsi
0x14008f1b7  push    rdi
0x14008f1b8  push    r14
0x14008f1ba  push    r15
0x14008f1bc  mov     rbp, rsp
0x14008f1bf  sub     rsp, 70h
0x14008f1c3  mov     [rbp+AccessMask], 0
0x14008f1ca  mov     r14, rcx
0x14008f1cd  mov     rcx, [rdx+0B8h]
0x14008f1d4  xorps   xmm0, xmm0
0x14008f1d7  mov     [rbp+arg_18], 0
0x14008f1de  mov     r8d, 0C0000002h
0x14008f1e4  mov     [rbp+arg_0], r8d
0x14008f1e8  mov     rsi, rdx
0x14008f1eb  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14008f1ef  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14008f1f3  mov     rax, [rcx+8]
0x14008f1f7  mov     edx, [rax+10h]
0x14008f1fa  mov     [rbp+AccessMask], edx
0x14008f1fd  test    r14, r14
0x14008f200  jz      short loc_14008F23D
0x14008f202  mov     rdi, [r14+0C8h]
0x14008f209  test    rdi, rdi
0x14008f20c  jz      short loc_14008F23D
0x14008f20e  mov     r15, [rcx+30h]
0x14008f212  test    r15, r15
0x14008f215  jz      loc_14008F3D8
0x14008f21b  cmp     dword ptr [r14+0B0h], 1
0x14008f223  jz      short loc_14008F273
0x14008f225  mov     rbx, [rsp+70h+arg_10]
0x14008f22d  mov     eax, r8d
0x14008f230  add     rsp, 70h
0x14008f234  pop     r15
0x14008f236  pop     r14
0x14008f238  pop     rdi
0x14008f239  pop     rsi
0x14008f23a  pop     rbp
0x14008f23b  retn
0x14008f23d  mov     r8d, 0C000000Dh
0x14008f243  mov     [rbp+arg_0], r8d
0x14008f247  cmp     r8d, 0C0000002h
0x14008f24e  jz      short loc_14008F225
0x14008f250  xor     edx, edx; PriorityBoost
0x14008f252  mov     qword ptr [rsi+38h], 0
0x14008f25a  mov     rcx, rsi; Irp
0x14008f25d  mov     [rsi+30h], r8d
0x14008f261  call    cs:__imp_IofCompleteRequest
0x14008f268  nop     dword ptr [rax+rax+00h]
0x14008f26d  mov     r8d, [rbp+arg_0]
0x14008f271  jmp     short loc_14008F225
0x14008f273  call    cs:__imp_IoGetFileObjectGenericMapping
0x14008f27a  nop     dword ptr [rax+rax+00h]
0x14008f27f  mov     rdx, rax; GenericMapping
0x14008f282  lea     rcx, [rbp+AccessMask]; AccessMask
0x14008f286  call    cs:__imp_RtlMapGenericMask
0x14008f28d  nop     dword ptr [rax+rax+00h]
0x14008f292  mov     edx, [rbp+AccessMask]
0x14008f295  test    edx, 102h
0x14008f29b  jnz     short loc_14008F2CA
0x14008f29d  mov     eax, edx
0x14008f29f  and     eax, 102h
0x14008f2a4  neg     eax
0x14008f2a6  sbb     ecx, ecx
0x14008f2a8  and     ecx, 3
0x14008f2ab  mov     ebx, ecx
0x14008f2ad  or      ebx, 1
0x14008f2b0  test    dl, 81h
0x14008f2b3  cmovz   ebx, ecx
0x14008f2b6  test    bl, 2
0x14008f2b9  jnz     loc_14008F3CB
0x14008f2bf  mov     r8d, 0C0000002h
0x14008f2c5  jmp     loc_14008F225
0x14008f2ca  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14008f2ce  call    cs:__imp_SeCaptureSubjectContext
0x14008f2d5  nop     dword ptr [rax+rax+00h]
0x14008f2da  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14008f2de  call    cs:__imp_SeLockSubjectContext
0x14008f2e5  nop     dword ptr [rax+rax+00h]
0x14008f2ea  mov     bl, [rsi+40h]
0x14008f2ed  mov     [rbp+arg_0], 0C0000022h
0x14008f2f4  mov     rdi, [rdi+10h]
0x14008f2f8  call    cs:__imp_IoGetFileObjectGenericMapping
0x14008f2ff  nop     dword ptr [rax+rax+00h]
0x14008f304  mov     r9d, [rbp+AccessMask]; DesiredAccess
0x14008f308  lea     rcx, [rbp+arg_0]
0x14008f30c  mov     [rsp+70h+AccessStatus], rcx; AccessStatus
0x14008f311  lea     rdx, [rbp+SubjectContext]; SubjectSecurityContext
0x14008f315  lea     rcx, [rbp+arg_18]
0x14008f319  mov     r8b, 1; SubjectContextLocked
0x14008f31c  mov     [rsp+70h+GrantedAccess], rcx; GrantedAccess
0x14008f321  mov     rcx, rdi; SecurityDescriptor
0x14008f324  mov     [rsp+70h+AccessMode], bl; AccessMode
0x14008f328  mov     [rsp+70h+GenericMapping], rax; GenericMapping
0x14008f32d  mov     [rsp+70h+Privileges], 0; Privileges
0x14008f336  mov     [rsp+70h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14008f33e  call    cs:__imp_SeAccessCheck
0x14008f345  nop     dword ptr [rax+rax+00h]
0x14008f34a  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14008f34e  mov     bl, al
0x14008f350  call    cs:__imp_SeUnlockSubjectContext
0x14008f357  nop     dword ptr [rax+rax+00h]
0x14008f35c  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14008f360  call    cs:__imp_SeReleaseSubjectContext
0x14008f367  nop     dword ptr [rax+rax+00h]
0x14008f36c  mov     r8d, [rbp+arg_0]
0x14008f370  test    r8d, r8d
0x14008f373  js      loc_14008F247
0x14008f379  test    bl, bl
0x14008f37b  jnz     short loc_14008F387
0x14008f37d  mov     r8d, 0C0000022h
0x14008f383  mov     [rbp+arg_0], r8d
0x14008f387  test    r8d, r8d
0x14008f38a  js      loc_14008F247
0x14008f390  test    bl, bl
0x14008f392  jz      loc_14008F247
0x14008f398  test    [rbp+arg_18], 102h
0x14008f39f  jnz     short loc_14008F3C3
0x14008f3a1  mov     r8d, 0C000000Dh
0x14008f3a7  jmp     short loc_14008F3BA
0x14008f3a9  mov     r8d, ebx
0x14008f3ac  mov     rdx, r15
0x14008f3af  mov     rcx, rax
0x14008f3b2  call    BlAttachFileObject
0x14008f3b7  xor     r8d, r8d
0x14008f3ba  mov     [rbp+arg_0], r8d
0x14008f3be  jmp     loc_14008F250
0x14008f3c3  mov     edx, [rbp+AccessMask]
0x14008f3c6  jmp     loc_14008F29D
0x14008f3cb  mov     rcx, r14
0x14008f3ce  call    BlDcbRef
0x14008f3d3  test    rax, rax
0x14008f3d6  jnz     short loc_14008F3A9
0x14008f3d8  mov     r8d, 0C0000001h
0x14008f3de  jmp     short loc_14008F3BA
```
