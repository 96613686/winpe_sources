# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800026e0`
- end: `0x180002760`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000603c`

## callees

- `0x180002554`
- `0x1800026e0`
- `0x180003d08`
- `0x180004250`

## string_xrefs

- `0x1800026f7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000272e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // r9d
  const char *v10; // [rsp+20h] [rbp-58h]
  void *v11; // [rsp+30h] [rbp-48h]
  _BYTE v12[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v10,
                    a6,
                    v11);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  wil::details::ResultStatus::FromResult(v12, (unsigned int)LastErrorFail);
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v9);
}

```

## disassembly

```asm
0x1800026e0  mov     [rsp+arg_0], rbx
0x1800026e5  mov     [rsp+arg_8], rsi
0x1800026ea  push    rdi
0x1800026eb  sub     rsp, 70h
0x1800026ef  mov     rsi, [rsp+78h+arg_28]
0x1800026f7  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800026fe  mov     [rsp+78h+var_50], rsi; char *
0x180002703  mov     ebx, edx
0x180002705  mov     rdi, rcx
0x180002708  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x18000270d  test    eax, eax
0x18000270f  jle     short loc_180002719
0x180002711  movzx   eax, ax
0x180002714  or      eax, 80070000h
0x180002719  mov     edx, eax
0x18000271b  lea     rcx, [rsp+78h+var_18]
0x180002720  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180002725  mov     [rsp+78h+var_40], 0
0x18000272e  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180002735  mov     edx, ebx
0x180002737  mov     rcx, rdi
0x18000273a  movsd   xmm0, qword ptr [rax]
0x18000273e  mov     eax, [rax+8]
0x180002741  mov     [rsp+78h+var_20], eax
0x180002745  lea     rax, [rsp+78h+var_28]
0x18000274a  mov     [rsp+78h+var_48], rax
0x18000274f  mov     [rsp+78h+var_50], rsi
0x180002754  movsd   [rsp+78h+var_28], xmm0
0x18000275a  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
