# WSTSealMessage

- ea: `0x180032898`
- end: `0x1800332a9`
- name: `WSTSealMessage`
- size: `2577`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024900`

## callees

- `0x18001b2b8`
- `0x1800201bc`
- `0x1800210f0`
- `0x180023cb8`
- `0x180023ce0`
- `0x18002b408`
- `0x18002b744`
- `0x18003265c`
- `0x180032898`
- `0x180044f8c`
- `0x180046010`

## import_xrefs

- `cryptdll!CDLocateCSystem` at `0x180032926`
- `cryptdll!CDLocateCSystem` at `0x180032926`
- `cryptdll!CDLocateCheckSum` at `0x180032bcc`
- `cryptdll!CDLocateCheckSum` at `0x180032bcc`

## string_xrefs

- `0x180032a67`: `onecore\ds\security\protocols\pku2u\message.cxx`

## pseudocode

```c
__int64 __fastcall WSTSealMessage(__int64 a1, int a2, __int64 a3, char a4)
{
  unsigned int v4; // r15d
  int v9; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r11
  unsigned int v14; // r10d
  unsigned int v15; // r12d
  unsigned int i; // r9d
  _DWORD *v17; // rdx
  int v18; // r8d
  int v19; // eax
  int v20; // r14d
  _BYTE *v21; // rdi
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  unsigned int v25; // r14d
  size_t v26; // rsi
  unsigned int v27; // eax
  __int64 v28; // r11
  __int64 v29; // rdx
  __int64 v30; // rcx
  int v31; // r9d
  unsigned int v32; // r10d
  unsigned int v33; // ebx
  int v34; // r15d
  char v35; // dl
  int v36; // ecx
  int v37; // r8d
  int v38; // ecx
  __int64 v39; // rcx
  unsigned int v40; // ebx
  __int64 v41; // r9
  const void *v42; // rdx
  int v43; // ecx
  char v44; // cl
  int v45; // edx
  int v46; // r8d
  int v47; // ecx
  unsigned __int64 v48; // rdx
  unsigned __int64 v49; // rcx
  char v50; // al
  int v51; // eax
  unsigned __int64 v52; // rdx
  unsigned __int64 v53; // rcx
  unsigned int v55; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v56; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v57; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v58; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v59; // [rsp+68h] [rbp-98h] BYREF
  __int64 v60; // [rsp+70h] [rbp-90h]
  __int64 v61; // [rsp+78h] [rbp-88h] BYREF
  __int64 v62; // [rsp+80h] [rbp-80h] BYREF
  void *v63; // [rsp+88h] [rbp-78h] BYREF
  __int64 v64; // [rsp+90h] [rbp-70h]
  size_t Size; // [rsp+98h] [rbp-68h]
  _BYTE Src[96]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v67; // [rsp+100h] [rbp+0h] BYREF
  int v68; // [rsp+108h] [rbp+8h]

  v4 = 0;
  v64 = a3;
  v58 = 0;
  v59 = 0;
  v57 = 0;
  v61 = 0;
  v56 = 0;
  v55 = 0;
  v62 = 0;
  v63 = 0;
  v9 = WSTGetChecksumAndEncryptionType(a1, 1, a2, (unsigned int)&v56, (__int64)&v55);
  if ( v9 < 0 )
    return (unsigned int)v9;
  v9 = CDLocateCSystem(v55, &v59);
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = v55;
      v12 = 34;
LABEL_6:
      WPP_SF_dd(v10[2], v12, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids, v11, v9);
    }
    goto LABEL_137;
  }
  v55 = *(_DWORD *)(v59 + 4);
  if ( v55 > 0x20 )
    goto LABEL_8;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  for ( i = 0; i < *(_DWORD *)(a3 + 4); ++i )
  {
    v17 = (_DWORD *)(*(_QWORD *)(a3 + 8) + 16LL * i);
    v18 = v17[1];
    v19 = v18 & 0x10000000;
    if ( v18 < 0 && v19 )
    {
      v9 = -2146893048;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids);
      goto LABEL_137;
    }
    if ( (v18 & 0xFFFFFFF) == 2 )
    {
      v13 = *(_QWORD *)(a3 + 8) + 16LL * i;
    }
    else if ( v18 >= 0 )
    {
      if ( (v18 & 0xFFFFFFF) == 9 )
      {
        *v17 = 0;
      }
      else
      {
        v14 += *v17;
        if ( a2 != -2147483647 && !v19 )
          v15 += *v17;
      }
    }
  }
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        36,
        (unsigned int)&WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\message.cxx",
        109);
    v9 = -1073741811;
    goto LABEL_137;
  }
  v20 = 0;
  if ( a2 != -2147483647 )
  {
    if ( v15 < v14 || !v15 )
      v20 = 16;
    if ( (*(_BYTE *)(a1 + 84) & 0x10) == 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids);
LABEL_38:
      v9 = -2146893054;
      goto LABEL_137;
    }
  }
  v9 = WSTMakeSignatureToken(a1, a2, v13, i, 1, a4, v20, (__int64)&v63, (__int64)&v62);
  if ( v9 < 0 )
    goto LABEL_137;
  v21 = v63;
  if ( a2 != -2147483647 )
  {
    *(_BYTE *)v63 |= 2u;
    *(_OWORD *)&v21[256 * (unsigned __int64)(unsigned __int8)v21[2] + 14 + (unsigned __int8)v21[3]] = *(_OWORD *)(v21 - 2);
    v22 = (*v21 & 2) != 0 ? (unsigned __int8)v21[3] + ((unsigned __int64)(unsigned __int8)v21[2] << 8) : 0LL;
    v9 = WSTRandomFill(&v21[((*v21 & 2) != 0 ? 42LL : 26LL) + v22], 16);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
          (unsigned int)v9);
      goto LABEL_137;
    }
  }
  v9 = CDLocateCheckSum(v56, &v58);
  if ( v9 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = v56;
      v12 = 39;
      goto LABEL_6;
    }
    goto LABEL_137;
  }
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v58 + 48))(
         *(_QWORD *)(a1 + 56),
         *(unsigned int *)(a1 + 48),
         (*(_DWORD *)(a1 + 80) & 2) != 0 ? 24 : 22,
         &v57);
  if ( v9 < 0 )
    goto LABEL_137;
  if ( a2 != -2147483647 )
  {
    v23 = (*v21 & 2) != 0 ? (unsigned __int8)v21[3] + ((unsigned __int64)(unsigned __int8)v21[2] << 8) : 0LL;
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(v58 + 24))(
           v57,
           16,
           &v21[v23 + ((*v21 & 2) != 0 ? 42LL : 26LL)]);
    if ( v9 < 0 )
      goto LABEL_137;
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v59 + 40))(
           *(_QWORD *)(a1 + 56),
           *(unsigned int *)(a1 + 48),
           (*(_DWORD *)(a1 + 80) & 2) != 0 ? 24 : 22,
           &v61);
    if ( v9 < 0 )
      goto LABEL_137;
    v15 += v20 + 16;
    v24 = (*v21 & 2) != 0 ? (unsigned __int8)v21[3] + ((unsigned __int64)(unsigned __int8)v21[2] << 8) : 0LL;
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _BYTE *))(v59 + 96))(
           v61,
           v15,
           16,
           &v21[v24 + ((*v21 & 2) != 0 ? 42LL : 26LL)]);
    if ( v9 < 0 )
      goto LABEL_137;
  }
  v25 = 0;
  v26 = 0;
  v62 = 0;
  v27 = 0;
  v63 = 0;
  while ( 1 )
  {
    v56 = v27;
    if ( v27 >= *(_DWORD *)(v64 + 4) )
      break;
    v28 = *(_QWORD *)(v64 + 8);
    v29 = v27;
    v30 = 16LL * v27;
    v60 = v27;
    v31 = *(_DWORD *)(v30 + v28 + 4);
    if ( (v31 & 0xFFFFFFF) != 2 && v31 >= 0 )
    {
      v32 = *(_DWORD *)(v30 + v28);
      if ( v32 )
      {
        if ( (v31 & 0x10000000) == 0 )
        {
          v33 = v55;
          v34 = *(_DWORD *)(v30 + v28);
          if ( (_DWORD)v26 )
          {
            v62 = *(_QWORD *)(v30 + v28 + 8) + v55 - (unsigned int)v26;
            v33 = v55;
            v34 = v26 + v32 - v55;
          }
          else
          {
            v62 = *(_QWORD *)(v30 + v28 + 8);
          }
          v25 = v34 & -v33;
          v4 = v34 - v25;
          v35 = *v21 & 2;
          if ( v35 )
            v36 = (unsigned __int8)v21[3] + ((unsigned __int8)v21[2] << 8);
          else
            v36 = 0;
          v37 = v35 != 0 ? 0x10 : 0;
          if ( v37 + v36 != v33 || v4 )
          {
            v29 = v60;
          }
          else
          {
            if ( v35 )
              v38 = (unsigned __int8)v21[3] + ((unsigned __int8)v21[2] << 8);
            else
              v38 = 0;
            v29 = v60;
            if ( v15 == v38 + v37 + v25 )
            {
              v25 -= v33;
              v4 = v33;
            }
          }
        }
        if ( v31 != 9 )
        {
          v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(v58 + 24))(
                 v57,
                 v32,
                 *(_QWORD *)(v28 + 16 * v29 + 8));
          if ( v9 < 0 )
            goto LABEL_137;
          if ( a2 != -2147483647 )
          {
            v39 = *(_QWORD *)(v64 + 8);
            if ( (*(_DWORD *)(v39 + 16 * v60 + 4) & 0x10000000) == 0 )
            {
              if ( (_DWORD)v26 )
              {
                v40 = v55;
                v41 = *(unsigned int *)(v39 + 16 * v60);
                if ( v55 - (unsigned int)v26 > (unsigned int)v41 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      40,
                      &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
                      v41);
                  goto LABEL_38;
                }
                v42 = *(const void **)(v39 + 16 * v60 + 8);
                Size = v55 - (unsigned int)v26;
                memcpy_0(&Src[v26], v42, Size);
                v15 -= v40;
                v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _BYTE *))(v59 + 96))(v61, v15, v40, Src);
                if ( v9 < 0 )
                  goto LABEL_137;
                memcpy_0(v63, Src, v26);
                memcpy_0(*(void **)(*(_QWORD *)(v64 + 8) + 16 * v60 + 8), &Src[v26], Size);
              }
              if ( v25 )
              {
                v15 -= v25;
                v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(v59 + 96))(v61, v15, v25, v62);
                if ( v9 < 0 )
                  goto LABEL_137;
              }
              memcpy_0(Src, (const void *)(v62 + v25), v4);
              v26 = v4;
              v63 = (void *)(*(unsigned int *)(*(_QWORD *)(v64 + 8) + 16 * v60)
                           + *(_QWORD *)(*(_QWORD *)(v64 + 8) + 16 * v60 + 8)
                           - v4);
            }
          }
        }
      }
    }
    v27 = v56 + 1;
  }
  if ( a2 == -2147483647 )
  {
    v9 = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(v58 + 24))(v57, 16, v21 - 2);
    if ( v9 < 0 )
      goto LABEL_137;
  }
  else
  {
    if ( (*v21 & 2) != 0 )
      v43 = (unsigned __int8)v21[3] + ((unsigned __int8)v21[2] << 8);
    else
      v43 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _BYTE *))(v58 + 24))(
           v57,
           v43 + ((*v21 & 2) != 0 ? 0x10 : 0),
           v21 + 14);
    if ( v9 < 0 )
      goto LABEL_137;
    v44 = *v21 & 2;
    if ( v44 )
      v45 = (unsigned __int8)v21[3] + ((unsigned __int8)v21[2] << 8);
    else
      v45 = 0;
    v46 = v44 != 0 ? 0x10 : 0;
    if ( (unsigned int)(v26 + v45 + v46) > 0x60 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        if ( v44 )
          v47 = (unsigned __int8)v21[3] + ((unsigned __int8)v21[2] << 8);
        else
          v47 = 0;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
          (unsigned int)(v47 + v46));
      }
