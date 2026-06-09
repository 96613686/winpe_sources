# CfgAdtReportFunctionProviderOperation

- ea: `0x1800787c4`
- end: `0x180078aa3`
- name: `CfgAdtReportFunctionProviderOperation`
- size: `735`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800740f0`
- `0x180075e40`

## callees

- `0x1800787c4`
- `0x180078c80`
- `0x180078dc8`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180078a35`
- `ntoskrnl!RtlInitUnicodeString` at `0x180078a35`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180078a6a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180078a6a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18007885e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18007885e`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x180078a57`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x180078a57`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180078910`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180078910`
- `ntoskrnl!SeSetAuditParameter` at `0x180078893`
- `ntoskrnl!SeSetAuditParameter` at `0x1800788d4`
- `ntoskrnl!SeSetAuditParameter` at `0x180078936`
- `ntoskrnl!SeSetAuditParameter` at `0x180078961`
- `ntoskrnl!SeSetAuditParameter` at `0x18007898c`
- `ntoskrnl!SeSetAuditParameter` at `0x1800789ba`
- `ntoskrnl!SeSetAuditParameter` at `0x1800789e9`
- `ntoskrnl!SeSetAuditParameter` at `0x180078a13`
- `ntoskrnl!SeSetAuditParameter` at `0x180078893`
- `ntoskrnl!SeSetAuditParameter` at `0x1800788d4`
- `ntoskrnl!SeSetAuditParameter` at `0x180078936`
- `ntoskrnl!SeSetAuditParameter` at `0x180078961`
- `ntoskrnl!SeSetAuditParameter` at `0x18007898c`
- `ntoskrnl!SeSetAuditParameter` at `0x1800789ba`
- `ntoskrnl!SeSetAuditParameter` at `0x1800789e9`
- `ntoskrnl!SeSetAuditParameter` at `0x180078a13`

## string_xrefs

- `0x180078a29`: `Security`

## pseudocode

```c
__int64 CfgAdtReportFunctionProviderOperation(
        unsigned __int16 a1,
        int a2,
        __int64 *a3,
        ULONG a4,
        PVOID a5,
        PVOID a6,
        ...)
{
  NTSTATUS appended; // ebx
  ULONG v10; // r8d
  __int64 *v11; // r9
  int Data; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING String; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+58h] [rbp-A8h] BYREF
  struct _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+80h] [rbp-80h] BYREF
  char v18; // [rsp+4A0h] [rbp+3A0h] BYREF
  __int64 v19; // [rsp+540h] [rbp+440h] BYREF
  va_list va; // [rsp+540h] [rbp+440h]
  __int64 v21; // [rsp+548h] [rbp+448h] BYREF
  va_list va1; // [rsp+548h] [rbp+448h]
  va_list va2; // [rsp+550h] [rbp+450h] BYREF

  va_start(va2, a6);
  va_start(va1, a6);
  va_start(va, a6);
  v19 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v21 = va_arg(va2, _QWORD);
  Data = a2;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  DestinationString = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  String = 0;
  appended = CfgAdtpInitializeParameters(&AuditParameters, a1, 5068);
  if ( appended >= 0 )
  {
    SeCaptureSubjectContext(&SubjectContext);
    appended = CfgAdtpAppendSecuritySubjectInfo(&AuditParameters);
    if ( appended >= 0 )
    {
      appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeMessage, AuditParameters.ParameterCount, &Data);
      if ( appended >= 0 )
      {
        v10 = ++AuditParameters.ParameterCount;
        if ( !a3 || (v11 = a3, !*(_WORD *)a3) )
          v11 = &qword_1800AF9A0;
        appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v10, v11);
        if ( appended >= 0 )
        {
          ++AuditParameters.ParameterCount;
          *(_DWORD *)&String.Length = 0x200000;
          String.Buffer = (PWSTR)&v18;
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
                        appended = SeReportSecurityEventWithSubCategory(
                                     0,
                                     &DestinationString,
                                     0,
                                     &AuditParameters,
                                     0x91u);
                      }
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
0x1800787c4  mov     [rsp-8+arg_0], rbx
0x1800787c9  push    rbp
0x1800787ca  push    rsi
0x1800787cb  push    rdi
0x1800787cc  push    r12
0x1800787ce  push    r13
0x1800787d0  push    r14
0x1800787d2  push    r15
0x1800787d4  lea     rbp, [rsp-3D0h]
0x1800787dc  sub     rsp, 4D0h
0x1800787e3  mov     rax, cs:__security_cookie
0x1800787ea  xor     rax, rsp
0x1800787ed  mov     [rbp+400h+var_40], rax
0x1800787f4  mov     r14, [rbp+400h+arg_20]
0x1800787fb  mov     rdi, r8
0x1800787fe  mov     r15, [rbp+400h+arg_28]
0x180078805  movzx   ebx, cx
0x180078808  mov     [rsp+500h+Data], edx
0x18007880c  lea     rcx, [rbp+400h+AuditParameters]; void *
0x180078810  xor     edx, edx; Val
0x180078812  mov     r8d, 418h; Size
0x180078818  mov     esi, r9d
0x18007881b  call    memset
0x180078820  xorps   xmm0, xmm0
0x180078823  lea     rcx, [rbp+400h+AuditParameters]
0x180078827  xorps   xmm1, xmm1
0x18007882a  mov     r8d, 13CCh
0x180078830  movzx   edx, bx
0x180078833  movups  xmmword ptr [rsp+500h+DestinationString.Length], xmm0
0x180078838  movups  xmmword ptr [rsp+500h+SubjectContext.ClientToken], xmm1
0x18007883d  movups  xmmword ptr [rsp+500h+SubjectContext.PrimaryToken], xmm1
0x180078842  movups  xmmword ptr [rsp+500h+String.Length], xmm0
0x180078847  call    CfgAdtpInitializeParameters
0x18007884c  xor     r13d, r13d
0x18007884f  mov     ebx, eax
0x180078851  test    eax, eax
0x180078853  js      loc_180078A76
0x180078859  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x18007885e  call    cs:__imp_SeCaptureSubjectContext
0x180078865  nop     dword ptr [rax+rax+00h]
0x18007886a  lea     rdx, [rsp+500h+SubjectContext]
0x18007886f  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180078873  call    CfgAdtpAppendSecuritySubjectInfo
0x180078878  mov     ebx, eax
0x18007887a  test    eax, eax
0x18007887c  js      loc_180078A65
0x180078882  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x180078886  lea     r9, [rsp+500h+Data]; Data
0x18007888b  lea     edx, [r13+15h]; Type
0x18007888f  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180078893  call    cs:__imp_SeSetAuditParameter
0x18007889a  nop     dword ptr [rax+rax+00h]
0x18007889f  mov     ebx, eax
0x1800788a1  test    eax, eax
0x1800788a3  js      loc_180078A65
0x1800788a9  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x1800788ad  lea     r12d, [r13+1]
0x1800788b1  add     r8d, r12d; Index
0x1800788b4  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x1800788b8  test    rdi, rdi
0x1800788bb  jz      short loc_1800788C6
0x1800788bd  mov     r9, rdi
0x1800788c0  cmp     [rdi], r13w
0x1800788c4  jnz     short loc_1800788CD
0x1800788c6  lea     r9, qword_1800AF9A0; Data
0x1800788cd  mov     edx, r12d; Type
0x1800788d0  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x1800788d4  call    cs:__imp_SeSetAuditParameter
0x1800788db  nop     dword ptr [rax+rax+00h]
0x1800788e0  mov     ebx, eax
0x1800788e2  test    eax, eax
0x1800788e4  js      loc_180078A65
0x1800788ea  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x1800788ee  lea     rax, [rbp+400h+var_60]
0x1800788f5  mov     edi, 0Ah
0x1800788fa  mov     dword ptr [rsp+500h+String.Length], 200000h
0x180078902  mov     edx, edi; Base
0x180078904  mov     [rsp+500h+String.Buffer], rax
0x180078909  lea     r8, [rsp+500h+String]; String
0x18007890e  mov     ecx, esi; Value
0x180078910  call    cs:__imp_RtlIntegerToUnicodeString
0x180078917  nop     dword ptr [rax+rax+00h]
0x18007891c  mov     ebx, eax
0x18007891e  test    eax, eax
0x180078920  js      loc_180078A65
0x180078926  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x18007892a  lea     r9, [rsp+500h+String]; Data
0x18007892f  mov     edx, r12d; Type
0x180078932  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180078936  call    cs:__imp_SeSetAuditParameter
0x18007893d  nop     dword ptr [rax+rax+00h]
0x180078942  mov     ebx, eax
0x180078944  test    eax, eax
0x180078946  js      loc_180078A65
0x18007894c  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x180078950  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180078954  add     r8d, r12d; Index
0x180078957  mov     r9, r14; Data
0x18007895a  mov     edx, r12d; Type
0x18007895d  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x180078961  call    cs:__imp_SeSetAuditParameter
0x180078968  nop     dword ptr [rax+rax+00h]
0x18007896d  mov     ebx, eax
0x18007896f  test    eax, eax
0x180078971  js      loc_180078A65
0x180078977  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18007897b  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18007897f  add     r8d, r12d; Index
0x180078982  mov     r9, r15; Data
0x180078985  mov     edx, r12d; Type
0x180078988  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18007898c  call    cs:__imp_SeSetAuditParameter
0x180078993  nop     dword ptr [rax+rax+00h]
0x180078998  mov     ebx, eax
0x18007899a  test    eax, eax
0x18007899c  js      loc_180078A65
0x1800789a2  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x1800789a6  lea     r9, [rbp+400h+arg_30]; Data
0x1800789ad  add     r8d, r12d; Index
0x1800789b0  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x1800789b4  mov     edx, edi; Type
0x1800789b6  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x1800789ba  call    cs:__imp_SeSetAuditParameter
0x1800789c1  nop     dword ptr [rax+rax+00h]
0x1800789c6  mov     ebx, eax
0x1800789c8  test    eax, eax
0x1800789ca  js      loc_180078A65
0x1800789d0  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x1800789d4  lea     r9, [rbp+400h+arg_38]; Data
0x1800789db  add     r8d, r12d; Index
0x1800789de  lea     edx, [rdi+0Bh]; Type
0x1800789e1  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x1800789e5  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x1800789e9  call    cs:__imp_SeSetAuditParameter
0x1800789f0  nop     dword ptr [rax+rax+00h]
0x1800789f5  mov     ebx, eax
0x1800789f7  test    eax, eax
0x1800789f9  js      short loc_180078A65
0x1800789fb  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x1800789ff  lea     r9, [rbp+400h+arg_40]; Data
0x180078a06  add     r8d, r12d; Index
0x180078a09  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180078a0d  mov     edx, edi; Type
0x180078a0f  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x180078a13  call    cs:__imp_SeSetAuditParameter
0x180078a1a  nop     dword ptr [rax+rax+00h]
0x180078a1f  mov     ebx, eax
0x180078a21  test    eax, eax
0x180078a23  js      short loc_180078A65
0x180078a25  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x180078a29  lea     rdx, aSecurity; "Security"
0x180078a30  lea     rcx, [rsp+500h+DestinationString]; DestinationString
0x180078a35  call    cs:__imp_RtlInitUnicodeString
0x180078a3c  nop     dword ptr [rax+rax+00h]
0x180078a41  lea     r9, [rbp+400h+AuditParameters]; AuditParameters
0x180078a45  mov     [rsp+500h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x180078a4d  xor     r8d, r8d; UserSid
0x180078a50  lea     rdx, [rsp+500h+DestinationString]; SourceName
0x180078a55  xor     ecx, ecx; Flags
0x180078a57  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x180078a5e  nop     dword ptr [rax+rax+00h]
0x180078a63  mov     ebx, eax
0x180078a65  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x180078a6a  call    cs:__imp_SeReleaseSubjectContext
0x180078a71  nop     dword ptr [rax+rax+00h]
0x180078a76  mov     eax, ebx
0x180078a78  mov     rcx, [rbp+400h+var_40]
0x180078a7f  xor     rcx, rsp; StackCookie
0x180078a82  call    __security_check_cookie
0x180078a87  mov     rbx, [rsp+500h+arg_0]
0x180078a8f  add     rsp, 4D0h
0x180078a96  pop     r15
0x180078a98  pop     r14
0x180078a9a  pop     r13
0x180078a9c  pop     r12
0x180078a9e  pop     rdi
0x180078a9f  pop     rsi
0x180078aa0  pop     rbp
0x180078aa1  retn
```
