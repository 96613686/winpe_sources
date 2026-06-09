# acmInitialize

- ea: `0x1800064a0`
- end: `0x18000654f`
- name: `acmInitialize`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180007400`

## callees

- `0x1800064a0`
- `0x180006560`
- `0x1800065c0`
- `0x1800065e0`
- `0x180006690`
- `0x1800087b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180006504`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x180006504`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006534`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180006534`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800064ee`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800064ee`

## pseudocode

```c
__int64 __fastcall acmInitialize(__int64 a1)
{
  __int64 v3; // rax
  __int64 v4; // rbx

  if ( gplag )
  {
    ++*(_DWORD *)(gplag + 12);
    return 1;
  }
  v3 = pagNew();
  v4 = v3;
  if ( v3 )
  {
    *(_QWORD *)(v3 + 12) = 1;
    *(_QWORD *)(v3 + 88) = a1;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v3 + 24));
    *(_DWORD *)(v4 + 208) = TlsAlloc();
    threadInitialize(v4);
    if ( (unsigned int)InitializeLock((LPCRITICAL_SECTION)(v4 + 128)) )
      return 1;
    threadTerminateProcess(v4);
    DeleteCriticalSection((LPCRITICAL_SECTION)(v4 + 24));
    pagDelete(v4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800064a0  mov     [rsp+arg_0], rbx
0x1800064a5  push    rdi
0x1800064a6  sub     rsp, 20h
0x1800064aa  mov     rdi, rcx
0x1800064ad  mov     rax, cs:gplag
0x1800064b4  test    rax, rax
0x1800064b7  jz      short loc_1800064CC
0x1800064b9  inc     dword ptr [rax+0Ch]
0x1800064bc  mov     eax, 1
0x1800064c1  mov     rbx, [rsp+28h+arg_0]
0x1800064c6  add     rsp, 20h
0x1800064ca  pop     rdi
0x1800064cb  retn
0x1800064cc  call    pagNew
0x1800064d1  mov     rbx, rax
0x1800064d4  mov     [rsp+28h+arg_10], rax
0x1800064d9  test    rax, rax
0x1800064dc  jz      short loc_180006542
0x1800064de  mov     qword ptr [rax+0Ch], 1
0x1800064e6  mov     [rax+58h], rdi
0x1800064ea  lea     rcx, [rax+18h]; lpCriticalSection
0x1800064ee  call    cs:__imp_InitializeCriticalSection
0x1800064f4  jmp     short loc_180006504
0x1800064f6  mov     rcx, [rsp+28h+arg_10]
0x1800064fb  call    pagDelete
0x180006500  xor     eax, eax
0x180006502  jmp     short loc_1800064C1
0x180006504  call    cs:__imp_TlsAlloc
0x18000650a  mov     [rbx+0D0h], eax
0x180006510  mov     rcx, rbx
0x180006513  call    threadInitialize
0x180006518  lea     rcx, [rbx+80h]; lpCriticalSection
0x18000651f  call    InitializeLock
0x180006524  test    eax, eax
0x180006526  jnz     short loc_1800064BC
0x180006528  mov     rcx, rbx
0x18000652b  call    threadTerminateProcess
0x180006530  lea     rcx, [rbx+18h]; lpCriticalSection
0x180006534  call    cs:__imp_DeleteCriticalSection
0x18000653a  mov     rcx, rbx
0x18000653d  call    pagDelete
0x180006542  xor     eax, eax
0x180006544  mov     rbx, [rsp+28h+arg_0]
0x180006549  add     rsp, 20h
0x18000654d  pop     rdi
0x18000654e  retn
```
