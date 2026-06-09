# NgcUtils::GetUserSidFromToken

- ea: `0x18001a4d0`
- end: `0x18001a676`
- name: `NgcUtils::GetUserSidFromToken`
- size: `422`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010a40`
- `0x18001570c`
- `0x1800158c4`

## callees

- `0x18000113c`
- `0x180003080`
- `0x18000cfcc`
- `0x1800163bc`
- `0x18001a4d0`
- `0x18001af98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a51f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a5be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a51f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a5be`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a624`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001a624`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a515`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a5b4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a515`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a5b4`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001a642`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001a642`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::GetUserSidFromToken(__int64 a1, PSID *a2)
{
  signed int v3; // ebx
  DWORD LastError; // eax
  __int64 LengthSid; // rbx
  DWORD TokenInformationLength; // [rsp+38h] [rbp-9h] BYREF
  DWORD v8; // [rsp+3Ch] [rbp-5h] BYREF
  LPVOID TokenInformation[3]; // [rsp+40h] [rbp-1h] BYREF
  _BYTE v10[32]; // [rsp+58h] [rbp+17h] BYREF
  DWORD *v11; // [rsp+78h] [rbp+37h]
  __int64 v12; // [rsp+80h] [rbp+3Fh]

  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, &TokenInformationLength)
    || (v3 = GetLastError(), v3 == 122) )
  {
    std::vector<unsigned char>::vector<unsigned char>(TokenInformation, TokenInformationLength);
    if ( GetTokenInformation(
           (HANDLE)0xFFFFFFFFFFFFFFFALL,
           TokenUser,
           TokenInformation[0],
           TokenInformationLength,
           &TokenInformationLength) )
    {
      LengthSid = GetLengthSid(*(PSID *)TokenInformation[0]);
      std::vector<unsigned char>::resize(a2, LengthSid);
      CopySid(LengthSid, *a2, *(PSID *)TokenInformation[0]);
      v3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( (unsigned int)dword_180075000 > 2 )
      {
        v8 = LastError;
        v11 = &v8;
        v12 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_180075000, word_180068A82, 0, 0, 3, v10);
      }
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
    }
    std::vector<unsigned char>::~vector<unsigned char>(TokenInformation);
  }
  else
  {
    if ( (unsigned int)dword_180075000 > 2 )
    {
      v8 = v3;
      v11 = &v8;
      v12 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180075000, byte_180068AAD, 0, 0, 3, v10);
    }
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001a4d0  mov     r11, rsp
0x18001a4d3  mov     [r11+8], rbx
0x18001a4d7  mov     [r11+18h], rdi
0x18001a4db  push    rbp
0x18001a4dc  lea     rbp, [r11-5Fh]
0x18001a4e0  sub     rsp, 90h
0x18001a4e7  mov     rax, cs:__security_cookie
0x18001a4ee  xor     rax, rsp
0x18001a4f1  mov     [rbp+57h+var_10], rax
0x18001a4f5  mov     rdi, rdx
0x18001a4f8  mov     [rbp+57h+TokenInformationLength], 0
0x18001a4ff  lea     rax, [rbp+57h+TokenInformationLength]
0x18001a503  mov     [r11-78h], rax
0x18001a507  xor     r9d, r9d; TokenInformationLength
0x18001a50a  xor     r8d, r8d; TokenInformation
0x18001a50d  lea     edx, [r9+1]; TokenInformationClass
0x18001a511  lea     rcx, [r9-6]; TokenHandle
0x18001a515  call    cs:__imp_GetTokenInformation
0x18001a51b  test    eax, eax
0x18001a51d  jnz     short loc_18001A58A
0x18001a51f  call    cs:__imp_GetLastError
0x18001a525  mov     ebx, eax
0x18001a527  cmp     eax, 7Ah ; 'z'
0x18001a52a  jz      short loc_18001A58A
0x18001a52c  mov     eax, cs:dword_180075000
0x18001a532  cmp     eax, 2
0x18001a535  jbe     short loc_18001A574
0x18001a537  mov     [rbp+57h+var_5C], ebx
0x18001a53a  lea     rax, [rbp+57h+var_5C]
0x18001a53e  mov     [rbp+57h+var_20], rax
0x18001a542  mov     [rbp+57h+var_18], 4
0x18001a54a  lea     rax, [rbp+57h+var_40]
0x18001a54e  mov     [rsp+90h+var_68], rax
0x18001a553  mov     dword ptr [rsp+90h+ReturnLength], 3
0x18001a55b  xor     r9d, r9d
0x18001a55e  xor     r8d, r8d
0x18001a561  lea     rdx, byte_180068AAD
0x18001a568  lea     rcx, dword_180075000
0x18001a56f  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a574  test    ebx, ebx
0x18001a576  jle     loc_18001A653
0x18001a57c  movzx   ebx, bx
0x18001a57f  or      ebx, 80070000h
0x18001a585  jmp     loc_18001A653
0x18001a58a  mov     edx, [rbp+57h+TokenInformationLength]
0x18001a58d  lea     rcx, [rbp+57h+TokenInformation]
0x18001a591  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18001a596  nop
0x18001a597  lea     rax, [rbp+57h+TokenInformationLength]
0x18001a59b  mov     [rsp+90h+ReturnLength], rax; ReturnLength
0x18001a5a0  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18001a5a4  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18001a5a8  mov     edx, 1; TokenInformationClass
0x18001a5ad  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18001a5b4  call    cs:__imp_GetTokenInformation
0x18001a5ba  test    eax, eax
0x18001a5bc  jnz     short loc_18001A61D
0x18001a5be  call    cs:__imp_GetLastError
0x18001a5c4  mov     ebx, eax
0x18001a5c6  mov     ecx, cs:dword_180075000
0x18001a5cc  cmp     ecx, 2
0x18001a5cf  jbe     short loc_18001A60E
0x18001a5d1  mov     [rbp+57h+var_5C], eax
0x18001a5d4  lea     rax, [rbp+57h+var_5C]
0x18001a5d8  mov     [rbp+57h+var_20], rax
0x18001a5dc  mov     [rbp+57h+var_18], 4
0x18001a5e4  lea     rax, [rbp+57h+var_40]
0x18001a5e8  mov     [rsp+90h+var_68], rax
0x18001a5ed  mov     dword ptr [rsp+90h+ReturnLength], 3
0x18001a5f5  xor     r9d, r9d
0x18001a5f8  xor     r8d, r8d
0x18001a5fb  lea     rdx, word_180068A82
0x18001a602  lea     rcx, dword_180075000
0x18001a609  call    _tlgWriteTransfer_EventWriteTransfer
0x18001a60e  test    ebx, ebx
0x18001a610  jle     short loc_18001A64A
0x18001a612  movzx   ebx, bx
0x18001a615  or      ebx, 80070000h
0x18001a61b  jmp     short loc_18001A64A
0x18001a61d  mov     rcx, [rbp+57h+TokenInformation]
0x18001a621  mov     rcx, [rcx]; pSid
0x18001a624  call    cs:__imp_GetLengthSid
0x18001a62a  mov     ebx, eax
0x18001a62c  mov     edx, eax
0x18001a62e  mov     rcx, rdi
0x18001a631  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18001a636  mov     r8, [rbp+57h+TokenInformation]
0x18001a63a  mov     r8, [r8]; pSourceSid
0x18001a63d  mov     rdx, [rdi]; pDestinationSid
0x18001a640  mov     ecx, ebx; nDestinationSidLength
0x18001a642  call    cs:__imp_CopySid
0x18001a648  xor     ebx, ebx
0x18001a64a  lea     rcx, [rbp+57h+TokenInformation]
0x18001a64e  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001a653  mov     eax, ebx
0x18001a655  mov     rcx, [rbp+57h+var_10]
0x18001a659  xor     rcx, rsp; StackCookie
0x18001a65c  call    __security_check_cookie
0x18001a661  lea     r11, [rsp+90h+var_s0]
0x18001a669  mov     rbx, [r11+10h]
0x18001a66d  mov     rdi, [r11+20h]
0x18001a671  mov     rsp, r11
0x18001a674  pop     rbp
0x18001a675  retn
```
