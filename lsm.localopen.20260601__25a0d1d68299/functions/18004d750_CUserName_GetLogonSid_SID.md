# CUserName::GetLogonSid(_SID * *)

- ea: `0x18004d750`
- end: `0x18004d90c`
- name: `?GetLogonSid@CUserName@@UEAAJPEAPEAU_SID@@@Z`
- size: `444`
- prototype: `__int64 __fastcall(CUserName *__hidden this, struct _SID **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800077a0`
- `0x18004d750`
- `0x18009959c`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18004d865`
- `ntdll!RtlLengthSid` at `0x18004d865`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d7cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d8b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d7cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004d8b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d8a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004d8a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d7e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d875`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d7e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004d875`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004d7b7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004d820`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004d7b7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004d820`

## string_xrefs

- `0x18004d788`: `No token`
- `0x18004d8d0`: `Cannot get the TOKEN_GROUPS length: 0x%x`
- `0x18004d84e`: `GetTokenInformation failed: 0x%x`
- `0x18004d8e3`: `Cannot get the TOKEN_GROUPS length`

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
0x18004d750  mov     [rsp+arg_0], rbx
0x18004d755  mov     [rsp+arg_10], rsi
0x18004d75a  push    rdi
0x18004d75b  sub     rsp, 30h
0x18004d75f  mov     [rsp+38h+TokenInformationLength], 0
0x18004d767  mov     rbx, rdx
0x18004d76a  mov     rsi, rcx
0x18004d76d  test    rdx, rdx
0x18004d770  jnz     short loc_18004D77C
0x18004d772  mov     ebx, 80070057h
0x18004d777  jmp     loc_18004D8F9
0x18004d77c  mov     rcx, [rcx+638h]; TokenHandle
0x18004d783  test    rcx, rcx
0x18004d786  jnz     short loc_18004D7A3
0x18004d788  lea     rdx, aNoToken; "No token"
0x18004d78f  mov     ecx, 8; int
0x18004d794  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004d799  mov     ebx, 800703F0h
0x18004d79e  jmp     loc_18004D8F9
0x18004d7a3  xor     r9d, r9d; TokenInformationLength
0x18004d7a6  lea     rax, [rsp+38h+TokenInformationLength]
0x18004d7ab  xor     r8d, r8d; TokenInformation
0x18004d7ae  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18004d7b3  lea     edx, [r9+1Ch]; TokenInformationClass
0x18004d7b7  call    cs:__imp_GetTokenInformation
0x18004d7be  nop     dword ptr [rax+rax+00h]
0x18004d7c3  test    eax, eax
0x18004d7c5  jnz     loc_18004D8E3
0x18004d7cb  call    cs:__imp_GetLastError
0x18004d7d2  nop     dword ptr [rax+rax+00h]
0x18004d7d7  cmp     eax, 7Ah ; 'z'
0x18004d7da  jnz     loc_18004D8B2
0x18004d7e0  mov     ecx, [rsp+38h+TokenInformationLength]; cb
0x18004d7e4  call    cs:__imp_CoTaskMemAlloc
0x18004d7eb  nop     dword ptr [rax+rax+00h]
0x18004d7f0  mov     rdi, rax
0x18004d7f3  test    rax, rax
0x18004d7f6  jnz     short loc_18004D802
0x18004d7f8  mov     ebx, 8007000Eh
0x18004d7fd  jmp     loc_18004D8F9
0x18004d802  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x18004d807  lea     rax, [rsp+38h+TokenInformationLength]
0x18004d80c  mov     rcx, [rsi+638h]; TokenHandle
0x18004d813  mov     r8, rdi; TokenInformation
0x18004d816  mov     edx, 1Ch; TokenInformationClass
0x18004d81b  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x18004d820  call    cs:__imp_GetTokenInformation
0x18004d827  nop     dword ptr [rax+rax+00h]
0x18004d82c  test    eax, eax
0x18004d82e  jnz     short loc_18004D861
0x18004d830  call    cs:__imp_GetLastError
0x18004d837  nop     dword ptr [rax+rax+00h]
0x18004d83c  mov     ebx, eax
0x18004d83e  test    eax, eax
0x18004d840  jle     short loc_18004D84B
0x18004d842  movzx   ebx, ax
0x18004d845  or      ebx, 80070000h
0x18004d84b  mov     r8d, ebx
0x18004d84e  lea     rdx, aGettokeninform_0; "GetTokenInformation failed: 0x%x"
0x18004d855  mov     ecx, 8; int
0x18004d85a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004d85f  jmp     short loc_18004D8A1
0x18004d861  mov     rcx, [rdi+8]; Sid
0x18004d865  call    cs:__imp_RtlLengthSid
0x18004d86c  nop     dword ptr [rax+rax+00h]
0x18004d871  mov     ecx, eax; cb
0x18004d873  mov     esi, eax
0x18004d875  call    cs:__imp_CoTaskMemAlloc
0x18004d87c  nop     dword ptr [rax+rax+00h]
0x18004d881  mov     [rbx], rax
0x18004d884  test    rax, rax
0x18004d887  jnz     short loc_18004D890
0x18004d889  mov     ebx, 8007000Eh
0x18004d88e  jmp     short loc_18004D8A1
0x18004d890  mov     rdx, [rdi+8]; Src
0x18004d894  mov     r8, rsi; Size
0x18004d897  mov     rcx, rax; void *
0x18004d89a  call    memcpy_0
0x18004d89f  xor     ebx, ebx
0x18004d8a1  mov     rcx, rdi; pv
0x18004d8a4  call    cs:__imp_CoTaskMemFree
0x18004d8ab  nop     dword ptr [rax+rax+00h]
0x18004d8b0  jmp     short loc_18004D8F9
0x18004d8b2  call    cs:__imp_GetLastError
0x18004d8b9  nop     dword ptr [rax+rax+00h]
0x18004d8be  mov     ebx, eax
0x18004d8c0  test    eax, eax
0x18004d8c2  jle     short loc_18004D8CD
0x18004d8c4  movzx   ebx, ax
0x18004d8c7  or      ebx, 80070000h
0x18004d8cd  mov     r8d, ebx
0x18004d8d0  lea     rdx, aCannotGetTheTo; "Cannot get the TOKEN_GROUPS length: 0x%"...
0x18004d8d7  mov     ecx, 8; int
0x18004d8dc  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004d8e1  jmp     short loc_18004D8F9
0x18004d8e3  lea     rdx, aCannotGetTheTo_0; "Cannot get the TOKEN_GROUPS length"
0x18004d8ea  mov     ecx, 8; int
0x18004d8ef  mov     ebx, 80070057h
0x18004d8f4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004d8f9  mov     rsi, [rsp+38h+arg_10]
0x18004d8fe  mov     eax, ebx
0x18004d900  mov     rbx, [rsp+38h+arg_0]
0x18004d905  add     rsp, 30h
0x18004d909  pop     rdi
0x18004d90a  retn
```
