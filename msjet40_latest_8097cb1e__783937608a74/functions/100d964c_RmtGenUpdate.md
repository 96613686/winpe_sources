# RmtGenUpdate

- ea: `0x100d964c`
- end: `0x100d9914`
- name: `RmtGenUpdate`
- size: `712`
- prototype: `int __stdcall(LPCVOID lpAddress, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x100d99fd`

## callees

- `0x100af0fe`
- `0x100afc15`
- `0x100b0db5`
- `0x100b0e93`
- `0x100b767a`
- `0x100d9565`
- `0x100d964c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100d96b8`
- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100d96b8`

## string_xrefs

- `0x100d96c3`: `UPDATE`

## pseudocode

```c
unsigned int __fastcall RmtGenUpdate(int a1, int a2, _DWORD *lpAddress, int a4, _DWORD *a5)
{
  _DWORD *v6; // edi
  int v7; // edx
  int v8; // eax
  _WORD *v9; // ecx
  int *v11; // edx
  unsigned int v12; // ebx
  unsigned int result; // eax
  int v14; // ecx
  _WORD *v15; // ecx
  void *v17; // eax
  int v18; // ebx
  int *v19; // ecx
  _DWORD *v20; // edi
  int v21; // edx
  unsigned int v22; // [esp+Ch] [ebp-1Ch]
  int v23; // [esp+10h] [ebp-18h]
  int v25; // [esp+18h] [ebp-10h]
  int v26; // [esp+1Ch] [ebp-Ch]
  _DWORD *v28; // [esp+24h] [ebp-4h]

  v23 = *(_DWORD *)(a2 + 300);
  v26 = *(_DWORD *)(a4 + 16);
  v6 = (_DWORD *)(a4 + 1040);
  v7 = a5[13] - 1;
  if ( (lpAddress[7] & 0x8000) == 0 )
    v7 = a5[13];
  v25 = v7;
  v28 = (_DWORD *)(a4 + 1056);
  *(_DWORD *)(a4 + 1056) = 0;
  v8 = ErrCallocPvHsegREAL(lpAddress, 2, 1);
  if ( v8 < 0 )
    goto LABEL_4;
  PPRmtStrcat2REAL(L"UPDATE", L" ");
  PPAddOwnerTable(*(wchar_t **)(a2 + 272), (void *)(v23 + 48));
  PPRmtStrcat2REAL(L" ", 0);
  PPRmtStrcat2REAL(L"SET", L" ");
  v9 = (_WORD *)*v6;
  while ( *v9++ )
    ;
  *(_WORD *)(a4 + 1044) = ((int)v9 - *v6 - 2) >> 1;
  v11 = &dword_1000EF34;
  v12 = *(_DWORD *)(a2 + 4);
  result = v12 + 52 * *(_DWORD *)(a2 + 8);
  v22 = result;
  if ( v12 >= result )
    goto LABEL_33;
  do
  {
    if ( (*(_WORD *)(v12 + 48) & 0x100) != 0 )
    {
      if ( (*(_WORD *)(v12 + 48) & 0x200) != 0 )
      {
        PPRmtStrcat2REAL(v11, 0);
        PPRmtStrcatCch2REAL(
          lpAddress,
          (void *)(*(_DWORD *)(a4 + 8) + 2 * *(_DWORD *)(v26 + 8)),
          *(_DWORD *)(v26 + 12) & 0x7F,
          v14,
          v14);
        PPRmtStrcat2REAL(L"=", L"?");
        result = v22;
        v11 = (int *)L",";
      }
      v26 += 24;
    }
    v12 += 52;
  }
  while ( v12 < result );
  if ( v11 == &dword_1000EF34 )
  {
LABEL_33:
    *v6 = 0;
    return result;
  }
  v15 = (_WORD *)*v6;
  while ( *v15++ )
    ;
  *(_WORD *)(a4 + 1046) = ((int)v15 - *v6 - 2) >> 1;
  PPRmtStrcat2REAL(L" WHERE ", *(void **)(a2 + 284));
  result = a1;
  if ( *(_WORD *)(a1 + 136) != 4 )
  {
    v17 = *(void **)(a2 + 296);
    if ( v17 )
      result = PPRmtStrcat2REAL(v17, 0);
    else
      result = AddAllColsQual(lpAddress, a4, (int)v6);
  }
  if ( (lpAddress[19] & 0x10) != 0 && lpAddress[41] == 4 )
  {
    v8 = ErrCallocPvHsegREAL(lpAddress, 2, 1);
    if ( v8 >= 0 )
    {
      v18 = 0;
      v19 = &dword_1000EF34;
      v20 = (_DWORD *)a5[12];
      if ( v25 - 1 <= 0 )
        goto LABEL_32;
      v21 = v25;
      while ( 1 )
      {
        if ( (*v20 & 0x1FF) == 1 )
        {
          if ( (v20[5] & 0x1FF) != 2 )
          {
            result = a4 + 1056;
            lpAddress[19] &= ~0x10u;
            *v28 = 0;
LABEL_31:
            if ( v19 == &dword_1000EF34 )
            {
LABEL_32:
              result = a4 + 1056;
              lpAddress[19] &= ~0x10u;
              *v28 = 0;
            }
            return result;
          }
          PPRmtStrcat2REAL(v19, 0);
          PPRmtStrcat2REAL(*(void **)(a5[16] + 4 * v18 + 4), L"=");
          PPRmtAddHte(a1, *(_DWORD *)(v20[4] + 8), (int)lpAddress, (int)v28, 0, 0, 0);
          v20 += 5;
          v19 = (int *)L",";
          v21 = v25;
          ++v18;
        }
        ++v18;
        result = v21 - 1;
        v20 += 5;
        if ( v18 >= v21 - 1 )
          goto LABEL_31;
      }
    }
LABEL_4:
    _longjmp(*(int **)(a1 + 24), v8);
  }
  return result;
}

