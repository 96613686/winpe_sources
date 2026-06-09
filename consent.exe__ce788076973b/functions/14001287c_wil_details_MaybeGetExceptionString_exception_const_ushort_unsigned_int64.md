# wil::details::MaybeGetExceptionString(exception const &,ushort *,unsigned __int64)

- ea: `0x14001287c`
- end: `0x1400128bd`
- name: `?MaybeGetExceptionString@details@wil@@YAXAEBVexception@@PEAG_K@Z`
- size: `65`
- prototype: `void __fastcall(wil::details *this, const struct exception *, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14001e516`
- `0x14001e5e8`
- `0x14001e6f6`
- `0x14001e741`

## callees

- `0x14000e558`
- `0x14001287c`
- `0x14001f010`

## pseudocode

```c
void __fastcall wil::details::MaybeGetExceptionString(
        wil::details *this,
        const struct exception *a2,
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
0x14001287c  test    rdx, rdx
0x14001287f  jz      short locret_1400128BC
0x140012881  mov     [rsp+arg_0], rbx
0x140012886  push    rdi
0x140012887  sub     rsp, 20h
0x14001288b  mov     rax, [rcx]
0x14001288e  mov     rdi, r8
0x140012891  mov     rbx, rdx
0x140012894  mov     rax, [rax+8]
0x140012898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001289d  mov     r9, rax
0x1400128a0  lea     r8, aStdExceptionHs; "std::exception: %hs"
0x1400128a7  mov     rdx, rdi; unsigned __int64
0x1400128aa  mov     rcx, rbx; unsigned __int16 *
0x1400128ad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400128b2  mov     rbx, [rsp+28h+arg_0]
0x1400128b7  add     rsp, 20h
0x1400128bb  pop     rdi
0x1400128bc  retn
```
