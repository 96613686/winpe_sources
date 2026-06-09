# WfpAuditEventVeto

- ea: `0x1400635a4`
- end: `0x140063b37`
- name: `WfpAuditEventVeto`
- size: `1427`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140049710`

## callees

- `0x140009520`
- `0x140009e00`
- `0x14003c074`
- `0x14004b180`
- `0x140060ee8`
- `0x140061f50`
- `0x140062030`
- `0x1400635a4`
- `0x140078400`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x140063af4`
- `ntoskrnl!KeLowerIrql` at `0x140063af4`
- `ntoskrnl!KfRaiseIrql` at `0x1400635ed`
- `ntoskrnl!KfRaiseIrql` at `0x1400635ed`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140063609`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140063609`
- `ntoskrnl!SeSetAuditParameter` at `0x140063670`
- `ntoskrnl!SeSetAuditParameter` at `0x1400636cb`
- `ntoskrnl!SeSetAuditParameter` at `0x1400636ed`
- `ntoskrnl!SeSetAuditParameter` at `0x14006375e`
- `ntoskrnl!SeSetAuditParameter` at `0x1400637ad`
- `ntoskrnl!SeSetAuditParameter` at `0x1400637da`
- `ntoskrnl!SeSetAuditParameter` at `0x140063806`
- `ntoskrnl!SeSetAuditParameter` at `0x140063834`
- `ntoskrnl!SeSetAuditParameter` at `0x14006386d`
- `ntoskrnl!SeSetAuditParameter` at `0x140063899`
- `ntoskrnl!SeSetAuditParameter` at `0x1400638c3`
- `ntoskrnl!SeSetAuditParameter` at `0x1400638ef`
- `ntoskrnl!SeSetAuditParameter` at `0x140063961`
- `ntoskrnl!SeSetAuditParameter` at `0x140063997`
- `ntoskrnl!SeSetAuditParameter` at `0x1400639c0`
- `ntoskrnl!SeSetAuditParameter` at `0x1400639e9`
- `ntoskrnl!SeSetAuditParameter` at `0x140063a0c`
- `ntoskrnl!SeSetAuditParameter` at `0x140063a31`
- `ntoskrnl!SeSetAuditParameter` at `0x140063a7d`
- `ntoskrnl!SeSetAuditParameter` at `0x140063aaf`
- `ntoskrnl!SeSetAuditParameter` at `0x140063670`
- `ntoskrnl!SeSetAuditParameter` at `0x1400636cb`
- `ntoskrnl!SeSetAuditParameter` at `0x1400636ed`
- `ntoskrnl!SeSetAuditParameter` at `0x14006375e`
- `ntoskrnl!SeSetAuditParameter` at `0x1400637ad`
- `ntoskrnl!SeSetAuditParameter` at `0x1400637da`
- `ntoskrnl!SeSetAuditParameter` at `0x140063806`
- `ntoskrnl!SeSetAuditParameter` at `0x140063834`
- `ntoskrnl!SeSetAuditParameter` at `0x14006386d`
- `ntoskrnl!SeSetAuditParameter` at `0x140063899`
- `ntoskrnl!SeSetAuditParameter` at `0x1400638c3`
- `ntoskrnl!SeSetAuditParameter` at `0x1400638ef`
- `ntoskrnl!SeSetAuditParameter` at `0x140063961`
- `ntoskrnl!SeSetAuditParameter` at `0x140063997`
- `ntoskrnl!SeSetAuditParameter` at `0x1400639c0`
- `ntoskrnl!SeSetAuditParameter` at `0x1400639e9`
- `ntoskrnl!SeSetAuditParameter` at `0x140063a0c`
- `ntoskrnl!SeSetAuditParameter` at `0x140063a31`
- `ntoskrnl!SeSetAuditParameter` at `0x140063a7d`
- `ntoskrnl!SeSetAuditParameter` at `0x140063aaf`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140063ae0`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x140063ae0`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400635d7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400635d7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400636b2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140063937`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400636b2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140063937`

## pseudocode

