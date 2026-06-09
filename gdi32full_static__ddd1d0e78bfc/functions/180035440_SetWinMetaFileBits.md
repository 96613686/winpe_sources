# SetWinMetaFileBits

- ea: `0x180035440`
- end: `0x1800358d2`
- name: `SetWinMetaFileBits`
- size: `1170`
- prototype: `HENHMETAFILE __stdcall(UINT nSize, const BYTE *lpMeta16Data, HDC hdcRef, const METAFILEPICT *lpMFP)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180075218`

## callees

- `0x180018720`
- `0x1800190c0`
- `0x180019310`
- `0x180031580`
- `0x1800315b0`
- `0x18003261c`
- `0x180033420`
- `0x180033650`
- `0x180035440`
- `0x1800358d8`
- `0x180035920`
- `0x180035f7c`
- `0x18007e1d0`
- `0x1800945e0`
- `0x1800a68d4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800357c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800357c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800357a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800357a7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800356ec`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18003572f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800356ec`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18003572f`
- `GDI32!DeleteDC` at `0x1800358a9`
- `GDI32!DeleteDC` at `0x1800358a9`
- `GDI32!GetDeviceCaps` at `0x180035569`
- `GDI32!GetDeviceCaps` at `0x180035580`
- `GDI32!GetDeviceCaps` at `0x1800356c0`
- `GDI32!GetDeviceCaps` at `0x1800356d7`
- `GDI32!GetDeviceCaps` at `0x180035703`
- `GDI32!GetDeviceCaps` at `0x18003571a`
- `GDI32!GetDeviceCaps` at `0x180035569`
- `GDI32!GetDeviceCaps` at `0x180035580`
- `GDI32!GetDeviceCaps` at `0x1800356c0`
- `GDI32!GetDeviceCaps` at `0x1800356d7`
- `GDI32!GetDeviceCaps` at `0x180035703`
- `GDI32!GetDeviceCaps` at `0x18003571a`
- `GDI32!pldcGet` at `0x1800355b0`
- `GDI32!pldcGet` at `0x1800355b0`
- `GDI32!GdiSetLastError` at `0x1800358bf`
- `GDI32!GdiSetLastError` at `0x1800358bf`

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
0x180035440  push    rbx
0x180035442  push    rbp
0x180035443  push    rsi
0x180035444  push    rdi
0x180035445  push    r12
0x180035447  push    r13
0x180035449  push    r14
0x18003544b  push    r15
0x18003544d  sub     rsp, 68h
0x180035451  xor     r12d, r12d
0x180035454  mov     [rsp+0A8h+var_68], r9
0x180035459  cmp     cs:gbDisableMetaFiles, r12d
0x180035460  xorps   xmm0, xmm0
0x180035463  mov     r13, r9
0x180035466  mov     r15d, ecx
0x180035469  mov     r14, r8
0x18003546c  mov     rsi, rdx
0x18003546f  movups  [rsp+0A8h+var_60], xmm0
0x180035474  jnz     loc_1800358CB
0x18003547a  cmp     r15d, 12h
0x18003547e  jb      loc_1800358BA
0x180035484  mov     rcx, rdx
0x180035487  call    IsValidMetaHeader16
0x18003548c  test    eax, eax
0x18003548e  jz      loc_1800358BA
0x180035494  lea     rax, [rsi+r15]
0x180035498  mov     [rsp+0A8h+var_70], r12
0x18003549d  mov     [rsp+0A8h+hmf], rax
0x1800354a2  lea     edi, [r12+1]
0x1800354a7  mov     [rsp+0A8h+var_80], edi
0x1800354ab  cmp     rax, rsi
0x1800354ae  jb      short loc_180035514
0x1800354b0  cmp     r15d, 3Eh ; '>'
0x1800354b4  jb      short loc_180035514
0x1800354b6  lea     rbx, [rsi+12h]
0x1800354ba  mov     eax, 626h
0x1800354bf  cmp     [rbx+4], ax
0x1800354c3  jnz     short loc_180035514
0x1800354c5  cmp     dword ptr [rbx], 16h
0x1800354c8  jbe     short loc_180035514
0x1800354ca  cmp     word ptr [rbx+6], 0Fh
0x1800354cf  jnz     short loc_180035514
0x1800354d1  cmp     dword ptr [rbx+0Ah], 43464D57h
0x1800354d8  jnz     short loc_180035514
0x1800354da  cmp     [rbx+0Eh], edi
0x1800354dd  jnz     short loc_180035514
0x1800354df  cmp     [rbx+18h], r12d
0x1800354e3  jnz     short loc_18003550F
0x1800354e5  mov     ecx, r15d
0x1800354e8  mov     r8, rsi
0x1800354eb  shr     ecx, 1
0x1800354ed  mov     edx, r12d
0x1800354f0  jz      loc_1800357BB
0x1800354f6  movzx   eax, word ptr [r8]
0x1800354fa  lea     r8, [r8+2]
0x1800354fe  add     dx, ax
0x180035501  add     ecx, 0FFFFFFFFh
0x180035504  jnz     short loc_1800354F6
0x180035506  test    dx, dx
0x180035509  jz      loc_1800357BB
0x18003550f  mov     [rsp+0A8h+var_80], r12d
0x180035514  mov     rdx, rsi; lpData
0x180035517  mov     ecx, r15d; cbBuffer
0x18003551a  call    SetMetaFileBitsEx
0x18003551f  mov     [rsp+0A8h+hmf], rax
0x180035524  mov     rbx, rax
0x180035527  test    rax, rax
0x18003552a  jnz     short loc_180035543
0x18003552c  mov     rax, [rsp+0A8h+var_70]
0x180035531  add     rsp, 68h
0x180035535  pop     r15
0x180035537  pop     r14
0x180035539  pop     r13
0x18003553b  pop     r12
0x18003553d  pop     rdi
0x18003553e  pop     rsi
0x18003553f  pop     rbp
0x180035540  pop     rbx
0x180035541  retn
0x180035543  mov     rbp, r12
0x180035546  test    r14, r14
0x180035549  jz      loc_18003586D
0x18003554f  mov     [rsp+0A8h+lprc], r12
0x180035554  test    r13, r13
0x180035557  jnz     loc_180035656
0x18003555d  lea     edi, [r13+8]
0x180035561  mov     edx, 76h ; 'v'; index
0x180035566  mov     rcx, r14; hdc
0x180035569  call    cs:__imp_GetDeviceCaps
0x180035570  nop     dword ptr [rax+rax+00h]
0x180035575  mov     edx, 75h ; 'u'; index
0x18003557a  mov     rcx, r14; hdc
0x18003557d  mov     r12d, eax
0x180035580  call    cs:__imp_GetDeviceCaps
0x180035587  nop     dword ptr [rax+rax+00h]
0x18003558c  mov     r8, [rsp+0A8h+lprc]; lprc
0x180035591  mov     r13d, eax
0x180035594  xor     r9d, r9d; lpDesc
0x180035597  xor     edx, edx; lpFilename
0x180035599  mov     rcx, r14; hdc
0x18003559c  call    CreateEnhMetaFileW
0x1800355a1  mov     rbx, rax
0x1800355a4  test    rax, rax
0x1800355a7  jz      loc_18003563B
0x1800355ad  mov     rcx, rax
0x1800355b0  call    cs:__imp_pldcGet
0x1800355b7  nop     dword ptr [rax+rax+00h]
0x1800355bc  test    rax, rax
0x1800355bf  jz      loc_18003589F
0x1800355c5  mov     ecx, ebx
0x1800355c7  and     ecx, 7F0000h
0x1800355cd  cmp     ecx, 660000h
0x1800355d3  jz      loc_18003589F
0x1800355d9  cmp     [rsp+0A8h+var_80], 0
0x1800355de  jz      short loc_1800355FF
0x1800355e0  cmp     edi, 8
0x1800355e3  jnz     short loc_1800355FF
0x1800355e5  mov     r14, [rax+10h]
0x1800355e9  mov     r8, rsi
0x1800355ec  mov     edx, r15d
0x1800355ef  mov     rcx, rbx
0x1800355f2  call    MF_GdiCommentWindowsMetaFile
0x1800355f7  test    eax, eax
0x1800355f9  jz      short loc_180035626
0x1800355fb  or      [r14+20h], edi
0x1800355ff  mov     edx, edi; iMode
0x180035601  mov     rcx, rbx; hdc
0x180035604  call    SetMapMode
0x180035609  test    eax, eax
0x18003560b  jz      short loc_180035626
0x18003560d  xor     r9d, r9d; lpsz
0x180035610  mov     r8d, r13d; y
0x180035613  mov     edx, r12d; x
0x180035616  mov     rcx, rbx; hdc
0x180035619  call    SetViewportExtEx
0x18003561e  test    eax, eax
0x180035620  jnz     loc_18003575B
0x180035626  mov     rcx, rbx; hdc
0x180035629  call    CloseEnhMetaFile
0x18003562e  test    rax, rax
0x180035631  jz      short loc_18003563B
0x180035633  mov     rcx, rax; hmf
0x180035636  call    DeleteEnhMetaFile
0x18003563b  mov     rbx, [rsp+0A8h+hmf]
0x180035640  test    rbp, rbp
0x180035643  jnz     loc_1800358A6
0x180035649  mov     rcx, rbx; hmf
0x18003564c  call    DeleteMetaFile
0x180035651  jmp     loc_18003552C
0x180035656  mov     edi, [r13+0]
0x18003565a  test    edi, edi
0x18003565c  jz      loc_180035895
0x180035662  mov     ecx, edi
0x180035664  sub     ecx, 1
0x180035667  jz      loc_180035561
0x18003566d  sub     ecx, 1
0x180035670  jz      loc_180035561
0x180035676  sub     ecx, 1
0x180035679  jz      loc_180035561
0x18003567f  sub     ecx, 1
0x180035682  jz      loc_180035561
0x180035688  sub     ecx, 1
0x18003568b  jz      loc_180035561
0x180035691  sub     ecx, 1
0x180035694  jz      loc_180035561
0x18003569a  sub     ecx, 1
0x18003569d  jz      short loc_1800356A4
0x18003569f  cmp     ecx, 1
0x1800356a2  jnz     short loc_180035640
0x1800356a4  cmp     [r13+4], r12d
0x1800356a8  jle     loc_180035561
0x1800356ae  cmp     [r13+8], r12d
0x1800356b2  jle     loc_180035561
0x1800356b8  mov     edx, 4; index
0x1800356bd  mov     rcx, r14; hdc
0x1800356c0  call    cs:__imp_GetDeviceCaps
0x1800356c7  nop     dword ptr [rax+rax+00h]
0x1800356cc  mov     edx, 76h ; 'v'; index
0x1800356d1  mov     rcx, r14; hdc
0x1800356d4  imul    ebx, eax, 64h ; 'd'
0x1800356d7  call    cs:__imp_GetDeviceCaps
0x1800356de  nop     dword ptr [rax+rax+00h]
0x1800356e3  mov     ecx, [r13+4]; nNumber
0x1800356e7  mov     r8d, ebx; nDenominator
0x1800356ea  mov     edx, eax; nNumerator
0x1800356ec  call    cs:__imp_MulDiv
0x1800356f3  nop     dword ptr [rax+rax+00h]
0x1800356f8  mov     edx, 6; index
0x1800356fd  mov     rcx, r14; hdc
0x180035700  mov     r12d, eax
0x180035703  call    cs:__imp_GetDeviceCaps
0x18003570a  nop     dword ptr [rax+rax+00h]
0x18003570f  mov     edx, 75h ; 'u'; index
0x180035714  mov     rcx, r14; hdc
0x180035717  imul    ebx, eax, 64h ; 'd'
0x18003571a  call    cs:__imp_GetDeviceCaps
0x180035721  nop     dword ptr [rax+rax+00h]
0x180035726  mov     ecx, [r13+8]; nNumber
0x18003572a  mov     r8d, ebx; nDenominator
0x18003572d  mov     edx, eax; nNumerator
0x18003572f  call    cs:__imp_MulDiv
0x180035736  nop     dword ptr [rax+rax+00h]
0x18003573b  mov     r13d, eax
0x18003573e  lea     r8, [rsp+0A8h+var_60]
0x180035743  mov     rax, [rsp+0A8h+var_68]
0x180035748  mov     ecx, [rax+4]
0x18003574b  mov     dword ptr [rsp+0A8h+var_60+8], ecx
0x18003574f  mov     ecx, [rax+8]
0x180035752  mov     dword ptr [rsp+0A8h+var_60+0Ch], ecx
0x180035756  jmp     loc_180035594
0x18003575b  xor     r9d, r9d; lpsz
0x18003575e  mov     r8d, r13d; y
0x180035761  mov     edx, r12d; x
0x180035764  mov     rcx, rbx; hdc
0x180035767  call    SetWindowExtEx
0x18003576c  test    eax, eax
0x18003576e  jz      loc_180035626
0x180035774  mov     rdx, [rsp+0A8h+hmf]; hmf
0x180035779  mov     rcx, rbx; hdc
0x18003577c  call    PlayMetaFile
0x180035781  mov     rcx, rbx; hdc
0x180035784  call    CloseEnhMetaFile
0x180035789  mov     [rsp+0A8h+var_70], rax
0x18003578e  jmp     loc_18003563B
0x180035793  mov     r8d, [rbx+20h]; Size
0x180035797  lea     rdx, [rbx+2Ch]; Src
0x18003579b  lea     rcx, [rdx+r8]
0x18003579f  cmp     rcx, rdx
0x1800357a2  jnb     short loc_1800357EA
0x1800357a4  mov     rcx, rbp; hMem
0x1800357a7  call    cs:__imp_LocalFree
0x1800357ae  nop     dword ptr [rax+rax+00h]
0x1800357b3  xor     r12d, r12d
0x1800357b6  jmp     loc_18003550F
0x1800357bb  mov     r12d, [rbx+28h]
0x1800357bf  xor     ecx, ecx; uFlags
0x1800357c1  mov     edx, r12d; uBytes
0x1800357c4  call    cs:__imp_LocalAlloc
0x1800357cb  nop     dword ptr [rax+rax+00h]
0x1800357d0  mov     rbp, rax
0x1800357d3  test    rax, rax
0x1800357d6  jz      short loc_1800357B3
0x1800357d8  mov     rax, [rsp+0A8h+hmf]
0x1800357dd  xor     edi, edi
0x1800357df  lea     rcx, [rax-2Ch]
0x1800357e3  mov     [rsp+0A8h+lprc], rcx
0x1800357e8  jmp     short loc_180035793
0x1800357ea  cmp     rcx, rax
0x1800357ed  ja      short loc_1800357A4
0x1800357ef  lea     eax, [r8+rdi]
0x1800357f3  cmp     eax, r12d
0x1800357f6  ja      short loc_1800357A4
0x1800357f8  mov     ecx, edi
0x1800357fa  add     rcx, rbp; void *
0x1800357fd  call    memcpy_0
0x180035802  add     edi, [rbx+20h]
0x180035805  mov     eax, [rbx]
0x180035807  lea     rbx, [rbx+rax*2]
0x18003580b  cmp     rbx, [rsp+0A8h+lprc]
0x180035810  ja      short loc_180035841
0x180035812  mov     eax, 626h
0x180035817  cmp     [rbx+4], ax
0x18003581b  jnz     short loc_180035841
0x18003581d  cmp     dword ptr [rbx], 16h
0x180035820  jbe     short loc_180035841
0x180035822  cmp     word ptr [rbx+6], 0Fh
0x180035827  jnz     short loc_180035841
0x180035829  cmp     dword ptr [rbx+0Ah], 43464D57h
0x180035830  jnz     short loc_180035841
0x180035832  cmp     dword ptr [rbx+0Eh], 1
0x180035836  mov     rax, [rsp+0A8h+hmf]
0x18003583b  jz      loc_180035793
0x180035841  cmp     edi, r12d
0x180035844  jnz     loc_1800357A4
0x18003584a  xor     r9d, r9d
0x18003584d  xor     r8d, r8d
0x180035850  xor     edx, edx
0x180035852  mov     rcx, rbp; unsigned int *
0x180035855  call    SetEnhMetaFileBitsAlt
0x18003585a  mov     [rsp+0A8h+var_70], rax
0x18003585f  test    rax, rax
0x180035862  jnz     loc_18003552C
0x180035868  jmp     loc_1800357A4
0x18003586d  xor     r9d, r9d; pdm
0x180035870  lea     rcx, String1; "DISPLAY"
0x180035877  xor     r8d, r8d; pszPort
0x18003587a  xor     edx, edx; pszDevice
0x18003587c  call    CreateICA
0x180035881  mov     rbp, rax
0x180035884  test    rax, rax
0x180035887  jz      loc_180035649
0x18003588d  mov     r14, rax
0x180035890  jmp     loc_18003554F
0x180035895  mov     edi, 8
0x18003589a  jmp     loc_1800356A4
0x18003589f  mov     ecx, 6
0x1800358a4  jmp     short loc_1800358BF
0x1800358a6  mov     rcx, rbp; hdc
0x1800358a9  call    cs:__imp_DeleteDC
0x1800358b0  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
