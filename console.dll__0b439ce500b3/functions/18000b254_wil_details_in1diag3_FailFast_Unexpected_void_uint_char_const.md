# wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)

- ea: `0x18000b254`
- end: `0x18000b268`
- name: `?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `20`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180009578`
- `0x18000a01c`
- `0x18000ab50`
- `0x18000ac68`
- `0x180010110`
- `0x1800114d4`
- `0x180011f44`

## callees

- `0x1800033a0`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_FailFast_Unexpected(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  wil::details::ReportFailure_Hr<3>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x18000b254  sub     rsp, 48h
0x18000b258  mov     rax, [rsp+48h]
0x18000b25d  mov     [rsp+48h+var_20], rax
0x18000b262  call    ??$ReportFailure_Hr@$02@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<3>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
