# CfgAdtReportFunctionPropertyOperation

- ea: `0x180078490`
- end: `0x1800787bc`
- name: `CfgAdtReportFunctionPropertyOperation`
- size: `812`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180076154`

## callees

- `0x180025ec0`
- `0x180078490`
- `0x180078c80`
- `0x180078ce4`
- `0x180078dc8`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800786d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007873f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800786d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007873f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180078783`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180078783`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180078536`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180078536`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x180078761`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x180078761`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1800785e4`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1800785e4`
- `ntoskrnl!SeSetAuditParameter` at `0x18007856b`
- `ntoskrnl!SeSetAuditParameter` at `0x1800785ab`
- `ntoskrnl!SeSetAuditParameter` at `0x18007860e`
- `ntoskrnl!SeSetAuditParameter` at `0x180078638`
- `ntoskrnl!SeSetAuditParameter` at `0x180078662`
- `ntoskrnl!SeSetAuditParameter` at `0x180078691`
- `ntoskrnl!SeSetAuditParameter` at `0x1800786f1`
- `ntoskrnl!SeSetAuditParameter` at `0x18007871e`
- `ntoskrnl!SeSetAuditParameter` at `0x18007856b`
- `ntoskrnl!SeSetAuditParameter` at `0x1800785ab`
- `ntoskrnl!SeSetAuditParameter` at `0x18007860e`
- `ntoskrnl!SeSetAuditParameter` at `0x180078638`
- `ntoskrnl!SeSetAuditParameter` at `0x180078662`
- `ntoskrnl!SeSetAuditParameter` at `0x180078691`
- `ntoskrnl!SeSetAuditParameter` at `0x1800786f1`
- `ntoskrnl!SeSetAuditParameter` at `0x18007871e`

## string_xrefs

- `0x180078733`: `Security`

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
          v12 = &qword_1800AF9A0;
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
0x180078490  mov     [rsp-8+arg_0], rbx
0x180078495  push    rbp
0x180078496  push    rsi
0x180078497  push    rdi
0x180078498  push    r12
0x18007849a  push    r13
0x18007849c  push    r14
0x18007849e  push    r15
0x1800784a0  lea     rbp, [rsp-3E0h]
0x1800784a8  sub     rsp, 4E0h
0x1800784af  mov     rax, cs:__security_cookie
0x1800784b6  xor     rax, rsp
0x1800784b9  mov     [rbp+410h+var_40], rax
0x1800784c0  mov     r15, [rbp+410h+arg_20]
0x1800784c7  mov     rdi, r8
0x1800784ca  mov     r12, [rbp+410h+arg_28]
0x1800784d1  movzx   ebx, cx
0x1800784d4  mov     r14, [rbp+410h+arg_38]
0x1800784db  lea     rcx, [rbp+410h+AuditParameters]; void *
0x1800784df  mov     [rsp+510h+Data], edx
0x1800784e3  mov     r8d, 418h; Size
0x1800784e9  xor     edx, edx; Val
0x1800784eb  mov     esi, r9d
0x1800784ee  call    memset
0x1800784f3  xorps   xmm1, xmm1
0x1800784f6  lea     rcx, [rbp+410h+AuditParameters]
0x1800784fa  xorps   xmm0, xmm0
0x1800784fd  mov     r8d, 13CDh
0x180078503  movzx   edx, bx
0x180078506  movups  xmmword ptr [rsp+510h+SourceName.Length], xmm0
0x18007850b  movups  xmmword ptr [rsp+510h+SubjectContext.ClientToken], xmm1
0x180078510  movups  xmmword ptr [rsp+510h+SubjectContext.PrimaryToken], xmm1
0x180078515  movups  xmmword ptr [rsp+510h+DestinationString.Length], xmm0
0x18007851a  movups  xmmword ptr [rsp+510h+String.Length], xmm1
0x18007851f  call    CfgAdtpInitializeParameters
0x180078524  xor     r13d, r13d
0x180078527  mov     ebx, eax
0x180078529  test    eax, eax
0x18007852b  js      loc_18007878F
0x180078531  lea     rcx, [rsp+510h+SubjectContext]; SubjectContext
0x180078536  call    cs:__imp_SeCaptureSubjectContext
0x18007853d  nop     dword ptr [rax+rax+00h]
0x180078542  lea     rdx, [rsp+510h+SubjectContext]
0x180078547  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18007854b  call    CfgAdtpAppendSecuritySubjectInfo
0x180078550  mov     ebx, eax
0x180078552  test    eax, eax
0x180078554  js      loc_18007877E
0x18007855a  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]; Index
0x18007855e  lea     r9, [rsp+510h+Data]; Data
0x180078563  lea     edx, [r13+15h]; Type
0x180078567  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18007856b  call    cs:__imp_SeSetAuditParameter
0x180078572  nop     dword ptr [rax+rax+00h]
0x180078577  mov     ebx, eax
0x180078579  test    eax, eax
0x18007857b  js      loc_18007877E
0x180078581  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x180078585  lea     eax, [r13+1]
0x180078589  add     r8d, eax; Index
0x18007858c  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x180078590  test    rdi, rdi
0x180078593  jz      short loc_18007859E
0x180078595  mov     r9, rdi
0x180078598  cmp     [rdi], r13w
0x18007859c  jnz     short loc_1800785A5
0x18007859e  lea     r9, qword_1800AF9A0; Data
0x1800785a5  mov     edx, eax; Type
0x1800785a7  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x1800785ab  call    cs:__imp_SeSetAuditParameter
0x1800785b2  nop     dword ptr [rax+rax+00h]
0x1800785b7  mov     ebx, eax
0x1800785b9  test    eax, eax
0x1800785bb  js      loc_18007877E
0x1800785c1  inc     [rbp+410h+AuditParameters.ParameterCount]
0x1800785c4  lea     rax, [rbp+410h+var_60]
0x1800785cb  lea     r8, [rsp+510h+String]; String
0x1800785d0  mov     [rsp+510h+String.Buffer], rax
0x1800785d5  mov     edx, 0Ah; Base
0x1800785da  mov     dword ptr [rsp+510h+String.Length], 200000h
0x1800785e2  mov     ecx, esi; Value
0x1800785e4  call    cs:__imp_RtlIntegerToUnicodeString
0x1800785eb  nop     dword ptr [rax+rax+00h]
0x1800785f0  mov     ebx, eax
0x1800785f2  test    eax, eax
0x1800785f4  js      loc_18007877E
0x1800785fa  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]; Index
0x1800785fe  lea     r9, [rsp+510h+String]; Data
0x180078603  mov     esi, 1
0x180078608  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18007860c  mov     edx, esi; Type
0x18007860e  call    cs:__imp_SeSetAuditParameter
0x180078615  nop     dword ptr [rax+rax+00h]
0x18007861a  mov     ebx, eax
0x18007861c  test    eax, eax
0x18007861e  js      loc_18007877E
0x180078624  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x180078628  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18007862c  add     r8d, esi; Index
0x18007862f  mov     r9, r15; Data
0x180078632  mov     edx, esi; Type
0x180078634  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x180078638  call    cs:__imp_SeSetAuditParameter
0x18007863f  nop     dword ptr [rax+rax+00h]
0x180078644  mov     ebx, eax
0x180078646  test    eax, eax
0x180078648  js      loc_18007877E
0x18007864e  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x180078652  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x180078656  add     r8d, esi; Index
0x180078659  mov     r9, r12; Data
0x18007865c  mov     edx, esi; Type
0x18007865e  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x180078662  call    cs:__imp_SeSetAuditParameter
0x180078669  nop     dword ptr [rax+rax+00h]
0x18007866e  mov     ebx, eax
0x180078670  test    eax, eax
0x180078672  js      loc_18007877E
0x180078678  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x18007867c  lea     r9, [rbp+410h+arg_30]; Data
0x180078683  add     r8d, esi; Index
0x180078686  lea     edx, [rsi+14h]; Type
0x180078689  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18007868d  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x180078691  call    cs:__imp_SeSetAuditParameter
0x180078698  nop     dword ptr [rax+rax+00h]
0x18007869d  mov     ebx, eax
0x18007869f  test    eax, eax
0x1800786a1  js      loc_18007877E
0x1800786a7  movzx   edx, word ptr [rbp+410h+arg_40]
0x1800786ae  lea     r8, [rsp+510h+DestinationString]
0x1800786b3  add     [rbp+410h+AuditParameters.ParameterCount], esi
0x1800786b6  mov     rcx, r14
0x1800786b9  call    CfgAdtpFormatPropertyBlock
0x1800786be  test    eax, eax
0x1800786c0  js      short loc_1800786C7
0x1800786c2  mov     dil, sil
0x1800786c5  jmp     short loc_1800786E2
0x1800786c7  lea     rdx, asc_1800BAEC0; "-"
0x1800786ce  mov     dil, r13b
0x1800786d1  lea     rcx, [rsp+510h+DestinationString]; DestinationString
0x1800786d6  call    cs:__imp_RtlInitUnicodeString
0x1800786dd  nop     dword ptr [rax+rax+00h]
0x1800786e2  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]; Index
0x1800786e6  lea     r9, [rsp+510h+DestinationString]; Data
0x1800786eb  mov     edx, esi; Type
0x1800786ed  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x1800786f1  call    cs:__imp_SeSetAuditParameter
0x1800786f8  nop     dword ptr [rax+rax+00h]
0x1800786fd  mov     ebx, eax
0x1800786ff  test    eax, eax
0x180078701  js      short loc_18007876F
0x180078703  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x180078707  lea     r9, [rbp+410h+arg_48]; Data
0x18007870e  add     r8d, esi; Index
0x180078711  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x180078715  mov     edx, 0Ah; Type
0x18007871a  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x18007871e  call    cs:__imp_SeSetAuditParameter
0x180078725  nop     dword ptr [rax+rax+00h]
0x18007872a  mov     ebx, eax
0x18007872c  test    eax, eax
0x18007872e  js      short loc_18007876F
0x180078730  add     [rbp+410h+AuditParameters.ParameterCount], esi
0x180078733  lea     rdx, aSecurity; "Security"
0x18007873a  lea     rcx, [rsp+510h+SourceName]; DestinationString
0x18007873f  call    cs:__imp_RtlInitUnicodeString
0x180078746  nop     dword ptr [rax+rax+00h]
0x18007874b  lea     r9, [rbp+410h+AuditParameters]; AuditParameters
0x18007874f  mov     [rsp+510h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x180078757  xor     r8d, r8d; UserSid
0x18007875a  lea     rdx, [rsp+510h+SourceName]; SourceName
0x18007875f  xor     ecx, ecx; Flags
0x180078761  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x180078768  nop     dword ptr [rax+rax+00h]
0x18007876d  mov     ebx, eax
0x18007876f  test    dil, dil
0x180078772  jz      short loc_18007877E
0x180078774  mov     rcx, [rsp+510h+DestinationString.Buffer]; P
0x180078779  call    BCryptFree
0x18007877e  lea     rcx, [rsp+510h+SubjectContext]; SubjectContext
0x180078783  call    cs:__imp_SeReleaseSubjectContext
0x18007878a  nop     dword ptr [rax+rax+00h]
0x18007878f  mov     eax, ebx
0x180078791  mov     rcx, [rbp+410h+var_40]
0x180078798  xor     rcx, rsp; StackCookie
0x18007879b  call    __security_check_cookie
0x1800787a0  mov     rbx, [rsp+510h+arg_0]
0x1800787a8  add     rsp, 4E0h
0x1800787af  pop     r15
0x1800787b1  pop     r14
0x1800787b3  pop     r13
0x1800787b5  pop     r12
0x1800787b7  pop     rdi
0x1800787b8  pop     rsi
0x1800787b9  pop     rbp
0x1800787ba  retn
```
