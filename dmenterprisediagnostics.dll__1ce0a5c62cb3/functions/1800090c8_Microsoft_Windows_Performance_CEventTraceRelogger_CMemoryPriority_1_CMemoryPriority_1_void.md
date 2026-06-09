# Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::~CMemoryPriority<1>(void)

- ea: `0x1800090c8`
- end: `0x180009102`
- name: `??1?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000bd60`

## callees

- `0x1800090c8`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800090dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800090dd`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::~CMemoryPriority<1>(
        __int64 a1)
{
  void (__fastcall *v1)(HANDLE, _QWORD, int *, __int64); // rbx
  HANDLE CurrentThread; // rax
  int v3; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(void (__fastcall **)(HANDLE, _QWORD, int *, __int64))a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(_DWORD *)(a1 + 16);
    CurrentThread = GetCurrentThread();
    v1(CurrentThread, 0, &v3, 4);
  }
}

```

## disassembly

```asm
0x1800090c8  push    rbx
0x1800090ca  sub     rsp, 30h
0x1800090ce  mov     rbx, [rcx]
0x1800090d1  test    rbx, rbx
0x1800090d4  jz      short loc_1800090FC
0x1800090d6  mov     ecx, [rcx+10h]
0x1800090d9  mov     [rsp+38h+arg_0], ecx
0x1800090dd  call    cs:__imp_GetCurrentThread
0x1800090e3  mov     rcx, rax
0x1800090e6  mov     r9d, 4
0x1800090ec  lea     r8, [rsp+38h+arg_0]
0x1800090f1  xor     edx, edx
0x1800090f3  mov     rax, rbx
0x1800090f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090fb  nop
0x1800090fc  add     rsp, 30h
0x180009100  pop     rbx
0x180009101  retn
```
