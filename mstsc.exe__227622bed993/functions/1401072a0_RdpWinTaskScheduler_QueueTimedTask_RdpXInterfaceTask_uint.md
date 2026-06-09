# RdpWinTaskScheduler::QueueTimedTask(RdpXInterfaceTask *,uint)

- ea: `0x1401072a0`
- end: `0x140107406`
- name: `?QueueTimedTask@RdpWinTaskScheduler@@UEAA?AW4_XResult32@@PEAURdpXInterfaceTask@@I@Z`
- size: `358`
- prototype: `enum _XResult32 __high(struct RdpXInterfaceTask *, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update`

## callees

- `0x14000cfb0`
- `0x14001e158`
- `0x140106e58`
- `0x1401072a0`
- `0x140107998`
- `0x140112010`

## import_xrefs

- `KERNEL32!CreateThreadpoolTimer` at `0x140107356`
- `KERNEL32!CreateThreadpoolTimer` at `0x140107356`
- `KERNEL32!SetThreadpoolTimer` at `0x1401073eb`
- `KERNEL32!SetThreadpoolTimer` at `0x1401073eb`
- `KERNEL32!GetLastError` at `0x140107383`
- `KERNEL32!GetLastError` at `0x140107383`

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
0x1401072a0  push    rbx
0x1401072a2  push    rbp
0x1401072a3  push    rsi
0x1401072a4  push    rdi
0x1401072a5  sub     rsp, 48h
0x1401072a9  mov     rax, [rdx]
0x1401072ac  lea     rbx, [rcx+10h]
0x1401072b0  mov     rsi, rcx
0x1401072b3  mov     ebp, r8d
0x1401072b6  mov     rcx, rdx
0x1401072b9  mov     [rsp+68h+var_38], rbx
0x1401072be  mov     rdi, rdx
0x1401072c1  mov     qword ptr [rsp+68h+pftDueTime.dwLowDateTime], 0
0x1401072ca  mov     rax, [rax]
0x1401072cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401072d2  mov     rax, [rbx]
0x1401072d5  mov     rcx, rbx
0x1401072d8  mov     [rsp+68h+var_30], 1
0x1401072e0  mov     rax, [rax+8]
0x1401072e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401072e9  mov     ebx, eax
0x1401072eb  test    eax, eax
0x1401072ed  jz      short loc_140107348
0x1401072ef  mov     rdx, cs:WPP_GLOBAL_Control
0x1401072f6  lea     rcx, WPP_GLOBAL_Control
0x1401072fd  cmp     rdx, rcx
0x140107300  jz      loc_1401073B6
0x140107306  test    byte ptr [rdx+44h], 10h
0x14010730a  jz      loc_1401073B6
0x140107310  cmp     byte ptr [rdx+41h], 2
0x140107314  jb      loc_1401073B6
0x14010731a  call    RdpX_GetActivityIdPrefix
0x14010731f  mov     rcx, cs:WPP_GLOBAL_Control
0x140107326  lea     r8, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids
0x14010732d  mov     edx, 11h
0x140107332  mov     [rsp+68h+var_40], ebx
0x140107336  mov     r9d, eax
0x140107339  mov     [rsp+68h+var_48], ebx
0x14010733d  mov     rcx, [rcx+38h]
0x140107341  call    WPP_SF_DLD
0x140107346  jmp     short loc_1401073B6
0x140107348  lea     r8, [rsi+38h]; pcbe
0x14010734c  mov     rdx, rdi; pv
0x14010734f  lea     rcx, ?staticTimerCallback@RdpWinTaskScheduler@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140107356  call    cs:__imp_CreateThreadpoolTimer
0x14010735c  mov     r10, rax
0x14010735f  test    rax, rax
0x140107362  jnz     short loc_1401073C7
0x140107364  mov     rax, cs:WPP_GLOBAL_Control
0x14010736b  lea     rcx, WPP_GLOBAL_Control
0x140107372  cmp     rax, rcx
0x140107375  jz      short loc_1401073B3
0x140107377  test    byte ptr [rax+44h], 10h
0x14010737b  jz      short loc_1401073B3
0x14010737d  cmp     byte ptr [rax+41h], 2
0x140107381  jb      short loc_1401073B3
0x140107383  call    cs:__imp_GetLastError
0x140107389  mov     ebx, eax
0x14010738b  call    RdpX_GetActivityIdPrefix
0x140107390  mov     rcx, cs:WPP_GLOBAL_Control
0x140107397  lea     r8, WPP_b4e1f14ccf7b3fb7b79d85e9eb249ee3_Traceguids
0x14010739e  mov     edx, 12h
0x1401073a3  mov     [rsp+68h+var_48], ebx
0x1401073a7  mov     r9d, eax
0x1401073aa  mov     rcx, [rcx+38h]
0x1401073ae  call    WPP_SF_Dd
0x1401073b3  or      ebx, 0FFFFFFFFh
0x1401073b6  mov     rax, [rdi]
0x1401073b9  mov     rcx, rdi
0x1401073bc  mov     rax, [rax+8]
0x1401073c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401073c5  jmp     short loc_1401073F1
0x1401073c7  imul    rax, rbp, 0FFFFFFFFFFFFD8F0h
0x1401073ce  xor     r9d, r9d; msWindowLength
0x1401073d1  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x1401073d6  mov     rcx, rax
0x1401073d9  mov     [rsp+68h+pftDueTime.dwLowDateTime], eax
0x1401073dd  shr     rcx, 20h
0x1401073e1  xor     r8d, r8d; msPeriod
0x1401073e4  mov     [rsp+68h+pftDueTime.dwHighDateTime], ecx
0x1401073e8  mov     rcx, r10; pti
0x1401073eb  call    cs:__imp_SetThreadpoolTimer
0x1401073f1  lea     rcx, [rsp+68h+var_38]; this
0x1401073f6  call    ??1RdpXSafeRundownAutoDispatch@@QEAA@XZ; RdpXSafeRundownAutoDispatch::~RdpXSafeRundownAutoDispatch(void)
0x1401073fb  mov     eax, ebx
0x1401073fd  add     rsp, 48h
0x140107401  pop     rdi
0x140107402  pop     rsi
0x140107403  pop     rbp
0x140107404  pop     rbx
0x140107405  retn
```
