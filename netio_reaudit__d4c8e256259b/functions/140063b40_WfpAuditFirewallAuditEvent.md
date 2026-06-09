# WfpAuditFirewallAuditEvent

- ea: `0x140063b40`
- end: `0x14006415b`
- name: `WfpAuditFirewallAuditEvent`
- size: `1563`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140049710`

## callees

- `0x140009520`
- `0x140009e00`
- `0x14003bf90`
- `0x14003c074`
- `0x1400496d0`
- `0x14004b180`
- `0x140054888`
- `0x140060ee8`
- `0x140061f50`
- `0x140061fcc`
- `0x140062030`
- `0x140063b40`
- `0x140077fa0`
- `0x140078400`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140064117`
- `ntoskrnl!KeLowerIrql` at `0x140064117`
- `ntoskrnl!KfRaiseIrql` at `0x140063bc3`
- `ntoskrnl!KfRaiseIrql` at `0x140063bc3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140063bdf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140063bdf`
- `ntoskrnl!SeSetAuditParameter` at `0x140063c9f`
- `ntoskrnl!SeSetAuditParameter` at `0x140063d1e`
- `ntoskrnl!SeSetAuditParameter` at `0x140063d3f`
- `ntoskrnl!SeSetAuditParameter` at `0x140063dab`
- `ntoskrnl!SeSetAuditParameter` at `0x140063ddb`
- `ntoskrnl!SeSetAuditParameter` at `0x140063e06`
- `ntoskrnl!SeSetAuditParameter` at `0x140063e2b`
- `ntoskrnl!SeSetAuditParameter` at `0x140063e59`
- `ntoskrnl!SeSetAuditParameter` at `0x140063ea5`
- `ntoskrnl!SeSetAuditParameter` at `0x140063ed9`
- `ntoskrnl!SeSetAuditParameter` at `0x140063f0e`
- `ntoskrnl!SeSetAuditParameter` at `0x140063f36`
- `ntoskrnl!SeSetAuditParameter` at `0x140063f58`
- `ntoskrnl!SeSetAuditParameter` at `0x140063f7d`
- `ntoskrnl!SeSetAuditParameter` at `0x140063f9f`
- `ntoskrnl!SeSetAuditParameter` at `0x140063ff0`
- `ntoskrnl!SeSetAuditParameter` at `0x140064012`
- `ntoskrnl!SeSetAuditParameter` at `0x14006404d`
- `ntoskrnl!SeSetAuditParameter` at `0x14006406e`
- `ntoskrnl!SeSetAuditParameter` at `0x1400640be`
- `ntoskrnl!SeSetAuditParameter` at `0x140063c9f`
- `ntoskrnl!SeSetAuditParameter` at `0x140063d1e`
- `ntoskrnl!SeSetAuditParameter` at `0x140063d3f`
- `ntoskrnl!SeSetAuditParameter` at `0x140063dab`
- `ntoskrnl!SeSetAuditParameter` at `0x140063ddb`
- `ntoskrnl!SeSetAuditParameter` at `0x140063e06`
- `ntoskrnl!SeSetAuditParameter` at `0x140063e2b`
- `ntoskrnl!SeSetAuditParameter` at `0x140063e59`
- `ntoskrnl!SeSetAuditParameter` at `0x140063ea5`
- `ntoskrnl!SeSetAuditParameter` at `0x140063ed9`
- `ntoskrnl!SeSetAuditParameter` at `0x140063f0e`
- `ntoskrnl!SeSetAuditParameter` at `0x140063f36`
- `ntoskrnl!SeSetAuditParameter` at `0x140063f58`
- `ntoskrnl!SeSetAuditParameter` at `0x140063f7d`
- `ntoskrnl!SeSetAuditParameter` at `0x140063f9f`
- `ntoskrnl!SeSetAuditParameter` at `0x140063ff0`
- `ntoskrnl!SeSetAuditParameter` at `0x140064012`
- `ntoskrnl!SeSetAuditParameter` at `0x14006404d`
- `ntoskrnl!SeSetAuditParameter` at `0x14006406e`
- `ntoskrnl!SeSetAuditParameter` at `0x1400640be`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140064103`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140064103`
- `ntoskrnl!KeGetCurrentIrql` at `0x140063bab`
- `ntoskrnl!KeGetCurrentIrql` at `0x140063bab`
- `ntoskrnl!RtlInitUnicodeString` at `0x140063d81`
- `ntoskrnl!RtlInitUnicodeString` at `0x140063d81`

