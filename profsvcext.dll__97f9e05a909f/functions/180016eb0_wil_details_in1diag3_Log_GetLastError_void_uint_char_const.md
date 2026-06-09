# wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)

- ea: `0x180016eb0`
- end: `0x180016ed0`
- name: `?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `32`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800092d4`

## callees

- `0x180010cbc`

## string_xrefs

- `0x180016ebe`: `clientcore\ds\security\gina\profile\roaming\roaming.cpp`

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
    (int)"clientcore\\ds\\security\\gina\\profile\\roaming\\roaming.cpp",
    (int)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x180016eb0  sub     rsp, 38h
0x180016eb4  mov     rax, [rsp+38h]
0x180016eb9  mov     [rsp+38h+var_10], rax; char *
0x180016ebe  lea     r8, aClientcoreDsSe_1; "clientcore\\ds\\security\\gina\\profile"...
0x180016ec5  call    ??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)
0x180016eca  nop
0x180016ecb  add     rsp, 38h
0x180016ecf  retn
```
