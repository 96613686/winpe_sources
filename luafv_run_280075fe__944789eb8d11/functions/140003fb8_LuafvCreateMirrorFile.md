# LuafvCreateMirrorFile

- ea: `0x140003fb8`
- end: `0x140004387`
- name: `LuafvCreateMirrorFile`
- size: `975`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140025350`

## callees

- `0x140003788`
- `0x140003fb8`
- `0x1400044d8`
- `0x140004b94`
- `0x14001dd90`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140004126`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140004126`
- `ntoskrnl!SeTokenObjectType` at `0x14000410d`
- `ntoskrnl!SeTokenObjectType` at `0x14000417d`
- `ntoskrnl!ZwQueryInformationToken` at `0x140004157`
- `ntoskrnl!ZwQueryInformationToken` at `0x140004157`
- `ntoskrnl!ZwClose` at `0x140004171`
- `ntoskrnl!ZwClose` at `0x140004325`
- `ntoskrnl!ZwClose` at `0x140004364`
- `ntoskrnl!ZwClose` at `0x140004171`
- `ntoskrnl!ZwClose` at `0x140004325`
- `ntoskrnl!ZwClose` at `0x140004364`
- `ntoskrnl!PsImpersonateClient` at `0x1400041d5`
- `ntoskrnl!PsImpersonateClient` at `0x1400042f3`
- `ntoskrnl!PsImpersonateClient` at `0x1400041d5`
- `ntoskrnl!PsImpersonateClient` at `0x1400042f3`
- `ntoskrnl!PsRevertToSelf` at `0x140004310`
- `ntoskrnl!PsRevertToSelf` at `0x140004310`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400040b1`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400040b1`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000434f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000434f`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400040e0`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400040e0`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400041a4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400041a4`
- `ntoskrnl!ObfDereferenceObject` at `0x140004302`
- `ntoskrnl!ObfDereferenceObject` at `0x14000433a`
- `ntoskrnl!ObfDereferenceObject` at `0x140004302`
- `ntoskrnl!ObfDereferenceObject` at `0x14000433a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400042c7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400042c7`
- `FLTMGR!FltGetFileNameInformation` at `0x140004030`
- `FLTMGR!FltGetFileNameInformation` at `0x140004030`
- `FLTMGR!FltCreateFileEx2` at `0x14000428e`
- `FLTMGR!FltCreateFileEx2` at `0x14000428e`

## pseudocode

```c
NTSTATUS __fastcall LuafvCreateMirrorFile(struct _FLT_CALLBACK_DATA *a1, __int64 a2, __int64 a3)
{
  NTSTATUS result; // eax
  NTSTATUS MirrorFileName; // ebx
  void *v8; // rdi
  char v9; // r14
  __int64 v10; // rdx
  PACCESS_TOKEN v11; // rax
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // rbx
  PACCESS_TOKEN ClientToken; // rcx
  PFLT_IO_PARAMETER_BLOCK v15; // rdx
  unsigned __int8 EffectiveOnly; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int8 CopyOnOpen[3]; // [rsp+81h] [rbp-7Fh] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+84h] [rbp-7Ch] BYREF
  HANDLE TokenHandle; // [rsp+88h] [rbp-78h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+90h] [rbp-70h] BYREF
  ULONG ReturnLength; // [rsp+98h] [rbp-68h] BYREF
  HANDLE TokenInformation; // [rsp+A0h] [rbp-60h] BYREF
  PVOID Object; // [rsp+A8h] [rbp-58h] BYREF
  PFILE_OBJECT FileObject; // [rsp+B0h] [rbp-50h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v26; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+100h] [rbp+0h] BYREF
  char v29; // [rsp+188h] [rbp+88h] BYREF

  FileHandle = 0;
  FileObject = 0;
  FileNameInformation = 0;
  v29 = 0;
  Object = 0;
  TokenInformation = 0;
  memset(&ObjectAttributes, 0, 44);
  TokenHandle = 0;
  CopyOnOpen[0] = 0;
  v26 = 0;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityAnonymous;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  ReturnLength = 0;
  result = FltGetFileNameInformation(a1, 1u, &FileNameInformation);
  MirrorFileName = result;
  if ( result >= 0 )
  {
    v8 = 0;
    v9 = 0;
    LuafvIsInstallerCaller(a1, &v29);
    if ( !(unsigned __int8)LuafvIsExcludedFile(&FileNameInformation->Name) )
    {
      if ( v29 )
      {
        MirrorFileName = GetMirrorFileName(a3 + 8, v10, &FileNameInformation->Name, &v26);
        if ( MirrorFileName >= 0 )
        {
          v11 = PsReferenceImpersonationToken(KeGetCurrentThread(), CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
          Iopb = a1->Iopb;
          v8 = v11;
          if ( Iopb->MajorFunction )
          {
            p_SubjectContext = &SubjectContext;
            SeCaptureSubjectContext(&SubjectContext);
            v9 = 1;
          }
          else
          {
            p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(Iopb->Parameters.WMI.ProviderId + 8)
                                                                  + 32LL);
          }
          ClientToken = p_SubjectContext->ClientToken;
          if ( !p_SubjectContext->ClientToken )
            ClientToken = p_SubjectContext->PrimaryToken;
          MirrorFileName = ObOpenObjectByPointer(
                             ClientToken,
                             0x200u,
                             0,
                             8u,
                             (POBJECT_TYPE)SeTokenObjectType,
                             0,
                             &TokenHandle);
          if ( MirrorFileName >= 0 )
          {
            MirrorFileName = ZwQueryInformationToken(
                               TokenHandle,
                               TokenLinkedToken,
                               &TokenInformation,
                               8u,
                               &ReturnLength);
            if ( MirrorFileName >= 0 )
            {
              ZwClose(TokenHandle);
              TokenHandle = 0;
              MirrorFileName = ObReferenceObjectByHandle(
                                 TokenInformation,
                                 8u,
                                 (POBJECT_TYPE)SeTokenObjectType,
                                 0,
                                 &Object,
                                 0);
              if ( MirrorFileName >= 0 )
              {
                MirrorFileName = PsImpersonateClient(KeGetCurrentThread(), Object, 1u, 1u, SecurityImpersonation);
                if ( MirrorFileName >= 0 )
                {
                  v15 = a1->Iopb;
                  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v26;
                  ObjectAttributes.Length = 48;
                  ObjectAttributes.RootDirectory = 0;
                  ObjectAttributes.Attributes = 576;
                  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                  MirrorFileName = FltCreateFileEx2(
                                     LuafvDriverData,
                                     *(PFLT_INSTANCE *)(a2 + 24),
                                     &FileHandle,
                                     &FileObject,
                                     *(_DWORD *)(v15->Parameters.WMI.ProviderId + 16),
                                     &ObjectAttributes,
                                     &a1->IoStatus,
                                     0,
                                     v15->Parameters.Create.FileAttributes,
                                     v15->Parameters.Create.ShareAccess,
                                     HIBYTE(v15->Parameters.Create.Options),
                                     v15->Parameters.Create.Options & 0xFFFFCF | 0x20,
                                     0,
                                     0,
                                     1u,
                                     0);
                  if ( MirrorFileName >= 0 )
                  {
                    *(_QWORD *)(a3 + 32) = FileObject;
                    *(_QWORD *)(a3 + 24) = FileHandle;
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( *((_QWORD *)&v26 + 1) )
      LuafvFreePool(*((_QWORD *)&v26 + 1));
    if ( FileNameInformation )
      FltReleaseFileNameInformation(FileNameInformation);
    if ( v8 )
    {
      PsImpersonateClient(KeGetCurrentThread(), v8, CopyOnOpen[0], EffectiveOnly, ImpersonationLevel);
      ObfDereferenceObject(v8);
    }
    else
    {
      PsRevertToSelf();
    }
    if ( TokenInformation )
      ZwClose(TokenInformation);
    if ( Object )
      ObfDereferenceObject(Object);
    if ( v9 )
      SeReleaseSubjectContext(&SubjectContext);
    if ( TokenHandle )
      ZwClose(TokenHandle);
    return MirrorFileName;
  }
  return result;
}

```

## disassembly

```asm
0x140003fb8  push    rbp
0x140003fba  push    rbx
0x140003fbb  push    rsi
0x140003fbc  push    rdi
0x140003fbd  push    r12
0x140003fbf  push    r13
0x140003fc1  push    r14
0x140003fc3  push    r15
0x140003fc5  lea     rbp, [rsp-28h]
0x140003fca  sub     rsp, 128h
0x140003fd1  xor     r12d, r12d
0x140003fd4  xorps   xmm0, xmm0
0x140003fd7  xor     eax, eax
0x140003fd9  mov     [rbp+60h+FileHandle], r12
0x140003fdd  mov     rsi, r8
0x140003fe0  mov     [rbp+60h+FileObject], r12
0x140003fe4  mov     r13, rdx
0x140003fe7  mov     [rbp+60h+FileNameInformation], r12
0x140003feb  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x140003fef  lea     edx, [rax+1]; NameOptions
0x140003ff2  mov     [rbp+60h+arg_18], r12b
0x140003ff9  lea     r8, [rbp+60h+FileNameInformation]; FileNameInformation
0x140003ffd  mov     [rbp+60h+Object], r12
0x140004001  mov     r15, rcx
0x140004004  mov     [rbp+60h+TokenInformation], r12
0x140004008  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x14000400c  mov     [rbp+60h+TokenHandle], r12
0x140004010  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x140004014  mov     [rbp+60h+CopyOnOpen], r12b
0x140004018  movups  [rbp+60h+var_A0], xmm0
0x14000401c  mov     [rbp+60h+EffectiveOnly], r12b
0x140004020  mov     [rbp+60h+ImpersonationLevel], r12d
0x140004024  movups  xmmword ptr [rbp+60h+SubjectContext.ClientToken], xmm0
0x140004028  mov     [rbp+60h+ReturnLength], r12d
0x14000402c  movups  xmmword ptr [rbp+60h+SubjectContext.PrimaryToken], xmm0
0x140004030  call    cs:__imp_FltGetFileNameInformation
0x140004037  nop     dword ptr [rax+rax+00h]
0x14000403c  mov     ebx, eax
0x14000403e  test    eax, eax
0x140004040  js      loc_140004372
0x140004046  lea     rdx, [rbp+60h+arg_18]
0x14000404d  mov     rcx, r15
0x140004050  mov     edi, r12d
0x140004053  mov     r14b, r12b
0x140004056  call    LuafvIsInstallerCaller
0x14000405b  mov     rcx, [rbp+60h+FileNameInformation]
0x14000405f  add     rcx, 8
0x140004063  call    LuafvIsExcludedFile
0x140004068  test    al, al
0x14000406a  jnz     loc_1400042B0
0x140004070  cmp     [rbp+60h+arg_18], r12b
0x140004077  jz      loc_1400042B0
0x14000407d  mov     r8, [rbp+60h+FileNameInformation]
0x140004081  lea     rcx, [rsi+8]
0x140004085  add     r8, 8
0x140004089  lea     r9, [rbp+60h+var_A0]
0x14000408d  call    GetMirrorFileName
0x140004092  mov     ebx, eax
0x140004094  test    eax, eax
0x140004096  js      loc_1400042B0
0x14000409c  mov     rcx, gs:188h; Thread
0x1400040a5  lea     r9, [rbp+60h+ImpersonationLevel]; ImpersonationLevel
0x1400040a9  lea     r8, [rbp+60h+EffectiveOnly]; EffectiveOnly
0x1400040ad  lea     rdx, [rbp+60h+CopyOnOpen]; CopyOnOpen
0x1400040b1  call    cs:__imp_PsReferenceImpersonationToken
0x1400040b8  nop     dword ptr [rax+rax+00h]
0x1400040bd  mov     rcx, [r15+10h]
0x1400040c1  mov     rdi, rax
0x1400040c4  cmp     [rcx+4], r12b
0x1400040c8  jnz     short loc_1400040D8
0x1400040ca  mov     rcx, [rcx+18h]
0x1400040ce  mov     rbx, [rcx+8]
0x1400040d2  add     rbx, 20h ; ' '
0x1400040d6  jmp     short loc_1400040EF
0x1400040d8  lea     rcx, [rbp+60h+SubjectContext]; SubjectContext
0x1400040dc  lea     rbx, [rbp+60h+SubjectContext]
0x1400040e0  call    cs:__imp_SeCaptureSubjectContext
0x1400040e7  nop     dword ptr [rax+rax+00h]
0x1400040ec  mov     r14b, 1
0x1400040ef  mov     rcx, [rbx]
0x1400040f2  test    rcx, rcx
0x1400040f5  jnz     short loc_1400040FB
0x1400040f7  mov     rcx, [rbx+10h]; Object
0x1400040fb  lea     rax, [rbp+60h+TokenHandle]
0x1400040ff  mov     r9d, 8; DesiredAccess
0x140004105  mov     [rsp+160h+Handle], rax; Handle
0x14000410a  xor     r8d, r8d; PassedAccessState
0x14000410d  mov     rax, cs:__imp_SeTokenObjectType
0x140004114  mov     [rsp+160h+AccessMode], r12b; AccessMode
0x140004119  mov     rdx, [rax]
0x14000411c  mov     [rsp+160h+ObjectType], rdx; ObjectType
0x140004121  mov     edx, 200h; HandleAttributes
0x140004126  call    cs:__imp_ObOpenObjectByPointer
0x14000412d  nop     dword ptr [rax+rax+00h]
0x140004132  mov     ebx, eax
0x140004134  test    eax, eax
0x140004136  js      loc_1400042B0
0x14000413c  mov     rcx, [rbp+60h+TokenHandle]; TokenHandle
0x140004140  lea     rax, [rbp+60h+ReturnLength]
0x140004144  mov     r9d, 8; TokenInformationLength
0x14000414a  mov     [rsp+160h+ObjectType], rax; ReturnLength
0x14000414f  lea     r8, [rbp+60h+TokenInformation]; TokenInformation
0x140004153  lea     edx, [r9+0Bh]; TokenInformationClass
0x140004157  call    cs:__imp_ZwQueryInformationToken
0x14000415e  nop     dword ptr [rax+rax+00h]
0x140004163  mov     ebx, eax
0x140004165  test    eax, eax
0x140004167  js      loc_1400042B0
0x14000416d  mov     rcx, [rbp+60h+TokenHandle]; Handle
0x140004171  call    cs:__imp_ZwClose
0x140004178  nop     dword ptr [rax+rax+00h]
0x14000417d  mov     r8, cs:__imp_SeTokenObjectType
0x140004184  lea     rax, [rbp+60h+Object]
0x140004188  mov     rcx, [rbp+60h+TokenInformation]; Handle
0x14000418c  xor     r9d, r9d; AccessMode
0x14000418f  mov     [rbp+60h+TokenHandle], r12
0x140004193  mov     qword ptr [rsp+160h+AccessMode], r12; HandleInformation
0x140004198  mov     r8, [r8]; ObjectType
0x14000419b  lea     edx, [r9+8]; DesiredAccess
0x14000419f  mov     [rsp+160h+ObjectType], rax; Object
0x1400041a4  call    cs:__imp_ObReferenceObjectByHandle
0x1400041ab  nop     dword ptr [rax+rax+00h]
0x1400041b0  mov     ebx, eax
0x1400041b2  test    eax, eax
0x1400041b4  js      loc_1400042B0
0x1400041ba  mov     rcx, gs:188h; Thread
0x1400041c3  mov     r9b, 1; EffectiveOnly
0x1400041c6  mov     rdx, [rbp+60h+Object]; Token
0x1400041ca  mov     r8b, r9b; CopyOnOpen
0x1400041cd  mov     dword ptr [rsp+160h+ObjectType], 2; ImpersonationLevel
0x1400041d5  call    cs:__imp_PsImpersonateClient
0x1400041dc  nop     dword ptr [rax+rax+00h]
0x1400041e1  mov     ebx, eax
0x1400041e3  test    eax, eax
0x1400041e5  js      loc_1400042B0
0x1400041eb  mov     rdx, [r15+10h]
0x1400041ef  lea     rax, [rbp+60h+var_A0]
0x1400041f3  mov     [rsp+160h+DriverContext], r12; DriverContext
0x1400041f8  lea     r8, [r15+18h]
0x1400041fc  mov     [rsp+160h+Flags], 1; Flags
0x140004204  xorps   xmm0, xmm0
0x140004207  mov     [rsp+160h+EaLength], r12d; EaLength
0x14000420c  mov     [rsp+160h+EaBuffer], r12; EaBuffer
0x140004211  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x140004215  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x14000421c  mov     [rbp+60h+ObjectAttributes.RootDirectory], r12
0x140004220  mov     [rbp+60h+ObjectAttributes.Attributes], 240h
0x140004227  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000422c  mov     r11d, [rdx+20h]
0x140004230  mov     r10d, r11d
0x140004233  movzx   eax, word ptr [rdx+2Ah]
0x140004237  and     r10d, 0FFFFCFh
0x14000423e  movzx   ecx, word ptr [rdx+28h]
0x140004242  or      r10d, 20h
0x140004246  mov     r9, [rdx+18h]
0x14000424a  mov     rdx, [r13+18h]; Instance
0x14000424e  mov     [rsp+160h+CreateOptions], r10d; CreateOptions
0x140004253  shr     r11d, 18h
0x140004257  mov     [rsp+160h+CreateDisposition], r11d; CreateDisposition
0x14000425c  mov     [rsp+160h+ShareAccess], eax; ShareAccess
0x140004260  lea     rax, [rbp+60h+ObjectAttributes]
0x140004264  mov     [rsp+160h+FileAttributes], ecx; FileAttributes
0x140004268  mov     rcx, cs:LuafvDriverData; Filter
0x14000426f  mov     [rsp+160h+AllocationSize], r12; AllocationSize
0x140004274  mov     [rsp+160h+Handle], r8; IoStatusBlock
0x140004279  lea     r8, [rbp+60h+FileHandle]; FileHandle
0x14000427d  mov     qword ptr [rsp+160h+AccessMode], rax; ObjectAttributes
0x140004282  mov     eax, [r9+10h]
0x140004286  lea     r9, [rbp+60h+FileObject]; FileObject
0x14000428a  mov     dword ptr [rsp+160h+ObjectType], eax; DesiredAccess
0x14000428e  call    cs:__imp_FltCreateFileEx2
0x140004295  nop     dword ptr [rax+rax+00h]
0x14000429a  mov     ebx, eax
0x14000429c  test    eax, eax
0x14000429e  js      short loc_1400042B0
0x1400042a0  mov     rax, [rbp+60h+FileObject]
0x1400042a4  mov     [rsi+20h], rax
0x1400042a8  mov     rax, [rbp+60h+FileHandle]
0x1400042ac  mov     [rsi+18h], rax
0x1400042b0  mov     rcx, qword ptr [rbp+60h+var_A0+8]
0x1400042b4  test    rcx, rcx
0x1400042b7  jz      short loc_1400042BE
0x1400042b9  call    LuafvFreePool
0x1400042be  mov     rcx, [rbp+60h+FileNameInformation]; FileNameInformation
0x1400042c2  test    rcx, rcx
0x1400042c5  jz      short loc_1400042D3
0x1400042c7  call    cs:__imp_FltReleaseFileNameInformation
0x1400042ce  nop     dword ptr [rax+rax+00h]
0x1400042d3  test    rdi, rdi
0x1400042d6  jz      short loc_140004310
0x1400042d8  mov     rcx, gs:188h; Thread
0x1400042e1  mov     rdx, rdi; Token
0x1400042e4  mov     eax, [rbp+60h+ImpersonationLevel]
0x1400042e7  mov     r9b, [rbp+60h+EffectiveOnly]; EffectiveOnly
0x1400042eb  mov     r8b, [rbp+60h+CopyOnOpen]; CopyOnOpen
0x1400042ef  mov     dword ptr [rsp+160h+ObjectType], eax; ImpersonationLevel
0x1400042f3  call    cs:__imp_PsImpersonateClient
0x1400042fa  nop     dword ptr [rax+rax+00h]
0x1400042ff  mov     rcx, rdi; Object
0x140004302  call    cs:__imp_ObfDereferenceObject
0x140004309  nop     dword ptr [rax+rax+00h]
0x14000430e  jmp     short loc_14000431C
0x140004310  call    cs:__imp_PsRevertToSelf
0x140004317  nop     dword ptr [rax+rax+00h]
0x14000431c  mov     rcx, [rbp+60h+TokenInformation]; Handle
0x140004320  test    rcx, rcx
0x140004323  jz      short loc_140004331
0x140004325  call    cs:__imp_ZwClose
0x14000432c  nop     dword ptr [rax+rax+00h]
0x140004331  mov     rcx, [rbp+60h+Object]; Object
0x140004335  test    rcx, rcx
0x140004338  jz      short loc_140004346
0x14000433a  call    cs:__imp_ObfDereferenceObject
0x140004341  nop     dword ptr [rax+rax+00h]
0x140004346  test    r14b, r14b
0x140004349  jz      short loc_14000435B
0x14000434b  lea     rcx, [rbp+60h+SubjectContext]; SubjectContext
0x14000434f  call    cs:__imp_SeReleaseSubjectContext
0x140004356  nop     dword ptr [rax+rax+00h]
0x14000435b  mov     rcx, [rbp+60h+TokenHandle]; Handle
0x14000435f  test    rcx, rcx
0x140004362  jz      short loc_140004370
0x140004364  call    cs:__imp_ZwClose
0x14000436b  nop     dword ptr [rax+rax+00h]
0x140004370  mov     eax, ebx
0x140004372  add     rsp, 128h
0x140004379  pop     r15
0x14000437b  pop     r14
0x14000437d  pop     r13
0x14000437f  pop     r12
0x140004381  pop     rdi
0x140004382  pop     rsi
0x140004383  pop     rbx
0x140004384  pop     rbp
0x140004385  retn
```
