# CLogonTaskFramework::s_UpdatePCSettingsWork(CLogonTaskFramework *,LogonFrameworkTelemetry::LogonTask *)

- ea: `0x14001b2fc`
- end: `0x14001b4bc`
- name: `?s_UpdatePCSettingsWork@CLogonTaskFramework@@CAJPEAV1@PEAVLogonTask@LogonFrameworkTelemetry@@@Z`
- size: `448`
- prototype: `__int64 __fastcall(struct CLogonTaskFramework *, struct LogonFrameworkTelemetry::LogonTask *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140019540`
- `0x1401ad490`

## callees

- `0x14000d230`
- `0x14001b2c8`
- `0x14001b2fc`
- `0x14001c330`
- `0x1400b3a50`
- `0x1400baca0`
- `0x140145bc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001b3c7`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14001b38b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14001b38b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriorityBoost` at `0x14001b427`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriorityBoost` at `0x14001b427`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14001b412`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14001b412`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001b34c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14001b34c`

## string_xrefs

- `0x14001b3f6`: `shell\lib\logontasks\logontasks.cpp`
- `0x14001b458`: `shell\lib\logontasks\logontasks.cpp`
- `0x14001b497`: `updatePCSettings`

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
  signed int LastError; // eax
  int v11; // edx
  unsigned int v12; // r8d
  int v13; // eax
  unsigned int v14; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-20h]
  void **v17; // [rsp+30h] [rbp-10h] BYREF
  HANDLE hThread; // [rsp+38h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  DWORD ThreadId; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v21; // [rsp+80h] [rbp+40h] BYREF

  v2 = (*((_BYTE *)a1 + 216) & 2) == 0;
  ThreadId = 0;
  v5 = v2 || (*((_DWORD *)a1 + 55) & 0x100) != 0;
  v6 = CreateThread(0, 0, CLogonTaskFramework::s_UpdatePCSettingsThreadProc, (LPVOID)v5, 4u, &ThreadId);
  hThread = v6;
  v17 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( !v6 )
  {
    Error = ResultFromKnownLastError();
    v8 = Error;
    if ( Error < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1E9E,
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
    v13 = ResultFromKnownLastError();
    v8 = v13;
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1EA7,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v13,
        dwCreationFlags);
  }
  else
  {
    v8 = 0;
  }
  if ( !v5 )
  {
    v14 = SHProcessMessagesUntilEvent(v9, hThread, 0x1D4C0u);
    v2 = *((_BYTE *)a1 + 237) == 0;
    v21 = v14;
    if ( !v2 )
      LogonFrameworkTelemetry::LogonTask::WaitResult<unsigned short const (&)[17],unsigned long const &>(
        a2,
        L"updatePCSettings",
        &v21);
  }
LABEL_11:
  v17 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  if ( hThread
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v17) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v11, v12);
    __debugbreak();
  }
  return v8;
}

```

## disassembly

