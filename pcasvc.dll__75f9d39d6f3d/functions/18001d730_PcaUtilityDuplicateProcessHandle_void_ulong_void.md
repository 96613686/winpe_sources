# PcaUtilityDuplicateProcessHandle(void * *,ulong,void *)

- ea: `0x18001d730`
- end: `0x18001d858`
- name: `?PcaUtilityDuplicateProcessHandle@@YAKPEAPEAXKPEAX@Z`
- size: `296`
- prototype: `__int64 __fastcall(void **, DWORD, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001d030`
- `0x18008f2b0`

## callees

- `0x180012920`
- `0x18001d730`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d7ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d803`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d76a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d76a`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d7a5`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x18001d7a5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001d796`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001d796`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d7e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d84d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d7e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d84d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001d758`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001d758`

## string_xrefs

- `0x18001d7f4`: `Failed to open client process [%u]`

## pseudocode

```c
__int64 __fastcall PcaUtilityDuplicateProcessHandle(void **a1, DWORD a2, void *a3)
{
  HANDLE v5; // rdi
  HANDLE CurrentProcess; // rax
  unsigned int v7; // ebx
  DWORD LastError; // eax
  const char *v10; // r9
  int v11; // r8d
  int v12; // ecx
  HANDLE TargetHandle; // [rsp+68h] [rbp+20h] BYREF

  TargetHandle = 0;
  v5 = OpenProcess(0x440u, 0, a2);
  if ( !v5 )
  {
    LastError = GetLastError();
    v10 = "Failed to open client process [%u]";
    v11 = 489;
LABEL_12:
    v7 = LastError;
    v12 = 1;
    goto LABEL_14;
  }
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(v5, a3, CurrentProcess, &TargetHandle, 0x1FFFFFu, 0, 0) )
  {
    LastError = GetLastError();
    v10 = "Failed to duplicate process handle [%u]";
    v11 = 505;
    goto LABEL_12;
  }
  if ( GetProcessId(TargetHandle) )
  {
    v7 = 0;
    *a1 = TargetHandle;
    TargetHandle = 0;
    goto LABEL_5;
  }
  v7 = 6;
  v10 = "Handle not valid [%u]";
  v11 = 516;
  v12 = 2;
LABEL_14:
  AslLogCallPrintf(v12, (unsigned int)"PcaUtilityDuplicateProcessHandle", v11, (_DWORD)v10);
LABEL_5:
  if ( TargetHandle )
    CloseHandle(TargetHandle);
  if ( v5 )
    CloseHandle(v5);
  return v7;
}

```

## disassembly

```asm
0x18001d730  mov     [rsp+arg_0], rbx
0x18001d735  mov     [rsp+arg_8], rsi
0x18001d73a  push    rdi
0x18001d73b  sub     rsp, 40h
0x18001d73f  mov     rbx, r8
0x18001d742  mov     [rsp+48h+TargetHandle], 0
0x18001d74b  mov     r8d, edx; dwProcessId
0x18001d74e  mov     rsi, rcx
0x18001d751  xor     edx, edx; bInheritHandle
0x18001d753  mov     ecx, 440h; dwDesiredAccess
0x18001d758  call    cs:__imp_OpenProcess
0x18001d75e  mov     rdi, rax
0x18001d761  test    rax, rax
0x18001d764  jz      loc_18001D7EE
0x18001d76a  call    cs:__imp_GetCurrentProcess
0x18001d770  mov     [rsp+48h+dwOptions], 0; dwOptions
0x18001d778  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x18001d77d  mov     r8, rax; hTargetProcessHandle
0x18001d780  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x18001d788  mov     rdx, rbx; hSourceHandle
0x18001d78b  mov     [rsp+48h+dwDesiredAccess], 1FFFFFh; dwDesiredAccess
0x18001d793  mov     rcx, rdi; hSourceProcessHandle
0x18001d796  call    cs:__imp_DuplicateHandle
0x18001d79c  test    eax, eax
0x18001d79e  jz      short loc_18001D803
0x18001d7a0  mov     rcx, [rsp+48h+TargetHandle]; Process
0x18001d7a5  call    cs:__imp_GetProcessId
0x18001d7ab  test    eax, eax
0x18001d7ad  jz      short loc_18001D823
0x18001d7af  mov     rax, [rsp+48h+TargetHandle]
0x18001d7b4  xor     ebx, ebx
0x18001d7b6  mov     [rsi], rax
0x18001d7b9  mov     [rsp+48h+TargetHandle], rbx
0x18001d7be  mov     rcx, [rsp+48h+TargetHandle]; hObject
0x18001d7c3  test    rcx, rcx
0x18001d7c6  jnz     loc_18001D84D
0x18001d7cc  test    rdi, rdi
0x18001d7cf  jnz     short loc_18001D7E3
0x18001d7d1  mov     rsi, [rsp+48h+arg_8]
0x18001d7d6  mov     eax, ebx
0x18001d7d8  mov     rbx, [rsp+48h+arg_0]
0x18001d7dd  add     rsp, 40h
0x18001d7e1  pop     rdi
0x18001d7e2  retn
0x18001d7e3  mov     rcx, rdi; hObject
0x18001d7e6  call    cs:__imp_CloseHandle
0x18001d7ec  jmp     short loc_18001D7D1
0x18001d7ee  call    cs:__imp_GetLastError
0x18001d7f4  lea     r9, aFailedToOpenCl; "Failed to open client process [%u]"
0x18001d7fb  mov     r8d, 1E9h
0x18001d801  jmp     short loc_18001D816
0x18001d803  call    cs:__imp_GetLastError
0x18001d809  lea     r9, aFailedToDuplic_5; "Failed to duplicate process handle [%u]"
0x18001d810  mov     r8d, 1F9h
0x18001d816  mov     [rsp+48h+dwDesiredAccess], eax
0x18001d81a  mov     ebx, eax
0x18001d81c  mov     ecx, 1
0x18001d821  jmp     short loc_18001D83C
0x18001d823  mov     ebx, 6
0x18001d828  lea     r9, aHandleNotValid; "Handle not valid [%u]"
0x18001d82f  mov     [rsp+48h+dwDesiredAccess], ebx
0x18001d833  mov     r8d, 204h
0x18001d839  lea     ecx, [rbx-4]
0x18001d83c  lea     rdx, aPcautilitydupl_0; "PcaUtilityDuplicateProcessHandle"
0x18001d843  call    AslLogCallPrintf
0x18001d848  jmp     loc_18001D7BE
0x18001d84d  call    cs:__imp_CloseHandle
0x18001d853  jmp     loc_18001D7CC
```
