# JetSetCurrentDirectoryW(x)

- ea: `0x1002b430`
- end: `0x1002b4f6`
- name: `_JetSetCurrentDirectoryW@4`
- size: `198`
- prototype: `int __stdcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1000b860`

## callees

- `0x1002a5c0`
- `0x1002b430`
- `0x1002b81a`
- `0x1002df32`

## import_xrefs

- `KERNEL32!SetCurrentDirectoryA` at `0x1002b4af`
- `KERNEL32!SetCurrentDirectoryA` at `0x1002b4af`
- `KERNEL32!SetCurrentDirectoryW` at `0x1002b455`
- `KERNEL32!SetCurrentDirectoryW` at `0x1002b455`
- `KERNEL32!SetLastError` at `0x1002b4a1`
- `KERNEL32!SetLastError` at `0x1002b4a1`

## pseudocode

```c
BOOL __stdcall JetSetCurrentDirectoryW(LPCWSTR lpPathName)
{
  BOOL v2; // esi
  int v3; // [esp+0h] [ebp-218h] BYREF
  LPCSTR v4; // [esp+4h] [ebp-214h]
  char v5; // [esp+8h] [ebp-210h] BYREF
  int v6; // [esp+210h] [ebp-8h]

  if ( wrap )
    return SetCurrentDirectoryW(lpPathName);
  v3 = 0;
  v4 = 0;
  CStrIn::Init((CStrIn *)&v3, lpPathName, -1);
  if ( v6 < 260 )
  {
    v2 = SetCurrentDirectoryA(v4);
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
0x1002b430  sub     esp, 218h
0x1002b436  mov     eax, ___security_cookie
0x1002b43b  xor     eax, esp
0x1002b43d  mov     [esp+218h+var_4], eax
0x1002b444  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1002b44b  mov     eax, [esp+218h+lpPathName]
0x1002b452  jz      short loc_1002B472
0x1002b454  push    eax; lpPathName
0x1002b455  call    ds:__imp__SetCurrentDirectoryW@4; SetCurrentDirectoryW(x)
0x1002b45b  mov     ecx, [esp+218h+var_4]
0x1002b462  xor     ecx, esp; StackCookie
0x1002b464  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002b469  add     esp, 218h
0x1002b46f  retn    4
0x1002b472  push    esi
0x1002b473  push    0FFFFFFFFh; int
0x1002b475  push    eax; lpWideCharStr
0x1002b476  lea     ecx, [esp+224h+var_218]; this
0x1002b47a  mov     [esp+224h+var_218], 0
0x1002b482  mov     [esp+224h+var_214], 0
0x1002b48a  call    ?Init@CStrIn@@IAEXPB_WH@Z; CStrIn::Init(wchar_t const *,int)
0x1002b48f  cmp     [esp+21Ch+var_8], 104h
0x1002b49a  jl      short loc_1002B4AB
0x1002b49c  push    0A1h; dwErrCode
0x1002b4a1  call    ds:__imp__SetLastError@4; SetLastError(x)
0x1002b4a7  xor     esi, esi
0x1002b4a9  jmp     short loc_1002B4B7
0x1002b4ab  push    [esp+21Ch+var_214]; lpPathName
0x1002b4af  call    ds:__imp__SetCurrentDirectoryA@4; SetCurrentDirectoryA(x)
0x1002b4b5  mov     esi, eax
0x1002b4b7  mov     edx, [esp+21Ch+var_214]
0x1002b4bb  lea     eax, [esp+21Ch+var_210]
0x1002b4bf  cmp     edx, eax
0x1002b4c1  jz      short loc_1002B4DC
0x1002b4c3  mov     ecx, edx
0x1002b4c5  shr     ecx, 10h
0x1002b4c8  test    ecx, ecx
0x1002b4ca  jz      short loc_1002B4DC
0x1002b4cc  cmp     [esp+21Ch+var_218], 0FFFFFFFFh
0x1002b4d1  jz      short loc_1002B4DC
0x1002b4d3  push    edx; Block
0x1002b4d4  call    _free
0x1002b4d9  add     esp, 4
0x1002b4dc  mov     ecx, [esp+21Ch+var_4]
0x1002b4e3  mov     eax, esi
0x1002b4e5  pop     esi
0x1002b4e6  xor     ecx, esp; StackCookie
0x1002b4e8  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002b4ed  add     esp, 218h
0x1002b4f3  retn    4
```
