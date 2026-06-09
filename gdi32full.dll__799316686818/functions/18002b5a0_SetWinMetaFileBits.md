# SetWinMetaFileBits

- ea: `0x18002b5a0`
- end: `0x18002b9e3`
- name: `SetWinMetaFileBits`
- size: `1091`
- prototype: `HENHMETAFILE __stdcall(UINT nSize, const BYTE *lpMeta16Data, HDC hdcRef, const METAFILEPICT *lpMFP)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180070c44`

## callees

- `0x180010000`
- `0x180010950`
- `0x180010b70`
- `0x1800281d0`
- `0x180028200`
- `0x180028f18`
- `0x180029c30`
- `0x180029e20`
- `0x18002b5a0`
- `0x18002b9ec`
- `0x18002ba30`
- `0x18002bc30`
- `0x1800795e0`
- `0x18008ec00`
- `0x1800a3514`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b8e7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002b8e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b8d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b8d0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18002b82d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18002b85e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18002b82d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18002b85e`
- `GDI32!DeleteDC` at `0x18002b9c6`
- `GDI32!DeleteDC` at `0x18002b9c6`
- `GDI32!GetDeviceCaps` at `0x18002b6c8`
- `GDI32!GetDeviceCaps` at `0x18002b6d9`
- `GDI32!GetDeviceCaps` at `0x18002b80d`
- `GDI32!GetDeviceCaps` at `0x18002b81e`
- `GDI32!GetDeviceCaps` at `0x18002b83e`
- `GDI32!GetDeviceCaps` at `0x18002b84f`
- `GDI32!GetDeviceCaps` at `0x18002b6c8`
- `GDI32!GetDeviceCaps` at `0x18002b6d9`
- `GDI32!GetDeviceCaps` at `0x18002b80d`
- `GDI32!GetDeviceCaps` at `0x18002b81e`
- `GDI32!GetDeviceCaps` at `0x18002b83e`
- `GDI32!GetDeviceCaps` at `0x18002b84f`
- `GDI32!pldcGet` at `0x18002b703`
- `GDI32!pldcGet` at `0x18002b703`
- `GDI32!GdiSetLastError` at `0x18002b9d6`
- `GDI32!GdiSetLastError` at `0x18002b9d6`

## pseudocode

```c
HENHMETAFILE __stdcall SetWinMetaFileBits(UINT nSize, const BYTE *lpMeta16Data, HDC hdcRef, const METAFILEPICT *lpMFP)
{
  __int64 v5; // r15
  const BYTE *v8; // rbx
  const BYTE *v9; // r8
  unsigned int v10; // ecx
  __int16 v11; // dx
  __int16 v12; // ax
  HMETAFILE v13; // rbx
  HDC v15; // rbp
  LONG mm; // edi
  int v17; // r12d
  int v18; // eax
  const RECT *v19; // r8
  int v20; // r13d
  HDC EnhMetaFileW; // rax
  HDC v22; // rbx
  __int64 v23; // rax
  __int64 v24; // r14
  HENHMETAFILE v25; // rax
  int v26; // ebx
  int DeviceCaps; // eax
  int v28; // ebx
  int v29; // eax
  size_t v30; // r8
  unsigned __int64 v31; // rcx
  unsigned int v32; // r12d
  char *v33; // rbp
  const BYTE *v34; // rax
  int v35; // edi
  HDC ICA; // rax
  __int64 v37; // rcx
  HMETAFILE hmf; // [rsp+20h] [rbp-88h]
  int v39; // [rsp+28h] [rbp-80h]
  HENHMETAFILE v40; // [rsp+38h] [rbp-70h]
  __int128 v42; // [rsp+48h] [rbp-60h] BYREF

  v5 = nSize;
  v42 = 0;
  if ( gbDisableMetaFiles )
    return 0;
  if ( nSize >= 0x12 && (unsigned int)IsValidMetaHeader16(lpMeta16Data) )
  {
    v40 = 0;
    v39 = 1;
    if ( &lpMeta16Data[v5] >= lpMeta16Data && (unsigned int)v5 >= 0x3E )
    {
      v8 = lpMeta16Data + 18;
      if ( *((_WORD *)lpMeta16Data + 11) == 1574
        && *(_DWORD *)v8 > 0x16u
        && *((_WORD *)lpMeta16Data + 12) == 15
        && *((_DWORD *)lpMeta16Data + 7) == 1128680791
        && *((_DWORD *)lpMeta16Data + 8) == 1 )
      {
        if ( !*(_DWORD *)(lpMeta16Data + 42) )
        {
          v9 = lpMeta16Data;
          v10 = (unsigned int)v5 >> 1;
          v11 = 0;
          if ( !((unsigned int)v5 >> 1) )
            goto LABEL_53;
          do
          {
            v12 = *(_WORD *)v9;
            v9 += 2;
            v11 += v12;
            --v10;
          }
          while ( v10 );
          if ( !v11 )
          {
LABEL_53:
            v32 = *(_DWORD *)(lpMeta16Data + 58);
            v33 = (char *)LocalAlloc(0, v32);
            if ( v33 )
            {
              v34 = &lpMeta16Data[v5];
              v35 = 0;
              do
              {
                v30 = *((unsigned int *)v8 + 8);
                v31 = (unsigned __int64)&v8[v30 + 44];
                if ( v31 < (unsigned __int64)(v8 + 44) || v31 > (unsigned __int64)v34 || (int)v30 + v35 > v32 )
                  goto LABEL_51;
                memcpy_0(&v33[v35], v8 + 44, v30);
                v35 += *((_DWORD *)v8 + 8);
                v8 += 2 * *(unsigned int *)v8;
                if ( v8 > &lpMeta16Data[v5 - 44] )
                  break;
                if ( *((_WORD *)v8 + 2) != 1574 )
                  break;
                if ( *(_DWORD *)v8 <= 0x16u )
                  break;
                if ( *((_WORD *)v8 + 3) != 15 )
                  break;
                if ( *(_DWORD *)(v8 + 10) != 1128680791 )
                  break;
                v34 = &lpMeta16Data[v5];
              }
              while ( *(_DWORD *)(v8 + 14) == 1 );
              if ( v35 != v32 || (v40 = (HENHMETAFILE)SetEnhMetaFileBitsAlt((unsigned int *)v33)) == 0 )
              {
LABEL_51:
                LocalFree(v33);
                goto LABEL_15;
              }
              return v40;
            }
          }
        }
LABEL_15:
        v39 = 0;
      }
    }
    hmf = SetMetaFileBitsEx(v5, lpMeta16Data);
    v13 = hmf;
    if ( !hmf )
      return v40;
    v15 = 0;
    if ( !hdcRef )
    {
      ICA = CreateICA("DISPLAY", 0, 0, 0);
      v15 = ICA;
      if ( !ICA )
      {
LABEL_36:
        DeleteMetaFile(v13);
        return v40;
      }
      hdcRef = ICA;
    }
    if ( lpMFP )
    {
      mm = lpMFP->mm;
      if ( lpMFP->mm )
      {
        if ( mm == 1 || mm == 2 || mm == 3 || mm == 4 || mm == 5 || mm == 6 )
          goto LABEL_21;
        if ( (unsigned int)(mm - 7) > 1 )
        {
LABEL_34:
          if ( v15 )
            DeleteDC(v15);
          goto LABEL_36;
        }
      }
      else
      {
        mm = 8;
      }
      if ( lpMFP->xExt > 0 && lpMFP->yExt > 0 )
      {
        v26 = 100 * GetDeviceCaps(hdcRef, 4);
        DeviceCaps = GetDeviceCaps(hdcRef, 118);
        v17 = MulDiv(lpMFP->xExt, DeviceCaps, v26);
        v28 = 100 * GetDeviceCaps(hdcRef, 6);
        v29 = GetDeviceCaps(hdcRef, 117);
        v20 = MulDiv(lpMFP->yExt, v29, v28);
        v19 = (const RECT *)&v42;
        *((_QWORD *)&v42 + 1) = *(_QWORD *)&lpMFP->xExt;
        goto LABEL_22;
      }
    }
    else
    {
      mm = 8;
    }
LABEL_21:
    v17 = GetDeviceCaps(hdcRef, 118);
    v18 = GetDeviceCaps(hdcRef, 117);
    v19 = 0;
    v20 = v18;
LABEL_22:
    EnhMetaFileW = CreateEnhMetaFileW(hdcRef, 0, v19, 0);
    v22 = EnhMetaFileW;
    if ( !EnhMetaFileW )
    {
LABEL_33:
      v13 = hmf;
      goto LABEL_34;
    }
    v23 = pldcGet(EnhMetaFileW);
    if ( v23 && ((unsigned int)v22 & 0x7F0000) != 0x660000 )
    {
      if ( v39 && mm == 8 )
      {
        v24 = *(_QWORD *)(v23 + 16);
        if ( !(unsigned int)MF_GdiCommentWindowsMetaFile(v22, (unsigned int)v5, lpMeta16Data) )
          goto LABEL_31;
        *(_DWORD *)(v24 + 32) |= 8u;
      }
      if ( SetMapMode(v22, mm) && SetViewportExtEx(v22, v17, v20, 0) && SetWindowExtEx(v22, v17, v20, 0) )
      {
        PlayMetaFile(v22, hmf);
        v40 = CloseEnhMetaFile(v22);
        goto LABEL_33;
      }
LABEL_31:
      v25 = CloseEnhMetaFile(v22);
      if ( v25 )
        DeleteEnhMetaFile(v25);
      goto LABEL_33;
    }
    v37 = 6;
    goto LABEL_71;
  }
  v37 = 13;
LABEL_71:
  GdiSetLastError(v37);
  return 0;
}

