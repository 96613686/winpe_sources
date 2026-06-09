# CfgAdtReportContextModification

- ea: `0x1800777b4`
- end: `0x1800779c9`
- name: `CfgAdtReportContextModification`
- size: `533`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007446c`

## callees

- `0x1800777b4`
- `0x180078c80`
- `0x180078dc8`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180077962`
- `ntoskrnl!RtlInitUnicodeString` at `0x180077962`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180077998`
- `ntoskrnl!SeReleaseSubjectContext` at `0x180077998`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180077836`
- `ntoskrnl!SeCaptureSubjectContext` at `0x180077836`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x180077985`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x180077985`
- `ntoskrnl!SeSetAuditParameter` at `0x18007786d`
- `ntoskrnl!SeSetAuditParameter` at `0x1800778ae`
- `ntoskrnl!SeSetAuditParameter` at `0x1800778e2`
- `ntoskrnl!SeSetAuditParameter` at `0x180077913`
- `ntoskrnl!SeSetAuditParameter` at `0x180077940`
- `ntoskrnl!SeSetAuditParameter` at `0x18007786d`
- `ntoskrnl!SeSetAuditParameter` at `0x1800778ae`
- `ntoskrnl!SeSetAuditParameter` at `0x1800778e2`
- `ntoskrnl!SeSetAuditParameter` at `0x180077913`
- `ntoskrnl!SeSetAuditParameter` at `0x180077940`

## string_xrefs

- `0x180077956`: `Security`

## pseudocode

