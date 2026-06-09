# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800145d4`
- end: `0x1800146de`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800143cc`

## callees

- `0x180002088`
- `0x180004dfc`
- `0x180005fb4`
- `0x180006260`
- `0x1800145d4`
- `0x180018ca0`
- `0x18001a010`

## string_xrefs

- `0x180014628`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        unsigned int *a7)
{
  bool v8; // si
  const struct wil::FailureInfo *v9; // rdx
  const struct wil::FailureInfo *v10; // rdx
  __int64 v11; // [rsp+48h] [rbp-14E0h]
  __int64 v12; // [rsp+58h] [rbp-14D0h]
  __int64 v13; // [rsp+68h] [rbp-14C0h]
  _BYTE v14[160]; // [rsp+80h] [rbp-14A8h] BYREF
  _BYTE v15[1024]; // [rsp+120h] [rbp-1408h] BYREF
  _BYTE v16[4104]; // [rsp+520h] [rbp-1008h] BYREF

  v8 = g_pfnThrowPlatformException != 0;
  memset_0(v14, 0, 0x98u);
  wil::details::LogFailure(
    a1,
    5331,
    (__int64)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    0,
    0,
    a6,
    0,
    a7,
    0,
    v11,
    (wil *)v16,
    v12,
    v15,
    v13,
    0,
    (unsigned __int64)v14);
  if ( (v14[4] & 1) != 0 )
    wil::details::WilFailFast((wil::details *)v14, v9);
  if ( v8 )
    ((void (__fastcall *)(_BYTE *, _BYTE *))g_pfnThrowPlatformException)(v14, v16);
  wil::ThrowResultException((wil *)v14, v9);
  wil::details::WilFailFast((wil::details *)v14, v10);
}

```

## disassembly

```asm
0x1800145d4  mov     [rsp+arg_8], rbx
0x1800145d9  mov     [rsp+arg_10], rsi
0x1800145de  push    rdi
0x1800145df  mov     eax, 1520h
0x1800145e4  call    _alloca_probe
0x1800145e9  sub     rsp, rax
0x1800145ec  cmp     cs:g_pfnThrowPlatformException, 0
0x1800145f4  mov     rdi, rcx
0x1800145f7  mov     rbx, [rsp+1528h+arg_28]
0x1800145ff  lea     rcx, [rsp+1528h+var_14A8]; void *
0x180014607  setnz   sil
0x18001460b  mov     r8d, 98h; Size
0x180014611  xor     edx, edx; Val
0x180014613  call    memset_0
0x180014618  lea     rax, [rsp+1528h+var_14A8]
0x180014620  xor     r9d, r9d
0x180014623  mov     [rsp+1528h+var_14B0], rax
0x180014628  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001462f  mov     [rsp+1528h+var_14B8], 0
0x180014637  lea     rax, [rsp+1528h+var_1408]
0x18001463f  mov     [rsp+1528h+var_14C8], rax
0x180014644  mov     edx, 14D3h
0x180014649  lea     rax, [rsp+1528h+var_1008]
0x180014651  mov     rcx, rdi
0x180014654  mov     [rsp+1528h+var_14D8], rax
0x180014659  mov     rax, [rsp+1528h+arg_30]
0x180014661  mov     [rsp+1528h+var_14E8], 0
0x18001466a  mov     [rsp+1528h+var_14F0], rax
0x18001466f  mov     [rsp+1528h+var_14F8], 0
0x180014677  mov     [rsp+1528h+var_1500], rbx
0x18001467c  mov     [rsp+1528h+var_1508], 0
0x180014685  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x18001468a  test    [rsp+1528h+var_14A4], 1
0x180014692  jz      short loc_1800146A2
0x180014694  lea     rcx, [rsp+1528h+var_14A8]; this
0x18001469c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800146a2  test    sil, sil
0x1800146a5  jz      short loc_1800146C3
0x1800146a7  mov     rax, cs:g_pfnThrowPlatformException
0x1800146ae  lea     rdx, [rsp+1528h+var_1008]
0x1800146b6  lea     rcx, [rsp+1528h+var_14A8]
0x1800146be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800146c3  lea     rcx, [rsp+1528h+var_14A8]; this
0x1800146cb  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800146d0  lea     rcx, [rsp+1528h+var_14A8]; this
0x1800146d8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
