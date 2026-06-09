# _endthreadex

- ea: `0x18003e600`
- end: `0x18003e628`
- name: `_endthreadex`
- size: `40`
- prototype: `void __cdecl(unsigned int ReturnCode)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003e5b8`

## callees

- `0x180017b50`
- `0x18003e004`
- `0x18003e074`
- `0x18003e600`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18003e621`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18003e621`

## pseudocode

```c
void __cdecl __noreturn endthreadex(unsigned int ReturnCode)
{
  void *v2; // rax

  CrtSetDbgBlockType();
  v2 = (void *)getptd_noexit();
  if ( v2 )
    freeptd(v2);
  ExitThread(ReturnCode);
}

```

## disassembly

```asm
0x18003e600  push    rbx
0x18003e602  sub     rsp, 20h
0x18003e606  mov     ebx, ecx
0x18003e608  call    _CrtSetDbgBlockType
0x18003e60d  call    _getptd_noexit
0x18003e612  test    rax, rax
0x18003e615  jz      short loc_18003E61F
0x18003e617  mov     rcx, rax; lpFlsData
0x18003e61a  call    _freeptd
0x18003e61f  mov     ecx, ebx; dwExitCode
0x18003e621  call    cs:__imp_ExitThread
```
