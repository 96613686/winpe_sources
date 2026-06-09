# SortMover::MakeBaseTable(Err &)

- ea: `0x1004d040`
- end: `0x1004d38d`
- name: `?MakeBaseTable@SortMover@@AAEXAAVErr@@@Z`
- size: `845`
- prototype: `void __thiscall(SortMover *__hidden this, struct Err *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops`

## callers

- `0x1004cee0`

## callees

- `0x1000eb60`
- `0x10010600`
- `0x100106b0`
- `0x10011f50`
- `0x10019110`
- `0x100191b0`
- `0x100195b0`
- `0x10019960`
- `0x10019d90`
- `0x1001c8c0`
- `0x10025ee0`
- `0x10026020`
- `0x10038630`
- `0x10038650`
- `0x100399c0`
- `0x100453a0`
- `0x10046360`
- `0x10046400`
- `0x1004d040`
- `0x10052cc0`
- `0x1005e3b0`
- `0x1005e798`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall SortMover::MakeBaseTable(struct Cursor **this, struct Err *a2)
{
  struct Cursor **v2; // ebx
  struct SortItem **v3; // eax
  struct Cursor *v4; // ecx
  struct SortItem **v5; // edx
  struct SortItem *v6; // eax
  int v7; // ecx
  int v8; // edi
  unsigned int v9; // edx
  const unsigned __int8 *v10; // edi
  CopyBuff *v11; // eax
  int v12; // ecx
  unsigned int inserted; // edi
  unsigned __int8 *v14; // eax
  Table *v15; // ebx
  struct Instance *v16; // eax
  int v17; // ecx
  int v18; // eax
  int v19; // eax
  int v20; // ecx
  struct Cursor *v21; // ebx
  int (__thiscall *v22)(struct Cursor *); // edi
  int v23; // eax
  int v24; // ecx
  _DWORD *v25; // eax
  CopyBuff *v26; // [esp+14h] [ebp-298h]
  _DWORD v27[2]; // [esp+18h] [ebp-294h] BYREF
  void (__thiscall *v28)(struct Cursor *, _DWORD, struct Err *); // [esp+20h] [ebp-28Ch]
  struct Cursor **v29; // [esp+24h] [ebp-288h]
  _BYTE v30[208]; // [esp+28h] [ebp-284h] BYREF
  _DWORD v31[3]; // [esp+F8h] [ebp-1B4h] BYREF
  Table *v32; // [esp+104h] [ebp-1A8h]
  CopyBuff *v33; // [esp+12Ch] [ebp-180h]
  int v34; // [esp+268h] [ebp-44h] BYREF
  void *Block; // [esp+26Ch] [ebp-40h]
  int v36; // [esp+270h] [ebp-3Ch]
  unsigned int v37; // [esp+274h] [ebp-38h]
  char v38; // [esp+278h] [ebp-34h] BYREF
  int v39; // [esp+2A8h] [ebp-4h]

  v2 = this;
  v29 = this;
  Cursor::Cursor((Cursor *)v31, this[1], a2);
  v39 = 0;
  if ( (*(_BYTE *)a2 & 8) == 0 )
  {
    Cursor::SetCurrentIndex((Cursor *)v31, 0, a2);
    if ( (*(_BYTE *)a2 & 8) == 0 )
    {
      v3 = Sort::First(v2[3], a2);
      v4 = v2[3];
      v5 = v3;
      v2[4] = (struct Cursor *)v3;
      if ( v3 != *((struct SortItem ***)v4 + 6) )
      {
        do
        {
          if ( (*(_BYTE *)a2 & 8) != 0 )
            break;
          v6 = *v5;
          v7 = *((unsigned __int16 *)*v5 + 1);
          v8 = (int)*v5 + 4;
          v9 = *(unsigned __int16 *)*v5;
          v10 = (const unsigned __int8 *)(v7 + v8);
          v27[0] = v7;
          v28 = (void (__thiscall *)(struct Cursor *, _DWORD, struct Err *))v9;
          v27[1] = (char *)v6 + 4;
          if ( v33 )
          {
            CopyBuff::Refresh(v33, v10, v9);
          }
          else
          {
            v26 = (CopyBuff *)operator new(0x828u);
            v11 = CopyBuff::CopyBuff(v26);
            v33 = v11;
            if ( v11 )
              CopyBuff::Refresh(v11, v10, (unsigned int)v28);
            else
              Err::SetError(a2, -1011, v12);
          }
          if ( (*(_BYTE *)a2 & 8) == 0 )
          {
            v37 = 32;
            v34 = 0;
            Block = &v38;
            v36 = 0;
            LOBYTE(v39) = 1;
            Key::Assign((Key *)&v34, (const struct QuickKey *)v27, a2);
            if ( (*(_BYTE *)a2 & 8) == 0 )
            {
              inserted = Cursor::InsertRecord((int)v31, 2, 0, a2);
              if ( (*(_BYTE *)a2 & 8) == 0 )
              {
                v14 = v34 + 4 > v37 ? Key::NextByteAlloc((Key *)&v34, 4u, a2) : (unsigned __int8 *)Block + v34;
                if ( (*(_BYTE *)a2 & 8) == 0 )
                {
                  *(_DWORD *)v14 = _byteswap_ulong(inserted);
                  v34 += 4;
                  if ( (*(_BYTE *)a2 & 8) == 0 )
                  {
                    v15 = v32;
                    v16 = (struct Instance *)(*(int (__thiscall **)(_DWORD *))(v31[0] + 56))(v31);
                    Table::AddRecords(v15, v16, 1);
                    if ( *((int *)v32 + 6) <= 0 || (v17 = *((_DWORD *)v32 + 381), v17 == -1) )
                      v18 = 0;
                    else
                      v18 = *((_DWORD *)v32 + v17 + 349);
                    if ( v18 )
                    {
                      Btree::Btree((Btree *)v30, (struct Cursor *)v31, *(struct PhysicalIndex **)(v18 + 8));
                      LOBYTE(v39) = 2;
                      Btree::AddLastKey((Btree *)v30, (const struct QuickKey *)&v34, a2);
                      Btree::~Btree((Btree *)v30);
                    }
                    v2 = v29;
                  }
                }
              }
            }
            LOBYTE(v39) = 0;
            if ( v36 == 1 && Block )
              operator delete[](Block);
            v2[4] = (struct Cursor *)Sort::Next(v2[3], (struct SortItem **)v2[4], a2);
          }
          v5 = (struct SortItem **)v2[4];
        }
        while ( v5 != *((struct SortItem ***)v2[3] + 6) );
      }
      if ( (*(_BYTE *)a2 & 1) == 0 && *((_DWORD *)a2 + 1) == -1603 )
        Err::Reset(a2);
      if ( (*(_BYTE *)a2 & 8) == 0 )
      {
        Sort::Release(v2[3]);
        v2[3] = 0;
        v19 = (*(int (__thiscall **)(struct Cursor *))(*(_DWORD *)v2[1] + 60))(v2[1]);
        if ( *(int *)(v19 + 24) <= 0 || (v20 = *(_DWORD *)(v19 + 1524), v20 == -1) || !*(_DWORD *)(v19 + 4 * v20 + 1396) )
        {
          (*(void (__thiscall **)(struct Cursor *, _DWORD, struct Err *))(*(_DWORD *)v29[1] + 8))(v29[1], 0, a2);
        }
        else
        {
          v21 = v29[1];
          v22 = *(int (__thiscall **)(struct Cursor *))(*(_DWORD *)v21 + 60);
          v28 = *(void (__thiscall **)(struct Cursor *, _DWORD, struct Err *))(*(_DWORD *)v21 + 8);
          v23 = v22(v21);
          if ( *(int *)(v23 + 24) <= 0 || (v24 = *(_DWORD *)(v23 + 1524), v24 == -1) )
            v25 = 0;
          else
            v25 = *(_DWORD **)(v23 + 4 * v24 + 1396);
          v28(v21, *v25, a2);
        }
      }
    }
  }
  Cursor::~Cursor((Cursor *)v31);
}

