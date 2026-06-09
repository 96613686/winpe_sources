# wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)

- ea: `0x18001f46c`
- end: `0x18001f48c`
- name: `?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z`
- size: `32`
- prototype: `unsigned int __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001c500`

## callees

- `0x180013380`

## string_xrefs

- `0x18001f47a`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Log_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v5; // [rsp+20h] [rbp-18h]
  __int64 retaddr; // [rsp+38h] [rbp+0h]

  return wil::details::ReportFailure_GetLastError<2>(
           (int)this,
           (int)a2,
           (int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
           v5,
           retaddr);
}

```

## disassembly

```asm
0x18001f46c  sub     rsp, 38h
0x18001f470  mov     rax, [rsp+38h]
0x18001f475  mov     [rsp+38h+var_10], rax; __int64
0x18001f47a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001f481  call    ??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)
0x18001f486  nop
0x18001f487  add     rsp, 38h
0x18001f48b  retn
```
