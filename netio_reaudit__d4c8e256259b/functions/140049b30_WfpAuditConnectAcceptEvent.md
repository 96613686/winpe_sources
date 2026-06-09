# WfpAuditConnectAcceptEvent

- ea: `0x140049b30`
- end: `0x14004a44e`
- name: `WfpAuditConnectAcceptEvent`
- size: `2334`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140049710`

## callees

- `0x14003bf90`
- `0x140049b30`
- `0x14004b180`
- `0x14004efd4`
- `0x140060ee8`
- `0x140061f50`
- `0x140062030`
- `0x140077fa0`
- `0x140078400`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14004a3a0`
- `ntoskrnl!KeLowerIrql` at `0x14004a3a0`
- `ntoskrnl!KfRaiseIrql` at `0x140049b8d`
- `ntoskrnl!KfRaiseIrql` at `0x140049b8d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140049bba`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140049bba`
- `ntoskrnl!SeSetAuditParameter` at `0x140049e60`
- `ntoskrnl!SeSetAuditParameter` at `0x140049edb`
- `ntoskrnl!SeSetAuditParameter` at `0x140049f4b`
- `ntoskrnl!SeSetAuditParameter` at `0x140049fcb`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a00b`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a047`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a083`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a0bf`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a127`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a174`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a1bb`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a1f7`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a230`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a26c`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a2a5`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a308`
- `ntoskrnl!SeSetAuditParameter` at `0x140049e60`
- `ntoskrnl!SeSetAuditParameter` at `0x140049edb`
- `ntoskrnl!SeSetAuditParameter` at `0x140049f4b`
- `ntoskrnl!SeSetAuditParameter` at `0x140049fcb`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a00b`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a047`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a083`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a0bf`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a127`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a174`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a1bb`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a1f7`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a230`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a26c`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a2a5`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a308`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x14004a37c`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x14004a37c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140049b7b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140049b7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a3ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004a3ba`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049d53`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049f9f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049d53`
- `ntoskrnl!RtlInitUnicodeString` at `0x140049f9f`

## pseudocode

```c
__int64 __fastcall WfpAuditConnectAcceptEvent(__int64 a1)
{
  char v2; // r13
  struct _SE_ADT_PARAMETER_ARRAY *v3; // rdi
  __int64 v4; // rdx
  __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  ULONG v12; // esi
  char v13; // al
  NTSTATUS v14; // eax
  __int64 v15; // r15
  PDEVICE_OBJECT v16; // rcx
  bool v17; // zf
  __int64 v18; // rdx
  __int64 v19; // r8
  ULONG v20; // r15d
  NTSTATUS v21; // eax
  __int64 v22; // rsi
  PDEVICE_OBJECT v23; // rcx
  bool v24; // zf
  NTSTATUS v25; // eax
  ULONG v26; // esi
  int IsEnabledDeviceUsageNoInline; // eax
  struct _UNICODE_STRING *v28; // r9
  NTSTATUS v29; // eax
  ULONG v30; // r15d
  NTSTATUS v31; // eax
  NTSTATUS v32; // eax
  ULONG v33; // r15d
  NTSTATUS v34; // eax
  NTSTATUS v35; // eax
  ULONG v36; // esi
  int v37; // eax
  ULONG v38; // r15d
  NTSTATUS v39; // eax
  __int64 *v40; // r9
  NTSTATUS v41; // eax
  __int64 *v42; // r9
  NTSTATUS v43; // eax
  ULONG v44; // r15d
  NTSTATUS v45; // eax
  NTSTATUS v46; // eax
  ULONG v47; // r15d
  NTSTATUS v48; // eax
  NTSTATUS v49; // eax
  ULONG v50; // esi
  int v51; // eax
  NTSTATUS v52; // eax
  void *v53; // rcx
  int v55; // [rsp+30h] [rbp-29h] BYREF
  KIRQL v56; // [rsp+34h] [rbp-25h]
  int Data; // [rsp+38h] [rbp-21h] BYREF
  ULONG Index; // [rsp+40h] [rbp-19h] BYREF
  int v59; // [rsp+48h] [rbp-11h] BYREF
  int v60; // [rsp+4Ch] [rbp-Dh] BYREF
  int v61; // [rsp+50h] [rbp-9h] BYREF
  int v62; // [rsp+54h] [rbp-5h] BYREF
  struct _UNICODE_STRING v63; // [rsp+58h] [rbp-1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v65; // [rsp+78h] [rbp+1Fh] BYREF
  int v66; // [rsp+80h] [rbp+27h]

  DestinationString = 0;
  Data = 0;
  v55 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  Index = 0;
  v65 = 0;
  v66 = 0;
  if ( KeGetCurrentIrql() >= 2u )
  {
    v56 = 0;
    v2 = 0;
  }
  else
  {
    v56 = KfRaiseIrql(2u);
    v2 = 1;
  }
  v3 = *(struct _SE_ADT_PARAMETER_ARRAY **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0)
                                          + gWfpPerProContext
                                          + 8);
  memset(v3, 0, sizeof(struct _SE_ADT_PARAMETER_ARRAY));
  v4 = *(_QWORD *)(a1 + 264);
  LOWORD(v65) = 257;
  switch ( v4 )
  {
    case 0LL:
    case 1LL:
    case 2LL:
    case 3LL:
    case 12LL:
    case 13LL:
    case 14LL:
    case 15LL:
    case 28LL:
    case 30LL:
    case 40LL:
    case 42LL:
    case 44LL:
    case 46LL:
    case 56LL:
    case 58LL:
    case 78LL:
    case 80LL:
    case 83LL:
    case 84LL:
      Data = 14592;
      break;
    case 4LL:
    case 6LL:
    case 16LL:
    case 18LL:
    case 32LL:
    case 34LL:
    case 48LL:
    case 50LL:
    case 57LL:
    case 59LL:
    case 79LL:
    case 81LL:
    case 85LL:
    case 86LL:
      Data = 14593;
      break;
    case 8LL:
    case 9LL:
    case 10LL:
    case 11LL:
      Data = 14594;
      break;
    case 20LL:
    case 22LL:
    case 24LL:
    case 26LL:
    case 36LL:
    case 38LL:
    case 52LL:
    case 54LL:
    case 62LL:
    case 63LL:
    case 64LL:
    case 65LL:
    case 66LL:
    case 67LL:
    case 68LL:
    case 69LL:
    case 70LL:
    case 71LL:
      Data = 14595;
      break;
    case 72LL:
    case 74LL:
    case 75LL:
      Data = 14641;
      break;
    case 73LL:
    case 76LL:
    case 77LL:
      Data = 14642;
      break;
    default:
      goto LABEL_128;
  }
  switch ( v4 )
  {
    case 0LL:
    case 1LL:
    case 2LL:
    case 3LL:
    case 4LL:
    case 6LL:
      v55 = 14596;
      goto LABEL_33;
    case 8LL:
    case 9LL:
    case 10LL:
    case 11LL:
      v55 = 14598;
      goto LABEL_33;
    case 12LL:
    case 13LL:
    case 14LL:
    case 15LL:
    case 16LL:
    case 18LL:
    case 78LL:
    case 79LL:
      v55 = 14597;
      goto LABEL_33;
    case 20LL:
    case 22LL:
      v55 = 14599;
      goto LABEL_33;
    case 24LL:
    case 26LL:
      v55 = 14600;
      goto LABEL_33;
    case 28LL:
    case 30LL:
    case 32LL:
    case 34LL:
      v55 = 14601;
      goto LABEL_33;
    case 36LL:
    case 38LL:
      v55 = 14608;
      goto LABEL_33;
    case 40LL:
    case 42LL:
      v55 = 14609;
      goto LABEL_33;
    case 44LL:
    case 46LL:
      v55 = 14610;
      goto LABEL_33;
    case 48LL:
    case 50LL:
      v55 = 14611;
      goto LABEL_33;
    case 52LL:
    case 54LL:
      v55 = 14612;
      goto LABEL_33;
    case 56LL:
    case 57LL:
      v55 = 14602;
      goto LABEL_33;
    case 58LL:
    case 59LL:
    case 80LL:
    case 81LL:
      v55 = 14603;
      goto LABEL_33;
    case 62LL:
    case 63LL:
      v55 = 14614;
      goto LABEL_33;
    case 64LL:
    case 65LL:
      v55 = 14615;
      goto LABEL_33;
    case 66LL:
    case 67LL:
      v55 = 14616;
      goto LABEL_33;
    case 68LL:
    case 69LL:
      v55 = 14617;
      goto LABEL_33;
    case 70LL:
    case 71LL:
      v55 = 14624;
      goto LABEL_33;
    case 72LL:
    case 73LL:
    case 74LL:
    case 75LL:
    case 76LL:
    case 77LL:
      v55 = 14604;
      goto LABEL_33;
    case 83LL:
    case 84LL:
      v55 = 14625;
      goto LABEL_33;
    case 85LL:
    case 86LL:
      v55 = 14626;
LABEL_33:
      RtlInitUnicodeString(&DestinationString, L"Windows Filtering Platform");
      v3->AuditId = *(_DWORD *)(a1 + 288);
      v3->CategoryId = 3;
      v3->Type = *(_WORD *)(a1 + 344);
      v5 = WfpAleAuditCommon(a1, v3, &Index);
      if ( v5 )
        goto LABEL_118;
      v6 = *(_DWORD *)(a1 + 388);
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            if ( v8 != 1 )
              goto LABEL_128;
            v59 = 14646;
          }
          else
          {
            v59 = 14645;
          }
        }
        else
        {
          v59 = 14644;
        }
      }
      else
      {
        v59 = 14643;
      }
      v9 = *(_DWORD *)(a1 + 392);
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          v11 = v10 - 1;
          if ( v11 )
          {
            if ( v11 == 1 )
            {
              v60 = 14646;
              goto LABEL_50;
            }
LABEL_128:
            __fastfail(5u);
          }
          v60 = 14645;
        }
        else
        {
          v60 = 14644;
        }
      }
      else
      {
        v60 = 14643;
      }
