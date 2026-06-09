# GetTemporaryDirectoryPath

- ea: `0x180009cd4`
- end: `0x180009db0`
- name: `GetTemporaryDirectoryPath`
- size: `220`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a148`

## callees

- `0x180009cd4`
- `0x180018b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d39`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180009d2f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180009d2f`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180009ce9`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180009ce9`

## pseudocode

```c
__int64 __fastcall GetTemporaryDirectoryPath(WCHAR *lpPathName)
{
  DWORD TempPathW; // eax
  const char *v3; // r9
  const char *v4; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  TempPathW = GetTempPathW(0x104u, lpPathName);
  if ( !TempPathW )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3DA,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      v3);
  if ( TempPathW > 0x104 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3DB,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      v3);
  if ( !CreateDirectoryW(lpPathName, 0) && GetLastError() != 183 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3E2,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      v4);
  result = -1;
  do
    ++result;
  while ( lpPathName[result] );
  if ( !result )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3E6,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      v4);
  if ( lpPathName[result - 1] != 92 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3E7,
      (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webview\\corewebview\\corewebviewcontrol.cpp",
      v4);
  return result;
}

```

## disassembly

```asm
0x180009cd4  mov     [rsp+arg_0], rbx
0x180009cd9  push    rdi
0x180009cda  sub     rsp, 20h
0x180009cde  mov     rbx, rcx
0x180009ce1  mov     rdx, rcx; lpBuffer
0x180009ce4  mov     ecx, 104h; nBufferLength
0x180009ce9  call    cs:__imp_GetTempPathW
0x180009cef  xor     edi, edi
0x180009cf1  test    eax, eax
0x180009cf3  jnz     short loc_180009D0C
0x180009cf5  mov     rcx, [rsp+28h]; this
0x180009cfa  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180009d01  mov     edx, 3DAh; void *
0x180009d06  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180009d0c  cmp     eax, 104h
0x180009d11  jbe     short loc_180009D2A
0x180009d13  mov     rcx, [rsp+28h]; this
0x180009d18  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180009d1f  mov     edx, 3DBh; void *
0x180009d24  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180009d2a  xor     edx, edx; lpSecurityAttributes
0x180009d2c  mov     rcx, rbx; lpPathName
0x180009d2f  call    cs:__imp_CreateDirectoryW
0x180009d35  test    eax, eax
0x180009d37  jnz     short loc_180009D5D
0x180009d39  call    cs:__imp_GetLastError
0x180009d3f  cmp     eax, 0B7h
0x180009d44  jz      short loc_180009D5D
0x180009d46  mov     rcx, [rsp+28h]; this
0x180009d4b  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180009d52  mov     edx, 3E2h; void *
0x180009d57  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180009d5d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009d61  inc     rax
0x180009d64  cmp     [rbx+rax*2], di
0x180009d68  jnz     short loc_180009D61
0x180009d6a  test    rax, rax
0x180009d6d  jnz     short loc_180009D86
0x180009d6f  mov     rcx, [rsp+28h]; this
0x180009d74  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180009d7b  mov     edx, 3E6h; void *
0x180009d80  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180009d86  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x180009d8c  jz      short loc_180009DA5
0x180009d8e  mov     rcx, [rsp+28h]; this
0x180009d93  lea     r8, aOnecoreuapInet_19; "onecoreuap\\inetcore\\edgemanager\\webv"...
0x180009d9a  mov     edx, 3E7h; void *
0x180009d9f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180009da5  mov     rbx, [rsp+28h+arg_0]
0x180009daa  add     rsp, 20h
0x180009dae  pop     rdi
0x180009daf  retn
```
