# wil::details::ReportFailure_GetLastError<3>(void *,uint,char const *,char const *,char const *,void *)

- ea: `0x1400022dc`
- end: `0x14000234c`
- name: `??$ReportFailure_GetLastError@$02@details@wil@@YAKPEAXIPEBD110@Z`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400056e8`

## callees

- `0x1400022b0`
- `0x1400022dc`
- `0x140003414`
- `0x1400038b0`

## string_xrefs

- `0x1400022f3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v11; // r8d
  int v12; // r9d
  const char *v13; // [rsp+20h] [rbp-58h]
  int v14; // [rsp+20h] [rbp-58h]
  void *v15; // [rsp+30h] [rbp-48h]
  __int64 v16; // [rsp+50h] [rbp-28h] BYREF
  int v17; // [rsp+58h] [rbp-20h]
  _BYTE v18[24]; // [rsp+60h] [rbp-18h] BYREF

  v6 = (int)a2;
  v7 = (int)a1;
  LastErrorFail = wil::details::GetLastErrorFail(
                    a1,
                    a2,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                    a4,
                    v13,
                    a6,
                    v15);
  if ( LastErrorFail > 0 )
    LastErrorFail = (unsigned __int16)LastErrorFail | 0x80070000;
  v9 = wil::details::ResultStatus::FromResult(v18, (unsigned int)LastErrorFail);
  v10 = *(_QWORD *)v9;
  v17 = *(_DWORD *)(v9 + 8);
  v16 = v10;
  wil::details::ReportFailure_Base<3,0>(v7, v6, v11, v12, v14, (__int64)a6, (__int64)&v16);
}

```

## disassembly

```asm
0x1400022dc  mov     [rsp+arg_0], rbx
0x1400022e1  mov     [rsp+arg_8], rsi
0x1400022e6  push    rdi
0x1400022e7  sub     rsp, 70h
0x1400022eb  mov     rsi, [rsp+78h+arg_28]
0x1400022f3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400022fa  mov     [rsp+78h+var_50], rsi; char *
0x1400022ff  mov     ebx, edx
0x140002301  mov     rdi, rcx
0x140002304  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x140002309  test    eax, eax
0x14000230b  jle     short loc_140002315
0x14000230d  movzx   eax, ax
0x140002310  or      eax, 80070000h
0x140002315  mov     edx, eax
0x140002317  lea     rcx, [rsp+78h+var_18]
0x14000231c  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x140002321  mov     edx, ebx
0x140002323  mov     rcx, rdi
0x140002326  movsd   xmm0, qword ptr [rax]
0x14000232a  mov     eax, [rax+8]
0x14000232d  mov     [rsp+78h+var_20], eax
0x140002331  lea     rax, [rsp+78h+var_28]
0x140002336  mov     [rsp+78h+var_48], rax
0x14000233b  mov     [rsp+78h+var_50], rsi
0x140002340  movsd   [rsp+78h+var_28], xmm0
0x140002346  call    ??$ReportFailure_Base@$02$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<3,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
