# ComposeErrorMsg(uint,ulong,uint,int)

- ea: `0x18000c02c`
- end: `0x18000c4d3`
- name: `?ComposeErrorMsg@@YAPEAGIKIH@Z`
- size: `1191`
- prototype: `unsigned __int16 *__fastcall(UINT uID, DWORD dwMessageId, UINT, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017df4`

## callees

- `0x18000c02c`
- `0x18000ca54`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c06e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c0a4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c152`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c342`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c45f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c06e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c0a4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c152`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c342`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c45f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c4a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c4a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c101`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c134`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c497`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c101`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c134`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c497`

## pseudocode

```c
unsigned __int16 *__fastcall ComposeErrorMsg(UINT uID, DWORD dwMessageId, UINT a3)
{
  WCHAR *v5; // rax
  int v6; // r14d
  DWORD v7; // ebx
  DWORD v8; // eax
  DWORD v9; // ebx
  DWORD v10; // ebx
  DWORD v11; // ebx
  DWORD v12; // ebx
  DWORD v13; // ebx
  DWORD v14; // ebx
  bool v15; // zf
  DWORD v16; // ebx
  DWORD v17; // ebx
  DWORD v18; // ebx
  bool v19; // zf
  DWORD v20; // ebx
  DWORD v21; // ebx
  DWORD v22; // ebx
  bool v23; // zf
  DWORD v24; // ebx
  DWORD v25; // ebx
  DWORD v26; // ebx
  DWORD v27; // ebx
  DWORD v28; // ebx
  bool v29; // zf
  UINT v30; // edx
  DWORD v31; // ebx
  DWORD v32; // ebx
  DWORD v33; // ebx
  DWORD v34; // ebx
  DWORD v35; // ebx
  DWORD v36; // ebx
  DWORD v37; // ebx
  DWORD v38; // ebx
  DWORD v39; // ebx
  DWORD v40; // ebx
  DWORD v41; // ebx
  DWORD v42; // ebx
  DWORD v43; // ebx
  DWORD v44; // ebx
  DWORD v45; // ebx
  DWORD v46; // ebx
  DWORD v47; // ebx
  DWORD v48; // ebx
  WCHAR lpBuffer[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR v51[4]; // [rsp+48h] [rbp-B8h] BYREF
  va_list Arguments; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v53; // [rsp+58h] [rbp-A8h]
  WCHAR *v54; // [rsp+68h] [rbp-98h]
  unsigned __int16 v55[32]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v56[32]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v57[80]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR v58[256]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR Buffer[256]; // [rsp+390h] [rbp+290h] BYREF
  WCHAR Source[256]; // [rsp+590h] [rbp+490h] BYREF

  if ( !LoadStringW(g_hInstance, uID, Buffer, 256) )
    return 0;
  v5 = 0;
  v6 = 0;
  *(_QWORD *)lpBuffer = 0;
  v7 = dwMessageId;
  if ( !dwMessageId )
    goto LABEL_11;
  if ( !LoadStringW(g_hInstance, 0x481u, v56, 32) )
    return 0;
  StringCchPrintfW(v55, 0x20u, v56, dwMessageId);
  if ( (((dwMessageId & 0x1FFF0000) - 458752) & 0xFFFEFFFF) == 0 )
    v7 = (unsigned __int16)dwMessageId;
  v8 = FormatMessageW(0x1100u, 0, v7, 0, lpBuffer, 1u, 0);
  if ( !v8 )
  {
    v8 = FormatMessageW(0x900u, g_hInstance, dwMessageId, 0, lpBuffer, 1u, 0);
    if ( !v8 )
    {
      if ( LoadStringW(g_hInstance, 0x482u, v57, 80) )
      {
        v5 = v57;
        *(_QWORD *)lpBuffer = v57;
        goto LABEL_11;
      }
      return 0;
    }
  }
  v6 = 1;
  *(_DWORD *)(*(_QWORD *)lpBuffer + 2LL * v8 - 4) = 0;
  v5 = *(WCHAR **)lpBuffer;
LABEL_11:
  *(_QWORD *)v51 = 0;
  v54 = 0;
  Arguments = (va_list)Buffer;
  v53 = 0;
  if ( a3 )
    goto LABEL_58;
  if ( !v7 )
    goto LABEL_45;
  if ( v7 <= 0x9B )
  {
    if ( v7 == 155 )
      goto LABEL_87;
    if ( v7 > 0x3A )
    {
      if ( v7 > 0x59 )
      {
        if ( v7 == 100 )
          goto LABEL_87;
        v29 = v7 == 113;
      }
      else
      {
        if ( v7 == 89 )
          goto LABEL_87;
        if ( v7 <= 0x43 )
        {
          if ( v7 == 67 )
            goto LABEL_79;
          v21 = v7 - 59;
          if ( !v21 )
            goto LABEL_79;
          v22 = v21 - 1;
          if ( !v22 )
            goto LABEL_79;
          v24 = v22 - 4;
          v23 = v24 == 0;
          goto LABEL_77;
        }
        v25 = v7 - 68;
        if ( !v25 )
          goto LABEL_87;
        v26 = v25 - 1;
        if ( !v26 )
          goto LABEL_87;
        v27 = v26 - 1;
        if ( !v27 )
          goto LABEL_79;
        v28 = v27 - 1;
        if ( !v28 )
          goto LABEL_79;
        v29 = v28 == 13;
      }
      if ( !v29 )
        goto LABEL_45;
      goto LABEL_87;
    }
    if ( v7 == 58 )
      goto LABEL_79;
    if ( v7 <= 0x32 )
    {
      if ( v7 != 50 )
      {
        v9 = v7 - 2;
        if ( !v9 )
          goto LABEL_68;
        v10 = v9 - 1;
        if ( !v10 )
          goto LABEL_68;
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 3;
            if ( v13 )
            {
              v14 = v13 - 6;
              if ( v14 )
              {
                v15 = v14 == 1;
                goto LABEL_67;
              }
            }
            goto LABEL_87;
          }
LABEL_68:
          a3 = 1155;
          goto LABEL_58;
        }
LABEL_87:
        a3 = 1169;
        goto LABEL_58;
      }
LABEL_79:
      a3 = 1168;
      goto LABEL_58;
    }
    v16 = v7 - 51;
    if ( !v16 )
      goto LABEL_79;
    v17 = v16 - 1;
    if ( !v17 )
      goto LABEL_79;
    v18 = v17 - 1;
    if ( !v18 )
      goto LABEL_79;
    v20 = v18 - 1;
    v19 = v20 == 0;
LABEL_75:
    if ( v19 )
      goto LABEL_79;
    v24 = v20 - 1;
    v23 = v24 == 0;
LABEL_77:
    if ( !v23 && v24 - 1 > 1 )
      goto LABEL_45;
    goto LABEL_79;
  }
  if ( v7 <= 0x4BA )
  {
    if ( v7 == 1210 )
      goto LABEL_68;
    if ( v7 > 0x3F5 )
    {
      v36 = v7 - 1015;
      if ( v36 )
      {
        v37 = v36 - 1;
        if ( v37 )
        {
          v38 = v37 - 2;
          if ( v38 )
          {
            v39 = v38 - 96;
            if ( !v39 )
              goto LABEL_87;
            v40 = v39 - 43;
            if ( v40 )
            {
              v15 = v40 == 46;
LABEL_67:
              if ( v15 )
                goto LABEL_68;
LABEL_45:
              if ( dwMessageId )
              {
                *((_QWORD *)&v53 + 1) = v5;
                *(_QWORD *)&v53 = v55;
                v30 = 1150;
              }
              else
              {
                v30 = 1152;
              }
LABEL_90:
              if ( LoadStringW(g_hInstance, v30, Source, 256) )
                FormatMessageW(0x2500u, Source, 0, 0, v51, 1u, &Arguments);
              goto LABEL_92;
            }
          }
        }
      }
    }
    else if ( v7 != 1013 )
    {
      v31 = v7 - 161;
      if ( !v31 )
        goto LABEL_68;
      v32 = v31 - 3;
      if ( !v32 )
        goto LABEL_87;
      v33 = v32 - 103;
      if ( !v33 )
        goto LABEL_68;
      v34 = v33 - 742;
      if ( v34 )
      {
        v35 = v34 - 1;
        if ( v35 )
        {
          if ( v35 - 1 > 1 )
            goto LABEL_45;
        }
      }
    }
    a3 = 1166;
    goto LABEL_58;
  }
  if ( v7 <= 0x4D6 )
  {
    if ( v7 == 1238 )
      goto LABEL_79;
    v41 = v7 - 1215;
    if ( !v41 )
      goto LABEL_68;
    v42 = v41 - 5;
    if ( !v42 )
      goto LABEL_79;
    v43 = v42 - 2;
    if ( !v43 )
      goto LABEL_79;
    v20 = v43 - 9;
    v19 = v20 == 0;
    goto LABEL_75;
  }
  v44 = v7 - 1311;
  if ( !v44 )
    goto LABEL_79;
  v45 = v44 - 139;
  if ( !v45 )
    goto LABEL_87;
  v46 = v45 - 1;
  if ( !v46 )
    goto LABEL_87;
  v47 = v46 - 1;
  if ( !v47 )
    goto LABEL_87;
  v48 = v47 - 269;
  if ( !v48 )
    goto LABEL_87;
  if ( v48 != 32 )
    goto LABEL_45;
  a3 = 1175;
LABEL_58:
  if ( LoadStringW(g_hInstance, a3, v58, 256) )
  {
    if ( dwMessageId )
    {
      v30 = 1149;
      *(_QWORD *)&v53 = v55;
      *((_QWORD *)&v53 + 1) = *(_QWORD *)lpBuffer;
      v54 = v58;
    }
    else
    {
      v30 = 1151;
      *(_QWORD *)&v53 = v58;
    }
    goto LABEL_90;
  }
LABEL_92:
  if ( v6 )
    LocalFree(*(HLOCAL *)lpBuffer);
  return *(unsigned __int16 **)v51;
}

```