```c
__int64 CfgAdtReportContextModification(unsigned __int16 a1, int a2, __int64 *a3, int a4, ...)
{
  NTSTATUS appended; // ebx
  ULONG v7; // r8d
  __int64 *v8; // r9
  int Data; // [rsp+30h] [rbp-D0h] BYREF
  int v11; // [rsp+38h] [rbp-C8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-C0h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+50h] [rbp-B0h] BYREF
  _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+70h] [rbp-90h] BYREF
  __int64 v15; // [rsp+4E0h] [rbp+3E0h] BYREF
  va_list va; // [rsp+4E0h] [rbp+3E0h]
  va_list va1; // [rsp+4E8h] [rbp+3E8h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v15 = va_arg(va1, _QWORD);
  Data = a2;
  v11 = a4;
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  DestinationString = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  appended = CfgAdtpInitializeParameters(&AuditParameters, a1, 5065);
  if ( appended >= 0 )
  {
    SeCaptureSubjectContext(&SubjectContext);
    appended = CfgAdtpAppendSecuritySubjectInfo(&AuditParameters);
    if ( appended >= 0 )
    {
      appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeMessage, AuditParameters.ParameterCount, &Data);
      if ( appended >= 0 )
      {
        v7 = ++AuditParameters.ParameterCount;
        if ( !a3 || (v8 = a3, !*(_WORD *)a3) )
          v8 = &qword_1800AF9A0;
        appended = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeString, v7, v8);
        if ( appended >= 0 )
        {
          appended = SeSetAuditParameter(
                       &AuditParameters,
                       SeAdtParmTypeHexUlong,
                       ++AuditParameters.ParameterCount,
                       &v11);
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
                ++AuditParameters.ParameterCount;
                RtlInitUnicodeString(&DestinationString, L"Security");
                appended = SeReportSecurityEventWithSubCategory(0, &DestinationString, 0, &AuditParameters, 0x91u);
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
0x1800777b4  mov     [rsp-8+arg_0], rbx
0x1800777b9  push    rbp
0x1800777ba  push    rsi
0x1800777bb  push    rdi
0x1800777bc  lea     rbp, [rsp-3A0h]
0x1800777c4  sub     rsp, 4A0h
0x1800777cb  mov     rax, cs:__security_cookie
0x1800777d2  xor     rax, rsp
0x1800777d5  mov     [rbp+3B0h+var_20], rax
0x1800777dc  mov     rdi, r8
0x1800777df  mov     [rsp+4B0h+Data], edx
0x1800777e3  movzx   ebx, cx
0x1800777e6  mov     [rsp+4B0h+var_478], r9d
0x1800777eb  xor     edx, edx; Val
0x1800777ed  lea     rcx, [rsp+4B0h+AuditParameters]; void *
0x1800777f2  mov     r8d, 418h; Size
0x1800777f8  call    memset
0x1800777fd  xorps   xmm1, xmm1
0x180077800  lea     rcx, [rsp+4B0h+AuditParameters]
0x180077805  xorps   xmm0, xmm0
0x180077808  mov     r8d, 13C9h
0x18007780e  movzx   edx, bx
0x180077811  movups  xmmword ptr [rsp+4B0h+DestinationString.Length], xmm0
0x180077816  movups  xmmword ptr [rsp+4B0h+SubjectContext.ClientToken], xmm1
0x18007781b  movups  xmmword ptr [rsp+4B0h+SubjectContext.PrimaryToken], xmm1
0x180077820  call    CfgAdtpInitializeParameters
0x180077825  xor     esi, esi
0x180077827  mov     ebx, eax
0x180077829  test    eax, eax
0x18007782b  js      loc_1800779A4
0x180077831  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x180077836  call    cs:__imp_SeCaptureSubjectContext
0x18007783d  nop     dword ptr [rax+rax+00h]
0x180077842  lea     rdx, [rsp+4B0h+SubjectContext]
0x180077847  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18007784c  call    CfgAdtpAppendSecuritySubjectInfo
0x180077851  mov     ebx, eax
0x180077853  test    eax, eax
0x180077855  js      loc_180077993
0x18007785b  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]; Index
0x180077860  lea     r9, [rsp+4B0h+Data]; Data
0x180077865  lea     edx, [rsi+15h]; Type
0x180077868  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18007786d  call    cs:__imp_SeSetAuditParameter
0x180077874  nop     dword ptr [rax+rax+00h]
0x180077879  mov     ebx, eax
0x18007787b  test    eax, eax
0x18007787d  js      loc_180077993
0x180077883  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x180077888  inc     r8d; Index
0x18007788b  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x180077890  test    rdi, rdi
0x180077893  jz      short loc_18007789D
0x180077895  mov     r9, rdi
0x180077898  cmp     [rdi], si
0x18007789b  jnz     short loc_1800778A4
0x18007789d  lea     r9, qword_1800AF9A0; Data
0x1800778a4  mov     edx, 1; Type
0x1800778a9  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x1800778ae  call    cs:__imp_SeSetAuditParameter
0x1800778b5  nop     dword ptr [rax+rax+00h]
0x1800778ba  mov     ebx, eax
0x1800778bc  test    eax, eax
0x1800778be  js      loc_180077993
0x1800778c4  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x1800778c9  lea     r9, [rsp+4B0h+var_478]; Data
0x1800778ce  inc     r8d; Index
0x1800778d1  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x1800778d6  mov     edi, 0Ah
0x1800778db  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x1800778e0  mov     edx, edi; Type
0x1800778e2  call    cs:__imp_SeSetAuditParameter
0x1800778e9  nop     dword ptr [rax+rax+00h]
0x1800778ee  mov     ebx, eax
0x1800778f0  test    eax, eax
0x1800778f2  js      loc_180077993
0x1800778f8  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x1800778fd  lea     r9, [rbp+3B0h+arg_20]; Data
0x180077904  inc     r8d; Index
0x180077907  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x18007790c  mov     edx, edi; Type
0x18007790e  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x180077913  call    cs:__imp_SeSetAuditParameter
0x18007791a  nop     dword ptr [rax+rax+00h]
0x18007791f  mov     ebx, eax
0x180077921  test    eax, eax
0x180077923  js      short loc_180077993
0x180077925  mov     r8d, [rsp+4B0h+AuditParameters.ParameterCount]
0x18007792a  lea     r9, [rbp+3B0h+arg_28]; Data
0x180077931  inc     r8d; Index
0x180077934  lea     rcx, [rsp+4B0h+AuditParameters]; AuditParameters
0x180077939  mov     edx, edi; Type
0x18007793b  mov     [rsp+4B0h+AuditParameters.ParameterCount], r8d
0x180077940  call    cs:__imp_SeSetAuditParameter
0x180077947  nop     dword ptr [rax+rax+00h]
0x18007794c  mov     ebx, eax
0x18007794e  test    eax, eax
0x180077950  js      short loc_180077993
0x180077952  inc     [rsp+4B0h+AuditParameters.ParameterCount]
0x180077956  lea     rdx, aSecurity; "Security"
0x18007795d  lea     rcx, [rsp+4B0h+DestinationString]; DestinationString
0x180077962  call    cs:__imp_RtlInitUnicodeString
0x180077969  nop     dword ptr [rax+rax+00h]
0x18007796e  lea     r9, [rsp+4B0h+AuditParameters]; AuditParameters
0x180077973  mov     [rsp+4B0h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x18007797b  xor     r8d, r8d; UserSid
0x18007797e  lea     rdx, [rsp+4B0h+DestinationString]; SourceName
0x180077983  xor     ecx, ecx; Flags
0x180077985  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x18007798c  nop     dword ptr [rax+rax+00h]
0x180077991  mov     ebx, eax
0x180077993  lea     rcx, [rsp+4B0h+SubjectContext]; SubjectContext
0x180077998  call    cs:__imp_SeReleaseSubjectContext
0x18007799f  nop     dword ptr [rax+rax+00h]
0x1800779a4  mov     eax, ebx
0x1800779a6  mov     rcx, [rbp+3B0h+var_20]
0x1800779ad  xor     rcx, rsp; StackCookie
0x1800779b0  call    __security_check_cookie
0x1800779b5  mov     rbx, [rsp+4B0h+arg_0]
0x1800779bd  add     rsp, 4A0h
0x1800779c4  pop     rdi
0x1800779c5  pop     rsi
0x1800779c6  pop     rbp
0x1800779c7  retn
```
