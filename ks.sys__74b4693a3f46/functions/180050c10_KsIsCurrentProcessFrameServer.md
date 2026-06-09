# KsIsCurrentProcessFrameServer

- ea: `0x180050c10`
- end: `0x180050ee4`
- name: `KsIsCurrentProcessFrameServer`
- size: `724`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180044ee0`
- `0x180050254`

## callees

- `0x180019b80`
- `0x180019fc0`
- `0x180050c10`

## import_xrefs

- `ntoskrnl!ExGetPreviousMode` at `0x180050c41`
- `ntoskrnl!ExGetPreviousMode` at `0x180050c41`
- `ntoskrnl!RtlInitializeSid` at `0x180050d09`
- `ntoskrnl!RtlInitializeSid` at `0x180050d27`
- `ntoskrnl!RtlInitializeSid` at `0x180050d09`
- `ntoskrnl!RtlInitializeSid` at `0x180050d27`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050d40`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050d57`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050d71`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050d8b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050da9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050dc2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050dd9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050df0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050e09`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050e22`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050e3a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050e53`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050d40`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050d57`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050d71`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050d8b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050da9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050dc2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050dd9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050df0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050e09`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050e22`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050e3a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x180050e53`
- `ntoskrnl!RtlCheckTokenMembership` at `0x180050e6e`
- `ntoskrnl!RtlCheckTokenMembership` at `0x180050e87`
- `ntoskrnl!RtlCheckTokenMembership` at `0x180050e6e`
- `ntoskrnl!RtlCheckTokenMembership` at `0x180050e87`
- `ntoskrnl!RtlLengthRequiredSid` at `0x180050c5d`
- `ntoskrnl!RtlLengthRequiredSid` at `0x180050ca7`
- `ntoskrnl!RtlLengthRequiredSid` at `0x180050c5d`
- `ntoskrnl!RtlLengthRequiredSid` at `0x180050ca7`
- `ntoskrnl!ExFreePoolWithTag` at `0x180050e98`
- `ntoskrnl!ExFreePoolWithTag` at `0x180050eae`
- `ntoskrnl!ExFreePoolWithTag` at `0x180050e98`
- `ntoskrnl!ExFreePoolWithTag` at `0x180050eae`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180050c78`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180050cc3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180050c78`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180050cc3`

## pseudocode

```c
char KsIsCurrentProcessFrameServer()
{
  char v0; // si
  ULONG v1; // ebx
  PVOID PoolWithTag; // rax
  void *v3; // rdi
  ULONG v4; // r14d
  PVOID v5; // rax
  void *v6; // rbx
  char v8; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v9[3]; // [rsp+21h] [rbp-1Fh] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+24h] [rbp-1Ch] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v8 = 0;
  v9[0] = 0;
  v0 = 1;
  if ( ExGetPreviousMode() )
  {
    v1 = RtlLengthRequiredSid(6u);
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, v1, 0x7363534Bu);
    v3 = PoolWithTag;
    if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      memset(PoolWithTag, 0, v1);
    v4 = RtlLengthRequiredSid(6u);
    v5 = ExAllocatePoolWithTag((POOL_TYPE)1025, v4, 0x7363534Bu);
    v6 = v5;
    if ( !ExPoolZeroingNativelySupported && v5 )
      memset(v5, 0, v4);
    if ( v3 )
    {
      if ( v6 )
      {
        if ( RtlInitializeSid(v3, &IdentifierAuthority, 6u) >= 0 && RtlInitializeSid(v6, &IdentifierAuthority, 6u) >= 0 )
        {
          *RtlSubAuthoritySid(v3, 0) = 80;
          *RtlSubAuthoritySid(v3, 1u) = -379073292;
          *RtlSubAuthoritySid(v3, 2u) = 2104103821;
          *RtlSubAuthoritySid(v3, 3u) = -1247697674;
          *RtlSubAuthoritySid(v3, 4u) = 1811662266;
          *RtlSubAuthoritySid(v3, 5u) = 774708259;
          *RtlSubAuthoritySid(v6, 0) = 80;
          *RtlSubAuthoritySid(v6, 1u) = -1558133237;
          *RtlSubAuthoritySid(v6, 2u) = 149274525;
          *RtlSubAuthoritySid(v6, 3u) = -1546006515;
          *RtlSubAuthoritySid(v6, 4u) = -428641286;
          *RtlSubAuthoritySid(v6, 5u) = -954125960;
          if ( (int)RtlCheckTokenMembership(0, v3, &v8) >= 0 )
            RtlCheckTokenMembership(0, v6, v9);
        }
      }
      ExFreePoolWithTag(v3, 0);
    }
    if ( v6 )
      ExFreePoolWithTag(v6, 0);
  }
  if ( !v8 && !v9[0] )
    return 0;
  return v0;
}

```

## disassembly

