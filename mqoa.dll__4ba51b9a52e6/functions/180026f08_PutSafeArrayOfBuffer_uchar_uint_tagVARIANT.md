# PutSafeArrayOfBuffer(uchar *,uint,tagVARIANT *)

- ea: `0x180026f08`
- end: `0x180026fb6`
- name: `?PutSafeArrayOfBuffer@@YAJPEAEIPEAUtagVARIANT@@@Z`
- size: `174`
- prototype: `__int64 __fastcall(unsigned __int8 *, ULONG, struct tagVARIANT *)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800181f0`
- `0x1800182d0`
- `0x1800184a0`
- `0x180018570`
- `0x180018640`
- `0x180018ed0`
- `0x180018f50`
- `0x1800190d0`
- `0x1800192e0`

## callees

- `0x180026f08`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x180026f24`
- `OLEAUT32!__imp_VariantClear` at `0x180026f24`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180026f44`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180026f44`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180026f8c`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180026f8c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180026f79`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180026f79`

## pseudocode

```c
__int64 __fastcall PutSafeArrayOfBuffer(unsigned __int8 *a1, ULONG a2, struct tagVARIANT *a3)
{
  SAFEARRAY *v6; // rsi
  HRESULT v8; // ebx
  unsigned int i; // edi
  HRESULT v10; // eax
  LONG rgIndices; // [rsp+58h] [rbp+10h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+68h] [rbp+20h] BYREF

  VariantClear(a3);
  rgsabound.lLbound = 0;
  rgsabound.cElements = a2;
  v6 = SafeArrayCreate(0x11u, 1u, &rgsabound);
  if ( !v6 )
    return 2147942414LL;
  v8 = 0;
  if ( a1 )
  {
    for ( i = 0; i < a2; ++i )
    {
      rgIndices = i;
      v8 = SafeArrayPutElement(v6, &rgIndices, &a1[i]);
      if ( v8 < 0 )
      {
        v10 = SafeArrayDestroy(v6);
        if ( v10 < 0 )
          return (unsigned int)v10;
        return (unsigned int)v8;
      }
    }
  }
  a3->vt = 8209;
  a3->llVal = (LONGLONG)v6;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180026f08  mov     [rsp+arg_0], rbx
0x180026f0d  push    rbp
0x180026f0e  push    rsi
0x180026f0f  push    rdi
0x180026f10  push    r14
0x180026f12  push    r15
0x180026f14  sub     rsp, 20h
0x180026f18  mov     rbp, rcx
0x180026f1b  mov     r14, r8
0x180026f1e  mov     rcx, r8; pvarg
0x180026f21  mov     r15d, edx
0x180026f24  call    cs:__imp_VariantClear
0x180026f2a  mov     ecx, 11h; vt
0x180026f2f  mov     [rsp+48h+rgsabound.lLbound], 0
0x180026f37  lea     r8, [rsp+48h+rgsabound]; rgsabound
0x180026f3c  mov     [rsp+48h+rgsabound.cElements], r15d
0x180026f41  lea     edx, [rcx-10h]; cDims
0x180026f44  call    cs:__imp_SafeArrayCreate
0x180026f4a  mov     rsi, rax
0x180026f4d  test    rax, rax
0x180026f50  jnz     short loc_180026F59
0x180026f52  mov     eax, 8007000Eh
0x180026f57  jmp     short loc_180026FA5
0x180026f59  xor     ebx, ebx
0x180026f5b  test    rbp, rbp
0x180026f5e  jz      short loc_180026F99
0x180026f60  xor     edi, edi
0x180026f62  cmp     edi, r15d
0x180026f65  jnb     short loc_180026F99
0x180026f67  mov     r8d, edi
0x180026f6a  lea     rdx, [rsp+48h+rgIndices]; rgIndices
0x180026f6f  add     r8, rbp; pv
0x180026f72  mov     [rsp+48h+rgIndices], edi
0x180026f76  mov     rcx, rsi; psa
0x180026f79  call    cs:__imp_SafeArrayPutElement
0x180026f7f  mov     ebx, eax
0x180026f81  test    eax, eax
0x180026f83  js      short loc_180026F89
0x180026f85  inc     edi
0x180026f87  jmp     short loc_180026F62
0x180026f89  mov     rcx, rsi; psa
0x180026f8c  call    cs:__imp_SafeArrayDestroy
0x180026f92  test    eax, eax
0x180026f94  cmovs   ebx, eax
0x180026f97  jmp     short loc_180026FA3
0x180026f99  mov     word ptr [r14], 2011h
0x180026f9f  mov     [r14+8], rsi
0x180026fa3  mov     eax, ebx
0x180026fa5  mov     rbx, [rsp+48h+arg_0]
0x180026faa  add     rsp, 20h
0x180026fae  pop     r15
0x180026fb0  pop     r14
0x180026fb2  pop     rdi
0x180026fb3  pop     rsi
0x180026fb4  pop     rbp
0x180026fb5  retn
```
