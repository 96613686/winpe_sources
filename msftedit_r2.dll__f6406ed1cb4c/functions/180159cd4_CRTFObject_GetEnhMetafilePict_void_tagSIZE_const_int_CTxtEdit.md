# CRTFObject::GetEnhMetafilePict(void *,tagSIZE const &,int,CTxtEdit *)

- ea: `0x180159cd4`
- end: `0x180159ee0`
- name: `?GetEnhMetafilePict@CRTFObject@@AEAAHPEAXAEBUtagSIZE@@HPEAVCTxtEdit@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(CRTFObject *this, HENHMETAFILE, const struct tagSIZE *, int, struct CTxtEdit *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18015a674`
- `0x18015b7ac`

## callees

- `0x18000f430`
- `0x18004d8d0`
- `0x18008a47c`
- `0x1800ee9f8`
- `0x180159cd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180159e85`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180159e9e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180159e85`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180159e9e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180159d17`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180159d17`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180159e03`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180159e03`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180159e1a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180159e1a`
- `ext-ms-win-gdi-metafile-l1-1-1!GetWinMetaFileBits` at `0x180159de4`
- `ext-ms-win-gdi-metafile-l1-1-1!GetWinMetaFileBits` at `0x180159e56`
- `ext-ms-win-gdi-metafile-l1-1-1!GetWinMetaFileBits` at `0x180159de4`
- `ext-ms-win-gdi-metafile-l1-1-1!GetWinMetaFileBits` at `0x180159e56`
- `ext-ms-win-gdi-metafile-l1-1-1!GetEnhMetaFileHeader` at `0x180159d05`
- `ext-ms-win-gdi-metafile-l1-1-1!GetEnhMetaFileHeader` at `0x180159d38`
- `ext-ms-win-gdi-metafile-l1-1-1!GetEnhMetaFileHeader` at `0x180159d05`
- `ext-ms-win-gdi-metafile-l1-1-1!GetEnhMetaFileHeader` at `0x180159d38`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteEnhMetaFile` at `0x180159e6c`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteEnhMetaFile` at `0x180159e6c`
- `ext-ms-win-gdi-metafile-l1-1-0!GetEnhMetaFileBits` at `0x180159da8`
- `ext-ms-win-gdi-metafile-l1-1-0!GetEnhMetaFileBits` at `0x180159e3d`
- `ext-ms-win-gdi-metafile-l1-1-0!GetEnhMetaFileBits` at `0x180159da8`
- `ext-ms-win-gdi-metafile-l1-1-0!GetEnhMetaFileBits` at `0x180159e3d`

## pseudocode

```c
__int64 __fastcall CRTFObject::GetEnhMetafilePict(
        CRTFObject *this,
        HENHMETAFILE a2,
        const struct tagSIZE *a3,
        int a4,
        struct CTxtEdit *a5)
{
  HDC v7; // rbx
  unsigned int v9; // edi
  void *v10; // r15
  signed int EnhMetaFileHeader; // r14d
  struct tagENHMETAHEADER *v12; // rax
  __int16 *v13; // r12
  LONG cx; // ecx
  __int16 v15; // ax
  __int64 v16; // r11
  int v17; // ecx
  signed int WinMetaFileBits; // eax
  HDC hdcRef; // rax
  UINT v20; // r14d
  HGLOBAL v21; // rax
  BYTE *v22; // rax
  UINT v23; // eax
  void *v24; // rcx

  v7 = 0;
  *((_QWORD *)this + 13) = 0;
  v9 = 0;
  v10 = 0;
  EnhMetaFileHeader = GetEnhMetaFileHeader(a2, 0, 0);
  v12 = (struct tagENHMETAHEADER *)malloc(EnhMetaFileHeader);
  v13 = (__int16 *)v12;
  if ( v12 )
  {
    if ( !GetEnhMetaFileHeader(a2, EnhMetaFileHeader, v12) )
      goto LABEL_16;
    *((_WORD *)this + 1) = 0;
    cx = a3->cx;
    *((_DWORD *)this + 24) = v13[40];
    *((_DWORD *)this + 25) = v13[42];
    v15 = CW32System::MulDivFunc(cx, 72, 127);
    v17 = *(_DWORD *)(v16 + 4);
    *((_WORD *)this + 20) = v15;
    *((_WORD *)this + 21) = CW32System::MulDivFunc(v17, 72, 127);
    if ( a4 )
    {
      *((_WORD *)this + 1) = 8;
      hdcRef = CTxtEdit::TxGetDC(a5);
      v7 = hdcRef;
      if ( !hdcRef )
        goto LABEL_16;
      WinMetaFileBits = GetWinMetaFileBits(a2, 0, 0, 8, hdcRef);
    }
    else
    {
      WinMetaFileBits = GetEnhMetaFileBits(a2, 0, 0);
    }
    v20 = WinMetaFileBits;
    if ( WinMetaFileBits )
    {
      v21 = GlobalAlloc(0x42u, WinMetaFileBits);
      v10 = v21;
      if ( v21 )
      {
        v22 = (BYTE *)GlobalLock(v21);
        *((_QWORD *)this + 13) = v22;
        if ( v22 )
        {
          v23 = a4 ? GetWinMetaFileBits(a2, v20, v22, 8, v7) : GetEnhMetaFileBits(a2, v20, v22);
          if ( v23 )
          {
            *((_DWORD *)this + 28) = v23;
            if ( DeleteEnhMetaFile(a2) )
              v9 = 1;
          }
        }
      }
    }
LABEL_16:
    free(v13);
    if ( v9 )
      goto LABEL_21;
  }
  v24 = (void *)*((_QWORD *)this + 13);
  if ( v24 )
    free(v24);
  if ( v10 )
    CW32System::GlobalFree(v10);
LABEL_21:
  if ( v7 )
    CTxtEdit::TxReleaseDC(a5, v7);
  return v9;
}

```

