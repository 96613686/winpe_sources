# MapsBackgroundTransferJob::PollState(void)

- ea: `0x18000d77c`
- end: `0x18000da30`
- name: `?PollState@MapsBackgroundTransferJob@@QEAAJXZ`
- size: `692`
- prototype: `__int64 __fastcall(MapsBackgroundTransferJob *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005820`
- `0x180012b80`

## callees

- `0x180004094`
- `0x180004408`
- `0x18000c348`
- `0x18000cba4`
- `0x18000d3dc`
- `0x18000d77c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d923`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d923`
- `ZTrace_Maps!ZTraceHelper` at `0x18000d806`
- `ZTrace_Maps!ZTraceHelper` at `0x18000d897`
- `ZTrace_Maps!ZTraceHelper` at `0x18000d806`
- `ZTrace_Maps!ZTraceHelper` at `0x18000d897`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000d83f`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18000d83f`

## string_xrefs

- `0x18000d7e8`: `BITS service has crashed and the RPC connected was dropped`

## pseudocode

```c
__int64 __fastcall MapsBackgroundTransferJob::PollState(MapsBackgroundTransferJob *this)
{
  unsigned int v2; // esi
  bool v3; // bl
  int v4; // eax
  int v5; // r8d
  int v6; // eax
  enum BG_JOB_STATE v7; // edx
  DWORD dwLowDateTime; // eax
  DWORD dwHighDateTime; // ecx
  __int64 v10; // r14
  int v11; // ecx
  unsigned __int64 v12; // rbx
  _BYTE v14[16]; // [rsp+30h] [rbp-10h] BYREF
  BG_JOB_STATE v15; // [rsp+70h] [rbp+30h] BYREF
  int v16; // [rsp+78h] [rbp+38h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp+40h] BYREF
  unsigned __int64 v18; // [rsp+88h] [rbp+48h]

  v2 = 0;
  v15 = BG_JOB_STATE_QUEUED;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(
    (__int64)v14,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 784));
  v3 = *((_QWORD *)this + 78) != 0;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>((__int64)v14);
  if ( !v3 )
    return v2;
  v4 = (*(__int64 (__fastcall **)(_QWORD, BG_JOB_STATE *))(**((_QWORD **)this + 3) + 112LL))(
         *((_QWORD *)this + 3),
         &v15);
  v2 = v4;
  if ( ((v4 + 2147023174) & 0xFFFFFFFA) != 0 || v4 == -2147023173 )
  {
    if ( v4 < 0 )
    {
      v5 = 403;
      return (unsigned int)ZTraceReportPropagation(v4, "MapsBackgroundTransferJob::PollState", v5, this);
    }
    if ( v15 )
    {
      if ( v15 == BG_JOB_STATE_TRANSFERRING )
        goto LABEL_19;
      if ( v15 == BG_JOB_STATE_SUSPENDED )
      {
        ZTraceHelper(0, "MapsBackgroundTransferJob::PollState", 408, this, "BITS job was suspended unexpectedly");
LABEL_17:
        v4 = MapsBackgroundTransferJob::AllRequestsFail(this, -2147467260);
        if ( v4 >= 0 )
          return v2;
        v5 = 411;
        return (unsigned int)ZTraceReportPropagation(v4, "MapsBackgroundTransferJob::PollState", v5, this);
      }
      if ( v15 != BG_JOB_STATE_TRANSIENT_ERROR )
      {
        if ( v15 != BG_JOB_STATE_TRANSFERRED )
        {
          if ( v15 != BG_JOB_STATE_CANCELLED )
            return v2;
          goto LABEL_17;
        }
LABEL_19:
        if ( *((_QWORD *)this + 96) )
        {
          v6 = *((_DWORD *)this + 194);
          *((_QWORD *)this + 96) = 0;
          *((_DWORD *)this + 194) = 0;
          *((_BYTE *)this + 780) = 0;
          if ( v6 )
          {
            v4 = MapsBackgroundTransferJob::InvokeStateChangedCallback(this, 1);
            if ( v4 < 0 )
            {
              v5 = 429;
              return (unsigned int)ZTraceReportPropagation(v4, "MapsBackgroundTransferJob::PollState", v5, this);
            }
          }
        }
        return v2;
      }
    }
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v7 = v15;
    dwLowDateTime = SystemTimeAsFileTime.dwLowDateTime;
    dwHighDateTime = SystemTimeAsFileTime.dwHighDateTime;
    if ( *((_QWORD *)this + 96)
      || (*((_DWORD *)this + 193) = SystemTimeAsFileTime.dwHighDateTime,
          *((_DWORD *)this + 192) = dwLowDateTime,
          v7 == BG_JOB_STATE_TRANSIENT_ERROR) )
    {
      v10 = *((_QWORD *)this + 96);
      v18 = __PAIR64__(dwHighDateTime, dwLowDateTime);
      v16 = 0;
      v4 = MapsBackgroundTransferJob::GetAndTraceWaitingReason(this, v7, (enum MAPSBTSVC_JOB_WAITING_REASON *)&v16);
      if ( v4 < 0 )
      {
        v5 = 459;
        return (unsigned int)ZTraceReportPropagation(v4, "MapsBackgroundTransferJob::PollState", v5, this);
      }
      v11 = *((_DWORD *)this + 194);
      v12 = v18;
      if ( v11 != v16 && (!v11 || v16 != 1) && (v18 - v10 > 0x5F5E100 || v15 == BG_JOB_STATE_TRANSIENT_ERROR) )
      {
        *((_DWORD *)this + 194) = v16;
        v4 = MapsBackgroundTransferJob::InvokeStateChangedCallback(this, 0);
        if ( v4 < 0 )
        {
          v5 = 476;
          return (unsigned int)ZTraceReportPropagation(v4, "MapsBackgroundTransferJob::PollState", v5, this);
        }
      }
      if ( !*((_BYTE *)this + 780)
        && v12 - *((_QWORD *)this + 96) > 10000000 * (unsigned __int64)*((unsigned int *)this + 184) )
      {
        v4 = MapsBackgroundTransferJob::InvokeStateChangedCallback(this, 2);
        if ( v4 >= 0 )
        {
          *((_BYTE *)this + 780) = 1;
          return v2;
        }
        v5 = 483;
        return (unsigned int)ZTraceReportPropagation(v4, "MapsBackgroundTransferJob::PollState", v5, this);
      }
    }
    return v2;
  }
  ZTraceHelper(
    0,
    "MapsBackgroundTransferJob::PollState",
    398,
    this,
    "BITS service has crashed and the RPC connected was dropped");
  v4 = MapsBackgroundTransferJob::AllRequestsFail(this, -2147467260);
  if ( v4 < 0 )
  {
    v5 = 399;
    return (unsigned int)ZTraceReportPropagation(v4, "MapsBackgroundTransferJob::PollState", v5, this);
  }
  return v2;
}

