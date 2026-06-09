# CreateMappedBitmap

- ea: `0x1800186d0`
- end: `0x180018ab1`
- name: `CreateMappedBitmap`
- size: `993`
- prototype: `HBITMAP __stdcall(HINSTANCE hInstance, INT_PTR idBitmap, UINT wFlags, LPCOLORMAP lpColorMap, int iNumMaps)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800264a0`

## callees

- `0x1800115f0`
- `0x1800186d0`
- `0x18008e3b0`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1800188d4`
- `GDI32!CreateCompatibleDC` at `0x1800188d4`
- `GDI32!CreateDIBSection` at `0x180018924`
- `GDI32!CreateDIBSection` at `0x180018924`
- `GDI32!CreateCompatibleBitmap` at `0x180018944`
- `GDI32!CreateCompatibleBitmap` at `0x180018944`
- `GDI32!SelectObject` at `0x180018965`
- `GDI32!SelectObject` at `0x180018a4e`
- `GDI32!SelectObject` at `0x180018965`
- `GDI32!SelectObject` at `0x180018a4e`
- `GDI32!StretchDIBits` at `0x1800189a7`
- `GDI32!StretchDIBits` at `0x180018a13`
- `GDI32!StretchDIBits` at `0x1800189a7`
- `GDI32!StretchDIBits` at `0x180018a13`
- `GDI32!BitBlt` at `0x180018a42`
- `GDI32!BitBlt` at `0x180018a42`
- `GDI32!DeleteObject` at `0x180018a57`
- `GDI32!DeleteObject` at `0x180018a57`
- `KERNEL32!FindResourceW` at `0x180018714`
- `KERNEL32!FindResourceW` at `0x180018714`
- `KERNEL32!LoadResource` at `0x180018729`
- `KERNEL32!LoadResource` at `0x180018729`
- `KERNEL32!LockResource` at `0x18001873f`
- `KERNEL32!LockResource` at `0x18001873f`
- `KERNEL32!GlobalAlloc` at `0x18001878d`
- `KERNEL32!GlobalAlloc` at `0x18001878d`
- `KERNEL32!GlobalFree` at `0x180018a70`
- `KERNEL32!GlobalFree` at `0x180018a70`
- `KERNEL32!FreeResource` at `0x180018a7a`
- `KERNEL32!FreeResource` at `0x180018a7a`
- `USER32!GetSysColor` at `0x1800187d5`
- `USER32!GetSysColor` at `0x1800187d5`
- `USER32!GetDC` at `0x1800188c8`
- `USER32!GetDC` at `0x1800188c8`
- `USER32!ReleaseDC` at `0x180018a67`
- `USER32!ReleaseDC` at `0x180018a67`

## pseudocode

```c
HBITMAP __stdcall CreateMappedBitmap(
        HINSTANCE hInstance,
        INT_PTR idBitmap,
        UINT wFlags,
        LPCOLORMAP lpColorMap,
        int iNumMaps)
{
  HRSRC ResourceW; // rax
  HGLOBAL Resource; // rax
  unsigned int *v9; // rax
  unsigned int *v10; // r14
  char v11; // cl
  HBITMAP v12; // r13
  __int64 v13; // rax
  unsigned __int64 v14; // rcx
  size_t v15; // rdi
  BITMAPINFO *v16; // rax
  BITMAPINFO *lpbmi; // rbx
  int v18; // esi
  int v19; // r12d
  __int64 v20; // rdi
  int v21; // ecx
  int v22; // r8d
  __int64 v23; // rdx
  int v24; // eax
  _DWORD *v25; // rdx
  __int64 i; // r8
  int v27; // ecx
  int v28; // eax
  int SrcWidth; // esi
  int SrcHeight; // r12d
  HDC DC; // r15
  HDC CompatibleDC; // rdi
  int v33; // r13d
  DWORD biCompression; // eax
  HBITMAP CompatibleBitmap; // rax
  char *lpBits; // r13
  HGDIOBJ v37; // r14
  __int128 v38; // xmm1
  __int128 v39; // xmm0
  __int128 v40; // xmm1
  char v42; // [rsp+70h] [rbp-90h]
  DWORD v43; // [rsp+70h] [rbp-90h]
  int v44; // [rsp+74h] [rbp-8Ch]
  HBITMAP v45; // [rsp+78h] [rbp-88h]
  _OWORD *v46; // [rsp+80h] [rbp-80h]
  void *ppvBits; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v48; // [rsp+90h] [rbp-70h]
  HGLOBAL hResData; // [rsp+98h] [rbp-68h]
  _OWORD v50[4]; // [rsp+A0h] [rbp-60h]
  _DWORD v51[44]; // [rsp+E0h] [rbp-20h] BYREF

  v42 = wFlags;
  ResourceW = FindResourceW(hInstance, (LPCWSTR)(unsigned __int16)idBitmap, (LPCWSTR)2);
  if ( ResourceW )
  {
    Resource = LoadResource(hInstance, ResourceW);
    hResData = Resource;
    if ( Resource )
    {
      v9 = (unsigned int *)LockResource(Resource);
      v10 = v9;
      if ( v9 )
      {
        v11 = *((_BYTE *)v9 + 14);
        v12 = 0;
        v13 = 4 * (1LL << v11);
        if ( !is_mul_ok(1LL << v11, 4u)
          || (v14 = *v10, v15 = v14 + v13, v48 = v14 + v13, v14 + v13 < v14)
          || (v16 = (BITMAPINFO *)GlobalAlloc(0x40u, v14 + v13), (lpbmi = v16) == 0) )
        {
LABEL_40:
          FreeResource(hResData);
          return v12;
        }
        memmove(v16, v10, v15);
        v18 = 16;
        if ( lpColorMap )
        {
          v22 = 0;
          if ( iNumMaps <= 16 )
          {
            v19 = iNumMaps;
            if ( iNumMaps <= 0 )
            {
LABEL_15:
              v25 = (DWORD *)((char *)&lpbmi->bmiHeader.biSize + lpbmi->bmiHeader.biSize);
              v46 = v25;
              v44 = v42 & 2;
              if ( (v42 & 2) != 0 )
              {
                for ( i = 0; i != 16; ++i )
                {
                  v27 = 0xFFFFFF;
                  if ( v25[i] != 16711935 )
                    v27 = 0;
                  *((_DWORD *)v50 + i) = v27;
                }
              }
              do
              {
                --v18;
                if ( v19 > 0 )
                {
                  v28 = 0;
                  while ( (*v25 & 0xFFFFFF) != v51[2 * v28 + 12] )
                  {
                    if ( ++v28 >= v19 )
                      goto LABEL_26;
                  }
                  *v25 = v51[2 * v28 + 13];
                }
LABEL_26:
                ++v25;
              }
              while ( v18 > 0 );
              SrcWidth = v10[1];
              SrcHeight = v10[2];
              DC = GetDC(0);
              CompatibleDC = CreateCompatibleDC(DC);
              if ( CompatibleDC )
              {
                v33 = 2 * SrcWidth;
                if ( (v42 & 2) == 0 )
                  v33 = SrcWidth;
                if ( (v42 & 4) != 0 )
                {
                  biCompression = lpbmi->bmiHeader.biCompression;
                  ppvBits = 0;
                  v43 = biCompression;
                  if ( biCompression != 3 )
                    lpbmi->bmiHeader.biCompression = 0;
                  CompatibleBitmap = CreateDIBSection(DC, lpbmi, 0, &ppvBits, 0, 0);
                  v45 = CompatibleBitmap;
                  lpbmi->bmiHeader.biCompression = v43;
                  if ( CompatibleBitmap )
                    goto LABEL_35;
                }
                CompatibleBitmap = CreateCompatibleBitmap(DC, v33, SrcHeight);
                v45 = CompatibleBitmap;
                if ( CompatibleBitmap )
                {
LABEL_35:
                  lpBits = (char *)v10 + v48;
                  v37 = SelectObject(CompatibleDC, CompatibleBitmap);
                  StretchDIBits(
                    CompatibleDC,
                    0,
                    0,
                    SrcWidth,
                    SrcHeight,
                    0,
                    0,
                    SrcWidth,
                    SrcHeight,
                    lpBits,
                    lpbmi,
                    0,
                    0xCC0020u);
                  if ( v44 )
                  {
                    v38 = v50[1];
                    *v46 = v50[0];
                    v39 = v50[2];
                    v46[1] = v38;
                    v40 = v50[3];
                    v46[2] = v39;
                    v46[3] = v40;
                    StretchDIBits(
                      CompatibleDC,
                      SrcWidth,
                      0,
                      SrcWidth,
                      SrcHeight,
                      0,
                      0,
                      SrcWidth,
                      SrcHeight,
                      lpBits,
                      lpbmi,
                      0,
                      0xCC0020u);
                    BitBlt(CompatibleDC, 0, 0, SrcWidth, SrcHeight, CompatibleDC, SrcWidth, 0, 0x220326u);
                  }
                  SelectObject(CompatibleDC, v37);
                }
                DeleteObject(CompatibleDC);
                v12 = v45;
              }
              ReleaseDC(0, DC);
              GlobalFree(lpbmi);
              goto LABEL_40;
            }
          }
          else
          {
            v19 = 16;
          }
        }
        else
        {
          v19 = 6;
          v20 = 0;
          lpColorMap = (LPCOLORMAP)v51;
          do
          {
            v21 = HIDWORD(qword_18009A4E0[v20]);
            v51[2 * v20] = qword_18009A4E0[v20];
            v51[2 * v20++ + 1] = GetSysColor(v21);
          }
          while ( v20 != 6 );
          v22 = 0;
          v12 = 0;
        }
        do
        {
          v23 = v22++;
          v24 = BYTE2(lpColorMap[v23].from);
          v51[2 * v23 + 13] = (LOBYTE(lpColorMap[v23].to) << 16)
                            | BYTE2(lpColorMap[v23].to)
                            | (BYTE1(lpColorMap[v23].to) << 8);
          v51[2 * v23 + 12] = (LOBYTE(lpColorMap[v23].from) << 16) | v24 | (BYTE1(lpColorMap[v23].from) << 8);
        }
        while ( v22 < v19 );
        goto LABEL_15;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800186d0  mov     [rsp-8+arg_10], rbx
0x1800186d5  push    rbp
0x1800186d6  push    rsi
0x1800186d7  push    rdi
0x1800186d8  push    r12
0x1800186da  push    r13
0x1800186dc  push    r14
0x1800186de  push    r15
0x1800186e0  lea     rbp, [rsp-0A0h]
0x1800186e8  sub     rsp, 1A0h
0x1800186ef  mov     rax, cs:__security_cookie
0x1800186f6  xor     rax, rsp
0x1800186f9  mov     [rbp+0D0h+var_40], rax
0x180018700  mov     [rsp+1D0h+var_160], r8d
0x180018705  mov     r15, r9
0x180018708  mov     r8d, 2; lpType
0x18001870e  movzx   edx, dx; lpName
0x180018711  mov     rbx, rcx
0x180018714  call    cs:__imp_FindResourceW
0x18001871a  test    rax, rax
0x18001871d  jz      loc_180018A85
0x180018723  mov     rdx, rax; hResInfo
0x180018726  mov     rcx, rbx; hModule
0x180018729  call    cs:__imp_LoadResource
0x18001872f  mov     [rbp+0D0h+hResData], rax
0x180018733  test    rax, rax
0x180018736  jz      loc_180018A85
0x18001873c  mov     rcx, rax; hResData
0x18001873f  call    cs:__imp_LockResource
0x180018745  mov     r14, rax
0x180018748  test    rax, rax
0x18001874b  jz      loc_180018A85
0x180018751  mov     cl, [rax+0Eh]
0x180018754  xor     r13d, r13d
0x180018757  mov     [rbp+0D0h+var_150], r13
0x18001875b  lea     edx, [r13+1]
0x18001875f  shl     rdx, cl
0x180018762  lea     eax, [r13+4]
0x180018766  mul     rdx
0x180018769  test    rdx, rdx
0x18001876c  jnz     loc_180018A76
0x180018772  mov     ecx, [r14]
0x180018775  lea     rdi, [rcx+rax]
0x180018779  mov     [rbp+0D0h+var_140], rdi
0x18001877d  cmp     rdi, rcx
0x180018780  jb      loc_180018A76
0x180018786  mov     rdx, rdi; dwBytes
0x180018789  lea     ecx, [r13+40h]; uFlags
0x18001878d  call    cs:__imp_GlobalAlloc
0x180018793  mov     rbx, rax
0x180018796  test    rax, rax
0x180018799  jz      loc_180018A76
0x18001879f  mov     r8, rdi; Size
0x1800187a2  mov     rdx, r14; Src
0x1800187a5  mov     rcx, rax; void *
0x1800187a8  call    memmove
0x1800187ad  lea     esi, [r13+10h]
0x1800187b1  test    r15, r15
0x1800187b4  jnz     short loc_1800187EF
0x1800187b6  lea     r12d, [r13+6]
0x1800187ba  xor     edi, edi
0x1800187bc  lea     r13, qword_18009A4E0
0x1800187c3  lea     r15, [rbp+0D0h+var_F0]
0x1800187c7  mov     eax, [r13+rdi*8+0]
0x1800187cc  mov     ecx, [r13+rdi*8+4]; nIndex
0x1800187d1  mov     [rbp+rdi*8+0D0h+var_F0], eax
0x1800187d5  call    cs:__imp_GetSysColor
0x1800187db  mov     [rbp+rdi*8+0D0h+var_EC], eax
0x1800187df  inc     rdi
0x1800187e2  cmp     rdi, r12
0x1800187e5  jnz     short loc_1800187C7
0x1800187e7  xor     r8d, r8d
0x1800187ea  xor     r13d, r13d
0x1800187ed  jmp     short loc_180018808
0x1800187ef  mov     eax, [rbp+0D0h+iNumMaps]
0x1800187f5  xor     r8d, r8d
0x1800187f8  cmp     eax, esi
0x1800187fa  jle     short loc_180018801
0x1800187fc  mov     r12d, esi
0x1800187ff  jmp     short loc_180018808
0x180018801  mov     r12d, eax
0x180018804  test    eax, eax
0x180018806  jle     short loc_180018852
0x180018808  movsxd  rdx, r8d
0x18001880b  inc     r8d
0x18001880e  movzx   eax, byte ptr [r15+rdx*8+6]
0x180018814  movzx   ecx, byte ptr [r15+rdx*8+5]
0x18001881a  shl     ecx, 8
0x18001881d  or      ecx, eax
0x18001881f  movzx   eax, byte ptr [r15+rdx*8+4]
0x180018825  shl     eax, 10h
0x180018828  or      ecx, eax
0x18001882a  movzx   eax, byte ptr [r15+rdx*8+2]
0x180018830  mov     [rbp+rdx*8+0D0h+var_BC], ecx
0x180018834  movzx   ecx, byte ptr [r15+rdx*8+1]
0x18001883a  shl     ecx, 8
0x18001883d  or      ecx, eax
0x18001883f  movzx   eax, byte ptr [r15+rdx*8]
0x180018844  shl     eax, 10h
0x180018847  or      ecx, eax
0x180018849  mov     [rbp+rdx*8+0D0h+var_C0], ecx
0x18001884d  cmp     r8d, r12d
0x180018850  jl      short loc_180018808
0x180018852  mov     edx, [rbx]
0x180018854  mov     r9d, 0FFFFFFh
0x18001885a  mov     eax, [rsp+1D0h+var_160]
0x18001885e  add     rdx, rbx
0x180018861  and     eax, 2
0x180018864  mov     [rbp+0D0h+var_150], rdx
0x180018868  mov     [rsp+1D0h+var_15C], eax
0x18001886c  jz      short loc_18001888E
0x18001886e  xor     r8d, r8d
0x180018871  xor     eax, eax
0x180018873  mov     ecx, r9d
0x180018876  cmp     dword ptr [rdx+r8*4], 0FF00FFh
0x18001887e  cmovnz  ecx, eax
0x180018881  mov     dword ptr [rbp+r8*4+0D0h+var_130], ecx
0x180018886  inc     r8
0x180018889  cmp     r8, rsi
0x18001888c  jnz     short loc_180018871
0x18001888e  dec     esi
0x180018890  test    r12d, r12d
0x180018893  jle     short loc_1800188B6
0x180018895  mov     ecx, [rdx]
0x180018897  xor     eax, eax
0x180018899  and     ecx, r9d
0x18001889c  movsxd  r8, eax
0x18001889f  cmp     ecx, [rbp+r8*8+0D0h+var_C0]
0x1800188a4  jz      short loc_1800188AF
0x1800188a6  inc     eax
0x1800188a8  cmp     eax, r12d
0x1800188ab  jl      short loc_18001889C
0x1800188ad  jmp     short loc_1800188B6
0x1800188af  mov     eax, [rbp+r8*8+0D0h+var_BC]
0x1800188b4  mov     [rdx], eax
0x1800188b6  add     rdx, 4
0x1800188ba  test    esi, esi
0x1800188bc  jg      short loc_18001888E
0x1800188be  mov     esi, [r14+4]
0x1800188c2  xor     ecx, ecx; hWnd
0x1800188c4  mov     r12d, [r14+8]
0x1800188c8  call    cs:__imp_GetDC
0x1800188ce  mov     rcx, rax; hdc
0x1800188d1  mov     r15, rax
0x1800188d4  call    cs:__imp_CreateCompatibleDC
0x1800188da  xor     ecx, ecx
0x1800188dc  mov     rdi, rax
0x1800188df  test    rax, rax
0x1800188e2  jz      loc_180018A62
0x1800188e8  cmp     [rsp+1D0h+var_15C], ecx
0x1800188ec  lea     r13d, [rsi+rsi]
0x1800188f0  cmovz   r13d, esi
0x1800188f4  test    byte ptr [rsp+1D0h+var_160], 4
0x1800188f9  jz      short loc_18001893B
0x1800188fb  mov     eax, [rbx+10h]
0x1800188fe  mov     [rbp+0D0h+ppvBits], rcx
0x180018902  mov     [rsp+1D0h+var_160], eax
0x180018906  cmp     eax, 3
0x180018909  jz      short loc_18001890E
0x18001890b  mov     [rbx+10h], ecx
0x18001890e  mov     [rsp+1D0h+offset], ecx; offset
0x180018912  lea     r9, [rbp+0D0h+ppvBits]; ppvBits
0x180018916  mov     [rsp+1D0h+hSection], rcx; hSection
0x18001891b  xor     r8d, r8d; usage
0x18001891e  mov     rcx, r15; hdc
0x180018921  mov     rdx, rbx; pbmi
0x180018924  call    cs:__imp_CreateDIBSection
0x18001892a  mov     ecx, [rsp+1D0h+var_160]
0x18001892e  mov     [rsp+1D0h+var_158], rax
0x180018933  mov     [rbx+10h], ecx
0x180018936  test    rax, rax
0x180018939  jnz     short loc_180018958
0x18001893b  mov     r8d, r12d; cy
0x18001893e  mov     edx, r13d; cx
0x180018941  mov     rcx, r15; hdc
0x180018944  call    cs:__imp_CreateCompatibleBitmap
0x18001894a  mov     [rsp+1D0h+var_158], rax
0x18001894f  test    rax, rax
0x180018952  jz      loc_180018A54
0x180018958  mov     r13, [rbp+0D0h+var_140]
0x18001895c  mov     rdx, rax; h
0x18001895f  mov     rcx, rdi; hdc
0x180018962  add     r13, r14
0x180018965  call    cs:__imp_SelectObject
0x18001896b  mov     [rsp+1D0h+rop], 0CC0020h; rop
0x180018973  mov     r9d, esi; DestWidth
0x180018976  mov     r14, rax
0x180018979  xor     r8d, r8d; yDest
0x18001897c  xor     eax, eax
0x18001897e  xor     edx, edx; xDest
0x180018980  mov     [rsp+1D0h+iUsage], eax; iUsage
0x180018984  mov     rcx, rdi; hdc
0x180018987  mov     [rsp+1D0h+lpbmi], rbx; lpbmi
0x18001898c  mov     [rsp+1D0h+lpBits], r13; lpBits
0x180018991  mov     [rsp+1D0h+SrcHeight], r12d; SrcHeight
0x180018996  mov     [rsp+1D0h+SrcWidth], esi; SrcWidth
0x18001899a  mov     [rsp+1D0h+ySrc], eax; ySrc
0x18001899e  mov     [rsp+1D0h+offset], eax; xSrc
0x1800189a2  mov     dword ptr [rsp+1D0h+hSection], r12d; DestHeight
0x1800189a7  call    cs:__imp_StretchDIBits
0x1800189ad  xor     ecx, ecx
0x1800189af  cmp     [rsp+1D0h+var_15C], ecx
0x1800189b3  jz      loc_180018A48
0x1800189b9  mov     rax, [rbp+0D0h+var_150]
0x1800189bd  mov     r9d, esi; DestWidth
0x1800189c0  movaps  xmm0, [rbp+0D0h+var_130]
0x1800189c4  xor     r8d, r8d; yDest
0x1800189c7  movaps  xmm1, [rbp+0D0h+var_120]
0x1800189cb  mov     edx, esi; xDest
0x1800189cd  mov     [rsp+1D0h+rop], 0CC0020h; rop
0x1800189d5  mov     [rsp+1D0h+iUsage], ecx; iUsage
0x1800189d9  mov     [rsp+1D0h+lpbmi], rbx; lpbmi
0x1800189de  mov     [rsp+1D0h+lpBits], r13; lpBits
0x1800189e3  movups  xmmword ptr [rax], xmm0
0x1800189e6  mov     [rsp+1D0h+SrcHeight], r12d; SrcHeight
0x1800189eb  movaps  xmm0, [rbp+0D0h+var_110]
0x1800189ef  movups  xmmword ptr [rax+10h], xmm1
0x1800189f3  mov     [rsp+1D0h+SrcWidth], esi; SrcWidth
0x1800189f7  movaps  xmm1, [rbp+0D0h+var_100]
0x1800189fb  mov     [rsp+1D0h+ySrc], ecx; ySrc
0x1800189ff  mov     [rsp+1D0h+offset], ecx; xSrc
0x180018a03  mov     rcx, rdi; hdc
0x180018a06  movups  xmmword ptr [rax+20h], xmm0
0x180018a0a  mov     dword ptr [rsp+1D0h+hSection], r12d; DestHeight
0x180018a0f  movups  xmmword ptr [rax+30h], xmm1
0x180018a13  call    cs:__imp_StretchDIBits
0x180018a19  mov     [rsp+1D0h+SrcHeight], 220326h; rop
0x180018a21  mov     r9d, esi; cx
0x180018a24  mov     [rsp+1D0h+SrcWidth], 0; y1
0x180018a2c  xor     r8d, r8d; y
0x180018a2f  mov     [rsp+1D0h+ySrc], esi; x1
0x180018a33  xor     edx, edx; x
0x180018a35  mov     qword ptr [rsp+1D0h+offset], rdi; hdcSrc
0x180018a3a  mov     rcx, rdi; hdc
0x180018a3d  mov     dword ptr [rsp+1D0h+hSection], r12d; cy
0x180018a42  call    cs:__imp_BitBlt
0x180018a48  mov     rdx, r14; h
0x180018a4b  mov     rcx, rdi; hdc
0x180018a4e  call    cs:__imp_SelectObject
0x180018a54  mov     rcx, rdi; ho
0x180018a57  call    cs:__imp_DeleteObject
0x180018a5d  mov     r13, [rsp+1D0h+var_158]
0x180018a62  mov     rdx, r15; hDC
0x180018a65  xor     ecx, ecx; hWnd
0x180018a67  call    cs:__imp_ReleaseDC
0x180018a6d  mov     rcx, rbx; hMem
0x180018a70  call    cs:__imp_GlobalFree
0x180018a76  mov     rcx, [rbp+0D0h+hResData]; hResData
0x180018a7a  call    cs:__imp_FreeResource
0x180018a80  mov     rax, r13
0x180018a83  jmp     short loc_180018A87
0x180018a85  xor     eax, eax
0x180018a87  mov     rcx, [rbp+0D0h+var_40]
0x180018a8e  xor     rcx, rsp; StackCookie
0x180018a91  call    __security_check_cookie
0x180018a96  mov     rbx, [rsp+1D0h+arg_10]
0x180018a9e  add     rsp, 1A0h
0x180018aa5  pop     r15
0x180018aa7  pop     r14
0x180018aa9  pop     r13
0x180018aab  pop     r12
0x180018aad  pop     rdi
0x180018aae  pop     rsi
0x180018aaf  pop     rbp
0x180018ab0  retn
```
