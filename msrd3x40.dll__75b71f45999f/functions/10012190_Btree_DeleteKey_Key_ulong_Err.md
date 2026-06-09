# Btree::DeleteKey(Key &,ulong,Err &)

- ea: `0x10012190`
- end: `0x100125d6`
- name: `?DeleteKey@Btree@@QAEXAAVKey@@KAAVErr@@@Z`
- size: `1094`
- prototype: `void __thiscall(Btree *__hidden this, struct Key *, unsigned int, struct Err *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, installer_update`

## callers

- `0x1001d640`

## callees

- `0x1000f890`
- `0x10010580`
- `0x10012190`
- `0x100125e0`
- `0x10023730`
- `0x10031d70`
- `0x10031ef0`
- `0x10031f50`
- `0x10032190`
- `0x100326a0`
- `0x100399c0`
- `0x100471e0`
- `0x100473e0`
- `0x10047a60`
- `0x1005d1d0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall Btree::DeleteKey(struct Transaction **this, struct Key *a2, unsigned int a3, void **a4)
{
  int v4; // ebx
  unsigned int v5; // edi
  struct Transaction *v6; // eax
  unsigned __int8 *ByteAlloc; // ecx
  struct QuickKey *v8; // eax
  int v9; // eax
  unsigned int v10; // ecx
  int v11; // eax
  unsigned int v12; // eax
  struct Transaction **v13; // edi
  int v14; // ecx
  unsigned int v15; // eax
  int v16; // ecx
  unsigned int v17; // ebx
  int v18; // eax
  unsigned int v19; // edx
  unsigned __int8 v20; // al
  int v22; // eax
  int v23; // edi
  unsigned int Bookmark; // eax
  int v25; // ecx
  bool v26; // zf
  struct Transaction **v27; // ebx
  int v28; // eax
  int v29; // ecx
  int v30; // ecx
  int v31; // eax
  int v32; // [esp+10h] [ebp-7Ch] BYREF
  int v33; // [esp+14h] [ebp-78h]
  unsigned int v34; // [esp+1Ch] [ebp-70h] BYREF
  int v35; // [esp+20h] [ebp-6Ch]
  int v36; // [esp+24h] [ebp-68h] BYREF
  int v37; // [esp+28h] [ebp-64h]
  struct QuickKey *v38; // [esp+30h] [ebp-5Ch]
  unsigned int v39; // [esp+34h] [ebp-58h] BYREF
  struct Transaction **v40; // [esp+38h] [ebp-54h]
  unsigned int v41; // [esp+3Ch] [ebp-50h]
  char v42[60]; // [esp+40h] [ebp-4Ch] BYREF
  int v43; // [esp+88h] [ebp-4h]

  v40 = this;
  v4 = 0;
  v38 = a2;
  v36 = 0;
  v37 = 0;
  v43 = 1;
  v32 = 0;
  v33 = 0;
  v5 = 0;
  v41 = 0;
  v39 = 0;
  v6 = this[10];
  if ( v6 )
    --*((_WORD *)v6 + 38);
  this[11] = 0;
  this[10] = 0;
  if ( (unsigned int)(*(_DWORD *)v38 + 4) > *((_DWORD *)v38 + 3) )
    ByteAlloc = Key::NextByteAlloc(v38, 4u, (struct Err *)a4);
  else
    ByteAlloc = (unsigned __int8 *)(*(_DWORD *)v38 + *((_DWORD *)v38 + 1));
  if ( (*(_BYTE *)a4 & 8) != 0 )
  {
    v8 = v38;
  }
  else
  {
    *(_DWORD *)ByteAlloc = _byteswap_ulong(a3);
    v8 = v38;
    *(_DWORD *)v38 += 4;
  }
  if ( (*(_BYTE *)a4 & 8) != 0 )
  {
    v9 = 0;
  }
  else
  {
    v9 = Btree::DescendToLeaf(v40, v8, v42, &v36, &v36, 2, a4);
    v4 = v37;
  }
  if ( (*(_BYTE *)a4 & 8) != 0 )
    goto LABEL_70;
  while ( 1 )
  {
    v35 = v9 - 1;
    if ( *(_WORD *)v4 == 259 )
    {
      if ( v5 != -2 )
      {
        v11 = IndexPage::Remove(&v36, v5, ByteAlloc);
        v41 = v11;
        v39 = v11;
        goto LABEL_25;
      }
      *(_DWORD *)(v4 + 16) = 0;
      v18 = *(unsigned __int16 *)(v4 + 2);
      v19 = (unsigned int)(1807 - v18) >> 3;
      v20 = *(_BYTE *)(v19 + v4 + 22) & byte_10003908[(1807 - v18) & 7];
      if ( !v20 )
      {
        while ( v19-- )
        {
          v20 = *(_BYTE *)(v4 + v19 + 22);
          if ( v20 )
            goto LABEL_42;
        }
LABEL_46:
        v11 = 1;
        v41 = 1;
        v39 = 1;
        goto LABEL_25;
      }
LABEL_42:
      v22 = (unsigned __int8)byte_10003708[v20];
      v23 = v22 + 8 * v19;
      if ( v23 == -1 )
        goto LABEL_46;
      Bookmark = IndexPage::GetBookmark((IndexPage *)&v36, v22 + 8 * v19, (struct Err *)a4);
      v26 = (*(_BYTE *)a4 & 8) == 0;
      v34 = Bookmark;
      if ( v26 )
      {
        IndexPage::Remove(&v36, v23, v25);
        if ( (*(_BYTE *)a4 & 8) == 0 )
        {
          *(_DWORD *)(v4 + 16) = v34;
          v11 = 0;
          v41 = 0;
          v39 = 0;
          goto LABEL_25;
        }
      }
      goto LABEL_24;
    }
    if ( *(_WORD *)v4 != 260 )
      goto LABEL_24;
    v10 = IndexPage::Find((IndexPage *)&v36, v38, (enum IdxStatus *)&v39);
    v11 = v39;
    v41 = v39;
    if ( v39 )
    {
      if ( (int)*a4 >= 8 )
        goto LABEL_25;
      if ( ((unsigned int)*a4 & 0xFFFFFFFE) != 0 )
      {
        if ( a4[3] )
          operator delete[](a4[3]);
        if ( a4[4] )
          operator delete[](a4[4]);
      }
      *a4 = (void *)8;
      a4[1] = (void *)-1601;
      a4[2] = 0;
      a4[3] = 0;
      a4[4] = 0;
LABEL_24:
      v11 = v41;
      goto LABEL_25;
    }
    v11 = IndexPage::Remove(&v36, v10, v10);
    v41 = v11;
    v39 = v11;
LABEL_25:
    if ( (*(_BYTE *)a4 & 8) != 0 || v11 != 1 )
      goto LABEL_68;
    v12 = *(_DWORD *)(v4 + 8);
    v13 = v40;
    if ( v12 )
    {
      Database::ReadPageForUpdate(*((Database **)*v40 + 2), (struct PageRef *)&v32, v12, a4, *v40, 0);
      if ( (*(_BYTE *)a4 & 8) != 0 )
        goto LABEL_68;
      v14 = v32;
      *(_DWORD *)(v32 + 4 * *(_DWORD *)(v32 + 24) + 28) |= 8u;
      ++*(_DWORD *)(v14 + 64);
      *(_DWORD *)(v14 + 4 * *(_DWORD *)(v14 + 24) + 28) = *(_DWORD *)(v14 + 4 * *(_DWORD *)(v14 + 24) + 28) & 0xFFFFFF0F
                                                        | 0x40;
      if ( (*(_BYTE *)a4 & 8) != 0 )
        goto LABEL_68;
      *(_DWORD *)(v33 + 12) = *(_DWORD *)(v4 + 12);
    }
    v15 = *(_DWORD *)(v4 + 12);
    if ( v15 )
    {
      Database::ReadPageForUpdate(*((Database **)*v13 + 2), (struct PageRef *)&v32, v15, a4, *v13, 0);
      if ( (*(_BYTE *)a4 & 8) != 0 )
        goto LABEL_68;
      v16 = v32;
      *(_DWORD *)(v32 + 4 * *(_DWORD *)(v32 + 24) + 28) |= 8u;
      ++*(_DWORD *)(v16 + 64);
      *(_DWORD *)(v16 + 4 * *(_DWORD *)(v16 + 24) + 28) = *(_DWORD *)(v16 + 4 * *(_DWORD *)(v16 + 24) + 28) & 0xFFFFFF0F
                                                        | 0x40;
      if ( (*(_BYTE *)a4 & 8) != 0 )
        goto LABEL_68;
      *(_DWORD *)(v33 + 8) = *(_DWORD *)(v4 + 8);
    }
    if ( !v35 )
      break;
    if ( v36 )
      v17 = *(_DWORD *)(v36 + 12);
    else
      v17 = 0;
    AbstractSpacemap::Setup(v13 + 27, 1, a4);
    if ( (*(_BYTE *)a4 & 8) == 0
      && AbstractSpacemap::GetBitmap(v13 + 27, v17, 2, a4) == 1
      && (*((_BYTE *)v13[31] + ((v17 - (unsigned int)v13[33]) >> 3))
        & *((_BYTE *)&Bitmap::ThisBit + ((v17 - (_DWORD)v13[33]) & 7))) != 0 )
    {
      Bitmap::Clear((Bitmap *)(v13 + 31), v17, (struct Err *)a4);
      v27 = v40;
      AbstractSpacemap::UpdateBitmap((AbstractSpacemap *)(v40 + 27));
    }
    else
    {
      v27 = v40;
    }
    if ( (*(_BYTE *)a4 & 8) == 0 )
    {
      v28 = v36 ? *(_DWORD *)(v36 + 12) : 0;
      Transaction::FreePage(*v27, v28, 1, a4);
      if ( (*(_BYTE *)a4 & 8) == 0 )
      {
        Database::ReadPageForUpdate(
          *((Database **)*v27 + 2),
          (struct PageRef *)&v36,
          *(_DWORD *)&v42[4 * v35 - 4],
          a4,
          *v27,
          0);
        v4 = v37;
        if ( (*(_BYTE *)a4 & 8) != 0 )
        {
          v5 = 0;
        }
        else
        {
          v5 = IndexPage::Find((IndexPage *)&v36, v38, (enum IdxStatus *)&v34);
          if ( v5 == -2 && !*(_DWORD *)(v4 + 16) )
            v5 = IndexPage::Last((IndexPage *)&v36);
          v29 = v36;
          *(_DWORD *)(v36 + 4 * *(_DWORD *)(v36 + 24) + 28) |= 8u;
          ++*(_DWORD *)(v29 + 64);
          v30 = v29 + 4 * *(_DWORD *)(v29 + 24);
          v31 = *(_DWORD *)(v30 + 28);
          ByteAlloc = (unsigned __int8 *)(v30 + 28);
          *(_DWORD *)ByteAlloc = v31 & 0xFFFFFF0F | 0x40;
        }
        v9 = v35;
        if ( (*(_BYTE *)a4 & 8) == 0 )
          continue;
      }
    }
    goto LABEL_68;
  }
  IndexPage::Initialize((IndexPage *)&v36, 0x104u, *(_DWORD *)(v4 + 4), 0, 0, (struct Err *)a4);
  *(_BYTE *)(v4 + 21) = 0;
LABEL_68:
  if ( v32 )
    --*(_WORD *)(v32 + 76);
LABEL_70:
  if ( v36 )
    --*(_WORD *)(v36 + 76);
}

```

