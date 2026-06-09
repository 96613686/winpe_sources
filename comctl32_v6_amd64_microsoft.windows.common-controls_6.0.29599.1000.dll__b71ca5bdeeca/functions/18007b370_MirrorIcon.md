# MirrorIcon

- ea: `0x18007b370`
- end: `0x18007b70e`
- name: `MirrorIcon`
- size: `926`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800108d0`
- `0x180028af0`

## callees

- `0x18007b370`
- `0x18007b714`
- `0x180114520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b428`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18007b428`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007b3cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18007b3cf`
- `GDI32!DeleteObject` at `0x18007b4d8`
- `GDI32!DeleteObject` at `0x18007b4e2`
- `GDI32!DeleteObject` at `0x18007b53e`
- `GDI32!DeleteObject` at `0x18007b547`
- `GDI32!DeleteObject` at `0x18007b4d8`
- `GDI32!DeleteObject` at `0x18007b4e2`
- `GDI32!DeleteObject` at `0x18007b53e`
- `GDI32!DeleteObject` at `0x18007b547`
- `GDI32!GetObjectW` at `0x18007b4cc`
- `GDI32!GetObjectW` at `0x18007b4cc`
- `GDI32!SelectObject` at `0x18007b581`
- `GDI32!SelectObject` at `0x18007b594`
- `GDI32!SelectObject` at `0x18007b629`
- `GDI32!SelectObject` at `0x18007b639`
- `GDI32!SelectObject` at `0x18007b581`
- `GDI32!SelectObject` at `0x18007b594`
- `GDI32!SelectObject` at `0x18007b629`
- `GDI32!SelectObject` at `0x18007b639`
- `GDI32!DeleteDC` at `0x18007b6c9`
- `GDI32!DeleteDC` at `0x18007b6c9`
- `GDI32!CreateCompatibleDC` at `0x18007b676`
- `GDI32!CreateCompatibleDC` at `0x18007b68e`
- `GDI32!CreateCompatibleDC` at `0x18007b676`
- `GDI32!CreateCompatibleDC` at `0x18007b68e`
- `GDI32!SetLayout` at `0x18007b6ac`
- `GDI32!SetLayout` at `0x18007b6be`
- `GDI32!SetLayout` at `0x18007b6ac`
- `GDI32!SetLayout` at `0x18007b6be`
- `GDI32!CreateCompatibleBitmap` at `0x18007b56a`
- `GDI32!CreateCompatibleBitmap` at `0x18007b56a`
- `GDI32!CreateBitmap` at `0x18007b529`
- `GDI32!CreateBitmap` at `0x18007b529`
- `USER32!DestroyIcon` at `0x18007b442`
- `USER32!DestroyIcon` at `0x18007b703`
- `USER32!DestroyIcon` at `0x18007b442`
- `USER32!DestroyIcon` at `0x18007b703`
- `USER32!CreateIconIndirect` at `0x18007b64f`
- `USER32!CreateIconIndirect` at `0x18007b64f`
- `USER32!GetDC` at `0x18007b404`
- `USER32!GetDC` at `0x18007b404`
- `USER32!GetIconInfo` at `0x18007b4b4`
- `USER32!GetIconInfo` at `0x18007b4b4`
- `USER32!DrawIconEx` at `0x18007b5d8`
- `USER32!DrawIconEx` at `0x18007b619`
- `USER32!DrawIconEx` at `0x18007b5d8`
- `USER32!DrawIconEx` at `0x18007b619`
- `USER32!ReleaseDC` at `0x18007b41b`
- `USER32!ReleaseDC` at `0x18007b41b`

## pseudocode

```c
__int64 __fastcall MirrorIcon(HICON *a1, HICON *a2)
{
  HICON *v2; // rbx
  HICON *v3; // rdi
  HICON v4; // r14
  HICON v5; // rsi
  HDC DC; // rax
  HDC v7; // r12
  unsigned int i; // r15d
  int ObjectW; // ebx
  HBITMAP DIB; // rax
  HBITMAP v12; // r13
  HBITMAP Bitmap; // rax
  HBITMAP v14; // rbx
  HGDIOBJ v15; // rdi
  HGDIOBJ v16; // rbx
  HICON hIcon[2]; // [rsp+50h] [rbp-59h]
  HBITMAP v18; // [rsp+60h] [rbp-49h]
  HICON *v19; // [rsp+68h] [rbp-41h]
  HICON *v20; // [rsp+70h] [rbp-39h]
  __int128 pv; // [rsp+78h] [rbp-31h] BYREF
  __int128 v22; // [rsp+88h] [rbp-21h]
  ICONINFO piconinfo; // [rsp+98h] [rbp-11h] BYREF
  __int128 v24; // [rsp+B8h] [rbp+Fh]

  v19 = a1;
  v20 = a2;
  v2 = a1;
  v3 = a2;
  pv = 0;
  v22 = 0;
  *(_OWORD *)hIcon = 0;
  v24 = 0;
  memset(&piconinfo, 0, sizeof(piconinfo));
  AcquireSRWLockExclusive(&SRWLock);
  if ( !g_hdc && !g_hdcMask )
  {
    g_hdc = CreateCompatibleDC(0);
    if ( g_hdc )
    {
      g_hdcMask = CreateCompatibleDC(0);
      if ( g_hdcMask )
      {
        SetLayout(g_hdc, 1u);
        SetLayout(g_hdcMask, 1u);
      }
      else
      {
        DeleteDC(g_hdc);
        g_hdc = 0;
      }
    }
  }
  if ( v2 )
  {
    v4 = *v2;
    hIcon[0] = *v2;
  }
  else
  {
    v4 = hIcon[0];
  }
  if ( v3 )
  {
    v5 = *v3;
    hIcon[1] = *v3;
  }
  else
  {
    v5 = hIcon[1];
  }
  DC = GetDC(0);
  v7 = DC;
  if ( g_hdc && g_hdcMask && DC )
  {
    for ( i = 0; i < 2; ++i )
    {
      if ( hIcon[i] )
      {
        if ( GetIconInfo(hIcon[i], &piconinfo) )
        {
          ObjectW = GetObjectW(piconinfo.hbmColor, 32, &pv);
          DeleteObject(piconinfo.hbmMask);
          DeleteObject(piconinfo.hbmColor);
          piconinfo.hbmColor = 0;
          piconinfo.hbmMask = 0;
          if ( ObjectW )
          {
            if ( WORD1(v22) == 32 )
              DIB = (HBITMAP)CreateDIB(v7, DWORD1(pv), DWORD2(pv), 0);
            else
              DIB = CreateCompatibleBitmap(v7, SDWORD1(pv), SDWORD2(pv));
            v12 = DIB;
            Bitmap = CreateBitmap(SDWORD1(pv), SDWORD2(pv), 1u, 1u, 0);
            v18 = Bitmap;
            v14 = Bitmap;
            if ( v12 && Bitmap )
            {
              v15 = SelectObject(g_hdc, v12);
              v16 = SelectObject(g_hdcMask, v14);
              DrawIconEx(g_hdc, 0, 0, hIcon[i], SDWORD1(pv), SDWORD2(pv), 0, 0, 2u);
              DrawIconEx(g_hdcMask, 0, 0, hIcon[i], SDWORD1(pv), SDWORD2(pv), 0, 0, 1u);
              SelectObject(g_hdc, v15);
              SelectObject(g_hdcMask, v16);
              v14 = v18;
              piconinfo.hbmMask = v18;
              piconinfo.hbmColor = v12;
              *((_QWORD *)&v24 + (int)i) = CreateIconIndirect(&piconinfo);
            }
            DeleteObject(v12);
            DeleteObject(v14);
          }
        }
      }
    }
    v2 = v19;
    v3 = v20;
  }
  ReleaseDC(0, v7);
  ReleaseSRWLockExclusive(&SRWLock);
  if ( v4 && (_QWORD)v24 )
  {
    *v2 = (HICON)v24;
    DestroyIcon(v4);
  }
  if ( v5 )
  {
    if ( *((_QWORD *)&v24 + 1) )
    {
      *v3 = (HICON)*((_QWORD *)&v24 + 1);
      if ( v5 != v4 )
        DestroyIcon(v5);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18007b370  mov     [rsp-8+arg_10], rbx
0x18007b375  push    rbp
0x18007b376  push    rsi
0x18007b377  push    rdi
0x18007b378  push    r12
0x18007b37a  push    r13
0x18007b37c  push    r14
0x18007b37e  push    r15
0x18007b380  lea     rbp, [rsp-27h]
0x18007b385  sub     rsp, 0D0h
0x18007b38c  mov     rax, cs:__security_cookie
0x18007b393  xor     rax, rsp
0x18007b396  mov     [rbp+57h+var_38], rax
0x18007b39a  xorps   xmm0, xmm0
0x18007b39d  mov     [rbp+57h+var_98], rcx
0x18007b3a1  xorps   xmm1, xmm1
0x18007b3a4  mov     [rbp+57h+var_90], rdx
0x18007b3a8  mov     rbx, rcx
0x18007b3ab  mov     rdi, rdx
0x18007b3ae  lea     rcx, SRWLock; SRWLock
0x18007b3b5  movups  [rbp+57h+pv], xmm0
0x18007b3b9  movups  [rbp+57h+var_78], xmm0
0x18007b3bd  movdqu  xmmword ptr [rbp+57h+hIcon], xmm1
0x18007b3c2  movdqu  [rbp+57h+var_48], xmm0
0x18007b3c7  movups  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm1
0x18007b3cb  movups  xmmword ptr [rbp+57h+piconinfo.hbmMask], xmm1
0x18007b3cf  call    cs:__imp_AcquireSRWLockExclusive
0x18007b3d5  xor     r13d, r13d
0x18007b3d8  cmp     cs:g_hdc, r13
0x18007b3df  jz      loc_18007B667
0x18007b3e5  test    rbx, rbx
0x18007b3e8  jz      loc_18007B47D
0x18007b3ee  mov     r14, [rbx]
0x18007b3f1  mov     [rbp+57h+hIcon], r14
0x18007b3f5  test    rdi, rdi
0x18007b3f8  jnz     loc_18007B6DB
0x18007b3fe  mov     rsi, [rbp+57h+hIcon+8]
0x18007b402  xor     ecx, ecx; hWnd
0x18007b404  call    cs:__imp_GetDC
0x18007b40a  cmp     cs:g_hdc, r13
0x18007b411  mov     r12, rax
0x18007b414  jnz     short loc_18007B486
0x18007b416  mov     rdx, r12; hDC
0x18007b419  xor     ecx, ecx; hWnd
0x18007b41b  call    cs:__imp_ReleaseDC
0x18007b421  lea     rcx, SRWLock; SRWLock
0x18007b428  call    cs:__imp_ReleaseSRWLockExclusive
0x18007b42e  test    r14, r14
0x18007b431  jz      short loc_18007B448
0x18007b433  mov     rax, qword ptr [rbp+57h+var_48]
0x18007b437  test    rax, rax
0x18007b43a  jz      short loc_18007B448
0x18007b43c  mov     rcx, r14; hIcon
0x18007b43f  mov     [rbx], rax
0x18007b442  call    cs:__imp_DestroyIcon
0x18007b448  test    rsi, rsi
0x18007b44b  jnz     loc_18007B6E7
0x18007b451  mov     eax, 1
0x18007b456  mov     rcx, [rbp+57h+var_38]
0x18007b45a  xor     rcx, rsp; StackCookie
0x18007b45d  call    __security_check_cookie
0x18007b462  mov     rbx, [rsp+100h+arg_10]
0x18007b46a  add     rsp, 0D0h
0x18007b471  pop     r15
0x18007b473  pop     r14
0x18007b475  pop     r13
0x18007b477  pop     r12
0x18007b479  pop     rdi
0x18007b47a  pop     rsi
0x18007b47b  pop     rbp
0x18007b47c  retn
0x18007b47d  mov     r14, [rbp+57h+hIcon]
0x18007b481  jmp     loc_18007B3F5
0x18007b486  cmp     cs:g_hdcMask, r13
0x18007b48d  jz      short loc_18007B416
0x18007b48f  test    r12, r12
0x18007b492  jz      short loc_18007B416
0x18007b494  mov     r15d, r13d
0x18007b497  mov     edi, 20h ; ' '
0x18007b49c  movsxd  rax, r15d
0x18007b49f  mov     rax, [rbp+rax*8+57h+hIcon]
0x18007b4a4  test    rax, rax
0x18007b4a7  jz      loc_18007B550
0x18007b4ad  lea     rdx, [rbp+57h+piconinfo]; piconinfo
0x18007b4b1  mov     rcx, rax; hIcon
0x18007b4b4  call    cs:__imp_GetIconInfo
0x18007b4ba  test    eax, eax
0x18007b4bc  jz      loc_18007B550
0x18007b4c2  mov     rcx, [rbp+57h+piconinfo.hbmColor]; h
0x18007b4c6  lea     r8, [rbp+57h+pv]; pv
0x18007b4ca  mov     edx, edi; c
0x18007b4cc  call    cs:__imp_GetObjectW
0x18007b4d2  mov     rcx, [rbp+57h+piconinfo.hbmMask]; ho
0x18007b4d6  mov     ebx, eax
0x18007b4d8  call    cs:__imp_DeleteObject
0x18007b4de  mov     rcx, [rbp+57h+piconinfo.hbmColor]; ho
0x18007b4e2  call    cs:__imp_DeleteObject
0x18007b4e8  mov     [rbp+57h+piconinfo.hbmColor], r13
0x18007b4ec  mov     [rbp+57h+piconinfo.hbmMask], r13
0x18007b4f0  test    ebx, ebx
0x18007b4f2  jz      short loc_18007B550
0x18007b4f4  mov     rcx, r12; hdc
0x18007b4f7  mov     r8d, dword ptr [rbp+57h+pv+8]; cy
0x18007b4fb  mov     edx, dword ptr [rbp+57h+pv+4]; cx
0x18007b4fe  cmp     word ptr [rbp+57h+var_78+2], di
0x18007b502  jnz     short loc_18007B56A
0x18007b504  xor     r9d, r9d
0x18007b507  call    CreateDIB
0x18007b50c  mov     edx, dword ptr [rbp+57h+pv+8]; nHeight
0x18007b50f  mov     r13, rax
0x18007b512  mov     ecx, dword ptr [rbp+57h+pv+4]; nWidth
0x18007b515  mov     eax, 1
0x18007b51a  mov     r9d, eax; nBitCount
0x18007b51d  mov     [rsp+100h+lpBits], 0; lpBits
0x18007b526  mov     r8d, eax; nPlanes
0x18007b529  call    cs:__imp_CreateBitmap
0x18007b52f  mov     [rbp+57h+var_A0], rax
0x18007b533  mov     rbx, rax
0x18007b536  test    r13, r13
0x18007b539  jnz     short loc_18007B572
0x18007b53b  mov     rcx, r13; ho
0x18007b53e  call    cs:__imp_DeleteObject
0x18007b544  mov     rcx, rbx; ho
0x18007b547  call    cs:__imp_DeleteObject
0x18007b54d  xor     r13d, r13d
0x18007b550  inc     r15d
0x18007b553  cmp     r15d, 2
0x18007b557  jb      loc_18007B49C
0x18007b55d  mov     rbx, [rbp+57h+var_98]
0x18007b561  mov     rdi, [rbp+57h+var_90]
0x18007b565  jmp     loc_18007B416
0x18007b56a  call    cs:__imp_CreateCompatibleBitmap
0x18007b570  jmp     short loc_18007B50C
0x18007b572  test    rbx, rbx
0x18007b575  jz      short loc_18007B53B
0x18007b577  mov     rcx, cs:g_hdc; hdc
0x18007b57e  mov     rdx, r13; h
0x18007b581  call    cs:__imp_SelectObject
0x18007b587  mov     rcx, cs:g_hdcMask; hdc
0x18007b58e  mov     rdx, rbx; h
0x18007b591  mov     rdi, rax
0x18007b594  call    cs:__imp_SelectObject
0x18007b59a  mov     [rsp+100h+diFlags], 2; diFlags
0x18007b5a2  xor     r8d, r8d; yTop
0x18007b5a5  mov     rbx, rax
0x18007b5a8  mov     [rsp+100h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x18007b5b1  mov     eax, dword ptr [rbp+57h+pv+8]
0x18007b5b4  xor     edx, edx; xLeft
0x18007b5b6  movsxd  rcx, r15d
0x18007b5b9  mov     [rsp+100h+istepIfAniCur], 0; istepIfAniCur
0x18007b5c1  mov     [rsp+100h+cyWidth], eax; cyWidth
0x18007b5c5  mov     eax, dword ptr [rbp+57h+pv+4]
0x18007b5c8  mov     r9, [rbp+rcx*8+57h+hIcon]; hIcon
0x18007b5cd  mov     rcx, cs:g_hdc; hdc
0x18007b5d4  mov     dword ptr [rsp+100h+lpBits], eax; cxWidth
0x18007b5d8  call    cs:__imp_DrawIconEx
0x18007b5de  mov     eax, dword ptr [rbp+57h+pv+8]
0x18007b5e1  xor     r8d, r8d; yTop
0x18007b5e4  mov     rcx, cs:g_hdcMask; hdc
0x18007b5eb  xor     edx, edx; xLeft
0x18007b5ed  mov     [rsp+100h+diFlags], 1; diFlags
0x18007b5f5  mov     [rsp+100h+hbrFlickerFreeDraw], 0; hbrFlickerFreeDraw
0x18007b5fe  mov     [rsp+100h+istepIfAniCur], 0; istepIfAniCur
0x18007b606  mov     [rsp+100h+cyWidth], eax; cyWidth
0x18007b60a  mov     eax, dword ptr [rbp+57h+pv+4]
0x18007b60d  mov     dword ptr [rsp+100h+lpBits], eax; cxWidth
0x18007b611  movsxd  rax, r15d
0x18007b614  mov     r9, [rbp+rax*8+57h+hIcon]; hIcon
0x18007b619  call    cs:__imp_DrawIconEx
0x18007b61f  mov     rcx, cs:g_hdc; hdc
0x18007b626  mov     rdx, rdi; h
0x18007b629  call    cs:__imp_SelectObject
0x18007b62f  mov     rcx, cs:g_hdcMask; hdc
0x18007b636  mov     rdx, rbx; h
0x18007b639  call    cs:__imp_SelectObject
0x18007b63f  mov     rbx, [rbp+57h+var_A0]
0x18007b643  lea     rcx, [rbp+57h+piconinfo]; piconinfo
0x18007b647  mov     [rbp+57h+piconinfo.hbmMask], rbx
0x18007b64b  mov     [rbp+57h+piconinfo.hbmColor], r13
0x18007b64f  call    cs:__imp_CreateIconIndirect
0x18007b655  movsxd  rcx, r15d
0x18007b658  mov     edi, 20h ; ' '
0x18007b65d  mov     qword ptr [rbp+rcx*8+57h+var_48], rax
0x18007b662  jmp     loc_18007B53B
0x18007b667  cmp     cs:g_hdcMask, r13
0x18007b66e  jnz     loc_18007B3E5
0x18007b674  xor     ecx, ecx; hdc
0x18007b676  call    cs:__imp_CreateCompatibleDC
0x18007b67c  mov     cs:g_hdc, rax
0x18007b683  test    rax, rax
0x18007b686  jz      loc_18007B3E5
0x18007b68c  xor     ecx, ecx; hdc
0x18007b68e  call    cs:__imp_CreateCompatibleDC
0x18007b694  mov     rcx, cs:g_hdc; hdc
0x18007b69b  mov     cs:g_hdcMask, rax
0x18007b6a2  test    rax, rax
0x18007b6a5  jz      short loc_18007B6C9
0x18007b6a7  mov     edx, 1; l
0x18007b6ac  call    cs:__imp_SetLayout
0x18007b6b2  mov     rcx, cs:g_hdcMask; hdc
0x18007b6b9  mov     edx, 1; l
0x18007b6be  call    cs:__imp_SetLayout
0x18007b6c4  jmp     loc_18007B3E5
0x18007b6c9  call    cs:__imp_DeleteDC
0x18007b6cf  mov     cs:g_hdc, r13
0x18007b6d6  jmp     loc_18007B3E5
0x18007b6db  mov     rsi, [rdi]
0x18007b6de  mov     [rbp+57h+hIcon+8], rsi
0x18007b6e2  jmp     loc_18007B402
0x18007b6e7  mov     rcx, qword ptr [rbp+57h+var_48+8]
0x18007b6eb  test    rcx, rcx
0x18007b6ee  jz      loc_18007B451
0x18007b6f4  mov     [rdi], rcx
0x18007b6f7  cmp     rsi, r14
0x18007b6fa  jz      loc_18007B451
0x18007b700  mov     rcx, rsi; hIcon
0x18007b703  call    cs:__imp_DestroyIcon
0x18007b709  jmp     loc_18007B451
```
