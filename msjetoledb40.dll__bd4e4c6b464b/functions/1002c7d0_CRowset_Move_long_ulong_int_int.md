# CRowset::Move(long,ulong,int,int)

- ea: `0x1002c7d0`
- end: `0x1002c8ea`
- name: `?Move@CRowset@@IAGJJKHH@Z`
- size: `282`
- prototype: `int(CRowset *__hidden this, int, unsigned int, int, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1002db00`
- `0x100304b0`
- `0x10031650`

## callees

- `0x1001bdc0`
- `0x1002c7d0`

## import_xrefs

- `msjet40!__imp__JetGetBookmark@20` at `0x1002c8a8`
- `msjet40!__imp__JetGetBookmark@20` at `0x1002c8a8`
- `msjet40!__imp__JetMove@16` at `0x1002c7fe`
- `msjet40!__imp__JetMove@16` at `0x1002c824`
- `msjet40!__imp__JetMove@16` at `0x1002c7fe`
- `msjet40!__imp__JetMove@16` at `0x1002c824`

## pseudocode

```c
int __userpurge CRowset::Move@<eax>(
        int a1@<edx>,
        _DWORD *a2@<ecx>,
        CRowset *this,
        int a4,
        unsigned int a5,
        int a6,
        int a7)
{
  JET_SESID v9; // ebx
  JET_ERR v11; // eax
  int v12; // edi
  int v13; // ecx
  int v14; // edi
  JET_ERR Bookmark; // eax
  int v16; // [esp+0h] [ebp-10h]
  const struct _GUID *v17; // [esp+4h] [ebp-Ch]
  unsigned int pcbActual; // [esp+Ch] [ebp-4h] BYREF

  v9 = *(_DWORD *)(a2[14] + 16);
  if ( a2[29] == 4 )
    return 265926;
  v11 = JetMove(v9, a2[27], a1, 0);
  if ( v11 )
  {
    if ( v11 == -1603 )
    {
      if ( a1 >= 0 || (a2[24] & 4) != 0 || (v11 = JetMove(v9, a2[27], 0x80000000, 0), v11 >= 0) )
      {
        v13 = a2[24];
        if ( (v13 & 0x80u) == 0 )
          a2[24] = v13 | 4;
        v12 = 265926;
        if ( !v11 )
          return 265926;
      }
      else
      {
        v12 = 265926;
      }
    }
    else
    {
      v12 = -2147467259;
    }
    CExtError::SendJetErrortoOLEAuto(v12, *(char **)(a2[14] + 16), v11, (int)&IID_IRowset, v16, v17);
    return v12;
  }
  else
  {
    if ( a1 > 0 )
      a2[24] &= ~0x200u;
    if ( a5 == 1 && a2[33] )
    {
      v14 = 0;
      Bookmark = JetGetBookmark(*(_DWORD *)(a2[14] + 16), a2[27], a2 + 31, 4u, &pcbActual);
      if ( Bookmark < 0 )
      {
        if ( Bookmark == -1603 )
        {
          a2[31] = -1;
          return 265926;
        }
        return -2147467259;
      }
      return v14;
    }
    else
    {
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1002c7d0  mov     edi, edi
0x1002c7d2  push    ebp
0x1002c7d3  mov     ebp, esp
0x1002c7d5  push    ecx
0x1002c7d6  push    ebx
0x1002c7d7  push    esi; struct _GUID *
0x1002c7d8  mov     esi, ecx
0x1002c7da  push    edi; int
0x1002c7db  mov     edi, edx
0x1002c7dd  cmp     dword ptr [esi+74h], 4
0x1002c7e1  mov     eax, [esi+38h]
0x1002c7e4  mov     ebx, [eax+10h]
0x1002c7e7  jnz     short loc_1002C7F7
0x1002c7e9  pop     edi
0x1002c7ea  pop     esi
0x1002c7eb  mov     eax, 40EC6h
0x1002c7f0  pop     ebx
0x1002c7f1  mov     esp, ebp
0x1002c7f3  pop     ebp
0x1002c7f4  retn    0Ch
0x1002c7f7  push    0; grbit
0x1002c7f9  push    edi; cRow
0x1002c7fa  push    dword ptr [esi+6Ch]; tableid
0x1002c7fd  push    ebx; sesid
0x1002c7fe  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1002c804  test    eax, eax
0x1002c806  jz      short loc_1002C879
0x1002c808  cmp     eax, 0FFFFF9BDh
0x1002c80d  jnz     short loc_1002C856
0x1002c80f  test    edi, edi
0x1002c811  jns     short loc_1002C835
0x1002c813  test    byte ptr [esi+60h], 4
0x1002c817  jnz     short loc_1002C835
0x1002c819  push    0; grbit
0x1002c81b  push    80000000h; cRow
0x1002c820  push    dword ptr [esi+6Ch]; tableid
0x1002c823  push    ebx; sesid
0x1002c824  call    ds:__imp__JetMove@16; JetMove(x,x,x,x)
0x1002c82a  test    eax, eax
0x1002c82c  jns     short loc_1002C835
0x1002c82e  mov     edi, 40EC6h
0x1002c833  jmp     short loc_1002C85B
0x1002c835  mov     ecx, [esi+60h]
0x1002c838  test    cl, cl
0x1002c83a  js      short loc_1002C842
0x1002c83c  or      ecx, 4
0x1002c83f  mov     [esi+60h], ecx
0x1002c842  mov     edi, 40EC6h
0x1002c847  test    eax, eax
0x1002c849  jnz     short loc_1002C85B
0x1002c84b  mov     eax, edi
0x1002c84d  pop     edi
0x1002c84e  pop     esi
0x1002c84f  pop     ebx
0x1002c850  mov     esp, ebp
0x1002c852  pop     ebp
0x1002c853  retn    0Ch
0x1002c856  mov     edi, 80004005h
0x1002c85b  mov     ecx, [esi+38h]
0x1002c85e  mov     edx, edi
0x1002c860  push    offset _IID_IRowset; int
0x1002c865  push    eax; unsigned int
0x1002c866  mov     ecx, [ecx+10h]
0x1002c869  call    ?SendJetErrortoOLEAuto@CExtError@@SGJKJJABU_GUID@@@Z; CExtError::SendJetErrortoOLEAuto(ulong,long,long,_GUID const &)
0x1002c86e  mov     eax, edi
0x1002c870  pop     edi
0x1002c871  pop     esi
0x1002c872  pop     ebx
0x1002c873  mov     esp, ebp
0x1002c875  pop     ebp
0x1002c876  retn    0Ch
0x1002c879  test    edi, edi
0x1002c87b  jle     short loc_1002C884
0x1002c87d  and     dword ptr [esi+60h], 0FFFFFDFFh
0x1002c884  cmp     [ebp+arg_8], 1
0x1002c888  jnz     short loc_1002C8DF
0x1002c88a  cmp     dword ptr [esi+84h], 0
0x1002c891  jz      short loc_1002C8DF
0x1002c893  mov     eax, [esi+38h]
0x1002c896  lea     ecx, [ebp+pcbActual]
0x1002c899  push    ecx; pcbActual
0x1002c89a  push    4; cbMax
0x1002c89c  lea     ebx, [esi+7Ch]
0x1002c89f  xor     edi, edi
0x1002c8a1  push    ebx; pvBookmark
0x1002c8a2  push    dword ptr [esi+6Ch]; tableid
0x1002c8a5  push    dword ptr [eax+10h]; sesid
0x1002c8a8  call    ds:__imp__JetGetBookmark@20; JetGetBookmark(x,x,x,x,x)
0x1002c8ae  test    eax, eax
0x1002c8b0  jns     short loc_1002C8D4
0x1002c8b2  cmp     eax, 0FFFFF9BDh
0x1002c8b7  jnz     short loc_1002C8CF
0x1002c8b9  mov     edi, 40EC6h
0x1002c8be  mov     dword ptr [ebx], 0FFFFFFFFh
0x1002c8c4  mov     eax, edi
0x1002c8c6  pop     edi
0x1002c8c7  pop     esi
0x1002c8c8  pop     ebx
0x1002c8c9  mov     esp, ebp
0x1002c8cb  pop     ebp
0x1002c8cc  retn    0Ch
0x1002c8cf  mov     edi, 80004005h
0x1002c8d4  mov     eax, edi
0x1002c8d6  pop     edi
0x1002c8d7  pop     esi
0x1002c8d8  pop     ebx
0x1002c8d9  mov     esp, ebp
0x1002c8db  pop     ebp
0x1002c8dc  retn    0Ch
0x1002c8df  pop     edi
0x1002c8e0  pop     esi
0x1002c8e1  xor     eax, eax
0x1002c8e3  pop     ebx
0x1002c8e4  mov     esp, ebp
0x1002c8e6  pop     ebp
0x1002c8e7  retn    0Ch
```
