# ICImageDecompress

- ea: `0x1800060a0`
- end: `0x1800063ba`
- name: `ICImageDecompress`
- size: `794`
- prototype: `HANDLE __stdcall(HIC hic, UINT uiFlags, LPBITMAPINFO lpbiIn, LPVOID lpBits, LPBITMAPINFO lpbiOut)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002640`
- `0x180002770`
- `0x1800033e0`
- `0x180003a60`
- `0x1800060a0`
- `0x180006db0`
- `0x180006e04`
- `0x180016309`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000615d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180006270`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180006384`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18000615d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180006270`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180006384`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000624c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800062f7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180006360`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800063a6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18000624c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800062f7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180006360`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1800063a6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006243`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006259`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800062ee`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006300`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006357`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000636d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000639d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800063af`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006243`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006259`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800062ee`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006300`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006357`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000636d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000639d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800063af`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180006267`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18000637b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180006267`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18000637b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006309`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180006309`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006154`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180006154`

## pseudocode

```c
HANDLE __stdcall ICImageDecompress(HIC hic, UINT uiFlags, LPBITMAPINFO lpbiIn, LPVOID lpBits, LPBITMAPINFO lpbiOut)
{
  LPBITMAPINFO v5; // rbx
  HIC v8; // rsi
  int v9; // r12d
  int v10; // ecx
  HGLOBAL v11; // rax
  struct tagBITMAPINFOHEADER *v12; // rax
  struct tagBITMAPINFOHEADER *v13; // rdi
  bool v14; // zf
  __int64 biHeight; // rcx
  unsigned __int64 v16; // rcx
  WORD biBitCount; // cx
  int biClrUsed; // ebp
  HGLOBAL v19; // rax
  unsigned int v20; // ebx
  HGLOBAL v21; // rax
  HGLOBAL v22; // rax
  struct tagBITMAPINFOHEADER *v23; // rax
  HGLOBAL v24; // rax
  HGLOBAL v25; // rax
  HGLOBAL v27; // rax
  unsigned int v28; // ebx
  HGLOBAL v29; // rax
  HGLOBAL v30; // rax
  const void *v31; // rbx
  HGLOBAL v32; // rax
  SIZE_T dwBytes; // [rsp+60h] [rbp+8h] BYREF

  v5 = lpbiOut;
  v8 = hic;
  if ( hic )
  {
    v9 = 0;
  }
  else
  {
    v9 = 1;
    v8 = ICLocate(0x63646976u, 0, &lpbiIn->bmiHeader, &lpbiOut->bmiHeader, 2u);
    if ( !v8 )
      return 0;
  }
  if ( ICSendMessage(v8, 0x400Bu, (DWORD_PTR)lpbiIn, 0) )
    goto LABEL_33;
  if ( v5 )
  {
    v10 = v5->bmiHeader.biSize + 1024;
    if ( v10 < v5->bmiHeader.biSize )
      goto LABEL_33;
  }
  else
  {
    v10 = ICSendMessage(v8, 0x400Au, (DWORD_PTR)lpbiIn, 0);
    if ( v10 <= 0 )
      goto LABEL_33;
  }
  v11 = GlobalAlloc(0x42u, v10);
  v12 = (struct tagBITMAPINFOHEADER *)GlobalLock(v11);
  v13 = v12;
  if ( !v12 )
  {
LABEL_33:
    if ( v9 )
      ICClose(v8);
    return 0;
  }
  if ( v5 )
    memmove_0(v12, v5, v5->bmiHeader.biSize + 4LL * v5->bmiHeader.biClrUsed);
  else
    ICSendMessage(v8, 0x400Au, (DWORD_PTR)lpbiIn, (DWORD_PTR)v12);
  if ( v13->biBitCount <= 8u )
    ICSendMessage(v8, 0x401Eu, (DWORD_PTR)lpbiIn, (DWORD_PTR)v13);
  v14 = v13->biHeight == 0x80000000;
  LODWORD(dwBytes) = 0;
  if ( v14 || (int)SAFE_DIBWIDTHBYTES(v13, &dwBytes) < 0 )
    goto LABEL_32;
  biHeight = (unsigned int)-v13->biHeight;
  if ( v13->biHeight > 0 )
    biHeight = (unsigned int)v13->biHeight;
  v16 = (unsigned int)dwBytes * biHeight;
  if ( v16 > 0xFFFFFFFF )
    goto LABEL_32;
  v14 = v13->biClrUsed == 0;
  v13->biSizeImage = v16;
  if ( v14 && (biBitCount = v13->biBitCount, (unsigned __int16)(biBitCount - 1) <= 7u) )
    biClrUsed = 1 << biBitCount;
  else
    biClrUsed = v13->biClrUsed;
  v13->biClrUsed = biClrUsed;
  LODWORD(dwBytes) = 0;
  if ( (int)SafeDibSize(v13, &dwBytes) < 0 )
    goto LABEL_32;
  v19 = GlobalHandle(v13);
  GlobalUnlock(v19);
  v20 = dwBytes;
  v21 = GlobalHandle(v13);
  v22 = GlobalReAlloc(v21, v20, 0);
  v23 = (struct tagBITMAPINFOHEADER *)GlobalLock(v22);
  v13 = v23;
  if ( !v23 )
    goto LABEL_33;
  if ( ICSendMessage(v8, 0x400Cu, (DWORD_PTR)lpbiIn, (DWORD_PTR)v23) )
  {
LABEL_32:
    v24 = GlobalHandle(v13);
    GlobalUnlock(v24);
    v25 = GlobalHandle(v13);
    GlobalFree(v25);
    goto LABEL_33;
  }
  if ( !lpBits )
    lpBits = (char *)&lpbiIn->bmiHeader.biSize + 4 * lpbiIn->bmiHeader.biClrUsed + lpbiIn->bmiHeader.biSize;
  if ( (ICDecompress(v8, 0, &lpbiIn->bmiHeader, lpBits, v13, (char *)&v13->biSize + 4 * v13->biClrUsed + v13->biSize)
      & 0x80000000) != 0 )
  {
    ICSendMessage(v8, 0x400Eu, 0, 0);
    goto LABEL_32;
  }
  if ( ICSendMessage(v8, 0x400Eu, 0, 0) )
    goto LABEL_32;
  LODWORD(dwBytes) = 0;
  if ( (int)SafeDibSize(v13, &dwBytes) < 0 )
    goto LABEL_32;
  v27 = GlobalHandle(v13);
  GlobalUnlock(v27);
  v28 = dwBytes;
  v29 = GlobalHandle(v13);
  v30 = GlobalReAlloc(v29, v28, 0);
  v31 = GlobalLock(v30);
  if ( v9 )
    ICClose(v8);
  v32 = GlobalHandle(v31);
  GlobalUnlock(v32);
  return GlobalHandle(v31);
}

```

