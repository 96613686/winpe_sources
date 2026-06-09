# wil::details::ReportFailure_Hr<0>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)

- ea: `0x180011b10`
- end: `0x180011b66`
- name: `??$ReportFailure_Hr@$0A@@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z`
- size: `86`
- prototype: `void __fastcall __noreturn(__int64, __int64, __int64, __int64, int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800123bc`

## callees

- `0x180006138`
- `0x180011ae4`

## string_xrefs

- `0x180011b2b`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_Hr<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7)
{
  int v7; // r9d
  int v8; // r10d
  _BYTE v9[24]; // [rsp+60h] [rbp-18h] BYREF

  wil::details::ResultStatus::FromResult(v9, a7);
  wil::details::ReportFailure_Base<0,0>(
    v8,
    v7,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
    v7);
}

```

## disassembly

```asm
0x180011b10  sub     rsp, 78h
0x180011b14  mov     r10, rcx
0x180011b17  mov     r9d, edx
0x180011b1a  mov     edx, [rsp+78h+arg_30]
0x180011b21  lea     rcx, [rsp+78h+var_18]
0x180011b26  call    ?FromResult@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromResult(long)
0x180011b2b  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\com"...
0x180011b32  mov     edx, r9d
0x180011b35  mov     rcx, r10
0x180011b38  movsd   xmm0, qword ptr [rax]
0x180011b3c  mov     eax, [rax+8]
0x180011b3f  mov     [rsp+78h+var_20], eax
0x180011b43  lea     rax, [rsp+78h+var_28]
0x180011b48  mov     [rsp+78h+var_48], rax
0x180011b4d  mov     rax, [rsp+78h+arg_28]
0x180011b55  mov     [rsp+78h+var_50], rax
0x180011b5a  movsd   [rsp+78h+var_28], xmm0
0x180011b60  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
