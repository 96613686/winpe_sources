# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180003d84`
- end: `0x180003de2`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `94`
- prototype: `DWORD __fastcall(wil::details *this, void *, int, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003adc`
- `0x180003b1c`
- `0x180004fb0`

## callees

- `0x180003d84`
- `0x180005098`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d98`

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
  int v6; // ebx
  int v8; // esi
  int v9; // ebp
  DWORD result; // eax
  wil::details *v11; // [rsp+30h] [rbp-38h]

  v6 = (int)a4;
  v8 = (int)a2;
  v9 = (int)this;
  result = GetLastError();
  if ( !result )
  {
    LODWORD(v11) = -2147024228;
    wil::details::ReportFailure_Hr<2>(v9, v8, a3, v6, (__int64)a5, (__int64)a6, v11);
    return 668;
  }
  return result;
}

```

## disassembly

```asm
0x180003d84  push    rbx
0x180003d86  push    rbp
0x180003d87  push    rsi
0x180003d88  push    rdi
0x180003d89  sub     rsp, 48h
0x180003d8d  mov     rbx, r9
0x180003d90  mov     rdi, r8
0x180003d93  mov     esi, edx
0x180003d95  mov     rbp, rcx
0x180003d98  call    cs:__imp_GetLastError
0x180003d9e  test    eax, eax
0x180003da0  jnz     short loc_180003DD9
0x180003da2  mov     dword ptr [rsp+68h+var_38], 8007029Ch; wil::details *
0x180003daa  mov     rax, [rsp+68h+arg_28]
0x180003db2  mov     [rsp+68h+var_40], rax; __int64
0x180003db7  mov     rax, [rsp+68h+arg_20]
0x180003dbf  mov     [rsp+68h+var_48], rax; __int64
0x180003dc4  mov     r9, rbx; int
0x180003dc7  mov     r8, rdi; int
0x180003dca  mov     edx, esi; int
0x180003dcc  mov     rcx, rbp; int
0x180003dcf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003dd4  mov     eax, 29Ch
0x180003dd9  add     rsp, 48h
0x180003ddd  pop     rdi
0x180003dde  pop     rsi
0x180003ddf  pop     rbp
0x180003de0  pop     rbx
0x180003de1  retn
```
