# CServiceTaskManager::_QueueTaskForDelayedExecution(TASK_DESCRIPTOR *)

- ea: `0x18002eec8`
- end: `0x18002f06f`
- name: `?_QueueTaskForDelayedExecution@CServiceTaskManager@@AEAAJPEAUTASK_DESCRIPTOR@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(CServiceTaskManager *__hidden this, struct TASK_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bf4c`

## callees

- `0x18002eec8`
- `0x18002f10c`
- `0x18003c560`
- `0x180069454`
- `0x180069530`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f04e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002f04e`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18002efe2`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18002efe2`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18002eee9`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18002eee9`

## pseudocode

```c
__int64 __fastcall CServiceTaskManager::_QueueTaskForDelayedExecution(
        CServiceTaskManager *this,
        struct TASK_DESCRIPTOR *a2)
{
  HANDLE WaitableTimerW; // rax
  unsigned int Error; // edi
  __int64 v5; // rcx
  CObjectMonitor *v6; // r11
  const wchar_t *v7; // r9
  __int64 v8; // rax
  __int64 v9; // r11
  __int64 v10; // r10
  __int64 v11; // r8
  LONG v12; // r8d
  void *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // r11
  __int64 v16; // r10
  __int64 v17; // r8
  void *v18; // rcx
  void *lpArgToCompletionRoutine; // [rsp+20h] [rbp-28h]
  int fResume; // [rsp+28h] [rbp-20h]
  LARGE_INTEGER DueTime; // [rsp+50h] [rbp+8h] BYREF

  DueTime.QuadPart = (LONGLONG)this;
  WaitableTimerW = CreateWaitableTimerW(0, 1, 0);
  *((_QWORD *)a2 + 6) = WaitableTimerW;
  if ( WaitableTimerW )
  {
    v5 = *((unsigned int *)a2 + 3);
    Error = 0;
    DueTime.QuadPart = -10000 * v5;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      {
        fResume = *((_DWORD *)a2 + 6);
        v7 = L"is";
        if ( !fResume )
          v7 = L"is not";
        WPP_SF_SdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_088402f2fc59396373c04b0fd13246f5_Traceguids,
          (_DWORD)v7,
          v5,
          fResume);
        v6 = WPP_GLOBAL_Control;
      }
      if ( v6 != (CObjectMonitor *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x400000) != 0 )
      {
        Tasks_TaskStateText(1);
        v8 = Tasks_TaskStateText(*((unsigned int *)a2 + 2));
        WPP_SF_SdSS(*(_QWORD *)(v9 + 16), 17, v11, v10 + 20, *(_DWORD *)(v10 + 16), v8, v11);
      }
    }
    v12 = *((_DWORD *)a2 + 6);
    v13 = (void *)*((_QWORD *)a2 + 6);
    lpArgToCompletionRoutine = (void *)*((unsigned int *)a2 + 1);
    *((_DWORD *)a2 + 2) = 1;
    if ( !SetWaitableTimer(
            v13,
            &DueTime,
            v12,
            CServiceTaskManager::_DelayedTaskTimerApcProc,
            lpArgToCompletionRoutine,
            0) )
    {
      Error = ResultFromLastError();
      if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      {
        Tasks_TaskStateText(0);
        v14 = Tasks_TaskStateText(*((unsigned int *)a2 + 2));
        WPP_SF_SdSS(*(_QWORD *)(v15 + 16), 18, v17, v16 + 20, *(_DWORD *)(v16 + 16), v14, v17);
      }
      v18 = (void *)*((_QWORD *)a2 + 6);
      *((_DWORD *)a2 + 2) = 0;
      CloseHandle(v18);
      *((_QWORD *)a2 + 6) = 0;
    }
  }
  else
  {
    return (unsigned int)ResultFromLastError();
  }
  return Error;
}

