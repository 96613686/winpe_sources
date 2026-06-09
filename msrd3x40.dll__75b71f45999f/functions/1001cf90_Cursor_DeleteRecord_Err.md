# Cursor::DeleteRecord(Err &)

- ea: `0x1001cf90`
- end: `0x1001d32e`
- name: `?DeleteRecord@Cursor@@AAEXAAVErr@@@Z`
- size: `926`
- prototype: `void __thiscall(Cursor *__hidden this, struct Err *)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, installer_update`

## callers

- `0x1001b180`
- `0x1001ebc0`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x1000f890`
- `0x10010580`
- `0x1001cf90`
- `0x1001d640`
- `0x10023730`
- `0x10023fc0`
- `0x10024ee0`
- `0x10025030`
- `0x100251a0`
- `0x10025ee0`
- `0x100471e0`
- `0x100473e0`
- `0x10047a60`
- `0x100481d0`
- `0x10048670`
- `0x1005d1d0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall Cursor::DeleteRecord(Cursor *this, struct Err *a2)
{
  Bitmap *v2; // ebx
  int v3; // esi
  struct Err *v4; // edi
  bool v5; // zf
  int v6; // ecx
  struct Transaction **v7; // eax
  unsigned int v8; // esi
  int v9; // edx
  unsigned int v10; // ecx
  char *v11; // edi
  int v12; // ebx
  int Bitmap; // eax
  unsigned int v14; // ecx
  unsigned int v15; // edx
  int v16; // edx
  unsigned int v17; // [esp-4h] [ebp-68h]
  unsigned int v18[3]; // [esp+10h] [ebp-54h] BYREF
  void *Block; // [esp+1Ch] [ebp-48h]
  void *v20; // [esp+20h] [ebp-44h]
  unsigned __int8 *v21; // [esp+24h] [ebp-40h] BYREF
  unsigned int v22; // [esp+28h] [ebp-3Ch]
  unsigned int v23; // [esp+2Ch] [ebp-38h]
  int v24; // [esp+30h] [ebp-34h]
  int v25; // [esp+34h] [ebp-30h] BYREF
  _WORD *v26; // [esp+38h] [ebp-2Ch]
  Bitmap *v27; // [esp+44h] [ebp-20h]
  unsigned int v28; // [esp+4Ch] [ebp-18h]
  unsigned int v29; // [esp+50h] [ebp-14h]
  unsigned int v30; // [esp+54h] [ebp-10h]
  int v31; // [esp+60h] [ebp-4h]

  v2 = this;
  v27 = this;
  v3 = 0;
  v29 = *((_DWORD *)this + 6);
  v25 = 0;
  v26 = 0;
  v4 = a2;
  v31 = 0;
  v24 = *((_DWORD *)this + 90);
  v5 = (*(_BYTE *)a2 & 8) == 0;
  v30 = v29 >> 8;
  v28 = (unsigned int)this + 40;
  if ( v5 )
  {
    Database::ReadPageForUpdate(
      *(Database **)(*((_DWORD *)this + 10) + 8),
      (struct PageRef *)&v25,
      v29 >> 8,
      a2,
      *((struct Transaction **)this + 10),
      0);
    v3 = v25;
  }
  else
  {
    v28 = (unsigned int)this + 40;
  }
  if ( (*(_BYTE *)a2 & 8) == 0 )
  {
    if ( *v26 == 265 )
      Err::SetError(a2, -1017, 265);
    if ( (*(_BYTE *)a2 & 8) == 0 )
    {
      switch ( DataPage::RecordAddress(&v25, v29, &v21) )
      {
        case 0:
          break;
        case 1:
          v17 = *((_DWORD *)v2 + 6);
          v29 = *(_DWORD *)v21;
          v30 = v29 >> 8;
          DataPage::Delete((DataPage *)&v25, v17);
          *(_DWORD *)(v3 + 4 * *(_DWORD *)(v3 + 24) + 28) |= 8u;
          v7 = (struct Transaction **)v28;
          ++*(_DWORD *)(v3 + 64);
          Database::ReadPageForUpdate(*((Database **)*v7 + 2), (struct PageRef *)&v25, v30, a2, *v7, 0);
          if ( (*(_BYTE *)a2 & 8) != 0 )
            goto LABEL_45;
          *(_DWORD *)(v25 + 4 * *(_DWORD *)(v25 + 24) + 28) = *(_DWORD *)(v25 + 4 * *(_DWORD *)(v25 + 24) + 28)
                                                            & 0xFFFFFF0F
                                                            | 0x60;
          if ( DataPage::RecordAddress(&v25, v29, &v21) != 2 )
            Database::MarkCorrupt(*(Database **)(*((_DWORD *)v2 + 1) + 16), a2);
          break;
        case 3:
          Err::SetError(a2, -1017, v6);
          break;
        default:
          Err::SetError(a2, -1045, v6);
          break;
      }
    }
  }
  v8 = v30;
  if ( (*(_BYTE *)a2 & 8) != 0 )
    goto LABEL_45;
  if ( !DataPage::WillFit(&v25, v22, a2) )
  {
    if ( (*(_BYTE *)a2 & 8) != 0 )
      goto LABEL_45;
    AbstractSpacemap::AddPage(v8, a2, (char *)v2 + 236);
  }
  if ( (*(_BYTE *)a2 & 8) == 0 )
  {
    Cursor::DeleteFromIndexes(v2, v21, v22, v23, *((_DWORD *)v2 + 6), a2);
    if ( (*(_BYTE *)a2 & 8) == 0 )
    {
      v9 = *((_DWORD *)v2 + 3);
      *((_DWORD *)v2 + 24) = &v21;
      v10 = *(_DWORD *)(v9 + 368);
      v28 = v10;
      if ( v10 != -1 )
      {
        v11 = (char *)v2 + 96;
        do
        {
          if ( v10 > 0xFE )
            v12 = 0;
          else
            v12 = *(_DWORD *)(v9 + 4 * v10 + 376);
          if ( (*(unsigned __int8 (__thiscall **)(int))(*(_DWORD *)v12 + 16))(v12) == 12
            || (*(unsigned __int8 (__thiscall **)(int))(*(_DWORD *)v12 + 16))(v12) == 11 )
          {
            v18[0] = 1;
            LOBYTE(v31) = 1;
            (*(void (__thiscall **)(int, char *, unsigned int *))(*(_DWORD *)v12 + 76))(v12, v11, v18);
            LOBYTE(v31) = 0;
            if ( (v18[0] & 0xFFFFFFFE) != 0 )
            {
              if ( Block )
                operator delete[](Block);
              if ( v20 )
                operator delete[](v20);
            }
          }
          v2 = v27;
          v9 = *((_DWORD *)v27 + 3);
          v10 = *(_DWORD *)(*(_DWORD *)(v9 + 360) + 8 * v28);
          v28 = v10;
        }
        while ( v10 != -1 );
        v4 = a2;
      }
      if ( (*(_BYTE *)v4 & 8) == 0 )
      {
        DataPage::Delete((DataPage *)&v25, v29);
        if ( (unsigned __int16)(2 * (v26[4] + 5)) + (unsigned int)(unsigned __int16)v26[1] < 0x800 )
        {
LABEL_44:
          v16 = v25;
          *(_DWORD *)(v25 + 4 * *(_DWORD *)(v25 + 24) + 28) = *(_DWORD *)(v25 + 4 * *(_DWORD *)(v25 + 24) + 28)
                                                            & 0xFFFFFF0F
                                                            | 0x50;
          *(_DWORD *)(v16 + 4 * *(_DWORD *)(v16 + 24) + 28) |= 8u;
          ++*(_DWORD *)(v16 + 64);
          goto LABEL_46;
        }
        v18[0] = 1;
        LOBYTE(v31) = 2;
        *v26 = 265;
        AbstractSpacemap::Setup((char *)v2 + 236, 1, v4);
        if ( (*(_BYTE *)v4 & 8) == 0 )
        {
          Bitmap = AbstractSpacemap::GetBitmap((char *)v2 + 236, v30, 2, v4);
          v14 = v30;
          if ( Bitmap != 1
            || (v15 = v30 - *((_DWORD *)v2 + 65),
                v27 = (Bitmap *)((char *)v2 + 252),
                (*(_BYTE *)((v15 >> 3) + *((_DWORD *)v2 + 63)) & *((_BYTE *)&Bitmap::ThisBit + (v15 & 7))) == 0) )
          {
LABEL_41:
            if ( (*(_BYTE *)v4 & 8) == 0 )
            {
              AbstractSpacemap::RemovePage(v14, v4, v14);
              if ( (*(_BYTE *)v4 & 8) == 0 )
                Transaction::FreePage(*(_DWORD *)(*((_DWORD *)v2 + 1) + 60), v30, 1, v4);
            }
            goto LABEL_44;
          }
          Bitmap::Clear(v27, v30, v4);
          AbstractSpacemap::UpdateBitmap((Bitmap *)((char *)v2 + 236));
        }
        v14 = v30;
        goto LABEL_41;
      }
    }
  }
LABEL_45:
  v16 = v25;
LABEL_46:
  if ( v16 )
    --*(_WORD *)(v16 + 76);
}

