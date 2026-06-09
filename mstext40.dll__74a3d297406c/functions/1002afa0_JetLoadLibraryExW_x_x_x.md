# JetLoadLibraryExW(x,x,x)

- ea: `0x1002afa0`
- end: `0x1002b06b`
- name: `_JetLoadLibraryExW@12`
- size: `203`
- prototype: `int __stdcall(LPCWSTR lpLibFileName, HANDLE hFile, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1002b070`

## callees

- `0x1002a5c0`
- `0x1002afa0`
- `0x1002b81a`
- `0x1002df32`

## import_xrefs

- `KERNEL32!LoadLibraryExA` at `0x1002b023`
- `KERNEL32!LoadLibraryExA` at `0x1002b023`
- `KERNEL32!SetLastError` at `0x1002b010`
- `KERNEL32!SetLastError` at `0x1002b010`
- `KERNEL32!LoadLibraryExW` at `0x1002afda`
- `KERNEL32!LoadLibraryExW` at `0x1002afda`

## pseudocode

```c
HMODULE __stdcall JetLoadLibraryExW(LPCWSTR lpLibFileName, HANDLE hFile, int a3)
{
  HMODULE Library; // esi
  int v5; // [esp+8h] [ebp-218h] BYREF
  LPCSTR v6; // [esp+Ch] [ebp-214h]
  char v7; // [esp+10h] [ebp-210h] BYREF
  int v8; // [esp+218h] [ebp-8h]

  if ( wrap )
    return LoadLibraryExW(lpLibFileName, hFile, a3 | 8);
  v5 = 0;
  v6 = 0;
  CStrIn::Init((CStrIn *)&v5, lpLibFileName, -1);
  if ( v8 < 260 )
  {
    Library = LoadLibraryExA(v6, hFile, a3 | 8);
  }
  else
  {
    SetLastError(0xA1u);
    Library = 0;
  }
  if ( v6 != &v7 && (unsigned int)v6 >> 16 && v5 != -1 )
    free((void *)v6);
  return Library;
}

```

## disassembly

```asm
0x1002afa0  sub     esp, 218h
0x1002afa6  mov     eax, ___security_cookie
0x1002afab  xor     eax, esp
0x1002afad  mov     [esp+218h+var_4], eax
0x1002afb4  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1002afbb  mov     eax, [esp+218h+lpLibFileName]
0x1002afc2  push    esi
0x1002afc3  mov     esi, [esp+21Ch+arg_8]
0x1002afca  push    edi
0x1002afcb  mov     edi, [esp+220h+hFile]
0x1002afd2  jz      short loc_1002AFE2
0x1002afd4  or      esi, 8
0x1002afd7  push    esi; dwFlags
0x1002afd8  push    edi; hFile
0x1002afd9  push    eax; lpLibFileName
0x1002afda  call    ds:__imp__LoadLibraryExW@12; LoadLibraryExW(x,x,x)
0x1002afe0  jmp     short loc_1002B052
0x1002afe2  push    0FFFFFFFFh; int
0x1002afe4  push    eax; lpWideCharStr
0x1002afe5  lea     ecx, [esp+228h+var_218]; this
0x1002afe9  mov     [esp+228h+var_218], 0
0x1002aff1  mov     [esp+228h+var_214], 0
0x1002aff9  call    ?Init@CStrIn@@IAEXPB_WH@Z; CStrIn::Init(wchar_t const *,int)
0x1002affe  cmp     [esp+220h+var_8], 104h
0x1002b009  jl      short loc_1002B01A
0x1002b00b  push    0A1h; dwErrCode
0x1002b010  call    ds:__imp__SetLastError@4; SetLastError(x)
0x1002b016  xor     esi, esi
0x1002b018  jmp     short loc_1002B02B
0x1002b01a  or      esi, 8
0x1002b01d  push    esi; dwFlags
0x1002b01e  push    edi; hFile
0x1002b01f  push    [esp+228h+var_214]; lpLibFileName
0x1002b023  call    ds:__imp__LoadLibraryExA@12; LoadLibraryExA(x,x,x)
0x1002b029  mov     esi, eax
0x1002b02b  mov     eax, [esp+220h+var_214]
0x1002b02f  lea     ecx, [esp+220h+var_210]
0x1002b033  cmp     eax, ecx
0x1002b035  jz      short loc_1002B050
0x1002b037  mov     ecx, eax
0x1002b039  shr     ecx, 10h
0x1002b03c  test    ecx, ecx
0x1002b03e  jz      short loc_1002B050
0x1002b040  cmp     [esp+220h+var_218], 0FFFFFFFFh
0x1002b045  jz      short loc_1002B050
0x1002b047  push    eax; Block
0x1002b048  call    _free
0x1002b04d  add     esp, 4
0x1002b050  mov     eax, esi
0x1002b052  mov     ecx, [esp+220h+var_4]
0x1002b059  pop     edi
0x1002b05a  pop     esi
0x1002b05b  xor     ecx, esp; StackCookie
0x1002b05d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002b062  add     esp, 218h
0x1002b068  retn    0Ch
```
