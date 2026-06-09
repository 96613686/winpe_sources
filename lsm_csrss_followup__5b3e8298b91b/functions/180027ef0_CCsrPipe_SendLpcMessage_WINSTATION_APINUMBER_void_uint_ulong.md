# CCsrPipe::SendLpcMessage(_WINSTATION_APINUMBER,void *,uint,ulong)

- ea: `0x180027ef0`
- end: `0x18002877c`
- name: `?SendLpcMessage@CCsrPipe@@AEAAJW4_WINSTATION_APINUMBER@@PEAXIK@Z`
- size: `2188`
- prototype: `int __high(enum _WINSTATION_APINUMBER, void *, unsigned int, unsigned int)`
- caller_count: `21`
- callee_count: `20`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027da0`
- `0x180027df0`
- `0x180027e50`
- `0x180027ea0`
- `0x180035580`
- `0x180035690`
- `0x1800705d0`
- `0x180070660`
- `0x180070700`
- `0x180070730`
- `0x180070760`
- `0x180070790`
- `0x180070810`
- `0x180070870`
- `0x180070920`
- `0x1800709b0`
- `0x180070a30`
- `0x180070a60`
- `0x180070b10`
- `0x180070b40`
- `0x180070ba0`

## callees

- `0x180001b80`
- `0x180002cf4`
- `0x1800074c0`
- `0x180010fb0`
- `0x18001ce00`
- `0x180022a04`
- `0x180022d58`
- `0x1800245e4`
- `0x180024b9c`
- `0x180024e40`
- `0x180025070`
- `0x180025994`
- `0x1800261f4`
- `0x1800267c4`
- `0x180027ef0`
- `0x18004b830`
- `0x18004b86c`
- `0x180070e04`
- `0x18009404c`
- `0x180097010`

## import_xrefs

- `ntdll!DbgPrint` at `0x1800283fe`
- `ntdll!DbgPrint` at `0x1800283fe`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002834f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028465`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002834f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180028465`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028023`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180028023`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800286e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800286e8`

## string_xrefs

