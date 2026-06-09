# AddV8Name

- ea: `0x1000ab50`
- end: `0x1000b341`
- name: `AddV8Name`
- size: `2033`
- prototype: `int __fastcall(int, _DWORD **, int, const unsigned __int16 *, int, int, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1000b350`

## callees

- `0x1000aae0`
- `0x1000ab50`
- `0x1000e440`
- `0x1002580a`
- `0x10025ab7`
- `0x10035510`
- `0x10035b40`
- `0x10035f40`
- `0x1003669c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1000b1e9`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1000b1e9`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1000b1f0`
- `mswstr10!__imp__DBCompareStringW@24` at `0x1000b1f0`

## pseudocode

```c
int __fastcall AddV8Name(int a1, _DWORD **a2, int a3, const unsigned __int16 *a4, int a5, int a6, int a7, int a8)
{
  __int16 *v10; // edi
  _WORD *v11; // eax
  int *v12; // eax
  int result; // eax
  _DWORD *v14; // ecx
  _DWORD *v15; // esi
  _WORD *v16; // edi
  __int16 v17; // cx
  _DWORD *m; // eax
  int v19; // eax
  _DWORD *v20; // edx
  _DWORD *v21; // ecx
  _DWORD *n; // eax
  int *v23; // esi
  _DWORD *v24; // eax
  _DWORD *v25; // esi
  size_t v26; // ebx
  int v27; // eax
  _DWORD *v28; // edi
  int v29; // esi
  int v30; // eax
  int v31; // ecx
  __int16 *v32; // edx
  _WORD *v33; // eax
  _WORD *v34; // esi
  _WORD *v35; // edx
  int *v36; // esi
  _DWORD *v37; // eax
  _DWORD *v38; // esi
  _WORD *v39; // edi
  __int16 v40; // cx
  _DWORD *i; // eax
  int v42; // eax
  _DWORD *v43; // edx
  _DWORD *v44; // ecx
  _DWORD *j; // eax
  unsigned int v46; // ebx
  int v47; // edi
  int v48; // eax
  _BYTE *v49; // esi
  const unsigned __int16 *v50; // ecx
  _BYTE *v51; // edx
  char v52; // al
  size_t v53; // esi
  const unsigned __int16 *v54; // edi
  signed int v55; // eax
  _DWORD **v56; // edi
  int v57; // eax
  int *v58; // esi
  int *v59; // eax
  int *v60; // ecx
  int v61; // ecx
  __int16 v62; // bx
  _WORD *v63; // ecx
  WCHAR *v64; // eax
  int v65; // edi
  _WORD *v66; // eax
  LCID UserDefaultLCID; // eax
  _DWORD *v68; // edx
  _DWORD *v69; // esi
  int v70; // eax
  _DWORD *v71; // edi
  _DWORD *v72; // ecx
  _DWORD *k; // eax
  int v74; // [esp-8h] [ebp-240h]
  int v75; // [esp-4h] [ebp-23Ch]
  _WORD *v76; // [esp+Ch] [ebp-22Ch]
  __int16 v77; // [esp+10h] [ebp-228h]
  int v78; // [esp+18h] [ebp-220h]
  int v80; // [esp+20h] [ebp-218h]
  int v81; // [esp+20h] [ebp-218h]
  char v82; // [esp+27h] [ebp-211h]
  void *Src; // [esp+28h] [ebp-210h]
  void *Srca; // [esp+28h] [ebp-210h]
  void *Srcb; // [esp+28h] [ebp-210h]
  void *Srcc; // [esp+28h] [ebp-210h]
  __int16 Srcd; // [esp+28h] [ebp-210h]
  void *Srce; // [esp+28h] [ebp-210h]
  int v89; // [esp+2Ch] [ebp-20Ch]
  _BYTE v90[516]; // [esp+30h] [ebp-208h] BYREF

  v89 = a1;
  v10 = *(__int16 **)(a1 + 80);
  if ( v10 )
  {
    v29 = *v10;
    v30 = 0;
    v80 = 1;
    v78 = 0;
    if ( v29 <= 0 )
    {
LABEL_39:
      if ( v30 == v29 )
      {
        Srcb = (void *)(6 * *v10 + 2);
        v33 = (_WORD *)MemAllocate(6 * *v10 + 8);
        v34 = v33;
        if ( !v33 )
          return -2;
        memcpy(v33, v10, (size_t)Srcb);
        ++*v34;
        if ( v80 )
          *(_DWORD *)(v89 + 76) = v78;
        v35 = &v34[3 * v78];
        v35[1] = *(_WORD *)(v89 + 76);
        v35[2] = a5;
        v35[3] = a5;
        MemFree(v10);
        *(_DWORD *)(v89 + 80) = v34;
        if ( v80 )
        {
          v36 = a2[1];
          if ( !v36 )
            return -10;
          while ( *((_WORD *)v36 + 2) != 23 )
          {
            v36 = (int *)*v36;
            if ( !v36 )
              return -10;
          }
          v37 = v36;
          do
          {
            if ( *((_WORD *)v36 + 2) != 23 )
              break;
            v37 = v36;
            v36 = (int *)*v36;
          }
          while ( v36 );
          v38 = v37;
          v39 = pExcelRecordBuffer;
          v77 = 4;
          v40 = 0;
          v89 = 262574;
          *(_DWORD *)pExcelRecordBuffer = 67174400;
          for ( i = *a2; i; ++v40 )
            i = (_DWORD *)*i;
          *v39 = v40;
          v42 = MemAllocate(15);
          v43 = (_DWORD *)v42;
          if ( !v42 )
            return -2;
          v44 = 0;
          *(_DWORD *)(v42 + 4) = v89;
          *(_DWORD *)(v42 + 8) = *(_DWORD *)v39;
          for ( j = a2[1]; j; j = (_DWORD *)*j )
          {
            if ( j == v38 )
              break;
            v44 = j;
          }
          *v43 = j;
          if ( v44 )
            *v44 = v43;
          else
            a2[1] = v43;
LABEL_61:
          Srcc = (void *)g_cbCurrentSize;
          v76 = pExcelRecordBuffer;
          v46 = wcslen(a4);
          v47 = 2 * v46;
          v48 = MemAllocate(2 * v46 + 2);
          v81 = v48;
          if ( v48 )
          {
            v49 = (_BYTE *)v48;
            v50 = a4;
            v51 = (char *)a4 + 1;
            if ( *a4 )
            {
              while ( !*v51 )
              {
                v52 = *(_BYTE *)v50;
                --v47;
                ++v50;
                *v49++ = v52;
                v51 += 2;
                if ( !*v50 )
                {
                  v48 = v81;
                  goto LABEL_66;
                }
              }
              v54 = a4;
              v53 = 2 * v46;
              v82 = 1;
            }
            else
            {
LABEL_66:
              v53 = v47;
              v82 = 0;
              v54 = (const unsigned __int16 *)v48;
            }
            LOWORD(v89) = 24;
            v77 = v53 + 26;
            HIWORD(v89) = v53 + 26;
            v55 = (__int16)(v53 + 26);
            if ( v55 >= (int)Srcc )
              v55 = (signed int)Srcc;
            memset(v76, 0, v55);
            if ( (int)Srcc >= (int)(v53 + 25) )
            {
              *((_BYTE *)v76 + 3) = v46;
              *v76 = 0;
              v76[2] = 11;
              v76[4] = 0;
              *((_BYTE *)v76 + 14) = v82;
              memcpy((char *)v76 + 15, v54, v53);
              *(_WORD *)((char *)v76 + v53 + 16) = v78;
              *(_WORD *)((char *)v76 + v53 + 18) = a7;
              *(_WORD *)((char *)v76 + v53 + 20) = a8;
              *(_WORD *)((char *)v76 + v53 + 22) = HIWORD(a7);
              *((_BYTE *)v76 + v53 + 15) = 59;
              *(_WORD *)((char *)v76 + v53 + 24) = HIWORD(a8);
            }
            MemFree(v81);
          }
          v56 = a2;
          v57 = 1;
          v58 = a2[1];
          if ( v58 )
          {
            while ( *((_WORD *)v58 + 2) != 24 || --v57 )
            {
              v58 = (int *)*v58;
              if ( !v58 )
                goto LABEL_76;
            }
            while ( *((_WORD *)v58 + 2) == 24 )
            {
              v62 = *((_WORD *)v58 + 4);
              Srcd = *((_WORD *)v58 + 8);
              ExcelExtractString(
                (int)v56[9],
                (UINT)v56[11],
                (__m128i *)&ExcelRecordTextBuffer,
                512,
                (LPCCH)v58 + 22,
                *((unsigned __int8 *)v58 + 11));
              if ( (v62 & 0x20) != 0 && NameLocalizer )
              {
                NameLocalizer(NameLocalizer, &ExcelRecordTextBuffer, v90, 256);
              }
              else
              {
                memset(v90, 0, 0x200u);
                v63 = v90;
                v64 = &ExcelRecordTextBuffer;
                v65 = 256;
                do
                {
                  if ( !*v64 )
                    break;
                  *v63++ = *v64++;
                  --v65;
                }
                while ( v65 );
                v66 = v63 - 1;
                if ( v65 )
                  v66 = v63;
                *v66 = 0;
              }
              UserDefaultLCID = GetUserDefaultLCID();
              if ( DBCompareStringW(UserDefaultLCID, 196609, a4, -1, v90, -1) == 2 && !Srcd )
              {
                if ( *((_WORD *)v58 + 2) != 24 )
                  break;
                memcpy(v58 + 2, pExcelRecordBuffer, *((__int16 *)v58 + 3));
                return 0;
              }
              v58 = (int *)*v58;
              if ( !v58 )
                break;
              v56 = a2;
            }
          }
LABEL_76:
          v59 = a2[1];
          v60 = v59;
          if ( v59 )
          {
            do
            {
              if ( *((_WORD *)v60 + 2) == 24 )
              {
                v68 = v60;
                do
                {
                  if ( *((_WORD *)v60 + 2) != 24 )
                    break;
                  v68 = v60;
                  v60 = (int *)*v60;
                }
                while ( v60 );
                v69 = (_DWORD *)*v68;
                if ( !*v68 )
                  goto LABEL_101;
                goto LABEL_107;
              }
              v60 = (int *)*v60;
            }
            while ( v60 );
            v61 = 1;
LABEL_102:
            while ( *((_WORD *)v59 + 2) != 23 || --v61 )
            {
              v59 = (int *)*v59;
              if ( !v59 )
                return -10;
            }
            v69 = (_DWORD *)*v59;
            if ( !*v59 )
              return -10;
LABEL_107:
            Srce = pExcelRecordBuffer;
            v70 = MemAllocate(v77 + 11);
            v71 = (_DWORD *)v70;
            if ( !v70 )
              return -2;
            *(_DWORD *)(v70 + 4) = v89;
            memcpy((void *)(v70 + 8), Srce, v77);
            v72 = 0;
            for ( k = a2[1]; k; k = (_DWORD *)*k )
            {
              if ( k == v69 )
                break;
              v72 = k;
            }
            *v71 = k;
            if ( v72 )
              *v72 = v71;
            else
              a2[1] = v71;
            return 0;
          }
LABEL_101:
          v61 = 1;
          if ( v59 )
            goto LABEL_102;
          return -10;
        }
      }
    }
    else
    {
      Srca = *(void **)(a1 + 76);
      while ( 1 )
      {
        v31 = 0;
        v32 = &v10[3 * v30];
        if ( (void *)v32[1] != Srca )
          v31 = v80;
        v80 = v31;
        if ( v32[2] == a5 && v32[3] == a5 )
          break;
        v30 = v78 + 1;
        v78 = v30;
        if ( v30 >= v29 )
          goto LABEL_39;
      }
    }
    v77 = HIWORD(v89);
    goto LABEL_61;
  }
  v11 = (_WORD *)MemAllocate(8);
  *(_DWORD *)(a1 + 80) = v11;
  if ( !v11 )
    return -2;
  LOWORD(v78) = 0;
  *v11 = 1;
  *(_WORD *)(*(_DWORD *)(a1 + 80) + 2) = 0;
  *(_WORD *)(*(_DWORD *)(a1 + 80) + 4) = a5;
  *(_WORD *)(*(_DWORD *)(a1 + 80) + 6) = a5;
  v12 = a2[1];
  if ( !v12 )
    return -10;
  while ( *((_WORD *)v12 + 2) != 133 )
  {
    v12 = (int *)*v12;
    if ( !v12 )
      return -10;
  }
  v14 = v12;
  do
  {
    if ( *((_WORD *)v12 + 2) != 133 )
      break;
    v14 = v12;
    v12 = (int *)*v12;
  }
  while ( v12 );
  v15 = (_DWORD *)*v14;
  if ( !*v14 )
    return -10;
  v16 = pExcelRecordBuffer;
  v17 = 0;
  v89 = 262574;
  *(_DWORD *)pExcelRecordBuffer = 67174400;
  for ( m = *a2; m; ++v17 )
    m = (_DWORD *)*m;
  *v16 = v17;
  v19 = MemAllocate(15);
  v20 = (_DWORD *)v19;
  if ( !v19 )
    return -2;
  v21 = 0;
  *(_DWORD *)(v19 + 4) = v89;
  *(_DWORD *)(v19 + 8) = *(_DWORD *)v16;
  for ( n = a2[1]; n; n = (_DWORD *)*n )
  {
    if ( n == v15 )
      break;
    v21 = n;
  }
  *v20 = n;
  if ( v21 )
    *v21 = v20;
  else
    a2[1] = v20;
  *(_DWORD *)(a1 + 76) = 0;
  v23 = a2[1];
  if ( !v23 )
    return -10;
  while ( *((_WORD *)v23 + 2) != 430 )
  {
    v23 = (int *)*v23;
    if ( !v23 )
      return -10;
  }
  v24 = v23;
  do
  {
    if ( *((_WORD *)v23 + 2) != 430 )
      break;
    v24 = v23;
    v23 = (int *)*v23;
  }
  while ( v23 );
  v25 = v24;
  result = BuildXTIRecord(v74, v75);
  if ( !result )
  {
    Src = pExcelRecordBuffer;
    v26 = SHIWORD(v89);
    v77 = HIWORD(v89);
    v27 = MemAllocate(SHIWORD(v89) + 11);
    v28 = (_DWORD *)v27;
    if ( v27 )
    {
      *(_DWORD *)(v27 + 4) = v89;
      memcpy((void *)(v27 + 8), Src, v26);
      *v28 = *v25;
      *v25 = v28;
      goto LABEL_61;
    }
    return -2;
  }
  return result;
}

```

