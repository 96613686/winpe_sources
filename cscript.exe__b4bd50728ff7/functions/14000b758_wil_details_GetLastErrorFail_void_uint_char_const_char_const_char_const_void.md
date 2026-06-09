# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x14000b758`
- end: `0x14000b7b9`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `unsigned int __usercall@<eax>(wil::details *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, const char *@<r9>, const char *, const char *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a52c`
- `0x14000a5ac`
- `0x14000b7c0`

## callees

- `0x14000a674`
- `0x14000b758`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000b76f`
- `KERNEL32!GetLastError` at `0x14000b76f`

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
0x14000b758  mov     [rsp+arg_0], rbx
0x14000b75d  mov     [rsp+arg_8], rsi
0x14000b762  push    rdi
0x14000b763  sub     rsp, 40h
0x14000b767  mov     rbx, r8
0x14000b76a  mov     edi, edx
0x14000b76c  mov     rsi, rcx
0x14000b76f  call    cs:__imp_GetLastError
0x14000b775  test    eax, eax
0x14000b777  jnz     short loc_14000B7A9
0x14000b779  mov     rax, [rsp+48h+arg_28]
0x14000b77e  xor     r9d, r9d; int
0x14000b781  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x14000b789  mov     r8, rbx; int
0x14000b78c  mov     [rsp+48h+var_20], rax; __int64
0x14000b791  mov     edx, edi; int
0x14000b793  mov     rcx, rsi; int
0x14000b796  mov     [rsp+48h+var_28], 0; __int64
0x14000b79f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000b7a4  mov     eax, 29Ch
0x14000b7a9  mov     rbx, [rsp+48h+arg_0]
0x14000b7ae  mov     rsi, [rsp+48h+arg_8]
0x14000b7b3  add     rsp, 40h
0x14000b7b7  pop     rdi
0x14000b7b8  retn
```
