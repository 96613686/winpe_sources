# CRunShrink::RunOperation(void)

- ea: `0x18005a820`
- end: `0x18005b203`
- name: `?RunOperation@CRunShrink@@UEAAJXZ`
- size: `2531`
- prototype: `__int64 __fastcall(CRunShrink *__hidden this)`
- caller_count: `0`
- callee_count: `24`
- tags: `loader_planting`

## callees

- `0x1800010dc`
- `0x180002420`
- `0x180006400`
- `0x18000ad50`
- `0x18000c794`
- `0x18000c848`
- `0x1800140bc`
- `0x1800156a0`
- `0x18001f22c`
- `0x18002a4b0`
- `0x18002a86c`
- `0x18002dd8c`
- `0x18002f114`
- `0x180037a1c`
- `0x180038b14`
- `0x180038c3c`
- `0x18004aa24`
- `0x18004b1cc`
- `0x18004b410`
- `0x18004b73c`
- `0x18005a820`
- `0x18005b20c`
- `0x180067b30`
- `0x18006a010`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18005a988`
- `ntdll!NtSetInformationThread` at `0x18005a9c2`
- `ntdll!NtSetInformationThread` at `0x18005a988`
- `ntdll!NtSetInformationThread` at `0x18005a9c2`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CRunShrink::RunOperation(CRunShrink *this)
{
  int v2; // r13d
  unsigned __int64 v3; // rsi
  unsigned __int64 v4; // rcx
  __int16 v5; // ax
  unsigned int v6; // eax
  int v7; // eax
  unsigned int v8; // eax
  __int64 v9; // r14
  __int64 v10; // r12
  struct IRunnableThread *v11; // rcx
  struct IRunnableThread *v12; // rcx
  __int64 v13; // rdi
  __int64 v14; // r14
  __int64 v15; // rdi
  struct IRunnableThread *v16; // rcx
  struct IRunnableThread *v17; // rcx
  struct IFreeSpaceManager *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // r9
  unsigned __int64 v21; // rdi
  CSxGlobalTracer *v22; // r10
  __int64 v23; // rcx
  unsigned __int64 v24; // rdi
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  unsigned int v28; // ebx
  struct IFreeSpaceManager *v29; // rcx
  struct IVolume *v30; // rcx
  struct IRunnableThread *v31; // rcx
  struct IVolume *v33; // [rsp+60h] [rbp-A0h] BYREF
  struct IRunnableThread *v34; // [rsp+68h] [rbp-98h] BYREF
  int v35; // [rsp+70h] [rbp-90h] BYREF
  __int16 v36; // [rsp+74h] [rbp-8Ch]
  __int16 v37; // [rsp+76h] [rbp-8Ah]
  __int16 v38; // [rsp+A8h] [rbp-58h] BYREF
  struct IFreeSpaceManager *v39; // [rsp+B0h] [rbp-50h] BYREF
  int ThreadInformation; // [rsp+B8h] [rbp-48h] BYREF
  int v41; // [rsp+BCh] [rbp-44h] BYREF
  int v42; // [rsp+C0h] [rbp-40h] BYREF
  int v43; // [rsp+C4h] [rbp-3Ch] BYREF
  __int64 v44; // [rsp+C8h] [rbp-38h] BYREF
  int v45; // [rsp+D0h] [rbp-30h] BYREF
  int v46; // [rsp+D4h] [rbp-2Ch] BYREF
  int v47; // [rsp+D8h] [rbp-28h] BYREF
  int v48; // [rsp+DCh] [rbp-24h] BYREF
  int v49[4]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v50[2]; // [rsp+F0h] [rbp-10h] BYREF
  struct _GUID *v51; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int64 v52; // [rsp+108h] [rbp+8h] BYREF
  const unsigned __int16 *v53; // [rsp+110h] [rbp+10h] BYREF
  struct _GUID v54; // [rsp+118h] [rbp+18h] BYREF
  _OWORD v55[3]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v56; // [rsp+160h] [rbp+60h]
  int v57; // [rsp+168h] [rbp+68h]
  __int16 v58; // [rsp+16Ch] [rbp+6Ch]
  __int128 v59; // [rsp+180h] [rbp+80h]
  __int64 v60; // [rsp+190h] [rbp+90h]
  __int64 v61; // [rsp+198h] [rbp+98h]
  __int64 v62; // [rsp+1A0h] [rbp+A0h]
  __int64 v63; // [rsp+1A8h] [rbp+A8h]
  int v64; // [rsp+1B0h] [rbp+B0h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v35, "CRunShrink::RunOperation", 297, 1);
  v34 = 0;
  v33 = 0;
  v46 = 0;
  v45 = 0;
  v42 = 0;
  v47 = 0;
  v2 = 0;
  v41 = 0;
  ThreadInformation = 2;
  v43 = 2;
  v39 = 0;
  v44 = 0;
  v3 = 0;
  memset(v55, 0, sizeof(v55));
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v54 = 0;
  (*(void (__fastcall **)(_QWORD, struct _GUID *))(**((_QWORD **)this + 5) + 152LL))(*((_QWORD *)this + 5), &v54);
  DfStartTracing();
  v5 = 328;
  if ( *((_QWORD *)this + 95) <= *((_QWORD *)this + 96) )
  {
    v35 = 0;
    v36 = 328;
    if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_9b40e9251fdc3d76fa0fc4f6af85682a_Traceguids);
    }
    ThreadInformation = 2;
    v6 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadIoPriority, &ThreadInformation, 4u);
    v7 = HRESULTFromNTSTATUS(v6);
    v35 = v7;
    v4 = 342;
    if ( v7 >= 0 )
    {
      v36 = 342;
      v41 = 2;
      v8 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadPriority, &v41, 4u);
      v7 = HRESULTFromNTSTATUS(v8);
      v35 = v7;
      v4 = 349;
      if ( v7 >= 0 )
      {
        v36 = 349;
        v7 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 5) + 176LL))(*((_QWORD *)this + 5), &v43);
        v35 = v7;
        v4 = 351;
        if ( v7 >= 0 )
        {
          v36 = 351;
          v7 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 5) + 184LL))(*((_QWORD *)this + 5), 1);
          v35 = v7;
          v4 = 352;
          if ( v7 >= 0 )
          {
            v36 = 352;
            v7 = CDefragOperation::_CreateVolumeForFileSystem(this, &v33);
            v35 = v7;
            v4 = 362;
            if ( v7 >= 0 )
            {
              v36 = 362;
              *((_QWORD *)this + 97) = 0;
              *((_QWORD *)this + 98) = 0;
              *((_QWORD *)this + 99) = 0;
              *((_QWORD *)this + 100) = 0;
              *((_DWORD *)this + 202) = 0;
              v7 = (*(__int64 (__fastcall **)(struct IVolume *, int *, int *, int *, int *))(*(_QWORD *)v33 + 192LL))(
                     v33,
                     &v47,
                     &v46,
                     &v45,
                     &v42);
              v35 = v7;
              v4 = 372;
              if ( v7 >= 0 )
              {
                v36 = 372;
                if ( !v42 )
                {
                  v35 = -1996488672;
                  v5 = 376;
                  goto LABEL_3;
                }
                v7 = (*(__int64 (__fastcall **)(struct IVolume *, char *))(*(_QWORD *)v33 + 48LL))(
                       v33,
                       (char *)this + 56);
                v35 = v7;
                v4 = 381;
                if ( v7 >= 0 )
                {
                  v36 = 381;
                  v4 = *((unsigned int *)this + 38);
                  if ( *((_QWORD *)this + 96) / v4 < *((_QWORD *)this + 17) )
                  {
                    v35 = -1996488671;
                    v5 = 391;
                    goto LABEL_3;
                  }
                  v9 = *((_QWORD *)this + 95) / v4 + 1;
                  if ( !(*((_QWORD *)this + 95) % v4) )
                    v9 = *((_QWORD *)this + 95) / v4;
                  v10 = v9 * *((unsigned int *)this + 40);
                  v7 = (*(__int64 (__fastcall **)(struct IVolume *, __int64, _QWORD))(*(_QWORD *)v33 + 208LL))(
                         v33,
                         v10,
                         0);
                  v35 = v7;
                  v4 = 404;
                  if ( v7 >= 0 )
                  {
                    v36 = 404;
                    v2 = 1;
                    v7 = CDefragOperation::_SetPhase(this, 1u);
                    v35 = v7;
                    v4 = 411;
                    if ( v7 >= 0 )
                    {
                      v36 = 411;
                      v11 = v34;
                      if ( v34 )
                      {
                        v34 = 0;
                        (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v11 + 16LL))(v11);
                      }
                      v7 = CRunAnalysis::CreateInstance(0, 0, v33, &v34, 0, 0, 0, 0);
                      v35 = v7;
                      v4 = 414;
                      if ( v7 >= 0 )
                      {
                        v36 = 414;
                        v7 = (*(__int64 (__fastcall **)(struct IRunnableThread *, _QWORD))(*(_QWORD *)v34 + 24LL))(
                               v34,
                               *((_QWORD *)this + 5));
                        v35 = v7;
                        v4 = 417;
                        if ( v7 >= 0 )
                        {
                          v36 = 417;
                          v12 = v34;
                          if ( v34 )
                          {
                            v34 = 0;
                            (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v12 + 16LL))(v12);
                          }
                          v7 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(
                                 *((_QWORD *)this + 6),
                                 (char *)this + 56);
                          v35 = v7;
                          v4 = 423;
                          if ( v7 >= 0 )
                          {
                            v36 = 423;
                            v5 = 426;
                            if ( !*((_DWORD *)this + 38) )
                            {
                              v35 = -2147467259;
                              goto LABEL_3;
                            }
                            v35 = 0;
                            v36 = 426;
                            v13 = *((_QWORD *)this + 18);
                            *((_QWORD *)this + 24) = 0;
                            v7 = CDefragOperation::_SetPhase(this, 4u);
                            v35 = v7;
                            v4 = 444;
                            if ( v7 < 0 )
                              goto LABEL_33;
                            v14 = v9 - 1;
                            v15 = v13 - 1;
                            v36 = 444;
                            v16 = v34;
                            if ( v34 )
                            {
                              v34 = 0;
                              (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v16 + 16LL))(v16);
                            }
                            v50[0] = v14;
                            v50[1] = v15;
                            v7 = CRunBruteForceEvict::CreateInstance(v50, v33, &v34);
                            v35 = v7;
                            v4 = 449;
                            if ( v7 >= 0 )
                            {
                              v36 = 449;
                              v7 = (*(__int64 (__fastcall **)(struct IRunnableThread *, _QWORD))(*(_QWORD *)v34 + 24LL))(
                                     v34,
                                     *((_QWORD *)this + 5));
                              if ( v7 == -1996488673 )
                              {
                                v7 = -1996488671;
                                v35 = -1996488671;
LABEL_40:
                                v4 = 457;
                                goto LABEL_8;
                              }
                              v35 = v7;
                              if ( v7 < 0 )
                                goto LABEL_40;
                              v36 = 457;
                              v17 = v34;
                              if ( v34 )
                              {
                                v34 = 0;
                                (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v17 + 16LL))(v17);
                              }
                              v7 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 6) + 24LL))(
                                     *((_QWORD *)this + 6),
                                     (char *)this + 56);
                              v35 = v7;
                              v4 = 463;
                              if ( v7 >= 0 )
                              {
                                v36 = 463;
                                v18 = v39;
                                if ( v39 )
                                {
                                  v39 = 0;
                                  (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v18 + 16LL))(v18);
                                }
                                v7 = CFreeSpaceManager::CreateInstance(
                                       *((unsigned __int16 **)this + 87),
                                       *((_QWORD *)this + 18),
                                       &v39);
                                v35 = v7;
                                v4 = 473;
                                if ( v7 >= 0 )
                                {
                                  v36 = 473;
                                  (*(void (__fastcall **)(struct IFreeSpaceManager *, __int64 *))(*(_QWORD *)v39 + 88LL))(
                                    v39,
                                    &v44);
                                  v20 = v44;
                                  v21 = *((unsigned int *)this + 38) * (v44 + 1);
                                  v22 = WPP_GLOBAL_Control;
                                  if ( WPP_GLOBAL_Control != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
                                  {
                                    WPP_SF_iI(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, 2048);
                                    v20 = v44;
                                    v22 = WPP_GLOBAL_Control;
                                  }
                                  v3 = *((_QWORD *)this + 95);
                                  if ( v21 >= v3 )
                                  {
                                    v3 = v21;
                                    if ( v21 > *((_QWORD *)this + 96) )
                                    {
                                      if ( v22 != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                                        && (*((_DWORD *)v22 + 7) & 0x800) != 0 )
                                      {
                                        WPP_SF_II(
                                          *((_QWORD *)v22 + 2),
                                          21,
                                          WPP_9b40e9251fdc3d76fa0fc4f6af85682a_Traceguids);
                                        v20 = v44;
                                      }
                                      if ( (int)SxFileLoggingSupport::Initialize(
                                                  (__int64)v55,
                                                  *((const unsigned __int16 **)this + 87),
                                                  *((_QWORD *)this + 89),
                                                  v20,
                                                  v14,
                                                  (__int64)this + 56,
                                                  3) >= 0 )
                                      {
                                        SxFileLoggingSupport::LogShrinkInhibitorFileInfo(
                                          (SxFileLoggingSupport *)v55,
                                          (struct CSxFunctionTracer *)&v35,
                                          0x1F1u,
                                          0x80000105,
                                          2u);
                                        SxFileLoggingSupport::LogShrinkInhibitorTelemetry(
                                          (SxFileLoggingSupport *)v55,
                                          &v54);
                                      }
                                      v35 = -1996488671;
                                      v37 = 502;
                                      goto LABEL_73;
                                    }
                                  }
                                  v24 = v3 / *((unsigned int *)this + 39) + 1;
                                  if ( !(v3 % *((unsigned int *)this + 39)) )
                                    v24 = v3 / *((unsigned int *)this + 39);
                                  v23 = *((unsigned int *)this + 39);
                                  v3 = v23 * v24;
                                  if ( v22 != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                                    && (*((_DWORD *)v22 + 7) & 0x800) != 0 )
                                  {
                                    WPP_SF_i(
                                      *((_QWORD *)v22 + 2),
                                      22,
                                      WPP_9b40e9251fdc3d76fa0fc4f6af85682a_Traceguids,
                                      v23 * v24);
                                    v22 = WPP_GLOBAL_Control;
                                  }
                                  if ( v24 != v10 )
                                  {
                                    if ( v22 != (CSxGlobalTracer *)&WPP_GLOBAL_Control
                                      && (*((_DWORD *)v22 + 7) & 0x800) != 0 )
                                    {
                                      WPP_SF_i(
                                        *((_QWORD *)v22 + 2),
                                        23,
                                        WPP_9b40e9251fdc3d76fa0fc4f6af85682a_Traceguids,
                                        v24);
                                    }
                                    v7 = (*(__int64 (__fastcall **)(struct IVolume *, unsigned __int64, _QWORD))(*(_QWORD *)v33 + 208LL))(
                                           v33,
                                           v24,
                                           0);
                                    v35 = v7;
                                    v4 = 522;
                                    if ( v7 < 0 )
                                    {
LABEL_33:
                                      v37 = v4;
                                      goto LABEL_72;
                                    }
                                    v36 = 522;
                                  }
                                  v7 = (*(__int64 (__fastcall **)(struct IVolume *, unsigned __int64, __int64))(*(_QWORD *)v33 + 208LL))(
                                         v33,
                                         v24,
                                         1);
                                  v35 = v7;
                                  v4 = 526;
                                  if ( v7 >= 0 )
                                  {
                                    v36 = 526;
                                    v7 = (*(__int64 (__fastcall **)(struct IVolume *, char *))(*(_QWORD *)v33 + 48LL))(
                                           v33,
                                           (char *)this + 56);
                                    v35 = v7;
                                    v4 = 531;
                                    if ( v7 >= 0 )
                                    {
                                      v36 = 531;
                                      *((_QWORD *)this + 36) = v3;
                                      v7 = 0;
                                      v35 = 0;
LABEL_72:
                                      if ( v7 >= 0 )
                                        goto LABEL_75;
                                      goto LABEL_73;
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_8:
    v37 = v4;
    goto LABEL_72;
  }
  v35 = -2147024809;
LABEL_3:
  v37 = v5;
LABEL_73:
  if ( v2 )
    (*(void (__fastcall **)(struct IVolume *, _QWORD, __int64))(*(_QWORD *)v33 + 208LL))(v33, 0, 2);
LABEL_75:
  if ( v43 != 2 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 184LL))(*((_QWORD *)this + 5));
  if ( dword_1800840E0 && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    v48 = v35;
    v38 = v37;
    v51 = &v54;
    v49[0] = 2;
    v52 = v3;
    v53 = (const unsigned __int16 *)*((_QWORD *)this + 87);
    v50[0] = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>>(
      v25,
      (__int64)&word_18007822E,
      v26,
      v27,
      (__int64)v50,
      &v53,
      (__int64)&v52,
      (__int64)v49,
      (__int64 *)&v51,
      (__int64)&v38,
      (__int64)&v48);
  }
  Log_DF_OPTIMIZE_RESULT(
    (struct CSxFunctionTracer *)&v35,
    0x230u,
    *((const unsigned __int16 **)this + 89),
    0x327u,
    v35,
    0);
  DfStopTracing();
  v28 = v35;
  SxFileLoggingSupport::~SxFileLoggingSupport((void **)v55);
  v29 = v39;
  if ( v39 )
  {
    v39 = 0;
    (*(void (__fastcall **)(struct IFreeSpaceManager *))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v30 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(struct IVolume *))(*(_QWORD *)v30 + 16LL))(v30);
  }
  v31 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(struct IRunnableThread *))(*(_QWORD *)v31 + 16LL))(v31);
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v35);
  return v28;
}

```

