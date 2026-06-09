# CfgAdtReportContextOperation

- ea: `0x1800779d0`
- end: `0x180077bb5`
- name: `CfgAdtReportContextOperation`
- size: `485`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007493c`
- `0x180074bac`

## callees

- `0x1800779d0`
- `0x180078c80`
- `0x180078dc8`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180077b4e`
- `ntoskrnl!RtlInitUnicodeString` at `0x180077b4e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180077b84`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180077b84`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180077a52`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180077a52`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x180077b71`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x180077b71`
- `ntoskrnl!SeSetAuditParameter` at `0x180077a89`
- `ntoskrnl!SeSetAuditParameter` at `0x180077aca`
- `ntoskrnl!SeSetAuditParameter` at `0x180077afc`
- `ntoskrnl!SeSetAuditParameter` at `0x180077b2c`
- `ntoskrnl!SeSetAuditParameter` at `0x180077a89`
- `ntoskrnl!SeSetAuditParameter` at `0x180077aca`
- `ntoskrnl!SeSetAuditParameter` at `0x180077afc`
- `ntoskrnl!SeSetAuditParameter` at `0x180077b2c`

## string_xrefs

- `0x180077b42`: `Security`

## pseudocode

```c
__int64 CfgAdtReportContextOperation(unsigned __int16 a1, int a2, __int64 *a3, int a4, ...)
{
  NTSTATUS appended; // ebx
  ULONG v7; // r8d
  __int64 *v8; // r9
  int Data; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-B0h] BYREF
  struct _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+70h] [rbp-90h] BYREF
  va_list va; // [rsp+4E0h] [rbp+3E0h] BYREF

  va_start(va, a4);
  Data = a2;
  v11 = a4;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  DestinationString = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  appended = CfgAdtpInitializeParameters(&AuditParameters, a1, 5064);
  if ( appended >= 0 )
  {
    SeCaptureSubjectContext(&SubjectContext);
    appended = CfgAdtpAppendSecuritySubjectInfo(&AuditParameters);
    if ( appended >= 0 )
    {
      appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeMessage, AuditParameters.ParameterCount, &Data);
      if ( appended >= 0 )
      {
        v7 = ++AuditParameters.ParameterCount;
        if ( !a3 || (v8 = a3, !*(_WORD *)a3) )
          v8 = &qword_1800AF9A0;
        appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v7, v8);
        if ( appended >= 0 )
        {
          appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeMessage, ++AuditParameters.ParameterCount, &v11);
          if ( appended >= 0 )
          {
            appended = SeSetAuditParameter(
                         &AuditParameters,
                         SeAdtParmTypeHexUlong,
                         ++AuditParameters.ParameterCount,
                         va);
            if ( appended >= 0 )
            {
              ++AuditParameters.ParameterCount;
              RtlInitUnicodeString(&DestinationString, L"Security");
              appended = SeReportSecurityEventWithSubCategory(0, &DestinationString, 0, &AuditParameters, 0x91u);
            }
          }
        }
      }
    }
    SeReleaseSubjectContext(&SubjectContext);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1800779d0  mov     [rsp-8+arg_0], rbx
