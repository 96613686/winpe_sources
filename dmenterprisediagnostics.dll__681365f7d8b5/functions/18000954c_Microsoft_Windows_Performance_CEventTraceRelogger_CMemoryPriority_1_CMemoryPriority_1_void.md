# Microsoft::Windows::Performance::CEventTraceRelogger::CMemoryPriority<1>::~CMemoryPriority<1>(void)

- ea: `0x18000954c`
- end: `0x18000958d`
- name: `??1?$CMemoryPriority@$00@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c2e0`

## callees

- `0x18000954c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009561`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180009561`

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
0x18000954c  push    rbx
0x18000954e  sub     rsp, 30h
0x180009552  mov     rbx, [rcx]
0x180009555  test    rbx, rbx
0x180009558  jz      short loc_180009586
0x18000955a  mov     ecx, [rcx+10h]
0x18000955d  mov     [rsp+38h+arg_0], ecx
0x180009561  call    cs:__imp_GetCurrentThread
0x180009568  nop     dword ptr [rax+rax+00h]
0x18000956d  mov     rcx, rax
0x180009570  mov     r9d, 4
0x180009576  lea     r8, [rsp+38h+arg_0]
0x18000957b  xor     edx, edx
0x18000957d  mov     rax, rbx
0x180009580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009585  nop
0x180009586  add     rsp, 30h
0x18000958a  pop     rbx
0x18000958b  retn
```
