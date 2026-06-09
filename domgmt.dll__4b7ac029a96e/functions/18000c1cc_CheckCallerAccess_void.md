# CheckCallerAccess(void)

- ea: `0x18000c1cc`
- end: `0x18000c2c7`
- name: `?CheckCallerAccess@@YAJXZ`
- size: `251`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c4f0`
- `0x18000c6b0`

## callees

- `0x180005944`
- `0x18000a918`
- `0x18000c1cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c211`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c272`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c29d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c211`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c272`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c29d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c261`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c28c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c261`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18000c28c`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000c226`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18000c226`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000c1e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000c1e7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c241`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c241`

## string_xrefs

- `0x18000c2b4`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 CheckCallerAccess(void)
{
  const char *v0; // r9
  unsigned int v1; // ebx
  HRESULT v3; // eax
  const char *v4; // r9
  unsigned int LastError; // ebx
  unsigned int v6; // ebx
  unsigned int v7; // r8d
  const char *v8; // r9
  __int64 v9; // rdx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  BOOL IsMember; // [rsp+30h] [rbp+8h] BYREF
  PSID Sid; // [rsp+38h] [rbp+10h] BYREF

  Sid = 0;
  if ( ConvertStringSidToSidW(L"S-1-5-80-3055155277-3816794035-3994065555-2874236192-2193176987", &Sid) )
  {
    IsMember = 0;
    v3 = CoImpersonateClient();
    if ( v3 < 0 )
    {
      try
      {
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x14B1,
          (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          (const char *)(unsigned int)v3,
          v10);
      }
      catch ( ... )
      {
        *(_DWORD *)(v9 + 48) = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x18, v7, v8);
        return IsMember;
      }
    }
    if ( CheckTokenMembership(0, Sid, &IsMember) )
    {
      v6 = !IsMember ? 0x80070005 : 0;
      CoRevertToSelf();
      if ( Sid )
        LocalFree(Sid);
      return v6;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x15,
                    (unsigned int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
                    v4);
      CoRevertToSelf();
      if ( Sid )
        LocalFree(Sid);
      return LastError;
    }
  }
  else
  {
    v1 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x11,
           (unsigned int)"onecore\\enduser\\deliveryoptimization\\management\\user.cpp",
           v0);
    if ( Sid )
      LocalFree(Sid);
    return v1;
  }
}

```

## disassembly

```asm
0x18000c1cc  push    rbx; int
0x18000c1ce  sub     rsp, 20h
0x18000c1d2  mov     [rsp+28h+Sid], 0
0x18000c1db  lea     rdx, [rsp+28h+Sid]; Sid
0x18000c1e0  lea     rcx, StringSid; "S-1-5-80-3055155277-3816794035-39940655"...
0x18000c1e7  call    cs:__imp_ConvertStringSidToSidW
0x18000c1ed  test    eax, eax
0x18000c1ef  jnz     short loc_18000C21E
0x18000c1f1  mov     rcx, [rsp+28h]; this
0x18000c1f6  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000c1fd  lea     edx, [rax+11h]; void *
0x18000c200  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c205  mov     ebx, eax
0x18000c207  mov     rcx, [rsp+28h+Sid]; hMem
0x18000c20c  test    rcx, rcx
0x18000c20f  jz      short loc_18000C217
0x18000c211  call    cs:__imp_LocalFree
0x18000c217  mov     eax, ebx
0x18000c219  jmp     loc_18000C2AB
0x18000c21e  mov     [rsp+28h+IsMember], 0
0x18000c226  call    cs:__imp_CoImpersonateClient
0x18000c22c  mov     rcx, [rsp+28h]; this
0x18000c231  test    eax, eax
0x18000c233  js      short loc_18000C2B1
0x18000c235  lea     r8, [rsp+28h+IsMember]; IsMember
0x18000c23a  mov     rdx, [rsp+28h+Sid]; SidToCheck
0x18000c23f  xor     ecx, ecx; TokenHandle
0x18000c241  call    cs:__imp_CheckTokenMembership
0x18000c247  test    eax, eax
0x18000c249  jnz     short loc_18000C27C
0x18000c24b  mov     rcx, [rsp+28h]; this
0x18000c250  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\deliveryoptimization"...
0x18000c257  lea     edx, [rax+15h]; void *
0x18000c25a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c25f  mov     ebx, eax
0x18000c261  call    cs:__imp_CoRevertToSelf
0x18000c267  nop
0x18000c268  mov     rcx, [rsp+28h+Sid]; hMem
0x18000c26d  test    rcx, rcx
0x18000c270  jz      short loc_18000C278
0x18000c272  call    cs:__imp_LocalFree
0x18000c278  mov     eax, ebx
0x18000c27a  jmp     short loc_18000C2AB
0x18000c27c  mov     eax, [rsp+28h+IsMember]
0x18000c280  neg     eax
0x18000c282  sbb     ebx, ebx
0x18000c284  not     ebx
0x18000c286  and     ebx, 80070005h
0x18000c28c  call    cs:__imp_CoRevertToSelf
0x18000c292  nop
0x18000c293  mov     rcx, [rsp+28h+Sid]; hMem
0x18000c298  test    rcx, rcx
0x18000c29b  jz      short loc_18000C2A3
0x18000c29d  call    cs:__imp_LocalFree
0x18000c2a3  mov     eax, ebx
0x18000c2a5  jmp     short loc_18000C2AB
0x18000c2a7  mov     eax, [rsp+28h+IsMember]
0x18000c2ab  add     rsp, 20h
0x18000c2af  pop     rbx
0x18000c2b0  retn
0x18000c2b1  mov     r9d, eax; char *
0x18000c2b4  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000c2bb  mov     edx, 14B1h; void *
0x18000c2c0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
