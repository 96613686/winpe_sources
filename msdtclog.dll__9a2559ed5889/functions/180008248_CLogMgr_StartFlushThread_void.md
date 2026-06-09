# CLogMgr::_StartFlushThread(void)

- ea: `0x180008248`
- end: `0x1800084c2`
- name: `?_StartFlushThread@CLogMgr@@AEAAXXZ`
- size: `634`
- prototype: `void __fastcall(CLogMgr *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800047b0`
- `0x180004a00`

## callees

- `0x18000651c`
- `0x180008248`
- `0x18001266c`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000840e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000845a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000848e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000840e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008440`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000845a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000848e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084a8`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800082c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800082e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008307`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008327`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800082c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x1800082e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008307`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180008327`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800083c8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800083c8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800083e6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800083e6`

## pseudocode

```c
void __fastcall CLogMgr::_StartFlushThread(CLogMgr *this)
{
  char *v2; // rdi
  HANDLE EventA; // rax
  HANDLE v4; // rax
  HANDLE v5; // rax
  HANDLE v6; // rcx
  HANDLE Thread; // rax
  ulong pExceptionObject; // [rsp+40h] [rbp+10h] BYREF

  if ( !this )
  {
    pExceptionObject = -2147418113;
    throw (long *)&pExceptionObject;
  }
  v2 = (char *)this + 408;
  (**((void (__fastcall ***)(char *))this + 51))((char *)this + 408);
  *((_DWORD *)this + 145) = 0;
  if ( *((_DWORD *)this + 72) )
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  }
  else
  {
    *((_DWORD *)this + 72) = 1;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
    EventA = CreateEventA(0, 0, 0, 0);
    *((_QWORD *)this + 68) = EventA;
    if ( !EventA )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
    v4 = CreateEventA(0, 0, 0, 0);
    *((_QWORD *)this + 69) = v4;
    if ( !v4 )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
    v5 = CreateEventA(0, 0, 0, 0);
    *((_QWORD *)this + 70) = v5;
    if ( !v5 )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
    v6 = CreateEventA(0, 0, 0, 0);
    *((_QWORD *)this + 71) = v6;
    if ( !v6 )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
    *((_QWORD *)this + 64) = *((_QWORD *)this + 68);
    *((_QWORD *)this + 65) = *((_QWORD *)this + 69);
    *((_QWORD *)this + 66) = *((_QWORD *)this + 70);
    *((_QWORD *)this + 67) = v6;
    *((_QWORD *)this + 76) = CLogMgr::Get64BitTickCount() + *((unsigned int *)this + 126);
    *((_QWORD *)this + 75) = CLogMgr::Get64BitTickCount() + *((unsigned int *)this + 125);
    *((_QWORD *)this + 73) = 0;
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)_FlushThread, this, 0, (LPDWORD)this + 148);
    *((_QWORD *)this + 73) = Thread;
    if ( !Thread )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
    if ( !SetThreadPriority(Thread, 1) )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
    g_hFlushThread = (HANDLE)*((_QWORD *)this + 73);
  }
}

