# JetCreateDirectoryW(x,x)

- ea: `0x1003379f`
- end: `0x1003381d`
- name: `_JetCreateDirectoryW@8`
- size: `126`
- prototype: `int __stdcall(LPCWSTR lpPathName, LPSECURITY_ATTRIBUTES lpSecurityAttributes)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10022890`

## callees

- `0x10032925`
- `0x10032956`
- `0x1003379f`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x100337e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x100337e8`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x100337c6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x100337c6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x100337f9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryA` at `0x100337f9`

## pseudocode

```c
BOOL __stdcall JetCreateDirectoryW(LPCWSTR lpPathName, LPSECURITY_ATTRIBUTES lpSecurityAttributes)
{
  BOOL DirectoryA; // esi
  _BYTE v4[4]; // [esp+4h] [ebp-218h] BYREF
  LPCSTR v5; // [esp+8h] [ebp-214h]
  int v6; // [esp+214h] [ebp-8h]

  if ( wrap )
    return CreateDirectoryW(lpPathName, lpSecurityAttributes);
  CStrIn::CStrIn((CStrIn *)v4, lpPathName);
  if ( v6 < 260 )
  {
    DirectoryA = CreateDirectoryA(v5, lpSecurityAttributes);
  }
  else
  {
    SetLastError(0xA1u);
    DirectoryA = 0;
  }
  CConvertStr::Free((CConvertStr *)v4);
  return DirectoryA;
}

```

## disassembly

```asm
0x1003379f  mov     edi, edi
0x100337a1  push    ebp
0x100337a2  mov     ebp, esp
0x100337a4  sub     esp, 218h
0x100337aa  mov     eax, ___security_cookie
0x100337af  xor     eax, ebp
0x100337b1  mov     [ebp+var_4], eax
0x100337b4  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x100337bb  mov     eax, [ebp+lpPathName]
0x100337be  push    esi
0x100337bf  mov     esi, [ebp+lpSecurityAttributes]
0x100337c2  jz      short loc_100337CE
0x100337c4  push    esi; lpSecurityAttributes
0x100337c5  push    eax; lpPathName
0x100337c6  call    ds:__imp__CreateDirectoryW@8; CreateDirectoryW(x,x)
0x100337cc  jmp     short loc_1003380E
0x100337ce  push    eax; unsigned __int16 *
0x100337cf  lea     ecx, [ebp+var_218]; this
0x100337d5  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x100337da  cmp     [ebp+var_8], 104h
0x100337e1  jl      short loc_100337F2
0x100337e3  push    0A1h; dwErrCode
0x100337e8  call    ds:__imp__SetLastError@4; SetLastError(x)
0x100337ee  xor     esi, esi
0x100337f0  jmp     short loc_10033801
0x100337f2  push    esi; lpSecurityAttributes
0x100337f3  push    [ebp+var_214]; lpPathName
0x100337f9  call    ds:__imp__CreateDirectoryA@8; CreateDirectoryA(x,x)
0x100337ff  mov     esi, eax
0x10033801  lea     ecx, [ebp+var_218]; this
0x10033807  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x1003380c  mov     eax, esi
0x1003380e  mov     ecx, [ebp+var_4]
0x10033811  xor     ecx, ebp; StackCookie
0x10033813  pop     esi
0x10033814  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033819  leave
0x1003381a  retn    8
```
