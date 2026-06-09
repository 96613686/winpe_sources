# IsUserPhonebook

- ea: `0x180099d40`
- end: `0x180099df4`
- name: `IsUserPhonebook`
- size: `180`
- prototype: `__int64 __fastcall(void *, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800993e8`

## callees

- `0x18000d88c`
- `0x18004e580`
- `0x180099d40`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180099d9e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180099d9e`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180099d53`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180099d53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099da8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099d5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180099da8`

## pseudocode

```c
__int64 __fastcall IsUserPhonebook(void *a1, const WCHAR *a2)
{
  DWORD LastError; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // ebx

  if ( !a1 || !a2 )
  {
    LastError = GetLastError();
    if ( !LastError )
      return 0;
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v5 = 1097;
    goto LABEL_15;
  }
  if ( ImpersonateLoggedOnUser(a1) )
  {
    v6 = IsPersonalPhonebook(a2);
    RevertToSelf();
    return v6;
  }
  LastError = GetLastError();
  if ( LastError )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v5 = 1098;
LABEL_15:
      WPP_SF_d(v4[2], v5, WPP_425b3625ab793a6219f8039beff53b24_Traceguids, LastError);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180099d40  push    rbx
0x180099d42  sub     rsp, 20h
0x180099d46  mov     rbx, rdx
0x180099d49  test    rcx, rcx
0x180099d4c  jz      short loc_180099DA8
0x180099d4e  test    rdx, rdx
0x180099d51  jz      short loc_180099DA8
0x180099d53  call    cs:__imp_ImpersonateLoggedOnUser
0x180099d59  test    eax, eax
0x180099d5b  jnz     short loc_180099D94
0x180099d5d  call    cs:__imp_GetLastError
0x180099d63  test    eax, eax
0x180099d65  jz      loc_180099DEC
0x180099d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180099d72  lea     rdx, WPP_GLOBAL_Control
0x180099d79  cmp     rcx, rdx
0x180099d7c  jz      short loc_180099DEC
0x180099d7e  test    dword ptr [rcx+1Ch], 800h
0x180099d85  jz      short loc_180099DEC
0x180099d87  cmp     byte ptr [rcx+19h], 2
0x180099d8b  jb      short loc_180099DEC
0x180099d8d  mov     edx, 44Ah
0x180099d92  jmp     short loc_180099DD9
0x180099d94  mov     rcx, rbx; lpString2
0x180099d97  call    IsPersonalPhonebook
0x180099d9c  mov     ebx, eax
0x180099d9e  call    cs:__imp_RevertToSelf
0x180099da4  mov     eax, ebx
0x180099da6  jmp     short loc_180099DEE
0x180099da8  call    cs:__imp_GetLastError
0x180099dae  test    eax, eax
0x180099db0  jz      short loc_180099DEC
0x180099db2  mov     rcx, cs:WPP_GLOBAL_Control
0x180099db9  lea     rdx, WPP_GLOBAL_Control
0x180099dc0  cmp     rcx, rdx
0x180099dc3  jz      short loc_180099DEC
0x180099dc5  test    dword ptr [rcx+1Ch], 800h
0x180099dcc  jz      short loc_180099DEC
0x180099dce  cmp     byte ptr [rcx+19h], 2
0x180099dd2  jb      short loc_180099DEC
0x180099dd4  mov     edx, 449h
0x180099dd9  mov     rcx, [rcx+10h]
0x180099ddd  lea     r8, WPP_425b3625ab793a6219f8039beff53b24_Traceguids
0x180099de4  mov     r9d, eax
0x180099de7  call    WPP_SF_d
0x180099dec  xor     eax, eax
0x180099dee  add     rsp, 20h
0x180099df2  pop     rbx
0x180099df3  retn
```
