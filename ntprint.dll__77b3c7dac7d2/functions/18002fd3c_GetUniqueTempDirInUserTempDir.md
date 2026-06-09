# GetUniqueTempDirInUserTempDir

- ea: `0x18002fd3c`
- end: `0x18002fe0e`
- name: `GetUniqueTempDirInUserTempDir`
- size: `210`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000908c`
- `0x18002e630`

## callees

- `0x180002300`
- `0x180018d18`
- `0x18002fd3c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002fdc5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002fdc5`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002fd72`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18002fd72`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002fdd8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002fdd8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002fdf2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002fdf2`

## pseudocode

```c
HRESULT __fastcall GetUniqueTempDirInUserTempDir(WCHAR *lpPathName)
{
  HRESULT result; // eax
  __int64 v3; // rbx
  __int64 v4; // rax
  GUID pguid; // [rsp+20h] [rbp-48h] BYREF

  if ( !lpPathName )
    return -2147024809;
  if ( GetTempPathW(0x104u, lpPathName) - 1 > 0x103 )
  {
    LODWORD(v3) = 0;
    result = GetLastErrorAsHResult();
    if ( result < 0 )
      return result;
  }
  else
  {
    v3 = -1;
    do
      ++v3;
    while ( lpPathName[v3] );
    if ( (_DWORD)v3 && lpPathName[(unsigned int)(v3 - 1)] != 92 )
    {
      if ( (unsigned int)v3 >= 0x103 )
        return -2147024809;
      v4 = (unsigned int)v3;
      LODWORD(v3) = v3 + 1;
      lpPathName[v4] = 92;
      lpPathName[(unsigned int)v3] = 0;
    }
  }
  CreateDirectoryW(lpPathName, 0);
  pguid = 0;
  result = CoCreateGuid(&pguid);
  if ( result >= 0 )
    return StringFromGUID2(&pguid, &lpPathName[(unsigned int)v3], 260 - v3);
  return result;
}

```

## disassembly

```asm
0x18002fd3c  push    rbx
0x18002fd3e  push    rbp
0x18002fd3f  push    rsi
0x18002fd40  push    rdi
0x18002fd41  sub     rsp, 48h
0x18002fd45  mov     rax, cs:__security_cookie
0x18002fd4c  xor     rax, rsp
0x18002fd4f  mov     [rsp+68h+var_38], rax
0x18002fd54  xor     ebp, ebp
0x18002fd56  mov     rdi, rcx
0x18002fd59  test    rcx, rcx
0x18002fd5c  jnz     short loc_18002FD68
0x18002fd5e  mov     eax, 80070057h
0x18002fd63  jmp     loc_18002FDF8
0x18002fd68  mov     esi, 104h
0x18002fd6d  mov     rdx, rdi; lpBuffer
0x18002fd70  mov     ecx, esi; nBufferLength
0x18002fd72  call    cs:__imp_GetTempPathW
0x18002fd78  dec     eax
0x18002fd7a  lea     r8d, [rsi-1]
0x18002fd7e  cmp     eax, r8d
0x18002fd81  ja      short loc_18002FDB5
0x18002fd83  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002fd87  inc     rbx
0x18002fd8a  cmp     [rdi+rbx*2], bp
0x18002fd8e  jnz     short loc_18002FD87
0x18002fd90  test    ebx, ebx
0x18002fd92  jz      short loc_18002FDC0
0x18002fd94  lea     eax, [rbx-1]
0x18002fd97  mov     edx, 5Ch ; '\'
0x18002fd9c  cmp     [rdi+rax*2], dx
0x18002fda0  jz      short loc_18002FDC0
0x18002fda2  cmp     ebx, r8d
0x18002fda5  jnb     short loc_18002FD5E
0x18002fda7  mov     eax, ebx
0x18002fda9  inc     ebx
0x18002fdab  mov     [rdi+rax*2], dx
0x18002fdaf  mov     [rdi+rbx*2], bp
0x18002fdb3  jmp     short loc_18002FDC0
0x18002fdb5  mov     ebx, ebp
0x18002fdb7  call    GetLastErrorAsHResult
0x18002fdbc  test    eax, eax
0x18002fdbe  js      short loc_18002FDF8
0x18002fdc0  xor     edx, edx; lpSecurityAttributes
0x18002fdc2  mov     rcx, rdi; lpPathName
0x18002fdc5  call    cs:__imp_CreateDirectoryW
0x18002fdcb  xorps   xmm0, xmm0
0x18002fdce  lea     rcx, [rsp+68h+pguid]; pguid
0x18002fdd3  movups  xmmword ptr [rsp+68h+pguid.Data1], xmm0
0x18002fdd8  call    cs:__imp_CoCreateGuid
0x18002fdde  test    eax, eax
0x18002fde0  js      short loc_18002FDF8
0x18002fde2  mov     eax, ebx
0x18002fde4  lea     rcx, [rsp+68h+pguid]; rguid
0x18002fde9  sub     esi, ebx
0x18002fdeb  mov     r8d, esi; cchMax
0x18002fdee  lea     rdx, [rdi+rax*2]; lpsz
0x18002fdf2  call    cs:__imp_StringFromGUID2
0x18002fdf8  mov     rcx, [rsp+68h+var_38]
0x18002fdfd  xor     rcx, rsp; StackCookie
0x18002fe00  call    __security_check_cookie
0x18002fe05  add     rsp, 48h
0x18002fe09  pop     rdi
0x18002fe0a  pop     rsi
0x18002fe0b  pop     rbp
0x18002fe0c  pop     rbx
0x18002fe0d  retn
```
