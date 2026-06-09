# NtDxgkDisplayPortOperation

- ea: `0x140063970`
- end: `0x14006454e`
- name: `NtDxgkDisplayPortOperation`
- size: `3038`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x1400091f0`
- `0x140012cd4`
- `0x140013a20`
- `0x140015618`
- `0x140015940`
- `0x140015ad0`
- `0x14001716c`
- `0x14001b9c0`
- `0x14001d214`
- `0x14001f630`
- `0x14002ee60`
- `0x14002f65c`
- `0x14004c888`
- `0x140063970`
- `0x1400674c4`
- `0x1400a0624`
- `0x1400a0bd0`
- `0x1401e76e0`
- `0x1402031e4`
- `0x1402034b4`
- `0x140203784`
- `0x140205b30`
- `0x140206d74`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1400639fd`
- `ntoskrnl!SeExports` at `0x140063a2c`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140063a15`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140063a44`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140063a15`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140063a44`
- `watchdog!WdLogSingleEntry2` at `0x140063bfe`
- `watchdog!WdLogSingleEntry2` at `0x140063cd6`
- `watchdog!WdLogSingleEntry2` at `0x140063d04`
- `watchdog!WdLogSingleEntry2` at `0x140063d2e`
- `watchdog!WdLogSingleEntry2` at `0x140063d5b`
- `watchdog!WdLogSingleEntry2` at `0x140063dad`
- `watchdog!WdLogSingleEntry2` at `0x140063eb4`
- `watchdog!WdLogSingleEntry2` at `0x140063ee5`
- `watchdog!WdLogSingleEntry2` at `0x140063f12`
- `watchdog!WdLogSingleEntry2` at `0x140063f41`
- `watchdog!WdLogSingleEntry2` at `0x140063ff8`
- `watchdog!WdLogSingleEntry2` at `0x140064032`
- `watchdog!WdLogSingleEntry2` at `0x140064066`
- `watchdog!WdLogSingleEntry2` at `0x1400640ab`
- `watchdog!WdLogSingleEntry2` at `0x1400640d6`
- `watchdog!WdLogSingleEntry2` at `0x140064129`
- `watchdog!WdLogSingleEntry2` at `0x14006416f`
- `watchdog!WdLogSingleEntry2` at `0x140064444`
- `watchdog!WdLogSingleEntry2` at `0x140063bfe`
- `watchdog!WdLogSingleEntry2` at `0x140063cd6`
- `watchdog!WdLogSingleEntry2` at `0x140063d04`
- `watchdog!WdLogSingleEntry2` at `0x140063d2e`
- `watchdog!WdLogSingleEntry2` at `0x140063d5b`
- `watchdog!WdLogSingleEntry2` at `0x140063dad`
- `watchdog!WdLogSingleEntry2` at `0x140063eb4`
- `watchdog!WdLogSingleEntry2` at `0x140063ee5`
- `watchdog!WdLogSingleEntry2` at `0x140063f12`
- `watchdog!WdLogSingleEntry2` at `0x140063f41`
- `watchdog!WdLogSingleEntry2` at `0x140063ff8`
- `watchdog!WdLogSingleEntry2` at `0x140064032`
- `watchdog!WdLogSingleEntry2` at `0x140064066`
- `watchdog!WdLogSingleEntry2` at `0x1400640ab`
- `watchdog!WdLogSingleEntry2` at `0x1400640d6`
- `watchdog!WdLogSingleEntry2` at `0x140064129`
- `watchdog!WdLogSingleEntry2` at `0x14006416f`
- `watchdog!WdLogSingleEntry2` at `0x140064444`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400642bb`
- `watchdog!WdLogNewEntry5_WdTrace` at `0x1400642bb`
- `watchdog!WdLogSingleEntry3` at `0x140063aca`
- `watchdog!WdLogSingleEntry3` at `0x140064366`
- `watchdog!WdLogSingleEntry3` at `0x140063aca`
- `watchdog!WdLogSingleEntry3` at `0x140064366`
- `watchdog!WdLogSingleEntry1` at `0x140063c93`
- `watchdog!WdLogSingleEntry1` at `0x140063f72`
- `watchdog!WdLogSingleEntry1` at `0x140063f9d`
- `watchdog!WdLogSingleEntry1` at `0x140063fca`
- `watchdog!WdLogSingleEntry1` at `0x1400641c4`
- `watchdog!WdLogSingleEntry1` at `0x1400643d0`
- `watchdog!WdLogSingleEntry1` at `0x1400644a9`
- `watchdog!WdLogSingleEntry1` at `0x140063c93`
- `watchdog!WdLogSingleEntry1` at `0x140063f72`
- `watchdog!WdLogSingleEntry1` at `0x140063f9d`
- `watchdog!WdLogSingleEntry1` at `0x140063fca`
- `watchdog!WdLogSingleEntry1` at `0x1400641c4`
- `watchdog!WdLogSingleEntry1` at `0x1400643d0`
- `watchdog!WdLogSingleEntry1` at `0x1400644a9`

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
  unsigned int v16; // eax
  int v17; // eax
  unsigned int v18; // r15d
  __int64 v19; // rcx
  __int64 v20; // r8
  unsigned int DPCaps; // eax
  unsigned int v22; // ecx
  unsigned int v23; // edx
  unsigned int v24; // r9d
  int v25; // r8d
  unsigned int v26; // eax
  unsigned int v27; // r14d
  __int64 v28; // rcx
  __int64 v29; // r8
  _QWORD *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // r8
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // rcx
  __int64 v36; // r8
  char v37[8]; // [rsp+50h] [rbp-128h] BYREF
  unsigned int v38; // [rsp+58h] [rbp-120h] BYREF
  __int64 v39; // [rsp+60h] [rbp-118h]
  char v40; // [rsp+68h] [rbp-110h]
  struct _DXGKARG_QUERYDPCAPS *v41; // [rsp+70h] [rbp-108h] BYREF
  __int64 v42; // [rsp+78h] [rbp-100h] BYREF
  unsigned int v43; // [rsp+80h] [rbp-F8h] BYREF
  struct DXGADAPTER *v44[2]; // [rsp+88h] [rbp-F0h] BYREF
  struct _LUID v45[2]; // [rsp+98h] [rbp-E0h] BYREF
  _BYTE v46[144]; // [rsp+B0h] [rbp-C8h] BYREF

  v38 = -1;
  v39 = 0;
  if ( (qword_1401604F0 & 2) != 0 )
  {
    v40 = 1;
    v38 = 2213;
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(Src, EventProfilerEnter, a3, 2213);
  }
  else
  {
    v40 = 0;
  }
  DXGETWPROFILER_BASE::PushProfilerEntry(&v38, 2213);
  v37[0] = 0;
  if ( ((int)RtlCheckTokenMembership(0, SeExports->SeAliasAdminsSid, v37) < 0 || !v37[0])
    && ((int)RtlCheckTokenMembership(0, SeExports->SeLocalSystemSid, v37) < 0 || !v37[0]) )
  {
    goto LABEL_100;
  }
  *(_OWORD *)&v45[0].LowPart = 0;
  RtlCopyFromUser(v45, Src, 0x10u);
  v44[0] = 0;
  DXGADAPTER_REFERENCE::AssignByLuid((DXGADAPTER_REFERENCE *)v44, &v45[1]);
  v4 = v44[0];
  if ( !v44[0] )
  {
    WdLogSingleEntry3(2, v45[1].HighPart, v45[1].LowPart, -1073741811);
    WdLogGlobalForLineNumber = 81;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Invalid Adapter (0x%I64x-0x%I64x) specified, returning 0x%I64x",
      v45[1].HighPart,
      v45[1].LowPart,
      -1073741811,
      0,
      0);
LABEL_96:
    DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v44, 0);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v38);
    if ( v40 )
    {
      if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
        McTemplateK0q_EtwWriteTransfer(v33, EventProfilerExit, v34, v38);
    }
    return 3221225485LL;
  }
  v5 = v45[0].HighPart - 16;
  if ( (unsigned int)(v45[0].HighPart - 17) > 0xFFF )
  {
    WdLogSingleEntry2(3, (int)v45[0].LowPart, (unsigned int)v45[0].HighPart);
    WdLogGlobalForLineNumber = 89;
    goto LABEL_96;
  }
  v6 = (struct _DXGKARG_QUERYDPCAPS *)operator new[](v5, 1265072196, 256);
  v7 = v6;
  v41 = v6;
  if ( !v6 )
  {
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v41);
    DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v44, 0);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v38);
    if ( v40 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v8, EventProfilerExit, v9, v38);
    return 3221225495LL;
  }
  RtlCopyFromUser(v6, Src + 16, v5);
  COREADAPTERACCESS::COREADAPTERACCESS((COREADAPTERACCESS *)v46, v4, 0);
  if ( (int)COREADAPTERACCESS::AcquireShared((COREADAPTERACCESS *)v46, 0) < 0 )
  {
    WdLogSingleEntry2(3, v45[1].HighPart, v45[1].LowPart);
    WdLogGlobalForLineNumber = 115;
LABEL_19:
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v46);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v41);
    goto LABEL_96;
  }
  v12 = *((_QWORD *)v4 + 406);
  if ( !v12 )
  {
    WdLogSingleEntry3(2, v45[1].HighPart, v45[1].LowPart, -1073741811);
    WdLogGlobalForLineNumber = 123;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Non-display adapter (0x%I64x-0x%I64x) specified, returning 0x%I64x",
      v45[1].HighPart,
      v45[1].LowPart,
      -1073741811,
      0,
      0);
    goto LABEL_19;
  }
  if ( *((_QWORD *)v4 + 182) )
  {
    EXCLUSIVEACCESS<VIDPN_MGR>::EXCLUSIVEACCESS<VIDPN_MGR>(&v42, *(_QWORD *)(v12 + 104));
    switch ( v45[0].LowPart )
    {
      case 1u:
        if ( v45[0].HighPart < 0x18u )
        {
          WdLogSingleEntry2(3, 1, (unsigned int)v45[0].HighPart);
          WdLogGlobalForLineNumber = 143;
          goto LABEL_28;
        }
        DPCaps = ADAPTER_DISPLAY::DdiQueryDPCaps(*((ADAPTER_DISPLAY **)v4 + 406), v7);
        break;
      case 2u:
        if ( v45[0].HighPart < 0x2Cu )
        {
          WdLogSingleEntry2(3, 2, (unsigned int)v45[0].HighPart);
          WdLogGlobalForLineNumber = 159;
          goto LABEL_28;
        }
        DPCaps = ADAPTER_DISPLAY::DdiGetDPAddress(*((ADAPTER_DISPLAY **)v4 + 406), v7);
        break;
      case 3u:
        if ( v45[0].HighPart < 0x38u )
        {
          WdLogSingleEntry2(3, 3, (unsigned int)v45[0].HighPart);
          WdLogGlobalForLineNumber = 175;
          goto LABEL_28;
        }
        if ( (*(_DWORD *)v7 & 1) != 0 )
        {
          WdLogSingleEntry2(3, 3, (unsigned int)v45[0].HighPart);
          WdLogGlobalForLineNumber = 187;
          goto LABEL_28;
        }
        if ( *((_BYTE *)v7 + 12) > 0x10u )
          goto LABEL_28;
        DPCaps = ADAPTER_DISPLAY::DdiDPAuxIoTransmission(*((ADAPTER_DISPLAY **)v4 + 406), v7);
        break;
      case 4u:
        if ( v45[0].HighPart < 0x3Cu )
        {
          WdLogSingleEntry2(3, 4, (unsigned int)v45[0].HighPart);
          WdLogGlobalForLineNumber = 204;
          goto LABEL_28;
        }
        v22 = *((_DWORD *)v7 + 4);
        if ( v22 + 40 > v5 )
        {
          WdLogSingleEntry2(3, 4, v22);
          WdLogGlobalForLineNumber = 216;
          goto LABEL_28;
        }
        v23 = *((_DWORD *)v7 + 6);
        if ( v23 > v22 )
        {
          WdLogSingleEntry2(3, 4, v23);
          WdLogGlobalForLineNumber = 222;
          goto LABEL_28;
        }
        v24 = *((_DWORD *)v7 + 5);
        if ( v24 > v22 )
        {
          WdLogSingleEntry2(3, 4, v24);
          WdLogGlobalForLineNumber = 228;
          goto LABEL_28;
        }
        v25 = *(_DWORD *)v7;
        if ( (*(_DWORD *)v7 & 1) == 0 && (v25 & 2) == 0 )
        {
          WdLogSingleEntry1(3, 4);
          WdLogGlobalForLineNumber = 234;
          goto LABEL_28;
        }
        if ( (*(_DWORD *)v7 & 1) != 0 && !v23 )
        {
          WdLogSingleEntry1(3, 4);
          WdLogGlobalForLineNumber = 240;
          goto LABEL_28;
        }
        if ( (v25 & 2) != 0 )
        {
          if ( !v24 )
          {
            WdLogSingleEntry1(3, 4);
            WdLogGlobalForLineNumber = 248;
            goto LABEL_28;
          }
          v26 = *((_DWORD *)v7 + 2);
          if ( v26 != 110 )
          {
            WdLogSingleEntry2(3, 4, v26);
            WdLogGlobalForLineNumber = 254;
            goto LABEL_28;
          }
        }
        if ( (v25 & 4) != 0 && (v25 & 0x38) != 8 )
        {
          WdLogSingleEntry2(3, 4, (*(_DWORD *)v7 >> 3) & 7);
          WdLogGlobalForLineNumber = 262;
          goto LABEL_28;
        }
        if ( (v25 & 0x38u) > 0x20 )
        {
          WdLogSingleEntry2(3, 4, (*(_DWORD *)v7 >> 3) & 7);
          WdLogGlobalForLineNumber = 268;
          goto LABEL_28;
        }
        DPCaps = ADAPTER_DISPLAY::DdiDPI2CIoTransmission(*((ADAPTER_DISPLAY **)v4 + 406), v7);
        break;
      case 5u:
        if ( v45[0].HighPart < 0x3Cu )
        {
          WdLogSingleEntry2(3, 5, (unsigned int)v45[0].HighPart);
          WdLogGlobalForLineNumber = 280;
          goto LABEL_28;
        }
        v14 = *((_DWORD *)v7 + 2);
        if ( v14 + 28 > v5 )
        {
          WdLogSingleEntry2(3, 5, v14);
          WdLogGlobalForLineNumber = 292;
          goto LABEL_28;
        }
        v15 = *((unsigned int *)v7 + 3);
        if ( (unsigned int)v15 > v14 )
        {
          WdLogSingleEntry2(3, 5, (unsigned int)v15);
          WdLogGlobalForLineNumber = 298;
          goto LABEL_28;
        }
        v16 = *((_DWORD *)v7 + 4);
        if ( v16 > v14 )
        {
          WdLogSingleEntry2(3, 5, v16);
          WdLogGlobalForLineNumber = 304;
          goto LABEL_28;
        }
        v43 = 127;
        v17 = SidebandMessageParser((char *)v7 + 28, v15, v13, &v43);
        v18 = v17;
        if ( v17 < 0 )
        {
          WdLogSingleEntry2(3, (int)v45[0].LowPart, v17);
          WdLogGlobalForLineNumber = 317;
          DXGFASTMUTEX::Release((DXGFASTMUTEX *)(v42 + 40));
          COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v46);
          wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v41);
          DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v44, 0);
          DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v38);
          if ( v40 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(v19, EventProfilerExit, v20, v38);
          return v18;
        }
        if ( v43 >= 2 && v43 != 18 && v43 != 32 && v43 != 34 && v43 != 56 )
        {
          DXGFASTMUTEX::Release((DXGFASTMUTEX *)(v42 + 40));
          COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v46);
          wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v41);
          DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v44, 0);
LABEL_100:
          DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v38);
          if ( v40 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(v35, EventProfilerExit, v36, v38);
          return 3221225506LL;
        }
        DPCaps = ADAPTER_DISPLAY::DdiDPSBMTransmission(*((ADAPTER_DISPLAY **)v4 + 406), v7);
        break;
      default:
        WdLogSingleEntry1(3, (int)v45[0].LowPart);
        WdLogGlobalForLineNumber = 340;
LABEL_28:
        DXGFASTMUTEX::Release((DXGFASTMUTEX *)(v42 + 40));
        goto LABEL_19;
    }
    v27 = DPCaps;
    v43 = DPCaps;
    RtlCopyToUser(Src + 16, v7, v5);
    DXGFASTMUTEX::Release((DXGFASTMUTEX *)(v42 + 40));
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v46);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v41);
    DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v44, 0);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v38);
    if ( v40 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v28, EventProfilerExit, v29, v38);
    return v27;
  }
  else
  {
    v30 = (_QWORD *)WdLogNewEntry5_WdTrace(v11);
    v30[3] = v45[1].HighPart;
    v30[4] = v45[1].LowPart;
    v30[5] = -1073741637;
    WdLogGlobalForLineNumber = 130;
    COREADAPTERACCESS::~COREADAPTERACCESS((COREADAPTERACCESS *)v46);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v41);
    DXGADAPTER_REFERENCE::Assign((DXGADAPTER_REFERENCE *)v44, 0);
    DXGETWPROFILER_BASE::PopProfilerEntry((DXGETWPROFILER_BASE *)&v38);
    if ( v40 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
      McTemplateK0q_EtwWriteTransfer(v31, EventProfilerExit, v32, v38);
    return 3221225659LL;
  }
}

```

