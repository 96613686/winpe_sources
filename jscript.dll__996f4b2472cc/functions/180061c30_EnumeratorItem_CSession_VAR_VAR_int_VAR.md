# EnumeratorItem(CSession *,VAR *,VAR *,int,VAR *)

- ea: `0x180061c30`
- end: `0x180061cd8`
- name: `?EnumeratorItem@@YAJPEAVCSession@@PEAVVAR@@1H1@Z`
- size: `168`
- prototype: `HRESULT __fastcall(struct CSession *, struct VAR *, struct VAR *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000a850`
- `0x18004b650`
- `0x180061c30`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180061c9e`
- `OLEAUT32!__imp_VariantCopy` at `0x180061c9e`

## pseudocode

```c
HRESULT __fastcall EnumeratorItem(struct CSession *a1, struct VAR *a2, struct VAR *a3)
{
  HRESULT result; // eax
  VARIANTARG *v6; // rbx
  struct EnumeratorObj *v7; // [rsp+20h] [rbp-28h] BYREF
  VARIANTARG pvargDest; // [rsp+28h] [rbp-20h] BYREF

  v7 = 0;
  if ( !(unsigned int)IsEnumerator(a2, &v7) )
    return -2146823273;
  v6 = (VARIANTARG *)PvarAlloc(a1);
  if ( !v6 )
    return -2147024882;
  pvargDest.vt = 0;
  if ( !*((_QWORD *)v7 + 13)
    || !*((_DWORD *)v7 + 34)
    || (result = VariantCopy(&pvargDest, (const VARIANTARG *)((char *)v7 + 112)), result >= 0) )
  {
    result = 0;
    *v6 = pvargDest;
    *(_WORD *)a3 = 128;
    *((_QWORD *)a3 + 1) = v6;
  }
  return result;
}

```

## disassembly

```asm
0x180061c30  mov     [rsp+arg_0], rbx
0x180061c35  push    rdi
0x180061c36  sub     rsp, 40h
0x180061c3a  mov     rax, rdx
0x180061c3d  mov     [rsp+48h+var_28], 0
0x180061c46  mov     rbx, rcx
0x180061c49  lea     rdx, [rsp+48h+var_28]; struct EnumeratorObj **
0x180061c4e  mov     rcx, rax; struct VAR *
0x180061c51  mov     rdi, r8
0x180061c54  call    ?IsEnumerator@@YAHPEAVVAR@@PEAPEAVEnumeratorObj@@@Z; IsEnumerator(VAR *,EnumeratorObj * *)
0x180061c59  test    eax, eax
0x180061c5b  jnz     short loc_180061C64
0x180061c5d  mov     eax, 800A1397h
0x180061c62  jmp     short loc_180061CCC
0x180061c64  mov     rcx, rbx; struct CSession *
0x180061c67  call    ?PvarAlloc@@YAPEAVVAR@@PEAVCSession@@@Z; PvarAlloc(CSession *)
0x180061c6c  mov     rbx, rax
0x180061c6f  test    rax, rax
0x180061c72  jnz     short loc_180061C7B
0x180061c74  mov     eax, 8007000Eh
0x180061c79  jmp     short loc_180061CCC
0x180061c7b  mov     rdx, [rsp+48h+var_28]
0x180061c80  xor     eax, eax
0x180061c82  mov     word ptr [rsp+48h+pvargDest], ax
0x180061c87  cmp     [rdx+68h], rax
0x180061c8b  jz      short loc_180061CAE
0x180061c8d  cmp     [rdx+88h], eax
0x180061c93  jz      short loc_180061CAE
0x180061c95  add     rdx, 70h ; 'p'; pvargSrc
0x180061c99  lea     rcx, [rsp+48h+pvargDest]; pvargDest
0x180061c9e  call    cs:__imp_VariantCopy
0x180061ca5  nop     dword ptr [rax+rax+00h]
0x180061caa  test    eax, eax
0x180061cac  js      short loc_180061CCC
0x180061cae  movups  xmm0, xmmword ptr [rsp+48h+pvargDest]
0x180061cb3  xor     eax, eax
0x180061cb5  movups  xmmword ptr [rbx], xmm0
0x180061cb8  movsd   xmm1, qword ptr [rsp+48h+pvargDest+10h]
0x180061cbe  movsd   qword ptr [rbx+10h], xmm1
0x180061cc3  mov     word ptr [rdi], 80h
0x180061cc8  mov     [rdi+8], rbx
0x180061ccc  mov     rbx, [rsp+48h+arg_0]
0x180061cd1  add     rsp, 40h
0x180061cd5  pop     rdi
0x180061cd6  retn
```
