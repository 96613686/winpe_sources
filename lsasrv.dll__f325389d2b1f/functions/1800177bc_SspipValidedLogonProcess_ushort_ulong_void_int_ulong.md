# SspipValidedLogonProcess(ushort *,ulong,void *,int,ulong *)

- ea: `0x1800177bc`
- end: `0x180017b22`
- name: `?SspipValidedLogonProcess@@YAJPEAGKPEAXHPEAK@Z`
- size: `870`
- prototype: `int(unsigned __int16 *, unsigned int, void *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016fa0`

## callees

- `0x180009330`
- `0x1800177bc`
- `0x1800b86d0`
- `0x1800b9304`
- `0x1800bc2c4`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `ntdll!NtPrivilegeCheck` at `0x18001791d`
- `ntdll!NtPrivilegeCheck` at `0x18001791d`
- `ntdll!NtPrivilegedServiceAuditAlarm` at `0x180017950`
- `ntdll!NtPrivilegedServiceAuditAlarm` at `0x180017950`
- `ntdll!NtQueryInformationToken` at `0x1800178a0`
- `ntdll!NtQueryInformationToken` at `0x1800178da`
- `ntdll!NtQueryInformationToken` at `0x180017b07`
- `ntdll!NtQueryInformationToken` at `0x1800178a0`
- `ntdll!NtQueryInformationToken` at `0x1800178da`
- `ntdll!NtQueryInformationToken` at `0x180017b07`
- `RPCRT4!I_RpcMapWin32Status` at `0x180017a2f`
- `RPCRT4!I_RpcMapWin32Status` at `0x180017a2f`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180017861`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180017861`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditLogonProcessRegistration` at `0x1800179f3`
- `ext-ms-win-security-lsaadtpriv-l1-1-0!LsapAdtAuditLogonProcessRegistration` at `0x1800179f3`

## pseudocode

```c
__int64 __fastcall SspipValidedLogonProcess(unsigned __int16 *a1, char a2, void *a3, __int64 a4, unsigned int *a5)
{
  int v8; // r14d
  RPC_STATUS v9; // eax
  NTSTATUS InformationToken; // ebx
  ULONG *p_Result; // rdi
  NTSTATUS v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned __int64 v21; // rcx
  void *v22; // rsp
  void *v23; // rsp
  ULONG *v24; // rax
  __int64 v25; // [rsp+0h] [rbp-30h] BYREF
  int Result; // [rsp+30h] [rbp+0h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp+4h] BYREF
  ULONG TokenInformationLength[4]; // [rsp+38h] [rbp+8h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+48h] [rbp+18h] BYREF
  _OWORD TokenInformation[3]; // [rsp+60h] [rbp+30h] BYREF
  __int64 v31; // [rsp+90h] [rbp+60h]
  _DWORD RpcCallAttributes[2]; // [rsp+A0h] [rbp+70h] BYREF
  _BYTE v33[44]; // [rsp+A8h] [rbp+78h] BYREF
  int v34; // [rsp+D4h] [rbp+A4h]
  _BYTE v35[88]; // [rsp+110h] [rbp+E0h] BYREF

  LOBYTE(Result) = 0;
  v31 = 0;
  TokenInformationLength[0] = 56;
  ReturnLength = 0;
  memset(&RequiredPrivileges, 0, sizeof(RequiredPrivileges));
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( !a1 || (v8 = 0, !*a1) )
    v8 = 1;
  *a5 = 0;
  memset_0(v33, 0, 0x68u);
  RpcCallAttributes[0] = 2;
  RpcCallAttributes[1] = 96;
  v9 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
  if ( v9 )
    return (unsigned int)I_RpcMapWin32Status(v9);
  if ( v8 )
  {
    if ( (a2 & 2) != 0 )
      *a5 |= 0x40000u;
  }
  else if ( v34 && (a2 & 1) != 0 )
  {
    *a5 |= 0x1000u;
  }
  InformationToken = NtQueryInformationToken(
                       a3,
                       TokenStatistics,
                       TokenInformation,
                       TokenInformationLength[0],
                       TokenInformationLength);
  if ( InformationToken >= 0 )
  {
    p_Result = (ULONG *)v35;
    v12 = NtQueryInformationToken(a3, TokenUser, v35, 0x54u, &ReturnLength);
    InformationToken = v12;
    if ( v12 < 0 )
    {
      if ( v12 != -1073741789 )
        return (unsigned int)InformationToken;
      v18 = ReturnLength;
      p_Result = 0;
      if ( !ReturnLength )
        goto LABEL_48;
      if ( ReturnLength > (unsigned __int64)g_ulMaxStackAllocSize )
        goto LABEL_48;
      v19 = ReturnLength + g_ulAdditionalProbeSize + 8;
      if ( v19 < ReturnLength || !(unsigned int)VerifyStackAvailable(v19, v13, v15, v16) )
        goto LABEL_48;
      v20 = v18 + 23;
      if ( v18 + 23 <= v18 + 8 )
        v20 = 0xFFFFFFFFFFFFFF0LL;
      v21 = v20 & 0xFFFFFFFFFFFFFFF0uLL;
      v22 = alloca(v21);
      v23 = alloca(v21);
      p_Result = (ULONG *)&Result;
      if ( &v25 == (__int64 *)-48LL || (Result = 1801679955, (p_Result = TokenInformationLength) == 0) )
      {
LABEL_48:
        if ( v18 + 8 >= v18 )
        {
          v24 = (ULONG *)((__int64 (*)(void))g_pfnAllocate)();
          p_Result = v24;
          if ( v24 )
          {
            *v24 = 1885431112;
            p_Result = v24 + 2;
          }
        }
      }
      if ( !p_Result )
        return (unsigned int)-1073741670;
      InformationToken = NtQueryInformationToken(a3, TokenUser, p_Result, ReturnLength, &ReturnLength);
      if ( InformationToken < 0 )
        goto LABEL_16;
    }
    if ( (*a5 & 0x1000) == 0 )
    {
      RequiredPrivileges.Privilege[0].Attributes = 0;
      RequiredPrivileges.PrivilegeCount = 1;
      RequiredPrivileges.Control = 1;
      RequiredPrivileges.Privilege[0].Luid = LsapTcbPrivilege;
      InformationToken = NtPrivilegeCheck(a3, &RequiredPrivileges, (PBOOLEAN)&Result);
      if ( !v8 || (_BYTE)Result )
      {
        NtPrivilegedServiceAuditAlarm(&LsapLsaAuName, &LsapRegisterLogonServiceName, a3, &RequiredPrivileges, Result);
        if ( !(_BYTE)Result )
        {
          InformationToken = -1073741727;
LABEL_16:
          if ( p_Result && p_Result != (ULONG *)v35 && *(p_Result - 2) == 1885431112 )
            ((void (*)(void))g_pfnFree)();
          return (unsigned int)InformationToken;
        }
        *a5 |= 2u;
      }
    }
    if ( (unsigned __int8)IsLsapAdtInitParametersArrayPresent(v14, v13, v15) && !v8 && (*a5 & 0x1000) == 0 )
      LsapAdtAuditLogonProcessRegistration(a1, (char *)TokenInformation + 8, p_Result);
    goto LABEL_16;
  }
  return (unsigned int)InformationToken;
}

