# WriteVariantToStream

- ea: `0x18001d5b0`
- end: `0x18001d765`
- name: `WriteVariantToStream`
- size: `437`
- prototype: `__int64 __fastcall(VARIANTARG *pvarSrc, struct ISequentialStream *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18001cd50`
- `0x18001d3c0`
- `0x18001d5b0`
- `0x180024010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001d5e0`
- `OLEAUT32!__imp_VariantInit` at `0x18001d5e0`
- `OLEAUT32!__imp_VariantClear` at `0x18001d6e5`
- `OLEAUT32!__imp_VariantClear` at `0x18001d6e5`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001d74c`
- `OLEAUT32!__imp_VariantChangeType` at `0x18001d74c`

## pseudocode

```c
__int64 __fastcall WriteVariantToStream(VARIANTARG *pvarSrc, struct ISequentialStream *a2)
{
  HRESULT v4; // ebx
  unsigned int vt; // ecx
  unsigned int v6; // edi
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  VARTYPE v20; // ax
  LONGLONG llVal; // rcx
  HRESULT v22; // eax
  VARIANTARG pvarg; // [rsp+30h] [rbp-58h] BYREF
  int v24; // [rsp+90h] [rbp+8h] BYREF

  v24 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  if ( !pvarSrc || !a2 )
  {
    v4 = -2147467261;
    goto LABEL_31;
  }
  vt = pvarSrc->vt;
  v6 = 0;
  if ( vt > 0xB )
  {
    v14 = vt - 13;
    if ( !v14 )
      goto LABEL_30;
    v15 = v14 - 3;
    if ( !v15 || (v16 = v15 - 1) == 0 )
    {
      v6 = 1;
      goto LABEL_25;
    }
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( !v18 )
        goto LABEL_22;
      v13 = v18 - 3;
      if ( !v13 )
        goto LABEL_22;
      goto LABEL_13;
    }
LABEL_23:
    v6 = 2;
    goto LABEL_25;
  }
  if ( vt == 11 )
    goto LABEL_23;
  v7 = vt - 2;
  if ( !v7 )
    goto LABEL_23;
  v8 = v7 - 1;
  if ( !v8 )
    goto LABEL_22;
  v9 = v8 - 1;
  if ( !v9 )
    goto LABEL_22;
  v10 = v9 - 1;
  if ( !v10 || (v11 = v10 - 1) == 0 || (v12 = v11 - 1) == 0 )
  {
    v6 = 8;
    goto LABEL_25;
  }
  v13 = v12 - 2;
  if ( !v13 )
    goto LABEL_30;
LABEL_13:
  if ( v13 == 1 )
LABEL_22:
    v6 = 4;
LABEL_25:
  v4 = ((__int64 (__fastcall *)(struct ISequentialStream *, VARIANTARG *, __int64, int *))a2->lpVtbl->Write)(
         a2,
         pvarSrc,
         2,
         &v24);
  if ( v4 < 0 )
    goto LABEL_31;
  if ( v24 != 2 )
  {
LABEL_30:
    v4 = -2147467259;
    goto LABEL_31;
  }
  if ( !v6 )
  {
    v20 = pvarSrc->vt;
    if ( pvarSrc->vt == 8 )
    {
      llVal = pvarSrc->llVal;
    }
    else
    {
      if ( (v20 & 0x2000) != 0 )
      {
        v22 = WriteSafeArrayToStream(pvarSrc->parray, v20 & 0xDFFF, a2);
        goto LABEL_35;
      }
      if ( v20 == 1 )
        goto LABEL_31;
      v4 = VariantChangeType(&pvarg, pvarSrc, 1u, 8u);
      if ( v4 < 0 )
        goto LABEL_31;
      llVal = pvarg.llVal;
    }
    v22 = WriteBSTRToStream(llVal, a2);
LABEL_35:
    v4 = v22;
    goto LABEL_31;
  }
  v4 = ((__int64 (__fastcall *)(struct ISequentialStream *, ULONG *, _QWORD, int *))a2->lpVtbl->Write)(
         a2,
         &pvarSrc->decVal.Lo32,
         v6,
         &v24);
  if ( v4 >= 0 && v6 != v24 )
    goto LABEL_30;
LABEL_31:
  VariantClear(&pvarg);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001d5b0  mov     r11, rsp
