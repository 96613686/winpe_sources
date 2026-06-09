# LuafvReportAuditVirtualizationEvent

- ea: `0x140016e78`
- end: `0x14001713a`
- name: `LuafvReportAuditVirtualizationEvent`
- size: `706`
- prototype: `__int64 __fastcall(PACL ResourceSacl, PFLT_CALLBACK_DATA CallbackData, PVOID Data, PVOID)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002698`

## callees

- `0x140005bb0`
- `0x140006000`
- `0x140016e78`

## import_xrefs

- `ntoskrnl!SeExamineSacl` at `0x140016f4d`
- `ntoskrnl!SeExamineSacl` at `0x140016f4d`
- `ntoskrnl!SeSetAuditParameter` at `0x140016fd2`
- `ntoskrnl!SeSetAuditParameter` at `0x140017001`
- `ntoskrnl!SeSetAuditParameter` at `0x14001702b`
- `ntoskrnl!SeSetAuditParameter` at `0x140017061`
- `ntoskrnl!SeSetAuditParameter` at `0x1400170be`
- `ntoskrnl!SeSetAuditParameter` at `0x140016fd2`
- `ntoskrnl!SeSetAuditParameter` at `0x140017001`
- `ntoskrnl!SeSetAuditParameter` at `0x14001702b`
- `ntoskrnl!SeSetAuditParameter` at `0x140017061`
- `ntoskrnl!SeSetAuditParameter` at `0x1400170be`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x1400170eb`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x1400170eb`
- `ntoskrnl!SeLocateProcessImageName` at `0x14001709d`
- `ntoskrnl!SeLocateProcessImageName` at `0x14001709d`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140016f66`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140016f66`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140016faa`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140016faa`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140016f0a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140016f0a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017108`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017108`
- `FLTMGR!FltGetRequestorProcessId` at `0x140017047`
- `FLTMGR!FltGetRequestorProcessId` at `0x140017047`
- `FLTMGR!FltGetRequestorProcess` at `0x14001707d`
- `FLTMGR!FltGetRequestorProcess` at `0x14001707d`

## pseudocode