- `0x180028726`: `Task completed successfully`
- `0x1800280a2`: `Created pCommand`
- `0x180028117`: `Queuing pCommand`
- `0x1800281a9`: `Sending pCommand`
- `0x180028297`: `pCommand deleted and set to NULL`
- `0x180028393`: `Time out while sending lpc command to csrss`
- `0x1800286ad`: `Cleaning up pCommand`
- `0x1800285da`: `Skipping cleaning up pCommand because it's null`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CCsrPipe::SendLpcMessage(__int64 a1, int a2, __int64 a3, unsigned int a4, DWORD dwMilliseconds)
{
  size_t v5; // rdi
  __int64 v7; // r13
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // edi
  BOOL v13; // ecx
  _BYTE *v14; // rax
  _BYTE *v15; // rbx
  const char *v16; // r14
  HANDLE EventW; // rax
  int v18; // r12d
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  _QWORD *v24; // rcx
  _QWORD *v25; // rcx
  int v26; // eax
  _QWORD *v27; // rcx
  int v28; // r8d
  int v29; // r9d
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  const char *v33; // rax
  __int16 *v34; // rdx
  DWORD v35; // edi
  LARGE_INTEGER CriticalSectionTimeout; // rcx
  unsigned int v37; // r14d
  signed int v38; // eax
  __int64 v39; // rax
  _QWORD *v40; // rcx
  __int64 v41; // rax
  void *v42; // rcx
  const char *v43; // rax
  int *v44; // rdx
  _QWORD v46[2]; // [rsp+50h] [rbp-21h] BYREF
  const char *v47; // [rsp+60h] [rbp-11h] BYREF
  const char *v48; // [rsp+68h] [rbp-9h] BYREF
  const char *v49; // [rsp+70h] [rbp-1h] BYREF
  _QWORD v50[9]; // [rsp+78h] [rbp+7h] BYREF
  const char *v51; // [rsp+E0h] [rbp+6Fh] BYREF
  int v52; // [rsp+E8h] [rbp+77h] BYREF

  v5 = a4;
  v7 = a2;
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v51 = "Sending LPC Message to Csrss";
    v46[0] = "CCsrPipe::SendLpcMessage";
    v47 = "CsrssPipe SendMessage";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"CsrssPipe SendMessage",
      (unsigned int)&byte_1800C5A17,
      a3,
      a4,
      (__int64)&v47,
      (__int64)v46,
      (__int64)&v51);
  }
  if ( !a3 )
  {
    _DbgPrintMessage(8, "SendLpcMessage: pMsg is NULL");
LABEL_5:
    v12 = -2147024809;
    goto LABEL_72;
  }
  if ( (_DWORD)v7 == 9 )
  {
    v13 = *(_BYTE *)(a3 + 16416) != 0;
    if ( v13 != (*(_QWORD *)(a3 + 16424) == 0) )
    {
      _DbgPrintMessage(
        8,
        "Message structure inconsistency: DoNotWait=%d but pStatus=%p",
        *(unsigned __int8 *)(a3 + 16416));
      goto LABEL_5;
    }
    if ( v13 != (*(_QWORD *)(a3 + 16408) == 0) )
    {
      _DbgPrintMessage(
        8,
        "Message structure inconsistency: DoNotWait=%d but pResponse=%p",
        *(unsigned __int8 *)(a3 + 16416));
      goto LABEL_5;
    }
  }
  v14 = operator new(0x4088u, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( !v14 )
  {
    v12 = -2147024882;
    goto LABEL_72;
  }
  v16 = (const char *)dwMilliseconds;
  if ( !dwMilliseconds )
  {
    v14[72] = 0;
    *((_QWORD *)v14 + 2) = 0;
LABEL_17:
    v18 = (unsigned __int8)v15[72];
    *((_DWORD *)v15 + 17) = v7;
    *((_DWORD *)v15 + 16) = _InterlockedIncrement((volatile signed __int32 *)(a1 + 1864));
    *((_DWORD *)v15 + 19) = -1073741823;
    memcpy_0(v15 + 80, (const void *)a3, v5);
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      v51 = (const char *)*((unsigned int *)v15 + 16);
      v47 = (const char *)(&CSR_LPC_NAME)[v7];
      v52 = v18;
      v46[0] = v15;
      v48 = "Created pCommand";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (unsigned int)&CSR_LPC_NAME,
        (unsigned int)&word_1800C59B6,
        v19,
        v20,
        (__int64)&v48,
        (__int64)v46,
        (__int64)&v52,
        (__int64)&v47,
        (__int64)&v51);
    }
    CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v46, (struct CResource *)(a1 + 1688));
    if ( !*(_DWORD *)(a1 + 1848) )
    {
      if ( (unsigned int)dword_1800DA020 > 5 )
      {
        v51 = (const char *)*((unsigned int *)v15 + 16);
        v48 = v15;
        v47 = "Queuing pCommand";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v21,
          (unsigned int)byte_1800C5969,
          v22,
          v23,
          (__int64)&v47,
          (__int64)&v48,
          (__int64)&v51);
      }
      v24 = *(_QWORD **)(a1 + 1800);
      if ( *v24 == a1 + 1792 )
      {
        *(_QWORD *)v15 = a1 + 1792;
        *((_QWORD *)v15 + 1) = v24;
        *v24 = v15;
        *(_QWORD *)(a1 + 1800) = v15;
        goto LABEL_38;
      }
