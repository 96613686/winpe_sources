# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x140003980`
- end: `0x140003a00`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `128`
- prototype: `void __fastcall __noreturn(wil::details *, void *, __int64, const char *, int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000cdfc`

## callees

- `0x1400036a0`
- `0x140003980`
- `0x1400070d8`
- `0x1400076a0`

## string_xrefs

- `0x140003997`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1400039ce`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
    (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    v11,
    v13,
    (__int64)a6,
    (__int64)&v15,
    0);
}

```

## disassembly

```asm
0x140003980  mov     [rsp+arg_0], rbx
0x140003985  mov     [rsp+arg_8], rsi
0x14000398a  push    rdi
0x14000398b  sub     rsp, 70h
0x14000398f  mov     rsi, [rsp+78h+arg_28]
0x140003997  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000399e  mov     [rsp+78h+var_50], rsi; char *
0x1400039a3  mov     ebx, edx
0x1400039a5  mov     rdi, rcx
0x1400039a8  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x1400039ad  test    eax, eax
0x1400039af  jle     short loc_1400039B9
0x1400039b1  movzx   eax, ax
0x1400039b4  or      eax, 80070000h
0x1400039b9  mov     edx, eax
0x1400039bb  lea     rcx, [rsp+78h+var_18]
0x1400039c0  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x1400039c5  mov     [rsp+78h+var_40], 0
0x1400039ce  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400039d5  mov     edx, ebx
0x1400039d7  mov     rcx, rdi
0x1400039da  movsd   xmm0, qword ptr [rax]
0x1400039de  mov     eax, [rax+8]
0x1400039e1  mov     [rsp+78h+var_20], eax
0x1400039e5  lea     rax, [rsp+78h+var_28]
0x1400039ea  mov     [rsp+78h+var_48], rax
0x1400039ef  mov     [rsp+78h+var_50], rsi
0x1400039f4  movsd   [rsp+78h+var_28], xmm0
0x1400039fa  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
