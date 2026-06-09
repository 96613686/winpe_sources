# WORK_QUEUE::DequeueWorkItem(ulong,WORK_ITEM * *)

- ea: `0x1800071d4`
- end: `0x180007398`
- name: `?DequeueWorkItem@WORK_QUEUE@@AEAAJKPEAPEAVWORK_ITEM@@@Z`
- size: `452`
- prototype: `int(WORK_QUEUE *__hidden this, unsigned int, struct WORK_ITEM **)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800076e0`
- `0x180007890`

## callees

- `0x1800071d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800072e8`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180007218`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x180007218`
- `iisutil!PuDbgPrint` at `0x180007292`
- `iisutil!PuDbgPrint` at `0x18000735f`
- `iisutil!PuDbgPrint` at `0x180007292`
- `iisutil!PuDbgPrint` at `0x18000735f`
- `iisutil!PuDbgPrintError` at `0x1800072d5`
- `iisutil!PuDbgPrintError` at `0x1800072d5`

## string_xrefs

- `0x18000728b`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\work_queue.cxx`
- `0x1800072ce`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\work_queue.cxx`
- `0x180007348`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\work_queue.cxx`
- `0x18000733c`: `CompletionKey = %08x\npOverlapped = %08x\nsize = %d \n`

## pseudocode

```c
__int64 __fastcall WORK_QUEUE::DequeueWorkItem(WORK_QUEUE *this, DWORD dwMilliseconds, HANDLE **a3)
{
  void *v3; // rcx
  BOOL QueuedCompletionStatus; // eax
  LPOVERLAPPED v6; // rdx
  signed int v7; // eax
  unsigned int v8; // ebx
  unsigned int v9; // edi
  signed int LastError; // eax
  unsigned __int64 v11; // r8
  HANDLE *p_hEvent; // rax
  DWORD NumberOfBytesTransferred; // [rsp+60h] [rbp+20h] BYREF
  unsigned __int64 CompletionKey; // [rsp+70h] [rbp+30h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+78h] [rbp+38h] BYREF

  v3 = (void *)*((_QWORD *)this + 2);
  *a3 = 0;
  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  Overlapped = 0;
  QueuedCompletionStatus = GetQueuedCompletionStatus(
                             v3,
                             &NumberOfBytesTransferred,
                             &CompletionKey,
                             &Overlapped,
                             dwMilliseconds);
  v6 = Overlapped;
  if ( QueuedCompletionStatus || Overlapped )
  {
    v8 = 0;
    v9 = 0;
    if ( !QueuedCompletionStatus )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      v6 = Overlapped;
    }
    v11 = CompletionKey;
    if ( CompletionKey )
    {
      if ( (g_dwDebugFlags & 0x110000) != 0 && (g_dwDebugFlags & 3) != 0 )
      {
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\work_queue.cxx",
          1274,
          "WORK_QUEUE::DequeueWorkItem",
          "CompletionKey = %08x\npOverlapped = %08x\nsize = %d \n",
          CompletionKey,
          (_DWORD)v6,
          NumberOfBytesTransferred);
        v11 = CompletionKey;
      }
      p_hEvent = (HANDLE *)(v11 - 40);
    }
    else
    {
      p_hEvent = &v6[-2].hEvent;
    }
    *a3 = p_hEvent;
    *((_DWORD *)p_hEvent + 20) = v9;
    *((_DWORD *)p_hEvent + 3) = NumberOfBytesTransferred;
    p_hEvent[2] = (HANDLE)CompletionKey;
    p_hEvent[12] = Overlapped;
  }
  else
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v8 == -2147024638 )
    {
      if ( (g_dwDebugFlags & 0x110000) != 0 && (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\work_queue.cxx",
          1224,
          "WORK_QUEUE::DequeueWorkItem",
          "Dequeuing work item timed out\n");
    }
    else if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\work_queue.cxx",
        1235,
        "WORK_QUEUE::DequeueWorkItem",
        v8,
        "Dequeueing work item failed\n");
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800071d4  mov     [rsp-18h+arg_8], rbx
0x1800071d9  push    rbp
0x1800071da  push    rsi
0x1800071db  push    rdi
0x1800071dc  mov     rbp, rsp
0x1800071df  sub     rsp, 40h
0x1800071e3  mov     rcx, [rcx+10h]; CompletionPort
0x1800071e7  lea     r9, [rbp+Overlapped]; lpOverlapped
0x1800071eb  mov     rsi, r8
0x1800071ee  mov     qword ptr [r8], 0
0x1800071f5  mov     [rsp+40h+dwMilliseconds], edx; dwMilliseconds
0x1800071f9  lea     r8, [rbp+CompletionKey]; lpCompletionKey
0x1800071fd  lea     rdx, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180007201  mov     [rbp+NumberOfBytesTransferred], 0
0x180007208  mov     [rbp+CompletionKey], 0
0x180007210  mov     [rbp+Overlapped], 0
0x180007218  call    cs:__imp_GetQueuedCompletionStatus
0x18000721e  mov     rdx, [rbp+Overlapped]
0x180007222  test    eax, eax
0x180007224  jnz     loc_1800072E0
0x18000722a  test    rdx, rdx
0x18000722d  jnz     loc_1800072E0
0x180007233  call    cs:__imp_GetLastError
0x180007239  mov     ebx, eax
0x18000723b  test    eax, eax
0x18000723d  jle     short loc_180007248
0x18000723f  movzx   ebx, ax
0x180007242  or      ebx, 80070000h
0x180007248  cmp     ebx, 80070102h
0x18000724e  jnz     short loc_18000729D
0x180007250  mov     eax, cs:g_dwDebugFlags
0x180007256  test    eax, 110000h
0x18000725b  setnz   cl
0x18000725e  test    al, 3
0x180007260  setnz   al
0x180007263  test    al, cl
0x180007265  jz      loc_180007389
0x18000726b  mov     rcx, cs:g_pDebug
0x180007272  lea     rax, aDequeuingWorkI; "Dequeuing work item timed out\n"
0x180007279  lea     r9, aWorkQueueDeque; "WORK_QUEUE::DequeueWorkItem"
0x180007280  mov     qword ptr [rsp+40h+dwMilliseconds], rax
0x180007285  mov     r8d, 4C8h
0x18000728b  lea     rdx, aServercommonIn_31; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180007292  call    cs:__imp_PuDbgPrint
0x180007298  jmp     loc_180007389
0x18000729d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800072a4  jz      loc_180007389
0x1800072aa  mov     rcx, cs:g_pDebug
0x1800072b1  lea     rax, aDequeueingWork; "Dequeueing work item failed\n"
0x1800072b8  mov     [rsp+40h+var_18], rax
0x1800072bd  lea     r9, aWorkQueueDeque; "WORK_QUEUE::DequeueWorkItem"
0x1800072c4  mov     r8d, 4D3h
0x1800072ca  mov     [rsp+40h+dwMilliseconds], ebx
0x1800072ce  lea     rdx, aServercommonIn_31; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800072d5  call    cs:__imp_PuDbgPrintError
0x1800072db  jmp     loc_180007389
0x1800072e0  xor     ebx, ebx
0x1800072e2  xor     edi, edi
0x1800072e4  test    eax, eax
0x1800072e6  jnz     short loc_180007301
0x1800072e8  call    cs:__imp_GetLastError
0x1800072ee  mov     edi, eax
0x1800072f0  test    eax, eax
0x1800072f2  jle     short loc_1800072FD
0x1800072f4  movzx   edi, ax
0x1800072f7  or      edi, 80070000h
0x1800072fd  mov     rdx, [rbp+Overlapped]
0x180007301  mov     r8, [rbp+CompletionKey]
0x180007305  test    r8, r8
0x180007308  jnz     short loc_180007310
0x18000730a  lea     rax, [rdx-28h]
0x18000730e  jmp     short loc_18000736D
0x180007310  mov     eax, cs:g_dwDebugFlags
0x180007316  test    eax, 110000h
0x18000731b  setnz   cl
0x18000731e  test    al, 3
0x180007320  setnz   al
0x180007323  test    al, cl
0x180007325  jz      short loc_180007369
0x180007327  mov     eax, [rbp+NumberOfBytesTransferred]
0x18000732a  lea     r9, aWorkQueueDeque; "WORK_QUEUE::DequeueWorkItem"
0x180007331  mov     rcx, cs:g_pDebug
0x180007338  mov     [rsp+40h+var_8], eax
0x18000733c  lea     rax, aCompletionkey0; "CompletionKey = %08x\npOverlapped = %08"...
0x180007343  mov     [rsp+40h+var_10], rdx
0x180007348  lea     rdx, aServercommonIn_31; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000734f  mov     [rsp+40h+var_18], r8
0x180007354  mov     r8d, 4FAh
0x18000735a  mov     qword ptr [rsp+40h+dwMilliseconds], rax
0x18000735f  call    cs:__imp_PuDbgPrint
0x180007365  mov     r8, [rbp+CompletionKey]
0x180007369  lea     rax, [r8-28h]
0x18000736d  mov     [rsi], rax
0x180007370  mov     [rax+50h], edi
0x180007373  mov     ecx, [rbp+NumberOfBytesTransferred]
0x180007376  mov     [rax+0Ch], ecx
0x180007379  mov     rcx, [rbp+CompletionKey]
0x18000737d  mov     [rax+10h], rcx
0x180007381  mov     rcx, [rbp+Overlapped]
0x180007385  mov     [rax+60h], rcx
0x180007389  mov     eax, ebx
0x18000738b  mov     rbx, [rsp+40h+arg_8]
0x180007390  add     rsp, 40h
0x180007394  pop     rdi
0x180007395  pop     rsi
0x180007396  pop     rbp
0x180007397  retn
```
