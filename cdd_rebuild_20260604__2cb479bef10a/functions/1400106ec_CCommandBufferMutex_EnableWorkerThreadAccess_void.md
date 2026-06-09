# CCommandBufferMutex::EnableWorkerThreadAccess(void)

- ea: `0x1400106ec`
- end: `0x140010790`
- name: `?EnableWorkerThreadAccess@CCommandBufferMutex@@QEAAXXZ`
- size: `164`
- prototype: `void __fastcall(CCommandBufferMutex *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400015e0`
- `0x140003840`
- `0x14000e880`
- `0x14000f370`
- `0x1400101a0`

## callees

- `0x1400106ec`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140010779`
- `ntoskrnl!ExReleaseFastMutexUnsafeAndLeaveCriticalRegion` at `0x140010779`
- `ntoskrnl!DbgPrint` at `0x140010714`
- `ntoskrnl!DbgPrint` at `0x140010714`
- `ntoskrnl!KdDebuggerEnabled` at `0x140010701`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001073b`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001073b`
- `watchdog!WdLogSingleEntry0` at `0x140010725`
- `watchdog!WdLogSingleEntry0` at `0x140010725`

## string_xrefs

- `0x14001070d`: `Error in EnableWorkerThreadAccess`

## pseudocode

```c
void __fastcall CCommandBufferMutex::EnableWorkerThreadAccess(CCommandBufferMutex *this)
{
  _QWORD *v2; // rax

  if ( *((_BYTE *)this + 9) != 1 || *((_BYTE *)this + 10) )
  {
    if ( (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Error in EnableWorkerThreadAccess");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 849;
      v2 = (_QWORD *)WdLogNewEntry5_WdError();
      v2[3] = gCddImageInfo;
      v2[4] = (unsigned int)dword_14003E570;
      v2[5] = 215857758;
      WdLogGlobalForLineNumber = 849;
      __debugbreak();
    }
  }
  ExReleaseFastMutexUnsafeAndLeaveCriticalRegion(*(_QWORD *)(*(_QWORD *)this + 2896LL));
  *((_BYTE *)this + 9) = 0;
}

```

## disassembly

```asm
0x1400106ec  push    rbx
0x1400106ee  sub     rsp, 20h
0x1400106f2  cmp     byte ptr [rcx+9], 1
0x1400106f6  mov     rbx, rcx
0x1400106f9  jnz     short loc_140010701
0x1400106fb  cmp     byte ptr [rcx+0Ah], 0
0x1400106ff  jz      short loc_14001076F
0x140010701  mov     rax, cs:KdDebuggerEnabled
0x140010708  cmp     byte ptr [rax], 0
0x14001070b  jz      short loc_14001076F
0x14001070d  lea     rcx, aErrorInEnablew; "Error in EnableWorkerThreadAccess"
0x140010714  call    cs:__imp_DbgPrint
0x14001071b  nop     dword ptr [rax+rax+00h]
0x140010720  mov     ecx, 2
0x140010725  call    cs:__imp_WdLogSingleEntry0
0x14001072c  nop     dword ptr [rax+rax+00h]
0x140010731  mov     cs:WdLogGlobalForLineNumber, 351h
0x14001073b  call    cs:__imp_WdLogNewEntry5_WdError
0x140010742  nop     dword ptr [rax+rax+00h]
0x140010747  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001074e  mov     [rax+18h], rcx
0x140010752  mov     ecx, cs:dword_14003E570
0x140010758  mov     [rax+20h], rcx
0x14001075c  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x140010764  mov     cs:WdLogGlobalForLineNumber, 351h
0x14001076e  int     3; Trap to Debugger
0x14001076f  mov     rcx, [rbx]
0x140010772  mov     rcx, [rcx+0B50h]
0x140010779  call    cs:__imp_ExReleaseFastMutexUnsafeAndLeaveCriticalRegion
0x140010780  nop     dword ptr [rax+rax+00h]
0x140010785  mov     byte ptr [rbx+9], 0
0x140010789  add     rsp, 20h
0x14001078d  pop     rbx
0x14001078e  retn
```
