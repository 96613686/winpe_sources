# WfpAuditBindEvent

- ea: `0x140049830`
- end: `0x140049b2a`
- name: `WfpAuditBindEvent`
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
- `0x140049830`
- `0x14004b180`
- `0x140060ee8`
- `0x140061f50`
- `0x140062030`
- `0x140078400`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140049adc`
- `ntoskrnl!KeLowerIrql` at `0x140049adc`
- `ntoskrnl!KfRaiseIrql` at `0x140049877`
- `ntoskrnl!KfRaiseIrql` at `0x140049877`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140049893`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140049893`
- `ntoskrnl!SeSetAuditParameter` at `0x140049921`
- `ntoskrnl!SeSetAuditParameter` at `0x1400499a2`
- `ntoskrnl!SeSetAuditParameter` at `0x1400499ce`
- `ntoskrnl!SeSetAuditParameter` at `0x140049a00`
- `ntoskrnl!SeSetAuditParameter` at `0x140049a21`
- `ntoskrnl!SeSetAuditParameter` at `0x140049a68`
- `ntoskrnl!SeSetAuditParameter` at `0x140049a98`
- `ntoskrnl!SeSetAuditParameter` at `0x140049921`
- `ntoskrnl!SeSetAuditParameter` at `0x1400499a2`
- `ntoskrnl!SeSetAuditParameter` at `0x1400499ce`
- `ntoskrnl!SeSetAuditParameter` at `0x140049a00`
- `ntoskrnl!SeSetAuditParameter` at `0x140049a21`
- `ntoskrnl!SeSetAuditParameter` at `0x140049a68`
- `ntoskrnl!SeSetAuditParameter` at `0x140049a98`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140049ac8`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140049ac8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004985f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004985f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049978`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049978`

## pseudocode

```c
__int64 __fastcall WfpAuditBindEvent(__int64 a1)
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
    WfpReportError(v5, "WfpAuditBindEvent");
  return v5;
}

```

## disassembly

