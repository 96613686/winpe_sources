# PageDesc::Commit(Transaction *,int,Err &)

- ea: `0x10042520`
- end: `0x100425ed`
- name: `?Commit@PageDesc@@QAEXPAVTransaction@@HAAVErr@@@Z`
- size: `205`
- prototype: `void __thiscall(PageDesc *__hidden this, struct Transaction *, int, struct Err *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x10024070`
- `0x1003cde0`
- `0x10042e50`

## callees

- `0x10012dd0`
- `0x10041c70`
- `0x10042520`
- `0x1005d5a0`
- `0x1005d5f0`

## pseudocode

```c
void __thiscall PageDesc::Commit(PageDesc *this, struct Transaction *a2, int a3, struct Err *a4)
{
  int v5; // ebx
  Transaction *v6; // ecx
  Collection *v7; // esi
  unsigned int v8; // eax
  struct Err *v9; // edx
  struct Database *v10; // [esp-8h] [ebp-10h]

  v5 = *((_DWORD *)this + 6);
  if ( v5 == a3 )
  {
    v6 = a2;
    if ( (*((_BYTE *)this + 82) & 4) != 0 )
    {
      Transaction::RemovePageDesc(a2, v5, this);
      v6 = a2;
    }
    if ( v5 == 1 )
    {
      if ( (*((_BYTE *)this + 82) & 2) != 0 )
      {
LABEL_12:
        ++*((_DWORD *)this + 16);
        if ( *((_BYTE *)this + 80) == 2 )
          *((_BYTE *)this + 80) = 1;
        if ( !*((_WORD *)this + 39) )
          *((_DWORD *)this + 15) = 0;
        goto LABEL_18;
      }
      v7 = (Collection *)(*((_DWORD *)this + 5) + 376);
      v8 = *(_DWORD *)(*((_DWORD *)this + 5) + 384);
      if ( v8 < *(_DWORD *)(*((_DWORD *)this + 5) + 380) )
      {
        v9 = a4;
      }
      else
      {
        Collection::Grow(v7, v8 + 1, a4);
        v9 = a4;
        if ( (*(_BYTE *)a4 & 8) != 0 )
          return;
      }
      *(_DWORD *)(*(_DWORD *)v7 + 4 * (*((_DWORD *)v7 + 2))++) = this;
      if ( (*(_BYTE *)v9 & 8) == 0 )
      {
        *((_BYTE *)this + 82) |= 2u;
        goto LABEL_12;
      }
    }
    else if ( (*((_BYTE *)this + 4 * v5 + 24) & 7) != 5
           || (Transaction::AddPageDesc(v6, v5 - 1, this, a4), (*(_BYTE *)a4 & 8) == 0) )
    {
LABEL_18:
      v10 = (struct Database *)*((_DWORD *)this + 5);
      --*((_DWORD *)this + 6);
      PageVersion::Discard((PageDesc *)((char *)this + 4 * v5 + 24), v10);
      *((_DWORD *)this + v5 + 6) = *((_DWORD *)this + v5 + 7);
    }
  }
}

```

## disassembly

```asm
0x10042520  mov     edi, edi
0x10042522  push    ebp
0x10042523  mov     ebp, esp
0x10042525  push    ebx
0x10042526  push    edi
0x10042527  mov     edi, ecx
0x10042529  mov     ebx, [edi+18h]
0x1004252c  cmp     ebx, [ebp+arg_4]
0x1004252f  jnz     loc_100425E7
0x10042535  test    byte ptr [edi+52h], 4
0x10042539  mov     ecx, [ebp+arg_0]; this
0x1004253c  jz      short loc_10042548
0x1004253e  push    edi; struct PageDesc *
0x1004253f  push    ebx; int
0x10042540  call    ?RemovePageDesc@Transaction@@QAEXHPAVPageDesc@@@Z; Transaction::RemovePageDesc(int,PageDesc *)
0x10042545  mov     ecx, [ebp+arg_0]; this
0x10042548  push    esi
0x10042549  cmp     ebx, 1
0x1004254c  jnz     short loc_100425AF
0x1004254e  test    byte ptr [edi+52h], 2
0x10042552  jnz     short loc_10042592
0x10042554  mov     esi, [edi+14h]
0x10042557  add     esi, 178h
0x1004255d  mov     eax, [esi+8]
0x10042560  cmp     eax, [esi+4]
0x10042563  jb      short loc_1004257B
0x10042565  push    [ebp+arg_8]; struct Err *
0x10042568  inc     eax
0x10042569  mov     ecx, esi; this
0x1004256b  push    eax; unsigned int
0x1004256c  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x10042571  mov     edx, [ebp+arg_8]
0x10042574  test    byte ptr [edx], 8
0x10042577  jnz     short loc_100425E6
0x10042579  jmp     short loc_1004257E
0x1004257b  mov     edx, [ebp+arg_8]
0x1004257e  mov     ecx, [esi+8]
0x10042581  mov     eax, [esi]
0x10042583  mov     [eax+ecx*4], edi
0x10042586  inc     dword ptr [esi+8]
0x10042589  test    byte ptr [edx], 8
0x1004258c  jnz     short loc_100425E6
0x1004258e  or      byte ptr [edi+52h], 2
0x10042592  inc     dword ptr [edi+40h]
0x10042595  cmp     byte ptr [edi+50h], 2
0x10042599  jnz     short loc_1004259F
0x1004259b  mov     byte ptr [edi+50h], 1
0x1004259f  cmp     word ptr [edi+4Eh], 0
0x100425a4  jnz     short loc_100425CD
0x100425a6  mov     dword ptr [edi+3Ch], 0
0x100425ad  jmp     short loc_100425CD
0x100425af  mov     eax, [edi+ebx*4+18h]
0x100425b3  and     eax, 7
0x100425b6  cmp     al, 5
0x100425b8  jnz     short loc_100425CD
0x100425ba  mov     esi, [ebp+arg_8]
0x100425bd  lea     eax, [ebx-1]
0x100425c0  push    esi; struct Err *
0x100425c1  push    edi; struct PageDesc *
0x100425c2  push    eax; int
0x100425c3  call    ?AddPageDesc@Transaction@@QAEXHPAVPageDesc@@AAVErr@@@Z; Transaction::AddPageDesc(int,PageDesc *,Err &)
0x100425c8  test    byte ptr [esi], 8
0x100425cb  jnz     short loc_100425E6
0x100425cd  push    dword ptr [edi+14h]; struct Database *
0x100425d0  dec     dword ptr [edi+18h]
0x100425d3  lea     eax, [ebx+6]
0x100425d6  lea     esi, [edi+eax*4]
0x100425d9  mov     ecx, esi; this
0x100425db  call    ?Discard@PageVersion@@QAEXAAVDatabase@@@Z; PageVersion::Discard(Database &)
0x100425e0  mov     eax, [edi+ebx*4+1Ch]
0x100425e4  mov     [esi], eax
0x100425e6  pop     esi
0x100425e7  pop     edi
0x100425e8  pop     ebx
0x100425e9  pop     ebp
0x100425ea  retn    0Ch
```
