# IASLoadVariantFromString

- ea: `0x18000a340`
- end: `0x18000a4a1`
- name: `IASLoadVariantFromString`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a5a0`

## callees

- `0x18000a340`
- `0x18000a654`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000a38c`
- `OLEAUT32!__imp_VariantInit` at `0x18000a38c`
- `OLEAUT32!__imp_VariantClear` at `0x18000a3e1`
- `OLEAUT32!__imp_VariantClear` at `0x18000a481`
- `OLEAUT32!__imp_VariantClear` at `0x18000a3e1`
- `OLEAUT32!__imp_VariantClear` at `0x18000a481`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000a3d0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000a3d0`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18000a472`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18000a472`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x18000a403`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x18000a434`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x18000a403`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x18000a434`

## pseudocode

```c
__int64 __fastcall IASLoadVariantFromString(__int64 a1, unsigned int a2, VARIANTARG *a3)
{
  __int64 v3; // rsi
  __int64 v6; // r15
  __int64 result; // rax
  __int64 v8; // rsi
  SAFEARRAY *v9; // rax
  SAFEARRAY *v10; // r14
  _QWORD *v11; // rax
  HRESULT v12; // edi
  SAFEARRAYBOUND rgsabound; // [rsp+20h] [rbp-10h] BYREF
  void *ppvData; // [rsp+28h] [rbp-8h] BYREF
  __int64 v15; // [rsp+60h] [rbp+30h] BYREF
  LONG rgIndices; // [rsp+78h] [rbp+48h] BYREF

  v15 = a1;
  v3 = a2;
  rgsabound = 0;
  rgIndices = 0;
  ppvData = 0;
  if ( !a1 || !a3 )
    return 2147500035LL;
  VariantInit(a3);
  v6 = a1 + 2 * v3;
  result = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))LoadSingleVariantFromString)(
             a1,
             (unsigned int)v3,
             a3,
             &v15,
             rgsabound);
  if ( (int)result >= 0 )
  {
    v8 = v15;
    if ( v15 != v6 )
    {
      rgsabound = (SAFEARRAYBOUND)2LL;
      v9 = SafeArrayCreate(0xCu, 1u, &rgsabound);
      v10 = v9;
      if ( v9 )
      {
        rgIndices = 0;
        SafeArrayPtrOfIndex(v9, &rgIndices, &ppvData);
        v11 = ppvData;
        *(_OWORD *)ppvData = *(_OWORD *)&a3->vt;
        v11[2] = a3->pRecInfo;
        a3->vt = 8204;
        a3->llVal = (LONGLONG)v10;
        do
        {
          ++rgIndices;
          v12 = SafeArrayPtrOfIndex(v10, &rgIndices, &ppvData);
          if ( v12 < 0 )
            break;
          v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))LoadSingleVariantFromString)(
                  v8,
                  (v6 - v8) >> 1,
                  ppvData,
                  &v15,
                  rgsabound);
          if ( v12 < 0 )
            break;
          v8 = v15;
          if ( v15 == v6 )
            return (unsigned int)v12;
          ++rgsabound.cElements;
          v12 = SafeArrayRedim(v10, &rgsabound);
        }
        while ( v12 >= 0 );
        VariantClear(a3);
        return (unsigned int)v12;
      }
      else
      {
        VariantClear(a3);
        return 2147942414LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a340  mov     [rsp-28h+arg_8], rbx
0x18000a345  mov     [rsp-28h+arg_0], rcx
0x18000a34a  push    rbp
0x18000a34b  push    rsi
0x18000a34c  push    rdi
0x18000a34d  push    r14
0x18000a34f  push    r15
0x18000a351  mov     rbp, rsp
0x18000a354  sub     rsp, 30h
0x18000a358  mov     esi, edx
0x18000a35a  mov     rbx, r8
0x18000a35d  mov     qword ptr [rbp+rgsabound.cElements], 0
0x18000a365  mov     rdi, rcx
0x18000a368  mov     [rbp+rgIndices], 0
0x18000a36f  mov     [rbp+ppvData], 0
0x18000a377  test    rcx, rcx
0x18000a37a  jz      loc_18000A48B
0x18000a380  test    rbx, rbx
0x18000a383  jz      loc_18000A48B
0x18000a389  mov     rcx, rbx; pvarg
0x18000a38c  call    cs:__imp_VariantInit
0x18000a392  lea     r9, [rbp+arg_0]
0x18000a396  mov     r8, rbx
0x18000a399  mov     edx, esi
0x18000a39b  lea     r15, [rdi+rsi*2]
0x18000a39f  mov     rcx, rdi
0x18000a3a2  call    LoadSingleVariantFromString
0x18000a3a7  test    eax, eax
0x18000a3a9  js      loc_18000A490
0x18000a3af  mov     rsi, [rbp+arg_0]
0x18000a3b3  cmp     rsi, r15
0x18000a3b6  jz      loc_18000A490
0x18000a3bc  mov     ecx, 0Ch; vt
0x18000a3c1  mov     qword ptr [rbp+rgsabound.cElements], 2
0x18000a3c9  lea     r8, [rbp+rgsabound]; rgsabound
0x18000a3cd  lea     edx, [rcx-0Bh]; cDims
0x18000a3d0  call    cs:__imp_SafeArrayCreate
0x18000a3d6  mov     r14, rax
0x18000a3d9  test    rax, rax
0x18000a3dc  jnz     short loc_18000A3F1
0x18000a3de  mov     rcx, rbx; pvarg
0x18000a3e1  call    cs:__imp_VariantClear
0x18000a3e7  mov     eax, 8007000Eh
0x18000a3ec  jmp     loc_18000A490
0x18000a3f1  lea     r8, [rbp+ppvData]; ppvData
0x18000a3f5  mov     [rbp+rgIndices], 0
0x18000a3fc  lea     rdx, [rbp+rgIndices]; rgIndices
0x18000a400  mov     rcx, r14; psa
0x18000a403  call    cs:__imp_SafeArrayPtrOfIndex
0x18000a409  movups  xmm0, xmmword ptr [rbx]
0x18000a40c  mov     rax, [rbp+ppvData]
0x18000a410  movups  xmmword ptr [rax], xmm0
0x18000a413  movsd   xmm1, qword ptr [rbx+10h]
0x18000a418  movsd   qword ptr [rax+10h], xmm1
0x18000a41d  mov     word ptr [rbx], 200Ch
0x18000a422  mov     [rbx+8], r14
0x18000a426  inc     [rbp+rgIndices]
0x18000a429  lea     r8, [rbp+ppvData]; ppvData
0x18000a42d  lea     rdx, [rbp+rgIndices]; rgIndices
0x18000a431  mov     rcx, r14; psa
0x18000a434  call    cs:__imp_SafeArrayPtrOfIndex
0x18000a43a  mov     edi, eax
0x18000a43c  test    eax, eax
0x18000a43e  js      short loc_18000A47E
0x18000a440  mov     r8, [rbp+ppvData]
0x18000a444  lea     r9, [rbp+arg_0]
0x18000a448  mov     rdx, r15
0x18000a44b  mov     rcx, rsi
0x18000a44e  sub     rdx, rsi
0x18000a451  sar     rdx, 1
0x18000a454  call    LoadSingleVariantFromString
0x18000a459  mov     edi, eax
0x18000a45b  test    eax, eax
0x18000a45d  js      short loc_18000A47E
0x18000a45f  mov     rsi, [rbp+arg_0]
0x18000a463  cmp     rsi, r15
0x18000a466  jz      short loc_18000A487
0x18000a468  inc     [rbp+rgsabound.cElements]
0x18000a46b  lea     rdx, [rbp+rgsabound]; psaboundNew
0x18000a46f  mov     rcx, r14; psa
0x18000a472  call    cs:__imp_SafeArrayRedim
0x18000a478  mov     edi, eax
0x18000a47a  test    eax, eax
0x18000a47c  jns     short loc_18000A426
0x18000a47e  mov     rcx, rbx; pvarg
0x18000a481  call    cs:__imp_VariantClear
0x18000a487  mov     eax, edi
0x18000a489  jmp     short loc_18000A490
0x18000a48b  mov     eax, 80004003h
0x18000a490  mov     rbx, [rsp+30h+arg_8]
0x18000a495  add     rsp, 30h
0x18000a499  pop     r15
0x18000a49b  pop     r14
0x18000a49d  pop     rdi
0x18000a49e  pop     rsi
0x18000a49f  pop     rbp
0x18000a4a0  retn
```
