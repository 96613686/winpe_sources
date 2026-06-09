# _drr_GetCertPropIdsFromRegistry

- ea: `0x180001fcc`
- end: `0x1800024dc`
- name: `_drr_GetCertPropIdsFromRegistry`
- size: `1296`
- prototype: `__int64 __fastcall(HKEY hkey)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800027d8`

## callees

- `0x180001fcc`
- `0x1800035cc`
- `0x1800035f4`
- `0x18000d89e`
- `0x18000d8d0`

## import_xrefs

- `msvcrt!iswspace` at `0x180002275`
- `msvcrt!iswspace` at `0x180002332`
- `msvcrt!iswspace` at `0x180002275`
- `msvcrt!iswspace` at `0x180002332`
- `msvcrt!iswxdigit` at `0x1800022b7`
- `msvcrt!iswxdigit` at `0x1800022b7`
- `msvcrt!iswdigit` at `0x1800022c9`
- `msvcrt!iswdigit` at `0x180002305`
- `msvcrt!iswdigit` at `0x1800022c9`
- `msvcrt!iswdigit` at `0x180002305`
- `msvcrt!_wtoi` at `0x18000231d`
- `msvcrt!_wtoi` at `0x18000231d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000209e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000212b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000209e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000212b`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800023ff`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x1800023ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000200a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800020bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002213`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000200a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800020bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002213`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000235f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002480`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000235f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002480`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800021e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002245`
- `api-ms-win-core-string-l1-1-0!FoldStringW` at `0x1800021db`
- `api-ms-win-core-string-l1-1-0!FoldStringW` at `0x180002202`
- `api-ms-win-core-string-l1-1-0!FoldStringW` at `0x180002238`
- `api-ms-win-core-string-l1-1-0!FoldStringW` at `0x1800021db`
- `api-ms-win-core-string-l1-1-0!FoldStringW` at `0x180002202`
- `api-ms-win-core-string-l1-1-0!FoldStringW` at `0x180002238`

## pseudocode

