# CfgAdtReportFunctionPropertyModification

- ea: `0x18006df68`
- end: `0x18006e2e8`
- name: `CfgAdtReportFunctionPropertyModification`
- size: `896`
- prototype: `__int64(unsigned __int16, int, __int64 *, ULONG, PVOID, PVOID, char *, unsigned __int16, char *, unsigned __int16, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006bfb4`

## callees

- `0x18001bd90`
- `0x18006df68`
- `0x18006eae0`
- `0x18006eb44`
- `0x18006ec28`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18006e192`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e1f1`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e25c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e192`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e1f1`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006e25c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e2af`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18006e2af`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e016`
- `ntoskrnl!SeCaptureSubjectContext` at `0x18006e016`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e27e`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18006e27e`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006e0c5`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x18006e0c5`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e04c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e08c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e0ef`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e119`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e149`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e1ae`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e20d`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e23a`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e04c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e08c`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e0ef`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e119`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e149`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e1ae`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e20d`
- `ntoskrnl!SeSetAuditParameter` at `0x18006e23a`

## string_xrefs

- `0x18006e250`: `Security`

## pseudocode

```c
__int64 CfgAdtReportFunctionPropertyModification(
        unsigned __int16 a1,
        int a2,
        __int64 *a3,
        ULONG a4,
        PVOID a5,
        PVOID a6,
        char *a7,
        unsigned __int16 a8,
        char *a9,
        unsigned __int16 a10,
        ...)
{
  NTSTATUS appended; // ebx
  ULONG v14; // r8d
  __int64 *v15; // r9
  char v16; // si
  char v17; // di
  int Data; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING String; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING v22; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING SourceName; // [rsp+68h] [rbp-98h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+78h] [rbp-88h] BYREF
  struct _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+A0h] [rbp-60h] BYREF
  char v26; // [rsp+4C0h] [rbp+3C0h] BYREF
  va_list va; // [rsp+580h] [rbp+480h] BYREF

  va_start(va, a10);
  Data = a2;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  SourceName = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  DestinationString = 0;
  v22 = 0;
  String = 0;
  appended = CfgAdtpInitializeParameters(&AuditParameters, a1, 5070);
  if ( appended >= 0 )
  {
    SeCaptureSubjectContext(&SubjectContext);
    appended = CfgAdtpAppendSecuritySubjectInfo(&AuditParameters);
    if ( appended >= 0 )
    {
      appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeMessage, AuditParameters.ParameterCount, &Data);
      if ( appended >= 0 )
      {
        v14 = ++AuditParameters.ParameterCount;
        if ( !a3 || (v15 = a3, !*(_WORD *)a3) )
          v15 = &qword_1800A83B0;
        appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v14, v15);
        if ( appended >= 0 )
        {
          ++AuditParameters.ParameterCount;
          String.Buffer = (PWSTR)&v26;
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
                  ++AuditParameters.ParameterCount;
                  v16 = 0;
                  if ( (int)CfgAdtpFormatPropertyBlock(a7, a8, (__int64)&DestinationString) < 0 )
                  {
                    v17 = 0;
                    RtlInitUnicodeString(&DestinationString, L"-");
                  }
                  else
                  {
                    v17 = 1;
                  }
                  appended = SeSetAuditParameter(
                               &AuditParameters,
                               SeAdtParmTypeString,
                               AuditParameters.ParameterCount,
                               &DestinationString);
                  if ( appended >= 0 )
                  {
                    ++AuditParameters.ParameterCount;
                    if ( (int)CfgAdtpFormatPropertyBlock(a9, a10, (__int64)&v22) < 0 )
                      RtlInitUnicodeString(&v22, L"-");
                    else
                      v16 = 1;
                    appended = SeSetAuditParameter(
                                 &AuditParameters,
                                 SeAdtParmTypeString,
                                 AuditParameters.ParameterCount,
                                 &v22);
                    if ( appended >= 0 )
                    {
                      appended = SeSetAuditParameter(
                                   &AuditParameters,
                                   SeAdtParmTypeHexUlong,
                                   ++AuditParameters.ParameterCount,
                                   va);
                      if ( appended >= 0 )
                      {
                        ++AuditParameters.ParameterCount;
                        RtlInitUnicodeString(&SourceName, L"Security");
                        appended = SeReportSecurityEventWithSubCategory(0, &SourceName, 0, &AuditParameters, 0x91u);
                      }
                    }
                  }
                  if ( v17 )
                    BCryptFree(DestinationString.Buffer);
                  if ( v16 )
                    BCryptFree(v22.Buffer);
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
0x18006df68  mov     [rsp-8+arg_0], rbx
0x18006df6d  push    rbp
0x18006df6e  push    rsi
0x18006df6f  push    rdi
0x18006df70  push    r12
0x18006df72  push    r13
0x18006df74  push    r14
0x18006df76  push    r15
0x18006df78  lea     rbp, [rsp-3F0h]
0x18006df80  sub     rsp, 4F0h
0x18006df87  mov     rax, cs:__security_cookie
0x18006df8e  xor     rax, rsp
0x18006df91  mov     [rbp+420h+var_40], rax
0x18006df98  mov     r14, [rbp+420h+arg_20]
0x18006df9f  mov     rdi, r8
0x18006dfa2  mov     r15, [rbp+420h+arg_28]
0x18006dfa9  movzx   ebx, cx
0x18006dfac  mov     r12, [rbp+420h+arg_30]
0x18006dfb3  lea     rcx, [rbp+420h+AuditParameters]; void *
0x18006dfb7  mov     r13, [rbp+420h+arg_40]
0x18006dfbe  mov     r8d, 418h; Size
0x18006dfc4  mov     [rsp+520h+Data], edx
0x18006dfc8  mov     esi, r9d
0x18006dfcb  xor     edx, edx; Val
0x18006dfcd  call    memset
0x18006dfd2  xorps   xmm0, xmm0
0x18006dfd5  lea     rcx, [rbp+420h+AuditParameters]
0x18006dfd9  xorps   xmm1, xmm1
0x18006dfdc  mov     r8d, 13CEh
0x18006dfe2  movzx   edx, bx
0x18006dfe5  movups  xmmword ptr [rsp+520h+SourceName.Length], xmm0
0x18006dfea  movups  xmmword ptr [rsp+520h+SubjectContext.ClientToken], xmm1
0x18006dfef  movups  xmmword ptr [rbp+420h+SubjectContext.PrimaryToken], xmm1
0x18006dff3  movups  xmmword ptr [rsp+520h+DestinationString.Length], xmm0
0x18006dff8  movups  xmmword ptr [rsp+520h+var_4C8.Length], xmm1
0x18006dffd  movups  xmmword ptr [rsp+520h+String.Length], xmm0
0x18006e002  call    CfgAdtpInitializeParameters
0x18006e007  mov     ebx, eax
0x18006e009  test    eax, eax
0x18006e00b  js      loc_18006E2BB
0x18006e011  lea     rcx, [rsp+520h+SubjectContext]; SubjectContext
0x18006e016  call    cs:__imp_SeCaptureSubjectContext
0x18006e01d  nop     dword ptr [rax+rax+00h]
0x18006e022  lea     rdx, [rsp+520h+SubjectContext]
0x18006e027  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006e02b  call    CfgAdtpAppendSecuritySubjectInfo
0x18006e030  mov     ebx, eax
0x18006e032  test    eax, eax
0x18006e034  js      loc_18006E2AA
0x18006e03a  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]; Index
0x18006e03e  lea     r9, [rsp+520h+Data]; Data
0x18006e043  mov     edx, 15h; Type
0x18006e048  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006e04c  call    cs:__imp_SeSetAuditParameter
0x18006e053  nop     dword ptr [rax+rax+00h]
0x18006e058  mov     ebx, eax
0x18006e05a  xor     eax, eax
0x18006e05c  test    ebx, ebx
0x18006e05e  js      loc_18006E2AA
0x18006e064  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]
0x18006e068  lea     ecx, [rax+1]
0x18006e06b  add     r8d, ecx; Index
0x18006e06e  mov     [rbp+420h+AuditParameters.ParameterCount], r8d
0x18006e072  test    rdi, rdi
0x18006e075  jz      short loc_18006E07F
0x18006e077  mov     r9, rdi
0x18006e07a  cmp     [rdi], ax
0x18006e07d  jnz     short loc_18006E086
0x18006e07f  lea     r9, qword_1800A83B0; Data
0x18006e086  mov     edx, ecx; Type
0x18006e088  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006e08c  call    cs:__imp_SeSetAuditParameter
0x18006e093  nop     dword ptr [rax+rax+00h]
0x18006e098  mov     ebx, eax
0x18006e09a  test    eax, eax
0x18006e09c  js      loc_18006E2AA
0x18006e0a2  inc     [rbp+420h+AuditParameters.ParameterCount]
0x18006e0a5  lea     rax, [rbp+420h+var_60]
0x18006e0ac  lea     r8, [rsp+520h+String]; String
0x18006e0b1  mov     [rsp+520h+String.Buffer], rax
0x18006e0b6  mov     edx, 0Ah; Base
0x18006e0bb  mov     dword ptr [rsp+520h+String.Length], 200000h
0x18006e0c3  mov     ecx, esi; Value
0x18006e0c5  call    cs:__imp_RtlIntegerToUnicodeString
0x18006e0cc  nop     dword ptr [rax+rax+00h]
0x18006e0d1  mov     ebx, eax
0x18006e0d3  test    eax, eax
0x18006e0d5  js      loc_18006E2AA
0x18006e0db  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]; Index
0x18006e0df  lea     r9, [rsp+520h+String]; Data
0x18006e0e4  mov     esi, 1
0x18006e0e9  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006e0ed  mov     edx, esi; Type
0x18006e0ef  call    cs:__imp_SeSetAuditParameter
0x18006e0f6  nop     dword ptr [rax+rax+00h]
0x18006e0fb  mov     ebx, eax
0x18006e0fd  test    eax, eax
0x18006e0ff  js      loc_18006E2AA
0x18006e105  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]
0x18006e109  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006e10d  add     r8d, esi; Index
0x18006e110  mov     r9, r14; Data
0x18006e113  mov     edx, esi; Type
0x18006e115  mov     [rbp+420h+AuditParameters.ParameterCount], r8d
0x18006e119  call    cs:__imp_SeSetAuditParameter
0x18006e120  nop     dword ptr [rax+rax+00h]
0x18006e125  xor     r14d, r14d
0x18006e128  mov     ebx, eax
0x18006e12a  test    eax, eax
0x18006e12c  js      loc_18006E2AA
0x18006e132  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]
0x18006e136  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006e13a  add     r8d, esi; Index
0x18006e13d  mov     r9, r15; Data
0x18006e140  mov     edx, esi; Type
0x18006e142  mov     [rbp+420h+AuditParameters.ParameterCount], r8d
0x18006e146  mov     r15d, esi
0x18006e149  call    cs:__imp_SeSetAuditParameter
0x18006e150  nop     dword ptr [rax+rax+00h]
0x18006e155  mov     ebx, eax
0x18006e157  test    eax, eax
0x18006e159  js      loc_18006E2AA
0x18006e15f  movzx   edx, [rbp+420h+arg_38]
0x18006e166  lea     r8, [rsp+520h+DestinationString]
0x18006e16b  add     [rbp+420h+AuditParameters.ParameterCount], r15d
0x18006e16f  mov     rcx, r12
0x18006e172  mov     sil, r14b
0x18006e175  call    CfgAdtpFormatPropertyBlock
0x18006e17a  test    eax, eax
0x18006e17c  js      short loc_18006E183
0x18006e17e  mov     dil, r15b
0x18006e181  jmp     short loc_18006E19E
0x18006e183  lea     rdx, asc_1800B32C0; "-"
0x18006e18a  mov     dil, r14b
0x18006e18d  lea     rcx, [rsp+520h+DestinationString]; DestinationString
0x18006e192  call    cs:__imp_RtlInitUnicodeString
0x18006e199  nop     dword ptr [rax+rax+00h]
0x18006e19e  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]; Index
0x18006e1a2  lea     r9, [rsp+520h+DestinationString]; Data
0x18006e1a7  mov     edx, r15d; Type
0x18006e1aa  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006e1ae  call    cs:__imp_SeSetAuditParameter
0x18006e1b5  nop     dword ptr [rax+rax+00h]
0x18006e1ba  mov     ebx, eax
0x18006e1bc  test    eax, eax
0x18006e1be  js      loc_18006E28C
0x18006e1c4  movzx   edx, [rbp+420h+arg_48]
0x18006e1cb  lea     r8, [rsp+520h+var_4C8]
0x18006e1d0  add     [rbp+420h+AuditParameters.ParameterCount], r15d
0x18006e1d4  mov     rcx, r13
0x18006e1d7  call    CfgAdtpFormatPropertyBlock
0x18006e1dc  test    eax, eax
0x18006e1de  js      short loc_18006E1E5
0x18006e1e0  mov     sil, r15b
0x18006e1e3  jmp     short loc_18006E1FD
0x18006e1e5  lea     rdx, asc_1800B32C0; "-"
0x18006e1ec  lea     rcx, [rsp+520h+var_4C8]; DestinationString
0x18006e1f1  call    cs:__imp_RtlInitUnicodeString
0x18006e1f8  nop     dword ptr [rax+rax+00h]
0x18006e1fd  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]; Index
0x18006e201  lea     r9, [rsp+520h+var_4C8]; Data
0x18006e206  mov     edx, r15d; Type
0x18006e209  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006e20d  call    cs:__imp_SeSetAuditParameter
0x18006e214  nop     dword ptr [rax+rax+00h]
0x18006e219  mov     ebx, eax
0x18006e21b  test    eax, eax
0x18006e21d  js      short loc_18006E28C
0x18006e21f  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]
0x18006e223  lea     r9, [rbp+420h+arg_50]; Data
0x18006e22a  add     r8d, r15d; Index
0x18006e22d  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18006e231  mov     edx, 0Ah; Type
0x18006e236  mov     [rbp+420h+AuditParameters.ParameterCount], r8d
0x18006e23a  call    cs:__imp_SeSetAuditParameter
0x18006e241  nop     dword ptr [rax+rax+00h]
0x18006e246  mov     ebx, eax
0x18006e248  test    eax, eax
0x18006e24a  js      short loc_18006E28C
0x18006e24c  add     [rbp+420h+AuditParameters.ParameterCount], r15d
0x18006e250  lea     rdx, aSecurity; "Security"
0x18006e257  lea     rcx, [rsp+520h+SourceName]; DestinationString
0x18006e25c  call    cs:__imp_RtlInitUnicodeString
0x18006e263  nop     dword ptr [rax+rax+00h]
0x18006e268  lea     r9, [rbp+420h+AuditParameters]; AuditParameters
0x18006e26c  mov     [rsp+520h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18006e274  xor     r8d, r8d; UserSid
0x18006e277  lea     rdx, [rsp+520h+SourceName]; SourceName
0x18006e27c  xor     ecx, ecx; Flags
0x18006e27e  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18006e285  nop     dword ptr [rax+rax+00h]
0x18006e28a  mov     ebx, eax
0x18006e28c  test    dil, dil
0x18006e28f  jz      short loc_18006E29B
0x18006e291  mov     rcx, [rsp+520h+DestinationString.Buffer]; P
0x18006e296  call    BCryptFree
0x18006e29b  test    sil, sil
0x18006e29e  jz      short loc_18006E2AA
0x18006e2a0  mov     rcx, [rsp+520h+var_4C8.Buffer]; P
0x18006e2a5  call    BCryptFree
0x18006e2aa  lea     rcx, [rsp+520h+SubjectContext]; SubjectContext
0x18006e2af  call    cs:__imp_SeReleaseSubjectContext
0x18006e2b6  nop     dword ptr [rax+rax+00h]
0x18006e2bb  mov     eax, ebx
0x18006e2bd  mov     rcx, [rbp+420h+var_40]
0x18006e2c4  xor     rcx, rsp; StackCookie
0x18006e2c7  call    __security_check_cookie
0x18006e2cc  mov     rbx, [rsp+520h+arg_0]
0x18006e2d4  add     rsp, 4F0h
0x18006e2db  pop     r15
0x18006e2dd  pop     r14
0x18006e2df  pop     r13
0x18006e2e1  pop     r12
0x18006e2e3  pop     rdi
0x18006e2e4  pop     rsi
0x18006e2e5  pop     rbp
0x18006e2e6  retn
```
