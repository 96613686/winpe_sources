# CfgAdtReportFunctionOperation

- ea: `0x18006dcc0`
- end: `0x18006df5f`
- name: `CfgAdtReportFunctionOperation`
- size: `671`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180069d20`
- `0x18006ba6c`

## callees

- `0x18006dcc0`
- `0x18006eae0`
- `0x18006ec28`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006defa`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006defa`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006df2f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006df2f`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006dd4e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006dd4e`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006df1c`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006df1c`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006de00`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006de00`
- `ntoskrnl!SeSetAuditParameter` at `0x18006dd83`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ddc4`
- `ntoskrnl!SeSetAuditParameter` at `0x18006de26`
- `ntoskrnl!SeSetAuditParameter` at `0x18006de51`
- `ntoskrnl!SeSetAuditParameter` at `0x18006de7f`
- `ntoskrnl!SeSetAuditParameter` at `0x18006deae`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ded8`
- `ntoskrnl!SeSetAuditParameter` at `0x18006dd83`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ddc4`
- `ntoskrnl!SeSetAuditParameter` at `0x18006de26`
- `ntoskrnl!SeSetAuditParameter` at `0x18006de51`
- `ntoskrnl!SeSetAuditParameter` at `0x18006de7f`
- `ntoskrnl!SeSetAuditParameter` at `0x18006deae`
- `ntoskrnl!SeSetAuditParameter` at `0x18006ded8`

## string_xrefs

