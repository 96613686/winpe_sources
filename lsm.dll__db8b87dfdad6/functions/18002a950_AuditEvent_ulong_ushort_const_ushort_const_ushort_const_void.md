# AuditEvent(ulong,ushort const *,ushort const *,ushort const *,void *)

- ea: `0x18002a950`
- end: `0x18002acf4`
- name: `?AuditEvent@@YAXKPEBG00PEAX@Z`
- size: `932`
- prototype: `void __fastcall(unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002a83c`

## callees

- `0x1800074c0`
- `0x18002a950`
- `0x18004b460`
- `0x180072da8`
- `0x180072dc4`
- `0x180097010`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18002a9f8`
- `ntdll!RtlAdjustPrivilege` at `0x18002aac5`
- `ntdll!RtlAdjustPrivilege` at `0x18002a9f8`
- `ntdll!RtlAdjustPrivilege` at `0x18002aac5`
- `ntdll!NtQueryInformationToken` at `0x18002aaf2`
- `ntdll!NtQueryInformationToken` at `0x18002aaf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002aa98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ac7b`
- `api-ms-win-security-audit-l1-1-0!AuditQuerySystemPolicy` at `0x18002a9bb`
- `api-ms-win-security-audit-l1-1-0!AuditQuerySystemPolicy` at `0x18002a9bb`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x18002a9d9`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x18002a9d9`

## string_xrefs

- `0x18002aa09`: `AuthzInit(): RtlAdjustPrivilege failed. 0#x\n`

## pseudocode

```c
void __fastcall AuditEvent(
        unsigned __int16 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        HANDLE TokenHandle)
{
  char AuditingInformation; // bl
  AuthzWrapper *v10; // rcx
  AuthzWrapper *v11; // rcx
  int v12; // ebx
  DWORD LastError; // eax
  DWORD v14; // eax
  NTSTATUS v15; // eax
  AuthzWrapper *v16; // rbx
  DWORD v17; // eax
  DWORD v18; // eax
  DWORD v19; // eax
  DWORD v20; // eax
  unsigned __int8 OldValue[8]; // [rsp+70h] [rbp-61h] BYREF
  AuthzWrapper *v22; // [rsp+78h] [rbp-59h] BYREF
  struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *v23; // [rsp+80h] [rbp-51h] BYREF
  PAUDIT_POLICY_INFORMATION ppAuditPolicy; // [rsp+88h] [rbp-49h] BYREF
  ULONG ReturnLength; // [rsp+90h] [rbp-41h] BYREF
  _OWORD TokenInformation[3]; // [rsp+98h] [rbp-39h] BYREF
  __int64 v27; // [rsp+C8h] [rbp-9h]

  v27 = 0;
  ReturnLength = 0;
  v22 = 0;
  v23 = 0;
  ppAuditPolicy = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  if ( AuditQuerySystemPolicy(&Audit_Logon_Others, 1u, &ppAuditPolicy) )
  {
    if ( ppAuditPolicy )
    {
      AuditingInformation = ppAuditPolicy->AuditingInformation;
      AuditFree(ppAuditPolicy);
      if ( (AuditingInformation & 1) != 0 )
      {
        OldValue[0] = 0;
        if ( RtlAdjustPrivilege(0x1Du, 1u, 0, OldValue) == -1073741700 )
        {
          _DbgPrintMessage(4, "AuthzInit(): RtlAdjustPrivilege failed. 0#x\n");
LABEL_52:
          if ( v23 )
            AuthzWrapper::AuthziFreeAuditEventType(v11, v23);
          return;
        }
        v23 = 0;
        v12 = AuthzWrapper::Init(v10);
        if ( v12 )
        {
          if ( qword_1800DD758 )
          {
            v12 = qword_1800DD758(0, 2, a1, 4, &v23);
            if ( v12 )
              goto LABEL_15;
          }
          else
          {
            v12 = 0;
          }
          LastError = GetLastError();
          _DbgPrintMessage(4, "AuthzInit(): AuthziInitializeAuditEventType() failed with %d", LastError);
        }
        if ( v23 )
        {
          if ( !(unsigned int)AuthzWrapper::AuthziFreeAuditEventType(v11, v23) )
          {
            v14 = GetLastError();
            _DbgPrintMessage(4, "AuthzInit(): AuthziFreeAuditEventType() failed with %d", v14);
          }
          v23 = 0;
        }
LABEL_15:
        if ( !OldValue[0] )
          RtlAdjustPrivilege(0x1Du, 0, 0, OldValue);
        if ( v12 )
        {
          if ( TokenHandle )
          {
            v15 = NtQueryInformationToken(TokenHandle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
            v16 = v22;
            if ( v15 >= 0 )
              v16 = (AuthzWrapper *)*((_QWORD *)&TokenInformation[0] + 1);
          }
          else
          {
            v16 = v22;
          }
          if ( !a2 || !*a2 )
            a2 = L"Unknown";
          if ( !a3 || !*a3 )
            a3 = L"Unknown";
          if ( !a4 || !*a4 )
            a4 = L"Unknown";
          ppAuditPolicy = 0;
          v22 = 0;
          if ( qword_1800DD708 )
          {
            if ( !v23 )
              return;
            if ( qword_1800DD770 && (unsigned int)qword_1800DD770(&v22, 4) )
            {
              if ( qword_1800DD768
                && (unsigned int)qword_1800DD768(1, qword_1800DD708, 4, v22, 6, v16, 2, a2, 2, a3, 2, a4) )
              {
                if ( qword_1800DD748
                  && (unsigned int)qword_1800DD748(
                                     0,
                                     qword_1800DD708,
                                     v23,
                                     v22,
                                     0,
                                     -1,
                                     &qword_1800A3968,
                                     &qword_1800A3968,
                                     &qword_1800A3968,
                                     &qword_1800A3968,
                                     &ppAuditPolicy) )
                {
                  if ( !qword_1800DD780 || !(unsigned int)qword_1800DD780(0, ppAuditPolicy, 0) )
                  {
                    v17 = GetLastError();
                    _DbgPrintMessage(4, "AuthzReportEventW(): AuthziLogAuditEvent() failed with %d", v17);
                  }
                }
                else
                {
                  v18 = GetLastError();
                  _DbgPrintMessage(4, "AuthzReportEventW(): AuthziInitializeAuditEvent() failed with %d", v18);
                }
              }
              else
              {
                v19 = GetLastError();
                _DbgPrintMessage(4, "AuthzReportEventW(): AuthziInitializeAuditParamsWithRM() failed with %d", v19);
              }
            }
            else
            {
              v20 = GetLastError();
              _DbgPrintMessage(4, "AuthzReportEventW(): AuthzAllocateAuditParams() failed with %d", v20);
            }
            if ( ppAuditPolicy && qword_1800DD750 )
              qword_1800DD750();
            v11 = v22;
            if ( v22 && qword_1800DD778 )
              qword_1800DD778();
          }
        }
        goto LABEL_52;
      }
    }
  }
}

```

