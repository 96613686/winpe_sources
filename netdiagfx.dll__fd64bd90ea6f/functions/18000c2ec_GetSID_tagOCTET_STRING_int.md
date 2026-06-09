# GetSID(tagOCTET_STRING *,int)

- ea: `0x18000c2ec`
- end: `0x18000c426`
- name: `?GetSID@@YAJPEAUtagOCTET_STRING@@H@Z`
- size: `314`
- prototype: `__int64 __fastcall(struct tagOCTET_STRING *, DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d8dc`

## callees

- `0x1800020d6`
- `0x18000c2ec`
- `0x18002c802`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000c3ca`
- `KERNEL32!GetLastError` at `0x18000c3ec`
- `KERNEL32!GetLastError` at `0x18000c3ca`
- `KERNEL32!GetLastError` at `0x18000c3ec`
- `KERNEL32!GetCurrentThread` at `0x18000c343`
- `KERNEL32!GetCurrentThread` at `0x18000c343`
- `KERNEL32!CloseHandle` at `0x18000c3e4`
- `KERNEL32!CloseHandle` at `0x18000c3e4`
- `ADVAPI32!OpenThreadToken` at `0x18000c359`
- `ADVAPI32!OpenThreadToken` at `0x18000c359`
- `ADVAPI32!GetTokenInformation` at `0x18000c389`
- `ADVAPI32!GetTokenInformation` at `0x18000c389`
- `ADVAPI32!GetLengthSid` at `0x18000c396`
- `ADVAPI32!GetLengthSid` at `0x18000c396`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c3a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c324`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000c3a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c404`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetSID(struct tagOCTET_STRING *a1, DWORD a2)
{
  PSID *v4; // rax
  PSID *v5; // rdi
  HANDLE CurrentThread; // rax
  DWORD LengthSid; // ebp
  BYTE *v8; // rax
  unsigned int v9; // ebx
  signed int LastError; // eax
  signed int v11; // eax
  void *TokenHandle; // [rsp+50h] [rbp+8h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp+10h] BYREF

  ReturnLength = a2;
  if ( !a1 )
    return 2147942487LL;
  TokenHandle = 0;
  v4 = (PSID *)CoTaskMemAlloc(0x4000u);
  v5 = v4;
  if ( v4 )
  {
    memset_0(v4, 0, 0x4000u);
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x20008u, 0, &TokenHandle) )
    {
      ReturnLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenUser, v5, 0x4000u, &ReturnLength) )
      {
        LengthSid = GetLengthSid(*v5);
        v8 = (BYTE *)CoTaskMemAlloc(LengthSid);
        a1->lpValue = v8;
        if ( v8 )
        {
          v9 = 0;
          memcpy_0(v8, *v5, LengthSid);
          a1->dwLength = LengthSid;
        }
        else
        {
          v9 = -2147024882;
        }
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
      CloseHandle(TokenHandle);
    }
    else
    {
      v11 = GetLastError();
      v9 = v11;
      if ( v11 > 0 )
        v9 = (unsigned __int16)v11 | 0x80070000;
    }
    CoTaskMemFree(v5);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v9;
}

```

## disassembly

```asm
0x18000c2ec  mov     [rsp+arg_10], rbx
0x18000c2f1  mov     [rsp+arg_18], rbp
0x18000c2f6  mov     [rsp+arg_8], edx
0x18000c2fa  push    rsi
0x18000c2fb  push    rdi
0x18000c2fc  push    r14
0x18000c2fe  sub     rsp, 30h
0x18000c302  mov     rsi, rcx
0x18000c305  test    rcx, rcx
0x18000c308  jnz     short loc_18000C314
0x18000c30a  mov     eax, 80070057h
0x18000c30f  jmp     loc_18000C413
0x18000c314  mov     ebx, 4000h
0x18000c319  mov     [rsp+48h+TokenHandle], 0
0x18000c322  mov     ecx, ebx; cb
0x18000c324  call    cs:__imp_CoTaskMemAlloc
0x18000c32a  mov     rdi, rax
0x18000c32d  test    rax, rax
0x18000c330  jz      loc_18000C40C
0x18000c336  mov     r8d, ebx; Size
0x18000c339  xor     edx, edx; Val
0x18000c33b  mov     rcx, rax; void *
0x18000c33e  call    memset_0
0x18000c343  call    cs:__imp_GetCurrentThread
0x18000c349  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x18000c34e  xor     r8d, r8d; OpenAsSelf
0x18000c351  mov     rcx, rax; ThreadHandle
0x18000c354  mov     edx, 20008h; DesiredAccess
0x18000c359  call    cs:__imp_OpenThreadToken
0x18000c35f  test    eax, eax
0x18000c361  jz      loc_18000C3EC
0x18000c367  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18000c36c  lea     rax, [rsp+48h+arg_8]
0x18000c371  mov     r9d, ebx; TokenInformationLength
0x18000c374  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000c379  mov     r8, rdi; TokenInformation
0x18000c37c  mov     [rsp+48h+arg_8], 0
0x18000c384  mov     edx, 1; TokenInformationClass
0x18000c389  call    cs:__imp_GetTokenInformation
0x18000c38f  test    eax, eax
0x18000c391  jz      short loc_18000C3CA
0x18000c393  mov     rcx, [rdi]; pSid
0x18000c396  call    cs:__imp_GetLengthSid
0x18000c39c  mov     ecx, eax; cb
0x18000c39e  mov     ebp, eax
0x18000c3a0  call    cs:__imp_CoTaskMemAlloc
0x18000c3a6  mov     [rsi+8], rax
0x18000c3aa  test    rax, rax
0x18000c3ad  jz      short loc_18000C3C3
0x18000c3af  mov     rdx, [rdi]; Src
0x18000c3b2  xor     ebx, ebx
0x18000c3b4  mov     r8d, ebp; Size
0x18000c3b7  mov     rcx, rax; void *
0x18000c3ba  call    memcpy_0
0x18000c3bf  mov     [rsi], ebp
0x18000c3c1  jmp     short loc_18000C3DF
0x18000c3c3  mov     ebx, 8007000Eh
0x18000c3c8  jmp     short loc_18000C3DF
0x18000c3ca  call    cs:__imp_GetLastError
0x18000c3d0  mov     ebx, eax
0x18000c3d2  test    eax, eax
0x18000c3d4  jle     short loc_18000C3DF
0x18000c3d6  movzx   ebx, ax
0x18000c3d9  or      ebx, 80070000h
0x18000c3df  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18000c3e4  call    cs:__imp_CloseHandle
0x18000c3ea  jmp     short loc_18000C401
0x18000c3ec  call    cs:__imp_GetLastError
0x18000c3f2  mov     ebx, eax
0x18000c3f4  test    eax, eax
0x18000c3f6  jle     short loc_18000C401
0x18000c3f8  movzx   ebx, ax
0x18000c3fb  or      ebx, 80070000h
0x18000c401  mov     rcx, rdi; pv
0x18000c404  call    cs:__imp_CoTaskMemFree
0x18000c40a  jmp     short loc_18000C411
0x18000c40c  mov     ebx, 8007000Eh
0x18000c411  mov     eax, ebx
0x18000c413  mov     rbx, [rsp+48h+arg_10]
0x18000c418  mov     rbp, [rsp+48h+arg_18]
0x18000c41d  add     rsp, 30h
0x18000c421  pop     r14
0x18000c423  pop     rdi
0x18000c424  pop     rsi
0x18000c425  retn
```
