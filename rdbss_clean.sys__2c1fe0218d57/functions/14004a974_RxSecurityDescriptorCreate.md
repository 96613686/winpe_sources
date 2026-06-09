# RxSecurityDescriptorCreate

- ea: `0x14004a974`
- end: `0x14004ad36`
- name: `RxSecurityDescriptorCreate`
- size: `962`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14008321c`

## callees

- `0x140016e20`
- `0x14004a974`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14004a9c3`
- `ntoskrnl!ExAllocatePool2` at `0x14004aad3`
- `ntoskrnl!ExAllocatePool2` at `0x14004abe6`
- `ntoskrnl!ExAllocatePool2` at `0x14004a9c3`
- `ntoskrnl!ExAllocatePool2` at `0x14004aad3`
- `ntoskrnl!ExAllocatePool2` at `0x14004abe6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ace5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004acfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ad17`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bc28`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bc4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bc6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ace5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004acfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004ad17`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bc28`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bc4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bc6c`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14004a9a7`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14004a9a7`
- `ntoskrnl!RtlInitializeSid` at `0x14004aa3a`
- `ntoskrnl!RtlInitializeSid` at `0x14004aa3a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004aaa3`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14004aaa3`
- `ntoskrnl!RtlCreateAcl` at `0x14004ab37`
- `ntoskrnl!RtlCreateAcl` at `0x14004ab37`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14004ab8d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14004ab8d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14004ac40`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14004ac40`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004ac8a`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14004ac8a`

## pseudocode

```c
__int64 __fastcall RxSecurityDescriptorCreate(
        __int64 a1,
        struct _SID_IDENTIFIER_AUTHORITY *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5)
{
  void *v7; // rsi
  struct _ACL *v8; // r14
  __int64 v9; // r15
  void *Pool2; // rax
  void *v11; // r13
  NTSTATUS Acl; // edi
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 i; // rdi
  struct _ACL *v17; // rax
  void *v18; // rax

  v7 = 0;
  v8 = 0;
  v9 = RtlLengthRequiredSid(6u);
  Pool2 = (void *)ExAllocatePool2(258, v9, 1934456914);
  v11 = Pool2;
  if ( !Pool2 )
  {
    Acl = -1073741670;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v14 = 15;
LABEL_6:
      v15 = 3221225626LL;
LABEL_7:
      WPP_SF_d(v13->AttachedDevice, v14, &WPP_001e8d57d6fa39c4469703a163e62a81_Traceguids, v15);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  Acl = RtlInitializeSid(Pool2, a2, 6u);
  if ( Acl < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_48;
    }
    v14 = 16;
    goto LABEL_13;
  }
  for ( i = 0; (unsigned int)i < 6; i = (unsigned int)(i + 1) )
    *RtlSubAuthoritySid(v11, i) = *(_DWORD *)(a4 + 4 * i);
  v17 = (struct _ACL *)ExAllocatePool2(258, (unsigned int)(v9 + 16), 1934456914);
  v8 = v17;
  if ( !v17 )
  {
    Acl = -1073741670;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v14 = 17;
      goto LABEL_6;
    }
    goto LABEL_48;
  }
  Acl = RtlCreateAcl(v17, v9 + 16, 2u);
  if ( Acl < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_48;
    }
    v14 = 18;
    goto LABEL_13;
  }
  Acl = RtlAddAccessAllowedAce(v8, 2u, 1u, v11);
  if ( Acl < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_48;
    }
    v14 = 19;
    goto LABEL_13;
  }
  v18 = (void *)ExAllocatePool2(258, 40, 1934456914);
  v7 = v18;
  if ( !v18 )
  {
    Acl = -1073741670;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v14 = 20;
      goto LABEL_6;
    }
    goto LABEL_48;
  }
  Acl = RtlCreateSecurityDescriptor(v18, 1u);
  if ( Acl < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || !BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      goto LABEL_48;
    }
    v14 = 21;
