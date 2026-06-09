# wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)

- ea: `0x1800096c4`
- end: `0x1800096e4`
- name: `?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, __int64, __int64, const char *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180009070`
- `0x1800092fc`
- `0x1800096ec`

## callees

- `0x1800071d0`

## string_xrefs

- `0x1800096cd`: `servercommon\base\securehostingservice\common\service\plugin\keyprotectionoperations.cpp`

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
    (__int64)"servercommon\\base\\securehostingservice\\common\\service\\plugin\\keyprotectionoperations.cpp",
    (__int64)a4,
    v5,
    retaddr,
    (unsigned int)a4);
}

```

## disassembly

```asm
0x1800096c4  sub     rsp, 48h
0x1800096c8  mov     rax, [rsp+48h]
0x1800096cd  lea     r8, aServercommonBa_0; "servercommon\\base\\securehostingservic"...
0x1800096d4  mov     [rsp+48h+var_18], r9d
0x1800096d9  mov     [rsp+48h+var_20], rax
0x1800096de  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
