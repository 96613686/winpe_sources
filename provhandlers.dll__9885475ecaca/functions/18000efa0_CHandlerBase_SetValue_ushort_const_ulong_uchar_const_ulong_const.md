# CHandlerBase::SetValue(ushort const *,ulong,uchar const *,ulong const *)

- ea: `0x18000efa0`
- end: `0x18000f002`
- name: `?SetValue@CHandlerBase@@UEAAJPEBGKPEBEPEBK@Z`
- size: `98`
- prototype: `__int64 __fastcall(CHandlerBase *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int8 *, const unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800076a4`
- `0x18000efa0`
- `0x180037aa8`

## string_xrefs

- `0x18000efb3`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`
- `0x18000efe1`: `onecoreuap\admin\prov\multivariant\handlers\common\handlerbase.cpp`

## pseudocode

```c
__int64 __fastcall CHandlerBase::SetValue(
        CHandlerBase *this,
        const unsigned __int16 *a2,
        __int64 a3,
        const unsigned __int8 *a4)
{
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a2 )
  {
    v4 = 121;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
      (const char *)0x80004003LL,
      v6);
    return 2147500035LL;
  }
  if ( !a4 )
  {
    v4 = 122;
    goto LABEL_3;
  }
  MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3, a4);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x7E,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\common\\handlerbase.cpp",
    (const char *)0x80004001LL,
    v6);
  return 2147500033LL;
}

```

## disassembly

```asm
0x18000efa0  sub     rsp, 28h
0x18000efa4  test    rdx, rdx
0x18000efa7  jnz     short loc_18000EFCC
0x18000efa9  mov     edx, 79h ; 'y'; void *
0x18000efae  mov     rcx, [rsp+28h]; this
0x18000efb3  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000efba  mov     r9d, 80004003h; char *
0x18000efc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000efc5  mov     eax, 80004003h
0x18000efca  jmp     short loc_18000EFFD
0x18000efcc  test    r9, r9
0x18000efcf  jnz     short loc_18000EFD7
0x18000efd1  lea     edx, [r9+7Ah]
0x18000efd5  jmp     short loc_18000EFAE
0x18000efd7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000efdc  mov     rcx, [rsp+28h]; this
0x18000efe1  lea     r8, aOnecoreuapAdmi_13; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000efe8  mov     r9d, 80004001h; char *
0x18000efee  mov     edx, 7Eh ; '~'; void *
0x18000eff3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000eff8  mov     eax, 80004001h
0x18000effd  add     rsp, 28h
0x18000f001  retn
```
