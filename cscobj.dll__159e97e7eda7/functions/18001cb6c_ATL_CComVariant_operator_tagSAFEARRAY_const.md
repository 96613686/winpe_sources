# ATL::CComVariant::operator=(tagSAFEARRAY const *)

- ea: `0x18001cb6c`
- end: `0x18001cbe7`
- name: `??4CComVariant@ATL@@QEAAAEAV01@PEBUtagSAFEARRAY@@@Z`
- size: `123`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct tagSAFEARRAY *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001dc18`
- `0x18001ef70`
- `0x1800281bc`

## callees

- `0x18001886c`
- `0x18001cb6c`
- `0x18001cfa0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001cb7c`
- `OLEAUT32!__imp_VariantClear` at `0x18001cb7c`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001cb98`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x18001cb98`

## pseudocode

```c
VARIANTARG *__fastcall ATL::CComVariant::operator=(VARIANTARG *a1, struct tagSAFEARRAY *a2)
{
  HRESULT v4; // eax
  SAFEARRAY *ppsaOut; // [rsp+38h] [rbp+10h] BYREF

  VariantClear(a1);
  ppsaOut = 0;
  if ( a2 )
  {
    v4 = SafeArrayCopy(a2, &ppsaOut);
    if ( v4 < 0 || !ppsaOut )
    {
      a1->vt = 10;
      a1->lVal = v4;
      ATL::AtlThrowImpl(-2147024882);
    }
    ATL::AtlSafeArrayGetActualVartype(a2, &a1->vt);
    a1->vt |= 0x2000u;
    a1->llVal = (LONGLONG)ppsaOut;
  }
  return a1;
}

```

## disassembly

```asm
0x18001cb6c  mov     [rsp+arg_0], rbx
0x18001cb71  push    rdi
0x18001cb72  sub     rsp, 20h
0x18001cb76  mov     rdi, rdx
0x18001cb79  mov     rbx, rcx
0x18001cb7c  call    cs:__imp_VariantClear
0x18001cb82  mov     [rsp+28h+ppsaOut], 0
0x18001cb8b  test    rdi, rdi
0x18001cb8e  jz      short loc_18001CBC6
0x18001cb90  lea     rdx, [rsp+28h+ppsaOut]; ppsaOut
0x18001cb95  mov     rcx, rdi; psa
0x18001cb98  call    cs:__imp_SafeArrayCopy
0x18001cb9e  test    eax, eax
0x18001cba0  js      short loc_18001CBD4
0x18001cba2  cmp     [rsp+28h+ppsaOut], 0
0x18001cba8  jz      short loc_18001CBD4
0x18001cbaa  mov     rdx, rbx; unsigned __int16 *
0x18001cbad  mov     rcx, rdi; struct tagSAFEARRAY *
0x18001cbb0  call    ?AtlSafeArrayGetActualVartype@ATL@@YAJPEAUtagSAFEARRAY@@PEAG@Z; ATL::AtlSafeArrayGetActualVartype(tagSAFEARRAY *,ushort *)
0x18001cbb5  mov     eax, 2000h
0x18001cbba  or      [rbx], ax
0x18001cbbd  mov     rax, [rsp+28h+ppsaOut]
0x18001cbc2  mov     [rbx+8], rax
0x18001cbc6  mov     rax, rbx
0x18001cbc9  mov     rbx, [rsp+28h+arg_0]
0x18001cbce  add     rsp, 20h
0x18001cbd2  pop     rdi
0x18001cbd3  retn
0x18001cbd4  mov     ecx, 8007000Eh; int
0x18001cbd9  mov     word ptr [rbx], 0Ah
0x18001cbde  mov     [rbx+8], eax
0x18001cbe1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
