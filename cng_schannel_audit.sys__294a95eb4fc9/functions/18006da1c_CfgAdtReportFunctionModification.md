# CfgAdtReportFunctionModification

- ea: `0x18006da1c`
- end: `0x18006dcba`
- name: `CfgAdtReportFunctionModification`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006a480`

## callees

- `0x18006da1c`
- `0x18006eae0`
- `0x18006ec28`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006dc55`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006dc55`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006dc8a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006dc8a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006daaa`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006daaa`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006dc77`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006dc77`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006db5c`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006db5c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006dadf`
- `ntoskrnl!SeSetAuditParameter` at `0x18006db20`
- `ntoskrnl!SeSetAuditParameter` at `0x18006db82`
- `ntoskrnl!SeSetAuditParameter` at `0x18006dbad`
- `ntoskrnl!SeSetAuditParameter` at `0x18006dbdb`
- `ntoskrnl!SeSetAuditParameter` at `0x18006dc09`
- `ntoskrnl!SeSetAuditParameter` at `0x18006dc33`
- `ntoskrnl!SeSetAuditParameter` at `0x18006dadf`
- `ntoskrnl!SeSetAuditParameter` at `0x18006db20`
- `ntoskrnl!SeSetAuditParameter` at `0x18006db82`
- `ntoskrnl!SeSetAuditParameter` at `0x18006dbad`
- `ntoskrnl!SeSetAuditParameter` at `0x18006dbdb`
- `ntoskrnl!SeSetAuditParameter` at `0x18006dc09`
- `ntoskrnl!SeSetAuditParameter` at `0x18006dc33`

## string_xrefs

- `0x18006dc49`: `Security`

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
          v10 = &qword_1800A83B0;
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
0x18006da1c  push    rbp
0x18006da1e  push    rbx
0x18006da1f  push    rsi
0x18006da20  push    rdi
0x18006da21  push    r12
0x18006da23  push    r14
0x18006da25  push    r15
0x18006da27  lea     rbp, [rsp-3D0h]
0x18006da2f  sub     rsp, 4D0h
0x18006da36  mov     rax, cs:__security_cookie
0x18006da3d  xor     rax, rsp
0x18006da40  mov     [rbp+400h+var_40], rax
0x18006da47  mov     r14, [rbp+400h+arg_20]
0x18006da4e  mov     rdi, r8
0x18006da51  movzx   ebx, cx
0x18006da54  mov     [rsp+500h+Data], edx
0x18006da58  xor     edx, edx; Val
0x18006da5a  lea     rcx, [rbp+400h+AuditParameters]; void *
0x18006da5e  mov     r8d, 418h; Size
0x18006da64  mov     esi, r9d
0x18006da67  call    memset
0x18006da6c  xorps   xmm0, xmm0
0x18006da6f  lea     rcx, [rbp+400h+AuditParameters]
0x18006da73  xorps   xmm1, xmm1
0x18006da76  mov     r8d, 13CBh
0x18006da7c  movzx   edx, bx
0x18006da7f  movups  xmmword ptr [rsp+500h+DestinationString.Length], xmm0
0x18006da84  movups  xmmword ptr [rsp+500h+SubjectContext.ClientToken], xmm1
0x18006da89  movups  xmmword ptr [rsp+500h+SubjectContext.PrimaryToken], xmm1
0x18006da8e  movups  xmmword ptr [rsp+500h+String.Length], xmm0
0x18006da93  call    CfgAdtpInitializeParameters
0x18006da98  xor     r15d, r15d
0x18006da9b  mov     ebx, eax
0x18006da9d  test    eax, eax
0x18006da9f  js      loc_18006DC96
0x18006daa5  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x18006daaa  call    cs:__imp_SeCaptureSubjectContext
0x18006dab1  nop     dword ptr [rax+rax+00h]
0x18006dab6  lea     rdx, [rsp+500h+SubjectContext]
0x18006dabb  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006dabf  call    CfgAdtpAppendSecuritySubjectInfo
0x18006dac4  mov     ebx, eax
0x18006dac6  test    eax, eax
0x18006dac8  js      loc_18006DC85
0x18006dace  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x18006dad2  lea     r9, [rsp+500h+Data]; Data
0x18006dad7  lea     edx, [r15+15h]; Type
0x18006dadb  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006dadf  call    cs:__imp_SeSetAuditParameter
0x18006dae6  nop     dword ptr [rax+rax+00h]
0x18006daeb  mov     ebx, eax
0x18006daed  test    eax, eax
0x18006daef  js      loc_18006DC85
0x18006daf5  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006daf9  lea     r12d, [r15+1]
0x18006dafd  add     r8d, r12d; Index
0x18006db00  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006db04  test    rdi, rdi
0x18006db07  jz      short loc_18006DB12
0x18006db09  mov     r9, rdi
0x18006db0c  cmp     [rdi], r15w
0x18006db10  jnz     short loc_18006DB19
0x18006db12  lea     r9, qword_1800A83B0; Data
0x18006db19  mov     edx, r12d; Type
0x18006db1c  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006db20  call    cs:__imp_SeSetAuditParameter
0x18006db27  nop     dword ptr [rax+rax+00h]
0x18006db2c  mov     ebx, eax
0x18006db2e  test    eax, eax
0x18006db30  js      loc_18006DC85
0x18006db36  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x18006db3a  lea     rax, [rbp+400h+var_60]
0x18006db41  mov     edi, 0Ah
0x18006db46  mov     dword ptr [rsp+500h+String.Length], 200000h
0x18006db4e  mov     edx, edi; Base
0x18006db50  mov     [rsp+500h+String.Buffer], rax
0x18006db55  lea     r8, [rsp+500h+String]; String
0x18006db5a  mov     ecx, esi; Value
0x18006db5c  call    cs:__imp_RtlIntegerToUnicodeString
0x18006db63  nop     dword ptr [rax+rax+00h]
0x18006db68  mov     ebx, eax
0x18006db6a  test    eax, eax
0x18006db6c  js      loc_18006DC85
0x18006db72  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x18006db76  lea     r9, [rsp+500h+String]; Data
0x18006db7b  mov     edx, r12d; Type
0x18006db7e  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006db82  call    cs:__imp_SeSetAuditParameter
0x18006db89  nop     dword ptr [rax+rax+00h]
0x18006db8e  mov     ebx, eax
0x18006db90  test    eax, eax
0x18006db92  js      loc_18006DC85
0x18006db98  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006db9c  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006dba0  add     r8d, r12d; Index
0x18006dba3  mov     r9, r14; Data
0x18006dba6  mov     edx, r12d; Type
0x18006dba9  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006dbad  call    cs:__imp_SeSetAuditParameter
0x18006dbb4  nop     dword ptr [rax+rax+00h]
0x18006dbb9  mov     ebx, eax
0x18006dbbb  test    eax, eax
0x18006dbbd  js      loc_18006DC85
0x18006dbc3  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006dbc7  lea     r9, [rbp+400h+arg_28]; Data
0x18006dbce  add     r8d, r12d; Index
0x18006dbd1  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006dbd5  mov     edx, edi; Type
0x18006dbd7  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006dbdb  call    cs:__imp_SeSetAuditParameter
0x18006dbe2  nop     dword ptr [rax+rax+00h]
0x18006dbe7  mov     ebx, eax
0x18006dbe9  test    eax, eax
0x18006dbeb  js      loc_18006DC85
0x18006dbf1  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006dbf5  lea     r9, [rbp+400h+arg_30]; Data
0x18006dbfc  add     r8d, r12d; Index
0x18006dbff  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006dc03  mov     edx, edi; Type
0x18006dc05  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006dc09  call    cs:__imp_SeSetAuditParameter
0x18006dc10  nop     dword ptr [rax+rax+00h]
0x18006dc15  mov     ebx, eax
0x18006dc17  test    eax, eax
0x18006dc19  js      short loc_18006DC85
0x18006dc1b  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006dc1f  lea     r9, [rbp+400h+arg_38]; Data
0x18006dc26  add     r8d, r12d; Index
0x18006dc29  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006dc2d  mov     edx, edi; Type
0x18006dc2f  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006dc33  call    cs:__imp_SeSetAuditParameter
0x18006dc3a  nop     dword ptr [rax+rax+00h]
0x18006dc3f  mov     ebx, eax
0x18006dc41  test    eax, eax
0x18006dc43  js      short loc_18006DC85
0x18006dc45  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x18006dc49  lea     rdx, aSecurity; "Security"
0x18006dc50  lea     rcx, [rsp+500h+DestinationString]; DestinationString
0x18006dc55  call    cs:__imp_RtlInitUnicodeString
0x18006dc5c  nop     dword ptr [rax+rax+00h]
0x18006dc61  lea     r9, [rbp+400h+AuditParameters]; AuditParameters
0x18006dc65  mov     [rsp+500h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006dc6d  xor     r8d, r8d; UserSid
0x18006dc70  lea     rdx, [rsp+500h+DestinationString]; SourceName
0x18006dc75  xor     ecx, ecx; Flags
0x18006dc77  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006dc7e  nop     dword ptr [rax+rax+00h]
0x18006dc83  mov     ebx, eax
0x18006dc85  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x18006dc8a  call    cs:__imp_SeReleaseSubjectContext
0x18006dc91  nop     dword ptr [rax+rax+00h]
0x18006dc96  mov     eax, ebx
0x18006dc98  mov     rcx, [rbp+400h+var_40]
0x18006dc9f  xor     rcx, rsp; StackCookie
0x18006dca2  call    __security_check_cookie
0x18006dca7  add     rsp, 4D0h
0x18006dcae  pop     r15
0x18006dcb0  pop     r14
0x18006dcb2  pop     r12
0x18006dcb4  pop     rdi
0x18006dcb5  pop     rsi
0x18006dcb6  pop     rbx
0x18006dcb7  pop     rbp
0x18006dcb8  retn
```
