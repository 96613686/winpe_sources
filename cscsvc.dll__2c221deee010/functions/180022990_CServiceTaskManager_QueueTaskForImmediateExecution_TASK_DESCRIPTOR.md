# CServiceTaskManager::_QueueTaskForImmediateExecution(TASK_DESCRIPTOR *)

- ea: `0x180022990`
- end: `0x180022c51`
- name: `?_QueueTaskForImmediateExecution@CServiceTaskManager@@CAJPEAUTASK_DESCRIPTOR@@@Z`
- size: `705`
- prototype: `__int64 __fastcall(struct TASK_DESCRIPTOR *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180022930`
- `0x18002bf4c`

## callees

- `0x180022990`
- `0x180029924`
- `0x18002f10c`
- `0x18003c488`
- `0x18003c5ec`
- `0x180069454`
- `0x180069530`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022a2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022a2a`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180022a15`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180022a15`
- `KERNEL32!QueueUserWorkItem` at `0x180022a62`
- `KERNEL32!QueueUserWorkItem` at `0x180022a62`

## pseudocode

```c
__int64 __fastcall CServiceTaskManager::_QueueTaskForImmediateExecution(struct TASK_DESCRIPTOR *a1)
{
  unsigned int v1; // edx
  unsigned int Error; // edi
  HANDLE v4; // rax
  __int64 v6; // rax
  __int64 v7; // r11
  __int64 v8; // r10
  __int64 v9; // r8
  CObjectMonitor *v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // edx
  __int64 v13; // rax
  __int64 v14; // r11
  __int64 v15; // r10
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // r11
  __int64 v19; // r10
  __int64 v20; // r8
  __int64 v21; // rax
  __int64 v22; // r10
  DWORD ThreadId; // [rsp+50h] [rbp+8h] BYREF

  v1 = *((_DWORD *)a1 + 2);
  Error = 0;
  if ( v1 == 6 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
    {
      return Error;
    }
    v11 = 19;
LABEL_19:
    WPP_SF_S(*((_QWORD *)v10 + 2), v11, WPP_088402f2fc59396373c04b0fd13246f5_Traceguids, *((_QWORD *)a1 + 7) + 20LL);
    return Error;
  }
  if ( v1 == 2 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CObjectMonitor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) == 0 )
    {
      return Error;
    }
    v11 = 20;
    goto LABEL_19;
  }
  if ( v1 - 4 <= 1 )
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      v21 = Tasks_TaskStateText(v1);
      WPP_SF_SS(
        *(_QWORD *)(v22 + 16),
        21,
        (unsigned int)WPP_088402f2fc59396373c04b0fd13246f5_Traceguids,
        *((_QWORD *)a1 + 7) + 20,
        v21);
    }
    return (unsigned int)-2147019886;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
    {
      Tasks_TaskStateText(2);
      v13 = Tasks_TaskStateText(v12);
      WPP_SF_SdSS(*(_QWORD *)(v14 + 16), 22, v16, v15 + 20, *(_DWORD *)(v15 + 16), v13, v16);
    }
    *((_DWORD *)a1 + 2) = 2;
    if ( *((_DWORD *)a1 + 4) )
    {
      _InterlockedIncrement((volatile signed __int32 *)a1);
      ThreadId = 0;
      v4 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)CServiceTaskManager::_TaskThreadProc, a1, 0, &ThreadId);
      if ( v4 )
      {
        *((_DWORD *)a1 + 9) = 0;
        CloseHandle(v4);
      }
      else
      {
        Error = ResultFromLastError();
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        {
          Tasks_TaskStateText(3);
          v17 = Tasks_TaskStateText(*((unsigned int *)a1 + 2));
          WPP_SF_SdSS(*(_QWORD *)(v18 + 16), 23, v20, v19 + 20, *(_DWORD *)(v19 + 16), v17, v20);
        }
        *((_DWORD *)a1 + 2) = 3;
        CServiceTaskManager::_ReleaseTaskDescriptor(a1);
      }
    }
    else
    {
      *((_DWORD *)a1 + 9) = 1;
      _InterlockedIncrement((volatile signed __int32 *)a1);
      if ( !QueueUserWorkItem(
              (LPTHREAD_START_ROUTINE)CServiceTaskManager::_TaskThreadProc,
              a1,
              *((_DWORD *)a1 + 8) != 0 ? 0x10 : 0) )
      {
        Error = ResultFromLastError();
        if ( WPP_GLOBAL_Control != (CObjectMonitor *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
        {
          Tasks_TaskStateText(3);
          v6 = Tasks_TaskStateText(*((unsigned int *)a1 + 2));
          WPP_SF_SdSS(*(_QWORD *)(v7 + 16), 24, v9, v8 + 20, *(_DWORD *)(v8 + 16), v6, v9);
        }
        *((_DWORD *)a1 + 2) = 3;
        *((_DWORD *)a1 + 9) = 0;
        CServiceTaskManager::_ReleaseTaskDescriptor(a1);
      }
    }
  }
  return Error;
}

