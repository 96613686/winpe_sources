# CfgAdtReportContextOperation

- ea: `0x18006d830`
- end: `0x18006da15`
- name: `CfgAdtReportContextOperation`
- size: `485`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006a79c`
- `0x18006aa0c`

## callees

- `0x18006d830`
- `0x18006eae0`
- `0x18006ec28`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006d9ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006d9ae`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006d9e4`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006d9e4`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006d8b2`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006d8b2`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006d9d1`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006d9d1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d8e9`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d92a`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d95c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d98c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d8e9`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d92a`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d95c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006d98c`

## string_xrefs

- `0x18006d9a2`: `Security`

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
          v8 = &qword_1800A83B0;
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
0x18006d830  mov     [rsp-8+arg_0], rbx
0x18006d835  push    rbp
0x18006d836  push    rsi
0x18006d837  push    rdi
0x18006d838  lea     rbp, [rsp-3A0h]
0x18006d840  sub     rsp, 4A0h
0x18006d847  mov     rax, cs:__security_cookie
0x18006d84e  xor     rax, rsp
0x18006d851  mov     [rbp+3B0h+var_20], rax
0x18006d858  mov     rdi, r8
0x18006d85b  mov     [rsp+4B0h+Data], edx
0x18006d85f  movzx   ebx, cx
0x18006d862  mov     [rsp+4B0h+var_478], r9d
0x18006d867  xor     edx, edx; Val
0x18006d869  lea     rcx, [rsp+4B0h+AuditParameters]; void *
0x18006d86e  mov     r8d, 418h; Size
0x18006d874  call    memset
0x18006d879  xorps   xmm1, xmm1
0x18006d87c  lea     rcx, [rsp+4B0h+AuditParameters]
0x18006d881  xorps   xmm0, xmm0
0x18006d884  mov     r8d, 13C8h
0x18006d88a  movzx   edx, bx
0x18006d88d  movups  xmmword ptr [rsp+4B0h+DestinationString.Length], xmm0
0x18006d892  movups  xmmword ptr [rsp+4B0h+SubjectContext.ClientToken], xmm1
0x18006d897  movups  xmmword ptr [rsp+4B0h+SubjectContext.PrimaryToken], xmm1
0x18006d89c  call    CfgAdtpInitializeParameters
0x18006d8a1  xor     esi, esi
0x18006d8a3  mov     ebx, eax
0x18006d8a5  test    eax, eax
0x18006d8a7  js      loc_18006D9F0
0x18006d8ad  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x18006d8b2  call    cs:__imp_SeCaptureSubjectContext
0x18006d8b9  nop     dword ptr [rax+rax+00h]
0x18006d8be  lea     rdx, [rsp+4B0h+SubjectContext]
0x18006d8c3  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006d8c8  call    CfgAdtpAppendSecuritySubjectInfo
0x18006d8cd  mov     ebx, eax
0x18006d8cf  test    eax, eax
0x18006d8d1  js      loc_18006D9DF
0x18006d8d7  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]; Index
0x18006d8dc  lea     r9, [rsp+4B0h+Data]; Data
0x18006d8e1  lea     edx, [rsi+15h]; Type
0x18006d8e4  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006d8e9  call    cs:__imp_SeSetAuditParameter
0x18006d8f0  nop     dword ptr [rax+rax+00h]
0x18006d8f5  mov     ebx, eax
0x18006d8f7  test    eax, eax
0x18006d8f9  js      loc_18006D9DF
0x18006d8ff  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006d904  inc     r8d; Index
0x18006d907  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006d90c  test    rdi, rdi
0x18006d90f  jz      short loc_18006D919
0x18006d911  mov     r9, rdi
0x18006d914  cmp     [rdi], si
0x18006d917  jnz     short loc_18006D920
0x18006d919  lea     r9, qword_1800A83B0; Data
0x18006d920  mov     edx, 1; Type
0x18006d925  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006d92a  call    cs:__imp_SeSetAuditParameter
0x18006d931  nop     dword ptr [rax+rax+00h]
0x18006d936  mov     ebx, eax
0x18006d938  test    eax, eax
0x18006d93a  js      loc_18006D9DF
0x18006d940  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006d945  lea     r9, [rsp+4B0h+var_478]; Data
0x18006d94a  inc     r8d; Index
0x18006d94d  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006d952  mov     edx, 15h; Type
0x18006d957  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006d95c  call    cs:__imp_SeSetAuditParameter
0x18006d963  nop     dword ptr [rax+rax+00h]
0x18006d968  mov     ebx, eax
0x18006d96a  test    eax, eax
0x18006d96c  js      short loc_18006D9DF
0x18006d96e  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006d973  lea     r9, [rbp+3B0h+arg_20]; Data
0x18006d97a  inc     r8d; Index
0x18006d97d  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006d982  mov     edx, 0Ah; Type
0x18006d987  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006d98c  call    cs:__imp_SeSetAuditParameter
0x18006d993  nop     dword ptr [rax+rax+00h]
0x18006d998  mov     ebx, eax
0x18006d99a  test    eax, eax
0x18006d99c  js      short loc_18006D9DF
0x18006d99e  inc     [rsp+4B0h+AuditParameters.ParameterCount]
0x18006d9a2  lea     rdx, aSecurity; "Security"
0x18006d9a9  lea     rcx, [rsp+4B0h+DestinationString]; DestinationString
0x18006d9ae  call    cs:__imp_RtlInitUnicodeString
0x18006d9b5  nop     dword ptr [rax+rax+00h]
0x18006d9ba  lea     r9, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006d9bf  mov     [rsp+4B0h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006d9c7  xor     r8d, r8d; UserSid
0x18006d9ca  lea     rdx, [rsp+4B0h+DestinationString]; SourceName
0x18006d9cf  xor     ecx, ecx; Flags
0x18006d9d1  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006d9d8  nop     dword ptr [rax+rax+00h]
0x18006d9dd  mov     ebx, eax
0x18006d9df  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x18006d9e4  call    cs:__imp_SeReleaseSubjectContext
0x18006d9eb  nop     dword ptr [rax+rax+00h]
0x18006d9f0  mov     eax, ebx
0x18006d9f2  mov     rcx, [rbp+3B0h+var_20]
0x18006d9f9  xor     rcx, rsp; StackCookie
0x18006d9fc  call    __security_check_cookie
0x18006da01  mov     rbx, [rsp+4B0h+arg_0]
0x18006da09  add     rsp, 4A0h
0x18006da10  pop     rdi
0x18006da11  pop     rsi
0x18006da12  pop     rbp
0x18006da13  retn
```
