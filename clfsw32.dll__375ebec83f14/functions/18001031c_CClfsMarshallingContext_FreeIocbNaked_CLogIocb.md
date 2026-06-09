# CClfsMarshallingContext::FreeIocbNaked(CLogIocb *)

- ea: `0x18001031c`
- end: `0x180010398`
- name: `?FreeIocbNaked@CClfsMarshallingContext@@AEAAXPEAVCLogIocb@@@Z`
- size: `124`
- prototype: `void(CClfsMarshallingContext *__hidden this, struct CLogIocb *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e004`
- `0x18000e534`
- `0x18000fa24`
- `0x18000fcdc`
- `0x1800101c8`
- `0x180010bdc`
- `0x1800135a4`

## callees

- `0x18000df4c`
- `0x18001031c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010380`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010370`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010370`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180010341`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPushEntrySList` at `0x180010341`

## pseudocode

```c
void __fastcall CClfsMarshallingContext::FreeIocbNaked(CClfsMarshallingContext *this, struct CLogIocb *a2)
{
  volatile signed __int32 *v3; // rbx

  v3 = (volatile signed __int32 *)((char *)this + 16);
  if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 8) > *((_DWORD *)this + 9) )
  {
    _InterlockedDecrement((volatile signed __int32 *)this + 8);
    if ( a2 )
    {
      CLogIocb::~CLogIocb(a2);
      if ( !HeapFree(g_hHeap, 0, a2) )
        GetLastError();
    }
  }
  else
  {
    InterlockedPushEntrySList((PSLIST_HEADER)this + 1, (PSLIST_ENTRY)a2);
    _InterlockedIncrement(v3 + 7);
  }
}

```

## disassembly

```asm
0x18001031c  mov     [rsp+arg_0], rbx
0x180010321  push    rdi
0x180010322  sub     rsp, 20h
0x180010326  mov     rdi, rdx
0x180010329  lea     rbx, [rcx+10h]
0x18001032d  mov     eax, 1
0x180010332  lock xadd [rbx+10h], eax
0x180010337  inc     eax
0x180010339  cmp     eax, [rbx+14h]
0x18001033c  ja      short loc_180010353
0x18001033e  mov     rcx, rbx; ListHead
0x180010341  call    cs:__imp_InterlockedPushEntrySList
0x180010348  nop     dword ptr [rax+rax+00h]
0x18001034d  lock inc dword ptr [rbx+1Ch]
0x180010351  jmp     short loc_18001038C
0x180010353  lock dec dword ptr [rbx+10h]
0x180010357  test    rdi, rdi
0x18001035a  jz      short loc_18001038C
0x18001035c  mov     rcx, rdi; this
0x18001035f  call    ??1CLogIocb@@QEAA@XZ; CLogIocb::~CLogIocb(void)
0x180010364  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x18001036b  mov     r8, rdi; lpMem
0x18001036e  xor     edx, edx; dwFlags
0x180010370  call    cs:__imp_HeapFree
0x180010377  nop     dword ptr [rax+rax+00h]
0x18001037c  test    eax, eax
0x18001037e  jnz     short loc_18001038C
0x180010380  call    cs:__imp_GetLastError
0x180010387  nop     dword ptr [rax+rax+00h]
0x18001038c  mov     rbx, [rsp+28h+arg_0]
0x180010391  add     rsp, 20h
0x180010395  pop     rdi
0x180010396  retn
```
