# Table::DeleteIndex(Instance *,ushort const *,Err &,TblRefOrIdx)

- ea: `0x10055ed0`
- end: `0x1005626b`
- name: `?DeleteIndex@Table@@QAEXPAVInstance@@PBGAAVErr@@W4TblRefOrIdx@@@Z`
- size: `923`
- prototype: ``
- caller_count: `5`
- callee_count: `22`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10029cd0`
- `0x1002a210`
- `0x1004cee0`
- `0x10053950`
- `0x10055ed0`

## callees

- `0x1000f750`
- `0x10025ee0`
- `0x10031960`
- `0x10044860`
- `0x10044950`
- `0x10044cb0`
- `0x10051890`
- `0x100518a0`
- `0x10052140`
- `0x10053400`
- `0x100536a0`
- `0x10055ed0`
- `0x10057150`
- `0x100574a0`
- `0x10057520`
- `0x100591e0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e798`
- `0x1005e7e8`
- `0x1005f064`
- `0x1005f07c`

## pseudocode

```c
void __thiscall Table::DeleteIndex(int this, struct Instance *a2, unsigned __int16 *a3, struct Err *a4, int a5)
{
  struct Err *v6; // edi
  bool v7; // zf
  struct Session *v8; // eax
  int v9; // eax
  int IndexOrRef; // eax
  int v11; // ebx
  int *v12; // eax
  unsigned int v13; // ecx
  unsigned int v14; // edx
  int v15; // edi
  int v16; // ebx
  char v17; // al
  struct Session *v18; // edx
  int v19; // eax
  unsigned int v20; // ecx
  int v21; // eax
  Table *v22; // ebx
  int v23; // eax
  int v24; // ecx
  unsigned int v25; // edx
  void *v26; // eax
  Table *v27; // eax
  int v28; // ecx
  int v29; // ecx
  PhysicalIndex *v30; // ebx
  int v31; // edx
  unsigned int v32; // edx
  _DWORD *v33; // ecx
  unsigned int v34; // eax
  unsigned int v35; // eax
  Session *v36; // ebx
  int v37[3]; // [esp+10h] [ebp-40h] BYREF
  void *Block; // [esp+1Ch] [ebp-34h]
  void *v39; // [esp+20h] [ebp-30h]
  int v40; // [esp+24h] [ebp-2Ch]
  void *v41; // [esp+28h] [ebp-28h]
  int v42; // [esp+2Ch] [ebp-24h]
  int v43; // [esp+30h] [ebp-20h]
  int v44; // [esp+34h] [ebp-1Ch] BYREF
  struct Session *v45; // [esp+38h] [ebp-18h]
  int v46; // [esp+3Ch] [ebp-14h]
  char v47; // [esp+42h] [ebp-Eh]
  char v48; // [esp+43h] [ebp-Dh]
  int v49; // [esp+4Ch] [ebp-4h]

  ++*(_DWORD *)(this + 340);
  v40 = this;
  v6 = a4;
  v49 = 0;
  v7 = *(_DWORD *)(this + 44) == 2;
  v8 = (struct Session *)*((_DWORD *)a2 + 3);
  v43 = 0;
  v44 = 0;
  v46 = 0;
  v47 = 0;
  v45 = v8;
  v48 = 0;
  if ( v7 || *(_DWORD *)(this + 48) == 8 )
  {
    v9 = *(_DWORD *)(*(_DWORD *)(this + 36) + 104);
    if ( !v9 || v9 == 3 )
      Err::SetError(a4, -1809, 0);
  }
  else
  {
    Err::SetError(a4, -1309, 0);
  }
  if ( (*(_BYTE *)a4 & 8) == 0 )
  {
    IndexOrRef = Table::FindIndexOrRef(this, a3, &v44, a5, a4);
    v7 = (*(_BYTE *)a4 & 8) == 0;
    v43 = IndexOrRef;
    if ( v7 )
    {
      v11 = *(_DWORD *)(this + 4 * IndexOrRef + 1396);
      v46 = v11;
      if ( *(_DWORD *)(v11 + 32) )
        Err::SetError(a4, -1051, IndexOrRef);
      if ( (*(_BYTE *)a4 & 8) == 0 )
      {
        v12 = *(int **)(v11 + 8);
        v13 = 0;
        v14 = v12[2];
        if ( v14 )
        {
          v15 = *v12;
          v16 = 0;
          do
          {
            v17 = *(_BYTE *)(*(_DWORD *)(v15 + 4 * v13) + 41);
            if ( v17 == 1 )
            {
              v48 = 1;
            }
            else
            {
              v7 = v17 == 0;
              v17 = v48;
              if ( v7 )
                ++v16;
            }
            ++v13;
          }
          while ( v13 < v14 );
          v6 = a4;
          v7 = v16 == 1;
          v11 = v46;
          if ( v7 && v17 && !a5 )
            Err::SetError(a4, -1051, v13);
        }
        if ( (*(_BYTE *)v6 & 8) == 0 )
        {
          Session::BeginTransaction(v45, 1, v6);
          if ( (*(_BYTE *)v6 & 8) == 0 )
          {
            v18 = v45;
            v19 = 0;
            v47 = 1;
            v20 = *((_DWORD *)v45 + 5);
            if ( v20 )
            {
              while ( *(_DWORD *)(*((_DWORD *)v45 + 3) + 4 * v19) != this )
              {
                if ( ++v19 >= v20 )
                {
                  v18 = v45;
                  goto LABEL_29;
                }
              }
            }
            else
            {
LABEL_29:
              if ( v19 == v20 )
                Table::AddNotify((Table *)this, v18);
            }
            if ( (*(_BYTE *)v6 & 8) == 0 )
            {
              if ( *(_BYTE *)(v11 + 41) != 2 )
              {
LABEL_47:
                if ( (*(_BYTE *)v6 & 8) == 0 )
                {
                  *(_DWORD *)(*(_DWORD *)(this + 4 * v43 + 1396) + 16) = *((_DWORD *)v45 + 14) - 1;
                  memcpy(
                    (void *)(this + 4 * (v44 + 381)),
                    (const void *)(this + 4 * (v44 + 382)),
                    4 * (*(_DWORD *)(this + 24) - v44) - 4);
                  --*(_DWORD *)(this + 24);
                  v29 = v46;
                  *(_DWORD *)(this + 4 * *(_DWORD *)(this + 24) + 1524) = -1;
                  v30 = *(PhysicalIndex **)(v29 + 8);
                  v31 = *((_DWORD *)v30 + 2);
                  if ( v31 )
                  {
                    *(_DWORD *)(*(_DWORD *)v30 + 4 * v31) = v29;
                    v32 = 0;
                    v33 = *(_DWORD **)v30;
                    if ( **(_DWORD **)v30 != v46 )
                    {
                      do
                        ++v32;
                      while ( v33[v32] != v46 );
                    }
                    v34 = *((_DWORD *)v30 + 2);
                    if ( v32 < v34 )
                    {
                      v35 = v34 - 1;
                      *((_DWORD *)v30 + 2) = v35;
                      v33[v32] = v33[v35];
                    }
                  }
                  if ( !*((_DWORD *)v30 + 2) )
                    PhysicalIndex::ClearColumnTracking(v30, v6);
                }
                goto LABEL_55;
              }
              v21 = v46;
              v22 = (Table *)this;
              v42 = *(_DWORD *)(v46 + 48);
              if ( v42 != *(_DWORD *)(this + 40) )
              {
                v23 = *(_DWORD *)(this + 36);
                v24 = 0;
                v25 = *(_DWORD *)(v23 + 56);
                if ( !v25 )
                  goto LABEL_38;
                v26 = *(void **)(v23 + 48);
                v41 = v26;
                while ( 1 )
                {
                  v6 = a4;
                  if ( *(_DWORD *)(*((_DWORD *)v26 + v24) + 40) == v42 )
                    break;
                  v26 = v41;
                  if ( ++v24 >= v25 )
                    goto LABEL_38;
                }
                v22 = *(Table **)(4 * v24 + *(_DWORD *)(*(_DWORD *)(this + 36) + 48));
                if ( v22 )
                {
                  Table::CompatibleMode(v22, v45, 2, a4);
                }
                else
                {
LABEL_38:
                  v41 = operator new(0x778u);
                  LOBYTE(v49) = 1;
                  v27 = Table::Table((Table *)v41, *(struct Database **)(this + 36), v6);
                  v22 = v27;
                  LOBYTE(v49) = 0;
                  if ( v27 )
                    Table::Open(v27, a2, *(_DWORD *)(v46 + 48), 2, v6);
                  else
                    Err::SetError(v6, -1011, v28);
                }
                v21 = v46;
              }
              if ( (*(_BYTE *)v6 & 8) == 0 )
              {
                ++*((_DWORD *)v22 + 19);
                Table::DeleteIndex(v22, a2, **((_DWORD **)v22 + *(_DWORD *)(v21 + 44) + 349), v6, 1);
                Table::Release(v22, a2);
                if ( v22 == (Table *)this )
                  Table::FindIndexFromName((Table *)this, a3, &v44);
                goto LABEL_47;
              }
            }
          }
        }
      }
    }
  }
LABEL_55:
  if ( v47 )
  {
    if ( (*(_BYTE *)v6 & 8) != 0 )
    {
      v36 = v45;
    }
    else
    {
      Table::DDLPerformed((Table *)this, a2);
      v36 = v45;
      Session::CommitTransaction(v45, (void **)v6, 0);
    }
    if ( (*(_BYTE *)v6 & 8) != 0 )
    {
      v37[0] = 1;
      LOBYTE(v49) = 2;
      Session::AbortTransaction(v36, (struct Err *)v37);
      if ( (v37[0] & 0xFFFFFFFE) != 0 )
      {
        if ( Block )
          operator delete[](Block);
        if ( v39 )
          operator delete[](v39);
      }
    }
  }
  --*(_DWORD *)(this + 340);
}

