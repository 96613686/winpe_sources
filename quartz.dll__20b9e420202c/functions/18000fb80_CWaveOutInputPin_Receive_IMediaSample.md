# CWaveOutInputPin::Receive(IMediaSample *)

- ea: `0x18000fb80`
- end: `0x180010543`
- name: `?Receive@CWaveOutInputPin@@UEAAJPEAUIMediaSample@@@Z`
- size: `2499`
- prototype: `__int64 __fastcall(CWaveOutInputPin *__hidden this, struct IMediaSample *)`
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fb80`
- `0x180010550`
- `0x180010748`
- `0x1800109c0`
- `0x180019ae0`
- `0x18001f478`
- `0x18002d5f4`
- `0x1800300cc`
- `0x18003022c`
- `0x18003065c`
- `0x1800388a0`
- `0x180039250`
- `0x1800f8018`
- `0x1800f9b88`
- `0x1800f9c18`
- `0x1800fb034`
- `0x1800fc1dc`
- `0x180130e7c`
- `0x18015bb8c`
- `0x18015e010`

## import_xrefs

- `KERNEL32!GetCurrentThread` at `0x18000fbd5`
- `KERNEL32!GetCurrentThread` at `0x18000fbf5`
- `KERNEL32!GetCurrentThread` at `0x18000fbd5`
- `KERNEL32!GetCurrentThread` at `0x18000fbf5`
- `KERNEL32!GetThreadPriority` at `0x18000fbe4`
- `KERNEL32!GetThreadPriority` at `0x18000fbe4`
- `KERNEL32!SetThreadPriority` at `0x18000fc09`
- `KERNEL32!SetThreadPriority` at `0x18000fc09`
- `KERNEL32!SetEvent` at `0x18000fc26`
- `KERNEL32!SetEvent` at `0x18000fc26`
- `KERNEL32!LeaveCriticalSection` at `0x18000fc42`
- `KERNEL32!LeaveCriticalSection` at `0x18000fc75`
- `KERNEL32!LeaveCriticalSection` at `0x18000fce0`
- `KERNEL32!LeaveCriticalSection` at `0x18000fe43`
- `KERNEL32!LeaveCriticalSection` at `0x1800100e4`
- `KERNEL32!LeaveCriticalSection` at `0x180010178`
- `KERNEL32!LeaveCriticalSection` at `0x1800101ac`
- `KERNEL32!LeaveCriticalSection` at `0x18001036c`
- `KERNEL32!LeaveCriticalSection` at `0x1800104e7`
- `KERNEL32!LeaveCriticalSection` at `0x180010501`
- `KERNEL32!LeaveCriticalSection` at `0x18000fc42`
- `KERNEL32!LeaveCriticalSection` at `0x18000fc75`
- `KERNEL32!LeaveCriticalSection` at `0x18000fce0`
- `KERNEL32!LeaveCriticalSection` at `0x18000fe43`
- `KERNEL32!LeaveCriticalSection` at `0x1800100e4`
- `KERNEL32!LeaveCriticalSection` at `0x180010178`
- `KERNEL32!LeaveCriticalSection` at `0x1800101ac`
- `KERNEL32!LeaveCriticalSection` at `0x18001036c`
- `KERNEL32!LeaveCriticalSection` at `0x1800104e7`
- `KERNEL32!LeaveCriticalSection` at `0x180010501`
- `KERNEL32!EnterCriticalSection` at `0x18000fbc9`
- `KERNEL32!EnterCriticalSection` at `0x180010147`
- `KERNEL32!EnterCriticalSection` at `0x1800103c4`
- `KERNEL32!EnterCriticalSection` at `0x18000fbc9`
- `KERNEL32!EnterCriticalSection` at `0x180010147`
- `KERNEL32!EnterCriticalSection` at `0x1800103c4`

## pseudocode

```c
__int64 __fastcall CWaveOutInputPin::Receive(CWaveOutInputPin *this, struct IMediaSample *a2)
{
  CWaveOutInputPin *v2; // r15
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  HANDLE CurrentThread; // rax
  HANDLE v8; // rax
  __int64 v9; // rcx
  int v11; // r13d
  CWaveOutFilter *v12; // r15
  __int64 v13; // rsi
  size_t v14; // r8
  unsigned __int16 *v15; // rdx
  int v16; // eax
  int v17; // esi
  __int64 v18; // r12
  int v19; // r15d
  struct IMediaSampleVtbl *lpVtbl; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r15
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  int v29; // r15d
  __int64 v30; // rax
  int v31; // r13d
  BOOL v32; // r12d
  __int64 v33; // rdx
  BOOL v34; // ecx
  int v35; // eax
  struct IMediaSampleVtbl *v36; // rax
  int v37; // eax
  __int64 v38; // rax
  CWaveOutClock *v39; // rcx
  int v40; // eax
  struct _RTL_CRITICAL_SECTION *v41; // rdx
  __int64 v42; // rax
  struct _EVENT_TRACE_HEADER *v43; // r15
  __int64 v44; // r10
  int v45; // r8d
  BOOL v46; // r11d
  __int64 *v47; // r9
  unsigned int v48; // eax
  __int64 v49; // r8
  unsigned int v50; // r13d
  __int64 v51; // rcx
  __int64 v52; // rdi
  int v53; // eax
  int v54; // r8d
  __int64 v55; // rdx
  __int64 v56; // r15
  __int64 v57; // rcx
  __int64 v58; // r13
  __int64 v59; // rax
  unsigned int v60; // eax
  __int64 v61; // rdx
  __int64 v62; // rsi
  __int64 v63; // rdx
  __int64 v64; // rax
  __int64 *v65; // rsi
  __int64 *v66; // r12
  __int64 v67; // rsi
  struct _RTL_CRITICAL_SECTION *v68; // rcx
  BOOL v69; // [rsp+30h] [rbp-99h]
  int v70; // [rsp+34h] [rbp-95h]
  int v71; // [rsp+38h] [rbp-91h] BYREF
  __int64 v72; // [rsp+40h] [rbp-89h] BYREF
  CBaseFilter *v73; // [rsp+48h] [rbp-81h] BYREF
  unsigned __int8 *v74; // [rsp+50h] [rbp-79h]
  __int64 v75; // [rsp+58h] [rbp-71h] BYREF
  struct IMediaSample *v76; // [rsp+60h] [rbp-69h] BYREF
  __int64 v77; // [rsp+68h] [rbp-61h] BYREF
  __int64 v78; // [rsp+70h] [rbp-59h] BYREF
  struct _EVENT_TRACE_HEADER v79; // [rsp+80h] [rbp-49h] BYREF
  __int64 v80; // [rsp+B0h] [rbp-19h]
  __int64 v81; // [rsp+B8h] [rbp-11h]
  __int64 v82; // [rsp+C0h] [rbp-9h]
  __int64 v83; // [rsp+C8h] [rbp-1h]
  BOOL v84; // [rsp+D0h] [rbp+7h]

  v2 = (CWaveOutInputPin *)((char *)this - 216);
  v4 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 12);
  v6 = v4 + 5;
  if ( !v4 )
    v6 = 0;
  EnterCriticalSection(v6);
  CurrentThread = GetCurrentThread();
  if ( !GetThreadPriority(CurrentThread) )
  {
    v8 = GetCurrentThread();
    SetThreadPriority(v8, 1);
  }
  v9 = *((_QWORD *)this + 12);
  if ( *(_DWORD *)(v9 + 40) == 1 )
    SetEvent(*(HANDLE *)(v9 + 416));
  if ( *(_DWORD *)(*((_QWORD *)this + 12) + 456LL) )
  {
    LeaveCriticalSection(v6);
    return 2147746348LL;
  }
  v11 = CBaseInputPin::Receive(this, a2);
  if ( v11 )
    goto LABEL_10;
  if ( (*((_BYTE *)this + 32) & 8) != 0 )
  {
    v12 = (CWaveOutFilter *)*((_QWORD *)this + 12);
    v13 = *((_QWORD *)this + 8);
    v14 = *(unsigned int *)(v13 + 72);
    v15 = *(unsigned __int16 **)(*((_QWORD *)v12 + 35) + 184LL);
    if ( v14 != v15[8] + 18LL || memcmp_0(*(const void **)(v13 + 80), v15, v14) )
    {
      v11 = CWaveOutFilter::ReOpenWaveDevice(v12, (struct CMediaType *)v13);
      if ( v11 )
      {
LABEL_10:
        LeaveCriticalSection(v6);
        return (unsigned int)v11;
      }
    }
    v2 = (CWaveOutInputPin *)((char *)this - 216);
  }
  v16 = *((_DWORD *)this + 8);
  v17 = v16 & 0x10;
  LODWORD(v72) = v17 != 0;
  if ( (v16 & 0x10) != 0 && (v16 & 0x100) != 0 )
  {
    v11 = CWaveOutInputPin::RemovePreroll(v2, a2);
    if ( *((_DWORD *)this + 89) )
      *((_DWORD *)this + 87) = 1;
    if ( v11 == 1 )
    {
      if ( !((unsigned int (__fastcall *)(struct IMediaSample *))a2->lpVtbl->IsDiscontinuity)(a2) )
        *((_DWORD *)this + 87) = 1;
      goto LABEL_138;
    }
    if ( v11 < 0 )
      goto LABEL_84;
  }
  v18 = *((int *)this + 9);
  v19 = *((_DWORD *)this + 87);
  v74 = (unsigned __int8 *)*((_QWORD *)this + 9);
  v73 = (CBaseFilter *)v74;
  v77 = *((_QWORD *)this + 5);
  v75 = *((_QWORD *)this + 6);
  lpVtbl = a2->lpVtbl;
  v71 = v18;
  v70 = v19;
  if ( !((unsigned int (__fastcall *)(struct IMediaSample *))lpVtbl->IsDiscontinuity)(a2) || v19 )
  {
    ++*((_DWORD *)this + 92);
    *((_DWORD *)this + 87) = 0;
  }
  v22 = *((unsigned int *)this + 90);
  if ( (_DWORD)v22 )
  {
    v23 = 10000000 * v18 / v22;
    v21 = 10000000 * v18 % v22;
  }
  else
  {
    v23 = 10000000;
  }
  v24 = *((_QWORD *)this + 12);
  *((_QWORD *)this + 47) = v23;
  v78 = 0;
  v25 = *(_QWORD *)(v24 + 48);
  if ( v25 && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 24LL))(v25, &v78) >= 0 )
    v78 -= *(_QWORD *)(v24 + 56);
  v26 = *((_QWORD *)this + 12);
  if ( !*(_BYTE *)(v26 + 452) )
  {
    CWaveOutFilter::QueueEOS((CWaveOutFilter *)v26);
    *((_DWORD *)this + 86) = 1;
    LeaveCriticalSection(v6);
    return 1;
  }
  if ( !*(_DWORD *)(v26 + 244) )
  {
    if ( v17 )
    {
      *((_QWORD *)this + 42) = v77;
    }
    else if ( *(_DWORD *)(v26 + 296) == 1
           && ((unsigned int (__fastcall *)(struct IMediaSample *, __int64))a2->lpVtbl->IsDiscontinuity)(a2, v21)
           && !v70 )
    {
      *((_QWORD *)this + 42) = *((_QWORD *)this + 41);
    }
    else
    {
      *((_QWORD *)this + 42) = 0;
    }
  }
  v27 = *((_QWORD *)this + 12);
  if ( *(_DWORD *)(v27 + 296) == 1 )
  {
    v28 = *((_QWORD *)this + 47);
    if ( v17 )
      *((_QWORD *)this + 41) = v77 + v28;
    else
      *((_QWORD *)this + 41) += v28;
  }
  v69 = 0;
  if ( *(_DWORD *)(v27 + 40) != 2 || *(_DWORD *)(v27 + 296) == -1 )
  {
    v29 = v72;
  }
  else
  {
    v29 = v72;
    if ( !*((_DWORD *)this + 89) )
    {
      if ( (unsigned int)CWaveSlave::UpdateSlaveMode((CWaveOutInputPin *)((char *)this + 128), v72) )
      {
        v30 = *((_QWORD *)this + 12);
        if ( *(_DWORD *)(v30 + 324) == 6 || (*((_BYTE *)this + 284) & 1) != 0 )
        {
          if ( !*(_DWORD *)(v30 + 260) || (*((_DWORD *)this + 71) & 1) != 0 )
          {
            v31 = v70;
          }
          else
          {
            v31 = v70;
            if ( ((unsigned int (__fastcall *)(struct IMediaSample *))a2->lpVtbl->IsDiscontinuity)(a2) && !v70 )
            {
              v32 = 0;
              v33 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 12) + 248LL) + 16LL);
              if ( v77 > v33 )
              {
                v32 = v77 - v33 > 300000;
                v69 = v32;
              }
LABEL_61:
              v34 = !((unsigned int (__fastcall *)(struct IMediaSample *))a2->lpVtbl->IsDiscontinuity)(a2) || v31 || v32;
              v72 = v77;
              v35 = CWaveSlave::AdjustSlaveClock((CWaveOutInputPin *)((char *)this + 128), &v72, &v75, &v71, v34);
              v11 = v35;
              if ( v35 == 1 )
                goto LABEL_138;
              if ( v35 >= 0 )
              {
                LODWORD(v18) = v71;
                goto LABEL_70;
              }
LABEL_84:
              LeaveCriticalSection(v6);
              return (unsigned int)v11;
            }
          }
          v32 = 0;
          goto LABEL_61;
        }
      }
    }
  }
