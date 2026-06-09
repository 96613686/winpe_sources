# LuafvPerformDelayedVirtualization

- ea: `0x140015388`
- end: `0x1400157cb`
- name: `LuafvPerformDelayedVirtualization`
- size: `1091`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140001440`

## callees

- `0x140005f30`
- `0x140006380`
- `0x140015388`
- `0x14001860c`
- `0x140022de8`

## import_xrefs

- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14001578d`
- `ntoskrnl!PsDereferenceImpersonationToken` at `0x14001578d`
- `ntoskrnl!PsImpersonateClient` at `0x14001577e`
- `ntoskrnl!PsImpersonateClient` at `0x14001577e`
- `ntoskrnl!PsRevertToSelf` at `0x14001574d`
- `ntoskrnl!PsRevertToSelf` at `0x14001574d`
- `ntoskrnl!SeDeleteClientSecurity` at `0x1400155c0`
- `ntoskrnl!SeDeleteClientSecurity` at `0x1400155c0`
- `ntoskrnl!SeImpersonateClientEx` at `0x1400155ae`
- `ntoskrnl!SeImpersonateClientEx` at `0x1400155ae`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140015595`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140015595`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x140015530`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x140015530`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400154dc`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400154dc`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x1400154c7`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x1400154c7`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400154a8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400154a8`
- `FLTMGR!FltReleasePushLockEx` at `0x140015547`
- `FLTMGR!FltReleasePushLockEx` at `0x14001579e`
- `FLTMGR!FltReleasePushLockEx` at `0x140015547`
- `FLTMGR!FltReleasePushLockEx` at `0x14001579e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001543e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14001543e`
- `FLTMGR!FltCreateFileEx2` at `0x1400156b7`
- `FLTMGR!FltCreateFileEx2` at `0x1400156b7`

## pseudocode

```c
__int64 __fastcall LuafvPerformDelayedVirtualization(__int64 a1, __int64 a2, __int64 a3)
{
  char v3; // r14
  __int64 v4; // rdi
  __int64 v7; // rax
  __int64 v8; // r12
  NTSTATUS VirtualFile; // ebx
  __int64 v10; // r13
  __int64 v11; // rax
  struct _UNICODE_STRING *v12; // r15
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // rbx
  char v14; // si
  PACCESS_TOKEN ClientToken; // rcx
  __int64 v16; // rcx
  PACCESS_TOKEN v17; // rsi
  struct _UNICODE_STRING *v19; // rax
  __int64 *v20; // r15
  __int64 *v21; // rbx
  struct _UNICODE_STRING *v22; // rdi
  __int64 v23; // rsi
  __int64 v24; // r14
  NTSTATUS v25; // eax
  NTSTATUS v26; // r12d
  __int64 v27; // rdx
  char v28; // [rsp+80h] [rbp-80h]
  unsigned __int8 EffectiveOnly; // [rsp+81h] [rbp-7Fh] BYREF
  unsigned __int8 CopyOnOpen[2]; // [rsp+82h] [rbp-7Eh] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+84h] [rbp-7Ch] BYREF
  PFILE_OBJECT FileObject; // [rsp+88h] [rbp-78h] BYREF
  struct _LUID AuthenticationId; // [rsp+90h] [rbp-70h] BYREF
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 v35; // [rsp+A0h] [rbp-60h]
  void *FileHandle; // [rsp+A8h] [rbp-58h] BYREF
  PACCESS_TOKEN v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  struct _UNICODE_STRING *v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  __int64 v41; // [rsp+D0h] [rbp-30h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+108h] [rbp+8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+128h] [rbp+28h] BYREF
  struct _SECURITY_QUALITY_OF_SERVICE ClientSecurityQos; // [rsp+138h] [rbp+38h] BYREF
  _SECURITY_CLIENT_CONTEXT ClientContext; // [rsp+150h] [rbp+50h] BYREF

  v40 = a3;
  v34 = a2;
  v3 = 0;
  v35 = a1;
  v4 = a3;
  AuthenticationId = 0;
  *(_QWORD *)&ClientSecurityQos.Length = 0;
  *(_DWORD *)&ClientSecurityQos.ContextTrackingMode = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  memset(&ClientContext, 0, 0x44u);
  FileHandle = 0;
  FileObject = 0;
  v7 = *(_QWORD *)(v4 + 192);
  CopyOnOpen[0] = 0;
  memset(&ObjectAttributes, 0, 44);
  v8 = v7 + 64;
  EffectiveOnly = 0;
  ImpersonationLevel = SecurityImpersonation;
  v38 = v7;
  IoStatusBlock = 0;
  v41 = v7 + 64;
  FltAcquirePushLockExclusiveEx(v7 + 64, 0);
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 32) + 80LL) & 0x4000) != 0 )
  {
    VirtualFile = -1073741823;
LABEL_15:
    FltReleasePushLockEx(v8, 0);
    return (unsigned int)VirtualFile;
  }
  if ( *(_BYTE *)(v4 + 252) )
  {
    VirtualFile = 0;
    goto LABEL_15;
  }
  v10 = *(_QWORD *)(v4 + 256);
  v11 = *(_QWORD *)(a2 + 16);
  v28 = 0;
  v12 = *(struct _UNICODE_STRING **)v10;
  v39 = *(struct _UNICODE_STRING **)v10;
  if ( *(_BYTE *)(v11 + 4) )
  {
    p_SubjectContext = &SubjectContext;
    SeCaptureSubjectContext(&SubjectContext);
    v14 = 1;
  }
  else
  {
    p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(v11 + 24) + 8LL) + 32LL);
    v14 = 0;
  }
  ClientToken = p_SubjectContext->ClientToken;
  if ( !p_SubjectContext->ClientToken )
    ClientToken = p_SubjectContext->PrimaryToken;
  SeQueryAuthenticationIdToken(ClientToken, &AuthenticationId);
  if ( v14 )
    SeReleaseSubjectContext(&SubjectContext);
  v16 = *((_QWORD *)v12[6].Buffer + 2);
  if ( *(_DWORD *)(v16 + 48) == AuthenticationId.LowPart )
  {
    v17 = 0;
    v37 = 0;
    if ( *(_DWORD *)(v16 + 52) == AuthenticationId.HighPart )
      goto LABEL_19;
  }
  ClientSecurityQos.Length = 12;
  ClientSecurityQos.ImpersonationLevel = SecurityImpersonation;
  *(_WORD *)&ClientSecurityQos.ContextTrackingMode = 1;
  VirtualFile = SeCreateClientSecurityFromSubjectContext(
                  (PSECURITY_SUBJECT_CONTEXT)(v4 + 264),
                  &ClientSecurityQos,
                  0,
                  &ClientContext);
  if ( VirtualFile < 0 )
    goto LABEL_15;
  v17 = PsReferenceImpersonationToken(KeGetCurrentThread(), CopyOnOpen, &EffectiveOnly, &ImpersonationLevel);
  v37 = v17;
  VirtualFile = SeImpersonateClientEx(&ClientContext, 0);
  SeDeleteClientSecurity(&ClientContext);
  if ( VirtualFile >= 0 )
  {
    v3 = 1;
    v28 = 1;
LABEL_19:
    VirtualFile = LuafvCreateVirtualFile(v35, v34, v10, *(_QWORD *)(v4 + 208));
    if ( VirtualFile >= 0 )
    {
      v19 = v12 + 3;
      ObjectAttributes.Length = 48;
      v20 = (__int64 *)(v38 + 24);
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = v19;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v21 = *(__int64 **)(v38 + 24);
      if ( v21 != (__int64 *)(v38 + 24) )
      {
        v22 = v39;
        v23 = v34;
        v24 = v35;
        do
        {
          v25 = FltCreateFileEx2(
                  LuafvDriverData,
                  *(PFLT_INSTANCE *)(v24 + 24),
                  &FileHandle,
                  &FileObject,
                  *((_DWORD *)v21 + 30),
                  &ObjectAttributes,
                  &IoStatusBlock,
                  0,
                  0,
                  *((_DWORD *)v21 + 31),
                  1u,
                  *((_DWORD *)v21 + 32),
                  0,
                  0,
                  1u,
                  0);
          v26 = v25;
          if ( v25 >= 0 )
          {
            v21[6] = (__int64)FileHandle;
            v21[7] = (__int64)FileObject;
            v21[8] = (__int64)FileObject;
            *((_BYTE *)v21 + 76) = 1;
            *(_BYTE *)(v10 + 52) |= 2u;
            v27 = v21[3];
            *(_QWORD *)(v27 + 40) = FileObject->SectionObjectPointer;
            *(_QWORD *)(v27 + 48) = FileObject->PrivateCacheMap;
          }
          else
          {
            LuafvLogFileError(v23, v22, LuafvDelayedSwitchFailed, (unsigned int)v25);
            v21[8] = 0;
            *((_DWORD *)v21 + 18) = v26;
          }
          v21 = (__int64 *)*v21;
        }
        while ( v21 != v20 );
        v4 = v40;
        v17 = v37;
        v3 = v28;
        v8 = v41;
      }
      VirtualFile = 0;
    }
  }
  if ( v3 )
    PsRevertToSelf();
  if ( v17 )
  {
    if ( v3 )
      PsImpersonateClient(KeGetCurrentThread(), v17, CopyOnOpen[0], EffectiveOnly, ImpersonationLevel);
    PsDereferenceImpersonationToken(v17);
  }
  FltReleasePushLockEx(v8, 0);
  if ( VirtualFile < 0 || *(_QWORD *)(v4 + 240) )
    return (unsigned int)VirtualFile;
  return *(unsigned int *)(v4 + 248);
}

