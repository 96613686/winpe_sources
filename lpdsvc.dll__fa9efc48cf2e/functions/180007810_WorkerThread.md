# WorkerThread

- ea: `0x180007810`
- end: `0x1800079c7`
- name: `WorkerThread`
- size: `439`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002e7c`
- `0x180002ea4`
- `0x180007354`
- `0x180007810`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18000785a`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18000785a`
- `KERNEL32!GetCurrentThreadId` at `0x180007819`
- `KERNEL32!GetCurrentThreadId` at `0x180007819`
- `KERNEL32!WaitForMultipleObjects` at `0x18000788c`
- `KERNEL32!WaitForMultipleObjects` at `0x18000788c`
- `KERNEL32!EnterCriticalSection` at `0x1800078be`
- `KERNEL32!EnterCriticalSection` at `0x18000793a`
- `KERNEL32!EnterCriticalSection` at `0x1800078be`
- `KERNEL32!EnterCriticalSection` at `0x18000793a`
- `KERNEL32!LeaveCriticalSection` at `0x1800078f1`
- `KERNEL32!LeaveCriticalSection` at `0x180007955`
- `KERNEL32!LeaveCriticalSection` at `0x1800078f1`
- `KERNEL32!LeaveCriticalSection` at `0x180007955`
- `KERNEL32!SetEvent` at `0x180007993`
- `KERNEL32!SetEvent` at `0x180007993`

## pseudocode

```c
__int64 __fastcall WorkerThread(PVOID Parameter)
{
  DWORD CurrentThreadId; // edi
  char *v2; // rbx
  int v3; // ebx
  HANDLE Handles[7]; // [rsp+20h] [rbp-38h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  *(_OWORD *)Handles = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids);
  rand();
  v2 = 0;
  Handles[0] = hWorkThreadSemaphore;
  Handles[1] = hEventShutdownGLB;
  while ( !WaitForMultipleObjects(2u, Handles, 0, 0x7D00u) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids);
    EnterCriticalSection(&csConnSemGLB);
    if ( scConnHeadGLB )
    {
      v2 = (char *)scConnHeadGLB;
      scConnHeadGLB = *(_QWORD *)scConnHeadGLB;
      *(_QWORD *)v2 = 0;
      --HIDWORD(qword_180013710);
    }
    LeaveCriticalSection(&csConnSemGLB);
    if ( v2 )
      ServiceTheClient(v2);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids, CurrentThreadId);
  EnterCriticalSection(&csConnSemGLB);
  LODWORD(Common) = Common - 1;
  v3 = Common;
  LeaveCriticalSection(&csConnSemGLB);
  if ( v3 < 1 && fShuttingDownGLB )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids);
    SetEvent(hEventLastThreadGLB);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x180007810  push    rbx
