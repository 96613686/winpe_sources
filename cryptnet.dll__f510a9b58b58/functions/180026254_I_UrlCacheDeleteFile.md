# I_UrlCacheDeleteFile

- ea: `0x180026254`
- end: `0x1800262c1`
- name: `I_UrlCacheDeleteFile`
- size: `109`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001ff84`

## callees

- `0x180026254`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002629b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002629b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800262a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800262a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026278`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026278`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002626e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002626e`

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
    Sleep(*((_DWORD *)qword_18002BA20 + v1));
    v1 = (unsigned int)(v1 + 1);
  }
  return v3;
}

```

## disassembly

```asm
0x180026254  mov     [rsp+arg_0], rbx
0x180026259  mov     [rsp+arg_8], rsi
0x18002625e  push    rdi
0x18002625f  sub     rsp, 20h
0x180026263  xor     edi, edi
0x180026265  mov     rsi, rcx
0x180026268  lea     ebx, [rdi+1]
0x18002626b  mov     rcx, rsi; lpFileName
0x18002626e  call    cs:__imp_DeleteFileW
0x180026274  test    eax, eax
0x180026276  jnz     short loc_1800262AF
0x180026278  call    cs:__imp_GetLastError
0x18002627e  cmp     eax, 20h ; ' '
0x180026281  jnz     short loc_180026288
0x180026283  cmp     edi, 6
0x180026286  jb      short loc_180026291
0x180026288  cmp     eax, 5
0x18002628b  jnz     short loc_1800262A5
0x18002628d  cmp     edi, ebx
0x18002628f  jnb     short loc_1800262A5
0x180026291  lea     rax, qword_18002BA20
0x180026298  mov     ecx, [rax+rdi*4]; dwMilliseconds
0x18002629b  call    cs:__imp_Sleep
0x1800262a1  add     edi, ebx
0x1800262a3  jmp     short loc_18002626B
0x1800262a5  mov     ecx, eax; dwErrCode
0x1800262a7  call    cs:__imp_SetLastError
0x1800262ad  xor     ebx, ebx
0x1800262af  mov     rsi, [rsp+28h+arg_8]
0x1800262b4  mov     eax, ebx
0x1800262b6  mov     rbx, [rsp+28h+arg_0]
0x1800262bb  add     rsp, 20h
0x1800262bf  pop     rdi
0x1800262c0  retn
```
