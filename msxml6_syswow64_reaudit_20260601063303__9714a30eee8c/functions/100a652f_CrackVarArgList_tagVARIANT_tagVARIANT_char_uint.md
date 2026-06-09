# CrackVarArgList(tagVARIANT * *,tagVARIANT *,char *,uint *)

- ea: `0x100a652f`
- end: `0x100a6633`
- name: `?CrackVarArgList@@YGJPAPAUtagVARIANT@@PAU1@PADPAI@Z`
- size: `260`
- prototype: `HRESULT __fastcall(tagVARIANT **ppva, tagVARIANT *pvaStart, VARIANTARG *args, unsigned int *pcArgs)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100a67c4`

## callees

- `0x10067b20`
- `0x100a652f`

## import_xrefs

- `OLEAUT32!__imp__SysAllocString@4` at `0x100a65b8`
- `OLEAUT32!__imp__SysAllocString@4` at `0x100a65b8`
- `OLEAUT32!__imp__VariantInit@4` at `0x100a65fe`
- `OLEAUT32!__imp__VariantInit@4` at `0x100a65fe`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100a660b`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100a660b`

## pseudocode

```c
HRESULT __fastcall CrackVarArgList(tagVARIANT **ppva, tagVARIANT *pvaStart, VARIANTARG *args, unsigned int *pcArgs)
{
  unsigned int v4; // ebx
  tagVARIANT **v5; // edx
  unsigned int vt; // eax
  char *v8; // ecx
  VARIANTARG *v9; // esi
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // ecx
  const OLECHAR *v14; // eax
  BSTR v15; // eax
  HRESULT result; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  VARIANTARG *pvargSrc; // [esp+Ch] [ebp-Ch]

  v4 = 0;
  v5 = ppva;
  *pcArgs = 0;
  while ( 1 )
  {
    vt = args->vt;
    args = (VARIANTARG *)((char *)args + 4);
    pvargSrc = args;
    v8 = (char *)args;
    if ( !(_WORD)vt )
      break;
    v9 = --*v5;
    if ( *v5 == pvaStart )
      return -2147467259;
    v9->vt = vt;
    if ( vt <= 0xB )
    {
      if ( vt == 11 || (v10 = vt - 2) == 0 )
      {
        args = (VARIANTARG *)((char *)args + 4);
        v9->iVal = *(_WORD *)v8;
        goto LABEL_24;
      }
      v11 = v10 - 1;
      if ( !v11 )
        goto LABEL_21;
      v12 = v11 - 5;
      if ( !v12 )
      {
        v14 = *(const OLECHAR **)&args->vt;
        args = (VARIANTARG *)((char *)args + 4);
        v9->decVal.Lo32 = *(_DWORD *)v8;
        if ( !v14 )
          goto LABEL_24;
        v15 = SysAllocString(v14);
        v9->decVal.Lo32 = (unsigned int)v15;
        if ( !v15 )
          return -2147024882;
        goto LABEL_23;
      }
      if ( v12 != 1 )
        goto LABEL_19;
      goto LABEL_10;
    }
    v17 = vt - 12;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        if ( v18 != 9 )
        {
LABEL_19:
          ++*v5;
          --v4;
          goto LABEL_24;
        }
        v9->vt = 3;
LABEL_21:
        args = (VARIANTARG *)((char *)args + 4);
        v9->decVal.Lo32 = *(_DWORD *)v8;
        goto LABEL_24;
      }
LABEL_10:
      v13 = *(_DWORD *)&args->vt;
      args = (VARIANTARG *)((char *)args + 4);
      v9->decVal.Lo32 = v13;
      if ( !v13 )
        goto LABEL_24;
      (*(void (__thiscall **)(_DWORD, unsigned int))(*(_DWORD *)v13 + 4))(*(_DWORD *)(*(_DWORD *)v13 + 4), v13);
      goto LABEL_23;
    }
    VariantInit(v9);
    ++args;
    result = VariantCopy(v9, pvargSrc);
    if ( result < 0 )
      return result;
LABEL_23:
    v5 = ppva;
LABEL_24:
    ++v4;
  }
  *pcArgs = v4;
  return 0;
}

```

## disassembly

