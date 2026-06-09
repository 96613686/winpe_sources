# wil::details::ReportFailure_NtStatus<0>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x140002ce8`
- end: `0x140002d3f`
- name: `??$ReportFailure_NtStatus@$0A@@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `87`
- prototype: `void __fastcall __noreturn(int, __int64, __int64, __int64, int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140006d34`

## callees

- `0x1400022f8`
- `0x1400043f4`

## string_xrefs

- `0x140002d02`: `onecoreuap\net\dusm\task\dusmtask.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NtStatus<0>(
        int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7)
{
  __int64 v8; // rax
  __int64 v9; // xmm0_8
  int v10; // r9d
  int v11; // [rsp+20h] [rbp-58h]
  __int64 v12; // [rsp+50h] [rbp-28h] BYREF
  int v13; // [rsp+58h] [rbp-20h]
  _BYTE v14[24]; // [rsp+60h] [rbp-18h] BYREF

  v8 = wil::details::ResultStatus::FromStatus(v14, a7);
  v9 = *(_QWORD *)v8;
  v13 = *(_DWORD *)(v8 + 8);
  v12 = v9;
  wil::details::ReportFailure_Base<0,0>(
    a1,
    197,
    (int)"onecoreuap\\net\\dusm\\task\\dusmtask.cpp",
    v10,
    v11,
    a6,
    (__int64)&v12);
}

```

## disassembly

```asm
0x140002ce8  push    rbx
0x140002cea  sub     rsp, 70h
0x140002cee  mov     edx, [rsp+78h+arg_30]
0x140002cf5  mov     rbx, rcx
0x140002cf8  lea     rcx, [rsp+78h+var_18]
0x140002cfd  call    ?FromStatus@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromStatus(long)
0x140002d02  lea     r8, aOnecoreuapNetD; "onecoreuap\\net\\dusm\\task\\dusmtask.c"...
0x140002d09  mov     edx, 0C5h
0x140002d0e  mov     rcx, rbx
0x140002d11  movsd   xmm0, qword ptr [rax]
0x140002d15  mov     eax, [rax+8]
0x140002d18  mov     [rsp+78h+var_20], eax
0x140002d1c  lea     rax, [rsp+78h+var_28]
0x140002d21  mov     [rsp+78h+var_48], rax
0x140002d26  mov     rax, [rsp+78h+arg_28]
0x140002d2e  mov     [rsp+78h+var_50], rax
0x140002d33  movsd   [rsp+78h+var_28], xmm0
0x140002d39  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