```asm
0x140049830  mov     [rsp-38h+arg_18], rbx
0x140049835  push    rbp
0x140049836  push    rsi
0x140049837  push    rdi
0x140049838  push    r12
0x14004983a  push    r13
0x14004983c  push    r14
0x14004983e  push    r15
0x140049840  mov     rbp, rsp
0x140049843  sub     rsp, 50h
0x140049847  xorps   xmm0, xmm0
0x14004984a  mov     [rbp+Data], 0
0x140049851  movups  xmmword ptr [rbp+SourceName.Length], xmm0
0x140049855  mov     rsi, rcx
0x140049858  mov     [rbp+arg_0], 0
0x14004985f  call    cs:__imp_KeGetCurrentIrql
0x140049866  nop     dword ptr [rax+rax+00h]
0x14004986b  mov     cl, 2; NewIrql
0x14004986d  mov     r15d, 1
0x140049873  cmp     al, cl
0x140049875  jnb     short loc_14004988B
0x140049877  call    cs:__imp_KfRaiseIrql
0x14004987e  nop     dword ptr [rax+rax+00h]
0x140049883  mov     r13b, al
0x140049886  mov     r12b, r15b
0x140049889  jmp     short loc_140049891
0x14004988b  xor     r13b, r13b
0x14004988e  xor     r12b, r12b
0x140049891  xor     ecx, ecx; ProcNumber
0x140049893  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004989a  nop     dword ptr [rax+rax+00h]
0x14004989f  imul    eax, cs:gWfpPerProContextSize
0x1400498a6  xor     edx, edx; Val
0x1400498a8  mov     r8d, 418h; Size
0x1400498ae  mov     ecx, eax
0x1400498b0  mov     rax, cs:gWfpPerProContext
0x1400498b7  mov     rdi, [rcx+rax+8]
0x1400498bc  mov     rcx, rdi; void *
0x1400498bf  call    memset
0x1400498c4  lea     rax, [rbp+Data]
0x1400498c8  mov     rdx, rdi
0x1400498cb  lea     r9, [rbp+arg_10]
0x1400498cf  mov     qword ptr [rsp+50h+AuditSubcategoryId], rax
0x1400498d4  lea     r8, [rbp+SourceName]
0x1400498d8  mov     rcx, rsi
0x1400498db  call    KfdAuditCommon
0x1400498e0  lea     r8, [rbp+arg_0]
0x1400498e4  mov     rdx, rdi
0x1400498e7  mov     rcx, rsi
0x1400498ea  call    WfpAleAuditCommon
0x1400498ef  mov     rbx, rax
0x1400498f2  test    rax, rax
0x1400498f5  jnz     loc_140049AD4
0x1400498fb  mov     r14d, [rbp+arg_0]
0x1400498ff  lea     r8, [rsi+8]
0x140049903  mov     edx, r14d
0x140049906  mov     rcx, rdi
0x140049909  call    WfpSetParmTypeSockAddr
0x14004990e  add     r14d, r15d
0x140049911  lea     r9, [rsi+110h]; Data
0x140049918  mov     r8d, r14d; Index
0x14004991b  lea     edx, [rax+1Bh]; Type
0x14004991e  mov     rcx, rdi; AuditParameters
0x140049921  call    cs:__imp_SeSetAuditParameter
0x140049928  nop     dword ptr [rax+rax+00h]
0x14004992d  test    eax, eax
0x14004992f  jz      short loc_14004994B
0x140049931  mov     r9d, r15d
0x140049934  mov     r8d, eax
0x140049937  lea     rdx, aSesetauditpara; "SeSetAuditParameter"
0x14004993e  call    WfpReportSysErrorAsNtStatus
0x140049943  mov     rbx, rax
0x140049946  jmp     loc_140049AD4
0x14004994b  inc     r14d
0x14004994e  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x140049954  test    al, 10h
0x140049956  jz      short loc_14004995D
0x140049958  and     eax, r15d
0x14004995b  jmp     short loc_140049962
0x14004995d  call    Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline
0x140049962  test    eax, eax
0x140049964  jz      short loc_1400499B9
0x140049966  xorps   xmm0, xmm0
0x140049969  lea     rdx, word_140088868; SourceString
0x140049970  lea     rcx, [rbp+DestinationString]; DestinationString
0x140049974  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140049978  call    cs:__imp_RtlInitUnicodeString
0x14004997f  nop     dword ptr [rax+rax+00h]
0x140049984  cmp     qword ptr [rsi+370h], 0
0x14004998c  lea     r9, [rsi+368h]
0x140049993  jnz     short loc_140049999
0x140049995  lea     r9, [rbp+DestinationString]; Data
0x140049999  mov     r8d, r14d; Index
0x14004999c  mov     edx, r15d; Type
0x14004999f  mov     rcx, rdi; AuditParameters
0x1400499a2  call    cs:__imp_SeSetAuditParameter
0x1400499a9  nop     dword ptr [rax+rax+00h]
0x1400499ae  test    eax, eax
0x1400499b0  jnz     loc_140049931
0x1400499b6  add     r14d, r15d
0x1400499b9  lea     r9, [rsi+118h]; Data
0x1400499c0  mov     r8d, r14d; Index
0x1400499c3  mov     edx, 0Fh; Type
0x1400499c8  mov     rcx, rdi; AuditParameters
0x1400499cb  mov     r15d, r14d
0x1400499ce  call    cs:__imp_SeSetAuditParameter
0x1400499d5  nop     dword ptr [rax+rax+00h]
0x1400499da  test    eax, eax
0x1400499dc  jz      short loc_1400499E9
0x1400499de  mov     r9d, 1
0x1400499e4  jmp     loc_140049934
0x1400499e9  lea     r14d, [r15+1]
0x1400499ed  mov     rcx, rdi; AuditParameters
0x1400499f0  mov     r15d, 15h
0x1400499f6  lea     r9, [rbp+Data]; Data
0x1400499fa  mov     edx, r15d; Type
0x1400499fd  mov     r8d, r14d; Index
0x140049a00  call    cs:__imp_SeSetAuditParameter
0x140049a07  nop     dword ptr [rax+rax+00h]
0x140049a0c  test    eax, eax
0x140049a0e  jnz     short loc_1400499DE
0x140049a10  lea     r9, [rsi+108h]; Data
0x140049a17  mov     rcx, rdi; AuditParameters
0x140049a1a  lea     r8d, [r14+1]; Index
0x140049a1e  lea     edx, [rax+0Fh]; Type
0x140049a21  call    cs:__imp_SeSetAuditParameter
0x140049a28  nop     dword ptr [rax+rax+00h]
0x140049a2d  test    eax, eax
0x140049a2f  jnz     short loc_1400499DE
0x140049a31  add     r14d, 2
0x140049a35  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x140049a3b  test    al, 10h
0x140049a3d  jz      short loc_140049A44
0x140049a3f  and     eax, 1
0x140049a42  jmp     short loc_140049A49
0x140049a44  call    Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline
0x140049a49  test    eax, eax
0x140049a4b  jz      short loc_140049AB0
0x140049a4d  mov     ecx, [rsi+35Ch]
0x140049a53  call    ConvertSublayerWeightToMessageId
0x140049a58  mov     rcx, rdi; AuditParameters
0x140049a5b  mov     [rbp+arg_0], eax
0x140049a5e  lea     r9, [rbp+arg_0]; Data
0x140049a62  mov     r8d, r14d; Index
0x140049a65  mov     edx, r15d; Type
0x140049a68  call    cs:__imp_SeSetAuditParameter
0x140049a6f  nop     dword ptr [rax+rax+00h]
0x140049a74  test    eax, eax
0x140049a76  jnz     loc_1400499DE
0x140049a7c  mov     ecx, [rsi+150h]
0x140049a82  call    ConvertFilterActionToMessageId
0x140049a87  mov     rcx, rdi; AuditParameters
0x140049a8a  mov     [rbp+arg_10], eax
0x140049a8d  lea     r9, [rbp+arg_10]; Data
0x140049a91  mov     edx, r15d; Type
0x140049a94  lea     r8d, [r14+1]; Index
0x140049a98  call    cs:__imp_SeSetAuditParameter
0x140049a9f  nop     dword ptr [rax+rax+00h]
0x140049aa4  test    eax, eax
0x140049aa6  jnz     loc_1400499DE
0x140049aac  add     r14d, 2
0x140049ab0  mov     r9, rdi; AuditParameters
0x140049ab3  mov     [rdi+8], r14d
0x140049ab7  xor     r8d, r8d; UserSid
0x140049aba  mov     [rsp+50h+AuditSubcategoryId], 7Fh; AuditSubcategoryId
0x140049ac2  lea     rdx, [rbp+SourceName]; SourceName
0x140049ac6  xor     ecx, ecx; Flags
0x140049ac8  call    cs:__imp_SeReportSecurityEventWithSubCategory
0x140049acf  nop     dword ptr [rax+rax+00h]
0x140049ad4  test    r12b, r12b
0x140049ad7  jz      short loc_140049AE8
0x140049ad9  mov     cl, r13b; NewIrql
0x140049adc  call    cs:__imp_KeLowerIrql
0x140049ae3  nop     dword ptr [rax+rax+00h]
0x140049ae8  lea     rcx, [rsi+130h]
0x140049aef  cmp     qword ptr [rcx], 0
0x140049af3  jz      short loc_140049AFA
0x140049af5  call    WfpPoolFree
0x140049afa  test    rbx, rbx
0x140049afd  jz      short loc_140049B0E
0x140049aff  lea     rdx, aWfpauditbindev; "WfpAuditBindEvent"
0x140049b06  mov     rcx, rbx
0x140049b09  call    WfpReportError
0x140049b0e  mov     rax, rbx
0x140049b11  mov     rbx, [rsp+50h+arg_18]
0x140049b19  add     rsp, 50h
0x140049b1d  pop     r15
0x140049b1f  pop     r14
0x140049b21  pop     r13
0x140049b23  pop     r12
0x140049b25  pop     rdi
0x140049b26  pop     rsi
0x140049b27  pop     rbp
0x140049b28  retn
```
