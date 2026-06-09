# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x180008760`
- end: `0x180008779`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, int)`
- caller_count: `27`
- callee_count: `1`
- tags: ``

## callers

- `0x1800082f0`
- `0x1800089f0`
- `0x180009300`
- `0x18000a068`
- `0x18000a4b8`
- `0x18000ca70`
- `0x18000cdbc`
- `0x18000cfcc`
- `0x18000d0b8`
- `0x18000d190`
- `0x18000d348`
- `0x18000d4d8`
- `0x18000dc5c`
- `0x18000e100`
- `0x18000efe0`
- `0x180011600`
- `0x180011848`
- `0x180011a28`
- `0x180011cc0`
- `0x180011e90`
- `0x1800127f4`
- `0x180012a08`
- `0x180012b44`
- `0x180013438`
- `0x180013714`
- `0x180013954`
- `0x180014c74`

## callees

- `0x180007d00`

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
0x180008760  sub     rsp, 48h
0x180008764  mov     rax, [rsp+48h]
0x180008769  mov     [rsp+48h+var_18], r9d
0x18000876e  mov     [rsp+48h+var_20], rax
0x180008773  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
