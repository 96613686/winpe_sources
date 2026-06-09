# VariantToPropVariant

- ea: `0x180033e40`
- end: `0x180033f02`
- name: `VariantToPropVariant`
- size: `194`
- prototype: `HRESULT __stdcall(const VARIANT *pVar, PROPVARIANT *pPropVar)`
- caller_count: `16`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b560`
- `0x180032920`
- `0x180032a30`
- `0x180033210`
- `0x180033634`
- `0x180033a20`
- `0x180033ac0`
- `0x180033e40`
- `0x180034d80`
- `0x180034e90`
- `0x180059940`
- `0x18007f670`
- `0x180096ee0`
- `0x1800970e0`
- `0x180097320`
- `0x180097890`

## callees

- `0x180033e40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033ef2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033ef2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033ec6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033ec6`
- `OLEAUT32!__imp_VariantCopy` at `0x180033ea0`
- `OLEAUT32!__imp_VariantCopy` at `0x180033ea0`

## pseudocode

```c
HRESULT __stdcall VariantToPropVariant(const VARIANT *pVar, PROPVARIANT *pPropVar)
{
  int v4; // esi
  void *v6; // rax

  if ( !pVar || !pPropVar )
    return -2147024809;
  *(_OWORD *)pPropVar = 0;
  pPropVar[2] = 0;
  v4 = -2147316576;
  if ( (pVar->vt & 0x6000) != 0x6000 && pVar->vt != 16391 && pVar->vt != 16392 )
  {
    if ( pVar->vt == 16396 )
    {
      v6 = CoTaskMemAlloc(0x18u);
      pPropVar[1] = v6;
      if ( v6 )
      {
        v4 = VariantToPropVariant(pVar->pvarVal, (PROPVARIANT *)v6);
        if ( v4 < 0 )
        {
          CoTaskMemFree(pPropVar[1]);
          pPropVar[1] = 0;
        }
        else
        {
          *(_WORD *)pPropVar = 16396;
        }
      }
    }
    else if ( pVar->vt != 16397 )
    {
      return VariantCopy((VARIANTARG *)pPropVar, pVar);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180033e40  mov     [rsp+arg_0], rbx
0x180033e45  mov     [rsp+arg_8], rsi
0x180033e4a  push    rdi
0x180033e4b  sub     rsp, 20h
0x180033e4f  mov     rbx, rdx
0x180033e52  mov     rdi, rcx
0x180033e55  test    rcx, rcx
0x180033e58  jz      short loc_180033EBA
0x180033e5a  test    rdx, rdx
0x180033e5d  jz      short loc_180033EBA
0x180033e5f  xor     eax, eax
0x180033e61  xorps   xmm0, xmm0
0x180033e64  movups  xmmword ptr [rdx], xmm0
0x180033e67  mov     [rdx+10h], rax
0x180033e6b  mov     esi, 80028CA0h
0x180033e70  movzx   eax, word ptr [rcx]
0x180033e73  mov     ecx, 6000h
0x180033e78  and     ax, cx
0x180033e7b  cmp     cx, ax
0x180033e7e  jz      short loc_180033EA8
0x180033e80  movzx   ecx, word ptr [rdi]
0x180033e83  sub     ecx, 4007h
0x180033e89  jz      short loc_180033EA8
0x180033e8b  sub     ecx, 1
0x180033e8e  jz      short loc_180033EA8
0x180033e90  sub     ecx, 4
0x180033e93  jz      short loc_180033EC1
0x180033e95  cmp     ecx, 1
0x180033e98  jz      short loc_180033EA8
0x180033e9a  mov     rdx, rdi; pvargSrc
0x180033e9d  mov     rcx, rbx; pvargDest
0x180033ea0  call    cs:__imp_VariantCopy
0x180033ea6  mov     esi, eax
0x180033ea8  mov     eax, esi
0x180033eaa  mov     rbx, [rsp+28h+arg_0]
0x180033eaf  mov     rsi, [rsp+28h+arg_8]
0x180033eb4  add     rsp, 20h
0x180033eb8  pop     rdi
0x180033eb9  retn
0x180033eba  mov     eax, 80070057h
0x180033ebf  jmp     short loc_180033EAA
0x180033ec1  mov     ecx, 18h; cb
0x180033ec6  call    cs:__imp_CoTaskMemAlloc
0x180033ecc  mov     [rbx+8], rax
0x180033ed0  test    rax, rax
0x180033ed3  jz      short loc_180033EA8
0x180033ed5  mov     rcx, [rdi+8]; pVar
0x180033ed9  mov     rdx, rax; pPropVar
0x180033edc  call    VariantToPropVariant
0x180033ee1  mov     esi, eax
0x180033ee3  test    eax, eax
0x180033ee5  js      short loc_180033EEE
0x180033ee7  mov     word ptr [rbx], 400Ch
0x180033eec  jmp     short loc_180033EA8
0x180033eee  mov     rcx, [rbx+8]; pv
0x180033ef2  call    cs:__imp_CoTaskMemFree
0x180033ef8  mov     qword ptr [rbx+8], 0
0x180033f00  jmp     short loc_180033EA8
```
