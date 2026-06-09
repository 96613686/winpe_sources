# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x18001e230`
- end: `0x18001e255`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005ee0`

## callees

- `0x18000e81c`

## string_xrefs

- `0x18001e239`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    760,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\cregistry.cxx",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18001e230  sub     rsp, 48h
0x18001e234  mov     rax, [rsp+48h]
0x18001e239  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x18001e240  mov     [rsp+48h+var_18], r9d
0x18001e245  mov     edx, 2F8h
0x18001e24a  mov     [rsp+48h+var_20], rax
0x18001e24f  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