```

## disassembly

```asm
0x180008248  mov     [rsp-8+arg_8], rbx
0x18000824d  mov     [rsp-8+arg_10], rdi
0x180008252  push    rbp
0x180008253  mov     rbp, rsp
0x180008256  sub     rsp, 30h
0x18000825a  mov     rbx, rcx
0x18000825d  test    rcx, rcx
0x180008260  jz      loc_180008428
0x180008266  lea     rdi, [rcx+198h]
0x18000826d  mov     rax, [rdi]
0x180008270  mov     rcx, rdi
0x180008273  mov     rax, [rax]
0x180008276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000827b  mov     dword ptr [rbx+244h], 0
0x180008285  cmp     dword ptr [rbx+120h], 0
0x18000828c  jz      short loc_1800082A3
0x18000828e  mov     rax, [rdi]
0x180008291  mov     rcx, rdi
0x180008294  mov     rax, [rax+8]
0x180008298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000829d  nop
0x18000829e  jmp     loc_1800083FE
0x1800082a3  mov     dword ptr [rbx+120h], 1
0x1800082ad  mov     rax, [rdi]
0x1800082b0  mov     rcx, rdi
0x1800082b3  mov     rax, [rax+8]
0x1800082b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082bc  nop
0x1800082bd  xor     r9d, r9d; lpName
0x1800082c0  xor     r8d, r8d; bInitialState
0x1800082c3  xor     edx, edx; bManualReset
0x1800082c5  xor     ecx, ecx; lpEventAttributes
0x1800082c7  call    cs:__imp_CreateEventA
0x1800082cd  mov     [rbx+220h], rax
0x1800082d4  test    rax, rax
0x1800082d7  jz      loc_180008440
0x1800082dd  xor     r9d, r9d; lpName
0x1800082e0  xor     r8d, r8d; bInitialState
0x1800082e3  xor     edx, edx; bManualReset
0x1800082e5  xor     ecx, ecx; lpEventAttributes
0x1800082e7  call    cs:__imp_CreateEventA
0x1800082ed  mov     [rbx+228h], rax
0x1800082f4  test    rax, rax
0x1800082f7  jz      loc_18000845A
0x1800082fd  xor     r9d, r9d; lpName
0x180008300  xor     r8d, r8d; bInitialState
0x180008303  xor     edx, edx; bManualReset
0x180008305  xor     ecx, ecx; lpEventAttributes
0x180008307  call    cs:__imp_CreateEventA
0x18000830d  mov     [rbx+230h], rax
0x180008314  test    rax, rax
0x180008317  jz      loc_180008474
0x18000831d  xor     r9d, r9d; lpName
0x180008320  xor     r8d, r8d; bInitialState
0x180008323  xor     edx, edx; bManualReset
0x180008325  xor     ecx, ecx; lpEventAttributes
0x180008327  call    cs:__imp_CreateEventA
0x18000832d  mov     rcx, rax
0x180008330  mov     [rbx+238h], rax
0x180008337  test    rax, rax
0x18000833a  jz      loc_18000848E
0x180008340  mov     rax, [rbx+220h]
0x180008347  mov     [rbx+200h], rax
0x18000834e  mov     rax, [rbx+228h]
0x180008355  mov     [rbx+208h], rax
0x18000835c  mov     rax, [rbx+230h]
0x180008363  mov     [rbx+210h], rax
0x18000836a  mov     [rbx+218h], rcx
0x180008371  call    ?Get64BitTickCount@CLogMgr@@SA_KXZ; CLogMgr::Get64BitTickCount(void)
0x180008376  mov     ecx, [rbx+1F8h]
0x18000837c  add     rcx, rax
0x18000837f  mov     [rbx+260h], rcx
0x180008386  call    ?Get64BitTickCount@CLogMgr@@SA_KXZ; CLogMgr::Get64BitTickCount(void)
0x18000838b  mov     ecx, [rbx+1F4h]
0x180008391  add     rcx, rax
0x180008394  mov     [rbx+258h], rcx
0x18000839b  mov     qword ptr [rbx+248h], 0
0x1800083a6  lea     rax, [rbx+250h]
0x1800083ad  mov     [rsp+30h+lpThreadId], rax; lpThreadId
0x1800083b2  mov     [rsp+30h+dwCreationFlags], 0; dwCreationFlags
0x1800083ba  mov     r9, rbx; lpParameter
0x1800083bd  lea     r8, ?_FlushThread@@YAKPEAK@Z; lpStartAddress
0x1800083c4  xor     edx, edx; dwStackSize
0x1800083c6  xor     ecx, ecx; lpThreadAttributes
0x1800083c8  call    cs:__imp_CreateThread
0x1800083ce  mov     [rbx+248h], rax
0x1800083d5  test    rax, rax
0x1800083d8  jz      loc_1800084A8
0x1800083de  mov     edx, 1; nPriority
0x1800083e3  mov     rcx, rax; hThread
0x1800083e6  call    cs:__imp_SetThreadPriority
0x1800083ec  test    eax, eax
0x1800083ee  jz      short loc_18000840E
0x1800083f0  mov     rax, [rbx+248h]
0x1800083f7  mov     cs:?g_hFlushThread@@3PEAXEA, rax; void * g_hFlushThread
0x1800083fe  mov     rbx, [rsp+30h+arg_8]
0x180008403  mov     rdi, [rsp+30h+arg_10]
0x180008408  add     rsp, 30h
0x18000840c  pop     rbp
0x18000840d  retn
0x18000840e  call    cs:__imp_GetLastError
0x180008414  mov     [rbp+pExceptionObject], eax
0x180008417  lea     rdx, _TI1K; pThrowInfo
0x18000841e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180008422  call    _CxxThrowException_0
0x180008428  mov     [rbp+pExceptionObject], 8000FFFFh
0x18000842f  lea     rdx, _TI1J; pThrowInfo
0x180008436  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000843a  call    _CxxThrowException_0
0x180008440  call    cs:__imp_GetLastError
0x180008446  mov     [rbp+pExceptionObject], eax
0x180008449  lea     rdx, _TI1K; pThrowInfo
0x180008450  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180008454  call    _CxxThrowException_0
0x18000845a  call    cs:__imp_GetLastError
0x180008460  mov     [rbp+pExceptionObject], eax
0x180008463  lea     rdx, _TI1K; pThrowInfo
0x18000846a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000846e  call    _CxxThrowException_0
0x180008474  call    cs:__imp_GetLastError
0x18000847a  mov     [rbp+pExceptionObject], eax
0x18000847d  lea     rdx, _TI1K; pThrowInfo
0x180008484  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180008488  call    _CxxThrowException_0
0x18000848e  call    cs:__imp_GetLastError
0x180008494  mov     [rbp+pExceptionObject], eax
0x180008497  lea     rdx, _TI1K; pThrowInfo
0x18000849e  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800084a2  call    _CxxThrowException_0
0x1800084a8  call    cs:__imp_GetLastError
0x1800084ae  mov     [rbp+pExceptionObject], eax
0x1800084b1  lea     rdx, _TI1K; pThrowInfo
0x1800084b8  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800084bc  call    _CxxThrowException_0
```
