# WcCreateFile

- ea: `0x14000e1c8`
- end: `0x14000e27e`
- name: `WcCreateFile`
- size: `182`
- prototype: `__int64 __fastcall(int, int, int, int, void *Block)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000e4c0`

## callees

- `0x14000e1c8`
- `0x14000ea6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000e269`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000e269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e23d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e23d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000e22b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000e22b`

## pseudocode

```c
__int64 __fastcall WcCreateFile(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, void *Block)
{
  __int64 result; // rax
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  LPCWSTR lpFileName; // [rsp+50h] [rbp+8h] BYREF

  *a1 = -1;
  Block = 0;
  lpFileName = 0;
  result = WcpConstructLongPath(a2, &Block, &lpFileName);
  if ( (int)result >= 0 )
  {
    FileW = CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      *a1 = FileW;
      v9 = 0;
    }
    if ( Block )
      free(Block);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x14000e1c8  mov     r11, rsp
0x14000e1cb  push    rbx
0x14000e1cc  sub     rsp, 40h
0x14000e1d0  mov     rax, rdx
0x14000e1d3  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x14000e1da  mov     rbx, rcx
0x14000e1dd  mov     qword ptr [r11+28h], 0
0x14000e1e5  mov     rcx, rax
0x14000e1e8  mov     qword ptr [r11+8], 0
0x14000e1f0  lea     r8, [r11+8]
0x14000e1f4  lea     rdx, [r11+28h]
0x14000e1f8  call    WcpConstructLongPath
0x14000e1fd  test    eax, eax
0x14000e1ff  js      short loc_14000E277
0x14000e201  mov     rcx, [rsp+48h+lpFileName]; lpFileName
0x14000e206  xor     r9d, r9d; lpSecurityAttributes
0x14000e209  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14000e212  mov     edx, 80000000h; dwDesiredAccess
0x14000e217  mov     [rsp+48h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x14000e21f  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x14000e227  lea     r8d, [r9+7]; dwShareMode
0x14000e22b  call    cs:__imp_CreateFileW
0x14000e232  nop     dword ptr [rax+rax+00h]
0x14000e237  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000e23b  jnz     short loc_14000E25A
0x14000e23d  call    cs:__imp_GetLastError
0x14000e244  nop     dword ptr [rax+rax+00h]
0x14000e249  mov     ebx, eax
0x14000e24b  test    eax, eax
0x14000e24d  jle     short loc_14000E25F
0x14000e24f  movzx   ebx, ax
0x14000e252  or      ebx, 80070000h
0x14000e258  jmp     short loc_14000E25F
0x14000e25a  mov     [rbx], rax
0x14000e25d  xor     ebx, ebx
0x14000e25f  mov     rcx, [rsp+48h+Block]; Block
0x14000e264  test    rcx, rcx
0x14000e267  jz      short loc_14000E275
0x14000e269  call    cs:__imp_free
0x14000e270  nop     dword ptr [rax+rax+00h]
0x14000e275  mov     eax, ebx
0x14000e277  add     rsp, 40h
0x14000e27b  pop     rbx
0x14000e27c  retn
```
