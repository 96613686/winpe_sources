# pmdcAllocMDC(void *,ushort const *,ushort const *,void *)

- ea: `0x180029ee4`
- end: `0x18002a280`
- name: `?pmdcAllocMDC@@YAPEAVMDC@@PEAXPEBG10@Z`
- size: `924`
- prototype: `struct MDC *__fastcall(void *, LPCWSTR lpFileName, const unsigned __int16 *, EMFSpoolData *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180029e20`
- `0x18004c018`

## callees

- `0x180023110`
- `0x180024010`
- `0x180029ee4`
- `0x18002a434`
- `0x18002a540`
- `0x18002b198`
- `0x180050ba0`
- `0x18007ac50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029f2d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029fc4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029fde`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029f2d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029fc4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180029fde`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002a18e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18002a18e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a1d1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002a1d1`
- `GDI32!GdiSetLastError` at `0x18002a1f3`
- `GDI32!GdiSetLastError` at `0x18002a1f3`

## pseudocode

```c
struct MDC *__fastcall pmdcAllocMDC(HDC a1, LPCWSTR lpFileName, const unsigned __int16 *a3, EMFSpoolData *this)
{
  __int64 v8; // r14
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  _QWORD *v11; // rax
  HLOCAL v12; // rax
  bool v13; // zf
  _QWORD *v14; // rax
  __int64 v15; // rax
  unsigned int v16; // edx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned int v21; // edi
  MRMETAFILE *v22; // rax
  MRMETAFILE *v23; // rsi
  int v24; // eax
  int PixelFormat; // eax
  int i; // ecx
  DWORD FullPathNameW; // eax
  HANDLE FileW; // rax
  char *v30; // rax
  LPWSTR FilePart; // [rsp+40h] [rbp-88h] BYREF
  tagPIXELFORMATDESCRIPTOR ppfd; // [rsp+48h] [rbp-80h] BYREF

  v8 = 0;
  if ( !gbDisableMetaFiles )
  {
    v9 = LocalAlloc(0, 0x308u);
    v10 = v9;
    if ( v9 )
    {
      *(_DWORD *)v9 = 4408397;
      v9[1] = -1;
      v9[2] = 0;
      v9[3] = 0x4000;
      *((_DWORD *)v9 + 8) = 0;
      v9[19] = 0;
      v9[20] = 0;
      v9[21] = 0;
      *((struct _RECTL *)v9 + 11) = rclInfinity;
      *((struct _RECTL *)v9 + 12) = rclInfinity;
      v9[95] = a1;
      v9[26] = 0;
      v11 = v9 + 93;
      v11[1] = v11;
      *v11 = v11;
      if ( lpFileName )
      {
        FilePart = 0;
        FullPathNameW = GetFullPathNameW(lpFileName, 0x104u, (LPWSTR)v10 + 108, &FilePart);
        if ( !FullPathNameW )
          goto LABEL_15;
        if ( FullPathNameW > 0x104 )
        {
          GdiSetLastError(206);
          goto LABEL_15;
        }
        *((_WORD *)v10 + FullPathNameW + 108) = 0;
        FileW = CreateFileW((LPCWSTR)v10 + 108, 0x40000000u, 0, 0, 2u, 0x80u, 0);
        v10[1] = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
LABEL_15:
          *((_DWORD *)v10 + 8) |= 2u;
          vFreeMDC((struct MDC *)v10);
          return (struct MDC *)v8;
        }
        *((_DWORD *)v10 + 8) |= 1u;
      }
      if ( this )
      {
        *((_DWORD *)v10 + 8) |= 0x80u;
        v10[2] = this;
        v13 = (unsigned int)EMFSpoolData::GetEMFData(this, (struct MDC *)v10) == 0;
      }
      else
      {
        v12 = LocalAlloc(0, 0x4000u);
        v10[2] = v12;
        v13 = v12 == 0;
      }
      if ( v13 )
        goto LABEL_15;
      v14 = LocalAlloc(0, 0x6000u);
      v10[19] = v14;
      if ( !v14 )
        goto LABEL_15;
      *v14 = 0;
      v15 = v10[19];
      v16 = 1;
      *(_DWORD *)(v15 + 8) = -1;
      *(_QWORD *)(v15 + 16) = 0;
      *((_DWORD *)v10 + 37) = 1;
      *((_DWORD *)v10 + 36) = 1024;
      do
      {
        v17 = v16++;
        v18 = 3 * v17;
        *(_QWORD *)(v10[19] + 8 * v18) = 0;
        v19 = v10[19];
        *(_DWORD *)(v19 + 8 * v18 + 8) = v16;
        *(_QWORD *)(v19 + 8 * v18 + 16) = 0;
      }
      while ( v16 < 0x400 );
      v20 = v10[19];
      *(_DWORD *)(v20 + 8 * v18 + 8) = -1;
      *(_QWORD *)(v20 + 8 * v18 + 16) = 0;
      if ( a3 )
      {
        for ( i = 0; a3[i] || a3[i + 1]; ++i )
          ;
        v21 = i + 2;
        if ( (unsigned int)(i + 2) >= 0x7FFFFFC8 )
          goto LABEL_15;
      }
      else
      {
        v21 = 0;
      }
      v22 = (MRMETAFILE *)MDC::pvNewRecord((MDC *)v10, ((2 * v21 + 3) & 0xFFFFFFFC) + 108);
      v23 = v22;
      if ( v22 )
      {
        MRMETAFILE::vInit(v22, a1, a3, v21);
        v24 = *((_DWORD *)v10 + 7);
        *(_OWORD *)((char *)v10 + 36) = *(_OWORD *)v23;
        *(_OWORD *)((char *)v10 + 52) = *((_OWORD *)v23 + 1);
        *(_OWORD *)((char *)v10 + 68) = *((_OWORD *)v23 + 2);
        *(_OWORD *)((char *)v10 + 84) = *((_OWORD *)v23 + 3);
        *(_OWORD *)((char *)v10 + 100) = *((_OWORD *)v23 + 4);
        *(_OWORD *)((char *)v10 + 116) = *((_OWORD *)v23 + 5);
        *((_OWORD *)v10 + 8) = *(_OWORD *)((char *)v23 + 92);
        *((_DWORD *)v10 + 7) = *((_DWORD *)v23 + 1) + v24;
        *((_DWORD *)v10 + 21) += *((_DWORD *)v23 + 1);
        ++*((_DWORD *)v10 + 22);
        PixelFormat = GetPixelFormat(a1);
        if ( !PixelFormat )
          return (struct MDC *)v10;
        memset(&ppfd, 0, sizeof(ppfd));
        if ( DescribePixelFormat(a1, PixelFormat, 0x28u, &ppfd) )
        {
          v30 = (char *)MDC::pvNewRecord((MDC *)v10, 0x30u);
          if ( v30 )
          {
            *(_DWORD *)v30 = 104;
            *(tagPIXELFORMATDESCRIPTOR *)(v30 + 8) = ppfd;
            *((_DWORD *)v10 + 7) += *((_DWORD *)v30 + 1);
            *((_DWORD *)v10 + 21) += *((_DWORD *)v30 + 1);
            ++*((_DWORD *)v10 + 22);
            return (struct MDC *)v10;
          }
        }
      }
      goto LABEL_15;
    }
  }
  return (struct MDC *)v8;
}

```

