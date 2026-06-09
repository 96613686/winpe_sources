# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x140004434`
- end: `0x14000444c`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `24`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400039f0`
- `0x140004840`

## callees

- `0x14000218c`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v5; // [rsp+20h] [rbp-18h]
  __int64 retaddr; // [rsp+38h] [rbp+0h]

  return wil::details::ReportFailure_GetLastErrorHr<1>((__int64)this, (unsigned int)a2, a3, (__int64)a4, v5, retaddr);
}

```

## disassembly

```asm
0x140004434  sub     rsp, 38h
0x140004438  mov     rax, [rsp+38h]
0x14000443d  mov     [rsp+38h+var_10], rax
0x140004442  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x140004447  add     rsp, 38h
0x14000444b  retn
```