```

## disassembly

```asm
0x18002b5a0  push    rbx
0x18002b5a2  push    rbp
0x18002b5a3  push    rsi
0x18002b5a4  push    rdi
0x18002b5a5  push    r12
0x18002b5a7  push    r13
0x18002b5a9  push    r14
0x18002b5ab  push    r15
0x18002b5ad  sub     rsp, 68h
0x18002b5b1  xor     r12d, r12d
0x18002b5b4  mov     [rsp+0A8h+var_68], r9
0x18002b5b9  cmp     cs:gbDisableMetaFiles, r12d
0x18002b5c0  xorps   xmm0, xmm0
0x18002b5c3  mov     r13, r9
0x18002b5c6  mov     r15d, ecx
0x18002b5c9  mov     r14, r8
0x18002b5cc  mov     rsi, rdx
0x18002b5cf  movups  [rsp+0A8h+var_60], xmm0
0x18002b5d4  jnz     loc_18002B9DC
0x18002b5da  cmp     r15d, 12h
0x18002b5de  jb      loc_18002B9D1
0x18002b5e4  mov     rcx, rdx
0x18002b5e7  call    IsValidMetaHeader16
0x18002b5ec  test    eax, eax
0x18002b5ee  jz      loc_18002B9D1
0x18002b5f4  lea     rax, [rsi+r15]
0x18002b5f8  mov     [rsp+0A8h+var_70], r12
0x18002b5fd  mov     [rsp+0A8h+hmf], rax
0x18002b602  lea     edi, [r12+1]
0x18002b607  mov     [rsp+0A8h+var_80], edi
0x18002b60b  cmp     rax, rsi
0x18002b60e  jb      short loc_18002B674
0x18002b610  cmp     r15d, 3Eh ; '>'
0x18002b614  jb      short loc_18002B674
0x18002b616  lea     rbx, [rsi+12h]
0x18002b61a  mov     eax, 626h
0x18002b61f  cmp     [rbx+4], ax
0x18002b623  jnz     short loc_18002B674
0x18002b625  cmp     dword ptr [rbx], 16h
0x18002b628  jbe     short loc_18002B674
0x18002b62a  cmp     word ptr [rbx+6], 0Fh
0x18002b62f  jnz     short loc_18002B674
0x18002b631  cmp     dword ptr [rbx+0Ah], 43464D57h
0x18002b638  jnz     short loc_18002B674
0x18002b63a  cmp     [rbx+0Eh], edi
0x18002b63d  jnz     short loc_18002B674
0x18002b63f  cmp     [rbx+18h], r12d
0x18002b643  jnz     short loc_18002B66F
0x18002b645  mov     ecx, r15d
0x18002b648  mov     r8, rsi
0x18002b64b  shr     ecx, 1
0x18002b64d  mov     edx, r12d
0x18002b650  jz      loc_18002B8DE
0x18002b656  movzx   eax, word ptr [r8]
0x18002b65a  lea     r8, [r8+2]
0x18002b65e  add     dx, ax
0x18002b661  add     ecx, 0FFFFFFFFh
0x18002b664  jnz     short loc_18002B656
0x18002b666  test    dx, dx
0x18002b669  jz      loc_18002B8DE
0x18002b66f  mov     [rsp+0A8h+var_80], r12d
0x18002b674  mov     rdx, rsi; lpData
0x18002b677  mov     ecx, r15d; cbBuffer
0x18002b67a  call    SetMetaFileBitsEx
0x18002b67f  mov     [rsp+0A8h+hmf], rax
0x18002b684  mov     rbx, rax
0x18002b687  test    rax, rax
0x18002b68a  jnz     short loc_18002B6A2
0x18002b68c  mov     rax, [rsp+0A8h+var_70]
0x18002b691  add     rsp, 68h
0x18002b695  pop     r15
0x18002b697  pop     r14
0x18002b699  pop     r13
0x18002b69b  pop     r12
0x18002b69d  pop     rdi
0x18002b69e  pop     rsi
0x18002b69f  pop     rbp
0x18002b6a0  pop     rbx
0x18002b6a1  retn
0x18002b6a2  mov     rbp, r12
0x18002b6a5  test    r14, r14
0x18002b6a8  jz      loc_18002B98A
0x18002b6ae  mov     [rsp+0A8h+lprc], r12
0x18002b6b3  test    r13, r13
0x18002b6b6  jnz     loc_18002B7A3
0x18002b6bc  lea     edi, [r13+8]
0x18002b6c0  mov     edx, 76h ; 'v'; index
0x18002b6c5  mov     rcx, r14; hdc
0x18002b6c8  call    cs:__imp_GetDeviceCaps
0x18002b6ce  mov     edx, 75h ; 'u'; index
0x18002b6d3  mov     rcx, r14; hdc
0x18002b6d6  mov     r12d, eax
0x18002b6d9  call    cs:__imp_GetDeviceCaps
0x18002b6df  mov     r8, [rsp+0A8h+lprc]; lprc
0x18002b6e4  mov     r13d, eax
0x18002b6e7  xor     r9d, r9d; lpDesc
0x18002b6ea  xor     edx, edx; lpFilename
0x18002b6ec  mov     rcx, r14; hdc
0x18002b6ef  call    CreateEnhMetaFileW
0x18002b6f4  mov     rbx, rax
0x18002b6f7  test    rax, rax
0x18002b6fa  jz      loc_18002B788
0x18002b700  mov     rcx, rax
0x18002b703  call    cs:__imp_pldcGet
0x18002b709  test    rax, rax
0x18002b70c  jz      loc_18002B9BC
0x18002b712  mov     ecx, ebx
0x18002b714  and     ecx, 7F0000h
0x18002b71a  cmp     ecx, 660000h
0x18002b720  jz      loc_18002B9BC
0x18002b726  cmp     [rsp+0A8h+var_80], 0
0x18002b72b  jz      short loc_18002B74C
0x18002b72d  cmp     edi, 8
0x18002b730  jnz     short loc_18002B74C
0x18002b732  mov     r14, [rax+10h]
0x18002b736  mov     r8, rsi
0x18002b739  mov     edx, r15d
0x18002b73c  mov     rcx, rbx
0x18002b73f  call    MF_GdiCommentWindowsMetaFile
0x18002b744  test    eax, eax
0x18002b746  jz      short loc_18002B773
0x18002b748  or      [r14+20h], edi
0x18002b74c  mov     edx, edi; iMode
0x18002b74e  mov     rcx, rbx; hdc
0x18002b751  call    SetMapMode
0x18002b756  test    eax, eax
0x18002b758  jz      short loc_18002B773
0x18002b75a  xor     r9d, r9d; lpsz
0x18002b75d  mov     r8d, r13d; y
0x18002b760  mov     edx, r12d; x
0x18002b763  mov     rcx, rbx; hdc
0x18002b766  call    SetViewportExtEx
0x18002b76b  test    eax, eax
0x18002b76d  jnz     loc_18002B884
0x18002b773  mov     rcx, rbx; hdc
0x18002b776  call    CloseEnhMetaFile
0x18002b77b  test    rax, rax
0x18002b77e  jz      short loc_18002B788
0x18002b780  mov     rcx, rax; hmf
0x18002b783  call    DeleteEnhMetaFile
0x18002b788  mov     rbx, [rsp+0A8h+hmf]
0x18002b78d  test    rbp, rbp
0x18002b790  jnz     loc_18002B9C3
0x18002b796  mov     rcx, rbx; hmf
0x18002b799  call    DeleteMetaFile
0x18002b79e  jmp     loc_18002B68C
0x18002b7a3  mov     edi, [r13+0]
0x18002b7a7  test    edi, edi
0x18002b7a9  jz      loc_18002B9B2
0x18002b7af  mov     ecx, edi
0x18002b7b1  sub     ecx, 1
0x18002b7b4  jz      loc_18002B6C0
0x18002b7ba  sub     ecx, 1
0x18002b7bd  jz      loc_18002B6C0
0x18002b7c3  sub     ecx, 1
0x18002b7c6  jz      loc_18002B6C0
0x18002b7cc  sub     ecx, 1
0x18002b7cf  jz      loc_18002B6C0
0x18002b7d5  sub     ecx, 1
0x18002b7d8  jz      loc_18002B6C0
0x18002b7de  sub     ecx, 1
0x18002b7e1  jz      loc_18002B6C0
0x18002b7e7  sub     ecx, 1
0x18002b7ea  jz      short loc_18002B7F1
0x18002b7ec  cmp     ecx, 1
0x18002b7ef  jnz     short loc_18002B78D
0x18002b7f1  cmp     [r13+4], r12d
0x18002b7f5  jle     loc_18002B6C0
0x18002b7fb  cmp     [r13+8], r12d
0x18002b7ff  jle     loc_18002B6C0
0x18002b805  mov     edx, 4; index
0x18002b80a  mov     rcx, r14; hdc
0x18002b80d  call    cs:__imp_GetDeviceCaps
0x18002b813  mov     edx, 76h ; 'v'; index
0x18002b818  mov     rcx, r14; hdc
0x18002b81b  imul    ebx, eax, 64h ; 'd'
0x18002b81e  call    cs:__imp_GetDeviceCaps
0x18002b824  mov     ecx, [r13+4]; nNumber
0x18002b828  mov     r8d, ebx; nDenominator
0x18002b82b  mov     edx, eax; nNumerator
0x18002b82d  call    cs:__imp_MulDiv
0x18002b833  mov     edx, 6; index
0x18002b838  mov     rcx, r14; hdc
0x18002b83b  mov     r12d, eax
0x18002b83e  call    cs:__imp_GetDeviceCaps
0x18002b844  mov     edx, 75h ; 'u'; index
0x18002b849  mov     rcx, r14; hdc
0x18002b84c  imul    ebx, eax, 64h ; 'd'
0x18002b84f  call    cs:__imp_GetDeviceCaps
0x18002b855  mov     ecx, [r13+8]; nNumber
0x18002b859  mov     r8d, ebx; nDenominator
0x18002b85c  mov     edx, eax; nNumerator
0x18002b85e  call    cs:__imp_MulDiv
0x18002b864  mov     r13d, eax
0x18002b867  lea     r8, [rsp+0A8h+var_60]
0x18002b86c  mov     rax, [rsp+0A8h+var_68]
0x18002b871  mov     ecx, [rax+4]
0x18002b874  mov     dword ptr [rsp+0A8h+var_60+8], ecx
0x18002b878  mov     ecx, [rax+8]
0x18002b87b  mov     dword ptr [rsp+0A8h+var_60+0Ch], ecx
0x18002b87f  jmp     loc_18002B6E7
0x18002b884  xor     r9d, r9d; lpsz
0x18002b887  mov     r8d, r13d; y
0x18002b88a  mov     edx, r12d; x
0x18002b88d  mov     rcx, rbx; hdc
0x18002b890  call    SetWindowExtEx
0x18002b895  test    eax, eax
0x18002b897  jz      loc_18002B773
0x18002b89d  mov     rdx, [rsp+0A8h+hmf]; hmf
0x18002b8a2  mov     rcx, rbx; hdc
0x18002b8a5  call    PlayMetaFile
0x18002b8aa  mov     rcx, rbx; hdc
0x18002b8ad  call    CloseEnhMetaFile
0x18002b8b2  mov     [rsp+0A8h+var_70], rax
0x18002b8b7  jmp     loc_18002B788
0x18002b8bc  mov     r8d, [rbx+20h]; Size
0x18002b8c0  lea     rdx, [rbx+2Ch]; Src
0x18002b8c4  lea     rcx, [rdx+r8]
0x18002b8c8  cmp     rcx, rdx
0x18002b8cb  jnb     short loc_18002B907
0x18002b8cd  mov     rcx, rbp; hMem
0x18002b8d0  call    cs:__imp_LocalFree
0x18002b8d6  xor     r12d, r12d
0x18002b8d9  jmp     loc_18002B66F
0x18002b8de  mov     r12d, [rbx+28h]
0x18002b8e2  xor     ecx, ecx; uFlags
0x18002b8e4  mov     edx, r12d; uBytes
0x18002b8e7  call    cs:__imp_LocalAlloc
0x18002b8ed  mov     rbp, rax
0x18002b8f0  test    rax, rax
0x18002b8f3  jz      short loc_18002B8D6
0x18002b8f5  mov     rax, [rsp+0A8h+hmf]
0x18002b8fa  xor     edi, edi
0x18002b8fc  lea     rcx, [rax-2Ch]
0x18002b900  mov     [rsp+0A8h+lprc], rcx
0x18002b905  jmp     short loc_18002B8BC
0x18002b907  cmp     rcx, rax
0x18002b90a  ja      short loc_18002B8CD
0x18002b90c  lea     eax, [r8+rdi]
0x18002b910  cmp     eax, r12d
0x18002b913  ja      short loc_18002B8CD
0x18002b915  mov     ecx, edi
0x18002b917  add     rcx, rbp; void *
0x18002b91a  call    memcpy_0
0x18002b91f  add     edi, [rbx+20h]
0x18002b922  mov     eax, [rbx]
0x18002b924  lea     rbx, [rbx+rax*2]
0x18002b928  cmp     rbx, [rsp+0A8h+lprc]
0x18002b92d  ja      short loc_18002B95E
0x18002b92f  mov     eax, 626h
0x18002b934  cmp     [rbx+4], ax
0x18002b938  jnz     short loc_18002B95E
0x18002b93a  cmp     dword ptr [rbx], 16h
0x18002b93d  jbe     short loc_18002B95E
0x18002b93f  cmp     word ptr [rbx+6], 0Fh
0x18002b944  jnz     short loc_18002B95E
0x18002b946  cmp     dword ptr [rbx+0Ah], 43464D57h
0x18002b94d  jnz     short loc_18002B95E
0x18002b94f  cmp     dword ptr [rbx+0Eh], 1
0x18002b953  mov     rax, [rsp+0A8h+hmf]
0x18002b958  jz      loc_18002B8BC
0x18002b95e  cmp     edi, r12d
0x18002b961  jnz     loc_18002B8CD
0x18002b967  xor     r9d, r9d
0x18002b96a  xor     r8d, r8d
0x18002b96d  xor     edx, edx
0x18002b96f  mov     rcx, rbp; unsigned int *
0x18002b972  call    SetEnhMetaFileBitsAlt
0x18002b977  mov     [rsp+0A8h+var_70], rax
0x18002b97c  test    rax, rax
0x18002b97f  jnz     loc_18002B68C
0x18002b985  jmp     loc_18002B8CD
0x18002b98a  xor     r9d, r9d; pdm
0x18002b98d  lea     rcx, String1; "DISPLAY"
0x18002b994  xor     r8d, r8d; pszPort
0x18002b997  xor     edx, edx; pszDevice
0x18002b999  call    CreateICA
0x18002b99e  mov     rbp, rax
0x18002b9a1  test    rax, rax
0x18002b9a4  jz      loc_18002B796
0x18002b9aa  mov     r14, rax
0x18002b9ad  jmp     loc_18002B6AE
0x18002b9b2  mov     edi, 8
0x18002b9b7  jmp     loc_18002B7F1
0x18002b9bc  mov     ecx, 6
0x18002b9c1  jmp     short loc_18002B9D6
0x18002b9c3  mov     rcx, rbp; hdc
0x18002b9c6  call    cs:__imp_DeleteDC
0x18002b9cc  jmp     loc_18002B796
0x18002b9d1  mov     ecx, 0Dh
0x18002b9d6  call    cs:__imp_GdiSetLastError
0x18002b9dc  xor     eax, eax
0x18002b9de  jmp     loc_18002B691
```
