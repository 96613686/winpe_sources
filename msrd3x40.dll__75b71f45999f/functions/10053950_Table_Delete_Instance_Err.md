# Table::Delete(Instance *,Err &)

- ea: `0x10053950`
- end: `0x10053cb3`
- name: `?Delete@Table@@QAEXPAVInstance@@AAVErr@@@Z`
- size: `867`
- prototype: `void __thiscall(Table *__hidden this, struct Instance *, struct Err *)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10035f50`
- `0x100364e0`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10025db0`
- `0x10025ee0`
- `0x10025f50`
- `0x10044860`
- `0x10044950`
- `0x100518a0`
- `0x10052140`
- `0x10053400`
- `0x100536a0`
- `0x10053950`
- `0x10053fa0`
- `0x10055ed0`
- `0x10056b10`
- `0x10057b70`
- `0x10057ce0`
- `0x10058bb0`
- `0x100591e0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall Table::Delete(struct Database **this, struct Instance *a2, void **a3)
{
  struct Err *v4; // esi
  Err *v5; // ecx
  const unsigned __int16 *v6; // edi
  int v7; // ecx
  int v8; // edi
  Table *v9; // ecx
  int v10; // eax
  struct Database *v11; // eax
  Table *v12; // edi
  int v13; // ecx
  unsigned int v14; // edx
  struct Instance *v15; // edi
  struct Cursor *MSORecord; // eax
  struct Session *v17; // edi
  int v18; // eax
  int v19; // esi
  unsigned int v20; // ecx
  int v21; // [esp-8h] [ebp-4Ch]
  int v22; // [esp-4h] [ebp-48h]
  Table *Block; // [esp+24h] [ebp-20h]
  int v24; // [esp+28h] [ebp-1Ch]
  struct Database *v25; // [esp+2Ch] [ebp-18h]
  struct Cursor *v26; // [esp+2Ch] [ebp-18h]
  _DWORD *v27; // [esp+30h] [ebp-14h]
  struct Session *v28; // [esp+34h] [ebp-10h]

  v4 = (struct Err *)a3;
  v28 = (struct Session *)*((_DWORD *)a2 + 3);
  Table::SetNameFromId((Table *)this, (char)this[10], a2, (struct Err *)a3);
  if ( (this[11] != (struct Database *)2 || this[19] != (struct Database *)1)
    && (this[12] != (struct Database *)2 || this[19] != (struct Database *)1) )
  {
    v6 = (const unsigned __int16 *)*this;
    if ( ((unsigned int)*a3 & 0xFFFFFFFE) != 0 )
    {
      if ( a3[3] )
        operator delete[](a3[3]);
      if ( a3[4] )
        operator delete[](a3[4]);
    }
    *a3 = (void *)8;
    a3[1] = (void *)-1304;
    a3[2] = (void *)-8154;
    a3[3] = 0;
    Err::CopyString(v5, (unsigned __int16 **)a3 + 4, v6);
  }
  if ( (*(_BYTE *)a3 & 8) != 0 )
    return;
  if ( Table::FindAnyReference(this, v21, v22) )
    Err::SetError(a3, -1051, v7);
  if ( (*(_BYTE *)a3 & 8) != 0 )
    return;
  v8 = 0;
  Session::BeginTransaction(v28, 1, a3);
  if ( (*(_BYTE *)a3 & 8) != 0 )
    return;
  this[17] = (struct Database *)*((_DWORD *)v28 + 14);
  if ( (*(_BYTE *)a3 & 8) != 0 )
    return;
  while ( 1 )
  {
    v10 = v8;
    v24 = ++v8;
    if ( v10 < 0 )
      break;
    if ( v10 >= (int)this[6] )
      break;
    if ( this[v10 + 381] == (struct Database *)-1 )
      break;
    _mm_lfence();
    v11 = this[(_DWORD)this[v10 + 381] + 349];
    v25 = v11;
    if ( !v11 )
      break;
    if ( *((_BYTE *)v11 + 41) == 2 )
    {
      v12 = (Table *)this;
      v27 = (_DWORD *)((char *)v11 + 48);
      if ( *((struct Database **)v11 + 12) != this[10] )
      {
        v13 = 0;
        v14 = *((_DWORD *)this[9] + 14);
        if ( !v14 )
          goto LABEL_27;
        v25 = v11;
        while ( 1 )
        {
          v4 = (struct Err *)a3;
          if ( *(_DWORD *)(*(_DWORD *)(4 * v13 + *((_DWORD *)this[9] + 12)) + 40) == *v27 )
            break;
          if ( ++v13 >= v14 )
            goto LABEL_27;
        }
        v12 = *(Table **)(4 * v13 + *((_DWORD *)this[9] + 12));
        if ( v12 )
        {
          Table::CompatibleMode(v12, v28, 2, a3);
        }
        else
        {
LABEL_27:
          Block = (Table *)operator new(0x778u);
          v12 = Table::Table(Block, this[9], v4);
          if ( !v12 && *(int *)v4 < 8 )
          {
            if ( (*(_DWORD *)v4 & 0xFFFFFFFE) != 0 )
            {
              if ( *((_DWORD *)v4 + 3) )
                operator delete[](*((void **)v4 + 3));
              if ( *((_DWORD *)v4 + 4) )
                operator delete[](*((void **)v4 + 4));
            }
            *(_DWORD *)v4 = 8;
            *((_DWORD *)v4 + 1) = -1011;
            *((_DWORD *)v4 + 2) = 0;
            *((_DWORD *)v4 + 3) = 0;
            *((_DWORD *)v4 + 4) = 0;
          }
          if ( (*(_BYTE *)v4 & 8) != 0 )
            goto LABEL_44;
          Table::Open(v12, a2, *v27, 2, v4);
        }
        if ( (*(_BYTE *)v4 & 8) != 0 )
          goto LABEL_44;
        v11 = v25;
      }
      ++*((_DWORD *)v12 + 19);
      Table::DeleteIndex((int)v12, a2, **((unsigned __int16 ***)v12 + *((_DWORD *)v11 + 11) + 349), v4, 1);
      Table::Release(v12, a2);
      v8 = v24;
    }
  }
  if ( (*(_BYTE *)v4 & 8) == 0 )
  {
    v15 = a2;
    Table::FreeAllocations((Table *)this, *((struct IAccMeth **)a2 + 15), v4);
    goto LABEL_45;
  }
LABEL_44:
  v15 = a2;
LABEL_45:
  if ( (*(_BYTE *)v4 & 8) != 0 )
    goto LABEL_52;
  MSORecord = Table::FindMSORecord(v9, (char)this[10], v15, v4);
  v26 = MSORecord;
  if ( !MSORecord )
  {
    Err::SetError(v4, -1305, -8300, L"MSysObjects", 0, v9);
    MSORecord = 0;
  }
  if ( (*(_BYTE *)v4 & 8) != 0
    || ((*(void (__thiscall **)(struct Cursor *, struct Err *))(*(_DWORD *)MSORecord + 32))(v26, v4),
        (*(_BYTE *)v4 & 8) != 0) )
  {
LABEL_52:
    v17 = v28;
  }
  else
  {
    v17 = v28;
    Session::CommitTransaction(v28, (void **)v4, 0);
    if ( (*(_BYTE *)v4 & 8) != 0 )
      goto LABEL_54;
    this[17] = (struct Database *)-1;
  }
  if ( (*(_BYTE *)v4 & 8) != 0 )
  {
LABEL_54:
    Table::AbortTransaction((Table *)this, v17, v9);
    if ( (*(_BYTE *)v4 & 8) != 0 )
      return;
  }
  v18 = 0;
  v19 = *((_DWORD *)v28 + 14);
  this[14] = (struct Database *)v19;
  v20 = *((_DWORD *)v28 + 5);
  if ( v20 )
  {
    while ( *(struct Database ***)(*((_DWORD *)v28 + 3) + 4 * v18) != this )
    {
      if ( ++v18 >= v20 )
        goto LABEL_58;
    }
  }
  else
  {
LABEL_58:
    if ( v18 == v20 && v19 > 0 )
      Table::AddNotify((Table *)this, v28);
  }
}