```

## disassembly

```asm
0x18000d77c  push    rbp
0x18000d77e  push    rbx
0x18000d77f  push    rsi
0x18000d780  push    rdi
0x18000d781  push    r14
0x18000d783  mov     rbp, rsp
0x18000d786  sub     rsp, 40h
0x18000d78a  mov     rdi, rcx
0x18000d78d  lea     rdx, [rcx+310h]
0x18000d794  xor     esi, esi
0x18000d796  lea     rcx, [rbp+var_10]
0x18000d79a  mov     [rbp+arg_0], esi
0x18000d79d  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x18000d7a2  cmp     [rdi+270h], rsi
0x18000d7a9  lea     rcx, [rbp+var_10]
0x18000d7ad  setnz   bl
0x18000d7b0  call    ??1?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::~CComCritSecLock<ATL::CComAutoCriticalSection>(void)
0x18000d7b5  test    bl, bl
0x18000d7b7  jz      loc_18000DA23
0x18000d7bd  mov     rcx, [rdi+18h]
0x18000d7c1  lea     rdx, [rbp+arg_0]
0x18000d7c5  mov     rax, [rcx]
0x18000d7c8  mov     rax, [rax+70h]
0x18000d7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7d1  mov     esi, eax
0x18000d7d3  lea     ecx, [rax+7FF8F946h]
0x18000d7d9  test    ecx, 0FFFFFFFAh
0x18000d7df  jnz     short loc_18000D829
0x18000d7e1  cmp     eax, 800706BBh
0x18000d7e6  jz      short loc_18000D829
0x18000d7e8  lea     rax, aBitsServiceHas; "BITS service has crashed and the RPC co"...
0x18000d7ef  mov     r9, rdi
0x18000d7f2  mov     r8d, 18Eh
0x18000d7f8  mov     [rsp+40h+var_20], rax
0x18000d7fd  lea     rdx, aMapsbackground_33; "MapsBackgroundTransferJob::PollState"
0x18000d804  xor     ecx, ecx
0x18000d806  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18000d80c  mov     edx, 80004004h; int
0x18000d811  mov     rcx, rdi; this
0x18000d814  call    ?AllRequestsFail@MapsBackgroundTransferJob@@AEAAJJ@Z; MapsBackgroundTransferJob::AllRequestsFail(long)
0x18000d819  test    eax, eax
0x18000d81b  jns     loc_18000DA23
0x18000d821  mov     r8d, 18Fh
0x18000d827  jmp     short loc_18000D833
0x18000d829  test    eax, eax
0x18000d82b  jns     short loc_18000D84C
0x18000d82d  mov     r8d, 193h
0x18000d833  mov     r9, rdi
0x18000d836  lea     rdx, aMapsbackground_33; "MapsBackgroundTransferJob::PollState"
0x18000d83d  mov     ecx, eax
0x18000d83f  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18000d845  mov     esi, eax
0x18000d847  jmp     loc_18000DA23
0x18000d84c  mov     ecx, [rbp+arg_0]
0x18000d84f  test    ecx, ecx
0x18000d851  jz      loc_18000D917
0x18000d857  sub     ecx, 2
0x18000d85a  jz      short loc_18000D8BD
0x18000d85c  sub     ecx, 1
0x18000d85f  jz      short loc_18000D879
0x18000d861  sub     ecx, 2
0x18000d864  jz      loc_18000D917
0x18000d86a  sub     ecx, 1
0x18000d86d  jz      short loc_18000D8BD
0x18000d86f  cmp     ecx, 2
0x18000d872  jz      short loc_18000D89D
0x18000d874  jmp     loc_18000DA23
0x18000d879  lea     rax, aBitsJobWasSusp; "BITS job was suspended unexpectedly"
0x18000d880  mov     r9, rdi
0x18000d883  mov     r8d, 198h
0x18000d889  mov     [rsp+40h+var_20], rax
0x18000d88e  lea     rdx, aMapsbackground_33; "MapsBackgroundTransferJob::PollState"
0x18000d895  xor     ecx, ecx
0x18000d897  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18000d89d  mov     edx, 80004004h; int
0x18000d8a2  mov     rcx, rdi; this
0x18000d8a5  call    ?AllRequestsFail@MapsBackgroundTransferJob@@AEAAJJ@Z; MapsBackgroundTransferJob::AllRequestsFail(long)
0x18000d8aa  test    eax, eax
0x18000d8ac  jns     loc_18000DA23
0x18000d8b2  mov     r8d, 19Bh
0x18000d8b8  jmp     loc_18000D833
0x18000d8bd  cmp     qword ptr [rdi+300h], 0
0x18000d8c5  jbe     loc_18000DA23
0x18000d8cb  mov     eax, [rdi+308h]
0x18000d8d1  mov     qword ptr [rdi+300h], 0
0x18000d8dc  mov     dword ptr [rdi+308h], 0
0x18000d8e6  mov     byte ptr [rdi+30Ch], 0
0x18000d8ed  test    eax, eax
0x18000d8ef  jz      loc_18000DA23
0x18000d8f5  xor     r8d, r8d
0x18000d8f8  mov     rcx, rdi
0x18000d8fb  lea     edx, [r8+1]
0x18000d8ff  call    ?InvokeStateChangedCallback@MapsBackgroundTransferJob@@AEAAJW4MAPSBTSVC_JOB_STATE_CHANGE@@W4MAPSBTSVC_JOB_WAITING_REASON@@@Z; MapsBackgroundTransferJob::InvokeStateChangedCallback(MAPSBTSVC_JOB_STATE_CHANGE,MAPSBTSVC_JOB_WAITING_REASON)
0x18000d904  test    eax, eax
0x18000d906  jns     loc_18000DA23
0x18000d90c  mov     r8d, 1ADh
0x18000d912  jmp     loc_18000D833
0x18000d917  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000d91b  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000d923  call    cs:__imp_GetSystemTimeAsFileTime
0x18000d929  cmp     qword ptr [rdi+300h], 0
0x18000d931  mov     edx, [rbp+arg_0]; enum BG_JOB_STATE
0x18000d934  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000d938  mov     ecx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x18000d93b  jnz     short loc_18000D952
0x18000d93d  mov     [rdi+304h], ecx
0x18000d943  mov     [rdi+300h], eax
0x18000d949  cmp     edx, 5
0x18000d94c  jnz     loc_18000DA23
0x18000d952  mov     r14, [rdi+300h]
0x18000d959  lea     r8, [rbp+arg_8]; enum MAPSBTSVC_JOB_WAITING_REASON *
0x18000d95d  mov     dword ptr [rbp+arg_18+4], ecx
0x18000d960  mov     rcx, rdi; this
0x18000d963  mov     dword ptr [rbp+arg_18], eax
0x18000d966  mov     [rbp+arg_8], 0
0x18000d96d  call    ?GetAndTraceWaitingReason@MapsBackgroundTransferJob@@AEAAJW4BG_JOB_STATE@@PEAW4MAPSBTSVC_JOB_WAITING_REASON@@@Z; MapsBackgroundTransferJob::GetAndTraceWaitingReason(BG_JOB_STATE,MAPSBTSVC_JOB_WAITING_REASON *)
0x18000d972  test    eax, eax
0x18000d974  jns     short loc_18000D981
0x18000d976  mov     r8d, 1CBh
0x18000d97c  jmp     loc_18000D833
0x18000d981  mov     r8d, [rbp+arg_8]
0x18000d985  mov     ecx, [rdi+308h]
0x18000d98b  cmp     ecx, r8d
0x18000d98e  mov     rbx, [rbp+arg_18]
0x18000d992  setnz   al
0x18000d995  cmp     r8d, 1
0x18000d999  setnz   dl
0x18000d99c  test    al, al
0x18000d99e  jz      short loc_18000D9DC
0x18000d9a0  test    ecx, ecx
0x18000d9a2  jz      short loc_18000D9A8
0x18000d9a4  test    dl, dl
0x18000d9a6  jz      short loc_18000D9DC
0x18000d9a8  mov     rax, rbx
0x18000d9ab  sub     rax, r14
0x18000d9ae  cmp     rax, 5F5E100h
0x18000d9b4  ja      short loc_18000D9BC
0x18000d9b6  cmp     [rbp+arg_0], 5
0x18000d9ba  jnz     short loc_18000D9DC
0x18000d9bc  xor     edx, edx
0x18000d9be  mov     [rdi+308h], r8d
0x18000d9c5  mov     rcx, rdi
0x18000d9c8  call    ?InvokeStateChangedCallback@MapsBackgroundTransferJob@@AEAAJW4MAPSBTSVC_JOB_STATE_CHANGE@@W4MAPSBTSVC_JOB_WAITING_REASON@@@Z; MapsBackgroundTransferJob::InvokeStateChangedCallback(MAPSBTSVC_JOB_STATE_CHANGE,MAPSBTSVC_JOB_WAITING_REASON)
0x18000d9cd  test    eax, eax
0x18000d9cf  jns     short loc_18000D9DC
0x18000d9d1  mov     r8d, 1DCh
0x18000d9d7  jmp     loc_18000D833
0x18000d9dc  cmp     byte ptr [rdi+30Ch], 0
0x18000d9e3  jnz     short loc_18000DA23
0x18000d9e5  mov     eax, [rdi+2E0h]
0x18000d9eb  sub     rbx, [rdi+300h]
0x18000d9f2  imul    rcx, rax, 989680h
0x18000d9f9  cmp     rbx, rcx
0x18000d9fc  jbe     short loc_18000DA23
0x18000d9fe  xor     r8d, r8d
0x18000da01  mov     rcx, rdi
0x18000da04  lea     edx, [r8+2]
0x18000da08  call    ?InvokeStateChangedCallback@MapsBackgroundTransferJob@@AEAAJW4MAPSBTSVC_JOB_STATE_CHANGE@@W4MAPSBTSVC_JOB_WAITING_REASON@@@Z; MapsBackgroundTransferJob::InvokeStateChangedCallback(MAPSBTSVC_JOB_STATE_CHANGE,MAPSBTSVC_JOB_WAITING_REASON)
0x18000da0d  test    eax, eax
0x18000da0f  jns     short loc_18000DA1C
0x18000da11  mov     r8d, 1E3h
0x18000da17  jmp     loc_18000D833
0x18000da1c  mov     byte ptr [rdi+30Ch], 1
0x18000da23  mov     eax, esi
0x18000da25  add     rsp, 40h
0x18000da29  pop     r14
0x18000da2b  pop     rdi
0x18000da2c  pop     rsi
0x18000da2d  pop     rbx
0x18000da2e  pop     rbp
0x18000da2f  retn
```
