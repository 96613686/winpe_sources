# CUserName::DuplicateTokenInPid(ulong,unsigned __int64 *)

- ea: `0x180008de0`
- end: `0x180008f2f`
- name: `?DuplicateTokenInPid@CUserName@@UEAAJKPEA_K@Z`
- size: `335`
- prototype: `int(CUserName *__hidden this, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800077a0`
- `0x180008de0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008e70`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180008e70`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ead`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008ead`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180008e98`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180008e98`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008e18`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180008e18`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180008e57`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180008e57`

## string_xrefs

- `0x180008ed1`: `No token`

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
0x180008de0  mov     [rsp+arg_10], rbx
0x180008de5  mov     [rsp+arg_18], rbp
0x180008dea  push    rdi
0x180008deb  sub     rsp, 40h
0x180008def  xor     ebp, ebp
0x180008df1  mov     rdi, r8
0x180008df4  test    byte ptr [rcx+640h], 1
0x180008dfb  mov     rbx, rcx
0x180008dfe  mov     [rsp+48h+hSourceHandle], rbp
0x180008e03  jz      loc_180008ED1
0x180008e09  mov     r8d, edx; dwProcessId
0x180008e0c  mov     [rsp+48h+arg_8], rsi
0x180008e11  xor     edx, edx; bInheritHandle
0x180008e13  mov     ecx, 40h ; '@'; dwDesiredAccess
0x180008e18  call    cs:__imp_OpenProcess
0x180008e1f  nop     dword ptr [rax+rax+00h]
0x180008e24  mov     rsi, rax
0x180008e27  test    rax, rax
0x180008e2a  jz      loc_180008F15
0x180008e30  mov     rcx, [rbx+638h]; hExistingToken
0x180008e37  lea     rax, [rsp+48h+hSourceHandle]
0x180008e3c  mov     [rsp+48h+phNewToken], rax; phNewToken
0x180008e41  mov     r9d, 2; ImpersonationLevel
0x180008e47  xor     r8d, r8d; lpTokenAttributes
0x180008e4a  mov     [rsp+48h+TokenType], 1; TokenType
0x180008e52  mov     edx, 2000000h; dwDesiredAccess
0x180008e57  call    cs:__imp_DuplicateTokenEx
0x180008e5e  nop     dword ptr [rax+rax+00h]
0x180008e63  test    eax, eax
0x180008e65  jz      loc_180008EF8
0x180008e6b  mov     rbx, [rsp+48h+hSourceHandle]
0x180008e70  call    cs:__imp_GetCurrentProcess
0x180008e77  nop     dword ptr [rax+rax+00h]
0x180008e7c  mov     [rsp+48h+dwOptions], 3; dwOptions
0x180008e84  mov     r9, rdi; lpTargetHandle
0x180008e87  mov     rcx, rax; hSourceProcessHandle
0x180008e8a  mov     dword ptr [rsp+48h+phNewToken], ebp; bInheritHandle
0x180008e8e  mov     r8, rsi; hTargetProcessHandle
0x180008e91  mov     [rsp+48h+TokenType], ebp; dwDesiredAccess
0x180008e95  mov     rdx, rbx; hSourceHandle
0x180008e98  call    cs:__imp_DuplicateHandle
0x180008e9f  nop     dword ptr [rax+rax+00h]
0x180008ea4  test    eax, eax
0x180008ea6  jz      short loc_180008EF8
0x180008ea8  mov     ebx, ebp
0x180008eaa  mov     rcx, rsi; hObject
0x180008ead  call    cs:__imp_CloseHandle
0x180008eb4  nop     dword ptr [rax+rax+00h]
0x180008eb9  mov     eax, ebx
0x180008ebb  mov     rsi, [rsp+48h+arg_8]
0x180008ec0  mov     rbx, [rsp+48h+arg_10]
0x180008ec5  mov     rbp, [rsp+48h+arg_18]
0x180008eca  add     rsp, 40h
0x180008ece  pop     rdi
0x180008ecf  retn
0x180008ed1  lea     rdx, aNoToken; "No token"
0x180008ed8  mov     ecx, 8; int
0x180008edd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180008ee2  mov     rbx, [rsp+48h+arg_10]
0x180008ee7  mov     eax, 800703F0h
0x180008eec  mov     rbp, [rsp+48h+arg_18]
0x180008ef1  add     rsp, 40h
0x180008ef5  pop     rdi
0x180008ef6  retn
0x180008ef8  call    cs:__imp_GetLastError
0x180008eff  nop     dword ptr [rax+rax+00h]
0x180008f04  mov     ebx, eax
0x180008f06  test    eax, eax
0x180008f08  jle     short loc_180008EAA
0x180008f0a  movzx   ebx, ax
0x180008f0d  or      ebx, 80070000h
0x180008f13  jmp     short loc_180008EAA
0x180008f15  call    cs:__imp_GetLastError
0x180008f1c  nop     dword ptr [rax+rax+00h]
0x180008f21  test    eax, eax
0x180008f23  jle     short loc_180008EBB
0x180008f25  movzx   eax, ax
0x180008f28  or      eax, 80070000h
0x180008f2d  jmp     short loc_180008EBB
```
