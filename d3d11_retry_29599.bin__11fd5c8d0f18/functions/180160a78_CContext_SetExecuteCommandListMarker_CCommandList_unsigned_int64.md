# CContext::SetExecuteCommandListMarker(CCommandList *,unsigned __int64)

- ea: `0x180160a78`
- end: `0x180160af2`
- name: `?SetExecuteCommandListMarker@CContext@@QEAAXPEAVCCommandList@@_K@Z`
- size: `122`
- prototype: `void __fastcall(CContext *__hidden this, struct CCommandList *, unsigned __int64)`
- caller_count: `11`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800f29b0`
- `0x1800f3540`
- `0x1800f40b0`
- `0x1800f4cd0`
- `0x1800f5840`
- `0x180113a80`
- `0x1801145b0`
- `0x180115160`
- `0x180160b20`
- `0x1801617c0`
- `0x180162550`

## callees

- `0x18014e198`
- `0x18014e208`
- `0x180160a78`
- `0x180167424`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180160abb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180160abb`

## pseudocode

```c
void __fastcall CContext::SetExecuteCommandListMarker(CContext *this, struct CCommandList *a2, __int64 a3)
{
  SMarkerData *v5; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v8; // rdx
  __int64 v9; // rax
  union _LARGE_INTEGER v10; // [rsp+60h] [rbp+8h] BYREF

  v10.QuadPart = 0;
  v5 = (CContext *)((char *)this + 39304);
  while ( !SMarkerData::CapacityForBatchedDataAndMatchingQPC(v5, &v10, 0x16u) )
    CContext::FlushMarkerData(this);
  CurrentThreadId = GetCurrentThreadId();
  LOBYTE(v8) = 35;
  v9 = SMarkerData::PushBackBatchedData(v5, v8, &v10, 22, CurrentThreadId);
  *(_QWORD *)(v9 + 6) = a3;
  *(_QWORD *)(v9 + 14) = *((_QWORD *)a2 + 21);
}

```

## disassembly

```asm
0x180160a78  push    rbx
0x180160a7a  push    rbp
0x180160a7b  push    rsi
0x180160a7c  push    rdi
0x180160a7d  sub     rsp, 38h
0x180160a81  mov     rsi, r8
0x180160a84  mov     qword ptr [rsp+58h+arg_0], 0
0x180160a8d  mov     rbp, rdx
0x180160a90  lea     rbx, [rcx+9988h]
0x180160a97  mov     rdi, rcx
0x180160a9a  jmp     short loc_180160AA4
0x180160a9c  mov     rcx, rdi; this
0x180160a9f  call    ?FlushMarkerData@CContext@@QEAAXXZ; CContext::FlushMarkerData(void)
0x180160aa4  mov     r8d, 16h; unsigned int
0x180160aaa  lea     rdx, [rsp+58h+arg_0]; union _LARGE_INTEGER *
0x180160aaf  mov     rcx, rbx; this
0x180160ab2  call    ?CapacityForBatchedDataAndMatchingQPC@SMarkerData@@QEBA_NAEAT_LARGE_INTEGER@@I@Z; SMarkerData::CapacityForBatchedDataAndMatchingQPC(_LARGE_INTEGER &,uint)
0x180160ab7  test    al, al
0x180160ab9  jz      short loc_180160A9C
0x180160abb  call    cs:__imp_GetCurrentThreadId
0x180160ac1  mov     r9d, 16h
0x180160ac7  lea     r8, [rsp+58h+arg_0]
0x180160acc  mov     dl, 23h ; '#'
0x180160ace  mov     [rsp+58h+var_38], eax
0x180160ad2  mov     rcx, rbx
0x180160ad5  call    ?PushBackBatchedData@SMarkerData@@QEAAPEAXW4EMarkerOp@@AEBT_LARGE_INTEGER@@IK@Z; SMarkerData::PushBackBatchedData(EMarkerOp,_LARGE_INTEGER const &,uint,ulong)
0x180160ada  mov     [rax+6], rsi
0x180160ade  mov     rcx, [rbp+0A8h]
0x180160ae5  mov     [rax+0Eh], rcx
0x180160ae9  add     rsp, 38h
0x180160aed  pop     rdi
0x180160aee  pop     rsi
0x180160aef  pop     rbp
0x180160af0  pop     rbx
0x180160af1  retn
```
