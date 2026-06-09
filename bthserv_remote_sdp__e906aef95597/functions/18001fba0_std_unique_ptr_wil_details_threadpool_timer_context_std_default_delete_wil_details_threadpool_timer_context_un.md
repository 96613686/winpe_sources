# std::unique_ptr<wil::details::threadpool_timer_context,std::default_delete<wil::details::threadpool_timer_context>>::~unique_ptr<wil::details::threadpool_timer_context,std::default_delete<wil::details::threadpool_timer_context>>(void)

- ea: `0x18001fba0`
- end: `0x18001fc0c`
- name: `??1?$unique_ptr@Uthreadpool_timer_context@details@wil@@U?$default_delete@Uthreadpool_timer_context@details@wil@@@std@@@std@@QEAA@XZ`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180020938`

## callees

- `0x180001b94`
- `0x18001fba0`
- `0x18001fdb4`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fbbb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fbbb`

## pseudocode

```c
void __fastcall std::unique_ptr<wil::details::threadpool_timer_context>::~unique_ptr<wil::details::threadpool_timer_context>(
        wil::details::threadpool_object_context **a1,
        __int64 a2)
{
  wil::details::threadpool_object_context *v2; // rbx
  struct _TP_TIMER *v3; // rcx
  _QWORD *v4; // rcx

  v2 = *a1;
  if ( *a1 )
  {
    v3 = (struct _TP_TIMER *)*((_QWORD *)v2 + 10);
    if ( v3 )
      CloseThreadpoolTimer(v3);
    v4 = (_QWORD *)*((_QWORD *)v2 + 9);
    if ( v4 )
    {
      LOBYTE(a2) = v4 != (_QWORD *)((char *)v2 + 16);
      (*(void (__fastcall **)(_QWORD *, __int64))(*v4 + 32LL))(v4, a2);
      *((_QWORD *)v2 + 9) = 0;
    }
    wil::details::threadpool_object_context::~threadpool_object_context(v2);
    operator delete(v2, (const struct std::nothrow_t *)0x68);
  }
}

```

## disassembly

```asm
0x18001fba0  mov     [rsp+arg_0], rbx
0x18001fba5  push    rdi
0x18001fba6  sub     rsp, 20h
0x18001fbaa  mov     rbx, [rcx]
0x18001fbad  test    rbx, rbx
0x18001fbb0  jz      short loc_18001FC00
0x18001fbb2  mov     rcx, [rbx+50h]; pti
0x18001fbb6  test    rcx, rcx
0x18001fbb9  jz      short loc_18001FBC7
0x18001fbbb  call    cs:__imp_CloseThreadpoolTimer
0x18001fbc2  nop     dword ptr [rax+rax+00h]
0x18001fbc7  lea     rdi, [rbx+10h]
0x18001fbcb  mov     rcx, [rdi+38h]
0x18001fbcf  test    rcx, rcx
0x18001fbd2  jz      short loc_18001FBEB
0x18001fbd4  mov     rax, [rcx]
0x18001fbd7  cmp     rcx, rdi
0x18001fbda  setnz   dl
0x18001fbdd  mov     rax, [rax+20h]
0x18001fbe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbe6  and     qword ptr [rdi+38h], 0
0x18001fbeb  mov     rcx, rbx; this
0x18001fbee  call    ??1threadpool_object_context@details@wil@@QEAA@XZ; wil::details::threadpool_object_context::~threadpool_object_context(void)
0x18001fbf3  mov     edx, 68h ; 'h'; struct std::nothrow_t *
0x18001fbf8  mov     rcx, rbx; void *
0x18001fbfb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fc00  mov     rbx, [rsp+28h+arg_0]
0x18001fc05  add     rsp, 20h
0x18001fc09  pop     rdi
0x18001fc0a  retn
```
