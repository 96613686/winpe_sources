# JetRegSetValueExW(x,x,x,x,x,x)

- ea: `0x10047820`
- end: `0x1004790d`
- name: `_JetRegSetValueExW@24`
- size: `237`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpValueName, DWORD Reserved, DWORD dwType, BYTE *lpData, DWORD cbData)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x10045b50`

## callees

- `0x10046833`
- `0x10046864`
- `0x10046899`
- `0x10047820`
- `0x10123110`
- `0x10124048`
- `0x10124129`
- `0x10124177`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1004788f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100478d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x1004788f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x100478d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x10047854`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x10047854`

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
0x10047820  push    430h
0x10047825  mov     eax, offset loc_10124DE9
0x1004782a  call    __EH_prolog3_GS
0x1004782f  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10047836  mov     eax, [ebp+lpData]
0x10047839  mov     ebx, [ebp+hKey]
0x1004783c  mov     ecx, [ebp+lpValueName]
0x1004783f  mov     edi, [ebp+cbData]
0x10047842  mov     [ebp+lpWideCharStr], eax
0x10047848  jz      short loc_1004785F
0x1004784a  push    edi; cbData
0x1004784b  push    eax; lpData
0x1004784c  push    [ebp+dwType]; dwType
0x1004784f  push    [ebp+Reserved]; Reserved
0x10047852  push    ecx; lpValueName
0x10047853  push    ebx; hKey
0x10047854  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x1004785a  jmp     loc_10047905
0x1004785f  push    ecx; unsigned __int16 *
0x10047860  lea     ecx, [ebp+var_438]; this
0x10047866  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x1004786b  mov     esi, [ebp+dwType]
0x1004786e  cmp     esi, 1
0x10047871  jz      short loc_10047899
0x10047873  cmp     esi, 2
0x10047876  jz      short loc_10047899
0x10047878  cmp     esi, 7
0x1004787b  jz      short loc_10047899
0x1004787d  push    edi; cbData
0x1004787e  push    [ebp+lpWideCharStr]; lpData
0x10047884  push    esi; dwType
0x10047885  push    [ebp+Reserved]; Reserved
0x10047888  push    [ebp+var_434]; lpValueName
0x1004788e  push    ebx; hKey
0x1004788f  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10047895  mov     esi, eax
0x10047897  jmp     short loc_100478F1
0x10047899  shr     edi, 1
0x1004789b  lea     ecx, [ebp+var_224]; this
0x100478a1  push    edi; int
0x100478a2  push    [ebp+lpWideCharStr]; lpWideCharStr
0x100478a8  mov     [ebp+var_224], 0
0x100478b2  mov     [ebp+var_220], 0
0x100478bc  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x100478c1  mov     eax, [ebp+var_14]
0x100478c4  inc     eax
0x100478c5  push    eax; cbData
0x100478c6  push    [ebp+var_220]; lpData
0x100478cc  push    esi; dwType
0x100478cd  push    [ebp+Reserved]; Reserved
0x100478d0  push    [ebp+var_434]; lpValueName
0x100478d6  push    ebx; hKey
0x100478d7  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x100478dd  mov     esi, eax
0x100478df  lea     ecx, [ebp+var_224]; this
0x100478e5  mov     [ebp+var_4], 0
0x100478ec  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x100478f1  lea     ecx, [ebp+var_438]; this
0x100478f7  mov     [ebp+var_4], 2
0x100478fe  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10047903  mov     eax, esi
0x10047905  call    __EH_epilog3_GS
0x1004790a  retn    18h
0x10124060  jmp     ds:__imp____std_terminate
0x10124de9  nop
0x10124dea  nop
0x10124deb  mov     edx, [esp-4+lpValueName]
0x10124def  lea     eax, [edx+0Ch]
0x10124df2  mov     ecx, [edx-440h]
0x10124df8  xor     ecx, eax; StackCookie
0x10124dfa  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124dff  mov     ecx, [edx-4]
0x10124e02  xor     ecx, eax; StackCookie
0x10124e04  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10124e09  mov     eax, offset stru_10127B08
0x10124e0e  jmp     ___CxxFrameHandler3
```