## disassembly

```asm
0x1800060a0  mov     [rsp+arg_8], rbx
0x1800060a5  mov     [rsp+arg_10], rbp
0x1800060aa  push    rsi
0x1800060ab  push    rdi
0x1800060ac  push    r12
0x1800060ae  push    r14
0x1800060b0  push    r15
0x1800060b2  sub     rsp, 30h
0x1800060b6  mov     rbx, [rsp+58h+lpbiOut]
0x1800060be  mov     r15, r9
0x1800060c1  mov     r14, r8
0x1800060c4  mov     rsi, rcx
0x1800060c7  mov     ebp, 1
0x1800060cc  test    rcx, rcx
0x1800060cf  jnz     short loc_1800060F8
0x1800060d1  mov     r9, rbx; lpbiOut
0x1800060d4  mov     [rsp+58h+wFlags], 2; wFlags
0x1800060db  xor     edx, edx; fccHandler
0x1800060dd  mov     ecx, 63646976h; fccType
0x1800060e2  mov     r12d, ebp
0x1800060e5  call    ICLocate
0x1800060ea  mov     rsi, rax
0x1800060ed  test    rax, rax
0x1800060f0  jz      loc_18000631C
0x1800060f6  jmp     short loc_1800060FB
0x1800060f8  xor     r12d, r12d
0x1800060fb  xor     r9d, r9d; dw2
0x1800060fe  mov     r8, r14; dw1
0x180006101  mov     edx, 400Bh; msg
0x180006106  mov     rcx, rsi; hic
0x180006109  call    ICSendMessage
0x18000610e  test    rax, rax
0x180006111  jnz     loc_18000630F
0x180006117  test    rbx, rbx
0x18000611a  jz      short loc_18000612E
0x18000611c  mov     eax, [rbx]
0x18000611e  lea     ecx, [rax+400h]
0x180006124  cmp     ecx, eax
0x180006126  jb      loc_18000630F
0x18000612c  jmp     short loc_18000614C
0x18000612e  xor     r9d, r9d; dw2
0x180006131  mov     r8, r14; dw1
0x180006134  mov     edx, 400Ah; msg
0x180006139  mov     rcx, rsi; hic
0x18000613c  call    ICSendMessage
0x180006141  mov     rcx, rax
0x180006144  test    eax, eax
0x180006146  jle     loc_18000630F
0x18000614c  movsxd  rdx, ecx; dwBytes
0x18000614f  mov     ecx, 42h ; 'B'; uFlags
0x180006154  call    cs:__imp_GlobalAlloc
0x18000615a  mov     rcx, rax; hMem
0x18000615d  call    cs:__imp_GlobalLock
0x180006163  mov     rdi, rax
0x180006166  test    rax, rax
0x180006169  jz      loc_18000630F
0x18000616f  test    rbx, rbx
0x180006172  jnz     short loc_180006189
0x180006174  mov     r9, rax; dw2
0x180006177  mov     r8, r14; dw1
0x18000617a  mov     edx, 400Ah; msg
0x18000617f  mov     rcx, rsi; hic
0x180006182  call    ICSendMessage
0x180006187  jmp     short loc_18000619D
0x180006189  mov     ecx, [rbx+20h]
0x18000618c  mov     rdx, rbx; Src
0x18000618f  mov     eax, [rbx]
0x180006191  lea     r8, [rax+rcx*4]; Size
0x180006195  mov     rcx, rdi; void *
0x180006198  call    memmove_0
0x18000619d  cmp     word ptr [rdi+0Eh], 8
0x1800061a2  ja      short loc_1800061B7
0x1800061a4  mov     r9, rdi; dw2
0x1800061a7  mov     r8, r14; dw1
0x1800061aa  mov     edx, 401Eh; msg
0x1800061af  mov     rcx, rsi; hic
0x1800061b2  call    ICSendMessage
0x1800061b7  cmp     dword ptr [rdi+8], 80000000h
0x1800061be  mov     dword ptr [rsp+58h+dwBytes], 0
0x1800061c6  jz      loc_1800062EB
0x1800061cc  lea     rdx, [rsp+58h+dwBytes]
0x1800061d1  mov     rcx, rdi
0x1800061d4  call    SAFE_DIBWIDTHBYTES
0x1800061d9  test    eax, eax
0x1800061db  js      loc_1800062EB
0x1800061e1  mov     ecx, [rdi+8]
0x1800061e4  mov     eax, dword ptr [rsp+58h+dwBytes]
0x1800061e8  neg     ecx
0x1800061ea  cmovs   ecx, [rdi+8]
0x1800061ee  imul    rcx, rax
0x1800061f2  mov     eax, 0FFFFFFFFh
0x1800061f7  cmp     rcx, rax
0x1800061fa  ja      loc_1800062EB
0x180006200  cmp     dword ptr [rdi+20h], 0
0x180006204  mov     [rdi+14h], ecx
0x180006207  jnz     short loc_18000621D
0x180006209  movzx   ecx, word ptr [rdi+0Eh]
0x18000620d  movzx   eax, cx
0x180006210  sub     ax, bp
0x180006213  cmp     ax, 7
0x180006217  ja      short loc_18000621D
0x180006219  shl     ebp, cl
0x18000621b  jmp     short loc_180006220
0x18000621d  mov     ebp, [rdi+20h]
0x180006220  lea     rdx, [rsp+58h+dwBytes]
0x180006225  mov     [rdi+20h], ebp
0x180006228  mov     rcx, rdi
0x18000622b  mov     dword ptr [rsp+58h+dwBytes], 0
0x180006233  call    SafeDibSize
0x180006238  test    eax, eax
0x18000623a  js      loc_1800062EB
0x180006240  mov     rcx, rdi; pMem
0x180006243  call    cs:__imp_GlobalHandle
0x180006249  mov     rcx, rax; hMem
0x18000624c  call    cs:__imp_GlobalUnlock
0x180006252  mov     ebx, dword ptr [rsp+58h+dwBytes]
0x180006256  mov     rcx, rdi; pMem
0x180006259  call    cs:__imp_GlobalHandle
0x18000625f  xor     r8d, r8d; uFlags
0x180006262  mov     edx, ebx; dwBytes
0x180006264  mov     rcx, rax; hMem
0x180006267  call    cs:__imp_GlobalReAlloc
0x18000626d  mov     rcx, rax; hMem
0x180006270  call    cs:__imp_GlobalLock
0x180006276  mov     rdi, rax
0x180006279  test    rax, rax
0x18000627c  jz      loc_18000630F
0x180006282  mov     r9, rax; dw2
0x180006285  mov     r8, r14; dw1
0x180006288  mov     edx, 400Ch; msg
0x18000628d  mov     rcx, rsi; hic
0x180006290  call    ICSendMessage
0x180006295  test    rax, rax
0x180006298  jnz     short loc_1800062EB
0x18000629a  test    r15, r15
0x18000629d  jnz     short loc_1800062AD
0x18000629f  movsxd  rcx, dword ptr [r14]
0x1800062a2  mov     edx, [r14+20h]
0x1800062a6  add     rcx, r14
0x1800062a9  lea     r15, [rcx+rdx*4]
0x1800062ad  mov     edx, [rdi+20h]
0x1800062b0  mov     r9, r15; lpData
0x1800062b3  movsxd  rcx, dword ptr [rdi]
0x1800062b6  mov     r8, r14; lpbiFormat
0x1800062b9  add     rcx, rdi
0x1800062bc  lea     rax, [rcx+rdx*4]
0x1800062c0  xor     edx, edx; dwFlags
0x1800062c2  mov     [rsp+58h+lpBits], rax; lpBits
0x1800062c7  mov     rcx, rsi; hic
0x1800062ca  mov     qword ptr [rsp+58h+wFlags], rdi; lpbi
0x1800062cf  call    ICDecompress
0x1800062d4  xor     r9d, r9d; dw2
0x1800062d7  xor     r8d, r8d; dw1
0x1800062da  mov     edx, 400Eh; msg
0x1800062df  mov     rcx, rsi; hic
0x1800062e2  test    eax, eax
0x1800062e4  jns     short loc_180006335
0x1800062e6  call    ICSendMessage
0x1800062eb  mov     rcx, rdi; pMem
0x1800062ee  call    cs:__imp_GlobalHandle
0x1800062f4  mov     rcx, rax; hMem
0x1800062f7  call    cs:__imp_GlobalUnlock
0x1800062fd  mov     rcx, rdi; pMem
0x180006300  call    cs:__imp_GlobalHandle
0x180006306  mov     rcx, rax; hMem
0x180006309  call    cs:__imp_GlobalFree
0x18000630f  test    r12d, r12d
0x180006312  jz      short loc_18000631C
0x180006314  mov     rcx, rsi; hic
0x180006317  call    ICClose
0x18000631c  xor     eax, eax
0x18000631e  mov     rbx, [rsp+58h+arg_8]
0x180006323  mov     rbp, [rsp+58h+arg_10]
0x180006328  add     rsp, 30h
0x18000632c  pop     r15
0x18000632e  pop     r14
0x180006330  pop     r12
0x180006332  pop     rdi
0x180006333  pop     rsi
0x180006334  retn
0x180006335  call    ICSendMessage
0x18000633a  test    rax, rax
0x18000633d  jnz     short loc_1800062EB
0x18000633f  lea     rdx, [rsp+58h+dwBytes]
0x180006344  mov     dword ptr [rsp+58h+dwBytes], eax
0x180006348  mov     rcx, rdi
0x18000634b  call    SafeDibSize
0x180006350  test    eax, eax
0x180006352  js      short loc_1800062EB
0x180006354  mov     rcx, rdi; pMem
0x180006357  call    cs:__imp_GlobalHandle
0x18000635d  mov     rcx, rax; hMem
0x180006360  call    cs:__imp_GlobalUnlock
0x180006366  mov     ebx, dword ptr [rsp+58h+dwBytes]
0x18000636a  mov     rcx, rdi; pMem
0x18000636d  call    cs:__imp_GlobalHandle
0x180006373  xor     r8d, r8d; uFlags
0x180006376  mov     edx, ebx; dwBytes
0x180006378  mov     rcx, rax; hMem
0x18000637b  call    cs:__imp_GlobalReAlloc
0x180006381  mov     rcx, rax; hMem
0x180006384  call    cs:__imp_GlobalLock
0x18000638a  mov     rbx, rax
0x18000638d  test    r12d, r12d
0x180006390  jz      short loc_18000639A
0x180006392  mov     rcx, rsi; hic
0x180006395  call    ICClose
0x18000639a  mov     rcx, rbx; pMem
0x18000639d  call    cs:__imp_GlobalHandle
0x1800063a3  mov     rcx, rax; hMem
0x1800063a6  call    cs:__imp_GlobalUnlock
0x1800063ac  mov     rcx, rbx; pMem
0x1800063af  call    cs:__imp_GlobalHandle
0x1800063b5  jmp     loc_18000631E
```
