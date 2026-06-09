# CallStackScopeTrace::CallStackScopeTrace(char const *,long)

- ea: `0x180001ec8`
- end: `0x180001f6a`
- name: `??0CallStackScopeTrace@@QEAA@PEBDJ@Z`
- size: `162`
- prototype: `CallStackScopeTrace *__fastcall(CallStackScopeTrace *__hidden this, const char *, int)`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

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

- `0x180001ec8`
- `0x180002200`
- `0x18001e010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001eec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180001eec`

## pseudocode

```c
CallStackScopeTrace *__fastcall CallStackScopeTrace::CallStackScopeTrace(
        CallStackScopeTrace *this,
        const char *a2,
        int a3)
{
  void ***v5; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx

  v5 = (void ***)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
    CallStackTracing::s_wpInstance = v7;
    if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
    {
      v5 = (void ***)CallStackTracing::s_wpInstance;
    }
    else
    {
      v5 = &off_180022080;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&off_180022080;
    }
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    v8 = CallStackTracing::Context((CallStackTracing *)v5);
    v9 = *((unsigned int *)v8 + 497);
    if ( (unsigned int)v9 < *((_DWORD *)v8 + 498) )
    {
      v10 = 2 * v9;
      *((_QWORD *)v8 + v10) = a2;
      *((_DWORD *)v8 + 2 * v10 + 2) = a3;
    }
    ++*((_DWORD *)v8 + 497);
  }
  return this;
}

```

## disassembly

```asm
0x180001ec8  mov     [rsp+arg_0], rbx
0x180001ecd  mov     [rsp+arg_8], rsi
0x180001ed2  push    rdi
0x180001ed3  sub     rsp, 20h
0x180001ed7  mov     rbx, rcx
0x180001eda  mov     edi, r8d
0x180001edd  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001ee4  mov     rsi, rdx
0x180001ee7  test    rcx, rcx
0x180001eea  jnz     short loc_180001F2D
0x180001eec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180001ef2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180001ef9  mov     rcx, rax
0x180001efc  test    rax, rax
0x180001eff  jz      short loc_180001F1F
0x180001f01  mov     rax, [rax]
0x180001f04  mov     edx, 7F0h
0x180001f09  mov     rax, [rax+8]
0x180001f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f12  test    eax, eax
0x180001f14  jz      short loc_180001F1F
0x180001f16  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180001f1d  jmp     short loc_180001F2D
0x180001f1f  lea     rcx, off_180022080; this
0x180001f26  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180001f2d  cmp     byte ptr [rcx+8], 0
0x180001f31  jz      short loc_180001F57
0x180001f33  call    ?Context@CallStackTracing@@QEAAAEAVCallStackContext@@XZ; CallStackTracing::Context(void)
0x180001f38  mov     ecx, [rax+7C4h]
0x180001f3e  cmp     ecx, [rax+7C8h]
0x180001f44  jnb     short loc_180001F51
0x180001f46  add     rcx, rcx
0x180001f49  mov     [rax+rcx*8], rsi
0x180001f4d  mov     [rax+rcx*8+8], edi
0x180001f51  inc     dword ptr [rax+7C4h]
0x180001f57  mov     rsi, [rsp+28h+arg_8]
0x180001f5c  mov     rax, rbx
0x180001f5f  mov     rbx, [rsp+28h+arg_0]
0x180001f64  add     rsp, 20h
0x180001f68  pop     rdi
0x180001f69  retn
```
