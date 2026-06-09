# ExcelMIAddName(x,x,x,x,x,x,x,x,x)

- ea: `0x1000b350`
- end: `0x1000bb94`
- name: `_ExcelMIAddName@36`
- size: `2116`
- prototype: `int __fastcall(int, int, int, int, const unsigned __int16 *, int, int, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x10016060`

## callees

- `0x1000ab50`
- `0x1000b350`
- `0x1000e440`
- `0x1002580a`
- `0x10025ab7`
- `0x10035510`
- `0x10035b40`
- `0x10035f40`
- `0x1003669c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1000b76d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1000b8e5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1000b76d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1000b8e5`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1000bb29`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1000bb29`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1000bb30`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1000bb30`

## pseudocode

```c
int __fastcall ExcelMIAddName(
        int a1,
        int a2,
        int a3,
        int a4,
        const unsigned __int16 *a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  int v9; // eax
  int result; // eax
  size_t v11; // ecx
  size_t v12; // edi
  int v13; // edx
  size_t v14; // eax
  size_t v15; // esi
  int v16; // eax
  int v17; // edx
  unsigned int v18; // ebx
  size_t v19; // esi
  int v20; // edx
  bool v21; // cf
  unsigned int v22; // ebx
  __int16 v23; // dx
  _DWORD *v24; // eax
  int v25; // eax
  size_t v26; // esi
  size_t v27; // eax
  __int16 *v28; // ebx
  int v29; // eax
  int v30; // edx
  int v31; // ebx
  int *v32; // ecx
  __int16 v33; // ax
  int *i; // eax
  int v35; // edi
  CHAR *v36; // ebx
  size_t v37; // eax
  __int16 v38; // ax
  size_t v39; // ecx
  _WORD *v40; // eax
  _DWORD *v41; // edi
  int v42; // edx
  _DWORD *v43; // ecx
  _DWORD *j; // eax
  int v45; // esi
  CHAR *v46; // edi
  int v47; // eax
  size_t v48; // ebx
  __int16 v49; // ax
  size_t v50; // ecx
  int v51; // edi
  int v52; // eax
  int *v53; // esi
  const void *v54; // ebx
  _WORD *v55; // eax
  _DWORD *v56; // esi
  int v57; // edx
  _DWORD *v58; // ecx
  _DWORD *v59; // eax
  __int16 v60; // bx
  _WORD *v61; // ecx
  WCHAR *v62; // eax
  int v63; // edi
  _WORD *v64; // eax
  LCID UserDefaultLCID; // eax
  int v66; // [esp-Ch] [ebp-248h]
  int v67; // [esp-Ch] [ebp-248h]
  size_t v68; // [esp-4h] [ebp-240h]
  __int16 v69; // [esp+Ch] [ebp-230h]
  __int16 v70; // [esp+10h] [ebp-22Ch]
  __int16 v71; // [esp+14h] [ebp-228h]
  __int16 Src; // [esp+1Ch] [ebp-220h]
  _BYTE *Srca; // [esp+1Ch] [ebp-220h]
  void *Srcb; // [esp+1Ch] [ebp-220h]
  void *Srcc; // [esp+1Ch] [ebp-220h]
  __int16 Srcd; // [esp+1Ch] [ebp-220h]
  int v77; // [esp+20h] [ebp-21Ch]
  _DWORD *v78; // [esp+20h] [ebp-21Ch]
  int v80; // [esp+28h] [ebp-214h]
  void *v81; // [esp+28h] [ebp-214h]
  _WORD *v82; // [esp+28h] [ebp-214h]
  size_t Size; // [esp+2Ch] [ebp-210h]
  _BYTE v84[516]; // [esp+30h] [ebp-20Ch] BYREF

  v9 = 1;
  v70 = 1;
  if ( *(int *)(a2 + 36) >= 8 )
    return AddV8Name(a1, (_DWORD **)a2, a1, a5, a6, a1, a8, a9);
  v11 = *(_DWORD *)(a2 + 4);
  v12 = v11;
  if ( !v11 )
  {
LABEL_45:
    v12 = 0;
    v25 = 1;
    if ( v11 )
      goto LABEL_46;
LABEL_51:
    v78 = (_DWORD *)v12;
    v70 = 1;
    v15 = v12;
    v80 = 1;
LABEL_52:
    Size = v15;
    goto LABEL_53;
  }
  while ( *(_WORD *)(v12 + 4) != 22 || --v9 )
  {
    v12 = *(_DWORD *)v12;
    if ( !v12 )
    {
      v13 = 1;
      v14 = v11;
      while ( *(_WORD *)(v14 + 4) != 156 || --v13 )
      {
        v14 = *(_DWORD *)v14;
        if ( !v14 )
        {
          v25 = 1;
          v12 = 0;
LABEL_46:
          while ( *(_WORD *)(v11 + 4) != 61 || --v25 )
          {
            v11 = *(_DWORD *)v11;
            if ( !v11 )
              goto LABEL_51;
          }
          v12 = v11;
          goto LABEL_51;
        }
      }
      v12 = *(_DWORD *)v14;
      if ( *(_DWORD *)v14 )
        goto LABEL_51;
      goto LABEL_45;
    }
  }
  v15 = *(_DWORD *)v12;
  v80 = *(__int16 *)(v12 + 8);
  v16 = 0;
  v17 = v80;
  Size = *(_DWORD *)v12;
  v77 = 0;
  if ( v80 <= 0 )
  {
LABEL_25:
    if ( v16 == v17 )
    {
      v80 = v17 + 1;
      v23 = v16 + 1;
      v70 = v16 + 1;
    }
    else
    {
      v15 = 0;
      v23 = 1;
LABEL_30:
      Size = 0;
    }
    v78 = 0;
    while ( *(_WORD *)(v11 + 4) != 24 )
    {
      v11 = *(_DWORD *)v11;
      if ( !v11 )
      {
        v70 = v23;
        goto LABEL_52;
      }
    }
    v24 = (_DWORD *)v11;
    do
    {
      if ( *(_WORD *)(v11 + 4) != 24 )
        break;
      v24 = (_DWORD *)v11;
      v11 = *(_DWORD *)v11;
    }
    while ( v11 );
    v78 = (_DWORD *)*v24;
LABEL_53:
    if ( v12 )
    {
      v26 = g_cbCurrentSize;
      v27 = 2;
      v28 = (__int16 *)pExcelRecordBuffer;
      v69 = 22;
      if ( (int)g_cbCurrentSize <= 2 )
        v27 = g_cbCurrentSize;
      v71 = 2;
      memset(pExcelRecordBuffer, 0, v27);
      if ( v26 >= 2 )
        *v28 = v80;
      if ( v80 == 1 )
      {
        v29 = MemAllocate(13);
        v30 = v29;
        if ( v29 )
        {
          *(_DWORD *)(v29 + 4) = 131094;
          v32 = 0;
          v33 = *v28;
          v31 = a2;
          *(_WORD *)(v30 + 8) = v33;
          for ( i = *(int **)(a2 + 4); i; i = (int *)*i )
          {
            if ( i == (int *)v12 )
              break;
            v32 = i;
          }
          *(_DWORD *)v30 = i;
          if ( v32 )
            *v32 = v30;
          else
            *(_DWORD *)(a2 + 4) = v30;
          result = 0;
        }
        else
        {
          v31 = a2;
          result = -2;
        }
        if ( result )
          return result;
        v15 = Size;
LABEL_73:
        if ( v15 )
        {
          v81 = (void *)g_cbCurrentSize;
          Srca = pExcelRecordBuffer;
          Size = *(_DWORD *)(v31 + 44);
          v35 = wcslen(a5);
          v36 = (CHAR *)MemAllocate(2 * v35 + 2);
          if ( v36 )
          {
            v66 = 2 * v35;
            if ( Size == 1200 )
              v37 = WideCharToMultiByte(0, 0, a5, v35, v36, v66, 0, 0);
            else
              v37 = WideCharToMultiByte(Size, 0, a5, v35, v36, v66, 0, 0);
            Size = v37;
            v38 = v37 + 2;
            v71 = v38;
            v39 = (size_t)v81;
            v69 = 23;
            if ( v38 < (int)v81 )
              v39 = v38;
            memset(Srca, 0, v39);
            if ( (int)v81 >= (int)(Size + 2) )
            {
              v68 = Size;
              *Srca = Size;
              Srca[1] = 3;
              memcpy(Srca + 2, v36, v68);
            }
            MemFree(v36);
          }
          Srcb = pExcelRecordBuffer;
          v40 = (_WORD *)MemAllocate(v71 + 11);
          v41 = v40;
          if ( !v40 )
            return -2;
          v40[2] = v69;
          v40[3] = v71;
          memcpy(v40 + 4, Srcb, v71);
          v42 = a2;
          v43 = 0;
          for ( j = *(_DWORD **)(a2 + 4); j; j = (_DWORD *)*j )
          {
            if ( j == (_DWORD *)v15 )
              break;
            v43 = j;
          }
          *v41 = j;
          if ( v43 )
            *v43 = v41;
          else
            *(_DWORD *)(a2 + 4) = v41;
        }
        else
        {
          v42 = a2;
        }
        Size = g_cbCurrentSize;
        v82 = pExcelRecordBuffer;
        Srcc = *(void **)(v42 + 44);
        v45 = wcslen(a5);
        v46 = (CHAR *)MemAllocate(2 * v45 + 2);
        if ( v46 )
        {
          v67 = 2 * v45;
          if ( Srcc == (void *)1200 )
            v47 = WideCharToMultiByte(0, 0, a5, v45, v46, v67, 0, 0);
          else
            v47 = WideCharToMultiByte((UINT)Srcc, 0, a5, v45, v46, v67, 0, 0);
          v48 = v47;
          v69 = 24;
          v49 = v47 + 35;
          v71 = v49;
          v50 = Size;
          if ( v49 < (int)Size )
            v50 = v49;
          memset(v82, 0, v50);
          if ( (int)Size >= (int)(v48 + 34) )
          {
            *((_BYTE *)v82 + 3) = v48;
            *v82 = 0;
            v82[2] = 21;
            memcpy(v82 + 7, v46, v48);
            *((_BYTE *)v82 + v48 + 14) = 59;
            *(_WORD *)((char *)v82 + v48 + 15) = -v70;
            *(_WORD *)((char *)v82 + v48 + 25) = a6;
            *(_WORD *)((char *)v82 + v48 + 27) = a6;
            *(_WORD *)((char *)v82 + v48 + 29) = a8;
            *(_WORD *)((char *)v82 + v48 + 31) = a9;
            *((_BYTE *)v82 + v48 + 33) = BYTE2(a8);
            *((_BYTE *)v82 + v48 + 34) = BYTE2(a9);
          }
          MemFree(v46);
        }
        v51 = a2;
        v52 = 1;
        v53 = *(int **)(a2 + 4);
        if ( v53 )
        {
          while ( *((_WORD *)v53 + 2) != 24 || --v52 )
          {
            v53 = (int *)*v53;
            if ( !v53 )
              goto LABEL_105;
          }
          while ( *((_WORD *)v53 + 2) == 24 )
          {
            v60 = *((_WORD *)v53 + 4);
            Srcd = *((_WORD *)v53 + 8);
            ExcelExtractString(
              *(_DWORD *)(v51 + 36),
              *(_DWORD *)(v51 + 44),
              (__m128i *)&ExcelRecordTextBuffer,
              512,
              (LPCCH)v53 + 22,
              *((unsigned __int8 *)v53 + 11));
            if ( (v60 & 0x20) != 0 && NameLocalizer )
            {
              NameLocalizer(NameLocalizer, &ExcelRecordTextBuffer, v84, 256);
            }
            else
            {
              memset(v84, 0, 0x200u);
              v61 = v84;
              v62 = &ExcelRecordTextBuffer;
              v63 = 256;
              do
              {
                if ( !*v62 )
                  break;
                *v61++ = *v62++;
                --v63;
              }
              while ( v63 );
              v64 = v61 - 1;
              if ( v63 )
                v64 = v61;
              *v64 = 0;
            }
            UserDefaultLCID = GetUserDefaultLCID();
            if ( DBCompareStringW(UserDefaultLCID, 196609, a5, -1, v84, -1) == 2 && !Srcd )
            {
              if ( *((_WORD *)v53 + 2) != 24 )
                break;
              memcpy(v53 + 2, pExcelRecordBuffer, *((__int16 *)v53 + 3));
              return 0;
            }
            v53 = (int *)*v53;
            if ( !v53 )
              break;
            v51 = a2;
          }
        }
LABEL_105:
        v54 = pExcelRecordBuffer;
        v55 = (_WORD *)MemAllocate(v71 + 11);
        v56 = v55;
        if ( v55 )
        {
          v55[2] = v69;
          v55[3] = v71;
          memcpy(v55 + 4, v54, v71);
          v57 = a2;
          v58 = 0;
          v59 = *(_DWORD **)(a2 + 4);
          if ( v59 )
          {
            do
            {
              if ( v59 == v78 )
                break;
              v58 = v59;
              v59 = (_DWORD *)*v59;
            }
            while ( v59 );
            v57 = a2;
          }
          *v56 = v59;
          if ( v58 )
            *v58 = v56;
          else
            *(_DWORD *)(v57 + 4) = v56;
          return 0;
        }
        return -2;
      }
      memcpy((void *)(v12 + 8), v28, *(__int16 *)(v12 + 6));
      v15 = Size;
    }
    else
    {
      v71 = Src;
      v69 = Src;
    }
    v31 = a2;
    goto LABEL_73;
  }
  while ( v15 && *(_WORD *)(v15 + 4) == 23 )
  {
    if ( (*(_BYTE *)(v15 + 9) & 0xF3) == 3 )
    {
      v18 = *(unsigned __int8 *)(v15 + 8);
      v19 = v15 + 10;
      v20 = a4;
      v21 = v18 < 4;
      v22 = v18 - 4;
      if ( v21 )
      {
LABEL_15:
        if ( v22 == -4 )
          goto LABEL_27;
      }
      else
      {
        while ( *(_DWORD *)v20 == *(_DWORD *)v19 )
        {
          v20 += 4;
          v19 += 4;
          v21 = v22 < 4;
          v22 -= 4;
          if ( v21 )
            goto LABEL_15;
        }
      }
      if ( *(_BYTE *)v20 == *(_BYTE *)v19
        && (v22 == -3
         || *(_BYTE *)(v20 + 1) == *(_BYTE *)(v19 + 1)
         && (v22 == -2
          || *(_BYTE *)(v20 + 2) == *(_BYTE *)(v19 + 2) && (v22 == -1 || *(_BYTE *)(v20 + 3) == *(_BYTE *)(v19 + 3)))) )
      {
LABEL_27:
        v12 = 0;
        v23 = v77 + 1;
        v15 = 0;
        v70 = v77 + 1;
        goto LABEL_30;
      }
      v17 = v80;
      v15 = Size;
    }
    v15 = *(_DWORD *)v15;
    v16 = v77 + 1;
    Size = v15;
    v77 = v16;
    if ( v16 >= v17 )
      goto LABEL_25;
  }
  return -10;
}

```

