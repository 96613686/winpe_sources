# NgcUtils::GetCallerAppContainerSid(std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x1800191c4`
- end: `0x18001936e`
- name: `?GetCallerAppContainerSid@NgcUtils@@YAJPEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010920`

## callees

- `0x18000113c`
- `0x180003080`
- `0x18000cfcc`
- `0x1800163bc`
- `0x1800191c4`
- `0x18001af98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019213`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800192b2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001931c`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001931c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019209`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800192a8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180019209`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800192a8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001933a`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18001933a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::GetCallerAppContainerSid(PSID *a1)
{
  signed int LastError; // ebx
  DWORD LengthSid; // ebx
  DWORD TokenInformationLength; // [rsp+38h] [rbp-9h] BYREF
  signed int v6; // [rsp+3Ch] [rbp-5h] BYREF
  LPVOID TokenInformation[3]; // [rsp+40h] [rbp-1h] BYREF
  _BYTE v8[32]; // [rsp+58h] [rbp+17h] BYREF
  signed int *v9; // [rsp+78h] [rbp+37h]
  __int64 v10; // [rsp+80h] [rbp+3Fh]

  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenAppContainerSid, 0, 0, &TokenInformationLength)
    || (LastError = GetLastError(), LastError == 122) )
  {
    std::vector<unsigned char>::vector<unsigned char>(TokenInformation, TokenInformationLength);
    if ( GetTokenInformation(
           (HANDLE)0xFFFFFFFFFFFFFFFALL,
           TokenAppContainerSid,
           TokenInformation[0],
           TokenInformationLength,
           &TokenInformationLength) )
    {
      LengthSid = GetLengthSid(*(PSID *)TokenInformation[0]);
      std::vector<unsigned char>::resize(a1, LengthSid);
      CopySid(LengthSid, *a1, *(PSID *)TokenInformation[0]);
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180075000 > 2 )
      {
        v6 = 0;
        v9 = &v6;
        v10 = 4;
        tlgWriteTransfer_EventWriteTransfer(&dword_180075000, &dword_180068A2C, 0, 0, 3, v8);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    std::vector<unsigned char>::~vector<unsigned char>(TokenInformation);
  }
  else
  {
    if ( (unsigned int)dword_180075000 > 2 )
    {
      v6 = LastError;
      v9 = &v6;
      v10 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180075000, &byte_180068A57, 0, 0, 3, v8);
    }
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800191c4  mov     r11, rsp
0x1800191c7  mov     [r11+10h], rbx
0x1800191cb  mov     [r11+18h], rdi
0x1800191cf  push    rbp
0x1800191d0  lea     rbp, [r11-5Fh]
0x1800191d4  sub     rsp, 90h
0x1800191db  mov     rax, cs:__security_cookie
0x1800191e2  xor     rax, rsp
0x1800191e5  mov     [rbp+57h+var_10], rax
0x1800191e9  mov     rdi, rcx
0x1800191ec  mov     [rbp+57h+TokenInformationLength], 0
0x1800191f3  lea     rax, [rbp+57h+TokenInformationLength]
0x1800191f7  mov     [r11-78h], rax
0x1800191fb  xor     r9d, r9d; TokenInformationLength
0x1800191fe  xor     r8d, r8d; TokenInformation
0x180019201  lea     edx, [r9+1Fh]; TokenInformationClass
0x180019205  lea     rcx, [r9-6]; TokenHandle
0x180019209  call    cs:__imp_GetTokenInformation
0x18001920f  test    eax, eax
0x180019211  jnz     short loc_18001927E
0x180019213  call    cs:__imp_GetLastError
0x180019219  mov     ebx, eax
0x18001921b  cmp     eax, 7Ah ; 'z'
0x18001921e  jz      short loc_18001927E
0x180019220  mov     eax, cs:dword_180075000
0x180019226  cmp     eax, 2
0x180019229  jbe     short loc_180019268
0x18001922b  mov     [rbp+57h+var_5C], ebx
0x18001922e  lea     rax, [rbp+57h+var_5C]
0x180019232  mov     [rbp+57h+var_20], rax
0x180019236  mov     [rbp+57h+var_18], 4
0x18001923e  lea     rax, [rbp+57h+var_40]
0x180019242  mov     [rsp+90h+var_68], rax
0x180019247  mov     dword ptr [rsp+90h+ReturnLength], 3
0x18001924f  xor     r9d, r9d
0x180019252  xor     r8d, r8d
0x180019255  lea     rdx, byte_180068A57
0x18001925c  lea     rcx, dword_180075000
0x180019263  call    _tlgWriteTransfer_EventWriteTransfer
0x180019268  test    ebx, ebx
0x18001926a  jle     loc_18001934B
0x180019270  movzx   ebx, bx
0x180019273  or      ebx, 80070000h
0x180019279  jmp     loc_18001934B
0x18001927e  mov     edx, [rbp+57h+TokenInformationLength]
0x180019281  lea     rcx, [rbp+57h+TokenInformation]
0x180019285  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18001928a  nop
0x18001928b  lea     rax, [rbp+57h+TokenInformationLength]
0x18001928f  mov     [rsp+90h+ReturnLength], rax; ReturnLength
0x180019294  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180019298  mov     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18001929c  mov     edx, 1Fh; TokenInformationClass
0x1800192a1  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800192a8  call    cs:__imp_GetTokenInformation
0x1800192ae  test    eax, eax
0x1800192b0  jnz     short loc_180019315
0x1800192b2  call    cs:__imp_GetLastError
0x1800192b8  mov     ebx, eax
0x1800192ba  mov     ecx, cs:dword_180075000
0x1800192c0  cmp     ecx, 2
0x1800192c3  jbe     short loc_180019306
0x1800192c5  mov     [rbp+57h+var_5C], 0
0x1800192cc  lea     rax, [rbp+57h+var_5C]
0x1800192d0  mov     [rbp+57h+var_20], rax
0x1800192d4  mov     [rbp+57h+var_18], 4
0x1800192dc  lea     rax, [rbp+57h+var_40]
0x1800192e0  mov     [rsp+90h+var_68], rax
0x1800192e5  mov     dword ptr [rsp+90h+ReturnLength], 3
0x1800192ed  xor     r9d, r9d
0x1800192f0  xor     r8d, r8d
0x1800192f3  lea     rdx, dword_180068A2C
0x1800192fa  lea     rcx, dword_180075000
0x180019301  call    _tlgWriteTransfer_EventWriteTransfer
0x180019306  test    ebx, ebx
0x180019308  jle     short loc_180019342
0x18001930a  movzx   ebx, bx
0x18001930d  or      ebx, 80070000h
0x180019313  jmp     short loc_180019342
0x180019315  mov     rcx, [rbp+57h+TokenInformation]
0x180019319  mov     rcx, [rcx]; pSid
0x18001931c  call    cs:__imp_GetLengthSid
0x180019322  mov     ebx, eax
0x180019324  mov     edx, eax
0x180019326  mov     rcx, rdi
0x180019329  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x18001932e  mov     r8, [rbp+57h+TokenInformation]
0x180019332  mov     r8, [r8]; pSourceSid
0x180019335  mov     rdx, [rdi]; pDestinationSid
0x180019338  mov     ecx, ebx; nDestinationSidLength
0x18001933a  call    cs:__imp_CopySid
0x180019340  xor     ebx, ebx
0x180019342  lea     rcx, [rbp+57h+TokenInformation]
0x180019346  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18001934b  mov     eax, ebx
0x18001934d  mov     rcx, [rbp+57h+var_10]
0x180019351  xor     rcx, rsp; StackCookie
0x180019354  call    __security_check_cookie
0x180019359  lea     r11, [rsp+90h+var_s0]
0x180019361  mov     rbx, [r11+18h]
0x180019365  mov     rdi, [r11+20h]
0x180019369  mov     rsp, r11
0x18001936c  pop     rbp
0x18001936d  retn
```
