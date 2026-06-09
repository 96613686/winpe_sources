# CGhostThread::CreateWorkerThread(void)

- ea: `0x180008558`
- end: `0x1800086b0`
- name: `?CreateWorkerThread@CGhostThread@@AEAAHXZ`
- size: `344`
- prototype: `__int64 __fastcall(CGhostThread *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800083e8`

## callees

- `0x180003850`
- `0x180004dc4`
- `0x1800084c8`
- `0x180008558`
- `0x180008b00`
- `0x180008b38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000860e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000860e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008576`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180008576`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800085bf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800085bf`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800085f4`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800085f4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180008642`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x180008642`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000859a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008671`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000859a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008671`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008690`

## pseudocode

```c
__int64 __fastcall CGhostThread::CreateWorkerThread(CGhostThread *this)
{
  unsigned int v2; // edi
  HANDLE EventW; // rax
  void *v4; // rcx
  HANDLE Thread; // rax
  void *v6; // rcx
  void *v7; // rax
  DWORD v8; // eax
  void *v9; // rcx
  HANDLE Handles[3]; // [rsp+30h] [rbp-18h] BYREF
  DWORD ExitCode; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 11) = EventW;
  if ( EventW )
  {
    CCountedObject::AddRef(this);
    v4 = (void *)*((_QWORD *)this + 12);
    if ( v4 )
      CloseHandle(v4);
    Thread = CreateThread(0, 0, CGhostThread::s_ThreadProc, this, 4u, (LPDWORD)this + 26);
    *((_QWORD *)this + 12) = Thread;
    v6 = Thread;
    if ( Thread )
    {
      v7 = (void *)*((_QWORD *)this + 11);
      Handles[1] = v6;
      Handles[0] = v7;
      CGhostThread::SetState(this, 2);
      ResumeThread(*((HANDLE *)this + 12));
      v8 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
      if ( v8 )
      {
        if ( v8 == 1 )
        {
          ExitCode = 0;
          CGhostThread::SetState(this, 1);
          v9 = (void *)*((_QWORD *)this + 12);
          *((_DWORD *)this + 26) = 0;
          if ( GetExitCodeThread(v9, &ExitCode) && ExitCode == 5 )
          {
            CGhostThread::CleanupAllGhosts(this, 1);
            CGhostThread::SetState(this, 4);
          }
          CloseHandle(*((HANDLE *)this + 12));
          *((_QWORD *)this + 12) = 0;
        }
        else
        {
          CGhostThread::ShutdownGhostThread(this, 0);
        }
      }
      else
      {
        v2 = 1;
      }
    }
    else
    {
      CCountedObject::Release(this);
    }
    CloseHandle(*((HANDLE *)this + 11));
    *((_QWORD *)this + 11) = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180008558  mov     [rsp+arg_8], rbx
0x18000855d  mov     [rsp+arg_10], rsi
0x180008562  push    rdi
0x180008563  sub     rsp, 40h
0x180008567  mov     rbx, rcx
0x18000856a  xor     r9d, r9d; lpName
0x18000856d  xor     ecx, ecx; lpEventAttributes
0x18000856f  xor     r8d, r8d; bInitialState
0x180008572  xor     edx, edx; bManualReset
0x180008574  xor     edi, edi
0x180008576  call    cs:__imp_CreateEventW
0x18000857c  mov     [rbx+58h], rax
0x180008580  test    rax, rax
0x180008583  jz      loc_18000869E
0x180008589  mov     rcx, rbx; this
0x18000858c  call    ?AddRef@CCountedObject@@QEAAXXZ; CCountedObject::AddRef(void)
0x180008591  mov     rcx, [rbx+60h]; hObject
0x180008595  test    rcx, rcx
0x180008598  jz      short loc_1800085A0
0x18000859a  call    cs:__imp_CloseHandle
0x1800085a0  lea     rsi, [rbx+68h]
0x1800085a4  mov     r9, rbx; lpParameter
0x1800085a7  mov     [rsp+48h+lpThreadId], rsi; lpThreadId
0x1800085ac  lea     r8, ?s_ThreadProc@CGhostThread@@CAKPEAX@Z; lpStartAddress
0x1800085b3  xor     edx, edx; dwStackSize
0x1800085b5  mov     [rsp+48h+dwCreationFlags], 4; dwCreationFlags
0x1800085bd  xor     ecx, ecx; lpThreadAttributes
0x1800085bf  call    cs:__imp_CreateThread
0x1800085c5  mov     [rbx+60h], rax
0x1800085c9  mov     rcx, rax
0x1800085cc  test    rax, rax
0x1800085cf  jz      loc_180008684
0x1800085d5  mov     rax, [rbx+58h]
0x1800085d9  mov     edx, 2
0x1800085de  mov     [rsp+48h+var_10], rcx
0x1800085e3  mov     rcx, rbx
0x1800085e6  mov     [rsp+48h+Handles], rax
0x1800085eb  call    ?SetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@W42@@Z; CGhostThread::SetState(tagGHOSTTHREADSTATE)
0x1800085f0  mov     rcx, [rbx+60h]; hThread
0x1800085f4  call    cs:__imp_ResumeThread
0x1800085fa  xor     r8d, r8d; bWaitAll
0x1800085fd  mov     [rsp+48h+dwCreationFlags], edi; bAlertable
0x180008601  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180008605  lea     rdx, [rsp+48h+Handles]; lpHandles
0x18000860a  lea     ecx, [r8+2]; nCount
0x18000860e  call    cs:__imp_WaitForMultipleObjectsEx
0x180008614  test    eax, eax
0x180008616  jz      short loc_18000867D
0x180008618  mov     rcx, rbx; this
0x18000861b  cmp     eax, 1
0x18000861e  jz      short loc_180008629
0x180008620  xor     edx, edx; void **
0x180008622  call    ?ShutdownGhostThread@CGhostThread@@QEAAHPEAPEAX@Z; CGhostThread::ShutdownGhostThread(void * *)
0x180008627  jmp     short loc_18000868C
0x180008629  mov     edx, 1
0x18000862e  mov     [rsp+48h+ExitCode], edi
0x180008632  call    ?SetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@W42@@Z; CGhostThread::SetState(tagGHOSTTHREADSTATE)
0x180008637  mov     rcx, [rbx+60h]; hThread
0x18000863b  lea     rdx, [rsp+48h+ExitCode]; lpExitCode
0x180008640  mov     [rsi], edi
0x180008642  call    cs:__imp_GetExitCodeThread
0x180008648  test    eax, eax
0x18000864a  jz      short loc_18000866D
0x18000864c  cmp     [rsp+48h+ExitCode], 5
0x180008651  jnz     short loc_18000866D
0x180008653  mov     edx, 1; int
0x180008658  mov     rcx, rbx; this
0x18000865b  call    ?CleanupAllGhosts@CGhostThread@@AEAAHH@Z; CGhostThread::CleanupAllGhosts(int)
0x180008660  mov     edx, 4
0x180008665  mov     rcx, rbx
0x180008668  call    ?SetState@CGhostThread@@AEAA?AW4tagGHOSTTHREADSTATE@@W42@@Z; CGhostThread::SetState(tagGHOSTTHREADSTATE)
0x18000866d  mov     rcx, [rbx+60h]; hObject
0x180008671  call    cs:__imp_CloseHandle
0x180008677  mov     [rbx+60h], rdi
0x18000867b  jmp     short loc_18000868C
0x18000867d  mov     edi, 1
0x180008682  jmp     short loc_18000868C
0x180008684  mov     rcx, rbx; this
0x180008687  call    ?Release@CCountedObject@@QEAAXXZ; CCountedObject::Release(void)
0x18000868c  mov     rcx, [rbx+58h]; hObject
0x180008690  call    cs:__imp_CloseHandle
0x180008696  mov     qword ptr [rbx+58h], 0
0x18000869e  mov     rbx, [rsp+48h+arg_8]
0x1800086a3  mov     eax, edi
0x1800086a5  mov     rsi, [rsp+48h+arg_10]
0x1800086aa  add     rsp, 40h
0x1800086ae  pop     rdi
0x1800086af  retn
```
