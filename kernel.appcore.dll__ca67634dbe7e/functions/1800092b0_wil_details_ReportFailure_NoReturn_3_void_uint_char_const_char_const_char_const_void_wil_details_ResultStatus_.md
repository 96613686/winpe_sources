# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800092b0`
- end: `0x180009359`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800091c8`

## callees

- `0x180005a4c`
- `0x180009914`
- `0x180009d9e`
- `0x180009e60`

## string_xrefs

- `0x1800092f2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int *a7)
{
  const struct wil::FailureInfo *v8; // rdx
  __int64 v9; // [rsp+48h] [rbp-14E0h]
  __int64 v10; // [rsp+58h] [rbp-14D0h]
  __int64 v11; // [rsp+68h] [rbp-14C0h]
  _BYTE v12[160]; // [rsp+80h] [rbp-14A8h] BYREF
  _BYTE v13[1024]; // [rsp+120h] [rbp-1408h] BYREF
  _BYTE v14[4104]; // [rsp+520h] [rbp-1008h] BYREF

  memset_0(v12, 0, 0x98u);
  wil::details::LogFailure(
    a1,
    3977,
    (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    0,
    0,
    a6,
    3,
    a7,
    0,
    v9,
    (wil *)v14,
    v10,
    v13,
    v11,
    0,
    (unsigned __int64)v12);
  wil::details::WilFailFast((wil::details *)v12, v8);
}

```

## disassembly

```asm
0x1800092b0  mov     [rsp+arg_8], rbx
0x1800092b5  push    rdi
0x1800092b6  mov     eax, 1520h
0x1800092bb  call    _alloca_probe
0x1800092c0  sub     rsp, rax
0x1800092c3  mov     rbx, [rsp+1528h+arg_28]
0x1800092cb  mov     rdi, rcx
0x1800092ce  lea     rcx, [rsp+1528h+var_14A8]; void *
0x1800092d6  xor     edx, edx; Val
0x1800092d8  mov     r8d, 98h; Size
0x1800092de  call    memset_0
0x1800092e3  xor     ecx, ecx
0x1800092e5  lea     rax, [rsp+1528h+var_14A8]
0x1800092ed  mov     [rsp+1528h+var_14B0], rax
0x1800092f2  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800092f9  mov     [rsp+1528h+var_14B8], ecx
0x1800092fd  lea     rax, [rsp+1528h+var_1408]
0x180009305  mov     [rsp+1528h+var_14C8], rax
0x18000930a  xor     r9d, r9d
0x18000930d  lea     rax, [rsp+1528h+var_1008]
0x180009315  mov     edx, 0F89h
0x18000931a  mov     [rsp+1528h+var_14D8], rax
0x18000931f  mov     rax, [rsp+1528h+arg_30]
0x180009327  mov     [rsp+1528h+var_14E8], rcx
0x18000932c  mov     [rsp+1528h+var_14F0], rax
0x180009331  mov     [rsp+1528h+var_14F8], 3
0x180009339  mov     [rsp+1528h+var_1500], rbx
0x18000933e  mov     [rsp+1528h+var_1508], rcx
0x180009343  mov     rcx, rdi
0x180009346  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x18000934b  lea     rcx, [rsp+1528h+var_14A8]; this
0x180009353  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
