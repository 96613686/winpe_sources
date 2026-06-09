# Csl::ReadEntireFile(ushort const *,utl::vector<uchar,utl::allocator<uchar>> &)

- ea: `0x14000c44c`
- end: `0x14000c65f`
- name: `?ReadEntireFile@Csl@@YAJPEBGAEAV?$vector@EV?$allocator@E@utl@@@utl@@@Z`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x14001694c`

## callees

- `0x140002344`
- `0x140002b2c`
- `0x140006fc4`
- `0x140006fe4`
- `0x14000c44c`
- `0x14000ce58`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c4f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c5b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c637`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c4f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c5b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c637`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14000c4bf`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14000c4bf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000c48b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000c48b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000c56f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000c56f`

## pseudocode

```c
__int64 __fastcall Csl::ReadEntireFile(const WCHAR *a1, __int64 a2)
{
  HANDLE FileW; // rax
  const char *v4; // r9
  void *v5; // rbx
  DWORD FileSize; // eax
  const char *v8; // r9
  size_t v9; // r14
  unsigned int LastError; // edi
  __int64 v11; // r12
  void *v12; // rdi
  char *v13; // rsi
  const char *v14; // r9
  unsigned int v15; // esi
  void *v16; // rcx
  int lpOverlapped; // [rsp+20h] [rbp-40h]
  void *lpBuffer[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  DWORD NumberOfBytesRead; // [rsp+A0h] [rbp+40h] BYREF

  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  v5 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x5EF,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
             v4);
  FileSize = GetFileSize(FileW, 0);
  v9 = FileSize;
  if ( FileSize == -1 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x5F3,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
                  v8);
LABEL_5:
    if ( v5 )
      CloseHandle(v5);
    return LastError;
  }
  v11 = -1;
  NumberOfBytesRead = 0;
  v19 = -1;
  *(__m128i *)lpBuffer = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( FileSize )
  {
    if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(lpBuffer, FileSize) )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5FA,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
        (const char *)0x8007000ELL,
        lpOverlapped);
      if ( lpBuffer[0] != (void *)-1LL )
        operator delete(lpBuffer[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_5;
    }
    memset_0(lpBuffer[1], 0, v9);
    v12 = lpBuffer[0];
    v11 = v19;
    v13 = (char *)lpBuffer[0] + v9;
    if ( !ReadFile(v5, lpBuffer[0], v9, &NumberOfBytesRead, 0) )
    {
      v15 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x601,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
              v14);
      if ( v12 != (void *)-1LL )
        operator delete(v12, (const struct std::nothrow_t *)&std::nothrow);
      if ( v5 )
        CloseHandle(v5);
      return v15;
    }
  }
  else
  {
    v13 = (char *)lpBuffer[1];
    v12 = lpBuffer[0];
  }
  v16 = *(void **)a2;
  if ( *(_QWORD *)a2 != -1 )
  {
    *(_QWORD *)(a2 + 8) = v16;
    operator delete(v16, (const struct std::nothrow_t *)&std::nothrow);
  }
  *(_QWORD *)a2 = v12;
  *(_QWORD *)(a2 + 8) = v13;
  *(_QWORD *)(a2 + 16) = v11;
  if ( v5 )
    CloseHandle(v5);
  return 0;
}

