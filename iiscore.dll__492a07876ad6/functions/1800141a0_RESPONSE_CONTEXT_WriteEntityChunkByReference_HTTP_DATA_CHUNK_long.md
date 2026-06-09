# RESPONSE_CONTEXT::WriteEntityChunkByReference(_HTTP_DATA_CHUNK *,long)

- ea: `0x1800141a0`
- end: `0x1800143c9`
- name: `?WriteEntityChunkByReference@RESPONSE_CONTEXT@@UEAAJPEAU_HTTP_DATA_CHUNK@@J@Z`
- size: `553`
- prototype: `DWORD __fastcall(RESPONSE_CONTEXT *this, struct _HTTP_DATA_CHUNK *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800141a0`
- `0x18003772e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014314`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014314`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800142c8`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800142c8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001424a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800142f8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014370`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001424a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800142f8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014370`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180014216`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180014216`

## pseudocode

```c
DWORD __fastcall RESPONSE_CONTEXT::WriteEntityChunkByReference(
        RESPONSE_CONTEXT *this,
        struct _HTTP_DATA_CHUNK *a2,
        int a3)
{
  __int64 v3; // r14
  __int64 v5; // rbp
  BOOL v6; // esi
  void *v7; // rdi
  unsigned int v8; // esi
  char *v9; // rax
  char *v10; // rdi
  __int64 v11; // rcx
  ULARGE_INTEGER Length; // rax
  HANDLE FileHandle; // rcx
  const void *v14; // rdi
  size_t v15; // rsi
  void *Ptr; // rax
  unsigned int v17; // eax
  __int64 v18; // rsi
  _LARGE_INTEGER FileSize; // [rsp+40h] [rbp+8h] BYREF

  v3 = a3;
  if ( !a2 )
  {
    Length.LowPart = -2147024809;
    return Length.LowPart;
  }
  v5 = *((_QWORD *)this + 1);
  if ( (unsigned __int16)(*(_WORD *)(v5 + 592) + 1) < *(_WORD *)(v5 + 592) )
  {
    Length.LowPart = -2147024362;
    return Length.LowPart;
  }
  if ( a2->DataChunkType != HttpDataChunkFromFileHandle )
    goto LABEL_4;
  Length = a2->FromFileHandle.ByteRange.Length;
  if ( !Length.QuadPart )
    return Length.LowPart;
  if ( Length.QuadPart != -1 )
    goto LABEL_4;
  FileHandle = a2->FromFileHandle.FileHandle;
  FileSize.QuadPart = 0;
  if ( GetFileSizeEx(FileHandle, &FileSize) )
  {
    a2->FromFileHandle.ByteRange.Length.QuadPart = FileSize.QuadPart
                                                 - a2->FromFileHandle.ByteRange.StartingOffset.QuadPart;
LABEL_4:
    v6 = 0;
    v7 = *(void **)(v5 + 600);
    if ( v7 )
      v6 = BUFFER::QueryPtr((BUFFER *)(v5 + 1000)) != v7;
    if ( !BUFFER::Resize((BUFFER *)(v5 + 1000), 32 * (*(unsigned __int16 *)(v5 + 592) + 1), 0x200u) )
      return -2147024888;
    if ( v6 )
    {
      v14 = *(const void **)(v5 + 600);
      v15 = 32LL * *(unsigned __int16 *)(v5 + 592);
      Ptr = BUFFER::QueryPtr((BUFFER *)(v5 + 1000));
      memmove_0(Ptr, v14, v15);
    }
    v8 = *(unsigned __int16 *)(v5 + 592);
    *(_WORD *)(v5 + 592) = v8 + 1;
    v9 = (char *)BUFFER::QueryPtr((BUFFER *)(v5 + 1000));
    *(_QWORD *)(v5 + 600) = v9;
    v10 = v9;
    if ( (_DWORD)v3 == -1 )
    {
      v11 = 32LL * v8;
      *(_OWORD *)&v9[v11] = *(_OWORD *)&a2->DataChunkType;
      *(_OWORD *)&v9[v11 + 16] = *(_OWORD *)&a2->FromFragmentCacheEx.ByteRange.Length.LowPart;
    }
    else
    {
      v17 = v8;
      v18 = 32 * v3;
      if ( v17 > (unsigned int)v3 )
        memmove_0(&v10[v18 + 32], &v10[v18], 32LL * (v17 - (unsigned int)v3));
      *(_OWORD *)&v10[32 * v3] = *(_OWORD *)&a2->DataChunkType;
      *(_OWORD *)&v10[v18 + 16] = *(_OWORD *)&a2->FromFragmentCacheEx.ByteRange.Length.LowPart;
    }
    Length.LowPart = 0;
    return Length.LowPart;
  }
  Length.LowPart = GetLastError();
  if ( (int)Length.LowPart > 0 )
    Length.LowPart = LOWORD(Length.QuadPart) | 0x80070000;
  return Length.LowPart;
}

```

## disassembly

