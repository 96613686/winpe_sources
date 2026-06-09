# DOSUniquePathname(x,x,x,x,x)

- ea: `0x100269d4`
- end: `0x10026b26`
- name: `_DOSUniquePathname@20`
- size: `338`
- prototype: `int __thiscall(LPCWCH lpWideCharStr, int, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x10022890`

## callees

- `0x10006400`
- `0x10018b80`
- `0x1001d5b0`
- `0x100256db`
- `0x100268a0`
- `0x100269d4`
- `0x10035510`

## pseudocode

```c
int __thiscall DOSUniquePathname(int lpWideCharStr, unsigned __int16 *a2, int a3, int a4)
{
  WCHAR *v4; // ebx
  __int16 v5; // di
  int v6; // eax
  int result; // eax
  int v8; // [esp+Ch] [ebp-44h]
  unsigned int i; // [esp+10h] [ebp-40h]
  unsigned __int16 cchMax[16]; // [esp+18h] [ebp-38h] BYREF
  int v11; // [esp+38h] [ebp-18h] BYREF
  wchar_t v12; // [esp+3Ch] [ebp-14h]
  _BYTE v13[4]; // [esp+48h] [ebp-8h] BYREF

  v4 = (WCHAR *)lpWideCharStr;
  v5 = 0;
  if ( a2 )
  {
    if ( *a2 )
    {
      v6 = a2[wcslen(a2) - 1];
      lpWideCharStr = 92;
      if ( (_WORD)v6 != 92 && v6 != 58 )
        v5 = 92;
    }
  }
  for ( i = 0; i < 0xFFFF; ++i )
  {
    ITOW(16, lpWideCharStr);
    WCSCPY2(&v11, L"00000000", 9u);
    v11 = *(_DWORD *)L"NET";
    v12 = aNet[2];
    v8 = WCSLEN2((size_t)cchMax);
    if ( (unsigned int)(8 - v8) < 9 )
      WCSCPY2(&v13[-2 * wcslen(cchMax)], cchMax, v8 + 1);
    *v4 = 0;
    if ( a2 )
    {
      if ( *a2 )
      {
        WCSCPY2(v4, a2, 0x105u);
        if ( v5 )
          WCSCAT2(v4, L"\\", 0x105u);
      }
    }
    WCSCAT2(v4, &v11, 0x105u);
    WCSCAT2(v4, L".TMP", 0x105u);
    lpWideCharStr = DOSFileExists(v4);
    if ( lpWideCharStr )
      break;
  }
  result = 0;
  if ( lpWideCharStr != -2 )
    return lpWideCharStr;
  return result;
}

```

## disassembly

