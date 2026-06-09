# CBackgroundCopyFile::Complete(void)

- ea: `0x1800828e8`
- end: `0x180082c0b`
- name: `?Complete@CBackgroundCopyFile@@QEAAJXZ`
- size: `803`
- prototype: `__int64 __fastcall(CBackgroundCopyFile *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180095970`

## callees

- `0x18000933c`
- `0x180009ab4`
- `0x18000cdd0`
- `0x18000ef98`
- `0x1800199b4`
- `0x180019c5c`
- `0x1800813e0`
- `0x1800828e8`
- `0x180083f48`
- `0x180084fec`
- `0x18008507c`
- `0x180093f74`
- `0x1800943c4`
- `0x1800a979c`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082b11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082b63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082b11`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082b63`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180082afb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180082b4d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180082afb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180082b4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082a96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180082a96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082994`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800829c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082b29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082b7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082994`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800829c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082b29`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180082b7b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180082a88`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180082a88`

## string_xrefs

- `0x180082ad9`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyFile.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CBackgroundCopyFile::Complete(CJobSharedData **this)
{
  char *v2; // rbx
  int v3; // eax
  char v4; // si
  bool v5; // zf
  _QWORD *v6; // rsi
  _QWORD *v7; // rdx
  const WCHAR *v8; // rdx
  const WCHAR *v9; // rcx
  unsigned int v10; // esi
  signed int LastError; // eax
  HANDLE v12; // r14
  wil::details::in1diag3 *v13; // rcx
  const char *v14; // r9
  __int64 result; // rax
  HANDLE v16; // rsi
  int v17; // [rsp+20h] [rbp-88h]
  HANDLE Token[2]; // [rsp+28h] [rbp-80h] BYREF
  __int128 v19; // [rsp+38h] [rbp-70h]
  __int128 v20; // [rsp+48h] [rbp-60h]
  LPCWSTR lpNewFileName[4]; // [rsp+58h] [rbp-50h] BYREF
  LPCWSTR lpExistingFileName[4]; // [rsp+78h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v20 = 0;
  *(_QWORD *)&v20 = this;
  BYTE8(v20) = 1;
  *(_OWORD *)Token = 0;
  v2 = (char *)(this + 33);
  Token[0] = this + 33;
  LOBYTE(Token[1]) = 0;
  v3 = mtx_do_lock(this + 33);
  try
  {
    if ( v3 )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
    {
      *((_DWORD *)v2 + 19) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v4 = 1;
    LOBYTE(Token[1]) = 1;
    CBackgroundCopyFile::_EndProgressMonitoring((CBackgroundCopyFile *)this);
    if ( CJobSharedData::IsXVCJob(this[4]) )
    {
      if ( !v2 )
        std::_Throw_system_error(1);
      v5 = (*((_DWORD *)v2 + 19))-- == 1;
      if ( v5 )
      {
        *((_DWORD *)v2 + 18) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)v2 + 2);
      }
      v4 = 0;
      LOBYTE(Token[1]) = 0;
      CBackgroundCopyFile::_SendCompleteEventAndToast((CBackgroundCopyFile *)this);
    }
    if ( v4 )
    {
      v5 = (*((_DWORD *)v2 + 19))-- == 1;
      if ( v5 )
      {
        *((_DWORD *)v2 + 18) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)v2 + 2);
      }
    }
    v19 = (unsigned __int64)v2;
    if ( (unsigned int)mtx_do_lock(v2) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
    {
      *((_DWORD *)v2 + 19) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    BYTE8(v19) = 1;
    CBackgroundCopyFile::_ShutdownDownloadSink((CBackgroundCopyFile *)this);
    if ( this[12] )
    {
      Token[0] = 0;
      CJobSharedData::ImpersonateOwner(this[4], (int)Token);
      v6 = this + 6;
      if ( (unsigned __int64)this[9] > 0xF )
        v6 = (_QWORD *)*v6;
      v7 = this + 10;
      if ( (unsigned __int64)this[13] > 0xF )
        v7 = (_QWORD *)*v7;
      UTF8toWstr(lpExistingFileName, v7, 0);
      UTF8toWstr(lpNewFileName, v6, 0);
      v8 = (const WCHAR *)lpNewFileName;
      if ( lpNewFileName[3] > (LPCWSTR)7 )
        v8 = lpNewFileName[0];
      v9 = (const WCHAR *)lpExistingFileName;
      if ( lpExistingFileName[3] > (LPCWSTR)7 )
        v9 = lpExistingFileName[0];
      if ( MoveFileExW(v9, v8, 1u) )
      {
        v10 = 0;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError )
        {
          v10 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v10 = LastError;
        }
        else
        {
          v10 = -2147467259;
        }
      }
      std::wstring::~wstring(lpNewFileName);
      std::wstring::~wstring(lpExistingFileName);
      if ( (v10 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3D9,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
          (const char *)v10,
          v17);
        v12 = Token[0];
        if ( Token[0] == (HANDLE)-1LL )
        {
LABEL_35:
          v5 = (*((_DWORD *)v2 + 19))-- == 1;
          if ( v5 )
          {
            *((_DWORD *)v2 + 18) = -1;
            ReleaseSRWLockExclusive((PSRWLOCK)v2 + 2);
          }
          CBackgroundCopyFile::_DetachDownloadRequest((CBackgroundCopyFile *)this);
          return v10;
        }
        if ( SetThreadToken(0, Token[0]) )
        {
          if ( v12 )
            CloseHandle(v12);
          goto LABEL_35;
        }
LABEL_50:
        wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
      }
      v16 = Token[0];
      if ( Token[0] != (HANDLE)-1LL )
      {
        if ( !SetThreadToken(0, Token[0]) )
          goto LABEL_50;
        if ( v16 )
          CloseHandle(v16);
      }
    }
    v5 = (*((_DWORD *)v2 + 19))-- == 1;
    if ( v5 )
    {
      *((_DWORD *)v2 + 18) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)v2 + 2);
    }
    CBackgroundCopyFile::_DetachDownloadRequest((CBackgroundCopyFile *)this);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3DE,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyFile.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x1800828e8  mov     r11, rsp
0x1800828eb  mov     [r11+10h], rbx
0x1800828ef  mov     [r11+18h], rsi
0x1800828f3  mov     [r11+20h], rdi
0x1800828f7  push    r14
0x1800828f9  sub     rsp, 0A0h
0x180082900  mov     rax, cs:__security_cookie
0x180082907  xor     rax, rsp
0x18008290a  mov     [rsp+0A8h+var_10], rax
0x180082912  mov     rdi, rcx
0x180082915  xorps   xmm0, xmm0
0x180082918  movups  [rsp+0A8h+var_60], xmm0
0x18008291d  mov     [r11-60h], rcx
0x180082921  mov     r14d, 1
0x180082927  mov     [r11-58h], r14b
0x18008292b  movups  xmmword ptr [rsp+0A8h+Token], xmm0
0x180082930  lea     rbx, [rcx+108h]
0x180082937  mov     [r11-80h], rbx
0x18008293b  mov     byte ptr [rsp+0A8h+Token+8], 0
0x180082940  mov     rcx, rbx
0x180082943  call    mtx_do_lock
0x180082948  test    eax, eax
0x18008294a  jnz     loc_180082BC4
0x180082950  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180082957  jz      loc_180082BCD
0x18008295d  mov     sil, r14b
0x180082960  mov     byte ptr [rsp+0A8h+Token+8], r14b
0x180082965  mov     rcx, rdi; this
0x180082968  call    ?_EndProgressMonitoring@CBackgroundCopyFile@@AEAAXXZ; CBackgroundCopyFile::_EndProgressMonitoring(void)
0x18008296d  mov     rcx, [rdi+20h]; this
0x180082971  call    ?IsXVCJob@CJobSharedData@@QEBA_NXZ; CJobSharedData::IsXVCJob(void)
0x180082976  test    al, al
0x180082978  jz      short loc_1800829AB
0x18008297a  test    rbx, rbx
0x18008297d  jz      loc_180082BE9
0x180082983  sub     dword ptr [rbx+4Ch], 1
0x180082987  jnz     short loc_18008299A
0x180082989  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180082990  lea     rcx, [rbx+10h]; SRWLock
0x180082994  call    cs:__imp_ReleaseSRWLockExclusive
0x18008299a  xor     sil, sil
0x18008299d  mov     byte ptr [rsp+0A8h+Token+8], sil
0x1800829a2  mov     rcx, rdi; this
0x1800829a5  call    ?_SendCompleteEventAndToast@CBackgroundCopyFile@@AEAAXXZ; CBackgroundCopyFile::_SendCompleteEventAndToast(void)
0x1800829aa  nop
0x1800829ab  test    sil, sil
0x1800829ae  jz      short loc_1800829C7
0x1800829b0  sub     dword ptr [rbx+4Ch], 1
0x1800829b4  jnz     short loc_1800829C7
0x1800829b6  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x1800829bd  lea     rcx, [rbx+10h]; SRWLock
0x1800829c1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800829c7  xorps   xmm0, xmm0
0x1800829ca  movups  [rsp+0A8h+var_70], xmm0
0x1800829cf  mov     qword ptr [rsp+0A8h+var_70], rbx
0x1800829d4  mov     byte ptr [rsp+0A8h+var_70+8], 0
0x1800829d9  mov     rcx, rbx
0x1800829dc  call    mtx_do_lock
0x1800829e1  test    eax, eax
0x1800829e3  jnz     loc_180082BDE
0x1800829e9  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1800829f0  jz      loc_180082BF2
0x1800829f6  mov     byte ptr [rsp+0A8h+var_70+8], r14b
0x1800829fb  mov     rcx, rdi; this
0x1800829fe  call    ?_ShutdownDownloadSink@CBackgroundCopyFile@@AEAAXXZ; CBackgroundCopyFile::_ShutdownDownloadSink(void)
0x180082a03  cmp     qword ptr [rdi+60h], 0
0x180082a08  jz      loc_180082B6A
0x180082a0e  mov     [rsp+0A8h+Token], 0
0x180082a17  lea     rdx, [rsp+0A8h+Token]; int
0x180082a1c  mov     rcx, [rdi+20h]; this
0x180082a20  call    ?ImpersonateOwner@CJobSharedData@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@XZ; CJobSharedData::ImpersonateOwner(void)
0x180082a25  nop
0x180082a26  lea     rsi, [rdi+30h]
0x180082a2a  cmp     qword ptr [rsi+18h], 0Fh
0x180082a2f  jbe     short loc_180082A34
0x180082a31  mov     rsi, [rsi]
0x180082a34  lea     rdx, [rdi+50h]
0x180082a38  cmp     qword ptr [rdx+18h], 0Fh
0x180082a3d  jbe     short loc_180082A42
0x180082a3f  mov     rdx, [rdx]
0x180082a42  xor     r8d, r8d
0x180082a45  lea     rcx, [rsp+0A8h+lpExistingFileName]
0x180082a4a  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x180082a4f  nop
0x180082a50  xor     r8d, r8d
0x180082a53  mov     rdx, rsi
0x180082a56  lea     rcx, [rsp+0A8h+lpNewFileName]
0x180082a5b  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x180082a60  lea     rdx, [rsp+0A8h+lpNewFileName]
0x180082a65  cmp     [rsp+0A8h+var_38], 7
0x180082a6b  cmova   rdx, [rsp+0A8h+lpNewFileName]; lpNewFileName
0x180082a71  lea     rcx, [rsp+0A8h+lpExistingFileName]
0x180082a76  cmp     [rsp+0A8h+var_18], 7
0x180082a7f  cmova   rcx, [rsp+0A8h+lpExistingFileName]; lpExistingFileName
0x180082a85  mov     r8d, r14d; dwFlags
0x180082a88  call    cs:__imp_MoveFileExW
0x180082a8e  test    eax, eax
0x180082a90  jz      short loc_180082A96
0x180082a92  xor     esi, esi
0x180082a94  jmp     short loc_180082AB5
0x180082a96  call    cs:__imp_GetLastError
0x180082a9c  test    eax, eax
0x180082a9e  jz      short loc_180082AB0
0x180082aa0  movzx   esi, ax
0x180082aa3  or      esi, 80070000h
0x180082aa9  test    eax, eax
0x180082aab  cmovle  esi, eax
0x180082aae  jmp     short loc_180082AB5
0x180082ab0  mov     esi, 80004005h
0x180082ab5  lea     rcx, [rsp+0A8h+lpNewFileName]
0x180082aba  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180082abf  nop
0x180082ac0  lea     rcx, [rsp+0A8h+lpExistingFileName]
0x180082ac5  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180082aca  test    esi, esi
0x180082acc  jns     short loc_180082B3D
0x180082ace  mov     rcx, [rsp+0A8h]; this
0x180082ad6  mov     r9d, esi; char *
0x180082ad9  lea     r8, aCW1SSrcDeliver_117; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180082ae0  mov     edx, 3D9h; void *
0x180082ae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082aea  nop
0x180082aeb  mov     r14, [rsp+0A8h+Token]
0x180082af0  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180082af4  jz      short loc_180082B18
0x180082af6  mov     rdx, r14; Token
0x180082af9  xor     ecx, ecx; Thread
0x180082afb  call    cs:__imp_SetThreadToken
0x180082b01  test    eax, eax
0x180082b03  jz      loc_180082C04
0x180082b09  test    r14, r14
0x180082b0c  jz      short loc_180082B18
0x180082b0e  mov     rcx, r14; hObject
0x180082b11  call    cs:__imp_CloseHandle
0x180082b17  nop
0x180082b18  sub     dword ptr [rbx+4Ch], 1
0x180082b1c  jnz     short loc_180082B30
0x180082b1e  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180082b25  lea     rcx, [rbx+10h]; SRWLock
0x180082b29  call    cs:__imp_ReleaseSRWLockExclusive
0x180082b2f  nop
0x180082b30  mov     rcx, rdi; this
0x180082b33  call    ?_DetachDownloadRequest@CBackgroundCopyFile@@AEAAXXZ; CBackgroundCopyFile::_DetachDownloadRequest(void)
0x180082b38  nop
0x180082b39  mov     eax, esi
0x180082b3b  jmp     short loc_180082B9A
0x180082b3d  mov     rsi, [rsp+0A8h+Token]
0x180082b42  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180082b46  jz      short loc_180082B6A
0x180082b48  mov     rdx, rsi; Token
0x180082b4b  xor     ecx, ecx; Thread
0x180082b4d  call    cs:__imp_SetThreadToken
0x180082b53  test    eax, eax
0x180082b55  jz      loc_180082C04
0x180082b5b  test    rsi, rsi
0x180082b5e  jz      short loc_180082B6A
0x180082b60  mov     rcx, rsi; hObject
0x180082b63  call    cs:__imp_CloseHandle
0x180082b69  nop
0x180082b6a  sub     dword ptr [rbx+4Ch], 1
0x180082b6e  jnz     short loc_180082B82
0x180082b70  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x180082b77  lea     rcx, [rbx+10h]; SRWLock
0x180082b7b  call    cs:__imp_ReleaseSRWLockExclusive
0x180082b81  nop
0x180082b82  mov     rcx, rdi; this
0x180082b85  call    ?_DetachDownloadRequest@CBackgroundCopyFile@@AEAAXXZ; CBackgroundCopyFile::_DetachDownloadRequest(void)
0x180082b8a  nop
0x180082b8b  xor     eax, eax
0x180082b8d  jmp     short loc_180082B9A
0x180082b8f  mov     eax, 8007000Eh
0x180082b94  jmp     short loc_180082B9A
0x180082b96  mov     eax, [rsp+0A8h+var_88]
0x180082b9a  mov     rcx, [rsp+0A8h+var_10]
0x180082ba2  xor     rcx, rsp; StackCookie
0x180082ba5  call    __security_check_cookie
0x180082baa  lea     r11, [rsp+0A8h+var_8]
0x180082bb2  mov     rbx, [r11+18h]
0x180082bb6  mov     rsi, [r11+20h]
0x180082bba  mov     rdi, [r11+28h]
0x180082bbe  mov     rsp, r11
0x180082bc1  pop     r14
0x180082bc3  retn
0x180082bc4  lea     ecx, [r14+4]; int
0x180082bc8  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180082bcd  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180082bd4  mov     ecx, 6; int
0x180082bd9  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180082bde  mov     ecx, 5; int
0x180082be3  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180082be9  mov     ecx, r14d
0x180082bec  call    ?_Throw_system_error@std@@YAXW4errc@1@@Z; std::_Throw_system_error(std::errc)
0x180082bf2  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180082bf9  mov     ecx, 6; int
0x180082bfe  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180082c04  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
