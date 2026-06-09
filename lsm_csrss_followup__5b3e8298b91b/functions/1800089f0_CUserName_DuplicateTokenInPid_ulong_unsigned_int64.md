# CUserName::DuplicateTokenInPid(ulong,unsigned __int64 *)

- ea: `0x1800089f0`
- end: `0x180008b0f`
- name: `?DuplicateTokenInPid@CUserName@@UEAAJKPEA_K@Z`
- size: `287`
- prototype: `int(CUserName *__hidden this, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800074c0`
- `0x1800089f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ae4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ae4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008afb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008a70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008a70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008aa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008aa1`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180008a92`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180008a92`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008a28`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008a28`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180008a61`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180008a61`

## string_xrefs

- `0x180008abe`: `No token`

## pseudocode

```c
int __fastcall CUserName::DuplicateTokenInPid(CUserName *this, DWORD a2, HANDLE *a3)
{
  bool v4; // zf
  HANDLE v6; // rsi
  HANDLE v7; // rbx
  HANDLE CurrentProcess; // rax
  unsigned int v9; // ebx
  int result; // eax
  signed int LastError; // eax
  HANDLE hSourceHandle; // [rsp+50h] [rbp+8h] BYREF

  v4 = (*((_BYTE *)this + 1600) & 1) == 0;
  hSourceHandle = 0;
  if ( v4 )
  {
    _DbgPrintMessage(8, "No token");
    return -2147023888;
  }
  else
  {
    v6 = OpenProcess(0x40u, 0, a2);
    if ( v6 )
    {
      if ( DuplicateTokenEx(*((HANDLE *)this + 199), 0x2000000u, 0, SecurityImpersonation, TokenPrimary, &hSourceHandle)
        && (v7 = hSourceHandle,
            CurrentProcess = GetCurrentProcess(),
            DuplicateHandle(CurrentProcess, v7, v6, a3, 0, 0, 3u)) )
      {
        v9 = 0;
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
      CloseHandle(v6);
      return v9;
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800089f0  mov     [rsp+arg_10], rbx
0x1800089f5  mov     [rsp+arg_18], rbp
0x1800089fa  push    rdi
0x1800089fb  sub     rsp, 40h
0x1800089ff  xor     ebp, ebp
0x180008a01  mov     rdi, r8
0x180008a04  test    byte ptr [rcx+640h], 1
0x180008a0b  mov     rbx, rcx
0x180008a0e  mov     [rsp+48h+hSourceHandle], rbp
0x180008a13  jz      loc_180008ABE
0x180008a19  mov     r8d, edx; dwProcessId
0x180008a1c  mov     [rsp+48h+arg_8], rsi
0x180008a21  xor     edx, edx; bInheritHandle
0x180008a23  mov     ecx, 40h ; '@'; dwDesiredAccess
0x180008a28  call    cs:__imp_OpenProcess
0x180008a2e  mov     rsi, rax
0x180008a31  test    rax, rax
0x180008a34  jz      loc_180008AFB
0x180008a3a  mov     rcx, [rbx+638h]; hExistingToken
0x180008a41  lea     rax, [rsp+48h+hSourceHandle]
0x180008a46  mov     [rsp+48h+phNewToken], rax; phNewToken
0x180008a4b  mov     r9d, 2; ImpersonationLevel
0x180008a51  xor     r8d, r8d; lpTokenAttributes
0x180008a54  mov     [rsp+48h+TokenType], 1; TokenType
0x180008a5c  mov     edx, 2000000h; dwDesiredAccess
0x180008a61  call    cs:__imp_DuplicateTokenEx
0x180008a67  test    eax, eax
0x180008a69  jz      short loc_180008AE4
0x180008a6b  mov     rbx, [rsp+48h+hSourceHandle]
0x180008a70  call    cs:__imp_GetCurrentProcess
0x180008a76  mov     [rsp+48h+dwOptions], 3; dwOptions
0x180008a7e  mov     r9, rdi; lpTargetHandle
0x180008a81  mov     rcx, rax; hSourceProcessHandle
0x180008a84  mov     dword ptr [rsp+48h+phNewToken], ebp; bInheritHandle
0x180008a88  mov     r8, rsi; hTargetProcessHandle
0x180008a8b  mov     [rsp+48h+TokenType], ebp; dwDesiredAccess
0x180008a8f  mov     rdx, rbx; hSourceHandle
0x180008a92  call    cs:__imp_DuplicateHandle
0x180008a98  test    eax, eax
0x180008a9a  jz      short loc_180008AE4
0x180008a9c  mov     ebx, ebp
0x180008a9e  mov     rcx, rsi; hObject
0x180008aa1  call    cs:__imp_CloseHandle
0x180008aa7  mov     eax, ebx
0x180008aa9  mov     rsi, [rsp+48h+arg_8]
0x180008aae  mov     rbx, [rsp+48h+arg_10]
0x180008ab3  mov     rbp, [rsp+48h+arg_18]
0x180008ab8  add     rsp, 40h
0x180008abc  pop     rdi
0x180008abd  retn
0x180008abe  lea     rdx, aNoToken; "No token"
0x180008ac5  mov     ecx, 8; int
0x180008aca  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008acf  mov     rbx, [rsp+48h+arg_10]
0x180008ad4  mov     eax, 800703F0h
0x180008ad9  mov     rbp, [rsp+48h+arg_18]
0x180008ade  add     rsp, 40h
0x180008ae2  pop     rdi
0x180008ae3  retn
0x180008ae4  call    cs:__imp_GetLastError
0x180008aea  mov     ebx, eax
0x180008aec  test    eax, eax
0x180008aee  jle     short loc_180008A9E
0x180008af0  movzx   ebx, ax
0x180008af3  or      ebx, 80070000h
0x180008af9  jmp     short loc_180008A9E
0x180008afb  call    cs:__imp_GetLastError
0x180008b01  test    eax, eax
0x180008b03  jle     short loc_180008AA9
0x180008b05  movzx   eax, ax
0x180008b08  or      eax, 80070000h
0x180008b0d  jmp     short loc_180008AA9
```
