# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1800036b8`
- end: `0x180003732`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `122`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180007ff4`

## callees

- `0x18000335c`
- `0x1800036b8`
- `0x180005960`
- `0x180005f3c`

## string_xrefs

- `0x1800036cf`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180003700`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800036b8  mov     [rsp+arg_0], rbx
0x1800036bd  mov     [rsp+arg_8], rsi
0x1800036c2  push    rdi
0x1800036c3  sub     rsp, 60h
0x1800036c7  mov     rsi, [rsp+68h+arg_28]
0x1800036cf  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800036d6  mov     [rsp+68h+var_40], rsi; char *
0x1800036db  mov     ebx, edx
0x1800036dd  mov     rdi, rcx
0x1800036e0  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1800036e5  test    eax, eax
0x1800036e7  jle     short loc_1800036F1
0x1800036e9  movzx   eax, ax
0x1800036ec  or      eax, 80070000h
0x1800036f1  mov     ecx, eax; this
0x1800036f3  mov     [rsp+68h+var_18], eax
0x1800036f7  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800036fc  mov     [rsp+68h+var_14], eax
0x180003700  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003707  lea     rax, [rsp+68h+var_18]
0x18000370c  mov     [rsp+68h+var_30], 0
0x180003715  mov     [rsp+68h+var_38], rax
0x18000371a  mov     edx, ebx
0x18000371c  mov     rcx, rdi
0x18000371f  mov     [rsp+68h+var_40], rsi
0x180003724  mov     [rsp+68h+var_10], 0
0x18000372c  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
