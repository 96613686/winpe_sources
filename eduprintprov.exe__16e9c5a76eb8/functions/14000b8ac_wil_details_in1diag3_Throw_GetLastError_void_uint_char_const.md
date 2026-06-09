# wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)

- ea: `0x14000b8ac`
- end: `0x14000b8c0`
- name: `?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140005f00`
- `0x140006724`
- `0x140007acc`
- `0x14000afac`
- `0x14000fa88`
- `0x140010f8c`

## callees

- `0x1400037c8`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  wil::details::ReportFailure_GetLastError<0>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x14000b8ac  sub     rsp, 38h
0x14000b8b0  mov     rax, [rsp+38h]
0x14000b8b5  mov     [rsp+38h+var_10], rax
0x14000b8ba  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
