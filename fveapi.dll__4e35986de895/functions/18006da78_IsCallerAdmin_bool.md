# IsCallerAdmin(bool *)

- ea: `0x18006da78`
- end: `0x18006db55`
- name: `?IsCallerAdmin@@YAJPEA_N@Z`
- size: `221`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006dbec`

## callees

- `0x180005410`
- `0x18006da78`
- `0x18011f010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18006db28`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801226dc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18006db28`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1801226dc`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18006db03`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18006db03`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006dade`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18006dade`

## pseudocode

```c
__int64 __fastcall IsCallerAdmin(bool *a1)
{
  unsigned int LastHresultError; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-28h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v6; // [rsp+70h] [rbp-18h] BYREF

  *(_DWORD *)v6.Value = 0;
  *(_WORD *)&v6.Value[4] = 1280;
  SidToCheck = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(&v6, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck)
    && CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    *a1 = IsMember != 0;
    LastHresultError = 0;
  }
  else
  {
    LastHresultError = GetLastHresultError();
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return LastHresultError;
}

```

## disassembly

```asm
0x18006da78  mov     r11, rsp
0x18006da7b  mov     [r11+10h], rbx
0x18006da7f  push    rdi
0x18006da80  sub     rsp, 80h
0x18006da87  mov     rax, cs:__security_cookie
0x18006da8e  xor     rax, rsp
0x18006da91  mov     [rsp+88h+var_10], rax
0x18006da96  mov     rbx, rcx
0x18006da99  xor     edi, edi
0x18006da9b  mov     [rsp+88h+var_18], edi
0x18006da9f  mov     [rsp+88h+var_14], 500h
0x18006daa6  mov     [r11-20h], rdi
0x18006daaa  mov     [rsp+88h+IsMember], edi
0x18006daae  lea     rax, [r11-20h]
0x18006dab2  mov     [r11-38h], rax
0x18006dab6  mov     [rsp+88h+nSubAuthority7], edi; nSubAuthority7
0x18006daba  mov     [rsp+88h+nSubAuthority6], edi; nSubAuthority6
0x18006dabe  mov     [rsp+88h+nSubAuthority5], edi; nSubAuthority5
0x18006dac2  mov     [rsp+88h+nSubAuthority4], edi; nSubAuthority4
0x18006dac6  mov     [rsp+88h+nSubAuthority3], edi; nSubAuthority3
0x18006daca  mov     [rsp+88h+nSubAuthority2], edi; nSubAuthority2
0x18006dace  mov     r9d, 220h; nSubAuthority1
0x18006dad4  lea     r8d, [rdi+20h]; nSubAuthority0
0x18006dad8  mov     dl, 2; nSubAuthorityCount
0x18006dada  lea     rcx, [r11-18h]; pIdentifierAuthority
0x18006dade  call    cs:__imp_AllocateAndInitializeSid
0x18006dae5  nop     dword ptr [rax+rax+00h]
0x18006daea  test    eax, eax
0x18006daec  jnz     short loc_18006DAF7
0x18006daee  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x18006daf3  mov     ebx, eax
0x18006daf5  jmp     short loc_18006DB1E
0x18006daf7  lea     r8, [rsp+88h+IsMember]; IsMember
0x18006dafc  mov     rdx, [rsp+88h+SidToCheck]; SidToCheck
0x18006db01  xor     ecx, ecx; TokenHandle
0x18006db03  call    cs:__imp_CheckTokenMembership
0x18006db0a  nop     dword ptr [rax+rax+00h]
0x18006db0f  test    eax, eax
0x18006db11  jz      short loc_18006DAEE
0x18006db13  cmp     [rsp+88h+IsMember], edi
0x18006db17  setnz   al
0x18006db1a  mov     [rbx], al
0x18006db1c  mov     ebx, edi
0x18006db1e  mov     rcx, [rsp+88h+SidToCheck]; pSid
0x18006db23  test    rcx, rcx
0x18006db26  jz      short loc_18006DB34
0x18006db28  call    cs:__imp_FreeSid
0x18006db2f  nop     dword ptr [rax+rax+00h]
0x18006db34  mov     eax, ebx
0x18006db36  mov     rcx, [rsp+88h+var_10]
0x18006db3b  xor     rcx, rsp; StackCookie
0x18006db3e  call    __security_check_cookie
0x18006db43  mov     rbx, [rsp+88h+arg_8]
0x18006db4b  add     rsp, 80h
0x18006db52  pop     rdi
0x18006db53  retn
0x1801226ca  push    rbp
0x1801226cc  sub     rsp, 60h
0x1801226d0  mov     rbp, rdx
0x1801226d3  mov     rcx, [rbp+68h]; pSid
0x1801226d7  test    rcx, rcx
0x1801226da  jz      short loc_1801226E9
0x1801226dc  call    cs:__imp_FreeSid
0x1801226e3  nop     dword ptr [rax+rax+00h]
0x1801226e8  nop
0x1801226e9  add     rsp, 60h
0x1801226ed  pop     rbp
0x1801226ee  retn
```
