# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140004940`
- end: `0x1400049a1`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `DWORD __fastcall(wil::details *this, void *, __int64, const char *, const char *, const char *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002478`
- `0x140002500`

## callees

- `0x140002690`
- `0x140004940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004957`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004957`

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
0x140004940  mov     [rsp+arg_0], rbx
0x140004945  mov     [rsp+arg_8], rsi
0x14000494a  push    rdi
0x14000494b  sub     rsp, 40h
0x14000494f  mov     rbx, r8
0x140004952  mov     edi, edx
0x140004954  mov     rsi, rcx
0x140004957  call    cs:__imp_GetLastError
0x14000495d  test    eax, eax
0x14000495f  jnz     short loc_140004991
0x140004961  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140004969  mov     rax, [rsp+48h+arg_28]
0x14000496e  mov     [rsp+48h+var_20], rax; __int64
0x140004973  mov     [rsp+48h+var_28], 0; __int64
0x14000497c  xor     r9d, r9d; int
0x14000497f  mov     r8, rbx; int
0x140004982  mov     edx, edi; int
0x140004984  mov     rcx, rsi; int
0x140004987  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000498c  mov     eax, 29Ch
0x140004991  mov     rbx, [rsp+48h+arg_0]
0x140004996  mov     rsi, [rsp+48h+arg_8]
0x14000499b  add     rsp, 40h
0x14000499f  pop     rdi
0x1400049a0  retn
```
