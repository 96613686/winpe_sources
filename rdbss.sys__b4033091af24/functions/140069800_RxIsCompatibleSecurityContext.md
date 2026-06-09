# RxIsCompatibleSecurityContext

- ea: `0x140069800`
- end: `0x140069966`
- name: `RxIsCompatibleSecurityContext`
- size: `358`
- prototype: `__int64 __fastcall(PLUID LogonId)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14004d498`
- `0x140069680`

## callees

- `0x140017310`
- `0x140022574`
- `0x1400225d4`
- `0x140025d80`
- `0x140069800`
- `0x14006e150`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14007e8d5`
- `ntoskrnl!ExAllocatePool2` at `0x14007e919`
- `ntoskrnl!ExAllocatePool2` at `0x14007e8d5`
- `ntoskrnl!ExAllocatePool2` at `0x14007e919`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007eadd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007eafc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007eadd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007eafc`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x14007eac7`
- `ntoskrnl!LsaFreeReturnBuffer` at `0x14007eac7`
- `ksecdd!SspiFreeAuthIdentity` at `0x14007eaa7`
- `ksecdd!SspiFreeAuthIdentity` at `0x14007eaa7`
- `ksecdd!MapSecurityError` at `0x14007e96c`
- `ksecdd!MapSecurityError` at `0x14007ea00`
- `ksecdd!MapSecurityError` at `0x14007e96c`
- `ksecdd!MapSecurityError` at `0x14007ea00`
- `ksecdd!GetSecurityUserInfo` at `0x14007e85b`
- `ksecdd!GetSecurityUserInfo` at `0x14007e85b`
- `ksecdd!SspiEncodeStringsAsAuthIdentity` at `0x14007e95c`
- `ksecdd!SspiEncodeStringsAsAuthIdentity` at `0x14007e95c`
- `ksecdd!SspiCompareAuthIdentities` at `0x14007e9f0`
- `ksecdd!SspiCompareAuthIdentities` at `0x14007e9f0`

## pseudocode

```c
__int64 __fastcall RxIsCompatibleSecurityContext(PLUID LogonId, int *a2, __int64 a3)
{
  int v4; // ecx
  int v6; // esi
  __int64 v7; // rax
  unsigned int v8; // edi
  int v9; // ebp
  struct _LUID v11; // rdx
  WCHAR *v12; // r12
  WCHAR *v13; // r15
  struct _LUID v14; // rcx
  NTSTATUS SecurityUserInfo; // eax
  PSecurityUserData v16; // rdi
  SECURITY_STRING *p_LogonDomainName; // rbp
  WCHAR *Pool2; // rax
  WCHAR *v19; // rax
  SECURITY_STATUS v20; // ebp
  NTSTATUS v21; // eax
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE v22; // rcx
  char v23; // r14
  SECURITY_STATUS v24; // ebp
  _QWORD v25[3]; // [rsp+50h] [rbp-58h] BYREF
  BOOLEAN SameSuppliedIdentity; // [rsp+B0h] [rbp+8h] BYREF
  BOOLEAN SameSuppliedUser; // [rsp+B8h] [rbp+10h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppAuthIdentity; // [rsp+C0h] [rbp+18h] BYREF
  PSecurityUserData UserInformation; // [rsp+C8h] [rbp+20h] BYREF

  v4 = *a2;
  v6 = 0;
  v25[0] = 0x20000;
  SameSuppliedUser = 0;
  SameSuppliedIdentity = 0;
  UserInformation = 0;
  ppAuthIdentity = 0;
  v25[1] = &dword_14002991C;
  if ( (LogonId->LowPart != v4 || LogonId->HighPart != a2[1])
    && (LogonId[1].LowPart != v4 || LogonId[1].HighPart != a2[1]) )
  {
    v8 = -1073741802;
    v9 = 1;
    goto LABEL_5;
  }
  v7 = *((_QWORD *)a2 + 4);
  if ( !v7 || !*(_QWORD *)(v7 + 8) )
  {
    v8 = 0;
    v6 = 1295;
    v9 = 0;
    goto LABEL_5;
  }
  v11 = LogonId[4];
  v12 = 0;
  v13 = 0;
  if ( !*(_QWORD *)&v11
    || (_m_prefetchw((const void *)(*(_QWORD *)&v11 + 64LL)),
        (_InterlockedXor((volatile signed __int32 *)(*(_QWORD *)&v11 + 64LL), 0) & 1) == 0) )
  {
    v14 = LogonId[4];
    if ( v14 )
    {
      v22 = *(PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)(*(_QWORD *)&v14 + 8LL);
      v23 = 0;
      ppAuthIdentity = v22;
    }
    else
    {
      SecurityUserInfo = GetSecurityUserInfo(LogonId, 1u, &UserInformation);
      if ( SecurityUserInfo >= 0 )
      {
        v16 = UserInformation;
        p_LogonDomainName = &UserInformation->LogonDomainName;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_DDD(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids,
            (unsigned int)SecurityUserInfo,
            LogonId->HighPart,
            LogonId->LowPart);
        }
        v16 = (PSecurityUserData)v25;
        p_LogonDomainName = (SECURITY_STRING *)v25;
      }
      Pool2 = (WCHAR *)ExAllocatePool2(64, v16->UserName.Length + 2LL, 1917024338);
      v13 = Pool2;
      if ( !Pool2 )
      {
        v8 = -1073741670;
        v9 = 0;
        goto LABEL_53;
      }
      memmove(Pool2, v16->UserName.Buffer, v16->UserName.Length);
      v19 = (WCHAR *)ExAllocatePool2(64, p_LogonDomainName->Length + 2LL, 1917024338);
      v12 = v19;
      if ( !v19 )
      {
        v8 = -1073741670;
        v9 = 0;
        goto LABEL_53;
      }
      memmove(v19, p_LogonDomainName->Buffer, p_LogonDomainName->Length);
      v20 = SspiEncodeStringsAsAuthIdentity(v13, v12, 0, &ppAuthIdentity);
      v21 = MapSecurityError(v20);
      v8 = v21;
      if ( v21 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids,
            (unsigned int)v21,
            v20);
        }
        v9 = 0;
        goto LABEL_53;
      }
      v22 = ppAuthIdentity;
      v23 = 1;
    }
    v24 = SspiCompareAuthIdentities(
            v22,
            *(PSEC_WINNT_AUTH_IDENTITY_OPAQUE *)(*((_QWORD *)a2 + 4) + 8LL),
            &SameSuppliedUser,
            &SameSuppliedIdentity);
    v8 = MapSecurityError(v24);
    if ( (v8 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids, v8, v24);
      }
      goto LABEL_50;
    }
    if ( v23 || !*(_QWORD *)(*((_QWORD *)a2 + 4) + 24LL) )
    {
      if ( !SameSuppliedUser )
      {
        v8 = -1073741419;
        v6 = 1409;
LABEL_50:
        v9 = 0;
        if ( v23 && ppAuthIdentity )
          SspiFreeAuthIdentity(ppAuthIdentity);
        goto LABEL_53;
      }
    }
    else if ( !SameSuppliedIdentity )
    {
      v8 = -1073741419;
      v6 = 1417;
      v9 = 0;
      goto LABEL_53;
    }
    v8 = 0;
    goto LABEL_50;
  }
  RxDereferenceCredential(*(_QWORD *)&LogonId[4]);
  LogonId[4] = 0;
  v6 = 1312;
  v8 = 0;
  v9 = 0;
