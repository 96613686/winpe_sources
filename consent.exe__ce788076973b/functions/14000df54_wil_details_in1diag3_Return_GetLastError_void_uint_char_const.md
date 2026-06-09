# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x14000df54`
- end: `0x14000df6d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1400026a0`
- `0x1400029e0`
- `0x140002ea0`
- `0x14000de20`
- `0x140013cec`
- `0x140019fbc`

## callees

- `0x14000df74`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2, a3);
}

```

## disassembly

```asm
0x14000df54  sub     rsp, 38h
0x14000df58  mov     rax, [rsp+38h]
0x14000df5d  mov     [rsp+38h+var_10], rax
0x14000df62  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x14000df67  nop
0x14000df68  add     rsp, 38h
0x14000df6c  retn
```
