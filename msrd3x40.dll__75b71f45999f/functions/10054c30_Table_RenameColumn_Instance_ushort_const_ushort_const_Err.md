# Table::RenameColumn(Instance *,ushort const *,ushort const *,Err &)

- ea: `0x10054c30`
- end: `0x10054e86`
- name: `?RenameColumn@Table@@QAEXPAVInstance@@PBG1AAVErr@@@Z`
- size: `598`
- prototype: `void __thiscall(Table *__hidden this, struct Instance *, const unsigned __int16 *, const unsigned __int16 *Src, struct Err *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10029600`

## callees

- `0x1000eb60`
- `0x10025ee0`
- `0x10043450`
- `0x100435f0`
- `0x1004dbb0`
- `0x10051890`
- `0x10054c30`
- `0x10056ff0`
- `0x10057520`
- `0x1005e3b0`
- `0x1005f064`
- `0x1005f07c`

## pseudocode

```c
void __thiscall Table::RenameColumn(
        Table *this,
        struct Instance *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *Src,
        struct Err *a5)
{
  bool v6; // zf
  char *v7; // esi
  int v8; // eax
  int v9; // edx
  int v10; // esi
  unsigned __int16 *v11; // ecx
  int v13; // ecx
  int v14; // ecx
  int *v15; // eax
  void **v16; // ecx
  const unsigned __int16 *v17; // esi
  size_t v19; // esi
  const unsigned __int16 **v20; // ecx
  struct Err *v21; // ecx
  _DWORD v22[3]; // [esp+10h] [ebp-38h] BYREF
  __int16 v23; // [esp+1Ch] [ebp-2Ch]
  int v24; // [esp+20h] [ebp-28h]
  int v25; // [esp+24h] [ebp-24h]
  Table *v26; // [esp+28h] [ebp-20h]
  int **v27; // [esp+2Ch] [ebp-1Ch]
  const unsigned __int16 **v28; // [esp+30h] [ebp-18h]
  int ColumnFromName; // [esp+34h] [ebp-14h]
  char v30; // [esp+3Bh] [ebp-Dh]
  int v31; // [esp+44h] [ebp-4h]

  ++*((_DWORD *)this + 85);
  v26 = this;
  v31 = 0;
  v6 = *((_DWORD *)this + 11) == 2;
  ColumnFromName = 0;
  v30 = 0;
  if ( v6 || *((_DWORD *)this + 12) == 8 )
  {
    v7 = (char *)this + 36;
    v8 = *(_DWORD *)(*((_DWORD *)this + 9) + 104);
    if ( !v8 || v8 == 3 )
      Err::SetError(a5, -1809, this);
  }
  else
  {
    Err::SetError(a5, -1309, this);
    v7 = (char *)this + 36;
  }
  if ( (*(_BYTE *)a5 & 8) == 0 )
  {
    ColumnFromName = Table::FindColumnFromName(this, Src);
    if ( ColumnFromName != -1 )
    {
      v9 = *(_DWORD *)v7;
      v10 = *(_DWORD *)(*(_DWORD *)v7 + 224);
      if ( !v10 )
        v10 = *(unsigned __int16 *)(v9 + 86);
      v11 = a3;
      v28 = (const unsigned __int16 **)(a3 + 1);
      while ( *v11++ )
        ;
      v22[0] = a3;
      v24 = v10;
      v25 = 0;
      v22[1] = 2 * (((char *)v11 - (char *)v28) >> 1);
      v22[2] = *(_DWORD *)(v9 + 92);
      v23 = *(_WORD *)(*(_DWORD *)(v9 + 60) + 100);
      if ( LString::Compare(v22, Src, 2 * wcslen(Src), 0) )
        Err::SetError(a5, -1508, v13);
      else
        v30 = 1;
    }
    if ( (*(_BYTE *)a5 & 8) == 0 )
    {
      v14 = Table::FindColumnFromName(this, a3);
      ColumnFromName = v14;
      if ( v14 != -1 )
        goto LABEL_20;
      Err::SetError(a5, -1507, -1);
    }
  }
  v14 = ColumnFromName;
LABEL_20:
  if ( (*(_BYTE *)a5 & 8) == 0 )
  {
    v28 = *(const unsigned __int16 ***)(*((_DWORD *)a2 + 3) + 56);
    v27 = (int **)((char *)this + 4 * v14 + 376);
    v15 = *v27;
    ColumnFromName = (int)v15;
    if ( (int)v28 > v15[14] )
    {
      v15 = (int *)(*(int (__thiscall **)(int, struct Err *))(*v15 + 64))(ColumnFromName, a5);
      if ( (*(_BYTE *)a5 & 8) != 0 )
      {
        v15 = (int *)ColumnFromName;
      }
      else
      {
        v15[14] = (int)v28;
        v15[15] = ColumnFromName;
        *v27 = v15;
        ColumnFromName = (int)v15;
      }
    }
    v6 = (*(_BYTE *)a5 & 8) == 0;
    v16 = (void **)(v15 + 1);
    v28 = (const unsigned __int16 **)(v15 + 1);
    if ( v6 )
    {
      v17 = Src;
      while ( *v17++ )
        ;
      v19 = 2 * (v17 - (Src + 1));
      memcpy(*v16, Src, v19);
      v20 = v28;
      (*v28)[v19 / 2] = 0;
      v15 = (int *)ColumnFromName;
      v20[1] = (const unsigned __int16 *)v19;
    }
    else
    {
      v28 = (const unsigned __int16 **)(v15 + 1);
    }
    if ( !v30 )
    {
      PresOrderList::Remove((Table *)((char *)this + 360), v15[3]);
      PresOrderList::Insert(
        (Table *)((char *)this + 360),
        *v28,
        *(_DWORD *)(ColumnFromName + 12),
        *(_DWORD *)(ColumnFromName + 24),
        v21);
    }
    Table::DDLPerformed(this, a2);
  }
  --*((_DWORD *)this + 85);
}

```

