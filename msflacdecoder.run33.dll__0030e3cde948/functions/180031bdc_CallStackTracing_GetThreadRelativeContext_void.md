# CallStackTracing::GetThreadRelativeContext(void)

- ea: `0x180031bdc`
- end: `0x180031c9e`
- name: `?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ`
- size: `194`
- prototype: `struct CallStackContext *__fastcall(CallStackTracing *__hidden this)`
- caller_count: `113`
- callee_count: `2`
- tags: ``

## callers

- `0x18002fce8`
- `0x18002fff0`
- `0x1800300e0`
- `0x18003051c`
- `0x1800309d0`
- `0x180030f28`
- `0x1800310e0`
- `0x180031440`
- `0x1800316e0`
- `0x180031ca4`
- `0x180032ab0`
- `0x180033730`
- `0x1800342f0`
- `0x1800344c0`
- `0x180034be8`
- `0x180035148`
- `0x180036d48`
- `0x18003733c`
- `0x1800377c4`
- `0x1800378f8`
- `0x180037a1c`
- `0x180037f6c`
- `0x1800382c0`
- `0x180038598`
- `0x180038840`
- `0x180038b38`
- `0x180039270`
- `0x180039448`
- `0x18003ac10`
- `0x18003b220`
- `0x18003b440`
- `0x18003b5b8`
- `0x18003b8f0`
- `0x18003ba10`
- `0x18003bb98`
- `0x18003bfb0`
- `0x18003c880`
- `0x18003cad0`
- `0x18003cca0`
- `0x18003d0b0`
- `0x18003d500`
- `0x18003d710`
- `0x18003d820`
- `0x18003db20`
- `0x18003e1a0`
- `0x18003e360`
- `0x18003e770`
- `0x18003e940`
- `0x18003ec70`
- `0x18003efe0`

## callees

- `0x180031bdc`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031c85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031c85`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031c0a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180031c0a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031c30`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180031c30`

## pseudocode

```c
struct CallStackContext *__fastcall CallStackTracing::GetThreadRelativeContext(CallStackTracing *this)
{
  char *v1; // rbx
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v5; // rdx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  __int64 v8; // rax

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
      v6 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
        CallStackTracing::s_wpInstance = v7;
        if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
        {
          v6 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v6 = &qword_18006EB20;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18006EB20;
        }
      }
      v8 = (*(__int64 (__fastcall **)(__int64 *))*v6)(v6);
      if ( v8 )
        v1 = (char *)v8;
    }
    SetLastError(LastError);
  }
  return (struct CallStackContext *)v1;
}

```

## disassembly

```asm
0x180031bdc  mov     [rsp+arg_0], rbx
0x180031be1  mov     [rsp+arg_8], rsi
0x180031be6  push    rdi
0x180031be7  sub     rsp, 20h
0x180031beb  cmp     byte ptr [rcx+8], 0
0x180031bef  lea     rbx, [rcx+0D0h]
0x180031bf6  mov     rdi, rcx
0x180031bf9  jz      loc_180031C8B
0x180031bff  call    cs:__imp_GetLastError
0x180031c05  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180031c08  mov     esi, eax
0x180031c0a  call    cs:__imp_TlsGetValue
0x180031c10  test    rax, rax
0x180031c13  jz      short loc_180031C1A
0x180031c15  mov     rbx, rax
0x180031c18  jmp     short loc_180031C83
0x180031c1a  call    cs:__imp_GetLastError
0x180031c20  test    eax, eax
0x180031c22  jnz     short loc_180031C83
0x180031c24  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031c2b  test    rcx, rcx
0x180031c2e  jnz     short loc_180031C71
0x180031c30  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180031c36  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180031c3d  mov     rcx, rax
0x180031c40  test    rax, rax
0x180031c43  jz      short loc_180031C63
0x180031c45  mov     rax, [rax]
0x180031c48  mov     edx, 7F0h
0x180031c4d  mov     rax, [rax+8]
0x180031c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c56  test    eax, eax
0x180031c58  jz      short loc_180031C63
0x180031c5a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180031c61  jmp     short loc_180031C71
0x180031c63  lea     rcx, qword_18006EB20
0x180031c6a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180031c71  mov     rax, [rcx]
0x180031c74  mov     rax, [rax]
0x180031c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c7c  test    rax, rax
0x180031c7f  cmovnz  rbx, rax
0x180031c83  mov     ecx, esi; dwErrCode
0x180031c85  call    cs:__imp_SetLastError
0x180031c8b  mov     rsi, [rsp+28h+arg_8]
0x180031c90  mov     rax, rbx
0x180031c93  mov     rbx, [rsp+28h+arg_0]
0x180031c98  add     rsp, 20h
0x180031c9c  pop     rdi
0x180031c9d  retn
```
