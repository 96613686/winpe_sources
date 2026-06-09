# Btree::CollectBookmarks(IndexMover &,ulong * const,long,Err &)

- ea: `0x100128e0`
- end: `0x10012b43`
- name: `?CollectBookmarks@Btree@@QAEJAAVIndexMover@@QAKJAAVErr@@@Z`
- size: `611`
- prototype: `int __thiscall(Btree *__hidden this, struct IndexMover *, unsigned int *const, int, struct Err *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x10030490`

## callees

- `0x100128e0`
- `0x10012b50`
- `0x10025ee0`
- `0x10030380`
- `0x10031ef0`
- `0x10032190`
- `0x100322f0`
- `0x10038630`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
int __thiscall Btree::CollectBookmarks(Btree *this, struct IndexMover *a2, IndexPage **a3, unsigned int a4, void **a5)
{
  unsigned int v6; // edi
  struct Err *v7; // esi
  int result; // eax
  int v9; // ecx
  int v10; // eax
  int v11; // ecx
  unsigned int v12; // eax
  int v13; // eax
  unsigned int v14; // edi
  int v15; // ebx
  unsigned int *v16; // ecx
  unsigned int v17; // edx
  IndexPage *v18; // esi
  unsigned int v19; // eax
  unsigned __int8 v20; // cl
  int v21; // eax
  int v22; // [esp+14h] [ebp-58h]
  unsigned int v23; // [esp+18h] [ebp-54h]
  unsigned int v25; // [esp+24h] [ebp-48h]
  IndexPage *v26; // [esp+28h] [ebp-44h]
  IndexPage *Bookmark; // [esp+28h] [ebp-44h]
  int v28; // [esp+2Ch] [ebp-40h] BYREF
  void *Block; // [esp+30h] [ebp-3Ch]
  int v30; // [esp+34h] [ebp-38h]
  int v31; // [esp+38h] [ebp-34h]
  char v32; // [esp+3Ch] [ebp-30h] BYREF
  int v33; // [esp+68h] [ebp-4h]

  v6 = 0;
  v7 = (struct Err *)a5;
  if ( !*((_DWORD *)this + 9) )
  {
    if ( (int)*a5 >= 8 )
      return v6;
    if ( ((unsigned int)*a5 & 0xFFFFFFFE) != 0 )
    {
      if ( a5[3] )
        operator delete[](a5[3]);
      if ( a5[4] )
        operator delete[](a5[4]);
    }
    *a5 = (void *)8;
    result = 0;
    a5[1] = (void *)-1603;
    a5[2] = 0;
    a5[3] = 0;
    a5[4] = 0;
    return result;
  }
  v28 = 0;
  Block = &v32;
  v30 = 0;
  v31 = 32;
  v33 = 0;
  v9 = *((_DWORD *)this + 6);
  v26 = (Btree *)((char *)this + 24);
  if ( v9 && *((_DWORD *)this + 8) == *(_DWORD *)(v9 + 64) )
    goto LABEL_13;
  v10 = Btree::Resync(this, a5) - 2;
  if ( !v10 )
  {
    Err::SetError(a5, -1603, v11);
    return 0;
  }
  if ( v10 == 1 )
    return 0;
LABEL_13:
  v12 = IndexPage::Last(v26);
  IndexPage::GetKey(v26, v12, (struct Key *)&v28, (struct Err *)a5);
  if ( (*(_BYTE *)a5 & 8) != 0 || IndexMover::IsInRange(a2, &v28) != 1 )
    goto LABEL_31;
  v13 = *((_DWORD *)v26 + 1);
  v14 = *((_DWORD *)this + 14);
  v15 = v13 + 22;
  v22 = v13 + 244;
  Bookmark = (IndexPage *)IndexPage::GetBookmark(v26, v14, (struct Err *)a5);
  if ( (*(_BYTE *)a5 & 8) != 0 )
  {
    v16 = (unsigned int *)this;
    v6 = 0;
    goto LABEL_29;
  }
  v17 = 1;
  v18 = Bookmark;
  *a3 = Bookmark;
  while ( 1 )
  {
    v23 = v14;
    v19 = v14 >> 3;
    v25 = v17;
    v20 = *(_BYTE *)(v15 + (v14 >> 3)) & byte_100036F0[v14 & 7];
    if ( !v20 )
      break;
LABEL_21:
    v14 = (unsigned __int8)byte_10003808[v20] + 8 * v19;
    if ( v14 == -1 || v17 >= a4 )
      goto LABEL_28;
    ++v17;
    v21 = _byteswap_ulong(*(_DWORD *)(v14 + v22));
    if ( v14 - v23 == 2 )
    {
      v21 = (unsigned int)v18 ^ (unsigned __int16)((unsigned __int16)v18 ^ v21);
LABEL_27:
      a3[v25] = (IndexPage *)v21;
      v18 = Bookmark;
    }
    else
    {
      if ( v14 - v23 != 3 )
        goto LABEL_27;
      a3[v25] = (IndexPage *)((unsigned int)v18 ^ ((unsigned int)v18 ^ v21) & 0xFFFFFF);
      v18 = Bookmark;
    }
  }
  while ( ++v19 < 0xE2 )
  {
    _mm_lfence();
    v20 = *(_BYTE *)(v19 + v15);
    if ( v20 )
      goto LABEL_21;
  }
LABEL_28:
  v16 = (unsigned int *)this;
  v6 = v17;
  v7 = (struct Err *)a5;
  *((_DWORD *)this + 14) = v23;
LABEL_29:
  if ( (*(_BYTE *)v7 & 8) == 0 )
    IndexPage::GetKey((IndexPage *)(v16 + 6), v16[14], (struct Key *)(v16 + 15), v7);
LABEL_31:
  if ( v30 == 1 && Block )
    operator delete[](Block);
  return v6;
}

