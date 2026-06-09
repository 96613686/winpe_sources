# KerbCreateTokenDacl(void *)

- ea: `0x180046100`
- end: `0x18004644e`
- name: `?KerbCreateTokenDacl@@YAJPEAX@Z`
- size: `846`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180046460`

## callees

- `0x180046100`
- `0x18006d3b4`
- `0x18006d780`
- `0x18008b70c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800463d3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800463d3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800462a2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800462a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800463eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800463f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046407`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046415`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046423`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800463eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800463f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046407`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046415`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180046423`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180046173`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180046173`
- `ntdll!NtClose` at `0x1800463dd`
- `ntdll!NtClose` at `0x180046432`
- `ntdll!NtClose` at `0x1800463dd`
- `ntdll!NtClose` at `0x180046432`
- `ntdll!NtSetSecurityObject` at `0x18004638e`
- `ntdll!NtSetSecurityObject` at `0x18004638e`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18004637c`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18004637c`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180046369`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180046369`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800462de`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800462f3`
- `ntdll!RtlAddAccessAllowedAce` at `0x18004630d`
- `ntdll!RtlAddAccessAllowedAce` at `0x180046326`
- `ntdll!RtlAddAccessAllowedAce` at `0x18004633e`
- `ntdll!RtlAddAccessAllowedAce` at `0x180046356`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800462de`
- `ntdll!RtlAddAccessAllowedAce` at `0x1800462f3`
- `ntdll!RtlAddAccessAllowedAce` at `0x18004630d`
- `ntdll!RtlAddAccessAllowedAce` at `0x180046326`
- `ntdll!RtlAddAccessAllowedAce` at `0x18004633e`
- `ntdll!RtlAddAccessAllowedAce` at `0x180046356`
- `ntdll!RtlCreateAcl` at `0x1800462c5`
- `ntdll!RtlCreateAcl` at `0x1800462c5`
- `ntdll!NtOpenProcessToken` at `0x1800461ad`
- `ntdll!NtOpenProcessToken` at `0x1800461ad`
- `ntdll!NtOpenThreadToken` at `0x180046167`
- `ntdll!NtOpenThreadToken` at `0x180046167`
- `ntdll!RtlEqualSid` at `0x180046253`
- `ntdll!RtlEqualSid` at `0x180046264`
- `ntdll!RtlEqualSid` at `0x180046253`
- `ntdll!RtlEqualSid` at `0x180046264`
- `ntdll!RtlLengthSid` at `0x18004620f`
- `ntdll!RtlLengthSid` at `0x18004621e`
- `ntdll!RtlLengthSid` at `0x18004622d`
- `ntdll!RtlLengthSid` at `0x18004623d`
- `ntdll!RtlLengthSid` at `0x180046271`
- `ntdll!RtlLengthSid` at `0x180046293`
- `ntdll!RtlLengthSid` at `0x18004620f`
- `ntdll!RtlLengthSid` at `0x18004621e`
- `ntdll!RtlLengthSid` at `0x18004622d`
- `ntdll!RtlLengthSid` at `0x18004623d`
- `ntdll!RtlLengthSid` at `0x180046271`
- `ntdll!RtlLengthSid` at `0x180046293`

## string_xrefs

- `0x18004639a`: `Failed to set the security info on the token: 0x%x`
- `0x1800463ab`: `KerbCreateTokenDacl`

## pseudocode

```c
__int64 __fastcall KerbCreateTokenDacl(HANDLE TokenHandle)
{
  struct _TOKEN_USER *v2; // rsi
  struct _TOKEN_USER *v3; // r12
  PSID *v4; // rdi
  struct _TOKEN_APPCONTAINER_INFORMATION *v5; // r14
  struct _ACL *v6; // r15
  NTSTATUS v7; // eax
  NTSTATUS TokenPackage; // ebx
  int TokenUser; // eax
  ULONG v10; // ebx
  ULONG v11; // ebx
  ULONG v12; // eax
  ULONG v13; // ebx
  ULONG v14; // eax
  int v15; // r13d
  struct _ACL *v16; // rax
  NTSTATUS v17; // eax
  struct _TOKEN_APPCONTAINER_INFORMATION *v19; // [rsp+30h] [rbp-39h] BYREF
  void *TokenHandlea; // [rsp+38h] [rbp-31h] BYREF
  HANDLE v21; // [rsp+40h] [rbp-29h] BYREF
  struct _TOKEN_USER *v22; // [rsp+48h] [rbp-21h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v24; // [rsp+70h] [rbp+7h]
  int v26; // [rsp+D8h] [rbp+6Fh] BYREF
  HLOCAL hMem; // [rsp+E0h] [rbp+77h] BYREF
  struct _TOKEN_USER *v28; // [rsp+E8h] [rbp+7Fh] BYREF

  v28 = 0;
  v22 = 0;
  hMem = 0;
  v19 = 0;
  v21 = 0;
  v2 = 0;
  TokenHandlea = 0;
  v3 = 0;
  v26 = 0;
  v4 = 0;
  v24 = 0;
  v5 = 0;
  v6 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v7 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandlea);
  TokenPackage = v7;
  if ( v7 < 0 )
  {
    if ( v7 != -1073741700 )
      goto LABEL_26;
  }
  else
  {
    RevertToSelf();
    TokenUser = KerbGetTokenUser(TokenHandlea, (struct _TOKEN_USER **)&hMem);
    v4 = (PSID *)hMem;
    TokenPackage = TokenUser;
    if ( TokenUser < 0 )
      goto LABEL_26;
  }
  TokenPackage = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &v21);
  if ( TokenPackage < 0 )
    goto LABEL_26;
  TokenPackage = KerbGetTokenUser(v21, &v28);
  if ( TokenPackage < 0 )
  {
LABEL_25:
    v2 = v28;
    goto LABEL_26;
  }
  TokenPackage = KerbGetTokenPackage(v21, &v26, &v19);
  if ( TokenPackage < 0 )
  {
LABEL_24:
    v5 = v19;
    goto LABEL_25;
  }
  TokenPackage = KerbGetTokenUser(TokenHandle, &v22);
  if ( TokenPackage < 0 )
  {
    v3 = v22;
    goto LABEL_24;
  }
  LODWORD(hMem) = 0;
  v2 = v28;
  v10 = RtlLengthSid(v28->User.Sid);
  v11 = RtlLengthSid(KerbGlobalAliasAdminsSid) + v10;
  v12 = RtlLengthSid(KerbGlobalLocalSystemSid);
  v3 = v22;
  v13 = RtlLengthSid(v22->User.Sid) + v12 + v11 + 40;
  if ( v4 && !RtlEqualSid(*v4, v2->User.Sid) && !RtlEqualSid(*v4, v3->User.Sid) )
  {
    v14 = RtlLengthSid(*v4);
    LODWORD(hMem) = 1;
    v13 += v14 + 8;
  }
  v15 = v26;
  v5 = v19;
  if ( v26 )
    v13 += RtlLengthSid(v19->TokenAppContainer) + 8;
  v16 = (struct _ACL *)LocalAlloc(0, v13);
  v6 = v16;
  if ( v16 )
  {
    RtlCreateAcl(v16, v13, 2u);
    RtlAddAccessAllowedAce(v6, 2u, 0xF01FFu, v2->User.Sid);
    RtlAddAccessAllowedAce(v6, 2u, 0xF01FFu, v3->User.Sid);
    if ( (_DWORD)hMem )
      RtlAddAccessAllowedAce(v6, 2u, 0xF01FFu, *v4);
    if ( v15 )
      RtlAddAccessAllowedAce(v6, 2u, 0xF01FFu, v5->TokenAppContainer);
    RtlAddAccessAllowedAce(v6, 2u, 0xF01FFu, KerbGlobalAliasAdminsSid);
    RtlAddAccessAllowedAce(v6, 2u, 0xF01FFu, KerbGlobalLocalSystemSid);
    RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v6, 0);
    v17 = NtSetSecurityObject(TokenHandle, 4u, SecurityDescriptor);
    TokenPackage = v17;
    if ( v17 < 0 )
      KerbTracerT::Log(1, "KerbCreateTokenDacl", 2312, "Failed to set the security info on the token: 0x%x", v17);
  }
  else
  {
    TokenPackage = -1073741670;
  }
