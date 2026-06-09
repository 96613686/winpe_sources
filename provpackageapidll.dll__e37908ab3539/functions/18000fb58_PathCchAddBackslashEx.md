# PathCchAddBackslashEx

- ea: `0x18000fb58`
- end: `0x18000fc09`
- name: `PathCchAddBackslashEx`
- size: `177`
- prototype: `HRESULT __stdcall(PWSTR pszPath, size_t cchPath, PWSTR *ppszEnd, size_t *pcchRemaining)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x18000fc8c`

## callees

- `0x18000f9b8`
- `0x18000fb58`

## pseudocode

```c
HRESULT __stdcall PathCchAddBackslashEx(PWSTR pszPath, size_t cchPath, PWSTR *ppszEnd, size_t *pcchRemaining)
{
  size_t v6; // rax
  HRESULT result; // eax
  unsigned __int64 v8; // rdx
  WCHAR *v9; // rcx
  unsigned __int16 *v10; // [rsp+48h] [rbp+10h] BYREF
  unsigned __int64 v11; // [rsp+50h] [rbp+18h] BYREF

  if ( ppszEnd )
    *ppszEnd = 0;
  if ( pcchRemaining )
    *pcchRemaining = 0;
  v6 = -1;
  do
    ++v6;
  while ( pszPath[v6] );
  if ( v6 >= cchPath )
    return -2147024774;
  v8 = cchPath - v6;
  v9 = &pszPath[v6];
  v10 = v9;
  v11 = v8;
  if ( !v6 || *(v9 - 1) == 92 )
  {
    result = 1;
  }
  else
  {
    result = StringCchCopyExW(v9, v8, L"\\", &v10, &v11);
    if ( result < 0 )
      return result;
    v9 = v10;
    v8 = v11;
  }
  if ( ppszEnd )
    *ppszEnd = v9;
  if ( pcchRemaining )
    *pcchRemaining = v8;
  return result;
}

```

## disassembly

```asm
0x18000fb58  mov     [rsp+arg_0], rbx
0x18000fb5d  mov     [rsp+arg_18], rsi
0x18000fb62  push    rdi
0x18000fb63  sub     rsp, 30h
0x18000fb67  xor     esi, esi
0x18000fb69  mov     rbx, r9
0x18000fb6c  mov     rdi, r8
0x18000fb6f  test    r8, r8
0x18000fb72  jz      short loc_18000FB77
0x18000fb74  mov     [r8], rsi
0x18000fb77  test    rbx, rbx
0x18000fb7a  jz      short loc_18000FB7F
0x18000fb7c  mov     [r9], rsi
0x18000fb7f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000fb83  inc     rax
0x18000fb86  cmp     [rcx+rax*2], si
0x18000fb8a  jnz     short loc_18000FB83
0x18000fb8c  cmp     rax, rdx
0x18000fb8f  jb      short loc_18000FB98
0x18000fb91  mov     eax, 8007007Ah
0x18000fb96  jmp     short loc_18000FBF9
0x18000fb98  sub     rdx, rax; unsigned __int64
0x18000fb9b  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18000fb9f  mov     [rsp+38h+arg_8], rcx
0x18000fba4  mov     [rsp+38h+arg_10], rdx
0x18000fba9  test    rax, rax
0x18000fbac  jz      short loc_18000FBE4
0x18000fbae  mov     eax, 5Ch ; '\'
0x18000fbb3  cmp     ax, [rcx-2]
0x18000fbb7  jz      short loc_18000FBE4
0x18000fbb9  lea     rax, [rsp+38h+arg_10]
0x18000fbbe  lea     r9, [rsp+38h+arg_8]; unsigned __int16 **
0x18000fbc3  mov     [rsp+38h+var_18], rax; unsigned __int64 *
0x18000fbc8  lea     r8, Delimiter; "\\"
0x18000fbcf  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18000fbd4  test    eax, eax
0x18000fbd6  js      short loc_18000FBF9
0x18000fbd8  mov     rcx, [rsp+38h+arg_8]
0x18000fbdd  mov     rdx, [rsp+38h+arg_10]
0x18000fbe2  jmp     short loc_18000FBE9
0x18000fbe4  mov     eax, 1
0x18000fbe9  test    rdi, rdi
0x18000fbec  jz      short loc_18000FBF1
0x18000fbee  mov     [rdi], rcx
0x18000fbf1  test    rbx, rbx
0x18000fbf4  jz      short loc_18000FBF9
0x18000fbf6  mov     [rbx], rdx
0x18000fbf9  mov     rbx, [rsp+38h+arg_0]
0x18000fbfe  mov     rsi, [rsp+38h+arg_18]
0x18000fc03  add     rsp, 30h
0x18000fc07  pop     rdi
0x18000fc08  retn
```
