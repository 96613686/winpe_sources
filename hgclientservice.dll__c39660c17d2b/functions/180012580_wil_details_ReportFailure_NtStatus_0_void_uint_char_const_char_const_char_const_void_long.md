# wil::details::ReportFailure_NtStatus<0>(void *,uint,char const *,char const *,char const *,void *,long)

- ea: `0x180012580`
- end: `0x1800125eb`
- name: `??$ReportFailure_NtStatus@$0A@@details@wil@@YAJPEAXIPEBD110J@Z`
- size: `107`
- prototype: `void __fastcall __noreturn(int, int, __int64, __int64, int, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013d08`

## callees

- `0x180007c30`
- `0x1800131e8`

## string_xrefs

- `0x1800125a8`: `servercommon\base\securehostingservice\common\service\lib\vsmcaagent.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NtStatus<0>(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int a7)
{
  __int64 v9; // rax
  __int64 v10; // xmm0_8
  int v11; // r9d
  int v12; // [rsp+20h] [rbp-58h]
  __int64 v13; // [rsp+50h] [rbp-28h] BYREF
  int v14; // [rsp+58h] [rbp-20h]
  _BYTE v15[24]; // [rsp+60h] [rbp-18h] BYREF

  v9 = wil::details::ResultStatus::FromStatus(v15, a7);
  v10 = *(_QWORD *)v9;
  v14 = *(_DWORD *)(v9 + 8);
  v13 = v10;
  wil::details::ReportFailure_Base<0,0>(
    a1,
    a2,
    (int)"servercommon\\base\\securehostingservice\\common\\service\\lib\\vsmcaagent.cpp",
    v11,
    v12,
    a6,
    (__int64)&v13,
    0,
    0);
}

```

## disassembly

```asm
0x180012580  mov     [rsp+arg_0], rbx
0x180012585  push    rdi
0x180012586  sub     rsp, 70h
0x18001258a  mov     ebx, edx
0x18001258c  mov     rdi, rcx
0x18001258f  mov     edx, [rsp+78h+arg_30]
0x180012596  lea     rcx, [rsp+78h+var_18]
0x18001259b  call    ?FromStatus@ResultStatus@details@wil@@SA?AU123@J@Z; wil::details::ResultStatus::FromStatus(long)
0x1800125a0  mov     [rsp+78h+var_38], 0
0x1800125a8  lea     r8, aServercommonBa_3; "servercommon\\base\\securehostingservic"...
0x1800125af  mov     [rsp+78h+var_40], 0
0x1800125b8  mov     edx, ebx
0x1800125ba  mov     rcx, rdi
0x1800125bd  movsd   xmm0, qword ptr [rax]
0x1800125c1  mov     eax, [rax+8]
0x1800125c4  mov     [rsp+78h+var_20], eax
0x1800125c8  lea     rax, [rsp+78h+var_28]
0x1800125cd  mov     [rsp+78h+var_48], rax
0x1800125d2  mov     rax, [rsp+78h+arg_28]
0x1800125da  mov     [rsp+78h+var_50], rax
0x1800125df  movsd   [rsp+78h+var_28], xmm0
0x1800125e5  call    ??$ReportFailure_Base@$0A@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z; wil::details::ReportFailure_Base<0,0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)
```
