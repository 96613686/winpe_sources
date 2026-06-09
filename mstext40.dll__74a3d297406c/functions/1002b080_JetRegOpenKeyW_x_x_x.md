# JetRegOpenKeyW(x,x,x)

- ea: `0x1002b080`
- end: `0x1002b137`
- name: `_JetRegOpenKeyW@12`
- size: `183`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1000aa30`
- `0x100148d0`

## callees

- `0x1002a5c0`
- `0x1002b080`
- `0x1002b81a`
- `0x1002df32`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x1002b0ef`
- `ADVAPI32!RegOpenKeyExA` at `0x1002b0ef`
- `ADVAPI32!RegOpenKeyExW` at `0x1002b0be`
- `ADVAPI32!RegOpenKeyExW` at `0x1002b0be`

## pseudocode

```c
LSTATUS __stdcall JetRegOpenKeyW(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult)
{
  LSTATUS v4; // esi
  int v5; // [esp+8h] [ebp-218h] BYREF
  LPCSTR v6; // [esp+Ch] [ebp-214h]
  char v7; // [esp+10h] [ebp-210h] BYREF

  if ( wrap )
    return RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, phkResult);
  v5 = 0;
  v6 = 0;
  CStrIn::Init((CStrIn *)&v5, lpSubKey, -1);
  v4 = RegOpenKeyExA(hKey, v6, 0, 0x20019u, phkResult);
  if ( v6 != &v7 && (unsigned int)v6 >> 16 && v5 != -1 )
    free((void *)v6);
  return v4;
}

```

## disassembly

```asm
0x1002b080  sub     esp, 218h
0x1002b086  mov     eax, ___security_cookie
0x1002b08b  xor     eax, esp
0x1002b08d  mov     [esp+218h+var_4], eax
0x1002b094  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1002b09b  mov     eax, [esp+218h+lpSubKey]
0x1002b0a2  push    esi
0x1002b0a3  mov     esi, [esp+21Ch+hKey]
0x1002b0aa  push    edi
0x1002b0ab  mov     edi, [esp+220h+phkResult]
0x1002b0b2  jz      short loc_1002B0C6
0x1002b0b4  push    edi; phkResult
0x1002b0b5  push    20019h; samDesired
0x1002b0ba  push    0; ulOptions
0x1002b0bc  push    eax; lpSubKey
0x1002b0bd  push    esi; hKey
0x1002b0be  call    ds:__imp__RegOpenKeyExW@20; RegOpenKeyExW(x,x,x,x,x)
0x1002b0c4  jmp     short loc_1002B11E
0x1002b0c6  push    0FFFFFFFFh; int
0x1002b0c8  push    eax; lpWideCharStr
0x1002b0c9  lea     ecx, [esp+228h+var_218]; this
0x1002b0cd  mov     [esp+228h+var_218], 0
0x1002b0d5  mov     [esp+228h+var_214], 0
0x1002b0dd  call    ?Init@CStrIn@@IAEXPB_WH@Z; CStrIn::Init(wchar_t const *,int)
0x1002b0e2  push    edi; phkResult
0x1002b0e3  push    20019h; samDesired
0x1002b0e8  push    0; ulOptions
0x1002b0ea  push    [esp+22Ch+var_214]; lpSubKey
0x1002b0ee  push    esi; hKey
0x1002b0ef  call    ds:__imp__RegOpenKeyExA@20; RegOpenKeyExA(x,x,x,x,x)
0x1002b0f5  mov     edx, [esp+220h+var_214]
0x1002b0f9  mov     esi, eax
0x1002b0fb  lea     eax, [esp+220h+var_210]
0x1002b0ff  cmp     edx, eax
0x1002b101  jz      short loc_1002B11C
0x1002b103  mov     ecx, edx
0x1002b105  shr     ecx, 10h
0x1002b108  test    ecx, ecx
0x1002b10a  jz      short loc_1002B11C
0x1002b10c  cmp     [esp+220h+var_218], 0FFFFFFFFh
0x1002b111  jz      short loc_1002B11C
0x1002b113  push    edx; Block
0x1002b114  call    _free
0x1002b119  add     esp, 4
0x1002b11c  mov     eax, esi
0x1002b11e  mov     ecx, [esp+220h+var_4]
0x1002b125  pop     edi
0x1002b126  pop     esi
0x1002b127  xor     ecx, esp; StackCookie
0x1002b129  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1002b12e  add     esp, 218h
0x1002b134  retn    0Ch
```
