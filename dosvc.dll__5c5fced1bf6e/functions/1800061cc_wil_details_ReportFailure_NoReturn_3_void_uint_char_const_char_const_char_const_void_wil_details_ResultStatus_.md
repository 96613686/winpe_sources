# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800061cc`
- end: `0x180006279`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `173`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000606c`

## callees

- `0x180002780`
- `0x180005b2c`
- `0x180008360`
- `0x18000a680`

## string_xrefs

- `0x180006215`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800061cc  mov     [rsp+arg_10], rbx
0x1800061d1  mov     [rsp+arg_18], rsi
0x1800061d6  push    rdi
0x1800061d7  mov     eax, 1520h
0x1800061dc  call    _alloca_probe
0x1800061e1  sub     rsp, rax
0x1800061e4  mov     rbx, [rsp+1528h+arg_28]
0x1800061ec  mov     esi, edx
0x1800061ee  mov     rdi, rcx
0x1800061f1  xor     edx, edx; Val
0x1800061f3  lea     rcx, [rsp+1528h+var_14A8]; void *
0x1800061fb  mov     r8d, 98h; Size
0x180006201  call    memset_0
0x180006206  xor     ecx, ecx
0x180006208  lea     rax, [rsp+1528h+var_14A8]
0x180006210  mov     [rsp+1528h+var_14B0], rax
0x180006215  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000621c  mov     [rsp+1528h+var_14B8], ecx
0x180006220  lea     rax, [rsp+1528h+var_1408]
0x180006228  mov     [rsp+1528h+var_14C8], rax
0x18000622d  xor     r9d, r9d
0x180006230  lea     rax, [rsp+1528h+var_1008]
0x180006238  mov     edx, esi
0x18000623a  mov     [rsp+1528h+var_14D8], rax
0x18000623f  mov     rax, [rsp+1528h+arg_30]
0x180006247  mov     [rsp+1528h+var_14E8], rcx
0x18000624c  mov     [rsp+1528h+var_14F0], rax
0x180006251  mov     [rsp+1528h+var_14F8], 3
0x180006259  mov     [rsp+1528h+var_1500], rbx
0x18000625e  mov     [rsp+1528h+var_1508], rcx
0x180006263  mov     rcx, rdi
0x180006266  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x18000626b  lea     rcx, [rsp+1528h+var_14A8]; this
0x180006273  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
