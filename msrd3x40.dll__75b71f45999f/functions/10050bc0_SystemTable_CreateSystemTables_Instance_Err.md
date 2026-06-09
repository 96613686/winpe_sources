# SystemTable::CreateSystemTables(Instance *,Err &)

- ea: `0x10050bc0`
- end: `0x1005112f`
- name: `?CreateSystemTables@SystemTable@@QAEXPAVInstance@@AAVErr@@@Z`
- size: `1391`
- prototype: `void __thiscall(SystemTable *__hidden this, struct Instance *, struct Err *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x10044340`

## callees

- `0x10010580`
- `0x10023730`
- `0x10044860`
- `0x10044950`
- `0x10044cb0`
- `0x10047d30`
- `0x10047e10`
- `0x10047eb0`
- `0x10049b80`
- `0x10050bc0`
- `0x100518a0`
- `0x10051e80`
- `0x10052140`
- `0x10053400`
- `0x100544e0`
- `0x10055260`
- `0x1005a700`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall SystemTable::CreateSystemTables(struct Database **this, struct Instance *a2, void **a3)
{
  int v3; // ecx
  struct Database **v4; // edx
  struct Database *v5; // eax
  int v6; // ecx
  unsigned int v7; // eax
  Table *v8; // ebx
  int v9; // edi
  int v10; // ecx
  unsigned int v11; // eax
  unsigned int v12; // eax
  bool v13; // zf
  unsigned int v14; // eax
  int v15; // eax
  unsigned int v16; // eax
  int v17; // edx
  char v18; // al
  unsigned int v19; // eax
  int v20; // ecx
  int v21; // eax
  int v22; // ebx
  int *v23; // edi
  struct Instance *v24; // ebx
  int v25; // [esp-10h] [ebp-104h]
  Table *v26; // [esp+20h] [ebp-D4h]
  int v27; // [esp+24h] [ebp-D0h] BYREF
  int v28; // [esp+28h] [ebp-CCh]
  unsigned int v29; // [esp+30h] [ebp-C4h]
  int v30; // [esp+34h] [ebp-C0h]
  int v31; // [esp+38h] [ebp-BCh]
  int v32; // [esp+3Ch] [ebp-B8h]
  int v33; // [esp+40h] [ebp-B4h]
  unsigned int v34; // [esp+44h] [ebp-B0h]
  Table *v35; // [esp+48h] [ebp-ACh]
  unsigned int v36; // [esp+4Ch] [ebp-A8h]
  struct Database **v37; // [esp+50h] [ebp-A4h]
  unsigned int i; // [esp+54h] [ebp-A0h]
  unsigned int v39; // [esp+58h] [ebp-9Ch]
  struct Instance *v40; // [esp+5Ch] [ebp-98h]
  char v41; // [esp+63h] [ebp-91h] BYREF
  _BYTE v42[28]; // [esp+64h] [ebp-90h] BYREF
  int v43; // [esp+80h] [ebp-74h]
  int v44; // [esp+90h] [ebp-64h]
  char v45[4]; // [esp+C4h] [ebp-30h] BYREF
  int v46; // [esp+C8h] [ebp-2Ch]
  char v47; // [esp+CCh] [ebp-28h]
  _DWORD v48[3]; // [esp+D0h] [ebp-24h] BYREF
  void *Block; // [esp+DCh] [ebp-18h]
  void *v50; // [esp+E0h] [ebp-14h]
  int v51; // [esp+F0h] [ebp-4h]

  v37 = this;
  v3 = *((_DWORD *)a2 + 3);
  v40 = a2;
  v36 = 0;
  v39 = 0;
  Session::BeginTransaction(v3, 1, a3);
  v4 = v37;
  v5 = *v37;
  v33 = *((unsigned __int16 *)*v37 + 42);
  v6 = *((unsigned __int16 *)v5 + 43);
  v31 = *((unsigned __int16 *)v5 + 44);
  v7 = 0;
  v32 = v6;
  v34 = 0;
  while ( (*(_BYTE *)a3 & 8) == 0 )
  {
    v8 = 0;
    v35 = 0;
    v27 = 0;
    v28 = 0;
    v51 = 0;
    v9 = 32 * v7;
    v29 = 32 * v7;
    v10 = (unsigned __int16)word_10066254[16 * v7];
    if ( v10 == 1 || *((_DWORD *)*v4 + 17) == 4 && !(_WORD)v10 )
    {
      switch ( dword_10066258[8 * v7] )
      {
        case 0:
          v11 = *((_DWORD *)*v4 + 97);
          goto LABEL_14;
        case 1:
          v11 = *((_DWORD *)*v4 + 98);
          goto LABEL_14;
        case 2:
          v11 = *((_DWORD *)*v4 + (*((_DWORD *)*v4 + 55) < 1912) + 99);
          goto LABEL_14;
        case 3:
          v11 = *((_DWORD *)*v4 + (*((_DWORD *)*v4 + 55) >= 1912) + 99);
          goto LABEL_14;
        case 4:
          v11 = *((_DWORD *)*v4 + 101);
          goto LABEL_14;
        case 5:
          v11 = *((_DWORD *)*v4 + 102);
LABEL_14:
          v39 = v11;
          break;
        default:
          break;
      }
      Database::ReadPageForUpdate(
        *(Database **)(*((_DWORD *)v40 + 15) + 8),
        (struct PageRef *)&v27,
        v39,
        (struct Err *)a3,
        *((struct Transaction **)v40 + 15),
        0);
      if ( (*(_BYTE *)a3 & 8) == 0 )
      {
        AbstractSpacemap::AbstractSpacemap((AbstractSpacemap *)v42);
        LOBYTE(v51) = 2;
        v12 = Spacemap::Create((Spacemap *)v42, *((struct Transaction **)v40 + 15), (struct Err *)a3, v36);
        v13 = (*(_BYTE *)a3 & 8) == 0;
        v36 = v12;
        if ( v13 )
        {
          *(_DWORD *)(v28 + 35) = v12;
          if ( (*(_BYTE *)a3 & 8) == 0 )
          {
            v14 = Spacemap::Create((Spacemap *)v42, *((struct Transaction **)v40 + 15), (struct Err *)a3, v12);
            v13 = (*(_BYTE *)a3 & 8) == 0;
            v36 = v14;
            if ( v13 )
              *(_DWORD *)(v28 + 39) = v14;
          }
        }
        LOBYTE(v51) = 3;
        v48[0] = 1;
        AbstractSpacemap::Close((AbstractSpacemap *)v42, (struct Err *)v48);
        if ( (v48[0] & 0xFFFFFFFE) != 0 )
        {
          if ( Block )
            operator delete[](Block);
          if ( v50 )
            operator delete[](v50);
        }
        if ( v44 )
          --*(_WORD *)(v44 + 76);
        if ( v43 )
          --*(_WORD *)(v43 + 76);
        LOBYTE(v51) = 0;
        if ( (*(_BYTE *)a3 & 8) == 0 )
        {
          v26 = (Table *)operator new(0x778u);
          LOBYTE(v51) = 4;
          v8 = Table::Table(v26, *v37, (struct Err *)a3);
          LOBYTE(v51) = 0;
          v15 = (int)*a3;
          v35 = v8;
          if ( v8 )
          {
            if ( (v15 & 8) != 0 )
            {
              Table::~Table(v8);
              operator delete(v8, 0x778u);
              v8 = 0;
              v35 = 0;
            }
          }
          else if ( v15 < 8 )
          {
            if ( (v15 & 0xFFFFFFFE) != 0 )
            {
              if ( a3[3] )
                operator delete[](a3[3]);
              if ( a3[4] )
                operator delete[](a3[4]);
            }
            *a3 = (void *)8;
            a3[1] = (void *)-1011;
            a3[2] = 0;
            a3[3] = 0;
            a3[4] = 0;
          }
          if ( (*(_BYTE *)a3 & 8) == 0 )
          {
            ++*((_DWORD *)v8 + 19);
            Table::Open(v8, v40, v39, 6, a3);
            if ( (*(_BYTE *)a3 & 8) == 0 )
            {
              v16 = 0;
              for ( i = 0; v16 < *(int *)((char *)&dword_10066260 + v9); i = v16 )
              {
                if ( (*(_BYTE *)a3 & 8) != 0 )
                  break;
                v17 = 16 * v16 + *(int *)((char *)&dword_10066264 + v9);
                v45[0] = *(_BYTE *)(v17 + 4);
                v46 = *(_DWORD *)(v17 + 8);
                v47 = *(_BYTE *)(v17 + 12);
                v48[0] = (unsigned __int16)v33;
                v48[1] = (unsigned __int16)v32;
                v48[2] = (unsigned __int16)v31;
                LOBYTE(v50) = (unsigned __int8)v50 & 0xF0 | 9;
                v18 = *(_BYTE *)(v17 + 13);
                BYTE1(v50) &= 0xF8u;
                Block = 0;
                LOBYTE(v50) = (unsigned __int8)v50 & 0xF | (16 * (v18 & 1 | 0xFC));
                Table::AddColumn(
                  v8,
                  v40,
                  *(const unsigned __int16 **)v17,
                  (const struct tagTblColDef *)v45,
                  (struct Err *)a3);
                v16 = i + 1;
              }
              v19 = 0;
              i = 0;
              if ( *(int *)((char *)dword_10066268 + v9) )
              {
                do
                {
                  if ( (*(_BYTE *)a3 & 8) != 0 )
                    break;
                  v20 = 3 * v19;
                  v21 = *(int *)((char *)&dword_1006626C + v9);
                  v22 = *(_DWORD *)(v21 + 4 * v20 + 8);
                  v23 = (int *)(v21 + 4 * v20);
                  LOBYTE(v20) = *((_BYTE *)v23 + 4);
                  v30 = *v23;
                  v41 = v41 & 0xFE | v20 & 1;
                  v41 ^= (v41 ^ *((_BYTE *)v23 + 4)) & 2;
                  v41 ^= (v41 ^ *((_BYTE *)v23 + 4)) & 4;
                  v41 ^= (v41 ^ *((_BYTE *)v23 + 4)) & 8;
                  v25 = v22;
                  v8 = v35;
                  v41 ^= (v41 ^ *((_BYTE *)v23 + 4)) & 0x10;
                  Table::AddIndex(v35, v40, v30, &v41, v25, 100, a3, 0);
                  v9 = v29;
                  v19 = i + 1;
                  i = v19;
                }
                while ( v19 < dword_10066268[v29 / 4] );
              }
            }
          }
        }
      }
      if ( v8 )
        Table::Release(v8, v40);
      v4 = v37;
      v51 = -1;
      if ( v27 )
        --*(_WORD *)(v27 + 76);
    }
    else
    {
      v51 = -1;
    }
    v7 = v34 + 1;
    v34 = v7;
    if ( v7 >= 0xA )
    {
      if ( (*(_BYTE *)a3 & 8) == 0 )
      {
        v24 = v40;
        Session::CommitTransaction(*((Session **)v40 + 3), a3, 0);
        goto LABEL_56;
      }
      break;
    }
  }
  v24 = v40;
LABEL_56:
  if ( (*(_BYTE *)a3 & 8) != 0 )
    Session::AbortTransaction(*((Session **)v24 + 3), (struct Err *)a3);
}