```

## disassembly

```asm
0x1001cf90  mov     edi, edi
0x1001cf92  push    ebp
0x1001cf93  mov     ebp, esp
0x1001cf95  push    0FFFFFFFFh
0x1001cf97  push    offset ?DeleteRecord@Cursor@@AAEXAAVErr@@@Z_SEH
0x1001cf9c  mov     eax, large fs:0
0x1001cfa2  push    eax
0x1001cfa3  sub     esp, 48h
0x1001cfa6  push    ebx
0x1001cfa7  push    esi
0x1001cfa8  push    edi; unsigned int
0x1001cfa9  mov     eax, ___security_cookie
0x1001cfae  xor     eax, ebp
0x1001cfb0  push    eax; void *
0x1001cfb1  lea     eax, [ebp+var_C]
0x1001cfb4  mov     large fs:0, eax
0x1001cfba  mov     ebx, ecx
0x1001cfbc  mov     [ebp+var_20], ebx
0x1001cfbf  mov     ecx, [ebx+18h]
0x1001cfc2  xor     esi, esi
0x1001cfc4  mov     [ebp+var_14], ecx
0x1001cfc7  mov     [ebp+var_30], esi
0x1001cfca  mov     [ebp+var_2C], esi
0x1001cfcd  mov     edi, [ebp+arg_0]
0x1001cfd0  mov     [ebp+var_4], esi
0x1001cfd3  mov     eax, [ebx+168h]
0x1001cfd9  mov     [ebp+var_34], eax
0x1001cfdc  lea     eax, [ebx+28h]
0x1001cfdf  shr     ecx, 8
0x1001cfe2  test    byte ptr [edi], 8
0x1001cfe5  mov     [ebp+var_10], ecx
0x1001cfe8  mov     [ebp+var_18], eax
0x1001cfeb  jnz     short loc_1001D004
0x1001cfed  mov     eax, [eax]
0x1001cfef  push    esi; char
0x1001cff0  push    eax; struct Transaction *
0x1001cff1  push    edi; struct Err *
0x1001cff2  push    ecx; unsigned int
0x1001cff3  lea     ecx, [ebp+var_30]
0x1001cff6  push    ecx; struct PageRef *
0x1001cff7  mov     ecx, [eax+8]; this
0x1001cffa  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x1001cfff  mov     esi, [ebp+var_30]
0x1001d002  jmp     short loc_1001D007
0x1001d004  mov     [ebp+var_18], eax
0x1001d007  test    byte ptr [edi], 8
0x1001d00a  mov     ecx, 109h
0x1001d00f  jnz     loc_1001D0E9; jumptable 1001D04B case 0
0x1001d015  mov     eax, [ebp+var_2C]
0x1001d018  cmp     [eax], cx
0x1001d01b  jnz     short loc_1001D02A
0x1001d01d  push    ecx
0x1001d01e  push    0FFFFFC07h
0x1001d023  mov     ecx, edi
0x1001d025  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1001d02a  test    byte ptr [edi], 8
0x1001d02d  jnz     loc_1001D0E9; jumptable 1001D04B case 0
0x1001d033  lea     eax, [ebp+var_40]
0x1001d036  push    eax
0x1001d037  push    [ebp+var_14]
0x1001d03a  lea     ecx, [ebp+var_30]
0x1001d03d  call    ?RecordAddress@DataPage@@QBE?AW4RowType@@KPAVRecord@@@Z; DataPage::RecordAddress(ulong,Record *)
0x1001d042  cmp     eax, 3; switch 4 cases
0x1001d045  ja      def_1001D04B; jumptable 1001D04B default case, case 2
0x1001d04b  jmp     ds:jpt_1001D04B[eax*4]; switch jump
0x1001d052  push    ecx; jumptable 1001D04B case 3
0x1001d053  push    0FFFFFC07h
0x1001d058  jmp     loc_1001D0E2
0x1001d05d  mov     eax, [ebp+var_40]; jumptable 1001D04B case 1
0x1001d060  lea     ecx, [ebp+var_30]; this
0x1001d063  push    dword ptr [ebx+18h]; unsigned int
0x1001d066  mov     eax, [eax]
0x1001d068  mov     [ebp+var_14], eax
0x1001d06b  shr     eax, 8
0x1001d06e  mov     [ebp+var_10], eax
0x1001d071  call    ?Delete@DataPage@@QAEXK@Z; DataPage::Delete(ulong)
0x1001d076  mov     eax, [esi+18h]
0x1001d079  lea     ecx, [ebp+var_30]
0x1001d07c  push    0; char
0x1001d07e  or      dword ptr [esi+eax*4+1Ch], 8
0x1001d083  mov     eax, [ebp+var_18]
0x1001d086  inc     dword ptr [esi+40h]
0x1001d089  mov     esi, [ebp+var_10]
0x1001d08c  mov     eax, [eax]
0x1001d08e  push    eax; struct Transaction *
0x1001d08f  push    edi; struct Err *
0x1001d090  push    esi; unsigned int
0x1001d091  push    ecx; struct PageRef *
0x1001d092  mov     ecx, [eax+8]; this
0x1001d095  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x1001d09a  test    byte ptr [edi], 8
0x1001d09d  jnz     loc_1001D30F
0x1001d0a3  mov     esi, [ebp+var_30]
0x1001d0a6  mov     eax, [esi+18h]
0x1001d0a9  lea     ecx, [esi+eax*4]
0x1001d0ac  mov     eax, [ecx+1Ch]
0x1001d0af  and     eax, 0FFFFFF6Fh
0x1001d0b4  or      eax, 60h
0x1001d0b7  mov     [ecx+1Ch], eax
0x1001d0ba  lea     eax, [ebp+var_40]
0x1001d0bd  push    eax
0x1001d0be  push    [ebp+var_14]
0x1001d0c1  lea     ecx, [ebp+var_30]
0x1001d0c4  call    ?RecordAddress@DataPage@@QBE?AW4RowType@@KPAVRecord@@@Z; DataPage::RecordAddress(ulong,Record *)
0x1001d0c9  sub     eax, 2
0x1001d0cc  jz      short loc_1001D0E9; jumptable 1001D04B case 0
0x1001d0ce  mov     eax, [ebx+4]
0x1001d0d1  push    edi; struct Err *
0x1001d0d2  mov     ecx, [eax+10h]; this
0x1001d0d5  call    ?MarkCorrupt@Database@@QAEXAAVErr@@@Z; Database::MarkCorrupt(Err &)
0x1001d0da  jmp     short loc_1001D0E9; jumptable 1001D04B case 0
0x1001d0dc  push    ecx; jumptable 1001D04B default case, case 2
0x1001d0dd  push    0FFFFFBEBh
0x1001d0e2  mov     ecx, edi
0x1001d0e4  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1001d0e9  test    byte ptr [edi], 8; jumptable 1001D04B case 0
0x1001d0ec  mov     esi, [ebp+var_10]
0x1001d0ef  jnz     loc_1001D30F
0x1001d0f5  push    edi
0x1001d0f6  push    [ebp+var_3C]
0x1001d0f9  lea     ecx, [ebp+var_30]
0x1001d0fc  call    ?WillFit@DataPage@@QBE?AW4DPBool@@IAAVErr@@@Z; DataPage::WillFit(uint,Err &)
0x1001d101  test    eax, eax
0x1001d103  jnz     short loc_1001D11C
0x1001d105  test    byte ptr [edi], 8
0x1001d108  jnz     loc_1001D30F
0x1001d10e  lea     ecx, [ebx+0ECh]
0x1001d114  push    ecx
0x1001d115  push    edi
0x1001d116  push    esi
0x1001d117  call    ?AddPage@AbstractSpacemap@@QAEXKAAVErr@@W4SMAssertAction@@@Z; AbstractSpacemap::AddPage(ulong,Err &,SMAssertAction)
0x1001d11c  test    byte ptr [edi], 8
0x1001d11f  jnz     loc_1001D30F
0x1001d125  push    edi; struct Err *
0x1001d126  push    dword ptr [ebx+18h]; unsigned int
0x1001d129  mov     ecx, ebx; this
0x1001d12b  push    [ebp+var_38]; unsigned int
0x1001d12e  push    [ebp+var_3C]; unsigned int
0x1001d131  push    [ebp+var_40]; unsigned __int8 *
0x1001d134  call    ?DeleteFromIndexes@Cursor@@AAEXPAEIIKAAVErr@@@Z; Cursor::DeleteFromIndexes(uchar *,uint,uint,ulong,Err &)
0x1001d139  test    byte ptr [edi], 8
0x1001d13c  jnz     loc_1001D30F
0x1001d142  mov     edx, [ebx+0Ch]
0x1001d145  lea     ecx, [ebp+var_40]
0x1001d148  lea     eax, [ebx+60h]
0x1001d14b  mov     [eax], ecx
0x1001d14d  mov     ecx, [edx+170h]
0x1001d153  mov     [ebp+var_18], ecx
0x1001d156  cmp     ecx, 0FFFFFFFFh
0x1001d159  jz      loc_1001D211
0x1001d15f  mov     edi, eax
0x1001d161  test    ecx, ecx
0x1001d163  js      short loc_1001D176
0x1001d165  cmp     ecx, 0FFh
0x1001d16b  jnb     short loc_1001D176
0x1001d16d  mov     ebx, [edx+ecx*4+178h]
0x1001d174  jmp     short loc_1001D178
0x1001d176  xor     ebx, ebx
0x1001d178  mov     eax, [ebx]
0x1001d17a  mov     esi, [eax+10h]
0x1001d17d  mov     ecx, esi
0x1001d17f  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001d185  mov     ecx, ebx
0x1001d187  call    esi
0x1001d189  cmp     al, 0Ch
0x1001d18b  jz      short loc_1001D1A2
0x1001d18d  mov     eax, [ebx]
0x1001d18f  mov     esi, [eax+10h]
0x1001d192  mov     ecx, esi
0x1001d194  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001d19a  mov     ecx, ebx
0x1001d19c  call    esi
0x1001d19e  cmp     al, 0Bh
0x1001d1a0  jnz     short loc_1001D1F0
0x1001d1a2  mov     [ebp+var_54], 1
0x1001d1a9  mov     byte ptr [ebp+var_4], 1
0x1001d1ad  mov     eax, [ebx]
0x1001d1af  mov     esi, [eax+4Ch]
0x1001d1b2  lea     eax, [ebp+var_54]
0x1001d1b5  push    eax; unsigned int
0x1001d1b6  push    edi; void *
0x1001d1b7  mov     ecx, esi
0x1001d1b9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1001d1bf  mov     ecx, ebx
0x1001d1c1  call    esi
0x1001d1c3  mov     byte ptr [ebp+var_4], 0
0x1001d1c7  test    [ebp+var_54], 0FFFFFFFEh
0x1001d1ce  jz      short loc_1001D1F0
0x1001d1d0  mov     eax, [ebp+Block]
0x1001d1d3  test    eax, eax
0x1001d1d5  jz      short loc_1001D1E0
0x1001d1d7  push    eax; Block
0x1001d1d8  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001d1dd  add     esp, 4
0x1001d1e0  mov     eax, [ebp+var_44]
0x1001d1e3  test    eax, eax
0x1001d1e5  jz      short loc_1001D1F0
0x1001d1e7  push    eax; Block
0x1001d1e8  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1001d1ed  add     esp, 4
0x1001d1f0  mov     ebx, [ebp+var_20]
0x1001d1f3  mov     ecx, [ebp+var_18]
0x1001d1f6  mov     edx, [ebx+0Ch]
0x1001d1f9  mov     eax, [edx+168h]
0x1001d1ff  mov     ecx, [eax+ecx*8]
0x1001d202  mov     [ebp+var_18], ecx
0x1001d205  cmp     ecx, 0FFFFFFFFh
0x1001d208  jnz     loc_1001D161
0x1001d20e  mov     edi, [ebp+arg_0]
0x1001d211  test    byte ptr [edi], 8
0x1001d214  jnz     loc_1001D30F
0x1001d21a  push    [ebp+var_14]; unsigned int
0x1001d21d  lea     ecx, [ebp+var_30]; this
0x1001d220  call    ?Delete@DataPage@@QAEXK@Z; DataPage::Delete(ulong)
0x1001d225  mov     edx, [ebp+var_2C]
0x1001d228  mov     ax, [edx+8]
0x1001d22c  movzx   ecx, word ptr [edx+2]
0x1001d230  add     ax, 5
0x1001d234  add     ax, ax
0x1001d237  movzx   eax, ax
0x1001d23a  add     ecx, eax
0x1001d23c  cmp     ecx, 800h
0x1001d242  jb      loc_1001D2EB
0x1001d248  mov     [ebp+var_54], 1
0x1001d24f  push    edi
0x1001d250  mov     eax, 109h
0x1001d255  mov     byte ptr [ebp+var_4], 2
0x1001d259  push    1
0x1001d25b  lea     ecx, [ebx+0ECh]
0x1001d261  mov     [edx], ax
0x1001d264  call    ?Setup@AbstractSpacemap@@IAEXW4SetupType@1@AAVErr@@@Z; AbstractSpacemap::Setup(AbstractSpacemap::SetupType,Err &)
0x1001d269  test    byte ptr [edi], 8
0x1001d26c  jnz     short loc_1001D2BF
0x1001d26e  push    edi
0x1001d26f  push    2
0x1001d271  push    [ebp+var_10]
0x1001d274  lea     ecx, [ebx+0ECh]
0x1001d27a  call    ?GetBitmap@AbstractSpacemap@@IAE?AW4GBResult@1@KW4GBDirection@1@AAVErr@@@Z; AbstractSpacemap::GetBitmap(ulong,AbstractSpacemap::GBDirection,Err &)
0x1001d27f  mov     ecx, [ebp+var_10]
0x1001d282  cmp     eax, 1
0x1001d285  jnz     short loc_1001D2C2
0x1001d287  lea     eax, [ebx+0FCh]
0x1001d28d  mov     esi, ecx
0x1001d28f  sub     esi, [eax+8]
0x1001d292  mov     edx, esi
0x1001d294  mov     [ebp+var_20], eax
0x1001d297  mov     eax, [eax]
0x1001d299  and     esi, 7
0x1001d29c  shr     edx, 3
0x1001d29f  mov     al, [edx+eax]
0x1001d2a2  test    ds:?ThisBit@Bitmap@@1QBEB[esi], al; uchar const * const Bitmap::ThisBit
0x1001d2a8  jz      short loc_1001D2C2
0x1001d2aa  push    edi; struct Err *
0x1001d2ab  push    ecx; unsigned int
0x1001d2ac  mov     ecx, [ebp+var_20]; this
0x1001d2af  call    ?Clear@Bitmap@@QAEXKAAVErr@@@Z; Bitmap::Clear(ulong,Err &)
0x1001d2b4  lea     ecx, [ebx+0ECh]; this
0x1001d2ba  call    ?UpdateBitmap@AbstractSpacemap@@IAEXXZ; AbstractSpacemap::UpdateBitmap(void)
0x1001d2bf  mov     ecx, [ebp+var_10]
0x1001d2c2  test    byte ptr [edi], 8
0x1001d2c5  jnz     short loc_1001D2EB
0x1001d2c7  push    ecx
0x1001d2c8  push    edi
0x1001d2c9  push    ecx
0x1001d2ca  lea     ecx, [ebx+8Ch]
0x1001d2d0  call    ?RemovePage@AbstractSpacemap@@QAEXKAAVErr@@W4SMAssertAction@@@Z; AbstractSpacemap::RemovePage(ulong,Err &,SMAssertAction)
0x1001d2d5  test    byte ptr [edi], 8
0x1001d2d8  jnz     short loc_1001D2EB
0x1001d2da  mov     ecx, [ebx+4]
0x1001d2dd  push    edi
0x1001d2de  push    1
0x1001d2e0  push    [ebp+var_10]
0x1001d2e3  mov     ecx, [ecx+3Ch]
0x1001d2e6  call    ?FreePage@Transaction@@QAEXKW4FreeDisposition@@AAVErr@@@Z; Transaction::FreePage(ulong,FreeDisposition,Err &)
0x1001d2eb  mov     edx, [ebp+var_30]
0x1001d2ee  mov     eax, [edx+18h]
0x1001d2f1  lea     ecx, [edx+eax*4]
0x1001d2f4  mov     eax, [ecx+1Ch]
0x1001d2f7  and     eax, 0FFFFFF5Fh
0x1001d2fc  or      eax, 50h
0x1001d2ff  mov     [ecx+1Ch], eax
0x1001d302  mov     eax, [edx+18h]
0x1001d305  or      dword ptr [edx+eax*4+1Ch], 8
0x1001d30a  inc     dword ptr [edx+40h]
0x1001d30d  jmp     short loc_1001D312
0x1001d30f  mov     edx, [ebp+var_30]
0x1001d312  test    edx, edx
0x1001d314  jz      short loc_1001D31A
0x1001d316  dec     word ptr [edx+4Ch]
0x1001d31a  mov     ecx, [ebp+var_C]
0x1001d31d  mov     large fs:0, ecx
0x1001d324  pop     ecx
0x1001d325  pop     edi
0x1001d326  pop     esi
0x1001d327  pop     ebx
0x1001d328  mov     esp, ebp
0x1001d32a  pop     ebp
0x1001d32b  retn    4
0x10060120  lea     ecx, [ebp+var_30]; this
0x10060123  jmp     ??1DataPage@@QAE@XZ; DataPage::~DataPage(void)
  ... truncated ...
```