LABEL_13:
    v15 = (unsigned int)Acl;
    goto LABEL_7;
  }
  Acl = RtlSetDaclSecurityDescriptor(v7, 1u, v8, 0);
  if ( Acl >= 0 )
  {
    *a5 = v7;
    goto LABEL_48;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    v14 = 22;
    goto LABEL_13;
  }
LABEL_48:
  if ( Acl < 0 )
  {
    if ( v7 )
      ExFreePoolWithTag(v7, 0x734D7852u);
    if ( v8 )
      ExFreePoolWithTag(v8, 0x734D7852u);
  }
  if ( v11 )
    ExFreePoolWithTag(v11, 0x734D7852u);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x14004a974  mov     rax, rsp
0x14004a977  push    rbx
0x14004a978  push    rsi
0x14004a979  push    rdi
0x14004a97a  push    r12
0x14004a97c  push    r13
0x14004a97e  push    r14
0x14004a980  push    r15
0x14004a982  sub     rsp, 40h
0x14004a986  mov     r12, r9
0x14004a989  mov     rbx, rdx
0x14004a98c  mov     dword ptr [rax-58h], 0
0x14004a993  xor     esi, esi
0x14004a995  mov     [rax-50h], rsi
0x14004a999  mov     [rax-40h], rsi
0x14004a99d  xor     r14d, r14d
0x14004a9a0  mov     [rax-48h], r14
0x14004a9a4  lea     ecx, [rsi+6]; SubAuthorityCount
0x14004a9a7  call    cs:__imp_RtlLengthRequiredSid
0x14004a9ae  nop     dword ptr [rax+rax+00h]
0x14004a9b3  mov     r15d, eax
0x14004a9b6  mov     edx, eax
0x14004a9b8  mov     ecx, 102h
0x14004a9bd  mov     r8d, 734D7852h
0x14004a9c3  call    cs:__imp_ExAllocatePool2
0x14004a9ca  nop     dword ptr [rax+rax+00h]
0x14004a9cf  mov     r13, rax
0x14004a9d2  mov     [rsp+78h+var_40], rax
0x14004a9d7  test    rax, rax
0x14004a9da  jnz     short loc_14004AA31
0x14004a9dc  mov     edi, 0C000009Ah
0x14004a9e1  mov     [rsp+78h+var_58], edi
0x14004a9e5  lea     rax, WPP_GLOBAL_Control
0x14004a9ec  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a9f3  cmp     rcx, rax
0x14004a9f6  jz      loc_14004ACD4
0x14004a9fc  mov     eax, [rcx+2Ch]
0x14004a9ff  lea     ebx, [rsi+1]
0x14004aa02  test    bl, al
0x14004aa04  jz      loc_14004ACD4
0x14004aa0a  cmp     [rcx+29h], bl
0x14004aa0d  jb      loc_14004ACD4
0x14004aa13  lea     edx, [rsi+0Fh]
0x14004aa16  mov     r9d, 0C000009Ah
0x14004aa1c  lea     r8, WPP_001e8d57d6fa39c4469703a163e62a81_Traceguids
0x14004aa23  mov     rcx, [rcx+18h]
0x14004aa27  call    WPP_SF_d
0x14004aa2c  jmp     loc_14004ACD4
0x14004aa31  mov     r8b, 6; SubAuthorityCount
0x14004aa34  mov     rdx, rbx; IdentifierAuthority
0x14004aa37  mov     rcx, r13; Sid
0x14004aa3a  call    cs:__imp_RtlInitializeSid
0x14004aa41  nop     dword ptr [rax+rax+00h]
0x14004aa46  mov     edi, eax
0x14004aa48  mov     [rsp+78h+var_58], eax
0x14004aa4c  test    eax, eax
0x14004aa4e  jns     short loc_14004AA88
0x14004aa50  lea     rax, WPP_GLOBAL_Control
0x14004aa57  mov     rcx, cs:WPP_GLOBAL_Control
0x14004aa5e  cmp     rcx, rax
0x14004aa61  jz      loc_14004ACD4
0x14004aa67  mov     eax, [rcx+2Ch]
0x14004aa6a  mov     ebx, 1
0x14004aa6f  test    bl, al
0x14004aa71  jz      loc_14004ACD4
0x14004aa77  cmp     [rcx+29h], bl
0x14004aa7a  jb      loc_14004ACD4
0x14004aa80  lea     edx, [rbx+0Fh]
0x14004aa83  mov     r9d, edi
0x14004aa86  jmp     short loc_14004AA1C
0x14004aa88  mov     [rsp+78h+var_54], 0
0x14004aa90  xor     edi, edi
0x14004aa92  lea     ebx, [rdi+1]
0x14004aa95  mov     [rsp+78h+var_54], edi
0x14004aa99  cmp     edi, 6
0x14004aa9c  jnb     short loc_14004AABE
0x14004aa9e  mov     edx, edi; SubAuthority
0x14004aaa0  mov     rcx, r13; Sid
0x14004aaa3  call    cs:__imp_RtlSubAuthoritySid
0x14004aaaa  nop     dword ptr [rax+rax+00h]
0x14004aaaf  mov     rdx, rax
0x14004aab2  mov     eax, edi
0x14004aab4  mov     ecx, [r12+rdi*4]
0x14004aab8  mov     [rdx], ecx
0x14004aaba  add     edi, ebx
0x14004aabc  jmp     short loc_14004AA95
0x14004aabe  lea     edi, [r15+10h]
0x14004aac2  mov     edx, edi
0x14004aac4  mov     r8d, 734D7852h
0x14004aaca  mov     r12d, 102h
0x14004aad0  mov     ecx, r12d
0x14004aad3  call    cs:__imp_ExAllocatePool2
0x14004aada  nop     dword ptr [rax+rax+00h]
0x14004aadf  mov     r14, rax
0x14004aae2  mov     [rsp+78h+var_48], rax
0x14004aae7  test    rax, rax
0x14004aaea  jnz     short loc_14004AB29
0x14004aaec  mov     edi, 0C000009Ah
0x14004aaf1  mov     [rsp+78h+var_58], edi
0x14004aaf5  lea     rax, WPP_GLOBAL_Control
0x14004aafc  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ab03  cmp     rcx, rax
0x14004ab06  jz      loc_14004ACD4
0x14004ab0c  mov     eax, [rcx+2Ch]
0x14004ab0f  test    bl, al
0x14004ab11  jz      loc_14004ACD4
0x14004ab17  cmp     [rcx+29h], bl
0x14004ab1a  jb      loc_14004ACD4
0x14004ab20  lea     edx, [r14+11h]
0x14004ab24  jmp     loc_14004AA16
0x14004ab29  mov     r15d, 2
0x14004ab2f  mov     r8d, r15d; AclRevision
0x14004ab32  mov     edx, edi; AclLength
0x14004ab34  mov     rcx, r14; Acl
0x14004ab37  call    cs:__imp_RtlCreateAcl
0x14004ab3e  nop     dword ptr [rax+rax+00h]
0x14004ab43  mov     edi, eax
0x14004ab45  mov     [rsp+78h+var_58], eax
0x14004ab49  test    eax, eax
0x14004ab4b  jns     short loc_14004AB81
0x14004ab4d  lea     rax, WPP_GLOBAL_Control
0x14004ab54  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ab5b  cmp     rcx, rax
0x14004ab5e  jz      loc_14004ACD4
0x14004ab64  mov     eax, [rcx+2Ch]
0x14004ab67  test    bl, al
0x14004ab69  jz      loc_14004ACD4
0x14004ab6f  cmp     [rcx+29h], bl
0x14004ab72  jb      loc_14004ACD4
0x14004ab78  lea     edx, [r15+10h]
0x14004ab7c  jmp     loc_14004AA83
0x14004ab81  mov     r9, r13; Sid
0x14004ab84  mov     r8d, ebx; AccessMask
0x14004ab87  mov     edx, r15d; AceRevision
0x14004ab8a  mov     rcx, r14; Acl
0x14004ab8d  call    cs:__imp_RtlAddAccessAllowedAce
0x14004ab94  nop     dword ptr [rax+rax+00h]
0x14004ab99  mov     edi, eax
0x14004ab9b  mov     [rsp+78h+var_58], eax
0x14004ab9f  test    eax, eax
0x14004aba1  jns     short loc_14004ABD8
0x14004aba3  lea     rax, WPP_GLOBAL_Control
0x14004abaa  mov     rcx, cs:WPP_GLOBAL_Control
0x14004abb1  cmp     rcx, rax
0x14004abb4  jz      loc_14004ACD4
0x14004abba  mov     eax, [rcx+2Ch]
0x14004abbd  test    bl, al
0x14004abbf  jz      loc_14004ACD4
0x14004abc5  cmp     [rcx+29h], bl
0x14004abc8  jb      loc_14004ACD4
0x14004abce  mov     edx, 13h
0x14004abd3  jmp     loc_14004AA83
0x14004abd8  mov     edx, 28h ; '('
0x14004abdd  mov     r8d, 734D7852h
0x14004abe3  mov     rcx, r12
0x14004abe6  call    cs:__imp_ExAllocatePool2
0x14004abed  nop     dword ptr [rax+rax+00h]
0x14004abf2  mov     rsi, rax
0x14004abf5  mov     [rsp+78h+var_50], rax
0x14004abfa  test    rax, rax
0x14004abfd  jnz     short loc_14004AC3B
0x14004abff  mov     edi, 0C000009Ah
0x14004ac04  mov     [rsp+78h+var_58], edi
0x14004ac08  lea     rax, WPP_GLOBAL_Control
0x14004ac0f  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ac16  cmp     rcx, rax
0x14004ac19  jz      loc_14004ACD4
0x14004ac1f  mov     eax, [rcx+2Ch]
0x14004ac22  test    bl, al
0x14004ac24  jz      loc_14004ACD4
0x14004ac2a  cmp     [rcx+29h], bl
0x14004ac2d  jb      loc_14004ACD4
0x14004ac33  lea     edx, [rsi+14h]
0x14004ac36  jmp     loc_14004AA16
0x14004ac3b  mov     edx, ebx; Revision
0x14004ac3d  mov     rcx, rsi; SecurityDescriptor
0x14004ac40  call    cs:__imp_RtlCreateSecurityDescriptor
0x14004ac47  nop     dword ptr [rax+rax+00h]
0x14004ac4c  mov     edi, eax
0x14004ac4e  mov     [rsp+78h+var_58], eax
0x14004ac52  test    eax, eax
0x14004ac54  jns     short loc_14004AC7F
0x14004ac56  lea     rax, WPP_GLOBAL_Control
0x14004ac5d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ac64  cmp     rcx, rax
0x14004ac67  jz      short loc_14004ACD4
0x14004ac69  mov     eax, [rcx+2Ch]
0x14004ac6c  test    bl, al
0x14004ac6e  jz      short loc_14004ACD4
0x14004ac70  cmp     [rcx+29h], bl
0x14004ac73  jb      short loc_14004ACD4
0x14004ac75  mov     edx, 15h
0x14004ac7a  jmp     loc_14004AA83
0x14004ac7f  xor     r9d, r9d; DaclDefaulted
0x14004ac82  mov     r8, r14; Dacl
0x14004ac85  mov     dl, bl; DaclPresent
0x14004ac87  mov     rcx, rsi; SecurityDescriptor
0x14004ac8a  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14004ac91  nop     dword ptr [rax+rax+00h]
0x14004ac96  mov     edi, eax
0x14004ac98  mov     [rsp+78h+var_58], eax
0x14004ac9c  test    eax, eax
0x14004ac9e  jns     short loc_14004ACC9
0x14004aca0  lea     rax, WPP_GLOBAL_Control
0x14004aca7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004acae  cmp     rcx, rax
0x14004acb1  jz      short loc_14004ACD4
0x14004acb3  mov     eax, [rcx+2Ch]
0x14004acb6  test    bl, al
0x14004acb8  jz      short loc_14004ACD4
0x14004acba  cmp     [rcx+29h], bl
0x14004acbd  jb      short loc_14004ACD4
0x14004acbf  mov     edx, 16h
0x14004acc4  jmp     loc_14004AA83
0x14004acc9  mov     rax, [rsp+78h+arg_20]
0x14004acd1  mov     [rax], rsi
0x14004acd4  test    edi, edi
0x14004acd6  jns     short loc_14004AD0A
0x14004acd8  test    rsi, rsi
0x14004acdb  jz      short loc_14004ACF1
0x14004acdd  mov     edx, 734D7852h; Tag
0x14004ace2  mov     rcx, rsi; P
0x14004ace5  call    cs:__imp_ExFreePoolWithTag
0x14004acec  nop     dword ptr [rax+rax+00h]
0x14004acf1  test    r14, r14
0x14004acf4  jz      short loc_14004AD0A
0x14004acf6  mov     edx, 734D7852h; Tag
0x14004acfb  mov     rcx, r14; P
0x14004acfe  call    cs:__imp_ExFreePoolWithTag
0x14004ad05  nop     dword ptr [rax+rax+00h]
0x14004ad0a  test    r13, r13
0x14004ad0d  jz      short loc_14004AD23
0x14004ad0f  mov     edx, 734D7852h; Tag
0x14004ad14  mov     rcx, r13; P
0x14004ad17  call    cs:__imp_ExFreePoolWithTag
0x14004ad1e  nop     dword ptr [rax+rax+00h]
0x14004ad23  mov     eax, edi
0x14004ad25  add     rsp, 40h
0x14004ad29  pop     r15
0x14004ad2b  pop     r14
0x14004ad2d  pop     r13
0x14004ad2f  pop     r12
0x14004ad31  pop     rdi
0x14004ad32  pop     rsi
0x14004ad33  pop     rbx
0x14004ad34  retn
0x14007bc0b  push    rbp
0x14007bc0d  sub     rsp, 20h
0x14007bc11  mov     rbp, rdx
0x14007bc14  cmp     dword ptr [rbp+20h], 0
0x14007bc18  jge     short loc_14007BC5E
0x14007bc1a  mov     rcx, [rbp+28h]; P
0x14007bc1e  test    rcx, rcx
0x14007bc21  jz      short loc_14007BC3C
0x14007bc23  mov     edx, 734D7852h; Tag
0x14007bc28  call    cs:__imp_ExFreePoolWithTag
0x14007bc2f  nop     dword ptr [rax+rax+00h]
0x14007bc34  mov     qword ptr [rbp+28h], 0
0x14007bc3c  mov     rcx, [rbp+30h]; P
0x14007bc40  test    rcx, rcx
0x14007bc43  jz      short loc_14007BC5E
0x14007bc45  mov     edx, 734D7852h; Tag
0x14007bc4a  call    cs:__imp_ExFreePoolWithTag
0x14007bc51  nop     dword ptr [rax+rax+00h]
0x14007bc56  mov     qword ptr [rbp+30h], 0
0x14007bc5e  mov     rcx, [rbp+38h]; P
0x14007bc62  test    rcx, rcx
0x14007bc65  jz      short loc_14007BC80
0x14007bc67  mov     edx, 734D7852h; Tag
0x14007bc6c  call    cs:__imp_ExFreePoolWithTag
0x14007bc73  nop     dword ptr [rax+rax+00h]
0x14007bc78  mov     qword ptr [rbp+38h], 0
0x14007bc80  add     rsp, 20h
0x14007bc84  pop     rbp
0x14007bc85  retn
```
