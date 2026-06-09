# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000e1a0`
- end: `0x18000e211`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `113`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180010978`

## callees

- `0x180006d2c`
- `0x18000bc6c`
- `0x18000e174`
- `0x18000e1a0`

## string_xrefs

- `0x18000e1b7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000e1e8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v12; // [rsp+20h] [rbp-48h]
  void *v13; // [rsp+30h] [rbp-38h]
  _DWORD v14[6]; // [rsp+50h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v11,
                    a6,
                    v13);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v14[0] = LastErrorFail;
  v14[1] = wil::details::HrToNtStatus((wil::details *)(unsigned int)LastErrorFail, v9);
  v14[2] = 0;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v10,
    v12,
    (__int64)a6,
    (__int64)v14);
}

```

## disassembly

```asm
0x18000e1a0  mov     [rsp+arg_0], rbx
0x18000e1a5  mov     [rsp+arg_8], rsi
0x18000e1aa  push    rdi
0x18000e1ab  sub     rsp, 60h
0x18000e1af  mov     rsi, [rsp+68h+arg_28]
0x18000e1b7  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e1be  mov     [rsp+68h+var_40], rsi; char *
0x18000e1c3  mov     ebx, edx
0x18000e1c5  mov     rdi, rcx
0x18000e1c8  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000e1cd  test    eax, eax
0x18000e1cf  jle     short loc_18000E1D9
0x18000e1d1  movzx   eax, ax
0x18000e1d4  or      eax, 80070000h
0x18000e1d9  mov     ecx, eax; this
0x18000e1db  mov     [rsp+68h+var_18], eax
0x18000e1df  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e1e4  mov     [rsp+68h+var_14], eax
0x18000e1e8  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e1ef  lea     rax, [rsp+68h+var_18]
0x18000e1f4  mov     [rsp+68h+var_10], 0
0x18000e1fc  mov     [rsp+68h+var_38], rax
0x18000e201  mov     edx, ebx
0x18000e203  mov     rcx, rdi
0x18000e206  mov     [rsp+68h+var_40], rsi
0x18000e20b  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
