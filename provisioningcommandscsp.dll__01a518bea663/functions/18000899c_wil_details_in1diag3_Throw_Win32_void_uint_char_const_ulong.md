# wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)

- ea: `0x18000899c`
- end: `0x1800089b5`
- name: `?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *this, void *, int, const char *, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800083a4`
- `0x18000a0dc`
- `0x18000a640`
- `0x18000a7f8`
- `0x18000aa94`
- `0x18000acc4`
- `0x18000af48`

## callees

- `0x18000831c`

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
0x18000899c  sub     rsp, 48h
0x1800089a0  mov     rax, [rsp+48h]
0x1800089a5  mov     [rsp+48h+var_18], r9d
0x1800089aa  mov     [rsp+48h+var_20], rax
0x1800089af  call    ??$ReportFailure_Win32@$0A@@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<0>(void *,uint,char const *,char const *,char const *,void *,ulong)
```
