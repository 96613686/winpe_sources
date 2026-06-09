# Table::CommitPrePages(Session *,Err &)

- ea: `0x10052320`
- end: `0x10052787`
- name: `?CommitPrePages@Table@@QAEXPAVSession@@AAVErr@@@Z`
- size: `1127`
- prototype: `void __thiscall(Table *__hidden this, struct Session *, struct Err *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10044950`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10012dd0`
- `0x10031580`
- `0x10031960`
- `0x100374c0`
- `0x100451d0`
- `0x10052320`
- `0x10057dd0`
- `0x1005e3b0`
- `0x1005e74d`
- `0x1005e7e8`
- `0x1005f064`

## pseudocode

```c
void __thiscall Table::CommitPrePages(Table *this, struct Session *a2, struct Err *a3)
{
  Table *v3; // edx
  Session *v4; // esi
  int v5; // edi
  int v6; // ebx
  int v7; // eax
  int v8; // ecx
  int v9; // eax
  _DWORD **v10; // ecx
  _DWORD *v11; // edi
  Table *v12; // ebx
  Table *v13; // edi
  char v14; // al
  int v15; // ebx
  _DWORD *v16; // ecx
  PhysicalIndex *v17; // edi
  struct IAccMeth *AccessMethod; // esi
  unsigned int v19; // ecx
  bool v20; // zf
  int v21; // eax
  _DWORD *v22; // esi
  int v23; // edi
  _DWORD *v24; // ebx
  int v25; // esi
  int v26; // edi
  Collection *v27; // esi
  unsigned int v28; // eax
  int v29; // edi
  Table *v30; // ebx
  int v31; // esi
  struct IAccMeth *v32; // edi
  unsigned int v33; // ecx
  unsigned int v34; // eax
  int v35; // ecx
  int v36[3]; // [esp+14h] [ebp-4Ch] BYREF
  void *v37; // [esp+20h] [ebp-40h]
  void *v38; // [esp+24h] [ebp-3Ch]
  _DWORD v39[3]; // [esp+28h] [ebp-38h] BYREF
  void *Block; // [esp+34h] [ebp-2Ch]
  void *v41; // [esp+38h] [ebp-28h]
  _DWORD *v42; // [esp+40h] [ebp-20h]
  _DWORD *v43; // [esp+44h] [ebp-1Ch]
  int v44; // [esp+48h] [ebp-18h]
  int v45; // [esp+4Ch] [ebp-14h]
  Table *v46; // [esp+50h] [ebp-10h]
  int v47; // [esp+5Ch] [ebp-4h]

  v3 = this;
  v46 = this;
  v4 = a2;
  v5 = 0;
  v6 = 1;
  v44 = 0;
  v36[0] = 1;
  v7 = *((_DWORD *)a2 + 14);
  v47 = 0;
  if ( *((_DWORD *)this + 17) == -1 )
  {
    v8 = *((_DWORD *)this + 13);
    v9 = v7 - 1;
    v45 = v9;
    if ( v8 != -1 && v8 > v9 )
    {
      if ( *((_DWORD *)v3 + 14) != -1 )
        *((_DWORD *)v3 + 14) = v9;
      if ( *((int *)v3 + 3) > 0 )
      {
        do
        {
          v10 = (_DWORD **)((char *)v3 + 4 * v5 + 376);
          v11 = *v10;
          v42 = v10;
          v43 = v11;
          if ( v11[14] > v9 )
          {
            v12 = (Table *)v11[15];
            if ( v12 != (Table *)((char *)v3 + 136) )
            {
              do
              {
                if ( *((_DWORD *)v12 + 14) < v9 )
                  break;
                v13 = (Table *)*((_DWORD *)v12 + 15);
                (**(void (__thiscall ***)(Table *, int))v12)(v12, 1);
                v12 = v13;
                v9 = v45;
              }
              while ( v13 != (Table *)((char *)v46 + 136) );
              v11 = v43;
            }
            v14 = (*(int (__thiscall **)(_DWORD *))(*v11 + 8))(v11);
            v3 = v46;
            if ( v14 && v12 == (Table *)((char *)v46 + 136) )
            {
              *v42 = (char *)v46 + 136;
              (*(void (__thiscall **)(_DWORD *, int))*v11)(v11, 1);
              v9 = v45;
              v3 = v46;
            }
            else
            {
              v9 = v45;
              v11[15] = v12;
              v11[14] = v9;
              v11[17] = 0;
            }
          }
          v5 = v44 + 1;
          v44 = v5;
        }
        while ( v5 < *((_DWORD *)v3 + 3) );
        v4 = a2;
      }
      v15 = 413;
      v44 = 413;
      do
      {
        v16 = (_DWORD *)*((_DWORD *)v3 + v15);
        v43 = v16;
        if ( v16 )
        {
          v17 = (PhysicalIndex *)v16[3];
          if ( v16[4] > v9 )
          {
            if ( v17 )
            {
              do
              {
                if ( *((_DWORD *)v17 + 4) < v9 )
                  break;
                v39[0] = 1;
                LOBYTE(v47) = 1;
                v42 = (_DWORD *)*((_DWORD *)v17 + 3);
                AccessMethod = Session::GetAccessMethod(v4, *((struct Database **)v3 + 9), (struct Err *)v39);
                if ( (v39[0] & 8) == 0 )
                {
                  PhysicalIndex::FreeAllocations(v17, AccessMethod, (struct Err *)v39);
                  v20 = (*((_DWORD *)AccessMethod + 11))-- == 1;
                  if ( v20 )
                  {
                    v21 = 1;
                    if ( *(int *)AccessMethod < 1 )
                    {
LABEL_29:
                      IAccMeth::`scalar deleting destructor'(AccessMethod, v19);
                    }
                    else
                    {
                      while ( 1 )
                      {
                        v19 = 7 * v21;
                        if ( *(_DWORD *)(*((_DWORD *)AccessMethod + 9) + 56 * v21 - 48) )
                          break;
                        if ( ++v21 > *(_DWORD *)AccessMethod )
                        {
                          if ( *((_DWORD *)AccessMethod + 8) )
                            break;
                          goto LABEL_29;
                        }
                      }
                    }
                  }
                }
                if ( *((_DWORD *)v17 + 7) )
                  operator delete[](*((void **)v17 + 7));
                if ( *(_DWORD *)v17 )
                  operator delete[](*(void **)v17);
                operator delete(v17);
                v22 = v42;
                LOBYTE(v47) = 0;
                v17 = (PhysicalIndex *)v42;
                if ( (v39[0] & 0xFFFFFFFE) != 0 )
                {
                  if ( Block )
                    operator delete[](Block);
                  if ( v41 )
                    operator delete[](v41);
                }
                v9 = v45;
                v20 = v22 == 0;
                v3 = v46;
                v4 = a2;
              }
              while ( !v20 );
              v16 = v43;
              v15 = v44;
            }
            v16[4] = v9;
            v16[3] = v17;
          }
          v16[2] = 0;
        }
        v4 = a2;
        v44 = ++v15;
      }
      while ( v15 != 445 );
      v23 = 349;
      v44 = 349;
      do
      {
        v24 = (_DWORD *)*((_DWORD *)v3 + v23);
        if ( v24 )
        {
          if ( v24[3] > v9 )
          {
            v25 = v24[5];
            if ( v25 )
            {
              do
              {
                if ( *(_DWORD *)(v25 + 12) < v9 )
                  break;
                v26 = *(_DWORD *)(v25 + 20);
                if ( *(_DWORD *)(v25 + 24) )
                  operator delete[](*(void **)(v25 + 24));
                operator delete((void *)v25);
                v9 = v45;
                v25 = v26;
              }
              while ( v26 );
              v23 = v44;
            }
            v24[3] = v9;
            if ( v24[4] <= v9 )
              v24[5] = v25;
            else
              v24[4] = v9;
          }
          if ( v24[4] == -1 )
          {
            v27 = (Collection *)v24[2];
            v28 = *((_DWORD *)v27 + 2);
            if ( v28 < *((_DWORD *)v27 + 1) || (Collection::Grow(v27, v28 + 1, (struct Err *)v36), (v36[0] & 8) == 0) )
              *(_DWORD *)(*(_DWORD *)v27 + 4 * (*((_DWORD *)v27 + 2))++) = v24;
          }
        }
        v9 = v45;
        ++v23;
        v3 = v46;
        v44 = v23;
      }
      while ( v23 != 381 );
      if ( !v45 )
      {
        v29 = 413;
        v30 = v46;
        v44 = 413;
        do
        {
          v31 = *((_DWORD *)v30 + v29);
          if ( v31 && !*(_DWORD *)(v31 + 8) )
          {
            PhysicalIndex::ClearColumnTracking((PhysicalIndex *)v31, a3);
            if ( *(_DWORD *)(v31 + 56) )
            {
              v32 = Session::GetAccessMethod(a2, *((struct Database **)v30 + 9), a3);
              PhysicalIndex::FreeAllocations((PhysicalIndex *)v31, v32, a3);
              v20 = (*((_DWORD *)v32 + 11))-- == 1;
              if ( v20 )
              {
                v33 = 1;
                if ( *(int *)v32 < 1 )
                {
LABEL_71:
                  IAccMeth::`scalar deleting destructor'(v32, v33);
                }
                else
                {
                  while ( !*(_DWORD *)(*((_DWORD *)v32 + 9) + 56 * v33 - 48) )
                  {
                    if ( (signed int)++v33 > *(_DWORD *)v32 )
                    {
                      if ( *((_DWORD *)v32 + 8) )
                        break;
                      goto LABEL_71;
                    }
                  }
                }
              }
              v29 = v44;
            }
            v34 = *(_DWORD *)(v31 + 60);
            v30 = v46;
            if ( v34 <= 0x1F )
              *((_DWORD *)v46 + v34 + 413) = 0;
            if ( *(_DWORD *)(v31 + 28) )
              operator delete[](*(void **)(v31 + 28));
            if ( *(_DWORD *)v31 )
              operator delete[](*(void **)v31);
            operator delete((void *)v31);
          }
          v44 = ++v29;
        }
        while ( v29 != 445 );
        v9 = v45;
      }
      v3 = v46;
      v35 = *((_DWORD *)v46 + 15);
      if ( v35 != -1 && v35 > v9 )
        *((_DWORD *)v46 + 15) = v9;
      if ( *((_DWORD *)v3 + 16) > v9 )
        *((_DWORD *)v3 + 16) = v9;
      v4 = a2;
      v6 = v36[0];
      *((_DWORD *)v3 + 13) = v9;
    }
    if ( !v9 )
      Table::Persist(v3, v4, a3);
  }
  if ( (v6 & 0xFFFFFFFE) != 0 )
  {
    if ( v37 )
      operator delete[](v37);
    if ( v38 )
      operator delete[](v38);
  }
}

```

## disassembly

```asm
0x10052320  mov     edi, edi
0x10052322  push    ebp
0x10052323  mov     ebp, esp
0x10052325  push    0FFFFFFFFh
0x10052327  push    offset ?CommitPrePages@Table@@QAEXPAVSession@@AAVErr@@@Z_SEH
0x1005232c  mov     eax, large fs:0
0x10052332  push    eax
0x10052333  sub     esp, 44h
0x10052336  push    ebx
0x10052337  push    esi
0x10052338  push    edi; unsigned int
0x10052339  mov     eax, ___security_cookie
0x1005233e  xor     eax, ebp
0x10052340  push    eax; unsigned int
0x10052341  lea     eax, [ebp+var_C]
0x10052344  mov     large fs:0, eax
0x1005234a  mov     edx, ecx
0x1005234c  mov     [ebp+var_10], edx
0x1005234f  mov     esi, [ebp+arg_0]
0x10052352  xor     edi, edi
0x10052354  mov     ebx, 1
0x10052359  mov     [ebp+var_18], edi
0x1005235c  mov     [ebp+var_4C], ebx
0x1005235f  mov     eax, [esi+38h]
0x10052362  mov     [ebp+var_4], edi
0x10052365  cmp     dword ptr [edx+44h], 0FFFFFFFFh
0x10052369  jnz     loc_1005274B
0x1005236f  mov     ecx, [edx+34h]
0x10052372  dec     eax
0x10052373  mov     [ebp+var_14], eax
0x10052376  cmp     ecx, 0FFFFFFFFh
0x10052379  jz      loc_1005273C
0x1005237f  cmp     ecx, eax
0x10052381  jle     loc_1005273C
0x10052387  cmp     dword ptr [edx+38h], 0FFFFFFFFh
0x1005238b  jz      short loc_10052390
0x1005238d  mov     [edx+38h], eax
0x10052390  cmp     dword ptr [edx+0Ch], 0
0x10052394  jle     loc_10052456
0x1005239a  nop     word ptr [eax+eax+00h]
0x100523a0  lea     edi, [edi+5Eh]
0x100523a3  lea     ecx, [edx+edi*4]
0x100523a6  mov     edi, [ecx]
0x100523a8  mov     [ebp+var_20], ecx
0x100523ab  mov     [ebp+var_1C], edi
0x100523ae  cmp     [edi+38h], eax
0x100523b1  jle     loc_10052443
0x100523b7  mov     ebx, [edi+3Ch]
0x100523ba  lea     ecx, [edx+88h]
0x100523c0  cmp     ebx, ecx
0x100523c2  jz      short loc_100523F2
0x100523c4  cmp     [ebx+38h], eax
0x100523c7  jl      short loc_100523EF
0x100523c9  mov     eax, [ebx]
0x100523cb  mov     edi, [ebx+3Ch]
0x100523ce  push    1; void *
0x100523d0  mov     esi, [eax]
0x100523d2  mov     ecx, esi
0x100523d4  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100523da  mov     ecx, ebx
0x100523dc  call    esi
0x100523de  mov     eax, [ebp+var_10]
0x100523e1  mov     ebx, edi
0x100523e3  add     eax, 88h
0x100523e8  cmp     edi, eax
0x100523ea  mov     eax, [ebp+var_14]
0x100523ed  jnz     short loc_100523C4
0x100523ef  mov     edi, [ebp+var_1C]
0x100523f2  mov     eax, [edi]
0x100523f4  mov     esi, [eax+8]
0x100523f7  mov     ecx, esi
0x100523f9  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100523ff  mov     ecx, edi
0x10052401  call    esi
0x10052403  mov     edx, [ebp+var_10]
0x10052406  test    al, al
0x10052408  jz      short loc_10052433
0x1005240a  lea     eax, [edx+88h]
0x10052410  cmp     ebx, eax
0x10052412  jnz     short loc_10052433
0x10052414  mov     ecx, [ebp+var_20]
0x10052417  push    1; void *
0x10052419  mov     [ecx], eax
0x1005241b  mov     eax, [edi]
0x1005241d  mov     esi, [eax]
0x1005241f  mov     ecx, esi
0x10052421  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10052427  mov     ecx, edi
0x10052429  call    esi
0x1005242b  mov     eax, [ebp+var_14]
0x1005242e  mov     edx, [ebp+var_10]
0x10052431  jmp     short loc_10052443
0x10052433  mov     eax, [ebp+var_14]
0x10052436  mov     [edi+3Ch], ebx
0x10052439  mov     [edi+38h], eax
0x1005243c  mov     dword ptr [edi+44h], 0
0x10052443  mov     edi, [ebp+var_18]
0x10052446  inc     edi
0x10052447  mov     [ebp+var_18], edi
0x1005244a  cmp     edi, [edx+0Ch]
0x1005244d  jl      loc_100523A0
0x10052453  mov     esi, [ebp+arg_0]
0x10052456  mov     ebx, 19Dh
0x1005245b  mov     [ebp+var_18], ebx
0x1005245e  mov     edi, edi
0x10052460  mov     ecx, [edx+ebx*4]
0x10052463  mov     [ebp+var_1C], ecx
0x10052466  test    ecx, ecx
0x10052468  jz      loc_10052575
0x1005246e  mov     edi, [ecx+0Ch]
0x10052471  cmp     [ecx+10h], eax
0x10052474  jle     loc_1005256E
0x1005247a  test    edi, edi
0x1005247c  jz      loc_10052568
0x10052482  cmp     [edi+10h], eax
0x10052485  jl      loc_10052562
0x1005248b  mov     [ebp+var_38], 1
0x10052492  mov     byte ptr [ebp+var_4], 1
0x10052496  mov     ecx, esi; this
0x10052498  mov     eax, [edi+0Ch]
0x1005249b  mov     [ebp+var_20], eax
0x1005249e  lea     eax, [ebp+var_38]
0x100524a1  push    eax; struct Err *
0x100524a2  push    dword ptr [edx+24h]; struct Database *
0x100524a5  call    ?GetAccessMethod@Session@@QAEPAVIAccMeth@@PAVDatabase@@AAVErr@@@Z; Session::GetAccessMethod(Database *,Err &)
0x100524aa  test    byte ptr [ebp+var_38], 8
0x100524ae  mov     esi, eax
0x100524b0  jnz     short loc_100524F5
0x100524b2  lea     eax, [ebp+var_38]
0x100524b5  mov     ecx, edi; this
0x100524b7  push    eax; struct Err *
0x100524b8  push    esi; struct IAccMeth *
0x100524b9  call    ?FreeAllocations@PhysicalIndex@@QAEXPAVIAccMeth@@AAVErr@@@Z; PhysicalIndex::FreeAllocations(IAccMeth *,Err &)
0x100524be  add     dword ptr [esi+2Ch], 0FFFFFFFFh
0x100524c2  jnz     short loc_100524F5
0x100524c4  mov     edx, [esi]
0x100524c6  mov     eax, 1
0x100524cb  cmp     edx, eax
0x100524cd  jl      short loc_100524ED
0x100524cf  mov     ebx, [esi+24h]
0x100524d2  lea     ecx, ds:0[eax*8]
0x100524d9  sub     ecx, eax
0x100524db  cmp     dword ptr [ebx+ecx*8-30h], 0
0x100524e0  ja      short loc_100524F5
0x100524e2  inc     eax
0x100524e3  cmp     eax, edx
0x100524e5  jle     short loc_100524D2
0x100524e7  cmp     dword ptr [esi+20h], 0
0x100524eb  ja      short loc_100524F5
0x100524ed  push    ecx; unsigned int
0x100524ee  mov     ecx, esi; this
0x100524f0  call    ??_GIAccMeth@@AAEPAXI@Z; IAccMeth::`scalar deleting destructor'(uint)
0x100524f5  mov     eax, [edi+1Ch]
0x100524f8  test    eax, eax
0x100524fa  jz      short loc_10052505
0x100524fc  push    eax; Block
0x100524fd  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10052502  add     esp, 4
0x10052505  mov     eax, [edi]
0x10052507  test    eax, eax
0x10052509  jz      short loc_10052514
0x1005250b  push    eax; Block
0x1005250c  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10052511  add     esp, 4
0x10052514  push    4Ch ; 'L'; unsigned int
0x10052516  push    edi; Block
0x10052517  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x1005251c  mov     esi, [ebp+var_20]
0x1005251f  add     esp, 8
0x10052522  mov     byte ptr [ebp+var_4], 0
0x10052526  mov     edi, esi
0x10052528  test    [ebp+var_38], 0FFFFFFFEh
0x1005252f  jz      short loc_10052551
0x10052531  mov     eax, [ebp+Block]
0x10052534  test    eax, eax
0x10052536  jz      short loc_10052541
0x10052538  push    eax; Block
0x10052539  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005253e  add     esp, 4
0x10052541  mov     eax, [ebp+var_28]
0x10052544  test    eax, eax
0x10052546  jz      short loc_10052551
0x10052548  push    eax; Block
0x10052549  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005254e  add     esp, 4
0x10052551  mov     eax, [ebp+var_14]
0x10052554  test    esi, esi
0x10052556  mov     edx, [ebp+var_10]
0x10052559  mov     esi, [ebp+arg_0]
0x1005255c  jnz     loc_10052482
0x10052562  mov     ecx, [ebp+var_1C]
0x10052565  mov     ebx, [ebp+var_18]
0x10052568  mov     [ecx+10h], eax
0x1005256b  mov     [ecx+0Ch], edi
0x1005256e  mov     dword ptr [ecx+8], 0
0x10052575  mov     esi, [ebp+arg_0]
0x10052578  inc     ebx
0x10052579  mov     [ebp+var_18], ebx
0x1005257c  cmp     ebx, 1BDh
0x10052582  jnz     loc_10052460
0x10052588  mov     edi, 15Dh
0x1005258d  mov     [ebp+var_18], edi
0x10052590  mov     ebx, [edx+edi*4]
0x10052593  test    ebx, ebx
0x10052595  jz      loc_10052618
0x1005259b  cmp     [ebx+0Ch], eax
0x1005259e  jle     short loc_100525E9
0x100525a0  mov     esi, [ebx+14h]
0x100525a3  test    esi, esi
0x100525a5  jz      short loc_100525D9
0x100525a7  cmp     [esi+0Ch], eax
0x100525aa  jl      short loc_100525D6
0x100525ac  mov     eax, [esi+18h]
0x100525af  mov     edi, [esi+14h]
0x100525b2  test    eax, eax
0x100525b4  jz      short loc_100525BF
0x100525b6  push    eax; Block
0x100525b7  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100525bc  add     esp, 4
0x100525bf  push    0C4h; unsigned int
0x100525c4  push    esi; Block
0x100525c5  call    ??3@YAXPAXI@Z; operator delete(void *,uint)
0x100525ca  mov     eax, [ebp+var_14]
0x100525cd  add     esp, 8
0x100525d0  mov     esi, edi
0x100525d2  test    edi, edi
0x100525d4  jnz     short loc_100525A7
0x100525d6  mov     edi, [ebp+var_18]
0x100525d9  mov     [ebx+0Ch], eax
0x100525dc  cmp     [ebx+10h], eax
0x100525df  jle     short loc_100525E6
0x100525e1  mov     [ebx+10h], eax
0x100525e4  jmp     short loc_100525E9
0x100525e6  mov     [ebx+14h], esi
0x100525e9  cmp     dword ptr [ebx+10h], 0FFFFFFFFh
0x100525ed  jnz     short loc_10052618
0x100525ef  mov     esi, [ebx+8]
0x100525f2  mov     eax, [esi+8]
0x100525f5  cmp     eax, [esi+4]
0x100525f8  jb      short loc_1005260D
0x100525fa  lea     ecx, [ebp+var_4C]
0x100525fd  inc     eax
0x100525fe  push    ecx; struct Err *
0x100525ff  push    eax; unsigned int
0x10052600  mov     ecx, esi; this
0x10052602  call    ?Grow@Collection@@QAEXKAAVErr@@@Z; Collection::Grow(ulong,Err &)
0x10052607  test    byte ptr [ebp+var_4C], 8
0x1005260b  jnz     short loc_10052618
0x1005260d  mov     ecx, [esi+8]
0x10052610  mov     eax, [esi]
0x10052612  mov     [eax+ecx*4], ebx
0x10052615  inc     dword ptr [esi+8]
0x10052618  mov     eax, [ebp+var_14]
0x1005261b  inc     edi
0x1005261c  mov     edx, [ebp+var_10]
0x1005261f  mov     [ebp+var_18], edi
0x10052622  cmp     edi, 17Dh
0x10052628  jnz     loc_10052590
0x1005262e  test    eax, eax
0x10052630  jnz     loc_10052719
0x10052636  mov     edi, 19Dh
0x1005263b  mov     ebx, edx
0x1005263d  mov     [ebp+var_18], edi
0x10052640  mov     esi, [ebx+edi*4]
0x10052643  test    esi, esi
0x10052645  jz      loc_10052706
0x1005264b  cmp     dword ptr [esi+8], 0
0x1005264f  jnz     loc_10052706
0x10052655  push    [ebp+arg_4]; struct Err *
0x10052658  mov     ecx, esi; this
0x1005265a  call    ?ClearColumnTracking@PhysicalIndex@@QAEXAAVErr@@@Z; PhysicalIndex::ClearColumnTracking(Err &)
0x1005265f  cmp     dword ptr [esi+38h], 0
0x10052663  jz      short loc_100526C6
0x10052665  push    [ebp+arg_4]; struct Err *
0x10052668  mov     ecx, [ebp+arg_0]; this
0x1005266b  push    dword ptr [ebx+24h]; struct Database *
0x1005266e  call    ?GetAccessMethod@Session@@QAEPAVIAccMeth@@PAVDatabase@@AAVErr@@@Z; Session::GetAccessMethod(Database *,Err &)
0x10052673  push    [ebp+arg_4]; struct Err *
0x10052676  mov     edi, eax
0x10052678  mov     ecx, esi; this
0x1005267a  push    edi; struct IAccMeth *
0x1005267b  call    ?FreeAllocations@PhysicalIndex@@QAEXPAVIAccMeth@@AAVErr@@@Z; PhysicalIndex::FreeAllocations(IAccMeth *,Err &)
0x10052680  add     dword ptr [edi+2Ch], 0FFFFFFFFh
0x10052684  jnz     short loc_100526C3
0x10052686  mov     edx, [edi]
0x10052688  mov     ecx, 1
0x1005268d  cmp     edx, ecx
0x1005268f  jl      short loc_100526BB
0x10052691  mov     ebx, [edi+24h]
0x10052694  nop     dword ptr [eax+00h]
0x10052698  nop     dword ptr [eax+eax+00000000h]
0x100526a0  lea     eax, ds:0[ecx*8]
0x100526a7  sub     eax, ecx
0x100526a9  cmp     dword ptr [ebx+eax*8-30h], 0
0x100526ae  ja      short loc_100526C3
0x100526b0  inc     ecx
0x100526b1  cmp     ecx, edx
0x100526b3  jle     short loc_100526A0
0x100526b5  cmp     dword ptr [edi+20h], 0
0x100526b9  ja      short loc_100526C3
  ... truncated ...
```
