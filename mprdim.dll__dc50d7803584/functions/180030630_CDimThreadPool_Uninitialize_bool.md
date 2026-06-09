# CDimThreadPool::Uninitialize(bool)

- ea: `0x180030630`
- end: `0x18003067f`
- name: `?Uninitialize@CDimThreadPool@@QEAAX_N@Z`
- size: `79`
- prototype: `void __fastcall(CDimThreadPool *__hidden this, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180013f9c`
- `0x1800304f8`

## callees

- `0x180030630`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180030652`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180030652`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180030668`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180030668`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180030648`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180030648`

## pseudocode

```c
void __fastcall CDimThreadPool::Uninitialize(CDimThreadPool *this, unsigned __int8 a2)
{
  struct _TP_CLEANUP_GROUP *v3; // rcx

  v3 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    CloseThreadpoolCleanupGroupMembers(v3, a2, 0);
    CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  if ( *(_QWORD *)this )
  {
    CloseThreadpool(*(PTP_POOL *)this);
    *(_QWORD *)this = 0;
  }
  *((_BYTE *)this + 88) = 0;
}

```

## disassembly

```asm
0x180030630  push    rbx
0x180030632  sub     rsp, 20h
0x180030636  mov     rbx, rcx
0x180030639  mov     rcx, [rcx+8]; ptpcg
0x18003063d  test    rcx, rcx
0x180030640  jz      short loc_180030660
0x180030642  movzx   edx, dl; fCancelPendingCallbacks
0x180030645  xor     r8d, r8d; pvCleanupContext
0x180030648  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18003064e  mov     rcx, [rbx+8]; ptpcg
0x180030652  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180030658  mov     qword ptr [rbx+8], 0
0x180030660  mov     rcx, [rbx]; ptpp
0x180030663  test    rcx, rcx
0x180030666  jz      short loc_180030675
0x180030668  call    cs:__imp_CloseThreadpool
0x18003066e  mov     qword ptr [rbx], 0
0x180030675  mov     byte ptr [rbx+58h], 0
0x180030679  add     rsp, 20h
0x18003067d  pop     rbx
0x18003067e  retn
```
