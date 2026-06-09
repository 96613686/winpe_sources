# CfgAdtReportFunctionModification

- ea: `0x180077bbc`
- end: `0x180077e5a`
- name: `CfgAdtReportFunctionModification`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180074620`

## callees

- `0x180077bbc`
- `0x180078c80`
- `0x180078dc8`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180077df5`
- `ntoskrnl!RtlInitUnicodeString` at `0x180077df5`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180077e2a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180077e2a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180077c4a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180077c4a`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x180077e17`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x180077e17`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180077cfc`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180077cfc`
- `ntoskrnl!SeSetAuditParameter` at `0x180077c7f`
- `ntoskrnl!SeSetAuditParameter` at `0x180077cc0`
- `ntoskrnl!SeSetAuditParameter` at `0x180077d22`
- `ntoskrnl!SeSetAuditParameter` at `0x180077d4d`
- `ntoskrnl!SeSetAuditParameter` at `0x180077d7b`
- `ntoskrnl!SeSetAuditParameter` at `0x180077da9`
- `ntoskrnl!SeSetAuditParameter` at `0x180077dd3`
- `ntoskrnl!SeSetAuditParameter` at `0x180077c7f`
- `ntoskrnl!SeSetAuditParameter` at `0x180077cc0`
- `ntoskrnl!SeSetAuditParameter` at `0x180077d22`
- `ntoskrnl!SeSetAuditParameter` at `0x180077d4d`
- `ntoskrnl!SeSetAuditParameter` at `0x180077d7b`
- `ntoskrnl!SeSetAuditParameter` at `0x180077da9`
- `ntoskrnl!SeSetAuditParameter` at `0x180077dd3`

## string_xrefs

- `0x180077de9`: `Security`

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
0x180077bbc  push    rbp
0x180077bbe  push    rbx
0x180077bbf  push    rsi
0x180077bc0  push    rdi
0x180077bc1  push    r12
0x180077bc3  push    r14
0x180077bc5  push    r15
0x180077bc7  lea     rbp, [rsp-3D0h]
0x180077bcf  sub     rsp, 4D0h
0x180077bd6  mov     rax, cs:__security_cookie
0x180077bdd  xor     rax, rsp
0x180077be0  mov     [rbp+400h+var_40], rax
0x180077be7  mov     r14, [rbp+400h+arg_20]
0x180077bee  mov     rdi, r8
0x180077bf1  movzx   ebx, cx
0x180077bf4  mov     [rsp+500h+Data], edx
0x180077bf8  xor     edx, edx; Val
0x180077bfa  lea     rcx, [rbp+400h+AuditParameters]; void *
0x180077bfe  mov     r8d, 418h; Size
0x180077c04  mov     esi, r9d
0x180077c07  call    memset
0x180077c0c  xorps   xmm0, xmm0
0x180077c0f  lea     rcx, [rbp+400h+AuditParameters]
0x180077c13  xorps   xmm1, xmm1
0x180077c16  mov     r8d, 13CBh
0x180077c1c  movzx   edx, bx
0x180077c1f  movups  xmmword ptr [rsp+500h+DestinationString.Length], xmm0
0x180077c24  movups  xmmword ptr [rsp+500h+SubjectContext.ClientToken], xmm1
0x180077c29  movups  xmmword ptr [rsp+500h+SubjectContext.PrimaryToken], xmm1
0x180077c2e  movups  xmmword ptr [rsp+500h+String.Length], xmm0
0x180077c33  call    CfgAdtpInitializeParameters
0x180077c38  xor     r15d, r15d
0x180077c3b  mov     ebx, eax
0x180077c3d  test    eax, eax
0x180077c3f  js      loc_180077E36
0x180077c45  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x180077c4a  call    cs:__imp_SeCaptureSubjectContext
0x180077c51  nop     dword ptr [rax+rax+00h]
0x180077c56  lea     rdx, [rsp+500h+SubjectContext]
0x180077c5b  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180077c5f  call    CfgAdtpAppendSecuritySubjectInfo
0x180077c64  mov     ebx, eax
0x180077c66  test    eax, eax
0x180077c68  js      loc_180077E25
0x180077c6e  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x180077c72  lea     r9, [rsp+500h+Data]; Data
0x180077c77  lea     edx, [r15+15h]; Type
0x180077c7b  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180077c7f  call    cs:__imp_SeSetAuditParameter
0x180077c86  nop     dword ptr [rax+rax+00h]
0x180077c8b  mov     ebx, eax
0x180077c8d  test    eax, eax
0x180077c8f  js      loc_180077E25
0x180077c95  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x180077c99  lea     r12d, [r15+1]
0x180077c9d  add     r8d, r12d; Index
0x180077ca0  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x180077ca4  test    rdi, rdi
0x180077ca7  jz      short loc_180077CB2
0x180077ca9  mov     r9, rdi
0x180077cac  cmp     [rdi], r15w
0x180077cb0  jnz     short loc_180077CB9
0x180077cb2  lea     r9, qword_1800AF9A0; Data
0x180077cb9  mov     edx, r12d; Type
0x180077cbc  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180077cc0  call    cs:__imp_SeSetAuditParameter
0x180077cc7  nop     dword ptr [rax+rax+00h]
0x180077ccc  mov     ebx, eax
0x180077cce  test    eax, eax
0x180077cd0  js      loc_180077E25
0x180077cd6  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x180077cda  lea     rax, [rbp+400h+var_60]
0x180077ce1  mov     edi, 0Ah
0x180077ce6  mov     dword ptr [rsp+500h+String.Length], 200000h
0x180077cee  mov     edx, edi; Base
0x180077cf0  mov     [rsp+500h+String.Buffer], rax
0x180077cf5  lea     r8, [rsp+500h+String]; String
0x180077cfa  mov     ecx, esi; Value
0x180077cfc  call    cs:__imp_RtlIntegerToUnicodeString
0x180077d03  nop     dword ptr [rax+rax+00h]
0x180077d08  mov     ebx, eax
0x180077d0a  test    eax, eax
0x180077d0c  js      loc_180077E25
0x180077d12  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]; Index
0x180077d16  lea     r9, [rsp+500h+String]; Data
0x180077d1b  mov     edx, r12d; Type
0x180077d1e  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180077d22  call    cs:__imp_SeSetAuditParameter
0x180077d29  nop     dword ptr [rax+rax+00h]
0x180077d2e  mov     ebx, eax
0x180077d30  test    eax, eax
0x180077d32  js      loc_180077E25
0x180077d38  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x180077d3c  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180077d40  add     r8d, r12d; Index
0x180077d43  mov     r9, r14; Data
0x180077d46  mov     edx, r12d; Type
0x180077d49  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x180077d4d  call    cs:__imp_SeSetAuditParameter
0x180077d54  nop     dword ptr [rax+rax+00h]
0x180077d59  mov     ebx, eax
0x180077d5b  test    eax, eax
0x180077d5d  js      loc_180077E25
0x180077d63  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x180077d67  lea     r9, [rbp+400h+arg_28]; Data
0x180077d6e  add     r8d, r12d; Index
0x180077d71  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180077d75  mov     edx, edi; Type
0x180077d77  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x180077d7b  call    cs:__imp_SeSetAuditParameter
0x180077d82  nop     dword ptr [rax+rax+00h]
0x180077d87  mov     ebx, eax
0x180077d89  test    eax, eax
0x180077d8b  js      loc_180077E25
0x180077d91  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x180077d95  lea     r9, [rbp+400h+arg_30]; Data
0x180077d9c  add     r8d, r12d; Index
0x180077d9f  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180077da3  mov     edx, edi; Type
0x180077da5  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x180077da9  call    cs:__imp_SeSetAuditParameter
0x180077db0  nop     dword ptr [rax+rax+00h]
0x180077db5  mov     ebx, eax
0x180077db7  test    eax, eax
0x180077db9  js      short loc_180077E25
0x180077dbb  mov     r8d, [rbp+400h+AuditParameters.ParameterCount]
0x180077dbf  lea     r9, [rbp+400h+arg_38]; Data
0x180077dc6  add     r8d, r12d; Index
0x180077dc9  lea     rcx, [rbp+400h+AuditParameters]; AuditParameters
0x180077dcd  mov     edx, edi; Type
0x180077dcf  mov     [rbp+400h+AuditParameters.ParameterCount], r8d
0x180077dd3  call    cs:__imp_SeSetAuditParameter
0x180077dda  nop     dword ptr [rax+rax+00h]
0x180077ddf  mov     ebx, eax
0x180077de1  test    eax, eax
0x180077de3  js      short loc_180077E25
0x180077de5  add     [rbp+400h+AuditParameters.ParameterCount], r12d
0x180077de9  lea     rdx, aSecurity; "Security"
0x180077df0  lea     rcx, [rsp+500h+DestinationString]; DestinationString
0x180077df5  call    cs:__imp_RtlInitUnicodeString
0x180077dfc  nop     dword ptr [rax+rax+00h]
0x180077e01  lea     r9, [rbp+400h+AuditParameters]; AuditParameters
0x180077e05  mov     [rsp+500h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x180077e0d  xor     r8d, r8d; UserSid
0x180077e10  lea     rdx, [rsp+500h+DestinationString]; SourceName
0x180077e15  xor     ecx, ecx; Flags
0x180077e17  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x180077e1e  nop     dword ptr [rax+rax+00h]
0x180077e23  mov     ebx, eax
0x180077e25  lea     rcx, [rsp+500h+SubjectContext]; SubjectContext
0x180077e2a  call    cs:__imp_SeReleaseSubjectContext
0x180077e31  nop     dword ptr [rax+rax+00h]
0x180077e36  mov     eax, ebx
0x180077e38  mov     rcx, [rbp+400h+var_40]
0x180077e3f  xor     rcx, rsp; StackCookie
0x180077e42  call    __security_check_cookie
0x180077e47  add     rsp, 4D0h
0x180077e4e  pop     r15
0x180077e50  pop     r14
0x180077e52  pop     r12
0x180077e54  pop     rdi
0x180077e55  pop     rsi
0x180077e56  pop     rbx
0x180077e57  pop     rbp
0x180077e58  retn
```
