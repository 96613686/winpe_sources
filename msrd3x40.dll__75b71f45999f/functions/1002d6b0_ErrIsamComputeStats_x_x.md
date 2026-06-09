# ErrIsamComputeStats(x,x)

- ea: `0x1002d6b0`
- end: `0x1002dc83`
- name: `_ErrIsamComputeStats@8`
- size: `1491`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1000eb60`
- `0x10025e60`
- `0x10026140`
- `0x1002d6b0`
- `0x10039890`
- `0x10052cc0`
- `0x10054120`
- `0x100572d0`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005e7f3`

## pseudocode

```c
int __stdcall ErrIsamComputeStats(void *a1, int *a2)
{
  int v2; // eax
  Table *v3; // ebx
  int v4; // edi
  struct Instance *v5; // eax
  int v6; // ecx
  int v7; // esi
  int v8; // eax
  unsigned int v9; // edi
  unsigned int v10; // esi
  _DWORD *v11; // ebx
  _DWORD *v12; // edx
  int v13; // ecx
  int v14; // ecx
  int v15; // edi
  void *v16; // edx
  struct Instance *v17; // eax
  Table *v18; // eax
  int v19; // ebx
  int v20; // eax
  QuickKey *v21; // esi
  unsigned __int8 *v22; // ecx
  signed int v23; // eax
  QuickKey *v24; // eax
  QuickKey *v25; // ebx
  unsigned __int8 *v26; // edi
  unsigned int v27; // ecx
  unsigned __int8 *v28; // edx
  int v29; // esi
  unsigned int v30; // ecx
  bool v31; // cf
  unsigned __int8 v32; // al
  unsigned __int8 v33; // al
  unsigned __int8 v34; // al
  int v35; // eax
  int v36; // ecx
  int *v38; // [esp+48h] [ebp-80h]
  int v39; // [esp+58h] [ebp-70h] BYREF
  int v40; // [esp+5Ch] [ebp-6Ch] BYREF
  int v41; // [esp+60h] [ebp-68h]
  void *Block; // [esp+64h] [ebp-64h]
  void *v43; // [esp+68h] [ebp-60h]
  Table *v44; // [esp+6Ch] [ebp-5Ch]
  unsigned int v45[3]; // [esp+70h] [ebp-58h] BYREF
  void *v46; // [esp+7Ch] [ebp-4Ch]
  void *v47; // [esp+80h] [ebp-48h]
  void *v48[2]; // [esp+84h] [ebp-44h] BYREF
  unsigned int v49; // [esp+8Ch] [ebp-3Ch]
  int v50; // [esp+90h] [ebp-38h]
  unsigned int v51; // [esp+94h] [ebp-34h]
  unsigned __int8 *v52; // [esp+98h] [ebp-30h]
  int v53; // [esp+9Ch] [ebp-2Ch]
  unsigned int v54; // [esp+A0h] [ebp-28h]
  _BYTE v55[32]; // [esp+A4h] [ebp-24h] BYREF

  v2 = *a2;
  v39 = 1;
  v3 = (Table *)(*(int (__thiscall **)(int *))(v2 + 60))(a2);
  v48[1] = 0;
  v44 = v3;
  v49 = 0;
  v48[0] = 0;
  v4 = -Table::GetRecCount(v3);
  v5 = (struct Instance *)(*(int (__thiscall **)(int *))(*a2 + 56))(a2);
  Table::AddRecords(v3, v5, v4);
  Table::GetPhysicalIndexes(v3, (struct Collection *)v48, (struct Err *)&v39);
  v6 = v39;
  if ( (v39 & 8) != 0 )
  {
    if ( (v39 & 1) != 0 )
    {
      v7 = 0;
    }
    else
    {
      v8 = RealJetError(a1);
      v6 = v39;
      v7 = v8;
    }
    goto LABEL_93;
  }
  v9 = v49;
  v10 = 0;
  if ( v49 )
  {
    v11 = v48[0];
    do
    {
      v12 = (_DWORD *)v11[v10++];
      v13 = v12[11] + v12[10];
      *(_BYTE *)(v12[5] + 88) |= 1u;
      v12[11] -= v13;
      v14 = v12[13] + v12[12];
      *(_BYTE *)(v12[5] + 88) |= 1u;
      v12[13] -= v14;
    }
    while ( v10 < v9 );
    v3 = v44;
  }
  (*(void (__thiscall **)(int, int, _DWORD, int *))(*(_DWORD *)a2[9] + 8))(a2[9], 1, 0, &v39);
  v6 = v39;
  if ( (v39 & 8) == 0 )
  {
    do
    {
      v17 = (struct Instance *)(*(int (__thiscall **)(int *, int))(*a2 + 56))(a2, 1);
      Table::AddRecords(v3, v17, (int)v38);
      v38 = &v40;
      (*(void (__thiscall **)(int, int, int))(*(_DWORD *)a2[9] + 8))(a2[9], 1, 2);
      v6 = v39;
    }
    while ( (v39 & 8) == 0 );
    if ( (v39 & 1) != 0 )
    {
      v7 = 0;
      goto LABEL_93;
    }
    if ( v40 == -1603 )
    {
      if ( (v39 & 0xFFFFFFFE) != 0 )
      {
        if ( Block )
          operator delete[](Block);
        if ( v43 )
          operator delete[](v43);
      }
      v18 = 0;
      v6 = 1;
      v39 = 1;
      v44 = 0;
      if ( v49 )
      {
        while ( 1 )
        {
          v52 = v55;
          v45[0] = 1;
          v51 = 0;
          v53 = 0;
          v54 = 32;
          v19 = *((_DWORD *)v48[0] + (_DWORD)v18);
          v20 = *a2;
          v50 = v19;
          (*(void (__thiscall **)(int *, _DWORD, unsigned int *))(v20 + 8))(a2, ***(_DWORD ***)v19, v45);
          (*(void (__thiscall **)(int, int, _DWORD, unsigned int *))(*(_DWORD *)a2[9] + 8))(a2[9], 1, 0, v45);
          v21 = (QuickKey *)(*(int (__thiscall **)(int))(*(_DWORD *)a2[9] + 56))(a2[9]);
          if ( v54 >= *(_DWORD *)v21 )
          {
            v22 = v52;
          }
          else
          {
            if ( v53 == 1 )
            {
              if ( v52 )
                operator delete[](v52);
              v53 = 0;
              v52 = v55;
            }
            v54 = *(_DWORD *)v21;
            v22 = (unsigned __int8 *)operator new[](v54);
            v53 = 1;
            v52 = v22;
          }
          v51 = *(_DWORD *)v21;
          QuickKey::Copy(v21, v22, v51, (struct Err *)v45);
          v51 -= 4;
          v23 = v45[0];
          if ( (v45[0] & 8) == 0 )
            break;
LABEL_61:
          if ( (v23 & 1) != 0 || v45[1] != -1603 )
          {
            v6 = v39;
            if ( v23 > v39 )
            {
              Err::operator=(v45);
              v6 = v39;
              v23 = v45[0];
            }
            if ( v53 == 1 && v52 )
            {
              operator delete[](v52);
              v6 = v39;
              v23 = v45[0];
            }
            if ( (v23 & 0xFFFFFFFE) != 0 )
            {
              if ( v46 )
              {
                operator delete[](v46);
                v6 = v39;
              }
              if ( v47 )
              {
                operator delete[](v47);
LABEL_83:
                v6 = v39;
              }
            }
            goto LABEL_84;
          }
          *(_BYTE *)(*(_DWORD *)(v19 + 20) + 88) |= 1u;
          ++*(_DWORD *)(v19 + 52);
          if ( v53 == 1 && v52 )
            operator delete[](v52);
          if ( (v45[0] & 0xFFFFFFFE) != 0 )
          {
            if ( v46 )
              operator delete[](v46);
            if ( v47 )
              operator delete[](v47);
          }
          v18 = (Table *)((char *)v44 + 1);
          v44 = v18;
          if ( (unsigned int)v18 >= v49 )
            goto LABEL_83;
        }
        while ( 1 )
        {
          *(_BYTE *)(*(_DWORD *)(v19 + 20) + 88) |= 1u;
          ++*(_DWORD *)(v19 + 44);
          (*(void (__thiscall **)(int, int, int, unsigned int *))(*(_DWORD *)a2[9] + 8))(a2[9], 1, 2, v45);
          v23 = v45[0];
          if ( (v45[0] & 8) != 0 )
            goto LABEL_61;
          v24 = (QuickKey *)(*(int (__thiscall **)(int))(*(_DWORD *)a2[9] + 56))(a2[9]);
          v25 = v24;
          v26 = v52;
          if ( (v45[0] & 8) == 0 )
            break;
LABEL_54:
          if ( v54 < *(_DWORD *)v25 )
          {
            if ( v53 == 1 )
            {
              if ( v26 )
                operator delete[](v26);
              v53 = 0;
              v52 = v55;
            }
            v54 = *(_DWORD *)v25;
            v26 = (unsigned __int8 *)operator new[](v54);
            v53 = 1;
            v52 = v26;
          }
          v51 = *(_DWORD *)v25;
          QuickKey::Copy(v25, v26, v51, (struct Err *)v45);
          v51 -= 4;
          v23 = v45[0];
          v19 = v50;
          if ( (v45[0] & 8) != 0 )
            goto LABEL_61;
        }
        v27 = *(_DWORD *)v24;
        v28 = v52;
        v29 = *((_DWORD *)v24 + 1);
        if ( v51 < *(_DWORD *)v24 )
          v27 = v51;
        v31 = v27 < 4;
        v30 = v27 - 4;
        if ( v31 )
        {
LABEL_42:
          if ( v30 == -4 )
            goto LABEL_51;
        }
        else
        {
          while ( *(_DWORD *)v28 == *(_DWORD *)v29 )
          {
            v28 += 4;
            v29 += 4;
            v31 = v30 < 4;
            v30 -= 4;
            if ( v31 )
              goto LABEL_42;
          }
        }
        v31 = *v28 < *(_BYTE *)v29;
        if ( *v28 != *(_BYTE *)v29
          || v30 != -3
          && ((v32 = v28[1], v31 = v32 < *(_BYTE *)(v29 + 1), v32 != *(_BYTE *)(v29 + 1))
           || v30 != -2
           && ((v33 = v28[2], v31 = v33 < *(_BYTE *)(v29 + 2), v33 != *(_BYTE *)(v29 + 2))
            || v30 != -1 && (v34 = v28[3], v31 = v34 < *(_BYTE *)(v29 + 3), v34 != *(_BYTE *)(v29 + 3)))) )
        {
          v35 = v31 ? -1 : 1;
          goto LABEL_52;
        }
LABEL_51:
        v35 = 0;
LABEL_52:
        if ( v35 )
        {
          v36 = v50;
          *(_BYTE *)(*(_DWORD *)(v50 + 20) + 88) |= 1u;
          ++*(_DWORD *)(v36 + 52);
          v26 = v52;
        }
        goto LABEL_54;
      }
LABEL_84:
      if ( (v6 & 1) != 0 )
      {
        v7 = 0;
        goto LABEL_93;
      }
      if ( (v6 & 8) == 0 )
        goto LABEL_90;
    }
    v15 = v41;
    if ( !v41 )
      goto LABEL_90;
    v16 = a1;
    if ( !a1 )
      goto LABEL_90;
    goto LABEL_89;
  }
  if ( (v39 & 1) != 0 )
  {
    v7 = 0;
    goto LABEL_93;
  }
  v7 = v40;
  if ( v40 == -1603 )
  {
    v7 = 0;
    goto LABEL_93;
  }
  v15 = v41;
  if ( !v41 )
    goto LABEL_91;
  v16 = a1;
  if ( !a1 )
    goto LABEL_91;
LABEL_89:
  (*(void (__thiscall **)(_DWORD, void *, void *, void *, _DWORD, int, _DWORD, _DWORD, _DWORD))(pJetInfoBlock + 44))(
    *(_DWORD *)(pJetInfoBlock + 44),
    v16,
    Block,
    v43,
    0,
    v15,
    0,
    0,
    0);
  v6 = v39;
LABEL_90:
  v7 = v40;
LABEL_91:
  if ( (v6 & 1) != 0 )
    v7 = 0;
LABEL_93:
  if ( v48[0] )
  {
    operator delete[](v48[0]);
    v6 = v39;
  }
  if ( (v6 & 0xFFFFFFFE) != 0 )
  {
    if ( Block )
      operator delete[](Block);
    if ( v43 )
      operator delete[](v43);
  }
  return v7;
}

```

