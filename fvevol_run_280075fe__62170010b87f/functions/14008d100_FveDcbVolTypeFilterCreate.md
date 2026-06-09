# FveDcbVolTypeFilterCreate

- ea: `0x14008d100`
- end: `0x14008d330`
- name: `FveDcbVolTypeFilterCreate`
- size: `560`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140086cec`
- `0x140086d30`
- `0x14008d100`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x14008d1b1`
- `ntoskrnl!IofCompleteRequest` at `0x14008d1b1`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14008d2b0`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14008d2b0`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14008d2a0`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14008d2a0`
- `ntoskrnl!SeAccessCheck` at `0x14008d28e`
- `ntoskrnl!SeAccessCheck` at `0x14008d28e`
- `ntoskrnl!SeLockSubjectContext` at `0x14008d22e`
- `ntoskrnl!SeLockSubjectContext` at `0x14008d22e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14008d21e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14008d21e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008d1c3`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008d248`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008d1c3`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14008d248`
- `ntoskrnl!RtlMapGenericMask` at `0x14008d1d6`
- `ntoskrnl!RtlMapGenericMask` at `0x14008d1d6`

## pseudocode

```c
__int64 __fastcall FveDcbVolTypeFilterCreate(__int64 a1, IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  __int64 v4; // r8
  __int64 v6; // rdi
  PFILE_OBJECT FileObject; // r15
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  __int64 v10; // rdx
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
  LODWORD(v4) = -1073741822;
  AccessStatus = -1073741822;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  AccessMask = *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 16);
  if ( !a1 || (v6 = *(_QWORD *)(a1 + 200)) == 0 )
  {
    LODWORD(v4) = -1073741811;
    AccessStatus = -1073741811;
    goto LABEL_7;
  }
  FileObject = CurrentStackLocation->FileObject;
  if ( !FileObject )
  {
LABEL_25:
    LODWORD(v4) = -1073741823;
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
    v4 = (unsigned int)AccessStatus;
    if ( AccessStatus >= 0 )
    {
      if ( !v15 )
      {
        v4 = 3221225506LL;
        AccessStatus = -1073741790;
      }
      if ( (int)v4 >= 0 && v15 )
      {
        if ( (GrantedAccess & 0x102) == 0 )
        {
          LODWORD(v4) = -1073741811;
          goto LABEL_22;
        }
        v10 = AccessMask;
LABEL_10:
        v11 = ((v10 & 0x102) != 0 ? 2 : 0) | 1;
        if ( (v10 & 0x81) == 0 )
          v11 = (v10 & 0x102) != 0 ? 3 : 0;
        if ( (v11 & 2) == 0 )
        {
          LODWORD(v4) = -1073741822;
          return (unsigned int)v4;
        }
        v16 = BlDcbRef(a1, v10, v4);
        if ( !v16 )
          goto LABEL_25;
        BlAttachFileObject(v16, FileObject, v11);
        LODWORD(v4) = 0;
LABEL_22:
        AccessStatus = v4;
        goto LABEL_8;
      }
    }
LABEL_7:
    if ( (_DWORD)v4 == -1073741822 )
      return (unsigned int)v4;
LABEL_8:
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = v4;
    IofCompleteRequest(a2, 0);
    LODWORD(v4) = AccessStatus;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14008d100  mov     [rsp-28h+arg_10], rbx
0x14008d105  push    rbp
0x14008d106  push    rsi
0x14008d107  push    rdi
0x14008d108  push    r14
0x14008d10a  push    r15
0x14008d10c  mov     rbp, rsp
0x14008d10f  sub     rsp, 70h
0x14008d113  mov     [rbp+AccessMask], 0
0x14008d11a  mov     r14, rcx
0x14008d11d  mov     rcx, [rdx+0B8h]
0x14008d124  xorps   xmm0, xmm0
0x14008d127  mov     [rbp+arg_18], 0
0x14008d12e  mov     r8d, 0C0000002h
0x14008d134  mov     [rbp+arg_0], r8d
0x14008d138  mov     rsi, rdx
0x14008d13b  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14008d13f  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14008d143  mov     rax, [rcx+8]
0x14008d147  mov     edx, [rax+10h]
0x14008d14a  mov     [rbp+AccessMask], edx
0x14008d14d  test    r14, r14
0x14008d150  jz      short loc_14008D18D
0x14008d152  mov     rdi, [r14+0C8h]
0x14008d159  test    rdi, rdi
0x14008d15c  jz      short loc_14008D18D
0x14008d15e  mov     r15, [rcx+30h]
0x14008d162  test    r15, r15
0x14008d165  jz      loc_14008D328
0x14008d16b  cmp     dword ptr [r14+0B0h], 1
0x14008d173  jz      short loc_14008D1C3
0x14008d175  mov     rbx, [rsp+70h+arg_10]
0x14008d17d  mov     eax, r8d
0x14008d180  add     rsp, 70h
0x14008d184  pop     r15
0x14008d186  pop     r14
0x14008d188  pop     rdi
0x14008d189  pop     rsi
0x14008d18a  pop     rbp
0x14008d18b  retn
0x14008d18d  mov     r8d, 0C000000Dh
0x14008d193  mov     [rbp+arg_0], r8d
0x14008d197  cmp     r8d, 0C0000002h
0x14008d19e  jz      short loc_14008D175
0x14008d1a0  xor     edx, edx; PriorityBoost
0x14008d1a2  mov     qword ptr [rsi+38h], 0
0x14008d1aa  mov     rcx, rsi; Irp
0x14008d1ad  mov     [rsi+30h], r8d
0x14008d1b1  call    cs:__imp_IofCompleteRequest
0x14008d1b8  nop     dword ptr [rax+rax+00h]
0x14008d1bd  mov     r8d, [rbp+arg_0]
0x14008d1c1  jmp     short loc_14008D175
0x14008d1c3  call    cs:__imp_IoGetFileObjectGenericMapping
0x14008d1ca  nop     dword ptr [rax+rax+00h]
0x14008d1cf  mov     rdx, rax; GenericMapping
0x14008d1d2  lea     rcx, [rbp+AccessMask]; AccessMask
0x14008d1d6  call    cs:__imp_RtlMapGenericMask
0x14008d1dd  nop     dword ptr [rax+rax+00h]
0x14008d1e2  mov     edx, [rbp+AccessMask]
0x14008d1e5  test    edx, 102h
0x14008d1eb  jnz     short loc_14008D21A
0x14008d1ed  mov     eax, edx
0x14008d1ef  and     eax, 102h
0x14008d1f4  neg     eax
0x14008d1f6  sbb     ecx, ecx
0x14008d1f8  and     ecx, 3
0x14008d1fb  mov     ebx, ecx
0x14008d1fd  or      ebx, 1
0x14008d200  test    dl, 81h
0x14008d203  cmovz   ebx, ecx
0x14008d206  test    bl, 2
0x14008d209  jnz     loc_14008D31B
0x14008d20f  mov     r8d, 0C0000002h
0x14008d215  jmp     loc_14008D175
0x14008d21a  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14008d21e  call    cs:__imp_SeCaptureSubjectContext
0x14008d225  nop     dword ptr [rax+rax+00h]
0x14008d22a  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14008d22e  call    cs:__imp_SeLockSubjectContext
0x14008d235  nop     dword ptr [rax+rax+00h]
0x14008d23a  mov     bl, [rsi+40h]
0x14008d23d  mov     [rbp+arg_0], 0C0000022h
0x14008d244  mov     rdi, [rdi+10h]
0x14008d248  call    cs:__imp_IoGetFileObjectGenericMapping
0x14008d24f  nop     dword ptr [rax+rax+00h]
0x14008d254  mov     r9d, [rbp+AccessMask]; DesiredAccess
0x14008d258  lea     rcx, [rbp+arg_0]
0x14008d25c  mov     [rsp+70h+AccessStatus], rcx; AccessStatus
0x14008d261  lea     rdx, [rbp+SubjectContext]; SubjectSecurityContext
0x14008d265  lea     rcx, [rbp+arg_18]
0x14008d269  mov     r8b, 1; SubjectContextLocked
0x14008d26c  mov     [rsp+70h+GrantedAccess], rcx; GrantedAccess
0x14008d271  mov     rcx, rdi; SecurityDescriptor
0x14008d274  mov     [rsp+70h+AccessMode], bl; AccessMode
0x14008d278  mov     [rsp+70h+GenericMapping], rax; GenericMapping
0x14008d27d  mov     [rsp+70h+Privileges], 0; Privileges
0x14008d286  mov     [rsp+70h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x14008d28e  call    cs:__imp_SeAccessCheck
0x14008d295  nop     dword ptr [rax+rax+00h]
0x14008d29a  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14008d29e  mov     bl, al
0x14008d2a0  call    cs:__imp_SeUnlockSubjectContext
0x14008d2a7  nop     dword ptr [rax+rax+00h]
0x14008d2ac  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14008d2b0  call    cs:__imp_SeReleaseSubjectContext
0x14008d2b7  nop     dword ptr [rax+rax+00h]
0x14008d2bc  mov     r8d, [rbp+arg_0]
0x14008d2c0  test    r8d, r8d
0x14008d2c3  js      loc_14008D197
0x14008d2c9  test    bl, bl
0x14008d2cb  jnz     short loc_14008D2D7
0x14008d2cd  mov     r8d, 0C0000022h
0x14008d2d3  mov     [rbp+arg_0], r8d
0x14008d2d7  test    r8d, r8d
0x14008d2da  js      loc_14008D197
0x14008d2e0  test    bl, bl
0x14008d2e2  jz      loc_14008D197
0x14008d2e8  test    [rbp+arg_18], 102h
0x14008d2ef  jnz     short loc_14008D313
0x14008d2f1  mov     r8d, 0C000000Dh
0x14008d2f7  jmp     short loc_14008D30A
0x14008d2f9  mov     r8d, ebx
0x14008d2fc  mov     rdx, r15
0x14008d2ff  mov     rcx, rax
0x14008d302  call    BlAttachFileObject
0x14008d307  xor     r8d, r8d
0x14008d30a  mov     [rbp+arg_0], r8d
0x14008d30e  jmp     loc_14008D1A0
0x14008d313  mov     edx, [rbp+AccessMask]
0x14008d316  jmp     loc_14008D1ED
0x14008d31b  mov     rcx, r14
0x14008d31e  call    BlDcbRef
0x14008d323  test    rax, rax
0x14008d326  jnz     short loc_14008D2F9
0x14008d328  mov     r8d, 0C0000001h
0x14008d32e  jmp     short loc_14008D30A
```
