# HbEvtpLogProcessorFeatures

- ea: `0x14001274c`
- end: `0x1400129ed`
- name: `HbEvtpLogProcessorFeatures`
- size: `673`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000ecd0`
- `0x1400115a0`

## callees

- `0x140001600`
- `0x1400022b4`
- `0x140002ae0`
- `0x14001274c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140012820`
- `ntoskrnl!ExAllocatePool2` at `0x140012820`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001298e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001298e`
- `winhvr!WinHvGetPartitionProperty` at `0x1400127a3`
- `winhvr!WinHvGetPartitionProperty` at `0x1400128c9`
- `winhvr!WinHvGetPartitionProperty` at `0x140012901`
- `winhvr!WinHvGetPartitionProperty` at `0x14001292b`
- `winhvr!WinHvGetPartitionProperty` at `0x1400127a3`
- `winhvr!WinHvGetPartitionProperty` at `0x1400128c9`
- `winhvr!WinHvGetPartitionProperty` at `0x140012901`
- `winhvr!WinHvGetPartitionProperty` at `0x14001292b`
- `winhvr!WinHvGetPartitionPropertyEx` at `0x140012867`
- `winhvr!WinHvGetPartitionPropertyEx` at `0x140012867`

## pseudocode

```c
__int64 __fastcall HbEvtpLogProcessorFeatures(char a1)
{
  int PartitionProperty; // eax
  int v3; // ebx
  __int64 Pool2; // rax
  unsigned __int8 *v5; // rsi
  unsigned __int16 i; // dx
  __int64 v7; // rcx
  unsigned __int8 v8; // di
  __int64 v9; // rcx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  __int64 *v13; // rdx
  __int64 v15; // [rsp+40h] [rbp-19h] BYREF
  __int64 v16; // [rsp+48h] [rbp-11h] BYREF
  __int64 v17; // [rsp+50h] [rbp-9h] BYREF
  __int64 v18; // [rsp+58h] [rbp-1h] BYREF
  __int128 v19; // [rsp+60h] [rbp+7h] BYREF
  __int64 v20; // [rsp+70h] [rbp+17h]

  v16 = 0;
  v20 = 0;
  v18 = 0;
  v17 = 0;
  v15 = 0;
  v19 = 0;
  PartitionProperty = WinHvGetPartitionProperty(-1, 393237, &v15);
  v3 = PartitionProperty;
  if ( PartitionProperty >= 0 )
  {
    if ( !(_BYTE)v15 )
    {
      HbpTraceEvent(
        0,
        "HbEvtpLogProcessorFeatures",
        4573,
        "%s",
        "HbEvtpLogProcessorFeatures: No processor feature banks available");
      return HbpTraceEvent(
               1,
               "HbEvtpLogProcessorFeatures",
               4700,
               "HbEvtpLogProcessorFeatures: Processor Feature bank: %d, Synthetic Proc Feature Bank: %d, status: 0x%x",
               (unsigned __int8)v15,
               BYTE1(v15),
               v3);
    }
    Pool2 = ExAllocatePool2(256, 4072, 1967284808);
    v5 = (unsigned __int8 *)Pool2;
    if ( !Pool2 )
    {
      v3 = -1073741670;
      HbpTraceEvent(0, "HbEvtpLogProcessorFeatures", 4584, "HbEvtpLogProcessorFeatures: Failed to allocate propertyEx");
      return HbpTraceEvent(
               1,
               "HbEvtpLogProcessorFeatures",
               4700,
               "HbEvtpLogProcessorFeatures: Processor Feature bank: %d, Synthetic Proc Feature Bank: %d, status: 0x%x",
               (unsigned __int8)v15,
               BYTE1(v15),
               v3);
    }
    if ( (int)WinHvGetPartitionPropertyEx(-1, 589840, 0, Pool2) < 0 )
    {
      HbpTraceEvent(
        2,
        "HbEvtpLogProcessorFeatures",
        4619,
        "Running on a downlevel that hypervisor does not support the extended processor feature property, fallback to legacy property");
      v8 = 0;
      while ( 1 )
      {
        v3 = WinHvGetPartitionProperty(-1, (unsigned int)v8 + 393226, &v18);
        if ( v3 < 0 )
          goto LABEL_22;
        v9 = v8++;
        *((_QWORD *)&v19 + v9) = v18;
        if ( v8 >= 2u )
          goto LABEL_14;
      }
    }
    for ( i = 0; i < *v5; *((_QWORD *)&v19 + v7) = *(_QWORD *)&v5[8 * v7 + 8] )
      v7 = i++;
LABEL_14:
    v3 = WinHvGetPartitionProperty(-1, 393219, &v16);
    if ( v3 >= 0 )
    {
      v16 *= 8;
      v3 = WinHvGetPartitionProperty(-1, 393218, &v17);
      if ( v3 >= 0 )
      {
        if ( a1 )
        {
          if ( (byte_140009539 & 2) != 0 )
          {
            v13 = HV_EVENTLOG_RUNTIME_HOST_PROCESSOR_FEATURES_V1;
            goto LABEL_21;
          }
        }
        else if ( (Microsoft_Windows_Hyper_V_HypervisorEnableBits & 0x40) != 0 )
        {
          v13 = HV_EVENTLOG_HOST_PROCESSOR_FEATURES_V1;
LABEL_21:
          LOBYTE(v12) = v15;
          McTemplateK0uIR0iq_EtwWriteTransfer(v10, (_DWORD)v13, v11, v12, (__int64)&v19, v17, v16);
        }
      }
    }
LABEL_22:
    ExFreePoolWithTag(v5, 0x75426248u);
    return HbpTraceEvent(
             1,
             "HbEvtpLogProcessorFeatures",
             4700,
             "HbEvtpLogProcessorFeatures: Processor Feature bank: %d, Synthetic Proc Feature Bank: %d, status: 0x%x",
             (unsigned __int8)v15,
             BYTE1(v15),
             v3);
  }
  HbpTraceEvent(
    0,
    "HbEvtpLogProcessorFeatures",
    4567,
    "HbEvtpLogProcessorFeatures: Failed to get feature bank count, status 0x%x",
    PartitionProperty);
  return HbpTraceEvent(
           1,
           "HbEvtpLogProcessorFeatures",
           4700,
           "HbEvtpLogProcessorFeatures: Processor Feature bank: %d, Synthetic Proc Feature Bank: %d, status: 0x%x",
           (unsigned __int8)v15,
           BYTE1(v15),
           v3);
}

```

