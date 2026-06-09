# CCommandBufferMutex::DisableWorkerThreadAccess(void)

- ea: `0x140010798`
- end: `0x14001083b`
- name: `?DisableWorkerThreadAccess@CCommandBufferMutex@@QEAAXXZ`
- size: `163`
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

- `0x140010798`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140010824`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x140010824`
- `ntoskrnl!DbgPrint` at `0x1400107bf`
- `ntoskrnl!DbgPrint` at `0x1400107bf`
- `ntoskrnl!KdDebuggerEnabled` at `0x1400107ad`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400107e6`
- `watchdog!WdLogNewEntry5_WdError` at `0x1400107e6`
- `watchdog!WdLogSingleEntry0` at `0x1400107d0`
- `watchdog!WdLogSingleEntry0` at `0x1400107d0`

## string_xrefs

- `0x1400107b8`: `Error in DisableWorkerThreadAccess`

## pseudocode

```c
void __fastcall CCommandBufferMutex::DisableWorkerThreadAccess(CCommandBufferMutex *this)
{
  _QWORD *v2; // rax

  if ( *((_BYTE *)this + 9) || *((_BYTE *)this + 10) )
  {
    if ( (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("Error in DisableWorkerThreadAccess");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 855;
      v2 = (_QWORD *)WdLogNewEntry5_WdError();
      v2[3] = gCddImageInfo;
      v2[4] = (unsigned int)dword_14003E570;
      v2[5] = 215857758;
      WdLogGlobalForLineNumber = 855;
      __debugbreak();
    }
  }
  ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*(_QWORD *)(*(_QWORD *)this + 2896LL));
  *((_BYTE *)this + 9) = 1;
}

```

## disassembly

```asm
0x140010798  push    rbx
0x14001079a  sub     rsp, 20h
0x14001079e  mov     rbx, rcx
0x1400107a1  xor     ecx, ecx
0x1400107a3  cmp     [rbx+9], cl
0x1400107a6  jnz     short loc_1400107AD
0x1400107a8  cmp     [rbx+0Ah], cl
0x1400107ab  jz      short loc_14001081A
0x1400107ad  mov     rax, cs:KdDebuggerEnabled
0x1400107b4  cmp     [rax], cl
0x1400107b6  jz      short loc_14001081A
0x1400107b8  lea     rcx, aErrorInDisable; "Error in DisableWorkerThreadAccess"
0x1400107bf  call    cs:__imp_DbgPrint
0x1400107c6  nop     dword ptr [rax+rax+00h]
0x1400107cb  mov     ecx, 2
0x1400107d0  call    cs:__imp_WdLogSingleEntry0
0x1400107d7  nop     dword ptr [rax+rax+00h]
0x1400107dc  mov     cs:WdLogGlobalForLineNumber, 357h
0x1400107e6  call    cs:__imp_WdLogNewEntry5_WdError
0x1400107ed  nop     dword ptr [rax+rax+00h]
0x1400107f2  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x1400107f9  mov     [rax+18h], rcx
0x1400107fd  mov     ecx, cs:dword_14003E570
0x140010803  mov     [rax+20h], rcx
0x140010807  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001080f  mov     cs:WdLogGlobalForLineNumber, 357h
0x140010819  int     3; Trap to Debugger
0x14001081a  mov     rcx, [rbx]
0x14001081d  mov     rcx, [rcx+0B50h]
0x140010824  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14001082b  nop     dword ptr [rax+rax+00h]
0x140010830  mov     byte ptr [rbx+9], 1
0x140010834  add     rsp, 20h
0x140010838  pop     rbx
0x140010839  retn
```