LABEL_89:
      __fastfail(3u);
    }
    *(_OWORD *)(v15 + 24) = *(_OWORD *)(a1 + 1808);
    *(_OWORD *)(v15 + 40) = *(_OWORD *)(a1 + 1824);
    *((_QWORD *)v15 + 7) = *(_QWORD *)(a1 + 1840);
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      v51 = (const char *)*((unsigned int *)v15 + 16);
      v48 = v15;
      v47 = "Sending pCommand";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v21,
        (unsigned int)&dword_1800C591C,
        v22,
        v23,
        (__int64)&v47,
        (__int64)&v48,
        (__int64)&v51);
    }
    if ( v15[72] )
    {
      v25 = *(_QWORD **)(a1 + 1800);
      if ( *v25 != a1 + 1792 )
        goto LABEL_89;
      *(_QWORD *)v15 = a1 + 1792;
      *((_QWORD *)v15 + 1) = v25;
      *v25 = v15;
      *(_QWORD *)(a1 + 1800) = v15;
    }
    v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _BYTE *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 1672) + 16LL))(
            *(_QWORD *)(a1 + 1672),
            *(_QWORD *)(a1 + 1856),
            0,
            v15 + 24,
            0,
            0,
            0,
            0,
            0);
    v12 = v26 | 0x10000000;
    if ( v26 < 0 )
    {
      if ( v15[72] )
      {
        v41 = *(_QWORD *)v15;
        if ( *(_BYTE **)(*(_QWORD *)v15 + 8LL) != v15 )
          goto LABEL_89;
        v27 = (_QWORD *)*((_QWORD *)v15 + 1);
        if ( (_BYTE *)*v27 != v15 )
          goto LABEL_89;
        *v27 = v41;
        *(_QWORD *)(v41 + 8) = v27;
      }
      if ( (unsigned int)dword_1800DA020 > 3 )
      {
        v51 = "SendLpcMessage";
        v52 = v12;
        v50[0] = "NtReplyPort";
        v49 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)v27,
          (unsigned int)&word_1800C586E,
          v28,
          v29,
          (__int64)&v49,
          (__int64)v50,
          (__int64)&v52,
          (__int64)&v51);
      }
      CAutoLock::Unlock((CAutoLock *)v46);
      goto LABEL_81;
    }
    *(_DWORD *)(a1 + 1848) = 0;
    if ( v15[72] )
    {
LABEL_38:
      CAutoLock::Unlock((CAutoLock *)v46);
      if ( !v18 )
      {
        v12 = 0;
        goto LABEL_72;
      }
      v35 = -1;
      if ( (_DWORD)v16 == -1 && (unsigned int)CUtils::IsKernelDebuggerAttached() )
      {
        CriticalSectionTimeout = NtCurrentPeb()->CriticalSectionTimeout;
        if ( CriticalSectionTimeout.QuadPart != -1
          && !((unsigned __int64)(CriticalSectionTimeout.QuadPart / -20000) >> 32) )
        {
          v35 = CriticalSectionTimeout.QuadPart / -20000;
          if ( v35 < 0x927C0 )
            v35 = 600000;
        }
        v37 = 0;
        while ( WaitForSingleObject(*((HANDLE *)v15 + 2), v35) == 258 )
        {
          if ( (unsigned int)dword_1800DA020 > 2 )
          {
            v51 = (const char *)a1;
            v48 = (const char *)(a1 + 1792);
            v47 = v15;
            v46[0] = *(int *)(a1 + 1592);
            v49 = (const char *)*(unsigned int *)(a1 + 1596);
            v50[0] = "Time out while sending lpc command to csrss";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              v9,
              (unsigned int)byte_1800C5753,
              v10,
              v11,
              (__int64)v50,
              (__int64)&v49,
              (__int64)v46,
              (__int64)&v47,
              (__int64)&v48,
              (__int64)&v51);
          }
          ++v37;
          if ( (_DWORD)v7 != 7 || v37 >= 3 )
          {
            __debugbreak();
            DbgPrint("CsrPipe=%p\n", (const void *)a1);
          }
        }
      }
      else
      {
        if ( (unsigned int)dword_1800DA020 > 4 )
        {
          v51 = (const char *)*((unsigned int *)v15 + 16);
          v50[0] = v15;
          v49 = v16;
          v48 = "Waiting for reply";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            v9,
            (unsigned int)&unk_1800C5818,
            v10,
            v11,
            (__int64)&v48,
            (__int64)&v49,
            (__int64)v50,
            (__int64)&v51);
        }
        v38 = WaitForSingleObject(*((HANDLE *)v15 + 2), (DWORD)v16);
        v12 = v38;
        if ( v38 > 0 )
          v12 = (unsigned __int16)v38 | 0x80070000;
        if ( v12 < 0 )
        {
          CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v50, (struct CResource *)(a1 + 1688));
          v39 = *(_QWORD *)v15;
          if ( *(_QWORD *)v15 )
          {
            if ( *(_BYTE **)(v39 + 8) != v15 || (v40 = (_QWORD *)*((_QWORD *)v15 + 1), (_BYTE *)*v40 != v15) )
              __fastfail(3u);
            *v40 = v39;
            *(_QWORD *)(v39 + 8) = v40;
          }
          CAutoLock::Unlock((CAutoLock *)v50);
          if ( (unsigned int)dword_1800DA020 > 3 )
          {
            v51 = "SendLpcMessage";
            v52 = v12;
            v50[0] = "WaitForSingleObject";
            v49 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v9,
              (unsigned int)&dword_1800C57D4,
              v10,
              v11,
              (__int64)&v49,
              (__int64)v50,
              (__int64)&v52,
              (__int64)&v51);
          }
