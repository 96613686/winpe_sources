# LuafvCreateMirrorFile

- ea: `0x1400041e8`
- end: `0x1400045b7`
- name: `LuafvCreateMirrorFile`
- size: `975`
- prototype: `NTSTATUS __fastcall(struct _FLT_CALLBACK_DATA *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140025300`

## callees

- `0x1400039b8`
- `0x1400041e8`
- `0x140004708`
- `0x140004d5c`
- `0x14001dd40`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x140004356`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140004356`
- `ntoskrnl!SeTokenObjectType` at `0x14000433d`
- `ntoskrnl!SeTokenObjectType` at `0x1400043ad`
- `ntoskrnl!ZwQueryInformationToken` at `0x140004387`
- `ntoskrnl!ZwQueryInformationToken` at `0x140004387`
- `ntoskrnl!ZwClose` at `0x1400043a1`
- `ntoskrnl!ZwClose` at `0x140004555`
- `ntoskrnl!ZwClose` at `0x140004594`
- `ntoskrnl!ZwClose` at `0x1400043a1`
- `ntoskrnl!ZwClose` at `0x140004555`
- `ntoskrnl!ZwClose` at `0x140004594`
- `ntoskrnl!PsImpersonateClient` at `0x140004405`
- `ntoskrnl!PsImpersonateClient` at `0x140004523`
- `ntoskrnl!PsImpersonateClient` at `0x140004405`
- `ntoskrnl!PsImpersonateClient` at `0x140004523`
- `ntoskrnl!PsRevertToSelf` at `0x140004540`
- `ntoskrnl!PsRevertToSelf` at `0x140004540`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400042e1`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x1400042e1`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000457f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14000457f`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004310`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140004310`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400043d4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400043d4`
- `ntoskrnl!ObfDereferenceObject` at `0x140004532`
- `ntoskrnl!ObfDereferenceObject` at `0x14000456a`
- `ntoskrnl!ObfDereferenceObject` at `0x140004532`
- `ntoskrnl!ObfDereferenceObject` at `0x14000456a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400044f7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400044f7`
- `FLTMGR!FltGetFileNameInformation` at `0x140004260`
- `FLTMGR!FltGetFileNameInformation` at `0x140004260`
- `FLTMGR!FltCreateFileEx2` at `0x1400044be`
- `FLTMGR!FltCreateFileEx2` at `0x1400044be`

## pseudocode

