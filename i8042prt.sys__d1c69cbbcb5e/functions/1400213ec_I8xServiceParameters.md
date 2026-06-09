# I8xServiceParameters

- ea: `0x1400213ec`
- end: `0x1400219d1`
- name: `I8xServiceParameters`
- size: `1509`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140021078`

## callees

- `0x1400014e0`
- `0x1400043e0`
- `0x140004530`
- `0x140007b10`
- `0x14000daa0`
- `0x1400213ec`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400214ab`
- `ntoskrnl!ExAllocatePool2` at `0x1400214ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400219a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400219a9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021672`
- `ntoskrnl!RtlInitUnicodeString` at `0x140021672`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140021473`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140021473`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400216a1`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140021682`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x140021682`
- `ntoskrnl!ZwClose` at `0x140021993`
- `ntoskrnl!ZwClose` at `0x140021993`

## string_xrefs

- `0x14002164b`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
void __fastcall I8xServiceParameters(__int64 a1)
{
  __int64 v1; // rdi
  void *v2; // rsi
  int v3; // edx
  int v4; // ebx
  __int64 v5; // r9
  __int64 Pool2; // rax
  HANDLE v7; // rbx
  PVOID SystemRoutineAddress; // rax
  int v9; // eax
  int v10; // eax
  int v11; // r9d
  int v12; // r9d
  int v13; // r9d
  int v14; // edx
  const char *v15; // rcx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // [rsp+30h] [rbp-50h] BYREF
  int v21; // [rsp+34h] [rbp-4Ch] BYREF
  int v22; // [rsp+38h] [rbp-48h] BYREF
  int v23; // [rsp+3Ch] [rbp-44h] BYREF
  int v24; // [rsp+40h] [rbp-40h] BYREF
  int v25; // [rsp+44h] [rbp-3Ch] BYREF
  int v26; // [rsp+48h] [rbp-38h] BYREF
  int v27; // [rsp+4Ch] [rbp-34h] BYREF
  int v28; // [rsp+50h] [rbp-30h] BYREF
  int v29; // [rsp+54h] [rbp-2Ch] BYREF
  int v30; // [rsp+58h] [rbp-28h] BYREF
  HANDLE Handle; // [rsp+60h] [rbp-20h]
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-18h] BYREF
  __int16 v33; // [rsp+C8h] [rbp+48h] BYREF
  __int16 v34; // [rsp+D0h] [rbp+50h] BYREF
  __int16 v35; // [rsp+D8h] [rbp+58h] BYREF

  v1 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  Handle = 0;
  v34 = 12000;
  v35 = 12000;
  v2 = 0;
  v29 = 0;
  v28 = 1;
  v33 = 3;
  v20 = 1;
  v25 = 1;
  v30 = 0;
  v22 = 0;
  v23 = 0;
  v21 = 0;
  v26 = 0;
  v27 = 0;
  v24 = 0;
  *(_WORD *)(*(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 78LL) = 50;
  *(_BYTE *)(v1 + 81) = 0;
  v4 = IoOpenDriverRegistryKey(a1, 0, 1, 0);
  if ( v4 >= 0 )
  {
    Pool2 = ExAllocatePool2(256, 504, 842281016, v5);
    v2 = (void *)Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)(Pool2 + 48) = 2;
      *(_DWORD *)(Pool2 + 8) = 288;
      *(_DWORD *)(Pool2 + 32) = 67108868;
      *(_QWORD *)(Pool2 + 16) = L"ResendIterations";
      *(_QWORD *)(Pool2 + 24) = &v21;
      *(_QWORD *)(Pool2 + 40) = &v33;
      *(_QWORD *)(Pool2 + 72) = L"PollingIterations";
      *(_QWORD *)(Pool2 + 80) = &v22;
      *(_QWORD *)(Pool2 + 96) = &v34;
      *(_DWORD *)(Pool2 + 88) = 67108868;
      *(_DWORD *)(Pool2 + 64) = 288;
      *(_DWORD *)(Pool2 + 104) = 2;
      *(_QWORD *)(Pool2 + 128) = L"PollingTerationsMaximum";
      *(_QWORD *)(Pool2 + 136) = &v23;
      *(_QWORD *)(Pool2 + 152) = &v35;
      *(_DWORD *)(Pool2 + 144) = 67108868;
      *(_DWORD *)(Pool2 + 120) = 288;
      *(_DWORD *)(Pool2 + 160) = 2;
      *(_QWORD *)(Pool2 + 184) = L"BreakOnSysRq";
      *(_QWORD *)(Pool2 + 192) = &v25;
      *(_QWORD *)(Pool2 + 208) = &v28;
      *(_DWORD *)(Pool2 + 200) = 67108868;
      *(_DWORD *)(Pool2 + 216) = 4;
      *(_DWORD *)(Pool2 + 176) = 288;
      *(_QWORD *)(Pool2 + 240) = L"Headless";
      *(_QWORD *)(Pool2 + 248) = &v26;
      *(_QWORD *)(Pool2 + 264) = &v29;
      *(_DWORD *)(Pool2 + 256) = 67108868;
      *(_DWORD *)(Pool2 + 272) = 4;
      *(_DWORD *)(Pool2 + 232) = 288;
      *(_QWORD *)(Pool2 + 296) = L"ReportResetErrors";
      *(_QWORD *)(Pool2 + 304) = &v27;
      *(_QWORD *)(Pool2 + 320) = &v30;
      *(_DWORD *)(Pool2 + 312) = 67108868;
      *(_DWORD *)(Pool2 + 328) = 4;
      *(_DWORD *)(Pool2 + 288) = 288;
      *(_QWORD *)(Pool2 + 352) = L"AsyncStart";
      *(_QWORD *)(Pool2 + 360) = &v24;
      *(_DWORD *)(Pool2 + 368) = 67108868;
      *(_DWORD *)(Pool2 + 384) = 4;
      *(_QWORD *)(Pool2 + 376) = &v20;
      *(_DWORD *)(Pool2 + 344) = 288;
      v7 = Handle;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
      SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
      if ( !SystemRoutineAddress )
        SystemRoutineAddress = RtlQueryRegistryValues;
      v9 = ((__int64 (__fastcall *)(__int64, HANDLE, void *, _QWORD, _QWORD))SystemRoutineAddress)(
             3221225472LL,
             v7,
             v2,
             0,
             0);
      v4 = v9;
      if ( v9 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v3,
          16,
          75,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
          v9);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          v3,
          17,
          74,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
      v4 = -1073741823;
    }
  }
  if ( v4 < 0 )
  {
    *(_WORD *)(v1 + 70) = v33;
    *(_WORD *)(v1 + 72) = v34;
    *(_WORD *)(v1 + 74) = v35;
    LODWORD(WPP_MAIN_CB.Dpc.DeferredRoutine) = v20;
    goto LABEL_33;
  }
  *(_WORD *)(v1 + 70) = v21;
  *(_WORD *)(v1 + 72) = v22;
  *(_WORD *)(v1 + 74) = v23;
  v10 = v24;
  if ( v24 >= 2 )
    v10 = v20;
  LODWORD(WPP_MAIN_CB.Dpc.DeferredRoutine) = v10;
  if ( v25 )
  {
    BYTE5(WPP_MAIN_CB.Dpc.DeferredRoutine) = 1;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_21;
    v11 = 76;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_21;
    v11 = 77;
  }
  WPP_RECORDER_SF_(
    WPP_GLOBAL_Control->DeviceExtension,
    v3,
    14,
    v11,
    (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
LABEL_21:
  if ( v26 )
  {
    BYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = 78;
LABEL_26:
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v3,
        14,
        v12,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
    }
  }
  else
  {
    BYTE6(WPP_MAIN_CB.Dpc.DeferredRoutine) = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = 79;
      goto LABEL_26;
    }
  }
  if ( v27 )
  {
    HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) = 1;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_43;
    v13 = 80;
  }
  else
  {
    HIBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) = 0;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_43;
    v13 = 81;
  }
  WPP_RECORDER_SF_(
    WPP_GLOBAL_Control->DeviceExtension,
    v3,
    14,
    v13,
    (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
LABEL_33:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v3,
      14,
      82,
      (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        14,
        83,
        (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
        (char)WPP_MAIN_CB.Dpc.DeferredRoutine);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v15 = File;
        if ( !*(_BYTE *)(v1 + 81) )
          v15 = "not";
        WPP_RECORDER_SF_s(
          WPP_GLOBAL_Control->DeviceExtension,
          (unsigned int)"not",
          14,
          84,
          (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
          (__int64)v15);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_SF_d(
            WPP_GLOBAL_Control->DeviceExtension,
            v16,
            14,
            85,
            (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
            *(_WORD *)(v1 + 78));
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v17,
              14,
              86,
              (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
              *(_WORD *)(v1 + 70));
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              WPP_RECORDER_SF_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v18,
                14,
                87,
                (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
                *(_WORD *)(v1 + 72));
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                WPP_RECORDER_SF_d(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v19,
                  14,
                  88,
                  (__int64)WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids,
                  *(_WORD *)(v1 + 74));
            }
          }
        }
      }
    }
  }
LABEL_43:
  if ( Handle )
    ZwClose(Handle);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
}

```

