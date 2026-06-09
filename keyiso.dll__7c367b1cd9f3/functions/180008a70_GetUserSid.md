# GetUserSid

- ea: `0x180008a70`
- end: `0x180008b3e`
- name: `GetUserSid`
- size: `206`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800081ec`
- `0x180008954`

## callees

- `0x180008a70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008b11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008aab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008aab`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008a9b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008ad3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008a9b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180008ad3`

## pseudocode

```c
__int64 __fastcall GetUserSid(HANDLE TokenHandle, _QWORD *a2)
{
  HLOCAL v4; // rdi
  unsigned int v5; // ebx
  signed int LastError; // eax
  signed int v8; // eax
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength)
    || (v8 = GetLastError(), v5 = v8, v8 == 122) )
  {
    v4 = LocalAlloc(0, TokenInformationLength);
    if ( v4 )
    {
      if ( GetTokenInformation(TokenHandle, TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
      {
        v5 = 0;
        *a2 = v4;
      }
      else
      {
        GetLastError();
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        LocalFree(v4);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else if ( v8 > 0 )
  {
    return (unsigned __int16)v8 | 0x80070000;
  }
  return v5;
}

```

## disassembly

```asm
0x180008a70  push    rbx
0x180008a72  push    rbp
0x180008a73  push    rsi
0x180008a74  push    rdi
0x180008a75  sub     rsp, 38h
0x180008a79  xor     r9d, r9d; TokenInformationLength
0x180008a7c  mov     [rsp+58h+TokenInformationLength], 0
0x180008a84  mov     rsi, rdx
0x180008a87  lea     rax, [rsp+58h+TokenInformationLength]
0x180008a8c  xor     r8d, r8d; TokenInformation
0x180008a8f  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180008a94  mov     rbp, rcx
0x180008a97  lea     edx, [r9+1]; TokenInformationClass
0x180008a9b  call    cs:__imp_GetTokenInformation
0x180008aa1  test    eax, eax
0x180008aa3  jz      short loc_180008B19
0x180008aa5  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x180008aa9  xor     ecx, ecx; uFlags
0x180008aab  call    cs:__imp_LocalAlloc
0x180008ab1  mov     rdi, rax
0x180008ab4  test    rax, rax
0x180008ab7  jz      short loc_180008B2C
0x180008ab9  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180008abe  lea     rax, [rsp+58h+TokenInformationLength]
0x180008ac3  mov     r8, rdi; TokenInformation
0x180008ac6  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180008acb  mov     edx, 1; TokenInformationClass
0x180008ad0  mov     rcx, rbp; TokenHandle
0x180008ad3  call    cs:__imp_GetTokenInformation
0x180008ad9  test    eax, eax
0x180008adb  jz      short loc_180008AFC
0x180008add  xor     ebx, ebx
0x180008adf  mov     [rsi], rdi
0x180008ae2  mov     eax, ebx
0x180008ae4  add     rsp, 38h
0x180008ae8  pop     rdi
0x180008ae9  pop     rsi
0x180008aea  pop     rbp
0x180008aeb  pop     rbx
0x180008aec  retn
0x180008aed  test    eax, eax
0x180008aef  jle     short loc_180008AE2
0x180008af1  movzx   ebx, ax
0x180008af4  or      ebx, 80070000h
0x180008afa  jmp     short loc_180008AE2
0x180008afc  call    cs:__imp_GetLastError
0x180008b02  call    cs:__imp_GetLastError
0x180008b08  mov     ebx, eax
0x180008b0a  test    eax, eax
0x180008b0c  jg      short loc_180008B33
0x180008b0e  mov     rcx, rdi; hMem
0x180008b11  call    cs:__imp_LocalFree
0x180008b17  jmp     short loc_180008AE2
0x180008b19  call    cs:__imp_GetLastError
0x180008b1f  mov     ebx, eax
0x180008b21  cmp     eax, 7Ah ; 'z'
0x180008b24  jz      loc_180008AA5
0x180008b2a  jmp     short loc_180008AED
0x180008b2c  mov     ebx, 8007000Eh
0x180008b31  jmp     short loc_180008AE2
0x180008b33  movzx   ebx, ax
0x180008b36  or      ebx, 80070000h
0x180008b3c  jmp     short loc_180008B0E
```
