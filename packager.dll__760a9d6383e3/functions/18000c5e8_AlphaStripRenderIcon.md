# AlphaStripRenderIcon

- ea: `0x18000c5e8`
- end: `0x18000c826`
- name: `AlphaStripRenderIcon`
- size: `574`
- prototype: `BOOL __fastcall(HDC hDC, int X, __int64, HICON)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a474`

## callees

- `0x18000c5e8`
- `0x18000cbf0`

## import_xrefs

- `USER32!GetIconInfo` at `0x18000c62d`
- `USER32!GetIconInfo` at `0x18000c62d`
- `USER32!CreateIconIndirect` at `0x18000c7b8`
- `USER32!CreateIconIndirect` at `0x18000c7b8`
- `USER32!DestroyIcon` at `0x18000c7f9`
- `USER32!DestroyIcon` at `0x18000c7f9`
- `USER32!DrawIcon` at `0x18000c7eb`
- `USER32!DrawIcon` at `0x18000c7eb`
- `GDI32!SelectObject` at `0x18000c6ef`
- `GDI32!SelectObject` at `0x18000c700`
- `GDI32!SelectObject` at `0x18000c781`
- `GDI32!SelectObject` at `0x18000c78e`
- `GDI32!SelectObject` at `0x18000c6ef`
- `GDI32!SelectObject` at `0x18000c700`
- `GDI32!SelectObject` at `0x18000c781`
- `GDI32!SelectObject` at `0x18000c78e`
- `GDI32!DeleteObject` at `0x18000c797`
- `GDI32!DeleteObject` at `0x18000c7c5`
- `GDI32!DeleteObject` at `0x18000c7cf`
- `GDI32!DeleteObject` at `0x18000c797`
- `GDI32!DeleteObject` at `0x18000c7c5`
- `GDI32!DeleteObject` at `0x18000c7cf`
- `GDI32!CreateDIBSection` at `0x18000c6d4`
- `GDI32!CreateDIBSection` at `0x18000c6d4`
- `GDI32!GetObjectW` at `0x18000c653`
- `GDI32!GetObjectW` at `0x18000c653`
- `GDI32!CreateCompatibleDC` at `0x18000c65b`
- `GDI32!CreateCompatibleDC` at `0x18000c666`
- `GDI32!CreateCompatibleDC` at `0x18000c65b`
- `GDI32!CreateCompatibleDC` at `0x18000c666`
- `GDI32!DeleteDC` at `0x18000c7a0`
- `GDI32!DeleteDC` at `0x18000c7ae`
- `GDI32!DeleteDC` at `0x18000c7a0`
- `GDI32!DeleteDC` at `0x18000c7ae`
- `GDI32!BitBlt` at `0x18000c73a`
- `GDI32!BitBlt` at `0x18000c73a`

## pseudocode

