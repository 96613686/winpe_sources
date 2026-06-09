# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180003e0c`
- end: `0x180003e8c`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800077a8`

## callees

- `0x180003dd4`
- `0x180003e0c`
- `0x1800052a8`
- `0x1800057f0`

## string_xrefs

- `0x180003e23`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180003e5a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180003e0c  mov     [rsp+arg_0], rbx
0x180003e11  mov     [rsp+arg_8], rsi
0x180003e16  push    rdi
0x180003e17  sub     rsp, 70h
0x180003e1b  mov     rsi, [rsp+78h+arg_28]
0x180003e23  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003e2a  mov     [rsp+78h+var_50], rsi; char *
0x180003e2f  mov     ebx, edx
0x180003e31  mov     rdi, rcx
0x180003e34  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180003e39  test    eax, eax
0x180003e3b  jle     short loc_180003E45
0x180003e3d  movzx   eax, ax
0x180003e40  or      eax, 80070000h
0x180003e45  mov     edx, eax
0x180003e47  lea     rcx, [rsp+78h+var_18]
0x180003e4c  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180003e51  mov     [rsp+78h+var_40], 0
0x180003e5a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003e61  mov     edx, ebx
0x180003e63  mov     rcx, rdi
0x180003e66  movsd   xmm0, qword ptr [rax]
0x180003e6a  mov     eax, [rax+8]
0x180003e6d  mov     [rsp+78h+var_20], eax
0x180003e71  lea     rax, [rsp+78h+var_28]
0x180003e76  mov     [rsp+78h+var_48], rax
0x180003e7b  mov     [rsp+78h+var_50], rsi
0x180003e80  movsd   [rsp+78h+var_28], xmm0
0x180003e86  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
