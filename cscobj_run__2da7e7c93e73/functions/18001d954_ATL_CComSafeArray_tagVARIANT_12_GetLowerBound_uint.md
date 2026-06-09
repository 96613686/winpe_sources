# ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(uint)

- ea: `0x18001d954`
- end: `0x18001d98c`
- name: `?GetLowerBound@?$CComSafeArray@UtagVARIANT@@$0M@@ATL@@QEBAJI@Z`
- size: `56`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001cc7c`
- `0x18001cda0`
- `0x18001dec8`
- `0x18001e100`
- `0x18001e4f8`
- `0x18001e9b8`
- `0x18001ec30`
- `0x18001f22c`
- `0x180028d64`

## callees

- `0x18001886c`
- `0x18001d954`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001d971`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001d971`

## pseudocode

```c
__int64 __fastcall ATL::CComSafeArray<tagVARIANT,12>::GetLowerBound(SAFEARRAY **a1, LONG a2)
{
  SAFEARRAY *v2; // rcx
  HRESULT LBound; // eax
  LONG plLbound; // [rsp+38h] [rbp+10h] BYREF

  plLbound = a2;
  v2 = *a1;
  plLbound = 0;
  LBound = SafeArrayGetLBound(v2, 1u, &plLbound);
  if ( LBound < 0 )
    ATL::AtlThrowImpl(LBound);
  return (unsigned int)plLbound;
}

```

## disassembly

```asm
0x18001d954  mov     [rsp+plLbound], edx
0x18001d958  sub     rsp, 28h
0x18001d95c  mov     rcx, [rcx]; psa
0x18001d95f  lea     r8, [rsp+28h+plLbound]; plLbound
0x18001d964  mov     edx, 1; nDim
0x18001d969  mov     [rsp+28h+plLbound], 0
0x18001d971  call    cs:__imp_SafeArrayGetLBound
0x18001d977  test    eax, eax
0x18001d979  jns     short loc_18001D983
0x18001d97b  mov     ecx, eax; int
0x18001d97d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d983  mov     eax, [rsp+28h+plLbound]
0x18001d987  add     rsp, 28h
0x18001d98b  retn
```
