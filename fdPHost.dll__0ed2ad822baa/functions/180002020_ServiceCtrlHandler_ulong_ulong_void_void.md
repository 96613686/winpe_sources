# ServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x180002020`
- end: `0x1800021e3`
- name: `?ServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `451`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, unsigned int *lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002020`
- `0x18000284c`
- `0x180002888`
- `0x180002f84`
- `0x18000303c`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800021a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002187`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002187`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002199`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002199`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000210a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000210a`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180002140`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180002140`

## pseudocode

```c
__int64 __fastcall ServiceCtrlHandler(DWORD dwControl, DWORD dwEventType, unsigned int *lpEventData, LPVOID lpContext)
{
  unsigned int v7; // edi
  DWORD v8; // ebx
  DWORD v9; // ebx
  DWORD v10; // ebx
  __int64 i; // rbx
  void (__fastcall *v12)(_QWORD, _QWORD, unsigned int *, LPVOID); // rax
  int v13; // eax
  int v14; // edx
  bool v15; // cf
  int v17; // [rsp+28h] [rbp-30h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids);
  _m_prefetchw((const void *)&g_ServiceControlFlags);
  if ( (_InterlockedOr(&g_ServiceControlFlags, 2u) & 1) != 0 )
  {
    v7 = 1115;
  }
  else
  {
    v7 = 0;
    v8 = dwControl - 1;
    if ( !v8 )
      goto LABEL_17;
    v9 = v8 - 3;
    if ( !v9 )
      goto LABEL_29;
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 == 9 )
      {
        if ( !g_bStopPending )
        {
          for ( i = 0; i != 2; ++i )
          {
            v12 = (void (__fastcall *)(_QWORD, _QWORD, unsigned int *, LPVOID))qword_180007028[7 * i];
            if ( v12 )
              v12(lpEventData[1], dwEventType, lpEventData, lpContext);
          }
        }
      }
      else
      {
        v7 = 120;
      }
    }
    else
    {
LABEL_17:
      g_bStopPending = 1;
      ServiceStatus.dwCurrentState = 3;
      SetServiceStatus(hServiceStatus, &ServiceStatus);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 26);
      v13 = CoRegisterServerShutdownDelay(0, 0);
      v14 = 0;
      if ( v13 )
        v15 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
      else
        v15 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        LOBYTE(v14) = !v15;
        if ( v14 )
        {
          v17 = v13;
          WPP_SF_sqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27);
        }
      }
      EnterCriticalSection(&g_hServiceStopEventLock);
      if ( g_hServiceStopEvent )
        SetEvent(g_hServiceStopEvent);
      LeaveCriticalSection(&g_hServiceStopEventLock);
    }
  }
LABEL_29:
  _InterlockedAnd(&g_ServiceControlFlags, 0xFFFFFFFD);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_sP(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, lpEventData, lpContext, v7, v17);
  return v7;
}

