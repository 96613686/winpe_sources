# CPolicyCriticalSection::RegisterWaitForLockNotificationOrClientCancellation(CPolicyCriticalSection::CLockCallbackContext *,void *,void *,ulong)

- ea: `0x180093234`
- end: `0x180093422`
- name: `?RegisterWaitForLockNotificationOrClientCancellation@CPolicyCriticalSection@@AEAAKPEAVCLockCallbackContext@1@PEAX1K@Z`
- size: `494`
- prototype: `unsigned int(CPolicyCriticalSection *__hidden this, struct CPolicyCriticalSection::CLockCallbackContext *, void *, void *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000dec0`

## callees

- `0x180045660`
- `0x18006f66c`
- `0x180075ec0`
- `0x180093234`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009336c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800933a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180093403`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009336c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800933a3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180093403`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093309`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800933b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800933c9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800933b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800933c9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800932de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800932fa`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800932de`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800932fa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800933e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800933f3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800933e3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800933f3`

## string_xrefs

- `0x180093329`: `CreateThreadpoolWait failed with 0x%x`
- `0x180093351`: `CreateThreadpoolWait failed with 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPolicyCriticalSection::RegisterWaitForLockNotificationOrClientCancellation(
        CPolicyCriticalSection *this,
        struct CPolicyCriticalSection::CLockCallbackContext *a2,
        void *a3,
        void *a4)
{
  struct CPolicyCriticalSection::CLockCallbackContext *v6; // rbx
  struct _RTL_CRITICAL_SECTION *v8; // rdx
  DWORD LastError; // edi
  PTP_WAIT ThreadpoolWait; // rax
  PTP_WAIT v11; // rax
  struct _TP_WAIT *v12; // rcx
  struct _TP_WAIT *v13; // rcx
  struct CPolicyCriticalSection::CLockCallbackContext *v14; // rbx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+50h] [rbp+30h] BYREF
  struct CPolicyCriticalSection::CLockCallbackContext *v17; // [rsp+58h] [rbp+38h] BYREF

  v17 = a2;
  v6 = a2;
  v8 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 7);
  if ( !v8 )
  {
    LastError = -2147418113;
LABEL_27:
    v12 = (struct _TP_WAIT *)*((_QWORD *)v6 + 2);
    if ( v12 )
    {
      CloseThreadpoolWait(v12);
      *((_QWORD *)v6 + 2) = 0;
    }
    v13 = (struct _TP_WAIT *)*((_QWORD *)v6 + 3);
    if ( v13 )
    {
      CloseThreadpoolWait(v13);
      *((_QWORD *)v6 + 3) = 0;
    }
    return LastError;
  }
  XEnterCritSec::XEnterCritSec((XEnterCritSec *)&lpCriticalSection, v8);
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"Registering wait for lock notification for %s", *((_QWORD *)this + 11));
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"Registering wait for lock notification for %s", *((_QWORD *)this + 11));
    }
  }
  ThreadpoolWait = CreateThreadpoolWait(CPolicyCriticalSection::LockEventCallback, v6, 0);
  *((_QWORD *)v6 + 2) = ThreadpoolWait;
  if ( ThreadpoolWait )
  {
    v11 = CreateThreadpoolWait(CPolicyCriticalSection::LockEventCallback, v6, 0);
    *((_QWORD *)v6 + 3) = v11;
    if ( v11 )
    {
      LastError = STLWrap_List<CPolicyCriticalSection::CLockCallbackContext *>::push_front((char *)this + 64, &v17);
      if ( !LastError )
      {
        if ( *((_QWORD *)this + 9) )
        {
          v14 = v17;
          SetThreadpoolWait(*((PTP_WAIT *)v17 + 2), a3, 0);
          SetThreadpoolWait(*((PTP_WAIT *)v14 + 3), a4, 0);
          if ( lpCriticalSection )
            LeaveCriticalSection(lpCriticalSection);
          return LastError;
        }
        LastError = -2147418113;
      }
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
      v6 = v17;
      goto LABEL_27;
    }
  }
  LastError = GetLastError();
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"CreateThreadpoolWait failed with 0x%x", LastError);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"CreateThreadpoolWait failed with 0x%x", LastError);
    }
  }
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  if ( LastError )
    goto LABEL_27;
  return LastError;
}

```

## disassembly

