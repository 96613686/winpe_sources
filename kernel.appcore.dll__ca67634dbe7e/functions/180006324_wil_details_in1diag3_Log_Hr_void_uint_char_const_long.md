# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x180006324`
- end: `0x18000634d`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `41`
- prototype: `void __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x1800011a0`
- `0x180001380`
- `0x180001790`
- `0x180001920`
- `0x180001af0`
- `0x180001d20`
- `0x180001ef0`
- `0x1800020d0`
- `0x180002850`
- `0x180003350`
- `0x180004b20`
- `0x180004f00`
- `0x180005e44`
- `0x180005f54`
- `0x1800060c0`
- `0x1800061c4`
- `0x180006274`
- `0x180006354`
- `0x18000641c`

## callees

- `0x1800091f4`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>((int)this, (int)a2, a3, 0, 0, retaddr, v4);
}

```

## disassembly

```asm
0x180006324  sub     rsp, 48h
0x180006328  mov     rax, [rsp+48h]
0x18000632d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180006332  xor     r9d, r9d; int
0x180006335  mov     [rsp+48h+var_20], rax; __int64
0x18000633a  mov     [rsp+48h+var_28], 0; __int64
0x180006343  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006348  add     rsp, 48h
0x18000634c  retn
```
