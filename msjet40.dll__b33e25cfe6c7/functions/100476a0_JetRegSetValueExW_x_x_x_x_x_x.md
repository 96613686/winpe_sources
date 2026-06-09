# JetRegSetValueExW(x,x,x,x,x,x)

- ea: `0x100476a0`
- end: `0x1004778d`
- name: `_JetRegSetValueExW@24`
- size: `237`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpValueName, DWORD Reserved, DWORD dwType, BYTE *lpData, DWORD cbData)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x100459d0`

## callees

- `0x100466b3`
- `0x100466e4`
- `0x10046719`
- `0x100476a0`
- `0x10122f60`
- `0x10123e98`
- `0x10123f79`
- `0x10123fc7`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1004770f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10047757`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1004770f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10047757`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x100476d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x100476d4`

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
  _BYTE v8[4]; // [esp+14h] [ebp-438h] BYREF
  LPCSTR v9; // [esp+18h] [ebp-434h]
  int v10; // [esp+228h] [ebp-224h] BYREF
  BYTE *v11; // [esp+22Ch] [ebp-220h]
  int v12; // [esp+438h] [ebp-14h]
  int v13; // [esp+448h] [ebp-4h]

  if ( wrap )
    return RegSetValueExW(hKey, lpValueName, Reserved, dwType, lpData, cbData);
  CStrIn::CStrIn((CStrIn *)v8, lpValueName);
  if ( dwType == 1 || dwType == 2 || dwType == 7 )
  {
    v10 = 0;
    v11 = 0;
    CStrIn::Init((CStrIn *)&v10, (LPCWCH)lpData, cbData >> 1);
    v7 = RegSetValueExA(hKey, v9, Reserved, dwType, v11, v12 + 1);
    v13 = 0;
    CConvertStr::Free((CConvertStr *)&v10);
  }
  else
  {
    v7 = RegSetValueExA(hKey, v9, Reserved, dwType, lpData, cbData);
  }
  v13 = 2;
  CConvertStr::Free((CConvertStr *)v8);
  return v7;
}

```

## disassembly

```asm
0x100476a0  push    430h
0x100476a5  mov     eax, offset loc_10124C39
0x100476aa  call    __EH_prolog3_GS
0x100476af  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x100476b6  mov     eax, [ebp+lpData]
0x100476b9  mov     ebx, [ebp+hKey]
0x100476bc  mov     ecx, [ebp+lpValueName]
0x100476bf  mov     edi, [ebp+cbData]
0x100476c2  mov     [ebp+lpWideCharStr], eax
0x100476c8  jz      short loc_100476DF
0x100476ca  push    edi; cbData
0x100476cb  push    eax; lpData
0x100476cc  push    [ebp+dwType]; dwType
0x100476cf  push    [ebp+Reserved]; Reserved
0x100476d2  push    ecx; lpValueName
0x100476d3  push    ebx; hKey
0x100476d4  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x100476da  jmp     loc_10047785
0x100476df  push    ecx; unsigned __int16 *
0x100476e0  lea     ecx, [ebp+var_438]; this
0x100476e6  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x100476eb  mov     esi, [ebp+dwType]
0x100476ee  cmp     esi, 1
0x100476f1  jz      short loc_10047719
0x100476f3  cmp     esi, 2
0x100476f6  jz      short loc_10047719
0x100476f8  cmp     esi, 7
0x100476fb  jz      short loc_10047719
0x100476fd  push    edi; cbData
0x100476fe  push    [ebp+lpWideCharStr]; lpData
0x10047704  push    esi; dwType
0x10047705  push    [ebp+Reserved]; Reserved
0x10047708  push    [ebp+var_434]; lpValueName
0x1004770e  push    ebx; hKey
0x1004770f  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10047715  mov     esi, eax
0x10047717  jmp     short loc_10047771
0x10047719  shr     edi, 1
0x1004771b  lea     ecx, [ebp+var_224]; this
0x10047721  push    edi; int
0x10047722  push    [ebp+lpWideCharStr]; lpWideCharStr
0x10047728  mov     [ebp+var_224], 0
0x10047732  mov     [ebp+var_220], 0
0x1004773c  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x10047741  mov     eax, [ebp+var_14]
0x10047744  inc     eax
0x10047745  push    eax; cbData
0x10047746  push    [ebp+var_220]; lpData
0x1004774c  push    esi; dwType
0x1004774d  push    [ebp+Reserved]; Reserved
0x10047750  push    [ebp+var_434]; lpValueName
0x10047756  push    ebx; hKey
0x10047757  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x1004775d  mov     esi, eax
0x1004775f  lea     ecx, [ebp+var_224]; this
0x10047765  mov     [ebp+var_4], 0
0x1004776c  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10047771  lea     ecx, [ebp+var_438]; this
0x10047777  mov     [ebp+var_4], 2
0x1004777e  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10047783  mov     eax, esi
0x10047785  call    __EH_epilog3_GS
0x1004778a  retn    18h
0x10123eb0  jmp     ds:__imp____std_terminate
0x10124c39  nop
0x10124c3a  nop
0x10124c3b  mov     edx, [esp-4+lpValueName]
0x10124c3f  lea     eax, [edx+0Ch]
0x10124c42  mov     ecx, [edx-440h]
0x10124c48  xor     ecx, eax; StackCookie
0x10124c4a  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124c4f  mov     ecx, [edx-4]
0x10124c52  xor     ecx, eax; StackCookie
0x10124c54  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124c59  mov     eax, offset stru_10127958
0x10124c5e  jmp     ___CxxFrameHandler3
```