## disassembly

```asm
0x10054c30  mov     edi, edi
0x10054c32  push    ebp
0x10054c33  mov     ebp, esp
0x10054c35  push    0FFFFFFFFh
0x10054c37  push    offset ?RenameColumn@Table@@QAEXPAVInstance@@PBG1AAVErr@@@Z_SEH
0x10054c3c  mov     eax, large fs:0
0x10054c42  push    eax
0x10054c43  sub     esp, 2Ch
0x10054c46  push    ebx
0x10054c47  push    esi
0x10054c48  push    edi
0x10054c49  mov     eax, ___security_cookie
0x10054c4e  xor     eax, ebp
0x10054c50  push    eax; unsigned int
0x10054c51  lea     eax, [ebp+var_C]
0x10054c54  mov     large fs:0, eax
0x10054c5a  mov     edi, ecx
0x10054c5c  inc     dword ptr [edi+154h]
0x10054c62  mov     [ebp+var_20], edi
0x10054c65  mov     ebx, [ebp+arg_C]
0x10054c68  xor     eax, eax
0x10054c6a  mov     [ebp+var_4], 0
0x10054c71  cmp     dword ptr [edi+2Ch], 2
0x10054c75  mov     [ebp+var_14], eax
0x10054c78  mov     [ebp+var_D], al
0x10054c7b  jz      short loc_10054C95
0x10054c7d  cmp     dword ptr [edi+30h], 8
0x10054c81  jz      short loc_10054C95
0x10054c83  push    ecx
0x10054c84  push    0FFFFFAE3h
0x10054c89  mov     ecx, ebx
0x10054c8b  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10054c90  lea     esi, [edi+24h]
0x10054c93  jmp     short loc_10054CB4
0x10054c95  mov     eax, [edi+24h]
0x10054c98  lea     esi, [edi+24h]
0x10054c9b  mov     eax, [eax+68h]
0x10054c9e  test    eax, eax
0x10054ca0  jz      short loc_10054CA7
0x10054ca2  cmp     eax, 3
0x10054ca5  jnz     short loc_10054CB4
0x10054ca7  push    ecx
0x10054ca8  push    0FFFFF8EFh
0x10054cad  mov     ecx, ebx
0x10054caf  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10054cb4  test    byte ptr [ebx], 8
0x10054cb7  jnz     loc_10054D8B
0x10054cbd  push    [ebp+Src]; unsigned __int16 *
0x10054cc0  mov     ecx, edi; this
0x10054cc2  call    ?FindColumnFromName@Table@@QAEHPBG@Z; Table::FindColumnFromName(ushort const *)
0x10054cc7  mov     [ebp+var_14], eax
0x10054cca  cmp     eax, 0FFFFFFFFh
0x10054ccd  jz      loc_10054D65
0x10054cd3  mov     edx, [esi]
0x10054cd5  mov     esi, [edx+0E0h]
0x10054cdb  test    esi, esi
0x10054cdd  jnz     short loc_10054CE3
0x10054cdf  movzx   esi, word ptr [edx+56h]
0x10054ce3  mov     ecx, [ebp+arg_4]
0x10054ce6  lea     eax, [ecx+2]
0x10054ce9  mov     [ebp+var_18], eax
0x10054cec  nop     dword ptr [eax+00h]
0x10054cf0  mov     ax, [ecx]
0x10054cf3  add     ecx, 2
0x10054cf6  test    ax, ax
0x10054cf9  jnz     short loc_10054CF0
0x10054cfb  sub     ecx, [ebp+var_18]
0x10054cfe  mov     eax, [ebp+arg_4]
0x10054d01  sar     ecx, 1
0x10054d03  mov     [ebp+var_38], eax
0x10054d06  mov     [ebp+var_28], esi
0x10054d09  mov     [ebp+var_24], 0
0x10054d10  lea     eax, [ecx+ecx]
0x10054d13  mov     [ebp+var_34], eax
0x10054d16  mov     eax, [edx+5Ch]
0x10054d19  mov     [ebp+var_30], eax
0x10054d1c  mov     eax, [edx+3Ch]
0x10054d1f  mov     edx, [ebp+Src]
0x10054d22  mov     ecx, edx
0x10054d24  mov     ax, [eax+64h]
0x10054d28  mov     [ebp+var_2C], ax
0x10054d2c  lea     esi, [ecx+2]
0x10054d2f  nop
0x10054d30  mov     ax, [ecx]
0x10054d33  add     ecx, 2
0x10054d36  test    ax, ax
0x10054d39  jnz     short loc_10054D30
0x10054d3b  sub     ecx, esi
0x10054d3d  sar     ecx, 1
0x10054d3f  push    0
0x10054d41  lea     eax, [ecx+ecx]
0x10054d44  push    eax
0x10054d45  push    edx
0x10054d46  lea     ecx, [ebp+var_38]
0x10054d49  call    ?Compare@LString@@QAE?AW4LCmp@@PAEIW4LSpec@@@Z; LString::Compare(uchar *,uint,LSpec)
0x10054d4e  test    eax, eax
0x10054d50  jnz     short loc_10054D58
0x10054d52  mov     [ebp+var_D], 1
0x10054d56  jmp     short loc_10054D65
0x10054d58  push    ecx
0x10054d59  push    0FFFFFA1Ch
0x10054d5e  mov     ecx, ebx
0x10054d60  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10054d65  test    byte ptr [ebx], 8
0x10054d68  jnz     short loc_10054D8B
0x10054d6a  push    [ebp+arg_4]; unsigned __int16 *
0x10054d6d  mov     ecx, edi; this
0x10054d6f  call    ?FindColumnFromName@Table@@QAEHPBG@Z; Table::FindColumnFromName(ushort const *)
0x10054d74  mov     ecx, eax
0x10054d76  mov     [ebp+var_14], ecx
0x10054d79  cmp     ecx, 0FFFFFFFFh
0x10054d7c  jnz     short loc_10054D8E
0x10054d7e  push    ecx
0x10054d7f  push    0FFFFFA1Dh
0x10054d84  mov     ecx, ebx
0x10054d86  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10054d8b  mov     ecx, [ebp+var_14]
0x10054d8e  test    byte ptr [ebx], 8
0x10054d91  jnz     loc_10054E6C
0x10054d97  mov     eax, [ebp+arg_0]
0x10054d9a  mov     eax, [eax+0Ch]
0x10054d9d  mov     edx, [eax+38h]
0x10054da0  lea     eax, [edi+178h]
0x10054da6  lea     eax, [eax+ecx*4]
0x10054da9  mov     [ebp+var_18], edx
0x10054dac  mov     [ebp+var_1C], eax
0x10054daf  mov     eax, [eax]
0x10054db1  mov     [ebp+var_14], eax
0x10054db4  cmp     edx, [eax+38h]
0x10054db7  jle     short loc_10054DEE
0x10054db9  mov     eax, [eax]
0x10054dbb  push    ebx; void *
0x10054dbc  mov     esi, [eax+40h]
0x10054dbf  mov     ecx, esi
0x10054dc1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10054dc7  mov     ecx, [ebp+var_14]
0x10054dca  call    esi
0x10054dcc  test    byte ptr [ebx], 8
0x10054dcf  mov     ecx, eax
0x10054dd1  jnz     short loc_10054DEB
0x10054dd3  mov     eax, [ebp+var_18]
0x10054dd6  mov     [ecx+38h], eax
0x10054dd9  mov     eax, [ebp+var_14]
0x10054ddc  mov     [ecx+3Ch], eax
0x10054ddf  mov     eax, [ebp+var_1C]
0x10054de2  mov     [eax], ecx
0x10054de4  mov     eax, ecx
0x10054de6  mov     [ebp+var_14], eax
0x10054de9  jmp     short loc_10054DEE
0x10054deb  mov     eax, [ebp+var_14]
0x10054dee  test    byte ptr [ebx], 8
0x10054df1  lea     ecx, [eax+4]
0x10054df4  mov     [ebp+var_18], ecx
0x10054df7  jnz     short loc_10054E31
0x10054df9  mov     edx, [ebp+Src]
0x10054dfc  mov     esi, edx
0x10054dfe  lea     ebx, [esi+2]
0x10054e01  mov     ax, [esi]
0x10054e04  add     esi, 2
0x10054e07  test    ax, ax
0x10054e0a  jnz     short loc_10054E01
0x10054e0c  sub     esi, ebx
0x10054e0e  sar     esi, 1
0x10054e10  add     esi, esi
0x10054e12  push    esi; Size
0x10054e13  push    edx; Src
0x10054e14  push    dword ptr [ecx]; void *
0x10054e16  call    _memcpy
0x10054e1b  mov     ecx, [ebp+var_18]
0x10054e1e  add     esp, 0Ch
0x10054e21  xor     edx, edx
0x10054e23  mov     eax, [ecx]
0x10054e25  mov     [esi+eax], dx
0x10054e29  mov     eax, [ebp+var_14]
0x10054e2c  mov     [ecx+4], esi
0x10054e2f  jmp     short loc_10054E34
0x10054e31  mov     [ebp+var_18], ecx
0x10054e34  cmp     [ebp+var_D], 0
0x10054e38  jnz     short loc_10054E62
0x10054e3a  push    dword ptr [eax+0Ch]; int
0x10054e3d  lea     ecx, [edi+168h]; this
0x10054e43  call    ?Remove@PresOrderList@@QAEHH@Z; PresOrderList::Remove(int)
0x10054e48  mov     eax, [ebp+var_14]
0x10054e4b  push    ecx; struct Err *
0x10054e4c  lea     ecx, [edi+168h]; this
0x10054e52  push    dword ptr [eax+18h]; int
0x10054e55  push    dword ptr [eax+0Ch]; int
0x10054e58  mov     eax, [ebp+var_18]
0x10054e5b  push    dword ptr [eax]; unsigned __int16 *
0x10054e5d  call    ?Insert@PresOrderList@@QAEXPBGHHAAVErr@@@Z; PresOrderList::Insert(ushort const *,int,int,Err &)
0x10054e62  push    [ebp+arg_0]; struct Instance *
0x10054e65  mov     ecx, edi; this
0x10054e67  call    ?DDLPerformed@Table@@AAEXPAVInstance@@@Z; Table::DDLPerformed(Instance *)
0x10054e6c  dec     dword ptr [edi+154h]
0x10054e72  mov     ecx, [ebp+var_C]
0x10054e75  mov     large fs:0, ecx
0x10054e7c  pop     ecx
0x10054e7d  pop     edi
0x10054e7e  pop     esi
0x10054e7f  pop     ebx
0x10054e80  mov     esp, ebp
0x10054e82  pop     ebp
0x10054e83  retn    10h
0x10061ed0  lea     ecx, [ebp+var_20]; this
0x10061ed3  jmp     ??1TblSemaphore@@QAE@XZ; TblSemaphore::~TblSemaphore(void)
0x10061edd  nop
0x10061ede  nop
0x10061edf  mov     edx, [esp-4+arg_4]
0x10061ee3  lea     eax, [edx+0Ch]
0x10061ee6  mov     ecx, [edx-3Ch]
0x10061ee9  xor     ecx, eax; StackCookie
0x10061eeb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061ef0  mov     eax, offset stru_10064668
0x10061ef5  jmp     ___CxxFrameHandler3
```