```c
__int64 __fastcall WfpAuditEventVeto(__int64 a1)
{
  ULONG v1; // esi
  KIRQL v3; // r12
  char v4; // r15
  struct _SE_ADT_PARAMETER_ARRAY *v5; // rdi
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rbx
  struct _UNICODE_STRING *p_DestinationString; // r9
  __int64 v10; // rax
  __int64 v11; // r10
  unsigned int v12; // r11d
  ULONG v13; // esi
  ULONG AuditId; // eax
  int *v15; // r9
  ULONG v17; // esi
  ULONG v18; // esi
  struct _UNICODE_STRING *v19; // r9
  ULONG v20; // esi
  ULONG v21; // esi
  ULONG v22; // esi
  int IsEnabledDeviceUsageNoInline; // eax
  int v25; // [rsp+30h] [rbp-40h] BYREF
  int v26; // [rsp+34h] [rbp-3Ch] BYREF
  int v27; // [rsp+38h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING v29; // [rsp+50h] [rbp-20h] BYREF
  struct _UNICODE_STRING SourceName; // [rsp+60h] [rbp-10h] BYREF
  int v31; // [rsp+B8h] [rbp+48h] BYREF
  int v32; // [rsp+C0h] [rbp+50h] BYREF
  int Data; // [rsp+C8h] [rbp+58h] BYREF

  SourceName = 0;
  Data = 0;
  v1 = 0;
  v25 = 0;
  DestinationString = 0;
  if ( KeGetCurrentIrql() >= 2u )
  {
    v3 = 0;
    v4 = 0;
  }
  else
  {
    v3 = KfRaiseIrql(2u);
    v4 = 1;
  }
  v5 = *(struct _SE_ADT_PARAMETER_ARRAY **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0)
                                          + gWfpPerProContext
                                          + 8);
  memset(v5, 0, sizeof(struct _SE_ADT_PARAMETER_ARRAY));
  KfdAuditCommon(a1, (_DWORD)v5, (unsigned int)&SourceName, (unsigned int)&Data, (__int64)&v25);
  if ( v5->AuditId == 5153 )
  {
    v6 = SeSetAuditParameter(v5, SeAdtParmTypeHexInt64, 0, (PVOID)(a1 + 352));
    if ( v6 )
      goto LABEL_6;
    p_DestinationString = (struct _UNICODE_STRING *)(a1 + 296);
    if ( !*(_WORD *)(a1 + 296) )
    {
      RtlInitUnicodeString(&DestinationString, L"-");
      p_DestinationString = &DestinationString;
    }
    v6 = SeSetAuditParameter(v5, SeAdtParmTypeString, 1u, p_DestinationString);
    if ( v6 )
      goto LABEL_6;
    v1 = 2;
  }
  v6 = SeSetAuditParameter(v5, SeAdtParmTypeMessage, v1, &Data);
  if ( v6 )
    goto LABEL_6;
  if ( Data == 14592 )
    v10 = 136;
  else
    v10 = 8;
  WfpSetParmTypeSockAddr(v5, v1 + 1, v10 + a1);
  v13 = v12 + 1;
  WfpSetParmTypeSockAddr(v5, v12, v11 + a1);
  AuditId = v5->AuditId;
  switch ( AuditId )
  {
    case 0x1421u:
      v15 = (int *)(a1 + 272);
      break;
    case 0x141Fu:
      v31 = 0;
      v6 = SeSetAuditParameter(v5, SeAdtParmTypeHexUlong, v13, (PVOID)(a1 + 272));
      if ( v6 )
        goto LABEL_6;
      v17 = v13 + 1;
      v31 = *(_DWORD *)(a1 + 412);
      v6 = SeSetAuditParameter(v5, SeAdtParmTypeUlongNoConv, v17, &v31);
      if ( v6 )
        goto LABEL_6;
      v31 = *(_DWORD *)(a1 + 404);
      v6 = SeSetAuditParameter(v5, SeAdtParmTypeUlongNoConv, v17 + 1, &v31);
      if ( v6 )
        goto LABEL_6;
      v13 = v17 + 2;
      v31 = *(unsigned __int16 *)(a1 + 408);
      v6 = SeSetAuditParameter(v5, SeAdtParmTypeHexUlong, v13, &v31);
      goto LABEL_18;
    case 0x141Bu:
      v32 = 0;
      v6 = SeSetAuditParameter(v5, SeAdtParmTypeHexUlong, v13, (PVOID)(a1 + 272));
      if ( v6 )
        goto LABEL_6;
      v32 = *(unsigned __int16 *)(a1 + 408);
      v6 = SeSetAuditParameter(v5, SeAdtParmTypeHexUlong, v13 + 1, &v32);
      if ( v6 )
        goto LABEL_6;
      v18 = v13 + 2;
      v6 = SeSetAuditParameter(v5, SeAdtParmTypeString, v18, (PVOID)(a1 + 680));
      if ( v6 )
        goto LABEL_6;
      v32 = *(_DWORD *)(a1 + 696);
      v6 = SeSetAuditParameter(v5, SeAdtParmTypeUlongNoConv, v18 + 1, &v32);
      if ( v6 )
        goto LABEL_6;
      v15 = &v32;
      v32 = *(_DWORD *)(a1 + 700);
      v13 = v18 + 2;
      break;
    default:
      __fastfail(5u);
  }
  v6 = SeSetAuditParameter(v5, SeAdtParmTypeUlongNoConv, v13, v15);
LABEL_18:
  if ( v6 )
    goto LABEL_6;
  if ( ((__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 0x10) != 0
     ? (__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 1
     : Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline() )
  {
    v29 = 0;
    RtlInitUnicodeString(&v29, &word_140088868);
    v19 = (struct _UNICODE_STRING *)(a1 + 872);
    if ( !*(_QWORD *)(a1 + 880) )
      v19 = &v29;
    v6 = SeSetAuditParameter(v5, SeAdtParmTypeString, v13 + 1, v19);
    if ( v6 )
      goto LABEL_6;
    v20 = v13 + 2;
    if ( ((v5->AuditId - 5147) & 0xFFFFFFFB) != 0 )
    {
      v6 = SeSetAuditParameter(v5, SeAdtParmTypeString, v20, (PVOID)(a1 + 808));
      if ( v6 )
        goto LABEL_6;
      ++v20;
    }
  }
  else
  {
    v6 = SeSetAuditParameter(v5, SeAdtParmTypeString, v13 + 1, (PVOID)(a1 + 808));
    if ( v6 )
      goto LABEL_6;
    v20 = v13 + 2;
  }
  v6 = SeSetAuditParameter(v5, SeAdtParmTypeHexInt64, v20, (PVOID)(a1 + 280));
  if ( v6 )
    goto LABEL_6;
  v21 = v20 + 1;
  v6 = SeSetAuditParameter(v5, SeAdtParmTypeMessage, v21, &v25);
  if ( v6 )
    goto LABEL_6;
  v6 = SeSetAuditParameter(v5, SeAdtParmTypeHexInt64, v21 + 1, (PVOID)(a1 + 264));
  if ( v6 )
    goto LABEL_6;
  v22 = v21 + 2;
  if ( ((__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = (__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline();
  if ( !IsEnabledDeviceUsageNoInline )
    goto LABEL_52;
  v26 = ConvertSublayerWeightToMessageId(*(unsigned int *)(a1 + 860));
  v6 = SeSetAuditParameter(v5, SeAdtParmTypeMessage, v22, &v26);
  if ( v6
    || (v27 = ConvertFilterActionToMessageId(*(unsigned int *)(a1 + 336)),
        (v6 = SeSetAuditParameter(v5, SeAdtParmTypeMessage, v22 + 1, &v27)) != 0) )
  {
LABEL_6:
    v8 = WfpReportSysErrorAsNtStatus(v7, "SeSetAuditParameter", v6, 1);
    goto LABEL_53;
  }
  v22 += 2;
LABEL_52:
  v5->ParameterCount = v22;
  v8 = 0;
  SeReportSecurityEventWithSubCategory(0, &SourceName, 0, v5, 0x7Eu);
LABEL_53:
  if ( v4 )
    KeLowerIrql(v3);
  if ( v8 )
    WfpReportError(v8, "WfpAuditEventVeto");
  return v8;
}

```

