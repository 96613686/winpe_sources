# CContext::SetMarker(EMarkerOp)

- ea: `0x18014e100`
- end: `0x18014e191`
- name: `?SetMarker@CContext@@QEAAXW4EMarkerOp@@@Z`
- size: `145`
- prototype: ``
- caller_count: `70`
- callee_count: `5`
- tags: ``

## callers

- `0x180001440`
- `0x1800015a0`
- `0x180001a20`
- `0x1800020d0`
- `0x180002ea0`
- `0x180003fb0`
- `0x180004e10`
- `0x180008b5c`
- `0x18002ba30`
- `0x1800cec00`
- `0x1800cedf0`
- `0x1800cf110`
- `0x1800d0270`
- `0x1800d20b0`
- `0x1800f05f0`
- `0x1800f06d0`
- `0x1800f07a0`
- `0x1800f0870`
- `0x1800f0950`
- `0x1800f0a30`
- `0x1800f0ba0`
- `0x1800f0c60`
- `0x1800f0d20`
- `0x1800f0e00`
- `0x1800f0ec0`
- `0x1800f0f60`
- `0x1800f1040`
- `0x1800f11b0`
- `0x180106e00`
- `0x180113780`
- `0x18012f2a0`
- `0x18012f300`
- `0x180146bf0`
- `0x18014b9d0`
- `0x18014c0e0`
- `0x18014c1b0`
- `0x18014d6c0`
- `0x18014d780`
- `0x18014db40`
- `0x18014dda0`
- `0x18014dea0`
- `0x18014dff0`
- `0x18014f5c0`
- `0x18014fa40`
- `0x180150070`
- `0x1801990e0`
- `0x180199e80`
- `0x18019fce0`
- `0x1801a0600`
- `0x1801a1570`

## callees

- `0x18014e100`
- `0x18014e198`
- `0x18014e208`
- `0x180167424`
- `0x1801cb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e13c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e13c`

## pseudocode

```c
__int64 __fastcall CContext::SetMarker(__int64 a1, char a2)
{
  SMarkerData *v4; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v6; // rdx
  union _LARGE_INTEGER v8; // [rsp+40h] [rbp+8h] BYREF

  v8.QuadPart = 0;
  v4 = (SMarkerData *)(a1 + 39304);
  while ( !SMarkerData::CapacityForBatchedDataAndMatchingQPC(v4, &v8, 6u) )
    CContext::FlushMarkerData((CContext *)a1);
  CurrentThreadId = GetCurrentThreadId();
  LOBYTE(v6) = a2;
  SMarkerData::PushBackBatchedData(v4, v6, &v8, 6, CurrentThreadId);
  ++*(_QWORD *)(a1 + 39336);
  return (*(__int64 (__fastcall **)(__int64))(a1 + 2776))(a1 + 40768);
}

```

## disassembly

```asm
0x18014e100  mov     [rsp+arg_8], rbx
0x18014e105  mov     [rsp+arg_10], rsi
0x18014e10a  push    rdi
0x18014e10b  sub     rsp, 30h
0x18014e10f  mov     sil, dl
0x18014e112  mov     rbx, rcx
0x18014e115  mov     qword ptr [rsp+38h+arg_0], 0
0x18014e11e  lea     rdi, [rcx+9988h]
0x18014e125  mov     r8d, 6; unsigned int
0x18014e12b  lea     rdx, [rsp+38h+arg_0]; union _LARGE_INTEGER *
0x18014e130  mov     rcx, rdi; this
0x18014e133  call    ?CapacityForBatchedDataAndMatchingQPC@SMarkerData@@QEBA_NAEAT_LARGE_INTEGER@@I@Z; SMarkerData::CapacityForBatchedDataAndMatchingQPC(_LARGE_INTEGER &,uint)
0x18014e138  test    al, al
0x18014e13a  jz      short loc_18014E187
0x18014e13c  call    cs:__imp_GetCurrentThreadId
0x18014e142  mov     [rsp+38h+var_18], eax
0x18014e146  mov     r9d, 6
0x18014e14c  lea     r8, [rsp+38h+arg_0]
0x18014e151  mov     dl, sil
0x18014e154  mov     rcx, rdi
0x18014e157  call    ?PushBackBatchedData@SMarkerData@@QEAAPEAXW4EMarkerOp@@AEBT_LARGE_INTEGER@@IK@Z; SMarkerData::PushBackBatchedData(EMarkerOp,_LARGE_INTEGER const &,uint,ulong)
0x18014e15c  inc     qword ptr [rbx+99A8h]
0x18014e163  lea     rcx, [rbx+9F40h]
0x18014e16a  mov     rax, [rbx+0AD8h]
0x18014e171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e176  nop
0x18014e177  mov     rbx, [rsp+38h+arg_8]
0x18014e17c  mov     rsi, [rsp+38h+arg_10]
0x18014e181  add     rsp, 30h
0x18014e185  pop     rdi
0x18014e186  retn
0x18014e187  mov     rcx, rbx; this
0x18014e18a  call    ?FlushMarkerData@CContext@@QEAAXXZ; CContext::FlushMarkerData(void)
0x18014e18f  jmp     short loc_18014E125
```