```

## disassembly

```asm
0x1800177bc  push    rbp
0x1800177be  push    rsi
0x1800177bf  push    rdi
0x1800177c0  push    r12
0x1800177c2  push    r13
0x1800177c4  push    r14
0x1800177c6  push    r15
0x1800177c8  sub     rsp, 170h
0x1800177cf  lea     rbp, [rsp+30h]
0x1800177d4  mov     [rbp+170h+arg_8], rbx
0x1800177db  mov     rax, cs:__security_cookie
0x1800177e2  xor     rax, rbp
0x1800177e5  mov     [rbp+170h+var_38], rax
0x1800177ec  mov     rsi, [rbp+170h+arg_20]
0x1800177f3  xor     r13d, r13d
0x1800177f6  xor     eax, eax
0x1800177f8  mov     byte ptr [rbp+170h+Result], r13b
0x1800177fc  mov     [rbp+170h+RequiredPrivileges.Privilege.Attributes], eax
0x1800177ff  xorps   xmm1, xmm1
0x180017802  mov     [rbp+170h+var_110], rax
0x180017806  xorps   xmm0, xmm0
0x180017809  mov     [rbp+170h+TokenInformationLength], 38h ; '8'
0x180017810  mov     r15, r8
0x180017813  mov     [rbp+170h+var_16C], r13d
0x180017817  mov     ebx, edx
0x180017819  mov     r12, rcx
0x18001781c  movups  xmmword ptr [rbp+170h+RequiredPrivileges.PrivilegeCount], xmm0
0x180017820  movups  [rbp+170h+TokenInformation], xmm1
0x180017824  movups  [rbp+170h+var_130], xmm1
0x180017828  movups  [rbp+170h+var_120], xmm1
0x18001782c  test    rcx, rcx
0x18001782f  jnz     loc_1800179A9
0x180017835  mov     r14d, 1
0x18001783b  xor     edx, edx; Val
0x18001783d  mov     [rsi], r13d
0x180017840  lea     rcx, [rbp+170h+var_F8]; void *
0x180017844  lea     r8d, [rdx+68h]; Size
0x180017848  call    memset_0
0x18001784d  lea     rdx, [rbp+170h+RpcCallAttributes]; RpcCallAttributes
0x180017851  mov     [rbp+170h+RpcCallAttributes], 2
0x180017858  xor     ecx, ecx; ClientBinding
0x18001785a  mov     [rbp+170h+var_FC], 60h ; '`'
0x180017861  call    cs:__imp_RpcServerInqCallAttributesW
0x180017868  nop     dword ptr [rax+rax+00h]
0x18001786d  test    eax, eax
0x18001786f  jnz     loc_180017A2D
0x180017875  test    r14d, r14d
0x180017878  jz      loc_180017A0E
0x18001787e  test    bl, 2
0x180017881  jz      short loc_180017887
0x180017883  bts     dword ptr [rsi], 12h
0x180017887  mov     r9d, [rbp+170h+TokenInformationLength]; TokenInformationLength
0x18001788b  lea     rax, [rbp+170h+TokenInformationLength]
0x18001788f  lea     r8, [rbp+170h+TokenInformation]; TokenInformation
0x180017893  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x180017898  mov     edx, 0Ah; TokenInformationClass
0x18001789d  mov     rcx, r15; TokenHandle
0x1800178a0  call    cs:__imp_NtQueryInformationToken
0x1800178a7  nop     dword ptr [rax+rax+00h]
0x1800178ac  mov     ebx, eax
0x1800178ae  test    eax, eax
0x1800178b0  js      loc_18001797D
0x1800178b6  mov     r9d, 54h ; 'T'; TokenInformationLength
0x1800178bc  lea     rax, [rbp+170h+var_16C]
0x1800178c0  lea     r8, [rbp+170h+var_90]; TokenInformation
0x1800178c7  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x1800178cc  mov     rcx, r15; TokenHandle
0x1800178cf  lea     rdi, [rbp+170h+var_90]
0x1800178d6  lea     edx, [r9-53h]; TokenInformationClass
0x1800178da  call    cs:__imp_NtQueryInformationToken
0x1800178e1  nop     dword ptr [rax+rax+00h]
0x1800178e6  mov     ebx, eax
0x1800178e8  test    eax, eax
0x1800178ea  js      loc_180017A42
0x1800178f0  test    dword ptr [rsi], 1000h
0x1800178f6  jnz     short loc_18001796A
0x1800178f8  mov     eax, 1
0x1800178fd  mov     [rbp+170h+RequiredPrivileges.Privilege.Attributes], r13d
0x180017901  mov     [rbp+170h+RequiredPrivileges.PrivilegeCount], eax
0x180017904  lea     r8, [rbp+170h+Result]; Result
0x180017908  mov     [rbp+170h+RequiredPrivileges.Control], eax
0x18001790b  lea     rdx, [rbp+170h+RequiredPrivileges]; RequiredPrivileges
0x18001790f  mov     rax, cs:?LsapTcbPrivilege@@3U_LUID@@A; _LUID LsapTcbPrivilege
0x180017916  mov     rcx, r15; ClientToken
0x180017919  mov     qword ptr [rbp+170h+RequiredPrivileges.Privilege.Luid.LowPart], rax
0x18001791d  call    cs:__imp_NtPrivilegeCheck
0x180017924  nop     dword ptr [rax+rax+00h]
0x180017929  mov     ebx, eax
0x18001792b  mov     al, byte ptr [rbp+170h+Result]
0x18001792e  test    r14d, r14d
0x180017931  jz      short loc_180017937
0x180017933  test    al, al
0x180017935  jz      short loc_18001796A
0x180017937  lea     r9, [rbp+170h+RequiredPrivileges]; Privileges
0x18001793b  mov     byte ptr [rsp+1A0h+ReturnLength], al; AccessGranted
0x18001793f  mov     r8, r15; ClientToken
0x180017942  lea     rdx, ?LsapRegisterLogonServiceName@@3U_UNICODE_STRING@@A; ServiceName
0x180017949  lea     rcx, ?LsapLsaAuName@@3U_UNICODE_STRING@@A; SubsystemName
0x180017950  call    cs:__imp_NtPrivilegedServiceAuditAlarm
0x180017957  nop     dword ptr [rax+rax+00h]
0x18001795c  mov     al, byte ptr [rbp+170h+Result]
0x18001795f  test    al, al
0x180017961  jz      loc_180017A04
0x180017967  or      dword ptr [rsi], 2
0x18001796a  call    IsLsapAdtInitParametersArrayPresent
0x18001796f  test    al, al
0x180017971  jz      short loc_180017978
0x180017973  test    r14d, r14d
0x180017976  jz      short loc_1800179E1
0x180017978  test    rdi, rdi
0x18001797b  jnz     short loc_1800179BB
0x18001797d  mov     eax, ebx
0x18001797f  mov     rcx, [rbp+170h+var_38]
0x180017986  xor     rcx, rbp; StackCookie
0x180017989  call    __security_check_cookie
0x18001798e  mov     rbx, [rbp+170h+arg_8]
0x180017995  lea     rsp, [rbp+140h]
0x18001799c  pop     r15
0x18001799e  pop     r14
0x1800179a0  pop     r13
0x1800179a2  pop     r12
0x1800179a4  pop     rdi
0x1800179a5  pop     rsi
0x1800179a6  pop     rbp
0x1800179a7  retn
0x1800179a9  mov     r14d, r13d
0x1800179ac  cmp     [rcx], r13w
0x1800179b0  jnz     loc_18001783B
0x1800179b6  jmp     loc_180017835
0x1800179bb  lea     rax, [rbp+170h+var_90]
0x1800179c2  cmp     rdi, rax
0x1800179c5  jz      short loc_18001797D
0x1800179c7  lea     rcx, [rdi-8]
0x1800179cb  cmp     dword ptr [rcx], 70616548h
0x1800179d1  jnz     short loc_18001797D
0x1800179d3  mov     rax, cs:g_pfnFree
0x1800179da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179df  jmp     short loc_18001797D
0x1800179e1  test    dword ptr [rsi], 1000h
0x1800179e7  jnz     short loc_180017978
0x1800179e9  mov     r8, rdi
0x1800179ec  lea     rdx, [rbp+170h+TokenInformation+8]
0x1800179f0  mov     rcx, r12
0x1800179f3  call    cs:__imp_LsapAdtAuditLogonProcessRegistration
0x1800179fa  nop     dword ptr [rax+rax+00h]
0x1800179ff  jmp     loc_180017978
0x180017a04  mov     ebx, 0C0000061h
0x180017a09  jmp     loc_180017978
0x180017a0e  cmp     [rbp+170h+var_CC], r13d
0x180017a15  jz      loc_180017887
0x180017a1b  test    bl, 1
0x180017a1e  jz      loc_180017887
0x180017a24  bts     dword ptr [rsi], 0Ch
0x180017a28  jmp     loc_180017887
0x180017a2d  mov     ecx, eax; Status
0x180017a2f  call    cs:__imp_I_RpcMapWin32Status
0x180017a36  nop     dword ptr [rax+rax+00h]
0x180017a3b  mov     ebx, eax
0x180017a3d  jmp     loc_18001797D
0x180017a42  cmp     eax, 0C0000023h
0x180017a47  jnz     loc_18001797D
0x180017a4d  mov     ebx, [rbp+170h+var_16C]
0x180017a50  mov     rdi, r13
0x180017a53  test    rbx, rbx
0x180017a56  jz      short loc_180017AB9
0x180017a58  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180017a5f  ja      short loc_180017AB9
0x180017a61  mov     rcx, cs:g_ulAdditionalProbeSize
0x180017a68  add     rcx, 8
0x180017a6c  add     rcx, rbx
0x180017a6f  cmp     rcx, rbx
0x180017a72  jb      short loc_180017AB9
0x180017a74  call    VerifyStackAvailable
0x180017a79  test    eax, eax
0x180017a7b  jz      short loc_180017AB9
0x180017a7d  lea     rax, [rbx+8]
0x180017a81  lea     rcx, [rax+0Fh]
0x180017a85  cmp     rcx, rax
0x180017a88  ja      short loc_180017A94
0x180017a8a  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180017a94  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180017a98  mov     rax, rcx
0x180017a9b  call    _alloca_probe
0x180017aa0  sub     rsp, rcx
0x180017aa3  lea     rdi, [rsp+1A0h+Result]
0x180017aa8  test    rdi, rdi
0x180017aab  jz      short loc_180017AB9
0x180017aad  mov     dword ptr [rdi], 6B637453h
0x180017ab3  add     rdi, 8
0x180017ab7  jnz     short loc_180017AE0
0x180017ab9  lea     rcx, [rbx+8]
0x180017abd  cmp     rcx, rbx
0x180017ac0  jb      short loc_180017AE0
0x180017ac2  mov     rax, cs:g_pfnAllocate
0x180017ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ace  mov     rdi, rax
0x180017ad1  test    rax, rax
0x180017ad4  jz      short loc_180017AE0
0x180017ad6  mov     dword ptr [rax], 70616548h
0x180017adc  add     rdi, 8
0x180017ae0  test    rdi, rdi
0x180017ae3  jnz     short loc_180017AEF
0x180017ae5  mov     ebx, 0C000009Ah
0x180017aea  jmp     loc_18001797D
0x180017aef  mov     r9d, [rbp+170h+var_16C]; TokenInformationLength
0x180017af3  lea     rax, [rbp+170h+var_16C]
0x180017af7  mov     r8, rdi; TokenInformation
0x180017afa  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x180017aff  mov     edx, 1; TokenInformationClass
0x180017b04  mov     rcx, r15; TokenHandle
0x180017b07  call    cs:__imp_NtQueryInformationToken
0x180017b0e  nop     dword ptr [rax+rax+00h]
0x180017b13  mov     ebx, eax
0x180017b15  test    eax, eax
0x180017b17  js      loc_180017978
0x180017b1d  jmp     loc_1800178F0
```