```c
BOOL __fastcall AlphaStripRenderIcon(HDC hDC, int X, __int64 a3, HICON a4)
{
  BOOL result; // eax
  HDC CompatibleDC; // rdi
  HDC v9; // rax
  HDC v10; // rbx
  HBITMAP v11; // rax
  HBITMAP v12; // r14
  HBITMAP hbmColor; // r15
  __int64 v14; // rcx
  unsigned int v15; // r8d
  _BYTE *v16; // rdx
  __int64 v17; // rcx
  HICON v18; // rbx
  void *ppvBits; // [rsp+50h] [rbp-71h] BYREF
  ICONINFO piconinfo; // [rsp+58h] [rbp-69h] BYREF
  _OWORD pv[2]; // [rsp+78h] [rbp-49h] BYREF
  HGDIOBJ h; // [rsp+98h] [rbp-29h]
  HGDIOBJ v23; // [rsp+A0h] [rbp-21h]
  BITMAPINFO pbmi; // [rsp+A8h] [rbp-19h] BYREF

  memset(&piconinfo, 0, sizeof(piconinfo));
  result = GetIconInfo(a4, &piconinfo);
  if ( result )
  {
    memset(pv, 0, sizeof(pv));
    GetObjectW(piconinfo.hbmColor, 32, pv);
    CompatibleDC = CreateCompatibleDC(0);
    v9 = CreateCompatibleDC(0);
    v10 = v9;
    if ( CompatibleDC )
    {
      if ( v9 )
      {
        *(_QWORD *)&pbmi.bmiHeader.biWidth = *(_QWORD *)((char *)pv + 4);
        ppvBits = 0;
        memset(&pbmi.bmiHeader.biSizeImage, 0, 24);
        pbmi.bmiHeader.biSize = 40;
        *(_QWORD *)&pbmi.bmiHeader.biPlanes = 2097153;
        v11 = CreateDIBSection(hDC, &pbmi, 0, &ppvBits, 0, 0);
        v12 = v11;
        if ( v11 )
        {
          hbmColor = v11;
          v23 = SelectObject(CompatibleDC, v11);
          h = SelectObject(v10, piconinfo.hbmColor);
          BitBlt(CompatibleDC, 0, 0, SDWORD1(pv[0]), SDWORD2(pv[0]), v10, 0, 0, 0xCC0020u);
          v14 = 0;
          v15 = DWORD2(pv[0]) * DWORD1(pv[0]);
          if ( DWORD2(pv[0]) * DWORD1(pv[0]) )
          {
            v16 = ppvBits;
            while ( !*((_BYTE *)ppvBits + 4 * v14 + 3) )
            {
              v14 = (unsigned int)(v14 + 1);
              if ( (unsigned int)v14 >= v15 )
                goto LABEL_13;
            }
            v17 = 0;
            do
            {
              v16[4 * v17 + 3] = 0;
              v17 = (unsigned int)(v17 + 1);
            }
            while ( (unsigned int)v17 < v15 );
            hbmColor = piconinfo.hbmColor;
            piconinfo.hbmColor = v12;
          }
LABEL_13:
          SelectObject(v10, h);
          SelectObject(CompatibleDC, v23);
          DeleteObject(hbmColor);
        }
      }
      DeleteDC(CompatibleDC);
    }
    if ( v10 )
      DeleteDC(v10);
    v18 = CreateIconIndirect(&piconinfo);
    DeleteObject(piconinfo.hbmColor);
    result = DeleteObject(piconinfo.hbmMask);
  }
  else
  {
    v18 = a4;
  }
  if ( v18 )
  {
    result = DrawIcon(hDC, X, 0, v18);
    if ( v18 != a4 )
      return DestroyIcon(v18);
  }
  return result;
}

```

## disassembly

