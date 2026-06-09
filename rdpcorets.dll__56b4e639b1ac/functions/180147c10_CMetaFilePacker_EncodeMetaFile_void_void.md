# CMetaFilePacker::EncodeMetaFile(void * *,void *)

- ea: `0x180147c10`
- end: `0x180147e62`
- name: `?EncodeMetaFile@CMetaFilePacker@@QEAAJPEAPEAXPEAX@Z`
- size: `594`
- prototype: `int(CMetaFilePacker *__hidden this, void **, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18013f934`

## callees

- `0x1800091a8`
- `0x180059878`
- `0x180147c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147cbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147cf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147d20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147dd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147e1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147e27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147cbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147cf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147d20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147dd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147e1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180147e27`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180147d6d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180147d6d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180147e44`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180147e44`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180147c2f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180147c6e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180147c2f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180147c6e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180147dc3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180147e13`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180147dc3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180147e13`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180147caf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180147d82`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180147caf`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180147d82`
- `GDI32!DeleteMetaFile` at `0x180147df0`
- `GDI32!DeleteMetaFile` at `0x180147df0`
- `GDI32!CreateMetaFileW` at `0x180147ce2`
- `GDI32!CreateMetaFileW` at `0x180147ce2`
- `GDI32!PlayMetaFile` at `0x180147d16`
- `GDI32!PlayMetaFile` at `0x180147d16`
- `GDI32!CloseMetaFile` at `0x180147d34`
- `GDI32!CloseMetaFile` at `0x180147d42`
- `GDI32!CloseMetaFile` at `0x180147d34`
- `GDI32!CloseMetaFile` at `0x180147d42`
- `GDI32!GetMetaFileBitsEx` at `0x180147d58`
- `GDI32!GetMetaFileBitsEx` at `0x180147db0`
- `GDI32!GetMetaFileBitsEx` at `0x180147d58`
- `GDI32!GetMetaFileBitsEx` at `0x180147db0`

## pseudocode

```c
__int64 __fastcall CMetaFilePacker::EncodeMetaFile(CMetaFilePacker *this, void **a2, void *a3)
{
  unsigned int v5; // edi
  int v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  HMETAFILE *v8; // rdi
  signed int LastError; // eax
  HMETAFILE v10; // rbp
  _DWORD *v11; // r15
  HDC MetaFileW; // rax
  HDC v13; // rsi
  signed int v14; // eax
  signed int v15; // eax
  HMETAFILE v16; // rax
  UINT MetaFileBits; // eax
  UINT v18; // esi
  HGLOBAL v19; // rax
  _DWORD *v20; // rax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax

  *a2 = 0;
  if ( GlobalSize(a3) >= 0x18 )
  {
    v8 = (HMETAFILE *)GlobalLock(a3);
    if ( !v8 )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_35;
    }
    v10 = 0;
    v11 = 0;
    MetaFileW = CreateMetaFileW(0);
    v13 = MetaFileW;
    if ( !MetaFileW )
      goto LABEL_10;
    if ( !PlayMetaFile(MetaFileW, v8[2]) )
    {
      v15 = GetLastError();
      v5 = v15;
      if ( v15 > 0 )
        v5 = (unsigned __int16)v15 | 0x80070000;
      CloseMetaFile(v13);
      goto LABEL_22;
    }
    v16 = CloseMetaFile(v13);
    v10 = v16;
    if ( !v16 )
      goto LABEL_10;
    MetaFileBits = GetMetaFileBitsEx(v16, 0, 0);
    v18 = MetaFileBits;
    if ( !MetaFileBits )
      goto LABEL_10;
    v19 = GlobalAlloc(0x42u, MetaFileBits + 12LL);
    *a2 = v19;
    if ( v19
      && (v20 = GlobalLock(v19), (v11 = v20) != 0)
      && (*v20 = *(_DWORD *)v8,
          v20[1] = *((_DWORD *)v8 + 1),
          v20[2] = *((_DWORD *)v8 + 2),
          GetMetaFileBitsEx(v10, v18, v20 + 3)) )
    {
      v5 = 0;
    }
    else
    {
LABEL_10:
      v14 = GetLastError();
      v5 = v14;
      if ( v14 > 0 )
        v5 = (unsigned __int16)v14 | 0x80070000;
    }
LABEL_22:
    if ( !GlobalUnlock(a3) )
    {
      if ( GetLastError() )
      {
        v21 = GetLastError();
        v5 = v21;
        if ( v21 > 0 )
          v5 = (unsigned __int16)v21 | 0x80070000;
      }
    }
    if ( v10 )
    {
      if ( !DeleteMetaFile(v10) )
      {
        v22 = GetLastError();
        v5 = v22;
        if ( v22 > 0 )
          v5 = (unsigned __int16)v22 | 0x80070000;
      }
    }
    if ( v11 )
    {
      if ( !GlobalUnlock(*a2) )
      {
        if ( GetLastError() )
        {
          v23 = GetLastError();
          v5 = v23;
          if ( v23 > 0 )
            v5 = (unsigned __int16)v23 | 0x80070000;
        }
      }
    }
LABEL_35:
    if ( (v5 & 0x80000000) == 0 )
      return v5;
    goto LABEL_36;
  }
  v5 = -2147024809;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = GlobalSize(a3);
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_3d26ebc3efb0365bdc62bf2d6cb174ee_Traceguids,
      CurrentThreadActivityIdPrefix,
      24,
      v6);
  }
