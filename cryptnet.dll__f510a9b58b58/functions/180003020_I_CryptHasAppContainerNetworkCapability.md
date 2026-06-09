# I_CryptHasAppContainerNetworkCapability

- ea: `0x180003020`
- end: `0x1800030fc`
- name: `I_CryptHasAppContainerNetworkCapability`
- size: `220`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003b40`

## callees

- `0x180003020`
- `0x1800265b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800030c0`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800030c0`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000309b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000309b`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x1800030af`
- `api-ms-win-security-base-l1-2-0!CheckTokenCapability` at `0x1800030af`

## pseudocode

```c
__int64 I_CryptHasAppContainerNetworkCapability()
{
  unsigned int i; // ebx
  DWORD v1; // r9d
  int v3; // [rsp+60h] [rbp-20h] BYREF
  PSID pSid; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  for ( i = 0; i < 3; ++i )
  {
    v1 = *((_DWORD *)qword_18002BA38 + i);
    v3 = 0;
    *(_DWORD *)pIdentifierAuthority.Value = 0;
    *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
    pSid = 0;
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 3u, v1, 0, 0, 0, 0, 0, 0, &pSid) )
    {
      if ( !(unsigned int)CheckTokenCapability(0, pSid, &v3) )
        v3 = 0;
      FreeSid(pSid);
      if ( v3 )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003020  mov     [rsp-8+arg_0], rbx
0x180003025  mov     [rsp-8+arg_8], rdi
0x18000302a  push    rbp
0x18000302b  mov     rbp, rsp
0x18000302e  sub     rsp, 80h
0x180003035  mov     rax, cs:__security_cookie
0x18000303c  xor     rax, rsp
0x18000303f  mov     [rbp+var_8], rax
0x180003043  xor     edi, edi
0x180003045  mov     ebx, edi
0x180003047  cmp     ebx, 3
0x18000304a  jnb     loc_1800030F8
0x180003050  lea     rax, [rbp+var_18]
0x180003054  mov     r9d, ebx
0x180003057  mov     [rsp+80h+pSid], rax; pSid
0x18000305c  lea     rcx, qword_18002BA38
0x180003063  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x180003067  mov     r8d, 3; nSubAuthority0
0x18000306d  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x180003071  mov     dl, 2; nSubAuthorityCount
0x180003073  mov     r9d, [rcx+r9*4]; nSubAuthority1
0x180003077  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18000307b  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x18000307f  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x180003083  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x180003087  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x18000308b  mov     [rbp+var_20], edi
0x18000308e  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x180003091  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 0F00h
0x180003097  mov     [rbp+var_18], rdi
0x18000309b  call    cs:__imp_AllocateAndInitializeSid
0x1800030a1  test    eax, eax
0x1800030a3  jz      short loc_1800030F1
0x1800030a5  mov     rdx, [rbp+var_18]
0x1800030a9  lea     r8, [rbp+var_20]
0x1800030ad  xor     ecx, ecx
0x1800030af  call    cs:__imp_CheckTokenCapability
0x1800030b5  test    eax, eax
0x1800030b7  jnz     short loc_1800030BC
0x1800030b9  mov     [rbp+var_20], edi
0x1800030bc  mov     rcx, [rbp+var_18]; pSid
0x1800030c0  call    cs:__imp_FreeSid
0x1800030c6  cmp     [rbp+var_20], edi
0x1800030c9  jz      short loc_1800030F1
0x1800030cb  mov     eax, 1
0x1800030d0  mov     rcx, [rbp+var_8]
0x1800030d4  xor     rcx, rsp; StackCookie
0x1800030d7  call    __security_check_cookie
0x1800030dc  lea     r11, [rsp+80h+var_s0]
0x1800030e4  mov     rbx, [r11+10h]
0x1800030e8  mov     rdi, [r11+18h]
0x1800030ec  mov     rsp, r11
0x1800030ef  pop     rbp
0x1800030f0  retn
0x1800030f1  inc     ebx
0x1800030f3  jmp     loc_180003047
0x1800030f8  xor     eax, eax
0x1800030fa  jmp     short loc_1800030D0
```
