# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002840`
- end: `0x14000295f`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140002098`

## callees

- `0x1400017bf`
- `0x140002840`
- `0x140003d00`
- `0x140004b20`
- `0x140004cd0`
- `0x140004d60`

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
0x140002840  push    rbx
0x140002842  push    rbp
0x140002843  push    rsi
0x140002844  push    rdi
0x140002845  push    r12
0x140002847  push    r13
0x140002849  push    r14
0x14000284b  push    r15
0x14000284d  mov     eax, 1538h
0x140002852  call    _alloca_probe
0x140002857  sub     rsp, rax
0x14000285a  mov     rax, cs:__security_cookie
0x140002861  xor     rax, rsp
0x140002864  mov     [rsp+1578h+var_58], rax
0x14000286c  mov     rbp, [rsp+1578h+arg_20]
0x140002874  mov     r12, r8
0x140002877  mov     rsi, [rsp+1578h+arg_28]
0x14000287f  mov     r15d, edx
0x140002882  mov     rdi, [rsp+1578h+arg_30]
0x14000288a  mov     r14, rcx
0x14000288d  mov     rbx, [rsp+1578h+arg_38]
0x140002895  lea     rcx, [rsp+1578h+var_14F8]; void *
0x14000289d  xor     edx, edx; Val
0x14000289f  mov     r8d, 98h; Size
0x1400028a5  mov     r13, r9
0x1400028a8  call    memset_0
0x1400028ad  lea     rax, [rsp+1578h+var_14F8]
0x1400028b5  mov     r9, r13
0x1400028b8  mov     [rsp+1578h+var_1500], rax
0x1400028bd  mov     r8, r12
0x1400028c0  mov     eax, [rsp+1578h+arg_48]
0x1400028c7  mov     edx, r15d
0x1400028ca  mov     [rsp+1578h+var_1508], eax
0x1400028ce  mov     rcx, r14
0x1400028d1  mov     [rsp+1578h+var_1510], 400h
0x1400028da  lea     rax, [rsp+1578h+var_1458]
0x1400028e2  mov     [rsp+1578h+var_1518], rax
0x1400028e7  lea     rax, [rsp+1578h+var_1058]
0x1400028ef  mov     [rsp+1578h+var_1520], 800h
0x1400028f8  mov     [rsp+1578h+var_1528], rax
0x1400028fd  mov     byte ptr [rsp+1578h+var_1530], 0
0x140002902  mov     [rsp+1578h+var_1538], rbx
0x140002907  mov     [rsp+1578h+var_1540], rdi
0x14000290c  mov     [rsp+1578h+var_1548], 2
0x140002914  mov     [rsp+1578h+var_1550], rsi
0x140002919  mov     [rsp+1578h+var_1558], rbp
0x14000291e  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x140002923  test    [rsp+1578h+var_14F4], 1
0x14000292b  jnz     short loc_140002951
0x14000292d  mov     rcx, [rsp+1578h+var_58]
0x140002935  xor     rcx, rsp; StackCookie
0x140002938  call    __security_check_cookie
0x14000293d  add     rsp, 1538h
0x140002944  pop     r15
0x140002946  pop     r14
0x140002948  pop     r13
0x14000294a  pop     r12
0x14000294c  pop     rdi
0x14000294d  pop     rsi
0x14000294e  pop     rbp
0x14000294f  pop     rbx
0x140002950  retn
0x140002951  lea     rcx, [rsp+1578h+var_14F8]; this
0x140002959  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