LABEL_36:
  if ( *a2 )
  {
    GlobalFree(*a2);
    *a2 = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180147c10  push    rbx
0x180147c12  push    rbp
0x180147c13  push    rsi
0x180147c14  push    rdi
0x180147c15  push    r12
0x180147c17  push    r14
0x180147c19  push    r15
0x180147c1b  sub     rsp, 30h
0x180147c1f  mov     rcx, r8; hMem
0x180147c22  mov     qword ptr [rdx], 0
0x180147c29  mov     r12, r8
0x180147c2c  mov     r14, rdx
0x180147c2f  call    cs:__imp_GlobalSize
0x180147c35  cmp     rax, 18h
0x180147c39  jnb     short loc_180147CAC
0x180147c3b  mov     edi, 80070057h
0x180147c40  mov     rax, cs:WPP_GLOBAL_Control
0x180147c47  lea     rcx, WPP_GLOBAL_Control
0x180147c4e  cmp     rax, rcx
0x180147c51  jz      loc_180147E3C
0x180147c57  test    byte ptr [rax+1Ch], 1
0x180147c5b  jz      loc_180147E3C
0x180147c61  cmp     byte ptr [rax+19h], 2
0x180147c65  jb      loc_180147E3C
0x180147c6b  mov     rcx, r12; hMem
0x180147c6e  call    cs:__imp_GlobalSize
0x180147c74  mov     rbx, rax
0x180147c77  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180147c7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180147c83  lea     r8, WPP_3d26ebc3efb0365bdc62bf2d6cb174ee_Traceguids
0x180147c8a  mov     edx, 0Ah
0x180147c8f  mov     [rsp+68h+var_40], ebx
0x180147c93  mov     r9d, eax
0x180147c96  mov     [rsp+68h+var_48], 18h
0x180147c9e  mov     rcx, [rcx+10h]
0x180147ca2  call    WPP_SF_DdD
0x180147ca7  jmp     loc_180147E3C
0x180147cac  mov     rcx, r12; hMem
0x180147caf  call    cs:__imp_GlobalLock
0x180147cb5  mov     rdi, rax
0x180147cb8  test    rax, rax
0x180147cbb  jnz     short loc_180147CDB
0x180147cbd  call    cs:__imp_GetLastError
0x180147cc3  mov     edi, eax
0x180147cc5  test    eax, eax
0x180147cc7  jle     loc_180147E38
0x180147ccd  movzx   edi, ax
0x180147cd0  or      edi, 80070000h
0x180147cd6  jmp     loc_180147E38
0x180147cdb  xor     ecx, ecx; pszFile
0x180147cdd  xor     ebp, ebp
0x180147cdf  xor     r15d, r15d
0x180147ce2  call    cs:__imp_CreateMetaFileW
0x180147ce8  mov     rsi, rax
0x180147ceb  mov     ebx, 80070000h
0x180147cf0  test    rax, rax
0x180147cf3  jnz     short loc_180147D0F
0x180147cf5  call    cs:__imp_GetLastError
0x180147cfb  mov     edi, eax
0x180147cfd  test    eax, eax
0x180147cff  jle     loc_180147DC0
0x180147d05  movzx   edi, ax
0x180147d08  or      edi, ebx
0x180147d0a  jmp     loc_180147DC0
0x180147d0f  mov     rdx, [rdi+10h]; hmf
0x180147d13  mov     rcx, rsi; hdc
0x180147d16  call    cs:__imp_PlayMetaFile
0x180147d1c  test    eax, eax
0x180147d1e  jnz     short loc_180147D3F
0x180147d20  call    cs:__imp_GetLastError
0x180147d26  mov     edi, eax
0x180147d28  test    eax, eax
0x180147d2a  jle     short loc_180147D31
0x180147d2c  movzx   edi, ax
0x180147d2f  or      edi, ebx
0x180147d31  mov     rcx, rsi; hdc
0x180147d34  call    cs:__imp_CloseMetaFile
0x180147d3a  jmp     loc_180147DC0
0x180147d3f  mov     rcx, rsi; hdc
0x180147d42  call    cs:__imp_CloseMetaFile
0x180147d48  mov     rbp, rax
0x180147d4b  test    rax, rax
0x180147d4e  jz      short loc_180147CF5
0x180147d50  xor     r8d, r8d; lpData
0x180147d53  xor     edx, edx; cbBuffer
0x180147d55  mov     rcx, rax; hMF
0x180147d58  call    cs:__imp_GetMetaFileBitsEx
0x180147d5e  mov     esi, eax
0x180147d60  test    eax, eax
0x180147d62  jz      short loc_180147CF5
0x180147d64  lea     rdx, [rsi+0Ch]; dwBytes
0x180147d68  mov     ecx, 42h ; 'B'; uFlags
0x180147d6d  call    cs:__imp_GlobalAlloc
0x180147d73  mov     [r14], rax
0x180147d76  test    rax, rax
0x180147d79  jz      loc_180147CF5
0x180147d7f  mov     rcx, rax; hMem
0x180147d82  call    cs:__imp_GlobalLock
0x180147d88  mov     r15, rax
0x180147d8b  test    rax, rax
0x180147d8e  jz      loc_180147CF5
0x180147d94  mov     eax, [rdi]
0x180147d96  lea     r8, [r15+0Ch]; lpData
0x180147d9a  mov     [r15], eax
0x180147d9d  mov     edx, esi; cbBuffer
0x180147d9f  mov     eax, [rdi+4]
0x180147da2  mov     rcx, rbp; hMF
0x180147da5  mov     [r15+4], eax
0x180147da9  mov     eax, [rdi+8]
0x180147dac  mov     [r15+8], eax
0x180147db0  call    cs:__imp_GetMetaFileBitsEx
0x180147db6  test    eax, eax
0x180147db8  jz      loc_180147CF5
0x180147dbe  xor     edi, edi
0x180147dc0  mov     rcx, r12; hMem
0x180147dc3  call    cs:__imp_GlobalUnlock
0x180147dc9  test    eax, eax
0x180147dcb  jnz     short loc_180147DE8
0x180147dcd  call    cs:__imp_GetLastError
0x180147dd3  test    eax, eax
0x180147dd5  jz      short loc_180147DE8
0x180147dd7  call    cs:__imp_GetLastError
0x180147ddd  mov     edi, eax
0x180147ddf  test    eax, eax
0x180147de1  jle     short loc_180147DE8
0x180147de3  movzx   edi, ax
0x180147de6  or      edi, ebx
0x180147de8  test    rbp, rbp
0x180147deb  jz      short loc_180147E0B
0x180147ded  mov     rcx, rbp; hmf
0x180147df0  call    cs:__imp_DeleteMetaFile
0x180147df6  test    eax, eax
0x180147df8  jnz     short loc_180147E0B
0x180147dfa  call    cs:__imp_GetLastError
0x180147e00  mov     edi, eax
0x180147e02  test    eax, eax
0x180147e04  jle     short loc_180147E0B
0x180147e06  movzx   edi, ax
0x180147e09  or      edi, ebx
0x180147e0b  test    r15, r15
0x180147e0e  jz      short loc_180147E38
0x180147e10  mov     rcx, [r14]; hMem
0x180147e13  call    cs:__imp_GlobalUnlock
0x180147e19  test    eax, eax
0x180147e1b  jnz     short loc_180147E38
0x180147e1d  call    cs:__imp_GetLastError
0x180147e23  test    eax, eax
0x180147e25  jz      short loc_180147E38
0x180147e27  call    cs:__imp_GetLastError
0x180147e2d  mov     edi, eax
0x180147e2f  test    eax, eax
0x180147e31  jle     short loc_180147E38
0x180147e33  movzx   edi, ax
0x180147e36  or      edi, ebx
0x180147e38  test    edi, edi
0x180147e3a  jns     short loc_180147E51
0x180147e3c  mov     rcx, [r14]; hMem
0x180147e3f  test    rcx, rcx
0x180147e42  jz      short loc_180147E51
0x180147e44  call    cs:__imp_GlobalFree
0x180147e4a  mov     qword ptr [r14], 0
0x180147e51  mov     eax, edi
0x180147e53  add     rsp, 30h
0x180147e57  pop     r15
0x180147e59  pop     r14
0x180147e5b  pop     r12
0x180147e5d  pop     rdi
0x180147e5e  pop     rsi
0x180147e5f  pop     rbp
0x180147e60  pop     rbx
0x180147e61  retn
```
