# PushRouter::Deinitialize(void)

- ea: `0x180014040`
- end: `0x18001416b`
- name: `?Deinitialize@PushRouter@@AEAAJXZ`
- size: `299`
- prototype: `__int64 __fastcall(PushRouter *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180013c24`
- `0x180014dcc`

## callees

- `0x180003a14`
- `0x180014040`
- `0x180014174`
- `0x18001b078`
- `0x18001c2d8`
- `0x18001c6c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800140a4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x1800140a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014086`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001414d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014086`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800140c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001414d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800140ed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800140ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014079`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180014079`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800140da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800140da`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014068`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014068`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800140f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014107`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800140f6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014107`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PushRouter::Deinitialize(PushRouter *this)
{
  void *v2; // rcx
  HANDLE *v3; // rbx
  CPushrouterLogger *Logger; // rax
  void *v5; // rcx
  PushMsgAuthModule *v6; // rbx
  void *v7; // rcx
  DWORD ExitCode; // [rsp+30h] [rbp+8h] BYREF

  ExitCode = 0;
  v2 = (void *)*((_QWORD *)this + 25);
  v3 = (HANDLE *)((char *)this + 184);
  if ( v2 )
  {
    SetEvent(v2);
    if ( *v3 )
      WaitForSingleObject(*v3, 0xFFFFFFFF);
    CloseHandle(*((HANDLE *)this + 25));
    *((_QWORD *)this + 25) = 0;
  }
  if ( *v3 )
  {
    if ( GetExitCodeThread(*v3, &ExitCode) && ExitCode )
    {
      Logger = CPushrouterLogger::GetLogger();
      CPushrouterLogger::LogPushRouterRoutingThreadAbandoned(Logger, ExitCode);
    }
    CloseHandle(*v3);
    *v3 = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  CTList<PushClient>::DeleteAll((char *)this + 24);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  LocalFree(*(HLOCAL *)this);
  v5 = (void *)*((_QWORD *)this + 1);
  *(_QWORD *)this = 0;
  LocalFree(v5);
  v6 = (PushMsgAuthModule *)*((_QWORD *)this + 26);
  *((_QWORD *)this + 1) = 0;
  if ( v6 )
  {
    PushMsgAuthModule::~PushMsgAuthModule(v6);
    operator delete(v6, (const struct std::nothrow_t *)0x18);
  }
  v7 = (void *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 26) = 0;
  if ( v7 )
  {
    CloseHandle(v7);
    *((_QWORD *)this + 22) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180014040  mov     [rsp+arg_8], rbx
0x180014045  push    rdi
0x180014046  sub     rsp, 20h
0x18001404a  mov     rdi, rcx
0x18001404d  mov     [rsp+28h+ExitCode], 0
0x180014055  mov     rcx, [rcx+0C8h]; hEvent
0x18001405c  lea     rbx, [rdi+0B8h]
0x180014063  test    rcx, rcx
0x180014066  jz      short loc_180014097
0x180014068  call    cs:__imp_SetEvent
0x18001406e  mov     rcx, [rbx]; hHandle
0x180014071  test    rcx, rcx
0x180014074  jz      short loc_18001407F
0x180014076  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180014079  call    cs:__imp_WaitForSingleObject
0x18001407f  mov     rcx, [rdi+0C8h]; hObject
0x180014086  call    cs:__imp_CloseHandle
0x18001408c  mov     qword ptr [rdi+0C8h], 0
0x180014097  mov     rcx, [rbx]; hThread
0x18001409a  test    rcx, rcx
0x18001409d  jz      short loc_1800140D6
0x18001409f  lea     rdx, [rsp+28h+ExitCode]; lpExitCode
0x1800140a4  call    cs:__imp_GetExitCodeThread
0x1800140aa  test    eax, eax
0x1800140ac  jz      short loc_1800140C6
0x1800140ae  cmp     [rsp+28h+ExitCode], 0
0x1800140b3  jz      short loc_1800140C6
0x1800140b5  call    ?GetLogger@CPushrouterLogger@@SAPEAV1@XZ; CPushrouterLogger::GetLogger(void)
0x1800140ba  mov     edx, [rsp+28h+ExitCode]; unsigned int
0x1800140be  mov     rcx, rax; this
0x1800140c1  call    ?LogPushRouterRoutingThreadAbandoned@CPushrouterLogger@@QEAAXK@Z; CPushrouterLogger::LogPushRouterRoutingThreadAbandoned(ulong)
0x1800140c6  mov     rcx, [rbx]; hObject
0x1800140c9  call    cs:__imp_CloseHandle
0x1800140cf  mov     qword ptr [rbx], 0
0x1800140d6  lea     rcx, [rdi+38h]; lpCriticalSection
0x1800140da  call    cs:__imp_EnterCriticalSection
0x1800140e0  lea     rcx, [rdi+18h]
0x1800140e4  call    ?DeleteAll@?$CTList@VPushClient@@@@QEAAXXZ; CTList<PushClient>::DeleteAll(void)
0x1800140e9  lea     rcx, [rdi+38h]; lpCriticalSection
0x1800140ed  call    cs:__imp_LeaveCriticalSection
0x1800140f3  mov     rcx, [rdi]; hMem
0x1800140f6  call    cs:__imp_LocalFree
0x1800140fc  mov     rcx, [rdi+8]; hMem
0x180014100  mov     qword ptr [rdi], 0
0x180014107  call    cs:__imp_LocalFree
0x18001410d  mov     rbx, [rdi+0D0h]
0x180014114  mov     qword ptr [rdi+8], 0
0x18001411c  test    rbx, rbx
0x18001411f  jz      short loc_180014136
0x180014121  mov     rcx, rbx; this
0x180014124  call    ??1PushMsgAuthModule@@QEAA@XZ; PushMsgAuthModule::~PushMsgAuthModule(void)
0x180014129  mov     edx, 18h; struct std::nothrow_t *
0x18001412e  mov     rcx, rbx; void *
0x180014131  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014136  mov     rcx, [rdi+0B0h]; hObject
0x18001413d  mov     qword ptr [rdi+0D0h], 0
0x180014148  test    rcx, rcx
0x18001414b  jz      short loc_18001415E
0x18001414d  call    cs:__imp_CloseHandle
0x180014153  mov     qword ptr [rdi+0B0h], 0
0x18001415e  mov     rbx, [rsp+28h+arg_8]
0x180014163  xor     eax, eax
0x180014165  add     rsp, 20h
0x180014169  pop     rdi
0x18001416a  retn
```
