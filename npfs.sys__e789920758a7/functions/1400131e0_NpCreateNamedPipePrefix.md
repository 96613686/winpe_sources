# NpCreateNamedPipePrefix

- ea: `0x1400131e0`
- end: `0x1400137cd`
- name: `NpCreateNamedPipePrefix`
- size: `1517`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_PREFIX_TABLE *, __int64, struct _SECURITY_SUBJECT_CONTEXT *, ACCESS_MASK DesiredAccess, KPROCESSOR_MODE PreviousMode, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140011490`

## callees

- `0x140001f40`
- `0x140002240`
- `0x140012730`
- `0x1400131e0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001326d`
- `ntoskrnl!ExAllocatePool2` at `0x1400132d7`
- `ntoskrnl!ExAllocatePool2` at `0x14001326d`
- `ntoskrnl!ExAllocatePool2` at `0x1400132d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400133ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400133ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136cf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136e0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140013409`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140013409`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140013428`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140013428`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001368a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001368a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013696`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013696`
- `ntoskrnl!SeFreePrivileges` at `0x140013793`
- `ntoskrnl!SeFreePrivileges` at `0x1400137b0`
- `ntoskrnl!SeFreePrivileges` at `0x140013793`
- `ntoskrnl!SeFreePrivileges` at `0x1400137b0`
- `ntoskrnl!SeAccessCheck` at `0x140013565`
- `ntoskrnl!SeAccessCheck` at `0x140013646`
- `ntoskrnl!SeAccessCheck` at `0x140013565`
- `ntoskrnl!SeAccessCheck` at `0x140013646`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14001337a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14001351c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400135ff`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14001337a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14001351c`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400135ff`
- `ntoskrnl!SeAssignSecurity` at `0x1400133b1`
- `ntoskrnl!SeAssignSecurity` at `0x1400133b1`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x1400136b8`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x1400136b8`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x14001359d`
- `ntoskrnl!RtlInsertUnicodePrefix` at `0x14001359d`
- `ntoskrnl!KeInitializeEvent` at `0x140013310`
- `ntoskrnl!KeInitializeEvent` at `0x140013310`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x1400134f0`
- `ntoskrnl!SeSinglePrivilegeCheck` at `0x1400134f0`
- `ntoskrnl!SeExports` at `0x1400134db`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x1400133d9`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x1400133d9`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001348c`
- `ntoskrnl!RtlFindUnicodePrefix` at `0x14001348c`

## pseudocode

