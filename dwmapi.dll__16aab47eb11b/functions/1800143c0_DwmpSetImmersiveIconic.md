# DwmpSetImmersiveIconic

- ea: `0x1800143c0`
- end: `0x1800148a5`
- name: `DwmpSetImmersiveIconic`
- size: `1253`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000352c`
- `0x180008ab4`
- `0x18000b8dc`
- `0x18000b92c`
- `0x18000b990`
- `0x18000d0a0`
- `0x18000ddc4`
- `0x1800143c0`
- `0x180014af0`
- `0x180014b4c`
- `0x180015224`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014468`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180014468`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800144fe`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x1800144fe`
- `USER32!GetWindowThreadProcessId` at `0x180014462`
- `USER32!GetWindowThreadProcessId` at `0x180014462`
- `USER32!GetShellWindow` at `0x18001444a`
- `USER32!GetShellWindow` at `0x18001444a`
- `GDI32!DeleteObject` at `0x1800147c1`
- `GDI32!DeleteObject` at `0x1800147c1`
- `GDI32!DeleteDC` at `0x1800147af`
- `GDI32!DeleteDC` at `0x1800147d3`
- `GDI32!DeleteDC` at `0x1800147af`
- `GDI32!DeleteDC` at `0x1800147d3`
- `GDI32!GdiAlphaBlend` at `0x1800146b8`
- `GDI32!GdiAlphaBlend` at `0x1800146b8`
- `GDI32!StretchDIBits` at `0x180014631`
- `GDI32!StretchDIBits` at `0x180014631`
- `GDI32!CreateDIBSection` at `0x18001457f`
- `GDI32!CreateDIBSection` at `0x18001457f`
- `GDI32!CreateCompatibleDC` at `0x180014533`
- `GDI32!CreateCompatibleDC` at `0x18001463a`
- `GDI32!CreateCompatibleDC` at `0x180014533`
- `GDI32!CreateCompatibleDC` at `0x18001463a`
- `GDI32!GetObjectW` at `0x1800144ad`
- `GDI32!GetObjectW` at `0x1800144ad`
- `GDI32!SelectObject` at `0x1800145c0`
- `GDI32!SelectObject` at `0x180014666`
- `GDI32!SelectObject` at `0x1800146c4`
- `GDI32!SelectObject` at `0x1800147a6`
- `GDI32!SelectObject` at `0x1800145c0`
- `GDI32!SelectObject` at `0x180014666`
- `GDI32!SelectObject` at `0x1800146c4`
- `GDI32!SelectObject` at `0x1800147a6`

## pseudocode

```c
__int64 __fastcall DwmpSetImmersiveIconic(void *a1, void *a2, int a3, int a4)
{
  bool v8; // di
  HWND ShellWindow; // rax
  CApiPortClient *v10; // rcx
  int ObjectW; // r12d
  int v12; // r14d
  LONG cx; // r14d
  int v14; // esi
  int cy; // esi
  HDC v16; // r15
  HDC CompatibleDC; // rax
  HDC v18; // r12
  BLENDFUNCTION v19; // ebx
  __int64 v20; // rcx
  HBITMAP v21; // rax
  void *v22; // r14
  BLENDFUNCTION v23; // esi
  HDC v24; // rax
  HGDIOBJ v25; // rbx
  __int64 v26; // rcx
  signed int v27; // eax
  int v28; // ebx
  int v29; // eax
  int v30; // eax
  unsigned int hSection; // [rsp+20h] [rbp-E0h]
  unsigned int hSectiona; // [rsp+20h] [rbp-E0h]
  void *offset; // [rsp+28h] [rbp-D8h]
  void *offseta; // [rsp+28h] [rbp-D8h]
  void *offsetb; // [rsp+28h] [rbp-D8h]
  void *offsetc; // [rsp+28h] [rbp-D8h]
  BLENDFUNCTION ftn; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwProcessId; // [rsp+74h] [rbp-8Ch] BYREF
  struct tagSIZE v40; // [rsp+78h] [rbp-88h] BYREF
  HGDIOBJ v41; // [rsp+80h] [rbp-80h]
  HGDIOBJ ho; // [rsp+88h] [rbp-78h]
  void **v43; // [rsp+90h] [rbp-70h] BYREF
  __int128 v44; // [rsp+98h] [rbp-68h]
  HGDIOBJ h[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v46; // [rsp+B8h] [rbp-48h]
  int v47; // [rsp+BCh] [rbp-44h]
  BITMAPINFO pbmi; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE pv[4]; // [rsp+F0h] [rbp-10h] BYREF
  int nNumerator; // [rsp+F4h] [rbp-Ch]
  int nDenominator; // [rsp+F8h] [rbp-8h]
  unsigned __int16 v52; // [rsp+102h] [rbp+2h]
  int v53; // [rsp+130h] [rbp+30h]

  h[0] = a2;
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0p_EtwEventWriteTransfer(a1, ApiSetIconicThumbnail_Start, a1);
  ftn = (BLENDFUNCTION)33488896;
  pbmi.bmiHeader.biSize = 40;
  v43 = &CStandardData::`vftable';
  v8 = 0;
  v44 = 0;
  memset(&pbmi.bmiHeader.biWidth, 0, 40);
  ShellWindow = GetShellWindow();
  if ( ShellWindow )
  {
    dwProcessId = 0;
    GetWindowThreadProcessId(ShellWindow, &dwProcessId);
    v8 = GetCurrentProcessId() == dwProcessId;
  }
  if ( !a1 || !v8 )
  {
    hSectiona = 794;
    goto LABEL_44;
  }
  if ( !a2 )
  {
    LODWORD(h[0]) = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
    *(HGDIOBJ *)((char *)h + 4) = a1;
    HIDWORD(h[1]) = a3;
    ftn = 0;
    v30 = CApiPortClient::SendRequestValidate(v10, h, 0x10u, (int *)&ftn);
    v19 = (BLENDFUNCTION)v30;
    if ( v30 < 0 )
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A170, 2u, v30, 0x37Cu, offset);
    else
      v19 = ftn;
    goto LABEL_45;
  }
  memset_0(pv, 0, 0x68u);
  ObjectW = GetObjectW(a2, 104, pv);
  v40 = 0;
  v12 = -nNumerator;
  if ( nNumerator > 0 )
    v12 = nNumerator;
  cx = v12 + 2;
  v14 = -nDenominator;
  v40.cx = cx;
  if ( nDenominator > 0 )
    v14 = nDenominator;
  cy = v14 + 2;
  v40.cy = cy;
  if ( a4 && a4 > nNumerator )
  {
    cx = a4 + 2;
    v40.cx = a4 + 2;
    cy = MulDiv(a4, nNumerator, nDenominator) + 2;
    v40.cy = cy;
  }
  if ( ObjectW != 104 || v52 != 32 || (v16 = 0, v53) )
  {
    hSectiona = 815;
LABEL_44:
    v19 = (BLENDFUNCTION)-2147024809;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A170, 2u, -2147024809, hSectiona, offset);
    goto LABEL_45;
  }
  CompatibleDC = CreateCompatibleDC(0);
  v18 = CompatibleDC;
  if ( !CompatibleDC )
  {
    v19 = (BLENDFUNCTION)-2147024882;
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A170, 2u, -2147024882, 0x335u, offset);
    goto LABEL_45;
  }
  pbmi.bmiHeader.biWidth = cx;
  pbmi.bmiHeader.biHeight = cy;
  *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
  v21 = CreateDIBSection(CompatibleDC, &pbmi, 0, 0, 0, 0);
  ho = v21;
  if ( v21 )
  {
    v41 = SelectObject(v18, v21);
    BYTE2(dwProcessId) = a3;
    pbmi.bmiHeader.biWidth = 1;
    pbmi.bmiHeader.biHeight = 1;
    BYTE1(dwProcessId) = BYTE1(a3);
    HIBYTE(dwProcessId) = -1;
    LOBYTE(dwProcessId) = BYTE2(a3);
    StretchDIBits(v18, 0, 0, cx, cy, 0, 0, 1, 1, &dwProcessId, &pbmi, 0, 0xCC0020u);
    v24 = CreateCompatibleDC(v18);
    v16 = v24;
    if ( !v24 )
    {
      v23 = (BLENDFUNCTION)-2147024882;
      MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A170, 2u, -2147024882, 0x359u, offsetb);
LABEL_34:
      v22 = v41;
      goto LABEL_35;
    }
    v25 = SelectObject(v24, h[0]);
    GdiAlphaBlend(
      v18,
      (cx - nNumerator) / 2,
      (cy - nDenominator) / 2,
      nNumerator,
      nDenominator,
      v16,
      0,
      0,
      nNumerator,
      nDenominator,
      ftn);
    SelectObject(v16, v25);
    v26 = 8;
    v27 = cx * cy * v52 / 8;
    v28 = v27;
    if ( v27 > 0 )
    {
      v29 = CApiPortClient::LockExtraDataPointer((CApiPortClient *)8, v27, (struct CStandardData *)&v43);
      v23 = (BLENDFUNCTION)v29;
      if ( v29 < 0 )
      {
        hSection = 868;
        goto LABEL_33;
      }
      v29 = CopyBitmapHelper((HBITMAP)ho, &v40, v28, *(void **)(*((_QWORD *)&v44 + 1) + 24LL));
      v23 = (BLENDFUNCTION)v29;
      if ( v29 < 0 )
      {
        hSection = 870;
        goto LABEL_33;
      }
      cy = v40.cy;
      cx = v40.cx;
    }
    LODWORD(h[0]) = 1073741882;
    v47 = 0;
    ftn = 0;
    *(HGDIOBJ *)((char *)h + 4) = a1;
    HIDWORD(h[1]) = cx;
    v46 = cy;
    v29 = CApiPortClient::SendRequestValidate(
            (CApiPortClient *)v26,
            (int *)h,
            0x18u,
            (const struct CExtraData *)&v43,
            (int *)&ftn);
    v23 = (BLENDFUNCTION)v29;
    if ( v29 >= 0 )
    {
      v23 = ftn;
      goto LABEL_34;
    }
    hSection = 881;
LABEL_33:
    MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A170, 2u, v29, hSection, offsetc);
    goto LABEL_34;
  }
  v22 = 0;
  v23 = (BLENDFUNCTION)-2147024882;
  MilInstrumentationCheckHR_MaybeFailFast(4u, &qword_18001A170, 2u, -2147024882, 0x342u, offseta);
LABEL_35:
  v19 = v23;
  SelectObject(v16, v22);
  DeleteDC(v18);
  if ( ho )
    DeleteObject(ho);
  if ( v16 )
    DeleteDC(v16);
LABEL_45:
  if ( (Microsoft_Windows_Dwm_ApiEnableBits & 1) != 0 )
    McTemplateU0qp_EtwEventWriteTransfer(v20, ApiSetIconicThumbnail_Stop, *(unsigned int *)&v19, a1);
  CStandardData::~CStandardData((CStandardData *)&v43);
  return *(unsigned int *)&v19;
}

```

## disassembly

```asm
0x1800143c0  push    rbp
0x1800143c2  push    rbx
0x1800143c3  push    rsi
0x1800143c4  push    rdi
0x1800143c5  push    r12
0x1800143c7  push    r13
0x1800143c9  push    r14
0x1800143cb  push    r15
0x1800143cd  lea     rbp, [rsp-78h]
0x1800143d2  sub     rsp, 178h
0x1800143d9  mov     rax, cs:__security_cookie
0x1800143e0  xor     rax, rsp
0x1800143e3  mov     [rbp+0B0h+var_50], rax
0x1800143e7  mov     edi, 1
0x1800143ec  mov     [rbp+0B0h+h], rdx
0x1800143f0  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, dil
0x1800143f7  mov     r15d, r9d
0x1800143fa  mov     ebx, r8d
0x1800143fd  mov     rsi, rdx
0x180014400  mov     r13, rcx
0x180014403  jz      short loc_180014414
0x180014405  mov     r8, rcx
0x180014408  lea     rdx, ApiSetIconicThumbnail_Start
0x18001440f  call    McTemplateU0p_EtwEventWriteTransfer
0x180014414  xorps   xmm0, xmm0
0x180014417  mov     dword ptr [rsp+1B0h+ftn.BlendOp], 1FF0000h
0x18001441f  lea     rax, ??_7CStandardData@@6B@; const CStandardData::`vftable'
0x180014426  mov     [rbp+0B0h+pbmi.bmiHeader.biSize], 28h ; '('
0x18001442d  mov     [rbp+0B0h+var_120], rax
0x180014431  xor     r14d, r14d
0x180014434  xor     eax, eax
0x180014436  mov     dil, r14b
0x180014439  mov     qword ptr [rbp+0B0h+pbmi.bmiHeader.biClrImportant], rax
0x18001443d  movdqu  [rbp+0B0h+var_118], xmm0
0x180014442  movups  xmmword ptr [rbp+0B0h+pbmi.bmiHeader.biWidth], xmm0
0x180014446  movups  xmmword ptr [rbp+0B0h+pbmi.bmiHeader.biSizeImage], xmm0
0x18001444a  call    cs:__imp_GetShellWindow
0x180014450  test    rax, rax
0x180014453  jz      short loc_180014476
0x180014455  lea     rdx, [rsp+1B0h+dwProcessId]; lpdwProcessId
0x18001445a  mov     [rsp+1B0h+dwProcessId], r14d
0x18001445f  mov     rcx, rax; hWnd
0x180014462  call    cs:__imp_GetWindowThreadProcessId
0x180014468  call    cs:__imp_GetCurrentProcessId
0x18001446e  cmp     eax, [rsp+1B0h+dwProcessId]
0x180014472  setz    dil
0x180014476  test    r13, r13
0x180014479  jz      loc_180014837
0x18001447f  test    dil, dil
0x180014482  jz      loc_180014837
0x180014488  test    rsi, rsi
0x18001448b  jz      loc_1800147EB
0x180014491  mov     edi, 68h ; 'h'
0x180014496  lea     rcx, [rbp+0B0h+pv]; void *
0x18001449a  mov     r8d, edi; Size
0x18001449d  xor     edx, edx; Val
0x18001449f  call    memset_0
0x1800144a4  lea     r8, [rbp+0B0h+pv]; pv
0x1800144a8  mov     edx, edi; c
0x1800144aa  mov     rcx, rsi; h
0x1800144ad  call    cs:__imp_GetObjectW
0x1800144b3  mov     edx, [rbp+0B0h+nNumerator]; nNumerator
0x1800144b6  mov     edi, 2
0x1800144bb  mov     r8d, [rbp+0B0h+nDenominator]; nDenominator
0x1800144bf  mov     r12d, eax
0x1800144c2  mov     qword ptr [rsp+1B0h+var_138.cx], r14
0x1800144c7  mov     esi, r8d
0x1800144ca  mov     r14d, edx
0x1800144cd  neg     r14d
0x1800144d0  cmovs   r14d, edx
0x1800144d4  add     r14d, edi
0x1800144d7  neg     esi
0x1800144d9  mov     [rsp+1B0h+var_138.cx], r14d
0x1800144de  cmovs   esi, r8d
0x1800144e2  add     esi, edi
0x1800144e4  mov     [rsp+1B0h+var_138.cy], esi
0x1800144e8  test    r15d, r15d
0x1800144eb  jz      short loc_18001450B
0x1800144ed  cmp     r15d, edx
0x1800144f0  jle     short loc_18001450B
0x1800144f2  lea     r14d, [r15+2]
0x1800144f6  mov     ecx, r15d; nNumber
0x1800144f9  mov     [rsp+1B0h+var_138.cx], r14d
0x1800144fe  call    cs:__imp_MulDiv
0x180014504  lea     esi, [rdi+rax]
0x180014507  mov     [rsp+1B0h+var_138.cy], esi
0x18001450b  cmp     r12d, 68h ; 'h'
0x18001450f  jnz     loc_1800147DE
0x180014515  lea     eax, [r12-48h]
0x18001451a  cmp     [rbp+0B0h+var_AE], ax
0x18001451e  jnz     loc_1800147DE
0x180014524  xor     r15d, r15d
0x180014527  cmp     [rbp+0B0h+var_80], r15d
0x18001452b  ja      loc_1800147DE
0x180014531  xor     ecx, ecx; hdc
0x180014533  call    cs:__imp_CreateCompatibleDC
0x180014539  mov     r12, rax
0x18001453c  test    rax, rax
0x18001453f  jnz     short loc_180014559
0x180014541  mov     ebx, 8007000Eh
0x180014546  mov     dword ptr [rsp+1B0h+hSection], 335h
0x18001454e  mov     r9d, ebx
0x180014551  mov     r8d, edi
0x180014554  jmp     loc_18001484E
0x180014559  mov     [rsp+1B0h+offset], r15d; void *
0x18001455e  lea     rdx, [rbp+0B0h+pbmi]; pbmi
0x180014562  xor     r9d, r9d; ppvBits
0x180014565  mov     [rsp+1B0h+hSection], r15; hSection
0x18001456a  xor     r8d, r8d; usage
0x18001456d  mov     [rbp+0B0h+pbmi.bmiHeader.biWidth], r14d
0x180014571  mov     rcx, r12; hdc
0x180014574  mov     [rbp+0B0h+pbmi.bmiHeader.biHeight], esi
0x180014577  mov     qword ptr [rbp+0B0h+pbmi.bmiHeader.biPlanes], 200001h
0x18001457f  call    cs:__imp_CreateDIBSection
0x180014585  mov     [rbp+0B0h+ho], rax
0x180014589  test    rax, rax
0x18001458c  jnz     short loc_1800145BA
0x18001458e  mov     ebx, 8007000Eh
0x180014593  mov     dword ptr [rsp+1B0h+hSection], 342h; unsigned int
0x18001459b  mov     r9d, ebx; int
0x18001459e  lea     rdx, qword_18001A170; int *
0x1800145a5  xor     r14d, r14d
0x1800145a8  lea     ecx, [rax+4]; unsigned int
0x1800145ab  mov     r8d, edi; unsigned int
0x1800145ae  mov     esi, ebx
0x1800145b0  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800145b5  jmp     loc_18001479E
0x1800145ba  mov     rdx, rax; h
0x1800145bd  mov     rcx, r12; hdc
0x1800145c0  call    cs:__imp_SelectObject
0x1800145c6  mov     [rsp+1B0h+rop], 0CC0020h; rop
0x1800145ce  mov     edx, 1
0x1800145d3  mov     [rsp+1B0h+iUsage], r15d; iUsage
0x1800145d8  movzx   ecx, bx
0x1800145db  mov     [rbp+0B0h+var_130], rax
0x1800145df  mov     r9d, r14d; DestWidth
0x1800145e2  shr     cx, 8
0x1800145e6  lea     rax, [rbp+0B0h+pbmi]
0x1800145ea  mov     [rsp+1B0h+lpbmi], rax; lpbmi
0x1800145ef  xor     r8d, r8d; yDest
0x1800145f2  lea     rax, [rsp+1B0h+dwProcessId]
0x1800145f7  mov     byte ptr [rsp+1B0h+dwProcessId+2], bl
0x1800145fb  mov     [rsp+1B0h+lpBits], rax; lpBits
0x180014600  mov     [rsp+1B0h+SrcHeight], edx; SrcHeight
0x180014604  mov     [rsp+1B0h+SrcWidth], edx; SrcWidth
0x180014608  mov     [rsp+1B0h+ySrc], r15d; ySrc
0x18001460d  mov     [rbp+0B0h+pbmi.bmiHeader.biWidth], edx
0x180014610  mov     [rbp+0B0h+pbmi.bmiHeader.biHeight], edx
0x180014613  xor     edx, edx; xDest
0x180014615  mov     byte ptr [rsp+1B0h+dwProcessId+1], cl
0x180014619  mov     rcx, r12; hdc
0x18001461c  shr     ebx, 10h
0x18001461f  mov     [rsp+1B0h+offset], r15d; xSrc
0x180014624  mov     dword ptr [rsp+1B0h+hSection], esi; DestHeight
0x180014628  mov     byte ptr [rsp+1B0h+dwProcessId+3], 0FFh
0x18001462d  mov     byte ptr [rsp+1B0h+dwProcessId], bl
0x180014631  call    cs:__imp_StretchDIBits
0x180014637  mov     rcx, r12; hdc
0x18001463a  call    cs:__imp_CreateCompatibleDC
0x180014640  mov     r15, rax
0x180014643  test    rax, rax
0x180014646  jnz     short loc_18001465F
0x180014648  mov     ebx, 8007000Eh
0x18001464d  mov     dword ptr [rsp+1B0h+hSection], 359h
0x180014655  mov     esi, ebx
0x180014657  mov     r9d, ebx
0x18001465a  jmp     loc_180014786
0x18001465f  mov     rdx, [rbp+0B0h+h]; h
0x180014663  mov     rcx, r15; hdc
0x180014666  call    cs:__imp_SelectObject
0x18001466c  mov     ecx, [rbp+0B0h+nDenominator]
0x18001466f  mov     rbx, rax
0x180014672  mov     r9d, [rbp+0B0h+nNumerator]; wDest
0x180014676  mov     eax, esi
0x180014678  sub     eax, ecx
0x18001467a  cdq
0x18001467b  idiv    edi
0x18001467d  mov     r8d, eax; yoriginDest
0x180014680  mov     eax, r14d
0x180014683  sub     eax, r9d
0x180014686  cdq
0x180014687  idiv    edi
0x180014689  mov     edx, eax; xoriginDest
0x18001468b  mov     eax, dword ptr [rsp+1B0h+ftn.BlendOp]
0x18001468f  mov     dword ptr [rsp+1B0h+lpbmi], eax; ftn
0x180014693  mov     dword ptr [rsp+1B0h+lpBits], ecx; hSrc
0x180014697  mov     [rsp+1B0h+SrcHeight], r9d; wSrc
0x18001469c  mov     [rsp+1B0h+SrcWidth], 0; yoriginSrc
0x1800146a4  mov     [rsp+1B0h+ySrc], 0; xoriginSrc
0x1800146ac  mov     qword ptr [rsp+1B0h+offset], r15; void *
0x1800146b1  mov     dword ptr [rsp+1B0h+hSection], ecx; hDest
0x1800146b5  mov     rcx, r12; hdcDest
0x1800146b8  call    cs:__imp_GdiAlphaBlend
0x1800146be  mov     rdx, rbx; h
0x1800146c1  mov     rcx, r15; hdc
0x1800146c4  call    cs:__imp_SelectObject
0x1800146ca  movzx   eax, [rbp+0B0h+var_AE]
0x1800146ce  mov     ecx, 8; this
0x1800146d3  imul    eax, esi
0x1800146d6  imul    eax, r14d
0x1800146da  cdq
0x1800146db  idiv    ecx
0x1800146dd  mov     ebx, eax
0x1800146df  test    eax, eax
0x1800146e1  jle     short loc_180014726
0x1800146e3  lea     r8, [rbp+0B0h+var_120]; struct CStandardData *
0x1800146e7  mov     edx, eax; unsigned int
0x1800146e9  call    ?LockExtraDataPointer@CApiPortClient@@QEAAJIPEAVCStandardData@@@Z; CApiPortClient::LockExtraDataPointer(uint,CStandardData *)
0x1800146ee  mov     esi, eax
0x1800146f0  test    eax, eax
0x1800146f2  js      short loc_180014771
0x1800146f4  mov     r9, qword ptr [rbp+0B0h+var_118+8]
0x1800146f8  lea     rdx, [rsp+1B0h+var_138]; struct tagSIZE *
0x1800146fd  mov     rcx, [rbp+0B0h+ho]; hbm
0x180014701  mov     r8d, ebx; int
0x180014704  mov     r9, [r9+18h]; void *
0x180014708  call    ?CopyBitmapHelper@@YAJPEAUHBITMAP__@@PEAUtagSIZE@@HPEAX@Z; CopyBitmapHelper(HBITMAP__ *,tagSIZE *,int,void *)
0x18001470d  mov     esi, eax
0x18001470f  test    eax, eax
0x180014711  jns     short loc_18001471D
0x180014713  mov     dword ptr [rsp+1B0h+hSection], 366h
0x18001471b  jmp     short loc_180014783
0x18001471d  mov     esi, [rsp+1B0h+var_138.cy]
0x180014721  mov     r14d, [rsp+1B0h+var_138.cx]
0x180014726  xor     eax, eax
0x180014728  mov     dword ptr [rbp+0B0h+h], 4000003Ah
0x18001472f  mov     [rbp+0B0h+var_F4], eax
0x180014732  lea     r9, [rbp+0B0h+var_120]; struct CExtraData *
0x180014736  mov     dword ptr [rsp+1B0h+ftn.BlendOp], eax
0x18001473a  lea     rdx, [rbp+0B0h+h]; void *
0x18001473e  xorps   xmm0, xmm0
0x180014741  lea     rax, [rsp+1B0h+ftn]
0x180014746  movups  xmmword ptr [rbp+0B0h+h+4], xmm0
0x18001474a  mov     r8d, 18h; unsigned __int64
0x180014750  mov     [rsp+1B0h+hSection], rax; int *
0x180014755  mov     [rbp+0B0h+h+4], r13
0x180014759  mov     dword ptr [rbp+0B0h+h+0Ch], r14d
0x18001475d  mov     [rbp+0B0h+var_F8], esi
0x180014760  call    ?SendRequestValidate@CApiPortClient@@QEAAJPEAX_KAEBVCExtraData@@PEAJ@Z; CApiPortClient::SendRequestValidate(void *,unsigned __int64,CExtraData const &,long *)
0x180014765  mov     esi, eax
0x180014767  test    eax, eax
0x180014769  js      short loc_18001477B
0x18001476b  mov     esi, dword ptr [rsp+1B0h+ftn.BlendOp]
0x18001476f  jmp     short loc_18001479A
0x180014771  mov     dword ptr [rsp+1B0h+hSection], 364h
0x180014779  jmp     short loc_180014783
0x18001477b  mov     dword ptr [rsp+1B0h+hSection], 371h; unsigned int
0x180014783  mov     r9d, eax; int
0x180014786  mov     r8d, edi; unsigned int
0x180014789  lea     rdx, qword_18001A170; int *
0x180014790  mov     ecx, 4; unsigned int
0x180014795  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18001479a  mov     r14, [rbp+0B0h+var_130]
0x18001479e  mov     rdx, r14; h
0x1800147a1  mov     rcx, r15; hdc
0x1800147a4  mov     ebx, esi
0x1800147a6  call    cs:__imp_SelectObject
0x1800147ac  mov     rcx, r12; hdc
0x1800147af  call    cs:__imp_DeleteDC
0x1800147b5  mov     rax, [rbp+0B0h+ho]
0x1800147b9  test    rax, rax
0x1800147bc  jz      short loc_1800147C7
0x1800147be  mov     rcx, rax; ho
0x1800147c1  call    cs:__imp_DeleteObject
0x1800147c7  test    r15, r15
0x1800147ca  jz      loc_18001485F
0x1800147d0  mov     rcx, r15; hdc
0x1800147d3  call    cs:__imp_DeleteDC
0x1800147d9  jmp     loc_18001485F
0x1800147de  mov     dword ptr [rsp+1B0h+hSection], 32Fh
0x1800147e6  mov     r8d, edi
0x1800147e9  jmp     short loc_180014845
0x1800147eb  movdqa  xmm0, cs:__xmm@00000000000000000000000040000055
0x1800147f3  lea     r9, [rsp+1B0h+ftn]; int *
0x1800147f8  movdqu  xmmword ptr [rbp+0B0h+h], xmm0
0x1800147fd  mov     r8d, 10h; unsigned __int64
0x180014803  mov     [rbp+0B0h+h+4], r13
0x180014807  lea     rdx, [rbp+0B0h+h]; void *
0x18001480b  mov     dword ptr [rbp+0B0h+h+0Ch], ebx
0x18001480e  mov     dword ptr [rsp+1B0h+ftn.BlendOp], r14d
0x180014813  call    ?SendRequestValidate@CApiPortClient@@QEAAJPEAX_KPEAJ@Z; CApiPortClient::SendRequestValidate(void *,unsigned __int64,long *)
0x180014818  mov     ebx, eax
0x18001481a  test    eax, eax
0x18001481c  js      short loc_180014824
0x18001481e  mov     ebx, dword ptr [rsp+1B0h+ftn.BlendOp]
0x180014822  jmp     short loc_18001485F
0x180014824  mov     dword ptr [rsp+1B0h+hSection], 37Ch
0x18001482c  mov     r9d, eax
0x18001482f  mov     r8d, 2
0x180014835  jmp     short loc_18001484E
0x180014837  mov     dword ptr [rsp+1B0h+hSection], 31Ah; unsigned int
0x18001483f  mov     r8d, 2; unsigned int
0x180014845  mov     r9d, 80070057h; int
0x18001484b  mov     ebx, r9d
0x18001484e  lea     rdx, qword_18001A170; int *
0x180014855  mov     ecx, 4; unsigned int
0x18001485a  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18001485f  test    cs:Microsoft_Windows_Dwm_ApiEnableBits, 1
0x180014866  jz      short loc_18001487A
0x180014868  mov     r9, r13
  ... truncated ...
```
