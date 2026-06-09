# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002174`
- end: `0x140002293`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140001d84`

## callees

- `0x140001380`
- `0x140001d16`
- `0x140002174`
- `0x140002920`
- `0x140002e80`
- `0x140003250`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // [rsp+48h] [rbp-1530h]
  _BYTE v16[160]; // [rsp+80h] [rbp-14F8h] BYREF
  _BYTE v17[1024]; // [rsp+120h] [rbp-1458h] BYREF
  _BYTE v18[4096]; // [rsp+520h] [rbp-1058h] BYREF

  memset_0(v16, 0, 0x98u);
  LOBYTE(v15) = 0;
  wil::details::LogFailure(
    a1,
    a2,
    a3,
    a4,
    a5,
    a6,
    2,
    a7,
    a8,
    v15,
    (wil *)v18,
    2048,
    v17,
    1024,
    a10,
    (unsigned __int64)v16);
  if ( (v16[4] & 1) != 0 )
    wil::details::WilFailFast((wil::details *)v16, v14);
}

```

## disassembly

```asm
0x140002174  push    rbx
0x140002176  push    rbp
0x140002177  push    rsi
0x140002178  push    rdi
0x140002179  push    r12
0x14000217b  push    r13
0x14000217d  push    r14
0x14000217f  push    r15
0x140002181  mov     eax, 1538h
0x140002186  call    _alloca_probe
0x14000218b  sub     rsp, rax
0x14000218e  mov     rax, cs:__security_cookie
0x140002195  xor     rax, rsp
0x140002198  mov     [rsp+1578h+var_58], rax
0x1400021a0  mov     rbp, [rsp+1578h+arg_20]
0x1400021a8  mov     r12, r8
0x1400021ab  mov     rsi, [rsp+1578h+arg_28]
0x1400021b3  mov     r15d, edx
0x1400021b6  mov     rdi, [rsp+1578h+arg_30]
0x1400021be  mov     r14, rcx
0x1400021c1  mov     rbx, [rsp+1578h+arg_38]
0x1400021c9  lea     rcx, [rsp+1578h+var_14F8]; void *
0x1400021d1  xor     edx, edx; Val
0x1400021d3  mov     r8d, 98h; Size
0x1400021d9  mov     r13, r9
0x1400021dc  call    memset_0
0x1400021e1  lea     rax, [rsp+1578h+var_14F8]
0x1400021e9  mov     r9, r13
0x1400021ec  mov     [rsp+1578h+var_1500], rax
0x1400021f1  mov     r8, r12
0x1400021f4  mov     eax, [rsp+1578h+arg_48]
0x1400021fb  mov     edx, r15d
0x1400021fe  mov     [rsp+1578h+var_1508], eax
0x140002202  mov     rcx, r14
0x140002205  mov     [rsp+1578h+var_1510], 400h
0x14000220e  lea     rax, [rsp+1578h+var_1458]
0x140002216  mov     [rsp+1578h+var_1518], rax
0x14000221b  lea     rax, [rsp+1578h+var_1058]
0x140002223  mov     [rsp+1578h+var_1520], 800h
0x14000222c  mov     [rsp+1578h+var_1528], rax
0x140002231  mov     byte ptr [rsp+1578h+var_1530], 0
0x140002236  mov     [rsp+1578h+var_1538], rbx
0x14000223b  mov     [rsp+1578h+var_1540], rdi
0x140002240  mov     [rsp+1578h+var_1548], 2
0x140002248  mov     [rsp+1578h+var_1550], rsi
0x14000224d  mov     [rsp+1578h+var_1558], rbp
0x140002252  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x140002257  test    [rsp+1578h+var_14F4], 1
0x14000225f  jnz     short loc_140002285
0x140002261  mov     rcx, [rsp+1578h+var_58]
0x140002269  xor     rcx, rsp; StackCookie
0x14000226c  call    __security_check_cookie
0x140002271  add     rsp, 1538h
0x140002278  pop     r15
0x14000227a  pop     r14
0x14000227c  pop     r13
0x14000227e  pop     r12
0x140002280  pop     rdi
0x140002281  pop     rsi
0x140002282  pop     rbp
0x140002283  pop     rbx
0x140002284  retn
0x140002285  lea     rcx, [rsp+1578h+var_14F8]; this
0x14000228d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
