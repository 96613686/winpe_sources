# winrt::impl::resume_apartment_on_threadpool(winrt::com_ptr<winrt::impl::IContextCallback> const &,std::experimental::coroutine_handle<void>,int *)

- ea: `0x180015c30`
- end: `0x180015ca3`
- name: `?resume_apartment_on_threadpool@impl@winrt@@YAXAEBU?$com_ptr@UIContextCallback@impl@winrt@@@2@U?$coroutine_handle@X@experimental@std@@PEAH@Z`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180015b40`

## callees

- `0x180002158`
- `0x1800143a8`
- `0x180015c30`
- `0x180015dfc`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::impl::resume_apartment_on_threadpool(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 *v6; // rsi
  void *v7; // r8
  __int64 v8; // rcx
  __int64 *v9; // [rsp+68h] [rbp+20h] BYREF

  v6 = (__int64 *)operator new(0x18u);
  v9 = v6;
  v8 = *a1;
  *v6 = *a1;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
  v6[1] = a2;
  v6[2] = a3;
  v9 = v6;
  winrt::impl::submit_threadpool_callback(
    (winrt::impl *)winrt::impl::fallback_submit_threadpool_callback,
    (void (*)(void *, void *))v6,
    v7);
  v9 = 0;
  std::unique_ptr<winrt::impl::threadpool_resume>::~unique_ptr<winrt::impl::threadpool_resume>(&v9);
}

```

## disassembly

```asm
0x180015c30  push    rbx
0x180015c32  push    rbp
0x180015c33  push    rsi
0x180015c34  push    rdi
0x180015c35  sub     rsp, 28h
0x180015c39  mov     rbp, r8
0x180015c3c  mov     rbx, rdx
0x180015c3f  mov     rdi, rcx
0x180015c42  mov     ecx, 18h; Size
0x180015c47  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015c4c  mov     rsi, rax
0x180015c4f  mov     [rsp+48h+arg_18], rax
0x180015c54  mov     rcx, [rdi]
0x180015c57  mov     [rax], rcx
0x180015c5a  test    rcx, rcx
0x180015c5d  jz      short loc_180015C6B
0x180015c5f  mov     rdx, [rcx]
0x180015c62  mov     rax, [rdx+8]
0x180015c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c6b  mov     [rsi+8], rbx
0x180015c6f  mov     [rsi+10h], rbp
0x180015c73  mov     [rsp+48h+arg_18], rsi
0x180015c78  mov     rdx, rsi; void (*)(void *, void *)
0x180015c7b  lea     rcx, ?fallback_submit_threadpool_callback@impl@winrt@@YAXPEAX0@Z; this
0x180015c82  call    ?submit_threadpool_callback@impl@winrt@@YA@P6AXPEAX0@Z0@Z; winrt::impl::submit_threadpool_callback(void (*)(void *,void *),void *)
0x180015c87  mov     [rsp+48h+arg_18], 0
0x180015c90  lea     rcx, [rsp+48h+arg_18]
0x180015c95  call    ??1?$unique_ptr@Uthreadpool_resume@impl@winrt@@U?$default_delete@Uthreadpool_resume@impl@winrt@@@std@@@std@@QEAA@XZ; std::unique_ptr<winrt::impl::threadpool_resume>::~unique_ptr<winrt::impl::threadpool_resume>(void)
0x180015c9a  add     rsp, 28h
0x180015c9e  pop     rdi
0x180015c9f  pop     rsi
0x180015ca0  pop     rbp
0x180015ca1  pop     rbx
0x180015ca2  retn
```
