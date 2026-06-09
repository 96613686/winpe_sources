# CSharedContext::Initialize(void)

- ea: `0x180078250`
- end: `0x180078328`
- name: `?Initialize@CSharedContext@@AEAA_NXZ`
- size: `216`
- prototype: `bool __fastcall(CSharedContext *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180076118`

## callees

- `0x180078250`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180078269`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007828e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180078269`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007828e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180078303`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180078303`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800782ce`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800782ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007829d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007829d`
- `USER32!GetThreadDesktop` at `0x1800782a5`
- `USER32!GetThreadDesktop` at `0x1800782a5`

## pseudocode

```c
bool __fastcall CSharedContext::Initialize(CSharedContext *this)
{
  HANDLE EventW; // rax
  int v3; // ecx
  HANDLE v4; // rax
  DWORD CurrentThreadId; // eax
  HANDLE Thread; // rax
  void *v7; // rcx
  void *v8; // rax
  int v9; // ebx
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF

  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 12) = EventW;
  if ( EventW
    && (v4 = CreateEventW(0, 1, 0, 0), (*((_QWORD *)this + 13) = v4) != 0)
    && (CurrentThreadId = GetCurrentThreadId(),
        *((_QWORD *)this + 10) = GetThreadDesktop(CurrentThreadId),
        Thread = CreateThread(0, 0, CSharedContext::StaticAlpcClientThreadProc, this, 0, 0),
        *((_QWORD *)this + 11) = Thread,
        (v7 = Thread) != 0) )
  {
    v8 = (void *)*((_QWORD *)this + 12);
    v9 = 0;
    Handles[1] = v7;
    Handles[0] = v8;
    if ( WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0) )
      v9 = -2147467259;
    v3 = v9;
  }
  else
  {
    v3 = -2147467259;
  }
  return v3 >= 0;
}

```

## disassembly

```asm
0x180078250  mov     [rsp+arg_0], rbx
0x180078255  push    rdi
0x180078256  sub     rsp, 40h
0x18007825a  xor     r9d, r9d; lpName
0x18007825d  mov     rdi, rcx
0x180078260  xor     r8d, r8d; bInitialState
0x180078263  xor     ecx, ecx; lpEventAttributes
0x180078265  lea     edx, [r9+1]; bManualReset
0x180078269  call    cs:__imp_CreateEventW
0x18007826f  mov     [rdi+60h], rax
0x180078273  test    rax, rax
0x180078276  jnz     short loc_180078282
0x180078278  mov     ecx, 80004005h
0x18007827d  jmp     loc_180078315
0x180078282  xor     r9d, r9d; lpName
0x180078285  xor     r8d, r8d; bInitialState
0x180078288  xor     ecx, ecx; lpEventAttributes
0x18007828a  lea     edx, [r9+1]; bManualReset
0x18007828e  call    cs:__imp_CreateEventW
0x180078294  mov     [rdi+68h], rax
0x180078298  test    rax, rax
0x18007829b  jz      short loc_180078278
0x18007829d  call    cs:__imp_GetCurrentThreadId
0x1800782a3  mov     ecx, eax; dwThreadId
0x1800782a5  call    cs:__imp_GetThreadDesktop
0x1800782ab  mov     r9, rdi; lpParameter
0x1800782ae  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x1800782b7  lea     r8, ?StaticAlpcClientThreadProc@CSharedContext@@CAKPEAX@Z; lpStartAddress
0x1800782be  mov     [rdi+50h], rax
0x1800782c2  xor     edx, edx; dwStackSize
0x1800782c4  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x1800782cc  xor     ecx, ecx; lpThreadAttributes
0x1800782ce  call    cs:__imp_CreateThread
0x1800782d4  mov     [rdi+58h], rax
0x1800782d8  mov     rcx, rax
0x1800782db  test    rax, rax
0x1800782de  jz      short loc_180078278
0x1800782e0  mov     rax, [rdi+60h]
0x1800782e4  lea     rdx, [rsp+48h+Handles]; lpHandles
0x1800782e9  xor     ebx, ebx
0x1800782eb  mov     [rsp+48h+var_10], rcx
0x1800782f0  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800782f4  mov     [rsp+48h+Handles], rax
0x1800782f9  xor     r8d, r8d; bWaitAll
0x1800782fc  mov     [rsp+48h+dwCreationFlags], ebx; bAlertable
0x180078300  lea     ecx, [rbx+2]; nCount
0x180078303  call    cs:__imp_WaitForMultipleObjectsEx
0x180078309  mov     ecx, 80004005h
0x18007830e  test    eax, eax
0x180078310  cmovnz  ebx, ecx
0x180078313  mov     ecx, ebx
0x180078315  mov     rbx, [rsp+48h+arg_0]
0x18007831a  shr     ecx, 1Fh
0x18007831d  xor     cl, 1
0x180078320  mov     al, cl
0x180078322  add     rsp, 40h
0x180078326  pop     rdi
0x180078327  retn
```