```

## disassembly

```asm
0x10055ed0  mov     edi, edi
0x10055ed2  push    ebp
0x10055ed3  mov     ebp, esp
0x10055ed5  push    0FFFFFFFFh
0x10055ed7  push    offset ?DeleteIndex@Table@@QAEXPAVInstance@@PBGAAVErr@@W4TblRefOrIdx@@@Z_SEH
0x10055edc  mov     eax, large fs:0
0x10055ee2  push    eax
0x10055ee3  sub     esp, 34h
0x10055ee6  push    ebx
0x10055ee7  push    esi
0x10055ee8  push    edi
0x10055ee9  mov     eax, ___security_cookie
0x10055eee  xor     eax, ebp
0x10055ef0  push    eax
0x10055ef1  lea     eax, [ebp+var_C]
0x10055ef4  mov     large fs:0, eax
0x10055efa  mov     esi, ecx
0x10055efc  inc     dword ptr [esi+154h]
0x10055f02  mov     [ebp+var_2C], esi
0x10055f05  mov     eax, [ebp+arg_0]
0x10055f08  xor     ecx, ecx
0x10055f0a  mov     edi, [ebp+arg_8]
0x10055f0d  xor     ebx, ebx
0x10055f0f  mov     [ebp+var_4], 0
0x10055f16  cmp     dword ptr [esi+2Ch], 2
0x10055f1a  mov     eax, [eax+0Ch]
0x10055f1d  mov     [ebp+var_20], ecx
0x10055f20  mov     [ebp+var_1C], ecx
0x10055f23  mov     [ebp+var_14], ebx
0x10055f26  mov     [ebp+var_E], cl
0x10055f29  mov     [ebp+var_18], eax
0x10055f2c  mov     [ebp+var_D], cl
0x10055f2f  jz      short loc_10055F3F
0x10055f31  cmp     dword ptr [esi+30h], 8
0x10055f35  jz      short loc_10055F3F
0x10055f37  push    ecx
0x10055f38  push    0FFFFFAE3h
0x10055f3d  jmp     short loc_10055F54
0x10055f3f  mov     eax, [esi+24h]
0x10055f42  mov     eax, [eax+68h]
0x10055f45  test    eax, eax
0x10055f47  jz      short loc_10055F4E
0x10055f49  cmp     eax, 3
0x10055f4c  jnz     short loc_10055F5D
0x10055f4e  push    ecx
0x10055f4f  push    0FFFFF8EFh
0x10055f54  mov     ecx, edi
0x10055f56  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10055f5b  xor     ecx, ecx
0x10055f5d  test    byte ptr [edi], 8
0x10055f60  jnz     loc_100561E6
0x10055f66  push    edi
0x10055f67  push    [ebp+arg_C]
0x10055f6a  lea     eax, [ebp+var_1C]
0x10055f6d  mov     ecx, esi
0x10055f6f  push    eax
0x10055f70  push    [ebp+arg_4]
0x10055f73  call    ?FindIndexOrRef@Table@@AAEJPBGPAJW4TblRefOrIdx@@AAVErr@@@Z; Table::FindIndexOrRef(ushort const *,long *,TblRefOrIdx,Err &)
0x10055f78  test    byte ptr [edi], 8
0x10055f7b  mov     ecx, eax
0x10055f7d  mov     [ebp+var_20], eax
0x10055f80  jnz     loc_100561E6
0x10055f86  mov     ebx, [esi+ecx*4+574h]
0x10055f8d  mov     [ebp+var_14], ebx
0x10055f90  cmp     dword ptr [ebx+20h], 0
0x10055f94  jz      short loc_10055FA3
0x10055f96  push    ecx
0x10055f97  push    0FFFFFBE5h
0x10055f9c  mov     ecx, edi
0x10055f9e  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10055fa3  test    byte ptr [edi], 8
0x10055fa6  jnz     loc_100561E6
0x10055fac  mov     eax, [ebx+8]
0x10055faf  xor     ecx, ecx
0x10055fb1  mov     edx, [eax+8]
0x10055fb4  test    edx, edx
0x10055fb6  jz      short loc_10055FFE
0x10055fb8  mov     edi, [eax]
0x10055fba  xor     ebx, ebx
0x10055fbc  nop     dword ptr [eax+00h]
0x10055fc0  mov     eax, [edi+ecx*4]
0x10055fc3  mov     al, [eax+29h]
0x10055fc6  cmp     al, 1
0x10055fc8  jnz     short loc_10055FCF
0x10055fca  mov     [ebp+var_D], al
0x10055fcd  jmp     short loc_10055FD7
0x10055fcf  test    al, al
0x10055fd1  mov     al, [ebp+var_D]
0x10055fd4  jnz     short loc_10055FD7
0x10055fd6  inc     ebx
0x10055fd7  inc     ecx
0x10055fd8  cmp     ecx, edx
0x10055fda  jb      short loc_10055FC0
0x10055fdc  mov     edi, [ebp+arg_8]
0x10055fdf  cmp     ebx, 1
0x10055fe2  mov     ebx, [ebp+var_14]
0x10055fe5  jnz     short loc_10055FFE
0x10055fe7  test    al, al
0x10055fe9  jz      short loc_10055FFE
0x10055feb  cmp     [ebp+arg_C], 0
0x10055fef  jnz     short loc_10055FFE
0x10055ff1  push    ecx
0x10055ff2  push    0FFFFFBE5h
0x10055ff7  mov     ecx, edi
0x10055ff9  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10055ffe  test    byte ptr [edi], 8
0x10056001  jnz     loc_100561E6
0x10056007  mov     ecx, [ebp+var_18]
0x1005600a  push    edi
0x1005600b  push    1
0x1005600d  call    ?BeginTransaction@Session@@QAEXW4TransactionType@@AAVErr@@@Z; Session::BeginTransaction(TransactionType,Err &)
0x10056012  test    byte ptr [edi], 8
0x10056015  jnz     loc_100561E6
0x1005601b  mov     edx, [ebp+var_18]
0x1005601e  xor     eax, eax
0x10056020  mov     [ebp+var_E], 1
0x10056024  mov     ecx, [edx+14h]
0x10056027  test    ecx, ecx
0x10056029  jz      short loc_1005603D
0x1005602b  mov     edx, [edx+0Ch]
0x1005602e  mov     edi, edi
0x10056030  cmp     [edx+eax*4], esi
0x10056033  jz      short loc_10056049
0x10056035  inc     eax
0x10056036  cmp     eax, ecx
0x10056038  jb      short loc_10056030
0x1005603a  mov     edx, [ebp+var_18]
0x1005603d  cmp     eax, ecx
0x1005603f  jnz     short loc_10056049
0x10056041  push    edx; struct Session *
0x10056042  mov     ecx, esi; this
0x10056044  call    ?AddNotify@Table@@AAEXPAVSession@@@Z; Table::AddNotify(Session *)
0x10056049  test    byte ptr [edi], 8
0x1005604c  jnz     loc_100561E6
0x10056052  cmp     byte ptr [ebx+29h], 2
0x10056056  jnz     loc_1005614A
0x1005605c  mov     eax, [ebp+var_14]
0x1005605f  mov     ebx, esi
0x10056061  mov     ecx, [eax+30h]
0x10056064  mov     [ebp+var_24], ecx
0x10056067  cmp     ecx, [esi+28h]
0x1005606a  jz      loc_10056109
0x10056070  mov     eax, [esi+24h]
0x10056073  xor     ecx, ecx
0x10056075  mov     edx, [eax+38h]
0x10056078  test    edx, edx
0x1005607a  jz      short loc_1005609F
0x1005607c  mov     eax, [eax+30h]
0x1005607f  mov     [ebp+var_28], eax
0x10056082  mov     edi, [ebp+var_24]
0x10056085  lea     ebx, ds:0[ecx*4]
0x1005608c  mov     eax, [ebx+eax]
0x1005608f  cmp     [eax+28h], edi
0x10056092  mov     edi, [ebp+arg_8]
0x10056095  jz      short loc_100560D7
0x10056097  mov     eax, [ebp+var_28]
0x1005609a  inc     ecx
0x1005609b  cmp     ecx, edx
0x1005609d  jb      short loc_10056082
0x1005609f  push    778h; Size
0x100560a4  call    ??2@YAPAXI@Z; operator new(uint)
0x100560a9  add     esp, 4
0x100560ac  mov     [ebp+var_28], eax
0x100560af  push    edi; struct Err *
0x100560b0  mov     byte ptr [ebp+var_4], 1
0x100560b4  mov     ecx, eax; this
0x100560b6  push    dword ptr [esi+24h]; struct Database *
0x100560b9  call    ??0Table@@QAE@PAVDatabase@@AAVErr@@@Z; Table::Table(Database *,Err &)
0x100560be  mov     ebx, eax
0x100560c0  mov     byte ptr [ebp+var_4], 0
0x100560c4  test    ebx, ebx
0x100560c6  jnz     short loc_100560F3
0x100560c8  push    ecx
0x100560c9  push    0FFFFFC0Dh
0x100560ce  mov     ecx, edi
0x100560d0  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x100560d5  jmp     short loc_10056106
0x100560d7  mov     eax, [esi+24h]
0x100560da  mov     eax, [eax+30h]
0x100560dd  mov     ebx, [ebx+eax]
0x100560e0  test    ebx, ebx
0x100560e2  jz      short loc_1005609F
0x100560e4  push    edi
0x100560e5  push    2
0x100560e7  push    [ebp+var_18]
0x100560ea  mov     ecx, ebx
0x100560ec  call    ?CompatibleMode@Table@@QAEXPAVSession@@W4TblMode@@AAVErr@@@Z; Table::CompatibleMode(Session *,TblMode,Err &)
0x100560f1  jmp     short loc_10056106
0x100560f3  mov     ecx, [ebp+var_14]
0x100560f6  push    edi
0x100560f7  push    2
0x100560f9  push    dword ptr [ecx+30h]
0x100560fc  mov     ecx, ebx
0x100560fe  push    [ebp+arg_0]
0x10056101  call    ?Open@Table@@QAEXPAVInstance@@KW4TblMode@@AAVErr@@@Z; Table::Open(Instance *,ulong,TblMode,Err &)
0x10056106  mov     eax, [ebp+var_14]
0x10056109  test    byte ptr [edi], 8
0x1005610c  jnz     loc_100561E6
0x10056112  inc     dword ptr [ebx+4Ch]
0x10056115  mov     ecx, ebx
0x10056117  mov     eax, [eax+2Ch]
0x1005611a  push    1
0x1005611c  push    edi
0x1005611d  mov     eax, [ebx+eax*4+574h]
0x10056124  push    dword ptr [eax]
0x10056126  push    [ebp+arg_0]
0x10056129  call    ?DeleteIndex@Table@@QAEXPAVInstance@@PBGAAVErr@@W4TblRefOrIdx@@@Z; Table::DeleteIndex(Instance *,ushort const *,Err &,TblRefOrIdx)
0x1005612e  push    [ebp+arg_0]; struct Instance *
0x10056131  mov     ecx, ebx; this
0x10056133  call    ?Release@Table@@QAEJPAVInstance@@@Z; Table::Release(Instance *)
0x10056138  cmp     ebx, esi
0x1005613a  jnz     short loc_1005614A
0x1005613c  lea     eax, [ebp+var_1C]
0x1005613f  mov     ecx, esi; this
0x10056141  push    eax; int *
0x10056142  push    [ebp+arg_4]; unsigned __int16 *
0x10056145  call    ?FindIndexFromName@Table@@QAEJPBGPAJ@Z; Table::FindIndexFromName(ushort const *,long *)
0x1005614a  test    byte ptr [edi], 8
0x1005614d  jnz     loc_100561E6
0x10056153  mov     ecx, [ebp+var_20]
0x10056156  mov     eax, [ebp+var_18]
0x10056159  mov     ecx, [esi+ecx*4+574h]
0x10056160  mov     eax, [eax+38h]
0x10056163  dec     eax
0x10056164  mov     [ecx+10h], eax
0x10056167  mov     eax, [esi+18h]
0x1005616a  mov     ecx, [ebp+var_1C]
0x1005616d  sub     eax, ecx
0x1005616f  lea     eax, ds:0FFFFFFFCh[eax*4]
0x10056176  push    eax; Size
0x10056177  lea     eax, [ecx+17Eh]
0x1005617d  add     ecx, 17Dh
0x10056183  lea     eax, [esi+eax*4]
0x10056186  push    eax; Src
0x10056187  lea     eax, [esi+ecx*4]
0x1005618a  push    eax; void *
0x1005618b  call    _memcpy
0x10056190  dec     dword ptr [esi+18h]
0x10056193  add     esp, 0Ch
0x10056196  mov     eax, [esi+18h]
0x10056199  mov     ecx, [ebp+var_14]
0x1005619c  mov     dword ptr [esi+eax*4+5F4h], 0FFFFFFFFh
0x100561a7  mov     ebx, [ecx+8]
0x100561aa  mov     edx, [ebx+8]
0x100561ad  test    edx, edx
0x100561af  jz      short loc_100561D8
0x100561b1  mov     eax, [ebx]
0x100561b3  mov     [eax+edx*4], ecx
0x100561b6  xor     edx, edx
0x100561b8  mov     ecx, [ebx]
0x100561ba  mov     eax, [ebp+var_14]
0x100561bd  cmp     [ecx], eax
0x100561bf  jz      short loc_100561C7
0x100561c1  inc     edx
0x100561c2  cmp     [ecx+edx*4], eax
0x100561c5  jnz     short loc_100561C1
0x100561c7  mov     eax, [ebx+8]
0x100561ca  cmp     edx, eax
0x100561cc  jnb     short loc_100561D8
0x100561ce  dec     eax
0x100561cf  mov     [ebx+8], eax
0x100561d2  mov     eax, [ecx+eax*4]
0x100561d5  mov     [ecx+edx*4], eax
0x100561d8  cmp     dword ptr [ebx+8], 0
0x100561dc  jnz     short loc_100561E6
0x100561de  push    edi; struct Err *
0x100561df  mov     ecx, ebx; this
0x100561e1  call    ?ClearColumnTracking@PhysicalIndex@@QAEXAAVErr@@@Z; PhysicalIndex::ClearColumnTracking(Err &)
0x100561e6  cmp     [ebp+var_E], 0
0x100561ea  jz      short loc_10056251
0x100561ec  test    byte ptr [edi], 8
0x100561ef  jnz     short loc_1005620A
0x100561f1  push    [ebp+arg_0]; struct Instance *
0x100561f4  mov     ecx, esi; this
0x100561f6  call    ?DDLPerformed@Table@@AAEXPAVInstance@@@Z; Table::DDLPerformed(Instance *)
0x100561fb  mov     ebx, [ebp+var_18]
0x100561fe  mov     ecx, ebx; this
0x10056200  push    0; unsigned int
0x10056202  push    edi; struct Err *
0x10056203  call    ?CommitTransaction@Session@@QAEXAAVErr@@K@Z; Session::CommitTransaction(Err &,ulong)
0x10056208  jmp     short loc_1005620D
0x1005620a  mov     ebx, [ebp+var_18]
0x1005620d  test    byte ptr [edi], 8
0x10056210  jz      short loc_10056251
0x10056212  mov     [ebp+var_40], 1
0x10056219  lea     eax, [ebp+var_40]
0x1005621c  mov     byte ptr [ebp+var_4], 2
0x10056220  push    eax; struct Err *
0x10056221  mov     ecx, ebx; this
0x10056223  call    ?AbortTransaction@Session@@QAEXAAVErr@@@Z; Session::AbortTransaction(Err &)
0x10056228  test    [ebp+var_40], 0FFFFFFFEh
0x1005622f  jz      short loc_10056251
0x10056231  mov     eax, [ebp+Block]
0x10056234  test    eax, eax
0x10056236  jz      short loc_10056241
0x10056238  push    eax; Block
0x10056239  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005623e  add     esp, 4
0x10056241  mov     eax, [ebp+var_30]
0x10056244  test    eax, eax
  ... truncated ...
```