```

## disassembly

```asm
0x10050bc0  mov     edi, edi
0x10050bc2  push    ebp
0x10050bc3  mov     ebp, esp
0x10050bc5  push    0FFFFFFFFh
0x10050bc7  push    offset ?CreateSystemTables@SystemTable@@QAEXPAVInstance@@AAVErr@@@Z_SEH
0x10050bcc  mov     eax, large fs:0
0x10050bd2  push    eax
0x10050bd3  sub     esp, 0D8h
0x10050bd9  mov     eax, ___security_cookie
0x10050bde  xor     eax, ebp
0x10050be0  mov     [ebp+var_10], eax
0x10050be3  push    ebx
0x10050be4  push    esi
0x10050be5  push    edi
0x10050be6  push    eax
0x10050be7  lea     eax, [ebp+var_C]
0x10050bea  mov     large fs:0, eax
0x10050bf0  mov     [ebp+var_A4], ecx
0x10050bf6  mov     ebx, [ebp+arg_0]
0x10050bf9  mov     esi, [ebp+arg_4]
0x10050bfc  push    esi
0x10050bfd  push    1
0x10050bff  mov     ecx, [ebx+0Ch]
0x10050c02  mov     [ebp+var_98], ebx
0x10050c08  mov     [ebp+var_A8], 0
0x10050c12  mov     [ebp+var_9C], 0
0x10050c1c  call    ?BeginTransaction@Session@@QAEXW4TransactionType@@AAVErr@@@Z; Session::BeginTransaction(TransactionType,Err &)
0x10050c21  mov     edx, [ebp+var_A4]
0x10050c27  mov     eax, [edx]
0x10050c29  movzx   ecx, word ptr [eax+54h]
0x10050c2d  mov     [ebp+var_B4], ecx
0x10050c33  movzx   ecx, word ptr [eax+56h]
0x10050c37  movzx   eax, word ptr [eax+58h]
0x10050c3b  mov     [ebp+var_BC], eax
0x10050c41  xor     eax, eax
0x10050c43  mov     [ebp+var_B8], ecx
0x10050c49  mov     [ebp+var_B0], eax
0x10050c4f  nop
0x10050c50  test    byte ptr [esi], 8
0x10050c53  jnz     loc_100510FD
0x10050c59  xor     ebx, ebx
0x10050c5b  mov     [ebp+var_AC], ebx
0x10050c61  mov     [ebp+var_D0], ebx
0x10050c67  mov     [ebp+var_CC], ebx
0x10050c6d  mov     edi, eax
0x10050c6f  mov     [ebp+var_4], ebx
0x10050c72  shl     edi, 5
0x10050c75  mov     [ebp+var_C4], edi
0x10050c7b  movzx   ecx, word_10066254[edi]
0x10050c82  cmp     ecx, 1
0x10050c85  jz      short loc_10050CA0
0x10050c87  mov     eax, [edx]
0x10050c89  cmp     dword ptr [eax+44h], 4
0x10050c8d  jnz     short loc_10050C94
0x10050c8f  test    cx, cx
0x10050c92  jz      short loc_10050CA0
0x10050c94  mov     [ebp+var_4], 0FFFFFFFFh
0x10050c9b  jmp     loc_100510CF
0x10050ca0  mov     eax, dword_10066258[edi]
0x10050ca6  cmp     eax, 5; switch 6 cases
0x10050ca9  ja      short def_10050CAB; jumptable 10050CAB default case
0x10050cab  jmp     ds:jpt_10050CAB[eax*4]; switch jump
0x10050cb2  mov     eax, [edx]; jumptable 10050CAB case 0
0x10050cb4  mov     eax, [eax+184h]
0x10050cba  jmp     short loc_10050D12
0x10050cbc  mov     eax, [edx]; jumptable 10050CAB case 1
0x10050cbe  mov     eax, [eax+188h]
0x10050cc4  jmp     short loc_10050D12
0x10050cc6  mov     ecx, [edx]; jumptable 10050CAB case 2
0x10050cc8  xor     eax, eax
0x10050cca  cmp     dword ptr [ecx+0DCh], 778h
0x10050cd4  setl    al
0x10050cd7  lea     eax, ds:18Ch[eax*4]
0x10050cde  mov     eax, [eax+ecx]
0x10050ce1  jmp     short loc_10050D12
0x10050ce3  mov     ecx, [edx]; jumptable 10050CAB case 3
0x10050ce5  xor     eax, eax
0x10050ce7  cmp     dword ptr [ecx+0DCh], 778h
0x10050cf1  setnl   al
0x10050cf4  lea     eax, ds:18Ch[eax*4]
0x10050cfb  mov     eax, [eax+ecx]
0x10050cfe  jmp     short loc_10050D12
0x10050d00  mov     eax, [edx]; jumptable 10050CAB case 4
0x10050d02  mov     eax, [eax+194h]
0x10050d08  jmp     short loc_10050D12
0x10050d0a  mov     eax, [edx]; jumptable 10050CAB case 5
0x10050d0c  mov     eax, [eax+198h]
0x10050d12  mov     [ebp+var_9C], eax
0x10050d18  mov     eax, [ebp+var_98]; jumptable 10050CAB default case
0x10050d1e  lea     ecx, [ebp+var_D0]
0x10050d24  push    0; char
0x10050d26  mov     eax, [eax+3Ch]
0x10050d29  push    eax; struct Transaction *
0x10050d2a  push    esi; struct Err *
0x10050d2b  push    [ebp+var_9C]; unsigned int
0x10050d31  push    ecx; struct PageRef *
0x10050d32  mov     ecx, [eax+8]; this
0x10050d35  call    ?ReadPageForUpdate@Database@@QAEXAAVPageRef@@KAAVErr@@PAVTransaction@@I@Z; Database::ReadPageForUpdate(PageRef &,ulong,Err &,Transaction *,uint)
0x10050d3a  test    byte ptr [esi], 8
0x10050d3d  jnz     loc_100510A3
0x10050d43  lea     ecx, [ebp+var_90]; this
0x10050d49  call    ??0AbstractSpacemap@@QAE@XZ; AbstractSpacemap::AbstractSpacemap(void)
0x10050d4e  mov     [ebp+var_E4], 0
0x10050d58  mov     [ebp+var_E0], 0
0x10050d62  mov     [ebp+var_DC], 0
0x10050d6c  mov     [ebp+var_D8], 0
0x10050d76  push    [ebp+var_A8]; unsigned int
0x10050d7c  mov     eax, [ebp+var_98]
0x10050d82  lea     ecx, [ebp+var_90]; this
0x10050d88  push    esi; struct Err *
0x10050d89  mov     byte ptr [ebp+var_4], 2
0x10050d8d  push    dword ptr [eax+3Ch]; struct Transaction *
0x10050d90  call    ?Create@Spacemap@@QAEKPAVTransaction@@AAVErr@@K@Z; Spacemap::Create(Transaction *,Err &,ulong)
0x10050d95  test    byte ptr [esi], 8
0x10050d98  mov     edx, eax
0x10050d9a  mov     [ebp+var_A8], edx
0x10050da0  jnz     short loc_10050DDC
0x10050da2  mov     ecx, [ebp+var_CC]
0x10050da8  mov     [ecx+23h], edx
0x10050dab  test    byte ptr [esi], 8
0x10050dae  jnz     short loc_10050DDC
0x10050db0  mov     eax, [ebp+var_98]
0x10050db6  lea     ecx, [ebp+var_90]; this
0x10050dbc  push    edx; unsigned int
0x10050dbd  push    esi; struct Err *
0x10050dbe  push    dword ptr [eax+3Ch]; struct Transaction *
0x10050dc1  call    ?Create@Spacemap@@QAEKPAVTransaction@@AAVErr@@K@Z; Spacemap::Create(Transaction *,Err &,ulong)
0x10050dc6  test    byte ptr [esi], 8
0x10050dc9  mov     edx, eax
0x10050dcb  mov     [ebp+var_A8], eax
0x10050dd1  jnz     short loc_10050DDC
0x10050dd3  mov     eax, [ebp+var_CC]
0x10050dd9  mov     [eax+27h], edx
0x10050ddc  lea     eax, [ebp+var_24]
0x10050ddf  mov     byte ptr [ebp+var_4], 3
0x10050de3  push    eax; struct Err *
0x10050de4  lea     ecx, [ebp+var_90]; this
0x10050dea  mov     [ebp+var_24], 1
0x10050df1  call    ?Close@AbstractSpacemap@@QAEXAAVErr@@@Z; AbstractSpacemap::Close(Err &)
0x10050df6  test    [ebp+var_24], 0FFFFFFFEh
0x10050dfd  jz      short loc_10050E1F
0x10050dff  mov     eax, [ebp+Block]
0x10050e02  test    eax, eax
0x10050e04  jz      short loc_10050E0F
0x10050e06  push    eax; Block
0x10050e07  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10050e0c  add     esp, 4
0x10050e0f  mov     eax, [ebp+var_14]
0x10050e12  test    eax, eax
0x10050e14  jz      short loc_10050E1F
0x10050e16  push    eax; Block
0x10050e17  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10050e1c  add     esp, 4
0x10050e1f  mov     eax, [ebp+var_64]
0x10050e22  test    eax, eax
0x10050e24  jz      short loc_10050E2A
0x10050e26  dec     word ptr [eax+4Ch]
0x10050e2a  mov     eax, [ebp+var_74]
0x10050e2d  test    eax, eax
0x10050e2f  jz      short loc_10050E35
0x10050e31  dec     word ptr [eax+4Ch]
0x10050e35  mov     byte ptr [ebp+var_4], 0
0x10050e39  test    byte ptr [esi], 8
0x10050e3c  jnz     loc_100510A3
0x10050e42  push    778h; Size
0x10050e47  call    ??2@YAPAXI@Z; operator new(uint)
0x10050e4c  add     esp, 4
0x10050e4f  mov     [ebp+var_D4], eax
0x10050e55  mov     ecx, [ebp+var_A4]
0x10050e5b  push    esi; struct Err *
0x10050e5c  mov     byte ptr [ebp+var_4], 4
0x10050e60  push    dword ptr [ecx]; struct Database *
0x10050e62  mov     ecx, eax; this
0x10050e64  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x10050e69  mov     ebx, eax
0x10050e6b  mov     byte ptr [ebp+var_4], 0
0x10050e6f  mov     eax, [esi]
0x10050e71  mov     [ebp+var_AC], ebx
0x10050e77  test    ebx, ebx
0x10050e79  jnz     short loc_10050ECB
0x10050e7b  cmp     eax, 8
0x10050e7e  jge     short loc_10050EEC
0x10050e80  test    eax, 0FFFFFFFEh
0x10050e85  jz      short loc_10050EA7
0x10050e87  mov     eax, [esi+0Ch]
0x10050e8a  test    eax, eax
0x10050e8c  jz      short loc_10050E97
0x10050e8e  push    eax; Block
0x10050e8f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10050e94  add     esp, 4
0x10050e97  mov     eax, [esi+10h]
0x10050e9a  test    eax, eax
0x10050e9c  jz      short loc_10050EA7
0x10050e9e  push    eax; Block
0x10050e9f  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10050ea4  add     esp, 4
0x10050ea7  mov     dword ptr [esi], 8
0x10050ead  mov     dword ptr [esi+4], 0FFFFFC0Dh
0x10050eb4  mov     dword ptr [esi+8], 0
0x10050ebb  mov     dword ptr [esi+0Ch], 0
0x10050ec2  mov     dword ptr [esi+10h], 0
0x10050ec9  jmp     short loc_10050EEC
0x10050ecb  test    al, 8
0x10050ecd  jz      short loc_10050EEC
0x10050ecf  mov     ecx, ebx; this
0x10050ed1  call    ??1Table@@QAE@XZ; Table::~Table(void)
0x10050ed6  push    778h; unsigned int
0x10050edb  push    ebx; Block
0x10050edc  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x10050ee1  add     esp, 8
0x10050ee4  xor     ebx, ebx
0x10050ee6  mov     [ebp+var_AC], ebx
0x10050eec  test    byte ptr [esi], 8
0x10050eef  jnz     loc_100510A3
0x10050ef5  inc     dword ptr [ebx+4Ch]
0x10050ef8  mov     ecx, ebx
0x10050efa  push    esi
0x10050efb  push    6
0x10050efd  push    [ebp+var_9C]
0x10050f03  push    [ebp+var_98]
0x10050f09  call    ?Open@Table@@QAEXPAVInstance@@KW4TblMode@@AAVErr@@@Z; Table::Open(Instance *,ulong,TblMode,Err &)
0x10050f0e  test    byte ptr [esi], 8
0x10050f11  jnz     loc_100510A3
0x10050f17  xor     eax, eax
0x10050f19  mov     [ebp+var_A0], eax
0x10050f1f  cmp     dword_10066260[edi], eax
0x10050f25  jbe     loc_10050FD3
0x10050f2b  nop     dword ptr [eax+eax+00h]
0x10050f30  test    byte ptr [esi], 8
0x10050f33  jnz     loc_10050FD3
0x10050f39  mov     edx, dword_10066264[edi]
0x10050f3f  shl     eax, 4
0x10050f42  add     edx, eax
0x10050f44  mov     cl, byte ptr [ebp+var_14]
0x10050f47  and     cl, 0F9h
0x10050f4a  or      cl, 9
0x10050f4d  push    esi; struct Err *
0x10050f4e  movzx   eax, byte ptr [edx+4]
0x10050f52  mov     [ebp+var_30], al
0x10050f55  mov     eax, [edx+8]
0x10050f58  mov     [ebp+var_2C], eax
0x10050f5b  movzx   eax, byte ptr [edx+0Ch]
0x10050f5f  mov     [ebp+var_28], al
0x10050f62  mov     eax, [ebp+var_B4]
0x10050f68  movzx   eax, ax
0x10050f6b  mov     [ebp+var_24], eax
0x10050f6e  mov     eax, [ebp+var_B8]
0x10050f74  movzx   eax, ax
0x10050f77  mov     [ebp+var_20], eax
0x10050f7a  mov     eax, [ebp+var_BC]
0x10050f80  movzx   eax, ax
0x10050f83  mov     [ebp+var_1C], eax
0x10050f86  mov     byte ptr [ebp+var_14], cl
0x10050f89  and     cl, 0Fh
0x10050f8c  movzx   eax, byte ptr [edx+0Dh]
0x10050f90  and     byte ptr [ebp+var_14+1], 0F8h
0x10050f94  and     al, 1
0x10050f96  or      al, 0FCh
0x10050f98  mov     [ebp+Block], 0
0x10050f9f  shl     al, 4
0x10050fa2  or      al, cl
0x10050fa4  mov     ecx, ebx; this
0x10050fa6  mov     byte ptr [ebp+var_14], al
0x10050fa9  lea     eax, [ebp+var_30]
0x10050fac  push    eax; struct tagTblColDef *
0x10050fad  push    dword ptr [edx]; unsigned __int16 *
0x10050faf  push    [ebp+var_98]; struct Instance *
0x10050fb5  call    ?AddColumn@Table@@QAEPAVColumn@@PAVInstance@@PBGPBUtagTblColDef@@AAVErr@@@Z; Table::AddColumn(Instance *,ushort const *,tagTblColDef const *,Err &)
0x10050fba  mov     eax, [ebp+var_A0]
0x10050fc0  inc     eax
0x10050fc1  mov     [ebp+var_A0], eax
0x10050fc7  cmp     eax, dword_10066260[edi]
0x10050fcd  jb      loc_10050F30
0x10050fd3  xor     eax, eax
0x10050fd5  mov     [ebp+var_A0], eax
0x10050fdb  cmp     dword_10066268[edi], eax
0x10050fe1  jbe     loc_100510A3
0x10050fe7  test    byte ptr [esi], 8
0x10050fea  jnz     loc_100510A3
0x10050ff0  lea     ecx, [eax+eax*2]
0x10050ff3  mov     eax, dword_1006626C[edi]
0x10050ff9  mov     ebx, [eax+ecx*4+8]
0x10050ffd  lea     edi, [eax+ecx*4]
0x10051000  mov     eax, [edi]
0x10051002  mov     cl, [edi+4]
0x10051005  mov     [ebp+var_C0], eax
0x1005100b  and     cl, 1
0x1005100e  movzx   eax, [ebp+var_91]
0x10051015  and     al, 0FEh
0x10051017  or      cl, al
0x10051019  mov     [ebp+var_91], cl
0x1005101f  mov     al, [edi+4]
0x10051022  xor     al, cl
0x10051024  and     al, 2
0x10051026  xor     al, cl
0x10051028  mov     [ebp+var_91], al
0x1005102e  mov     cl, [edi+4]
0x10051031  xor     cl, al
0x10051033  and     cl, 4
0x10051036  xor     cl, al
  ... truncated ...
```
