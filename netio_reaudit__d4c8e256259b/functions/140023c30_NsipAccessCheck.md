# NsipAccessCheck

- ea: `0x140023c30`
- end: `0x140023feb`
- name: `NsipAccessCheck`
- size: `955`
- prototype: ``
- caller_count: `6`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140021820`
- `0x140021d30`
- `0x140022080`
- `0x140023160`
- `0x140024cc0`
- `0x140025b90`

## callees

- `0x140023c30`
- `0x140023ff4`
- `0x140024220`
- `0x140050ea4`
- `0x1400605c8`
- `0x140077fa0`
- `0x140078920`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140023ee1`
- `ntoskrnl!ZwClose` at `0x140023ee1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140023ce1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140023ce1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023e2c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023e93`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023e2c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140023e93`
- `ntoskrnl!SeAccessCheck` at `0x140023ded`
- `ntoskrnl!SeAccessCheck` at `0x140023ded`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x140023d9a`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x140023d9a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140023cf6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140023cf6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023e20`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023e87`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023e20`
- `ntoskrnl!ExReleaseResourceLite` at `0x140023e87`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140023e0d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140023e0d`
- `ntoskrnl!PsGetCurrentProcess` at `0x140023d7e`
- `ntoskrnl!PsGetCurrentProcess` at `0x140023d7e`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140023dfd`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140023dfd`
- `ntoskrnl!SeLockSubjectContext` at `0x140023daa`
- `ntoskrnl!SeLockSubjectContext` at `0x140023daa`

## pseudocode

```c
__int64 __fastcall NsipAccessCheck(unsigned int *a1, char a2, char a3)
{
  ACCESS_MASK v3; // r15d
  __int64 v5; // rcx
  unsigned int *v8; // rdi
  __int64 v9; // r9
  __int64 *i; // rbx
  int v11; // eax
  __int64 v12; // rax
  unsigned int v13; // edx
  void *v14; // rdi
  struct _KPROCESS *CurrentProcess; // rax
  unsigned int v16; // r8d
  __int64 result; // rax
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  int AccessStatus; // [rsp+50h] [rbp-39h] BYREF
  __int64 GrantedAccess; // [rsp+54h] [rbp-35h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-29h] BYREF
  _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v24[24]; // [rsp+88h] [rbp-1h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+A0h] [rbp+17h] BYREF

  GenericMapping.GenericWrite = 131078;
  AccessStatus = 0;
  Handle = 0;
  v3 = 131097;
  GrantedAccess = 0;
  v5 = *a1;
  GenericMapping.GenericRead = 131097;
  GenericMapping.GenericExecute = 131097;
  GenericMapping.GenericAll = 983103;
  memset(v24, 0, 22);
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  if ( !(_DWORD)v5 && !*((_QWORD *)a1 + 1) )
    return 3221225485LL;
  v8 = (unsigned int *)*((_QWORD *)a1 + 1);
  if ( !v8 )
  {
    result = NsipFindModuleGuidByModuleId(v5, v24);
    AccessStatus = result;
    if ( (int)result < 0 )
      return result;
    v8 = (unsigned int *)v24;
  }
  v9 = v8[1];
  if ( (_DWORD)v9 == 1 )
  {
    if ( a2 != 1 )
    {
      if ( a3 == 1 )
        v3 = 196639;
      else
        v3 = 131103;
    }
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(&NsipCachedRegistryKeyListLock, 1u);
    for ( i = (__int64 *)qword_14009ADF0; ; i = (__int64 *)*i )
    {
      if ( i == (__int64 *)&qword_14009ADF0 || (v11 = memcmp((char *)i + 44, v8, 0x18u), v11 > 0) )
      {
        i = &NsipCachedRegistryKeyList;
        goto LABEL_23;
      }
      if ( v11 >= 0 )
        break;
    }
    v12 = i[2];
    v13 = a1[4];
    while ( (__int64 *)v12 != i + 2 && *(_DWORD *)(v12 + 44) <= v13 )
    {
      if ( *(_DWORD *)(v12 + 44) >= v13 )
      {
        v14 = *(void **)(v12 + 32);
        if ( !v14 )
        {
          v14 = (void *)qword_14009AE00;
          if ( i[4] )
            v14 = (void *)i[4];
        }
        AccessStatus = 0;
        CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
        SeCaptureSubjectContextEx(KeGetCurrentThread(), CurrentProcess, &SubjectContext);
        SeLockSubjectContext(&SubjectContext);
        SeAccessCheck(
          v14,
          &SubjectContext,
          1u,
          v3,
          0,
          0,
          &GenericMapping,
          1,
          (PACCESS_MASK)&GrantedAccess + 1,
          &AccessStatus);
        SeUnlockSubjectContext(&SubjectContext);
        SeReleaseSubjectContext(&SubjectContext);
        ExReleaseResourceLite(&NsipCachedRegistryKeyListLock);
        KeLeaveCriticalRegion();
        v16 = AccessStatus;
        if ( AccessStatus < 0 )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
          {
            v19 = 30;
            goto LABEL_44;
          }
        }
        return v16;
      }
      v12 = *(_QWORD *)v12;
    }
LABEL_23:
    ExReleaseResourceLite(&NsipCachedRegistryKeyListLock);
    KeLeaveCriticalRegion();
    AccessStatus = NsipOpenInformationObjectKeyOrParent(&Handle, (__int64)&GrantedAccess);
    v16 = AccessStatus;
    if ( AccessStatus < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        v19 = 31;
LABEL_44:
        WPP_SF_d(v18->AttachedDevice, v19, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids, v16);
        return (unsigned int)AccessStatus;
      }
      return v16;
    }
    else
    {
      NsipInsertCachedNode(Handle, GrantedAccess, (int)v8, a1[4], i);
      ZwClose(Handle);
      return (unsigned int)AccessStatus;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids, v9);
    }
    return 3221225659LL;
  }
}

```

