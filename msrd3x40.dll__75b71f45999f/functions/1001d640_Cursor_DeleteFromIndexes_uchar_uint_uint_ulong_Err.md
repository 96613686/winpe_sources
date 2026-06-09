# Cursor::DeleteFromIndexes(uchar *,uint,uint,ulong,Err &)

- ea: `0x1001d640`
- end: `0x1001d991`
- name: `?DeleteFromIndexes@Cursor@@AAEXPAEIIKAAVErr@@@Z`
- size: `849`
- prototype: `void __thiscall(Cursor *__hidden this, unsigned __int8 *, unsigned int, unsigned int, unsigned int, struct Err *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1001c3d0`
- `0x1001cf90`

## callees

- `0x1000f930`
- `0x10010600`
- `0x100106b0`
- `0x10012190`
- `0x1001d640`
- `0x1001db50`
- `0x1001dfc0`
- `0x10038630`
- `0x10057340`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall Cursor::DeleteFromIndexes(
        Table **this,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        struct Err *a6)
{
  bool v6; // zf
  Bitmap *v7; // ebx
  unsigned int v8; // edx
  int OneInclusive; // esi
  unsigned __int8 v10; // al
  struct PhysicalIndex *v11; // edx
  int v12; // ecx
  int v13; // ecx
  unsigned int v14; // ecx
  int v15; // esi
  unsigned int v16; // ecx
  unsigned __int8 v17; // dl
  struct PhysicalIndex *v18; // eax
  int v19; // edx
  int v20; // ecx
  unsigned int v21; // esi
  struct Index *v22; // eax
  struct PhysicalIndex *v23; // ebx
  struct Index *v24; // eax
  unsigned int v25; // eax
  int v26; // edx
  unsigned int v27; // eax
  unsigned __int8 v28; // dl
  _DWORD v29[4]; // [esp+10h] [ebp-144h] BYREF
  unsigned int *p_PhysicalIndexes; // [esp+20h] [ebp-134h] BYREF
  int v31; // [esp+24h] [ebp-130h]
  int v32; // [esp+28h] [ebp-12Ch]
  unsigned int PhysicalIndexes; // [esp+2Ch] [ebp-128h] BYREF
  Bitmap *v34; // [esp+30h] [ebp-124h]
  struct Index *v35; // [esp+34h] [ebp-120h]
  Cursor *v36; // [esp+38h] [ebp-11Ch]
  struct PhysicalIndex *i; // [esp+3Ch] [ebp-118h]
  struct Transaction *v38[52]; // [esp+40h] [ebp-114h] BYREF
  int v39; // [esp+110h] [ebp-44h] BYREF
  void *Block; // [esp+114h] [ebp-40h]
  int v41; // [esp+118h] [ebp-3Ch]
  int v42; // [esp+11Ch] [ebp-38h]
  char v43; // [esp+120h] [ebp-34h] BYREF
  int v44; // [esp+150h] [ebp-4h]

  v36 = (Cursor *)this;
  v29[0] = a2;
  v29[1] = a3;
  v29[2] = a4;
  Block = &v43;
  v39 = 0;
  v41 = 0;
  v42 = 32;
  v44 = 0;
  v6 = this[11] == (Table *)3;
  p_PhysicalIndexes = 0;
  v31 = 0;
  v32 = 0;
  if ( v6 )
  {
    PhysicalIndexes = Table::GetPhysicalIndexes(this[3], a6);
    v7 = (Bitmap *)&p_PhysicalIndexes;
    v31 = 4;
    p_PhysicalIndexes = &PhysicalIndexes;
  }
  else
  {
    v7 = (Table *)((char *)this[13] + 28);
  }
  v8 = *((_DWORD *)v7 + 2);
  v34 = v7;
  OneInclusive = Bitmap::NextOneInclusive(v7, v8);
  while ( (*(_BYTE *)a6 & 8) == 0 )
  {
    if ( OneInclusive == -1 )
      break;
    i = *(struct PhysicalIndex **)(*((_DWORD *)v36 + 3) + 4 * OneInclusive + 1652);
    v39 = 0;
    v10 = Cursor::BuildKeyFromRecord(v36, i, (struct Record *)v29, (struct Key *)&v39, a6);
    if ( (*(_BYTE *)a6 & 8) == 0 && ((*((_BYTE *)i + 64) & 2) == 0 || (v10 & 2) != 0) )
    {
      Btree::Btree((Btree *)v38, v36, i);
      LOBYTE(v44) = 1;
      Btree::DeleteKey(v38, (struct Key *)&v39, a5, (void **)a6);
      if ( (*(_BYTE *)a6 & 8) == 0 )
      {
        v11 = i;
        if ( *((_DWORD *)i + 11) + *((_DWORD *)i + 10) > 0 )
        {
          *(_BYTE *)(*((_DWORD *)i + 5) + 88) |= 1u;
          v12 = --*((_DWORD *)v11 + 11) + *((_DWORD *)v11 + 10);
          i = (struct PhysicalIndex *)(*((_DWORD *)v11 + 12) + *((_DWORD *)v11 + 13));
          if ( v12 < (int)i )
          {
            v13 = v12 - (_DWORD)i;
            *(_BYTE *)(*((_DWORD *)v11 + 5) + 88) |= 1u;
            *((_DWORD *)v11 + 13) += v13;
          }
        }
      }
      LOBYTE(v44) = 0;
      Btree::~Btree((Btree *)v38);
    }
    v14 = OneInclusive - *((_DWORD *)v7 + 2);
    v15 = v14 & 7;
    v16 = v14 >> 3;
    v17 = *(_BYTE *)(*(_DWORD *)v7 + v16) & byte_100036F0[v15];
    if ( v17 )
    {
LABEL_17:
      OneInclusive = *((_DWORD *)v7 + 2) + (unsigned __int8)byte_10003808[v17] + 8 * v16;
    }
    else
    {
      while ( ++v16 < *((_DWORD *)v7 + 1) )
      {
        _mm_lfence();
        v17 = *(_BYTE *)(v16 + *(_DWORD *)v7);
        if ( v17 )
          goto LABEL_17;
      }
      OneInclusive = -1;
    }
  }
  v18 = (struct PhysicalIndex *)Bitmap::NextOneInclusive(v7, *((_DWORD *)v7 + 2));
  v6 = (*(_BYTE *)a6 & 8) == 0;
  v19 = (int)v18;
  for ( i = v18; v6; i = (struct PhysicalIndex *)v19 )
  {
    if ( v19 == -1 )
      break;
    v20 = 0;
    v21 = 0;
    v22 = *(struct Index **)(*((_DWORD *)v36 + 3) + 4 * v19 + 1652);
    v39 = 0;
    v35 = v22;
    if ( *((_DWORD *)v22 + 2) )
    {
      v23 = v22;
      do
      {
        if ( (*(_BYTE *)a6 & 8) != 0 )
          break;
        v24 = *(struct Index **)(*(_DWORD *)v23 + 4 * v21);
        v35 = v24;
        if ( *((_BYTE *)v24 + 41) == 1 )
        {
          if ( !v20 )
          {
            Cursor::BuildKeyFromRecord(v36, v23, (struct Record *)v29, (struct Key *)&v39, a6);
            v24 = v35;
          }
          Cursor::CascadeChange(v36, v24, (struct Key *)&v39, a6);
          v20 = v39;
        }
        ++v21;
      }
      while ( v21 < *((_DWORD *)v23 + 2) );
      v7 = v34;
      v19 = (int)i;
    }
    v25 = v19 - *((_DWORD *)v7 + 2);
    v26 = v25 & 7;
    v27 = v25 >> 3;
    v28 = *(_BYTE *)(*(_DWORD *)v7 + v27) & byte_100036F0[v26];
    if ( v28 )
    {
LABEL_33:
      v19 = *((_DWORD *)v7 + 2) + (unsigned __int8)byte_10003808[v28] + 8 * v27;
    }
    else
    {
      while ( ++v27 < *((_DWORD *)v7 + 1) )
      {
        _mm_lfence();
        v28 = *(_BYTE *)(v27 + *(_DWORD *)v7);
        if ( v28 )
          goto LABEL_33;
      }
      v19 = -1;
    }
    v6 = (*(_BYTE *)a6 & 8) == 0;
  }
  if ( v41 == 1 )
  {
    if ( Block )
      operator delete[](Block);
  }
}

