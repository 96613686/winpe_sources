# PageDesc::DontReadPage(PageRef &,Transaction *,Err &)

- ea: `0x10042d20`
- end: `0x10042e40`
- name: `?DontReadPage@PageDesc@@QAEXAAVPageRef@@PAVTransaction@@AAVErr@@@Z`
- size: `288`
- prototype: `void __thiscall(PageDesc *__hidden this, struct PageRef *, struct Transaction *, struct Err *)`
- caller_count: `15`
- callee_count: `6`
- tags: ``

## callers

- `0x100105a0`
- `0x10011540`
- `0x1001c8c0`
- `0x1001ccc0`
- `0x10021720`
- `0x100237e0`
- `0x10031300`
- `0x1003c9a0`
- `0x1003f550`
- `0x10046c70`
- `0x10046de0`
- `0x100475f0`
- `0x10047800`
- `0x10052e30`
- `0x1005c7e0`

## callees

- `0x10012dd0`
- `0x10025ee0`
- `0x10041c70`
- `0x10042d20`
- `0x100430f0`
- `0x1004e980`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10042d2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10042d2f`

## pseudocode

```c
void __thiscall PageDesc::DontReadPage(PageDesc *this, struct PageRef *a2, struct Transaction *a3, struct Err *a4)
{
  int v5; // edi
  int v6; // ecx
  struct Err *v7; // ebx
  char v8; // al
  PageDesc *v9; // edi
  int v10; // ebx
  unsigned int v11; // eax
  int i; // ecx
  int v13; // eax
  unsigned int Pages; // eax
  unsigned int v15; // eax
  int v16; // eax

  v5 = *(_DWORD *)a3;
  *((_DWORD *)this + 18) = GetTickCount();
  PageDesc::RemovePageFromCache(this);
  if ( v5 )
  {
    v10 = *((_DWORD *)a3 + 9) + 56 * v5;
    v11 = *(_DWORD *)(v10 - 48);
    if ( v11 < *(_DWORD *)(v10 - 52)
      || (Collection::Grow((Collection *)(v10 - 56), v11 + 1, a4), (*(_BYTE *)a4 & 8) == 0) )
    {
      *(_DWORD *)(*(_DWORD *)(v10 - 56) + 4 * (*(_DWORD *)(v10 - 48))++) = this;
    }
    v7 = a4;
    if ( (*(_BYTE *)a4 & 8) != 0 )
      return;
    for ( i = 0; i <= v5; ++i )
      *((_DWORD *)this + i + 7) = *((_DWORD *)this + i + 7) & 0xF0 | 5;
    *((_DWORD *)this + 6) = v5;
    v9 = (PageDesc *)((char *)this + 4 * v5);
    *((_DWORD *)this + 15) = a3;
    v8 = 2;
  }
  else
  {
    if ( (*((_BYTE *)this + 82) & 1) == 0 )
    {
      Err::SetError(a4, -1054, v6);
      return;
    }
    v7 = a4;
    v8 = 1;
    v9 = this;
  }
  *((_BYTE *)this + 80) = v8;
  v13 = *((_DWORD *)v9 + 7);
  if ( (v13 & 7) != 0 )
  {
    PageVersion::Discard((PageDesc *)((char *)v9 + 28), *((struct Database **)this + 5));
    Pages = (unsigned int)System::AllocatePages((struct QMsg *)&Sys, (struct Err *)1);
    if ( (*(_BYTE *)v7 & 8) != 0 )
      return;
    v13 = Pages ^ (unsigned __int8)(Pages ^ *((_BYTE *)v9 + 28) & 0xF8);
  }
  v15 = v13 & 0xFFFFFFF7;
  *((_DWORD *)v9 + 7) = v15;
  *((_DWORD *)a2 + 1) = v15 & 0xFFFFFF00;
  v16 = *(_DWORD *)a2;
  if ( *(PageDesc **)a2 != this )
  {
    if ( v16 )
      --*(_WORD *)(v16 + 76);
    *(_DWORD *)a2 = this;
    ++*((_WORD *)this + 38);
    *((_DWORD *)a2 + 2) = 0;
  }
}