## disassembly

```asm
0x140023c30  mov     [rsp-8+arg_8], rbx
0x140023c35  mov     [rsp-8+arg_10], rsi
0x140023c3a  push    rbp
0x140023c3b  push    rdi
0x140023c3c  push    r12
0x140023c3e  push    r14
0x140023c40  push    r15
0x140023c42  lea     rbp, [rsp-37h]
0x140023c47  sub     rsp, 0C0h
0x140023c4e  mov     rax, cs:__security_cookie
0x140023c55  xor     rax, rsp
0x140023c58  mov     [rbp+57h+var_30], rax
0x140023c5c  xor     r12d, r12d
0x140023c5f  mov     [rbp+57h+var_40.GenericWrite], 20006h
0x140023c66  xor     eax, eax
0x140023c68  mov     [rbp+57h+var_90], r12d
0x140023c6c  xorps   xmm1, xmm1
0x140023c6f  mov     [rbp+57h+Handle], r12
0x140023c73  mov     r15d, 20019h
0x140023c79  mov     dword ptr [rbp+57h+var_8C], r12d
0x140023c7d  mov     r14, rcx
0x140023c80  mov     dword ptr [rbp+57h+var_8C+4], r12d
0x140023c84  mov     ecx, [rcx]
0x140023c86  xorps   xmm0, xmm0
0x140023c89  mov     [rbp+57h+var_40.GenericRead], r15d
0x140023c8d  movzx   esi, r8b
0x140023c91  mov     [rbp+57h+var_40.GenericExecute], r15d
0x140023c95  movzx   ebx, dl
0x140023c98  mov     [rbp+57h+var_40.GenericAll], 0F003Fh
0x140023c9f  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x140023ca3  mov     qword ptr [rbp+57h+var_58+0Eh], rax
0x140023ca7  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm1
0x140023cab  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm1
0x140023caf  test    ecx, ecx
0x140023cb1  jnz     short loc_140023CBD
0x140023cb3  cmp     [r14+8], rax
0x140023cb7  jz      loc_140023F7D
0x140023cbd  mov     rdi, [r14+8]
0x140023cc1  test    rdi, rdi
0x140023cc4  jz      loc_140023F87
0x140023cca  mov     r9d, [rdi+4]
0x140023cce  cmp     r9d, 1
0x140023cd2  jnz     loc_140023FA4
0x140023cd8  cmp     bl, r9b
0x140023cdb  jnz     loc_140023F61
0x140023ce1  call    cs:__imp_KeEnterCriticalRegion
0x140023ce8  nop     dword ptr [rax+rax+00h]
0x140023ced  mov     dl, 1; Wait
0x140023cef  lea     rcx, NsipCachedRegistryKeyListLock; Resource
0x140023cf6  call    cs:__imp_ExAcquireResourceSharedLite
0x140023cfd  nop     dword ptr [rax+rax+00h]
0x140023d02  mov     rbx, cs:qword_14009ADF0
0x140023d09  lea     rsi, qword_14009ADF0
0x140023d10  cmp     rbx, rsi
0x140023d13  jz      loc_140023E71
0x140023d19  lea     rcx, [rbx+2Ch]; Buf1
0x140023d1d  mov     r8d, 18h; Size
0x140023d23  mov     rdx, rdi; Buf2
0x140023d26  call    memcmp
0x140023d2b  test    eax, eax
0x140023d2d  jg      loc_140023E71
0x140023d33  jns     short loc_140023D3A
0x140023d35  mov     rbx, [rbx]
0x140023d38  jmp     short loc_140023D10
0x140023d3a  mov     rax, [rbx+10h]
0x140023d3e  lea     r8, [rbx+10h]
0x140023d42  mov     edx, [r14+10h]
0x140023d46  cmp     rax, r8
0x140023d49  jz      loc_140023E78
0x140023d4f  cmp     [rax+2Ch], edx
0x140023d52  ja      loc_140023E78
0x140023d58  jnb     short loc_140023D5F
0x140023d5a  mov     rax, [rax]
0x140023d5d  jmp     short loc_140023D46
0x140023d5f  mov     rdi, [rax+20h]
0x140023d63  test    rdi, rdi
0x140023d66  jnz     short loc_140023D7A
0x140023d68  mov     rax, [rbx+20h]
0x140023d6c  mov     rdi, cs:qword_14009AE00
0x140023d73  test    rax, rax
0x140023d76  cmovnz  rdi, rax
0x140023d7a  mov     [rbp+57h+var_90], r12d
0x140023d7e  call    cs:__imp_PsGetCurrentProcess
0x140023d85  nop     dword ptr [rax+rax+00h]
0x140023d8a  mov     rcx, gs:188h; Thread
0x140023d93  lea     r8, [rbp+57h+SubjectContext]; SubjectContext
0x140023d97  mov     rdx, rax; Process
0x140023d9a  call    cs:__imp_SeCaptureSubjectContextEx
0x140023da1  nop     dword ptr [rax+rax+00h]
0x140023da6  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140023daa  call    cs:__imp_SeLockSubjectContext
0x140023db1  nop     dword ptr [rax+rax+00h]
0x140023db6  lea     rax, [rbp+57h+var_90]
0x140023dba  mov     r9d, r15d; DesiredAccess
0x140023dbd  mov     [rsp+0E0h+AccessStatus], rax; AccessStatus
0x140023dc2  lea     rdx, [rbp+57h+SubjectContext]; SubjectSecurityContext
0x140023dc6  lea     rax, [rbp+57h+var_8C+4]
0x140023dca  mov     r8b, 1; SubjectContextLocked
0x140023dcd  mov     [rsp+0E0h+GrantedAccess], rax; GrantedAccess
0x140023dd2  mov     rcx, rdi; SecurityDescriptor
0x140023dd5  mov     [rsp+0E0h+AccessMode], 1; AccessMode
0x140023dda  lea     rax, [rbp+57h+var_40]
0x140023dde  mov     [rsp+0E0h+GenericMapping], rax; GenericMapping
0x140023de3  mov     [rsp+0E0h+Privileges], r12; Privileges
0x140023de8  mov     [rsp+0E0h+PreviouslyGrantedAccess], r12d; PreviouslyGrantedAccess
0x140023ded  call    cs:__imp_SeAccessCheck
0x140023df4  nop     dword ptr [rax+rax+00h]
0x140023df9  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140023dfd  call    cs:__imp_SeUnlockSubjectContext
0x140023e04  nop     dword ptr [rax+rax+00h]
0x140023e09  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x140023e0d  call    cs:__imp_SeReleaseSubjectContext
0x140023e14  nop     dword ptr [rax+rax+00h]
0x140023e19  lea     rcx, NsipCachedRegistryKeyListLock; Resource
0x140023e20  call    cs:__imp_ExReleaseResourceLite
0x140023e27  nop     dword ptr [rax+rax+00h]
0x140023e2c  call    cs:__imp_KeLeaveCriticalRegion
0x140023e33  nop     dword ptr [rax+rax+00h]
0x140023e38  mov     r8d, [rbp+57h+var_90]
0x140023e3c  test    r8d, r8d
0x140023e3f  js      loc_140023F2B
0x140023e45  mov     eax, r8d
0x140023e48  mov     rcx, [rbp+57h+var_30]
0x140023e4c  xor     rcx, rsp; StackCookie
0x140023e4f  call    __security_check_cookie
0x140023e54  lea     r11, [rsp+0E0h+var_20]
0x140023e5c  mov     rbx, [r11+38h]
0x140023e60  mov     rsi, [r11+40h]
0x140023e64  mov     rsp, r11
0x140023e67  pop     r15
0x140023e69  pop     r14
0x140023e6b  pop     r12
0x140023e6d  pop     rdi
0x140023e6e  pop     rbp
0x140023e6f  retn
0x140023e71  lea     rbx, NsipCachedRegistryKeyList
0x140023e78  mov     eax, 0C0000225h
0x140023e7d  lea     rcx, NsipCachedRegistryKeyListLock; Resource
0x140023e84  mov     [rbp+57h+var_90], eax
0x140023e87  call    cs:__imp_ExReleaseResourceLite
0x140023e8e  nop     dword ptr [rax+rax+00h]
0x140023e93  call    cs:__imp_KeLeaveCriticalRegion
0x140023e9a  nop     dword ptr [rax+rax+00h]
0x140023e9f  mov     r8d, [r14+10h]
0x140023ea3  lea     rax, [rbp+57h+var_8C]
0x140023ea7  mov     r9d, r15d
0x140023eaa  mov     qword ptr [rsp+0E0h+PreviouslyGrantedAccess], rax; __int64
0x140023eaf  mov     rdx, rdi
0x140023eb2  lea     rcx, [rbp+57h+Handle]; KeyHandle
0x140023eb6  call    NsipOpenInformationObjectKeyOrParent
0x140023ebb  mov     [rbp+57h+var_90], eax
0x140023ebe  mov     r8d, eax
0x140023ec1  test    eax, eax
0x140023ec3  js      short loc_140023EF5
0x140023ec5  mov     r9d, [r14+10h]
0x140023ec9  mov     r8, rdi
0x140023ecc  mov     edx, dword ptr [rbp+57h+var_8C]
0x140023ecf  mov     rcx, [rbp+57h+Handle]
0x140023ed3  mov     qword ptr [rsp+0E0h+PreviouslyGrantedAccess], rbx
0x140023ed8  call    NsipInsertCachedNode
0x140023edd  mov     rcx, [rbp+57h+Handle]; Handle
0x140023ee1  call    cs:__imp_ZwClose
0x140023ee8  nop     dword ptr [rax+rax+00h]
0x140023eed  mov     eax, [rbp+57h+var_90]
0x140023ef0  jmp     loc_140023E48
0x140023ef5  mov     rcx, cs:WPP_GLOBAL_Control
0x140023efc  lea     rax, WPP_GLOBAL_Control
0x140023f03  cmp     rcx, rax
0x140023f06  jz      loc_140023E45
0x140023f0c  cmp     byte ptr [rcx+29h], 2
0x140023f10  jb      loc_140023E45
0x140023f16  mov     eax, [rcx+2Ch]
0x140023f19  test    al, 10h
0x140023f1b  jz      loc_140023E45
0x140023f21  mov     edx, 1Fh
0x140023f26  jmp     loc_14007B3D2
0x140023f2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023f32  lea     rax, WPP_GLOBAL_Control
0x140023f39  cmp     rcx, rax
0x140023f3c  jz      loc_140023E45
0x140023f42  cmp     byte ptr [rcx+29h], 2
0x140023f46  jb      loc_140023E45
0x140023f4c  mov     eax, [rcx+2Ch]
0x140023f4f  test    al, 10h
0x140023f51  jz      loc_140023E45
0x140023f57  mov     edx, 1Eh
0x140023f5c  jmp     loc_14007B3D2
0x140023f61  cmp     sil, 1
0x140023f65  jz      short loc_140023F72
0x140023f67  mov     r15d, 2001Fh
0x140023f6d  jmp     loc_140023CE1
0x140023f72  mov     r15d, 3001Fh
0x140023f78  jmp     loc_140023CE1
0x140023f7d  mov     eax, 0C000000Dh
0x140023f82  jmp     loc_140023E48
0x140023f87  lea     rdx, [rbp+57h+var_58]
0x140023f8b  call    NsipFindModuleGuidByModuleId
0x140023f90  mov     [rbp+57h+var_90], eax
0x140023f93  test    eax, eax
0x140023f95  js      loc_140023E48
0x140023f9b  lea     rdi, [rbp+57h+var_58]
0x140023f9f  jmp     loc_140023CCA
0x140023fa4  mov     rcx, cs:WPP_GLOBAL_Control
0x140023fab  lea     rax, WPP_GLOBAL_Control
0x140023fb2  cmp     rcx, rax
0x140023fb5  jz      loc_14007B3C8
0x140023fbb  cmp     byte ptr [rcx+29h], 2
0x140023fbf  jb      loc_14007B3C8
0x140023fc5  mov     eax, [rcx+2Ch]
0x140023fc8  test    al, 10h
0x140023fca  jz      loc_14007B3C8
0x140023fd0  mov     rcx, [rcx+18h]
0x140023fd4  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x140023fdb  mov     edx, 1Dh
0x140023fe0  call    WPP_SF_d
0x140023fe5  nop
0x140023fe6  jmp     loc_14007B3C8
0x14007b3c8  mov     eax, 0C00000BBh
0x14007b3cd  jmp     loc_140023E48
0x14007b3d2  mov     rcx, [rcx+18h]
0x14007b3d6  mov     r9d, r8d
0x14007b3d9  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x14007b3e0  call    WPP_SF_d
0x14007b3e5  mov     r8d, [rbp+57h+var_90]
0x14007b3e9  jmp     loc_140023E45
```