```asm
0x1800141a0  push    rbx
0x1800141a2  push    r14
0x1800141a4  sub     rsp, 28h
0x1800141a8  movsxd  r14, r8d
0x1800141ab  mov     rbx, rdx
0x1800141ae  test    rdx, rdx
0x1800141b1  jz      loc_18001433E
0x1800141b7  mov     [rsp+38h+arg_8], rbp
0x1800141bc  mov     rbp, [rcx+8]
0x1800141c0  movzx   ecx, word ptr [rbp+250h]
0x1800141c7  lea     eax, [rcx+1]
0x1800141ca  cmp     ax, cx
0x1800141cd  jb      loc_180014348
0x1800141d3  cmp     dword ptr [rdx], 1
0x1800141d6  jz      loc_18001429F
0x1800141dc  mov     [rsp+38h+arg_10], rsi
0x1800141e1  xor     esi, esi
0x1800141e3  mov     [rsp+38h+arg_18], rdi
0x1800141e8  mov     rdi, [rbp+258h]
0x1800141ef  mov     [rsp+38h+var_18], r15
0x1800141f4  test    rdi, rdi
0x1800141f7  jnz     loc_1800142F1
0x1800141fd  movzx   edx, word ptr [rbp+250h]
0x180014204  lea     rcx, [rbp+3E8h]
0x18001420b  inc     edx
0x18001420d  mov     r8d, 200h
0x180014213  shl     edx, 5
0x180014216  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x18001421d  nop     dword ptr [rax+rax+00h]
0x180014222  test    al, al
0x180014224  jz      loc_1800142EA
0x18001422a  test    esi, esi
0x18001422c  jnz     loc_180014357
0x180014232  movzx   esi, word ptr [rbp+250h]
0x180014239  lea     rcx, [rbp+3E8h]
0x180014240  lea     eax, [rsi+1]
0x180014243  mov     [rbp+250h], ax
0x18001424a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180014251  nop     dword ptr [rax+rax+00h]
0x180014256  mov     [rbp+258h], rax
0x18001425d  mov     rdi, rax
0x180014260  cmp     r14d, 0FFFFFFFFh
0x180014264  jnz     loc_18001438F
0x18001426a  movups  xmm0, xmmword ptr [rbx]
0x18001426d  mov     ecx, esi
0x18001426f  shl     rcx, 5
0x180014273  movups  xmmword ptr [rcx+rax], xmm0
0x180014277  movups  xmm1, xmmword ptr [rbx+10h]
0x18001427b  movups  xmmword ptr [rcx+rax+10h], xmm1
0x180014280  xor     eax, eax
0x180014282  mov     rdi, [rsp+38h+arg_18]
0x180014287  mov     rsi, [rsp+38h+arg_10]
0x18001428c  mov     r15, [rsp+38h+var_18]
0x180014291  mov     rbp, [rsp+38h+arg_8]
0x180014296  add     rsp, 28h
0x18001429a  pop     r14
0x18001429c  pop     rbx
0x18001429d  retn
0x18001429f  mov     rax, [rdx+10h]
0x1800142a3  test    rax, rax
0x1800142a6  jz      loc_180014352
0x1800142ac  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800142b0  jnz     loc_1800141DC
0x1800142b6  mov     rcx, [rbx+18h]; hFile
0x1800142ba  lea     rdx, [rsp+38h+FileSize]; lpFileSize
0x1800142bf  mov     qword ptr [rsp+38h+FileSize], 0
0x1800142c8  call    cs:__imp_GetFileSizeEx
0x1800142cf  nop     dword ptr [rax+rax+00h]
0x1800142d4  test    eax, eax
0x1800142d6  jz      short loc_180014314
0x1800142d8  mov     rax, qword ptr [rsp+38h+FileSize]
0x1800142dd  sub     rax, [rbx+8]
0x1800142e1  mov     [rbx+10h], rax
0x1800142e5  jmp     loc_1800141DC
0x1800142ea  mov     eax, 80070008h
0x1800142ef  jmp     short loc_180014282
0x1800142f1  lea     rcx, [rbp+3E8h]
0x1800142f8  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800142ff  nop     dword ptr [rax+rax+00h]
0x180014304  cmp     rax, rdi
0x180014307  mov     ecx, 1
0x18001430c  cmovnz  esi, ecx
0x18001430f  jmp     loc_1800141FD
0x180014314  call    cs:__imp_GetLastError
0x18001431b  nop     dword ptr [rax+rax+00h]
0x180014320  test    eax, eax
0x180014322  jle     loc_180014291
0x180014328  mov     rbp, [rsp+38h+arg_8]
0x18001432d  movzx   eax, ax
0x180014330  or      eax, 80070000h
0x180014335  add     rsp, 28h
0x180014339  pop     r14
0x18001433b  pop     rbx
0x18001433c  retn
0x18001433e  mov     eax, 80070057h
0x180014343  jmp     loc_180014296
0x180014348  mov     eax, 80070216h
0x18001434d  jmp     loc_180014291
0x180014352  jmp     loc_180014291
0x180014357  movzx   esi, word ptr [rbp+250h]
0x18001435e  lea     rcx, [rbp+3E8h]
0x180014365  mov     rdi, [rbp+258h]
0x18001436c  shl     rsi, 5
0x180014370  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180014377  nop     dword ptr [rax+rax+00h]
0x18001437c  mov     r8, rsi; Size
0x18001437f  mov     rdx, rdi; Src
0x180014382  mov     rcx, rax; void *
0x180014385  call    memmove_0
0x18001438a  jmp     loc_180014232
0x18001438f  mov     eax, esi
0x180014391  mov     rsi, r14
0x180014394  shl     rsi, 5
0x180014398  cmp     eax, r14d
0x18001439b  jbe     short loc_1800143B4
0x18001439d  sub     eax, r14d
0x1800143a0  lea     rdx, [rdi+rsi]; Src
0x1800143a4  mov     r8d, eax
0x1800143a7  lea     rcx, [rdx+20h]; void *
0x1800143ab  shl     r8, 5; Size
0x1800143af  call    memmove_0
0x1800143b4  movups  xmm0, xmmword ptr [rbx]
0x1800143b7  movups  xmmword ptr [rdi+rsi], xmm0
0x1800143bb  movups  xmm1, xmmword ptr [rbx+10h]
0x1800143bf  movups  xmmword ptr [rdi+rsi+10h], xmm1
0x1800143c4  jmp     loc_180014280
```
