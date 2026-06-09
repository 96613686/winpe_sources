# IsCNRAvailable(_cnrlink const *)

- ea: `0x1800048ec`
- end: `0x1800049d3`
- name: `?IsCNRAvailable@@YAHPEBU_cnrlink@@@Z`
- size: `231`
- prototype: `_BOOL8 __fastcall(const struct _cnrlink *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180005240`

## callees

- `0x180001ae0`
- `0x180001bd0`
- `0x1800048ec`
- `0x180005750`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000498d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000498d`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000497a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800049a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x18000497a`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800049a3`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004941`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180004941`

## pseudocode

```c
_BOOL8 __fastcall IsCNRAvailable(const struct _cnrlink *a1)
{
  const CHAR *v1; // r8
  WCHAR *v2; // rbx
  UINT v3; // edi
  BOOL v4; // ebx
  WCHAR FileName[264]; // [rsp+30h] [rbp-438h] BYREF
  WCHAR WideCharStr[264]; // [rsp+240h] [rbp-228h] BYREF

  v1 = (char *)a1 + *((unsigned int *)a1 + 2);
  if ( v1 == (char *)a1 + 20 )
  {
    v2 = WideCharStr;
    MultiByteToWideChar(0, 0, v1, -1, WideCharStr, 260);
  }
  else
  {
    v2 = (WCHAR *)((char *)a1 + *((unsigned int *)a1 + 5));
  }
  StringCchCopyW(FileName, 0x104u, v2);
  CatPath(FileName, L"\\");
  v3 = SetErrorMode(1u);
  v4 = GetFileAttributesW(FileName) != -1;
  SetErrorMode(v3);
  return v4;
}

```

## disassembly

```asm
0x1800048ec  mov     [rsp+arg_8], rbx
0x1800048f1  push    rdi
0x1800048f2  sub     rsp, 460h
0x1800048f9  mov     rax, cs:__security_cookie
0x180004900  xor     rax, rsp
0x180004903  mov     [rsp+468h+var_18], rax
0x18000490b  mov     r8d, [rcx+8]
0x18000490f  lea     rax, [rcx+14h]
0x180004913  add     r8, rcx; lpMultiByteStr
0x180004916  mov     edi, 104h
0x18000491b  cmp     r8, rax
0x18000491e  jnz     short loc_18000494F
0x180004920  lea     rax, [rsp+468h+WideCharStr]
0x180004928  mov     [rsp+468h+cchWideChar], edi; cchWideChar
0x18000492c  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180004930  mov     [rsp+468h+lpWideCharStr], rax; lpWideCharStr
0x180004935  xor     edx, edx; dwFlags
0x180004937  lea     rbx, [rsp+468h+WideCharStr]
0x18000493f  xor     ecx, ecx; CodePage
0x180004941  call    cs:__imp_MultiByteToWideChar
0x180004948  nop     dword ptr [rax+rax+00h]
0x18000494d  jmp     short loc_180004954
0x18000494f  mov     ebx, [rax]
0x180004951  add     rbx, rcx
0x180004954  mov     r8, rbx; unsigned __int16 *
0x180004957  lea     rcx, [rsp+468h+FileName]; unsigned __int16 *
0x18000495c  mov     rdx, rdi; unsigned __int64
0x18000495f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004964  lea     rdx, asc_180006504; "\\"
0x18000496b  lea     rcx, [rsp+468h+FileName]; unsigned __int16 *
0x180004970  call    ?CatPath@@YAJPEAGPEBGH@Z; CatPath(ushort *,ushort const *,int)
0x180004975  mov     ecx, 1; uMode
0x18000497a  call    cs:__imp_SetErrorMode
0x180004981  nop     dword ptr [rax+rax+00h]
0x180004986  lea     rcx, [rsp+468h+FileName]; lpFileName
0x18000498b  mov     edi, eax
0x18000498d  call    cs:__imp_GetFileAttributesW
0x180004994  nop     dword ptr [rax+rax+00h]
0x180004999  xor     ebx, ebx
0x18000499b  mov     ecx, edi; uMode
0x18000499d  cmp     eax, 0FFFFFFFFh
0x1800049a0  setnz   bl
0x1800049a3  call    cs:__imp_SetErrorMode
0x1800049aa  nop     dword ptr [rax+rax+00h]
0x1800049af  mov     eax, ebx
0x1800049b1  mov     rcx, [rsp+468h+var_18]
0x1800049b9  xor     rcx, rsp; StackCookie
0x1800049bc  call    __security_check_cookie
0x1800049c1  mov     rbx, [rsp+468h+arg_8]
0x1800049c9  add     rsp, 460h
0x1800049d0  pop     rdi
0x1800049d1  retn
```
