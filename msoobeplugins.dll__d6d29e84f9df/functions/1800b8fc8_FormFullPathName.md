# FormFullPathName

- ea: `0x1800b8fc8`
- end: `0x1800b9065`
- name: `FormFullPathName`
- size: `157`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800b91d0`

## callees

- `0x1800b8fc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b900a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800b900a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8ff9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b8ff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b903a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b903a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b9044`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b9054`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b9044`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b9054`
- `KERNEL32!GetFullPathNameW` at `0x1800b8fe8`
- `KERNEL32!GetFullPathNameW` at `0x1800b9025`
- `KERNEL32!GetFullPathNameW` at `0x1800b8fe8`
- `KERNEL32!GetFullPathNameW` at `0x1800b9025`

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
0x1800b8fc8  push    rbx
0x1800b8fca  push    rbp
0x1800b8fcb  push    rsi
0x1800b8fcc  push    rdi
0x1800b8fcd  sub     rsp, 28h
0x1800b8fd1  mov     rdi, rcx
0x1800b8fd4  test    rcx, rcx
0x1800b8fd7  jz      short loc_1800B904F
0x1800b8fd9  xor     eax, eax
0x1800b8fdb  cmp     ax, [rcx]
0x1800b8fde  jz      short loc_1800B904F
0x1800b8fe0  xor     r9d, r9d; lpFilePart
0x1800b8fe3  xor     r8d, r8d; lpBuffer
0x1800b8fe6  xor     edx, edx; nBufferLength
0x1800b8fe8  call    cs:__imp_GetFullPathNameW
0x1800b8fee  mov     ebp, eax
0x1800b8ff0  test    eax, eax
0x1800b8ff2  jz      short loc_1800B9038
0x1800b8ff4  mov     ebx, ebp
0x1800b8ff6  add     rbx, rbx
0x1800b8ff9  call    cs:__imp_GetProcessHeap
0x1800b8fff  mov     r8, rbx; dwBytes
0x1800b9002  mov     edx, 8; dwFlags
0x1800b9007  mov     rcx, rax; hHeap
0x1800b900a  call    cs:__imp_HeapAlloc
0x1800b9010  mov     rsi, rax
0x1800b9013  test    rax, rax
0x1800b9016  jz      short loc_1800B9031
0x1800b9018  xor     r9d, r9d; lpFilePart
0x1800b901b  mov     r8, rax; lpBuffer
0x1800b901e  mov     edx, ebp; nBufferLength
0x1800b9020  mov     rcx, rdi; lpFileName
0x1800b9023  xor     ebx, ebx
0x1800b9025  call    cs:__imp_GetFullPathNameW
0x1800b902b  test    eax, eax
0x1800b902d  jnz     short loc_1800B9042
0x1800b902f  jmp     short loc_1800B903A
0x1800b9031  mov     ebx, 0Eh
0x1800b9036  jmp     short loc_1800B9042
0x1800b9038  xor     esi, esi
0x1800b903a  call    cs:__imp_GetLastError
0x1800b9040  mov     ebx, eax
0x1800b9042  mov     ecx, ebx; dwErrCode
0x1800b9044  call    cs:__imp_SetLastError
0x1800b904a  mov     rax, rsi
0x1800b904d  jmp     short loc_1800B905C
0x1800b904f  mov     ecx, 57h ; 'W'; dwErrCode
0x1800b9054  call    cs:__imp_SetLastError
0x1800b905a  xor     eax, eax
0x1800b905c  add     rsp, 28h
0x1800b9060  pop     rdi
0x1800b9061  pop     rsi
0x1800b9062  pop     rbp
0x1800b9063  pop     rbx
0x1800b9064  retn
```
