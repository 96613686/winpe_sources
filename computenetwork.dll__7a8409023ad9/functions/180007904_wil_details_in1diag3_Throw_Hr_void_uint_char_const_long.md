# wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)

- ea: `0x180007904`
- end: `0x18000791d`
- name: `?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `25`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `52`
- callee_count: `1`
- tags: ``

## callers

- `0x1800055f0`
- `0x180005650`
- `0x1800057b0`
- `0x180005870`
- `0x180005930`
- `0x1800059f0`
- `0x180005ab0`
- `0x180005b70`
- `0x180005c70`
- `0x180005d30`
- `0x180005e30`
- `0x180005ed0`
- `0x180007b20`
- `0x180007b80`
- `0x180007be0`
- `0x180007c40`
- `0x180007ca0`
- `0x180007d00`
- `0x180007e90`
- `0x180007f60`
- `0x180008030`
- `0x180008100`
- `0x1800084a0`
- `0x180008670`
- `0x180008730`
- `0x1800087f0`
- `0x1800088d0`
- `0x180008990`
- `0x180008a50`
- `0x180008b10`
- `0x180008bd0`
- `0x180008c90`
- `0x180008d50`
- `0x180008e10`
- `0x180008ed0`
- `0x180008f90`
- `0x180009090`
- `0x180009190`
- `0x180009290`
- `0x180009390`
- `0x180009490`
- `0x180009590`
- `0x180009690`
- `0x180009730`
- `0x180009920`
- `0x1800099e0`
- `0x180009bc0`
- `0x180009c20`
- `0x18000a608`
- `0x18000aaa0`

## callees

- `0x18000348c`

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
0x180007904  sub     rsp, 48h
0x180007908  mov     rax, [rsp+48h]
0x18000790d  mov     [rsp+48h+var_18], r9d
0x180007912  mov     [rsp+48h+var_20], rax
0x180007917  call    ??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
```
