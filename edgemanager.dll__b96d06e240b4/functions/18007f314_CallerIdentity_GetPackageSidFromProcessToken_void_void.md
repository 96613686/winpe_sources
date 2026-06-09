# CallerIdentity::GetPackageSidFromProcessToken(void *,void * *)

- ea: `0x18007f314`
- end: `0x18007f43d`
- name: `?GetPackageSidFromProcessToken@CallerIdentity@@YAJPEAXPEAPEAX@Z`
- size: `297`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180027154`

## callees

- `0x18007f314`
- `0x18007f444`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f354`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007f422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007f42b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007f422`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007f42b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007f37f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007f3e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007f37f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007f3e4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007f340`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007f3b1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007f340`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18007f3b1`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007f3d5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18007f3d5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007f401`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18007f401`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetPackageSidFromProcessToken(HANDLE TokenHandle, _QWORD *a2, void **a3)
{
  signed int Error; // ebx
  signed int LastError; // eax
  PSID *v7; // rdi
  DWORD LengthSid; // ebx
  HLOCAL v9; // rax
  void *v10; // rsi
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength) )
    return (unsigned int)-2147418113;
  LastError = GetLastError();
  Error = LastError;
  if ( LastError == 122 )
    goto LABEL_24;
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
  if ( Error >= 0 )
  {
LABEL_24:
    v7 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
    if ( !v7 )
      return (unsigned int)-2147024882;
    if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, v7, TokenInformationLength, &TokenInformationLength)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      if ( *v7 )
      {
        LengthSid = GetLengthSid(*v7);
        v9 = LocalAlloc(0x40u, LengthSid);
        v10 = v9;
        if ( v9 )
        {
          if ( CopySid(LengthSid, v9, *v7) )
          {
            Error = 0;
          }
          else
          {
            Error = ResultFromKnownLastError();
            if ( Error < 0 )
            {
              LocalFree(v10);
              goto LABEL_20;
            }
          }
          *a2 = v10;
        }
        else
        {
          Error = -2147024882;
        }
      }
      else
      {
        Error = -2147023728;
      }
LABEL_20:
      LocalFree(v7);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18007f314  push    rbx
0x18007f316  push    rsi
0x18007f317  push    rdi
0x18007f318  push    r14
0x18007f31a  sub     rsp, 38h
0x18007f31e  xor     r9d, r9d; TokenInformationLength
0x18007f321  mov     [rsp+58h+TokenInformationLength], 0
0x18007f329  mov     r14, rdx
0x18007f32c  lea     rax, [rsp+58h+TokenInformationLength]
0x18007f331  xor     r8d, r8d; TokenInformation
0x18007f334  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18007f339  mov     rsi, rcx
0x18007f33c  lea     edx, [r9+1Fh]; TokenInformationClass
0x18007f340  call    cs:__imp_GetTokenInformation
0x18007f346  test    eax, eax
0x18007f348  jz      short loc_18007F354
0x18007f34a  mov     ebx, 8000FFFFh
0x18007f34f  jmp     loc_18007F431
0x18007f354  call    cs:__imp_GetLastError
0x18007f35a  mov     ebx, eax
0x18007f35c  cmp     eax, 7Ah ; 'z'
0x18007f35f  jz      short loc_18007F376
0x18007f361  test    eax, eax
0x18007f363  jle     short loc_18007F36E
0x18007f365  movzx   ebx, ax
0x18007f368  or      ebx, 80070000h
0x18007f36e  test    ebx, ebx
0x18007f370  js      loc_18007F431
0x18007f376  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x18007f37a  mov     ecx, 40h ; '@'; uFlags
0x18007f37f  call    cs:__imp_LocalAlloc
0x18007f385  mov     rdi, rax
0x18007f388  test    rax, rax
0x18007f38b  jnz     short loc_18007F397
0x18007f38d  mov     ebx, 8007000Eh
0x18007f392  jmp     loc_18007F431
0x18007f397  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18007f39c  lea     rax, [rsp+58h+TokenInformationLength]
0x18007f3a1  mov     r8, rdi; TokenInformation
0x18007f3a4  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18007f3a9  mov     edx, 1Fh; TokenInformationClass
0x18007f3ae  mov     rcx, rsi; TokenHandle
0x18007f3b1  call    cs:__imp_GetTokenInformation
0x18007f3b7  test    eax, eax
0x18007f3b9  jnz     short loc_18007F3C6
0x18007f3bb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18007f3c0  mov     ebx, eax
0x18007f3c2  test    eax, eax
0x18007f3c4  js      short loc_18007F431
0x18007f3c6  mov     rcx, [rdi]; pSid
0x18007f3c9  test    rcx, rcx
0x18007f3cc  jnz     short loc_18007F3D5
0x18007f3ce  mov     ebx, 80070490h
0x18007f3d3  jmp     short loc_18007F428
0x18007f3d5  call    cs:__imp_GetLengthSid
0x18007f3db  mov     edx, eax; uBytes
0x18007f3dd  mov     ecx, 40h ; '@'; uFlags
0x18007f3e2  mov     ebx, eax
0x18007f3e4  call    cs:__imp_LocalAlloc
0x18007f3ea  mov     rsi, rax
0x18007f3ed  test    rax, rax
0x18007f3f0  jnz     short loc_18007F3F9
0x18007f3f2  mov     ebx, 8007000Eh
0x18007f3f7  jmp     short loc_18007F428
0x18007f3f9  mov     r8, [rdi]; pSourceSid
0x18007f3fc  mov     rdx, rsi; pDestinationSid
0x18007f3ff  mov     ecx, ebx; nDestinationSidLength
0x18007f401  call    cs:__imp_CopySid
0x18007f407  test    eax, eax
0x18007f409  jz      short loc_18007F40F
0x18007f40b  xor     ebx, ebx
0x18007f40d  jmp     short loc_18007F41A
0x18007f40f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18007f414  mov     ebx, eax
0x18007f416  test    eax, eax
0x18007f418  js      short loc_18007F41F
0x18007f41a  mov     [r14], rsi
0x18007f41d  jmp     short loc_18007F428
0x18007f41f  mov     rcx, rsi; hMem
0x18007f422  call    cs:__imp_LocalFree
0x18007f428  mov     rcx, rdi; hMem
0x18007f42b  call    cs:__imp_LocalFree
0x18007f431  mov     eax, ebx
0x18007f433  add     rsp, 38h
0x18007f437  pop     r14
0x18007f439  pop     rdi
0x18007f43a  pop     rsi
0x18007f43b  pop     rbx
0x18007f43c  retn
```