- `0x18006deee`: `Security`

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
0x18006dcc0  push    rbp
0x18006dcc2  push    rbx
0x18006dcc3  push    rsi
0x18006dcc4  push    rdi
0x18006dcc5  push    r12
0x18006dcc7  push    r14
0x18006dcc9  push    r15
0x18006dccb  lea     rbp, [rsp-3D0h]
0x18006dcd3  sub     rsp, 4D0h
0x18006dcda  mov     rax, cs:__security_cookie
0x18006dce1  xor     rax, rsp
0x18006dce4  mov     [rbp+400h+var_40], rax
0x18006dceb  mov     r14, [rbp+400h+arg_20]
0x18006dcf2  mov     rdi, r8
0x18006dcf5  movzx   ebx, cx
0x18006dcf8  mov     [rsp+500h+Data], edx
0x18006dcfc  xor     edx, edx; Val
0x18006dcfe  lea     rcx, [rbp+400h+AuditParameters]; void *
0x18006dd02  mov     r8d, 418h; Size
0x18006dd08  mov     esi, r9d
0x18006dd0b  call    memset
0x18006dd10  xorps   xmm0, xmm0
0x18006dd13  lea     rcx, [rbp+400h+AuditParameters]
0x18006dd17  xorps   xmm1, xmm1
0x18006dd1a  mov     r8d, 13CAh
0x18006dd20  movzx   edx, bx
0x18006dd23  movups  xmmword ptr [rsp+500h+DestinationString.Length], xmm0
0x18006dd28  movups  xmmword ptr [rsp+500h+SubjectContext.ClientToken], xmm1
0x18006dd2d  movups  xmmword ptr [rsp+500h+SubjectContext.PrimaryToken], xmm1
0x18006dd32  movups  xmmword ptr [rsp+500h+String.Length], xmm0
0x18006dd37  call    CfgAdtpInitializeParameters
0x18006dd3c  xor     r15d, r15d
0x18006dd3f  mov     ebx, eax
0x18006dd41  test    eax, eax
0x18006dd43  js      loc_18006DF3B
0x18006dd49  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x18006dd4e  call    cs:__imp_SeCaptureSubjectContext
0x18006dd55  nop     dword ptr [rax+rax+00h]
0x18006dd5a  lea     rdx, [rsp+500h+SubjectContext]
0x18006dd5f  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006dd63  call    CfgAdtpAppendSecuritySubjectInfo
0x18006dd68  mov     ebx, eax
0x18006dd6a  test    eax, eax
0x18006dd6c  js      loc_18006DF2A
0x18006dd72  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x18006dd76  lea     r9, [rsp+500h+Data]; Data
0x18006dd7b  lea     edx, [r15+15h]; Type
0x18006dd7f  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006dd83  call    cs:__imp_SeSetAuditParameter
0x18006dd8a  nop     dword ptr [rax+rax+00h]
0x18006dd8f  mov     ebx, eax
0x18006dd91  test    eax, eax
0x18006dd93  js      loc_18006DF2A
0x18006dd99  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006dd9d  lea     r12d, [r15+1]
0x18006dda1  add     r8d, r12d; Index
0x18006dda4  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006dda8  test    rdi, rdi
0x18006ddab  jz      short loc_18006DDB6
0x18006ddad  mov     r9, rdi
0x18006ddb0  cmp     [rdi], r15w
0x18006ddb4  jnz     short loc_18006DDBD
0x18006ddb6  lea     r9, qword_1800A83B0; Data
0x18006ddbd  mov     edx, r12d; Type
0x18006ddc0  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006ddc4  call    cs:__imp_SeSetAuditParameter
0x18006ddcb  nop     dword ptr [rax+rax+00h]
0x18006ddd0  mov     ebx, eax
0x18006ddd2  test    eax, eax
0x18006ddd4  js      loc_18006DF2A
0x18006ddda  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x18006ddde  lea     rax, [rbp+400h+var_60]
0x18006dde5  mov     edi, 0Ah
0x18006ddea  mov     dword ptr [rsp+500h+String.Length], 200000h
0x18006ddf2  mov     edx, edi; Base
0x18006ddf4  mov     [rsp+500h+String.Buffer], rax
0x18006ddf9  lea     r8, [rsp+500h+String]; String
0x18006ddfe  mov     ecx, esi; Value
0x18006de00  call    cs:__imp_RtlIntegerToUnicodeString
0x18006de07  nop     dword ptr [rax+rax+00h]
0x18006de0c  mov     ebx, eax
0x18006de0e  test    eax, eax
0x18006de10  js      loc_18006DF2A
0x18006de16  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x18006de1a  lea     r9, [rsp+500h+String]; Data
0x18006de1f  mov     edx, r12d; Type
0x18006de22  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006de26  call    cs:__imp_SeSetAuditParameter
0x18006de2d  nop     dword ptr [rax+rax+00h]
0x18006de32  mov     ebx, eax
0x18006de34  test    eax, eax
0x18006de36  js      loc_18006DF2A
0x18006de3c  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006de40  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006de44  add     r8d, r12d; Index
0x18006de47  mov     r9, r14; Data
0x18006de4a  mov     edx, r12d; Type
0x18006de4d  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006de51  call    cs:__imp_SeSetAuditParameter
0x18006de58  nop     dword ptr [rax+rax+00h]
0x18006de5d  mov     ebx, eax
0x18006de5f  test    eax, eax
0x18006de61  js      loc_18006DF2A
0x18006de67  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006de6b  lea     r9, [rbp+400h+arg_28]; Data
0x18006de72  add     r8d, r12d; Index
0x18006de75  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006de79  mov     edx, edi; Type
0x18006de7b  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006de7f  call    cs:__imp_SeSetAuditParameter
0x18006de86  nop     dword ptr [rax+rax+00h]
0x18006de8b  mov     ebx, eax
0x18006de8d  test    eax, eax
0x18006de8f  js      loc_18006DF2A
0x18006de95  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006de99  lea     r9, [rbp+400h+arg_30]; Data
0x18006dea0  add     r8d, r12d; Index
0x18006dea3  lea     edx, [rdi+0Bh]; Type
0x18006dea6  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006deaa  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006deae  call    cs:__imp_SeSetAuditParameter
0x18006deb5  nop     dword ptr [rax+rax+00h]
0x18006deba  mov     ebx, eax
0x18006debc  test    eax, eax
0x18006debe  js      short loc_18006DF2A
0x18006dec0  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x18006dec4  lea     r9, [rbp+400h+arg_38]; Data
0x18006decb  add     r8d, r12d; Index
0x18006dece  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x18006ded2  mov     edx, edi; Type
0x18006ded4  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x18006ded8  call    cs:__imp_SeSetAuditParameter
0x18006dedf  nop     dword ptr [rax+rax+00h]
0x18006dee4  mov     ebx, eax
0x18006dee6  test    eax, eax
0x18006dee8  js      short loc_18006DF2A
0x18006deea  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x18006deee  lea     rdx, aSecurity; "Security"
0x18006def5  lea     rcx, [rsp+500h+DestinationString]; DestinationString
0x18006defa  call    cs:__imp_RtlInitUnicodeString
0x18006df01  nop     dword ptr [rax+rax+00h]
0x18006df06  lea     r9, [rbp+400h+AuditParameters]; AuditParameters
0x18006df0a  mov     [rsp+500h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006df12  xor     r8d, r8d; UserSid
0x18006df15  lea     rdx, [rsp+500h+DestinationString]; SourceName
0x18006df1a  xor     ecx, ecx; Flags
0x18006df1c  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006df23  nop     dword ptr [rax+rax+00h]
0x18006df28  mov     ebx, eax
0x18006df2a  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x18006df2f  call    cs:__imp_SeReleaseSubjectContext
0x18006df36  nop     dword ptr [rax+rax+00h]
0x18006df3b  mov     eax, ebx
0x18006df3d  mov     rcx, [rbp+400h+var_40]
0x18006df44  xor     rcx, rsp; StackCookie
0x18006df47  call    __security_check_cookie
0x18006df4c  add     rsp, 4D0h
0x18006df53  pop     r15
0x18006df55  pop     r14
0x18006df57  pop     r12
0x18006df59  pop     rdi
0x18006df5a  pop     rsi
0x18006df5b  pop     rbx
0x18006df5c  pop     rbp
0x18006df5d  retn
```