LABEL_8:
      v9 = -1073741637;
      goto LABEL_137;
    }
    if ( v44 )
      v48 = (unsigned __int8)v21[3] + ((unsigned __int64)(unsigned __int8)v21[2] << 8);
    else
      v48 = 0;
    memcpy_0(&Src[v26], v21 + 14, v48 + (v44 != 0 ? 0x10 : 0));
    v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _BYTE *))(v59 + 96))(v61, 0, v15, Src);
    if ( v9 < 0 )
      goto LABEL_137;
    memcpy_0(v63, Src, v26);
    if ( (*v21 & 2) != 0 )
      v49 = (unsigned __int8)v21[3] + ((unsigned __int64)(unsigned __int8)v21[2] << 8);
    else
      v49 = 0;
    memcpy_0(v21 + 14, &Src[v26], v49 + ((*v21 & 2) != 0 ? 0x10 : 0));
    LODWORD(v26) = 0;
  }
  v50 = 28;
  v21[4] = 0;
  if ( a2 == -2147483647 )
    v50 = 12;
  v21[5] = v50;
  if ( a2 == -2147483647 )
  {
    *((_WORD *)v21 + 1) = 3072;
  }
  else if ( (_DWORD)v26 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
        (unsigned int)v26);
    v9 = -2146893048;
    goto LABEL_137;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v58 + 32))(v57, &v67);
  if ( v9 >= 0 )
  {
    v51 = (*(__int64 (__fastcall **)(__int64 *))(v58 + 40))(&v57);
    v57 = 0;
    v9 = v51;
    if ( v51 >= 0 )
    {
      if ( (*v21 & 2) != 0 )
        v52 = (unsigned __int8)v21[3] + ((unsigned __int64)(unsigned __int8)v21[2] << 8);
      else
        v52 = 0;
      v53 = v52 + ((*v21 & 2) != 0 ? 0x10 : 0);
      *(_QWORD *)&v21[v53 + 14] = v67;
      *(_DWORD *)&v21[v53 + 22] = v68;
    }
  }
