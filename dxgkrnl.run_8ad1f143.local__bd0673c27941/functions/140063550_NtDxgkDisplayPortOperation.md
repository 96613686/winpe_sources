# NtDxgkDisplayPortOperation

- ea: `0x140063550`
- end: `0x14006412e`
- name: `NtDxgkDisplayPortOperation`
- size: `3038`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x140009030`
- `0x140012b14`
- `0x140013860`
- `0x140015458`
- `0x140015780`
- `0x140015910`
- `0x140016fac`
- `0x14001b890`
- `0x14001d0e4`
- `0x14001f460`
- `0x14002ec90`
- `0x14002f48c`
- `0x14004c688`
- `0x140063550`
- `0x1400670a4`
- `0x14009fb54`
- `0x1400a0100`
- `0x1401e5360`
- `0x140200e04`
- `0x1402010d4`
- `0x1402013a4`
- `0x1402034e4`
- `0x140204728`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1400635dd`
- `ntoskrnl!SeExports` at `0x14006360c`
- `ntoskrnl!RtlCheckTokenMembership` at `0x1400635f5`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140063624`
- `ntoskrnl!RtlCheckTokenMembership` at `0x1400635f5`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140063624`
- `watchdog!WdLogSingleEntry2` at `0x1400637de`
- `watchdog!WdLogSingleEntry2` at `0x1400638b6`
- `watchdog!WdLogSingleEntry2` at `0x1400638e4`
- `watchdog!WdLogSingleEntry2` at `0x14006390e`
- `watchdog!WdLogSingleEntry2` at `0x14006393b`
- `watchdog!WdLogSingleEntry2` at `0x14006398d`
- `watchdog!WdLogSingleEntry2` at `0x140063a94`
- `watchdog!WdLogSingleEntry2` at `0x140063ac5`
- `watchdog!WdLogSingleEntry2` at `0x140063af2`
- `watchdog!WdLogSingleEntry2` at `0x140063b21`
- `watchdog!WdLogSingleEntry2` at `0x140063bd8`
- `watchdog!WdLogSingleEntry2` at `0x140063c12`
- `watchdog!WdLogSingleEntry2` at `0x140063c46`
- `watchdog!WdLogSingleEntry2` at `0x140063c8b`
- `watchdog!WdLogSingleEntry2` at `0x140063cb6`
- `watchdog!WdLogSingleEntry2` at `0x140063d09`
- `watchdog!WdLogSingleEntry2` at `0x140063d4f`
- `watchdog!WdLogSingleEntry2` at `0x140064024`
- `watchdog!WdLogSingleEntry2` at `0x1400637de`
- `watchdog!WdLogSingleEntry2` at `0x1400638b6`
- `watchdog!WdLogSingleEntry2` at `0x1400638e4`
- `watchdog!WdLogSingleEntry2` at `0x14006390e`
- `watchdog!WdLogSingleEntry2` at `0x14006393b`
- `watchdog!WdLogSingleEntry2` at `0x14006398d`
- `watchdog!WdLogSingleEntry2` at `0x140063a94`
- `watchdog!WdLogSingleEntry2` at `0x140063ac5`
- `watchdog!WdLogSingleEntry2` at `0x140063af2`
- `watchdog!WdLogSingleEntry2` at `0x140063b21`
- `watchdog!WdLogSingleEntry2` at `0x140063bd8`
- `watchdog!WdLogSingleEntry2` at `0x140063c12`
- `watchdog!WdLogSingleEntry2` at `0x140063c46`
- `watchdog!WdLogSingleEntry2` at `0x140063c8b`
- `watchdog!WdLogSingleEntry2` at `0x140063cb6`
- `watchdog!WdLogSingleEntry2` at `0x140063d09`
- `watchdog!WdLogSingleEntry2` at `0x140063d4f`
- `watchdog!WdLogSingleEntry2` at `0x140064024`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140063e9b`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x140063e9b`
- `watchdog!WdLogSingleEntry3` at `0x1400636aa`
- `watchdog!WdLogSingleEntry3` at `0x140063f46`
- `watchdog!WdLogSingleEntry3` at `0x1400636aa`
- `watchdog!WdLogSingleEntry3` at `0x140063f46`
- `watchdog!WdLogSingleEntry1` at `0x140063873`
- `watchdog!WdLogSingleEntry1` at `0x140063b52`
- `watchdog!WdLogSingleEntry1` at `0x140063b7d`
- `watchdog!WdLogSingleEntry1` at `0x140063baa`
- `watchdog!WdLogSingleEntry1` at `0x140063da4`
- `watchdog!WdLogSingleEntry1` at `0x140063fb0`
- `watchdog!WdLogSingleEntry1` at `0x140064089`
- `watchdog!WdLogSingleEntry1` at `0x140063873`
- `watchdog!WdLogSingleEntry1` at `0x140063b52`
- `watchdog!WdLogSingleEntry1` at `0x140063b7d`
- `watchdog!WdLogSingleEntry1` at `0x140063baa`
- `watchdog!WdLogSingleEntry1` at `0x140063da4`
- `watchdog!WdLogSingleEntry1` at `0x140063fb0`
- `watchdog!WdLogSingleEntry1` at `0x140064089`