0x18001d5b3  push    rbx
0x18001d5b4  push    rsi
0x18001d5b5  push    rdi
0x18001d5b6  push    r12
0x18001d5b8  push    r14
0x18001d5ba  push    r15
0x18001d5bc  sub     rsp, 58h
0x18001d5c0  xorps   xmm0, xmm0
0x18001d5c3  mov     dword ptr [r11+8], 0
0x18001d5cb  mov     rsi, rcx
0x18001d5ce  xor     eax, eax
0x18001d5d0  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x18001d5d5  lea     rcx, [r11-58h]; pvarg
0x18001d5d9  mov     [r11-48h], rax
0x18001d5dd  mov     r14, rdx
0x18001d5e0  call    cs:__imp_VariantInit
0x18001d5e7  nop     dword ptr [rax+rax+00h]
0x18001d5ec  test    rsi, rsi
0x18001d5ef  jnz     short loc_18001D5FB
0x18001d5f1  mov     ebx, 80004003h
0x18001d5f6  jmp     loc_18001D6E0
0x18001d5fb  test    r14, r14
0x18001d5fe  jz      short loc_18001D5F1
0x18001d600  movzx   ecx, word ptr [rsi]
0x18001d603  xor     edi, edi
0x18001d605  lea     r15d, [rdi+8]
0x18001d609  lea     r12d, [rdi+1]
0x18001d60d  cmp     ecx, 0Bh
0x18001d610  ja      short loc_18001D647
0x18001d612  jz      short loc_18001D670
0x18001d614  sub     ecx, 2
0x18001d617  jz      short loc_18001D670
0x18001d619  sub     ecx, r12d
0x18001d61c  jz      short loc_18001D669
0x18001d61e  sub     ecx, r12d
0x18001d621  jz      short loc_18001D669
0x18001d623  sub     ecx, r12d
0x18001d626  jz      short loc_18001D642
0x18001d628  sub     ecx, r12d
0x18001d62b  jz      short loc_18001D642
0x18001d62d  sub     ecx, r12d
0x18001d630  jz      short loc_18001D642
0x18001d632  sub     ecx, 2
0x18001d635  jz      loc_18001D6DB
0x18001d63b  cmp     ecx, r12d
0x18001d63e  jz      short loc_18001D669
0x18001d640  jmp     short loc_18001D67A
0x18001d642  mov     edi, r15d
0x18001d645  jmp     short loc_18001D67A
0x18001d647  sub     ecx, 0Dh
0x18001d64a  jz      loc_18001D6DB
0x18001d650  sub     ecx, 3
0x18001d653  jz      short loc_18001D677
0x18001d655  sub     ecx, r12d
0x18001d658  jz      short loc_18001D677
0x18001d65a  sub     ecx, r12d
0x18001d65d  jz      short loc_18001D670
0x18001d65f  sub     ecx, r12d
0x18001d662  jz      short loc_18001D669
0x18001d664  sub     ecx, 3
0x18001d667  jnz     short loc_18001D63B
0x18001d669  mov     edi, 4
0x18001d66e  jmp     short loc_18001D67A
0x18001d670  mov     edi, 2
0x18001d675  jmp     short loc_18001D67A
0x18001d677  mov     edi, r12d
0x18001d67a  mov     rax, [r14]
0x18001d67d  lea     r9, [rsp+88h+arg_0]
0x18001d685  mov     r8d, 2
0x18001d68b  mov     rdx, rsi
0x18001d68e  mov     rcx, r14
0x18001d691  mov     rax, [rax+20h]
0x18001d695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d69a  mov     ebx, eax
0x18001d69c  test    eax, eax
0x18001d69e  js      short loc_18001D6E0
0x18001d6a0  cmp     [rsp+88h+arg_0], 2
0x18001d6a8  jnz     short loc_18001D6DB
0x18001d6aa  test    edi, edi
0x18001d6ac  jz      short loc_18001D702
0x18001d6ae  mov     rax, [r14]
0x18001d6b1  lea     rdx, [rsi+8]
0x18001d6b5  lea     r9, [rsp+88h+arg_0]
0x18001d6bd  mov     r8d, edi
0x18001d6c0  mov     rcx, r14
0x18001d6c3  mov     rax, [rax+20h]
0x18001d6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6cc  mov     ebx, eax
0x18001d6ce  test    eax, eax
0x18001d6d0  js      short loc_18001D6E0
0x18001d6d2  cmp     edi, [rsp+88h+arg_0]
0x18001d6d9  jz      short loc_18001D6E0
0x18001d6db  mov     ebx, 80004005h
0x18001d6e0  lea     rcx, [rsp+88h+pvarg]; pvarg
0x18001d6e5  call    cs:__imp_VariantClear
0x18001d6ec  nop     dword ptr [rax+rax+00h]
0x18001d6f1  mov     eax, ebx
0x18001d6f3  add     rsp, 58h
0x18001d6f7  pop     r15
0x18001d6f9  pop     r14
0x18001d6fb  pop     r12
0x18001d6fd  pop     rdi
0x18001d6fe  pop     rsi
0x18001d6ff  pop     rbx
0x18001d700  retn
0x18001d702  movzx   eax, word ptr [rsi]
0x18001d705  cmp     ax, r15w
0x18001d709  jnz     short loc_18001D71B
0x18001d70b  mov     rcx, [rsi+8]
0x18001d70f  mov     rdx, r14
0x18001d712  call    WriteBSTRToStream
0x18001d717  mov     ebx, eax
0x18001d719  jmp     short loc_18001D6E0
0x18001d71b  bt      ax, 0Dh
0x18001d720  jnb     short loc_18001D738
0x18001d722  mov     rcx, [rsi+8]; psa
0x18001d726  mov     edx, 0DFFFh
0x18001d72b  and     dx, ax; unsigned __int16
0x18001d72e  mov     r8, r14; struct ISequentialStream *
0x18001d731  call    ?WriteSafeArrayToStream@@YAJPEAUtagSAFEARRAY@@GPEAUISequentialStream@@@Z; WriteSafeArrayToStream(tagSAFEARRAY *,ushort,ISequentialStream *)
0x18001d736  jmp     short loc_18001D717
0x18001d738  cmp     ax, r12w
0x18001d73c  jz      short loc_18001D6E0
0x18001d73e  mov     r9d, r15d; vt
0x18001d741  lea     rcx, [rsp+88h+pvarg]; pvargDest
0x18001d746  mov     r8d, r12d; wFlags
0x18001d749  mov     rdx, rsi; pvarSrc
0x18001d74c  call    cs:__imp_VariantChangeType
0x18001d753  nop     dword ptr [rax+rax+00h]
0x18001d758  mov     ebx, eax
0x18001d75a  test    eax, eax
0x18001d75c  js      short loc_18001D6E0
0x18001d75e  mov     rcx, qword ptr [rsp+88h+pvarg+8]
0x18001d763  jmp     short loc_18001D70F
```
