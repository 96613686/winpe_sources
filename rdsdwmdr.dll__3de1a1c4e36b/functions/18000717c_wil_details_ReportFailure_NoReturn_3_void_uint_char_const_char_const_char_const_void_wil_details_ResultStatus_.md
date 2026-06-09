# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000717c`
- end: `0x180007229`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180006f60`

## callees

- `0x18000a448`
- `0x18000c768`
- `0x18002b93a`
- `0x18002b9f0`

## string_xrefs

- `0x1800071c5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  const struct wil::FailureInfo *v9; // rdx
  _BYTE v10[160]; // [rsp+80h] [rbp-14A8h] BYREF

  memset_0(v10, 0, 0x98u);
  wil::details::LogFailure(a1, a2, "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h", 0, 0, a6, 3, a7, 0);
  wil::details::WilFailFast((wil::details *)v10, v9);
}

```

## disassembly

```asm
0x18000717c  mov     [rsp+arg_10], rbx
0x180007181  mov     [rsp+arg_18], rsi
0x180007186  push    rdi
0x180007187  mov     eax, 1520h
0x18000718c  call    _alloca_probe
0x180007191  sub     rsp, rax
0x180007194  mov     rbx, [rsp+1528h+arg_28]
0x18000719c  mov     esi, edx
0x18000719e  mov     rdi, rcx
0x1800071a1  xor     edx, edx; Val
0x1800071a3  lea     rcx, [rsp+1528h+var_14A8]; void *
0x1800071ab  mov     r8d, 98h; Size
0x1800071b1  call    memset_0
0x1800071b6  xor     ecx, ecx
0x1800071b8  lea     rax, [rsp+1528h+var_14A8]
0x1800071c0  mov     [rsp+1528h+var_14B0], rax
0x1800071c5  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800071cc  mov     [rsp+1528h+var_14B8], ecx
0x1800071d0  lea     rax, [rsp+1528h+var_1408]
0x1800071d8  mov     [rsp+1528h+var_14C8], rax
0x1800071dd  xor     r9d, r9d
0x1800071e0  lea     rax, [rsp+1528h+var_1008]
0x1800071e8  mov     edx, esi
0x1800071ea  mov     [rsp+1528h+var_14D8], rax
0x1800071ef  mov     rax, [rsp+1528h+arg_30]
0x1800071f7  mov     [rsp+1528h+var_14E8], rcx
0x1800071fc  mov     [rsp+1528h+var_14F0], rax
0x180007201  mov     [rsp+1528h+var_14F8], 3
0x180007209  mov     [rsp+1528h+var_1500], rbx
0x18000720e  mov     [rsp+1528h+var_1508], rcx
0x180007213  mov     rcx, rdi
0x180007216  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x18000721b  lea     rcx, [rsp+1528h+var_14A8]; this
0x180007223  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
