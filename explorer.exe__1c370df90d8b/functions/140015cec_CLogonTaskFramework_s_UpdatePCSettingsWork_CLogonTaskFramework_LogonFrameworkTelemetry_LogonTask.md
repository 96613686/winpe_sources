# CLogonTaskFramework::s_UpdatePCSettingsWork(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x140015cec`
- end: `0x140015e98`
- name: `?s_UpdatePCSettingsWork@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14008d470`
- `0x1401ad140`

## callees

- `0x14000c3a4`
- `0x14000f1a0`
- `0x140015cec`
- `0x140016b10`
- `0x14001eba8`
- `0x140139974`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140015dc9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140015dc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015dab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140015dab`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140015d3c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140015d3c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140015dfb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140015dfb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriorityBoost` at `0x140015e0a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriorityBoost` at `0x140015e0a`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140015d75`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x140015d75`

## string_xrefs

- `0x140015ddf`: `shell\lib\logontasks\logontasks.cpp`
- `0x140015e35`: `shell\lib\logontasks\logontasks.cpp`
- `0x140015e74`: `updatePCSettings`

## pseudocode

```c
__int64 __fastcall CLogonTaskFramework::s_UpdatePCSettingsWork(
        struct CLogonTaskFramework *a1,
        struct LogonFrameworkTelemetry::LogonTask *a2)
{
  bool v2; // zf
  bool v5; // di
  HANDLE v6; // rax
  int Error; // eax
  unsigned int v8; // ebx
  HWND v9; // rcx
  int LastError; // eax
  int v11; // eax
  unsigned int v12; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-20h]
  const int *v15; // [rsp+30h] [rbp-10h] BYREF
  HANDLE hThread; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD ThreadId; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v19; // [rsp+80h] [rbp+40h] BYREF

  v2 = (*((_BYTE *)a1 + 216) & 2) == 0;
  ThreadId = 0;
  v5 = v2 || (*((_DWORD *)a1 + 55) & 0x100) != 0;
  v6 = CreateThread(0, 0, CLogonTaskFramework::s_UpdatePCSettingsThreadProc, (LPVOID)v5, 4u, &ThreadId);
  hThread = v6;
  v15 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( !v6 )
  {
    Error = ResultFromKnownLastError();
    v8 = Error;
    if ( Error < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1E84,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)Error,
        dwCreationFlags);
      goto LABEL_11;
    }
    v6 = hThread;
  }
  if ( v5 )
  {
    SetThreadPriority(v6, -1);
    SetThreadPriorityBoost(hThread, 1);
    v6 = hThread;
  }
  if ( ResumeThread(v6) == -1 )
  {
    v11 = ResultFromKnownLastError();
    v8 = v11;
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1E8D,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v11,
        dwCreationFlags);
  }
  else
  {
    v8 = 0;
  }
  if ( !v5 )
  {
    v12 = SHProcessMessagesUntilEvent(v9, hThread, 0x1D4C0u);
    v2 = *((_BYTE *)a1 + 237) == 0;
    v19 = v12;
    if ( !v2 )
      LogonFrameworkTelemetry::LogonTask::WaitResult<unsigned short const (&)[17],unsigned long const &>(
        a2,
        L"updatePCSettings",
        &v19);
  }
LABEL_11:
  v15 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( hThread
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v15) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
  return v8;
}

```

## disassembly