## disassembly

```asm
0x18002a950  push    rbp
0x18002a952  push    rbx
0x18002a953  push    rsi
0x18002a954  push    rdi
0x18002a955  push    r12
0x18002a957  push    r13
0x18002a959  push    r14
0x18002a95b  push    r15
0x18002a95d  lea     rbp, [rsp-17h]
0x18002a962  sub     rsp, 0E8h
0x18002a969  mov     rax, cs:__security_cookie
0x18002a970  xor     rax, rsp
0x18002a973  mov     [rbp+4Fh+var_50], rax
0x18002a977  mov     r12, [rbp+4Fh+TokenHandle]
0x18002a97b  xorps   xmm0, xmm0
0x18002a97e  xor     edi, edi
0x18002a980  xor     eax, eax
0x18002a982  mov     r14, r8
0x18002a985  mov     [rbp+4Fh+var_58], rax
0x18002a989  mov     rsi, rdx
0x18002a98c  mov     [rbp+4Fh+var_90], edi
0x18002a98f  mov     r13d, ecx
0x18002a992  mov     [rbp+4Fh+var_A8], rdi
0x18002a996  lea     edx, [rax+1]; dwPolicyCount
0x18002a999  mov     [rbp+4Fh+var_A0], rdi
0x18002a99d  lea     r8, [rbp+4Fh+ppAuditPolicy]; ppAuditPolicy
0x18002a9a1  mov     [rbp+4Fh+ppAuditPolicy], rdi
0x18002a9a5  lea     rcx, Audit_Logon_Others; pSubCategoryGuids
0x18002a9ac  mov     r15, r9
0x18002a9af  movups  [rbp+4Fh+TokenInformation], xmm0
0x18002a9b3  movups  [rbp+4Fh+var_78], xmm0
0x18002a9b7  movups  [rbp+4Fh+var_68], xmm0
0x18002a9bb  call    cs:__imp_AuditQuerySystemPolicy
0x18002a9c1  test    al, al
0x18002a9c3  jz      loc_18002ACD4
0x18002a9c9  mov     rcx, [rbp+4Fh+ppAuditPolicy]; Buffer
0x18002a9cd  test    rcx, rcx
0x18002a9d0  jz      loc_18002ACD4
0x18002a9d6  mov     bl, [rcx+10h]
0x18002a9d9  call    cs:__imp_AuditFree
0x18002a9df  test    bl, 1
0x18002a9e2  jz      loc_18002ACD4
0x18002a9e8  lea     r9, [rbp+4Fh+OldValue]; OldValue
0x18002a9ec  mov     [rbp+4Fh+OldValue], dil
0x18002a9f0  xor     r8d, r8d; ForThread
0x18002a9f3  lea     ecx, [rdi+1Dh]; Privilege
0x18002a9f6  mov     dl, 1; NewValue
0x18002a9f8  call    cs:__imp_RtlAdjustPrivilege
0x18002a9fe  mov     r8d, 0C000007Ch
0x18002aa04  cmp     eax, r8d
0x18002aa07  jnz     short loc_18002AA1D
0x18002aa09  lea     rdx, aAuthzinitRtlad; "AuthzInit(): RtlAdjustPrivilege failed."...
0x18002aa10  lea     ecx, [rdi+4]; int
0x18002aa13  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002aa18  jmp     loc_18002ACC6
0x18002aa1d  mov     [rbp+4Fh+var_A0], rdi
0x18002aa21  call    ?Init@AuthzWrapper@@QEAAHXZ; AuthzWrapper::Init(void)
0x18002aa26  mov     ebx, eax
0x18002aa28  mov     edi, 4
0x18002aa2d  test    eax, eax
0x18002aa2f  jz      short loc_18002AA83
0x18002aa31  mov     rax, cs:qword_1800DD758
0x18002aa38  test    rax, rax
0x18002aa3b  jnz     short loc_18002AA45
0x18002aa3d  xor     r13d, r13d
0x18002aa40  mov     ebx, r13d
0x18002aa43  jmp     short loc_18002AA6A
0x18002aa45  lea     rcx, [rbp+4Fh+var_A0]
0x18002aa49  mov     r9d, edi
0x18002aa4c  mov     [rsp+120h+ReturnLength], rcx
0x18002aa51  movzx   r8d, r13w
0x18002aa55  xor     ecx, ecx
0x18002aa57  mov     edx, 2
0x18002aa5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa61  xor     r13d, r13d
0x18002aa64  mov     ebx, eax
0x18002aa66  test    eax, eax
0x18002aa68  jnz     short loc_18002AAB3
0x18002aa6a  call    cs:__imp_GetLastError
0x18002aa70  lea     rdx, aAuthzinitAuthz_0; "AuthzInit(): AuthziInitializeAuditEvent"...
0x18002aa77  mov     ecx, edi; int
0x18002aa79  mov     r8d, eax
0x18002aa7c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002aa81  jmp     short loc_18002AA86
0x18002aa83  xor     r13d, r13d
0x18002aa86  mov     rdx, [rbp+4Fh+var_A0]; struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *
0x18002aa8a  test    rdx, rdx
0x18002aa8d  jz      short loc_18002AAB3
0x18002aa8f  call    ?AuthziFreeAuditEventType@AuthzWrapper@@QEAAHPEAUAUTHZ_AUDIT_EVENT_TYPE_HANDLE__@@@Z; AuthzWrapper::AuthziFreeAuditEventType(AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *)
0x18002aa94  test    eax, eax
0x18002aa96  jnz     short loc_18002AAAF
0x18002aa98  call    cs:__imp_GetLastError
0x18002aa9e  lea     rdx, aAuthzinitAuthz; "AuthzInit(): AuthziFreeAuditEventType()"...
0x18002aaa5  mov     ecx, edi; int
0x18002aaa7  mov     r8d, eax
0x18002aaaa  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002aaaf  mov     [rbp+4Fh+var_A0], r13
0x18002aab3  cmp     [rbp+4Fh+OldValue], r13b
0x18002aab7  jnz     short loc_18002AACB
0x18002aab9  xor     edx, edx; NewValue
0x18002aabb  lea     r9, [rbp+4Fh+OldValue]; OldValue
0x18002aabf  xor     r8d, r8d; ForThread
0x18002aac2  lea     ecx, [rdx+1Dh]; Privilege
0x18002aac5  call    cs:__imp_RtlAdjustPrivilege
0x18002aacb  test    ebx, ebx
0x18002aacd  jz      loc_18002ACC6
0x18002aad3  test    r12, r12
0x18002aad6  jz      short loc_18002AB05
0x18002aad8  mov     r9d, 38h ; '8'; TokenInformationLength
0x18002aade  lea     rax, [rbp+4Fh+var_90]
0x18002aae2  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x18002aae6  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18002aaeb  mov     rcx, r12; TokenHandle
0x18002aaee  lea     edx, [r9-2Eh]; TokenInformationClass
0x18002aaf2  call    cs:__imp_NtQueryInformationToken
0x18002aaf8  mov     rbx, [rbp+4Fh+var_A8]
0x18002aafc  test    eax, eax
0x18002aafe  cmovns  rbx, qword ptr [rbp+4Fh+TokenInformation+8]
0x18002ab03  jmp     short loc_18002AB09
0x18002ab05  mov     rbx, [rbp+4Fh+var_A8]
0x18002ab09  lea     rax, aUnknown_0; "Unknown"
0x18002ab10  test    rsi, rsi
0x18002ab13  jz      short loc_18002AB1B
0x18002ab15  cmp     [rsi], r13w
0x18002ab19  jnz     short loc_18002AB1E
0x18002ab1b  mov     rsi, rax
0x18002ab1e  test    r14, r14
0x18002ab21  jz      short loc_18002AB29
0x18002ab23  cmp     [r14], r13w
0x18002ab27  jnz     short loc_18002AB2C
0x18002ab29  mov     r14, rax
0x18002ab2c  test    r15, r15
0x18002ab2f  jz      short loc_18002AB37
0x18002ab31  cmp     [r15], r13w
0x18002ab35  jnz     short loc_18002AB3A
0x18002ab37  mov     r15, rax
0x18002ab3a  cmp     cs:qword_1800DD708, r13
0x18002ab41  mov     [rbp+4Fh+ppAuditPolicy], r13
0x18002ab45  mov     [rbp+4Fh+var_A8], r13
0x18002ab49  jz      loc_18002ACC6
0x18002ab4f  cmp     [rbp+4Fh+var_A0], r13
0x18002ab53  jz      loc_18002ACD4
0x18002ab59  mov     rax, cs:qword_1800DD770
0x18002ab60  test    rax, rax
0x18002ab63  jz      loc_18002AC7B
0x18002ab69  mov     edx, edi
0x18002ab6b  lea     rcx, [rbp+4Fh+var_A8]
0x18002ab6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ab74  test    eax, eax
0x18002ab76  jz      loc_18002AC7B
0x18002ab7c  mov     rax, cs:qword_1800DD768
0x18002ab83  test    rax, rax
0x18002ab86  jz      loc_18002AC6C
0x18002ab8c  mov     r9, [rbp+4Fh+var_A8]
0x18002ab90  mov     ecx, 2
0x18002ab95  mov     rdx, cs:qword_1800DD708
0x18002ab9c  mov     r8d, edi
0x18002ab9f  mov     [rsp+120h+var_C8], r15
0x18002aba4  mov     dword ptr [rsp+120h+var_D0], ecx
0x18002aba8  mov     [rsp+120h+var_D8], r14
0x18002abad  mov     dword ptr [rsp+120h+var_E0], ecx
0x18002abb1  mov     [rsp+120h+var_E8], rsi
0x18002abb6  mov     dword ptr [rsp+120h+var_F0], ecx
0x18002abba  mov     ecx, 1
0x18002abbf  mov     [rsp+120h+var_F8], rbx
0x18002abc4  mov     dword ptr [rsp+120h+ReturnLength], 6
0x18002abcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002abd1  test    eax, eax
0x18002abd3  jz      loc_18002AC6C
0x18002abd9  mov     rax, cs:qword_1800DD748
0x18002abe0  test    rax, rax
0x18002abe3  jz      short loc_18002AC5D
0x18002abe5  mov     r9, [rbp+4Fh+var_A8]
0x18002abe9  lea     rcx, [rbp+4Fh+ppAuditPolicy]
0x18002abed  mov     r8, [rbp+4Fh+var_A0]
0x18002abf1  mov     rdx, cs:qword_1800DD708
0x18002abf8  mov     [rsp+120h+var_D0], rcx
0x18002abfd  lea     rcx, qword_1800A3968
0x18002ac04  mov     [rsp+120h+var_D8], rcx
0x18002ac09  mov     [rsp+120h+var_E0], rcx
0x18002ac0e  mov     [rsp+120h+var_E8], rcx
0x18002ac13  mov     [rsp+120h+var_F0], rcx
0x18002ac18  xor     ecx, ecx
0x18002ac1a  mov     dword ptr [rsp+120h+var_F8], 0FFFFFFFFh
0x18002ac22  mov     [rsp+120h+ReturnLength], r13
0x18002ac27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac2c  test    eax, eax
0x18002ac2e  jz      short loc_18002AC5D
0x18002ac30  mov     rax, cs:qword_1800DD780
0x18002ac37  test    rax, rax
0x18002ac3a  jz      short loc_18002AC4E
0x18002ac3c  mov     rdx, [rbp+4Fh+ppAuditPolicy]
0x18002ac40  xor     r8d, r8d
0x18002ac43  xor     ecx, ecx
0x18002ac45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac4a  test    eax, eax
0x18002ac4c  jnz     short loc_18002AC92
0x18002ac4e  call    cs:__imp_GetLastError
0x18002ac54  lea     rdx, aAuthzreporteve_2; "AuthzReportEventW(): AuthziLogAuditEven"...
0x18002ac5b  jmp     short loc_18002AC88
0x18002ac5d  call    cs:__imp_GetLastError
0x18002ac63  lea     rdx, aAuthzreporteve; "AuthzReportEventW(): AuthziInitializeAu"...
0x18002ac6a  jmp     short loc_18002AC88
0x18002ac6c  call    cs:__imp_GetLastError
0x18002ac72  lea     rdx, aAuthzreporteve_0; "AuthzReportEventW(): AuthziInitializeAu"...
0x18002ac79  jmp     short loc_18002AC88
0x18002ac7b  call    cs:__imp_GetLastError
0x18002ac81  lea     rdx, aAuthzreporteve_1; "AuthzReportEventW(): AuthzAllocateAudit"...
0x18002ac88  mov     r8d, eax
0x18002ac8b  mov     ecx, edi; int
0x18002ac8d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ac92  mov     rcx, [rbp+4Fh+ppAuditPolicy]
0x18002ac96  test    rcx, rcx
0x18002ac99  jz      short loc_18002ACAC
0x18002ac9b  mov     rax, cs:qword_1800DD750
0x18002aca2  test    rax, rax
0x18002aca5  jz      short loc_18002ACAC
0x18002aca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acac  mov     rcx, [rbp+4Fh+var_A8]
0x18002acb0  test    rcx, rcx
0x18002acb3  jz      short loc_18002ACC6
0x18002acb5  mov     rax, cs:qword_1800DD778
0x18002acbc  test    rax, rax
0x18002acbf  jz      short loc_18002ACC6
0x18002acc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acc6  mov     rdx, [rbp+4Fh+var_A0]; struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *
0x18002acca  test    rdx, rdx
0x18002accd  jz      short loc_18002ACD4
0x18002accf  call    ?AuthziFreeAuditEventType@AuthzWrapper@@QEAAHPEAUAUTHZ_AUDIT_EVENT_TYPE_HANDLE__@@@Z; AuthzWrapper::AuthziFreeAuditEventType(AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *)
0x18002acd4  mov     rcx, [rbp+4Fh+var_50]
0x18002acd8  xor     rcx, rsp; StackCookie
0x18002acdb  call    __security_check_cookie
0x18002ace0  add     rsp, 0E8h
0x18002ace7  pop     r15
0x18002ace9  pop     r14
0x18002aceb  pop     r13
0x18002aced  pop     r12
0x18002acef  pop     rdi
0x18002acf0  pop     rsi
0x18002acf1  pop     rbx
0x18002acf2  pop     rbp
0x18002acf3  retn
```
