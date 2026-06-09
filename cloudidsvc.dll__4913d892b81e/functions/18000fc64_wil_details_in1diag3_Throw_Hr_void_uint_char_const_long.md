# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x18000fc64`
- end: `0x18000fc89`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ed90`

## callees

- `0x180008940`

## string_xrefs

- `0x18000fc6d`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>(
    (_DWORD)this,
    118,
    (unsigned int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x18000fc64  sub     rsp, 48h
0x18000fc68  mov     rax, [rsp+48h]
0x18000fc6d  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000fc74  mov     [rsp+48h+var_18], r9d
0x18000fc79  mov     edx, 76h ; 'v'
0x18000fc7e  mov     [rsp+48h+var_20], rax
0x18000fc83  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
