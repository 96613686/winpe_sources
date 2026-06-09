# CMFD3D12Buffer::SetBufferReadOnly(int)

- ea: `0x18005f590`
- end: `0x18005f657`
- name: `?SetBufferReadOnly@CMFD3D12Buffer@@UEAAJH@Z`
- size: `199`
- prototype: `__int64 __fastcall(CMFD3D12Buffer *__hidden this, int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18005f590`
- `0x18006dc78`
- `0x180070010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f626`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5ee`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005f5de`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005f5de`

## string_xrefs

- `0x18005f637`: `CMFD3D12Buffer::SetBufferReadOnly`

## pseudocode

```c
__int64 __fastcall CMFD3D12Buffer::SetBufferReadOnly(CMFD3D12Buffer *this, int a2)
{
  unsigned int v2; // edi
  CallStackTracing *v3; // rbx
  CallStackContext *v4; // rsi
  DWORD LastError; // ebp
  CallStackContext *Value; // rax
  CallStackTracing *v7; // rcx
  __int64 v8; // rax

  v2 = 0;
  if ( !a2 )
  {
    v3 = CallStackTracing::s_wpInstance;
    v2 = -1072875854;
    if ( !CallStackTracing::s_wpInstance )
    {
      v3 = (CallStackTracing *)&qword_18009CF60;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
    }
    if ( *((_BYTE *)v3 + 8) )
    {
      v4 = (CallStackTracing *)((char *)v3 + 208);
      LastError = GetLastError();
      Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v3 + 3));
      if ( Value )
      {
        v4 = Value;
      }
      else if ( !GetLastError() )
      {
        v7 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v7 = (CallStackTracing *)&qword_18009CF60;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18009CF60;
        }
        v8 = (**(__int64 (__fastcall ***)(CallStackTracing *))v7)(v7);
        if ( v8 )
          v4 = (CallStackContext *)v8;
      }
      SetLastError(LastError);
      if ( *((_DWORD *)v4 + 499) != -1072875854 )
        CallStackContext::TraceFailure(v4, "CMFD3D12Buffer::SetBufferReadOnly", 692, -1072875854);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18005f590  push    rbx
0x18005f592  push    rbp
0x18005f593  push    rsi
0x18005f594  push    rdi
0x18005f595  sub     rsp, 28h
0x18005f599  xor     edi, edi
0x18005f59b  test    edx, edx
0x18005f59d  jnz     loc_18005F64C
0x18005f5a3  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f5aa  mov     edi, 0C00D36B2h
0x18005f5af  test    rbx, rbx
0x18005f5b2  jnz     short loc_18005F5C2
0x18005f5b4  lea     rbx, qword_18009CF60
0x18005f5bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f5c2  cmp     byte ptr [rbx+8], 0
0x18005f5c6  jz      loc_18005F64C
0x18005f5cc  lea     rsi, [rbx+0D0h]
0x18005f5d3  call    cs:__imp_GetLastError
0x18005f5d9  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18005f5dc  mov     ebp, eax
0x18005f5de  call    cs:__imp_TlsGetValue
0x18005f5e4  test    rax, rax
0x18005f5e7  jz      short loc_18005F5EE
0x18005f5e9  mov     rsi, rax
0x18005f5ec  jmp     short loc_18005F624
0x18005f5ee  call    cs:__imp_GetLastError
0x18005f5f4  test    eax, eax
0x18005f5f6  jnz     short loc_18005F624
0x18005f5f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f5ff  test    rcx, rcx
0x18005f602  jnz     short loc_18005F612
0x18005f604  lea     rcx, qword_18009CF60
0x18005f60b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18005f612  mov     rax, [rcx]
0x18005f615  mov     rax, [rax]
0x18005f618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f61d  test    rax, rax
0x18005f620  cmovnz  rsi, rax
0x18005f624  mov     ecx, ebp; dwErrCode
0x18005f626  call    cs:__imp_SetLastError
0x18005f62c  cmp     [rsi+7CCh], edi
0x18005f632  jz      short loc_18005F64C
0x18005f634  mov     r9d, edi; int
0x18005f637  lea     rdx, aCmfd3d12buffer_6; "CMFD3D12Buffer::SetBufferReadOnly"
0x18005f63e  mov     r8d, 2B4h; int
0x18005f644  mov     rcx, rsi; this
0x18005f647  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18005f64c  mov     eax, edi
0x18005f64e  add     rsp, 28h
0x18005f652  pop     rdi
0x18005f653  pop     rsi
0x18005f654  pop     rbp
0x18005f655  pop     rbx
0x18005f656  retn
```
