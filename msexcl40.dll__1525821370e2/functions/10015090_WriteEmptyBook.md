# WriteEmptyBook

- ea: `0x10015090`
- end: `0x100158bd`
- name: `WriteEmptyBook`
- size: `2093`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x100158d0`

## callees

- `0x100147f0`
- `0x10014c50`
- `0x10015090`
- `0x1002580a`
- `0x10025ab7`
- `0x1002611f`
- `0x10032cb3`
- `0x10035510`
- `0x10035530`
- `0x1003669c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x100150e1`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x100150f4`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x10015137`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1001514a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x100150e1`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x100150f4`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x10015137`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x1001514a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1001556f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1001556f`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x100150bd`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x10015114`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001516f`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x100150bd`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x10015114`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1001516f`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x100150c4`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x100150c4`

## pseudocode

```c
int __thiscall WriteEmptyBook(int this)
{
  LCID UserDefaultLCID; // eax
  unsigned int LocaleInfoW; // eax
  LCID v4; // eax
  unsigned int v5; // eax
  int v6; // eax
  LCID v7; // eax
  unsigned int v8; // eax
  WCHAR *v9; // esi
  int v10; // eax
  int v11; // edx
  unsigned __int16 *v12; // ecx
  unsigned __int16 *v13; // eax
  int v14; // eax
  int v15; // eax
  int result; // eax
  char *v17; // edi
  __int16 v18; // ax
  int v19; // ecx
  char *v20; // edi
  __int16 v21; // ax
  int v22; // ecx
  char *v23; // edi
  __int16 v24; // ax
  int v25; // esi
  int v26; // edx
  int *v27; // ecx
  int *v28; // eax
  int v29; // ecx
  int v30; // ecx
  bool v31; // zf
  void *v32; // edx
  char *v33; // esi
  unsigned __int16 *v34; // edx
  char *v35; // ecx
  __int16 v36; // ax
  UINT v37; // edx
  char *v38; // ecx
  __int16 v39; // ax
  void *v40; // eax
  __int16 v41; // ax
  __int16 v42; // cx
  unsigned __int16 v43; // ax
  _WORD *v44; // edi
  unsigned int v45; // esi
  void *v46; // eax
  _BYTE *v47; // ecx
  _BYTE *v48; // edi
  _BYTE *v49; // edx
  size_t v50; // eax
  __int16 v51; // di
  char v52; // al
  _WORD *v53; // ecx
  int v54; // edx
  int v55; // edi
  int v56; // esi
  __int16 v57; // ax
  int *v58; // ecx
  int v59; // esi
  int v60; // eax
  int *v61; // ecx
  int v62; // esi
  int v63; // edx
  int *v64; // ecx
  int v65; // [esp-14h] [ebp-6Ch]
  CHAR *v66; // [esp-10h] [ebp-68h]
  int v67; // [esp+Ch] [ebp-4Ch] BYREF
  void *v68; // [esp+10h] [ebp-48h]
  void *v69; // [esp+14h] [ebp-44h]
  void *Src; // [esp+18h] [ebp-40h]
  int v71; // [esp+1Ch] [ebp-3Ch]
  int v72; // [esp+20h] [ebp-38h]
  size_t Size; // [esp+24h] [ebp-34h]
  unsigned __int16 v74[8]; // [esp+28h] [ebp-30h] BYREF
  unsigned int v75; // [esp+38h] [ebp-20h]
  int v76; // [esp+3Ch] [ebp-1Ch]
  int v77; // [esp+40h] [ebp-18h]
  WCHAR LCData[8]; // [esp+44h] [ebp-14h] BYREF

  v68 = pExcelRecordBuffer;
  UserDefaultLCID = GetUserDefaultLCID();
  LocaleInfoW = GetLocaleInfoW(UserDefaultLCID, 0x1Bu, LCData, 8);
  if ( LocaleInfoW >= 8 )
    goto LABEL_104;
  LCData[LocaleInfoW] = 0;
  v76 = __o__wtoi(LCData) >= 3 ? 3 : __o__wtoi(LCData);
  v4 = GetUserDefaultLCID();
  v5 = JetGetLocaleInfoW(v4, 0x1Cu, LCData, 8);
  if ( v5 >= 8
    || ((LCData[v5] = 0, __o__wtoi(LCData) >= 15) ? (v6 = 15) : (v6 = __o__wtoi(LCData)),
        v77 = word_1000454C[v6],
        v7 = GetUserDefaultLCID(),
        v8 = JetGetLocaleInfoW(v7, 0x14u, LCData, 8),
        v8 >= 8) )
  {
LABEL_104:
    __report_rangecheckfailure();
  }
  v9 = LCData;
  LCData[v8] = 0;
  v10 = 2147483646;
  v11 = 8;
  v12 = v74;
  do
  {
    if ( !v10 )
      break;
    if ( !*v9 )
      break;
    *v12++ = *v9++;
    --v10;
    --v11;
  }
  while ( v11 );
  v13 = v12 - 1;
  if ( v11 )
    v13 = v12;
  *v13 = 0;
  v75 = 2 * wcslen(v74);
  v14 = *(_DWORD *)(this + 4);
  if ( v14 == 3 )
  {
    v15 = WriteStream(dword_1003A040, 62);
    if ( !v15 )
    {
      v17 = (char *)v68;
      v18 = *(_WORD *)(this + 28);
      v67 = 131138;
      *(_WORD *)v68 = v18;
      v15 = BFWriteFile(*(_DWORD *)(this + 20), (char *)&v67, 4u);
      if ( !v15 )
      {
        v15 = BFWriteFile(*(_DWORD *)(this + 20), v17, SHIWORD(v67));
        if ( !v15 )
        {
          v15 = WriteStream(dword_10039A80, 100);
          if ( !v15 )
          {
            *(_WORD *)v17 = *(_WORD *)(this + 32);
            *((_WORD *)v17 + 1) = *(_WORD *)(this + 32);
            v19 = *(_DWORD *)(this + 20);
            v67 = 262284;
            v15 = BFWriteFile(v19, (char *)&v67, 4u);
            if ( !v15 )
            {
              v15 = BFWriteFile(*(_DWORD *)(this + 20), v17, SHIWORD(v67));
              if ( !v15 )
                return WriteStream(dword_100394B0, 1077);
            }
          }
        }
      }
    }
    goto LABEL_18;
  }
  if ( v14 == 4 )
  {
    v15 = WriteStream(dword_1003A520, 62);
    if ( !v15 )
    {
      v20 = (char *)v68;
      v21 = *(_WORD *)(this + 28);
      v67 = 131138;
      *(_WORD *)v68 = v21;
      v15 = BFWriteFile(*(_DWORD *)(this + 20), (char *)&v67, 4u);
      if ( !v15 )
      {
        v15 = BFWriteFile(*(_DWORD *)(this + 20), v20, SHIWORD(v67));
        if ( !v15 )
        {
          v15 = WriteStream(dword_1003A560, 92);
          if ( !v15 )
          {
            *(_WORD *)v20 = *(_WORD *)(this + 32);
            *((_WORD *)v20 + 1) = *(_WORD *)(this + 32);
            v22 = *(_DWORD *)(this + 20);
            v67 = 262284;
            v15 = BFWriteFile(v22, (char *)&v67, 4u);
            if ( !v15 )
            {
              v15 = BFWriteFile(*(_DWORD *)(this + 20), v20, SHIWORD(v67));
              if ( !v15 )
                return WriteStream(dword_10039AF0, 1350);
            }
          }
        }
      }
    }
    goto LABEL_18;
  }
  if ( v14 < 5 )
    return 0;
  if ( v14 == 5 )
  {
    v15 = WriteStream(&unk_1003A260, 70);
    if ( v15 )
      goto LABEL_18;
    v23 = (char *)v68;
    v24 = *(_WORD *)(this + 28);
    v67 = 131138;
    *(_WORD *)v68 = v24;
    v25 = *(_DWORD *)(this + 40);
    if ( v25 )
    {
      v26 = MemAllocate(13);
      if ( !v26 )
        return -2;
      *(_DWORD *)(v26 + 4) = v67;
      *(_WORD *)(v26 + 8) = *(_WORD *)v23;
      v27 = *(int **)(v25 + 4);
      if ( v27 )
      {
        while ( *v27 )
          v27 = (int *)*v27;
        *v27 = v26;
        v28 = dword_100393E0;
        v29 = 196;
      }
      else
      {
        *(_DWORD *)(v25 + 4) = v26;
        v28 = dword_100393E0;
        v29 = 196;
      }
    }
    else
    {
      v15 = BFWriteFile(*(_DWORD *)(this + 20), (char *)&v67, 4u);
      if ( v15 )
        goto LABEL_18;
      v15 = BFWriteFile(*(_DWORD *)(this + 20), v23, SHIWORD(v67));
      if ( v15 )
        goto LABEL_18;
      v28 = dword_100393E0;
      v29 = 196;
    }
  }
  else
  {
    v23 = (char *)v68;
    v28 = (int *)&unk_100398F0;
    v29 = 399;
  }
  result = WriteStream(v28, v29);
  if ( result )
    return result;
  v30 = 0;
  v71 = 0;
  do
  {
    v31 = *(_DWORD *)(this + 4) == 5;
    v32 = *(&off_10038900 + 88 * v76 + 8 * v77 + v30);
    v69 = v32;
    if ( v31 )
    {
      v33 = (char *)MemAllocate(512);
      if ( !v33 )
        return -2;
      v34 = (unsigned __int16 *)v69;
      v35 = (char *)v69;
      v69 = (char *)v69 + 2;
      do
      {
        v36 = *(_WORD *)v35;
        v35 += 2;
      }
      while ( v36 );
      AdjustFormatString(v74, v34, 2 * ((v35 - (_BYTE *)v69) >> 1), v33);
      v37 = *(_DWORD *)(this + 24);
      v38 = v33;
      v69 = v33 + 2;
      do
      {
        v39 = *(_WORD *)v38;
        v38 += 2;
      }
      while ( v39 );
      v66 = v23 + 3;
      v65 = (v38 - (_BYTE *)v69) >> 1;
      if ( v37 == 1200 )
        v40 = (void *)WideCharToMultiByte(0, 0, (LPCWCH)v33, v65, v66, 8221, 0, 0);
      else
        v40 = (void *)WideCharToMultiByte(v37, 0, (LPCWCH)v33, v65, v66, 8221, 0, 0);
      Src = v40;
      MemFree(v33);
      LOWORD(v67) = 1054;
      *(_WORD *)v23 = word_10004570[v71];
      v41 = (__int16)Src;
      v23[2] = (char)Src;
      HIWORD(v67) = v41 + 3;
      v42 = v41 + 3;
      v43 = v41 + 3;
    }
    else
    {
      v44 = v23 + 5;
      Src = v44;
      AdjustFormatString(v74, (unsigned __int16 *)v32, 2 * wcslen((const unsigned __int16 *)v32), v44);
      v45 = wcslen(v44);
      Size = 2 * v45;
      v72 = 2 * v45;
      v46 = (void *)MemAllocate(2 * v45 + 2);
      v69 = v46;
      if ( !v46 )
        return -2;
      v47 = v44;
      v48 = v46;
      v49 = (char *)Src + 1;
      if ( *(_WORD *)Src )
      {
        while ( !*v49 )
        {
          v49 += 2;
          *v48 = *v47;
          v47 += 2;
          ++v48;
          v50 = --v72;
          if ( !*(_WORD *)v47 )
            goto LABEL_70;
        }
        v51 = Size;
        memcpy(Src, Src, Size);
        v52 = 1;
      }
      else
      {
        v50 = v72;
LABEL_70:
        LOWORD(v45) = v50;
        v51 = v50;
        memcpy(Src, v69, v50);
        v52 = 0;
      }
      v53 = v68;
      v54 = v71;
      *((_BYTE *)v68 + 4) = v52;
      *v53 = word_10004570[v54];
      v53[1] = v45;
      LOWORD(v67) = 1054;
      HIWORD(v67) = v51 + 5;
      MemFree(v69);
      v42 = v51 + 5;
      v43 = v51 + 5;
    }
    v55 = *(_DWORD *)(this + 40);
    Size = v43;
    if ( v55 )
    {
      v56 = MemAllocate(v42 + 11);
      if ( !v56 )
        return -2;
      v57 = Size;
      *(_DWORD *)(v56 + 4) = v67;
      memcpy((void *)(v56 + 8), v68, v57);
      v58 = *(int **)(v55 + 4);
      if ( v58 )
      {
        while ( *v58 )
          v58 = (int *)*v58;
        v23 = (char *)v68;
        *v58 = v56;
      }
      else
      {
        *(_DWORD *)(v55 + 4) = v56;
        v23 = (char *)v68;
      }
    }
    else
    {
      v15 = BFWriteFile(*(_DWORD *)(this + 20), (char *)&v67, 4u);
      if ( v15 )
        goto LABEL_18;
      v23 = (char *)v68;
      v15 = BFWriteFile(*(_DWORD *)(this + 20), (char *)v68, SHIWORD(v67));
      if ( v15 )
        goto LABEL_18;
    }
    v30 = v71 + 1;
    v71 = v30;
  }
  while ( v30 < 8 );
  if ( *(_DWORD *)(this + 4) == 5 )
    return WriteStream(dword_1003A080, 472);
  v15 = WriteStream(dword_1003A2B0, 622);
  if ( !v15 )
  {
    *(_WORD *)v23 = *(_WORD *)(this + 32);
    *((_WORD *)v23 + 1) = *(_WORD *)(this + 32);
    v59 = *(_DWORD *)(this + 40);
    v67 = 262284;
    if ( v59 )
    {
      v60 = MemAllocate(15);
      if ( !v60 )
        return -2;
      *(_DWORD *)(v60 + 4) = v67;
      *(_DWORD *)(v60 + 8) = *(_DWORD *)v23;
      v61 = *(int **)(v59 + 4);
      if ( v61 )
      {
        while ( *v61 )
          v61 = (int *)*v61;
        *v61 = v60;
      }
      else
      {
        *(_DWORD *)(v59 + 4) = v60;
      }
      goto LABEL_94;
    }
    v15 = BFWriteFile(*(_DWORD *)(this + 20), (char *)&v67, 4u);
    if ( !v15 )
    {
      v15 = BFWriteFile(*(_DWORD *)(this + 20), v23, SHIWORD(v67));
      if ( !v15 )
      {
LABEL_94:
        v67 = 10;
        *(_WORD *)v23 = 0;
        v62 = *(_DWORD *)(this + 40);
        if ( !v62 )
        {
          v15 = BFWriteFile(*(_DWORD *)(this + 20), (char *)&v67, 4u);
          if ( !v15 )
            return BFWriteFile(*(_DWORD *)(this + 20), v23, SHIWORD(v67));
          goto LABEL_18;
        }
        v63 = MemAllocate(11);
        if ( !v63 )
          return -2;
        *(_DWORD *)(v63 + 4) = v67;
        v64 = *(int **)(v62 + 4);
        if ( !v64 )
        {
          *(_DWORD *)(v62 + 4) = v63;
          return 0;
        }
        while ( *v64 )
          v64 = (int *)*v64;
        *v64 = v63;
        return 0;
      }
    }
  }
LABEL_18:
  result = dword_10001970[abs32(v15)];
  if ( result == -10 )
    return -10;
  return result;
}