LABEL_70:
  if ( (PerflogEnableFlags & 0x20) != 0 )
  {
    memset_0(&v79, 0, 0x58u);
    v79.UserTime = 0x20000;
    v79.Size = 88;
    v80 = v78;
    v81 = *((_QWORD *)this + 5);
    v82 = *((_QWORD *)this + 6);
    v36 = a2->lpVtbl;
    v79.Guid = GUID_AUDIORECV;
    v37 = ((__int64 (__fastcall *)(struct IMediaSample *))v36->IsDiscontinuity)(a2);
    v83 = *((_QWORD *)this + 47);
    v84 = v37 == 0;
    PerflogTraceEvent(&v79);
  }
  if ( !*((_DWORD *)this + 30) )
  {
    v38 = *((_QWORD *)this + 12);
    if ( !*(_DWORD *)(v38 + 260) )
    {
      v39 = *(CWaveOutClock **)(v38 + 288);
      if ( v39 )
        *(_QWORD *)(*((_QWORD *)this + 12) + 408LL) = CWaveOutClock::NextHdr(v39, v74, v18, v29, a2);
      LeaveCriticalSection(v6);
      v76 = 0;
      while ( (int)v18 > 0 && !v11 )
      {
        v40 = (*(__int64 (__fastcall **)(__int64, struct IMediaSample **, _QWORD, _QWORD, _DWORD))(*(_QWORD *)(*((_QWORD *)this + 14) + 24LL)
                                                                                                 + 56LL))(
                *((_QWORD *)this + 14) + 24LL,
                &v76,
                0,
                0,
                0);
        v41 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 12);
        v11 = v40;
        v6 = v41 + 5;
        if ( !v41 )
          v6 = 0;
        EnterCriticalSection(v6);
        if ( v11 < 0 )
        {
          CWaveOutFilter::ScheduleComplete(*((CWaveOutFilter **)this + 12), 0);
          goto LABEL_84;
        }
        v11 = CWaveOutInputPin::CopyToOurSample(
                (CWaveOutInputPin *)((char *)this - 216),
                v76,
                (unsigned __int8 **)&v73,
                &v71);
        LeaveCriticalSection(v6);
        ((void (__fastcall *)(struct IMediaSample *))v76->lpVtbl->Release)(v76);
        LODWORD(v18) = v71;
      }
      return (unsigned int)v11;
    }
  }
  ((void (__fastcall *)(struct IMediaSample *))a2->lpVtbl->AddRef)(a2);
  v42 = *((_QWORD *)this + 12);
  memset(&v79, 0, sizeof(v79));
  if ( *(_DWORD *)(v42 + 240) )
  {
    v43 = (struct _EVENT_TRACE_HEADER *)&v74[-*(int *)(v42 + 256)];
  }
  else
  {
    v43 = &v79;
    *(_QWORD *)&v79.Size = v74;
    v79.TimeStamp.QuadPart = (LONGLONG)a2;
  }
  v43->ThreadId = v18;
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 12) + 244LL));
  if ( *(_DWORD *)(*((_QWORD *)this + 12) + 240LL) )
    v43->Guid.Data1 &= ~0x10u;
  v44 = *((_QWORD *)this + 12);
  v45 = ~*((_DWORD *)this + 8);
  v73 = (CBaseFilter *)v44;
  v46 = (v45 & 4) == 0 || v70 || v69;
  v47 = &v77;
  if ( (v45 & 0x10) != 0 )
    v47 = 0;
  v48 = (*(__int64 (__fastcall **)(_QWORD, struct _EVENT_TRACE_HEADER *, _QWORD, __int64 *, BOOL))(**(_QWORD **)(v44 + 248)
                                                                                                 + 88LL))(
          *(_QWORD *)(v44 + 248),
          v43,
          *(unsigned int *)(v44 + 256),
          v47,
          v46);
  v50 = v48;
  if ( v48 )
    CBaseFilter::NotifyEvent(v73, 513, 9, v48);
  if ( v43->ThreadId )
    *((_DWORD *)this + 89) = 0;
  v51 = *((_QWORD *)this + 12);
  if ( v50 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v51 + 244));
    v52 = *((_QWORD *)this + 12);
    v53 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v52 + 280) + 112LL))(*(_QWORD *)(v52 + 280));
    if ( v50 == 6 )
    {
      if ( v53 )
        goto LABEL_115;
      if ( *(_DWORD *)(v52 + 456) )
        goto LABEL_115;
      *(_DWORD *)(v52 + 456) = 1;
      if ( _InterlockedDecrement((volatile signed __int32 *)(v52 + 244)) >= 0 || *(_DWORD *)(v52 + 40) != 2 )
        goto LABEL_115;
      v54 = 1;
    }
    else
    {
      if ( v53 )
        goto LABEL_115;
      if ( *(_DWORD *)(v52 + 456) )
        goto LABEL_115;
      *(_DWORD *)(v52 + 456) = 1;
      if ( _InterlockedDecrement((volatile signed __int32 *)(v52 + 244)) >= 0 || *(_DWORD *)(v52 + 40) != 2 )
        goto LABEL_115;
      v54 = 0;
    }
    CWaveOutFilter::SendComplete((CWaveOutFilter *)v52, 1, v54);
