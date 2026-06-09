# WfpAuditListenEvent

- ea: `0x14004ae80`
- end: `0x14004b17a`
- name: `WfpAuditListenEvent`
- size: `762`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140049710`

## callees

- `0x140006c40`
- `0x140009520`
- `0x140009e00`
- `0x14003bf90`
- `0x14003c074`
- `0x14004ae80`
- `0x14004b180`
- `0x140060ee8`
- `0x140061f50`
- `0x140062030`
- `0x140078400`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14004b12c`
- `ntoskrnl!KeLowerIrql` at `0x14004b12c`
- `ntoskrnl!KfRaiseIrql` at `0x14004aec7`
- `ntoskrnl!KfRaiseIrql` at `0x14004aec7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004aee3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004aee3`
- `ntoskrnl!SeSetAuditParameter` at `0x14004af71`
- `ntoskrnl!SeSetAuditParameter` at `0x14004aff2`
- `ntoskrnl!SeSetAuditParameter` at `0x14004b01e`
- `ntoskrnl!SeSetAuditParameter` at `0x14004b050`
- `ntoskrnl!SeSetAuditParameter` at `0x14004b071`
- `ntoskrnl!SeSetAuditParameter` at `0x14004b0b8`
- `ntoskrnl!SeSetAuditParameter` at `0x14004b0e8`
- `ntoskrnl!SeSetAuditParameter` at `0x14004af71`
- `ntoskrnl!SeSetAuditParameter` at `0x14004aff2`
- `ntoskrnl!SeSetAuditParameter` at `0x14004b01e`
- `ntoskrnl!SeSetAuditParameter` at `0x14004b050`
- `ntoskrnl!SeSetAuditParameter` at `0x14004b071`
- `ntoskrnl!SeSetAuditParameter` at `0x14004b0b8`
- `ntoskrnl!SeSetAuditParameter` at `0x14004b0e8`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x14004b118`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x14004b118`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004aeaf`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004aeaf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004afc8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004afc8`

## pseudocode

```c
__int64 __fastcall WfpAuditListenEvent(__int64 a1)
{
  KIRQL v2; // r13
  char v3; // r12
  struct _SE_ADT_PARAMETER_ARRAY *v4; // rdi
  __int64 v5; // rbx
  unsigned int v6; // r14d
  int v7; // eax
  ULONG v8; // r14d
  unsigned int v9; // eax
  __int64 v10; // rcx
  ULONG v11; // r14d
  int IsEnabledDeviceUsageNoInline; // eax
  struct _UNICODE_STRING *p_DestinationString; // r9
  ULONG v14; // r14d
  ULONG v15; // r14d
  int v16; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING SourceName; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v20; // [rsp+90h] [rbp+40h] BYREF
  int Data; // [rsp+98h] [rbp+48h] BYREF
  int v22; // [rsp+A0h] [rbp+50h] BYREF

  Data = 0;
  SourceName = 0;
  v20 = 0;
  if ( KeGetCurrentIrql() >= 2u )
  {
    v2 = 0;
    v3 = 0;
  }
  else
  {
    v2 = KfRaiseIrql(2u);
    v3 = 1;
  }
  v4 = *(struct _SE_ADT_PARAMETER_ARRAY **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0)
                                          + gWfpPerProContext
                                          + 8);
  memset(v4, 0, sizeof(struct _SE_ADT_PARAMETER_ARRAY));
  KfdAuditCommon(a1, (_DWORD)v4, (unsigned int)&SourceName, (unsigned int)&v22, (__int64)&Data);
  v5 = WfpAleAuditCommon(a1, v4, &v20);
  if ( !v5 )
  {
    v6 = v20;
    v7 = WfpSetParmTypeSockAddr(v4, v20, a1 + 8);
    v8 = v6 + 1;
    v9 = SeSetAuditParameter(v4, (SE_ADT_PARAMETER_TYPE)(v7 + 27), v8, (PVOID)(a1 + 272));
    if ( !v9 )
    {
      v11 = v8 + 1;
      if ( ((__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = (__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline();
      if ( IsEnabledDeviceUsageNoInline )
      {
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, &word_140088868);
        p_DestinationString = (struct _UNICODE_STRING *)(a1 + 872);
        if ( !*(_QWORD *)(a1 + 880) )
          p_DestinationString = &DestinationString;
        v9 = SeSetAuditParameter(v4, SeAdtParmTypeString, v11, p_DestinationString);
        if ( v9 )
          goto LABEL_6;
        ++v11;
      }
      v9 = SeSetAuditParameter(v4, SeAdtParmTypeHexInt64, v11, (PVOID)(a1 + 280));
      if ( !v9 )
      {
        v14 = v11 + 1;
        v9 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, v14, &Data);
        if ( !v9 )
        {
          v9 = SeSetAuditParameter(v4, SeAdtParmTypeHexInt64, v14 + 1, (PVOID)(a1 + 264));
          if ( !v9 )
          {
            v15 = v14 + 2;
            if ( ((__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 0x10) != 0 )
              v16 = (__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 1;
            else
              v16 = Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline();
            if ( !v16 )
              goto LABEL_26;
            v20 = ConvertSublayerWeightToMessageId(*(unsigned int *)(a1 + 860));
            v9 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, v15, &v20);
            if ( !v9 )
            {
              v22 = ConvertFilterActionToMessageId(*(unsigned int *)(a1 + 336));
              v9 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, v15 + 1, &v22);
              if ( !v9 )
              {
                v15 += 2;
LABEL_26:
                v4->ParameterCount = v15;
                SeReportSecurityEventWithSubCategory(0, &SourceName, 0, v4, 0x7Fu);
                goto LABEL_27;
              }
            }
          }
        }
      }
    }
LABEL_6:
    v5 = WfpReportSysErrorAsNtStatus(v10, "SeSetAuditParameter", v9, 1);
  }
LABEL_27:
  if ( v3 )
    KeLowerIrql(v2);
  if ( *(_QWORD *)(a1 + 304) )
    WfpPoolFree(a1 + 304);
  if ( v5 )
    WfpReportError(v5, "WfpAuditListenEvent");
  return v5;
}

```