```asm
0x14001b2fc  mov     [rsp-28h+arg_8], rbx
0x14001b301  push    rbp
0x14001b302  push    rsi
0x14001b303  push    rdi
0x14001b304  push    r12
0x14001b306  push    r14
0x14001b308  mov     rbp, rsp
0x14001b30b  sub     rsp, 40h
0x14001b30f  test    byte ptr [rcx+0D8h], 2
0x14001b316  mov     r14, rdx
0x14001b319  mov     rsi, rcx
0x14001b31c  mov     [rbp+ThreadId], 0
0x14001b323  jnz     loc_14001B43C
0x14001b329  mov     dil, 1
0x14001b32c  lea     rax, [rbp+ThreadId]
0x14001b330  movzx   r9d, dil; lpParameter
0x14001b334  mov     [rsp+40h+lpThreadId], rax; lpThreadId
0x14001b339  lea     r8, ?s_UpdatePCSettingsThreadProc@CLogonTaskFramework@@CAKPEAX@Z; lpStartAddress
0x14001b340  xor     edx, edx; dwStackSize
0x14001b342  mov     [rsp+40h+dwCreationFlags], 4; int
0x14001b34a  xor     ecx, ecx; lpThreadAttributes
0x14001b34c  call    cs:__imp_CreateThread
0x14001b353  nop     dword ptr [rax+rax+00h]
0x14001b358  mov     [rbp+hThread], rax
0x14001b35c  lea     r12, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x14001b363  mov     [rbp+var_10], r12
0x14001b367  test    rax, rax
0x14001b36a  jnz     short loc_14001B37F
0x14001b36c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001b371  mov     ebx, eax
0x14001b373  test    eax, eax
0x14001b375  js      loc_14001B454
0x14001b37b  mov     rax, [rbp+hThread]
0x14001b37f  test    dil, dil
0x14001b382  jnz     loc_14001B40C
0x14001b388  mov     rcx, rax; hThread
0x14001b38b  call    cs:__imp_ResumeThread
0x14001b392  nop     dword ptr [rax+rax+00h]
0x14001b397  cmp     eax, 0FFFFFFFFh
0x14001b39a  jz      short loc_14001B3E7
0x14001b39c  xor     ebx, ebx
0x14001b39e  test    dil, dil
0x14001b3a1  jz      loc_14001B471
0x14001b3a7  cmp     [rbp+hThread], 0
0x14001b3ac  mov     [rbp+var_10], r12
0x14001b3b0  jz      loc_14001B4A8
0x14001b3b6  lea     rcx, [rbp+var_10]
0x14001b3ba  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x14001b3bf  test    al, al
0x14001b3c1  jnz     loc_14001B4A8
0x14001b3c7  call    cs:__imp_GetLastError
0x14001b3ce  nop     dword ptr [rax+rax+00h]
0x14001b3d3  test    eax, eax
0x14001b3d5  jle     short loc_14001B3DF
0x14001b3d7  movzx   eax, ax
0x14001b3da  or      eax, 80070000h
0x14001b3df  mov     ecx, eax; this
0x14001b3e1  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14001b3e6  int     3; Trap to Debugger
0x14001b3e7  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14001b3ec  mov     ebx, eax
0x14001b3ee  test    eax, eax
0x14001b3f0  jns     short loc_14001B39E
0x14001b3f2  mov     rcx, [rbp+28h]; this
0x14001b3f6  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14001b3fd  mov     r9d, eax; char *
0x14001b400  mov     edx, 1EA7h; void *
0x14001b405  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001b40a  jmp     short loc_14001B39E
0x14001b40c  or      edx, 0FFFFFFFFh; nPriority
0x14001b40f  mov     rcx, rax; hThread
0x14001b412  call    cs:__imp_SetThreadPriority
0x14001b419  nop     dword ptr [rax+rax+00h]
0x14001b41e  mov     rcx, [rbp+hThread]; hThread
0x14001b422  mov     edx, 1; bDisablePriorityBoost
0x14001b427  call    cs:__imp_SetThreadPriorityBoost
0x14001b42e  nop     dword ptr [rax+rax+00h]
0x14001b433  mov     rax, [rbp+hThread]
0x14001b437  jmp     loc_14001B388
0x14001b43c  test    dword ptr [rcx+0DCh], 100h
0x14001b446  jnz     loc_14001B329
0x14001b44c  xor     dil, dil
0x14001b44f  jmp     loc_14001B32C
0x14001b454  mov     rcx, [rbp+28h]; this
0x14001b458  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14001b45f  mov     r9d, eax; char *
0x14001b462  mov     edx, 1E9Eh; void *
0x14001b467  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001b46c  jmp     loc_14001B3A7
0x14001b471  mov     rdx, [rbp+hThread]; void *
0x14001b475  mov     r8d, 1D4C0h; unsigned int
0x14001b47b  call    ?SHProcessMessagesUntilEvent@@YAKPEAUHWND__@@PEAXK@Z; SHProcessMessagesUntilEvent(HWND__ *,void *,ulong)
0x14001b480  cmp     byte ptr [rsi+0EDh], 0
0x14001b487  mov     [rbp+arg_10], eax
0x14001b48a  jz      loc_14001B3A7
0x14001b490  lea     r8, [rbp+arg_10]
0x14001b494  mov     rcx, r14
0x14001b497  lea     rdx, aUpdatepcsettin_0; "updatePCSettings"
0x14001b49e  call    ??$WaitResult@AEAY0BB@$$CBGAEBK@LogonTask@LogonFrameworkTelemetry@@QEAAXAEAY0BB@$$CBGAEBK@Z; LogonFrameworkTelemetry::LogonTask::WaitResult<ushort const (&)[17],ulong const &>(ushort const (&)[17],ulong const &)
0x14001b4a3  jmp     loc_14001B3A7
0x14001b4a8  mov     eax, ebx
0x14001b4aa  mov     rbx, [rsp+40h+arg_8]
0x14001b4af  add     rsp, 40h
0x14001b4b3  pop     r14
0x14001b4b5  pop     r12
0x14001b4b7  pop     rdi
0x14001b4b8  pop     rsi
0x14001b4b9  pop     rbp
0x14001b4ba  retn
```
