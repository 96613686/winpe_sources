# NgcUtils::CallerIsAppContainer(bool *)

- ea: `0x1800187a4`
- end: `0x180018892`
- name: `?CallerIsAppContainer@NgcUtils@@YAJPEA_N@Z`
- size: `238`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010450`

## callees

- `0x18000113c`
- `0x180003080`
- `0x1800187a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018849`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018849`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800187f1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800187f1`

## pseudocode

```c
signed int __fastcall NgcUtils::CallerIsAppContainer(NgcUtils *this, bool *a2)
{
  DWORD LastError; // eax
  signed int result; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-50h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-4Ch] BYREF
  DWORD v7; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v8; // [rsp+40h] [rbp-40h] BYREF
  DWORD *v9; // [rsp+60h] [rbp-20h]
  __int64 v10; // [rsp+68h] [rbp-18h]

  TokenInformation = 0;
  ReturnLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    if ( ReturnLength == 4 )
    {
      *(_BYTE *)this = TokenInformation != 0;
      return 0;
    }
    else
    {
      return -2147467259;
    }
  }
  else
  {
    if ( (unsigned int)dword_180075000 > 2 )
    {
      LastError = GetLastError();
      v10 = 4;
      v7 = LastError;
      v9 = &v7;
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180075000, (unsigned __int8 *)byte_180068A01, 0, 0, 3u, &v8);
    }
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1800187a4  mov     [rsp-8+arg_8], rbx
0x1800187a9  push    rbp
0x1800187aa  mov     rbp, rsp
0x1800187ad  sub     rsp, 80h
0x1800187b4  mov     rax, cs:__security_cookie
0x1800187bb  xor     rax, rsp
0x1800187be  mov     [rbp+var_10], rax
0x1800187c2  mov     r9d, 4; TokenInformationLength
0x1800187c8  mov     [rbp+TokenInformation], 0
0x1800187cf  mov     rbx, rcx
0x1800187d2  mov     [rbp+var_50], 0
0x1800187d9  lea     rax, [rbp+var_50]
0x1800187dd  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800187e4  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800187e8  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x1800187ed  lea     edx, [r9+19h]; TokenInformationClass
0x1800187f1  call    cs:__imp_GetTokenInformation
0x1800187f7  test    eax, eax
0x1800187f9  jnz     short loc_18001885D
0x1800187fb  mov     eax, cs:dword_180075000
0x180018801  cmp     eax, 2
0x180018804  jbe     short loc_180018849
0x180018806  call    cs:__imp_GetLastError
0x18001880c  xor     r9d, r9d
0x18001880f  mov     [rbp+var_18], 4
0x180018817  mov     [rbp+var_48], eax
0x18001881a  lea     rdx, byte_180068A01
0x180018821  lea     rax, [rbp+var_48]
0x180018825  xor     r8d, r8d
0x180018828  mov     [rbp+var_20], rax
0x18001882c  lea     rcx, dword_180075000
0x180018833  lea     rax, [rbp+var_40]
0x180018837  mov     [rsp+80h+var_58], rax
0x18001883c  mov     dword ptr [rsp+80h+ReturnLength], 3
0x180018844  call    _tlgWriteTransfer_EventWriteTransfer
0x180018849  call    cs:__imp_GetLastError
0x18001884f  test    eax, eax
0x180018851  jle     short loc_180018875
0x180018853  movzx   eax, ax
0x180018856  or      eax, 80070000h
0x18001885b  jmp     short loc_180018875
0x18001885d  cmp     [rbp+var_50], 4
0x180018861  jz      short loc_18001886A
0x180018863  mov     eax, 80004005h
0x180018868  jmp     short loc_180018875
0x18001886a  cmp     [rbp+TokenInformation], 0
0x18001886e  setnz   al
0x180018871  mov     [rbx], al
0x180018873  xor     eax, eax
0x180018875  mov     rcx, [rbp+var_10]
0x180018879  xor     rcx, rsp; StackCookie
0x18001887c  call    __security_check_cookie
0x180018881  mov     rbx, [rsp+80h+arg_8]
0x180018889  add     rsp, 80h
0x180018890  pop     rbp
0x180018891  retn
```
