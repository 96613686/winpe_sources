# ColumnLv::Delete(tagColParams *,Err &)

- ea: `0x100185d0`
- end: `0x10018681`
- name: `?Delete@ColumnLv@@UAEXPAUtagColParams@@AAVErr@@@Z`
- size: `177`
- prototype: `void __thiscall(ColumnLv *__hidden this, struct tagColParams *, struct Err *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x10018200`
- `0x100185d0`
- `0x1003a6f0`
- `0x1003bbf0`
- `0x1003f080`
- `0x1003f180`
- `0x10043b60`

## pseudocode

```c
void __thiscall ColumnLv::Delete(ColumnLv *this, Record **a2, void **a3)
{
  unsigned __int8 v4; // al
  unsigned __int8 *v5; // eax
  LongValue *LvObject; // eax
  LongValue *v7; // esi
  int v8; // ecx
  LvDataNew *v9; // ecx
  unsigned int v10; // [esp+Ch] [ebp-4h] BYREF

  v4 = **(_BYTE **)*a2;
  if ( (unsigned __int8)*((_DWORD *)this + 3) < v4
    && (*(_BYTE *)(*((_DWORD *)*a2 + 1) + (*((_DWORD *)this + 3) >> 3) - (((unsigned int)v4 + 7) >> 3) + *(_DWORD *)*a2)
      & *((_BYTE *)&Bitmap::ThisBit + (*((_DWORD *)this + 3) & 7))) != 0 )
  {
    v5 = Record::Address(*a2, *((_DWORD *)this + 4), &v10, a3);
    if ( (*(_BYTE *)a3 & 8) == 0 && *(int *)v5 >= 0 )
    {
      LvObject = ColumnLv::FindOrCreateLvObject(this, (struct tagColParams *)a2, (struct Err *)a3);
      v7 = LvObject;
      if ( (*(_BYTE *)a3 & 8) == 0 )
      {
        LongValue::RemoveOldPagesFromSM(LvObject, (struct tagColParams *)a2, (struct Err *)a3);
        if ( (*(_BYTE *)a3 & 8) == 0 )
          LongValue::FreePages(v7, (struct tagColParams *)a2, v8, 0x7FFFFFFF, 0, v8, (struct Err *)a3);
        v9 = (LvDataNew *)*((_DWORD *)v7 + 1);
        if ( v9 )
          LvDataNew::Reset(v9);
        LvDataOrig::Reset(*(LvDataOrig **)v7);
        *((_DWORD *)v7 + 6) = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x100185d0  mov     edi, edi
0x100185d2  push    ebp
0x100185d3  mov     ebp, esp
0x100185d5  push    ecx
0x100185d6  push    ebx
0x100185d7  mov     ebx, [ebp+arg_0]
0x100185da  push    esi
0x100185db  push    edi
0x100185dc  mov     esi, ecx
0x100185de  mov     edi, [ebx]
0x100185e0  mov     edx, [esi+0Ch]
0x100185e3  mov     eax, [edi]
0x100185e5  mov     al, [eax]
0x100185e7  cmp     dl, al
0x100185e9  jnb     loc_10018678
0x100185ef  movzx   eax, al
0x100185f2  mov     ecx, edx
0x100185f4  add     eax, 7
0x100185f7  shr     ecx, 3
0x100185fa  shr     eax, 3
0x100185fd  and     edx, 7
0x10018600  sub     ecx, eax
0x10018602  mov     eax, [edi]
0x10018604  add     ecx, [edi+4]
0x10018607  mov     al, [ecx+eax]
0x1001860a  test    ds:?ThisBit@Bitmap@@1QBEB[edx], al; uchar const * const Bitmap::ThisBit
0x10018610  jz      short loc_10018678
0x10018612  mov     edi, [ebp+arg_4]
0x10018615  lea     eax, [ebp+var_4]
0x10018618  mov     ecx, [ebx]; this
0x1001861a  push    edi; struct Err *
0x1001861b  push    eax; unsigned int *
0x1001861c  push    dword ptr [esi+10h]; unsigned int
0x1001861f  call    ?Address@Record@@QAEPAEIPAIAAVErr@@@Z; Record::Address(uint,uint *,Err &)
0x10018624  test    byte ptr [edi], 8
0x10018627  jnz     short loc_10018678
0x10018629  cmp     dword ptr [eax], 0
0x1001862c  jl      short loc_10018678
0x1001862e  push    edi; struct Err *
0x1001862f  push    ebx; struct tagColParams *
0x10018630  mov     ecx, esi; this
0x10018632  call    ?FindOrCreateLvObject@ColumnLv@@QAEPAVLongValue@@PAUtagColParams@@AAVErr@@@Z; ColumnLv::FindOrCreateLvObject(tagColParams *,Err &)
0x10018637  test    byte ptr [edi], 8
0x1001863a  mov     esi, eax
0x1001863c  jnz     short loc_10018678
0x1001863e  push    edi; struct Err *
0x1001863f  push    ebx; struct tagColParams *
0x10018640  mov     ecx, esi; this
0x10018642  call    ?RemoveOldPagesFromSM@LongValue@@QAEXPAUtagColParams@@AAVErr@@@Z; LongValue::RemoveOldPagesFromSM(tagColParams *,Err &)
0x10018647  test    byte ptr [edi], 8
0x1001864a  jnz     short loc_1001865E
0x1001864c  push    edi; struct Err *
0x1001864d  push    ecx; int
0x1001864e  push    0; int
0x10018650  push    7FFFFFFFh; int
0x10018655  push    ecx; int
0x10018656  push    ebx; struct tagColParams *
0x10018657  mov     ecx, esi; this
0x10018659  call    ?FreePages@LongValue@@QAEXPAUtagColParams@@HHHHAAVErr@@@Z; LongValue::FreePages(tagColParams *,int,int,int,int,Err &)
0x1001865e  mov     ecx, [esi+4]; this
0x10018661  test    ecx, ecx
0x10018663  jz      short loc_1001866A
0x10018665  call    ?Reset@LvDataNew@@QAEXXZ; LvDataNew::Reset(void)
0x1001866a  mov     ecx, [esi]; this
0x1001866c  call    ?Reset@LvDataOrig@@QAEXXZ; LvDataOrig::Reset(void)
0x10018671  mov     dword ptr [esi+18h], 0
0x10018678  pop     edi
0x10018679  pop     esi
0x1001867a  pop     ebx
0x1001867b  mov     esp, ebp
0x1001867d  pop     ebp
0x1001867e  retn    8
```
