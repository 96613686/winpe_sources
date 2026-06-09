# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x180004bf8`
- end: `0x180004c75`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800162e8`

## callees

- `0x180004818`
- `0x180004bf8`
- `0x18000ccf0`
- `0x18000d73c`

## string_xrefs

- `0x180004c0f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180004c43`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
    (__int64)&v15,
    0);
}

```

## disassembly

```asm
0x180004bf8  mov     [rsp+arg_0], rbx
0x180004bfd  mov     [rsp+arg_8], rsi
0x180004c02  push    rdi
0x180004c03  sub     rsp, 70h
0x180004c07  mov     rsi, [rsp+78h+arg_28]
0x180004c0f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004c16  mov     [rsp+78h+var_50], rsi; char *
0x180004c1b  mov     ebx, edx
0x180004c1d  mov     rdi, rcx
0x180004c20  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180004c25  test    eax, eax
0x180004c27  jle     short loc_180004C31
0x180004c29  movzx   eax, ax
0x180004c2c  or      eax, 80070000h
0x180004c31  mov     edx, eax
0x180004c33  lea     rcx, [rsp+78h+var_18]
0x180004c38  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180004c3d  and     [rsp+78h+var_40], 0
0x180004c43  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004c4a  mov     edx, ebx
0x180004c4c  mov     rcx, rdi
0x180004c4f  movsd   xmm0, qword ptr [rax]
0x180004c53  mov     eax, [rax+8]
0x180004c56  mov     [rsp+78h+var_20], eax
0x180004c5a  lea     rax, [rsp+78h+var_28]
0x180004c5f  mov     [rsp+78h+var_48], rax
0x180004c64  mov     [rsp+78h+var_50], rsi
0x180004c69  movsd   [rsp+78h+var_28], xmm0
0x180004c6f  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)
```
