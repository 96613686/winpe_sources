# PurgeTask::StartPurgeThread(IStream *)

- ea: `0x18003959c`
- end: `0x18003960f`
- name: `?StartPurgeThread@PurgeTask@@AEAAJPEAUIStream@@@Z`
- size: `115`
- prototype: `HRESULT __fastcall(PurgeTask *this, IStream *pStream)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800393f0`

## callees

- `0x18003959c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800395f8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800395f8`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800395da`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800395da`

## pseudocode

```c
__int64 __fastcall PurgeTask::StartPurgeThread(PurgeTask *this, IStream *pStream)
{
  void *v4; // rax

  pStream->AddRef(pStream);
  v4 = (void *)_o__beginthreadex(0, 0, PurgeTaskThreadThunk, pStream, 0, 0);
  this->m_taskThread = v4;
  if ( v4 )
    return 0;
  pStream->Release(pStream);
  return *(unsigned int *)_o__errno();
}

```

## disassembly

```asm
0x18003959c  mov     [rsp+arg_0], rbx
0x1800395a1  push    rdi
0x1800395a2  sub     rsp, 30h
0x1800395a6  mov     rax, [pStream]
0x1800395a9  mov     rbx, this
0x1800395ac  mov     this, pStream
0x1800395af  mov     rdi, pStream
0x1800395b2  mov     rax, [rax+8]
0x1800395b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395bb  mov     r9, rdi
0x1800395be  mov     [rsp+38h+var_10], 0
0x1800395c7  lea     r8, ?PurgeTaskThreadThunk@@YAIPEAX@Z; PurgeTaskThreadThunk(void *)
0x1800395ce  mov     [rsp+38h+var_18], 0
0x1800395d6  xor     edx, edx
0x1800395d8  xor     ecx, ecx
0x1800395da  call    cs:__imp__o__beginthreadex
0x1800395e0  mov     [rbx+40h], rax
0x1800395e4  test    rax, rax
0x1800395e7  jnz     short loc_180039602
0x1800395e9  mov     rax, [rdi]
0x1800395ec  mov     this, rdi
0x1800395ef  mov     rax, [rax+10h]
0x1800395f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395f8  call    cs:__imp__o__errno
0x1800395fe  mov     eax, [rax]
0x180039600  jmp     short loc_180039604
0x180039602  xor     eax, eax
0x180039604  mov     rbx, [rsp+38h+arg_0]
0x180039609  add     rsp, 30h
0x18003960d  pop     rdi
0x18003960e  retn
```
