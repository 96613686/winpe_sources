# CfgAdtReportFunctionProviderOperation

- ea: `0x18006e624`
- end: `0x18006e903`
- name: `CfgAdtReportFunctionProviderOperation`
- size: `735`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180069f50`
- `0x18006bca0`

## callees

- `0x18006e624`
- `0x18006eae0`
- `0x18006ec28`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006e895`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e895`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e8ca`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e8ca`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e6be`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e6be`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e8b7`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e8b7`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006e770`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006e770`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e6f3`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e734`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e796`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e7c1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e7ec`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e81a`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e849`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e873`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e6f3`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e734`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e796`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e7c1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e7ec`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e81a`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e849`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e873`

## string_xrefs

- `0x18006e889`: `Security`

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
          v11 = &qword_1800A83B0;
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
0x18006e624  mov     [rsp-8+arg_0], rbx
0x18006e629  push    rbp
0x18006e62a  push    rsi
0x18006e62b  push    rdi
0x18006e62c  push    r12
0x18006e62e  push    r13
0x18006e630  push    r14
0x18006e632  push    r15
0x18006e634  lea     rbp, [rsp-3D0h]
0x18006e63c  sub     rsp, 4D0h
0x18006e643  mov     rax, cs:__security_cookie
0x18006e64a  xor     rax, rsp
0x18006e64d  mov     [rbp+400h+var_40], rax
0x18006e654  mov     r14, [rbp+400h+arg_20]
0x18006e65b  mov     rdi, r8
0x18006e65e  mov     r15, [rbp+400h+arg_28]
0x18006e665  movzx   ebx, cx
0x18006e668  mov     [rsp+500h+Data], edx
0x18006e66c  lea     rcx, [rbp+400h+AuditParameters]; void *
0x18006e670  xor     edx, edx; Val
0x18006e672  mov     r8d, 418h; Size
0x18006e678  mov     esi, r9d
0x18006e67b  call    memset
0x18006e680  xorps   xmm0, xmm0
0x18006e683  lea     rcx, [rbp+400h+AuditParameters]
0x18006e687  xorps   xmm1, xmm1
0x18006e68a  mov     r8d, 13CCh
0x18006e690  movzx   edx, bx
0x18006e693  movups  xmmword ptr [rsp+500h+DestinationString.Length], xmm0
0x18006e698  movups  xmmword ptr [rsp+500h+SubjectContext.ClientToken], xmm1
0x18006e69d  movups  xmmword ptr [rsp+500h+SubjectContext.PrimaryToken], xmm1
0x18006e6a2  movups  xmmword ptr [rsp+500h+String.Length], xmm0
0x18006e6a7  call    CfgAdtpInitializeParameters
0x18006e6ac  xor     r13d, r13d
0x18006e6af  mov     ebx, eax
0x18006e6b1  test    eax, eax
0x18006e6b3  js      loc_18006E8D6
0x18006e6b9  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x18006e6be  call    cs:__imp_SeCaptureSubjectContext
0x18006e6c5  nop     dword ptr [rax+rax+00h]
0x18006e6ca  lea     rdx, [rsp+500h+SubjectContext]
0x18006e6cf  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e6d3  call    CfgAdtpAppendSecuritySubjectInfo
0x18006e6d8  mov     ebx, eax
0x18006e6da  test    eax, eax
0x18006e6dc  js      loc_18006E8C5
0x18006e6e2  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x18006e6e6  lea     r9, [rsp+500h+Data]; Data
0x18006e6eb  lea     edx, [r13+15h]; Type
0x18006e6ef  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e6f3  call    cs:__imp_SeSetAuditParameter
0x18006e6fa  nop     dword ptr [rax+rax+00h]
0x18006e6ff  mov     ebx, eax
0x18006e701  test    eax, eax
0x18006e703  js      loc_18006E8C5
0x18006e709  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e70d  lea     r12d, [r13+1]
0x18006e711  add     r8d, r12d; Index
0x18006e714  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e718  test    rdi, rdi
0x18006e71b  jz      short loc_18006E726
0x18006e71d  mov     r9, rdi
0x18006e720  cmp     [rdi], r13w
0x18006e724  jnz     short loc_18006E72D
0x18006e726  lea     r9, qword_1800A83B0; Data
0x18006e72d  mov     edx, r12d; Type
0x18006e730  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e734  call    cs:__imp_SeSetAuditParameter
0x18006e73b  nop     dword ptr [rax+rax+00h]
0x18006e740  mov     ebx, eax
0x18006e742  test    eax, eax
0x18006e744  js      loc_18006E8C5
0x18006e74a  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x18006e74e  lea     rax, [rbp+400h+var_60]
0x18006e755  mov     edi, 0Ah
0x18006e75a  mov     dword ptr [rsp+500h+String.Length], 200000h
0x18006e762  mov     edx, edi; Base
0x18006e764  mov     [rsp+500h+String.Buffer], rax
0x18006e769  lea     r8, [rsp+500h+String]; String
0x18006e76e  mov     ecx, esi; Value
0x18006e770  call    cs:__imp_RtlIntegerToUnicodeString
0x18006e777  nop     dword ptr [rax+rax+00h]
0x18006e77c  mov     ebx, eax
0x18006e77e  test    eax, eax
0x18006e780  js      loc_18006E8C5
0x18006e786  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x18006e78a  lea     r9, [rsp+500h+String]; Data
0x18006e78f  mov     edx, r12d; Type
0x18006e792  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e796  call    cs:__imp_SeSetAuditParameter
0x18006e79d  nop     dword ptr [rax+rax+00h]
0x18006e7a2  mov     ebx, eax
0x18006e7a4  test    eax, eax
0x18006e7a6  js      loc_18006E8C5
0x18006e7ac  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e7b0  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e7b4  add     r8d, r12d; Index
0x18006e7b7  mov     r9, r14; Data
0x18006e7ba  mov     edx, r12d; Type
0x18006e7bd  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e7c1  call    cs:__imp_SeSetAuditParameter
0x18006e7c8  nop     dword ptr [rax+rax+00h]
0x18006e7cd  mov     ebx, eax
0x18006e7cf  test    eax, eax
0x18006e7d1  js      loc_18006E8C5
0x18006e7d7  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e7db  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e7df  add     r8d, r12d; Index
0x18006e7e2  mov     r9, r15; Data
0x18006e7e5  mov     edx, r12d; Type
0x18006e7e8  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e7ec  call    cs:__imp_SeSetAuditParameter
0x18006e7f3  nop     dword ptr [rax+rax+00h]
0x18006e7f8  mov     ebx, eax
0x18006e7fa  test    eax, eax
0x18006e7fc  js      loc_18006E8C5
0x18006e802  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e806  lea     r9, [rbp+400h+arg_30]; Data
0x18006e80d  add     r8d, r12d; Index
0x18006e810  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e814  mov     edx, edi; Type
0x18006e816  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e81a  call    cs:__imp_SeSetAuditParameter
0x18006e821  nop     dword ptr [rax+rax+00h]
0x18006e826  mov     ebx, eax
0x18006e828  test    eax, eax
0x18006e82a  js      loc_18006E8C5
0x18006e830  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e834  lea     r9, [rbp+400h+arg_38]; Data
0x18006e83b  add     r8d, r12d; Index
0x18006e83e  lea     edx, [rdi+0Bh]; Type
0x18006e841  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e845  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e849  call    cs:__imp_SeSetAuditParameter
0x18006e850  nop     dword ptr [rax+rax+00h]
0x18006e855  mov     ebx, eax
0x18006e857  test    eax, eax
0x18006e859  js      short loc_18006E8C5
0x18006e85b  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e85f  lea     r9, [rbp+400h+arg_40]; Data
0x18006e866  add     r8d, r12d; Index
0x18006e869  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e86d  mov     edx, edi; Type
0x18006e86f  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e873  call    cs:__imp_SeSetAuditParameter
0x18006e87a  nop     dword ptr [rax+rax+00h]
0x18006e87f  mov     ebx, eax
0x18006e881  test    eax, eax
0x18006e883  js      short loc_18006E8C5
0x18006e885  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x18006e889  lea     rdx, aSecurity; "Security"
0x18006e890  lea     rcx, [rsp+500h+DestinationString]; DestinationString
0x18006e895  call    cs:__imp_RtlInitUnicodeString
0x18006e89c  nop     dword ptr [rax+rax+00h]
0x18006e8a1  lea     r9, [rbp+400h+AuditParameters]; AuditParameters
0x18006e8a5  mov     [rsp+500h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006e8ad  xor     r8d, r8d; UserSid
0x18006e8b0  lea     rdx, [rsp+500h+DestinationString]; SourceName
0x18006e8b5  xor     ecx, ecx; Flags
0x18006e8b7  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006e8be  nop     dword ptr [rax+rax+00h]
0x18006e8c3  mov     ebx, eax
0x18006e8c5  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x18006e8ca  call    cs:__imp_SeReleaseSubjectContext
0x18006e8d1  nop     dword ptr [rax+rax+00h]
0x18006e8d6  mov     eax, ebx
0x18006e8d8  mov     rcx, [rbp+400h+var_40]
0x18006e8df  xor     rcx, rsp; StackCookie
0x18006e8e2  call    __security_check_cookie
0x18006e8e7  mov     rbx, [rsp+500h+arg_0]
0x18006e8ef  add     rsp, 4D0h
0x18006e8f6  pop     r15
0x18006e8f8  pop     r14
0x18006e8fa  pop     r13
0x18006e8fc  pop     r12
0x18006e8fe  pop     rdi
0x18006e8ff  pop     rsi
0x18006e900  pop     rbp
0x18006e901  retn
```