## disassembly

```asm
0x1002d6b0  mov     edi, edi
0x1002d6b2  push    ebp
0x1002d6b3  mov     ebp, esp
0x1002d6b5  and     esp, 0FFFFFFF8h
0x1002d6b8  sub     esp, 74h
0x1002d6bb  mov     eax, ___security_cookie
0x1002d6c0  xor     eax, esp
0x1002d6c2  mov     [esp+74h+var_4], eax
0x1002d6c6  push    ebx
0x1002d6c7  mov     ebx, [ebp+arg_4]
0x1002d6ca  push    esi; unsigned int
0x1002d6cb  push    edi; int
0x1002d6cc  mov     [esp+80h+var_74], ebx
0x1002d6d0  mov     eax, [ebx]
0x1002d6d2  mov     [esp+80h+var_70], 1
0x1002d6da  mov     esi, [eax+3Ch]
0x1002d6dd  mov     ecx, esi
0x1002d6df  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002d6e5  mov     ecx, ebx
0x1002d6e7  call    esi
0x1002d6e9  mov     ebx, eax
0x1002d6eb  mov     [esp+80h+var_40], 0
0x1002d6f3  mov     ecx, ebx; this
0x1002d6f5  mov     [esp+80h+var_5C], ebx
0x1002d6f9  mov     [esp+80h+var_3C], 0
0x1002d701  mov     [esp+80h+var_44], 0
0x1002d709  call    ?GetRecCount@Table@@QAEKXZ; Table::GetRecCount(void)
0x1002d70e  mov     ecx, [esp+80h+var_74]
0x1002d712  mov     edi, eax
0x1002d714  neg     edi
0x1002d716  mov     ecx, [ecx]
0x1002d718  mov     esi, [ecx+38h]
0x1002d71b  mov     ecx, esi
0x1002d71d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002d723  mov     ecx, [esp+80h+var_74]
0x1002d727  call    esi
0x1002d729  push    edi; int
0x1002d72a  push    eax; struct Instance *
0x1002d72b  mov     ecx, ebx; this
0x1002d72d  call    ?AddRecords@Table@@QAEJPAVInstance@@J@Z; Table::AddRecords(Instance *,long)
0x1002d732  lea     eax, [esp+80h+var_70]
0x1002d736  mov     ecx, ebx; this
0x1002d738  push    eax; struct Err *
0x1002d739  lea     eax, [esp+84h+var_44]
0x1002d73d  push    eax; struct Collection *
0x1002d73e  call    ?GetPhysicalIndexes@Table@@QBEXAAVCollection@@AAVErr@@@Z; Table::GetPhysicalIndexes(Collection &,Err &)
0x1002d743  mov     ecx, [esp+80h+var_70]
0x1002d747  test    cl, 8
0x1002d74a  jz      short loc_1002D76F
0x1002d74c  test    cl, 1
0x1002d74f  jz      short loc_1002D758
0x1002d751  xor     esi, esi
0x1002d753  jmp     loc_1002DC2E
0x1002d758  mov     ecx, [ebp+arg_0]; void *
0x1002d75b  lea     edx, [esp+80h+var_70]
0x1002d75f  call    RealJetError
0x1002d764  mov     ecx, [esp+80h+var_70]
0x1002d768  mov     esi, eax
0x1002d76a  jmp     loc_1002DC2E
0x1002d76f  mov     edi, [esp+80h+var_3C]
0x1002d773  xor     esi, esi
0x1002d775  test    edi, edi
0x1002d777  jz      short loc_1002D7AC
0x1002d779  mov     ebx, [esp+80h+var_44]
0x1002d77d  nop     dword ptr [eax]
0x1002d780  mov     edx, [ebx+esi*4]
0x1002d783  inc     esi
0x1002d784  mov     eax, [edx+14h]
0x1002d787  mov     ecx, [edx+28h]
0x1002d78a  add     ecx, [edx+2Ch]
0x1002d78d  or      byte ptr [eax+58h], 1
0x1002d791  sub     [edx+2Ch], ecx
0x1002d794  mov     eax, [edx+14h]
0x1002d797  mov     ecx, [edx+30h]
0x1002d79a  add     ecx, [edx+34h]
0x1002d79d  or      byte ptr [eax+58h], 1
0x1002d7a1  sub     [edx+34h], ecx
0x1002d7a4  cmp     esi, edi
0x1002d7a6  jb      short loc_1002D780
0x1002d7a8  mov     ebx, [esp+80h+var_5C]
0x1002d7ac  mov     eax, [esp+80h+var_74]
0x1002d7b0  mov     edi, [eax+24h]
0x1002d7b3  mov     eax, [edi]
0x1002d7b5  mov     esi, [eax+8]
0x1002d7b8  lea     eax, [esp+80h+var_70]
0x1002d7bc  push    eax
0x1002d7bd  push    0; unsigned int
0x1002d7bf  push    1; void *
0x1002d7c1  mov     ecx, esi
0x1002d7c3  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002d7c9  mov     ecx, edi
0x1002d7cb  call    esi
0x1002d7cd  mov     ecx, [esp+80h+var_70]
0x1002d7d1  test    cl, 8
0x1002d7d4  jz      short loc_1002D811
0x1002d7d6  test    cl, 1
0x1002d7d9  jz      short loc_1002D7E2
0x1002d7db  xor     esi, esi
0x1002d7dd  jmp     loc_1002DC2E
0x1002d7e2  mov     esi, [esp+80h+var_6C]
0x1002d7e6  cmp     esi, 0FFFFF9BDh
0x1002d7ec  jnz     short loc_1002D7F5
0x1002d7ee  xor     esi, esi
0x1002d7f0  jmp     loc_1002DC2E
0x1002d7f5  mov     edi, [esp+80h+var_68]
0x1002d7f9  test    edi, edi
0x1002d7fb  jz      loc_1002DC23
0x1002d801  mov     edx, [ebp+arg_0]
0x1002d804  test    edx, edx
0x1002d806  jz      loc_1002DC23
0x1002d80c  jmp     loc_1002DBF7
0x1002d811  mov     edi, [esp+80h+var_74]
0x1002d815  push    1; void *
0x1002d817  mov     eax, [edi]
0x1002d819  mov     esi, [eax+38h]
0x1002d81c  mov     ecx, esi
0x1002d81e  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002d824  mov     ecx, edi
0x1002d826  call    esi
0x1002d828  push    eax; struct Instance *
0x1002d829  mov     ecx, ebx; this
0x1002d82b  call    ?AddRecords@Table@@QAEJPAVInstance@@J@Z; Table::AddRecords(Instance *,long)
0x1002d830  mov     edi, [edi+24h]
0x1002d833  mov     eax, [edi]
0x1002d835  mov     esi, [eax+8]
0x1002d838  lea     eax, [esp+7Ch+var_6C]
0x1002d83c  push    eax; void *
0x1002d83d  push    2; unsigned int
0x1002d83f  push    1; void *
0x1002d841  mov     ecx, esi
0x1002d843  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002d849  mov     ecx, edi
0x1002d84b  call    esi
0x1002d84d  mov     ecx, [esp+80h+var_70]
0x1002d851  test    cl, 8
0x1002d854  jz      short loc_1002D811
0x1002d856  test    cl, 1
0x1002d859  jz      short loc_1002D862
0x1002d85b  xor     esi, esi
0x1002d85d  jmp     loc_1002DC2E
0x1002d862  cmp     [esp+80h+var_6C], 0FFFFF9BDh
0x1002d86a  jnz     loc_1002DBE8
0x1002d870  test    ecx, 0FFFFFFFEh
0x1002d876  jz      short loc_1002D89A
0x1002d878  mov     eax, [esp+80h+Block]
0x1002d87c  test    eax, eax
0x1002d87e  jz      short loc_1002D889
0x1002d880  push    eax; Block
0x1002d881  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002d886  add     esp, 4
0x1002d889  mov     eax, [esp+80h+var_60]
0x1002d88d  test    eax, eax
0x1002d88f  jz      short loc_1002D89A
0x1002d891  push    eax; Block
0x1002d892  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002d897  add     esp, 4
0x1002d89a  xor     eax, eax
0x1002d89c  mov     ecx, 1
0x1002d8a1  mov     [esp+80h+var_70], ecx
0x1002d8a5  mov     [esp+80h+var_5C], eax
0x1002d8a9  cmp     [esp+80h+var_3C], eax
0x1002d8ad  jbe     loc_1002DBDA
0x1002d8b3  mov     edi, [esp+80h+var_74]
0x1002d8b7  lea     ecx, [esp+80h+var_24]
0x1002d8bb  mov     [esp+80h+var_30], ecx
0x1002d8bf  mov     ecx, [esp+80h+var_44]
0x1002d8c3  mov     [esp+80h+var_58], 1
0x1002d8cb  mov     [esp+80h+var_34], 0
0x1002d8d3  mov     [esp+80h+var_2C], 0
0x1002d8db  mov     [esp+80h+var_28], 20h ; ' '
0x1002d8e3  mov     ebx, [ecx+eax*4]
0x1002d8e6  lea     ecx, [esp+80h+var_58]
0x1002d8ea  mov     eax, [edi]
0x1002d8ec  push    ecx; unsigned int
0x1002d8ed  mov     [esp+84h+var_38], ebx
0x1002d8f1  mov     esi, [eax+8]
0x1002d8f4  mov     ecx, esi
0x1002d8f6  mov     eax, [ebx]
0x1002d8f8  mov     eax, [eax]
0x1002d8fa  push    dword ptr [eax]; void *
0x1002d8fc  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002d902  mov     ecx, edi
0x1002d904  call    esi
0x1002d906  mov     edi, [edi+24h]
0x1002d909  mov     eax, [edi]
0x1002d90b  mov     esi, [eax+8]
0x1002d90e  lea     eax, [esp+80h+var_58]
0x1002d912  push    eax
0x1002d913  push    0; unsigned int
0x1002d915  push    1; void *
0x1002d917  mov     ecx, esi
0x1002d919  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002d91f  mov     ecx, edi
0x1002d921  call    esi
0x1002d923  mov     eax, [esp+80h+var_74]
0x1002d927  mov     edi, [eax+24h]
0x1002d92a  mov     eax, [edi]
0x1002d92c  mov     esi, [eax+38h]
0x1002d92f  mov     ecx, esi
0x1002d931  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002d937  mov     ecx, edi
0x1002d939  call    esi
0x1002d93b  mov     ecx, [esp+80h+var_28]
0x1002d93f  mov     esi, eax
0x1002d941  cmp     ecx, [esi]
0x1002d943  jnb     short loc_1002D98C
0x1002d945  cmp     [esp+80h+var_2C], 1
0x1002d94a  jnz     short loc_1002D96D
0x1002d94c  mov     ecx, [esp+80h+var_30]
0x1002d950  test    ecx, ecx
0x1002d952  jz      short loc_1002D95D
0x1002d954  push    ecx; Block
0x1002d955  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1002d95a  add     esp, 4
0x1002d95d  lea     eax, [esp+80h+var_24]
0x1002d961  mov     [esp+80h+var_2C], 0
0x1002d969  mov     [esp+80h+var_30], eax
0x1002d96d  mov     eax, [esi]
0x1002d96f  push    eax; unsigned int
0x1002d970  mov     [esp+84h+var_28], eax
0x1002d974  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1002d979  mov     ecx, eax
0x1002d97b  mov     [esp+84h+var_2C], 1
0x1002d983  add     esp, 4
0x1002d986  mov     [esp+80h+var_30], ecx
0x1002d98a  jmp     short loc_1002D990
0x1002d98c  mov     ecx, [esp+80h+var_30]
0x1002d990  mov     eax, [esi]
0x1002d992  lea     edx, [esp+80h+var_58]
0x1002d996  push    edx; struct Err *
0x1002d997  push    eax; unsigned int
0x1002d998  push    ecx; unsigned __int8 *
0x1002d999  mov     ecx, esi; this
0x1002d99b  mov     [esp+8Ch+var_34], eax
0x1002d99f  call    ?Copy@QuickKey@@QBEIPAEIAAVErr@@@Z; QuickKey::Copy(uchar *,uint,Err &)
0x1002d9a4  sub     [esp+80h+var_34], 4
0x1002d9a9  mov     eax, [esp+80h+var_58]
0x1002d9ad  test    al, 8
0x1002d9af  jnz     loc_1002DAFA
0x1002d9b5  mov     eax, [ebx+14h]
0x1002d9b8  or      byte ptr [eax+58h], 1
0x1002d9bc  mov     eax, [esp+80h+var_74]
0x1002d9c0  inc     dword ptr [ebx+2Ch]
0x1002d9c3  mov     edi, [eax+24h]
0x1002d9c6  mov     eax, [edi]
0x1002d9c8  mov     esi, [eax+8]
0x1002d9cb  lea     eax, [esp+80h+var_58]
0x1002d9cf  push    eax
0x1002d9d0  push    2; unsigned int
0x1002d9d2  push    1; void *
0x1002d9d4  mov     ecx, esi
0x1002d9d6  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002d9dc  mov     ecx, edi
0x1002d9de  call    esi
0x1002d9e0  mov     eax, [esp+80h+var_58]
0x1002d9e4  test    al, 8
0x1002d9e6  jnz     loc_1002DAFA
0x1002d9ec  mov     eax, [esp+80h+var_74]
0x1002d9f0  mov     edi, [eax+24h]
0x1002d9f3  mov     eax, [edi]
0x1002d9f5  mov     esi, [eax+38h]
0x1002d9f8  mov     ecx, esi
0x1002d9fa  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1002da00  mov     ecx, edi
0x1002da02  call    esi
0x1002da04  test    byte ptr [esp+80h+var_58], 8
0x1002da09  mov     ebx, eax
0x1002da0b  mov     edi, [esp+80h+var_30]
0x1002da0f  jnz     short loc_1002DA88
0x1002da11  mov     ecx, [ebx]
0x1002da13  mov     edx, edi
0x1002da15  cmp     [esp+80h+var_34], ecx
0x1002da19  mov     esi, [ebx+4]
0x1002da1c  cmovb   ecx, [esp+80h+var_34]
0x1002da21  sub     ecx, 4
0x1002da24  jb      short loc_1002DA37
0x1002da26  mov     eax, [edx]
0x1002da28  cmp     eax, [esi]
0x1002da2a  jnz     short loc_1002DA3C
0x1002da2c  add     edx, 4
0x1002da2f  add     esi, 4
0x1002da32  sub     ecx, 4
0x1002da35  jnb     short loc_1002DA26
0x1002da37  cmp     ecx, 0FFFFFFFCh
0x1002da3a  jz      short loc_1002DA70
0x1002da3c  mov     al, [edx]
0x1002da3e  cmp     al, [esi]
0x1002da40  jnz     short loc_1002DA69
0x1002da42  cmp     ecx, 0FFFFFFFDh
0x1002da45  jz      short loc_1002DA70
0x1002da47  mov     al, [edx+1]
0x1002da4a  cmp     al, [esi+1]
0x1002da4d  jnz     short loc_1002DA69
0x1002da4f  cmp     ecx, 0FFFFFFFEh
0x1002da52  jz      short loc_1002DA70
0x1002da54  mov     al, [edx+2]
0x1002da57  cmp     al, [esi+2]
0x1002da5a  jnz     short loc_1002DA69
0x1002da5c  cmp     ecx, 0FFFFFFFFh
0x1002da5f  jz      short loc_1002DA70
  ... truncated ...
```
