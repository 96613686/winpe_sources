# CVariantVector<uchar>::CVariantVector<uchar>(tagVARIANT *)

- ea: `0x1800273d0`
- end: `0x1800274d6`
- name: `??0?$CVariantVector@E@@QEAA@PEAUtagVARIANT@@@Z`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800276b0`

## callees

- `0x180001f0c`
- `0x18000c808`
- `0x1800273d0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800273f5`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800273f5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180027439`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180027439`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18002741b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x18002741b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002748b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002748b`

## pseudocode

```c
__int64 __fastcall CVariantVector<unsigned char>::CVariantVector<unsigned char>(__int64 a1, __int64 a2)
{
  SAFEARRAY *v3; // rcx
  SAFEARRAY *v4; // rcx
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  bool v7; // sf
  HRESULT v8; // eax
  void **pExceptionObject; // [rsp+20h] [rbp-20h] BYREF
  int v11; // [rsp+28h] [rbp-18h]
  __int128 v12; // [rsp+30h] [rbp-10h]
  LONG plUbound; // [rsp+50h] [rbp+10h] BYREF
  LONG plLbound; // [rsp+58h] [rbp+18h] BYREF

  v3 = *(SAFEARRAY **)(a2 + 8);
  *(_QWORD *)a1 = v3;
  if ( *(_WORD *)a2 != 8209 || SafeArrayGetDim(v3) != 1 )
  {
    v11 = -2147352571;
    pExceptionObject = &_w32_error::`vftable';
    v12 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  v4 = *(SAFEARRAY **)a1;
  plLbound = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(v4, 1u, &plLbound);
  if ( LBound < 0 )
    _com_issue_error(LBound);
  UBound = SafeArrayGetUBound(*(SAFEARRAY **)a1, 1u, &plUbound);
  if ( UBound < 0 )
    _com_issue_error(UBound);
  v7 = plUbound - plLbound + 1 < 0;
  *(_DWORD *)(a1 + 8) = plUbound - plLbound + 1;
  if ( v7 )
  {
    v11 = -2147352565;
    pExceptionObject = &_w32_error::`vftable';
    v12 = 0;
    throw (_com_error *)&pExceptionObject;
  }
  v8 = SafeArrayAccessData(*(SAFEARRAY **)a1, (void **)(a1 + 16));
  if ( v8 < 0 )
    _com_issue_error(v8);
  return a1;
}

```

## disassembly

```asm
0x1800273d0  mov     [rsp-8+arg_10], rbx
0x1800273d5  push    rbp
0x1800273d6  mov     rbp, rsp
0x1800273d9  sub     rsp, 40h
0x1800273dd  mov     rbx, rcx
0x1800273e0  mov     eax, 2011h
0x1800273e5  mov     rcx, [rdx+8]; psa
0x1800273e9  mov     [rbx], rcx
0x1800273ec  cmp     [rdx], ax
0x1800273ef  jnz     loc_1800274AB
0x1800273f5  call    cs:__imp_SafeArrayGetDim
0x1800273fb  cmp     eax, 1
0x1800273fe  jnz     loc_1800274AB
0x180027404  mov     rcx, [rbx]; psa
0x180027407  lea     r8, [rbp+plLbound]; plLbound
0x18002740b  mov     edx, eax; nDim
0x18002740d  mov     [rbp+plLbound], 0
0x180027414  mov     [rbp+plUbound], 0
0x18002741b  call    cs:__imp_SafeArrayGetLBound
0x180027421  test    eax, eax
0x180027423  jns     short loc_18002742D
0x180027425  mov     ecx, eax; int
0x180027427  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002742d  mov     rcx, [rbx]; psa
0x180027430  lea     r8, [rbp+plUbound]; plUbound
0x180027434  mov     edx, 1; nDim
0x180027439  call    cs:__imp_SafeArrayGetUBound
0x18002743f  test    eax, eax
0x180027441  jns     short loc_18002744B
0x180027443  mov     ecx, eax; int
0x180027445  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002744b  mov     eax, [rbp+plUbound]
0x18002744e  sub     eax, [rbp+plLbound]
0x180027451  add     eax, 1
0x180027454  mov     [rbx+8], eax
0x180027457  jns     short loc_180027484
0x180027459  lea     rax, ??_7_w32_error@@6B@; const _w32_error::`vftable'
0x180027460  mov     [rbp+var_18], 8002000Bh
0x180027467  xorps   xmm0, xmm0
0x18002746a  mov     [rbp+pExceptionObject], rax
0x18002746e  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180027475  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180027479  movdqu  [rbp+var_10], xmm0
0x18002747e  call    _CxxThrowException_0
0x180027484  mov     rcx, [rbx]; psa
0x180027487  lea     rdx, [rbx+10h]; ppvData
0x18002748b  call    cs:__imp_SafeArrayAccessData
0x180027491  test    eax, eax
0x180027493  jns     short loc_18002749D
0x180027495  mov     ecx, eax; int
0x180027497  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18002749d  mov     rax, rbx
0x1800274a0  mov     rbx, [rsp+40h+arg_10]
0x1800274a5  add     rsp, 40h
0x1800274a9  pop     rbp
0x1800274aa  retn
0x1800274ab  lea     rax, ??_7_w32_error@@6B@; const _w32_error::`vftable'
0x1800274b2  mov     [rbp+var_18], 80020005h
0x1800274b9  xorps   xmm0, xmm0
0x1800274bc  mov     [rbp+pExceptionObject], rax
0x1800274c0  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x1800274c7  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800274cb  movdqu  [rbp+var_10], xmm0
0x1800274d0  call    _CxxThrowException_0
```
