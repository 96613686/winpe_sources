# _pSpUtilsCreateFile

- ea: `0x180007968`
- end: `0x1800079e7`
- name: `_pSpUtilsCreateFile`
- size: `127`
- prototype: `DWORD __fastcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, __int64, __int64, int, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180007f70`

## callees

- `0x180007968`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079b4`
- `KERNEL32!SleepEx` at `0x1800079cd`
- `KERNEL32!SleepEx` at `0x1800079cd`
- `KERNEL32!CreateFileW` at `0x1800079a5`
- `KERNEL32!CreateFileW` at `0x1800079a5`

## pseudocode

```c
DWORD __fastcall pSpUtilsCreateFile(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned int a6,
        _QWORD *a7)
{
  unsigned int v9; // ebx
  HANDLE FileW; // rax
  DWORD result; // eax

  v9 = 0;
  do
  {
    FileW = CreateFileW(lpFileName, dwDesiredAccess, 1u, 0, 4u, 0, 0);
    *a7 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      result = GetLastError();
      if ( result != 32 || v9 >= a6 )
        return result;
      SleepEx(0x32u, 0);
      v9 += 50;
    }
  }
  while ( *a7 == -1 );
  return 0;
}

```

## disassembly

```asm
0x180007968  push    rbx
0x18000796a  push    rbp
0x18000796b  push    rsi
0x18000796c  push    rdi
0x18000796d  sub     rsp, 48h
0x180007971  mov     rdi, [rsp+68h+arg_30]
0x180007979  mov     esi, edx
0x18000797b  mov     rbp, rcx
0x18000797e  xor     ebx, ebx
0x180007980  xor     r9d, r9d; lpSecurityAttributes
0x180007983  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18000798c  mov     [rsp+68h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180007994  mov     edx, esi; dwDesiredAccess
0x180007996  mov     rcx, rbp; lpFileName
0x180007999  mov     [rsp+68h+dwCreationDisposition], 4; dwCreationDisposition
0x1800079a1  lea     r8d, [r9+1]; dwShareMode
0x1800079a5  call    cs:__imp_CreateFileW
0x1800079ab  mov     [rdi], rax
0x1800079ae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800079b2  jnz     short loc_1800079D6
0x1800079b4  call    cs:__imp_GetLastError
0x1800079ba  cmp     eax, 20h ; ' '
0x1800079bd  jnz     short loc_1800079DE
0x1800079bf  cmp     ebx, [rsp+68h+arg_28]
0x1800079c6  jnb     short loc_1800079DE
0x1800079c8  xor     edx, edx; bAlertable
0x1800079ca  lea     ecx, [rax+12h]; dwMilliseconds
0x1800079cd  call    cs:__imp_SleepEx
0x1800079d3  add     ebx, 32h ; '2'
0x1800079d6  cmp     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x1800079da  jz      short loc_180007980
0x1800079dc  xor     eax, eax
0x1800079de  add     rsp, 48h
0x1800079e2  pop     rdi
0x1800079e3  pop     rsi
0x1800079e4  pop     rbp
0x1800079e5  pop     rbx
0x1800079e6  retn
```
