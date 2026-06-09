# CMetaFilePacker::DecodeMetaFile(void * *,uchar *,uint)

- ea: `0x140069af8`
- end: `0x140069cfa`
- name: `?DecodeMetaFile@CMetaFilePacker@@QEAAJPEAPEAXPEAEI@Z`
- size: `514`
- prototype: `__int64 __fastcall(CMetaFilePacker *__hidden this, void **, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400614c8`

## callees

- `0x140004b1c`
- `0x1400056c4`
- `0x140069af8`
- `0x14006a0e2`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069bc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069bc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069bfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069c86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069c90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140069caf`
- `GDI32!DeleteMetaFile` at `0x140069ccc`
- `GDI32!DeleteMetaFile` at `0x140069ccc`
- `GDI32!SetMetaFileBitsEx` at `0x140069be9`
- `GDI32!SetMetaFileBitsEx` at `0x140069be9`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x140069b86`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x140069c17`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x140069b86`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x140069c17`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x140069ca4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x140069cda`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x140069ca4`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x140069cda`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x140069bb5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x140069c28`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x140069bb5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x140069c28`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x140069c4f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x140069c7c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x140069c4f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x140069c7c`

## pseudocode

```c
__int64 __fastcall CMetaFilePacker::DecodeMetaFile(
        CMetaFilePacker *this,
        void **a2,
        unsigned __int8 *a3,
        unsigned int a4)
{
  unsigned int v6; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  UINT v8; // ebp
  HMETAFILE v9; // r12
  SIZE_T v10; // r15
  HGLOBAL v11; // rax
  void *v12; // r13
  signed int v13; // eax
  BYTE *v14; // rax
  const BYTE *v15; // rdi
  _DWORD *v16; // rsi
  signed int LastError; // eax
  HGLOBAL v18; // rax
  _DWORD *v19; // rax
  int v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  signed int v23; // eax

  *a2 = 0;
  if ( a4 < 0xC )
  {
    v6 = -2092629015;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_3d26ebc3efb0365bdc62bf2d6cb174ee_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
LABEL_31:
    if ( *a2 )
    {
      GlobalFree(*a2);
      *a2 = 0;
    }
    return v6;
  }
  v8 = a4 - 12;
  v9 = 0;
  v10 = a4 - 12;
  v11 = GlobalAlloc(0x42u, v10);
  v12 = v11;
  if ( v11 )
  {
    v14 = (BYTE *)GlobalLock(v11);
    v15 = v14;
    if ( !v14 )
      goto LABEL_23;
    v16 = 0;
    memcpy_0(v14, a3 + 12, v10);
    v9 = SetMetaFileBitsEx(v8, v15);
    if ( v9 && (v18 = GlobalAlloc(0x42u, 0x18u), (*a2 = v18) != 0) && (v19 = GlobalLock(v18), (v16 = v19) != 0) )
    {
      *v19 = *(_DWORD *)a3;
      v19[1] = *((_DWORD *)a3 + 1);
      v20 = *((_DWORD *)a3 + 2);
      v6 = 0;
      v16[2] = v20;
      *((_QWORD *)v16 + 2) = v9;
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( !GlobalUnlock(v12) )
    {
      if ( GetLastError() )
      {
        v21 = GetLastError();
        v6 = v21;
        if ( v21 > 0 )
          v6 = (unsigned __int16)v21 | 0x80070000;
      }
    }
    if ( v16 && !GlobalUnlock(*a2) && GetLastError() )
    {
LABEL_23:
      v22 = GetLastError();
      v6 = v22;
      if ( v22 > 0 )
        v6 = (unsigned __int16)v22 | 0x80070000;
    }
    if ( GlobalFree(v12) )
    {
      v23 = GetLastError();
      v6 = v23;
      if ( v23 > 0 )
        v6 = (unsigned __int16)v23 | 0x80070000;
    }
  }
  else
  {
    v13 = GetLastError();
    v6 = v13;
    if ( v13 > 0 )
      v6 = (unsigned __int16)v13 | 0x80070000;
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    if ( v9 )
      DeleteMetaFile(v9);
    goto LABEL_31;
  }
  return v6;
}

```

## disassembly

```asm
0x140069af8  push    rbx
0x140069afa  push    rbp
0x140069afb  push    rsi
0x140069afc  push    rdi
0x140069afd  push    r12
0x140069aff  push    r13
0x140069b01  push    r14
0x140069b03  push    r15
0x140069b05  sub     rsp, 28h
0x140069b09  mov     qword ptr [rdx], 0
0x140069b10  mov     rbx, r8
0x140069b13  mov     r14, rdx
0x140069b16  cmp     r9d, 0Ch
0x140069b1a  jnb     short loc_140069B75
0x140069b1c  mov     ebx, 834503E9h
0x140069b21  mov     rax, cs:WPP_GLOBAL_Control
0x140069b28  lea     rcx, WPP_GLOBAL_Control
0x140069b2f  cmp     rax, rcx
0x140069b32  jz      loc_140069CD2
0x140069b38  test    byte ptr [rax+1Ch], 1
0x140069b3c  jz      loc_140069CD2
0x140069b42  cmp     byte ptr [rax+19h], 2
0x140069b46  jb      loc_140069CD2
0x140069b4c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140069b51  mov     rcx, cs:WPP_GLOBAL_Control
0x140069b58  lea     r8, WPP_3d26ebc3efb0365bdc62bf2d6cb174ee_Traceguids
0x140069b5f  mov     edx, 0Bh
0x140069b64  mov     r9d, eax
0x140069b67  mov     rcx, [rcx+10h]
0x140069b6b  call    WPP_SF_d
0x140069b70  jmp     loc_140069CD2
0x140069b75  lea     ebp, [r9-0Ch]
0x140069b79  xor     r12d, r12d
0x140069b7c  mov     edx, ebp; dwBytes
0x140069b7e  mov     r15d, ebp
0x140069b81  lea     ecx, [r12+42h]; uFlags
0x140069b86  call    cs:__imp_GlobalAlloc
0x140069b8c  mov     r13, rax
0x140069b8f  test    rax, rax
0x140069b92  jnz     short loc_140069BB2
0x140069b94  call    cs:__imp_GetLastError
0x140069b9a  mov     ebx, eax
0x140069b9c  test    eax, eax
0x140069b9e  jle     loc_140069CC0
0x140069ba4  movzx   ebx, ax
0x140069ba7  or      ebx, 80070000h
0x140069bad  jmp     loc_140069CC0
0x140069bb2  mov     rcx, r13; hMem
0x140069bb5  call    cs:__imp_GlobalLock
0x140069bbb  mov     rdi, rax
0x140069bbe  test    rax, rax
0x140069bc1  jnz     short loc_140069BD3
0x140069bc3  call    cs:__imp_GetLastError
0x140069bc9  mov     edi, 80070000h
0x140069bce  jmp     loc_140069C96
0x140069bd3  lea     rdx, [rbx+0Ch]; Src
0x140069bd7  mov     r8, r15; Size
0x140069bda  mov     rcx, rdi; void *
0x140069bdd  xor     esi, esi
0x140069bdf  call    memcpy_0
0x140069be4  mov     rdx, rdi; lpData
0x140069be7  mov     ecx, ebp; cbBuffer
0x140069be9  call    cs:__imp_SetMetaFileBitsEx
0x140069bef  mov     r12, rax
0x140069bf2  mov     edi, 80070000h
0x140069bf7  test    rax, rax
0x140069bfa  jnz     short loc_140069C0F
0x140069bfc  call    cs:__imp_GetLastError
0x140069c02  mov     ebx, eax
0x140069c04  test    eax, eax
0x140069c06  jle     short loc_140069C4C
0x140069c08  movzx   ebx, ax
0x140069c0b  or      ebx, edi
0x140069c0d  jmp     short loc_140069C4C
0x140069c0f  mov     edx, 18h; dwBytes
0x140069c14  lea     ecx, [rdx+2Ah]; uFlags
0x140069c17  call    cs:__imp_GlobalAlloc
0x140069c1d  mov     [r14], rax
0x140069c20  test    rax, rax
0x140069c23  jz      short loc_140069BFC
0x140069c25  mov     rcx, rax; hMem
0x140069c28  call    cs:__imp_GlobalLock
0x140069c2e  mov     rsi, rax
0x140069c31  test    rax, rax
0x140069c34  jz      short loc_140069BFC
0x140069c36  mov     eax, [rbx]
0x140069c38  mov     [rsi], eax
0x140069c3a  mov     eax, [rbx+4]
0x140069c3d  mov     [rsi+4], eax
0x140069c40  mov     eax, [rbx+8]
0x140069c43  xor     ebx, ebx
0x140069c45  mov     [rsi+8], eax
0x140069c48  mov     [rsi+10h], r12
0x140069c4c  mov     rcx, r13; hMem
0x140069c4f  call    cs:__imp_GlobalUnlock
0x140069c55  test    eax, eax
0x140069c57  jnz     short loc_140069C74
0x140069c59  call    cs:__imp_GetLastError
0x140069c5f  test    eax, eax
0x140069c61  jz      short loc_140069C74
0x140069c63  call    cs:__imp_GetLastError
0x140069c69  mov     ebx, eax
0x140069c6b  test    eax, eax
0x140069c6d  jle     short loc_140069C74
0x140069c6f  movzx   ebx, ax
0x140069c72  or      ebx, edi
0x140069c74  test    rsi, rsi
0x140069c77  jz      short loc_140069CA1
0x140069c79  mov     rcx, [r14]; hMem
0x140069c7c  call    cs:__imp_GlobalUnlock
0x140069c82  test    eax, eax
0x140069c84  jnz     short loc_140069CA1
0x140069c86  call    cs:__imp_GetLastError
0x140069c8c  test    eax, eax
0x140069c8e  jz      short loc_140069CA1
0x140069c90  call    cs:__imp_GetLastError
0x140069c96  mov     ebx, eax
0x140069c98  test    eax, eax
0x140069c9a  jle     short loc_140069CA1
0x140069c9c  movzx   ebx, ax
0x140069c9f  or      ebx, edi
0x140069ca1  mov     rcx, r13; hMem
0x140069ca4  call    cs:__imp_GlobalFree
0x140069caa  test    rax, rax
0x140069cad  jz      short loc_140069CC0
0x140069caf  call    cs:__imp_GetLastError
0x140069cb5  mov     ebx, eax
0x140069cb7  test    eax, eax
0x140069cb9  jle     short loc_140069CC0
0x140069cbb  movzx   ebx, ax
0x140069cbe  or      ebx, edi
0x140069cc0  test    ebx, ebx
0x140069cc2  jns     short loc_140069CE7
0x140069cc4  test    r12, r12
0x140069cc7  jz      short loc_140069CD2
0x140069cc9  mov     rcx, r12; hmf
0x140069ccc  call    cs:__imp_DeleteMetaFile
0x140069cd2  mov     rcx, [r14]; hMem
0x140069cd5  test    rcx, rcx
0x140069cd8  jz      short loc_140069CE7
0x140069cda  call    cs:__imp_GlobalFree
0x140069ce0  mov     qword ptr [r14], 0
0x140069ce7  mov     eax, ebx
0x140069ce9  add     rsp, 28h
0x140069ced  pop     r15
0x140069cef  pop     r14
0x140069cf1  pop     r13
0x140069cf3  pop     r12
0x140069cf5  pop     rdi
0x140069cf6  pop     rsi
0x140069cf7  pop     rbp
0x140069cf8  pop     rbx
0x140069cf9  retn
```
