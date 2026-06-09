# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x140008b88`
- end: `0x140008ba1`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x140003598`
- `0x1400041b0`
- `0x140009de4`
- `0x14000ad18`
- `0x14000b454`
- `0x14000be30`
- `0x14000c520`
- `0x14000c560`
- `0x14000c610`
- `0x14000c7f0`
- `0x14000c920`
- `0x14000ca40`
- `0x14000cd30`
- `0x14000cf10`
- `0x14000d760`

## callees

- `0x140002758`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x140008b88  sub     rsp, 48h
0x140008b8c  mov     rax, [rsp+48h]
0x140008b91  mov     [rsp+48h+var_18], r9d
0x140008b96  mov     [rsp+48h+var_20], rax
0x140008b9b  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
