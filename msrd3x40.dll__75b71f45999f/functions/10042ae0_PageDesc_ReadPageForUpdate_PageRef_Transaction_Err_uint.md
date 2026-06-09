# PageDesc::ReadPageForUpdate(PageRef &,Transaction *,Err &,uint)

- ea: `0x10042ae0`
- end: `0x10042d1a`
- name: `?ReadPageForUpdate@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@AAVErr@@I@Z`
- size: `570`
- prototype: `void __thiscall(PageDesc *__hidden this, struct PageRef *, struct Transaction *, struct Err *, char)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x10023730`

## callees

- `0x10012dd0`
- `0x10025ee0`
- `0x10041bb0`
- `0x10041e80`
- `0x10042130`
- `0x100422a0`
- `0x100429a0`
- `0x10042ae0`
- `0x1004e980`
- `0x1005d5f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10042b31`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10042b31`

## pseudocode

```c
void __thiscall PageDesc::ReadPageForUpdate(
        PageDesc *this,
        struct PageRef *a2,
        struct Transaction *a3,
        struct Err *a4,
        unsigned int a5)
{
  struct PageVersion *v6; // edi
  int v7; // eax
  int i; // edi
  Collection *v9; // edx
  unsigned int v10; // eax
  struct PageVersion *v11; // eax
  int v12; // ecx
  struct Page *Pages; // ecx
  int v14; // eax
  Collection *v15; // [esp+Ch] [ebp-Ch]
  struct Page *v16; // [esp+Ch] [ebp-Ch]
  int v17; // [esp+10h] [ebp-8h]
  struct PageVersion *v18; // [esp+14h] [ebp-4h]

  v17 = *(_DWORD *)a3;
  if ( !*(_DWORD *)a3 )
  {
    if ( (*((_BYTE *)this + 82) & 1) != 0 )
      PageDesc::ReadPage(this, a2, a3, a5, a4);
    else
      Err::SetError(a4, -1054, a3);
    return;
  }
  *((_DWORD *)this + 18) = GetTickCount();
  v6 = (PageDesc *)((char *)this + 4 * *((_DWORD *)this + 6) + 28);
  v18 = v6;
  PageDesc::IncrementLock(this, a5, a3, a4);
  if ( (*(_BYTE *)a4 & 8) != 0 )
    return;
  v7 = *((_DWORD *)this + 6);
  if ( v7 >= v17 )
    goto LABEL_27;
  for ( i = v7 + 1; i < v17; ++i )
    *((_DWORD *)this + i + 7) = *((_DWORD *)this + i + 7) & 0xF0 | 5;
  if ( *(_DWORD *)a2 )
    --*(_WORD *)(*(_DWORD *)a2 + 76);
  *((_DWORD *)a2 + 1) = 0;
  *(_DWORD *)a2 = 0;
  v9 = (Collection *)(*((_DWORD *)a3 + 9) - 56 + 56 * i);
  v10 = *((_DWORD *)v9 + 2);
  v15 = v9;
  if ( v10 >= *((_DWORD *)v9 + 1) )
  {
    Collection::Grow(v9, v10 + 1, a4);
    if ( (*(_BYTE *)a4 & 8) != 0 )
    {
LABEL_25:
      PageDesc::DecrementLock(this, a3, a4, 0);
      return;
    }
    v9 = v15;
  }
  *(_DWORD *)(*(_DWORD *)v9 + 4 * (*((_DWORD *)v9 + 2))++) = this;
  if ( (*(_BYTE *)a4 & 8) != 0 )
    goto LABEL_25;
  v11 = v18;
  if ( (*(_BYTE *)v18 & 7) != 0 )
  {
    PageDesc::WireCurrentPage(this, v18, 2, a4);
    if ( (*(_BYTE *)a4 & 8) != 0 )
    {
LABEL_24:
      Transaction::RemovePageDesc(a3, v17, this);
      goto LABEL_25;
    }
    v11 = v18;
  }
  ++*((_DWORD *)this + 16);
  v12 = *(_DWORD *)v11;
  *((_DWORD *)this + i + 7) = *(_DWORD *)v11;
  if ( !*((_DWORD *)this + 6) )
    *((_DWORD *)this + i + 7) = v12 & 0xFFFFFF0F | 0x30;
  if ( (*(_DWORD *)v11 & 8) == 0 && !*((_BYTE *)this + 80) )
  {
    *(_DWORD *)v18 = (*((_DWORD *)this + 3) << 8) | *(_DWORD *)v11 & 0xF8 | 3;
    *((_DWORD *)this + 6) = i;
    v6 = (PageDesc *)((char *)this + 4 * i + 28);
    goto LABEL_27;
  }
  Pages = System::AllocatePages((struct QMsg *)&Sys, (struct Err *)1);
  v16 = Pages;
  if ( (*(_BYTE *)a4 & 8) != 0 )
    goto LABEL_24;
  Page::operator=(Pages, (void *)(*(_DWORD *)v18 & 0xFFFFFF00));
  *(_DWORD *)v18 = (unsigned int)v16 ^ (unsigned __int8)v16 ^ *(_DWORD *)v18 & 0xF8;
  *((_DWORD *)this + 6) = i;
  v6 = (PageDesc *)((char *)this + 4 * i + 28);
LABEL_27:
  PageDesc::DecrementLock(this, a3, a4, 0);
  if ( (*(_BYTE *)v6 & 7) == 0 || (PageDesc::WireCurrentPage(this, v6, 2, a4), (*(_BYTE *)a4 & 8) == 0) )
  {
    *((_DWORD *)a2 + 1) = *(_DWORD *)v6 & 0xFFFFFF00;
    v14 = *(_DWORD *)a2;
    if ( *(PageDesc **)a2 != this )
    {
      if ( v14 )
        --*(_WORD *)(v14 + 76);
      *(_DWORD *)a2 = this;
      ++*((_WORD *)this + 38);
      *((_DWORD *)a2 + 2) = 0;
    }
  }
}