## disassembly

```asm
0x1400635a4  mov     [rsp-38h+arg_0], rbx
0x1400635a9  push    rbp
0x1400635aa  push    rsi
0x1400635ab  push    rdi
0x1400635ac  push    r12
0x1400635ae  push    r13
0x1400635b0  push    r14
0x1400635b2  push    r15
0x1400635b4  mov     rbp, rsp
0x1400635b7  sub     rsp, 70h
0x1400635bb  xorps   xmm0, xmm0
0x1400635be  xor     r14d, r14d
0x1400635c1  movups  xmmword ptr [rbp+SourceName.Length], xmm0
0x1400635c5  mov     [rbp+Data], r14d
0x1400635c9  mov     esi, r14d
0x1400635cc  mov     [rbp+var_40], r14d
0x1400635d0  mov     rbx, rcx
0x1400635d3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400635d7  call    cs:__imp_KeGetCurrentIrql
0x1400635de  nop     dword ptr [rax+rax+00h]
0x1400635e3  lea     r13d, [r14+1]
0x1400635e7  cmp     al, 2
0x1400635e9  jnb     short loc_140063601
0x1400635eb  mov     cl, 2; NewIrql
0x1400635ed  call    cs:__imp_KfRaiseIrql
0x1400635f4  nop     dword ptr [rax+rax+00h]
0x1400635f9  mov     r12b, al
0x1400635fc  mov     r15b, r13b
0x1400635ff  jmp     short loc_140063607
0x140063601  mov     r12b, r14b
0x140063604  mov     r15b, r14b
0x140063607  xor     ecx, ecx; ProcNumber
0x140063609  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140063610  nop     dword ptr [rax+rax+00h]
0x140063615  imul    eax, cs:gWfpPerProContextSize
0x14006361c  xor     edx, edx; Val
0x14006361e  mov     r8d, 418h; Size
0x140063624  mov     ecx, eax
0x140063626  mov     rax, cs:gWfpPerProContext
0x14006362d  mov     rdi, [rcx+rax+8]
0x140063632  mov     rcx, rdi; void *
0x140063635  call    memset
0x14006363a  lea     rax, [rbp+var_40]
0x14006363e  mov     rdx, rdi
0x140063641  lea     r9, [rbp+Data]
0x140063645  mov     qword ptr [rsp+70h+AuditSubcategoryId], rax
0x14006364a  lea     r8, [rbp+SourceName]
0x14006364e  mov     rcx, rbx
0x140063651  call    KfdAuditCommon
0x140063656  cmp     dword ptr [rdi+4], 1421h
0x14006365d  jnz     short loc_1400636DE
0x14006365f  xor     r8d, r8d; Index
0x140063662  lea     r9, [rbx+160h]; Data
0x140063669  mov     rcx, rdi; AuditParameters
0x14006366c  lea     edx, [r8+0Fh]; Type
0x140063670  call    cs:__imp_SeSetAuditParameter
0x140063677  nop     dword ptr [rax+rax+00h]
0x14006367c  test    eax, eax
0x14006367e  jz      short loc_14006369A
0x140063680  mov     r9d, r13d
0x140063683  lea     rdx, aSesetauditpara; "SeSetAuditParameter"
0x14006368a  mov     r8d, eax
0x14006368d  call    WfpReportSysErrorAsNtStatus
0x140063692  mov     rbx, rax
0x140063695  jmp     loc_140063AEC
0x14006369a  lea     r9, [rbx+128h]
0x1400636a1  cmp     [r9], r14w
0x1400636a5  jnz     short loc_1400636C2
0x1400636a7  lea     rdx, asc_140089DE4; "-"
0x1400636ae  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400636b2  call    cs:__imp_RtlInitUnicodeString
0x1400636b9  nop     dword ptr [rax+rax+00h]
0x1400636be  lea     r9, [rbp+DestinationString]; Data
0x1400636c2  mov     r8d, r13d; Index
0x1400636c5  mov     edx, r13d; Type
0x1400636c8  mov     rcx, rdi; AuditParameters
0x1400636cb  call    cs:__imp_SeSetAuditParameter
0x1400636d2  nop     dword ptr [rax+rax+00h]
0x1400636d7  test    eax, eax
0x1400636d9  jnz     short loc_140063680
0x1400636db  lea     esi, [rax+2]
0x1400636de  lea     r9, [rbp+Data]; Data
0x1400636e2  mov     r8d, esi; Index
0x1400636e5  mov     edx, 15h; Type
0x1400636ea  mov     rcx, rdi; AuditParameters
0x1400636ed  call    cs:__imp_SeSetAuditParameter
0x1400636f4  nop     dword ptr [rax+rax+00h]
0x1400636f9  test    eax, eax
0x1400636fb  jnz     short loc_140063680
0x1400636fd  cmp     [rbp+Data], 3900h
0x140063704  lea     edx, [rsi+1]
0x140063707  lea     r11d, [rdx+1]
0x14006370b  jnz     short loc_140063718
0x14006370d  mov     eax, 88h
0x140063712  lea     r10d, [rax-80h]
0x140063716  jmp     short loc_140063723
0x140063718  mov     eax, 8
0x14006371d  mov     r10d, 88h
0x140063723  lea     r8, [rax+rbx]
0x140063727  mov     rcx, rdi
0x14006372a  call    WfpSetParmTypeSockAddr
0x14006372f  mov     edx, r11d
0x140063732  lea     r8, [r10+rbx]
0x140063736  mov     rcx, rdi
0x140063739  lea     esi, [r11+1]
0x14006373d  call    WfpSetParmTypeSockAddr
0x140063742  mov     eax, [rdi+4]
0x140063745  cmp     eax, 1421h
0x14006374a  jnz     short loc_140063788
0x14006374c  lea     r9, [rbx+110h]; Data
0x140063753  mov     r8d, esi; Index
0x140063756  mov     edx, 1Bh; Type
0x14006375b  mov     rcx, rdi; AuditParameters
0x14006375e  call    cs:__imp_SeSetAuditParameter
0x140063765  nop     dword ptr [rax+rax+00h]
0x14006376a  test    eax, eax
0x14006376c  jnz     loc_140063680
0x140063772  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x140063778  test    al, 10h
0x14006377a  jz      loc_140063918
0x140063780  and     eax, r13d
0x140063783  jmp     loc_14006391D
0x140063788  cmp     eax, 141Fh
0x14006378d  jnz     loc_140063848
0x140063793  mov     [rbp+arg_8], r14d
0x140063797  lea     r9, [rbx+110h]; Data
0x14006379e  mov     r14d, 0Ah
0x1400637a4  mov     r8d, esi; Index
0x1400637a7  mov     edx, r14d; Type
0x1400637aa  mov     rcx, rdi; AuditParameters
0x1400637ad  call    cs:__imp_SeSetAuditParameter
0x1400637b4  nop     dword ptr [rax+rax+00h]
0x1400637b9  test    eax, eax
0x1400637bb  jnz     loc_140063680
0x1400637c1  mov     eax, [rbx+19Ch]
0x1400637c7  lea     r9, [rbp+arg_8]; Data
0x1400637cb  inc     esi
0x1400637cd  mov     [rbp+arg_8], eax
0x1400637d0  mov     r8d, esi; Index
0x1400637d3  lea     edx, [r14+11h]; Type
0x1400637d7  mov     rcx, rdi; AuditParameters
0x1400637da  call    cs:__imp_SeSetAuditParameter
0x1400637e1  nop     dword ptr [rax+rax+00h]
0x1400637e6  test    eax, eax
0x1400637e8  jnz     loc_140063680
0x1400637ee  mov     eax, [rbx+194h]
0x1400637f4  lea     r9, [rbp+arg_8]; Data
0x1400637f8  lea     r8d, [rsi+1]; Index
0x1400637fc  mov     [rbp+arg_8], eax
0x1400637ff  lea     edx, [r14+11h]; Type
0x140063803  mov     rcx, rdi; AuditParameters
0x140063806  call    cs:__imp_SeSetAuditParameter
0x14006380d  nop     dword ptr [rax+rax+00h]
0x140063812  test    eax, eax
0x140063814  jnz     loc_140063680
0x14006381a  movzx   eax, word ptr [rbx+198h]
0x140063821  lea     r9, [rbp+arg_8]; Data
0x140063825  add     esi, 2
0x140063828  mov     [rbp+arg_8], eax
0x14006382b  mov     r8d, esi; Index
0x14006382e  mov     edx, r14d; Type
0x140063831  mov     rcx, rdi; AuditParameters
0x140063834  call    cs:__imp_SeSetAuditParameter
0x14006383b  nop     dword ptr [rax+rax+00h]
0x140063840  xor     r14d, r14d
0x140063843  jmp     loc_14006376A
0x140063848  cmp     eax, 141Bh
0x14006384d  jnz     loc_140063B30
0x140063853  mov     [rbp+arg_10], r14d
0x140063857  lea     r9, [rbx+110h]; Data
0x14006385e  mov     r14d, 0Ah
0x140063864  mov     r8d, esi; Index
0x140063867  mov     edx, r14d; Type
0x14006386a  mov     rcx, rdi; AuditParameters
0x14006386d  call    cs:__imp_SeSetAuditParameter
0x140063874  nop     dword ptr [rax+rax+00h]
0x140063879  test    eax, eax
0x14006387b  jnz     loc_140063680
0x140063881  movzx   eax, word ptr [rbx+198h]
0x140063888  lea     r9, [rbp+arg_10]; Data
0x14006388c  lea     r8d, [rsi+1]; Index
0x140063890  mov     [rbp+arg_10], eax
0x140063893  mov     edx, r14d; Type
0x140063896  mov     rcx, rdi; AuditParameters
0x140063899  call    cs:__imp_SeSetAuditParameter
0x1400638a0  nop     dword ptr [rax+rax+00h]
0x1400638a5  xor     r14d, r14d
0x1400638a8  test    eax, eax
0x1400638aa  jnz     loc_140063680
0x1400638b0  add     esi, 2
0x1400638b3  lea     r9, [rbx+2A8h]; Data
0x1400638ba  mov     r8d, esi; Index
0x1400638bd  mov     edx, r13d; Type
0x1400638c0  mov     rcx, rdi; AuditParameters
0x1400638c3  call    cs:__imp_SeSetAuditParameter
0x1400638ca  nop     dword ptr [rax+rax+00h]
0x1400638cf  test    eax, eax
0x1400638d1  jnz     loc_140063680
0x1400638d7  mov     eax, [rbx+2B8h]
0x1400638dd  lea     r9, [rbp+arg_10]; Data
0x1400638e1  lea     r8d, [rsi+1]; Index
0x1400638e5  mov     [rbp+arg_10], eax
0x1400638e8  lea     edx, [r14+1Bh]; Type
0x1400638ec  mov     rcx, rdi; AuditParameters
0x1400638ef  call    cs:__imp_SeSetAuditParameter
0x1400638f6  nop     dword ptr [rax+rax+00h]
0x1400638fb  test    eax, eax
0x1400638fd  jnz     loc_140063680
0x140063903  mov     eax, [rbx+2BCh]
0x140063909  lea     r9, [rbp+arg_10]
0x14006390d  mov     [rbp+arg_10], eax
0x140063910  add     esi, 2
0x140063913  jmp     loc_140063753
0x140063918  call    Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline
0x14006391d  test    eax, eax
0x14006391f  jz      loc_1400639AF
0x140063925  xorps   xmm0, xmm0
0x140063928  lea     rdx, word_140088868; SourceString
0x14006392f  lea     rcx, [rbp+var_20]; DestinationString
0x140063933  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140063937  call    cs:__imp_RtlInitUnicodeString
0x14006393e  nop     dword ptr [rax+rax+00h]
0x140063943  lea     r9, [rbx+368h]
0x14006394a  cmp     [rbx+370h], r14
0x140063951  jnz     short loc_140063957
0x140063953  lea     r9, [rbp+var_20]; Data
0x140063957  lea     r8d, [rsi+1]; Index
0x14006395b  mov     edx, r13d; Type
0x14006395e  mov     rcx, rdi; AuditParameters
0x140063961  call    cs:__imp_SeSetAuditParameter
0x140063968  nop     dword ptr [rax+rax+00h]
0x14006396d  test    eax, eax
0x14006396f  jnz     loc_140063680
0x140063975  mov     eax, [rdi+4]
0x140063978  add     esi, 2
0x14006397b  sub     eax, 141Bh
0x140063980  test    eax, 0FFFFFFFBh
0x140063985  jz      short loc_1400639D7
0x140063987  lea     r9, [rbx+328h]; Data
0x14006398e  mov     r8d, esi; Index
0x140063991  mov     edx, r13d; Type
0x140063994  mov     rcx, rdi; AuditParameters
0x140063997  call    cs:__imp_SeSetAuditParameter
0x14006399e  nop     dword ptr [rax+rax+00h]
0x1400639a3  test    eax, eax
0x1400639a5  jnz     loc_140063680
0x1400639ab  inc     esi
0x1400639ad  jmp     short loc_1400639D7
0x1400639af  lea     r9, [rbx+328h]; Data
0x1400639b6  mov     edx, r13d; Type
0x1400639b9  lea     r8d, [rsi+1]; Index
0x1400639bd  mov     rcx, rdi; AuditParameters
0x1400639c0  call    cs:__imp_SeSetAuditParameter
0x1400639c7  nop     dword ptr [rax+rax+00h]
0x1400639cc  test    eax, eax
0x1400639ce  jnz     loc_140063680
0x1400639d4  add     esi, 2
0x1400639d7  lea     r9, [rbx+118h]; Data
0x1400639de  mov     r8d, esi; Index
0x1400639e1  mov     edx, 0Fh; Type
0x1400639e6  mov     rcx, rdi; AuditParameters
0x1400639e9  call    cs:__imp_SeSetAuditParameter
0x1400639f0  nop     dword ptr [rax+rax+00h]
0x1400639f5  test    eax, eax
0x1400639f7  jnz     loc_140063680
0x1400639fd  inc     esi
0x1400639ff  lea     r9, [rbp+var_40]; Data
0x140063a03  mov     r8d, esi; Index
0x140063a06  lea     edx, [rax+15h]; Type
0x140063a09  mov     rcx, rdi; AuditParameters
0x140063a0c  call    cs:__imp_SeSetAuditParameter
0x140063a13  nop     dword ptr [rax+rax+00h]
0x140063a18  test    eax, eax
0x140063a1a  jnz     loc_140063680
0x140063a20  lea     r9, [rbx+108h]; Data
0x140063a27  mov     rcx, rdi; AuditParameters
0x140063a2a  lea     r8d, [rsi+1]; Index
0x140063a2e  lea     edx, [rax+0Fh]; Type
0x140063a31  call    cs:__imp_SeSetAuditParameter
0x140063a38  nop     dword ptr [rax+rax+00h]
0x140063a3d  test    eax, eax
0x140063a3f  jnz     loc_140063680
0x140063a45  add     esi, 2
0x140063a48  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x140063a4e  test    al, 10h
0x140063a50  jz      short loc_140063A57
0x140063a52  and     eax, r13d
0x140063a55  jmp     short loc_140063A5C
0x140063a57  call    Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline
0x140063a5c  test    eax, eax
0x140063a5e  jz      short loc_140063AC6
0x140063a60  mov     ecx, [rbx+35Ch]
0x140063a66  call    ConvertSublayerWeightToMessageId
0x140063a6b  mov     rcx, rdi; AuditParameters
0x140063a6e  mov     [rbp+var_3C], eax
0x140063a71  lea     r9, [rbp+var_3C]; Data
0x140063a75  mov     r8d, esi; Index
0x140063a78  mov     edx, 15h; Type
0x140063a7d  call    cs:__imp_SeSetAuditParameter
0x140063a84  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
