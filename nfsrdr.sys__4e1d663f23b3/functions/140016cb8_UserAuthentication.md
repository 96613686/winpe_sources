# UserAuthentication

- ea: `0x140016cb8`
- end: `0x1400173f0`
- name: `UserAuthentication`
- size: `1848`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, _OWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140022c5c`

## callees

- `0x1400159fc`
- `0x14001643c`
- `0x140016634`
- `0x140016aa8`
- `0x140016cb8`
- `0x1400173f8`
- `0x14001744c`
- `0x140017538`
- `0x140017590`
- `0x140020fa8`
- `0x140029290`
- `0x1400378fc`
- `0x14003972c`
- `0x14003aba0`
- `0x14003b0c0`

## import_xrefs

- `ntoskrnl!SeCaptureSubjectContext` at `0x140016dc6`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140016dc6`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140016dee`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140016dee`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140016e02`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140016e02`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016e92`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016edc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016f2c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016f77`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016e92`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016edc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016f2c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016f77`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400170f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400170f0`

## pseudocode

```c
__int64 __fastcall UserAuthentication(__int64 a1, __int64 a2, unsigned int a3, _OWORD *a4, unsigned int a5)
{
  __int64 v6; // r14
  __int64 v9; // rdi
  PACCESS_TOKEN PrimaryToken; // rcx
  size_t v11; // r14
  size_t v13; // r15
  unsigned int v14; // r14d
  const wchar_t *v15; // rcx
  unsigned int v16; // r14d
  size_t v17; // r15
  const wchar_t *v18; // rcx
  const wchar_t *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r8
  int v22; // r9d
  void *v23; // r15
  int inserted; // ebx
  int UidGidFromPasswdGroupByUserName; // r14d
  int v26; // r11d
  int v27; // r10d
  char v28; // r9
  int v29; // eax
  int v30; // [rsp+28h] [rbp-150h]
  char v31; // [rsp+40h] [rbp-138h] BYREF
  _BYTE v32[7]; // [rsp+41h] [rbp-137h] BYREF
  size_t v33; // [rsp+48h] [rbp-130h] BYREF
  size_t pcchLength; // [rsp+50h] [rbp-128h] BYREF
  struct _LUID AuthenticationId; // [rsp+58h] [rbp-120h] BYREF
  UNICODE_STRING Source; // [rsp+60h] [rbp-118h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-108h] BYREF
  size_t v38; // [rsp+80h] [rbp-F8h] BYREF
  struct _UNICODE_STRING v39; // [rsp+88h] [rbp-F0h] BYREF
  struct _UNICODE_STRING v40; // [rsp+98h] [rbp-E0h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+A8h] [rbp-D0h] BYREF
  __int128 v42; // [rsp+C8h] [rbp-B0h] BYREF
  int v43; // [rsp+D8h] [rbp-A0h]
  _OWORD v44[5]; // [rsp+E0h] [rbp-98h] BYREF

  v6 = a3;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  *(_QWORD *)&v40.Length = 0;
  v40.Buffer = 0;
  *(_QWORD *)&v39.Length = 0;
  v39.Buffer = 0;
  *(_QWORD *)&Source.Length = 0;
  Source.Buffer = 0;
  memset(v44, 0, 0x4Cu);
  AuthenticationId = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  v42 = 0;
  v43 = 0;
  pcchLength = 0;
  v33 = 0;
  v38 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids, a2);
  v9 = *(_QWORD *)(a1 + 80);
  v42 = *(_OWORD *)(v9 + 1376);
  v43 = *(_DWORD *)(v9 + 1392);
  SeCaptureSubjectContext(&SubjectContext);
  PrimaryToken = SubjectContext.PrimaryToken;
  if ( SubjectContext.ClientToken )
    PrimaryToken = SubjectContext.ClientToken;
  SeQueryAuthenticationIdToken(PrimaryToken, &AuthenticationId);
  SeReleaseSubjectContext(&SubjectContext);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
    WPP_SF_dd(
      WPP_GLOBAL_Control->AttachedDevice,
      29,
      WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids,
      AuthenticationId.LowPart,
      AuthenticationId.HighPart);
  if ( (unsigned int)v6 < 0x30 || !a2 )
    return 3221225485LL;
  *(_QWORD *)a2 = a2 + 40;
  v11 = (unsigned int)((unsigned __int64)(v6 - 40) >> 1);
  if ( RtlStringCchLengthW((STRSAFE_PCNZWCH)(a2 + 40), v11, &pcchLength) )
    return 3221225485LL;
  RtlInitUnicodeString(&DestinationString, *(PCWSTR *)a2);
  v13 = pcchLength;
  v14 = v11 - pcchLength - 1;
  v15 = (const wchar_t *)(a2 + 2 * (pcchLength + 21));
  *(_QWORD *)(a2 + 8) = v15;
  if ( RtlStringCchLengthW(v15, v14, &v33) )
    return 3221225485LL;
  RtlInitUnicodeString(&v40, *(PCWSTR *)(a2 + 8));
  v16 = v14 - v33 - 1;
  v17 = v33 + v13;
  v18 = (const wchar_t *)(a2 + 2 * (v17 + 22));
  *(_QWORD *)(a2 + 24) = v18;
  if ( RtlStringCchLengthW(v18, v16, &v38) )
    return 3221225485LL;
  RtlInitUnicodeString(&v39, *(PCWSTR *)(a2 + 24));
  v19 = (const wchar_t *)(a2 + 2 * (v17 + 38));
  *(_QWORD *)(a2 + 32) = v19;
  if ( RtlStringCchLengthW(v19, v16 - (unsigned int)v38 - 1, &v38) )
    return 3221225485LL;
  RtlInitUnicodeString(&Source, *(PCWSTR *)(a2 + 32));
  if ( a5 < 0x4C )
    return 3221225507LL;
  memset(v44, 0, 0x4Cu);
  *(_QWORD *)&v44[0] = *(_QWORD *)(v9 + 2332);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
    WPP_SF_ZZD(
      WPP_GLOBAL_Control->AttachedDevice,
      v20,
      v21,
      (unsigned int)&DestinationString,
      (__int64)&v39,
      *(_DWORD *)(a2 + 16));
  v22 = *(_DWORD *)(a2 + 16);
  if ( v22 == 5 )
  {
    if ( Source.Length )
    {
      v23 = (void *)NfsRdrpConcatDomainAndUser(&Source, &DestinationString);
      if ( !v23 )
      {
        inserted = -1073741670;
LABEL_67:
        memset(a4, 0, 0x4Cu);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids);
        return (unsigned int)inserted;
      }
      UidGidFromPasswdGroupByUserName = NfsRdrpGetUidGidFromPasswdGroupByUserName(v9, &DestinationString, &Source, v44);
      if ( UidGidFromPasswdGroupByUserName < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids);
        UidGidFromPasswdGroupByUserName = MapGetUnixCredsFromNTUserName(a1, &v42, v23, v44);
      }
      if ( UidGidFromPasswdGroupByUserName < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids);
      }
      ExFreePoolWithTag(v23, 0);
      if ( UidGidFromPasswdGroupByUserName < 0 )
      {
        v26 = 0;
        LODWORD(v33) = 0;
        v27 = 0;
        LODWORD(pcchLength) = 0;
        LOBYTE(v21) = 0;
        v31 = 0;
        v28 = 0;
        v32[0] = 0;
        DWORD2(v44[0]) = 0;
        if ( (*(_DWORD *)(v9 + 2316) & 8) != 0 )
        {
          v20 = 3221226238LL;
LABEL_44:
          if ( (int)v20 >= 0 && ((_BYTE)v21 || v28) )
          {
            v29 = v44[0];
            if ( (_BYTE)v21 )
              v29 = v26;
            LODWORD(v44[0]) = v29;
            if ( v28 )
              DWORD1(v44[0]) = v27;
          }
          goto LABEL_53;
        }
        v20 = 0;
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 2352));
        if ( (_InterlockedCompareExchange((volatile signed __int32 *)(v9 + 2316), 0, 0) & 8) != 0 )
        {
          _InterlockedDecrement((volatile signed __int32 *)(v9 + 2352));
          v20 = 3221226238LL;
        }
        if ( (int)v20 >= 0 )
        {
          v20 = (unsigned int)NfsUpCallGetUidGidWithLdapClient(
                                *(_QWORD *)(v9 + 2016),
                                (unsigned int)&Source,
                                (unsigned int)&DestinationString,
                                (unsigned int)&v40,
                                (__int64)&v33,
                                (__int64)&pcchLength,
                                (__int64)&v31,
                                (__int64)v32);
          _InterlockedDecrement((volatile signed __int32 *)(v9 + 2352));
          v26 = v33;
          v27 = pcchLength;
          LOBYTE(v21) = v31;
          v28 = v32[0];
          goto LABEL_44;
        }
      }
    }
  }
  else if ( v22 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids);
    inserted = -1073741811;
    goto LABEL_67;
  }