LABEL_69:
          if ( v15 )
            goto LABEL_81;
LABEL_72:
          if ( (unsigned int)dword_1800DA020 > 4 )
          {
            v51 = "Skipping cleaning up pCommand because it's null";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v9,
              (unsigned int)&word_1800C5676,
              v10,
              v11,
              (__int64)&v51);
          }
          goto LABEL_86;
        }
      }
      v12 = *((_DWORD *)v15 + 19) | 0x10000000;
      if ( !*((_DWORD *)v15 + 19) )
      {
        if ( (unsigned int)dword_1800DA020 > 4 )
        {
          v51 = (const char *)*((unsigned int *)v15 + 16);
          v50[0] = (&CSR_LPC_NAME)[*((int *)v15 + 17)];
          v49 = v15;
          v48 = "Got a successful reply";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            (unsigned int)&CSR_LPC_NAME,
            (unsigned int)byte_1800C56ED,
            v10,
            v11,
            (__int64)&v48,
            (__int64)&v49,
            (__int64)v50,
            (__int64)&v51);
        }
        if ( *((_DWORD *)v15 + 17) == 19 )
          *(_DWORD *)(a3 + 8240) = *((_DWORD *)v15 + 2080);
      }
      goto LABEL_69;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_CcsrOobRead>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFix_CcsrOobRead>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned int)dword_1800DA020 > 4 )
      {
        v33 = (const char *)*((unsigned int *)v15 + 16);
        v34 = (__int16 *)&byte_1800C58E7;
LABEL_36:
        v51 = v33;
        v48 = "pCommand deleted and set to NULL";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v30,
          (_DWORD)v34,
          v31,
          v32,
          (__int64)&v48,
          (__int64)&v51);
      }
    }
    else if ( (unsigned int)dword_1800DA020 > 4 )
    {
      v33 = (const char *)*(unsigned int *)(a3 + 40);
      v34 = word_1800C58B2;
      goto LABEL_36;
    }
    operator delete(v15, (const struct std::nothrow_t *)0x4088);
    v15 = 0;
    goto LABEL_38;
  }
  v14[72] = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)v15 + 2) = EventW;
  if ( EventW )
    goto LABEL_17;
  v12 = -2147024882;
LABEL_81:
  if ( (unsigned int)dword_1800DA020 > 4 )
  {
    v51 = (const char *)*((unsigned int *)v15 + 16);
    v50[0] = v15;
    v49 = "Cleaning up pCommand";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v9,
      (unsigned int)&unk_1800C56A0,
      v10,
      v11,
      (__int64)&v49,
      (__int64)v50,
      (__int64)&v51);
  }
  v42 = (void *)*((_QWORD *)v15 + 2);
  if ( v42 )
    CloseHandle(v42);
  operator delete(v15, (const struct std::nothrow_t *)0x4088);
LABEL_86:
  if ( v12 >= 0 )
  {
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      v43 = "Task completed successfully";
      v44 = &dword_1800C55F4;
      goto LABEL_92;
    }
  }
  else if ( (unsigned int)dword_1800DA020 > 2 )
  {
    v43 = "CsrssPipe SendMessage";
    v44 = (int *)byte_1800C5631;
LABEL_92:
    v50[0] = v43;
    v52 = v12;
    v51 = "CCsrPipe::SendLpcMessage";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v9,
      (_DWORD)v44,
      v10,
      v11,
      (__int64)v50,
      (__int64)&v51,
      (__int64)&v52);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180027ef0  mov     [rsp-8+arg_0], rbx
