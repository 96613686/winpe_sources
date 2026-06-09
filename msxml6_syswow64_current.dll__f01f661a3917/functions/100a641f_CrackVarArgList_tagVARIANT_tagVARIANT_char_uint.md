# CrackVarArgList(tagVARIANT * *,tagVARIANT *,char *,uint *)

- ea: `0x100a641f`
- end: `0x100a6523`
- name: `?CrackVarArgList@@YGJPAPAUtagVARIANT@@PAU1@PADPAI@Z`
- size: `260`
- prototype: `HRESULT __userpurge@<eax>(tagVARIANT **ppva@<ecx>, tagVARIANT *pvaStart@<edx>, char *args, unsigned int *pcArgs)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x100a66b4`

## callees

- `0x10067bc0`
- `0x100a641f`

## import_xrefs

- `OLEAUT32!__imp__SysAllocString@4` at `0x100a64a8`
- `OLEAUT32!__imp__SysAllocString@4` at `0x100a64a8`
- `OLEAUT32!__imp__VariantInit@4` at `0x100a64ee`
- `OLEAUT32!__imp__VariantInit@4` at `0x100a64ee`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100a64fb`
- `OLEAUT32!__imp__VariantCopy@8` at `0x100a64fb`

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
0x100a641f  mov     edi, edi
0x100a6421  push    ebp
0x100a6422  mov     ebp, esp
0x100a6424  sub     esp, 0Ch
0x100a6427  push    ebx
0x100a6428  push    esi
0x100a6429  mov     esi, [ebp+pcArgs]
0x100a642c  xor     ebx, ebx
0x100a642e  mov     [ebp+var_8], pvaStart
0x100a6431  mov     pvaStart, ppva
0x100a6433  push    edi
0x100a6434  mov     edi, [ebp+args]
0x100a6437  mov     [ebp+var_4], pvaStart
0x100a643a  mov     [esi], ebx
0x100a643c  movzx   eax, word ptr [edi]
0x100a643f  add     edi, 4
0x100a6442  mov     [ebp+pvargSrc], edi
0x100a6445  mov     ppva, edi
0x100a6447  test    ax, ax
0x100a644a  jz      loc_100A6515
0x100a6450  add     dword ptr [pvaStart], 0FFFFFFF0h
0x100a6453  mov     esi, [pvaStart]
0x100a6455  cmp     esi, [ebp+var_8]
0x100a6458  jz      loc_100A650E
0x100a645e  mov     [esi], ax
0x100a6461  cmp     eax, 0Bh
0x100a6464  ja      short loc_100A64C8
0x100a6466  jz      short loc_100A64BC
0x100a6468  dec     eax
0x100a6469  sub     eax, 1
0x100a646c  jz      short loc_100A64BC
0x100a646e  sub     eax, 1
0x100a6471  jz      short loc_100A64E3
0x100a6473  sub     eax, 5
0x100a6476  jz      short loc_100A649B
0x100a6478  sub     eax, 1
0x100a647b  jnz     short loc_100A64D7
0x100a647d  mov     ppva, [ppva]
0x100a647f  add     edi, 4
0x100a6482  mov     [esi+8], ppva
0x100a6485  test    ppva, ppva
0x100a6487  jz      short loc_100A6508
0x100a6489  mov     eax, [ppva]
0x100a648b  push    ppva
0x100a648c  mov     esi, [eax+4]
0x100a648f  mov     ppva, esi; this
0x100a6491  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a6497  call    esi
0x100a6499  jmp     short loc_100A6505
0x100a649b  mov     eax, [ppva]
0x100a649d  add     edi, 4
0x100a64a0  mov     [esi+8], eax
0x100a64a3  test    eax, eax
0x100a64a5  jz      short loc_100A6508
0x100a64a7  push    eax; psz
0x100a64a8  call    ds:__imp__SysAllocString@4; SysAllocString(x)
0x100a64ae  mov     [esi+8], eax
0x100a64b1  test    eax, eax
0x100a64b3  jnz     short loc_100A6505
0x100a64b5  mov     eax, 8007000Eh
0x100a64ba  jmp     short loc_100A651C
0x100a64bc  mov     ax, [ppva]
0x100a64bf  add     edi, 4
0x100a64c2  mov     [esi+8], ax
0x100a64c6  jmp     short loc_100A6508
0x100a64c8  sub     eax, 0Ch
0x100a64cb  jz      short loc_100A64ED
0x100a64cd  sub     eax, 1
0x100a64d0  jz      short loc_100A647D
0x100a64d2  sub     eax, 9
0x100a64d5  jz      short loc_100A64DD
0x100a64d7  add     dword ptr [pvaStart], 10h
0x100a64da  dec     ebx
0x100a64db  jmp     short loc_100A6508
0x100a64dd  push    3
0x100a64df  pop     eax
0x100a64e0  mov     [esi], ax
0x100a64e3  mov     eax, [ppva]
0x100a64e5  add     edi, 4
0x100a64e8  mov     [esi+8], eax
0x100a64eb  jmp     short loc_100A6508
0x100a64ed  push    esi; pvarg
0x100a64ee  call    ds:__imp__VariantInit@4; VariantInit(x)
0x100a64f4  push    [ebp+pvargSrc]; pvargSrc
0x100a64f7  add     edi, 10h
0x100a64fa  push    esi; pvargDest
0x100a64fb  call    ds:__imp__VariantCopy@8; VariantCopy(x,x)
0x100a6501  test    eax, eax
0x100a6503  js      short loc_100A651C
0x100a6505  mov     pvaStart, [ebp+var_4]
0x100a6508  inc     ebx
0x100a6509  jmp     loc_100A643C
0x100a650e  mov     eax, 80004005h
0x100a6513  jmp     short loc_100A651C
0x100a6515  mov     eax, [ebp+pcArgs]
0x100a6518  mov     [eax], ebx
0x100a651a  xor     eax, eax
0x100a651c  pop     edi
0x100a651d  pop     esi
0x100a651e  pop     ebx
0x100a651f  leave
0x100a6520  retn    8
```
