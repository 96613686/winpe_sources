# Tsf3OverrideUtil::IsRunningAsSystem(void)

- ea: `0x180076ff8`
- end: `0x18007709c`
- name: `?IsRunningAsSystem@Tsf3OverrideUtil@@YA_NXZ`
- size: `164`
- prototype: `bool __fastcall(Tsf3OverrideUtil *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800d1d78`
- `0x1800d22c0`

## callees

- `0x180076ff8`
- `0x1800d2958`
- `0x1800d2978`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007700c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18007700c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077088`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180077088`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007705c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18007705c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007703b`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x18007703b`

## pseudocode

```c
bool __fastcall Tsf3OverrideUtil::IsRunningAsSystem(Tsf3OverrideUtil *this)
{
  bool v1; // di
  HLOCAL v2; // rax
  void *v3; // rdx
  unsigned int v4; // r8d
  const char *v5; // r9
  void *v6; // rbx
  const char *v7; // r9
  __int64 v8; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  WINBOOL IsMember; // [rsp+30h] [rbp+8h] BYREF
  DWORD cbSid; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  v2 = LocalAlloc(0, 0x44u);
  v6 = v2;
  if ( v2 )
  {
    cbSid = 68;
    if ( CreateWellKnownSid(WinLocalSystemSid, 0, v2, &cbSid) )
    {
      IsMember = 0;
      if ( CheckTokenMembership(0, v6, &IsMember) )
      {
        v1 = IsMember != 0;
        goto LABEL_9;
      }
      v8 = 127;
    }
    else
    {
      v8 = 124;
    }
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\internal\\shell\\inc\\Tsf3OverrideUtil.h",
      v7);
LABEL_9:
    LocalFree(v6);
    return v1;
  }
  wil::details::in1diag3::_Log_NullAlloc(retaddr, v3, v4, v5);
  return v1;
}

```

## disassembly

```asm
0x180076ff8  mov     [rsp+arg_10], rbx
0x180076ffd  push    rdi
0x180076ffe  sub     rsp, 20h
0x180077002  mov     edx, 44h ; 'D'; uBytes
0x180077007  xor     ecx, ecx; uFlags
0x180077009  xor     dil, dil
0x18007700c  call    cs:__imp_LocalAlloc
0x180077012  mov     rcx, [rsp+28h]; this
0x180077017  mov     rbx, rax
0x18007701a  test    rax, rax
0x18007701d  jnz     short loc_180077026
0x18007701f  call    ?_Log_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_NullAlloc(void *,uint,char const *)
0x180077024  jmp     short loc_18007708E
0x180077026  xor     edx, edx; DomainSid
0x180077028  mov     [rsp+28h+cbSid], 44h ; 'D'
0x180077030  lea     r9, [rsp+28h+cbSid]; cbSid
0x180077035  mov     r8, rbx; pSid
0x180077038  lea     ecx, [rdx+16h]; WellKnownSidType
0x18007703b  call    cs:__imp_CreateWellKnownSid
0x180077041  test    eax, eax
0x180077043  jnz     short loc_18007704A
0x180077045  lea     edx, [rax+7Ch]
0x180077048  jmp     short loc_180077069
0x18007704a  lea     r8, [rsp+28h+IsMember]; IsMember
0x18007704f  mov     [rsp+28h+IsMember], 0
0x180077057  mov     rdx, rbx; SidToCheck
0x18007705a  xor     ecx, ecx; TokenHandle
0x18007705c  call    cs:__imp_CheckTokenMembership
0x180077062  test    eax, eax
0x180077064  jnz     short loc_18007707C
0x180077066  lea     edx, [rax+7Fh]; void *
0x180077069  mov     rcx, [rsp+28h]; this
0x18007706e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\shell\\inc\\Tsf3Over"...
0x180077075  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18007707a  jmp     short loc_180077085
0x18007707c  cmp     [rsp+28h+IsMember], 0
0x180077081  setnz   dil
0x180077085  mov     rcx, rbx; hMem
0x180077088  call    cs:__imp_LocalFree
0x18007708e  mov     rbx, [rsp+28h+arg_10]
0x180077093  mov     al, dil
0x180077096  add     rsp, 20h
0x18007709a  pop     rdi
0x18007709b  retn
```
