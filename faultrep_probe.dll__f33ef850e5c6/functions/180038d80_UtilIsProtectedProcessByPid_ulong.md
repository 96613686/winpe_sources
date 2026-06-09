# UtilIsProtectedProcessByPid(ulong)

- ea: `0x180038d80`
- end: `0x180038e3d`
- name: `?UtilIsProtectedProcessByPid@@YA_NK@Z`
- size: `189`
- prototype: `bool __fastcall(DWORD dwProcessId)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180009190`

## callees

- `0x180009f40`
- `0x180038c0c`
- `0x180038d80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038dbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038dbf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038e1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038e1c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180038da3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180038da3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall UtilIsProtectedProcessByPid(DWORD dwProcessId)
{
  HANDLE v2; // rax
  void *v3; // rdi
  char v4; // bl
  signed int LastError; // eax
  int v7; // [rsp+48h] [rbp+10h] BYREF
  HANDLE v8; // [rsp+50h] [rbp+18h]

  v7 = 0;
  v2 = OpenProcess(0x1000u, 0, dwProcessId);
  v3 = v2;
  v8 = v2;
  v4 = 1;
  if ( (unsigned __int64)v2 + 1 <= 1 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        &WPP_6a89774ccafd3658ac587217d925a2f4_Traceguids,
        dwProcessId,
        LastError);
    return 0;
  }
  UtilGetProtectedProcessInfo(v2, (enum _PS_PROTECTED_TYPE *)&v7, 0);
  CloseHandle(v3);
  if ( v7 <= 0 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x180038d80  mov     [rsp+arg_0], rbx
0x180038d85  mov     [rsp+arg_18], rsi
0x180038d8a  push    rdi
0x180038d8b  sub     rsp, 30h
0x180038d8f  mov     esi, ecx
0x180038d91  mov     [rsp+38h+arg_8], 0
0x180038d99  mov     r8d, ecx; dwProcessId
0x180038d9c  xor     edx, edx; bInheritHandle
0x180038d9e  mov     ecx, 1000h; dwDesiredAccess
0x180038da3  call    cs:__imp_OpenProcess
0x180038da9  mov     rdi, rax
0x180038dac  mov     [rsp+38h+arg_10], rax
0x180038db1  lea     rdx, [rax+1]
0x180038db5  mov     ebx, 1
0x180038dba  cmp     rdx, rbx
0x180038dbd  ja      short loc_180038E08
0x180038dbf  call    cs:__imp_GetLastError
0x180038dc5  test    eax, eax
0x180038dc7  jle     short loc_180038DD1
0x180038dc9  movzx   eax, ax
0x180038dcc  or      eax, 80070000h
0x180038dd1  lea     rdx, WPP_GLOBAL_Control
0x180038dd8  mov     rcx, cs:WPP_GLOBAL_Control
0x180038ddf  cmp     rcx, rdx
0x180038de2  jz      short loc_180038E06
0x180038de4  test    [rcx+1Ch], bl
0x180038de7  jz      short loc_180038E06
0x180038de9  mov     edx, 0Dh
0x180038dee  mov     [rsp+38h+var_18], eax
0x180038df2  mov     r9d, esi
0x180038df5  lea     r8, WPP_6a89774ccafd3658ac587217d925a2f4_Traceguids
0x180038dfc  mov     rcx, [rcx+10h]
0x180038e00  call    WPP_SF_Dd
0x180038e05  nop
0x180038e06  jmp     short loc_180038E29
0x180038e08  xor     r8d, r8d; enum _PS_PROTECTED_SIGNER *
0x180038e0b  lea     rdx, [rsp+38h+arg_8]; enum _PS_PROTECTED_TYPE *
0x180038e10  mov     rcx, rdi; void *
0x180038e13  call    ?UtilGetProtectedProcessInfo@@YAJPEAXPEAW4_PS_PROTECTED_TYPE@@PEAW4_PS_PROTECTED_SIGNER@@@Z; UtilGetProtectedProcessInfo(void *,_PS_PROTECTED_TYPE *,_PS_PROTECTED_SIGNER *)
0x180038e18  nop
0x180038e19  mov     rcx, rdi; hObject
0x180038e1c  call    cs:__imp_CloseHandle
0x180038e22  cmp     [rsp+38h+arg_8], 0
0x180038e27  jg      short loc_180038E2B
0x180038e29  xor     bl, bl
0x180038e2b  mov     al, bl
0x180038e2d  mov     rbx, [rsp+38h+arg_0]
0x180038e32  mov     rsi, [rsp+38h+arg_18]
0x180038e37  add     rsp, 30h
0x180038e3b  pop     rdi
0x180038e3c  retn
```
