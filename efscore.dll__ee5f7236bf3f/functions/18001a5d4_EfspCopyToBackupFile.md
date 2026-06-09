# EfspCopyToBackupFile

- ea: `0x18001a5d4`
- end: `0x18001a79a`
- name: `EfspCopyToBackupFile`
- size: `454`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b61c`
- `0x18001c22c`

## callees

- `0x180019e9c`
- `0x18001a5d4`
- `0x180063698`
- `0x180066828`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a74b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a61d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a669`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a74b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a613`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001a613`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a5f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001a5f9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001a741`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001a741`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a782`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a782`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001a65a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001a65a`
- `ntdll!NtFsControlFile` at `0x18001a6b5`
- `ntdll!NtFsControlFile` at `0x18001a6b5`

## pseudocode

```c
__int64 __fastcall EfspCopyToBackupFile(__int64 a1, void *a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v6; // ebx
  char v7; // si
  int v8; // eax
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  DWORD v12; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp+18h] BYREF

  TokenHandle = 0;
  IoStatusBlock = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v6 = LastError;
    v7 = -32;
LABEL_3:
    v8 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 10, v7);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v8, 10, v7);
    goto LABEL_12;
  }
  if ( !RevertToSelf() )
  {
    v6 = 1008;
    LastError = GetLastError();
    v7 = -20;
    goto LABEL_3;
  }
  v9 = NtFsControlFile(a2, 0, 0, 0, &IoStatusBlock, 0x90194u, 0, 0, 0, 0);
  v10 = v9;
  if ( v9 >= 0
    || (fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v9, 10, 253),
        (v6 = EfspMapError(v10, (unsigned int)(*(_DWORD *)(a1 + 76) != 0) + 6000)) == 0) )
  {
    v11 = EfspCopyStreamlessFile(*(HANDLE *)(a1 + 8), a2);
    v6 = v11;
    if ( v11 )
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v11, 10, 9);
  }
  if ( !SetThreadToken(0, TokenHandle) )
  {
    v12 = GetLastError();
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v12, 10, 23);
  }
LABEL_12:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v6;
}

