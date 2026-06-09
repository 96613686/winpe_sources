# Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreatePersistFile(ushort const *)

- ea: `0x140019b64`
- end: `0x140019d37`
- name: `?CreatePersistFile@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBG@Z`
- size: `467`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001a7a0`

## callees

- `0x140003450`
- `0x1400036e4`
- `0x140003eb4`
- `0x140005864`
- `0x14000b0f4`
- `0x14000be18`
- `0x140013068`
- `0x140019b64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019ceb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019c39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140019ceb`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x140019baf`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x140019baf`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140019cdb`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x140019cdb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140019c29`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140019c29`

## pseudocode

```c
int __fastcall Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreatePersistFile(
        LPWSTR *this,
        const unsigned __int16 *a2)
{
  int BasicProfileFolderPath; // edi
  __int64 v5; // rdx
  DWORD LastError; // eax
  WCHAR *v8; // rax
  LPWSTR v9; // rcx
  signed int v10; // ebx
  __int64 v11; // rdx
  signed int v12; // eax
  unsigned int PathName[132]; // [rsp+20h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  memset_0(PathName, 0, 0x208u);
  BasicProfileFolderPath = GetBasicProfileFolderPath(6, 0, PathName, 259);
  if ( BasicProfileFolderPath < 0 )
  {
    v5 = 513;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)BasicProfileFolderPath,
      PathName[0]);
    return BasicProfileFolderPath;
  }
  BasicProfileFolderPath = StringCchCatW((unsigned __int16 *)PathName, 0x103u, L"\\");
  if ( BasicProfileFolderPath < 0 )
  {
    v5 = 518;
    goto LABEL_3;
  }
  BasicProfileFolderPath = StringCchCatW((unsigned __int16 *)PathName, 0x103u, a2);
  if ( BasicProfileFolderPath < 0 )
  {
    v5 = 523;
    goto LABEL_3;
  }
  if ( !CreateDirectoryW((LPCWSTR)PathName, 0) )
  {
    LastError = GetLastError();
    if ( LastError != 183 )
    {
      if ( LastError )
        return wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x212,
                 (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
                 (const char *)LastError,
                 PathName[0]);
      return 0;
    }
  }
  v8 = (WCHAR *)operator new[](0x208u, (const struct std::nothrow_t *)std::nothrow);
  v9 = *this;
  *this = v8;
  if ( v9 )
    operator delete(v9);
  if ( !*this )
  {
    v10 = -2147024882;
    v11 = 535;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v10,
      PathName[0]);
    return v10;
  }
  **this = 0;
  if ( !GetTempFileNameW((LPCWSTR)PathName, L"DPU", 1u, *this) )
  {
    v12 = GetLastError();
    v10 = v12;
    if ( v12 > 0 )
      v10 = (unsigned __int16)v12 | 0x80070000;
    if ( v10 < 0 )
    {
      v11 = 548;
      goto LABEL_16;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140019b64  mov     [rsp+arg_10], rbx
0x140019b69  push    rbp
0x140019b6a  push    rsi
0x140019b6b  push    rdi
0x140019b6c  sub     rsp, 240h
0x140019b73  mov     rax, cs:__security_cookie
0x140019b7a  xor     rax, rsp
0x140019b7d  mov     [rsp+258h+var_28], rax
0x140019b85  mov     rsi, rdx
0x140019b88  mov     rbx, rcx
0x140019b8b  xor     edx, edx; Val
0x140019b8d  lea     rcx, [rsp+258h+PathName]; void *
0x140019b92  mov     r8d, 208h; Size
0x140019b98  call    memset_0
0x140019b9d  xor     edx, edx
0x140019b9f  lea     r8, [rsp+258h+PathName]
0x140019ba4  mov     ebp, 103h
0x140019ba9  mov     r9d, ebp
0x140019bac  lea     ecx, [rdx+6]
0x140019baf  call    cs:__imp_GetBasicProfileFolderPath
0x140019bb6  nop     dword ptr [rax+rax+00h]
0x140019bbb  mov     edi, eax
0x140019bbd  test    eax, eax
0x140019bbf  jns     short loc_140019BE4
0x140019bc1  mov     edx, 201h; void *
0x140019bc6  mov     rcx, [rsp+258h]; this
0x140019bce  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140019bd5  mov     r9d, edi; char *
0x140019bd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019bdd  mov     eax, edi
0x140019bdf  jmp     loc_140019D13
0x140019be4  lea     r8, pszSrc; "\\"
0x140019beb  mov     rdx, rbp; unsigned __int64
0x140019bee  lea     rcx, [rsp+258h+PathName]; unsigned __int16 *
0x140019bf3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140019bf8  mov     edi, eax
0x140019bfa  test    eax, eax
0x140019bfc  jns     short loc_140019C05
0x140019bfe  mov     edx, 206h
0x140019c03  jmp     short loc_140019BC6
0x140019c05  mov     r8, rsi; unsigned __int16 *
0x140019c08  lea     rcx, [rsp+258h+PathName]; unsigned __int16 *
0x140019c0d  mov     rdx, rbp; unsigned __int64
0x140019c10  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140019c15  mov     edi, eax
0x140019c17  test    eax, eax
0x140019c19  jns     short loc_140019C22
0x140019c1b  mov     edx, 20Bh
0x140019c20  jmp     short loc_140019BC6
0x140019c22  xor     edx, edx; lpSecurityAttributes
0x140019c24  lea     rcx, [rsp+258h+PathName]; lpPathName
0x140019c29  call    cs:__imp_CreateDirectoryW
0x140019c30  nop     dword ptr [rax+rax+00h]
0x140019c35  test    eax, eax
0x140019c37  jnz     short loc_140019C75
0x140019c39  call    cs:__imp_GetLastError
0x140019c40  nop     dword ptr [rax+rax+00h]
0x140019c45  cmp     eax, 0B7h
0x140019c4a  jz      short loc_140019C75
0x140019c4c  test    eax, eax
0x140019c4e  jz      loc_140019D11
0x140019c54  mov     rcx, [rsp+258h]; this
0x140019c5c  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140019c63  mov     r9d, eax; char *
0x140019c66  mov     edx, 212h; void *
0x140019c6b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140019c70  jmp     loc_140019D13
0x140019c75  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140019c7c  mov     ecx, 208h; unsigned __int64
0x140019c81  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140019c86  mov     rcx, [rbx]; Block
0x140019c89  mov     [rbx], rax
0x140019c8c  test    rcx, rcx
0x140019c8f  jz      short loc_140019C96
0x140019c91  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140019c96  mov     rcx, [rbx]
0x140019c99  test    rcx, rcx
0x140019c9c  jnz     short loc_140019CC3
0x140019c9e  mov     ebx, 8007000Eh
0x140019ca3  mov     edx, 217h; void *
0x140019ca8  mov     rcx, [rsp+258h]; this
0x140019cb0  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x140019cb7  mov     r9d, ebx; char *
0x140019cba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019cbf  mov     eax, ebx
0x140019cc1  jmp     short loc_140019D13
0x140019cc3  xor     eax, eax
0x140019cc5  lea     rdx, PrefixString; "DPU"
0x140019ccc  mov     [rcx], ax
0x140019ccf  lea     rcx, [rsp+258h+PathName]; lpPathName
0x140019cd4  mov     r9, [rbx]; lpTempFileName
0x140019cd7  lea     r8d, [rax+1]; uUnique
0x140019cdb  call    cs:__imp_GetTempFileNameW
0x140019ce2  nop     dword ptr [rax+rax+00h]
0x140019ce7  test    eax, eax
0x140019ce9  jnz     short loc_140019D11
0x140019ceb  call    cs:__imp_GetLastError
0x140019cf2  nop     dword ptr [rax+rax+00h]
0x140019cf7  mov     ebx, eax
0x140019cf9  test    eax, eax
0x140019cfb  jle     short loc_140019D06
0x140019cfd  movzx   ebx, ax
0x140019d00  or      ebx, 80070000h
0x140019d06  test    ebx, ebx
0x140019d08  jns     short loc_140019D11
0x140019d0a  mov     edx, 224h
0x140019d0f  jmp     short loc_140019CA8
0x140019d11  xor     eax, eax
0x140019d13  mov     rcx, [rsp+258h+var_28]
0x140019d1b  xor     rcx, rsp; StackCookie
0x140019d1e  call    __security_check_cookie
0x140019d23  mov     rbx, [rsp+258h+arg_10]
0x140019d2b  add     rsp, 240h
0x140019d32  pop     rdi
0x140019d33  pop     rsi
0x140019d34  pop     rbp
0x140019d35  retn
```
