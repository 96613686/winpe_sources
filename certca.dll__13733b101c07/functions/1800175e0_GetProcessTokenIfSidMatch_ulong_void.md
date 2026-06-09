# GetProcessTokenIfSidMatch(ulong,void *)

- ea: `0x1800175e0`
- end: `0x180017807`
- name: `?GetProcessTokenIfSidMatch@@YAPEAXKPEAX@Z`
- size: `551`
- prototype: `void *__fastcall(DWORD dwProcessId, PSID pSid1)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018620`

## callees

- `0x180008400`
- `0x180008610`
- `0x18000d520`
- `0x180012450`
- `0x1800175e0`
- `0x180038262`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017737`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017737`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800177da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800177da`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800176de`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800176de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017717`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017748`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017748`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017711`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017779`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017711`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017779`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017798`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180017798`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800177a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800177cc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800177a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800177cc`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017639`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017639`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x18001766d`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x18001766d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180017692`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180017692`

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
                CSPrintErrorLineFileData2(0, 0x24BA019Au, 1, 1);
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
0x1800175e0  mov     [rsp-8+arg_10], rbx
0x1800175e5  push    rbp
0x1800175e6  push    rsi
0x1800175e7  push    rdi
0x1800175e8  lea     rbp, [rsp-160h]
0x1800175f0  sub     rsp, 260h
0x1800175f7  mov     rax, cs:__security_cookie
0x1800175fe  xor     rax, rsp
0x180017601  mov     [rbp+170h+var_20], rax
0x180017608  mov     rsi, rdx
0x18001760b  mov     [rsp+270h+TokenHandle], 0
0x180017614  mov     ebx, ecx
0x180017616  xor     eax, eax
0x180017618  xor     edx, edx; Val
0x18001761a  mov     [rsp+270h+ImageFileName], ax
0x18001761f  lea     rcx, [rsp+270h+var_22E]; void *
0x180017624  mov     r8d, 206h; Size
0x18001762a  call    memset_0
0x18001762f  mov     r8d, ebx; dwProcessId
0x180017632  xor     edx, edx; bInheritHandle
0x180017634  mov     ecx, 1000h; dwDesiredAccess
0x180017639  call    cs:__imp_OpenProcess
0x18001763f  mov     rdi, rax
0x180017642  test    rax, rax
0x180017645  jnz     short loc_18001765D
0x180017647  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001764c  mov     edx, eax; int
0x18001764e  mov     ecx, 2489019Ah; unsigned int
0x180017653  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180017658  jmp     loc_1800177E0
0x18001765d  mov     r8d, 104h; nSize
0x180017663  lea     rdx, [rsp+270h+ImageFileName]; lpImageFileName
0x180017668  mov     rcx, rdi; hProcess
0x18001766b  xor     ebx, ebx
0x18001766d  call    cs:__imp_K32GetProcessImageFileNameW
0x180017673  test    eax, eax
0x180017675  jnz     short loc_18001768D
0x180017677  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001767c  mov     ecx, 248E019Ah; unsigned int
0x180017681  mov     edx, eax; int
0x180017683  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180017688  jmp     loc_1800177C9
0x18001768d  lea     rcx, [rsp+270h+ImageFileName]; pszPath
0x180017692  call    cs:__imp_PathFindFileNameW
0x180017698  test    rax, rax
0x18001769b  jnz     short loc_1800176A9
0x18001769d  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800176a2  mov     ecx, 2495019Ah
0x1800176a7  jmp     short loc_180017681
0x1800176a9  mov     r9b, 1; bool
0x1800176ac  lea     rdx, aSmssExe; "smss.exe"
0x1800176b3  mov     r8d, 8; int
0x1800176b9  mov     rcx, rax; lpString1
0x1800176bc  call    ?mylstrcmpNLSub@@YAHPEBG0H_N@Z; mylstrcmpNLSub(ushort const *,ushort const *,int,bool)
0x1800176c1  test    eax, eax
0x1800176c3  jz      short loc_1800176D1
0x1800176c5  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800176ca  mov     ecx, 249A019Ah
0x1800176cf  jmp     short loc_180017681
0x1800176d1  lea     r8, [rsp+270h+TokenHandle]; TokenHandle
0x1800176d6  mov     edx, 0Ah; DesiredAccess
0x1800176db  mov     rcx, rdi; ProcessHandle
0x1800176de  call    cs:__imp_OpenProcessToken
0x1800176e4  test    eax, eax
0x1800176e6  jnz     short loc_1800176F4
0x1800176e8  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800176ed  mov     ecx, 249F019Ah
0x1800176f2  jmp     short loc_180017681
0x1800176f4  mov     rcx, [rsp+270h+TokenHandle]; TokenHandle
0x1800176f9  lea     rax, [rsp+270h+TokenInformationLength]
0x1800176fe  xor     r9d, r9d; TokenInformationLength
0x180017701  mov     [rsp+270h+TokenInformationLength], ebx
0x180017705  xor     r8d, r8d; TokenInformation
0x180017708  mov     [rsp+270h+ReturnLength], rax; ReturnLength
0x18001770d  lea     edx, [r9+1]; TokenInformationClass
0x180017711  call    cs:__imp_GetTokenInformation
0x180017717  call    cs:__imp_GetLastError
0x18001771d  cmp     eax, 7Ah ; 'z'
0x180017720  jz      short loc_180017731
0x180017722  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180017727  mov     ecx, 24A7019Ah
0x18001772c  jmp     loc_180017681
0x180017731  mov     edx, [rsp+270h+TokenInformationLength]; uBytes
0x180017735  xor     ecx, ecx; uFlags
0x180017737  call    cs:__imp_LocalAlloc
0x18001773d  mov     rbx, rax
0x180017740  test    rax, rax
0x180017743  jnz     short loc_18001775D
0x180017745  lea     ecx, [rax+0Eh]; dwErrCode
0x180017748  call    cs:__imp_SetLastError
0x18001774e  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180017753  mov     ecx, 24AE019Ah
0x180017758  jmp     loc_180017681
0x18001775d  mov     r9d, [rsp+270h+TokenInformationLength]; TokenInformationLength
0x180017762  lea     rax, [rsp+270h+TokenInformationLength]
0x180017767  mov     rcx, [rsp+270h+TokenHandle]; TokenHandle
0x18001776c  mov     r8, rbx; TokenInformation
0x18001776f  mov     edx, 1; TokenInformationClass
0x180017774  mov     [rsp+270h+ReturnLength], rax; ReturnLength
0x180017779  call    cs:__imp_GetTokenInformation
0x18001777f  test    eax, eax
0x180017781  jnz     short loc_180017792
0x180017783  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180017788  mov     ecx, 24B3019Ah
0x18001778d  jmp     loc_180017681
0x180017792  mov     rdx, [rbx]; pSid2
0x180017795  mov     rcx, rsi; pSid1
0x180017798  call    cs:__imp_EqualSid
0x18001779e  test    eax, eax
0x1800177a0  jnz     short loc_1800177C9
0x1800177a2  mov     rcx, [rsp+270h+TokenHandle]; hObject
0x1800177a7  call    cs:__imp_CloseHandle
0x1800177ad  xor     ecx, ecx; unsigned __int16 *
0x1800177af  mov     [rsp+270h+TokenHandle], 0
0x1800177b8  mov     edx, 24BA019Ah; unsigned int
0x1800177bd  lea     r9d, [rcx+1]; int
0x1800177c1  mov     r8d, r9d; int
0x1800177c4  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x1800177c9  mov     rcx, rdi; hObject
0x1800177cc  call    cs:__imp_CloseHandle
0x1800177d2  test    rbx, rbx
0x1800177d5  jz      short loc_1800177E0
0x1800177d7  mov     rcx, rbx; hMem
0x1800177da  call    cs:__imp_LocalFree
0x1800177e0  mov     rax, [rsp+270h+TokenHandle]
0x1800177e5  mov     rcx, [rbp+170h+var_20]
0x1800177ec  xor     rcx, rsp; StackCookie
0x1800177ef  call    __security_check_cookie
0x1800177f4  mov     rbx, [rsp+270h+arg_10]
0x1800177fc  add     rsp, 260h
0x180017803  pop     rdi
0x180017804  pop     rsi
0x180017805  pop     rbp
0x180017806  retn
```
