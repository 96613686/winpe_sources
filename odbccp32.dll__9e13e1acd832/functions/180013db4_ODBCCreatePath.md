# ODBCCreatePath

- ea: `0x180013db4`
- end: `0x180013ebb`
- name: `ODBCCreatePath`
- size: `263`
- prototype: `__int64 __fastcall(WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180012c98`

## callees

- `0x180013db4`
- `0x180014ae0`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x180013e6c`
- `KERNEL32!CreateDirectoryW` at `0x180013e6c`

## pseudocode

```c
__int64 __fastcall ODBCCreatePath(WCHAR *a1)
{
  unsigned __int64 v1; // rax
  WCHAR *v2; // rbx
  WCHAR *v4; // rdi
  unsigned int DirectoryW; // edx
  int v6; // ecx
  WCHAR v7; // ax
  WCHAR v8; // cx
  WCHAR PathName[260]; // [rsp+20h] [rbp-228h] BYREF
  char v10; // [rsp+228h] [rbp-20h] BYREF

  v1 = -1;
  v2 = a1;
  do
    ++v1;
  while ( a1[v1] );
  if ( v1 > 0x104 )
    return 0;
  v4 = PathName;
  DirectoryW = 0;
  if ( *a1 == 46 )
  {
    v6 = 1;
    goto LABEL_10;
  }
  if ( *a1 == 92 && a1[1] == 92 )
  {
    v6 = 4;
    do
    {
LABEL_10:
      v7 = *v2;
      if ( !*v2 || v4 >= (WCHAR *)&v10 )
        break;
      if ( v7 == 92 || v7 == 47 )
        --v6;
      *v4 = v7;
      ++v2;
      ++v4;
    }
    while ( v6 );
    goto LABEL_16;
  }
  do
  {
LABEL_16:
    if ( *v2 == 92 || *v2 == 47 || !*v2 )
    {
      *v4 = 0;
      DirectoryW = CreateDirectoryW(PathName, 0);
    }
    v8 = *v2;
    *v4 = *v2;
    if ( !v8 )
      break;
    ++v4;
    ++v2;
  }
  while ( v4 <= (WCHAR *)&v10 );
  return DirectoryW;
}

```

## disassembly

```asm
0x180013db4  mov     [rsp+arg_0], rbx
0x180013db9  mov     [rsp+arg_8], rsi
0x180013dbe  push    rdi
0x180013dbf  sub     rsp, 240h
0x180013dc6  mov     rax, cs:__security_cookie
0x180013dcd  xor     rax, rsp
0x180013dd0  mov     [rsp+248h+var_18], rax
0x180013dd8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013ddc  mov     rbx, rcx
0x180013ddf  xor     esi, esi
0x180013de1  inc     rax
0x180013de4  cmp     [rcx+rax*2], si
0x180013de8  jnz     short loc_180013DE1
0x180013dea  cmp     rax, 104h
0x180013df0  jbe     short loc_180013DF9
0x180013df2  xor     eax, eax
0x180013df4  jmp     loc_180013E96
0x180013df9  cmp     word ptr [rcx], 2Eh ; '.'
0x180013dfd  lea     rdi, [rsp+248h+PathName]
0x180013e02  mov     edx, esi
0x180013e04  jnz     short loc_180013E0D
0x180013e06  mov     ecx, 1
0x180013e0b  jmp     short loc_180013E1F
0x180013e0d  cmp     word ptr [rcx], 5Ch ; '\'
0x180013e11  jnz     short loc_180013E51
0x180013e13  cmp     word ptr [rcx+2], 5Ch ; '\'
0x180013e18  jnz     short loc_180013E51
0x180013e1a  mov     ecx, 4
0x180013e1f  movzx   eax, word ptr [rbx]
0x180013e22  test    ax, ax
0x180013e25  jz      short loc_180013E51
0x180013e27  lea     r8, [rsp+248h+var_20]
0x180013e2f  cmp     rdi, r8
0x180013e32  jnb     short loc_180013E51
0x180013e34  cmp     ax, 5Ch ; '\'
0x180013e38  jz      short loc_180013E40
0x180013e3a  cmp     ax, 2Fh ; '/'
0x180013e3e  jnz     short loc_180013E42
0x180013e40  dec     ecx
0x180013e42  mov     [rdi], ax
0x180013e45  add     rbx, 2
0x180013e49  add     rdi, 2
0x180013e4d  test    ecx, ecx
0x180013e4f  jnz     short loc_180013E1F
0x180013e51  cmp     word ptr [rbx], 5Ch ; '\'
0x180013e55  jz      short loc_180013E62
0x180013e57  cmp     word ptr [rbx], 2Fh ; '/'
0x180013e5b  jz      short loc_180013E62
0x180013e5d  cmp     [rbx], si
0x180013e60  jnz     short loc_180013E74
0x180013e62  xor     edx, edx; lpSecurityAttributes
0x180013e64  mov     [rdi], si
0x180013e67  lea     rcx, [rsp+248h+PathName]; lpPathName
0x180013e6c  call    cs:__imp_CreateDirectoryW
0x180013e72  mov     edx, eax
0x180013e74  movzx   ecx, word ptr [rbx]
0x180013e77  mov     [rdi], cx
0x180013e7a  test    cx, cx
0x180013e7d  jz      short loc_180013E94
0x180013e7f  add     rdi, 2
0x180013e83  lea     rax, [rsp+248h+var_20]
0x180013e8b  add     rbx, 2
0x180013e8f  cmp     rdi, rax
0x180013e92  jbe     short loc_180013E51
0x180013e94  mov     eax, edx
0x180013e96  mov     rcx, [rsp+248h+var_18]
0x180013e9e  xor     rcx, rsp; StackCookie
0x180013ea1  call    __security_check_cookie
0x180013ea6  lea     r11, [rsp+248h+var_8]
0x180013eae  mov     rbx, [r11+10h]
0x180013eb2  mov     rsi, [r11+18h]
0x180013eb6  mov     rsp, r11
0x180013eb9  pop     rdi
0x180013eba  retn
```