```

## disassembly

```asm
0x10015090  mov     edi, edi
0x10015092  push    ebp
0x10015093  mov     ebp, esp
0x10015095  and     esp, 0FFFFFFF8h
0x10015098  sub     esp, 4Ch
0x1001509b  mov     eax, ___security_cookie
0x100150a0  xor     eax, esp
0x100150a2  mov     [esp+4Ch+var_4], eax
0x100150a6  mov     eax, _pExcelRecordBuffer
0x100150ab  push    ebx
0x100150ac  push    esi
0x100150ad  push    edi
0x100150ae  mov     [esp+58h+var_48], eax
0x100150b2  mov     ebx, ecx
0x100150b4  push    8; cchData
0x100150b6  lea     eax, [esp+5Ch+LCData]
0x100150ba  push    eax; lpLCData
0x100150bb  push    1Bh; LCType
0x100150bd  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x100150c3  push    eax; Locale
0x100150c4  call    ds:__imp__GetLocaleInfoW@16; GetLocaleInfoW(x,x,x,x)
0x100150ca  add     eax, eax
0x100150cc  cmp     eax, 10h
0x100150cf  jnb     loc_100158B8
0x100150d5  xor     ecx, ecx
0x100150d7  mov     [esp+eax+58h+LCData], cx
0x100150dc  lea     eax, [esp+58h+LCData]
0x100150e0  push    eax
0x100150e1  call    ds:__imp___o__wtoi
0x100150e7  add     esp, 4
0x100150ea  cmp     eax, 3
0x100150ed  jge     short loc_10015103
0x100150ef  lea     eax, [esp+58h+LCData]
0x100150f3  push    eax
0x100150f4  call    ds:__imp___o__wtoi
0x100150fa  add     esp, 4
0x100150fd  mov     [esp+58h+var_1C], eax
0x10015101  jmp     short loc_1001510B
0x10015103  mov     [esp+58h+var_1C], 3
0x1001510b  push    8; cchData
0x1001510d  lea     eax, [esp+5Ch+LCData]
0x10015111  push    eax; lpLCData
0x10015112  push    1Ch; LCType
0x10015114  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x1001511a  push    eax; Locale
0x1001511b  call    _JetGetLocaleInfoW@16; JetGetLocaleInfoW(x,x,x,x)
0x10015120  add     eax, eax
0x10015122  cmp     eax, 10h
0x10015125  jnb     loc_100158B8
0x1001512b  xor     ecx, ecx
0x1001512d  mov     [esp+eax+58h+LCData], cx
0x10015132  lea     eax, [esp+58h+LCData]
0x10015136  push    eax
0x10015137  call    ds:__imp___o__wtoi
0x1001513d  add     esp, 4
0x10015140  cmp     eax, 0Fh
0x10015143  jge     short loc_10015155
0x10015145  lea     eax, [esp+58h+LCData]
0x10015149  push    eax
0x1001514a  call    ds:__imp___o__wtoi
0x10015150  add     esp, 4
0x10015153  jmp     short loc_1001515A
0x10015155  mov     eax, 0Fh
0x1001515a  movsx   eax, ds:word_1000454C[eax*2]
0x10015162  mov     [esp+58h+var_18], eax
0x10015166  lea     eax, [esp+58h+LCData]
0x1001516a  push    8; cchData
0x1001516c  push    eax; lpLCData
0x1001516d  push    14h; LCType
0x1001516f  call    ds:__imp__GetUserDefaultLCID@0; GetUserDefaultLCID()
0x10015175  push    eax; Locale
0x10015176  call    _JetGetLocaleInfoW@16; JetGetLocaleInfoW(x,x,x,x)
0x1001517b  add     eax, eax
0x1001517d  cmp     eax, 10h
0x10015180  jnb     loc_100158B8
0x10015186  xor     ecx, ecx
0x10015188  lea     esi, [esp+58h+LCData]
0x1001518c  mov     [esp+eax+58h+LCData], cx
0x10015191  mov     eax, 7FFFFFFEh
0x10015196  lea     edx, [ecx+8]
0x10015199  lea     ecx, [esp+58h+var_30]
0x1001519d  nop     dword ptr [eax]
0x100151a0  test    eax, eax
0x100151a2  jz      short loc_100151BB
0x100151a4  movzx   edi, word ptr [esi]
0x100151a7  test    di, di
0x100151aa  jz      short loc_100151BB
0x100151ac  mov     [ecx], di
0x100151af  add     esi, 2
0x100151b2  add     ecx, 2
0x100151b5  dec     eax
0x100151b6  sub     edx, 1
0x100151b9  jnz     short loc_100151A0
0x100151bb  test    edx, edx
0x100151bd  lea     eax, [ecx-2]
0x100151c0  cmovnz  eax, ecx
0x100151c3  xor     ecx, ecx
0x100151c5  mov     [eax], cx
0x100151c8  lea     ecx, [esp+58h+var_30]
0x100151cc  lea     edx, [ecx+2]
0x100151cf  nop
0x100151d0  mov     ax, [ecx]
0x100151d3  add     ecx, 2
0x100151d6  test    ax, ax
0x100151d9  jnz     short loc_100151D0
0x100151db  sub     ecx, edx
0x100151dd  sar     ecx, 1
0x100151df  lea     eax, [ecx+ecx]
0x100151e2  mov     [esp+58h+var_20], eax
0x100151e6  mov     eax, [ebx+4]
0x100151e9  cmp     eax, 3
0x100151ec  jnz     loc_100152EB
0x100151f2  push    3Eh ; '>'
0x100151f4  push    offset dword_1003A040
0x100151f9  lea     edx, [esp+60h+var_30]
0x100151fd  mov     ecx, ebx
0x100151ff  call    WriteStream
0x10015204  test    eax, eax
0x10015206  jz      short loc_10015230
0x10015208  cdq
0x10015209  mov     ecx, 0FFFFFFF6h
0x1001520e  xor     eax, edx
0x10015210  sub     eax, edx
0x10015212  mov     eax, ds:dword_10001970[eax*4]
0x10015219  cmp     eax, ecx
0x1001521b  cmovz   eax, ecx
0x1001521e  pop     edi
0x1001521f  pop     esi
0x10015220  pop     ebx
0x10015221  mov     ecx, [esp+4Ch+var_4]
0x10015225  xor     ecx, esp; StackCookie
0x10015227  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001522c  mov     esp, ebp
0x1001522e  pop     ebp
0x1001522f  retn
0x10015230  mov     edi, [esp+58h+var_48]
0x10015234  lea     edx, [esp+58h+var_4C]
0x10015238  mov     ax, [ebx+1Ch]
0x1001523c  push    4
0x1001523e  mov     [esp+5Ch+var_4C], 20042h
0x10015246  mov     [edi], ax
0x10015249  mov     ecx, [ebx+14h]
0x1001524c  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10015251  test    eax, eax
0x10015253  jnz     short loc_10015208
0x10015255  movsx   eax, word ptr [esp+58h+var_4C+2]
0x1001525a  mov     edx, edi
0x1001525c  mov     ecx, [ebx+14h]
0x1001525f  push    eax
0x10015260  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10015265  test    eax, eax
0x10015267  jnz     short loc_10015208
0x10015269  push    64h ; 'd'
0x1001526b  push    offset dword_10039A80
0x10015270  lea     edx, [esp+60h+var_30]
0x10015274  mov     ecx, ebx
0x10015276  call    WriteStream
0x1001527b  test    eax, eax
0x1001527d  jnz     short loc_10015208
0x1001527f  movzx   eax, word ptr [ebx+20h]
0x10015283  lea     edx, [esp+58h+var_4C]
0x10015287  mov     [edi], ax
0x1001528a  movzx   eax, word ptr [ebx+20h]
0x1001528e  mov     [edi+2], ax
0x10015292  mov     ecx, [ebx+14h]
0x10015295  push    4
0x10015297  mov     [esp+5Ch+var_4C], 4008Ch
0x1001529f  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x100152a4  test    eax, eax
0x100152a6  jnz     loc_10015208
0x100152ac  movsx   eax, word ptr [esp+58h+var_4C+2]
0x100152b1  mov     edx, edi
0x100152b3  mov     ecx, [ebx+14h]
0x100152b6  push    eax
0x100152b7  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x100152bc  test    eax, eax
0x100152be  jnz     loc_10015208
0x100152c4  push    435h
0x100152c9  push    offset dword_100394B0
0x100152ce  lea     edx, [esp+60h+var_30]
0x100152d2  mov     ecx, ebx
0x100152d4  call    WriteStream
0x100152d9  pop     edi
0x100152da  pop     esi
0x100152db  pop     ebx
0x100152dc  mov     ecx, [esp+4Ch+var_4]
0x100152e0  xor     ecx, esp; StackCookie
0x100152e2  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100152e7  mov     esp, ebp
0x100152e9  pop     ebp
0x100152ea  retn
0x100152eb  cmp     eax, 4
0x100152ee  jnz     loc_100153BD
0x100152f4  push    3Eh ; '>'
0x100152f6  push    offset dword_1003A520
0x100152fb  lea     edx, [esp+60h+var_30]
0x100152ff  mov     ecx, ebx
0x10015301  call    WriteStream
0x10015306  test    eax, eax
0x10015308  jnz     loc_10015208
0x1001530e  mov     edi, [esp+58h+var_48]
0x10015312  lea     edx, [esp+58h+var_4C]
0x10015316  mov     ax, [ebx+1Ch]
0x1001531a  push    4
0x1001531c  mov     [esp+5Ch+var_4C], 20042h
0x10015324  mov     [edi], ax
0x10015327  mov     ecx, [ebx+14h]
0x1001532a  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1001532f  test    eax, eax
0x10015331  jnz     loc_10015208
0x10015337  movsx   eax, word ptr [esp+58h+var_4C+2]
0x1001533c  mov     edx, edi
0x1001533e  mov     ecx, [ebx+14h]
0x10015341  push    eax
0x10015342  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10015347  test    eax, eax
0x10015349  jnz     loc_10015208
0x1001534f  push    5Ch ; '\'
0x10015351  push    offset dword_1003A560
0x10015356  lea     edx, [esp+60h+var_30]
0x1001535a  mov     ecx, ebx
0x1001535c  call    WriteStream
0x10015361  test    eax, eax
0x10015363  jnz     loc_10015208
0x10015369  movzx   eax, word ptr [ebx+20h]
0x1001536d  lea     edx, [esp+58h+var_4C]
0x10015371  mov     [edi], ax
0x10015374  movzx   eax, word ptr [ebx+20h]
0x10015378  mov     [edi+2], ax
0x1001537c  mov     ecx, [ebx+14h]
0x1001537f  push    4
0x10015381  mov     [esp+5Ch+var_4C], 4008Ch
0x10015389  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1001538e  test    eax, eax
0x10015390  jnz     loc_10015208
0x10015396  movsx   eax, word ptr [esp+58h+var_4C+2]
0x1001539b  mov     edx, edi
0x1001539d  mov     ecx, [ebx+14h]
0x100153a0  push    eax
0x100153a1  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x100153a6  test    eax, eax
0x100153a8  jnz     loc_10015208
0x100153ae  push    546h
0x100153b3  push    offset dword_10039AF0
0x100153b8  jmp     loc_100152CE
0x100153bd  cmp     eax, 5
0x100153c0  jl      loc_1001586C
0x100153c6  jnz     loc_100154A2
0x100153cc  push    46h ; 'F'
0x100153ce  push    offset unk_1003A260
0x100153d3  lea     edx, [esp+60h+var_30]
0x100153d7  mov     ecx, ebx
0x100153d9  call    WriteStream
0x100153de  test    eax, eax
0x100153e0  jnz     loc_10015208
0x100153e6  mov     edi, [esp+58h+var_48]
0x100153ea  mov     ax, [ebx+1Ch]
0x100153ee  mov     [esp+58h+var_4C], 20042h
0x100153f6  mov     [edi], ax
0x100153f9  mov     esi, [ebx+28h]
0x100153fc  test    esi, esi
0x100153fe  jz      short loc_10015468
0x10015400  mov     ecx, 0Dh
0x10015405  call    _MemAllocate@4; MemAllocate(x)
0x1001540a  mov     edx, eax
0x1001540c  test    edx, edx
0x1001540e  jnz     short loc_10015427
0x10015410  mov     eax, 0FFFFFFFEh
0x10015415  pop     edi
0x10015416  pop     esi
0x10015417  pop     ebx
0x10015418  mov     ecx, [esp+4Ch+var_4]
0x1001541c  xor     ecx, esp; StackCookie
0x1001541e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10015423  mov     esp, ebp
0x10015425  pop     ebp
0x10015426  retn
0x10015427  mov     eax, [esp+58h+var_4C]
0x1001542b  mov     [edx+4], eax
0x1001542e  mov     ax, [edi]
0x10015431  mov     [edx+8], ax
0x10015435  mov     ecx, [esi+4]
0x10015438  test    ecx, ecx
0x1001543a  jnz     short loc_10015450
0x1001543c  mov     [esi+4], edx
0x1001543f  mov     eax, offset dword_100393E0
0x10015444  mov     ecx, 0C4h
0x10015449  jmp     short loc_100154B0
0x10015450  mov     eax, [ecx]
0x10015452  test    eax, eax
0x10015454  jz      short loc_1001545A
0x10015456  mov     ecx, eax
0x10015458  jmp     short loc_10015450
0x1001545a  mov     [ecx], edx
0x1001545c  mov     eax, offset dword_100393E0
0x10015461  mov     ecx, 0C4h
0x10015466  jmp     short loc_100154B0
0x10015468  mov     ecx, [ebx+14h]
0x1001546b  lea     edx, [esp+58h+var_4C]
0x1001546f  push    4
  ... truncated ...
```