```asm
0x100269d4  mov     edi, edi
0x100269d6  push    ebp
0x100269d7  mov     ebp, esp
0x100269d9  sub     esp, 44h
0x100269dc  mov     eax, ___security_cookie
0x100269e1  xor     eax, ebp
0x100269e3  mov     [ebp+var_4], eax
0x100269e6  push    ebx
0x100269e7  push    esi
0x100269e8  mov     esi, [ebp+arg_0]
0x100269eb  xor     eax, eax
0x100269ed  mov     [ebp+var_3C], eax
0x100269f0  mov     ebx, ecx
0x100269f2  push    edi
0x100269f3  mov     edi, eax
0x100269f5  test    esi, esi
0x100269f7  jz      short loc_10026A28
0x100269f9  cmp     [esi], ax
0x100269fc  jz      short loc_10026A28
0x100269fe  mov     ecx, esi
0x10026a00  lea     edx, [ecx+2]
0x10026a03  mov     ax, [ecx]
0x10026a06  add     ecx, 2
0x10026a09  cmp     ax, word ptr [ebp+var_3C]
0x10026a0d  jnz     short loc_10026A03
0x10026a0f  sub     ecx, edx
0x10026a11  sar     ecx, 1
0x10026a13  push    5Ch ; '\'
0x10026a15  movzx   eax, word ptr [esi+ecx*2-2]
0x10026a1a  pop     ecx
0x10026a1b  cmp     ax, cx
0x10026a1e  jz      short loc_10026A26
0x10026a20  cmp     eax, 3Ah ; ':'
0x10026a23  cmovnz  edi, ecx
0x10026a26  xor     eax, eax
0x10026a28  mov     [ebp+var_40], eax
0x10026a2b  push    ecx
0x10026a2c  push    10h
0x10026a2e  lea     edx, [ebp+cchMax]
0x10026a31  mov     ecx, eax
0x10026a33  call    _ITOW@16; ITOW(x,x,x,x)
0x10026a38  push    9
0x10026a3a  mov     edx, offset a00000000; "00000000"
0x10026a3f  lea     ecx, [ebp+var_18]
0x10026a42  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10026a47  mov     eax, dword ptr ds:aNet; "NET"
0x10026a4c  lea     ecx, [ebp+cchMax]; cchMax
0x10026a4f  mov     [ebp+var_18], eax
0x10026a52  mov     ax, word ptr ds:aNet+4; "T"
0x10026a58  push    10h
0x10026a5a  pop     edx
0x10026a5b  mov     [ebp+var_14], ax
0x10026a5f  call    _WCSLEN2@8; WCSLEN2(x,x)
0x10026a64  push    8
0x10026a66  pop     ecx
0x10026a67  sub     ecx, eax
0x10026a69  mov     [ebp+var_44], eax
0x10026a6c  cmp     ecx, 9
0x10026a6f  jnb     short loc_10026A9C
0x10026a71  lea     ecx, [ebp+cchMax]
0x10026a74  lea     edx, [ecx+2]
0x10026a77  mov     ax, [ecx]
0x10026a7a  add     ecx, 2
0x10026a7d  cmp     ax, word ptr [ebp+var_3C]
0x10026a81  jnz     short loc_10026A77
0x10026a83  mov     eax, [ebp+var_44]
0x10026a86  sub     ecx, edx
0x10026a88  sar     ecx, 1
0x10026a8a  lea     edx, [ebp+cchMax]
0x10026a8d  inc     eax
0x10026a8e  push    eax
0x10026a8f  lea     eax, [ecx+ecx]
0x10026a92  lea     ecx, [ebp+var_8]
0x10026a95  sub     ecx, eax
0x10026a97  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10026a9c  xor     eax, eax
0x10026a9e  mov     [ebx], ax
0x10026aa1  test    esi, esi
0x10026aa3  jz      short loc_10026ACE
0x10026aa5  cmp     [esi], ax
0x10026aa8  jz      short loc_10026ACE
0x10026aaa  push    105h
0x10026aaf  mov     edx, esi
0x10026ab1  mov     ecx, ebx
0x10026ab3  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10026ab8  test    di, di
0x10026abb  jz      short loc_10026ACE
0x10026abd  push    105h
0x10026ac2  mov     edx, offset asc_1000539C; "\\"
0x10026ac7  mov     ecx, ebx
0x10026ac9  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10026ace  push    105h
0x10026ad3  lea     edx, [ebp+var_18]
0x10026ad6  mov     ecx, ebx
0x10026ad8  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10026add  push    105h
0x10026ae2  mov     edx, offset aTmp; ".TMP"
0x10026ae7  mov     ecx, ebx
0x10026ae9  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10026aee  mov     ecx, ebx; lpWideCharStr
0x10026af0  call    _DOSFileExists@4; DOSFileExists(x)
0x10026af5  mov     ecx, eax
0x10026af7  test    ecx, ecx
0x10026af9  jnz     short loc_10026B0D
0x10026afb  mov     eax, [ebp+var_40]
0x10026afe  inc     eax
0x10026aff  mov     [ebp+var_40], eax
0x10026b02  cmp     eax, 0FFFFh
0x10026b07  jb      loc_10026A2B
0x10026b0d  xor     eax, eax
0x10026b0f  cmp     ecx, 0FFFFFFFEh
0x10026b12  pop     edi
0x10026b13  cmovnz  eax, ecx
0x10026b16  mov     ecx, [ebp+var_4]
0x10026b19  pop     esi
0x10026b1a  xor     ecx, ebp; StackCookie
0x10026b1c  pop     ebx
0x10026b1d  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10026b22  leave
0x10026b23  retn    0Ch
```
