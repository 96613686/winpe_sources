# GetCallerSid

- ea: `0x140009e84`
- end: `0x14000a07d`
- name: `GetCallerSid`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140008f78`

## callees

- `0x140009e84`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x140009f17`
- `ADVAPI32!GetTokenInformation` at `0x140009f97`
- `ADVAPI32!GetTokenInformation` at `0x140009f17`
- `ADVAPI32!GetTokenInformation` at `0x140009f97`
- `ADVAPI32!OpenThreadToken` at `0x140009eda`
- `ADVAPI32!OpenThreadToken` at `0x140009eda`
- `ADVAPI32!GetLengthSid` at `0x140009fc7`
- `ADVAPI32!GetLengthSid` at `0x140009fc7`
- `ADVAPI32!IsValidSid` at `0x14000a00b`
- `ADVAPI32!IsValidSid` at `0x14000a00b`
- `ADVAPI32!CopySid` at `0x140009ffc`
- `ADVAPI32!CopySid` at `0x140009ffc`
- `KERNEL32!CloseHandle` at `0x14000a04f`
- `KERNEL32!CloseHandle` at `0x14000a04f`
- `KERNEL32!LocalAlloc` at `0x140009f60`
- `KERNEL32!LocalAlloc` at `0x140009fd9`
- `KERNEL32!LocalAlloc` at `0x140009f60`
- `KERNEL32!LocalAlloc` at `0x140009fd9`
- `KERNEL32!GetCurrentThread` at `0x140009ebf`
- `KERNEL32!GetCurrentThread` at `0x140009ebf`
- `KERNEL32!LocalFree` at `0x14000a028`
- `KERNEL32!LocalFree` at `0x14000a037`
- `KERNEL32!LocalFree` at `0x14000a028`
- `KERNEL32!LocalFree` at `0x14000a037`
- `KERNEL32!GetLastError` at `0x140009f2b`
- `KERNEL32!GetLastError` at `0x140009fa7`
- `KERNEL32!GetLastError` at `0x140009f2b`
- `KERNEL32!GetLastError` at `0x140009fa7`
- `ole32!CoImpersonateClient` at `0x140009e99`
- `ole32!CoImpersonateClient` at `0x140009e99`
- `ole32!CoRevertToSelf` at `0x14000a05b`
- `ole32!CoRevertToSelf` at `0x14000a05b`

## pseudocode

