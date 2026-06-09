# CIPropertyStorageWrapper::GetPropNodeData(_propertyNodeDef *,tagPROPVARIANT *)

- ea: `0x180011330`
- end: `0x1800114fc`
- name: `?GetPropNodeData@CIPropertyStorageWrapper@@QEAAJPEAU_propertyNodeDef@@PEAUtagPROPVARIANT@@@Z`
- size: `460`
- prototype: `__int64 __fastcall(CIPropertyStorageWrapper *__hidden this, struct _propertyNodeDef *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180011840`

## callees

- `0x180011330`
- `0x1800184c2`
- `0x180019010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18001147d`
- `ole32!CoTaskMemAlloc` at `0x18001147d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800113f7`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800113f7`

## pseudocode

```c
__int64 __fastcall CIPropertyStorageWrapper::GetPropNodeData(
        CIPropertyStorageWrapper *this,
        struct _propertyNodeDef *a2,
        struct tagPROPVARIANT *a3)
{
  unsigned int v3; // esi
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  int v10; // eax
  UINT v11; // edx
  void *v12; // rax
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v19; // ecx
  LARGE_INTEGER *v20; // rax
  LARGE_INTEGER v21; // rcx

  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v3 = 0;
  a3->vt = *((_WORD *)a2 + 16);
  v6 = *((unsigned __int16 *)a2 + 16);
  if ( v6 > 0x24 )
  {
    if ( v6 > 0x47 )
      return (unsigned int)-2147467263;
    v19 = v6 - 64;
    if ( v19 )
    {
      if ( v19 != 2 )
        return (unsigned int)-2147467263;
      v20 = (LARGE_INTEGER *)*((_QWORD *)a2 + 5);
      v21 = *v20;
      a3->hVal = *v20;
      if ( v21.QuadPart )
        (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v21.QuadPart + 8LL))(v21);
      return v3;
    }
    goto LABEL_13;
  }
  if ( v6 == 36 )
    return (unsigned int)-2147467263;
  if ( v6 > 0x10 )
  {
    if ( v6 > 0x18 )
    {
      if ( v6 != 31 )
        return (unsigned int)-2147467263;
      v12 = CoTaskMemAlloc(*((unsigned int *)a2 + 9));
LABEL_33:
      a3->hVal.QuadPart = (LONGLONG)v12;
      if ( v12 )
        memcpy_0(v12, *((const void **)a2 + 5), *((unsigned int *)a2 + 9));
      else
        return (unsigned int)-2147024882;
      return v3;
    }
    if ( v6 == 24 )
      return (unsigned int)-2147467263;
    v13 = v6 - 17;
    if ( !v13 )
    {
LABEL_20:
      a3->cVal = **((_BYTE **)a2 + 5);
      return v3;
    }
    v14 = v13 - 1;
    if ( !v14 )
      goto LABEL_12;
    v15 = v14 - 1;
    if ( !v15 )
      goto LABEL_11;
    v16 = v15 - 1;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        if ( v17 - 1 < 2 )
          goto LABEL_11;
        return (unsigned int)-2147467263;
      }
    }
LABEL_13:
    a3->hVal.QuadPart = **((_QWORD **)a2 + 5);
    return v3;
  }
  if ( v6 == 16 )
    goto LABEL_20;
  if ( v6 > 7 )
  {
    v9 = v6 - 8;
    if ( v9 )
    {
      if ( v9 != 3 )
        return (unsigned int)-2147467263;
      goto LABEL_12;
    }
    v10 = *((_DWORD *)a2 + 9) >> 1;
    v11 = v10 - 1;
    if ( !v10 )
      v11 = 0;
    v12 = SysAllocStringLen(0, v11);
    goto LABEL_33;
  }
  if ( v6 == 7 )
    goto LABEL_13;
  if ( *((_WORD *)a2 + 16) )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        if ( v8 == 1 )
        {
LABEL_11:
          a3->lVal = **((_DWORD **)a2 + 5);
          return v3;
        }
        return (unsigned int)-2147467263;
      }
LABEL_12:
      a3->iVal = **((_WORD **)a2 + 5);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180011330  mov     [rsp+arg_0], rbx
