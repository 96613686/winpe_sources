# AutoThreadpool::UninitializeAndWaitForPendingWorkItems(void)

- ea: `0x140015438`
- end: `0x1400154d7`
- name: `?UninitializeAndWaitForPendingWorkItems@AutoThreadpool@@QEAAXXZ`
- size: `159`
- prototype: `void __fastcall(AutoThreadpool *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400150b8`
- `0x140016035`

## callees

- `0x140015438`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001544c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001544c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400154bf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400154bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x140015470`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x140015470`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1400154a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1400154a3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x140015483`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x140015483`

## pseudocode

```c
void __fastcall AutoThreadpool::UninitializeAndWaitForPendingWorkItems(AutoThreadpool *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rdi
  struct _TP_CLEANUP_GROUP *v3; // rcx
  struct _TP_POOL *v4; // rcx

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((_QWORD *)this + 6) )
  {
    v3 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 16);
    if ( v3 )
    {
      CloseThreadpoolCleanupGroupMembers(v3, 0, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 16));
      *((_QWORD *)this + 16) = 0;
    }
    v4 = (struct _TP_POOL *)*((_QWORD *)this + 6);
    if ( v4 )
    {
      CloseThreadpool(v4);
      *((_QWORD *)this + 6) = 0;
    }
  }
  if ( v1 )
    LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x140015438  mov     [rsp+arg_0], rbx
0x14001543d  push    rdi
0x14001543e  sub     rsp, 20h
0x140015442  lea     rdi, [rcx+8]
0x140015446  mov     rbx, rcx
0x140015449  mov     rcx, rdi; lpCriticalSection
0x14001544c  call    cs:__imp_EnterCriticalSection
0x140015453  nop     dword ptr [rax+rax+00h]
0x140015458  cmp     qword ptr [rbx+30h], 0
0x14001545d  jz      short loc_1400154B7
0x14001545f  mov     rcx, [rbx+80h]; ptpcg
0x140015466  test    rcx, rcx
0x140015469  jz      short loc_14001549A
0x14001546b  xor     r8d, r8d; pvCleanupContext
0x14001546e  xor     edx, edx; fCancelPendingCallbacks
0x140015470  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x140015477  nop     dword ptr [rax+rax+00h]
0x14001547c  mov     rcx, [rbx+80h]; ptpcg
0x140015483  call    cs:__imp_CloseThreadpoolCleanupGroup
0x14001548a  nop     dword ptr [rax+rax+00h]
0x14001548f  mov     qword ptr [rbx+80h], 0
0x14001549a  mov     rcx, [rbx+30h]; ptpp
0x14001549e  test    rcx, rcx
0x1400154a1  jz      short loc_1400154B7
0x1400154a3  call    cs:__imp_CloseThreadpool
0x1400154aa  nop     dword ptr [rax+rax+00h]
0x1400154af  mov     qword ptr [rbx+30h], 0
0x1400154b7  test    rdi, rdi
0x1400154ba  jz      short loc_1400154CB
0x1400154bc  mov     rcx, rdi; lpCriticalSection
0x1400154bf  call    cs:__imp_LeaveCriticalSection
0x1400154c6  nop     dword ptr [rax+rax+00h]
0x1400154cb  mov     rbx, [rsp+28h+arg_0]
0x1400154d0  add     rsp, 20h
0x1400154d4  pop     rdi
0x1400154d5  retn
```
