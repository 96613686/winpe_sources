# GetSID(tagOCTET_STRING *,int)

- ea: `0x180008f1c`
- end: `0x180009053`
- name: `?GetSID@@YAJPEAUtagOCTET_STRING@@H@Z`
- size: `311`
- prototype: `__int64 __fastcall(struct tagOCTET_STRING *, DWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x18000a730`
- `0x18000b3c0`

## callees

- `0x1800026a6`
- `0x180008f1c`
- `0x18001f652`

## import_xrefs

- `ADVAPI32!GetLengthSid` at `0x180008fc3`
- `ADVAPI32!GetLengthSid` at `0x180008fc3`
- `ADVAPI32!GetTokenInformation` at `0x180008fb6`
- `ADVAPI32!GetTokenInformation` at `0x180008fb6`
- `ADVAPI32!OpenProcessToken` at `0x180008f86`
- `ADVAPI32!OpenProcessToken` at `0x180008f86`
- `KERNEL32!GetLastError` at `0x180008ff7`
- `KERNEL32!GetLastError` at `0x180009019`
- `KERNEL32!GetLastError` at `0x180008ff7`
- `KERNEL32!GetLastError` at `0x180009019`
- `KERNEL32!GetCurrentProcess` at `0x180008f73`
- `KERNEL32!GetCurrentProcess` at `0x180008f73`
- `KERNEL32!CloseHandle` at `0x180009011`
- `KERNEL32!CloseHandle` at `0x180009011`
- `ole32!CoTaskMemAlloc` at `0x180008f54`
- `ole32!CoTaskMemAlloc` at `0x180008fcd`
- `ole32!CoTaskMemAlloc` at `0x180008f54`
- `ole32!CoTaskMemAlloc` at `0x180008fcd`
- `ole32!CoTaskMemFree` at `0x180009031`
- `ole32!CoTaskMemFree` at `0x180009031`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetSID(struct tagOCTET_STRING *a1, DWORD a2)
{
  PSID *v4; // rax
  PSID *v5; // rdi
  HANDLE CurrentProcess; // rax
  DWORD LengthSid; // ebp
  BYTE *v8; // rax
  unsigned int v9; // ebx
  signed int LastError; // eax
  signed int v11; // eax
  HANDLE TokenHandle; // [rsp+50h] [rbp+8h] BYREF
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
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
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
0x180008f1c  mov     [rsp+arg_10], rbx
0x180008f21  mov     [rsp+arg_18], rbp
0x180008f26  mov     [rsp+arg_8], edx
0x180008f2a  push    rsi
0x180008f2b  push    rdi
0x180008f2c  push    r14
0x180008f2e  sub     rsp, 30h
0x180008f32  mov     rsi, rcx
0x180008f35  test    rcx, rcx
0x180008f38  jnz     short loc_180008F44
0x180008f3a  mov     eax, 80070057h
0x180008f3f  jmp     loc_180009040
0x180008f44  mov     ebx, 4000h
0x180008f49  mov     [rsp+48h+TokenHandle], 0
0x180008f52  mov     ecx, ebx; cb
0x180008f54  call    cs:__imp_CoTaskMemAlloc
0x180008f5a  mov     rdi, rax
0x180008f5d  test    rax, rax
0x180008f60  jz      loc_180009039
0x180008f66  mov     r8d, ebx; Size
0x180008f69  xor     edx, edx; Val
0x180008f6b  mov     rcx, rax; void *
0x180008f6e  call    memset_0
0x180008f73  call    cs:__imp_GetCurrentProcess
0x180008f79  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180008f7e  mov     edx, 20008h; DesiredAccess
0x180008f83  mov     rcx, rax; ProcessHandle
0x180008f86  call    cs:__imp_OpenProcessToken
0x180008f8c  test    eax, eax
0x180008f8e  jz      loc_180009019
0x180008f94  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x180008f99  lea     rax, [rsp+48h+arg_8]
0x180008f9e  mov     r9d, ebx; TokenInformationLength
0x180008fa1  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180008fa6  mov     r8, rdi; TokenInformation
0x180008fa9  mov     [rsp+48h+arg_8], 0
0x180008fb1  mov     edx, 1; TokenInformationClass
0x180008fb6  call    cs:__imp_GetTokenInformation
0x180008fbc  test    eax, eax
0x180008fbe  jz      short loc_180008FF7
0x180008fc0  mov     rcx, [rdi]; pSid
0x180008fc3  call    cs:__imp_GetLengthSid
0x180008fc9  mov     ecx, eax; cb
0x180008fcb  mov     ebp, eax
0x180008fcd  call    cs:__imp_CoTaskMemAlloc
0x180008fd3  mov     [rsi+8], rax
0x180008fd7  test    rax, rax
0x180008fda  jz      short loc_180008FF0
0x180008fdc  mov     rdx, [rdi]; Src
0x180008fdf  xor     ebx, ebx
0x180008fe1  mov     r8d, ebp; Size
0x180008fe4  mov     rcx, rax; void *
0x180008fe7  call    memcpy_0
0x180008fec  mov     [rsi], ebp
0x180008fee  jmp     short loc_18000900C
0x180008ff0  mov     ebx, 8007000Eh
0x180008ff5  jmp     short loc_18000900C
0x180008ff7  call    cs:__imp_GetLastError
0x180008ffd  mov     ebx, eax
0x180008fff  test    eax, eax
0x180009001  jle     short loc_18000900C
0x180009003  movzx   ebx, ax
0x180009006  or      ebx, 80070000h
0x18000900c  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180009011  call    cs:__imp_CloseHandle
0x180009017  jmp     short loc_18000902E
0x180009019  call    cs:__imp_GetLastError
0x18000901f  mov     ebx, eax
0x180009021  test    eax, eax
0x180009023  jle     short loc_18000902E
0x180009025  movzx   ebx, ax
0x180009028  or      ebx, 80070000h
0x18000902e  mov     rcx, rdi; pv
0x180009031  call    cs:__imp_CoTaskMemFree
0x180009037  jmp     short loc_18000903E
0x180009039  mov     ebx, 8007000Eh
0x18000903e  mov     eax, ebx
0x180009040  mov     rbx, [rsp+48h+arg_10]
0x180009045  mov     rbp, [rsp+48h+arg_18]
0x18000904a  add     rsp, 30h
0x18000904e  pop     r14
0x180009050  pop     rdi
0x180009051  pop     rsi
0x180009052  retn
```
