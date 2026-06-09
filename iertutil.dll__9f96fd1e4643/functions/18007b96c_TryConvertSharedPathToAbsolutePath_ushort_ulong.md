# TryConvertSharedPathToAbsolutePath(ushort *,ulong *)

- ea: `0x18007b96c`
- end: `0x18007ba9c`
- name: `?TryConvertSharedPathToAbsolutePath@@YAHPEAGPEAK@Z`
- size: `304`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180027178`

## callees

- `0x180028610`
- `0x180031670`
- `0x18007b96c`
- `0x180083c10`

## import_xrefs

- `KERNELBASE!StrChrW` at `0x18007b9bf`
- `KERNELBASE!StrChrW` at `0x18007b9bf`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18007ba32`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18007ba32`
- `srvcli!NetShareGetInfo` at `0x18007ba0c`
- `srvcli!NetShareGetInfo` at `0x18007ba0c`
- `netutils!NetApiBufferFree` at `0x18007ba3f`
- `netutils!NetApiBufferFree` at `0x18007ba3f`

## pseudocode

```c
__int64 __fastcall TryConvertSharedPathToAbsolutePath(unsigned __int16 *a1, unsigned int *a2)
{
  PWSTR v4; // rax
  PWSTR v5; // rbx
  HRESULT v6; // ebx
  __int64 v7; // rax
  LPBYTE bufptr; // [rsp+30h] [rbp-458h] BYREF
  WCHAR netname[264]; // [rsp+40h] [rbp-448h] BYREF
  WCHAR pszPathOut[264]; // [rsp+250h] [rbp-238h] BYREF

  if ( !a1 )
    return 0;
  if ( !a2 )
    return 0;
  if ( *a1 != 92 )
    return 0;
  v4 = StrChrW(a1 + 1, 0x5Cu);
  v5 = v4;
  if ( !v4 )
    return 0;
  if ( (int)StringCchCopyNW(netname, 0x104u, a1 + 1, ((char *)v4 - (char *)a1 - 2) >> 1) < 0 )
    return 0;
  bufptr = 0;
  if ( NetShareGetInfo(0, netname, 2u, &bufptr) )
    return 0;
  v6 = PathCchCombineEx(pszPathOut, 0x104u, *((PCWSTR *)bufptr + 5), v5 + 1, 0);
  NetApiBufferFree(bufptr);
  if ( v6 < 0 )
    return 0;
  StringCchCopyW(a1, 0x104u, pszPathOut);
  v7 = -1;
  do
    ++v7;
  while ( a1[v7] );
  *a2 = v7;
  return 1;
}

```

## disassembly

```asm
0x18007b96c  mov     [rsp+arg_10], rbx
0x18007b971  mov     [rsp+arg_18], rbp
0x18007b976  push    rsi
0x18007b977  push    rdi
0x18007b978  push    r14
0x18007b97a  sub     rsp, 470h
0x18007b981  mov     rax, cs:__security_cookie
0x18007b988  xor     rax, rsp
0x18007b98b  mov     [rsp+488h+var_28], rax
0x18007b993  xor     r14d, r14d
0x18007b996  mov     rsi, rdx
0x18007b999  mov     rdi, rcx
0x18007b99c  test    rcx, rcx
0x18007b99f  jz      loc_18007BA72
0x18007b9a5  test    rdx, rdx
0x18007b9a8  jz      loc_18007BA72
0x18007b9ae  lea     edx, [r14+5Ch]; wMatch
0x18007b9b2  cmp     [rcx], dx
0x18007b9b5  jnz     loc_18007BA72
0x18007b9bb  add     rcx, 2; pszStart
0x18007b9bf  call    cs:__imp_StrChrW
0x18007b9c5  mov     rbx, rax
0x18007b9c8  test    rax, rax
0x18007b9cb  jz      loc_18007BA72
0x18007b9d1  mov     r9, rax
0x18007b9d4  lea     r8, [rdi+2]; unsigned __int16 *
0x18007b9d8  sub     r9, rdi
0x18007b9db  lea     rcx, [rsp+488h+netname]; unsigned __int16 *
0x18007b9e0  sub     r9, 2
0x18007b9e4  mov     ebp, 104h
0x18007b9e9  sar     r9, 1; unsigned __int64
0x18007b9ec  mov     edx, ebp; unsigned __int64
0x18007b9ee  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18007b9f3  test    eax, eax
0x18007b9f5  js      short loc_18007BA72
0x18007b9f7  lea     r9, [rsp+488h+bufptr]; bufptr
0x18007b9fc  mov     [rsp+488h+bufptr], r14
0x18007ba01  lea     r8d, [r14+2]; level
0x18007ba05  xor     ecx, ecx; servername
0x18007ba07  lea     rdx, [rsp+488h+netname]; netname
0x18007ba0c  call    cs:__imp_NetShareGetInfo
0x18007ba12  test    eax, eax
0x18007ba14  jnz     short loc_18007BA72
0x18007ba16  mov     r8, [rsp+488h+bufptr]
0x18007ba1b  lea     r9, [rbx+2]; pszMore
0x18007ba1f  mov     edx, ebp; cchPathOut
0x18007ba21  mov     [rsp+488h+dwFlags], r14d; dwFlags
0x18007ba26  lea     rcx, [rsp+488h+pszPathOut]; pszPathOut
0x18007ba2e  mov     r8, [r8+28h]; pszPathIn
0x18007ba32  call    cs:__imp_PathCchCombineEx
0x18007ba38  mov     rcx, [rsp+488h+bufptr]; Buffer
0x18007ba3d  mov     ebx, eax
0x18007ba3f  call    cs:__imp_NetApiBufferFree
0x18007ba45  test    ebx, ebx
0x18007ba47  js      short loc_18007BA72
0x18007ba49  lea     r8, [rsp+488h+pszPathOut]; unsigned __int16 *
0x18007ba51  mov     edx, ebp; unsigned __int64
0x18007ba53  mov     rcx, rdi; unsigned __int16 *
0x18007ba56  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007ba5b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007ba5f  inc     rax
0x18007ba62  cmp     [rdi+rax*2], r14w
0x18007ba67  jnz     short loc_18007BA5F
0x18007ba69  mov     [rsi], eax
0x18007ba6b  mov     eax, 1
0x18007ba70  jmp     short loc_18007BA74
0x18007ba72  xor     eax, eax
0x18007ba74  mov     rcx, [rsp+488h+var_28]
0x18007ba7c  xor     rcx, rsp; StackCookie
0x18007ba7f  call    __security_check_cookie
0x18007ba84  lea     r11, [rsp+488h+var_18]
0x18007ba8c  mov     rbx, [r11+30h]
0x18007ba90  mov     rbp, [r11+38h]
0x18007ba94  mov     rsp, r11
0x18007ba97  pop     r14
0x18007ba99  pop     rdi
0x18007ba9a  pop     rsi
0x18007ba9b  retn
```
