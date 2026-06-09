# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180004270`
- end: `0x1800042d1`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, int, const char *, const char *, const char *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ec8`
- `0x180002f40`
- `0x1800042d8`
- `0x180006608`

## callees

- `0x18000300c`
- `0x180004270`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004287`

## pseudocode

```c
DWORD __fastcall wil::details::GetLastErrorFail(
        wil::details *this,
        void *a2,
        int a3,
        const char *a4,
        const char *a5,
        const char *a6)
{
  int v7; // edi
  int v8; // esi
  DWORD result; // eax
  wil::details *v10; // [rsp+30h] [rbp-18h]

  v7 = (int)a2;
  v8 = (int)this;
  result = GetLastError();
  if ( !result )
  {
    LODWORD(v10) = -2147024228;
    wil::details::ReportFailure_Hr<2>(v8, v7, a3, 0, 0, (__int64)a6, v10);
    return 668;
  }
  return result;
}

```

## disassembly

```asm
0x180004270  mov     [rsp+arg_0], rbx
0x180004275  mov     [rsp+arg_8], rsi
0x18000427a  push    rdi
0x18000427b  sub     rsp, 40h
0x18000427f  mov     rbx, r8
0x180004282  mov     edi, edx
0x180004284  mov     rsi, rcx
0x180004287  call    cs:__imp_GetLastError
0x18000428d  test    eax, eax
0x18000428f  jnz     short loc_1800042C1
0x180004291  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180004299  mov     rax, [rsp+48h+arg_28]
0x18000429e  mov     [rsp+48h+var_20], rax; __int64
0x1800042a3  mov     [rsp+48h+var_28], 0; __int64
0x1800042ac  xor     r9d, r9d; int
0x1800042af  mov     r8, rbx; int
0x1800042b2  mov     edx, edi; int
0x1800042b4  mov     rcx, rsi; int
0x1800042b7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800042bc  mov     eax, 29Ch
0x1800042c1  mov     rbx, [rsp+48h+arg_0]
0x1800042c6  mov     rsi, [rsp+48h+arg_8]
0x1800042cb  add     rsp, 40h
0x1800042cf  pop     rdi
0x1800042d0  retn
```