```

## disassembly

```asm
0x10042ae0  mov     edi, edi
0x10042ae2  push    ebp
0x10042ae3  mov     ebp, esp
0x10042ae5  sub     esp, 0Ch
0x10042ae8  push    ebx
0x10042ae9  push    esi
0x10042aea  mov     esi, ecx
0x10042aec  mov     ecx, [ebp+arg_4]
0x10042aef  push    edi
0x10042af0  mov     eax, [ecx]
0x10042af2  mov     [ebp+var_8], eax
0x10042af5  test    eax, eax
0x10042af7  jnz     short loc_10042B31
0x10042af9  test    byte ptr [esi+52h], 1
0x10042afd  jz      short loc_10042B1A
0x10042aff  push    [ebp+arg_8]; struct Err *
0x10042b02  mov     eax, [ebp+arg_0]
0x10042b05  push    dword ptr [ebp+arg_C]; char
0x10042b08  push    ecx; struct Transaction *
0x10042b09  push    eax; struct PageRef *
0x10042b0a  mov     ecx, esi; this
0x10042b0c  call    ?ReadPage@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@IAAVErr@@@Z; PageDesc::ReadPage(PageRef &,Transaction *,uint,Err &)
0x10042b11  pop     edi
0x10042b12  pop     esi
0x10042b13  pop     ebx
0x10042b14  mov     esp, ebp
0x10042b16  pop     ebp
0x10042b17  retn    10h
0x10042b1a  push    ecx
0x10042b1b  mov     ecx, [ebp+arg_8]
0x10042b1e  push    0FFFFFBE2h
0x10042b23  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10042b28  pop     edi
0x10042b29  pop     esi
0x10042b2a  pop     ebx
0x10042b2b  mov     esp, ebp
0x10042b2d  pop     ebp
0x10042b2e  retn    10h
0x10042b31  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10042b37  mov     ebx, [ebp+arg_8]
0x10042b3a  mov     ecx, esi; this
0x10042b3c  mov     [esi+48h], eax
0x10042b3f  mov     eax, [esi+18h]
0x10042b42  push    ebx; struct Err *
0x10042b43  push    [ebp+arg_4]; struct Transaction *
0x10042b46  add     eax, 7
0x10042b49  push    dword ptr [ebp+arg_C]; unsigned int
0x10042b4c  lea     edi, [esi+eax*4]
0x10042b4f  mov     [ebp+var_4], edi
0x10042b52  call    ?IncrementLock@PageDesc@@QAEXIPAVTransaction@@AAVErr@@@Z; PageDesc::IncrementLock(uint,Transaction *,Err &)
0x10042b57  test    byte ptr [ebx], 8
0x10042b5a  jnz     loc_10042D11
0x10042b60  mov     eax, [esi+18h]
0x10042b63  mov     ecx, [ebp+var_8]
0x10042b66  cmp     eax, ecx
0x10042b68  jge     loc_10042CC7
0x10042b6e  lea     edi, [eax+1]
0x10042b71  cmp     edi, ecx
0x10042b73  jge     short loc_10042B95
0x10042b75  nop     word ptr [eax+eax+00000000h]
0x10042b80  mov     eax, [esi+edi*4+1Ch]
0x10042b84  and     eax, 0F0h
0x10042b89  or      eax, 5
0x10042b8c  mov     [esi+edi*4+1Ch], eax
0x10042b90  inc     edi
0x10042b91  cmp     edi, ecx
0x10042b93  jl      short loc_10042B80
0x10042b95  mov     eax, [ebp+arg_0]
0x10042b98  mov     ecx, [eax]
0x10042b9a  test    ecx, ecx
0x10042b9c  jz      short loc_10042BA2
0x10042b9e  dec     word ptr [ecx+4Ch]
0x10042ba2  mov     dword ptr [eax+4], 0
0x10042ba9  lea     edx, ds:0[edi*8]
0x10042bb0  mov     dword ptr [eax], 0
0x10042bb6  sub     edx, edi
0x10042bb8  mov     eax, [ebp+arg_4]
0x10042bbb  mov     eax, [eax+24h]
0x10042bbe  add     eax, 0FFFFFFC8h
0x10042bc1  lea     edx, [eax+edx*8]
0x10042bc4  mov     eax, [edx+8]
0x10042bc7  mov     [ebp+var_C], edx
0x10042bca  cmp     eax, [edx+4]
0x10042bcd  jb      short loc_10042BE5
0x10042bcf  push    ebx; struct Err *
0x10042bd0  inc     eax
0x10042bd1  mov     ecx, edx; this
0x10042bd3  push    eax; unsigned int
0x10042bd4  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x10042bd9  test    byte ptr [ebx], 8
0x10042bdc  jnz     loc_10042C82
0x10042be2  mov     edx, [ebp+var_C]
0x10042be5  mov     ecx, [edx+8]
0x10042be8  mov     eax, [edx]
0x10042bea  mov     [eax+ecx*4], esi
0x10042bed  inc     dword ptr [edx+8]
0x10042bf0  test    byte ptr [ebx], 8
0x10042bf3  jnz     loc_10042C82
0x10042bf9  mov     eax, [ebp+var_4]
0x10042bfc  test    byte ptr [eax], 7
0x10042bff  jz      short loc_10042C14
0x10042c01  push    ebx; struct Err *
0x10042c02  push    2; char
0x10042c04  push    eax; struct PageVersion *
0x10042c05  mov     ecx, esi; this
0x10042c07  call    ?WireCurrentPage@PageDesc@@QAEXAAVPageVersion@@IAAVErr@@@Z; PageDesc::WireCurrentPage(PageVersion &,uint,Err &)
0x10042c0c  test    byte ptr [ebx], 8
0x10042c0f  jnz     short loc_10042C75
0x10042c11  mov     eax, [ebp+var_4]
0x10042c14  inc     dword ptr [esi+40h]
0x10042c17  mov     ecx, [eax]
0x10042c19  mov     [esi+edi*4+1Ch], ecx
0x10042c1d  cmp     dword ptr [esi+18h], 0
0x10042c21  jnz     short loc_10042C30
0x10042c23  and     ecx, 0FFFFFF3Fh
0x10042c29  or      ecx, 30h
0x10042c2c  mov     [esi+edi*4+1Ch], ecx
0x10042c30  mov     ecx, [eax]
0x10042c32  test    cl, 8
0x10042c35  jnz     short loc_10042C5E
0x10042c37  cmp     byte ptr [esi+50h], 0
0x10042c3b  jnz     short loc_10042C5E
0x10042c3d  mov     eax, [esi+0Ch]
0x10042c40  and     cl, 0FBh
0x10042c43  or      cl, 3
0x10042c46  shl     eax, 8
0x10042c49  movzx   ecx, cl
0x10042c4c  or      ecx, eax
0x10042c4e  mov     eax, [ebp+var_4]
0x10042c51  mov     [eax], ecx
0x10042c53  mov     [esi+18h], edi
0x10042c56  add     edi, 7
0x10042c59  lea     edi, [esi+edi*4]
0x10042c5c  jmp     short loc_10042CC7
0x10042c5e  push    ebx
0x10042c5f  push    1; struct Err *
0x10042c61  mov     ecx, offset ?Sys@@3VSystem@@A; lpParameter
0x10042c66  call    ?AllocatePages@System@@QAEPAVPage@@KAAVErr@@@Z; System::AllocatePages(ulong,Err &)
0x10042c6b  test    byte ptr [ebx], 8
0x10042c6e  mov     ecx, eax; void *
0x10042c70  mov     [ebp+var_C], ecx
0x10042c73  jz      short loc_10042C98
0x10042c75  mov     eax, [ebp+var_8]
0x10042c78  mov     ecx, [ebp+arg_4]; this
0x10042c7b  push    esi; struct PageDesc *
0x10042c7c  push    eax; int
0x10042c7d  call    ?RemovePageDesc@Transaction@@QAEXHPAVPageDesc@@@Z; Transaction::RemovePageDesc(int,PageDesc *)
0x10042c82  push    0
0x10042c84  push    ebx
0x10042c85  push    [ebp+arg_4]
0x10042c88  mov     ecx, esi
0x10042c8a  call    ?DecrementLock@PageDesc@@QAEXPAVTransaction@@AAVErr@@W4UnlockType@@@Z; PageDesc::DecrementLock(Transaction *,Err &,UnlockType)
0x10042c8f  pop     edi
0x10042c90  pop     esi
0x10042c91  pop     ebx
0x10042c92  mov     esp, ebp
0x10042c94  pop     ebp
0x10042c95  retn    10h
0x10042c98  mov     eax, [ebp+var_4]
0x10042c9b  mov     eax, [eax]
0x10042c9d  and     eax, 0FFFFFF00h
0x10042ca2  push    eax; Src
0x10042ca3  call    ??4Page@@QAEABV0@ABV0@@Z; Page::operator=(Page const &)
0x10042ca8  mov     ecx, [ebp+var_4]
0x10042cab  mov     eax, [ecx]
0x10042cad  and     eax, 0FFFFFFF8h
0x10042cb0  xor     eax, [ebp+var_C]
0x10042cb3  movzx   ecx, al
0x10042cb6  mov     eax, [ebp+var_4]
0x10042cb9  xor     ecx, [ebp+var_C]
0x10042cbc  mov     [eax], ecx
0x10042cbe  mov     [esi+18h], edi
0x10042cc1  add     edi, 7
0x10042cc4  lea     edi, [esi+edi*4]
0x10042cc7  push    0
0x10042cc9  push    ebx
0x10042cca  push    [ebp+arg_4]
0x10042ccd  mov     ecx, esi
0x10042ccf  call    ?DecrementLock@PageDesc@@QAEXPAVTransaction@@AAVErr@@W4UnlockType@@@Z; PageDesc::DecrementLock(Transaction *,Err &,UnlockType)
0x10042cd4  test    byte ptr [edi], 7
0x10042cd7  jz      short loc_10042CE9
0x10042cd9  push    ebx; struct Err *
0x10042cda  push    2; char
0x10042cdc  push    edi; struct PageVersion *
0x10042cdd  mov     ecx, esi; this
0x10042cdf  call    ?WireCurrentPage@PageDesc@@QAEXAAVPageVersion@@IAAVErr@@@Z; PageDesc::WireCurrentPage(PageVersion &,uint,Err &)
0x10042ce4  test    byte ptr [ebx], 8
0x10042ce7  jnz     short loc_10042D11
0x10042ce9  mov     ecx, [ebp+arg_0]
0x10042cec  mov     eax, [edi]
0x10042cee  and     eax, 0FFFFFF00h
0x10042cf3  mov     [ecx+4], eax
0x10042cf6  mov     eax, [ecx]
0x10042cf8  cmp     eax, esi
0x10042cfa  jz      short loc_10042D11
0x10042cfc  test    eax, eax
0x10042cfe  jz      short loc_10042D04
0x10042d00  dec     word ptr [eax+4Ch]
0x10042d04  mov     [ecx], esi
0x10042d06  inc     word ptr [esi+4Ch]
0x10042d0a  mov     dword ptr [ecx+8], 0
0x10042d11  pop     edi
0x10042d12  pop     esi
0x10042d13  pop     ebx
0x10042d14  mov     esp, ebp
0x10042d16  pop     ebp
0x10042d17  retn    10h
```
