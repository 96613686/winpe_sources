# CfgAdtReportFunctionPropertyOperation

- ea: `0x18006e2f0`
- end: `0x18006e61c`
- name: `CfgAdtReportFunctionPropertyOperation`
- size: `812`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006bfb4`

## callees

- `0x18001bd90`
- `0x18006e2f0`
- `0x18006eae0`
- `0x18006eb44`
- `0x18006ec28`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006e536`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e59f`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e536`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e59f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e5e3`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e5e3`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e396`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e396`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e5c1`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e5c1`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006e444`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006e444`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e3cb`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e40b`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e46e`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e498`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e4c2`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e4f1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e551`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e57e`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e3cb`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e40b`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e46e`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e498`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e4c2`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e4f1`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e551`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e57e`

## string_xrefs

- `0x18006e593`: `Security`

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
          v12 = &qword_1800A83B0;
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
0x18006e2f0  mov     [rsp-8+arg_0], rbx
0x18006e2f5  push    rbp
0x18006e2f6  push    rsi
0x18006e2f7  push    rdi
0x18006e2f8  push    r12
0x18006e2fa  push    r13
0x18006e2fc  push    r14
0x18006e2fe  push    r15
0x18006e300  lea     rbp, [rsp-3E0h]
0x18006e308  sub     rsp, 4E0h
0x18006e30f  mov     rax, cs:__security_cookie
0x18006e316  xor     rax, rsp
0x18006e319  mov     [rbp+410h+var_40], rax
0x18006e320  mov     r15, [rbp+410h+arg_20]
0x18006e327  mov     rdi, r8
0x18006e32a  mov     r12, [rbp+410h+arg_28]
0x18006e331  movzx   ebx, cx
0x18006e334  mov     r14, [rbp+410h+arg_38]
0x18006e33b  lea     rcx, [rbp+410h+AuditParameters]; void *
0x18006e33f  mov     [rsp+510h+Data], edx
0x18006e343  mov     r8d, 418h; Size
0x18006e349  xor     edx, edx; Val
0x18006e34b  mov     esi, r9d
0x18006e34e  call    memset
0x18006e353  xorps   xmm1, xmm1
0x18006e356  lea     rcx, [rbp+410h+AuditParameters]
0x18006e35a  xorps   xmm0, xmm0
0x18006e35d  mov     r8d, 13CDh
0x18006e363  movzx   edx, bx
0x18006e366  movups  xmmword ptr [rsp+510h+SourceName.Length], xmm0
0x18006e36b  movups  xmmword ptr [rsp+510h+SubjectContext.ClientToken], xmm1
0x18006e370  movups  xmmword ptr [rsp+510h+SubjectContext.PrimaryToken], xmm1
0x18006e375  movups  xmmword ptr [rsp+510h+DestinationString.Length], xmm0
0x18006e37a  movups  xmmword ptr [rsp+510h+String.Length], xmm1
0x18006e37f  call    CfgAdtpInitializeParameters
0x18006e384  xor     r13d, r13d
0x18006e387  mov     ebx, eax
0x18006e389  test    eax, eax
0x18006e38b  js      loc_18006E5EF
0x18006e391  lea     rcx, [rsp+510h+SubjectContext]; SubjectContext
0x18006e396  call    cs:__imp_SeCaptureSubjectContext
0x18006e39d  nop     dword ptr [rax+rax+00h]
0x18006e3a2  lea     rdx, [rsp+510h+SubjectContext]
0x18006e3a7  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006e3ab  call    CfgAdtpAppendSecuritySubjectInfo
0x18006e3b0  mov     ebx, eax
0x18006e3b2  test    eax, eax
0x18006e3b4  js      loc_18006E5DE
0x18006e3ba  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]; Index
0x18006e3be  lea     r9, [rsp+510h+Data]; Data
0x18006e3c3  lea     edx, [r13+15h]; Type
0x18006e3c7  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006e3cb  call    cs:__imp_SeSetAuditParameter
0x18006e3d2  nop     dword ptr [rax+rax+00h]
0x18006e3d7  mov     ebx, eax
0x18006e3d9  test    eax, eax
0x18006e3db  js      loc_18006E5DE
0x18006e3e1  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x18006e3e5  lea     eax, [r13+1]
0x18006e3e9  add     r8d, eax; Index
0x18006e3ec  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x18006e3f0  test    rdi, rdi
0x18006e3f3  jz      short loc_18006E3FE
0x18006e3f5  mov     r9, rdi
0x18006e3f8  cmp     [rdi], r13w
0x18006e3fc  jnz     short loc_18006E405
0x18006e3fe  lea     r9, qword_1800A83B0; Data
0x18006e405  mov     edx, eax; Type
0x18006e407  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006e40b  call    cs:__imp_SeSetAuditParameter
0x18006e412  nop     dword ptr [rax+rax+00h]
0x18006e417  mov     ebx, eax
0x18006e419  test    eax, eax
0x18006e41b  js      loc_18006E5DE
0x18006e421  inc     [rbp+410h+AuditParameters.ParameterCount]
0x18006e424  lea     rax, [rbp+410h+var_60]
0x18006e42b  lea     r8, [rsp+510h+String]; String
0x18006e430  mov     [rsp+510h+String.Buffer], rax
0x18006e435  mov     edx, 0Ah; Base
0x18006e43a  mov     dword ptr [rsp+510h+String.Length], 200000h
0x18006e442  mov     ecx, esi; Value
0x18006e444  call    cs:__imp_RtlIntegerToUnicodeString
0x18006e44b  nop     dword ptr [rax+rax+00h]
0x18006e450  mov     ebx, eax
0x18006e452  test    eax, eax
0x18006e454  js      loc_18006E5DE
0x18006e45a  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]; Index
0x18006e45e  lea     r9, [rsp+510h+String]; Data
0x18006e463  mov     esi, 1
0x18006e468  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006e46c  mov     edx, esi; Type
0x18006e46e  call    cs:__imp_SeSetAuditParameter
0x18006e475  nop     dword ptr [rax+rax+00h]
0x18006e47a  mov     ebx, eax
0x18006e47c  test    eax, eax
0x18006e47e  js      loc_18006E5DE
0x18006e484  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x18006e488  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006e48c  add     r8d, esi; Index
0x18006e48f  mov     r9, r15; Data
0x18006e492  mov     edx, esi; Type
0x18006e494  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x18006e498  call    cs:__imp_SeSetAuditParameter
0x18006e49f  nop     dword ptr [rax+rax+00h]
0x18006e4a4  mov     ebx, eax
0x18006e4a6  test    eax, eax
0x18006e4a8  js      loc_18006E5DE
0x18006e4ae  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x18006e4b2  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006e4b6  add     r8d, esi; Index
0x18006e4b9  mov     r9, r12; Data
0x18006e4bc  mov     edx, esi; Type
0x18006e4be  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x18006e4c2  call    cs:__imp_SeSetAuditParameter
0x18006e4c9  nop     dword ptr [rax+rax+00h]
0x18006e4ce  mov     ebx, eax
0x18006e4d0  test    eax, eax
0x18006e4d2  js      loc_18006E5DE
0x18006e4d8  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x18006e4dc  lea     r9, [rbp+410h+arg_30]; Data
0x18006e4e3  add     r8d, esi; Index
0x18006e4e6  lea     edx, [rsi+14h]; Type
0x18006e4e9  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006e4ed  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x18006e4f1  call    cs:__imp_SeSetAuditParameter
0x18006e4f8  nop     dword ptr [rax+rax+00h]
0x18006e4fd  mov     ebx, eax
0x18006e4ff  test    eax, eax
0x18006e501  js      loc_18006E5DE
0x18006e507  movzx   edx, word ptr [rbp+410h+arg_40]
0x18006e50e  lea     r8, [rsp+510h+DestinationString]
0x18006e513  add     [rbp+410h+AuditParameters.ParameterCount], esi
0x18006e516  mov     rcx, r14
0x18006e519  call    CfgAdtpFormatPropertyBlock
0x18006e51e  test    eax, eax
0x18006e520  js      short loc_18006E527
0x18006e522  mov     dil, sil
0x18006e525  jmp     short loc_18006E542
0x18006e527  lea     rdx, asc_1800B32C0; "-"
0x18006e52e  mov     dil, r13b
0x18006e531  lea     rcx, [rsp+510h+DestinationString]; DestinationString
0x18006e536  call    cs:__imp_RtlInitUnicodeString
0x18006e53d  nop     dword ptr [rax+rax+00h]
0x18006e542  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]; Index
0x18006e546  lea     r9, [rsp+510h+DestinationString]; Data
0x18006e54b  mov     edx, esi; Type
0x18006e54d  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006e551  call    cs:__imp_SeSetAuditParameter
0x18006e558  nop     dword ptr [rax+rax+00h]
0x18006e55d  mov     ebx, eax
0x18006e55f  test    eax, eax
0x18006e561  js      short loc_18006E5CF
0x18006e563  mov     r8d, [rbp+410h+AuditParameters.ParameterCount]
0x18006e567  lea     r9, [rbp+410h+arg_48]; Data
0x18006e56e  add     r8d, esi; Index
0x18006e571  lea     rcx, [rbp+410h+AuditParameters]; AuditParameters
0x18006e575  mov     edx, 0Ah; Type
0x18006e57a  mov     [rbp+410h+AuditParameters.ParameterCount], r8d
0x18006e57e  call    cs:__imp_SeSetAuditParameter
0x18006e585  nop     dword ptr [rax+rax+00h]
0x18006e58a  mov     ebx, eax
0x18006e58c  test    eax, eax
0x18006e58e  js      short loc_18006E5CF
0x18006e590  add     [rbp+410h+AuditParameters.ParameterCount], esi
0x18006e593  lea     rdx, aSecurity; "Security"
0x18006e59a  lea     rcx, [rsp+510h+SourceName]; DestinationString
0x18006e59f  call    cs:__imp_RtlInitUnicodeString
0x18006e5a6  nop     dword ptr [rax+rax+00h]
0x18006e5ab  lea     r9, [rbp+410h+AuditParameters]; AuditParameters
0x18006e5af  mov     [rsp+510h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006e5b7  xor     r8d, r8d; UserSid
0x18006e5ba  lea     rdx, [rsp+510h+SourceName]; SourceName
0x18006e5bf  xor     ecx, ecx; Flags
0x18006e5c1  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006e5c8  nop     dword ptr [rax+rax+00h]
0x18006e5cd  mov     ebx, eax
0x18006e5cf  test    dil, dil
0x18006e5d2  jz      short loc_18006E5DE
0x18006e5d4  mov     rcx, [rsp+510h+DestinationString.Buffer]; P
0x18006e5d9  call    BCryptFree
0x18006e5de  lea     rcx, [rsp+510h+SubjectContext]; SubjectContext
0x18006e5e3  call    cs:__imp_SeReleaseSubjectContext
0x18006e5ea  nop     dword ptr [rax+rax+00h]
0x18006e5ef  mov     eax, ebx
0x18006e5f1  mov     rcx, [rbp+410h+var_40]
0x18006e5f8  xor     rcx, rsp; StackCookie
0x18006e5fb  call    __security_check_cookie
0x18006e600  mov     rbx, [rsp+510h+arg_0]
0x18006e608  add     rsp, 4E0h
0x18006e60f  pop     r15
0x18006e611  pop     r14
0x18006e613  pop     r13
0x18006e615  pop     r12
0x18006e617  pop     rdi
0x18006e618  pop     rsi
0x18006e619  pop     rbp
0x18006e61a  retn
```
