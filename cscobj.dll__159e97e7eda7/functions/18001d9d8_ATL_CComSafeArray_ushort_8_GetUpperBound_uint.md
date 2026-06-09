# ATL::CComSafeArray<ushort *,8>::GetUpperBound(uint)

- ea: `0x18001d9d8`
- end: `0x18001da10`
- name: `?GetUpperBound@?$CComSafeArray@PEAG$07@ATL@@QEBAJI@Z`
- size: `56`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001cc7c`
- `0x18001dec8`
- `0x18001e100`
- `0x18001e4f8`
- `0x18001e9b8`
- `0x18001ec30`
- `0x18001f22c`
- `0x180028d64`

## callees

- `0x18001886c`
- `0x18001d9d8`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001d9f5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001d9f5`

## pseudocode

```c
__int64 __fastcall ATL::CComSafeArray<unsigned short *,8>::GetUpperBound(SAFEARRAY **a1, LONG a2)
{
  SAFEARRAY *v2; // rcx
  HRESULT UBound; // eax
  LONG plUbound; // [rsp+38h] [rbp+10h] BYREF

  plUbound = a2;
  v2 = *a1;
  plUbound = 0;
  UBound = SafeArrayGetUBound(v2, 1u, &plUbound);
  if ( UBound < 0 )
    ATL::AtlThrowImpl(UBound);
  return (unsigned int)plUbound;
}

```

## disassembly

```asm
0x18001d9d8  mov     [rsp+plUbound], edx
0x18001d9dc  sub     rsp, 28h
0x18001d9e0  mov     rcx, [rcx]; psa
0x18001d9e3  lea     r8, [rsp+28h+plUbound]; plUbound
0x18001d9e8  mov     edx, 1; nDim
0x18001d9ed  mov     [rsp+28h+plUbound], 0
0x18001d9f5  call    cs:__imp_SafeArrayGetUBound
0x18001d9fb  test    eax, eax
0x18001d9fd  jns     short loc_18001DA07
0x18001d9ff  mov     ecx, eax; int
0x18001da01  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001da07  mov     eax, [rsp+28h+plUbound]
0x18001da0b  add     rsp, 28h
0x18001da0f  retn
```