## disassembly

```asm
0x180029ee4  push    rbx
0x180029ee6  push    rbp
0x180029ee7  push    rsi
0x180029ee8  push    rdi
0x180029ee9  push    r12
0x180029eeb  push    r13
0x180029eed  push    r14
0x180029eef  push    r15
0x180029ef1  sub     rsp, 88h
0x180029ef8  mov     rax, cs:__security_cookie
0x180029eff  xor     rax, rsp
0x180029f02  mov     [rsp+0C8h+var_58], rax
0x180029f07  xor     r13d, r13d
0x180029f0a  mov     rdi, r9
0x180029f0d  cmp     cs:gbDisableMetaFiles, r13d
0x180029f14  mov     rbp, r8
0x180029f17  mov     rsi, rdx
0x180029f1a  mov     r12, rcx
0x180029f1d  mov     r14d, r13d
0x180029f20  jnz     loc_18002A106
0x180029f26  mov     edx, 308h; uBytes
0x180029f2b  xor     ecx, ecx; uFlags
0x180029f2d  call    cs:__imp_LocalAlloc
0x180029f33  mov     rbx, rax
0x180029f36  test    rax, rax
0x180029f39  jz      loc_18002A106
0x180029f3f  mov     dword ptr [rax], 43444Dh
0x180029f45  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x180029f4d  mov     [rax+10h], r13
0x180029f51  mov     qword ptr [rax+18h], 4000h
0x180029f59  mov     [rax+20h], r13d
0x180029f5d  mov     [rax+98h], r13
0x180029f64  mov     [rax+0A0h], r13
0x180029f6b  mov     [rax+0A8h], r13
0x180029f72  movups  xmm0, cs:?rclInfinity@@3U_RECTL@@A; _RECTL rclInfinity
0x180029f79  movdqu  xmmword ptr [rax+0B0h], xmm0
0x180029f81  movups  xmm1, cs:?rclInfinity@@3U_RECTL@@A; _RECTL rclInfinity
0x180029f88  movdqu  xmmword ptr [rax+0C0h], xmm1
0x180029f90  mov     [rax+2F8h], r12
0x180029f97  mov     [rax+0D0h], r13
0x180029f9e  add     rax, 2E8h
0x180029fa4  mov     [rax+8], rax
0x180029fa8  mov     [rax], rax
0x180029fab  test    rsi, rsi
0x180029fae  jnz     loc_18002A172
0x180029fb4  test    rdi, rdi
0x180029fb7  jnz     loc_18002A12A
0x180029fbd  mov     edx, 4000h; uBytes
0x180029fc2  xor     ecx, ecx; uFlags
0x180029fc4  call    cs:__imp_LocalAlloc
0x180029fca  mov     [rbx+10h], rax
0x180029fce  test    rax, rax
0x180029fd1  jz      loc_18002A0FA
0x180029fd7  mov     edx, 6000h; uBytes
0x180029fdc  xor     ecx, ecx; uFlags
0x180029fde  call    cs:__imp_LocalAlloc
0x180029fe4  mov     [rbx+98h], rax
0x180029feb  test    rax, rax
0x180029fee  jz      loc_18002A0FA
0x180029ff4  mov     [rax], r13
0x180029ff7  or      r8d, 0FFFFFFFFh
0x180029ffb  mov     rax, [rbx+98h]
0x18002a002  mov     r9d, 400h
0x18002a008  mov     edx, 1
0x18002a00d  mov     [rax+8], r8d
0x18002a011  mov     [rax+10h], r13
0x18002a015  mov     dword ptr [rbx+94h], 1
0x18002a01f  mov     [rbx+90h], r9d
0x18002a026  mov     eax, edx
0x18002a028  inc     edx
0x18002a02a  lea     rcx, [rax+rax*2]
0x18002a02e  mov     rax, [rbx+98h]
0x18002a035  mov     [rax+rcx*8], r13
0x18002a039  mov     rax, [rbx+98h]
0x18002a040  mov     [rax+rcx*8+8], edx
0x18002a044  mov     [rax+rcx*8+10h], r13
0x18002a049  cmp     edx, r9d
0x18002a04c  jb      short loc_18002A026
0x18002a04e  mov     rax, [rbx+98h]
0x18002a055  mov     [rax+rcx*8+8], r8d
0x18002a05a  mov     [rax+rcx*8+10h], r13
0x18002a05f  test    rbp, rbp
0x18002a062  jnz     loc_18002A145
0x18002a068  mov     edi, r13d
0x18002a06b  lea     edx, ds:3[rdi*2]
0x18002a072  mov     rcx, rbx; this
0x18002a075  and     edx, 0FFFFFFFCh
0x18002a078  add     edx, 6Ch ; 'l'; unsigned int
0x18002a07b  call    ?pvNewRecord@MDC@@QEAAPEAXK@Z; MDC::pvNewRecord(ulong)
0x18002a080  mov     rsi, rax
0x18002a083  test    rax, rax
0x18002a086  jz      short loc_18002A0FA
0x18002a088  mov     r9d, edi; unsigned int
0x18002a08b  mov     r8, rbp; unsigned __int16 *
0x18002a08e  mov     rdx, r12; void *
0x18002a091  mov     rcx, rax; this
0x18002a094  call    ?vInit@MRMETAFILE@@QEAAXPEAXPEBGI@Z; MRMETAFILE::vInit(void *,ushort const *,uint)
0x18002a099  movups  xmm0, xmmword ptr [rsi]
0x18002a09c  mov     eax, [rbx+1Ch]
0x18002a09f  mov     rcx, r12; hdc
0x18002a0a2  movups  xmmword ptr [rbx+24h], xmm0
0x18002a0a6  movups  xmm1, xmmword ptr [rsi+10h]
0x18002a0aa  movups  xmmword ptr [rbx+34h], xmm1
0x18002a0ae  movups  xmm0, xmmword ptr [rsi+20h]
0x18002a0b2  movups  xmmword ptr [rbx+44h], xmm0
0x18002a0b6  movups  xmm1, xmmword ptr [rsi+30h]
0x18002a0ba  movups  xmmword ptr [rbx+54h], xmm1
0x18002a0be  movups  xmm0, xmmword ptr [rsi+40h]
0x18002a0c2  movups  xmmword ptr [rbx+64h], xmm0
0x18002a0c6  movups  xmm1, xmmword ptr [rsi+50h]
0x18002a0ca  movups  xmmword ptr [rbx+74h], xmm1
0x18002a0ce  movups  xmm0, xmmword ptr [rsi+5Ch]
0x18002a0d2  movups  xmmword ptr [rbx+80h], xmm0
0x18002a0d9  add     eax, [rsi+4]
0x18002a0dc  mov     [rbx+1Ch], eax
0x18002a0df  mov     eax, [rsi+4]
0x18002a0e2  add     [rbx+54h], eax
0x18002a0e5  inc     dword ptr [rbx+58h]
0x18002a0e8  call    GetPixelFormat
0x18002a0ed  test    eax, eax
0x18002a0ef  jnz     loc_18002A1FE
0x18002a0f5  mov     r14, rbx
0x18002a0f8  jmp     short loc_18002A106
0x18002a0fa  or      dword ptr [rbx+20h], 2
0x18002a0fe  mov     rcx, rbx; this
0x18002a101  call    ?vFreeMDC@@YAXPEAVMDC@@@Z; vFreeMDC(MDC *)
0x18002a106  mov     rax, r14
0x18002a109  mov     rcx, [rsp+0C8h+var_58]
0x18002a10e  xor     rcx, rsp; StackCookie
0x18002a111  call    __security_check_cookie
0x18002a116  add     rsp, 88h
0x18002a11d  pop     r15
0x18002a11f  pop     r14
0x18002a121  pop     r13
0x18002a123  pop     r12
0x18002a125  pop     rdi
0x18002a126  pop     rsi
0x18002a127  pop     rbp
0x18002a128  pop     rbx
0x18002a129  retn
0x18002a12a  bts     dword ptr [rbx+20h], 7
0x18002a12f  mov     rdx, rbx; struct MDC *
0x18002a132  mov     rcx, rdi; this
0x18002a135  mov     [rbx+10h], rdi
0x18002a139  call    ?GetEMFData@EMFSpoolData@@QEAAHPEAVMDC@@@Z; EMFSpoolData::GetEMFData(MDC *)
0x18002a13e  test    eax, eax
0x18002a140  jmp     loc_180029FD1
0x18002a145  mov     ecx, r13d
0x18002a148  mov     eax, ecx
0x18002a14a  lea     edx, [rcx+1]
0x18002a14d  cmp     [rbp+rax*2+0], r13w
0x18002a153  jz      short loc_18002A159
0x18002a155  mov     ecx, edx
0x18002a157  jmp     short loc_18002A148
0x18002a159  cmp     [rbp+rdx*2+0], r13w
0x18002a15f  jnz     short loc_18002A155
0x18002a161  lea     edi, [rcx+2]
0x18002a164  cmp     edi, 7FFFFFC8h
0x18002a16a  jb      loc_18002A06B
0x18002a170  jmp     short loc_18002A0FA
0x18002a172  lea     r15, [rbx+0D8h]
0x18002a179  mov     [rsp+0C8h+FilePart], r13
0x18002a17e  mov     r8, r15; lpBuffer
0x18002a181  lea     r9, [rsp+0C8h+FilePart]; lpFilePart
0x18002a186  mov     edx, 104h; nBufferLength
0x18002a18b  mov     rcx, rsi; lpFileName
0x18002a18e  call    cs:__imp_GetFullPathNameW
0x18002a194  test    eax, eax
0x18002a196  jz      loc_18002A0FA
0x18002a19c  cmp     eax, 104h
0x18002a1a1  ja      short loc_18002A1EE
0x18002a1a3  mov     ecx, eax
0x18002a1a5  xor     r9d, r9d; lpSecurityAttributes
0x18002a1a8  mov     [rsp+0C8h+hTemplateFile], r13; hTemplateFile
0x18002a1ad  xor     r8d, r8d; dwShareMode
0x18002a1b0  mov     [rsp+0C8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002a1b8  mov     edx, 40000000h; dwDesiredAccess
0x18002a1bd  mov     [rsp+0C8h+dwCreationDisposition], 2; dwCreationDisposition
0x18002a1c5  mov     [rbx+rcx*2+0D8h], r13w
0x18002a1ce  mov     rcx, r15; lpFileName
0x18002a1d1  call    cs:__imp_CreateFileW
0x18002a1d7  mov     [rbx+8], rax
0x18002a1db  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a1df  jz      loc_18002A0FA
0x18002a1e5  or      dword ptr [rbx+20h], 1
0x18002a1e9  jmp     loc_180029FB4
0x18002a1ee  mov     ecx, 0CEh
0x18002a1f3  call    cs:__imp_GdiSetLastError
0x18002a1f9  jmp     loc_18002A0FA
0x18002a1fe  xor     ecx, ecx
0x18002a200  lea     r9, [rsp+0C8h+ppfd]; ppfd
0x18002a205  xorps   xmm0, xmm0
0x18002a208  mov     qword ptr [rsp+0C8h+ppfd.dwVisibleMask], rcx
0x18002a20d  mov     edx, eax; iPixelFormat
0x18002a20f  movups  xmmword ptr [rsp+0C8h+ppfd.nSize], xmm0
0x18002a214  lea     r8d, [rcx+28h]; nBytes
0x18002a218  mov     rcx, r12; hdc
0x18002a21b  movups  xmmword ptr [rsp+0C8h+ppfd.cAlphaBits], xmm0
0x18002a220  call    DescribePixelFormat
0x18002a225  test    eax, eax
0x18002a227  jz      loc_18002A0FA
0x18002a22d  mov     edx, 30h ; '0'; unsigned int
0x18002a232  mov     rcx, rbx; this
0x18002a235  call    ?pvNewRecord@MDC@@QEAAPEAXK@Z; MDC::pvNewRecord(ulong)
0x18002a23a  mov     rcx, rax
0x18002a23d  test    rax, rax
0x18002a240  jz      loc_18002A0FA
0x18002a246  mov     dword ptr [rax], 68h ; 'h'
0x18002a24c  movups  xmm0, xmmword ptr [rsp+0C8h+ppfd.nSize]
0x18002a251  movups  xmmword ptr [rax+8], xmm0
0x18002a255  movups  xmm1, xmmword ptr [rsp+0C8h+ppfd.cAlphaBits]
0x18002a25a  movups  xmmword ptr [rax+18h], xmm1
0x18002a25e  movsd   xmm0, qword ptr [rsp+0C8h+ppfd.dwVisibleMask]
0x18002a264  movsd   qword ptr [rax+28h], xmm0
0x18002a269  mov     eax, [rbx+1Ch]
0x18002a26c  add     eax, [rcx+4]
0x18002a26f  mov     [rbx+1Ch], eax
0x18002a272  mov     eax, [rcx+4]
0x18002a275  add     [rbx+54h], eax
0x18002a278  inc     dword ptr [rbx+58h]
0x18002a27b  jmp     loc_18002A0F5
```