## pseudocode

```c
__int64 __fastcall WfpAuditFirewallAuditEvent(__int64 a1)
{
  KIRQL v2; // r13
  char v3; // r12
  struct _SE_ADT_PARAMETER_ARRAY *v4; // rdi
  __int64 v5; // rbx
  char v6; // al
  ULONG v7; // r14d
  unsigned int v8; // eax
  __int64 v9; // rcx
  ULONG v10; // r14d
  __int64 v11; // r8
  __int64 v12; // r11
  ULONG v13; // r14d
  ULONG v14; // r14d
  int IsEnabledDeviceUsageNoInline; // eax
  struct _UNICODE_STRING *p_DestinationString; // r9
  ULONG v17; // r14d
  ULONG v18; // r14d
  ULONG v20; // r15d
  __int64 *v21; // r9
  __int64 *v22; // r9
  ULONG v23; // r14d
  __int64 v24; // rcx
  unsigned int v25; // r15d
  int v26; // eax
  ULONG Index; // [rsp+30h] [rbp-59h] BYREF
  int Data; // [rsp+38h] [rbp-51h] BYREF
  int v30; // [rsp+3Ch] [rbp-4Dh] BYREF
  int v31; // [rsp+40h] [rbp-49h] BYREF
  int v32; // [rsp+44h] [rbp-45h] BYREF
  int v33; // [rsp+48h] [rbp-41h] BYREF
  int v34; // [rsp+4Ch] [rbp-3Dh] BYREF
  int v35; // [rsp+50h] [rbp-39h] BYREF
  int v36; // [rsp+54h] [rbp-35h] BYREF
  int v37; // [rsp+58h] [rbp-31h] BYREF
  int v38; // [rsp+5Ch] [rbp-2Dh] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING SourceName; // [rsp+70h] [rbp-19h] BYREF
  __int64 v41; // [rsp+80h] [rbp-9h] BYREF
  int v42; // [rsp+88h] [rbp-1h]

  Data = 0;
  v41 = 0;
  SourceName = 0;
  v42 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  Index = 0;
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
  LOWORD(v41) = 257;
  KfdAuditCommon(a1, (_DWORD)v4, (unsigned int)&SourceName, (unsigned int)&Data, (__int64)&v30);
  v5 = WfpAleAuditCommon(a1, v4, &Index);
  if ( v5 )
    goto LABEL_58;
  ConvertProfileIdToProfileMessageId(*(unsigned int *)(a1 + 388), &v31);
  ConvertProfileIdToProfileMessageId(*(unsigned int *)(a1 + 392), &v32);
  v6 = *(_BYTE *)(a1 + 828);
  v7 = Index;
  v33 = 1826 - (*(_DWORD *)(a1 + 400) != 0);
  v34 = 1826 - (v6 != 0);
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, Index, &Data);
  if ( v8 )
    goto LABEL_6;
  v10 = v7 + 1;
  if ( Data == 14592 )
  {
    WfpSetParmTypeSockAddr(v4, v10, a1 + 136);
    v11 = a1 + 8;
  }
  else
  {
    WfpSetParmTypeSockAddr(v4, v10, a1 + 8);
    v11 = v12;
  }
  WfpSetParmTypeSockAddr(v4, v10 + 1, v11);
  v13 = v10 + 2;
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeUlongNoConv, v13, (PVOID)(a1 + 272));
  if ( v8 )
    goto LABEL_6;
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeUlongNoConv, v13 + 1, (PVOID)(a1 + 824));
  if ( v8 )
    goto LABEL_6;
  v14 = v13 + 2;
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
    v8 = SeSetAuditParameter(v4, SeAdtParmTypeString, v14, p_DestinationString);
    if ( v8 )
      goto LABEL_6;
    ++v14;
  }
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeString, v14, (PVOID)(a1 + 808));
  if ( v8 )
    goto LABEL_6;
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeHexInt64, v14 + 1, (PVOID)(a1 + 280));
  if ( v8 )
    goto LABEL_6;
  v17 = v14 + 2;
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, v17, &v30);
  if ( v8 )
    goto LABEL_6;
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeHexInt64, v17 + 1, (PVOID)(a1 + 264));
  if ( v8 )
    goto LABEL_6;
  v18 = v17 + 2;
  if ( ((__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 0x10) != 0
     ? (__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 1
     : Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline() )
  {
    v37 = ConvertSublayerWeightToMessageId(*(unsigned int *)(a1 + 860));
    v8 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, v18, &v37);
    if ( v8 )
      goto LABEL_6;
    v20 = ++v18;
  }
  else
  {
    v20 = v18;
  }
  v21 = &v41;
  if ( *(_QWORD *)(a1 + 328) )
    v21 = *(__int64 **)(a1 + 328);
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeSid, v18, v21);
  if ( v8 )
    goto LABEL_6;
  v22 = &v41;
  if ( *(_QWORD *)(a1 + 320) )
    v22 = *(__int64 **)(a1 + 320);
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeSid, v20 + 1, v22);
  if ( v8 )
    goto LABEL_6;
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, v20 + 2, &v31);
  if ( v8 )
    goto LABEL_6;
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, v20 + 3, &v32);
  if ( v8 )
    goto LABEL_6;
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, v20 + 4, &v33);
  if ( v8 )
    goto LABEL_6;
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, v20 + 5, &v34);
  if ( v8 )
    goto LABEL_6;
  v23 = v20 + 6;
  if ( *(_DWORD *)(a1 + 288) == 5160 )
  {
    v24 = *(unsigned int *)(a1 + 860);
    Index = 0;
    v35 = 0;
    v36 = 0;
    ConvertPolicyStoreIdToPolicyStoryCategory(v24, &Index, &v35);
    v8 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, v23, &Index);
    if ( v8 )
      goto LABEL_6;
    v8 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, v20 + 7, &v35);
    if ( v8 )
      goto LABEL_6;
    v36 = 14661 - (*(_DWORD *)(a1 + 864) != 0);
    v8 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, v20 + 8, &v36);
    if ( v8 )
      goto LABEL_6;
    v8 = SeSetAuditParameter(v4, SeAdtParmTypeUlongNoConv, v20 + 9, (PVOID)(a1 + 864));
    if ( v8 )
      goto LABEL_6;
    v23 = v20 + 10;
  }
  v25 = v23;
  if ( ((__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 0x10) != 0 )
    v26 = (__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 1;
  else
    v26 = Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline();
  if ( !v26 )
    goto LABEL_55;
  v38 = ConvertFilterActionToMessageId(*(unsigned int *)(a1 + 336));
  v8 = SeSetAuditParameter(v4, SeAdtParmTypeMessage, v23, &v38);
  if ( v8 )
  {
LABEL_6:
    v5 = WfpReportSysErrorAsNtStatus(v9, "SeSetAuditParameter", v8, 1);
    goto LABEL_58;
  }
  ++v23;
  ++v25;
LABEL_55:
  v4->ParameterCount = v23;
  if ( v25 >= 0x20 )
    MicrosoftTelemetryAssertTriggeredMsgKM("paramCount is larger than SE_MAX_AUDIT_PARAMETERS");
  SeReportSecurityEventWithSubCategory(0, &SourceName, 0, v4, 0x7Fu);
LABEL_58:
  if ( v3 )
    KeLowerIrql(v2);
  if ( v5 )
    WfpReportError(v5, "WfpAuditFirewallAuditEvent");
  return v5;
}

```