## disassembly

```asm
0x140063970  mov     [rsp+arg_8], rbx
0x140063975  mov     [rsp+arg_10], rsi
0x14006397a  push    rdi
0x14006397b  push    r12
0x14006397d  push    r13
0x14006397f  push    r14
0x140063981  push    r15
0x140063983  sub     rsp, 150h
0x14006398a  mov     rax, cs:__security_cookie
0x140063991  xor     rax, rsp
0x140063994  mov     [rsp+178h+var_38], rax
0x14006399c  mov     r12, rcx
0x14006399f  mov     [rsp+178h+var_120], 0FFFFFFFFh
0x1400639a7  xor     edi, edi
0x1400639a9  mov     [rsp+178h+var_118], rdi
0x1400639ae  mov     rax, cs:qword_1401604F0
0x1400639b5  lea     ebx, [rdi+1]
0x1400639b8  test    al, 2
0x1400639ba  jz      short loc_1400639E4
0x1400639bc  mov     [rsp+178h+var_110], bl
0x1400639c0  mov     [rsp+178h+var_120], 8A5h
0x1400639c8  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x1400639ce  jz      short loc_1400639E9
0x1400639d0  mov     r9d, 8A5h
0x1400639d6  lea     rdx, EventProfilerEnter
0x1400639dd  call    McTemplateK0q_EtwWriteTransfer
0x1400639e2  jmp     short loc_1400639E9
0x1400639e4  mov     [rsp+178h+var_110], dil
0x1400639e9  mov     edx, 8A5h
0x1400639ee  lea     rcx, [rsp+178h+var_120]
0x1400639f3  call    ?PushProfilerEntry@DXGETWPROFILER_BASE@@QEAAXW4_DXGKETW_PROFILER_TYPE@@@Z; DXGETWPROFILER_BASE::PushProfilerEntry(_DXGKETW_PROFILER_TYPE)
0x1400639f8  mov     [rsp+178h+var_128], dil
0x1400639fd  mov     rax, cs:__imp_SeExports
0x140063a04  mov     rdx, [rax]
0x140063a07  lea     r8, [rsp+178h+var_128]
0x140063a0c  mov     rdx, [rdx+110h]
0x140063a13  xor     ecx, ecx
0x140063a15  call    cs:__imp_RtlCheckTokenMembership
0x140063a1c  nop     dword ptr [rax+rax+00h]
0x140063a21  test    eax, eax
0x140063a23  js      short loc_140063A2C
0x140063a25  cmp     [rsp+178h+var_128], dil
0x140063a2a  jnz     short loc_140063A63
0x140063a2c  mov     rax, cs:__imp_SeExports
0x140063a33  mov     rdx, [rax]
0x140063a36  lea     r8, [rsp+178h+var_128]
0x140063a3b  mov     rdx, [rdx+108h]
0x140063a42  xor     ecx, ecx
0x140063a44  call    cs:__imp_RtlCheckTokenMembership
0x140063a4b  nop     dword ptr [rax+rax+00h]
0x140063a50  test    eax, eax
0x140063a52  js      loc_1400644F1
0x140063a58  cmp     [rsp+178h+var_128], dil
0x140063a5d  jz      loc_1400644F1
0x140063a63  xorps   xmm0, xmm0
0x140063a66  movups  xmmword ptr [rsp+178h+var_E0.LowPart], xmm0
0x140063a6e  mov     r8d, 10h; Size
0x140063a74  mov     rdx, r12; Src
0x140063a77  lea     rcx, [rsp+178h+var_E0]; void *
0x140063a7f  call    RtlCopyFromUser
0x140063a84  nop
0x140063a85  mov     [rsp+178h+var_F0], rdi
0x140063a8d  lea     rdx, [rsp+178h+var_E0.LowPart+8]; struct _LUID *
0x140063a95  lea     rcx, [rsp+178h+var_F0]; this
0x140063a9d  call    ?AssignByLuid@DXGADAPTER_REFERENCE@@QEAA_NAEBU_LUID@@@Z; DXGADAPTER_REFERENCE::AssignByLuid(_LUID const &)
0x140063aa2  mov     r14, [rsp+178h+var_F0]
0x140063aaa  test    r14, r14
0x140063aad  jnz     short loc_140063B28
0x140063aaf  mov     r8d, [rsp+178h+var_E0.LowPart+8]
0x140063ab7  movsxd  rdx, [rsp+178h+var_E0.HighPart+8]
0x140063abf  lea     ecx, [r14+2]
0x140063ac3  mov     r9, 0FFFFFFFFC000000Dh
0x140063aca  call    cs:__imp_WdLogSingleEntry3
0x140063ad1  nop     dword ptr [rax+rax+00h]
0x140063ad6  mov     cs:WdLogGlobalForLineNumber, 51h ; 'Q'
0x140063ae0  mov     ecx, [rsp+178h+var_E0.LowPart+8]
0x140063ae7  movsxd  rax, [rsp+178h+var_E0.HighPart+8]
0x140063aef  mov     [rsp+178h+var_138], rdi
0x140063af4  mov     [rsp+178h+var_140], rdi
0x140063af9  mov     [rsp+178h+var_148], 0FFFFFFFFC000000Dh
0x140063b02  mov     [rsp+178h+var_150], rcx
0x140063b07  mov     [rsp+178h+var_158], rax
0x140063b0c  lea     r9, aInvalidAdapter_1; "Invalid Adapter (0x%I64x-0x%I64x) speci"...
0x140063b13  or      r8d, 0FFFFFFFFh
0x140063b17  mov     edx, 40000h
0x140063b1c  xor     ecx, ecx
0x140063b1e  call    DxgkLogInternalTriageEvent
0x140063b23  jmp     loc_14006445A
0x140063b28  mov     ecx, [rsp+178h+var_E0.HighPart]
0x140063b2f  lea     r13d, [rcx-10h]
0x140063b33  lea     eax, [r13-1]
0x140063b37  cmp     eax, 0FFFh
0x140063b3c  ja      loc_140064434
0x140063b42  movsxd  r15, r13d
0x140063b45  mov     edx, 4B677844h
0x140063b4a  mov     r8d, 100h
0x140063b50  mov     rcx, r15
0x140063b53  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x140063b58  mov     rsi, rax
0x140063b5b  mov     [rsp+178h+var_108], rax
0x140063b60  test    rax, rax
0x140063b63  jnz     short loc_140063BB2
0x140063b65  lea     rcx, [rsp+178h+var_108]
0x140063b6a  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x140063b6f  xor     edx, edx; struct DXGADAPTER *
0x140063b71  lea     rcx, [rsp+178h+var_F0]; this
0x140063b79  call    ?Assign@DXGADAPTER_REFERENCE@@QEAAXPEAVDXGADAPTER@@@Z; DXGADAPTER_REFERENCE::Assign(DXGADAPTER *)
0x140063b7e  lea     rcx, [rsp+178h+var_120]; this
0x140063b83  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140063b88  cmp     [rsp+178h+var_110], dil
0x140063b8d  jz      short loc_140063BA8
0x140063b8f  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x140063b95  jz      short loc_140063BA8
0x140063b97  mov     r9d, [rsp+178h+var_120]
0x140063b9c  lea     rdx, EventProfilerExit
0x140063ba3  call    McTemplateK0q_EtwWriteTransfer
0x140063ba8  mov     eax, 0C0000017h
0x140063bad  jmp     loc_140064520
0x140063bb2  lea     rdx, [r12+10h]; Src
0x140063bb7  mov     r8, r15; Size
0x140063bba  mov     rcx, rsi; void *
0x140063bbd  call    RtlCopyFromUser
0x140063bc2  nop
0x140063bc3  xor     r8d, r8d; struct DXGADAPTER *
0x140063bc6  mov     rdx, r14; struct DXGADAPTER *
0x140063bc9  lea     rcx, [rsp+178h+var_C8]; this
0x140063bd1  call    ??0COREADAPTERACCESS@@QEAA@QEAVDXGADAPTER@@0@Z; COREADAPTERACCESS::COREADAPTERACCESS(DXGADAPTER * const,DXGADAPTER * const)
0x140063bd6  xor     edx, edx; char *
0x140063bd8  lea     rcx, [rsp+178h+var_C8]; this
0x140063be0  call    ?AcquireShared@COREADAPTERACCESS@@QEAAJPEBD@Z; COREADAPTERACCESS::AcquireShared(char const *)
0x140063be5  test    eax, eax
0x140063be7  jns     short loc_140063C30
0x140063be9  mov     r8d, [rsp+178h+var_E0.LowPart+8]
0x140063bf1  movsxd  rdx, [rsp+178h+var_E0.HighPart+8]
0x140063bf9  mov     ecx, 3
0x140063bfe  call    cs:__imp_WdLogSingleEntry2
0x140063c05  nop     dword ptr [rax+rax+00h]
0x140063c0a  mov     cs:WdLogGlobalForLineNumber, 73h ; 's'
0x140063c14  lea     rcx, [rsp+178h+var_C8]; this
0x140063c1c  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x140063c21  lea     rcx, [rsp+178h+var_108]
0x140063c26  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x140063c2b  jmp     loc_14006445A
0x140063c30  mov     rdx, [r14+0CB0h]
0x140063c37  test    rdx, rdx
0x140063c3a  jz      loc_14006434A
0x140063c40  cmp     [r14+5B0h], rdi
0x140063c47  jz      loc_1400642BB
0x140063c4d  mov     rdx, [rdx+68h]
0x140063c51  lea     rcx, [rsp+178h+var_100]
0x140063c56  call    ??0?$EXCLUSIVEACCESS@VVIDPN_MGR@@@@QEAA@QEAVVIDPN_MGR@@@Z; EXCLUSIVEACCESS<VIDPN_MGR>::EXCLUSIVEACCESS<VIDPN_MGR>(VIDPN_MGR * const)
0x140063c5b  movsxd  rdx, [rsp+178h+var_E0.LowPart]
0x140063c63  mov     ecx, edx
0x140063c65  sub     ecx, 1
0x140063c68  jz      loc_140064155
0x140063c6e  sub     ecx, 1
0x140063c71  jz      loc_14006410F
0x140063c77  sub     ecx, 1
0x140063c7a  jz      loc_140064095
0x140063c80  sub     ecx, 1
0x140063c83  jz      loc_140063E9A
0x140063c89  cmp     ecx, 1
0x140063c8c  jz      short loc_140063CBC
0x140063c8e  mov     ecx, 3
0x140063c93  call    cs:__imp_WdLogSingleEntry1
0x140063c9a  nop     dword ptr [rax+rax+00h]
0x140063c9f  mov     cs:WdLogGlobalForLineNumber, 154h
0x140063ca9  mov     rcx, [rsp+178h+var_100]
0x140063cae  add     rcx, 28h ; '('; this
0x140063cb2  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x140063cb7  jmp     loc_140063C14
0x140063cbc  cmp     [rsp+178h+var_E0.HighPart], 3Ch ; '<'
0x140063cc4  jnb     short loc_140063CEE
0x140063cc6  mov     r8d, [rsp+178h+var_E0.HighPart]
0x140063cce  mov     edx, 5
0x140063cd3  lea     ecx, [rdx-2]
0x140063cd6  call    cs:__imp_WdLogSingleEntry2
0x140063cdd  nop     dword ptr [rax+rax+00h]
0x140063ce2  mov     cs:WdLogGlobalForLineNumber, 118h
0x140063cec  jmp     short loc_140063CA9
0x140063cee  mov     ecx, [rsi+8]
0x140063cf1  lea     eax, [rcx+1Ch]
0x140063cf4  cmp     eax, r13d
0x140063cf7  jbe     short loc_140063D1C
0x140063cf9  mov     r8d, ecx
0x140063cfc  mov     edx, 5
0x140063d01  lea     ecx, [rdx-2]
0x140063d04  call    cs:__imp_WdLogSingleEntry2
0x140063d0b  nop     dword ptr [rax+rax+00h]
0x140063d10  mov     cs:WdLogGlobalForLineNumber, 124h
0x140063d1a  jmp     short loc_140063CA9
0x140063d1c  mov     edx, [rsi+0Ch]
0x140063d1f  cmp     edx, ecx
0x140063d21  jbe     short loc_140063D49
0x140063d23  mov     r8d, edx
0x140063d26  mov     edx, 5
0x140063d2b  lea     ecx, [rdx-2]
0x140063d2e  call    cs:__imp_WdLogSingleEntry2
0x140063d35  nop     dword ptr [rax+rax+00h]
0x140063d3a  mov     cs:WdLogGlobalForLineNumber, 12Ah
0x140063d44  jmp     loc_140063CA9
0x140063d49  mov     eax, [rsi+10h]
0x140063d4c  cmp     eax, ecx
0x140063d4e  jbe     short loc_140063D76
0x140063d50  mov     r8d, eax
0x140063d53  mov     edx, 5
0x140063d58  lea     ecx, [rdx-2]
0x140063d5b  call    cs:__imp_WdLogSingleEntry2
0x140063d62  nop     dword ptr [rax+rax+00h]
0x140063d67  mov     cs:WdLogGlobalForLineNumber, 130h
0x140063d71  jmp     loc_140063CA9
0x140063d76  mov     [rsp+178h+var_F8], 7Fh
0x140063d81  lea     rcx, [rsi+1Ch]
0x140063d85  lea     r9, [rsp+178h+var_F8]
0x140063d8d  call    ?SidebandMessageParser@@YAJPEAEIT_SB_MSG_PARSER_CONFIG@@PEAW4_SBMT_REQUEST_ID@@P6AJPEAX0I@Z3@Z; SidebandMessageParser(uchar *,uint,_SB_MSG_PARSER_CONFIG,_SBMT_REQUEST_ID *,long (*)(void *,uchar *,uint),void *)
0x140063d92  movsxd  r15, eax
0x140063d95  test    eax, eax
0x140063d97  jns     loc_140063E29
0x140063d9d  mov     r8, r15
0x140063da0  movsxd  rdx, [rsp+178h+var_E0.LowPart]
0x140063da8  mov     ecx, 3
0x140063dad  call    cs:__imp_WdLogSingleEntry2
0x140063db4  nop     dword ptr [rax+rax+00h]
0x140063db9  mov     cs:WdLogGlobalForLineNumber, 13Dh
0x140063dc3  mov     rcx, [rsp+178h+var_100]
0x140063dc8  add     rcx, 28h ; '('; this
0x140063dcc  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x140063dd1  lea     rcx, [rsp+178h+var_C8]; this
0x140063dd9  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x140063dde  lea     rcx, [rsp+178h+var_108]
0x140063de3  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x140063de8  xor     edx, edx; struct DXGADAPTER *
0x140063dea  lea     rcx, [rsp+178h+var_F0]; this
0x140063df2  call    ?Assign@DXGADAPTER_REFERENCE@@QEAAXPEAVDXGADAPTER@@@Z; DXGADAPTER_REFERENCE::Assign(DXGADAPTER *)
0x140063df7  lea     rcx, [rsp+178h+var_120]; this
0x140063dfc  call    ?PopProfilerEntry@DXGETWPROFILER_BASE@@QEAAXXZ; DXGETWPROFILER_BASE::PopProfilerEntry(void)
0x140063e01  cmp     [rsp+178h+var_110], dil
0x140063e06  jz      short loc_140063E21
0x140063e08  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, bl
0x140063e0e  jz      short loc_140063E21
0x140063e10  mov     r9d, [rsp+178h+var_120]
0x140063e15  lea     rdx, EventProfilerExit
0x140063e1c  call    McTemplateK0q_EtwWriteTransfer
0x140063e21  mov     eax, r15d
0x140063e24  jmp     loc_140064520
0x140063e29  mov     ecx, [rsp+178h+var_F8]
0x140063e30  test    ecx, ecx
0x140063e32  jz      short loc_140063E86
0x140063e34  sub     ecx, 1
0x140063e37  jz      short loc_140063E86
0x140063e39  sub     ecx, 11h
0x140063e3c  jz      short loc_140063E86
0x140063e3e  sub     ecx, 0Eh
0x140063e41  jz      short loc_140063E86
0x140063e43  sub     ecx, 2
0x140063e46  jz      short loc_140063E86
0x140063e48  cmp     ecx, 16h
0x140063e4b  jz      short loc_140063E86
0x140063e4d  mov     rcx, [rsp+178h+var_100]
0x140063e52  add     rcx, 28h ; '('; this
0x140063e56  call    ?Release@DXGFASTMUTEX@@QEAAXXZ; DXGFASTMUTEX::Release(void)
0x140063e5b  lea     rcx, [rsp+178h+var_C8]; this
0x140063e63  call    ??1COREADAPTERACCESS@@QEAA@XZ; COREADAPTERACCESS::~COREADAPTERACCESS(void)
0x140063e68  lea     rcx, [rsp+178h+var_108]
0x140063e6d  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x140063e72  xor     edx, edx; struct DXGADAPTER *
0x140063e74  lea     rcx, [rsp+178h+var_F0]; this
0x140063e7c  call    ?Assign@DXGADAPTER_REFERENCE@@QEAAXPEAVDXGADAPTER@@@Z; DXGADAPTER_REFERENCE::Assign(DXGADAPTER *)
0x140063e81  jmp     loc_1400644F1
0x140063e86  mov     rdx, rsi; struct _DXGKARG_DPSBMTRANSMISSION *
0x140063e89  mov     rcx, [r14+0CB0h]; this
0x140063e90  call    ?DdiDPSBMTransmission@ADAPTER_DISPLAY@@QEAAJPEAU_DXGKARG_DPSBMTRANSMISSION@@@Z; ADAPTER_DISPLAY::DdiDPSBMTransmission(_DXGKARG_DPSBMTRANSMISSION *)
0x140063e95  jmp     loc_140064199
0x140063e9a  cmp     [rsp+178h+var_E0.HighPart], 3Ch ; '<'
0x140063ea2  jnb     short loc_140063ECF
0x140063ea4  mov     r8d, [rsp+178h+var_E0.HighPart]
0x140063eac  mov     edx, 4
0x140063eb1  lea     ecx, [rdx-1]
0x140063eb4  call    cs:__imp_WdLogSingleEntry2
0x140063ebb  nop     dword ptr [rax+rax+00h]
0x140063ec0  mov     cs:WdLogGlobalForLineNumber, 0CCh
0x140063eca  jmp     loc_140063CA9
0x140063ecf  mov     ecx, [rsi+10h]
0x140063ed2  lea     eax, [rcx+28h]
0x140063ed5  cmp     eax, r13d
0x140063ed8  jbe     short loc_140063F00
0x140063eda  mov     r8d, ecx
0x140063edd  mov     edx, 4
0x140063ee2  lea     ecx, [rdx-1]
0x140063ee5  call    cs:__imp_WdLogSingleEntry2
0x140063eec  nop     dword ptr [rax+rax+00h]
0x140063ef1  mov     cs:WdLogGlobalForLineNumber, 0D8h
0x140063efb  jmp     loc_140063CA9
0x140063f00  mov     edx, [rsi+18h]
0x140063f03  cmp     edx, ecx
0x140063f05  jbe     short loc_140063F2D
0x140063f07  mov     r8d, edx
0x140063f0a  mov     edx, 4
0x140063f0f  lea     ecx, [rdx-1]
0x140063f12  call    cs:__imp_WdLogSingleEntry2
  ... truncated ...
```
