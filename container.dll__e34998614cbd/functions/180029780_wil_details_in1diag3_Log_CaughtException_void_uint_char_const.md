# wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)

- ea: `0x180029780`
- end: `0x1800297ae`
- name: `?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `46`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800332ba`

## callees

- `0x18002828c`

## string_xrefs

- `0x180029796`: `onecore\base\gendrv\silos\container\registry_provider.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Log_CaughtException(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  return wil::details::ReportFailure_CaughtException<2>(
           (_DWORD)this,
           65,
           (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
           (_DWORD)a4);
}

```

## disassembly

```asm
0x180029780  sub     rsp, 48h
0x180029784  mov     rax, [rsp+48h]
0x180029789  mov     [rsp+48h+var_18], 0
0x180029791  mov     [rsp+48h+var_20], rax
0x180029796  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x18002979d  mov     edx, 41h ; 'A'
0x1800297a2  call    ??$ReportFailure_CaughtException@$01@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<2>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x1800297a7  nop
0x1800297a8  add     rsp, 48h
0x1800297ac  retn
```
