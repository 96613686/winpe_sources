# winrt::impl::submit_threadpool_callback(void (*)(void *,void *),void *)

- ea: `0x180015dfc`
- end: `0x180015e24`
- name: `?submit_threadpool_callback@impl@winrt@@YA@P6AXPEAX0@Z0@Z`
- size: `40`
- prototype: `__int64 __fastcall(winrt::impl *__hidden this, void (*)(void *, void *), void *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800154e8`
- `0x180015b40`
- `0x180015c30`

## callees

- `0x1800024c8`
- `0x1800058c4`
- `0x180015dfc`
- `0x180015e80`

## pseudocode

```c
BOOL __fastcall winrt::impl::submit_threadpool_callback(winrt::impl *this, void (*a2)(void *, void *), void *a3)
{
  BOOL result; // eax
  winrt *v4; // rax
  const struct winrt::impl::slim_source_location *v5; // rdx
  _BYTE v6[40]; // [rsp+20h] [rbp-28h] BYREF

  result = TrySubmitThreadpoolCallback_0((PTP_SIMPLE_CALLBACK)this, a2, 0);
  if ( !result )
  {
    v4 = (winrt *)winrt::impl::slim_source_location::current(v6);
    winrt::throw_last_error(v4, v5);
  }
  return result;
}

```

## disassembly

```asm
0x180015dfc  sub     rsp, 48h
0x180015e00  xor     r8d, r8d; pcbe
0x180015e03  call    TrySubmitThreadpoolCallback_0
0x180015e08  test    eax, eax
0x180015e0a  jz      short loc_180015E11
0x180015e0c  add     rsp, 48h
0x180015e10  retn
0x180015e11  lea     rcx, [rsp+48h+var_28]
0x180015e16  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x180015e1b  mov     rcx, rax; this
0x180015e1e  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
