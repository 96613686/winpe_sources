# CfgAdtReportProviderOperation

- ea: `0x180078aac`
- end: `0x180078c78`
- name: `CfgAdtReportProviderOperation`
- size: `460`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180075710`
- `0x1800765e0`

## callees

- `0x180078aac`
- `0x180078c80`
- `0x180078dc8`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180078c11`
- `ntoskrnl!RtlInitUnicodeString` at `0x180078c11`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180078c47`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180078c47`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180078b2b`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180078b2b`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x180078c34`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x180078c34`
- `ntoskrnl!SeSetAuditParameter` at `0x180078b64`
- `ntoskrnl!SeSetAuditParameter` at `0x180078b91`
- `ntoskrnl!SeSetAuditParameter` at `0x180078bc1`
- `ntoskrnl!SeSetAuditParameter` at `0x180078bef`
- `ntoskrnl!SeSetAuditParameter` at `0x180078b64`
- `ntoskrnl!SeSetAuditParameter` at `0x180078b91`
- `ntoskrnl!SeSetAuditParameter` at `0x180078bc1`
- `ntoskrnl!SeSetAuditParameter` at `0x180078bef`

## string_xrefs

- `0x180078c05`: `Security`

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
0x180078aac  mov     [rsp-8+arg_0], rbx
0x180078ab1  push    rbp
0x180078ab2  push    rsi
0x180078ab3  push    rdi
0x180078ab4  lea     rbp, [rsp-3A0h]
0x180078abc  sub     rsp, 4A0h
0x180078ac3  mov     rax, cs:__security_cookie
0x180078aca  xor     rax, rsp
0x180078acd  mov     [rbp+3B0h+var_20], rax
0x180078ad4  mov     rsi, r8
0x180078ad7  mov     [rsp+4B0h+Data], r9d
0x180078adc  mov     rdi, rdx
0x180078adf  movzx   ebx, cx
0x180078ae2  xor     edx, edx; Val
0x180078ae4  lea     rcx, [rsp+4B0h+AuditParameters]; void *
0x180078ae9  mov     r8d, 418h; Size
0x180078aef  call    memset
0x180078af4  xorps   xmm1, xmm1
0x180078af7  lea     rcx, [rsp+4B0h+AuditParameters]
0x180078afc  xorps   xmm0, xmm0
0x180078aff  mov     r8d, 13C7h
0x180078b05  movzx   edx, bx
0x180078b08  movups  xmmword ptr [rsp+4B0h+DestinationString.Length], xmm0
0x180078b0d  movups  xmmword ptr [rsp+4B0h+SubjectContext.ClientToken], xmm1
0x180078b12  movups  xmmword ptr [rsp+4B0h+SubjectContext.PrimaryToken], xmm1
0x180078b17  call    CfgAdtpInitializeParameters
0x180078b1c  mov     ebx, eax
0x180078b1e  test    eax, eax
0x180078b20  js      loc_180078C53
0x180078b26  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x180078b2b  call    cs:__imp_SeCaptureSubjectContext
0x180078b32  nop     dword ptr [rax+rax+00h]
0x180078b37  lea     rdx, [rsp+4B0h+SubjectContext]
0x180078b3c  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x180078b41  call    CfgAdtpAppendSecuritySubjectInfo
0x180078b46  mov     ebx, eax
0x180078b48  test    eax, eax
0x180078b4a  js      loc_180078C42
0x180078b50  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]; Index
0x180078b55  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x180078b5a  mov     r9, rdi; Data
0x180078b5d  mov     edi, 1
0x180078b62  mov     edx, edi; Type
0x180078b64  call    cs:__imp_SeSetAuditParameter
0x180078b6b  nop     dword ptr [rax+rax+00h]
0x180078b70  mov     ebx, eax
0x180078b72  test    eax, eax
0x180078b74  js      loc_180078C42
0x180078b7a  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x180078b7f  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x180078b84  add     r8d, edi; Index
0x180078b87  mov     r9, rsi; Data
0x180078b8a  mov     edx, edi; Type
0x180078b8c  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x180078b91  call    cs:__imp_SeSetAuditParameter
0x180078b98  nop     dword ptr [rax+rax+00h]
0x180078b9d  mov     ebx, eax
0x180078b9f  test    eax, eax
0x180078ba1  js      loc_180078C42
0x180078ba7  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x180078bac  lea     r9, [rsp+4B0h+Data]; Data
0x180078bb1  add     r8d, edi; Index
0x180078bb4  lea     edx, [rdi+14h]; Type
0x180078bb7  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x180078bbc  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x180078bc1  call    cs:__imp_SeSetAuditParameter
0x180078bc8  nop     dword ptr [rax+rax+00h]
0x180078bcd  mov     ebx, eax
0x180078bcf  test    eax, eax
0x180078bd1  js      short loc_180078C42
0x180078bd3  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x180078bd8  lea     r9, [rbp+3B0h+arg_20]; Data
0x180078bdf  add     r8d, edi; Index
0x180078be2  lea     edx, [rdi+9]; Type
0x180078be5  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x180078bea  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x180078bef  call    cs:__imp_SeSetAuditParameter
0x180078bf6  nop     dword ptr [rax+rax+00h]
0x180078bfb  mov     ebx, eax
0x180078bfd  test    eax, eax
0x180078bff  js      short loc_180078C42
0x180078c01  add     [rsp+4B0h+AuditParameters.ParameterCount], edi
0x180078c05  lea     rdx, aSecurity; "Security"
0x180078c0c  lea     rcx, [rsp+4B0h+DestinationString]; DestinationString
0x180078c11  call    cs:__imp_RtlInitUnicodeString
0x180078c18  nop     dword ptr [rax+rax+00h]
0x180078c1d  lea     r9, [rsp+4B0h+AuditParameters]; AuditParameters
0x180078c22  mov     [rsp+4B0h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x180078c2a  xor     r8d, r8d; UserSid
0x180078c2d  lea     rdx, [rsp+4B0h+DestinationString]; SourceName
0x180078c32  xor     ecx, ecx; Flags
0x180078c34  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x180078c3b  nop     dword ptr [rax+rax+00h]
0x180078c40  mov     ebx, eax
0x180078c42  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x180078c47  call    cs:__imp_SeReleaseSubjectContext
0x180078c4e  nop     dword ptr [rax+rax+00h]
0x180078c53  mov     eax, ebx
0x180078c55  mov     rcx, [rbp+3B0h+var_20]
0x180078c5c  xor     rcx, rsp; StackCookie
0x180078c5f  call    __security_check_cookie
0x180078c64  mov     rbx, [rsp+4B0h+arg_0]
0x180078c6c  add     rsp, 4A0h
0x180078c73  pop     rdi
0x180078c74  pop     rsi
0x180078c75  pop     rbp
0x180078c76  retn
```
