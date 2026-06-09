# CCheckGroupMembership::IsAdministrator(int *)

- ea: `0x180019074`
- end: `0x1800191a5`
- name: `?IsAdministrator@CCheckGroupMembership@@SAJPEAH@Z`
- size: `305`
- prototype: `__int64 __fastcall(PBOOL IsMember)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019330`

## callees

- `0x180019074`
- `0x180055880`
- `0x180055940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001913d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001916a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001913d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001916a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019188`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180019188`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180019133`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180019133`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001911d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001911d`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800190bd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800190fa`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800190bd`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800190fa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180019160`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180019160`

## pseudocode

```c
__int64 __fastcall CCheckGroupMembership::IsAdministrator(PBOOL IsMember)
{
  unsigned int v3; // ebx
  unsigned __int64 v4; // rax
  void *v5; // rsp
  signed int LastError; // eax
  HANDLE CurrentThread; // rax
  signed int v8; // eax
  signed int v9; // eax
  DWORD cbSid; // [rsp+20h] [rbp+0h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp+8h] BYREF

  if ( !IsMember )
    return 2147500035LL;
  v3 = 0;
  *IsMember = 0;
  TokenHandle = 0;
  cbSid = 0;
  CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, 0, &cbSid);
  v4 = cbSid + 1 + 15LL;
  if ( v4 <= cbSid + 1 )
    v4 = 0xFFFFFFFFFFFFFF0LL;
  v5 = alloca(v4 & 0xFFFFFFFFFFFFFFF0uLL);
  if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, &cbSid, &cbSid) )
    goto LABEL_9;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( !v3 )
  {
LABEL_9:
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      goto LABEL_21;
    v8 = GetLastError();
    v3 = v8;
    if ( v8 > 0 )
      v3 = (unsigned __int16)v8 | 0x80070000;
    if ( !v3 )
    {
LABEL_21:
      if ( !CheckTokenMembership(TokenHandle, &cbSid, IsMember) )
      {
        v9 = GetLastError();
        v3 = v9;
        if ( v9 > 0 )
          v3 = (unsigned __int16)v9 | 0x80070000;
      }
    }
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x180019074  push    rbp
0x180019076  push    rbx
0x180019077  push    rsi
0x180019078  push    rdi
0x180019079  sub     rsp, 48h
0x18001907d  lea     rbp, [rsp+20h]
0x180019082  mov     rax, cs:__security_cookie
0x180019089  xor     rax, rbp
0x18001908c  mov     [rbp+40h+var_30], rax
0x180019090  mov     rdi, rcx
0x180019093  test    rcx, rcx
0x180019096  jnz     short loc_1800190A2
0x180019098  mov     eax, 80004003h
0x18001909d  jmp     loc_180019190
0x1800190a2  xor     ebx, ebx
0x1800190a4  mov     dword ptr [rcx], 0
0x1800190aa  lea     r9, [rbp+40h+cbSid]; cbSid
0x1800190ae  mov     [rbp+40h+TokenHandle], rbx
0x1800190b2  xor     r8d, r8d; pSid
0x1800190b5  mov     [rbp+40h+cbSid], ebx
0x1800190b8  xor     edx, edx; DomainSid
0x1800190ba  lea     ecx, [rbx+1Ah]; WellKnownSidType
0x1800190bd  call    cs:__imp_CreateWellKnownSid
0x1800190c3  mov     eax, [rbp+40h+cbSid]
0x1800190c6  inc     eax
0x1800190c8  mov     ecx, eax
0x1800190ca  add     rax, 0Fh
0x1800190ce  cmp     rax, rcx
0x1800190d1  ja      short loc_1800190DD
0x1800190d3  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800190dd  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800190e1  call    _alloca_probe
0x1800190e6  sub     rsp, rax
0x1800190e9  lea     r9, [rbp+40h+cbSid]; cbSid
0x1800190ed  xor     edx, edx; DomainSid
0x1800190ef  lea     rsi, [rsp+60h+cbSid]
0x1800190f4  mov     r8, rsi; pSid
0x1800190f7  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800190fa  call    cs:__imp_CreateWellKnownSid
0x180019100  test    eax, eax
0x180019102  jnz     short loc_18001911D
0x180019104  call    cs:__imp_GetLastError
0x18001910a  mov     ebx, eax
0x18001910c  test    eax, eax
0x18001910e  jle     short loc_180019119
0x180019110  movzx   ebx, ax
0x180019113  or      ebx, 80070000h
0x180019119  test    ebx, ebx
0x18001911b  jnz     short loc_18001917F
0x18001911d  call    cs:__imp_GetCurrentThread
0x180019123  mov     edx, 8; DesiredAccess
0x180019128  lea     r9, [rbp+40h+TokenHandle]; TokenHandle
0x18001912c  mov     rcx, rax; ThreadHandle
0x18001912f  lea     r8d, [rdx-7]; OpenAsSelf
0x180019133  call    cs:__imp_OpenThreadToken
0x180019139  test    eax, eax
0x18001913b  jnz     short loc_180019156
0x18001913d  call    cs:__imp_GetLastError
0x180019143  mov     ebx, eax
0x180019145  test    eax, eax
0x180019147  jle     short loc_180019152
0x180019149  movzx   ebx, ax
0x18001914c  or      ebx, 80070000h
0x180019152  test    ebx, ebx
0x180019154  jnz     short loc_18001917F
0x180019156  mov     rcx, [rbp+40h+TokenHandle]; TokenHandle
0x18001915a  mov     r8, rdi; IsMember
0x18001915d  mov     rdx, rsi; SidToCheck
0x180019160  call    cs:__imp_CheckTokenMembership
0x180019166  test    eax, eax
0x180019168  jnz     short loc_18001917F
0x18001916a  call    cs:__imp_GetLastError
0x180019170  mov     ebx, eax
0x180019172  test    eax, eax
0x180019174  jle     short loc_18001917F
0x180019176  movzx   ebx, ax
0x180019179  or      ebx, 80070000h
0x18001917f  mov     rcx, [rbp+40h+TokenHandle]; hObject
0x180019183  test    rcx, rcx
0x180019186  jz      short loc_18001918E
0x180019188  call    cs:__imp_CloseHandle
0x18001918e  mov     eax, ebx
0x180019190  mov     rcx, [rbp+40h+var_30]
0x180019194  xor     rcx, rbp; StackCookie
0x180019197  call    __security_check_cookie
0x18001919c  lea     rsp, [rbp+28h]
0x1800191a0  pop     rdi
0x1800191a1  pop     rsi
0x1800191a2  pop     rbx
0x1800191a3  pop     rbp
0x1800191a4  retn
```