```asm
0x18000c5e8  mov     [rsp-8+arg_10], rbx
0x18000c5ed  push    rbp
0x18000c5ee  push    rsi
0x18000c5ef  push    rdi
0x18000c5f0  push    r12
0x18000c5f2  push    r13
0x18000c5f4  push    r14
0x18000c5f6  push    r15
0x18000c5f8  lea     rbp, [rsp-1Fh]
0x18000c5fd  sub     rsp, 0E0h
0x18000c604  mov     rax, cs:__security_cookie
0x18000c60b  xor     rax, rsp
0x18000c60e  mov     [rbp+4Fh+var_38], rax
0x18000c612  xorps   xmm0, xmm0
0x18000c615  mov     r13d, edx
0x18000c618  mov     r12, rcx
0x18000c61b  lea     rdx, [rbp+4Fh+piconinfo]; piconinfo
0x18000c61f  mov     rcx, r9; hIcon
0x18000c622  mov     rsi, r9
0x18000c625  movups  xmmword ptr [rbp+4Fh+piconinfo.fIcon], xmm0
0x18000c629  movups  xmmword ptr [rbp+4Fh+piconinfo.hbmMask], xmm0
0x18000c62d  call    cs:__imp_GetIconInfo
0x18000c633  test    eax, eax
0x18000c635  jz      loc_18000C7D7
0x18000c63b  mov     rcx, [rbp+4Fh+piconinfo.hbmColor]; h
0x18000c63f  lea     r8, [rbp+4Fh+pv]; pv
0x18000c643  xorps   xmm0, xmm0
0x18000c646  mov     edx, 20h ; ' '; c
0x18000c64b  movups  [rbp+4Fh+pv], xmm0
0x18000c64f  movups  [rbp+4Fh+var_88], xmm0
0x18000c653  call    cs:__imp_GetObjectW
0x18000c659  xor     ecx, ecx; hdc
0x18000c65b  call    cs:__imp_CreateCompatibleDC
0x18000c661  xor     ecx, ecx; hdc
0x18000c663  mov     rdi, rax
0x18000c666  call    cs:__imp_CreateCompatibleDC
0x18000c66c  mov     rbx, rax
0x18000c66f  test    rdi, rdi
0x18000c672  jz      loc_18000C7A6
0x18000c678  test    rax, rax
0x18000c67b  jz      loc_18000C79D
0x18000c681  xor     eax, eax
0x18000c683  mov     [rsp+110h+offset], 0; offset
0x18000c68b  xorps   xmm0, xmm0
0x18000c68e  mov     qword ptr [rbp+4Fh+pbmi.bmiHeader.biClrImportant], rax
0x18000c692  mov     eax, dword ptr [rbp+4Fh+pv+4]
0x18000c695  lea     r9, [rbp+4Fh+ppvBits]; ppvBits
0x18000c699  movups  xmmword ptr [rbp+4Fh+pbmi.bmiHeader.biWidth], xmm0
0x18000c69d  mov     [rbp+4Fh+pbmi.bmiHeader.biWidth], eax
0x18000c6a0  lea     rdx, [rbp+4Fh+pbmi]; pbmi
0x18000c6a4  mov     eax, dword ptr [rbp+4Fh+pv+8]
0x18000c6a7  xor     r8d, r8d; usage
0x18000c6aa  mov     rcx, r12; hdc
0x18000c6ad  mov     [rbp+4Fh+pbmi.bmiHeader.biHeight], eax
0x18000c6b0  mov     [rbp+4Fh+ppvBits], 0
0x18000c6b8  movups  xmmword ptr [rbp+4Fh+pbmi.bmiHeader.biSizeImage], xmm0
0x18000c6bc  mov     [rbp+4Fh+pbmi.bmiHeader.biSize], 28h ; '('
0x18000c6c3  mov     qword ptr [rbp+4Fh+pbmi.bmiHeader.biPlanes], 200001h
0x18000c6cb  mov     [rsp+110h+hSection], 0; hSection
0x18000c6d4  call    cs:__imp_CreateDIBSection
0x18000c6da  mov     r14, rax
0x18000c6dd  test    rax, rax
0x18000c6e0  jz      loc_18000C79D
0x18000c6e6  mov     rdx, rax; h
0x18000c6e9  mov     rcx, rdi; hdc
0x18000c6ec  mov     r15, rax
0x18000c6ef  call    cs:__imp_SelectObject
0x18000c6f5  mov     rdx, [rbp+4Fh+piconinfo.hbmColor]; h
0x18000c6f9  mov     rcx, rbx; hdc
0x18000c6fc  mov     [rbp+4Fh+var_70], rax
0x18000c700  call    cs:__imp_SelectObject
0x18000c706  mov     ecx, dword ptr [rbp+4Fh+pv+8]
0x18000c709  xor     r8d, r8d; y
0x18000c70c  mov     r9d, dword ptr [rbp+4Fh+pv+4]; cx
0x18000c710  xor     edx, edx; x
0x18000c712  mov     [rsp+110h+rop], 0CC0020h; rop
0x18000c71a  mov     [rsp+110h+y1], 0; y1
0x18000c722  mov     [rsp+110h+x1], 0; x1
0x18000c72a  mov     qword ptr [rsp+110h+offset], rbx; hdcSrc
0x18000c72f  mov     dword ptr [rsp+110h+hSection], ecx; cy
0x18000c733  mov     rcx, rdi; hdc
0x18000c736  mov     [rbp+4Fh+h], rax
0x18000c73a  call    cs:__imp_BitBlt
0x18000c740  mov     r8d, dword ptr [rbp+4Fh+pv+4]
0x18000c744  xor     ecx, ecx
0x18000c746  imul    r8d, dword ptr [rbp+4Fh+pv+8]
0x18000c74b  test    r8d, r8d
0x18000c74e  jz      short loc_18000C77A
0x18000c750  mov     rdx, [rbp+4Fh+ppvBits]
0x18000c754  cmp     byte ptr [rdx+rcx*4+3], 0
0x18000c759  jnz     short loc_18000C764
0x18000c75b  inc     ecx
0x18000c75d  cmp     ecx, r8d
0x18000c760  jb      short loc_18000C754
0x18000c762  jmp     short loc_18000C77A
0x18000c764  xor     ecx, ecx
0x18000c766  mov     byte ptr [rdx+rcx*4+3], 0
0x18000c76b  inc     ecx
0x18000c76d  cmp     ecx, r8d
0x18000c770  jb      short loc_18000C766
0x18000c772  mov     r15, [rbp+4Fh+piconinfo.hbmColor]
0x18000c776  mov     [rbp+4Fh+piconinfo.hbmColor], r14
0x18000c77a  mov     rdx, [rbp+4Fh+h]; h
0x18000c77e  mov     rcx, rbx; hdc
0x18000c781  call    cs:__imp_SelectObject
0x18000c787  mov     rdx, [rbp+4Fh+var_70]; h
0x18000c78b  mov     rcx, rdi; hdc
0x18000c78e  call    cs:__imp_SelectObject
0x18000c794  mov     rcx, r15; ho
0x18000c797  call    cs:__imp_DeleteObject
0x18000c79d  mov     rcx, rdi; hdc
0x18000c7a0  call    cs:__imp_DeleteDC
0x18000c7a6  test    rbx, rbx
0x18000c7a9  jz      short loc_18000C7B4
0x18000c7ab  mov     rcx, rbx; hdc
0x18000c7ae  call    cs:__imp_DeleteDC
0x18000c7b4  lea     rcx, [rbp+4Fh+piconinfo]; piconinfo
0x18000c7b8  call    cs:__imp_CreateIconIndirect
0x18000c7be  mov     rcx, [rbp+4Fh+piconinfo.hbmColor]; ho
0x18000c7c2  mov     rbx, rax
0x18000c7c5  call    cs:__imp_DeleteObject
0x18000c7cb  mov     rcx, [rbp+4Fh+piconinfo.hbmMask]; ho
0x18000c7cf  call    cs:__imp_DeleteObject
0x18000c7d5  jmp     short loc_18000C7DA
0x18000c7d7  mov     rbx, rsi
0x18000c7da  test    rbx, rbx
0x18000c7dd  jz      short loc_18000C7FF
0x18000c7df  mov     r9, rbx; hIcon
0x18000c7e2  xor     r8d, r8d; Y
0x18000c7e5  mov     edx, r13d; X
0x18000c7e8  mov     rcx, r12; hDC
0x18000c7eb  call    cs:__imp_DrawIcon
0x18000c7f1  cmp     rbx, rsi
0x18000c7f4  jz      short loc_18000C7FF
0x18000c7f6  mov     rcx, rbx; hIcon
0x18000c7f9  call    cs:__imp_DestroyIcon
0x18000c7ff  mov     rcx, [rbp+4Fh+var_38]
0x18000c803  xor     rcx, rsp; StackCookie
0x18000c806  call    __security_check_cookie
0x18000c80b  mov     rbx, [rsp+110h+arg_10]
0x18000c813  add     rsp, 0E0h
0x18000c81a  pop     r15
0x18000c81c  pop     r14
0x18000c81e  pop     r13
0x18000c820  pop     r12
0x18000c822  pop     rdi
0x18000c823  pop     rsi
0x18000c824  pop     rbp
0x18000c825  retn
```
