# wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)

- ea: `0x18000fc3c`
- end: `0x18000fc5c`
- name: `?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ed90`

## callees

- `0x1800088d4`

## string_xrefs

- `0x18000fc45`: `onecoreuap\ds\ext\common\ntservice\lib\utilities.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<0>(
    (int)this,
    102,
    (int)"onecoreuap\\ds\\ext\\common\\ntservice\\lib\\utilities.cpp",
    (int)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x18000fc3c  sub     rsp, 38h
0x18000fc40  mov     rax, [rsp+38h]
0x18000fc45  lea     r8, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\common\\ntservice"...
0x18000fc4c  mov     edx, 66h ; 'f'; int
0x18000fc51  mov     [rsp+38h+var_10], rax; char *
0x18000fc56  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
