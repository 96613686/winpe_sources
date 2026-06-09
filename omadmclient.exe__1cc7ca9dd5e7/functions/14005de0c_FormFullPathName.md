# FormFullPathName

- ea: `0x14005de0c`
- end: `0x14005dedc`
- name: `FormFullPathName`
- size: `208`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14005e1a8`

## callees

- `0x14005de0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005de4b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14005de4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14005de62`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14005de62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005de9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005de9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005deae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005dec4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005deae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005dec4`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14005de34`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14005de83`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14005de34`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x14005de83`

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
0x14005de0c  push    rbx
0x14005de0e  push    rbp
0x14005de0f  push    rsi
0x14005de10  push    rdi
0x14005de11  sub     rsp, 28h
0x14005de15  mov     rdi, rcx
0x14005de18  test    rcx, rcx
0x14005de1b  jz      loc_14005DEBF
0x14005de21  xor     eax, eax
0x14005de23  cmp     ax, [rcx]
0x14005de26  jz      loc_14005DEBF
0x14005de2c  xor     r9d, r9d; lpFilePart
0x14005de2f  xor     r8d, r8d; lpBuffer
0x14005de32  xor     edx, edx; nBufferLength
0x14005de34  call    cs:__imp_GetFullPathNameW
0x14005de3b  nop     dword ptr [rax+rax+00h]
0x14005de40  mov     ebp, eax
0x14005de42  test    eax, eax
0x14005de44  jz      short loc_14005DE9C
0x14005de46  mov     ebx, ebp
0x14005de48  add     rbx, rbx
0x14005de4b  call    cs:__imp_GetProcessHeap
0x14005de52  nop     dword ptr [rax+rax+00h]
0x14005de57  mov     r8, rbx; dwBytes
0x14005de5a  mov     edx, 8; dwFlags
0x14005de5f  mov     rcx, rax; hHeap
0x14005de62  call    cs:__imp_HeapAlloc
0x14005de69  nop     dword ptr [rax+rax+00h]
0x14005de6e  mov     rsi, rax
0x14005de71  test    rax, rax
0x14005de74  jz      short loc_14005DE95
0x14005de76  xor     r9d, r9d; lpFilePart
0x14005de79  mov     r8, rax; lpBuffer
0x14005de7c  mov     edx, ebp; nBufferLength
0x14005de7e  mov     rcx, rdi; lpFileName
0x14005de81  xor     ebx, ebx
0x14005de83  call    cs:__imp_GetFullPathNameW
0x14005de8a  nop     dword ptr [rax+rax+00h]
0x14005de8f  test    eax, eax
0x14005de91  jnz     short loc_14005DEAC
0x14005de93  jmp     short loc_14005DE9E
0x14005de95  mov     ebx, 0Eh
0x14005de9a  jmp     short loc_14005DEAC
0x14005de9c  xor     esi, esi
0x14005de9e  call    cs:__imp_GetLastError
0x14005dea5  nop     dword ptr [rax+rax+00h]
0x14005deaa  mov     ebx, eax
0x14005deac  mov     ecx, ebx; dwErrCode
0x14005deae  call    cs:__imp_SetLastError
0x14005deb5  nop     dword ptr [rax+rax+00h]
0x14005deba  mov     rax, rsi
0x14005debd  jmp     short loc_14005DED2
0x14005debf  mov     ecx, 57h ; 'W'; dwErrCode
0x14005dec4  call    cs:__imp_SetLastError
0x14005decb  nop     dword ptr [rax+rax+00h]
0x14005ded0  xor     eax, eax
0x14005ded2  add     rsp, 28h
0x14005ded6  pop     rdi
0x14005ded7  pop     rsi
0x14005ded8  pop     rbp
0x14005ded9  pop     rbx
0x14005deda  retn
```
