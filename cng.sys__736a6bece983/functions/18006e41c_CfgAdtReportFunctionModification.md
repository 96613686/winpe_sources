# CfgAdtReportFunctionModification

- ea: `0x18006e41c`
- end: `0x18006e6ba`
- name: `CfgAdtReportFunctionModification`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006ae80`

## callees

- `0x18006e41c`
- `0x18006f4e0`
- `0x18006f628`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006e655`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e655`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e68a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e68a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e4aa`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e4aa`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e677`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e677`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006e55c`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006e55c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e4df`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e520`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e582`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e5ad`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e5db`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e609`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e633`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e4df`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e520`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e582`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e5ad`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e5db`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e609`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e633`

## string_xrefs

- `0x18006e649`: `Security`

## pseudocode

```c
__int64 CfgAdtReportFunctionModification(unsigned __int16 a1, int a2, __int64 *a3, ULONG a4, PVOID a5, ...)
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
  appended = CfgAdtpInitializeParameters(&AuditParameters, a1, 5067);
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
          v10 = &qword_1800AA3B0;
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
                               SeAdtParmTypeHexUlong,
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
0x18006e41c  push    rbp
0x18006e41e  push    rbx
0x18006e41f  push    rsi
0x18006e420  push    rdi
0x18006e421  push    r12
0x18006e423  push    r14
0x18006e425  push    r15
0x18006e427  lea     rbp, [rsp-3D0h]
0x18006e42f  sub     rsp, 4D0h
0x18006e436  mov     rax, cs:__security_cookie
0x18006e43d  xor     rax, rsp
0x18006e440  mov     [rbp+400h+var_40], rax
0x18006e447  mov     r14, [rbp+400h+arg_20]
0x18006e44e  mov     rdi, r8
0x18006e451  movzx   ebx, cx
0x18006e454  mov     [rsp+500h+Data], edx
0x18006e458  xor     edx, edx; Val
0x18006e45a  lea     rcx, [rbp+400h+AuditParameters]; void *
0x18006e45e  mov     r8d, 418h; Size
0x18006e464  mov     esi, r9d
0x18006e467  call    memset
0x18006e46c  xorps   xmm0, xmm0
0x18006e46f  lea     rcx, [rbp+400h+AuditParameters]
0x18006e473  xorps   xmm1, xmm1
0x18006e476  mov     r8d, 13CBh
0x18006e47c  movzx   edx, bx
0x18006e47f  movups  xmmword ptr [rsp+500h+DestinationString.Length], xmm0
0x18006e484  movups  xmmword ptr [rsp+500h+SubjectContext.ClientToken], xmm1
0x18006e489  movups  xmmword ptr [rsp+500h+SubjectContext.PrimaryToken], xmm1
0x18006e48e  movups  xmmword ptr [rsp+500h+String.Length], xmm0
0x18006e493  call    CfgAdtpInitializeParameters
0x18006e498  xor     r15d, r15d
0x18006e49b  mov     ebx, eax
0x18006e49d  test    eax, eax
0x18006e49f  js      loc_18006E696
0x18006e4a5  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x18006e4aa  call    cs:__imp_SeCaptureSubjectContext
0x18006e4b1  nop     dword ptr [rax+rax+00h]
0x18006e4b6  lea     rdx, [rsp+500h+SubjectContext]
0x18006e4bb  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e4bf  call    CfgAdtpAppendSecuritySubjectInfo
0x18006e4c4  mov     ebx, eax
0x18006e4c6  test    eax, eax
0x18006e4c8  js      loc_18006E685
0x18006e4ce  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x18006e4d2  lea     r9, [rsp+500h+Data]; Data
0x18006e4d7  lea     edx, [r15+15h]; Type
0x18006e4db  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e4df  call    cs:__imp_SeSetAuditParameter
0x18006e4e6  nop     dword ptr [rax+rax+00h]
0x18006e4eb  mov     ebx, eax
0x18006e4ed  test    eax, eax
0x18006e4ef  js      loc_18006E685
0x18006e4f5  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e4f9  lea     r12d, [r15+1]
0x18006e4fd  add     r8d, r12d; Index
0x18006e500  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e504  test    rdi, rdi
0x18006e507  jz      short loc_18006E512
0x18006e509  mov     r9, rdi
0x18006e50c  cmp     [rdi], r15w
0x18006e510  jnz     short loc_18006E519
0x18006e512  lea     r9, qword_1800AA3B0; Data
0x18006e519  mov     edx, r12d; Type
0x18006e51c  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e520  call    cs:__imp_SeSetAuditParameter
0x18006e527  nop     dword ptr [rax+rax+00h]
0x18006e52c  mov     ebx, eax
0x18006e52e  test    eax, eax
0x18006e530  js      loc_18006E685
0x18006e536  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x18006e53a  lea     rax, [rbp+400h+var_60]
0x18006e541  mov     edi, 0Ah
0x18006e546  mov     dword ptr [rsp+500h+String.Length], 200000h
0x18006e54e  mov     edx, edi; Base
0x18006e550  mov     [rsp+500h+String.Buffer], rax
0x18006e555  lea     r8, [rsp+500h+String]; String
0x18006e55a  mov     ecx, esi; Value
0x18006e55c  call    cs:__imp_RtlIntegerToUnicodeString
0x18006e563  nop     dword ptr [rax+rax+00h]
0x18006e568  mov     ebx, eax
0x18006e56a  test    eax, eax
0x18006e56c  js      loc_18006E685
0x18006e572  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x18006e576  lea     r9, [rsp+500h+String]; Data
0x18006e57b  mov     edx, r12d; Type
0x18006e57e  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e582  call    cs:__imp_SeSetAuditParameter
0x18006e589  nop     dword ptr [rax+rax+00h]
0x18006e58e  mov     ebx, eax
0x18006e590  test    eax, eax
0x18006e592  js      loc_18006E685
0x18006e598  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e59c  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e5a0  add     r8d, r12d; Index
0x18006e5a3  mov     r9, r14; Data
0x18006e5a6  mov     edx, r12d; Type
0x18006e5a9  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e5ad  call    cs:__imp_SeSetAuditParameter
0x18006e5b4  nop     dword ptr [rax+rax+00h]
0x18006e5b9  mov     ebx, eax
0x18006e5bb  test    eax, eax
0x18006e5bd  js      loc_18006E685
0x18006e5c3  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e5c7  lea     r9, [rbp+400h+arg_28]; Data
0x18006e5ce  add     r8d, r12d; Index
0x18006e5d1  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e5d5  mov     edx, edi; Type
0x18006e5d7  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e5db  call    cs:__imp_SeSetAuditParameter
0x18006e5e2  nop     dword ptr [rax+rax+00h]
0x18006e5e7  mov     ebx, eax
0x18006e5e9  test    eax, eax
0x18006e5eb  js      loc_18006E685
0x18006e5f1  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e5f5  lea     r9, [rbp+400h+arg_30]; Data
0x18006e5fc  add     r8d, r12d; Index
0x18006e5ff  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e603  mov     edx, edi; Type
0x18006e605  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e609  call    cs:__imp_SeSetAuditParameter
0x18006e610  nop     dword ptr [rax+rax+00h]
0x18006e615  mov     ebx, eax
0x18006e617  test    eax, eax
0x18006e619  js      short loc_18006E685
0x18006e61b  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006e61f  lea     r9, [rbp+400h+arg_38]; Data
0x18006e626  add     r8d, r12d; Index
0x18006e629  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006e62d  mov     edx, edi; Type
0x18006e62f  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006e633  call    cs:__imp_SeSetAuditParameter
0x18006e63a  nop     dword ptr [rax+rax+00h]
0x18006e63f  mov     ebx, eax
0x18006e641  test    eax, eax
0x18006e643  js      short loc_18006E685
0x18006e645  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x18006e649  lea     rdx, aSecurity; "Security"
0x18006e650  lea     rcx, [rsp+500h+DestinationString]; DestinationString
0x18006e655  call    cs:__imp_RtlInitUnicodeString
0x18006e65c  nop     dword ptr [rax+rax+00h]
0x18006e661  lea     r9, [rbp+400h+AuditParameters]; AuditParameters
0x18006e665  mov     [rsp+500h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006e66d  xor     r8d, r8d; UserSid
0x18006e670  lea     rdx, [rsp+500h+DestinationString]; SourceName
0x18006e675  xor     ecx, ecx; Flags
0x18006e677  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006e67e  nop     dword ptr [rax+rax+00h]
0x18006e683  mov     ebx, eax
0x18006e685  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x18006e68a  call    cs:__imp_SeReleaseSubjectContext
0x18006e691  nop     dword ptr [rax+rax+00h]
0x18006e696  mov     eax, ebx
0x18006e698  mov     rcx, [rbp+400h+var_40]
0x18006e69f  xor     rcx, rsp; StackCookie
0x18006e6a2  call    __security_check_cookie
0x18006e6a7  add     rsp, 4D0h
0x18006e6ae  pop     r15
0x18006e6b0  pop     r14
0x18006e6b2  pop     r12
0x18006e6b4  pop     rdi
0x18006e6b5  pop     rsi
0x18006e6b6  pop     rbx
0x18006e6b7  pop     rbp
0x18006e6b8  retn
```
