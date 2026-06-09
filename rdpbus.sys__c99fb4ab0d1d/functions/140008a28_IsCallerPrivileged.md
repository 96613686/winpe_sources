# IsCallerPrivileged

- ea: `0x140008a28`
- end: `0x140008c71`
- name: `IsCallerPrivileged`
- size: `585`
- prototype: `BOOLEAN __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000890c`

## callees

- `0x1400020b4`
- `0x1400020e4`
- `0x140008a28`

## import_xrefs

- `ntoskrnl!SeFreePrivileges` at `0x140008bac`
- `ntoskrnl!SeFreePrivileges` at `0x140008bac`
- `ntoskrnl!RtlMapGenericMask` at `0x140008b1f`
- `ntoskrnl!RtlMapGenericMask` at `0x140008b1f`
- `ntoskrnl!SeAccessCheck` at `0x140008b94`
- `ntoskrnl!SeAccessCheck` at `0x140008b94`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140008b05`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x140008b05`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140008bbb`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140008bbb`
- `ntoskrnl!SeLockSubjectContext` at `0x140008b32`
- `ntoskrnl!SeLockSubjectContext` at `0x140008b32`

## pseudocode

```c
BOOLEAN __fastcall IsCallerPrivileged(__int64 a1, __int64 a2)
{
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rbx
  struct _SECURITY_SUBJECT_CONTEXT *v7; // rbp
  struct _GENERIC_MAPPING *GenericMapping; // r14
  struct _SECURITY_SUBJECT_CONTEXT *v9; // rbp
  KPROCESSOR_MODE AccessMode; // cl
  BOOLEAN v11; // bl
  PPRIVILEGE_SET Privileges; // [rsp+50h] [rbp-38h] BYREF
  DWORD AccessMask; // [rsp+90h] [rbp+8h] BYREF
  int AccessStatus; // [rsp+A0h] [rbp+18h] BYREF
  DWORD GrantedAccess; // [rsp+A8h] [rbp+20h] BYREF

  Privileges = 0;
  GrantedAccess = 0;
  AccessMask = 0x10000000;
  AccessStatus = 0;
  if ( !a1 || !a2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 0;
    v5 = 29;
    goto LABEL_30;
  }
  if ( *(_BYTE *)a2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 0;
    v5 = 30;
LABEL_30:
    WPP_SF_(v4->AttachedDevice, v5, WPP_decc11c9483a3275477ae1b226799886_Traceguids);
    return 0;
  }
  if ( !*(_QWORD *)&WPP_MAIN_CB.DeviceType )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 0;
    v5 = 31;
    goto LABEL_30;
  }
  v6 = *(_QWORD *)(a2 + 8);
  if ( !v6 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      return 0;
    v5 = 32;
    goto LABEL_30;
  }
  v7 = *(struct _SECURITY_SUBJECT_CONTEXT **)(v6 + 8);
  GenericMapping = IoGetFileObjectGenericMapping();
  RtlMapGenericMask(&AccessMask, GenericMapping);
  v9 = v7 + 1;
  SeLockSubjectContext(v9);
  AccessMode = 1;
  if ( (*(_BYTE *)(a2 + 2) & 1) == 0 )
    AccessMode = *(_BYTE *)(a1 + 64);
  v11 = SeAccessCheck(
          *(PSECURITY_DESCRIPTOR *)&WPP_MAIN_CB.DeviceType,
          v9,
          1u,
          AccessMask,
          0,
          &Privileges,
          GenericMapping,
          AccessMode,
          &GrantedAccess,
          &AccessStatus);
  if ( Privileges )
    SeFreePrivileges(Privileges);
  SeUnlockSubjectContext(v9);
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_decc11c9483a3275477ae1b226799886_Traceguids);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      WPP_decc11c9483a3275477ae1b226799886_Traceguids,
      (unsigned int)AccessStatus);
  }
  return v11;
}

```

## disassembly

