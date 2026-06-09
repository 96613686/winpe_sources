# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140003338`
- end: `0x1400033af`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `119`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000bc2c`

## callees

- `0x1400032e0`
- `0x140003338`
- `0x140006ac8`
- `0x140006f50`

## string_xrefs

- `0x14000334f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000337d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  __int64 v9; // rax
  __int64 v10; // xmm0_8
  int v11; // r9d
  const char *v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+20h] [rbp-58h]
  void *v14; // [rsp+30h] [rbp-48h]
  __int64 v15; // [rsp+50h] [rbp-28h] BYREF
  int v16; // [rsp+58h] [rbp-20h]
  _BYTE v17[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v12,
                    a6,
                    v14);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v9 = wil::details::ResultStatus::FromResult(v17, (unsigned int)LastErrorFail);
  v10 = *(_QWORD *)v9;
  v16 = *(_DWORD *)(v9 + 8);
  v15 = v10;
  wil::details::ReportFailure_Base<3,0>(
    v7,
    v6,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v11,
    v13,
    (__int64)a6,
    (__int64)&v15);
}

```

## disassembly

```asm
0x140003338  mov     [rsp+arg_0], rbx
0x14000333d  mov     [rsp+arg_8], rsi
0x140003342  push    rdi
0x140003343  sub     rsp, 70h
0x140003347  mov     rsi, [rsp+78h+arg_28]
0x14000334f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003356  mov     [rsp+78h+var_50], rsi; char *
0x14000335b  mov     ebx, edx
0x14000335d  mov     rdi, rcx
0x140003360  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140003365  test    eax, eax
0x140003367  jle     short loc_140003371
0x140003369  movzx   eax, ax
0x14000336c  or      eax, 80070000h
0x140003371  mov     edx, eax
0x140003373  lea     rcx, [rsp+78h+var_18]
0x140003378  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x14000337d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140003384  mov     edx, ebx
0x140003386  mov     rcx, rdi
0x140003389  movsd   xmm0, qword ptr [rax]
0x14000338d  mov     eax, [rax+8]
0x140003390  mov     [rsp+78h+var_20], eax
0x140003394  lea     rax, [rsp+78h+var_28]
0x140003399  mov     [rsp+78h+var_48], rax
0x14000339e  mov     [rsp+78h+var_50], rsi
0x1400033a3  movsd   [rsp+78h+var_28], xmm0
0x1400033a9  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