```

## disassembly

```asm
0x18001a5d4  mov     rax, rsp
0x18001a5d7  mov     [rax+8], rbx
0x18001a5db  mov     [rax+10h], rbp
0x18001a5df  push    rsi
0x18001a5e0  sub     rsp, 60h
0x18001a5e4  xorps   xmm0, xmm0
0x18001a5e7  mov     qword ptr [rax+18h], 0
0x18001a5ef  movups  xmmword ptr [rax-18h], xmm0
0x18001a5f3  mov     rsi, rdx
0x18001a5f6  mov     rbp, rcx
0x18001a5f9  call    cs:__imp_GetCurrentThread
0x18001a5ff  mov     edx, 0Ch; DesiredAccess
0x18001a604  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x18001a60c  mov     rcx, rax; ThreadHandle
0x18001a60f  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x18001a613  call    cs:__imp_OpenThreadToken
0x18001a619  test    eax, eax
0x18001a61b  jnz     short loc_18001A65A
0x18001a61d  call    cs:__imp_GetLastError
0x18001a623  mov     ebx, eax
0x18001a625  mov     esi, 6E0h
0x18001a62a  mov     rcx, cs:g_hPublisher
0x18001a631  lea     rdx, EFS_API_ERROR
0x18001a638  mov     r9d, 0Ah
0x18001a63e  mov     dword ptr [rsp+68h+IoStatusBlock], esi
0x18001a642  mov     r8d, eax
0x18001a645  call    fnEfsLogTrace1
0x18001a64a  lea     rdx, EFS_TRACE_ERROR
0x18001a651  mov     dword ptr [rsp+68h+IoStatusBlock], esi
0x18001a655  jmp     loc_18001A760
0x18001a65a  call    cs:__imp_RevertToSelf
0x18001a660  test    eax, eax
0x18001a662  jnz     short loc_18001A676
0x18001a664  mov     ebx, 3F0h
0x18001a669  call    cs:__imp_GetLastError
0x18001a66f  mov     esi, 6ECh
0x18001a674  jmp     short loc_18001A62A
0x18001a676  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x18001a67e  lea     rax, [rsp+68h+var_18]
0x18001a683  mov     [rsp+68h+OutputBuffer], 0; OutputBuffer
0x18001a68c  xor     r9d, r9d; ApcContext
0x18001a68f  mov     [rsp+68h+InputBufferLength], 0; InputBufferLength
0x18001a697  xor     r8d, r8d; ApcRoutine
0x18001a69a  mov     [rsp+68h+InputBuffer], 0; InputBuffer
0x18001a6a3  xor     edx, edx; Event
0x18001a6a5  mov     [rsp+68h+FsControlCode], 90194h; FsControlCode
0x18001a6ad  mov     rcx, rsi; FileHandle
0x18001a6b0  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x18001a6b5  call    cs:__imp_NtFsControlFile
0x18001a6bb  mov     ebx, eax
0x18001a6bd  test    eax, eax
0x18001a6bf  jns     short loc_18001A701
0x18001a6c1  mov     rcx, cs:g_hPublisher
0x18001a6c8  lea     rdx, EFS_API_ERROR
0x18001a6cf  mov     r9d, 0Ah
0x18001a6d5  mov     dword ptr [rsp+68h+IoStatusBlock], 6FDh
0x18001a6dd  mov     r8d, eax
0x18001a6e0  call    fnEfsLogTrace1
0x18001a6e5  mov     ecx, [rbp+4Ch]
0x18001a6e8  neg     ecx
0x18001a6ea  mov     ecx, ebx
0x18001a6ec  sbb     edx, edx
0x18001a6ee  neg     edx
0x18001a6f0  add     edx, 1770h
0x18001a6f6  call    EfspMapError
0x18001a6fb  mov     ebx, eax
0x18001a6fd  test    eax, eax
0x18001a6ff  jnz     short loc_18001A737
0x18001a701  mov     rcx, [rbp+8]; HANDLE
0x18001a705  mov     rdx, rsi; hFile
0x18001a708  call    EfspCopyStreamlessFile
0x18001a70d  mov     ebx, eax
0x18001a70f  test    eax, eax
0x18001a711  jz      short loc_18001A737
0x18001a713  mov     rcx, cs:g_hPublisher
0x18001a71a  lea     rdx, EFS_API_ERROR
0x18001a721  mov     r9d, 0Ah
0x18001a727  mov     dword ptr [rsp+68h+IoStatusBlock], 709h
0x18001a72f  mov     r8d, eax
0x18001a732  call    fnEfsLogTrace1
0x18001a737  mov     rdx, [rsp+68h+TokenHandle]; Token
0x18001a73f  xor     ecx, ecx; Thread
0x18001a741  call    cs:__imp_SetThreadToken
0x18001a747  test    eax, eax
0x18001a749  jnz     short loc_18001A775
0x18001a74b  call    cs:__imp_GetLastError
0x18001a751  lea     rdx, EFS_API_ERROR
0x18001a758  mov     dword ptr [rsp+68h+IoStatusBlock], 717h
0x18001a760  mov     rcx, cs:g_hPublisher
0x18001a767  mov     r9d, 0Ah
0x18001a76d  mov     r8d, eax
0x18001a770  call    fnEfsLogTrace1
0x18001a775  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18001a77d  test    rcx, rcx
0x18001a780  jz      short loc_18001A788
0x18001a782  call    cs:__imp_CloseHandle
0x18001a788  mov     rbp, [rsp+68h+arg_8]
0x18001a78d  mov     eax, ebx
0x18001a78f  mov     rbx, [rsp+68h+arg_0]
0x18001a794  add     rsp, 60h
0x18001a798  pop     rsi
0x18001a799  retn
```
