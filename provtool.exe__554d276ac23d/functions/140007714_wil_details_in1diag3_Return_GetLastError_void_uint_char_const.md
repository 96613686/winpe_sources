# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x140007714`
- end: `0x14000772d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140005854`
- `0x140007844`
- `0x14000820c`
- `0x140009590`

## callees

- `0x140002588`

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
0x140007714  sub     rsp, 38h
0x140007718  mov     rax, [rsp+38h]
0x14000771d  mov     [rsp+38h+var_10], rax
0x140007722  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x140007727  nop
0x140007728  add     rsp, 38h
0x14000772c  retn
```
