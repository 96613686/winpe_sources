# CInplaceShareEngine::_IsUnderSmbShare(ushort const *)

- ea: `0x18001d7b4`
- end: `0x18001d8c7`
- name: `?_IsUnderSmbShare@CInplaceShareEngine@@AEAAHPEBG@Z`
- size: `275`
- prototype: `int(CInplaceShareEngine *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d380`
- `0x180012160`

## callees

- `0x18001d7b4`
- `0x1800254e0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d891`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001d891`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18001d86f`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18001d86f`
- `SHLWAPI!PathIsRootW` at `0x18001d830`
- `SHLWAPI!PathIsRootW` at `0x18001d830`

## pseudocode

```c
__int64 __fastcall CInplaceShareEngine::_IsUnderSmbShare(CInplaceShareEngine *this, const unsigned __int16 *a2)
{
  WCHAR *v3; // rax
  unsigned int v5; // edx
  __int64 v6; // r9
  const unsigned __int16 *v7; // r10
  __int64 v8; // r8
  WCHAR *v9; // rcx
  int v10; // ebx
  int v11; // eax
  _DWORD v13[4]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-238h] BYREF

  v3 = pszPath;
  v5 = 0;
  v6 = 2147483646;
  v13[0] = 0;
  v7 = a2;
  v8 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*v7 )
      break;
    *v3++ = *v7++;
    --v6;
    --v8;
  }
  while ( v8 );
  v9 = v3 - 1;
  if ( v8 )
    v9 = v3;
  *v9 = 0;
  if ( v8 )
  {
    v10 = 0;
    do
    {
      if ( PathIsRootW(pszPath) || v10 < 0 )
        break;
      v10 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, __int64, _DWORD *))(**((_QWORD **)this + 8) + 48LL))(
              *((_QWORD *)this + 8),
              pszPath,
              1,
              v13);
      if ( v10 >= 0 )
      {
        if ( v13[0] )
          break;
        PathRemoveFileSpecW(pszPath);
      }
    }
    while ( !v13[0] );
    v11 = CompareStringOrdinal(pszPath, -1, a2, -1, 1);
    v5 = 0;
    if ( v11 != 2 )
      return v13[0];
  }
  return v5;
}

```

## disassembly

```asm
0x18001d7b4  mov     [rsp+arg_10], rbx
0x18001d7b9  push    rbp
0x18001d7ba  push    rsi
0x18001d7bb  push    rdi
0x18001d7bc  sub     rsp, 260h
0x18001d7c3  mov     rax, cs:__security_cookie
0x18001d7ca  xor     rax, rsp
0x18001d7cd  mov     [rsp+278h+var_28], rax
0x18001d7d5  mov     rdi, rdx
0x18001d7d8  lea     rax, [rsp+278h+pszPath]
0x18001d7dd  xor     ebp, ebp
0x18001d7df  mov     rsi, rcx
0x18001d7e2  mov     edx, ebp
0x18001d7e4  mov     r9d, 7FFFFFFEh
0x18001d7ea  mov     [rsp+278h+var_248], edx
0x18001d7ee  mov     r10, rdi
0x18001d7f1  mov     r8d, 104h
0x18001d7f7  test    r9, r9
0x18001d7fa  jz      short loc_18001D819
0x18001d7fc  movzx   ecx, word ptr [r10]
0x18001d800  test    cx, cx
0x18001d803  jz      short loc_18001D819
0x18001d805  mov     [rax], cx
0x18001d808  add     r10, 2
0x18001d80c  add     rax, 2
0x18001d810  dec     r9
0x18001d813  sub     r8, 1
0x18001d817  jnz     short loc_18001D7F7
0x18001d819  test    r8, r8
0x18001d81c  lea     rcx, [rax-2]
0x18001d820  cmovnz  rcx, rax
0x18001d824  mov     [rcx], bp
0x18001d827  jz      short loc_18001D8A2
0x18001d829  mov     ebx, ebp
0x18001d82b  lea     rcx, [rsp+278h+pszPath]; pszPath
0x18001d830  call    cs:__imp_PathIsRootW
0x18001d836  test    eax, eax
0x18001d838  jnz     short loc_18001D87B
0x18001d83a  test    ebx, ebx
0x18001d83c  js      short loc_18001D87B
0x18001d83e  mov     rcx, [rsi+40h]
0x18001d842  lea     r9, [rsp+278h+var_248]
0x18001d847  mov     r8d, 1
0x18001d84d  lea     rdx, [rsp+278h+pszPath]
0x18001d852  mov     rax, [rcx]
0x18001d855  mov     rax, [rax+30h]
0x18001d859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d85e  mov     ebx, eax
0x18001d860  test    eax, eax
0x18001d862  js      short loc_18001D875
0x18001d864  cmp     [rsp+278h+var_248], ebp
0x18001d868  jnz     short loc_18001D87B
0x18001d86a  lea     rcx, [rsp+278h+pszPath]; pszPath
0x18001d86f  call    cs:__imp_PathRemoveFileSpecW
0x18001d875  cmp     [rsp+278h+var_248], ebp
0x18001d879  jz      short loc_18001D82B
0x18001d87b  or      edx, 0FFFFFFFFh; cchCount1
0x18001d87e  mov     [rsp+278h+bIgnoreCase], 1; bIgnoreCase
0x18001d886  mov     r9d, edx; cchCount2
0x18001d889  lea     rcx, [rsp+278h+pszPath]; lpString1
0x18001d88e  mov     r8, rdi; lpString2
0x18001d891  call    cs:__imp_CompareStringOrdinal
0x18001d897  mov     edx, ebp
0x18001d899  cmp     eax, 2
0x18001d89c  jz      short loc_18001D8A2
0x18001d89e  mov     edx, [rsp+278h+var_248]
0x18001d8a2  mov     eax, edx
0x18001d8a4  mov     rcx, [rsp+278h+var_28]
0x18001d8ac  xor     rcx, rsp; StackCookie
0x18001d8af  call    __security_check_cookie
0x18001d8b4  mov     rbx, [rsp+278h+arg_10]
0x18001d8bc  add     rsp, 260h
0x18001d8c3  pop     rdi
0x18001d8c4  pop     rsi
0x18001d8c5  pop     rbp
0x18001d8c6  retn
```
