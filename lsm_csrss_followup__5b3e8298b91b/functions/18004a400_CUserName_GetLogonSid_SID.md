# CUserName::GetLogonSid(_SID * *)

- ea: `0x18004a400`
- end: `0x18004a585`
- name: `?GetLogonSid@CUserName@@UEAAJPEAPEAU_SID@@@Z`
- size: `389`
- prototype: `__int64 __fastcall(CUserName *__hidden this, struct _SID **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800074c0`
- `0x18004a400`
- `0x18009404c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18004a4f7`
- `ntdll!RtlLengthSid` at `0x18004a4f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a532`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a475`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a532`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a52a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a52a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a488`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a488`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a501`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004a467`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004a4be`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004a467`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004a4be`

## string_xrefs

- `0x18004a438`: `No token`
- `0x18004a54a`: `Cannot get the TOKEN_GROUPS length: 0x%x`
- `0x18004a4e0`: `GetTokenInformation failed: 0x%x`
- `0x18004a55d`: `Cannot get the TOKEN_GROUPS length`

## pseudocode

```c
__int64 __fastcall CUserName::GetLogonSid(CUserName *this, struct _SID **a2)
{
  unsigned int v4; // ebx
  void *v5; // rcx
  PSID *v6; // rdi
  signed int LastError; // eax
  SIZE_T v8; // rsi
  struct _SID *v9; // rax
  signed int v10; // eax
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = 0;
  if ( a2 )
  {
    v5 = (void *)*((_QWORD *)this + 199);
    if ( v5 )
    {
      if ( GetTokenInformation(v5, TokenLogonSid, 0, 0, &TokenInformationLength) )
      {
        v4 = -2147024809;
        _DbgPrintMessage(8, "Cannot get the TOKEN_GROUPS length");
      }
      else if ( GetLastError() == 122 )
      {
        v6 = (PSID *)CoTaskMemAlloc(TokenInformationLength);
        if ( v6 )
        {
          if ( GetTokenInformation(
                 *((HANDLE *)this + 199),
                 TokenLogonSid,
                 v6,
                 TokenInformationLength,
                 &TokenInformationLength) )
          {
            v8 = RtlLengthSid(v6[1]);
            v9 = (struct _SID *)CoTaskMemAlloc(v8);
            *a2 = v9;
            if ( v9 )
            {
              memcpy_0(v9, v6[1], v8);
              v4 = 0;
            }
            else
            {
              v4 = -2147024882;
            }
          }
          else
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            _DbgPrintMessage(8, "GetTokenInformation failed: 0x%x", v4);
          }
          CoTaskMemFree(v6);
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
      else
      {
        v10 = GetLastError();
        v4 = v10;
        if ( v10 > 0 )
          v4 = (unsigned __int16)v10 | 0x80070000;
        _DbgPrintMessage(8, "Cannot get the TOKEN_GROUPS length: 0x%x", v4);
      }
    }
    else
    {
      _DbgPrintMessage(8, "No token");
      return (unsigned int)-2147023888;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18004a400  mov     [rsp+arg_0], rbx
0x18004a405  mov     [rsp+arg_10], rsi
0x18004a40a  push    rdi
0x18004a40b  sub     rsp, 30h
0x18004a40f  mov     [rsp+38h+TokenInformationLength], 0
0x18004a417  mov     rbx, rdx
0x18004a41a  mov     rsi, rcx
0x18004a41d  test    rdx, rdx
0x18004a420  jnz     short loc_18004A42C
0x18004a422  mov     ebx, 80070057h
0x18004a427  jmp     loc_18004A573
0x18004a42c  mov     rcx, [rcx+638h]; TokenHandle
0x18004a433  test    rcx, rcx
0x18004a436  jnz     short loc_18004A453
0x18004a438  lea     rdx, aNoToken; "No token"
0x18004a43f  mov     ecx, 8; int
0x18004a444  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004a449  mov     ebx, 800703F0h
0x18004a44e  jmp     loc_18004A573
0x18004a453  xor     r9d, r9d; TokenInformationLength
0x18004a456  lea     rax, [rsp+38h+TokenInformationLength]
0x18004a45b  xor     r8d, r8d; TokenInformation
0x18004a45e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18004a463  lea     edx, [r9+1Ch]; TokenInformationClass
0x18004a467  call    cs:__imp_GetTokenInformation
0x18004a46d  test    eax, eax
0x18004a46f  jnz     loc_18004A55D
0x18004a475  call    cs:__imp_GetLastError
0x18004a47b  cmp     eax, 7Ah ; 'z'
0x18004a47e  jnz     loc_18004A532
0x18004a484  mov     ecx, [rsp+38h+TokenInformationLength]; cb
0x18004a488  call    cs:__imp_CoTaskMemAlloc
0x18004a48e  mov     rdi, rax
0x18004a491  test    rax, rax
0x18004a494  jnz     short loc_18004A4A0
0x18004a496  mov     ebx, 8007000Eh
0x18004a49b  jmp     loc_18004A573
0x18004a4a0  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18004a4a5  lea     rax, [rsp+38h+TokenInformationLength]
0x18004a4aa  mov     rcx, [rsi+638h]; TokenHandle
0x18004a4b1  mov     r8, rdi; TokenInformation
0x18004a4b4  mov     edx, 1Ch; TokenInformationClass
0x18004a4b9  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18004a4be  call    cs:__imp_GetTokenInformation
0x18004a4c4  test    eax, eax
0x18004a4c6  jnz     short loc_18004A4F3
0x18004a4c8  call    cs:__imp_GetLastError
0x18004a4ce  mov     ebx, eax
0x18004a4d0  test    eax, eax
0x18004a4d2  jle     short loc_18004A4DD
0x18004a4d4  movzx   ebx, ax
0x18004a4d7  or      ebx, 80070000h
0x18004a4dd  mov     r8d, ebx
0x18004a4e0  lea     rdx, aGettokeninform_0; "GetTokenInformation failed: 0x%x"
0x18004a4e7  mov     ecx, 8; int
0x18004a4ec  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004a4f1  jmp     short loc_18004A527
0x18004a4f3  mov     rcx, [rdi+8]; Sid
0x18004a4f7  call    cs:__imp_RtlLengthSid
0x18004a4fd  mov     ecx, eax; cb
0x18004a4ff  mov     esi, eax
0x18004a501  call    cs:__imp_CoTaskMemAlloc
0x18004a507  mov     [rbx], rax
0x18004a50a  test    rax, rax
0x18004a50d  jnz     short loc_18004A516
0x18004a50f  mov     ebx, 8007000Eh
0x18004a514  jmp     short loc_18004A527
0x18004a516  mov     rdx, [rdi+8]; Src
0x18004a51a  mov     r8, rsi; Size
0x18004a51d  mov     rcx, rax; void *
0x18004a520  call    memcpy_0
0x18004a525  xor     ebx, ebx
0x18004a527  mov     rcx, rdi; pv
0x18004a52a  call    cs:__imp_CoTaskMemFree
0x18004a530  jmp     short loc_18004A573
0x18004a532  call    cs:__imp_GetLastError
0x18004a538  mov     ebx, eax
0x18004a53a  test    eax, eax
0x18004a53c  jle     short loc_18004A547
0x18004a53e  movzx   ebx, ax
0x18004a541  or      ebx, 80070000h
0x18004a547  mov     r8d, ebx
0x18004a54a  lea     rdx, aCannotGetTheTo; "Cannot get the TOKEN_GROUPS length: 0x%"...
0x18004a551  mov     ecx, 8; int
0x18004a556  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004a55b  jmp     short loc_18004A573
0x18004a55d  lea     rdx, aCannotGetTheTo_0; "Cannot get the TOKEN_GROUPS length"
0x18004a564  mov     ecx, 8; int
0x18004a569  mov     ebx, 80070057h
0x18004a56e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004a573  mov     rsi, [rsp+38h+arg_10]
0x18004a578  mov     eax, ebx
0x18004a57a  mov     rbx, [rsp+38h+arg_0]
0x18004a57f  add     rsp, 30h
0x18004a583  pop     rdi
0x18004a584  retn
```
