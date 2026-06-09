# NgcUtils::IsCurrentSessionRemote(bool *)

- ea: `0x1800176bc`
- end: `0x180017756`
- name: `?IsCurrentSessionRemote@NgcUtils@@YAJPEA_N@Z`
- size: `154`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180035688`

## callees

- `0x1800176bc`
- `0x180028360`
- `0x18002f338`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017701`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017701`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180017733`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180017733`

## string_xrefs

- `0x180017715`: `onecore\ds\security\ngc\utils\common\lib\tokenutils.cpp`

## pseudocode

```c
__int64 __fastcall NgcUtils::IsCurrentSessionRemote(NgcUtils *this, bool *a2)
{
  const char *v3; // r9
  __int64 v4; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v7; // [rsp+40h] [rbp+8h] BYREF
  unsigned int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  *(_BYTE *)this = 0;
  if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent(this, a2) )
  {
    TokenInformation = 0;
    ReturnLength = 0;
    if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    {
      v4 = 276;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v4,
               (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tokenutils.cpp",
               v3);
    }
    v7 = 0;
    if ( !(unsigned __int8)WinStationIsSessionRemoteable(0, TokenInformation, &v7) )
    {
      v4 = 283;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v4,
               (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\tokenutils.cpp",
               v3);
    }
    *(_BYTE *)this = v7 != 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800176bc  push    rbx
0x1800176be  sub     rsp, 30h
0x1800176c2  mov     rbx, rcx
0x1800176c5  mov     byte ptr [rcx], 0
0x1800176c8  call    IsWinStationIsSessionRemoteablePresent
0x1800176cd  test    al, al
0x1800176cf  jz      short loc_18001774E
0x1800176d1  mov     r9d, 4; TokenInformationLength
0x1800176d7  mov     [rsp+38h+TokenInformation], 0
0x1800176df  lea     rax, [rsp+38h+arg_10]
0x1800176e4  mov     [rsp+38h+arg_10], 0
0x1800176ec  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800176f1  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800176f6  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800176fd  lea     edx, [r9+8]; TokenInformationClass
0x180017701  call    cs:__imp_GetTokenInformation
0x180017707  test    eax, eax
0x180017709  jnz     short loc_180017723
0x18001770b  mov     edx, 114h; void *
0x180017710  mov     rcx, [rsp+38h]; this
0x180017715  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18001771c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017721  jmp     short loc_180017750
0x180017723  mov     edx, [rsp+38h+TokenInformation]
0x180017727  lea     r8, [rsp+38h+arg_0]
0x18001772c  xor     ecx, ecx
0x18001772e  mov     [rsp+38h+arg_0], 0
0x180017733  call    cs:__imp_WinStationIsSessionRemoteable
0x180017739  test    al, al
0x18001773b  jnz     short loc_180017744
0x18001773d  mov     edx, 11Bh
0x180017742  jmp     short loc_180017710
0x180017744  cmp     [rsp+38h+arg_0], 0
0x180017749  setnz   al
0x18001774c  mov     [rbx], al
0x18001774e  xor     eax, eax
0x180017750  add     rsp, 30h
0x180017754  pop     rbx
0x180017755  retn
```