0x180011335  mov     [rsp+arg_8], rsi
0x18001133a  push    rdi
0x18001133b  sub     rsp, 20h
0x18001133f  xor     eax, eax
0x180011341  xorps   xmm0, xmm0
0x180011344  movups  xmmword ptr [r8], xmm0
0x180011348  mov     [r8+10h], rax
0x18001134c  xor     esi, esi
0x18001134e  movzx   eax, word ptr [rdx+20h]
0x180011352  mov     rdi, r8
0x180011355  mov     [r8], ax
0x180011359  mov     rbx, rdx
0x18001135c  movzx   ecx, word ptr [rdx+20h]
0x180011360  cmp     ecx, 24h ; '$'
0x180011363  ja      loc_1800114A5
0x180011369  jz      loc_180011440
0x18001136f  cmp     ecx, 10h
0x180011372  ja      loc_18001140E
0x180011378  jz      loc_180011402
0x18001137e  cmp     ecx, 7
0x180011381  ja      short loc_1800113D1
0x180011383  jz      short loc_1800113C4
0x180011385  test    ecx, ecx
0x180011387  jz      loc_180011445
0x18001138d  sub     ecx, 1
0x180011390  jz      loc_180011445
0x180011396  sub     ecx, 1
0x180011399  jz      short loc_1800113B3
0x18001139b  sub     ecx, 1
0x18001139e  jnz     loc_1800114CF
0x1800113a4  mov     rax, [rdx+28h]
0x1800113a8  mov     ecx, [rax]
0x1800113aa  mov     [r8+8], ecx
0x1800113ae  jmp     loc_180011445
0x1800113b3  mov     rax, [rdx+28h]
0x1800113b7  movzx   ecx, word ptr [rax]
0x1800113ba  mov     [r8+8], cx
0x1800113bf  jmp     loc_180011445
0x1800113c4  mov     rax, [rdx+28h]
0x1800113c8  mov     rcx, [rax]
0x1800113cb  mov     [r8+8], rcx
0x1800113cf  jmp     short loc_180011445
0x1800113d1  sub     ecx, 8
0x1800113d4  jz      short loc_1800113EA
0x1800113d6  sub     ecx, 1
0x1800113d9  jz      short loc_180011440
0x1800113db  sub     ecx, 1
0x1800113de  jz      short loc_180011440
0x1800113e0  sub     ecx, 1
0x1800113e3  jz      short loc_1800113B3
0x1800113e5  jmp     loc_1800114CF
0x1800113ea  mov     eax, [rdx+24h]
0x1800113ed  shr     eax, 1
0x1800113ef  lea     edx, [rax-1]
0x1800113f2  cmovz   edx, eax; ui
0x1800113f5  xor     ecx, ecx; strIn
0x1800113f7  call    cs:__imp_SysAllocStringLen
0x1800113fd  jmp     loc_180011483
0x180011402  mov     rax, [rdx+28h]
0x180011406  mov     cl, [rax]
0x180011408  mov     [r8+8], cl
0x18001140c  jmp     short loc_180011445
0x18001140e  cmp     ecx, 18h
0x180011411  ja      short loc_180011457
0x180011413  jz      short loc_180011440
0x180011415  sub     ecx, 11h
0x180011418  jz      short loc_180011402
0x18001141a  sub     ecx, 1
0x18001141d  jz      short loc_1800113B3
0x18001141f  sub     ecx, 1
0x180011422  jz      short loc_1800113A4
0x180011424  sub     ecx, 1
0x180011427  jz      short loc_1800113C4
0x180011429  sub     ecx, 1
0x18001142c  jz      short loc_1800113C4
0x18001142e  sub     ecx, 1
0x180011431  jz      loc_1800113A4
0x180011437  cmp     ecx, 1
0x18001143a  jz      loc_1800113A4
0x180011440  mov     esi, 80004001h
0x180011445  mov     rbx, [rsp+28h+arg_0]
0x18001144a  mov     eax, esi
0x18001144c  mov     rsi, [rsp+28h+arg_8]
0x180011451  add     rsp, 20h
0x180011455  pop     rdi
0x180011456  retn
0x180011457  sub     ecx, 19h
0x18001145a  jz      short loc_180011440
0x18001145c  sub     ecx, 1
0x18001145f  jz      short loc_180011440
0x180011461  sub     ecx, 1
0x180011464  jz      short loc_180011440
0x180011466  sub     ecx, 1
0x180011469  jz      short loc_180011440
0x18001146b  sub     ecx, 1
0x18001146e  jz      short loc_180011440
0x180011470  sub     ecx, 1
0x180011473  jz      short loc_180011440
0x180011475  cmp     ecx, 1
0x180011478  jnz     short loc_180011440
0x18001147a  mov     ecx, [rdx+24h]; cb
0x18001147d  call    cs:__imp_CoTaskMemAlloc
0x180011483  mov     [rdi+8], rax
0x180011487  test    rax, rax
0x18001148a  jnz     short loc_180011493
0x18001148c  mov     esi, 8007000Eh
0x180011491  jmp     short loc_180011445
0x180011493  mov     r8d, [rbx+24h]; Size
0x180011497  mov     rcx, rax; void *
0x18001149a  mov     rdx, [rbx+28h]; Src
0x18001149e  call    memcpy_0
0x1800114a3  jmp     short loc_180011445
0x1800114a5  cmp     ecx, 47h ; 'G'
0x1800114a8  ja      short loc_180011440
0x1800114aa  sub     ecx, 40h ; '@'
0x1800114ad  jz      loc_1800113C4
0x1800114b3  sub     ecx, 1
0x1800114b6  jz      short loc_180011440
0x1800114b8  sub     ecx, 1
0x1800114bb  jz      short loc_1800114D7
0x1800114bd  sub     ecx, 1
0x1800114c0  jz      loc_180011440
0x1800114c6  sub     ecx, 1
0x1800114c9  jz      loc_180011440
0x1800114cf  sub     ecx, 1
0x1800114d2  jmp     loc_180011440
0x1800114d7  mov     rax, [rdx+28h]
0x1800114db  mov     rcx, [rax]
0x1800114de  mov     [r8+8], rcx
0x1800114e2  test    rcx, rcx
0x1800114e5  jz      loc_180011445
0x1800114eb  mov     rax, [rcx]
0x1800114ee  mov     rax, [rax+8]
0x1800114f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114f7  jmp     loc_180011445
```
