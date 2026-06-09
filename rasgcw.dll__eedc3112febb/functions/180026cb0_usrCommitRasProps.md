# usrCommitRasProps

- ea: `0x180026cb0`
- end: `0x180026d5a`
- name: `usrCommitRasProps`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180026f44`

## callees

- `0x180026710`
- `0x180026cb0`
- `0x18002c318`
- `0x18002f382`
- `0x18002f3b0`

## import_xrefs

- `MPRAPI!MprAdminUserWrite` at `0x180026d18`
- `MPRAPI!MprAdminUserWrite` at `0x180026d18`

## string_xrefs

- `0x180026d28`: `usrCommitRasProps: unable to commit %S (0x%08x)`

## pseudocode

```c
__int64 __fastcall usrCommitRasProps(__int64 a1)
{
  __int64 result; // rax
  int v3; // eax
  unsigned int v4; // ebx
  char v5; // [rsp+20h] [rbp-128h] BYREF
  char v6; // [rsp+21h] [rbp-127h] BYREF
  _BYTE v7[270]; // [rsp+22h] [rbp-126h] BYREF

  v6 = 0;
  memset_0(&v6, 0, 0x102u);
  v5 = *(_BYTE *)(a1 + 796);
  result = StringCchCopyWrapW(v7, 129, a1 + 538);
  if ( !(_DWORD)result )
  {
    v3 = MprAdminUserWrite(*(_QWORD *)a1, 0, &v5);
    v4 = v3;
    if ( v3 )
      DbgOutputTrace("usrCommitRasProps: unable to commit %S (0x%08x)", *(const wchar_t **)(a1 + 8), v3);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180026cb0  mov     [rsp+arg_8], rbx
0x180026cb5  push    rdi
0x180026cb6  sub     rsp, 140h
0x180026cbd  mov     rax, cs:__security_cookie
0x180026cc4  xor     rax, rsp
0x180026cc7  mov     [rsp+148h+var_18], rax
0x180026ccf  mov     rdi, rcx
0x180026cd2  xor     eax, eax
0x180026cd4  lea     rcx, [rsp+148h+var_127]; void *
0x180026cd9  mov     [rsp+148h+var_127], al
0x180026cdd  xor     edx, edx; Val
0x180026cdf  mov     r8d, 102h; Size
0x180026ce5  call    memset_0
0x180026cea  mov     al, [rdi+31Ch]
0x180026cf0  lea     r8, [rdi+21Ah]
0x180026cf7  mov     edx, 81h
0x180026cfc  mov     [rsp+148h+var_128], al
0x180026d00  lea     rcx, [rsp+148h+var_126]
0x180026d05  call    StringCchCopyWrapW
0x180026d0a  test    eax, eax
0x180026d0c  jnz     short loc_180026D39
0x180026d0e  mov     rcx, [rdi]
0x180026d11  lea     r8, [rsp+148h+var_128]
0x180026d16  xor     edx, edx
0x180026d18  call    cs:__imp_MprAdminUserWrite
0x180026d1e  mov     ebx, eax
0x180026d20  test    eax, eax
0x180026d22  jz      short loc_180026D37
0x180026d24  mov     rdx, [rdi+8]
0x180026d28  lea     rcx, aUsrcommitraspr; "usrCommitRasProps: unable to commit %S "...
0x180026d2f  mov     r8d, eax
0x180026d32  call    DbgOutputTrace
0x180026d37  mov     eax, ebx
0x180026d39  mov     rcx, [rsp+148h+var_18]
0x180026d41  xor     rcx, rsp; StackCookie
0x180026d44  call    __security_check_cookie
0x180026d49  mov     rbx, [rsp+148h+arg_8]
0x180026d51  add     rsp, 140h
0x180026d58  pop     rdi
0x180026d59  retn
```
