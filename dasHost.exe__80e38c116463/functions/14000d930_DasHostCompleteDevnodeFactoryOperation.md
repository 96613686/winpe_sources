# DasHostCompleteDevnodeFactoryOperation

- ea: `0x14000d930`
- end: `0x14000da72`
- name: `DasHostCompleteDevnodeFactoryOperation`
- size: `322`
- prototype: `__int64 __fastcall(RTL_SRWLOCK **, int, const unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140008eec`
- `0x140008f88`
- `0x14000d930`
- `0x14000f370`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d991`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000d991`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d9e3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000d9e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000da0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000da0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d9ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d9ff`

## pseudocode

```c
__int64 __fastcall DasHostCompleteDevnodeFactoryOperation(RTL_SRWLOCK **a1, int a2, const unsigned __int16 *a3, int a4)
{
  RTL_SRWLOCK *v4; // rsi
  unsigned int v8; // ebx
  struct _OPERATION_LIST_ENTRY *Ptr; // rax
  struct _OPERATION_LIST_ENTRY *v10; // rdi
  RTL_SRWLOCK *v11; // rcx
  RTL_SRWLOCK **v12; // rdx
  HANDLE ProcessHeap; // rax
  int v14; // edx
  int v15; // r8d
  int v17; // [rsp+28h] [rbp-60h]

  v4 = *a1;
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      a2,
      (int)a3,
      20,
      &WPP_390cfc987846301e1004d86ef1b4fc88_Traceguids);
  (*((void (__fastcall **)(RTL_SRWLOCK *))v4->Ptr + 1))(v4);
  AcquireSRWLockExclusive(v4 + 12);
  v8 = 0;
  Ptr = (struct _OPERATION_LIST_ENTRY *)v4[10].Ptr;
  if ( Ptr == (struct _OPERATION_LIST_ENTRY *)&v4[10] )
  {
    v10 = 0;
  }
  else
  {
    while ( 1 )
    {
      v10 = Ptr;
      v11 = *(RTL_SRWLOCK **)Ptr;
      if ( *((_DWORD *)Ptr + 5) == a2 )
        break;
      v10 = 0;
      Ptr = *(struct _OPERATION_LIST_ENTRY **)Ptr;
      if ( v11 == &v4[10] )
        goto LABEL_11;
    }
    if ( v11[1].Ptr != Ptr || (v12 = (RTL_SRWLOCK **)*((_QWORD *)Ptr + 1), *v12 != (RTL_SRWLOCK *)Ptr) )
      __fastfail(3u);
    *v12 = v11;
    v11[1].Ptr = v12;
  }
LABEL_11:
  ReleaseSRWLockExclusive(v4 + 12);
  if ( v10 )
  {
    CDasHostDevnodeMgmt::CompleteDevnodeFactoryOperation((CDasHostDevnodeMgmt *)v4, v10, a3, a4);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  else
  {
    v8 = 1;
  }
  (*((void (__fastcall **)(RTL_SRWLOCK *))v4->Ptr + 2))(v4);
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v14,
      v15,
      21,
      &WPP_390cfc987846301e1004d86ef1b4fc88_Traceguids,
      v17,
      v8);
  return v8;
}