## disassembly

```asm
0x14004ae80  mov     [rsp-38h+arg_18], rbx
0x14004ae85  push    rbp
0x14004ae86  push    rsi
0x14004ae87  push    rdi
0x14004ae88  push    r12
0x14004ae8a  push    r13
0x14004ae8c  push    r14
0x14004ae8e  push    r15
0x14004ae90  mov     rbp, rsp
0x14004ae93  sub     rsp, 50h
0x14004ae97  xorps   xmm0, xmm0
0x14004ae9a  mov     [rbp+Data], 0
0x14004aea1  movups  xmmword ptr [rbp+SourceName.Length], xmm0
0x14004aea5  mov     rsi, rcx
0x14004aea8  mov     [rbp+arg_0], 0
0x14004aeaf  call    cs:__imp_KeGetCurrentIrql
0x14004aeb6  nop     dword ptr [rax+rax+00h]
0x14004aebb  mov     cl, 2; NewIrql
0x14004aebd  mov     r15d, 1
0x14004aec3  cmp     al, cl
0x14004aec5  jnb     short loc_14004AEDB
0x14004aec7  call    cs:__imp_KfRaiseIrql
0x14004aece  nop     dword ptr [rax+rax+00h]
0x14004aed3  mov     r13b, al
0x14004aed6  mov     r12b, r15b
0x14004aed9  jmp     short loc_14004AEE1
0x14004aedb  xor     r13b, r13b
0x14004aede  xor     r12b, r12b
0x14004aee1  xor     ecx, ecx; ProcNumber
0x14004aee3  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004aeea  nop     dword ptr [rax+rax+00h]
0x14004aeef  imul    eax, cs:gWfpPerProContextSize
0x14004aef6  xor     edx, edx; Val
0x14004aef8  mov     r8d, 418h; Size
0x14004aefe  mov     ecx, eax
0x14004af00  mov     rax, cs:gWfpPerProContext
0x14004af07  mov     rdi, [rcx+rax+8]
0x14004af0c  mov     rcx, rdi; void *
0x14004af0f  call    memset
0x14004af14  lea     rax, [rbp+Data]
0x14004af18  mov     rdx, rdi
0x14004af1b  lea     r9, [rbp+arg_10]
0x14004af1f  mov     qword ptr [rsp+50h+AuditSubcategoryId], rax
0x14004af24  lea     r8, [rbp+SourceName]
0x14004af28  mov     rcx, rsi
0x14004af2b  call    KfdAuditCommon
0x14004af30  lea     r8, [rbp+arg_0]
0x14004af34  mov     rdx, rdi
0x14004af37  mov     rcx, rsi
0x14004af3a  call    WfpAleAuditCommon
0x14004af3f  mov     rbx, rax
0x14004af42  test    rax, rax
0x14004af45  jnz     loc_14004B124
0x14004af4b  mov     r14d, [rbp+arg_0]
0x14004af4f  lea     r8, [rsi+8]
0x14004af53  mov     edx, r14d
0x14004af56  mov     rcx, rdi
0x14004af59  call    WfpSetParmTypeSockAddr
0x14004af5e  add     r14d, r15d
0x14004af61  lea     r9, [rsi+110h]; Data
0x14004af68  mov     r8d, r14d; Index
0x14004af6b  lea     edx, [rax+1Bh]; Type
0x14004af6e  mov     rcx, rdi; AuditParameters
0x14004af71  call    cs:__imp_SeSetAuditParameter
0x14004af78  nop     dword ptr [rax+rax+00h]
0x14004af7d  test    eax, eax
0x14004af7f  jz      short loc_14004AF9B
0x14004af81  mov     r9d, r15d
0x14004af84  mov     r8d, eax
0x14004af87  lea     rdx, aSesetauditpara; "SeSetAuditParameter"
0x14004af8e  call    WfpReportSysErrorAsNtStatus
0x14004af93  mov     rbx, rax
0x14004af96  jmp     loc_14004B124
0x14004af9b  inc     r14d
0x14004af9e  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x14004afa4  test    al, 10h
0x14004afa6  jz      short loc_14004AFAD
0x14004afa8  and     eax, r15d
0x14004afab  jmp     short loc_14004AFB2
0x14004afad  call    Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline
0x14004afb2  test    eax, eax
0x14004afb4  jz      short loc_14004B009
0x14004afb6  xorps   xmm0, xmm0
0x14004afb9  lea     rdx, word_140088868; SourceString
0x14004afc0  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004afc4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004afc8  call    cs:__imp_RtlInitUnicodeString
0x14004afcf  nop     dword ptr [rax+rax+00h]
0x14004afd4  cmp     qword ptr [rsi+370h], 0
0x14004afdc  lea     r9, [rsi+368h]
0x14004afe3  jnz     short loc_14004AFE9
0x14004afe5  lea     r9, [rbp+DestinationString]; Data
0x14004afe9  mov     r8d, r14d; Index
0x14004afec  mov     edx, r15d; Type
0x14004afef  mov     rcx, rdi; AuditParameters
0x14004aff2  call    cs:__imp_SeSetAuditParameter
0x14004aff9  nop     dword ptr [rax+rax+00h]
0x14004affe  test    eax, eax
0x14004b000  jnz     loc_14004AF81
0x14004b006  add     r14d, r15d
0x14004b009  lea     r9, [rsi+118h]; Data
0x14004b010  mov     r8d, r14d; Index
0x14004b013  mov     edx, 0Fh; Type
0x14004b018  mov     rcx, rdi; AuditParameters
0x14004b01b  mov     r15d, r14d
0x14004b01e  call    cs:__imp_SeSetAuditParameter
0x14004b025  nop     dword ptr [rax+rax+00h]
0x14004b02a  test    eax, eax
0x14004b02c  jz      short loc_14004B039
0x14004b02e  mov     r9d, 1
0x14004b034  jmp     loc_14004AF84
0x14004b039  lea     r14d, [r15+1]
0x14004b03d  mov     rcx, rdi; AuditParameters
0x14004b040  mov     r15d, 15h
0x14004b046  lea     r9, [rbp+Data]; Data
0x14004b04a  mov     edx, r15d; Type
0x14004b04d  mov     r8d, r14d; Index
0x14004b050  call    cs:__imp_SeSetAuditParameter
0x14004b057  nop     dword ptr [rax+rax+00h]
0x14004b05c  test    eax, eax
0x14004b05e  jnz     short loc_14004B02E
0x14004b060  lea     r9, [rsi+108h]; Data
0x14004b067  mov     rcx, rdi; AuditParameters
0x14004b06a  lea     r8d, [r14+1]; Index
0x14004b06e  lea     edx, [rax+0Fh]; Type
0x14004b071  call    cs:__imp_SeSetAuditParameter
0x14004b078  nop     dword ptr [rax+rax+00h]
0x14004b07d  test    eax, eax
0x14004b07f  jnz     short loc_14004B02E
0x14004b081  add     r14d, 2
0x14004b085  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x14004b08b  test    al, 10h
0x14004b08d  jz      short loc_14004B094
0x14004b08f  and     eax, 1
0x14004b092  jmp     short loc_14004B099
0x14004b094  call    Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline
0x14004b099  test    eax, eax
0x14004b09b  jz      short loc_14004B100
0x14004b09d  mov     ecx, [rsi+35Ch]
0x14004b0a3  call    ConvertSublayerWeightToMessageId
0x14004b0a8  mov     rcx, rdi; AuditParameters
0x14004b0ab  mov     [rbp+arg_0], eax
0x14004b0ae  lea     r9, [rbp+arg_0]; Data
0x14004b0b2  mov     r8d, r14d; Index
0x14004b0b5  mov     edx, r15d; Type
0x14004b0b8  call    cs:__imp_SeSetAuditParameter
0x14004b0bf  nop     dword ptr [rax+rax+00h]
0x14004b0c4  test    eax, eax
0x14004b0c6  jnz     loc_14004B02E
0x14004b0cc  mov     ecx, [rsi+150h]
0x14004b0d2  call    ConvertFilterActionToMessageId
0x14004b0d7  mov     rcx, rdi; AuditParameters
0x14004b0da  mov     [rbp+arg_10], eax
0x14004b0dd  lea     r9, [rbp+arg_10]; Data
0x14004b0e1  mov     edx, r15d; Type
0x14004b0e4  lea     r8d, [r14+1]; Index
0x14004b0e8  call    cs:__imp_SeSetAuditParameter
0x14004b0ef  nop     dword ptr [rax+rax+00h]
0x14004b0f4  test    eax, eax
0x14004b0f6  jnz     loc_14004B02E
0x14004b0fc  add     r14d, 2
0x14004b100  mov     r9, rdi; AuditParameters
0x14004b103  mov     [rdi+8], r14d
0x14004b107  xor     r8d, r8d; UserSid
0x14004b10a  mov     [rsp+50h+AuditSubcategoryId], 7Fh; AuditSubcategoryId
0x14004b112  lea     rdx, [rbp+SourceName]; SourceName
0x14004b116  xor     ecx, ecx; Flags
0x14004b118  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x14004b11f  nop     dword ptr [rax+rax+00h]
0x14004b124  test    r12b, r12b
0x14004b127  jz      short loc_14004B138
0x14004b129  mov     cl, r13b; NewIrql
0x14004b12c  call    cs:__imp_KeLowerIrql
0x14004b133  nop     dword ptr [rax+rax+00h]
0x14004b138  lea     rcx, [rsi+130h]
0x14004b13f  cmp     qword ptr [rcx], 0
0x14004b143  jz      short loc_14004B14A
0x14004b145  call    WfpPoolFree
0x14004b14a  test    rbx, rbx
0x14004b14d  jz      short loc_14004B15E
0x14004b14f  lea     rdx, aWfpauditlisten; "WfpAuditListenEvent"
0x14004b156  mov     rcx, rbx
0x14004b159  call    WfpReportError
0x14004b15e  mov     rax, rbx
0x14004b161  mov     rbx, [rsp+50h+arg_18]
0x14004b169  add     rsp, 50h
0x14004b16d  pop     r15
0x14004b16f  pop     r14
0x14004b171  pop     r13
0x14004b173  pop     r12
0x14004b175  pop     rdi
0x14004b176  pop     rsi
0x14004b177  pop     rbp
0x14004b178  retn
```