```asm
0x140015cec  mov     [rsp-28h+arg_8], rbx
0x140015cf1  push    rbp
0x140015cf2  push    rsi
0x140015cf3  push    rdi
0x140015cf4  push    r13
0x140015cf6  push    r14
0x140015cf8  mov     rbp, rsp
0x140015cfb  sub     rsp, 40h
0x140015cff  test    byte ptr [rcx+0D8h], 2
0x140015d06  mov     r14, rdx
0x140015d09  mov     rsi, rcx
0x140015d0c  mov     [rbp+ThreadId], 0
0x140015d13  jnz     loc_140015E19
0x140015d19  mov     dil, 1
0x140015d1c  lea     rax, [rbp+ThreadId]
0x140015d20  movzx   r9d, dil; lpParameter
0x140015d24  mov     [rsp+40h+lpThreadId], rax; lpThreadId
0x140015d29  lea     r8, ?s_UpdatePCSettingsThreadProc@CLogonTaskFramework@@CAKPEAX@Z; lpStartAddress
0x140015d30  xor     edx, edx; dwStackSize
0x140015d32  mov     [rsp+40h+dwCreationFlags], 4; int
0x140015d3a  xor     ecx, ecx; lpThreadAttributes
0x140015d3c  call    cs:__imp_CreateThread
0x140015d42  mov     [rbp+hThread], rax
0x140015d46  lea     r13, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x140015d4d  mov     [rbp+var_10], r13
0x140015d51  test    rax, rax
0x140015d54  jnz     short loc_140015D69
0x140015d56  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140015d5b  mov     ebx, eax
0x140015d5d  test    eax, eax
0x140015d5f  js      loc_140015E31
0x140015d65  mov     rax, [rbp+hThread]
0x140015d69  test    dil, dil
0x140015d6c  jnz     loc_140015DF5
0x140015d72  mov     rcx, rax; hThread
0x140015d75  call    cs:__imp_ResumeThread
0x140015d7b  cmp     eax, 0FFFFFFFFh
0x140015d7e  jz      short loc_140015DD0
0x140015d80  xor     ebx, ebx
0x140015d82  test    dil, dil
0x140015d85  jz      loc_140015E4E
0x140015d8b  cmp     [rbp+hThread], 0
0x140015d90  mov     [rbp+var_10], r13
0x140015d94  jz      loc_140015E85
0x140015d9a  lea     rcx, [rbp+var_10]
0x140015d9e  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x140015da3  test    al, al
0x140015da5  jnz     loc_140015E85
0x140015dab  call    cs:__imp_GetLastError
0x140015db1  test    eax, eax
0x140015db3  jle     short loc_140015DBD
0x140015db5  movzx   eax, ax
0x140015db8  or      eax, 80070000h
0x140015dbd  xor     r9d, r9d; lpArguments
0x140015dc0  xor     r8d, r8d; nNumberOfArguments
0x140015dc3  mov     ecx, eax; dwExceptionCode
0x140015dc5  lea     edx, [r9+1]; dwExceptionFlags
0x140015dc9  call    cs:__imp_RaiseException
0x140015dcf  int     3; Trap to Debugger
0x140015dd0  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140015dd5  mov     ebx, eax
0x140015dd7  test    eax, eax
0x140015dd9  jns     short loc_140015D82
0x140015ddb  mov     rcx, [rbp+28h]; this
0x140015ddf  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140015de6  mov     r9d, eax; char *
0x140015de9  mov     edx, 1E8Dh; void *
0x140015dee  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140015df3  jmp     short loc_140015D82
0x140015df5  or      edx, 0FFFFFFFFh; nPriority
0x140015df8  mov     rcx, rax; hThread
0x140015dfb  call    cs:__imp_SetThreadPriority
0x140015e01  mov     rcx, [rbp+hThread]; hThread
0x140015e05  mov     edx, 1; bDisablePriorityBoost
0x140015e0a  call    cs:__imp_SetThreadPriorityBoost
0x140015e10  mov     rax, [rbp+hThread]
0x140015e14  jmp     loc_140015D72
0x140015e19  test    dword ptr [rcx+0DCh], 100h
0x140015e23  jnz     loc_140015D19
0x140015e29  xor     dil, dil
0x140015e2c  jmp     loc_140015D1C
0x140015e31  mov     rcx, [rbp+28h]; this
0x140015e35  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140015e3c  mov     r9d, eax; char *
0x140015e3f  mov     edx, 1E84h; void *
0x140015e44  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140015e49  jmp     loc_140015D8B
0x140015e4e  mov     rdx, [rbp+hThread]; void *
0x140015e52  mov     r8d, 1D4C0h; unsigned int
0x140015e58  call    ?SHProcessMessagesUntilEvent@@YAKPEAUHWND__@@PEAXK@Z; SHProcessMessagesUntilEvent(HWND__ *,void *,ulong)
0x140015e5d  cmp     byte ptr [rsi+0EDh], 0
0x140015e64  mov     [rbp+arg_10], eax
0x140015e67  jz      loc_140015D8B
0x140015e6d  lea     r8, [rbp+arg_10]
0x140015e71  mov     rcx, r14
0x140015e74  lea     rdx, aUpdatepcsettin_0; "updatePCSettings"
0x140015e7b  call    ??$WaitResult@AEAY0BB@$$CBGAEBK@LogonTask@LogonFrameworkTelemetry@@QEAAXAEAY0BB@$$CBGAEBK@Z; LogonFrameworkTelemetry::LogonTask::WaitResult<ushort const (&)[17],ulong const &>(ushort const (&)[17],ulong const &)
0x140015e80  jmp     loc_140015D8B
0x140015e85  mov     eax, ebx
0x140015e87  mov     rbx, [rsp+40h+arg_8]
0x140015e8c  add     rsp, 40h
0x140015e90  pop     r14
0x140015e92  pop     r13
0x140015e94  pop     rdi
0x140015e95  pop     rsi
0x140015e96  pop     rbp
0x140015e97  retn
```