```

## disassembly

```asm
0x14000c44c  mov     rax, rsp
0x14000c44f  mov     [rax+8], rbx
0x14000c453  mov     [rax+10h], rsi
0x14000c457  push    rbp
0x14000c458  push    rdi
0x14000c459  push    r12
0x14000c45b  push    r14
0x14000c45d  push    r15
0x14000c45f  mov     rbp, rsp
0x14000c462  sub     rsp, 60h
0x14000c466  mov     qword ptr [rax-58h], 0
0x14000c46e  xor     r9d, r9d; lpSecurityAttributes
0x14000c471  mov     r15, rdx
0x14000c474  mov     dword ptr [rax-60h], 0
0x14000c47b  mov     edx, 80000000h; dwDesiredAccess
0x14000c480  mov     dword ptr [rax-68h], 3
0x14000c487  lea     r8d, [r9+1]; dwShareMode
0x14000c48b  call    cs:__imp_CreateFileW
0x14000c492  nop     dword ptr [rax+rax+00h]
0x14000c497  mov     rbx, rax
0x14000c49a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000c49e  jnz     short loc_14000C4BA
0x14000c4a0  mov     rcx, [rbp+28h]; this
0x14000c4a4  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000c4ab  mov     edx, 5EFh; void *
0x14000c4b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c4b5  jmp     loc_14000C645
0x14000c4ba  xor     edx, edx; lpFileSizeHigh
0x14000c4bc  mov     rcx, rbx; hFile
0x14000c4bf  call    cs:__imp_GetFileSize
0x14000c4c6  nop     dword ptr [rax+rax+00h]
0x14000c4cb  mov     r14d, eax
0x14000c4ce  cmp     eax, 0FFFFFFFFh
0x14000c4d1  jnz     short loc_14000C505
0x14000c4d3  mov     rcx, [rbp+28h]; this
0x14000c4d7  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000c4de  mov     edx, 5F3h; void *
0x14000c4e3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c4e8  mov     edi, eax
0x14000c4ea  test    rbx, rbx
0x14000c4ed  jz      short loc_14000C4FE
0x14000c4ef  mov     rcx, rbx; hObject
0x14000c4f2  call    cs:__imp_CloseHandle
0x14000c4f9  nop     dword ptr [rax+rax+00h]
0x14000c4fe  mov     eax, edi
0x14000c500  jmp     loc_14000C645
0x14000c505  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000c50d  or      r12, 0FFFFFFFFFFFFFFFFh
0x14000c511  mov     [rbp+NumberOfBytesRead], 0
0x14000c518  mov     [rbp+var_10], r12
0x14000c51c  movdqu  xmmword ptr [rbp+lpBuffer], xmm0
0x14000c521  test    eax, eax
0x14000c523  jz      loc_14000C603
0x14000c529  mov     rdx, r14
0x14000c52c  lea     rcx, [rbp+lpBuffer]
0x14000c530  mov     rsi, r14
0x14000c533  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x14000c538  test    al, al
0x14000c53a  jz      loc_14000C5C7
0x14000c540  mov     rcx, [rbp+lpBuffer+8]; void *
0x14000c544  mov     r8, r14; Size
0x14000c547  xor     edx, edx; Val
0x14000c549  call    memset_0
0x14000c54e  mov     rdi, [rbp+lpBuffer]
0x14000c552  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x14000c556  mov     r12, [rbp+var_10]
0x14000c55a  mov     rdx, rdi; lpBuffer
0x14000c55d  mov     r8d, r14d; nNumberOfBytesToRead
0x14000c560  mov     qword ptr [rsp+60h+lpOverlapped], 0; lpOverlapped
0x14000c569  mov     rcx, rbx; hFile
0x14000c56c  add     rsi, rdi
0x14000c56f  call    cs:__imp_ReadFile
0x14000c576  nop     dword ptr [rax+rax+00h]
0x14000c57b  test    eax, eax
0x14000c57d  jnz     loc_14000C60B
0x14000c583  mov     rcx, [rbp+28h]; this
0x14000c587  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000c58e  mov     edx, 601h; void *
0x14000c593  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c598  mov     esi, eax
0x14000c59a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000c59e  jz      short loc_14000C5AF
0x14000c5a0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c5a7  mov     rcx, rdi; void *
0x14000c5aa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c5af  test    rbx, rbx
0x14000c5b2  jz      short loc_14000C5C3
0x14000c5b4  mov     rcx, rbx; hObject
0x14000c5b7  call    cs:__imp_CloseHandle
0x14000c5be  nop     dword ptr [rax+rax+00h]
0x14000c5c3  mov     eax, esi
0x14000c5c5  jmp     short loc_14000C645
0x14000c5c7  mov     rcx, [rbp+28h]; this
0x14000c5cb  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000c5d2  mov     edi, 8007000Eh
0x14000c5d7  mov     edx, 5FAh; void *
0x14000c5dc  mov     r9d, edi; char *
0x14000c5df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c5e4  mov     rcx, [rbp+lpBuffer]; void *
0x14000c5e8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000c5ec  jz      loc_14000C4EA
0x14000c5f2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c5f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c5fe  jmp     loc_14000C4EA
0x14000c603  mov     rsi, [rbp+lpBuffer+8]
0x14000c607  mov     rdi, [rbp+lpBuffer]
0x14000c60b  mov     rcx, [r15]; void *
0x14000c60e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000c612  jz      short loc_14000C624
0x14000c614  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000c61b  mov     [r15+8], rcx
0x14000c61f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000c624  mov     [r15], rdi
0x14000c627  mov     [r15+8], rsi
0x14000c62b  mov     [r15+10h], r12
0x14000c62f  test    rbx, rbx
0x14000c632  jz      short loc_14000C643
0x14000c634  mov     rcx, rbx; hObject
0x14000c637  call    cs:__imp_CloseHandle
0x14000c63e  nop     dword ptr [rax+rax+00h]
0x14000c643  xor     eax, eax
0x14000c645  lea     r11, [rsp+60h+var_s0]
0x14000c64a  mov     rbx, [r11+30h]
0x14000c64e  mov     rsi, [r11+38h]
0x14000c652  mov     rsp, r11
0x14000c655  pop     r15
0x14000c657  pop     r14
0x14000c659  pop     r12
0x14000c65b  pop     rdi
0x14000c65c  pop     rbp
0x14000c65d  retn
```
