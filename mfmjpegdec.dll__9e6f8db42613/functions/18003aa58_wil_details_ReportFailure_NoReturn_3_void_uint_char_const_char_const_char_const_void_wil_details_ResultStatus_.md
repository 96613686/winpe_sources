# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18003aa58`
- end: `0x18003ab05`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003a848`

## callees

- `0x180024bf4`
- `0x18003a740`
- `0x18003c5e0`
- `0x18003da20`

## string_xrefs

- `0x18003aaa1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18003aa58  mov     [rsp+arg_10], rbx
0x18003aa5d  mov     [rsp+arg_18], rsi
0x18003aa62  push    rdi
0x18003aa63  mov     eax, 1520h
0x18003aa68  call    _alloca_probe
0x18003aa6d  sub     rsp, rax
0x18003aa70  mov     rbx, [rsp+1528h+arg_28]
0x18003aa78  mov     esi, edx
0x18003aa7a  mov     rdi, rcx
0x18003aa7d  xor     edx, edx; Val
0x18003aa7f  lea     rcx, [rsp+1528h+var_14A8]; void *
0x18003aa87  mov     r8d, 98h; Size
0x18003aa8d  call    memset_0
0x18003aa92  xor     ecx, ecx
0x18003aa94  lea     rax, [rsp+1528h+var_14A8]
0x18003aa9c  mov     [rsp+1528h+var_14B0], rax
0x18003aaa1  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003aaa8  mov     [rsp+1528h+var_14B8], ecx
0x18003aaac  lea     rax, [rsp+1528h+var_1408]
0x18003aab4  mov     [rsp+1528h+var_14C8], rax
0x18003aab9  xor     r9d, r9d
0x18003aabc  lea     rax, [rsp+1528h+var_1008]
0x18003aac4  mov     edx, esi
0x18003aac6  mov     [rsp+1528h+var_14D8], rax
0x18003aacb  mov     rax, [rsp+1528h+arg_30]
0x18003aad3  mov     [rsp+1528h+var_14E8], rcx
0x18003aad8  mov     [rsp+1528h+var_14F0], rax
0x18003aadd  mov     [rsp+1528h+var_14F8], 3
0x18003aae5  mov     [rsp+1528h+var_1500], rbx
0x18003aaea  mov     [rsp+1528h+var_1508], rcx
0x18003aaef  mov     rcx, rdi
0x18003aaf2  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x18003aaf7  lea     rcx, [rsp+1528h+var_14A8]; this
0x18003aaff  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
