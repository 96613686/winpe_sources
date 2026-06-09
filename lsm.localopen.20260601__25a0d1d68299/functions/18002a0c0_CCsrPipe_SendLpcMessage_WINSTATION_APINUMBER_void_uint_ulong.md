# CCsrPipe::SendLpcMessage(_WINSTATION_APINUMBER,void *,uint,ulong)

- ea: `0x18002a0c0`
- end: `0x18002a96b`
- name: `?SendLpcMessage@CCsrPipe@@AEAAJW4_WINSTATION_APINUMBER@@PEAXIK@Z`
- size: `2219`
- prototype: `int __high(enum _WINSTATION_APINUMBER, void *, unsigned int, unsigned int)`
- caller_count: `21`
- callee_count: `20`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029f60`
- `0x180029fb0`
- `0x18002a010`
- `0x18002a070`
- `0x180037720`
- `0x180037830`
- `0x180074670`
- `0x180074700`
- `0x1800747a0`
- `0x1800747d0`
- `0x180074800`
- `0x180074830`
- `0x1800748b0`
- `0x180074910`
- `0x1800749c0`
- `0x180074a50`
- `0x180074ae0`
- `0x180074b10`
- `0x180074bc0`
- `0x180074bf0`
- `0x180074c50`

## callees

- `0x180001b90`
- `0x180002d0c`
- `0x1800077a0`
- `0x1800129d0`
- `0x180014b20`
- `0x1800248e8`
- `0x180026238`
- `0x180026548`
- `0x180026b1c`
- `0x180026e3c`
- `0x18002701c`
- `0x1800279bc`
- `0x1800282e0`
- `0x1800288ac`
- `0x18002a0c0`
- `0x18004ec20`
- `0x18004ec5c`
- `0x180074f24`
- `0x18009959c`
- `0x18009c010`

## import_xrefs

- `ntdll!DbgPrint` at `0x18002a5da`
- `ntdll!DbgPrint` at `0x18002a5da`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a525`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a647`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a525`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002a647`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002a1f3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002a1f3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a8d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a8d0`

## string_xrefs

