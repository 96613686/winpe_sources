# AdvertisingIdHelpers::GetCurrentUserSid(Windows::Internal::String *)

- ea: `0x180001790`
- end: `0x18000190b`
- name: `?GetCurrentUserSid@AdvertisingIdHelpers@@YAJPEAVString@Internal@Windows@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(AdvertisingIdHelpers *__hidden this, struct Windows::Internal::String *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001380`
- `0x180001d20`
- `0x180002b70`

## callees

- `0x180001790`
- `0x180006324`
- `0x180009d9e`
- `0x180009dd0`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800018a3`
- `ntdll!RtlFreeUnicodeString` at `0x1800018a3`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180001849`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180001849`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800017dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800017dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800017ef`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800017ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800018d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800018d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000182e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000182e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001898`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001898`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180001886`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000186f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000186f`

## pseudocode

```c
__int64 __fastcall AdvertisingIdHelpers::GetCurrentUserSid(HSTRING *this, struct Windows::Internal::String *a2)
{
  HANDLE CurrentProcess; // rax
  NTSTATUS v4; // ebx
  HRESULT v5; // eax
  unsigned int v6; // ebx
  HSTRING v7; // rcx
  signed int LastError; // eax
  int ReturnLength; // [rsp+20h] [rbp-B8h]
  DWORD v11; // [rsp+30h] [rbp-A8h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-98h] BYREF
  _UNICODE_STRING UnicodeString; // [rsp+48h] [rbp-90h] BYREF
  PSID TokenInformation[12]; // [rsp+60h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  TokenHandle = 0;
  v11 = 0;
  UnicodeString = 0;
  memset_0(TokenInformation, 0, 0x58u);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle)
    && (memset_0(TokenInformation, 0, 0x58u), GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &v11)) )
  {
    v4 = RtlConvertSidToUnicodeString(&UnicodeString, TokenInformation[0], 1u);
    if ( v4 < 0 )
    {
      v6 = v4 | 0x10000000;
    }
    else
    {
      string = 0;
      v5 = WindowsCreateString(UnicodeString.Buffer, UnicodeString.Length >> 1, &string);
      v6 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB0,
          (unsigned int)"onecore\\base\\appmodel\\advertisingid\\helper\\advertisingidhelpers.cpp",
          (const char *)(unsigned int)v5,
          ReturnLength);
      }
      else
      {
        v7 = *this;
        *this = string;
        WindowsDeleteString(v7);
        v6 = 0;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  RtlFreeUnicodeString(&UnicodeString);
  return v6;
}

```

## disassembly

