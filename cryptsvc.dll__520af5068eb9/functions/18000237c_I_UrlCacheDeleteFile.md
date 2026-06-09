# I_UrlCacheDeleteFile

- ea: `0x18000237c`
- end: `0x1800023ed`
- name: `I_UrlCacheDeleteFile`
- size: `113`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800025c8`

## callees

- `0x18000237c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800023b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800023dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800023dd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002396`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180002396`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800023cc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800023cc`

## pseudocode

```c
__int64 __fastcall I_UrlCacheDeleteFile(LPCWSTR lpFileName)
{
  __int64 v1; // rdi
  unsigned int v3; // ebx
  DWORD LastError; // eax

  v1 = 0;
  v3 = 1;
  while ( !DeleteFileW(lpFileName) )
  {
    LastError = GetLastError();
    if ( (LastError != 32 || (unsigned int)v1 >= 6) && (LastError != 5 || (_DWORD)v1) )
    {
      SetLastError(LastError);
      return 0;
    }
    Sleep(*((_DWORD *)qword_18001B4D0 + v1));
    v1 = (unsigned int)(v1 + 1);
  }
  return v3;
}

```

## disassembly

```asm
0x18000237c  mov     [rsp+arg_0], rbx
0x180002381  mov     [rsp+arg_8], rsi
0x180002386  push    rdi
0x180002387  sub     rsp, 20h
0x18000238b  xor     edi, edi
0x18000238d  mov     rsi, rcx
0x180002390  lea     ebx, [rdi+1]
0x180002393  mov     rcx, rsi; lpFileName
0x180002396  call    cs:__imp_DeleteFileW
0x18000239c  test    eax, eax
0x18000239e  jz      short loc_1800023B2
0x1800023a0  mov     rsi, [rsp+28h+arg_8]
0x1800023a5  mov     eax, ebx
0x1800023a7  mov     rbx, [rsp+28h+arg_0]
0x1800023ac  add     rsp, 20h
0x1800023b0  pop     rdi
0x1800023b1  retn
0x1800023b2  call    cs:__imp_GetLastError
0x1800023b8  cmp     eax, 20h ; ' '
0x1800023bb  jnz     short loc_1800023D6
0x1800023bd  cmp     edi, 6
0x1800023c0  jnb     short loc_1800023D6
0x1800023c2  lea     rax, qword_18001B4D0
0x1800023c9  mov     ecx, [rax+rdi*4]; dwMilliseconds
0x1800023cc  call    cs:__imp_Sleep
0x1800023d2  add     edi, ebx
0x1800023d4  jmp     short loc_180002393
0x1800023d6  cmp     eax, 5
0x1800023d9  jz      short loc_1800023E7
0x1800023db  mov     ecx, eax; dwErrCode
0x1800023dd  call    cs:__imp_SetLastError
0x1800023e3  xor     ebx, ebx
0x1800023e5  jmp     short loc_1800023A0
0x1800023e7  cmp     edi, ebx
0x1800023e9  jnb     short loc_1800023DB
0x1800023eb  jmp     short loc_1800023C2
```