```asm
0x100a652f  mov     edi, edi
0x100a6531  push    ebp
0x100a6532  mov     ebp, esp
0x100a6534  sub     esp, 0Ch
0x100a6537  push    ebx
0x100a6538  push    esi
0x100a6539  mov     esi, [ebp+pcArgs]
0x100a653c  xor     ebx, ebx
0x100a653e  mov     [ebp+var_8], pvaStart
0x100a6541  mov     pvaStart, ppva
0x100a6543  push    edi
0x100a6544  mov     edi, [ebp+args]
0x100a6547  mov     [ebp+var_4], pvaStart
0x100a654a  mov     [esi], ebx
0x100a654c  movzx   eax, word ptr [edi]
0x100a654f  add     edi, 4
0x100a6552  mov     [ebp+pvargSrc], edi
0x100a6555  mov     ppva, edi
0x100a6557  test    ax, ax
0x100a655a  jz      loc_100A6625
0x100a6560  add     dword ptr [pvaStart], 0FFFFFFF0h
0x100a6563  mov     esi, [pvaStart]
0x100a6565  cmp     esi, [ebp+var_8]
0x100a6568  jz      loc_100A661E
0x100a656e  mov     [esi], ax
0x100a6571  cmp     eax, 0Bh
0x100a6574  ja      short loc_100A65D8
0x100a6576  jz      short loc_100A65CC
0x100a6578  dec     eax
0x100a6579  sub     eax, 1
0x100a657c  jz      short loc_100A65CC
0x100a657e  sub     eax, 1
0x100a6581  jz      short loc_100A65F3
0x100a6583  sub     eax, 5
0x100a6586  jz      short loc_100A65AB
0x100a6588  sub     eax, 1
0x100a658b  jnz     short loc_100A65E7
0x100a658d  mov     ppva, [ppva]
0x100a658f  add     edi, 4
0x100a6592  mov     [esi+8], ppva
0x100a6595  test    ppva, ppva
0x100a6597  jz      short loc_100A6618
0x100a6599  mov     eax, [ppva]
0x100a659b  push    ppva
0x100a659c  mov     esi, [eax+4]
0x100a659f  mov     ppva, esi; this
0x100a65a1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a65a7  call    esi
0x100a65a9  jmp     short loc_100A6615
0x100a65ab  mov     eax, [ppva]
0x100a65ad  add     edi, 4
0x100a65b0  mov     [esi+8], eax
0x100a65b3  test    eax, eax
0x100a65b5  jz      short loc_100A6618
0x100a65b7  push    eax; psz
0x100a65b8  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x100a65be  mov     [esi+8], eax
0x100a65c1  test    eax, eax
0x100a65c3  jnz     short loc_100A6615
0x100a65c5  mov     eax, 8007000Eh
0x100a65ca  jmp     short loc_100A662C
0x100a65cc  mov     ax, [ppva]
0x100a65cf  add     edi, 4
0x100a65d2  mov     [esi+8], ax
0x100a65d6  jmp     short loc_100A6618
0x100a65d8  sub     eax, 0Ch
0x100a65db  jz      short loc_100A65FD
0x100a65dd  sub     eax, 1
0x100a65e0  jz      short loc_100A658D
0x100a65e2  sub     eax, 9
0x100a65e5  jz      short loc_100A65ED
0x100a65e7  add     dword ptr [pvaStart], 10h
0x100a65ea  dec     ebx
0x100a65eb  jmp     short loc_100A6618
0x100a65ed  push    3
0x100a65ef  pop     eax
0x100a65f0  mov     [esi], ax
0x100a65f3  mov     eax, [ppva]
0x100a65f5  add     edi, 4
0x100a65f8  mov     [esi+8], eax
0x100a65fb  jmp     short loc_100A6618
0x100a65fd  push    esi; pvarg
0x100a65fe  call    ds:__imp__VariantInit@4; VariantInit(x)
0x100a6604  push    [ebp+pvargSrc]; pvargSrc
0x100a6607  add     edi, 10h
0x100a660a  push    esi; pvargDest
0x100a660b  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x100a6611  test    eax, eax
0x100a6613  js      short loc_100A662C
0x100a6615  mov     pvaStart, [ebp+var_4]
0x100a6618  inc     ebx
0x100a6619  jmp     loc_100A654C
0x100a661e  mov     eax, 80004005h
0x100a6623  jmp     short loc_100A662C
0x100a6625  mov     eax, [ebp+pcArgs]
0x100a6628  mov     [eax], ebx
0x100a662a  xor     eax, eax
0x100a662c  pop     edi
0x100a662d  pop     esi
0x100a662e  pop     ebx
0x100a662f  leave
0x100a6630  retn    8
```
