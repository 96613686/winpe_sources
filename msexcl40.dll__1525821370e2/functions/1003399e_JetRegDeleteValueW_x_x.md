# JetRegDeleteValueW(x,x)

- ea: `0x1003399e`
- end: `0x10033a03`
- name: `_JetRegDeleteValueW@8`
- size: `101`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpValueName)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x100252b0`

## callees

- `0x10032925`
- `0x10032956`
- `0x1003399e`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x100339c5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x100339c5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x100339df`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueA` at `0x100339df`

## pseudocode

```c
LSTATUS __stdcall JetRegDeleteValueW(HKEY hKey, LPCWSTR lpValueName)
{
  LSTATUS v3; // esi
  _BYTE v4[4]; // [esp+4h] [ebp-218h] BYREF
  LPCSTR v5; // [esp+8h] [ebp-214h]

  if ( wrap )
    return RegDeleteValueW(hKey, lpValueName);
  CStrIn::CStrIn((CStrIn *)v4, lpValueName);
  v3 = RegDeleteValueA(hKey, v5);
  CConvertStr::Free((CConvertStr *)v4);
  return v3;
}

```

## disassembly

```asm
0x1003399e  mov     edi, edi
0x100339a0  push    ebp
0x100339a1  mov     ebp, esp
0x100339a3  sub     esp, 218h
0x100339a9  mov     eax, ___security_cookie
0x100339ae  xor     eax, ebp
0x100339b0  mov     [ebp+var_4], eax
0x100339b3  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x100339ba  mov     eax, [ebp+lpValueName]
0x100339bd  push    esi
0x100339be  mov     esi, [ebp+hKey]
0x100339c1  push    eax; unsigned __int16 *
0x100339c2  jz      short loc_100339CD
0x100339c4  push    esi; hKey
0x100339c5  call    ds:__imp__RegDeleteValueW@8; RegDeleteValueW(x,x)
0x100339cb  jmp     short loc_100339F4
0x100339cd  lea     ecx, [ebp+var_218]; this
0x100339d3  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x100339d8  push    [ebp+var_214]; lpValueName
0x100339de  push    esi; hKey
0x100339df  call    ds:__imp__RegDeleteValueA@8; RegDeleteValueA(x,x)
0x100339e5  lea     ecx, [ebp+var_218]; this
0x100339eb  mov     esi, eax
0x100339ed  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x100339f2  mov     eax, esi
0x100339f4  mov     ecx, [ebp+var_4]
0x100339f7  xor     ecx, ebp; StackCookie
0x100339f9  pop     esi
0x100339fa  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100339ff  leave
0x10033a00  retn    8
```
