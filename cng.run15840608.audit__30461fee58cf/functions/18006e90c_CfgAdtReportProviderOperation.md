# CfgAdtReportProviderOperation

- ea: `0x18006e90c`
- end: `0x18006ead8`
- name: `CfgAdtReportProviderOperation`
- size: `460`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006b570`
- `0x18006c440`

## callees

- `0x18006e90c`
- `0x18006eae0`
- `0x18006ec28`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006ea71`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006ea71`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006eaa7`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006eaa7`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e98b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e98b`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006ea94`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006ea94`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e9c4`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e9f1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ea21`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ea4f`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e9c4`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e9f1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ea21`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ea4f`

## string_xrefs

- `0x18006ea65`: `Security`

## pseudocode

```c
__int64 CfgAdtReportProviderOperation(unsigned __int16 a1, void *a2, void *a3, int a4, ...)
{
  NTSTATUS appended; // ebx
  int Data; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+48h] [rbp-B8h] BYREF
  struct _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+70h] [rbp-90h] BYREF
  va_list va; // [rsp+4E0h] [rbp+3E0h] BYREF

  va_start(va, a4);
  Data = a4;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  DestinationString = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  appended = CfgAdtpInitializeParameters(&AuditParameters, a1, 5063);
  if ( appended >= 0 )
  {
    SeCaptureSubjectContext(&SubjectContext);
    appended = CfgAdtpAppendSecuritySubjectInfo(&AuditParameters);
    if ( appended >= 0 )
    {
      appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, AuditParameters.ParameterCount, a2);
      if ( appended >= 0 )
      {
        appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, ++AuditParameters.ParameterCount, a3);
        if ( appended >= 0 )
        {
          appended = SeSetAuditParameter(
                       &AuditParameters,
                       SeAdtParmTypeMessage,
                       ++AuditParameters.ParameterCount,
                       &Data);
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
0x18006e90c  mov     [rsp-8+arg_0], rbx
0x18006e911  push    rbp
0x18006e912  push    rsi
0x18006e913  push    rdi
0x18006e914  lea     rbp, [rsp-3A0h]
0x18006e91c  sub     rsp, 4A0h
0x18006e923  mov     rax, cs:__security_cookie
0x18006e92a  xor     rax, rsp
0x18006e92d  mov     [rbp+3B0h+var_20], rax
0x18006e934  mov     rsi, r8
0x18006e937  mov     [rsp+4B0h+Data], r9d
0x18006e93c  mov     rdi, rdx
0x18006e93f  movzx   ebx, cx
0x18006e942  xor     edx, edx; Val
0x18006e944  lea     rcx, [rsp+4B0h+AuditParameters]; void *
0x18006e949  mov     r8d, 418h; Size
0x18006e94f  call    memset
0x18006e954  xorps   xmm1, xmm1
0x18006e957  lea     rcx, [rsp+4B0h+AuditParameters]
0x18006e95c  xorps   xmm0, xmm0
0x18006e95f  mov     r8d, 13C7h
0x18006e965  movzx   edx, bx
0x18006e968  movups  xmmword ptr [rsp+4B0h+DestinationString.Length], xmm0
0x18006e96d  movups  xmmword ptr [rsp+4B0h+SubjectContext.ClientToken], xmm1
0x18006e972  movups  xmmword ptr [rsp+4B0h+SubjectContext.PrimaryToken], xmm1
0x18006e977  call    CfgAdtpInitializeParameters
0x18006e97c  mov     ebx, eax
0x18006e97e  test    eax, eax
0x18006e980  js      loc_18006EAB3
0x18006e986  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x18006e98b  call    cs:__imp_SeCaptureSubjectContext
0x18006e992  nop     dword ptr [rax+rax+00h]
0x18006e997  lea     rdx, [rsp+4B0h+SubjectContext]
0x18006e99c  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e9a1  call    CfgAdtpAppendSecuritySubjectInfo
0x18006e9a6  mov     ebx, eax
0x18006e9a8  test    eax, eax
0x18006e9aa  js      loc_18006EAA2
0x18006e9b0  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]; Index
0x18006e9b5  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e9ba  mov     r9, rdi; Data
0x18006e9bd  mov     edi, 1
0x18006e9c2  mov     edx, edi; Type
0x18006e9c4  call    cs:__imp_SeSetAuditParameter
0x18006e9cb  nop     dword ptr [rax+rax+00h]
0x18006e9d0  mov     ebx, eax
0x18006e9d2  test    eax, eax
0x18006e9d4  js      loc_18006EAA2
0x18006e9da  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006e9df  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e9e4  add     r8d, edi; Index
0x18006e9e7  mov     r9, rsi; Data
0x18006e9ea  mov     edx, edi; Type
0x18006e9ec  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006e9f1  call    cs:__imp_SeSetAuditParameter
0x18006e9f8  nop     dword ptr [rax+rax+00h]
0x18006e9fd  mov     ebx, eax
0x18006e9ff  test    eax, eax
0x18006ea01  js      loc_18006EAA2
0x18006ea07  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006ea0c  lea     r9, [rsp+4B0h+Data]; Data
0x18006ea11  add     r8d, edi; Index
0x18006ea14  lea     edx, [rdi+14h]; Type
0x18006ea17  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006ea1c  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006ea21  call    cs:__imp_SeSetAuditParameter
0x18006ea28  nop     dword ptr [rax+rax+00h]
0x18006ea2d  mov     ebx, eax
0x18006ea2f  test    eax, eax
0x18006ea31  js      short loc_18006EAA2
0x18006ea33  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006ea38  lea     r9, [rbp+3B0h+arg_20]; Data
0x18006ea3f  add     r8d, edi; Index
0x18006ea42  lea     edx, [rdi+9]; Type
0x18006ea45  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006ea4a  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006ea4f  call    cs:__imp_SeSetAuditParameter
0x18006ea56  nop     dword ptr [rax+rax+00h]
0x18006ea5b  mov     ebx, eax
0x18006ea5d  test    eax, eax
0x18006ea5f  js      short loc_18006EAA2
0x18006ea61  add     [rsp+4B0h+AuditParameters.ParameterCount], edi
0x18006ea65  lea     rdx, aSecurity; "Security"
0x18006ea6c  lea     rcx, [rsp+4B0h+DestinationString]; DestinationString
0x18006ea71  call    cs:__imp_RtlInitUnicodeString
0x18006ea78  nop     dword ptr [rax+rax+00h]
0x18006ea7d  lea     r9, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006ea82  mov     [rsp+4B0h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006ea8a  xor     r8d, r8d; UserSid
0x18006ea8d  lea     rdx, [rsp+4B0h+DestinationString]; SourceName
0x18006ea92  xor     ecx, ecx; Flags
0x18006ea94  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006ea9b  nop     dword ptr [rax+rax+00h]
0x18006eaa0  mov     ebx, eax
0x18006eaa2  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x18006eaa7  call    cs:__imp_SeReleaseSubjectContext
0x18006eaae  nop     dword ptr [rax+rax+00h]
0x18006eab3  mov     eax, ebx
0x18006eab5  mov     rcx, [rbp+3B0h+var_20]
0x18006eabc  xor     rcx, rsp; StackCookie
0x18006eabf  call    __security_check_cookie
0x18006eac4  mov     rbx, [rsp+4B0h+arg_0]
0x18006eacc  add     rsp, 4A0h
0x18006ead3  pop     rdi
0x18006ead4  pop     rsi
0x18006ead5  pop     rbp
0x18006ead6  retn
```
