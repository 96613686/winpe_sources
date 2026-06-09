# DOSLocatesDirectory(x,x,x)

- ea: `0x1000b860`
- end: `0x1000b975`
- name: `_DOSLocatesDirectory@12`
- size: `277`
- prototype: `int __stdcall(LPCWSTR lpFileName, int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x10011d90`

## callees

- `0x1000b860`
- `0x1000d2c0`
- `0x1000e350`
- `0x1002ac80`
- `0x1002ad40`
- `0x1002b430`
- `0x1002b81a`

## pseudocode

```c
BOOL __stdcall DOSLocatesDirectory(WCHAR *lpFileName, unsigned int a2, int *a3)
{
  unsigned int v4; // esi
  unsigned int v5; // esi
  int v6; // eax
  WCHAR *v7; // esi
  int FileAttributesW; // eax
  BOOL v9; // edi
  WCHAR Buffer[262]; // [esp+8h] [ebp-210h] BYREF

  if ( !lpFileName )
    return 0;
  *a3 = 0;
  v4 = wcslen(lpFileName);
  if ( NetProtocolType((int)lpFileName) )
    return NetDirectoryExists(lpFileName, a3) == 0;
  if ( a2 < v4 )
    return 0;
  v5 = v4 - 1;
  v6 = lpFileName[v5];
  v7 = &lpFileName[v5];
  if ( v6 == 58 )
    return 1;
  if ( *lpFileName == 92 && lpFileName[1] == 92 )
  {
    FileAttributesW = JetGetFileAttributesW(lpFileName);
    if ( FileAttributesW == -1 )
      return 0;
    return ((unsigned __int8)FileAttributesW >> 4) & 1;
  }
  else
  {
    if ( v6 != 92 || v7 == lpFileName || *(v7 - 1) == 58 )
      v7 = 0;
    else
      *v7 = 0;
    JetGetCurrentDirectoryW(0x105u, Buffer);
    v9 = JetSetCurrentDirectoryW(lpFileName);
    if ( v9 )
      JetSetCurrentDirectoryW(Buffer);
    if ( v7 )
      *v7 = 92;
    return v9;
  }
}

```

## disassembly

```asm
0x1000b860  sub     esp, 210h
0x1000b866  mov     eax, ___security_cookie
0x1000b86b  xor     eax, esp
0x1000b86d  mov     [esp+210h+var_4], eax
0x1000b874  push    ebx
0x1000b875  mov     ebx, [esp+214h+arg_8]
0x1000b87c  push    edi
0x1000b87d  mov     edi, [esp+218h+lpFileName]
0x1000b884  test    edi, edi
0x1000b886  jnz     short loc_1000B88F
0x1000b888  xor     eax, eax
0x1000b88a  jmp     loc_1000B95C
0x1000b88f  push    esi
0x1000b890  mov     esi, edi
0x1000b892  mov     dword ptr [ebx], 0
0x1000b898  lea     ecx, [esi+2]
0x1000b89b  jmp     short loc_1000B8A0
0x1000b8a0  mov     ax, [esi]
0x1000b8a3  add     esi, 2
0x1000b8a6  test    ax, ax
0x1000b8a9  jnz     short loc_1000B8A0
0x1000b8ab  sub     esi, ecx
0x1000b8ad  push    edi
0x1000b8ae  sar     esi, 1
0x1000b8b0  call    _NetProtocolType@4; NetProtocolType(x)
0x1000b8b5  test    eax, eax
0x1000b8b7  jz      short loc_1000B8CA
0x1000b8b9  push    ebx
0x1000b8ba  push    edi
0x1000b8bb  call    _NetDirectoryExists@8; NetDirectoryExists(x,x)
0x1000b8c0  neg     eax
0x1000b8c2  sbb     eax, eax
0x1000b8c4  inc     eax
0x1000b8c5  jmp     loc_1000B95B
0x1000b8ca  cmp     [esp+21Ch+arg_4], esi
0x1000b8d1  jb      short loc_1000B8FF
0x1000b8d3  dec     esi
0x1000b8d4  movzx   eax, word ptr [edi+esi*2]
0x1000b8d8  lea     esi, [edi+esi*2]
0x1000b8db  cmp     eax, 3Ah ; ':'
0x1000b8de  jnz     short loc_1000B8E7
0x1000b8e0  mov     eax, 1
0x1000b8e5  jmp     short loc_1000B95B
0x1000b8e7  cmp     word ptr [edi], 5Ch ; '\'
0x1000b8eb  jnz     short loc_1000B90E
0x1000b8ed  cmp     word ptr [edi+2], 5Ch ; '\'
0x1000b8f2  jnz     short loc_1000B90E
0x1000b8f4  push    edi; lpFileName
0x1000b8f5  call    _JetGetFileAttributesW@4; JetGetFileAttributesW(x)
0x1000b8fa  cmp     eax, 0FFFFFFFFh
0x1000b8fd  jnz     short loc_1000B903
0x1000b8ff  xor     eax, eax
0x1000b901  jmp     short loc_1000B95B
0x1000b903  movzx   eax, al
0x1000b906  shr     eax, 4
0x1000b909  and     eax, 1
0x1000b90c  jmp     short loc_1000B95B
0x1000b90e  cmp     eax, 5Ch ; '\'
0x1000b911  jnz     short loc_1000B925
0x1000b913  cmp     esi, edi
0x1000b915  jz      short loc_1000B925
0x1000b917  cmp     word ptr [esi-2], 3Ah ; ':'
0x1000b91c  jz      short loc_1000B925
0x1000b91e  xor     eax, eax
0x1000b920  mov     [esi], ax
0x1000b923  jmp     short loc_1000B927
0x1000b925  xor     esi, esi
0x1000b927  lea     eax, [esp+21Ch+Buffer]
0x1000b92b  push    eax; lpBuffer
0x1000b92c  push    105h; nBufferLength
0x1000b931  call    _JetGetCurrentDirectoryW@8; JetGetCurrentDirectoryW(x,x)
0x1000b936  push    edi; lpPathName
0x1000b937  call    _JetSetCurrentDirectoryW@4; JetSetCurrentDirectoryW(x)
0x1000b93c  mov     edi, eax
0x1000b93e  cmp     edi, 1
0x1000b941  jnz     short loc_1000B94D
0x1000b943  lea     eax, [esp+21Ch+Buffer]
0x1000b947  push    eax; lpPathName
0x1000b948  call    _JetSetCurrentDirectoryW@4; JetSetCurrentDirectoryW(x)
0x1000b94d  test    esi, esi
0x1000b94f  jz      short loc_1000B959
0x1000b951  mov     eax, 5Ch ; '\'
0x1000b956  mov     [esi], ax
0x1000b959  mov     eax, edi
0x1000b95b  pop     esi
0x1000b95c  mov     ecx, [esp+218h+var_4]
0x1000b963  pop     edi
0x1000b964  pop     ebx
0x1000b965  xor     ecx, esp; StackCookie
0x1000b967  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000b96c  add     esp, 210h
0x1000b972  retn    0Ch
```
