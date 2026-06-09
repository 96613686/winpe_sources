# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180002c24`
- end: `0x180002c9e`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800071f0`

## callees

- `0x180002a60`
- `0x180002c24`
- `0x180004870`
- `0x180004d94`

## string_xrefs

- `0x180002c3b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180002c6c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_GetLastError<3>(
        wil::details *a1,
        void *a2,
        __int64 a3,
        const char *a4,
        int a5,
        char *a6)
{
  int v6; // ebx
  int v7; // edi
  signed int LastErrorFail; // eax
  int v9; // edx
  int v10; // r9d
  const char *v11; // [rsp+20h] [rbp-48h]
  void *v12; // [rsp+30h] [rbp-38h]

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v11,
                    a6,
                    v12);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v9);
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v10);
}

```

## disassembly

```asm
0x180002c24  mov     [rsp+arg_0], rbx
0x180002c29  mov     [rsp+arg_8], rsi
0x180002c2e  push    rdi
0x180002c2f  sub     rsp, 60h
0x180002c33  mov     rsi, [rsp+68h+arg_28]
0x180002c3b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002c42  mov     [rsp+68h+var_40], rsi; char *
0x180002c47  mov     ebx, edx
0x180002c49  mov     rdi, rcx
0x180002c4c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180002c51  test    eax, eax
0x180002c53  jle     short loc_180002C5D
0x180002c55  movzx   eax, ax
0x180002c58  or      eax, 80070000h
0x180002c5d  mov     ecx, eax; this
0x180002c5f  mov     [rsp+68h+var_18], eax
0x180002c63  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002c68  mov     [rsp+68h+var_14], eax
0x180002c6c  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002c73  lea     rax, [rsp+68h+var_18]
0x180002c78  mov     [rsp+68h+var_30], 0
0x180002c81  mov     [rsp+68h+var_38], rax
0x180002c86  mov     edx, ebx
0x180002c88  mov     rcx, rdi
0x180002c8b  mov     [rsp+68h+var_40], rsi
0x180002c90  mov     [rsp+68h+var_10], 0
0x180002c98  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
