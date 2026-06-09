# HsmpAccessCheck

- ea: `0x1400503a0`
- end: `0x140050744`
- name: `HsmpAccessCheck`
- size: `932`
- prototype: `__int64 __fastcall(__int64, struct _FILE_OBJECT *, ACCESS_MASK)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140033f48`
- `0x14003bb10`
- `0x14004f710`
- `0x1400608bc`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14001e1c0`
- `0x1400503a0`

## import_xrefs

- `ntoskrnl!SeReleaseSubjectContext` at `0x140050595`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140050595`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140050551`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140050616`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140050551`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140050616`
- `ntoskrnl!SeLockSubjectContext` at `0x1400504cc`
- `ntoskrnl!SeLockSubjectContext` at `0x1400505d0`
- `ntoskrnl!SeLockSubjectContext` at `0x1400504cc`
- `ntoskrnl!SeLockSubjectContext` at `0x1400505d0`
- `ntoskrnl!SePrivilegeCheck` at `0x1400505fe`
- `ntoskrnl!SePrivilegeCheck` at `0x1400505fe`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400504ba`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400505be`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400504ba`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400505be`
- `ntoskrnl!SeAccessCheck` at `0x14005051b`
- `ntoskrnl!SeAccessCheck` at `0x1400506d0`
- `ntoskrnl!SeAccessCheck` at `0x14005051b`
- `ntoskrnl!SeAccessCheck` at `0x1400506d0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400504db`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005068d`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400504db`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005068d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005053c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005053c`
- `ntoskrnl!ExAllocatePool2` at `0x14005045b`
- `ntoskrnl!ExAllocatePool2` at `0x14005045b`
- `FLTMGR!FltQuerySecurityObject` at `0x14005042e`
- `FLTMGR!FltQuerySecurityObject` at `0x14005048f`
- `FLTMGR!FltQuerySecurityObject` at `0x14005042e`
- `FLTMGR!FltQuerySecurityObject` at `0x14005048f`

## pseudocode

```c
__int64 __fastcall HsmpAccessCheck(__int64 a1, struct _FILE_OBJECT *a2, ACCESS_MASK a3)
{
  char v3; // bl
  void *Pool2; // rdi
  char v8; // si
  struct _GENERIC_MAPPING *GenericMapping; // rax
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  int AccessStatus; // [rsp+58h] [rbp-29h] BYREF
  ULONG LengthNeeded; // [rsp+5Ch] [rbp-25h] BYREF
  DWORD GrantedAccess; // [rsp+60h] [rbp-21h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+68h] [rbp-19h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+88h] [rbp+7h] BYREF

  v3 = 0;
  AccessStatus = 0;
  LengthNeeded = 0;
  GrantedAccess = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  if ( (a3 & 6) != 0 )
  {
    SeCaptureSubjectContext(&SubjectContext);
    v3 = 1;
    SeLockSubjectContext(&SubjectContext);
    RequiredPrivileges.PrivilegeCount = 1;
    RequiredPrivileges.Control = 1;
    RequiredPrivileges.Privilege[0].Luid = (LUID)18LL;
    if ( SePrivilegeCheck(&RequiredPrivileges, &SubjectContext, 1) )
    {
LABEL_12:
      SeUnlockSubjectContext(&SubjectContext);
      goto LABEL_13;
    }
    SeUnlockSubjectContext(&SubjectContext);
  }
  Pool2 = 0;
  AccessStatus = FltQuerySecurityObject(*(PFLT_INSTANCE *)(a1 + 32), a2, 0x1FFu, 0, 0, &LengthNeeded);
  HsmDbgBreakOnStatus((unsigned int)AccessStatus);
  if ( AccessStatus == -1073741789 )
  {
    Pool2 = (void *)ExAllocatePool2(256, LengthNeeded, 1683190600);
    if ( !Pool2 )
    {
      AccessStatus = -1073741670;
      HsmDbgBreakOnStatus(3221225626LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
          a1,
          a2,
          AccessStatus);
      }
      goto LABEL_13;
    }
    AccessStatus = FltQuerySecurityObject(*(PFLT_INSTANCE *)(a1 + 32), a2, 0x1FFu, Pool2, LengthNeeded, 0);
    HsmDbgBreakOnStatus((unsigned int)AccessStatus);
  }
  if ( AccessStatus < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
        a1,
        a2,
        AccessStatus);
    }
    v8 = 0;
  }
  else
  {
    if ( !v3 )
    {
      SeCaptureSubjectContext(&SubjectContext);
      v3 = 1;
    }
    SeLockSubjectContext(&SubjectContext);
    v8 = 1;
    GenericMapping = IoGetFileObjectGenericMapping();
    if ( !SeAccessCheck(Pool2, &SubjectContext, 1u, a3, 0, 0, GenericMapping, 1, &GrantedAccess, &AccessStatus) )
    {
      FileObjectGenericMapping = IoGetFileObjectGenericMapping();
      if ( !SeAccessCheck(
              Pool2,
              &SubjectContext,
              1u,
              0x40000u,
              0,
              0,
              FileObjectGenericMapping,
              1,
              &GrantedAccess,
              &AccessStatus) )
      {
        AccessStatus = -1073688808;
        HsmDbgBreakOnStatus(3221278488LL);
      }
    }
  }
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x64537348u);
  if ( v8 )
    goto LABEL_12;
