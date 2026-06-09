# GetSafeArrayDataOfVariant(tagVARIANT *,uchar * *,ulong *)

- ea: `0x180026c48`
- end: `0x180026d00`
- name: `?GetSafeArrayDataOfVariant@@YAJPEAUtagVARIANT@@PEAPEAEPEAK@Z`
- size: `184`
- prototype: `HRESULT __fastcall(struct tagVARIANT *, unsigned __int8 **, unsigned int *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180019890`
- `0x1800199e0`
- `0x180019e20`
- `0x180019f20`
- `0x18001a090`
- `0x180026d08`

## callees

- `0x180026c48`
- `0x180026fbc`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180026cc3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180026cc3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180026cdd`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180026cdd`

## pseudocode

```c
HRESULT __fastcall GetSafeArrayDataOfVariant(struct tagVARIANT *a1, unsigned __int8 **a2, unsigned int *a3)
{
  HRESULT v5; // edi
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rbx
  SAFEARRAY *llVal; // rbx
  unsigned int v8; // esi
  HRESULT result; // eax
  void *ppvData; // [rsp+40h] [rbp+8h] BYREF

  ppvData = 0;
  *a2 = 0;
  if ( !a1 || (a1->vt & 0x2000) == 0 )
    return -2147024809;
  v5 = 0;
  p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a1->llVal;
  *a3 = 0;
  if ( (a1->vt & 0x4000) != 0 )
    p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)p_llVal->llVal;
  llVal = (SAFEARRAY *)p_llVal->llVal;
  if ( !llVal )
    return v5;
  v8 = SafeArraySize3(llVal->cDims, llVal->cbElements, llVal->rgsabound);
  if ( v8 == -1 )
    return -2147024882;
  result = SafeArrayAccessData(llVal, &ppvData);
  v5 = result;
  if ( result >= 0 )
  {
    *a2 = (unsigned __int8 *)ppvData;
    *a3 = v8;
    SafeArrayUnaccessData(llVal);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180026c48  mov     [rsp+arg_8], rbx
0x180026c4d  mov     [rsp+arg_10], rsi
0x180026c52  push    rdi
0x180026c53  push    r14
0x180026c55  push    r15
0x180026c57  sub     rsp, 20h
0x180026c5b  mov     [rsp+38h+ppvData], 0
0x180026c64  mov     r15, r8
0x180026c67  mov     qword ptr [rdx], 0
0x180026c6e  mov     r14, rdx
0x180026c71  test    rcx, rcx
0x180026c74  jz      short loc_180026CE7
0x180026c76  mov     eax, 2000h
0x180026c7b  test    [rcx], ax
0x180026c7e  jz      short loc_180026CE7
0x180026c80  xor     edi, edi
0x180026c82  lea     rbx, [rcx+8]
0x180026c86  mov     eax, 4000h
0x180026c8b  mov     [r8], edi
0x180026c8e  test    [rcx], ax
0x180026c91  jz      short loc_180026C96
0x180026c93  mov     rbx, [rbx]
0x180026c96  mov     rbx, [rbx]
0x180026c99  test    rbx, rbx
0x180026c9c  jz      short loc_180026CE3
0x180026c9e  mov     edx, [rbx+4]; unsigned int
0x180026ca1  lea     r8, [rbx+18h]; struct tagSAFEARRAYBOUND *
0x180026ca5  movzx   ecx, word ptr [rbx]; unsigned __int16
0x180026ca8  call    ?SafeArraySize3@@YAKGKPEAUtagSAFEARRAYBOUND@@@Z; SafeArraySize3(ushort,ulong,tagSAFEARRAYBOUND *)
0x180026cad  mov     esi, eax
0x180026caf  cmp     eax, 0FFFFFFFFh
0x180026cb2  jnz     short loc_180026CBB
0x180026cb4  mov     eax, 8007000Eh
0x180026cb9  jmp     short loc_180026CEC
0x180026cbb  lea     rdx, [rsp+38h+ppvData]; ppvData
0x180026cc0  mov     rcx, rbx; psa
0x180026cc3  call    cs:__imp_SafeArrayAccessData
0x180026cc9  mov     edi, eax
0x180026ccb  test    eax, eax
0x180026ccd  js      short loc_180026CEC
0x180026ccf  mov     rax, [rsp+38h+ppvData]
0x180026cd4  mov     rcx, rbx; psa
0x180026cd7  mov     [r14], rax
0x180026cda  mov     [r15], esi
0x180026cdd  call    cs:__imp_SafeArrayUnaccessData
0x180026ce3  mov     eax, edi
0x180026ce5  jmp     short loc_180026CEC
0x180026ce7  mov     eax, 80070057h
0x180026cec  mov     rbx, [rsp+38h+arg_8]
0x180026cf1  mov     rsi, [rsp+38h+arg_10]
0x180026cf6  add     rsp, 20h
0x180026cfa  pop     r15
0x180026cfc  pop     r14
0x180026cfe  pop     rdi
0x180026cff  retn
```
