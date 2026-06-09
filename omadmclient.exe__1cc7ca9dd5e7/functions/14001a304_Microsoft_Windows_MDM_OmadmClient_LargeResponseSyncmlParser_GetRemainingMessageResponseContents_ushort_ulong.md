# Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::GetRemainingMessageResponseContents(ushort * *,ulong *)

- ea: `0x14001a304`
- end: `0x14001a620`
- name: `?GetRemainingMessageResponseContents@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@QEAAJPEAPEAGPEAK@Z`
- size: `796`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *__hidden this, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002b464`

## callees

- `0x140003eb4`
- `0x140005820`
- `0x14000b0d4`
- `0x14000b0f4`
- `0x140019680`
- `0x14001971c`
- `0x14001a304`
- `0x14001a7a0`
- `0x14001d7e4`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a54e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a54e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001a56d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14001a56d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a43a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a55f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a43a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a55f`
- `DMCmnUtils!MBToUnicode` at `0x14001a5bc`
- `DMCmnUtils!MBToUnicode` at `0x14001a5bc`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14001a584`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14001a584`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14001a509`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14001a509`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14001a407`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14001a407`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001a3c7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001a3c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::GetRemainingMessageResponseContents(
        const unsigned __int16 **this,
        unsigned __int16 **a2,
        unsigned int *a3)
{
  __int64 v6; // rdx
  unsigned int LastError; // ebx
  __int64 v8; // r9
  int v10; // eax
  const unsigned __int16 *v11; // rcx
  HANDLE FileW; // rax
  const char *v13; // r9
  void *v14; // rdi
  const char *v15; // r9
  DWORD LowPart; // r8d
  __int64 v17; // rax
  size_t v18; // rsi
  void *v19; // rax
  void *v20; // rcx
  _QWORD *v21; // rax
  char *v22; // rbx
  const char *v23; // r9
  DWORD v24; // ebx
  const char *v25; // r9
  int v26; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-40h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-40h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-40h]
  __int64 v30; // [rsp+40h] [rbp-20h] BYREF
  LPVOID lpBuffer[2]; // [rsp+48h] [rbp-18h] BYREF
  char *v32; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  DWORD NumberOfBytesRead; // [rsp+A8h] [rbp+48h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+B8h] [rbp+58h] BYREF

  v30 = -1;
  if ( !a2 )
  {
    v6 = 233;
LABEL_3:
    LastError = -2147024809;
    v8 = 2147942487LL;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)v8,
      dwCreationDisposition);
    return LastError;
  }
  if ( !a3 )
  {
    v6 = 234;
    goto LABEL_3;
  }
  *a2 = 0;
  *a3 = 0;
  if ( !*this )
  {
    v10 = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::InitializePersistFile(
            (Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *)this,
            this[1],
            0);
    LastError = v10;
    if ( v10 < 0 )
    {
      v8 = (unsigned int)v10;
      v6 = 241;
      goto LABEL_4;
    }
  }
  v11 = this[2];
  if ( v11 )
  {
    this[2] = 0;
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v11 + 16LL))(v11);
  }
  FileW = CreateFileW(*this, 0x80000000, 1u, 0, 3u, 0, 0);
  v14 = FileW;
  v30 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
    return (unsigned int)wil::details::in1diag3::Return_GetLastError(
                           retaddr,
                           (void *)0x100,
                           (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
                           v13);
  FileSize.QuadPart = 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x106,
                  (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
                  v15);
    goto LABEL_17;
  }
  LowPart = FileSize.LowPart;
  v17 = FileSize.LowPart + 1;
  if ( (unsigned int)v17 < FileSize.LowPart )
  {
    LastError = -2147024362;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)0x80070216LL,
      dwCreationDispositiona);
    goto LABEL_17;
  }
  v18 = (unsigned int)v17;
  *(_OWORD *)lpBuffer = 0;
  v32 = 0;
  if ( FileSize.LowPart != -1 )
  {
    if ( (unsigned int)v17 < 0x1000uLL )
    {
      v21 = operator new((unsigned int)v17);
    }
    else
    {
      if ( v17 + 39 <= (unsigned __int64)(unsigned int)v17 )
        __scrt_throw_std_bad_array_new_length();
      v19 = operator new(v17 + 39);
      v20 = v19;
      if ( !v19 )
        __fastfail(5u);
      v21 = (_QWORD *)(((unsigned __int64)v19 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v21 - 1) = v20;
    }
    lpBuffer[0] = v21;
    v22 = (char *)v21 + v18;
    v32 = (char *)v21 + v18;
    memset_0(v21, 0, v18);
    lpBuffer[1] = v22;
    v30 = 0;
    std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&v30);
    LowPart = FileSize.LowPart;
  }
  NumberOfBytesRead = 0;
  if ( !ReadFile(v14, lpBuffer[0], LowPart, &NumberOfBytesRead, 0) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x113,
                  (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
                  v23);
    std::vector<unsigned char>::~vector<unsigned char>(lpBuffer);
LABEL_17:
    if ( v14 )
      CloseHandle(v14);
    return LastError;
  }
  *((_BYTE *)lpBuffer[0] + FileSize.LowPart) = 0;
  if ( v14 )
  {
    v24 = GetLastError();
    CloseHandle(v14);
    SetLastError(v24);
  }
  v30 = -1;
  if ( !DeleteFileW(*this) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x11C,
                  (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
                  v25);
LABEL_37:
    std::vector<unsigned char>::~vector<unsigned char>(lpBuffer);
    return LastError;
  }
  v26 = MBToUnicode((const char *)lpBuffer[0], 0xFDE9u, a2, a3);
  LastError = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x124,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v26,
      dwCreationDispositionb);
    goto LABEL_37;
  }
  std::vector<unsigned char>::~vector<unsigned char>(lpBuffer);
  return 0;
}

