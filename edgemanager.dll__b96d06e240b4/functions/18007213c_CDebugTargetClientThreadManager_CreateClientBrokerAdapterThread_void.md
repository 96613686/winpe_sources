# CDebugTargetClientThreadManager::CreateClientBrokerAdapterThread(void)

- ea: `0x18007213c`
- end: `0x180072232`
- name: `?CreateClientBrokerAdapterThread@CDebugTargetClientThreadManager@@QEAAXXZ`
- size: `246`
- prototype: `void __fastcall(CDebugTargetClientThreadManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002ddb0`

## callees

- `0x180018b30`
- `0x180037b5c`
- `0x18007213c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800721f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800721f4`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072160`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007218e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180072160`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007218e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800721cd`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800721cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072219`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180072219`

## string_xrefs

- `0x180072174`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetclientbrokeradapter.cpp`
- `0x1800721a2`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetclientbrokeradapter.cpp`
- `0x1800721dd`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetclientbrokeradapter.cpp`
- `0x180072203`: `onecoreuap\inetcore\edgemanager\webruntime\webrtdiagnosticsbrokeradapter\debugtargetclientbrokeradapter.cpp`

## pseudocode

```c
void __fastcall CDebugTargetClientThreadManager::CreateClientBrokerAdapterThread(CDebugTargetClientThreadManager *this)
{
  DWORD *lpThreadId; // rdi
  HANDLE EventW; // rax
  const char *v4; // r9
  HANDLE v5; // rax
  const char *v6; // r9
  const char *v7; // r9
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  lpThreadId = (DWORD *)((char *)this + 4);
  if ( !*((_DWORD *)this + 1) )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 1) = EventW;
    if ( !EventW )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x66,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetclientbrokeradapter.cpp",
        v4);
    v5 = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 2) = v5;
    if ( !v5 )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetclientbrokeradapter.cpp",
        v6);
    if ( !CreateThread(
            0,
            0,
            (LPTHREAD_START_ROUTINE)CDebugTargetClientThreadManager::ClientBrokerAdapterThreadProc,
            this,
            0,
            lpThreadId) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetclientbrokeradapter.cpp",
        v7);
    if ( WaitForSingleObject(*((HANDLE *)this + 1), 0xFFFFFFFF) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webrtdiagnosticsbrokeradapter\\debugtargetclientbrokeradapter.cpp",
        v8);
    CloseHandle(*((HANDLE *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18007213c  mov     [rsp+arg_0], rbx
0x180072141  push    rdi
0x180072142  sub     rsp, 30h
0x180072146  lea     rdi, [rcx+4]
0x18007214a  mov     rbx, rcx
0x18007214d  cmp     dword ptr [rdi], 0
0x180072150  jnz     loc_180072227
0x180072156  xor     r9d, r9d; lpName
0x180072159  xor     r8d, r8d; bInitialState
0x18007215c  xor     edx, edx; bManualReset
0x18007215e  xor     ecx, ecx; lpEventAttributes
0x180072160  call    cs:__imp_CreateEventW
0x180072166  mov     [rbx+8], rax
0x18007216a  test    rax, rax
0x18007216d  jnz     short loc_180072184
0x18007216f  mov     rcx, [rsp+38h]; this
0x180072174  lea     r8, aOnecoreuapInet_5; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18007217b  lea     edx, [rax+66h]; void *
0x18007217e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180072184  xor     r9d, r9d; lpName
0x180072187  xor     r8d, r8d; bInitialState
0x18007218a  xor     edx, edx; bManualReset
0x18007218c  xor     ecx, ecx; lpEventAttributes
0x18007218e  call    cs:__imp_CreateEventW
0x180072194  mov     [rbx+10h], rax
0x180072198  test    rax, rax
0x18007219b  jnz     short loc_1800721B2
0x18007219d  mov     rcx, [rsp+38h]; this
0x1800721a2  lea     r8, aOnecoreuapInet_5; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800721a9  lea     edx, [rax+68h]; void *
0x1800721ac  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800721b2  mov     [rsp+38h+lpThreadId], rdi; lpThreadId
0x1800721b7  lea     r8, ?ClientBrokerAdapterThreadProc@CDebugTargetClientThreadManager@@SAJPEAX@Z; lpStartAddress
0x1800721be  mov     r9, rbx; lpParameter
0x1800721c1  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800721c9  xor     edx, edx; dwStackSize
0x1800721cb  xor     ecx, ecx; lpThreadAttributes
0x1800721cd  call    cs:__imp_CreateThread
0x1800721d3  test    rax, rax
0x1800721d6  jnz     short loc_1800721ED
0x1800721d8  mov     rcx, [rsp+38h]; this
0x1800721dd  lea     r8, aOnecoreuapInet_5; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800721e4  lea     edx, [rax+69h]; void *
0x1800721e7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800721ed  mov     rcx, [rbx+8]; hHandle
0x1800721f1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800721f4  call    cs:__imp_WaitForSingleObject
0x1800721fa  test    eax, eax
0x1800721fc  jz      short loc_180072215
0x1800721fe  mov     rcx, [rsp+38h]; this
0x180072203  lea     r8, aOnecoreuapInet_5; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18007220a  mov     edx, 6Bh ; 'k'; void *
0x18007220f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180072215  mov     rcx, [rbx+8]; hObject
0x180072219  call    cs:__imp_CloseHandle
0x18007221f  mov     qword ptr [rbx+8], 0
0x180072227  mov     rbx, [rsp+38h+arg_0]
0x18007222c  add     rsp, 30h
0x180072230  pop     rdi
0x180072231  retn
```
