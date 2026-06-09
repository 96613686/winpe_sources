# Vml::PathIsDirectoryW(ushort const *)

- ea: `0x180024abc`
- end: `0x180024bc3`
- name: `?PathIsDirectoryW@Vml@@YAHPEBG@Z`
- size: `263`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180022140`
- `0x180029380`
- `0x1800295f0`
- `0x18003ae9c`
- `0x18003ba60`

## callees

- `0x1800067c0`
- `0x180006828`
- `0x180006bf8`
- `0x180007438`
- `0x180024abc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180024b91`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180024b91`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180024ae6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180024ae6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x180024af7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x180024af7`
- `MPR!WNetGetResourceInformationW` at `0x180024b55`
- `MPR!WNetGetResourceInformationW` at `0x180024b55`

## pseudocode

```c
__int64 __fastcall Vml::PathIsDirectoryW(WCHAR *lpFileName, const unsigned __int16 *a2)
{
  struct _NETRESOURCEW *v3; // rax
  struct _NETRESOURCEW *v4; // rbx
  unsigned int v5; // edi
  DWORD FileAttributesW; // eax
  LPWSTR lpSystem; // [rsp+20h] [rbp-28h] BYREF
  DWORD cbBuffer; // [rsp+28h] [rbp-20h] BYREF

  if ( !lpFileName || PathIsUNCServerW(lpFileName) )
    return 0;
  if ( !PathIsUNCServerShareW(lpFileName)
    || (v3 = (struct _NETRESOURCEW *)operator new(0x400u, (const struct std::nothrow_t *)&std::nothrow), (v4 = v3) == 0) )
  {
LABEL_12:
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW != -1 )
      return (FileAttributesW >> 4) & 1;
    return 0;
  }
  memset_0(v3, 0, 0x400u);
  *(_QWORD *)&v4->dwScope = 2;
  v4->lpRemoteName = lpFileName;
  cbBuffer = 1024;
  lpSystem = 0;
  if ( WNetGetResourceInformationW(v4, v4, &cbBuffer, &lpSystem) || !v4->dwDisplayType )
  {
    operator delete(v4, 0x400u);
    goto LABEL_12;
  }
  if ( v4->dwDisplayType != 3 || (v5 = 1, v4->dwType > 1) )
    v5 = 0;
  operator delete(v4, 0x400u);
  return v5;
}

```

## disassembly

```asm
0x180024abc  mov     [rsp+arg_8], rbx
0x180024ac1  mov     [rsp+arg_10], rbp
0x180024ac6  push    rdi
0x180024ac7  sub     rsp, 40h
0x180024acb  mov     rax, cs:__security_cookie
0x180024ad2  xor     rax, rsp
0x180024ad5  mov     [rsp+48h+var_18], rax
0x180024ada  mov     rdi, rcx
0x180024add  test    rcx, rcx
0x180024ae0  jz      loc_180024BA4
0x180024ae6  call    cs:__imp_PathIsUNCServerW
0x180024aec  test    eax, eax
0x180024aee  jnz     loc_180024BA4
0x180024af4  mov     rcx, rdi; pszPath
0x180024af7  call    cs:__imp_PathIsUNCServerShareW
0x180024afd  test    eax, eax
0x180024aff  jz      loc_180024B8E
0x180024b05  mov     ebp, 400h
0x180024b0a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180024b11  mov     ecx, ebp; unsigned __int64
0x180024b13  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180024b18  mov     rbx, rax
0x180024b1b  test    rax, rax
0x180024b1e  jz      short loc_180024B8E
0x180024b20  mov     r8d, ebp; Size
0x180024b23  xor     edx, edx; Val
0x180024b25  mov     rcx, rax; void *
0x180024b28  call    memset_0
0x180024b2d  mov     qword ptr [rbx], 2
0x180024b34  lea     r9, [rsp+48h+lpSystem]; lplpSystem
0x180024b39  mov     [rbx+18h], rdi
0x180024b3d  lea     r8, [rsp+48h+cbBuffer]; lpcbBuffer
0x180024b42  mov     rdx, rbx; lpBuffer
0x180024b45  mov     [rsp+48h+cbBuffer], ebp
0x180024b49  mov     rcx, rbx; lpNetResource
0x180024b4c  mov     [rsp+48h+lpSystem], 0
0x180024b55  call    cs:__imp_WNetGetResourceInformationW
0x180024b5b  test    eax, eax
0x180024b5d  jnz     short loc_180024B83
0x180024b5f  cmp     [rbx+8], eax
0x180024b62  jz      short loc_180024B83
0x180024b64  cmp     dword ptr [rbx+8], 3
0x180024b68  jnz     short loc_180024B72
0x180024b6a  lea     edi, [rax+1]
0x180024b6d  cmp     [rbx+4], edi
0x180024b70  jbe     short loc_180024B74
0x180024b72  xor     edi, edi
0x180024b74  mov     rdx, rbp; unsigned __int64
0x180024b77  mov     rcx, rbx; void *
0x180024b7a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024b7f  mov     eax, edi
0x180024b81  jmp     short loc_180024BA6
0x180024b83  mov     rdx, rbp; unsigned __int64
0x180024b86  mov     rcx, rbx; void *
0x180024b89  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180024b8e  mov     rcx, rdi; lpFileName
0x180024b91  call    cs:__imp_GetFileAttributesW
0x180024b97  cmp     eax, 0FFFFFFFFh
0x180024b9a  jz      short loc_180024BA4
0x180024b9c  shr     eax, 4
0x180024b9f  and     eax, 1
0x180024ba2  jmp     short loc_180024BA6
0x180024ba4  xor     eax, eax
0x180024ba6  mov     rcx, [rsp+48h+var_18]
0x180024bab  xor     rcx, rsp; StackCookie
0x180024bae  call    __security_check_cookie
0x180024bb3  mov     rbx, [rsp+48h+arg_8]
0x180024bb8  mov     rbp, [rsp+48h+arg_10]
0x180024bbd  add     rsp, 40h
0x180024bc1  pop     rdi
0x180024bc2  retn
```
