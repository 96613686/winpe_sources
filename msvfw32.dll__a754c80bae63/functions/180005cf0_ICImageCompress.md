# ICImageCompress

- ea: `0x180005cf0`
- end: `0x18000608d`
- name: `ICImageCompress`
- size: `925`
- prototype: `HANDLE __stdcall(HIC hic, UINT uiFlags, LPBITMAPINFO lpbiIn, LPVOID lpBits, LPBITMAPINFO lpbiOut, LONG lQuality, LONG *plSize)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800068bc`

## callees

- `0x180002640`
- `0x1800026e0`
- `0x1800033e0`
- `0x180003a60`
- `0x180005cf0`
- `0x180006e04`
- `0x180016309`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180005ddd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180005ebe`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180006057`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180005ddd`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180005ebe`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180006057`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005e97`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005fa7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180006030`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180006079`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005e97`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180005fa7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180006030`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180006079`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005e8e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005ea7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005f9e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005fb0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006027`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006040`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006070`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006082`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005e8e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005ea7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005f9e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180005fb0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006027`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006040`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006070`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180006082`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180005eb5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18000604e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180005eb5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x18000604e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005fb9`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180005fb9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180005dd4`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180005dd4`

## pseudocode

```c
HANDLE __stdcall ICImageCompress(
        HIC hic,
        UINT uiFlags,
        LPBITMAPINFO lpbiIn,
        LPVOID lpBits,
        LPBITMAPINFO lpbiOut,
        LONG lQuality,
        LONG *plSize)
{
  LONG *v7; // r15
  HIC v10; // rsi
  int v11; // r12d
  signed int v12; // ecx
  HGLOBAL v13; // rax
  struct tagBITMAPINFOHEADER *v14; // rdi
  WORD biBitCount; // cx
  int biClrUsed; // ebp
  HGLOBAL v17; // rax
  unsigned int v18; // ebx
  HGLOBAL v19; // rax
  HGLOBAL v20; // rax
  struct tagBITMAPINFOHEADER *v21; // rax
  LONG dwQuality; // r8d
  HGLOBAL v23; // rax
  HGLOBAL v24; // rax
  HGLOBAL v26; // rax
  unsigned int v27; // ebx
  HGLOBAL v28; // rax
  HGLOBAL v29; // rax
  const void *v30; // rbx
  HGLOBAL v31; // rax
  DWORD dwFlags; // [rsp+70h] [rbp-58h] BYREF
  DWORD ckid[21]; // [rsp+74h] [rbp-54h] BYREF
  LONG dwFrameSize; // [rsp+D0h] [rbp+8h]

  v7 = plSize;
  dwFlags = 0;
  ckid[0] = 0;
  v10 = hic;
  if ( plSize )
    dwFrameSize = *plSize;
  else
    dwFrameSize = 0;
  if ( hic )
  {
    v11 = 0;
  }
  else
  {
    v11 = 1;
    v10 = ICLocate(0x63646976u, 0, &lpbiIn->bmiHeader, &lpbiOut->bmiHeader, 1u);
    if ( !v10 )
      return 0;
  }
  if ( ICSendMessage(v10, 0x4006u, (DWORD_PTR)lpbiIn, 0) )
    goto LABEL_32;
  if ( lpbiOut )
  {
    v12 = lpbiOut->bmiHeader.biSize + 1024;
    if ( v12 < lpbiOut->bmiHeader.biSize )
      goto LABEL_32;
  }
  else
  {
    v12 = ICSendMessage(v10, 0x4004u, (DWORD_PTR)lpbiIn, 0);
    if ( v12 <= 0 )
      goto LABEL_32;
  }
  v13 = GlobalAlloc(0x42u, v12);
  v14 = (struct tagBITMAPINFOHEADER *)GlobalLock(v13);
  if ( !v14 )
  {
LABEL_32:
    if ( v11 )
      ICClose(v10);
    return 0;
  }
  if ( !lpbiOut || ICSendMessage(v10, 0x4006u, (DWORD_PTR)lpbiIn, (DWORD_PTR)lpbiOut) )
    ICSendMessage(v10, 0x4004u, (DWORD_PTR)lpbiIn, (DWORD_PTR)v14);
  else
    memmove_0(v14, lpbiOut, lpbiOut->bmiHeader.biSize + 4LL * lpbiOut->bmiHeader.biClrUsed);
  v14->biSizeImage = ICSendMessage(v10, 0x4005u, (DWORD_PTR)lpbiIn, (DWORD_PTR)v14);
  if ( v14->biClrUsed || (biBitCount = v14->biBitCount, (unsigned __int16)(biBitCount - 1) > 7u) )
    biClrUsed = v14->biClrUsed;
  else
    biClrUsed = 1 << biBitCount;
  v14->biClrUsed = biClrUsed;
  LODWORD(plSize) = 0;
  if ( (int)SafeDibSize(v14, &plSize) < 0 )
    goto LABEL_31;
  v17 = GlobalHandle(v14);
  GlobalUnlock(v17);
  v18 = (unsigned int)plSize;
  v19 = GlobalHandle(v14);
  v20 = GlobalReAlloc(v19, v18, 0);
  v21 = (struct tagBITMAPINFOHEADER *)GlobalLock(v20);
  v14 = v21;
  if ( !v21 )
    goto LABEL_32;
  if ( ICSendMessage(v10, 0x4007u, (DWORD_PTR)lpbiIn, (DWORD_PTR)v21) )
  {
LABEL_31:
    v23 = GlobalHandle(v14);
    GlobalUnlock(v23);
    v24 = GlobalHandle(v14);
    GlobalFree(v24);
    goto LABEL_32;
  }
  if ( !lpBits )
    lpBits = (char *)&lpbiIn->bmiHeader.biSize + 4 * lpbiIn->bmiHeader.biClrUsed + lpbiIn->bmiHeader.biSize;
  dwQuality = lQuality;
  if ( lQuality == -1 )
  {
    ICSendMessage(v10, 0x501Eu, (DWORD_PTR)&dw1, 4u);
    dwQuality = dw1;
  }
  if ( (ICCompress(
          v10,
          0,
          v14,
          (char *)&v14->biSize + 4 * v14->biClrUsed + v14->biSize,
          &lpbiIn->bmiHeader,
          lpBits,
          ckid,
          &dwFlags,
          0,
          dwFrameSize,
          dwQuality,
          0,
          0)
      & 0x80000000) != 0 )
  {
    ICSendMessage(v10, 0x4009u, 0, 0);
    goto LABEL_31;
  }
  if ( v7 )
    *v7 = v14->biSizeImage;
  if ( ICSendMessage(v10, 0x4009u, 0, 0) )
    goto LABEL_31;
  LODWORD(plSize) = 0;
  if ( (int)SafeDibSize(v14, &plSize) < 0 )
    goto LABEL_31;
  v26 = GlobalHandle(v14);
  GlobalUnlock(v26);
  v27 = (unsigned int)plSize;
  v28 = GlobalHandle(v14);
  v29 = GlobalReAlloc(v28, v27, 0);
  v30 = GlobalLock(v29);
  if ( v11 )
    ICClose(v10);
  v31 = GlobalHandle(v30);
  GlobalUnlock(v31);
  return GlobalHandle(v30);
}

```

