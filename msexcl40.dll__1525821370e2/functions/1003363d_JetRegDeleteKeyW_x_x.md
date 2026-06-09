# JetRegDeleteKeyW(x,x)

- ea: `0x1003363d`
- end: `0x100336a2`
- name: `_JetRegDeleteKeyW@8`
- size: `101`
- prototype: `int __stdcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x100252b0`

## callees

- `0x10032925`
- `0x10032956`
- `0x1003363d`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x1003367e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyA` at `0x1003367e`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x10033664`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x10033664`

## pseudocode

```c
LSTATUS __stdcall JetRegDeleteKeyW(HKEY hKey, LPCWSTR lpSubKey)
{
  LSTATUS v3; // esi
  _BYTE v4[4]; // [esp+4h] [ebp-218h] BYREF
  LPCSTR v5; // [esp+8h] [ebp-214h]

  if ( wrap )
    return RegDeleteKeyW(hKey, lpSubKey);
  CStrIn::CStrIn((CStrIn *)v4, lpSubKey);
  v3 = RegDeleteKeyA(hKey, v5);
  CConvertStr::Free((CConvertStr *)v4);
  return v3;
}

```

## disassembly

```asm
0x1003363d  mov     edi, edi
0x1003363f  push    ebp
0x10033640  mov     ebp, esp
0x10033642  sub     esp, 218h
0x10033648  mov     eax, ___security_cookie
0x1003364d  xor     eax, ebp
0x1003364f  mov     [ebp+var_4], eax
0x10033652  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x10033659  mov     eax, [ebp+lpSubKey]
0x1003365c  push    esi
0x1003365d  mov     esi, [ebp+hKey]
0x10033660  push    eax; unsigned __int16 *
0x10033661  jz      short loc_1003366C
0x10033663  push    esi; hKey
0x10033664  call    ds:__imp__RegDeleteKeyW@8; RegDeleteKeyW(x,x)
0x1003366a  jmp     short loc_10033693
0x1003366c  lea     ecx, [ebp+var_218]; this
0x10033672  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10033677  push    [ebp+var_214]; lpSubKey
0x1003367d  push    esi; hKey
0x1003367e  call    ds:__imp__RegDeleteKeyA@8; RegDeleteKeyA(x,x)
0x10033684  lea     ecx, [ebp+var_218]; this
0x1003368a  mov     esi, eax
0x1003368c  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10033691  mov     eax, esi
0x10033693  mov     ecx, [ebp+var_4]
0x10033696  xor     ecx, ebp; StackCookie
0x10033698  pop     esi
0x10033699  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1003369e  leave
0x1003369f  retn    8
```
