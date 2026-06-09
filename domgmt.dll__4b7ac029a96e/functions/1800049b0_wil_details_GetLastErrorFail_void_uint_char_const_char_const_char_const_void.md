# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800049b0`
- end: `0x180004a11`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, __int64, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003090`
- `0x180006ee8`
- `0x180006f70`

## callees

- `0x180003220`
- `0x1800049b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049c7`

## pseudocode

```c
DWORD __fastcall wil::details::GetLastErrorFail(
        wil::details *this,
        void *a2,
        __int64 a3,
        const char *a4,
        const char *a5,
        const char *a6)
{
  int v7; // edi
  DWORD result; // eax
  wil::details *v10; // [rsp+30h] [rbp-18h]

  v7 = (int)a2;
  result = GetLastError();
  if ( !result )
  {
    LODWORD(v10) = -2147024228;
    wil::details::ReportFailure_Hr<2>((__int64)this, v7, a3, 0, 0, (__int64)a6, v10);
    return 668;
  }
  return result;
}

```

## disassembly

```asm
0x1800049b0  mov     [rsp+arg_0], rbx
0x1800049b5  mov     [rsp+arg_8], rsi
0x1800049ba  push    rdi
0x1800049bb  sub     rsp, 40h
0x1800049bf  mov     rbx, r8
0x1800049c2  mov     edi, edx
0x1800049c4  mov     rsi, rcx
0x1800049c7  call    cs:__imp_GetLastError
0x1800049cd  test    eax, eax
0x1800049cf  jnz     short loc_180004A01
0x1800049d1  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x1800049d9  mov     rax, [rsp+48h+arg_28]
0x1800049de  mov     [rsp+48h+var_20], rax; __int64
0x1800049e3  mov     [rsp+48h+var_28], 0; __int64
0x1800049ec  xor     r9d, r9d; int
0x1800049ef  mov     r8, rbx; int
0x1800049f2  mov     edx, edi; int
0x1800049f4  mov     rcx, rsi; int
0x1800049f7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800049fc  mov     eax, 29Ch
0x180004a01  mov     rbx, [rsp+48h+arg_0]
0x180004a06  mov     rsi, [rsp+48h+arg_8]
0x180004a0b  add     rsp, 40h
0x180004a0f  pop     rdi
0x180004a10  retn
```
