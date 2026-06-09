# Instance::OpenTable(ushort const *,TblMode,uchar &,Err &)

- ea: `0x10036620`
- end: `0x100368fd`
- name: `?OpenTable@Instance@@QAEPAVTable@@PBGW4TblMode@@AAEAAVErr@@@Z`
- size: `733`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10036910`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10025db0`
- `0x10025ee0`
- `0x10025f50`
- `0x10036620`
- `0x10037710`
- `0x10037bb0`
- `0x10051a30`
- `0x100536a0`
- `0x10053f40`
- `0x10059320`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
Table *__thiscall Instance::OpenTable(
        struct Instance *this,
        unsigned __int16 *Src,
        unsigned int a3,
        _BYTE *a4,
        void **a5)
{
  void **v6; // ebx
  int v7; // ecx
  unsigned int v8; // edx
  struct Session **v9; // edi
  unsigned int v10; // esi
  int v11; // eax
  char *v12; // eax
  int v13; // ecx
  Table *v14; // eax
  struct Err *v15; // ecx
  Table *v16; // esi
  int v17; // eax
  Table *v18; // ecx
  struct Session *v19; // eax
  bool v20; // zf
  char *Block; // [esp+24h] [ebp-28h]
  Table *Blocka; // [esp+24h] [ebp-28h]
  int v24; // [esp+28h] [ebp-24h]
  int v25; // [esp+2Ch] [ebp-20h]
  struct Database **v26; // [esp+30h] [ebp-1Ch]
  unsigned int v27; // [esp+34h] [ebp-18h] BYREF
  struct Instance *v28; // [esp+38h] [ebp-14h]
  unsigned int v29; // [esp+3Ch] [ebp-10h] BYREF
  int v30; // [esp+48h] [ebp-4h]

  v28 = this;
  v6 = a5;
  v25 = a3;
  v27 = 0;
  LOWORD(v29) = 0;
  Instance::ReadSysObjRecord(this, 0xF000001u, Src, a5);
  if ( (*(_BYTE *)a5 & 8) != 0 )
    return 0;
  (*(void (__thiscall **)(_DWORD *, _DWORD, unsigned int *, int, _DWORD, void **))(**((_DWORD **)this + 5) + 108))(
    *((_DWORD **)this + 5),
    *((_DWORD *)v28 + 10),
    &v29,
    2,
    0,
    a5);
  if ( (*(_BYTE *)a5 & 8) == 0 && (_WORD)v29 != 1 )
  {
    switch ( (unsigned __int16)v29 )
    {
      case 4u:
        if ( a3 != 7 )
          Err::SetError(a5, -1035, v7);
        break;
      case 5u:
        Err::SetError(a5, -1034, v7);
        break;
      case 6u:
        Err::SetError(a5, -1052, v7);
        break;
      default:
        Err::SetError(a5, -1305, -8300, Src, 0, v7);
        break;
    }
  }
  if ( (*(_BYTE *)a5 & 8) != 0 )
    return 0;
  (*(void (__thiscall **)(_DWORD, _DWORD, unsigned int *, int, _DWORD, void **))(**((_DWORD **)v28 + 5) + 108))(
    *((_DWORD *)v28 + 5),
    *((_DWORD *)v28 + 8),
    &v27,
    4,
    0,
    a5);
  if ( (*(_BYTE *)a5 & 8) != 0 )
    return 0;
  v8 = a3;
  v9 = (struct Session **)v28;
  if ( a3 == 6 )
  {
    v10 = v27;
    v26 = (struct Database **)((char *)v28 + 16);
    v11 = 0;
    while ( *(_DWORD *)(*((_DWORD *)v28 + 4) + 4 * v11 + 388) != v27 )
    {
      if ( (unsigned int)++v11 >= 6 )
      {
        v8 = 2;
        v25 = 2;
        goto LABEL_23;
      }
    }
    v12 = (char *)v28 + 16;
    v25 = 6;
    v26 = (struct Database **)((char *)v28 + 16);
  }
  else
  {
    v26 = (struct Database **)((char *)v28 + 16);
    if ( a3 == 7 )
    {
      v26 = (struct Database **)((char *)v28 + 16);
      v8 = 0;
      v10 = v27;
      v12 = (char *)v28 + 16;
    }
    else
    {
      v10 = v27;
LABEL_23:
      v12 = (char *)v28 + 16;
    }
  }
  v13 = 0;
  v24 = *(_DWORD *)v12;
  if ( *(_DWORD *)(*(_DWORD *)v12 + 56) )
  {
    while ( 1 )
    {
      Block = (char *)(4 * v13);
      v9 = (struct Session **)v28;
      v6 = a5;
      if ( *(_DWORD *)(*(_DWORD *)(4 * v13 + *(_DWORD *)(v24 + 48)) + 40) == v10 )
        break;
      if ( (unsigned int)++v13 >= *(_DWORD *)(v24 + 56) )
        goto LABEL_27;
    }
    v17 = *(_DWORD *)(v24 + 48);
    v16 = *(Table **)&Block[v17];
    if ( v16 )
    {
      v18 = *(Table **)&Block[v17];
      v19 = (struct Session *)*((_DWORD *)v28 + 3);
      if ( v25 == 7 )
        Table::AddSession(v18, v19, (struct Err *)a5);
      else
        Table::CompatibleMode((int)v18, v19, v8, (struct Err *)a5);
      goto LABEL_39;
    }
  }
LABEL_27:
  if ( v25 != 7 )
  {
    v16 = (Table *)Instance::OpenTable(v9, Src, v27, v8, v6);
    goto LABEL_36;
  }
  Blocka = (Table *)operator new(0x778u);
  v30 = 0;
  v14 = Table::Table(Blocka, *v26, (struct Instance *)v9, v27, (struct Err *)v6);
  v30 = -1;
  v16 = v14;
  if ( (*(_BYTE *)v6 & 8) == 0 )
  {
    Table::SetName(v14, Src, v15);
    if ( (*(_BYTE *)v6 & 8) == 0 )
    {
      Table::AddSession(v16, v9[3], (struct Err *)v6);
LABEL_36:
      if ( (*(_BYTE *)v6 & 8) == 0 )
      {
        v20 = (_WORD)v29 == 4;
        *a4 = 1;
        if ( v20 )
          *((_BYTE *)v16 + 344) = 1;
      }
    }
  }
LABEL_39:
  if ( ((unsigned __int8)*v6 & 1) == 0 && v6[1] == (void *)-1305 )
  {
    if ( ((unsigned int)*v6 & 0xFFFFFFFE) != 0 )
    {
      if ( v6[3] )
        operator delete[](v6[3]);
      if ( v6[4] )
        operator delete[](v6[4]);
    }
    *v6 = (void *)8;
    v6[1] = (void *)-1305;
    v6[2] = (void *)-8300;
    Err::CopyString(v15, (wchar_t *)v6 + 6, Src);
    v6[4] = 0;
  }
  return v16;
}

