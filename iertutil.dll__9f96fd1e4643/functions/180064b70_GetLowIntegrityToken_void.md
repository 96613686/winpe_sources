# GetLowIntegrityToken(void * *)

- ea: `0x180064b70`
- end: `0x180064c06`
- name: `?GetLowIntegrityToken@@YAJPEAPEAX@Z`
- size: `150`
- prototype: `__int64 __fastcall(PHANDLE NewTokenHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180064b70`
- `0x180064c0c`
- `0x180064ca4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064be4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064bc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064be4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180064b86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180064b86`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180064b99`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180064b99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064bdc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064bdc`

## pseudocode

```c
__int64 __fastcall GetLowIntegrityToken(PHANDLE NewTokenHandle)
{
  HANDLE CurrentProcess; // rax
  unsigned int v3; // ebx
  signed int LastError; // eax
  signed int v5; // eax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x2000000u, &TokenHandle) )
  {
    if ( !GetLuaToken(TokenHandle, NewTokenHandle) || (v3 = 0, !IESetTokenIntegrityLevel(*NewTokenHandle)) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    CloseHandle(TokenHandle);
  }
  else
  {
    v5 = GetLastError();
    v3 = v5;
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
  }
  return v3;
}

```

## disassembly

```asm
0x180064b70  mov     [rsp+arg_0], rbx
0x180064b75  push    rdi
0x180064b76  sub     rsp, 20h
0x180064b7a  mov     rdi, rcx
0x180064b7d  mov     [rsp+28h+TokenHandle], 0
0x180064b86  call    cs:__imp_GetCurrentProcess
0x180064b8c  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180064b91  mov     edx, 2000000h; DesiredAccess
0x180064b96  mov     rcx, rax; ProcessHandle
0x180064b99  call    cs:__imp_OpenProcessToken
0x180064b9f  test    eax, eax
0x180064ba1  jz      short loc_180064BE4
0x180064ba3  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180064ba8  mov     rdx, rdi; NewTokenHandle
0x180064bab  call    ?GetLuaToken@@YAHPEAXPEAPEAX@Z; GetLuaToken(void *,void * *)
0x180064bb0  test    eax, eax
0x180064bb2  jz      short loc_180064BC2
0x180064bb4  mov     rcx, [rdi]; TokenHandle
0x180064bb7  xor     ebx, ebx
0x180064bb9  call    ?IESetTokenIntegrityLevel@@YAHPEAXK@Z; IESetTokenIntegrityLevel(void *,ulong)
0x180064bbe  test    eax, eax
0x180064bc0  jnz     short loc_180064BD7
0x180064bc2  call    cs:__imp_GetLastError
0x180064bc8  mov     ebx, eax
0x180064bca  test    eax, eax
0x180064bcc  jle     short loc_180064BD7
0x180064bce  movzx   ebx, ax
0x180064bd1  or      ebx, 80070000h
0x180064bd7  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180064bdc  call    cs:__imp_CloseHandle
0x180064be2  jmp     short loc_180064BF9
0x180064be4  call    cs:__imp_GetLastError
0x180064bea  mov     ebx, eax
0x180064bec  test    eax, eax
0x180064bee  jle     short loc_180064BF9
0x180064bf0  movzx   ebx, ax
0x180064bf3  or      ebx, 80070000h
0x180064bf9  mov     eax, ebx
0x180064bfb  mov     rbx, [rsp+28h+arg_0]
0x180064c00  add     rsp, 20h
0x180064c04  pop     rdi
0x180064c05  retn
```
