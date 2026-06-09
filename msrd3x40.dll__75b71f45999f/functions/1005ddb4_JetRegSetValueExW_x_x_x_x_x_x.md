# JetRegSetValueExW(x,x,x,x,x,x)

- ea: `0x1005ddb4`
- end: `0x1005dea5`
- name: `_JetRegSetValueExW@24`
- size: `241`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpValueName, DWORD Reserved, DWORD dwType, BYTE *lpData, DWORD cbData)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x10038080`

## callees

- `0x1005d64e`
- `0x1005d67f`
- `0x1005d6b4`
- `0x1005ddb4`
- `0x1005e3b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1005ddf0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1005ddf0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1005de2c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1005de74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1005de2c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1005de74`

## pseudocode

```c
LSTATUS __stdcall JetRegSetValueExW(
        HKEY hKey,
        LPCWSTR lpValueName,
        DWORD Reserved,
        DWORD dwType,
        BYTE *lpData,
        DWORD cbData)
{
  LSTATUS v7; // esi
  _BYTE v8[4]; // [esp+Ch] [ebp-42Ch] BYREF
  LPCSTR v9; // [esp+10h] [ebp-428h]
  int v10; // [esp+220h] [ebp-218h] BYREF
  BYTE *v11; // [esp+224h] [ebp-214h]
  int v12; // [esp+430h] [ebp-8h]

  if ( wrap )
    return RegSetValueExW(hKey, lpValueName, Reserved, dwType, lpData, cbData);
  CStrIn::CStrIn((CStrIn *)v8, lpValueName);
  if ( dwType == 1 || dwType == 2 || dwType == 7 )
  {
    v10 = 0;
    v11 = 0;
    CStrIn::Init((CStrIn *)&v10, (LPCWCH)lpData, cbData >> 1);
    v7 = RegSetValueExA(hKey, v9, Reserved, dwType, v11, v12 + 1);
    CConvertStr::Free((CConvertStr *)&v10);
  }
  else
  {
    v7 = RegSetValueExA(hKey, v9, Reserved, dwType, lpData, cbData);
  }
  CConvertStr::Free((CConvertStr *)v8);
  return v7;
}

```

## disassembly

```asm
0x1005ddb4  mov     edi, edi
0x1005ddb6  push    ebp
0x1005ddb7  mov     ebp, esp
0x1005ddb9  sub     esp, 430h
0x1005ddbf  mov     eax, ___security_cookie
0x1005ddc4  xor     eax, ebp
0x1005ddc6  mov     [ebp+var_4], eax
0x1005ddc9  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1005ddd0  mov     eax, [ebp+lpData]
0x1005ddd3  mov     ecx, [ebp+lpValueName]
0x1005ddd6  push    ebx
0x1005ddd7  mov     ebx, [ebp+hKey]
0x1005ddda  push    edi
0x1005dddb  mov     edi, [ebp+cbData]
0x1005ddde  mov     [ebp+lpWideCharStr], eax
0x1005dde4  jz      short loc_1005DDFB
0x1005dde6  push    edi; cbData
0x1005dde7  push    eax; lpData
0x1005dde8  push    [ebp+dwType]; dwType
0x1005ddeb  push    [ebp+Reserved]; Reserved
0x1005ddee  push    ecx; lpValueName
0x1005ddef  push    ebx; hKey
0x1005ddf0  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x1005ddf6  jmp     loc_1005DE95
0x1005ddfb  push    esi
0x1005ddfc  push    ecx; unsigned __int16 *
0x1005ddfd  lea     ecx, [ebp+var_42C]; this
0x1005de03  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x1005de08  mov     esi, [ebp+dwType]
0x1005de0b  cmp     esi, 1
0x1005de0e  jz      short loc_1005DE36
0x1005de10  cmp     esi, 2
0x1005de13  jz      short loc_1005DE36
0x1005de15  cmp     esi, 7
0x1005de18  jz      short loc_1005DE36
0x1005de1a  push    edi; cbData
0x1005de1b  push    [ebp+lpWideCharStr]; lpData
0x1005de21  push    esi; dwType
0x1005de22  push    [ebp+Reserved]; Reserved
0x1005de25  push    [ebp+var_428]; lpValueName
0x1005de2b  push    ebx; hKey
0x1005de2c  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x1005de32  mov     esi, eax
0x1005de34  jmp     short loc_1005DE87
0x1005de36  shr     edi, 1
0x1005de38  lea     ecx, [ebp+var_218]; this
0x1005de3e  push    edi; int
0x1005de3f  push    [ebp+lpWideCharStr]; lpWideCharStr
0x1005de45  mov     [ebp+var_218], 0
0x1005de4f  mov     [ebp+var_214], 0
0x1005de59  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x1005de5e  mov     eax, [ebp+var_8]
0x1005de61  inc     eax
0x1005de62  push    eax; cbData
0x1005de63  push    [ebp+var_214]; lpData
0x1005de69  push    esi; dwType
0x1005de6a  push    [ebp+Reserved]; Reserved
0x1005de6d  push    [ebp+var_428]; lpValueName
0x1005de73  push    ebx; hKey
0x1005de74  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x1005de7a  lea     ecx, [ebp+var_218]; this
0x1005de80  mov     esi, eax
0x1005de82  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1005de87  lea     ecx, [ebp+var_42C]; this
0x1005de8d  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1005de92  mov     eax, esi
0x1005de94  pop     esi
0x1005de95  mov     ecx, [ebp+var_4]
0x1005de98  pop     edi
0x1005de99  xor     ecx, ebp; StackCookie
0x1005de9b  pop     ebx
0x1005de9c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005dea1  leave
0x1005dea2  retn    18h
```
