# CfgAdtReportFunctionOperation

- ea: `0x18006e6c0`
- end: `0x18006e95f`
- name: `CfgAdtReportFunctionOperation`
- size: `671`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006a720`
- `0x18006c46c`

## callees

- `0x18006e6c0`
- `0x18006f4e0`
- `0x18006f628`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006e8fa`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e8fa`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e92f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e92f`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e74e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e74e`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e91c`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e91c`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006e800`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006e800`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e783`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e7c4`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e826`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e851`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e87f`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e8ae`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e8d8`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e783`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e7c4`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e826`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e851`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e87f`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e8ae`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e8d8`

## string_xrefs

- `0x18006e8ee`: `Security`

## pseudocode

```c
__int64 CfgAdtReportFunctionOperation(unsigned __int16 a1, int a2, __int64 *a3, ULONG a4, PVOID a5, ...)
{
  NTSTATUS appended; // ebx
  ULONG v9; // r8d
  __int64 *v10; // r9
  int Data; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING String; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+58h] [rbp-A8h] BYREF
  struct _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+80h] [rbp-80h] BYREF
  char v17; // [rsp+4A0h] [rbp+3A0h] BYREF
  __int64 v18; // [rsp+538h] [rbp+438h] BYREF
  va_list va; // [rsp+538h] [rbp+438h]
  __int64 v20; // [rsp+540h] [rbp+440h] BYREF
  va_list va1; // [rsp+540h] [rbp+440h]
  va_list va2; // [rsp+548h] [rbp+448h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v18 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v20 = va_arg(va2, _QWORD);
  Data = a2;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  DestinationString = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  String = 0;
  appended = CfgAdtpInitializeParameters(&AuditParameters, a1, 5066);
  if ( appended >= 0 )
  {
    SeCaptureSubjectContext(&SubjectContext);
    appended = CfgAdtpAppendSecuritySubjectInfo(&AuditParameters);
    if ( appended >= 0 )
    {
      appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeMessage, AuditParameters.ParameterCount, &Data);
      if ( appended >= 0 )
      {
        v9 = ++AuditParameters.ParameterCount;
        if ( !a3 || (v10 = a3, !*(_WORD *)a3) )
          v10 = &qword_1800AA3B0;
        appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v9, v10);
        if ( appended >= 0 )
        {
          ++AuditParameters.ParameterCount;
          *(_DWORD *)&String.Length = 0x200000;
          String.Buffer = (PWSTR)&v17;
          appended = RtlIntegerToUnicodeString(a4, 0xAu, &String);
          if ( appended >= 0 )
          {
            appended = SeSetAuditParameter(
                         &AuditParameters,
                         SeAdtParmTypeString,
                         AuditParameters.ParameterCount,
                         &String);
            if ( appended >= 0 )
            {
              appended = SeSetAuditParameter(
                           &AuditParameters,
                           SeAdtParmTypeString,
                           ++AuditParameters.ParameterCount,
                           a5);
              if ( appended >= 0 )
              {
                appended = SeSetAuditParameter(
                             &AuditParameters,
                             SeAdtParmTypeHexUlong,
                             ++AuditParameters.ParameterCount,
                             va);
                if ( appended >= 0 )
                {
                  appended = SeSetAuditParameter(
                               &AuditParameters,
                               SeAdtParmTypeMessage,
                               ++AuditParameters.ParameterCount,
                               va1);
                  if ( appended >= 0 )
                  {
                    appended = SeSetAuditParameter(
                                 &AuditParameters,
                                 SeAdtParmTypeHexUlong,
                                 ++AuditParameters.ParameterCount,
                                 va2);
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
0x18006e6c0  push    rbp
0x18006e6c2  push    rbx
0x18006e6c3  push    rsi
0x18006e6c4  push    rdi
0x18006e6c5  push    r12
0x18006e6c7  push    r14
0x18006e6c9  push    r15
0x18006e6cb  lea     rbp, [rsp-3D0h]
0x18006e6d3  sub     rsp, 4D0h
0x18006e6da  mov     rax, cs:__security_cookie
0x18006e6e1  xor     rax, rsp
0x18006e6e4  mov     [rbp+400h+var_40], rax
0x18006e6eb  mov     r14, [rbp+400h+arg_20]
0x18006e6f2  mov     rdi, r8
0x18006e6f5  movzx   ebx, cx
0x18006e6f8  mov     [rsp+500h+Data], edx
0x18006e6fc  xor     edx, edx; Val
0x18006e6fe  lea     rcx, [rbp+400h+AuditParameters]; void *
0x18006e702  mov     r8d, 418h; Size
0x18006e708  mov     esi, r9d
0x18006e70b  call    memset
0x18006e710  xorps   xmm0, xmm0
0x18006e713  lea     rcx, [rbp+400h+AuditParameters]
0x18006e717  xorps   xmm1, xmm1
0x18006e71a  mov     r8d, 13CAh
0x18006e720  movzx   edx, bx
0x18006e723  movups  xmmword ptr [rsp+500h+DestinationString.Length], xmm0
0x18006e728  movups  xmmword ptr [rsp+500h+SubjectContext.ClientToken], xmm1
0x18006e72d  movups  xmmword ptr [rsp+500h+SubjectContext.PrimaryToken], xmm1
0x18006e732  movups  xmmword ptr [rsp+500h+String.Length], xmm0
0x18006e737  call    CfgAdtpInitializeParameters
0x18006e73c  xor     r15d, r15d
0x18006e73f  mov     ebx, eax
0x18006e741  test    eax, eax
0x18006e743  js      loc_18006E93B
0x18006e749  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x18006e74e  call    cs:__imp_SeCaptureSubjectContext
0x18006e755  nop     dword ptr [rax+rax+00h]
0x18006e75a  lea     rdx, [rsp+500h+SubjectContext]
0x18006e75f  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e763  call    CfgAdtpAppendSecuritySubjectInfo
0x18006e768  mov     ebx, eax
0x18006e76a  test    eax, eax
0x18006e76c  js      loc_18006E92A
0x18006e772  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x18006e776  lea     r9, [rsp+500h+Data]; Data
0x18006e77b  lea     edx, [r15+15h]; Type
0x18006e77f  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e783  call    cs:__imp_SeSetAuditParameter
0x18006e78a  nop     dword ptr [rax+rax+00h]
0x18006e78f  mov     ebx, eax
0x18006e791  test    eax, eax
0x18006e793  js      loc_18006E92A
0x18006e799  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e79d  lea     r12d, [r15+1]
0x18006e7a1  add     r8d, r12d; Index
0x18006e7a4  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e7a8  test    rdi, rdi
0x18006e7ab  jz      short loc_18006E7B6
0x18006e7ad  mov     r9, rdi
0x18006e7b0  cmp     [rdi], r15w
0x18006e7b4  jnz     short loc_18006E7BD
0x18006e7b6  lea     r9, qword_1800AA3B0; Data
0x18006e7bd  mov     edx, r12d; Type
0x18006e7c0  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e7c4  call    cs:__imp_SeSetAuditParameter
0x18006e7cb  nop     dword ptr [rax+rax+00h]
0x18006e7d0  mov     ebx, eax
0x18006e7d2  test    eax, eax
0x18006e7d4  js      loc_18006E92A
0x18006e7da  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x18006e7de  lea     rax, [rbp+400h+var_60]
0x18006e7e5  mov     edi, 0Ah
0x18006e7ea  mov     dword ptr [rsp+500h+String.Length], 200000h
0x18006e7f2  mov     edx, edi; Base
0x18006e7f4  mov     [rsp+500h+String.Buffer], rax
0x18006e7f9  lea     r8, [rsp+500h+String]; String
0x18006e7fe  mov     ecx, esi; Value
0x18006e800  call    cs:__imp_RtlIntegerToUnicodeString
0x18006e807  nop     dword ptr [rax+rax+00h]
0x18006e80c  mov     ebx, eax
0x18006e80e  test    eax, eax
0x18006e810  js      loc_18006E92A
0x18006e816  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x18006e81a  lea     r9, [rsp+500h+String]; Data
0x18006e81f  mov     edx, r12d; Type
0x18006e822  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e826  call    cs:__imp_SeSetAuditParameter
0x18006e82d  nop     dword ptr [rax+rax+00h]
0x18006e832  mov     ebx, eax
0x18006e834  test    eax, eax
0x18006e836  js      loc_18006E92A
0x18006e83c  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e840  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e844  add     r8d, r12d; Index
0x18006e847  mov     r9, r14; Data
0x18006e84a  mov     edx, r12d; Type
0x18006e84d  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e851  call    cs:__imp_SeSetAuditParameter
0x18006e858  nop     dword ptr [rax+rax+00h]
0x18006e85d  mov     ebx, eax
0x18006e85f  test    eax, eax
0x18006e861  js      loc_18006E92A
0x18006e867  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e86b  lea     r9, [rbp+400h+arg_28]; Data
0x18006e872  add     r8d, r12d; Index
0x18006e875  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e879  mov     edx, edi; Type
0x18006e87b  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e87f  call    cs:__imp_SeSetAuditParameter
0x18006e886  nop     dword ptr [rax+rax+00h]
0x18006e88b  mov     ebx, eax
0x18006e88d  test    eax, eax
0x18006e88f  js      loc_18006E92A
0x18006e895  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e899  lea     r9, [rbp+400h+arg_30]; Data
0x18006e8a0  add     r8d, r12d; Index
0x18006e8a3  lea     edx, [rdi+0Bh]; Type
0x18006e8a6  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e8aa  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e8ae  call    cs:__imp_SeSetAuditParameter
0x18006e8b5  nop     dword ptr [rax+rax+00h]
0x18006e8ba  mov     ebx, eax
0x18006e8bc  test    eax, eax
0x18006e8be  js      short loc_18006E92A
0x18006e8c0  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e8c4  lea     r9, [rbp+400h+arg_38]; Data
0x18006e8cb  add     r8d, r12d; Index
0x18006e8ce  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e8d2  mov     edx, edi; Type
0x18006e8d4  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e8d8  call    cs:__imp_SeSetAuditParameter
0x18006e8df  nop     dword ptr [rax+rax+00h]
0x18006e8e4  mov     ebx, eax
0x18006e8e6  test    eax, eax
0x18006e8e8  js      short loc_18006E92A
0x18006e8ea  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x18006e8ee  lea     rdx, aSecurity; "Security"
0x18006e8f5  lea     rcx, [rsp+500h+DestinationString]; DestinationString
0x18006e8fa  call    cs:__imp_RtlInitUnicodeString
0x18006e901  nop     dword ptr [rax+rax+00h]
0x18006e906  lea     r9, [rbp+400h+AuditParameters]; AuditParameters
0x18006e90a  mov     [rsp+500h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006e912  xor     r8d, r8d; UserSid
0x18006e915  lea     rdx, [rsp+500h+DestinationString]; SourceName
0x18006e91a  xor     ecx, ecx; Flags
0x18006e91c  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006e923  nop     dword ptr [rax+rax+00h]
0x18006e928  mov     ebx, eax
0x18006e92a  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x18006e92f  call    cs:__imp_SeReleaseSubjectContext
0x18006e936  nop     dword ptr [rax+rax+00h]
0x18006e93b  mov     eax, ebx
0x18006e93d  mov     rcx, [rbp+400h+var_40]
0x18006e944  xor     rcx, rsp; StackCookie
0x18006e947  call    __security_check_cookie
0x18006e94c  add     rsp, 4D0h
0x18006e953  pop     r15
0x18006e955  pop     r14
0x18006e957  pop     r12
0x18006e959  pop     rdi
0x18006e95a  pop     rsi
0x18006e95b  pop     rbx
0x18006e95c  pop     rbp
0x18006e95d  retn
```
