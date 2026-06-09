# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x1800079e0`
- end: `0x180007a00`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000751c`
- `0x1800076ac`

## callees

- `0x180006750`

## string_xrefs

- `0x1800079e9`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`

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
    (_DWORD)a2,
    (unsigned int)"admin\\prov\\launch\\csp\\provisioningcommandsnode.cpp",
    (_DWORD)a4);
}

```

## disassembly

```asm
0x1800079e0  sub     rsp, 48h
0x1800079e4  mov     rax, [rsp+48h]
0x1800079e9  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x1800079f0  mov     [rsp+48h+var_18], r9d
0x1800079f5  mov     [rsp+48h+var_20], rax
0x1800079fa  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
