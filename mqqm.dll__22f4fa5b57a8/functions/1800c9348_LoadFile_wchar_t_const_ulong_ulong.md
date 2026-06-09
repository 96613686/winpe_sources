# LoadFile(wchar_t const *,ulong *,ulong *)

- ea: `0x1800c9348`
- end: `0x1800c961f`
- name: `?LoadFile@@YAPEA_WPEB_WPEAK1@Z`
- size: `727`
- prototype: `wchar_t *__fastcall(const wchar_t *, unsigned int *, unsigned int *)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800c7058`
- `0x1800c726c`
- `0x1800c7480`
- `0x1800c7694`
- `0x1800c8f88`

## callees

- `0x180004d91`
- `0x18000e558`
- `0x18000f7e4`
- `0x1800261c0`
- `0x18009bd1c`
- `0x1800c9348`
- `0x1800ce9ac`

## import_xrefs

- `msvcrt!free` at `0x1800c956f`
- `msvcrt!free` at `0x1800c95ee`
- `msvcrt!free` at `0x1800c95f8`
- `msvcrt!free` at `0x1800c956f`
- `msvcrt!free` at `0x1800c95ee`
- `msvcrt!free` at `0x1800c95f8`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c953d`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800c953d`
- `KERNEL32!GetLastError` at `0x1800c93a2`
- `KERNEL32!GetLastError` at `0x1800c940d`
- `KERNEL32!GetLastError` at `0x1800c949c`
- `KERNEL32!GetLastError` at `0x1800c93a2`
- `KERNEL32!GetLastError` at `0x1800c940d`
- `KERNEL32!GetLastError` at `0x1800c949c`
- `KERNEL32!CreateFileW` at `0x1800c938f`
- `KERNEL32!CreateFileW` at `0x1800c938f`
- `KERNEL32!GetFileSize` at `0x1800c9400`
- `KERNEL32!GetFileSize` at `0x1800c9400`
- `KERNEL32!ReadFile` at `0x1800c9492`
- `KERNEL32!ReadFile` at `0x1800c9492`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
wchar_t *__fastcall LoadFile(const wchar_t *a1, unsigned int *a2, unsigned int *a3)
{
  HANDLE FileW; // rax
  void *v6; // rbx
  DWORD LastError; // eax
  unsigned int v8; // ebx
  DWORD FileSize; // eax
  unsigned __int64 v10; // rsi
  DWORD v11; // eax
  unsigned int v12; // ebx
  void *v13; // rdi
  DWORD v14; // eax
  unsigned int v15; // ebx
  _BYTE *v16; // rdx
  __int16 *v17; // rcx
  bool v19; // al
  _BYTE *v20; // rdx
  char *v21; // rcx
  wchar_t *v22; // rbx
  unsigned __int64 v23; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v24[2]; // [rsp+48h] [rbp-21h] BYREF
  __int128 pExceptionObject; // [rsp+58h] [rbp-11h] BYREF
  __int64 v26; // [rsp+68h] [rbp-1h]
  DWORD NumberOfBytesRead; // [rsp+E8h] [rbp+7Fh] BYREF

  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  v6 = FileW;
  v24[0] = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
    bad_win32_error::bad_win32_error((bad_win32_error *)&pExceptionObject, v8);
    throw (bad_win32_error *)&pExceptionObject;
  }
  FileSize = GetFileSize(FileW, 0);
  v10 = FileSize;
  if ( FileSize == -1 )
  {
    v11 = GetLastError();
    v12 = v11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11);
    bad_win32_error::bad_win32_error((bad_win32_error *)&pExceptionObject, v12);
    throw (bad_win32_error *)&pExceptionObject;
  }
  v13 = MmAllocate(FileSize);
  v24[1] = v13;
  NumberOfBytesRead = 0;
  if ( !ReadFile(v6, v13, v10, &NumberOfBytesRead, 0) )
  {
    v14 = GetLastError();
    v15 = v14;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), v14);
    bad_win32_error::bad_win32_error((bad_win32_error *)&pExceptionObject, v15);
    throw (bad_win32_error *)&pExceptionObject;
  }
  if ( v10 < 2 )
    goto LABEL_24;
  v16 = v13;
  v17 = (__int16 *)byte_180107E64;
  do
  {
    if ( *(_BYTE *)v17 != *v16 )
      break;
    v17 = (__int16 *)((char *)v17 + 1);
    ++v16;
  }
  while ( v17 != &word_180107E66 );
  if ( v17 == &word_180107E66 )
  {
    if ( (v10 & 1) != 0 )
    {
      pExceptionObject = 0;
      v26 = 0;
      exception::exception((exception *)&pExceptionObject);
      *(_QWORD *)&pExceptionObject = &bad_route::`vftable';
      throw (bad_unicode_file *)&pExceptionObject;
    }
    *a2 = (unsigned int)v10 >> 1;
    *a3 = 1;
    free(0);
    CAutoCloseFileHandle::~CAutoCloseFileHandle((CAutoCloseFileHandle *)v24);
    return (wchar_t *)v13;
  }
  else
  {
LABEL_24:
    if ( v10 >= 3 )
    {
      v20 = v13;
      v21 = byte_180107E60;
      do
      {
        if ( *v21 != *v20 )
          break;
        ++v21;
        ++v20;
      }
      while ( v21 != &byte_180107E63 );
      v19 = v21 == &byte_180107E63;
    }
    else
    {
      v19 = 0;
    }
    v23 = 0;
    v22 = UtlUtf8ToWcs((LPCCH)v13 + (v19 ? 3 : 0), (unsigned int)v10 - (v19 ? 3 : 0), &v23);
    *a2 = v23;
    *a3 = 0;
    free(0);
    free(v13);
    CAutoCloseFileHandle::~CAutoCloseFileHandle((CAutoCloseFileHandle *)v24);
    return v22;
  }
}

```

## disassembly

```asm
0x1800c9348  push    rbp
0x1800c934a  push    rbx
0x1800c934b  push    rsi
0x1800c934c  push    rdi
0x1800c934d  push    r12
0x1800c934f  push    r13
0x1800c9351  push    r14
0x1800c9353  push    r15
0x1800c9355  lea     rbp, [rsp-1Fh]
0x1800c935a  sub     rsp, 88h
0x1800c9361  mov     r12, r8
0x1800c9364  mov     r13, rdx
0x1800c9367  mov     r14, rcx
0x1800c936a  mov     [rsp+0C0h+hTemplateFile], 0; hTemplateFile
0x1800c9373  mov     [rsp+0C0h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800c937b  mov     [rsp+0C0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800c9383  xor     r9d, r9d; lpSecurityAttributes
0x1800c9386  mov     edx, 80000000h; dwDesiredAccess
0x1800c938b  lea     r8d, [r9+1]; dwShareMode
0x1800c938f  call    cs:__imp_CreateFileW
0x1800c9395  mov     rbx, rax
0x1800c9398  mov     [rbp+57h+var_78], rax
0x1800c939c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c93a0  jnz     short loc_1800C93FB
0x1800c93a2  call    cs:__imp_GetLastError
0x1800c93a8  mov     ebx, eax
0x1800c93aa  lea     rdx, WPP_GLOBAL_Control
0x1800c93b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c93b8  cmp     rcx, rdx
0x1800c93bb  jz      short loc_1800C93DF
0x1800c93bd  test    byte ptr [rcx+1Ch], 1
0x1800c93c1  jz      short loc_1800C93DF
0x1800c93c3  mov     edx, 0Ah
0x1800c93c8  mov     [rsp+0C0h+dwCreationDisposition], eax; char
0x1800c93cc  mov     r9, r14
0x1800c93cf  lea     r8, WPP_599bcc5d8bdb3e71d05f73bea05937d7_Traceguids
0x1800c93d6  mov     rcx, [rcx+10h]; LoggerHandle
0x1800c93da  call    WPP_SF_Sd
0x1800c93df  mov     edx, ebx; unsigned int
0x1800c93e1  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800c93e5  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800c93ea  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800c93f1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c93f5  call    _CxxThrowException_0
0x1800c93fb  xor     edx, edx; lpFileSizeHigh
0x1800c93fd  mov     rcx, rbx; hFile
0x1800c9400  call    cs:__imp_GetFileSize
0x1800c9406  mov     esi, eax
0x1800c9408  cmp     eax, 0FFFFFFFFh
0x1800c940b  jnz     short loc_1800C9466
0x1800c940d  call    cs:__imp_GetLastError
0x1800c9413  mov     ebx, eax
0x1800c9415  lea     rdx, WPP_GLOBAL_Control
0x1800c941c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9423  cmp     rcx, rdx
0x1800c9426  jz      short loc_1800C944A
0x1800c9428  test    byte ptr [rcx+1Ch], 1
0x1800c942c  jz      short loc_1800C944A
0x1800c942e  mov     edx, 0Bh
0x1800c9433  mov     [rsp+0C0h+dwCreationDisposition], eax; char
0x1800c9437  mov     r9, r14
0x1800c943a  lea     r8, WPP_599bcc5d8bdb3e71d05f73bea05937d7_Traceguids
0x1800c9441  mov     rcx, [rcx+10h]; LoggerHandle
0x1800c9445  call    WPP_SF_Sd
0x1800c944a  mov     edx, ebx; unsigned int
0x1800c944c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800c9450  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800c9455  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800c945c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c9460  call    _CxxThrowException_0
0x1800c9466  mov     rcx, rsi; unsigned __int64
0x1800c9469  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800c946e  mov     rdi, rax
0x1800c9471  mov     [rbp+57h+var_70], rax
0x1800c9475  mov     [rbp+57h+NumberOfBytesRead], 0
0x1800c947c  mov     qword ptr [rsp+0C0h+dwCreationDisposition], 0; lpOverlapped
0x1800c9485  lea     r9, [rbp+57h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800c9489  mov     r8d, esi; nNumberOfBytesToRead
0x1800c948c  mov     rdx, rax; lpBuffer
0x1800c948f  mov     rcx, rbx; hFile
0x1800c9492  call    cs:__imp_ReadFile
0x1800c9498  test    eax, eax
0x1800c949a  jnz     short loc_1800C94F5
0x1800c949c  call    cs:__imp_GetLastError
0x1800c94a2  mov     ebx, eax
0x1800c94a4  lea     rdx, WPP_GLOBAL_Control
0x1800c94ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c94b2  cmp     rcx, rdx
0x1800c94b5  jz      short loc_1800C94D9
0x1800c94b7  test    byte ptr [rcx+1Ch], 1
0x1800c94bb  jz      short loc_1800C94D9
0x1800c94bd  mov     edx, 0Ch
0x1800c94c2  mov     [rsp+0C0h+dwCreationDisposition], eax; char
0x1800c94c6  mov     r9, r14
0x1800c94c9  lea     r8, WPP_599bcc5d8bdb3e71d05f73bea05937d7_Traceguids
0x1800c94d0  mov     rcx, [rcx+10h]; LoggerHandle
0x1800c94d4  call    WPP_SF_Sd
0x1800c94d9  mov     edx, ebx; unsigned int
0x1800c94db  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800c94df  call    ??0bad_win32_error@@QEAA@K@Z; bad_win32_error::bad_win32_error(ulong)
0x1800c94e4  lea     rdx, _TI3?AVbad_win32_error@@; pThrowInfo
0x1800c94eb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c94ef  call    _CxxThrowException_0
0x1800c94f5  cmp     rsi, 2
0x1800c94f9  jb      loc_1800C9587
0x1800c94ff  mov     rdx, rdi
0x1800c9502  lea     rcx, byte_180107E64
0x1800c9509  lea     r8, word_180107E66
0x1800c9510  mov     al, [rdx]
0x1800c9512  cmp     [rcx], al
0x1800c9514  jnz     short loc_1800C9521
0x1800c9516  inc     rcx
0x1800c9519  inc     rdx
0x1800c951c  cmp     rcx, r8
0x1800c951f  jnz     short loc_1800C9510
0x1800c9521  cmp     rcx, r8
0x1800c9524  jnz     short loc_1800C9587
0x1800c9526  test    sil, 1
0x1800c952a  jz      short loc_1800C955F
0x1800c952c  xorps   xmm0, xmm0
0x1800c952f  xor     eax, eax
0x1800c9531  movups  [rbp+57h+pExceptionObject], xmm0
0x1800c9535  mov     [rbp+57h+var_58], rax
0x1800c9539  lea     rcx, [rbp+57h+pExceptionObject]
0x1800c953d  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x1800c9543  lea     rax, ??_7bad_route@@6B@; const bad_route::`vftable'
0x1800c954a  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x1800c954e  lea     rdx, _TI2?AVbad_unicode_file@@; pThrowInfo
0x1800c9555  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800c9559  call    _CxxThrowException_0
0x1800c955f  shr     esi, 1
0x1800c9561  mov     [r13+0], esi
0x1800c9565  mov     dword ptr [r12], 1
0x1800c956d  xor     ecx, ecx; Block
0x1800c956f  call    cs:__imp_free
0x1800c9575  nop
0x1800c9576  lea     rcx, [rbp+57h+var_78]; this
0x1800c957a  call    ??1CAutoCloseFileHandle@@QEAA@XZ; CAutoCloseFileHandle::~CAutoCloseFileHandle(void)
0x1800c957f  mov     rax, rdi
0x1800c9582  jmp     loc_1800C960B
0x1800c9587  cmp     rsi, 3
0x1800c958b  jnb     short loc_1800C9591
0x1800c958d  xor     al, al
0x1800c958f  jmp     short loc_1800C95B9
0x1800c9591  mov     rdx, rdi
0x1800c9594  lea     rcx, byte_180107E60
0x1800c959b  lea     r8, byte_180107E63
0x1800c95a2  mov     al, [rdx]
0x1800c95a4  cmp     [rcx], al
0x1800c95a6  jnz     short loc_1800C95B3
0x1800c95a8  inc     rcx
0x1800c95ab  inc     rdx
0x1800c95ae  cmp     rcx, r8
0x1800c95b1  jnz     short loc_1800C95A2
0x1800c95b3  cmp     rcx, r8
0x1800c95b6  setz    al
0x1800c95b9  neg     al
0x1800c95bb  sbb     eax, eax
0x1800c95bd  and     eax, 3
0x1800c95c0  mov     ecx, eax
0x1800c95c2  mov     [rbp+57h+var_80], 0
0x1800c95ca  sub     esi, eax
0x1800c95cc  mov     edx, esi; cbMultiByte
0x1800c95ce  add     rcx, rdi; lpMultiByteStr
0x1800c95d1  lea     r8, [rbp+57h+var_80]; unsigned __int64 *
0x1800c95d5  call    ?UtlUtf8ToWcs@@YAPEA_WPEBE_KPEA_K@Z; UtlUtf8ToWcs(uchar const *,unsigned __int64,unsigned __int64 *)
0x1800c95da  mov     rbx, rax
0x1800c95dd  mov     eax, dword ptr [rbp+57h+var_80]
0x1800c95e0  mov     [r13+0], eax
0x1800c95e4  mov     dword ptr [r12], 0
0x1800c95ec  xor     ecx, ecx; Block
0x1800c95ee  call    cs:__imp_free
0x1800c95f4  nop
0x1800c95f5  mov     rcx, rdi; Block
0x1800c95f8  call    cs:__imp_free
0x1800c95fe  nop
0x1800c95ff  lea     rcx, [rbp+57h+var_78]; this
0x1800c9603  call    ??1CAutoCloseFileHandle@@QEAA@XZ; CAutoCloseFileHandle::~CAutoCloseFileHandle(void)
0x1800c9608  mov     rax, rbx
0x1800c960b  add     rsp, 88h
0x1800c9612  pop     r15
0x1800c9614  pop     r14
0x1800c9616  pop     r13
0x1800c9618  pop     r12
0x1800c961a  pop     rdi
0x1800c961b  pop     rsi
0x1800c961c  pop     rbx
0x1800c961d  pop     rbp
0x1800c961e  retn
```