## disassembly

```asm
0x180005cf0  push    rbx
0x180005cf2  push    rbp
0x180005cf3  push    rsi
0x180005cf4  push    rdi
0x180005cf5  push    r12
0x180005cf7  push    r13
0x180005cf9  push    r14
0x180005cfb  push    r15
0x180005cfd  sub     rsp, 88h
0x180005d04  mov     r15, [rsp+0C8h+plSize]
0x180005d0c  mov     r13, r9
0x180005d0f  mov     [rsp+0C8h+dwFlags], 0
0x180005d17  mov     r14, r8
0x180005d1a  mov     [rsp+0C8h+ckid], 0
0x180005d22  mov     rsi, rcx
0x180005d25  test    r15, r15
0x180005d28  jz      short loc_180005D36
0x180005d2a  mov     eax, [r15]
0x180005d2d  mov     [rsp+0C8h+arg_0], eax
0x180005d34  jmp     short loc_180005D41
0x180005d36  mov     [rsp+0C8h+arg_0], 0
0x180005d41  mov     rbx, [rsp+0C8h+lpbiOut]
0x180005d49  mov     ebp, 1
0x180005d4e  test    rcx, rcx
0x180005d51  jnz     short loc_180005D78
0x180005d53  mov     r9, rbx; lpbiOut
0x180005d56  mov     [rsp+0C8h+wFlags], bp; wFlags
0x180005d5b  xor     edx, edx; fccHandler
0x180005d5d  mov     ecx, 63646976h; fccType
0x180005d62  mov     r12d, ebp
0x180005d65  call    ICLocate
0x180005d6a  mov     rsi, rax
0x180005d6d  test    rax, rax
0x180005d70  jz      loc_180005FCC
0x180005d76  jmp     short loc_180005D7B
0x180005d78  xor     r12d, r12d
0x180005d7b  xor     r9d, r9d; dw2
0x180005d7e  mov     r8, r14; dw1
0x180005d81  mov     edx, 4006h; msg
0x180005d86  mov     rcx, rsi; hic
0x180005d89  call    ICSendMessage
0x180005d8e  test    rax, rax
0x180005d91  jnz     loc_180005FBF
0x180005d97  test    rbx, rbx
0x180005d9a  jz      short loc_180005DAE
0x180005d9c  mov     eax, [rbx]
0x180005d9e  lea     ecx, [rax+400h]
0x180005da4  cmp     ecx, eax
0x180005da6  jb      loc_180005FBF
0x180005dac  jmp     short loc_180005DCC
0x180005dae  xor     r9d, r9d; dw2
0x180005db1  mov     r8, r14; dw1
0x180005db4  mov     edx, 4004h; msg
0x180005db9  mov     rcx, rsi; hic
0x180005dbc  call    ICSendMessage
0x180005dc1  mov     rcx, rax
0x180005dc4  test    eax, eax
0x180005dc6  jle     loc_180005FBF
0x180005dcc  movsxd  rdx, ecx; dwBytes
0x180005dcf  mov     ecx, 42h ; 'B'; uFlags
0x180005dd4  call    cs:__imp_GlobalAlloc
0x180005dda  mov     rcx, rax; hMem
0x180005ddd  call    cs:__imp_GlobalLock
0x180005de3  mov     rdi, rax
0x180005de6  test    rax, rax
0x180005de9  jz      loc_180005FBF
0x180005def  test    rbx, rbx
0x180005df2  jz      short loc_180005E22
0x180005df4  mov     r9, rbx; dw2
0x180005df7  mov     r8, r14; dw1
0x180005dfa  mov     edx, 4006h; msg
0x180005dff  mov     rcx, rsi; hic
0x180005e02  call    ICSendMessage
0x180005e07  test    rax, rax
0x180005e0a  jnz     short loc_180005E22
0x180005e0c  mov     ecx, [rbx+20h]
0x180005e0f  mov     rdx, rbx; Src
0x180005e12  mov     eax, [rbx]
0x180005e14  lea     r8, [rax+rcx*4]; Size
0x180005e18  mov     rcx, rdi; void *
0x180005e1b  call    memmove_0
0x180005e20  jmp     short loc_180005E35
0x180005e22  mov     r9, rdi; dw2
0x180005e25  mov     r8, r14; dw1
0x180005e28  mov     edx, 4004h; msg
0x180005e2d  mov     rcx, rsi; hic
0x180005e30  call    ICSendMessage
0x180005e35  mov     r9, rdi; dw2
0x180005e38  mov     r8, r14; dw1
0x180005e3b  mov     edx, 4005h; msg
0x180005e40  mov     rcx, rsi; hic
0x180005e43  call    ICSendMessage
0x180005e48  xor     ebx, ebx
0x180005e4a  mov     [rdi+14h], eax
0x180005e4d  cmp     [rdi+20h], ebx
0x180005e50  jnz     short loc_180005E66
0x180005e52  movzx   ecx, word ptr [rdi+0Eh]
0x180005e56  movzx   eax, cx
0x180005e59  sub     ax, bp
0x180005e5c  cmp     ax, 7
0x180005e60  ja      short loc_180005E66
0x180005e62  shl     ebp, cl
0x180005e64  jmp     short loc_180005E69
0x180005e66  mov     ebp, [rdi+20h]
0x180005e69  lea     rdx, [rsp+0C8h+plSize]
0x180005e71  mov     [rdi+20h], ebp
0x180005e74  mov     rcx, rdi
0x180005e77  mov     dword ptr [rsp+0C8h+plSize], ebx
0x180005e7e  call    SafeDibSize
0x180005e83  test    eax, eax
0x180005e85  js      loc_180005F9B
0x180005e8b  mov     rcx, rdi; pMem
0x180005e8e  call    cs:__imp_GlobalHandle
0x180005e94  mov     rcx, rax; hMem
0x180005e97  call    cs:__imp_GlobalUnlock
0x180005e9d  mov     ebx, dword ptr [rsp+0C8h+plSize]
0x180005ea4  mov     rcx, rdi; pMem
0x180005ea7  call    cs:__imp_GlobalHandle
0x180005ead  xor     r8d, r8d; uFlags
0x180005eb0  mov     edx, ebx; dwBytes
0x180005eb2  mov     rcx, rax; hMem
0x180005eb5  call    cs:__imp_GlobalReAlloc
0x180005ebb  mov     rcx, rax; hMem
0x180005ebe  call    cs:__imp_GlobalLock
0x180005ec4  xor     ebx, ebx
0x180005ec6  mov     rdi, rax
0x180005ec9  test    rax, rax
0x180005ecc  jz      loc_180005FBF
0x180005ed2  mov     r9, rax; dw2
0x180005ed5  mov     r8, r14; dw1
0x180005ed8  mov     edx, 4007h; msg
0x180005edd  mov     rcx, rsi; hic
0x180005ee0  call    ICSendMessage
0x180005ee5  test    rax, rax
0x180005ee8  jnz     loc_180005F9B
0x180005eee  test    r13, r13
0x180005ef1  jnz     short loc_180005F01
0x180005ef3  movsxd  rcx, dword ptr [r14]
0x180005ef6  mov     edx, [r14+20h]
0x180005efa  add     rcx, r14
0x180005efd  lea     r13, [rcx+rdx*4]
0x180005f01  mov     r8d, [rsp+0C8h+lQuality]
0x180005f09  cmp     r8d, 0FFFFFFFFh
0x180005f0d  jnz     short loc_180005F2E
0x180005f0f  lea     r9d, [r8+5]; dw2
0x180005f13  mov     edx, 501Eh; msg
0x180005f18  lea     r8, dw1; dw1
0x180005f1f  mov     rcx, rsi; hic
0x180005f22  call    ICSendMessage
0x180005f27  mov     r8d, cs:dw1
0x180005f2e  mov     edx, [rdi+20h]
0x180005f31  movsxd  rcx, dword ptr [rdi]
0x180005f34  mov     eax, [rsp+0C8h+arg_0]
0x180005f3b  add     rcx, rdi
0x180005f3e  mov     [rsp+0C8h+lpPrev], rbx; lpPrev
0x180005f43  mov     [rsp+0C8h+lpbiPrev], rbx; lpbiPrev
0x180005f48  mov     [rsp+0C8h+dwQuality], r8d; dwQuality
0x180005f4d  mov     r8, rdi; lpbiOutput
0x180005f50  mov     [rsp+0C8h+dwFrameSize], eax; dwFrameSize
0x180005f54  lea     r9, [rcx+rdx*4]; lpData
0x180005f58  mov     [rsp+0C8h+lFrameNum], ebx; lFrameNum
0x180005f5c  lea     rax, [rsp+0C8h+dwFlags]
0x180005f61  mov     [rsp+0C8h+lpdwFlags], rax; lpdwFlags
0x180005f66  xor     edx, edx; dwFlags
0x180005f68  lea     rax, [rsp+0C8h+ckid]
0x180005f6d  mov     rcx, rsi; hic
0x180005f70  mov     [rsp+0C8h+lpckid], rax; lpckid
0x180005f75  mov     [rsp+0C8h+lpBits], r13; lpBits
0x180005f7a  mov     qword ptr [rsp+0C8h+wFlags], r14; lpbiInput
0x180005f7f  call    ICCompress
0x180005f84  test    eax, eax
0x180005f86  jns     short loc_180005FE2
0x180005f88  xor     r9d, r9d; dw2
0x180005f8b  xor     r8d, r8d; dw1
0x180005f8e  mov     edx, 4009h; msg
0x180005f93  mov     rcx, rsi; hic
0x180005f96  call    ICSendMessage
0x180005f9b  mov     rcx, rdi; pMem
0x180005f9e  call    cs:__imp_GlobalHandle
0x180005fa4  mov     rcx, rax; hMem
0x180005fa7  call    cs:__imp_GlobalUnlock
0x180005fad  mov     rcx, rdi; pMem
0x180005fb0  call    cs:__imp_GlobalHandle
0x180005fb6  mov     rcx, rax; hMem
0x180005fb9  call    cs:__imp_GlobalFree
0x180005fbf  test    r12d, r12d
0x180005fc2  jz      short loc_180005FCC
0x180005fc4  mov     rcx, rsi; hic
0x180005fc7  call    ICClose
0x180005fcc  xor     eax, eax
0x180005fce  add     rsp, 88h
0x180005fd5  pop     r15
0x180005fd7  pop     r14
0x180005fd9  pop     r13
0x180005fdb  pop     r12
0x180005fdd  pop     rdi
0x180005fde  pop     rsi
0x180005fdf  pop     rbp
0x180005fe0  pop     rbx
0x180005fe1  retn
0x180005fe2  test    r15, r15
0x180005fe5  jz      short loc_180005FED
0x180005fe7  mov     eax, [rdi+14h]
0x180005fea  mov     [r15], eax
0x180005fed  xor     r9d, r9d; dw2
0x180005ff0  xor     r8d, r8d; dw1
0x180005ff3  mov     edx, 4009h; msg
0x180005ff8  mov     rcx, rsi; hic
0x180005ffb  call    ICSendMessage
0x180006000  test    rax, rax
0x180006003  jnz     short loc_180005F9B
0x180006005  lea     rdx, [rsp+0C8h+plSize]
0x18000600d  mov     dword ptr [rsp+0C8h+plSize], ebx
0x180006014  mov     rcx, rdi
0x180006017  call    SafeDibSize
0x18000601c  test    eax, eax
0x18000601e  js      loc_180005F9B
0x180006024  mov     rcx, rdi; pMem
0x180006027  call    cs:__imp_GlobalHandle
0x18000602d  mov     rcx, rax; hMem
0x180006030  call    cs:__imp_GlobalUnlock
0x180006036  mov     ebx, dword ptr [rsp+0C8h+plSize]
0x18000603d  mov     rcx, rdi; pMem
0x180006040  call    cs:__imp_GlobalHandle
0x180006046  xor     r8d, r8d; uFlags
0x180006049  mov     edx, ebx; dwBytes
0x18000604b  mov     rcx, rax; hMem
0x18000604e  call    cs:__imp_GlobalReAlloc
0x180006054  mov     rcx, rax; hMem
0x180006057  call    cs:__imp_GlobalLock
0x18000605d  mov     rbx, rax
0x180006060  test    r12d, r12d
0x180006063  jz      short loc_18000606D
0x180006065  mov     rcx, rsi; hic
0x180006068  call    ICClose
0x18000606d  mov     rcx, rbx; pMem
0x180006070  call    cs:__imp_GlobalHandle
0x180006076  mov     rcx, rax; hMem
0x180006079  call    cs:__imp_GlobalUnlock
0x18000607f  mov     rcx, rbx; pMem
0x180006082  call    cs:__imp_GlobalHandle
0x180006088  jmp     loc_180005FCE
```
