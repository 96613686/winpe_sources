# WriteCellRecord

- ea: `0x1000c030`
- end: `0x1000c63c`
- name: `WriteCellRecord`
- size: `1548`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1000c670`

## callees

- `0x1000c030`
- `0x1002580a`
- `0x10025ab7`
- `0x1002611f`
- `0x1003669c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1000c314`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1000c544`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1000c553`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1000c314`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1000c544`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1000c553`

## pseudocode

```c
int __fastcall WriteCellRecord(int a1, _DWORD *a2, _WORD *a3, unsigned __int16 a4, int *a5)
{
  int *v5; // ebx
  int *v6; // edi
  unsigned __int16 v7; // dx
  int v8; // eax
  _WORD *v9; // edi
  __int16 v10; // cx
  __int16 v11; // si
  unsigned __int16 v12; // di
  int *v13; // edx
  __int16 v14; // ax
  int v15; // eax
  _WORD *v16; // ecx
  __int16 v17; // ax
  _WORD *v18; // ecx
  char v19; // al
  __int16 v20; // cx
  char *v21; // ebx
  int v22; // ecx
  unsigned __int16 *v23; // ebx
  int v24; // eax
  const WCHAR *v25; // eax
  const WCHAR *v26; // esi
  const WCHAR *v27; // ecx
  int v29; // esi
  CHAR *v30; // edi
  UINT v31; // eax
  int v32; // eax
  size_t v33; // ecx
  signed int v34; // eax
  char *v35; // ecx
  __int16 v36; // ax
  __int64 v37; // xmm0_8
  int v38; // eax
  int v39; // edi
  _WORD *v40; // eax
  unsigned __int16 v41; // cx
  int *v42; // edx
  char *v43; // ebx
  __int16 v44; // ax
  int v45; // ecx
  int v46; // edi
  int v47; // ecx
  int v48; // eax
  char *v49; // ecx
  __int16 v50; // ax
  int v51; // eax
  char *v52; // ebx
  int v53; // eax
  const WCHAR *v54; // eax
  const WCHAR *v55; // esi
  const WCHAR *v56; // ecx
  int v58; // esi
  CHAR *v59; // eax
  UINT v60; // ecx
  size_t v61; // edx
  __int16 v62; // cx
  char *v63; // edi
  int v64; // eax
  int result; // eax
  int v66; // [esp-Ch] [ebp-40h]
  int v67; // [esp-Ch] [ebp-40h]
  CHAR *Src; // [esp+14h] [ebp-20h]
  unsigned __int16 v70; // [esp+18h] [ebp-1Ch]
  signed int v71; // [esp+18h] [ebp-1Ch]
  __int16 v72; // [esp+1Ch] [ebp-18h]
  __int16 v73; // [esp+1Ch] [ebp-18h]
  signed int v74; // [esp+1Ch] [ebp-18h]
  size_t v75; // [esp+1Ch] [ebp-18h]
  int *v76; // [esp+20h] [ebp-14h]
  unsigned __int16 v77; // [esp+20h] [ebp-14h]
  int v78; // [esp+20h] [ebp-14h]
  __int16 v79; // [esp+20h] [ebp-14h]
  unsigned __int16 v80; // [esp+24h] [ebp-10h]
  __int16 v81; // [esp+24h] [ebp-10h]
  int *v82; // [esp+24h] [ebp-10h]
  LPCWCH lpWideCharStr; // [esp+2Ch] [ebp-8h] BYREF

  v5 = a5;
  v6 = (int *)*a5;
  v7 = *(unsigned __int8 *)(*a5 + 6);
  v80 = v7;
  if ( v7 < a3[7] )
    a3[7] = v7;
  if ( v7 > a3[9] )
    a3[9] = v7;
  if ( a4 < a3[6] )
    a3[6] = a4;
  if ( a4 > a3[8] )
    a3[8] = a4;
  switch ( *((_BYTE *)v6 + 7) )
  {
    case 1:
      v8 = *v6;
      if ( *v6 && *(_BYTE *)(v8 + 7) == 1 && *((unsigned __int8 *)v6 + 6) + 1 == *(unsigned __int8 *)(v8 + 6) )
      {
        v9 = pExcelRecordBuffer;
        v10 = 4;
        v76 = 0;
        v81 = 4;
        *(_WORD *)pExcelRecordBuffer = a4;
        v9[1] = v7;
        v11 = 6;
        lpWideCharStr = (LPCWCH)393406;
        v12 = v7;
        do
        {
          v13 = (int *)*v5;
          if ( *(_BYTE *)(*v5 + 7) != 1 )
            break;
          if ( v12 != *((unsigned __int8 *)v13 + 6) )
            break;
          v11 += 2;
          v14 = *((_WORD *)v13 + 2);
          ++v12;
          v76 = (int *)*v5;
          HIWORD(lpWideCharStr) = v11;
          *(_WORD *)((char *)pExcelRecordBuffer + v10) = v14;
          v5 = a5;
          v10 = v81 + 2;
          v15 = *v13;
          v81 += 2;
          *a5 = *v13;
        }
        while ( v15 );
        *(_WORD *)((char *)pExcelRecordBuffer + v81) = v12 - 1;
        *v5 = (int)v76;
      }
      else
      {
        v16 = pExcelRecordBuffer;
        v11 = 6;
        v17 = *((_WORD *)v6 + 2);
        lpWideCharStr = (LPCWCH)393729;
        *(_WORD *)pExcelRecordBuffer = a4;
        v16[1] = v7;
        v16[2] = v17;
      }
      break;
    case 2:
      v11 = 8;
      v18 = pExcelRecordBuffer;
      v72 = *((_WORD *)v6 + 2);
      lpWideCharStr = (LPCWCH)524805;
      if ( (int)g_cbCurrentSize >= 8 )
      {
        *(_WORD *)pExcelRecordBuffer = a4;
        v18[1] = v7;
        v18[2] = v72;
        v19 = *((_BYTE *)v6 + 8);
        if ( *((_BYTE *)v6 + 9) )
        {
          *((_BYTE *)v18 + 6) = v19;
          *((_BYTE *)v18 + 7) = 1;
        }
        else
        {
          *((_BYTE *)v18 + 7) = 0;
          *((_BYTE *)v18 + 6) = v19 != 0;
        }
      }
      break;
    case 3:
      v20 = *((_WORD *)v6 + 9);
      v21 = (char *)pExcelRecordBuffer;
      v73 = *((_WORD *)v6 + 2);
      LOWORD(lpWideCharStr) = 6;
      v11 = v20 + 22;
      HIWORD(lpWideCharStr) = v20 + 22;
      if ( (int)g_cbCurrentSize >= v20 + 22 )
      {
        *(_WORD *)pExcelRecordBuffer = a4;
        *((_WORD *)v21 + 2) = v73;
        *((_WORD *)v21 + 1) = v7;
        v22 = v6[3];
        *(_DWORD *)(v21 + 6) = v6[2];
        *(_DWORD *)(v21 + 10) = v22;
        *((_WORD *)v21 + 7) = *((_WORD *)v6 + 8);
        *((_DWORD *)v21 + 4) = 0;
        *((_WORD *)v21 + 10) = *((_WORD *)v6 + 9);
        memcpy(v21 + 22, v6 + 5, *((__int16 *)v6 + 9));
      }
      break;
    case 4:
    case 8:
      v23 = (unsigned __int16 *)pExcelRecordBuffer;
      v77 = *((_WORD *)v6 + 2);
      v74 = g_cbCurrentSize;
      if ( (int)a2[9] <= 5 )
      {
        v24 = v6[2];
        if ( !v24 || v24 == -1 )
          v25 = &WideCharStr;
        else
          v25 = (const WCHAR *)(v24 + 14);
        v26 = v25;
        lpWideCharStr = v25;
        v27 = v25 + 1;
        while ( *v26++ )
          ;
        v29 = v26 - v27;
        if ( v29 > 255 )
          v29 = 255;
        v30 = (CHAR *)MemAllocate(2 * v29 + 2);
        if ( !v30 )
          goto LABEL_68;
        v66 = 2 * v29;
        v31 = a2[11];
        if ( v31 == 1200 )
          v32 = WideCharToMultiByte(0, 0, lpWideCharStr, v29, v30, v66, 0, 0);
        else
          v32 = WideCharToMultiByte(v31, 0, lpWideCharStr, v29, v30, v66, 0, 0);
        v33 = v32;
        LOWORD(lpWideCharStr) = 516;
        v70 = v32;
        v34 = v32 + 8;
        v11 = v34;
        HIWORD(lpWideCharStr) = v34;
        if ( v74 >= v34 )
        {
          *v23 = a4;
          v23[1] = v80;
          v23[2] = v77;
          v23[3] = v70;
          memcpy(v23 + 4, v30, v33);
        }
        MemFree(v30);
      }
      else
      {
        v11 = 10;
        lpWideCharStr = (LPCWCH)655613;
        if ( (int)g_cbCurrentSize >= 10 )
        {
          *(_WORD *)pExcelRecordBuffer = a4;
          v23[1] = v7;
          v23[2] = v77;
          *(_DWORD *)(v23 + 3) = v6[3];
        }
      }
      break;
    case 5:
      v35 = (char *)pExcelRecordBuffer;
      v11 = 14;
      v36 = *((_WORD *)v6 + 2);
      *(_WORD *)pExcelRecordBuffer = a4;
      *((_WORD *)v35 + 1) = v7;
      *((_WORD *)v35 + 2) = v36;
      v37 = *((_QWORD *)v6 + 1);
      lpWideCharStr = (LPCWCH)918019;
      *(_QWORD *)(v35 + 6) = v37;
      break;
    case 6:
      v38 = *v6;
      if ( *v6 && *(_BYTE *)(v38 + 7) == 6 && *((unsigned __int8 *)v6 + 6) + 1 == *(unsigned __int8 *)(v38 + 6) )
      {
        v82 = 0;
        v39 = 4;
        v40 = pExcelRecordBuffer;
        lpWideCharStr = (LPCWCH)393405;
        v11 = 6;
        *(_WORD *)pExcelRecordBuffer = a4;
        v41 = v7;
        v40[1] = v7;
        v78 = v7;
        do
        {
          v42 = (int *)*v5;
          if ( *(_BYTE *)(*v5 + 7) != 6 )
            break;
          if ( v41 != *((unsigned __int8 *)v42 + 6) )
            break;
          v43 = (char *)pExcelRecordBuffer;
          v11 += 6;
          v44 = *((_WORD *)v42 + 2);
          v45 = (__int16)v39;
          v46 = v39 + 2;
          v82 = v42;
          HIWORD(lpWideCharStr) = v11;
          *(_WORD *)((char *)pExcelRecordBuffer + v45) = v44;
          v47 = (__int16)v46;
          v39 = v46 + 4;
          *(_DWORD *)&v43[v47] = v42[2];
          v5 = a5;
          v41 = v78 + 1;
          v48 = *v42;
          ++v78;
          *a5 = *v42;
        }
        while ( v48 );
        *(_WORD *)((char *)pExcelRecordBuffer + (__int16)v39) = v41 - 1;
        *v5 = (int)v82;
      }
      else
      {
        v49 = (char *)pExcelRecordBuffer;
        v11 = 10;
        v50 = *((_WORD *)v6 + 2);
        *(_WORD *)pExcelRecordBuffer = a4;
        *((_WORD *)v49 + 1) = v7;
        *((_WORD *)v49 + 2) = v50;
        v51 = v6[2];
        lpWideCharStr = (LPCWCH)655998;
        *(_DWORD *)(v49 + 6) = v51;
      }
      break;
    case 7:
    case 9:
      v52 = (char *)pExcelRecordBuffer;
      v79 = *((_WORD *)v6 + 2);
      v71 = g_cbCurrentSize;
      if ( (int)a2[9] <= 5 )
      {
        v53 = v6[2];
        if ( !v53 || v53 == -1 )
          v54 = &WideCharStr;
        else
          v54 = (const WCHAR *)(v53 + 14);
        v55 = v54;
        lpWideCharStr = v54;
        v56 = v54 + 1;
        while ( *v55++ )
          ;
        v58 = v55 - v56;
        v59 = (CHAR *)MemAllocate(2 * v58 + 2);
        Src = v59;
        if ( !v59 )
          goto LABEL_68;
        v67 = 2 * v58;
        v60 = a2[11];
        if ( v60 == 1200 )
          v61 = WideCharToMultiByte(0, 0, lpWideCharStr, v58, v59, v67, 0, 0);
        else
          v61 = WideCharToMultiByte(v60, 0, lpWideCharStr, v58, v59, v67, 0, 0);
        v75 = v61;
        v62 = *((_WORD *)v6 + 8);
        LOWORD(lpWideCharStr) = 214;
        v11 = v61 + v62 + 9;
        HIWORD(lpWideCharStr) = v11;
        if ( v71 >= (int)(v61 + v62 + 9) )
        {
          *(_WORD *)v52 = a4;
          *((_WORD *)v52 + 1) = v80;
          *((_WORD *)v52 + 2) = v79;
          memcpy(v52 + 8, Src, v61);
          v52[v75 + 8] = *((__int16 *)v6 + 8) / 2;
          memcpy(&v52[v75 + 9], (char *)v6 + 18, *((__int16 *)v6 + 8));
        }
      }
      else
      {
        v11 = 10;
        lpWideCharStr = (LPCWCH)655613;
        if ( (int)g_cbCurrentSize >= 10 )
        {
          *(_WORD *)pExcelRecordBuffer = a4;
          *((_WORD *)v52 + 1) = v7;
          *((_WORD *)v52 + 2) = v79;
          *(_DWORD *)(v52 + 6) = v6[3];
        }
      }
      break;
    default:
LABEL_68:
      v11 = HIWORD(lpWideCharStr);
      break;
  }
  v63 = (char *)pExcelRecordBuffer;
  a2[5] += v11 + 4;
  if ( a2[6] != 1 )
    return 0;
  v64 = BFWriteFile(*(_DWORD *)(a1 + 20), (char *)&lpWideCharStr, 4u);
  if ( !v64 )
  {
    v64 = BFWriteFile(*(_DWORD *)(a1 + 20), v63, SHIWORD(lpWideCharStr));
    if ( !v64 )
      return 0;
  }
  result = dword_10001970[abs32(v64)];
  if ( result == -10 )
    return -10;
  return result;
}

```

