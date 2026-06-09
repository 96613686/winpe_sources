# EventDispatcher_RegisterConnection(IUnknown *,_GUID const &,ulong,ulong *)

- ea: `0x18003365c`
- end: `0x1800339ae`
- name: `?EventDispatcher_RegisterConnection@@YAJPEAUIUnknown@@AEBU_GUID@@KPEAK@Z`
- size: `850`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _GUID *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180061ec0`

## callees

- `0x18000cf58`
- `0x18000d640`
- `0x1800258f0`
- `0x18002a8ac`
- `0x18002cb30`
- `0x18002ee34`
- `0x18003365c`
- `0x18003598c`
- `0x180036394`
- `0x180039610`
- `0x180039fb4`
- `0x18003c460`
- `0x18003e928`
- `0x18004e2c4`
- `0x18004fef4`
- `0x180080934`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003390d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003390d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800336e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800336e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033946`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033946`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033951`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033951`

## pseudocode

```c
__int64 __fastcall EventDispatcher_RegisterConnection(
        struct IUnknown *a1,
        struct _GUID *a2,
        unsigned int a3,
        unsigned int *a4)
{
  unsigned __int64 v6; // r8
  int EventFilters; // edi
  int SessionIdFromToken; // eax
  void *v9; // rdx
  void *pSid; // r12
  unsigned int v11; // r14d
  _LUID v12; // rbx
  enum tagOFFLINEFILES_EVENTS v13; // esi
  unsigned int v14; // r13d
  const struct _GUID *v15; // r10
  unsigned int *v16; // rbx
  HANDLE hObject; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v19; // [rsp+68h] [rbp-98h] BYREF
  enum tagOFFLINEFILES_PATHFILTER_MATCH v20; // [rsp+6Ch] [rbp-94h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  void *lpMem; // [rsp+78h] [rbp-88h] BYREF
  _LUID v23; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID *v24; // [rsp+88h] [rbp-78h]
  struct IUnknown *v25; // [rsp+90h] [rbp-70h]
  unsigned int *v26; // [rsp+98h] [rbp-68h]
  _DWORD v27[40]; // [rsp+A0h] [rbp-60h] BYREF

  v24 = a2;
  v25 = a1;
  v26 = a4;
  memset_0(v27, 0, 0x9Cu);
  pv = 0;
  v20 = OFFLINEFILES_PATHFILTER_SELF;
  EventFilters = EventDispatcher_GetEventFilters(a1, v27, v6, (unsigned __int16 **)&pv, &v20);
  if ( EventFilters < 0 )
    goto LABEL_33;
  EnterCriticalSection(&g_csEventDispatcherLock);
  if ( g_bEventDispatcherTerminating )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids, a3);
    }
    EventFilters = -2147023781;
  }
  else
  {
    hObject = 0;
    EventFilters = CscSec_OpenThreadTokenForAccessCheckAndImpersonation(&hObject);
    if ( EventFilters >= 0 )
    {
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids, hObject);
      lpMem = 0;
      EventFilters = CscSec_GetSidFromToken(hObject, &lpMem);
      if ( EventFilters >= 0 )
      {
        v19 = 0;
        v23 = 0;
        SessionIdFromToken = CscSec_GetSessionIdFromToken(hObject, &v19);
        pSid = lpMem;
        EventFilters = SessionIdFromToken;
        if ( SessionIdFromToken >= 0 )
        {
          EventFilters = CscSec_GetAuthIdFromToken(hObject, &v23);
          if ( EventFilters >= 0 )
          {
            v11 = g_dwNextEventConnCookie;
            if ( g_dwNextEventConnCookie )
            {
              v12 = v23;
              v13 = OFFLINEFILES_EVENT_CACHEMOVED;
              ++g_dwNextEventConnCookie;
              EventFilters = 0;
              v14 = v19;
              while ( 1 )
              {
                if ( v27[v13] )
                {
                  if ( (unsigned int)EventDispatcher_InterfaceSupportsEvent(v24, v13) )
                  {
                    EventFilters = EventDispatcher_RegisterEventSink(
                                     v13,
                                     v25,
                                     v15,
                                     (const unsigned __int16 *)pv,
                                     v20,
                                     v11,
                                     a3,
                                     v14,
                                     v12,
                                     hObject,
                                     pSid);
                    if ( EventFilters < 0 )
                      break;
                  }
                }
                if ( ++v13 >= OFFLINEFILES_NUM_EVENTS )
                {
                  v16 = v26;
                  if ( v26 )
                  {
                    PerfCounter_AdjustCounter(&g_PerfCounters, &dword_1800B8264, 1);
                    *v16 = v11;
                    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
                    {
                      WPP_SF_dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        34,
                        WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids,
                        v11,
                        a3);
                    }
                  }
                  break;
                }
              }
            }
            else
            {
              EventFilters = -2147024637;
              if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids);
              }
            }
          }
        }
        CscUtil_HeapFree(pSid, v9);
      }
      CloseHandle(hObject);
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids, hObject);
    }
  }
  LeaveCriticalSection(&g_csEventDispatcherLock);
  CoTaskMemFree(pv);
  if ( EventFilters < 0 )
  {
LABEL_33:
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids, a3);
  }
  return (unsigned int)EventFilters;
}