```

## disassembly

```asm
0x14000d930  push    rbx
0x14000d932  push    rbp
0x14000d933  push    rsi
0x14000d934  push    rdi
0x14000d935  push    r12
0x14000d937  push    r13
0x14000d939  push    r14
0x14000d93b  push    r15
0x14000d93d  sub     rsp, 48h
0x14000d941  mov     rsi, [rcx]
0x14000d944  mov     r15d, r9d
0x14000d947  mov     r12, r8
0x14000d94a  mov     ebp, edx
0x14000d94c  lea     rax, WPP_RECORDER_INITIALIZED
0x14000d953  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000d95a  lea     r13, WPP_390cfc987846301e1004d86ef1b4fc88_Traceguids
0x14000d961  jz      short loc_14000D97E
0x14000d963  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d96a  mov     r9d, 14h; int
0x14000d970  mov     [rsp+88h+MessageGuid], r13; MessageGuid
0x14000d975  mov     rcx, [rcx+28h]; int
0x14000d979  call    WPP_RECORDER_SF_s
0x14000d97e  mov     rax, [rsi]
0x14000d981  mov     rcx, rsi
0x14000d984  mov     rax, [rax+8]
0x14000d988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d98d  lea     rcx, [rsi+60h]; SRWLock
0x14000d991  call    cs:__imp_AcquireSRWLockExclusive
0x14000d997  lea     rdx, [rsi+50h]
0x14000d99b  xor     ebx, ebx
0x14000d99d  mov     rax, [rdx]
0x14000d9a0  cmp     rax, rdx
0x14000d9a3  jnz     short loc_14000D9A9
0x14000d9a5  mov     edi, ebx
0x14000d9a7  jmp     short loc_14000D9DF
0x14000d9a9  mov     rdi, rax
0x14000d9ac  mov     rcx, [rax]
0x14000d9af  cmp     [rax+14h], ebp
0x14000d9b2  jz      short loc_14000D9C1
0x14000d9b4  mov     rdi, rbx
0x14000d9b7  mov     rax, rcx
0x14000d9ba  cmp     rcx, rdx
0x14000d9bd  jnz     short loc_14000D9A9
0x14000d9bf  jmp     short loc_14000D9DF
0x14000d9c1  cmp     [rcx+8], rax
0x14000d9c5  jnz     loc_14000DA6B
0x14000d9cb  mov     rdx, [rax+8]
0x14000d9cf  cmp     [rdx], rax
0x14000d9d2  jnz     loc_14000DA6B
0x14000d9d8  mov     [rdx], rcx
0x14000d9db  mov     [rcx+8], rdx
0x14000d9df  lea     rcx, [rsi+60h]; SRWLock
0x14000d9e3  call    cs:__imp_ReleaseSRWLockExclusive
0x14000d9e9  test    rdi, rdi
0x14000d9ec  jz      short loc_14000DA15
0x14000d9ee  mov     r9d, r15d; int
0x14000d9f1  mov     r8, r12; unsigned __int16 *
0x14000d9f4  mov     rdx, rdi; struct _OPERATION_LIST_ENTRY *
0x14000d9f7  mov     rcx, rsi; this
0x14000d9fa  call    ?CompleteDevnodeFactoryOperation@CDasHostDevnodeMgmt@@QEAAXPEAU_OPERATION_LIST_ENTRY@@PEBGJ@Z; CDasHostDevnodeMgmt::CompleteDevnodeFactoryOperation(_OPERATION_LIST_ENTRY *,ushort const *,long)
0x14000d9ff  call    cs:__imp_GetProcessHeap
0x14000da05  mov     r8, rdi; lpMem
0x14000da08  xor     edx, edx; dwFlags
0x14000da0a  mov     rcx, rax; hHeap
0x14000da0d  call    cs:__imp_HeapFree
0x14000da13  jmp     short loc_14000DA1A
0x14000da15  mov     ebx, 1
0x14000da1a  mov     rax, [rsi]
0x14000da1d  mov     rcx, rsi
0x14000da20  mov     rax, [rax+10h]
0x14000da24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da29  lea     rax, WPP_RECORDER_INITIALIZED
0x14000da30  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000da37  jz      short loc_14000DA58
0x14000da39  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da40  mov     r9d, 15h; int
0x14000da46  mov     dword ptr [rsp+88h+var_58], ebx; char
0x14000da4a  mov     [rsp+88h+MessageGuid], r13; MessageGuid
0x14000da4f  mov     rcx, [rcx+28h]; int
0x14000da53  call    WPP_RECORDER_SF_sd
0x14000da58  mov     eax, ebx
0x14000da5a  add     rsp, 48h
0x14000da5e  pop     r15
0x14000da60  pop     r14
0x14000da62  pop     r13
0x14000da64  pop     r12
0x14000da66  pop     rdi
0x14000da67  pop     rsi
0x14000da68  pop     rbp
0x14000da69  pop     rbx
0x14000da6a  retn
0x14000da6b  mov     ecx, 3
0x14000da70  int     29h; Win8: RtlFailFast(ecx)
```