LABEL_115:
    ((void (__fastcall *)(struct IMediaSample *))a2->lpVtbl->Release)(a2);
    LeaveCriticalSection(v6);
    return 2147500037LL;
  }
  if ( *(_DWORD *)(v51 + 324) == 3 && *(_DWORD *)(v51 + 40) == 2 )
  {
    v55 = *(_QWORD *)(v51 + 56);
    if ( (*((_BYTE *)this + 32) & 0x10) != 0 )
      v55 += *((_QWORD *)this + 5);
    CWaveOutFilter::SetUpRestartWave((CWaveOutFilter *)v51, v55, v49);
  }
  v56 = *(_QWORD *)(*((_QWORD *)this + 12) + 288LL);
  if ( !v56 )
    goto LABEL_138;
  v73 = (CBaseFilter *)(v56 + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)(v56 + 40));
  v57 = *(_QWORD *)(*(_QWORD *)(v56 + 136) + 280LL);
  v58 = *(unsigned int *)(v57 + 576);
  if ( v17 )
  {
    v59 = *(_QWORD *)(v57 + 184);
    if ( *(_WORD *)v59 == 80 && (*(_BYTE *)(v59 + 30) & 0x10) != 0 )
    {
      v60 = MPEG1AudioFrameOffset(v74, v18);
      v61 = *(_QWORD *)(v56 + 168);
      if ( v60 == -1 )
      {
        v62 = *(_QWORD *)(v56 + 176);
        v63 = (unsigned int)v18 + v61;
        *(_QWORD *)(v56 + 168) = v63;
        v64 = 10000000 * v63;
LABEL_136:
        v68 = (struct _RTL_CRITICAL_SECTION *)(v56 + 40);
        v67 = v64 / v58 + v62;
        goto LABEL_137;
      }
      *(_QWORD *)(v56 + 152) += v61 + v60;
      LODWORD(v18) = v18 - v60;
    }
    else
    {
      *(_QWORD *)(v56 + 152) += *(_QWORD *)(v56 + 168);
    }
    v65 = (__int64 *)(v56 + 176);
    *(_QWORD *)(v56 + 168) = (unsigned int)v18;
    v66 = (__int64 *)(v56 + 184);
    ((void (__fastcall *)(struct IMediaSample *, __int64, __int64))a2->lpVtbl->GetTime)(a2, v56 + 176, v56 + 184);
    if ( *(_DWORD *)(*(_QWORD *)(v56 + 136) + 40LL) == 2 && *(_DWORD *)(v56 + 224) )
      CWaveOutClock::AdjustClock((CWaveOutClock *)v56);
  }
  else
  {
    v65 = (__int64 *)(v56 + 176);
    *(_QWORD *)(v56 + 168) += (unsigned int)v18;
    v66 = (__int64 *)(v56 + 184);
  }
  if ( (_DWORD)v58 )
  {
    v64 = 10000000LL * *(_QWORD *)(v56 + 168);
    v62 = *v65;
    goto LABEL_136;
  }
  v67 = *v66;
  v68 = (struct _RTL_CRITICAL_SECTION *)v73;
