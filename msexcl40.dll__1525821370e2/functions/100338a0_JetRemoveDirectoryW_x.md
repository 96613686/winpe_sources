# JetRemoveDirectoryW(x)

- ea: `0x100338a0`
- end: `0x10033919`
- name: `_JetRemoveDirectoryW@4`
- size: `121`
- prototype: `int __stdcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x100278d3`

## callees

- `0x10032925`
- `0x10032956`
- `0x100338a0`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x100338e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x100338e5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x100338c2`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x100338c2`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x100338f5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x100338f5`

## pseudocode

```c
BOOL __stdcall JetRemoveDirectoryW(LPCWSTR lpPathName)
{
  BOOL v2; // esi
  _BYTE v3[4]; // [esp+0h] [ebp-218h] BYREF
  LPCSTR v4; // [esp+4h] [ebp-214h]
  int v5; // [esp+210h] [ebp-8h]

  if ( wrap )
    return RemoveDirectoryW(lpPathName);
  CStrIn::CStrIn((CStrIn *)v3, lpPathName);
  if ( v5 < 260 )
  {
    v2 = RemoveDirectoryA(v4);
  }
  else
  {
    SetLastError(0xA1u);
    v2 = 0;
  }
  CConvertStr::Free((CConvertStr *)v3);
  return v2;
}

```

## disassembly

```asm
0x100338a0  mov     edi, edi
0x100338a2  push    ebp
0x100338a3  mov     ebp, esp
0x100338a5  sub     esp, 218h
0x100338ab  mov     eax, ___security_cookie
0x100338b0  xor     eax, ebp
0x100338b2  mov     [ebp+var_4], eax
0x100338b5  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x100338bc  mov     eax, [ebp+lpPathName]
0x100338bf  jz      short loc_100338CA
0x100338c1  push    eax; lpPathName
0x100338c2  call    ds:__imp__RemoveDirectoryW@4; RemoveDirectoryW(x)
0x100338c8  jmp     short loc_1003390B
0x100338ca  push    esi
0x100338cb  push    eax; unsigned __int16 *
0x100338cc  lea     ecx, [ebp+var_218]; this
0x100338d2  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x100338d7  cmp     [ebp+var_8], 104h
0x100338de  jl      short loc_100338EF
0x100338e0  push    0A1h; dwErrCode
0x100338e5  call    ds:__imp__SetLastError@4; SetLastError(x)
0x100338eb  xor     esi, esi
0x100338ed  jmp     short loc_100338FD
0x100338ef  push    [ebp+var_214]; lpPathName
0x100338f5  call    ds:__imp__RemoveDirectoryA@4; RemoveDirectoryA(x)
0x100338fb  mov     esi, eax
0x100338fd  lea     ecx, [ebp+var_218]; this
0x10033903  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10033908  mov     eax, esi
0x1003390a  pop     esi
0x1003390b  mov     ecx, [ebp+var_4]
0x1003390e  xor     ecx, ebp; StackCookie
0x10033910  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033915  leave
0x10033916  retn    4
```
