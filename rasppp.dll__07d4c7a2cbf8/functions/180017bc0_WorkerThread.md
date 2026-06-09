# WorkerThread

- ea: `0x180017bc0`
- end: `0x180017d68`
- name: `WorkerThread`
- size: `424`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001d3e`
- `0x18000f698`
- `0x180014bb0`
- `0x180017bc0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017d1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017d1e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017cb5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017cb5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180017c3e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180017c3e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180017cd8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180017cd8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017cf0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017cf0`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180017c1d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180017c9e`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180017c1d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x180017c9e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180017c23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180017d3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180017d45`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180017d4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180017c23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180017d3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180017d45`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180017d4f`

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
  Handles[2] = qword_18004CA40;
  RegNotifyChangeKeyValue(hKey, 1, 4u, qword_18004CA40, 1);
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
        RegNotifyChangeKeyValue(hKey, 1, 4u, qword_18004CA40, 1);
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
0x180017bc0  push    rbx
0x180017bc2  push    rbp
0x180017bc3  push    rsi
0x180017bc4  push    rdi
0x180017bc5  push    r14
0x180017bc7  sub     rsp, 60h
0x180017bcb  mov     rax, cs:__security_cookie
0x180017bd2  xor     rax, rsp
0x180017bd5  mov     [rsp+88h+var_38], rax
0x180017bda  mov     rax, cs:hEvent
0x180017be1  mov     ebp, 1
0x180017be6  mov     r9, cs:qword_18004CA40; hEvent
0x180017bed  or      ebx, 0FFFFFFFFh
0x180017bf0  mov     rcx, cs:hKey; hKey
0x180017bf7  mov     edx, ebp; bWatchSubtree
0x180017bf9  mov     [rsp+88h+Handles], rax
0x180017bfe  mov     edi, ebp
0x180017c00  mov     rax, qword ptr cs:TimerQ+8
0x180017c07  lea     r8d, [rbp+3]; dwNotifyFilter
0x180017c0b  mov     [rsp+88h+var_58], ebp
0x180017c0f  mov     [rsp+88h+var_48], rax
0x180017c14  mov     [rsp+88h+var_40], r9
0x180017c19  mov     [rsp+88h+fAsynchronous], ebp; fAsynchronous
0x180017c1d  call    cs:__imp_RegNotifyChangeKeyValue
0x180017c23  call    cs:__imp_GetTickCount
0x180017c29  xor     r8d, r8d; bWaitAll
0x180017c2c  mov     [rsp+88h+fAsynchronous], ebp; bAlertable
0x180017c30  mov     r9d, ebx; dwMilliseconds
0x180017c33  lea     rdx, [rsp+88h+Handles]; lpHandles
0x180017c38  mov     esi, eax
0x180017c3a  lea     ecx, [r8+3]; nCount
0x180017c3e  call    cs:__imp_WaitForMultipleObjectsEx
0x180017c44  test    eax, eax
0x180017c46  jz      short loc_180017CAE
0x180017c48  sub     eax, ebp
0x180017c4a  jz      short loc_180017CA6
0x180017c4c  sub     eax, ebp
0x180017c4e  jz      short loc_180017C7D
0x180017c50  cmp     eax, 100h
0x180017c55  jnz     loc_180017D24
0x180017c5b  lea     rcx, [rsp+88h+var_58]
0x180017c60  call    TimerTick
0x180017c65  mov     edi, [rsp+88h+var_58]
0x180017c69  mov     eax, edi
0x180017c6b  neg     eax
0x180017c6d  sbb     ebx, ebx
0x180017c6f  and     ebx, 0FFFFFC17h
0x180017c75  add     ebx, 3E8h
0x180017c7b  jmp     short loc_180017C23
0x180017c7d  xor     ecx, ecx
0x180017c7f  call    ProcessChangeNotification
0x180017c84  mov     r9, cs:qword_18004CA40; hEvent
0x180017c8b  mov     r8d, 4; dwNotifyFilter
0x180017c91  mov     rcx, cs:hKey; hKey
0x180017c98  mov     edx, ebp; bWatchSubtree
0x180017c9a  mov     [rsp+88h+fAsynchronous], ebp; fAsynchronous
0x180017c9e  call    cs:__imp_RegNotifyChangeKeyValue
0x180017ca4  jmp     short loc_180017D24
0x180017ca6  xor     edi, edi
0x180017ca8  mov     [rsp+88h+var_58], edi
0x180017cac  jmp     short loc_180017D2C
0x180017cae  lea     rcx, CriticalSection; lpCriticalSection
0x180017cb5  call    cs:__imp_EnterCriticalSection
0x180017cbb  mov     r14, qword ptr cs:WorkItemQ
0x180017cc2  mov     rax, [r14]
0x180017cc5  mov     qword ptr cs:WorkItemQ, rax
0x180017ccc  test    rax, rax
0x180017ccf  jnz     short loc_180017CE9
0x180017cd1  mov     rcx, cs:hEvent; hEvent
0x180017cd8  call    cs:__imp_ResetEvent
0x180017cde  mov     qword ptr cs:WorkItemQ+8, 0
0x180017ce9  lea     rcx, CriticalSection; lpCriticalSection
0x180017cf0  call    cs:__imp_LeaveCriticalSection
0x180017cf6  mov     rax, [r14+8]
0x180017cfa  mov     rcx, r14
0x180017cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d02  xor     edx, edx; Val
0x180017d04  mov     r8d, 1C10h; Size
0x180017d0a  mov     rcx, r14; void *
0x180017d0d  call    memset_0
0x180017d12  mov     rcx, cs:hHeap; hHeap
0x180017d19  mov     r8, r14; lpMem
0x180017d1c  xor     edx, edx; dwFlags
0x180017d1e  call    cs:__imp_HeapFree
0x180017d24  test    edi, edi
0x180017d26  jnz     loc_180017C23
0x180017d2c  cmp     ebx, 0FFFFFFFFh
0x180017d2f  jnz     short loc_180017D3B
0x180017d31  mov     ebx, 3E8h
0x180017d36  jmp     loc_180017C23
0x180017d3b  call    cs:__imp_GetTickCount
0x180017d41  cmp     eax, esi
0x180017d43  jb      short loc_180017D4F
0x180017d45  call    cs:__imp_GetTickCount
0x180017d4b  sub     eax, esi
0x180017d4d  jmp     short loc_180017D59
0x180017d4f  call    cs:__imp_GetTickCount
0x180017d55  not     esi
0x180017d57  add     eax, esi
0x180017d59  cmp     eax, ebx
0x180017d5b  jnb     loc_180017C5B
0x180017d61  sub     ebx, eax
0x180017d63  jmp     loc_180017C23
```
