# CMetaFilePacker::EncodeMetaFile(void * *,void *)

- ea: `0x140069d00`
- end: `0x140069f52`
- name: `?EncodeMetaFile@CMetaFilePacker@@QEAAJPEAPEAXPEAX@Z`
- size: `594`
- prototype: `int(CMetaFilePacker *__hidden this, void **, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400619b8`

## callees

- `0x140004b1c`
- `0x14000cae0`
- `0x140069d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069dad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069de5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069e10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069dad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069de5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069e10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069ebd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069ec7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069f17`
- `GDI32!CreateMetaFileW` at `0x140069dd2`
- `GDI32!CreateMetaFileW` at `0x140069dd2`
- `GDI32!PlayMetaFile` at `0x140069e06`
- `GDI32!PlayMetaFile` at `0x140069e06`
- `GDI32!DeleteMetaFile` at `0x140069ee0`
- `GDI32!DeleteMetaFile` at `0x140069ee0`
- `GDI32!CloseMetaFile` at `0x140069e24`
- `GDI32!CloseMetaFile` at `0x140069e32`
- `GDI32!CloseMetaFile` at `0x140069e24`
- `GDI32!CloseMetaFile` at `0x140069e32`
- `GDI32!GetMetaFileBitsEx` at `0x140069e48`
- `GDI32!GetMetaFileBitsEx` at `0x140069ea0`
- `GDI32!GetMetaFileBitsEx` at `0x140069e48`
- `GDI32!GetMetaFileBitsEx` at `0x140069ea0`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x140069e5d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x140069e5d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x140069f34`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x140069f34`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x140069d9f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x140069e72`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x140069d9f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x140069e72`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x140069d1f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x140069d5e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x140069d1f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x140069d5e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x140069eb3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x140069f03`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x140069eb3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x140069f03`

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
0x140069d00  push    rbx
0x140069d02  push    rbp
0x140069d03  push    rsi
0x140069d04  push    rdi
0x140069d05  push    r12
0x140069d07  push    r14
0x140069d09  push    r15
0x140069d0b  sub     rsp, 30h
0x140069d0f  mov     rcx, r8; hMem
0x140069d12  mov     qword ptr [rdx], 0
0x140069d19  mov     r12, r8
0x140069d1c  mov     r14, rdx
0x140069d1f  call    cs:__imp_GlobalSize
0x140069d25  cmp     rax, 18h
0x140069d29  jnb     short loc_140069D9C
0x140069d2b  mov     edi, 80070057h
0x140069d30  mov     rax, cs:WPP_GLOBAL_Control
0x140069d37  lea     rcx, WPP_GLOBAL_Control
0x140069d3e  cmp     rax, rcx
0x140069d41  jz      loc_140069F2C
0x140069d47  test    byte ptr [rax+1Ch], 1
0x140069d4b  jz      loc_140069F2C
0x140069d51  cmp     byte ptr [rax+19h], 2
0x140069d55  jb      loc_140069F2C
0x140069d5b  mov     rcx, r12; hMem
0x140069d5e  call    cs:__imp_GlobalSize
0x140069d64  mov     rbx, rax
0x140069d67  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140069d6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140069d73  lea     r8, WPP_3d26ebc3efb0365bdc62bf2d6cb174ee_Traceguids
0x140069d7a  mov     edx, 0Ah
0x140069d7f  mov     [rsp+68h+var_40], ebx
0x140069d83  mov     r9d, eax
0x140069d86  mov     [rsp+68h+var_48], 18h
0x140069d8e  mov     rcx, [rcx+10h]
0x140069d92  call    WPP_SF_DdD
0x140069d97  jmp     loc_140069F2C
0x140069d9c  mov     rcx, r12; hMem
0x140069d9f  call    cs:__imp_GlobalLock
0x140069da5  mov     rdi, rax
0x140069da8  test    rax, rax
0x140069dab  jnz     short loc_140069DCB
0x140069dad  call    cs:__imp_GetLastError
0x140069db3  mov     edi, eax
0x140069db5  test    eax, eax
0x140069db7  jle     loc_140069F28
0x140069dbd  movzx   edi, ax
0x140069dc0  or      edi, 80070000h
0x140069dc6  jmp     loc_140069F28
0x140069dcb  xor     ecx, ecx; pszFile
0x140069dcd  xor     ebp, ebp
0x140069dcf  xor     r15d, r15d
0x140069dd2  call    cs:__imp_CreateMetaFileW
0x140069dd8  mov     rsi, rax
0x140069ddb  mov     ebx, 80070000h
0x140069de0  test    rax, rax
0x140069de3  jnz     short loc_140069DFF
0x140069de5  call    cs:__imp_GetLastError
0x140069deb  mov     edi, eax
0x140069ded  test    eax, eax
0x140069def  jle     loc_140069EB0
0x140069df5  movzx   edi, ax
0x140069df8  or      edi, ebx
0x140069dfa  jmp     loc_140069EB0
0x140069dff  mov     rdx, [rdi+10h]; hmf
0x140069e03  mov     rcx, rsi; hdc
0x140069e06  call    cs:__imp_PlayMetaFile
0x140069e0c  test    eax, eax
0x140069e0e  jnz     short loc_140069E2F
0x140069e10  call    cs:__imp_GetLastError
0x140069e16  mov     edi, eax
0x140069e18  test    eax, eax
0x140069e1a  jle     short loc_140069E21
0x140069e1c  movzx   edi, ax
0x140069e1f  or      edi, ebx
0x140069e21  mov     rcx, rsi; hdc
0x140069e24  call    cs:__imp_CloseMetaFile
0x140069e2a  jmp     loc_140069EB0
0x140069e2f  mov     rcx, rsi; hdc
0x140069e32  call    cs:__imp_CloseMetaFile
0x140069e38  mov     rbp, rax
0x140069e3b  test    rax, rax
0x140069e3e  jz      short loc_140069DE5
0x140069e40  xor     r8d, r8d; lpData
0x140069e43  xor     edx, edx; cbBuffer
0x140069e45  mov     rcx, rax; hMF
0x140069e48  call    cs:__imp_GetMetaFileBitsEx
0x140069e4e  mov     esi, eax
0x140069e50  test    eax, eax
0x140069e52  jz      short loc_140069DE5
0x140069e54  lea     rdx, [rsi+0Ch]; dwBytes
0x140069e58  mov     ecx, 42h ; 'B'; uFlags
0x140069e5d  call    cs:__imp_GlobalAlloc
0x140069e63  mov     [r14], rax
0x140069e66  test    rax, rax
0x140069e69  jz      loc_140069DE5
0x140069e6f  mov     rcx, rax; hMem
0x140069e72  call    cs:__imp_GlobalLock
0x140069e78  mov     r15, rax
0x140069e7b  test    rax, rax
0x140069e7e  jz      loc_140069DE5
0x140069e84  mov     eax, [rdi]
0x140069e86  lea     r8, [r15+0Ch]; lpData
0x140069e8a  mov     [r15], eax
0x140069e8d  mov     edx, esi; cbBuffer
0x140069e8f  mov     eax, [rdi+4]
0x140069e92  mov     rcx, rbp; hMF
0x140069e95  mov     [r15+4], eax
0x140069e99  mov     eax, [rdi+8]
0x140069e9c  mov     [r15+8], eax
0x140069ea0  call    cs:__imp_GetMetaFileBitsEx
0x140069ea6  test    eax, eax
0x140069ea8  jz      loc_140069DE5
0x140069eae  xor     edi, edi
0x140069eb0  mov     rcx, r12; hMem
0x140069eb3  call    cs:__imp_GlobalUnlock
0x140069eb9  test    eax, eax
0x140069ebb  jnz     short loc_140069ED8
0x140069ebd  call    cs:__imp_GetLastError
0x140069ec3  test    eax, eax
0x140069ec5  jz      short loc_140069ED8
0x140069ec7  call    cs:__imp_GetLastError
0x140069ecd  mov     edi, eax
0x140069ecf  test    eax, eax
0x140069ed1  jle     short loc_140069ED8
0x140069ed3  movzx   edi, ax
0x140069ed6  or      edi, ebx
0x140069ed8  test    rbp, rbp
0x140069edb  jz      short loc_140069EFB
0x140069edd  mov     rcx, rbp; hmf
0x140069ee0  call    cs:__imp_DeleteMetaFile
0x140069ee6  test    eax, eax
0x140069ee8  jnz     short loc_140069EFB
0x140069eea  call    cs:__imp_GetLastError
0x140069ef0  mov     edi, eax
0x140069ef2  test    eax, eax
0x140069ef4  jle     short loc_140069EFB
0x140069ef6  movzx   edi, ax
0x140069ef9  or      edi, ebx
0x140069efb  test    r15, r15
0x140069efe  jz      short loc_140069F28
0x140069f00  mov     rcx, [r14]; hMem
0x140069f03  call    cs:__imp_GlobalUnlock
0x140069f09  test    eax, eax
0x140069f0b  jnz     short loc_140069F28
0x140069f0d  call    cs:__imp_GetLastError
0x140069f13  test    eax, eax
0x140069f15  jz      short loc_140069F28
0x140069f17  call    cs:__imp_GetLastError
0x140069f1d  mov     edi, eax
0x140069f1f  test    eax, eax
0x140069f21  jle     short loc_140069F28
0x140069f23  movzx   edi, ax
0x140069f26  or      edi, ebx
0x140069f28  test    edi, edi
0x140069f2a  jns     short loc_140069F41
0x140069f2c  mov     rcx, [r14]; hMem
0x140069f2f  test    rcx, rcx
0x140069f32  jz      short loc_140069F41
0x140069f34  call    cs:__imp_GlobalFree
0x140069f3a  mov     qword ptr [r14], 0
0x140069f41  mov     eax, edi
0x140069f43  add     rsp, 30h
0x140069f47  pop     r15
0x140069f49  pop     r14
0x140069f4b  pop     r12
0x140069f4d  pop     rdi
0x140069f4e  pop     rsi
0x140069f4f  pop     rbp
0x140069f50  pop     rbx
0x140069f51  retn
```
