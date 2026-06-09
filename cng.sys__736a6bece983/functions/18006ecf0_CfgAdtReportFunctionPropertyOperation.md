# CfgAdtReportFunctionPropertyOperation

- ea: `0x18006ecf0`
- end: `0x18006f01c`
- name: `CfgAdtReportFunctionPropertyOperation`
- size: `812`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006c9b4`

## callees

- `0x180018e40`
- `0x18006ecf0`
- `0x18006f4e0`
- `0x18006f544`
- `0x18006f628`
- `0x18009f650`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006ef36`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006ef9f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006ef36`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006ef9f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006efe3`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006efe3`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006ed96`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006ed96`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006efc1`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006efc1`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006ee44`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006ee44`
- `ntoskrnl!SeSetAuditParameter` at `0x18006edcb`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ee0b`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ee6e`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ee98`
- `ntoskrnl!SeSetAuditParameter` at `0x18006eec2`
- `ntoskrnl!SeSetAuditParameter` at `0x18006eef1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ef51`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ef7e`
- `ntoskrnl!SeSetAuditParameter` at `0x18006edcb`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ee0b`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ee6e`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ee98`
- `ntoskrnl!SeSetAuditParameter` at `0x18006eec2`
- `ntoskrnl!SeSetAuditParameter` at `0x18006eef1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ef51`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ef7e`

## string_xrefs

- `0x18006ef93`: `Security`

## pseudocode

```c
__int64 CfgAdtReportFunctionPropertyOperation(
        unsigned __int16 a1,
        int a2,
        __int64 *a3,
        ULONG a4,
        PVOID a5,
        PVOID a6,
        ...)
{
  __int64 v8; // r14
  NTSTATUS appended; // ebx
  ULONG v11; // r8d
  __int64 *v12; // r9
  char v13; // di
  int Data; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING String; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING SourceName; // [rsp+58h] [rbp-A8h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+68h] [rbp-98h] BYREF
  struct _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+90h] [rbp-70h] BYREF
  char v21; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int64 v22; // [rsp+550h] [rbp+450h] BYREF
  va_list va; // [rsp+550h] [rbp+450h]
  __int64 v24; // [rsp+558h] [rbp+458h]
  __int64 v25; // [rsp+560h] [rbp+460h]
  va_list va1; // [rsp+568h] [rbp+468h] BYREF

  va_start(va1, a6);
  va_start(va, a6);
  v22 = va_arg(va1, _QWORD);
  v24 = va_arg(va1, _QWORD);
  v25 = va_arg(va1, _QWORD);
  v8 = v24;
  Data = a2;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  SourceName = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  DestinationString = 0;
  String = 0;
  appended = CfgAdtpInitializeParameters(&AuditParameters, a1, 5069);
  if ( appended >= 0 )
  {
    SeCaptureSubjectContext(&SubjectContext);
    appended = CfgAdtpAppendSecuritySubjectInfo(&AuditParameters);
    if ( appended >= 0 )
    {
      appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeMessage, AuditParameters.ParameterCount, &Data);
      if ( appended >= 0 )
      {
        v11 = ++AuditParameters.ParameterCount;
        if ( !a3 || (v12 = a3, !*(_WORD *)a3) )
          v12 = &qword_1800AA3B0;
        appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v11, v12);
        if ( appended >= 0 )
        {
          ++AuditParameters.ParameterCount;
          String.Buffer = (PWSTR)&v21;
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
                  appended = SeSetAuditParameter(
                               &AuditParameters,
                               SeAdtParmTypeMessage,
                               ++AuditParameters.ParameterCount,
                               va);
                  if ( appended >= 0 )
                  {
                    ++AuditParameters.ParameterCount;
                    if ( (int)CfgAdtpFormatPropertyBlock(v8, (unsigned __int16)v25, &DestinationString) < 0 )
                    {
                      v13 = 0;
                      RtlInitUnicodeString(&DestinationString, L"-");
                    }
                    else
                    {
                      v13 = 1;
                    }
                    appended = SeSetAuditParameter(
                                 &AuditParameters,
                                 SeAdtParmTypeString,
                                 AuditParameters.ParameterCount,
                                 &DestinationString);
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
                        RtlInitUnicodeString(&SourceName, L"Security");
                        appended = SeReportSecurityEventWithSubCategory(0, &SourceName, 0, &AuditParameters, 0x91u);
                      }
                    }
                    if ( v13 )
                      BCryptFree(DestinationString.Buffer);
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
0x18006ecf0  mov     [rsp-8+arg_0], rbx
0x18006ecf5  push    rbp
0x18006ecf6  push    rsi
0x18006ecf7  push    rdi
0x18006ecf8  push    r12
0x18006ecfa  push    r13
0x18006ecfc  push    r14
0x18006ecfe  push    r15
0x18006ed00  lea     rbp, [rsp-3E0h]
0x18006ed08  sub     rsp, 4E0h
0x18006ed0f  mov     rax, cs:__security_cookie
0x18006ed16  xor     rax, rsp
0x18006ed19  mov     [rbp+410h+var_40], rax
0x18006ed20  mov     r15, [rbp+410h+arg_20]
0x18006ed27  mov     rdi, r8
0x18006ed2a  mov     r12, [rbp+410h+arg_28]
0x18006ed31  movzx   ebx, cx
0x18006ed34  mov     r14, [rbp+410h+arg_38]
0x18006ed3b  lea     rcx, [rbp+410h+AuditParameters]; void *
0x18006ed3f  mov     [rsp+510h+Data], edx
0x18006ed43  mov     r8d, 418h; Size
0x18006ed49  xor     edx, edx; Val
0x18006ed4b  mov     esi, r9d
0x18006ed4e  call    memset
0x18006ed53  xorps   xmm1, xmm1
0x18006ed56  lea     rcx, [rbp+410h+AuditParameters]
0x18006ed5a  xorps   xmm0, xmm0
0x18006ed5d  mov     r8d, 13CDh
0x18006ed63  movzx   edx, bx
0x18006ed66  movups  xmmword ptr [rsp+510h+SourceName.Length], xmm0
0x18006ed6b  movups  xmmword ptr [rsp+510h+SubjectContext.ClientToken], xmm1
0x18006ed70  movups  xmmword ptr [rsp+510h+SubjectContext.PrimaryToken], xmm1
0x18006ed75  movups  xmmword ptr [rsp+510h+DestinationString.Length], xmm0
0x18006ed7a  movups  xmmword ptr [rsp+510h+String.Length], xmm1
0x18006ed7f  call    CfgAdtpInitializeParameters
0x18006ed84  xor     r13d, r13d
0x18006ed87  mov     ebx, eax
0x18006ed89  test    eax, eax
0x18006ed8b  js      loc_18006EFEF
0x18006ed91  lea     rcx, [rsp+510h+SubjectContext]; SubjectContext
0x18006ed96  call    cs:__imp_SeCaptureSubjectContext
0x18006ed9d  nop     dword ptr [rax+rax+00h]
0x18006eda2  lea     rdx, [rsp+510h+SubjectContext]
0x18006eda7  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006edab  call    CfgAdtpAppendSecuritySubjectInfo
0x18006edb0  mov     ebx, eax
0x18006edb2  test    eax, eax
0x18006edb4  js      loc_18006EFDE
0x18006edba  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]; Index
0x18006edbe  lea     r9, [rsp+510h+Data]; Data
0x18006edc3  lea     edx, [r13+15h]; Type
0x18006edc7  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006edcb  call    cs:__imp_SeSetAuditParameter
0x18006edd2  nop     dword ptr [rax+rax+00h]
0x18006edd7  mov     ebx, eax
0x18006edd9  test    eax, eax
0x18006eddb  js      loc_18006EFDE
0x18006ede1  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x18006ede5  lea     eax, [r13+1]
0x18006ede9  add     r8d, eax; Index
0x18006edec  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x18006edf0  test    rdi, rdi
0x18006edf3  jz      short loc_18006EDFE
0x18006edf5  mov     r9, rdi
0x18006edf8  cmp     [rdi], r13w
0x18006edfc  jnz     short loc_18006EE05
0x18006edfe  lea     r9, qword_1800AA3B0; Data
0x18006ee05  mov     edx, eax; Type
0x18006ee07  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006ee0b  call    cs:__imp_SeSetAuditParameter
0x18006ee12  nop     dword ptr [rax+rax+00h]
0x18006ee17  mov     ebx, eax
0x18006ee19  test    eax, eax
0x18006ee1b  js      loc_18006EFDE
0x18006ee21  inc     [rbp+410h+AuditParameters.ParameterCount]
0x18006ee24  lea     rax, [rbp+410h+var_60]
0x18006ee2b  lea     r8, [rsp+510h+String]; String
0x18006ee30  mov     [rsp+510h+String.Buffer], rax
0x18006ee35  mov     edx, 0Ah; Base
0x18006ee3a  mov     dword ptr [rsp+510h+String.Length], 200000h
0x18006ee42  mov     ecx, esi; Value
0x18006ee44  call    cs:__imp_RtlIntegerToUnicodeString
0x18006ee4b  nop     dword ptr [rax+rax+00h]
0x18006ee50  mov     ebx, eax
0x18006ee52  test    eax, eax
0x18006ee54  js      loc_18006EFDE
0x18006ee5a  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]; Index
0x18006ee5e  lea     r9, [rsp+510h+String]; Data
0x18006ee63  mov     esi, 1
0x18006ee68  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006ee6c  mov     edx, esi; Type
0x18006ee6e  call    cs:__imp_SeSetAuditParameter
0x18006ee75  nop     dword ptr [rax+rax+00h]
0x18006ee7a  mov     ebx, eax
0x18006ee7c  test    eax, eax
0x18006ee7e  js      loc_18006EFDE
0x18006ee84  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x18006ee88  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006ee8c  add     r8d, esi; Index
0x18006ee8f  mov     r9, r15; Data
0x18006ee92  mov     edx, esi; Type
0x18006ee94  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x18006ee98  call    cs:__imp_SeSetAuditParameter
0x18006ee9f  nop     dword ptr [rax+rax+00h]
0x18006eea4  mov     ebx, eax
0x18006eea6  test    eax, eax
0x18006eea8  js      loc_18006EFDE
0x18006eeae  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x18006eeb2  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006eeb6  add     r8d, esi; Index
0x18006eeb9  mov     r9, r12; Data
0x18006eebc  mov     edx, esi; Type
0x18006eebe  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x18006eec2  call    cs:__imp_SeSetAuditParameter
0x18006eec9  nop     dword ptr [rax+rax+00h]
0x18006eece  mov     ebx, eax
0x18006eed0  test    eax, eax
0x18006eed2  js      loc_18006EFDE
0x18006eed8  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x18006eedc  lea     r9, [rbp+410h+arg_30]; Data
0x18006eee3  add     r8d, esi; Index
0x18006eee6  lea     edx, [rsi+14h]; Type
0x18006eee9  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006eeed  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x18006eef1  call    cs:__imp_SeSetAuditParameter
0x18006eef8  nop     dword ptr [rax+rax+00h]
0x18006eefd  mov     ebx, eax
0x18006eeff  test    eax, eax
0x18006ef01  js      loc_18006EFDE
0x18006ef07  movzx   edx, word ptr [rbp+410h+arg_40]
0x18006ef0e  lea     r8, [rsp+510h+DestinationString]
0x18006ef13  add     [rbp+410h+AuditParameters.ParameterCount], esi
0x18006ef16  mov     rcx, r14
0x18006ef19  call    CfgAdtpFormatPropertyBlock
0x18006ef1e  test    eax, eax
0x18006ef20  js      short loc_18006EF27
0x18006ef22  mov     dil, sil
0x18006ef25  jmp     short loc_18006EF42
0x18006ef27  lea     rdx, asc_1800B56C0; "-"
0x18006ef2e  mov     dil, r13b
0x18006ef31  lea     rcx, [rsp+510h+DestinationString]; DestinationString
0x18006ef36  call    cs:__imp_RtlInitUnicodeString
0x18006ef3d  nop     dword ptr [rax+rax+00h]
0x18006ef42  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]; Index
0x18006ef46  lea     r9, [rsp+510h+DestinationString]; Data
0x18006ef4b  mov     edx, esi; Type
0x18006ef4d  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006ef51  call    cs:__imp_SeSetAuditParameter
0x18006ef58  nop     dword ptr [rax+rax+00h]
0x18006ef5d  mov     ebx, eax
0x18006ef5f  test    eax, eax
0x18006ef61  js      short loc_18006EFCF
0x18006ef63  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x18006ef67  lea     r9, [rbp+410h+arg_48]; Data
0x18006ef6e  add     r8d, esi; Index
0x18006ef71  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006ef75  mov     edx, 0Ah; Type
0x18006ef7a  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x18006ef7e  call    cs:__imp_SeSetAuditParameter
0x18006ef85  nop     dword ptr [rax+rax+00h]
0x18006ef8a  mov     ebx, eax
0x18006ef8c  test    eax, eax
0x18006ef8e  js      short loc_18006EFCF
0x18006ef90  add     [rbp+410h+AuditParameters.ParameterCount], esi
0x18006ef93  lea     rdx, aSecurity; "Security"
0x18006ef9a  lea     rcx, [rsp+510h+SourceName]; DestinationString
0x18006ef9f  call    cs:__imp_RtlInitUnicodeString
0x18006efa6  nop     dword ptr [rax+rax+00h]
0x18006efab  lea     r9, [rbp+410h+AuditParameters]; AuditParameters
0x18006efaf  mov     [rsp+510h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006efb7  xor     r8d, r8d; UserSid
0x18006efba  lea     rdx, [rsp+510h+SourceName]; SourceName
0x18006efbf  xor     ecx, ecx; Flags
0x18006efc1  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006efc8  nop     dword ptr [rax+rax+00h]
0x18006efcd  mov     ebx, eax
0x18006efcf  test    dil, dil
0x18006efd2  jz      short loc_18006EFDE
0x18006efd4  mov     rcx, [rsp+510h+DestinationString.Buffer]; P
0x18006efd9  call    BCryptFree
0x18006efde  lea     rcx, [rsp+510h+SubjectContext]; SubjectContext
0x18006efe3  call    cs:__imp_SeReleaseSubjectContext
0x18006efea  nop     dword ptr [rax+rax+00h]
0x18006efef  mov     eax, ebx
0x18006eff1  mov     rcx, [rbp+410h+var_40]
0x18006eff8  xor     rcx, rsp; StackCookie
0x18006effb  call    __security_check_cookie
0x18006f000  mov     rbx, [rsp+510h+arg_0]
0x18006f008  add     rsp, 4E0h
0x18006f00f  pop     r15
0x18006f011  pop     r14
0x18006f013  pop     r13
0x18006f015  pop     r12
0x18006f017  pop     rdi
0x18006f018  pop     rsi
0x18006f019  pop     rbp
0x18006f01a  retn
```
