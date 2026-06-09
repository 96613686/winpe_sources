# WriteStream

- ea: `0x10014c50`
- end: `0x10015083`
- name: `WriteStream`
- size: `1075`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x10015090`

## callees

- `0x100147f0`
- `0x10014900`
- `0x10014c50`
- `0x1002580a`
- `0x1002611f`
- `0x10035510`
- `0x1003669c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10014e04`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10014e19`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10014f5b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10014e04`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10014e19`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10014f5b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10014d90`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10014dab`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10014ed7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10014ef2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10014d90`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10014dab`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10014ed7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10014ef2`

## pseudocode

```c
int __fastcall WriteStream(int a1, void *a2, __int16 *a3, int a4)
{
  __int16 *v4; // edx
  __int16 v5; // ax
  __int16 v6; // dx
  char *v7; // ebx
  __int16 v8; // si
  int v9; // esi
  char *v10; // ecx
  __int16 v11; // ax
  __int16 v12; // ax
  int v13; // edi
  int v14; // eax
  UINT v15; // edx
  size_t v16; // esi
  int v17; // kr00_4
  UINT v18; // esi
  __int16 v19; // ax
  __int16 v20; // cx
  int v21; // eax
  __int16 v22; // di
  UINT v23; // edx
  size_t v24; // esi
  int v25; // kr04_4
  UINT v26; // esi
  __int16 v27; // ax
  int v28; // edi
  int v29; // eax
  int v30; // esi
  int *v31; // ecx
  int v32; // eax
  int result; // eax
  CHAR *v34; // [esp-10h] [ebp-440h]
  CHAR *v35; // [esp-10h] [ebp-440h]
  int v36; // [esp-Ch] [ebp-43Ch]
  int v37; // [esp-Ch] [ebp-43Ch]
  int v38; // [esp+10h] [ebp-420h]
  __int16 v40; // [esp+18h] [ebp-418h]
  __int16 *v41; // [esp+1Ch] [ebp-414h]
  int v43; // [esp+24h] [ebp-40Ch] BYREF
  WCHAR WideCharStr[256]; // [esp+28h] [ebp-408h] BYREF
  WCHAR v45[258]; // [esp+228h] [ebp-208h] BYREF

  v4 = a3;
  v41 = a3;
  while ( 1 )
  {
    v5 = *v4;
    v6 = v4[1];
    v7 = (char *)pExcelRecordBuffer;
    v8 = v5;
    v38 = v6;
    a4 += -4 - v6;
    if ( v5 > 561 )
    {
      if ( v5 != 1054 )
      {
LABEL_20:
        v12 = v6;
        LOWORD(v43) = v8;
        v7 = (char *)(v41 + 2);
        v9 = a1;
        HIWORD(v43) = v6;
        goto LABEL_30;
      }
      v21 = *((unsigned __int8 *)v41 + 6);
      v22 = v41[2];
      v23 = *(_DWORD *)(a1 + 24);
      v24 = 2 * v21;
      if ( v23 == 1200 )
        MultiByteToWideChar(0, 0, (LPCCH)v41 + 7, v21, WideCharStr, 256);
      else
        MultiByteToWideChar(v23, 0, (LPCCH)v41 + 7, v21, WideCharStr, 256);
      AdjustFormatString(a2, WideCharStr, v24, v45);
      v25 = wcslen(v45);
      v26 = *(_DWORD *)(a1 + 24);
      v37 = 2 * v25;
      v35 = v7 + 3;
      if ( v26 == 1200 )
        v27 = WideCharToMultiByte(0, 0, v45, v25, v35, v37, 0, 0);
      else
        v27 = WideCharToMultiByte(v26, 0, v45, v25, v35, v37, 0, 0);
      v7[2] = v27;
      v20 = 1054;
      *(_WORD *)v7 = v22;
      v12 = v27 + 3;
      goto LABEL_28;
    }
    if ( v5 == 561 )
    {
      v9 = a1;
      AdjustFontName(*(_DWORD *)(a1 + 4), *(_DWORD *)(a1 + 24), v41 + 2, (char *)pExcelRecordBuffer);
      LOWORD(v43) = 561;
      v12 = strlen(v7 + 7) + 7;
LABEL_29:
      HIWORD(v43) = v12;
      goto LABEL_30;
    }
    if ( v5 == 30 )
    {
      v13 = a1;
      v14 = *((unsigned __int8 *)v41 + 4);
      v15 = *(_DWORD *)(a1 + 24);
      v16 = 2 * v14;
      if ( v15 == 1200 )
      {
        MultiByteToWideChar(0, 0, (LPCCH)v41 + 5, v14, WideCharStr, 256);
      }
      else
      {
        MultiByteToWideChar(v15, 0, (LPCCH)v41 + 5, v14, WideCharStr, 256);
        v13 = a1;
      }
      AdjustFormatString(a2, WideCharStr, v16, v45);
      v17 = wcslen(v45);
      v18 = *(_DWORD *)(v13 + 24);
      v36 = 2 * v17;
      v34 = v7 + 1;
      if ( v18 == 1200 )
        v19 = WideCharToMultiByte(0, 0, v45, v17, v34, v36, 0, 0);
      else
        v19 = WideCharToMultiByte(v18, 0, v45, v17, v34, v36, 0, 0);
      *v7 = v19;
      v20 = 30;
      v12 = v19 + 1;
LABEL_28:
      v9 = a1;
      LOWORD(v43) = v20;
      goto LABEL_29;
    }
    if ( v5 != 49 )
      goto LABEL_20;
    v9 = a1;
    AdjustFontName(*(_DWORD *)(a1 + 4), *(_DWORD *)(a1 + 24), v41 + 2, (char *)pExcelRecordBuffer);
    if ( *(int *)(a1 + 4) < 8 )
    {
      LOWORD(v43) = 49;
      HIWORD(v43) = strlen(v7 + 15) + 15;
      v12 = HIWORD(v43);
    }
    else
    {
      v10 = v7 + 16;
      do
      {
        v11 = *(_WORD *)v10;
        v10 += 2;
      }
      while ( v11 );
      LOWORD(v43) = 49;
      HIWORD(v43) = 2 * ((v10 - (v7 + 18)) >> 1) + 16;
      v12 = HIWORD(v43);
    }
LABEL_30:
    v28 = *(_DWORD *)(v9 + 40);
    v40 = v12;
    if ( !v28 )
      break;
    v29 = MemAllocate(v12 + 11);
    v30 = v29;
    if ( !v29 )
      return -2;
    *(_DWORD *)(v29 + 4) = v43;
    memcpy((void *)(v29 + 8), v7, v40);
    v31 = *(int **)(v28 + 4);
    if ( v31 )
    {
      while ( *v31 )
        v31 = (int *)*v31;
      *v31 = v30;
    }
    else
    {
      *(_DWORD *)(v28 + 4) = v30;
    }
LABEL_39:
    v4 = (__int16 *)((char *)v41 + v38 + 4);
    v41 = v4;
    if ( !a4 )
      return 0;
  }
  v32 = BFWriteFile(*(_DWORD *)(v9 + 20), (char *)&v43, 4u);
  if ( !v32 )
  {
    v32 = BFWriteFile(*(_DWORD *)(v9 + 20), v7, SHIWORD(v43));
    if ( !v32 )
      goto LABEL_39;
  }
  result = dword_10001970[abs32(v32)];
  if ( result == -10 )
    return -10;
  return result;
}

