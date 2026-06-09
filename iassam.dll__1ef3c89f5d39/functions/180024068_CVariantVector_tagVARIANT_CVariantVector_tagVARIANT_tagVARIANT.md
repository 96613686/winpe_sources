# CVariantVector<tagVARIANT>::CVariantVector<tagVARIANT>(tagVARIANT *)

- ea: `0x180024068`
- end: `0x18002416e`
- name: `??0?$CVariantVector@UtagVARIANT@@@@QEAA@PEAUtagVARIANT@@@Z`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800241e0`

## callees

- `0x180001f0c`
- `0x18000c808`
- `0x180024068`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002408d`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002408d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800240d1`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800240d1`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800240b3`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800240b3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180024123`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180024123`

## pseudocode

```c
__int64 __fastcall CVariantVector<tagVARIANT>::CVariantVector<tagVARIANT>(__int64 a1, __int64 a2)
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
  if ( *(_WORD *)a2 != 8204 || SafeArrayGetDim(v3) != 1 )
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
0x180024068  mov     [rsp-8+arg_10], rbx
0x18002406d  push    rbp
0x18002406e  mov     rbp, rsp
0x180024071  sub     rsp, 40h
0x180024075  mov     rbx, rcx
0x180024078  mov     eax, 200Ch
0x18002407d  mov     rcx, [rdx+8]; psa
0x180024081  mov     [rbx], rcx
0x180024084  cmp     [rdx], ax
0x180024087  jnz     loc_180024143
0x18002408d  call    cs:__imp_SafeArrayGetDim
0x180024093  cmp     eax, 1
0x180024096  jnz     loc_180024143
0x18002409c  mov     rcx, [rbx]; psa
0x18002409f  lea     r8, [rbp+plLbound]; plLbound
0x1800240a3  mov     edx, eax; nDim
0x1800240a5  mov     [rbp+plLbound], 0
0x1800240ac  mov     [rbp+plUbound], 0
0x1800240b3  call    cs:__imp_SafeArrayGetLBound
0x1800240b9  test    eax, eax
0x1800240bb  jns     short loc_1800240C5
0x1800240bd  mov     ecx, eax; int
0x1800240bf  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800240c5  mov     rcx, [rbx]; psa
0x1800240c8  lea     r8, [rbp+plUbound]; plUbound
0x1800240cc  mov     edx, 1; nDim
0x1800240d1  call    cs:__imp_SafeArrayGetUBound
0x1800240d7  test    eax, eax
0x1800240d9  jns     short loc_1800240E3
0x1800240db  mov     ecx, eax; int
0x1800240dd  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x1800240e3  mov     eax, [rbp+plUbound]
0x1800240e6  sub     eax, [rbp+plLbound]
0x1800240e9  add     eax, 1
0x1800240ec  mov     [rbx+8], eax
0x1800240ef  jns     short loc_18002411C
0x1800240f1  lea     rax, ??_7_w32_error@@6B@; const _w32_error::`vftable'
0x1800240f8  mov     [rbp+var_18], 8002000Bh
0x1800240ff  xorps   xmm0, xmm0
0x180024102  mov     [rbp+pExceptionObject], rax
0x180024106  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18002410d  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024111  movdqu  [rbp+var_10], xmm0
0x180024116  call    _CxxThrowException_0
0x18002411c  mov     rcx, [rbx]; psa
0x18002411f  lea     rdx, [rbx+10h]; ppvData
0x180024123  call    cs:__imp_SafeArrayAccessData
0x180024129  test    eax, eax
0x18002412b  jns     short loc_180024135
0x18002412d  mov     ecx, eax; int
0x18002412f  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180024135  mov     rax, rbx
0x180024138  mov     rbx, [rsp+40h+arg_10]
0x18002413d  add     rsp, 40h
0x180024141  pop     rbp
0x180024142  retn
0x180024143  lea     rax, ??_7_w32_error@@6B@; const _w32_error::`vftable'
0x18002414a  mov     [rbp+var_18], 80020005h
0x180024151  xorps   xmm0, xmm0
0x180024154  mov     [rbp+pExceptionObject], rax
0x180024158  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18002415f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180024163  movdqu  [rbp+var_10], xmm0
0x180024168  call    _CxxThrowException_0
```
