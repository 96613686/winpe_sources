# LuafvReportAuditVirtualizationEvent

- ea: `0x140016ec8`
- end: `0x14001718a`
- name: `LuafvReportAuditVirtualizationEvent`
- size: `706`
- prototype: `__int64 __fastcall(PACL ResourceSacl, PFLT_CALLBACK_DATA CallbackData, PVOID Data, PVOID)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002408`

## callees

- `0x140005f30`
- `0x140006380`
- `0x140016ec8`

## import_xrefs

- `ntoskrnl!SeExamineSacl` at `0x140016f9d`
- `ntoskrnl!SeExamineSacl` at `0x140016f9d`
- `ntoskrnl!SeSetAuditParameter` at `0x140017022`
- `ntoskrnl!SeSetAuditParameter` at `0x140017051`
- `ntoskrnl!SeSetAuditParameter` at `0x14001707b`
- `ntoskrnl!SeSetAuditParameter` at `0x1400170b1`
- `ntoskrnl!SeSetAuditParameter` at `0x14001710e`
- `ntoskrnl!SeSetAuditParameter` at `0x140017022`
- `ntoskrnl!SeSetAuditParameter` at `0x140017051`
- `ntoskrnl!SeSetAuditParameter` at `0x14001707b`
- `ntoskrnl!SeSetAuditParameter` at `0x1400170b1`
- `ntoskrnl!SeSetAuditParameter` at `0x14001710e`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x14001713b`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x14001713b`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400170ed`
- `ntoskrnl!SeLocateProcessImageName` at `0x1400170ed`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140016fb6`
- `ntoskrnl!SeReleaseSubjectContext` at `0x140016fb6`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140016ffa`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x140016ffa`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140016f5a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x140016f5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017158`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017158`
- `FLTMGR!FltGetRequestorProcessId` at `0x140017097`
- `FLTMGR!FltGetRequestorProcessId` at `0x140017097`
- `FLTMGR!FltGetRequestorProcess` at `0x1400170cd`
- `FLTMGR!FltGetRequestorProcess` at `0x1400170cd`

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
0x140016ec8  push    rbp
0x140016eca  push    rbx
0x140016ecb  push    rsi
0x140016ecc  push    rdi
0x140016ecd  push    r12
0x140016ecf  push    r13
0x140016ed1  push    r14
0x140016ed3  push    r15
0x140016ed5  lea     rbp, [rsp-3B8h]
0x140016edd  sub     rsp, 4B8h
0x140016ee4  mov     rax, cs:__security_cookie
0x140016eeb  xor     rax, rsp
0x140016eee  mov     [rbp+3F0h+var_50], rax
0x140016ef5  xorps   xmm0, xmm0
0x140016ef8  mov     r12, r8
0x140016efb  mov     r14, rdx
0x140016efe  mov     r15, rcx
0x140016f01  xor     edi, edi
0x140016f03  lea     rcx, [rbp+3F0h+AuditParameters]; void *
0x140016f07  xor     edx, edx; Val
0x140016f09  mov     [rsp+4F0h+var_4B0], dil
0x140016f0e  mov     r8d, 418h; Size
0x140016f14  mov     [rsp+4F0h+var_4AF], dil
0x140016f19  movups  xmmword ptr [rsp+4F0h+SubjectContext.ClientToken], xmm0
0x140016f1e  mov     r13, r9
0x140016f21  movups  xmmword ptr [rsp+4F0h+SubjectContext.PrimaryToken], xmm0
0x140016f26  call    memset
0x140016f2b  mov     rax, [r14+10h]
0x140016f2f  mov     qword ptr [rsp+4F0h+AuthenticationId.LowPart], rdi
0x140016f34  mov     [rsp+4F0h+pImageFileName], rdi
0x140016f39  cmp     [rax+4], dil
0x140016f3d  jnz     short loc_140016F50
0x140016f3f  mov     rax, [rax+18h]
0x140016f43  mov     sil, dil
0x140016f46  mov     rbx, [rax+8]
0x140016f4a  add     rbx, 20h ; ' '
0x140016f4e  jmp     short loc_140016F69
0x140016f50  lea     rcx, [rsp+4F0h+SubjectContext]; SubjectContext
0x140016f55  lea     rbx, [rsp+4F0h+SubjectContext]
0x140016f5a  call    cs:__imp_SeCaptureSubjectContext
0x140016f61  nop     dword ptr [rax+rax+00h]
0x140016f66  mov     sil, 1
0x140016f69  mov     rdi, [rbx]
0x140016f6c  test    rdi, rdi
0x140016f6f  jnz     short loc_140016F75
0x140016f71  mov     rdi, [rbx+10h]
0x140016f75  lea     rax, [rsp+4F0h+var_4AF]
0x140016f7a  mov     r9d, 1F01FFh; DesiredAccess
0x140016f80  mov     [rsp+4F0h+GenerateAlarm], rax; GenerateAlarm
0x140016f85  mov     r8, rdi; Token
0x140016f88  lea     rax, [rsp+4F0h+var_4B0]
0x140016f8d  mov     rdx, r15; ResourceSacl
0x140016f90  mov     [rsp+4F0h+GenerateAudit], rax; GenerateAudit
0x140016f95  mov     rcx, r15; Sacl
0x140016f98  mov     [rsp+4F0h+AccessGranted], 1; AccessGranted
0x140016f9d  call    cs:__imp_SeExamineSacl
0x140016fa4  nop     dword ptr [rax+rax+00h]
0x140016fa9  xor     r15d, r15d
0x140016fac  test    sil, sil
0x140016faf  jz      short loc_140016FC2
0x140016fb1  lea     rcx, [rsp+4F0h+SubjectContext]; SubjectContext
0x140016fb6  call    cs:__imp_SeReleaseSubjectContext
0x140016fbd  nop     dword ptr [rax+rax+00h]
0x140016fc2  cmp     [rsp+4F0h+var_4B0], r15b
0x140016fc7  jnz     short loc_140016FD7
0x140016fc9  mov     ebx, r15d
0x140016fcc  cmp     [rsp+4F0h+var_4AF], r15b
0x140016fd1  jz      loc_140017149
0x140016fd7  lea     rdx, [rsp+4F0h+AuthenticationId]; AuthenticationId
0x140016fdc  mov     [rbp+3F0h+AuditParameters.CategoryId], 3
0x140016fe3  mov     rcx, rdi; Token
0x140016fe6  mov     qword ptr [rbp+3F0h+AuditParameters.AuditId], 13BBh
0x140016fee  mov     [rbp+3F0h+AuditParameters.Length], r15d
0x140016ff2  mov     qword ptr [rbp+3F0h+AuditParameters.FlatSubCategoryId], 80000h
0x140016ffa  call    cs:__imp_SeQueryAuthenticationIdToken
0x140017001  nop     dword ptr [rax+rax+00h]
0x140017006  mov     ebx, eax
0x140017008  test    eax, eax
0x14001700a  js      loc_140017149
0x140017010  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]; Index
0x140017014  lea     r9, [rsp+4F0h+AuthenticationId]; Data
0x140017019  mov     edx, 5; Type
0x14001701e  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140017022  call    cs:__imp_SeSetAuditParameter
0x140017029  nop     dword ptr [rax+rax+00h]
0x14001702e  mov     ebx, eax
0x140017030  test    eax, eax
0x140017032  js      loc_140017149
0x140017038  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]
0x14001703c  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140017040  inc     r8d; Index
0x140017043  mov     edi, 2
0x140017048  mov     r9, r12; Data
0x14001704b  mov     [rbp+3F0h+AuditParameters.ParameterCount], r8d
0x14001704f  mov     edx, edi; Type
0x140017051  call    cs:__imp_SeSetAuditParameter
0x140017058  nop     dword ptr [rax+rax+00h]
0x14001705d  mov     ebx, eax
0x14001705f  test    eax, eax
0x140017061  js      loc_140017149
0x140017067  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]
0x14001706b  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x14001706f  inc     r8d; Index
0x140017072  mov     r9, r13; Data
0x140017075  mov     edx, edi; Type
0x140017077  mov     [rbp+3F0h+AuditParameters.ParameterCount], r8d
0x14001707b  call    cs:__imp_SeSetAuditParameter
0x140017082  nop     dword ptr [rax+rax+00h]
0x140017087  mov     ebx, eax
0x140017089  test    eax, eax
0x14001708b  js      loc_140017149
0x140017091  inc     [rbp+3F0h+AuditParameters.ParameterCount]
0x140017094  mov     rcx, r14; CallbackData
0x140017097  call    cs:__imp_FltGetRequestorProcessId
0x14001709e  nop     dword ptr [rax+rax+00h]
0x1400170a3  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]; Index
0x1400170a7  lea     edx, [rdi+9]; Type
0x1400170aa  mov     r9d, eax; Data
0x1400170ad  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x1400170b1  call    cs:__imp_SeSetAuditParameter
0x1400170b8  nop     dword ptr [rax+rax+00h]
0x1400170bd  mov     ebx, eax
0x1400170bf  test    eax, eax
0x1400170c1  js      loc_140017149
0x1400170c7  inc     [rbp+3F0h+AuditParameters.ParameterCount]
0x1400170ca  mov     rcx, r14; CallbackData
0x1400170cd  call    cs:__imp_FltGetRequestorProcess
0x1400170d4  nop     dword ptr [rax+rax+00h]
0x1400170d9  test    rax, rax
0x1400170dc  jnz     short loc_1400170E5
0x1400170de  mov     ebx, 0C000071Ch
0x1400170e3  jmp     short loc_140017149
0x1400170e5  lea     rdx, [rsp+4F0h+pImageFileName]; pImageFileName
0x1400170ea  mov     rcx, rax; Process
0x1400170ed  call    cs:__imp_SeLocateProcessImageName
0x1400170f4  nop     dword ptr [rax+rax+00h]
0x1400170f9  mov     ebx, eax
0x1400170fb  test    eax, eax
0x1400170fd  js      short loc_140017149
0x1400170ff  mov     r9, [rsp+4F0h+pImageFileName]; Data
0x140017104  lea     rcx, [rbp+3F0h+AuditParameters]; AuditParameters
0x140017108  mov     r8d, [rbp+3F0h+AuditParameters.ParameterCount]; Index
0x14001710c  mov     edx, edi; Type
0x14001710e  call    cs:__imp_SeSetAuditParameter
0x140017115  nop     dword ptr [rax+rax+00h]
0x14001711a  mov     ebx, eax
0x14001711c  test    eax, eax
0x14001711e  js      short loc_140017149
0x140017120  inc     [rbp+3F0h+AuditParameters.ParameterCount]
0x140017123  lea     r9, [rbp+3F0h+AuditParameters]; AuditParameters
0x140017127  xor     r8d, r8d; UserSid
0x14001712a  mov     dword ptr [rsp+4F0h+AccessGranted], 75h ; 'u'; AuditSubcategoryId
0x140017132  lea     rdx, LuafvAuditSource; SourceName
0x140017139  xor     ecx, ecx; Flags
0x14001713b  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x140017142  nop     dword ptr [rax+rax+00h]
0x140017147  mov     ebx, eax
0x140017149  mov     rcx, [rsp+4F0h+pImageFileName]; P
0x14001714e  test    rcx, rcx
0x140017151  jz      short loc_140017164
0x140017153  mov     edx, 61506553h; Tag
0x140017158  call    cs:__imp_ExFreePoolWithTag
0x14001715f  nop     dword ptr [rax+rax+00h]
0x140017164  mov     eax, ebx
0x140017166  mov     rcx, [rbp+3F0h+var_50]
0x14001716d  xor     rcx, rsp; StackCookie
0x140017170  call    __security_check_cookie
0x140017175  add     rsp, 4B8h
0x14001717c  pop     r15
0x14001717e  pop     r14
0x140017180  pop     r13
0x140017182  pop     r12
0x140017184  pop     rdi
0x140017185  pop     rsi
0x140017186  pop     rbx
0x140017187  pop     rbp
0x140017188  retn
```