```c
__int64 __fastcall NpCreateNamedPipePrefix(
        __int64 a1,
        struct _UNICODE_PREFIX_TABLE *a2,
        __int64 a3,
        struct _SECURITY_SUBJECT_CONTEXT *a4,
        ACCESS_MASK DesiredAccess,
        KPROCESSOR_MODE PreviousMode,
        int a7)
{
  unsigned __int16 v7; // r14
  int v8; // ebx
  __int16 v11; // r12
  USHORT v12; // r14
  USHORT v13; // si
  char *Pool2; // rax
  char *v15; // rdi
  char v16; // al
  __int64 v17; // rax
  _WORD *v18; // rdx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  PACCESS_TOKEN ClientToken; // rdx
  USHORT v21; // r12
  __int64 v22; // r8
  __int64 v23; // r9
  struct _UNICODE_PREFIX_TABLE *v24; // rbx
  struct _UNICODE_PREFIX_TABLE *v25; // r12
  PUNICODE_PREFIX_TABLE_ENTRY UnicodePrefix; // rax
  PUNICODE_STRING *p_Prefix; // rsi
  unsigned __int64 RightChild_low; // rcx
  KPROCESSOR_MODE AccessMode; // r14
  PUNICODE_STRING v30; // rbx
  struct _GENERIC_MAPPING *FileObjectGenericMapping; // rax
  BOOLEAN v32; // bl
  __int64 Prefix; // rsi
  void *v34; // rbx
  struct _GENERIC_MAPPING *v35; // rax
  BOOLEAN v36; // bl
  __int64 v37; // rcx
  void *v38; // rcx
  int v39; // eax
  char *v41; // rsi
  char **v42; // rax
  PPRIVILEGE_SET Privileges; // [rsp+50h] [rbp-51h] BYREF
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+58h] [rbp-49h] BYREF
  _WORD *v45; // [rsp+60h] [rbp-41h]
  PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext; // [rsp+68h] [rbp-39h]
  struct _UNICODE_PREFIX_TABLE *v47; // [rsp+70h] [rbp-31h]
  UNICODE_STRING FullName; // [rsp+80h] [rbp-21h] BYREF
  UNICODE_STRING v49; // [rsp+90h] [rbp-11h] BYREF
  int AccessStatus; // [rsp+F0h] [rbp+4Fh] BYREF
  struct _UNICODE_PREFIX_TABLE *v51; // [rsp+F8h] [rbp+57h]
  DWORD GrantedAccess; // [rsp+100h] [rbp+5Fh] BYREF
  struct _SECURITY_SUBJECT_CONTEXT *v53; // [rsp+108h] [rbp+67h]

  v53 = a4;
  v51 = a2;
  v7 = *(_WORD *)(a3 + 88);
  v8 = *(_DWORD *)(a3 + 92);
  AccessStatus = 0;
  NewDescriptor = 0;
  Privileges = 0;
  GrantedAccess = 0;
  *(_OWORD *)a1 = 0;
  v49 = 0;
  if ( v7 <= 2u || (v45 = *(_WORD **)(a3 + 96), *v45 != 92) )
  {
    v39 = -1073741811;
    goto LABEL_35;
  }
  v11 = *(_WORD *)(a3 + 90);
  v12 = v7 - 2;
  v13 = v12;
  Pool2 = (char *)ExAllocatePool2(257, v12 + 408LL, 1884319822);
  v15 = Pool2;
  if ( !Pool2 )
  {
    v39 = -1073741670;
    goto LABEL_35;
  }
  memset(Pool2, 0, 0x198u);
  v16 = v15[7];
  v15[4] |= 0x40u;
  v15[6] |= 2u;
  v15[7] = v16 & 0xF | 0x50;
  *((_QWORD *)v15 + 8) = v15 + 56;
  *((_QWORD *)v15 + 7) = v15 + 56;
  *((_QWORD *)v15 + 9) = 0;
  *((_QWORD *)v15 + 10) = 0;
  *((_QWORD *)v15 + 11) = 0;
  *((_QWORD *)v15 + 12) = 0;
  *((_DWORD *)v15 + 26) = 0;
  *((_QWORD *)v15 + 14) = 0;
  v17 = ExAllocatePool2(65, 56, 1884319822);
  *((_QWORD *)v15 + 6) = v17;
  if ( !v17 )
  {
    AccessStatus = -1073741670;
    goto LABEL_29;
  }
  *(_DWORD *)v17 = 1;
  *(_QWORD *)(v17 + 8) = 0;
  *(_DWORD *)(v17 + 16) = 0;
  KeInitializeEvent((PRKEVENT)(v17 + 24), SynchronizationEvent, 0);
  v18 = v45;
  *(_DWORD *)v15 = 26739203;
  *((_DWORD *)v15 + 30) = 1;
  *((_DWORD *)v15 + 31) = 1;
  *((_QWORD *)v15 + 30) = v15 + 232;
  *((_QWORD *)v15 + 29) = v15 + 232;
  *((_QWORD *)v15 + 32) = v15 + 248;
  *((_QWORD *)v15 + 31) = v15 + 248;
  *((_QWORD *)v15 + 21) = v15 + 408;
  *((_WORD *)v15 + 80) = v12;
  *((_WORD *)v15 + 81) = v12;
  memmove(v15 + 408, v18 + 1, v12);
  GenericMapping = IoGetFileObjectGenericMapping();
  ClientToken = v53[2].ClientToken;
  SubjectSecurityContext = v53 + 1;
  AccessStatus = SeAssignSecurity(0, ClientToken, &NewDescriptor, 0, v53 + 1, GenericMapping, PagedPool);
  if ( AccessStatus < 0 )
    goto LABEL_29;
  AccessStatus = ObLogSecurityDescriptor(NewDescriptor, v15 + 152, 1);
  ExFreePoolWithTag(NewDescriptor, 0);
  if ( AccessStatus < 0 )
    goto LABEL_29;
  v21 = v11 - 2;
  KeEnterCriticalRegion();
  v47 = v51 + 8;
  ExAcquirePushLockExclusiveEx(&v51[8], 0, v22, v23);
  FullName.Length = v12;
  FullName.MaximumLength = v21;
  *(_DWORD *)(&FullName.MaximumLength + 1) = v8;
  FullName.Buffer = v45 + 1;
  if ( v12 >= 2u && v45[1] == 92 )
  {
    v13 = v12 - 2;
    FullName.MaximumLength = v21 - 2;
    FullName.Buffer = v45 + 2;
    FullName.Length = v12 - 2;
  }
  v24 = v51;
  v25 = v51 + 9;
  UnicodePrefix = RtlFindUnicodePrefix(v51 + 9, &FullName, v13);
  if ( UnicodePrefix )
  {
    p_Prefix = &UnicodePrefix[-4].Prefix;
    RightChild_low = LOWORD(UnicodePrefix[-1].Links.RightChild);
    v49.Length = FullName.Length - RightChild_low;
    v49.MaximumLength = FullName.Length - RightChild_low;
    v49.Buffer = &FullName.Buffer[RightChild_low >> 1];
    if ( LOWORD(UnicodePrefix[-4].Prefix) != 515 )
      p_Prefix = 0;
  }
  else
  {
    p_Prefix = 0;
    v49 = FullName;
  }
  AccessMode = PreviousMode;
  if ( SeSinglePrivilegeCheck(SeExports->SeTcbPrivilege, PreviousMode) )
    goto LABEL_19;
  if ( !p_Prefix )
  {
    AccessStatus = -1073741727;
    goto LABEL_28;
  }
  Privileges = 0;
  v30 = p_Prefix[19];
  FileObjectGenericMapping = IoGetFileObjectGenericMapping();
  v32 = SeAccessCheck(
          v30,
          SubjectSecurityContext,
          0,
          4u,
          0,
          &Privileges,
          FileObjectGenericMapping,
          AccessMode,
          &GrantedAccess,
          &AccessStatus);
  if ( Privileges )
    SeFreePrivileges(Privileges);
  if ( v32 )
  {
    v24 = v51;
LABEL_19:
    if ( RtlInsertUnicodePrefix(v25, (PUNICODE_STRING)v15 + 10, (PUNICODE_PREFIX_TABLE_ENTRY)(v15 + 176)) )
    {
      if ( p_Prefix )
      {
        v41 = (char *)(p_Prefix + 31);
        v42 = (char **)*((_QWORD *)v41 + 1);
        if ( *v42 != v41 )
          __fastfail(3u);
        *((_QWORD *)v15 + 29) = v41;
        *((_QWORD *)v15 + 30) = v42;
        *v42 = v15 + 232;
        *((_QWORD *)v41 + 1) = v15 + 232;
      }
      *(_QWORD *)(a3 + 24) = v15;
      v15 = 0;
      AccessStatus = 0;
      *(_QWORD *)(a3 + 32) = 1;
      *(_QWORD *)(a1 + 8) = 2;
    }
    else if ( a7 == 3 )
    {
      Prefix = NpFindPrefix(v24, a3 + 88, 0, &v49);
      if ( Prefix && *(_WORD *)Prefix == 515 && !v49.Length )
      {
        Privileges = 0;
        v34 = *(void **)(Prefix + 152);
        v35 = IoGetFileObjectGenericMapping();
        v36 = SeAccessCheck(
                v34,
                SubjectSecurityContext,
                0,
                DesiredAccess,
                0,
                &Privileges,
                v35,
                AccessMode,
                &GrantedAccess,
                &AccessStatus);
        if ( Privileges )
          SeFreePrivileges(Privileges);
        if ( v36 )
        {
          *(_QWORD *)(a3 + 24) = Prefix;
          *(_QWORD *)(a3 + 32) = 1;
          ++*(_DWORD *)(Prefix + 120);
          _InterlockedAdd((volatile signed __int32 *)(Prefix + 124), 1u);
          *(_QWORD *)(a1 + 8) = 1;
          AccessStatus = 0;
        }
      }
      else
      {
        AccessStatus = -1073741772;
      }
    }
    else
    {
      AccessStatus = -1073741771;
    }
  }
LABEL_28:
  ExReleasePushLockExclusiveEx(v47, 0);
  KeLeaveCriticalRegion();
  if ( v15 )
  {
LABEL_29:
    v37 = *((_QWORD *)v15 + 19);
    if ( v37 )
      ObDereferenceSecurityDescriptor(v37, 1);
    v38 = (void *)*((_QWORD *)v15 + 6);
    if ( v38 )
      ExFreePoolWithTag(v38, 0);
    ExFreePoolWithTag(v15, 0);
  }
  v39 = AccessStatus;
LABEL_35:
  *(_DWORD *)a1 = v39;
  return a1;
}

```