LABEL_53:
  if ( (*(_DWORD *)(a2 + 20) & 1) != 0 )
  {
    if ( (unsigned int)NuiUpdateDefault(
                         (unsigned int)&AuthenticationId,
                         (unsigned int)&DestinationString,
                         (unsigned int)&v39,
                         (unsigned int)&Source,
                         *(_DWORD *)(a2 + 16),
                         16,
                         (__int64)v44,
                         0) )
    {
      inserted = NuiInsertDefault(
                   (unsigned int)&AuthenticationId,
                   (unsigned int)&DestinationString,
                   (unsigned int)&v39,
                   (unsigned int)&Source,
                   *(_DWORD *)(a2 + 16),
                   v30,
                   (__int64)v44);
      if ( inserted < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids);
        goto LABEL_67;
      }
    }
  }
  *a4 = v44[0];
  a4[1] = v44[1];
  a4[2] = v44[2];
  a4[3] = v44[3];
  *(_OWORD *)((char *)a4 + 60) = *(_OWORD *)((char *)&v44[3] + 12);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_ll(WPP_GLOBAL_Control->AttachedDevice, v20, v21, LODWORD(v44[0]), DWORD1(v44[0]));
  return 0;
}

```

## disassembly

```asm
0x140016cb8  mov     r11, rsp
0x140016cbb  push    rbx
0x140016cbc  push    rdi
0x140016cbd  push    r12
0x140016cbf  push    r13
0x140016cc1  push    r14
0x140016cc3  push    r15
0x140016cc5  sub     rsp, 148h
0x140016ccc  mov     rax, cs:__security_cookie
0x140016cd3  xor     rax, rsp
0x140016cd6  mov     [rsp+178h+var_48], rax
0x140016cde  mov     r12, r9
0x140016ce1  mov     r14d, r8d
0x140016ce4  mov     rbx, rdx
0x140016ce7  mov     r13, rcx
0x140016cea  xor     r15d, r15d
0x140016ced  mov     qword ptr [rsp+178h+DestinationString.Length], r15
0x140016cf2  mov     [rsp+178h+DestinationString.Buffer], r15
0x140016cf7  mov     [r11-0E0h], r15
0x140016cfe  mov     [r11-0D8h], r15
0x140016d05  mov     [r11-0F0h], r15
0x140016d0c  mov     [r11-0E8h], r15
0x140016d13  mov     qword ptr [rsp+178h+Source.Length], r15
0x140016d18  mov     [rsp+178h+Source.Buffer], r15
0x140016d1d  xor     edx, edx; Val
0x140016d1f  lea     r8d, [r15+4Ch]; Size
0x140016d23  lea     rcx, [r11-98h]; void *
0x140016d2a  call    memset
0x140016d2f  mov     qword ptr [rsp+178h+AuthenticationId.LowPart], r15
0x140016d34  xorps   xmm0, xmm0
0x140016d37  movups  xmmword ptr [rsp+178h+SubjectContext.ClientToken], xmm0
0x140016d3f  movups  xmmword ptr [rsp+178h+SubjectContext.PrimaryToken], xmm0
0x140016d47  xorps   xmm1, xmm1
0x140016d4a  xor     eax, eax
0x140016d4c  movups  [rsp+178h+var_B0], xmm1
0x140016d54  mov     [rsp+178h+var_A0], eax
0x140016d5b  mov     [rsp+178h+pcchLength], r15
0x140016d60  mov     [rsp+178h+var_130], r15
0x140016d65  mov     [rsp+178h+var_F8], r15
0x140016d6d  lea     rax, WPP_GLOBAL_Control
0x140016d74  mov     rcx, cs:WPP_GLOBAL_Control
0x140016d7b  cmp     rcx, rax
0x140016d7e  jz      short loc_140016D9E
0x140016d80  mov     eax, [rcx+2Ch]
0x140016d83  test    al, 8
0x140016d85  jz      short loc_140016D9E
0x140016d87  lea     edx, [r15+1Ch]
0x140016d8b  mov     r9, rbx
0x140016d8e  lea     r8, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids
0x140016d95  mov     rcx, [rcx+18h]
0x140016d99  call    WPP_SF_q
0x140016d9e  mov     rdi, [r13+50h]
0x140016da2  movups  xmm0, xmmword ptr [rdi+560h]
0x140016da9  movups  [rsp+178h+var_B0], xmm0
0x140016db1  mov     eax, [rdi+570h]
0x140016db7  mov     [rsp+178h+var_A0], eax
0x140016dbe  lea     rcx, [rsp+178h+SubjectContext]; SubjectContext
0x140016dc6  call    cs:__imp_SeCaptureSubjectContext
0x140016dcd  nop     dword ptr [rax+rax+00h]
0x140016dd2  mov     rcx, [rsp+178h+SubjectContext.PrimaryToken]
0x140016dda  mov     rax, [rsp+178h+SubjectContext.ClientToken]
0x140016de2  test    rax, rax
0x140016de5  cmovnz  rcx, rax; Token
0x140016de9  lea     rdx, [rsp+178h+AuthenticationId]; AuthenticationId
0x140016dee  call    cs:__imp_SeQueryAuthenticationIdToken
0x140016df5  nop     dword ptr [rax+rax+00h]
0x140016dfa  lea     rcx, [rsp+178h+SubjectContext]; SubjectContext
0x140016e02  call    cs:__imp_SeReleaseSubjectContext
0x140016e09  nop     dword ptr [rax+rax+00h]
0x140016e0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e15  lea     rax, WPP_GLOBAL_Control
0x140016e1c  cmp     rcx, rax
0x140016e1f  jz      short loc_140016E4C
0x140016e21  test    dword ptr [rcx+2Ch], 20000h
0x140016e28  jz      short loc_140016E4C
0x140016e2a  mov     edx, 1Dh
0x140016e2f  mov     eax, [rsp+178h+AuthenticationId.HighPart]
0x140016e33  mov     dword ptr [rsp+178h+var_158], eax
0x140016e37  mov     r9d, [rsp+178h+AuthenticationId.LowPart]
0x140016e3c  lea     r8, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids
0x140016e43  mov     rcx, [rcx+18h]
0x140016e47  call    WPP_SF_dd
0x140016e4c  cmp     r14d, 30h ; '0'
0x140016e50  jb      loc_1400173C8
0x140016e56  test    rbx, rbx
0x140016e59  jz      loc_1400173C8
0x140016e5f  lea     rcx, [rbx+28h]; psz
0x140016e63  mov     [rbx], rcx
0x140016e66  lea     rax, [r14-28h]
0x140016e6a  shr     rax, 1
0x140016e6d  mov     r14d, eax
0x140016e70  mov     edx, eax; cchMax
0x140016e72  lea     r8, [rsp+178h+pcchLength]; pcchLength
0x140016e77  call    RtlStringCchLengthW
0x140016e7c  test    eax, eax
0x140016e7e  jz      short loc_140016E8A
0x140016e80  mov     eax, 0C000000Dh
0x140016e85  jmp     loc_1400173CD
0x140016e8a  mov     rdx, [rbx]; SourceString
0x140016e8d  lea     rcx, [rsp+178h+DestinationString]; DestinationString
0x140016e92  call    cs:__imp_RtlInitUnicodeString
0x140016e99  nop     dword ptr [rax+rax+00h]
0x140016e9e  mov     r15, [rsp+178h+pcchLength]
0x140016ea3  sub     r14d, r15d
0x140016ea6  dec     r14d
0x140016ea9  lea     rcx, [r15+15h]
0x140016ead  lea     rcx, [rbx+rcx*2]; psz
0x140016eb1  mov     [rbx+8], rcx
0x140016eb5  mov     edx, r14d; cchMax
0x140016eb8  lea     r8, [rsp+178h+var_130]; pcchLength
0x140016ebd  call    RtlStringCchLengthW
0x140016ec2  test    eax, eax
0x140016ec4  jz      short loc_140016ED0
0x140016ec6  mov     eax, 0C000000Dh
0x140016ecb  jmp     loc_1400173CD
0x140016ed0  mov     rdx, [rbx+8]; SourceString
0x140016ed4  lea     rcx, [rsp+178h+var_E0]; DestinationString
0x140016edc  call    cs:__imp_RtlInitUnicodeString
0x140016ee3  nop     dword ptr [rax+rax+00h]
0x140016ee8  mov     rax, [rsp+178h+var_130]
0x140016eed  sub     r14d, eax
0x140016ef0  dec     r14d
0x140016ef3  add     r15, rax
0x140016ef6  lea     rcx, [r15+16h]
0x140016efa  lea     rcx, [rbx+rcx*2]; psz
0x140016efe  mov     [rbx+18h], rcx
0x140016f02  mov     edx, r14d; cchMax
0x140016f05  lea     r8, [rsp+178h+var_F8]; pcchLength
0x140016f0d  call    RtlStringCchLengthW
0x140016f12  test    eax, eax
0x140016f14  jz      short loc_140016F20
0x140016f16  mov     eax, 0C000000Dh
0x140016f1b  jmp     loc_1400173CD
0x140016f20  mov     rdx, [rbx+18h]; SourceString
0x140016f24  lea     rcx, [rsp+178h+var_F0]; DestinationString
0x140016f2c  call    cs:__imp_RtlInitUnicodeString
0x140016f33  nop     dword ptr [rax+rax+00h]
0x140016f38  lea     rcx, [r15+26h]
0x140016f3c  lea     rcx, [rbx+rcx*2]; psz
0x140016f40  mov     [rbx+20h], rcx
0x140016f44  sub     r14d, dword ptr [rsp+178h+var_F8]
0x140016f4c  lea     edx, [r14-1]; cchMax
0x140016f50  lea     r8, [rsp+178h+var_F8]; pcchLength
0x140016f58  call    RtlStringCchLengthW
0x140016f5d  xor     r14d, r14d
0x140016f60  test    eax, eax
0x140016f62  jz      short loc_140016F6E
0x140016f64  mov     eax, 0C000000Dh
0x140016f69  jmp     loc_1400173CD
0x140016f6e  mov     rdx, [rbx+20h]; SourceString
0x140016f72  lea     rcx, [rsp+178h+Source]; DestinationString
0x140016f77  call    cs:__imp_RtlInitUnicodeString
0x140016f7e  nop     dword ptr [rax+rax+00h]
0x140016f83  cmp     [rsp+178h+arg_20], 4Ch ; 'L'
0x140016f8b  jnb     short loc_140016F97
0x140016f8d  mov     eax, 0C0000023h
0x140016f92  jmp     loc_1400173CD
0x140016f97  xor     edx, edx; Val
0x140016f99  lea     r8d, [rdx+4Ch]; Size
0x140016f9d  lea     rcx, [rsp+178h+var_98]; void *
0x140016fa5  call    memset
0x140016faa  mov     eax, [rdi+91Ch]
0x140016fb0  mov     dword ptr [rsp+178h+var_98], eax
0x140016fb7  mov     eax, [rdi+920h]
0x140016fbd  mov     dword ptr [rsp+178h+var_98+4], eax
0x140016fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140016fcb  lea     r15, WPP_GLOBAL_Control
0x140016fd2  cmp     rcx, r15
0x140016fd5  jz      short loc_140017000
0x140016fd7  mov     eax, [rcx+2Ch]
0x140016fda  test    al, 2
0x140016fdc  jz      short loc_140017000
0x140016fde  mov     eax, [rbx+10h]
0x140016fe1  mov     dword ptr [rsp+178h+var_150], eax
0x140016fe5  lea     rax, [rsp+178h+var_F0]
0x140016fed  mov     [rsp+178h+var_158], rax
0x140016ff2  lea     r9, [rsp+178h+DestinationString]
0x140016ff7  mov     rcx, [rcx+18h]
0x140016ffb  call    WPP_SF_ZZD
0x140017000  mov     r9d, [rbx+10h]
0x140017004  cmp     r9d, 5
0x140017008  jnz     loc_14001721B
0x14001700e  cmp     [rsp+178h+Source.Length], r14w
0x140017014  jbe     loc_140017224
0x14001701a  lea     rdx, [rsp+178h+DestinationString]; PCUNICODE_STRING
0x14001701f  lea     rcx, [rsp+178h+Source]; Source
0x140017024  call    NfsRdrpConcatDomainAndUser
0x140017029  mov     r15, rax
0x14001702c  test    rax, rax
0x14001702f  jnz     short loc_140017042
0x140017031  mov     ebx, 0C000009Ah
0x140017036  lea     r15, WPP_GLOBAL_Control
0x14001703d  jmp     loc_140017384
0x140017042  lea     r9, [rsp+178h+var_98]
0x14001704a  lea     r8, [rsp+178h+Source]
0x14001704f  lea     rdx, [rsp+178h+DestinationString]
0x140017054  mov     rcx, rdi
0x140017057  call    NfsRdrpGetUidGidFromPasswdGroupByUserName
0x14001705c  mov     r14d, eax
0x14001705f  test    eax, eax
0x140017061  jns     short loc_1400170B4
0x140017063  mov     rcx, cs:WPP_GLOBAL_Control
0x14001706a  lea     rax, WPP_GLOBAL_Control
0x140017071  cmp     rcx, rax
0x140017074  jz      short loc_140017096
0x140017076  mov     edx, [rcx+2Ch]
0x140017079  test    dl, 1
0x14001707c  jz      short loc_140017096
0x14001707e  mov     edx, 1Fh
0x140017083  mov     r9d, r14d
0x140017086  lea     r8, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids
0x14001708d  mov     rcx, [rcx+18h]
0x140017091  call    WPP_SF_d
0x140017096  lea     r9, [rsp+178h+var_98]
0x14001709e  mov     r8, r15
0x1400170a1  lea     rdx, [rsp+178h+var_B0]
0x1400170a9  mov     rcx, r13
0x1400170ac  call    MapGetUnixCredsFromNTUserName
0x1400170b1  mov     r14d, eax
0x1400170b4  test    r14d, r14d
0x1400170b7  jns     short loc_1400170EB
0x1400170b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400170c0  lea     rax, WPP_GLOBAL_Control
0x1400170c7  cmp     rcx, rax
0x1400170ca  jz      short loc_1400170EB
0x1400170cc  mov     eax, [rcx+2Ch]
0x1400170cf  test    al, 1
0x1400170d1  jz      short loc_1400170EB
0x1400170d3  mov     edx, 20h ; ' '
0x1400170d8  mov     r9d, r14d
0x1400170db  lea     r8, WPP_6e2ab52aad8b3bbfdaad4cd7cd77f43e_Traceguids
0x1400170e2  mov     rcx, [rcx+18h]
0x1400170e6  call    WPP_SF_d
0x1400170eb  xor     edx, edx; Tag
0x1400170ed  mov     rcx, r15; P
0x1400170f0  call    cs:__imp_ExFreePoolWithTag
0x1400170f7  nop     dword ptr [rax+rax+00h]
0x1400170fc  test    r14d, r14d
0x1400170ff  jns     loc_14001720F
0x140017105  xor     r14d, r14d
0x140017108  mov     r11d, r14d
0x14001710b  mov     dword ptr [rsp+178h+var_130], r14d
0x140017110  mov     r10d, r14d
0x140017113  mov     dword ptr [rsp+178h+pcchLength], r14d
0x140017118  mov     r8b, r14b
0x14001711b  mov     [rsp+178h+var_138], r14b
0x140017120  mov     r9b, r14b
0x140017123  mov     [rsp+178h+var_137], r14b
0x140017128  mov     dword ptr [rsp+178h+var_98+8], r14d
0x140017130  mov     eax, [rdi+90Ch]
0x140017136  test    al, 8
0x140017138  jz      short loc_140017144
0x14001713a  mov     edx, 0C00002FEh
0x14001713f  jmp     loc_1400171D6
0x140017144  mov     edx, r14d
0x140017147  lock inc dword ptr [rdi+930h]
0x14001714e  mov     ecx, r14d
0x140017151  xor     eax, eax
0x140017153  lock cmpxchg [rdi+90Ch], ecx
0x14001715b  test    al, 8
0x14001715d  jz      short loc_14001716B
0x14001715f  lock dec dword ptr [rdi+930h]
0x140017166  mov     edx, 0C00002FEh
0x14001716b  test    edx, edx
0x14001716d  js      loc_140017212
0x140017173  lea     rax, [rsp+178h+var_137]
0x140017178  mov     [rsp+178h+var_140], rax
0x14001717d  lea     rax, [rsp+178h+var_138]
0x140017182  mov     [rsp+178h+var_148], rax
0x140017187  lea     rax, [rsp+178h+pcchLength]
0x14001718c  mov     [rsp+178h+var_150], rax
0x140017191  lea     rax, [rsp+178h+var_130]
0x140017196  mov     [rsp+178h+var_158], rax
0x14001719b  lea     r9, [rsp+178h+var_E0]
0x1400171a3  lea     r8, [rsp+178h+DestinationString]
0x1400171a8  lea     rdx, [rsp+178h+Source]
0x1400171ad  mov     rcx, [rdi+7E0h]
0x1400171b4  call    NfsUpCallGetUidGidWithLdapClient
0x1400171b9  mov     edx, eax
0x1400171bb  lock dec dword ptr [rdi+930h]
0x1400171c2  mov     r11d, dword ptr [rsp+178h+var_130]
0x1400171c7  mov     r10d, dword ptr [rsp+178h+pcchLength]
0x1400171cc  mov     r8b, [rsp+178h+var_138]
0x1400171d1  mov     r9b, [rsp+178h+var_137]
0x1400171d6  test    edx, edx
0x1400171d8  js      short loc_140017212
0x1400171da  test    r8b, r8b
0x1400171dd  jnz     short loc_1400171E4
0x1400171df  test    r9b, r9b
0x1400171e2  jz      short loc_140017212
0x1400171e4  mov     eax, dword ptr [rsp+178h+var_98]
0x1400171eb  test    r8b, r8b
0x1400171ee  cmovnz  eax, r11d
0x1400171f2  mov     dword ptr [rsp+178h+var_98], eax
0x1400171f9  lea     r15, WPP_GLOBAL_Control
0x140017200  test    r9b, r9b
0x140017203  jz      short loc_140017224
0x140017205  mov     dword ptr [rsp+178h+var_98+4], r10d
0x14001720d  jmp     short loc_140017224
0x14001720f  xor     r14d, r14d
  ... truncated ...
```
