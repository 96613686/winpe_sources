# CallStackTracing::Context(void)

- ea: `0x180002200`
- end: `0x1800022c2`
- name: `?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ`
- size: `194`
- prototype: `struct CallStackContext *__fastcall(CallStackTracing *__hidden this)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x180001ec8`
- `0x180002370`
- `0x180002540`
- `0x180002810`
- `0x180002ac0`
- `0x180003678`
- `0x1800039e0`
- `0x180003e30`
- `0x180004060`
- `0x1800041dc`
- `0x18000440c`
- `0x180004818`
- `0x180004c54`
- `0x180004fc0`
- `0x180005340`
- `0x1800057a0`
- `0x180005db0`
- `0x180005fbc`
- `0x180006b70`
- `0x180006fd4`

## callees

- `0x180002200`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800022a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800022a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000223e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000223e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000222e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000222e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180002254`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180002254`

## pseudocode

```c
struct CallStackContext *__fastcall CallStackTracing::Context(CallStackTracing *this)
{
  char *v1; // rbx
  DWORD LastError; // esi
  char *Value; // rax
  void ***v5; // rcx
  CallStackTracing *v6; // rax
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
      v5 = (void ***)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v6;
        if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
        {
          v5 = (void ***)CallStackTracing::s_wpInstance;
        }
        else
        {
          v5 = &off_180022080;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
        }
      }
      v7 = ((__int64 (__fastcall *)(void ***))**v5)(v5);
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
0x180002200  mov     [rsp+arg_0], rbx
0x180002205  mov     [rsp+arg_8], rsi
0x18000220a  push    rdi
0x18000220b  sub     rsp, 20h
0x18000220f  cmp     byte ptr [rcx+8], 0
0x180002213  lea     rbx, [rcx+0D0h]
0x18000221a  mov     rdi, rcx
0x18000221d  jz      loc_1800022AF
0x180002223  call    cs:__imp_GetLastError
0x180002229  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18000222c  mov     esi, eax
0x18000222e  call    cs:__imp_TlsGetValue
0x180002234  test    rax, rax
0x180002237  jz      short loc_18000223E
0x180002239  mov     rbx, rax
0x18000223c  jmp     short loc_1800022A7
0x18000223e  call    cs:__imp_GetLastError
0x180002244  test    eax, eax
0x180002246  jnz     short loc_1800022A7
0x180002248  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000224f  test    rcx, rcx
0x180002252  jnz     short loc_180002295
0x180002254  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18000225a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180002261  mov     rcx, rax
0x180002264  test    rax, rax
0x180002267  jz      short loc_180002287
0x180002269  mov     rax, [rax]
0x18000226c  mov     edx, 7F0h
0x180002271  mov     rax, [rax+8]
0x180002275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000227a  test    eax, eax
0x18000227c  jz      short loc_180002287
0x18000227e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180002285  jmp     short loc_180002295
0x180002287  lea     rcx, off_180022080
0x18000228e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180002295  mov     rax, [rcx]
0x180002298  mov     rax, [rax]
0x18000229b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022a0  test    rax, rax
0x1800022a3  cmovnz  rbx, rax
0x1800022a7  mov     ecx, esi; dwErrCode
0x1800022a9  call    cs:__imp_SetLastError
0x1800022af  mov     rsi, [rsp+28h+arg_8]
0x1800022b4  mov     rax, rbx
0x1800022b7  mov     rbx, [rsp+28h+arg_0]
0x1800022bc  add     rsp, 20h
0x1800022c0  pop     rdi
0x1800022c1  retn
```
