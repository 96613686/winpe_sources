# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180003234`
- end: `0x1800032b4`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800078bc`

## callees

- `0x180003074`
- `0x180003234`
- `0x180004bb8`
- `0x180005100`

## string_xrefs

- `0x18000324b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180003282`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180003234  mov     [rsp+arg_0], rbx
0x180003239  mov     [rsp+arg_8], rsi
0x18000323e  push    rdi
0x18000323f  sub     rsp, 70h
0x180003243  mov     rsi, [rsp+78h+arg_28]
0x18000324b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003252  mov     [rsp+78h+var_50], rsi; char *
0x180003257  mov     ebx, edx
0x180003259  mov     rdi, rcx
0x18000325c  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180003261  test    eax, eax
0x180003263  jle     short loc_18000326D
0x180003265  movzx   eax, ax
0x180003268  or      eax, 80070000h
0x18000326d  mov     edx, eax
0x18000326f  lea     rcx, [rsp+78h+var_18]
0x180003274  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180003279  mov     [rsp+78h+var_40], 0
0x180003282  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003289  mov     edx, ebx
0x18000328b  mov     rcx, rdi
0x18000328e  movsd   xmm0, qword ptr [rax]
0x180003292  mov     eax, [rax+8]
0x180003295  mov     [rsp+78h+var_20], eax
0x180003299  lea     rax, [rsp+78h+var_28]
0x18000329e  mov     [rsp+78h+var_48], rax
0x1800032a3  mov     [rsp+78h+var_50], rsi
0x1800032a8  movsd   [rsp+78h+var_28], xmm0
0x1800032ae  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
