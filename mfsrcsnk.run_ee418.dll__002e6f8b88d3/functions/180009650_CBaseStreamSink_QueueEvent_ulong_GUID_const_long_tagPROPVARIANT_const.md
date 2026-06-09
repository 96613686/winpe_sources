# CBaseStreamSink::QueueEvent(ulong,_GUID const &,long,tagPROPVARIANT const *)

- ea: `0x180009650`
- end: `0x180009aab`
- name: `?QueueEvent@CBaseStreamSink@@UEAAJKAEBU_GUID@@JPEBUtagPROPVARIANT@@@Z`
- size: `1115`
- prototype: `int(CBaseStreamSink *__hidden this, unsigned int, const struct _GUID *, int, const struct tagPROPVARIANT *)`
- caller_count: `5`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180073dc0`
- `0x1800c6f2c`
- `0x1800e0460`
- `0x1800e3654`
- `0x18011b6d0`

## callees

- `0x180009650`
- `0x18000a884`
- `0x18000e0c0`
- `0x180010190`
- `0x18001303c`
- `0x180071a44`
- `0x180073b14`
- `0x1801636a4`
- `0x1801636fc`
- `0x180164394`
- `0x1801646ac`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800097a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000983b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800097a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000983b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000967a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800097dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000967a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800097dd`
- `MFPlat!MFCreateMediaEventResult` at `0x180009801`
- `MFPlat!MFCreateMediaEventResult` at `0x180009801`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800098be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009911`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800098be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180009911`
- `MFPlat!MFCreateMediaEvent` at `0x180009756`
- `MFPlat!MFCreateMediaEvent` at `0x180009756`

## string_xrefs

- `0x180009694`: `CBaseStreamSink::QueueEvent`
- `0x18000998a`: `CBaseStreamSink::QueueEvent`

## pseudocode

