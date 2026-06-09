# CCommandBufferMutex::CCommandBufferMutex(CDDPDEV *,uchar,uchar)

- ea: `0x14001d488`
- end: `0x14001d604`
- name: `??0CCommandBufferMutex@@QEAA@PEAUCDDPDEV@@EE@Z`
- size: `380`
- prototype: `CCommandBufferMutex *__fastcall(CCommandBufferMutex *__hidden this, struct CDDPDEV *, unsigned __int8, unsigned __int8)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003840`
- `0x140005cc0`
- `0x140007b00`
- `0x14001c630`
- `0x14002ee20`
- `0x14002f640`
- `0x140031110`
- `0x140033800`
- `0x1400339f0`

## callees

- `0x14001d488`

## import_xrefs

- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001d4c7`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001d5f3`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001d4c7`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireFastMutexUnsafe` at `0x14001d5f3`
- `ntoskrnl!DbgPrint` at `0x14001d501`
- `ntoskrnl!DbgPrint` at `0x14001d589`
- `ntoskrnl!DbgPrint` at `0x14001d501`
- `ntoskrnl!DbgPrint` at `0x14001d589`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001d4ee`
- `ntoskrnl!KdDebuggerEnabled` at `0x14001d572`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001d528`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001d5b0`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001d528`
- `watchdog!WdLogNewEntry5_WdError` at `0x14001d5b0`
- `watchdog!WdLogSingleEntry0` at `0x14001d512`
- `watchdog!WdLogSingleEntry0` at `0x14001d59a`
- `watchdog!WdLogSingleEntry0` at `0x14001d512`
- `watchdog!WdLogSingleEntry0` at `0x14001d59a`

## string_xrefs

- `0x14001d4fa`: `bAllowWorkerThreadAccess is not set for worker thread in EnableWorkerThreadAccess`
- `0x14001d582`: `bFromWorkerThread is set for non worker thread in EnableWorkerThreadAccess`

## pseudocode

```c
CCommandBufferMutex *__fastcall CCommandBufferMutex::CCommandBufferMutex(
        CCommandBufferMutex *this,
        struct _KTHREAD **a2,
        char a3,
        char a4)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rax

  if ( a3 )
  {
    if ( !a4 && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("bAllowWorkerThreadAccess is not set for worker thread in EnableWorkerThreadAccess");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 830;
      v9 = (_QWORD *)WdLogNewEntry5_WdError();
      v9[3] = gCddImageInfo;
      v9[4] = (unsigned int)dword_14003E570;
      v9[5] = 215857758;
      WdLogGlobalForLineNumber = 830;
      __debugbreak();
    }
    if ( KeGetCurrentThread() != a2[321] && (_BYTE)KdDebuggerEnabled )
    {
      DbgPrint("bFromWorkerThread is set for non worker thread in EnableWorkerThreadAccess");
      WdLogSingleEntry0(2);
      WdLogGlobalForLineNumber = 832;
      v10 = (_QWORD *)WdLogNewEntry5_WdError();
      v10[3] = gCddImageInfo;
      v10[4] = (unsigned int)dword_14003E570;
      v10[5] = 215857758;
      WdLogGlobalForLineNumber = 832;
      __debugbreak();
    }
  }
  *(_QWORD *)this = a2;
  *((_BYTE *)this + 10) = a3;
  *((_BYTE *)this + 8) = a3 == 0;
  *((_BYTE *)this + 9) = a4 == 0;
  if ( !a3 )
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(a2[361]);
  if ( !a4 )
    ExEnterCriticalRegionAndAcquireFastMutexUnsafe(*(_QWORD *)(*(_QWORD *)this + 2896LL));
  return this;
}

```

## disassembly

