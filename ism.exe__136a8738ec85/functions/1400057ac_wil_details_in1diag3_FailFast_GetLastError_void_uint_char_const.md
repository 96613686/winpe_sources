# wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)

- ea: `0x1400057ac`
- end: `0x1400057c0`
- name: `?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140002b08`
- `0x140002c44`
- `0x140002e78`
- `0x14000321c`
- `0x14000473c`
- `0x1400053bc`
- `0x1400059e8`

## callees

- `0x140001f44`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  wil::details::ReportFailure_GetLastError<3>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x1400057ac  sub     rsp, 38h
0x1400057b0  mov     rax, [rsp+38h]
0x1400057b5  mov     [rsp+38h+var_10], rax
0x1400057ba  call    ??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)
```
