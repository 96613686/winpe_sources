# CConnectionList::AddNotificationIfPossible(void)

- ea: `0x180041dc8`
- end: `0x180041e68`
- name: `?AddNotificationIfPossible@CConnectionList@@QEAAHXZ`
- size: `160`
- prototype: `__int64 __fastcall(CConnectionList *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800487a0`
- `0x180058210`

## callees

- `0x180041dc8`

## import_xrefs

- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x180041e33`
- `SHLWAPI!__imp_SHCreateThreadWithHandle` at `0x180041e33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041e0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180041e0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041de7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041de7`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180041e44`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadId` at `0x180041e44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041e55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180041e55`

## pseudocode

```c
__int64 __fastcall CConnectionList::AddNotificationIfPossible(CConnectionList *this)
{
  UINT v1; // edi
  BOOL v2; // ebx

  v1 = 0;
  EnterCriticalSection(&CriticalSection);
  v2 = g_dwNumInstances++ == 0;
  LeaveCriticalSection(&CriticalSection);
  if ( v2 )
  {
    v1 = SHCreateThreadWithHandle((WCHAR)CConnectionList::NotifyThread);
    if ( v1 )
    {
      CConnectionList::m_dwNotifyThread = GetThreadId(0);
      CloseHandle(0);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180041dc8  mov     [rsp+arg_8], rbx
0x180041dcd  mov     [rsp+Thread], rcx
0x180041dd2  push    rdi
0x180041dd3  sub     rsp, 30h
0x180041dd7  xor     edi, edi
0x180041dd9  lea     rcx, CriticalSection; lpCriticalSection
0x180041de0  mov     [rsp+38h+Thread], rdi
0x180041de5  xor     ebx, ebx
0x180041de7  call    cs:__imp_EnterCriticalSection
0x180041ded  mov     eax, cs:?g_dwNumInstances@@3KA; ulong g_dwNumInstances
0x180041df3  lea     edx, [rdi+1]
0x180041df6  test    eax, eax
0x180041df8  lea     rcx, CriticalSection; lpCriticalSection
0x180041dff  cmovz   ebx, edx
0x180041e02  add     eax, edx
0x180041e04  mov     cs:?g_dwNumInstances@@3KA, eax; ulong g_dwNumInstances
0x180041e0a  call    cs:__imp_LeaveCriticalSection
0x180041e10  test    ebx, ebx
0x180041e12  jz      short loc_180041E5B
0x180041e14  lea     rax, [rsp+38h+Thread]
0x180041e19  xor     r9d, r9d
0x180041e1c  lea     r8d, [rdi+0Ch]
0x180041e20  mov     [rsp+38h+var_18], rax
0x180041e25  lea     rdx, ?g_ccl@@3VCConnectionList@@A; CConnectionList g_ccl
0x180041e2c  lea     rcx, ?NotifyThread@CConnectionList@@CAKPEAX@Z; ch
0x180041e33  call    cs:__imp_SHCreateThreadWithHandle
0x180041e39  mov     edi, eax
0x180041e3b  test    eax, eax
0x180041e3d  jz      short loc_180041E5B
0x180041e3f  mov     rcx, [rsp+38h+Thread]; Thread
0x180041e44  call    cs:__imp_GetThreadId
0x180041e4a  mov     rcx, [rsp+38h+Thread]; hObject
0x180041e4f  mov     cs:?m_dwNotifyThread@CConnectionList@@0KA, eax; ulong CConnectionList::m_dwNotifyThread
0x180041e55  call    cs:__imp_CloseHandle
0x180041e5b  mov     rbx, [rsp+38h+arg_8]
0x180041e60  mov     eax, edi
0x180041e62  add     rsp, 30h
0x180041e66  pop     rdi
0x180041e67  retn
```