## disassembly

```asm
0x1000ab50  mov     edi, edi
0x1000ab52  push    ebp
0x1000ab53  mov     ebp, esp
0x1000ab55  sub     esp, 22Ch
0x1000ab5b  mov     eax, ___security_cookie
0x1000ab60  xor     eax, ebp
0x1000ab62  mov     [ebp+var_4], eax
0x1000ab65  mov     eax, [ebp+arg_4]
0x1000ab68  push    ebx
0x1000ab69  mov     ebx, ecx
0x1000ab6b  mov     [ebp+var_224], eax
0x1000ab71  push    esi
0x1000ab72  push    edi
0x1000ab73  mov     esi, edx
0x1000ab75  mov     [ebp+var_20C], ebx
0x1000ab7b  mov     edi, [ebx+50h]
0x1000ab7e  mov     [ebp+var_21C], esi
0x1000ab84  test    edi, edi
0x1000ab86  jnz     loc_1000AD64
0x1000ab8c  lea     ecx, [edi+8]
0x1000ab8f  call    _MemAllocate@4; MemAllocate(x)
0x1000ab94  mov     [ebx+50h], eax
0x1000ab97  test    eax, eax
0x1000ab99  jz      loc_1000AC5A
0x1000ab9f  mov     ecx, 1
0x1000aba4  mov     [ebp+var_220], edi
0x1000abaa  mov     [eax], cx
0x1000abad  xor     ecx, ecx
0x1000abaf  mov     eax, [ebx+50h]
0x1000abb2  mov     [eax+2], cx
0x1000abb6  mov     eax, [ebx+50h]
0x1000abb9  movzx   ecx, word ptr [ebp+arg_8]
0x1000abbd  mov     [eax+4], cx
0x1000abc1  mov     eax, [ebx+50h]
0x1000abc4  mov     [eax+6], cx
0x1000abc8  xor     ecx, ecx
0x1000abca  mov     eax, [esi+4]
0x1000abcd  test    eax, eax
0x1000abcf  jz      short loc_1000ABEB
0x1000abd1  mov     edx, 85h
0x1000abd6  cmp     [eax+4], dx
0x1000abda  jnz     short loc_1000ABE5
0x1000abdc  test    ecx, ecx
0x1000abde  jz      short loc_1000AC03
0x1000abe0  sub     ecx, 1
0x1000abe3  jz      short loc_1000AC15
0x1000abe5  mov     eax, [eax]
0x1000abe7  test    eax, eax
0x1000abe9  jnz     short loc_1000ABD6
0x1000abeb  mov     eax, 0FFFFFFF6h
0x1000abf0  pop     edi
0x1000abf1  pop     esi
0x1000abf2  pop     ebx
0x1000abf3  mov     ecx, [ebp+var_4]
0x1000abf6  xor     ecx, ebp; StackCookie
0x1000abf8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000abfd  mov     esp, ebp
0x1000abff  pop     ebp
0x1000ac00  retn    18h
0x1000ac03  mov     ecx, eax
0x1000ac05  cmp     [eax+4], dx
0x1000ac09  jnz     short loc_1000AC13
0x1000ac0b  mov     ecx, eax
0x1000ac0d  mov     eax, [eax]
0x1000ac0f  test    eax, eax
0x1000ac11  jnz     short loc_1000AC05
0x1000ac13  mov     eax, ecx
0x1000ac15  mov     esi, [eax]
0x1000ac17  test    esi, esi
0x1000ac19  jz      short loc_1000ABEB
0x1000ac1b  mov     edi, _pExcelRecordBuffer
0x1000ac21  xor     ecx, ecx
0x1000ac23  mov     eax, [ebp+var_21C]
0x1000ac29  mov     [ebp+var_20C], 401AEh
0x1000ac33  mov     dword ptr [edi], 4010000h
0x1000ac39  mov     eax, [eax]
0x1000ac3b  test    eax, eax
0x1000ac3d  jz      short loc_1000AC47
0x1000ac3f  nop
0x1000ac40  mov     eax, [eax]
0x1000ac42  inc     ecx
0x1000ac43  test    eax, eax
0x1000ac45  jnz     short loc_1000AC40
0x1000ac47  mov     [edi], cx
0x1000ac4a  mov     ecx, 0Fh
0x1000ac4f  call    _MemAllocate@4; MemAllocate(x)
0x1000ac54  mov     edx, eax
0x1000ac56  test    edx, edx
0x1000ac58  jnz     short loc_1000AC72
0x1000ac5a  mov     eax, 0FFFFFFFEh
0x1000ac5f  pop     edi
0x1000ac60  pop     esi
0x1000ac61  pop     ebx
0x1000ac62  mov     ecx, [ebp+var_4]
0x1000ac65  xor     ecx, ebp; StackCookie
0x1000ac67  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000ac6c  mov     esp, ebp
0x1000ac6e  pop     ebp
0x1000ac6f  retn    18h
0x1000ac72  mov     eax, [ebp+var_20C]
0x1000ac78  xor     ecx, ecx
0x1000ac7a  mov     [edx+4], eax
0x1000ac7d  mov     eax, [edi]
0x1000ac7f  mov     edi, [ebp+var_21C]
0x1000ac85  mov     [edx+8], eax
0x1000ac88  mov     eax, [edi+4]
0x1000ac8b  test    eax, eax
0x1000ac8d  jz      short loc_1000AC9C
0x1000ac8f  nop
0x1000ac90  cmp     eax, esi
0x1000ac92  jz      short loc_1000AC9C
0x1000ac94  mov     ecx, eax
0x1000ac96  mov     eax, [eax]
0x1000ac98  test    eax, eax
0x1000ac9a  jnz     short loc_1000AC90
0x1000ac9c  mov     [edx], eax
0x1000ac9e  test    ecx, ecx
0x1000aca0  jnz     short loc_1000ACA7
0x1000aca2  mov     [edi+4], edx
0x1000aca5  jmp     short loc_1000ACA9
0x1000aca7  mov     [ecx], edx
0x1000aca9  mov     dword ptr [ebx+4Ch], 0
0x1000acb0  xor     eax, eax
0x1000acb2  mov     esi, [edi+4]
0x1000acb5  test    esi, esi
0x1000acb7  jz      loc_1000ABEB
0x1000acbd  mov     ecx, 1AEh
0x1000acc2  cmp     [esi+4], cx
0x1000acc6  jnz     short loc_1000ACD1
0x1000acc8  test    eax, eax
0x1000acca  jz      short loc_1000ACDC
0x1000accc  sub     eax, 1
0x1000accf  jz      short loc_1000ACF0
0x1000acd1  mov     esi, [esi]
0x1000acd3  test    esi, esi
0x1000acd5  jnz     short loc_1000ACC2
0x1000acd7  jmp     loc_1000ABEB
0x1000acdc  mov     eax, esi
0x1000acde  mov     edi, edi
0x1000ace0  cmp     [esi+4], cx
0x1000ace4  jnz     short loc_1000ACEE
0x1000ace6  mov     eax, esi
0x1000ace8  mov     esi, [esi]
0x1000acea  test    esi, esi
0x1000acec  jnz     short loc_1000ACE0
0x1000acee  mov     esi, eax
0x1000acf0  test    esi, esi
0x1000acf2  jz      loc_1000ABEB
0x1000acf8  sub     esp, 8
0x1000acfb  lea     edx, [ebp+var_20C]
0x1000ad01  mov     ecx, ebx
0x1000ad03  call    BuildXTIRecord
0x1000ad08  test    eax, eax
0x1000ad0a  jnz     loc_1000ABF0
0x1000ad10  mov     eax, _pExcelRecordBuffer
0x1000ad15  mov     [ebp+Src], eax
0x1000ad1b  mov     ax, word ptr [ebp+var_20C+2]
0x1000ad22  movsx   ebx, ax
0x1000ad25  mov     [ebp+var_228], eax
0x1000ad2b  lea     ecx, [ebx+0Bh]
0x1000ad2e  call    _MemAllocate@4; MemAllocate(x)
0x1000ad33  mov     edi, eax
0x1000ad35  test    edi, edi
0x1000ad37  jz      loc_1000AC5A
0x1000ad3d  mov     eax, [ebp+var_20C]
0x1000ad43  push    ebx; Size
0x1000ad44  push    [ebp+Src]; Src
0x1000ad4a  mov     [edi+4], eax
0x1000ad4d  lea     eax, [edi+8]
0x1000ad50  push    eax; void *
0x1000ad51  call    _memcpy
0x1000ad56  mov     eax, [esi]
0x1000ad58  add     esp, 0Ch
0x1000ad5b  mov     [edi], eax
0x1000ad5d  mov     [esi], edi
0x1000ad5f  jmp     loc_1000AF3F
0x1000ad64  movsx   esi, word ptr [edi]
0x1000ad67  xor     eax, eax
0x1000ad69  mov     ebx, [ebp+arg_8]
0x1000ad6c  mov     [ebp+var_218], 1
0x1000ad76  mov     [ebp+var_220], eax
0x1000ad7c  test    esi, esi
0x1000ad7e  jle     short loc_1000ADD4
0x1000ad80  mov     ecx, [ecx+4Ch]
0x1000ad83  mov     [ebp+Src], ecx
0x1000ad89  nop     dword ptr [eax+00000000h]
0x1000ad90  lea     eax, [eax+eax*2]
0x1000ad93  xor     ecx, ecx
0x1000ad95  lea     edx, [edi+eax*2]
0x1000ad98  movsx   eax, word ptr [edx+2]
0x1000ad9c  cmp     eax, [ebp+Src]
0x1000ada2  movsx   eax, word ptr [edx+4]
0x1000ada6  cmovnz  ecx, [ebp+var_218]
0x1000adad  mov     [ebp+var_218], ecx
0x1000adb3  cmp     eax, ebx
0x1000adb5  jnz     short loc_1000ADC3
0x1000adb7  movsx   eax, word ptr [edx+6]
0x1000adbb  cmp     eax, ebx
0x1000adbd  jz      loc_1000AF32
0x1000adc3  mov     eax, [ebp+var_220]
0x1000adc9  inc     eax
0x1000adca  mov     [ebp+var_220], eax
0x1000add0  cmp     eax, esi
0x1000add2  jl      short loc_1000AD90
0x1000add4  cmp     eax, esi
0x1000add6  jnz     loc_1000AF32
0x1000addc  movsx   eax, word ptr [edi]
0x1000addf  lea     eax, [eax+eax*2]
0x1000ade2  lea     eax, ds:2[eax*2]
0x1000ade9  lea     ecx, [eax+6]
0x1000adec  mov     [ebp+Src], eax
0x1000adf2  call    _MemAllocate@4; MemAllocate(x)
0x1000adf7  mov     esi, eax
0x1000adf9  test    esi, esi
0x1000adfb  jz      loc_1000AC5A
0x1000ae01  push    [ebp+Src]; Size
0x1000ae07  push    edi; Src
0x1000ae08  push    esi; void *
0x1000ae09  call    _memcpy
0x1000ae0e  inc     word ptr [esi]
0x1000ae11  add     esp, 0Ch
0x1000ae14  cmp     [ebp+var_218], 0
0x1000ae1b  mov     eax, [ebp+var_220]
0x1000ae21  jz      short loc_1000AE2C
0x1000ae23  mov     ecx, [ebp+var_20C]
0x1000ae29  mov     [ecx+4Ch], eax
0x1000ae2c  lea     eax, [eax+eax*2]
0x1000ae2f  mov     ecx, edi
0x1000ae31  lea     edx, [esi+eax*2]
0x1000ae34  mov     eax, [ebp+var_20C]
0x1000ae3a  mov     ax, [eax+4Ch]
0x1000ae3e  mov     [edx+2], ax
0x1000ae42  movzx   eax, bx
0x1000ae45  mov     [edx+4], ax
0x1000ae49  mov     [edx+6], ax
0x1000ae4d  call    _MemFree@4; MemFree(x)
0x1000ae52  cmp     [ebp+var_218], 0
0x1000ae59  mov     eax, [ebp+var_20C]
0x1000ae5f  mov     [eax+50h], esi
0x1000ae62  jz      loc_1000AF32
0x1000ae68  mov     ebx, [ebp+var_21C]
0x1000ae6e  xor     eax, eax
0x1000ae70  mov     esi, [ebx+4]
0x1000ae73  test    esi, esi
0x1000ae75  jz      loc_1000ABEB
0x1000ae7b  nop     dword ptr [eax+eax+00h]
0x1000ae80  cmp     word ptr [esi+4], 17h
0x1000ae85  jnz     short loc_1000AE90
0x1000ae87  test    eax, eax
0x1000ae89  jz      short loc_1000AE9B
0x1000ae8b  sub     eax, 1
0x1000ae8e  jz      short loc_1000AEB1
0x1000ae90  mov     esi, [esi]
0x1000ae92  test    esi, esi
0x1000ae94  jnz     short loc_1000AE80
0x1000ae96  jmp     loc_1000ABEB
0x1000ae9b  mov     eax, esi
0x1000ae9d  nop     dword ptr [eax]
0x1000aea0  cmp     word ptr [esi+4], 17h
0x1000aea5  jnz     short loc_1000AEAF
0x1000aea7  mov     eax, esi
0x1000aea9  mov     esi, [esi]
0x1000aeab  test    esi, esi
0x1000aead  jnz     short loc_1000AEA0
0x1000aeaf  mov     esi, eax
0x1000aeb1  test    esi, esi
0x1000aeb3  jz      loc_1000ABEB
0x1000aeb9  mov     edi, _pExcelRecordBuffer
0x1000aebf  mov     eax, 4
0x1000aec4  mov     [ebp+var_228], eax
0x1000aeca  xor     ecx, ecx
0x1000aecc  mov     [ebp+var_20C], 401AEh
0x1000aed6  mov     dword ptr [edi], 4010000h
0x1000aedc  mov     eax, [ebx]
0x1000aede  test    eax, eax
0x1000aee0  jz      short loc_1000AEE9
0x1000aee2  mov     eax, [eax]
0x1000aee4  inc     ecx
0x1000aee5  test    eax, eax
0x1000aee7  jnz     short loc_1000AEE2
0x1000aee9  mov     [edi], cx
0x1000aeec  mov     ecx, 0Fh
0x1000aef1  call    _MemAllocate@4; MemAllocate(x)
0x1000aef6  mov     edx, eax
0x1000aef8  test    edx, edx
0x1000aefa  jz      loc_1000AC5A
0x1000af00  mov     eax, [ebp+var_20C]
0x1000af06  xor     ecx, ecx
0x1000af08  mov     [edx+4], eax
0x1000af0b  mov     eax, [edi]
0x1000af0d  mov     [edx+8], eax
0x1000af10  mov     eax, [ebx+4]
0x1000af13  test    eax, eax
0x1000af15  jz      short loc_1000AF23
0x1000af17  cmp     eax, esi
0x1000af19  jz      short loc_1000AF23
0x1000af1b  mov     ecx, eax
0x1000af1d  mov     eax, [eax]
0x1000af1f  test    eax, eax
0x1000af21  jnz     short loc_1000AF17
  ... truncated ...
```