```

## disassembly

```asm
0x18002eec8  mov     [rsp+arg_8], rbx
0x18002eecd  mov     [rsp+arg_10], rdi
0x18002eed2  mov     qword ptr [rsp+DueTime], rcx
0x18002eed7  push    r14
0x18002eed9  sub     rsp, 40h
0x18002eedd  xor     r8d, r8d; lpTimerName
0x18002eee0  mov     rbx, rdx
0x18002eee3  xor     ecx, ecx; lpTimerAttributes
0x18002eee5  lea     edx, [r8+1]; bManualReset
0x18002eee9  call    cs:__imp_CreateWaitableTimerW
0x18002eeef  mov     [rbx+30h], rax
0x18002eef3  test    rax, rax
0x18002eef6  jnz     short loc_18002EF04
0x18002eef8  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002eefd  mov     edi, eax
0x18002eeff  jmp     loc_18002F05C
0x18002ef04  mov     ecx, [rbx+0Ch]
0x18002ef07  xor     edi, edi
0x18002ef09  imul    rax, rcx, 0FFFFFFFFFFFFD8F0h
0x18002ef10  mov     qword ptr [rsp+48h+DueTime], rax
0x18002ef15  mov     r11, cs:WPP_GLOBAL_Control
0x18002ef1c  lea     r14, WPP_GLOBAL_Control
0x18002ef23  cmp     r11, r14
0x18002ef26  jz      loc_18002EFBB
0x18002ef2c  test    dword ptr [r11+1Ch], 400000h
0x18002ef34  jz      short loc_18002EF6F
0x18002ef36  mov     eax, [rbx+18h]
0x18002ef39  lea     rdx, aIsNot; "is not"
0x18002ef40  test    eax, eax
0x18002ef42  mov     [rsp+48h+fResume], eax
0x18002ef46  mov     dword ptr [rsp+48h+lpArgToCompletionRoutine], ecx
0x18002ef4a  lea     r9, aIs; "is"
0x18002ef51  mov     rcx, [r11+10h]
0x18002ef55  lea     r8, WPP_088402f2fc59396373c04b0fd13246f5_Traceguids
0x18002ef5c  cmovz   r9, rdx
0x18002ef60  lea     edx, [rdi+10h]
0x18002ef63  call    WPP_SF_SdD
0x18002ef68  mov     r11, cs:WPP_GLOBAL_Control
0x18002ef6f  cmp     r11, r14
0x18002ef72  jz      short loc_18002EFBB
0x18002ef74  test    dword ptr [r11+1Ch], 400000h
0x18002ef7c  jz      short loc_18002EFBB
0x18002ef7e  mov     r10, [rbx+38h]
0x18002ef82  mov     ecx, 1
0x18002ef87  call    Tasks_TaskStateText
0x18002ef8c  mov     ecx, [rbx+8]
0x18002ef8f  mov     r8, rax
0x18002ef92  call    Tasks_TaskStateText
0x18002ef97  mov     rcx, [r11+10h]
0x18002ef9b  lea     r9, [r10+14h]
0x18002ef9f  mov     [rsp+48h+var_18], r8
0x18002efa4  mov     edx, 11h
0x18002efa9  mov     qword ptr [rsp+48h+fResume], rax
0x18002efae  mov     eax, [r10+10h]
0x18002efb2  mov     dword ptr [rsp+48h+lpArgToCompletionRoutine], eax
0x18002efb6  call    WPP_SF_SdSS
0x18002efbb  mov     eax, [rbx+4]
0x18002efbe  lea     r9, ?_DelayedTaskTimerApcProc@CServiceTaskManager@@CAXPEAXKK@Z; pfnCompletionRoutine
0x18002efc5  mov     r8d, [rbx+18h]; lPeriod
0x18002efc9  lea     rdx, [rsp+48h+DueTime]; lpDueTime
0x18002efce  mov     rcx, [rbx+30h]; hTimer
0x18002efd2  mov     [rsp+48h+fResume], edi; fResume
0x18002efd6  mov     [rsp+48h+lpArgToCompletionRoutine], rax; lpArgToCompletionRoutine
0x18002efdb  mov     dword ptr [rbx+8], 1
0x18002efe2  call    cs:__imp_SetWaitableTimer
0x18002efe8  test    eax, eax
0x18002efea  jnz     short loc_18002F05C
0x18002efec  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002eff1  mov     edi, eax
0x18002eff3  mov     r11, cs:WPP_GLOBAL_Control
0x18002effa  cmp     r11, r14
0x18002effd  jz      short loc_18002F043
0x18002efff  test    dword ptr [r11+1Ch], 400000h
0x18002f007  jz      short loc_18002F043
0x18002f009  mov     r10, [rbx+38h]
0x18002f00d  xor     ecx, ecx
0x18002f00f  call    Tasks_TaskStateText
0x18002f014  mov     ecx, [rbx+8]
0x18002f017  mov     r8, rax
0x18002f01a  call    Tasks_TaskStateText
0x18002f01f  mov     rcx, [r11+10h]
0x18002f023  lea     r9, [r10+14h]
0x18002f027  mov     [rsp+48h+var_18], r8
0x18002f02c  mov     edx, 12h
0x18002f031  mov     qword ptr [rsp+48h+fResume], rax
0x18002f036  mov     eax, [r10+10h]
0x18002f03a  mov     dword ptr [rsp+48h+lpArgToCompletionRoutine], eax
0x18002f03e  call    WPP_SF_SdSS
0x18002f043  mov     rcx, [rbx+30h]; hObject
0x18002f047  mov     dword ptr [rbx+8], 0
0x18002f04e  call    cs:__imp_CloseHandle
0x18002f054  mov     qword ptr [rbx+30h], 0
0x18002f05c  mov     rbx, [rsp+48h+arg_8]
0x18002f061  mov     eax, edi
0x18002f063  mov     rdi, [rsp+48h+arg_10]
0x18002f068  add     rsp, 40h
0x18002f06c  pop     r14
0x18002f06e  retn
```