## disassembly

```asm
0x14001274c  push    rbp
0x14001274e  push    rbx
0x14001274f  push    rsi
0x140012750  push    rdi
0x140012751  push    r12
0x140012753  push    r14
0x140012755  lea     rbp, [rsp-2Fh]
0x14001275a  sub     rsp, 88h
0x140012761  mov     rax, cs:__security_cookie
0x140012768  xor     rax, rsp
0x14001276b  mov     [rbp+57h+var_38], rax
0x14001276f  xor     eax, eax
0x140012771  mov     [rbp+57h+var_68], 0
0x140012779  mov     r14b, cl
0x14001277c  mov     [rbp+57h+var_40], rax
0x140012780  xorps   xmm0, xmm0
0x140012783  mov     [rbp+57h+var_58], rax
0x140012787  or      r12, 0FFFFFFFFFFFFFFFFh
0x14001278b  mov     [rbp+57h+var_60], rax
0x14001278f  mov     rcx, r12
0x140012792  mov     [rbp+57h+var_70], rax
0x140012796  lea     r8, [rbp+57h+var_70]
0x14001279a  mov     edx, 60015h
0x14001279f  movups  [rbp+57h+var_50], xmm0
0x1400127a3  call    cs:__imp_WinHvGetPartitionProperty
0x1400127aa  nop     dword ptr [rax+rax+00h]
0x1400127af  lea     edi, [r12+2]
0x1400127b4  mov     ebx, eax
0x1400127b6  test    eax, eax
0x1400127b8  jns     short loc_1400127DE
0x1400127ba  lea     r9, aHbevtplogproce_0; "HbEvtpLogProcessorFeatures: Failed to g"...
0x1400127c1  mov     dword ptr [rsp+0B0h+var_90], eax
0x1400127c5  mov     r8d, 11D7h
0x1400127cb  lea     rdx, aHbevtplogproce_2; "HbEvtpLogProcessorFeatures"
0x1400127d2  xor     ecx, ecx
0x1400127d4  call    HbpTraceEvent
0x1400127d9  jmp     loc_14001299F
0x1400127de  cmp     byte ptr [rbp+57h+var_70], 0
0x1400127e2  jnz     short loc_140012810
0x1400127e4  lea     rax, aHbevtplogproce; "HbEvtpLogProcessorFeatures: No processo"...
0x1400127eb  mov     r8d, 11DDh
0x1400127f1  lea     r9, aS; "%s"
0x1400127f8  mov     [rsp+0B0h+var_90], rax
0x1400127fd  lea     rdx, aHbevtplogproce_2; "HbEvtpLogProcessorFeatures"
0x140012804  xor     ecx, ecx
0x140012806  call    HbpTraceEvent
0x14001280b  jmp     loc_14001299F
0x140012810  mov     edx, 0FE8h
0x140012815  mov     ecx, 100h
0x14001281a  mov     r8d, 75426248h
0x140012820  call    cs:__imp_ExAllocatePool2
0x140012827  nop     dword ptr [rax+rax+00h]
0x14001282c  mov     rsi, rax
0x14001282f  test    rax, rax
0x140012832  jnz     short loc_140012859
0x140012834  mov     ebx, 0C000009Ah
0x140012839  lea     r9, aHbevtplogproce_1; "HbEvtpLogProcessorFeatures: Failed to a"...
0x140012840  mov     r8d, 11E8h
0x140012846  lea     rdx, aHbevtplogproce_2; "HbEvtpLogProcessorFeatures"
0x14001284d  xor     ecx, ecx
0x14001284f  call    HbpTraceEvent
0x140012854  jmp     loc_14001299F
0x140012859  mov     r9, rsi
0x14001285c  xor     r8d, r8d
0x14001285f  mov     edx, 90010h
0x140012864  mov     rcx, r12
0x140012867  call    cs:__imp_WinHvGetPartitionPropertyEx
0x14001286e  nop     dword ptr [rax+rax+00h]
0x140012873  test    eax, eax
0x140012875  js      short loc_140012897
0x140012877  xor     edx, edx
0x140012879  cmp     [rsi], dl
0x14001287b  jbe     short loc_1400128F5
0x14001287d  movzx   ecx, dx
0x140012880  add     dx, di
0x140012883  mov     rax, [rsi+rcx*8+8]
0x140012888  mov     qword ptr [rbp+rcx*8+57h+var_50], rax
0x14001288d  movzx   eax, byte ptr [rsi]
0x140012890  cmp     dx, ax
0x140012893  jb      short loc_14001287D
0x140012895  jmp     short loc_1400128F5
0x140012897  lea     r9, aRunningOnADown; "Running on a downlevel that hypervisor "...
0x14001289e  mov     r8d, 120Bh
0x1400128a4  lea     rdx, aHbevtplogproce_2; "HbEvtpLogProcessorFeatures"
0x1400128ab  mov     ecx, 2
0x1400128b0  call    HbpTraceEvent
0x1400128b5  xor     dil, dil
0x1400128b8  movzx   edx, dil
0x1400128bc  lea     r8, [rbp+57h+var_58]
0x1400128c0  add     edx, 6000Ah
0x1400128c6  mov     rcx, r12
0x1400128c9  call    cs:__imp_WinHvGetPartitionProperty
0x1400128d0  nop     dword ptr [rax+rax+00h]
0x1400128d5  mov     ebx, eax
0x1400128d7  test    eax, eax
0x1400128d9  js      loc_140012986
0x1400128df  mov     rax, [rbp+57h+var_58]
0x1400128e3  movzx   ecx, dil
0x1400128e7  inc     dil
0x1400128ea  mov     qword ptr [rbp+rcx*8+57h+var_50], rax
0x1400128ef  cmp     dil, 2
0x1400128f3  jb      short loc_1400128B8
0x1400128f5  lea     r8, [rbp+57h+var_68]
0x1400128f9  mov     edx, 60003h
0x1400128fe  mov     rcx, r12
0x140012901  call    cs:__imp_WinHvGetPartitionProperty
0x140012908  nop     dword ptr [rax+rax+00h]
0x14001290d  mov     ebx, eax
0x14001290f  test    eax, eax
0x140012911  js      short loc_140012986
0x140012913  mov     rax, [rbp+57h+var_68]
0x140012917  lea     r8, [rbp+57h+var_60]
0x14001291b  shl     rax, 3
0x14001291f  mov     edx, 60002h
0x140012924  mov     rcx, r12
0x140012927  mov     [rbp+57h+var_68], rax
0x14001292b  call    cs:__imp_WinHvGetPartitionProperty
0x140012932  nop     dword ptr [rax+rax+00h]
0x140012937  mov     ebx, eax
0x140012939  test    eax, eax
0x14001293b  js      short loc_140012986
0x14001293d  test    r14b, r14b
0x140012940  jnz     short loc_140012954
0x140012942  test    cs:Microsoft_Windows_Hyper_V_HypervisorEnableBits, 40h
0x140012949  jz      short loc_140012986
0x14001294b  lea     rdx, HV_EVENTLOG_HOST_PROCESSOR_FEATURES_V1
0x140012952  jmp     short loc_140012964
0x140012954  test    cs:byte_140009539, 2
0x14001295b  jz      short loc_140012986
0x14001295d  lea     rdx, HV_EVENTLOG_RUNTIME_HOST_PROCESSOR_FEATURES_V1
0x140012964  mov     eax, dword ptr [rbp+57h+var_68]
0x140012967  mov     r9b, byte ptr [rbp+57h+var_70]
0x14001296b  mov     [rsp+0B0h+var_80], eax
0x14001296f  mov     rax, [rbp+57h+var_60]
0x140012973  mov     [rsp+0B0h+var_88], rax
0x140012978  lea     rax, [rbp+57h+var_50]
0x14001297c  mov     [rsp+0B0h+var_90], rax
0x140012981  call    McTemplateK0uIR0iq_EtwWriteTransfer
0x140012986  mov     edx, 75426248h; Tag
0x14001298b  mov     rcx, rsi; P
0x14001298e  call    cs:__imp_ExFreePoolWithTag
0x140012995  nop     dword ptr [rax+rax+00h]
0x14001299a  mov     edi, 1
0x14001299f  movzx   r8d, byte ptr [rbp+57h+var_70]
0x1400129a4  lea     r9, aHbevtplogproce_3; "HbEvtpLogProcessorFeatures: Processor F"...
0x1400129ab  movzx   eax, byte ptr [rbp+57h+var_70+1]
0x1400129af  lea     rdx, aHbevtplogproce_2; "HbEvtpLogProcessorFeatures"
0x1400129b6  mov     [rsp+0B0h+var_80], ebx
0x1400129ba  mov     ecx, edi
0x1400129bc  mov     dword ptr [rsp+0B0h+var_88], eax
0x1400129c0  mov     dword ptr [rsp+0B0h+var_90], r8d
0x1400129c5  mov     r8d, 125Ch
0x1400129cb  call    HbpTraceEvent
0x1400129d0  mov     rcx, [rbp+57h+var_38]
0x1400129d4  xor     rcx, rsp; StackCookie
0x1400129d7  call    __security_check_cookie
0x1400129dc  add     rsp, 88h
0x1400129e3  pop     r14
0x1400129e5  pop     r12
0x1400129e7  pop     rdi
0x1400129e8  pop     rsi
0x1400129e9  pop     rbx
0x1400129ea  pop     rbp
0x1400129eb  retn
```
