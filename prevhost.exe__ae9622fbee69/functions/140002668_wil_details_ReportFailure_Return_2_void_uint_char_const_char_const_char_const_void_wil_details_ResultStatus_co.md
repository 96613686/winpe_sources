# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002668`
- end: `0x140002787`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140001ec0`

## callees

- `0x140001470`
- `0x140001e52`
- `0x140002668`
- `0x1400040dc`
- `0x140005570`
- `0x140005b00`

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
0x140002668  push    rbx
0x14000266a  push    rbp
0x14000266b  push    rsi
0x14000266c  push    rdi
0x14000266d  push    r12
0x14000266f  push    r13
0x140002671  push    r14
0x140002673  push    r15
0x140002675  mov     eax, 1538h
0x14000267a  call    _alloca_probe
0x14000267f  sub     rsp, rax
0x140002682  mov     rax, cs:__security_cookie
0x140002689  xor     rax, rsp
0x14000268c  mov     [rsp+1578h+var_58], rax
0x140002694  mov     rbp, [rsp+1578h+arg_20]
0x14000269c  mov     r12, r8
0x14000269f  mov     rsi, [rsp+1578h+arg_28]
0x1400026a7  mov     r15d, edx
0x1400026aa  mov     rdi, [rsp+1578h+arg_30]
0x1400026b2  mov     r14, rcx
0x1400026b5  mov     rbx, [rsp+1578h+arg_38]
0x1400026bd  lea     rcx, [rsp+1578h+var_14F8]; void *
0x1400026c5  xor     edx, edx; Val
0x1400026c7  mov     r8d, 98h; Size
0x1400026cd  mov     r13, r9
0x1400026d0  call    memset_0
0x1400026d5  lea     rax, [rsp+1578h+var_14F8]
0x1400026dd  mov     r9, r13
0x1400026e0  mov     [rsp+1578h+var_1500], rax
0x1400026e5  mov     r8, r12
0x1400026e8  mov     eax, [rsp+1578h+arg_48]
0x1400026ef  mov     edx, r15d
0x1400026f2  mov     [rsp+1578h+var_1508], eax
0x1400026f6  mov     rcx, r14
0x1400026f9  mov     [rsp+1578h+var_1510], 400h
0x140002702  lea     rax, [rsp+1578h+var_1458]
0x14000270a  mov     [rsp+1578h+var_1518], rax
0x14000270f  lea     rax, [rsp+1578h+var_1058]
0x140002717  mov     [rsp+1578h+var_1520], 800h
0x140002720  mov     [rsp+1578h+var_1528], rax
0x140002725  mov     byte ptr [rsp+1578h+var_1530], 0
0x14000272a  mov     [rsp+1578h+var_1538], rbx
0x14000272f  mov     [rsp+1578h+var_1540], rdi
0x140002734  mov     [rsp+1578h+var_1548], 2
0x14000273c  mov     [rsp+1578h+var_1550], rsi
0x140002741  mov     [rsp+1578h+var_1558], rbp
0x140002746  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x14000274b  test    [rsp+1578h+var_14F4], 1
0x140002753  jnz     short loc_140002779
0x140002755  mov     rcx, [rsp+1578h+var_58]
0x14000275d  xor     rcx, rsp; StackCookie
0x140002760  call    __security_check_cookie
0x140002765  add     rsp, 1538h
0x14000276c  pop     r15
0x14000276e  pop     r14
0x140002770  pop     r13
0x140002772  pop     r12
0x140002774  pop     rdi
0x140002775  pop     rsi
0x140002776  pop     rbp
0x140002777  pop     rbx
0x140002778  retn
0x140002779  lea     rcx, [rsp+1578h+var_14F8]; this
0x140002781  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