```c
__int64 __fastcall drr_GetCertPropIdsFromRegistry(HKEY hkey)
{
  _QWORD *v2; // rax
  unsigned int v3; // edi
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int ValueW; // eax
  _WORD *v7; // rax
  _WORD *pvData; // r12
  WCHAR v9; // cx
  const WCHAR *v10; // rdx
  WCHAR v11; // r13
  const WCHAR *v12; // rax
  WCHAR *v13; // r14
  int v14; // esi
  const WCHAR *v15; // rbp
  int v16; // ebx
  WCHAR *v17; // rax
  int v18; // ebp
  wint_t *v19; // rbx
  __int64 v20; // rax
  WCHAR *v21; // r15
  int v22; // esi
  int v23; // ebp
  int v24; // eax
  int v25; // ecx
  int v26; // esi
  int v27; // ecx
  int v28; // edx
  _DWORD *v29; // r9
  unsigned int v30; // r8d
  __int64 v31; // rcx
  HLOCAL v32; // rax
  __int64 v33; // rax
  DWORD pcbData; // [rsp+40h] [rbp-88h] BYREF
  const WCHAR *v36; // [rsp+48h] [rbp-80h]
  WCHAR DestStr[16]; // [rsp+50h] [rbp-78h] BYREF

  dword_180013890 = 6;
  pcbData = 0;
  v2 = LocalAlloc(0, 0x18u);
  hMem = v2;
  if ( !v2 )
  {
    dword_180013890 = 0;
    v3 = 14;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = 10;
LABEL_5:
      WPP_SF_(v4[2], v5, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids);
      return v3;
    }
    return v3;
  }
  *(_OWORD *)v2 = xmmword_18000FB30;
  v2[2] = 0x4D00000013LL;
  ValueW = RegGetValueW(hkey, 0, L"PropIds", 0x20u, 0, 0, &pcbData);
  if ( ValueW || !pcbData )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids, ValueW);
    return 0;
  }
  v7 = LocalAlloc(0, pcbData);
  pvData = v7;
  if ( v7 )
  {
    memset_0(v7, 0, pcbData);
    v3 = RegGetValueW(hkey, 0, L"PropIds", 0x20u, 0, pvData, &pcbData);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids, v3);
      goto LABEL_87;
    }
    v9 = *pvData;
    if ( !*pvData )
    {
LABEL_87:
      LocalFree(pvData);
      return v3;
    }
    v10 = pvData;
    while ( 1 )
    {
      if ( v9 == 43 )
        v11 = v10[1];
      else
        v11 = v9;
      v12 = v10 + 1;
      if ( v9 != 43 )
        v12 = v10;
      v13 = DestStr;
      v14 = 0;
      v15 = v12 + 1;
      if ( v11 != 45 )
        v15 = v12;
      v36 = v15;
      if ( FoldStringW(0x80u, v15, -1, DestStr, 16) || GetLastError() != 122 )
        goto LABEL_30;
      v16 = FoldStringW(0x80u, v15, -1, 0, 0);
      v17 = (WCHAR *)LocalAlloc(0, 2LL * v16);
      v13 = v17;
      if ( v17 )
        break;
LABEL_79:
      v33 = -1;
      do
        ++v33;
      while ( v15[v33] );
      v10 = &v15[v33 + 1];
      v9 = *v10;
      if ( !*v10 )
        goto LABEL_87;
    }
    if ( !FoldStringW(0x80u, v15, -1, v17, v16) )
    {
      v18 = 0;
      GetLastError();
LABEL_60:
      if ( v13 != DestStr )
        LocalFree(v13);
LABEL_62:
      if ( v18 )
      {
        v27 = dword_180013890;
        v28 = 0;
        v29 = hMem;
        v30 = 0;
        if ( dword_180013890 )
        {
          while ( *((_DWORD *)hMem + v30) != v14 || !*((_DWORD *)hMem + v30) )
          {
            if ( ++v30 >= dword_180013890 )
              goto LABEL_69;
          }
          v28 = 1;
        }
LABEL_69:
        if ( v11 == 45 )
        {
          if ( v28 )
          {
            if ( v30 < dword_180013890 - 1 )
            {
              while ( 1 )
              {
                v31 = v30++;
                v29[v31] = v29[v30];
                v27 = dword_180013890;
                if ( v30 >= dword_180013890 - 1 )
                  break;
                v29 = hMem;
              }
            }
            dword_180013890 = v27 - 1;
          }
        }
        else if ( !v28 )
        {
          v32 = LocalReAlloc(hMem, 4LL * (unsigned int)(dword_180013890 + 1), 2u);
          if ( !v32 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids);
            v3 = 0;
            goto LABEL_87;
          }
          hMem = v32;
          *((_DWORD *)v32 + (unsigned int)dword_180013890++) = v14;
        }
      }
      v15 = v36;
      goto LABEL_79;
    }
LABEL_30:
    v18 = 0;
    v19 = v13;
    v20 = -1;
    do
      ++v20;
    while ( v13[v20] );
    v21 = &v13[v20];
    if ( v13 )
    {
      do
      {
        if ( v19 >= v21 )
          break;
        if ( !iswspace(*v19) )
          break;
        ++v19;
      }
      while ( v19 );
    }
    if ( *v19 != 48 || ((v19[1] - 88) & 0xFFDF) != 0 )
    {
      do
      {
        if ( v19 >= v21 )
          break;
        if ( !iswdigit(*v19) )
          break;
        v18 = 1;
        ++v19;
      }
      while ( v19 );
      v14 = _wtoi(v13);
LABEL_53:
      while ( v19 )
      {
        if ( v19 >= v21 )
          break;
        if ( !iswspace(*v19) )
          break;
        ++v19;
      }
    }
    else
    {
      for ( v19 += 2; v19; ++v19 )
      {
        if ( v19 >= v21 )
          break;
        if ( !iswxdigit(*v19) )
          goto LABEL_53;
        v22 = 16 * v14;
        v23 = v22;
        v24 = iswdigit(*v19);
        v25 = *v19;
        if ( v24 )
        {
          v26 = v25 - 48;
        }
        else
        {
          if ( (unsigned __int16)(v25 - 65) > 5u )
          {
            v14 = (v25 - 87) | v22;
            goto LABEL_47;
          }
          v26 = v25 - 55;
        }
        v14 = v23 | v26;
LABEL_47:
        v18 = 1;
      }
    }
    if ( *v19 )
      v18 = 0;
    if ( !v13 )
      goto LABEL_62;
    goto LABEL_60;
  }
  v3 = 14;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v5 = 12;
    goto LABEL_5;
  }
  return v3;
}

```

