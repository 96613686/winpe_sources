# WorkerThread

- ea: `0x1800183e0`
- end: `0x1800185d0`
- name: `WorkerThread`
- size: `496`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001d3e`
- `0x18000fafc`
- `0x1800152d0`
- `0x1800183e0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001856e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001856e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800184f3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800184f3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001846a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001846a`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001851c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001851c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001853a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001853a`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001843d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800184d0`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18001843d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x1800184d0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018449`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018591`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800185a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800185b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018449`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018591`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800185a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800185b1`

## pseudocode

```c
void __fastcall __noreturn WorkerThread(PVOID Parameter)
{
  DWORD v1; // ebx
  int v2; // edi
  DWORD TickCount; // esi
  DWORD v4; // eax
  DWORD v5; // eax
  DWORD v6; // eax
  void (__fastcall **v7)(_QWORD); // r14
  DWORD v8; // eax
  int v9; // [rsp+30h] [rbp-58h] BYREF
  HANDLE Handles[3]; // [rsp+38h] [rbp-50h] BYREF

  v1 = -1;
  Handles[0] = hEvent;
  v2 = 1;
  v9 = 1;
  Handles[1] = *(&TimerQ + 1);
  Handles[2] = qword_18004DA40;
  RegNotifyChangeKeyValue(hKey, 1, 4u, qword_18004DA40, 1);
  while ( 1 )
  {
    while ( 1 )
    {
      TickCount = GetTickCount();
      v4 = WaitForMultipleObjectsEx(3u, Handles, 0, v1, 1);
      if ( v4 )
        break;
      EnterCriticalSection(&CriticalSection);
      v7 = (void (__fastcall **)(_QWORD))WorkItemQ;
      WorkItemQ = *(void **)WorkItemQ;
      if ( !WorkItemQ )
      {
        ResetEvent(hEvent);
        *(&WorkItemQ + 1) = 0;
      }
      LeaveCriticalSection(&CriticalSection);
      v7[1](v7);
      memset_0(v7, 0, 0x1C10u);
      HeapFree(hHeap, 0, v7);
LABEL_12:
      if ( !v2 )
        goto LABEL_13;
    }
    v5 = v4 - 1;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        if ( v6 == 256 )
          goto LABEL_6;
      }
      else
      {
        ProcessChangeNotification(0);
        RegNotifyChangeKeyValue(hKey, 1, 4u, qword_18004DA40, 1);
      }
      goto LABEL_12;
    }
    v2 = 0;
    v9 = 0;
LABEL_13:
    if ( v1 == -1 )
    {
      v1 = 1000;
    }
    else
    {
      if ( GetTickCount() < TickCount )
        v8 = ~TickCount + GetTickCount();
      else
        v8 = GetTickCount() - TickCount;
      if ( v8 >= v1 )
      {
LABEL_6:
        TimerTick(&v9);
        v2 = v9;
        v1 = v9 != 0 ? -1 : 1000;
      }
      else
      {
        v1 -= v8;
      }
    }
  }
}

```

## disassembly

