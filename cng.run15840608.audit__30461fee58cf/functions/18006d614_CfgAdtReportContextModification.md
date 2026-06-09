# CfgAdtReportContextModification

- ea: `0x18006d614`
- end: `0x18006d829`
- name: `CfgAdtReportContextModification`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006a2cc`

## callees

- `0x18006d614`
- `0x18006eae0`
- `0x18006ec28`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006d7c2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006d7c2`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006d7f8`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006d7f8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006d696`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006d696`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006d7e5`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006d7e5`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d6cd`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d70e`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d742`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d773`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d7a0`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d6cd`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d70e`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d742`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d773`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d7a0`

## string_xrefs

- `0x18006d7b6`: `Security`

## pseudocode

```c
__int64 CfgAdtReportContextModification(unsigned __int16 a1, int a2, __int64 *a3, int a4, ...)
{
  NTSTATUS appended; // ebx
  ULONG v7; // r8d
  __int64 *v8; // r9
  int Data; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-B0h] BYREF
  _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+70h] [rbp-90h] BYREF
  __int64 v15; // [rsp+4E0h] [rbp+3E0h] BYREF
  va_list va; // [rsp+4E0h] [rbp+3E0h]
  va_list va1; // [rsp+4E8h] [rbp+3E8h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v15 = va_arg(va1, _QWORD);
  Data = a2;
  v11 = a4;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  DestinationString = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  appended = CfgAdtpInitializeParameters(&AuditParameters, a1, 5065);
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
          v8 = &qword_1800A83B0;
        appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v7, v8);
        if ( appended >= 0 )
        {
          appended = SeSetAuditParameter(
                       &AuditParameters,
                       SeAdtParmTypeHexUlong,
                       ++AuditParameters.ParameterCount,
                       &v11);
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
                           SeAdtParmTypeHexUlong,
                           ++AuditParameters.ParameterCount,
                           va1);
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
    SeReleaseSubjectContext(&SubjectContext);
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18006d614  mov     [rsp-8+arg_0], rbx
0x18006d619  push    rbp
0x18006d61a  push    rsi
0x18006d61b  push    rdi
0x18006d61c  lea     rbp, [rsp-3A0h]
0x18006d624  sub     rsp, 4A0h
0x18006d62b  mov     rax, cs:__security_cookie
0x18006d632  xor     rax, rsp
0x18006d635  mov     [rbp+3B0h+var_20], rax
0x18006d63c  mov     rdi, r8
0x18006d63f  mov     [rsp+4B0h+Data], edx
0x18006d643  movzx   ebx, cx
0x18006d646  mov     [rsp+4B0h+var_478], r9d
0x18006d64b  xor     edx, edx; Val
0x18006d64d  lea     rcx, [rsp+4B0h+AuditParameters]; void *
0x18006d652  mov     r8d, 418h; Size
0x18006d658  call    memset
0x18006d65d  xorps   xmm1, xmm1
0x18006d660  lea     rcx, [rsp+4B0h+AuditParameters]
0x18006d665  xorps   xmm0, xmm0
0x18006d668  mov     r8d, 13C9h
0x18006d66e  movzx   edx, bx
0x18006d671  movups  xmmword ptr [rsp+4B0h+DestinationString.Length], xmm0
0x18006d676  movups  xmmword ptr [rsp+4B0h+SubjectContext.ClientToken], xmm1
0x18006d67b  movups  xmmword ptr [rsp+4B0h+SubjectContext.PrimaryToken], xmm1
0x18006d680  call    CfgAdtpInitializeParameters
0x18006d685  xor     esi, esi
0x18006d687  mov     ebx, eax
0x18006d689  test    eax, eax
0x18006d68b  js      loc_18006D804
0x18006d691  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x18006d696  call    cs:__imp_SeCaptureSubjectContext
0x18006d69d  nop     dword ptr [rax+rax+00h]
0x18006d6a2  lea     rdx, [rsp+4B0h+SubjectContext]
0x18006d6a7  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006d6ac  call    CfgAdtpAppendSecuritySubjectInfo
0x18006d6b1  mov     ebx, eax
0x18006d6b3  test    eax, eax
0x18006d6b5  js      loc_18006D7F3
0x18006d6bb  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]; Index
0x18006d6c0  lea     r9, [rsp+4B0h+Data]; Data
0x18006d6c5  lea     edx, [rsi+15h]; Type
0x18006d6c8  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006d6cd  call    cs:__imp_SeSetAuditParameter
0x18006d6d4  nop     dword ptr [rax+rax+00h]
0x18006d6d9  mov     ebx, eax
0x18006d6db  test    eax, eax
0x18006d6dd  js      loc_18006D7F3
0x18006d6e3  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006d6e8  inc     r8d; Index
0x18006d6eb  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006d6f0  test    rdi, rdi
0x18006d6f3  jz      short loc_18006D6FD
0x18006d6f5  mov     r9, rdi
0x18006d6f8  cmp     [rdi], si
0x18006d6fb  jnz     short loc_18006D704
0x18006d6fd  lea     r9, qword_1800A83B0; Data
0x18006d704  mov     edx, 1; Type
0x18006d709  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006d70e  call    cs:__imp_SeSetAuditParameter
0x18006d715  nop     dword ptr [rax+rax+00h]
0x18006d71a  mov     ebx, eax
0x18006d71c  test    eax, eax
0x18006d71e  js      loc_18006D7F3
0x18006d724  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006d729  lea     r9, [rsp+4B0h+var_478]; Data
0x18006d72e  inc     r8d; Index
0x18006d731  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006d736  mov     edi, 0Ah
0x18006d73b  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006d740  mov     edx, edi; Type
0x18006d742  call    cs:__imp_SeSetAuditParameter
0x18006d749  nop     dword ptr [rax+rax+00h]
0x18006d74e  mov     ebx, eax
0x18006d750  test    eax, eax
0x18006d752  js      loc_18006D7F3
0x18006d758  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006d75d  lea     r9, [rbp+3B0h+arg_20]; Data
0x18006d764  inc     r8d; Index
0x18006d767  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006d76c  mov     edx, edi; Type
0x18006d76e  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006d773  call    cs:__imp_SeSetAuditParameter
0x18006d77a  nop     dword ptr [rax+rax+00h]
0x18006d77f  mov     ebx, eax
0x18006d781  test    eax, eax
0x18006d783  js      short loc_18006D7F3
0x18006d785  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006d78a  lea     r9, [rbp+3B0h+arg_28]; Data
0x18006d791  inc     r8d; Index
0x18006d794  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006d799  mov     edx, edi; Type
0x18006d79b  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006d7a0  call    cs:__imp_SeSetAuditParameter
0x18006d7a7  nop     dword ptr [rax+rax+00h]
0x18006d7ac  mov     ebx, eax
0x18006d7ae  test    eax, eax
0x18006d7b0  js      short loc_18006D7F3
0x18006d7b2  inc     [rsp+4B0h+AuditParameters.ParameterCount]
0x18006d7b6  lea     rdx, aSecurity; "Security"
0x18006d7bd  lea     rcx, [rsp+4B0h+DestinationString]; DestinationString
0x18006d7c2  call    cs:__imp_RtlInitUnicodeString
0x18006d7c9  nop     dword ptr [rax+rax+00h]
0x18006d7ce  lea     r9, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006d7d3  mov     [rsp+4B0h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006d7db  xor     r8d, r8d; UserSid
0x18006d7de  lea     rdx, [rsp+4B0h+DestinationString]; SourceName
0x18006d7e3  xor     ecx, ecx; Flags
0x18006d7e5  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006d7ec  nop     dword ptr [rax+rax+00h]
0x18006d7f1  mov     ebx, eax
0x18006d7f3  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x18006d7f8  call    cs:__imp_SeReleaseSubjectContext
0x18006d7ff  nop     dword ptr [rax+rax+00h]
0x18006d804  mov     eax, ebx
0x18006d806  mov     rcx, [rbp+3B0h+var_20]
0x18006d80d  xor     rcx, rsp; StackCookie
0x18006d810  call    __security_check_cookie
0x18006d815  mov     rbx, [rsp+4B0h+arg_0]
0x18006d81d  add     rsp, 4A0h
0x18006d824  pop     rdi
0x18006d825  pop     rsi
0x18006d826  pop     rbp
0x18006d827  retn
```
