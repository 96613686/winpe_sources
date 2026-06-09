# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180016f08`
- end: `0x18001700e`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180016c88`

## callees

- `0x180015174`
- `0x180016f08`
- `0x18001a3dc`
- `0x18001ca18`
- `0x18001d010`
- `0x18002e480`
- `0x180030010`

## string_xrefs

- `0x180016f5b`: `onecoreuap\internal\admin\inc\private\registryutils.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int *a7)
{
  bool v9; // bp
  const struct wil::FailureInfo *v10; // rdx
  const struct wil::FailureInfo *v11; // rdx
  __int64 v12; // [rsp+48h] [rbp-14F0h]
  __int64 v13; // [rsp+58h] [rbp-14E0h]
  __int64 v14; // [rsp+68h] [rbp-14D0h]
  _BYTE v15[160]; // [rsp+80h] [rbp-14B8h] BYREF
  _BYTE v16[1024]; // [rsp+120h] [rbp-1418h] BYREF
  _BYTE v17[4120]; // [rsp+520h] [rbp-1018h] BYREF

  v9 = g_pfnThrowPlatformException != 0;
  memset_0(v15, 0, 0x98u);
  wil::details::LogFailure(
    a1,
    a2,
    (__int64)"onecoreuap\\internal\\admin\\inc\\private\\registryutils.h",
    0,
    0,
    a6,
    0,
    a7,
    0,
    v12,
    (wil *)v17,
    v13,
    v16,
    v14,
    0,
    (unsigned __int64)v15);
  if ( (v15[4] & 1) != 0 )
    wil::details::WilFailFast((wil::details *)v15, v10);
  if ( v9 )
    ((void (__fastcall *)(_BYTE *, _BYTE *))g_pfnThrowPlatformException)(v15, v17);
  wil::ThrowResultException((wil *)v15, v10);
  wil::details::WilFailFast((wil::details *)v15, v11);
}

```

## disassembly

```asm
0x180016f08  mov     [rsp+arg_10], rbx
0x180016f0d  push    rbp
0x180016f0e  push    rsi
0x180016f0f  push    rdi
0x180016f10  mov     eax, 1520h
0x180016f15  call    _alloca_probe
0x180016f1a  sub     rsp, rax
0x180016f1d  cmp     cs:g_pfnThrowPlatformException, 0
0x180016f25  mov     esi, edx
0x180016f27  mov     rbx, [rsp+1538h+arg_28]
0x180016f2f  mov     rdi, rcx
0x180016f32  setnz   bpl
0x180016f36  lea     rcx, [rsp+1538h+var_14B8]; void *
0x180016f3e  xor     edx, edx; Val
0x180016f40  mov     r8d, 98h; Size
0x180016f46  call    memset_0
0x180016f4b  lea     rax, [rsp+1538h+var_14B8]
0x180016f53  xor     r9d, r9d
0x180016f56  mov     [rsp+1538h+var_14C0], rax
0x180016f5b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\admin\\inc\\priva"...
0x180016f62  mov     [rsp+1538h+var_14C8], 0
0x180016f6a  lea     rax, [rsp+1538h+var_1418]
0x180016f72  mov     [rsp+1538h+var_14D8], rax
0x180016f77  mov     edx, esi
0x180016f79  lea     rax, [rsp+1538h+var_1018]
0x180016f81  mov     rcx, rdi
0x180016f84  mov     [rsp+1538h+var_14E8], rax
0x180016f89  mov     rax, [rsp+1538h+arg_30]
0x180016f91  mov     [rsp+1538h+var_14F8], 0
0x180016f9a  mov     [rsp+1538h+var_1500], rax
0x180016f9f  mov     [rsp+1538h+var_1508], 0
0x180016fa7  mov     [rsp+1538h+var_1510], rbx
0x180016fac  mov     [rsp+1538h+var_1518], 0
0x180016fb5  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x180016fba  test    [rsp+1538h+var_14B4], 1
0x180016fc2  jz      short loc_180016FD2
0x180016fc4  lea     rcx, [rsp+1538h+var_14B8]; this
0x180016fcc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180016fd2  test    bpl, bpl
0x180016fd5  jz      short loc_180016FF3
0x180016fd7  mov     rax, cs:g_pfnThrowPlatformException
0x180016fde  lea     rdx, [rsp+1538h+var_1018]
0x180016fe6  lea     rcx, [rsp+1538h+var_14B8]
0x180016fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ff3  lea     rcx, [rsp+1538h+var_14B8]; this
0x180016ffb  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180017000  lea     rcx, [rsp+1538h+var_14B8]; this
0x180017008  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
