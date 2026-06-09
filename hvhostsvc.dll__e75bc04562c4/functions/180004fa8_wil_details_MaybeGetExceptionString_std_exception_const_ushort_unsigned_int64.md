# wil::details::MaybeGetExceptionString(std::exception const &,ushort *,unsigned __int64)

- ea: `0x180004fa8`
- end: `0x180004fe9`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVexception@std@@PEAG_K@Z`
- size: `65`
- prototype: `void __fastcall(wil::details *this, const struct std::exception *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800092d4`
- `0x1800093a6`
- `0x1800094b4`
- `0x1800094ff`

## callees

- `0x180004fa8`
- `0x180005a80`
- `0x18000a010`

## pseudocode

```c
void __fastcall wil::details::MaybeGetExceptionString(
        wil::details *this,
        const struct std::exception *a2,
        unsigned __int16 *a3)
{
  __int64 v5; // rax

  if ( a2 )
  {
    v5 = (*(__int64 (__fastcall **)(wil::details *))(*(_QWORD *)this + 8LL))(this);
    StringCchPrintfW((unsigned __int16 *)a2, (unsigned __int64)a3, L"std::exception: %hs", v5);
  }
}

```

## disassembly

```asm
0x180004fa8  test    rdx, rdx
0x180004fab  jz      short locret_180004FE8
0x180004fad  mov     [rsp+arg_0], rbx
0x180004fb2  push    rdi
0x180004fb3  sub     rsp, 20h
0x180004fb7  mov     rax, [rcx]
0x180004fba  mov     rdi, r8
0x180004fbd  mov     rbx, rdx
0x180004fc0  mov     rax, [rax+8]
0x180004fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc9  mov     r9, rax
0x180004fcc  lea     r8, aStdExceptionHs; "std::exception: %hs"
0x180004fd3  mov     rdx, rdi; unsigned __int64
0x180004fd6  mov     rcx, rbx; unsigned __int16 *
0x180004fd9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004fde  mov     rbx, [rsp+28h+arg_0]
0x180004fe3  add     rsp, 20h
0x180004fe7  pop     rdi
0x180004fe8  retn
```