## disassembly

```asm
0x10012190  mov     edi, edi
0x10012192  push    ebp
0x10012193  mov     ebp, esp
0x10012195  push    0FFFFFFFFh
0x10012197  push    offset ?DeleteKey@Btree@@QAEXAAVKey@@KAAVErr@@@Z_SEH
0x1001219c  mov     eax, large fs:0
0x100121a2  push    eax
0x100121a3  sub     esp, 70h
0x100121a6  mov     eax, ___security_cookie
0x100121ab  xor     eax, ebp
0x100121ad  mov     [ebp+var_10], eax
0x100121b0  push    ebx
0x100121b1  push    esi
0x100121b2  push    edi
0x100121b3  push    eax
0x100121b4  lea     eax, [ebp+var_C]
0x100121b7  mov     large fs:0, eax
0x100121bd  mov     [ebp+var_54], ecx
0x100121c0  mov     eax, [ebp+arg_0]
0x100121c3  xor     ebx, ebx
0x100121c5  mov     esi, [ebp+arg_8]
0x100121c8  mov     [ebp+var_5C], eax
0x100121cb  mov     [ebp+var_68], 0
0x100121d2  mov     [ebp+var_64], ebx
0x100121d5  xor     eax, eax
0x100121d7  mov     [ebp+var_4], ebx
0x100121da  mov     [ebp+var_7C], eax
0x100121dd  mov     [ebp+var_78], eax
0x100121e0  mov     byte ptr [ebp+var_4], 1
0x100121e4  xor     edi, edi
0x100121e6  mov     [ebp+var_50], eax
0x100121e9  mov     [ebp+var_58], eax
0x100121ec  mov     eax, [ecx+28h]
0x100121ef  test    eax, eax
0x100121f1  jz      short loc_100121F7
0x100121f3  dec     word ptr [eax+4Ch]
0x100121f7  mov     [ecx+2Ch], edi
0x100121fa  mov     [ecx+28h], edi
0x100121fd  mov     ecx, [ebp+var_5C]; this
0x10012200  mov     edx, [ecx]
0x10012202  lea     eax, [edx+4]
0x10012205  cmp     eax, [ecx+0Ch]
0x10012208  ja      short loc_10012211
0x1001220a  mov     ecx, [ecx+4]
0x1001220d  add     ecx, edx
0x1001220f  jmp     short loc_1001221B
0x10012211  push    esi; struct Err *
0x10012212  push    4; unsigned int
0x10012214  call    ?NextByteAlloc@Key@@AAEPAEIAAVErr@@@Z; Key::NextByteAlloc(uint,Err &)
0x10012219  mov     ecx, eax
0x1001221b  test    byte ptr [esi], 8
0x1001221e  jnz     short loc_1001222F
0x10012220  mov     eax, [ebp+arg_4]
0x10012223  bswap   eax
0x10012225  mov     [ecx], eax
0x10012227  mov     eax, [ebp+var_5C]
0x1001222a  add     dword ptr [eax], 4
0x1001222d  jmp     short loc_10012232
0x1001222f  mov     eax, [ebp+var_5C]
0x10012232  test    byte ptr [esi], 8
0x10012235  jnz     short loc_10012251
0x10012237  push    esi
0x10012238  push    2
0x1001223a  lea     ecx, [ebp+var_68]
0x1001223d  push    ecx
0x1001223e  push    ecx
0x1001223f  lea     ecx, [ebp+var_4C]
0x10012242  push    ecx
0x10012243  mov     ecx, [ebp+var_54]
0x10012246  push    eax
0x10012247  call    ?DescendToLeaf@Btree@@AAEIABVQuickKey@@PAKIAAVIndexPage@@W4BTUpd@@AAVErr@@@Z; Btree::DescendToLeaf(QuickKey const &,ulong *,uint,IndexPage &,BTUpd,Err &)
0x1001224c  mov     ebx, [ebp+var_64]
0x1001224f  jmp     short loc_10012253
0x10012251  xor     eax, eax
0x10012253  test    byte ptr [esi], 8
0x10012256  jnz     loc_100125AD
0x1001225c  nop     dword ptr [eax+00h]
0x10012260  dec     eax
0x10012261  mov     [ebp+var_6C], eax
0x10012264  movzx   eax, word ptr [ebx]
0x10012267  sub     eax, 103h
0x1001226c  jz      loc_100123D8
0x10012272  sub     eax, 1
0x10012275  jnz     short loc_100122F5
0x10012277  lea     eax, [ebp+var_58]
0x1001227a  push    eax; enum IdxStatus *
0x1001227b  push    [ebp+var_5C]; struct QuickKey *
0x1001227e  lea     ecx, [ebp+var_68]; this
0x10012281  call    ?Find@IndexPage@@QBEIABVQuickKey@@AAW4IdxStatus@@@Z; IndexPage::Find(QuickKey const &,IdxStatus &)
0x10012286  mov     ecx, eax
0x10012288  mov     eax, [ebp+var_58]
0x1001228b  mov     [ebp+var_50], eax
0x1001228e  test    eax, eax
0x10012290  jnz     short loc_100122A4
0x10012292  push    ecx
0x10012293  push    ecx
0x10012294  lea     ecx, [ebp+var_68]
0x10012297  call    ?Remove@IndexPage@@QAE?AW4IdxStatus@@IAAVErr@@@Z; IndexPage::Remove(uint,Err &)
0x1001229c  mov     [ebp+var_50], eax
0x1001229f  mov     [ebp+var_58], eax
0x100122a2  jmp     short loc_100122F8
0x100122a4  mov     ecx, [esi]
0x100122a6  cmp     ecx, 8
0x100122a9  jge     short loc_100122F8
0x100122ab  test    ecx, 0FFFFFFFEh
0x100122b1  jz      short loc_100122D3
0x100122b3  mov     eax, [esi+0Ch]
0x100122b6  test    eax, eax
0x100122b8  jz      short loc_100122C3
0x100122ba  push    eax; Block
0x100122bb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100122c0  add     esp, 4
0x100122c3  mov     eax, [esi+10h]
0x100122c6  test    eax, eax
0x100122c8  jz      short loc_100122D3
0x100122ca  push    eax; Block
0x100122cb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100122d0  add     esp, 4
0x100122d3  mov     dword ptr [esi], 8
0x100122d9  mov     dword ptr [esi+4], 0FFFFF9BFh
0x100122e0  mov     dword ptr [esi+8], 0
0x100122e7  mov     dword ptr [esi+0Ch], 0
0x100122ee  mov     dword ptr [esi+10h], 0
0x100122f5  mov     eax, [ebp+var_50]
0x100122f8  test    byte ptr [esi], 8
0x100122fb  jnz     loc_100125A2
0x10012301  cmp     eax, 1
0x10012304  jnz     loc_100125A2
0x1001230a  mov     eax, [ebx+8]
0x1001230d  mov     edi, [ebp+var_54]
0x10012310  test    eax, eax
0x10012312  jz      short loc_10012364
0x10012314  mov     ecx, [edi]
0x10012316  push    0; char
0x10012318  push    ecx; struct Transaction *
0x10012319  push    esi; struct Err *
0x1001231a  mov     ecx, [ecx+8]; this
0x1001231d  push    eax; unsigned int
0x1001231e  lea     eax, [ebp+var_7C]
0x10012321  push    eax; struct PageRef *
0x10012322  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x10012327  test    byte ptr [esi], 8
0x1001232a  jnz     loc_100125A2
0x10012330  mov     ecx, [ebp+var_7C]
0x10012333  mov     eax, [ecx+18h]
0x10012336  or      dword ptr [ecx+eax*4+1Ch], 8
0x1001233b  inc     dword ptr [ecx+40h]
0x1001233e  mov     eax, [ecx+18h]
0x10012341  lea     ecx, [ecx+eax*4]
0x10012344  mov     eax, [ecx+1Ch]
0x10012347  and     eax, 0FFFFFF4Fh
0x1001234c  or      eax, 40h
0x1001234f  mov     [ecx+1Ch], eax
0x10012352  test    byte ptr [esi], 8
0x10012355  jnz     loc_100125A2
0x1001235b  mov     eax, [ebp+var_78]
0x1001235e  mov     ecx, [ebx+0Ch]
0x10012361  mov     [eax+0Ch], ecx
0x10012364  mov     eax, [ebx+0Ch]
0x10012367  test    eax, eax
0x10012369  jz      short loc_100123BB
0x1001236b  mov     ecx, [edi]
0x1001236d  push    0; char
0x1001236f  push    ecx; struct Transaction *
0x10012370  push    esi; struct Err *
0x10012371  mov     ecx, [ecx+8]; this
0x10012374  push    eax; unsigned int
0x10012375  lea     eax, [ebp+var_7C]
0x10012378  push    eax; struct PageRef *
0x10012379  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x1001237e  test    byte ptr [esi], 8
0x10012381  jnz     loc_100125A2
0x10012387  mov     ecx, [ebp+var_7C]
0x1001238a  mov     eax, [ecx+18h]
0x1001238d  or      dword ptr [ecx+eax*4+1Ch], 8
0x10012392  inc     dword ptr [ecx+40h]
0x10012395  mov     eax, [ecx+18h]
0x10012398  lea     ecx, [ecx+eax*4]
0x1001239b  mov     eax, [ecx+1Ch]
0x1001239e  and     eax, 0FFFFFF4Fh
0x100123a3  or      eax, 40h
0x100123a6  mov     [ecx+1Ch], eax
0x100123a9  test    byte ptr [esi], 8
0x100123ac  jnz     loc_100125A2
0x100123b2  mov     eax, [ebp+var_78]
0x100123b5  mov     ecx, [ebx+8]
0x100123b8  mov     [eax+8], ecx
0x100123bb  cmp     [ebp+var_6C], 0
0x100123bf  jz      loc_10012589
0x100123c5  mov     eax, [ebp+var_68]
0x100123c8  test    eax, eax
0x100123ca  jz      loc_10012489
0x100123d0  mov     ebx, [eax+0Ch]
0x100123d3  jmp     loc_1001248B
0x100123d8  cmp     edi, 0FFFFFFFEh
0x100123db  jnz     loc_10012474
0x100123e1  mov     dword ptr [ebx+10h], 0
0x100123e8  mov     ecx, 70Fh
0x100123ed  movzx   eax, word ptr [ebx+2]
0x100123f1  sub     ecx, eax
0x100123f3  mov     edx, ecx
0x100123f5  and     ecx, 7
0x100123f8  shr     edx, 3
0x100123fb  mov     al, ds:byte_10003908[ecx]
0x10012401  and     al, [edx+ebx+16h]
0x10012405  jnz     short loc_10012416
0x10012407  mov     eax, edx
0x10012409  dec     edx
0x1001240a  test    eax, eax
0x1001240c  jz      short loc_10012464
0x1001240e  mov     al, [ebx+edx+16h]
0x10012412  test    al, al
0x10012414  jz      short loc_10012407
0x10012416  movzx   eax, al
0x10012419  movzx   eax, ds:byte_10003708[eax]
0x10012420  lea     edi, [eax+edx*8]
0x10012423  cmp     edi, 0FFFFFFFFh
0x10012426  jz      short loc_10012464
0x10012428  push    esi; struct Err *
0x10012429  push    edi; unsigned int
0x1001242a  lea     ecx, [ebp+var_68]; this
0x1001242d  call    ?GetBookmark@IndexPage@@QAEKIAAVErr@@@Z; IndexPage::GetBookmark(uint,Err &)
0x10012432  test    byte ptr [esi], 8
0x10012435  mov     [ebp+var_70], eax
0x10012438  jnz     loc_100122F5
0x1001243e  push    ecx
0x1001243f  push    edi
0x10012440  lea     ecx, [ebp+var_68]
0x10012443  call    ?Remove@IndexPage@@QAE?AW4IdxStatus@@IAAVErr@@@Z; IndexPage::Remove(uint,Err &)
0x10012448  test    byte ptr [esi], 8
0x1001244b  jnz     loc_100122F5
0x10012451  mov     eax, [ebp+var_70]
0x10012454  mov     [ebx+10h], eax
0x10012457  xor     eax, eax
0x10012459  mov     [ebp+var_50], eax
0x1001245c  mov     [ebp+var_58], eax
0x1001245f  jmp     loc_100122F8
0x10012464  mov     eax, 1
0x10012469  mov     [ebp+var_50], eax
0x1001246c  mov     [ebp+var_58], eax
0x1001246f  jmp     loc_100122F8
0x10012474  push    ecx
0x10012475  push    edi
0x10012476  lea     ecx, [ebp+var_68]
0x10012479  call    ?Remove@IndexPage@@QAE?AW4IdxStatus@@IAAVErr@@@Z; IndexPage::Remove(uint,Err &)
0x1001247e  mov     [ebp+var_50], eax
0x10012481  mov     [ebp+var_58], eax
0x10012484  jmp     loc_100122F8
0x10012489  xor     ebx, ebx
0x1001248b  push    esi
0x1001248c  push    1
0x1001248e  lea     ecx, [edi+6Ch]
0x10012491  call    ?Setup@AbstractSpacemap@@IAEXW4SetupType@1@AAVErr@@@Z; AbstractSpacemap::Setup(AbstractSpacemap::SetupType,Err &)
0x10012496  test    byte ptr [esi], 8
0x10012499  jnz     short loc_100124DE
0x1001249b  push    esi
0x1001249c  push    2
0x1001249e  push    ebx
0x1001249f  lea     ecx, [edi+6Ch]
0x100124a2  call    ?GetBitmap@AbstractSpacemap@@IAE?AW4GBResult@1@KW4GBDirection@1@AAVErr@@@Z; AbstractSpacemap::GetBitmap(ulong,AbstractSpacemap::GBDirection,Err &)
0x100124a7  cmp     eax, 1
0x100124aa  jnz     short loc_100124DE
0x100124ac  mov     eax, [edi+7Ch]
0x100124af  lea     ecx, [edi+7Ch]; this
0x100124b2  mov     edi, ebx
0x100124b4  sub     edi, [ecx+8]
0x100124b7  mov     edx, edi
0x100124b9  and     edi, 7
0x100124bc  shr     edx, 3
0x100124bf  mov     al, [edx+eax]
0x100124c2  test    ds:?ThisBit@Bitmap@@1QBEB[edi], al; uchar const * const Bitmap::ThisBit
0x100124c8  jz      short loc_100124DE
0x100124ca  push    esi; struct Err *
0x100124cb  push    ebx; unsigned int
0x100124cc  call    ?Clear@Bitmap@@QAEXKAAVErr@@@Z; Bitmap::Clear(ulong,Err &)
0x100124d1  mov     ebx, [ebp+var_54]
0x100124d4  lea     ecx, [ebx+6Ch]; this
0x100124d7  call    ?UpdateBitmap@AbstractSpacemap@@IAEXXZ; AbstractSpacemap::UpdateBitmap(void)
0x100124dc  jmp     short loc_100124E1
0x100124de  mov     ebx, [ebp+var_54]
0x100124e1  test    byte ptr [esi], 8
0x100124e4  jnz     loc_100125A2
0x100124ea  mov     eax, [ebp+var_68]
0x100124ed  test    eax, eax
0x100124ef  jz      short loc_100124F6
0x100124f1  mov     eax, [eax+0Ch]
0x100124f4  jmp     short loc_100124F8
0x100124f6  xor     eax, eax
0x100124f8  mov     ecx, [ebx]
0x100124fa  push    esi
0x100124fb  push    1
0x100124fd  push    eax
0x100124fe  call    ?FreePage@Transaction@@QAEXKW4FreeDisposition@@AAVErr@@@Z; Transaction::FreePage(ulong,FreeDisposition,Err &)
0x10012503  test    byte ptr [esi], 8
0x10012506  jnz     loc_100125A2
0x1001250c  mov     ecx, [ebx]
0x1001250e  mov     eax, [ebp+var_6C]
0x10012511  push    0; char
0x10012513  push    ecx; struct Transaction *
0x10012514  mov     ecx, [ecx+8]; this
  ... truncated ...
```
