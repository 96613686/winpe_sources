# CfgAdtReportFunctionOperation

- ea: `0x180077e60`
- end: `0x1800780ff`
- name: `CfgAdtReportFunctionOperation`
- size: `671`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180073ec0`
- `0x180075c0c`

## callees

- `0x180077e60`
- `0x180078c80`
- `0x180078dc8`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18007809a`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007809a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1800780cf`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1800780cf`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180077eee`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180077eee`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x1800780bc`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x1800780bc`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180077fa0`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180077fa0`
- `ntoskrnl!SeSetAuditParameter` at `0x180077f23`
- `ntoskrnl!SeSetAuditParameter` at `0x180077f64`
- `ntoskrnl!SeSetAuditParameter` at `0x180077fc6`
- `ntoskrnl!SeSetAuditParameter` at `0x180077ff1`
- `ntoskrnl!SeSetAuditParameter` at `0x18007801f`
- `ntoskrnl!SeSetAuditParameter` at `0x18007804e`
- `ntoskrnl!SeSetAuditParameter` at `0x180078078`
- `ntoskrnl!SeSetAuditParameter` at `0x180077f23`
- `ntoskrnl!SeSetAuditParameter` at `0x180077f64`
- `ntoskrnl!SeSetAuditParameter` at `0x180077fc6`
- `ntoskrnl!SeSetAuditParameter` at `0x180077ff1`
- `ntoskrnl!SeSetAuditParameter` at `0x18007801f`
- `ntoskrnl!SeSetAuditParameter` at `0x18007804e`
- `ntoskrnl!SeSetAuditParameter` at `0x180078078`

## string_xrefs

