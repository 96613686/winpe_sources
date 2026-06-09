# CfgAdtReportFunctionPropertyModification

- ea: `0x18006e968`
- end: `0x18006ece8`
- name: `CfgAdtReportFunctionPropertyModification`
- size: `896`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006c9b4`

## callees

- `0x180018e40`
- `0x18006e968`
- `0x18006f4e0`
- `0x18006f544`
- `0x18006f628`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006eb92`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006ebf1`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006ec5c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006eb92`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006ebf1`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006ec5c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006ecaf`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006ecaf`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006ea16`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006ea16`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006ec7e`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006ec7e`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006eac5`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006eac5`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ea4c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ea8c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006eaef`
- `ntoskrnl!SeSetAuditParameter` at `0x18006eb19`
- `ntoskrnl!SeSetAuditParameter` at `0x18006eb49`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ebae`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ec0d`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ec3a`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ea4c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ea8c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006eaef`
- `ntoskrnl!SeSetAuditParameter` at `0x18006eb19`
- `ntoskrnl!SeSetAuditParameter` at `0x18006eb49`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ebae`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ec0d`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ec3a`

## string_xrefs

- `0x18006ec50`: `Security`

## pseudocode

```c
__int64 CfgAdtReportFunctionPropertyModification(
        unsigned __int16 a1,
        int a2,
        __int64 *a3,
        ULONG a4,
        PVOID a5,
        PVOID a6,
        __int64 a7,
        unsigned __int16 a8,
        __int64 a9,
        unsigned __int16 a10,
        ...)
{
  NTSTATUS appended; // ebx
  ULONG v14; // r8d
  __int64 *v15; // r9
  char v16; // si
  char v17; // di
  int Data; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING String; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v22; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING SourceName; // [rsp+68h] [rbp-98h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+78h] [rbp-88h] BYREF
  struct _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+A0h] [rbp-60h] BYREF
  char v26; // [rsp+4C0h] [rbp+3C0h] BYREF
  va_list va; // [rsp+580h] [rbp+480h] BYREF

  va_start(va, a10);
  Data = a2;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  SourceName = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  DestinationString = 0;
  v22 = 0;
  String = 0;
  appended = CfgAdtpInitializeParameters(&AuditParameters, a1, 5070);
  if ( appended >= 0 )
  {
    SeCaptureSubjectContext(&SubjectContext);
    appended = CfgAdtpAppendSecuritySubjectInfo(&AuditParameters);
    if ( appended >= 0 )
    {
      appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeMessage, AuditParameters.ParameterCount, &Data);
      if ( appended >= 0 )
      {
        v14 = ++AuditParameters.ParameterCount;
        if ( !a3 || (v15 = a3, !*(_WORD *)a3) )
          v15 = &qword_1800AA3B0;
        appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v14, v15);
        if ( appended >= 0 )
        {
          ++AuditParameters.ParameterCount;
          String.Buffer = (PWSTR)&v26;
          *(_DWORD *)&String.Length = 0x200000;
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
                             SeAdtParmTypeString,
                             ++AuditParameters.ParameterCount,
                             a6);
                if ( appended >= 0 )
                {
                  ++AuditParameters.ParameterCount;
                  v16 = 0;
                  if ( (int)CfgAdtpFormatPropertyBlock(a7, a8, &DestinationString) < 0 )
                  {
                    v17 = 0;
                    RtlInitUnicodeString(&DestinationString, L"-");
                  }
                  else
                  {
                    v17 = 1;
                  }
                  appended = SeSetAuditParameter(
                               &AuditParameters,
                               SeAdtParmTypeString,
                               AuditParameters.ParameterCount,
                               &DestinationString);
                  if ( appended >= 0 )
                  {
                    ++AuditParameters.ParameterCount;
                    if ( (int)CfgAdtpFormatPropertyBlock(a9, a10, &v22) < 0 )
                      RtlInitUnicodeString(&v22, L"-");
                    else
                      v16 = 1;
                    appended = SeSetAuditParameter(
                                 &AuditParameters,
                                 SeAdtParmTypeString,
                                 AuditParameters.ParameterCount,
                                 &v22);
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
                        RtlInitUnicodeString(&SourceName, L"Security");
                        appended = SeReportSecurityEventWithSubCategory(0, &SourceName, 0, &AuditParameters, 0x91u);
                      }
                    }
                  }
                  if ( v17 )
                    BCryptFree(DestinationString.Buffer);
                  if ( v16 )
                    BCryptFree(v22.Buffer);
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
0x18006e968  mov     [rsp-8+arg_0], rbx
0x18006e96d  push    rbp
0x18006e96e  push    rsi
0x18006e96f  push    rdi
0x18006e970  push    r12
0x18006e972  push    r13
0x18006e974  push    r14
0x18006e976  push    r15
0x18006e978  lea     rbp, [rsp-3F0h]
0x18006e980  sub     rsp, 4F0h
0x18006e987  mov     rax, cs:__security_cookie
0x18006e98e  xor     rax, rsp
0x18006e991  mov     [rbp+420h+var_40], rax
0x18006e998  mov     r14, [rbp+420h+arg_20]
0x18006e99f  mov     rdi, r8
0x18006e9a2  mov     r15, [rbp+420h+arg_28]
0x18006e9a9  movzx   ebx, cx
0x18006e9ac  mov     r12, [rbp+420h+arg_30]
0x18006e9b3  lea     rcx, [rbp+420h+AuditParameters]; void *
0x18006e9b7  mov     r13, [rbp+420h+arg_40]
0x18006e9be  mov     r8d, 418h; Size
0x18006e9c4  mov     [rsp+520h+Data], edx
0x18006e9c8  mov     esi, r9d
0x18006e9cb  xor     edx, edx; Val
0x18006e9cd  call    memset
0x18006e9d2  xorps   xmm0, xmm0
0x18006e9d5  lea     rcx, [rbp+420h+AuditParameters]
0x18006e9d9  xorps   xmm1, xmm1
0x18006e9dc  mov     r8d, 13CEh
0x18006e9e2  movzx   edx, bx
0x18006e9e5  movups  xmmword ptr [rsp+520h+SourceName.Length], xmm0
0x18006e9ea  movups  xmmword ptr [rsp+520h+SubjectContext.ClientToken], xmm1
0x18006e9ef  movups  xmmword ptr [rbp+420h+SubjectContext.PrimaryToken], xmm1
0x18006e9f3  movups  xmmword ptr [rsp+520h+DestinationString.Length], xmm0
0x18006e9f8  movups  xmmword ptr [rsp+520h+var_4C8.Length], xmm1
0x18006e9fd  movups  xmmword ptr [rsp+520h+String.Length], xmm0
0x18006ea02  call    CfgAdtpInitializeParameters
0x18006ea07  mov     ebx, eax
0x18006ea09  test    eax, eax
0x18006ea0b  js      loc_18006ECBB
0x18006ea11  lea     rcx, [rsp+520h+SubjectContext]; SubjectContext
0x18006ea16  call    cs:__imp_SeCaptureSubjectContext
0x18006ea1d  nop     dword ptr [rax+rax+00h]
0x18006ea22  lea     rdx, [rsp+520h+SubjectContext]
0x18006ea27  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006ea2b  call    CfgAdtpAppendSecuritySubjectInfo
0x18006ea30  mov     ebx, eax
0x18006ea32  test    eax, eax
0x18006ea34  js      loc_18006ECAA
0x18006ea3a  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]; Index
0x18006ea3e  lea     r9, [rsp+520h+Data]; Data
0x18006ea43  mov     edx, 15h; Type
0x18006ea48  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006ea4c  call    cs:__imp_SeSetAuditParameter
0x18006ea53  nop     dword ptr [rax+rax+00h]
0x18006ea58  mov     ebx, eax
0x18006ea5a  xor     eax, eax
0x18006ea5c  test    ebx, ebx
0x18006ea5e  js      loc_18006ECAA
0x18006ea64  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]
0x18006ea68  lea     ecx, [rax+1]
0x18006ea6b  add     r8d, ecx; Index
0x18006ea6e  mov     [rbp+420h+AuditParameters.ParameterCount], r8d
0x18006ea72  test    rdi, rdi
0x18006ea75  jz      short loc_18006EA7F
0x18006ea77  mov     r9, rdi
0x18006ea7a  cmp     [rdi], ax
0x18006ea7d  jnz     short loc_18006EA86
0x18006ea7f  lea     r9, qword_1800AA3B0; Data
0x18006ea86  mov     edx, ecx; Type
0x18006ea88  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006ea8c  call    cs:__imp_SeSetAuditParameter
0x18006ea93  nop     dword ptr [rax+rax+00h]
0x18006ea98  mov     ebx, eax
0x18006ea9a  test    eax, eax
0x18006ea9c  js      loc_18006ECAA
0x18006eaa2  inc     [rbp+420h+AuditParameters.ParameterCount]
0x18006eaa5  lea     rax, [rbp+420h+var_60]
0x18006eaac  lea     r8, [rsp+520h+String]; String
0x18006eab1  mov     [rsp+520h+String.Buffer], rax
0x18006eab6  mov     edx, 0Ah; Base
0x18006eabb  mov     dword ptr [rsp+520h+String.Length], 200000h
0x18006eac3  mov     ecx, esi; Value
0x18006eac5  call    cs:__imp_RtlIntegerToUnicodeString
0x18006eacc  nop     dword ptr [rax+rax+00h]
0x18006ead1  mov     ebx, eax
0x18006ead3  test    eax, eax
0x18006ead5  js      loc_18006ECAA
0x18006eadb  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]; Index
0x18006eadf  lea     r9, [rsp+520h+String]; Data
0x18006eae4  mov     esi, 1
0x18006eae9  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006eaed  mov     edx, esi; Type
0x18006eaef  call    cs:__imp_SeSetAuditParameter
0x18006eaf6  nop     dword ptr [rax+rax+00h]
0x18006eafb  mov     ebx, eax
0x18006eafd  test    eax, eax
0x18006eaff  js      loc_18006ECAA
0x18006eb05  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]
0x18006eb09  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006eb0d  add     r8d, esi; Index
0x18006eb10  mov     r9, r14; Data
0x18006eb13  mov     edx, esi; Type
0x18006eb15  mov     [rbp+420h+AuditParameters.ParameterCount], r8d
0x18006eb19  call    cs:__imp_SeSetAuditParameter
0x18006eb20  nop     dword ptr [rax+rax+00h]
0x18006eb25  xor     r14d, r14d
0x18006eb28  mov     ebx, eax
0x18006eb2a  test    eax, eax
0x18006eb2c  js      loc_18006ECAA
0x18006eb32  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]
0x18006eb36  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006eb3a  add     r8d, esi; Index
0x18006eb3d  mov     r9, r15; Data
0x18006eb40  mov     edx, esi; Type
0x18006eb42  mov     [rbp+420h+AuditParameters.ParameterCount], r8d
0x18006eb46  mov     r15d, esi
0x18006eb49  call    cs:__imp_SeSetAuditParameter
0x18006eb50  nop     dword ptr [rax+rax+00h]
0x18006eb55  mov     ebx, eax
0x18006eb57  test    eax, eax
0x18006eb59  js      loc_18006ECAA
0x18006eb5f  movzx   edx, [rbp+420h+arg_38]
0x18006eb66  lea     r8, [rsp+520h+DestinationString]
0x18006eb6b  add     [rbp+420h+AuditParameters.ParameterCount], r15d
0x18006eb6f  mov     rcx, r12
0x18006eb72  mov     sil, r14b
0x18006eb75  call    CfgAdtpFormatPropertyBlock
0x18006eb7a  test    eax, eax
0x18006eb7c  js      short loc_18006EB83
0x18006eb7e  mov     dil, r15b
0x18006eb81  jmp     short loc_18006EB9E
0x18006eb83  lea     rdx, asc_1800B56C0; "-"
0x18006eb8a  mov     dil, r14b
0x18006eb8d  lea     rcx, [rsp+520h+DestinationString]; DestinationString
0x18006eb92  call    cs:__imp_RtlInitUnicodeString
0x18006eb99  nop     dword ptr [rax+rax+00h]
0x18006eb9e  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]; Index
0x18006eba2  lea     r9, [rsp+520h+DestinationString]; Data
0x18006eba7  mov     edx, r15d; Type
0x18006ebaa  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006ebae  call    cs:__imp_SeSetAuditParameter
0x18006ebb5  nop     dword ptr [rax+rax+00h]
0x18006ebba  mov     ebx, eax
0x18006ebbc  test    eax, eax
0x18006ebbe  js      loc_18006EC8C
0x18006ebc4  movzx   edx, [rbp+420h+arg_48]
0x18006ebcb  lea     r8, [rsp+520h+var_4C8]
0x18006ebd0  add     [rbp+420h+AuditParameters.ParameterCount], r15d
0x18006ebd4  mov     rcx, r13
0x18006ebd7  call    CfgAdtpFormatPropertyBlock
0x18006ebdc  test    eax, eax
0x18006ebde  js      short loc_18006EBE5
0x18006ebe0  mov     sil, r15b
0x18006ebe3  jmp     short loc_18006EBFD
0x18006ebe5  lea     rdx, asc_1800B56C0; "-"
0x18006ebec  lea     rcx, [rsp+520h+var_4C8]; DestinationString
0x18006ebf1  call    cs:__imp_RtlInitUnicodeString
0x18006ebf8  nop     dword ptr [rax+rax+00h]
0x18006ebfd  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]; Index
0x18006ec01  lea     r9, [rsp+520h+var_4C8]; Data
0x18006ec06  mov     edx, r15d; Type
0x18006ec09  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006ec0d  call    cs:__imp_SeSetAuditParameter
0x18006ec14  nop     dword ptr [rax+rax+00h]
0x18006ec19  mov     ebx, eax
0x18006ec1b  test    eax, eax
0x18006ec1d  js      short loc_18006EC8C
0x18006ec1f  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]
0x18006ec23  lea     r9, [rbp+420h+arg_50]; Data
0x18006ec2a  add     r8d, r15d; Index
0x18006ec2d  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006ec31  mov     edx, 0Ah; Type
0x18006ec36  mov     [rbp+420h+AuditParameters.ParameterCount], r8d
0x18006ec3a  call    cs:__imp_SeSetAuditParameter
0x18006ec41  nop     dword ptr [rax+rax+00h]
0x18006ec46  mov     ebx, eax
0x18006ec48  test    eax, eax
0x18006ec4a  js      short loc_18006EC8C
0x18006ec4c  add     [rbp+420h+AuditParameters.ParameterCount], r15d
0x18006ec50  lea     rdx, aSecurity; "Security"
0x18006ec57  lea     rcx, [rsp+520h+SourceName]; DestinationString
0x18006ec5c  call    cs:__imp_RtlInitUnicodeString
0x18006ec63  nop     dword ptr [rax+rax+00h]
0x18006ec68  lea     r9, [rbp+420h+AuditParameters]; AuditParameters
0x18006ec6c  mov     [rsp+520h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006ec74  xor     r8d, r8d; UserSid
0x18006ec77  lea     rdx, [rsp+520h+SourceName]; SourceName
0x18006ec7c  xor     ecx, ecx; Flags
0x18006ec7e  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006ec85  nop     dword ptr [rax+rax+00h]
0x18006ec8a  mov     ebx, eax
0x18006ec8c  test    dil, dil
0x18006ec8f  jz      short loc_18006EC9B
0x18006ec91  mov     rcx, [rsp+520h+DestinationString.Buffer]; P
0x18006ec96  call    BCryptFree
0x18006ec9b  test    sil, sil
0x18006ec9e  jz      short loc_18006ECAA
0x18006eca0  mov     rcx, [rsp+520h+var_4C8.Buffer]; P
0x18006eca5  call    BCryptFree
0x18006ecaa  lea     rcx, [rsp+520h+SubjectContext]; SubjectContext
0x18006ecaf  call    cs:__imp_SeReleaseSubjectContext
0x18006ecb6  nop     dword ptr [rax+rax+00h]
0x18006ecbb  mov     eax, ebx
0x18006ecbd  mov     rcx, [rbp+420h+var_40]
0x18006ecc4  xor     rcx, rsp; StackCookie
0x18006ecc7  call    __security_check_cookie
0x18006eccc  mov     rbx, [rsp+520h+arg_0]
0x18006ecd4  add     rsp, 4F0h
0x18006ecdb  pop     r15
0x18006ecdd  pop     r14
0x18006ecdf  pop     r13
0x18006ece1  pop     r12
0x18006ece3  pop     rdi
0x18006ece4  pop     rsi
0x18006ece5  pop     rbp
0x18006ece6  retn
```
