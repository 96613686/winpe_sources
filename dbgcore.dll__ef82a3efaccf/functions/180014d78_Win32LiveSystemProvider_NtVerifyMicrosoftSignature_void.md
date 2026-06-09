# Win32LiveSystemProvider::NtVerifyMicrosoftSignature(void *)

- ea: `0x180014d78`
- end: `0x180014ec7`
- name: `?NtVerifyMicrosoftSignature@Win32LiveSystemProvider@@AEAAJPEAX@Z`
- size: `335`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016198`

## callees

- `0x180014d78`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ea1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014e97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ea1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014dd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014e91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014dd6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014e91`

## pseudocode

```c
__int64 __fastcall Win32LiveSystemProvider::NtVerifyMicrosoftSignature(Win32LiveSystemProvider *this, void *a2)
{
  unsigned int (__fastcall *v2)(void *, int *, unsigned int *, _QWORD, _QWORD, _QWORD); // r10
  unsigned int v3; // ebx
  unsigned int (__fastcall *v5)(void **, __int64, __int64, void *); // rax
  unsigned int (__fastcall *v6)(void *, int *, unsigned int *, _QWORD, _QWORD, _QWORD); // rax
  __int64 v7; // rax
  _QWORD *v8; // rdx
  _QWORD *v9; // rax
  signed int LastError; // eax
  unsigned int v12; // [rsp+60h] [rbp+20h] BYREF
  void *v13; // [rsp+68h] [rbp+28h] BYREF
  int v14; // [rsp+70h] [rbp+30h] BYREF

  v13 = a2;
  v2 = (unsigned int (__fastcall *)(void *, int *, unsigned int *, _QWORD, _QWORD, _QWORD))*((_QWORD *)this + 73);
  v3 = 0;
  v14 = 0;
  v12 = 0;
  if ( v2 )
  {
    if ( v2(a2, &v14, &v12, 0, 0, 0) && v12 >= 8 )
      return v3;
  }
  else
  {
    SetLastError(0x32u);
  }
  v5 = (unsigned int (__fastcall *)(void **, __int64, __int64, void *))*((_QWORD *)this + 74);
  if ( v5 )
  {
    if ( !v5(&v13, 1, 5, v13) )
      goto LABEL_16;
    v6 = (unsigned int (__fastcall *)(void *, int *, unsigned int *, _QWORD, _QWORD, _QWORD))*((_QWORD *)this + 73);
    if ( v6 )
    {
      if ( v6(v13, &v14, &v12, 0, 0, 0) )
      {
        if ( v12 >= 8 )
        {
          v7 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 6) + 8LL))(*((_QWORD *)this + 6), 24);
          v8 = (_QWORD *)v7;
          if ( v7 )
          {
            *(_QWORD *)(v7 + 16) = v13;
            v9 = (_QWORD *)*((_QWORD *)this + 97);
            *v8 = (char *)this + 768;
            v8[1] = v9;
            *v9 = v8;
            *((_QWORD *)this + 97) = v8;
          }
          else
          {
            return (unsigned int)-1073740760;
          }
        }
        else
        {
          return (unsigned int)-2146869244;
        }
        return v3;
      }
      goto LABEL_16;
    }
  }
  SetLastError(0x32u);
LABEL_16:
  if ( GetLastError() )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v3;
}

```

## disassembly

