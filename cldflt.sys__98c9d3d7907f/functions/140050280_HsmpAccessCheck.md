# HsmpAccessCheck

- ea: `0x140050280`
- end: `0x140050624`
- name: `HsmpAccessCheck`
- size: `932`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140033f48`
- `0x14003baf0`
- `0x14004f5f0`
- `0x14006079c`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14001e140`
- `0x140050280`

## import_xrefs

- `ntoskrnl!SeReleaseSubjectContext` at `0x140050475`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140050475`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140050431`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400504f6`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140050431`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400504f6`
- `ntoskrnl!SeLockSubjectContext` at `0x1400503ac`
- `ntoskrnl!SeLockSubjectContext` at `0x1400504b0`
- `ntoskrnl!SeLockSubjectContext` at `0x1400503ac`
- `ntoskrnl!SeLockSubjectContext` at `0x1400504b0`
- `ntoskrnl!SePrivilegeCheck` at `0x1400504de`
- `ntoskrnl!SePrivilegeCheck` at `0x1400504de`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14005039a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14005049e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14005039a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14005049e`
- `ntoskrnl!SeAccessCheck` at `0x1400503fb`
- `ntoskrnl!SeAccessCheck` at `0x1400505b0`
- `ntoskrnl!SeAccessCheck` at `0x1400503fb`
- `ntoskrnl!SeAccessCheck` at `0x1400505b0`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400503bb`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005056d`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400503bb`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14005056d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005041c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005041c`
- `ntoskrnl!ExAllocatePool2` at `0x14005033b`
- `ntoskrnl!ExAllocatePool2` at `0x14005033b`
- `FLTMGR!FltQuerySecurityObject` at `0x14005030e`
- `FLTMGR!FltQuerySecurityObject` at `0x14005036f`
- `FLTMGR!FltQuerySecurityObject` at `0x14005030e`
- `FLTMGR!FltQuerySecurityObject` at `0x14005036f`

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
        WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a2);
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
      WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a2);
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
0x140050280  mov     r11, rsp
0x140050283  push    rbp
0x140050284  lea     rbp, [r11-5Fh]
0x140050288  sub     rsp, 0D0h
0x14005028f  mov     rax, cs:__security_cookie
0x140050296  xor     rax, rsp
0x140050299  mov     [rbp+57h+var_38], rax
0x14005029d  mov     [r11-10h], rbx
0x1400502a1  xorps   xmm0, xmm0
0x1400502a4  mov     [r11-18h], rsi
0x1400502a8  xor     eax, eax
0x1400502aa  mov     [r11-20h], rdi
0x1400502ae  xor     bl, bl
0x1400502b0  mov     [r11-28h], r12
0x1400502b4  mov     rsi, rcx
0x1400502b7  xor     r12d, r12d
0x1400502ba  mov     [r11-30h], r14
0x1400502be  mov     [r11-38h], r15
0x1400502c2  mov     r14d, r8d
0x1400502c5  mov     [rbp+57h+AccessStatus], r12d
0x1400502c9  mov     r15, rdx
0x1400502cc  mov     [rbp+57h+var_7C], r12d
0x1400502d0  mov     [rbp+57h+var_78], r12d
0x1400502d4  mov     [rbp+57h+RequiredPrivileges.Privilege.Attributes], eax
0x1400502d7  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x1400502db  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x1400502df  movups  xmmword ptr [rbp+57h+RequiredPrivileges.PrivilegeCount], xmm0
0x1400502e3  test    r8b, 6
0x1400502e7  jnz     loc_14005049A
0x1400502ed  mov     rcx, [rsi+20h]; Instance
0x1400502f1  lea     rax, [rbp+57h+var_7C]
0x1400502f5  mov     [rsp+0D0h+LengthNeeded], rax; LengthNeeded
0x1400502fa  xor     r9d, r9d; SecurityDescriptor
0x1400502fd  mov     r8d, 1FFh; SecurityInformation
0x140050303  mov     [rsp+0D0h+Length], r12d; Length
0x140050308  mov     rdx, r15; FileObject
0x14005030b  mov     rdi, r12
0x14005030e  call    cs:__imp_FltQuerySecurityObject
0x140050315  nop     dword ptr [rax+rax+00h]
0x14005031a  mov     ecx, eax
0x14005031c  mov     [rbp+57h+AccessStatus], eax
0x14005031f  call    HsmDbgBreakOnStatus
0x140050324  cmp     [rbp+57h+AccessStatus], 0C0000023h
0x14005032b  jnz     short loc_140050385
0x14005032d  mov     edx, [rbp+57h+var_7C]
0x140050330  mov     ecx, 100h
0x140050335  mov     r8d, 64537348h
0x14005033b  call    cs:__imp_ExAllocatePool2
0x140050342  nop     dword ptr [rax+rax+00h]
0x140050347  mov     rdi, rax
0x14005034a  test    rax, rax
0x14005034d  jz      loc_140050507
0x140050353  mov     eax, [rbp+57h+var_7C]
0x140050356  mov     r9, rdi; SecurityDescriptor
0x140050359  mov     rcx, [rsi+20h]; Instance
0x14005035d  mov     r8d, 1FFh; SecurityInformation
0x140050363  mov     [rsp+0D0h+LengthNeeded], r12; LengthNeeded
0x140050368  mov     rdx, r15; FileObject
0x14005036b  mov     [rsp+0D0h+Length], eax; Length
0x14005036f  call    cs:__imp_FltQuerySecurityObject
0x140050376  nop     dword ptr [rax+rax+00h]
0x14005037b  mov     ecx, eax
0x14005037d  mov     [rbp+57h+AccessStatus], eax
0x140050380  call    HsmDbgBreakOnStatus
0x140050385  mov     r8d, [rbp+57h+AccessStatus]
0x140050389  test    r8d, r8d
0x14005038c  js      loc_1400505DA
0x140050392  test    bl, bl
0x140050394  jnz     short loc_1400503A8
0x140050396  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14005039a  call    cs:__imp_SeCaptureSubjectContext
0x1400503a1  nop     dword ptr [rax+rax+00h]
0x1400503a6  mov     bl, 1
0x1400503a8  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400503ac  call    cs:__imp_SeLockSubjectContext
0x1400503b3  nop     dword ptr [rax+rax+00h]
0x1400503b8  mov     sil, 1
0x1400503bb  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400503c2  nop     dword ptr [rax+rax+00h]
0x1400503c7  lea     rcx, [rbp+57h+AccessStatus]
0x1400503cb  mov     r9d, r14d; DesiredAccess
0x1400503ce  mov     [rsp+48h], rcx; AccessStatus
0x1400503d3  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x1400503d7  lea     rcx, [rbp+57h+var_78]
0x1400503db  movzx   r8d, sil; SubjectContextLocked
0x1400503df  mov     [rsp+0D0h+GrantedAccess], rcx; GrantedAccess
0x1400503e4  mov     rcx, rdi; SecurityDescriptor
0x1400503e7  mov     [rsp+0D0h+AccessMode], sil; AccessMode
0x1400503ec  mov     [rsp+0D0h+GenericMapping], rax; GenericMapping
0x1400503f1  mov     [rsp+0D0h+LengthNeeded], r12; Privileges
0x1400503f6  mov     [rsp+0D0h+Length], r12d; PreviouslyGrantedAccess
0x1400503fb  call    cs:__imp_SeAccessCheck
0x140050402  nop     dword ptr [rax+rax+00h]
0x140050407  test    al, al
0x140050409  jz      loc_14005056D
0x14005040f  test    rdi, rdi
0x140050412  jz      short loc_140050428
0x140050414  mov     edx, 64537348h; Tag
0x140050419  mov     rcx, rdi; P
0x14005041c  call    cs:__imp_ExFreePoolWithTag
0x140050423  nop     dword ptr [rax+rax+00h]
0x140050428  test    sil, sil
0x14005042b  jz      short loc_14005043D
0x14005042d  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140050431  call    cs:__imp_SeUnlockSubjectContext
0x140050438  nop     dword ptr [rax+rax+00h]
0x14005043d  mov     r15, [rsp+0D0h+var_30]
0x140050445  test    bl, bl
0x140050447  mov     rbx, [rsp+0C8h]
0x14005044f  mov     r14, [rsp+0D0h+var_28]
0x140050457  mov     r12, [rsp+0D0h+var_20]
0x14005045f  mov     rdi, [rsp+0D0h+var_18]
0x140050467  mov     rsi, [rsp+0D0h+var_10]
0x14005046f  jz      short loc_140050481
0x140050471  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140050475  call    cs:__imp_SeReleaseSubjectContext
0x14005047c  nop     dword ptr [rax+rax+00h]
0x140050481  mov     eax, [rbp+57h+AccessStatus]
0x140050484  mov     rcx, [rbp+57h+var_38]
0x140050488  xor     rcx, rsp; StackCookie
0x14005048b  call    __security_check_cookie
0x140050490  add     rsp, 0D0h
0x140050497  pop     rbp
0x140050498  retn
0x14005049a  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14005049e  call    cs:__imp_SeCaptureSubjectContext
0x1400504a5  nop     dword ptr [rax+rax+00h]
0x1400504aa  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400504ae  mov     bl, 1
0x1400504b0  call    cs:__imp_SeLockSubjectContext
0x1400504b7  nop     dword ptr [rax+rax+00h]
0x1400504bc  movzx   r8d, bl; AccessMode
0x1400504c0  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], 1
0x1400504c7  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x1400504cb  mov     [rbp+57h+RequiredPrivileges.Control], 1
0x1400504d2  lea     rcx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x1400504d6  mov     qword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], 12h
0x1400504de  call    cs:__imp_SePrivilegeCheck
0x1400504e5  nop     dword ptr [rax+rax+00h]
0x1400504ea  test    al, al
0x1400504ec  jnz     loc_14005042D
0x1400504f2  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x1400504f6  call    cs:__imp_SeUnlockSubjectContext
0x1400504fd  nop     dword ptr [rax+rax+00h]
0x140050502  jmp     loc_1400502ED
0x140050507  mov     ecx, 0C000009Ah
0x14005050c  mov     [rbp+57h+AccessStatus], 0C000009Ah
0x140050513  call    HsmDbgBreakOnStatus
0x140050518  mov     rcx, cs:WPP_GLOBAL_Control
0x14005051f  lea     rax, WPP_GLOBAL_Control
0x140050526  cmp     rcx, rax
0x140050529  jz      loc_14005043D
0x14005052f  mov     eax, [rcx+2Ch]
0x140050532  test    al, 8
0x140050534  jz      loc_14005043D
0x14005053a  cmp     byte ptr [rcx+29h], 2
0x14005053e  jb      loc_14005043D
0x140050544  mov     eax, [rbp+57h+AccessStatus]
0x140050547  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005054e  mov     rcx, [rcx+18h]
0x140050552  mov     edx, 11h
0x140050557  mov     dword ptr [rsp+0D0h+LengthNeeded], eax
0x14005055b  mov     r9, rsi
0x14005055e  mov     qword ptr [rsp+0D0h+Length], r15
0x140050563  call    WPP_SF_qqd
0x140050568  jmp     loc_14005043D
0x14005056d  call    cs:__imp_IoGetFileObjectGenericMapping
0x140050574  nop     dword ptr [rax+rax+00h]
0x140050579  lea     rcx, [rbp+57h+AccessStatus]
0x14005057d  mov     r9d, 40000h; DesiredAccess
0x140050583  mov     [rsp+48h], rcx; AccessStatus
0x140050588  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x14005058c  lea     rcx, [rbp+57h+var_78]
0x140050590  movzx   r8d, sil; SubjectContextLocked
0x140050594  mov     [rsp+0D0h+GrantedAccess], rcx; GrantedAccess
0x140050599  mov     rcx, rdi; SecurityDescriptor
0x14005059c  mov     [rsp+0D0h+AccessMode], sil; AccessMode
0x1400505a1  mov     [rsp+0D0h+GenericMapping], rax; GenericMapping
0x1400505a6  mov     [rsp+0D0h+LengthNeeded], r12; Privileges
0x1400505ab  mov     [rsp+0D0h+Length], r12d; PreviouslyGrantedAccess
0x1400505b0  call    cs:__imp_SeAccessCheck
0x1400505b7  nop     dword ptr [rax+rax+00h]
0x1400505bc  test    al, al
0x1400505be  jnz     loc_14005040F
0x1400505c4  mov     ecx, 0C000CF18h
0x1400505c9  mov     [rbp+57h+AccessStatus], 0C000CF18h
0x1400505d0  call    HsmDbgBreakOnStatus
0x1400505d5  jmp     loc_14005040F
0x1400505da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400505e1  lea     rax, WPP_GLOBAL_Control
0x1400505e8  cmp     rcx, rax
0x1400505eb  jz      short loc_14005061C
0x1400505ed  mov     eax, [rcx+2Ch]
0x1400505f0  test    al, 8
0x1400505f2  jz      short loc_14005061C
0x1400505f4  cmp     byte ptr [rcx+29h], 2
0x1400505f8  jb      short loc_14005061C
0x1400505fa  mov     rcx, [rcx+18h]
0x1400505fe  mov     edx, 12h
0x140050603  mov     dword ptr [rsp+0D0h+LengthNeeded], r8d
0x140050608  mov     r9, rsi
0x14005060b  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x140050612  mov     qword ptr [rsp+0D0h+Length], r15
0x140050617  call    WPP_SF_qqd
0x14005061c  xor     sil, sil
0x14005061f  jmp     loc_14005040F
```