- `0x18007808e`: `Security`

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
          v10 = &qword_1800AF9A0;
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
0x180077e60  push    rbp
0x180077e62  push    rbx
0x180077e63  push    rsi
0x180077e64  push    rdi
0x180077e65  push    r12
0x180077e67  push    r14
0x180077e69  push    r15
0x180077e6b  lea     rbp, [rsp-3D0h]
0x180077e73  sub     rsp, 4D0h
0x180077e7a  mov     rax, cs:__security_cookie
0x180077e81  xor     rax, rsp
0x180077e84  mov     [rbp+400h+var_40], rax
0x180077e8b  mov     r14, [rbp+400h+arg_20]
0x180077e92  mov     rdi, r8
0x180077e95  movzx   ebx, cx
0x180077e98  mov     [rsp+500h+Data], edx
0x180077e9c  xor     edx, edx; Val
0x180077e9e  lea     rcx, [rbp+400h+AuditParameters]; void *
0x180077ea2  mov     r8d, 418h; Size
0x180077ea8  mov     esi, r9d
0x180077eab  call    memset
0x180077eb0  xorps   xmm0, xmm0
0x180077eb3  lea     rcx, [rbp+400h+AuditParameters]
0x180077eb7  xorps   xmm1, xmm1
0x180077eba  mov     r8d, 13CAh
0x180077ec0  movzx   edx, bx
0x180077ec3  movups  xmmword ptr [rsp+500h+DestinationString.Length], xmm0
0x180077ec8  movups  xmmword ptr [rsp+500h+SubjectContext.ClientToken], xmm1
0x180077ecd  movups  xmmword ptr [rsp+500h+SubjectContext.PrimaryToken], xmm1
0x180077ed2  movups  xmmword ptr [rsp+500h+String.Length], xmm0
0x180077ed7  call    CfgAdtpInitializeParameters
0x180077edc  xor     r15d, r15d
0x180077edf  mov     ebx, eax
0x180077ee1  test    eax, eax
0x180077ee3  js      loc_1800780DB
0x180077ee9  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x180077eee  call    cs:__imp_SeCaptureSubjectContext
0x180077ef5  nop     dword ptr [rax+rax+00h]
0x180077efa  lea     rdx, [rsp+500h+SubjectContext]
0x180077eff  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180077f03  call    CfgAdtpAppendSecuritySubjectInfo
0x180077f08  mov     ebx, eax
0x180077f0a  test    eax, eax
0x180077f0c  js      loc_1800780CA
0x180077f12  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x180077f16  lea     r9, [rsp+500h+Data]; Data
0x180077f1b  lea     edx, [r15+15h]; Type
0x180077f1f  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180077f23  call    cs:__imp_SeSetAuditParameter
0x180077f2a  nop     dword ptr [rax+rax+00h]
0x180077f2f  mov     ebx, eax
0x180077f31  test    eax, eax
0x180077f33  js      loc_1800780CA
0x180077f39  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x180077f3d  lea     r12d, [r15+1]
0x180077f41  add     r8d, r12d; Index
0x180077f44  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x180077f48  test    rdi, rdi
0x180077f4b  jz      short loc_180077F56
0x180077f4d  mov     r9, rdi
0x180077f50  cmp     [rdi], r15w
0x180077f54  jnz     short loc_180077F5D
0x180077f56  lea     r9, qword_1800AF9A0; Data
0x180077f5d  mov     edx, r12d; Type
0x180077f60  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180077f64  call    cs:__imp_SeSetAuditParameter
0x180077f6b  nop     dword ptr [rax+rax+00h]
0x180077f70  mov     ebx, eax
0x180077f72  test    eax, eax
0x180077f74  js      loc_1800780CA
0x180077f7a  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x180077f7e  lea     rax, [rbp+400h+var_60]
0x180077f85  mov     edi, 0Ah
0x180077f8a  mov     dword ptr [rsp+500h+String.Length], 200000h
0x180077f92  mov     edx, edi; Base
0x180077f94  mov     [rsp+500h+String.Buffer], rax
0x180077f99  lea     r8, [rsp+500h+String]; String
0x180077f9e  mov     ecx, esi; Value
0x180077fa0  call    cs:__imp_RtlIntegerToUnicodeString
0x180077fa7  nop     dword ptr [rax+rax+00h]
0x180077fac  mov     ebx, eax
0x180077fae  test    eax, eax
0x180077fb0  js      loc_1800780CA
0x180077fb6  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x180077fba  lea     r9, [rsp+500h+String]; Data
0x180077fbf  mov     edx, r12d; Type
0x180077fc2  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180077fc6  call    cs:__imp_SeSetAuditParameter
0x180077fcd  nop     dword ptr [rax+rax+00h]
0x180077fd2  mov     ebx, eax
0x180077fd4  test    eax, eax
0x180077fd6  js      loc_1800780CA
0x180077fdc  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x180077fe0  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180077fe4  add     r8d, r12d; Index
0x180077fe7  mov     r9, r14; Data
0x180077fea  mov     edx, r12d; Type
0x180077fed  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x180077ff1  call    cs:__imp_SeSetAuditParameter
0x180077ff8  nop     dword ptr [rax+rax+00h]
0x180077ffd  mov     ebx, eax
0x180077fff  test    eax, eax
0x180078001  js      loc_1800780CA
0x180078007  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18007800b  lea     r9, [rbp+400h+arg_28]; Data
0x180078012  add     r8d, r12d; Index
0x180078015  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180078019  mov     edx, edi; Type
0x18007801b  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18007801f  call    cs:__imp_SeSetAuditParameter
0x180078026  nop     dword ptr [rax+rax+00h]
0x18007802b  mov     ebx, eax
0x18007802d  test    eax, eax
0x18007802f  js      loc_1800780CA
0x180078035  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x180078039  lea     r9, [rbp+400h+arg_30]; Data
0x180078040  add     r8d, r12d; Index
0x180078043  lea     edx, [rdi+0Bh]; Type
0x180078046  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18007804a  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18007804e  call    cs:__imp_SeSetAuditParameter
0x180078055  nop     dword ptr [rax+rax+00h]
0x18007805a  mov     ebx, eax
0x18007805c  test    eax, eax
0x18007805e  js      short loc_1800780CA
0x180078060  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x180078064  lea     r9, [rbp+400h+arg_38]; Data
0x18007806b  add     r8d, r12d; Index
0x18007806e  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180078072  mov     edx, edi; Type
0x180078074  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x180078078  call    cs:__imp_SeSetAuditParameter
0x18007807f  nop     dword ptr [rax+rax+00h]
0x180078084  mov     ebx, eax
0x180078086  test    eax, eax
0x180078088  js      short loc_1800780CA
0x18007808a  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x18007808e  lea     rdx, aSecurity; "Security"
0x180078095  lea     rcx, [rsp+500h+DestinationString]; DestinationString
0x18007809a  call    cs:__imp_RtlInitUnicodeString
0x1800780a1  nop     dword ptr [rax+rax+00h]
0x1800780a6  lea     r9, [rbp+400h+AuditParameters]; AuditParameters
0x1800780aa  mov     [rsp+500h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x1800780b2  xor     r8d, r8d; UserSid
0x1800780b5  lea     rdx, [rsp+500h+DestinationString]; SourceName
0x1800780ba  xor     ecx, ecx; Flags
0x1800780bc  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x1800780c3  nop     dword ptr [rax+rax+00h]
0x1800780c8  mov     ebx, eax
0x1800780ca  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x1800780cf  call    cs:__imp_SeReleaseSubjectContext
0x1800780d6  nop     dword ptr [rax+rax+00h]
0x1800780db  mov     eax, ebx
0x1800780dd  mov     rcx, [rbp+400h+var_40]
0x1800780e4  xor     rcx, rsp; StackCookie
0x1800780e7  call    __security_check_cookie
0x1800780ec  add     rsp, 4D0h
0x1800780f3  pop     r15
0x1800780f5  pop     r14
0x1800780f7  pop     r12
0x1800780f9  pop     rdi
0x1800780fa  pop     rsi
0x1800780fb  pop     rbx
0x1800780fc  pop     rbp
0x1800780fd  retn
```
