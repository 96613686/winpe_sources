# JetRegSetValueExW(x,x,x,x,x,x)

- ea: `0x100336a8`
- end: `0x10033799`
- name: `_JetRegSetValueExW@24`
- size: `241`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpValueName, DWORD Reserved, DWORD dwType, BYTE *lpData, DWORD cbData)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x10024ca0`
- `0x10024cc9`
- `0x10024d06`
- `0x10024d8e`

## callees

- `0x10032925`
- `0x10032956`
- `0x1003298b`
- `0x100336a8`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x100336e4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x100336e4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10033720`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10033768`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10033720`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x10033768`

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
0x100336a8  mov     edi, edi
0x100336aa  push    ebp
0x100336ab  mov     ebp, esp
0x100336ad  sub     esp, 430h
0x100336b3  mov     eax, ___security_cookie
0x100336b8  xor     eax, ebp
0x100336ba  mov     [ebp+var_4], eax
0x100336bd  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x100336c4  mov     eax, [ebp+lpData]
0x100336c7  mov     ecx, [ebp+lpValueName]
0x100336ca  push    ebx
0x100336cb  mov     ebx, [ebp+hKey]
0x100336ce  push    edi
0x100336cf  mov     edi, [ebp+cbData]
0x100336d2  mov     [ebp+lpWideCharStr], eax
0x100336d8  jz      short loc_100336EF
0x100336da  push    edi; cbData
0x100336db  push    eax; lpData
0x100336dc  push    [ebp+dwType]; dwType
0x100336df  push    [ebp+Reserved]; Reserved
0x100336e2  push    ecx; lpValueName
0x100336e3  push    ebx; hKey
0x100336e4  call    ds:__imp__RegSetValueExW@24; RegSetValueExW(x,x,x,x,x,x)
0x100336ea  jmp     loc_10033789
0x100336ef  push    esi
0x100336f0  push    ecx; unsigned __int16 *
0x100336f1  lea     ecx, [ebp+var_42C]; this
0x100336f7  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x100336fc  mov     esi, [ebp+dwType]
0x100336ff  cmp     esi, 1
0x10033702  jz      short loc_1003372A
0x10033704  cmp     esi, 2
0x10033707  jz      short loc_1003372A
0x10033709  cmp     esi, 7
0x1003370c  jz      short loc_1003372A
0x1003370e  push    edi; cbData
0x1003370f  push    [ebp+lpWideCharStr]; lpData
0x10033715  push    esi; dwType
0x10033716  push    [ebp+Reserved]; Reserved
0x10033719  push    [ebp+var_428]; lpValueName
0x1003371f  push    ebx; hKey
0x10033720  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x10033726  mov     esi, eax
0x10033728  jmp     short loc_1003377B
0x1003372a  shr     edi, 1
0x1003372c  lea     ecx, [ebp+var_218]; this
0x10033732  push    edi; int
0x10033733  push    [ebp+lpWideCharStr]; lpWideCharStr
0x10033739  mov     [ebp+var_218], 0
0x10033743  mov     [ebp+var_214], 0
0x1003374d  call    ?Init@CStrIn@@IAEXPBGH@Z; CStrIn::Init(ushort const *,int)
0x10033752  mov     eax, [ebp+var_8]
0x10033755  inc     eax
0x10033756  push    eax; cbData
0x10033757  push    [ebp+var_214]; lpData
0x1003375d  push    esi; dwType
0x1003375e  push    [ebp+Reserved]; Reserved
0x10033761  push    [ebp+var_428]; lpValueName
0x10033767  push    ebx; hKey
0x10033768  call    ds:__imp__RegSetValueExA@24; RegSetValueExA(x,x,x,x,x,x)
0x1003376e  lea     ecx, [ebp+var_218]; this
0x10033774  mov     esi, eax
0x10033776  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1003377b  lea     ecx, [ebp+var_42C]; this
0x10033781  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10033786  mov     eax, esi
0x10033788  pop     esi
0x10033789  mov     ecx, [ebp+var_4]
0x1003378c  pop     edi
0x1003378d  xor     ecx, ebp; StackCookie
0x1003378f  pop     ebx
0x10033790  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033795  leave
0x10033796  retn    18h
```
