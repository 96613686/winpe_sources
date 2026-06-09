# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180004f4c`
- end: `0x180004fb4`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `104`
- prototype: `unsigned int __fastcall(wil::details *__hidden this, void *, unsigned int, const char *, const char *, const char *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004cd0`
- `0x180004d04`
- `0x180005d48`

## callees

- `0x180004f4c`
- `0x180005e08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f63`

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
0x180004f4c  mov     [rsp+arg_0], rbx
0x180004f51  mov     [rsp+arg_8], rsi
0x180004f56  push    rdi
0x180004f57  sub     rsp, 40h
0x180004f5b  mov     rbx, r8
0x180004f5e  mov     edi, edx
0x180004f60  mov     rsi, rcx
0x180004f63  call    cs:__imp_GetLastError
0x180004f6a  nop     dword ptr [rax+rax+00h]
0x180004f6f  test    eax, eax
0x180004f71  jnz     short loc_180004FA3
0x180004f73  mov     rax, [rsp+48h+arg_28]
0x180004f78  xor     r9d, r9d; int
0x180004f7b  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x180004f83  mov     r8, rbx; int
0x180004f86  mov     [rsp+48h+var_20], rax; __int64
0x180004f8b  mov     edx, edi; int
0x180004f8d  mov     rcx, rsi; int
0x180004f90  mov     [rsp+48h+var_28], 0; __int64
0x180004f99  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004f9e  mov     eax, 29Ch
0x180004fa3  mov     rbx, [rsp+48h+arg_0]
0x180004fa8  mov     rsi, [rsp+48h+arg_8]
0x180004fad  add     rsp, 40h
0x180004fb1  pop     rdi
0x180004fb2  retn
```
