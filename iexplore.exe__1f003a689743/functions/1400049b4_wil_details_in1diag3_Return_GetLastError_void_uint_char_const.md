# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x1400049b4`
- end: `0x1400049cc`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `24`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003cdc`
- `0x140004f44`

## callees

- `0x1400026d0`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x1400049b4  sub     rsp, 38h
0x1400049b8  mov     rax, [rsp+38h]
0x1400049bd  mov     [rsp+38h+var_10], rax
0x1400049c2  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x1400049c7  add     rsp, 38h
0x1400049cb  retn
```
