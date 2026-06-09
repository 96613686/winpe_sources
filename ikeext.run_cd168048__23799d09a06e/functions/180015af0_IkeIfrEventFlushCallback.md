# IkeIfrEventFlushCallback

- ea: `0x180015af0`
- end: `0x180015c63`
- name: `IkeIfrEventFlushCallback`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x1800061ec`
- `0x180010db0`
- `0x180015af0`
- `0x180015c70`
- `0x180016300`
- `0x1800488f0`
- `0x18004890c`
- `0x18005bc40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b83`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015bf4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015b36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180015bf4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015b2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015be4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015b2a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015be4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015b75`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015b75`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015bdb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015bdb`

## string_xrefs

- `0x180015b8f`: `CreateThreadpoolTimer`

## pseudocode

```c
void IkeIfrEventFlushCallback()
{
  LPCRITICAL_SECTION v0; // rdi
  __int64 p_LockSemaphore; // rdi
  struct _RTL_CRITICAL_SECTION *v2; // rbp
  __int64 v3; // rsi
  int v4; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  DWORD LastError; // eax
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  int TlsMmLuid; // eax
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+18h] BYREF

  v0 = gIkeExtGlobals;
  IkeIfrFlushPendingEvents(0);
  p_LockSemaphore = (__int64)&v0[98].LockSemaphore;
  v2 = gIkeExtGlobals + 67;
  pftDueTime = 0;
  v3 = 0;
  EnterCriticalSection(gIkeExtGlobals + 67);
  v4 = *(_DWORD *)(p_LockSemaphore + 24);
  LeaveCriticalSection(v2);
  if ( v4 == 1 )
  {
    v3 = WfpStopTimer(v2, p_LockSemaphore);
    if ( v3 )
      goto LABEL_7;
  }
  *(_OWORD *)p_LockSemaphore = 0;
  *(_OWORD *)(p_LockSemaphore + 16) = 0;
  *(_QWORD *)(p_LockSemaphore + 32) = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(WfpUserModeTimerInternalCallback, (PVOID)p_LockSemaphore, 0);
  *(_QWORD *)p_LockSemaphore = ThreadpoolTimer;
  if ( ThreadpoolTimer )
  {
    *(_QWORD *)(p_LockSemaphore + 16) = 0;
    *(_QWORD *)(p_LockSemaphore + 8) = IkeIfrEventFlushCallback;
    *(_QWORD *)(p_LockSemaphore + 32) = v2;
    pftDueTime.dwHighDateTime = -2;
    pftDueTime.dwLowDateTime = -1405032704;
    SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0x7530u);
    EnterCriticalSection(v2);
    *(_DWORD *)(p_LockSemaphore + 24) = 1;
    LeaveCriticalSection(v2);
  }
  else
  {
    LastError = GetLastError();
    v3 = WfpReportSysErrorAsWinError(v7, "CreateThreadpoolTimer", LastError, 1);
  }
  if ( v3 )
  {
LABEL_7:
    WfpReportError(v3, "WfpStartTimer");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v9 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v8);
      TlsMmLuid = IkeGetTlsMmLuid(v12, v11, v13, v14);
      WPP_SF_iS(v9, 26, (unsigned int)WPP_0162bb2a8b4239af156c6f597e3eee45_Traceguids, TlsMmLuid, TlsPeerAddr);
    }
  }
}

```

## disassembly