## disassembly

```asm
0x1000b350  mov     edi, edi
0x1000b352  push    ebp
0x1000b353  mov     ebp, esp
0x1000b355  sub     esp, 230h
0x1000b35b  mov     eax, ___security_cookie
0x1000b360  xor     eax, ebp
0x1000b362  mov     [ebp+var_8], eax
0x1000b365  cmp     dword ptr [edx+24h], 8
0x1000b369  mov     eax, 1
0x1000b36e  push    ebx
0x1000b36f  mov     ebx, [ebp+arg_8]
0x1000b372  push    esi
0x1000b373  push    edi
0x1000b374  mov     [ebp+var_218], edx
0x1000b37a  mov     [ebp+lpWideCharStr], ebx
0x1000b380  mov     [ebp+var_22C], eax
0x1000b386  jl      short loc_1000B3AC
0x1000b388  push    [ebp+arg_18]
0x1000b38b  push    [ebp+arg_14]
0x1000b38e  push    ecx
0x1000b38f  push    [ebp+arg_C]
0x1000b392  push    ebx
0x1000b393  push    ecx
0x1000b394  call    AddV8Name
0x1000b399  pop     edi
0x1000b39a  pop     esi
0x1000b39b  pop     ebx
0x1000b39c  mov     ecx, [ebp+var_8]
0x1000b39f  xor     ecx, ebp; StackCookie
0x1000b3a1  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000b3a6  mov     esp, ebp
0x1000b3a8  pop     ebp
0x1000b3a9  retn    1Ch
0x1000b3ac  mov     ecx, [edx+4]
0x1000b3af  mov     edi, ecx
0x1000b3b1  test    edi, edi
0x1000b3b3  jz      loc_1000B561
0x1000b3b9  nop     dword ptr [eax+00000000h]
0x1000b3c0  cmp     word ptr [edi+4], 16h
0x1000b3c5  jnz     short loc_1000B3D0
0x1000b3c7  test    eax, eax
0x1000b3c9  jz      short loc_1000B3E0
0x1000b3cb  sub     eax, 1
0x1000b3ce  jz      short loc_1000B3F3
0x1000b3d0  mov     edi, [edi]
0x1000b3d2  test    edi, edi
0x1000b3d4  jnz     short loc_1000B3C0
0x1000b3d6  lea     edx, [edi+1]
0x1000b3d9  mov     eax, ecx
0x1000b3db  jmp     loc_1000B56C
0x1000b3e0  mov     eax, edi
0x1000b3e2  cmp     word ptr [edi+4], 16h
0x1000b3e7  jnz     short loc_1000B3F1
0x1000b3e9  mov     eax, edi
0x1000b3eb  mov     edi, [edi]
0x1000b3ed  test    edi, edi
0x1000b3ef  jnz     short loc_1000B3E2
0x1000b3f1  mov     edi, eax
0x1000b3f3  test    edi, edi
0x1000b3f5  jz      loc_1000B561
0x1000b3fb  movsx   eax, word ptr [edi+8]
0x1000b3ff  mov     esi, [edi]
0x1000b401  mov     [ebp+var_214], eax
0x1000b407  xor     eax, eax
0x1000b409  mov     edx, [ebp+var_214]
0x1000b40f  mov     [ebp+Size], esi
0x1000b415  mov     [ebp+var_21C], eax
0x1000b41b  test    edx, edx
0x1000b41d  jle     loc_1000B4BC
0x1000b423  test    esi, esi
0x1000b425  jz      loc_1000B4E9
0x1000b42b  cmp     word ptr [esi+4], 17h
0x1000b430  jnz     loc_1000B4E9
0x1000b436  mov     al, [esi+9]
0x1000b439  and     al, 0F3h
0x1000b43b  cmp     al, 3
0x1000b43d  jnz     short loc_1000B49F
0x1000b43f  movzx   ebx, byte ptr [esi+8]
0x1000b443  add     esi, 0Ah
0x1000b446  mov     edx, [ebp+arg_4]
0x1000b449  sub     ebx, 4
0x1000b44c  jb      short loc_1000B461
0x1000b44e  mov     edi, edi
0x1000b450  mov     eax, [edx]
0x1000b452  cmp     eax, [esi]
0x1000b454  jnz     short loc_1000B466
0x1000b456  add     edx, 4
0x1000b459  add     esi, 4
0x1000b45c  sub     ebx, 4
0x1000b45f  jnb     short loc_1000B450
0x1000b461  cmp     ebx, 0FFFFFFFCh
0x1000b464  jz      short loc_1000B4D4
0x1000b466  mov     al, [edx]
0x1000b468  cmp     al, [esi]
0x1000b46a  jnz     short loc_1000B493
0x1000b46c  cmp     ebx, 0FFFFFFFDh
0x1000b46f  jz      short loc_1000B4D4
0x1000b471  mov     al, [edx+1]
0x1000b474  cmp     al, [esi+1]
0x1000b477  jnz     short loc_1000B493
0x1000b479  cmp     ebx, 0FFFFFFFEh
0x1000b47c  jz      short loc_1000B4D4
0x1000b47e  mov     al, [edx+2]
0x1000b481  cmp     al, [esi+2]
0x1000b484  jnz     short loc_1000B493
0x1000b486  cmp     ebx, 0FFFFFFFFh
0x1000b489  jz      short loc_1000B4D4
0x1000b48b  mov     al, [edx+3]
0x1000b48e  cmp     al, [esi+3]
0x1000b491  jz      short loc_1000B4D4
0x1000b493  mov     edx, [ebp+var_214]
0x1000b499  mov     esi, [ebp+Size]
0x1000b49f  mov     eax, [ebp+var_21C]
0x1000b4a5  mov     esi, [esi]
0x1000b4a7  inc     eax
0x1000b4a8  mov     [ebp+Size], esi
0x1000b4ae  mov     [ebp+var_21C], eax
0x1000b4b4  cmp     eax, edx
0x1000b4b6  jl      loc_1000B423
0x1000b4bc  cmp     eax, edx
0x1000b4be  jnz     short loc_1000B501
0x1000b4c0  inc     edx
0x1000b4c1  mov     [ebp+var_214], edx
0x1000b4c7  lea     edx, [eax+1]
0x1000b4ca  mov     [ebp+var_22C], edx
0x1000b4d0  xor     eax, eax
0x1000b4d2  jmp     short loc_1000B51A
0x1000b4d4  mov     edx, [ebp+var_21C]
0x1000b4da  xor     edi, edi
0x1000b4dc  inc     edx
0x1000b4dd  xor     esi, esi
0x1000b4df  mov     [ebp+var_22C], edx
0x1000b4e5  xor     eax, eax
0x1000b4e7  jmp     short loc_1000B514
0x1000b4e9  mov     eax, 0FFFFFFF6h
0x1000b4ee  pop     edi
0x1000b4ef  pop     esi
0x1000b4f0  pop     ebx
0x1000b4f1  mov     ecx, [ebp+var_8]
0x1000b4f4  xor     ecx, ebp; StackCookie
0x1000b4f6  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000b4fb  mov     esp, ebp
0x1000b4fd  pop     ebp
0x1000b4fe  retn    1Ch
0x1000b501  mov     esi, [ebp+var_214]
0x1000b507  xor     eax, eax
0x1000b509  mov     [ebp+var_214], esi
0x1000b50f  xor     esi, esi
0x1000b511  lea     edx, [eax+1]
0x1000b514  mov     [ebp+Size], esi
0x1000b51a  mov     [ebp+var_21C], eax
0x1000b520  cmp     word ptr [ecx+4], 18h
0x1000b525  jnz     short loc_1000B530
0x1000b527  test    eax, eax
0x1000b529  jz      short loc_1000B541
0x1000b52b  sub     eax, 1
0x1000b52e  jz      short loc_1000B554
0x1000b530  mov     ecx, [ecx]
0x1000b532  test    ecx, ecx
0x1000b534  jnz     short loc_1000B520
0x1000b536  mov     [ebp+var_22C], edx
0x1000b53c  jmp     loc_1000B5FC
0x1000b541  mov     eax, ecx
0x1000b543  cmp     word ptr [ecx+4], 18h
0x1000b548  jnz     short loc_1000B552
0x1000b54a  mov     eax, ecx
0x1000b54c  mov     ecx, [ecx]
0x1000b54e  test    ecx, ecx
0x1000b550  jnz     short loc_1000B543
0x1000b552  mov     ecx, eax
0x1000b554  mov     eax, [ecx]
0x1000b556  mov     [ebp+var_21C], eax
0x1000b55c  jmp     loc_1000B602
0x1000b561  mov     eax, ecx
0x1000b563  mov     edx, 1
0x1000b568  test    eax, eax
0x1000b56a  jz      short loc_1000B5A7
0x1000b56c  mov     esi, 9Ch
0x1000b571  cmp     [eax+4], si
0x1000b575  jnz     short loc_1000B580
0x1000b577  test    edx, edx
0x1000b579  jz      short loc_1000B58F
0x1000b57b  sub     edx, 1
0x1000b57e  jz      short loc_1000B5A1
0x1000b580  mov     eax, [eax]
0x1000b582  test    eax, eax
0x1000b584  jnz     short loc_1000B571
0x1000b586  mov     eax, 1
0x1000b58b  xor     edi, edi
0x1000b58d  jmp     short loc_1000B5B2
0x1000b58f  mov     edx, eax
0x1000b591  cmp     [eax+4], si
0x1000b595  jnz     short loc_1000B59F
0x1000b597  mov     edx, eax
0x1000b599  mov     eax, [eax]
0x1000b59b  test    eax, eax
0x1000b59d  jnz     short loc_1000B591
0x1000b59f  mov     eax, edx
0x1000b5a1  mov     edi, [eax]
0x1000b5a3  test    edi, edi
0x1000b5a5  jnz     short loc_1000B5E3
0x1000b5a7  xor     edi, edi
0x1000b5a9  mov     eax, 1
0x1000b5ae  test    ecx, ecx
0x1000b5b0  jz      short loc_1000B5E3
0x1000b5b2  cmp     word ptr [ecx+4], 3Dh ; '='
0x1000b5b7  jnz     short loc_1000B5C2
0x1000b5b9  test    eax, eax
0x1000b5bb  jz      short loc_1000B5CA
0x1000b5bd  sub     eax, 1
0x1000b5c0  jz      short loc_1000B5E1
0x1000b5c2  mov     ecx, [ecx]
0x1000b5c4  test    ecx, ecx
0x1000b5c6  jnz     short loc_1000B5B2
0x1000b5c8  jmp     short loc_1000B5E3
0x1000b5ca  mov     eax, ecx
0x1000b5cc  nop     dword ptr [eax+00h]
0x1000b5d0  cmp     word ptr [ecx+4], 3Dh ; '='
0x1000b5d5  jnz     short loc_1000B5DF
0x1000b5d7  mov     eax, ecx
0x1000b5d9  mov     ecx, [ecx]
0x1000b5db  test    ecx, ecx
0x1000b5dd  jnz     short loc_1000B5D0
0x1000b5df  mov     ecx, eax
0x1000b5e1  mov     edi, ecx
0x1000b5e3  mov     eax, 1
0x1000b5e8  mov     [ebp+var_21C], edi
0x1000b5ee  mov     [ebp+var_22C], eax
0x1000b5f4  mov     esi, edi
0x1000b5f6  mov     [ebp+var_214], eax
0x1000b5fc  mov     [ebp+Size], esi
0x1000b602  test    edi, edi
0x1000b604  jz      loc_1000B6D5
0x1000b60a  mov     esi, _g_cbCurrentSize
0x1000b610  mov     eax, 2
0x1000b615  mov     ebx, _pExcelRecordBuffer
0x1000b61b  cmp     esi, eax
0x1000b61d  mov     [ebp+var_230], 16h
0x1000b627  cmovle  eax, esi
0x1000b62a  mov     [ebp+var_228], 2
0x1000b634  push    eax; Size
0x1000b635  push    0; Val
0x1000b637  push    ebx; void *
0x1000b638  call    _memset
0x1000b63d  mov     eax, [ebp+var_214]
0x1000b643  add     esp, 0Ch
0x1000b646  cmp     esi, 2
0x1000b649  jb      short loc_1000B64E
0x1000b64b  mov     [ebx], ax
0x1000b64e  cmp     eax, 1
0x1000b651  jnz     short loc_1000B6BB
0x1000b653  lea     ecx, [eax+0Ch]
0x1000b656  call    _MemAllocate@4; MemAllocate(x)
0x1000b65b  mov     edx, eax
0x1000b65d  test    edx, edx
0x1000b65f  jnz     short loc_1000B66C
0x1000b661  mov     ebx, [ebp+var_218]
0x1000b667  lea     eax, [edx-2]
0x1000b66a  jmp     short loc_1000B6AB
0x1000b66c  mov     dword ptr [edx+4], 20016h
0x1000b673  xor     ecx, ecx
0x1000b675  mov     ax, [ebx]
0x1000b678  mov     ebx, [ebp+var_218]
0x1000b67e  mov     [edx+8], ax
0x1000b682  mov     eax, [ebx+4]
0x1000b685  test    eax, eax
0x1000b687  jz      short loc_1000B69C
0x1000b689  nop     dword ptr [eax+00000000h]
0x1000b690  cmp     eax, edi
0x1000b692  jz      short loc_1000B69C
0x1000b694  mov     ecx, eax
0x1000b696  mov     eax, [eax]
0x1000b698  test    eax, eax
0x1000b69a  jnz     short loc_1000B690
0x1000b69c  mov     [edx], eax
0x1000b69e  test    ecx, ecx
0x1000b6a0  jnz     short loc_1000B6A7
0x1000b6a2  mov     [ebx+4], edx
0x1000b6a5  jmp     short loc_1000B6A9
0x1000b6a7  mov     [ecx], edx
0x1000b6a9  xor     eax, eax
0x1000b6ab  test    eax, eax
0x1000b6ad  jnz     loc_1000BB81
0x1000b6b3  mov     esi, [ebp+Size]
0x1000b6b9  jmp     short loc_1000B6F3
0x1000b6bb  movsx   eax, word ptr [edi+6]
0x1000b6bf  push    eax; Size
0x1000b6c0  lea     eax, [edi+8]
0x1000b6c3  push    ebx; Src
0x1000b6c4  push    eax; void *
0x1000b6c5  call    _memcpy
0x1000b6ca  mov     esi, [ebp+Size]
0x1000b6d0  add     esp, 0Ch
0x1000b6d3  jmp     short loc_1000B6ED
0x1000b6d5  mov     eax, [ebp+Src]
0x1000b6db  mov     [ebp+var_228], eax
0x1000b6e1  mov     eax, [ebp+Src]
0x1000b6e7  mov     [ebp+var_230], eax
0x1000b6ed  mov     ebx, [ebp+var_218]
0x1000b6f3  test    esi, esi
  ... truncated ...
```