## disassembly

```asm
0x18005a820  push    rbp
0x18005a822  push    rbx
0x18005a823  push    rsi
0x18005a824  push    rdi
0x18005a825  push    r12
0x18005a827  push    r13
0x18005a829  push    r14
0x18005a82b  push    r15
0x18005a82d  lea     rbp, [rsp-0D8h]
0x18005a835  sub     rsp, 1D8h
0x18005a83c  mov     rax, cs:__security_cookie
0x18005a843  xor     rax, rsp
0x18005a846  mov     [rbp+110h+var_50], rax
0x18005a84d  mov     rbx, rcx
0x18005a850  mov     r9d, 1; unsigned __int16
0x18005a856  mov     r8d, 129h; unsigned __int16
0x18005a85c  lea     rdx, aCrunshrinkRuno; "CRunShrink::RunOperation"
0x18005a863  lea     rcx, [rsp+210h+var_1A0]; this
0x18005a868  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18005a86d  nop
0x18005a86e  xor     edi, edi
0x18005a870  mov     [rsp+210h+var_1A8], rdi
0x18005a875  mov     [rsp+210h+var_1B0], rdi
0x18005a87a  mov     [rbp+110h+var_13C], edi
0x18005a87d  mov     [rbp+110h+var_140], edi
0x18005a880  mov     [rbp+110h+var_150], edi
0x18005a883  mov     [rbp+110h+var_138], edi
0x18005a886  mov     r13d, edi
0x18005a889  mov     [rbp+110h+var_154], edi
0x18005a88c  lea     r15d, [rdi+2]
0x18005a890  mov     [rbp+110h+ThreadInformation], r15d
0x18005a894  mov     [rbp+110h+var_14C], r15d
0x18005a898  mov     [rbp+110h+var_160], rdi
0x18005a89c  mov     [rbp+110h+var_148], rdi
0x18005a8a0  mov     esi, edi
0x18005a8a2  xorps   xmm0, xmm0
0x18005a8a5  movdqa  [rbp+110h+var_E0], xmm0
0x18005a8aa  xorps   xmm1, xmm1
0x18005a8ad  movups  [rbp+110h+var_D0], xmm1
0x18005a8b1  movups  [rbp+110h+var_C0], xmm1
0x18005a8b5  mov     [rbp+110h+var_B0], rdi
0x18005a8b9  mov     [rbp+110h+var_A8], edi
0x18005a8bc  mov     [rbp+110h+var_A4], di
0x18005a8c0  movdqa  [rbp+110h+var_90], xmm0
0x18005a8c8  mov     [rbp+110h+var_80], rdi
0x18005a8cf  mov     [rbp+110h+var_78], rdi
0x18005a8d6  mov     [rbp+110h+var_70], rdi
0x18005a8dd  mov     [rbp+110h+var_68], rdi
0x18005a8e4  mov     [rbp+110h+var_60], edi
0x18005a8ea  movups  xmmword ptr [rbp+110h+var_F8.Data1], xmm0
0x18005a8ee  mov     rcx, [rbx+28h]
0x18005a8f2  mov     rax, [rcx]
0x18005a8f5  lea     rdx, [rbp+110h+var_F8]
0x18005a8f9  mov     rax, [rax+98h]
0x18005a900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a905  call    ?DfStartTracing@@YAJXZ; DfStartTracing(void)
0x18005a90a  mov     rax, [rbx+300h]
0x18005a911  cmp     [rbx+2F8h], rax
0x18005a918  mov     eax, 148h
0x18005a91d  jbe     short loc_18005A931
0x18005a91f  mov     [rsp+210h+var_1A0], 80070057h
0x18005a927  mov     [rsp+210h+var_19A], ax
0x18005a92c  jmp     loc_18005B061
0x18005a931  mov     [rsp+210h+var_1A0], edi
0x18005a935  mov     [rsp+210h+var_19C], ax
0x18005a93a  lea     rax, WPP_GLOBAL_Control
0x18005a941  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a948  cmp     rcx, rax
0x18005a94b  jz      short loc_18005A968
0x18005a94d  test    byte ptr [rcx+1Ch], 10h
0x18005a951  jz      short loc_18005A968
0x18005a953  mov     edx, 13h
0x18005a958  lea     r8, WPP_9b40e9251fdc3d76fa0fc4f6af85682a_Traceguids
0x18005a95f  mov     rcx, [rcx+10h]
0x18005a963  call    WPP_SF_
0x18005a968  mov     [rbp+110h+ThreadInformation], r15d
0x18005a96c  mov     r12d, 4
0x18005a972  mov     r9d, r12d; ThreadInformationLength
0x18005a975  lea     r8, [rbp+110h+ThreadInformation]; ThreadInformation
0x18005a979  lea     edx, [r12+12h]; ThreadInformationClass
0x18005a97e  mov     r14, 0FFFFFFFFFFFFFFFEh
0x18005a985  mov     rcx, r14; ThreadHandle
0x18005a988  call    cs:__imp_NtSetInformationThread
0x18005a98e  mov     ecx, eax
0x18005a990  call    HRESULTFromNTSTATUS
0x18005a995  mov     [rsp+210h+var_1A0], eax
0x18005a999  mov     ecx, 156h
0x18005a99e  test    eax, eax
0x18005a9a0  jns     short loc_18005A9AC
0x18005a9a2  mov     [rsp+210h+var_19A], cx
0x18005a9a7  jmp     loc_18005B05D
0x18005a9ac  mov     [rsp+210h+var_19C], cx
0x18005a9b1  mov     [rbp+110h+var_154], r15d
0x18005a9b5  mov     r9d, r12d; ThreadInformationLength
0x18005a9b8  lea     r8, [rbp+110h+var_154]; ThreadInformation
0x18005a9bc  mov     edx, r15d; ThreadInformationClass
0x18005a9bf  mov     rcx, r14; ThreadHandle
0x18005a9c2  call    cs:__imp_NtSetInformationThread
0x18005a9c8  mov     ecx, eax
0x18005a9ca  call    HRESULTFromNTSTATUS
0x18005a9cf  mov     [rsp+210h+var_1A0], eax
0x18005a9d3  mov     ecx, 15Dh
0x18005a9d8  test    eax, eax
0x18005a9da  js      short loc_18005A9A2
0x18005a9dc  mov     [rsp+210h+var_19C], cx
0x18005a9e1  mov     rcx, [rbx+28h]
0x18005a9e5  mov     rax, [rcx]
0x18005a9e8  lea     rdx, [rbp+110h+var_14C]
0x18005a9ec  mov     rax, [rax+0B0h]
0x18005a9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a9f8  mov     [rsp+210h+var_1A0], eax
0x18005a9fc  mov     ecx, 15Fh
0x18005aa01  test    eax, eax
0x18005aa03  js      short loc_18005A9A2
0x18005aa05  mov     [rsp+210h+var_19C], cx
0x18005aa0a  mov     rcx, [rbx+28h]
0x18005aa0e  mov     rax, [rcx]
0x18005aa11  mov     edx, 1
0x18005aa16  mov     rax, [rax+0B8h]
0x18005aa1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aa22  mov     [rsp+210h+var_1A0], eax
0x18005aa26  mov     ecx, 160h
0x18005aa2b  test    eax, eax
0x18005aa2d  js      loc_18005A9A2
0x18005aa33  mov     [rsp+210h+var_19C], cx
0x18005aa38  mov     rcx, [rsp+210h+var_1B0]
0x18005aa3d  test    rcx, rcx
0x18005aa40  jz      short loc_18005AA54
0x18005aa42  mov     [rsp+210h+var_1B0], rdi
0x18005aa47  mov     rax, [rcx]
0x18005aa4a  mov     rax, [rax+10h]
0x18005aa4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aa53  nop
0x18005aa54  lea     rdx, [rsp+210h+var_1B0]; struct IVolume **
0x18005aa59  mov     rcx, rbx; this
0x18005aa5c  call    ?_CreateVolumeForFileSystem@CDefragOperation@@IEAAJPEAPEAUIVolume@@@Z; CDefragOperation::_CreateVolumeForFileSystem(IVolume * *)
0x18005aa61  mov     [rsp+210h+var_1A0], eax
0x18005aa65  mov     ecx, 16Ah
0x18005aa6a  test    eax, eax
0x18005aa6c  js      loc_18005A9A2
0x18005aa72  mov     [rsp+210h+var_19C], cx
0x18005aa77  mov     [rbx+308h], rdi
0x18005aa7e  mov     [rbx+310h], rdi
0x18005aa85  mov     [rbx+318h], rdi
0x18005aa8c  mov     [rbx+320h], rdi
0x18005aa93  mov     [rbx+328h], edi
0x18005aa99  mov     rcx, [rsp+210h+var_1B0]
0x18005aa9e  mov     rax, [rcx]
0x18005aaa1  lea     rdx, [rbp+110h+var_150]
0x18005aaa5  mov     [rsp+210h+var_1F0], rdx
0x18005aaaa  lea     r9, [rbp+110h+var_140]
0x18005aaae  lea     r8, [rbp+110h+var_13C]
0x18005aab2  lea     rdx, [rbp+110h+var_138]
0x18005aab6  mov     rax, [rax+0C0h]
0x18005aabd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aac2  mov     [rsp+210h+var_1A0], eax
0x18005aac6  mov     ecx, 174h
0x18005aacb  test    eax, eax
0x18005aacd  js      loc_18005A9A2
0x18005aad3  mov     [rsp+210h+var_19C], cx
0x18005aad8  cmp     [rbp+110h+var_150], edi
0x18005aadb  jnz     short loc_18005AAED
0x18005aadd  mov     [rsp+210h+var_1A0], 89000020h
0x18005aae5  lea     eax, [rcx+4]
0x18005aae8  jmp     loc_18005A927
0x18005aaed  mov     rcx, [rsp+210h+var_1B0]
0x18005aaf2  lea     r15, [rbx+38h]
0x18005aaf6  mov     rax, [rcx]
0x18005aaf9  mov     rdx, r15
0x18005aafc  mov     rax, [rax+30h]
0x18005ab00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab05  mov     [rsp+210h+var_1A0], eax
0x18005ab09  mov     ecx, 17Dh
0x18005ab0e  test    eax, eax
0x18005ab10  js      loc_18005A9A2
0x18005ab16  mov     [rsp+210h+var_19C], cx
0x18005ab1b  mov     ecx, [rbx+98h]
0x18005ab21  xor     edx, edx
0x18005ab23  mov     rax, [rbx+300h]
0x18005ab2a  div     rcx
0x18005ab2d  cmp     rax, [rbx+88h]
0x18005ab34  jnb     short loc_18005AB49
0x18005ab36  mov     eax, 89000021h
0x18005ab3b  mov     [rsp+210h+var_1A0], eax
0x18005ab3f  mov     eax, 187h
0x18005ab44  jmp     loc_18005A927
0x18005ab49  xor     edx, edx
0x18005ab4b  mov     rax, [rbx+2F8h]
0x18005ab52  div     rcx
0x18005ab55  lea     r14, [rax+1]
0x18005ab59  test    rdx, rdx
0x18005ab5c  cmovz   r14, rax
0x18005ab60  mov     r12d, [rbx+0A0h]
0x18005ab67  imul    r12, r14
0x18005ab6b  mov     rcx, [rsp+210h+var_1B0]
0x18005ab70  mov     rax, [rcx]
0x18005ab73  xor     r8d, r8d
0x18005ab76  mov     rdx, r12
0x18005ab79  mov     rax, [rax+0D0h]
0x18005ab80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ab85  mov     [rsp+210h+var_1A0], eax
0x18005ab89  mov     ecx, 194h
0x18005ab8e  test    eax, eax
0x18005ab90  js      loc_18005A9A2
0x18005ab96  mov     [rsp+210h+var_19C], cx
0x18005ab9b  mov     eax, 1
0x18005aba0  mov     r13d, eax
0x18005aba3  mov     edx, eax
0x18005aba5  mov     rcx, rbx
0x18005aba8  call    ?_SetPhase@CDefragOperation@@IEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0001@@@Z; CDefragOperation::_SetPhase(__MIDL___MIDL_itf_dfengine_0000_0000_0001)
0x18005abad  mov     [rsp+210h+var_1A0], eax
0x18005abb1  mov     ecx, 19Bh
0x18005abb6  test    eax, eax
0x18005abb8  js      loc_18005A9A2
0x18005abbe  mov     [rsp+210h+var_19C], cx
0x18005abc3  mov     rcx, [rsp+210h+var_1A8]
0x18005abc8  test    rcx, rcx
0x18005abcb  jz      short loc_18005ABDF
0x18005abcd  mov     [rsp+210h+var_1A8], rdi
0x18005abd2  mov     rax, [rcx]
0x18005abd5  mov     rax, [rax+10h]
0x18005abd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005abde  nop
0x18005abdf  mov     [rsp+210h+var_1D8], rdi; unsigned __int16 *
0x18005abe4  mov     [rsp+210h+var_1E0], rdi; unsigned __int64 *
0x18005abe9  mov     [rsp+210h+var_1E8], rdi; unsigned __int64 *
0x18005abee  mov     [rsp+210h+var_1F0], rdi; struct __MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *
0x18005abf3  lea     r9, [rsp+210h+var_1A8]; struct IRunnableThread **
0x18005abf8  mov     r8, [rsp+210h+var_1B0]; struct IVolume *
0x18005abfd  xor     edx, edx; int
0x18005abff  xor     ecx, ecx; int
0x18005ac01  call    ?CreateInstance@CRunAnalysis@@SAJHHPEAUIVolume@@PEAPEAUIRunnableThread@@PEAU__MIDL___MIDL_itf_dfengine_np_0000_0000_0001@@PEA_K3PEAG@Z; CRunAnalysis::CreateInstance(int,int,IVolume *,IRunnableThread * *,__MIDL___MIDL_itf_dfengine_np_0000_0000_0001 *,unsigned __int64 *,unsigned __int64 *,ushort *)
0x18005ac06  mov     [rsp+210h+var_1A0], eax
0x18005ac0a  mov     ecx, 19Eh
0x18005ac0f  test    eax, eax
0x18005ac11  js      loc_18005A9A2
0x18005ac17  mov     [rsp+210h+var_19C], cx
0x18005ac1c  mov     rcx, [rsp+210h+var_1A8]
0x18005ac21  mov     rax, [rcx]
0x18005ac24  mov     rdx, [rbx+28h]
0x18005ac28  mov     rax, [rax+18h]
0x18005ac2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac31  mov     [rsp+210h+var_1A0], eax
0x18005ac35  mov     ecx, 1A1h
0x18005ac3a  test    eax, eax
0x18005ac3c  js      loc_18005A9A2
0x18005ac42  mov     [rsp+210h+var_19C], cx
0x18005ac47  mov     rcx, [rsp+210h+var_1A8]
0x18005ac4c  test    rcx, rcx
0x18005ac4f  jz      short loc_18005AC63
0x18005ac51  mov     [rsp+210h+var_1A8], rdi
0x18005ac56  mov     rax, [rcx]
0x18005ac59  mov     rax, [rax+10h]
0x18005ac5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac62  nop
0x18005ac63  mov     rcx, [rbx+30h]
0x18005ac67  mov     rax, [rcx]
0x18005ac6a  mov     rdx, r15
0x18005ac6d  mov     rax, [rax+18h]
0x18005ac71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ac76  mov     [rsp+210h+var_1A0], eax
0x18005ac7a  mov     ecx, 1A7h
0x18005ac7f  test    eax, eax
0x18005ac81  js      loc_18005A9A2
0x18005ac87  mov     [rsp+210h+var_19C], cx
0x18005ac8c  lea     eax, [rcx+3]
0x18005ac8f  cmp     [rbx+98h], edi
0x18005ac95  ja      short loc_18005ACA4
0x18005ac97  mov     [rsp+210h+var_1A0], 80004005h
0x18005ac9f  jmp     loc_18005A927
0x18005aca4  mov     [rsp+210h+var_1A0], edi
0x18005aca8  mov     [rsp+210h+var_19C], ax
0x18005acad  mov     rdi, [rbx+90h]
0x18005acb4  mov     qword ptr [rbx+0C0h], 0
0x18005acbf  mov     edx, 4
0x18005acc4  mov     rcx, rbx
0x18005acc7  call    ?_SetPhase@CDefragOperation@@IEAAJW4__MIDL___MIDL_itf_dfengine_0000_0000_0001@@@Z; CDefragOperation::_SetPhase(__MIDL___MIDL_itf_dfengine_0000_0000_0001)
0x18005accc  mov     [rsp+210h+var_1A0], eax
0x18005acd0  mov     ecx, 1BCh
0x18005acd5  test    eax, eax
0x18005acd7  jns     short loc_18005ACE5
0x18005acd9  mov     [rsp+210h+var_19A], cx
0x18005acde  xor     edi, edi
0x18005ace0  jmp     loc_18005B05D
0x18005ace5  dec     r14
0x18005ace8  dec     rdi
0x18005aceb  mov     [rsp+210h+var_19C], cx
0x18005acf0  mov     rcx, [rsp+210h+var_1A8]
0x18005acf5  test    rcx, rcx
0x18005acf8  jz      short loc_18005AD10
0x18005acfa  mov     [rsp+210h+var_1A8], 0
0x18005ad03  mov     rax, [rcx]
0x18005ad06  mov     rax, [rax+10h]
0x18005ad0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ad0f  nop
0x18005ad10  mov     [rbp+110h+var_120], r14
0x18005ad14  mov     [rbp+110h+var_118], rdi
0x18005ad18  lea     r8, [rsp+210h+var_1A8]
0x18005ad1d  mov     rdx, [rsp+210h+var_1B0]
0x18005ad22  lea     rcx, [rbp+110h+var_120]
  ... truncated ...
```
