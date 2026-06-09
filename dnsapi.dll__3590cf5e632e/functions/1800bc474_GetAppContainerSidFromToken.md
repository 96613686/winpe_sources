# GetAppContainerSidFromToken

- ea: `0x1800bc474`
- end: `0x1800bc5d0`
- name: `GetAppContainerSidFromToken`
- size: `348`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID pDestinationSid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bc874`

## callees

- `0x18008b5f0`
- `0x1800bc474`
- `0x1800dc9e0`
- `0x1800ddfa8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc4f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc559`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc4f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc559`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bc4e9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800bc4e9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800bc549`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800bc549`

## pseudocode

```c
__int64 __fastcall GetAppContainerSidFromToken(HANDLE TokenHandle, PSID pDestinationSid)
{
  DWORD v2; // r9d
  signed int v5; // eax
  signed int v6; // ebx
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+38h] [rbp-70h] BYREF
  PSID TokenInformation[10]; // [rsp+40h] [rbp-68h] BYREF

  v2 = 76;
  TokenInformationLength = 76;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
  {
    WPP_SF_q(1035, 15, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids, TokenHandle);
    v2 = TokenInformationLength;
  }
  if ( GetTokenInformation(TokenHandle, TokenAppContainerSid, TokenInformation, v2, &TokenInformationLength) )
  {
    if ( TokenInformation[0] )
    {
      if ( CopySid(0x44u, pDestinationSid, TokenInformation[0]) )
      {
        v6 = 0;
      }
      else
      {
        LastError = GetLastError();
        v6 = LastError;
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        if ( v6 >= 0 )
          v6 = -2147418113;
      }
    }
    else
    {
      v6 = -2147418113;
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147418113;
  }
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 16, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800bc474  mov     [rsp+arg_10], rbx
0x1800bc479  push    rdi
0x1800bc47a  sub     rsp, 0A0h
0x1800bc481  mov     rax, cs:__security_cookie
0x1800bc488  xor     rax, rsp
0x1800bc48b  mov     [rsp+0A8h+var_18], rax
0x1800bc493  mov     r9d, 4Ch ; 'L'
0x1800bc499  mov     [rsp+0A8h+var_74], 0
0x1800bc4a1  mov     [rsp+0A8h+TokenInformationLength], r9d
0x1800bc4a6  mov     rdi, rdx
0x1800bc4a9  mov     rbx, rcx
0x1800bc4ac  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800bc4b3  jz      short loc_1800BC4D2
0x1800bc4b5  lea     edx, [r9-3Dh]
0x1800bc4b9  mov     ecx, 40Bh
0x1800bc4be  mov     r9, rbx
0x1800bc4c1  lea     r8, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids
0x1800bc4c8  call    WPP_SF_q
0x1800bc4cd  mov     r9d, [rsp+0A8h+TokenInformationLength]; TokenInformationLength
0x1800bc4d2  lea     rax, [rsp+0A8h+TokenInformationLength]
0x1800bc4d7  mov     edx, 1Fh; TokenInformationClass
0x1800bc4dc  lea     r8, [rsp+0A8h+TokenInformation]; TokenInformation
0x1800bc4e1  mov     [rsp+0A8h+ReturnLength], rax; ReturnLength
0x1800bc4e6  mov     rcx, rbx; TokenHandle
0x1800bc4e9  call    cs:__imp_GetTokenInformation
0x1800bc4f0  nop     dword ptr [rax+rax+00h]
0x1800bc4f5  test    eax, eax
0x1800bc4f7  jnz     short loc_1800BC528
0x1800bc4f9  call    cs:__imp_GetLastError
0x1800bc500  nop     dword ptr [rax+rax+00h]
0x1800bc505  mov     ebx, eax
0x1800bc507  test    eax, eax
0x1800bc509  jle     short loc_1800BC514
0x1800bc50b  movzx   ebx, ax
0x1800bc50e  or      ebx, 80070000h
0x1800bc514  test    ebx, ebx
0x1800bc516  mov     [rsp+0A8h+var_74], 122h
0x1800bc51e  mov     eax, 8000FFFFh
0x1800bc523  cmovns  ebx, eax
0x1800bc526  jmp     short loc_1800BC58A
0x1800bc528  mov     r8, [rsp+0A8h+TokenInformation]; pSourceSid
0x1800bc52d  test    r8, r8
0x1800bc530  jnz     short loc_1800BC541
0x1800bc532  mov     ebx, 8000FFFFh
0x1800bc537  mov     [rsp+0A8h+var_74], 124h
0x1800bc53f  jmp     short loc_1800BC58A
0x1800bc541  mov     rdx, rdi; pDestinationSid
0x1800bc544  mov     ecx, 44h ; 'D'; nDestinationSidLength
0x1800bc549  call    cs:__imp_CopySid
0x1800bc550  nop     dword ptr [rax+rax+00h]
0x1800bc555  test    eax, eax
0x1800bc557  jnz     short loc_1800BC588
0x1800bc559  call    cs:__imp_GetLastError
0x1800bc560  nop     dword ptr [rax+rax+00h]
0x1800bc565  mov     ebx, eax
0x1800bc567  test    eax, eax
0x1800bc569  jle     short loc_1800BC574
0x1800bc56b  movzx   ebx, ax
0x1800bc56e  or      ebx, 80070000h
0x1800bc574  test    ebx, ebx
0x1800bc576  mov     [rsp+0A8h+var_74], 128h
0x1800bc57e  mov     eax, 8000FFFFh
0x1800bc583  cmovns  ebx, eax
0x1800bc586  jmp     short loc_1800BC58A
0x1800bc588  xor     ebx, ebx
0x1800bc58a  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800bc591  jz      short loc_1800BC5AC
0x1800bc593  mov     edx, 10h
0x1800bc598  lea     r8, WPP_c8767a4f47dd3eef630fa09f96ecdab4_Traceguids
0x1800bc59f  mov     ecx, 40Bh
0x1800bc5a4  mov     r9d, ebx
0x1800bc5a7  call    WPP_SF_d
0x1800bc5ac  mov     eax, ebx
0x1800bc5ae  mov     rcx, [rsp+0A8h+var_18]
0x1800bc5b6  xor     rcx, rsp; StackCookie
0x1800bc5b9  call    __security_check_cookie
0x1800bc5be  mov     rbx, [rsp+0A8h+arg_10]
0x1800bc5c6  add     rsp, 0A0h
0x1800bc5cd  pop     rdi
0x1800bc5ce  retn
```
