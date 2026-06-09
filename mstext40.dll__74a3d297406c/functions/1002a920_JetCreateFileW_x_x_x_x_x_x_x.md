# JetCreateFileW(x,x,x,x,x,x,x)

- ea: `0x1002a920`
- end: `0x1002aa05`
- name: `_JetCreateFileW@28`
- size: `229`
- prototype: `int __stdcall(LPCWSTR lpFileName, DWORD dwDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD dwCreationDisposition, int, HANDLE hTemplateFile)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1000b410`
- `0x1000b640`
- `0x1000b9b0`

## callees

- `0x1002a5c0`
- `0x1002a920`
- `0x1002b81a`
- `0x1002df32`

## import_xrefs

- `KERNEL32!CreateFileA` at `0x1002a9bb`
- `KERNEL32!CreateFileA` at `0x1002a9bb`
- `KERNEL32!CreateFileW` at `0x1002a987`
- `KERNEL32!CreateFileW` at `0x1002a987`

## pseudocode

```c
HANDLE __stdcall JetCreateFileW(
        LPCWSTR lpFileName,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        DWORD dwCreationDisposition,
        int a6,
        HANDLE hTemplateFile)
{
  HANDLE FileA; // esi
  int v9; // [esp+18h] [ebp-218h] BYREF
  LPCSTR v10; // [esp+1Ch] [ebp-214h]
  char v11; // [esp+20h] [ebp-210h] BYREF

  if ( wrap )
    return CreateFileW(
             lpFileName,
             dwDesiredAccess,
             dwShareMode,
             lpSecurityAttributes,
             dwCreationDisposition,
             a6 | 0x110000,
             hTemplateFile);
  v9 = 0;
  v10 = 0;
  CStrIn::Init((CStrIn *)&v9, lpFileName, -1);
  FileA = CreateFileA(
            v10,
            dwDesiredAccess,
            dwShareMode,
            lpSecurityAttributes,
            dwCreationDisposition,
            a6 | 0x110000,
            hTemplateFile);
  if ( v10 != &v11 && (unsigned int)v10 >> 16 && v9 != -1 )
    free((void *)v10);
  return FileA;
}

```

## disassembly

```asm
0x1002a920  sub     esp, 220h
0x1002a926  mov     eax, ___security_cookie
0x1002a92b  xor     eax, esp
0x1002a92d  mov     [esp+220h+var_4], eax
0x1002a934  mov     ecx, [esp+220h+dwCreationDisposition]
0x1002a93b  mov     edx, [esp+220h+hTemplateFile]
0x1002a942  mov     eax, [esp+220h+lpFileName]
0x1002a949  push    ebx
0x1002a94a  mov     ebx, [esp+224h+dwShareMode]
0x1002a951  push    ebp
0x1002a952  mov     ebp, [esp+228h+lpSecurityAttributes]
0x1002a959  push    esi
0x1002a95a  mov     esi, [esp+22Ch+arg_14]
0x1002a961  or      esi, 110000h
0x1002a967  mov     [esp+22Ch+var_220], ecx
0x1002a96b  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1002a972  push    edi
0x1002a973  mov     edi, [esp+230h+dwDesiredAccess]
0x1002a97a  mov     [esp+230h+var_21C], edx
0x1002a97e  jz      short loc_1002A98F
0x1002a980  push    edx; hTemplateFile
0x1002a981  push    esi; dwFlagsAndAttributes
0x1002a982  push    ecx; dwCreationDisposition
0x1002a983  push    ebp; lpSecurityAttributes
0x1002a984  push    ebx; dwShareMode
0x1002a985  push    edi; dwDesiredAccess
0x1002a986  push    eax; lpFileName
0x1002a987  call    ds:__imp__CreateFileW@28; CreateFileW(x,x,x,x,x,x,x)
0x1002a98d  jmp     short loc_1002A9EA
0x1002a98f  push    0FFFFFFFFh; int
0x1002a991  push    eax; lpWideCharStr
0x1002a992  lea     ecx, [esp+238h+var_218]; this
0x1002a996  mov     [esp+238h+var_218], 0
0x1002a99e  mov     [esp+238h+var_214], 0
0x1002a9a6  call    ?Init@CStrIn@@IAEXPB_WH@Z; CStrIn::Init(wchar_t const *,int)
0x1002a9ab  push    [esp+230h+var_21C]; hTemplateFile
0x1002a9af  push    esi; dwFlagsAndAttributes
0x1002a9b0  push    [esp+238h+var_220]; dwCreationDisposition
0x1002a9b4  push    ebp; lpSecurityAttributes
0x1002a9b5  push    ebx; dwShareMode
0x1002a9b6  push    edi; dwDesiredAccess
0x1002a9b7  push    [esp+248h+var_214]; lpFileName
0x1002a9bb  call    ds:__imp__CreateFileA@28; CreateFileA(x,x,x,x,x,x,x)
0x1002a9c1  mov     esi, eax
0x1002a9c3  lea     ecx, [esp+230h+var_210]
0x1002a9c7  mov     eax, [esp+230h+var_214]
0x1002a9cb  cmp     eax, ecx
0x1002a9cd  jz      short loc_1002A9E8
0x1002a9cf  mov     ecx, eax
0x1002a9d1  shr     ecx, 10h
0x1002a9d4  test    ecx, ecx
0x1002a9d6  jz      short loc_1002A9E8
0x1002a9d8  cmp     [esp+230h+var_218], 0FFFFFFFFh
0x1002a9dd  jz      short loc_1002A9E8
0x1002a9df  push    eax; Block
0x1002a9e0  call    _free
0x1002a9e5  add     esp, 4
0x1002a9e8  mov     eax, esi
0x1002a9ea  mov     ecx, [esp+230h+var_4]
0x1002a9f1  pop     edi
0x1002a9f2  pop     esi
0x1002a9f3  pop     ebp
0x1002a9f4  pop     ebx
0x1002a9f5  xor     ecx, esp; StackCookie
0x1002a9f7  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002a9fc  add     esp, 220h
0x1002aa02  retn    1Ch
```
