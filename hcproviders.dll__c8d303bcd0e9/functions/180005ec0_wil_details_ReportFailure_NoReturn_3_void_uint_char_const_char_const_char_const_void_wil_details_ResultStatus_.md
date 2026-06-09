# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180005ec0`
- end: `0x180005f6d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180005d1c`

## callees

- `0x180007474`
- `0x1800082b0`
- `0x180009e16`
- `0x180009ed0`

## string_xrefs

- `0x180005f09`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int *a7)
{
  const struct wil::FailureInfo *v9; // rdx
  __int64 v10; // [rsp+48h] [rbp-14E0h]
  __int64 v11; // [rsp+58h] [rbp-14D0h]
  __int64 v12; // [rsp+68h] [rbp-14C0h]
  _BYTE v13[160]; // [rsp+80h] [rbp-14A8h] BYREF
  _BYTE v14[1024]; // [rsp+120h] [rbp-1408h] BYREF
  _BYTE v15[4104]; // [rsp+520h] [rbp-1008h] BYREF

  memset_0(v13, 0, 0x98u);
  wil::details::LogFailure(
    a1,
    a2,
    (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    0,
    0,
    a6,
    3,
    a7,
    0,
    v10,
    (wil *)v15,
    v11,
    v14,
    v12,
    0,
    (unsigned __int64)v13);
  wil::details::WilFailFast((wil::details *)v13, v9);
}

```

## disassembly

```asm
0x180005ec0  mov     [rsp+arg_10], rbx
0x180005ec5  mov     [rsp+arg_18], rsi
0x180005eca  push    rdi
0x180005ecb  mov     eax, 1520h
0x180005ed0  call    _alloca_probe
0x180005ed5  sub     rsp, rax
0x180005ed8  mov     rbx, [rsp+1528h+arg_28]
0x180005ee0  mov     esi, edx
0x180005ee2  mov     rdi, rcx
0x180005ee5  xor     edx, edx; Val
0x180005ee7  lea     rcx, [rsp+1528h+var_14A8]; void *
0x180005eef  mov     r8d, 98h; Size
0x180005ef5  call    memset_0
0x180005efa  xor     ecx, ecx
0x180005efc  lea     rax, [rsp+1528h+var_14A8]
0x180005f04  mov     [rsp+1528h+var_14B0], rax
0x180005f09  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005f10  mov     [rsp+1528h+var_14B8], ecx
0x180005f14  lea     rax, [rsp+1528h+var_1408]
0x180005f1c  mov     [rsp+1528h+var_14C8], rax
0x180005f21  xor     r9d, r9d
0x180005f24  lea     rax, [rsp+1528h+var_1008]
0x180005f2c  mov     edx, esi
0x180005f2e  mov     [rsp+1528h+var_14D8], rax
0x180005f33  mov     rax, [rsp+1528h+arg_30]
0x180005f3b  mov     [rsp+1528h+var_14E8], rcx
0x180005f40  mov     [rsp+1528h+var_14F0], rax
0x180005f45  mov     [rsp+1528h+var_14F8], 3
0x180005f4d  mov     [rsp+1528h+var_1500], rbx
0x180005f52  mov     [rsp+1528h+var_1508], rcx
0x180005f57  mov     rcx, rdi
0x180005f5a  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x180005f5f  lea     rcx, [rsp+1528h+var_14A8]; this
0x180005f67  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
