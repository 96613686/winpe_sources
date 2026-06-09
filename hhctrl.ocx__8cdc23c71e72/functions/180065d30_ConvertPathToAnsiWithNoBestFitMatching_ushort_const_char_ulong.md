# ConvertPathToAnsiWithNoBestFitMatching(ushort const *,char *,ulong)

- ea: `0x180065d30`
- end: `0x180065e49`
- name: `?ConvertPathToAnsiWithNoBestFitMatching@@YA_NPEBGPEADK@Z`
- size: `281`
- prototype: `bool __fastcall(LPCWSTR lpszLongPath, LPSTR lpMultiByteStr, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180055060`
- `0x180067b00`
- `0x180067c20`
- `0x1800696e0`

## callees

- `0x180065d30`
- `0x180075c90`

## import_xrefs

- `KERNEL32!GetShortPathNameW` at `0x180065dce`
- `KERNEL32!GetShortPathNameW` at `0x180065dce`
- `KERNEL32!WideCharToMultiByte` at `0x180065da3`
- `KERNEL32!WideCharToMultiByte` at `0x180065e0b`
- `KERNEL32!WideCharToMultiByte` at `0x180065da3`
- `KERNEL32!WideCharToMultiByte` at `0x180065e0b`

## pseudocode

```c
bool __fastcall ConvertPathToAnsiWithNoBestFitMatching(LPCWSTR lpszLongPath, LPSTR lpMultiByteStr, int cbMultiByte)
{
  __int64 v3; // rbx
  int v6; // eax
  DWORD ShortPathNameW; // eax
  int v9; // eax
  WINBOOL UsedDefaultChar[4]; // [rsp+40h] [rbp-248h] BYREF
  WCHAR szShortPath[264]; // [rsp+50h] [rbp-238h] BYREF

  v3 = cbMultiByte;
  if ( !lpszLongPath || !lpMultiByteStr || !cbMultiByte )
    return 0;
  UsedDefaultChar[0] = 0;
  v6 = WideCharToMultiByte(0, 0x400u, lpszLongPath, -1, lpMultiByteStr, cbMultiByte, 0, UsedDefaultChar);
  if ( (int)v3 > 0 )
    lpMultiByteStr[v3 - 1] = 0;
  if ( v6 && !UsedDefaultChar[0] )
    return 1;
  ShortPathNameW = GetShortPathNameW(lpszLongPath, szShortPath, 0x104u);
  if ( ShortPathNameW - 1 > 0x103 )
    return 0;
  UsedDefaultChar[0] = 0;
  v9 = WideCharToMultiByte(0, 0x400u, szShortPath, ShortPathNameW + 1, lpMultiByteStr, v3, 0, UsedDefaultChar);
  if ( (int)v3 > 0 )
    lpMultiByteStr[v3 - 1] = 0;
  return v9 && !UsedDefaultChar[0];
}

```

## disassembly

```asm
0x180065d30  mov     [rsp+arg_18], rbx
0x180065d35  push    rbp
0x180065d36  push    rsi
0x180065d37  push    rdi
0x180065d38  sub     rsp, 270h
0x180065d3f  mov     rax, cs:__security_cookie
0x180065d46  xor     rax, rsp
0x180065d49  mov     [rsp+288h+var_28], rax
0x180065d51  movsxd  rbx, r8d
0x180065d54  mov     rdi, rdx
0x180065d57  mov     rsi, rcx
0x180065d5a  test    rcx, rcx
0x180065d5d  jz      loc_180065E24
0x180065d63  test    rdx, rdx
0x180065d66  jz      loc_180065E24
0x180065d6c  test    r8d, r8d
0x180065d6f  jz      loc_180065E24
0x180065d75  lea     rax, [rsp+288h+UsedDefaultChar]
0x180065d7a  xor     ebp, ebp
0x180065d7c  mov     [rsp+288h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180065d81  mov     r8, rcx; lpWideCharStr
0x180065d84  mov     [rsp+288h+lpDefaultChar], rbp; lpDefaultChar
0x180065d89  mov     r9d, 0FFFFFFFFh; cchWideChar
0x180065d8f  mov     [rsp+288h+cbMultiByte], ebx; cbMultiByte
0x180065d93  xor     ecx, ecx; CodePage
0x180065d95  mov     [rsp+288h+lpMultiByteStr], rdx; lpMultiByteStr
0x180065d9a  mov     edx, 400h; dwFlags
0x180065d9f  mov     [rsp+288h+UsedDefaultChar], ebp
0x180065da3  call    cs:__imp_WideCharToMultiByte
0x180065da9  test    ebx, ebx
0x180065dab  jle     short loc_180065DB2
0x180065dad  mov     [rbx+rdi-1], bpl
0x180065db2  test    eax, eax
0x180065db4  jz      short loc_180065DC0
0x180065db6  cmp     [rsp+288h+UsedDefaultChar], ebp
0x180065dba  jnz     short loc_180065DC0
0x180065dbc  mov     al, 1
0x180065dbe  jmp     short loc_180065E26
0x180065dc0  mov     r8d, 104h; cchBuffer
0x180065dc6  lea     rdx, [rsp+288h+szShortPath]; lpszShortPath
0x180065dcb  mov     rcx, rsi; lpszLongPath
0x180065dce  call    cs:__imp_GetShortPathNameW
0x180065dd4  lea     ecx, [rax-1]
0x180065dd7  cmp     ecx, 103h
0x180065ddd  ja      short loc_180065E24
0x180065ddf  lea     r9d, [rax+1]; cchWideChar
0x180065de3  mov     [rsp+288h+UsedDefaultChar], ebp
0x180065de7  lea     rax, [rsp+288h+UsedDefaultChar]
0x180065dec  mov     edx, 400h; dwFlags
0x180065df1  mov     [rsp+288h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x180065df6  lea     r8, [rsp+288h+szShortPath]; lpWideCharStr
0x180065dfb  mov     [rsp+288h+lpDefaultChar], rbp; lpDefaultChar
0x180065e00  xor     ecx, ecx; CodePage
0x180065e02  mov     [rsp+288h+cbMultiByte], ebx; cbMultiByte
0x180065e06  mov     [rsp+288h+lpMultiByteStr], rdi; lpMultiByteStr
0x180065e0b  call    cs:__imp_WideCharToMultiByte
0x180065e11  test    ebx, ebx
0x180065e13  jle     short loc_180065E1A
0x180065e15  mov     [rbx+rdi-1], bpl
0x180065e1a  test    eax, eax
0x180065e1c  jz      short loc_180065E24
0x180065e1e  cmp     [rsp+288h+UsedDefaultChar], ebp
0x180065e22  jz      short loc_180065DBC
0x180065e24  xor     al, al
0x180065e26  mov     rcx, [rsp+288h+var_28]
0x180065e2e  xor     rcx, rsp; StackCookie
0x180065e31  call    __security_check_cookie
0x180065e36  mov     rbx, [rsp+288h+arg_18]
0x180065e3e  add     rsp, 270h
0x180065e45  pop     rdi
0x180065e46  pop     rsi
0x180065e47  pop     rbp
0x180065e48  retn
```