LABEL_53:
  if ( UserInformation )
    LsaFreeReturnBuffer(UserInformation);
  if ( v13 )
    ExFreePoolWithTag(v13, 0);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
LABEL_5:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_DDdddd(WPP_GLOBAL_Control->AttachedDevice, SameSuppliedUser, a3, v8, v6, v9);
  }
  return v8;
}

```

## disassembly

```asm
0x140069800  mov     rax, rsp
0x140069803  push    rbp
0x140069804  push    rsi
0x140069805  push    rdi
0x140069806  sub     rsp, 90h
0x14006980d  mov     [rax-20h], rbx
0x140069811  mov     rdi, rcx
0x140069814  mov     ecx, [rdx]
0x140069816  mov     rbx, rdx
0x140069819  mov     [rax-28h], r12
0x14006981d  mov     [rax-30h], r13
0x140069821  xor     r13d, r13d
0x140069824  mov     esi, r13d
0x140069827  mov     [rax-38h], r14
0x14006982b  lea     r14, WPP_GLOBAL_Control
0x140069832  mov     qword ptr [rax-58h], 20000h
0x14006983a  mov     [rax+10h], sil
0x14006983e  mov     [rax+8], sil
0x140069842  mov     [rax+20h], r13
0x140069846  mov     [rax+18h], r13
0x14006984a  lea     rax, dword_14002991C
0x140069851  mov     [rsp+0A8h+var_50], rax
0x140069856  cmp     [rdi], ecx
0x140069858  jnz     short loc_1400698B7
0x14006985a  mov     eax, [rdx+4]
0x14006985d  cmp     [rdi+4], eax
0x140069860  jnz     short loc_1400698B7
0x140069862  mov     rax, [rdx+20h]
0x140069866  test    rax, rax
0x140069869  jnz     short loc_1400698C8
0x14006986b  mov     edi, r13d
0x14006986e  mov     esi, 50Fh
0x140069873  mov     ebp, r13d
0x140069876  mov     rcx, cs:WPP_GLOBAL_Control
0x14006987d  mov     r13, [rsp+0A8h+var_30]
0x140069882  cmp     rcx, r14
0x140069885  mov     r14, [rsp+0A8h+var_38]
0x14006988a  mov     r12, [rsp+0A8h+var_28]
0x140069892  mov     rbx, [rsp+0A8h+var_20]
0x14006989a  jz      short loc_1400698A9
0x14006989c  test    dword ptr [rcx+2Ch], 1000h
0x1400698a3  jnz     loc_14006992B
0x1400698a9  mov     eax, edi
0x1400698ab  add     rsp, 90h
0x1400698b2  pop     rdi
0x1400698b3  pop     rsi
0x1400698b4  pop     rbp
0x1400698b5  retn
0x1400698b7  cmp     [rdi+8], ecx
0x1400698ba  jz      short loc_14006991D
0x1400698bc  mov     edi, 0C0000016h
0x1400698c1  mov     ebp, 1
0x1400698c6  jmp     short loc_140069876
0x1400698c8  cmp     [rax+8], rsi
0x1400698cc  jz      short loc_14006986B
0x1400698ce  mov     rdx, [rdi+20h]
0x1400698d2  mov     r12, r13
0x1400698d5  mov     [rsp+0A8h+var_40], r15
0x1400698da  mov     r15, r13
0x1400698dd  test    rdx, rdx
0x1400698e0  jz      loc_14007E83E
0x1400698e6  prefetchw byte ptr [rdx+40h]
0x1400698ea  mov     eax, [rdx+40h]
0x1400698ed  mov     ecx, eax
0x1400698ef  xor     ecx, esi
0x1400698f1  lock cmpxchg [rdx+40h], ecx
0x1400698f6  jnz     short loc_1400698ED
0x1400698f8  test    al, 1
0x1400698fa  jz      loc_14007E83E
0x140069900  mov     rcx, [rdi+20h]
0x140069904  call    RxDereferenceCredential
0x140069909  mov     [rdi+20h], r13
0x14006990d  mov     esi, 520h
0x140069912  mov     edi, r13d
0x140069915  mov     ebp, r13d
0x140069918  jmp     loc_14007EABA
0x14006991d  mov     eax, [rdx+4]
0x140069920  cmp     [rdi+0Ch], eax
0x140069923  jz      loc_140069862
0x140069929  jmp     short loc_1400698BC
0x14006992b  cmp     byte ptr [rcx+29h], 2
0x14006992f  jb      loc_1400698A9
0x140069935  movzx   eax, [rsp+0A8h+SameSuppliedIdentity]
0x14006993d  mov     r9d, edi
0x140069940  movzx   edx, [rsp+0A8h+SameSuppliedUser]
0x140069948  mov     rcx, [rcx+18h]
0x14006994c  mov     [rsp+0A8h+var_68], eax
0x140069950  mov     [rsp+0A8h+var_70], edx
0x140069954  mov     [rsp+0A8h+var_80], ebp
0x140069958  mov     [rsp+0A8h+var_88], esi
0x14006995c  call    WPP_SF_DDdddd
0x140069961  jmp     loc_1400698A9
0x14007e83e  mov     rcx, [rdi+20h]
0x14007e842  test    rcx, rcx
0x14007e845  jnz     loc_14007E9C9
0x14007e84b  lea     r8, [rsp+0A8h+UserInformation]; UserInformation
0x14007e853  mov     edx, 1; Flags
0x14007e858  mov     rcx, rdi; LogonId
0x14007e85b  call    cs:__imp_GetSecurityUserInfo
0x14007e862  nop     dword ptr [rax+rax+00h]
0x14007e867  mov     r9d, eax
0x14007e86a  test    eax, eax
0x14007e86c  jns     short loc_14007E8B7
0x14007e86e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e875  cmp     rcx, r14
0x14007e878  jz      short loc_14007E8AB
0x14007e87a  test    dword ptr [rcx+2Ch], 1000h
0x14007e881  jz      short loc_14007E8AB
0x14007e883  cmp     byte ptr [rcx+29h], 2
0x14007e887  jb      short loc_14007E8AB
0x14007e889  mov     eax, [rdi]
0x14007e88b  lea     r8, WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids
0x14007e892  mov     rcx, [rcx+18h]
0x14007e896  mov     edx, 12h
0x14007e89b  mov     [rsp+0A8h+var_80], eax
0x14007e89f  mov     eax, [rdi+4]
0x14007e8a2  mov     [rsp+0A8h+var_88], eax
0x14007e8a6  call    WPP_SF_DDD
0x14007e8ab  lea     rdi, [rsp+0A8h+var_58]
0x14007e8b0  lea     rbp, [rsp+0A8h+var_58]
0x14007e8b5  jmp     short loc_14007E8C3
0x14007e8b7  mov     rdi, [rsp+0A8h+UserInformation]
0x14007e8bf  lea     rbp, [rdi+10h]
0x14007e8c3  movzx   edx, word ptr [rdi]
0x14007e8c6  mov     ecx, 40h ; '@'
0x14007e8cb  add     rdx, 2
0x14007e8cf  mov     r8d, 72437852h
0x14007e8d5  call    cs:__imp_ExAllocatePool2
0x14007e8dc  nop     dword ptr [rax+rax+00h]
0x14007e8e1  mov     r15, rax
0x14007e8e4  test    rax, rax
0x14007e8e7  jnz     short loc_14007E8F6
0x14007e8e9  mov     edi, 0C000009Ah
0x14007e8ee  mov     ebp, r13d
0x14007e8f1  jmp     loc_14007EABA
0x14007e8f6  movzx   r8d, word ptr [rdi]; Size
0x14007e8fa  mov     rcx, r15; void *
0x14007e8fd  mov     rdx, [rdi+8]; Src
0x14007e901  call    memmove
0x14007e906  movzx   edx, word ptr [rbp+0]
0x14007e90a  mov     ecx, 40h ; '@'
0x14007e90f  add     rdx, 2
0x14007e913  mov     r8d, 72437852h
0x14007e919  call    cs:__imp_ExAllocatePool2
0x14007e920  nop     dword ptr [rax+rax+00h]
0x14007e925  mov     r12, rax
0x14007e928  test    rax, rax
0x14007e92b  jnz     short loc_14007E93A
0x14007e92d  mov     edi, 0C000009Ah
0x14007e932  mov     ebp, r13d
0x14007e935  jmp     loc_14007EABA
0x14007e93a  movzx   r8d, word ptr [rbp+0]; Size
0x14007e93f  mov     rcx, r12; void *
0x14007e942  mov     rdx, [rbp+8]; Src
0x14007e946  call    memmove
0x14007e94b  lea     r9, [rsp+0A8h+ppAuthIdentity]; ppAuthIdentity
0x14007e953  xor     r8d, r8d; pszPackedCredentialsString
0x14007e956  mov     rdx, r12; pszDomainName
0x14007e959  mov     rcx, r15; pszUserName
0x14007e95c  call    cs:__imp_SspiEncodeStringsAsAuthIdentity
0x14007e963  nop     dword ptr [rax+rax+00h]
0x14007e968  mov     ecx, eax; SecStatus
0x14007e96a  mov     ebp, eax
0x14007e96c  call    cs:__imp_MapSecurityError
0x14007e973  nop     dword ptr [rax+rax+00h]
0x14007e978  mov     edi, eax
0x14007e97a  test    eax, eax
0x14007e97c  jns     short loc_14007E9BC
0x14007e97e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e985  cmp     rcx, r14
0x14007e988  jz      short loc_14007E9B4
0x14007e98a  mov     edx, [rcx+2Ch]
0x14007e98d  test    dl, 1
0x14007e990  jz      short loc_14007E9B4
0x14007e992  cmp     byte ptr [rcx+29h], 1
0x14007e996  jb      short loc_14007E9B4
0x14007e998  mov     rcx, [rcx+18h]
0x14007e99c  lea     r8, WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids
0x14007e9a3  mov     edx, 13h
0x14007e9a8  mov     [rsp+0A8h+var_88], ebp
0x14007e9ac  mov     r9d, eax
0x14007e9af  call    WPP_SF_Dd
0x14007e9b4  mov     ebp, r13d
0x14007e9b7  jmp     loc_14007EABA
0x14007e9bc  mov     rcx, [rsp+0A8h+ppAuthIdentity]
0x14007e9c4  mov     r14b, 1
0x14007e9c7  jmp     short loc_14007E9D8
0x14007e9c9  mov     rcx, [rcx+8]; AuthIdentity1
0x14007e9cd  xor     r14b, r14b
0x14007e9d0  mov     [rsp+0A8h+ppAuthIdentity], rcx
0x14007e9d8  mov     rdx, [rbx+20h]
0x14007e9dc  lea     r9, [rsp+0A8h+SameSuppliedIdentity]; SameSuppliedIdentity
0x14007e9e4  lea     r8, [rsp+0A8h+SameSuppliedUser]; SameSuppliedUser
0x14007e9ec  mov     rdx, [rdx+8]; AuthIdentity2
0x14007e9f0  call    cs:__imp_SspiCompareAuthIdentities
0x14007e9f7  nop     dword ptr [rax+rax+00h]
0x14007e9fc  mov     ecx, eax; SecStatus
0x14007e9fe  mov     ebp, eax
0x14007ea00  call    cs:__imp_MapSecurityError
0x14007ea07  nop     dword ptr [rax+rax+00h]
0x14007ea0c  mov     edi, eax
0x14007ea0e  test    eax, eax
0x14007ea10  jns     short loc_14007EA51
0x14007ea12  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ea19  lea     rax, WPP_GLOBAL_Control
0x14007ea20  cmp     rcx, rax
0x14007ea23  jz      short loc_14007EA92
0x14007ea25  mov     edx, [rcx+2Ch]
0x14007ea28  test    dl, 1
0x14007ea2b  jz      short loc_14007EA92
0x14007ea2d  cmp     byte ptr [rcx+29h], 1
0x14007ea31  jb      short loc_14007EA92
0x14007ea33  mov     rcx, [rcx+18h]
0x14007ea37  lea     r8, WPP_b27d4ea20cf23c7ef3650225eec88b96_Traceguids
0x14007ea3e  mov     edx, 14h
0x14007ea43  mov     [rsp+0A8h+var_88], ebp
0x14007ea47  mov     r9d, edi
0x14007ea4a  call    WPP_SF_Dd
0x14007ea4f  jmp     short loc_14007EA92
0x14007ea51  test    r14b, r14b
0x14007ea54  jnz     short loc_14007EA79
0x14007ea56  mov     rax, [rbx+20h]
0x14007ea5a  cmp     [rax+18h], rsi
0x14007ea5e  jz      short loc_14007EA79
0x14007ea60  cmp     [rsp+0A8h+SameSuppliedIdentity], sil
0x14007ea68  jnz     short loc_14007EA8F
0x14007ea6a  mov     edi, 0C0000195h
0x14007ea6f  mov     esi, 589h
0x14007ea74  mov     ebp, r13d
0x14007ea77  jmp     short loc_14007EAB3
0x14007ea79  cmp     [rsp+0A8h+SameSuppliedUser], sil
0x14007ea81  jnz     short loc_14007EA8F
0x14007ea83  mov     edi, 0C0000195h
0x14007ea88  mov     esi, 581h
0x14007ea8d  jmp     short loc_14007EA92
0x14007ea8f  mov     edi, r13d
0x14007ea92  mov     ebp, r13d
0x14007ea95  test    r14b, r14b
0x14007ea98  jz      short loc_14007EAB3
0x14007ea9a  mov     rcx, [rsp+0A8h+ppAuthIdentity]; AuthData
0x14007eaa2  test    rcx, rcx
0x14007eaa5  jz      short loc_14007EAB3
0x14007eaa7  call    cs:__imp_SspiFreeAuthIdentity
0x14007eaae  nop     dword ptr [rax+rax+00h]
0x14007eab3  lea     r14, WPP_GLOBAL_Control
0x14007eaba  mov     rcx, [rsp+0A8h+UserInformation]; Buffer
0x14007eac2  test    rcx, rcx
0x14007eac5  jz      short loc_14007EAD3
0x14007eac7  call    cs:__imp_LsaFreeReturnBuffer
0x14007eace  nop     dword ptr [rax+rax+00h]
0x14007ead3  test    r15, r15
0x14007ead6  jz      short loc_14007EAE9
0x14007ead8  xor     edx, edx; Tag
0x14007eada  mov     rcx, r15; P
0x14007eadd  call    cs:__imp_ExFreePoolWithTag
0x14007eae4  nop     dword ptr [rax+rax+00h]
0x14007eae9  mov     r15, [rsp+0A8h+var_40]
0x14007eaee  test    r12, r12
0x14007eaf1  jz      loc_140069876
0x14007eaf7  xor     edx, edx; Tag
0x14007eaf9  mov     rcx, r12; P
0x14007eafc  call    cs:__imp_ExFreePoolWithTag
0x14007eb03  nop     dword ptr [rax+rax+00h]
0x14007eb08  nop
0x14007eb09  jmp     loc_140069876
```
