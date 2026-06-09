# CImpersonate::SuspendImpersonation(void)

- ea: `0x18000b230`
- end: `0x18000b2ce`
- name: `?SuspendImpersonation@CImpersonate@@QEAAJXZ`
- size: `158`
- prototype: `__int64 __fastcall(CImpersonate *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000847c`
- `0x18003496c`

## callees

- `0x18000b230`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b283`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b283`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b28c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b28c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b2b3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b268`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000b268`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b276`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000b276`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b255`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b255`

## pseudocode

```c
__int64 __fastcall CImpersonate::SuspendImpersonation(CImpersonate *this)
{
  unsigned int v3; // ebx
  void **v4; // rsi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax

  if ( (*((_BYTE *)this + 8) & 1) != 0 )
    return 2147549183LL;
  v3 = 0;
  v4 = (void **)((char *)this + 16);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, v4) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      if ( LastError <= 0 )
        return (unsigned int)LastError;
      return (unsigned __int16)LastError | 0x80070000;
    }
LABEL_9:
    *((_DWORD *)this + 2) |= 1u;
    return v3;
  }
  if ( SetThreadToken(0, 0) )
    goto LABEL_9;
  CloseHandle(*v4);
  *v4 = 0;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v3;
}

```

## disassembly

```asm
0x18000b230  mov     [rsp+arg_0], rbx
0x18000b235  mov     [rsp+arg_8], rsi
0x18000b23a  push    rdi
0x18000b23b  sub     rsp, 20h
0x18000b23f  test    byte ptr [rcx+8], 1
0x18000b243  mov     rdi, rcx
0x18000b246  jz      short loc_18000B24F
0x18000b248  mov     eax, 8000FFFFh
0x18000b24d  jmp     short loc_18000B2A3
0x18000b24f  xor     ebx, ebx
0x18000b251  lea     rsi, [rcx+10h]
0x18000b255  call    cs:__imp_GetCurrentThread
0x18000b25b  mov     r9, rsi; TokenHandle
0x18000b25e  lea     edx, [rbx+4]; DesiredAccess
0x18000b261  mov     rcx, rax; ThreadHandle
0x18000b264  lea     r8d, [rbx+1]; OpenAsSelf
0x18000b268  call    cs:__imp_OpenThreadToken
0x18000b26e  test    eax, eax
0x18000b270  jz      short loc_18000B2B3
0x18000b272  xor     edx, edx; Token
0x18000b274  xor     ecx, ecx; Thread
0x18000b276  call    cs:__imp_SetThreadToken
0x18000b27c  test    eax, eax
0x18000b27e  jnz     short loc_18000B2C0
0x18000b280  mov     rcx, [rsi]; hObject
0x18000b283  call    cs:__imp_CloseHandle
0x18000b289  mov     [rsi], rbx
0x18000b28c  call    cs:__imp_GetLastError
0x18000b292  mov     ebx, eax
0x18000b294  test    eax, eax
0x18000b296  jle     short loc_18000B2A1
0x18000b298  movzx   ebx, ax
0x18000b29b  or      ebx, 80070000h
0x18000b2a1  mov     eax, ebx
0x18000b2a3  mov     rbx, [rsp+28h+arg_0]
0x18000b2a8  mov     rsi, [rsp+28h+arg_8]
0x18000b2ad  add     rsp, 20h
0x18000b2b1  pop     rdi
0x18000b2b2  retn
0x18000b2b3  call    cs:__imp_GetLastError
0x18000b2b9  cmp     eax, 3F0h
0x18000b2be  jnz     short loc_18000B2C6
0x18000b2c0  or      dword ptr [rdi+8], 1
0x18000b2c4  jmp     short loc_18000B2A1
0x18000b2c6  test    eax, eax
0x18000b2c8  jg      short loc_18000B298
0x18000b2ca  mov     ebx, eax
0x18000b2cc  jmp     short loc_18000B2A1
```
