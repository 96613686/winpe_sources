# AccGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void * *)

- ea: `0x18001ce64`
- end: `0x18001cf76`
- name: `?AccGetTokenInformation@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z`
- size: `274`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, enum _TOKEN_INFORMATION_CLASS, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180045ad8`

## callees

- `0x18001ce64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cf5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cf5a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cee9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001cee9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ceac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cf20`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001ceac`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cf20`

## pseudocode

```c
__int64 __fastcall AccGetTokenInformation(HANDLE TokenHandle, DWORD a2, void **a3)
{
  signed int v6; // ebx
  signed int LastError; // eax
  HLOCAL v8; // rdi
  signed int v9; // eax
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+60h] [rbp+18h] BYREF

  TokenInformationLength = a2;
  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
    return (unsigned int)-2147418113;
  v6 = 0;
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    else
      v6 = LastError;
  }
  if ( v6 < 0 )
    return (unsigned int)v6;
  v8 = LocalAlloc(0x40u, TokenInformationLength);
  if ( v8 )
  {
    ReturnLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v8, TokenInformationLength, &ReturnLength) )
    {
      if ( ReturnLength == TokenInformationLength )
      {
LABEL_15:
        *a3 = v8;
        return (unsigned int)v6;
      }
      v6 = -2147418113;
    }
    else
    {
      v9 = GetLastError();
      v6 = v9;
      if ( v9 > 0 )
        v6 = (unsigned __int16)v9 | 0x80070000;
      if ( v6 >= 0 )
        goto LABEL_15;
    }
    LocalFree(v8);
    return (unsigned int)v6;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x18001ce64  mov     [rsp+arg_0], rbx
0x18001ce69  mov     [rsp+TokenInformationLength], edx
0x18001ce6d  push    rbp
0x18001ce6e  push    rsi
0x18001ce6f  push    rdi
0x18001ce70  sub     rsp, 30h
0x18001ce74  mov     rsi, r8
0x18001ce77  mov     rbp, rcx
0x18001ce7a  test    r8, r8
0x18001ce7d  jnz     short loc_18001CE89
0x18001ce7f  mov     eax, 80070057h
0x18001ce84  jmp     loc_18001CF69
0x18001ce89  xor     r9d, r9d; TokenInformationLength
0x18001ce8c  mov     qword ptr [r8], 0
0x18001ce93  lea     rax, [rsp+48h+TokenInformationLength]
0x18001ce98  mov     [rsp+48h+TokenInformationLength], 0
0x18001cea0  xor     r8d, r8d; TokenInformation
0x18001cea3  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001cea8  lea     edx, [r9+19h]; TokenInformationClass
0x18001ceac  call    cs:__imp_GetTokenInformation
0x18001ceb2  test    eax, eax
0x18001ceb4  jnz     loc_18001CF62
0x18001ceba  xor     ebx, ebx
0x18001cebc  call    cs:__imp_GetLastError
0x18001cec2  cmp     eax, 7Ah ; 'z'
0x18001cec5  jz      short loc_18001CED8
0x18001cec7  test    eax, eax
0x18001cec9  jg      short loc_18001CECF
0x18001cecb  mov     ebx, eax
0x18001cecd  jmp     short loc_18001CED8
0x18001cecf  movzx   ebx, ax
0x18001ced2  or      ebx, 80070000h
0x18001ced8  test    ebx, ebx
0x18001ceda  js      loc_18001CF67
0x18001cee0  mov     edx, [rsp+48h+TokenInformationLength]; uBytes
0x18001cee4  mov     ecx, 40h ; '@'; uFlags
0x18001cee9  call    cs:__imp_LocalAlloc
0x18001ceef  mov     rdi, rax
0x18001cef2  test    rax, rax
0x18001cef5  jnz     short loc_18001CEFE
0x18001cef7  mov     ebx, 8007000Eh
0x18001cefc  jmp     short loc_18001CF67
0x18001cefe  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18001cf03  lea     rax, [rsp+48h+arg_10]
0x18001cf08  mov     r8, rdi; TokenInformation
0x18001cf0b  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001cf10  mov     edx, 19h; TokenInformationClass
0x18001cf15  mov     [rsp+48h+arg_10], 0
0x18001cf1d  mov     rcx, rbp; TokenHandle
0x18001cf20  call    cs:__imp_GetTokenInformation
0x18001cf26  test    eax, eax
0x18001cf28  jnz     short loc_18001CF48
0x18001cf2a  call    cs:__imp_GetLastError
0x18001cf30  mov     ebx, eax
0x18001cf32  test    eax, eax
0x18001cf34  jle     short loc_18001CF3F
0x18001cf36  movzx   ebx, ax
0x18001cf39  or      ebx, 80070000h
0x18001cf3f  test    ebx, ebx
0x18001cf41  js      short loc_18001CF57
0x18001cf43  mov     [rsi], rdi
0x18001cf46  jmp     short loc_18001CF67
0x18001cf48  mov     eax, [rsp+48h+TokenInformationLength]
0x18001cf4c  cmp     [rsp+48h+arg_10], eax
0x18001cf50  jz      short loc_18001CF43
0x18001cf52  mov     ebx, 8000FFFFh
0x18001cf57  mov     rcx, rdi; hMem
0x18001cf5a  call    cs:__imp_LocalFree
0x18001cf60  jmp     short loc_18001CF67
0x18001cf62  mov     ebx, 8000FFFFh
0x18001cf67  mov     eax, ebx
0x18001cf69  mov     rbx, [rsp+48h+arg_0]
0x18001cf6e  add     rsp, 30h
0x18001cf72  pop     rdi
0x18001cf73  pop     rsi
0x18001cf74  pop     rbp
0x18001cf75  retn
```
