# RdpWinTaskScheduler::QueueTimedTask(RdpXInterfaceTask *,uint)

- ea: `0x140109410`
- end: `0x140109576`
- name: `?QueueTimedTask@RdpWinTaskScheduler@@UEAA?AW4_XResult32@@PEAURdpXInterfaceTask@@I@Z`
- size: `358`
- prototype: `enum _XResult32 __high(struct RdpXInterfaceTask *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x14000cfb0`
- `0x14001e158`
- `0x140108fc8`
- `0x140109410`
- `0x140109b08`
- `0x140114010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x1401094c6`
- `KERNEL32!CreateThreadpoolTimer` at `0x1401094c6`
- `KERNEL32!SetThreadpoolTimer` at `0x14010955b`
- `KERNEL32!SetThreadpoolTimer` at `0x14010955b`
- `KERNEL32!GetLastError` at `0x1401094f3`
- `KERNEL32!GetLastError` at `0x1401094f3`

## pseudocode

```c
__int64 __fastcall RdpWinTaskScheduler::QueueTimedTask(__int64 a1, void (__fastcall ***a2)(void *), unsigned int a3)
{
  void (__fastcall **v3)(void *); // rax
  __int64 *v4; // rbx
  __int64 v6; // rbp
  __int64 v8; // rax
  unsigned int v9; // ebx
  __int64 v10; // r8
  unsigned int ActivityIdPrefix; // eax
  struct _TP_TIMER *ThreadpoolTimer; // r10
  DWORD LastError; // ebx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned int v17; // eax
  __int64 v19; // [rsp+30h] [rbp-38h] BYREF
  int v20; // [rsp+38h] [rbp-30h]
  struct _FILETIME pftDueTime; // [rsp+70h] [rbp+8h] BYREF

  v3 = *a2;
  v4 = (__int64 *)(a1 + 16);
  v6 = a3;
  v19 = a1 + 16;
  pftDueTime = 0;
  (*v3)(a2);
  v8 = *v4;
  v20 = 1;
  v9 = (*(__int64 (__fastcall **)(__int64 *))(v8 + 8))(v4);
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(&WPP_GLOBAL_Control, WPP_GLOBAL_Control, v10);
      WPP_SF_DLD(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        17,
        WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids,
        ActivityIdPrefix,
        v9,
        v9);
    }
  }
  else
  {
    ThreadpoolTimer = CreateThreadpoolTimer(
                        RdpWinTaskScheduler::staticTimerCallback,
                        a2,
                        (PTP_CALLBACK_ENVIRON)(a1 + 56));
    if ( ThreadpoolTimer )
    {
      pftDueTime = (struct _FILETIME)(-10000 * v6);
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
      goto LABEL_14;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
    {
      LastError = GetLastError();
      v17 = RdpX_GetActivityIdPrefix(v15, v14, v16);
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        18,
        WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids,
        v17,
        LastError);
    }
    v9 = -1;
  }
  (*a2)[1](a2);
LABEL_14:
  RdpXSafeRundownAutoDispatch::~RdpXSafeRundownAutoDispatch((RdpXSafeRundownAutoDispatch *)&v19);
  return v9;
}

```

## disassembly

