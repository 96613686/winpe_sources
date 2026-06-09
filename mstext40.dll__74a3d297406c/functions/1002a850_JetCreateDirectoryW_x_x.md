# JetCreateDirectoryW(x,x)

- ea: `0x1002a850`
- end: `0x1002a920`
- name: `_JetCreateDirectoryW@8`
- size: `208`
- prototype: `int __stdcall(LPCWSTR lpPathName, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1000b980`

## callees

- `0x1002a5c0`
- `0x1002a850`
- `0x1002b81a`
- `0x1002df32`

## import_xrefs

- `KERNEL32!CreateDirectoryA` at `0x1002a8d9`
- `KERNEL32!CreateDirectoryA` at `0x1002a8d9`
- `KERNEL32!CreateDirectoryW` at `0x1002a87e`
- `KERNEL32!CreateDirectoryW` at `0x1002a87e`
- `KERNEL32!SetLastError` at `0x1002a8ca`
- `KERNEL32!SetLastError` at `0x1002a8ca`

## pseudocode

```c
BOOL __stdcall JetCreateDirectoryW(LPCWSTR lpPathName, LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  BOOL DirectoryA; // esi
  int v4; // [esp+4h] [ebp-218h] BYREF
  LPCSTR v5; // [esp+8h] [ebp-214h]
  char v6; // [esp+Ch] [ebp-210h] BYREF
  int v7; // [esp+214h] [ebp-8h]

  if ( wrap )
    return CreateDirectoryW(lpPathName, lpSecurityAttributes);
  v4 = 0;
  v5 = 0;
  CStrIn::Init((CStrIn *)&v4, lpPathName, -1);
  if ( v7 < 260 )
  {
    DirectoryA = CreateDirectoryA(v5, lpSecurityAttributes);
  }
  else
  {
    SetLastError(0xA1u);
    DirectoryA = 0;
  }
  if ( v5 != &v6 && (unsigned int)v5 >> 16 && v4 != -1 )
    free((void *)v5);
  return DirectoryA;
}

```

## disassembly

```asm
0x1002a850  sub     esp, 218h
0x1002a856  mov     eax, ___security_cookie
0x1002a85b  xor     eax, esp
0x1002a85d  mov     [esp+218h+var_4], eax
0x1002a864  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1002a86b  mov     eax, [esp+218h+lpPathName]
0x1002a872  push    esi
0x1002a873  mov     esi, [esp+21Ch+lpSecurityAttributes]
0x1002a87a  jz      short loc_1002A89C
0x1002a87c  push    esi; lpSecurityAttributes
0x1002a87d  push    eax; lpPathName
0x1002a87e  call    ds:__imp__CreateDirectoryW@8; CreateDirectoryW(x,x)
0x1002a884  pop     esi
0x1002a885  mov     ecx, [esp+218h+var_4]
0x1002a88c  xor     ecx, esp; StackCookie
0x1002a88e  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002a893  add     esp, 218h
0x1002a899  retn    8
0x1002a89c  push    0FFFFFFFFh; int
0x1002a89e  push    eax; lpWideCharStr
0x1002a89f  lea     ecx, [esp+224h+var_218]; this
0x1002a8a3  mov     [esp+224h+var_218], 0
0x1002a8ab  mov     [esp+224h+var_214], 0
0x1002a8b3  call    ?Init@CStrIn@@IAEXPB_WH@Z; CStrIn::Init(wchar_t const *,int)
0x1002a8b8  cmp     [esp+21Ch+var_8], 104h
0x1002a8c3  jl      short loc_1002A8D4
0x1002a8c5  push    0A1h; dwErrCode
0x1002a8ca  call    ds:__imp__SetLastError@4; SetLastError(x)
0x1002a8d0  xor     esi, esi
0x1002a8d2  jmp     short loc_1002A8E1
0x1002a8d4  push    esi; lpSecurityAttributes
0x1002a8d5  push    [esp+220h+var_214]; lpPathName
0x1002a8d9  call    ds:__imp__CreateDirectoryA@8; CreateDirectoryA(x,x)
0x1002a8df  mov     esi, eax
0x1002a8e1  mov     edx, [esp+21Ch+var_214]
0x1002a8e5  lea     eax, [esp+21Ch+var_210]
0x1002a8e9  cmp     edx, eax
0x1002a8eb  jz      short loc_1002A906
0x1002a8ed  mov     ecx, edx
0x1002a8ef  shr     ecx, 10h
0x1002a8f2  test    ecx, ecx
0x1002a8f4  jz      short loc_1002A906
0x1002a8f6  cmp     [esp+21Ch+var_218], 0FFFFFFFFh
0x1002a8fb  jz      short loc_1002A906
0x1002a8fd  push    edx; Block
0x1002a8fe  call    _free
0x1002a903  add     esp, 4
0x1002a906  mov     ecx, [esp+21Ch+var_4]
0x1002a90d  mov     eax, esi
0x1002a90f  pop     esi
0x1002a910  xor     ecx, esp; StackCookie
0x1002a912  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002a917  add     esp, 218h
0x1002a91d  retn    8
```
