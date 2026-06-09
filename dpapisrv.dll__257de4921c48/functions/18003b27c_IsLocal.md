# IsLocal

- ea: `0x18003b27c`
- end: `0x18003b394`
- name: `IsLocal`
- size: `280`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025a2c`

## callees

- `0x18001d810`
- `0x18003b27c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b364`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003b364`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003b330`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003b330`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003b30f`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003b30f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003b2ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18003b2ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003b2b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18003b2b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b34f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b34f`

## pseudocode

```c
BOOL IsLocal()
{
  HANDLE CurrentThread; // rax
  BOOL result; // eax
  int v2; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp+27h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+2Fh] BYREF
  PSID SidToCheck; // [rsp+70h] [rbp+37h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+78h] [rbp+3Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 512;
  TokenHandle = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  CurrentThread = GetCurrentThread();
  result = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
  if ( result )
  {
    v2 = AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &SidToCheck);
    if ( v2 )
    {
      IsMember = 0;
      v2 = CheckTokenMembership(TokenHandle, SidToCheck, &IsMember);
      if ( v2 )
        v2 = IsMember != 0 ? v2 : 0;
    }
    CloseHandle(TokenHandle);
    if ( SidToCheck )
      FreeSid(SidToCheck);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18003b27c  mov     [rsp-8+arg_0], rbx
0x18003b281  mov     [rsp-8+arg_8], rdi
0x18003b286  push    rbp
0x18003b287  lea     rbp, [rsp-57h]
0x18003b28c  sub     rsp, 90h
0x18003b293  mov     rax, cs:__security_cookie
0x18003b29a  xor     rax, rsp
0x18003b29d  mov     [rbp+57h+var_10], rax
0x18003b2a1  xor     edi, edi
0x18003b2a3  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 200h
0x18003b2a9  mov     [rbp+57h+TokenHandle], rdi
0x18003b2ad  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x18003b2b0  mov     [rbp+57h+SidToCheck], rdi
0x18003b2b4  call    cs:__imp_GetCurrentThread
0x18003b2bb  nop     dword ptr [rax+rax+00h]
0x18003b2c0  mov     rcx, rax; ThreadHandle
0x18003b2c3  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x18003b2c7  lea     edx, [rdi+8]; DesiredAccess
0x18003b2ca  lea     r8d, [rdi+1]; OpenAsSelf
0x18003b2ce  call    cs:__imp_OpenThreadToken
0x18003b2d5  nop     dword ptr [rax+rax+00h]
0x18003b2da  test    eax, eax
0x18003b2dc  jz      loc_18003B372
0x18003b2e2  lea     rax, [rbp+57h+SidToCheck]
0x18003b2e6  xor     r9d, r9d; nSubAuthority1
0x18003b2e9  mov     [rsp+90h+pSid], rax; pSid
0x18003b2ee  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18003b2f2  mov     [rsp+90h+nSubAuthority7], edi; nSubAuthority7
0x18003b2f6  xor     r8d, r8d; nSubAuthority0
0x18003b2f9  mov     [rsp+90h+nSubAuthority6], edi; nSubAuthority6
0x18003b2fd  mov     dl, 1; nSubAuthorityCount
0x18003b2ff  mov     [rsp+90h+nSubAuthority5], edi; nSubAuthority5
0x18003b303  mov     [rsp+90h+nSubAuthority4], edi; nSubAuthority4
0x18003b307  mov     [rsp+90h+nSubAuthority3], edi; nSubAuthority3
0x18003b30b  mov     [rsp+90h+nSubAuthority2], edi; nSubAuthority2
0x18003b30f  call    cs:__imp_AllocateAndInitializeSid
0x18003b316  nop     dword ptr [rax+rax+00h]
0x18003b31b  mov     ebx, eax
0x18003b31d  test    eax, eax
0x18003b31f  jz      short loc_18003B34B
0x18003b321  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18003b325  lea     r8, [rbp+57h+IsMember]; IsMember
0x18003b329  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18003b32d  mov     [rbp+57h+IsMember], edi
0x18003b330  call    cs:__imp_CheckTokenMembership
0x18003b337  nop     dword ptr [rax+rax+00h]
0x18003b33c  mov     ebx, eax
0x18003b33e  test    eax, eax
0x18003b340  jz      short loc_18003B34B
0x18003b342  mov     eax, [rbp+57h+IsMember]
0x18003b345  neg     eax
0x18003b347  sbb     ecx, ecx
0x18003b349  and     ebx, ecx
0x18003b34b  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18003b34f  call    cs:__imp_CloseHandle
0x18003b356  nop     dword ptr [rax+rax+00h]
0x18003b35b  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18003b35f  test    rcx, rcx
0x18003b362  jz      short loc_18003B370
0x18003b364  call    cs:__imp_FreeSid
0x18003b36b  nop     dword ptr [rax+rax+00h]
0x18003b370  mov     eax, ebx
0x18003b372  mov     rcx, [rbp+57h+var_10]
0x18003b376  xor     rcx, rsp; StackCookie
0x18003b379  call    __security_check_cookie
0x18003b37e  lea     r11, [rsp+90h+var_s0]
0x18003b386  mov     rbx, [r11+10h]
0x18003b38a  mov     rdi, [r11+18h]
0x18003b38e  mov     rsp, r11
0x18003b391  pop     rbp
0x18003b392  retn
```
