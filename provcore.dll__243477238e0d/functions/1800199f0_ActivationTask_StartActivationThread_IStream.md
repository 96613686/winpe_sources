# ActivationTask::StartActivationThread(IStream *)

- ea: `0x1800199f0`
- end: `0x180019a6d`
- name: `?StartActivationThread@ActivationTask@@AEAAJPEAUIStream@@@Z`
- size: `125`
- prototype: `HRESULT __fastcall(ActivationTask *this, IStream *pStream)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180019810`

## callees

- `0x1800199f0`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180019a56`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180019a56`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180019a38`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x180019a38`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180019a04`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180019a04`

## pseudocode

```c
__int64 __fastcall ActivationTask::StartActivationThread(ActivationTask *this, IStream *pStream)
{
  void *v4; // rax

  ResetEvent(this->m_cancelEvent);
  pStream->AddRef(pStream);
  v4 = (void *)_o__beginthreadex(0, 0, ActivationTaskThreadThunk, pStream, 0, 0);
  this->m_taskThread = v4;
  if ( v4 )
    return 0;
  pStream->Release(pStream);
  return *(unsigned int *)_o__errno();
}

```

## disassembly

```asm
0x1800199f0  mov     [rsp+arg_0], rbx
0x1800199f5  push    rdi
0x1800199f6  sub     rsp, 30h
0x1800199fa  mov     rbx, this
0x1800199fd  mov     rdi, pStream
0x180019a00  mov     this, [this+40h]; hEvent
0x180019a04  call    cs:__imp_ResetEvent
0x180019a0a  mov     rax, [rdi]
0x180019a0d  mov     this, rdi
0x180019a10  mov     rax, [rax+8]
0x180019a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a19  mov     r9, rdi
0x180019a1c  mov     [rsp+38h+var_10], 0
0x180019a25  lea     r8, ?ActivationTaskThreadThunk@@YAIPEAX@Z; ActivationTaskThreadThunk(void *)
0x180019a2c  mov     [rsp+38h+var_18], 0
0x180019a34  xor     edx, edx
0x180019a36  xor     ecx, ecx
0x180019a38  call    cs:__imp__o__beginthreadex
0x180019a3e  mov     [rbx+48h], rax
0x180019a42  test    rax, rax
0x180019a45  jnz     short loc_180019A60
0x180019a47  mov     rax, [rdi]
0x180019a4a  mov     this, rdi
0x180019a4d  mov     rax, [rax+10h]
0x180019a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a56  call    cs:__imp__o__errno
0x180019a5c  mov     eax, [rax]
0x180019a5e  jmp     short loc_180019A62
0x180019a60  xor     eax, eax
0x180019a62  mov     rbx, [rsp+38h+arg_0]
0x180019a67  add     rsp, 30h
0x180019a6b  pop     rdi
0x180019a6c  retn
```
