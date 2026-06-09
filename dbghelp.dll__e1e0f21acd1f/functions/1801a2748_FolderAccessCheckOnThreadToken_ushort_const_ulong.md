# FolderAccessCheckOnThreadToken(ushort const *,ulong)

- ea: `0x1801a2748`
- end: `0x1801a2805`
- name: `?FolderAccessCheckOnThreadToken@@YAJPEBGK@Z`
- size: `189`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801a360c`

## callees

- `0x1801a25c4`
- `0x1801a2748`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a278a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801a278a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a27f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801a27f7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801a2772`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801a27d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801a2772`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801a27d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801a275b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801a27b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801a275b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801a27b9`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1801a27af`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x1801a27af`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801a27e6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1801a27e6`

## pseudocode

```c
signed int __fastcall FolderAccessCheckOnThreadToken(const unsigned __int16 *a1)
{
  HANDLE CurrentThread; // rax
  const unsigned __int16 *v2; // rcx
  unsigned int v3; // r8d
  int v4; // ebx
  signed int result; // eax
  HANDLE v6; // rax
  const unsigned __int16 *v7; // rcx
  unsigned int v8; // r8d
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v4 = FolderAccessCheck(v2, TokenHandle, v3);
LABEL_10:
    if ( TokenHandle != (void *)-1LL )
      CloseHandle(TokenHandle);
    return v4;
  }
  result = GetLastError();
  if ( result == 1008 )
  {
    v4 = -2147024891;
    if ( ImpersonateSelf(SecurityImpersonation) )
    {
      v6 = GetCurrentThread();
      if ( OpenThreadToken(v6, 8u, 1, &TokenHandle) )
        v4 = FolderAccessCheck(v7, TokenHandle, v8);
      RevertToSelf();
    }
    goto LABEL_10;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1801a2748  mov     [rsp+TokenHandle], rcx
0x1801a274d  push    rbx
0x1801a274e  sub     rsp, 20h
0x1801a2752  mov     [rsp+28h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1801a275b  call    cs:__imp_GetCurrentThread
0x1801a2761  mov     edx, 8; DesiredAccess
0x1801a2766  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1801a276b  mov     rcx, rax; ThreadHandle
0x1801a276e  lea     r8d, [rdx-7]; OpenAsSelf
0x1801a2772  call    cs:__imp_OpenThreadToken
0x1801a2778  test    eax, eax
0x1801a277a  jz      short loc_1801A278A
0x1801a277c  mov     rdx, [rsp+28h+TokenHandle]; void *
0x1801a2781  call    ?FolderAccessCheck@@YAJPEBGPEAXK@Z; FolderAccessCheck(ushort const *,void *,ulong)
0x1801a2786  mov     ebx, eax
0x1801a2788  jmp     short loc_1801A27EC
0x1801a278a  call    cs:__imp_GetLastError
0x1801a2790  cmp     eax, 3F0h
0x1801a2795  jz      short loc_1801A27A5
0x1801a2797  test    eax, eax
0x1801a2799  jle     short loc_1801A27FF
0x1801a279b  movzx   eax, ax
0x1801a279e  or      eax, 80070000h
0x1801a27a3  jmp     short loc_1801A27FF
0x1801a27a5  mov     ecx, 2; ImpersonationLevel
0x1801a27aa  mov     ebx, 80070005h
0x1801a27af  call    cs:__imp_ImpersonateSelf
0x1801a27b5  test    eax, eax
0x1801a27b7  jz      short loc_1801A27EC
0x1801a27b9  call    cs:__imp_GetCurrentThread
0x1801a27bf  mov     edx, 8; DesiredAccess
0x1801a27c4  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1801a27c9  mov     rcx, rax; ThreadHandle
0x1801a27cc  lea     r8d, [rdx-7]; OpenAsSelf
0x1801a27d0  call    cs:__imp_OpenThreadToken
0x1801a27d6  test    eax, eax
0x1801a27d8  jz      short loc_1801A27E6
0x1801a27da  mov     rdx, [rsp+28h+TokenHandle]; void *
0x1801a27df  call    ?FolderAccessCheck@@YAJPEBGPEAXK@Z; FolderAccessCheck(ushort const *,void *,ulong)
0x1801a27e4  mov     ebx, eax
0x1801a27e6  call    cs:__imp_RevertToSelf
0x1801a27ec  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1801a27f1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801a27f5  jz      short loc_1801A27FD
0x1801a27f7  call    cs:__imp_CloseHandle
0x1801a27fd  mov     eax, ebx
0x1801a27ff  add     rsp, 20h
0x1801a2803  pop     rbx
0x1801a2804  retn
```
