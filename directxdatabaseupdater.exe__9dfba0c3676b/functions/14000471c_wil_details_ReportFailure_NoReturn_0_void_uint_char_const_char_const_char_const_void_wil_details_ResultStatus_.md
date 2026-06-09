# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x14000471c`
- end: `0x140004820`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `260`
- prototype: `void __fastcall __noreturn(__int64, unsigned int, __int64, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x140004238`

## callees

- `0x140003ab8`
- `0x14000471c`
- `0x140008600`
- `0x14000d6a8`
- `0x140018460`
- `0x14001a010`

## string_xrefs

- `0x14000476f`: `onecore\windows\directx\database\updater\exe\main.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  bool v9; // bp
  const struct wil::FailureInfo *v10; // rdx
  _BYTE v11[160]; // [rsp+80h] [rbp-14B8h] BYREF
  _BYTE v12[4120]; // [rsp+520h] [rbp-1018h] BYREF

  v9 = g_pfnThrowPlatformException != 0;
  memset_0(v11, 0, 0x98u);
  wil::details::LogFailure(a1, a2, "onecore\\windows\\directx\\database\\updater\\exe\\main.cpp", 0, 0, a6, 0, a7, 0);
  if ( (v11[4] & 1) == 0 )
  {
    if ( v9 )
      ((void (__fastcall *)(_BYTE *, _BYTE *))g_pfnThrowPlatformException)(v11, v12);
    if ( wil::details::g_pfnThrowResultException )
      wil::details::g_pfnThrowResultException((const struct wil::FailureInfo *)v11);
  }
  wil::details::WilFailFast((wil::details *)v11, v10);
}

```

## disassembly

```asm
0x14000471c  mov     [rsp+arg_10], rbx
0x140004721  push    rbp
0x140004722  push    rsi
0x140004723  push    rdi
0x140004724  mov     eax, 1520h
0x140004729  call    _alloca_probe
0x14000472e  sub     rsp, rax
0x140004731  cmp     cs:g_pfnThrowPlatformException, 0
0x140004739  mov     esi, edx
0x14000473b  mov     rbx, [rsp+1538h+arg_28]
0x140004743  mov     rdi, rcx
0x140004746  setnz   bpl
0x14000474a  lea     rcx, [rsp+1538h+var_14B8]; void *
0x140004752  xor     edx, edx; Val
0x140004754  mov     r8d, 98h; Size
0x14000475a  call    memset_0
0x14000475f  lea     rax, [rsp+1538h+var_14B8]
0x140004767  xor     r9d, r9d
0x14000476a  mov     [rsp+1538h+var_14C0], rax
0x14000476f  lea     r8, aOnecoreWindows_2; "onecore\\windows\\directx\\database\\up"...
0x140004776  mov     [rsp+1538h+var_14C8], 0
0x14000477e  lea     rax, [rsp+1538h+var_1418]
0x140004786  mov     [rsp+1538h+var_14D8], rax
0x14000478b  mov     edx, esi
0x14000478d  lea     rax, [rsp+1538h+var_1018]
0x140004795  mov     rcx, rdi
0x140004798  mov     [rsp+1538h+var_14E8], rax
0x14000479d  mov     rax, [rsp+1538h+arg_30]
0x1400047a5  mov     [rsp+1538h+var_14F8], 0
0x1400047ae  mov     [rsp+1538h+var_1500], rax
0x1400047b3  mov     [rsp+1538h+var_1508], 0
0x1400047bb  mov     [rsp+1538h+var_1510], rbx
0x1400047c0  mov     [rsp+1538h+var_1518], 0
0x1400047c9  call    ?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z; wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)
0x1400047ce  test    [rsp+1538h+var_14B4], 1
0x1400047d6  jnz     short loc_140004812
0x1400047d8  test    bpl, bpl
0x1400047db  jz      short loc_1400047F9
0x1400047dd  mov     rax, cs:g_pfnThrowPlatformException
0x1400047e4  lea     rdx, [rsp+1538h+var_1018]
0x1400047ec  lea     rcx, [rsp+1538h+var_14B8]
0x1400047f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047f9  mov     rax, cs:?g_pfnThrowResultException@details@wil@@3P6AXAEBUFailureInfo@2@@ZEA; void (*wil::details::g_pfnThrowResultException)(wil::FailureInfo const &)
0x140004800  test    rax, rax
0x140004803  jz      short loc_140004812
0x140004805  lea     rcx, [rsp+1538h+var_14B8]
0x14000480d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004812  lea     rcx, [rsp+1538h+var_14B8]; this
0x14000481a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
