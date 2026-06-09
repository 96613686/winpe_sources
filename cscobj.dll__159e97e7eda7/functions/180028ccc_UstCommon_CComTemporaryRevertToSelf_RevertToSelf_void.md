# UstCommon::CComTemporaryRevertToSelf::RevertToSelf(void)

- ea: `0x180028ccc`
- end: `0x180028d5b`
- name: `?RevertToSelf@CComTemporaryRevertToSelf@UstCommon@@QEAAJXZ`
- size: `143`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027a30`

## callees

- `0x180028ccc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028d1f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180028d1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180028ce9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180028ce9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028cfc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180028cfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028d29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028d41`

## pseudocode

```c
__int64 __fastcall UstCommon::CComTemporaryRevertToSelf::RevertToSelf(PHANDLE TokenHandle)
{
  signed int v2; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v5; // eax

  v2 = -2147467259;
  if ( !*TokenHandle )
  {
    v2 = 0;
    *TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xEu, 1, TokenHandle) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v2 >= 0 && !RevertToSelf() )
    {
      v5 = GetLastError();
      v2 = v5;
      if ( v5 > 0 )
        v2 = (unsigned __int16)v5 | 0x80070000;
      CloseHandle(*TokenHandle);
      *TokenHandle = 0;
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180028ccc  mov     [rsp+arg_0], rbx
0x180028cd1  push    rdi
0x180028cd2  sub     rsp, 20h
0x180028cd6  cmp     qword ptr [rcx], 0
0x180028cda  mov     rdi, rcx
0x180028cdd  mov     ebx, 80004005h
0x180028ce2  jnz     short loc_180028D4E
0x180028ce4  xor     ebx, ebx
0x180028ce6  mov     [rcx], rbx
0x180028ce9  call    cs:__imp_GetCurrentThread
0x180028cef  mov     r9, rdi; TokenHandle
0x180028cf2  lea     edx, [rbx+0Eh]; DesiredAccess
0x180028cf5  mov     rcx, rax; ThreadHandle
0x180028cf8  lea     r8d, [rbx+1]; OpenAsSelf
0x180028cfc  call    cs:__imp_OpenThreadToken
0x180028d02  test    eax, eax
0x180028d04  jnz     short loc_180028D1B
0x180028d06  call    cs:__imp_GetLastError
0x180028d0c  mov     ebx, eax
0x180028d0e  test    eax, eax
0x180028d10  jle     short loc_180028D1B
0x180028d12  movzx   ebx, ax
0x180028d15  or      ebx, 80070000h
0x180028d1b  test    ebx, ebx
0x180028d1d  js      short loc_180028D4E
0x180028d1f  call    cs:__imp_RevertToSelf
0x180028d25  test    eax, eax
0x180028d27  jnz     short loc_180028D4E
0x180028d29  call    cs:__imp_GetLastError
0x180028d2f  mov     ebx, eax
0x180028d31  test    eax, eax
0x180028d33  jle     short loc_180028D3E
0x180028d35  movzx   ebx, ax
0x180028d38  or      ebx, 80070000h
0x180028d3e  mov     rcx, [rdi]; hObject
0x180028d41  call    cs:__imp_CloseHandle
0x180028d47  mov     qword ptr [rdi], 0
0x180028d4e  mov     eax, ebx
0x180028d50  mov     rbx, [rsp+28h+arg_0]
0x180028d55  add     rsp, 20h
0x180028d59  pop     rdi
0x180028d5a  retn
```