LABEL_137:
  LeaveCriticalSection(v68);
  *(_QWORD *)(*((_QWORD *)this + 12) + 408LL) = v67;
LABEL_138:
  LeaveCriticalSection(v6);
  return 0;
}

```

## disassembly

```asm
0x18000fb80  push    rbp
0x18000fb82  push    rbx
0x18000fb83  push    rdi
0x18000fb84  push    r14
0x18000fb86  push    r15
0x18000fb88  lea     rbp, [rsp-37h]
0x18000fb8d  sub     rsp, 100h
0x18000fb94  mov     rax, cs:__security_cookie
0x18000fb9b  xor     rax, rsp
0x18000fb9e  mov     [rbp+57h+var_40], rax
0x18000fba2  lea     r15, [rcx-0D8h]
0x18000fba9  mov     rdi, rcx
0x18000fbac  mov     rcx, [r15+138h]
0x18000fbb3  xor     eax, eax
0x18000fbb5  test    rcx, rcx
0x18000fbb8  mov     r14, rdx
0x18000fbbb  lea     rbx, [rcx+0C8h]
0x18000fbc2  cmovz   rbx, rax
0x18000fbc6  mov     rcx, rbx; lpCriticalSection
0x18000fbc9  call    cs:__imp_EnterCriticalSection
0x18000fbd0  nop     dword ptr [rax+rax+00h]
0x18000fbd5  call    cs:__imp_GetCurrentThread
0x18000fbdc  nop     dword ptr [rax+rax+00h]
0x18000fbe1  mov     rcx, rax; hThread
0x18000fbe4  call    cs:__imp_GetThreadPriority
0x18000fbeb  nop     dword ptr [rax+rax+00h]
0x18000fbf0  cmp     eax, 1
0x18000fbf3  jnb     short loc_18000FC15
0x18000fbf5  call    cs:__imp_GetCurrentThread
0x18000fbfc  nop     dword ptr [rax+rax+00h]
0x18000fc01  mov     rcx, rax; hThread
0x18000fc04  mov     edx, 1; nPriority
0x18000fc09  call    cs:__imp_SetThreadPriority
0x18000fc10  nop     dword ptr [rax+rax+00h]
0x18000fc15  mov     rcx, [rdi+60h]
0x18000fc19  cmp     dword ptr [rcx+28h], 1
0x18000fc1d  jnz     short loc_18000FC32
0x18000fc1f  mov     rcx, [rcx+1A0h]; hEvent
0x18000fc26  call    cs:__imp_SetEvent
0x18000fc2d  nop     dword ptr [rax+rax+00h]
0x18000fc32  mov     rax, [rdi+60h]
0x18000fc36  cmp     dword ptr [rax+1C8h], 0
0x18000fc3d  jz      short loc_18000FC58
0x18000fc3f  mov     rcx, rbx; lpCriticalSection
0x18000fc42  call    cs:__imp_LeaveCriticalSection
0x18000fc49  nop     dword ptr [rax+rax+00h]
0x18000fc4e  mov     eax, 8004022Ch
0x18000fc53  jmp     loc_180010527
0x18000fc58  mov     rdx, r14; struct IMediaSample *
0x18000fc5b  mov     [rsp+120h+var_30], r13
0x18000fc63  mov     rcx, rdi; this
0x18000fc66  call    ?Receive@CBaseInputPin@@UEAAJPEAUIMediaSample@@@Z; CBaseInputPin::Receive(IMediaSample *)
0x18000fc6b  mov     r13d, eax
0x18000fc6e  test    eax, eax
0x18000fc70  jz      short loc_18000FC89
0x18000fc72  mov     rcx, rbx; lpCriticalSection
0x18000fc75  call    cs:__imp_LeaveCriticalSection
0x18000fc7c  nop     dword ptr [rax+rax+00h]
0x18000fc81  mov     eax, r13d
0x18000fc84  jmp     loc_18001051F
0x18000fc89  test    byte ptr [rdi+20h], 8
0x18000fc8d  mov     [rsp+120h+arg_10], rsi
0x18000fc95  jz      short loc_18000FCFB
0x18000fc97  mov     r15, [rdi+60h]
0x18000fc9b  mov     rsi, [rdi+40h]
0x18000fc9f  mov     rax, [r15+118h]
0x18000fca6  mov     r8d, [rsi+48h]; Size
0x18000fcaa  mov     rdx, [rax+0B8h]; Buf2
0x18000fcb1  movzx   eax, word ptr [rdx+10h]
0x18000fcb5  add     rax, 12h
0x18000fcb9  cmp     r8, rax
0x18000fcbc  jnz     short loc_18000FCCB
0x18000fcbe  mov     rcx, [rsi+50h]; Buf1
0x18000fcc2  call    memcmp_0
0x18000fcc7  test    eax, eax
0x18000fcc9  jz      short loc_18000FCF4
0x18000fccb  mov     rdx, rsi; struct CMediaType *
0x18000fcce  mov     rcx, r15; this
0x18000fcd1  call    ?ReOpenWaveDevice@CWaveOutFilter@@AEAAJPEAVCMediaType@@@Z; CWaveOutFilter::ReOpenWaveDevice(CMediaType *)
0x18000fcd6  mov     r13d, eax
0x18000fcd9  test    eax, eax
0x18000fcdb  jz      short loc_18000FCF4
0x18000fcdd  mov     rcx, rbx; lpCriticalSection
0x18000fce0  call    cs:__imp_LeaveCriticalSection
0x18000fce7  nop     dword ptr [rax+rax+00h]
0x18000fcec  mov     eax, r13d
0x18000fcef  jmp     loc_180010517
0x18000fcf4  lea     r15, [rdi-0D8h]
0x18000fcfb  mov     eax, [rdi+20h]
0x18000fcfe  mov     ecx, 0
0x18000fd03  mov     esi, eax
0x18000fd05  mov     [rsp+120h+var_28], r12
0x18000fd0d  and     esi, 10h
0x18000fd10  setnz   cl
0x18000fd13  mov     dword ptr [rsp+120h+var_E0], ecx
0x18000fd17  test    esi, esi
0x18000fd19  jz      short loc_18000FD74
0x18000fd1b  bt      eax, 8
0x18000fd1f  jnb     short loc_18000FD74
0x18000fd21  mov     rdx, r14; struct IMediaSample *
0x18000fd24  mov     rcx, r15; this
0x18000fd27  call    ?RemovePreroll@CWaveOutInputPin@@QEAAJPEAUIMediaSample@@@Z; CWaveOutInputPin::RemovePreroll(IMediaSample *)
0x18000fd2c  cmp     dword ptr [rdi+164h], 0
0x18000fd33  mov     r13d, eax
0x18000fd36  jz      short loc_18000FD42
0x18000fd38  mov     dword ptr [rdi+15Ch], 1
0x18000fd42  cmp     r13d, 1
0x18000fd46  jnz     short loc_18000FD6B
0x18000fd48  mov     rax, [r14]
0x18000fd4b  mov     rcx, r14
0x18000fd4e  mov     rax, [rax+78h]
0x18000fd52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd57  test    eax, eax
0x18000fd59  jnz     loc_1800104FE
0x18000fd5f  mov     [rdi+15Ch], r13d
0x18000fd66  jmp     loc_1800104FE
0x18000fd6b  test    r13d, r13d
0x18000fd6e  js      loc_1800101A9
0x18000fd74  mov     rax, [rdi+48h]
0x18000fd78  mov     rcx, r14
0x18000fd7b  movsxd  r12, dword ptr [rdi+24h]
0x18000fd7f  mov     r15d, [rdi+15Ch]
0x18000fd86  mov     [rbp+57h+var_D0], rax
0x18000fd8a  mov     [rsp+120h+var_D8], rax
0x18000fd8f  mov     rax, [rdi+28h]
0x18000fd93  mov     [rbp+57h+var_B8], rax
0x18000fd97  mov     rax, [rdi+30h]
0x18000fd9b  mov     [rbp+57h+var_C8], rax
0x18000fd9f  mov     rax, [r14]
0x18000fda2  mov     [rsp+120h+var_E8], r12d
0x18000fda7  mov     [rsp+120h+var_EC], r15d
0x18000fdac  mov     rax, [rax+78h]
0x18000fdb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdb5  test    eax, eax
0x18000fdb7  jz      short loc_18000FDBE
0x18000fdb9  test    r15d, r15d
0x18000fdbc  jz      short loc_18000FDCE
0x18000fdbe  inc     dword ptr [rdi+170h]
0x18000fdc4  mov     dword ptr [rdi+15Ch], 0
0x18000fdce  mov     ecx, [rdi+168h]
0x18000fdd4  test    ecx, ecx
0x18000fdd6  jnz     short loc_18000FDDF
0x18000fdd8  mov     eax, 989680h
0x18000fddd  jmp     short loc_18000FDEB
0x18000fddf  imul    rax, r12, 989680h
0x18000fde6  cqo
0x18000fde8  idiv    rcx
0x18000fdeb  mov     r15, [rdi+60h]
0x18000fdef  mov     [rdi+178h], rax
0x18000fdf6  mov     [rbp+57h+var_B0], 0
0x18000fdfe  mov     rcx, [r15+30h]
0x18000fe02  test    rcx, rcx
0x18000fe05  jz      short loc_18000FE23
0x18000fe07  mov     rax, [rcx]
0x18000fe0a  lea     rdx, [rbp+57h+var_B0]
0x18000fe0e  mov     rax, [rax+18h]
0x18000fe12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe17  test    eax, eax
0x18000fe19  js      short loc_18000FE23
0x18000fe1b  mov     rcx, [r15+38h]
0x18000fe1f  sub     [rbp+57h+var_B0], rcx
0x18000fe23  mov     rcx, [rdi+60h]; this
0x18000fe27  cmp     byte ptr [rcx+1C4h], 0
0x18000fe2e  jnz     short loc_18000FE56
0x18000fe30  call    ?QueueEOS@CWaveOutFilter@@AEAAJXZ; CWaveOutFilter::QueueEOS(void)
0x18000fe35  mov     esi, 1
0x18000fe3a  mov     rcx, rbx; lpCriticalSection
0x18000fe3d  mov     [rdi+158h], esi
0x18000fe43  call    cs:__imp_LeaveCriticalSection
0x18000fe4a  nop     dword ptr [rax+rax+00h]
0x18000fe4f  mov     eax, esi
0x18000fe51  jmp     loc_18001050F
0x18000fe56  cmp     dword ptr [rcx+0F4h], 0
0x18000fe5d  jnz     short loc_18000FEAE
0x18000fe5f  test    esi, esi
0x18000fe61  jz      short loc_18000FE70
0x18000fe63  mov     rax, [rbp+57h+var_B8]
0x18000fe67  mov     [rdi+150h], rax
0x18000fe6e  jmp     short loc_18000FEAE
0x18000fe70  cmp     dword ptr [rcx+128h], 1
0x18000fe77  jnz     short loc_18000FEA3
0x18000fe79  mov     rax, [r14]
0x18000fe7c  mov     rcx, r14
0x18000fe7f  mov     rax, [rax+78h]
0x18000fe83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe88  test    eax, eax
0x18000fe8a  jz      short loc_18000FEA3
0x18000fe8c  cmp     [rsp+120h+var_EC], 0
0x18000fe91  jnz     short loc_18000FEA3
0x18000fe93  mov     rax, [rdi+148h]
0x18000fe9a  mov     [rdi+150h], rax
0x18000fea1  jmp     short loc_18000FEAE
0x18000fea3  mov     qword ptr [rdi+150h], 0
0x18000feae  mov     rdx, [rdi+60h]
0x18000feb2  cmp     dword ptr [rdx+128h], 1
0x18000feb9  jnz     short loc_18000FEDA
0x18000febb  mov     rcx, [rdi+178h]
0x18000fec2  test    esi, esi
0x18000fec4  jz      short loc_18000FED3
0x18000fec6  add     rcx, [rbp+57h+var_B8]
0x18000feca  mov     [rdi+148h], rcx
0x18000fed1  jmp     short loc_18000FEDA
0x18000fed3  add     [rdi+148h], rcx
0x18000feda  cmp     dword ptr [rdx+28h], 2
0x18000fede  mov     [rsp+120h+var_F0], 0
0x18000fee6  jnz     loc_18001001C
0x18000feec  cmp     dword ptr [rdx+128h], 0FFFFFFFFh
0x18000fef3  jz      loc_18001001C
0x18000fef9  cmp     dword ptr [rdi+164h], 0
0x18000ff00  mov     r15d, dword ptr [rsp+120h+var_E0]
0x18000ff05  jnz     loc_180010021
0x18000ff0b  lea     rcx, [rdi+80h]; this
0x18000ff12  mov     edx, r15d; int
0x18000ff15  call    ?UpdateSlaveMode@CWaveSlave@@IEAAHH@Z; CWaveSlave::UpdateSlaveMode(int)
0x18000ff1a  test    eax, eax
0x18000ff1c  jz      loc_180010021
0x18000ff22  mov     rax, [rdi+60h]
0x18000ff26  cmp     dword ptr [rax+144h], 6
0x18000ff2d  jz      short loc_18000FF3C
0x18000ff2f  test    byte ptr [rdi+11Ch], 1
0x18000ff36  jz      loc_180010021
0x18000ff3c  cmp     dword ptr [rax+104h], 0
0x18000ff43  jz      short loc_18000FFA2
0x18000ff45  mov     eax, [rdi+11Ch]
0x18000ff4b  test    al, 1
0x18000ff4d  jnz     short loc_18000FFA2
0x18000ff4f  mov     rax, [r14]
0x18000ff52  mov     rcx, r14
0x18000ff55  mov     rax, [rax+78h]
0x18000ff59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff5e  mov     r13d, [rsp+120h+var_EC]
0x18000ff63  test    eax, eax
0x18000ff65  jz      short loc_18000FFA7
0x18000ff67  test    r13d, r13d
0x18000ff6a  jnz     short loc_18000FFA7
0x18000ff6c  mov     rax, [rdi+60h]
0x18000ff70  mov     r12d, [rsp+120h+var_F0]
0x18000ff75  mov     rcx, [rax+0F8h]
0x18000ff7c  mov     rax, [rbp+57h+var_B8]
0x18000ff80  mov     rdx, [rcx+10h]
0x18000ff84  cmp     rax, rdx
0x18000ff87  jle     short loc_18000FFAC
0x18000ff89  sub     rax, rdx
0x18000ff8c  cmp     rax, 493E0h
0x18000ff92  mov     eax, 1
0x18000ff97  cmovg   r12d, eax
0x18000ff9b  mov     [rsp+120h+var_F0], r12d
0x18000ffa0  jmp     short loc_18000FFAC
0x18000ffa2  mov     r13d, [rsp+120h+var_EC]
0x18000ffa7  mov     r12d, [rsp+120h+var_F0]
0x18000ffac  mov     rax, [r14]
0x18000ffaf  mov     rcx, r14
0x18000ffb2  mov     rax, [rax+78h]
0x18000ffb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffbb  test    eax, eax
0x18000ffbd  jz      short loc_18000FFCD
0x18000ffbf  test    r13d, r13d
0x18000ffc2  jnz     short loc_18000FFCD
0x18000ffc4  test    r12d, r12d
0x18000ffc7  jnz     short loc_18000FFCD
0x18000ffc9  xor     ecx, ecx
0x18000ffcb  jmp     short loc_18000FFD2
0x18000ffcd  mov     ecx, 1
0x18000ffd2  mov     rax, [rbp+57h+var_C8]
0x18000ffd6  lea     r9, [rsp+120h+var_E8]; int *
0x18000ffdb  mov     [rbp+57h+var_C8], rax
0x18000ffdf  lea     r8, [rbp+57h+var_C8]; __int64 *
0x18000ffe3  mov     rax, [rbp+57h+var_B8]
0x18000ffe7  lea     rdx, [rsp+120h+var_E0]; __int64 *
0x18000ffec  mov     dword ptr [rsp+120h+var_100], ecx; int
0x18000fff0  lea     rcx, [rdi+80h]; this
0x18000fff7  mov     [rsp+120h+var_E0], rax
0x18000fffc  call    ?AdjustSlaveClock@CWaveSlave@@IEAAJAEB_J0PEAJH@Z; CWaveSlave::AdjustSlaveClock(__int64 const &,__int64 const &,long *,int)
0x180010001  mov     r13d, eax
0x180010004  cmp     eax, 1
0x180010007  jz      loc_1800104FE
0x18001000d  test    eax, eax
0x18001000f  js      loc_1800101A9
0x180010015  mov     r12d, [rsp+120h+var_E8]
0x18001001a  jmp     short loc_180010021
0x18001001c  mov     r15d, dword ptr [rsp+120h+var_E0]
0x180010021  test    byte ptr cs:?PerflogEnableFlags@@3KA, 20h; ulong PerflogEnableFlags
0x180010028  jz      short loc_18001009B
0x18001002a  xor     edx, edx; Val
0x18001002c  lea     rcx, [rbp+57h+var_A0]; void *
0x180010030  mov     r8d, 58h ; 'X'; Size
0x180010036  call    memset_0
0x18001003b  movups  xmm0, xmmword ptr cs:GUID_AUDIORECV.Data1
0x180010042  mov     eax, 58h ; 'X'
0x180010047  mov     dword ptr [rbp+57h+var_A0.28h+4], 20000h
0x18001004e  mov     [rbp+57h+var_A0.Size], ax
0x180010052  mov     rcx, r14
0x180010055  mov     rax, [rbp+57h+var_B0]
0x180010059  mov     [rbp+57h+var_70], rax
0x18001005d  mov     rax, [rdi+28h]
0x180010061  mov     [rbp+57h+var_68], rax
0x180010065  mov     rax, [rdi+30h]
0x180010069  mov     [rbp+57h+var_60], rax
0x18001006d  mov     rax, [r14]
0x180010070  movups  xmmword ptr [rbp+57h+var_A0.18h], xmm0
  ... truncated ...
```
