# Table::Open(Instance *,ulong,TblMode,Err &)

- ea: `0x10053400`
- end: `0x10053698`
- name: `?Open@Table@@QAEXPAVInstance@@KW4TblMode@@AAVErr@@@Z`
- size: `664`
- prototype: ``
- caller_count: `8`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x1001dc70`
- `0x1001dfc0`
- `0x10035650`
- `0x10035910`
- `0x10037bb0`
- `0x10050bc0`
- `0x10053950`
- `0x10055ed0`

## callees

- `0x1000f750`
- `0x10020af0`
- `0x10020e70`
- `0x10025db0`
- `0x10053400`
- `0x10053fa0`
- `0x10057e90`
- `0x10059320`
- `0x1005a700`
- `0x1005ab70`
- `0x1005b3b0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall Table::Open(int this, struct Session **a2, unsigned int a3, int a4, struct Err *a5)
{
  int v6; // ebx
  void *v7; // eax
  int v8; // ecx
  int v9; // ecx
  unsigned int v10; // eax
  int v11; // ecx
  int v12; // eax
  Err *v13; // ecx
  const unsigned __int16 *v14; // edi
  void *v15; // eax
  _DWORD v16[3]; // [esp+28h] [ebp-38h] BYREF
  void *Block; // [esp+34h] [ebp-2Ch]
  void *v18; // [esp+38h] [ebp-28h]
  unsigned int v19; // [esp+3Ch] [ebp-24h] BYREF
  void *v20; // [esp+40h] [ebp-20h]
  void *v21; // [esp+44h] [ebp-1Ch]
  int v22; // [esp+48h] [ebp-18h]
  struct Session *v23; // [esp+4Ch] [ebp-14h]
  char v24; // [esp+53h] [ebp-Dh]
  int v25; // [esp+5Ch] [ebp-4h]

  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v6 = a4;
  v25 = 0;
  v24 = 0;
  v23 = a2[3];
  if ( a4 == 5 )
  {
    v6 = 1;
    v24 = 1;
  }
  else if ( a4 == 6 )
  {
    v6 = 2;
    v24 = 1;
  }
  Database::LockTable(*(_DWORD *)(this + 36), a3, v6, a5, 1);
  if ( (*(_BYTE *)a5 & 8) != 0 )
  {
    v16[0] = 1;
    LOBYTE(v25) = 1;
    Table::SetNameFromId((Table *)this, a3, (struct Instance *)a2, (struct Err *)v16);
    Table::ReportLockConflict((Table *)this, *(const unsigned __int16 **)this, a5);
    LOBYTE(v25) = 0;
    if ( (v16[0] & 0xFFFFFFFE) == 0 )
      goto LABEL_34;
    if ( Block )
      operator delete[](Block);
    v7 = v18;
    goto LABEL_32;
  }
  *(_DWORD *)(this + 48) = v6;
  v19 = a3;
  TblPage::ReadPages((TblPage *)&v19, (struct Instance *)a2, a3, (void **)a5);
  if ( (*(_BYTE *)a5 & 8) != 0 || *((_BYTE *)v20 + 12) != 83 || v24 )
  {
    v10 = a3;
  }
  else
  {
    Database::UnlockTable(*(_DWORD *)(this + 36), a3, v6, a5);
    v6 = 0;
    if ( (*(_BYTE *)a5 & 8) == 0 )
    {
      v9 = *(_DWORD *)(this + 36);
      *(_DWORD *)(this + 48) = 9;
      Database::LockTable(v9, a3, 0, a5, 1);
      if ( (*(_BYTE *)a5 & 8) == 0
        || (Table::ReportLockConflict((Table *)this, *(const unsigned __int16 **)this, a5), (*(_BYTE *)a5 & 8) == 0) )
      {
        *(_DWORD *)(this + 48) = 0;
      }
    }
    v8 = *(_DWORD *)(this + 36);
    v10 = a3;
    if ( a3 == *(_DWORD *)(v8 + 404) || a3 == *(_DWORD *)(v8 + 408) )
      *(_BYTE *)(this + 88) &= ~2u;
    else
      *(_BYTE *)(this + 88) |= 2u;
  }
  if ( (*(_BYTE *)a5 & 8) == 0 )
  {
    *(_DWORD *)(this + 40) = v10;
    TblPage::InitTable((TblPage *)&v19, (struct Table *)this, v8, (void **)a5);
    if ( (*(_BYTE *)a5 & 8) == 0 )
    {
      Table::AddSession((Table *)this, v23, a5);
      if ( (*(_BYTE *)a5 & 8) == 0 )
      {
        *(_DWORD *)(this + 44) = v6;
        goto LABEL_34;
      }
    }
  }
  v11 = *(_DWORD *)(this + 36);
  v16[0] = 1;
  Database::UnlockTable(v11, a3, v6, v16);
  v12 = v16[0];
  if ( (v16[0] & 8) == 0 )
    *(_DWORD *)(this + 48) = 9;
  if ( (v12 & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    v7 = v18;
    if ( v18 )
    {
LABEL_32:
      if ( v7 )
        operator delete[](v7);
    }
  }
LABEL_34:
  v13 = *(Err **)a5;
  if ( (*(_DWORD *)a5 & 1) == 0 && *((_DWORD *)a5 + 1) == -1206 )
  {
    v14 = *(const unsigned __int16 **)(*(_DWORD *)(this + 36) + 8);
    if ( ((unsigned int)v13 & 0xFFFFFFFE) != 0 )
    {
      if ( *((_DWORD *)a5 + 3) )
        operator delete[](*((void **)a5 + 3));
      if ( *((_DWORD *)a5 + 4) )
        operator delete[](*((void **)a5 + 4));
    }
    *(_DWORD *)a5 = 8;
    *((_DWORD *)a5 + 1) = -1206;
    *((_DWORD *)a5 + 2) = -8188;
    Err::CopyString(v13, (wchar_t *)a5 + 6, v14);
    *((_DWORD *)a5 + 4) = 0;
  }
  v15 = v21;
  if ( v21 )
  {
    if ( *(_DWORD *)v21 )
      --*(_WORD *)(*(_DWORD *)v21 + 76);
    operator delete(v15, 0xCu);
  }
  else if ( v20 )
  {
    operator delete[](v20);
  }
}

```

## disassembly

```asm
0x10053400  mov     edi, edi
0x10053402  push    ebp
0x10053403  mov     ebp, esp
0x10053405  push    0FFFFFFFFh
0x10053407  push    offset ?Open@Table@@QAEXPAVInstance@@KW4TblMode@@AAVErr@@@Z_SEH
0x1005340c  mov     eax, large fs:0
0x10053412  push    eax
0x10053413  sub     esp, 44h
0x10053416  push    ebx
0x10053417  push    esi
0x10053418  push    edi
0x10053419  mov     eax, ___security_cookie
0x1005341e  xor     eax, ebp
0x10053420  push    eax
0x10053421  lea     eax, [ebp+var_C]
0x10053424  mov     large fs:0, eax
0x1005342a  mov     edi, ecx
0x1005342c  xor     eax, eax
0x1005342e  mov     [ebp+var_24], 0
0x10053435  mov     [ebp+var_20], eax
0x10053438  mov     [ebp+var_1C], eax
0x1005343b  mov     [ebp+var_18], eax
0x1005343e  mov     ebx, [ebp+arg_8]
0x10053441  mov     [ebp+var_4], eax
0x10053444  mov     eax, [ebp+arg_0]
0x10053447  mov     [ebp+var_D], 0
0x1005344b  mov     eax, [eax+0Ch]
0x1005344e  mov     [ebp+var_14], eax
0x10053451  cmp     ebx, 5
0x10053454  jnz     short loc_10053460
0x10053456  mov     ebx, 1
0x1005345b  mov     [ebp+var_D], bl
0x1005345e  jmp     short loc_1005346E
0x10053460  cmp     ebx, 6
0x10053463  jnz     short loc_1005346E
0x10053465  mov     ebx, 2
0x1005346a  mov     [ebp+var_D], 1
0x1005346e  mov     esi, [ebp+arg_C]
0x10053471  mov     ecx, [edi+24h]
0x10053474  push    1
0x10053476  push    esi
0x10053477  push    ebx
0x10053478  push    [ebp+arg_4]
0x1005347b  call    ?LockTable@Database@@QAEXKW4TblLck@@AAVErr@@W4DBROLock@@@Z; Database::LockTable(ulong,TblLck,Err &,DBROLock)
0x10053480  test    byte ptr [esi], 8
0x10053483  jz      short loc_100534D4
0x10053485  mov     [ebp+var_38], 1
0x1005348c  lea     eax, [ebp+var_38]
0x1005348f  mov     byte ptr [ebp+var_4], 1
0x10053493  push    eax; struct Err *
0x10053494  push    [ebp+arg_0]; struct Instance *
0x10053497  mov     ecx, edi; this
0x10053499  push    [ebp+arg_4]; char
0x1005349c  call    ?SetNameFromId@Table@@AAEXKPAVInstance@@AAVErr@@@Z; Table::SetNameFromId(ulong,Instance *,Err &)
0x100534a1  push    esi; struct Err *
0x100534a2  push    dword ptr [edi]; unsigned __int16 *
0x100534a4  mov     ecx, edi; this
0x100534a6  call    ?ReportLockConflict@Table@@AAEXPBGAAVErr@@@Z; Table::ReportLockConflict(ushort const *,Err &)
0x100534ab  mov     byte ptr [ebp+var_4], 0
0x100534af  test    [ebp+var_38], 0FFFFFFFEh
0x100534b6  jz      loc_100535E1
0x100534bc  mov     eax, [ebp+Block]
0x100534bf  test    eax, eax
0x100534c1  jz      short loc_100534CC
0x100534c3  push    eax; Block
0x100534c4  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100534c9  add     esp, 4
0x100534cc  mov     eax, [ebp+var_28]
0x100534cf  jmp     loc_100535D4
0x100534d4  mov     eax, [ebp+arg_4]
0x100534d7  lea     ecx, [ebp+var_24]; this
0x100534da  push    esi; struct Err *
0x100534db  push    eax; unsigned int
0x100534dc  push    [ebp+arg_0]; struct Instance *
0x100534df  mov     [edi+30h], ebx
0x100534e2  mov     [ebp+var_24], eax
0x100534e5  call    ?ReadPages@TblPage@@AAEXPAVInstance@@KAAVErr@@@Z; TblPage::ReadPages(Instance *,ulong,Err &)
0x100534ea  test    byte ptr [esi], 8
0x100534ed  jnz     short loc_10053561
0x100534ef  mov     eax, [ebp+var_20]
0x100534f2  cmp     byte ptr [eax+0Ch], 53h ; 'S'
0x100534f6  jnz     short loc_10053561
0x100534f8  cmp     [ebp+var_D], 0
0x100534fc  jnz     short loc_10053561
0x100534fe  mov     ecx, [edi+24h]
0x10053501  push    esi
0x10053502  push    ebx
0x10053503  push    [ebp+arg_4]
0x10053506  call    ?UnlockTable@Database@@QAEXKW4TblLck@@AAVErr@@@Z; Database::UnlockTable(ulong,TblLck,Err &)
0x1005350b  xor     ebx, ebx
0x1005350d  test    byte ptr [esi], 8
0x10053510  jnz     short loc_1005353F
0x10053512  mov     ecx, [edi+24h]
0x10053515  push    1
0x10053517  push    esi
0x10053518  push    ebx
0x10053519  push    [ebp+arg_4]
0x1005351c  mov     dword ptr [edi+30h], 9
0x10053523  call    ?LockTable@Database@@QAEXKW4TblLck@@AAVErr@@W4DBROLock@@@Z; Database::LockTable(ulong,TblLck,Err &,DBROLock)
0x10053528  test    byte ptr [esi], 8
0x1005352b  jz      short loc_1005353C
0x1005352d  push    esi; struct Err *
0x1005352e  push    dword ptr [edi]; unsigned __int16 *
0x10053530  mov     ecx, edi; this
0x10053532  call    ?ReportLockConflict@Table@@AAEXPBGAAVErr@@@Z; Table::ReportLockConflict(ushort const *,Err &)
0x10053537  test    byte ptr [esi], 8
0x1005353a  jnz     short loc_1005353F
0x1005353c  mov     [edi+30h], ebx
0x1005353f  mov     ecx, [edi+24h]
0x10053542  mov     eax, [ebp+arg_4]
0x10053545  cmp     eax, [ecx+194h]
0x1005354b  jz      short loc_1005355B
0x1005354d  cmp     eax, [ecx+198h]
0x10053553  jz      short loc_1005355B
0x10053555  or      byte ptr [edi+58h], 2
0x10053559  jmp     short loc_10053564
0x1005355b  and     byte ptr [edi+58h], 0FDh
0x1005355f  jmp     short loc_10053564
0x10053561  mov     eax, [ebp+arg_4]
0x10053564  test    byte ptr [esi], 8
0x10053567  jnz     short loc_10053591
0x10053569  push    esi; struct Err *
0x1005356a  push    ecx; int
0x1005356b  push    edi; struct Table *
0x1005356c  lea     ecx, [ebp+var_24]; this
0x1005356f  mov     [edi+28h], eax
0x10053572  call    ?InitTable@TblPage@@QAEXPAVTable@@HAAVErr@@@Z; TblPage::InitTable(Table *,int,Err &)
0x10053577  test    byte ptr [esi], 8
0x1005357a  jnz     short loc_10053591
0x1005357c  push    esi; struct Err *
0x1005357d  push    [ebp+var_14]; struct Session *
0x10053580  mov     ecx, edi; this
0x10053582  call    ?AddSession@Table@@QAEXPAVSession@@AAVErr@@@Z; Table::AddSession(Session *,Err &)
0x10053587  test    byte ptr [esi], 8
0x1005358a  jnz     short loc_10053591
0x1005358c  mov     [edi+2Ch], ebx
0x1005358f  jmp     short loc_100535E1
0x10053591  mov     ecx, [edi+24h]
0x10053594  lea     eax, [ebp+var_38]
0x10053597  push    eax
0x10053598  push    ebx
0x10053599  push    [ebp+arg_4]
0x1005359c  mov     [ebp+var_38], 1
0x100535a3  call    ?UnlockTable@Database@@QAEXKW4TblLck@@AAVErr@@@Z; Database::UnlockTable(ulong,TblLck,Err &)
0x100535a8  mov     eax, [ebp+var_38]
0x100535ab  test    al, 8
0x100535ad  jnz     short loc_100535B6
0x100535af  mov     dword ptr [edi+30h], 9
0x100535b6  test    eax, 0FFFFFFFEh
0x100535bb  jz      short loc_100535E1
0x100535bd  mov     eax, [ebp+Block]
0x100535c0  test    eax, eax
0x100535c2  jz      short loc_100535CD
0x100535c4  push    eax; Block
0x100535c5  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100535ca  add     esp, 4
0x100535cd  mov     eax, [ebp+var_28]
0x100535d0  test    eax, eax
0x100535d2  jz      short loc_100535E1
0x100535d4  test    eax, eax
0x100535d6  jz      short loc_100535E1
0x100535d8  push    eax; Block
0x100535d9  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100535de  add     esp, 4
0x100535e1  mov     ecx, [esi]
0x100535e3  test    cl, 1
0x100535e6  jnz     short loc_10053644
0x100535e8  cmp     dword ptr [esi+4], 0FFFFFB4Ah
0x100535ef  jnz     short loc_10053644
0x100535f1  mov     eax, [edi+24h]
0x100535f4  mov     edi, [eax+8]
0x100535f7  test    ecx, 0FFFFFFFEh
0x100535fd  jz      short loc_1005361F
0x100535ff  mov     eax, [esi+0Ch]
0x10053602  test    eax, eax
0x10053604  jz      short loc_1005360F
0x10053606  push    eax; Block
0x10053607  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005360c  add     esp, 4
0x1005360f  mov     eax, [esi+10h]
0x10053612  test    eax, eax
0x10053614  jz      short loc_1005361F
0x10053616  push    eax; Block
0x10053617  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005361c  add     esp, 4
0x1005361f  push    edi; unsigned __int16 *
0x10053620  lea     eax, [esi+0Ch]
0x10053623  mov     dword ptr [esi], 8
0x10053629  push    eax; unsigned __int16 **
0x1005362a  mov     dword ptr [esi+4], 0FFFFFB4Ah
0x10053631  mov     dword ptr [esi+8], 0FFFFE004h
0x10053638  call    ?CopyString@Err@@AAEXAAPAGPBG@Z; Err::CopyString(ushort * &,ushort const *)
0x1005363d  mov     dword ptr [esi+10h], 0
0x10053644  mov     eax, [ebp+var_1C]
0x10053647  test    eax, eax
0x10053649  jz      short loc_10053674
0x1005364b  mov     ecx, [eax]
0x1005364d  test    ecx, ecx
0x1005364f  jz      short loc_10053655
0x10053651  dec     word ptr [ecx+4Ch]
0x10053655  push    0Ch; unsigned int
0x10053657  push    eax; Block
0x10053658  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005365d  add     esp, 8
0x10053660  mov     ecx, [ebp+var_C]
0x10053663  mov     large fs:0, ecx
0x1005366a  pop     ecx
0x1005366b  pop     edi
0x1005366c  pop     esi
0x1005366d  pop     ebx
0x1005366e  mov     esp, ebp
0x10053670  pop     ebp
0x10053671  retn    10h
0x10053674  mov     eax, [ebp+var_20]
0x10053677  test    eax, eax
0x10053679  jz      short loc_10053684
0x1005367b  push    eax; Block
0x1005367c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10053681  add     esp, 4
0x10053684  mov     ecx, [ebp+var_C]
0x10053687  mov     large fs:0, ecx
0x1005368e  pop     ecx
0x1005368f  pop     edi
0x10053690  pop     esi
0x10053691  pop     ebx
0x10053692  mov     esp, ebp
0x10053694  pop     ebp
0x10053695  retn    10h
0x10061cc0  lea     ecx, [ebp+var_24]; this
0x10061cc3  jmp     ??1TblPage@@QAE@XZ; TblPage::~TblPage(void)
0x10061cc8  lea     ecx, [ebp+var_38]; this
0x10061ccb  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10061cd0  lea     ecx, [ebp+var_4C]; this
0x10061cd3  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10061cdd  nop
0x10061cde  nop
0x10061cdf  mov     edx, [esp-4+arg_4]
0x10061ce3  lea     eax, [edx+0Ch]
0x10061ce6  mov     ecx, [edx-54h]
0x10061ce9  xor     ecx, eax; StackCookie
0x10061ceb  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10061cf0  mov     eax, offset stru_100644D4
0x10061cf5  jmp     ___CxxFrameHandler3
```