```

## disassembly

```asm
0x18003365c  mov     [rsp-8+arg_8], rbx
0x180033661  push    rbp
0x180033662  push    rsi
0x180033663  push    rdi
0x180033664  push    r12
0x180033666  push    r13
0x180033668  push    r14
0x18003366a  push    r15
0x18003366c  lea     rbp, [rsp-50h]
0x180033671  sub     rsp, 150h
0x180033678  mov     rax, cs:__security_cookie
0x18003367f  xor     rax, rsp
0x180033682  mov     [rbp+80h+var_40], rax
0x180033686  mov     r15d, r8d
0x180033689  mov     [rbp+80h+var_F8], rdx
0x18003368d  mov     rbx, rcx
0x180033690  mov     [rbp+80h+var_F0], rcx
0x180033694  xor     edx, edx; Val
0x180033696  mov     [rbp+80h+var_E8], r9
0x18003369a  mov     r8d, 9Ch; Size
0x1800336a0  lea     rcx, [rbp+80h+var_E0]; void *
0x1800336a4  call    memset_0
0x1800336a9  lea     rax, [rsp+180h+var_114]
0x1800336ae  xor     r13d, r13d
0x1800336b1  lea     r9, [rsp+180h+pv]; unsigned __int16 **
0x1800336b6  mov     qword ptr [rsp+180h+var_160], rax; enum tagOFFLINEFILES_PATHFILTER_MATCH *
0x1800336bb  lea     rdx, [rbp+80h+var_E0]; void *
0x1800336bf  mov     [rsp+180h+pv], r13
0x1800336c4  mov     rcx, rbx; struct IUnknown *
0x1800336c7  mov     [rsp+180h+var_114], r13d
0x1800336cc  call    ?EventDispatcher_GetEventFilters@@YAJPEAUIUnknown@@PEAH_KPEAPEAGPEAW4tagOFFLINEFILES_PATHFILTER_MATCH@@@Z; EventDispatcher_GetEventFilters(IUnknown *,int *,unsigned __int64,ushort * *,tagOFFLINEFILES_PATHFILTER_MATCH *)
0x1800336d1  lea     rbx, WPP_GLOBAL_Control
0x1800336d8  mov     edi, eax
0x1800336da  test    eax, eax
0x1800336dc  js      loc_18003395B
0x1800336e2  lea     rcx, ?g_csEventDispatcherLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800336e9  call    cs:__imp_EnterCriticalSection
0x1800336ef  cmp     cs:?g_bEventDispatcherTerminating@@3HA, r13d; int g_bEventDispatcherTerminating
0x1800336f6  jz      short loc_18003372B
0x1800336f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800336ff  cmp     rcx, rbx
0x180033702  jz      short loc_180033721
0x180033704  test    byte ptr [rcx+1Ch], 10h
0x180033708  jz      short loc_180033721
0x18003370a  mov     rcx, [rcx+10h]
0x18003370e  lea     edx, [r13+20h]
0x180033712  mov     r9d, r15d
0x180033715  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x18003371c  call    WPP_SF_d
0x180033721  mov     edi, 8007045Bh
0x180033726  jmp     loc_18003393F
0x18003372b  lea     rcx, [rsp+180h+hObject]; TokenHandle
0x180033730  mov     [rsp+180h+hObject], r13
0x180033735  call    ?CscSec_OpenThreadTokenForAccessCheckAndImpersonation@@YAJPEAPEAX@Z; CscSec_OpenThreadTokenForAccessCheckAndImpersonation(void * *)
0x18003373a  mov     edi, eax
0x18003373c  test    eax, eax
0x18003373e  js      loc_18003393F
0x180033744  mov     rcx, cs:WPP_GLOBAL_Control
0x18003374b  cmp     rcx, rbx
0x18003374e  jz      short loc_180033770
0x180033750  test    byte ptr [rcx+1Ch], 8
0x180033754  jz      short loc_180033770
0x180033756  mov     r9, [rsp+180h+hObject]
0x18003375b  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x180033762  mov     rcx, [rcx+10h]
0x180033766  mov     edx, 21h ; '!'
0x18003376b  call    WPP_SF_q
0x180033770  mov     rcx, [rsp+180h+hObject]; TokenHandle
0x180033775  lea     rdx, [rsp+180h+lpMem]; void **
0x18003377a  mov     [rsp+180h+lpMem], r13
0x18003377f  call    ?CscSec_GetSidFromToken@@YAJPEAXPEAPEAX@Z; CscSec_GetSidFromToken(void *,void * *)
0x180033784  mov     edi, eax
0x180033786  test    eax, eax
0x180033788  js      loc_180033908
0x18003378e  mov     rcx, [rsp+180h+hObject]; void *
0x180033793  lea     rdx, [rsp+180h+var_118]; unsigned int *
0x180033798  mov     [rsp+180h+var_118], r13d
0x18003379d  mov     qword ptr [rbp+80h+var_100.LowPart], r13
0x1800337a1  call    ?CscSec_GetSessionIdFromToken@@YAJPEAXPEAK@Z; CscSec_GetSessionIdFromToken(void *,ulong *)
0x1800337a6  mov     r12, [rsp+180h+lpMem]
0x1800337ab  mov     edi, eax
0x1800337ad  test    eax, eax
0x1800337af  js      loc_180033900
0x1800337b5  mov     rcx, [rsp+180h+hObject]; void *
0x1800337ba  lea     rdx, [rbp+80h+var_100]; struct _LUID *
0x1800337be  call    ?CscSec_GetAuthIdFromToken@@YAJPEAXPEAU_LUID@@@Z; CscSec_GetAuthIdFromToken(void *,_LUID *)
0x1800337c3  mov     edi, eax
0x1800337c5  test    eax, eax
0x1800337c7  js      loc_180033900
0x1800337cd  mov     r14d, cs:?g_dwNextEventConnCookie@@3KA; ulong g_dwNextEventConnCookie
0x1800337d4  test    r14d, r14d
0x1800337d7  jz      loc_1800338C9
0x1800337dd  mov     rbx, qword ptr [rbp+80h+var_100.LowPart]
0x1800337e1  lea     eax, [r14+1]
0x1800337e5  mov     esi, r13d
0x1800337e8  mov     cs:?g_dwNextEventConnCookie@@3KA, eax; ulong g_dwNextEventConnCookie
0x1800337ee  mov     edi, r13d
0x1800337f1  mov     r13d, [rsp+180h+var_118]
0x1800337f6  mov     eax, esi
0x1800337f8  cmp     [rbp+rax*4+80h+var_E0], 0
0x1800337fd  jz      short loc_180033859
0x1800337ff  mov     r10, [rbp+80h+var_F8]
0x180033803  mov     edx, esi; enum tagOFFLINEFILES_EVENTS
0x180033805  mov     rcx, r10; struct _GUID *
0x180033808  call    ?EventDispatcher_InterfaceSupportsEvent@@YAHAEBU_GUID@@W4tagOFFLINEFILES_EVENTS@@@Z; EventDispatcher_InterfaceSupportsEvent(_GUID const &,tagOFFLINEFILES_EVENTS)
0x18003380d  test    eax, eax
0x18003380f  jz      short loc_180033859
0x180033811  mov     rax, [rsp+180h+hObject]
0x180033816  mov     r8, r10; struct _GUID *
0x180033819  mov     r9, [rsp+180h+pv]; unsigned __int16 *
0x18003381e  mov     ecx, esi; enum tagOFFLINEFILES_EVENTS
0x180033820  mov     rdx, [rbp+80h+var_F0]; struct IUnknown *
0x180033824  mov     [rsp+180h+pSid], r12; pSid
0x180033829  mov     [rsp+180h+hSourceHandle], rax; hSourceHandle
0x18003382e  mov     eax, [rsp+180h+var_114]
0x180033832  mov     qword ptr [rsp+180h+var_140.LowPart], rbx; struct _LUID
0x180033837  mov     [rsp+180h+var_148], r13d; unsigned int
0x18003383c  mov     [rsp+180h+var_150], r15d; unsigned int
0x180033841  mov     [rsp+180h+var_158], r14d; unsigned int
0x180033846  mov     [rsp+180h+var_160], eax; tagOFFLINEFILES_PATHFILTER_MATCH
0x18003384a  call    ?EventDispatcher_RegisterEventSink@@YAJW4tagOFFLINEFILES_EVENTS@@PEAUIUnknown@@AEBU_GUID@@PEBGW4tagOFFLINEFILES_PATHFILTER_MATCH@@KKKU_LUID@@PEAX6@Z; EventDispatcher_RegisterEventSink(tagOFFLINEFILES_EVENTS,IUnknown *,_GUID const &,ushort const *,tagOFFLINEFILES_PATHFILTER_MATCH,ulong,ulong,ulong,_LUID,void *,void *)
0x18003384f  mov     edi, eax
0x180033851  test    eax, eax
0x180033853  js      loc_1800338F9
0x180033859  inc     esi
0x18003385b  cmp     esi, 27h ; '''
0x18003385e  jl      short loc_1800337F6
0x180033860  test    edi, edi
0x180033862  js      loc_1800338F9
0x180033868  mov     rbx, [rbp+80h+var_E8]
0x18003386c  test    rbx, rbx
0x18003386f  jz      loc_1800338F9
0x180033875  mov     r8d, 1; int
0x18003387b  lea     rdx, dword_1800B8264; unsigned int *
0x180033882  lea     rcx, ?g_PerfCounters@@3UPERF_CTR_BLOCK@@A; unsigned int *
0x180033889  call    ?PerfCounter_AdjustCounter@@YAXPEAK0J@Z; PerfCounter_AdjustCounter(ulong *,ulong *,long)
0x18003388e  mov     [rbx], r14d
0x180033891  mov     rcx, cs:WPP_GLOBAL_Control
0x180033898  lea     rbx, WPP_GLOBAL_Control
0x18003389f  cmp     rcx, rbx
0x1800338a2  jz      short loc_180033900
0x1800338a4  test    byte ptr [rcx+1Ch], 10h
0x1800338a8  jz      short loc_180033900
0x1800338aa  mov     rcx, [rcx+10h]
0x1800338ae  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x1800338b5  mov     edx, 22h ; '"'
0x1800338ba  mov     [rsp+180h+var_160], r15d
0x1800338bf  mov     r9d, r14d
0x1800338c2  call    WPP_SF_dd
0x1800338c7  jmp     short loc_180033900
0x1800338c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800338d0  mov     esi, 80070103h
0x1800338d5  mov     edi, esi
0x1800338d7  cmp     rcx, rbx
0x1800338da  jz      short loc_180033900
0x1800338dc  test    byte ptr [rcx+1Ch], 10h
0x1800338e0  jz      short loc_180033900
0x1800338e2  mov     rcx, [rcx+10h]
0x1800338e6  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x1800338ed  mov     edx, 23h ; '#'
0x1800338f2  call    WPP_SF_
0x1800338f7  jmp     short loc_180033900
0x1800338f9  lea     rbx, WPP_GLOBAL_Control
0x180033900  mov     rcx, r12; lpMem
0x180033903  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180033908  mov     rcx, [rsp+180h+hObject]; hObject
0x18003390d  call    cs:__imp_CloseHandle
0x180033913  mov     rcx, cs:WPP_GLOBAL_Control
0x18003391a  cmp     rcx, rbx
0x18003391d  jz      short loc_18003393F
0x18003391f  test    byte ptr [rcx+1Ch], 8
0x180033923  jz      short loc_18003393F
0x180033925  mov     r9, [rsp+180h+hObject]
0x18003392a  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x180033931  mov     rcx, [rcx+10h]
0x180033935  mov     edx, 24h ; '$'
0x18003393a  call    WPP_SF_q
0x18003393f  lea     rcx, ?g_csEventDispatcherLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180033946  call    cs:__imp_LeaveCriticalSection
0x18003394c  mov     rcx, [rsp+180h+pv]; pv
0x180033951  call    cs:__imp_CoTaskMemFree
0x180033957  test    edi, edi
0x180033959  jns     short loc_180033985
0x18003395b  mov     rcx, cs:WPP_GLOBAL_Control
0x180033962  cmp     rcx, rbx
0x180033965  jz      short loc_180033985
0x180033967  test    byte ptr [rcx+1Ch], 2
0x18003396b  jz      short loc_180033985
0x18003396d  mov     rcx, [rcx+10h]
0x180033971  lea     r8, WPP_ec025b6fc19f3c7778dfc92dc65caf05_Traceguids
0x180033978  mov     edx, 25h ; '%'
0x18003397d  mov     r9d, r15d
0x180033980  call    WPP_SF_d
0x180033985  mov     eax, edi
0x180033987  mov     rcx, [rbp+80h+var_40]
0x18003398b  xor     rcx, rsp; StackCookie
0x18003398e  call    __security_check_cookie
0x180033993  mov     rbx, [rsp+180h+arg_8]
0x18003399b  add     rsp, 150h
0x1800339a2  pop     r15
0x1800339a4  pop     r14
0x1800339a6  pop     r13
0x1800339a8  pop     r12
0x1800339aa  pop     rdi
0x1800339ab  pop     rsi
0x1800339ac  pop     rbp
0x1800339ad  retn
```