## disassembly

```asm
0x180001fcc  push    rbx
0x180001fce  push    rbp
0x180001fcf  push    rsi
0x180001fd0  push    rdi
0x180001fd1  push    r12
0x180001fd3  push    r13
0x180001fd5  push    r14
0x180001fd7  push    r15
0x180001fd9  sub     rsp, 88h
0x180001fe0  mov     rax, cs:__security_cookie
0x180001fe7  xor     rax, rsp
0x180001fea  mov     [rsp+0C8h+var_58], rax
0x180001fef  xor     r15d, r15d
0x180001ff2  mov     cs:dword_180013890, 6
0x180001ffc  mov     rbx, rcx
0x180001fff  mov     [rsp+0C8h+var_88], r15d
0x180002004  xor     ecx, ecx; uFlags
0x180002006  lea     edx, [r15+18h]; uBytes
0x18000200a  call    cs:__imp_LocalAlloc
0x180002010  mov     cs:hMem, rax
0x180002017  test    rax, rax
0x18000201a  jnz     short loc_18000205F
0x18000201c  mov     cs:dword_180013890, r15d
0x180002023  lea     edi, [rax+0Eh]
0x180002026  mov     rcx, cs:WPP_GLOBAL_Control
0x18000202d  lea     rax, WPP_GLOBAL_Control
0x180002034  cmp     rcx, rax
0x180002037  jz      loc_1800024B9
0x18000203d  test    byte ptr [rcx+1Ch], 2
0x180002041  jz      loc_1800024B9
0x180002047  lea     edx, [rdi-4]
0x18000204a  mov     rcx, [rcx+10h]
0x18000204e  lea     r8, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids
0x180002055  call    WPP_SF_
0x18000205a  jmp     loc_1800024B9
0x18000205f  movups  xmm0, cs:xmmword_18000FB30
0x180002066  mov     edi, 20h ; ' '
0x18000206b  lea     r8, Value; "PropIds"
0x180002072  mov     r9d, edi; dwFlags
0x180002075  xor     edx, edx; lpSubKey
0x180002077  movups  xmmword ptr [rax], xmm0
0x18000207a  mov     rcx, rbx; hkey
0x18000207d  movsd   xmm1, cs:qword_18000FB40
0x180002085  movsd   qword ptr [rax+10h], xmm1
0x18000208a  lea     rax, [rsp+0C8h+var_88]
0x18000208f  mov     [rsp+0C8h+pcbData], rax; pcbData
0x180002094  mov     [rsp+0C8h+pvData], r15; pvData
0x180002099  mov     [rsp+0C8h+pdwType], r15; pdwType
0x18000209e  call    cs:__imp_RegGetValueW
0x1800020a4  mov     r9d, eax
0x1800020a7  test    eax, eax
0x1800020a9  jnz     loc_180002488
0x1800020af  mov     ecx, [rsp+0C8h+var_88]
0x1800020b3  test    ecx, ecx
0x1800020b5  jz      loc_180002488
0x1800020bb  mov     edx, ecx; uBytes
0x1800020bd  xor     ecx, ecx; uFlags
0x1800020bf  call    cs:__imp_LocalAlloc
0x1800020c5  mov     r12, rax
0x1800020c8  test    rax, rax
0x1800020cb  jnz     short loc_1800020F9
0x1800020cd  lea     edi, [rax+0Eh]
0x1800020d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800020d7  lea     rax, WPP_GLOBAL_Control
0x1800020de  cmp     rcx, rax
0x1800020e1  jz      loc_1800024B9
0x1800020e7  test    byte ptr [rcx+1Ch], 2
0x1800020eb  jz      loc_1800024B9
0x1800020f1  lea     edx, [rdi-2]
0x1800020f4  jmp     loc_18000204A
0x1800020f9  mov     r8d, [rsp+0C8h+var_88]; Size
0x1800020fe  xor     edx, edx; Val
0x180002100  mov     rcx, r12; void *
0x180002103  call    memset_0
0x180002108  lea     rax, [rsp+0C8h+var_88]
0x18000210d  mov     r9d, edi; dwFlags
0x180002110  mov     [rsp+0C8h+pcbData], rax; pcbData
0x180002115  lea     r8, Value; "PropIds"
0x18000211c  mov     [rsp+0C8h+pvData], r12; pvData
0x180002121  xor     edx, edx; lpSubKey
0x180002123  mov     rcx, rbx; hkey
0x180002126  mov     [rsp+0C8h+pdwType], r15; pdwType
0x18000212b  call    cs:__imp_RegGetValueW
0x180002131  mov     edi, eax
0x180002133  test    eax, eax
0x180002135  jz      short loc_180002175
0x180002137  mov     rcx, cs:WPP_GLOBAL_Control
0x18000213e  lea     rax, WPP_GLOBAL_Control
0x180002145  cmp     rcx, rax
0x180002148  jz      loc_18000247D
0x18000214e  test    byte ptr [rcx+1Ch], 2
0x180002152  jz      loc_18000247D
0x180002158  mov     rcx, [rcx+10h]
0x18000215c  lea     r8, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids
0x180002163  mov     edx, 0Dh
0x180002168  mov     r9d, edi
0x18000216b  call    WPP_SF_D
0x180002170  jmp     loc_18000247D
0x180002175  movzx   ecx, word ptr [r12]
0x18000217a  test    cx, cx
0x18000217d  jz      loc_18000247D
0x180002183  mov     rdx, r12
0x180002186  mov     r9d, 2Dh ; '-'
0x18000218c  lea     r8d, [r9-2]
0x180002190  cmp     r8w, cx
0x180002194  jnz     short loc_18000219D
0x180002196  movzx   r13d, word ptr [rdx+2]
0x18000219b  jmp     short loc_1800021A1
0x18000219d  movzx   r13d, cx
0x1800021a1  lea     rax, [rdx+2]
0x1800021a5  mov     dword ptr [rsp+0C8h+pdwType], 10h; cchDest
0x1800021ad  cmovnz  rax, rdx
0x1800021b1  lea     r14, [rsp+0C8h+DestStr]
0x1800021b6  cmp     r9w, r13w
0x1800021ba  mov     ecx, 80h; dwMapFlags
0x1800021bf  lea     r9, [rsp+0C8h+DestStr]; lpDestStr
0x1800021c4  mov     esi, r15d
0x1800021c7  lea     rbp, [rax+2]
0x1800021cb  cmovnz  rbp, rax
0x1800021cf  or      r8d, 0FFFFFFFFh; cchSrc
0x1800021d3  mov     rdx, rbp; lpSrcStr
0x1800021d6  mov     [rsp+0C8h+var_80], rbp
0x1800021db  call    cs:__imp_FoldStringW
0x1800021e1  test    eax, eax
0x1800021e3  jnz     short loc_180002250
0x1800021e5  call    cs:__imp_GetLastError
0x1800021eb  cmp     eax, 7Ah ; 'z'
0x1800021ee  jnz     short loc_180002250
0x1800021f0  xor     r9d, r9d; lpDestStr
0x1800021f3  mov     dword ptr [rsp+0C8h+pdwType], r15d; cchDest
0x1800021f8  or      r8d, 0FFFFFFFFh; cchSrc
0x1800021fc  lea     ecx, [rax+6]; dwMapFlags
0x1800021ff  mov     rdx, rbp; lpSrcStr
0x180002202  call    cs:__imp_FoldStringW
0x180002208  movsxd  rbx, eax
0x18000220b  xor     ecx, ecx; uFlags
0x18000220d  mov     rdx, rbx
0x180002210  add     rdx, rdx; uBytes
0x180002213  call    cs:__imp_LocalAlloc
0x180002219  mov     r14, rax
0x18000221c  test    rax, rax
0x18000221f  jz      loc_180002425
0x180002225  mov     r9, rax; lpDestStr
0x180002228  mov     dword ptr [rsp+0C8h+pdwType], ebx; cchDest
0x18000222c  or      r8d, 0FFFFFFFFh; cchSrc
0x180002230  mov     rdx, rbp; lpSrcStr
0x180002233  mov     ecx, 80h; dwMapFlags
0x180002238  call    cs:__imp_FoldStringW
0x18000223e  test    eax, eax
0x180002240  jnz     short loc_180002250
0x180002242  mov     ebp, r15d
0x180002245  call    cs:__imp_GetLastError
0x18000224b  jmp     loc_180002352
0x180002250  mov     ebp, r15d
0x180002253  mov     rbx, r14
0x180002256  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000225a  inc     rax
0x18000225d  cmp     [r14+rax*2], r15w
0x180002262  jnz     short loc_18000225A
0x180002264  lea     r15, [r14+rax*2]
0x180002268  test    r14, r14
0x18000226b  jz      short loc_180002285
0x18000226d  cmp     rbx, r15
0x180002270  jnb     short loc_180002285
0x180002272  movzx   ecx, word ptr [rbx]; C
0x180002275  call    cs:__imp_iswspace
0x18000227b  test    eax, eax
0x18000227d  jz      short loc_180002285
0x18000227f  add     rbx, 2
0x180002283  jnz     short loc_18000226D
0x180002285  mov     eax, 30h ; '0'
0x18000228a  cmp     ax, [rbx]
0x18000228d  jnz     short loc_1800022FD
0x18000228f  movzx   eax, word ptr [rbx+2]
0x180002293  mov     ecx, 0FFDFh
0x180002298  sub     ax, 58h ; 'X'
0x18000229c  test    cx, ax
0x18000229f  jnz     short loc_1800022FD
0x1800022a1  add     rbx, 4
0x1800022a5  jz      loc_180002342
0x1800022ab  cmp     rbx, r15
0x1800022ae  jnb     loc_180002342
0x1800022b4  movzx   ecx, word ptr [rbx]; C
0x1800022b7  call    cs:__imp_iswxdigit
0x1800022bd  test    eax, eax
0x1800022bf  jz      short loc_180002325
0x1800022c1  movzx   ecx, word ptr [rbx]; C
0x1800022c4  shl     esi, 4
0x1800022c7  mov     ebp, esi
0x1800022c9  call    cs:__imp_iswdigit
0x1800022cf  movzx   ecx, word ptr [rbx]
0x1800022d2  test    eax, eax
0x1800022d4  jz      short loc_1800022DB
0x1800022d6  lea     esi, [rcx-30h]
0x1800022d9  jmp     short loc_1800022E7
0x1800022db  lea     eax, [rcx-41h]
0x1800022de  cmp     ax, 5
0x1800022e2  ja      short loc_1800022EB
0x1800022e4  lea     esi, [rcx-37h]
0x1800022e7  or      esi, ebp
0x1800022e9  jmp     short loc_1800022F0
0x1800022eb  lea     eax, [rcx-57h]
0x1800022ee  or      esi, eax
0x1800022f0  mov     ebp, 1
0x1800022f5  add     rbx, 2
0x1800022f9  jnz     short loc_1800022AB
0x1800022fb  jmp     short loc_180002342
0x1800022fd  cmp     rbx, r15
0x180002300  jnb     short loc_18000231A
0x180002302  movzx   ecx, word ptr [rbx]; C
0x180002305  call    cs:__imp_iswdigit
0x18000230b  test    eax, eax
0x18000230d  jz      short loc_18000231A
0x18000230f  mov     ebp, 1
0x180002314  add     rbx, 2
0x180002318  jnz     short loc_1800022FD
0x18000231a  mov     rcx, r14; String
0x18000231d  call    cs:__imp__wtoi
0x180002323  mov     esi, eax
0x180002325  test    rbx, rbx
0x180002328  jz      short loc_180002342
0x18000232a  cmp     rbx, r15
0x18000232d  jnb     short loc_180002342
0x18000232f  movzx   ecx, word ptr [rbx]; C
0x180002332  call    cs:__imp_iswspace
0x180002338  test    eax, eax
0x18000233a  jz      short loc_180002342
0x18000233c  add     rbx, 2
0x180002340  jnz     short loc_18000232A
0x180002342  xor     r15d, r15d
0x180002345  cmp     r15w, [rbx]
0x180002349  cmovnz  ebp, r15d
0x18000234d  test    r14, r14
0x180002350  jz      short loc_180002365
0x180002352  lea     rax, [rsp+0C8h+DestStr]
0x180002357  cmp     r14, rax
0x18000235a  jz      short loc_180002365
0x18000235c  mov     rcx, r14; hMem
0x18000235f  call    cs:__imp_LocalFree
0x180002365  test    ebp, ebp
0x180002367  jz      loc_180002420
0x18000236d  mov     ecx, cs:dword_180013890
0x180002373  mov     edx, r15d
0x180002376  mov     r9, cs:hMem
0x18000237d  mov     r8d, r15d
0x180002380  test    ecx, ecx
0x180002382  jz      short loc_1800023A2
0x180002384  mov     eax, r8d
0x180002387  cmp     [r9+rax*4], esi
0x18000238b  jnz     short loc_180002393
0x18000238d  cmp     [r9+rax*4], r15d
0x180002391  jnz     short loc_18000239D
0x180002393  inc     r8d
0x180002396  cmp     r8d, ecx
0x180002399  jb      short loc_180002384
0x18000239b  jmp     short loc_1800023A2
0x18000239d  mov     edx, 1
0x1800023a2  mov     eax, 2Dh ; '-'
0x1800023a7  cmp     ax, r13w
0x1800023ab  jnz     short loc_1800023EB
0x1800023ad  test    edx, edx
0x1800023af  jz      short loc_180002420
0x1800023b1  lea     eax, [rcx-1]
0x1800023b4  cmp     r8d, eax
0x1800023b7  jnb     short loc_1800023E1
0x1800023b9  mov     ecx, r8d
0x1800023bc  lea     edx, [r8+1]
0x1800023c0  mov     eax, [r9+rdx*4]
0x1800023c4  mov     r8d, edx
0x1800023c7  mov     [r9+rcx*4], eax
0x1800023cb  mov     ecx, cs:dword_180013890
0x1800023d1  lea     eax, [rcx-1]
0x1800023d4  cmp     edx, eax
0x1800023d6  jnb     short loc_1800023E1
0x1800023d8  mov     r9, cs:hMem
0x1800023df  jmp     short loc_1800023B9
0x1800023e1  dec     ecx
0x1800023e3  mov     cs:dword_180013890, ecx
0x1800023e9  jmp     short loc_180002420
0x1800023eb  test    edx, edx
0x1800023ed  jnz     short loc_180002420
0x1800023ef  lea     edx, [rcx+1]
0x1800023f2  mov     r8d, 2; uFlags
0x1800023f8  shl     rdx, 2; uBytes
0x1800023fc  mov     rcx, r9; hMem
0x1800023ff  call    cs:__imp_LocalReAlloc
0x180002405  test    rax, rax
0x180002408  jz      short loc_18000244C
0x18000240a  mov     ecx, cs:dword_180013890
0x180002410  mov     cs:hMem, rax
0x180002417  mov     [rax+rcx*4], esi
0x18000241a  inc     cs:dword_180013890
0x180002420  mov     rbp, [rsp+0C8h+var_80]
0x180002425  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002429  inc     rax
0x18000242c  cmp     [rbp+rax*2+0], r15w
0x180002432  jnz     short loc_180002429
0x180002434  lea     rdx, ds:2[rax*2]
0x18000243c  add     rdx, rbp
0x18000243f  movzx   ecx, word ptr [rdx]
  ... truncated ...
```