```asm
0x140008a28  mov     rax, rsp
0x140008a2b  push    rbx
0x140008a2c  push    rbp
0x140008a2d  push    rsi
0x140008a2e  push    rdi
0x140008a2f  push    r14
0x140008a31  sub     rsp, 60h
0x140008a35  mov     qword ptr [rax-38h], 0
0x140008a3d  mov     rdi, rdx
0x140008a40  mov     dword ptr [rax+20h], 0
0x140008a47  mov     rsi, rcx
0x140008a4a  mov     dword ptr [rax+8], 10000000h
0x140008a51  mov     dword ptr [rax+18h], 0
0x140008a58  test    rcx, rcx
0x140008a5b  jz      loc_140008C35
0x140008a61  test    rdx, rdx
0x140008a64  jz      loc_140008C35
0x140008a6a  cmp     byte ptr [rdx], 0
0x140008a6d  jz      short loc_140008A9A
0x140008a6f  mov     rcx, cs:WPP_GLOBAL_Control
0x140008a76  lea     rax, WPP_GLOBAL_Control
0x140008a7d  cmp     rcx, rax
0x140008a80  jz      loc_140008C63
0x140008a86  cmp     byte ptr [rcx+29h], 2
0x140008a8a  jb      loc_140008C63
0x140008a90  mov     edx, 1Eh
0x140008a95  jmp     loc_140008C53
0x140008a9a  cmp     qword ptr cs:WPP_MAIN_CB.DeviceType, 0
0x140008aa2  jnz     short loc_140008ACF
0x140008aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x140008aab  lea     rax, WPP_GLOBAL_Control
0x140008ab2  cmp     rcx, rax
0x140008ab5  jz      loc_140008C63
0x140008abb  cmp     byte ptr [rcx+29h], 2
0x140008abf  jb      loc_140008C63
0x140008ac5  mov     edx, 1Fh
0x140008aca  jmp     loc_140008C53
0x140008acf  mov     rbx, [rdx+8]
0x140008ad3  test    rbx, rbx
0x140008ad6  jnz     short loc_140008B01
0x140008ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x140008adf  lea     rax, WPP_GLOBAL_Control
0x140008ae6  cmp     rcx, rax
0x140008ae9  jz      loc_140008C63
0x140008aef  cmp     byte ptr [rcx+29h], 2
0x140008af3  jb      loc_140008C63
0x140008af9  lea     edx, [rbx+20h]
0x140008afc  jmp     loc_140008C53
0x140008b01  mov     rbp, [rbx+8]
0x140008b05  call    cs:__imp_IoGetFileObjectGenericMapping
0x140008b0c  nop     dword ptr [rax+rax+00h]
0x140008b11  mov     rdx, rax; GenericMapping
0x140008b14  lea     rcx, [rsp+88h+AccessMask]; AccessMask
0x140008b1c  mov     r14, rax
0x140008b1f  call    cs:__imp_RtlMapGenericMask
0x140008b26  nop     dword ptr [rax+rax+00h]
0x140008b2b  add     rbp, 20h ; ' '
0x140008b2f  mov     rcx, rbp; SubjectContext
0x140008b32  call    cs:__imp_SeLockSubjectContext
0x140008b39  nop     dword ptr [rax+rax+00h]
0x140008b3e  mov     r8b, 1; SubjectContextLocked
0x140008b41  mov     cl, r8b
0x140008b44  test    [rdi+2], r8b
0x140008b48  jnz     short loc_140008B4D
0x140008b4a  mov     cl, [rsi+40h]
0x140008b4d  mov     r9d, [rsp+88h+AccessMask]; DesiredAccess
0x140008b55  lea     rax, [rsp+88h+arg_10]
0x140008b5d  mov     [rsp+88h+AccessStatus], rax; AccessStatus
0x140008b62  mov     rdx, rbp; SubjectSecurityContext
0x140008b65  lea     rax, [rsp+88h+arg_18]
0x140008b6d  mov     [rsp+88h+GrantedAccess], rax; GrantedAccess
0x140008b72  lea     rax, [rsp+88h+var_38]
0x140008b77  mov     [rsp+88h+AccessMode], cl; AccessMode
0x140008b7b  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceType; SecurityDescriptor
0x140008b82  mov     [rsp+88h+GenericMapping], r14; GenericMapping
0x140008b87  mov     [rsp+88h+Privileges], rax; Privileges
0x140008b8c  mov     [rsp+88h+PreviouslyGrantedAccess], 0; PreviouslyGrantedAccess
0x140008b94  call    cs:__imp_SeAccessCheck
0x140008b9b  nop     dword ptr [rax+rax+00h]
0x140008ba0  mov     rcx, [rsp+88h+var_38]; Privileges
0x140008ba5  mov     bl, al
0x140008ba7  test    rcx, rcx
0x140008baa  jz      short loc_140008BB8
0x140008bac  call    cs:__imp_SeFreePrivileges
0x140008bb3  nop     dword ptr [rax+rax+00h]
0x140008bb8  mov     rcx, rbp; SubjectContext
0x140008bbb  call    cs:__imp_SeUnlockSubjectContext
0x140008bc2  nop     dword ptr [rax+rax+00h]
0x140008bc7  test    bl, bl
0x140008bc9  jz      short loc_140008BFB
0x140008bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140008bd2  lea     rax, WPP_GLOBAL_Control
0x140008bd9  cmp     rcx, rax
0x140008bdc  jz      short loc_140008C31
0x140008bde  cmp     byte ptr [rcx+29h], 4
0x140008be2  jb      short loc_140008C31
0x140008be4  mov     rcx, [rcx+18h]
0x140008be8  lea     r8, WPP_decc11c9483a3275477ae1b226799886_Traceguids
0x140008bef  mov     edx, 21h ; '!'
0x140008bf4  call    WPP_SF_
0x140008bf9  jmp     short loc_140008C31
0x140008bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c02  lea     rax, WPP_GLOBAL_Control
0x140008c09  cmp     rcx, rax
0x140008c0c  jz      short loc_140008C31
0x140008c0e  cmp     byte ptr [rcx+29h], 4
0x140008c12  jb      short loc_140008C31
0x140008c14  mov     r9d, [rsp+88h+arg_10]
0x140008c1c  lea     r8, WPP_decc11c9483a3275477ae1b226799886_Traceguids
0x140008c23  mov     rcx, [rcx+18h]
0x140008c27  mov     edx, 22h ; '"'
0x140008c2c  call    WPP_SF_D
0x140008c31  mov     al, bl
0x140008c33  jmp     short loc_140008C65
0x140008c35  mov     rcx, cs:WPP_GLOBAL_Control
0x140008c3c  lea     rax, WPP_GLOBAL_Control
0x140008c43  cmp     rcx, rax
0x140008c46  jz      short loc_140008C63
0x140008c48  cmp     byte ptr [rcx+29h], 2
0x140008c4c  jb      short loc_140008C63
0x140008c4e  mov     edx, 1Dh
0x140008c53  mov     rcx, [rcx+18h]
0x140008c57  lea     r8, WPP_decc11c9483a3275477ae1b226799886_Traceguids
0x140008c5e  call    WPP_SF_
0x140008c63  xor     al, al
0x140008c65  add     rsp, 60h
0x140008c69  pop     r14
0x140008c6b  pop     rdi
0x140008c6c  pop     rsi
0x140008c6d  pop     rbp
0x140008c6e  pop     rbx
0x140008c6f  retn
```
