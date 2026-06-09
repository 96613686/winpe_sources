# InitializeDefaultServerRootSecurityDescriptor(void)

- ea: `0x1400b3084`
- end: `0x1400b36fd`
- name: `?InitializeDefaultServerRootSecurityDescriptor@@YAXXZ`
- size: `1657`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14034c36c`

## callees

- `0x14008dbd0`
- `0x1400b3084`
- `0x1400ca788`
- `0x1401e9ce0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1400b36cc`
- `ntoskrnl!ExRaiseStatus` at `0x1400b36cc`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b313e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b313e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b35dd`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401eba80`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b35dd`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401eba80`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b357d`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b357d`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3152`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b31c8`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b322a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3289`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3302`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3152`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b31c8`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b322a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3289`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b3302`
- `ntoskrnl!RtlInitializeSid` at `0x1400b318e`
- `ntoskrnl!RtlInitializeSid` at `0x1400b3204`
- `ntoskrnl!RtlInitializeSid` at `0x1400b3266`
- `ntoskrnl!RtlInitializeSid` at `0x1400b32c5`
- `ntoskrnl!RtlInitializeSid` at `0x1400b333e`
- `ntoskrnl!RtlInitializeSid` at `0x1400b318e`
- `ntoskrnl!RtlInitializeSid` at `0x1400b3204`
- `ntoskrnl!RtlInitializeSid` at `0x1400b3266`
- `ntoskrnl!RtlInitializeSid` at `0x1400b32c5`
- `ntoskrnl!RtlInitializeSid` at `0x1400b333e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b319f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b31b3`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3215`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3277`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b32d6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b32ee`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b334f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b319f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b31b3`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3215`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b3277`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b32d6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b32ee`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b334f`
- `ntoskrnl!RtlCreateAcl` at `0x1400b33b6`
- `ntoskrnl!RtlCreateAcl` at `0x1400b33b6`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400b3537`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400b3537`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400b3561`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400b3561`
- `ntoskrnl!SeAssignSecurity` at `0x1400b35ab`
- `ntoskrnl!SeAssignSecurity` at `0x1400b35ab`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400b35c8`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400b35c8`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b33e7`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3418`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3449`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b347a`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b34aa`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b34da`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3510`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b33e7`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3418`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3449`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b347a`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b34aa`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b34da`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400b3510`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b35f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3609`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b361a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b362b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b363c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b364f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3660`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401eba98`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebab0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebac8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebae0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebaf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebb10`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebb28`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b35f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3609`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b361a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b362b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b363c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b364f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b3660`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401eba98`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebab0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebac8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebae0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebaf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebb10`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebb28`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3127`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b316c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b31e2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3244`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b32a3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b331c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3397`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3127`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b316c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b31e2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3244`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b32a3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b331c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b3397`

## pseudocode

```c
void InitializeDefaultServerRootSecurityDescriptor(void)
{
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rsi
  ULONG v1; // eax
  unsigned __int8 *Sid; // r15
  ULONG v3; // eax
  unsigned __int8 *v4; // r12
  ULONG v5; // eax
  unsigned __int8 *v6; // r13
  ULONG v7; // eax
  unsigned __int8 *v8; // r14
  ULONG v9; // eax
  ULONG v10; // ebx
  struct _ACL *v11; // rdi
  int Acl; // ebx
  POOL_TYPE PoolType; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  unsigned __int8 *P; // [rsp+48h] [rbp-C0h]
  _OWORD SecurityDescriptor[2]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v17; // [rsp+A0h] [rbp-68h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+A8h] [rbp-60h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v19; // [rsp+B0h] [rbp-58h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v20; // [rsp+B8h] [rbp-50h] BYREF

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v17 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v19.Value = 0;
  *(_WORD *)&v19.Value[4] = 768;
  *(_DWORD *)v20.Value = 0;
  *(_WORD *)&v20.Value[4] = 256;
  PoolWithTag = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                      (POOL_TYPE)(::PoolType | 0x10),
                                                      0x20u,
                                                      0x4A666552u);
  SeCaptureSubjectContext(PoolWithTag);
  v1 = RtlLengthRequiredSid(2u);
  Sid = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v1, 0x4A666552u);
  RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(Sid, 0) = 32;
  *RtlSubAuthoritySid(Sid, 1u) = 544;
  v3 = RtlLengthRequiredSid(1u);
  v4 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v3, 0x4A666552u);
  RtlInitializeSid(v4, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v4, 0) = 18;
  v5 = RtlLengthRequiredSid(1u);
  v6 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v5, 0x4A666552u);
  RtlInitializeSid(v6, &v19, 1u);
  *RtlSubAuthoritySid(v6, 0) = 0;
  v7 = RtlLengthRequiredSid(2u);
  v8 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v7, 0x4A666552u);
  RtlInitializeSid(v8, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(v8, 0) = 32;
  *RtlSubAuthoritySid(v8, 1u) = 545;
  v9 = RtlLengthRequiredSid(1u);
  P = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v9, 0x4A666552u);
  RtlInitializeSid(P, &v20, 1u);
  *RtlSubAuthoritySid(P, 0) = 0;
  v10 = 4 * (Sid[1] + v4[1] + v6[1] + v8[1] + P[1]) + 232;
  v11 = (struct _ACL *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v10, 0x4A666552u);
  Acl = RtlCreateAcl(v11, v10, 2u);
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 0x10000000u, Sid);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 0x10000000u, v4);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAceEx(v11, 2u, 0xBu, 0x10000000u, v6);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 0x80100020, v8);
          if ( Acl >= 0 )
          {
            Acl = RtlAddAccessAllowedAceEx(v11, 2u, 2u, 4u, v8);
            if ( Acl >= 0 )
            {
              Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 2u, v8);
              if ( Acl >= 0 )
              {
                Acl = RtlAddAccessAllowedAceEx(v11, 2u, 3u, 0x80100020, P);
                if ( Acl >= 0 )
                {
                  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
                  if ( Acl >= 0 )
                  {
                    Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v11, 0);
                    if ( Acl >= 0 )
                    {
                      PoolType = ::PoolType;
                      GenericMapping = IoGetFileObjectGenericMapping();
                      Acl = SeAssignSecurity(
                              0,
                              SecurityDescriptor,
                              &ModificationDescriptor,
                              0,
                              PoolWithTag,
                              GenericMapping,
                              PoolType);
                      if ( Acl >= 0 )
                        dword_1402612C8 = RtlLengthSecurityDescriptor(ModificationDescriptor);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  SeReleaseSubjectContext(PoolWithTag);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  ExFreePoolWithTag(Sid, 0);
  ExFreePoolWithTag(v4, 0);
  ExFreePoolWithTag(v6, 0);
  ExFreePoolWithTag(P, 0);
  ExFreePoolWithTag(v8, 0);
  if ( Acl < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        23,
        WPP_bee596de7a9331ebd70d5dc28c9a6eb9_Traceguids,
        (unsigned int)Acl);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(Acl, 0, "NtfsInit.c", 0x197Fu);
    ExRaiseStatus(Acl);
  }
}

```

## disassembly

```asm
0x1400b3084  mov     r11, rsp
0x1400b3087  push    rbx
0x1400b3088  push    rsi
0x1400b3089  push    rdi
0x1400b308a  push    r12
0x1400b308c  push    r13
0x1400b308e  push    r14
0x1400b3090  push    r15
0x1400b3092  sub     rsp, 0D0h
0x1400b3099  mov     rax, cs:__security_cookie
0x1400b30a0  xor     rax, rsp
0x1400b30a3  mov     [rsp+108h+var_48], rax
0x1400b30ab  xor     r14d, r14d
0x1400b30ae  mov     [rsp+108h+var_B8], r14
0x1400b30b3  mov     [rsp+108h+var_C8], r14b
0x1400b30b8  mov     [rsp+108h+var_B0], r14
0x1400b30bd  mov     [rsp+108h+var_A8], r14
0x1400b30c2  mov     [rsp+108h+var_A0], r14
0x1400b30c7  mov     [rsp+108h+var_98], r14
0x1400b30cc  mov     [rsp+108h+var_90], r14
0x1400b30d1  mov     [rsp+108h+P], r14
0x1400b30d6  xorps   xmm0, xmm0
0x1400b30d9  xor     eax, eax
0x1400b30db  movups  [rsp+108h+SecurityDescriptor], xmm0
0x1400b30e3  movups  xmmword ptr [r11-78h], xmm0
0x1400b30e8  mov     [r11-68h], rax
0x1400b30ec  mov     [r11-60h], r14d
0x1400b30f0  mov     word ptr [r11-5Ch], 500h
0x1400b30f7  mov     [r11-58h], r14d
0x1400b30fb  mov     word ptr [r11-54h], 300h
0x1400b3102  mov     [r11-50h], r14d
0x1400b3106  mov     word ptr [r11-4Ch], 100h
0x1400b310d  lea     r13d, [r14+1]
0x1400b3111  mov     ecx, cs:PoolType
0x1400b3117  or      ecx, 10h; PoolType
0x1400b311a  mov     edi, 4A666552h
0x1400b311f  mov     r8d, edi; Tag
0x1400b3122  lea     ebx, [rax+20h]
0x1400b3125  mov     edx, ebx; NumberOfBytes
0x1400b3127  call    cs:__imp_ExAllocatePoolWithTag
0x1400b312e  nop     dword ptr [rax+rax+00h]
0x1400b3133  mov     rsi, rax
0x1400b3136  mov     [rsp+108h+var_B8], rax
0x1400b313b  mov     rcx, rax; SubjectContext
0x1400b313e  call    cs:__imp_SeCaptureSubjectContext
0x1400b3145  nop     dword ptr [rax+rax+00h]
0x1400b314a  mov     [rsp+108h+var_C8], r13b
0x1400b314f  lea     ecx, [rbx-1Eh]; SubAuthorityCount
0x1400b3152  call    cs:__imp_RtlLengthRequiredSid
0x1400b3159  nop     dword ptr [rax+rax+00h]
0x1400b315e  mov     edx, eax; NumberOfBytes
0x1400b3160  mov     ecx, cs:PoolType
0x1400b3166  or      ecx, 10h; PoolType
0x1400b3169  mov     r8d, edi; Tag
0x1400b316c  call    cs:__imp_ExAllocatePoolWithTag
0x1400b3173  nop     dword ptr [rax+rax+00h]
0x1400b3178  mov     r15, rax
0x1400b317b  mov     [rsp+108h+var_A8], rax
0x1400b3180  mov     r8b, 2; SubAuthorityCount
0x1400b3183  lea     rdx, [rsp+108h+IdentifierAuthority]; IdentifierAuthority
0x1400b318b  mov     rcx, rax; Sid
0x1400b318e  call    cs:__imp_RtlInitializeSid
0x1400b3195  nop     dword ptr [rax+rax+00h]
0x1400b319a  xor     edx, edx; SubAuthority
0x1400b319c  mov     rcx, r15; Sid
0x1400b319f  call    cs:__imp_RtlSubAuthoritySid
0x1400b31a6  nop     dword ptr [rax+rax+00h]
0x1400b31ab  mov     [rax], ebx
0x1400b31ad  mov     edx, r13d; SubAuthority
0x1400b31b0  mov     rcx, r15; Sid
0x1400b31b3  call    cs:__imp_RtlSubAuthoritySid
0x1400b31ba  nop     dword ptr [rax+rax+00h]
0x1400b31bf  mov     dword ptr [rax], 220h
0x1400b31c5  mov     ecx, r13d; SubAuthorityCount
0x1400b31c8  call    cs:__imp_RtlLengthRequiredSid
0x1400b31cf  nop     dword ptr [rax+rax+00h]
0x1400b31d4  mov     edx, eax; NumberOfBytes
0x1400b31d6  mov     ecx, cs:PoolType
0x1400b31dc  or      ecx, 10h; PoolType
0x1400b31df  mov     r8d, edi; Tag
0x1400b31e2  call    cs:__imp_ExAllocatePoolWithTag
0x1400b31e9  nop     dword ptr [rax+rax+00h]
0x1400b31ee  mov     r12, rax
0x1400b31f1  mov     [rsp+108h+var_A0], rax
0x1400b31f6  mov     r8b, r13b; SubAuthorityCount
0x1400b31f9  lea     rdx, [rsp+108h+IdentifierAuthority]; IdentifierAuthority
0x1400b3201  mov     rcx, rax; Sid
0x1400b3204  call    cs:__imp_RtlInitializeSid
0x1400b320b  nop     dword ptr [rax+rax+00h]
0x1400b3210  xor     edx, edx; SubAuthority
0x1400b3212  mov     rcx, r12; Sid
0x1400b3215  call    cs:__imp_RtlSubAuthoritySid
0x1400b321c  nop     dword ptr [rax+rax+00h]
0x1400b3221  mov     dword ptr [rax], 12h
0x1400b3227  mov     ecx, r13d; SubAuthorityCount
0x1400b322a  call    cs:__imp_RtlLengthRequiredSid
0x1400b3231  nop     dword ptr [rax+rax+00h]
0x1400b3236  mov     edx, eax; NumberOfBytes
0x1400b3238  mov     ecx, cs:PoolType
0x1400b323e  or      ecx, 10h; PoolType
0x1400b3241  mov     r8d, edi; Tag
0x1400b3244  call    cs:__imp_ExAllocatePoolWithTag
0x1400b324b  nop     dword ptr [rax+rax+00h]
0x1400b3250  mov     r13, rax
0x1400b3253  mov     [rsp+108h+var_98], rax
0x1400b3258  mov     r8b, 1; SubAuthorityCount
0x1400b325b  lea     rdx, [rsp+108h+var_58]; IdentifierAuthority
0x1400b3263  mov     rcx, rax; Sid
0x1400b3266  call    cs:__imp_RtlInitializeSid
0x1400b326d  nop     dword ptr [rax+rax+00h]
0x1400b3272  xor     edx, edx; SubAuthority
0x1400b3274  mov     rcx, r13; Sid
0x1400b3277  call    cs:__imp_RtlSubAuthoritySid
0x1400b327e  nop     dword ptr [rax+rax+00h]
0x1400b3283  mov     [rax], r14d
0x1400b3286  lea     ecx, [rbx-1Eh]; SubAuthorityCount
0x1400b3289  call    cs:__imp_RtlLengthRequiredSid
0x1400b3290  nop     dword ptr [rax+rax+00h]
0x1400b3295  mov     edx, eax; NumberOfBytes
0x1400b3297  mov     ecx, cs:PoolType
0x1400b329d  or      ecx, 10h; PoolType
0x1400b32a0  mov     r8d, edi; Tag
0x1400b32a3  call    cs:__imp_ExAllocatePoolWithTag
0x1400b32aa  nop     dword ptr [rax+rax+00h]
0x1400b32af  mov     r14, rax
0x1400b32b2  mov     [rsp+108h+var_90], rax
0x1400b32b7  mov     r8b, 2; SubAuthorityCount
0x1400b32ba  lea     rdx, [rsp+108h+IdentifierAuthority]; IdentifierAuthority
0x1400b32c2  mov     rcx, rax; Sid
0x1400b32c5  call    cs:__imp_RtlInitializeSid
0x1400b32cc  nop     dword ptr [rax+rax+00h]
0x1400b32d1  xor     edx, edx; SubAuthority
0x1400b32d3  mov     rcx, r14; Sid
0x1400b32d6  call    cs:__imp_RtlSubAuthoritySid
0x1400b32dd  nop     dword ptr [rax+rax+00h]
0x1400b32e2  mov     [rax], ebx
0x1400b32e4  mov     ebx, 1
0x1400b32e9  mov     edx, ebx; SubAuthority
0x1400b32eb  mov     rcx, r14; Sid
0x1400b32ee  call    cs:__imp_RtlSubAuthoritySid
0x1400b32f5  nop     dword ptr [rax+rax+00h]
0x1400b32fa  mov     dword ptr [rax], 221h
0x1400b3300  mov     ecx, ebx; SubAuthorityCount
0x1400b3302  call    cs:__imp_RtlLengthRequiredSid
0x1400b3309  nop     dword ptr [rax+rax+00h]
0x1400b330e  mov     edx, eax; NumberOfBytes
0x1400b3310  mov     ecx, cs:PoolType
0x1400b3316  or      ecx, 10h; PoolType
0x1400b3319  mov     r8d, edi; Tag
0x1400b331c  call    cs:__imp_ExAllocatePoolWithTag
0x1400b3323  nop     dword ptr [rax+rax+00h]
0x1400b3328  mov     rbx, rax
0x1400b332b  mov     [rsp+108h+P], rax
0x1400b3330  mov     r8b, 1; SubAuthorityCount
0x1400b3333  lea     rdx, [rsp+108h+var_50]; IdentifierAuthority
0x1400b333b  mov     rcx, rax; Sid
0x1400b333e  call    cs:__imp_RtlInitializeSid
0x1400b3345  nop     dword ptr [rax+rax+00h]
0x1400b334a  xor     edx, edx; SubAuthority
0x1400b334c  mov     rcx, rbx; Sid
0x1400b334f  call    cs:__imp_RtlSubAuthoritySid
0x1400b3356  nop     dword ptr [rax+rax+00h]
0x1400b335b  mov     dword ptr [rax], 0
0x1400b3361  movzx   ebx, byte ptr [rbx+1]
0x1400b3365  movzx   ecx, byte ptr [r14+1]
0x1400b336a  add     ebx, ecx
0x1400b336c  movzx   ecx, byte ptr [r13+1]
0x1400b3371  add     ebx, ecx
0x1400b3373  movzx   eax, byte ptr [r12+1]
0x1400b3379  add     ebx, eax
0x1400b337b  movzx   eax, byte ptr [r15+1]
0x1400b3380  add     ebx, eax
0x1400b3382  lea     ebx, ds:0E8h[rbx*4]
0x1400b3389  mov     edx, ebx; NumberOfBytes
0x1400b338b  mov     ecx, cs:PoolType
0x1400b3391  or      ecx, 10h; PoolType
0x1400b3394  mov     r8d, edi; Tag
0x1400b3397  call    cs:__imp_ExAllocatePoolWithTag
0x1400b339e  nop     dword ptr [rax+rax+00h]
0x1400b33a3  mov     rdi, rax
0x1400b33a6  mov     [rsp+108h+var_B0], rax
0x1400b33ab  mov     r8d, 2; AclRevision
0x1400b33b1  mov     edx, ebx; AclLength
0x1400b33b3  mov     rcx, rax; Acl
0x1400b33b6  call    cs:__imp_RtlCreateAcl
0x1400b33bd  nop     dword ptr [rax+rax+00h]
0x1400b33c2  mov     ebx, eax
0x1400b33c4  mov     [rsp+108h+var_C4], eax
0x1400b33c8  test    eax, eax
0x1400b33ca  js      loc_1400B35DA
0x1400b33d0  mov     [rsp+108h+Sid], r15; Sid
0x1400b33d5  mov     edx, 2; AceRevision
0x1400b33da  mov     r9d, 10000000h; AccessMask
0x1400b33e0  lea     r8d, [rdx+1]; AceFlags
0x1400b33e4  mov     rcx, rdi; Acl
0x1400b33e7  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b33ee  nop     dword ptr [rax+rax+00h]
0x1400b33f3  mov     ebx, eax
0x1400b33f5  mov     [rsp+108h+var_C4], eax
0x1400b33f9  test    eax, eax
0x1400b33fb  js      loc_1400B35DA
0x1400b3401  mov     [rsp+108h+Sid], r12; Sid
0x1400b3406  mov     edx, 2; AceRevision
0x1400b340b  mov     r9d, 10000000h; AccessMask
0x1400b3411  lea     r8d, [rdx+1]; AceFlags
0x1400b3415  mov     rcx, rdi; Acl
0x1400b3418  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b341f  nop     dword ptr [rax+rax+00h]
0x1400b3424  mov     ebx, eax
0x1400b3426  mov     [rsp+108h+var_C4], eax
0x1400b342a  test    eax, eax
0x1400b342c  js      loc_1400B35DA
0x1400b3432  mov     [rsp+108h+Sid], r13; Sid
0x1400b3437  mov     edx, 2; AceRevision
0x1400b343c  mov     r9d, 10000000h; AccessMask
0x1400b3442  lea     r8d, [rdx+9]; AceFlags
0x1400b3446  mov     rcx, rdi; Acl
0x1400b3449  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b3450  nop     dword ptr [rax+rax+00h]
0x1400b3455  mov     ebx, eax
0x1400b3457  mov     [rsp+108h+var_C4], eax
0x1400b345b  test    eax, eax
0x1400b345d  js      loc_1400B35DA
0x1400b3463  mov     [rsp+108h+Sid], r14; Sid
0x1400b3468  mov     edx, 2; AceRevision
0x1400b346d  mov     r9d, 80100020h; AccessMask
0x1400b3473  lea     r8d, [rdx+1]; AceFlags
0x1400b3477  mov     rcx, rdi; Acl
0x1400b347a  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b3481  nop     dword ptr [rax+rax+00h]
0x1400b3486  mov     ebx, eax
0x1400b3488  mov     [rsp+108h+var_C4], eax
0x1400b348c  test    eax, eax
0x1400b348e  js      loc_1400B35DA
0x1400b3494  mov     [rsp+108h+Sid], r14; Sid
0x1400b3499  mov     eax, 2
0x1400b349e  lea     r9d, [rax+2]; AccessMask
0x1400b34a2  mov     r8d, eax; AceFlags
0x1400b34a5  mov     edx, eax; AceRevision
0x1400b34a7  mov     rcx, rdi; Acl
0x1400b34aa  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b34b1  nop     dword ptr [rax+rax+00h]
0x1400b34b6  mov     ebx, eax
0x1400b34b8  mov     [rsp+108h+var_C4], eax
0x1400b34bc  test    eax, eax
0x1400b34be  js      loc_1400B35DA
0x1400b34c4  mov     [rsp+108h+Sid], r14; Sid
0x1400b34c9  mov     eax, 2
0x1400b34ce  mov     r9d, eax; AccessMask
0x1400b34d1  lea     r8d, [rax+1]; AceFlags
0x1400b34d5  mov     edx, eax; AceRevision
0x1400b34d7  mov     rcx, rdi; Acl
0x1400b34da  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b34e1  nop     dword ptr [rax+rax+00h]
0x1400b34e6  mov     ebx, eax
0x1400b34e8  mov     [rsp+108h+var_C4], eax
0x1400b34ec  test    eax, eax
0x1400b34ee  js      loc_1400B35DA
0x1400b34f4  mov     rax, [rsp+108h+P]
0x1400b34f9  mov     [rsp+108h+Sid], rax; Sid
0x1400b34fe  mov     edx, 2; AceRevision
0x1400b3503  mov     r9d, 80100020h; AccessMask
0x1400b3509  lea     r8d, [rdx+1]; AceFlags
0x1400b350d  mov     rcx, rdi; Acl
0x1400b3510  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400b3517  nop     dword ptr [rax+rax+00h]
0x1400b351c  mov     ebx, eax
0x1400b351e  mov     [rsp+108h+var_C4], eax
0x1400b3522  test    eax, eax
0x1400b3524  js      loc_1400B35DA
0x1400b352a  mov     edx, 1; Revision
0x1400b352f  lea     rcx, [rsp+108h+SecurityDescriptor]; SecurityDescriptor
0x1400b3537  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400b353e  nop     dword ptr [rax+rax+00h]
0x1400b3543  mov     ebx, eax
0x1400b3545  mov     [rsp+108h+var_C4], eax
0x1400b3549  test    eax, eax
0x1400b354b  js      loc_1400B35DA
0x1400b3551  xor     r9d, r9d; DaclDefaulted
0x1400b3554  mov     r8, rdi; Dacl
0x1400b3557  mov     dl, 1; DaclPresent
0x1400b3559  lea     rcx, [rsp+108h+SecurityDescriptor]; SecurityDescriptor
0x1400b3561  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400b3568  nop     dword ptr [rax+rax+00h]
0x1400b356d  mov     ebx, eax
0x1400b356f  mov     [rsp+108h+var_C4], eax
0x1400b3573  test    eax, eax
0x1400b3575  js      short loc_1400B35DA
0x1400b3577  mov     ebx, cs:PoolType
0x1400b357d  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400b3584  nop     dword ptr [rax+rax+00h]
0x1400b3589  mov     [rsp+108h+PoolType], ebx; PoolType
0x1400b358d  mov     [rsp+108h+GenericMapping], rax; GenericMapping
0x1400b3592  mov     [rsp+108h+Sid], rsi; SubjectContext
0x1400b3597  xor     r9d, r9d; IsDirectoryObject
0x1400b359a  lea     r8, ModificationDescriptor; NewDescriptor
0x1400b35a1  lea     rdx, [rsp+108h+SecurityDescriptor]; ExplicitDescriptor
0x1400b35a9  xor     ecx, ecx; ParentDescriptor
0x1400b35ab  call    cs:__imp_SeAssignSecurity
0x1400b35b2  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
