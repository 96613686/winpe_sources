# JetSetCurrentDirectoryW(x)

- ea: `0x1003391f`
- end: `0x10033998`
- name: `_JetSetCurrentDirectoryW@4`
- size: `121`
- prototype: `int __stdcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x10026676`

## callees

- `0x10032925`
- `0x10032956`
- `0x1003391f`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x10033964`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x10033964`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x10033941`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryW` at `0x10033941`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryA` at `0x10033974`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryA` at `0x10033974`

## pseudocode

```c
BOOL __stdcall JetSetCurrentDirectoryW(LPCWSTR lpPathName)
{
  BOOL v2; // esi
  _BYTE v3[4]; // [esp+0h] [ebp-218h] BYREF
  LPCSTR v4; // [esp+4h] [ebp-214h]
  int v5; // [esp+210h] [ebp-8h]

  if ( wrap )
    return SetCurrentDirectoryW(lpPathName);
  CStrIn::CStrIn((CStrIn *)v3, lpPathName);
  if ( v5 < 260 )
  {
    v2 = SetCurrentDirectoryA(v4);
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
0x1003391f  mov     edi, edi
0x10033921  push    ebp
0x10033922  mov     ebp, esp
0x10033924  sub     esp, 218h
0x1003392a  mov     eax, ___security_cookie
0x1003392f  xor     eax, ebp
0x10033931  mov     [ebp+var_4], eax
0x10033934  cmp     ?wrap@@3VWrapper@@A, 0; Wrapper wrap
0x1003393b  mov     eax, [ebp+lpPathName]
0x1003393e  jz      short loc_10033949
0x10033940  push    eax; lpPathName
0x10033941  call    ds:__imp__SetCurrentDirectoryW@4; SetCurrentDirectoryW(x)
0x10033947  jmp     short loc_1003398A
0x10033949  push    esi
0x1003394a  push    eax; unsigned __int16 *
0x1003394b  lea     ecx, [ebp+var_218]; this
0x10033951  call    ??0CStrIn@@QAE@PBG@Z; CStrIn::CStrIn(ushort const *)
0x10033956  cmp     [ebp+var_8], 104h
0x1003395d  jl      short loc_1003396E
0x1003395f  push    0A1h; dwErrCode
0x10033964  call    ds:__imp__SetLastError@4; SetLastError(x)
0x1003396a  xor     esi, esi
0x1003396c  jmp     short loc_1003397C
0x1003396e  push    [ebp+var_214]; lpPathName
0x10033974  call    ds:__imp__SetCurrentDirectoryA@4; SetCurrentDirectoryA(x)
0x1003397a  mov     esi, eax
0x1003397c  lea     ecx, [ebp+var_218]; this
0x10033982  call    ?Free@CConvertStr@@IAEXXZ; CConvertStr::Free(void)
0x10033987  mov     eax, esi
0x10033989  pop     esi
0x1003398a  mov     ecx, [ebp+var_4]
0x1003398d  xor     ecx, ebp; StackCookie
0x1003398f  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10033994  leave
0x10033995  retn    4
```
