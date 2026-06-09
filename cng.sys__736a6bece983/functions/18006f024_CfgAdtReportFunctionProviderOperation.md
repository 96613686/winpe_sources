# CfgAdtReportFunctionProviderOperation

- ea: `0x18006f024`
- end: `0x18006f303`
- name: `CfgAdtReportFunctionProviderOperation`
- size: `735`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006a950`
- `0x18006c6a0`

## callees

- `0x18006f024`
- `0x18006f4e0`
- `0x18006f628`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006f295`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006f295`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006f2ca`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006f2ca`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006f0be`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006f0be`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006f2b7`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006f2b7`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006f170`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006f170`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f0f3`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f134`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f196`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f1c1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f1ec`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f21a`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f249`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f273`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f0f3`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f134`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f196`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f1c1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f1ec`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f21a`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f249`
- `ntoskrnl!SeSetAuditParameter` at `0x18006f273`

## string_xrefs

- `0x18006f289`: `Security`

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
          v11 = &qword_1800AA3B0;
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
0x18006f024  mov     [rsp-8+arg_0], rbx
0x18006f029  push    rbp
0x18006f02a  push    rsi
0x18006f02b  push    rdi
0x18006f02c  push    r12
0x18006f02e  push    r13
0x18006f030  push    r14
0x18006f032  push    r15
0x18006f034  lea     rbp, [rsp-3D0h]
0x18006f03c  sub     rsp, 4D0h
0x18006f043  mov     rax, cs:__security_cookie
0x18006f04a  xor     rax, rsp
0x18006f04d  mov     [rbp+400h+var_40], rax
0x18006f054  mov     r14, [rbp+400h+arg_20]
0x18006f05b  mov     rdi, r8
0x18006f05e  mov     r15, [rbp+400h+arg_28]
0x18006f065  movzx   ebx, cx
0x18006f068  mov     [rsp+500h+Data], edx
0x18006f06c  lea     rcx, [rbp+400h+AuditParameters]; void *
0x18006f070  xor     edx, edx; Val
0x18006f072  mov     r8d, 418h; Size
0x18006f078  mov     esi, r9d
0x18006f07b  call    memset
0x18006f080  xorps   xmm0, xmm0
0x18006f083  lea     rcx, [rbp+400h+AuditParameters]
0x18006f087  xorps   xmm1, xmm1
0x18006f08a  mov     r8d, 13CCh
0x18006f090  movzx   edx, bx
0x18006f093  movups  xmmword ptr [rsp+500h+DestinationString.Length], xmm0
0x18006f098  movups  xmmword ptr [rsp+500h+SubjectContext.ClientToken], xmm1
0x18006f09d  movups  xmmword ptr [rsp+500h+SubjectContext.PrimaryToken], xmm1
0x18006f0a2  movups  xmmword ptr [rsp+500h+String.Length], xmm0
0x18006f0a7  call    CfgAdtpInitializeParameters
0x18006f0ac  xor     r13d, r13d
0x18006f0af  mov     ebx, eax
0x18006f0b1  test    eax, eax
0x18006f0b3  js      loc_18006F2D6
0x18006f0b9  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x18006f0be  call    cs:__imp_SeCaptureSubjectContext
0x18006f0c5  nop     dword ptr [rax+rax+00h]
0x18006f0ca  lea     rdx, [rsp+500h+SubjectContext]
0x18006f0cf  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006f0d3  call    CfgAdtpAppendSecuritySubjectInfo
0x18006f0d8  mov     ebx, eax
0x18006f0da  test    eax, eax
0x18006f0dc  js      loc_18006F2C5
0x18006f0e2  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x18006f0e6  lea     r9, [rsp+500h+Data]; Data
0x18006f0eb  lea     edx, [r13+15h]; Type
0x18006f0ef  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006f0f3  call    cs:__imp_SeSetAuditParameter
0x18006f0fa  nop     dword ptr [rax+rax+00h]
0x18006f0ff  mov     ebx, eax
0x18006f101  test    eax, eax
0x18006f103  js      loc_18006F2C5
0x18006f109  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006f10d  lea     r12d, [r13+1]
0x18006f111  add     r8d, r12d; Index
0x18006f114  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006f118  test    rdi, rdi
0x18006f11b  jz      short loc_18006F126
0x18006f11d  mov     r9, rdi
0x18006f120  cmp     [rdi], r13w
0x18006f124  jnz     short loc_18006F12D
0x18006f126  lea     r9, qword_1800AA3B0; Data
0x18006f12d  mov     edx, r12d; Type
0x18006f130  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006f134  call    cs:__imp_SeSetAuditParameter
0x18006f13b  nop     dword ptr [rax+rax+00h]
0x18006f140  mov     ebx, eax
0x18006f142  test    eax, eax
0x18006f144  js      loc_18006F2C5
0x18006f14a  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x18006f14e  lea     rax, [rbp+400h+var_60]
0x18006f155  mov     edi, 0Ah
0x18006f15a  mov     dword ptr [rsp+500h+String.Length], 200000h
0x18006f162  mov     edx, edi; Base
0x18006f164  mov     [rsp+500h+String.Buffer], rax
0x18006f169  lea     r8, [rsp+500h+String]; String
0x18006f16e  mov     ecx, esi; Value
0x18006f170  call    cs:__imp_RtlIntegerToUnicodeString
0x18006f177  nop     dword ptr [rax+rax+00h]
0x18006f17c  mov     ebx, eax
0x18006f17e  test    eax, eax
0x18006f180  js      loc_18006F2C5
0x18006f186  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x18006f18a  lea     r9, [rsp+500h+String]; Data
0x18006f18f  mov     edx, r12d; Type
0x18006f192  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006f196  call    cs:__imp_SeSetAuditParameter
0x18006f19d  nop     dword ptr [rax+rax+00h]
0x18006f1a2  mov     ebx, eax
0x18006f1a4  test    eax, eax
0x18006f1a6  js      loc_18006F2C5
0x18006f1ac  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006f1b0  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006f1b4  add     r8d, r12d; Index
0x18006f1b7  mov     r9, r14; Data
0x18006f1ba  mov     edx, r12d; Type
0x18006f1bd  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006f1c1  call    cs:__imp_SeSetAuditParameter
0x18006f1c8  nop     dword ptr [rax+rax+00h]
0x18006f1cd  mov     ebx, eax
0x18006f1cf  test    eax, eax
0x18006f1d1  js      loc_18006F2C5
0x18006f1d7  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006f1db  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006f1df  add     r8d, r12d; Index
0x18006f1e2  mov     r9, r15; Data
0x18006f1e5  mov     edx, r12d; Type
0x18006f1e8  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006f1ec  call    cs:__imp_SeSetAuditParameter
0x18006f1f3  nop     dword ptr [rax+rax+00h]
0x18006f1f8  mov     ebx, eax
0x18006f1fa  test    eax, eax
0x18006f1fc  js      loc_18006F2C5
0x18006f202  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006f206  lea     r9, [rbp+400h+arg_30]; Data
0x18006f20d  add     r8d, r12d; Index
0x18006f210  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006f214  mov     edx, edi; Type
0x18006f216  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006f21a  call    cs:__imp_SeSetAuditParameter
0x18006f221  nop     dword ptr [rax+rax+00h]
0x18006f226  mov     ebx, eax
0x18006f228  test    eax, eax
0x18006f22a  js      loc_18006F2C5
0x18006f230  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006f234  lea     r9, [rbp+400h+arg_38]; Data
0x18006f23b  add     r8d, r12d; Index
0x18006f23e  lea     edx, [rdi+0Bh]; Type
0x18006f241  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006f245  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006f249  call    cs:__imp_SeSetAuditParameter
0x18006f250  nop     dword ptr [rax+rax+00h]
0x18006f255  mov     ebx, eax
0x18006f257  test    eax, eax
0x18006f259  js      short loc_18006F2C5
0x18006f25b  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006f25f  lea     r9, [rbp+400h+arg_40]; Data
0x18006f266  add     r8d, r12d; Index
0x18006f269  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006f26d  mov     edx, edi; Type
0x18006f26f  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006f273  call    cs:__imp_SeSetAuditParameter
0x18006f27a  nop     dword ptr [rax+rax+00h]
0x18006f27f  mov     ebx, eax
0x18006f281  test    eax, eax
0x18006f283  js      short loc_18006F2C5
0x18006f285  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x18006f289  lea     rdx, aSecurity; "Security"
0x18006f290  lea     rcx, [rsp+500h+DestinationString]; DestinationString
0x18006f295  call    cs:__imp_RtlInitUnicodeString
0x18006f29c  nop     dword ptr [rax+rax+00h]
0x18006f2a1  lea     r9, [rbp+400h+AuditParameters]; AuditParameters
0x18006f2a5  mov     [rsp+500h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006f2ad  xor     r8d, r8d; UserSid
0x18006f2b0  lea     rdx, [rsp+500h+DestinationString]; SourceName
0x18006f2b5  xor     ecx, ecx; Flags
0x18006f2b7  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006f2be  nop     dword ptr [rax+rax+00h]
0x18006f2c3  mov     ebx, eax
0x18006f2c5  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x18006f2ca  call    cs:__imp_SeReleaseSubjectContext
0x18006f2d1  nop     dword ptr [rax+rax+00h]
0x18006f2d6  mov     eax, ebx
0x18006f2d8  mov     rcx, [rbp+400h+var_40]
0x18006f2df  xor     rcx, rsp; StackCookie
0x18006f2e2  call    __security_check_cookie
0x18006f2e7  mov     rbx, [rsp+500h+arg_0]
0x18006f2ef  add     rsp, 4D0h
0x18006f2f6  pop     r15
0x18006f2f8  pop     r14
0x18006f2fa  pop     r13
0x18006f2fc  pop     r12
0x18006f2fe  pop     rdi
0x18006f2ff  pop     rsi
0x18006f300  pop     rbp
0x18006f301  retn
```