## disassembly

```asm
0x1000c030  mov     edi, edi
0x1000c032  push    ebp
0x1000c033  mov     ebp, esp
0x1000c035  sub     esp, 28h
0x1000c038  push    ebx
0x1000c039  mov     ebx, [ebp+arg_8]
0x1000c03c  push    esi
0x1000c03d  movzx   esi, [ebp+arg_4]
0x1000c041  push    edi
0x1000c042  mov     edi, [ebx]
0x1000c044  mov     [ebp+var_24], ecx
0x1000c047  mov     [ebp+var_C], edx
0x1000c04a  movzx   eax, byte ptr [edi+6]
0x1000c04e  mov     ecx, eax
0x1000c050  mov     edx, eax
0x1000c052  mov     [ebp+var_18], ecx
0x1000c055  mov     ecx, [ebp+arg_0]
0x1000c058  mov     [ebp+var_10], edx
0x1000c05b  cmp     ax, [ecx+0Eh]
0x1000c05f  jnb     short loc_1000C065
0x1000c061  mov     [ecx+0Eh], dx
0x1000c065  mov     eax, [ebp+var_18]
0x1000c068  cmp     ax, [ecx+12h]
0x1000c06c  jbe     short loc_1000C072
0x1000c06e  mov     [ecx+12h], dx
0x1000c072  movzx   eax, [ebp+arg_4]
0x1000c076  cmp     ax, [ecx+0Ch]
0x1000c07a  jnb     short loc_1000C080
0x1000c07c  mov     [ecx+0Ch], si
0x1000c080  cmp     ax, [ecx+10h]
0x1000c084  jbe     short loc_1000C08A
0x1000c086  mov     [ecx+10h], si
0x1000c08a  movzx   eax, byte ptr [edi+7]
0x1000c08e  dec     eax; switch 9 cases
0x1000c08f  cmp     eax, 8
0x1000c092  ja      def_1000C098; jumptable 1000C098 default case
0x1000c098  jmp     ds:jpt_1000C098[eax*4]; switch jump
0x1000c09f  mov     eax, [edi]; jumptable 1000C098 case 1
0x1000c0a1  test    eax, eax
0x1000c0a3  jz      loc_1000C14D
0x1000c0a9  cmp     byte ptr [eax+7], 1
0x1000c0ad  jnz     loc_1000C14D
0x1000c0b3  movzx   ecx, byte ptr [edi+6]
0x1000c0b7  movzx   eax, byte ptr [eax+6]
0x1000c0bb  inc     ecx
0x1000c0bc  cmp     ecx, eax
0x1000c0be  jnz     loc_1000C14D
0x1000c0c4  mov     edi, _pExcelRecordBuffer
0x1000c0ca  xor     eax, eax
0x1000c0cc  mov     ecx, 4
0x1000c0d1  mov     [ebp+var_14], eax
0x1000c0d4  movzx   eax, [ebp+arg_4]
0x1000c0d8  mov     [ebp+var_10], ecx
0x1000c0db  mov     [edi], ax
0x1000c0de  mov     [edi+2], dx
0x1000c0e2  lea     esi, [ecx+2]
0x1000c0e5  mov     [ebp+lpWideCharStr], 600BEh
0x1000c0ec  movzx   edi, dx
0x1000c0ef  nop
0x1000c0f0  mov     edx, [ebx]
0x1000c0f2  cmp     byte ptr [edx+7], 1
0x1000c0f6  jnz     short loc_1000C132
0x1000c0f8  movzx   eax, byte ptr [edx+6]
0x1000c0fc  cmp     di, ax
0x1000c0ff  jnz     short loc_1000C132
0x1000c101  mov     ebx, _pExcelRecordBuffer
0x1000c107  add     si, 2
0x1000c10b  mov     ax, [edx+4]
0x1000c10f  inc     edi
0x1000c110  movsx   ecx, cx
0x1000c113  mov     [ebp+var_14], edx
0x1000c116  mov     word ptr [ebp+lpWideCharStr+2], si
0x1000c11a  mov     [ecx+ebx], ax
0x1000c11e  mov     ecx, [ebp+var_10]
0x1000c121  mov     ebx, [ebp+arg_8]
0x1000c124  add     ecx, 2
0x1000c127  mov     eax, [edx]
0x1000c129  mov     [ebp+var_10], ecx
0x1000c12c  mov     [ebx], eax
0x1000c12e  test    eax, eax
0x1000c130  jnz     short loc_1000C0F0
0x1000c132  mov     eax, [ebp+var_10]
0x1000c135  lea     ecx, [edi-1]
0x1000c138  mov     edx, _pExcelRecordBuffer
0x1000c13e  cwde
0x1000c13f  mov     [eax+edx], cx
0x1000c143  mov     eax, [ebp+var_14]
0x1000c146  mov     [ebx], eax
0x1000c148  jmp     loc_1000C5D3
0x1000c14d  mov     ecx, _pExcelRecordBuffer
0x1000c153  mov     esi, 6
0x1000c158  movzx   eax, word ptr [edi+4]
0x1000c15c  movzx   ebx, [ebp+arg_4]
0x1000c160  mov     [ebp+lpWideCharStr], 60201h
0x1000c167  mov     [ecx], bx
0x1000c16a  mov     [ecx+2], dx
0x1000c16e  mov     [ecx+4], ax
0x1000c172  jmp     loc_1000C5D3
0x1000c177  movzx   eax, word ptr [edi+4]; jumptable 1000C098 case 2
0x1000c17b  mov     esi, 8
0x1000c180  mov     ecx, _pExcelRecordBuffer
0x1000c186  mov     [ebp+var_18], eax
0x1000c189  mov     [ebp+lpWideCharStr], 80205h
0x1000c190  cmp     _g_cbCurrentSize, esi
0x1000c196  jl      loc_1000C5D3
0x1000c19c  movzx   eax, [ebp+arg_4]
0x1000c1a0  mov     [ecx], ax
0x1000c1a3  mov     eax, [ebp+var_18]
0x1000c1a6  mov     [ecx+2], dx
0x1000c1aa  mov     [ecx+4], ax
0x1000c1ae  cmp     byte ptr [edi+9], 0
0x1000c1b2  mov     al, [edi+8]
0x1000c1b5  jnz     short loc_1000C1C8
0x1000c1b7  test    al, al
0x1000c1b9  mov     byte ptr [ecx+7], 0
0x1000c1bd  setnz   al
0x1000c1c0  mov     [ecx+6], al
0x1000c1c3  jmp     loc_1000C5D3
0x1000c1c8  mov     [ecx+6], al
0x1000c1cb  mov     byte ptr [ecx+7], 1
0x1000c1cf  jmp     loc_1000C5D3
0x1000c1d4  movzx   eax, word ptr [edi+4]; jumptable 1000C098 case 3
0x1000c1d8  movzx   ecx, word ptr [edi+12h]
0x1000c1dc  mov     ebx, _pExcelRecordBuffer
0x1000c1e2  mov     [ebp+var_18], eax
0x1000c1e5  mov     eax, 6
0x1000c1ea  mov     word ptr [ebp+lpWideCharStr], ax
0x1000c1ee  movsx   eax, cx
0x1000c1f1  lea     esi, [ecx+16h]
0x1000c1f4  add     eax, 16h
0x1000c1f7  mov     word ptr [ebp+lpWideCharStr+2], si
0x1000c1fb  cmp     _g_cbCurrentSize, eax
0x1000c201  jl      loc_1000C5D3
0x1000c207  movzx   eax, [ebp+arg_4]
0x1000c20b  mov     [ebx], ax
0x1000c20e  mov     eax, [ebp+var_18]
0x1000c211  mov     [ebx+4], ax
0x1000c215  mov     [ebx+2], dx
0x1000c219  mov     eax, [edi+8]
0x1000c21c  mov     ecx, [edi+0Ch]
0x1000c21f  mov     [ebx+6], eax
0x1000c222  mov     [ebx+0Ah], ecx
0x1000c225  movzx   eax, word ptr [edi+10h]
0x1000c229  mov     [ebx+0Eh], ax
0x1000c22d  mov     dword ptr [ebx+10h], 0
0x1000c234  movzx   eax, word ptr [edi+12h]
0x1000c238  mov     [ebx+14h], ax
0x1000c23c  movsx   eax, word ptr [edi+12h]
0x1000c240  push    eax; Size
0x1000c241  lea     eax, [edi+14h]
0x1000c244  push    eax; Src
0x1000c245  lea     eax, [ebx+16h]
0x1000c248  push    eax; void *
0x1000c249  call    _memcpy
0x1000c24e  add     esp, 0Ch
0x1000c251  jmp     loc_1000C5D3
0x1000c256  movzx   eax, word ptr [edi+4]; jumptable 1000C098 cases 4,8
0x1000c25a  mov     ecx, _g_cbCurrentSize
0x1000c260  mov     ebx, _pExcelRecordBuffer
0x1000c266  mov     [ebp+var_14], eax
0x1000c269  mov     eax, [ebp+var_C]
0x1000c26c  mov     [ebp+var_18], ecx
0x1000c26f  cmp     dword ptr [eax+24h], 5
0x1000c273  jle     short loc_1000C2A6
0x1000c275  mov     esi, 0Ah
0x1000c27a  mov     [ebp+lpWideCharStr], 0A00FDh
0x1000c281  cmp     ecx, esi
0x1000c283  jl      loc_1000C5D3
0x1000c289  movzx   eax, [ebp+arg_4]
0x1000c28d  mov     [ebx], ax
0x1000c290  mov     eax, [ebp+var_14]
0x1000c293  mov     [ebx+2], dx
0x1000c297  mov     [ebx+4], ax
0x1000c29b  mov     eax, [edi+0Ch]
0x1000c29e  mov     [ebx+6], eax
0x1000c2a1  jmp     loc_1000C5D3
0x1000c2a6  mov     eax, [edi+8]
0x1000c2a9  test    eax, eax
0x1000c2ab  jz      short loc_1000C2B7
0x1000c2ad  cmp     eax, 0FFFFFFFFh
0x1000c2b0  jz      short loc_1000C2B7
0x1000c2b2  add     eax, 0Eh
0x1000c2b5  jmp     short loc_1000C2BC
0x1000c2b7  mov     eax, offset WideCharStr
0x1000c2bc  mov     esi, eax
0x1000c2be  mov     [ebp+lpWideCharStr], eax
0x1000c2c1  lea     ecx, [esi+2]
0x1000c2c4  mov     ax, [esi]
0x1000c2c7  add     esi, 2
0x1000c2ca  test    ax, ax
0x1000c2cd  jnz     short loc_1000C2C4
0x1000c2cf  sub     esi, ecx
0x1000c2d1  mov     eax, 0FFh
0x1000c2d6  sar     esi, 1
0x1000c2d8  cmp     esi, eax
0x1000c2da  cmovg   esi, eax
0x1000c2dd  lea     ecx, ds:2[esi*2]
0x1000c2e4  call    _MemAllocate@4; MemAllocate(x)
0x1000c2e9  mov     edi, eax
0x1000c2eb  test    edi, edi
0x1000c2ed  jz      def_1000C098; jumptable 1000C098 default case
0x1000c2f3  mov     eax, [ebp+var_C]
0x1000c2f6  lea     ecx, [esi+esi]
0x1000c2f9  push    0; lpUsedDefaultChar
0x1000c2fb  push    0; lpDefaultChar
0x1000c2fd  push    ecx; cbMultiByte
0x1000c2fe  mov     eax, [eax+2Ch]
0x1000c301  push    edi; lpMultiByteStr
0x1000c302  push    esi; cchWideChar
0x1000c303  push    [ebp+lpWideCharStr]; lpWideCharStr
0x1000c306  push    0; dwFlags
0x1000c308  cmp     eax, 4B0h
0x1000c30d  jz      short loc_1000C312
0x1000c30f  push    eax
0x1000c310  jmp     short loc_1000C314
0x1000c312  push    0; CodePage
0x1000c314  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000c31a  mov     ecx, eax
0x1000c31c  mov     eax, 204h
0x1000c321  mov     word ptr [ebp+lpWideCharStr], ax
0x1000c325  movzx   eax, cx
0x1000c328  mov     [ebp+var_1C], eax
0x1000c32b  lea     esi, [eax+8]
0x1000c32e  lea     eax, [ecx+8]
0x1000c331  mov     word ptr [ebp+lpWideCharStr+2], si
0x1000c335  cmp     [ebp+var_18], eax
0x1000c338  jl      short loc_1000C364
0x1000c33a  movzx   eax, [ebp+arg_4]
0x1000c33e  mov     [ebx], ax
0x1000c341  mov     eax, [ebp+var_10]
0x1000c344  mov     [ebx+2], ax
0x1000c348  mov     eax, [ebp+var_14]
0x1000c34b  mov     [ebx+4], ax
0x1000c34f  mov     eax, [ebp+var_1C]
0x1000c352  push    ecx; Size
0x1000c353  mov     [ebx+6], ax
0x1000c357  lea     eax, [ebx+8]
0x1000c35a  push    edi; Src
0x1000c35b  push    eax; void *
0x1000c35c  call    _memcpy
0x1000c361  add     esp, 0Ch
0x1000c364  mov     ecx, edi
0x1000c366  call    _MemFree@4; MemFree(x)
0x1000c36b  jmp     loc_1000C5D3
0x1000c370  mov     ecx, _pExcelRecordBuffer; jumptable 1000C098 case 5
0x1000c376  mov     esi, 0Eh
0x1000c37b  movzx   eax, word ptr [edi+4]
0x1000c37f  movzx   ebx, [ebp+arg_4]
0x1000c383  mov     edx, [ebp+var_10]
0x1000c386  mov     [ecx], bx
0x1000c389  mov     [ecx+2], dx
0x1000c38d  mov     [ecx+4], ax
0x1000c391  movsd   xmm0, qword ptr [edi+8]
0x1000c396  mov     [ebp+lpWideCharStr], 0E0203h
0x1000c39d  movsd   qword ptr [ecx+6], xmm0
0x1000c3a2  jmp     loc_1000C5D3
0x1000c3a7  mov     eax, [edi]; jumptable 1000C098 case 6
0x1000c3a9  test    eax, eax
0x1000c3ab  jz      loc_1000C45C
0x1000c3b1  cmp     byte ptr [eax+7], 6
0x1000c3b5  jnz     loc_1000C45C
0x1000c3bb  movzx   ecx, byte ptr [edi+6]
0x1000c3bf  movzx   eax, byte ptr [eax+6]
0x1000c3c3  inc     ecx
0x1000c3c4  cmp     ecx, eax
0x1000c3c6  jnz     loc_1000C45C
0x1000c3cc  movzx   ecx, [ebp+arg_4]
0x1000c3d0  xor     eax, eax
0x1000c3d2  mov     [ebp+var_10], eax
0x1000c3d5  mov     edi, 4
0x1000c3da  mov     eax, _pExcelRecordBuffer
0x1000c3df  mov     [ebp+lpWideCharStr], 600BDh
0x1000c3e6  lea     esi, [edi+2]
0x1000c3e9  mov     [eax], cx
0x1000c3ec  movzx   ecx, dx
0x1000c3ef  mov     [eax+2], dx
0x1000c3f3  mov     [ebp+var_14], ecx
0x1000c3f6  mov     edx, [ebx]
0x1000c3f8  cmp     byte ptr [edx+7], 6
0x1000c3fc  jnz     short loc_1000C444
0x1000c3fe  movzx   eax, byte ptr [edx+6]
0x1000c402  cmp     cx, ax
0x1000c405  jnz     short loc_1000C444
0x1000c407  mov     ebx, _pExcelRecordBuffer
0x1000c40d  add     si, 6
0x1000c411  mov     ax, [edx+4]
0x1000c415  movsx   ecx, di
0x1000c418  add     edi, 2
0x1000c41b  mov     [ebp+var_10], edx
0x1000c41e  mov     word ptr [ebp+lpWideCharStr+2], si
0x1000c422  mov     [ecx+ebx], ax
0x1000c426  mov     eax, [edx+8]
0x1000c429  movsx   ecx, di
0x1000c42c  add     edi, 4
0x1000c42f  mov     [ecx+ebx], eax
0x1000c432  mov     ecx, [ebp+var_14]
0x1000c435  mov     ebx, [ebp+arg_8]
0x1000c438  inc     ecx
0x1000c439  mov     eax, [edx]
0x1000c43b  mov     [ebp+var_14], ecx
  ... truncated ...
```