## disassembly

```asm
0x180159cd4  mov     [rsp+arg_10], r8
0x180159cd9  push    rbx
0x180159cda  push    rbp
0x180159cdb  push    rsi
0x180159cdc  push    rdi
0x180159cdd  push    r12
0x180159cdf  push    r13
0x180159ce1  push    r14
0x180159ce3  push    r15
0x180159ce5  sub     rsp, 38h
0x180159ce9  mov     rsi, rdx
0x180159cec  mov     rbp, rcx
0x180159cef  xor     ebx, ebx
0x180159cf1  xor     r8d, r8d; lpEnhMetaHeader
0x180159cf4  mov     [rcx+68h], rbx
0x180159cf8  xor     edx, edx; nSize
0x180159cfa  mov     rcx, rsi; hemf
0x180159cfd  mov     r13d, r9d
0x180159d00  xor     edi, edi
0x180159d02  xor     r15d, r15d
0x180159d05  call    cs:__imp_GetEnhMetaFileHeader
0x180159d0c  nop     dword ptr [rax+rax+00h]
0x180159d11  movsxd  r14, eax
0x180159d14  mov     rcx, r14; Size
0x180159d17  call    cs:__imp_malloc
0x180159d1e  nop     dword ptr [rax+rax+00h]
0x180159d23  mov     r12, rax
0x180159d26  test    rax, rax
0x180159d29  jz      loc_180159E95
0x180159d2f  mov     r8, rax; lpEnhMetaHeader
0x180159d32  mov     edx, r14d; nSize
0x180159d35  mov     rcx, rsi; hemf
0x180159d38  call    cs:__imp_GetEnhMetaFileHeader
0x180159d3f  nop     dword ptr [rax+rax+00h]
0x180159d44  test    eax, eax
0x180159d46  jz      loc_180159E82
0x180159d4c  mov     r11, [rsp+78h+arg_10]
0x180159d54  lea     r14d, [rdi+48h]
0x180159d58  xor     eax, eax
0x180159d5a  lea     r8d, [rdi+7Fh]; int
0x180159d5e  mov     [rbp+2], ax
0x180159d62  mov     edx, r14d; int
0x180159d65  movsx   eax, word ptr [r12+50h]
0x180159d6b  mov     ecx, [r11]; int
0x180159d6e  mov     [rbp+60h], eax
0x180159d71  movsx   eax, word ptr [r12+54h]
0x180159d77  mov     [rbp+64h], eax
0x180159d7a  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180159d7f  mov     ecx, [r11+4]; int
0x180159d83  lea     r8d, [rdi+7Fh]; int
0x180159d87  mov     edx, r14d; int
0x180159d8a  mov     [rbp+28h], ax
0x180159d8e  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180159d93  mov     [rbp+2Ah], ax
0x180159d97  lea     r14d, [rdi+8]
0x180159d9b  test    r13d, r13d
0x180159d9e  jnz     short loc_180159DB6
0x180159da0  xor     r8d, r8d; lpData
0x180159da3  xor     edx, edx; nSize
0x180159da5  mov     rcx, rsi; hEMF
0x180159da8  call    cs:__imp_GetEnhMetaFileBits
0x180159daf  nop     dword ptr [rax+rax+00h]
0x180159db4  jmp     short loc_180159DF0
0x180159db6  mov     rcx, [rsp+78h+arg_20]; this
0x180159dbe  mov     [rbp+2], r14w
0x180159dc3  call    ?TxGetDC@CTxtEdit@@QEAAPEAUHDC__@@XZ; CTxtEdit::TxGetDC(void)
0x180159dc8  mov     rbx, rax
0x180159dcb  test    rax, rax
0x180159dce  jz      loc_180159E82
0x180159dd4  mov     r9d, r14d; iMapMode
0x180159dd7  mov     [rsp+78h+hdcRef], rax; hdcRef
0x180159ddc  xor     r8d, r8d; pData16
0x180159ddf  xor     edx, edx; cbData16
0x180159de1  mov     rcx, rsi; hemf
0x180159de4  call    cs:__imp_GetWinMetaFileBits
0x180159deb  nop     dword ptr [rax+rax+00h]
0x180159df0  mov     r14d, eax
0x180159df3  test    eax, eax
0x180159df5  jz      loc_180159E82
0x180159dfb  movsxd  rdx, eax; dwBytes
0x180159dfe  mov     ecx, 42h ; 'B'; uFlags
0x180159e03  call    cs:__imp_GlobalAlloc
0x180159e0a  nop     dword ptr [rax+rax+00h]
0x180159e0f  mov     r15, rax
0x180159e12  test    rax, rax
0x180159e15  jz      short loc_180159E82
0x180159e17  mov     rcx, rax; hMem
0x180159e1a  call    cs:__imp_GlobalLock
0x180159e21  nop     dword ptr [rax+rax+00h]
0x180159e26  mov     [rbp+68h], rax
0x180159e2a  test    rax, rax
0x180159e2d  jz      short loc_180159E82
0x180159e2f  mov     r8, rax; pData16
0x180159e32  mov     edx, r14d; cbData16
0x180159e35  mov     rcx, rsi; hemf
0x180159e38  test    r13d, r13d
0x180159e3b  jnz     short loc_180159E4B
0x180159e3d  call    cs:__imp_GetEnhMetaFileBits
0x180159e44  nop     dword ptr [rax+rax+00h]
0x180159e49  jmp     short loc_180159E62
0x180159e4b  mov     r9d, 8; iMapMode
0x180159e51  mov     [rsp+78h+hdcRef], rbx; hdcRef
0x180159e56  call    cs:__imp_GetWinMetaFileBits
0x180159e5d  nop     dword ptr [rax+rax+00h]
0x180159e62  test    eax, eax
0x180159e64  jz      short loc_180159E82
0x180159e66  mov     rcx, rsi; hmf
0x180159e69  mov     [rbp+70h], eax
0x180159e6c  call    cs:__imp_DeleteEnhMetaFile
0x180159e73  nop     dword ptr [rax+rax+00h]
0x180159e78  test    eax, eax
0x180159e7a  mov     ecx, 1
0x180159e7f  cmovnz  edi, ecx
0x180159e82  mov     rcx, r12; Block
0x180159e85  call    cs:__imp_free
0x180159e8c  nop     dword ptr [rax+rax+00h]
0x180159e91  test    edi, edi
0x180159e93  jnz     short loc_180159EB7
0x180159e95  mov     rcx, [rbp+68h]; Block
0x180159e99  test    rcx, rcx
0x180159e9c  jz      short loc_180159EAA
0x180159e9e  call    cs:__imp_free
0x180159ea5  nop     dword ptr [rax+rax+00h]
0x180159eaa  test    r15, r15
0x180159ead  jz      short loc_180159EB7
0x180159eaf  mov     rcx, r15; void *
0x180159eb2  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x180159eb7  test    rbx, rbx
0x180159eba  jz      short loc_180159ECC
0x180159ebc  mov     rcx, [rsp+78h+arg_20]; this
0x180159ec4  mov     rdx, rbx; HDC
0x180159ec7  call    ?TxReleaseDC@CTxtEdit@@QEAAHPEAUHDC__@@@Z; CTxtEdit::TxReleaseDC(HDC__ *)
0x180159ecc  mov     eax, edi
0x180159ece  add     rsp, 38h
0x180159ed2  pop     r15
0x180159ed4  pop     r14
0x180159ed6  pop     r13
0x180159ed8  pop     r12
0x180159eda  pop     rdi
0x180159edb  pop     rsi
0x180159edc  pop     rbp
0x180159edd  pop     rbx
0x180159ede  retn
```
