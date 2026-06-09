# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180003ec0`
- end: `0x180003f31`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `113`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008aa8`

## callees

- `0x18000255c`
- `0x180002720`
- `0x180003e94`
- `0x180003ec0`

## string_xrefs

- `0x180003ed7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180003f08`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180003ec0  mov     [rsp+arg_0], rbx
0x180003ec5  mov     [rsp+arg_8], rsi
0x180003eca  push    rdi
0x180003ecb  sub     rsp, 60h
0x180003ecf  mov     rsi, [rsp+68h+arg_28]
0x180003ed7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003ede  mov     [rsp+68h+var_40], rsi; char *
0x180003ee3  mov     ebx, edx
0x180003ee5  mov     rdi, rcx
0x180003ee8  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180003eed  test    eax, eax
0x180003eef  jle     short loc_180003EF9
0x180003ef1  movzx   eax, ax
0x180003ef4  or      eax, 80070000h
0x180003ef9  mov     ecx, eax; this
0x180003efb  mov     [rsp+68h+var_18], eax
0x180003eff  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003f04  mov     [rsp+68h+var_14], eax
0x180003f08  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003f0f  lea     rax, [rsp+68h+var_18]
0x180003f14  mov     [rsp+68h+var_10], 0
0x180003f1c  mov     [rsp+68h+var_38], rax
0x180003f21  mov     edx, ebx
0x180003f23  mov     rcx, rdi
0x180003f26  mov     [rsp+68h+var_40], rsi
0x180003f2b  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