```asm
0x180050c10  push    rbp
0x180050c12  push    rbx
0x180050c13  push    rsi
0x180050c14  push    rdi
0x180050c15  push    r14
0x180050c17  mov     rbp, rsp
0x180050c1a  sub     rsp, 40h
0x180050c1e  mov     rax, cs:__security_cookie
0x180050c25  xor     rax, rsp
0x180050c28  mov     [rbp+var_10], rax
0x180050c2c  mov     dword ptr [rbp+IdentifierAuthority.Value], 0
0x180050c33  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x180050c39  mov     [rbp+var_20], 0
0x180050c3d  mov     [rbp+var_1F], 0
0x180050c41  call    cs:__imp_ExGetPreviousMode
0x180050c48  nop     dword ptr [rax+rax+00h]
0x180050c4d  mov     esi, 1
0x180050c52  test    al, al
0x180050c54  jz      loc_180050EBA
0x180050c5a  lea     ecx, [rsi+5]; SubAuthorityCount
0x180050c5d  call    cs:__imp_RtlLengthRequiredSid
0x180050c64  nop     dword ptr [rax+rax+00h]
0x180050c69  mov     edx, eax; NumberOfBytes
0x180050c6b  mov     r8d, 7363534Bh; Tag
0x180050c71  mov     ecx, 401h; PoolType
0x180050c76  mov     ebx, eax
0x180050c78  call    cs:__imp_ExAllocatePoolWithTag
0x180050c7f  nop     dword ptr [rax+rax+00h]
0x180050c84  cmp     cs:ExPoolZeroingNativelySupported, 0
0x180050c8b  mov     rdi, rax
0x180050c8e  jnz     short loc_180050CA2
0x180050c90  test    rax, rax
0x180050c93  jz      short loc_180050CA2
0x180050c95  mov     r8d, ebx; Size
0x180050c98  xor     edx, edx; Val
0x180050c9a  mov     rcx, rax; void *
0x180050c9d  call    memset
0x180050ca2  mov     ecx, 6; SubAuthorityCount
0x180050ca7  call    cs:__imp_RtlLengthRequiredSid
0x180050cae  nop     dword ptr [rax+rax+00h]
0x180050cb3  mov     edx, eax; NumberOfBytes
0x180050cb5  mov     r8d, 7363534Bh; Tag
0x180050cbb  mov     ecx, 401h; PoolType
0x180050cc0  mov     r14d, eax
0x180050cc3  call    cs:__imp_ExAllocatePoolWithTag
0x180050cca  nop     dword ptr [rax+rax+00h]
0x180050ccf  cmp     cs:ExPoolZeroingNativelySupported, 0
0x180050cd6  mov     rbx, rax
0x180050cd9  jnz     short loc_180050CED
0x180050cdb  test    rax, rax
0x180050cde  jz      short loc_180050CED
0x180050ce0  mov     r8d, r14d; Size
0x180050ce3  xor     edx, edx; Val
0x180050ce5  mov     rcx, rax; void *
0x180050ce8  call    memset
0x180050ced  test    rdi, rdi
0x180050cf0  jz      loc_180050EA4
0x180050cf6  test    rbx, rbx
0x180050cf9  jz      loc_180050E93
0x180050cff  mov     r8b, 6; SubAuthorityCount
0x180050d02  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x180050d06  mov     rcx, rdi; Sid
0x180050d09  call    cs:__imp_RtlInitializeSid
0x180050d10  nop     dword ptr [rax+rax+00h]
0x180050d15  test    eax, eax
0x180050d17  js      loc_180050E93
0x180050d1d  mov     r8b, 6; SubAuthorityCount
0x180050d20  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x180050d24  mov     rcx, rbx; Sid
0x180050d27  call    cs:__imp_RtlInitializeSid
0x180050d2e  nop     dword ptr [rax+rax+00h]
0x180050d33  test    eax, eax
0x180050d35  js      loc_180050E93
0x180050d3b  xor     edx, edx; SubAuthority
0x180050d3d  mov     rcx, rdi; Sid
0x180050d40  call    cs:__imp_RtlSubAuthoritySid
0x180050d47  nop     dword ptr [rax+rax+00h]
0x180050d4c  mov     edx, esi; SubAuthority
0x180050d4e  mov     rcx, rdi; Sid
0x180050d51  mov     dword ptr [rax], 50h ; 'P'
0x180050d57  call    cs:__imp_RtlSubAuthoritySid
0x180050d5e  nop     dword ptr [rax+rax+00h]
0x180050d63  mov     edx, 2; SubAuthority
0x180050d68  mov     rcx, rdi; Sid
0x180050d6b  mov     dword ptr [rax], 0E967CCF4h
0x180050d71  call    cs:__imp_RtlSubAuthoritySid
0x180050d78  nop     dword ptr [rax+rax+00h]
0x180050d7d  mov     edx, 3; SubAuthority
0x180050d82  mov     rcx, rdi; Sid
0x180050d85  mov     dword ptr [rax], 7D6A138Dh
0x180050d8b  call    cs:__imp_RtlSubAuthoritySid
0x180050d92  nop     dword ptr [rax+rax+00h]
0x180050d97  mov     r14d, 4
0x180050d9d  mov     rcx, rdi; Sid
0x180050da0  mov     edx, r14d; SubAuthority
0x180050da3  mov     dword ptr [rax], 0B5A1A4F6h
0x180050da9  call    cs:__imp_RtlSubAuthoritySid
0x180050db0  nop     dword ptr [rax+rax+00h]
0x180050db5  lea     edx, [r14+1]; SubAuthority
0x180050db9  mov     rcx, rdi; Sid
0x180050dbc  mov     dword ptr [rax], 6BFBC5BAh
0x180050dc2  call    cs:__imp_RtlSubAuthoritySid
0x180050dc9  nop     dword ptr [rax+rax+00h]
0x180050dce  xor     edx, edx; SubAuthority
0x180050dd0  mov     rcx, rbx; Sid
0x180050dd3  mov     dword ptr [rax], 2E2D1C23h
0x180050dd9  call    cs:__imp_RtlSubAuthoritySid
0x180050de0  nop     dword ptr [rax+rax+00h]
0x180050de5  mov     edx, esi; SubAuthority
0x180050de7  mov     rcx, rbx; Sid
0x180050dea  mov     dword ptr [rax], 50h ; 'P'
0x180050df0  call    cs:__imp_RtlSubAuthoritySid
0x180050df7  nop     dword ptr [rax+rax+00h]
0x180050dfc  lea     edx, [r14-2]; SubAuthority
0x180050e00  mov     rcx, rbx; Sid
0x180050e03  mov     dword ptr [rax], 0A320C60Bh
0x180050e09  call    cs:__imp_RtlSubAuthoritySid
0x180050e10  nop     dword ptr [rax+rax+00h]
0x180050e15  lea     edx, [r14-1]; SubAuthority
0x180050e19  mov     rcx, rbx; Sid
0x180050e1c  mov     dword ptr [rax], 8E5BF9Dh
0x180050e22  call    cs:__imp_RtlSubAuthoritySid
0x180050e29  nop     dword ptr [rax+rax+00h]
0x180050e2e  mov     edx, r14d; SubAuthority
0x180050e31  mov     rcx, rbx; Sid
0x180050e34  mov     dword ptr [rax], 0A3D9D00Dh
0x180050e3a  call    cs:__imp_RtlSubAuthoritySid
0x180050e41  nop     dword ptr [rax+rax+00h]
0x180050e46  lea     edx, [r14+1]; SubAuthority
0x180050e4a  mov     rcx, rbx; Sid
0x180050e4d  mov     dword ptr [rax], 0E67373FAh
0x180050e53  call    cs:__imp_RtlSubAuthoritySid
0x180050e5a  nop     dword ptr [rax+rax+00h]
0x180050e5f  lea     r8, [rbp+var_20]
0x180050e63  mov     rdx, rdi
0x180050e66  xor     ecx, ecx
0x180050e68  mov     dword ptr [rax], 0C7213178h
0x180050e6e  call    cs:__imp_RtlCheckTokenMembership
0x180050e75  nop     dword ptr [rax+rax+00h]
0x180050e7a  test    eax, eax
0x180050e7c  js      short loc_180050E93
0x180050e7e  lea     r8, [rbp+var_1F]
0x180050e82  mov     rdx, rbx
0x180050e85  xor     ecx, ecx
0x180050e87  call    cs:__imp_RtlCheckTokenMembership
0x180050e8e  nop     dword ptr [rax+rax+00h]
0x180050e93  xor     edx, edx; Tag
0x180050e95  mov     rcx, rdi; P
0x180050e98  call    cs:__imp_ExFreePoolWithTag
0x180050e9f  nop     dword ptr [rax+rax+00h]
0x180050ea4  test    rbx, rbx
0x180050ea7  jz      short loc_180050EBA
0x180050ea9  xor     edx, edx; Tag
0x180050eab  mov     rcx, rbx; P
0x180050eae  call    cs:__imp_ExFreePoolWithTag
0x180050eb5  nop     dword ptr [rax+rax+00h]
0x180050eba  cmp     [rbp+var_20], 0
0x180050ebe  jnz     short loc_180050EC9
0x180050ec0  cmp     [rbp+var_1F], 0
0x180050ec4  jnz     short loc_180050EC9
0x180050ec6  xor     sil, sil
0x180050ec9  mov     al, sil
0x180050ecc  mov     rcx, [rbp+var_10]
0x180050ed0  xor     rcx, rsp; StackCookie
0x180050ed3  call    __security_check_cookie
0x180050ed8  add     rsp, 40h
0x180050edc  pop     r14
0x180050ede  pop     rdi
0x180050edf  pop     rsi
0x180050ee0  pop     rbx
0x180050ee1  pop     rbp
0x180050ee2  retn
```