```asm
0x180001790  mov     [rsp+arg_8], rbx
0x180001795  mov     [rsp+arg_10], rsi
0x18000179a  push    rdi
0x18000179b  sub     rsp, 0D0h
0x1800017a2  mov     rax, cs:__security_cookie
0x1800017a9  xor     rax, rsp
0x1800017ac  mov     [rsp+0D8h+var_18], rax
0x1800017b4  mov     rdi, rcx
0x1800017b7  xor     esi, esi
0x1800017b9  xorps   xmm0, xmm0
0x1800017bc  mov     [rsp+0D8h+TokenHandle], rsi
0x1800017c1  lea     rcx, [rsp+0D8h+TokenInformation]; void *
0x1800017c6  mov     [rsp+0D8h+var_A8], esi
0x1800017ca  xor     edx, edx; Val
0x1800017cc  mov     r8d, 58h ; 'X'; Size
0x1800017d2  movups  xmmword ptr [rsp+0D8h+UnicodeString.Length], xmm0
0x1800017d7  call    memset_0
0x1800017dc  call    cs:__imp_GetCurrentProcess
0x1800017e2  lea     r8, [rsp+0D8h+TokenHandle]; TokenHandle
0x1800017e7  mov     edx, 20008h; DesiredAccess
0x1800017ec  mov     rcx, rax; ProcessHandle
0x1800017ef  call    cs:__imp_OpenProcessToken
0x1800017f5  test    eax, eax
0x1800017f7  jz      loc_1800018D0
0x1800017fd  xor     edx, edx; Val
0x1800017ff  lea     rcx, [rsp+0D8h+TokenInformation]; void *
0x180001804  mov     r8d, 58h ; 'X'; Size
0x18000180a  call    memset_0
0x18000180f  mov     rcx, [rsp+0D8h+TokenHandle]; TokenHandle
0x180001814  lea     rax, [rsp+0D8h+var_A8]
0x180001819  mov     r9d, 58h ; 'X'; TokenInformationLength
0x18000181f  mov     qword ptr [rsp+0D8h+ReturnLength], rax; int
0x180001824  lea     r8, [rsp+0D8h+TokenInformation]; TokenInformation
0x180001829  mov     edx, 1; TokenInformationClass
0x18000182e  call    cs:__imp_GetTokenInformation
0x180001834  test    eax, eax
0x180001836  jz      loc_1800018D0
0x18000183c  mov     rdx, [rsp+0D8h+TokenInformation]; Sid
0x180001841  lea     rcx, [rsp+0D8h+UnicodeString]; UnicodeString
0x180001846  mov     r8b, 1; AllocateDestinationString
0x180001849  call    cs:__imp_RtlConvertSidToUnicodeString
0x18000184f  mov     ebx, eax
0x180001851  test    eax, eax
0x180001853  js      loc_1800018E7
0x180001859  movzx   edx, [rsp+0D8h+UnicodeString.Length]
0x18000185e  lea     r8, [rsp+0D8h+string]; string
0x180001863  mov     rcx, [rsp+0D8h+UnicodeString.Buffer]; sourceString
0x180001868  shr     edx, 1; length
0x18000186a  mov     [rsp+0D8h+string], rsi
0x18000186f  call    cs:__imp_WindowsCreateString
0x180001875  mov     ebx, eax
0x180001877  test    eax, eax
0x180001879  js      short loc_1800018ED
0x18000187b  mov     rax, [rsp+0D8h+string]
0x180001880  mov     rcx, [rdi]; string
0x180001883  mov     [rdi], rax
0x180001886  call    cs:__imp_WindowsDeleteString
0x18000188c  mov     ebx, esi
0x18000188e  mov     rcx, [rsp+0D8h+TokenHandle]; hObject
0x180001893  test    rcx, rcx
0x180001896  jz      short loc_18000189E
0x180001898  call    cs:__imp_CloseHandle
0x18000189e  lea     rcx, [rsp+0D8h+UnicodeString]; UnicodeString
0x1800018a3  call    cs:__imp_RtlFreeUnicodeString
0x1800018a9  mov     eax, ebx
0x1800018ab  mov     rcx, [rsp+0D8h+var_18]
0x1800018b3  xor     rcx, rsp; StackCookie
0x1800018b6  call    __security_check_cookie
0x1800018bb  lea     r11, [rsp+0D8h+var_8]
0x1800018c3  mov     rbx, [r11+18h]
0x1800018c7  mov     rsi, [r11+20h]
0x1800018cb  mov     rsp, r11
0x1800018ce  pop     rdi
0x1800018cf  retn
0x1800018d0  call    cs:__imp_GetLastError
0x1800018d6  mov     ebx, eax
0x1800018d8  test    eax, eax
0x1800018da  jle     short loc_18000188E
0x1800018dc  movzx   ebx, ax
0x1800018df  or      ebx, 80070000h
0x1800018e5  jmp     short loc_18000188E
0x1800018e7  bts     ebx, 1Ch
0x1800018eb  jmp     short loc_18000188E
0x1800018ed  mov     rcx, [rsp+0D8h]; this
0x1800018f5  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\advertisingid"...
0x1800018fc  mov     r9d, eax; char *
0x1800018ff  mov     edx, 0B0h; void *
0x180001904  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001909  jmp     short loc_18000188E
```
