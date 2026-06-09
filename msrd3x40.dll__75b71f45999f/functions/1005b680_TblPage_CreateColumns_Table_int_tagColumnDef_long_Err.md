# TblPage::CreateColumns(Table *,int,tagColumnDef *,long,Err &)

- ea: `0x1005b680`
- end: `0x1005bda8`
- name: `?CreateColumns@TblPage@@AAEJPAVTable@@HPAUtagColumnDef@@JAAVErr@@@Z`
- size: `1832`
- prototype: `int __thiscall(TblPage *this, struct Table *, int, struct tagColumnDef *, int, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1005ab70`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10013730`
- `0x10025ee0`
- `0x10043450`
- `0x1005b680`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005f064`
- `0x1005f07c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1005b9af`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1005b9c6`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1005b9dd`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1005b9f4`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1005ba0b`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1005b9af`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1005b9c6`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1005b9dd`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1005b9f4`
- `api-ms-win-crt-private-l1-1-0!_o__strnicmp` at `0x1005ba0b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1005bad2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1005bad2`

## pseudocode

```c
int __thiscall TblPage::CreateColumns(
        TblPage *this,
        struct Table *a2,
        int a3,
        struct tagColumnDef *a4,
        int a5,
        void **a6)
{
  int v6; // ecx
  int v7; // ebx
  struct Table *v8; // esi
  struct tagColumnDef *v9; // edx
  void **v10; // edi
  __int16 v11; // ax
  __int16 v12; // cx
  struct tagColumnDef *v13; // ecx
  int v14; // edx
  char *v15; // edx
  unsigned __int8 v16; // al
  int v17; // ecx
  int v18; // ecx
  unsigned __int8 *v19; // ebx
  _WORD *v20; // ecx
  unsigned __int16 *v21; // eax
  unsigned __int16 *v22; // ebx
  unsigned __int16 v23; // ax
  unsigned __int16 v24; // si
  int v25; // edi
  wchar_t v26; // si
  struct Column *v27; // eax
  struct Column *v28; // ebx
  UINT v29; // edx
  int v30; // eax
  size_t v31; // ecx
  int i; // edi
  unsigned int v34; // eax
  Err *v35; // ecx
  void (__thiscall ***v36)(_DWORD, int); // eax
  unsigned int v37; // [esp+0h] [ebp-F8h]
  struct Err *v38; // [esp+4h] [ebp-F4h]
  struct Err *v39; // [esp+38h] [ebp-C0h]
  Err *v40; // [esp+3Ch] [ebp-BCh]
  unsigned __int8 *v42; // [esp+44h] [ebp-B4h]
  __int16 v43; // [esp+4Ch] [ebp-ACh]
  int v44; // [esp+4Ch] [ebp-ACh]
  _WORD *v45; // [esp+50h] [ebp-A8h]
  struct ColumnVtbl *v46; // [esp+50h] [ebp-A8h]
  const wchar_t *v47; // [esp+58h] [ebp-A0h]
  unsigned int v48; // [esp+58h] [ebp-A0h]
  int v49; // [esp+58h] [ebp-A0h]
  WCHAR WideCharStr[68]; // [esp+60h] [ebp-98h] BYREF
  int v51; // [esp+F4h] [ebp-4h]

  v6 = *((_DWORD *)this + 1);
  v7 = 0;
  v8 = a2;
  v9 = a4;
  v10 = a6;
  v11 = *(_WORD *)(v6 + 17);
  if ( v11 >= 0 )
  {
    v12 = *(_WORD *)(v6 + 13);
    v43 = v12;
    if ( v11 <= v12 && (unsigned __int16)v12 < 0x100u )
    {
      v42 = (unsigned __int8 *)a4 + 18 * v11;
      v13 = (struct tagColumnDef *)v42;
      if ( v11 > 0 )
      {
        do
        {
          v14 = *(unsigned __int8 *)v13;
          if ( (unsigned int)(v14 - 1) > 0x3F )
          {
LABEL_30:
            Err::SetError(v10, -1206, v13);
            v9 = a4;
            goto LABEL_85;
          }
          v13 = (struct tagColumnDef *)((char *)v13 + v14 + 1);
          ++v7;
          v10 = a6;
          v8 = a2;
        }
        while ( v7 < *(__int16 *)(*((_DWORD *)this + 1) + 17) );
        v7 = 0;
        while ( 1 )
        {
          v13 = a4;
          v15 = (char *)a4 + 18 * v7;
          v16 = *v15;
          if ( !*v15 || v16 >= 0x10u )
            break;
          if ( (v15[13] & 1) != 0 && v16 != 1 )
          {
            v13 = (struct tagColumnDef *)(*((unsigned __int16 *)v15 + 7) + *((unsigned __int16 *)v15 + 8));
            if ( (unsigned int)v13 > 0x7D3 )
              goto LABEL_30;
          }
          if ( *(_WORD *)(v15 + 3) > 0xFFu || *(_WORD *)(v15 + 1) > 0xFEu )
            goto LABEL_30;
          ++v7;
          v8 = a2;
          if ( v7 >= *(__int16 *)(*((_DWORD *)this + 1) + 17) )
            goto LABEL_16;
        }
        if ( (int)*a6 >= 8 )
        {
          v9 = a4;
        }
        else
        {
          if ( ((unsigned int)*a6 & 0xFFFFFFFE) != 0 )
          {
            if ( a6[3] )
              operator delete[](a6[3]);
            if ( a6[4] )
              operator delete[](a6[4]);
          }
          v9 = a4;
          *a6 = (void *)8;
          a6[1] = (void *)-1206;
          a6[2] = 0;
          a6[3] = 0;
          a6[4] = 0;
        }
LABEL_85:
        for ( i = 0; i < v7; ++i )
        {
          v34 = *(__int16 *)((char *)v9 + 18 * i + 1);
          v49 = v34;
          if ( v34 > 0xFE )
            break;
          v35 = (struct Table *)((char *)v8 + 136);
          v40 = (struct Table *)((char *)v8 + 136);
          if ( *((struct Table **)v8 + v34 + 94) != (struct Table *)((char *)v8 + 136) )
          {
            _mm_lfence();
            v36 = (void (__thiscall ***)(_DWORD, int))*((_DWORD *)v8 + v34 + 94);
            if ( v36 )
            {
              (**v36)(v36, 1);
              v8 = a2;
              v35 = v40;
              v9 = a4;
            }
            *((_DWORD *)v8 + v49 + 94) = v35;
          }
        }
        return 0;
      }
LABEL_16:
      v17 = 0;
      if ( v43 > 0 )
      {
        do
          *((_DWORD *)v8 + v17++ + 94) = (char *)v8 + 136;
        while ( v17 < *(__int16 *)(*((_DWORD *)this + 1) + 13) );
      }
      v18 = 0;
      v19 = v42;
      v44 = 0;
      if ( *(__int16 *)(*((_DWORD *)this + 1) + 17) <= 0 )
        return v19 - (unsigned __int8 *)a4;
      while ( 1 )
      {
        v20 = (_WORD *)((char *)a4 + 18 * v18);
        v45 = v20;
        if ( *(_DWORD *)(*((_DWORD *)v8 + 9) + 104) == 3 && *v19 == 5 )
        {
          if ( *((_DWORD *)v8 + 16) == -1 )
          {
            v51 = -1;
            goto LABEL_48;
          }
          v21 = *(unsigned __int16 **)v8;
          v51 = -1;
          if ( v21 )
          {
            v51 = -1;
            v22 = v21;
            v47 = L"MSysSchChange";
            do
            {
              v23 = *v22++;
              v24 = v23 + 32;
              if ( (unsigned __int16)(v23 - 65) > 0x19u )
                v24 = v23;
              v25 = v24;
              v26 = *v47 + 32;
              if ( (unsigned __int16)(*v47 - 65) > 0x19u )
                v26 = *v47;
              ++v47;
            }
            while ( (_WORD)v25 && (_WORD)v25 == v26 );
            if ( v25 == v26 )
            {
              if ( !__strnicmp((const char *)v42 + 1, "Memo1", 5u) || !__strnicmp((const char *)v42 + 1, "Memo2", *v42) )
              {
                v20 = v45;
                *(_BYTE *)v45 = 11;
                goto LABEL_48;
              }
              if ( !__strnicmp((const char *)v42 + 1, "Text1", *v42)
                || !__strnicmp((const char *)v42 + 1, "Text2", *v42)
                || !__strnicmp((const char *)v42 + 1, "Text3", *v42) )
              {
                v20 = v45;
                *(_BYTE *)v45 = 9;
                goto LABEL_48;
              }
            }
            v20 = v45;
          }
        }
LABEL_48:
        v27 = Column::NewColumn(
                v20[8],
                *(_WORD *)((char *)v20 + 7),
                *(unsigned __int16 *)((char *)v20 + 9),
                *(unsigned __int16 *)((char *)v20 + 11),
                0,
                (Err *)a6,
                v37,
                v38);
        v28 = v27;
        if ( (*(_BYTE *)a6 & 8) != 0 )
          goto LABEL_60;
        ((void (__thiscall *)(struct Column *, void *))v27->lpVtbl[1].AddRef)(v27, v45);
        v8 = a2;
        v48 = *(__int16 *)((char *)v45 + 1);
        v29 = *(unsigned __int16 *)(*(_DWORD *)(*((_DWORD *)a2 + 9) + 60) + 100);
        v28[11].lpVtbl = (struct ColumnVtbl *)v29;
        if ( v42 == (unsigned __int8 *)-1 || !*v42 )
        {
          v30 = 0;
          WideCharStr[0] = 0;
        }
        else
        {
          v30 = MultiByteToWideChar(v29, 0, (LPCCH)v42 + 1, *v42, WideCharStr, 65);
          v8 = a2;
          if ( !v30 )
          {
            if ( (int)*a6 < 8 )
            {
              if ( ((unsigned int)*a6 & 0xFFFFFFFE) != 0 )
              {
                if ( a6[3] )
                  operator delete[](a6[3]);
                if ( a6[4] )
                  operator delete[](a6[4]);
              }
              *a6 = (void *)8;
              a6[1] = (void *)-1002;
              a6[2] = 0;
              a6[3] = 0;
              a6[4] = 0;
            }
            ((void (__thiscall *)(struct Column *, int))v28->lpVtbl->QueryInterface)(v28, 1);
            goto LABEL_60;
          }
        }
        v31 = 2 * v30;
        v46 = (struct ColumnVtbl *)(2 * v30);
        if ( v48 > 0xFE || (v39 = (struct Err *)(v31 >> 1), v31 >> 1 > 0x40) )
        {
          ((void (__thiscall *)(struct Column *, int))v28->lpVtbl->QueryInterface)(v28, 1);
          if ( (int)*a6 < 8 )
          {
            if ( ((unsigned int)*a6 & 0xFFFFFFFE) != 0 )
            {
              if ( a6[3] )
                operator delete[](a6[3]);
              if ( a6[4] )
                operator delete[](a6[4]);
            }
            v7 = v44;
            v8 = a2;
            v9 = a4;
            *a6 = (void *)8;
            a6[1] = (void *)-1206;
            a6[2] = 0;
            a6[3] = 0;
            a6[4] = 0;
            goto LABEL_85;
          }
LABEL_60:
          v7 = v44;
          v8 = a2;
          v9 = a4;
          goto LABEL_85;
        }
        memcpy(v28[1].lpVtbl, WideCharStr, v31);
        *((_WORD *)&v28[1].lpVtbl->QueryInterface + (_DWORD)v39) = 0;
        v28[2].lpVtbl = v46;
        if ( ((int)v28[12].lpVtbl & 2) != 0 )
          *((_DWORD *)v8 + 21) = v48;
        if ( ((int)v28[12].lpVtbl & 4) != 0 )
          *((_DWORD *)v8 + 20) = v48;
        PresOrderList::Insert(
          (struct Table *)((char *)v8 + 360),
          (const unsigned __int16 *)v28[1].lpVtbl,
          v48,
          (int)v28[6].lpVtbl,
          v39);
        v28[14].lpVtbl = 0;
        v18 = v44 + 1;
        v28[15].lpVtbl = *(struct ColumnVtbl **)((char *)v8 + 4 * v48 + 376);
        *((_DWORD *)v8 + v48 + 94) = v28;
        v44 = v18;
        v19 = &v42[*v42 + 1];
        v42 = v19;
        if ( v18 >= *(__int16 *)(*((_DWORD *)this + 1) + 17) )
          return v19 - (unsigned __int8 *)a4;
      }
    }
  }
  if ( (int)*a6 >= 8 )
    goto LABEL_85;
  if ( ((unsigned int)*a6 & 0xFFFFFFFE) != 0 )
  {
    if ( a6[3] )
      operator delete[](a6[3]);
    if ( a6[4] )
      operator delete[](a6[4]);
  }
  *a6 = (void *)8;
  a6[1] = (void *)-1206;
  a6[2] = 0;
  a6[3] = 0;
  a6[4] = 0;
  return 0;
}

```

