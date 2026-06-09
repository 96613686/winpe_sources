# DavQueryPathFromRequest

- ea: `0x180009de0`
- end: `0x180009f17`
- name: `DavQueryPathFromRequest`
- size: `311`
- prototype: `void *__fastcall(HINTERNET hInternet)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007450`

## callees

- `0x180009de0`
- `0x180011afc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ed9`
- `KERNEL32!LocalAlloc` at `0x180009e2a`
- `KERNEL32!LocalAlloc` at `0x180009e2a`
- `KERNEL32!LocalFree` at `0x180009e89`
- `KERNEL32!LocalFree` at `0x180009e89`
- `WINHTTP!WinHttpQueryOption` at `0x180009e04`
- `WINHTTP!WinHttpQueryOption` at `0x180009e48`
- `WINHTTP!WinHttpQueryOption` at `0x180009e04`
- `WINHTTP!WinHttpQueryOption` at `0x180009e48`

## pseudocode

```c
void *__fastcall DavQueryPathFromRequest(HINTERNET hInternet)
{
  void *v2; // rbx
  DWORD LastError; // eax
  __int64 v4; // r8
  HLOCAL v5; // rax
  DWORD v6; // eax
  __int64 v7; // r8
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  DWORD dwBufferLength; // [rsp+38h] [rbp+10h] BYREF

  dwBufferLength = 0;
  v2 = 0;
  if ( WinHttpQueryOption(hInternet, 0x22u, 0, &dwBufferLength) )
  {
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v2;
    v9 = 31;
LABEL_18:
    WPP_SF_l(v8[2], v9, v4, LastError);
    return v2;
  }
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v2;
    v9 = 30;
    goto LABEL_18;
  }
  v5 = LocalAlloc(0x40u, dwBufferLength);
  v2 = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v2;
    v9 = 29;
    goto LABEL_18;
  }
  if ( !WinHttpQueryOption(hInternet, 0x22u, v5, &dwBufferLength) )
  {
    v6 = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, v7, v6);
    LocalFree(v2);
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180009de0  mov     [rsp+arg_0], rbx
0x180009de5  push    rdi
0x180009de6  sub     rsp, 20h
0x180009dea  lea     r9, [rsp+28h+dwBufferLength]; lpdwBufferLength
0x180009def  mov     [rsp+28h+dwBufferLength], 0
0x180009df7  xor     r8d, r8d; lpBuffer
0x180009dfa  mov     edx, 22h ; '"'; dwOption
0x180009dff  mov     rdi, rcx
0x180009e02  xor     ebx, ebx
0x180009e04  call    cs:__imp_WinHttpQueryOption
0x180009e0a  test    eax, eax
0x180009e0c  jnz     loc_180009ED9
0x180009e12  call    cs:__imp_GetLastError
0x180009e18  cmp     eax, 7Ah ; 'z'
0x180009e1b  jnz     loc_180009EB9
0x180009e21  mov     edx, [rsp+28h+dwBufferLength]; uBytes
0x180009e25  mov     ecx, 40h ; '@'; uFlags
0x180009e2a  call    cs:__imp_LocalAlloc
0x180009e30  mov     rbx, rax
0x180009e33  test    rax, rax
0x180009e36  jz      short loc_180009E93
0x180009e38  lea     r9, [rsp+28h+dwBufferLength]; lpdwBufferLength
0x180009e3d  mov     r8, rax; lpBuffer
0x180009e40  mov     edx, 22h ; '"'; dwOption
0x180009e45  mov     rcx, rdi; hInternet
0x180009e48  call    cs:__imp_WinHttpQueryOption
0x180009e4e  test    eax, eax
0x180009e50  jnz     loc_180009F09
0x180009e56  call    cs:__imp_GetLastError
0x180009e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e63  lea     rdx, WPP_GLOBAL_Control
0x180009e6a  cmp     rcx, rdx
0x180009e6d  jz      short loc_180009E86
0x180009e6f  test    byte ptr [rcx+1Ch], 1
0x180009e73  jz      short loc_180009E86
0x180009e75  mov     rcx, [rcx+10h]
0x180009e79  mov     edx, 1Ch
0x180009e7e  mov     r9d, eax
0x180009e81  call    WPP_SF_l
0x180009e86  mov     rcx, rbx; hMem
0x180009e89  call    cs:__imp_LocalFree
0x180009e8f  xor     ebx, ebx
0x180009e91  jmp     short loc_180009F09
0x180009e93  call    cs:__imp_GetLastError
0x180009e99  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ea0  lea     rdx, WPP_GLOBAL_Control
0x180009ea7  cmp     rcx, rdx
0x180009eaa  jz      short loc_180009F09
0x180009eac  test    byte ptr [rcx+1Ch], 1
0x180009eb0  jz      short loc_180009F09
0x180009eb2  mov     edx, 1Dh
0x180009eb7  jmp     short loc_180009EFD
0x180009eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ec0  lea     rdx, WPP_GLOBAL_Control
0x180009ec7  cmp     rcx, rdx
0x180009eca  jz      short loc_180009F09
0x180009ecc  test    byte ptr [rcx+1Ch], 1
0x180009ed0  jz      short loc_180009F09
0x180009ed2  mov     edx, 1Eh
0x180009ed7  jmp     short loc_180009EFD
0x180009ed9  call    cs:__imp_GetLastError
0x180009edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ee6  lea     rdx, WPP_GLOBAL_Control
0x180009eed  cmp     rcx, rdx
0x180009ef0  jz      short loc_180009F09
0x180009ef2  test    byte ptr [rcx+1Ch], 1
0x180009ef6  jz      short loc_180009F09
0x180009ef8  mov     edx, 1Fh
0x180009efd  mov     rcx, [rcx+10h]
0x180009f01  mov     r9d, eax
0x180009f04  call    WPP_SF_l
0x180009f09  mov     rax, rbx
0x180009f0c  mov     rbx, [rsp+28h+arg_0]
0x180009f11  add     rsp, 20h
0x180009f15  pop     rdi
0x180009f16  retn
```
