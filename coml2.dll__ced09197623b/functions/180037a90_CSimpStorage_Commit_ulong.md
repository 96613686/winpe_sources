# CSimpStorage::Commit(ulong)

- ea: `0x180037a90`
- end: `0x180037f00`
- name: `?Commit@CSimpStorage@@UEAAJK@Z`
- size: `1136`
- prototype: `__int64 __fastcall(CSimpStorage *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004e980`
- `0x18004f0b0`

## callees

- `0x180008968`
- `0x1800089f0`
- `0x180026bc4`
- `0x180037a90`
- `0x180037f08`
- `0x180042bd0`
- `0x180043100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037e9f`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180037e95`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180037e95`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180037e21`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180037e5e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180037e21`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180037e5e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037e48`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037e80`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037e48`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180037e80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037b82`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180037b82`

## pseudocode

```c
__int64 __fastcall CSimpStorage::Commit(CSimpStorage *this, int a2)
{
  __int64 result; // rax
  int v4; // r9d
  unsigned int v5; // r14d
  unsigned int v6; // ebx
  unsigned int v7; // esi
  int v8; // r9d
  int v9; // ecx
  int v10; // r8d
  char *v11; // rax
  char *v12; // r12
  unsigned int v13; // ebp
  unsigned int v14; // r15d
  unsigned __int16 v15; // r13
  unsigned int v16; // r14d
  unsigned int v17; // r8d
  unsigned int v18; // edx
  char *v19; // r9
  char *v20; // r9
  unsigned int i; // r8d
  __int64 v22; // rcx
  unsigned int v23; // edx
  __int64 v24; // rax
  unsigned int v25; // ecx
  unsigned int v26; // ebp
  __int64 v27; // rsi
  CDirEntry *v28; // r15
  unsigned int v29; // edx
  unsigned int j; // r8d
  __int64 v31; // rax
  CDfName *v32; // rbx
  CDirEntry *v33; // rbx
  void *v34; // rcx
  LONG v35; // edx
  DWORD LastError; // eax
  unsigned int v37; // ebx
  DWORD NumberOfBytesWritten; // [rsp+30h] [rbp-D8h] BYREF
  char *v39; // [rsp+38h] [rbp-D0h]
  unsigned int v40; // [rsp+44h] [rbp-C4h]
  unsigned int v41; // [rsp+48h] [rbp-C0h]
  unsigned int v42; // [rsp+4Ch] [rbp-BCh]
  unsigned int v43; // [rsp+50h] [rbp-B8h]
  int v44; // [rsp+54h] [rbp-B4h]
  CDirEntry *v45; // [rsp+58h] [rbp-B0h]
  DWORD nNumberOfBytesToWrite[2]; // [rsp+60h] [rbp-A8h]
  unsigned __int8 v47[64]; // [rsp+70h] [rbp-98h] BYREF
  __int16 v48; // [rsp+B0h] [rbp-58h]

  v44 = a2;
  *(_OWORD *)v47 = *(_OWORD *)L"Root Entry";
  *(_QWORD *)&v47[14] = *(_QWORD *)L"try";
  v48 = 22;
  if ( (a2 & 0xFFFFFFF0) != 0 )
    return 2147680511LL;
  if ( *((_QWORD *)this + 79) )
    return 2147680257LL;
  if ( !*((_DWORD *)this + 18) )
    return 0;
  v4 = *((_DWORD *)this + 150);
  v5 = (unsigned int)(*((_DWORD *)this + 160) + 4) >> 2;
  v6 = 0;
  v7 = 0;
  v40 = v5;
  v8 = v5 + v4;
  v9 = -1;
  v10 = -1;
  while ( v7 != v9 || v6 != v10 )
  {
    v9 = v7;
    v10 = v6;
    v7 = (v6 + v8 + v7 + 127) >> 7;
    if ( v7 >= 0x6D )
      v6 = (v7 + 17) / 0x7F;
  }
  if ( !v7 )
    return 2147680509LL;
  *(_QWORD *)nNumberOfBytesToWrite = (v6 + v5 + v7) << 9;
  v11 = (char *)HeapAlloc(g_hHeap, 0, *(SIZE_T *)nNumberOfBytesToWrite);
  *((_QWORD *)this + 74) = v11;
  v12 = v11;
  if ( !v11 )
    return 2147680264LL;
  v43 = *((_DWORD *)this + 150);
  v13 = v43 + v6;
  v42 = v43 + v6;
  v14 = v6 + v43 + v7;
  v41 = v14;
  v39 = &v11[512 * v6];
  v45 = (CDirEntry *)&v11[512 * (v7 + v6)];
  memset_0(v11, 255, v6 << 9);
  memset_0(&v12[512 * v6], 255, v7 << 9);
  v15 = 0;
  if ( 4 * v5 )
  {
    v16 = 4 * v5;
    do
      CDirEntry::Init((CDirEntry *)((char *)v45 + 128 * (unsigned __int64)v15++), 0);
    while ( v15 < v16 );
    v5 = v40;
    v14 = v41;
    v13 = v42;
  }
  if ( v6 )
  {
    v17 = v43;
    v18 = v43;
    if ( v43 < v13 )
    {
      v19 = v39;
      do
      {
        *(_DWORD *)&v19[4 * v18] = -4;
        *(_DWORD *)&v12[512 * (v18 - v17) + 508] = v18 + 1;
        ++v18;
      }
      while ( v18 < v13 );
    }
    *(_DWORD *)&v12[512 * v6 - 4] = -2;
    *((_DWORD *)this + 36) = v17;
    *((_DWORD *)this + 37) = v6;
  }
  v20 = v39;
  for ( i = v13; i < v14; ++i )
  {
    v22 = i - v13;
    *(_DWORD *)&v20[4 * i] = -3;
    if ( (unsigned int)v22 >= 0x6D )
      *(_DWORD *)&v12[4 * i - 436 + 4 * (((int)v22 - 109) / 0x7Fu - v13)] = i;
    else
      *((_DWORD *)this + v22 + 38) = i;
  }
  v23 = v14 + v5;
  v24 = v14;
  if ( v14 < v14 + v5 )
  {
    do
    {
      v25 = v24 + 1;
      *(_DWORD *)&v20[4 * v24] = v24 + 1;
      v24 = (unsigned int)(v24 + 1);
    }
    while ( v25 < v23 );
  }
  *(_DWORD *)&v20[4 * v23 - 4] = -2;
  v26 = 1;
  *((_DWORD *)this + 31) = v14;
  *((_DWORD *)this + 30) = v7;
  *((_DWORD *)this + 147) = 1;
  v27 = *((_QWORD *)this + 78);
  if ( v27 )
  {
    v28 = v45;
    do
    {
      v29 = *(_DWORD *)(v27 + 68);
      for ( j = v29 + ((unsigned int)(*(_DWORD *)(v27 + 72) + 511) >> 9); v29 < j; *(_DWORD *)&v20[4 * v31] = v29 )
        v31 = v29++;
      *(_DWORD *)&v20[4 * j - 4] = -2;
      v32 = (CDirEntry *)((char *)v28 + 128 * (unsigned __int64)v26);
      *((_BYTE *)v32 + 66) = 2;
      CDfName::Set(v32, *(_WORD *)(v27 + 64), (const unsigned __int8 *)v27);
      ++v26;
      v20 = v39;
      *((_DWORD *)v32 + 29) = *(_DWORD *)(v27 + 68);
      *((_QWORD *)v32 + 15) = *(unsigned int *)(v27 + 72);
      *((_BYTE *)v32 + 67) |= 1u;
      v27 = *(_QWORD *)(v27 + 80);
    }
    while ( v27 );
  }
  v33 = v45;
  CDirEntry::Init(v45, 5u);
  CDfName::Set(v45, 0x16u, v47);
  *((_OWORD *)v45 + 5) = *(_OWORD *)((char *)this + 604);
  *((_BYTE *)v33 + 67) |= 1u;
  *((_DWORD *)v33 + 19) = CSimpStorage::BuildTree(this, v33, 1u, *((_DWORD *)this + 160));
  v34 = (void *)*((_QWORD *)this + 8);
  v35 = (*((_DWORD *)this + 150) + 1) << 9;
  NumberOfBytesWritten = 0;
  if ( SetFilePointer(v34, v35, 0, 0) != -1
    && WriteFile(*((HANDLE *)this + 8), *((LPCVOID *)this + 74), nNumberOfBytesToWrite[0], &NumberOfBytesWritten, 0)
    && SetFilePointer(*((HANDLE *)this + 8), 0, 0, 0) != -1
    && WriteFile(*((HANDLE *)this + 8), (char *)this + 76, 0x200u, &NumberOfBytesWritten, 0)
    && ((v44 & 4) != 0 || FlushFileBuffers(*((HANDLE *)this + 8))) )
  {
    operator delete(*((void **)this + 74), 1u);
    *((_QWORD *)this + 74) = 0;
    *((_DWORD *)this + 18) = 0;
    return 0;
  }
  LastError = GetLastError();
  v37 = Win32ErrorToScode(LastError);
  operator delete(*((void **)this + 74), 1u);
  result = v37;
  *((_QWORD *)this + 74) = 0;
  return result;
}

