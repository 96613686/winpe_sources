# CLBIMProxy::IsChsIME(ulong)

- ea: `0x1800bde24`
- end: `0x1800bdf0c`
- name: `?IsChsIME@CLBIMProxy@@AEBA_NK@Z`
- size: `232`
- prototype: `bool(CLBIMProxy *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18002ee38`

## callees

- `0x18009eaea`
- `0x1800bde24`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800bde52`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800bde52`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1800bde65`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x1800bde65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bded6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdedf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bded6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bdedf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800bde79`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800bde79`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1800bdea9`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x1800bdea9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800bdebf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x1800bdebf`

## pseudocode

```c
bool __fastcall CLBIMProxy::IsChsIME(CLBIMProxy *this, DWORD a2)
{
  bool v2; // bl
  HANDLE v3; // rax
  HANDLE v4; // rdi
  void *v5; // rsi
  DWORD ProcessIdOfThread; // eax
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = 0;
  v3 = OpenThread(0x40u, 0, a2);
  v4 = 0;
  v5 = v3;
  if ( v3 )
  {
    ProcessIdOfThread = GetProcessIdOfThread(v3);
    if ( ProcessIdOfThread )
    {
      v4 = OpenProcess(0x410u, 0, ProcessIdOfThread);
      if ( v4 )
      {
        memset_0(Filename, 0, 0x208u);
        if ( K32GetModuleFileNameExW(v4, 0, Filename, 0x103u) )
          v2 = StrStrIW(Filename, L"chsime.exe") != 0;
      }
    }
  }
  CloseHandle(v5);
  CloseHandle(v4);
  return v2;
}

```

## disassembly

```asm
0x1800bde24  mov     [rsp+arg_0], rbx
0x1800bde29  mov     [rsp+arg_10], rsi
0x1800bde2e  push    rdi
0x1800bde2f  sub     rsp, 240h
0x1800bde36  mov     rax, cs:__security_cookie
0x1800bde3d  xor     rax, rsp
0x1800bde40  mov     [rsp+248h+var_18], rax
0x1800bde48  mov     r8d, edx; dwThreadId
0x1800bde4b  xor     bl, bl
0x1800bde4d  xor     edx, edx; bInheritHandle
0x1800bde4f  lea     ecx, [rdx+40h]; dwDesiredAccess
0x1800bde52  call    cs:__imp_OpenThread
0x1800bde58  xor     edi, edi
0x1800bde5a  mov     rsi, rax
0x1800bde5d  test    rax, rax
0x1800bde60  jz      short loc_1800BDED3
0x1800bde62  mov     rcx, rax; Thread
0x1800bde65  call    cs:__imp_GetProcessIdOfThread
0x1800bde6b  test    eax, eax
0x1800bde6d  jz      short loc_1800BDED3
0x1800bde6f  mov     r8d, eax; dwProcessId
0x1800bde72  xor     edx, edx; bInheritHandle
0x1800bde74  mov     ecx, 410h; dwDesiredAccess
0x1800bde79  call    cs:__imp_OpenProcess
0x1800bde7f  mov     rdi, rax
0x1800bde82  test    rax, rax
0x1800bde85  jz      short loc_1800BDED3
0x1800bde87  xor     edx, edx; Val
0x1800bde89  lea     rcx, [rsp+248h+Filename]; void *
0x1800bde8e  mov     r8d, 208h; Size
0x1800bde94  call    memset_0
0x1800bde99  mov     r9d, 103h; nSize
0x1800bde9f  lea     r8, [rsp+248h+Filename]; lpFilename
0x1800bdea4  xor     edx, edx; hModule
0x1800bdea6  mov     rcx, rdi; hProcess
0x1800bdea9  call    cs:__imp_K32GetModuleFileNameExW
0x1800bdeaf  test    eax, eax
0x1800bdeb1  jz      short loc_1800BDED3
0x1800bdeb3  lea     rdx, pszSrch; "chsime.exe"
0x1800bdeba  lea     rcx, [rsp+248h+Filename]; pszFirst
0x1800bdebf  call    cs:__imp_StrStrIW
0x1800bdec5  movzx   ebx, bl
0x1800bdec8  mov     ecx, 1
0x1800bdecd  test    rax, rax
0x1800bded0  cmovnz  ebx, ecx
0x1800bded3  mov     rcx, rsi; hObject
0x1800bded6  call    cs:__imp_CloseHandle
0x1800bdedc  mov     rcx, rdi; hObject
0x1800bdedf  call    cs:__imp_CloseHandle
0x1800bdee5  mov     al, bl
0x1800bdee7  mov     rcx, [rsp+248h+var_18]
0x1800bdeef  xor     rcx, rsp; StackCookie
0x1800bdef2  call    __security_check_cookie
0x1800bdef7  lea     r11, [rsp+248h+var_8]
0x1800bdeff  mov     rbx, [r11+10h]
0x1800bdf03  mov     rsi, [r11+20h]
0x1800bdf07  mov     rsp, r11
0x1800bdf0a  pop     rdi
0x1800bdf0b  retn
```
