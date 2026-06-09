# CallStackTracing::GetThreadRelativeContext(void)

- ea: `0x180001a90`
- end: `0x180001b1d`
- name: `?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ`
- size: `141`
- prototype: `struct CallStackContext *__fastcall(CallStackTracing *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ad0`

## callees

- `0x180001a90`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001aca`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180001aca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001aaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001aaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001b11`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001aba`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180001aba`

## pseudocode

```c
struct CallStackContext *__fastcall CallStackTracing::GetThreadRelativeContext(CallStackTracing *this)
{
  char *v1; // rdi
  DWORD LastError; // esi
  char *Value; // rax
  struct CallStackTracing *v6; // rcx
  __int64 v7; // rax

  v1 = (char *)this + 208;
  if ( *((_BYTE *)this + 8) )
  {
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)this + 3));
    if ( Value )
    {
      v1 = Value;
    }
    else if ( !GetLastError() )
    {
      v6 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v6 = (struct CallStackTracing *)&qword_18000A4C0;
        CallStackTracing::s_wpInstance = (struct CallStackTracing *)&qword_18000A4C0;
      }
      v7 = (**(__int64 (__fastcall ***)(struct CallStackTracing *))v6)(v6);
      if ( v7 )
        v1 = (char *)v7;
    }
    SetLastError(LastError);
  }
  return (struct CallStackContext *)v1;
}

```

## disassembly

```asm
0x180001a90  mov     [rsp+arg_8], rbx
0x180001a95  push    rdi
0x180001a96  sub     rsp, 20h
0x180001a9a  cmp     byte ptr [rcx+8], 0
0x180001a9e  lea     rdi, [rcx+0D0h]
0x180001aa5  mov     rbx, rcx
0x180001aa8  jz      short loc_180001AD5
0x180001aaa  mov     [rsp+28h+arg_0], rsi
0x180001aaf  call    cs:__imp_GetLastError
0x180001ab5  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180001ab8  mov     esi, eax
0x180001aba  call    cs:__imp_TlsGetValue
0x180001ac0  test    rax, rax
0x180001ac3  jz      short loc_180001B11
0x180001ac5  mov     rdi, rax
0x180001ac8  mov     ecx, esi; dwErrCode
0x180001aca  call    cs:__imp_SetLastError
0x180001ad0  mov     rsi, [rsp+28h+arg_0]
0x180001ad5  mov     rbx, [rsp+28h+arg_8]
0x180001ada  mov     rax, rdi
0x180001add  add     rsp, 20h
0x180001ae1  pop     rdi
0x180001ae2  retn
0x180001ae3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001aea  test    rcx, rcx
0x180001aed  jnz     short loc_180001AFD
0x180001aef  lea     rcx, qword_18000A4C0
0x180001af6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001afd  mov     rax, [rcx]
0x180001b00  mov     rax, [rax]
0x180001b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b08  test    rax, rax
0x180001b0b  cmovnz  rdi, rax
0x180001b0f  jmp     short loc_180001AC8
0x180001b11  call    cs:__imp_GetLastError
0x180001b17  test    eax, eax
0x180001b19  jnz     short loc_180001AC8
0x180001b1b  jmp     short loc_180001AE3
```