```asm
0x1800183e0  push    rbx
0x1800183e2  push    rbp
0x1800183e3  push    rsi
0x1800183e4  push    rdi
0x1800183e5  push    r14
0x1800183e7  sub     rsp, 60h
0x1800183eb  mov     rax, cs:__security_cookie
0x1800183f2  xor     rax, rsp
0x1800183f5  mov     [rsp+88h+var_38], rax
0x1800183fa  mov     rax, cs:hEvent
0x180018401  mov     ebp, 1
0x180018406  mov     r9, cs:qword_18004DA40; hEvent
0x18001840d  or      ebx, 0FFFFFFFFh
0x180018410  mov     rcx, cs:hKey; hKey
0x180018417  mov     edx, ebp; bWatchSubtree
0x180018419  mov     [rsp+88h+Handles], rax
0x18001841e  mov     edi, ebp
0x180018420  mov     rax, qword ptr cs:TimerQ+8
0x180018427  lea     r8d, [rbp+3]; dwNotifyFilter
0x18001842b  mov     [rsp+88h+var_58], ebp
0x18001842f  mov     [rsp+88h+var_48], rax
0x180018434  mov     [rsp+88h+var_40], r9
0x180018439  mov     [rsp+88h+fAsynchronous], ebp; fAsynchronous
0x18001843d  call    cs:__imp_RegNotifyChangeKeyValue
0x180018444  nop     dword ptr [rax+rax+00h]
0x180018449  call    cs:__imp_GetTickCount
0x180018450  nop     dword ptr [rax+rax+00h]
0x180018455  xor     r8d, r8d; bWaitAll
0x180018458  mov     [rsp+88h+fAsynchronous], ebp; bAlertable
0x18001845c  mov     r9d, ebx; dwMilliseconds
0x18001845f  lea     rdx, [rsp+88h+Handles]; lpHandles
0x180018464  mov     esi, eax
0x180018466  lea     ecx, [r8+3]; nCount
0x18001846a  call    cs:__imp_WaitForMultipleObjectsEx
0x180018471  nop     dword ptr [rax+rax+00h]
0x180018476  test    eax, eax
0x180018478  jz      short loc_1800184EC
0x18001847a  sub     eax, ebp
0x18001847c  jz      short loc_1800184E1
0x18001847e  sub     eax, ebp
0x180018480  jz      short loc_1800184AF
0x180018482  cmp     eax, 100h
0x180018487  jnz     loc_18001857A
0x18001848d  lea     rcx, [rsp+88h+var_58]
0x180018492  call    TimerTick
0x180018497  mov     edi, [rsp+88h+var_58]
0x18001849b  mov     eax, edi
0x18001849d  neg     eax
0x18001849f  sbb     ebx, ebx
0x1800184a1  and     ebx, 0FFFFFC17h
0x1800184a7  add     ebx, 3E8h
0x1800184ad  jmp     short loc_180018449
0x1800184af  xor     ecx, ecx
0x1800184b1  call    ProcessChangeNotification
0x1800184b6  mov     r9, cs:qword_18004DA40; hEvent
0x1800184bd  mov     r8d, 4; dwNotifyFilter
0x1800184c3  mov     rcx, cs:hKey; hKey
0x1800184ca  mov     edx, ebp; bWatchSubtree
0x1800184cc  mov     [rsp+88h+fAsynchronous], ebp; fAsynchronous
0x1800184d0  call    cs:__imp_RegNotifyChangeKeyValue
0x1800184d7  nop     dword ptr [rax+rax+00h]
0x1800184dc  jmp     loc_18001857A
0x1800184e1  xor     edi, edi
0x1800184e3  mov     [rsp+88h+var_58], edi
0x1800184e7  jmp     loc_180018582
0x1800184ec  lea     rcx, CriticalSection; lpCriticalSection
0x1800184f3  call    cs:__imp_EnterCriticalSection
0x1800184fa  nop     dword ptr [rax+rax+00h]
0x1800184ff  mov     r14, qword ptr cs:WorkItemQ
0x180018506  mov     rax, [r14]
0x180018509  mov     qword ptr cs:WorkItemQ, rax
0x180018510  test    rax, rax
0x180018513  jnz     short loc_180018533
0x180018515  mov     rcx, cs:hEvent; hEvent
0x18001851c  call    cs:__imp_ResetEvent
0x180018523  nop     dword ptr [rax+rax+00h]
0x180018528  mov     qword ptr cs:WorkItemQ+8, 0
0x180018533  lea     rcx, CriticalSection; lpCriticalSection
0x18001853a  call    cs:__imp_LeaveCriticalSection
0x180018541  nop     dword ptr [rax+rax+00h]
0x180018546  mov     rax, [r14+8]
0x18001854a  mov     rcx, r14
0x18001854d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018552  xor     edx, edx; Val
0x180018554  mov     r8d, 1C10h; Size
0x18001855a  mov     rcx, r14; void *
0x18001855d  call    memset_0
0x180018562  mov     rcx, cs:hHeap; hHeap
0x180018569  mov     r8, r14; lpMem
0x18001856c  xor     edx, edx; dwFlags
0x18001856e  call    cs:__imp_HeapFree
0x180018575  nop     dword ptr [rax+rax+00h]
0x18001857a  test    edi, edi
0x18001857c  jnz     loc_180018449
0x180018582  cmp     ebx, 0FFFFFFFFh
0x180018585  jnz     short loc_180018591
0x180018587  mov     ebx, 3E8h
0x18001858c  jmp     loc_180018449
0x180018591  call    cs:__imp_GetTickCount
0x180018598  nop     dword ptr [rax+rax+00h]
0x18001859d  cmp     eax, esi
0x18001859f  jb      short loc_1800185B1
0x1800185a1  call    cs:__imp_GetTickCount
0x1800185a8  nop     dword ptr [rax+rax+00h]
0x1800185ad  sub     eax, esi
0x1800185af  jmp     short loc_1800185C1
0x1800185b1  call    cs:__imp_GetTickCount
0x1800185b8  nop     dword ptr [rax+rax+00h]
0x1800185bd  not     esi
0x1800185bf  add     eax, esi
0x1800185c1  cmp     eax, ebx
0x1800185c3  jnb     loc_18001848D
0x1800185c9  sub     ebx, eax
0x1800185cb  jmp     loc_180018449
```