```

## disassembly

```asm
0x10042d20  mov     edi, edi
0x10042d22  push    ebp
0x10042d23  mov     ebp, esp
0x10042d25  push    ebx
0x10042d26  mov     ebx, [ebp+arg_4]
0x10042d29  push    esi
0x10042d2a  push    edi
0x10042d2b  mov     esi, ecx
0x10042d2d  mov     edi, [ebx]
0x10042d2f  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10042d35  mov     ecx, esi; this
0x10042d37  mov     [esi+48h], eax
0x10042d3a  call    ?RemovePageFromCache@PageDesc@@QAEXXZ; PageDesc::RemovePageFromCache(void)
0x10042d3f  test    edi, edi
0x10042d41  jnz     short loc_10042D6A
0x10042d43  test    byte ptr [esi+52h], 1
0x10042d47  jz      short loc_10042D55
0x10042d49  mov     ebx, [ebp+arg_8]
0x10042d4c  mov     al, 1
0x10042d4e  mov     edi, esi
0x10042d50  jmp     loc_10042DD7
0x10042d55  push    ecx
0x10042d56  mov     ecx, [ebp+arg_8]
0x10042d59  push    0FFFFFBE2h
0x10042d5e  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10042d63  pop     edi
0x10042d64  pop     esi
0x10042d65  pop     ebx
0x10042d66  pop     ebp
0x10042d67  retn    0Ch
0x10042d6a  mov     eax, [ebx+24h]
0x10042d6d  lea     ecx, ds:0[edi*8]
0x10042d74  sub     ecx, edi
0x10042d76  lea     ebx, [eax+ecx*8]
0x10042d79  mov     eax, [ebx-30h]
0x10042d7c  cmp     eax, [ebx-34h]
0x10042d7f  jb      short loc_10042D96
0x10042d81  push    [ebp+arg_8]; struct Err *
0x10042d84  inc     eax
0x10042d85  lea     ecx, [ebx-38h]; this
0x10042d88  push    eax; unsigned int
0x10042d89  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x10042d8e  mov     eax, [ebp+arg_8]
0x10042d91  test    byte ptr [eax], 8
0x10042d94  jnz     short loc_10042DA2
0x10042d96  mov     ecx, [ebx-30h]
0x10042d99  mov     eax, [ebx-38h]
0x10042d9c  mov     [eax+ecx*4], esi
0x10042d9f  inc     dword ptr [ebx-30h]
0x10042da2  mov     ebx, [ebp+arg_8]
0x10042da5  test    byte ptr [ebx], 8
0x10042da8  jnz     loc_10042E39
0x10042dae  xor     ecx, ecx
0x10042db0  test    edi, edi
0x10042db2  js      short loc_10042DC9
0x10042db4  mov     eax, [esi+ecx*4+1Ch]
0x10042db8  and     eax, 0F0h
0x10042dbd  or      eax, 5
0x10042dc0  mov     [esi+ecx*4+1Ch], eax
0x10042dc4  inc     ecx
0x10042dc5  cmp     ecx, edi
0x10042dc7  jle     short loc_10042DB4
0x10042dc9  mov     eax, [ebp+arg_4]
0x10042dcc  mov     [esi+18h], edi
0x10042dcf  lea     edi, [esi+edi*4]
0x10042dd2  mov     [esi+3Ch], eax
0x10042dd5  mov     al, 2
0x10042dd7  mov     [esi+50h], al
0x10042dda  mov     eax, [edi+1Ch]
0x10042ddd  test    al, 7
0x10042ddf  jz      short loc_10042E0D
0x10042de1  push    dword ptr [esi+14h]; struct Database *
0x10042de4  lea     ecx, [edi+1Ch]; this
0x10042de7  call    ?Discard@PageVersion@@QAEXAAVDatabase@@@Z; PageVersion::Discard(Database &)
0x10042dec  push    ebx
0x10042ded  push    1; struct Err *
0x10042def  mov     ecx, offset ?Sys@@3VSystem@@A; lpParameter
0x10042df4  call    ?AllocatePages@System@@QAEPAVPage@@KAAVErr@@@Z; System::AllocatePages(ulong,Err &)
0x10042df9  test    byte ptr [ebx], 8
0x10042dfc  mov     edx, eax
0x10042dfe  jnz     short loc_10042E39
0x10042e00  mov     ecx, [edi+1Ch]
0x10042e03  and     ecx, 0FFFFFFF8h
0x10042e06  xor     ecx, edx
0x10042e08  movzx   eax, cl
0x10042e0b  xor     eax, edx
0x10042e0d  mov     ecx, [ebp+arg_0]
0x10042e10  and     eax, 0FFFFFFF7h
0x10042e13  mov     [edi+1Ch], eax
0x10042e16  and     eax, 0FFFFFF00h
0x10042e1b  mov     [ecx+4], eax
0x10042e1e  mov     eax, [ecx]
0x10042e20  cmp     eax, esi
0x10042e22  jz      short loc_10042E39
0x10042e24  test    eax, eax
0x10042e26  jz      short loc_10042E2C
0x10042e28  dec     word ptr [eax+4Ch]
0x10042e2c  mov     [ecx], esi
0x10042e2e  inc     word ptr [esi+4Ch]
0x10042e32  mov     dword ptr [ecx+8], 0
0x10042e39  pop     edi
0x10042e3a  pop     esi
0x10042e3b  pop     ebx
0x10042e3c  pop     ebp
0x10042e3d  retn    0Ch
```
