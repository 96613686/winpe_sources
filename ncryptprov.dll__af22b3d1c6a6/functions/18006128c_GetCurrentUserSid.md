# GetCurrentUserSid

- ea: `0x18006128c`
- end: `0x1800613c3`
- name: `GetCurrentUserSid`
- size: `311`
- prototype: `__int64 __fastcall(PSID pDestinationSid)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c3a0`

## callees

- `0x18000af80`
- `0x1800110b8`
- `0x180038970`
- `0x18006128c`
- `0x180062310`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006131c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061350`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006131c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061350`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061393`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180061393`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180061340`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180061340`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006130c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006130c`

## string_xrefs

- `0x180061366`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(PSID pDestinationSid)
{
  DWORD v2; // eax
  DWORD v3; // ebx
  __int64 v4; // r9
  __int64 v5; // rcx
  signed int LastError; // eax
  HANDLE TokenHandle; // [rsp+30h] [rbp-88h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  ReturnLength = 0;
  TokenHandle = 0;
  memset_0(TokenInformation, 0, 0x58u);
  v2 = OpenCallerToken(8u, &TokenHandle);
  v3 = v2;
  if ( v2 )
  {
    v4 = 338;
    v5 = v2;
  }
  else
  {
    if ( !GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError <= 0 )
        goto LABEL_11;
      v3 = (unsigned __int16)LastError;
      goto LABEL_10;
    }
    v3 = 0;
    if ( CopySid(0x44u, pDestinationSid, TokenInformation[0]) )
      goto LABEL_11;
    v3 = GetLastError();
    v5 = v3;
    v4 = 358;
  }
  DebugTraceError(v5, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c", v4);
  if ( (int)v3 <= 0 )
    goto LABEL_11;
  v3 = (unsigned __int16)v3;
LABEL_10:
  v3 |= 0x80070000;
LABEL_11:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x18006128c  mov     [rsp+arg_8], rbx
0x180061291  push    rsi
0x180061292  sub     rsp, 0B0h
0x180061299  mov     rax, cs:__security_cookie
0x1800612a0  xor     rax, rsp
0x1800612a3  mov     [rsp+0B8h+var_18], rax
0x1800612ab  xor     edx, edx; Val
0x1800612ad  mov     [rsp+0B8h+var_80], 0
0x1800612b5  mov     rsi, rcx
0x1800612b8  mov     [rsp+0B8h+TokenHandle], 0
0x1800612c1  lea     rcx, [rsp+0B8h+TokenInformation]; void *
0x1800612c6  lea     r8d, [rdx+58h]; Size
0x1800612ca  call    memset_0
0x1800612cf  lea     rdx, [rsp+0B8h+TokenHandle]
0x1800612d4  mov     ecx, 8; DesiredAccess
0x1800612d9  call    OpenCallerToken
0x1800612de  mov     ebx, eax
0x1800612e0  test    eax, eax
0x1800612e2  jz      short loc_1800612EE
0x1800612e4  mov     r9d, 152h
0x1800612ea  mov     ecx, eax
0x1800612ec  jmp     short loc_180061366
0x1800612ee  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800612f3  lea     rax, [rsp+0B8h+var_80]
0x1800612f8  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800612fe  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180061303  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180061308  lea     edx, [r9-57h]; TokenInformationClass
0x18006130c  call    cs:__imp_GetTokenInformation
0x180061313  nop     dword ptr [rax+rax+00h]
0x180061318  test    eax, eax
0x18006131a  jnz     short loc_180061333
0x18006131c  call    cs:__imp_GetLastError
0x180061323  nop     dword ptr [rax+rax+00h]
0x180061328  mov     ebx, eax
0x18006132a  test    eax, eax
0x18006132c  jle     short loc_180061386
0x18006132e  movzx   ebx, ax
0x180061331  jmp     short loc_180061380
0x180061333  mov     r8, [rsp+0B8h+TokenInformation]; pSourceSid
0x180061338  xor     ebx, ebx
0x18006133a  mov     rdx, rsi; pDestinationSid
0x18006133d  lea     ecx, [rbx+44h]; nDestinationSidLength
0x180061340  call    cs:__imp_CopySid
0x180061347  nop     dword ptr [rax+rax+00h]
0x18006134c  test    eax, eax
0x18006134e  jnz     short loc_180061386
0x180061350  call    cs:__imp_GetLastError
0x180061357  nop     dword ptr [rax+rax+00h]
0x18006135c  mov     ebx, eax
0x18006135e  mov     ecx, eax
0x180061360  mov     r9d, 166h
0x180061366  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006136d  lea     rdx, aDwreturn; "dwReturn"
0x180061374  call    DebugTraceError
0x180061379  test    ebx, ebx
0x18006137b  jle     short loc_180061386
0x18006137d  movzx   ebx, bx
0x180061380  or      ebx, 80070000h
0x180061386  cmp     [rsp+0B8h+TokenHandle], 0
0x18006138c  jz      short loc_18006139F
0x18006138e  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x180061393  call    cs:__imp_CloseHandle
0x18006139a  nop     dword ptr [rax+rax+00h]
0x18006139f  mov     eax, ebx
0x1800613a1  mov     rcx, [rsp+0B8h+var_18]
0x1800613a9  xor     rcx, rsp; StackCookie
0x1800613ac  call    __security_check_cookie
0x1800613b1  mov     rbx, [rsp+0B8h+arg_8]
0x1800613b9  add     rsp, 0B0h
0x1800613c0  pop     rsi
0x1800613c1  retn
```
