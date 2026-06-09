# CRDPGfxRecorder::AddBitmapUpdate(unsigned __int64,tagRECT,PixelMap *,PixelMap *,int)

- ea: `0x1800c6710`
- end: `0x1800c69a8`
- name: `?AddBitmapUpdate@CRDPGfxRecorder@@UEAAJ_KUtagRECT@@PEAVPixelMap@@2H@Z`
- size: `664`
- prototype: `__int64 __fastcall(CRDPGfxRecorder *__hidden this, unsigned __int64, struct tagRECT *__struct_ptr, struct PixelMap *, struct PixelMap *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x1800c7380`

## callees

- `0x1800091a8`
- `0x18002e600`
- `0x180033940`
- `0x180033964`
- `0x180034970`
- `0x1800598d0`
- `0x1800c6710`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c68a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c68a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6928`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c6893`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c691e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c6893`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800c691e`

## string_xrefs

- `0x1800c6967`: `failed to open file`

## pseudocode

```c
__int64 __fastcall CRDPGfxRecorder::AddBitmapUpdate(HANDLE *this, __int64 a2, struct tagRECT *a3, struct PixelMap *a4)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v8; // ebx
  int v9; // r15d
  char *v10; // rax
  char *v11; // rsi
  unsigned int v12; // eax
  int v13; // ecx
  signed int LastError; // eax
  unsigned int v15; // eax
  int v16; // edx
  signed int v17; // eax
  DWORD NumberOfBytesWritten; // [rsp+88h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        31,
        (unsigned int)WPP_00f57cbcba22367f230f2d13c3b6dfe1_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"pNewmap");
    }
    return (unsigned int)-2147467261;
  }
  v9 = *((_DWORD *)a4 + 1) * *(_DWORD *)a4 * (unsigned __int8)((*((_DWORD *)a4 + 3) + 1) >> 3) + 72;
  v10 = (char *)operator new(0x48u);
  v11 = v10;
  if ( v10 )
  {
    v8 = 0;
    memset_0(v10, 0, 0x48u);
    *(_DWORD *)v11 = 1651856467;
    *((_WORD *)v11 + 6) = 0;
    *((_DWORD *)v11 + 2) = v9;
    *((_DWORD *)v11 + 1) = 6;
    *((_QWORD *)v11 + 2) = a2;
    *((_DWORD *)v11 + 6) = *((_DWORD *)a4 + 1);
    *((_DWORD *)v11 + 7) = *(_DWORD *)a4;
    *((_WORD *)v11 + 16) = 32;
    *((_DWORD *)v11 + 9) = 1;
    v13 = *((_DWORD *)a4 + 1) * *(_DWORD *)a4 * (unsigned __int8)((*((_DWORD *)a4 + 3) + 1) >> 3);
    *(_QWORD *)(v11 + 44) = 0;
    *((_DWORD *)v11 + 17) = v13;
    *((_DWORD *)v11 + 14) = *((_DWORD *)a4 + 1);
    *((_DWORD *)v11 + 13) = *(_DWORD *)a4;
    *((_DWORD *)v11 + 10) = 0;
    *((_DWORD *)v11 + 15) = 0;
    if ( WriteFile(this[12], v11, 0x48u, &NumberOfBytesWritten, 0) )
      goto LABEL_27;
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
    {
LABEL_27:
      if ( WriteFile(
             this[12],
             *((LPCVOID *)a4 + 3),
             *((_DWORD *)a4 + 1) * *(_DWORD *)a4 * (unsigned __int8)((*((_DWORD *)a4 + 3) + 1) >> 3),
             &NumberOfBytesWritten,
             0) )
      {
        goto LABEL_30;
      }
      v17 = GetLastError();
      v8 = v17;
      if ( v17 > 0 )
        v8 = (unsigned __int16)v17 | 0x80070000;
      if ( v8 >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 34;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      v15 = RdpWppGetCurrentThreadActivityIdPrefix();
      v16 = 33;
    }
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      (unsigned int)WPP_00f57cbcba22367f230f2d13c3b6dfe1_Traceguids,
      v15,
      (__int64)"failed to open file",
      v8);
LABEL_30:
    operator delete(v11);
    return (unsigned int)v8;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      (unsigned int)WPP_00f57cbcba22367f230f2d13c3b6dfe1_Traceguids,
      v12,
      (__int64)"BYTE");
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x1800c6710  mov     rax, rsp
0x1800c6713  push    rbx
0x1800c6714  push    rbp
0x1800c6715  push    rsi
0x1800c6716  push    rdi
0x1800c6717  push    r14
0x1800c6719  push    r15
0x1800c671b  sub     rsp, 38h
0x1800c671f  mov     dword ptr [rax+20h], 0
0x1800c6726  mov     rdi, r9
0x1800c6729  mov     r14, rdx
0x1800c672c  mov     rbp, rcx
0x1800c672f  test    r9, r9
0x1800c6732  jnz     short loc_1800C678B
0x1800c6734  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c673b  lea     rax, WPP_GLOBAL_Control
0x1800c6742  cmp     rcx, rax
0x1800c6745  jz      short loc_1800C6781
0x1800c6747  test    byte ptr [rcx+1Ch], 8
0x1800c674b  jz      short loc_1800C6781
0x1800c674d  cmp     byte ptr [rcx+19h], 2
0x1800c6751  jb      short loc_1800C6781
0x1800c6753  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c6758  lea     rcx, aPnewmap; "pNewmap"
0x1800c675f  mov     r9d, eax
0x1800c6762  mov     [rsp+68h+lpOverlapped], rcx
0x1800c6767  lea     edx, [rdi+1Fh]
0x1800c676a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6771  lea     r8, WPP_00f57cbcba22367f230f2d13c3b6dfe1_Traceguids
0x1800c6778  mov     rcx, [rcx+10h]
0x1800c677c  call    WPP_SF_Ds
0x1800c6781  mov     ebx, 80004003h
0x1800c6786  jmp     loc_1800C6999
0x1800c678b  mov     eax, [r9+0Ch]
0x1800c678f  mov     ecx, 48h ; 'H'; Size
0x1800c6794  inc     eax
0x1800c6796  sar     eax, 3
0x1800c6799  movzx   r15d, al
0x1800c679d  imul    r15d, [r9]
0x1800c67a1  imul    r15d, [r9+4]
0x1800c67a6  add     r15d, 48h ; 'H'
0x1800c67aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c67af  mov     rsi, rax
0x1800c67b2  test    rax, rax
0x1800c67b5  jnz     short loc_1800C680E
0x1800c67b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c67be  lea     rax, WPP_GLOBAL_Control
0x1800c67c5  cmp     rcx, rax
0x1800c67c8  jz      short loc_1800C6804
0x1800c67ca  test    byte ptr [rcx+1Ch], 8
0x1800c67ce  jz      short loc_1800C6804
0x1800c67d0  cmp     byte ptr [rcx+19h], 2
0x1800c67d4  jb      short loc_1800C6804
0x1800c67d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c67db  lea     rcx, aByte; "BYTE"
0x1800c67e2  mov     r9d, eax
0x1800c67e5  mov     [rsp+68h+lpOverlapped], rcx
0x1800c67ea  lea     edx, [rsi+20h]
0x1800c67ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c67f4  lea     r8, WPP_00f57cbcba22367f230f2d13c3b6dfe1_Traceguids
0x1800c67fb  mov     rcx, [rcx+10h]
0x1800c67ff  call    WPP_SF_Ds
0x1800c6804  mov     ebx, 8007000Eh
0x1800c6809  jmp     loc_1800C6999
0x1800c680e  xor     ebx, ebx
0x1800c6810  xor     edx, edx; Val
0x1800c6812  mov     rcx, rsi; void *
0x1800c6815  lea     r8d, [rbx+48h]; Size
0x1800c6819  call    memset_0
0x1800c681e  xor     eax, eax
0x1800c6820  mov     dword ptr [rsi], 62755453h
0x1800c6826  mov     [rsi+0Ch], ax
0x1800c682a  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c6832  mov     [rsi+8], r15d
0x1800c6836  lea     r8d, [rbx+48h]; nNumberOfBytesToWrite
0x1800c683a  mov     dword ptr [rsi+4], 6
0x1800c6841  mov     rdx, rsi; lpBuffer
0x1800c6844  mov     [rsi+10h], r14
0x1800c6848  mov     eax, [rdi+4]
0x1800c684b  mov     [rsi+18h], eax
0x1800c684e  mov     eax, [rdi]
0x1800c6850  mov     [rsi+1Ch], eax
0x1800c6853  mov     word ptr [rsi+20h], 20h ; ' '
0x1800c6859  mov     dword ptr [rsi+24h], 1
0x1800c6860  mov     eax, [rdi+0Ch]
0x1800c6863  inc     eax
0x1800c6865  mov     [rsp+68h+lpOverlapped], rbx; lpOverlapped
0x1800c686a  sar     eax, 3
0x1800c686d  movzx   ecx, al
0x1800c6870  imul    ecx, [rdi]
0x1800c6873  imul    ecx, [rdi+4]
0x1800c6877  mov     [rsi+2Ch], rbx
0x1800c687b  mov     [rsi+44h], ecx
0x1800c687e  mov     eax, [rdi+4]
0x1800c6881  mov     [rsi+38h], eax
0x1800c6884  mov     eax, [rdi]
0x1800c6886  mov     [rsi+34h], eax
0x1800c6889  mov     [rsi+28h], ebx
0x1800c688c  mov     [rsi+3Ch], ebx
0x1800c688f  mov     rcx, [rbp+60h]; hFile
0x1800c6893  call    cs:__imp_WriteFile
0x1800c6899  mov     r14d, 80070000h
0x1800c689f  test    eax, eax
0x1800c68a1  jnz     short loc_1800C68F0
0x1800c68a3  call    cs:__imp_GetLastError
0x1800c68a9  mov     ebx, eax
0x1800c68ab  test    eax, eax
0x1800c68ad  jle     short loc_1800C68B5
0x1800c68af  movzx   ebx, ax
0x1800c68b2  or      ebx, r14d
0x1800c68b5  test    ebx, ebx
0x1800c68b7  jns     short loc_1800C68F0
0x1800c68b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c68c0  lea     rax, WPP_GLOBAL_Control
0x1800c68c7  cmp     rcx, rax
0x1800c68ca  jz      loc_1800C6991
0x1800c68d0  test    byte ptr [rcx+1Ch], 8
0x1800c68d4  jz      loc_1800C6991
0x1800c68da  cmp     byte ptr [rcx+19h], 2
0x1800c68de  jb      loc_1800C6991
0x1800c68e4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c68e9  mov     edx, 21h ; '!'
0x1800c68ee  jmp     short loc_1800C6967
0x1800c68f0  mov     eax, [rdi+0Ch]
0x1800c68f3  lea     r9, [rsp+68h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800c68fb  mov     rdx, [rdi+18h]; lpBuffer
0x1800c68ff  inc     eax
0x1800c6901  mov     rcx, [rbp+60h]; hFile
0x1800c6905  sar     eax, 3
0x1800c6908  movzx   r8d, al
0x1800c690c  imul    r8d, [rdi]
0x1800c6910  mov     [rsp+68h+lpOverlapped], 0; lpOverlapped
0x1800c6919  imul    r8d, [rdi+4]; nNumberOfBytesToWrite
0x1800c691e  call    cs:__imp_WriteFile
0x1800c6924  test    eax, eax
0x1800c6926  jnz     short loc_1800C6991
0x1800c6928  call    cs:__imp_GetLastError
0x1800c692e  mov     ebx, eax
0x1800c6930  test    eax, eax
0x1800c6932  jle     short loc_1800C693A
0x1800c6934  movzx   ebx, ax
0x1800c6937  or      ebx, r14d
0x1800c693a  test    ebx, ebx
0x1800c693c  jns     short loc_1800C6991
0x1800c693e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6945  lea     rax, WPP_GLOBAL_Control
0x1800c694c  cmp     rcx, rax
0x1800c694f  jz      short loc_1800C6991
0x1800c6951  test    byte ptr [rcx+1Ch], 8
0x1800c6955  jz      short loc_1800C6991
0x1800c6957  cmp     byte ptr [rcx+19h], 2
0x1800c695b  jb      short loc_1800C6991
0x1800c695d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800c6962  mov     edx, 22h ; '"'
0x1800c6967  lea     rcx, aFailedToOpenFi; "failed to open file"
0x1800c696e  mov     [rsp+68h+var_40], ebx
0x1800c6972  mov     [rsp+68h+lpOverlapped], rcx
0x1800c6977  lea     r8, WPP_00f57cbcba22367f230f2d13c3b6dfe1_Traceguids
0x1800c697e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c6985  mov     r9d, eax
0x1800c6988  mov     rcx, [rcx+10h]
0x1800c698c  call    WPP_SF_DsD
0x1800c6991  mov     rcx, rsi; Block
0x1800c6994  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800c6999  mov     eax, ebx
0x1800c699b  add     rsp, 38h
0x1800c699f  pop     r15
0x1800c69a1  pop     r14
0x1800c69a3  pop     rdi
0x1800c69a4  pop     rsi
0x1800c69a5  pop     rbp
0x1800c69a6  pop     rbx
0x1800c69a7  retn
```
