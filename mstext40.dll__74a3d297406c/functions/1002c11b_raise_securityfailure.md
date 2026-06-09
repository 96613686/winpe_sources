# ___raise_securityfailure

- ea: `0x1002c11b`
- end: `0x1002c158`
- name: `___raise_securityfailure`
- size: `61`
- prototype: `int __cdecl(struct _EXCEPTION_POINTERS *ExceptionInfo)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1002c158`
- `0x1002c25f`

## callees

- `0x1002c11b`
- `0x10030293`
- `0x10030620`
- `0x10030635`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1002c11e`
- `KERNEL32!IsDebuggerPresent` at `0x1002c11e`

## pseudocode

```c
int __cdecl __raise_securityfailure(struct _EXCEPTION_POINTERS *ExceptionInfo)
{
  dword_100446FC = IsDebuggerPresent();
  _crt_debugger_hook(1);
  __crtUnhandledException(ExceptionInfo);
  if ( !dword_100446FC )
    _crt_debugger_hook(1);
  return __crtTerminateProcess(0xC0000409);
}

```

## disassembly

```asm
0x1002c11b  push    ebp
0x1002c11c  mov     ebp, esp
0x1002c11e  call    ds:__imp__IsDebuggerPresent@0
0x1002c124  push    1
0x1002c126  mov     dword_100446FC, eax
0x1002c12b  call    __crt_debugger_hook
0x1002c130  push    [ebp+ExceptionInfo]; ExceptionInfo
0x1002c133  call    ___crtUnhandledException
0x1002c138  cmp     dword_100446FC, 0
0x1002c13f  pop     ecx
0x1002c140  pop     ecx
0x1002c141  jnz     short loc_1002C14B
0x1002c143  push    1
0x1002c145  call    __crt_debugger_hook
0x1002c14a  pop     ecx
0x1002c14b  push    0C0000409h; uExitCode
0x1002c150  call    ___crtTerminateProcess
0x1002c155  pop     ecx
0x1002c156  pop     ebp
0x1002c157  retn
```
