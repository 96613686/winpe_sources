# wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)

- ea: `0x180008da4`
- end: `0x180008dbd`
- name: `?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180008768`
- `0x18000a5f4`
- `0x18000abb0`
- `0x18000ad90`
- `0x18000b064`
- `0x18000b2c0`
- `0x18000b570`

## callees

- `0x1800086dc`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Win32(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4,
        unsigned int a5)
{
  wil::details::ReportFailure_Win32<0>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180008da4  sub     rsp, 48h
0x180008da8  mov     rax, [rsp+48h]
0x180008dad  mov     [rsp+48h+var_18], r9d
0x180008db2  mov     [rsp+48h+var_20], rax
0x180008db7  call    ??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)
```