```

## disassembly

```asm
0x180002020  push    rbx
0x180002022  push    rbp
0x180002023  push    rsi
0x180002024  push    rdi
0x180002025  push    r15
0x180002027  sub     rsp, 30h
0x18000202b  mov     rsi, r8
0x18000202e  mov     ebp, edx
0x180002030  mov     ebx, ecx
0x180002032  mov     rcx, cs:WPP_GLOBAL_Control
0x180002039  lea     r15, WPP_GLOBAL_Control
0x180002040  cmp     rcx, r15
0x180002043  jz      short loc_180002060
0x180002045  cmp     byte ptr [rcx+19h], 4
0x180002049  jb      short loc_180002060
0x18000204b  mov     rcx, [rcx+10h]
0x18000204f  lea     r8, WPP_fe2b77c2a50e30d09de66304557b9354_Traceguids
0x180002056  mov     edx, 14h
0x18000205b  call    WPP_SF_s
0x180002060  prefetchw byte ptr cs:?g_ServiceControlFlags@@3JC; long volatile g_ServiceControlFlags
0x180002067  mov     eax, cs:?g_ServiceControlFlags@@3JC; long volatile g_ServiceControlFlags
0x18000206d  mov     ecx, eax
0x18000206f  or      ecx, 2
0x180002072  lock cmpxchg cs:?g_ServiceControlFlags@@3JC, ecx; long volatile g_ServiceControlFlags
0x18000207a  jnz     short loc_18000206D
0x18000207c  test    al, 1
0x18000207e  jz      short loc_18000208A
0x180002080  mov     edi, 45Bh
0x180002085  jmp     loc_1800021AC
0x18000208a  xor     edi, edi
0x18000208c  sub     ebx, 1
0x18000208f  jz      short loc_1800020E8
0x180002091  sub     ebx, 3
0x180002094  jz      loc_1800021AC
0x18000209a  sub     ebx, 1
0x18000209d  jz      short loc_1800020E8
0x18000209f  cmp     ebx, 9
0x1800020a2  jz      short loc_1800020AE
0x1800020a4  mov     edi, 78h ; 'x'
0x1800020a9  jmp     loc_1800021AC
0x1800020ae  cmp     cs:?g_bStopPending@@3HA, edi; int g_bStopPending
0x1800020b4  jnz     loc_1800021AC
0x1800020ba  xor     ebx, ebx
0x1800020bc  imul    rax, rbx, 38h ; '8'
0x1800020c0  lea     rcx, qword_180007028
0x1800020c7  mov     rax, [rax+rcx]
0x1800020cb  test    rax, rax
0x1800020ce  jz      short loc_1800020DA
0x1800020d0  mov     ecx, [rsi+4]
0x1800020d3  mov     edx, ebp
0x1800020d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020da  inc     rbx
0x1800020dd  cmp     rbx, 2
0x1800020e1  jnz     short loc_1800020BC
0x1800020e3  jmp     loc_1800021AC
0x1800020e8  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800020ef  lea     rdx, ServiceStatus; lpServiceStatus
0x1800020f6  mov     cs:?g_bStopPending@@3HA, 1; int g_bStopPending
0x180002100  mov     cs:ServiceStatus.dwCurrentState, 3
0x18000210a  call    cs:__imp_SetServiceStatus
0x180002110  mov     rbx, cs:?g_pSharedService@@3PEAVCFdphostSharedService@@EA; CFdphostSharedService * g_pSharedService
0x180002117  mov     rcx, cs:WPP_GLOBAL_Control
0x18000211e  cmp     rcx, r15
0x180002121  jz      short loc_18000213C
0x180002123  cmp     byte ptr [rcx+19h], 4
0x180002127  jb      short loc_18000213C
0x180002129  mov     rcx, [rcx+10h]
0x18000212d  mov     edx, 1Ah
0x180002132  mov     [rsp+58h+var_38], rbx
0x180002137  call    WPP_SF_sq
0x18000213c  xor     edx, edx
0x18000213e  xor     ecx, ecx
0x180002140  call    cs:__imp_CoRegisterServerShutdownDelay
0x180002146  mov     rcx, cs:WPP_GLOBAL_Control
0x18000214d  xor     edx, edx
0x18000214f  test    eax, eax
0x180002151  jnz     short loc_180002159
0x180002153  cmp     byte ptr [rcx+19h], 4
0x180002157  jmp     short loc_18000215D
0x180002159  cmp     byte ptr [rcx+19h], 2
0x18000215d  setnb   dl
0x180002160  cmp     rcx, r15
0x180002163  jz      short loc_180002180
0x180002165  test    edx, edx
0x180002167  jz      short loc_180002180
0x180002169  mov     rcx, [rcx+10h]
0x18000216d  mov     edx, 1Bh
0x180002172  mov     [rsp+58h+var_30], eax
0x180002176  mov     [rsp+58h+var_38], rbx
0x18000217b  call    WPP_SF_sqd
0x180002180  lea     rcx, ?g_hServiceStopEventLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002187  call    cs:__imp_EnterCriticalSection
0x18000218d  mov     rcx, cs:?g_hServiceStopEvent@@3PEAXEA; hEvent
0x180002194  test    rcx, rcx
0x180002197  jz      short loc_18000219F
0x180002199  call    cs:__imp_SetEvent
0x18000219f  lea     rcx, ?g_hServiceStopEventLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800021a6  call    cs:__imp_LeaveCriticalSection
0x1800021ac  lock and cs:?g_ServiceControlFlags@@3JC, 0FFFFFFFDh; long volatile g_ServiceControlFlags
0x1800021b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800021bb  cmp     rcx, r15
0x1800021be  jz      short loc_1800021D6
0x1800021c0  cmp     byte ptr [rcx+19h], 4
0x1800021c4  jb      short loc_1800021D6
0x1800021c6  mov     rcx, [rcx+10h]
0x1800021ca  mov     edx, edi
0x1800021cc  mov     [rsp+58h+var_38], rdx
0x1800021d1  call    WPP_SF_sP
0x1800021d6  mov     eax, edi
0x1800021d8  add     rsp, 30h
0x1800021dc  pop     r15
0x1800021de  pop     rdi
0x1800021df  pop     rsi
0x1800021e0  pop     rbp
0x1800021e1  pop     rbx
0x1800021e2  retn
```