```

## disassembly

```asm
0x1004d040  mov     edi, edi
0x1004d042  push    ebp
0x1004d043  mov     ebp, esp
0x1004d045  push    0FFFFFFFFh
0x1004d047  push    offset ?MakeBaseTable@SortMover@@AAEXAAVErr@@@Z_SEH
0x1004d04c  mov     eax, large fs:0
0x1004d052  push    eax
0x1004d053  sub     esp, 290h
0x1004d059  mov     eax, ___security_cookie
0x1004d05e  xor     eax, ebp
0x1004d060  mov     [ebp+var_14], eax
0x1004d063  push    ebx
0x1004d064  push    esi
0x1004d065  push    edi; unsigned int
0x1004d066  push    eax; void *
0x1004d067  lea     eax, [ebp+var_C]
0x1004d06a  mov     large fs:0, eax
0x1004d070  mov     ebx, ecx
0x1004d072  mov     [ebp+var_288], ebx
0x1004d078  mov     esi, [ebp+arg_0]
0x1004d07b  lea     ecx, [ebp+var_1B4]; this
0x1004d081  push    esi; struct Err *
0x1004d082  push    dword ptr [ebx+4]; struct Cursor *
0x1004d085  call    ??0Cursor@@QAE@AAV0@AAVErr@@@Z; Cursor::Cursor(Cursor &,Err &)
0x1004d08a  mov     [ebp+var_4], 0
0x1004d091  test    byte ptr [esi], 8
0x1004d094  jnz     loc_1004D364
0x1004d09a  push    esi; struct Err *
0x1004d09b  push    0; unsigned __int16 *
0x1004d09d  lea     ecx, [ebp+var_1B4]; this
0x1004d0a3  call    ?SetCurrentIndex@Cursor@@UAEXPBGAAVErr@@@Z; Cursor::SetCurrentIndex(ushort const *,Err &)
0x1004d0a8  test    byte ptr [esi], 8
0x1004d0ab  jnz     loc_1004D364
0x1004d0b1  mov     ecx, [ebx+0Ch]; this
0x1004d0b4  push    esi; struct Err *
0x1004d0b5  call    ?First@Sort@@QAEPAPAVSortItem@@AAVErr@@@Z; Sort::First(Err &)
0x1004d0ba  mov     ecx, [ebx+0Ch]
0x1004d0bd  mov     edx, eax
0x1004d0bf  mov     [ebx+10h], edx
0x1004d0c2  cmp     edx, [ecx+18h]
0x1004d0c5  jz      loc_1004D297
0x1004d0cb  nop     dword ptr [eax+eax+00h]
0x1004d0d0  test    byte ptr [esi], 8
0x1004d0d3  jnz     loc_1004D297
0x1004d0d9  mov     eax, [edx]
0x1004d0db  movzx   ecx, word ptr [eax+2]
0x1004d0df  lea     edi, [eax+4]
0x1004d0e2  movzx   edx, word ptr [eax]
0x1004d0e5  add     edi, ecx
0x1004d0e7  add     eax, 4
0x1004d0ea  mov     [ebp+var_294], ecx
0x1004d0f0  mov     ecx, [ebp+var_180]; this
0x1004d0f6  mov     [ebp+var_28C], edx
0x1004d0fc  mov     [ebp+var_290], eax
0x1004d102  test    ecx, ecx
0x1004d104  jnz     short loc_1004D143
0x1004d106  push    828h; Size
0x1004d10b  call    ??2@YAPAXI@Z; operator new(uint)
0x1004d110  add     esp, 4
0x1004d113  mov     [ebp+var_298], eax
0x1004d119  mov     ecx, eax; this
0x1004d11b  call    ??0CopyBuff@@QAE@XZ; CopyBuff::CopyBuff(void)
0x1004d120  mov     [ebp+var_180], eax
0x1004d126  test    eax, eax
0x1004d128  jnz     short loc_1004D139
0x1004d12a  push    ecx
0x1004d12b  push    0FFFFFC0Dh
0x1004d130  mov     ecx, esi
0x1004d132  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1004d137  jmp     short loc_1004D14A
0x1004d139  push    [ebp+var_28C]
0x1004d13f  mov     ecx, eax
0x1004d141  jmp     short loc_1004D144
0x1004d143  push    edx; unsigned int
0x1004d144  push    edi; Src
0x1004d145  call    ?Refresh@CopyBuff@@QAEXPBEI@Z; CopyBuff::Refresh(uchar const *,uint)
0x1004d14a  test    byte ptr [esi], 8
0x1004d14d  jnz     loc_1004D288
0x1004d153  xor     edi, edi
0x1004d155  mov     [ebp+var_38], 20h ; ' '
0x1004d15c  lea     eax, [ebp+var_34]
0x1004d15f  mov     [ebp+var_44], edi
0x1004d162  mov     [ebp+Block], eax
0x1004d165  mov     [ebp+var_3C], edi
0x1004d168  push    esi; struct Err *
0x1004d169  lea     eax, [ebp+var_294]
0x1004d16f  mov     byte ptr [ebp+var_4], 1
0x1004d173  push    eax; struct QuickKey *
0x1004d174  lea     ecx, [ebp+var_44]; this
0x1004d177  call    ?Assign@Key@@QAEXABVQuickKey@@AAVErr@@@Z; Key::Assign(QuickKey const &,Err &)
0x1004d17c  test    byte ptr [esi], 8
0x1004d17f  jnz     loc_1004D25F
0x1004d185  push    esi
0x1004d186  push    edi
0x1004d187  push    2
0x1004d189  lea     ecx, [ebp+var_1B4]
0x1004d18f  call    ?InsertRecord@Cursor@@AAEKW4CurInsType@@KAAVErr@@@Z; Cursor::InsertRecord(CurInsType,ulong,Err &)
0x1004d194  test    byte ptr [esi], 8
0x1004d197  mov     edi, eax
0x1004d199  jnz     loc_1004D25F
0x1004d19f  mov     edx, [ebp+var_44]
0x1004d1a2  lea     ecx, [edx+4]
0x1004d1a5  cmp     ecx, [ebp+var_38]
0x1004d1a8  ja      short loc_1004D1B1
0x1004d1aa  mov     eax, [ebp+Block]
0x1004d1ad  add     eax, edx
0x1004d1af  jmp     short loc_1004D1BC
0x1004d1b1  push    esi; struct Err *
0x1004d1b2  push    4; unsigned int
0x1004d1b4  lea     ecx, [ebp+var_44]; this
0x1004d1b7  call    ?NextByteAlloc@Key@@AAEPAEIAAVErr@@@Z; Key::NextByteAlloc(uint,Err &)
0x1004d1bc  test    byte ptr [esi], 8
0x1004d1bf  jnz     loc_1004D25F
0x1004d1c5  bswap   edi
0x1004d1c7  mov     [eax], edi
0x1004d1c9  add     [ebp+var_44], 4
0x1004d1cd  test    byte ptr [esi], 8
0x1004d1d0  jnz     loc_1004D25F
0x1004d1d6  mov     eax, [ebp+var_1B4]
0x1004d1dc  mov     ebx, [ebp+var_1A8]
0x1004d1e2  mov     edi, [eax+38h]
0x1004d1e5  mov     ecx, edi
0x1004d1e7  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004d1ed  lea     ecx, [ebp+var_1B4]
0x1004d1f3  call    edi
0x1004d1f5  push    1; int
0x1004d1f7  push    eax; struct Instance *
0x1004d1f8  mov     ecx, ebx; this
0x1004d1fa  call    ?AddRecords@Table@@QAEJPAVInstance@@J@Z; Table::AddRecords(Instance *,long)
0x1004d1ff  mov     eax, [ebp+var_1A8]
0x1004d205  cmp     dword ptr [eax+18h], 0
0x1004d209  jle     short loc_1004D21F
0x1004d20b  mov     ecx, [eax+5F4h]
0x1004d211  cmp     ecx, 0FFFFFFFFh
0x1004d214  jz      short loc_1004D21F
0x1004d216  mov     eax, [eax+ecx*4+574h]
0x1004d21d  jmp     short loc_1004D221
0x1004d21f  xor     eax, eax
0x1004d221  test    eax, eax
0x1004d223  jz      short loc_1004D259
0x1004d225  push    dword ptr [eax+8]; struct PhysicalIndex *
0x1004d228  lea     eax, [ebp+var_1B4]
0x1004d22e  push    eax; struct Cursor *
0x1004d22f  lea     ecx, [ebp+var_284]; this
0x1004d235  call    ??0Btree@@QAE@PAVCursor@@PAVPhysicalIndex@@@Z; Btree::Btree(Cursor *,PhysicalIndex *)
0x1004d23a  push    esi; struct Err *
0x1004d23b  lea     eax, [ebp+var_44]
0x1004d23e  mov     byte ptr [ebp+var_4], 2
0x1004d242  push    eax; struct QuickKey *
0x1004d243  lea     ecx, [ebp+var_284]; this
0x1004d249  call    ?AddLastKey@Btree@@QAEXABVQuickKey@@AAVErr@@@Z; Btree::AddLastKey(QuickKey const &,Err &)
0x1004d24e  lea     ecx, [ebp+var_284]; this
0x1004d254  call    ??1Btree@@QAE@XZ; Btree::~Btree(void)
0x1004d259  mov     ebx, [ebp+var_288]
0x1004d25f  mov     byte ptr [ebp+var_4], 0
0x1004d263  cmp     [ebp+var_3C], 1
0x1004d267  jnz     short loc_1004D279
0x1004d269  mov     eax, [ebp+Block]
0x1004d26c  test    eax, eax
0x1004d26e  jz      short loc_1004D279
0x1004d270  push    eax; Block
0x1004d271  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1004d276  add     esp, 4
0x1004d279  mov     ecx, [ebx+0Ch]; this
0x1004d27c  push    esi; struct Err *
0x1004d27d  push    dword ptr [ebx+10h]; struct SortItem **
0x1004d280  call    ?Next@Sort@@QAEPAPAVSortItem@@PAPAV2@AAVErr@@@Z; Sort::Next(SortItem * *,Err &)
0x1004d285  mov     [ebx+10h], eax
0x1004d288  mov     eax, [ebx+0Ch]
0x1004d28b  mov     edx, [ebx+10h]
0x1004d28e  cmp     edx, [eax+18h]
0x1004d291  jnz     loc_1004D0D0
0x1004d297  test    byte ptr [esi], 1
0x1004d29a  jnz     short loc_1004D2AC
0x1004d29c  cmp     dword ptr [esi+4], 0FFFFF9BDh
0x1004d2a3  jnz     short loc_1004D2AC
0x1004d2a5  mov     ecx, esi; this
0x1004d2a7  call    ?Reset@Err@@QAEXXZ; Err::Reset(void)
0x1004d2ac  test    byte ptr [esi], 8
0x1004d2af  jnz     loc_1004D364
0x1004d2b5  mov     ecx, [ebx+0Ch]; this
0x1004d2b8  call    ?Release@Sort@@QAEIXZ; Sort::Release(void)
0x1004d2bd  mov     dword ptr [ebx+0Ch], 0
0x1004d2c4  mov     ebx, [ebx+4]
0x1004d2c7  mov     eax, [ebx]
0x1004d2c9  mov     edi, [eax+3Ch]
0x1004d2cc  mov     ecx, edi
0x1004d2ce  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004d2d4  mov     ecx, ebx
0x1004d2d6  call    edi
0x1004d2d8  cmp     dword ptr [eax+18h], 0
0x1004d2dc  jle     short loc_1004D347
0x1004d2de  mov     ecx, [eax+5F4h]
0x1004d2e4  cmp     ecx, 0FFFFFFFFh
0x1004d2e7  jz      short loc_1004D347
0x1004d2e9  cmp     dword ptr [eax+ecx*4+574h], 0
0x1004d2f1  jz      short loc_1004D347
0x1004d2f3  mov     edi, [ebp+var_288]
0x1004d2f9  mov     ebx, [edi+4]
0x1004d2fc  mov     eax, [ebx]
0x1004d2fe  mov     ecx, [eax+8]
0x1004d301  mov     edi, [eax+3Ch]
0x1004d304  mov     [ebp+var_28C], ecx
0x1004d30a  mov     ecx, edi
0x1004d30c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004d312  mov     ecx, ebx
0x1004d314  call    edi
0x1004d316  cmp     dword ptr [eax+18h], 0
0x1004d31a  jle     short loc_1004D330
0x1004d31c  mov     ecx, [eax+5F4h]
0x1004d322  cmp     ecx, 0FFFFFFFFh
0x1004d325  jz      short loc_1004D330
0x1004d327  mov     eax, [eax+ecx*4+574h]
0x1004d32e  jmp     short loc_1004D332
0x1004d330  xor     eax, eax
0x1004d332  push    esi; unsigned int
0x1004d333  push    dword ptr [eax]; void *
0x1004d335  mov     esi, [ebp+var_28C]
0x1004d33b  mov     ecx, esi
0x1004d33d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004d343  mov     ecx, ebx
0x1004d345  jmp     short loc_1004D362
0x1004d347  mov     edi, [ebp+var_288]
0x1004d34d  push    esi; unsigned int
0x1004d34e  push    0; void *
0x1004d350  mov     edi, [edi+4]
0x1004d353  mov     eax, [edi]
0x1004d355  mov     esi, [eax+8]
0x1004d358  mov     ecx, esi
0x1004d35a  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1004d360  mov     ecx, edi
0x1004d362  call    esi
0x1004d364  lea     ecx, [ebp+var_1B4]; this
0x1004d36a  call    ??1Cursor@@UAE@XZ; Cursor::~Cursor(void)
0x1004d36f  mov     ecx, [ebp+var_C]
0x1004d372  mov     large fs:0, ecx
0x1004d379  pop     ecx
0x1004d37a  pop     edi
0x1004d37b  pop     esi
0x1004d37c  pop     ebx
0x1004d37d  mov     ecx, [ebp+var_14]
0x1004d380  xor     ecx, ebp; StackCookie
0x1004d382  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1004d387  mov     esp, ebp
0x1004d389  pop     ebp
0x1004d38a  retn    4
0x100616d0  lea     ecx, [ebp+var_1B4]; this
0x100616d6  jmp     ??1Cursor@@UAE@XZ; Cursor::~Cursor(void)
0x100616db  lea     ecx, [ebp+var_44]; this
0x100616de  jmp     ??1Key@@QAE@XZ; Key::~Key(void)
0x100616e3  lea     ecx, [ebp+var_284]; this
0x100616e9  jmp     ??1Btree@@QAE@XZ; Btree::~Btree(void)
0x100616f3  nop
0x100616f4  nop
0x100616f5  mov     edx, [esp-4+arg_4]
0x100616f9  lea     eax, [edx+0Ch]
0x100616fc  mov     ecx, [edx-2A0h]
0x10061702  xor     ecx, eax; StackCookie
0x10061704  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061709  mov     ecx, [edx-8]
0x1006170c  xor     ecx, eax; StackCookie
0x1006170e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061713  mov     eax, offset stru_10064068
0x10061718  jmp     ___CxxFrameHandler3
```
