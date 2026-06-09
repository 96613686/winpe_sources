# FormFullPathName

- ea: `0x180069844`
- end: `0x1800698e1`
- name: `FormFullPathName`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180069a4c`

## callees

- `0x180069844`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180069875`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180069875`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180069886`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180069886`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800698c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800698d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800698c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800698d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800698b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800698b6`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180069864`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800698a1`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180069864`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x1800698a1`

## pseudocode

```c
WCHAR *__fastcall FormFullPathName(LPCWSTR lpFileName)
{
  DWORD FullPathNameW; // ebp
  HANDLE ProcessHeap; // rax
  WCHAR *v4; // rax
  WCHAR *v5; // rsi
  DWORD LastError; // ebx

  if ( lpFileName && *lpFileName )
  {
    FullPathNameW = GetFullPathNameW(lpFileName, 0, 0, 0);
    if ( FullPathNameW )
    {
      ProcessHeap = GetProcessHeap();
      v4 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2LL * FullPathNameW);
      v5 = v4;
      if ( v4 )
      {
        LastError = 0;
        if ( !GetFullPathNameW(lpFileName, FullPathNameW, v4, 0) )
          goto LABEL_9;
      }
      else
      {
        LastError = 14;
      }
LABEL_10:
      SetLastError(LastError);
      return v5;
    }
    v5 = 0;
LABEL_9:
    LastError = GetLastError();
    goto LABEL_10;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180069844  push    rbx
0x180069846  push    rbp
0x180069847  push    rsi
0x180069848  push    rdi
0x180069849  sub     rsp, 28h
0x18006984d  mov     rdi, rcx
0x180069850  test    rcx, rcx
0x180069853  jz      short loc_1800698CB
0x180069855  xor     eax, eax
0x180069857  cmp     ax, [rcx]
0x18006985a  jz      short loc_1800698CB
0x18006985c  xor     r9d, r9d; lpFilePart
0x18006985f  xor     r8d, r8d; lpBuffer
0x180069862  xor     edx, edx; nBufferLength
0x180069864  call    cs:__imp_GetFullPathNameW
0x18006986a  mov     ebp, eax
0x18006986c  test    eax, eax
0x18006986e  jz      short loc_1800698B4
0x180069870  mov     ebx, ebp
0x180069872  add     rbx, rbx
0x180069875  call    cs:__imp_GetProcessHeap
0x18006987b  mov     r8, rbx; dwBytes
0x18006987e  mov     edx, 8; dwFlags
0x180069883  mov     rcx, rax; hHeap
0x180069886  call    cs:__imp_HeapAlloc
0x18006988c  mov     rsi, rax
0x18006988f  test    rax, rax
0x180069892  jz      short loc_1800698AD
0x180069894  xor     r9d, r9d; lpFilePart
0x180069897  mov     r8, rax; lpBuffer
0x18006989a  mov     edx, ebp; nBufferLength
0x18006989c  mov     rcx, rdi; lpFileName
0x18006989f  xor     ebx, ebx
0x1800698a1  call    cs:__imp_GetFullPathNameW
0x1800698a7  test    eax, eax
0x1800698a9  jnz     short loc_1800698BE
0x1800698ab  jmp     short loc_1800698B6
0x1800698ad  mov     ebx, 0Eh
0x1800698b2  jmp     short loc_1800698BE
0x1800698b4  xor     esi, esi
0x1800698b6  call    cs:__imp_GetLastError
0x1800698bc  mov     ebx, eax
0x1800698be  mov     ecx, ebx; dwErrCode
0x1800698c0  call    cs:__imp_SetLastError
0x1800698c6  mov     rax, rsi
0x1800698c9  jmp     short loc_1800698D8
0x1800698cb  mov     ecx, 57h ; 'W'; dwErrCode
0x1800698d0  call    cs:__imp_SetLastError
0x1800698d6  xor     eax, eax
0x1800698d8  add     rsp, 28h
0x1800698dc  pop     rdi
0x1800698dd  pop     rsi
0x1800698de  pop     rbp
0x1800698df  pop     rbx
0x1800698e0  retn
```
