# JetDeleteFileW(x)

- ea: `0x1002aa10`
- end: `0x1002aaba`
- name: `_JetDeleteFileW@4`
- size: `170`
- prototype: `int __stdcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1000b5f0`

## callees

- `0x1002a5c0`
- `0x1002aa10`
- `0x1002b81a`
- `0x1002df32`

## import_xrefs

- `KERNEL32!DeleteFileA` at `0x1002aa73`
- `KERNEL32!DeleteFileA` at `0x1002aa73`
- `KERNEL32!DeleteFileW` at `0x1002aa35`
- `KERNEL32!DeleteFileW` at `0x1002aa35`

## pseudocode

```c
BOOL __stdcall JetDeleteFileW(LPCWSTR lpFileName)
{
  BOOL v2; // esi
  int v3; // [esp+0h] [ebp-218h] BYREF
  LPCSTR v4; // [esp+4h] [ebp-214h]
  char v5; // [esp+8h] [ebp-210h] BYREF

  if ( wrap )
    return DeleteFileW(lpFileName);
  v3 = 0;
  v4 = 0;
  CStrIn::Init((CStrIn *)&v3, lpFileName, -1);
  v2 = DeleteFileA(v4);
  if ( v4 != &v5 && (unsigned int)v4 >> 16 && v3 != -1 )
    free((void *)v4);
  return v2;
}

```

## disassembly

```asm
0x1002aa10  sub     esp, 218h
0x1002aa16  mov     eax, ___security_cookie
0x1002aa1b  xor     eax, esp
0x1002aa1d  mov     [esp+218h+var_4], eax
0x1002aa24  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1002aa2b  mov     eax, [esp+218h+lpFileName]
0x1002aa32  jz      short loc_1002AA52
0x1002aa34  push    eax; lpFileName
0x1002aa35  call    ds:__imp__DeleteFileW@4; DeleteFileW(x)
0x1002aa3b  mov     ecx, [esp+218h+var_4]
0x1002aa42  xor     ecx, esp; StackCookie
0x1002aa44  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002aa49  add     esp, 218h
0x1002aa4f  retn    4
0x1002aa52  push    esi
0x1002aa53  push    0FFFFFFFFh; int
0x1002aa55  push    eax; lpWideCharStr
0x1002aa56  lea     ecx, [esp+224h+var_218]; this
0x1002aa5a  mov     [esp+224h+var_218], 0
0x1002aa62  mov     [esp+224h+var_214], 0
0x1002aa6a  call    ?Init@CStrIn@@IAEXPB_WH@Z; CStrIn::Init(wchar_t const *,int)
0x1002aa6f  push    [esp+21Ch+var_214]; lpFileName
0x1002aa73  call    ds:__imp__DeleteFileA@4; DeleteFileA(x)
0x1002aa79  mov     esi, eax
0x1002aa7b  lea     ecx, [esp+21Ch+var_210]
0x1002aa7f  mov     eax, [esp+21Ch+var_214]
0x1002aa83  cmp     eax, ecx
0x1002aa85  jz      short loc_1002AAA0
0x1002aa87  mov     ecx, eax
0x1002aa89  shr     ecx, 10h
0x1002aa8c  test    ecx, ecx
0x1002aa8e  jz      short loc_1002AAA0
0x1002aa90  cmp     [esp+21Ch+var_218], 0FFFFFFFFh
0x1002aa95  jz      short loc_1002AAA0
0x1002aa97  push    eax; Block
0x1002aa98  call    _free
0x1002aa9d  add     esp, 4
0x1002aaa0  mov     ecx, [esp+21Ch+var_4]
0x1002aaa7  mov     eax, esi
0x1002aaa9  pop     esi
0x1002aaaa  xor     ecx, esp; StackCookie
0x1002aaac  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002aab1  add     esp, 218h
0x1002aab7  retn    4
```
