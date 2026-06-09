# EfsMdmCleanupHandler

- ea: `0x180041b58`
- end: `0x180041c12`
- name: `EfsMdmCleanupHandler`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033a10`

## callees

- `0x180041b58`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041bec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180041bec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041bfa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180041bfa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180041bdd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180041bdd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180041bd3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180041bd3`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180041bb6`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180041bb6`
- `ntdll!RtlDeleteCriticalSection` at `0x180041be6`
- `ntdll!RtlDeleteCriticalSection` at `0x180041be6`

## pseudocode

```c
__int64 EfsMdmCleanupHandler()
{
  PRTL_CRITICAL_SECTION v0; // rbx
  unsigned int v1; // esi
  char *v2; // rdi
  HANDLE ProcessHeap; // rax

  v0 = pEfsMdmContext;
  if ( pEfsMdmContext )
  {
    v1 = 0;
    v2 = 0;
    if ( pEfsMdmContext[3].OwningThread )
    {
      do
      {
        if ( *((_QWORD *)&v0[3].LockSemaphore + (_QWORD)v2) )
          RtlUnsubscribeWnfNotificationWaitForCompletion();
        ++v2;
      }
      while ( v2 < v0[3].OwningThread );
    }
    CloseThreadpoolCleanupGroupMembers((PTP_CLEANUP_GROUP)v0[2].SpinCount, 1, 0);
    CloseThreadpoolCleanupGroup((PTP_CLEANUP_GROUP)v0[2].SpinCount);
    RtlDeleteCriticalSection(v0);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v0);
  }
  else
  {
    v1 = 160;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, 160, 32, 240);
  }
  return v1;
}

```

## disassembly

```asm
0x180041b58  mov     [rsp+arg_0], rbx
0x180041b5d  mov     [rsp+arg_8], rsi
0x180041b62  push    rdi
0x180041b63  sub     rsp, 30h
0x180041b67  mov     rbx, cs:pEfsMdmContext
0x180041b6e  test    rbx, rbx
0x180041b71  jnz     short loc_180041B9C
0x180041b73  mov     rcx, cs:g_hPublisher
0x180041b7a  lea     r9d, [rbx+20h]
0x180041b7e  mov     esi, 0A0h
0x180041b83  mov     [rsp+38h+var_18], 1F0h
0x180041b8b  mov     r8d, esi
0x180041b8e  lea     rdx, EFS_TRACE_ERROR
0x180041b95  call    fnEfsLogTrace1
0x180041b9a  jmp     short loc_180041C00
0x180041b9c  xor     esi, esi
0x180041b9e  xor     edi, edi
0x180041ba0  cmp     [rbx+88h], rsi
0x180041ba7  jbe     short loc_180041BC8
0x180041ba9  mov     rcx, [rbx+rdi*8+90h]
0x180041bb1  test    rcx, rcx
0x180041bb4  jz      short loc_180041BBC
0x180041bb6  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180041bbc  inc     rdi
0x180041bbf  cmp     rdi, [rbx+88h]
0x180041bc6  jb      short loc_180041BA9
0x180041bc8  mov     rcx, [rbx+70h]; ptpcg
0x180041bcc  xor     r8d, r8d; pvCleanupContext
0x180041bcf  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180041bd3  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180041bd9  mov     rcx, [rbx+70h]; ptpcg
0x180041bdd  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180041be3  mov     rcx, rbx; CriticalSection
0x180041be6  call    cs:__imp_RtlDeleteCriticalSection
0x180041bec  call    cs:__imp_GetProcessHeap
0x180041bf2  mov     r8, rbx; lpMem
0x180041bf5  xor     edx, edx; dwFlags
0x180041bf7  mov     rcx, rax; hHeap
0x180041bfa  call    cs:__imp_HeapFree
0x180041c00  mov     rbx, [rsp+38h+arg_0]
0x180041c05  mov     eax, esi
0x180041c07  mov     rsi, [rsp+38h+arg_8]
0x180041c0c  add     rsp, 30h
0x180041c10  pop     rdi
0x180041c11  retn
```
