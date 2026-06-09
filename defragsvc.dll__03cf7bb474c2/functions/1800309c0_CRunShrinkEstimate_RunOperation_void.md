# CRunShrinkEstimate::RunOperation(void)

- ea: `0x1800309c0`
- end: `0x18003149f`
- name: `?RunOperation@CRunShrinkEstimate@@UEAAJXZ`
- size: `2783`
- prototype: `__int64 __fastcall(CRunShrinkEstimate *__hidden this)`
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting`

## callees

- `0x1800010dc`
- `0x180002314`
- `0x180006400`
- `0x18000ad50`
- `0x18000c794`
- `0x18000c848`
- `0x1800140bc`
- `0x1800156a0`
- `0x18002a4b0`
- `0x18002a86c`
- `0x18002dd8c`
- `0x18002f114`
- `0x1800309c0`
- `0x180038b14`
- `0x180038c3c`
- `0x180046494`
- `0x18004aa24`
- `0x18004b1cc`
- `0x18004b410`
- `0x18004b73c`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x180030b10`
- `ntdll!NtSetInformationThread` at `0x180030b4b`
- `ntdll!NtSetInformationThread` at `0x180030b10`
- `ntdll!NtSetInformationThread` at `0x180030b4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall CRunShrinkEstimate::RunOperation(CRunShrinkEstimate *this)
{
  int v2; // r15d
  unsigned int v3; // eax
  unsigned __int64 v4; // rcx
  __int16 v5; // ax
  unsigned int v6; // eax
  int v7; // eax
  struct IRunnableThread *v8; // rcx
  struct IRunnableThread *v9; // rcx
  struct IVolume *v10; // rdi
  __int64 (__fastcall *v11)(struct IVolume *, _QWORD, __int64 *); // rsi
  __int64 v12; // rcx
  struct IFreeSpaceManager *v13; // rcx
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  const unsigned __int16 *v17; // rsi
  __int64 v18; // rdi
  int v19; // eax
  const unsigned __int16 *v20; // rdi
  __int64 v21; // rax
  bool v22; // sf
  int v23; // eax
  __int64 v24; // rax
  unsigned __int64 v25; // rdi
  unsigned __int64 v26; // r9
  CSxGlobalTracer *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  unsigned __int64 v30; // r9
  unsigned __int64 v31; // rax
  unsigned __int64 v32; // r9
  __int64 v33; // rcx
  __int64 v34; // r8
  __int64 v35; // r9
  unsigned int v36; // ebx
  struct IFreeSpaceManager *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  struct IVolume *v40; // rcx
  struct IRunnableThread *v41; // rcx
  unsigned int v43; // [rsp+60h] [rbp-A0h] BYREF
  struct IVolume *v44; // [rsp+68h] [rbp-98h] BYREF
  int v45; // [rsp+70h] [rbp-90h] BYREF
  __int16 v46; // [rsp+74h] [rbp-8Ch]
  __int16 v47; // [rsp+76h] [rbp-8Ah]
  int v48; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v50; // [rsp+B8h] [rbp-48h] BYREF
  struct IFreeSpaceManager *v51; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v52; // [rsp+C8h] [rbp-38h] BYREF
  struct IRunnableThread *v53; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v54[2]; // [rsp+D8h] [rbp-28h] BYREF
  int ThreadInformation; // [rsp+DCh] [rbp-24h] BYREF
  int v56; // [rsp+E0h] [rbp-20h] BYREF
  int v57; // [rsp+E4h] [rbp-1Ch] BYREF
  int v58; // [rsp+E8h] [rbp-18h] BYREF
  int v59; // [rsp+ECh] [rbp-14h] BYREF
  int v60; // [rsp+F0h] [rbp-10h] BYREF
  int v61; // [rsp+F4h] [rbp-Ch] BYREF
  int v62; // [rsp+F8h] [rbp-8h] BYREF
  int v63; // [rsp+FCh] [rbp-4h] BYREF
  int v64; // [rsp+100h] [rbp+0h] BYREF
  int v65; // [rsp+104h] [rbp+4h] BYREF
  __int64 v66; // [rsp+108h] [rbp+8h] BYREF
  const unsigned __int16 *v67[2]; // [rsp+110h] [rbp+10h] BYREF
  struct _GUID *v68; // [rsp+120h] [rbp+20h] BYREF
  __int64 v69; // [rsp+128h] [rbp+28h] BYREF
  struct _GUID v70; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v71[3]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v72; // [rsp+170h] [rbp+70h]
  int v73; // [rsp+178h] [rbp+78h]
  __int16 v74; // [rsp+17Ch] [rbp+7Ch]
  __int128 v75; // [rsp+190h] [rbp+90h]
  __int64 v76; // [rsp+1A0h] [rbp+A0h]
  __int64 v77; // [rsp+1A8h] [rbp+A8h]
  __int64 v78; // [rsp+1B0h] [rbp+B0h]
  __int64 v79; // [rsp+1B8h] [rbp+B8h]
  int v80; // [rsp+1C0h] [rbp+C0h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v45, "CRunShrinkEstimate::RunOperation", 51, 1);
  v53 = 0;
  v44 = 0;
  v52 = 0;
  v49 = 0;
  v43 = 0;
  v48 = 0;
  v51 = 0;
  v61 = 0;
  v60 = 0;
  v57 = 0;
  v62 = 0;
  v2 = 0;
  v58 = 0;
  v66 = 0;
  v50 = 0;
  v56 = 0;
  ThreadInformation = 2;
  v59 = 2;
  memset(v71, 0, sizeof(v71));
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v70 = 0;
  DfStartTracing();
  (*(void (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 5) + 152LL))(*((_QWORD *)this + 5), &v70);
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_8d35fd7dedcd3e3933bba2ff422c3af6_Traceguids);
  ThreadInformation = 2;
  v3 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIoPriority, &ThreadInformation, 4u);
  v45 = HRESULTFromNTSTATUS(v3);
  v5 = 95;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 95;
  v56 = 2;
  v6 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPriority, &v56, 4u);
  v45 = HRESULTFromNTSTATUS(v6);
  v5 = 102;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 102;
  v45 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 5) + 176LL))(*((_QWORD *)this + 5), &v59);
  v5 = 104;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 104;
  v45 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 184LL))(*((_QWORD *)this + 5), 1);
  v5 = 105;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 105;
  v45 = CDefragOperation::_CreateVolumeForFileSystem(this, &v44);
  v5 = 114;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 114;
  v45 = (*(__int64 (__fastcall **)(struct IVolume *, int *, int *, int *, int *))(*(_QWORD *)v44 + 192LL))(
          v44,
          &v62,
          &v61,
          &v60,
          &v57);
  v5 = 117;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 117;
  if ( !v57 )
  {
    v45 = -1996488672;
    v5 = 121;
LABEL_5:
    v47 = v5;
    goto LABEL_86;
  }
  v7 = (*(__int64 (__fastcall **)(struct IVolume *))(*(_QWORD *)v44 + 296LL))(v44);
  if ( v7 < 0
    && WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_8d35fd7dedcd3e3933bba2ff422c3af6_Traceguids, (unsigned int)v7);
  }
  v45 = CDefragOperation::_SetPhase(this, 1u);
  v5 = 142;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 142;
  v8 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v45 = CRunAnalysis::CreateInstance(0, 0, v44, &v53, 0, 0, 0, 0);
  v5 = 145;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 145;
  v45 = (*(__int64 (__fastcall **)(struct IRunnableThread *, _QWORD))(*(_QWORD *)v53 + 24LL))(
          v53,
          *((_QWORD *)this + 5));
  v5 = 148;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 148;
  v9 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v45 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(
          *((_QWORD *)this + 6),
          (char *)this + 56);
  v5 = 154;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 154;
  v10 = v44;
  v11 = *(__int64 (__fastcall **)(struct IVolume *, _QWORD, __int64 *))(*(_QWORD *)v44 + 104LL);
  v12 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v45 = v11(v10, 0, &v52);
  v5 = 157;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 157;
  v13 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v45 = CFreeSpaceManager::CreateInstance(*((unsigned __int16 **)this + 87), *((_QWORD *)this + 18), &v51);
  v5 = 163;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 163;
  v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v52 + 48LL))(v52, &v43);
  v4 = (unsigned int)v14;
  v45 = v14;
  v22 = v14 < 0;
  v5 = 165;
  if ( v22 )
    goto LABEL_5;
  while ( 1 )
  {
    v46 = v5;
    if ( (_DWORD)v4 == 1 )
      break;
    v15 = *(_QWORD *)v44;
    if ( v49 )
    {
      v45 = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD, __int64, _QWORD))(v15 + 56))(v44, v43, v49, 0);
      if ( v45 < 0 )
      {
        v47 = 170;
        goto LABEL_86;
      }
      v46 = 170;
    }
    else
    {
      v45 = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD, _QWORD, __int64 *))(v15 + 56))(v44, v43, 0, &v49);
      v5 = 174;
      if ( v45 < 0 )
        goto LABEL_5;
      v46 = 174;
    }
    v45 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v49 + 64LL))(v49, 1, &v48);
    if ( v45 < 0 )
    {
      v47 = 177;
      goto LABEL_86;
    }
    v46 = 177;
    if ( !v48 )
    {
      v45 = (*(__int64 (__fastcall **)(__int64, struct IFreeSpaceManager *))(*(_QWORD *)v49 + 192LL))(v49, v51);
      if ( v45 < 0 )
      {
        v47 = 182;
        goto LABEL_86;
      }
      v46 = 182;
    }
    v16 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v52 + 56LL))(v52, &v43);
    v4 = (unsigned int)v16;
    v45 = v16;
    v22 = v16 < 0;
    v5 = 185;
    if ( v22 )
      goto LABEL_5;
  }
  v45 = 0;
  v45 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, unsigned __int64 *))(*(_QWORD *)v51 + 88LL))(v51, &v50);
  v5 = 190;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 190;
  v17 = (const unsigned __int16 *)(v50 + 1);
  if ( v50 + 1 <= *((_QWORD *)this + 17) )
    v17 = (const unsigned __int16 *)*((_QWORD *)this + 17);
  v18 = *((_QWORD *)this + 18);
  v19 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v52 + 48LL))(v52, &v43);
  v4 = (unsigned int)v19;
  v45 = v19;
  v22 = v19 < 0;
  v5 = 202;
  if ( v22 )
    goto LABEL_5;
  v20 = (const unsigned __int16 *)(v18 - 1);
  while ( 1 )
  {
    v46 = v5;
    if ( (_DWORD)v4 == 1 )
      break;
    v21 = *(_QWORD *)v44;
    if ( v49 )
    {
      v45 = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD, __int64, _QWORD))(v21 + 56))(v44, v43, v49, 0);
      v22 = v45 < 0;
      v5 = 207;
    }
    else
    {
      v45 = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD, _QWORD, __int64 *))(v21 + 56))(v44, v43, 0, &v49);
      v22 = v45 < 0;
      v5 = 211;
    }
    if ( v22 )
      goto LABEL_5;
    v46 = v5;
    v45 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v49 + 64LL))(v49, 1, &v48);
    v5 = 216;
    if ( v45 < 0 )
      goto LABEL_5;
    v46 = 216;
    if ( !v48 )
    {
      v67[0] = v17;
      v67[1] = v20;
      v45 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **, int *))(*(_QWORD *)v49 + 152LL))(
              v49,
              v67,
              &v58);
      v5 = 220;
      if ( v45 < 0 )
        goto LABEL_5;
      v46 = 220;
      if ( v58 )
      {
        v45 = (*(__int64 (__fastcall **)(struct IVolume *, _QWORD, __int64))(*(_QWORD *)v44 + 312LL))(v44, v43, v49);
        v5 = 224;
        if ( v45 < 0 )
          goto LABEL_5;
        v46 = 224;
        v45 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v49 + 64LL))(v49, 1, &v48);
        v5 = 226;
        if ( v45 < 0 )
          goto LABEL_5;
        v46 = 226;
        if ( v48 )
        {
          v45 = (*(__int64 (__fastcall **)(__int64, struct IFreeSpaceManager *))(*(_QWORD *)v49 + 200LL))(v49, v51);
          v5 = 231;
          if ( v45 < 0 )
            goto LABEL_5;
          v46 = 231;
        }
      }
    }
    v23 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v52 + 56LL))(v52, &v43);
    v4 = (unsigned int)v23;
    v45 = v23;
    v22 = v23 < 0;
    v5 = 236;
    if ( v22 )
      goto LABEL_5;
  }
  v45 = 0;
  v45 = (*(__int64 (__fastcall **)(struct IFreeSpaceManager *, unsigned __int64 *))(*(_QWORD *)v51 + 88LL))(v51, &v50);
  v5 = 241;
  if ( v45 < 0 )
    goto LABEL_5;
  v46 = 241;
  v24 = *((_QWORD *)this + 17);
  v25 = v24 - 1;
  if ( !v24 )
    v25 = 0;
  if ( (int)SxFileLoggingSupport::Initialize(
              (__int64)v71,
              *((const unsigned __int16 **)this + 87),
              *((_QWORD *)this + 89),
              v50,
              v25,
              (__int64)this + 56,
              1) >= 0 )
  {
    SxFileLoggingSupport::LogShrinkInhibitorFileInfo(
      (SxFileLoggingSupport *)v71,
      (struct CSxFunctionTracer *)&v45,
      0x105u,
      0x40000103u,
      4u);
    SxFileLoggingSupport::LogShrinkInhibitorTelemetry((SxFileLoggingSupport *)v71, &v70);
  }
  v26 = v50;
  if ( v25 <= v50 )
  {
    v2 = 1;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSxGlobalTracer *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
    {
      goto LABEL_81;
    }
    v28 = 13;
  }
  else
  {
    v26 = v25;
    v50 = v25;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CSxGlobalTracer *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
    {
      goto LABEL_81;
    }
    v28 = 12;
  }
  WPP_SF_(*((_QWORD *)v27 + 2), v28, WPP_8d35fd7dedcd3e3933bba2ff422c3af6_Traceguids);
  v26 = v50;
LABEL_81:
  v29 = *((unsigned int *)this + 38);
  v30 = 0x3200000 / (unsigned int)v29 + v26;
  v50 = v30;
  v31 = *((_QWORD *)this + 18);
  if ( v30 >= v31 )
  {
    v30 = v31 - 1;
    v50 = v31 - 1;
  }
  v32 = v29 * (v31 + ~v30);
  *((_QWORD *)this + 34) = v32;
  v4 = (unsigned __int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
  {
    WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_8d35fd7dedcd3e3933bba2ff422c3af6_Traceguids, v32);
  }
LABEL_86:
  if ( v59 != 2 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 184LL))(*((_QWORD *)this + 5));
  if ( dword_1800840E0 && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    v63 = v45;
    v54[0] = v47;
    v68 = &v70;
    v64 = 2;
    v65 = v2;
    v69 = *((_QWORD *)this + 34);
    v67[0] = *((const unsigned __int16 **)this + 87);
    v66 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v33,
      (__int64)&dword_180078194,
      v34,
      v35,
      (__int64)&v66,
      v67,
      (__int64)&v69,
      (__int64)&v65,
      (__int64)&v64,
      (__int64 *)&v68,
      (__int64)v54,
      (__int64)&v63);
  }
  Log_DF_OPTIMIZE_RESULT(
    (struct CSxFunctionTracer *)&v45,
    0x137u,
    *((const unsigned __int16 **)this + 89),
    0x328u,
    v45,
    0);
  DfStopTracing();
  v36 = v45;
  SxFileLoggingSupport::~SxFileLoggingSupport((void **)v71);
  v37 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v37 + 16LL))(v37);
  }
  v38 = v49;
  if ( v49 )
  {
    v49 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  v39 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  }
  v40 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v41 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v41 + 16LL))(v41);
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v45);
  return v36;
}

```