```

## disassembly

```asm
0x180022990  mov     [rsp+arg_8], rbx
0x180022995  mov     [rsp+arg_10], rsi
0x18002299a  push    rdi
0x18002299b  sub     rsp, 40h
0x18002299f  mov     edx, [rcx+8]
0x1800229a2  xor     edi, edi
0x1800229a4  mov     rbx, rcx
0x1800229a7  cmp     edx, 6
0x1800229aa  jz      loc_180022B27
0x1800229b0  cmp     edx, 2
0x1800229b3  jz      loc_180022AE1
0x1800229b9  lea     eax, [rdx-4]
0x1800229bc  cmp     eax, 1
0x1800229bf  jbe     loc_180022C01
0x1800229c5  mov     r11, cs:WPP_GLOBAL_Control
0x1800229cc  lea     rsi, WPP_GLOBAL_Control
0x1800229d3  cmp     r11, rsi
0x1800229d6  jz      short loc_1800229E6
0x1800229d8  test    dword ptr [r11+1Ch], 400000h
0x1800229e0  jnz     loc_180022B52
0x1800229e6  mov     dword ptr [rbx+8], 2
0x1800229ed  cmp     [rbx+10h], edi
0x1800229f0  jz      short loc_180022A42
0x1800229f2  lock inc dword ptr [rbx]
0x1800229f5  lea     rax, [rsp+48h+ThreadId]
0x1800229fa  mov     [rsp+48h+ThreadId], edi
0x1800229fe  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180022a03  lea     r8, ?_TaskThreadProc@CServiceTaskManager@@CAKPEAX@Z; lpStartAddress
0x180022a0a  mov     r9, rbx; lpParameter
0x180022a0d  mov     [rsp+48h+dwCreationFlags], edi; dwCreationFlags
0x180022a11  xor     edx, edx; dwStackSize
0x180022a13  xor     ecx, ecx; lpThreadAttributes
0x180022a15  call    cs:__imp_CreateThread
0x180022a1b  test    rax, rax
0x180022a1e  jz      loc_180022B93
0x180022a24  mov     rcx, rax; hObject
0x180022a27  mov     [rbx+24h], edi
0x180022a2a  call    cs:__imp_CloseHandle
0x180022a30  mov     rbx, [rsp+48h+arg_8]
0x180022a35  mov     eax, edi
0x180022a37  mov     rsi, [rsp+48h+arg_10]
0x180022a3c  add     rsp, 40h
0x180022a40  pop     rdi
0x180022a41  retn
0x180022a42  mov     dword ptr [rbx+24h], 1
0x180022a49  lock inc dword ptr [rbx]
0x180022a4c  mov     eax, [rbx+20h]
0x180022a4f  lea     rcx, ?_TaskThreadProc@CServiceTaskManager@@CAKPEAX@Z; Function
0x180022a56  neg     eax
0x180022a58  mov     rdx, rbx; Context
0x180022a5b  sbb     r8d, r8d
0x180022a5e  and     r8d, 10h; Flags
0x180022a62  call    cs:__imp_QueueUserWorkItem
0x180022a68  test    eax, eax
0x180022a6a  jnz     short loc_180022A30
0x180022a6c  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180022a71  mov     edi, eax
0x180022a73  mov     r11, cs:WPP_GLOBAL_Control
0x180022a7a  cmp     r11, rsi
0x180022a7d  jz      short loc_180022AC6
0x180022a7f  test    dword ptr [r11+1Ch], 400000h
0x180022a87  jz      short loc_180022AC6
0x180022a89  mov     r10, [rbx+38h]
0x180022a8d  mov     ecx, 3
0x180022a92  call    Tasks_TaskStateText
0x180022a97  mov     ecx, [rbx+8]
0x180022a9a  mov     r8, rax
0x180022a9d  call    Tasks_TaskStateText
0x180022aa2  mov     rcx, [r11+10h]
0x180022aa6  lea     r9, [r10+14h]
0x180022aaa  mov     [rsp+48h+var_18], r8
0x180022aaf  mov     edx, 18h
0x180022ab4  mov     [rsp+48h+lpThreadId], rax
0x180022ab9  mov     eax, [r10+10h]
0x180022abd  mov     [rsp+48h+dwCreationFlags], eax
0x180022ac1  call    WPP_SF_SdSS
0x180022ac6  mov     rcx, rbx; struct TASK_DESCRIPTOR *
0x180022ac9  mov     dword ptr [rbx+8], 3
0x180022ad0  mov     dword ptr [rbx+24h], 0
0x180022ad7  call    ?_ReleaseTaskDescriptor@CServiceTaskManager@@CAXPEAUTASK_DESCRIPTOR@@@Z; CServiceTaskManager::_ReleaseTaskDescriptor(TASK_DESCRIPTOR *)
0x180022adc  jmp     loc_180022A30
0x180022ae1  mov     rcx, cs:WPP_GLOBAL_Control
0x180022ae8  lea     rsi, WPP_GLOBAL_Control
0x180022aef  cmp     rcx, rsi
0x180022af2  jz      loc_180022A30
0x180022af8  test    dword ptr [rcx+1Ch], 400000h
0x180022aff  jz      loc_180022A30
0x180022b05  mov     edx, 14h
0x180022b0a  mov     r9, [rbx+38h]
0x180022b0e  lea     r8, WPP_088402f2fc59396373c04b0fd13246f5_Traceguids
0x180022b15  mov     rcx, [rcx+10h]
0x180022b19  add     r9, 14h
0x180022b1d  call    WPP_SF_S
0x180022b22  jmp     loc_180022A30
0x180022b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180022b2e  lea     rsi, WPP_GLOBAL_Control
0x180022b35  cmp     rcx, rsi
0x180022b38  jz      loc_180022A30
0x180022b3e  test    dword ptr [rcx+1Ch], 400000h
0x180022b45  jz      loc_180022A30
0x180022b4b  mov     edx, 13h
0x180022b50  jmp     short loc_180022B0A
0x180022b52  mov     r10, [rcx+38h]
0x180022b56  mov     ecx, 2
0x180022b5b  call    Tasks_TaskStateText
0x180022b60  mov     ecx, edx
0x180022b62  mov     r8, rax
0x180022b65  call    Tasks_TaskStateText
0x180022b6a  mov     rcx, [r11+10h]
0x180022b6e  lea     r9, [r10+14h]
0x180022b72  mov     [rsp+48h+var_18], r8
0x180022b77  mov     edx, 16h
0x180022b7c  mov     [rsp+48h+lpThreadId], rax
0x180022b81  mov     eax, [r10+10h]
0x180022b85  mov     [rsp+48h+dwCreationFlags], eax
0x180022b89  call    WPP_SF_SdSS
0x180022b8e  jmp     loc_1800229E6
0x180022b93  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180022b98  mov     edi, eax
0x180022b9a  mov     r11, cs:WPP_GLOBAL_Control
0x180022ba1  cmp     r11, rsi
0x180022ba4  jz      short loc_180022BED
0x180022ba6  test    dword ptr [r11+1Ch], 400000h
0x180022bae  jz      short loc_180022BED
0x180022bb0  mov     r10, [rbx+38h]
0x180022bb4  mov     ecx, 3
0x180022bb9  call    Tasks_TaskStateText
0x180022bbe  mov     ecx, [rbx+8]
0x180022bc1  mov     r8, rax
0x180022bc4  call    Tasks_TaskStateText
0x180022bc9  mov     rcx, [r11+10h]
0x180022bcd  lea     r9, [r10+14h]
0x180022bd1  mov     [rsp+48h+var_18], r8
0x180022bd6  mov     edx, 17h
0x180022bdb  mov     [rsp+48h+lpThreadId], rax
0x180022be0  mov     eax, [r10+10h]
0x180022be4  mov     [rsp+48h+dwCreationFlags], eax
0x180022be8  call    WPP_SF_SdSS
0x180022bed  mov     rcx, rbx; struct TASK_DESCRIPTOR *
0x180022bf0  mov     dword ptr [rbx+8], 3
0x180022bf7  call    ?_ReleaseTaskDescriptor@CServiceTaskManager@@CAXPEAUTASK_DESCRIPTOR@@@Z; CServiceTaskManager::_ReleaseTaskDescriptor(TASK_DESCRIPTOR *)
0x180022bfc  jmp     loc_180022A30
0x180022c01  mov     r10, cs:WPP_GLOBAL_Control
0x180022c08  lea     rsi, WPP_GLOBAL_Control
0x180022c0f  cmp     r10, rsi
0x180022c12  jz      short loc_180022C47
0x180022c14  test    dword ptr [r10+1Ch], 400000h
0x180022c1c  jz      short loc_180022C47
0x180022c1e  mov     ecx, edx
0x180022c20  call    Tasks_TaskStateText
0x180022c25  mov     r9, [rbx+38h]
0x180022c29  lea     r8, WPP_088402f2fc59396373c04b0fd13246f5_Traceguids
0x180022c30  mov     rcx, [r10+10h]
0x180022c34  add     r9, 14h
0x180022c38  mov     edx, 15h
0x180022c3d  mov     qword ptr [rsp+48h+dwCreationFlags], rax
0x180022c42  call    WPP_SF_SS
0x180022c47  mov     edi, 80071392h
0x180022c4c  jmp     loc_180022A30
```
