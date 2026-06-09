# CheckAccessForPolicyGeneration

- ea: `0x1800b6478`
- end: `0x1800b6900`
- name: `CheckAccessForPolicyGeneration`
- size: `1160`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800709d4`

## callees

- `0x18000a504`
- `0x18000a52c`
- `0x18002c690`
- `0x18003d8d0`
- `0x180072a08`
- `0x18007d320`
- `0x1800b6478`
- `0x1800b6908`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b6874`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b64f3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b6513`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b6591`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b64f3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b6513`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800b6591`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b6615`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b6615`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x1800b686a`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x1800b686a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800b671a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800b671a`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800b676f`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x1800b676f`

## string_xrefs

- `0x1800b6562`: `CheckAccessForPolicyGeneration: SOM for account is %s`
- `0x1800b65b9`: `CheckAccessForPolicyGeneration: GetDomain failed with error %d`
- `0x1800b65d4`: `CheckAccessForPolicyGeneration: Som resides in domain %s`
- `0x1800b6631`: `CheckAccessForPolicyGeneration:  AllocMem failed with %d.`
- `0x1800b66ec`: `CheckAccessForPolicyGeneration: getting SD off %s`
- `0x1800b672a`: `CheckAccessForPolicyGeneration: DuplicateTokenEx failed, 0x%X`
- `0x1800b687c`: `CheckAccessForPolicyGeneration: AccessCheckByType failed, 0x%X`
- `0x1800b6885`: `CheckAccessForPolicyGeneration: GetNamedSecurityInfo failed, 0x%X`

## pseudocode

