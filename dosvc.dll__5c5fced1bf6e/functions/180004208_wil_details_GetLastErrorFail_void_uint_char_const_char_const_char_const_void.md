# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180004208`
- end: `0x180004269`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, __int64, const char *, const char *, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006098`
- `0x180008904`
- `0x180008988`

## callees

- `0x180004208`
- `0x180006108`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000421f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000421f`

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
0x180004208  mov     [rsp+arg_0], rbx
0x18000420d  mov     [rsp+arg_8], rsi
0x180004212  push    rdi
0x180004213  sub     rsp, 40h
0x180004217  mov     rbx, r8
0x18000421a  mov     edi, edx
0x18000421c  mov     rsi, rcx
0x18000421f  call    cs:__imp_GetLastError
0x180004225  test    eax, eax
0x180004227  jnz     short loc_180004259
0x180004229  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180004231  mov     rax, [rsp+48h+arg_28]
0x180004236  mov     [rsp+48h+var_20], rax; __int64
0x18000423b  mov     [rsp+48h+var_28], 0; __int64
0x180004244  xor     r9d, r9d; int
0x180004247  mov     r8, rbx; int
0x18000424a  mov     edx, edi; int
0x18000424c  mov     rcx, rsi; int
0x18000424f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004254  mov     eax, 29Ch
0x180004259  mov     rbx, [rsp+48h+arg_0]
0x18000425e  mov     rsi, [rsp+48h+arg_8]
0x180004263  add     rsp, 40h
0x180004267  pop     rdi
0x180004268  retn
```
