# ICSeqCompressFrameStart

- ea: `0x1800065e0`
- end: `0x1800068b3`
- name: `ICSeqCompressFrameStart`
- size: `723`
- prototype: `BOOL __stdcall(PCOMPVARS pc, LPBITMAPINFO lpbiIn)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800014b0`
- `0x180001d62`
- `0x180002df0`
- `0x180003a60`
- `0x1800065e0`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800066fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800067b4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180006809`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800066fa`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800067b4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180006809`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000666a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180006867`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000666a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180006867`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006661`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006674`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000685e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006871`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006661`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006674`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000685e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006871`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000667d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000687a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000667d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000687a`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800066f1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800067ab`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006800`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800066f1`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800067ab`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006800`

## pseudocode

```c
BOOL __stdcall ICSeqCompressFrameStart(PCOMPVARS pc, LPBITMAPINFO lpbiIn)
{
  HIC hic; // rcx
  LPBITMAPINFO lpbiOut; // rcx
  HGLOBAL v6; // rax
  HGLOBAL v7; // rax
  unsigned int v8; // eax
  HGLOBAL v9; // rax
  struct tagBITMAPINFO *v10; // rax
  LPBITMAPINFO v11; // rbx
  LPBITMAPINFO v12; // r8
  int biClrUsed; // edx
  WORD biBitCount; // cx
  LPBITMAPINFO v15; // r9
  HIC v16; // rcx
  DWORD biSizeImage; // ecx
  HGLOBAL v18; // rax
  void *v19; // rax
  HGLOBAL v20; // rax
  void *v21; // rax
  const void *lpBitsPrev; // rcx
  HGLOBAL v23; // rax
  HGLOBAL v24; // rax
  ICINFO picinfo; // [rsp+20h] [rbp-268h] BYREF

  memset_0(&picinfo, 0, sizeof(picinfo));
  if ( !pc )
    return 0;
  if ( pc->cbSize != 96 )
    return 0;
  hic = pc->hic;
  if ( !hic || !lpbiIn )
    return 0;
  if ( ICSendMessage(hic, 0x4006u, (DWORD_PTR)lpbiIn, (DWORD_PTR)pc->lpbiOut) )
  {
    lpbiOut = pc->lpbiOut;
    if ( lpbiOut )
    {
      v6 = GlobalHandle(lpbiOut);
      GlobalUnlock(v6);
      v7 = GlobalHandle(pc->lpbiOut);
      GlobalFree(v7);
      pc->lpbiOut = 0;
    }
  }
  if ( pc->lKey < 0 )
    pc->lKey = 1;
  if ( pc->lQ == -1 )
  {
    ICSendMessage(pc->hic, 0x501Eu, (DWORD_PTR)&dw1, 4u);
    pc->lQ = dw1;
  }
  if ( !pc->lpbiOut )
  {
    v8 = ICSendMessage(pc->hic, 0x4004u, (DWORD_PTR)lpbiIn, 0);
    if ( v8 )
    {
      v9 = GlobalAlloc(2u, v8);
      v10 = (struct tagBITMAPINFO *)GlobalLock(v9);
      pc->lpbiOut = v10;
      if ( v10 )
      {
        ICSendMessage(pc->hic, 0x4004u, (DWORD_PTR)lpbiIn, (DWORD_PTR)v10);
        goto LABEL_16;
      }
    }
    return 0;
  }
LABEL_16:
  v11 = pc->lpbiOut;
  v11->bmiHeader.biSizeImage = ICSendMessage(pc->hic, 0x4005u, (DWORD_PTR)lpbiIn, (DWORD_PTR)v11);
  v12 = pc->lpbiOut;
  biClrUsed = v12->bmiHeader.biClrUsed;
  if ( !biClrUsed )
  {
    biBitCount = v12->bmiHeader.biBitCount;
    if ( (unsigned __int16)(biBitCount - 1) <= 7u )
      biClrUsed = 1 << biBitCount;
  }
  v12->bmiHeader.biClrUsed = biClrUsed;
  v15 = pc->lpbiOut;
  v16 = pc->hic;
  pc->lKeyCount = pc->lKey;
  pc->lpbiIn = lpbiIn;
  pc->lFrame = 0;
  if ( ICSendMessage(v16, 0x4006u, (DWORD_PTR)lpbiIn, (DWORD_PTR)v15) )
    return 0;
  biSizeImage = pc->lpbiOut->bmiHeader.biSizeImage;
  if ( biSizeImage + 2064 < biSizeImage )
    return 0;
  v18 = GlobalAlloc(2u, biSizeImage + 2064);
  v19 = GlobalLock(v18);
  pc->lpBitsOut = v19;
  if ( !v19 )
    return 0;
  if ( ICGetInfo(pc->hic, &picinfo, 0x238u) <= 0 )
    return 0;
  if ( pc->lKey != 1 && (picinfo.dwFlags & 4) != 0 && (picinfo.dwFlags & 0x20) == 0 )
  {
    v20 = GlobalAlloc(2u, lpbiIn->bmiHeader.biSizeImage);
    v21 = GlobalLock(v20);
    pc->lpBitsPrev = v21;
    if ( !v21 )
      return 0;
  }
  if ( ICSendMessage(pc->hic, 0x4007u, (DWORD_PTR)lpbiIn, (DWORD_PTR)pc->lpbiOut) )
    return 0;
  if ( pc->lpBitsPrev )
  {
    if ( ICSendMessage(pc->hic, 0x400Cu, (DWORD_PTR)pc->lpbiOut, (DWORD_PTR)lpbiIn) )
    {
      lpBitsPrev = pc->lpBitsPrev;
      pc->lKeyCount = 1;
      pc->lKey = 1;
      v23 = GlobalHandle(lpBitsPrev);
      GlobalUnlock(v23);
      v24 = GlobalHandle(pc->lpBitsPrev);
      GlobalFree(v24);
      pc->lpBitsPrev = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800065e0  mov     [rsp+arg_10], rbx
0x1800065e5  push    rsi
0x1800065e6  push    rdi
0x1800065e7  push    r14
0x1800065e9  sub     rsp, 270h
0x1800065f0  mov     rax, cs:__security_cookie
0x1800065f7  xor     rax, rsp
0x1800065fa  mov     [rsp+288h+var_28], rax
0x180006602  mov     rsi, rdx
0x180006605  mov     rdi, rcx
0x180006608  xor     edx, edx; Val
0x18000660a  lea     rcx, [rsp+288h+picinfo]; void *
0x18000660f  mov     r8d, 238h; Size
0x180006615  call    memset_0
0x18000661a  test    rdi, rdi
0x18000661d  jz      loc_18000688D
0x180006623  cmp     dword ptr [rdi], 60h ; '`'
0x180006626  jnz     loc_18000688D
0x18000662c  mov     rcx, [rdi+8]; hic
0x180006630  test    rcx, rcx
0x180006633  jz      loc_18000688D
0x180006639  test    rsi, rsi
0x18000663c  jz      loc_18000688D
0x180006642  mov     r9, [rdi+20h]; dw2
0x180006646  mov     r8, rsi; dw1
0x180006649  mov     edx, 4006h; msg
0x18000664e  call    ICSendMessage
0x180006653  test    rax, rax
0x180006656  jz      short loc_18000668B
0x180006658  mov     rcx, [rdi+20h]; pMem
0x18000665c  test    rcx, rcx
0x18000665f  jz      short loc_18000668B
0x180006661  call    cs:__imp_GlobalHandle
0x180006667  mov     rcx, rax; hMem
0x18000666a  call    cs:__imp_GlobalUnlock
0x180006670  mov     rcx, [rdi+20h]; pMem
0x180006674  call    cs:__imp_GlobalHandle
0x18000667a  mov     rcx, rax; hMem
0x18000667d  call    cs:__imp_GlobalFree
0x180006683  mov     qword ptr [rdi+20h], 0
0x18000668b  cmp     dword ptr [rdi+3Ch], 0
0x18000668f  mov     r14d, 1
0x180006695  jge     short loc_18000669B
0x180006697  mov     [rdi+3Ch], r14d
0x18000669b  cmp     dword ptr [rdi+44h], 0FFFFFFFFh
0x18000669f  jnz     short loc_1800066C5
0x1800066a1  mov     rcx, [rdi+8]; hic
0x1800066a5  lea     r8, dw1; dw1
0x1800066ac  mov     r9d, 4; dw2
0x1800066b2  mov     edx, 501Eh; msg
0x1800066b7  call    ICSendMessage
0x1800066bc  mov     eax, cs:dw1
0x1800066c2  mov     [rdi+44h], eax
0x1800066c5  cmp     qword ptr [rdi+20h], 0
0x1800066ca  jnz     short loc_18000671E
0x1800066cc  mov     rcx, [rdi+8]; hic
0x1800066d0  mov     ebx, 4004h
0x1800066d5  mov     edx, ebx; msg
0x1800066d7  xor     r9d, r9d; dw2
0x1800066da  mov     r8, rsi; dw1
0x1800066dd  call    ICSendMessage
0x1800066e2  test    eax, eax
0x1800066e4  jz      loc_18000688D
0x1800066ea  mov     edx, eax; dwBytes
0x1800066ec  mov     ecx, 2; uFlags
0x1800066f1  call    cs:__imp_GlobalAlloc
0x1800066f7  mov     rcx, rax; hMem
0x1800066fa  call    cs:__imp_GlobalLock
0x180006700  mov     [rdi+20h], rax
0x180006704  test    rax, rax
0x180006707  jz      loc_18000688D
0x18000670d  mov     rcx, [rdi+8]; hic
0x180006711  mov     r9, rax; dw2
0x180006714  mov     r8, rsi; dw1
0x180006717  mov     edx, ebx; msg
0x180006719  call    ICSendMessage
0x18000671e  mov     rbx, [rdi+20h]
0x180006722  mov     r8, rsi; dw1
0x180006725  mov     rcx, [rdi+8]; hic
0x180006729  mov     r9, rbx; dw2
0x18000672c  mov     edx, 4005h; msg
0x180006731  call    ICSendMessage
0x180006736  mov     [rbx+14h], eax
0x180006739  mov     r8, [rdi+20h]
0x18000673d  mov     edx, [r8+20h]
0x180006741  test    edx, edx
0x180006743  jnz     short loc_18000675C
0x180006745  movzx   ecx, word ptr [r8+0Eh]
0x18000674a  movzx   eax, cx
0x18000674d  sub     ax, r14w
0x180006751  cmp     ax, 7
0x180006755  ja      short loc_18000675C
0x180006757  mov     edx, r14d
0x18000675a  shl     edx, cl
0x18000675c  mov     [r8+20h], edx
0x180006760  mov     r8, rsi; dw1
0x180006763  mov     eax, [rdi+3Ch]
0x180006766  mov     edx, 4006h; msg
0x18000676b  mov     r9, [rdi+20h]; dw2
0x18000676f  mov     rcx, [rdi+8]; hic
0x180006773  mov     [rdi+48h], eax
0x180006776  mov     [rdi+18h], rsi
0x18000677a  mov     dword ptr [rdi+38h], 0
0x180006781  call    ICSendMessage
0x180006786  test    rax, rax
0x180006789  jnz     loc_18000688D
0x18000678f  mov     rax, [rdi+20h]
0x180006793  mov     ecx, [rax+14h]
0x180006796  lea     eax, [rcx+810h]
0x18000679c  cmp     eax, ecx
0x18000679e  jb      loc_18000688D
0x1800067a4  mov     edx, eax; dwBytes
0x1800067a6  mov     ecx, 2; uFlags
0x1800067ab  call    cs:__imp_GlobalAlloc
0x1800067b1  mov     rcx, rax; hMem
0x1800067b4  call    cs:__imp_GlobalLock
0x1800067ba  mov     [rdi+28h], rax
0x1800067be  test    rax, rax
0x1800067c1  jz      loc_18000688D
0x1800067c7  mov     rcx, [rdi+8]; hic
0x1800067cb  lea     rdx, [rsp+288h+picinfo]; picinfo
0x1800067d0  mov     r8d, 238h; cb
0x1800067d6  call    ICGetInfo
0x1800067db  test    rax, rax
0x1800067de  jle     loc_18000688D
0x1800067e4  cmp     [rdi+3Ch], r14d
0x1800067e8  jz      short loc_180006818
0x1800067ea  test    byte ptr [rsp+288h+picinfo.dwFlags], 4
0x1800067ef  jz      short loc_180006818
0x1800067f1  test    byte ptr [rsp+288h+picinfo.dwFlags], 20h
0x1800067f6  jnz     short loc_180006818
0x1800067f8  mov     edx, [rsi+14h]; dwBytes
0x1800067fb  mov     ecx, 2; uFlags
0x180006800  call    cs:__imp_GlobalAlloc
0x180006806  mov     rcx, rax; hMem
0x180006809  call    cs:__imp_GlobalLock
0x18000680f  mov     [rdi+30h], rax
0x180006813  test    rax, rax
0x180006816  jz      short loc_18000688D
0x180006818  mov     r9, [rdi+20h]; dw2
0x18000681c  mov     r8, rsi; dw1
0x18000681f  mov     rcx, [rdi+8]; hic
0x180006823  mov     edx, 4007h; msg
0x180006828  call    ICSendMessage
0x18000682d  test    rax, rax
0x180006830  jnz     short loc_18000688D
0x180006832  cmp     [rdi+30h], rax
0x180006836  jz      short loc_180006888
0x180006838  mov     r8, [rdi+20h]; dw1
0x18000683c  mov     r9, rsi; dw2
0x18000683f  mov     rcx, [rdi+8]; hic
0x180006843  mov     edx, 400Ch; msg
0x180006848  call    ICSendMessage
0x18000684d  test    rax, rax
0x180006850  jz      short loc_180006888
0x180006852  mov     rcx, [rdi+30h]; pMem
0x180006856  mov     [rdi+48h], r14d
0x18000685a  mov     [rdi+3Ch], r14d
0x18000685e  call    cs:__imp_GlobalHandle
0x180006864  mov     rcx, rax; hMem
0x180006867  call    cs:__imp_GlobalUnlock
0x18000686d  mov     rcx, [rdi+30h]; pMem
0x180006871  call    cs:__imp_GlobalHandle
0x180006877  mov     rcx, rax; hMem
0x18000687a  call    cs:__imp_GlobalFree
0x180006880  mov     qword ptr [rdi+30h], 0
0x180006888  mov     eax, r14d
0x18000688b  jmp     short loc_18000688F
0x18000688d  xor     eax, eax
0x18000688f  mov     rcx, [rsp+288h+var_28]
0x180006897  xor     rcx, rsp; StackCookie
0x18000689a  call    __security_check_cookie
0x18000689f  mov     rbx, [rsp+288h+arg_10]
0x1800068a7  add     rsp, 270h
0x1800068ae  pop     r14
0x1800068b0  pop     rdi
0x1800068b1  pop     rsi
0x1800068b2  retn
```
