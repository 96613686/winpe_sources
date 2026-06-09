# DOSLocatesDirectory(x,x,x)

- ea: `0x10026676`
- end: `0x1002676c`
- name: `_DOSLocatesDirectory@12`
- size: `246`
- prototype: `int __thiscall(LPCWSTR lpPathName, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10026c60`

## callees

- `0x10022871`
- `0x10023bdb`
- `0x10026676`
- `0x1003306e`
- `0x10033823`
- `0x1003391f`
- `0x10035510`

## pseudocode

```c
BOOL __thiscall DOSLocatesDirectory(WCHAR *lpPathName, int *a2)
{
  unsigned int v3; // edi
  WCHAR *v5; // edi
  unsigned int FileAttributesW; // eax
  BOOL v7; // esi
  WCHAR Buffer[266]; // [esp+Ch] [ebp-218h] BYREF

  if ( !lpPathName )
    return 0;
  *a2 = 0;
  v3 = wcslen(lpPathName);
  if ( NetProtocolType(lpPathName) )
    return !NetDirectoryExists(lpPathName, a2);
  if ( v3 > 0x105 )
    return 0;
  v5 = &lpPathName[v3 - 1];
  if ( *v5 == 58 )
    return 1;
  if ( *lpPathName == 92 && lpPathName[1] == 92 )
  {
    FileAttributesW = JetGetFileAttributesW(lpPathName);
    if ( FileAttributesW != -1 )
      return (FileAttributesW >> 4) & 1;
    return 0;
  }
  if ( *v5 != 92 || v5 == lpPathName || *(v5 - 1) == 58 )
    v5 = 0;
  else
    *v5 = 0;
  JetGetCurrentDirectoryW(0x105u, Buffer);
  v7 = JetSetCurrentDirectoryW(lpPathName);
  if ( v7 )
    JetSetCurrentDirectoryW(Buffer);
  if ( v5 )
    *v5 = 92;
  return v7;
}

```

## disassembly

```asm
0x10026676  mov     edi, edi
0x10026678  push    ebp
0x10026679  mov     ebp, esp
0x1002667b  sub     esp, 218h
0x10026681  mov     eax, ___security_cookie
0x10026686  xor     eax, ebp
0x10026688  mov     [ebp+var_4], eax
0x1002668b  push    ebx
0x1002668c  mov     ebx, [ebp+arg_0]
0x1002668f  push    esi
0x10026690  mov     esi, ecx
0x10026692  push    edi
0x10026693  test    esi, esi
0x10026695  jz      loc_10026759
0x1002669b  mov     edi, esi
0x1002669d  xor     edx, edx
0x1002669f  mov     [ebx], edx
0x100266a1  lea     ecx, [edi+2]
0x100266a4  mov     ax, [edi]
0x100266a7  add     edi, 2
0x100266aa  cmp     ax, dx
0x100266ad  jnz     short loc_100266A4
0x100266af  sub     edi, ecx
0x100266b1  mov     ecx, esi
0x100266b3  sar     edi, 1
0x100266b5  call    _NetProtocolType@4; NetProtocolType(x)
0x100266ba  test    eax, eax
0x100266bc  jz      short loc_100266D7
0x100266be  mov     edx, ebx
0x100266c0  mov     ecx, esi
0x100266c2  call    _NetDirectoryExists@8; NetDirectoryExists(x,x)
0x100266c7  test    eax, eax
0x100266c9  jnz     loc_10026759
0x100266cf  xor     eax, eax
0x100266d1  inc     eax
0x100266d2  jmp     loc_1002675B
0x100266d7  mov     ecx, 105h
0x100266dc  cmp     edi, ecx
0x100266de  ja      short loc_10026759
0x100266e0  dec     edi
0x100266e1  push    3Ah ; ':'
0x100266e3  pop     edx
0x100266e4  lea     edi, [esi+edi*2]
0x100266e7  movzx   eax, word ptr [edi]
0x100266ea  cmp     ax, dx
0x100266ed  jz      short loc_100266CF
0x100266ef  push    5Ch ; '\'
0x100266f1  pop     ebx
0x100266f2  cmp     [esi], bx
0x100266f5  jnz     short loc_10026710
0x100266f7  cmp     [esi+2], bx
0x100266fb  jnz     short loc_10026710
0x100266fd  push    esi; lpFileName
0x100266fe  call    _JetGetFileAttributesW@4; JetGetFileAttributesW(x)
0x10026703  cmp     eax, 0FFFFFFFFh
0x10026706  jz      short loc_10026759
0x10026708  shr     eax, 4
0x1002670b  and     eax, 1
0x1002670e  jmp     short loc_1002675B
0x10026710  cmp     ax, bx
0x10026713  jnz     short loc_10026726
0x10026715  cmp     edi, esi
0x10026717  jz      short loc_10026726
0x10026719  cmp     [edi-2], dx
0x1002671d  jz      short loc_10026726
0x1002671f  xor     eax, eax
0x10026721  mov     [edi], ax
0x10026724  jmp     short loc_10026728
0x10026726  xor     edi, edi
0x10026728  lea     eax, [ebp+Buffer]
0x1002672e  push    eax; lpBuffer
0x1002672f  push    ecx; nBufferLength
0x10026730  call    _JetGetCurrentDirectoryW@8; JetGetCurrentDirectoryW(x,x)
0x10026735  push    esi; lpPathName
0x10026736  call    _JetSetCurrentDirectoryW@4; JetSetCurrentDirectoryW(x)
0x1002673b  mov     esi, eax
0x1002673d  cmp     esi, 1
0x10026740  jnz     short loc_1002674E
0x10026742  lea     eax, [ebp+Buffer]
0x10026748  push    eax; lpPathName
0x10026749  call    _JetSetCurrentDirectoryW@4; JetSetCurrentDirectoryW(x)
0x1002674e  test    edi, edi
0x10026750  jz      short loc_10026755
0x10026752  mov     [edi], bx
0x10026755  mov     eax, esi
0x10026757  jmp     short loc_1002675B
0x10026759  xor     eax, eax
0x1002675b  mov     ecx, [ebp+var_4]
0x1002675e  pop     edi
0x1002675f  pop     esi
0x10026760  xor     ecx, ebp; StackCookie
0x10026762  pop     ebx
0x10026763  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10026768  leave
0x10026769  retn    4
```