```asm
0x180093234  mov     [rsp-28h+arg_10], rbx
0x180093239  mov     [rsp-28h+arg_18], rsi
0x18009323e  mov     [rsp-28h+arg_8], rdx
0x180093243  push    rbp
0x180093244  push    rdi
0x180093245  push    r12
0x180093247  push    r14
0x180093249  push    r15
0x18009324b  mov     rbp, rsp
0x18009324e  sub     rsp, 20h
0x180093252  mov     r14, r9
0x180093255  mov     r15, r8
0x180093258  mov     rbx, rdx
0x18009325b  mov     rsi, rcx
0x18009325e  mov     rdx, [rcx+38h]; struct _RTL_CRITICAL_SECTION *
0x180093262  xor     r12d, r12d
0x180093265  test    rdx, rdx
0x180093268  jnz     short loc_180093274
0x18009326a  mov     edi, 8000FFFFh
0x18009326f  jmp     loc_1800933AD
0x180093274  lea     rcx, [rbp+lpCriticalSection]; this
0x180093278  call    ??0XEnterCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; XEnterCritSec::XEnterCritSec(_RTL_CRITICAL_SECTION *)
0x18009327d  nop
0x18009327e  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180093285  jz      short loc_1800932D1
0x180093287  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009328e  test    rax, rax
0x180093291  jz      short loc_1800932AA
0x180093293  mov     r8, [rsi+58h]
0x180093297  lea     rdx, aRegisteringWai; "Registering wait for lock notification "...
0x18009329e  mov     ecx, 4
0x1800932a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800932a8  jmp     short loc_1800932D1
0x1800932aa  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800932b1  jz      short loc_1800932D1
0x1800932b3  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800932ba  jz      short loc_1800932D1
0x1800932bc  mov     r8, [rsi+58h]
0x1800932c0  lea     rdx, aRegisteringWai; "Registering wait for lock notification "...
0x1800932c7  mov     ecx, 4; unsigned int
0x1800932cc  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800932d1  xor     r8d, r8d; pcbe
0x1800932d4  mov     rdx, rbx; pv
0x1800932d7  lea     rcx, ?LockEventCallback@CPolicyCriticalSection@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800932de  call    cs:__imp_CreateThreadpoolWait
0x1800932e4  mov     [rbx+10h], rax
0x1800932e8  test    rax, rax
0x1800932eb  jz      short loc_180093309
0x1800932ed  xor     r8d, r8d; pcbe
0x1800932f0  mov     rdx, rbx; pv
0x1800932f3  lea     rcx, ?LockEventCallback@CPolicyCriticalSection@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800932fa  call    cs:__imp_CreateThreadpoolWait
0x180093300  mov     [rbx+18h], rax
0x180093304  test    rax, rax
0x180093307  jnz     short loc_18009337C
0x180093309  call    cs:__imp_GetLastError
0x18009330f  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180093316  mov     edi, eax
0x180093318  jz      short loc_180093363
0x18009331a  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180093321  test    rax, rax
0x180093324  jz      short loc_18009333C
0x180093326  mov     r8d, edi
0x180093329  lea     rdx, aCreatethreadpo; "CreateThreadpoolWait failed with 0x%x"
0x180093330  mov     ecx, 2
0x180093335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009333a  jmp     short loc_180093363
0x18009333c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180093343  jz      short loc_180093363
0x180093345  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009334c  jz      short loc_180093363
0x18009334e  mov     r8d, edi
0x180093351  lea     rdx, aCreatethreadpo; "CreateThreadpoolWait failed with 0x%x"
0x180093358  mov     ecx, 2; unsigned int
0x18009335d  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180093362  nop
0x180093363  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180093367  test    rcx, rcx
0x18009336a  jz      short loc_180093372
0x18009336c  call    cs:__imp_LeaveCriticalSection
0x180093372  test    edi, edi
0x180093374  jz      loc_180093409
0x18009337a  jmp     short loc_1800933AD
0x18009337c  lea     rcx, [rsi+40h]
0x180093380  lea     rdx, [rbp+arg_8]
0x180093384  call    ?push_front@?$STLWrap_List@PEAVCLockCallbackContext@CPolicyCriticalSection@@@@QEAAKAEBQEAVCLockCallbackContext@CPolicyCriticalSection@@@Z; STLWrap_List<CPolicyCriticalSection::CLockCallbackContext *>::push_front(CPolicyCriticalSection::CLockCallbackContext * const &)
0x180093389  mov     edi, eax
0x18009338b  test    eax, eax
0x18009338d  jnz     short loc_18009339A
0x18009338f  cmp     [rsi+48h], r12
0x180093393  jnz     short loc_1800933D5
0x180093395  mov     edi, 8000FFFFh
0x18009339a  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18009339e  test    rcx, rcx
0x1800933a1  jz      short loc_1800933A9
0x1800933a3  call    cs:__imp_LeaveCriticalSection
0x1800933a9  mov     rbx, [rbp+arg_8]
0x1800933ad  mov     rcx, [rbx+10h]; pwa
0x1800933b1  test    rcx, rcx
0x1800933b4  jz      short loc_1800933C0
0x1800933b6  call    cs:__imp_CloseThreadpoolWait
0x1800933bc  mov     [rbx+10h], r12
0x1800933c0  mov     rcx, [rbx+18h]; pwa
0x1800933c4  test    rcx, rcx
0x1800933c7  jz      short loc_180093409
0x1800933c9  call    cs:__imp_CloseThreadpoolWait
0x1800933cf  mov     [rbx+18h], r12
0x1800933d3  jmp     short loc_180093409
0x1800933d5  xor     r8d, r8d; pftTimeout
0x1800933d8  mov     rdx, r15; h
0x1800933db  mov     rbx, [rbp+arg_8]
0x1800933df  mov     rcx, [rbx+10h]; pwa
0x1800933e3  call    cs:__imp_SetThreadpoolWait
0x1800933e9  xor     r8d, r8d; pftTimeout
0x1800933ec  mov     rdx, r14; h
0x1800933ef  mov     rcx, [rbx+18h]; pwa
0x1800933f3  call    cs:__imp_SetThreadpoolWait
0x1800933f9  nop
0x1800933fa  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800933fe  test    rcx, rcx
0x180093401  jz      short loc_180093409
0x180093403  call    cs:__imp_LeaveCriticalSection
0x180093409  mov     eax, edi
0x18009340b  mov     rbx, [rsp+20h+arg_10]
0x180093410  mov     rsi, [rsp+20h+arg_18]
0x180093415  add     rsp, 20h
0x180093419  pop     r15
0x18009341b  pop     r14
0x18009341d  pop     r12
0x18009341f  pop     rdi
0x180093420  pop     rbp
0x180093421  retn
```
