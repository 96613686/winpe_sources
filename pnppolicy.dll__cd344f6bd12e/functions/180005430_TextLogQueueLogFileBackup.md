# TextLogQueueLogFileBackup

- ea: `0x180005430`
- end: `0x1800054cd`
- name: `TextLogQueueLogFileBackup`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800063bc`

## callees

- `0x180004ec4`
- `0x180005430`
- `0x18000a1a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000549a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000549a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000547f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000547f`
- `KERNEL32!MoveFileExW` at `0x180005475`
- `KERNEL32!MoveFileExW` at `0x180005475`

## pseudocode

```c
__int64 __fastcall TextLogQueueLogFileBackup(LPCWSTR lpExistingFileName)
{
  unsigned int v2; // edi
  DWORD LastError; // ebx
  WCHAR NewFileName[264]; // [rsp+30h] [rbp-228h] BYREF

  v2 = 0;
  LastError = 0;
  if ( !(unsigned int)TextLogGenerateBackupLogFileName(lpExistingFileName, NewFileName)
    || !MoveFileExW(lpExistingFileName, NewFileName, 5u) )
  {
    LastError = GetLastError();
  }
  SetLastError(LastError);
  LOBYTE(v2) = LastError == 0;
  return v2;
}

```

## disassembly

```asm
0x180005430  mov     [rsp+arg_8], rbx
0x180005435  mov     [rsp+arg_10], rsi
0x18000543a  push    rdi
0x18000543b  sub     rsp, 250h
0x180005442  mov     rax, cs:__security_cookie
0x180005449  xor     rax, rsp
0x18000544c  mov     [rsp+258h+var_18], rax
0x180005454  mov     rsi, rcx
0x180005457  xor     edi, edi
0x180005459  mov     ebx, edi
0x18000545b  lea     rdx, [rsp+258h+NewFileName]
0x180005460  call    TextLogGenerateBackupLogFileName
0x180005465  test    eax, eax
0x180005467  jz      short loc_18000547F
0x180005469  lea     r8d, [rdi+5]; dwFlags
0x18000546d  lea     rdx, [rsp+258h+NewFileName]; lpNewFileName
0x180005472  mov     rcx, rsi; lpExistingFileName
0x180005475  call    cs:__imp_MoveFileExW
0x18000547b  test    eax, eax
0x18000547d  jnz     short loc_18000548B
0x18000547f  call    cs:__imp_GetLastError
0x180005485  mov     [rsp+258h+var_238], eax
0x180005489  mov     ebx, eax
0x18000548b  jmp     short loc_180005498
0x18000548d  mov     ebx, 54Fh
0x180005492  mov     [rsp+258h+var_238], ebx
0x180005496  xor     edi, edi
0x180005498  mov     ecx, ebx; dwErrCode
0x18000549a  call    cs:__imp_SetLastError
0x1800054a0  test    ebx, ebx
0x1800054a2  setz    dil
0x1800054a6  mov     eax, edi
0x1800054a8  mov     rcx, [rsp+258h+var_18]
0x1800054b0  xor     rcx, rsp; StackCookie
0x1800054b3  call    __security_check_cookie
0x1800054b8  lea     r11, [rsp+258h+var_8]
0x1800054c0  mov     rbx, [r11+18h]
0x1800054c4  mov     rsi, [r11+20h]
0x1800054c8  mov     rsp, r11
0x1800054cb  pop     rdi
0x1800054cc  retn
```
