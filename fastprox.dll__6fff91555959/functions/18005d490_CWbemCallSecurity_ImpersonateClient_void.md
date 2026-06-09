# CWbemCallSecurity::ImpersonateClient(void)

- ea: `0x18005d490`
- end: `0x18005d561`
- name: `?ImpersonateClient@CWbemCallSecurity@@UEAAJXZ`
- size: `209`
- prototype: `__int64 __fastcall(CWbemCallSecurity *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18005d490`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005d4f0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18005d4f0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005d4cf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005d4cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005d4ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005d4ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d531`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d531`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d539`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005d539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d546`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d546`

## pseudocode

```c
signed int __fastcall CWbemCallSecurity::ImpersonateClient(CWbemCallSecurity *this)
{
  __int64 v2; // rax
  HANDLE *v3; // rdi
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  signed int result; // eax
  DWORD v7; // ebx

  if ( *((_DWORD *)this + 5) )
    return 0;
  v2 = *((_QWORD *)this + 3);
  if ( !v2 )
    return -2147024890;
  if ( !*(_DWORD *)(v2 + 24) )
    return -2147023549;
  v3 = (HANDLE *)((char *)this + 32);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, v3) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 && LastError != 1309 )
      return -2147024891;
  }
  if ( SetThreadToken(0, *(HANDLE *)(*((_QWORD *)this + 3) + 16LL)) )
  {
    *((_DWORD *)this + 5) = *(_DWORD *)(*((_QWORD *)this + 3) + 24LL);
    return 0;
  }
  v7 = GetLastError();
  CloseHandle(*v3);
  SetLastError(v7);
  *v3 = 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18005d490  mov     [rsp+arg_0], rbx
0x18005d495  push    rdi
0x18005d496  sub     rsp, 20h
0x18005d49a  cmp     dword ptr [rcx+14h], 0
0x18005d49e  mov     rbx, rcx
0x18005d4a1  jnz     short loc_18005D504
0x18005d4a3  mov     rax, [rcx+18h]
0x18005d4a7  test    rax, rax
0x18005d4aa  jz      loc_18005D55A
0x18005d4b0  cmp     dword ptr [rax+18h], 0
0x18005d4b4  jz      short loc_18005D51F
0x18005d4b6  lea     rdi, [rcx+20h]
0x18005d4ba  call    cs:__imp_GetCurrentThread
0x18005d4c0  mov     edx, 4; DesiredAccess
0x18005d4c5  mov     r9, rdi; TokenHandle
0x18005d4c8  mov     rcx, rax; ThreadHandle
0x18005d4cb  lea     r8d, [rdx-3]; OpenAsSelf
0x18005d4cf  call    cs:__imp_OpenThreadToken
0x18005d4d5  test    eax, eax
0x18005d4d7  jnz     short loc_18005D4E6
0x18005d4d9  call    cs:__imp_GetLastError
0x18005d4df  cmp     eax, 3F0h
0x18005d4e4  jnz     short loc_18005D511
0x18005d4e6  mov     rdx, [rbx+18h]
0x18005d4ea  xor     ecx, ecx; Thread
0x18005d4ec  mov     rdx, [rdx+10h]; Token
0x18005d4f0  call    cs:__imp_SetThreadToken
0x18005d4f6  test    eax, eax
0x18005d4f8  jz      short loc_18005D526
0x18005d4fa  mov     rax, [rbx+18h]
0x18005d4fe  mov     ecx, [rax+18h]
0x18005d501  mov     [rbx+14h], ecx
0x18005d504  xor     eax, eax
0x18005d506  mov     rbx, [rsp+28h+arg_0]
0x18005d50b  add     rsp, 20h
0x18005d50f  pop     rdi
0x18005d510  retn
0x18005d511  cmp     eax, 51Dh
0x18005d516  jz      short loc_18005D4E6
0x18005d518  mov     eax, 80070005h
0x18005d51d  jmp     short loc_18005D506
0x18005d51f  mov     eax, 80070543h
0x18005d524  jmp     short loc_18005D506
0x18005d526  call    cs:__imp_GetLastError
0x18005d52c  mov     rcx, [rdi]; hObject
0x18005d52f  mov     ebx, eax
0x18005d531  call    cs:__imp_CloseHandle
0x18005d537  mov     ecx, ebx; dwErrCode
0x18005d539  call    cs:__imp_SetLastError
0x18005d53f  mov     qword ptr [rdi], 0
0x18005d546  call    cs:__imp_GetLastError
0x18005d54c  test    eax, eax
0x18005d54e  jle     short loc_18005D506
0x18005d550  movzx   eax, ax
0x18005d553  or      eax, 80070000h
0x18005d558  jmp     short loc_18005D506
0x18005d55a  mov     eax, 80070006h
0x18005d55f  jmp     short loc_18005D506
```
