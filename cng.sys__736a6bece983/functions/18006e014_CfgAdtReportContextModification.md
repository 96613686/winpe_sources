# CfgAdtReportContextModification

- ea: `0x18006e014`
- end: `0x18006e229`
- name: `CfgAdtReportContextModification`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006accc`

## callees

- `0x18006e014`
- `0x18006f4e0`
- `0x18006f628`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006e1c2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e1c2`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e1f8`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e1f8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e096`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e096`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e1e5`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e1e5`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e0cd`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e10e`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e142`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e173`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e1a0`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e0cd`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e10e`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e142`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e173`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e1a0`

## string_xrefs

- `0x18006e1b6`: `Security`

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
          v8 = &qword_1800AA3B0;
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
0x18006e014  mov     [rsp-8+arg_0], rbx
0x18006e019  push    rbp
0x18006e01a  push    rsi
0x18006e01b  push    rdi
0x18006e01c  lea     rbp, [rsp-3A0h]
0x18006e024  sub     rsp, 4A0h
0x18006e02b  mov     rax, cs:__security_cookie
0x18006e032  xor     rax, rsp
0x18006e035  mov     [rbp+3B0h+var_20], rax
0x18006e03c  mov     rdi, r8
0x18006e03f  mov     [rsp+4B0h+Data], edx
0x18006e043  movzx   ebx, cx
0x18006e046  mov     [rsp+4B0h+var_478], r9d
0x18006e04b  xor     edx, edx; Val
0x18006e04d  lea     rcx, [rsp+4B0h+AuditParameters]; void *
0x18006e052  mov     r8d, 418h; Size
0x18006e058  call    memset
0x18006e05d  xorps   xmm1, xmm1
0x18006e060  lea     rcx, [rsp+4B0h+AuditParameters]
0x18006e065  xorps   xmm0, xmm0
0x18006e068  mov     r8d, 13C9h
0x18006e06e  movzx   edx, bx
0x18006e071  movups  xmmword ptr [rsp+4B0h+DestinationString.Length], xmm0
0x18006e076  movups  xmmword ptr [rsp+4B0h+SubjectContext.ClientToken], xmm1
0x18006e07b  movups  xmmword ptr [rsp+4B0h+SubjectContext.PrimaryToken], xmm1
0x18006e080  call    CfgAdtpInitializeParameters
0x18006e085  xor     esi, esi
0x18006e087  mov     ebx, eax
0x18006e089  test    eax, eax
0x18006e08b  js      loc_18006E204
0x18006e091  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x18006e096  call    cs:__imp_SeCaptureSubjectContext
0x18006e09d  nop     dword ptr [rax+rax+00h]
0x18006e0a2  lea     rdx, [rsp+4B0h+SubjectContext]
0x18006e0a7  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e0ac  call    CfgAdtpAppendSecuritySubjectInfo
0x18006e0b1  mov     ebx, eax
0x18006e0b3  test    eax, eax
0x18006e0b5  js      loc_18006E1F3
0x18006e0bb  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]; Index
0x18006e0c0  lea     r9, [rsp+4B0h+Data]; Data
0x18006e0c5  lea     edx, [rsi+15h]; Type
0x18006e0c8  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e0cd  call    cs:__imp_SeSetAuditParameter
0x18006e0d4  nop     dword ptr [rax+rax+00h]
0x18006e0d9  mov     ebx, eax
0x18006e0db  test    eax, eax
0x18006e0dd  js      loc_18006E1F3
0x18006e0e3  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006e0e8  inc     r8d; Index
0x18006e0eb  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006e0f0  test    rdi, rdi
0x18006e0f3  jz      short loc_18006E0FD
0x18006e0f5  mov     r9, rdi
0x18006e0f8  cmp     [rdi], si
0x18006e0fb  jnz     short loc_18006E104
0x18006e0fd  lea     r9, qword_1800AA3B0; Data
0x18006e104  mov     edx, 1; Type
0x18006e109  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e10e  call    cs:__imp_SeSetAuditParameter
0x18006e115  nop     dword ptr [rax+rax+00h]
0x18006e11a  mov     ebx, eax
0x18006e11c  test    eax, eax
0x18006e11e  js      loc_18006E1F3
0x18006e124  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006e129  lea     r9, [rsp+4B0h+var_478]; Data
0x18006e12e  inc     r8d; Index
0x18006e131  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e136  mov     edi, 0Ah
0x18006e13b  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006e140  mov     edx, edi; Type
0x18006e142  call    cs:__imp_SeSetAuditParameter
0x18006e149  nop     dword ptr [rax+rax+00h]
0x18006e14e  mov     ebx, eax
0x18006e150  test    eax, eax
0x18006e152  js      loc_18006E1F3
0x18006e158  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006e15d  lea     r9, [rbp+3B0h+arg_20]; Data
0x18006e164  inc     r8d; Index
0x18006e167  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e16c  mov     edx, edi; Type
0x18006e16e  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006e173  call    cs:__imp_SeSetAuditParameter
0x18006e17a  nop     dword ptr [rax+rax+00h]
0x18006e17f  mov     ebx, eax
0x18006e181  test    eax, eax
0x18006e183  js      short loc_18006E1F3
0x18006e185  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18006e18a  lea     r9, [rbp+3B0h+arg_28]; Data
0x18006e191  inc     r8d; Index
0x18006e194  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e199  mov     edx, edi; Type
0x18006e19b  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x18006e1a0  call    cs:__imp_SeSetAuditParameter
0x18006e1a7  nop     dword ptr [rax+rax+00h]
0x18006e1ac  mov     ebx, eax
0x18006e1ae  test    eax, eax
0x18006e1b0  js      short loc_18006E1F3
0x18006e1b2  inc     [rsp+4B0h+AuditParameters.ParameterCount]
0x18006e1b6  lea     rdx, aSecurity; "Security"
0x18006e1bd  lea     rcx, [rsp+4B0h+DestinationString]; DestinationString
0x18006e1c2  call    cs:__imp_RtlInitUnicodeString
0x18006e1c9  nop     dword ptr [rax+rax+00h]
0x18006e1ce  lea     r9, [rsp+4B0h+AuditParameters]; AuditParameters
0x18006e1d3  mov     [rsp+4B0h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006e1db  xor     r8d, r8d; UserSid
0x18006e1de  lea     rdx, [rsp+4B0h+DestinationString]; SourceName
0x18006e1e3  xor     ecx, ecx; Flags
0x18006e1e5  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006e1ec  nop     dword ptr [rax+rax+00h]
0x18006e1f1  mov     ebx, eax
0x18006e1f3  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x18006e1f8  call    cs:__imp_SeReleaseSubjectContext
0x18006e1ff  nop     dword ptr [rax+rax+00h]
0x18006e204  mov     eax, ebx
0x18006e206  mov     rcx, [rbp+3B0h+var_20]
0x18006e20d  xor     rcx, rsp; StackCookie
0x18006e210  call    __security_check_cookie
0x18006e215  mov     rbx, [rsp+4B0h+arg_0]
0x18006e21d  add     rsp, 4A0h
0x18006e224  pop     rdi
0x18006e225  pop     rsi
0x18006e226  pop     rbp
0x18006e227  retn
```
