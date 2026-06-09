# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140016544`
- end: `0x1400165b5`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `113`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001b51c`

## callees

- `0x140016518`
- `0x140016544`
- `0x1400184c0`
- `0x1400189a8`

## string_xrefs

- `0x14001655b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14001658c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x140016544  mov     [rsp+arg_0], rbx
0x140016549  mov     [rsp+arg_8], rsi
0x14001654e  push    rdi
0x14001654f  sub     rsp, 60h
0x140016553  mov     rsi, [rsp+68h+arg_28]
0x14001655b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140016562  mov     [rsp+68h+var_40], rsi; char *
0x140016567  mov     ebx, edx
0x140016569  mov     rdi, rcx
0x14001656c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140016571  test    eax, eax
0x140016573  jle     short loc_14001657D
0x140016575  movzx   eax, ax
0x140016578  or      eax, 80070000h
0x14001657d  mov     ecx, eax; this
0x14001657f  mov     [rsp+68h+var_18], eax
0x140016583  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140016588  mov     [rsp+68h+var_14], eax
0x14001658c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140016593  lea     rax, [rsp+68h+var_18]
0x140016598  mov     [rsp+68h+var_10], 0
0x1400165a0  mov     [rsp+68h+var_38], rax
0x1400165a5  mov     edx, ebx
0x1400165a7  mov     rcx, rdi
0x1400165aa  mov     [rsp+68h+var_40], rsi
0x1400165af  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
