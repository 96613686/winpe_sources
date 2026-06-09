# WfpAuditEventGeneral

- ea: `0x14004a460`
- end: `0x14004ae78`
- name: `WfpAuditEventGeneral`
- size: `2584`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140049710`

## callees

- `0x14004a460`
- `0x14004b180`
- `0x14004efd4`
- `0x140060ee8`
- `0x140061f50`
- `0x140062030`
- `0x140078400`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14004ae0d`
- `ntoskrnl!KeLowerIrql` at `0x14004ae0d`
- `ntoskrnl!KfRaiseIrql` at `0x14004a49d`
- `ntoskrnl!KfRaiseIrql` at `0x14004a49d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004a4bf`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14004a4bf`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a69d`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a70c`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a755`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a7cb`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a88c`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a8dd`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a922`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a964`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a9aa`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a9fb`
- `ntoskrnl!SeSetAuditParameter` at `0x14004aa41`
- `ntoskrnl!SeSetAuditParameter` at `0x14004aa7f`
- `ntoskrnl!SeSetAuditParameter` at `0x14004aac1`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ab06`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ab8d`
- `ntoskrnl!SeSetAuditParameter` at `0x14004abdb`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ac1a`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ac59`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ac95`
- `ntoskrnl!SeSetAuditParameter` at `0x14004acd1`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ad37`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ad7e`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a69d`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a70c`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a755`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a7cb`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a88c`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a8dd`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a922`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a964`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a9aa`
- `ntoskrnl!SeSetAuditParameter` at `0x14004a9fb`
- `ntoskrnl!SeSetAuditParameter` at `0x14004aa41`
- `ntoskrnl!SeSetAuditParameter` at `0x14004aa7f`
- `ntoskrnl!SeSetAuditParameter` at `0x14004aac1`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ab06`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ab8d`
- `ntoskrnl!SeSetAuditParameter` at `0x14004abdb`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ac1a`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ac59`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ac95`
- `ntoskrnl!SeSetAuditParameter` at `0x14004acd1`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ad37`
- `ntoskrnl!SeSetAuditParameter` at `0x14004ad7e`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x14004adf1`
- `ntoskrnl!SeReportSecurityEventWithSubCategory` at `0x14004adf1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004a48b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14004a48b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004a652`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004a73a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004ab61`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004a652`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004a73a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004ab61`

## pseudocode

```c
__int64 __fastcall WfpAuditEventGeneral(__int64 a1)
{
  ULONG v1; // esi
  KIRQL v3; // r13
  char v4; // r12
  struct _SE_ADT_PARAMETER_ARRAY *v5; // rdi
  __int64 v6; // rdx
  ULONG v7; // ecx
  NTSTATUS v8; // eax
  __int64 v9; // rsi
  PDEVICE_OBJECT v10; // rcx
  bool v11; // zf
  __int64 v12; // rbx
  NTSTATUS v13; // eax
  PDEVICE_OBJECT v14; // rcx
  bool v15; // zf
  NTSTATUS v16; // eax
  NTSTATUS v17; // eax
  __int64 v18; // r14
  PDEVICE_OBJECT v19; // rcx
  bool v20; // zf
  __int64 v21; // rax
  __int64 v22; // r10
  unsigned int v23; // r11d
  ULONG v24; // esi
  ULONG AuditId; // eax
  NTSTATUS v26; // eax
  NTSTATUS v27; // eax
  ULONG v28; // r14d
  NTSTATUS v29; // eax
  NTSTATUS v30; // eax
  NTSTATUS v31; // eax
  NTSTATUS v32; // eax
  ULONG v33; // r14d
  NTSTATUS v34; // eax
  ULONG v35; // r14d
  NTSTATUS v36; // eax
  NTSTATUS v37; // eax
  NTSTATUS v38; // eax
  ULONG v39; // r14d
  int IsEnabledDeviceUsageNoInline; // eax
  struct _UNICODE_STRING *v41; // r9
  NTSTATUS v42; // eax
  ULONG v43; // esi
  NTSTATUS v44; // eax
  NTSTATUS v45; // eax
  NTSTATUS v46; // eax
  ULONG v47; // r14d
  NTSTATUS v48; // eax
  NTSTATUS v49; // eax
  ULONG v50; // esi
  int v51; // eax
  NTSTATUS v52; // eax
  NTSTATUS v53; // eax
  struct _UNICODE_STRING Data; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING v56; // [rsp+40h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-20h] BYREF
  int v58; // [rsp+B0h] [rbp+40h] BYREF
  int v59; // [rsp+B8h] [rbp+48h] BYREF
  int v60; // [rsp+C0h] [rbp+50h] BYREF
  int v61; // [rsp+C8h] [rbp+58h] BYREF

  v1 = 0;
  DestinationString = 0;
  v59 = 0;
  Data = 0;
  v58 = 0;
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
  v6 = *(_QWORD *)(a1 + 264);
  switch ( v6 )
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
      v59 = 14592;
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
      v59 = 14593;
      break;
    case 8LL:
    case 9LL:
    case 10LL:
    case 11LL:
      v59 = 14594;
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
      v59 = 14595;
      break;
    case 72LL:
    case 74LL:
    case 75LL:
      v59 = 14641;
      break;
    case 73LL:
    case 76LL:
    case 77LL:
      v59 = 14642;
      break;
    default:
      goto LABEL_126;
  }
  switch ( v6 )
  {
    case 0LL:
    case 1LL:
    case 2LL:
    case 3LL:
    case 4LL:
    case 6LL:
      v58 = 14596;
      goto LABEL_33;
    case 8LL:
    case 9LL:
    case 10LL:
    case 11LL:
      v58 = 14598;
      goto LABEL_33;
    case 12LL:
    case 13LL:
    case 14LL:
    case 15LL:
    case 16LL:
    case 18LL:
    case 78LL:
    case 79LL:
      v58 = 14597;
      goto LABEL_33;
    case 20LL:
    case 22LL:
      v58 = 14599;
      goto LABEL_33;
    case 24LL:
    case 26LL:
      v58 = 14600;
      goto LABEL_33;
    case 28LL:
    case 30LL:
    case 32LL:
    case 34LL:
      v58 = 14601;
      goto LABEL_33;
    case 36LL:
    case 38LL:
      v58 = 14608;
      goto LABEL_33;
    case 40LL:
    case 42LL:
      v58 = 14609;
      goto LABEL_33;
    case 44LL:
    case 46LL:
      v58 = 14610;
      goto LABEL_33;
    case 48LL:
    case 50LL:
      v58 = 14611;
      goto LABEL_33;
    case 52LL:
    case 54LL:
      v58 = 14612;
      goto LABEL_33;
    case 56LL:
    case 57LL:
      v58 = 14602;
      goto LABEL_33;
    case 58LL:
    case 59LL:
    case 80LL:
    case 81LL:
      v58 = 14603;
      goto LABEL_33;
    case 62LL:
    case 63LL:
      v58 = 14614;
      goto LABEL_33;
    case 64LL:
    case 65LL:
      v58 = 14615;
      goto LABEL_33;
    case 66LL:
    case 67LL:
      v58 = 14616;
      goto LABEL_33;
    case 68LL:
    case 69LL:
      v58 = 14617;
      goto LABEL_33;
    case 70LL:
    case 71LL:
      v58 = 14624;
      goto LABEL_33;
    case 72LL:
    case 73LL:
    case 74LL:
    case 75LL:
    case 76LL:
    case 77LL:
      v58 = 14604;
      goto LABEL_33;
    case 83LL:
    case 84LL:
      v58 = 14625;
      goto LABEL_33;
    case 85LL:
    case 86LL:
      v58 = 14626;
LABEL_33:
      RtlInitUnicodeString(&DestinationString, L"Windows Filtering Platform");
      v7 = *(_DWORD *)(a1 + 288);
      v5->AuditId = v7;
      v5->CategoryId = 3;
      v5->Type = *(_WORD *)(a1 + 344);
      if ( v7 != 5152 )
        goto LABEL_51;
      v8 = SeSetAuditParameter(v5, SeAdtParmTypeHexInt64, 0, (PVOID)(a1 + 352));
      v9 = v8;
      if ( v8 )
      {
        v10 = WPP_GLOBAL_Control;
        v11 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_36:
        if ( !v11 && BYTE1(v10->Timer) >= 2u && (HIDWORD(v10->Timer) & 0x1000) != 0 )
          WPP_SF_sd(
            v10->AttachedDevice,
            10,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"SeSetAuditParameter",
            v9);
        goto LABEL_40;
      }
      if ( *(_WORD *)(a1 + 296) )
      {
        v13 = SeSetAuditParameter(v5, SeAdtParmTypeString, 1u, (PVOID)(a1 + 296));
        v9 = v13;
        if ( v13 )
        {
          v14 = WPP_GLOBAL_Control;
          v15 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
          goto LABEL_46;
        }
LABEL_50:
        v1 = 2;
LABEL_51:
        v17 = SeSetAuditParameter(v5, SeAdtParmTypeMessage, v1, &v59);
        v18 = v17;
        if ( v17 )
        {
          v19 = WPP_GLOBAL_Control;
          v20 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
          goto LABEL_53;
        }
        if ( v59 == 14592 )
          v21 = 136;
        else
          v21 = 8;
        WfpSetParmTypeSockAddr(v5, v1 + 1, v21 + a1);
        v24 = v23 + 1;
        WfpSetParmTypeSockAddr(v5, v23, v22 + a1);
        AuditId = v5->AuditId;
        switch ( AuditId )
        {
          case 0x1420u:
            v26 = SeSetAuditParameter(v5, SeAdtParmTypeUlongNoConv, v24, (PVOID)(a1 + 272));
            v18 = v26;
            if ( v26 )
            {
              v19 = WPP_GLOBAL_Control;
              v20 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
              goto LABEL_53;
            }
            break;
          case 0x141Eu:
            v60 = 0;
            v27 = SeSetAuditParameter(v5, SeAdtParmTypeHexUlong, v24, (PVOID)(a1 + 272));
            v18 = v27;
            if ( v27 )
            {
              v19 = WPP_GLOBAL_Control;
              v20 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
              goto LABEL_53;
            }
            v28 = v24 + 1;
            v60 = *(_DWORD *)(a1 + 412);
            v29 = SeSetAuditParameter(v5, SeAdtParmTypeUlongNoConv, v24 + 1, &v60);
            v9 = v29;
            if ( v29 )
            {
              v10 = WPP_GLOBAL_Control;
              v11 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
              goto LABEL_36;
            }
            v60 = *(_DWORD *)(a1 + 404);
            v30 = SeSetAuditParameter(v5, SeAdtParmTypeUlongNoConv, v28 + 1, &v60);
            v9 = v30;
            if ( v30 )
            {
              v10 = WPP_GLOBAL_Control;
              v11 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
              goto LABEL_36;
            }
            v24 = v28 + 2;
            v60 = *(unsigned __int16 *)(a1 + 408);
            v31 = SeSetAuditParameter(v5, SeAdtParmTypeHexUlong, v28 + 2, &v60);
            v18 = v31;
            if ( v31 )
            {
              v19 = WPP_GLOBAL_Control;
              v20 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
              goto LABEL_53;
            }
            break;
          case 0x141Au:
            v60 = 0;
            v32 = SeSetAuditParameter(v5, SeAdtParmTypeHexUlong, v24, (PVOID)(a1 + 272));
            v18 = v32;
            if ( v32 )
            {
              v19 = WPP_GLOBAL_Control;
              v20 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
              goto LABEL_53;
            }
            v33 = v24 + 1;
            v60 = *(unsigned __int16 *)(a1 + 408);
            v34 = SeSetAuditParameter(v5, SeAdtParmTypeHexUlong, v24 + 1, &v60);
            v9 = v34;
            if ( v34 )
            {
              v10 = WPP_GLOBAL_Control;
              v11 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
              goto LABEL_36;
            }
            v35 = v33 + 1;
            v36 = SeSetAuditParameter(v5, SeAdtParmTypeString, v35, (PVOID)(a1 + 680));
            v9 = v36;
            if ( v36 )
            {
              v10 = WPP_GLOBAL_Control;
              v11 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
              goto LABEL_36;
            }
            v60 = *(_DWORD *)(a1 + 696);
            v37 = SeSetAuditParameter(v5, SeAdtParmTypeUlongNoConv, v35 + 1, &v60);
            v9 = v37;
            if ( v37 )
            {
              v10 = WPP_GLOBAL_Control;
              v11 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
              goto LABEL_36;
            }
            v24 = v35 + 2;
            v60 = *(_DWORD *)(a1 + 700);
            v38 = SeSetAuditParameter(v5, SeAdtParmTypeUlongNoConv, v35 + 2, &v60);
            v18 = v38;
            if ( v38 )
            {
              v19 = WPP_GLOBAL_Control;
              v20 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
              goto LABEL_53;
            }
            break;
          default:
LABEL_126:
            __fastfail(5u);
        }
        v39 = v24 + 1;
        if ( ((__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 0x10) != 0 )
          IsEnabledDeviceUsageNoInline = (__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 1;
        else
          IsEnabledDeviceUsageNoInline = Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline();
        if ( IsEnabledDeviceUsageNoInline )
        {
          v56 = 0;
          RtlInitUnicodeString(&v56, &word_140088868);
          v41 = (struct _UNICODE_STRING *)(a1 + 872);
          if ( !*(_QWORD *)(a1 + 880) )
            v41 = &v56;
          v42 = SeSetAuditParameter(v5, SeAdtParmTypeString, v39, v41);
          v9 = v42;
          if ( v42 )
          {
            v10 = WPP_GLOBAL_Control;
            v11 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
            goto LABEL_36;
          }
          v43 = v39 + 1;
          if ( ((v5->AuditId - 5146) & 0xFFFFFFFB) != 0 )
          {
            v44 = SeSetAuditParameter(v5, SeAdtParmTypeString, v43, (PVOID)(a1 + 808));
            v18 = v44;
            if ( v44 )
            {
              v19 = WPP_GLOBAL_Control;
              v20 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
              goto LABEL_53;
            }
            ++v43;
          }
        }
        else
        {
          v45 = SeSetAuditParameter(v5, SeAdtParmTypeString, v39, (PVOID)(a1 + 808));
          v9 = v45;
          if ( v45 )
          {
            v10 = WPP_GLOBAL_Control;
            v11 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
            goto LABEL_36;
          }
          v43 = v39 + 1;
        }
        v46 = SeSetAuditParameter(v5, SeAdtParmTypeHexInt64, v43, (PVOID)(a1 + 280));
        v18 = v46;
        if ( v46 )
        {
          v19 = WPP_GLOBAL_Control;
          v20 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
          goto LABEL_53;
        }
        v47 = v43 + 1;
        v48 = SeSetAuditParameter(v5, SeAdtParmTypeMessage, v43 + 1, &v58);
        v9 = v48;
        if ( v48 )
        {
          v10 = WPP_GLOBAL_Control;
          v11 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
          goto LABEL_36;
        }
        v49 = SeSetAuditParameter(v5, SeAdtParmTypeHexInt64, v47 + 1, (PVOID)(a1 + 264));
        v9 = v49;
        if ( v49 )
        {
          v10 = WPP_GLOBAL_Control;
          v11 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
          goto LABEL_36;
        }
        v50 = v47 + 2;
        if ( ((__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 0x10) != 0 )
          v51 = (__int64)WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink & 1;
        else
          v51 = Feature_Netsec_WFP_Audit_Event_Enrichment__private_IsEnabledDeviceUsageNoInline();
        if ( v51 )
        {
          v60 = ConvertSublayerWeightToMessageId(*(unsigned int *)(a1 + 860));
          v52 = SeSetAuditParameter(v5, SeAdtParmTypeMessage, v50, &v60);
          v18 = v52;
          if ( v52 )
          {
            v19 = WPP_GLOBAL_Control;
            v20 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_53:
            if ( !v20 && BYTE1(v19->Timer) >= 2u && (HIDWORD(v19->Timer) & 0x1000) != 0 )
              WPP_SF_sd(
                v19->AttachedDevice,
                10,
                (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                (unsigned int)"SeSetAuditParameter",
                v18);
            v12 = v18;
            goto LABEL_118;
          }
          v61 = ConvertFilterActionToMessageId(*(unsigned int *)(a1 + 336));
          v53 = SeSetAuditParameter(v5, SeAdtParmTypeMessage, v50 + 1, &v61);
          v12 = v53;
          if ( v53 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
            {
              WPP_SF_sd(
                WPP_GLOBAL_Control->AttachedDevice,
                10,
                (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                (unsigned int)"SeSetAuditParameter",
                v53);
            }
            goto LABEL_118;
          }
          v50 += 2;
        }
        v12 = 0;
        v5->ParameterCount = v50;
        SeReportSecurityEventWithSubCategory(0, &DestinationString, 0, v5, 0x7Eu);
        goto LABEL_118;
      }
      RtlInitUnicodeString(&Data, L"-");
      v16 = SeSetAuditParameter(v5, SeAdtParmTypeString, 1u, &Data);
      v9 = v16;
      if ( !v16 )
        goto LABEL_50;
      v14 = WPP_GLOBAL_Control;
      v15 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_46:
      if ( v15 || BYTE1(v14->Timer) < 2u || (HIDWORD(v14->Timer) & 0x1000) == 0 )
      {
LABEL_40:
        v12 = v9;
        goto LABEL_118;
      }
      WPP_SF_sd(
        v14->AttachedDevice,
        10,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"SeSetAuditParameter",
        v9);
      v12 = v9;
LABEL_118:
      if ( v4 )
        KeLowerIrql(v3);
      if ( v12
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
      {
        WPP_SF_sd(
          WPP_GLOBAL_Control->AttachedDevice,
          15,
          (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
          (unsigned int)"WfpAuditEventGeneral",
          v12);
      }
      return v12;
    default:
      goto LABEL_126;
  }
}

```

## disassembly

```asm
0x14004a460  push    rbp
0x14004a462  push    rbx
0x14004a463  push    rsi
0x14004a464  push    rdi
0x14004a465  push    r12
0x14004a467  push    r13
0x14004a469  push    r15
0x14004a46b  mov     rbp, rsp
0x14004a46e  sub     rsp, 70h
0x14004a472  xorps   xmm0, xmm0
0x14004a475  xorps   xmm1, xmm1
0x14004a478  xor     esi, esi
0x14004a47a  mov     rbx, rcx
0x14004a47d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14004a481  mov     [rbp+arg_8], esi
0x14004a484  movups  xmmword ptr [rbp+Data.Length], xmm1
0x14004a488  mov     [rbp+arg_0], esi
0x14004a48b  call    cs:__imp_KeGetCurrentIrql
0x14004a492  nop     dword ptr [rax+rax+00h]
0x14004a497  cmp     al, 2
0x14004a499  jnb     short loc_14004A4B2
0x14004a49b  mov     cl, 2; NewIrql
0x14004a49d  call    cs:__imp_KfRaiseIrql
0x14004a4a4  nop     dword ptr [rax+rax+00h]
0x14004a4a9  movzx   r13d, al
0x14004a4ad  mov     r12b, 1
0x14004a4b0  jmp     short loc_14004A4B8
0x14004a4b2  xor     r13b, r13b
0x14004a4b5  xor     r12b, r12b
0x14004a4b8  xor     ecx, ecx; ProcNumber
0x14004a4ba  mov     [rsp+70h+var_8], r14
0x14004a4bf  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14004a4c6  nop     dword ptr [rax+rax+00h]
0x14004a4cb  imul    eax, cs:gWfpPerProContextSize
0x14004a4d2  xor     edx, edx; Val
0x14004a4d4  mov     r8d, 418h; Size
0x14004a4da  mov     ecx, eax
0x14004a4dc  mov     rax, cs:gWfpPerProContext
0x14004a4e3  mov     rdi, [rcx+rax+8]
0x14004a4e8  mov     rcx, rdi; void *
0x14004a4eb  call    memset
0x14004a4f0  mov     rdx, [rbx+108h]
0x14004a4f7  cmp     rdx, 56h; switch 87 cases
0x14004a4fb  ja      def_14004A51C; jumptable 000000014004A51C default case, cases 5,7,17,19,21,23,25,27,29,31,33,35,37,39,41,43,45,47,49,51,53,55,60,61,82
0x14004a501  lea     r8, cs:140000000h
0x14004a508  movzx   eax, ds:(byte_14008F9B1 - 140000000h)[r8+rdx]
0x14004a511  mov     ecx, ds:(jpt_14004A51C - 140000000h)[r8+rax*4]
0x14004a519  add     rcx, r8
0x14004a51c  jmp     rcx; switch jump
0x14004a522  mov     [rbp+arg_8], 3900h; jumptable 000000014004A51C cases 0-3,12-15,28,30,40,42,44,46,56,58,78,80,83,84
0x14004a529  jmp     short loc_14004A556
0x14004a52b  mov     [rbp+arg_8], 3901h; jumptable 000000014004A51C cases 4,6,16,18,32,34,48,50,57,59,79,81,85,86
0x14004a532  jmp     short loc_14004A556
0x14004a534  mov     [rbp+arg_8], 3902h; jumptable 000000014004A51C cases 8-11
0x14004a53b  jmp     short loc_14004A556
0x14004a53d  mov     [rbp+arg_8], 3931h; jumptable 000000014004A51C cases 72,74,75
0x14004a544  jmp     short loc_14004A556
0x14004a546  mov     [rbp+arg_8], 3932h; jumptable 000000014004A51C cases 73,76,77
0x14004a54d  jmp     short loc_14004A556
0x14004a54f  mov     [rbp+arg_8], 3903h; jumptable 000000014004A51C cases 20,22,24,26,36,38,52,54,62-71
0x14004a556  cmp     rdx, 56h; switch 87 cases
0x14004a55a  ja      def_14004A51C; jumptable 000000014004A51C default case, cases 5,7,17,19,21,23,25,27,29,31,33,35,37,39,41,43,45,47,49,51,53,55,60,61,82
0x14004a560  movzx   eax, ds:(byte_14008FA60 - 140000000h)[r8+rdx]
0x14004a569  mov     ecx, ds:(jpt_14004A574 - 140000000h)[r8+rax*4]
0x14004a571  add     rcx, r8
0x14004a574  jmp     rcx; switch jump
0x14004a57a  mov     [rbp+arg_0], 3904h; jumptable 000000014004A574 cases 0-4,6
0x14004a581  jmp     loc_14004A647
0x14004a586  mov     [rbp+arg_0], 3906h; jumptable 000000014004A574 cases 8-11
0x14004a58d  jmp     loc_14004A647
0x14004a592  mov     [rbp+arg_0], 3905h; jumptable 000000014004A574 cases 12-16,18,78,79
0x14004a599  jmp     loc_14004A647
0x14004a59e  mov     [rbp+arg_0], 3907h; jumptable 000000014004A574 cases 20,22
0x14004a5a5  jmp     loc_14004A647
0x14004a5aa  mov     [rbp+arg_0], 3908h; jumptable 000000014004A574 cases 24,26
0x14004a5b1  jmp     loc_14004A647
0x14004a5b6  mov     [rbp+arg_0], 3920h; jumptable 000000014004A574 cases 70,71
0x14004a5bd  jmp     loc_14004A647
0x14004a5c2  mov     [rbp+arg_0], 3909h; jumptable 000000014004A574 cases 28,30,32,34
0x14004a5c9  jmp     short loc_14004A647
0x14004a5cb  mov     [rbp+arg_0], 3910h; jumptable 000000014004A574 cases 36,38
0x14004a5d2  jmp     short loc_14004A647
0x14004a5d4  mov     [rbp+arg_0], 3916h; jumptable 000000014004A574 cases 62,63
0x14004a5db  jmp     short loc_14004A647
0x14004a5dd  mov     [rbp+arg_0], 3917h; jumptable 000000014004A574 cases 64,65
0x14004a5e4  jmp     short loc_14004A647
0x14004a5e6  mov     [rbp+arg_0], 3918h; jumptable 000000014004A574 cases 66,67
0x14004a5ed  jmp     short loc_14004A647
0x14004a5ef  mov     [rbp+arg_0], 3919h; jumptable 000000014004A574 cases 68,69
0x14004a5f6  jmp     short loc_14004A647
0x14004a5f8  mov     [rbp+arg_0], 3911h; jumptable 000000014004A574 cases 40,42
0x14004a5ff  jmp     short loc_14004A647
0x14004a601  mov     [rbp+arg_0], 3912h; jumptable 000000014004A574 cases 44,46
0x14004a608  jmp     short loc_14004A647
0x14004a60a  mov     [rbp+arg_0], 3913h; jumptable 000000014004A574 cases 48,50
0x14004a611  jmp     short loc_14004A647
0x14004a613  mov     [rbp+arg_0], 3914h; jumptable 000000014004A574 cases 52,54
0x14004a61a  jmp     short loc_14004A647
0x14004a61c  mov     [rbp+arg_0], 390Ah; jumptable 000000014004A574 cases 56,57
0x14004a623  jmp     short loc_14004A647
0x14004a625  mov     [rbp+arg_0], 390Bh; jumptable 000000014004A574 cases 58,59,80,81
0x14004a62c  jmp     short loc_14004A647
0x14004a62e  mov     [rbp+arg_0], 390Ch; jumptable 000000014004A574 cases 72-77
0x14004a635  jmp     short loc_14004A647
0x14004a637  mov     [rbp+arg_0], 3921h; jumptable 000000014004A574 cases 83,84
0x14004a63e  jmp     short loc_14004A647
0x14004a640  mov     [rbp+arg_0], 3922h; jumptable 000000014004A574 cases 85,86
0x14004a647  lea     rdx, aWindowsFilteri; "Windows Filtering Platform"
0x14004a64e  lea     rcx, [rbp+DestinationString]; DestinationString
0x14004a652  call    cs:__imp_RtlInitUnicodeString
0x14004a659  nop     dword ptr [rax+rax+00h]
0x14004a65e  mov     ecx, [rbx+120h]
0x14004a664  lea     r14, WPP_GLOBAL_Control
0x14004a66b  mov     [rdi+4], ecx
0x14004a66e  mov     dword ptr [rdi], 3
0x14004a674  movzx   eax, word ptr [rbx+158h]
0x14004a67b  mov     [rdi+12h], ax
0x14004a67f  cmp     ecx, 1420h
0x14004a685  jnz     loc_14004A7BC
0x14004a68b  lea     r9, [rbx+160h]; Data
0x14004a692  xor     r8d, r8d; Index
0x14004a695  mov     edx, 0Fh; Type
0x14004a69a  mov     rcx, rdi; AuditParameters
0x14004a69d  call    cs:__imp_SeSetAuditParameter
0x14004a6a4  nop     dword ptr [rax+rax+00h]
0x14004a6a9  movsxd  rsi, eax
0x14004a6ac  test    eax, eax
0x14004a6ae  jz      short loc_14004A6F3
0x14004a6b0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a6b7  cmp     rcx, r14
0x14004a6ba  jz      short loc_14004A6EB
0x14004a6bc  cmp     byte ptr [rcx+29h], 2
0x14004a6c0  jb      short loc_14004A6EB
0x14004a6c2  test    dword ptr [rcx+2Ch], 1000h
0x14004a6c9  jz      short loc_14004A6EB
0x14004a6cb  mov     rcx, [rcx+18h]
0x14004a6cf  lea     r9, aSesetauditpara; "SeSetAuditParameter"
0x14004a6d6  mov     edx, 0Ah
0x14004a6db  mov     [rsp+70h+AuditSubcategoryId], esi
0x14004a6df  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14004a6e6  call    WPP_SF_sd
0x14004a6eb  mov     rbx, rsi
0x14004a6ee  jmp     loc_14004AE04
0x14004a6f3  lea     r9, [rbx+128h]; Data
0x14004a6fa  cmp     word ptr [r9], 0
0x14004a6ff  jz      short loc_14004A72F
0x14004a701  mov     edx, 1; Type
0x14004a706  mov     rcx, rdi; AuditParameters
0x14004a709  mov     r8d, edx; Index
0x14004a70c  call    cs:__imp_SeSetAuditParameter
0x14004a713  nop     dword ptr [rax+rax+00h]
0x14004a718  movsxd  rsi, eax
0x14004a71b  test    eax, eax
0x14004a71d  jz      loc_14004A7B7
0x14004a723  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a72a  cmp     rcx, r14
0x14004a72d  jmp     short loc_14004A772
0x14004a72f  lea     rdx, asc_140089DE4; "-"
0x14004a736  lea     rcx, [rbp+Data]; DestinationString
0x14004a73a  call    cs:__imp_RtlInitUnicodeString
0x14004a741  nop     dword ptr [rax+rax+00h]
0x14004a746  mov     edx, 1; Type
0x14004a74b  lea     r9, [rbp+Data]; Data
0x14004a74f  mov     r8d, edx; Index
0x14004a752  mov     rcx, rdi; AuditParameters
0x14004a755  call    cs:__imp_SeSetAuditParameter
0x14004a75c  nop     dword ptr [rax+rax+00h]
0x14004a761  movsxd  rsi, eax
0x14004a764  test    eax, eax
0x14004a766  jz      short loc_14004A7B7
0x14004a768  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a76f  cmp     rcx, r14
0x14004a772  jz      loc_14004A6EB
0x14004a778  cmp     byte ptr [rcx+29h], 2
0x14004a77c  jb      loc_14004A6EB
0x14004a782  test    dword ptr [rcx+2Ch], 1000h
0x14004a789  jz      loc_14004A6EB
0x14004a78f  mov     rcx, [rcx+18h]
0x14004a793  lea     r9, aSesetauditpara; "SeSetAuditParameter"
0x14004a79a  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14004a7a1  mov     [rsp+70h+AuditSubcategoryId], esi
0x14004a7a5  mov     edx, 0Ah
0x14004a7aa  call    WPP_SF_sd
0x14004a7af  mov     rbx, rsi
0x14004a7b2  jmp     loc_14004AE04
0x14004a7b7  mov     esi, 2
0x14004a7bc  lea     r9, [rbp+arg_8]; Data
0x14004a7c0  mov     r8d, esi; Index
0x14004a7c3  mov     edx, 15h; Type
0x14004a7c8  mov     rcx, rdi; AuditParameters
0x14004a7cb  call    cs:__imp_SeSetAuditParameter
0x14004a7d2  nop     dword ptr [rax+rax+00h]
0x14004a7d7  movsxd  r14, eax
0x14004a7da  test    eax, eax
0x14004a7dc  jz      short loc_14004A829
0x14004a7de  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a7e5  lea     rax, WPP_GLOBAL_Control
0x14004a7ec  cmp     rcx, rax
0x14004a7ef  jz      short loc_14004A821
0x14004a7f1  cmp     byte ptr [rcx+29h], 2
0x14004a7f5  jb      short loc_14004A821
0x14004a7f7  test    dword ptr [rcx+2Ch], 1000h
0x14004a7fe  jz      short loc_14004A821
0x14004a800  mov     rcx, [rcx+18h]
0x14004a804  lea     r9, aSesetauditpara; "SeSetAuditParameter"
0x14004a80b  mov     edx, 0Ah
0x14004a810  mov     [rsp+70h+AuditSubcategoryId], r14d
0x14004a815  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14004a81c  call    WPP_SF_sd
0x14004a821  mov     rbx, r14
0x14004a824  jmp     loc_14004ADFD
0x14004a829  cmp     [rbp+arg_8], 3900h
0x14004a830  lea     edx, [rsi+1]
0x14004a833  lea     r11d, [rdx+1]
0x14004a837  jnz     short loc_14004A846
0x14004a839  mov     eax, 88h
0x14004a83e  mov     r10d, 8
0x14004a844  jmp     short loc_14004A851
0x14004a846  mov     eax, 8
0x14004a84b  mov     r10d, 88h
0x14004a851  lea     r8, [rax+rbx]
0x14004a855  mov     rcx, rdi
0x14004a858  call    WfpSetParmTypeSockAddr
0x14004a85d  mov     edx, r11d
0x14004a860  lea     r8, [r10+rbx]
0x14004a864  mov     rcx, rdi
0x14004a867  lea     esi, [r11+1]
0x14004a86b  call    WfpSetParmTypeSockAddr
0x14004a870  mov     eax, [rdi+4]
0x14004a873  cmp     eax, 1420h
0x14004a878  jnz     short loc_14004A8B9
0x14004a87a  lea     r9, [rbx+110h]; Data
0x14004a881  mov     r8d, esi; Index
0x14004a884  mov     edx, 1Bh; Type
0x14004a889  mov     rcx, rdi; AuditParameters
0x14004a88c  call    cs:__imp_SeSetAuditParameter
0x14004a893  nop     dword ptr [rax+rax+00h]
0x14004a898  movsxd  r14, eax
0x14004a89b  test    eax, eax
0x14004a89d  jz      loc_14004AB2F
0x14004a8a3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a8aa  lea     rax, WPP_GLOBAL_Control
0x14004a8b1  cmp     rcx, rax
0x14004a8b4  jmp     loc_14004A7EF
0x14004a8b9  cmp     eax, 141Eh
0x14004a8be  jnz     loc_14004A9D7
0x14004a8c4  lea     r9, [rbx+110h]; Data
0x14004a8cb  mov     [rbp+arg_10], 0
0x14004a8d2  mov     r8d, esi; Index
0x14004a8d5  mov     edx, 0Ah; Type
0x14004a8da  mov     rcx, rdi; AuditParameters
0x14004a8dd  call    cs:__imp_SeSetAuditParameter
0x14004a8e4  nop     dword ptr [rax+rax+00h]
0x14004a8e9  movsxd  r14, eax
0x14004a8ec  test    eax, eax
0x14004a8ee  jz      short loc_14004A906
0x14004a8f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a8f7  lea     rax, WPP_GLOBAL_Control
0x14004a8fe  cmp     rcx, rax
0x14004a901  jmp     loc_14004A7EF
0x14004a906  mov     eax, [rbx+19Ch]
0x14004a90c  lea     r14d, [rsi+1]
0x14004a910  mov     r8d, r14d; Index
0x14004a913  mov     [rbp+arg_10], eax
0x14004a916  lea     r9, [rbp+arg_10]; Data
0x14004a91a  mov     edx, 1Bh; Type
0x14004a91f  mov     rcx, rdi; AuditParameters
0x14004a922  call    cs:__imp_SeSetAuditParameter
0x14004a929  nop     dword ptr [rax+rax+00h]
0x14004a92e  movsxd  rsi, eax
0x14004a931  test    eax, eax
0x14004a933  jz      short loc_14004A94B
0x14004a935  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a93c  lea     r14, WPP_GLOBAL_Control
0x14004a943  cmp     rcx, r14
0x14004a946  jmp     loc_14004A6BA
0x14004a94b  mov     eax, [rbx+194h]
0x14004a951  lea     r9, [rbp+arg_10]; Data
0x14004a955  lea     r8d, [r14+1]; Index
0x14004a959  mov     [rbp+arg_10], eax
0x14004a95c  mov     edx, 1Bh; Type
0x14004a961  mov     rcx, rdi; AuditParameters
0x14004a964  call    cs:__imp_SeSetAuditParameter
0x14004a96b  nop     dword ptr [rax+rax+00h]
0x14004a970  movsxd  rsi, eax
0x14004a973  test    eax, eax
0x14004a975  jz      short loc_14004A98D
0x14004a977  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a97e  lea     r14, WPP_GLOBAL_Control
0x14004a985  cmp     rcx, r14
0x14004a988  jmp     loc_14004A6BA
0x14004a98d  movzx   eax, word ptr [rbx+198h]
0x14004a994  lea     esi, [r14+2]
0x14004a998  mov     r8d, esi; Index
0x14004a99b  mov     [rbp+arg_10], eax
0x14004a99e  lea     r9, [rbp+arg_10]; Data
0x14004a9a2  mov     edx, 0Ah; Type
0x14004a9a7  mov     rcx, rdi; AuditParameters
0x14004a9aa  call    cs:__imp_SeSetAuditParameter
0x14004a9b1  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
