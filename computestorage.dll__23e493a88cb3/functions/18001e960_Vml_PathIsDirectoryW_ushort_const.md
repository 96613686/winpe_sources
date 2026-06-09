# Vml::PathIsDirectoryW(ushort const *)

- ea: `0x18001e960`
- end: `0x18001ea80`
- name: `?PathIsDirectoryW@Vml@@YAHPEBG@Z`
- size: `288`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001cd00`

## callees

- `0x180002690`
- `0x180002b74`
- `0x180002bac`
- `0x1800032b8`
- `0x18001e960`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ea47`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ea47`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18001e98a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x18001e98a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x18001e9a1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x18001e9a1`
- `MPR!WNetGetResourceInformationW` at `0x18001ea05`
- `MPR!WNetGetResourceInformationW` at `0x18001ea05`

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
    operator delete(v4);
    goto LABEL_12;
  }
  if ( v4->dwDisplayType != 3 || (v5 = 1, v4->dwType > 1) )
    v5 = 0;
  operator delete(v4);
  return v5;
}

```

## disassembly

```asm
0x18001e960  mov     [rsp+arg_8], rbx
0x18001e965  mov     [rsp+arg_10], rbp
0x18001e96a  push    rdi
0x18001e96b  sub     rsp, 40h
0x18001e96f  mov     rax, cs:__security_cookie
0x18001e976  xor     rax, rsp
0x18001e979  mov     [rsp+48h+var_18], rax
0x18001e97e  mov     rdi, rcx
0x18001e981  test    rcx, rcx
0x18001e984  jz      loc_18001EA60
0x18001e98a  call    cs:__imp_PathIsUNCServerW
0x18001e991  nop     dword ptr [rax+rax+00h]
0x18001e996  test    eax, eax
0x18001e998  jnz     loc_18001EA60
0x18001e99e  mov     rcx, rdi; pszPath
0x18001e9a1  call    cs:__imp_PathIsUNCServerShareW
0x18001e9a8  nop     dword ptr [rax+rax+00h]
0x18001e9ad  test    eax, eax
0x18001e9af  jz      loc_18001EA44
0x18001e9b5  mov     ebp, 400h
0x18001e9ba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e9c1  mov     ecx, ebp; unsigned __int64
0x18001e9c3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e9c8  mov     rbx, rax
0x18001e9cb  test    rax, rax
0x18001e9ce  jz      short loc_18001EA44
0x18001e9d0  mov     r8d, ebp; Size
0x18001e9d3  xor     edx, edx; Val
0x18001e9d5  mov     rcx, rax; void *
0x18001e9d8  call    memset_0
0x18001e9dd  mov     qword ptr [rbx], 2
0x18001e9e4  lea     r9, [rsp+48h+lpSystem]; lplpSystem
0x18001e9e9  mov     [rbx+18h], rdi
0x18001e9ed  lea     r8, [rsp+48h+cbBuffer]; lpcbBuffer
0x18001e9f2  mov     rdx, rbx; lpBuffer
0x18001e9f5  mov     [rsp+48h+cbBuffer], ebp
0x18001e9f9  mov     rcx, rbx; lpNetResource
0x18001e9fc  mov     [rsp+48h+lpSystem], 0
0x18001ea05  call    cs:__imp_WNetGetResourceInformationW
0x18001ea0c  nop     dword ptr [rax+rax+00h]
0x18001ea11  test    eax, eax
0x18001ea13  jnz     short loc_18001EA39
0x18001ea15  cmp     [rbx+8], eax
0x18001ea18  jz      short loc_18001EA39
0x18001ea1a  cmp     dword ptr [rbx+8], 3
0x18001ea1e  jnz     short loc_18001EA28
0x18001ea20  lea     edi, [rax+1]
0x18001ea23  cmp     [rbx+4], edi
0x18001ea26  jbe     short loc_18001EA2A
0x18001ea28  xor     edi, edi
0x18001ea2a  mov     rdx, rbp; unsigned __int64
0x18001ea2d  mov     rcx, rbx; void *
0x18001ea30  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ea35  mov     eax, edi
0x18001ea37  jmp     short loc_18001EA62
0x18001ea39  mov     rdx, rbp; unsigned __int64
0x18001ea3c  mov     rcx, rbx; void *
0x18001ea3f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ea44  mov     rcx, rdi; lpFileName
0x18001ea47  call    cs:__imp_GetFileAttributesW
0x18001ea4e  nop     dword ptr [rax+rax+00h]
0x18001ea53  cmp     eax, 0FFFFFFFFh
0x18001ea56  jz      short loc_18001EA60
0x18001ea58  shr     eax, 4
0x18001ea5b  and     eax, 1
0x18001ea5e  jmp     short loc_18001EA62
0x18001ea60  xor     eax, eax
0x18001ea62  mov     rcx, [rsp+48h+var_18]
0x18001ea67  xor     rcx, rsp; StackCookie
0x18001ea6a  call    __security_check_cookie
0x18001ea6f  mov     rbx, [rsp+48h+arg_8]
0x18001ea74  mov     rbp, [rsp+48h+arg_10]
0x18001ea79  add     rsp, 40h
0x18001ea7d  pop     rdi
0x18001ea7e  retn
```