```asm
0x14001d488  push    rbx
0x14001d48a  push    rbp
0x14001d48b  push    rsi
0x14001d48c  push    rdi
0x14001d48d  sub     rsp, 28h
0x14001d491  mov     sil, r9b
0x14001d494  mov     dil, r8b
0x14001d497  mov     rbp, rdx
0x14001d49a  mov     rbx, rcx
0x14001d49d  test    r8b, r8b
0x14001d4a0  jnz     short loc_14001D4E9
0x14001d4a2  test    dil, dil
0x14001d4a5  mov     [rbx], rbp
0x14001d4a8  mov     [rbx+0Ah], dil
0x14001d4ac  setz    al
0x14001d4af  test    sil, sil
0x14001d4b2  mov     [rbx+8], al
0x14001d4b5  setz    al
0x14001d4b8  mov     [rbx+9], al
0x14001d4bb  test    dil, dil
0x14001d4be  jnz     short loc_14001D4D3
0x14001d4c0  mov     rcx, [rbp+0B48h]
0x14001d4c7  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14001d4ce  nop     dword ptr [rax+rax+00h]
0x14001d4d3  test    sil, sil
0x14001d4d6  jz      loc_14001D5E9
0x14001d4dc  mov     rax, rbx
0x14001d4df  add     rsp, 28h
0x14001d4e3  pop     rdi
0x14001d4e4  pop     rsi
0x14001d4e5  pop     rbp
0x14001d4e6  pop     rbx
0x14001d4e7  retn
0x14001d4e9  test    sil, sil
0x14001d4ec  jnz     short loc_14001D55C
0x14001d4ee  mov     rax, cs:KdDebuggerEnabled
0x14001d4f5  cmp     [rax], sil
0x14001d4f8  jz      short loc_14001D55C
0x14001d4fa  lea     rcx, aBallowworkerth; "bAllowWorkerThreadAccess is not set for"...
0x14001d501  call    cs:__imp_DbgPrint
0x14001d508  nop     dword ptr [rax+rax+00h]
0x14001d50d  mov     ecx, 2
0x14001d512  call    cs:__imp_WdLogSingleEntry0
0x14001d519  nop     dword ptr [rax+rax+00h]
0x14001d51e  mov     cs:WdLogGlobalForLineNumber, 33Eh
0x14001d528  call    cs:__imp_WdLogNewEntry5_WdError
0x14001d52f  nop     dword ptr [rax+rax+00h]
0x14001d534  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001d53b  mov     [rax+18h], rcx
0x14001d53f  mov     ecx, cs:dword_14003E570
0x14001d545  mov     [rax+20h], rcx
0x14001d549  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001d551  mov     cs:WdLogGlobalForLineNumber, 33Eh
0x14001d55b  int     3; Trap to Debugger
0x14001d55c  mov     rax, gs:188h
0x14001d565  cmp     rax, [rbp+0A08h]
0x14001d56c  jz      loc_14001D4A2
0x14001d572  mov     rax, cs:KdDebuggerEnabled
0x14001d579  cmp     byte ptr [rax], 0
0x14001d57c  jz      loc_14001D4A2
0x14001d582  lea     rcx, aBfromworkerthr; "bFromWorkerThread is set for non worker"...
0x14001d589  call    cs:__imp_DbgPrint
0x14001d590  nop     dword ptr [rax+rax+00h]
0x14001d595  mov     ecx, 2
0x14001d59a  call    cs:__imp_WdLogSingleEntry0
0x14001d5a1  nop     dword ptr [rax+rax+00h]
0x14001d5a6  mov     cs:WdLogGlobalForLineNumber, 340h
0x14001d5b0  call    cs:__imp_WdLogNewEntry5_WdError
0x14001d5b7  nop     dword ptr [rax+rax+00h]
0x14001d5bc  mov     rcx, cs:?gCddImageInfo@@3U_CDD_IMAGE_INFO@@A; _CDD_IMAGE_INFO gCddImageInfo
0x14001d5c3  mov     [rax+18h], rcx
0x14001d5c7  mov     ecx, cs:dword_14003E570
0x14001d5cd  mov     [rax+20h], rcx
0x14001d5d1  mov     qword ptr [rax+28h], 0CDDBA5Eh
0x14001d5d9  mov     cs:WdLogGlobalForLineNumber, 340h
0x14001d5e3  int     3; Trap to Debugger
0x14001d5e4  jmp     loc_14001D4A2
0x14001d5e9  mov     rcx, [rbx]
0x14001d5ec  mov     rcx, [rcx+0B50h]
0x14001d5f3  call    cs:__imp_ExEnterCriticalRegionAndAcquireFastMutexUnsafe
0x14001d5fa  nop     dword ptr [rax+rax+00h]
0x14001d5ff  jmp     loc_14001D4DC
```
