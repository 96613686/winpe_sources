# CallStackTracing::GetThreadRelativeContext(void)

- ea: `0x180056474`
- end: `0x1800564ff`
- name: `?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ`
- size: `139`
- prototype: `struct CallStackContext *__fastcall(CallStackTracing *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18005af70`
- `0x18005d000`

## callees

- `0x180056474`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800564e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800564e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800564ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800564ae`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005649e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005649e`

## pseudocode

```c
struct CallStackContext *__fastcall CallStackTracing::GetThreadRelativeContext(CallStackTracing *this)
{
  char *v1; // rbx
  DWORD LastError; // esi
  char *Value; // rax
  CallStackTracing *v5; // rcx
  __int64 v6; // rax

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
      v5 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v5 = (CallStackTracing *)&qword_18009CF60;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
      }
      v6 = (**(__int64 (__fastcall ***)(CallStackTracing *))v5)(v5);
      if ( v6 )
        v1 = (char *)v6;
    }
    SetLastError(LastError);
  }
  return (struct CallStackContext *)v1;
}

```

## disassembly

```asm
0x180056474  mov     [rsp+arg_0], rbx
0x180056479  mov     [rsp+arg_8], rsi
0x18005647e  push    rdi
0x18005647f  sub     rsp, 20h
0x180056483  cmp     byte ptr [rcx+8], 0
0x180056487  lea     rbx, [rcx+0D0h]
0x18005648e  mov     rdi, rcx
0x180056491  jz      short loc_1800564EC
0x180056493  call    cs:__imp_GetLastError
0x180056499  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18005649c  mov     esi, eax
0x18005649e  call    cs:__imp_TlsGetValue
0x1800564a4  test    rax, rax
0x1800564a7  jz      short loc_1800564AE
0x1800564a9  mov     rbx, rax
0x1800564ac  jmp     short loc_1800564E4
0x1800564ae  call    cs:__imp_GetLastError
0x1800564b4  test    eax, eax
0x1800564b6  jnz     short loc_1800564E4
0x1800564b8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800564bf  test    rcx, rcx
0x1800564c2  jnz     short loc_1800564D2
0x1800564c4  lea     rcx, qword_18009CF60
0x1800564cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800564d2  mov     rax, [rcx]
0x1800564d5  mov     rax, [rax]
0x1800564d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800564dd  test    rax, rax
0x1800564e0  cmovnz  rbx, rax
0x1800564e4  mov     ecx, esi; dwErrCode
0x1800564e6  call    cs:__imp_SetLastError
0x1800564ec  mov     rsi, [rsp+28h+arg_8]
0x1800564f1  mov     rax, rbx
0x1800564f4  mov     rbx, [rsp+28h+arg_0]
0x1800564f9  add     rsp, 20h
0x1800564fd  pop     rdi
0x1800564fe  retn
```