```c
__int64 __fastcall LuafvReportAuditVirtualizationEvent(
        PACL ResourceSacl,
        PFLT_CALLBACK_DATA CallbackData,
        PVOID Data,
        PVOID a4)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  char v9; // si
  struct _SECURITY_SUBJECT_CONTEXT *p_SubjectContext; // rbx
  PACCESS_TOKEN ClientToken; // rdi
  NTSTATUS v12; // ebx
  ULONG RequestorProcessId; // eax
  struct _KPROCESS *RequestorProcess; // rax
  unsigned __int8 GenerateAudit; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 GenerateAlarm[7]; // [rsp+41h] [rbp-BFh] BYREF
  PUNICODE_STRING pImageFileName; // [rsp+48h] [rbp-B8h] BYREF
  struct _LUID AuthenticationId; // [rsp+50h] [rbp-B0h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+58h] [rbp-A8h] BYREF
  _SE_ADT_PARAMETER_ARRAY AuditParameters; // [rsp+80h] [rbp-80h] BYREF

  GenerateAudit = 0;
  GenerateAlarm[0] = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  memset(&AuditParameters, 0, sizeof(AuditParameters));
  Iopb = CallbackData->Iopb;
  AuthenticationId = 0;
  pImageFileName = 0;
  if ( Iopb->MajorFunction )
  {
    p_SubjectContext = &SubjectContext;
    SeCaptureSubjectContext(&SubjectContext);
    v9 = 1;
  }
  else
  {
    v9 = 0;
    p_SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(Iopb->Parameters.WMI.ProviderId + 8) + 32LL);
  }
  ClientToken = p_SubjectContext->ClientToken;
  if ( !p_SubjectContext->ClientToken )
    ClientToken = p_SubjectContext->PrimaryToken;
  SeExamineSacl(ResourceSacl, ResourceSacl, ClientToken, 0x1F01FFu, 1u, &GenerateAudit, GenerateAlarm);
  if ( v9 )
    SeReleaseSubjectContext(&SubjectContext);
  if ( GenerateAudit || (v12 = 0, GenerateAlarm[0]) )
  {
    AuditParameters.CategoryId = 3;
    *(_QWORD *)&AuditParameters.AuditId = 5051;
    AuditParameters.Length = 0;
    *(_QWORD *)&AuditParameters.FlatSubCategoryId = 0x80000;
    v12 = SeQueryAuthenticationIdToken(ClientToken, &AuthenticationId);
    if ( v12 >= 0 )
    {
      v12 = SeSetAuditParameter(
              &AuditParameters,
              SeAdtParmTypeLogonId,
              AuditParameters.ParameterCount,
              &AuthenticationId);
      if ( v12 >= 0 )
      {
        v12 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeFileSpec, ++AuditParameters.ParameterCount, Data);
        if ( v12 >= 0 )
        {
          v12 = SeSetAuditParameter(&AuditParameters, SeAdtParmTypeFileSpec, ++AuditParameters.ParameterCount, a4);
          if ( v12 >= 0 )
          {
            ++AuditParameters.ParameterCount;
            RequestorProcessId = FltGetRequestorProcessId(CallbackData);
            v12 = SeSetAuditParameter(
                    &AuditParameters,
                    SeAdtParmTypePtr,
                    AuditParameters.ParameterCount,
                    (PVOID)RequestorProcessId);
            if ( v12 >= 0 )
            {
              ++AuditParameters.ParameterCount;
              RequestorProcess = FltGetRequestorProcess(CallbackData);
              if ( RequestorProcess )
              {
                v12 = SeLocateProcessImageName(RequestorProcess, &pImageFileName);
                if ( v12 >= 0 )
                {
                  v12 = SeSetAuditParameter(
                          &AuditParameters,
                          SeAdtParmTypeFileSpec,
                          AuditParameters.ParameterCount,
                          pImageFileName);
                  if ( v12 >= 0 )
                  {
                    ++AuditParameters.ParameterCount;
                    v12 = SeReportSecurityEventWithSubCategory(0, &LuafvAuditSource, 0, &AuditParameters, 0x75u);
                  }
                }
              }
              else
              {
                v12 = -1073740004;
              }
            }
          }
        }
      }
    }
  }
  if ( pImageFileName )
    ExFreePoolWithTag(pImageFileName, 0x61506553u);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140016e78  push    rbp
0x140016e7a  push    rbx
0x140016e7b  push    rsi
0x140016e7c  push    rdi
0x140016e7d  push    r12
0x140016e7f  push    r13
0x140016e81  push    r14
0x140016e83  push    r15
0x140016e85  lea     rbp, [rsp-3B8h]
0x140016e8d  sub     rsp, 4B8h
0x140016e94  mov     rax, cs:__security_cookie
0x140016e9b  xor     rax, rsp
0x140016e9e  mov     [rbp+3F0h+var_50], rax
0x140016ea5  xorps   xmm0, xmm0
0x140016ea8  mov     r12, r8
0x140016eab  mov     r14, rdx
0x140016eae  mov     r15, rcx
0x140016eb1  xor     edi, edi
0x140016eb3  lea     rcx, [rbp+3F0h+AuditParameters]; void *
0x140016eb7  xor     edx, edx; Val
0x140016eb9  mov     [rsp+4F0h+var_4B0], dil
0x140016ebe  mov     r8d, 418h; Size
0x140016ec4  mov     [rsp+4F0h+var_4AF], dil
0x140016ec9  movups  xmmword ptr [rsp+4F0h+SubjectContext.ClientToken], xmm0
0x140016ece  mov     r13, r9
0x140016ed1  movups  xmmword ptr [rsp+4F0h+SubjectContext.PrimaryToken], xmm0
0x140016ed6  call    memset
0x140016edb  mov     rax, [r14+10h]
0x140016edf  mov     qword ptr [rsp+4F0h+AuthenticationId.LowPart], rdi
0x140016ee4  mov     [rsp+4F0h+pImageFileName], rdi
0x140016ee9  cmp     [rax+4], dil
0x140016eed  jnz     short loc_140016F00
0x140016eef  mov     rax, [rax+18h]
0x140016ef3  mov     sil, dil
0x140016ef6  mov     rbx, [rax+8]
0x140016efa  add     rbx, 20h ; ' '
0x140016efe  jmp     short loc_140016F19
0x140016f00  lea     rcx, [rsp+4F0h+SubjectContext]; SubjectContext
0x140016f05  lea     rbx, [rsp+4F0h+SubjectContext]
0x140016f0a  call    cs:__imp_SeCaptureSubjectContext
0x140016f11  nop     dword ptr [rax+rax+00h]
0x140016f16  mov     sil, 1
0x140016f19  mov     rdi, [rbx]
0x140016f1c  test    rdi, rdi
0x140016f1f  jnz     short loc_140016F25
0x140016f21  mov     rdi, [rbx+10h]
0x140016f25  lea     rax, [rsp+4F0h+var_4AF]
0x140016f2a  mov     r9d, 1F01FFh; DesiredAccess
0x140016f30  mov     [rsp+4F0h+GenerateAlarm], rax; GenerateAlarm
0x140016f35  mov     r8, rdi; Token
0x140016f38  lea     rax, [rsp+4F0h+var_4B0]
0x140016f3d  mov     rdx, r15; ResourceSacl
0x140016f40  mov     [rsp+4F0h+GenerateAudit], rax; GenerateAudit
0x140016f45  mov     rcx, r15; Sacl
0x140016f48  mov     [rsp+4F0h+AccessGranted], 1; AccessGranted
0x140016f4d  call    cs:__imp_SeExamineSacl
0x140016f54  nop     dword ptr [rax+rax+00h]
0x140016f59  xor     r15d, r15d
0x140016f5c  test    sil, sil
0x140016f5f  jz      short loc_140016F72
0x140016f61  lea     rcx, [rsp+4F0h+SubjectContext]; SubjectContext
0x140016f66  call    cs:__imp_SeReleaseSubjectContext
0x140016f6d  nop     dword ptr [rax+rax+00h]
0x140016f72  cmp     [rsp+4F0h+var_4B0], r15b
0x140016f77  jnz     short loc_140016F87
0x140016f79  mov     ebx, r15d
0x140016f7c  cmp     [rsp+4F0h+var_4AF], r15b
0x140016f81  jz      loc_1400170F9
0x140016f87  lea     rdx, [rsp+4F0h+AuthenticationId]; AuthenticationId
0x140016f8c  mov     [rbp+3F0h+AuditParameters.CategoryId], 3
0x140016f93  mov     rcx, rdi; Token
0x140016f96  mov     qword ptr [rbp+3F0h+AuditParameters.AuditId], 13BBh
0x140016f9e  mov     [rbp+3F0h+AuditParameters.Length], r15d
0x140016fa2  mov     qword ptr [rbp+3F0h+AuditParameters.FlatSubCategoryId], 80000h
0x140016faa  call    cs:__imp_SeQueryAuthenticationIdToken
0x140016fb1  nop     dword ptr [rax+rax+00h]
0x140016fb6  mov     ebx, eax
0x140016fb8  test    eax, eax
0x140016fba  js      loc_1400170F9
0x140016fc0  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]; Index
0x140016fc4  lea     r9, [rsp+4F0h+AuthenticationId]; Data
0x140016fc9  mov     edx, 5; Type
0x140016fce  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140016fd2  call    cs:__imp_SeSetAuditParameter
0x140016fd9  nop     dword ptr [rax+rax+00h]
0x140016fde  mov     ebx, eax
0x140016fe0  test    eax, eax
0x140016fe2  js      loc_1400170F9
0x140016fe8  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]
0x140016fec  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140016ff0  inc     r8d; Index
0x140016ff3  mov     edi, 2
0x140016ff8  mov     r9, r12; Data
0x140016ffb  mov     [rbp+3F0h+AuditParameters.ParameterCount], r8d
0x140016fff  mov     edx, edi; Type
0x140017001  call    cs:__imp_SeSetAuditParameter
0x140017008  nop     dword ptr [rax+rax+00h]
0x14001700d  mov     ebx, eax
0x14001700f  test    eax, eax
0x140017011  js      loc_1400170F9
0x140017017  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]
0x14001701b  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x14001701f  inc     r8d; Index
0x140017022  mov     r9, r13; Data
0x140017025  mov     edx, edi; Type
0x140017027  mov     [rbp+3F0h+AuditParameters.ParameterCount], r8d
0x14001702b  call    cs:__imp_SeSetAuditParameter
0x140017032  nop     dword ptr [rax+rax+00h]
0x140017037  mov     ebx, eax
0x140017039  test    eax, eax
0x14001703b  js      loc_1400170F9
0x140017041  inc     [rbp+3F0h+AuditParameters.ParameterCount]
0x140017044  mov     rcx, r14; CallbackData
0x140017047  call    cs:__imp_FltGetRequestorProcessId
0x14001704e  nop     dword ptr [rax+rax+00h]
0x140017053  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]; Index
0x140017057  lea     edx, [rdi+9]; Type
0x14001705a  mov     r9d, eax; Data
0x14001705d  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140017061  call    cs:__imp_SeSetAuditParameter
0x140017068  nop     dword ptr [rax+rax+00h]
0x14001706d  mov     ebx, eax
0x14001706f  test    eax, eax
0x140017071  js      loc_1400170F9
0x140017077  inc     [rbp+3F0h+AuditParameters.ParameterCount]
0x14001707a  mov     rcx, r14; CallbackData
0x14001707d  call    cs:__imp_FltGetRequestorProcess
0x140017084  nop     dword ptr [rax+rax+00h]
0x140017089  test    rax, rax
0x14001708c  jnz     short loc_140017095
0x14001708e  mov     ebx, 0C000071Ch
0x140017093  jmp     short loc_1400170F9
0x140017095  lea     rdx, [rsp+4F0h+pImageFileName]; pImageFileName
0x14001709a  mov     rcx, rax; Process
0x14001709d  call    cs:__imp_SeLocateProcessImageName
0x1400170a4  nop     dword ptr [rax+rax+00h]
0x1400170a9  mov     ebx, eax
0x1400170ab  test    eax, eax
0x1400170ad  js      short loc_1400170F9
0x1400170af  mov     r9, [rsp+4F0h+pImageFileName]; Data
0x1400170b4  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x1400170b8  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]; Index
0x1400170bc  mov     edx, edi; Type
0x1400170be  call    cs:__imp_SeSetAuditParameter
0x1400170c5  nop     dword ptr [rax+rax+00h]
0x1400170ca  mov     ebx, eax
0x1400170cc  test    eax, eax
0x1400170ce  js      short loc_1400170F9
0x1400170d0  inc     [rbp+3F0h+AuditParameters.ParameterCount]
0x1400170d3  lea     r9, [rbp+3F0h+AuditParameters]; AuditParameters
0x1400170d7  xor     r8d, r8d; UserSid
0x1400170da  mov     dword ptr [rsp+4F0h+AccessGranted], 75h ; 'u'; AuditSubcategoryId
0x1400170e2  lea     rdx, LuafvAuditSource; SourceName
0x1400170e9  xor     ecx, ecx; Flags
0x1400170eb  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x1400170f2  nop     dword ptr [rax+rax+00h]
0x1400170f7  mov     ebx, eax
0x1400170f9  mov     rcx, [rsp+4F0h+pImageFileName]; P
0x1400170fe  test    rcx, rcx
0x140017101  jz      short loc_140017114
0x140017103  mov     edx, 61506553h; Tag
0x140017108  call    cs:__imp_ExFreePoolWithTag
0x14001710f  nop     dword ptr [rax+rax+00h]
0x140017114  mov     eax, ebx
0x140017116  mov     rcx, [rbp+3F0h+var_50]
0x14001711d  xor     rcx, rsp; StackCookie
0x140017120  call    __security_check_cookie
0x140017125  add     rsp, 4B8h
0x14001712c  pop     r15
0x14001712e  pop     r14
0x140017130  pop     r13
0x140017132  pop     r12
0x140017134  pop     rdi
0x140017135  pop     rsi
0x140017136  pop     rbx
0x140017137  pop     rbp
0x140017138  retn
```