LABEL_137:
  if ( v61 && v59 )
    (*(void (__fastcall **)(__int64 *))(v59 + 64))(&v61);
  if ( v57 && v58 )
    (*(void (__fastcall **)(__int64 *))(v58 + 40))(&v57);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180032898  push    rbp
0x18003289a  push    rbx
0x18003289b  push    rsi
0x18003289c  push    rdi
0x18003289d  push    r12
0x18003289f  push    r13
0x1800328a1  push    r14
0x1800328a3  push    r15
0x1800328a5  lea     rbp, [rsp-58h]
0x1800328aa  sub     rsp, 158h
0x1800328b1  mov     rax, cs:__security_cookie
0x1800328b8  xor     rax, rsp
0x1800328bb  mov     [rbp+90h+var_50], rax
0x1800328bf  xor     r15d, r15d
0x1800328c2  mov     [rbp+90h+var_100], r8
0x1800328c6  lea     rax, [rsp+190h+var_140]
0x1800328cb  mov     edi, r9d
0x1800328ce  mov     r14, r8
0x1800328d1  mov     [rsp+190h+var_130], r15
0x1800328d6  mov     r8d, edx
0x1800328d9  mov     [rsp+190h+var_128], r15
0x1800328de  mov     r13d, edx
0x1800328e1  mov     [rsp+190h+var_138], r15
0x1800328e6  lea     edx, [r15+1]
0x1800328ea  mov     [rsp+190h+var_118], r15
0x1800328ef  lea     r9, [rsp+190h+var_13C]
0x1800328f4  mov     [rsp+190h+var_13C], r15d
0x1800328f9  mov     rsi, rcx
0x1800328fc  mov     [rsp+190h+var_140], r15d
0x180032901  mov     [rbp+90h+var_110], r15
0x180032905  mov     [rbp+90h+var_108], r15
0x180032909  mov     [rsp+190h+var_170], rax
0x18003290e  call    WSTGetChecksumAndEncryptionType
0x180032913  mov     ebx, eax
0x180032915  test    eax, eax
0x180032917  js      loc_180033287
0x18003291d  mov     ecx, [rsp+190h+var_140]
0x180032921  lea     rdx, [rsp+190h+var_128]
0x180032926  call    cs:__imp_CDLocateCSystem
0x18003292c  mov     ebx, eax
0x18003292e  test    eax, eax
0x180032930  jns     short loc_180032975
0x180032932  mov     rcx, cs:WPP_GLOBAL_Control
0x180032939  lea     rax, WPP_GLOBAL_Control
0x180032940  cmp     rcx, rax
0x180032943  jz      loc_180033247
0x180032949  test    byte ptr [rcx+1Ch], 1
0x18003294d  jz      loc_180033247
0x180032953  mov     r9d, [rsp+190h+var_140]
0x180032958  lea     edx, [r15+22h]
0x18003295c  mov     rcx, [rcx+10h]
0x180032960  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x180032967  mov     dword ptr [rsp+190h+var_170], ebx
0x18003296b  call    WPP_SF_dd
0x180032970  jmp     loc_180033247
0x180032975  mov     rax, [rsp+190h+var_128]
0x18003297a  mov     eax, [rax+4]
0x18003297d  mov     [rsp+190h+var_140], eax
0x180032981  cmp     eax, 20h ; ' '
0x180032984  jbe     short loc_180032990
0x180032986  mov     ebx, 0C00000BBh
0x18003298b  jmp     loc_180033247
0x180032990  mov     r11, r15
0x180032993  mov     r10d, r15d
0x180032996  mov     r12d, r15d
0x180032999  mov     r9d, r15d
0x18003299c  mov     ebx, 80000001h
0x1800329a1  cmp     r9d, [r14+4]
0x1800329a5  jnb     loc_180032A41
0x1800329ab  mov     edx, r9d
0x1800329ae  shl     rdx, 4
0x1800329b2  add     rdx, [r14+8]
0x1800329b6  mov     r8d, [rdx+4]
0x1800329ba  mov     eax, r8d
0x1800329bd  and     eax, 10000000h
0x1800329c2  test    r8d, r8d
0x1800329c5  jns     short loc_1800329CB
0x1800329c7  test    eax, eax
0x1800329c9  jnz     short loc_180032A01
0x1800329cb  mov     ecx, r8d
0x1800329ce  and     ecx, 0FFFFFFFh
0x1800329d4  cmp     ecx, 2
0x1800329d7  jnz     short loc_1800329DE
0x1800329d9  mov     r11, rdx
0x1800329dc  jmp     short loc_1800329FC
0x1800329de  test    r8d, r8d
0x1800329e1  js      short loc_1800329FC
0x1800329e3  cmp     ecx, 9
0x1800329e6  jnz     short loc_1800329ED
0x1800329e8  mov     [rdx], r15d
0x1800329eb  jmp     short loc_1800329FC
0x1800329ed  add     r10d, [rdx]
0x1800329f0  cmp     r13d, ebx
0x1800329f3  jz      short loc_1800329FC
0x1800329f5  test    eax, eax
0x1800329f7  jnz     short loc_1800329FC
0x1800329f9  add     r12d, [rdx]
0x1800329fc  inc     r9d
0x1800329ff  jmp     short loc_1800329A1
0x180032a01  mov     ebx, 80090308h
0x180032a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180032a0d  lea     rax, WPP_GLOBAL_Control
0x180032a14  cmp     rcx, rax
0x180032a17  jz      loc_180033247
0x180032a1d  test    byte ptr [rcx+1Ch], 1
0x180032a21  jz      loc_180033247
0x180032a27  mov     rcx, [rcx+10h]
0x180032a2b  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x180032a32  mov     edx, 23h ; '#'
0x180032a37  call    WPP_SF_
0x180032a3c  jmp     loc_180033247
0x180032a41  test    r11, r11
0x180032a44  jnz     short loc_180032A8C
0x180032a46  mov     rcx, cs:WPP_GLOBAL_Control
0x180032a4d  lea     rax, WPP_GLOBAL_Control
0x180032a54  cmp     rcx, rax
0x180032a57  jz      short loc_180032A82
0x180032a59  test    byte ptr [rcx+1Ch], 1
0x180032a5d  jz      short loc_180032A82
0x180032a5f  mov     rcx, [rcx+10h]
0x180032a63  lea     edx, [r11+24h]
0x180032a67  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\protocols\\pku2u"...
0x180032a6e  mov     dword ptr [rsp+190h+var_170], 46Dh
0x180032a76  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x180032a7d  call    WPP_SF_sd
0x180032a82  mov     ebx, 0C000000Dh
0x180032a87  jmp     loc_180033247
0x180032a8c  mov     r14d, r15d
0x180032a8f  cmp     r13d, ebx
0x180032a92  jz      short loc_180032AE2
0x180032a94  cmp     r12d, r10d
0x180032a97  jb      short loc_180032A9E
0x180032a99  test    r12d, r12d
0x180032a9c  jnz     short loc_180032AA4
0x180032a9e  mov     r14d, 10h
0x180032aa4  test    byte ptr [rsi+54h], 10h
0x180032aa8  jnz     short loc_180032AE2
0x180032aaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ab1  lea     rax, WPP_GLOBAL_Control
0x180032ab8  cmp     rcx, rax
0x180032abb  jz      short loc_180032AD8
0x180032abd  test    byte ptr [rcx+1Ch], 1
0x180032ac1  jz      short loc_180032AD8
0x180032ac3  mov     rcx, [rcx+10h]
0x180032ac7  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x180032ace  mov     edx, 25h ; '%'
0x180032ad3  call    WPP_SF_
0x180032ad8  mov     ebx, 80090302h
0x180032add  jmp     loc_180033247
0x180032ae2  lea     rcx, [rbp+90h+var_110]
0x180032ae6  mov     r8, r11
0x180032ae9  mov     [rsp+190h+var_150], rcx
0x180032aee  mov     edx, r13d
0x180032af1  lea     rcx, [rbp+90h+var_108]
0x180032af5  mov     [rsp+190h+var_158], rcx
0x180032afa  mov     rcx, rsi
0x180032afd  mov     [rsp+190h+var_160], r14d
0x180032b02  mov     [rsp+190h+var_168], rdi
0x180032b07  mov     byte ptr [rsp+190h+var_170], 1
0x180032b0c  call    WSTMakeSignatureToken
0x180032b11  mov     ebx, eax
0x180032b13  test    eax, eax
0x180032b15  js      loc_180033247
0x180032b1b  mov     rdi, [rbp+90h+var_108]
0x180032b1f  cmp     r13d, 80000001h
0x180032b26  jz      loc_180032BC3
0x180032b2c  or      byte ptr [rdi], 2
0x180032b2f  movzx   eax, byte ptr [rdi+2]
0x180032b33  movzx   ecx, byte ptr [rdi+3]
0x180032b37  movups  xmm0, xmmword ptr [rdi-2]
0x180032b3b  shl     rax, 8
0x180032b3f  add     rax, rdi
0x180032b42  movdqu  xmmword ptr [rcx+rax+0Eh], xmm0
0x180032b48  mov     dl, [rdi]
0x180032b4a  and     dl, 2
0x180032b4d  jz      short loc_180032B60
0x180032b4f  movzx   ecx, byte ptr [rdi+2]
0x180032b53  movzx   eax, byte ptr [rdi+3]
0x180032b57  shl     rcx, 8
0x180032b5b  add     rcx, rax
0x180032b5e  jmp     short loc_180032B63
0x180032b60  mov     rcx, r15
0x180032b63  neg     dl
0x180032b65  mov     edx, 10h
0x180032b6a  sbb     rax, rax
0x180032b6d  and     eax, 10h
0x180032b70  add     rax, 1Ah
0x180032b74  add     rcx, rax
0x180032b77  add     rcx, rdi
0x180032b7a  call    WSTRandomFill
0x180032b7f  mov     ebx, eax
0x180032b81  test    eax, eax
0x180032b83  jns     short loc_180032BC3
0x180032b85  mov     rcx, cs:WPP_GLOBAL_Control
0x180032b8c  lea     rax, WPP_GLOBAL_Control
0x180032b93  cmp     rcx, rax
0x180032b96  jz      loc_180033247
0x180032b9c  test    byte ptr [rcx+1Ch], 1
0x180032ba0  jz      loc_180033247
0x180032ba6  mov     rcx, [rcx+10h]
0x180032baa  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x180032bb1  mov     edx, 26h ; '&'
0x180032bb6  mov     r9d, ebx
0x180032bb9  call    WPP_SF_d
0x180032bbe  jmp     loc_180033247
0x180032bc3  mov     ecx, [rsp+190h+var_13C]
0x180032bc7  lea     rdx, [rsp+190h+var_130]
0x180032bcc  call    cs:__imp_CDLocateCheckSum
0x180032bd2  mov     ebx, eax
0x180032bd4  test    eax, eax
0x180032bd6  jns     short loc_180032C08
0x180032bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180032bdf  lea     rax, WPP_GLOBAL_Control
0x180032be6  cmp     rcx, rax
0x180032be9  jz      loc_180033247
0x180032bef  test    byte ptr [rcx+1Ch], 1
0x180032bf3  jz      loc_180033247
0x180032bf9  mov     r9d, [rsp+190h+var_13C]
0x180032bfe  mov     edx, 27h ; '''
0x180032c03  jmp     loc_18003295C
0x180032c08  mov     eax, [rsi+50h]
0x180032c0b  lea     r9, [rsp+190h+var_138]
0x180032c10  mov     edx, [rsi+30h]
0x180032c13  and     al, 2
0x180032c15  mov     rcx, [rsi+38h]
0x180032c19  neg     al
0x180032c1b  mov     rax, [rsp+190h+var_130]
0x180032c20  sbb     r8d, r8d
0x180032c23  and     r8d, 2
0x180032c27  add     r8d, 16h
0x180032c2b  mov     rax, [rax+30h]
0x180032c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c34  mov     ebx, eax
0x180032c36  test    eax, eax
0x180032c38  js      loc_180033247
0x180032c3e  cmp     r13d, 80000001h
0x180032c45  jz      loc_180032D30
0x180032c4b  mov     rax, [rsp+190h+var_130]
0x180032c50  mov     cl, [rdi]
0x180032c52  mov     r9, [rax+18h]
0x180032c56  and     cl, 2
0x180032c59  jz      short loc_180032C6C
0x180032c5b  movzx   edx, byte ptr [rdi+2]
0x180032c5f  movzx   eax, byte ptr [rdi+3]
0x180032c63  shl     rdx, 8
0x180032c67  add     rdx, rax
0x180032c6a  jmp     short loc_180032C6F
0x180032c6c  mov     rdx, r15
0x180032c6f  neg     cl
0x180032c71  mov     rax, r9
0x180032c74  sbb     rcx, rcx
0x180032c77  and     ecx, 10h
0x180032c7a  lea     r8, [rcx+1Ah]
0x180032c7e  mov     rcx, [rsp+190h+var_138]
0x180032c83  add     r8, rdx
0x180032c86  mov     edx, 10h
0x180032c8b  add     r8, rdi
0x180032c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c93  mov     ebx, eax
0x180032c95  test    eax, eax
0x180032c97  js      loc_180033247
0x180032c9d  mov     eax, [rsi+50h]
0x180032ca0  lea     r9, [rsp+190h+var_118]
0x180032ca5  mov     edx, [rsi+30h]
0x180032ca8  and     al, 2
0x180032caa  mov     rcx, [rsi+38h]
0x180032cae  neg     al
0x180032cb0  mov     rax, [rsp+190h+var_128]
0x180032cb5  sbb     r8d, r8d
0x180032cb8  and     r8d, 2
0x180032cbc  add     r8d, 16h
0x180032cc0  mov     rax, [rax+28h]
0x180032cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cc9  mov     ebx, eax
0x180032ccb  test    eax, eax
0x180032ccd  js      loc_180033247
0x180032cd3  mov     rax, [rsp+190h+var_128]
0x180032cd8  add     r12d, 10h
0x180032cdc  mov     cl, [rdi]
0x180032cde  add     r12d, r14d
0x180032ce1  mov     r10, [rax+60h]
0x180032ce5  and     cl, 2
0x180032ce8  jz      short loc_180032CFB
0x180032cea  movzx   edx, byte ptr [rdi+2]
0x180032cee  movzx   eax, byte ptr [rdi+3]
0x180032cf2  shl     rdx, 8
0x180032cf6  add     rdx, rax
0x180032cf9  jmp     short loc_180032CFE
0x180032cfb  mov     rdx, r15
0x180032cfe  neg     cl
0x180032d00  mov     r8d, 10h
0x180032d06  mov     rax, r10
0x180032d09  sbb     rcx, rcx
0x180032d0c  and     ecx, 10h
0x180032d0f  lea     r9, [rcx+1Ah]
0x180032d13  mov     rcx, [rsp+190h+var_118]
0x180032d18  add     r9, rdx
0x180032d1b  mov     edx, r12d
0x180032d1e  add     r9, rdi
0x180032d21  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
