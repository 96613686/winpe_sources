# JetRemoveDirectoryW(x)

- ea: `0x1002b360`
- end: `0x1002b426`
- name: `_JetRemoveDirectoryW@4`
- size: `198`
- prototype: `int __stdcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1000ba60`

## callees

- `0x1002a5c0`
- `0x1002b360`
- `0x1002b81a`
- `0x1002df32`

## import_xrefs

- `KERNEL32!RemoveDirectoryA` at `0x1002b3df`
- `KERNEL32!RemoveDirectoryA` at `0x1002b3df`
- `KERNEL32!RemoveDirectoryW` at `0x1002b385`
- `KERNEL32!RemoveDirectoryW` at `0x1002b385`
- `KERNEL32!SetLastError` at `0x1002b3d1`
- `KERNEL32!SetLastError` at `0x1002b3d1`

## pseudocode

```c
BOOL __stdcall JetRemoveDirectoryW(LPCWSTR lpPathName)
{
  BOOL v2; // esi
  int v3; // [esp+0h] [ebp-218h] BYREF
  LPCSTR v4; // [esp+4h] [ebp-214h]
  char v5; // [esp+8h] [ebp-210h] BYREF
  int v6; // [esp+210h] [ebp-8h]

  if ( wrap )
    return RemoveDirectoryW(lpPathName);
  v3 = 0;
  v4 = 0;
  CStrIn::Init((CStrIn *)&v3, lpPathName, -1);
  if ( v6 < 260 )
  {
    v2 = RemoveDirectoryA(v4);
  }
  else
  {
    SetLastError(0xA1u);
    v2 = 0;
  }
  if ( v4 != &v5 && (unsigned int)v4 >> 16 && v3 != -1 )
    free((void *)v4);
  return v2;
}

```

## disassembly

```asm
0x1002b360  sub     esp, 218h
0x1002b366  mov     eax, ___security_cookie
0x1002b36b  xor     eax, esp
0x1002b36d  mov     [esp+218h+var_4], eax
0x1002b374  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1002b37b  mov     eax, [esp+218h+lpPathName]
0x1002b382  jz      short loc_1002B3A2
0x1002b384  push    eax; lpPathName
0x1002b385  call    ds:__imp__RemoveDirectoryW@4; RemoveDirectoryW(x)
0x1002b38b  mov     ecx, [esp+218h+var_4]
0x1002b392  xor     ecx, esp; StackCookie
0x1002b394  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002b399  add     esp, 218h
0x1002b39f  retn    4
0x1002b3a2  push    esi
0x1002b3a3  push    0FFFFFFFFh; int
0x1002b3a5  push    eax; lpWideCharStr
0x1002b3a6  lea     ecx, [esp+224h+var_218]; this
0x1002b3aa  mov     [esp+224h+var_218], 0
0x1002b3b2  mov     [esp+224h+var_214], 0
0x1002b3ba  call    ?Init@CStrIn@@IAEXPB_WH@Z; CStrIn::Init(wchar_t const *,int)
0x1002b3bf  cmp     [esp+21Ch+var_8], 104h
0x1002b3ca  jl      short loc_1002B3DB
0x1002b3cc  push    0A1h; dwErrCode
0x1002b3d1  call    ds:__imp__SetLastError@4; SetLastError(x)
0x1002b3d7  xor     esi, esi
0x1002b3d9  jmp     short loc_1002B3E7
0x1002b3db  push    [esp+21Ch+var_214]; lpPathName
0x1002b3df  call    ds:__imp__RemoveDirectoryA@4; RemoveDirectoryA(x)
0x1002b3e5  mov     esi, eax
0x1002b3e7  mov     edx, [esp+21Ch+var_214]
0x1002b3eb  lea     eax, [esp+21Ch+var_210]
0x1002b3ef  cmp     edx, eax
0x1002b3f1  jz      short loc_1002B40C
0x1002b3f3  mov     ecx, edx
0x1002b3f5  shr     ecx, 10h
0x1002b3f8  test    ecx, ecx
0x1002b3fa  jz      short loc_1002B40C
0x1002b3fc  cmp     [esp+21Ch+var_218], 0FFFFFFFFh
0x1002b401  jz      short loc_1002B40C
0x1002b403  push    edx; Block
0x1002b404  call    _free
0x1002b409  add     esp, 4
0x1002b40c  mov     ecx, [esp+21Ch+var_4]
0x1002b413  mov     eax, esi
0x1002b415  pop     esi
0x1002b416  xor     ecx, esp; StackCookie
0x1002b418  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002b41d  add     esp, 218h
0x1002b423  retn    4
```