```

## disassembly

```asm
0x1001d640  mov     edi, edi
0x1001d642  push    ebp
0x1001d643  mov     ebp, esp
0x1001d645  push    0FFFFFFFFh
0x1001d647  push    offset ?DeleteFromIndexes@Cursor@@AAEXPAEIIKAAVErr@@@Z_SEH
0x1001d64c  mov     eax, large fs:0
0x1001d652  push    eax
0x1001d653  sub     esp, 138h
0x1001d659  mov     eax, ___security_cookie
0x1001d65e  xor     eax, ebp
0x1001d660  mov     [ebp+var_14], eax
0x1001d663  push    ebx
0x1001d664  push    esi
0x1001d665  push    edi
0x1001d666  push    eax
0x1001d667  lea     eax, [ebp+var_C]
0x1001d66a  mov     large fs:0, eax
0x1001d670  mov     [ebp+var_11C], ecx
0x1001d676  mov     eax, [ebp+arg_0]
0x1001d679  mov     edi, [ebp+arg_10]
0x1001d67c  mov     [ebp+var_144], eax
0x1001d682  mov     eax, [ebp+arg_4]
0x1001d685  mov     [ebp+var_140], eax
0x1001d68b  mov     eax, [ebp+arg_8]
0x1001d68e  mov     [ebp+var_13C], eax
0x1001d694  lea     eax, [ebp+var_34]
0x1001d697  mov     [ebp+Block], eax
0x1001d69a  mov     [ebp+var_44], 0
0x1001d6a1  mov     [ebp+var_3C], 0
0x1001d6a8  mov     [ebp+var_38], 20h ; ' '
0x1001d6af  mov     [ebp+var_4], 0
0x1001d6b6  cmp     dword ptr [ecx+2Ch], 3
0x1001d6ba  mov     [ebp+var_134], 0
0x1001d6c4  mov     [ebp+var_130], 0
0x1001d6ce  mov     [ebp+var_12C], 0
0x1001d6d8  jnz     short loc_1001D707
0x1001d6da  mov     ecx, [ecx+0Ch]; this
0x1001d6dd  push    edi; struct Err *
0x1001d6de  call    ?GetPhysicalIndexes@Table@@QBEKAAVErr@@@Z; Table::GetPhysicalIndexes(Err &)
0x1001d6e3  mov     [ebp+var_128], eax
0x1001d6e9  lea     ebx, [ebp+var_134]
0x1001d6ef  lea     eax, [ebp+var_128]
0x1001d6f5  mov     [ebp+var_130], 4
0x1001d6ff  mov     [ebp+var_134], eax
0x1001d705  jmp     short loc_1001D70D
0x1001d707  mov     ebx, [ecx+34h]
0x1001d70a  add     ebx, 1Ch
0x1001d70d  mov     edx, [ebx+8]; unsigned int
0x1001d710  mov     ecx, ebx; this
0x1001d712  mov     [ebp+var_124], ebx
0x1001d718  call    ?NextOneInclusive@Bitmap@@QBIKK@Z; Bitmap::NextOneInclusive(ulong)
0x1001d71d  test    byte ptr [edi], 8
0x1001d720  mov     esi, eax
0x1001d722  jnz     loc_1001D84E
0x1001d728  nop     dword ptr [eax+eax+00000000h]
0x1001d730  cmp     esi, 0FFFFFFFFh
0x1001d733  jz      loc_1001D84E
0x1001d739  mov     ecx, [ebp+var_11C]; this
0x1001d73f  lea     edx, [ebp+var_44]
0x1001d742  push    edi; struct Err *
0x1001d743  push    edx; struct Key *
0x1001d744  lea     edx, [ebp+var_144]
0x1001d74a  mov     eax, [ecx+0Ch]
0x1001d74d  push    edx; struct Record *
0x1001d74e  mov     eax, [eax+esi*4+674h]
0x1001d755  push    eax; struct PhysicalIndex *
0x1001d756  mov     [ebp+var_118], eax
0x1001d75c  mov     [ebp+var_44], 0
0x1001d763  call    ?BuildKeyFromRecord@Cursor@@QAEEPAVPhysicalIndex@@AAVRecord@@AAVKey@@AAVErr@@@Z; Cursor::BuildKeyFromRecord(PhysicalIndex *,Record &,Key &,Err &)
0x1001d768  test    byte ptr [edi], 8
0x1001d76b  jnz     loc_1001D7FE
0x1001d771  mov     ecx, [ebp+var_118]
0x1001d777  test    byte ptr [ecx+40h], 2
0x1001d77b  jz      short loc_1001D781
0x1001d77d  test    al, 2
0x1001d77f  jz      short loc_1001D7FE
0x1001d781  push    ecx; struct PhysicalIndex *
0x1001d782  push    [ebp+var_11C]; struct Cursor *
0x1001d788  lea     ecx, [ebp+var_114]; this
0x1001d78e  call    ??0Btree@@QAE@PAVCursor@@PAVPhysicalIndex@@@Z; Btree::Btree(Cursor *,PhysicalIndex *)
0x1001d793  push    edi; struct Err *
0x1001d794  push    [ebp+arg_C]; unsigned int
0x1001d797  lea     eax, [ebp+var_44]
0x1001d79a  mov     byte ptr [ebp+var_4], 1
0x1001d79e  push    eax; struct Key *
0x1001d79f  lea     ecx, [ebp+var_114]; this
0x1001d7a5  call    ?DeleteKey@Btree@@QAEXAAVKey@@KAAVErr@@@Z; Btree::DeleteKey(Key &,ulong,Err &)
0x1001d7aa  test    byte ptr [edi], 8
0x1001d7ad  jnz     short loc_1001D7EF
0x1001d7af  mov     edx, [ebp+var_118]
0x1001d7b5  mov     eax, [edx+28h]
0x1001d7b8  add     eax, [edx+2Ch]
0x1001d7bb  test    eax, eax
0x1001d7bd  jle     short loc_1001D7EF
0x1001d7bf  mov     eax, [edx+14h]
0x1001d7c2  or      byte ptr [eax+58h], 1
0x1001d7c6  dec     dword ptr [edx+2Ch]
0x1001d7c9  mov     eax, [edx+34h]
0x1001d7cc  mov     ecx, [edx+28h]
0x1001d7cf  add     eax, [edx+30h]
0x1001d7d2  add     ecx, [edx+2Ch]
0x1001d7d5  mov     [ebp+var_118], eax
0x1001d7db  cmp     ecx, eax
0x1001d7dd  jge     short loc_1001D7EF
0x1001d7df  mov     eax, [edx+14h]
0x1001d7e2  sub     ecx, [ebp+var_118]
0x1001d7e8  or      byte ptr [eax+58h], 1
0x1001d7ec  add     [edx+34h], ecx
0x1001d7ef  lea     ecx, [ebp+var_114]; this
0x1001d7f5  mov     byte ptr [ebp+var_4], 0
0x1001d7f9  call    ??1Btree@@QAE@XZ; Btree::~Btree(void)
0x1001d7fe  sub     esi, [ebx+8]
0x1001d801  mov     eax, [ebx]
0x1001d803  mov     ecx, esi
0x1001d805  and     esi, 7
0x1001d808  shr     ecx, 3
0x1001d80b  mov     dl, ds:byte_100036F0[esi]
0x1001d811  and     dl, [eax+ecx]
0x1001d814  jnz     short loc_1001D835
0x1001d816  mov     esi, [ebx+4]
0x1001d819  nop     dword ptr [eax+00000000h]
0x1001d820  inc     ecx
0x1001d821  cmp     ecx, esi
0x1001d823  jnb     loc_1001D984
0x1001d829  lfence
0x1001d82c  mov     eax, [ebx]
0x1001d82e  mov     dl, [ecx+eax]
0x1001d831  test    dl, dl
0x1001d833  jz      short loc_1001D820
0x1001d835  movzx   eax, dl
0x1001d838  movzx   eax, ds:byte_10003808[eax]
0x1001d83f  lea     esi, [eax+ecx*8]
0x1001d842  add     esi, [ebx+8]
0x1001d845  test    byte ptr [edi], 8
0x1001d848  jz      loc_1001D730
0x1001d84e  mov     edx, [ebx+8]; unsigned int
0x1001d851  mov     ecx, ebx; this
0x1001d853  call    ?NextOneInclusive@Bitmap@@QBIKK@Z; Bitmap::NextOneInclusive(ulong)
0x1001d858  test    byte ptr [edi], 8
0x1001d85b  mov     edx, eax
0x1001d85d  mov     [ebp+var_118], edx
0x1001d863  jnz     loc_1001D950
0x1001d869  nop     dword ptr [eax+00000000h]
0x1001d870  cmp     edx, 0FFFFFFFFh
0x1001d873  jz      loc_1001D950
0x1001d879  mov     eax, [ebp+var_11C]
0x1001d87f  xor     ecx, ecx
0x1001d881  xor     esi, esi
0x1001d883  mov     eax, [eax+0Ch]
0x1001d886  mov     eax, [eax+edx*4+674h]
0x1001d88d  mov     [ebp+var_44], ecx
0x1001d890  mov     [ebp+var_120], eax
0x1001d896  cmp     [eax+8], ecx
0x1001d899  jbe     short loc_1001D8FE
0x1001d89b  mov     ebx, eax
0x1001d89d  nop     dword ptr [eax]
0x1001d8a0  test    byte ptr [edi], 8
0x1001d8a3  jnz     short loc_1001D8F2
0x1001d8a5  mov     eax, [ebx]
0x1001d8a7  mov     eax, [eax+esi*4]
0x1001d8aa  mov     [ebp+var_120], eax
0x1001d8b0  cmp     byte ptr [eax+29h], 1
0x1001d8b4  jnz     short loc_1001D8EC
0x1001d8b6  test    ecx, ecx
0x1001d8b8  jnz     short loc_1001D8D8
0x1001d8ba  mov     ecx, [ebp+var_11C]; this
0x1001d8c0  lea     eax, [ebp+var_44]
0x1001d8c3  push    edi; struct Err *
0x1001d8c4  push    eax; struct Key *
0x1001d8c5  lea     eax, [ebp+var_144]
0x1001d8cb  push    eax; struct Record *
0x1001d8cc  push    ebx; struct PhysicalIndex *
0x1001d8cd  call    ?BuildKeyFromRecord@Cursor@@QAEEPAVPhysicalIndex@@AAVRecord@@AAVKey@@AAVErr@@@Z; Cursor::BuildKeyFromRecord(PhysicalIndex *,Record &,Key &,Err &)
0x1001d8d2  mov     eax, [ebp+var_120]
0x1001d8d8  push    edi; struct Err *
0x1001d8d9  lea     ecx, [ebp+var_44]
0x1001d8dc  push    ecx; struct Key *
0x1001d8dd  mov     ecx, [ebp+var_11C]; this
0x1001d8e3  push    eax; struct Index *
0x1001d8e4  call    ?CascadeChange@Cursor@@AAEXAAVIndex@@AAVKey@@AAVErr@@@Z; Cursor::CascadeChange(Index &,Key &,Err &)
0x1001d8e9  mov     ecx, [ebp+var_44]
0x1001d8ec  inc     esi
0x1001d8ed  cmp     esi, [ebx+8]
0x1001d8f0  jb      short loc_1001D8A0
0x1001d8f2  mov     ebx, [ebp+var_124]
0x1001d8f8  mov     edx, [ebp+var_118]
0x1001d8fe  sub     edx, [ebx+8]
0x1001d901  mov     ecx, [ebx]
0x1001d903  mov     eax, edx
0x1001d905  and     edx, 7
0x1001d908  shr     eax, 3
0x1001d90b  mov     dl, ds:byte_100036F0[edx]
0x1001d911  and     dl, [ecx+eax]
0x1001d914  jnz     short loc_1001D931
0x1001d916  mov     esi, [ebx+4]
0x1001d919  nop     dword ptr [eax+00000000h]
0x1001d920  inc     eax
0x1001d921  cmp     eax, esi
0x1001d923  jnb     short loc_1001D98C
0x1001d925  lfence
0x1001d928  mov     ecx, [ebx]
0x1001d92a  mov     dl, [eax+ecx]
0x1001d92d  test    dl, dl
0x1001d92f  jz      short loc_1001D920
0x1001d931  movzx   ecx, dl
0x1001d934  movzx   ecx, ds:byte_10003808[ecx]
0x1001d93b  lea     edx, [ecx+eax*8]
0x1001d93e  add     edx, [ebx+8]
0x1001d941  test    byte ptr [edi], 8
0x1001d944  mov     [ebp+var_118], edx
0x1001d94a  jz      loc_1001D870
0x1001d950  cmp     [ebp+var_3C], 1
0x1001d954  jnz     short loc_1001D966
0x1001d956  mov     eax, [ebp+Block]
0x1001d959  test    eax, eax
0x1001d95b  jz      short loc_1001D966
0x1001d95d  push    eax; Block
0x1001d95e  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001d963  add     esp, 4
0x1001d966  mov     ecx, [ebp+var_C]
0x1001d969  mov     large fs:0, ecx
0x1001d970  pop     ecx
0x1001d971  pop     edi
0x1001d972  pop     esi
0x1001d973  pop     ebx
0x1001d974  mov     ecx, [ebp+var_14]
0x1001d977  xor     ecx, ebp; StackCookie
0x1001d979  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001d97e  mov     esp, ebp
0x1001d980  pop     ebp
0x1001d981  retn    14h
0x1001d984  or      esi, 0FFFFFFFFh
0x1001d987  jmp     loc_1001D845
0x1001d98c  or      edx, 0FFFFFFFFh
0x1001d98f  jmp     short loc_1001D941
0x100601b0  lea     ecx, [ebp+var_44]; this
0x100601b3  jmp     ??1Key@@QAE@XZ; Key::~Key(void)
0x100601b8  lea     ecx, [ebp+var_114]; this
0x100601be  jmp     ??1Btree@@QAE@XZ; Btree::~Btree(void)
0x100601c8  nop
0x100601c9  nop
0x100601ca  mov     edx, [esp-4+arg_4]
0x100601ce  lea     eax, [edx+0Ch]
0x100601d1  mov     ecx, [edx-148h]
0x100601d7  xor     ecx, eax; StackCookie
0x100601d9  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100601de  mov     ecx, [edx-8]
0x100601e1  xor     ecx, eax; StackCookie
0x100601e3  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100601e8  mov     eax, offset stru_100631B4
0x100601ed  jmp     ___CxxFrameHandler3
```
