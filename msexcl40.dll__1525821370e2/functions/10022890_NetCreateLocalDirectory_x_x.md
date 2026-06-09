# NetCreateLocalDirectory(x,x)

- ea: `0x10022890`
- end: `0x1002291a`
- name: `_NetCreateLocalDirectory@8`
- size: `138`
- prototype: `int __thiscall(LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x10026c60`

## callees

- `0x10006400`
- `0x10018b80`
- `0x10022890`
- `0x100269d4`
- `0x10032f10`
- `0x1003379f`
- `0x10035510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100228e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x100228e4`

## pseudocode

```c
int __thiscall NetCreateLocalDirectory(LPCWCH lpWideCharStr)
{
  int v2; // ecx
  WCHAR Buffer[266]; // [esp+8h] [ebp-218h] BYREF

  *lpWideCharStr = 0;
  JetGetTempPathW(0x104u, Buffer);
  if ( DOSUniquePathname(lpWideCharStr, (int)Buffer, v2, v2)
    || JetCreateDirectoryW(lpWideCharStr, 0) != 1 && (unsigned __int16)GetLastError() )
  {
    WCSCPY2(261);
  }
  return WCSCAT2(261);
}

```

## disassembly

```asm
0x10022890  mov     edi, edi
0x10022892  push    ebp
0x10022893  mov     ebp, esp
0x10022895  sub     esp, 218h
0x1002289b  mov     eax, ___security_cookie
0x100228a0  xor     eax, ebp
0x100228a2  mov     [ebp+var_4], eax
0x100228a5  push    esi
0x100228a6  mov     esi, ecx
0x100228a8  xor     eax, eax
0x100228aa  push    edi
0x100228ab  mov     [esi], ax
0x100228ae  lea     eax, [ebp+Buffer]
0x100228b4  push    eax; lpBuffer
0x100228b5  push    104h; nBufferLength
0x100228ba  call    _JetGetTempPathW@8; JetGetTempPathW(x,x)
0x100228bf  push    ecx; int
0x100228c0  push    ecx; int
0x100228c1  lea     eax, [ebp+Buffer]
0x100228c7  mov     ecx, esi; lpWideCharStr
0x100228c9  push    eax; int
0x100228ca  call    _DOSUniquePathname@20; DOSUniquePathname(x,x,x,x,x)
0x100228cf  mov     edi, 105h
0x100228d4  test    eax, eax
0x100228d6  jnz     short loc_100228F1
0x100228d8  push    eax; lpSecurityAttributes
0x100228d9  push    esi; lpPathName
0x100228da  call    _JetCreateDirectoryW@8; JetCreateDirectoryW(x,x)
0x100228df  cmp     eax, 1
0x100228e2  jz      short loc_100228FF
0x100228e4  call    ds:__imp__GetLastError@0; GetLastError()
0x100228ea  movzx   eax, ax
0x100228ed  test    eax, eax
0x100228ef  jz      short loc_100228FF
0x100228f1  push    edi
0x100228f2  lea     edx, [ebp+Buffer]
0x100228f8  mov     ecx, esi
0x100228fa  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100228ff  push    edi
0x10022900  mov     edx, offset asc_1000539C; "\\"
0x10022905  mov     ecx, esi
0x10022907  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002290c  mov     ecx, [ebp+var_4]
0x1002290f  pop     edi
0x10022910  xor     ecx, ebp; StackCookie
0x10022912  pop     esi
0x10022913  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10022918  leave
0x10022919  retn
```
