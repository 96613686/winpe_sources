# wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140003910`
- end: `0x140003971`
- name: `?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z`
- size: `97`
- prototype: `unsigned int __usercall@<eax>(wil::details *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, const char *@<r9>, const char *, const char *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002658`
- `0x1400026d0`
- `0x140003978`

## callees

- `0x140002798`
- `0x140003910`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140003927`
- `KERNEL32!GetLastError` at `0x140003927`

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
0x140003910  mov     [rsp+arg_0], rbx
0x140003915  mov     [rsp+arg_8], rsi
0x14000391a  push    rdi
0x14000391b  sub     rsp, 40h
0x14000391f  mov     rbx, r8
0x140003922  mov     edi, edx
0x140003924  mov     rsi, rcx
0x140003927  call    cs:__imp_GetLastError
0x14000392d  test    eax, eax
0x14000392f  jnz     short loc_140003961
0x140003931  mov     rax, [rsp+48h+arg_28]
0x140003936  xor     r9d, r9d; int
0x140003939  mov     dword ptr [rsp+48h+var_18], 8007029Ch; wil::details *
0x140003941  mov     r8, rbx; int
0x140003944  mov     [rsp+48h+var_20], rax; __int64
0x140003949  mov     edx, edi; int
0x14000394b  mov     rcx, rsi; int
0x14000394e  mov     [rsp+48h+var_28], 0; __int64
0x140003957  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000395c  mov     eax, 29Ch
0x140003961  mov     rbx, [rsp+48h+arg_0]
0x140003966  mov     rsi, [rsp+48h+arg_8]
0x14000396b  add     rsp, 40h
0x14000396f  pop     rdi
0x140003970  retn
```
