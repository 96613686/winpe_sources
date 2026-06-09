# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x18000d284`
- end: `0x18000d2f5`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `113`
- prototype: `void __fastcall __noreturn(int, int, int, int, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180011e50`

## callees

- `0x18000b348`
- `0x18000b50c`
- `0x18000d258`
- `0x18000d284`

## string_xrefs

- `0x18000d29b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000d2cc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000d284  mov     [rsp+arg_0], rbx
0x18000d289  mov     [rsp+arg_8], rsi
0x18000d28e  push    rdi
0x18000d28f  sub     rsp, 60h
0x18000d293  mov     rsi, [rsp+68h+arg_28]
0x18000d29b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d2a2  mov     [rsp+68h+var_40], rsi; char *
0x18000d2a7  mov     ebx, edx
0x18000d2a9  mov     rdi, rcx
0x18000d2ac  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000d2b1  test    eax, eax
0x18000d2b3  jle     short loc_18000D2BD
0x18000d2b5  movzx   eax, ax
0x18000d2b8  or      eax, 80070000h
0x18000d2bd  mov     ecx, eax; this
0x18000d2bf  mov     [rsp+68h+var_18], eax
0x18000d2c3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d2c8  mov     [rsp+68h+var_14], eax
0x18000d2cc  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000d2d3  lea     rax, [rsp+68h+var_18]
0x18000d2d8  mov     [rsp+68h+var_10], 0
0x18000d2e0  mov     [rsp+68h+var_38], rax
0x18000d2e5  mov     edx, ebx
0x18000d2e7  mov     rcx, rdi
0x18000d2ea  mov     [rsp+68h+var_40], rsi
0x18000d2ef  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