```

## disassembly

```asm
0x10014c50  mov     edi, edi
0x10014c52  push    ebp
0x10014c53  mov     ebp, esp
0x10014c55  sub     esp, 424h
0x10014c5b  mov     eax, ___security_cookie
0x10014c60  xor     eax, ebp
0x10014c62  mov     [ebp+var_4], eax
0x10014c65  push    ebx
0x10014c66  push    esi
0x10014c67  mov     [ebp+Src], edx
0x10014c6d  mov     edx, [ebp+arg_0]
0x10014c70  push    edi
0x10014c71  mov     [ebp+var_410], ecx
0x10014c77  mov     [ebp+var_414], edx
0x10014c7d  nop     dword ptr [eax]
0x10014c80  movzx   eax, word ptr [edx]
0x10014c83  movzx   edx, word ptr [edx+2]
0x10014c87  mov     ecx, eax
0x10014c89  mov     ebx, _pExcelRecordBuffer
0x10014c8f  mov     esi, eax
0x10014c91  movsx   eax, dx
0x10014c94  mov     edi, edx
0x10014c96  mov     [ebp+var_420], eax
0x10014c9c  mov     eax, 0FFFFFFFCh
0x10014ca1  sub     eax, [ebp+var_420]
0x10014ca7  add     [ebp+arg_4], eax
0x10014caa  mov     eax, 231h
0x10014caf  cmp     cx, ax
0x10014cb2  jg      loc_10014E6D
0x10014cb8  jz      loc_10014E2C
0x10014cbe  cmp     cx, 1Eh
0x10014cc2  jz      loc_10014D5E
0x10014cc8  cmp     cx, 31h ; '1'
0x10014ccc  jnz     loc_10014E77
0x10014cd2  mov     esi, [ebp+var_410]
0x10014cd8  mov     eax, [ebp+var_414]
0x10014cde  push    ebx; void *
0x10014cdf  add     eax, 4
0x10014ce2  mov     edx, [esi+18h]
0x10014ce5  mov     ecx, [esi+4]
0x10014ce8  push    eax; Src
0x10014ce9  call    AdjustFontName
0x10014cee  cmp     dword ptr [esi+4], 8
0x10014cf2  jl      short loc_10014D31
0x10014cf4  lea     ecx, [ebx+10h]
0x10014cf7  lea     edx, [ecx+2]
0x10014cfa  nop     word ptr [eax+eax+00h]
0x10014d00  mov     ax, [ecx]
0x10014d03  add     ecx, 2
0x10014d06  test    ax, ax
0x10014d09  jnz     short loc_10014D00
0x10014d0b  sub     ecx, edx
0x10014d0d  mov     eax, 31h ; '1'
0x10014d12  sar     ecx, 1
0x10014d14  mov     word ptr [ebp+var_40C], ax
0x10014d1b  lea     eax, ds:10h[ecx*2]
0x10014d22  mov     word ptr [ebp+var_40C+2], ax
0x10014d29  movzx   eax, ax
0x10014d2c  jmp     loc_10014F83
0x10014d31  lea     ecx, [ebx+0Fh]
0x10014d34  lea     edx, [ecx+1]
0x10014d37  mov     al, [ecx]
0x10014d39  inc     ecx
0x10014d3a  test    al, al
0x10014d3c  jnz     short loc_10014D37
0x10014d3e  sub     ecx, edx
0x10014d40  mov     eax, 31h ; '1'
0x10014d45  mov     word ptr [ebp+var_40C], ax
0x10014d4c  lea     eax, [ecx+0Fh]
0x10014d4f  mov     word ptr [ebp+var_40C+2], ax
0x10014d56  movzx   eax, ax
0x10014d59  jmp     loc_10014F83
0x10014d5e  mov     ecx, [ebp+var_414]
0x10014d64  mov     edi, [ebp+var_410]
0x10014d6a  push    100h; cchWideChar
0x10014d6f  movzx   eax, byte ptr [ecx+4]
0x10014d73  add     ecx, 5
0x10014d76  mov     edx, [edi+18h]
0x10014d79  lea     esi, [eax+eax]
0x10014d7c  cmp     edx, 4B0h
0x10014d82  jz      short loc_10014D9E
0x10014d84  lea     edi, [ebp+WideCharStr]
0x10014d8a  push    edi; lpWideCharStr
0x10014d8b  push    eax; cbMultiByte
0x10014d8c  push    ecx; lpMultiByteStr
0x10014d8d  push    0; dwFlags
0x10014d8f  push    edx; CodePage
0x10014d90  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x10014d96  mov     edi, [ebp+var_410]
0x10014d9c  jmp     short loc_10014DB1
0x10014d9e  lea     edx, [ebp+WideCharStr]
0x10014da4  push    edx; lpWideCharStr
0x10014da5  push    eax; cbMultiByte
0x10014da6  push    ecx; lpMultiByteStr
0x10014da7  push    0; dwFlags
0x10014da9  push    0; CodePage
0x10014dab  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x10014db1  mov     ecx, [ebp+Src]; Src
0x10014db7  lea     eax, [ebp+var_208]
0x10014dbd  push    eax; void *
0x10014dbe  push    esi; Size
0x10014dbf  lea     edx, [ebp+WideCharStr]; void *
0x10014dc5  call    AdjustFormatString
0x10014dca  lea     ecx, [ebp+var_208]
0x10014dd0  lea     edx, [ecx+2]
0x10014dd3  mov     ax, [ecx]
0x10014dd6  add     ecx, 2
0x10014dd9  test    ax, ax
0x10014ddc  jnz     short loc_10014DD3
0x10014dde  mov     esi, [edi+18h]
0x10014de1  sub     ecx, edx
0x10014de3  sar     ecx, 1
0x10014de5  lea     edx, [ebx+1]
0x10014de8  push    0; lpUsedDefaultChar
0x10014dea  push    0; lpDefaultChar
0x10014dec  lea     eax, [ecx+ecx]
0x10014def  push    eax; cbMultiByte
0x10014df0  lea     eax, [ebp+var_208]
0x10014df6  push    edx; lpMultiByteStr
0x10014df7  push    ecx; cchWideChar
0x10014df8  push    eax; lpWideCharStr
0x10014df9  push    0; dwFlags
0x10014dfb  cmp     esi, 4B0h
0x10014e01  jz      short loc_10014E17
0x10014e03  push    esi; CodePage
0x10014e04  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10014e0a  mov     [ebx], al
0x10014e0c  mov     ecx, 1Eh
0x10014e11  inc     eax
0x10014e12  jmp     loc_10014F6F
0x10014e17  push    0; CodePage
0x10014e19  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10014e1f  mov     [ebx], al
0x10014e21  mov     ecx, 1Eh
0x10014e26  inc     eax
0x10014e27  jmp     loc_10014F6F
0x10014e2c  mov     esi, [ebp+var_410]
0x10014e32  mov     eax, [ebp+var_414]
0x10014e38  push    ebx; void *
0x10014e39  add     eax, 4
0x10014e3c  mov     edx, [esi+18h]
0x10014e3f  mov     ecx, [esi+4]
0x10014e42  push    eax; Src
0x10014e43  call    AdjustFontName
0x10014e48  lea     ecx, [ebx+7]
0x10014e4b  lea     edx, [ecx+1]
0x10014e4e  mov     edi, edi
0x10014e50  mov     al, [ecx]
0x10014e52  inc     ecx
0x10014e53  test    al, al
0x10014e55  jnz     short loc_10014E50
0x10014e57  sub     ecx, edx
0x10014e59  mov     eax, 231h
0x10014e5e  mov     word ptr [ebp+var_40C], ax
0x10014e65  lea     eax, [ecx+7]
0x10014e68  jmp     loc_10014F7C
0x10014e6d  mov     eax, 41Eh
0x10014e72  cmp     cx, ax
0x10014e75  jz      short loc_10014E9B
0x10014e77  mov     ebx, [ebp+var_414]
0x10014e7d  mov     eax, edi
0x10014e7f  mov     word ptr [ebp+var_40C], si
0x10014e86  add     ebx, 4
0x10014e89  mov     esi, [ebp+var_410]
0x10014e8f  mov     word ptr [ebp+var_40C+2], dx
0x10014e96  jmp     loc_10014F86
0x10014e9b  mov     ecx, [ebp+var_414]
0x10014ea1  mov     edx, [ebp+var_410]
0x10014ea7  push    100h; cchWideChar
0x10014eac  movzx   eax, byte ptr [ecx+6]
0x10014eb0  movzx   edi, word ptr [ecx+4]
0x10014eb4  add     ecx, 7
0x10014eb7  mov     edx, [edx+18h]
0x10014eba  mov     [ebp+var_418], edi
0x10014ec0  lea     esi, [eax+eax]
0x10014ec3  cmp     edx, 4B0h
0x10014ec9  jz      short loc_10014EE5
0x10014ecb  lea     edi, [ebp+WideCharStr]
0x10014ed1  push    edi; lpWideCharStr
0x10014ed2  push    eax; cbMultiByte
0x10014ed3  push    ecx; lpMultiByteStr
0x10014ed4  push    0; dwFlags
0x10014ed6  push    edx; CodePage
0x10014ed7  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x10014edd  mov     edi, [ebp+var_418]
0x10014ee3  jmp     short loc_10014EF8
0x10014ee5  lea     edx, [ebp+WideCharStr]
0x10014eeb  push    edx; lpWideCharStr
0x10014eec  push    eax; cbMultiByte
0x10014eed  push    ecx; lpMultiByteStr
0x10014eee  push    0; dwFlags
0x10014ef0  push    0; CodePage
0x10014ef2  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x10014ef8  mov     ecx, [ebp+Src]; Src
0x10014efe  lea     eax, [ebp+var_208]
0x10014f04  push    eax; void *
0x10014f05  push    esi; Size
0x10014f06  lea     edx, [ebp+WideCharStr]; void *
0x10014f0c  call    AdjustFormatString
0x10014f11  lea     ecx, [ebp+var_208]
0x10014f17  lea     edx, [ecx+2]
0x10014f1a  nop     word ptr [eax+eax+00h]
0x10014f20  mov     ax, [ecx]
0x10014f23  add     ecx, 2
0x10014f26  test    ax, ax
0x10014f29  jnz     short loc_10014F20
0x10014f2b  mov     eax, [ebp+var_410]
0x10014f31  sub     ecx, edx
0x10014f33  sar     ecx, 1
0x10014f35  lea     edx, [ebx+3]
0x10014f38  push    0; lpUsedDefaultChar
0x10014f3a  push    0; lpDefaultChar
0x10014f3c  mov     esi, [eax+18h]
0x10014f3f  lea     eax, [ecx+ecx]
0x10014f42  push    eax; cbMultiByte
0x10014f43  lea     eax, [ebp+var_208]
0x10014f49  push    edx; lpMultiByteStr
0x10014f4a  push    ecx; cchWideChar
0x10014f4b  push    eax; lpWideCharStr
0x10014f4c  push    0; dwFlags
0x10014f4e  cmp     esi, 4B0h
0x10014f54  jz      short loc_10014F59
0x10014f56  push    esi
0x10014f57  jmp     short loc_10014F5B
0x10014f59  push    0; CodePage
0x10014f5b  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10014f61  mov     [ebx+2], al
0x10014f64  mov     ecx, 41Eh
0x10014f69  mov     [ebx], di
0x10014f6c  add     eax, 3
0x10014f6f  mov     esi, [ebp+var_410]
0x10014f75  mov     word ptr [ebp+var_40C], cx
0x10014f7c  mov     word ptr [ebp+var_40C+2], ax
0x10014f83  movzx   eax, ax
0x10014f86  mov     edi, [esi+28h]
0x10014f89  movzx   eax, ax
0x10014f8c  mov     [ebp+var_418], eax
0x10014f92  test    edi, edi
0x10014f94  jz      short loc_10014FE3
0x10014f96  cwde
0x10014f97  lea     ecx, [eax+0Bh]
0x10014f9a  call    _MemAllocate@4; MemAllocate(x)
0x10014f9f  mov     esi, eax
0x10014fa1  test    esi, esi
0x10014fa3  jz      loc_10015041
0x10014fa9  mov     ecx, [ebp+var_40C]
0x10014faf  mov     [esi+4], ecx
0x10014fb2  mov     ecx, [ebp+var_418]
0x10014fb8  movsx   eax, cx
0x10014fbb  lea     ecx, [esi+8]
0x10014fbe  push    eax; Size
0x10014fbf  push    ebx; Src
0x10014fc0  push    ecx; void *
0x10014fc1  call    _memcpy
0x10014fc6  mov     ecx, [edi+4]
0x10014fc9  add     esp, 0Ch
0x10014fcc  test    ecx, ecx
0x10014fce  jnz     short loc_10014FD5
0x10014fd0  mov     [edi+4], esi
0x10014fd3  jmp     short loc_1001500D
0x10014fd5  mov     eax, [ecx]
0x10014fd7  test    eax, eax
0x10014fd9  jz      short loc_10014FDF
0x10014fdb  mov     ecx, eax
0x10014fdd  jmp     short loc_10014FD5
0x10014fdf  mov     [ecx], esi
0x10014fe1  jmp     short loc_1001500D
0x10014fe3  mov     ecx, [esi+14h]
0x10014fe6  lea     edx, [ebp+var_40C]
0x10014fec  push    4
0x10014fee  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10014ff3  test    eax, eax
0x10014ff5  jnz     short loc_10015059
0x10014ff7  movsx   eax, word ptr [ebp+var_40C+2]
0x10014ffe  mov     edx, ebx
0x10015000  mov     ecx, [esi+14h]
0x10015003  push    eax
0x10015004  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x10015009  test    eax, eax
0x1001500b  jnz     short loc_10015059
0x1001500d  mov     edx, [ebp+var_414]
0x10015013  add     edx, 4
0x10015016  add     edx, [ebp+var_420]
0x1001501c  cmp     [ebp+arg_4], 0
0x10015020  mov     [ebp+var_414], edx
0x10015026  jnz     loc_10014C80
0x1001502c  xor     eax, eax
0x1001502e  pop     edi
0x1001502f  pop     esi
0x10015030  pop     ebx
0x10015031  mov     ecx, [ebp+var_4]
0x10015034  xor     ecx, ebp; StackCookie
0x10015036  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001503b  mov     esp, ebp
0x1001503d  pop     ebp
0x1001503e  retn    8
0x10015041  mov     eax, 0FFFFFFFEh
0x10015046  pop     edi
0x10015047  pop     esi
0x10015048  pop     ebx
  ... truncated ...
```