LABEL_26:
  if ( TokenHandlea )
  {
    SetThreadToken(0, TokenHandlea);
    NtClose(TokenHandlea);
  }
  if ( v3 )
    LocalFree(v3);
  if ( v2 )
    LocalFree(v2);
  if ( v4 )
    LocalFree(v4);
  if ( v5 )
    LocalFree(v5);
  if ( v6 )
    LocalFree(v6);
  if ( v21 )
    NtClose(v21);
  return (unsigned int)TokenPackage;
}

```

## disassembly

```asm
0x180046100  mov     [rsp-8+Handle], rcx
0x180046105  push    rbp
0x180046106  push    rbx
0x180046107  push    rsi
0x180046108  push    rdi
0x180046109  push    r12
0x18004610b  push    r13
0x18004610d  push    r14
0x18004610f  push    r15
0x180046111  lea     rbp, [rsp-1Fh]
0x180046116  sub     rsp, 88h
0x18004611d  xor     eax, eax
0x18004611f  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180046123  xorps   xmm0, xmm0
0x180046126  mov     [rbp+57h+arg_18], rax
0x18004612a  mov     r13, rcx
0x18004612d  mov     [rbp+57h+var_78], rax
0x180046131  mov     r8b, 1; OpenAsSelf
0x180046134  mov     [rbp+57h+hMem], rax
0x180046138  lea     edx, [rax+0Ch]; DesiredAccess
0x18004613b  mov     [rbp+57h+var_90], rax
0x18004613f  lea     rcx, [rax-2]; ThreadHandle
0x180046143  mov     [rbp+57h+var_80], rax
0x180046147  mov     esi, eax
0x180046149  mov     [rbp+57h+TokenHandle], rax
0x18004614d  mov     r12d, eax
0x180046150  mov     [rbp+57h+arg_8], eax
0x180046153  mov     edi, eax
0x180046155  mov     [rbp+57h+var_50], rax
0x180046159  mov     r14d, eax
0x18004615c  mov     r15d, eax
0x18004615f  movups  [rbp+57h+SecurityDescriptor], xmm0
0x180046163  movups  [rbp+57h+var_60], xmm0
0x180046167  call    cs:__imp_NtOpenThreadToken
0x18004616d  mov     ebx, eax
0x18004616f  test    eax, eax
0x180046171  js      short loc_180046195
0x180046173  call    cs:__imp_RevertToSelf
0x180046179  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18004617d  lea     rdx, [rbp+57h+hMem]; struct _TOKEN_USER **
0x180046181  call    ?KerbGetTokenUser@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; KerbGetTokenUser(void *,_TOKEN_USER * *)
0x180046186  mov     rdi, [rbp+57h+hMem]
0x18004618a  mov     ebx, eax
0x18004618c  test    eax, eax
0x18004618e  jns     short loc_1800461A0
0x180046190  jmp     loc_1800463C8
0x180046195  cmp     eax, 0C000007Ch
0x18004619a  jnz     loc_1800463C8
0x1800461a0  lea     r8, [rbp+57h+var_80]; TokenHandle
0x1800461a4  mov     edx, 8; DesiredAccess
0x1800461a9  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800461ad  call    cs:__imp_NtOpenProcessToken
0x1800461b3  mov     ebx, eax
0x1800461b5  test    eax, eax
0x1800461b7  js      loc_1800463C8
0x1800461bd  mov     rcx, [rbp+57h+var_80]; TokenHandle
0x1800461c1  lea     rdx, [rbp+57h+arg_18]; struct _TOKEN_USER **
0x1800461c5  call    ?KerbGetTokenUser@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; KerbGetTokenUser(void *,_TOKEN_USER * *)
0x1800461ca  mov     ebx, eax
0x1800461cc  test    eax, eax
0x1800461ce  js      loc_1800463C4
0x1800461d4  mov     rcx, [rbp+57h+var_80]; TokenHandle
0x1800461d8  lea     r8, [rbp+57h+var_90]; struct _TOKEN_APPCONTAINER_INFORMATION **
0x1800461dc  lea     rdx, [rbp+57h+arg_8]; int *
0x1800461e0  call    ?KerbGetTokenPackage@@YAJPEAXPEAHPEAPEAU_TOKEN_APPCONTAINER_INFORMATION@@@Z; KerbGetTokenPackage(void *,int *,_TOKEN_APPCONTAINER_INFORMATION * *)
0x1800461e5  mov     ebx, eax
0x1800461e7  test    eax, eax
0x1800461e9  js      loc_1800463C0
0x1800461ef  lea     rdx, [rbp+57h+var_78]; struct _TOKEN_USER **
0x1800461f3  mov     rcx, r13; TokenHandle
0x1800461f6  call    ?KerbGetTokenUser@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z; KerbGetTokenUser(void *,_TOKEN_USER * *)
0x1800461fb  mov     ebx, eax
0x1800461fd  test    eax, eax
0x1800461ff  js      loc_1800463BC
0x180046205  mov     dword ptr [rbp+57h+hMem], esi
0x180046208  mov     rsi, [rbp+57h+arg_18]
0x18004620c  mov     rcx, [rsi]; Sid
0x18004620f  call    cs:__imp_RtlLengthSid
0x180046215  mov     rcx, cs:?KerbGlobalAliasAdminsSid@@3PEAXEA; Sid
0x18004621c  mov     ebx, eax
0x18004621e  call    cs:__imp_RtlLengthSid
0x180046224  mov     rcx, cs:?KerbGlobalLocalSystemSid@@3PEAXEA; Sid
0x18004622b  add     ebx, eax
0x18004622d  call    cs:__imp_RtlLengthSid
0x180046233  mov     r12, [rbp+57h+var_78]
0x180046237  add     ebx, eax
0x180046239  mov     rcx, [r12]; Sid
0x18004623d  call    cs:__imp_RtlLengthSid
0x180046243  add     ebx, 28h ; '('
0x180046246  add     ebx, eax
0x180046248  test    rdi, rdi
0x18004624b  jz      short loc_180046283
0x18004624d  mov     rdx, [rsi]; Sid2
0x180046250  mov     rcx, [rdi]; Sid1
0x180046253  call    cs:__imp_RtlEqualSid
0x180046259  test    al, al
0x18004625b  jnz     short loc_180046283
0x18004625d  mov     rdx, [r12]; Sid2
0x180046261  mov     rcx, [rdi]; Sid1
0x180046264  call    cs:__imp_RtlEqualSid
0x18004626a  test    al, al
0x18004626c  jnz     short loc_180046283
0x18004626e  mov     rcx, [rdi]; Sid
0x180046271  call    cs:__imp_RtlLengthSid
0x180046277  add     ebx, 8
0x18004627a  mov     dword ptr [rbp+57h+hMem], 1
0x180046281  add     ebx, eax
0x180046283  mov     r13d, [rbp+57h+arg_8]
0x180046287  mov     r14, [rbp+57h+var_90]
0x18004628b  test    r13d, r13d
0x18004628e  jz      short loc_18004629E
0x180046290  mov     rcx, [r14]; Sid
0x180046293  call    cs:__imp_RtlLengthSid
0x180046299  add     eax, 8
0x18004629c  add     ebx, eax
0x18004629e  mov     edx, ebx; uBytes
0x1800462a0  xor     ecx, ecx; uFlags
0x1800462a2  call    cs:__imp_LocalAlloc
0x1800462a8  mov     r15, rax
0x1800462ab  test    rax, rax
0x1800462ae  jnz     short loc_1800462BA
0x1800462b0  mov     ebx, 0C000009Ah
0x1800462b5  jmp     loc_1800463C8
0x1800462ba  mov     r8d, 2; AclRevision
0x1800462c0  mov     edx, ebx; AclSize
0x1800462c2  mov     rcx, r15; Acl
0x1800462c5  call    cs:__imp_RtlCreateAcl
0x1800462cb  mov     r9, [rsi]; Sid
0x1800462ce  mov     ebx, 2
0x1800462d3  mov     edx, ebx; Revision
0x1800462d5  mov     r8d, 0F01FFh; AccessMask
0x1800462db  mov     rcx, r15; Acl
0x1800462de  call    cs:__imp_RtlAddAccessAllowedAce
0x1800462e4  mov     r9, [r12]; Sid
0x1800462e8  mov     r8d, 0F01FFh; AccessMask
0x1800462ee  mov     edx, ebx; Revision
0x1800462f0  mov     rcx, r15; Acl
0x1800462f3  call    cs:__imp_RtlAddAccessAllowedAce
0x1800462f9  cmp     dword ptr [rbp+57h+hMem], 0
0x1800462fd  jz      short loc_180046313
0x1800462ff  mov     r9, [rdi]; Sid
0x180046302  mov     r8d, 0F01FFh; AccessMask
0x180046308  mov     edx, ebx; Revision
0x18004630a  mov     rcx, r15; Acl
0x18004630d  call    cs:__imp_RtlAddAccessAllowedAce
0x180046313  test    r13d, r13d
0x180046316  jz      short loc_18004632C
0x180046318  mov     r9, [r14]; Sid
0x18004631b  mov     r8d, 0F01FFh; AccessMask
0x180046321  mov     edx, ebx; Revision
0x180046323  mov     rcx, r15; Acl
0x180046326  call    cs:__imp_RtlAddAccessAllowedAce
0x18004632c  mov     r9, cs:?KerbGlobalAliasAdminsSid@@3PEAXEA; Sid
0x180046333  mov     r8d, 0F01FFh; AccessMask
0x180046339  mov     edx, ebx; Revision
0x18004633b  mov     rcx, r15; Acl
0x18004633e  call    cs:__imp_RtlAddAccessAllowedAce
0x180046344  mov     r9, cs:?KerbGlobalLocalSystemSid@@3PEAXEA; Sid
0x18004634b  mov     r8d, 0F01FFh; AccessMask
0x180046351  mov     edx, ebx; Revision
0x180046353  mov     rcx, r15; Acl
0x180046356  call    cs:__imp_RtlAddAccessAllowedAce
0x18004635c  mov     r13d, 1
0x180046362  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180046366  mov     edx, r13d; Revision
0x180046369  call    cs:__imp_RtlCreateSecurityDescriptor
0x18004636f  xor     r9d, r9d; DaclDefaulted
0x180046372  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180046376  mov     r8, r15; Dacl
0x180046379  mov     dl, r13b; DaclPresent
0x18004637c  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180046382  mov     rcx, [rbp+57h+Handle]; Handle
0x180046386  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18004638a  lea     edx, [r13+3]; SecurityInformation
0x18004638e  call    cs:__imp_NtSetSecurityObject
0x180046394  mov     ebx, eax
0x180046396  test    eax, eax
0x180046398  jns     short loc_1800463C8
0x18004639a  lea     r9, aFailedToSetThe; "Failed to set the security info on the "...
0x1800463a1  mov     [rsp+0C0h+var_A0], eax
0x1800463a5  mov     r8d, 908h
0x1800463ab  lea     rdx, aKerbcreatetoke_10; "KerbCreateTokenDacl"
0x1800463b2  mov     ecx, r13d
0x1800463b5  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800463ba  jmp     short loc_1800463C8
0x1800463bc  mov     r12, [rbp+57h+var_78]
0x1800463c0  mov     r14, [rbp+57h+var_90]
0x1800463c4  mov     rsi, [rbp+57h+arg_18]
0x1800463c8  mov     rdx, [rbp+57h+TokenHandle]; Token
0x1800463cc  test    rdx, rdx
0x1800463cf  jz      short loc_1800463E3
0x1800463d1  xor     ecx, ecx; Thread
0x1800463d3  call    cs:__imp_SetThreadToken
0x1800463d9  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x1800463dd  call    cs:__imp_NtClose
0x1800463e3  test    r12, r12
0x1800463e6  jz      short loc_1800463F1
0x1800463e8  mov     rcx, r12; hMem
0x1800463eb  call    cs:__imp_LocalFree
0x1800463f1  test    rsi, rsi
0x1800463f4  jz      short loc_1800463FF
0x1800463f6  mov     rcx, rsi; hMem
0x1800463f9  call    cs:__imp_LocalFree
0x1800463ff  test    rdi, rdi
0x180046402  jz      short loc_18004640D
0x180046404  mov     rcx, rdi; hMem
0x180046407  call    cs:__imp_LocalFree
0x18004640d  test    r14, r14
0x180046410  jz      short loc_18004641B
0x180046412  mov     rcx, r14; hMem
0x180046415  call    cs:__imp_LocalFree
0x18004641b  test    r15, r15
0x18004641e  jz      short loc_180046429
0x180046420  mov     rcx, r15; hMem
0x180046423  call    cs:__imp_LocalFree
0x180046429  mov     rcx, [rbp+57h+var_80]; Handle
0x18004642d  test    rcx, rcx
0x180046430  jz      short loc_180046438
0x180046432  call    cs:__imp_NtClose
0x180046438  mov     eax, ebx
0x18004643a  add     rsp, 88h
0x180046441  pop     r15
0x180046443  pop     r14
0x180046445  pop     r13
0x180046447  pop     r12
0x180046449  pop     rdi
0x18004644a  pop     rsi
0x18004644b  pop     rbx
0x18004644c  pop     rbp
0x18004644d  retn
```