```c
NTSTATUS __fastcall LuafvCreateMirrorFile(struct _FLT_CALLBACK_DATA *a1, __int64 a2, _QWORD *a3)
{
  NTSTATUS result; // eax
  int MirrorFileName; // ebx
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
  struct _UNICODE_STRING v26; // [rsp+C0h] [rbp-40h] BYREF
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
        MirrorFileName = GetMirrorFileName(a3 + 1, v10, &FileNameInformation->Name, &v26);
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
                  ObjectAttributes.ObjectName = &v26;
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
                    a3[4] = FileObject;
                    a3[3] = FileHandle;
                  }
                }
              }
            }
          }
        }
      }
    }
    if ( v26.Buffer )
      LuafvFreePool(v26.Buffer);
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
0x1400041e8  push    rbp
0x1400041ea  push    rbx
0x1400041eb  push    rsi
0x1400041ec  push    rdi
0x1400041ed  push    r12
0x1400041ef  push    r13
0x1400041f1  push    r14
0x1400041f3  push    r15
0x1400041f5  lea     rbp, [rsp-28h]
0x1400041fa  sub     rsp, 128h
0x140004201  xor     r12d, r12d
0x140004204  xorps   xmm0, xmm0
0x140004207  xor     eax, eax
0x140004209  mov     [rbp+60h+FileHandle], r12
0x14000420d  mov     rsi, r8
0x140004210  mov     [rbp+60h+FileObject], r12
0x140004214  mov     r13, rdx
0x140004217  mov     [rbp+60h+FileNameInformation], r12
0x14000421b  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x14000421f  lea     edx, [rax+1]; NameOptions
0x140004222  mov     [rbp+60h+arg_18], r12b
0x140004229  lea     r8, [rbp+60h+FileNameInformation]; FileNameInformation
0x14000422d  mov     [rbp+60h+Object], r12
0x140004231  mov     r15, rcx
0x140004234  mov     [rbp+60h+TokenInformation], r12
0x140004238  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x14000423c  mov     [rbp+60h+TokenHandle], r12
0x140004240  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x140004244  mov     [rbp+60h+CopyOnOpen], r12b
0x140004248  movups  [rbp+60h+var_A0], xmm0
0x14000424c  mov     [rbp+60h+EffectiveOnly], r12b
0x140004250  mov     [rbp+60h+ImpersonationLevel], r12d
0x140004254  movups  xmmword ptr [rbp+60h+SubjectContext.ClientToken], xmm0
0x140004258  mov     [rbp+60h+ReturnLength], r12d
0x14000425c  movups  xmmword ptr [rbp+60h+SubjectContext.PrimaryToken], xmm0
0x140004260  call    cs:__imp_FltGetFileNameInformation
0x140004267  nop     dword ptr [rax+rax+00h]
0x14000426c  mov     ebx, eax
0x14000426e  test    eax, eax
0x140004270  js      loc_1400045A2
0x140004276  lea     rdx, [rbp+60h+arg_18]
0x14000427d  mov     rcx, r15
0x140004280  mov     edi, r12d
0x140004283  mov     r14b, r12b
0x140004286  call    LuafvIsInstallerCaller
0x14000428b  mov     rcx, [rbp+60h+FileNameInformation]
0x14000428f  add     rcx, 8
0x140004293  call    LuafvIsExcludedFile
0x140004298  test    al, al
0x14000429a  jnz     loc_1400044E0
0x1400042a0  cmp     [rbp+60h+arg_18], r12b
0x1400042a7  jz      loc_1400044E0
0x1400042ad  mov     r8, [rbp+60h+FileNameInformation]
0x1400042b1  lea     rcx, [rsi+8]
0x1400042b5  add     r8, 8
0x1400042b9  lea     r9, [rbp+60h+var_A0]
0x1400042bd  call    GetMirrorFileName
0x1400042c2  mov     ebx, eax
0x1400042c4  test    eax, eax
0x1400042c6  js      loc_1400044E0
0x1400042cc  mov     rcx, gs:188h; Thread
0x1400042d5  lea     r9, [rbp+60h+ImpersonationLevel]; ImpersonationLevel
0x1400042d9  lea     r8, [rbp+60h+EffectiveOnly]; EffectiveOnly
0x1400042dd  lea     rdx, [rbp+60h+CopyOnOpen]; CopyOnOpen
0x1400042e1  call    cs:__imp_PsReferenceImpersonationToken
0x1400042e8  nop     dword ptr [rax+rax+00h]
0x1400042ed  mov     rcx, [r15+10h]
0x1400042f1  mov     rdi, rax
0x1400042f4  cmp     [rcx+4], r12b
0x1400042f8  jnz     short loc_140004308
0x1400042fa  mov     rcx, [rcx+18h]
0x1400042fe  mov     rbx, [rcx+8]
0x140004302  add     rbx, 20h ; ' '
0x140004306  jmp     short loc_14000431F
0x140004308  lea     rcx, [rbp+60h+SubjectContext]; SubjectContext
0x14000430c  lea     rbx, [rbp+60h+SubjectContext]
0x140004310  call    cs:__imp_SeCaptureSubjectContext
0x140004317  nop     dword ptr [rax+rax+00h]
0x14000431c  mov     r14b, 1
0x14000431f  mov     rcx, [rbx]
0x140004322  test    rcx, rcx
0x140004325  jnz     short loc_14000432B
0x140004327  mov     rcx, [rbx+10h]; Object
0x14000432b  lea     rax, [rbp+60h+TokenHandle]
0x14000432f  mov     r9d, 8; DesiredAccess
0x140004335  mov     [rsp+160h+Handle], rax; Handle
0x14000433a  xor     r8d, r8d; PassedAccessState
0x14000433d  mov     rax, cs:__imp_SeTokenObjectType
0x140004344  mov     [rsp+160h+AccessMode], r12b; AccessMode
0x140004349  mov     rdx, [rax]
0x14000434c  mov     [rsp+160h+ObjectType], rdx; ObjectType
0x140004351  mov     edx, 200h; HandleAttributes
0x140004356  call    cs:__imp_ObOpenObjectByPointer
0x14000435d  nop     dword ptr [rax+rax+00h]
0x140004362  mov     ebx, eax
0x140004364  test    eax, eax
0x140004366  js      loc_1400044E0
0x14000436c  mov     rcx, [rbp+60h+TokenHandle]; TokenHandle
0x140004370  lea     rax, [rbp+60h+ReturnLength]
0x140004374  mov     r9d, 8; TokenInformationLength
0x14000437a  mov     [rsp+160h+ObjectType], rax; ReturnLength
0x14000437f  lea     r8, [rbp+60h+TokenInformation]; TokenInformation
0x140004383  lea     edx, [r9+0Bh]; TokenInformationClass
0x140004387  call    cs:__imp_ZwQueryInformationToken
0x14000438e  nop     dword ptr [rax+rax+00h]
0x140004393  mov     ebx, eax
0x140004395  test    eax, eax
0x140004397  js      loc_1400044E0
0x14000439d  mov     rcx, [rbp+60h+TokenHandle]; Handle
0x1400043a1  call    cs:__imp_ZwClose
0x1400043a8  nop     dword ptr [rax+rax+00h]
0x1400043ad  mov     r8, cs:__imp_SeTokenObjectType
0x1400043b4  lea     rax, [rbp+60h+Object]
0x1400043b8  mov     rcx, [rbp+60h+TokenInformation]; Handle
0x1400043bc  xor     r9d, r9d; AccessMode
0x1400043bf  mov     [rbp+60h+TokenHandle], r12
0x1400043c3  mov     qword ptr [rsp+160h+AccessMode], r12; HandleInformation
0x1400043c8  mov     r8, [r8]; ObjectType
0x1400043cb  lea     edx, [r9+8]; DesiredAccess
0x1400043cf  mov     [rsp+160h+ObjectType], rax; Object
0x1400043d4  call    cs:__imp_ObReferenceObjectByHandle
0x1400043db  nop     dword ptr [rax+rax+00h]
0x1400043e0  mov     ebx, eax
0x1400043e2  test    eax, eax
0x1400043e4  js      loc_1400044E0
0x1400043ea  mov     rcx, gs:188h; Thread
0x1400043f3  mov     r9b, 1; EffectiveOnly
0x1400043f6  mov     rdx, [rbp+60h+Object]; Token
0x1400043fa  mov     r8b, r9b; CopyOnOpen
0x1400043fd  mov     dword ptr [rsp+160h+ObjectType], 2; ImpersonationLevel
0x140004405  call    cs:__imp_PsImpersonateClient
0x14000440c  nop     dword ptr [rax+rax+00h]
0x140004411  mov     ebx, eax
0x140004413  test    eax, eax
0x140004415  js      loc_1400044E0
0x14000441b  mov     rdx, [r15+10h]
0x14000441f  lea     rax, [rbp+60h+var_A0]
0x140004423  mov     [rsp+160h+DriverContext], r12; DriverContext
0x140004428  lea     r8, [r15+18h]
0x14000442c  mov     [rsp+160h+Flags], 1; Flags
0x140004434  xorps   xmm0, xmm0
0x140004437  mov     [rsp+160h+EaLength], r12d; EaLength
0x14000443c  mov     [rsp+160h+EaBuffer], r12; EaBuffer
0x140004441  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x140004445  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x14000444c  mov     [rbp+60h+ObjectAttributes.RootDirectory], r12
0x140004450  mov     [rbp+60h+ObjectAttributes.Attributes], 240h
0x140004457  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000445c  mov     r11d, [rdx+20h]
0x140004460  mov     r10d, r11d
0x140004463  movzx   eax, word ptr [rdx+2Ah]
0x140004467  and     r10d, 0FFFFCFh
0x14000446e  movzx   ecx, word ptr [rdx+28h]
0x140004472  or      r10d, 20h
0x140004476  mov     r9, [rdx+18h]
0x14000447a  mov     rdx, [r13+18h]; Instance
0x14000447e  mov     [rsp+160h+CreateOptions], r10d; CreateOptions
0x140004483  shr     r11d, 18h
0x140004487  mov     [rsp+160h+CreateDisposition], r11d; CreateDisposition
0x14000448c  mov     [rsp+160h+ShareAccess], eax; ShareAccess
0x140004490  lea     rax, [rbp+60h+ObjectAttributes]
0x140004494  mov     [rsp+160h+FileAttributes], ecx; FileAttributes
0x140004498  mov     rcx, cs:LuafvDriverData; Filter
0x14000449f  mov     [rsp+160h+AllocationSize], r12; AllocationSize
0x1400044a4  mov     [rsp+160h+Handle], r8; IoStatusBlock
0x1400044a9  lea     r8, [rbp+60h+FileHandle]; FileHandle
0x1400044ad  mov     qword ptr [rsp+160h+AccessMode], rax; ObjectAttributes
0x1400044b2  mov     eax, [r9+10h]
0x1400044b6  lea     r9, [rbp+60h+FileObject]; FileObject
0x1400044ba  mov     dword ptr [rsp+160h+ObjectType], eax; DesiredAccess
0x1400044be  call    cs:__imp_FltCreateFileEx2
0x1400044c5  nop     dword ptr [rax+rax+00h]
0x1400044ca  mov     ebx, eax
0x1400044cc  test    eax, eax
0x1400044ce  js      short loc_1400044E0
0x1400044d0  mov     rax, [rbp+60h+FileObject]
0x1400044d4  mov     [rsi+20h], rax
0x1400044d8  mov     rax, [rbp+60h+FileHandle]
0x1400044dc  mov     [rsi+18h], rax
0x1400044e0  mov     rcx, qword ptr [rbp+60h+var_A0+8]
0x1400044e4  test    rcx, rcx
0x1400044e7  jz      short loc_1400044EE
0x1400044e9  call    LuafvFreePool
0x1400044ee  mov     rcx, [rbp+60h+FileNameInformation]; FileNameInformation
0x1400044f2  test    rcx, rcx
0x1400044f5  jz      short loc_140004503
0x1400044f7  call    cs:__imp_FltReleaseFileNameInformation
0x1400044fe  nop     dword ptr [rax+rax+00h]
0x140004503  test    rdi, rdi
0x140004506  jz      short loc_140004540
0x140004508  mov     rcx, gs:188h; Thread
0x140004511  mov     rdx, rdi; Token
0x140004514  mov     eax, [rbp+60h+ImpersonationLevel]
0x140004517  mov     r9b, [rbp+60h+EffectiveOnly]; EffectiveOnly
0x14000451b  mov     r8b, [rbp+60h+CopyOnOpen]; CopyOnOpen
0x14000451f  mov     dword ptr [rsp+160h+ObjectType], eax; ImpersonationLevel
0x140004523  call    cs:__imp_PsImpersonateClient
0x14000452a  nop     dword ptr [rax+rax+00h]
0x14000452f  mov     rcx, rdi; Object
0x140004532  call    cs:__imp_ObfDereferenceObject
0x140004539  nop     dword ptr [rax+rax+00h]
0x14000453e  jmp     short loc_14000454C
0x140004540  call    cs:__imp_PsRevertToSelf
0x140004547  nop     dword ptr [rax+rax+00h]
0x14000454c  mov     rcx, [rbp+60h+TokenInformation]; Handle
0x140004550  test    rcx, rcx
0x140004553  jz      short loc_140004561
0x140004555  call    cs:__imp_ZwClose
0x14000455c  nop     dword ptr [rax+rax+00h]
0x140004561  mov     rcx, [rbp+60h+Object]; Object
0x140004565  test    rcx, rcx
0x140004568  jz      short loc_140004576
0x14000456a  call    cs:__imp_ObfDereferenceObject
0x140004571  nop     dword ptr [rax+rax+00h]
0x140004576  test    r14b, r14b
0x140004579  jz      short loc_14000458B
0x14000457b  lea     rcx, [rbp+60h+SubjectContext]; SubjectContext
0x14000457f  call    cs:__imp_SeReleaseSubjectContext
0x140004586  nop     dword ptr [rax+rax+00h]
0x14000458b  mov     rcx, [rbp+60h+TokenHandle]; Handle
0x14000458f  test    rcx, rcx
0x140004592  jz      short loc_1400045A0
0x140004594  call    cs:__imp_ZwClose
0x14000459b  nop     dword ptr [rax+rax+00h]
0x1400045a0  mov     eax, ebx
0x1400045a2  add     rsp, 128h
0x1400045a9  pop     r15
0x1400045ab  pop     r14
0x1400045ad  pop     r13
0x1400045af  pop     r12
0x1400045b1  pop     rdi
0x1400045b2  pop     rsi
0x1400045b3  pop     rbx
0x1400045b4  pop     rbp
0x1400045b5  retn
```
