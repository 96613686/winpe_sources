# my_tempnam

- ea: `0x140009b38`
- end: `0x140009c1d`
- name: `my_tempnam`
- size: `229`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400061d0`
- `0x14000c6d4`

## callees

- `0x140008e64`
- `0x140009b38`
- `0x14000e450`

## import_xrefs

- `msvcrt!_tempnam` at `0x140009bf9`
- `msvcrt!_tempnam` at `0x140009bf9`
- `KERNEL32!GetCurrentProcessId` at `0x140009bc7`
- `KERNEL32!GetCurrentProcessId` at `0x140009bc7`

## pseudocode

```c
char *__fastcall my_tempnam(__int64 a1, char *a2)
{
  __int64 v2; // rdi
  char *v3; // r8
  __int64 v4; // rax
  __int64 v5; // rcx
  char *v6; // rax
  char *v7; // rax
  __int64 v8; // rdx
  unsigned __int64 v9; // rbx
  DWORD CurrentProcessId; // eax
  char FilePrefix[24]; // [rsp+20h] [rbp-28h] BYREF

  v2 = 0;
  v3 = FilePrefix;
  v4 = 2147483646;
  v5 = 10;
  do
  {
    if ( !v4 )
      break;
    if ( !*a2 )
      break;
    *v3++ = *a2++;
    --v4;
    --v5;
  }
  while ( v5 );
  v6 = v3 - 1;
  if ( v5 )
    v6 = v3;
  *v6 = 0;
  if ( v5 )
  {
    v7 = FilePrefix;
    v8 = 21;
    do
    {
      if ( !*v7 )
        break;
      ++v7;
      --v8;
    }
    while ( v8 );
    v9 = (21 - v8) & -(__int64)(v8 != 0);
    if ( v8 )
    {
      if ( v9 < 0x15 )
      {
        CurrentProcessId = GetCurrentProcessId();
        if ( !StringCbPrintfA(&FilePrefix[v9], 0xBu, "_%u_", CurrentProcessId) )
          return _tempnam(DirectoryName, FilePrefix);
      }
    }
  }
  return (char *)v2;
}

```

## disassembly

```asm
0x140009b38  mov     [rsp+arg_0], rbx
0x140009b3d  push    rdi
0x140009b3e  sub     rsp, 40h
0x140009b42  mov     rax, cs:__security_cookie
0x140009b49  xor     rax, rsp
0x140009b4c  mov     [rsp+48h+var_10], rax
0x140009b51  xor     edi, edi
0x140009b53  lea     r8, [rsp+48h+FilePrefix]
0x140009b58  mov     eax, 7FFFFFFEh
0x140009b5d  lea     ecx, [rdi+0Ah]
0x140009b60  test    rax, rax
0x140009b63  jz      short loc_140009B7F
0x140009b65  mov     r9b, [rdx]
0x140009b68  test    r9b, r9b
0x140009b6b  jz      short loc_140009B7F
0x140009b6d  mov     [r8], r9b
0x140009b70  inc     rdx
0x140009b73  inc     r8
0x140009b76  dec     rax
0x140009b79  sub     rcx, 1
0x140009b7d  jnz     short loc_140009B60
0x140009b7f  test    rcx, rcx
0x140009b82  lea     rax, [r8-1]
0x140009b86  cmovnz  rax, r8
0x140009b8a  mov     [rax], dil
0x140009b8d  jz      short loc_140009C02
0x140009b8f  mov     r8d, 15h
0x140009b95  lea     rax, [rsp+48h+FilePrefix]
0x140009b9a  mov     edx, r8d
0x140009b9d  cmp     [rax], dil
0x140009ba0  jz      short loc_140009BAB
0x140009ba2  inc     rax
0x140009ba5  sub     rdx, 1
0x140009ba9  jnz     short loc_140009B9D
0x140009bab  mov     rcx, r8
0x140009bae  mov     rax, rdx
0x140009bb1  sub     rcx, rdx
0x140009bb4  neg     rax
0x140009bb7  sbb     rbx, rbx
0x140009bba  and     rbx, rcx
0x140009bbd  test    rdx, rdx
0x140009bc0  jz      short loc_140009C02
0x140009bc2  cmp     rbx, r8
0x140009bc5  jnb     short loc_140009C02
0x140009bc7  call    cs:__imp_GetCurrentProcessId
0x140009bcd  lea     rcx, [rsp+48h+FilePrefix]
0x140009bd2  mov     edx, 0Bh; cbDest
0x140009bd7  add     rcx, rbx; pszDest
0x140009bda  lea     r8, aU; "_%u_"
0x140009be1  mov     r9d, eax
0x140009be4  call    StringCbPrintfA
0x140009be9  test    eax, eax
0x140009beb  jnz     short loc_140009C02
0x140009bed  lea     rdx, [rsp+48h+FilePrefix]; FilePrefix
0x140009bf2  lea     rcx, DirectoryName; DirectoryName
0x140009bf9  call    cs:__imp__tempnam
0x140009bff  mov     rdi, rax
0x140009c02  mov     rax, rdi
0x140009c05  mov     rcx, [rsp+48h+var_10]
0x140009c0a  xor     rcx, rsp; StackCookie
0x140009c0d  call    __security_check_cookie
0x140009c12  mov     rbx, [rsp+48h+arg_0]
0x140009c17  add     rsp, 40h
0x140009c1b  pop     rdi
0x140009c1c  retn
```
