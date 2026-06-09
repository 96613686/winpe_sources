# CConnection::StartCompositionThread(int)

- ea: `0x18015b074`
- end: `0x18015b1d6`
- name: `?StartCompositionThread@CConnection@@IEAAJH@Z`
- size: `354`
- prototype: `__int64 __fastcall(CConnection *__hidden this, int nPriority)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18022fe00`

## callees

- `0x18015adb4`
- `0x18015b074`
- `0x180200500`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18015b0a0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18015b0a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015b1c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18015b1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015b1b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015b1b1`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18015b166`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18015b166`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18015b14e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18015b14e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18015b105`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18015b105`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015b1bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015b1bc`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18015b141`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18015b141`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18015b193`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18015b193`

## string_xrefs

- `0x18015b137`: `DWM Compositor Thread`

## pseudocode

```c
__int64 __fastcall CConnection::StartCompositionThread(HANDLE *this, int nPriority)
{
  HANDLE *v3; // r14
  HANDLE EventW; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  HANDLE v9; // rax
  char *v10; // rbp
  void *v11; // rsi
  DWORD LastError; // ebx
  HANDLE Handles[9]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  DWORD ThreadId; // [rsp+80h] [rbp+8h] BYREF

  ThreadId = 0;
  v3 = this + 5;
  EventW = CreateEventW(0, 1, 0, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v3,
    EventW);
  if ( (((unsigned __int64)*v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v7 = 170;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\connection.cpp",
             v6);
  }
  v9 = CreateThread(0, 0, CConnection::CompositionThreadEntryPoint, this, 4u, &ThreadId);
  v10 = (char *)this[4];
  v11 = v9;
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v10);
    SetLastError(LastError);
  }
  this[4] = v11;
  if ( (((unsigned __int64)v11 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v7 = 179;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\connection.cpp",
             v6);
  }
  SetThreadDescription(v11, L"DWM Compositor Thread");
  if ( !SetThreadPriority(this[4], nPriority) )
  {
    v7 = 184;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\connection.cpp",
             v6);
  }
  if ( ResumeThread(this[4]) == -1 )
  {
    v7 = 188;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\connection.cpp",
             v6);
  }
  Handles[0] = this[4];
  Handles[1] = *v3;
  if ( WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF) == -1 )
  {
    v7 = 193;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v7,
             (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\connection.cpp",
             v6);
  }
  return 0;
}

```

## disassembly

```asm
0x18015b074  mov     rax, rsp
0x18015b077  push    rbx
0x18015b078  push    rbp
0x18015b079  push    rsi
0x18015b07a  push    rdi
0x18015b07b  push    r14
0x18015b07d  push    r15
0x18015b07f  sub     rsp, 48h
0x18015b083  xor     r9d, r9d; lpName
0x18015b086  mov     dword ptr [rax+8], 0
0x18015b08d  mov     r15d, edx
0x18015b090  lea     r14, [rcx+28h]
0x18015b094  mov     rdi, rcx
0x18015b097  xor     r8d, r8d; bInitialState
0x18015b09a  xor     ecx, ecx; lpEventAttributes
0x18015b09c  lea     edx, [r9+1]; bManualReset
0x18015b0a0  call    cs:__imp_CreateEventW
0x18015b0a6  mov     rdx, rax
0x18015b0a9  mov     rcx, r14
0x18015b0ac  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18015b0b1  mov     rax, [r14]
0x18015b0b4  inc     rax
0x18015b0b7  test    rax, 0FFFFFFFFFFFFFFFEh
0x18015b0bd  jnz     short loc_18015B0E2
0x18015b0bf  mov     edx, 0AAh; void *
0x18015b0c4  mov     rcx, [rsp+78h]; this
0x18015b0c9  lea     r8, aOnecoreuapWind_59; "onecoreuap\\windows\\dwm\\dwmcore\\engi"...
0x18015b0d0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18015b0d5  add     rsp, 48h
0x18015b0d9  pop     r15
0x18015b0db  pop     r14
0x18015b0dd  pop     rdi
0x18015b0de  pop     rsi
0x18015b0df  pop     rbp
0x18015b0e0  pop     rbx
0x18015b0e1  retn
0x18015b0e2  lea     rax, [rsp+78h+ThreadId]
0x18015b0ea  mov     r9, rdi; lpParameter
0x18015b0ed  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x18015b0f2  lea     r8, ?CompositionThreadEntryPoint@CConnection@@CAKPEAX@Z; lpStartAddress
0x18015b0f9  xor     edx, edx; dwStackSize
0x18015b0fb  mov     [rsp+78h+dwCreationFlags], 4; dwCreationFlags
0x18015b103  xor     ecx, ecx; lpThreadAttributes
0x18015b105  call    cs:__imp_CreateThread
0x18015b10b  mov     rbp, [rdi+20h]
0x18015b10f  mov     rsi, rax
0x18015b112  lea     rdx, [rbp-1]
0x18015b116  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18015b11a  jbe     loc_18015B1B1
0x18015b120  lea     rax, [rsi+1]
0x18015b124  mov     [rdi+20h], rsi
0x18015b128  test    rax, 0FFFFFFFFFFFFFFFEh
0x18015b12e  jnz     short loc_18015B137
0x18015b130  mov     edx, 0B3h
0x18015b135  jmp     short loc_18015B0C4
0x18015b137  lea     rdx, ThreadDescription; "DWM Compositor Thread"
0x18015b13e  mov     rcx, rsi; hThread
0x18015b141  call    cs:__imp_SetThreadDescription
0x18015b147  mov     rcx, [rdi+20h]; hThread
0x18015b14b  mov     edx, r15d; nPriority
0x18015b14e  call    cs:__imp_SetThreadPriority
0x18015b154  test    eax, eax
0x18015b156  jnz     short loc_18015B162
0x18015b158  mov     edx, 0B8h
0x18015b15d  jmp     loc_18015B0C4
0x18015b162  mov     rcx, [rdi+20h]; hThread
0x18015b166  call    cs:__imp_ResumeThread
0x18015b16c  or      ebx, 0FFFFFFFFh
0x18015b16f  cmp     eax, ebx
0x18015b171  jz      short loc_18015B1A7
0x18015b173  mov     rax, [rdi+20h]
0x18015b177  lea     rdx, [rsp+78h+Handles]; lpHandles
0x18015b17c  xor     r8d, r8d; bWaitAll
0x18015b17f  mov     [rsp+78h+Handles], rax
0x18015b184  mov     rax, [r14]
0x18015b187  mov     r9d, ebx; dwMilliseconds
0x18015b18a  mov     [rsp+78h+var_40], rax
0x18015b18f  lea     ecx, [r8+2]; nCount
0x18015b193  call    cs:__imp_WaitForMultipleObjects
0x18015b199  cmp     eax, ebx
0x18015b19b  jnz     short loc_18015B1CF
0x18015b19d  mov     edx, 0C1h
0x18015b1a2  jmp     loc_18015B0C4
0x18015b1a7  mov     edx, 0BCh
0x18015b1ac  jmp     loc_18015B0C4
0x18015b1b1  call    cs:__imp_GetLastError
0x18015b1b7  mov     rcx, rbp; hObject
0x18015b1ba  mov     ebx, eax
0x18015b1bc  call    cs:__imp_CloseHandle
0x18015b1c2  mov     ecx, ebx; dwErrCode
0x18015b1c4  call    cs:__imp_SetLastError
0x18015b1ca  jmp     loc_18015B120
0x18015b1cf  xor     eax, eax
0x18015b1d1  jmp     loc_18015B0D5
```