```asm
0x180014d78  mov     [rsp-18h+arg_8], rdx
0x180014d7d  push    rbp
0x180014d7e  push    rbx
0x180014d7f  push    rdi
0x180014d80  mov     rbp, rsp
0x180014d83  sub     rsp, 40h
0x180014d87  mov     r10, [rcx+248h]
0x180014d8e  xor     ebx, ebx
0x180014d90  mov     [rbp+arg_10], ebx
0x180014d93  mov     rax, rdx
0x180014d96  mov     [rbp+arg_0], ebx
0x180014d99  mov     rdi, rcx
0x180014d9c  test    r10, r10
0x180014d9f  jz      short loc_180014DD1
0x180014da1  mov     rcx, rax
0x180014da4  mov     [rsp+40h+var_18], rbx
0x180014da9  mov     rax, r10
0x180014dac  mov     [rsp+40h+var_20], rbx
0x180014db1  xor     r9d, r9d
0x180014db4  lea     r8, [rbp+arg_0]
0x180014db8  lea     rdx, [rbp+arg_10]
0x180014dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dc1  test    eax, eax
0x180014dc3  jz      short loc_180014DDC
0x180014dc5  cmp     [rbp+arg_0], 8
0x180014dc9  jnb     loc_180014EBD
0x180014dcf  jmp     short loc_180014DDC
0x180014dd1  mov     ecx, 32h ; '2'; dwErrCode
0x180014dd6  call    cs:__imp_SetLastError
0x180014ddc  mov     rax, [rdi+250h]
0x180014de3  test    rax, rax
0x180014de6  jz      loc_180014E8C
0x180014dec  mov     r9, [rbp+arg_8]
0x180014df0  lea     rcx, [rbp+arg_8]
0x180014df4  mov     edx, 1
0x180014df9  lea     r8d, [rdx+4]
0x180014dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e02  test    eax, eax
0x180014e04  jz      loc_180014E97
0x180014e0a  mov     rax, [rdi+248h]
0x180014e11  test    rax, rax
0x180014e14  jz      short loc_180014E8C
0x180014e16  mov     rcx, [rbp+arg_8]
0x180014e1a  lea     r8, [rbp+arg_0]
0x180014e1e  mov     [rsp+40h+var_18], rbx
0x180014e23  lea     rdx, [rbp+arg_10]
0x180014e27  xor     r9d, r9d
0x180014e2a  mov     [rsp+40h+var_20], rbx
0x180014e2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e34  test    eax, eax
0x180014e36  jz      short loc_180014E97
0x180014e38  cmp     [rbp+arg_0], 8
0x180014e3c  jnb     short loc_180014E45
0x180014e3e  mov     ebx, 80096004h
0x180014e43  jmp     short loc_180014EBD
0x180014e45  mov     rcx, [rdi+30h]
0x180014e49  mov     edx, 18h
0x180014e4e  mov     rax, [rcx]
0x180014e51  mov     rax, [rax+8]
0x180014e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e5a  mov     rdx, rax
0x180014e5d  test    rax, rax
0x180014e60  jz      short loc_180014E85
0x180014e62  mov     rax, [rbp+arg_8]
0x180014e66  lea     rcx, [rdi+300h]
0x180014e6d  mov     [rdx+10h], rax
0x180014e71  mov     rax, [rcx+8]
0x180014e75  mov     [rdx], rcx
0x180014e78  mov     [rdx+8], rax
0x180014e7c  mov     [rax], rdx
0x180014e7f  mov     [rcx+8], rdx
0x180014e83  jmp     short loc_180014EBD
0x180014e85  mov     ebx, 0C0000428h
0x180014e8a  jmp     short loc_180014EBD
0x180014e8c  mov     ecx, 32h ; '2'; dwErrCode
0x180014e91  call    cs:__imp_SetLastError
0x180014e97  call    cs:__imp_GetLastError
0x180014e9d  test    eax, eax
0x180014e9f  jz      short loc_180014EB8
0x180014ea1  call    cs:__imp_GetLastError
0x180014ea7  mov     ebx, eax
0x180014ea9  test    eax, eax
0x180014eab  jle     short loc_180014EBD
0x180014ead  movzx   ebx, ax
0x180014eb0  or      ebx, 80070000h
0x180014eb6  jmp     short loc_180014EBD
0x180014eb8  mov     ebx, 80004005h
0x180014ebd  mov     eax, ebx
0x180014ebf  add     rsp, 40h
0x180014ec3  pop     rdi
0x180014ec4  pop     rbx
0x180014ec5  pop     rbp
0x180014ec6  retn
```