```c
__int64 __fastcall GetCallerSid(_QWORD *a1)
{
  int v2; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  PSID *v5; // rsi
  signed int v6; // eax
  DWORD LengthSid; // ebp
  HLOCAL v8; // rax
  void *v9; // rdi
  DWORD TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  v2 = CoImpersonateClient();
  if ( v2 >= 0 )
  {
    TokenHandle = 0;
    *a1 = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      TokenInformationLength = 0;
      if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
      {
        v2 = -2147418113;
      }
      else
      {
        LastError = GetLastError();
        if ( LastError == 122 )
        {
          v5 = (PSID *)LocalAlloc(0x40u, TokenInformationLength);
          if ( v5 )
          {
            if ( GetTokenInformation(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength) )
            {
              LengthSid = GetLengthSid(*v5);
              v8 = LocalAlloc(0x40u, LengthSid);
              v9 = v8;
              if ( v8 )
              {
                CopySid(LengthSid, v8, *v5);
                if ( IsValidSid(v9) )
                {
                  *a1 = v9;
                }
                else
                {
                  v2 = -2147467259;
                  LocalFree(v9);
                }
              }
              else
              {
                v2 = -2147024882;
              }
            }
            else
            {
              v6 = GetLastError();
              v2 = v6;
              if ( v6 > 0 )
                v2 = (unsigned __int16)v6 | 0x80070000;
            }
            LocalFree(v5);
          }
          else
          {
            v2 = -2147024882;
          }
        }
        else if ( LastError > 0 )
        {
          v2 = (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          v2 = LastError;
        }
      }
      CloseHandle(TokenHandle);
    }
    else
    {
      v2 = -2147467259;
    }
    CoRevertToSelf();
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140009e84  mov     [rsp+arg_0], rbx
0x140009e89  mov     [rsp+arg_18], rbp
0x140009e8e  push    rsi
0x140009e8f  push    rdi
0x140009e90  push    r14
0x140009e92  sub     rsp, 30h
0x140009e96  mov     r14, rcx
0x140009e99  call    cs:__imp_CoImpersonateClient
0x140009ea0  nop     dword ptr [rax+rax+00h]
0x140009ea5  mov     ebx, eax
0x140009ea7  test    eax, eax
0x140009ea9  js      loc_14000A067
0x140009eaf  mov     [rsp+48h+TokenHandle], 0
0x140009eb8  mov     qword ptr [r14], 0
0x140009ebf  call    cs:__imp_GetCurrentThread
0x140009ec6  nop     dword ptr [rax+rax+00h]
0x140009ecb  xor     r8d, r8d; OpenAsSelf
0x140009ece  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x140009ed3  mov     rcx, rax; ThreadHandle
0x140009ed6  lea     edx, [r8+8]; DesiredAccess
0x140009eda  call    cs:__imp_OpenThreadToken
0x140009ee1  nop     dword ptr [rax+rax+00h]
0x140009ee6  test    eax, eax
0x140009ee8  jnz     short loc_140009EF4
0x140009eea  mov     ebx, 80004005h
0x140009eef  jmp     loc_14000A05B
0x140009ef4  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x140009ef9  lea     rax, [rsp+48h+TokenInformationLength]
0x140009efe  xor     r9d, r9d; TokenInformationLength
0x140009f01  mov     [rsp+48h+TokenInformationLength], 0
0x140009f09  xor     r8d, r8d; TokenInformation
0x140009f0c  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140009f11  lea     ebp, [r9+1]
0x140009f15  mov     edx, ebp; TokenInformationClass
0x140009f17  call    cs:__imp_GetTokenInformation
0x140009f1e  nop     dword ptr [rax+rax+00h]
0x140009f23  test    eax, eax
0x140009f25  jnz     loc_14000A045
0x140009f2b  call    cs:__imp_GetLastError
0x140009f32  nop     dword ptr [rax+rax+00h]
0x140009f37  cmp     eax, 7Ah ; 'z'
0x140009f3a  jz      short loc_140009F55
0x140009f3c  test    eax, eax
0x140009f3e  jg      short loc_140009F47
0x140009f40  mov     ebx, eax
0x140009f42  jmp     loc_14000A04A
0x140009f47  movzx   ebx, ax
0x140009f4a  or      ebx, 80070000h
0x140009f50  jmp     loc_14000A04A
0x140009f55  mov     edx, [rsp+48h+TokenInformationLength]; uBytes
0x140009f59  mov     edi, 40h ; '@'
0x140009f5e  mov     ecx, edi; uFlags
0x140009f60  call    cs:__imp_LocalAlloc
0x140009f67  nop     dword ptr [rax+rax+00h]
0x140009f6c  mov     rsi, rax
0x140009f6f  test    rax, rax
0x140009f72  jnz     short loc_140009F7E
0x140009f74  mov     ebx, 8007000Eh
0x140009f79  jmp     loc_14000A04A
0x140009f7e  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x140009f83  lea     rax, [rsp+48h+TokenInformationLength]
0x140009f88  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x140009f8d  mov     r8, rsi; TokenInformation
0x140009f90  mov     edx, ebp; TokenInformationClass
0x140009f92  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140009f97  call    cs:__imp_GetTokenInformation
0x140009f9e  nop     dword ptr [rax+rax+00h]
0x140009fa3  test    eax, eax
0x140009fa5  jnz     short loc_140009FC4
0x140009fa7  call    cs:__imp_GetLastError
0x140009fae  nop     dword ptr [rax+rax+00h]
0x140009fb3  mov     ebx, eax
0x140009fb5  test    eax, eax
0x140009fb7  jle     short loc_14000A034
0x140009fb9  movzx   ebx, ax
0x140009fbc  or      ebx, 80070000h
0x140009fc2  jmp     short loc_14000A034
0x140009fc4  mov     rcx, [rsi]; pSid
0x140009fc7  call    cs:__imp_GetLengthSid
0x140009fce  nop     dword ptr [rax+rax+00h]
0x140009fd3  mov     edx, eax; uBytes
0x140009fd5  mov     ecx, edi; uFlags
0x140009fd7  mov     ebp, eax
0x140009fd9  call    cs:__imp_LocalAlloc
0x140009fe0  nop     dword ptr [rax+rax+00h]
0x140009fe5  mov     rdi, rax
0x140009fe8  test    rax, rax
0x140009feb  jnz     short loc_140009FF4
0x140009fed  mov     ebx, 8007000Eh
0x140009ff2  jmp     short loc_14000A034
0x140009ff4  mov     r8, [rsi]; pSourceSid
0x140009ff7  mov     rdx, rdi; pDestinationSid
0x140009ffa  mov     ecx, ebp; nDestinationSidLength
0x140009ffc  call    cs:__imp_CopySid
0x14000a003  nop     dword ptr [rax+rax+00h]
0x14000a008  mov     rcx, rdi; pSid
0x14000a00b  call    cs:__imp_IsValidSid
0x14000a012  nop     dword ptr [rax+rax+00h]
0x14000a017  test    eax, eax
0x14000a019  jz      short loc_14000A020
0x14000a01b  mov     [r14], rdi
0x14000a01e  jmp     short loc_14000A034
0x14000a020  mov     rcx, rdi; hMem
0x14000a023  mov     ebx, 80004005h
0x14000a028  call    cs:__imp_LocalFree
0x14000a02f  nop     dword ptr [rax+rax+00h]
0x14000a034  mov     rcx, rsi; hMem
0x14000a037  call    cs:__imp_LocalFree
0x14000a03e  nop     dword ptr [rax+rax+00h]
0x14000a043  jmp     short loc_14000A04A
0x14000a045  mov     ebx, 8000FFFFh
0x14000a04a  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x14000a04f  call    cs:__imp_CloseHandle
0x14000a056  nop     dword ptr [rax+rax+00h]
0x14000a05b  call    cs:__imp_CoRevertToSelf
0x14000a062  nop     dword ptr [rax+rax+00h]
0x14000a067  mov     rbp, [rsp+48h+arg_18]
0x14000a06c  mov     eax, ebx
0x14000a06e  mov     rbx, [rsp+48h+arg_0]
0x14000a073  add     rsp, 30h
0x14000a077  pop     r14
0x14000a079  pop     rdi
0x14000a07a  pop     rsi
0x14000a07b  retn
```
