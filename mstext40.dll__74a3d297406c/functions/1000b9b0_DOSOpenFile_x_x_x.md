# DOSOpenFile(x,x,x)

- ea: `0x1000b9b0`
- end: `0x1000ba2b`
- name: `_DOSOpenFile@12`
- size: `123`
- prototype: `int __stdcall(LPCWSTR lpFileName, int, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x100113f0`
- `0x1001ad40`
- `0x1001d570`
- `0x1001ff80`
- `0x10029180`

## callees

- `0x1000b9b0`
- `0x1002a920`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000ba13`
- `KERNEL32!GetLastError` at `0x1000ba13`

## pseudocode

```c
int __stdcall DOSOpenFile(LPCWSTR lpFileName, char a2, _DWORD *a3)
{
  DWORD v3; // ecx
  DWORD v4; // eax
  HANDLE FileW; // eax
  int result; // eax

  if ( (a2 & 2) != 0 )
  {
    v3 = -1073741824;
  }
  else
  {
    v3 = 0x80000000;
    if ( (a2 & 1) != 0 )
      v3 = 0x40000000;
  }
  if ( (a2 & 0x10) != 0 )
  {
    v4 = 0;
  }
  else if ( (a2 & 0x20) != 0 )
  {
    v4 = 1;
  }
  else
  {
    v4 = 3 - ((a2 & 0x30) != 0);
  }
  FileW = JetCreateFileW(lpFileName, v3, v4, 0, 3u, 128, 0);
  if ( FileW == (HANDLE)-1 )
  {
    result = -(unsigned __int16)GetLastError();
    if ( !result )
      return -2;
  }
  else
  {
    *a3 = FileW;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1000b9b0  mov     eax, [esp+arg_4]
0x1000b9b4  test    al, 2
0x1000b9b6  jz      short loc_1000B9BF
0x1000b9b8  mov     ecx, 0C0000000h
0x1000b9bd  jmp     short loc_1000B9CE
0x1000b9bf  test    al, 1
0x1000b9c1  mov     ecx, 80000000h
0x1000b9c6  mov     edx, 40000000h
0x1000b9cb  cmovnz  ecx, edx
0x1000b9ce  test    al, 10h
0x1000b9d0  jz      short loc_1000B9D6
0x1000b9d2  xor     eax, eax
0x1000b9d4  jmp     short loc_1000B9ED
0x1000b9d6  test    al, 20h
0x1000b9d8  jz      short loc_1000B9E1
0x1000b9da  mov     eax, 1
0x1000b9df  jmp     short loc_1000B9ED
0x1000b9e1  and     al, 30h
0x1000b9e3  movsx   eax, al
0x1000b9e6  neg     eax
0x1000b9e8  sbb     eax, eax
0x1000b9ea  add     eax, 3
0x1000b9ed  push    0; hTemplateFile
0x1000b9ef  push    80h; int
0x1000b9f4  push    3; dwCreationDisposition
0x1000b9f6  push    0; lpSecurityAttributes
0x1000b9f8  push    eax; dwShareMode
0x1000b9f9  push    ecx; dwDesiredAccess
0x1000b9fa  push    [esp+18h+lpFileName]; lpFileName
0x1000b9fe  call    _JetCreateFileW@28; JetCreateFileW(x,x,x,x,x,x,x)
0x1000ba03  cmp     eax, 0FFFFFFFFh
0x1000ba06  jz      short loc_1000BA13
0x1000ba08  mov     ecx, [esp+arg_8]
0x1000ba0c  mov     [ecx], eax
0x1000ba0e  xor     eax, eax
0x1000ba10  retn    0Ch
0x1000ba13  call    ds:__imp__GetLastError@0; GetLastError()
0x1000ba19  and     eax, 0FFFFh
0x1000ba1e  mov     ecx, 0FFFFFFFEh
0x1000ba23  neg     eax
0x1000ba25  cmovz   eax, ecx
0x1000ba28  retn    0Ch
```
