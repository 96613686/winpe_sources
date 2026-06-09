# RmtGenUpdate

- ea: `0x100d94bc`
- end: `0x100d9784`
- name: `RmtGenUpdate`
- size: `712`
- prototype: `unsigned int __fastcall(int, int, _DWORD *lpAddress, int, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x100d986d`

## callees

- `0x100aef6e`
- `0x100afa85`
- `0x100b0c26`
- `0x100b0d04`
- `0x100b74ea`
- `0x100d93d5`
- `0x100d94bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100d9528`
- `api-ms-win-crt-private-l1-1-0!longjmp` at `0x100d9528`

## string_xrefs

- `0x100d9533`: `UPDATE`

## pseudocode

```c
unsigned int __fastcall RmtGenUpdate(int a1, int a2, _DWORD *lpAddress, int a4, _DWORD *a5)
{
  _WORD **v6; // edi
  int v7; // edx
  int v8; // eax
  _WORD *v9; // ecx
  const unsigned __int16 *v11; // edx
  unsigned int v12; // ebx
  unsigned int result; // eax
  int v14; // ecx
  _WORD *v15; // ecx
  const unsigned __int16 *v17; // eax
  int v18; // ebx
  int *v19; // ecx
  _DWORD *v20; // edi
  int v21; // edx
  unsigned int v22; // [esp+Ch] [ebp-1Ch]
  int v23; // [esp+10h] [ebp-18h]
  int v25; // [esp+18h] [ebp-10h]
  int v26; // [esp+1Ch] [ebp-Ch]
  _WORD **v28; // [esp+24h] [ebp-4h]

  v23 = *(_DWORD *)(a2 + 300);
  v26 = *(_DWORD *)(a4 + 16);
  v6 = (_WORD **)(a4 + 1040);
  v7 = a5[13] - 1;
  if ( (lpAddress[7] & 0x8000) == 0 )
    v7 = a5[13];
  v25 = v7;
  v28 = (_WORD **)(a4 + 1056);
  *(_DWORD *)(a4 + 1056) = 0;
  v8 = ErrCallocPvHsegREAL(lpAddress, 2, 1);
  if ( v8 < 0 )
    goto LABEL_4;
  PPRmtStrcat2REAL(lpAddress, v6, L"UPDATE", L" ");
  PPAddOwnerTable(*(wchar_t **)(a2 + 272), (void *)(v23 + 48));
  PPRmtStrcat2REAL(lpAddress, v6, L" ", 0);
  PPRmtStrcat2REAL(lpAddress, v6, L"SET", L" ");
  v9 = *v6;
  while ( *v9++ )
    ;
  *(_WORD *)(a4 + 1044) = v9 - (*v6 + 1);
  v11 = (const unsigned __int16 *)&dword_1000EE3C;
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
        PPRmtStrcat2REAL(lpAddress, v6, v11, 0);
        PPRmtStrcatCch2REAL(
          lpAddress,
          (void *)(*(_DWORD *)(a4 + 8) + 2 * *(_DWORD *)(v26 + 8)),
          *(_DWORD *)(v26 + 12) & 0x7F,
          v14,
          v14);
        PPRmtStrcat2REAL(lpAddress, v6, L"=", L"?");
        result = v22;
        v11 = L",";
      }
      v26 += 24;
    }
    v12 += 52;
  }
  while ( v12 < result );
  if ( v11 == (const unsigned __int16 *)&dword_1000EE3C )
  {
LABEL_33:
    *v6 = 0;
    return result;
  }
  v15 = *v6;
  while ( *v15++ )
    ;
  *(_WORD *)(a4 + 1046) = v15 - (*v6 + 1);
  PPRmtStrcat2REAL(lpAddress, v6, L" WHERE ", *(const unsigned __int16 **)(a2 + 284));
  result = a1;
  if ( *(_WORD *)(a1 + 136) != 4 )
  {
    v17 = *(const unsigned __int16 **)(a2 + 296);
    if ( v17 )
      result = PPRmtStrcat2REAL(lpAddress, v6, v17, 0);
    else
      result = AddAllColsQual(lpAddress, a4, (int)v6);
  }
  if ( (lpAddress[19] & 0x10) != 0 && lpAddress[41] == 4 )
  {
    v8 = ErrCallocPvHsegREAL(lpAddress, 2, 1);
    if ( v8 >= 0 )
    {
      v18 = 0;
      v19 = &dword_1000EE3C;
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
            if ( v19 == &dword_1000EE3C )
            {
LABEL_32:
              result = a4 + 1056;
              lpAddress[19] &= ~0x10u;
              *v28 = 0;
            }
            return result;
          }
          PPRmtStrcat2REAL(lpAddress, v28, (const unsigned __int16 *)v19, 0);
          PPRmtStrcat2REAL(lpAddress, v28, *(const unsigned __int16 **)(a5[16] + 4 * v18 + 4), L"=");
          PPRmtAddHte(lpAddress, v28, 0, 0, 0);
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
0x100d94bc  mov     edi, edi
0x100d94be  push    ebp
0x100d94bf  mov     ebp, esp
0x100d94c1  sub     esp, 1Ch
0x100d94c4  push    ebx
0x100d94c5  mov     ebx, edx
0x100d94c7  mov     [ebp+var_8], ecx
0x100d94ca  mov     ecx, [ebp+arg_4]
0x100d94cd  push    esi
0x100d94ce  mov     esi, [ebp+lpAddress]
0x100d94d1  mov     eax, [ebx+12Ch]
0x100d94d7  mov     [ebp+var_18], eax
0x100d94da  mov     eax, [ecx+10h]
0x100d94dd  test    dword ptr [esi+1Ch], 8000h
0x100d94e4  mov     [ebp+var_C], eax
0x100d94e7  mov     eax, [ebp+arg_8]
0x100d94ea  push    edi
0x100d94eb  lea     edi, [ecx+410h]
0x100d94f1  mov     [ebp+var_14], ebx
0x100d94f4  push    edi
0x100d94f5  mov     eax, [eax+34h]
0x100d94f8  push    1
0x100d94fa  push    2
0x100d94fc  lea     edx, [eax-1]
0x100d94ff  cmovz   edx, eax
0x100d9502  lea     eax, [ecx+420h]
0x100d9508  mov     [ebp+var_10], edx
0x100d950b  mov     ecx, esi
0x100d950d  xor     edx, edx
0x100d950f  mov     [ebp+var_4], eax
0x100d9512  mov     [ebp+var_1C], edx
0x100d9515  mov     [eax], edx
0x100d9517  pop     edx
0x100d9518  call    _ErrCallocPvHsegREAL@16; ErrCallocPvHsegREAL(x,x,x,x)
0x100d951d  test    eax, eax
0x100d951f  jns     short loc_100D952E
0x100d9521  push    eax; Value
0x100d9522  mov     eax, [ebp+var_8]
0x100d9525  push    dword ptr [eax+18h]; Buf
0x100d9528  call    ds:__imp__longjmp
0x100d952e  push    offset asc_1000EE40; " "
0x100d9533  push    offset aUpdate_1; "UPDATE"
0x100d9538  mov     edx, edi
0x100d953a  mov     ecx, esi
0x100d953c  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d9541  mov     eax, [ebp+var_18]
0x100d9544  mov     edx, edi
0x100d9546  add     eax, 30h ; '0'
0x100d9549  mov     ecx, esi
0x100d954b  push    eax; Src
0x100d954c  push    dword ptr [ebx+110h]; Str
0x100d9552  call    _PPAddOwnerTable@16; PPAddOwnerTable(x,x,x,x)
0x100d9557  push    0; void *
0x100d9559  push    offset asc_1000EE40; " "
0x100d955e  mov     edx, edi
0x100d9560  mov     ecx, esi
0x100d9562  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d9567  push    offset asc_1000EE40; " "
0x100d956c  push    offset aSet_0; "SET"
0x100d9571  mov     edx, edi
0x100d9573  mov     ecx, esi
0x100d9575  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d957a  mov     ecx, [edi]
0x100d957c  lea     edx, [ecx+2]
0x100d957f  mov     ax, [ecx]
0x100d9582  add     ecx, 2
0x100d9585  cmp     ax, word ptr [ebp+var_1C]
0x100d9589  jnz     short loc_100D957F
0x100d958b  mov     eax, [ebp+var_14]
0x100d958e  sub     ecx, edx
0x100d9590  mov     edx, [ebp+arg_4]
0x100d9593  sar     ecx, 1
0x100d9595  mov     [edx+414h], cx
0x100d959c  mov     edx, offset dword_1000EE3C
0x100d95a1  imul    eax, [eax+8], 34h ; '4'
0x100d95a5  mov     ebx, [ebx+4]
0x100d95a8  add     eax, ebx
0x100d95aa  mov     [ebp+var_1C], eax
0x100d95ad  cmp     ebx, eax
0x100d95af  jnb     loc_100D9777
0x100d95b5  movzx   ecx, word ptr [ebx+30h]
0x100d95b9  test    ecx, 100h
0x100d95bf  jz      short loc_100D9616
0x100d95c1  test    ecx, 200h
0x100d95c7  jz      short loc_100D9612
0x100d95c9  push    0; void *
0x100d95cb  push    edx; Src
0x100d95cc  mov     edx, edi
0x100d95ce  mov     ecx, esi
0x100d95d0  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d95d5  push    ecx; int
0x100d95d6  push    ecx; int
0x100d95d7  mov     ecx, [ebp+var_C]
0x100d95da  mov     edx, edi
0x100d95dc  mov     eax, [ecx+0Ch]
0x100d95df  mov     ecx, [ecx+8]
0x100d95e2  and     eax, 7Fh
0x100d95e5  push    eax; int
0x100d95e6  mov     eax, [ebp+arg_4]
0x100d95e9  mov     eax, [eax+8]
0x100d95ec  lea     eax, [eax+ecx*2]
0x100d95ef  mov     ecx, esi; lpAddress
0x100d95f1  push    eax; Src
0x100d95f2  call    _PPRmtStrcatCch2REAL@24; PPRmtStrcatCch2REAL(x,x,x,x,x,x)
0x100d95f7  push    offset asc_1000EEA4; "?"
0x100d95fc  push    offset asc_1000EEC4; "="
0x100d9601  mov     edx, edi
0x100d9603  mov     ecx, esi
0x100d9605  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d960a  mov     eax, [ebp+var_1C]
0x100d960d  mov     edx, offset asc_1000EE34; ","
0x100d9612  add     [ebp+var_C], 18h
0x100d9616  add     ebx, 34h ; '4'
0x100d9619  cmp     ebx, eax
0x100d961b  jb      short loc_100D95B5
0x100d961d  cmp     edx, offset dword_1000EE3C
0x100d9623  jz      loc_100D9777
0x100d9629  mov     ecx, [edi]
0x100d962b  xor     ebx, ebx
0x100d962d  lea     edx, [ecx+2]
0x100d9630  mov     ax, [ecx]
0x100d9633  add     ecx, 2
0x100d9636  cmp     ax, bx
0x100d9639  jnz     short loc_100D9630
0x100d963b  mov     eax, [ebp+arg_4]
0x100d963e  sub     ecx, edx
0x100d9640  mov     ebx, [ebp+var_14]
0x100d9643  mov     edx, edi
0x100d9645  sar     ecx, 1
0x100d9647  mov     [eax+416h], cx
0x100d964e  mov     ecx, esi
0x100d9650  push    dword ptr [ebx+11Ch]; void *
0x100d9656  push    offset aWhere_0; " WHERE "
0x100d965b  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d9660  mov     eax, [ebp+var_8]
0x100d9663  push    4
0x100d9665  pop     ecx
0x100d9666  cmp     [eax+88h], cx
0x100d966d  jz      short loc_100D9696
0x100d966f  mov     eax, [ebx+128h]
0x100d9675  test    eax, eax
0x100d9677  jz      short loc_100D9687
0x100d9679  push    0; void *
0x100d967b  push    eax; Src
0x100d967c  mov     edx, edi
0x100d967e  mov     ecx, esi
0x100d9680  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d9685  jmp     short loc_100D9693
0x100d9687  push    edi; int
0x100d9688  push    [ebp+arg_4]; int
0x100d968b  mov     edx, ebx
0x100d968d  push    esi; lpAddress
0x100d968e  call    AddAllColsQual
0x100d9693  push    4
0x100d9695  pop     ecx
0x100d9696  test    byte ptr [esi+4Ch], 10h
0x100d969a  jz      loc_100D977D
0x100d96a0  cmp     [esi+0A4h], ecx
0x100d96a6  jnz     loc_100D977D
0x100d96ac  push    [ebp+var_4]
0x100d96af  mov     ecx, esi
0x100d96b1  push    1
0x100d96b3  push    2
0x100d96b5  pop     edx
0x100d96b6  call    _ErrCallocPvHsegREAL@16; ErrCallocPvHsegREAL(x,x,x,x)
0x100d96bb  test    eax, eax
0x100d96bd  js      loc_100D9521
0x100d96c3  mov     eax, [ebp+arg_8]
0x100d96c6  xor     ebx, ebx
0x100d96c8  mov     ecx, offset dword_1000EE3C
0x100d96cd  mov     edi, [eax+30h]
0x100d96d0  mov     eax, [ebp+var_10]
0x100d96d3  dec     eax
0x100d96d4  test    eax, eax
0x100d96d6  jle     loc_100D9768
0x100d96dc  mov     edx, [ebp+var_10]
0x100d96df  mov     eax, [edi]
0x100d96e1  and     eax, 1FFh
0x100d96e6  cmp     eax, 1
0x100d96e9  jnz     short loc_100D9746
0x100d96eb  lea     eax, [edi+14h]
0x100d96ee  mov     [ebp+var_1C], eax
0x100d96f1  mov     eax, [eax]
0x100d96f3  and     eax, 1FFh
0x100d96f8  cmp     eax, 2
0x100d96fb  jnz     short loc_100D9753
0x100d96fd  mov     edx, [ebp+var_4]
0x100d9700  push    0; void *
0x100d9702  push    ecx; Src
0x100d9703  mov     ecx, esi
0x100d9705  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d970a  mov     eax, [ebp+arg_8]
0x100d970d  mov     ecx, esi
0x100d970f  mov     edx, [ebp+var_4]
0x100d9712  push    offset asc_1000EEC4; "="
0x100d9717  mov     eax, [eax+40h]
0x100d971a  push    dword ptr [eax+ebx*4+4]; Src
0x100d971e  call    _PPRmtStrcat2REAL@16; PPRmtStrcat2REAL(x,x,x,x)
0x100d9723  mov     edx, [edi+10h]
0x100d9726  xor     eax, eax
0x100d9728  mov     ecx, [ebp+var_8]
0x100d972b  push    eax
0x100d972c  push    eax
0x100d972d  mov     edx, [edx+8]
0x100d9730  push    eax
0x100d9731  push    [ebp+var_4]
0x100d9734  push    esi
0x100d9735  call    _PPRmtAddHte@28; PPRmtAddHte(x,x,x,x,x,x,x)
0x100d973a  mov     edi, [ebp+var_1C]
0x100d973d  mov     ecx, offset asc_1000EE34; ","
0x100d9742  mov     edx, [ebp+var_10]
0x100d9745  inc     ebx
0x100d9746  inc     ebx
0x100d9747  lea     eax, [edx-1]
0x100d974a  add     edi, 14h
0x100d974d  cmp     ebx, eax
0x100d974f  jl      short loc_100D96DF
0x100d9751  jmp     short loc_100D9760
0x100d9753  mov     eax, [ebp+var_4]
0x100d9756  and     dword ptr [esi+4Ch], 0FFFFFFEFh
0x100d975a  mov     dword ptr [eax], 0
0x100d9760  cmp     ecx, offset dword_1000EE3C
0x100d9766  jnz     short loc_100D977D
0x100d9768  mov     eax, [ebp+var_4]
0x100d976b  and     dword ptr [esi+4Ch], 0FFFFFFEFh
0x100d976f  mov     dword ptr [eax], 0
0x100d9775  jmp     short loc_100D977D
0x100d9777  mov     dword ptr [edi], 0
0x100d977d  pop     edi
0x100d977e  pop     esi
0x100d977f  pop     ebx
0x100d9780  leave
0x100d9781  retn    0Ch
```