```asm
0x180015af0  push    rbx
0x180015af2  push    rbp
0x180015af3  push    rsi
0x180015af4  push    rdi
0x180015af5  sub     rsp, 38h
0x180015af9  mov     rdi, cs:gIkeExtGlobals
0x180015b00  xor     ecx, ecx
0x180015b02  call    IkeIfrFlushPendingEvents
0x180015b07  mov     rbp, cs:gIkeExtGlobals
0x180015b0e  add     rdi, 0F68h
0x180015b15  add     rbp, 0A78h
0x180015b1c  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], 0
0x180015b25  mov     rcx, rbp; lpCriticalSection
0x180015b28  xor     esi, esi
0x180015b2a  call    cs:__imp_EnterCriticalSection
0x180015b30  mov     ebx, [rdi+18h]
0x180015b33  mov     rcx, rbp; lpCriticalSection
0x180015b36  call    cs:__imp_LeaveCriticalSection
0x180015b3c  cmp     ebx, 1
0x180015b3f  jnz     short loc_180015B58
0x180015b41  mov     rdx, rdi
0x180015b44  mov     rcx, rbp; lpCriticalSection
0x180015b47  call    WfpStopTimer
0x180015b4c  mov     rsi, rax
0x180015b4f  test    rax, rax
0x180015b52  jnz     loc_180015BFF
0x180015b58  xorps   xmm0, xmm0
0x180015b5b  lea     rcx, WfpUserModeTimerInternalCallback; pfnti
0x180015b62  movups  xmmword ptr [rdi], xmm0
0x180015b65  xor     eax, eax
0x180015b67  xor     r8d, r8d; pcbe
0x180015b6a  movups  xmmword ptr [rdi+10h], xmm0
0x180015b6e  mov     rdx, rdi; pv
0x180015b71  mov     [rdi+20h], rax
0x180015b75  call    cs:__imp_CreateThreadpoolTimer
0x180015b7b  mov     [rdi], rax
0x180015b7e  test    rax, rax
0x180015b81  jnz     short loc_180015BA3
0x180015b83  call    cs:__imp_GetLastError
0x180015b89  mov     r9d, 1
0x180015b8f  lea     rdx, aCreatethreadpo_0; "CreateThreadpoolTimer"
0x180015b96  mov     r8d, eax
0x180015b99  call    WfpReportSysErrorAsWinError
0x180015b9e  mov     rsi, rax
0x180015ba1  jmp     short loc_180015BFA
0x180015ba3  lea     rcx, IkeIfrEventFlushCallback
0x180015baa  mov     qword ptr [rdi+10h], 0
0x180015bb2  mov     [rdi+8], rcx
0x180015bb6  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x180015bbb  mov     rcx, rax; pti
0x180015bbe  mov     [rdi+20h], rbp
0x180015bc2  mov     r9d, 7530h; msWindowLength
0x180015bc8  mov     [rsp+58h+pftDueTime.dwHighDateTime], 0FFFFFFFEh
0x180015bd0  xor     r8d, r8d; msPeriod
0x180015bd3  mov     [rsp+58h+pftDueTime.dwLowDateTime], 0AC40E700h
0x180015bdb  call    cs:__imp_SetThreadpoolTimer
0x180015be1  mov     rcx, rbp; lpCriticalSection
0x180015be4  call    cs:__imp_EnterCriticalSection
0x180015bea  mov     rcx, rbp; lpCriticalSection
0x180015bed  mov     dword ptr [rdi+18h], 1
0x180015bf4  call    cs:__imp_LeaveCriticalSection
0x180015bfa  test    rsi, rsi
0x180015bfd  jz      short loc_180015C5A
0x180015bff  lea     rdx, aWfpstarttimer; "WfpStartTimer"
0x180015c06  mov     rcx, rsi
0x180015c09  call    WfpReportError
0x180015c0e  mov     rdi, cs:WPP_GLOBAL_Control
0x180015c15  lea     rax, WPP_GLOBAL_Control
0x180015c1c  cmp     rdi, rax
0x180015c1f  jz      short loc_180015C5A
0x180015c21  cmp     byte ptr [rdi+19h], 2
0x180015c25  jb      short loc_180015C5A
0x180015c27  test    byte ptr [rdi+1Ch], 10h
0x180015c2b  jz      short loc_180015C5A
0x180015c2d  mov     rdi, [rdi+10h]
0x180015c31  call    IkeGetTlsPeerAddr
0x180015c36  mov     rbx, rax
0x180015c39  call    IkeGetTlsMmLuid
0x180015c3e  mov     r9, rax
0x180015c41  mov     [rsp+58h+var_38], rbx
0x180015c46  mov     edx, 1Ah
0x180015c4b  lea     r8, WPP_0162bb2a8b4239af156c6f597e3eee45_Traceguids
0x180015c52  mov     rcx, rdi
0x180015c55  call    WPP_SF_iS
0x180015c5a  add     rsp, 38h
0x180015c5e  pop     rdi
0x180015c5f  pop     rsi
0x180015c60  pop     rbp
0x180015c61  pop     rbx
0x180015c62  retn
```
