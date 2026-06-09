# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x14000b8f4`
- end: `0x14000b90d`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140005f00`
- `0x140006724`
- `0x140007acc`
- `0x14000afac`
- `0x14000b968`
- `0x14000d2a4`
- `0x14000fa88`
- `0x140010384`
- `0x140010f8c`

## callees

- `0x140003a94`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::_Throw_Hr(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4,
        int a5)
{
  wil::details::ReportFailure_Hr<0>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x14000b8f4  sub     rsp, 48h
0x14000b8f8  mov     rax, [rsp+48h]
0x14000b8fd  mov     [rsp+48h+var_18], r9d
0x14000b902  mov     [rsp+48h+var_20], rax
0x14000b907  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