LABEL_50:
      v12 = Index;
      v13 = *(_BYTE *)(a1 + 828);
      v61 = 1826 - (*(_DWORD *)(a1 + 400) != 0);
      v62 = 1826 - (v13 != 0);
      v14 = SeSetAuditParameter(v3, SeAdtParmTypeMessage, Index, &Data);
      v15 = v14;
      if ( v14 )
      {
        v16 = WPP_GLOBAL_Control;
        v17 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_111;
      }
      v18 = v12 + 1;
      if ( Data == 14592 )
      {
        WfpSetParmTypeSockAddr(v3, v18, a1 + 136);
        v19 = a1 + 8;
      }
      else
      {
        WfpSetParmTypeSockAddr(v3, v18, a1 + 8);
        v19 = a1 + 136;
      }
      WfpSetParmTypeSockAddr(v3, v12 + 2, v19);
      v20 = v12 + 3;
      v21 = SeSetAuditParameter(v3, SeAdtParmTypeUlongNoConv, v12 + 3, (PVOID)(a1 + 272));
      v22 = v21;
      if ( v21 )
      {
        v23 = WPP_GLOBAL_Control;
        v24 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_57;
      }
      v25 = SeSetAuditParameter(v3, SeAdtParmTypeUlongNoConv, v20 + 1, (PVOID)(a1 + 824));
      v22 = v25;
      if ( v25 )
      {
        v23 = WPP_GLOBAL_Control;
        v24 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_57;
      }
      v26 = v20 + 2;
      if ( ((__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 0x10) != 0 )
        IsEnabledDeviceUsageNoInline = (__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 1;
      else
        IsEnabledDeviceUsageNoInline = Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline();
      if ( IsEnabledDeviceUsageNoInline )
      {
        v63 = 0;
        RtlInitUnicodeString(&v63, &word_140088868);
        v28 = (struct _UNICODE_STRING *)(a1 + 872);
        if ( !*(_QWORD *)(a1 + 880) )
          v28 = &v63;
        v29 = SeSetAuditParameter(v3, SeAdtParmTypeString, v26, v28);
        v15 = v29;
        if ( v29 )
        {
          v16 = WPP_GLOBAL_Control;
          v17 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
          goto LABEL_111;
        }
        ++v26;
      }
      v30 = v26;
      v31 = SeSetAuditParameter(v3, SeAdtParmTypeString, v26, (PVOID)(a1 + 808));
      v22 = v31;
      if ( v31 )
      {
        v23 = WPP_GLOBAL_Control;
        v24 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_57;
      }
      v32 = SeSetAuditParameter(v3, SeAdtParmTypeHexInt64, v30 + 1, (PVOID)(a1 + 280));
      v22 = v32;
      if ( v32 )
      {
        v23 = WPP_GLOBAL_Control;
        v24 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_57;
      }
      v33 = v30 + 2;
      v34 = SeSetAuditParameter(v3, SeAdtParmTypeMessage, v33, &v55);
      v22 = v34;
      if ( v34 )
      {
        v23 = WPP_GLOBAL_Control;
        v24 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_57;
      }
      v35 = SeSetAuditParameter(v3, SeAdtParmTypeHexInt64, v33 + 1, (PVOID)(a1 + 264));
      v22 = v35;
      if ( v35 )
      {
        v23 = WPP_GLOBAL_Control;
        v24 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_57;
      }
      v36 = v33 + 2;
      if ( ((__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 0x10) != 0 )
        v37 = (__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 1;
      else
        v37 = Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline();
      if ( v37 )
      {
        Index = ConvertSublayerWeightToMessageId(*(unsigned int *)(a1 + 860));
        v39 = SeSetAuditParameter(v3, SeAdtParmTypeMessage, v36, &Index);
        v15 = v39;
        if ( v39 )
        {
          v16 = WPP_GLOBAL_Control;
          v17 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
          goto LABEL_111;
        }
        v38 = ++v36;
      }
      else
      {
        v38 = v33 + 2;
      }
      v40 = &v65;
      if ( *(_QWORD *)(a1 + 328) )
        v40 = *(__int64 **)(a1 + 328);
      v41 = SeSetAuditParameter(v3, SeAdtParmTypeSid, v36, v40);
      v22 = v41;
      if ( v41 )
      {
        v23 = WPP_GLOBAL_Control;
        v24 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_57;
      }
      v42 = &v65;
      if ( *(_QWORD *)(a1 + 320) )
        v42 = *(__int64 **)(a1 + 320);
      v43 = SeSetAuditParameter(v3, SeAdtParmTypeSid, v38 + 1, v42);
      v22 = v43;
      if ( v43 )
      {
        v23 = WPP_GLOBAL_Control;
        v24 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_57;
      }
      v44 = v38 + 2;
      v45 = SeSetAuditParameter(v3, SeAdtParmTypeMessage, v44, &v59);
      v22 = v45;
      if ( v45 )
      {
        v23 = WPP_GLOBAL_Control;
        v24 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_57;
      }
      v46 = SeSetAuditParameter(v3, SeAdtParmTypeMessage, v44 + 1, &v60);
      v22 = v46;
      if ( v46 )
      {
        v23 = WPP_GLOBAL_Control;
        v24 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_57;
      }
      v47 = v44 + 2;
      v48 = SeSetAuditParameter(v3, SeAdtParmTypeMessage, v47, &v61);
      v22 = v48;
      if ( v48 )
      {
        v23 = WPP_GLOBAL_Control;
        v24 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
        goto LABEL_57;
      }
      v49 = SeSetAuditParameter(v3, SeAdtParmTypeMessage, v47 + 1, &v62);
      v22 = v49;
      if ( !v49 )
      {
        v50 = v47 + 2;
        if ( ((__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 0x10) != 0 )
          v51 = (__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 1;
        else
          v51 = Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline();
        if ( v51 )
        {
          Index = ConvertFilterActionToMessageId(*(unsigned int *)(a1 + 336));
          v52 = SeSetAuditParameter(v3, SeAdtParmTypeMessage, v50, &Index);
          v15 = v52;
          if ( v52 )
          {
            v16 = WPP_GLOBAL_Control;
            v17 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_111:
            if ( !v17 && BYTE1(v16->Timer) >= 2u && (HIDWORD(v16->Timer) & 0x1000) != 0 )
              WPP_SF_sd(
                v16->AttachedDevice,
                10,
                (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                (unsigned int)"SeSetAuditParameter",
                v15);
            v5 = v15;
            goto LABEL_118;
          }
          ++v50;
        }
        v3->ParameterCount = v50;
        SeReportSecurityEventWithSubCategory(0, &DestinationString, 0, v3, 0x7Fu);
        goto LABEL_118;
      }
      v23 = WPP_GLOBAL_Control;
      v24 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_57:
      if ( !v24 && BYTE1(v23->Timer) >= 2u && (HIDWORD(v23->Timer) & 0x1000) != 0 )
        WPP_SF_sd(
          v23->AttachedDevice,
          10,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"SeSetAuditParameter",
          v22);
      v5 = v22;
LABEL_118:
      if ( v2 )
        KeLowerIrql(v56);
      v53 = *(void **)(a1 + 304);
      if ( v53 )
      {
        ExFreePoolWithTag(v53, 0);
        *(_QWORD *)(a1 + 304) = 0xBADBADFABADBADFAuLL;
      }
      if ( v5
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpAuditConnectAcceptEvent",
          v5);
      }
      return v5;
    default:
      goto LABEL_128;
  }
}

```

## disassembly

```asm
0x140049b30  push    rbp
0x140049b32  push    rdi
0x140049b33  push    r12
0x140049b35  push    r13
0x140049b37  push    r14
0x140049b39  lea     rbp, [rsp-37h]
0x140049b3e  sub     rsp, 90h
0x140049b45  mov     rax, cs:__security_cookie
0x140049b4c  xor     rax, rsp
0x140049b4f  mov     [rbp+57h+var_28], rax
0x140049b53  xor     eax, eax
0x140049b55  xorps   xmm0, xmm0
0x140049b58  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140049b5c  mov     [rbp+57h+Data], eax
0x140049b5f  mov     r14, rcx
0x140049b62  mov     [rbp+57h+var_80], eax
0x140049b65  mov     [rbp+57h+var_68], eax
0x140049b68  mov     [rbp+57h+var_64], eax
0x140049b6b  mov     [rbp+57h+var_60], eax
0x140049b6e  mov     [rbp+57h+var_5C], eax
0x140049b71  mov     [rbp+57h+Index], eax
0x140049b74  mov     [rbp+57h+var_38], rax
0x140049b78  mov     [rbp+57h+var_30], eax
0x140049b7b  call    cs:__imp_KeGetCurrentIrql
0x140049b82  nop     dword ptr [rax+rax+00h]
0x140049b87  cmp     al, 2
0x140049b89  jnb     short loc_140049BA1
0x140049b8b  mov     cl, 2; NewIrql
0x140049b8d  call    cs:__imp_KfRaiseIrql
0x140049b94  nop     dword ptr [rax+rax+00h]
0x140049b99  mov     [rbp+57h+var_7C], al
0x140049b9c  mov     r13b, 1
0x140049b9f  jmp     short loc_140049BA8
0x140049ba1  mov     [rbp+57h+var_7C], 0
0x140049ba5  xor     r13b, r13b
0x140049ba8  mov     [rsp+0B0h+arg_8], rbx
0x140049bb0  xor     ecx, ecx; ProcNumber
0x140049bb2  mov     [rsp+0B0h+arg_10], rsi
0x140049bba  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140049bc1  nop     dword ptr [rax+rax+00h]
0x140049bc6  imul    eax, cs:gWfpPerProContextSize
0x140049bcd  xor     edx, edx; Val
0x140049bcf  mov     r8d, 418h; Size
0x140049bd5  mov     ecx, eax
0x140049bd7  mov     rax, cs:gWfpPerProContext
0x140049bde  mov     rdi, [rcx+rax+8]
0x140049be3  mov     rcx, rdi; void *
0x140049be6  call    memset
0x140049beb  mov     rdx, [r14+108h]
0x140049bf2  mov     word ptr [rbp+57h+var_38], 101h
0x140049bf8  cmp     rdx, 56h; switch 87 cases
0x140049bfc  ja      def_140049C1D; jumptable 0000000140049C1D default case, cases 5,7,17,19,21,23,25,27,29,31,33,35,37,39,41,43,45,47,49,51,53,55,60,61,82
0x140049c02  lea     r8, cs:140000000h
0x140049c09  movzx   eax, ds:(byte_14008F88F - 140000000h)[r8+rdx]
0x140049c12  mov     ecx, ds:(jpt_140049C1D - 140000000h)[r8+rax*4]
0x140049c1a  add     rcx, r8
0x140049c1d  jmp     rcx; switch jump
0x140049c23  mov     [rbp+57h+Data], 3900h; jumptable 0000000140049C1D cases 0-3,12-15,28,30,40,42,44,46,56,58,78,80,83,84
0x140049c2a  jmp     short loc_140049C57
0x140049c2c  mov     [rbp+57h+Data], 3901h; jumptable 0000000140049C1D cases 4,6,16,18,32,34,48,50,57,59,79,81,85,86
0x140049c33  jmp     short loc_140049C57
0x140049c35  mov     [rbp+57h+Data], 3902h; jumptable 0000000140049C1D cases 8-11
0x140049c3c  jmp     short loc_140049C57
0x140049c3e  mov     [rbp+57h+Data], 3931h; jumptable 0000000140049C1D cases 72,74,75
0x140049c45  jmp     short loc_140049C57
0x140049c47  mov     [rbp+57h+Data], 3932h; jumptable 0000000140049C1D cases 73,76,77
0x140049c4e  jmp     short loc_140049C57
0x140049c50  mov     [rbp+57h+Data], 3903h; jumptable 0000000140049C1D cases 20,22,24,26,36,38,52,54,62-71
0x140049c57  cmp     rdx, 56h; switch 87 cases
0x140049c5b  ja      def_140049C1D; jumptable 0000000140049C1D default case, cases 5,7,17,19,21,23,25,27,29,31,33,35,37,39,41,43,45,47,49,51,53,55,60,61,82
0x140049c61  movzx   eax, ds:(byte_14008F93E - 140000000h)[r8+rdx]
0x140049c6a  mov     ecx, ds:(jpt_140049C75 - 140000000h)[r8+rax*4]
0x140049c72  add     rcx, r8
0x140049c75  jmp     rcx; switch jump
0x140049c7b  mov     [rbp+57h+var_80], 3904h; jumptable 0000000140049C75 cases 0-4,6
0x140049c82  jmp     loc_140049D48
0x140049c87  mov     [rbp+57h+var_80], 3906h; jumptable 0000000140049C75 cases 8-11
0x140049c8e  jmp     loc_140049D48
0x140049c93  mov     [rbp+57h+var_80], 3905h; jumptable 0000000140049C75 cases 12-16,18,78,79
0x140049c9a  jmp     loc_140049D48
0x140049c9f  mov     [rbp+57h+var_80], 3907h; jumptable 0000000140049C75 cases 20,22
0x140049ca6  jmp     loc_140049D48
0x140049cab  mov     [rbp+57h+var_80], 3908h; jumptable 0000000140049C75 cases 24,26
0x140049cb2  jmp     loc_140049D48
0x140049cb7  mov     [rbp+57h+var_80], 3920h; jumptable 0000000140049C75 cases 70,71
0x140049cbe  jmp     loc_140049D48
0x140049cc3  mov     [rbp+57h+var_80], 3909h; jumptable 0000000140049C75 cases 28,30,32,34
0x140049cca  jmp     short loc_140049D48
0x140049ccc  mov     [rbp+57h+var_80], 3910h; jumptable 0000000140049C75 cases 36,38
0x140049cd3  jmp     short loc_140049D48
0x140049cd5  mov     [rbp+57h+var_80], 3916h; jumptable 0000000140049C75 cases 62,63
0x140049cdc  jmp     short loc_140049D48
0x140049cde  mov     [rbp+57h+var_80], 3917h; jumptable 0000000140049C75 cases 64,65
0x140049ce5  jmp     short loc_140049D48
0x140049ce7  mov     [rbp+57h+var_80], 3918h; jumptable 0000000140049C75 cases 66,67
0x140049cee  jmp     short loc_140049D48
0x140049cf0  mov     [rbp+57h+var_80], 3919h; jumptable 0000000140049C75 cases 68,69
0x140049cf7  jmp     short loc_140049D48
0x140049cf9  mov     [rbp+57h+var_80], 3911h; jumptable 0000000140049C75 cases 40,42
0x140049d00  jmp     short loc_140049D48
0x140049d02  mov     [rbp+57h+var_80], 3912h; jumptable 0000000140049C75 cases 44,46
0x140049d09  jmp     short loc_140049D48
0x140049d0b  mov     [rbp+57h+var_80], 3913h; jumptable 0000000140049C75 cases 48,50
0x140049d12  jmp     short loc_140049D48
0x140049d14  mov     [rbp+57h+var_80], 3914h; jumptable 0000000140049C75 cases 52,54
0x140049d1b  jmp     short loc_140049D48
0x140049d1d  mov     [rbp+57h+var_80], 390Ah; jumptable 0000000140049C75 cases 56,57
0x140049d24  jmp     short loc_140049D48
0x140049d26  mov     [rbp+57h+var_80], 390Bh; jumptable 0000000140049C75 cases 58,59,80,81
0x140049d2d  jmp     short loc_140049D48
0x140049d2f  mov     [rbp+57h+var_80], 390Ch; jumptable 0000000140049C75 cases 72-77
0x140049d36  jmp     short loc_140049D48
0x140049d38  mov     [rbp+57h+var_80], 3921h; jumptable 0000000140049C75 cases 83,84
0x140049d3f  jmp     short loc_140049D48
0x140049d41  mov     [rbp+57h+var_80], 3922h; jumptable 0000000140049C75 cases 85,86
0x140049d48  lea     rdx, aWindowsFilteri; "Windows Filtering Platform"
0x140049d4f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140049d53  call    cs:__imp_RtlInitUnicodeString
0x140049d5a  nop     dword ptr [rax+rax+00h]
0x140049d5f  mov     eax, [r14+120h]
0x140049d66  lea     r8, [rbp+57h+Index]
0x140049d6a  mov     [rdi+4], eax
0x140049d6d  mov     rdx, rdi
0x140049d70  mov     dword ptr [rdi], 3
0x140049d76  mov     rcx, r14
0x140049d79  movzx   eax, word ptr [r14+158h]
0x140049d81  mov     [rdi+12h], ax
0x140049d85  call    WfpAleAuditCommon
0x140049d8a  lea     rsi, WPP_GLOBAL_Control
0x140049d91  mov     rbx, rax
0x140049d94  test    rax, rax
0x140049d97  jnz     loc_14004A397
0x140049d9d  mov     eax, [r14+184h]
0x140049da4  test    eax, eax
0x140049da6  jz      short loc_140049DD6
0x140049da8  sub     eax, 1
0x140049dab  jz      short loc_140049DCD
0x140049dad  sub     eax, 1
0x140049db0  jz      short loc_140049DC4
0x140049db2  cmp     eax, 1
0x140049db5  jnz     def_140049C1D; jumptable 0000000140049C1D default case, cases 5,7,17,19,21,23,25,27,29,31,33,35,37,39,41,43,45,47,49,51,53,55,60,61,82
0x140049dbb  mov     [rbp+57h+var_68], 3936h
0x140049dc2  jmp     short loc_140049DDD
0x140049dc4  mov     [rbp+57h+var_68], 3935h
0x140049dcb  jmp     short loc_140049DDD
0x140049dcd  mov     [rbp+57h+var_68], 3934h
0x140049dd4  jmp     short loc_140049DDD
0x140049dd6  mov     [rbp+57h+var_68], 3933h
0x140049ddd  mov     ecx, [r14+188h]
0x140049de4  test    ecx, ecx
0x140049de6  jz      short loc_140049E16
0x140049de8  sub     ecx, 1
0x140049deb  jz      short loc_140049E0D
0x140049ded  sub     ecx, 1
0x140049df0  jz      short loc_140049E04
0x140049df2  cmp     ecx, 1
0x140049df5  jnz     def_140049C1D; jumptable 0000000140049C1D default case, cases 5,7,17,19,21,23,25,27,29,31,33,35,37,39,41,43,45,47,49,51,53,55,60,61,82
0x140049dfb  mov     [rbp+57h+var_64], 3936h
0x140049e02  jmp     short loc_140049E1D
0x140049e04  mov     [rbp+57h+var_64], 3935h
0x140049e0b  jmp     short loc_140049E1D
0x140049e0d  mov     [rbp+57h+var_64], 3934h
0x140049e14  jmp     short loc_140049E1D
0x140049e16  mov     [rbp+57h+var_64], 3933h
0x140049e1d  mov     eax, [r14+190h]
0x140049e24  lea     r9, [rbp+57h+Data]; Data
0x140049e28  mov     esi, [rbp+57h+Index]
0x140049e2b  neg     eax
0x140049e2d  movzx   eax, byte ptr [r14+33Ch]
0x140049e35  mov     r8d, esi; Index
0x140049e38  sbb     ecx, ecx
0x140049e3a  mov     [rsp+0B0h+arg_18], r15
0x140049e42  add     ecx, 722h
0x140049e48  mov     edx, 15h; Type
0x140049e4d  mov     [rbp+57h+var_60], ecx
0x140049e50  neg     al
0x140049e52  sbb     ecx, ecx
0x140049e54  add     ecx, 722h
0x140049e5a  mov     [rbp+57h+var_5C], ecx
0x140049e5d  mov     rcx, rdi; AuditParameters
0x140049e60  call    cs:__imp_SeSetAuditParameter
0x140049e67  nop     dword ptr [rax+rax+00h]
0x140049e6c  movsxd  r15, eax
0x140049e6f  test    eax, eax
0x140049e71  jz      short loc_140049E89
0x140049e73  mov     rcx, cs:WPP_GLOBAL_Control
0x140049e7a  lea     rsi, WPP_GLOBAL_Control
0x140049e81  cmp     rcx, rsi
0x140049e84  jmp     loc_14004A32C
0x140049e89  cmp     [rbp+57h+Data], 3900h
0x140049e90  lea     edx, [rsi+1]
0x140049e93  mov     rcx, rdi
0x140049e96  jnz     short loc_140049EAA
0x140049e98  lea     r8, [r14+88h]
0x140049e9f  call    WfpSetParmTypeSockAddr
0x140049ea4  lea     r8, [r14+8]
0x140049ea8  jmp     short loc_140049EBA
0x140049eaa  lea     r8, [r14+8]
0x140049eae  call    WfpSetParmTypeSockAddr
0x140049eb3  lea     r8, [r14+88h]
0x140049eba  lea     edx, [rsi+2]
0x140049ebd  mov     rcx, rdi
0x140049ec0  call    WfpSetParmTypeSockAddr
0x140049ec5  lea     r15d, [rsi+3]
0x140049ec9  mov     edx, 1Bh; Type
0x140049ece  mov     r8d, r15d; Index
0x140049ed1  lea     r9, [r14+110h]; Data
0x140049ed8  mov     rcx, rdi; AuditParameters
0x140049edb  call    cs:__imp_SeSetAuditParameter
0x140049ee2  nop     dword ptr [rax+rax+00h]
0x140049ee7  movsxd  rsi, eax
0x140049eea  test    eax, eax
0x140049eec  jz      short loc_140049F38
0x140049eee  mov     rcx, cs:WPP_GLOBAL_Control
0x140049ef5  lea     rax, WPP_GLOBAL_Control
0x140049efc  cmp     rcx, rax
0x140049eff  jz      short loc_140049F30
0x140049f01  cmp     byte ptr [rcx+29h], 2
0x140049f05  jb      short loc_140049F30
0x140049f07  test    dword ptr [rcx+2Ch], 1000h
0x140049f0e  jz      short loc_140049F30
0x140049f10  mov     rcx, [rcx+18h]
0x140049f14  lea     r9, aSesetauditpara; "SeSetAuditParameter"
0x140049f1b  mov     edx, 0Ah
0x140049f20  mov     [rsp+0B0h+AuditSubcategoryId], esi
0x140049f24  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140049f2b  call    WPP_SF_sd
0x140049f30  mov     rbx, rsi
0x140049f33  jmp     loc_14004A388
0x140049f38  lea     r9, [r14+338h]; Data
0x140049f3f  mov     edx, 1Bh; Type
0x140049f44  lea     r8d, [r15+1]; Index
0x140049f48  mov     rcx, rdi; AuditParameters
0x140049f4b  call    cs:__imp_SeSetAuditParameter
0x140049f52  nop     dword ptr [rax+rax+00h]
0x140049f57  movsxd  rsi, eax
0x140049f5a  test    eax, eax
0x140049f5c  jz      short loc_140049F71
0x140049f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140049f65  lea     rax, WPP_GLOBAL_Control
0x140049f6c  cmp     rcx, rax
0x140049f6f  jmp     short loc_140049EFF
0x140049f71  lea     esi, [r15+2]
0x140049f75  mov     eax, dword ptr cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x140049f7b  test    al, 10h
0x140049f7d  jz      short loc_140049F84
0x140049f7f  and     eax, 1
0x140049f82  jmp     short loc_140049F89
0x140049f84  call    Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline
0x140049f89  test    eax, eax
0x140049f8b  jz      short loc_140049FF6
0x140049f8d  xorps   xmm0, xmm0
0x140049f90  lea     rdx, word_140088868; SourceString
0x140049f97  lea     rcx, [rbp+57h+var_58]; DestinationString
0x140049f9b  movups  xmmword ptr [rbp+57h+var_58.Length], xmm0
0x140049f9f  call    cs:__imp_RtlInitUnicodeString
0x140049fa6  nop     dword ptr [rax+rax+00h]
0x140049fab  cmp     qword ptr [r14+370h], 0
0x140049fb3  lea     r9, [r14+368h]
0x140049fba  jnz     short loc_140049FC0
0x140049fbc  lea     r9, [rbp+57h+var_58]; Data
0x140049fc0  mov     r8d, esi; Index
0x140049fc3  mov     edx, 1; Type
0x140049fc8  mov     rcx, rdi; AuditParameters
0x140049fcb  call    cs:__imp_SeSetAuditParameter
0x140049fd2  nop     dword ptr [rax+rax+00h]
0x140049fd7  movsxd  r15, eax
0x140049fda  test    eax, eax
0x140049fdc  jz      short loc_140049FF4
0x140049fde  mov     rcx, cs:WPP_GLOBAL_Control
0x140049fe5  lea     rsi, WPP_GLOBAL_Control
0x140049fec  cmp     rcx, rsi
0x140049fef  jmp     loc_14004A32C
0x140049ff4  inc     esi
0x140049ff6  lea     r9, [r14+328h]; Data
0x140049ffd  mov     r8d, esi; Index
0x14004a000  mov     edx, 1; Type
0x14004a005  mov     rcx, rdi; AuditParameters
0x14004a008  mov     r15d, esi
0x14004a00b  call    cs:__imp_SeSetAuditParameter
0x14004a012  nop     dword ptr [rax+rax+00h]
0x14004a017  movsxd  rsi, eax
0x14004a01a  test    eax, eax
0x14004a01c  jz      short loc_14004A034
0x14004a01e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a025  lea     rax, WPP_GLOBAL_Control
0x14004a02c  cmp     rcx, rax
0x14004a02f  jmp     loc_140049EFF
0x14004a034  lea     r9, [r14+118h]; Data
0x14004a03b  mov     edx, 0Fh; Type
0x14004a040  lea     r8d, [r15+1]; Index
0x14004a044  mov     rcx, rdi; AuditParameters
0x14004a047  call    cs:__imp_SeSetAuditParameter
0x14004a04e  nop     dword ptr [rax+rax+00h]
0x14004a053  movsxd  rsi, eax
0x14004a056  test    eax, eax
0x14004a058  jz      short loc_14004A070
0x14004a05a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a061  lea     rax, WPP_GLOBAL_Control
0x14004a068  cmp     rcx, rax
  ... truncated ...
```
