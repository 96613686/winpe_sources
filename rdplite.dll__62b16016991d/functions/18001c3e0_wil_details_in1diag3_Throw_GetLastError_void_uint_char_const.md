# wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)

- ea: `0x18001c3e0`
- end: `0x18001c400`
- name: `?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001b3a0`

## callees

- `0x18000eac0`

## string_xrefs

- `0x18001c3e9`: `onecoreuap\termsrv\rdp_bin\win\common\inc\ThreadPoolIo.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<0>(
    (int)this,
    133,
    (int)"onecoreuap\\termsrv\\rdp_bin\\win\\common\\inc\\ThreadPoolIo.h",
    (int)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x18001c3e0  sub     rsp, 38h
0x18001c3e4  mov     rax, [rsp+38h]
0x18001c3e9  lea     r8, aOnecoreuapTerm_19; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18001c3f0  mov     edx, 85h; int
0x18001c3f5  mov     [rsp+38h+var_10], rax; char *
0x18001c3fa  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