```

## disassembly

```asm
0x140015388  mov     [rsp-8+arg_18], rbx
0x14001538d  push    rbp
0x14001538e  push    rsi
0x14001538f  push    rdi
0x140015390  push    r12
0x140015392  push    r13
0x140015394  push    r14
0x140015396  push    r15
0x140015398  lea     rbp, [rsp-0B0h]
0x1400153a0  sub     rsp, 1B0h
0x1400153a7  mov     rax, cs:__security_cookie
0x1400153ae  xor     rax, rsp
0x1400153b1  mov     [rbp+0E0h+var_40], rax
0x1400153b8  xor     eax, eax
0x1400153ba  mov     [rbp+0E0h+var_118], r8
0x1400153be  xorps   xmm0, xmm0
0x1400153c1  mov     [rbp+0E0h+var_148], rdx
0x1400153c5  xor     r14d, r14d
0x1400153c8  mov     [rbp+0E0h+var_140], rcx
0x1400153cc  mov     rdi, r8
0x1400153cf  mov     qword ptr [rbp+0E0h+AuthenticationId.LowPart], r14
0x1400153d3  mov     rbx, rdx
0x1400153d6  mov     qword ptr [rbp+0E0h+ClientSecurityQos.Length], rax
0x1400153da  mov     rsi, rcx
0x1400153dd  mov     dword ptr [rbp+0E0h+ClientSecurityQos.ContextTrackingMode], eax
0x1400153e0  lea     r8d, [r14+44h]; Size
0x1400153e4  mov     dword ptr [rbp+0E0h+ClientContext+0Ch], eax
0x1400153e7  xor     edx, edx; Val
0x1400153e9  lea     rcx, [rbp+0E0h+ClientContext]; void *
0x1400153ed  movups  xmmword ptr [rbp+0E0h+SubjectContext.ClientToken], xmm0
0x1400153f1  movups  xmmword ptr [rbp+0E0h+SubjectContext.PrimaryToken], xmm0
0x1400153f5  call    memset
0x1400153fa  xorps   xmm0, xmm0
0x1400153fd  mov     [rbp+0E0h+FileHandle], r14
0x140015401  xor     eax, eax
0x140015403  mov     [rbp+0E0h+FileObject], r14
0x140015407  mov     rax, [rdi+0C0h]
0x14001540e  xor     edx, edx
0x140015410  movups  xmmword ptr [rbp+0E0h+var_108.ObjectName], xmm0
0x140015414  mov     [rbp+0E0h+CopyOnOpen], r14b
0x140015418  movups  xmmword ptr [rbp+0E0h+var_108.Length], xmm0
0x14001541c  lea     r12, [rax+40h]
0x140015420  mov     [rbp+0E0h+EffectiveOnly], r14b
0x140015424  mov     rcx, r12
0x140015427  mov     [rbp+0E0h+ImpersonationLevel], 2
0x14001542e  movups  xmmword ptr [rbp+0E0h+var_108+1Ch], xmm0
0x140015432  mov     [rbp+0E0h+var_128], rax
0x140015436  movups  xmmword ptr [rbp+0E0h+var_B8], xmm0
0x14001543a  mov     [rbp+0E0h+var_110], r12
0x14001543e  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140015445  nop     dword ptr [rax+rax+00h]
0x14001544a  mov     rax, [rsi+20h]
0x14001544e  test    dword ptr [rax+50h], 4000h
0x140015455  jz      short loc_140015461
0x140015457  mov     ebx, 0C0000001h
0x14001545c  jmp     loc_140015542
0x140015461  cmp     [rdi+0FCh], r14b
0x140015468  jz      short loc_140015472
0x14001546a  mov     ebx, r14d
0x14001546d  jmp     loc_140015542
0x140015472  mov     r13, [rdi+100h]
0x140015479  mov     rax, [rbx+10h]
0x14001547d  mov     [rbp+0E0h+var_160], r14b
0x140015481  mov     r15, [r13+0]
0x140015485  mov     [rbp+0E0h+var_120], r15
0x140015489  cmp     [rax+4], r14b
0x14001548d  jnz     short loc_1400154A0
0x14001548f  mov     rax, [rax+18h]
0x140015493  mov     rbx, [rax+8]
0x140015497  add     rbx, 20h ; ' '
0x14001549b  xor     sil, sil
0x14001549e  jmp     short loc_1400154B7
0x1400154a0  lea     rcx, [rbp+0E0h+SubjectContext]; SubjectContext
0x1400154a4  lea     rbx, [rbp+0E0h+SubjectContext]
0x1400154a8  call    cs:__imp_SeCaptureSubjectContext
0x1400154af  nop     dword ptr [rax+rax+00h]
0x1400154b4  mov     sil, 1
0x1400154b7  mov     rcx, [rbx]
0x1400154ba  test    rcx, rcx
0x1400154bd  jnz     short loc_1400154C3
0x1400154bf  mov     rcx, [rbx+10h]; Token
0x1400154c3  lea     rdx, [rbp+0E0h+AuthenticationId]; AuthenticationId
0x1400154c7  call    cs:__imp_SeQueryAuthenticationIdToken
0x1400154ce  nop     dword ptr [rax+rax+00h]
0x1400154d3  test    sil, sil
0x1400154d6  jz      short loc_1400154E8
0x1400154d8  lea     rcx, [rbp+0E0h+SubjectContext]; SubjectContext
0x1400154dc  call    cs:__imp_SeReleaseSubjectContext
0x1400154e3  nop     dword ptr [rax+rax+00h]
0x1400154e8  mov     rax, [r15+68h]
0x1400154ec  mov     rcx, [rax+10h]
0x1400154f0  mov     eax, [rbp+0E0h+AuthenticationId.LowPart]
0x1400154f3  cmp     [rcx+30h], eax
0x1400154f6  jnz     short loc_14001550A
0x1400154f8  mov     eax, [rbp+0E0h+AuthenticationId.HighPart]
0x1400154fb  xor     esi, esi
0x1400154fd  mov     [rbp+0E0h+var_130], rsi
0x140015501  cmp     [rcx+34h], eax
0x140015504  jz      loc_1400155DB
0x14001550a  lea     rcx, [rdi+108h]; SubjectContext
0x140015511  mov     [rbp+0E0h+ClientSecurityQos.Length], 0Ch
0x140015518  lea     r9, [rbp+0E0h+ClientContext]; ClientContext
0x14001551c  mov     [rbp+0E0h+ClientSecurityQos.ImpersonationLevel], 2
0x140015523  xor     r8d, r8d; ServerIsRemote
0x140015526  mov     word ptr [rbp+0E0h+ClientSecurityQos.ContextTrackingMode], 1
0x14001552c  lea     rdx, [rbp+0E0h+ClientSecurityQos]; ClientSecurityQos
0x140015530  call    cs:__imp_SeCreateClientSecurityFromSubjectContext
0x140015537  nop     dword ptr [rax+rax+00h]
0x14001553c  mov     ebx, eax
0x14001553e  test    eax, eax
0x140015540  jns     short loc_140015580
0x140015542  xor     edx, edx
0x140015544  mov     rcx, r12
0x140015547  call    cs:__imp_FltReleasePushLockEx
0x14001554e  nop     dword ptr [rax+rax+00h]
0x140015553  mov     eax, ebx
0x140015555  mov     rcx, [rbp+0E0h+var_40]
0x14001555c  xor     rcx, rsp; StackCookie
0x14001555f  call    __security_check_cookie
0x140015564  mov     rbx, [rsp+1E0h+arg_18]
0x14001556c  add     rsp, 1B0h
0x140015573  pop     r15
0x140015575  pop     r14
0x140015577  pop     r13
0x140015579  pop     r12
0x14001557b  pop     rdi
0x14001557c  pop     rsi
0x14001557d  pop     rbp
0x14001557e  retn
0x140015580  mov     rcx, gs:188h; Thread
0x140015589  lea     r9, [rbp+0E0h+ImpersonationLevel]; ImpersonationLevel
0x14001558d  lea     r8, [rbp+0E0h+EffectiveOnly]; EffectiveOnly
0x140015591  lea     rdx, [rbp+0E0h+CopyOnOpen]; CopyOnOpen
0x140015595  call    cs:__imp_PsReferenceImpersonationToken
0x14001559c  nop     dword ptr [rax+rax+00h]
0x1400155a1  xor     edx, edx; ServerThread
0x1400155a3  lea     rcx, [rbp+0E0h+ClientContext]; ClientContext
0x1400155a7  mov     rsi, rax
0x1400155aa  mov     [rbp+0E0h+var_130], rax
0x1400155ae  call    cs:__imp_SeImpersonateClientEx
0x1400155b5  nop     dword ptr [rax+rax+00h]
0x1400155ba  lea     rcx, [rbp+0E0h+ClientContext]
0x1400155be  mov     ebx, eax
0x1400155c0  call    cs:__imp_SeDeleteClientSecurity
0x1400155c7  nop     dword ptr [rax+rax+00h]
0x1400155cc  test    ebx, ebx
0x1400155ce  js      loc_140015748
0x1400155d4  mov     r14b, 1
0x1400155d7  mov     [rbp+0E0h+var_160], r14b
0x1400155db  mov     r9, [rdi+0D0h]
0x1400155e2  mov     r8, r13
0x1400155e5  mov     rdx, [rbp+0E0h+var_148]
0x1400155e9  mov     rcx, [rbp+0E0h+var_140]
0x1400155ed  call    LuafvCreateVirtualFile
0x1400155f2  mov     ebx, eax
0x1400155f4  test    eax, eax
0x1400155f6  js      loc_140015748
0x1400155fc  lea     rax, [r15+30h]
0x140015600  mov     [rbp+0E0h+var_108.Length], 30h ; '0'
0x140015607  mov     r15, [rbp+0E0h+var_128]
0x14001560b  xorps   xmm0, xmm0
0x14001560e  add     r15, 18h
0x140015612  mov     [rbp+0E0h+var_108.RootDirectory], 0
0x14001561a  mov     [rbp+0E0h+var_108.Attributes], 240h
0x140015621  mov     [rbp+0E0h+var_108.ObjectName], rax
0x140015625  movdqu  xmmword ptr [rbp+0E0h+var_108.SecurityDescriptor], xmm0
0x14001562a  mov     rbx, [r15]
0x14001562d  cmp     rbx, r15
0x140015630  jz      loc_140015746
0x140015636  mov     rdi, [rbp+0E0h+var_120]
0x14001563a  mov     rsi, [rbp+0E0h+var_148]
0x14001563e  mov     r14, [rbp+0E0h+var_140]
0x140015642  mov     eax, [rbx+80h]
0x140015648  lea     r9, [rbp+0E0h+FileObject]; FileObject
0x14001564c  mov     rdx, [r14+18h]; Instance
0x140015650  lea     r8, [rbp+0E0h+FileHandle]; FileHandle
0x140015654  mov     [rsp+1E0h+DriverContext], 0; DriverContext
0x14001565d  mov     ecx, 1
0x140015662  mov     [rsp+1E0h+Flags], ecx; Flags
0x140015666  mov     [rsp+1E0h+EaLength], 0; EaLength
0x14001566e  mov     [rsp+1E0h+EaBuffer], 0; EaBuffer
0x140015677  mov     [rsp+1E0h+CreateOptions], eax; CreateOptions
0x14001567b  mov     eax, [rbx+7Ch]
0x14001567e  mov     [rsp+1E0h+CreateDisposition], ecx; CreateDisposition
0x140015682  mov     rcx, cs:LuafvDriverData; Filter
0x140015689  mov     [rsp+1E0h+ShareAccess], eax; ShareAccess
0x14001568d  lea     rax, [rbp+0E0h+var_B8]
0x140015691  mov     [rsp+1E0h+FileAttributes], 0; FileAttributes
0x140015699  mov     [rsp+1E0h+AllocationSize], 0; AllocationSize
0x1400156a2  mov     [rsp+1E0h+IoStatusBlock], rax; IoStatusBlock
0x1400156a7  lea     rax, [rbp+0E0h+var_108]
0x1400156ab  mov     [rsp+1E0h+ObjectAttributes], rax; ObjectAttributes
0x1400156b0  mov     eax, [rbx+78h]
0x1400156b3  mov     [rsp+1E0h+DesiredAccess], eax; DesiredAccess
0x1400156b7  call    cs:__imp_FltCreateFileEx2
0x1400156be  nop     dword ptr [rax+rax+00h]
0x1400156c3  mov     r12d, eax
0x1400156c6  test    eax, eax
0x1400156c8  jns     short loc_1400156ED
0x1400156ca  mov     r9d, eax
0x1400156cd  lea     r8, LuafvDelayedSwitchFailed
0x1400156d4  mov     rdx, rdi
0x1400156d7  mov     rcx, rsi
0x1400156da  call    LuafvLogFileError
0x1400156df  mov     qword ptr [rbx+40h], 0
0x1400156e7  mov     [rbx+48h], r12d
0x1400156eb  jmp     short loc_14001572A
0x1400156ed  mov     rax, [rbp+0E0h+FileHandle]
0x1400156f1  mov     [rbx+30h], rax
0x1400156f5  mov     rax, [rbp+0E0h+FileObject]
0x1400156f9  mov     [rbx+38h], rax
0x1400156fd  mov     rax, [rbp+0E0h+FileObject]
0x140015701  mov     [rbx+40h], rax
0x140015705  mov     byte ptr [rbx+4Ch], 1
0x140015709  or      byte ptr [r13+34h], 2
0x14001570e  mov     rax, [rbp+0E0h+FileObject]
0x140015712  mov     rdx, [rbx+18h]
0x140015716  mov     rcx, [rax+28h]
0x14001571a  mov     [rdx+28h], rcx
0x14001571e  mov     rax, [rbp+0E0h+FileObject]
0x140015722  mov     rcx, [rax+30h]
0x140015726  mov     [rdx+30h], rcx
0x14001572a  mov     rbx, [rbx]
0x14001572d  cmp     rbx, r15
0x140015730  jnz     loc_140015642
0x140015736  mov     rdi, [rbp+0E0h+var_118]
0x14001573a  mov     rsi, [rbp+0E0h+var_130]
0x14001573e  mov     r14b, [rbp+0E0h+var_160]
0x140015742  mov     r12, [rbp+0E0h+var_110]
0x140015746  xor     ebx, ebx
0x140015748  test    r14b, r14b
0x14001574b  jz      short loc_140015759
0x14001574d  call    cs:__imp_PsRevertToSelf
0x140015754  nop     dword ptr [rax+rax+00h]
0x140015759  test    rsi, rsi
0x14001575c  jz      short loc_140015799
0x14001575e  test    r14b, r14b
0x140015761  jz      short loc_14001578A
0x140015763  mov     rcx, gs:188h; Thread
0x14001576c  mov     rdx, rsi; Token
0x14001576f  mov     eax, [rbp+0E0h+ImpersonationLevel]
0x140015772  mov     r9b, [rbp+0E0h+EffectiveOnly]; EffectiveOnly
0x140015776  mov     r8b, [rbp+0E0h+CopyOnOpen]; CopyOnOpen
0x14001577a  mov     [rsp+1E0h+DesiredAccess], eax; ImpersonationLevel
0x14001577e  call    cs:__imp_PsImpersonateClient
0x140015785  nop     dword ptr [rax+rax+00h]
0x14001578a  mov     rcx, rsi; ImpersonationToken
0x14001578d  call    cs:__imp_PsDereferenceImpersonationToken
0x140015794  nop     dword ptr [rax+rax+00h]
0x140015799  xor     edx, edx
0x14001579b  mov     rcx, r12
0x14001579e  call    cs:__imp_FltReleasePushLockEx
0x1400157a5  nop     dword ptr [rax+rax+00h]
0x1400157aa  test    ebx, ebx
0x1400157ac  js      loc_140015553
0x1400157b2  cmp     qword ptr [rdi+0F0h], 0
0x1400157ba  jnz     loc_140015553
0x1400157c0  mov     eax, [rdi+0F8h]
0x1400157c6  jmp     loc_140015555
```
