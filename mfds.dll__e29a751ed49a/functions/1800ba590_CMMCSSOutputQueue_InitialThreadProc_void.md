# CMMCSSOutputQueue::InitialThreadProc(void *)

- ea: `0x1800ba590`
- end: `0x1800ba674`
- name: `?InitialThreadProc@CMMCSSOutputQueue@@KAKPEAX@Z`
- size: `228`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800ba590`
- `0x1800ba770`
- `0x1800c6fdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba5fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba5fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ba641`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800ba5c9`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800ba5c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ba5b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800ba5b7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800ba60f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800ba60f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800ba658`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800ba658`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800ba631`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800ba631`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800ba5e5`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800ba5e5`

## pseudocode

```c
__int64 __fastcall CMMCSSOutputQueue::InitialThreadProc(WCHAR *lpThreadParameter)
{
  const WCHAR *v2; // rdi
  int v3; // esi
  HANDLE CurrentThread; // rbp
  int ThreadPriority; // eax
  int v6; // r14d
  HANDLE v7; // rax
  unsigned int v8; // eax
  void *v9; // rcx
  unsigned int v10; // edi
  DWORD TaskIndex; // [rsp+60h] [rbp+8h] BYREF

  v2 = lpThreadParameter + 76;
  v3 = CAMThread::CoInitializeHelper();
  if ( *v2 )
  {
    CurrentThread = GetCurrentThread();
    ThreadPriority = GetThreadPriority(CurrentThread);
    TaskIndex = 0;
    v6 = ThreadPriority;
    v7 = AvSetMmThreadCharacteristicsW(v2, &TaskIndex);
    *((_QWORD *)lpThreadParameter + 18) = v7;
    if ( !v7 )
    {
      GetLastError();
      SetThreadPriority(CurrentThread, v6);
    }
  }
  v8 = CMMCSSOutputQueue::ThreadProc((CMMCSSOutputQueue *)lpThreadParameter);
  v9 = (void *)*((_QWORD *)lpThreadParameter + 18);
  v10 = v8;
  if ( v9 )
  {
    if ( !AvRevertMmThreadCharacteristics(v9) )
      GetLastError();
    *((_QWORD *)lpThreadParameter + 18) = 0;
  }
  if ( !v3 )
    CoUninitialize();
  return v10;
}

```

## disassembly

```asm
0x1800ba590  push    rbx
0x1800ba592  push    rbp
0x1800ba593  push    rsi
0x1800ba594  push    rdi
0x1800ba595  push    r14
0x1800ba597  push    r15
0x1800ba599  sub     rsp, 28h
0x1800ba59d  mov     rbx, rcx
0x1800ba5a0  call    ?CoInitializeHelper@CAMThread@@SAJXZ; CAMThread::CoInitializeHelper(void)
0x1800ba5a5  lea     rdi, [rbx+98h]
0x1800ba5ac  xor     r15d, r15d
0x1800ba5af  mov     esi, eax
0x1800ba5b1  cmp     [rdi], r15w
0x1800ba5b5  jz      short loc_1800BA61B
0x1800ba5b7  call    cs:__imp_GetCurrentThread
0x1800ba5be  nop     dword ptr [rax+rax+00h]
0x1800ba5c3  mov     rcx, rax; hThread
0x1800ba5c6  mov     rbp, rax
0x1800ba5c9  call    cs:__imp_GetThreadPriority
0x1800ba5d0  nop     dword ptr [rax+rax+00h]
0x1800ba5d5  lea     rdx, [rsp+58h+TaskIndex]; TaskIndex
0x1800ba5da  mov     [rsp+58h+TaskIndex], r15d
0x1800ba5df  mov     rcx, rdi; TaskName
0x1800ba5e2  mov     r14d, eax
0x1800ba5e5  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x1800ba5ec  nop     dword ptr [rax+rax+00h]
0x1800ba5f1  mov     [rbx+90h], rax
0x1800ba5f8  test    rax, rax
0x1800ba5fb  jnz     short loc_1800BA61B
0x1800ba5fd  call    cs:__imp_GetLastError
0x1800ba604  nop     dword ptr [rax+rax+00h]
0x1800ba609  mov     edx, r14d; nPriority
0x1800ba60c  mov     rcx, rbp; hThread
0x1800ba60f  call    cs:__imp_SetThreadPriority
0x1800ba616  nop     dword ptr [rax+rax+00h]
0x1800ba61b  mov     rcx, rbx; this
0x1800ba61e  call    ?ThreadProc@CMMCSSOutputQueue@@IEAAKXZ; CMMCSSOutputQueue::ThreadProc(void)
0x1800ba623  mov     rcx, [rbx+90h]; AvrtHandle
0x1800ba62a  mov     edi, eax
0x1800ba62c  test    rcx, rcx
0x1800ba62f  jz      short loc_1800BA654
0x1800ba631  call    cs:__imp_AvRevertMmThreadCharacteristics
0x1800ba638  nop     dword ptr [rax+rax+00h]
0x1800ba63d  test    eax, eax
0x1800ba63f  jnz     short loc_1800BA64D
0x1800ba641  call    cs:__imp_GetLastError
0x1800ba648  nop     dword ptr [rax+rax+00h]
0x1800ba64d  mov     [rbx+90h], r15
0x1800ba654  test    esi, esi
0x1800ba656  jnz     short loc_1800BA664
0x1800ba658  call    cs:__imp_CoUninitialize
0x1800ba65f  nop     dword ptr [rax+rax+00h]
0x1800ba664  mov     eax, edi
0x1800ba666  add     rsp, 28h
0x1800ba66a  pop     r15
0x1800ba66c  pop     r14
0x1800ba66e  pop     rdi
0x1800ba66f  pop     rsi
0x1800ba670  pop     rbp
0x1800ba671  pop     rbx
0x1800ba672  retn
```
