# ATL::CComSafeArray<ushort *,8>::GetCount(uint)

- ea: `0x18001d8e4`
- end: `0x18001d94d`
- name: `?GetCount@?$CComSafeArray@PEAG$07@ATL@@QEBAKI@Z`
- size: `105`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001cc7c`
- `0x18001cda0`
- `0x18001e100`
- `0x18001e4f8`
- `0x18001e9b8`
- `0x18001ec30`
- `0x18001f22c`
- `0x180028d64`

## callees

- `0x18001886c`
- `0x18001d8e4`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001d92b`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x18001d92b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001d90c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18001d90c`

## pseudocode

```c
__int64 __fastcall ATL::CComSafeArray<unsigned short *,8>::GetCount(SAFEARRAY **a1, LONG a2)
{
  SAFEARRAY *v3; // rcx
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  LONG v7; // [rsp+30h] [rbp+8h] BYREF
  LONG plUbound; // [rsp+38h] [rbp+10h] BYREF

  plUbound = a2;
  v7 = 0;
  v3 = *a1;
  plUbound = 0;
  LBound = SafeArrayGetLBound(v3, 1u, &v7);
  if ( LBound < 0 )
    ATL::AtlThrowImpl(LBound);
  UBound = SafeArrayGetUBound(*a1, 1u, &plUbound);
  if ( UBound < 0 )
    ATL::AtlThrowImpl(UBound);
  return (unsigned int)(plUbound - v7 + 1);
}

```

## disassembly

```asm
0x18001d8e4  mov     rax, rsp
0x18001d8e7  mov     [rax+10h], edx
0x18001d8ea  push    rbx
0x18001d8eb  sub     rsp, 20h
0x18001d8ef  mov     rbx, rcx
0x18001d8f2  mov     dword ptr [rax+8], 0
0x18001d8f9  mov     rcx, [rcx]; psa
0x18001d8fc  lea     r8, [rax+8]; plLbound
0x18001d900  mov     edx, 1; nDim
0x18001d905  mov     dword ptr [rax+10h], 0
0x18001d90c  call    cs:__imp_SafeArrayGetLBound
0x18001d912  test    eax, eax
0x18001d914  jns     short loc_18001D91E
0x18001d916  mov     ecx, eax; int
0x18001d918  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d91e  mov     rcx, [rbx]; psa
0x18001d921  lea     r8, [rsp+28h+plUbound]; plUbound
0x18001d926  mov     edx, 1; nDim
0x18001d92b  call    cs:__imp_SafeArrayGetUBound
0x18001d931  test    eax, eax
0x18001d933  jns     short loc_18001D93D
0x18001d935  mov     ecx, eax; int
0x18001d937  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001d93d  mov     eax, [rsp+28h+plUbound]
0x18001d941  sub     eax, [rsp+28h+arg_0]
0x18001d945  inc     eax
0x18001d947  add     rsp, 20h
0x18001d94b  pop     rbx
0x18001d94c  retn
```