## disassembly

```asm
0x1400213ec  mov     [rsp-38h+arg_0], rbx
0x1400213f1  push    rbp
0x1400213f2  push    rsi
0x1400213f3  push    rdi
0x1400213f4  push    r12
0x1400213f6  push    r13
0x1400213f8  push    r14
0x1400213fa  push    r15
0x1400213fc  mov     rbp, rsp
0x1400213ff  sub     rsp, 80h
0x140021406  mov     rdi, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x14002140d  xor     r14d, r14d
0x140021410  mov     eax, 2EE0h
0x140021415  mov     [rbp+Handle], r14
0x140021419  mov     [rbp+arg_10], ax
0x14002141d  xor     r9d, r9d
0x140021420  mov     [rbp+arg_18], ax
0x140021424  mov     esi, r14d
0x140021427  lea     edx, [r14+1]
0x14002142b  mov     [rbp+var_2C], r14d
0x14002142f  lea     eax, [rdx+2]
0x140021432  mov     [rbp+var_30], edx
0x140021435  mov     [rbp+arg_8], ax
0x140021439  mov     r8d, edx
0x14002143c  mov     [rbp+var_50], edx
0x14002143f  lea     rax, [rbp+Handle]
0x140021443  mov     [rbp+var_3C], edx
0x140021446  xor     edx, edx
0x140021448  mov     [rbp+var_28], r14d
0x14002144c  mov     [rbp+var_48], r14d
0x140021450  mov     [rbp+var_44], r14d
0x140021454  mov     [rbp+var_4C], r14d
0x140021458  mov     [rbp+var_38], r14d
0x14002145c  mov     [rbp+var_34], r14d
0x140021460  mov     [rbp+var_40], r14d
0x140021464  mov     [rsp+80h+var_60], rax
0x140021469  mov     word ptr [rdi+4Eh], 32h ; '2'
0x14002146f  mov     [rdi+51h], r14b
0x140021473  call    cs:__imp_IoOpenDriverRegistryKey
0x14002147a  nop     dword ptr [rax+rax+00h]
0x14002147f  lea     r12, WPP_302e7ed89cfa3d9fb97f1e0f79e25f62_Traceguids
0x140021486  mov     ebx, eax
0x140021488  lea     r15, WPP_RECORDER_INITIALIZED
0x14002148f  lea     r13d, [r14+2]
0x140021493  test    eax, eax
0x140021495  js      loc_1400216E3
0x14002149b  mov     edx, 1F8h
0x1400214a0  mov     ecx, 100h
0x1400214a5  mov     r8d, 32343038h
0x1400214ab  call    cs:__imp_ExAllocatePool2
0x1400214b2  nop     dword ptr [rax+rax+00h]
0x1400214b7  mov     rsi, rax
0x1400214ba  test    rax, rax
0x1400214bd  jnz     short loc_1400214EF
0x1400214bf  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400214c6  jz      short loc_1400214E5
0x1400214c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400214cf  lea     r9d, [r14+4Ah]
0x1400214d3  lea     r8d, [r14+11h]
0x1400214d7  mov     [rsp+80h+var_60], r12
0x1400214dc  mov     rcx, [rcx+40h]
0x1400214e0  call    WPP_RECORDER_SF_
0x1400214e5  mov     ebx, 0C0000001h
0x1400214ea  jmp     loc_1400216E3
0x1400214ef  mov     [rsi+30h], r13d
0x1400214f3  mov     r8d, 120h
0x1400214f9  mov     [rax+8], r8d
0x1400214fd  mov     edx, 4000004h
0x140021502  mov     [rsi+20h], edx
0x140021505  lea     rax, aResenditeratio; "ResendIterations"
0x14002150c  mov     [rsi+10h], rax
0x140021510  mov     ecx, 4
0x140021515  lea     rax, [rbp+var_4C]
0x140021519  xorps   xmm0, xmm0
0x14002151c  mov     [rsi+18h], rax
0x140021520  lea     rax, [rbp+arg_8]
0x140021524  mov     [rsi+28h], rax
0x140021528  lea     rax, aPollingiterati; "PollingIterations"
0x14002152f  mov     [rsi+48h], rax
0x140021533  lea     rax, [rbp+var_48]
0x140021537  mov     [rsi+50h], rax
0x14002153b  lea     rax, [rbp+arg_10]
0x14002153f  mov     [rsi+60h], rax
0x140021543  lea     rax, aPollingteratio; "PollingTerationsMaximum"
0x14002154a  mov     [rsi+58h], edx
0x14002154d  mov     [rsi+40h], r8d
0x140021551  mov     [rsi+68h], r13d
0x140021555  mov     [rsi+80h], rax
0x14002155c  lea     rax, [rbp+var_44]
0x140021560  mov     [rsi+88h], rax
0x140021567  lea     rax, [rbp+arg_18]
0x14002156b  mov     [rsi+98h], rax
0x140021572  lea     rax, aBreakonsysrq; "BreakOnSysRq"
0x140021579  mov     [rsi+90h], edx
0x14002157f  mov     [rsi+78h], r8d
0x140021583  mov     [rsi+0A0h], r13d
0x14002158a  mov     [rsi+0B8h], rax
0x140021591  lea     rax, [rbp+var_3C]
0x140021595  mov     [rsi+0C0h], rax
0x14002159c  lea     rax, [rbp+var_30]
0x1400215a0  mov     [rsi+0D0h], rax
0x1400215a7  lea     rax, aHeadless; "Headless"
0x1400215ae  mov     [rsi+0C8h], edx
0x1400215b4  mov     [rsi+0D8h], ecx
0x1400215ba  mov     [rsi+0B0h], r8d
0x1400215c1  mov     [rsi+0F0h], rax
0x1400215c8  lea     rax, [rbp+var_38]
0x1400215cc  mov     [rsi+0F8h], rax
0x1400215d3  lea     rax, [rbp+var_2C]
0x1400215d7  mov     [rsi+108h], rax
0x1400215de  lea     rax, aReportreseterr; "ReportResetErrors"
0x1400215e5  mov     [rsi+100h], edx
0x1400215eb  mov     [rsi+110h], ecx
0x1400215f1  mov     [rsi+0E8h], r8d
0x1400215f8  mov     [rsi+128h], rax
0x1400215ff  lea     rax, [rbp+var_34]
0x140021603  mov     [rsi+130h], rax
0x14002160a  lea     rax, [rbp+var_28]
0x14002160e  mov     [rsi+140h], rax
0x140021615  lea     rax, aAsyncstart; "AsyncStart"
0x14002161c  mov     [rsi+138h], edx
0x140021622  mov     [rsi+148h], ecx
0x140021628  mov     [rsi+120h], r8d
0x14002162f  mov     [rsi+160h], rax
0x140021636  lea     rax, [rbp+var_40]
0x14002163a  mov     [rsi+168h], rax
0x140021641  lea     rax, [rbp+var_50]
0x140021645  mov     [rsi+170h], edx
0x14002164b  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140021652  mov     [rsi+180h], ecx
0x140021658  lea     rcx, [rbp+DestinationString]; DestinationString
0x14002165c  mov     [rsi+178h], rax
0x140021663  mov     [rsi+158h], r8d
0x14002166a  mov     rbx, [rbp+Handle]
0x14002166e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140021672  call    cs:__imp_RtlInitUnicodeString
0x140021679  nop     dword ptr [rax+rax+00h]
0x14002167e  lea     rcx, [rbp+DestinationString]; SystemRoutineName
0x140021682  call    cs:__imp_MmGetSystemRoutineAddress
0x140021689  nop     dword ptr [rax+rax+00h]
0x14002168e  mov     [rsp+80h+var_60], r14
0x140021693  mov     r8, rsi
0x140021696  test    rax, rax
0x140021699  mov     rdx, rbx
0x14002169c  mov     ecx, 0C0000000h
0x1400216a1  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400216a9  xor     r9d, r9d
0x1400216ac  call    _guard_dispatch_icall
0x1400216b1  mov     ebx, eax
0x1400216b3  test    eax, eax
0x1400216b5  jns     short loc_1400216E3
0x1400216b7  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400216be  jz      short loc_1400216E3
0x1400216c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400216c7  mov     r9d, 4Bh ; 'K'
0x1400216cd  mov     dword ptr [rsp+80h+var_58], eax
0x1400216d1  mov     [rsp+80h+var_60], r12
0x1400216d6  mov     rcx, [rcx+40h]
0x1400216da  lea     r8d, [r9-3Bh]
0x1400216de  call    WPP_RECORDER_SF_D
0x1400216e3  mov     r13d, 0Eh
0x1400216e9  test    ebx, ebx
0x1400216eb  jns     short loc_140021713
0x1400216ed  movzx   eax, [rbp+arg_8]
0x1400216f1  mov     [rdi+46h], ax
0x1400216f5  movzx   eax, [rbp+arg_10]
0x1400216f9  mov     [rdi+48h], ax
0x1400216fd  movzx   eax, [rbp+arg_18]
0x140021701  mov     [rdi+4Ah], ax
0x140021705  mov     eax, [rbp+var_50]
0x140021708  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, eax
0x14002170e  jmp     loc_140021820
0x140021713  movzx   eax, word ptr [rbp+var_4C]
0x140021717  mov     [rdi+46h], ax
0x14002171b  movzx   eax, word ptr [rbp+var_48]
0x14002171f  mov     [rdi+48h], ax
0x140021723  movzx   eax, word ptr [rbp+var_44]
0x140021727  mov     [rdi+4Ah], ax
0x14002172b  mov     eax, [rbp+var_40]
0x14002172e  cmp     eax, 2
0x140021731  cmovge  eax, [rbp+var_50]
0x140021735  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, eax
0x14002173b  cmp     [rbp+var_3C], r14d
0x14002173f  jz      short loc_140021759
0x140021741  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+5, 1
0x140021748  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14002174f  jz      short loc_140021780
0x140021751  mov     r9d, 4Ch ; 'L'
0x140021757  jmp     short loc_140021768
0x140021759  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140021760  jz      short loc_140021780
0x140021762  mov     r9d, 4Dh ; 'M'
0x140021768  mov     rcx, cs:WPP_GLOBAL_Control
0x14002176f  mov     r8d, r13d
0x140021772  mov     [rsp+80h+var_60], r12
0x140021777  mov     rcx, [rcx+40h]
0x14002177b  call    WPP_RECORDER_SF_
0x140021780  cmp     [rbp+var_38], r14d
0x140021784  jz      short loc_14002179E
0x140021786  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+6, 1
0x14002178d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140021794  jz      short loc_1400217CC
0x140021796  mov     r9d, 4Eh ; 'N'
0x14002179c  jmp     short loc_1400217B4
0x14002179e  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+6, r14b
0x1400217a5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400217ac  jz      short loc_1400217CC
0x1400217ae  mov     r9d, 4Fh ; 'O'
0x1400217b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400217bb  mov     r8d, r13d
0x1400217be  mov     [rsp+80h+var_60], r12
0x1400217c3  mov     rcx, [rcx+40h]
0x1400217c7  call    WPP_RECORDER_SF_
0x1400217cc  cmp     [rbp+var_34], r14d
0x1400217d0  jz      short loc_1400217EE
0x1400217d2  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+7, 1
0x1400217d9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400217e0  jz      loc_14002198A
0x1400217e6  mov     r9d, 50h ; 'P'
0x1400217ec  jmp     short loc_140021808
0x1400217ee  mov     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+7, r14b
0x1400217f5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400217fc  jz      loc_14002198A
0x140021802  mov     r9d, 51h ; 'Q'
0x140021808  mov     rcx, cs:WPP_GLOBAL_Control
0x14002180f  mov     r8d, r13d
0x140021812  mov     [rsp+80h+var_60], r12
0x140021817  mov     rcx, [rcx+40h]
0x14002181b  call    WPP_RECORDER_SF_
0x140021820  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140021827  jz      loc_14002198A
0x14002182d  mov     rcx, cs:WPP_GLOBAL_Control
0x140021834  mov     r9d, 52h ; 'R'
0x14002183a  mov     r8d, r13d
0x14002183d  mov     [rsp+80h+var_60], r12
0x140021842  mov     rcx, [rcx+40h]
0x140021846  call    WPP_RECORDER_SF_
0x14002184b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140021852  jz      loc_14002198A
0x140021858  mov     rcx, cs:WPP_GLOBAL_Control
0x14002185f  mov     r9d, 53h ; 'S'
0x140021865  mov     eax, dword ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x14002186b  mov     r8d, r13d
0x14002186e  mov     dword ptr [rsp+80h+var_58], eax
0x140021872  mov     [rsp+80h+var_60], r12
0x140021877  mov     rcx, [rcx+40h]
0x14002187b  call    WPP_RECORDER_SF_d
0x140021880  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140021887  jz      loc_14002198A
0x14002188d  cmp     [rdi+51h], r14b
0x140021891  lea     rdx, aNot; "not"
0x140021898  lea     rcx, File
0x14002189f  mov     r9d, 54h ; 'T'
0x1400218a5  cmovz   rcx, rdx
0x1400218a9  mov     r8d, r13d
0x1400218ac  mov     [rsp+80h+var_58], rcx
0x1400218b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400218b8  mov     [rsp+80h+var_60], r12
0x1400218bd  mov     rcx, [rcx+40h]
0x1400218c1  call    WPP_RECORDER_SF_s
0x1400218c6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400218cd  jz      loc_14002198A
0x1400218d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400218da  mov     r9d, 55h ; 'U'
0x1400218e0  movzx   eax, word ptr [rdi+4Eh]
0x1400218e4  mov     r8d, r13d
0x1400218e7  mov     dword ptr [rsp+80h+var_58], eax
0x1400218eb  mov     [rsp+80h+var_60], r12
0x1400218f0  mov     rcx, [rcx+40h]
0x1400218f4  call    WPP_RECORDER_SF_d
0x1400218f9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140021900  jz      loc_14002198A
0x140021906  mov     rcx, cs:WPP_GLOBAL_Control
0x14002190d  mov     r9d, 56h ; 'V'
0x140021913  movzx   eax, word ptr [rdi+46h]
0x140021917  mov     r8d, r13d
0x14002191a  mov     dword ptr [rsp+80h+var_58], eax
0x14002191e  mov     [rsp+80h+var_60], r12
0x140021923  mov     rcx, [rcx+40h]
0x140021927  call    WPP_RECORDER_SF_d
0x14002192c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140021933  jz      short loc_14002198A
0x140021935  mov     rcx, cs:WPP_GLOBAL_Control
0x14002193c  mov     r9d, 57h ; 'W'
0x140021942  movzx   eax, word ptr [rdi+48h]
0x140021946  mov     r8d, r13d
0x140021949  mov     dword ptr [rsp+80h+var_58], eax
0x14002194d  mov     [rsp+80h+var_60], r12
0x140021952  mov     rcx, [rcx+40h]
0x140021956  call    WPP_RECORDER_SF_d
0x14002195b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140021962  jz      short loc_14002198A
0x140021964  mov     rcx, cs:WPP_GLOBAL_Control
0x14002196b  mov     r9d, 58h ; 'X'
0x140021971  movzx   eax, word ptr [rdi+4Ah]
0x140021975  mov     r8d, r13d
0x140021978  mov     dword ptr [rsp+80h+var_58], eax
0x14002197c  mov     [rsp+80h+var_60], r12
0x140021981  mov     rcx, [rcx+40h]
0x140021985  call    WPP_RECORDER_SF_d
  ... truncated ...
```
