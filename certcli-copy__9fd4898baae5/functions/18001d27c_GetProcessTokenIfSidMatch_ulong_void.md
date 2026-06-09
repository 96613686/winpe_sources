# GetProcessTokenIfSidMatch(ulong,void *)

- ea: `0x18001d27c`
- end: `0x18001d4a5`
- name: `?GetProcessTokenIfSidMatch@@YAPEAXKPEAX@Z`
- size: `553`
- prototype: `void *__fastcall(DWORD dwProcessId, PSID pSid1)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e660`

## callees

- `0x18001d27c`
- `0x1800200c0`
- `0x180021438`
- `0x1800396f2`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d3b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d3b5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d3e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d3e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d3d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d3d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d478`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d478`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d445`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d46a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d445`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d46a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001d3af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001d417`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001d3af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001d417`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d436`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001d436`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001d37c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001d37c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001d2d5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001d2d5`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x18001d30a`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x18001d30a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001d330`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18001d330`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d2ef`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d320`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d2ef`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18001d320`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x18001d461`
- `certca!__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z` at `0x18001d461`

## pseudocode

```c
void *__fastcall GetProcessTokenIfSidMatch(DWORD dwProcessId, PSID pSid1)
{
  HANDLE v4; // rax
  void *v5; // rdi
  int v6; // eax
  PSID *v7; // rbx
  int v8; // eax
  unsigned int v9; // ecx
  const WCHAR *FileNameW; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR ImageFileName; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[526]; // [rsp+42h] [rbp-BEh] BYREF

  TokenHandle = 0;
  ImageFileName = 0;
  memset_0(v15, 0, 0x206u);
  v4 = OpenProcess(0x1000u, 0, dwProcessId);
  v5 = v4;
  if ( !v4 )
  {
    v6 = myHLastError();
    CSPrintErrorLineFile(0x2489019Au, v6);
    return TokenHandle;
  }
  v7 = 0;
  if ( K32GetProcessImageFileNameW(v4, &ImageFileName, 0x104u) )
  {
    FileNameW = PathFindFileNameW(&ImageFileName);
    if ( FileNameW )
    {
      if ( (unsigned int)mylstrcmpNLSub(FileNameW, L"smss.exe", 8, 1) )
      {
        v8 = myHLastError();
        v9 = 614072730;
      }
      else if ( OpenProcessToken(v5, 0xAu, &TokenHandle) )
      {
        TokenInformationLength = 0;
        GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
        if ( GetLastError() == 122 )
        {
          v7 = (PSID *)LocalAlloc(0, TokenInformationLength);
          if ( v7 )
          {
            if ( GetTokenInformation(TokenHandle, TokenUser, v7, TokenInformationLength, &TokenInformationLength) )
            {
              if ( !EqualSid(pSid1, *v7) )
              {
                CloseHandle(TokenHandle);
                TokenHandle = 0;
                CSPrintErrorLineFile2(0x24BA019Au, 1, 1);
              }
              goto LABEL_20;
            }
            v8 = myHLastError();
            v9 = 615711130;
          }
          else
          {
            SetLastError(0xEu);
            v8 = myHLastError();
            v9 = 615383450;
          }
        }
        else
        {
          v8 = myHLastError();
          v9 = 614924698;
        }
      }
      else
      {
        v8 = myHLastError();
        v9 = 614400410;
      }
    }
    else
    {
      v8 = myHLastError();
      v9 = 613745050;
    }
  }
  else
  {
    v8 = myHLastError();
    v9 = 613286298;
  }
  CSPrintErrorLineFile(v9, v8);
LABEL_20:
  CloseHandle(v5);
  if ( v7 )
    LocalFree(v7);
  return TokenHandle;
}

