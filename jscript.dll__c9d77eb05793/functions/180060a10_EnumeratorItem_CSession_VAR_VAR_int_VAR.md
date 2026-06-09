# EnumeratorItem(CSession *,VAR *,VAR *,int,VAR *)

- ea: `0x180060a10`
- end: `0x180060ab1`
- name: `?EnumeratorItem@@YAJPEAVCSession@@PEAVVAR@@1H1@Z`
- size: `161`
- prototype: `__int64 __fastcall(struct CSession *, struct VAR *, struct VAR *, int, struct VAR *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000d670`
- `0x18004ad20`
- `0x180060a10`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180060a7e`
- `OLEAUT32!__imp_VariantCopy` at `0x180060a7e`

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
0x180060a10  mov     [rsp+arg_0], rbx
0x180060a15  push    rdi
0x180060a16  sub     rsp, 40h
0x180060a1a  mov     rax, rdx
0x180060a1d  mov     [rsp+48h+var_28], 0
0x180060a26  mov     rbx, rcx
0x180060a29  lea     rdx, [rsp+48h+var_28]; struct EnumeratorObj **
0x180060a2e  mov     rcx, rax; struct VAR *
0x180060a31  mov     rdi, r8
0x180060a34  call    ?IsEnumerator@@YAHPEAVVAR@@PEAPEAVEnumeratorObj@@@Z; IsEnumerator(VAR *,EnumeratorObj * *)
0x180060a39  test    eax, eax
0x180060a3b  jnz     short loc_180060A44
0x180060a3d  mov     eax, 800A1397h
0x180060a42  jmp     short loc_180060AA6
0x180060a44  mov     rcx, rbx; struct CSession *
0x180060a47  call    ?PvarAlloc@@YAPEAVVAR@@PEAVCSession@@@Z; PvarAlloc(CSession *)
0x180060a4c  mov     rbx, rax
0x180060a4f  test    rax, rax
0x180060a52  jnz     short loc_180060A5B
0x180060a54  mov     eax, 8007000Eh
0x180060a59  jmp     short loc_180060AA6
0x180060a5b  mov     rdx, [rsp+48h+var_28]
0x180060a60  xor     eax, eax
0x180060a62  mov     word ptr [rsp+48h+pvargDest], ax
0x180060a67  cmp     [rdx+68h], rax
0x180060a6b  jz      short loc_180060A88
0x180060a6d  cmp     [rdx+88h], eax
0x180060a73  jz      short loc_180060A88
0x180060a75  add     rdx, 70h ; 'p'; pvargSrc
0x180060a79  lea     rcx, [rsp+48h+pvargDest]; pvargDest
0x180060a7e  call    cs:__imp_VariantCopy
0x180060a84  test    eax, eax
0x180060a86  js      short loc_180060AA6
0x180060a88  movups  xmm0, xmmword ptr [rsp+48h+pvargDest]
0x180060a8d  xor     eax, eax
0x180060a8f  movups  xmmword ptr [rbx], xmm0
0x180060a92  movsd   xmm1, qword ptr [rsp+48h+pvargDest+10h]
0x180060a98  movsd   qword ptr [rbx+10h], xmm1
0x180060a9d  mov     word ptr [rdi], 80h
0x180060aa2  mov     [rdi+8], rbx
0x180060aa6  mov     rbx, [rsp+48h+arg_0]
0x180060aab  add     rsp, 40h
0x180060aaf  pop     rdi
0x180060ab0  retn
```