```c
__int64 __fastcall CheckAccessForPolicyGeneration(
        void *a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        LPBOOL AccessStatus)
{
  const WCHAR *v5; // rdi
  WCHAR v6; // ax
  HANDLE v7; // r13
  unsigned int Domain; // eax
  unsigned __int16 *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // r14d
  HLOCAL v13; // rax
  DWORD LastError; // eax
  int v16; // eax
  unsigned __int16 v17; // si
  int v18; // eax
  int v19; // eax
  int v20; // eax
  DWORD NamedSecurityInfoW; // eax
  GUID *v22; // rax
  DWORD GrantedAccess; // [rsp+60h] [rbp-A0h] BYREF
  void *phNewToken; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v25; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hExistingToken; // [rsp+78h] [rbp-88h] BYREF
  DWORD PrivilegeSetLength; // [rsp+80h] [rbp-80h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_TYPE_LIST ObjectTypeList; // [rsp+90h] [rbp-70h] BYREF
  int v30; // [rsp+A0h] [rbp-60h]
  _DWORD *v31; // [rsp+A8h] [rbp-58h]
  _DWORD v32[4]; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD v33[4]; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v34[4]; // [rsp+D0h] [rbp-30h] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+E0h] [rbp-20h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+F0h] [rbp-10h] BYREF

  v5 = a2;
  hExistingToken = a1;
  phNewToken = 0;
  *AccessStatus = 0;
  if ( !*a2 )
    goto LABEL_35;
  do
  {
    if ( CompareStringW(0x7Fu, 1u, v5, 3, L"OU=", 3) == 2 || CompareStringW(0x7Fu, 1u, v5, 3, L"DC=", 3) == 2 )
      break;
    while ( *v5 && *v5 != 44 )
      ++v5;
    v6 = *v5;
    if ( *v5 == 44 )
      v6 = *++v5;
  }
  while ( v6 );
  v7 = hExistingToken;
  if ( *v5 )
  {
    CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 4u, L"CheckAccessForPolicyGeneration: SOM for account is %s", v5);
    v25 = 0;
    GrantedAccess = CompareStringW(0x7Fu, 1u, v5, 3, L"DC=", 3);
    Domain = GetDomain(v5);
    LODWORD(v9) = Domain;
    if ( Domain )
    {
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgRsop,
        2u,
        L"CheckAccessForPolicyGeneration: GetDomain failed with error %d",
        Domain);
LABEL_20:
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v25);
      XHandle::~XHandle(&phNewToken);
      return (unsigned int)v9;
    }
    CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 4u, L"CheckAccessForPolicyGeneration: Som resides in domain %s", v25);
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( v25[v11] );
    do
      ++v10;
    while ( v5[v10] );
    v12 = v11 + v10 + 12;
    v13 = LocalAlloc(0x40u, 2LL * v12);
    hExistingToken = v13;
    v9 = (unsigned __int16 *)v13;
    if ( !v13 )
    {
      LastError = GetLastError();
      CDebugWrapper::Msg(
        (CDebugWrapper *)dbgRsop,
        2u,
        L"CheckAccessForPolicyGeneration:  AllocMem failed with %d.",
        LastError);
      LODWORD(v9) = GetLastError();
LABEL_19:
      XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&hExistingToken);
      goto LABEL_20;
    }
    v16 = StringCchCopyW((unsigned __int16 *)v13, v12, L"LDAP://");
    v17 = v16;
    if ( v16 >= 0 )
    {
      v18 = StringCchCatW(v9, v12, v25);
      v17 = v18;
      if ( v18 >= 0 )
      {
        v19 = StringCchCatW(v9, v12, L"/");
        v17 = v19;
        if ( v19 >= 0 )
        {
          v20 = StringCchCatW(v9, v12, v5);
          v17 = v20;
          if ( v20 >= 0 )
          {
            CDebugWrapper::Msg((CDebugWrapper *)dbgRsop, 4u, L"CheckAccessForPolicyGeneration: getting SD off %s", v9);
            if ( DuplicateTokenEx(v7, 0xCu, 0, SecurityImpersonation, TokenImpersonation, &phNewToken) )
            {
              pSecurityDescriptor = 0;
              NamedSecurityInfoW = GetNamedSecurityInfoW(v9, SE_DS_OBJECT_ALL, 7u, 0, 0, 0, 0, &pSecurityDescriptor);
              LODWORD(v9) = NamedSecurityInfoW;
              if ( NamedSecurityInfoW )
              {
                CDebugWrapper::Msg(
                  (CDebugWrapper *)dbgRsop,
                  2u,
                  L"CheckAccessForPolicyGeneration: GetNamedSecurityInfo failed, 0x%X",
                  NamedSecurityInfoW);
              }
              else
              {
                v22 = (GUID *)v32;
                if ( GrantedAccess != 2 )
                  v22 = (GUID *)v33;
                ObjectTypeList.ObjectType = v22;
                v33[0] = -1080657243;
                v31 = v34;
                v33[1] = 298847718;
                v33[2] = -1442806366;
                v33[3] = -498520064;
                v32[0] = 421091931;
                v32[1] = 298872224;
                v32[2] = -1073687633;
                v32[3] = -919545521;
                v34[0] = -1213090850;
                v34[1] = 1111665417;
                v34[2] = -2137444194;
                v34[3] = -148712475;
                *(_DWORD *)&ObjectTypeList.Level = 0;
                v30 = 1;
                GenericMapping.GenericRead = 131220;
                GenericMapping.GenericWrite = 131112;
                GenericMapping.GenericExecute = 131076;
                GenericMapping.GenericAll = 983551;
                PrivilegeSetLength = 64;
                GrantedAccess = 0;
                if ( !AccessCheckByType(
                        pSecurityDescriptor,
                        0,
                        phNewToken,
                        0x100u,
                        &ObjectTypeList,
                        2u,
                        &GenericMapping,
                        &PrivilegeSet,
                        &PrivilegeSetLength,
                        &GrantedAccess,
                        AccessStatus) )
                {
                  v9 = (unsigned __int16 *)GetLastError();
                  CDebugWrapper::Msg(
                    (CDebugWrapper *)dbgRsop,
                    2u,
                    L"CheckAccessForPolicyGeneration: AccessCheckByType failed, 0x%X",
                    v9);
                }
              }
              XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&pSecurityDescriptor);
            }
            else
            {
              v9 = (unsigned __int16 *)GetLastError();
              CDebugWrapper::Msg(
                (CDebugWrapper *)dbgRsop,
                2u,
                L"CheckAccessForPolicyGeneration: DuplicateTokenEx failed, 0x%X",
                v9);
            }
            goto LABEL_19;
          }
        }
      }
    }
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&hExistingToken);
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>((void **)&v25);
    XHandle::~XHandle(&phNewToken);
    return v17;
  }
  else
  {
LABEL_35:
    XHandle::~XHandle(&phNewToken);
    return 87;
  }
}

```

## disassembly