```c
__int64 __fastcall CBaseStreamSink::QueueEvent(
        CBaseStreamSink *this,
        unsigned int a2,
        const struct _GUID *a3,
        HRESULT a4,
        const struct tagPROPVARIANT *pvValue)
{
  struct _RTL_CRITICAL_SECTION *v5; // r13
  __int64 v10; // rdx
  __int64 v11; // r8
  CallStackTracing *v12; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  char *v16; // r12
  char *v17; // rsi
  struct CallStackContext *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rcx
  HRESULT v21; // ebx
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  struct IMFMediaEvent *v26; // rbx
  unsigned int v27; // edx
  __int64 *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  wchar_t *v33; // rcx
  CallStackTracing *v34; // rax
  wchar_t *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  struct CallStackContext *v38; // rax
  __int64 v39; // rdx
  const char *v40; // rax
  int v41; // edx
  int v42; // r8d
  int v43; // [rsp+30h] [rbp-28h] BYREF
  IMFMediaEvent *ppEvent; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v45[3]; // [rsp+40h] [rbp-18h] BYREF
  int v46; // [rsp+A0h] [rbp+48h] BYREF

  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 248);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 248));
  v12 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v12 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v12 + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v12);
    v14 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v14 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v15 = 2 * v14;
      *((_QWORD *)ThreadRelativeContext + v15) = "CBaseStreamSink::QueueEvent";
      *((_DWORD *)ThreadRelativeContext + 2 * v15 + 2) = 227;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
    v12 = CallStackTracing::s_wpInstance;
  }
  v16 = (char *)this - 16;
  if ( *((_DWORD *)this + 82) == 7 )
  {
    v21 = -1072870856;
    if ( g_wppLevels >= 4u )
    {
      v39 = 26;
LABEL_58:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, &WPP_85ded7c3193c34fe64ab2cb119f9c690_Traceguids, v16, v21);
    }
  }
  else
  {
    v17 = (char *)this + 88;
    if ( !v12 )
    {
      CallStackTracing::InitInstance();
      v12 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v18 = CallStackTracing::GetThreadRelativeContext(v12);
      v19 = *((unsigned int *)v18 + 497);
      if ( (unsigned int)v19 < *((_DWORD *)v18 + 498) )
      {
        v20 = 2 * v19;
        *((_QWORD *)v18 + v20) = "CMFMediaEventGenerator::QueueEvent";
        *((_DWORD *)v18 + 2 * v20 + 2) = 366;
      }
      ++*((_DWORD *)v18 + 497);
    }
    if ( (unsigned __int8)byte_1801B110B >= 0x10u )
    {
      v40 = MFTRACE_STRING_FROM_MET(a2);
      WPP_SF_qsL(*((_QWORD *)WPP_GLOBAL_Control + 17), v41, v42, (_DWORD)v17, (__int64)v40, a4);
    }
    if ( *((_DWORD *)this + 34) )
    {
      v21 = -1072873851;
    }
    else
    {
      ppEvent = 0;
      v21 = MFCreateMediaEvent(a2, a3, a4, pvValue, &ppEvent);
      if ( v21 >= 0 )
      {
        v26 = ppEvent;
        v45[0] = 0;
        v46 = 0;
        v43 = 0;
        if ( ppEvent
          && ((int (__fastcall *)(IMFMediaEvent *, int *))ppEvent->lpVtbl->GetType)(ppEvent, &v46) >= 0
          && v46 == 1
          && ((int (__fastcall *)(struct IMFMediaEvent *, int *))v26->lpVtbl->GetStatus)(v26, &v43) >= 0 )
        {
          v33 = (wchar_t *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v34 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30, v31, v32);
            CallStackTracing::s_wpInstance = v34;
            if ( v34 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 2032) )
            {
              v33 = (wchar_t *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v33 = &qword_1801B07E0;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)v33 + 8) )
          {
            v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v33);
            if ( v43 < 0 && *((_DWORD *)v37 + 499) != v43 )
              CallStackContext::TraceFailure(v37, "CMFMediaEventGenerator::QueueEvent", 458, v43);
          }
        }
        EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
        if ( *((_DWORD *)v17 + 12) )
        {
          v21 = -1072873851;
        }
        else
        {
          if ( (unsigned __int8)byte_1801B110B >= 0x10u )
            MFTRACE_MEDIA_EVENT_IMPL(0x30001u, v27, v26);
          v21 = MFCreateMediaEventResult(v26, v45);
          if ( v21 >= 0 )
          {
            v28 = (__int64 *)*((_QWORD *)v17 + 9);
            v29 = v45[0] + 128LL;
            *(_QWORD *)(v45[0] + 128LL) = v17 + 64;
            *(_QWORD *)(v29 + 8) = v28;
            *v28 = v29;
            ++*((_DWORD *)v17 + 14);
            *((_QWORD *)v17 + 9) = v29;
            v21 = CMFMediaEventGenerator::CheckDispatchEvent((CMFMediaEventGenerator *)v17);
          }
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 8));
      }
      if ( ppEvent )
        ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
    }
    if ( (unsigned __int8)byte_1801B110B >= 0x20u )
      WPP_SF_qL(*((_QWORD *)WPP_GLOBAL_Control + 17), v10, v11, v17, v21);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v46);
    if ( v21 < 0 )
    {
      v35 = (wchar_t *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (wchar_t *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = &qword_1801B07E0;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v38 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
        if ( *((_DWORD *)v38 + 499) != v21 )
          CallStackContext::TraceFailure(v38, "CBaseStreamSink::QueueEvent", 244, v21);
      }
      if ( g_wppLevels )
      {
        v39 = 27;
        goto LABEL_58;
      }
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v46);
  LeaveCriticalSection(v5);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180009650  push    rbp
0x180009652  push    rbx
0x180009653  push    rsi
0x180009654  push    rdi
0x180009655  push    r12
0x180009657  push    r13
0x180009659  push    r14
0x18000965b  push    r15
0x18000965d  mov     rbp, rsp
0x180009660  sub     rsp, 58h
0x180009664  lea     r13, [rcx+0F8h]
0x18000966b  mov     rbx, rcx
0x18000966e  mov     rcx, r13; lpCriticalSection
0x180009671  mov     edi, r9d
0x180009674  mov     r15, r8
0x180009677  mov     r14d, edx
0x18000967a  call    cs:__imp_EnterCriticalSection
0x180009680  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180009687  test    rcx, rcx
0x18000968a  jz      loc_180009846
0x180009690  cmp     byte ptr [rcx+8], 0
0x180009694  lea     rsi, aCbasestreamsin_23; "CBaseStreamSink::QueueEvent"
0x18000969b  jz      short loc_1800096CC
0x18000969d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800096a2  mov     ecx, [rax+7C4h]
0x1800096a8  cmp     ecx, [rax+7C8h]
0x1800096ae  jnb     short loc_1800096BF
0x1800096b0  add     rcx, rcx
0x1800096b3  mov     [rax+rcx*8], rsi
0x1800096b7  mov     dword ptr [rax+rcx*8+8], 0E3h
0x1800096bf  inc     dword ptr [rax+7C4h]
0x1800096c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800096cc  lea     r12, [rbx-10h]
0x1800096d0  cmp     dword ptr [r12+158h], 7
0x1800096d9  jz      loc_1800099A4
0x1800096df  lea     rsi, [rbx+58h]
0x1800096e3  test    rcx, rcx
0x1800096e6  jz      loc_180009857
0x1800096ec  cmp     byte ptr [rcx+8], 0
0x1800096f0  lea     rbx, aCmfmediaeventg_0; "CMFMediaEventGenerator::QueueEvent"
0x1800096f7  jz      short loc_180009721
0x1800096f9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800096fe  mov     ecx, [rax+7C4h]
0x180009704  cmp     ecx, [rax+7C8h]
0x18000970a  jnb     short loc_18000971B
0x18000970c  add     rcx, rcx
0x18000970f  mov     [rax+rcx*8], rbx
0x180009713  mov     dword ptr [rax+rcx*8+8], 16Eh
0x18000971b  inc     dword ptr [rax+7C4h]
0x180009721  cmp     cs:byte_1801B110B, 10h
0x180009728  jnb     loc_1800099C0
0x18000972e  cmp     dword ptr [rsi+30h], 0
0x180009732  jnz     loc_1800098EA
0x180009738  mov     r9, [rbp+pvValue]; pvValue
0x18000973c  lea     rax, [rbp+var_20]
0x180009740  mov     r8d, edi; hrStatus
0x180009743  mov     [rsp+58h+ppEvent], rax; ppEvent
0x180009748  mov     rdx, r15; guidExtendedType
0x18000974b  mov     [rbp+var_20], 0
0x180009753  mov     ecx, r14d; met
0x180009756  call    cs:__imp_MFCreateMediaEvent
0x18000975c  xor     r14d, r14d
0x18000975f  mov     ebx, eax
0x180009761  test    eax, eax
0x180009763  jns     short loc_1800097BD
0x180009765  mov     rcx, [rbp+var_20]
0x180009769  test    rcx, rcx
0x18000976c  jz      short loc_18000977A
0x18000976e  mov     rax, [rcx]
0x180009771  mov     rax, [rax+10h]
0x180009775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000977a  cmp     cs:byte_1801B110B, 20h ; ' '
0x180009781  jnb     loc_180009A2D
0x180009787  lea     rcx, [rbp+arg_0]; this
0x18000978b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180009790  test    ebx, ebx
0x180009792  js      loc_180009901
0x180009798  lea     rcx, [rbp+arg_0]; this
0x18000979c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800097a1  mov     rcx, r13; lpCriticalSection
0x1800097a4  call    cs:__imp_LeaveCriticalSection
0x1800097aa  mov     eax, ebx
0x1800097ac  add     rsp, 58h
0x1800097b0  pop     r15
0x1800097b2  pop     r14
0x1800097b4  pop     r13
0x1800097b6  pop     r12
0x1800097b8  pop     rdi
0x1800097b9  pop     rsi
0x1800097ba  pop     rbx
0x1800097bb  pop     rbp
0x1800097bc  retn
0x1800097bd  mov     rbx, [rbp+var_20]
0x1800097c1  mov     [rbp+var_18], r14
0x1800097c5  mov     [rbp+arg_0], r14d
0x1800097c9  mov     [rbp+var_28], r14d
0x1800097cd  test    rbx, rbx
0x1800097d0  jnz     loc_180009868
0x1800097d6  lea     rdi, [rsi+8]
0x1800097da  mov     rcx, rdi; lpCriticalSection
0x1800097dd  call    cs:__imp_EnterCriticalSection
0x1800097e3  cmp     [rsi+30h], r14d
0x1800097e7  jnz     loc_1800098F7
0x1800097ed  cmp     cs:byte_1801B110B, 10h
0x1800097f4  jnb     loc_180009A1B
0x1800097fa  lea     rdx, [rbp+var_18]
0x1800097fe  mov     rcx, rbx
0x180009801  call    cs:__imp_MFCreateMediaEventResult
0x180009807  mov     ebx, eax
0x180009809  test    eax, eax
0x18000980b  js      short loc_180009838
0x18000980d  mov     rdx, [rbp+var_18]
0x180009811  lea     rcx, [rsi+40h]
0x180009815  mov     rax, [rcx+8]
0x180009819  sub     rdx, 0FFFFFFFFFFFFFF80h
0x18000981d  mov     [rdx], rcx
0x180009820  mov     [rdx+8], rax
0x180009824  mov     [rax], rdx
0x180009827  inc     dword ptr [rsi+38h]
0x18000982a  mov     [rcx+8], rdx
0x18000982e  mov     rcx, rsi; this
0x180009831  call    ?CheckDispatchEvent@CMFMediaEventGenerator@@IEAAJXZ; CMFMediaEventGenerator::CheckDispatchEvent(void)
0x180009836  mov     ebx, eax
0x180009838  mov     rcx, rdi; lpCriticalSection
0x18000983b  call    cs:__imp_LeaveCriticalSection
0x180009841  jmp     loc_180009765
0x180009846  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18000984b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009852  jmp     loc_180009690
0x180009857  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18000985c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009863  jmp     loc_1800096EC
0x180009868  mov     rax, [rbx]
0x18000986b  lea     rdx, [rbp+arg_0]
0x18000986f  mov     rcx, rbx
0x180009872  mov     rax, [rax+108h]
0x180009879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000987e  test    eax, eax
0x180009880  js      loc_1800097D6
0x180009886  cmp     [rbp+arg_0], 1
0x18000988a  jnz     loc_1800097D6
0x180009890  mov     rax, [rbx]
0x180009893  lea     rdx, [rbp+var_28]
0x180009897  mov     rcx, rbx
0x18000989a  mov     rax, [rax+118h]
0x1800098a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098a6  test    eax, eax
0x1800098a8  js      loc_1800097D6
0x1800098ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800098b5  test    rcx, rcx
0x1800098b8  jnz     loc_180009A0C
0x1800098be  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800098c4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800098cb  mov     rcx, rax
0x1800098ce  test    rax, rax
0x1800098d1  jnz     loc_1800099EC
0x1800098d7  lea     rcx, qword_1801B07E0
0x1800098de  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800098e5  jmp     loc_180009A0C
0x1800098ea  mov     ebx, 0C00D3E85h
0x1800098ef  xor     r14d, r14d
0x1800098f2  jmp     loc_18000977A
0x1800098f7  mov     ebx, 0C00D3E85h
0x1800098fc  jmp     loc_180009838
0x180009901  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180009908  test    rcx, rcx
0x18000990b  jnz     loc_180009A6C
0x180009911  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180009917  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18000991e  mov     rcx, rax
0x180009921  test    rax, rax
0x180009924  jnz     loc_180009A4C
0x18000992a  lea     rcx, qword_1801B07E0
0x180009931  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180009938  jmp     loc_180009A6C
0x18000993d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180009942  mov     r9d, [rbp+var_28]; int
0x180009946  test    r9d, r9d
0x180009949  jns     loc_1800097D6
0x18000994f  cmp     [rax+7CCh], r9d
0x180009956  jz      loc_1800097D6
0x18000995c  mov     r8d, 1CAh; int
0x180009962  lea     rdx, aCmfmediaeventg_0; "CMFMediaEventGenerator::QueueEvent"
0x180009969  mov     rcx, rax; this
0x18000996c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180009971  jmp     loc_1800097D6
0x180009976  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18000997b  cmp     [rax+7CCh], ebx
0x180009981  jz      loc_180009A76
0x180009987  mov     r9d, ebx; int
0x18000998a  lea     rdx, aCbasestreamsin_23; "CBaseStreamSink::QueueEvent"
0x180009991  mov     r8d, 0F4h; int
0x180009997  mov     rcx, rax; this
0x18000999a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18000999f  jmp     loc_180009A76
0x1800099a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 4; MFWppLevels g_wppLevels
0x1800099ab  mov     ebx, 0C00D4A38h
0x1800099b0  jb      loc_180009798
0x1800099b6  mov     edx, 1Ah
0x1800099bb  jmp     loc_180009A88
0x1800099c0  mov     ecx, r14d; unsigned int
0x1800099c3  call    ?MFTRACE_STRING_FROM_MET@@YAPEBDK@Z; MFTRACE_STRING_FROM_MET(ulong)
0x1800099c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099cf  mov     r9, rsi
0x1800099d2  mov     [rsp+58h+var_30], edi
0x1800099d6  mov     [rsp+58h+ppEvent], rax
0x1800099db  mov     rcx, [rcx+88h]
0x1800099e2  call    WPP_SF_qsL
0x1800099e7  jmp     loc_18000972E
0x1800099ec  mov     rax, [rax]
0x1800099ef  mov     edx, 7F0h
0x1800099f4  mov     rax, [rax+8]
0x1800099f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099fd  test    eax, eax
0x1800099ff  jz      loc_1800098D7
0x180009a05  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180009a0c  cmp     [rcx+8], r14b
0x180009a10  jz      loc_1800097D6
0x180009a16  jmp     loc_18000993D
0x180009a1b  mov     r8, rbx; struct IMFMediaEvent *
0x180009a1e  mov     ecx, 30001h; unsigned int
0x180009a23  call    ?MFTRACE_MEDIA_EVENT_IMPL@@YAXKKPEAUIMFMediaEvent@@@Z; MFTRACE_MEDIA_EVENT_IMPL(ulong,ulong,IMFMediaEvent *)
0x180009a28  jmp     loc_1800097FA
0x180009a2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a34  mov     r9, rsi
0x180009a37  mov     dword ptr [rsp+58h+ppEvent], ebx
0x180009a3b  mov     rcx, [rcx+88h]
0x180009a42  call    WPP_SF_qL
0x180009a47  jmp     loc_180009787
0x180009a4c  mov     rax, [rax]
0x180009a4f  mov     edx, 7F0h
0x180009a54  mov     rax, [rax+8]
0x180009a58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a5d  test    eax, eax
0x180009a5f  jz      loc_18000992A
0x180009a65  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180009a6c  cmp     [rcx+8], r14b
0x180009a70  jnz     loc_180009976
0x180009a76  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180009a7d  jb      loc_180009798
0x180009a83  mov     edx, 1Bh
0x180009a88  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a8f  lea     r8, WPP_85ded7c3193c34fe64ab2cb119f9c690_Traceguids
0x180009a96  mov     r9, r12
0x180009a99  mov     dword ptr [rsp+58h+ppEvent], ebx
0x180009a9d  mov     rcx, [rcx+10h]
0x180009aa1  call    WPP_SF_qD
0x180009aa6  jmp     loc_180009798
```
