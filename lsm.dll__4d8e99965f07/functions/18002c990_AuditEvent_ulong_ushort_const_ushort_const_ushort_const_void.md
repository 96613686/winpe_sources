# AuditEvent(ulong,ushort const *,ushort const *,ushort const *,void *)

- ea: `0x18002c990`
- end: `0x18002cd77`
- name: `?AuditEvent@@YAXKPEBG00PEAX@Z`
- size: `999`
- prototype: `void __fastcall(unsigned int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c878`

## callees

- `0x1800077a0`
- `0x18002c990`
- `0x18004e850`
- `0x180076f28`
- `0x180076f44`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18002ca44`
- `ntdll!RtlAdjustPrivilege` at `0x18002cb23`
- `ntdll!RtlAdjustPrivilege` at `0x18002ca44`
- `ntdll!RtlAdjustPrivilege` at `0x18002cb23`
- `ntdll!NtQueryInformationToken` at `0x18002cb56`
- `ntdll!NtQueryInformationToken` at `0x18002cb56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cabc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002caf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cccd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cce2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cabc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002caf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cccd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002cce2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ccf7`
- `api-ms-win-security-audit-l1-1-0!AuditQuerySystemPolicy` at `0x18002c9fb`
- `api-ms-win-security-audit-l1-1-0!AuditQuerySystemPolicy` at `0x18002c9fb`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x18002ca1f`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x18002ca1f`

## string_xrefs

- `0x18002ca5b`: `AuthzInit(): RtlAdjustPrivilege failed. 0#x\n`

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
          if ( qword_1800E2768 )
          {
            v12 = qword_1800E2768(0, 2, a1, 4, &v23);
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
          if ( qword_1800E2718 )
          {
            if ( !v23 )
              return;
            if ( qword_1800E2780 && (unsigned int)qword_1800E2780(&v22, 4) )
            {
              if ( qword_1800E2778
                && (unsigned int)qword_1800E2778(1, qword_1800E2718, 4, v22, 6, v16, 2, a2, 2, a3, 2, a4) )
              {
                if ( qword_1800E2758
                  && (unsigned int)qword_1800E2758(
                                     0,
                                     qword_1800E2718,
                                     v23,
                                     v22,
                                     0,
                                     -1,
                                     &dword_1800A8ADC,
                                     &dword_1800A8ADC,
                                     &dword_1800A8ADC,
                                     &dword_1800A8ADC,
                                     &ppAuditPolicy) )
                {
                  if ( !qword_1800E2790 || !(unsigned int)qword_1800E2790(0, ppAuditPolicy, 0) )
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
            if ( ppAuditPolicy && qword_1800E2760 )
              qword_1800E2760();
            v11 = v22;
            if ( v22 && qword_1800E2788 )
              qword_1800E2788();
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
0x18002c990  push    rbp
0x18002c992  push    rbx
0x18002c993  push    rsi
0x18002c994  push    rdi
0x18002c995  push    r12
0x18002c997  push    r13
0x18002c999  push    r14
0x18002c99b  push    r15
0x18002c99d  lea     rbp, [rsp-17h]
0x18002c9a2  sub     rsp, 0E8h
0x18002c9a9  mov     rax, cs:__security_cookie
0x18002c9b0  xor     rax, rsp
0x18002c9b3  mov     [rbp+4Fh+var_50], rax
0x18002c9b7  mov     r12, [rbp+4Fh+TokenHandle]
0x18002c9bb  xorps   xmm0, xmm0
0x18002c9be  xor     edi, edi
0x18002c9c0  xor     eax, eax
0x18002c9c2  mov     r14, r8
0x18002c9c5  mov     [rbp+4Fh+var_58], rax
0x18002c9c9  mov     rsi, rdx
0x18002c9cc  mov     [rbp+4Fh+var_90], edi
0x18002c9cf  mov     r13d, ecx
0x18002c9d2  mov     [rbp+4Fh+var_A8], rdi
0x18002c9d6  lea     edx, [rax+1]; dwPolicyCount
0x18002c9d9  mov     [rbp+4Fh+var_A0], rdi
0x18002c9dd  lea     r8, [rbp+4Fh+ppAuditPolicy]; ppAuditPolicy
0x18002c9e1  mov     [rbp+4Fh+ppAuditPolicy], rdi
0x18002c9e5  lea     rcx, Audit_Logon_Others; pSubCategoryGuids
0x18002c9ec  mov     r15, r9
0x18002c9ef  movups  [rbp+4Fh+TokenInformation], xmm0
0x18002c9f3  movups  [rbp+4Fh+var_78], xmm0
0x18002c9f7  movups  [rbp+4Fh+var_68], xmm0
0x18002c9fb  call    cs:__imp_AuditQuerySystemPolicy
0x18002ca02  nop     dword ptr [rax+rax+00h]
0x18002ca07  test    al, al
0x18002ca09  jz      loc_18002CD56
0x18002ca0f  mov     rcx, [rbp+4Fh+ppAuditPolicy]; Buffer
0x18002ca13  test    rcx, rcx
0x18002ca16  jz      loc_18002CD56
0x18002ca1c  mov     bl, [rcx+10h]
0x18002ca1f  call    cs:__imp_AuditFree
0x18002ca26  nop     dword ptr [rax+rax+00h]
0x18002ca2b  test    bl, 1
0x18002ca2e  jz      loc_18002CD56
0x18002ca34  lea     r9, [rbp+4Fh+OldValue]; OldValue
0x18002ca38  mov     [rbp+4Fh+OldValue], dil
0x18002ca3c  xor     r8d, r8d; ForThread
0x18002ca3f  lea     ecx, [rdi+1Dh]; Privilege
0x18002ca42  mov     dl, 1; NewValue
0x18002ca44  call    cs:__imp_RtlAdjustPrivilege
0x18002ca4b  nop     dword ptr [rax+rax+00h]
0x18002ca50  mov     r8d, 0C000007Ch
0x18002ca56  cmp     eax, r8d
0x18002ca59  jnz     short loc_18002CA6F
0x18002ca5b  lea     rdx, aAuthzinitRtlad; "AuthzInit(): RtlAdjustPrivilege failed."...
0x18002ca62  lea     ecx, [rdi+4]; int
0x18002ca65  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002ca6a  jmp     loc_18002CD48
0x18002ca6f  mov     [rbp+4Fh+var_A0], rdi
0x18002ca73  call    ?Init@AuthzWrapper@@QEAAHXZ; AuthzWrapper::Init(void)
0x18002ca78  mov     ebx, eax
0x18002ca7a  mov     edi, 4
0x18002ca7f  test    eax, eax
0x18002ca81  jz      short loc_18002CADB
0x18002ca83  mov     rax, cs:qword_1800E2768
0x18002ca8a  test    rax, rax
0x18002ca8d  jnz     short loc_18002CA97
0x18002ca8f  xor     r13d, r13d
0x18002ca92  mov     ebx, r13d
0x18002ca95  jmp     short loc_18002CABC
0x18002ca97  lea     rcx, [rbp+4Fh+var_A0]
0x18002ca9b  mov     r9d, edi
0x18002ca9e  mov     [rsp+120h+ReturnLength], rcx
0x18002caa3  movzx   r8d, r13w
0x18002caa7  xor     ecx, ecx
0x18002caa9  mov     edx, 2
0x18002caae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cab3  xor     r13d, r13d
0x18002cab6  mov     ebx, eax
0x18002cab8  test    eax, eax
0x18002caba  jnz     short loc_18002CB11
0x18002cabc  call    cs:__imp_GetLastError
0x18002cac3  nop     dword ptr [rax+rax+00h]
0x18002cac8  lea     rdx, aAuthzinitAuthz_0; "AuthzInit(): AuthziInitializeAuditEvent"...
0x18002cacf  mov     ecx, edi; int
0x18002cad1  mov     r8d, eax
0x18002cad4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002cad9  jmp     short loc_18002CADE
0x18002cadb  xor     r13d, r13d
0x18002cade  mov     rdx, [rbp+4Fh+var_A0]; struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *
0x18002cae2  test    rdx, rdx
0x18002cae5  jz      short loc_18002CB11
0x18002cae7  call    ?AuthziFreeAuditEventType@AuthzWrapper@@QEAAHPEAUAUTHZ_AUDIT_EVENT_TYPE_HANDLE__@@@Z; AuthzWrapper::AuthziFreeAuditEventType(AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *)
0x18002caec  test    eax, eax
0x18002caee  jnz     short loc_18002CB0D
0x18002caf0  call    cs:__imp_GetLastError
0x18002caf7  nop     dword ptr [rax+rax+00h]
0x18002cafc  lea     rdx, aAuthzinitAuthz; "AuthzInit(): AuthziFreeAuditEventType()"...
0x18002cb03  mov     ecx, edi; int
0x18002cb05  mov     r8d, eax
0x18002cb08  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002cb0d  mov     [rbp+4Fh+var_A0], r13
0x18002cb11  cmp     [rbp+4Fh+OldValue], r13b
0x18002cb15  jnz     short loc_18002CB2F
0x18002cb17  xor     edx, edx; NewValue
0x18002cb19  lea     r9, [rbp+4Fh+OldValue]; OldValue
0x18002cb1d  xor     r8d, r8d; ForThread
0x18002cb20  lea     ecx, [rdx+1Dh]; Privilege
0x18002cb23  call    cs:__imp_RtlAdjustPrivilege
0x18002cb2a  nop     dword ptr [rax+rax+00h]
0x18002cb2f  test    ebx, ebx
0x18002cb31  jz      loc_18002CD48
0x18002cb37  test    r12, r12
0x18002cb3a  jz      short loc_18002CB6F
0x18002cb3c  mov     r9d, 38h ; '8'; TokenInformationLength
0x18002cb42  lea     rax, [rbp+4Fh+var_90]
0x18002cb46  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x18002cb4a  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x18002cb4f  mov     rcx, r12; TokenHandle
0x18002cb52  lea     edx, [r9-2Eh]; TokenInformationClass
0x18002cb56  call    cs:__imp_NtQueryInformationToken
0x18002cb5d  nop     dword ptr [rax+rax+00h]
0x18002cb62  mov     rbx, [rbp+4Fh+var_A8]
0x18002cb66  test    eax, eax
0x18002cb68  cmovns  rbx, qword ptr [rbp+4Fh+TokenInformation+8]
0x18002cb6d  jmp     short loc_18002CB73
0x18002cb6f  mov     rbx, [rbp+4Fh+var_A8]
0x18002cb73  lea     rax, aUnknown_0; "Unknown"
0x18002cb7a  test    rsi, rsi
0x18002cb7d  jz      short loc_18002CB85
0x18002cb7f  cmp     [rsi], r13w
0x18002cb83  jnz     short loc_18002CB88
0x18002cb85  mov     rsi, rax
0x18002cb88  test    r14, r14
0x18002cb8b  jz      short loc_18002CB93
0x18002cb8d  cmp     [r14], r13w
0x18002cb91  jnz     short loc_18002CB96
0x18002cb93  mov     r14, rax
0x18002cb96  test    r15, r15
0x18002cb99  jz      short loc_18002CBA1
0x18002cb9b  cmp     [r15], r13w
0x18002cb9f  jnz     short loc_18002CBA4
0x18002cba1  mov     r15, rax
0x18002cba4  cmp     cs:qword_1800E2718, r13
0x18002cbab  mov     [rbp+4Fh+ppAuditPolicy], r13
0x18002cbaf  mov     [rbp+4Fh+var_A8], r13
0x18002cbb3  jz      loc_18002CD48
0x18002cbb9  cmp     [rbp+4Fh+var_A0], r13
0x18002cbbd  jz      loc_18002CD56
0x18002cbc3  mov     rax, cs:qword_1800E2780
0x18002cbca  test    rax, rax
0x18002cbcd  jz      loc_18002CCF7
0x18002cbd3  mov     edx, edi
0x18002cbd5  lea     rcx, [rbp+4Fh+var_A8]
0x18002cbd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbde  test    eax, eax
0x18002cbe0  jz      loc_18002CCF7
0x18002cbe6  mov     rax, cs:qword_1800E2778
0x18002cbed  test    rax, rax
0x18002cbf0  jz      loc_18002CCE2
0x18002cbf6  mov     r9, [rbp+4Fh+var_A8]
0x18002cbfa  mov     ecx, 2
0x18002cbff  mov     rdx, cs:qword_1800E2718
0x18002cc06  mov     r8d, edi
0x18002cc09  mov     [rsp+120h+var_C8], r15
0x18002cc0e  mov     dword ptr [rsp+120h+var_D0], ecx
0x18002cc12  mov     [rsp+120h+var_D8], r14
0x18002cc17  mov     dword ptr [rsp+120h+var_E0], ecx
0x18002cc1b  mov     [rsp+120h+var_E8], rsi
0x18002cc20  mov     dword ptr [rsp+120h+var_F0], ecx
0x18002cc24  mov     ecx, 1
0x18002cc29  mov     [rsp+120h+var_F8], rbx
0x18002cc2e  mov     dword ptr [rsp+120h+ReturnLength], 6
0x18002cc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc3b  test    eax, eax
0x18002cc3d  jz      loc_18002CCE2
0x18002cc43  mov     rax, cs:qword_1800E2758
0x18002cc4a  test    rax, rax
0x18002cc4d  jz      short loc_18002CCCD
0x18002cc4f  mov     r9, [rbp+4Fh+var_A8]
0x18002cc53  lea     rcx, [rbp+4Fh+ppAuditPolicy]
0x18002cc57  mov     r8, [rbp+4Fh+var_A0]
0x18002cc5b  mov     rdx, cs:qword_1800E2718
0x18002cc62  mov     [rsp+120h+var_D0], rcx
0x18002cc67  lea     rcx, dword_1800A8ADC
0x18002cc6e  mov     [rsp+120h+var_D8], rcx
0x18002cc73  mov     [rsp+120h+var_E0], rcx
0x18002cc78  mov     [rsp+120h+var_E8], rcx
0x18002cc7d  mov     [rsp+120h+var_F0], rcx
0x18002cc82  xor     ecx, ecx
0x18002cc84  mov     dword ptr [rsp+120h+var_F8], 0FFFFFFFFh
0x18002cc8c  mov     [rsp+120h+ReturnLength], r13
0x18002cc91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc96  test    eax, eax
0x18002cc98  jz      short loc_18002CCCD
0x18002cc9a  mov     rax, cs:qword_1800E2790
0x18002cca1  test    rax, rax
0x18002cca4  jz      short loc_18002CCB8
0x18002cca6  mov     rdx, [rbp+4Fh+ppAuditPolicy]
0x18002ccaa  xor     r8d, r8d
0x18002ccad  xor     ecx, ecx
0x18002ccaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ccb4  test    eax, eax
0x18002ccb6  jnz     short loc_18002CD14
0x18002ccb8  call    cs:__imp_GetLastError
0x18002ccbf  nop     dword ptr [rax+rax+00h]
0x18002ccc4  lea     rdx, aAuthzreporteve_2; "AuthzReportEventW(): AuthziLogAuditEven"...
0x18002cccb  jmp     short loc_18002CD0A
0x18002cccd  call    cs:__imp_GetLastError
0x18002ccd4  nop     dword ptr [rax+rax+00h]
0x18002ccd9  lea     rdx, aAuthzreporteve; "AuthzReportEventW(): AuthziInitializeAu"...
0x18002cce0  jmp     short loc_18002CD0A
0x18002cce2  call    cs:__imp_GetLastError
0x18002cce9  nop     dword ptr [rax+rax+00h]
0x18002ccee  lea     rdx, aAuthzreporteve_0; "AuthzReportEventW(): AuthziInitializeAu"...
0x18002ccf5  jmp     short loc_18002CD0A
0x18002ccf7  call    cs:__imp_GetLastError
0x18002ccfe  nop     dword ptr [rax+rax+00h]
0x18002cd03  lea     rdx, aAuthzreporteve_1; "AuthzReportEventW(): AuthzAllocateAudit"...
0x18002cd0a  mov     r8d, eax
0x18002cd0d  mov     ecx, edi; int
0x18002cd0f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002cd14  mov     rcx, [rbp+4Fh+ppAuditPolicy]
0x18002cd18  test    rcx, rcx
0x18002cd1b  jz      short loc_18002CD2E
0x18002cd1d  mov     rax, cs:qword_1800E2760
0x18002cd24  test    rax, rax
0x18002cd27  jz      short loc_18002CD2E
0x18002cd29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd2e  mov     rcx, [rbp+4Fh+var_A8]
0x18002cd32  test    rcx, rcx
0x18002cd35  jz      short loc_18002CD48
0x18002cd37  mov     rax, cs:qword_1800E2788
0x18002cd3e  test    rax, rax
0x18002cd41  jz      short loc_18002CD48
0x18002cd43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cd48  mov     rdx, [rbp+4Fh+var_A0]; struct AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *
0x18002cd4c  test    rdx, rdx
0x18002cd4f  jz      short loc_18002CD56
0x18002cd51  call    ?AuthziFreeAuditEventType@AuthzWrapper@@QEAAHPEAUAUTHZ_AUDIT_EVENT_TYPE_HANDLE__@@@Z; AuthzWrapper::AuthziFreeAuditEventType(AUTHZ_AUDIT_EVENT_TYPE_HANDLE__ *)
0x18002cd56  mov     rcx, [rbp+4Fh+var_50]
0x18002cd5a  xor     rcx, rsp; StackCookie
0x18002cd5d  call    __security_check_cookie
0x18002cd62  add     rsp, 0E8h
0x18002cd69  pop     r15
0x18002cd6b  pop     r14
0x18002cd6d  pop     r13
0x18002cd6f  pop     r12
0x18002cd71  pop     rdi
0x18002cd72  pop     rsi
0x18002cd73  pop     rbx
0x18002cd74  pop     rbp
0x18002cd75  retn
```
