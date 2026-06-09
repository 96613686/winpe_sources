# VerifyDirectoryPath(ushort *)

- ea: `0x18001ec34`
- end: `0x18001ecd5`
- name: `?VerifyDirectoryPath@@YAHPEAG@Z`
- size: `161`
- prototype: `__int64 __fastcall(LPCWSTR lpSrc)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001e308`

## callees

- `0x18000be40`
- `0x18000c7e8`
- `0x18001ec34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec9d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ec8b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001ec8b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ec7c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001ec7c`

## pseudocode

```c
__int64 __fastcall VerifyDirectoryPath(LPCWSTR lpSrc)
{
  unsigned int v2; // edi
  DWORD FileAttributesW; // eax
  DWORD LastError; // eax
  WCHAR Dst[2]; // [rsp+20h] [rbp-228h] BYREF
  _BYTE v7[524]; // [rsp+24h] [rbp-224h] BYREF

  v2 = 0;
  *(_DWORD *)Dst = 0;
  memset_0(v7, 0, 0x204u);
  if ( ExpandEnvironmentStringsW(lpSrc, Dst, 0x104u) )
  {
    FileAttributesW = GetFileAttributesW(Dst);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      if ( LastError == 5 || LastError == 32 )
        return 1;
    }
    else
    {
      return FileAttributesW & 0x10;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001ec34  mov     [rsp+arg_8], rbx
0x18001ec39  push    rdi
0x18001ec3a  sub     rsp, 240h
0x18001ec41  mov     rax, cs:__security_cookie
0x18001ec48  xor     rax, rsp
0x18001ec4b  mov     [rsp+248h+var_18], rax
0x18001ec53  mov     rbx, rcx
0x18001ec56  xor     edi, edi
0x18001ec58  lea     rcx, [rsp+248h+var_224]; void *
0x18001ec5d  mov     dword ptr [rsp+248h+Dst], edi
0x18001ec61  xor     edx, edx; Val
0x18001ec63  mov     r8d, 204h; Size
0x18001ec69  call    memset_0
0x18001ec6e  mov     r8d, 104h; nSize
0x18001ec74  lea     rdx, [rsp+248h+Dst]; lpDst
0x18001ec79  mov     rcx, rbx; lpSrc
0x18001ec7c  call    cs:__imp_ExpandEnvironmentStringsW
0x18001ec82  test    eax, eax
0x18001ec84  jz      short loc_18001ECB2
0x18001ec86  lea     rcx, [rsp+248h+Dst]; lpFileName
0x18001ec8b  call    cs:__imp_GetFileAttributesW
0x18001ec91  cmp     eax, 0FFFFFFFFh
0x18001ec94  jz      short loc_18001EC9D
0x18001ec96  mov     edi, eax
0x18001ec98  and     edi, 10h
0x18001ec9b  jmp     short loc_18001ECB2
0x18001ec9d  call    cs:__imp_GetLastError
0x18001eca3  cmp     eax, 5
0x18001eca6  jz      short loc_18001ECAD
0x18001eca8  cmp     eax, 20h ; ' '
0x18001ecab  jnz     short loc_18001ECB2
0x18001ecad  mov     edi, 1
0x18001ecb2  mov     eax, edi
0x18001ecb4  mov     rcx, [rsp+248h+var_18]
0x18001ecbc  xor     rcx, rsp; StackCookie
0x18001ecbf  call    __security_check_cookie
0x18001ecc4  mov     rbx, [rsp+248h+arg_8]
0x18001eccc  add     rsp, 240h
0x18001ecd3  pop     rdi
0x18001ecd4  retn
```