0x1800779d5  push    rbp
0x1800779d6  push    rsi
0x1800779d7  push    rdi
0x1800779d8  lea     rbp, [rsp-3A0h]
0x1800779e0  sub     rsp, 4A0h
0x1800779e7  mov     rax, cs:__security_cookie
0x1800779ee  xor     rax, rsp
0x1800779f1  mov     [rbp+3B0h+var_20], rax
0x1800779f8  mov     rdi, r8
0x1800779fb  mov     [rsp+4B0h+Data], edx
0x1800779ff  movzx   ebx, cx
0x180077a02  mov     [rsp+4B0h+var_478], r9d
0x180077a07  xor     edx, edx; Val
0x180077a09  lea     rcx, [rsp+4B0h+AuditParameters]; void *
0x180077a0e  mov     r8d, 418h; Size
0x180077a14  call    memset
0x180077a19  xorps   xmm1, xmm1
0x180077a1c  lea     rcx, [rsp+4B0h+AuditParameters]
0x180077a21  xorps   xmm0, xmm0
0x180077a24  mov     r8d, 13C8h
0x180077a2a  movzx   edx, bx
0x180077a2d  movups  xmmword ptr [rsp+4B0h+DestinationString.Length], xmm0
0x180077a32  movups  xmmword ptr [rsp+4B0h+SubjectContext.ClientToken], xmm1
0x180077a37  movups  xmmword ptr [rsp+4B0h+SubjectContext.PrimaryToken], xmm1
0x180077a3c  call    CfgAdtpInitializeParameters
0x180077a41  xor     esi, esi
0x180077a43  mov     ebx, eax
0x180077a45  test    eax, eax
0x180077a47  js      loc_180077B90
0x180077a4d  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x180077a52  call    cs:__imp_SeCaptureSubjectContext
0x180077a59  nop     dword ptr [rax+rax+00h]
0x180077a5e  lea     rdx, [rsp+4B0h+SubjectContext]
0x180077a63  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x180077a68  call    CfgAdtpAppendSecuritySubjectInfo
0x180077a6d  mov     ebx, eax
0x180077a6f  test    eax, eax
0x180077a71  js      loc_180077B7F
0x180077a77  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]; Index
0x180077a7c  lea     r9, [rsp+4B0h+Data]; Data
0x180077a81  lea     edx, [rsi+15h]; Type
0x180077a84  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x180077a89  call    cs:__imp_SeSetAuditParameter
0x180077a90  nop     dword ptr [rax+rax+00h]
0x180077a95  mov     ebx, eax
0x180077a97  test    eax, eax
0x180077a99  js      loc_180077B7F
0x180077a9f  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x180077aa4  inc     r8d; Index
0x180077aa7  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x180077aac  test    rdi, rdi
0x180077aaf  jz      short loc_180077AB9
0x180077ab1  mov     r9, rdi
0x180077ab4  cmp     [rdi], si
0x180077ab7  jnz     short loc_180077AC0
0x180077ab9  lea     r9, qword_1800AF9A0; Data
0x180077ac0  mov     edx, 1; Type
0x180077ac5  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x180077aca  call    cs:__imp_SeSetAuditParameter
0x180077ad1  nop     dword ptr [rax+rax+00h]
0x180077ad6  mov     ebx, eax
0x180077ad8  test    eax, eax
0x180077ada  js      loc_180077B7F
0x180077ae0  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x180077ae5  lea     r9, [rsp+4B0h+var_478]; Data
0x180077aea  inc     r8d; Index
0x180077aed  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x180077af2  mov     edx, 15h; Type
0x180077af7  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x180077afc  call    cs:__imp_SeSetAuditParameter
0x180077b03  nop     dword ptr [rax+rax+00h]
0x180077b08  mov     ebx, eax
0x180077b0a  test    eax, eax
0x180077b0c  js      short loc_180077B7F
0x180077b0e  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x180077b13  lea     r9, [rbp+3B0h+arg_20]; Data
0x180077b1a  inc     r8d; Index
0x180077b1d  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x180077b22  mov     edx, 0Ah; Type
0x180077b27  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x180077b2c  call    cs:__imp_SeSetAuditParameter
0x180077b33  nop     dword ptr [rax+rax+00h]
0x180077b38  mov     ebx, eax
0x180077b3a  test    eax, eax
0x180077b3c  js      short loc_180077B7F
0x180077b3e  inc     [rsp+4B0h+AuditParameters.ParameterCount]
0x180077b42  lea     rdx, aSecurity; "Security"
0x180077b49  lea     rcx, [rsp+4B0h+DestinationString]; DestinationString
0x180077b4e  call    cs:__imp_RtlInitUnicodeString
0x180077b55  nop     dword ptr [rax+rax+00h]
0x180077b5a  lea     r9, [rsp+4B0h+AuditParameters]; AuditParameters
0x180077b5f  mov     [rsp+4B0h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x180077b67  xor     r8d, r8d; UserSid
0x180077b6a  lea     rdx, [rsp+4B0h+DestinationString]; SourceName
0x180077b6f  xor     ecx, ecx; Flags
0x180077b71  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x180077b78  nop     dword ptr [rax+rax+00h]
0x180077b7d  mov     ebx, eax
0x180077b7f  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x180077b84  call    cs:__imp_SeReleaseSubjectContext
0x180077b8b  nop     dword ptr [rax+rax+00h]
0x180077b90  mov     eax, ebx
0x180077b92  mov     rcx, [rbp+3B0h+var_20]
0x180077b99  xor     rcx, rsp; StackCookie
0x180077b9c  call    __security_check_cookie
0x180077ba1  mov     rbx, [rsp+4B0h+arg_0]
0x180077ba9  add     rsp, 4A0h
0x180077bb0  pop     rdi
0x180077bb1  pop     rsi
0x180077bb2  pop     rbp
0x180077bb3  retn
```
