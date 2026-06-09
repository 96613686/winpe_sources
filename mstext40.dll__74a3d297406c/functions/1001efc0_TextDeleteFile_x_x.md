# TextDeleteFile(x,x)

- ea: `0x1001efc0`
- end: `0x1001f054`
- name: `_TextDeleteFile@8`
- size: `148`
- prototype: `int __stdcall(int, STRSAFE_LPCWSTR pszSrc)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x10011310`
- `0x100113f0`

## callees

- `0x1000ad60`
- `0x1000b5f0`
- `0x1001efc0`
- `0x1002b81a`

## pseudocode

```c
int __stdcall TextDeleteFile(int a1, STRSAFE_LPCWSTR pszSrc)
{
  wchar_t *v2; // eax
  int v3; // edx
  wchar_t v4; // cx
  wchar_t pszDest[262]; // [esp+4h] [ebp-210h] BYREF

  v2 = pszDest;
  v3 = 261;
  while ( v3 != -2147483385 )
  {
    v4 = *(wchar_t *)((char *)v2 + a1 - (_DWORD)pszDest);
    if ( !v4 )
      break;
    *v2++ = v4;
    if ( !--v3 )
    {
      --v2;
      break;
    }
  }
  *v2 = 0;
  StringCchCatW(pszDest, 0x105u, pszSrc);
  DOSFileDelete(pszDest);
  return 0;
}

```

## disassembly

```asm
0x1001efc0  sub     esp, 210h
0x1001efc6  mov     eax, ___security_cookie
0x1001efcb  xor     eax, esp
0x1001efcd  mov     [esp+210h+var_4], eax
0x1001efd4  push    esi
0x1001efd5  mov     esi, [esp+214h+arg_0]
0x1001efdc  lea     eax, [esp+214h+pszDest]
0x1001efe0  mov     ecx, eax
0x1001efe2  mov     edx, 105h
0x1001efe7  sub     esi, ecx
0x1001efe9  lea     esp, [esp+0]
0x1001eff0  lea     ecx, [edx+7FFFFEF9h]
0x1001eff6  test    ecx, ecx
0x1001eff8  jz      short loc_1001F00E
0x1001effa  movzx   ecx, word ptr [esi+eax]
0x1001effe  test    cx, cx
0x1001f001  jz      short loc_1001F00E
0x1001f003  mov     [eax], cx
0x1001f006  add     eax, 2
0x1001f009  dec     edx
0x1001f00a  jnz     short loc_1001EFF0
0x1001f00c  jmp     short loc_1001F012
0x1001f00e  test    edx, edx
0x1001f010  jnz     short loc_1001F015
0x1001f012  sub     eax, 2
0x1001f015  push    [esp+214h+pszSrc]; pszSrc
0x1001f01c  xor     ecx, ecx
0x1001f01e  mov     [eax], cx
0x1001f021  lea     eax, [esp+218h+pszDest]
0x1001f025  push    105h; cchDest
0x1001f02a  push    eax; pszDest
0x1001f02b  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1001f030  lea     eax, [esp+214h+pszDest]
0x1001f034  push    eax
0x1001f035  call    _DOSFileDelete@4; DOSFileDelete(x)
0x1001f03a  mov     ecx, [esp+214h+var_4]
0x1001f041  xor     eax, eax
0x1001f043  pop     esi
0x1001f044  xor     ecx, esp; StackCookie
0x1001f046  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001f04b  add     esp, 210h
0x1001f051  retn    8
```