```

## disassembly

```asm
0x100d964c  mov     edi, edi
0x100d964e  push    ebp
0x100d964f  mov     ebp, esp
0x100d9651  sub     esp, 1Ch
0x100d9654  push    ebx
0x100d9655  mov     ebx, edx
0x100d9657  mov     [ebp+var_8], ecx
0x100d965a  mov     ecx, [ebp+arg_4]
0x100d965d  push    esi
0x100d965e  mov     esi, [ebp+lpAddress]
0x100d9661  mov     eax, [ebx+12Ch]
0x100d9667  mov     [ebp+var_18], eax
0x100d966a  mov     eax, [ecx+10h]
0x100d966d  test    dword ptr [esi+1Ch], 8000h
0x100d9674  mov     [ebp+var_C], eax
0x100d9677  mov     eax, [ebp+arg_8]
0x100d967a  push    edi
0x100d967b  lea     edi, [ecx+410h]
0x100d9681  mov     [ebp+var_14], ebx
0x100d9684  push    edi
0x100d9685  mov     eax, [eax+34h]
0x100d9688  push    1
0x100d968a  push    2
0x100d968c  lea     edx, [eax-1]
0x100d968f  cmovz   edx, eax
0x100d9692  lea     eax, [ecx+420h]
0x100d9698  mov     [ebp+var_10], edx
0x100d969b  mov     ecx, esi
0x100d969d  xor     edx, edx
0x100d969f  mov     [ebp+var_4], eax
0x100d96a2  mov     [ebp+var_1C], edx
0x100d96a5  mov     [eax], edx
0x100d96a7  pop     edx
0x100d96a8  call    _ErrCallocPvHsegREAL@16; ErrCallocPvHsegREAL(x,x,x,x)
0x100d96ad  test    eax, eax
0x100d96af  jns     short loc_100D96BE
0x100d96b1  push    eax; Value
0x100d96b2  mov     eax, [ebp+var_8]
0x100d96b5  push    dword ptr [eax+18h]; Buf
0x100d96b8  call    ds:__imp__longjmp
0x100d96be  push    offset asc_1000EF38; " "
0x100d96c3  push    offset aUpdate_1; "UPDATE"
0x100d96c8  mov     edx, edi
0x100d96ca  mov     ecx, esi
0x100d96cc  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d96d1  mov     eax, [ebp+var_18]
0x100d96d4  mov     edx, edi
0x100d96d6  add     eax, 30h ; '0'
0x100d96d9  mov     ecx, esi
0x100d96db  push    eax; Src
0x100d96dc  push    dword ptr [ebx+110h]; Str
0x100d96e2  call    _PPAddOwnerTable@16; PPAddOwnerTable(x,x,x,x)
0x100d96e7  push    0; void *
0x100d96e9  push    offset asc_1000EF38; " "
0x100d96ee  mov     edx, edi
0x100d96f0  mov     ecx, esi
0x100d96f2  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d96f7  push    offset asc_1000EF38; " "
0x100d96fc  push    offset aSet_0; "SET"
0x100d9701  mov     edx, edi
0x100d9703  mov     ecx, esi
0x100d9705  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d970a  mov     ecx, [edi]
0x100d970c  lea     edx, [ecx+2]
0x100d970f  mov     ax, [ecx]
0x100d9712  add     ecx, 2
0x100d9715  cmp     ax, word ptr [ebp+var_1C]
0x100d9719  jnz     short loc_100D970F
0x100d971b  mov     eax, [ebp+var_14]
0x100d971e  sub     ecx, edx
0x100d9720  mov     edx, [ebp+arg_4]
0x100d9723  sar     ecx, 1
0x100d9725  mov     [edx+414h], cx
0x100d972c  mov     edx, offset dword_1000EF34
0x100d9731  imul    eax, [eax+8], 34h ; '4'
0x100d9735  mov     ebx, [ebx+4]
0x100d9738  add     eax, ebx
0x100d973a  mov     [ebp+var_1C], eax
0x100d973d  cmp     ebx, eax
0x100d973f  jnb     loc_100D9907
0x100d9745  movzx   ecx, word ptr [ebx+30h]
0x100d9749  test    ecx, 100h
0x100d974f  jz      short loc_100D97A6
0x100d9751  test    ecx, 200h
0x100d9757  jz      short loc_100D97A2
0x100d9759  push    0; void *
0x100d975b  push    edx; Src
0x100d975c  mov     edx, edi
0x100d975e  mov     ecx, esi
0x100d9760  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d9765  push    ecx; int
0x100d9766  push    ecx; int
0x100d9767  mov     ecx, [ebp+var_C]
0x100d976a  mov     edx, edi
0x100d976c  mov     eax, [ecx+0Ch]
0x100d976f  mov     ecx, [ecx+8]
0x100d9772  and     eax, 7Fh
0x100d9775  push    eax; int
0x100d9776  mov     eax, [ebp+arg_4]
0x100d9779  mov     eax, [eax+8]
0x100d977c  lea     eax, [eax+ecx*2]
0x100d977f  mov     ecx, esi; lpAddress
0x100d9781  push    eax; Src
0x100d9782  call    _PPRmtStrcatCch2REAL@24; PPRmtStrcatCch2REAL(x,x,x,x,x,x)
0x100d9787  push    offset asc_1000EF9C; "?"
0x100d978c  push    offset asc_1000EFBC; "="
0x100d9791  mov     edx, edi
0x100d9793  mov     ecx, esi
0x100d9795  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d979a  mov     eax, [ebp+var_1C]
0x100d979d  mov     edx, offset asc_1000EF2C; ","
0x100d97a2  add     [ebp+var_C], 18h
0x100d97a6  add     ebx, 34h ; '4'
0x100d97a9  cmp     ebx, eax
0x100d97ab  jb      short loc_100D9745
0x100d97ad  cmp     edx, offset dword_1000EF34
0x100d97b3  jz      loc_100D9907
0x100d97b9  mov     ecx, [edi]
0x100d97bb  xor     ebx, ebx
0x100d97bd  lea     edx, [ecx+2]
0x100d97c0  mov     ax, [ecx]
0x100d97c3  add     ecx, 2
0x100d97c6  cmp     ax, bx
0x100d97c9  jnz     short loc_100D97C0
0x100d97cb  mov     eax, [ebp+arg_4]
0x100d97ce  sub     ecx, edx
0x100d97d0  mov     ebx, [ebp+var_14]
0x100d97d3  mov     edx, edi
0x100d97d5  sar     ecx, 1
0x100d97d7  mov     [eax+416h], cx
0x100d97de  mov     ecx, esi
0x100d97e0  push    dword ptr [ebx+11Ch]; void *
0x100d97e6  push    offset aWhere_0; " WHERE "
0x100d97eb  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d97f0  mov     eax, [ebp+var_8]
0x100d97f3  push    4
0x100d97f5  pop     ecx
0x100d97f6  cmp     [eax+88h], cx
0x100d97fd  jz      short loc_100D9826
0x100d97ff  mov     eax, [ebx+128h]
0x100d9805  test    eax, eax
0x100d9807  jz      short loc_100D9817
0x100d9809  push    0; void *
0x100d980b  push    eax; Src
0x100d980c  mov     edx, edi
0x100d980e  mov     ecx, esi
0x100d9810  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d9815  jmp     short loc_100D9823
0x100d9817  push    edi; int
0x100d9818  push    [ebp+arg_4]; int
0x100d981b  mov     edx, ebx
0x100d981d  push    esi; lpAddress
0x100d981e  call    AddAllColsQual
0x100d9823  push    4
0x100d9825  pop     ecx
0x100d9826  test    byte ptr [esi+4Ch], 10h
0x100d982a  jz      loc_100D990D
0x100d9830  cmp     [esi+0A4h], ecx
0x100d9836  jnz     loc_100D990D
0x100d983c  push    [ebp+var_4]
0x100d983f  mov     ecx, esi
0x100d9841  push    1
0x100d9843  push    2
0x100d9845  pop     edx
0x100d9846  call    _ErrCallocPvHsegREAL@16; ErrCallocPvHsegREAL(x,x,x,x)
0x100d984b  test    eax, eax
0x100d984d  js      loc_100D96B1
0x100d9853  mov     eax, [ebp+arg_8]
0x100d9856  xor     ebx, ebx
0x100d9858  mov     ecx, offset dword_1000EF34
0x100d985d  mov     edi, [eax+30h]
0x100d9860  mov     eax, [ebp+var_10]
0x100d9863  dec     eax
0x100d9864  test    eax, eax
0x100d9866  jle     loc_100D98F8
0x100d986c  mov     edx, [ebp+var_10]
0x100d986f  mov     eax, [edi]
0x100d9871  and     eax, 1FFh
0x100d9876  cmp     eax, 1
0x100d9879  jnz     short loc_100D98D6
0x100d987b  lea     eax, [edi+14h]
0x100d987e  mov     [ebp+var_1C], eax
0x100d9881  mov     eax, [eax]
0x100d9883  and     eax, 1FFh
0x100d9888  cmp     eax, 2
0x100d988b  jnz     short loc_100D98E3
0x100d988d  mov     edx, [ebp+var_4]
0x100d9890  push    0; void *
0x100d9892  push    ecx; Src
0x100d9893  mov     ecx, esi
0x100d9895  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d989a  mov     eax, [ebp+arg_8]
0x100d989d  mov     ecx, esi
0x100d989f  mov     edx, [ebp+var_4]
0x100d98a2  push    offset asc_1000EFBC; "="
0x100d98a7  mov     eax, [eax+40h]
0x100d98aa  push    dword ptr [eax+ebx*4+4]; Src
0x100d98ae  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d98b3  mov     edx, [edi+10h]
0x100d98b6  xor     eax, eax
0x100d98b8  mov     ecx, [ebp+var_8]
0x100d98bb  push    eax
0x100d98bc  push    eax
0x100d98bd  mov     edx, [edx+8]
0x100d98c0  push    eax
0x100d98c1  push    [ebp+var_4]
0x100d98c4  push    esi
0x100d98c5  call    _PPRmtAddHte@28; PPRmtAddHte(x,x,x,x,x,x,x)
0x100d98ca  mov     edi, [ebp+var_1C]
0x100d98cd  mov     ecx, offset asc_1000EF2C; ","
0x100d98d2  mov     edx, [ebp+var_10]
0x100d98d5  inc     ebx
0x100d98d6  inc     ebx
0x100d98d7  lea     eax, [edx-1]
0x100d98da  add     edi, 14h
0x100d98dd  cmp     ebx, eax
0x100d98df  jl      short loc_100D986F
0x100d98e1  jmp     short loc_100D98F0
0x100d98e3  mov     eax, [ebp+var_4]
0x100d98e6  and     dword ptr [esi+4Ch], 0FFFFFFEFh
0x100d98ea  mov     dword ptr [eax], 0
0x100d98f0  cmp     ecx, offset dword_1000EF34
0x100d98f6  jnz     short loc_100D990D
0x100d98f8  mov     eax, [ebp+var_4]
0x100d98fb  and     dword ptr [esi+4Ch], 0FFFFFFEFh
0x100d98ff  mov     dword ptr [eax], 0
0x100d9905  jmp     short loc_100D990D
0x100d9907  mov     dword ptr [edi], 0
0x100d990d  pop     edi
0x100d990e  pop     esi
0x100d990f  pop     ebx
0x100d9910  leave
0x100d9911  retn    0Ch
```