0x180007812  push    rbp
0x180007813  push    rsi
0x180007814  push    rdi
0x180007815  sub     rsp, 38h
0x180007819  call    cs:__imp_GetCurrentThreadId
0x18000781f  xorps   xmm0, xmm0
0x180007822  mov     edi, eax
0x180007824  movups  xmmword ptr [rsp+58h+Handles], xmm0
0x180007829  mov     rcx, cs:WPP_GLOBAL_Control
0x180007830  lea     rsi, WPP_GLOBAL_Control
0x180007837  lea     rbp, WPP_29826dfb2f8839e6e8539e32ef026641_Traceguids
0x18000783e  cmp     rcx, rsi
0x180007841  jz      short loc_18000785A
0x180007843  test    byte ptr [rcx+1Ch], 1
0x180007847  jz      short loc_18000785A
0x180007849  mov     rcx, [rcx+10h]
0x18000784d  mov     edx, 0Ah
0x180007852  mov     r8, rbp
0x180007855  call    WPP_SF_
0x18000785a  call    cs:__imp_rand
0x180007860  mov     rax, cs:hWorkThreadSemaphore
0x180007867  xor     ebx, ebx
0x180007869  mov     [rsp+58h+Handles], rax
0x18000786e  mov     rax, cs:hEventShutdownGLB
0x180007875  mov     [rsp+58h+Handles+8], rax
0x18000787a  xor     r8d, r8d; bWaitAll
0x18000787d  lea     rdx, [rsp+58h+Handles]; lpHandles
0x180007882  mov     r9d, 7D00h; dwMilliseconds
0x180007888  lea     ecx, [r8+2]; nCount
0x18000788c  call    cs:__imp_WaitForMultipleObjects
0x180007892  test    eax, eax
0x180007894  jnz     short loc_18000790D
0x180007896  mov     rcx, cs:WPP_GLOBAL_Control
0x18000789d  cmp     rcx, rsi
0x1800078a0  jz      short loc_1800078B7
0x1800078a2  test    byte ptr [rcx+1Ch], 2
0x1800078a6  jz      short loc_1800078B7
0x1800078a8  mov     rcx, [rcx+10h]
0x1800078ac  lea     edx, [rax+0Bh]
0x1800078af  mov     r8, rbp
0x1800078b2  call    WPP_SF_
0x1800078b7  lea     rcx, csConnSemGLB; lpCriticalSection
0x1800078be  call    cs:__imp_EnterCriticalSection
0x1800078c4  mov     rax, cs:scConnHeadGLB
0x1800078cb  test    rax, rax
0x1800078ce  jz      short loc_1800078EA
0x1800078d0  mov     rbx, rax
0x1800078d3  mov     rax, [rax]
0x1800078d6  mov     cs:scConnHeadGLB, rax
0x1800078dd  mov     qword ptr [rbx], 0
0x1800078e4  dec     dword ptr cs:qword_180013710+4
0x1800078ea  lea     rcx, csConnSemGLB; lpCriticalSection
0x1800078f1  call    cs:__imp_LeaveCriticalSection
0x1800078f7  test    rbx, rbx
0x1800078fa  jz      loc_18000787A
0x180007900  mov     rcx, rbx; hMem
0x180007903  call    ServiceTheClient
0x180007908  jmp     loc_18000787A
0x18000790d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007914  cmp     rcx, rsi
0x180007917  jz      short loc_180007933
0x180007919  test    byte ptr [rcx+1Ch], 2
0x18000791d  jz      short loc_180007933
0x18000791f  mov     rcx, [rcx+10h]
0x180007923  mov     edx, 0Dh
0x180007928  mov     r9d, edi
0x18000792b  mov     r8, rbp
0x18000792e  call    WPP_SF_d
0x180007933  lea     rcx, csConnSemGLB; lpCriticalSection
0x18000793a  call    cs:__imp_EnterCriticalSection
0x180007940  mov     ebx, dword ptr cs:Common
0x180007946  lea     rcx, csConnSemGLB; lpCriticalSection
0x18000794d  dec     ebx
0x18000794f  mov     dword ptr cs:Common, ebx
0x180007955  call    cs:__imp_LeaveCriticalSection
0x18000795b  cmp     ebx, 1
0x18000795e  jge     short loc_180007999
0x180007960  cmp     cs:fShuttingDownGLB, 0
0x180007967  jz      short loc_180007999
0x180007969  mov     rcx, cs:WPP_GLOBAL_Control
0x180007970  cmp     rcx, rsi
0x180007973  jz      short loc_18000798C
0x180007975  test    byte ptr [rcx+1Ch], 2
0x180007979  jz      short loc_18000798C
0x18000797b  mov     rcx, [rcx+10h]
0x18000797f  mov     edx, 0Eh
0x180007984  mov     r8, rbp
0x180007987  call    WPP_SF_
0x18000798c  mov     rcx, cs:hEventLastThreadGLB; hEvent
0x180007993  call    cs:__imp_SetEvent
0x180007999  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079a0  cmp     rcx, rsi
0x1800079a3  jz      short loc_1800079BC
0x1800079a5  test    byte ptr [rcx+1Ch], 1
0x1800079a9  jz      short loc_1800079BC
0x1800079ab  mov     rcx, [rcx+10h]
0x1800079af  mov     edx, 0Fh
0x1800079b4  mov     r8, rbp
0x1800079b7  call    WPP_SF_
0x1800079bc  xor     eax, eax
0x1800079be  add     rsp, 38h
0x1800079c2  pop     rdi
0x1800079c3  pop     rsi
0x1800079c4  pop     rbp
0x1800079c5  pop     rbx
0x1800079c6  retn
```