```

## disassembly

```asm
0x18001d27c  mov     [rsp-8+arg_10], rbx
0x18001d281  push    rbp
0x18001d282  push    rsi
0x18001d283  push    rdi
0x18001d284  lea     rbp, [rsp-160h]
0x18001d28c  sub     rsp, 260h
0x18001d293  mov     rax, cs:__security_cookie
0x18001d29a  xor     rax, rsp
0x18001d29d  mov     [rbp+170h+var_20], rax
0x18001d2a4  mov     rsi, rdx
0x18001d2a7  mov     [rsp+270h+TokenHandle], 0
0x18001d2b0  mov     ebx, ecx
0x18001d2b2  xor     eax, eax
0x18001d2b4  xor     edx, edx; Val
0x18001d2b6  mov     [rsp+270h+ImageFileName], ax
0x18001d2bb  lea     rcx, [rsp+270h+var_22E]; void *
0x18001d2c0  mov     r8d, 206h; Size
0x18001d2c6  call    memset_0
0x18001d2cb  mov     r8d, ebx; dwProcessId
0x18001d2ce  xor     edx, edx; bInheritHandle
0x18001d2d0  mov     ecx, 1000h; dwDesiredAccess
0x18001d2d5  call    cs:__imp_OpenProcess
0x18001d2db  mov     rdi, rax
0x18001d2de  test    rax, rax
0x18001d2e1  jnz     short loc_18001D2FA
0x18001d2e3  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001d2e8  mov     edx, eax
0x18001d2ea  mov     ecx, 2489019Ah
0x18001d2ef  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001d2f5  jmp     loc_18001D47E
0x18001d2fa  mov     r8d, 104h; nSize
0x18001d300  lea     rdx, [rsp+270h+ImageFileName]; lpImageFileName
0x18001d305  mov     rcx, rdi; hProcess
0x18001d308  xor     ebx, ebx
0x18001d30a  call    cs:__imp_K32GetProcessImageFileNameW
0x18001d310  test    eax, eax
0x18001d312  jnz     short loc_18001D32B
0x18001d314  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001d319  mov     ecx, 248E019Ah
0x18001d31e  mov     edx, eax
0x18001d320  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001d326  jmp     loc_18001D467
0x18001d32b  lea     rcx, [rsp+270h+ImageFileName]; pszPath
0x18001d330  call    cs:__imp_PathFindFileNameW
0x18001d336  test    rax, rax
0x18001d339  jnz     short loc_18001D347
0x18001d33b  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001d340  mov     ecx, 2495019Ah
0x18001d345  jmp     short loc_18001D31E
0x18001d347  mov     r9b, 1; bool
0x18001d34a  lea     rdx, aSmssExe; "smss.exe"
0x18001d351  mov     r8d, 8; int
0x18001d357  mov     rcx, rax; lpString1
0x18001d35a  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x18001d35f  test    eax, eax
0x18001d361  jz      short loc_18001D36F
0x18001d363  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001d368  mov     ecx, 249A019Ah
0x18001d36d  jmp     short loc_18001D31E
0x18001d36f  lea     r8, [rsp+270h+TokenHandle]; TokenHandle
0x18001d374  mov     edx, 0Ah; DesiredAccess
0x18001d379  mov     rcx, rdi; ProcessHandle
0x18001d37c  call    cs:__imp_OpenProcessToken
0x18001d382  test    eax, eax
0x18001d384  jnz     short loc_18001D392
0x18001d386  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001d38b  mov     ecx, 249F019Ah
0x18001d390  jmp     short loc_18001D31E
0x18001d392  mov     rcx, [rsp+270h+TokenHandle]; TokenHandle
0x18001d397  lea     rax, [rsp+270h+TokenInformationLength]
0x18001d39c  xor     r9d, r9d; TokenInformationLength
0x18001d39f  mov     [rsp+270h+TokenInformationLength], ebx
0x18001d3a3  xor     r8d, r8d; TokenInformation
0x18001d3a6  mov     [rsp+270h+ReturnLength], rax; ReturnLength
0x18001d3ab  lea     edx, [r9+1]; TokenInformationClass
0x18001d3af  call    cs:__imp_GetTokenInformation
0x18001d3b5  call    cs:__imp_GetLastError
0x18001d3bb  cmp     eax, 7Ah ; 'z'
0x18001d3be  jz      short loc_18001D3CF
0x18001d3c0  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001d3c5  mov     ecx, 24A7019Ah
0x18001d3ca  jmp     loc_18001D31E
0x18001d3cf  mov     edx, [rsp+270h+TokenInformationLength]; uBytes
0x18001d3d3  xor     ecx, ecx; uFlags
0x18001d3d5  call    cs:__imp_LocalAlloc
0x18001d3db  mov     rbx, rax
0x18001d3de  test    rax, rax
0x18001d3e1  jnz     short loc_18001D3FB
0x18001d3e3  lea     ecx, [rax+0Eh]; dwErrCode
0x18001d3e6  call    cs:__imp_SetLastError
0x18001d3ec  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001d3f1  mov     ecx, 24AE019Ah
0x18001d3f6  jmp     loc_18001D31E
0x18001d3fb  mov     r9d, [rsp+270h+TokenInformationLength]; TokenInformationLength
0x18001d400  lea     rax, [rsp+270h+TokenInformationLength]
0x18001d405  mov     rcx, [rsp+270h+TokenHandle]; TokenHandle
0x18001d40a  mov     r8, rbx; TokenInformation
0x18001d40d  mov     edx, 1; TokenInformationClass
0x18001d412  mov     [rsp+270h+ReturnLength], rax; ReturnLength
0x18001d417  call    cs:__imp_GetTokenInformation
0x18001d41d  test    eax, eax
0x18001d41f  jnz     short loc_18001D430
0x18001d421  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001d426  mov     ecx, 24B3019Ah
0x18001d42b  jmp     loc_18001D31E
0x18001d430  mov     rdx, [rbx]; pSid2
0x18001d433  mov     rcx, rsi; pSid1
0x18001d436  call    cs:__imp_EqualSid
0x18001d43c  test    eax, eax
0x18001d43e  jnz     short loc_18001D467
0x18001d440  mov     rcx, [rsp+270h+TokenHandle]; hObject
0x18001d445  call    cs:__imp_CloseHandle
0x18001d44b  mov     edx, 1
0x18001d450  mov     [rsp+270h+TokenHandle], 0
0x18001d459  mov     r8d, edx
0x18001d45c  mov     ecx, 24BA019Ah
0x18001d461  call    cs:__imp_?CSPrintErrorLineFile2@@YAXKJJ@Z; CSPrintErrorLineFile2(ulong,long,long)
0x18001d467  mov     rcx, rdi; hObject
0x18001d46a  call    cs:__imp_CloseHandle
0x18001d470  test    rbx, rbx
0x18001d473  jz      short loc_18001D47E
0x18001d475  mov     rcx, rbx; hMem
0x18001d478  call    cs:__imp_LocalFree
0x18001d47e  mov     rax, [rsp+270h+TokenHandle]
0x18001d483  mov     rcx, [rbp+170h+var_20]
0x18001d48a  xor     rcx, rsp; StackCookie
0x18001d48d  call    __security_check_cookie
0x18001d492  mov     rbx, [rsp+270h+arg_10]
0x18001d49a  add     rsp, 260h
0x18001d4a1  pop     rdi
0x18001d4a2  pop     rsi
0x18001d4a3  pop     rbp
0x18001d4a4  retn
```