```

## disassembly

```asm
0x14001a304  mov     [rsp-38h+arg_0], rbx
0x14001a309  push    rbp
0x14001a30a  push    rsi
0x14001a30b  push    rdi
0x14001a30c  push    r12
0x14001a30e  push    r13
0x14001a310  push    r14
0x14001a312  push    r15
0x14001a314  mov     rbp, rsp
0x14001a317  sub     rsp, 60h
0x14001a31b  mov     r15, r8
0x14001a31e  mov     r12, rdx
0x14001a321  mov     r14, rcx
0x14001a324  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x14001a32c  xor     r13d, r13d
0x14001a32f  test    rdx, rdx
0x14001a332  jnz     short loc_14001A359
0x14001a334  mov     edx, 0E9h; void *
0x14001a339  mov     ebx, 80070057h
0x14001a33e  mov     r9d, ebx; char *
0x14001a341  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001a348  mov     rcx, [rbp+38h]; this
0x14001a34c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a351  nop
0x14001a352  mov     eax, ebx
0x14001a354  jmp     loc_14001A601
0x14001a359  test    r15, r15
0x14001a35c  jnz     short loc_14001A365
0x14001a35e  mov     edx, 0EAh
0x14001a363  jmp     short loc_14001A339
0x14001a365  mov     [rdx], r13
0x14001a368  mov     [r8], r13d
0x14001a36b  cmp     [rcx], r13
0x14001a36e  jnz     short loc_14001A38C
0x14001a370  xor     r8d, r8d; int
0x14001a373  mov     rdx, [rcx+8]; unsigned __int16 *
0x14001a377  call    ?InitializePersistFile@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBGH@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::InitializePersistFile(ushort const *,int)
0x14001a37c  mov     ebx, eax
0x14001a37e  test    eax, eax
0x14001a380  jns     short loc_14001A38C
0x14001a382  mov     r9d, eax
0x14001a385  mov     edx, 0F1h
0x14001a38a  jmp     short loc_14001A341
0x14001a38c  mov     rcx, [r14+10h]
0x14001a390  test    rcx, rcx
0x14001a393  jz      short loc_14001A3A6
0x14001a395  mov     [r14+10h], r13
0x14001a399  mov     rax, [rcx]
0x14001a39c  mov     rax, [rax+10h]
0x14001a3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a3a5  nop
0x14001a3a6  mov     [rsp+60h+hTemplateFile], r13; hTemplateFile
0x14001a3ab  mov     [rsp+60h+dwFlagsAndAttributes], r13d; dwFlagsAndAttributes
0x14001a3b0  mov     [rsp+60h+dwCreationDisposition], 3; int
0x14001a3b8  xor     r9d, r9d; lpSecurityAttributes
0x14001a3bb  mov     edx, 80000000h; dwDesiredAccess
0x14001a3c0  lea     r8d, [r9+1]; dwShareMode
0x14001a3c4  mov     rcx, [r14]; lpFileName
0x14001a3c7  call    cs:__imp_CreateFileW
0x14001a3ce  nop     dword ptr [rax+rax+00h]
0x14001a3d3  mov     rdi, rax
0x14001a3d6  mov     [rbp+var_20], rax
0x14001a3da  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001a3de  jnz     short loc_14001A3FC
0x14001a3e0  mov     rcx, [rbp+38h]; this
0x14001a3e4  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001a3eb  mov     edx, 100h; void *
0x14001a3f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001a3f5  mov     ebx, eax
0x14001a3f7  jmp     loc_14001A352
0x14001a3fc  mov     qword ptr [rbp+FileSize], r13
0x14001a400  lea     rdx, [rbp+FileSize]; lpFileSize
0x14001a404  mov     rcx, rdi; hFile
0x14001a407  call    cs:__imp_GetFileSizeEx
0x14001a40e  nop     dword ptr [rax+rax+00h]
0x14001a413  test    eax, eax
0x14001a415  jnz     short loc_14001A44B
0x14001a417  mov     rcx, [rbp+38h]; this
0x14001a41b  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001a422  mov     edx, 106h; void *
0x14001a427  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001a42c  mov     ebx, eax
0x14001a42e  test    rdi, rdi
0x14001a431  jz      loc_14001A352
0x14001a437  mov     rcx, rdi; hObject
0x14001a43a  call    cs:__imp_CloseHandle
0x14001a441  nop     dword ptr [rax+rax+00h]
0x14001a446  jmp     loc_14001A352
0x14001a44b  mov     r8d, dword ptr [rbp+FileSize]
0x14001a44f  lea     eax, [r8+1]
0x14001a453  cmp     eax, r8d
0x14001a456  jnb     short loc_14001A477
0x14001a458  mov     rcx, [rbp+38h]; this
0x14001a45c  mov     ebx, 80070216h
0x14001a461  mov     r9d, ebx; char *
0x14001a464  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001a46b  mov     edx, 10Bh; void *
0x14001a470  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a475  jmp     short loc_14001A42E
0x14001a477  mov     esi, eax
0x14001a479  xorps   xmm0, xmm0
0x14001a47c  movdqu  xmmword ptr [rbp+lpBuffer], xmm0
0x14001a481  mov     [rbp+var_8], r13
0x14001a485  test    eax, eax
0x14001a487  jz      short loc_14001A4F5
0x14001a489  cmp     rsi, 1000h
0x14001a490  jb      short loc_14001A4BF
0x14001a492  lea     rcx, [rax+27h]; Size
0x14001a496  cmp     rcx, rsi
0x14001a499  jbe     loc_14001A61A
0x14001a49f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001a4a4  mov     rcx, rax
0x14001a4a7  test    rax, rax
0x14001a4aa  jnz     short loc_14001A4B1
0x14001a4ac  lea     ecx, [rax+5]
0x14001a4af  int     29h; Win8: RtlFailFast(ecx)
0x14001a4b1  add     rax, 27h ; '''
0x14001a4b5  and     rax, 0FFFFFFFFFFFFFFE0h
0x14001a4b9  mov     [rax-8], rcx
0x14001a4bd  jmp     short loc_14001A4C7
0x14001a4bf  mov     rcx, rsi; Size
0x14001a4c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001a4c7  mov     [rbp+lpBuffer], rax
0x14001a4cb  lea     rbx, [rsi+rax]
0x14001a4cf  mov     [rbp+var_8], rbx
0x14001a4d3  mov     r8, rsi; Size
0x14001a4d6  xor     edx, edx; Val
0x14001a4d8  mov     rcx, rax; void *
0x14001a4db  call    memset_0
0x14001a4e0  mov     [rbp+lpBuffer+8], rbx
0x14001a4e4  mov     [rbp+var_20], r13
0x14001a4e8  lea     rcx, [rbp+var_20]
0x14001a4ec  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x14001a4f1  mov     r8d, dword ptr [rbp+FileSize]; nNumberOfBytesToRead
0x14001a4f5  mov     [rbp+NumberOfBytesRead], r13d
0x14001a4f9  mov     qword ptr [rsp+60h+dwCreationDisposition], r13; int
0x14001a4fe  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x14001a502  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x14001a506  mov     rcx, rdi; hFile
0x14001a509  call    cs:__imp_ReadFile
0x14001a510  nop     dword ptr [rax+rax+00h]
0x14001a515  test    eax, eax
0x14001a517  jnz     short loc_14001A53E
0x14001a519  mov     rcx, [rbp+38h]; this
0x14001a51d  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001a524  mov     edx, 113h; void *
0x14001a529  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001a52e  mov     ebx, eax
0x14001a530  lea     rcx, [rbp+lpBuffer]
0x14001a534  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x14001a539  jmp     loc_14001A42E
0x14001a53e  mov     ecx, dword ptr [rbp+FileSize]
0x14001a541  mov     rax, [rbp+lpBuffer]
0x14001a545  mov     [rcx+rax], r13b
0x14001a549  test    rdi, rdi
0x14001a54c  jz      short loc_14001A579
0x14001a54e  call    cs:__imp_GetLastError
0x14001a555  nop     dword ptr [rax+rax+00h]
0x14001a55a  mov     ebx, eax
0x14001a55c  mov     rcx, rdi; hObject
0x14001a55f  call    cs:__imp_CloseHandle
0x14001a566  nop     dword ptr [rax+rax+00h]
0x14001a56b  mov     ecx, ebx; dwErrCode
0x14001a56d  call    cs:__imp_SetLastError
0x14001a574  nop     dword ptr [rax+rax+00h]
0x14001a579  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x14001a581  mov     rcx, [r14]; lpFileName
0x14001a584  call    cs:__imp_DeleteFileW
0x14001a58b  nop     dword ptr [rax+rax+00h]
0x14001a590  test    eax, eax
0x14001a592  jnz     short loc_14001A5AD
0x14001a594  mov     rcx, [rbp+38h]; this
0x14001a598  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001a59f  mov     edx, 11Ch; void *
0x14001a5a4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001a5a9  mov     ebx, eax
0x14001a5ab  jmp     short loc_14001A5E7
0x14001a5ad  mov     r9, r15
0x14001a5b0  mov     r8, r12
0x14001a5b3  mov     edx, 0FDE9h
0x14001a5b8  mov     rcx, [rbp+lpBuffer]
0x14001a5bc  call    cs:__imp_?MBToUnicode@@YAJPEBDIPEAPEAGPEAK@Z; MBToUnicode(char const *,uint,ushort * *,ulong *)
0x14001a5c3  nop     dword ptr [rax+rax+00h]
0x14001a5c8  mov     ebx, eax
0x14001a5ca  test    eax, eax
0x14001a5cc  jns     short loc_14001A5F5
0x14001a5ce  mov     rcx, [rbp+38h]; this
0x14001a5d2  mov     r9d, eax; char *
0x14001a5d5  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001a5dc  mov     edx, 124h; void *
0x14001a5e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a5e6  nop
0x14001a5e7  lea     rcx, [rbp+lpBuffer]
0x14001a5eb  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x14001a5f0  jmp     loc_14001A352
0x14001a5f5  lea     rcx, [rbp+lpBuffer]
0x14001a5f9  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x14001a5fe  nop
0x14001a5ff  xor     eax, eax
0x14001a601  mov     rbx, [rsp+60h+arg_0]
0x14001a609  add     rsp, 60h
0x14001a60d  pop     r15
0x14001a60f  pop     r14
0x14001a611  pop     r13
0x14001a613  pop     r12
0x14001a615  pop     rdi
0x14001a616  pop     rsi
0x14001a617  pop     rbp
0x14001a618  retn
0x14001a61a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
