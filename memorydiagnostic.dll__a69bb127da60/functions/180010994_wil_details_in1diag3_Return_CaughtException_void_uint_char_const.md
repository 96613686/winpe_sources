# wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)

- ea: `0x180010994`
- end: `0x1800109ad`
- name: `?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180020a98`
- `0x180020ad7`
- `0x180020b49`
- `0x180020b97`
- `0x180020bd3`
- `0x180020ce0`
- `0x180020d5c`
- `0x1800210f4`
- `0x180021254`
- `0x180021296`
- `0x18002132c`
- `0x1800213a1`
- `0x180021401`
- `0x180021477`
- `0x1800214b3`
- `0x180021513`
- `0x180022104`

## callees

- `0x180004db0`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_CaughtException(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_CaughtException<1>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180010994  sub     rsp, 48h
0x180010998  mov     rax, [rsp+48h]
0x18001099d  mov     [rsp+48h+var_20], rax
0x1800109a2  call    ??$ReportFailure_CaughtException@$00@details@wil@@YAJPEAXIPEBD110W4SupportedExceptions@1@@Z; wil::details::ReportFailure_CaughtException<1>(void *,uint,char const *,char const *,char const *,void *,wil::SupportedExceptions)
0x1800109a7  nop
0x1800109a8  add     rsp, 48h
0x1800109ac  retn
```
