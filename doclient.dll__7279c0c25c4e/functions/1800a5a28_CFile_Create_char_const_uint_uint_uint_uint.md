# CFile::Create(char const *,uint,uint,uint,uint)

- ea: `0x1800a5a28`
- end: `0x1800a5aff`
- name: `?Create@CFile@@QEAAJPEBDIIII@Z`
- size: `215`
- prototype: `__int64 __fastcall(void **this, const char *, DWORD, DWORD, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes)`
- caller_count: `9`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180021a04`
- `0x180086e68`
- `0x1800a08b0`
- `0x1800a5b08`
- `0x1800ac938`
- `0x1800acb58`
- `0x1800bb2ac`
- `0x1800effa8`
- `0x1800f029c`

## callees

- `0x180008a54`
- `0x18000ef98`
- `0x1800a5a28`
- `0x1800a979c`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5ab3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a5ab3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5aa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a5aa8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a5abb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800a5abb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5a91`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a5a91`

## pseudocode

```c
__int64 __fastcall CFile::Create(
        void **this,
        const char *a2,
        DWORD a3,
        DWORD a4,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes)
{
  const WCHAR *v9; // rcx
  unsigned int LastErrorFailHr; // r14d
  HANDLE FileW; // rax
  wil::details *v12; // rcx
  void *v13; // rdi
  HANDLE v14; // rsi
  DWORD LastError; // ebx
  LPCWSTR lpFileName[4]; // [rsp+40h] [rbp-68h] BYREF

  UTF8toWstr(lpFileName, a2, 0);
  v9 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v9 = lpFileName[0];
  LastErrorFailHr = 0;
  FileW = CreateFileW(v9, a3, a4, 0, dwCreationDisposition, dwFlagsAndAttributes, 0);
  v13 = *this;
  v14 = FileW;
  if ( *this != (void *)-1LL && v13 )
  {
    LastError = GetLastError();
    CloseHandle(v13);
    SetLastError(LastError);
  }
  *this = v14;
  if ( (((unsigned __int64)v14 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v12);
  std::wstring::~wstring(lpFileName);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800a5a28  push    rbx
0x1800a5a2a  push    rbp
0x1800a5a2b  push    rsi
0x1800a5a2c  push    rdi
0x1800a5a2d  push    r14
0x1800a5a2f  push    r15
0x1800a5a31  sub     rsp, 78h
0x1800a5a35  mov     rax, cs:__security_cookie
0x1800a5a3c  xor     rax, rsp
0x1800a5a3f  mov     [rsp+0A8h+var_48], rax
0x1800a5a44  mov     edi, [rsp+0A8h+arg_20]
0x1800a5a4b  mov     esi, r8d
0x1800a5a4e  mov     ebx, [rsp+0A8h+arg_28]
0x1800a5a55  mov     r15, rcx
0x1800a5a58  xor     r8d, r8d
0x1800a5a5b  lea     rcx, [rsp+0A8h+lpFileName]
0x1800a5a60  mov     ebp, r9d
0x1800a5a63  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x1800a5a68  cmp     [rsp+0A8h+var_50], 7
0x1800a5a6e  lea     rcx, [rsp+0A8h+lpFileName]
0x1800a5a73  mov     r8d, ebp; dwShareMode
0x1800a5a76  mov     edx, esi; dwDesiredAccess
0x1800a5a78  cmova   rcx, [rsp+0A8h+lpFileName]; lpFileName
0x1800a5a7e  xor     r14d, r14d
0x1800a5a81  mov     [rsp+0A8h+hTemplateFile], r14; hTemplateFile
0x1800a5a86  xor     r9d, r9d; lpSecurityAttributes
0x1800a5a89  mov     [rsp+0A8h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x1800a5a8d  mov     [rsp+0A8h+dwCreationDisposition], edi; dwCreationDisposition
0x1800a5a91  call    cs:__imp_CreateFileW
0x1800a5a97  mov     rdi, [r15]
0x1800a5a9a  mov     rsi, rax
0x1800a5a9d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800a5aa1  jz      short loc_1800A5AC1
0x1800a5aa3  test    rdi, rdi
0x1800a5aa6  jz      short loc_1800A5AC1
0x1800a5aa8  call    cs:__imp_GetLastError
0x1800a5aae  mov     rcx, rdi; hObject
0x1800a5ab1  mov     ebx, eax
0x1800a5ab3  call    cs:__imp_CloseHandle
0x1800a5ab9  mov     ecx, ebx; dwErrCode
0x1800a5abb  call    cs:__imp_SetLastError
0x1800a5ac1  lea     rax, [rsi+1]
0x1800a5ac5  mov     [r15], rsi
0x1800a5ac8  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800a5ace  jnz     short loc_1800A5AD8
0x1800a5ad0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800a5ad5  mov     r14d, eax
0x1800a5ad8  lea     rcx, [rsp+0A8h+lpFileName]
0x1800a5add  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a5ae2  mov     eax, r14d
0x1800a5ae5  mov     rcx, [rsp+0A8h+var_48]
0x1800a5aea  xor     rcx, rsp; StackCookie
0x1800a5aed  call    __security_check_cookie
0x1800a5af2  add     rsp, 78h
0x1800a5af6  pop     r15
0x1800a5af8  pop     r14
0x1800a5afa  pop     rdi
0x1800a5afb  pop     rsi
0x1800a5afc  pop     rbp
0x1800a5afd  pop     rbx
0x1800a5afe  retn
```
