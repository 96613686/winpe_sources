# CGroupPolicySession::RefreshGroupPolicyForPrincipal(int,ulong,_tagREFRESH_RESULT *)

- ea: `0x180091020`
- end: `0x180091423`
- name: `?RefreshGroupPolicyForPrincipal@CGroupPolicySession@@QEAAKHKPEAU_tagREFRESH_RESULT@@@Z`
- size: `1027`
- prototype: `unsigned int __fastcall(CGroupPolicySession *__hidden this, int, unsigned int, struct _tagREFRESH_RESULT *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18008b168`
- `0x18008b310`

## callees

- `0x18000a52c`
- `0x180039148`
- `0x180045660`
- `0x180046de0`
- `0x180049a40`
- `0x180049b90`
- `0x18005bcc4`
- `0x180075ec0`
- `0x18009033c`
- `0x1800906e4`
- `0x180091020`
- `0x18009142c`
- `0x1800b2738`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180091276`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180091276`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800910e6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800910e6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800911a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800912d8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800911a1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800912d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800910b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800910cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800913eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800910b0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800910cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800913eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091101`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091101`

## string_xrefs

- `0x180091167`: `CGPApplicationService::RefreshEvent Wait to Make sure the service is completely initialized. `
- `0x180091189`: `CGPApplicationService::RefreshEvent Wait to Make sure the service is completely initialized. `
- `0x1800911c3`: `CGPApplicationService::RefreshEvent Wait failed with error 0x%x.`
- `0x1800911ea`: `CGPApplicationService::RefreshEvent Wait failed with error 0x%x.`
- `0x180091219`: `m_pPolicyInfoReadyEvent triggered by shutdown.`
- `0x180091240`: `m_pPolicyInfoReadyEvent triggered by shutdown.`
- `0x180091375`: `CGroupPolicySession::RefreshGroupPolicyForPrincipal: Completed WaitForSingleObject.`
- `0x18009139c`: `CGroupPolicySession::RefreshGroupPolicyForPrincipal: Completed WaitForSingleObject.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGroupPolicySession::RefreshGroupPolicyForPrincipal(
        CGroupPolicySession *this,
        int a2,
        DWORD a3,
        struct _tagREFRESH_RESULT *a4)
{
  int v6; // edi
  HANDLE v8; // rbx
  DWORD LastError; // edi
  __int64 *v10; // rax
  __int64 v11; // rax
  int v12; // r12d
  HANDLE v13; // r13
  HANDLE EventW; // rax
  DWORD v15; // eax
  __int64 v16; // r8
  struct _GPOINFO *GPOInfo; // rax
  void *v18; // rcx
  HANDLE TargetHandle; // [rsp+20h] [rbp-28h] BYREF
  HANDLE hSourceHandle; // [rsp+28h] [rbp-20h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp-18h] BYREF
  _BYTE v23[16]; // [rsp+38h] [rbp-10h] BYREF

  v6 = a2;
  XAddRefRelease::XAddRefRelease((XAddRefRelease *)v23, this);
  v8 = 0;
  hSourceHandle = 0;
  TargetHandle = 0;
  if ( (unsigned int)IsDSRepairBoot() )
  {
    LastError = 50;
    CGPOperationalTraceEvent::ReportOperationalEventInternal(1, 4104, 50, 0);
    goto LABEL_72;
  }
  XEnterCritSec::XEnterCritSec((XEnterCritSec *)&lpCriticalSection, *((struct _RTL_CRITICAL_SECTION **)this + 34));
  v10 = (__int64 *)*((_QWORD *)this + 56);
  if ( v10 )
  {
    v11 = *v10;
    if ( v11 )
    {
      if ( *(_DWORD *)(v11 + 8) > 5u )
      {
        if ( lpCriticalSection )
          LeaveCriticalSection(lpCriticalSection);
        LastError = 170;
        goto LABEL_72;
      }
    }
  }
  v12 = 0;
  v13 = 0;
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( a3 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    XHandle::operator=(&hSourceHandle, EventW);
    v8 = hSourceHandle;
    if ( !hSourceHandle )
    {
      LastError = GetLastError();
      goto LABEL_59;
    }
    LastError = DuplicateEventHandle(hSourceHandle, &TargetHandle);
    if ( LastError )
      goto LABEL_72;
    LastError = CGroupPolicySession::AddToRefreshPolicyCallersList(this, TargetHandle);
    if ( LastError )
      goto LABEL_72;
    v12 = 1;
    v13 = TargetHandle;
    TargetHandle = 0;
    v6 = a2;
  }
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPApplicationService::RefreshEvent Wait to Make sure the service is completely initialized. ");
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(
        4u,
        L"CGPApplicationService::RefreshEvent Wait to Make sure the service is completely initialized. ");
    }
  }
  v15 = WaitForSingleObject(*((HANDLE *)this + 27), 0x1388u);
  v16 = v15;
  if ( (v15 & 0x80000000) != 0 && *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGPApplicationService::RefreshEvent Wait failed with error 0x%x.", v15);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGPApplicationService::RefreshEvent Wait failed with error 0x%x.", v15);
    }
  }
  if ( *((_DWORD *)this + 81) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"m_pPolicyInfoReadyEvent triggered by shutdown.", v16);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"m_pPolicyInfoReadyEvent triggered by shutdown.", v16);
      }
    }
    LastError = 1115;
    goto LABEL_60;
  }
  GPOInfo = CGroupPolicySession::GetGPOInfo(this);
  if ( GPOInfo )
  {
    if ( v6 )
      v18 = (void *)*((_QWORD *)GPOInfo + 11);
    else
      v18 = (void *)*((_QWORD *)GPOInfo + 10);
    SetEvent(v18);
  }
  if ( a3 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGroupPolicySession::RefreshGroupPolicyForPrincipal: Beginning WaitForSingleObject.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGroupPolicySession::RefreshGroupPolicyForPrincipal: Beginning WaitForSingleObject.");
      }
    }
    LastError = WaitForSingleObject(v8, a3);
    if ( LastError )
    {
      if ( LastError == 258 )
        LastError = 1460;
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(4u, L"CGroupPolicySession::RefreshGroupPolicyForPrincipal: Failed WaitForSingleObject.");
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(4u, L"CGroupPolicySession::RefreshGroupPolicyForPrincipal: Failed WaitForSingleObject.");
        }
LABEL_59:
        if ( !LastError )
          goto LABEL_72;
      }
LABEL_60:
      if ( v12 )
        CGroupPolicySession::RemoveFromRefreshPolicyCallersList(this, v13);
      goto LABEL_72;
    }
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"CGroupPolicySession::RefreshGroupPolicyForPrincipal: Completed WaitForSingleObject.");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"CGroupPolicySession::RefreshGroupPolicyForPrincipal: Completed WaitForSingleObject.");
      }
    }
  }
  if ( a4 )
  {
    XEnterCritSec::XEnterCritSec((XEnterCritSec *)&lpCriticalSection, *((struct _RTL_CRITICAL_SECTION **)this + 34));
    *(_OWORD *)a4 = *(_OWORD *)((char *)this + 456);
    *((_DWORD *)a4 + 4) = *((_DWORD *)this + 118);
    *((_DWORD *)a4 + 5) = *((_DWORD *)this + 119);
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
  LastError = 0;
LABEL_72:
  XHandle::~XHandle(&TargetHandle);
  XHandle::~XHandle(&hSourceHandle);
  XAddRefRelease::~XAddRefRelease((XAddRefRelease *)v23);
  return LastError;
}

```