```

## disassembly

```asm
0x10036620  mov     edi, edi
0x10036622  push    ebp
0x10036623  mov     ebp, esp
0x10036625  push    0FFFFFFFFh
0x10036627  push    offset ?OpenTable@Instance@@QAEPAVTable@@PBGW4TblMode@@AAEAAVErr@@@Z_SEH
0x1003662c  mov     eax, large fs:0
0x10036632  push    eax
0x10036633  sub     esp, 30h
0x10036636  push    ebx
0x10036637  push    esi
0x10036638  push    edi
0x10036639  mov     eax, ___security_cookie
0x1003663e  xor     eax, ebp
0x10036640  push    eax
0x10036641  lea     eax, [ebp+var_C]
0x10036644  mov     large fs:0, eax
0x1003664a  mov     esi, ecx
0x1003664c  mov     [ebp+var_14], esi
0x1003664f  mov     ebx, [ebp+arg_C]
0x10036652  xor     eax, eax
0x10036654  mov     ecx, [ebp+arg_4]
0x10036657  push    ebx; struct Err *
0x10036658  push    [ebp+Src]; unsigned __int16 *
0x1003665b  mov     [ebp+var_20], ecx
0x1003665e  mov     ecx, esi; this
0x10036660  push    0F000001h; unsigned int
0x10036665  mov     [ebp+var_18], 0
0x1003666c  mov     word ptr [ebp+var_10], ax
0x10036670  call    ?ReadSysObjRecord@Instance@@QAEXKPBGAAVErr@@@Z; Instance::ReadSysObjRecord(ulong,ushort const *,Err &)
0x10036675  test    byte ptr [ebx], 8
0x10036678  jnz     loc_100368E7
0x1003667e  mov     edi, [esi+14h]
0x10036681  push    ebx
0x10036682  push    0
0x10036684  push    2
0x10036686  mov     eax, [edi]
0x10036688  mov     esi, [eax+6Ch]
0x1003668b  lea     eax, [ebp+var_10]
0x1003668e  push    eax; unsigned int
0x1003668f  mov     eax, [ebp+var_14]
0x10036692  mov     ecx, esi
0x10036694  push    dword ptr [eax+28h]; void *
0x10036697  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1003669d  mov     ecx, edi
0x1003669f  call    esi
0x100366a1  test    byte ptr [ebx], 8
0x100366a4  jnz     short loc_100366FC
0x100366a6  mov     ax, word ptr [ebp+var_10]
0x100366aa  cmp     ax, 1
0x100366ae  jz      short loc_100366FC
0x100366b0  movzx   eax, ax
0x100366b3  sub     eax, 4
0x100366b6  jz      short loc_100366E9
0x100366b8  push    ecx
0x100366b9  mov     ecx, ebx
0x100366bb  sub     eax, 1
0x100366be  jz      short loc_100366E2
0x100366c0  sub     eax, 1
0x100366c3  jz      short loc_100366DB
0x100366c5  push    0
0x100366c7  push    [ebp+Src]
0x100366ca  push    0FFFFDF94h
0x100366cf  push    0FFFFFAE7h
0x100366d4  call    ?SetError@Err@@QAEXJJPBG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort const *,ushort const *,ErrAssert)
0x100366d9  jmp     short loc_100366FC
0x100366db  push    0FFFFFBE4h
0x100366e0  jmp     short loc_100366F7
0x100366e2  push    0FFFFFBF6h
0x100366e7  jmp     short loc_100366F7
0x100366e9  cmp     [ebp+arg_4], 7
0x100366ed  jz      short loc_100366FC
0x100366ef  push    ecx
0x100366f0  push    0FFFFFBF5h
0x100366f5  mov     ecx, ebx
0x100366f7  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100366fc  test    byte ptr [ebx], 8
0x100366ff  mov     esi, [ebp+var_14]
0x10036702  jnz     loc_100368E7
0x10036708  mov     edi, [esi+14h]
0x1003670b  push    ebx
0x1003670c  push    0
0x1003670e  push    4
0x10036710  mov     eax, [edi]
0x10036712  mov     esi, [eax+6Ch]
0x10036715  lea     eax, [ebp+var_18]
0x10036718  push    eax; unsigned int
0x10036719  mov     eax, [ebp+var_14]
0x1003671c  mov     ecx, esi
0x1003671e  push    dword ptr [eax+20h]; void *
0x10036721  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10036727  mov     ecx, edi
0x10036729  call    esi
0x1003672b  test    byte ptr [ebx], 8
0x1003672e  jnz     loc_100368E7
0x10036734  mov     edx, [ebp+arg_4]
0x10036737  mov     edi, [ebp+var_14]
0x1003673a  cmp     edx, 6
0x1003673d  jnz     short loc_10036774
0x1003673f  mov     ecx, [edi+10h]
0x10036742  lea     eax, [edi+10h]
0x10036745  mov     esi, [ebp+var_18]
0x10036748  mov     [ebp+var_1C], eax
0x1003674b  xor     eax, eax
0x1003674d  nop     dword ptr [eax]
0x10036750  cmp     [ecx+eax*4+184h], esi
0x10036757  jz      short loc_10036769
0x10036759  inc     eax
0x1003675a  cmp     eax, 6
0x1003675d  jb      short loc_10036750
0x1003675f  mov     edx, 2
0x10036764  mov     [ebp+var_20], edx
0x10036767  jmp     short loc_1003678F
0x10036769  lea     eax, [edi+10h]
0x1003676c  mov     [ebp+var_20], edx
0x1003676f  mov     [ebp+var_1C], eax
0x10036772  jmp     short loc_10036792
0x10036774  lea     esi, [edi+10h]
0x10036777  mov     [ebp+var_1C], esi
0x1003677a  cmp     edx, 7
0x1003677d  jnz     short loc_1003678C
0x1003677f  mov     [ebp+var_1C], esi
0x10036782  xor     edx, edx
0x10036784  mov     esi, [ebp+var_18]
0x10036787  mov     eax, [ebp+var_1C]
0x1003678a  jmp     short loc_10036792
0x1003678c  mov     esi, [ebp+var_18]
0x1003678f  lea     eax, [edi+10h]
0x10036792  mov     eax, [eax]
0x10036794  xor     ecx, ecx
0x10036796  mov     [ebp+var_24], eax
0x10036799  cmp     [eax+38h], ecx
0x1003679c  jbe     short loc_100367C7
0x1003679e  mov     edi, edi
0x100367a0  mov     edi, [ebp+var_24]
0x100367a3  lea     eax, ds:0[ecx*4]
0x100367aa  mov     [ebp+Block], eax
0x100367ad  mov     ebx, [edi+30h]
0x100367b0  mov     edi, [ebp+var_14]
0x100367b3  mov     eax, [eax+ebx]
0x100367b6  mov     ebx, [ebp+arg_C]
0x100367b9  cmp     [eax+28h], esi
0x100367bc  mov     eax, [ebp+var_24]
0x100367bf  jz      short loc_10036820
0x100367c1  inc     ecx
0x100367c2  cmp     ecx, [eax+38h]
0x100367c5  jb      short loc_100367A0
0x100367c7  cmp     [ebp+var_20], 7
0x100367cb  jnz     short loc_1003684A
0x100367cd  push    778h; Size
0x100367d2  call    ??2@YAPAXI@Z; operator new(uint)
0x100367d7  add     esp, 4
0x100367da  mov     [ebp+Block], eax
0x100367dd  mov     ecx, [ebp+var_1C]
0x100367e0  push    ebx; struct Err *
0x100367e1  mov     [ebp+var_4], 0
0x100367e8  push    [ebp+var_18]; unsigned int
0x100367eb  push    edi; struct Instance *
0x100367ec  push    dword ptr [ecx]; struct Database *
0x100367ee  mov     ecx, eax; this
0x100367f0  call    ??0Table@@QAE@PAVDatabase@@PAVInstance@@KAAVErr@@@Z; Table::Table(Database *,Instance *,ulong,Err &)
0x100367f5  mov     [ebp+var_4], 0FFFFFFFFh
0x100367fc  mov     esi, eax
0x100367fe  test    byte ptr [ebx], 8
0x10036801  jnz     short loc_10036874
0x10036803  push    ecx; struct Err *
0x10036804  push    [ebp+Src]; Src
0x10036807  mov     ecx, esi; this
0x10036809  call    ?SetName@Table@@QAEXPBGAAVErr@@@Z; Table::SetName(ushort const *,Err &)
0x1003680e  test    byte ptr [ebx], 8
0x10036811  jnz     short loc_10036874
0x10036813  push    ebx; struct Err *
0x10036814  push    dword ptr [edi+0Ch]; struct Session *
0x10036817  mov     ecx, esi; this
0x10036819  call    ?AddSession@Table@@QAEXPAVSession@@AAVErr@@@Z; Table::AddSession(Session *,Err &)
0x1003681e  jmp     short loc_1003685B
0x10036820  mov     eax, [eax+30h]
0x10036823  mov     esi, [ebp+Block]
0x10036826  mov     esi, [esi+eax]
0x10036829  test    esi, esi
0x1003682b  jz      short loc_100367C7
0x1003682d  cmp     [ebp+var_20], 7
0x10036831  mov     ecx, esi; this
0x10036833  mov     eax, [edi+0Ch]
0x10036836  push    ebx; struct Err *
0x10036837  jz      short loc_10036842
0x10036839  push    edx
0x1003683a  push    eax
0x1003683b  call    ?CompatibleMode@Table@@QAEXPAVSession@@W4TblMode@@AAVErr@@@Z; Table::CompatibleMode(Session *,TblMode,Err &)
0x10036840  jmp     short loc_10036874
0x10036842  push    eax; struct Session *
0x10036843  call    ?AddSession@Table@@QAEXPAVSession@@AAVErr@@@Z; Table::AddSession(Session *,Err &)
0x10036848  jmp     short loc_10036874
0x1003684a  push    ebx
0x1003684b  push    edx
0x1003684c  push    [ebp+var_18]
0x1003684f  mov     ecx, edi
0x10036851  push    [ebp+Src]
0x10036854  call    ?OpenTable@Instance@@AAEPAVTable@@PBGKW4TblMode@@AAVErr@@@Z; Instance::OpenTable(ushort const *,ulong,TblMode,Err &)
0x10036859  mov     esi, eax
0x1003685b  test    byte ptr [ebx], 8
0x1003685e  jnz     short loc_10036874
0x10036860  cmp     word ptr [ebp+var_10], 4
0x10036865  mov     eax, [ebp+arg_8]
0x10036868  mov     byte ptr [eax], 1
0x1003686b  jnz     short loc_10036874
0x1003686d  mov     byte ptr [esi+158h], 1
0x10036874  mov     eax, [ebx]
0x10036876  test    al, 1
0x10036878  jnz     short loc_100368D1
0x1003687a  cmp     dword ptr [ebx+4], 0FFFFFAE7h
0x10036881  jnz     short loc_100368D1
0x10036883  test    eax, 0FFFFFFFEh
0x10036888  jz      short loc_100368AA
0x1003688a  mov     eax, [ebx+0Ch]
0x1003688d  test    eax, eax
0x1003688f  jz      short loc_1003689A
0x10036891  push    eax; Block
0x10036892  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10036897  add     esp, 4
0x1003689a  mov     eax, [ebx+10h]
0x1003689d  test    eax, eax
0x1003689f  jz      short loc_100368AA
0x100368a1  push    eax; Block
0x100368a2  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100368a7  add     esp, 4
0x100368aa  push    [ebp+Src]; unsigned __int16 *
0x100368ad  lea     eax, [ebx+0Ch]
0x100368b0  mov     dword ptr [ebx], 8
0x100368b6  push    eax; unsigned __int16 **
0x100368b7  mov     dword ptr [ebx+4], 0FFFFFAE7h
0x100368be  mov     dword ptr [ebx+8], 0FFFFDF94h
0x100368c5  call    ?CopyString@Err@@AAEXAAPAGPBG@Z; Err::CopyString(ushort * &,ushort const *)
0x100368ca  mov     dword ptr [ebx+10h], 0
0x100368d1  mov     eax, esi
0x100368d3  mov     ecx, [ebp+var_C]
0x100368d6  mov     large fs:0, ecx
0x100368dd  pop     ecx
0x100368de  pop     edi
0x100368df  pop     esi
0x100368e0  pop     ebx
0x100368e1  mov     esp, ebp
0x100368e3  pop     ebp
0x100368e4  retn    10h
0x100368e7  xor     eax, eax
0x100368e9  mov     ecx, [ebp+var_C]
0x100368ec  mov     large fs:0, ecx
0x100368f3  pop     ecx
0x100368f4  pop     edi
0x100368f5  pop     esi
0x100368f6  pop     ebx
0x100368f7  mov     esp, ebp
0x100368f9  pop     ebp
0x100368fa  retn    10h
0x10060c00  push    778h; unsigned int
0x10060c05  mov     eax, [ebp+Block]
0x10060c08  push    eax; Block
0x10060c09  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10060c0e  add     esp, 8
0x10060c11  retn
0x10060c12  lea     ecx, [ebp+var_3C]; this
0x10060c15  jmp     ??1Err@@QAE@XZ; Err::~Err(void)
0x10060c1f  nop
0x10060c20  nop
0x10060c21  mov     edx, [esp-4+arg_4]
0x10060c25  lea     eax, [edx+0Ch]
0x10060c28  mov     ecx, [edx-40h]
0x10060c2b  xor     ecx, eax; StackCookie
0x10060c2d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10060c32  mov     eax, offset stru_100638E4
0x10060c37  jmp     ___CxxFrameHandler3
```
