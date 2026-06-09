# Table::DeleteColumn(Instance *,ushort const *,Err &,TblColDeleteType)

- ea: `0x10054e90`
- end: `0x10055259`
- name: `?DeleteColumn@Table@@QAEXPAVInstance@@PBGAAVErr@@W4TblColDeleteType@@@Z`
- size: `969`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10029750`
- `0x10029890`

## callees

- `0x1000eb60`
- `0x10025ee0`
- `0x100435f0`
- `0x10044860`
- `0x10044950`
- `0x10047d30`
- `0x10047e10`
- `0x10048100`
- `0x10051890`
- `0x10054e90`
- `0x10056ff0`
- `0x10057520`
- `0x10057ce0`
- `0x1005d280`
- `0x1005e3b0`
- `0x1005e798`
- `0x1005f064`

## pseudocode

```c
void __thiscall Table::DeleteColumn(_DWORD *this, struct Instance *a2, unsigned __int16 *a3, struct Err *a4, int a5)
{
  const unsigned __int16 *v6; // edx
  int v7; // ecx
  int v8; // eax
  int ColumnFromName; // eax
  int v10; // esi
  Session *v11; // esi
  struct Err *v12; // ecx
  int v13; // esi
  struct Session *v14; // esi
  int v15; // eax
  void (__thiscall ***v16)(void *, int); // esi
  int v17; // [esp-8h] [ebp-104h]
  int v19; // [esp+14h] [ebp-E8h]
  int v20; // [esp+18h] [ebp-E4h]
  _DWORD *v21; // [esp+1Ch] [ebp-E0h]
  Session *v22; // [esp+24h] [ebp-D8h]
  int v23; // [esp+28h] [ebp-D4h]
  _DWORD v24[24]; // [esp+2Ch] [ebp-D0h] BYREF
  _DWORD v25[24]; // [esp+8Ch] [ebp-70h] BYREF
  int v26; // [esp+F8h] [ebp-4h]

  v6 = a3;
  ++this[85];
  v7 = 0;
  v26 = 0;
  v20 = 0;
  v21 = 0;
  if ( this[11] != 2 && this[12] != 8 )
  {
    Err::SetError(a4, -1309, 0);
LABEL_7:
    v6 = a3;
    goto LABEL_8;
  }
  v8 = *(_DWORD *)(this[9] + 104);
  if ( !v8 || v8 == 3 )
  {
    Err::SetError(a4, -1809, 0);
    goto LABEL_7;
  }
LABEL_8:
  if ( (*(_BYTE *)a4 & 8) != 0 )
  {
    ColumnFromName = 0;
  }
  else
  {
    ColumnFromName = Table::FindColumnFromName((Table *)this, v6);
    v20 = ColumnFromName;
    if ( ColumnFromName == -1 )
    {
      Err::SetError(a4, -1507, v7);
      ColumnFromName = -1;
    }
  }
  if ( (*(_BYTE *)a4 & 8) != 0 )
    goto LABEL_42;
  v10 = this[ColumnFromName + 94];
  v23 = v10;
  if ( (*(_BYTE *)(v10 + 48) & 8) != 0 && a5 != 1 )
    Err::SetError(a4, -1046, v7);
  if ( (*(_BYTE *)a4 & 8) != 0 )
    goto LABEL_42;
  if ( *(_DWORD *)(v10 + 68) )
    Err::SetError(a4, -1046, v7);
  if ( (*(_BYTE *)a4 & 8) != 0 )
    goto LABEL_42;
  v21 = operator new(0xCCu);
  v21[1] = v21 + 18;
  *((_WORD *)v21 + 36) = 0;
  v21[2] = 0;
  *((_BYTE *)v21 + 49) &= 0xF8u;
  v21[3] = -1;
  v21[4] = -1;
  v21[5] = 0;
  v21[6] = 0;
  v21[7] = 0;
  v21[8] = 0;
  v21[9] = 0;
  v21[10] = 0;
  *((_BYTE *)v21 + 48) = 0;
  v21[13] = 0;
  v21[14] = -1;
  v21[15] = 0;
  v21[16] = 256;
  v21[17] = 0;
  *((_BYTE *)v21 + 202) = 0;
  *v21 = &ColumnDeleted::`vftable';
  if ( (*(_BYTE *)a4 & 8) != 0 )
    goto LABEL_42;
  if ( (*(unsigned __int8 (__thiscall **)(int))(*(_DWORD *)v10 + 16))(v10) == 12
    || (*(unsigned __int8 (__thiscall **)(int))(*(_DWORD *)v10 + 16))(v10) == 11 )
  {
    v11 = (Session *)*((_DWORD *)a2 + 3);
    v22 = v11;
    Session::BeginTransaction(v11, 1, a4);
    if ( (*(_BYTE *)a4 & 8) != 0 )
      goto LABEL_42;
    this[17] = *((_DWORD *)v11 + 14);
    if ( (*(_BYTE *)a4 & 8) != 0 )
      goto LABEL_42;
    AbstractSpacemap::AbstractSpacemap((AbstractSpacemap *)v25);
    LOBYTE(v26) = 1;
    v17 = *(_DWORD *)(v23 + 204);
    v19 = *((_DWORD *)a2 + 15);
    v25[0] = *(_DWORD *)(v19 + 8);
    v25[2] = v17;
    v25[1] = v19;
    v25[23] = *(_DWORD *)(*(_DWORD *)(v25[0] + 60) + 104);
    Transaction::FreePages(v19, v25, v17, a4);
    if ( (*(_BYTE *)a4 & 8) != 0 )
      goto LABEL_32;
    AbstractSpacemap::Delete((AbstractSpacemap *)v25, a4);
    if ( (*(_BYTE *)a4 & 8) != 0 )
      goto LABEL_32;
    v13 = *(_DWORD *)(v23 + 208);
    if ( v13 )
    {
      AbstractSpacemap::AbstractSpacemap((AbstractSpacemap *)v24);
      LOBYTE(v26) = 2;
      v24[1] = v19;
      v24[2] = v13;
      v24[0] = *(_DWORD *)(v19 + 8);
      v24[23] = *(_DWORD *)(*(_DWORD *)(v24[0] + 60) + 104);
      AbstractSpacemap::Delete((AbstractSpacemap *)v24, a4);
      LOBYTE(v26) = 1;
      Spacemap::~Spacemap((Spacemap *)v24);
    }
    if ( (*(_BYTE *)a4 & 8) != 0 )
    {
LABEL_32:
      v14 = v22;
    }
    else
    {
      v14 = v22;
      Session::CommitTransaction(v22, (void **)a4, 0);
      if ( (*(_BYTE *)a4 & 8) != 0 )
        goto LABEL_34;
      this[17] = -1;
    }
    if ( (*(_BYTE *)a4 & 8) == 0 )
    {
LABEL_35:
      LOBYTE(v26) = 0;
      Spacemap::~Spacemap((Spacemap *)v25);
      goto LABEL_36;
    }
LABEL_34:
    Table::AbortTransaction((Table *)this, v14, v12);
    goto LABEL_35;
  }
LABEL_36:
  if ( (*(_BYTE *)a4 & 8) != 0 )
  {
LABEL_42:
    v16 = (void (__thiscall ***)(void *, int))v21;
    goto LABEL_43;
  }
  v15 = *(_DWORD *)(*((_DWORD *)a2 + 3) + 56);
  if ( this[21] == v20 )
  {
    this[21] = -1;
  }
  else if ( this[20] == v20 )
  {
    this[20] = -1;
  }
  v16 = (void (__thiscall ***)(void *, int))v21;
  --this[5];
  v21[14] = v15;
  v21[15] = this[v20 + 94];
  this[v20 + 94] = v21;
  PresOrderList::Remove((PresOrderList *)(this + 90), v20);
  Table::DDLPerformed((Table *)this, a2);
LABEL_43:
  if ( (*(_BYTE *)a4 & 8) != 0 && v16 )
    (**v16)(v21, 1);
  --this[85];
}

```

## disassembly

```asm
0x10054e90  mov     edi, edi
0x10054e92  push    ebp
0x10054e93  mov     ebp, esp
0x10054e95  push    0FFFFFFFFh
0x10054e97  push    offset ?DeleteColumn@Table@@QAEXPAVInstance@@PBGAAVErr@@W4TblColDeleteType@@@Z_SEH
0x10054e9c  mov     eax, large fs:0
0x10054ea2  push    eax
0x10054ea3  sub     esp, 0E0h
0x10054ea9  mov     eax, ___security_cookie
0x10054eae  xor     eax, ebp
0x10054eb0  mov     [ebp+var_10], eax
0x10054eb3  push    ebx
0x10054eb4  push    esi
0x10054eb5  push    edi; unsigned int
0x10054eb6  push    eax; unsigned int
0x10054eb7  lea     eax, [ebp+var_C]
0x10054eba  mov     large fs:0, eax
0x10054ec0  mov     edi, ecx
0x10054ec2  mov     eax, [ebp+arg_0]
0x10054ec5  mov     edx, [ebp+arg_4]
0x10054ec8  mov     ebx, [ebp+arg_8]
0x10054ecb  inc     dword ptr [edi+154h]
0x10054ed1  mov     [ebp+var_DC], eax
0x10054ed7  mov     [ebp+var_D8], edx
0x10054edd  mov     [ebp+var_EC], edi
0x10054ee3  xor     ecx, ecx
0x10054ee5  mov     [ebp+var_4], 0
0x10054eec  xor     esi, esi
0x10054eee  mov     [ebp+var_E4], 0
0x10054ef8  cmp     dword ptr [edi+2Ch], 2
0x10054efc  mov     [ebp+var_E0], ecx
0x10054f02  mov     [ebp+var_D4], esi
0x10054f08  jz      short loc_10054F18
0x10054f0a  cmp     dword ptr [edi+30h], 8
0x10054f0e  jz      short loc_10054F18
0x10054f10  push    ecx
0x10054f11  push    0FFFFFAE3h
0x10054f16  jmp     short loc_10054F2D
0x10054f18  mov     eax, [edi+24h]
0x10054f1b  mov     eax, [eax+68h]
0x10054f1e  test    eax, eax
0x10054f20  jz      short loc_10054F27
0x10054f22  cmp     eax, 3
0x10054f25  jnz     short loc_10054F3A
0x10054f27  push    ecx
0x10054f28  push    0FFFFF8EFh
0x10054f2d  mov     ecx, ebx
0x10054f2f  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10054f34  mov     edx, [ebp+var_D8]
0x10054f3a  test    byte ptr [ebx], 8
0x10054f3d  jnz     short loc_10054F67
0x10054f3f  push    edx; unsigned __int16 *
0x10054f40  mov     ecx, edi; this
0x10054f42  call    ?FindColumnFromName@Table@@QAEHPBG@Z; Table::FindColumnFromName(ushort const *)
0x10054f47  mov     [ebp+var_E4], eax
0x10054f4d  cmp     eax, 0FFFFFFFFh
0x10054f50  jnz     short loc_10054F69
0x10054f52  push    ecx
0x10054f53  push    0FFFFFA1Dh
0x10054f58  mov     ecx, ebx
0x10054f5a  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10054f5f  mov     eax, [ebp+var_E4]
0x10054f65  jmp     short loc_10054F69
0x10054f67  xor     eax, eax
0x10054f69  test    byte ptr [ebx], 8
0x10054f6c  jnz     loc_10055210
0x10054f72  mov     esi, [edi+eax*4+178h]
0x10054f79  mov     [ebp+var_D4], esi
0x10054f7f  test    byte ptr [esi+30h], 8
0x10054f83  jz      short loc_10054F98
0x10054f85  cmp     [ebp+arg_C], 1
0x10054f89  jz      short loc_10054F98
0x10054f8b  push    ecx
0x10054f8c  push    0FFFFFBEAh
0x10054f91  mov     ecx, ebx
0x10054f93  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10054f98  test    byte ptr [ebx], 8
0x10054f9b  jnz     loc_10055210
0x10054fa1  cmp     dword ptr [esi+44h], 0
0x10054fa5  jz      short loc_10054FB4
0x10054fa7  push    ecx
0x10054fa8  push    0FFFFFBEAh
0x10054fad  mov     ecx, ebx
0x10054faf  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10054fb4  test    byte ptr [ebx], 8
0x10054fb7  jnz     loc_10055210
0x10054fbd  push    0CCh; Size
0x10054fc2  call    ??2@YAPAXI@Z; operator new(uint)
0x10054fc7  mov     esi, eax
0x10054fc9  xor     ecx, ecx
0x10054fcb  lea     eax, [esi+48h]
0x10054fce  mov     [ebp+var_E0], esi
0x10054fd4  add     esp, 4
0x10054fd7  mov     [ebp+var_E8], esi
0x10054fdd  mov     [esi+4], eax
0x10054fe0  mov     [eax], cx
0x10054fe3  mov     [esi+8], ecx
0x10054fe6  and     byte ptr [esi+31h], 0F8h
0x10054fea  mov     dword ptr [esi+0Ch], 0FFFFFFFFh
0x10054ff1  mov     dword ptr [esi+10h], 0FFFFFFFFh
0x10054ff8  mov     [esi+14h], ecx
0x10054ffb  mov     [esi+18h], ecx
0x10054ffe  mov     [esi+1Ch], ecx
0x10055001  mov     [esi+20h], ecx
0x10055004  mov     [esi+24h], ecx
0x10055007  mov     [esi+28h], ecx
0x1005500a  mov     [esi+30h], cl
0x1005500d  mov     [esi+34h], ecx
0x10055010  mov     dword ptr [esi+38h], 0FFFFFFFFh
0x10055017  mov     [esi+3Ch], ecx
0x1005501a  mov     dword ptr [esi+40h], 100h
0x10055021  mov     [esi+44h], ecx
0x10055024  mov     [esi+0CAh], cl
0x1005502a  mov     dword ptr [esi], offset ??_7ColumnDeleted@@6B@; const ColumnDeleted::`vftable'
0x10055030  test    byte ptr [ebx], 8
0x10055033  jnz     loc_10055210
0x10055039  mov     eax, [ebp+var_D4]
0x1005503f  mov     eax, [eax]
0x10055041  mov     esi, [eax+10h]
0x10055044  mov     ecx, esi
0x10055046  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005504c  mov     ecx, [ebp+var_D4]
0x10055052  call    esi
0x10055054  cmp     al, 0Ch
0x10055056  jz      short loc_1005507B
0x10055058  mov     eax, [ebp+var_D4]
0x1005505e  mov     eax, [eax]
0x10055060  mov     esi, [eax+10h]
0x10055063  mov     ecx, esi
0x10055065  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005506b  mov     ecx, [ebp+var_D4]
0x10055071  call    esi
0x10055073  cmp     al, 0Bh
0x10055075  jnz     loc_100551A7
0x1005507b  mov     esi, [ebp+var_DC]
0x10055081  push    ebx
0x10055082  push    1
0x10055084  mov     esi, [esi+0Ch]
0x10055087  mov     ecx, esi
0x10055089  mov     [ebp+var_D8], esi
0x1005508f  call    ?BeginTransaction@Session@@QAEXW4TransactionType@@AAVErr@@@Z; Session::BeginTransaction(TransactionType,Err &)
0x10055094  test    byte ptr [ebx], 8
0x10055097  jnz     loc_10055210
0x1005509d  mov     eax, [esi+38h]
0x100550a0  mov     [edi+44h], eax
0x100550a3  test    byte ptr [ebx], 8
0x100550a6  jnz     loc_10055210
0x100550ac  lea     ecx, [ebp+var_70]; this
0x100550af  call    ??0AbstractSpacemap@@QAE@XZ; AbstractSpacemap::AbstractSpacemap(void)
0x100550b4  mov     eax, [ebp+var_DC]
0x100550ba  mov     esi, [ebp+var_D4]
0x100550c0  mov     byte ptr [ebp+var_4], 1
0x100550c4  push    ebx
0x100550c5  mov     edx, [eax+3Ch]
0x100550c8  mov     ecx, [esi+0CCh]
0x100550ce  push    ecx
0x100550cf  mov     [ebp+var_E8], edx
0x100550d5  mov     eax, [edx+8]
0x100550d8  mov     [ebp+var_70], eax
0x100550db  mov     [ebp+var_68], ecx
0x100550de  mov     ecx, edx
0x100550e0  mov     [ebp+var_6C], edx
0x100550e3  mov     eax, [eax+3Ch]
0x100550e6  mov     eax, [eax+68h]
0x100550e9  mov     [ebp+var_14], eax
0x100550ec  lea     eax, [ebp+var_70]
0x100550ef  push    eax
0x100550f0  call    ?FreePages@Transaction@@QAEXPAVAbstractSpacemap@@W4FreeDisposition@@AAVErr@@@Z; Transaction::FreePages(AbstractSpacemap *,FreeDisposition,Err &)
0x100550f5  test    byte ptr [ebx], 8
0x100550f8  jnz     loc_10055187
0x100550fe  push    ebx; struct Err *
0x100550ff  lea     ecx, [ebp+var_70]; this
0x10055102  call    ?Delete@AbstractSpacemap@@QAEXAAVErr@@@Z; AbstractSpacemap::Delete(Err &)
0x10055107  test    byte ptr [ebx], 8
0x1005510a  jnz     short loc_10055187
0x1005510c  mov     esi, [esi+0D0h]
0x10055112  test    esi, esi
0x10055114  jz      short loc_10055164
0x10055116  lea     ecx, [ebp+var_D0]; this
0x1005511c  call    ??0AbstractSpacemap@@QAE@XZ; AbstractSpacemap::AbstractSpacemap(void)
0x10055121  mov     ecx, [ebp+var_E8]
0x10055127  mov     byte ptr [ebp+var_4], 2
0x1005512b  mov     [ebp+var_CC], ecx
0x10055131  mov     [ebp+var_C8], esi
0x10055137  mov     eax, [ecx+8]
0x1005513a  lea     ecx, [ebp+var_D0]; this
0x10055140  mov     [ebp+var_D0], eax
0x10055146  push    ebx; struct Err *
0x10055147  mov     eax, [eax+3Ch]
0x1005514a  mov     eax, [eax+68h]
0x1005514d  mov     [ebp+var_74], eax
0x10055150  call    ?Delete@AbstractSpacemap@@QAEXAAVErr@@@Z; AbstractSpacemap::Delete(Err &)
0x10055155  lea     ecx, [ebp+var_D0]; this
0x1005515b  mov     byte ptr [ebp+var_4], 1
0x1005515f  call    ??1Spacemap@@QAE@XZ; Spacemap::~Spacemap(void)
0x10055164  test    byte ptr [ebx], 8
0x10055167  jnz     short loc_10055187
0x10055169  mov     esi, [ebp+var_D8]
0x1005516f  mov     ecx, esi; this
0x10055171  push    0; unsigned int
0x10055173  push    ebx; struct Err *
0x10055174  call    ?CommitTransaction@Session@@QAEXAAVErr@@K@Z; Session::CommitTransaction(Err &,ulong)
0x10055179  test    byte ptr [ebx], 8
0x1005517c  jnz     short loc_10055192
0x1005517e  mov     dword ptr [edi+44h], 0FFFFFFFFh
0x10055185  jmp     short loc_1005518D
0x10055187  mov     esi, [ebp+var_D8]
0x1005518d  test    byte ptr [ebx], 8
0x10055190  jz      short loc_1005519B
0x10055192  push    ecx; struct Err *
0x10055193  push    esi; struct Session *
0x10055194  mov     ecx, edi; this
0x10055196  call    ?AbortTransaction@Table@@AAEXPAVSession@@AAVErr@@@Z; Table::AbortTransaction(Session *,Err &)
0x1005519b  lea     ecx, [ebp+var_70]; this
0x1005519e  mov     byte ptr [ebp+var_4], 0
0x100551a2  call    ??1Spacemap@@QAE@XZ; Spacemap::~Spacemap(void)
0x100551a7  test    byte ptr [ebx], 8
0x100551aa  jnz     short loc_10055210
0x100551ac  mov     eax, [ebp+var_DC]
0x100551b2  mov     ecx, [ebp+var_E4]
0x100551b8  mov     eax, [eax+0Ch]
0x100551bb  mov     eax, [eax+38h]
0x100551be  cmp     [edi+54h], ecx
0x100551c1  jnz     short loc_100551CC
0x100551c3  mov     dword ptr [edi+54h], 0FFFFFFFFh
0x100551ca  jmp     short loc_100551D8
0x100551cc  cmp     [edi+50h], ecx
0x100551cf  jnz     short loc_100551D8
0x100551d1  mov     dword ptr [edi+50h], 0FFFFFFFFh
0x100551d8  mov     esi, [ebp+var_E0]
0x100551de  dec     dword ptr [edi+14h]
0x100551e1  push    ecx; int
0x100551e2  mov     [esi+38h], eax
0x100551e5  mov     eax, [edi+ecx*4+178h]
0x100551ec  mov     [esi+3Ch], eax
0x100551ef  mov     [edi+ecx*4+178h], esi
0x100551f6  lea     ecx, [edi+168h]; this
0x100551fc  call    ?Remove@PresOrderList@@QAEHH@Z; PresOrderList::Remove(int)
0x10055201  push    [ebp+var_DC]; struct Instance *
0x10055207  mov     ecx, edi; this
0x10055209  call    ?DDLPerformed@Table@@AAEXPAVInstance@@@Z; Table::DDLPerformed(Instance *)
0x1005520e  jmp     short loc_10055216
0x10055210  mov     esi, [ebp+var_E0]
0x10055216  test    byte ptr [ebx], 8
0x10055219  jz      short loc_10055235
0x1005521b  test    esi, esi
0x1005521d  jz      short loc_10055235
0x1005521f  mov     eax, [esi]
0x10055221  push    1; void *
0x10055223  mov     esi, [eax]
0x10055225  mov     ecx, esi
0x10055227  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005522d  mov     ecx, [ebp+var_E0]
0x10055233  call    esi
0x10055235  dec     dword ptr [edi+154h]
0x1005523b  mov     ecx, [ebp+var_C]
0x1005523e  mov     large fs:0, ecx
0x10055245  pop     ecx
0x10055246  pop     edi
0x10055247  pop     esi
0x10055248  pop     ebx
0x10055249  mov     ecx, [ebp+var_10]
0x1005524c  xor     ecx, ebp; StackCookie
0x1005524e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10055253  mov     esp, ebp
0x10055255  pop     ebp
0x10055256  retn    10h
0x10061f00  lea     ecx, [ebp+var_EC]; this
0x10061f06  jmp     ??1TblSemaphore@@QAE@XZ; TblSemaphore::~TblSemaphore(void)
0x10061f0b  lea     ecx, [ebp+var_70]; this
0x10061f0e  jmp     ??1Spacemap@@QAE@XZ; Spacemap::~Spacemap(void)
0x10061f13  lea     ecx, [ebp+var_D0]; this
0x10061f19  jmp     ??1Spacemap@@QAE@XZ; Spacemap::~Spacemap(void)
0x10061f23  nop
0x10061f24  nop
0x10061f25  mov     edx, [esp-4+arg_4]
0x10061f29  lea     eax, [edx+0Ch]
0x10061f2c  mov     ecx, [edx-0F0h]
0x10061f32  xor     ecx, eax; StackCookie
0x10061f34  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061f39  mov     ecx, [edx-4]
0x10061f3c  xor     ecx, eax; StackCookie
0x10061f3e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061f43  mov     eax, offset stru_10064694
0x10061f48  jmp     ___CxxFrameHandler3
```
