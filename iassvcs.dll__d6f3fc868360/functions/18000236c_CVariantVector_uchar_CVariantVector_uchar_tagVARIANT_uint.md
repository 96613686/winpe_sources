# CVariantVector<uchar>::CVariantVector<uchar>(tagVARIANT *,uint)

- ea: `0x18000236c`
- end: `0x18000241f`
- name: `??0?$CVariantVector@E@@QEAA@PEAUtagVARIANT@@I@Z`
- size: `179`
- prototype: `__int64 __fastcall(__int64, VARIANTARG *, ULONG)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ce90`

## callees

- `0x180001e0e`
- `0x18000236c`
- `0x180002500`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000238a`
- `OLEAUT32!__imp_VariantInit` at `0x18000238a`
- `OLEAUT32!__imp_VariantClear` at `0x1800023fb`
- `OLEAUT32!__imp_VariantClear` at `0x1800023fb`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800023b8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800023b8`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000239a`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18000239a`

## pseudocode

```c
__int64 __fastcall CVariantVector<unsigned char>::CVariantVector<unsigned char>(__int64 a1, VARIANTARG *a2, ULONG a3)
{
  SAFEARRAY *Vector; // rax
  struct IErrorInfo *v7; // r8
  bool v8; // r9
  HRESULT v9; // ebx
  struct IErrorInfo *v11; // r8
  bool v12; // r9
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  *(_DWORD *)(a1 + 8) = a3;
  VariantInit(a2);
  Vector = SafeArrayCreateVector(0x11u, 0, a3);
  a2->llVal = (LONGLONG)Vector;
  *(_QWORD *)a1 = Vector;
  if ( !Vector )
  {
    _com_error::_com_error((_com_error *)pExceptionObject, -2147024882, v7, v8);
    throw (_com_error *)pExceptionObject;
  }
  a2->vt = 8209;
  v9 = SafeArrayAccessData(*(SAFEARRAY **)a1, (void **)(a1 + 16));
  if ( v9 < 0 )
  {
    VariantClear(a2);
    _com_error::_com_error((_com_error *)pExceptionObject, v9, v11, v12);
    throw (_com_error *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x18000236c  mov     [rsp+arg_0], rbx
0x180002371  mov     [rsp+arg_8], rsi
0x180002376  push    rdi
0x180002377  sub     rsp, 40h
0x18000237b  mov     ebx, r8d
0x18000237e  mov     rdi, rcx
0x180002381  mov     [rcx+8], ebx
0x180002384  mov     rsi, rdx
0x180002387  mov     rcx, rdx; pvarg
0x18000238a  call    cs:__imp_VariantInit
0x180002390  mov     ecx, 11h; vt
0x180002395  mov     r8d, ebx; cElements
0x180002398  xor     edx, edx; lLbound
0x18000239a  call    cs:__imp_SafeArrayCreateVector
0x1800023a0  mov     [rsi+8], rax
0x1800023a4  mov     [rdi], rax
0x1800023a7  test    rax, rax
0x1800023aa  jz      short loc_1800023D7
0x1800023ac  mov     word ptr [rsi], 2011h
0x1800023b1  lea     rdx, [rdi+10h]; ppvData
0x1800023b5  mov     rcx, [rdi]; psa
0x1800023b8  call    cs:__imp_SafeArrayAccessData
0x1800023be  mov     ebx, eax
0x1800023c0  test    eax, eax
0x1800023c2  js      short loc_1800023F8
0x1800023c4  mov     rbx, [rsp+48h+arg_0]
0x1800023c9  mov     rax, rdi
0x1800023cc  mov     rsi, [rsp+48h+arg_8]
0x1800023d1  add     rsp, 40h
0x1800023d5  pop     rdi
0x1800023d6  retn
0x1800023d7  mov     edx, 8007000Eh; int
0x1800023dc  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800023e1  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x1800023e6  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x1800023ed  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800023f2  call    _CxxThrowException_0
0x1800023f8  mov     rcx, rsi; pvarg
0x1800023fb  call    cs:__imp_VariantClear
0x180002401  mov     edx, ebx; int
0x180002403  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002408  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x18000240d  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180002414  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002419  call    _CxxThrowException_0
```