## pseudocode

```c
__int64 __fastcall NtDxgkDisplayPortOperation(char *Src, __int64 a2, __int64 a3)
{
  struct DXGADAPTER *v4; // r14
  int v5; // r13d
  struct _DXGKARG_QUERYDPCAPS *v6; // rax
  struct _DXGKARG_QUERYDPCAPS *v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // ecx
  __int64 v15; // rdx
  int v16; // r15d
  __int64 v17; // rcx
  __int64 v18; // r8
  unsigned int DPCaps; // eax
  unsigned int v20; // ecx
  unsigned int v21; // edx
  unsigned int v22; // r9d
  int v23; // r8d
  unsigned int v24; // r14d
  __int64 v25; // rcx
  __int64 v26; // r8
  _QWORD *v27; // rax
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // r8
  char v34[8]; // [rsp+50h] [rbp-128h] BYREF
  unsigned int v35; // [rsp+58h] [rbp-120h] BYREF
  __int64 v36; // [rsp+60h] [rbp-118h]
  char v37; // [rsp+68h] [rbp-110h]
  struct _DXGKARG_QUERYDPCAPS *v38; // [rsp+70h] [rbp-108h] BYREF
  __int64 v39; // [rsp+78h] [rbp-100h] BYREF
  unsigned int v40; // [rsp+80h] [rbp-F8h] BYREF
  struct DXGADAPTER *v41[2]; // [rsp+88h] [rbp-F0h] BYREF
  struct _LUID v42[2]; // [rsp+98h] [rbp-E0h] BYREF
  _BYTE v43[144]; // [rsp+B0h] [rbp-C8h] BYREF

  v35 = -1;
  v36 = 0;
  if ( (qword_14015C500 & 2) != 0 )
  {
    v37 = 1;
    v35 = 2213;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(Src, EventProfilerEnter, a3, 2213);
  }
  else
  {
    v37 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v35, 2213);
  v34[0] = 0;
  if ( ((int)RtlCheckTokenMembership(0, SeExports->SeAliasAdminsSid, v34) < 0 || !v34[0])
    && ((int)RtlCheckTokenMembership(0, SeExports->SeLocalSystemSid, v34) < 0 || !v34[0]) )
  {
    goto LABEL_100;
  }
  *(_OWORD *)&v42[0].LowPart = 0;
  RtlCopyFromUser(v42, Src, 0x10u);
  v41[0] = 0;
  DXGADAPTER_REFERENCE::AssignByLuid((DXGADAPTER_REFERENCE *)v41, &v42[1]);
  v4 = v41[0];
  if ( !v41[0] )
  {
    WdLogSingleEntry3(2, v42[1].HighPart, v42[1].LowPart, -1073741811);
    WdLogGlobalForLineNumber = 81;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid Adapter (0x%I64x-0x%I64x) specified, returning 0x%I64x",
      v42[1].HighPart,
      v42[1].LowPart,
      -1073741811,
      0,
      0);
LABEL_96:
    DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v41, 0);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v35);
    if ( v37 )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v30, EventProfilerExit, v31, v35);
    }
    return 3221225485LL;
  }
  v5 = v42[0].HighPart - 16;
  if ( (unsigned int)(v42[0].HighPart - 17) > 0xFFF )
  {
    WdLogSingleEntry2(3, (int)v42[0].LowPart);
    WdLogGlobalForLineNumber = 89;
    goto LABEL_96;
  }
  v6 = (struct _DXGKARG_QUERYDPCAPS *)operator new[](v5, 1265072196, 256);
  v7 = v6;
  v38 = v6;
  if ( !v6 )
  {
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v38);
    DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v41, 0);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v35);
    if ( v37 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v8, EventProfilerExit, v9, v35);
    return 3221225495LL;
  }
  RtlCopyFromUser(v6, Src + 16, v5);
  COREADAPTERACCESS::COREADAPTERACCESS((COREADAPTERACCESS *)v43, v4, 0);
  if ( (int)COREADAPTERACCESS::AcquireShared((COREADAPTERACCESS *)v43, 0) < 0 )
  {
    WdLogSingleEntry2(3, v42[1].HighPart);
    WdLogGlobalForLineNumber = 115;
LABEL_19:
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v43);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v38);
    goto LABEL_96;
  }
  v12 = *((_QWORD *)v4 + 404);
  if ( !v12 )
  {
    WdLogSingleEntry3(2, v42[1].HighPart, v42[1].LowPart, -1073741811);
    WdLogGlobalForLineNumber = 123;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Non-display adapter (0x%I64x-0x%I64x) specified, returning 0x%I64x",
      v42[1].HighPart,
      v42[1].LowPart,
      -1073741811,
      0,
      0);
    goto LABEL_19;
  }
  if ( *((_QWORD *)v4 + 182) )
  {
    EXCLUSIVEACCESS<VIDPN_MGR>::EXCLUSIVEACCESS<VIDPN_MGR>(&v39, *(_QWORD *)(v12 + 104));
    switch ( v42[0].LowPart )
    {
      case 1u:
        if ( v42[0].HighPart < 0x18u )
        {
          WdLogSingleEntry2(3, 1);
          WdLogGlobalForLineNumber = 143;
          goto LABEL_28;
        }
        DPCaps = ADAPTER_DISPLAY::DdiQueryDPCaps(*((ADAPTER_DISPLAY **)v4 + 404), v7);
        break;
      case 2u:
        if ( v42[0].HighPart < 0x2Cu )
        {
          WdLogSingleEntry2(3, 2);
          WdLogGlobalForLineNumber = 159;
          goto LABEL_28;
        }
        DPCaps = ADAPTER_DISPLAY::DdiGetDPAddress(*((ADAPTER_DISPLAY **)v4 + 404), v7);
        break;
      case 3u:
        if ( v42[0].HighPart < 0x38u )
        {
          WdLogSingleEntry2(3, 3);
          WdLogGlobalForLineNumber = 175;
          goto LABEL_28;
        }
        if ( (*(_DWORD *)v7 & 1) != 0 )
        {
          WdLogSingleEntry2(3, 3);
          WdLogGlobalForLineNumber = 187;
          goto LABEL_28;
        }
        if ( *((_BYTE *)v7 + 12) > 0x10u )
          goto LABEL_28;
        DPCaps = ADAPTER_DISPLAY::DdiDPAuxIoTransmission(*((ADAPTER_DISPLAY **)v4 + 404), v7);
        break;
      case 4u:
        if ( v42[0].HighPart < 0x3Cu )
        {
          WdLogSingleEntry2(3, 4);
          WdLogGlobalForLineNumber = 204;
          goto LABEL_28;
        }
        v20 = *((_DWORD *)v7 + 4);
        if ( v20 + 40 > v5 )
        {
          WdLogSingleEntry2(3, 4);
          WdLogGlobalForLineNumber = 216;
          goto LABEL_28;
        }
        v21 = *((_DWORD *)v7 + 6);
        if ( v21 > v20 )
        {
          WdLogSingleEntry2(3, 4);
          WdLogGlobalForLineNumber = 222;
          goto LABEL_28;
        }
        v22 = *((_DWORD *)v7 + 5);
        if ( v22 > v20 )
        {
          WdLogSingleEntry2(3, 4);
          WdLogGlobalForLineNumber = 228;
          goto LABEL_28;
        }
        v23 = *(_DWORD *)v7;
        if ( (*(_DWORD *)v7 & 1) == 0 && (v23 & 2) == 0 )
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 234;
          goto LABEL_28;
        }
        if ( (*(_DWORD *)v7 & 1) != 0 && !v21 )
        {
          WdLogSingleEntry1(3);
          WdLogGlobalForLineNumber = 240;
          goto LABEL_28;
        }
        if ( (v23 & 2) != 0 )
        {
          if ( !v22 )
          {
            WdLogSingleEntry1(3);
            WdLogGlobalForLineNumber = 248;
            goto LABEL_28;
          }
          if ( *((_DWORD *)v7 + 2) != 110 )
          {
            WdLogSingleEntry2(3, 4);
            WdLogGlobalForLineNumber = 254;
            goto LABEL_28;
          }
        }
        if ( (v23 & 4) != 0 && (v23 & 0x38) != 8 )
        {
          WdLogSingleEntry2(3, 4);
          WdLogGlobalForLineNumber = 262;
          goto LABEL_28;
        }
        if ( (v23 & 0x38u) > 0x20 )
        {
          WdLogSingleEntry2(3, 4);
          WdLogGlobalForLineNumber = 268;
          goto LABEL_28;
        }
        DPCaps = ADAPTER_DISPLAY::DdiDPI2CIoTransmission(*((ADAPTER_DISPLAY **)v4 + 404), v7);
        break;
      case 5u:
        if ( v42[0].HighPart < 0x3Cu )
        {
          WdLogSingleEntry2(3, 5);
          WdLogGlobalForLineNumber = 280;
          goto LABEL_28;
        }
        v14 = *((_DWORD *)v7 + 2);
        if ( v14 + 28 > v5 )
        {
          WdLogSingleEntry2(3, 5);
          WdLogGlobalForLineNumber = 292;
          goto LABEL_28;
        }
        v15 = *((unsigned int *)v7 + 3);
        if ( (unsigned int)v15 > v14 )
        {
          WdLogSingleEntry2(3, 5);
          WdLogGlobalForLineNumber = 298;
          goto LABEL_28;
        }
        if ( *((_DWORD *)v7 + 4) > v14 )
        {
          WdLogSingleEntry2(3, 5);
          WdLogGlobalForLineNumber = 304;
          goto LABEL_28;
        }
        v40 = 127;
        v16 = SidebandMessageParser((char *)v7 + 28, v15, v13, &v40);
        if ( v16 < 0 )
        {
          WdLogSingleEntry2(3, (int)v42[0].LowPart);
          WdLogGlobalForLineNumber = 317;
          DXGFASTMUTEX::Release((DXGFASTMUTEX *)(v39 + 40));
          COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v43);
          wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v38);
          DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v41, 0);
          DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v35);
          if ( v37 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(v17, EventProfilerExit, v18, v35);
          return (unsigned int)v16;
        }
        if ( v40 >= 2 && v40 != 18 && v40 != 32 && v40 != 34 && v40 != 56 )
        {
          DXGFASTMUTEX::Release((DXGFASTMUTEX *)(v39 + 40));
          COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v43);
          wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v38);
          DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v41, 0);
LABEL_100:
          DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v35);
          if ( v37 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(v32, EventProfilerExit, v33, v35);
          return 3221225506LL;
        }
        DPCaps = ADAPTER_DISPLAY::DdiDPSBMTransmission(*((ADAPTER_DISPLAY **)v4 + 404), v7);
        break;
      default:
        WdLogSingleEntry1(3);
        WdLogGlobalForLineNumber = 340;
LABEL_28:
        DXGFASTMUTEX::Release((DXGFASTMUTEX *)(v39 + 40));
        goto LABEL_19;
    }
    v24 = DPCaps;
    v40 = DPCaps;
    RtlCopyToUser(Src + 16, v7, v5);
    DXGFASTMUTEX::Release((DXGFASTMUTEX *)(v39 + 40));
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v43);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v38);
    DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v41, 0);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v35);
    if ( v37 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v25, EventProfilerExit, v26, v35);
    return v24;
  }
  else
  {
    v27 = (_QWORD *)WdLogNewEntry5_WdTrace(v11);
    v27[3] = v42[1].HighPart;
    v27[4] = v42[1].LowPart;
    v27[5] = -1073741637;
    WdLogGlobalForLineNumber = 130;
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v43);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v38);
    DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v41, 0);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v35);
    if ( v37 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v28, EventProfilerExit, v29, v35);
    return 3221225659LL;
  }
}

```