## disassembly

```asm
0x1800309c0  push    rbp
0x1800309c2  push    rbx
0x1800309c3  push    rsi
0x1800309c4  push    rdi
0x1800309c5  push    r12
0x1800309c7  push    r13
0x1800309c9  push    r14
0x1800309cb  push    r15
0x1800309cd  lea     rbp, [rsp-0E8h]
0x1800309d5  sub     rsp, 1E8h
0x1800309dc  mov     rax, cs:__security_cookie
0x1800309e3  xor     rax, rsp
0x1800309e6  mov     [rbp+120h+var_50], rax
0x1800309ed  mov     rbx, rcx
0x1800309f0  mov     esi, 1
0x1800309f5  mov     r9d, esi; unsigned __int16
0x1800309f8  lea     r8d, [rsi+32h]; unsigned __int16
0x1800309fc  lea     rdx, aCrunshrinkesti_0; "CRunShrinkEstimate::RunOperation"
0x180030a03  lea     rcx, [rsp+220h+var_1B0]; this
0x180030a08  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180030a0d  nop
0x180030a0e  xor     r12d, r12d
0x180030a11  mov     [rbp+120h+var_150], r12
0x180030a15  mov     [rsp+220h+var_1B8], r12
0x180030a1a  mov     [rbp+120h+var_158], r12
0x180030a1e  mov     [rbp+120h+var_170], r12
0x180030a22  mov     [rsp+220h+var_1C0], r12d
0x180030a27  mov     [rbp+120h+var_178], r12d
0x180030a2b  mov     [rbp+120h+var_160], r12
0x180030a2f  mov     [rbp+120h+var_12C], r12d
0x180030a33  mov     [rbp+120h+var_130], r12d
0x180030a37  mov     [rbp+120h+var_13C], r12d
0x180030a3b  mov     [rbp+120h+var_128], r12d
0x180030a3f  mov     r15d, r12d
0x180030a42  mov     [rbp+120h+var_138], r12d
0x180030a46  mov     [rbp+120h+var_118], r12
0x180030a4a  mov     [rbp+120h+var_168], r12
0x180030a4e  mov     [rbp+120h+var_140], r12d
0x180030a52  lea     edi, [rsi+1]
0x180030a55  mov     [rbp+120h+ThreadInformation], edi
0x180030a58  mov     [rbp+120h+var_134], edi
0x180030a5b  xorps   xmm0, xmm0
0x180030a5e  movdqa  [rbp+120h+var_E0], xmm0
0x180030a63  xorps   xmm1, xmm1
0x180030a66  movups  [rbp+120h+var_D0], xmm1
0x180030a6a  movups  [rbp+120h+var_C0], xmm1
0x180030a6e  mov     [rbp+120h+var_B0], r12
0x180030a72  mov     [rbp+120h+var_A8], r12d
0x180030a76  mov     [rbp+120h+var_A4], r12w
0x180030a7b  movdqa  [rbp+120h+var_90], xmm0
0x180030a83  mov     [rbp+120h+var_80], r12
0x180030a8a  mov     [rbp+120h+var_78], r12
0x180030a91  mov     [rbp+120h+var_70], r12
0x180030a98  mov     [rbp+120h+var_68], r12
0x180030a9f  mov     [rbp+120h+var_60], r12d
0x180030aa6  movups  xmmword ptr [rbp+120h+var_F0.Data1], xmm0
0x180030aaa  call    ?DfStartTracing@@YAJXZ; DfStartTracing(void)
0x180030aaf  mov     rcx, [rbx+28h]
0x180030ab3  mov     rax, [rcx]
0x180030ab6  lea     rdx, [rbp+120h+var_F0]
0x180030aba  mov     rax, [rax+98h]
0x180030ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ac6  lea     r14, WPP_GLOBAL_Control
0x180030acd  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ad4  cmp     rcx, r14
0x180030ad7  jz      short loc_180030AF2
0x180030ad9  test    byte ptr [rcx+1Ch], 10h
0x180030add  jz      short loc_180030AF2
0x180030adf  lea     edx, [rsi+9]
0x180030ae2  lea     r8, WPP_8d35fd7dedcd3e3933bba2ff422c3af6_Traceguids
0x180030ae9  mov     rcx, [rcx+10h]
0x180030aed  call    WPP_SF_
0x180030af2  mov     [rbp+120h+ThreadInformation], edi
0x180030af5  mov     r13d, 4
0x180030afb  mov     r9d, r13d; ThreadInformationLength
0x180030afe  lea     r8, [rbp+120h+ThreadInformation]; ThreadInformation
0x180030b02  lea     edx, [r13+12h]; ThreadInformationClass
0x180030b06  mov     rdi, 0FFFFFFFFFFFFFFFEh
0x180030b0d  mov     rcx, rdi; ThreadHandle
0x180030b10  call    cs:__imp_NtSetInformationThread
0x180030b16  mov     ecx, eax
0x180030b18  call    HRESULTFromNTSTATUS
0x180030b1d  mov     [rsp+220h+var_1B0], eax
0x180030b21  test    eax, eax
0x180030b23  lea     eax, [rdi+61h]
0x180030b26  jns     short loc_180030B32
0x180030b28  mov     [rsp+220h+var_1AA], ax
0x180030b2d  jmp     loc_1800312DB
0x180030b32  mov     [rsp+220h+var_1AC], ax
0x180030b37  mov     eax, 2
0x180030b3c  mov     [rbp+120h+var_140], eax
0x180030b3f  mov     r9d, r13d; ThreadInformationLength
0x180030b42  lea     r8, [rbp+120h+var_140]; ThreadInformation
0x180030b46  mov     edx, eax; ThreadInformationClass
0x180030b48  mov     rcx, rdi; ThreadHandle
0x180030b4b  call    cs:__imp_NtSetInformationThread
0x180030b51  mov     ecx, eax
0x180030b53  call    HRESULTFromNTSTATUS
0x180030b58  mov     [rsp+220h+var_1B0], eax
0x180030b5c  test    eax, eax
0x180030b5e  mov     eax, 66h ; 'f'
0x180030b63  js      short loc_180030B28
0x180030b65  mov     [rsp+220h+var_1AC], ax
0x180030b6a  mov     rcx, [rbx+28h]
0x180030b6e  mov     rax, [rcx]
0x180030b71  lea     rdx, [rbp+120h+var_134]
0x180030b75  mov     rax, [rax+0B0h]
0x180030b7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b81  mov     [rsp+220h+var_1B0], eax
0x180030b85  test    eax, eax
0x180030b87  mov     eax, 68h ; 'h'
0x180030b8c  js      short loc_180030B28
0x180030b8e  mov     [rsp+220h+var_1AC], ax
0x180030b93  mov     rcx, [rbx+28h]
0x180030b97  mov     rax, [rcx]
0x180030b9a  mov     edx, esi
0x180030b9c  mov     rax, [rax+0B8h]
0x180030ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ba8  mov     [rsp+220h+var_1B0], eax
0x180030bac  test    eax, eax
0x180030bae  mov     eax, 69h ; 'i'
0x180030bb3  js      loc_180030B28
0x180030bb9  mov     [rsp+220h+var_1AC], ax
0x180030bbe  mov     rcx, [rsp+220h+var_1B8]
0x180030bc3  test    rcx, rcx
0x180030bc6  jz      short loc_180030BDA
0x180030bc8  mov     [rsp+220h+var_1B8], r12
0x180030bcd  mov     rax, [rcx]
0x180030bd0  mov     rax, [rax+10h]
0x180030bd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bd9  nop
0x180030bda  lea     rdx, [rsp+220h+var_1B8]; struct IVolume **
0x180030bdf  mov     rcx, rbx; this
0x180030be2  call    ?_CreateVolumeForFileSystem@CDefragOperation@@IEAAJPEAPEAUIVolume@@@Z; CDefragOperation::_CreateVolumeForFileSystem(IVolume * *)
0x180030be7  mov     [rsp+220h+var_1B0], eax
0x180030beb  test    eax, eax
0x180030bed  mov     eax, 72h ; 'r'
0x180030bf2  js      loc_180030B28
0x180030bf8  mov     [rsp+220h+var_1AC], ax
0x180030bfd  mov     rcx, [rsp+220h+var_1B8]
0x180030c02  mov     rax, [rcx]
0x180030c05  lea     rdx, [rbp+120h+var_13C]
0x180030c09  mov     [rsp+220h+var_200], rdx
0x180030c0e  lea     r9, [rbp+120h+var_130]
0x180030c12  lea     r8, [rbp+120h+var_12C]
0x180030c16  lea     rdx, [rbp+120h+var_128]
0x180030c1a  mov     rax, [rax+0C0h]
0x180030c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c26  mov     [rsp+220h+var_1B0], eax
0x180030c2a  test    eax, eax
0x180030c2c  mov     eax, 75h ; 'u'
0x180030c31  js      loc_180030B28
0x180030c37  mov     [rsp+220h+var_1AC], ax
0x180030c3c  cmp     [rbp+120h+var_13C], r12d
0x180030c40  jnz     short loc_180030C54
0x180030c42  mov     [rsp+220h+var_1B0], 89000020h
0x180030c4a  mov     eax, 79h ; 'y'
0x180030c4f  jmp     loc_180030B28
0x180030c54  mov     rcx, [rsp+220h+var_1B8]
0x180030c59  mov     rax, [rcx]
0x180030c5c  mov     rax, [rax+128h]
0x180030c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030c68  test    eax, eax
0x180030c6a  jns     short loc_180030C99
0x180030c6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030c73  cmp     rcx, r14
0x180030c76  jz      short loc_180030C99
0x180030c78  test    dword ptr [rcx+1Ch], 400000h
0x180030c7f  jz      short loc_180030C99
0x180030c81  mov     edx, 0Bh
0x180030c86  mov     r9d, eax
0x180030c89  lea     r8, WPP_8d35fd7dedcd3e3933bba2ff422c3af6_Traceguids
0x180030c90  mov     rcx, [rcx+10h]
0x180030c94  call    WPP_SF_d
0x180030c99  mov     edx, esi
0x180030c9b  mov     rcx, rbx
0x180030c9e  call    ?_SetPhase@CDefragOperation@@IEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0001@@@Z; CDefragOperation::_SetPhase(__MIDL___MIDL_itf_dfengine_0000_0000_0001)
0x180030ca3  mov     [rsp+220h+var_1B0], eax
0x180030ca7  test    eax, eax
0x180030ca9  mov     eax, 8Eh
0x180030cae  js      loc_180030B28
0x180030cb4  mov     [rsp+220h+var_1AC], ax
0x180030cb9  mov     rcx, [rbp+120h+var_150]
0x180030cbd  test    rcx, rcx
0x180030cc0  jz      short loc_180030CD3
0x180030cc2  mov     [rbp+120h+var_150], r12
0x180030cc6  mov     rax, [rcx]
0x180030cc9  mov     rax, [rax+10h]
0x180030ccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cd2  nop
0x180030cd3  mov     [rsp+220h+var_1E8], r12; unsigned __int16 *
0x180030cd8  mov     [rsp+220h+var_1F0], r12; unsigned __int64 *
0x180030cdd  mov     [rsp+220h+var_1F8], r12; unsigned __int64 *
0x180030ce2  mov     [rsp+220h+var_200], r12; struct __MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *
0x180030ce7  lea     r9, [rbp+120h+var_150]; struct IRunnableThread **
0x180030ceb  mov     r8, [rsp+220h+var_1B8]; struct IVolume *
0x180030cf0  xor     edx, edx; int
0x180030cf2  xor     ecx, ecx; int
0x180030cf4  call    ?CreateInstance@CRunAnalysis@@SAJHHPEAUIVolume@@PEAPEAUIRunnableThread@@PEAU__MIDL___MIDL_itf_dfengine_np_0000_0000_0001@@PEA_K3PEAG@Z; CRunAnalysis::CreateInstance(int,int,IVolume *,IRunnableThread * *,__MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *,unsigned __int64 *,unsigned __int64 *,ushort *)
0x180030cf9  mov     [rsp+220h+var_1B0], eax
0x180030cfd  test    eax, eax
0x180030cff  mov     eax, 91h
0x180030d04  js      loc_180030B28
0x180030d0a  mov     [rsp+220h+var_1AC], ax
0x180030d0f  mov     rcx, [rbp+120h+var_150]
0x180030d13  mov     rax, [rcx]
0x180030d16  mov     rdx, [rbx+28h]
0x180030d1a  mov     rax, [rax+18h]
0x180030d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d23  mov     [rsp+220h+var_1B0], eax
0x180030d27  test    eax, eax
0x180030d29  mov     eax, 94h
0x180030d2e  js      loc_180030B28
0x180030d34  mov     [rsp+220h+var_1AC], ax
0x180030d39  mov     rcx, [rbp+120h+var_150]
0x180030d3d  test    rcx, rcx
0x180030d40  jz      short loc_180030D53
0x180030d42  mov     [rbp+120h+var_150], r12
0x180030d46  mov     rax, [rcx]
0x180030d49  mov     rax, [rax+10h]
0x180030d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d52  nop
0x180030d53  mov     rcx, [rbx+30h]
0x180030d57  lea     r14, [rbx+38h]
0x180030d5b  mov     rax, [rcx]
0x180030d5e  mov     rdx, r14
0x180030d61  mov     rax, [rax+18h]
0x180030d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d6a  mov     [rsp+220h+var_1B0], eax
0x180030d6e  test    eax, eax
0x180030d70  mov     eax, 9Ah
0x180030d75  js      loc_180030B28
0x180030d7b  mov     [rsp+220h+var_1AC], ax
0x180030d80  mov     rdi, [rsp+220h+var_1B8]
0x180030d85  mov     rax, [rdi]
0x180030d88  mov     rsi, [rax+68h]
0x180030d8c  mov     rcx, [rbp+120h+var_158]
0x180030d90  test    rcx, rcx
0x180030d93  jz      short loc_180030DA6
0x180030d95  mov     [rbp+120h+var_158], r12
0x180030d99  mov     rdx, [rcx]
0x180030d9c  mov     rax, [rdx+10h]
0x180030da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030da5  nop
0x180030da6  lea     r8, [rbp+120h+var_158]
0x180030daa  xor     edx, edx
0x180030dac  mov     rcx, rdi
0x180030daf  mov     rax, rsi
0x180030db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030db7  mov     [rsp+220h+var_1B0], eax
0x180030dbb  test    eax, eax
0x180030dbd  mov     eax, 9Dh
0x180030dc2  js      loc_180030B28
0x180030dc8  mov     [rsp+220h+var_1AC], ax
0x180030dcd  mov     rcx, [rbp+120h+var_160]
0x180030dd1  test    rcx, rcx
0x180030dd4  jz      short loc_180030DE7
0x180030dd6  mov     [rbp+120h+var_160], r12
0x180030dda  mov     rax, [rcx]
0x180030ddd  mov     rax, [rax+10h]
0x180030de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030de6  nop
0x180030de7  lea     r8, [rbp+120h+var_160]; struct IFreeSpaceManager **
0x180030deb  mov     rdx, [rbx+90h]; unsigned __int64
0x180030df2  mov     rcx, [rbx+2B8h]; unsigned __int16 *
0x180030df9  call    ?CreateInstance@CFreeSpaceManager@@SAJPEAG_KPEAPEAUIFreeSpaceManager@@@Z; CFreeSpaceManager::CreateInstance(ushort *,unsigned __int64,IFreeSpaceManager * *)
0x180030dfe  mov     [rsp+220h+var_1B0], eax
0x180030e02  test    eax, eax
0x180030e04  mov     eax, 0A3h
0x180030e09  js      loc_180030B28
0x180030e0f  mov     [rsp+220h+var_1AC], ax
0x180030e14  mov     rcx, [rbp+120h+var_158]
0x180030e18  mov     rax, [rcx]
0x180030e1b  lea     rdx, [rsp+220h+var_1C0]
0x180030e20  mov     rax, [rax+30h]
0x180030e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e29  mov     ecx, eax
0x180030e2b  mov     [rsp+220h+var_1B0], eax
0x180030e2f  test    eax, eax
0x180030e31  mov     eax, 0A5h
0x180030e36  js      loc_180030B28
0x180030e3c  lea     edi, [rax+5]
0x180030e3f  lea     esi, [rax+11h]
0x180030e42  lea     r13d, [rax+0Ch]
0x180030e46  mov     [rsp+220h+var_1AC], ax
0x180030e4b  cmp     ecx, 1
0x180030e4e  jz      loc_180030F4F
0x180030e54  mov     r8, [rbp+120h+var_170]
0x180030e58  mov     rcx, [rsp+220h+var_1B8]
0x180030e5d  mov     rax, [rcx]
0x180030e60  test    r8, r8
0x180030e63  jz      short loc_180030E88
0x180030e65  xor     r9d, r9d
0x180030e68  mov     edx, [rsp+220h+var_1C0]
0x180030e6c  mov     rax, [rax+38h]
0x180030e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030e75  mov     [rsp+220h+var_1B0], eax
0x180030e79  test    eax, eax
0x180030e7b  js      loc_180030F30
0x180030e81  mov     [rsp+220h+var_1AC], di
  ... truncated ...
```
