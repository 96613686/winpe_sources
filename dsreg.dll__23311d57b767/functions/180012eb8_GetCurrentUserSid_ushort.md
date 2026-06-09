# GetCurrentUserSid(ushort * *)

- ea: `0x180012eb8`
- end: `0x180012f6f`
- name: `?GetCurrentUserSid@@YAJPEAPEAG@Z`
- size: `183`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `15`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f794`
- `0x180012d1c`
- `0x180053630`
- `0x1800543ec`
- `0x180056ccc`
- `0x180058074`
- `0x18006850c`
- `0x1800752b0`
- `0x180075868`
- `0x1800762e8`
- `0x180080100`
- `0x180081964`
- `0x180083004`
- `0x1800834f4`
- `0x1800b66dc`

## callees

- `0x1800084f4`
- `0x180009780`
- `0x180012eb8`
- `0x18001c9b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f1b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012f11`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012f11`

## string_xrefs

- `0x180012f2a`: `ConvertSidToStringSidW`
- `0x180012ef6`: `GetCurrentUserSid`
- `0x180012f31`: `GetCurrentUserSid`
- `0x180012eef`: `GetCurrentUserTokenInfo`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(LPWSTR *StringSid, __int64 a2, unsigned int *a3)
{
  int CurrentUserTokenInfo; // eax
  void *v5; // rsi
  unsigned int v6; // ebx
  DWORD LastError; // eax
  int v8; // edi
  void *lpMem; // [rsp+38h] [rbp+10h] BYREF

  lpMem = 0;
  CurrentUserTokenInfo = GetCurrentUserTokenInfo(TokenUser, &lpMem, a3);
  v5 = lpMem;
  v6 = CurrentUserTokenInfo;
  if ( CurrentUserTokenInfo >= 0 )
  {
    if ( !ConvertSidToStringSidW(*(PSID *)lpMem, StringSid) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError )
      {
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"GetCurrentUserSid",
          L"ConvertSidToStringSidW",
          LastError);
        if ( v8 > 0 )
          v6 = (unsigned __int16)v8 | 0x80070000;
        else
          v6 = v8;
      }
    }
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"GetCurrentUserSid",
      L"GetCurrentUserTokenInfo",
      (unsigned int)CurrentUserTokenInfo);
  }
  SafeFree(v5);
  return v6;
}

```

## disassembly

```asm
0x180012eb8  mov     rax, rsp
0x180012ebb  mov     [rax+8], rbx
0x180012ebf  mov     [rax+18h], rsi
0x180012ec3  push    rdi
0x180012ec4  sub     rsp, 20h
0x180012ec8  mov     rdi, rcx
0x180012ecb  mov     qword ptr [rax+10h], 0
0x180012ed3  mov     ecx, 1; TokenInformationClass
0x180012ed8  lea     rdx, [rax+10h]; void **
0x180012edc  call    ?GetCurrentUserTokenInfo@@YAJW4_TOKEN_INFORMATION_CLASS@@PEAPEAXPEAK@Z; GetCurrentUserTokenInfo(_TOKEN_INFORMATION_CLASS,void * *,ulong *)
0x180012ee1  mov     rsi, [rsp+28h+lpMem]
0x180012ee6  mov     ebx, eax
0x180012ee8  test    eax, eax
0x180012eea  jns     short loc_180012F0B
0x180012eec  mov     r9d, eax
0x180012eef  lea     r8, aGetcurrentuser_1; "GetCurrentUserTokenInfo"
0x180012ef6  lea     rdx, aGetcurrentuser_0; "GetCurrentUserSid"
0x180012efd  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180012f04  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180012f09  jmp     short loc_180012F55
0x180012f0b  mov     rcx, [rsi]; Sid
0x180012f0e  mov     rdx, rdi; StringSid
0x180012f11  call    cs:__imp_ConvertSidToStringSidW
0x180012f17  test    eax, eax
0x180012f19  jnz     short loc_180012F55
0x180012f1b  call    cs:__imp_GetLastError
0x180012f21  mov     edi, eax
0x180012f23  test    eax, eax
0x180012f25  jz      short loc_180012F55
0x180012f27  mov     r9d, eax
0x180012f2a  lea     r8, aConvertsidtost_0; "ConvertSidToStringSidW"
0x180012f31  lea     rdx, aGetcurrentuser_0; "GetCurrentUserSid"
0x180012f38  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180012f3f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180012f44  test    edi, edi
0x180012f46  jg      short loc_180012F4C
0x180012f48  mov     ebx, edi
0x180012f4a  jmp     short loc_180012F55
0x180012f4c  movzx   ebx, di
0x180012f4f  or      ebx, 80070000h
0x180012f55  mov     rcx, rsi; lpMem
0x180012f58  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180012f5d  mov     rsi, [rsp+28h+arg_10]
0x180012f62  mov     eax, ebx
0x180012f64  mov     rbx, [rsp+28h+arg_0]
0x180012f69  add     rsp, 20h
0x180012f6d  pop     rdi
0x180012f6e  retn
```