## disassembly

```asm
0x140063550  mov     [rsp+arg_8], rbx
0x140063555  mov     [rsp+arg_10], rsi
0x14006355a  push    rdi
0x14006355b  push    r12
0x14006355d  push    r13
0x14006355f  push    r14
0x140063561  push    r15
0x140063563  sub     rsp, 150h
0x14006356a  mov     rax, cs:__security_cookie
0x140063571  xor     rax, rsp
0x140063574  mov     [rsp+178h+var_38], rax
0x14006357c  mov     r12, rcx
0x14006357f  mov     [rsp+178h+var_120], 0FFFFFFFFh
0x140063587  xor     edi, edi
0x140063589  mov     [rsp+178h+var_118], rdi
0x14006358e  mov     rax, cs:qword_14015C500
0x140063595  lea     ebx, [rdi+1]
0x140063598  test    al, 2
0x14006359a  jz      short loc_1400635C4
0x14006359c  mov     [rsp+178h+var_110], bl
0x1400635a0  mov     [rsp+178h+var_120], 8A5h
0x1400635a8  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x1400635ae  jz      short loc_1400635C9
0x1400635b0  mov     r9d, 8A5h
0x1400635b6  lea     rdx, EventProfilerEnter
0x1400635bd  call    McTemplateK0q_EtwWriteTransfer
0x1400635c2  jmp     short loc_1400635C9
0x1400635c4  mov     [rsp+178h+var_110], dil
0x1400635c9  mov     edx, 8A5h
0x1400635ce  lea     rcx, [rsp+178h+var_120]
0x1400635d3  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1400635d8  mov     [rsp+178h+var_128], dil
0x1400635dd  mov     rax, cs:__imp_SeExports
0x1400635e4  mov     rdx, [rax]
0x1400635e7  lea     r8, [rsp+178h+var_128]
0x1400635ec  mov     rdx, [rdx+110h]
0x1400635f3  xor     ecx, ecx
0x1400635f5  call    cs:__imp_RtlCheckTokenMembership
0x1400635fc  nop     dword ptr [rax+rax+00h]
0x140063601  test    eax, eax
0x140063603  js      short loc_14006360C
0x140063605  cmp     [rsp+178h+var_128], dil
0x14006360a  jnz     short loc_140063643
0x14006360c  mov     rax, cs:__imp_SeExports
0x140063613  mov     rdx, [rax]
0x140063616  lea     r8, [rsp+178h+var_128]
0x14006361b  mov     rdx, [rdx+108h]
0x140063622  xor     ecx, ecx
0x140063624  call    cs:__imp_RtlCheckTokenMembership
0x14006362b  nop     dword ptr [rax+rax+00h]
0x140063630  test    eax, eax
0x140063632  js      loc_1400640D1
0x140063638  cmp     [rsp+178h+var_128], dil
0x14006363d  jz      loc_1400640D1
0x140063643  xorps   xmm0, xmm0
0x140063646  movups  xmmword ptr [rsp+178h+var_E0.LowPart], xmm0
0x14006364e  mov     r8d, 10h; Size
0x140063654  mov     rdx, r12; Src
0x140063657  lea     rcx, [rsp+178h+var_E0]; void *
0x14006365f  call    RtlCopyFromUser
0x140063664  nop
0x140063665  mov     [rsp+178h+var_F0], rdi
0x14006366d  lea     rdx, [rsp+178h+var_E0.LowPart+8]; struct _LUID *
0x140063675  lea     rcx, [rsp+178h+var_F0]; this
0x14006367d  call    ?AssignByLuid@DXGADAPTER_REFERENCE@@QEAA_NAEBU_LUID@@@Z; DXGADAPTER_REFERENCE::AssignByLuid(_LUID const &)
0x140063682  mov     r14, [rsp+178h+var_F0]
0x14006368a  test    r14, r14
0x14006368d  jnz     short loc_140063708
0x14006368f  mov     r8d, [rsp+178h+var_E0.LowPart+8]
0x140063697  movsxd  rdx, [rsp+178h+var_E0.HighPart+8]
0x14006369f  lea     ecx, [r14+2]
0x1400636a3  mov     r9, 0FFFFFFFFC000000Dh
0x1400636aa  call    cs:__imp_WdLogSingleEntry3
0x1400636b1  nop     dword ptr [rax+rax+00h]
0x1400636b6  mov     cs:WdLogGlobalForLineNumber, 51h ; 'Q'
0x1400636c0  mov     ecx, [rsp+178h+var_E0.LowPart+8]
0x1400636c7  movsxd  rax, [rsp+178h+var_E0.HighPart+8]
0x1400636cf  mov     [rsp+178h+var_138], rdi
0x1400636d4  mov     [rsp+178h+var_140], rdi
0x1400636d9  mov     [rsp+178h+var_148], 0FFFFFFFFC000000Dh
0x1400636e2  mov     [rsp+178h+var_150], rcx
0x1400636e7  mov     [rsp+178h+var_158], rax
0x1400636ec  lea     r9, aInvalidAdapter_1; "Invalid Adapter (0x%I64x-0x%I64x) speci"...
0x1400636f3  or      r8d, 0FFFFFFFFh
0x1400636f7  mov     edx, 40000h
0x1400636fc  xor     ecx, ecx
0x1400636fe  call    DxgkLogInternalTriageEvent
0x140063703  jmp     loc_14006403A
0x140063708  mov     ecx, [rsp+178h+var_E0.HighPart]
0x14006370f  lea     r13d, [rcx-10h]
0x140063713  lea     eax, [r13-1]
0x140063717  cmp     eax, 0FFFh
0x14006371c  ja      loc_140064014
0x140063722  movsxd  r15, r13d
0x140063725  mov     edx, 4B677844h
0x14006372a  mov     r8d, 100h
0x140063730  mov     rcx, r15
0x140063733  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140063738  mov     rsi, rax
0x14006373b  mov     [rsp+178h+var_108], rax
0x140063740  test    rax, rax
0x140063743  jnz     short loc_140063792
0x140063745  lea     rcx, [rsp+178h+var_108]
0x14006374a  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x14006374f  xor     edx, edx; struct DXGADAPTER *
0x140063751  lea     rcx, [rsp+178h+var_F0]; this
0x140063759  call    ?Assign@DXGADAPTER_REFERENCE@@QEAAXPEAVDXGADAPTER@@@Z; DXGADAPTER_REFERENCE::Assign(DXGADAPTER *)
0x14006375e  lea     rcx, [rsp+178h+var_120]; this
0x140063763  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140063768  cmp     [rsp+178h+var_110], dil
0x14006376d  jz      short loc_140063788
0x14006376f  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x140063775  jz      short loc_140063788
0x140063777  mov     r9d, [rsp+178h+var_120]
0x14006377c  lea     rdx, EventProfilerExit
0x140063783  call    McTemplateK0q_EtwWriteTransfer
0x140063788  mov     eax, 0C0000017h
0x14006378d  jmp     loc_140064100
0x140063792  lea     rdx, [r12+10h]; Src
0x140063797  mov     r8, r15; Size
0x14006379a  mov     rcx, rsi; void *
0x14006379d  call    RtlCopyFromUser
0x1400637a2  nop
0x1400637a3  xor     r8d, r8d; struct DXGADAPTER *
0x1400637a6  mov     rdx, r14; struct DXGADAPTER *
0x1400637a9  lea     rcx, [rsp+178h+var_C8]; this
0x1400637b1  call    ??0COREADAPTERACCESS@@QEAA@QEAVDXGADAPTER@@0@Z; COREADAPTERACCESS::COREADAPTERACCESS(DXGADAPTER * const,DXGADAPTER * const)
0x1400637b6  xor     edx, edx; char *
0x1400637b8  lea     rcx, [rsp+178h+var_C8]; this
0x1400637c0  call    ?AcquireShared@COREADAPTERACCESS@@QEAAJPEBD@Z; COREADAPTERACCESS::AcquireShared(char const *)
0x1400637c5  test    eax, eax
0x1400637c7  jns     short loc_140063810
0x1400637c9  mov     r8d, [rsp+178h+var_E0.LowPart+8]
0x1400637d1  movsxd  rdx, [rsp+178h+var_E0.HighPart+8]
0x1400637d9  mov     ecx, 3
0x1400637de  call    cs:__imp_WdLogSingleEntry2
0x1400637e5  nop     dword ptr [rax+rax+00h]
0x1400637ea  mov     cs:WdLogGlobalForLineNumber, 73h ; 's'
0x1400637f4  lea     rcx, [rsp+178h+var_C8]; this
0x1400637fc  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x140063801  lea     rcx, [rsp+178h+var_108]
0x140063806  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x14006380b  jmp     loc_14006403A
0x140063810  mov     rdx, [r14+0CA0h]
0x140063817  test    rdx, rdx
0x14006381a  jz      loc_140063F2A
0x140063820  cmp     [r14+5B0h], rdi
0x140063827  jz      loc_140063E9B
0x14006382d  mov     rdx, [rdx+68h]
0x140063831  lea     rcx, [rsp+178h+var_100]
0x140063836  call    ??0?$EXCLUSIVEACCESS@VVIDPN_MGR@@@@QEAA@QEAVVIDPN_MGR@@@Z; EXCLUSIVEACCESS<VIDPN_MGR>::EXCLUSIVEACCESS<VIDPN_MGR>(VIDPN_MGR * const)
0x14006383b  movsxd  rdx, [rsp+178h+var_E0.LowPart]
0x140063843  mov     ecx, edx
0x140063845  sub     ecx, 1
0x140063848  jz      loc_140063D35
0x14006384e  sub     ecx, 1
0x140063851  jz      loc_140063CEF
0x140063857  sub     ecx, 1
0x14006385a  jz      loc_140063C75
0x140063860  sub     ecx, 1
0x140063863  jz      loc_140063A7A
0x140063869  cmp     ecx, 1
0x14006386c  jz      short loc_14006389C
0x14006386e  mov     ecx, 3
0x140063873  call    cs:__imp_WdLogSingleEntry1
0x14006387a  nop     dword ptr [rax+rax+00h]
0x14006387f  mov     cs:WdLogGlobalForLineNumber, 154h
0x140063889  mov     rcx, [rsp+178h+var_100]
0x14006388e  add     rcx, 28h ; '('; this
0x140063892  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x140063897  jmp     loc_1400637F4
0x14006389c  cmp     [rsp+178h+var_E0.HighPart], 3Ch ; '<'
0x1400638a4  jnb     short loc_1400638CE
0x1400638a6  mov     r8d, [rsp+178h+var_E0.HighPart]
0x1400638ae  mov     edx, 5
0x1400638b3  lea     ecx, [rdx-2]
0x1400638b6  call    cs:__imp_WdLogSingleEntry2
0x1400638bd  nop     dword ptr [rax+rax+00h]
0x1400638c2  mov     cs:WdLogGlobalForLineNumber, 118h
0x1400638cc  jmp     short loc_140063889
0x1400638ce  mov     ecx, [rsi+8]
0x1400638d1  lea     eax, [rcx+1Ch]
0x1400638d4  cmp     eax, r13d
0x1400638d7  jbe     short loc_1400638FC
0x1400638d9  mov     r8d, ecx
0x1400638dc  mov     edx, 5
0x1400638e1  lea     ecx, [rdx-2]
0x1400638e4  call    cs:__imp_WdLogSingleEntry2
0x1400638eb  nop     dword ptr [rax+rax+00h]
0x1400638f0  mov     cs:WdLogGlobalForLineNumber, 124h
0x1400638fa  jmp     short loc_140063889
0x1400638fc  mov     edx, [rsi+0Ch]
0x1400638ff  cmp     edx, ecx
0x140063901  jbe     short loc_140063929
0x140063903  mov     r8d, edx
0x140063906  mov     edx, 5
0x14006390b  lea     ecx, [rdx-2]
0x14006390e  call    cs:__imp_WdLogSingleEntry2
0x140063915  nop     dword ptr [rax+rax+00h]
0x14006391a  mov     cs:WdLogGlobalForLineNumber, 12Ah
0x140063924  jmp     loc_140063889
0x140063929  mov     eax, [rsi+10h]
0x14006392c  cmp     eax, ecx
0x14006392e  jbe     short loc_140063956
0x140063930  mov     r8d, eax
0x140063933  mov     edx, 5
0x140063938  lea     ecx, [rdx-2]
0x14006393b  call    cs:__imp_WdLogSingleEntry2
0x140063942  nop     dword ptr [rax+rax+00h]
0x140063947  mov     cs:WdLogGlobalForLineNumber, 130h
0x140063951  jmp     loc_140063889
0x140063956  mov     [rsp+178h+var_F8], 7Fh
0x140063961  lea     rcx, [rsi+1Ch]
0x140063965  lea     r9, [rsp+178h+var_F8]
0x14006396d  call    ?SidebandMessageParser@@YAJPEAEIT_SB_MSG_PARSER_CONFIG@@PEAW4_SBMT_REQUEST_ID@@P6AJPEAX0I@Z3@Z; SidebandMessageParser(uchar *,uint,_SB_MSG_PARSER_CONFIG,_SBMT_REQUEST_ID *,long (*)(void *,uchar *,uint),void *)
0x140063972  movsxd  r15, eax
0x140063975  test    eax, eax
0x140063977  jns     loc_140063A09
0x14006397d  mov     r8, r15
0x140063980  movsxd  rdx, [rsp+178h+var_E0.LowPart]
0x140063988  mov     ecx, 3
0x14006398d  call    cs:__imp_WdLogSingleEntry2
0x140063994  nop     dword ptr [rax+rax+00h]
0x140063999  mov     cs:WdLogGlobalForLineNumber, 13Dh
0x1400639a3  mov     rcx, [rsp+178h+var_100]
0x1400639a8  add     rcx, 28h ; '('; this
0x1400639ac  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x1400639b1  lea     rcx, [rsp+178h+var_C8]; this
0x1400639b9  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x1400639be  lea     rcx, [rsp+178h+var_108]
0x1400639c3  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x1400639c8  xor     edx, edx; struct DXGADAPTER *
0x1400639ca  lea     rcx, [rsp+178h+var_F0]; this
0x1400639d2  call    ?Assign@DXGADAPTER_REFERENCE@@QEAAXPEAVDXGADAPTER@@@Z; DXGADAPTER_REFERENCE::Assign(DXGADAPTER *)
0x1400639d7  lea     rcx, [rsp+178h+var_120]; this
0x1400639dc  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x1400639e1  cmp     [rsp+178h+var_110], dil
0x1400639e6  jz      short loc_140063A01
0x1400639e8  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x1400639ee  jz      short loc_140063A01
0x1400639f0  mov     r9d, [rsp+178h+var_120]
0x1400639f5  lea     rdx, EventProfilerExit
0x1400639fc  call    McTemplateK0q_EtwWriteTransfer
0x140063a01  mov     eax, r15d
0x140063a04  jmp     loc_140064100
0x140063a09  mov     ecx, [rsp+178h+var_F8]
0x140063a10  test    ecx, ecx
0x140063a12  jz      short loc_140063A66
0x140063a14  sub     ecx, 1
0x140063a17  jz      short loc_140063A66
0x140063a19  sub     ecx, 11h
0x140063a1c  jz      short loc_140063A66
0x140063a1e  sub     ecx, 0Eh
0x140063a21  jz      short loc_140063A66
0x140063a23  sub     ecx, 2
0x140063a26  jz      short loc_140063A66
0x140063a28  cmp     ecx, 16h
0x140063a2b  jz      short loc_140063A66
0x140063a2d  mov     rcx, [rsp+178h+var_100]
0x140063a32  add     rcx, 28h ; '('; this
0x140063a36  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x140063a3b  lea     rcx, [rsp+178h+var_C8]; this
0x140063a43  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x140063a48  lea     rcx, [rsp+178h+var_108]
0x140063a4d  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x140063a52  xor     edx, edx; struct DXGADAPTER *
0x140063a54  lea     rcx, [rsp+178h+var_F0]; this
0x140063a5c  call    ?Assign@DXGADAPTER_REFERENCE@@QEAAXPEAVDXGADAPTER@@@Z; DXGADAPTER_REFERENCE::Assign(DXGADAPTER *)
0x140063a61  jmp     loc_1400640D1
0x140063a66  mov     rdx, rsi; struct _DXGKARG_DPSBMTRANSMISSION *
0x140063a69  mov     rcx, [r14+0CA0h]; this
0x140063a70  call    ?DdiDPSBMTransmission@ADAPTER_DISPLAY@@QEAAJPEAU_DXGKARG_DPSBMTRANSMISSION@@@Z; ADAPTER_DISPLAY::DdiDPSBMTransmission(_DXGKARG_DPSBMTRANSMISSION *)
0x140063a75  jmp     loc_140063D79
0x140063a7a  cmp     [rsp+178h+var_E0.HighPart], 3Ch ; '<'
0x140063a82  jnb     short loc_140063AAF
0x140063a84  mov     r8d, [rsp+178h+var_E0.HighPart]
0x140063a8c  mov     edx, 4
0x140063a91  lea     ecx, [rdx-1]
0x140063a94  call    cs:__imp_WdLogSingleEntry2
0x140063a9b  nop     dword ptr [rax+rax+00h]
0x140063aa0  mov     cs:WdLogGlobalForLineNumber, 0CCh
0x140063aaa  jmp     loc_140063889
0x140063aaf  mov     ecx, [rsi+10h]
0x140063ab2  lea     eax, [rcx+28h]
0x140063ab5  cmp     eax, r13d
0x140063ab8  jbe     short loc_140063AE0
0x140063aba  mov     r8d, ecx
0x140063abd  mov     edx, 4
0x140063ac2  lea     ecx, [rdx-1]
0x140063ac5  call    cs:__imp_WdLogSingleEntry2
0x140063acc  nop     dword ptr [rax+rax+00h]
0x140063ad1  mov     cs:WdLogGlobalForLineNumber, 0D8h
0x140063adb  jmp     loc_140063889
0x140063ae0  mov     edx, [rsi+18h]
0x140063ae3  cmp     edx, ecx
0x140063ae5  jbe     short loc_140063B0D
0x140063ae7  mov     r8d, edx
0x140063aea  mov     edx, 4
0x140063aef  lea     ecx, [rdx-1]
0x140063af2  call    cs:__imp_WdLogSingleEntry2
  ... truncated ...
```
