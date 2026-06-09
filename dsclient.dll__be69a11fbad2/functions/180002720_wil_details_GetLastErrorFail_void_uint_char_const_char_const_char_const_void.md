# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180002720`
- end: `0x180002781`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, int, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800024a4`
- `0x1800024d8`
- `0x180003ec0`

## callees

- `0x180002720`
- `0x180003f88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002737`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002737`

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
0x180002720  mov     [rsp+arg_0], rbx
0x180002725  mov     [rsp+arg_8], rsi
0x18000272a  push    rdi
0x18000272b  sub     rsp, 40h
0x18000272f  mov     rbx, r8
0x180002732  mov     edi, edx
0x180002734  mov     rsi, rcx
0x180002737  call    cs:__imp_GetLastError
0x18000273d  test    eax, eax
0x18000273f  jnz     short loc_180002771
0x180002741  mov     rax, [rsp+48h+arg_28]
0x180002746  xor     r9d, r9d; int
0x180002749  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180002751  mov     r8, rbx; int
0x180002754  mov     [rsp+48h+var_20], rax; __int64
0x180002759  mov     edx, edi; int
0x18000275b  mov     rcx, rsi; int
0x18000275e  mov     [rsp+48h+var_28], 0; __int64
0x180002767  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000276c  mov     eax, 29Ch
0x180002771  mov     rbx, [rsp+48h+arg_0]
0x180002776  mov     rsi, [rsp+48h+arg_8]
0x18000277b  add     rsp, 40h
0x18000277f  pop     rdi
0x180002780  retn
```