```asm
0x140109410  push    rbx
0x140109412  push    rbp
0x140109413  push    rsi
0x140109414  push    rdi
0x140109415  sub     rsp, 48h
0x140109419  mov     rax, [rdx]
0x14010941c  lea     rbx, [rcx+10h]
0x140109420  mov     rsi, rcx
0x140109423  mov     ebp, r8d
0x140109426  mov     rcx, rdx
0x140109429  mov     [rsp+68h+var_38], rbx
0x14010942e  mov     rdi, rdx
0x140109431  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0
0x14010943a  mov     rax, [rax]
0x14010943d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140109442  mov     rax, [rbx]
0x140109445  mov     rcx, rbx
0x140109448  mov     [rsp+68h+var_30], 1
0x140109450  mov     rax, [rax+8]
0x140109454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140109459  mov     ebx, eax
0x14010945b  test    eax, eax
0x14010945d  jz      short loc_1401094B8
0x14010945f  mov     rdx, cs:WPP_GLOBAL_Control
0x140109466  lea     rcx, WPP_GLOBAL_Control
0x14010946d  cmp     rdx, rcx
0x140109470  jz      loc_140109526
0x140109476  test    byte ptr [rdx+44h], 10h
0x14010947a  jz      loc_140109526
0x140109480  cmp     byte ptr [rdx+41h], 2
0x140109484  jb      loc_140109526
0x14010948a  call    RdpX_GetActivityIdPrefix
0x14010948f  mov     rcx, cs:WPP_GLOBAL_Control
0x140109496  lea     r8, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids
0x14010949d  mov     edx, 11h
0x1401094a2  mov     [rsp+68h+var_40], ebx
0x1401094a6  mov     r9d, eax
0x1401094a9  mov     [rsp+68h+var_48], ebx
0x1401094ad  mov     rcx, [rcx+38h]
0x1401094b1  call    WPP_SF_DLD
0x1401094b6  jmp     short loc_140109526
0x1401094b8  lea     r8, [rsi+38h]; pcbe
0x1401094bc  mov     rdx, rdi; pv
0x1401094bf  lea     rcx, ?staticTimerCallback@RdpWinTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1401094c6  call    cs:__imp_CreateThreadpoolTimer
0x1401094cc  mov     r10, rax
0x1401094cf  test    rax, rax
0x1401094d2  jnz     short loc_140109537
0x1401094d4  mov     rax, cs:WPP_GLOBAL_Control
0x1401094db  lea     rcx, WPP_GLOBAL_Control
0x1401094e2  cmp     rax, rcx
0x1401094e5  jz      short loc_140109523
0x1401094e7  test    byte ptr [rax+44h], 10h
0x1401094eb  jz      short loc_140109523
0x1401094ed  cmp     byte ptr [rax+41h], 2
0x1401094f1  jb      short loc_140109523
0x1401094f3  call    cs:__imp_GetLastError
0x1401094f9  mov     ebx, eax
0x1401094fb  call    RdpX_GetActivityIdPrefix
0x140109500  mov     rcx, cs:WPP_GLOBAL_Control
0x140109507  lea     r8, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids
0x14010950e  mov     edx, 12h
0x140109513  mov     [rsp+68h+var_48], ebx
0x140109517  mov     r9d, eax
0x14010951a  mov     rcx, [rcx+38h]
0x14010951e  call    WPP_SF_Dd
0x140109523  or      ebx, 0FFFFFFFFh
0x140109526  mov     rax, [rdi]
0x140109529  mov     rcx, rdi
0x14010952c  mov     rax, [rax+8]
0x140109530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140109535  jmp     short loc_140109561
0x140109537  imul    rax, rbp, 0FFFFFFFFFFFFD8F0h
0x14010953e  xor     r9d, r9d; msWindowLength
0x140109541  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x140109546  mov     rcx, rax
0x140109549  mov     [rsp+68h+pftDueTime.dwLowDateTime], eax
0x14010954d  shr     rcx, 20h
0x140109551  xor     r8d, r8d; msPeriod
0x140109554  mov     [rsp+68h+pftDueTime.dwHighDateTime], ecx
0x140109558  mov     rcx, r10; pti
0x14010955b  call    cs:__imp_SetThreadpoolTimer
0x140109561  lea     rcx, [rsp+68h+var_38]; this
0x140109566  call    ??1RdpXSafeRundownAutoDispatch@@QEAA@XZ; RdpXSafeRundownAutoDispatch::~RdpXSafeRundownAutoDispatch(void)
0x14010956b  mov     eax, ebx
0x14010956d  add     rsp, 48h
0x140109571  pop     rdi
0x140109572  pop     rsi
0x140109573  pop     rbp
0x140109574  pop     rbx
0x140109575  retn
```