0x180027ef5  push    rbp
0x180027ef6  push    rsi
0x180027ef7  push    rdi
0x180027ef8  push    r12
0x180027efa  push    r13
0x180027efc  push    r14
0x180027efe  push    r15
0x180027f00  lea     rbp, [rsp-1Fh]
0x180027f05  sub     rsp, 90h
0x180027f0c  mov     edi, r9d
0x180027f0f  mov     r15, r8
0x180027f12  movsxd  r13, edx
0x180027f15  mov     rsi, rcx
0x180027f18  mov     eax, cs:dword_1800DA020
0x180027f1e  lea     r12, aCcsrpipeSendlp; "CCsrPipe::SendLpcMessage"
0x180027f25  lea     rcx, aCsrsspipeSendm; "CsrssPipe SendMessage"
0x180027f2c  cmp     eax, 4
0x180027f2f  jbe     short loc_180027F6B
0x180027f31  lea     rax, aSendingLpcMess; "Sending LPC Message to Csrss"
0x180027f38  mov     [rbp+4Fh+arg_10], rax
0x180027f3c  mov     [rbp+4Fh+var_70], r12
0x180027f40  mov     [rbp+4Fh+var_60], rcx
0x180027f44  lea     rax, [rbp+4Fh+arg_10]
0x180027f48  mov     [rsp+0C0h+var_90], rax
0x180027f4d  lea     rax, [rbp+4Fh+var_70]
0x180027f51  mov     [rsp+0C0h+var_98], rax
0x180027f56  lea     rax, [rbp+4Fh+var_60]
0x180027f5a  mov     [rsp+0C0h+var_A0], rax
0x180027f5f  lea     rdx, byte_1800C5A17
0x180027f66  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180027f6b  test    r15, r15
0x180027f6e  jnz     short loc_180027F8A
0x180027f70  lea     rdx, aSendlpcmessage_0; "SendLpcMessage: pMsg is NULL"
0x180027f77  lea     ecx, [r15+8]; int
0x180027f7b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027f80  mov     edi, 80070057h
0x180027f85  jmp     loc_1800285CB
0x180027f8a  cmp     r13d, 9
0x180027f8e  jnz     short loc_180027FE7
0x180027f90  movzx   edx, byte ptr [r15+4020h]
0x180027f98  mov     r9, [r15+4028h]
0x180027f9f  xor     ecx, ecx
0x180027fa1  test    dl, dl
0x180027fa3  setnz   cl
0x180027fa6  xor     eax, eax
0x180027fa8  test    r9, r9
0x180027fab  setz    al
0x180027fae  cmp     ecx, eax
0x180027fb0  jz      short loc_180027FC8
0x180027fb2  mov     r8d, edx
0x180027fb5  lea     rdx, aMessageStructu; "Message structure inconsistency: DoNotW"...
0x180027fbc  mov     ecx, 8; int
0x180027fc1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180027fc6  jmp     short loc_180027F80
0x180027fc8  mov     r9, [r15+4018h]
0x180027fcf  xor     eax, eax
0x180027fd1  test    r9, r9
0x180027fd4  setz    al
0x180027fd7  cmp     ecx, eax
0x180027fd9  jz      short loc_180027FE7
0x180027fdb  mov     r8d, edx
0x180027fde  lea     rdx, aMessageStructu_0; "Message structure inconsistency: DoNotW"...
0x180027fe5  jmp     short loc_180027FBC
0x180027fe7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180027fee  mov     ecx, 4088h; unsigned __int64
0x180027ff3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180027ff8  mov     rbx, rax
0x180027ffb  test    rax, rax
0x180027ffe  jnz     short loc_18002800A
0x180028000  mov     edi, 8007000Eh
0x180028005  jmp     loc_1800285CB
0x18002800a  mov     r14d, [rbp+4Fh+dwMilliseconds]
0x18002800e  test    r14d, r14d
0x180028011  jz      short loc_18002803C
0x180028013  mov     byte ptr [rax+48h], 1
0x180028017  xor     r9d, r9d; lpName
0x18002801a  xor     r8d, r8d; bInitialState
0x18002801d  lea     edx, [r9+1]; bManualReset
0x180028021  xor     ecx, ecx; lpEventAttributes
0x180028023  call    cs:__imp_CreateEventW
0x180028029  mov     [rbx+10h], rax
0x18002802d  test    rax, rax
0x180028030  jnz     short loc_180028048
0x180028032  mov     edi, 8007000Eh
0x180028037  jmp     loc_180028697
0x18002803c  mov     byte ptr [rax+48h], 0
0x180028040  mov     qword ptr [rax+10h], 0
0x180028048  movzx   r12d, byte ptr [rbx+48h]
0x18002804d  mov     [rbx+44h], r13d
0x180028051  mov     eax, 1
0x180028056  lock xadd [rsi+748h], eax
0x18002805e  inc     eax
0x180028060  mov     [rbx+40h], eax
0x180028063  mov     dword ptr [rbx+4Ch], 0C0000001h
0x18002806a  mov     r8, rdi; Size
0x18002806d  lea     rcx, [rbx+50h]; void *
0x180028071  mov     rdx, r15; Src
0x180028074  call    memcpy_0
0x180028079  mov     eax, cs:dword_1800DA020
0x18002807f  lea     rcx, ?CSR_LPC_NAME@@3PAPEBDA; char const * near * CSR_LPC_NAME
0x180028086  cmp     eax, 5
0x180028089  jbe     short loc_1800280E6
0x18002808b  mov     eax, [rbx+40h]
0x18002808e  mov     [rbp+4Fh+arg_10], rax
0x180028092  mov     rax, [rcx+r13*8]
0x180028096  mov     [rbp+4Fh+var_60], rax
0x18002809a  mov     [rbp+4Fh+arg_18], r12d
0x18002809e  mov     [rbp+4Fh+var_70], rbx
0x1800280a2  lea     rax, aCreatedPcomman; "Created pCommand"
0x1800280a9  mov     [rbp+4Fh+var_58], rax
0x1800280ad  lea     rax, [rbp+4Fh+arg_10]
0x1800280b1  mov     [rsp+0C0h+var_80], rax
0x1800280b6  lea     rax, [rbp+4Fh+var_60]
0x1800280ba  mov     [rsp+0C0h+var_88], rax
0x1800280bf  lea     rax, [rbp+4Fh+arg_18]
0x1800280c3  mov     [rsp+0C0h+var_90], rax
0x1800280c8  lea     rax, [rbp+4Fh+var_70]
0x1800280cc  mov     [rsp+0C0h+var_98], rax
0x1800280d1  lea     rax, [rbp+4Fh+var_58]
0x1800280d5  mov     [rsp+0C0h+var_A0], rax
0x1800280da  lea     rdx, word_1800C59B6
0x1800280e1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800280e6  lea     rdx, [rsi+698h]; struct CResource *
0x1800280ed  lea     rcx, [rbp+4Fh+var_70]; this
0x1800280f1  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800280f6  nop
0x1800280f7  xor     edx, edx
0x1800280f9  cmp     [rsi+738h], edx
0x1800280ff  jnz     short loc_180028170
0x180028101  mov     eax, cs:dword_1800DA020
0x180028107  cmp     eax, 5
0x18002810a  jbe     short loc_180028149
0x18002810c  mov     eax, [rbx+40h]
0x18002810f  mov     [rbp+4Fh+arg_10], rax
0x180028113  mov     [rbp+4Fh+var_58], rbx
0x180028117  lea     rax, aQueuingPcomman; "Queuing pCommand"
0x18002811e  mov     [rbp+4Fh+var_60], rax
0x180028122  lea     rax, [rbp+4Fh+arg_10]
0x180028126  mov     [rsp+0C0h+var_90], rax
0x18002812b  lea     rax, [rbp+4Fh+var_58]
0x18002812f  mov     [rsp+0C0h+var_98], rax
0x180028134  lea     rax, [rbp+4Fh+var_60]
0x180028138  mov     [rsp+0C0h+var_A0], rax
0x18002813d  lea     rdx, byte_1800C5969
0x180028144  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180028149  lea     rax, [rsi+700h]
0x180028150  mov     rcx, [rax+8]
0x180028154  cmp     [rcx], rax
0x180028157  jnz     loc_18002871A
0x18002815d  mov     [rbx], rax
0x180028160  mov     [rbx+8], rcx
0x180028164  mov     [rcx], rbx
0x180028167  mov     [rax+8], rbx
0x18002816b  jmp     loc_1800282C8
0x180028170  movups  xmm0, xmmword ptr [rsi+710h]
0x180028177  movups  xmmword ptr [rbx+18h], xmm0
0x18002817b  movups  xmm1, xmmword ptr [rsi+720h]
0x180028182  movups  xmmword ptr [rbx+28h], xmm1
0x180028186  movsd   xmm0, qword ptr [rsi+730h]
0x18002818e  movsd   qword ptr [rbx+38h], xmm0
0x180028193  mov     eax, cs:dword_1800DA020
0x180028199  cmp     eax, 5
0x18002819c  jbe     short loc_1800281DD
0x18002819e  mov     eax, [rbx+40h]
0x1800281a1  mov     [rbp+4Fh+arg_10], rax
0x1800281a5  mov     [rbp+4Fh+var_58], rbx
0x1800281a9  lea     rax, aSendingPcomman; "Sending pCommand"
0x1800281b0  mov     [rbp+4Fh+var_60], rax
0x1800281b4  lea     rax, [rbp+4Fh+arg_10]
0x1800281b8  mov     [rsp+0C0h+var_90], rax
0x1800281bd  lea     rax, [rbp+4Fh+var_58]
0x1800281c1  mov     [rsp+0C0h+var_98], rax
0x1800281c6  lea     rax, [rbp+4Fh+var_60]
0x1800281ca  mov     [rsp+0C0h+var_A0], rax
0x1800281cf  lea     rdx, dword_1800C591C
0x1800281d6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800281db  xor     edx, edx
0x1800281dd  cmp     [rbx+48h], dl
0x1800281e0  jz      short loc_180028204
0x1800281e2  lea     rax, [rsi+700h]
0x1800281e9  mov     rcx, [rax+8]
0x1800281ed  cmp     [rcx], rax
0x1800281f0  jnz     loc_18002871A
0x1800281f6  mov     [rbx], rax
0x1800281f9  mov     [rbx+8], rcx
0x1800281fd  mov     [rcx], rbx
0x180028200  mov     [rax+8], rbx
0x180028204  mov     rcx, [rsi+688h]
0x18002820b  mov     rax, [rcx]
0x18002820e  mov     [rsp+0C0h+var_80], rdx
0x180028213  mov     [rsp+0C0h+var_88], rdx
0x180028218  mov     [rsp+0C0h+var_90], rdx
0x18002821d  mov     [rsp+0C0h+var_98], rdx
0x180028222  mov     [rsp+0C0h+var_A0], rdx
0x180028227  lea     r9, [rbx+18h]
0x18002822b  xor     r8d, r8d
0x18002822e  mov     rdx, [rsi+740h]
0x180028235  mov     rax, [rax+10h]
0x180028239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002823e  mov     edi, eax
0x180028240  or      edi, 10000000h
0x180028246  jl      loc_1800285FF
0x18002824c  mov     dword ptr [rsi+738h], 0
0x180028256  cmp     byte ptr [rbx+48h], 0
0x18002825a  jnz     short loc_1800282C8
0x18002825c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_CcsrOobRead@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_CcsrOobRead@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_CcsrOobRead> `wil::Feature<__WilFeatureTraits_Feature_BugFix_CcsrOobRead>::GetImpl(void)'::`2'::impl
0x180028263  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_CcsrOobRead@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_CcsrOobRead>::__private_IsEnabled(void)
0x180028268  test    al, al
0x18002826a  mov     eax, cs:dword_1800DA020
0x180028270  jz      short loc_180028283
0x180028272  cmp     eax, 4
0x180028275  jbe     short loc_1800282B9
0x180028277  mov     eax, [rbx+40h]
0x18002827a  lea     rdx, byte_1800C58E7
0x180028281  jmp     short loc_180028293
0x180028283  cmp     eax, 4
0x180028286  jbe     short loc_1800282B9
0x180028288  mov     eax, [r15+28h]
0x18002828c  lea     rdx, word_1800C58B2
0x180028293  mov     [rbp+4Fh+arg_10], rax
0x180028297  lea     rax, aPcommandDelete; "pCommand deleted and set to NULL"
0x18002829e  mov     [rbp+4Fh+var_58], rax
0x1800282a2  lea     rax, [rbp+4Fh+arg_10]
0x1800282a6  mov     [rsp+0C0h+var_98], rax
0x1800282ab  lea     rax, [rbp+4Fh+var_58]
0x1800282af  mov     [rsp+0C0h+var_A0], rax
0x1800282b4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800282b9  mov     edx, 4088h; struct std::nothrow_t *
0x1800282be  mov     rcx, rbx; void *
0x1800282c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800282c6  xor     ebx, ebx
0x1800282c8  lea     rcx, [rbp+4Fh+var_70]; this
0x1800282cc  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800282d1  nop
0x1800282d2  test    r12d, r12d
0x1800282d5  jz      loc_1800285C2
0x1800282db  or      edi, 0FFFFFFFFh
0x1800282de  cmp     r14d, edi
0x1800282e1  jnz     loc_180028409
0x1800282e7  call    ?IsKernelDebuggerAttached@CUtils@@SAHXZ; CUtils::IsKernelDebuggerAttached(void)
0x1800282ec  test    eax, eax
0x1800282ee  jz      loc_180028409
0x1800282f4  mov     rcx, gs:60h
0x1800282fd  mov     rcx, [rcx+0C0h]
0x180028304  mov     rax, rcx
0x180028307  shr     rax, 20h
0x18002830b  cmp     eax, 0FFFFFFFFh
0x18002830e  jnz     short loc_180028314
0x180028310  cmp     ecx, edi
0x180028312  jz      short loc_180028346
0x180028314  mov     rax, 0CB923A29C779A6B5h
0x18002831e  imul    rcx
0x180028321  sar     rdx, 0Ch
0x180028325  mov     rax, rdx
0x180028328  shr     rax, 3Fh
0x18002832c  add     rdx, rax
0x18002832f  mov     rax, rdx
0x180028332  shr     rax, 20h
0x180028336  test    eax, eax
0x180028338  jnz     short loc_180028346
0x18002833a  mov     edi, edx
0x18002833c  mov     eax, 927C0h
0x180028341  cmp     edx, eax
0x180028343  cmovb   edi, eax
0x180028346  xor     r14d, r14d
0x180028349  mov     edx, edi; dwMilliseconds
0x18002834b  mov     rcx, [rbx+10h]; hHandle
0x18002834f  call    cs:__imp_WaitForSingleObject
0x180028355  cmp     eax, 102h
0x18002835a  jnz     loc_18002852D
0x180028360  mov     eax, cs:dword_1800DA020
0x180028366  cmp     eax, 2
0x180028369  jbe     short loc_1800283E0
0x18002836b  mov     [rbp+4Fh+arg_10], rsi
0x18002836f  lea     rax, [rsi+700h]
0x180028376  mov     [rbp+4Fh+var_58], rax
0x18002837a  mov     [rbp+4Fh+var_60], rbx
0x18002837e  movsxd  rax, dword ptr [rsi+638h]
0x180028385  mov     [rbp+4Fh+var_70], rax
0x180028389  mov     eax, [rsi+63Ch]
0x18002838f  mov     [rbp+4Fh+var_50], rax
0x180028393  lea     rax, aTimeOutWhileSe; "Time out while sending lpc command to c"...
0x18002839a  mov     [rbp+4Fh+var_48], rax
0x18002839e  lea     rax, [rbp+4Fh+arg_10]
0x1800283a2  mov     [rsp+0C0h+var_78], rax
0x1800283a7  lea     rax, [rbp+4Fh+var_58]
0x1800283ab  mov     [rsp+0C0h+var_80], rax
0x1800283b0  lea     rax, [rbp+4Fh+var_60]
0x1800283b4  mov     [rsp+0C0h+var_88], rax
0x1800283b9  lea     rax, [rbp+4Fh+var_70]
0x1800283bd  mov     [rsp+0C0h+var_90], rax
0x1800283c2  lea     rax, [rbp+4Fh+var_50]
0x1800283c6  mov     [rsp+0C0h+var_98], rax
0x1800283cb  lea     rax, [rbp+4Fh+var_48]
0x1800283cf  mov     [rsp+0C0h+var_A0], rax
0x1800283d4  lea     rdx, byte_1800C5753
0x1800283db  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800283e0  inc     r14d
0x1800283e3  cmp     r13d, 7
  ... truncated ...
```