```

## disassembly

```asm
0x180037a90  mov     rax, rsp
0x180037a93  push    rbx
0x180037a94  push    rbp
0x180037a95  push    rsi
0x180037a96  push    rdi
0x180037a97  push    r12
0x180037a99  push    r13
0x180037a9b  push    r14
0x180037a9d  push    r15
0x180037a9f  sub     rsp, 0C8h
0x180037aa6  movsd   xmm1, qword ptr cs:aRootEntry+0Eh; "try"
0x180037aae  mov     rdi, rcx
0x180037ab1  mov     [rsp+108h+var_B4], edx
0x180037ab5  mov     ecx, 16h
0x180037aba  movups  xmm0, xmmword ptr cs:aRootEntry; "Root Entry"
0x180037ac1  movaps  xmmword ptr [rsp+108h+var_98], xmm0
0x180037ac6  movsd   qword ptr [rsp+108h+var_98+0Eh], xmm1
0x180037acc  mov     [rax-58h], cx
0x180037ad0  test    edx, 0FFFFFFF0h
0x180037ad6  jnz     loc_180037EE7
0x180037adc  cmp     qword ptr [rdi+278h], 0
0x180037ae4  jz      short loc_180037AF0
0x180037ae6  mov     eax, 80030001h
0x180037aeb  jmp     loc_180037EEC
0x180037af0  cmp     dword ptr [rdi+48h], 0
0x180037af4  jnz     short loc_180037AFD
0x180037af6  xor     eax, eax
0x180037af8  jmp     loc_180037EEC
0x180037afd  mov     r14d, [rdi+280h]
0x180037b04  or      eax, 0FFFFFFFFh
0x180037b07  mov     r9d, [rdi+258h]
0x180037b0e  add     r14d, 4
0x180037b12  shr     r14d, 2
0x180037b16  xor     ebx, ebx
0x180037b18  xor     esi, esi
0x180037b1a  mov     [rsp+108h+var_C4], r14d
0x180037b1f  add     r9d, r14d
0x180037b22  mov     ecx, eax
0x180037b24  mov     r8d, eax
0x180037b27  cmp     esi, ecx
0x180037b29  jnz     short loc_180037B30
0x180037b2b  cmp     ebx, r8d
0x180037b2e  jz      short loc_180037B5A
0x180037b30  mov     ecx, esi
0x180037b32  mov     r8d, ebx
0x180037b35  add     esi, 7Fh
0x180037b38  add     esi, r9d
0x180037b3b  add     esi, ebx
0x180037b3d  shr     esi, 7
0x180037b40  cmp     esi, 6Dh ; 'm'
0x180037b43  jb      short loc_180037B27
0x180037b45  lea     ebx, [rsi+11h]
0x180037b48  mov     eax, 2040811h
0x180037b4d  mul     ebx
0x180037b4f  sub     ebx, edx
0x180037b51  shr     ebx, 1
0x180037b53  add     ebx, edx
0x180037b55  shr     ebx, 6
0x180037b58  jmp     short loc_180037B27
0x180037b5a  test    esi, esi
0x180037b5c  jnz     short loc_180037B68
0x180037b5e  mov     eax, 800300FDh
0x180037b63  jmp     loc_180037EEC
0x180037b68  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180037b6f  lea     eax, [r14+rsi]
0x180037b73  add     eax, ebx
0x180037b75  xor     edx, edx; dwFlags
0x180037b77  shl     eax, 9
0x180037b7a  mov     r8d, eax; dwBytes
0x180037b7d  mov     qword ptr [rsp+108h+nNumberOfBytesToWrite], rax
0x180037b82  call    cs:__imp_HeapAlloc
0x180037b88  mov     [rdi+250h], rax
0x180037b8f  mov     r12, rax
0x180037b92  test    rax, rax
0x180037b95  jnz     short loc_180037BA1
0x180037b97  mov     eax, 80030008h
0x180037b9c  jmp     loc_180037EEC
0x180037ba1  mov     eax, [rdi+258h]
0x180037ba7  mov     edx, 0FFh; Val
0x180037bac  mov     [rsp+108h+var_B8], eax
0x180037bb0  mov     rcx, r12; void *
0x180037bb3  lea     ebp, [rax+rbx]
0x180037bb6  lea     r15d, [rax+rsi]
0x180037bba  mov     [rsp+108h+var_BC], ebp
0x180037bbe  mov     eax, ebx
0x180037bc0  add     r15d, ebx
0x180037bc3  shl     eax, 9
0x180037bc6  mov     r8d, eax; Size
0x180037bc9  mov     [rsp+108h+var_C0], r15d
0x180037bce  lea     r13, [rax+r12]
0x180037bd2  lea     eax, [rsi+rbx]
0x180037bd5  mov     [rsp+108h+var_D0], r13
0x180037bda  shl     eax, 9
0x180037bdd  add     rax, r12
0x180037be0  mov     [rsp+108h+var_B0], rax
0x180037be5  call    memset_0
0x180037bea  mov     r8d, esi
0x180037bed  mov     edx, 0FFh; Val
0x180037bf2  shl     r8d, 9; Size
0x180037bf6  mov     rcx, r13; void *
0x180037bf9  call    memset_0
0x180037bfe  xor     r13d, r13d
0x180037c01  lea     eax, ds:0[r14*4]
0x180037c09  lea     r10d, [r13+1]
0x180037c0d  test    eax, eax
0x180037c0f  jz      short loc_180037C4F
0x180037c11  mov     rbp, [rsp+108h+var_B0]
0x180037c16  mov     r14d, eax
0x180037c19  mov     r15d, r10d
0x180037c1c  movzx   ecx, r13w
0x180037c20  xor     edx, edx; unsigned int
0x180037c22  shl     rcx, 7
0x180037c26  add     rcx, rbp; this
0x180037c29  call    ?Init@CDirEntry@@QEAAXK@Z; CDirEntry::Init(ulong)
0x180037c2e  add     r13w, r15w
0x180037c32  movzx   eax, r13w
0x180037c36  cmp     eax, r14d
0x180037c39  jb      short loc_180037C1C
0x180037c3b  mov     r14d, [rsp+108h+var_C4]
0x180037c40  mov     r10d, 1
0x180037c46  mov     r15d, [rsp+108h+var_C0]
0x180037c4b  mov     ebp, [rsp+108h+var_BC]
0x180037c4f  xor     r13d, r13d
0x180037c52  test    ebx, ebx
0x180037c54  jz      short loc_180037CA6
0x180037c56  mov     r8d, [rsp+108h+var_B8]
0x180037c5b  mov     edx, r8d
0x180037c5e  cmp     r8d, ebp
0x180037c61  jnb     short loc_180037C88
0x180037c63  mov     r9, [rsp+108h+var_D0]
0x180037c68  lea     ecx, [rdx+1]
0x180037c6b  mov     eax, edx
0x180037c6d  sub     edx, r8d
0x180037c70  shl     edx, 7
0x180037c73  add     edx, 7Fh
0x180037c76  mov     dword ptr [r9+rax*4], 0FFFFFFFCh
0x180037c7e  mov     [r12+rdx*4], ecx
0x180037c82  mov     edx, ecx
0x180037c84  cmp     ecx, ebp
0x180037c86  jb      short loc_180037C68
0x180037c88  lea     eax, [rbx-1]
0x180037c8b  shl     eax, 7
0x180037c8e  add     eax, 7Fh
0x180037c91  mov     dword ptr [r12+rax*4], 0FFFFFFFEh
0x180037c99  mov     [rdi+90h], r8d
0x180037ca0  mov     [rdi+94h], ebx
0x180037ca6  mov     r9, [rsp+108h+var_D0]
0x180037cab  mov     r8d, ebp
0x180037cae  cmp     ebp, r15d
0x180037cb1  jnb     short loc_180037CFA
0x180037cb3  mov     eax, r8d
0x180037cb6  mov     ecx, r8d
0x180037cb9  sub     ecx, ebp
0x180037cbb  mov     dword ptr [r9+rax*4], 0FFFFFFFDh
0x180037cc3  cmp     ecx, 6Dh ; 'm'
0x180037cc6  jnb     short loc_180037CD2
0x180037cc8  mov     [rdi+rcx*4+98h], r8d
0x180037cd0  jmp     short loc_180037CF2
0x180037cd2  add     ecx, 0FFFFFF93h
0x180037cd5  mov     eax, 2040811h
0x180037cda  mul     ecx
0x180037cdc  sub     ecx, edx
0x180037cde  shr     ecx, 1
0x180037ce0  lea     eax, [rdx+rcx]
0x180037ce3  shr     eax, 6
0x180037ce6  sub     eax, ebp
0x180037ce8  add     eax, 0FFFFFF93h
0x180037ceb  add     eax, r8d
0x180037cee  mov     [r12+rax*4], r8d
0x180037cf2  add     r8d, r10d
0x180037cf5  cmp     r8d, r15d
0x180037cf8  jb      short loc_180037CB3
0x180037cfa  lea     edx, [r15+r14]
0x180037cfe  mov     eax, r15d
0x180037d01  cmp     r15d, edx
0x180037d04  jnb     short loc_180037D13
0x180037d06  lea     ecx, [rax+1]
0x180037d09  mov     [r9+rax*4], ecx
0x180037d0d  mov     eax, ecx
0x180037d0f  cmp     ecx, edx
0x180037d11  jb      short loc_180037D06
0x180037d13  mov     r12d, 1
0x180037d19  lea     eax, [rdx-1]
0x180037d1c  mov     dword ptr [r9+rax*4], 0FFFFFFFEh
0x180037d24  mov     ebp, r12d
0x180037d27  mov     [rdi+7Ch], r15d
0x180037d2b  mov     [rdi+78h], esi
0x180037d2e  mov     [rdi+24Ch], r12d
0x180037d35  mov     rsi, [rdi+270h]
0x180037d3c  test    rsi, rsi
0x180037d3f  jz      short loc_180037DBA
0x180037d41  mov     r15, [rsp+108h+var_B0]
0x180037d46  mov     edx, [rsi+44h]
0x180037d49  mov     r8d, [rsi+48h]
0x180037d4d  add     r8d, 1FFh
0x180037d54  shr     r8d, 9
0x180037d58  add     r8d, edx
0x180037d5b  cmp     edx, r8d
0x180037d5e  jnb     short loc_180037D70
0x180037d60  lea     ecx, [rdx+1]
0x180037d63  mov     eax, edx
0x180037d65  mov     edx, ecx
0x180037d67  mov     [r9+rax*4], ecx
0x180037d6b  cmp     ecx, r8d
0x180037d6e  jb      short loc_180037D60
0x180037d70  lea     eax, [r8-1]
0x180037d74  mov     ebx, ebp
0x180037d76  mov     dword ptr [r9+rax*4], 0FFFFFFFEh
0x180037d7e  mov     r8, rsi; unsigned __int8 *
0x180037d81  shl     rbx, 7
0x180037d85  add     rbx, r15
0x180037d88  mov     rcx, rbx; this
0x180037d8b  mov     byte ptr [rbx+42h], 2
0x180037d8f  movzx   edx, word ptr [rsi+40h]; unsigned __int16
0x180037d93  call    ?Set@CDfName@@QEAAXGPEBE@Z; CDfName::Set(ushort,uchar const *)
0x180037d98  mov     eax, [rsi+44h]
0x180037d9b  add     ebp, r12d
0x180037d9e  mov     r9, [rsp+108h+var_D0]
0x180037da3  mov     [rbx+74h], eax
0x180037da6  mov     eax, [rsi+48h]
0x180037da9  mov     [rbx+78h], rax
0x180037dad  or      [rbx+43h], r12b
0x180037db1  mov     rsi, [rsi+50h]
0x180037db5  test    rsi, rsi
0x180037db8  jnz     short loc_180037D46
0x180037dba  mov     rbx, [rsp+108h+var_B0]
0x180037dbf  mov     edx, 5; unsigned int
0x180037dc4  mov     rcx, rbx; this
0x180037dc7  call    ?Init@CDirEntry@@QEAAXK@Z; CDirEntry::Init(ulong)
0x180037dcc  mov     edx, 16h; unsigned __int16
0x180037dd1  lea     r8, [rsp+108h+var_98]; unsigned __int8 *
0x180037dd6  mov     rcx, rbx; this
0x180037dd9  call    ?Set@CDfName@@QEAAXGPEBE@Z; CDfName::Set(ushort,uchar const *)
0x180037dde  movups  xmm0, xmmword ptr [rdi+25Ch]
0x180037de5  mov     r8d, r12d; unsigned int
0x180037de8  mov     rdx, rbx; struct CDirEntry *
0x180037deb  mov     rcx, rdi; this
0x180037dee  movdqu  xmmword ptr [rbx+50h], xmm0
0x180037df3  or      [rbx+43h], r12b
0x180037df7  mov     r9d, [rdi+280h]; unsigned int
0x180037dfe  call    ?BuildTree@CSimpStorage@@IEAAKPEAVCDirEntry@@KK@Z; CSimpStorage::BuildTree(CDirEntry *,ulong,ulong)
0x180037e03  mov     [rbx+4Ch], eax
0x180037e06  xor     r9d, r9d; dwMoveMethod
0x180037e09  mov     edx, [rdi+258h]
0x180037e0f  xor     r8d, r8d; lpDistanceToMoveHigh
0x180037e12  mov     rcx, [rdi+40h]; hFile
0x180037e16  add     edx, r12d
0x180037e19  shl     edx, 9; lDistanceToMove
0x180037e1c  mov     [rsp+108h+NumberOfBytesWritten], r13d
0x180037e21  call    cs:__imp_SetFilePointer
0x180037e27  or      ebx, 0FFFFFFFFh
0x180037e2a  cmp     eax, ebx
0x180037e2c  jz      short loc_180037E9F
0x180037e2e  mov     r8d, [rsp+108h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x180037e33  lea     r9, [rsp+108h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180037e38  mov     rdx, [rdi+250h]; lpBuffer
0x180037e3f  mov     rcx, [rdi+40h]; hFile
0x180037e43  mov     [rsp+108h+lpOverlapped], r13; lpOverlapped
0x180037e48  call    cs:__imp_WriteFile
0x180037e4e  test    eax, eax
0x180037e50  jz      short loc_180037E9F
0x180037e52  mov     rcx, [rdi+40h]; hFile
0x180037e56  xor     r9d, r9d; dwMoveMethod
0x180037e59  xor     r8d, r8d; lpDistanceToMoveHigh
0x180037e5c  xor     edx, edx; lDistanceToMove
0x180037e5e  call    cs:__imp_SetFilePointer
0x180037e64  cmp     eax, ebx
0x180037e66  jz      short loc_180037E9F
0x180037e68  mov     rcx, [rdi+40h]; hFile
0x180037e6c  lea     r9, [rsp+108h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180037e71  mov     r8d, 200h; nNumberOfBytesToWrite
0x180037e77  mov     [rsp+108h+lpOverlapped], r13; lpOverlapped
0x180037e7c  lea     rdx, [rdi+4Ch]; lpBuffer
0x180037e80  call    cs:__imp_WriteFile
0x180037e86  test    eax, eax
0x180037e88  jz      short loc_180037E9F
0x180037e8a  test    byte ptr [rsp+108h+var_B4], 4
0x180037e8f  jnz     short loc_180037EC8
0x180037e91  mov     rcx, [rdi+40h]; hFile
0x180037e95  call    cs:__imp_FlushFileBuffers
0x180037e9b  test    eax, eax
0x180037e9d  jnz     short loc_180037EC8
0x180037e9f  call    cs:__imp_GetLastError
0x180037ea5  mov     ecx, eax; unsigned int
0x180037ea7  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x180037eac  mov     rcx, [rdi+250h]; void *
0x180037eb3  mov     rdx, r12; unsigned __int64
0x180037eb6  mov     ebx, eax
0x180037eb8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180037ebd  mov     eax, ebx
0x180037ebf  mov     [rdi+250h], r13
0x180037ec6  jmp     short loc_180037EEC
0x180037ec8  mov     rcx, [rdi+250h]; void *
0x180037ecf  mov     rdx, r12; unsigned __int64
0x180037ed2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180037ed7  mov     [rdi+250h], r13
0x180037ede  mov     [rdi+48h], r13d
0x180037ee2  jmp     loc_180037AF6
0x180037ee7  mov     eax, 800300FFh
0x180037eec  add     rsp, 0C8h
  ... truncated ...
```