## disassembly

```asm
0x140063b40  push    rbp
0x140063b42  push    rbx
0x140063b43  push    rsi
0x140063b44  push    rdi
0x140063b45  push    r12
0x140063b47  push    r13
0x140063b49  push    r14
0x140063b4b  push    r15
0x140063b4d  lea     rbp, [rsp-1Fh]
0x140063b52  sub     rsp, 0A8h
0x140063b59  mov     rax, cs:__security_cookie
0x140063b60  xor     rax, rsp
0x140063b63  mov     [rbp+57h+var_50], rax
0x140063b67  xor     eax, eax
0x140063b69  mov     [rbp+57h+Data], 0
0x140063b70  xorps   xmm0, xmm0
0x140063b73  mov     [rbp+57h+var_60], rax
0x140063b77  movups  xmmword ptr [rbp+57h+SourceName.Length], xmm0
0x140063b7b  mov     [rbp+57h+var_58], eax
0x140063b7e  mov     rsi, rcx
0x140063b81  mov     [rbp+57h+var_A4], 0
0x140063b88  mov     [rbp+57h+var_A0], 0
0x140063b8f  mov     [rbp+57h+var_9C], 0
0x140063b96  mov     [rbp+57h+var_98], 0
0x140063b9d  mov     [rbp+57h+var_94], 0
0x140063ba4  mov     [rbp+57h+Index], 0
0x140063bab  call    cs:__imp_KeGetCurrentIrql
0x140063bb2  nop     dword ptr [rax+rax+00h]
0x140063bb7  mov     cl, 2; NewIrql
0x140063bb9  mov     r15d, 1
0x140063bbf  cmp     al, cl
0x140063bc1  jnb     short loc_140063BD7
0x140063bc3  call    cs:__imp_KfRaiseIrql
0x140063bca  nop     dword ptr [rax+rax+00h]
0x140063bcf  mov     r13b, al
0x140063bd2  mov     r12b, r15b
0x140063bd5  jmp     short loc_140063BDD
0x140063bd7  xor     r13b, r13b
0x140063bda  xor     r12b, r12b
0x140063bdd  xor     ecx, ecx; ProcNumber
0x140063bdf  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140063be6  nop     dword ptr [rax+rax+00h]
0x140063beb  imul    eax, cs:gWfpPerProContextSize
0x140063bf2  xor     edx, edx; Val
0x140063bf4  mov     r8d, 418h; Size
0x140063bfa  mov     ecx, eax
0x140063bfc  mov     rax, cs:gWfpPerProContext
0x140063c03  mov     rdi, [rcx+rax+8]
0x140063c08  mov     rcx, rdi; void *
0x140063c0b  call    memset
0x140063c10  lea     rax, [rbp+57h+var_A4]
0x140063c14  mov     word ptr [rbp+57h+var_60], 101h
0x140063c1a  lea     r9, [rbp+57h+Data]
0x140063c1e  mov     qword ptr [rsp+0E0h+AuditSubcategoryId], rax
0x140063c23  lea     r8, [rbp+57h+SourceName]
0x140063c27  mov     rdx, rdi
0x140063c2a  mov     rcx, rsi
0x140063c2d  call    KfdAuditCommon
0x140063c32  lea     r8, [rbp+57h+Index]
0x140063c36  mov     rdx, rdi
0x140063c39  mov     rcx, rsi
0x140063c3c  call    WfpAleAuditCommon
0x140063c41  mov     rbx, rax
0x140063c44  test    rax, rax
0x140063c47  jnz     loc_14006410F
0x140063c4d  mov     ecx, [rsi+184h]
0x140063c53  lea     rdx, [rbp+57h+var_A0]
0x140063c57  call    ConvertProfileIdToProfileMessageId
0x140063c5c  mov     ecx, [rsi+188h]
0x140063c62  lea     rdx, [rbp+57h+var_9C]
0x140063c66  call    ConvertProfileIdToProfileMessageId
0x140063c6b  mov     edx, [rsi+190h]
0x140063c71  lea     r9, [rbp+57h+Data]; Data
0x140063c75  mov     al, [rsi+33Ch]
0x140063c7b  neg     edx
0x140063c7d  mov     r14d, [rbp+57h+Index]
0x140063c81  mov     edx, 722h
0x140063c86  sbb     ecx, ecx
0x140063c88  mov     r8d, r14d; Index
0x140063c8b  add     ecx, edx
0x140063c8d  mov     [rbp+57h+var_98], ecx
0x140063c90  neg     al
0x140063c92  sbb     ecx, ecx
0x140063c94  add     ecx, edx
0x140063c96  lea     edx, [rbx+15h]; Type
0x140063c99  mov     [rbp+57h+var_94], ecx
0x140063c9c  mov     rcx, rdi; AuditParameters
0x140063c9f  call    cs:__imp_SeSetAuditParameter
0x140063ca6  nop     dword ptr [rax+rax+00h]
0x140063cab  test    eax, eax
0x140063cad  jz      short loc_140063CC9
0x140063caf  mov     r9d, r15d
0x140063cb2  mov     r8d, eax
0x140063cb5  lea     rdx, aSesetauditpara; "SeSetAuditParameter"
0x140063cbc  call    WfpReportSysErrorAsNtStatus
0x140063cc1  mov     rbx, rax
0x140063cc4  jmp     loc_14006410F
0x140063cc9  add     r14d, r15d
0x140063ccc  lea     r11, [rsi+88h]
0x140063cd3  cmp     [rbp+57h+Data], 3900h
0x140063cda  mov     edx, r14d
0x140063cdd  mov     rcx, rdi
0x140063ce0  jnz     short loc_140063CF0
0x140063ce2  mov     r8, r11
0x140063ce5  call    WfpSetParmTypeSockAddr
0x140063cea  lea     r8, [rsi+8]
0x140063cee  jmp     short loc_140063CFC
0x140063cf0  lea     r8, [rsi+8]
0x140063cf4  call    WfpSetParmTypeSockAddr
0x140063cf9  mov     r8, r11
0x140063cfc  lea     edx, [r14+1]
0x140063d00  mov     rcx, rdi
0x140063d03  call    WfpSetParmTypeSockAddr
0x140063d08  add     r14d, 2
0x140063d0c  lea     r9, [rsi+110h]; Data
0x140063d13  mov     r8d, r14d; Index
0x140063d16  mov     edx, 1Bh; Type
0x140063d1b  mov     rcx, rdi; AuditParameters
0x140063d1e  call    cs:__imp_SeSetAuditParameter
0x140063d25  nop     dword ptr [rax+rax+00h]
0x140063d2a  test    eax, eax
0x140063d2c  jnz     short loc_140063CAF
0x140063d2e  lea     r9, [rsi+338h]; Data
0x140063d35  mov     rcx, rdi; AuditParameters
0x140063d38  lea     r8d, [r14+1]; Index
0x140063d3c  lea     edx, [rax+1Bh]; Type
0x140063d3f  call    cs:__imp_SeSetAuditParameter
0x140063d46  nop     dword ptr [rax+rax+00h]
0x140063d4b  test    eax, eax
0x140063d4d  jnz     loc_140063CAF
0x140063d53  add     r14d, 2
0x140063d57  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x140063d5d  test    al, 10h
0x140063d5f  jz      short loc_140063D66
0x140063d61  and     eax, r15d
0x140063d64  jmp     short loc_140063D6B
0x140063d66  call    Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline
0x140063d6b  test    eax, eax
0x140063d6d  jz      short loc_140063DC2
0x140063d6f  xorps   xmm0, xmm0
0x140063d72  lea     rdx, word_140088868; SourceString
0x140063d79  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140063d7d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140063d81  call    cs:__imp_RtlInitUnicodeString
0x140063d88  nop     dword ptr [rax+rax+00h]
0x140063d8d  cmp     qword ptr [rsi+370h], 0
0x140063d95  lea     r9, [rsi+368h]
0x140063d9c  jnz     short loc_140063DA2
0x140063d9e  lea     r9, [rbp+57h+DestinationString]; Data
0x140063da2  mov     r8d, r14d; Index
0x140063da5  mov     edx, r15d; Type
0x140063da8  mov     rcx, rdi; AuditParameters
0x140063dab  call    cs:__imp_SeSetAuditParameter
0x140063db2  nop     dword ptr [rax+rax+00h]
0x140063db7  test    eax, eax
0x140063db9  jnz     loc_140063CAF
0x140063dbf  add     r14d, r15d
0x140063dc2  mov     r8d, r14d; Index
0x140063dc5  lea     r9, [rsi+328h]; Data
0x140063dcc  mov     r15d, r14d
0x140063dcf  mov     rcx, rdi; AuditParameters
0x140063dd2  mov     r14d, 1
0x140063dd8  mov     edx, r14d; Type
0x140063ddb  call    cs:__imp_SeSetAuditParameter
0x140063de2  nop     dword ptr [rax+rax+00h]
0x140063de7  test    eax, eax
0x140063de9  jz      short loc_140063DF3
0x140063deb  mov     r9d, r14d
0x140063dee  jmp     loc_140063CB2
0x140063df3  lea     r9, [rsi+118h]; Data
0x140063dfa  mov     edx, 0Fh; Type
0x140063dff  lea     r8d, [r15+1]; Index
0x140063e03  mov     rcx, rdi; AuditParameters
0x140063e06  call    cs:__imp_SeSetAuditParameter
0x140063e0d  nop     dword ptr [rax+rax+00h]
0x140063e12  test    eax, eax
0x140063e14  jnz     short loc_140063DEB
0x140063e16  lea     r14d, [r15+2]
0x140063e1a  mov     rcx, rdi; AuditParameters
0x140063e1d  lea     r15d, [rax+15h]
0x140063e21  mov     r8d, r14d; Index
0x140063e24  mov     edx, r15d; Type
0x140063e27  lea     r9, [rbp+57h+var_A4]; Data
0x140063e2b  call    cs:__imp_SeSetAuditParameter
0x140063e32  nop     dword ptr [rax+rax+00h]
0x140063e37  test    eax, eax
0x140063e39  jz      short loc_140063E46
0x140063e3b  mov     r9d, 1
0x140063e41  jmp     loc_140063CB2
0x140063e46  lea     r9, [rsi+108h]; Data
0x140063e4d  mov     edx, 0Fh; Type
0x140063e52  lea     r8d, [r14+1]; Index
0x140063e56  mov     rcx, rdi; AuditParameters
0x140063e59  call    cs:__imp_SeSetAuditParameter
0x140063e60  nop     dword ptr [rax+rax+00h]
0x140063e65  test    eax, eax
0x140063e67  jnz     short loc_140063E3B
0x140063e69  add     r14d, 2
0x140063e6d  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x140063e73  test    al, 10h
0x140063e75  jz      short loc_140063E7C
0x140063e77  and     eax, 1
0x140063e7a  jmp     short loc_140063E81
0x140063e7c  call    Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline
0x140063e81  test    eax, eax
0x140063e83  jnz     short loc_140063E8A
0x140063e85  mov     r15d, r14d
0x140063e88  jmp     short loc_140063EBC
0x140063e8a  mov     ecx, [rsi+35Ch]
0x140063e90  call    ConvertSublayerWeightToMessageId
0x140063e95  mov     rcx, rdi; AuditParameters
0x140063e98  mov     [rbp+57h+var_88], eax
0x140063e9b  lea     r9, [rbp+57h+var_88]; Data
0x140063e9f  mov     r8d, r14d; Index
0x140063ea2  mov     edx, r15d; Type
0x140063ea5  call    cs:__imp_SeSetAuditParameter
0x140063eac  nop     dword ptr [rax+rax+00h]
0x140063eb1  test    eax, eax
0x140063eb3  jnz     short loc_140063E3B
0x140063eb5  lea     r15d, [r14+1]
0x140063eb9  mov     r14d, r15d
0x140063ebc  mov     rax, [rsi+148h]
0x140063ec3  lea     r9, [rbp+57h+var_60]
0x140063ec7  test    rax, rax
0x140063eca  mov     r8d, r14d; Index
0x140063ecd  mov     edx, 4; Type
0x140063ed2  mov     rcx, rdi; AuditParameters
0x140063ed5  cmovnz  r9, rax; Data
0x140063ed9  call    cs:__imp_SeSetAuditParameter
0x140063ee0  nop     dword ptr [rax+rax+00h]
0x140063ee5  test    eax, eax
0x140063ee7  jnz     loc_140063E3B
0x140063eed  mov     rax, [rsi+140h]
0x140063ef4  lea     r14d, [r15+1]
0x140063ef8  test    rax, rax
0x140063efb  lea     r9, [rbp+57h+var_60]
0x140063eff  mov     r8d, r14d; Index
0x140063f02  mov     edx, 4; Type
0x140063f07  cmovnz  r9, rax; Data
0x140063f0b  mov     rcx, rdi; AuditParameters
0x140063f0e  call    cs:__imp_SeSetAuditParameter
0x140063f15  nop     dword ptr [rax+rax+00h]
0x140063f1a  test    eax, eax
0x140063f1c  jnz     loc_140063E3B
0x140063f22  lea     r15d, [rax+15h]
0x140063f26  inc     r14d
0x140063f29  mov     r8d, r14d; Index
0x140063f2c  lea     r9, [rbp+57h+var_A0]; Data
0x140063f30  mov     edx, r15d; Type
0x140063f33  mov     rcx, rdi; AuditParameters
0x140063f36  call    cs:__imp_SeSetAuditParameter
0x140063f3d  nop     dword ptr [rax+rax+00h]
0x140063f42  test    eax, eax
0x140063f44  jnz     loc_140063E3B
0x140063f4a  lea     r9, [rbp+57h+var_9C]; Data
0x140063f4e  mov     edx, r15d; Type
0x140063f51  lea     r8d, [r14+1]; Index
0x140063f55  mov     rcx, rdi; AuditParameters
0x140063f58  call    cs:__imp_SeSetAuditParameter
0x140063f5f  nop     dword ptr [rax+rax+00h]
0x140063f64  test    eax, eax
0x140063f66  jnz     loc_140063E3B
0x140063f6c  add     r14d, 2
0x140063f70  lea     r9, [rbp+57h+var_98]; Data
0x140063f74  mov     r8d, r14d; Index
0x140063f77  mov     edx, r15d; Type
0x140063f7a  mov     rcx, rdi; AuditParameters
0x140063f7d  call    cs:__imp_SeSetAuditParameter
0x140063f84  nop     dword ptr [rax+rax+00h]
0x140063f89  test    eax, eax
0x140063f8b  jnz     loc_140063E3B
0x140063f91  lea     r9, [rbp+57h+var_94]; Data
0x140063f95  mov     edx, r15d; Type
0x140063f98  lea     r8d, [r14+1]; Index
0x140063f9c  mov     rcx, rdi; AuditParameters
0x140063f9f  call    cs:__imp_SeSetAuditParameter
0x140063fa6  nop     dword ptr [rax+rax+00h]
0x140063fab  test    eax, eax
0x140063fad  jnz     loc_140063E3B
0x140063fb3  add     r14d, 2
0x140063fb7  cmp     dword ptr [rsi+120h], 1428h
0x140063fc1  jnz     loc_140064086
0x140063fc7  mov     ecx, [rsi+35Ch]
0x140063fcd  lea     r8, [rbp+57h+var_90]
0x140063fd1  lea     rdx, [rbp+57h+Index]
0x140063fd5  mov     [rbp+57h+Index], eax
0x140063fd8  mov     [rbp+57h+var_90], eax
0x140063fdb  mov     [rbp+57h+var_8C], eax
0x140063fde  call    ConvertPolicyStoreIdToPolicyStoryCategory
0x140063fe3  mov     rcx, rdi; AuditParameters
0x140063fe6  lea     r9, [rbp+57h+Index]; Data
0x140063fea  mov     r8d, r14d; Index
0x140063fed  mov     edx, r15d; Type
0x140063ff0  call    cs:__imp_SeSetAuditParameter
0x140063ff7  nop     dword ptr [rax+rax+00h]
0x140063ffc  test    eax, eax
0x140063ffe  jnz     loc_140063E3B
0x140064004  lea     r9, [rbp+57h+var_90]; Data
0x140064008  mov     edx, r15d; Type
0x14006400b  lea     r8d, [r14+1]; Index
  ... truncated ...
```
