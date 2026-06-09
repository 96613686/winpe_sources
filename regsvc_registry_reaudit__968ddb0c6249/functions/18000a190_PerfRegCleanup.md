# PerfRegCleanup

- ea: `0x18000a190`
- end: `0x18000a29e`
- name: `PerfRegCleanup`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180008600`

## callees

- `0x18000a190`
- `0x18000aaa0`
- `0x18000aac8`
- `0x18000acd0`
- `0x18000be10`
- `0x18000cb04`
- `0x180013310`

## import_xrefs

- `ntdll!RtlRunOnceInitialize` at `0x18000a28e`
- `ntdll!RtlRunOnceInitialize` at `0x18000a28e`
- `ntdll!RtlDllShutdownInProgress` at `0x18000a24c`
- `ntdll!RtlDllShutdownInProgress` at `0x18000a24c`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a246`
- `ntdll!RtlDeleteCriticalSection` at `0x18000a246`
- `ntdll!RtlRunOnceBeginInitialize` at `0x18000a1a2`
- `ntdll!RtlRunOnceBeginInitialize` at `0x18000a1a2`
- `ntdll!EtwEventUnregister` at `0x18000a27c`
- `ntdll!EtwEventUnregister` at `0x18000a27c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a222`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a222`

## pseudocode

```c
__int64 PerfRegCleanup()
{
  _QWORD *v0; // rcx
  __int64 v2; // rcx

  if ( (int)RtlRunOnceBeginInitialize(qword_18002B570, 1) < 0 )
    return 1;
  v0 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids);
    v0 = WPP_GLOBAL_Control;
  }
  if ( !hGlobalDataMutex )
  {
LABEL_12:
    PerfpDeleteErrorLogs(&PerfpErrorLog);
    RtlDeleteCriticalSection(&PerfpCritSect);
    if ( !RtlDllShutdownInProgress() )
      CleanupRpcBindingHandle();
    CleanupV2Resources();
    v2 = qword_18002B068;
    dword_18002B048 = 0;
    qword_18002B068 = 0;
    EtwEventUnregister(v2);
    WppCleanupUm();
    RtlRunOnceInitialize(qword_18002B570);
    return 1;
  }
  if ( !NumberOfOpens )
  {
    CloseHandle(hGlobalDataMutex);
    hGlobalDataMutex = 0;
    goto LABEL_12;
  }
  if ( (*((_DWORD *)v0 + 7) & 0x100) != 0 && *((_BYTE *)v0 + 25) >= 3u )
    WPP_SF_d(v0[2], 50, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids, (unsigned int)NumberOfOpens);
  return 0;
}

```

## disassembly

```asm
0x18000a190  sub     rsp, 28h
0x18000a194  xor     r8d, r8d
0x18000a197  lea     rcx, qword_18002B570
0x18000a19e  lea     edx, [r8+1]
0x18000a1a2  call    cs:__imp_RtlRunOnceBeginInitialize
0x18000a1a8  test    eax, eax
0x18000a1aa  js      loc_18000A294
0x18000a1b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1b7  test    byte ptr [rcx+1Ch], 1
0x18000a1bb  jz      short loc_18000A1DF
0x18000a1bd  cmp     byte ptr [rcx+19h], 4
0x18000a1c1  jb      short loc_18000A1DF
0x18000a1c3  mov     rcx, [rcx+10h]
0x18000a1c7  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18000a1ce  mov     edx, 31h ; '1'
0x18000a1d3  call    WPP_SF_
0x18000a1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1df  mov     rax, cs:?hGlobalDataMutex@@3PEAXEA; void * hGlobalDataMutex
0x18000a1e6  test    rax, rax
0x18000a1e9  jz      short loc_18000A233
0x18000a1eb  mov     r9d, cs:?NumberOfOpens@@3JA; long NumberOfOpens
0x18000a1f2  test    r9d, r9d
0x18000a1f5  jz      short loc_18000A21F
0x18000a1f7  test    dword ptr [rcx+1Ch], 100h
0x18000a1fe  jz      short loc_18000A21B
0x18000a200  cmp     byte ptr [rcx+19h], 3
0x18000a204  jb      short loc_18000A21B
0x18000a206  mov     rcx, [rcx+10h]
0x18000a20a  lea     r8, WPP_268e67c0a25b3e0647c4a3b3acad50ad_Traceguids
0x18000a211  mov     edx, 32h ; '2'
0x18000a216  call    WPP_SF_d
0x18000a21b  xor     eax, eax
0x18000a21d  jmp     short loc_18000A299
0x18000a21f  mov     rcx, rax; hObject
0x18000a222  call    cs:__imp_CloseHandle
0x18000a228  mov     cs:?hGlobalDataMutex@@3PEAXEA, 0; void * hGlobalDataMutex
0x18000a233  lea     rcx, ?PerfpErrorLog@@3UERROR_LOG@@A; struct ERROR_LOG *
0x18000a23a  call    ?PerfpDeleteErrorLogs@@YAXPEAUERROR_LOG@@@Z; PerfpDeleteErrorLogs(ERROR_LOG *)
0x18000a23f  lea     rcx, ?PerfpCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000a246  call    cs:__imp_RtlDeleteCriticalSection
0x18000a24c  call    cs:__imp_RtlDllShutdownInProgress
0x18000a252  test    al, al
0x18000a254  jnz     short loc_18000A25B
0x18000a256  call    ?CleanupRpcBindingHandle@@YAXXZ; CleanupRpcBindingHandle(void)
0x18000a25b  call    CleanupV2Resources
0x18000a260  mov     rcx, cs:qword_18002B068
0x18000a267  mov     cs:dword_18002B048, 0
0x18000a271  mov     cs:qword_18002B068, 0
0x18000a27c  call    cs:__imp_EtwEventUnregister
0x18000a282  call    WppCleanupUm
0x18000a287  lea     rcx, qword_18002B570
0x18000a28e  call    cs:__imp_RtlRunOnceInitialize
0x18000a294  mov     eax, 1
0x18000a299  add     rsp, 28h
0x18000a29d  retn
```