## disassembly

```asm
0x1005b680  mov     edi, edi
0x1005b682  push    ebp
0x1005b683  mov     ebp, esp
0x1005b685  push    0FFFFFFFFh
0x1005b687  push    offset ?CreateColumns@TblPage@@AAEJPAVTable@@HPAUtagColumnDef@@JAAVErr@@@Z_SEH
0x1005b68c  mov     eax, large fs:0
0x1005b692  push    eax
0x1005b693  sub     esp, 0DCh
0x1005b699  mov     eax, ___security_cookie
0x1005b69e  xor     eax, ebp
0x1005b6a0  mov     [ebp+var_10], eax
0x1005b6a3  push    ebx
0x1005b6a4  push    esi
0x1005b6a5  push    edi; struct Err *
0x1005b6a6  push    eax; unsigned int
0x1005b6a7  lea     eax, [ebp+var_C]
0x1005b6aa  mov     large fs:0, eax
0x1005b6b0  mov     eax, ecx
0x1005b6b2  mov     [ebp+var_B8], eax
0x1005b6b8  mov     ecx, [eax+4]
0x1005b6bb  xor     ebx, ebx
0x1005b6bd  mov     esi, [ebp+arg_0]
0x1005b6c0  mov     edx, [ebp+arg_8]
0x1005b6c3  mov     edi, [ebp+arg_10]
0x1005b6c6  movzx   eax, word ptr [ecx+11h]
0x1005b6ca  mov     [ebp+var_A4], esi
0x1005b6d0  mov     [ebp+var_9C], edx
0x1005b6d6  mov     [ebp+var_BC], edi
0x1005b6dc  test    ax, ax
0x1005b6df  js      loc_1005BCBD
0x1005b6e5  movzx   ecx, word ptr [ecx+0Dh]
0x1005b6e9  mov     [ebp+var_AC], ecx
0x1005b6ef  cmp     ax, cx
0x1005b6f2  jg      loc_1005BCBD
0x1005b6f8  test    cx, cx
0x1005b6fb  js      loc_1005BCBD
0x1005b701  mov     [ebp+var_A0], 0FFh
0x1005b70b  cmp     cx, word ptr [ebp+var_A0]
0x1005b712  jg      loc_1005BCBD
0x1005b718  mov     ecx, [ebp+var_9C]
0x1005b71e  movsx   edx, ax
0x1005b721  lea     eax, [edx+edx*8]
0x1005b724  lea     eax, [ecx+eax*2]
0x1005b727  mov     [ebp+var_B4], eax
0x1005b72d  mov     ecx, eax
0x1005b72f  test    edx, edx
0x1005b731  jle     loc_1005B7E8
0x1005b737  movzx   edx, byte ptr [ecx]
0x1005b73a  lea     eax, [edx-1]
0x1005b73d  cmp     eax, 3Fh ; '?'
0x1005b740  ja      loc_1005B8EE
0x1005b746  mov     edi, [ebp+var_B8]
0x1005b74c  inc     edx
0x1005b74d  add     ecx, edx
0x1005b74f  inc     ebx
0x1005b750  mov     esi, [edi+4]
0x1005b753  mov     edi, [ebp+var_BC]
0x1005b759  movzx   edx, word ptr [esi+11h]
0x1005b75d  mov     esi, [ebp+var_A4]
0x1005b763  movsx   eax, dx
0x1005b766  cmp     ebx, eax
0x1005b768  jl      short loc_1005B737
0x1005b76a  xor     ebx, ebx
0x1005b76c  nop     dword ptr [eax+00h]
0x1005b770  mov     ecx, [ebp+var_9C]
0x1005b776  lea     eax, [ebx+ebx*8]
0x1005b779  lea     edx, [ecx+eax*2]
0x1005b77c  mov     al, [edx]
0x1005b77e  test    al, al
0x1005b780  jz      loc_1005B88F
0x1005b786  cmp     al, 10h
0x1005b788  jnb     loc_1005B88F
0x1005b78e  test    byte ptr [edx+0Dh], 1
0x1005b792  jz      short loc_1005B7AE
0x1005b794  cmp     al, 1
0x1005b796  jz      short loc_1005B7AE
0x1005b798  movzx   ecx, word ptr [edx+10h]
0x1005b79c  movzx   eax, word ptr [edx+0Eh]
0x1005b7a0  add     ecx, eax
0x1005b7a2  cmp     ecx, 7D3h
0x1005b7a8  ja      loc_1005B8EE
0x1005b7ae  mov     eax, [ebp+var_A0]
0x1005b7b4  cmp     [edx+3], ax
0x1005b7b8  ja      loc_1005B8EE
0x1005b7be  mov     eax, 0FEh
0x1005b7c3  cmp     [edx+1], ax
0x1005b7c7  ja      loc_1005B8EE
0x1005b7cd  mov     esi, [ebp+var_B8]
0x1005b7d3  inc     ebx
0x1005b7d4  mov     edx, [esi+4]
0x1005b7d7  mov     esi, [ebp+var_A4]
0x1005b7dd  movzx   ecx, word ptr [edx+11h]
0x1005b7e1  movsx   eax, cx
0x1005b7e4  cmp     ebx, eax
0x1005b7e6  jl      short loc_1005B770
0x1005b7e8  xor     eax, eax
0x1005b7ea  xor     ecx, ecx
0x1005b7ec  cmp     ax, word ptr [ebp+var_AC]
0x1005b7f3  jge     short loc_1005B819
0x1005b7f5  lea     edx, [esi+88h]
0x1005b7fb  nop     dword ptr [eax+eax+00h]
0x1005b800  mov     eax, [ebp+var_B8]
0x1005b806  mov     [esi+ecx*4+178h], edx
0x1005b80d  inc     ecx
0x1005b80e  mov     eax, [eax+4]
0x1005b811  movsx   eax, word ptr [eax+0Dh]
0x1005b815  cmp     ecx, eax
0x1005b817  jl      short loc_1005B800
0x1005b819  mov     eax, [ebp+var_B8]
0x1005b81f  xor     ecx, ecx
0x1005b821  mov     ebx, [ebp+var_B4]
0x1005b827  xor     edx, edx
0x1005b829  mov     [ebp+var_AC], ecx
0x1005b82f  mov     eax, [eax+4]
0x1005b832  cmp     dx, [eax+11h]
0x1005b836  jge     loc_1005BC36
0x1005b83c  nop     dword ptr [eax+00h]
0x1005b840  lea     eax, [ecx+ecx*8]
0x1005b843  mov     ecx, [ebp+var_9C]
0x1005b849  lea     ecx, [ecx+eax*2]
0x1005b84c  mov     eax, [esi+24h]
0x1005b84f  mov     [ebp+var_A8], ecx
0x1005b855  cmp     dword ptr [eax+68h], 3
0x1005b859  jnz     loc_1005BA34
0x1005b85f  mov     al, [ebx]
0x1005b861  mov     [ebp+var_AD], al
0x1005b867  cmp     al, 5
0x1005b869  jnz     loc_1005BA34
0x1005b86f  mov     [ebp+var_D4], 1
0x1005b879  cmp     dword ptr [esi+40h], 0FFFFFFFFh
0x1005b87d  jnz     loc_1005B906
0x1005b883  mov     [ebp+var_4], 0FFFFFFFFh
0x1005b88a  jmp     loc_1005BA34
0x1005b88f  mov     eax, [edi]
0x1005b891  cmp     eax, 8
0x1005b894  jge     loc_1005BD06
0x1005b89a  test    eax, 0FFFFFFFEh
0x1005b89f  jz      short loc_1005B8C1
0x1005b8a1  mov     eax, [edi+0Ch]
0x1005b8a4  test    eax, eax
0x1005b8a6  jz      short loc_1005B8B1
0x1005b8a8  push    eax; Block
0x1005b8a9  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005b8ae  add     esp, 4
0x1005b8b1  mov     eax, [edi+10h]
0x1005b8b4  test    eax, eax
0x1005b8b6  jz      short loc_1005B8C1
0x1005b8b8  push    eax; Block
0x1005b8b9  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x1005b8be  add     esp, 4
0x1005b8c1  mov     edx, [ebp+var_9C]
0x1005b8c7  mov     dword ptr [edi], 8
0x1005b8cd  mov     dword ptr [edi+4], 0FFFFFB4Ah
0x1005b8d4  mov     dword ptr [edi+8], 0
0x1005b8db  mov     dword ptr [edi+0Ch], 0
0x1005b8e2  mov     dword ptr [edi+10h], 0
0x1005b8e9  jmp     loc_1005BD08
0x1005b8ee  push    ecx
0x1005b8ef  push    0FFFFFB4Ah
0x1005b8f4  mov     ecx, edi
0x1005b8f6  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x1005b8fb  mov     edx, [ebp+var_9C]
0x1005b901  jmp     loc_1005BD08
0x1005b906  mov     eax, [esi]
0x1005b908  mov     [ebp+var_C0], eax
0x1005b90e  mov     [ebp+var_4], 0FFFFFFFFh
0x1005b915  test    eax, eax
0x1005b917  jz      loc_1005BA34
0x1005b91d  mov     [ebp+var_E8], 1
0x1005b927  mov     [ebp+var_4], 0FFFFFFFFh
0x1005b92e  mov     ebx, eax
0x1005b930  mov     [ebp+var_A0], offset aMsysschchange; "MSysSchChange"
0x1005b93a  nop     word ptr [eax+eax+00h]
0x1005b940  movzx   eax, word ptr [ebx]
0x1005b943  lea     ebx, [ebx+2]
0x1005b946  mov     ecx, eax
0x1005b948  lea     edx, [eax-41h]
0x1005b94b  lea     eax, [ecx+20h]
0x1005b94e  cmp     dx, 19h
0x1005b952  movzx   esi, ax
0x1005b955  mov     eax, ecx
0x1005b957  cmova   esi, eax
0x1005b95a  mov     eax, [ebp+var_A0]
0x1005b960  movzx   edi, si
0x1005b963  movzx   eax, word ptr [eax]
0x1005b966  mov     ecx, eax
0x1005b968  lea     edx, [eax-41h]
0x1005b96b  lea     eax, [ecx+20h]
0x1005b96e  cmp     dx, 19h
0x1005b972  movzx   esi, ax
0x1005b975  mov     eax, ecx
0x1005b977  cmova   esi, eax
0x1005b97a  add     [ebp+var_A0], 2
0x1005b981  movzx   eax, si
0x1005b984  test    di, di
0x1005b987  jz      short loc_1005B98E
0x1005b989  cmp     di, ax
0x1005b98c  jz      short loc_1005B940
0x1005b98e  mov     ebx, [ebp+var_B4]
0x1005b994  mov     ecx, edi
0x1005b996  sub     ecx, eax
0x1005b998  jnz     loc_1005BA2E
0x1005b99e  movzx   eax, [ebp+var_AD]
0x1005b9a5  lea     esi, [ebx+1]
0x1005b9a8  push    eax; MaxCount
0x1005b9a9  push    offset aMemo1; "Memo1"
0x1005b9ae  push    esi; String1
0x1005b9af  call    ds:__imp___strnicmp
0x1005b9b5  add     esp, 0Ch
0x1005b9b8  test    eax, eax
0x1005b9ba  jz      short loc_1005BA23
0x1005b9bc  movzx   eax, byte ptr [ebx]
0x1005b9bf  push    eax; MaxCount
0x1005b9c0  push    offset aMemo2; "Memo2"
0x1005b9c5  push    esi; String1
0x1005b9c6  call    ds:__imp___strnicmp
0x1005b9cc  add     esp, 0Ch
0x1005b9cf  test    eax, eax
0x1005b9d1  jz      short loc_1005BA23
0x1005b9d3  movzx   eax, byte ptr [ebx]
0x1005b9d6  push    eax; MaxCount
0x1005b9d7  push    offset aText1; "Text1"
0x1005b9dc  push    esi; String1
0x1005b9dd  call    ds:__imp___strnicmp
0x1005b9e3  add     esp, 0Ch
0x1005b9e6  test    eax, eax
0x1005b9e8  jz      short loc_1005BA18
0x1005b9ea  movzx   eax, byte ptr [ebx]
0x1005b9ed  push    eax; MaxCount
0x1005b9ee  push    offset aText2; "Text2"
0x1005b9f3  push    esi; String1
0x1005b9f4  call    ds:__imp___strnicmp
0x1005b9fa  add     esp, 0Ch
0x1005b9fd  test    eax, eax
0x1005b9ff  jz      short loc_1005BA18
0x1005ba01  movzx   eax, byte ptr [ebx]
0x1005ba04  push    eax; MaxCount
0x1005ba05  push    offset aText3; "Text3"
0x1005ba0a  push    esi; String1
0x1005ba0b  call    ds:__imp___strnicmp
0x1005ba11  add     esp, 0Ch
0x1005ba14  test    eax, eax
0x1005ba16  jnz     short loc_1005BA2E
0x1005ba18  mov     ecx, [ebp+var_A8]
0x1005ba1e  mov     byte ptr [ecx], 9
0x1005ba21  jmp     short loc_1005BA34
0x1005ba23  mov     ecx, [ebp+var_A8]
0x1005ba29  mov     byte ptr [ecx], 0Bh
0x1005ba2c  jmp     short loc_1005BA34
0x1005ba2e  mov     ecx, [ebp+var_A8]
0x1005ba34  push    [ebp+var_BC]; Err *
0x1005ba3a  movzx   ebx, word ptr [ecx+0Bh]
0x1005ba3e  movzx   edi, word ptr [ecx+9]
0x1005ba42  movzx   esi, word ptr [ecx+7]
0x1005ba46  mov     dl, [ecx+0Dh]
0x1005ba49  movzx   eax, word ptr [ecx+10h]
0x1005ba4d  not     dl
0x1005ba4f  mov     cl, [ecx]
0x1005ba51  and     dl, 1
0x1005ba54  push    0; unsigned int
0x1005ba56  push    ebx; unsigned int
0x1005ba57  push    edi; unsigned int
0x1005ba58  push    esi; unsigned __int8
0x1005ba59  push    eax; unsigned __int8
0x1005ba5a  call    ?NewColumn@Column@@SGPAV1@EEIIIIKAAVErr@@@Z; Column::NewColumn(uchar,uchar,uint,uint,uint,uint,ulong,Err &)
0x1005ba5f  mov     edi, [ebp+var_BC]
0x1005ba65  mov     ebx, eax
0x1005ba67  test    byte ptr [edi], 8
0x1005ba6a  jnz     loc_1005BB48
0x1005ba70  mov     eax, [ebx]
0x1005ba72  push    [ebp+var_A8]; void *
0x1005ba78  mov     esi, [eax+44h]
0x1005ba7b  mov     ecx, esi
0x1005ba7d  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1005ba83  mov     ecx, ebx
0x1005ba85  call    esi
0x1005ba87  mov     ecx, [ebp+var_A8]
0x1005ba8d  mov     esi, [ebp+var_A4]
0x1005ba93  movsx   eax, word ptr [ecx+1]
0x1005ba97  mov     [ebp+var_A0], eax
0x1005ba9d  mov     eax, [esi+24h]
0x1005baa0  mov     eax, [eax+3Ch]
0x1005baa3  movzx   edx, word ptr [eax+64h]
0x1005baa7  mov     eax, [ebp+var_B4]
0x1005baad  mov     [ebx+2Ch], edx
0x1005bab0  movzx   ecx, byte ptr [eax]
0x1005bab3  add     eax, 1
0x1005bab6  jz      loc_1005BB5F
0x1005babc  test    ecx, ecx
0x1005babe  jz      loc_1005BB5F
0x1005bac4  push    41h ; 'A'; cchWideChar
0x1005bac6  lea     esi, [ebp+WideCharStr]
0x1005bacc  push    esi; lpWideCharStr
0x1005bacd  push    ecx; cbMultiByte
0x1005bace  push    eax; lpMultiByteStr
0x1005bacf  push    0; dwFlags
0x1005bad1  push    edx; CodePage
0x1005bad2  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x1005bad8  mov     esi, [ebp+var_A4]
0x1005bade  test    eax, eax
  ... truncated ...
```