```

## disassembly

```asm
0x100128e0  mov     edi, edi
0x100128e2  push    ebp
0x100128e3  mov     ebp, esp
0x100128e5  push    0FFFFFFFFh
0x100128e7  push    offset ?CollectBookmarks@Btree@@QAEJAAVIndexMover@@QAKJAAVErr@@@Z_SEH
0x100128ec  mov     eax, large fs:0
0x100128f2  push    eax
0x100128f3  sub     esp, 50h
0x100128f6  mov     eax, ___security_cookie
0x100128fb  xor     eax, ebp
0x100128fd  mov     [ebp+var_10], eax
0x10012900  push    ebx
0x10012901  push    esi
0x10012902  push    edi
0x10012903  push    eax
0x10012904  lea     eax, [ebp+var_C]
0x10012907  mov     large fs:0, eax
0x1001290d  mov     edx, ecx
0x1001290f  mov     [ebp+var_4C], edx
0x10012912  mov     eax, [ebp+arg_4]
0x10012915  xor     edi, edi
0x10012917  mov     esi, [ebp+arg_C]
0x1001291a  mov     ebx, [ebp+arg_0]
0x1001291d  mov     [ebp+var_50], eax
0x10012920  mov     [ebp+var_5C], esi
0x10012923  cmp     [edx+24h], edi
0x10012926  jnz     short loc_10012977
0x10012928  mov     eax, [esi]
0x1001292a  cmp     eax, 8
0x1001292d  jge     loc_10012AFC
0x10012933  test    eax, 0FFFFFFFEh
0x10012938  jz      short loc_1001295A
0x1001293a  mov     eax, [esi+0Ch]
0x1001293d  test    eax, eax
0x1001293f  jz      short loc_1001294A
0x10012941  push    eax; Block
0x10012942  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10012947  add     esp, 4
0x1001294a  mov     eax, [esi+10h]
0x1001294d  test    eax, eax
0x1001294f  jz      short loc_1001295A
0x10012951  push    eax; Block
0x10012952  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10012957  add     esp, 4
0x1001295a  mov     dword ptr [esi], 8
0x10012960  mov     eax, edi
0x10012962  mov     dword ptr [esi+4], 0FFFFF9BDh
0x10012969  mov     [esi+8], edi
0x1001296c  mov     [esi+0Ch], edi
0x1001296f  mov     [esi+10h], edi
0x10012972  jmp     loc_10012B25
0x10012977  lea     eax, [ebp+var_30]
0x1001297a  mov     [ebp+var_40], edi
0x1001297d  mov     [ebp+Block], eax
0x10012980  mov     [ebp+var_38], edi
0x10012983  mov     [ebp+var_34], 20h ; ' '
0x1001298a  lea     eax, [edx+18h]
0x1001298d  mov     [ebp+var_4], 0
0x10012994  mov     ecx, [eax]
0x10012996  mov     [ebp+var_44], eax
0x10012999  test    ecx, ecx
0x1001299b  jz      short loc_100129A5
0x1001299d  mov     eax, [eax+8]
0x100129a0  cmp     eax, [ecx+40h]
0x100129a3  jz      short loc_100129BF
0x100129a5  push    esi
0x100129a6  mov     ecx, edx
0x100129a8  call    ?Resync@Btree@@AAE?AW4BTResyncStatus@@AAVErr@@@Z; Btree::Resync(Err &)
0x100129ad  sub     eax, 2
0x100129b0  jz      loc_10012B00
0x100129b6  sub     eax, 1
0x100129b9  jz      loc_10012B0D
0x100129bf  mov     ecx, [ebp+var_44]; this
0x100129c2  lea     eax, [ebp+var_40]
0x100129c5  push    esi; struct Err *
0x100129c6  push    eax; struct Key *
0x100129c7  call    ?Last@IndexPage@@QBEIXZ; IndexPage::Last(void)
0x100129cc  mov     ecx, [ebp+var_44]; this
0x100129cf  push    eax; unsigned int
0x100129d0  call    ?GetKey@IndexPage@@QAEXIAAVKey@@AAVErr@@@Z; IndexPage::GetKey(uint,Key &,Err &)
0x100129d5  test    byte ptr [esi], 8
0x100129d8  jnz     loc_10012AE6
0x100129de  lea     eax, [ebp+var_40]
0x100129e1  mov     ecx, ebx
0x100129e3  push    eax
0x100129e4  call    ?IsInRange@IndexMover@@QAE?AW4RangeResult@@ABVQuickKey@@@Z; IndexMover::IsInRange(QuickKey const &)
0x100129e9  cmp     eax, 1
0x100129ec  jnz     loc_10012AE6
0x100129f2  mov     ecx, [ebp+var_44]; this
0x100129f5  mov     edi, [ebp+var_4C]
0x100129f8  push    esi; struct Err *
0x100129f9  mov     eax, [ecx+4]
0x100129fc  mov     edi, [edi+38h]
0x100129ff  push    edi; unsigned int
0x10012a00  lea     ebx, [eax+16h]
0x10012a03  add     eax, 0F4h
0x10012a08  mov     [ebp+var_58], eax
0x10012a0b  call    ?GetBookmark@IndexPage@@QAEKIAAVErr@@@Z; IndexPage::GetBookmark(uint,Err &)
0x10012a10  test    byte ptr [esi], 8
0x10012a13  mov     [ebp+var_44], eax
0x10012a16  jz      short loc_10012A22
0x10012a18  mov     ecx, [ebp+var_4C]
0x10012a1b  xor     edi, edi
0x10012a1d  jmp     loc_10012AD1
0x10012a22  mov     eax, [ebp+var_50]
0x10012a25  mov     edx, 1
0x10012a2a  mov     esi, [ebp+var_44]
0x10012a2d  mov     [eax], esi
0x10012a2f  nop
0x10012a30  mov     eax, edi
0x10012a32  mov     [ebp+var_54], edi
0x10012a35  and     edi, 7
0x10012a38  shr     eax, 3
0x10012a3b  mov     [ebp+var_48], edx
0x10012a3e  mov     cl, ds:byte_100036F0[edi]
0x10012a44  and     cl, [ebx+eax]
0x10012a47  jnz     short loc_10012A62
0x10012a49  nop     dword ptr [eax+00000000h]
0x10012a50  inc     eax
0x10012a51  cmp     eax, 0E2h
0x10012a56  jnb     short loc_10012AC0
0x10012a58  lfence
0x10012a5b  mov     cl, [eax+ebx]
0x10012a5e  test    cl, cl
0x10012a60  jz      short loc_10012A50
0x10012a62  movzx   ecx, cl
0x10012a65  movzx   ecx, ds:byte_10003808[ecx]
0x10012a6c  lea     edi, [ecx+eax*8]
0x10012a6f  cmp     edi, 0FFFFFFFFh
0x10012a72  jz      short loc_10012AC0
0x10012a74  cmp     edx, [ebp+arg_8]
0x10012a77  jnb     short loc_10012AC0
0x10012a79  mov     eax, [ebp+var_58]
0x10012a7c  mov     ecx, edi
0x10012a7e  sub     ecx, [ebp+var_54]
0x10012a81  inc     edx
0x10012a82  mov     eax, [edi+eax]
0x10012a85  bswap   eax
0x10012a87  sub     ecx, 2
0x10012a8a  jz      short loc_10012AA8
0x10012a8c  sub     ecx, 1
0x10012a8f  jnz     short loc_10012AAF
0x10012a91  mov     ecx, [ebp+var_48]
0x10012a94  xor     eax, esi
0x10012a96  and     eax, 0FFFFFFh
0x10012a9b  xor     eax, esi
0x10012a9d  mov     esi, [ebp+var_50]
0x10012aa0  mov     [esi+ecx*4], eax
0x10012aa3  mov     esi, [ebp+var_44]
0x10012aa6  jmp     short loc_10012A30
0x10012aa8  xor     eax, esi
0x10012aaa  movzx   eax, ax
0x10012aad  xor     eax, esi
0x10012aaf  mov     esi, [ebp+var_50]
0x10012ab2  mov     ecx, [ebp+var_48]
0x10012ab5  mov     [esi+ecx*4], eax
0x10012ab8  mov     esi, [ebp+var_44]
0x10012abb  jmp     loc_10012A30
0x10012ac0  mov     ecx, [ebp+var_4C]
0x10012ac3  mov     edi, edx
0x10012ac5  mov     eax, [ebp+var_54]
0x10012ac8  mov     esi, [ebp+var_5C]
0x10012acb  mov     [ebp+var_48], edx
0x10012ace  mov     [ecx+38h], eax
0x10012ad1  test    byte ptr [esi], 8
0x10012ad4  jnz     short loc_10012AE6
0x10012ad6  push    esi; struct Err *
0x10012ad7  lea     eax, [ecx+3Ch]
0x10012ada  push    eax; struct Key *
0x10012adb  push    dword ptr [ecx+38h]; unsigned int
0x10012ade  lea     ecx, [ecx+18h]; this
0x10012ae1  call    ?GetKey@IndexPage@@QAEXIAAVKey@@AAVErr@@@Z; IndexPage::GetKey(uint,Key &,Err &)
0x10012ae6  cmp     [ebp+var_38], 1
0x10012aea  jnz     short loc_10012AFC
0x10012aec  mov     ecx, [ebp+Block]
0x10012aef  test    ecx, ecx
0x10012af1  jz      short loc_10012AFC
0x10012af3  push    ecx; Block
0x10012af4  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10012af9  add     esp, 4
0x10012afc  mov     eax, edi
0x10012afe  jmp     short loc_10012B25
0x10012b00  push    ecx
0x10012b01  push    0FFFFF9BDh
0x10012b06  mov     ecx, esi
0x10012b08  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10012b0d  cmp     [ebp+var_38], 1
0x10012b11  jnz     short loc_10012B23
0x10012b13  mov     eax, [ebp+Block]
0x10012b16  test    eax, eax
0x10012b18  jz      short loc_10012B23
0x10012b1a  push    eax; Block
0x10012b1b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10012b20  add     esp, 4
0x10012b23  xor     eax, eax
0x10012b25  mov     ecx, [ebp+var_C]
0x10012b28  mov     large fs:0, ecx
0x10012b2f  pop     ecx
0x10012b30  pop     edi
0x10012b31  pop     esi
0x10012b32  pop     ebx
0x10012b33  mov     ecx, [ebp+var_10]
0x10012b36  xor     ecx, ebp; StackCookie
0x10012b38  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10012b3d  mov     esp, ebp
0x10012b3f  pop     ebp
0x10012b40  retn    10h
0x1005fb80  lea     ecx, [ebp+var_40]; this
0x1005fb83  jmp     ??1Key@@QAE@XZ; Key::~Key(void)
0x1005fb8d  nop
0x1005fb8e  nop
0x1005fb8f  mov     edx, [esp-4+arg_4]
0x1005fb93  lea     eax, [edx+0Ch]
0x1005fb96  mov     ecx, [edx-60h]
0x1005fb99  xor     ecx, eax; StackCookie
0x1005fb9b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005fba0  mov     ecx, [edx-4]
0x1005fba3  xor     ecx, eax; StackCookie
0x1005fba5  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005fbaa  mov     eax, offset stru_10062D2C
0x1005fbaf  jmp     ___CxxFrameHandler3
```
