# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x180007670`
- end: `0x180007690`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, __int64, __int64, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800071d8`
- `0x180007360`

## callees

- `0x180006450`

## string_xrefs

- `0x180007679`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_Hr(
        wil::details::in1diag3 *this,
        __int64 a2,
        __int64 a3,
        const char *a4,
        int a5)
{
  int v5; // [rsp+20h] [rbp-28h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  wil::details::ReportFailure_Hr<0>(
    (__int64)this,
    a2,
    (__int64)"admin\\prov\\launch\\csp\\provisioningcommandsnode.cpp",
    (__int64)a4,
    v5,
    retaddr,
    (unsigned int)a4);
}

```

## disassembly

```asm
0x180007670  sub     rsp, 48h
0x180007674  mov     rax, [rsp+48h]
0x180007679  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x180007680  mov     [rsp+48h+var_18], r9d
0x180007685  mov     [rsp+48h+var_20], rax
0x18000768a  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
