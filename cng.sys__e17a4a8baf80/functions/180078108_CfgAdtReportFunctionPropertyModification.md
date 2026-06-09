# CfgAdtReportFunctionPropertyModification

- ea: `0x180078108`
- end: `0x180078488`
- name: `CfgAdtReportFunctionPropertyModification`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180076154`

## callees

- `0x180025ec0`
- `0x180078108`
- `0x180078c80`
- `0x180078ce4`
- `0x180078dc8`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x180078332`
- `ntoskrnl!RtlInitUnicodeString` at `0x180078391`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800783fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x180078332`
- `ntoskrnl!RtlInitUnicodeString` at `0x180078391`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800783fc`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18007844f`
- `ntoskrnl!SeReleaseSubjectContext` at `0x18007844f`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1800781b6`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1800781b6`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18007841e`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x18007841e`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180078265`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180078265`
- `ntoskrnl!SeSetAuditParameter` at `0x1800781ec`
- `ntoskrnl!SeSetAuditParameter` at `0x18007822c`
- `ntoskrnl!SeSetAuditParameter` at `0x18007828f`
- `ntoskrnl!SeSetAuditParameter` at `0x1800782b9`
- `ntoskrnl!SeSetAuditParameter` at `0x1800782e9`
- `ntoskrnl!SeSetAuditParameter` at `0x18007834e`
- `ntoskrnl!SeSetAuditParameter` at `0x1800783ad`
- `ntoskrnl!SeSetAuditParameter` at `0x1800783da`
- `ntoskrnl!SeSetAuditParameter` at `0x1800781ec`
- `ntoskrnl!SeSetAuditParameter` at `0x18007822c`
- `ntoskrnl!SeSetAuditParameter` at `0x18007828f`
- `ntoskrnl!SeSetAuditParameter` at `0x1800782b9`
- `ntoskrnl!SeSetAuditParameter` at `0x1800782e9`
- `ntoskrnl!SeSetAuditParameter` at `0x18007834e`
- `ntoskrnl!SeSetAuditParameter` at `0x1800783ad`
- `ntoskrnl!SeSetAuditParameter` at `0x1800783da`

## string_xrefs

- `0x1800783f0`: `Security`

## pseudocode

```c
__int64 CfgAdtReportFunctionPropertyModification(
        unsigned __int16 a1,
        int a2,
        __int64 *a3,
        ULONG a4,
        PVOID a5,
        PVOID a6,
        __int64 a7,
        unsigned __int16 a8,
        __int64 a9,
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
          v15 = &qword_1800AF9A0;
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
                  if ( (int)CfgAdtpFormatPropertyBlock(a7, a8, &DestinationString) < 0 )
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
                    if ( (int)CfgAdtpFormatPropertyBlock(a9, a10, &v22) < 0 )
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
0x180078108  mov     [rsp-8+arg_0], rbx
0x18007810d  push    rbp
0x18007810e  push    rsi
0x18007810f  push    rdi
0x180078110  push    r12
0x180078112  push    r13
0x180078114  push    r14
0x180078116  push    r15
0x180078118  lea     rbp, [rsp-3F0h]
0x180078120  sub     rsp, 4F0h
0x180078127  mov     rax, cs:__security_cookie
0x18007812e  xor     rax, rsp
0x180078131  mov     [rbp+420h+var_40], rax
0x180078138  mov     r14, [rbp+420h+arg_20]
0x18007813f  mov     rdi, r8
0x180078142  mov     r15, [rbp+420h+arg_28]
0x180078149  movzx   ebx, cx
0x18007814c  mov     r12, [rbp+420h+arg_30]
0x180078153  lea     rcx, [rbp+420h+AuditParameters]; void *
0x180078157  mov     r13, [rbp+420h+arg_40]
0x18007815e  mov     r8d, 418h; Size
0x180078164  mov     [rsp+520h+Data], edx
0x180078168  mov     esi, r9d
0x18007816b  xor     edx, edx; Val
0x18007816d  call    memset
0x180078172  xorps   xmm0, xmm0
0x180078175  lea     rcx, [rbp+420h+AuditParameters]
0x180078179  xorps   xmm1, xmm1
0x18007817c  mov     r8d, 13CEh
0x180078182  movzx   edx, bx
0x180078185  movups  xmmword ptr [rsp+520h+SourceName.Length], xmm0
0x18007818a  movups  xmmword ptr [rsp+520h+SubjectContext.ClientToken], xmm1
0x18007818f  movups  xmmword ptr [rbp+420h+SubjectContext.PrimaryToken], xmm1
0x180078193  movups  xmmword ptr [rsp+520h+DestinationString.Length], xmm0
0x180078198  movups  xmmword ptr [rsp+520h+var_4C8.Length], xmm1
0x18007819d  movups  xmmword ptr [rsp+520h+String.Length], xmm0
0x1800781a2  call    CfgAdtpInitializeParameters
0x1800781a7  mov     ebx, eax
0x1800781a9  test    eax, eax
0x1800781ab  js      loc_18007845B
0x1800781b1  lea     rcx, [rsp+520h+SubjectContext]; SubjectContext
0x1800781b6  call    cs:__imp_SeCaptureSubjectContext
0x1800781bd  nop     dword ptr [rax+rax+00h]
0x1800781c2  lea     rdx, [rsp+520h+SubjectContext]
0x1800781c7  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x1800781cb  call    CfgAdtpAppendSecuritySubjectInfo
0x1800781d0  mov     ebx, eax
0x1800781d2  test    eax, eax
0x1800781d4  js      loc_18007844A
0x1800781da  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]; Index
0x1800781de  lea     r9, [rsp+520h+Data]; Data
0x1800781e3  mov     edx, 15h; Type
0x1800781e8  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x1800781ec  call    cs:__imp_SeSetAuditParameter
0x1800781f3  nop     dword ptr [rax+rax+00h]
0x1800781f8  mov     ebx, eax
0x1800781fa  xor     eax, eax
0x1800781fc  test    ebx, ebx
0x1800781fe  js      loc_18007844A
0x180078204  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]
0x180078208  lea     ecx, [rax+1]
0x18007820b  add     r8d, ecx; Index
0x18007820e  mov     [rbp+420h+AuditParameters.ParameterCount], r8d
0x180078212  test    rdi, rdi
0x180078215  jz      short loc_18007821F
0x180078217  mov     r9, rdi
0x18007821a  cmp     [rdi], ax
0x18007821d  jnz     short loc_180078226
0x18007821f  lea     r9, qword_1800AF9A0; Data
0x180078226  mov     edx, ecx; Type
0x180078228  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18007822c  call    cs:__imp_SeSetAuditParameter
0x180078233  nop     dword ptr [rax+rax+00h]
0x180078238  mov     ebx, eax
0x18007823a  test    eax, eax
0x18007823c  js      loc_18007844A
0x180078242  inc     [rbp+420h+AuditParameters.ParameterCount]
0x180078245  lea     rax, [rbp+420h+var_60]
0x18007824c  lea     r8, [rsp+520h+String]; String
0x180078251  mov     [rsp+520h+String.Buffer], rax
0x180078256  mov     edx, 0Ah; Base
0x18007825b  mov     dword ptr [rsp+520h+String.Length], 200000h
0x180078263  mov     ecx, esi; Value
0x180078265  call    cs:__imp_RtlIntegerToUnicodeString
0x18007826c  nop     dword ptr [rax+rax+00h]
0x180078271  mov     ebx, eax
0x180078273  test    eax, eax
0x180078275  js      loc_18007844A
0x18007827b  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]; Index
0x18007827f  lea     r9, [rsp+520h+String]; Data
0x180078284  mov     esi, 1
0x180078289  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18007828d  mov     edx, esi; Type
0x18007828f  call    cs:__imp_SeSetAuditParameter
0x180078296  nop     dword ptr [rax+rax+00h]
0x18007829b  mov     ebx, eax
0x18007829d  test    eax, eax
0x18007829f  js      loc_18007844A
0x1800782a5  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]
0x1800782a9  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x1800782ad  add     r8d, esi; Index
0x1800782b0  mov     r9, r14; Data
0x1800782b3  mov     edx, esi; Type
0x1800782b5  mov     [rbp+420h+AuditParameters.ParameterCount], r8d
0x1800782b9  call    cs:__imp_SeSetAuditParameter
0x1800782c0  nop     dword ptr [rax+rax+00h]
0x1800782c5  xor     r14d, r14d
0x1800782c8  mov     ebx, eax
0x1800782ca  test    eax, eax
0x1800782cc  js      loc_18007844A
0x1800782d2  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]
0x1800782d6  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x1800782da  add     r8d, esi; Index
0x1800782dd  mov     r9, r15; Data
0x1800782e0  mov     edx, esi; Type
0x1800782e2  mov     [rbp+420h+AuditParameters.ParameterCount], r8d
0x1800782e6  mov     r15d, esi
0x1800782e9  call    cs:__imp_SeSetAuditParameter
0x1800782f0  nop     dword ptr [rax+rax+00h]
0x1800782f5  mov     ebx, eax
0x1800782f7  test    eax, eax
0x1800782f9  js      loc_18007844A
0x1800782ff  movzx   edx, [rbp+420h+arg_38]
0x180078306  lea     r8, [rsp+520h+DestinationString]
0x18007830b  add     [rbp+420h+AuditParameters.ParameterCount], r15d
0x18007830f  mov     rcx, r12
0x180078312  mov     sil, r14b
0x180078315  call    CfgAdtpFormatPropertyBlock
0x18007831a  test    eax, eax
0x18007831c  js      short loc_180078323
0x18007831e  mov     dil, r15b
0x180078321  jmp     short loc_18007833E
0x180078323  lea     rdx, asc_1800BAEC0; "-"
0x18007832a  mov     dil, r14b
0x18007832d  lea     rcx, [rsp+520h+DestinationString]; DestinationString
0x180078332  call    cs:__imp_RtlInitUnicodeString
0x180078339  nop     dword ptr [rax+rax+00h]
0x18007833e  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]; Index
0x180078342  lea     r9, [rsp+520h+DestinationString]; Data
0x180078347  mov     edx, r15d; Type
0x18007834a  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x18007834e  call    cs:__imp_SeSetAuditParameter
0x180078355  nop     dword ptr [rax+rax+00h]
0x18007835a  mov     ebx, eax
0x18007835c  test    eax, eax
0x18007835e  js      loc_18007842C
0x180078364  movzx   edx, [rbp+420h+arg_48]
0x18007836b  lea     r8, [rsp+520h+var_4C8]
0x180078370  add     [rbp+420h+AuditParameters.ParameterCount], r15d
0x180078374  mov     rcx, r13
0x180078377  call    CfgAdtpFormatPropertyBlock
0x18007837c  test    eax, eax
0x18007837e  js      short loc_180078385
0x180078380  mov     sil, r15b
0x180078383  jmp     short loc_18007839D
0x180078385  lea     rdx, asc_1800BAEC0; "-"
0x18007838c  lea     rcx, [rsp+520h+var_4C8]; DestinationString
0x180078391  call    cs:__imp_RtlInitUnicodeString
0x180078398  nop     dword ptr [rax+rax+00h]
0x18007839d  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]; Index
0x1800783a1  lea     r9, [rsp+520h+var_4C8]; Data
0x1800783a6  mov     edx, r15d; Type
0x1800783a9  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x1800783ad  call    cs:__imp_SeSetAuditParameter
0x1800783b4  nop     dword ptr [rax+rax+00h]
0x1800783b9  mov     ebx, eax
0x1800783bb  test    eax, eax
0x1800783bd  js      short loc_18007842C
0x1800783bf  mov     r8d, [rbp+420h+AuditParameters.ParameterCount]
0x1800783c3  lea     r9, [rbp+420h+arg_50]; Data
0x1800783ca  add     r8d, r15d; Index
0x1800783cd  lea     rcx, [rbp+420h+AuditParameters]; AuditParameters
0x1800783d1  mov     edx, 0Ah; Type
0x1800783d6  mov     [rbp+420h+AuditParameters.ParameterCount], r8d
0x1800783da  call    cs:__imp_SeSetAuditParameter
0x1800783e1  nop     dword ptr [rax+rax+00h]
0x1800783e6  mov     ebx, eax
0x1800783e8  test    eax, eax
0x1800783ea  js      short loc_18007842C
0x1800783ec  add     [rbp+420h+AuditParameters.ParameterCount], r15d
0x1800783f0  lea     rdx, aSecurity; "Security"
0x1800783f7  lea     rcx, [rsp+520h+SourceName]; DestinationString
0x1800783fc  call    cs:__imp_RtlInitUnicodeString
0x180078403  nop     dword ptr [rax+rax+00h]
0x180078408  lea     r9, [rbp+420h+AuditParameters]; AuditParameters
0x18007840c  mov     [rsp+520h+AuditSubcategoryId], 91h; AuditSubcategoryId
0x180078414  xor     r8d, r8d; UserSid
0x180078417  lea     rdx, [rsp+520h+SourceName]; SourceName
0x18007841c  xor     ecx, ecx; Flags
0x18007841e  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x180078425  nop     dword ptr [rax+rax+00h]
0x18007842a  mov     ebx, eax
0x18007842c  test    dil, dil
0x18007842f  jz      short loc_18007843B
0x180078431  mov     rcx, [rsp+520h+DestinationString.Buffer]; P
0x180078436  call    BCryptFree
0x18007843b  test    sil, sil
0x18007843e  jz      short loc_18007844A
0x180078440  mov     rcx, [rsp+520h+var_4C8.Buffer]; P
0x180078445  call    BCryptFree
0x18007844a  lea     rcx, [rsp+520h+SubjectContext]; SubjectContext
0x18007844f  call    cs:__imp_SeReleaseSubjectContext
0x180078456  nop     dword ptr [rax+rax+00h]
0x18007845b  mov     eax, ebx
0x18007845d  mov     rcx, [rbp+420h+var_40]
0x180078464  xor     rcx, rsp; StackCookie
0x180078467  call    __security_check_cookie
0x18007846c  mov     rbx, [rsp+520h+arg_0]
0x180078474  add     rsp, 4F0h
0x18007847b  pop     r15
0x18007847d  pop     r14
0x18007847f  pop     r13
0x180078481  pop     r12
0x180078483  pop     rdi
0x180078484  pop     rsi
0x180078485  pop     rbp
0x180078486  retn
```
