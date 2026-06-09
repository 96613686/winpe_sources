# pmdcAllocMDC(void *,ushort const *,ushort const *,void *)

- ea: `0x180033728`
- end: `0x180033ae9`
- name: `?pmdcAllocMDC@@YAPEAVMDC@@PEAXPEBG10@Z`
- size: `961`
- prototype: `struct MDC *__fastcall(void *, LPCWSTR lpFileName, const unsigned __int16 *, EMFSpoolData *this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x180033650`
- `0x180052060`

## callees

- `0x18002c048`
- `0x18002cfe8`
- `0x180033728`
- `0x180033b90`
- `0x180033cc0`
- `0x18003500c`
- `0x180056640`
- `0x18007f800`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033771`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003380e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003382e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180033771`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003380e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003382e`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800339e5`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800339e5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033a2e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033a2e`
- `GDI32!GdiSetLastError` at `0x180033a56`
- `GDI32!GdiSetLastError` at `0x180033a56`

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
0x180033728  push    rbx
0x18003372a  push    rbp
0x18003372b  push    rsi
0x18003372c  push    rdi
0x18003372d  push    r12
0x18003372f  push    r13
0x180033731  push    r14
0x180033733  push    r15
0x180033735  sub     rsp, 88h
0x18003373c  mov     rax, cs:__security_cookie
0x180033743  xor     rax, rsp
0x180033746  mov     [rsp+0C8h+var_58], rax
0x18003374b  xor     r13d, r13d
0x18003374e  mov     rdi, r9
0x180033751  cmp     cs:gbDisableMetaFiles, r13d
0x180033758  mov     rbp, r8
0x18003375b  mov     rsi, rdx
0x18003375e  mov     r12, rcx
0x180033761  mov     r14d, r13d
0x180033764  jnz     loc_18003395C
0x18003376a  mov     edx, 308h; uBytes
0x18003376f  xor     ecx, ecx; uFlags
0x180033771  call    cs:__imp_LocalAlloc
0x180033778  nop     dword ptr [rax+rax+00h]
0x18003377d  mov     rbx, rax
0x180033780  test    rax, rax
0x180033783  jz      loc_18003395C
0x180033789  mov     dword ptr [rax], 43444Dh
0x18003378f  mov     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x180033797  mov     [rax+10h], r13
0x18003379b  mov     qword ptr [rax+18h], 4000h
0x1800337a3  mov     [rax+20h], r13d
0x1800337a7  mov     [rax+98h], r13
0x1800337ae  mov     [rax+0A0h], r13
0x1800337b5  mov     [rax+0A8h], r13
0x1800337bc  movups  xmm0, cs:?rclInfinity@@3U_RECTL@@A; _RECTL rclInfinity
0x1800337c3  movdqu  xmmword ptr [rax+0B0h], xmm0
0x1800337cb  movups  xmm1, cs:?rclInfinity@@3U_RECTL@@A; _RECTL rclInfinity
0x1800337d2  movdqu  xmmword ptr [rax+0C0h], xmm1
0x1800337da  mov     [rax+2F8h], r12
0x1800337e1  mov     [rax+0D0h], r13
0x1800337e8  add     rax, 2E8h
0x1800337ee  mov     [rax+8], rax
0x1800337f2  mov     [rax], rax
0x1800337f5  test    rsi, rsi
0x1800337f8  jnz     loc_1800339C9
0x1800337fe  test    rdi, rdi
0x180033801  jnz     loc_180033981
0x180033807  mov     edx, 4000h; uBytes
0x18003380c  xor     ecx, ecx; uFlags
0x18003380e  call    cs:__imp_LocalAlloc
0x180033815  nop     dword ptr [rax+rax+00h]
0x18003381a  mov     [rbx+10h], rax
0x18003381e  test    rax, rax
0x180033821  jz      loc_180033950
0x180033827  mov     edx, 6000h; uBytes
0x18003382c  xor     ecx, ecx; uFlags
0x18003382e  call    cs:__imp_LocalAlloc
0x180033835  nop     dword ptr [rax+rax+00h]
0x18003383a  mov     [rbx+98h], rax
0x180033841  test    rax, rax
0x180033844  jz      loc_180033950
0x18003384a  mov     [rax], r13
0x18003384d  or      r8d, 0FFFFFFFFh
0x180033851  mov     rax, [rbx+98h]
0x180033858  mov     r9d, 400h
0x18003385e  mov     edx, 1
0x180033863  mov     [rax+8], r8d
0x180033867  mov     [rax+10h], r13
0x18003386b  mov     dword ptr [rbx+94h], 1
0x180033875  mov     [rbx+90h], r9d
0x18003387c  mov     eax, edx
0x18003387e  inc     edx
0x180033880  lea     rcx, [rax+rax*2]
0x180033884  mov     rax, [rbx+98h]
0x18003388b  mov     [rax+rcx*8], r13
0x18003388f  mov     rax, [rbx+98h]
0x180033896  mov     [rax+rcx*8+8], edx
0x18003389a  mov     [rax+rcx*8+10h], r13
0x18003389f  cmp     edx, r9d
0x1800338a2  jb      short loc_18003387C
0x1800338a4  mov     rax, [rbx+98h]
0x1800338ab  mov     [rax+rcx*8+8], r8d
0x1800338b0  mov     [rax+rcx*8+10h], r13
0x1800338b5  test    rbp, rbp
0x1800338b8  jnz     loc_18003399C
0x1800338be  mov     edi, r13d
0x1800338c1  lea     edx, ds:3[rdi*2]
0x1800338c8  mov     rcx, rbx; this
0x1800338cb  and     edx, 0FFFFFFFCh
0x1800338ce  add     edx, 6Ch ; 'l'; unsigned int
0x1800338d1  call    ?pvNewRecord@MDC@@QEAAPEAXK@Z; MDC::pvNewRecord(ulong)
0x1800338d6  mov     rsi, rax
0x1800338d9  test    rax, rax
0x1800338dc  jz      short loc_180033950
0x1800338de  mov     r9d, edi; unsigned int
0x1800338e1  mov     r8, rbp; unsigned __int16 *
0x1800338e4  mov     rdx, r12; void *
0x1800338e7  mov     rcx, rax; this
0x1800338ea  call    ?vInit@MRMETAFILE@@QEAAXPEAXPEBGI@Z; MRMETAFILE::vInit(void *,ushort const *,uint)
0x1800338ef  movups  xmm0, xmmword ptr [rsi]
0x1800338f2  mov     eax, [rbx+1Ch]
0x1800338f5  mov     rcx, r12; hdc
0x1800338f8  movups  xmmword ptr [rbx+24h], xmm0
0x1800338fc  movups  xmm1, xmmword ptr [rsi+10h]
0x180033900  movups  xmmword ptr [rbx+34h], xmm1
0x180033904  movups  xmm0, xmmword ptr [rsi+20h]
0x180033908  movups  xmmword ptr [rbx+44h], xmm0
0x18003390c  movups  xmm1, xmmword ptr [rsi+30h]
0x180033910  movups  xmmword ptr [rbx+54h], xmm1
0x180033914  movups  xmm0, xmmword ptr [rsi+40h]
0x180033918  movups  xmmword ptr [rbx+64h], xmm0
0x18003391c  movups  xmm1, xmmword ptr [rsi+50h]
0x180033920  movups  xmmword ptr [rbx+74h], xmm1
0x180033924  movups  xmm0, xmmword ptr [rsi+5Ch]
0x180033928  movups  xmmword ptr [rbx+80h], xmm0
0x18003392f  add     eax, [rsi+4]
0x180033932  mov     [rbx+1Ch], eax
0x180033935  mov     eax, [rsi+4]
0x180033938  add     [rbx+54h], eax
0x18003393b  inc     dword ptr [rbx+58h]
0x18003393e  call    GetPixelFormat
0x180033943  test    eax, eax
0x180033945  jnz     loc_180033A67
0x18003394b  mov     r14, rbx
0x18003394e  jmp     short loc_18003395C
0x180033950  or      dword ptr [rbx+20h], 2
0x180033954  mov     rcx, rbx; this
0x180033957  call    ?vFreeMDC@@YAXPEAVMDC@@@Z; vFreeMDC(MDC *)
0x18003395c  mov     rax, r14
0x18003395f  mov     rcx, [rsp+0C8h+var_58]
0x180033964  xor     rcx, rsp; StackCookie
0x180033967  call    __security_check_cookie
0x18003396c  add     rsp, 88h
0x180033973  pop     r15
0x180033975  pop     r14
0x180033977  pop     r13
0x180033979  pop     r12
0x18003397b  pop     rdi
0x18003397c  pop     rsi
0x18003397d  pop     rbp
0x18003397e  pop     rbx
0x18003397f  retn
0x180033981  bts     dword ptr [rbx+20h], 7
0x180033986  mov     rdx, rbx; struct MDC *
0x180033989  mov     rcx, rdi; this
0x18003398c  mov     [rbx+10h], rdi
0x180033990  call    ?GetEMFData@EMFSpoolData@@QEAAHPEAVMDC@@@Z; EMFSpoolData::GetEMFData(MDC *)
0x180033995  test    eax, eax
0x180033997  jmp     loc_180033821
0x18003399c  mov     ecx, r13d
0x18003399f  mov     eax, ecx
0x1800339a1  lea     edx, [rcx+1]
0x1800339a4  cmp     [rbp+rax*2+0], r13w
0x1800339aa  jz      short loc_1800339B0
0x1800339ac  mov     ecx, edx
0x1800339ae  jmp     short loc_18003399F
0x1800339b0  cmp     [rbp+rdx*2+0], r13w
0x1800339b6  jnz     short loc_1800339AC
0x1800339b8  lea     edi, [rcx+2]
0x1800339bb  cmp     edi, 7FFFFFC8h
0x1800339c1  jb      loc_1800338C1
0x1800339c7  jmp     short loc_180033950
0x1800339c9  lea     r15, [rbx+0D8h]
0x1800339d0  mov     [rsp+0C8h+FilePart], r13
0x1800339d5  mov     r8, r15; lpBuffer
0x1800339d8  lea     r9, [rsp+0C8h+FilePart]; lpFilePart
0x1800339dd  mov     edx, 104h; nBufferLength
0x1800339e2  mov     rcx, rsi; lpFileName
0x1800339e5  call    cs:__imp_GetFullPathNameW
0x1800339ec  nop     dword ptr [rax+rax+00h]
0x1800339f1  test    eax, eax
0x1800339f3  jz      loc_180033950
0x1800339f9  cmp     eax, 104h
0x1800339fe  ja      short loc_180033A51
0x180033a00  mov     ecx, eax
0x180033a02  xor     r9d, r9d; lpSecurityAttributes
0x180033a05  mov     [rsp+0C8h+hTemplateFile], r13; hTemplateFile
0x180033a0a  xor     r8d, r8d; dwShareMode
0x180033a0d  mov     [rsp+0C8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180033a15  mov     edx, 40000000h; dwDesiredAccess
0x180033a1a  mov     [rsp+0C8h+dwCreationDisposition], 2; dwCreationDisposition
0x180033a22  mov     [rbx+rcx*2+0D8h], r13w
0x180033a2b  mov     rcx, r15; lpFileName
0x180033a2e  call    cs:__imp_CreateFileW
0x180033a35  nop     dword ptr [rax+rax+00h]
0x180033a3a  mov     [rbx+8], rax
0x180033a3e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180033a42  jz      loc_180033950
0x180033a48  or      dword ptr [rbx+20h], 1
0x180033a4c  jmp     loc_1800337FE
0x180033a51  mov     ecx, 0CEh
0x180033a56  call    cs:__imp_GdiSetLastError
0x180033a5d  nop     dword ptr [rax+rax+00h]
0x180033a62  jmp     loc_180033950
0x180033a67  xor     ecx, ecx
0x180033a69  lea     r9, [rsp+0C8h+ppfd]; ppfd
0x180033a6e  xorps   xmm0, xmm0
0x180033a71  mov     qword ptr [rsp+0C8h+ppfd.dwVisibleMask], rcx
0x180033a76  mov     edx, eax; iPixelFormat
0x180033a78  movups  xmmword ptr [rsp+0C8h+ppfd.nSize], xmm0
0x180033a7d  lea     r8d, [rcx+28h]; nBytes
0x180033a81  mov     rcx, r12; hdc
0x180033a84  movups  xmmword ptr [rsp+0C8h+ppfd.cAlphaBits], xmm0
0x180033a89  call    DescribePixelFormat
0x180033a8e  test    eax, eax
0x180033a90  jz      loc_180033950
0x180033a96  mov     edx, 30h ; '0'; unsigned int
0x180033a9b  mov     rcx, rbx; this
0x180033a9e  call    ?pvNewRecord@MDC@@QEAAPEAXK@Z; MDC::pvNewRecord(ulong)
0x180033aa3  mov     rcx, rax
0x180033aa6  test    rax, rax
0x180033aa9  jz      loc_180033950
0x180033aaf  mov     dword ptr [rax], 68h ; 'h'
0x180033ab5  movups  xmm0, xmmword ptr [rsp+0C8h+ppfd.nSize]
0x180033aba  movups  xmmword ptr [rax+8], xmm0
0x180033abe  movups  xmm1, xmmword ptr [rsp+0C8h+ppfd.cAlphaBits]
0x180033ac3  movups  xmmword ptr [rax+18h], xmm1
0x180033ac7  movsd   xmm0, qword ptr [rsp+0C8h+ppfd.dwVisibleMask]
0x180033acd  movsd   qword ptr [rax+28h], xmm0
0x180033ad2  mov     eax, [rbx+1Ch]
0x180033ad5  add     eax, [rcx+4]
0x180033ad8  mov     [rbx+1Ch], eax
0x180033adb  mov     eax, [rcx+4]
0x180033ade  add     [rbx+54h], eax
0x180033ae1  inc     dword ptr [rbx+58h]
0x180033ae4  jmp     loc_18003394B
```