## disassembly

```asm
0x180091020  mov     [rsp-40h+arg_8], edx
0x180091024  push    rbp
0x180091025  push    rbx
0x180091026  push    rsi
0x180091027  push    rdi
0x180091028  push    r12
0x18009102a  push    r13
0x18009102c  push    r14
0x18009102e  push    r15
0x180091030  mov     rbp, rsp
0x180091033  sub     rsp, 48h
0x180091037  mov     r14, r9
0x18009103a  mov     r15d, r8d
0x18009103d  mov     edi, edx
0x18009103f  mov     rsi, rcx
0x180091042  mov     rdx, rcx; struct IAddRefRelease *
0x180091045  lea     rcx, [rbp+var_10]; this
0x180091049  call    ??0XAddRefRelease@@QEAA@PEAVIAddRefRelease@@@Z; XAddRefRelease::XAddRefRelease(IAddRefRelease *)
0x18009104e  nop
0x18009104f  xor     ebx, ebx
0x180091051  mov     [rbp+hSourceHandle], rbx
0x180091055  mov     [rbp+TargetHandle], rbx
0x180091059  call    ?IsDSRepairBoot@@YAHXZ; IsDSRepairBoot(void)
0x18009105e  test    eax, eax
0x180091060  jz      short loc_18009107D
0x180091062  lea     edi, [rbx+32h]
0x180091065  xor     r9d, r9d
0x180091068  mov     r8d, edi
0x18009106b  mov     edx, 1008h
0x180091070  lea     ecx, [rbx+1]
0x180091073  call    ?ReportOperationalEventInternal@CGPOperationalTraceEvent@@KAKW4tagLogLevel@@KKPEBG@Z; CGPOperationalTraceEvent::ReportOperationalEventInternal(tagLogLevel,ulong,ulong,ushort const *)
0x180091078  jmp     loc_1800913F3
0x18009107d  mov     rdx, [rsi+110h]; struct _RTL_CRITICAL_SECTION *
0x180091084  lea     rcx, [rbp+lpCriticalSection]; this
0x180091088  call    ??0XEnterCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; XEnterCritSec::XEnterCritSec(_RTL_CRITICAL_SECTION *)
0x18009108d  mov     rax, [rsi+1C0h]
0x180091094  test    rax, rax
0x180091097  jz      short loc_1800910C0
0x180091099  mov     rax, [rax]
0x18009109c  test    rax, rax
0x18009109f  jz      short loc_1800910C0
0x1800910a1  cmp     dword ptr [rax+8], 5
0x1800910a5  jbe     short loc_1800910C0
0x1800910a7  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800910ab  test    rcx, rcx
0x1800910ae  jz      short loc_1800910B6
0x1800910b0  call    cs:__imp_LeaveCriticalSection
0x1800910b6  mov     edi, 0AAh
0x1800910bb  jmp     loc_1800913F3
0x1800910c0  xor     r12d, r12d
0x1800910c3  xor     r13d, r13d
0x1800910c6  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800910ca  test    rcx, rcx
0x1800910cd  jz      short loc_1800910D5
0x1800910cf  call    cs:__imp_LeaveCriticalSection
0x1800910d5  test    r15d, r15d
0x1800910d8  jz      short loc_18009114D
0x1800910da  xor     r9d, r9d; lpName
0x1800910dd  xor     r8d, r8d; bInitialState
0x1800910e0  lea     edx, [r9+1]; bManualReset
0x1800910e4  xor     ecx, ecx; lpEventAttributes
0x1800910e6  call    cs:__imp_CreateEventW
0x1800910ec  mov     rdx, rax
0x1800910ef  lea     rcx, [rbp+hSourceHandle]
0x1800910f3  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x1800910f8  mov     rbx, [rbp+hSourceHandle]
0x1800910fc  test    rbx, rbx
0x1800910ff  jnz     short loc_18009110E
0x180091101  call    cs:__imp_GetLastError
0x180091107  mov     edi, eax
0x180091109  jmp     loc_18009133F
0x18009110e  lea     rdx, [rbp+TargetHandle]; lpTargetHandle
0x180091112  mov     rcx, rbx; hSourceHandle
0x180091115  call    ?DuplicateEventHandle@@YAKPEAXPEAPEAX@Z; DuplicateEventHandle(void *,void * *)
0x18009111a  mov     edi, eax
0x18009111c  test    eax, eax
0x18009111e  jnz     loc_1800913F3
0x180091124  mov     rdx, [rbp+TargetHandle]; void *
0x180091128  mov     rcx, rsi; this
0x18009112b  call    ?AddToRefreshPolicyCallersList@CGroupPolicySession@@AEAAKPEAX@Z; CGroupPolicySession::AddToRefreshPolicyCallersList(void *)
0x180091130  mov     edi, eax
0x180091132  test    eax, eax
0x180091134  jnz     loc_1800913F3
0x18009113a  lea     r12d, [rax+1]
0x18009113e  mov     r13, [rbp+TargetHandle]
0x180091142  mov     [rbp+TargetHandle], 0
0x18009114a  mov     edi, [rbp+arg_8]
0x18009114d  mov     ecx, 4; unsigned int
0x180091152  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180091159  jz      short loc_180091195
0x18009115b  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180091162  test    rax, rax
0x180091165  jz      short loc_180091175
0x180091167  lea     rdx, aCgpapplication_24; "CGPApplicationService::RefreshEvent Wai"...
0x18009116e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091173  jmp     short loc_180091195
0x180091175  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x18009117d  jz      short loc_180091195
0x18009117f  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180091187  jz      short loc_180091195
0x180091189  lea     rdx, aCgpapplication_24; "CGPApplicationService::RefreshEvent Wai"...
0x180091190  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180091195  mov     edx, 1388h; dwMilliseconds
0x18009119a  mov     rcx, [rsi+0D8h]; hHandle
0x1800911a1  call    cs:__imp_WaitForSingleObject
0x1800911a7  mov     r8d, eax
0x1800911aa  test    eax, eax
0x1800911ac  jns     short loc_1800911FB
0x1800911ae  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800911b5  jz      short loc_1800911FB
0x1800911b7  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800911be  test    rax, rax
0x1800911c1  jz      short loc_1800911D6
0x1800911c3  lea     rdx, aCgpapplication_48; "CGPApplicationService::RefreshEvent Wai"...
0x1800911ca  mov     ecx, 4
0x1800911cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800911d4  jmp     short loc_1800911FB
0x1800911d6  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800911de  jz      short loc_1800911FB
0x1800911e0  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800911e8  jz      short loc_1800911FB
0x1800911ea  lea     rdx, aCgpapplication_48; "CGPApplicationService::RefreshEvent Wai"...
0x1800911f1  mov     ecx, 4; unsigned int
0x1800911f6  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800911fb  cmp     dword ptr [rsi+144h], 0
0x180091202  jz      short loc_18009125B
0x180091204  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18009120b  jz      short loc_180091251
0x18009120d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180091214  test    rax, rax
0x180091217  jz      short loc_18009122C
0x180091219  lea     rdx, aMPpolicyinfore; "m_pPolicyInfoReadyEvent triggered by sh"...
0x180091220  mov     ecx, 4
0x180091225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009122a  jmp     short loc_180091251
0x18009122c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180091234  jz      short loc_180091251
0x180091236  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009123e  jz      short loc_180091251
0x180091240  lea     rdx, aMPpolicyinfore; "m_pPolicyInfoReadyEvent triggered by sh"...
0x180091247  mov     ecx, 4; unsigned int
0x18009124c  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180091251  mov     edi, 45Bh
0x180091256  jmp     loc_180091347
0x18009125b  mov     rcx, rsi; this
0x18009125e  call    ?GetGPOInfo@CGroupPolicySession@@AEAAPEAU_GPOINFO@@XZ; CGroupPolicySession::GetGPOInfo(void)
0x180091263  test    rax, rax
0x180091266  jz      short loc_18009127C
0x180091268  test    edi, edi
0x18009126a  jz      short loc_180091272
0x18009126c  mov     rcx, [rax+58h]
0x180091270  jmp     short loc_180091276
0x180091272  mov     rcx, [rax+50h]; hEvent
0x180091276  call    cs:__imp_SetEvent
0x18009127c  test    r15d, r15d
0x18009127f  jz      loc_1800913AD
0x180091285  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x18009128c  jz      short loc_1800912D2
0x18009128e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180091295  test    rax, rax
0x180091298  jz      short loc_1800912AD
0x18009129a  lea     rdx, aCgrouppolicyse_1; "CGroupPolicySession::RefreshGroupPolicy"...
0x1800912a1  mov     ecx, 4
0x1800912a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800912ab  jmp     short loc_1800912D2
0x1800912ad  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x1800912b5  jz      short loc_1800912D2
0x1800912b7  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800912bf  jz      short loc_1800912D2
0x1800912c1  lea     rdx, aCgrouppolicyse_1; "CGroupPolicySession::RefreshGroupPolicy"...
0x1800912c8  mov     ecx, 4; unsigned int
0x1800912cd  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800912d2  mov     edx, r15d; dwMilliseconds
0x1800912d5  mov     rcx, rbx; hHandle
0x1800912d8  call    cs:__imp_WaitForSingleObject
0x1800912de  mov     edi, eax
0x1800912e0  test    eax, eax
0x1800912e2  jz      short loc_180091360
0x1800912e4  mov     eax, 5B4h
0x1800912e9  cmp     edi, 102h
0x1800912ef  cmovz   edi, eax
0x1800912f2  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800912f9  jz      short loc_180091347
0x1800912fb  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180091302  test    rax, rax
0x180091305  jz      short loc_18009131A
0x180091307  lea     rdx, aCgrouppolicyse_62; "CGroupPolicySession::RefreshGroupPolicy"...
0x18009130e  mov     ecx, 4
0x180091313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091318  jmp     short loc_18009133F
0x18009131a  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180091322  jz      short loc_18009133F
0x180091324  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009132c  jz      short loc_18009133F
0x18009132e  lea     rdx, aCgrouppolicyse_62; "CGroupPolicySession::RefreshGroupPolicy"...
0x180091335  mov     ecx, 4; unsigned int
0x18009133a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18009133f  test    edi, edi
0x180091341  jz      loc_1800913F3
0x180091347  test    r12d, r12d
0x18009134a  jz      loc_1800913F3
0x180091350  mov     rdx, r13; void *
0x180091353  mov     rcx, rsi; this
0x180091356  call    ?RemoveFromRefreshPolicyCallersList@CGroupPolicySession@@AEAAKPEAX@Z; CGroupPolicySession::RemoveFromRefreshPolicyCallersList(void *)
0x18009135b  jmp     loc_1800913F3
0x180091360  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x180091367  jz      short loc_1800913AD
0x180091369  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180091370  test    rax, rax
0x180091373  jz      short loc_180091388
0x180091375  lea     rdx, aCgrouppolicyse_66; "CGroupPolicySession::RefreshGroupPolicy"...
0x18009137c  mov     ecx, 4
0x180091381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091386  jmp     short loc_1800913AD
0x180091388  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, 0; void * g_lpDebugMsgContextInstance
0x180091390  jz      short loc_1800913AD
0x180091392  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, 0; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009139a  jz      short loc_1800913AD
0x18009139c  lea     rdx, aCgrouppolicyse_66; "CGroupPolicySession::RefreshGroupPolicy"...
0x1800913a3  mov     ecx, 4; unsigned int
0x1800913a8  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800913ad  test    r14, r14
0x1800913b0  jz      short loc_1800913F1
0x1800913b2  mov     rdx, [rsi+110h]; struct _RTL_CRITICAL_SECTION *
0x1800913b9  lea     rcx, [rbp+lpCriticalSection]; this
0x1800913bd  call    ??0XEnterCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; XEnterCritSec::XEnterCritSec(_RTL_CRITICAL_SECTION *)
0x1800913c2  movups  xmm0, xmmword ptr [rsi+1C8h]
0x1800913c9  movdqu  xmmword ptr [r14], xmm0
0x1800913ce  mov     eax, [rsi+1D8h]
0x1800913d4  mov     [r14+10h], eax
0x1800913d8  mov     eax, [rsi+1DCh]
0x1800913de  mov     [r14+14h], eax
0x1800913e2  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800913e6  test    rcx, rcx
0x1800913e9  jz      short loc_1800913F1
0x1800913eb  call    cs:__imp_LeaveCriticalSection
0x1800913f1  xor     edi, edi
0x1800913f3  lea     rcx, [rbp+TargetHandle]; this
0x1800913f7  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x1800913fc  nop
0x1800913fd  lea     rcx, [rbp+hSourceHandle]; this
0x180091401  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x180091406  nop
0x180091407  lea     rcx, [rbp+var_10]; this
0x18009140b  call    ??1XAddRefRelease@@QEAA@XZ; XAddRefRelease::~XAddRefRelease(void)
0x180091410  mov     eax, edi
0x180091412  add     rsp, 48h
0x180091416  pop     r15
0x180091418  pop     r14
0x18009141a  pop     r13
0x18009141c  pop     r12
0x18009141e  pop     rdi
0x18009141f  pop     rsi
0x180091420  pop     rbx
0x180091421  pop     rbp
0x180091422  retn
```