LABEL_13:
  if ( v3 )
    SeReleaseSubjectContext(&SubjectContext);
  return (unsigned int)AccessStatus;
}

```

## disassembly

```asm
0x1400503a0  mov     r11, rsp
0x1400503a3  push    rbp
0x1400503a4  lea     rbp, [r11-5Fh]
0x1400503a8  sub     rsp, 0D0h
0x1400503af  mov     rax, cs:__security_cookie
0x1400503b6  xor     rax, rsp
0x1400503b9  mov     [rbp+57h+var_38], rax
0x1400503bd  mov     [r11-10h], rbx
0x1400503c1  xorps   xmm0, xmm0
0x1400503c4  mov     [r11-18h], rsi
0x1400503c8  xor     eax, eax
0x1400503ca  mov     [r11-20h], rdi
0x1400503ce  xor     bl, bl
0x1400503d0  mov     [r11-28h], r12
0x1400503d4  mov     rsi, rcx
0x1400503d7  xor     r12d, r12d
0x1400503da  mov     [r11-30h], r14
0x1400503de  mov     [r11-38h], r15
0x1400503e2  mov     r14d, r8d
0x1400503e5  mov     [rbp+57h+AccessStatus], r12d
0x1400503e9  mov     r15, rdx
0x1400503ec  mov     [rbp+57h+var_7C], r12d
0x1400503f0  mov     [rbp+57h+var_78], r12d
0x1400503f4  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x1400503f7  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x1400503fb  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x1400503ff  movups  xmmword ptr [rbp+57h+RequiredPrivileges.PrivilegeCount], xmm0
0x140050403  test    r8b, 6
0x140050407  jnz     loc_1400505BA
0x14005040d  mov     rcx, [rsi+20h]; Instance
0x140050411  lea     rax, [rbp+57h+var_7C]
0x140050415  mov     [rsp+0D0h+LengthNeeded], rax; LengthNeeded
0x14005041a  xor     r9d, r9d; SecurityDescriptor
0x14005041d  mov     r8d, 1FFh; SecurityInformation
0x140050423  mov     [rsp+0D0h+Length], r12d; Length
0x140050428  mov     rdx, r15; FileObject
0x14005042b  mov     rdi, r12
0x14005042e  call    cs:__imp_FltQuerySecurityObject
0x140050435  nop     dword ptr [rax+rax+00h]
0x14005043a  mov     ecx, eax
0x14005043c  mov     [rbp+57h+AccessStatus], eax
0x14005043f  call    HsmDbgBreakOnStatus
0x140050444  cmp     [rbp+57h+AccessStatus], 0C0000023h
0x14005044b  jnz     short loc_1400504A5
0x14005044d  mov     edx, [rbp+57h+var_7C]
0x140050450  mov     ecx, 100h
0x140050455  mov     r8d, 64537348h
0x14005045b  call    cs:__imp_ExAllocatePool2
0x140050462  nop     dword ptr [rax+rax+00h]
0x140050467  mov     rdi, rax
0x14005046a  test    rax, rax
0x14005046d  jz      loc_140050627
0x140050473  mov     eax, [rbp+57h+var_7C]
0x140050476  mov     r9, rdi; SecurityDescriptor
0x140050479  mov     rcx, [rsi+20h]; Instance
0x14005047d  mov     r8d, 1FFh; SecurityInformation
0x140050483  mov     [rsp+0D0h+LengthNeeded], r12; LengthNeeded
0x140050488  mov     rdx, r15; FileObject
0x14005048b  mov     [rsp+0D0h+Length], eax; Length
0x14005048f  call    cs:__imp_FltQuerySecurityObject
0x140050496  nop     dword ptr [rax+rax+00h]
0x14005049b  mov     ecx, eax
0x14005049d  mov     [rbp+57h+AccessStatus], eax
0x1400504a0  call    HsmDbgBreakOnStatus
0x1400504a5  mov     r8d, [rbp+57h+AccessStatus]
0x1400504a9  test    r8d, r8d
0x1400504ac  js      loc_1400506FA
0x1400504b2  test    bl, bl
0x1400504b4  jnz     short loc_1400504C8
0x1400504b6  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400504ba  call    cs:__imp_SeCaptureSubjectContext
0x1400504c1  nop     dword ptr [rax+rax+00h]
0x1400504c6  mov     bl, 1
0x1400504c8  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400504cc  call    cs:__imp_SeLockSubjectContext
0x1400504d3  nop     dword ptr [rax+rax+00h]
0x1400504d8  mov     sil, 1
0x1400504db  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400504e2  nop     dword ptr [rax+rax+00h]
0x1400504e7  lea     rcx, [rbp+57h+AccessStatus]
0x1400504eb  mov     r9d, r14d; DesiredAccess
0x1400504ee  mov     [rsp+48h], rcx; AccessStatus
0x1400504f3  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x1400504f7  lea     rcx, [rbp+57h+var_78]
0x1400504fb  movzx   r8d, sil; SubjectContextLocked
0x1400504ff  mov     [rsp+0D0h+GrantedAccess], rcx; GrantedAccess
0x140050504  mov     rcx, rdi; SecurityDescriptor
0x140050507  mov     [rsp+0D0h+AccessMode], sil; AccessMode
0x14005050c  mov     [rsp+0D0h+GenericMapping], rax; GenericMapping
0x140050511  mov     [rsp+0D0h+LengthNeeded], r12; Privileges
0x140050516  mov     [rsp+0D0h+Length], r12d; PreviouslyGrantedAccess
0x14005051b  call    cs:__imp_SeAccessCheck
0x140050522  nop     dword ptr [rax+rax+00h]
0x140050527  test    al, al
0x140050529  jz      loc_14005068D
0x14005052f  test    rdi, rdi
0x140050532  jz      short loc_140050548
0x140050534  mov     edx, 64537348h; Tag
0x140050539  mov     rcx, rdi; P
0x14005053c  call    cs:__imp_ExFreePoolWithTag
0x140050543  nop     dword ptr [rax+rax+00h]
0x140050548  test    sil, sil
0x14005054b  jz      short loc_14005055D
0x14005054d  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140050551  call    cs:__imp_SeUnlockSubjectContext
0x140050558  nop     dword ptr [rax+rax+00h]
0x14005055d  mov     r15, [rsp+0D0h+var_30]
0x140050565  test    bl, bl
0x140050567  mov     rbx, [rsp+0C8h]
0x14005056f  mov     r14, [rsp+0D0h+var_28]
0x140050577  mov     r12, [rsp+0D0h+var_20]
0x14005057f  mov     rdi, [rsp+0D0h+var_18]
0x140050587  mov     rsi, [rsp+0D0h+var_10]
0x14005058f  jz      short loc_1400505A1
0x140050591  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140050595  call    cs:__imp_SeReleaseSubjectContext
0x14005059c  nop     dword ptr [rax+rax+00h]
0x1400505a1  mov     eax, [rbp+57h+AccessStatus]
0x1400505a4  mov     rcx, [rbp+57h+var_38]
0x1400505a8  xor     rcx, rsp; StackCookie
0x1400505ab  call    __security_check_cookie
0x1400505b0  add     rsp, 0D0h
0x1400505b7  pop     rbp
0x1400505b8  retn
0x1400505ba  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400505be  call    cs:__imp_SeCaptureSubjectContext
0x1400505c5  nop     dword ptr [rax+rax+00h]
0x1400505ca  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400505ce  mov     bl, 1
0x1400505d0  call    cs:__imp_SeLockSubjectContext
0x1400505d7  nop     dword ptr [rax+rax+00h]
0x1400505dc  movzx   r8d, bl; AccessMode
0x1400505e0  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], 1
0x1400505e7  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x1400505eb  mov     [rbp+57h+RequiredPrivileges.Control], 1
0x1400505f2  lea     rcx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x1400505f6  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x1400505fe  call    cs:__imp_SePrivilegeCheck
0x140050605  nop     dword ptr [rax+rax+00h]
0x14005060a  test    al, al
0x14005060c  jnz     loc_14005054D
0x140050612  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140050616  call    cs:__imp_SeUnlockSubjectContext
0x14005061d  nop     dword ptr [rax+rax+00h]
0x140050622  jmp     loc_14005040D
0x140050627  mov     ecx, 0C000009Ah
0x14005062c  mov     [rbp+57h+AccessStatus], 0C000009Ah
0x140050633  call    HsmDbgBreakOnStatus
0x140050638  mov     rcx, cs:WPP_GLOBAL_Control
0x14005063f  lea     rax, WPP_GLOBAL_Control
0x140050646  cmp     rcx, rax
0x140050649  jz      loc_14005055D
0x14005064f  mov     eax, [rcx+2Ch]
0x140050652  test    al, 8
0x140050654  jz      loc_14005055D
0x14005065a  cmp     byte ptr [rcx+29h], 2
0x14005065e  jb      loc_14005055D
0x140050664  mov     eax, [rbp+57h+AccessStatus]
0x140050667  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005066e  mov     rcx, [rcx+18h]
0x140050672  mov     edx, 11h
0x140050677  mov     dword ptr [rsp+0D0h+LengthNeeded], eax
0x14005067b  mov     r9, rsi
0x14005067e  mov     qword ptr [rsp+0D0h+Length], r15
0x140050683  call    WPP_SF_qqd
0x140050688  jmp     loc_14005055D
0x14005068d  call    cs:__imp_IoGetFileObjectGenericMapping
0x140050694  nop     dword ptr [rax+rax+00h]
0x140050699  lea     rcx, [rbp+57h+AccessStatus]
0x14005069d  mov     r9d, 40000h; DesiredAccess
0x1400506a3  mov     [rsp+48h], rcx; AccessStatus
0x1400506a8  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x1400506ac  lea     rcx, [rbp+57h+var_78]
0x1400506b0  movzx   r8d, sil; SubjectContextLocked
0x1400506b4  mov     [rsp+0D0h+GrantedAccess], rcx; GrantedAccess
0x1400506b9  mov     rcx, rdi; SecurityDescriptor
0x1400506bc  mov     [rsp+0D0h+AccessMode], sil; AccessMode
0x1400506c1  mov     [rsp+0D0h+GenericMapping], rax; GenericMapping
0x1400506c6  mov     [rsp+0D0h+LengthNeeded], r12; Privileges
0x1400506cb  mov     [rsp+0D0h+Length], r12d; PreviouslyGrantedAccess
0x1400506d0  call    cs:__imp_SeAccessCheck
0x1400506d7  nop     dword ptr [rax+rax+00h]
0x1400506dc  test    al, al
0x1400506de  jnz     loc_14005052F
0x1400506e4  mov     ecx, 0C000CF18h
0x1400506e9  mov     [rbp+57h+AccessStatus], 0C000CF18h
0x1400506f0  call    HsmDbgBreakOnStatus
0x1400506f5  jmp     loc_14005052F
0x1400506fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140050701  lea     rax, WPP_GLOBAL_Control
0x140050708  cmp     rcx, rax
0x14005070b  jz      short loc_14005073C
0x14005070d  mov     eax, [rcx+2Ch]
0x140050710  test    al, 8
0x140050712  jz      short loc_14005073C
0x140050714  cmp     byte ptr [rcx+29h], 2
0x140050718  jb      short loc_14005073C
0x14005071a  mov     rcx, [rcx+18h]
0x14005071e  mov     edx, 12h
0x140050723  mov     dword ptr [rsp+0D0h+LengthNeeded], r8d
0x140050728  mov     r9, rsi
0x14005072b  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x140050732  mov     qword ptr [rsp+0D0h+Length], r15
0x140050737  call    WPP_SF_qqd
0x14005073c  xor     sil, sil
0x14005073f  jmp     loc_14005052F
```
