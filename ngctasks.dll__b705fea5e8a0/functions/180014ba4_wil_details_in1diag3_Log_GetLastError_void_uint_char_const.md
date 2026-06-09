# wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)

- ea: `0x180014ba4`
- end: `0x180014bc4`
- name: `?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800110c4`
- `0x18001132c`

## callees

- `0x18000fd5c`

## string_xrefs

- `0x180014bb2`: `onecore\ds\security\ngc\ngctask\dll\ngctasks.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<2>(
    (int)this,
    (int)a2,
    (int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\ngctasks.cpp",
    (int)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x180014ba4  sub     rsp, 38h
0x180014ba8  mov     rax, [rsp+38h]
0x180014bad  mov     [rsp+38h+var_10], rax; char *
0x180014bb2  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180014bb9  call    ??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)
0x180014bbe  nop
0x180014bbf  add     rsp, 38h
0x180014bc3  retn
```
