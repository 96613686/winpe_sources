# _endthread

- ea: `0x18003e3e0`
- end: `0x18003e419`
- name: `_endthread`
- size: `57`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003e3a8`

## callees

- `0x180017b50`
- `0x18003e004`
- `0x18003e074`
- `0x18003e3e0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e402`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e402`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18003e412`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18003e412`

## pseudocode

```c
void __cdecl __noreturn endthread()
{
  __int64 v0; // rax
  void *v1; // rbx
  void *v2; // rcx

  CrtSetDbgBlockType();
  v0 = getptd_noexit();
  v1 = (void *)v0;
  if ( v0 )
  {
    v2 = *(void **)(v0 + 8);
    if ( v2 != (void *)-1LL )
      CloseHandle(v2);
    freeptd(v1);
  }
  ExitThread(0);
}

```

## disassembly

```asm
0x18003e3e0  push    rbx
0x18003e3e2  sub     rsp, 20h
0x18003e3e6  call    _CrtSetDbgBlockType
0x18003e3eb  call    _getptd_noexit
0x18003e3f0  mov     rbx, rax
0x18003e3f3  test    rax, rax
0x18003e3f6  jz      short loc_18003E410
0x18003e3f8  mov     rcx, [rax+8]; hObject
0x18003e3fc  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003e400  jz      short loc_18003E408
0x18003e402  call    cs:__imp_CloseHandle
0x18003e408  mov     rcx, rbx; lpFlsData
0x18003e40b  call    _freeptd
0x18003e410  xor     ecx, ecx; dwExitCode
0x18003e412  call    cs:__imp_ExitThread
```
