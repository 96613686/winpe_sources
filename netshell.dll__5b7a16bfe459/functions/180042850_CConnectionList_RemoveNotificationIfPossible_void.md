# CConnectionList::RemoveNotificationIfPossible(void)

- ea: `0x180042850`
- end: `0x1800428c0`
- name: `?RemoveNotificationIfPossible@CConnectionList@@QEAAHXZ`
- size: `112`
- prototype: `__int64 __fastcall(CConnectionList *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800487a0`
- `0x180058210`

## callees

- `0x180042850`

## import_xrefs

- `USER32!PostThreadMessageW` at `0x1800428a8`
- `USER32!PostThreadMessageW` at `0x1800428a8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004288d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004288d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004286a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004286a`

## pseudocode

```c
__int64 __fastcall CConnectionList::RemoveNotificationIfPossible(CConnectionList *this)
{
  unsigned int v1; // edi
  BOOL v2; // ebx

  v1 = 0;
  EnterCriticalSection(&CriticalSection);
  v2 = g_dwNumInstances-- == 1;
  LeaveCriticalSection(&CriticalSection);
  if ( v2 )
  {
    v1 = 1;
    PostThreadMessageW(CConnectionList::m_dwNotifyThread, 0x12u, 0, 0);
  }
  return v1;
}

```

## disassembly

```asm
0x180042850  mov     [rsp+arg_0], rbx
0x180042855  mov     [rsp+arg_8], rsi
0x18004285a  push    rdi
0x18004285b  sub     rsp, 20h
0x18004285f  lea     rcx, CriticalSection; lpCriticalSection
0x180042866  xor     edi, edi
0x180042868  xor     ebx, ebx
0x18004286a  call    cs:__imp_EnterCriticalSection
0x180042870  mov     eax, cs:?g_dwNumInstances@@3KA; ulong g_dwNumInstances
0x180042876  lea     esi, [rdi+1]
0x180042879  cmp     eax, esi
0x18004287b  lea     rcx, CriticalSection; lpCriticalSection
0x180042882  cmovz   ebx, esi
0x180042885  dec     eax
0x180042887  mov     cs:?g_dwNumInstances@@3KA, eax; ulong g_dwNumInstances
0x18004288d  call    cs:__imp_LeaveCriticalSection
0x180042893  test    ebx, ebx
0x180042895  jz      short loc_1800428AE
0x180042897  mov     ecx, cs:?m_dwNotifyThread@CConnectionList@@0KA; idThread
0x18004289d  lea     edx, [rsi+11h]; Msg
0x1800428a0  xor     r9d, r9d; lParam
0x1800428a3  xor     r8d, r8d; wParam
0x1800428a6  mov     edi, esi
0x1800428a8  call    cs:__imp_PostThreadMessageW
0x1800428ae  mov     rbx, [rsp+28h+arg_0]
0x1800428b3  mov     eax, edi
0x1800428b5  mov     rsi, [rsp+28h+arg_8]
0x1800428ba  add     rsp, 20h
0x1800428be  pop     rdi
0x1800428bf  retn
```
