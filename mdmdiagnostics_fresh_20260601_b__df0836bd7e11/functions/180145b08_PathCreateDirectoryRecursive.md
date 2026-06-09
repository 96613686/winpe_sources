# PathCreateDirectoryRecursive

- ea: `0x180145b08`
- end: `0x180145c1c`
- name: `PathCreateDirectoryRecursive`
- size: `276`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180145a98`
- `0x180145b08`

## callees

- `0x1801454a4`
- `0x180145b08`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180145b4d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180145be5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180145b4d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180145be5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145bf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145bf3`

## pseudocode

```c
signed int __fastcall PathCreateDirectoryRecursive(LPCWSTR lpPathName, int a2, unsigned int a3)
{
  signed int result; // eax
  int v6; // r9d
  __int64 v7; // rdi
  int v8; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v9; // [rsp+68h] [rbp+20h] BYREF

  v9 = 0;
  v8 = 0;
  if ( !lpPathName || !a2 || a3 >= 0x80 )
    return -2147024809;
  if ( CreateDirectoryW(lpPathName, 0) )
    return 0;
  result = GetLastError();
  if ( result == 183 )
    return 0;
  if ( result != 3 )
  {
LABEL_8:
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  result = StringFindChar((_DWORD)lpPathName, 92, a2, v6, (__int64)&v9, (__int64)&v8);
  if ( result < 0 )
    return result;
  if ( !v8 )
    return -2147024893;
  v7 = v9;
  lpPathName[v9] = 0;
  result = PathCreateDirectoryRecursive(lpPathName);
  if ( result >= 0 )
  {
    lpPathName[v7] = 92;
    if ( !CreateDirectoryW(lpPathName, 0) )
    {
      result = GetLastError();
      if ( result != 183 )
        goto LABEL_8;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180145b08  mov     [rsp+arg_8], rbx
0x180145b0d  push    rsi
0x180145b0e  push    rdi
0x180145b0f  push    r15
0x180145b11  sub     rsp, 30h
0x180145b15  mov     [rsp+48h+arg_18], 0
0x180145b1d  mov     esi, r8d
0x180145b20  mov     [rsp+48h+arg_0], 0
0x180145b28  mov     edi, edx
0x180145b2a  mov     rbx, rcx
0x180145b2d  test    rcx, rcx
0x180145b30  jz      loc_180145C09
0x180145b36  test    edx, edx
0x180145b38  jz      loc_180145C09
0x180145b3e  cmp     r8d, 80h
0x180145b45  jnb     loc_180145C09
0x180145b4b  xor     edx, edx; lpSecurityAttributes
0x180145b4d  call    cs:__imp_CreateDirectoryW
0x180145b53  test    eax, eax
0x180145b55  jz      short loc_180145B5E
0x180145b57  xor     eax, eax
0x180145b59  jmp     loc_180145C0E
0x180145b5e  call    cs:__imp_GetLastError
0x180145b64  cmp     eax, 0B7h
0x180145b69  jz      short loc_180145B57
0x180145b6b  cmp     eax, 3
0x180145b6e  jz      short loc_180145B85
0x180145b70  test    eax, eax
0x180145b72  jle     loc_180145C0E
0x180145b78  movzx   eax, ax
0x180145b7b  or      eax, 80070000h
0x180145b80  jmp     loc_180145C0E
0x180145b85  lea     rax, [rsp+48h+arg_0]
0x180145b8a  mov     r15d, 5Ch ; '\'
0x180145b90  mov     [rsp+48h+var_20], rax
0x180145b95  mov     edx, r15d
0x180145b98  lea     rax, [rsp+48h+arg_18]
0x180145b9d  mov     r8d, edi
0x180145ba0  mov     rcx, rbx
0x180145ba3  mov     [rsp+48h+var_28], rax
0x180145ba8  call    StringFindChar
0x180145bad  test    eax, eax
0x180145baf  js      short loc_180145C0E
0x180145bb1  cmp     [rsp+48h+arg_0], 0
0x180145bb6  jnz     short loc_180145BBF
0x180145bb8  mov     eax, 80070003h
0x180145bbd  jmp     short loc_180145C0E
0x180145bbf  mov     edx, [rsp+48h+arg_18]
0x180145bc3  lea     r8d, [rsi+1]
0x180145bc7  xor     eax, eax
0x180145bc9  mov     rcx, rbx; lpPathName
0x180145bcc  mov     edi, edx
0x180145bce  mov     [rbx+rdx*2], ax
0x180145bd2  call    PathCreateDirectoryRecursive
0x180145bd7  test    eax, eax
0x180145bd9  js      short loc_180145C0E
0x180145bdb  xor     edx, edx; lpSecurityAttributes
0x180145bdd  mov     [rbx+rdi*2], r15w
0x180145be2  mov     rcx, rbx; lpPathName
0x180145be5  call    cs:__imp_CreateDirectoryW
0x180145beb  test    eax, eax
0x180145bed  jnz     loc_180145B57
0x180145bf3  call    cs:__imp_GetLastError
0x180145bf9  cmp     eax, 0B7h
0x180145bfe  jz      loc_180145B57
0x180145c04  jmp     loc_180145B70
0x180145c09  mov     eax, 80070057h
0x180145c0e  mov     rbx, [rsp+48h+arg_8]
0x180145c13  add     rsp, 30h
0x180145c17  pop     r15
0x180145c19  pop     rdi
0x180145c1a  pop     rsi
0x180145c1b  retn
```
