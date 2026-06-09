# CIncomingConnectionSavePage::LaunchRASServiceStartThread(CIncomingConnectionSavePage *)

- ea: `0x18001f174`
- end: `0x18001f263`
- name: `?LaunchRASServiceStartThread@CIncomingConnectionSavePage@@AEAAHPEAV1@@Z`
- size: `239`
- prototype: `int(CIncomingConnectionSavePage *__hidden this, struct CIncomingConnectionSavePage *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001f2c0`

## callees

- `0x18001f174`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f22e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f22e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f213`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001f213`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18001f1a4`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x18001f1a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f1e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f1e2`
- `rtutils!TracePrintfExA` at `0x18001f1d3`
- `rtutils!TracePrintfExA` at `0x18001f249`
- `rtutils!TracePrintfExA` at `0x18001f1d3`
- `rtutils!TracePrintfExA` at `0x18001f249`

## string_xrefs

- `0x18001f23a`: `LaunchRASServicStartThread:Failed to start testing thread. Error = %d`
- `0x18001f1c7`: `LaunchRASServicStartThread is already running. This is invalid state.`

## pseudocode

```c
__int64 __fastcall CIncomingConnectionSavePage::LaunchRASServiceStartThread(
        CIncomingConnectionSavePage *this,
        struct CIncomingConnectionSavePage *a2)
{
  void *v3; // rcx
  HANDLE v5; // rax
  DWORD LastError; // eax
  DWORD v8; // [rsp+40h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+50h] [rbp+18h] BYREF

  ThreadId = 0;
  v3 = (void *)*((_QWORD *)this + 21);
  if ( v3 )
  {
    v8 = 0;
    if ( GetExitCodeThread(v3, &v8) && v8 == 259 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "LaunchRASServicStartThread is already running. This is invalid state.");
      return 0;
    }
    CloseHandle(*((HANDLE *)this + 21));
    *((_QWORD *)this + 21) = 0;
  }
  v5 = CreateThread(0, 0, CIncomingConnectionSavePage::RASServiceStartThread, a2, 0, &ThreadId);
  *((_QWORD *)this + 21) = v5;
  if ( !v5 )
  {
    if ( g_dwTraceId != -1 )
    {
      LastError = GetLastError();
      TracePrintfExA(
        g_dwTraceId,
        0xCu,
        "LaunchRASServicStartThread:Failed to start testing thread. Error = %d",
        LastError);
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18001f174  mov     rax, rsp
0x18001f177  mov     [rax+10h], rbx
0x18001f17b  push    rdi
0x18001f17c  sub     rsp, 30h
0x18001f180  mov     rbx, rcx
0x18001f183  mov     dword ptr [rax+18h], 0
0x18001f18a  mov     rcx, [rcx+0A8h]; hThread
0x18001f191  mov     rdi, rdx
0x18001f194  test    rcx, rcx
0x18001f197  jz      short loc_18001F1F3
0x18001f199  lea     rdx, [rax+8]; lpExitCode
0x18001f19d  mov     dword ptr [rax+8], 0
0x18001f1a4  call    cs:__imp_GetExitCodeThread
0x18001f1aa  test    eax, eax
0x18001f1ac  jz      short loc_18001F1DB
0x18001f1ae  cmp     [rsp+38h+arg_0], 103h
0x18001f1b6  jnz     short loc_18001F1DB
0x18001f1b8  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001f1be  cmp     ecx, 0FFFFFFFFh
0x18001f1c1  jz      loc_18001F24F
0x18001f1c7  lea     r8, aLaunchrasservi; "LaunchRASServicStartThread is already r"...
0x18001f1ce  mov     edx, 0Ch; dwFlags
0x18001f1d3  call    cs:__imp_TracePrintfExA
0x18001f1d9  jmp     short loc_18001F24F
0x18001f1db  mov     rcx, [rbx+0A8h]; hObject
0x18001f1e2  call    cs:__imp_CloseHandle
0x18001f1e8  mov     qword ptr [rbx+0A8h], 0
0x18001f1f3  lea     rax, [rsp+38h+ThreadId]
0x18001f1f8  mov     r9, rdi; lpParameter
0x18001f1fb  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18001f200  lea     r8, ?RASServiceStartThread@CIncomingConnectionSavePage@@CAP6AKPEAX@ZPEAV1@@Z; lpStartAddress
0x18001f207  xor     edx, edx; dwStackSize
0x18001f209  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x18001f211  xor     ecx, ecx; lpThreadAttributes
0x18001f213  call    cs:__imp_CreateThread
0x18001f219  mov     [rbx+0A8h], rax
0x18001f220  test    rax, rax
0x18001f223  jnz     short loc_18001F253
0x18001f225  cmp     cs:g_dwTraceId, 0FFFFFFFFh
0x18001f22c  jz      short loc_18001F24F
0x18001f22e  call    cs:__imp_GetLastError
0x18001f234  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001f23a  lea     r8, aLaunchrasservi_0; "LaunchRASServicStartThread:Failed to st"...
0x18001f241  mov     r9d, eax
0x18001f244  mov     edx, 0Ch; dwFlags
0x18001f249  call    cs:__imp_TracePrintfExA
0x18001f24f  xor     eax, eax
0x18001f251  jmp     short loc_18001F258
0x18001f253  mov     eax, 1
0x18001f258  mov     rbx, [rsp+38h+arg_8]
0x18001f25d  add     rsp, 30h
0x18001f261  pop     rdi
0x18001f262  retn
```