## disassembly

```asm
0x18000c02c  push    rbp
0x18000c02e  push    rbx
0x18000c02f  push    rsi
0x18000c030  push    rdi
0x18000c031  push    r14
0x18000c033  lea     rbp, [rsp-6A0h]
0x18000c03b  sub     rsp, 7A0h
0x18000c042  mov     rax, cs:__security_cookie
0x18000c049  xor     rax, rsp
0x18000c04c  mov     [rbp+6C0h+var_30], rax
0x18000c053  mov     esi, edx
0x18000c055  mov     edi, r8d
0x18000c058  mov     edx, ecx; uID
0x18000c05a  lea     r8, [rbp+6C0h+Buffer]; lpBuffer
0x18000c061  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000c068  mov     r9d, 100h; cchBufferMax
0x18000c06e  call    cs:__imp_LoadStringW
0x18000c074  test    eax, eax
0x18000c076  jz      loc_18000C4B4
0x18000c07c  xor     eax, eax
0x18000c07e  xor     r14d, r14d
0x18000c081  mov     qword ptr [rsp+7C0h+var_780], rax
0x18000c086  mov     ebx, esi
0x18000c088  test    esi, esi
0x18000c08a  jz      loc_18000C183
0x18000c090  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000c097  lea     r9d, [r14+20h]; cchBufferMax
0x18000c09b  lea     r8, [rbp+6C0h+var_710]; lpBuffer
0x18000c09f  mov     edx, 481h; uID
0x18000c0a4  call    cs:__imp_LoadStringW
0x18000c0aa  test    eax, eax
0x18000c0ac  jz      loc_18000C4B4
0x18000c0b2  mov     r9d, esi
0x18000c0b5  lea     r8, [rbp+6C0h+var_710]; unsigned __int16 *
0x18000c0b9  lea     edx, [r14+20h]; unsigned __int64
0x18000c0bd  lea     rcx, [rsp+7C0h+var_750]; unsigned __int16 *
0x18000c0c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000c0c7  mov     eax, esi
0x18000c0c9  and     eax, 1FFF0000h
0x18000c0ce  sub     eax, 70000h
0x18000c0d3  test    eax, 0FFFEFFFFh
0x18000c0d8  jnz     short loc_18000C0DD
0x18000c0da  movzx   ebx, si
0x18000c0dd  mov     [rsp+7C0h+Arguments], r14; Arguments
0x18000c0e2  lea     rax, [rsp+7C0h+var_780]
0x18000c0e7  mov     [rsp+7C0h+nSize], 1; nSize
0x18000c0ef  xor     r9d, r9d; dwLanguageId
0x18000c0f2  mov     r8d, ebx; dwMessageId
0x18000c0f5  mov     [rsp+7C0h+lpBuffer], rax; lpBuffer
0x18000c0fa  xor     edx, edx; lpSource
0x18000c0fc  mov     ecx, 1100h; dwFlags
0x18000c101  call    cs:__imp_FormatMessageW
0x18000c107  test    eax, eax
0x18000c109  jnz     short loc_18000C16B
0x18000c10b  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; lpSource
0x18000c112  lea     rax, [rsp+7C0h+var_780]
0x18000c117  mov     [rsp+7C0h+Arguments], r14; Arguments
0x18000c11c  xor     r9d, r9d; dwLanguageId
0x18000c11f  mov     [rsp+7C0h+nSize], 1; nSize
0x18000c127  mov     r8d, esi; dwMessageId
0x18000c12a  mov     ecx, 900h; dwFlags
0x18000c12f  mov     [rsp+7C0h+lpBuffer], rax; lpBuffer
0x18000c134  call    cs:__imp_FormatMessageW
0x18000c13a  test    eax, eax
0x18000c13c  jnz     short loc_18000C16B
0x18000c13e  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000c145  lea     r9d, [rax+50h]; cchBufferMax
0x18000c149  lea     r8, [rbp+6C0h+var_6D0]; lpBuffer
0x18000c14d  mov     edx, 482h; uID
0x18000c152  call    cs:__imp_LoadStringW
0x18000c158  test    eax, eax
0x18000c15a  jz      loc_18000C4B4
0x18000c160  lea     rax, [rbp+6C0h+var_6D0]
0x18000c164  mov     qword ptr [rsp+7C0h+var_780], rax
0x18000c169  jmp     short loc_18000C183
0x18000c16b  mov     rcx, qword ptr [rsp+7C0h+var_780]
0x18000c170  mov     r14d, 1
0x18000c176  mov     edx, eax
0x18000c178  xor     eax, eax
0x18000c17a  mov     [rcx+rdx*2-4], eax
0x18000c17e  mov     rax, qword ptr [rsp+7C0h+var_780]
0x18000c183  mov     qword ptr [rsp+7C0h+var_778], 0
0x18000c18c  xorps   xmm0, xmm0
0x18000c18f  mov     [rsp+7C0h+var_758], 0
0x18000c198  lea     rcx, [rbp+6C0h+Buffer]
0x18000c19f  mov     [rsp+7C0h+var_770], rcx
0x18000c1a4  movdqu  [rsp+7C0h+var_768], xmm0
0x18000c1aa  test    edi, edi
0x18000c1ac  jnz     loc_18000C32C
0x18000c1b2  test    ebx, ebx
0x18000c1b4  jz      loc_18000C2AF
0x18000c1ba  mov     ecx, 9Bh
0x18000c1bf  cmp     ebx, ecx
0x18000c1c1  ja      loc_18000C2D0
0x18000c1c7  jz      loc_18000C429
0x18000c1cd  cmp     ebx, 3Ah ; ':'
0x18000c1d0  ja      short loc_18000C244
0x18000c1d2  jz      loc_18000C3EA
0x18000c1d8  cmp     ebx, 32h ; '2'
0x18000c1db  ja      short loc_18000C221
0x18000c1dd  jz      loc_18000C3EA
0x18000c1e3  sub     ebx, 2
0x18000c1e6  jz      loc_18000C3AB
0x18000c1ec  sub     ebx, 1
0x18000c1ef  jz      loc_18000C3AB
0x18000c1f5  sub     ebx, 1
0x18000c1f8  jz      loc_18000C429
0x18000c1fe  sub     ebx, 1
0x18000c201  jz      loc_18000C3AB
0x18000c207  sub     ebx, 3
0x18000c20a  jz      loc_18000C429
0x18000c210  sub     ebx, 6
0x18000c213  jz      loc_18000C429
0x18000c219  cmp     ebx, 1
0x18000c21c  jmp     loc_18000C3A5
0x18000c221  sub     ebx, 33h ; '3'
0x18000c224  jz      loc_18000C3EA
0x18000c22a  sub     ebx, 1
0x18000c22d  jz      loc_18000C3EA
0x18000c233  sub     ebx, 1
0x18000c236  jz      loc_18000C3EA
0x18000c23c  sub     ebx, 1
0x18000c23f  jmp     loc_18000C3D5
0x18000c244  cmp     ebx, 59h ; 'Y'
0x18000c247  ja      short loc_18000C29D
0x18000c249  jz      loc_18000C429
0x18000c24f  cmp     ebx, 43h ; 'C'
0x18000c252  ja      short loc_18000C274
0x18000c254  jz      loc_18000C3EA
0x18000c25a  sub     ebx, 3Bh ; ';'
0x18000c25d  jz      loc_18000C3EA
0x18000c263  sub     ebx, 1
0x18000c266  jz      loc_18000C3EA
0x18000c26c  sub     ebx, 4
0x18000c26f  jmp     loc_18000C3DA
0x18000c274  sub     ebx, 44h ; 'D'
0x18000c277  jz      loc_18000C429
0x18000c27d  sub     ebx, 1
0x18000c280  jz      loc_18000C429
0x18000c286  sub     ebx, 1
0x18000c289  jz      loc_18000C3EA
0x18000c28f  sub     ebx, 1
0x18000c292  jz      loc_18000C3EA
0x18000c298  cmp     ebx, 0Dh
0x18000c29b  jmp     short loc_18000C2A9
0x18000c29d  cmp     ebx, 64h ; 'd'
0x18000c2a0  jz      loc_18000C429
0x18000c2a6  cmp     ebx, 71h ; 'q'
0x18000c2a9  jz      loc_18000C429
0x18000c2af  test    esi, esi
0x18000c2b1  jz      loc_18000C433
0x18000c2b7  lea     rcx, [rsp+7C0h+var_750]
0x18000c2bc  mov     qword ptr [rsp+7C0h+var_768+8], rax
0x18000c2c1  mov     qword ptr [rsp+7C0h+var_768], rcx
0x18000c2c6  mov     edx, 47Eh
0x18000c2cb  jmp     loc_18000C44B
0x18000c2d0  mov     ecx, 4BAh
0x18000c2d5  cmp     ebx, ecx
0x18000c2d7  ja      loc_18000C3B5
0x18000c2dd  jz      loc_18000C3AB
0x18000c2e3  mov     ecx, 3F5h
0x18000c2e8  cmp     ebx, ecx
0x18000c2ea  ja      loc_18000C382
0x18000c2f0  jz      short loc_18000C327
0x18000c2f2  sub     ebx, 0A1h
0x18000c2f8  jz      loc_18000C3AB
0x18000c2fe  sub     ebx, 3
0x18000c301  jz      loc_18000C429
0x18000c307  sub     ebx, 67h ; 'g'
0x18000c30a  jz      loc_18000C3AB
0x18000c310  sub     ebx, 2E6h
0x18000c316  jz      short loc_18000C327
0x18000c318  sub     ebx, 1
0x18000c31b  jz      short loc_18000C327
0x18000c31d  sub     ebx, 1
0x18000c320  jz      short loc_18000C327
0x18000c322  cmp     ebx, 1
0x18000c325  jnz     short loc_18000C2AF
0x18000c327  mov     edi, 48Eh
0x18000c32c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000c333  lea     r8, [rbp+6C0h+var_630]; lpBuffer
0x18000c33a  mov     r9d, 100h; cchBufferMax
0x18000c340  mov     edx, edi; uID
0x18000c342  call    cs:__imp_LoadStringW
0x18000c348  test    eax, eax
0x18000c34a  jz      loc_18000C49D
0x18000c350  test    esi, esi
0x18000c352  jz      loc_18000C43A
0x18000c358  lea     rax, [rsp+7C0h+var_750]
0x18000c35d  mov     edx, 47Dh
0x18000c362  mov     qword ptr [rsp+7C0h+var_768], rax
0x18000c367  mov     rax, qword ptr [rsp+7C0h+var_780]
0x18000c36c  mov     qword ptr [rsp+7C0h+var_768+8], rax
0x18000c371  lea     rax, [rbp+6C0h+var_630]
0x18000c378  mov     [rsp+7C0h+var_758], rax
0x18000c37d  jmp     loc_18000C44B
0x18000c382  sub     ebx, 3F7h
0x18000c388  jz      short loc_18000C327
0x18000c38a  sub     ebx, 1
0x18000c38d  jz      short loc_18000C327
0x18000c38f  sub     ebx, 2
0x18000c392  jz      short loc_18000C327
0x18000c394  sub     ebx, 60h ; '`'
0x18000c397  jz      loc_18000C429
0x18000c39d  sub     ebx, 2Bh ; '+'
0x18000c3a0  jz      short loc_18000C327
0x18000c3a2  cmp     ebx, 2Eh ; '.'
0x18000c3a5  jnz     loc_18000C2AF
0x18000c3ab  mov     edi, 483h
0x18000c3b0  jmp     loc_18000C32C
0x18000c3b5  mov     ecx, 4D6h
0x18000c3ba  cmp     ebx, ecx
0x18000c3bc  ja      short loc_18000C3F4
0x18000c3be  jz      short loc_18000C3EA
0x18000c3c0  sub     ebx, 4BFh
0x18000c3c6  jz      short loc_18000C3AB
0x18000c3c8  sub     ebx, 5
0x18000c3cb  jz      short loc_18000C3EA
0x18000c3cd  sub     ebx, 2
0x18000c3d0  jz      short loc_18000C3EA
0x18000c3d2  sub     ebx, 9
0x18000c3d5  jz      short loc_18000C3EA
0x18000c3d7  sub     ebx, 1
0x18000c3da  jz      short loc_18000C3EA
0x18000c3dc  sub     ebx, 1
0x18000c3df  jz      short loc_18000C3EA
0x18000c3e1  cmp     ebx, 1
0x18000c3e4  jnz     loc_18000C2AF
0x18000c3ea  mov     edi, 490h
0x18000c3ef  jmp     loc_18000C32C
0x18000c3f4  sub     ebx, 51Fh
0x18000c3fa  jz      short loc_18000C3EA
0x18000c3fc  sub     ebx, 8Bh
0x18000c402  jz      short loc_18000C429
0x18000c404  sub     ebx, 1
0x18000c407  jz      short loc_18000C429
0x18000c409  sub     ebx, 1
0x18000c40c  jz      short loc_18000C429
0x18000c40e  sub     ebx, 10Dh
0x18000c414  jz      short loc_18000C429
0x18000c416  cmp     ebx, 20h ; ' '
0x18000c419  jnz     loc_18000C2AF
0x18000c41f  mov     edi, 497h
0x18000c424  jmp     loc_18000C32C
0x18000c429  mov     edi, 491h
0x18000c42e  jmp     loc_18000C32C
0x18000c433  mov     edx, 480h
0x18000c438  jmp     short loc_18000C44B
0x18000c43a  lea     rax, [rbp+6C0h+var_630]
0x18000c441  mov     edx, 47Fh; uID
0x18000c446  mov     qword ptr [rsp+7C0h+var_768], rax
0x18000c44b  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000c452  lea     r8, [rbp+6C0h+Source]; lpBuffer
0x18000c459  mov     r9d, 100h; cchBufferMax
0x18000c45f  call    cs:__imp_LoadStringW
0x18000c465  test    eax, eax
0x18000c467  jz      short loc_18000C49D
0x18000c469  lea     rax, [rsp+7C0h+var_770]
0x18000c46e  xor     r9d, r9d; dwLanguageId
0x18000c471  mov     [rsp+7C0h+Arguments], rax; Arguments
0x18000c476  lea     rdx, [rbp+6C0h+Source]; lpSource
0x18000c47d  lea     rax, [rsp+7C0h+var_778]
0x18000c482  mov     [rsp+7C0h+nSize], 1; nSize
0x18000c48a  xor     r8d, r8d; dwMessageId
0x18000c48d  mov     [rsp+7C0h+lpBuffer], rax; lpBuffer
0x18000c492  mov     ecx, 2500h; dwFlags
0x18000c497  call    cs:__imp_FormatMessageW
0x18000c49d  test    r14d, r14d
0x18000c4a0  jz      short loc_18000C4AD
0x18000c4a2  mov     rcx, qword ptr [rsp+7C0h+var_780]; hMem
0x18000c4a7  call    cs:__imp_LocalFree
0x18000c4ad  mov     rax, qword ptr [rsp+7C0h+var_778]
0x18000c4b2  jmp     short loc_18000C4B6
0x18000c4b4  xor     eax, eax
0x18000c4b6  mov     rcx, [rbp+6C0h+var_30]
0x18000c4bd  xor     rcx, rsp; StackCookie
0x18000c4c0  call    __security_check_cookie
0x18000c4c5  add     rsp, 7A0h
0x18000c4cc  pop     r14
0x18000c4ce  pop     rdi
0x18000c4cf  pop     rsi
0x18000c4d0  pop     rbx
0x18000c4d1  pop     rbp
0x18000c4d2  retn
```