- `0x18002a914`: `Task completed successfully`
- `0x18002a278`: `Created pCommand`
- `0x18002a2ed`: `Queuing pCommand`
- `0x18002a37f`: `Sending pCommand`
- `0x18002a46d`: `pCommand deleted and set to NULL`
- `0x18002a56f`: `Time out while sending lpc command to csrss`
- `0x18002a895`: `Cleaning up pCommand`
- `0x18002a7c2`: `Skipping cleaning up pCommand because it's null`

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
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v51 = "Sending LPC Message to Csrss";
    v46[0] = "CCsrPipe::SendLpcMessage";
    v47 = "CsrssPipe SendMessage";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"CsrssPipe SendMessage",
      (unsigned int)&byte_1800CAB9F,
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
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      v51 = (const char *)*((unsigned int *)v15 + 16);
      v47 = (const char *)(&CSR_LPC_NAME)[v7];
      v52 = v18;
      v46[0] = v15;
      v48 = "Created pCommand";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (unsigned int)&CSR_LPC_NAME,
        (unsigned int)&word_1800CAB3E,
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
      if ( (unsigned int)dword_1800DF020 > 5 )
      {
        v51 = (const char *)*((unsigned int *)v15 + 16);
        v48 = v15;
        v47 = "Queuing pCommand";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v21,
          (unsigned int)byte_1800CAAF1,
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
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      v51 = (const char *)*((unsigned int *)v15 + 16);
      v48 = v15;
      v47 = "Sending pCommand";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v21,
        (unsigned int)&dword_1800CAAA4,
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
      if ( (unsigned int)dword_1800DF020 > 3 )
      {
        v51 = "SendLpcMessage";
        v52 = v12;
        v50[0] = "NtReplyPort";
        v49 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (_DWORD)v27,
          (unsigned int)&word_1800CA9F6,
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
          if ( (unsigned int)dword_1800DF020 > 2 )
          {
            v51 = (const char *)a1;
            v48 = (const char *)(a1 + 1792);
            v47 = v15;
            v46[0] = *(int *)(a1 + 1592);
            v49 = (const char *)*(unsigned int *)(a1 + 1596);
            v50[0] = "Time out while sending lpc command to csrss";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              v9,
              (unsigned int)byte_1800CA8DB,
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
        if ( (unsigned int)dword_1800DF020 > 4 )
        {
          v51 = (const char *)*((unsigned int *)v15 + 16);
          v50[0] = v15;
          v49 = v16;
          v48 = "Waiting for reply";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            v9,
            (unsigned int)&unk_1800CA9A0,
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
          if ( (unsigned int)dword_1800DF020 > 3 )
          {
            v51 = "SendLpcMessage";
            v52 = v12;
            v50[0] = "WaitForSingleObject";
            v49 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v9,
              (unsigned int)&dword_1800CA95C,
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
          if ( (unsigned int)dword_1800DF020 > 4 )
          {
            v51 = "Skipping cleaning up pCommand because it's null";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v9,
              (unsigned int)&word_1800CA7FE,
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
        if ( (unsigned int)dword_1800DF020 > 4 )
        {
          v51 = (const char *)*((unsigned int *)v15 + 16);
          v50[0] = (&CSR_LPC_NAME)[*((int *)v15 + 17)];
          v49 = v15;
          v48 = "Got a successful reply";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
            (unsigned int)&CSR_LPC_NAME,
            (unsigned int)byte_1800CA875,
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
      if ( (unsigned int)dword_1800DF020 > 4 )
      {
        v33 = (const char *)*((unsigned int *)v15 + 16);
        v34 = (__int16 *)&byte_1800CAA6F;
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
    else if ( (unsigned int)dword_1800DF020 > 4 )
    {
      v33 = (const char *)*(unsigned int *)(a3 + 40);
      v34 = word_1800CAA3A;
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
  if ( (unsigned int)dword_1800DF020 > 4 )
  {
    v51 = (const char *)*((unsigned int *)v15 + 16);
    v50[0] = v15;
    v49 = "Cleaning up pCommand";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v9,
      (unsigned int)&unk_1800CA828,
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
    if ( (unsigned int)dword_1800DF020 > 5 )
    {
      v43 = "Task completed successfully";
      v44 = &dword_1800CA77C;
      goto LABEL_92;
    }
  }
  else if ( (unsigned int)dword_1800DF020 > 2 )
  {
    v43 = "CsrssPipe SendMessage";
    v44 = (int *)byte_1800CA7B9;
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
0x18002a0c0  mov     [rsp-8+arg_0], rbx
0x18002a0c5  push    rbp
0x18002a0c6  push    rsi
0x18002a0c7  push    rdi
0x18002a0c8  push    r12
0x18002a0ca  push    r13
0x18002a0cc  push    r14
0x18002a0ce  push    r15
0x18002a0d0  lea     rbp, [rsp-1Fh]
0x18002a0d5  sub     rsp, 90h
0x18002a0dc  mov     edi, r9d
0x18002a0df  mov     r15, r8
0x18002a0e2  movsxd  r13, edx
0x18002a0e5  mov     rsi, rcx
0x18002a0e8  mov     eax, cs:dword_1800DF020
0x18002a0ee  lea     r12, aCcsrpipeSendlp; "CCsrPipe::SendLpcMessage"
0x18002a0f5  lea     rcx, aCsrsspipeSendm; "CsrssPipe SendMessage"
0x18002a0fc  cmp     eax, 4
0x18002a0ff  jbe     short loc_18002A13B
0x18002a101  lea     rax, aSendingLpcMess; "Sending LPC Message to Csrss"
0x18002a108  mov     [rbp+4Fh+arg_10], rax
0x18002a10c  mov     [rbp+4Fh+var_70], r12
0x18002a110  mov     [rbp+4Fh+var_60], rcx
0x18002a114  lea     rax, [rbp+4Fh+arg_10]
0x18002a118  mov     [rsp+0C0h+var_90], rax
0x18002a11d  lea     rax, [rbp+4Fh+var_70]
0x18002a121  mov     [rsp+0C0h+var_98], rax
0x18002a126  lea     rax, [rbp+4Fh+var_60]
0x18002a12a  mov     [rsp+0C0h+var_A0], rax
0x18002a12f  lea     rdx, byte_1800CAB9F
0x18002a136  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18002a13b  test    r15, r15
0x18002a13e  jnz     short loc_18002A15A
0x18002a140  lea     rdx, aSendlpcmessage_0; "SendLpcMessage: pMsg is NULL"
0x18002a147  lea     ecx, [r15+8]; int
0x18002a14b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a150  mov     edi, 80070057h
0x18002a155  jmp     loc_18002A7B3
0x18002a15a  cmp     r13d, 9
0x18002a15e  jnz     short loc_18002A1B7
0x18002a160  movzx   edx, byte ptr [r15+4020h]
0x18002a168  mov     r9, [r15+4028h]
0x18002a16f  xor     ecx, ecx
0x18002a171  test    dl, dl
0x18002a173  setnz   cl
0x18002a176  xor     eax, eax
0x18002a178  test    r9, r9
0x18002a17b  setz    al
0x18002a17e  cmp     ecx, eax
0x18002a180  jz      short loc_18002A198
0x18002a182  mov     r8d, edx
0x18002a185  lea     rdx, aMessageStructu; "Message structure inconsistency: DoNotW"...
0x18002a18c  mov     ecx, 8; int
0x18002a191  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18002a196  jmp     short loc_18002A150
0x18002a198  mov     r9, [r15+4018h]
0x18002a19f  xor     eax, eax
0x18002a1a1  test    r9, r9
0x18002a1a4  setz    al
0x18002a1a7  cmp     ecx, eax
0x18002a1a9  jz      short loc_18002A1B7
0x18002a1ab  mov     r8d, edx
0x18002a1ae  lea     rdx, aMessageStructu_0; "Message structure inconsistency: DoNotW"...
0x18002a1b5  jmp     short loc_18002A18C
0x18002a1b7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002a1be  mov     ecx, 4088h; unsigned __int64
0x18002a1c3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002a1c8  mov     rbx, rax
0x18002a1cb  test    rax, rax
0x18002a1ce  jnz     short loc_18002A1DA
0x18002a1d0  mov     edi, 8007000Eh
0x18002a1d5  jmp     loc_18002A7B3
0x18002a1da  mov     r14d, [rbp+4Fh+dwMilliseconds]
0x18002a1de  test    r14d, r14d
0x18002a1e1  jz      short loc_18002A212
0x18002a1e3  mov     byte ptr [rax+48h], 1
0x18002a1e7  xor     r9d, r9d; lpName
0x18002a1ea  xor     r8d, r8d; bInitialState
0x18002a1ed  lea     edx, [r9+1]; bManualReset
0x18002a1f1  xor     ecx, ecx; lpEventAttributes
0x18002a1f3  call    cs:__imp_CreateEventW
0x18002a1fa  nop     dword ptr [rax+rax+00h]
0x18002a1ff  mov     [rbx+10h], rax
0x18002a203  test    rax, rax
0x18002a206  jnz     short loc_18002A21E
0x18002a208  mov     edi, 8007000Eh
0x18002a20d  jmp     loc_18002A87F
0x18002a212  mov     byte ptr [rax+48h], 0
0x18002a216  mov     qword ptr [rax+10h], 0
0x18002a21e  movzx   r12d, byte ptr [rbx+48h]
0x18002a223  mov     [rbx+44h], r13d
0x18002a227  mov     eax, 1
0x18002a22c  lock xadd [rsi+748h], eax
0x18002a234  inc     eax
0x18002a236  mov     [rbx+40h], eax
0x18002a239  mov     dword ptr [rbx+4Ch], 0C0000001h
0x18002a240  mov     r8, rdi; Size
0x18002a243  lea     rcx, [rbx+50h]; void *
0x18002a247  mov     rdx, r15; Src
0x18002a24a  call    memcpy_0
0x18002a24f  mov     eax, cs:dword_1800DF020
0x18002a255  lea     rcx, ?CSR_LPC_NAME@@3PAPEBDA; char const * near * CSR_LPC_NAME
0x18002a25c  cmp     eax, 5
0x18002a25f  jbe     short loc_18002A2BC
0x18002a261  mov     eax, [rbx+40h]
0x18002a264  mov     [rbp+4Fh+arg_10], rax
0x18002a268  mov     rax, [rcx+r13*8]
0x18002a26c  mov     [rbp+4Fh+var_60], rax
0x18002a270  mov     [rbp+4Fh+arg_18], r12d
0x18002a274  mov     [rbp+4Fh+var_70], rbx
0x18002a278  lea     rax, aCreatedPcomman; "Created pCommand"
0x18002a27f  mov     [rbp+4Fh+var_58], rax
0x18002a283  lea     rax, [rbp+4Fh+arg_10]
0x18002a287  mov     [rsp+0C0h+var_80], rax
0x18002a28c  lea     rax, [rbp+4Fh+var_60]
0x18002a290  mov     [rsp+0C0h+var_88], rax
0x18002a295  lea     rax, [rbp+4Fh+arg_18]
0x18002a299  mov     [rsp+0C0h+var_90], rax
0x18002a29e  lea     rax, [rbp+4Fh+var_70]
0x18002a2a2  mov     [rsp+0C0h+var_98], rax
0x18002a2a7  lea     rax, [rbp+4Fh+var_58]
0x18002a2ab  mov     [rsp+0C0h+var_A0], rax
0x18002a2b0  lea     rdx, word_1800CAB3E
0x18002a2b7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18002a2bc  lea     rdx, [rsi+698h]; struct CResource *
0x18002a2c3  lea     rcx, [rbp+4Fh+var_70]; this
0x18002a2c7  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18002a2cc  nop
0x18002a2cd  xor     edx, edx
0x18002a2cf  cmp     [rsi+738h], edx
0x18002a2d5  jnz     short loc_18002A346
0x18002a2d7  mov     eax, cs:dword_1800DF020
0x18002a2dd  cmp     eax, 5
0x18002a2e0  jbe     short loc_18002A31F
0x18002a2e2  mov     eax, [rbx+40h]
0x18002a2e5  mov     [rbp+4Fh+arg_10], rax
0x18002a2e9  mov     [rbp+4Fh+var_58], rbx
0x18002a2ed  lea     rax, aQueuingPcomman; "Queuing pCommand"
0x18002a2f4  mov     [rbp+4Fh+var_60], rax
0x18002a2f8  lea     rax, [rbp+4Fh+arg_10]
0x18002a2fc  mov     [rsp+0C0h+var_90], rax
0x18002a301  lea     rax, [rbp+4Fh+var_58]
0x18002a305  mov     [rsp+0C0h+var_98], rax
0x18002a30a  lea     rax, [rbp+4Fh+var_60]
0x18002a30e  mov     [rsp+0C0h+var_A0], rax
0x18002a313  lea     rdx, byte_1800CAAF1
0x18002a31a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18002a31f  lea     rax, [rsi+700h]
0x18002a326  mov     rcx, [rax+8]
0x18002a32a  cmp     [rcx], rax
0x18002a32d  jnz     loc_18002A908
0x18002a333  mov     [rbx], rax
0x18002a336  mov     [rbx+8], rcx
0x18002a33a  mov     [rcx], rbx
0x18002a33d  mov     [rax+8], rbx
0x18002a341  jmp     loc_18002A49E
0x18002a346  movups  xmm0, xmmword ptr [rsi+710h]
0x18002a34d  movups  xmmword ptr [rbx+18h], xmm0
0x18002a351  movups  xmm1, xmmword ptr [rsi+720h]
0x18002a358  movups  xmmword ptr [rbx+28h], xmm1
0x18002a35c  movsd   xmm0, qword ptr [rsi+730h]
0x18002a364  movsd   qword ptr [rbx+38h], xmm0
0x18002a369  mov     eax, cs:dword_1800DF020
0x18002a36f  cmp     eax, 5
0x18002a372  jbe     short loc_18002A3B3
0x18002a374  mov     eax, [rbx+40h]
0x18002a377  mov     [rbp+4Fh+arg_10], rax
0x18002a37b  mov     [rbp+4Fh+var_58], rbx
0x18002a37f  lea     rax, aSendingPcomman; "Sending pCommand"
0x18002a386  mov     [rbp+4Fh+var_60], rax
0x18002a38a  lea     rax, [rbp+4Fh+arg_10]
0x18002a38e  mov     [rsp+0C0h+var_90], rax
0x18002a393  lea     rax, [rbp+4Fh+var_58]
0x18002a397  mov     [rsp+0C0h+var_98], rax
0x18002a39c  lea     rax, [rbp+4Fh+var_60]
0x18002a3a0  mov     [rsp+0C0h+var_A0], rax
0x18002a3a5  lea     rdx, dword_1800CAAA4
0x18002a3ac  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x18002a3b1  xor     edx, edx
0x18002a3b3  cmp     [rbx+48h], dl
0x18002a3b6  jz      short loc_18002A3DA
0x18002a3b8  lea     rax, [rsi+700h]
0x18002a3bf  mov     rcx, [rax+8]
0x18002a3c3  cmp     [rcx], rax
0x18002a3c6  jnz     loc_18002A908
0x18002a3cc  mov     [rbx], rax
0x18002a3cf  mov     [rbx+8], rcx
0x18002a3d3  mov     [rcx], rbx
0x18002a3d6  mov     [rax+8], rbx
0x18002a3da  mov     rcx, [rsi+688h]
0x18002a3e1  mov     rax, [rcx]
0x18002a3e4  mov     [rsp+0C0h+var_80], rdx
0x18002a3e9  mov     [rsp+0C0h+var_88], rdx
0x18002a3ee  mov     [rsp+0C0h+var_90], rdx
0x18002a3f3  mov     [rsp+0C0h+var_98], rdx
0x18002a3f8  mov     [rsp+0C0h+var_A0], rdx
0x18002a3fd  lea     r9, [rbx+18h]
0x18002a401  xor     r8d, r8d
0x18002a404  mov     rdx, [rsi+740h]
0x18002a40b  mov     rax, [rax+10h]
0x18002a40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a414  mov     edi, eax
0x18002a416  or      edi, 10000000h
0x18002a41c  jl      loc_18002A7E7
0x18002a422  mov     dword ptr [rsi+738h], 0
0x18002a42c  cmp     byte ptr [rbx+48h], 0
0x18002a430  jnz     short loc_18002A49E
0x18002a432  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFix_CcsrOobRead@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_CcsrOobRead@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_CcsrOobRead> `wil::Feature<__WilFeatureTraits_Feature_BugFix_CcsrOobRead>::GetImpl(void)'::`2'::impl
0x18002a439  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFix_CcsrOobRead@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFix_CcsrOobRead>::__private_IsEnabled(void)
0x18002a43e  test    al, al
0x18002a440  mov     eax, cs:dword_1800DF020
0x18002a446  jz      short loc_18002A459
0x18002a448  cmp     eax, 4
0x18002a44b  jbe     short loc_18002A48F
0x18002a44d  mov     eax, [rbx+40h]
0x18002a450  lea     rdx, byte_1800CAA6F
0x18002a457  jmp     short loc_18002A469
0x18002a459  cmp     eax, 4
0x18002a45c  jbe     short loc_18002A48F
0x18002a45e  mov     eax, [r15+28h]
0x18002a462  lea     rdx, word_1800CAA3A
0x18002a469  mov     [rbp+4Fh+arg_10], rax
0x18002a46d  lea     rax, aPcommandDelete; "pCommand deleted and set to NULL"
0x18002a474  mov     [rbp+4Fh+var_58], rax
0x18002a478  lea     rax, [rbp+4Fh+arg_10]
0x18002a47c  mov     [rsp+0C0h+var_98], rax
0x18002a481  lea     rax, [rbp+4Fh+var_58]
0x18002a485  mov     [rsp+0C0h+var_A0], rax
0x18002a48a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18002a48f  mov     edx, 4088h; struct std::nothrow_t *
0x18002a494  mov     rcx, rbx; void *
0x18002a497  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002a49c  xor     ebx, ebx
0x18002a49e  lea     rcx, [rbp+4Fh+var_70]; this
0x18002a4a2  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18002a4a7  nop
0x18002a4a8  test    r12d, r12d
0x18002a4ab  jz      loc_18002A7AA
0x18002a4b1  or      edi, 0FFFFFFFFh
0x18002a4b4  cmp     r14d, edi
0x18002a4b7  jnz     loc_18002A5EB
0x18002a4bd  call    ?IsKernelDebuggerAttached@CUtils@@SAHXZ; CUtils::IsKernelDebuggerAttached(void)
0x18002a4c2  test    eax, eax
0x18002a4c4  jz      loc_18002A5EB
0x18002a4ca  mov     rcx, gs:60h
0x18002a4d3  mov     rcx, [rcx+0C0h]
0x18002a4da  mov     rax, rcx
0x18002a4dd  shr     rax, 20h
0x18002a4e1  cmp     eax, 0FFFFFFFFh
0x18002a4e4  jnz     short loc_18002A4EA
0x18002a4e6  cmp     ecx, edi
0x18002a4e8  jz      short loc_18002A51C
0x18002a4ea  mov     rax, 0CB923A29C779A6B5h
0x18002a4f4  imul    rcx
0x18002a4f7  sar     rdx, 0Ch
0x18002a4fb  mov     rax, rdx
0x18002a4fe  shr     rax, 3Fh
0x18002a502  add     rdx, rax
0x18002a505  mov     rax, rdx
0x18002a508  shr     rax, 20h
0x18002a50c  test    eax, eax
0x18002a50e  jnz     short loc_18002A51C
0x18002a510  mov     edi, edx
0x18002a512  mov     eax, 927C0h
0x18002a517  cmp     edx, eax
0x18002a519  cmovb   edi, eax
0x18002a51c  xor     r14d, r14d
0x18002a51f  mov     edx, edi; dwMilliseconds
0x18002a521  mov     rcx, [rbx+10h]; hHandle
0x18002a525  call    cs:__imp_WaitForSingleObject
0x18002a52c  nop     dword ptr [rax+rax+00h]
0x18002a531  cmp     eax, 102h
0x18002a536  jnz     loc_18002A715
0x18002a53c  mov     eax, cs:dword_1800DF020
0x18002a542  cmp     eax, 2
0x18002a545  jbe     short loc_18002A5BC
0x18002a547  mov     [rbp+4Fh+arg_10], rsi
0x18002a54b  lea     rax, [rsi+700h]
0x18002a552  mov     [rbp+4Fh+var_58], rax
0x18002a556  mov     [rbp+4Fh+var_60], rbx
0x18002a55a  movsxd  rax, dword ptr [rsi+638h]
0x18002a561  mov     [rbp+4Fh+var_70], rax
0x18002a565  mov     eax, [rsi+63Ch]
0x18002a56b  mov     [rbp+4Fh+var_50], rax
0x18002a56f  lea     rax, aTimeOutWhileSe; "Time out while sending lpc command to c"...
0x18002a576  mov     [rbp+4Fh+var_48], rax
0x18002a57a  lea     rax, [rbp+4Fh+arg_10]
0x18002a57e  mov     [rsp+0C0h+var_78], rax
0x18002a583  lea     rax, [rbp+4Fh+var_58]
0x18002a587  mov     [rsp+0C0h+var_80], rax
0x18002a58c  lea     rax, [rbp+4Fh+var_60]
0x18002a590  mov     [rsp+0C0h+var_88], rax
0x18002a595  lea     rax, [rbp+4Fh+var_70]
0x18002a599  mov     [rsp+0C0h+var_90], rax
0x18002a59e  lea     rax, [rbp+4Fh+var_50]
0x18002a5a2  mov     [rsp+0C0h+var_98], rax
0x18002a5a7  lea     rax, [rbp+4Fh+var_48]
0x18002a5ab  mov     [rsp+0C0h+var_A0], rax
0x18002a5b0  lea     rdx, byte_1800CA8DB
0x18002a5b7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
  ... truncated ...
```