```asm
0x1800b6478  mov     [rsp-8+arg_10], rbx
0x1800b647d  push    rbp
0x1800b647e  push    rsi
0x1800b647f  push    rdi
0x1800b6480  push    r12
0x1800b6482  push    r13
0x1800b6484  push    r14
0x1800b6486  push    r15
0x1800b6488  lea     rbp, [rsp-40h]
0x1800b648d  sub     rsp, 140h
0x1800b6494  mov     rax, cs:__security_cookie
0x1800b649b  xor     rax, rsp
0x1800b649e  mov     [rbp+70h+var_40], rax
0x1800b64a2  mov     r12, [rbp+70h+arg_20]
0x1800b64a9  xor     esi, esi
0x1800b64ab  mov     rdi, rdx
0x1800b64ae  mov     [rsp+170h+hExistingToken], rcx
0x1800b64b3  mov     [rsp+170h+phNewToken], rsi
0x1800b64b8  mov     [r12], esi
0x1800b64bc  cmp     [rdx], si
0x1800b64bf  jz      loc_1800B68CA
0x1800b64c5  lea     ebx, [rsi+3]
0x1800b64c8  lea     r13d, [rsi+1]
0x1800b64cc  lea     r15d, [rsi+7Fh]
0x1800b64d0  lea     r14, aDc; "DC="
0x1800b64d7  lea     rax, aOu; "OU="
0x1800b64de  mov     [rsp+170h+cchCount2], ebx; cchCount2
0x1800b64e2  mov     r9d, ebx; cchCount1
0x1800b64e5  mov     [rsp+170h+lpString2], rax; lpString2
0x1800b64ea  mov     r8, rdi; lpString1
0x1800b64ed  mov     edx, r13d; dwCmpFlags
0x1800b64f0  mov     ecx, r15d; Locale
0x1800b64f3  call    cs:__imp_CompareStringW
0x1800b64f9  cmp     eax, 2
0x1800b64fc  jz      short loc_1800B6547
0x1800b64fe  mov     [rsp+170h+cchCount2], ebx; cchCount2
0x1800b6502  mov     r9d, ebx; cchCount1
0x1800b6505  mov     r8, rdi; lpString1
0x1800b6508  mov     [rsp+170h+lpString2], r14; lpString2
0x1800b650d  mov     edx, r13d; dwCmpFlags
0x1800b6510  mov     ecx, r15d; Locale
0x1800b6513  call    cs:__imp_CompareStringW
0x1800b6519  cmp     eax, 2
0x1800b651c  jz      short loc_1800B6547
0x1800b651e  jmp     short loc_1800B652A
0x1800b6520  cmp     ax, 2Ch ; ','
0x1800b6524  jz      short loc_1800B6532
0x1800b6526  add     rdi, 2
0x1800b652a  movzx   eax, word ptr [rdi]
0x1800b652d  test    ax, ax
0x1800b6530  jnz     short loc_1800B6520
0x1800b6532  movzx   eax, word ptr [rdi]
0x1800b6535  cmp     ax, 2Ch ; ','
0x1800b6539  jnz     short loc_1800B6542
0x1800b653b  add     rdi, 2
0x1800b653f  movzx   eax, word ptr [rdi]
0x1800b6542  test    ax, ax
0x1800b6545  jnz     short loc_1800B64D7
0x1800b6547  mov     r13, [rsp+170h+hExistingToken]
0x1800b654c  cmp     [rdi], si
0x1800b654f  jz      loc_1800B68CA
0x1800b6555  lea     r14, ?dbgRsop@@3VCDebugWrapper@@A; CDebugWrapper dbgRsop
0x1800b655c  mov     r9, rdi
0x1800b655f  mov     rcx, r14; this
0x1800b6562  lea     r8, aCheckaccessfor_1; "CheckAccessForPolicyGeneration: SOM for"...
0x1800b6569  mov     edx, 4; unsigned int
0x1800b656e  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800b6573  lea     rax, aDc; "DC="
0x1800b657a  mov     [rsp+170h+cchCount2], ebx; cchCount2
0x1800b657e  mov     r9d, ebx; cchCount1
0x1800b6581  mov     [rsp+170h+lpString2], rax; lpString2
0x1800b6586  mov     r8, rdi; lpString1
0x1800b6589  mov     edx, 1; dwCmpFlags
0x1800b658e  mov     ecx, r15d; Locale
0x1800b6591  call    cs:__imp_CompareStringW
0x1800b6597  lea     rdx, [rsp+170h+var_100]
0x1800b659c  mov     [rsp+170h+var_100], rsi
0x1800b65a1  mov     rcx, rdi; lpString1
0x1800b65a4  mov     [rsp+170h+var_110], eax
0x1800b65a8  call    GetDomain
0x1800b65ad  mov     ebx, eax
0x1800b65af  mov     rcx, r14; this
0x1800b65b2  test    eax, eax
0x1800b65b4  jz      short loc_1800B65CF
0x1800b65b6  mov     r9d, eax
0x1800b65b9  lea     r8, aCheckaccessfor_5; "CheckAccessForPolicyGeneration: GetDoma"...
0x1800b65c0  mov     edx, 2; unsigned int
0x1800b65c5  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800b65ca  jmp     loc_1800B6659
0x1800b65cf  mov     r15, [rsp+170h+var_100]
0x1800b65d4  lea     r8, aCheckaccessfor_2; "CheckAccessForPolicyGeneration: Som res"...
0x1800b65db  mov     r9, r15
0x1800b65de  mov     edx, 4; unsigned int
0x1800b65e3  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800b65e8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b65ec  mov     rcx, rax
0x1800b65ef  inc     rcx
0x1800b65f2  cmp     [r15+rcx*2], si
0x1800b65f7  jnz     short loc_1800B65EF
0x1800b65f9  inc     rax
0x1800b65fc  cmp     [rdi+rax*2], si
0x1800b6600  jnz     short loc_1800B65F9
0x1800b6602  lea     r14, [rax+0Ch]
0x1800b6606  add     r14, rcx
0x1800b6609  mov     ecx, 40h ; '@'; uFlags
0x1800b660e  mov     r14d, r14d
0x1800b6611  lea     rdx, [r14+r14]; uBytes
0x1800b6615  call    cs:__imp_LocalAlloc
0x1800b661b  mov     [rsp+170h+hExistingToken], rax
0x1800b6620  mov     rbx, rax
0x1800b6623  test    rax, rax
0x1800b6626  jnz     short loc_1800B6674
0x1800b6628  call    cs:__imp_GetLastError
0x1800b662e  mov     r9d, eax
0x1800b6631  lea     r8, aCheckaccessfor_6; "CheckAccessForPolicyGeneration:  AllocM"...
0x1800b6638  lea     edx, [rbx+2]; unsigned int
0x1800b663b  lea     rcx, ?dbgRsop@@3VCDebugWrapper@@A; this
0x1800b6642  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800b6647  call    cs:__imp_GetLastError
0x1800b664d  mov     ebx, eax
0x1800b664f  lea     rcx, [rsp+170h+hExistingToken]
0x1800b6654  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b6659  lea     rcx, [rsp+170h+var_100]
0x1800b665e  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b6663  lea     rcx, [rsp+170h+phNewToken]; this
0x1800b6668  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x1800b666d  mov     eax, ebx
0x1800b666f  jmp     loc_1800B68D9
0x1800b6674  lea     r8, aLdap; "LDAP://"
0x1800b667b  mov     rdx, r14; unsigned __int64
0x1800b667e  mov     rcx, rbx; unsigned __int16 *
0x1800b6681  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b6686  mov     esi, eax
0x1800b6688  test    eax, eax
0x1800b668a  js      loc_1800B68A7
0x1800b6690  mov     r8, r15; unsigned __int16 *
0x1800b6693  mov     rdx, r14; unsigned __int64
0x1800b6696  mov     rcx, rbx; unsigned __int16 *
0x1800b6699  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b669e  xor     r15d, r15d
0x1800b66a1  mov     esi, eax
0x1800b66a3  test    eax, eax
0x1800b66a5  js      loc_1800B68A7
0x1800b66ab  lea     r8, asc_1800C8F0C; "/"
0x1800b66b2  mov     rdx, r14; unsigned __int64
0x1800b66b5  mov     rcx, rbx; unsigned __int16 *
0x1800b66b8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b66bd  mov     esi, eax
0x1800b66bf  test    eax, eax
0x1800b66c1  js      loc_1800B68A7
0x1800b66c7  mov     r8, rdi; unsigned __int16 *
0x1800b66ca  mov     rdx, r14; unsigned __int64
0x1800b66cd  mov     rcx, rbx; unsigned __int16 *
0x1800b66d0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b66d5  mov     esi, eax
0x1800b66d7  test    eax, eax
0x1800b66d9  js      loc_1800B68A7
0x1800b66df  lea     rsi, ?dbgRsop@@3VCDebugWrapper@@A; CDebugWrapper dbgRsop
0x1800b66e6  mov     r9, rbx
0x1800b66e9  mov     rcx, rsi; this
0x1800b66ec  lea     r8, aCheckaccessfor_4; "CheckAccessForPolicyGeneration: getting"...
0x1800b66f3  lea     edx, [r15+4]; unsigned int
0x1800b66f7  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800b66fc  lea     edi, [r15+2]
0x1800b6700  xor     r8d, r8d; lpTokenAttributes
0x1800b6703  lea     rax, [rsp+170h+phNewToken]
0x1800b6708  mov     r9d, edi; ImpersonationLevel
0x1800b670b  mov     qword ptr [rsp+170h+cchCount2], rax; phNewToken
0x1800b6710  lea     edx, [rdi+0Ah]; dwDesiredAccess
0x1800b6713  mov     rcx, r13; hExistingToken
0x1800b6716  mov     dword ptr [rsp+170h+lpString2], edi; TokenType
0x1800b671a  call    cs:__imp_DuplicateTokenEx
0x1800b6720  test    eax, eax
0x1800b6722  jnz     short loc_1800B6745
0x1800b6724  call    cs:__imp_GetLastError
0x1800b672a  lea     r8, aCheckaccessfor_3; "CheckAccessForPolicyGeneration: Duplica"...
0x1800b6731  mov     edx, edi; unsigned int
0x1800b6733  mov     r9d, eax
0x1800b6736  mov     rcx, rsi; this
0x1800b6739  mov     ebx, eax
0x1800b673b  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800b6740  jmp     loc_1800B664F
0x1800b6745  xor     r9d, r9d; ppsidOwner
0x1800b6748  mov     [rbp+70h+pSecurityDescriptor], r15
0x1800b674c  lea     rax, [rbp+70h+pSecurityDescriptor]
0x1800b6750  mov     rcx, rbx; pObjectName
0x1800b6753  mov     [rsp+170h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800b6758  mov     [rsp+170h+ppSacl], r15; ppSacl
0x1800b675d  lea     edx, [r9+9]; ObjectType
0x1800b6761  mov     qword ptr [rsp+170h+cchCount2], r15; ppDacl
0x1800b6766  lea     r8d, [r9+7]; SecurityInfo
0x1800b676a  mov     [rsp+170h+lpString2], r15; ppsidGroup
0x1800b676f  call    cs:__imp_GetNamedSecurityInfoW
0x1800b6775  mov     ebx, eax
0x1800b6777  test    eax, eax
0x1800b6779  jnz     loc_1800B6885
0x1800b677f  cmp     [rsp+170h+var_110], edi
0x1800b6783  lea     rcx, [rbp+70h+var_B0]
0x1800b6787  mov     r8, [rsp+170h+phNewToken]; ClientToken
0x1800b678c  lea     rax, [rbp+70h+var_C0]
0x1800b6790  cmovnz  rax, rcx
0x1800b6794  mov     [rsp+170h+AccessStatus], r12; AccessStatus
0x1800b6799  mov     rcx, [rbp+70h+pSecurityDescriptor]; pSecurityDescriptor
0x1800b679d  mov     r9d, 100h; DesiredAccess
0x1800b67a3  mov     [rbp+70h+ObjectTypeList.ObjectType], rax
0x1800b67a7  xor     edx, edx; PrincipalSelfSid
0x1800b67a9  lea     rax, [rbp+70h+var_A0]
0x1800b67ad  mov     [rbp+70h+var_B0], 0BF967AA5h
0x1800b67b4  mov     [rbp+70h+var_C8], rax
0x1800b67b8  lea     rax, [rsp+170h+var_110]
0x1800b67bd  mov     [rsp+170h+GrantedAccess], rax; GrantedAccess
0x1800b67c2  lea     rax, [rbp+70h+var_F0]
0x1800b67c6  mov     [rsp+170h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800b67cb  lea     rax, [rbp+70h+PrivilegeSet]
0x1800b67cf  mov     [rsp+170h+ppSecurityDescriptor], rax; PrivilegeSet
0x1800b67d4  lea     rax, [rbp+70h+GenericMapping]
0x1800b67d8  mov     [rsp+170h+ppSacl], rax; GenericMapping
0x1800b67dd  lea     rax, [rbp+70h+ObjectTypeList]
0x1800b67e1  mov     [rsp+170h+cchCount2], edi; ObjectTypeListLength
0x1800b67e5  mov     [rsp+170h+lpString2], rax; ObjectTypeList
0x1800b67ea  mov     [rbp+70h+var_AC], 11D00DE6h
0x1800b67f1  mov     [rbp+70h+var_A8], 0AA0085A2h
0x1800b67f8  mov     [rbp+70h+var_A4], 0E2493000h
0x1800b67ff  mov     [rbp+70h+var_C0], 19195A5Bh
0x1800b6806  mov     [rbp+70h+var_BC], 11D06DA0h
0x1800b680d  mov     [rbp+70h+var_B8], 0C000D3AFh
0x1800b6814  mov     [rbp+70h+var_B4], 0C930D94Fh
0x1800b681b  mov     [rbp+70h+var_A0], 0B7B1B3DEh
0x1800b6822  mov     [rbp+70h+var_9C], 4242AB09h
0x1800b6829  mov     [rbp+70h+var_98], 8099309Eh
0x1800b6830  mov     [rbp+70h+var_94], 0F722D3E5h
0x1800b6837  mov     dword ptr [rbp+70h+ObjectTypeList.Level], r15d
0x1800b683b  mov     [rbp+70h+var_D0], 1
0x1800b6842  mov     [rbp+70h+GenericMapping.GenericRead], 20094h
0x1800b6849  mov     [rbp+70h+GenericMapping.GenericWrite], 20028h
0x1800b6850  mov     [rbp+70h+GenericMapping.GenericExecute], 20004h
0x1800b6857  mov     [rbp+70h+GenericMapping.GenericAll], 0F01FFh
0x1800b685e  mov     [rbp+70h+var_F0], 40h ; '@'
0x1800b6865  mov     [rsp+170h+var_110], r15d
0x1800b686a  call    cs:__imp_AccessCheckByType
0x1800b6870  test    eax, eax
0x1800b6872  jnz     short loc_1800B6899
0x1800b6874  call    cs:__imp_GetLastError
0x1800b687a  mov     ebx, eax
0x1800b687c  lea     r8, aCheckaccessfor; "CheckAccessForPolicyGeneration: AccessC"...
0x1800b6883  jmp     short loc_1800B688C
0x1800b6885  lea     r8, aCheckaccessfor_0; "CheckAccessForPolicyGeneration: GetName"...
0x1800b688c  mov     r9d, eax
0x1800b688f  mov     edx, edi; unsigned int
0x1800b6891  mov     rcx, rsi; this
0x1800b6894  call    ?Msg@CDebugWrapper@@QEAAXKPEBGZZ; CDebugWrapper::Msg(ulong,ushort const *,...)
0x1800b6899  lea     rcx, [rbp+70h+pSecurityDescriptor]
0x1800b689d  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b68a2  jmp     loc_1800B664F
0x1800b68a7  lea     rcx, [rsp+170h+hExistingToken]
0x1800b68ac  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b68b1  lea     rcx, [rsp+170h+var_100]
0x1800b68b6  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800b68bb  lea     rcx, [rsp+170h+phNewToken]; this
0x1800b68c0  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x1800b68c5  movzx   eax, si
0x1800b68c8  jmp     short loc_1800B68D9
0x1800b68ca  lea     rcx, [rsp+170h+phNewToken]; this
0x1800b68cf  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x1800b68d4  mov     eax, 57h ; 'W'
0x1800b68d9  mov     rcx, [rbp+70h+var_40]
0x1800b68dd  xor     rcx, rsp; StackCookie
0x1800b68e0  call    __security_check_cookie
0x1800b68e5  mov     rbx, [rsp+170h+arg_10]
0x1800b68ed  add     rsp, 140h
0x1800b68f4  pop     r15
0x1800b68f6  pop     r14
0x1800b68f8  pop     r13
0x1800b68fa  pop     r12
0x1800b68fc  pop     rdi
0x1800b68fd  pop     rsi
0x1800b68fe  pop     rbp
0x1800b68ff  retn
```