```

## disassembly

```asm
0x10053950  mov     edi, edi
0x10053952  push    ebp
0x10053953  mov     ebp, esp
0x10053955  push    0FFFFFFFFh
0x10053957  push    offset ?Delete@Table@@QAEXPAVInstance@@AAVErr@@@Z_SEH
0x1005395c  mov     eax, large fs:0
0x10053962  push    eax
0x10053963  sub     esp, 28h
0x10053966  push    ebx
0x10053967  push    esi
0x10053968  push    edi
0x10053969  mov     eax, ___security_cookie
0x1005396e  xor     eax, ebp
0x10053970  push    eax; unsigned int
0x10053971  lea     eax, [ebp+var_C]
0x10053974  mov     large fs:0, eax
0x1005397a  mov     ebx, ecx
0x1005397c  mov     ecx, [ebp+arg_0]
0x1005397f  mov     esi, [ebp+arg_4]
0x10053982  push    esi; struct Err *
0x10053983  push    ecx; struct Instance *
0x10053984  mov     eax, [ecx+0Ch]
0x10053987  mov     ecx, ebx; this
0x10053989  push    dword ptr [ebx+28h]; char
0x1005398c  mov     [ebp+var_10], eax
0x1005398f  call    ?SetNameFromId@Table@@AAEXKPAVInstance@@AAVErr@@@Z; Table::SetNameFromId(ulong,Instance *,Err &)
0x10053994  cmp     dword ptr [ebx+2Ch], 2
0x10053998  jnz     short loc_100539A0
0x1005399a  cmp     dword ptr [ebx+4Ch], 1
0x1005399e  jz      short loc_10053A02
0x100539a0  cmp     dword ptr [ebx+30h], 2
0x100539a4  jnz     short loc_100539AC
0x100539a6  cmp     dword ptr [ebx+4Ch], 1
0x100539aa  jz      short loc_10053A02
0x100539ac  test    dword ptr [esi], 0FFFFFFFEh
0x100539b2  mov     edi, [ebx]
0x100539b4  jz      short loc_100539D6
0x100539b6  mov     eax, [esi+0Ch]
0x100539b9  test    eax, eax
0x100539bb  jz      short loc_100539C6
0x100539bd  push    eax; Block
0x100539be  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100539c3  add     esp, 4
0x100539c6  mov     eax, [esi+10h]
0x100539c9  test    eax, eax
0x100539cb  jz      short loc_100539D6
0x100539cd  push    eax; Block
0x100539ce  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100539d3  add     esp, 4
0x100539d6  mov     dword ptr [esi], 8
0x100539dc  mov     dword ptr [esi+4], 0FFFFFAE8h
0x100539e3  mov     dword ptr [esi+8], 0FFFFE026h
0x100539ea  push    edi; unsigned __int16 *
0x100539eb  lea     eax, [esi+10h]
0x100539ee  mov     dword ptr [esi+0Ch], 0
0x100539f5  push    eax; unsigned __int16 **
0x100539f6  mov     [ebp+var_4], 0FFFFFFFFh
0x100539fd  call    ?CopyString@Err@@AAEXAAPAGPBG@Z; Err::CopyString(ushort * &,ushort const *)
0x10053a02  test    byte ptr [esi], 8
0x10053a05  jnz     loc_10053C9F
0x10053a0b  sub     esp, 8
0x10053a0e  mov     ecx, ebx
0x10053a10  call    ?FindAnyReference@Table@@QAEPAVIndex@@W4TblFindRef@@E@Z; Table::FindAnyReference(TblFindRef,uchar)
0x10053a15  test    eax, eax
0x10053a17  jz      short loc_10053A26
0x10053a19  push    ecx
0x10053a1a  push    0FFFFFBE5h
0x10053a1f  mov     ecx, esi
0x10053a21  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10053a26  test    byte ptr [esi], 8
0x10053a29  jnz     loc_10053C9F
0x10053a2f  mov     ecx, [ebp+var_10]
0x10053a32  xor     edi, edi
0x10053a34  push    esi
0x10053a35  push    1
0x10053a37  call    ?BeginTransaction@Session@@QAEXW4TransactionType@@AAVErr@@@Z; Session::BeginTransaction(TransactionType,Err &)
0x10053a3c  test    byte ptr [esi], 8
0x10053a3f  jnz     loc_10053C9F
0x10053a45  mov     eax, [ebp+var_10]
0x10053a48  mov     eax, [eax+38h]
0x10053a4b  mov     [ebx+44h], eax
0x10053a4e  test    byte ptr [esi], 8
0x10053a51  jnz     loc_10053C9F
0x10053a57  mov     eax, edi
0x10053a59  inc     edi
0x10053a5a  mov     [ebp+var_1C], edi
0x10053a5d  test    eax, eax
0x10053a5f  js      loc_10053BD9
0x10053a65  cmp     eax, [ebx+18h]
0x10053a68  jge     loc_10053BD9
0x10053a6e  cmp     dword ptr [ebx+eax*4+5F4h], 0FFFFFFFFh
0x10053a76  jz      loc_10053BD9
0x10053a7c  lfence
0x10053a7f  mov     eax, [ebx+eax*4+5F4h]
0x10053a86  mov     eax, [ebx+eax*4+574h]
0x10053a8d  mov     [ebp+var_18], eax
0x10053a90  test    eax, eax
0x10053a92  jz      loc_10053BD9
0x10053a98  cmp     byte ptr [eax+29h], 2
0x10053a9c  jnz     short loc_10053A57
0x10053a9e  lea     ecx, [eax+30h]
0x10053aa1  mov     edi, ebx
0x10053aa3  mov     [ebp+var_14], ecx
0x10053aa6  mov     ecx, [ecx]
0x10053aa8  cmp     ecx, [ebx+28h]
0x10053aab  jz      loc_10053B8B
0x10053ab1  mov     edi, [ebx+24h]
0x10053ab4  xor     ecx, ecx
0x10053ab6  mov     edx, [edi+38h]
0x10053ab9  test    edx, edx
0x10053abb  jz      short loc_10053AED
0x10053abd  mov     [ebp+var_18], eax
0x10053ac0  mov     esi, [ebx+24h]
0x10053ac3  lea     edi, ds:0[ecx*4]
0x10053aca  mov     eax, [esi+30h]
0x10053acd  mov     eax, [edi+eax]
0x10053ad0  mov     edi, [ebp+var_14]
0x10053ad3  mov     esi, [edi]
0x10053ad5  lea     edi, ds:0[ecx*4]
0x10053adc  cmp     [eax+28h], esi
0x10053adf  mov     esi, [ebp+arg_4]
0x10053ae2  jz      loc_10053BB9
0x10053ae8  inc     ecx
0x10053ae9  cmp     ecx, edx
0x10053aeb  jb      short loc_10053AC0
0x10053aed  push    778h; Size
0x10053af2  call    ??2@YAPAXI@Z; operator new(uint)
0x10053af7  add     esp, 4
0x10053afa  mov     [ebp+Block], eax
0x10053afd  push    esi; struct Err *
0x10053afe  mov     [ebp+var_4], 1
0x10053b05  mov     ecx, eax; this
0x10053b07  push    dword ptr [ebx+24h]; struct Database *
0x10053b0a  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x10053b0f  mov     edi, eax
0x10053b11  mov     [ebp+var_4], 0FFFFFFFFh
0x10053b18  test    edi, edi
0x10053b1a  jnz     short loc_10053B6C
0x10053b1c  mov     eax, [esi]
0x10053b1e  cmp     eax, 8
0x10053b21  jge     short loc_10053B6C
0x10053b23  test    eax, 0FFFFFFFEh
0x10053b28  jz      short loc_10053B4A
0x10053b2a  mov     eax, [esi+0Ch]
0x10053b2d  test    eax, eax
0x10053b2f  jz      short loc_10053B3A
0x10053b31  push    eax; Block
0x10053b32  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10053b37  add     esp, 4
0x10053b3a  mov     eax, [esi+10h]
0x10053b3d  test    eax, eax
0x10053b3f  jz      short loc_10053B4A
0x10053b41  push    eax; Block
0x10053b42  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10053b47  add     esp, 4
0x10053b4a  mov     dword ptr [esi], 8
0x10053b50  mov     dword ptr [esi+4], 0FFFFFC0Dh
0x10053b57  mov     dword ptr [esi+8], 0
0x10053b5e  mov     dword ptr [esi+0Ch], 0
0x10053b65  mov     dword ptr [esi+10h], 0
0x10053b6c  test    byte ptr [esi], 8
0x10053b6f  jnz     short loc_10053BEE
0x10053b71  mov     eax, [ebp+var_14]
0x10053b74  mov     ecx, edi
0x10053b76  push    esi
0x10053b77  push    2
0x10053b79  push    dword ptr [eax]
0x10053b7b  push    [ebp+arg_0]
0x10053b7e  call    ?Open@Table@@QAEXPAVInstance@@KW4TblMode@@AAVErr@@@Z; Table::Open(Instance *,ulong,TblMode,Err &)
0x10053b83  test    byte ptr [esi], 8
0x10053b86  jnz     short loc_10053BEE
0x10053b88  mov     eax, [ebp+var_18]
0x10053b8b  inc     dword ptr [edi+4Ch]
0x10053b8e  mov     ecx, edi
0x10053b90  mov     eax, [eax+2Ch]
0x10053b93  push    1
0x10053b95  push    esi
0x10053b96  mov     eax, [edi+eax*4+574h]
0x10053b9d  push    dword ptr [eax]
0x10053b9f  push    [ebp+arg_0]
0x10053ba2  call    ?DeleteIndex@Table@@QAEXPAVInstance@@PBGAAVErr@@W4TblRefOrIdx@@@Z; Table::DeleteIndex(Instance *,ushort const *,Err &,TblRefOrIdx)
0x10053ba7  push    [ebp+arg_0]; struct Instance *
0x10053baa  mov     ecx, edi; this
0x10053bac  call    ?Release@Table@@QAEJPAVInstance@@@Z; Table::Release(Instance *)
0x10053bb1  mov     edi, [ebp+var_1C]
0x10053bb4  jmp     loc_10053A57
0x10053bb9  mov     eax, [ebx+24h]
0x10053bbc  mov     eax, [eax+30h]
0x10053bbf  mov     edi, [edi+eax]
0x10053bc2  test    edi, edi
0x10053bc4  jz      loc_10053AED
0x10053bca  push    esi
0x10053bcb  push    2
0x10053bcd  push    [ebp+var_10]
0x10053bd0  mov     ecx, edi
0x10053bd2  call    ?CompatibleMode@Table@@QAEXPAVSession@@W4TblMode@@AAVErr@@@Z; Table::CompatibleMode(Session *,TblMode,Err &)
0x10053bd7  jmp     short loc_10053B83
0x10053bd9  test    byte ptr [esi], 8
0x10053bdc  jnz     short loc_10053BEE
0x10053bde  mov     edi, [ebp+arg_0]
0x10053be1  mov     ecx, ebx; this
0x10053be3  push    esi; struct Err *
0x10053be4  push    dword ptr [edi+3Ch]; struct IAccMeth *
0x10053be7  call    ?FreeAllocations@Table@@AAEXPAVIAccMeth@@AAVErr@@@Z; Table::FreeAllocations(IAccMeth *,Err &)
0x10053bec  jmp     short loc_10053BF1
0x10053bee  mov     edi, [ebp+arg_0]
0x10053bf1  test    byte ptr [esi], 8
0x10053bf4  jnz     short loc_10053C5A
0x10053bf6  push    esi; struct Err *
0x10053bf7  push    edi; struct Instance *
0x10053bf8  push    dword ptr [ebx+28h]; char
0x10053bfb  call    ?FindMSORecord@Table@@AAEPAVCursor@@KPAVInstance@@AAVErr@@@Z; Table::FindMSORecord(ulong,Instance *,Err &)
0x10053c00  mov     [ebp+var_18], eax
0x10053c03  test    eax, eax
0x10053c05  jnz     short loc_10053C22
0x10053c07  push    ecx
0x10053c08  push    eax
0x10053c09  push    offset aMsysobjects; "MSysObjects"
0x10053c0e  push    0FFFFDF94h
0x10053c13  push    0FFFFFAE7h
0x10053c18  mov     ecx, esi
0x10053c1a  call    ?SetError@Err@@QAEXJJPBG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort const *,ushort const *,ErrAssert)
0x10053c1f  mov     eax, [ebp+var_18]
0x10053c22  test    byte ptr [esi], 8
0x10053c25  jnz     short loc_10053C5A
0x10053c27  mov     eax, [eax]
0x10053c29  push    esi; void *
0x10053c2a  mov     edi, [eax+20h]
0x10053c2d  mov     ecx, edi
0x10053c2f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10053c35  mov     ecx, [ebp+var_18]
0x10053c38  call    edi
0x10053c3a  test    byte ptr [esi], 8
0x10053c3d  jnz     short loc_10053C5A
0x10053c3f  mov     edi, [ebp+var_10]
0x10053c42  mov     ecx, edi; this
0x10053c44  push    0; unsigned int
0x10053c46  push    esi; struct Err *
0x10053c47  call    ?CommitTransaction@Session@@QAEXAAVErr@@K@Z; Session::CommitTransaction(Err &,ulong)
0x10053c4c  test    byte ptr [esi], 8
0x10053c4f  jnz     short loc_10053C62
0x10053c51  mov     dword ptr [ebx+44h], 0FFFFFFFFh
0x10053c58  jmp     short loc_10053C5D
0x10053c5a  mov     edi, [ebp+var_10]
0x10053c5d  test    byte ptr [esi], 8
0x10053c60  jz      short loc_10053C70
0x10053c62  push    ecx; struct Err *
0x10053c63  push    edi; struct Session *
0x10053c64  mov     ecx, ebx; this
0x10053c66  call    ?AbortTransaction@Table@@AAEXPAVSession@@AAVErr@@@Z; Table::AbortTransaction(Session *,Err &)
0x10053c6b  test    byte ptr [esi], 8
0x10053c6e  jnz     short loc_10053C9F
0x10053c70  mov     edi, [ebp+var_10]
0x10053c73  xor     eax, eax
0x10053c75  mov     esi, [edi+38h]
0x10053c78  mov     [ebx+38h], esi
0x10053c7b  mov     ecx, [edi+14h]
0x10053c7e  test    ecx, ecx
0x10053c80  jz      short loc_10053C8F
0x10053c82  mov     edx, [edi+0Ch]
0x10053c85  cmp     [edx+eax*4], ebx
0x10053c88  jz      short loc_10053C9F
0x10053c8a  inc     eax
0x10053c8b  cmp     eax, ecx
0x10053c8d  jb      short loc_10053C85
0x10053c8f  cmp     eax, ecx
0x10053c91  jnz     short loc_10053C9F
0x10053c93  test    esi, esi
0x10053c95  jle     short loc_10053C9F
0x10053c97  push    edi; struct Session *
0x10053c98  mov     ecx, ebx; this
0x10053c9a  call    ?AddNotify@Table@@AAEXPAVSession@@@Z; Table::AddNotify(Session *)
0x10053c9f  mov     ecx, [ebp+var_C]
0x10053ca2  mov     large fs:0, ecx
0x10053ca9  pop     ecx
0x10053caa  pop     edi
0x10053cab  pop     esi
0x10053cac  pop     ebx
0x10053cad  mov     esp, ebp
0x10053caf  pop     ebp
0x10053cb0  retn    8
0x10061d00  lea     ecx, [ebp+var_34]; this
0x10061d03  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10061d08  push    778h; unsigned int
0x10061d0d  mov     eax, [ebp+Block]
0x10061d10  push    eax; Block
0x10061d11  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10061d16  add     esp, 8
0x10061d19  retn
0x10061d1f  nop
0x10061d20  nop
0x10061d21  mov     edx, [esp-4+arg_4]
0x10061d25  lea     eax, [edx+0Ch]
0x10061d28  mov     ecx, [edx-38h]
0x10061d2b  xor     ecx, eax; StackCookie
0x10061d2d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061d32  mov     eax, offset stru_10064510
0x10061d37  jmp     ___CxxFrameHandler3
```