## disassembly

```asm
0x1400131e0  mov     [rsp-8+arg_18], r9
0x1400131e5  mov     [rsp-8+arg_8], rdx
0x1400131ea  push    rbp
0x1400131eb  push    rbx
0x1400131ec  push    rsi
0x1400131ed  push    rdi
0x1400131ee  push    r12
0x1400131f0  push    r13
0x1400131f2  push    r14
0x1400131f4  push    r15
0x1400131f6  lea     rbp, [rsp-7]
0x1400131fb  sub     rsp, 0A8h
0x140013202  movzx   r14d, word ptr [r8+58h]
0x140013207  xor     eax, eax
0x140013209  mov     ebx, [r8+5Ch]
0x14001320d  xorps   xmm0, xmm0
0x140013210  mov     r13, r8
0x140013213  mov     [rbp+3Fh+arg_0], eax
0x140013216  mov     r15, rcx
0x140013219  mov     [rbp+3Fh+NewDescriptor], rax
0x14001321d  lea     edx, [rax+2]
0x140013220  mov     [rbp+3Fh+Privileges], rax
0x140013224  mov     [rbp+3Fh+arg_10], eax
0x140013227  movups  xmmword ptr [rcx], xmm0
0x14001322a  movups  xmmword ptr [rbp+3Fh+var_50.Length], xmm0
0x14001322e  cmp     r14w, dx
0x140013232  jbe     loc_14001371A
0x140013238  mov     rcx, [r8+60h]
0x14001323c  lea     r8d, [rax+5Ch]
0x140013240  mov     [rbp+3Fh+var_80], rcx
0x140013244  cmp     r8w, [rcx]
0x140013248  jnz     loc_14001371A
0x14001324e  movzx   r12d, word ptr [r13+5Ah]
0x140013253  sub     r14w, dx
0x140013257  movzx   esi, r14w
0x14001325b  mov     ecx, 101h
0x140013260  mov     r8d, 7050704Eh
0x140013266  lea     rdx, [rsi+198h]
0x14001326d  call    cs:__imp_ExAllocatePool2
0x140013274  nop     dword ptr [rax+rax+00h]
0x140013279  mov     rdi, rax
0x14001327c  test    rax, rax
0x14001327f  jz      loc_140013775
0x140013285  xor     edx, edx; Val
0x140013287  mov     r8d, 198h; Size
0x14001328d  mov     rcx, rax; void *
0x140013290  call    memset
0x140013295  mov     al, [rdi+7]
0x140013298  mov     r8d, 7050704Eh
0x14001329e  or      byte ptr [rdi+4], 40h
0x1400132a2  and     al, 0Fh
0x1400132a4  or      byte ptr [rdi+6], 2
0x1400132a8  or      al, 50h
0x1400132aa  mov     [rdi+7], al
0x1400132ad  lea     rax, [rdi+38h]
0x1400132b1  mov     [rax+8], rax
0x1400132b5  mov     [rax], rax
0x1400132b8  xor     eax, eax
0x1400132ba  mov     [rdi+48h], rax
0x1400132be  mov     [rdi+50h], rax
0x1400132c2  mov     [rdi+58h], rax
0x1400132c6  lea     edx, [rax+38h]
0x1400132c9  mov     [rdi+60h], rax
0x1400132cd  lea     ecx, [rax+41h]
0x1400132d0  mov     [rdi+68h], eax
0x1400132d3  mov     [rdi+70h], rax
0x1400132d7  call    cs:__imp_ExAllocatePool2
0x1400132de  nop     dword ptr [rax+rax+00h]
0x1400132e3  mov     [rdi+30h], rax
0x1400132e7  test    rax, rax
0x1400132ea  jz      loc_140013786
0x1400132f0  xor     r8d, r8d; State
0x1400132f3  mov     dword ptr [rax], 1
0x1400132f9  lea     rcx, [rax+18h]; Event
0x1400132fd  mov     qword ptr [rax+8], 0
0x140013305  mov     dword ptr [rax+10h], 0
0x14001330c  lea     edx, [r8+1]; Type
0x140013310  call    cs:__imp_KeInitializeEvent
0x140013317  nop     dword ptr [rax+rax+00h]
0x14001331c  mov     rdx, [rbp+3Fh+var_80]
0x140013320  lea     rax, [rdi+0E8h]
0x140013327  mov     dword ptr [rdi], 1980203h
0x14001332d  lea     rcx, [rdi+198h]; void *
0x140013334  mov     dword ptr [rdi+78h], 1
0x14001333b  mov     r8d, esi; Size
0x14001333e  mov     dword ptr [rdi+7Ch], 1
0x140013345  add     rdx, 2; Src
0x140013349  mov     [rax+8], rax
0x14001334d  mov     [rax], rax
0x140013350  lea     rax, [rdi+0F8h]
0x140013357  mov     [rax+8], rax
0x14001335b  mov     [rax], rax
0x14001335e  mov     [rdi+0A8h], rcx
0x140013365  mov     [rdi+0A0h], r14w
0x14001336d  mov     [rdi+0A2h], r14w
0x140013375  call    memmove
0x14001337a  call    cs:__imp_IoGetFileObjectGenericMapping
0x140013381  nop     dword ptr [rax+rax+00h]
0x140013386  mov     rdx, [rbp+3Fh+arg_18]
0x14001338a  lea     r8, [rbp+3Fh+NewDescriptor]; NewDescriptor
0x14001338e  mov     [rsp+0E0h+PoolType], 1; PoolType
0x140013396  xor     r9d, r9d; IsDirectoryObject
0x140013399  mov     [rsp+0E0h+GenericMapping], rax; GenericMapping
0x14001339e  lea     rcx, [rdx+20h]
0x1400133a2  mov     rdx, [rdx+40h]; ExplicitDescriptor
0x1400133a6  mov     [rbp+3Fh+SubjectSecurityContext], rcx
0x1400133aa  mov     [rsp+0E0h+SubjectContext], rcx; SubjectContext
0x1400133af  xor     ecx, ecx; ParentDescriptor
0x1400133b1  call    cs:__imp_SeAssignSecurity
0x1400133b8  nop     dword ptr [rax+rax+00h]
0x1400133bd  mov     [rbp+3Fh+arg_0], eax
0x1400133c0  test    eax, eax
0x1400133c2  js      loc_1400136A7
0x1400133c8  mov     rcx, [rbp+3Fh+NewDescriptor]
0x1400133cc  lea     rdx, [rdi+98h]
0x1400133d3  mov     r8d, 1
0x1400133d9  call    cs:__imp_ObLogSecurityDescriptor
0x1400133e0  nop     dword ptr [rax+rax+00h]
0x1400133e5  mov     rcx, [rbp+3Fh+NewDescriptor]; P
0x1400133e9  xor     edx, edx; Tag
0x1400133eb  mov     [rbp+3Fh+arg_0], eax
0x1400133ee  call    cs:__imp_ExFreePoolWithTag
0x1400133f5  nop     dword ptr [rax+rax+00h]
0x1400133fa  cmp     [rbp+3Fh+arg_0], 0
0x1400133fe  jl      loc_1400136A7
0x140013404  sub     r12w, 2
0x140013409  call    cs:__imp_KeEnterCriticalRegion
0x140013410  nop     dword ptr [rax+rax+00h]
0x140013415  mov     rax, [rbp+3Fh+arg_8]
0x140013419  xor     edx, edx
0x14001341b  add     rax, 0C0h
0x140013421  mov     rcx, rax
0x140013424  mov     [rbp+3Fh+var_70], rax
0x140013428  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001342f  nop     dword ptr [rax+rax+00h]
0x140013434  mov     rax, [rbp+3Fh+var_80]
0x140013438  mov     ecx, 2
0x14001343d  add     rax, 2
0x140013441  mov     [rbp+3Fh+FullName.Length], r14w
0x140013446  mov     [rbp+3Fh+FullName.MaximumLength], r12w
0x14001344b  mov     dword ptr [rbp+3Fh+FullName+4], ebx
0x14001344e  mov     [rbp+3Fh+FullName.Buffer], rax
0x140013452  cmp     si, cx
0x140013455  jb      short loc_140013476
0x140013457  lea     edx, [rcx+5Ah]
0x14001345a  cmp     dx, [rax]
0x14001345d  jnz     short loc_140013476
0x14001345f  sub     r12w, cx
0x140013463  sub     si, cx
0x140013466  add     rax, rcx
0x140013469  mov     [rbp+3Fh+FullName.MaximumLength], r12w
0x14001346e  mov     [rbp+3Fh+FullName.Buffer], rax
0x140013472  mov     [rbp+3Fh+FullName.Length], si
0x140013476  mov     rbx, [rbp+3Fh+arg_8]
0x14001347a  lea     rdx, [rbp+3Fh+FullName]; FullName
0x14001347e  movzx   r8d, si; CaseInsensitiveIndex
0x140013482  lea     r12, [rbx+0D8h]
0x140013489  mov     rcx, r12; PrefixTable
0x14001348c  call    cs:__imp_RtlFindUnicodePrefix
0x140013493  nop     dword ptr [rax+rax+00h]
0x140013498  test    rax, rax
0x14001349b  jz      loc_14001370A
0x1400134a1  lea     rsi, [rax-0B0h]
0x1400134a8  movzx   eax, [rbp+3Fh+FullName.Length]
0x1400134ac  movzx   ecx, word ptr [rsi+0A0h]
0x1400134b3  sub     ax, cx
0x1400134b6  shr     rcx, 1
0x1400134b9  mov     [rbp+3Fh+var_50.Length], ax
0x1400134bd  mov     [rbp+3Fh+var_50.MaximumLength], ax
0x1400134c1  mov     rax, [rbp+3Fh+FullName.Buffer]
0x1400134c5  lea     rcx, [rax+rcx*2]
0x1400134c9  xor     eax, eax
0x1400134cb  mov     [rbp+3Fh+var_50.Buffer], rcx
0x1400134cf  mov     ecx, 203h
0x1400134d4  cmp     [rsi], cx
0x1400134d7  cmovnz  rsi, rax
0x1400134db  mov     rax, cs:__imp_SeExports
0x1400134e2  mov     r14b, [rbp+3Fh+PreviousMode]
0x1400134e6  mov     dl, r14b; PreviousMode
0x1400134e9  mov     rcx, [rax]
0x1400134ec  mov     rcx, [rcx+28h]; PrivilegeValue
0x1400134f0  call    cs:__imp_SeSinglePrivilegeCheck
0x1400134f7  nop     dword ptr [rax+rax+00h]
0x1400134fc  test    al, al
0x1400134fe  jnz     loc_14001358C
0x140013504  test    rsi, rsi
0x140013507  jz      loc_140013721
0x14001350d  mov     [rbp+3Fh+Privileges], 0
0x140013515  mov     rbx, [rsi+98h]
0x14001351c  call    cs:__imp_IoGetFileObjectGenericMapping
0x140013523  nop     dword ptr [rax+rax+00h]
0x140013528  mov     rdx, [rbp+3Fh+SubjectSecurityContext]; SubjectSecurityContext
0x14001352c  lea     rcx, [rbp+3Fh+arg_0]
0x140013530  mov     [rsp+0E0h+AccessStatus], rcx; AccessStatus
0x140013535  mov     r9d, 4; DesiredAccess
0x14001353b  lea     rcx, [rbp+3Fh+arg_10]
0x14001353f  xor     r8d, r8d; SubjectContextLocked
0x140013542  mov     [rsp+0E0h+GrantedAccess], rcx; GrantedAccess
0x140013547  mov     rcx, rbx; SecurityDescriptor
0x14001354a  mov     [rsp+0E0h+AccessMode], r14b; AccessMode
0x14001354f  mov     qword ptr [rsp+0E0h+PoolType], rax; GenericMapping
0x140013554  lea     rax, [rbp+3Fh+Privileges]
0x140013558  mov     [rsp+0E0h+GenericMapping], rax; Privileges
0x14001355d  mov     dword ptr [rsp+0E0h+SubjectContext], 0; PreviouslyGrantedAccess
0x140013565  call    cs:__imp_SeAccessCheck
0x14001356c  nop     dword ptr [rax+rax+00h]
0x140013571  mov     rcx, [rbp+3Fh+Privileges]; Privileges
0x140013575  mov     bl, al
0x140013577  test    rcx, rcx
0x14001357a  jnz     loc_140013793
0x140013580  test    bl, bl
0x140013582  jz      loc_140013684
0x140013588  mov     rbx, [rbp+3Fh+arg_8]
0x14001358c  lea     r8, [rdi+0B0h]; PrefixTableEntry
0x140013593  mov     rcx, r12; PrefixTable
0x140013596  lea     rdx, [rdi+0A0h]; Prefix
0x14001359d  call    cs:__imp_RtlInsertUnicodePrefix
0x1400135a4  nop     dword ptr [rax+rax+00h]
0x1400135a9  test    al, al
0x1400135ab  jnz     loc_14001372D
0x1400135b1  cmp     [rbp+3Fh+arg_30], 3
0x1400135b5  jnz     loc_1400137A4
0x1400135bb  lea     r9, [rbp+3Fh+var_50]
0x1400135bf  xor     r8d, r8d
0x1400135c2  lea     rdx, [r13+58h]
0x1400135c6  mov     rcx, rbx
0x1400135c9  call    NpFindPrefix
0x1400135ce  mov     rsi, rax
0x1400135d1  test    rax, rax
0x1400135d4  jz      loc_1400137C1
0x1400135da  mov     eax, 203h
0x1400135df  cmp     [rsi], ax
0x1400135e2  jnz     loc_1400137C1
0x1400135e8  xor     ecx, ecx
0x1400135ea  cmp     cx, [rbp+3Fh+var_50.Length]
0x1400135ee  jnz     loc_1400137C1
0x1400135f4  mov     [rbp+3Fh+Privileges], rcx
0x1400135f8  mov     rbx, [rsi+98h]
0x1400135ff  call    cs:__imp_IoGetFileObjectGenericMapping
0x140013606  nop     dword ptr [rax+rax+00h]
0x14001360b  mov     r9d, [rbp+3Fh+DesiredAccess]; DesiredAccess
0x14001360f  lea     rcx, [rbp+3Fh+arg_0]
0x140013613  mov     rdx, [rbp+3Fh+SubjectSecurityContext]; SubjectSecurityContext
0x140013617  xor     r8d, r8d; SubjectContextLocked
0x14001361a  mov     [rsp+0E0h+AccessStatus], rcx; AccessStatus
0x14001361f  lea     rcx, [rbp+3Fh+arg_10]
0x140013623  mov     [rsp+0E0h+GrantedAccess], rcx; GrantedAccess
0x140013628  mov     rcx, rbx; SecurityDescriptor
0x14001362b  mov     [rsp+0E0h+AccessMode], r14b; AccessMode
0x140013630  mov     qword ptr [rsp+0E0h+PoolType], rax; GenericMapping
0x140013635  lea     rax, [rbp+3Fh+Privileges]
0x140013639  mov     [rsp+0E0h+GenericMapping], rax; Privileges
0x14001363e  mov     dword ptr [rsp+0E0h+SubjectContext], 0; PreviouslyGrantedAccess
0x140013646  call    cs:__imp_SeAccessCheck
0x14001364d  nop     dword ptr [rax+rax+00h]
0x140013652  mov     rcx, [rbp+3Fh+Privileges]; Privileges
0x140013656  mov     bl, al
0x140013658  test    rcx, rcx
0x14001365b  jnz     loc_1400137B0
0x140013661  test    bl, bl
0x140013663  jz      short loc_140013684
0x140013665  mov     eax, 1
0x14001366a  mov     [r13+18h], rsi
0x14001366e  mov     [r13+20h], rax
0x140013672  add     [rsi+78h], eax
0x140013675  lock add [rsi+7Ch], eax
0x140013679  mov     [r15+8], rax
0x14001367d  mov     [rbp+3Fh+arg_0], 0
0x140013684  mov     rcx, [rbp+3Fh+var_70]
0x140013688  xor     edx, edx
0x14001368a  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140013691  nop     dword ptr [rax+rax+00h]
0x140013696  call    cs:__imp_KeLeaveCriticalRegion
0x14001369d  nop     dword ptr [rax+rax+00h]
0x1400136a2  test    rdi, rdi
0x1400136a5  jz      short loc_1400136EC
0x1400136a7  mov     rcx, [rdi+98h]
0x1400136ae  test    rcx, rcx
0x1400136b1  jz      short loc_1400136C4
0x1400136b3  mov     edx, 1
0x1400136b8  call    cs:__imp_ObDereferenceSecurityDescriptor
0x1400136bf  nop     dword ptr [rax+rax+00h]
0x1400136c4  mov     rcx, [rdi+30h]; P
0x1400136c8  test    rcx, rcx
0x1400136cb  jz      short loc_1400136DB
0x1400136cd  xor     edx, edx; Tag
0x1400136cf  call    cs:__imp_ExFreePoolWithTag
0x1400136d6  nop     dword ptr [rax+rax+00h]
0x1400136db  xor     edx, edx; Tag
0x1400136dd  mov     rcx, rdi; P
0x1400136e0  call    cs:__imp_ExFreePoolWithTag
0x1400136e7  nop     dword ptr [rax+rax+00h]
0x1400136ec  mov     eax, [rbp+3Fh+arg_0]
0x1400136ef  mov     [r15], eax
0x1400136f2  mov     rax, r15
0x1400136f5  add     rsp, 0A8h
0x1400136fc  pop     r15
0x1400136fe  pop     r14
0x140013700  pop     r13
0x140013702  pop     r12
  ... truncated ...
```
