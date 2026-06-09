# CFontManager::_CheckIfFlagSetInReg(ushort const *)

- ea: `0x18001d9c4`
- end: `0x18001da63`
- name: `?_CheckIfFlagSetInReg@CFontManager@@AEAAHPEBG@Z`
- size: `159`
- prototype: `__int64 __fastcall(CFontManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e168`

## callees

- `0x18001d9c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001da53`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001da53`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001da39`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001da39`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d9fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d9fe`

## string_xrefs

- `0x18001da28`: `SkipDeleteSystemFontWarning`

## pseudocode

```c
_BOOL8 __fastcall CFontManager::_CheckIfFlagSetInReg(CFontManager *this, const unsigned __int16 *a2)
{
  BOOL v2; // ebx
  CFontManager *Data; // [rsp+50h] [rbp+20h] BYREF
  const unsigned __int16 *Type; // [rsp+58h] [rbp+28h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF

  Type = a2;
  Data = this;
  v2 = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Font Management",
          0,
          1u,
          &hKey) )
  {
    LODWORD(Data) = 0;
    cbData = 4;
    LODWORD(Type) = 0;
    if ( !RegQueryValueExW(hKey, L"SkipDeleteSystemFontWarning", 0, (LPDWORD)&Type, (LPBYTE)&Data, &cbData)
      && (_DWORD)Type == 4 )
    {
      v2 = (_DWORD)Data == 1;
    }
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x18001d9c4  mov     [rsp-18h+Type], rdx
0x18001d9c9  mov     [rsp-18h+Data], rcx
0x18001d9ce  push    rbp
0x18001d9cf  push    rbx
0x18001d9d0  push    rdi
0x18001d9d1  mov     rbp, rsp
0x18001d9d4  sub     rsp, 30h
0x18001d9d8  xor     ebx, ebx
0x18001d9da  lea     rax, [rbp+hKey]
0x18001d9de  xor     r8d, r8d; ulOptions
0x18001d9e1  mov     [rbp+hKey], rbx
0x18001d9e5  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001d9ec  mov     [rsp+30h+phkResult], rax; phkResult
0x18001d9f1  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18001d9f8  lea     edi, [rbx+1]
0x18001d9fb  mov     r9d, edi; samDesired
0x18001d9fe  call    cs:__imp_RegOpenKeyExW
0x18001da04  test    eax, eax
0x18001da06  jnz     short loc_18001DA59
0x18001da08  mov     rcx, [rbp+hKey]; hKey
0x18001da0c  lea     rax, [rbp+cbData]
0x18001da10  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18001da15  lea     r9, [rbp+Type]; lpType
0x18001da19  lea     rax, [rbp+Data]
0x18001da1d  mov     dword ptr [rbp+Data], ebx
0x18001da20  xor     r8d, r8d; lpReserved
0x18001da23  mov     [rsp+30h+phkResult], rax; lpData
0x18001da28  lea     rdx, aSkipdeletesyst; "SkipDeleteSystemFontWarning"
0x18001da2f  mov     [rbp+cbData], 4
0x18001da36  mov     dword ptr [rbp+Type], ebx
0x18001da39  call    cs:__imp_RegQueryValueExW
0x18001da3f  test    eax, eax
0x18001da41  jnz     short loc_18001DA4F
0x18001da43  cmp     dword ptr [rbp+Type], 4
0x18001da47  jnz     short loc_18001DA4F
0x18001da49  cmp     dword ptr [rbp+Data], edi
0x18001da4c  cmovz   ebx, edi
0x18001da4f  mov     rcx, [rbp+hKey]; hKey
0x18001da53  call    cs:__imp_RegCloseKey
0x18001da59  mov     eax, ebx
0x18001da5b  add     rsp, 30h
0x18001da5f  pop     rdi
0x18001da60  pop     rbx
0x18001da61  pop     rbp
0x18001da62  retn
```
