# CSystemACLApplicator::Init(void)

- ea: `0x18001d050`
- end: `0x18001d2e8`
- name: `?Init@CSystemACLApplicator@@UEAAJXZ`
- size: `664`
- prototype: `__int64 __fastcall(CSystemACLApplicator *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000feb0`

## callees

- `0x180004594`
- `0x18000f5b0`
- `0x18000f864`
- `0x180011118`
- `0x180011748`
- `0x18001d050`
- `0x18001d5e4`
- `0x180022830`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001d1f3`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001d1f3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001d274`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18001d274`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d186`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d186`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x18001d247`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAce` at `0x18001d247`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001d171`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001d171`

## string_xrefs

- `0x18001d1cf`: `onecore\ds\security\gina\profile\profext\dirjunc.cpp`
- `0x18001d206`: `onecore\ds\security\gina\profile\profext\dirjunc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSystemACLApplicator::Init(CSystemACLApplicator *this)
{
  DWORD v2; // r14d
  unsigned int i; // edi
  unsigned __int64 v4; // rsi
  const char *v5; // r9
  __int64 v6; // rdx
  void *v7; // rax
  struct _ACL *v8; // rdi
  unsigned int LastError; // ebx
  __int64 v10; // rdx
  unsigned int j; // ebx
  char v12; // al
  DWORD nSubAuthority2; // [rsp+20h] [rbp-99h]
  int v15; // [rsp+60h] [rbp-59h] BYREF
  __int16 v16; // [rsp+64h] [rbp-55h]
  BYTE nSubAuthorityCount[2]; // [rsp+66h] [rbp-53h]
  DWORD nSubAuthority0[2]; // [rsp+68h] [rbp-51h]
  _BYTE v19[4]; // [rsp+70h] [rbp-49h]
  DWORD AccessMask; // [rsp+74h] [rbp-45h]
  PSID v21; // [rsp+78h] [rbp-41h] BYREF
  int v22; // [rsp+80h] [rbp-39h]
  __int16 v23; // [rsp+84h] [rbp-35h]
  char v24; // [rsp+86h] [rbp-33h]
  __int64 v25; // [rsp+88h] [rbp-31h]
  char v26; // [rsp+90h] [rbp-29h]
  int v27; // [rsp+94h] [rbp-25h]
  __int64 v28; // [rsp+98h] [rbp-21h]
  int v29; // [rsp+A0h] [rbp-19h]
  __int16 v30; // [rsp+A4h] [rbp-15h]
  char v31; // [rsp+A6h] [rbp-13h]
  __int64 v32; // [rsp+A8h] [rbp-11h]
  char v33; // [rsp+B0h] [rbp-9h]
  int v34; // [rsp+B4h] [rbp-5h]
  __int64 v35; // [rsp+B8h] [rbp-1h]
  int v36; // [rsp+C0h] [rbp+7h]
  __int16 v37; // [rsp+C4h] [rbp+Bh]
  char v38; // [rsp+C6h] [rbp+Dh]
  int v39; // [rsp+C8h] [rbp+Fh]
  int v40; // [rsp+CCh] [rbp+13h]
  char v41; // [rsp+D0h] [rbp+17h]
  int v42; // [rsp+D4h] [rbp+1Bh]
  __int64 v43; // [rsp+D8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v15 = 0;
  v16 = 256;
  nSubAuthorityCount[0] = 1;
  *(_QWORD *)nSubAuthority0 = 0;
  v19[0] = 1;
  AccessMask = 1;
  v21 = 0;
  v22 = 0;
  v23 = 256;
  v24 = 1;
  v25 = 0;
  v26 = 0;
  v27 = 1179817;
  v28 = 0;
  v29 = 0;
  v30 = 1280;
  v31 = 1;
  v32 = 18;
  v33 = 0;
  v34 = 2032127;
  v35 = 0;
  v36 = 0;
  v37 = 1280;
  v38 = 2;
  v39 = 32;
  v40 = 544;
  v41 = 0;
  v42 = 2032127;
  v43 = 0;
  v2 = 8;
  for ( i = 0; i < 4; ++i )
  {
    v4 = 32LL * i;
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      (char *)&v21 + v4,
      0);
    if ( !AllocateAndInitializeSid(
            (PSID_IDENTIFIER_AUTHORITY)((char *)&v15 + v4),
            nSubAuthorityCount[v4],
            nSubAuthority0[v4 / 4],
            nSubAuthority0[v4 / 4 + 1],
            0,
            0,
            0,
            0,
            0,
            0,
            (PSID *)((char *)&v21 + v4)) )
    {
      v6 = 113;
LABEL_11:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v6,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
                    v5);
      goto LABEL_23;
    }
    v2 += GetLengthSid(*(&v21 + 4 * i)) + 8;
  }
  v7 = operator new[](v2);
  wil::unique_any_array_ptr<unsigned char,std::default_delete<unsigned char [0]>,wil::empty_deleter,unsigned __int64>::reset(
    (char *)this + 8,
    v7,
    v2);
  v8 = (struct _ACL *)*((_QWORD *)this + 1);
  if ( v8 )
  {
    if ( !InitializeAcl(*((PACL *)this + 1), v2, 2u) )
    {
      v6 = 123;
      goto LABEL_11;
    }
    for ( j = 0; j < 4; ++j )
    {
      v12 = v19[32 * j];
      if ( v12 == 1 )
      {
        if ( !AddAccessDeniedAce(v8, 2u, *(&AccessMask + 8 * j), *(&v21 + 4 * j)) )
        {
          v6 = 129;
          goto LABEL_11;
        }
      }
      else
      {
        if ( v12 )
        {
          LastError = -2147418113;
          v10 = 137;
          goto LABEL_8;
        }
        if ( !AddAccessAllowedAce(v8, 2u, *(&AccessMask + 8 * j), *(&v21 + 4 * j)) )
        {
          v6 = 133;
          goto LABEL_11;
        }
      }
    }
    LastError = 0;
  }
  else
  {
    LastError = -2147024882;
    v10 = 119;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\dirjunc.cpp",
      (const char *)LastError,
      nSubAuthority2);
  }
LABEL_23:
  `eh vector destructor iterator'(&v15, 0x20u, 4u, CSystemACLApplicator::Init_::_2_::ACE_INFO::_ACE_INFO);
  return LastError;
}

```

## disassembly

```asm
0x18001d050  mov     [rsp-8+arg_8], rbx
0x18001d055  mov     [rsp-8+arg_10], rsi
0x18001d05a  push    rbp
0x18001d05b  push    rdi
0x18001d05c  push    r12
0x18001d05e  push    r14
0x18001d060  push    r15
0x18001d062  lea     rbp, [rsp-37h]
0x18001d067  sub     rsp, 0F0h
0x18001d06e  mov     rax, cs:__security_cookie
0x18001d075  xor     rax, rsp
0x18001d078  mov     [rbp+57h+var_30], rax
0x18001d07c  mov     r15, rcx
0x18001d07f  xor     r12d, r12d
0x18001d082  mov     [rbp+57h+var_B0], r12d
0x18001d086  mov     [rbp+57h+var_AC], 100h
0x18001d08c  mov     [rbp+57h+nSubAuthorityCount], 1
0x18001d090  mov     qword ptr [rbp+57h+nSubAuthority0], r12
0x18001d094  mov     [rbp+57h+var_A0], 1
0x18001d098  mov     [rbp+57h+AccessMask], 1
0x18001d09f  mov     [rbp+57h+var_98], r12
0x18001d0a3  mov     [rbp+57h+var_90], r12d
0x18001d0a7  mov     [rbp+57h+var_8C], 100h
0x18001d0ad  mov     [rbp+57h+var_8A], 1
0x18001d0b1  mov     [rbp+57h+var_88], r12
0x18001d0b5  mov     [rbp+57h+var_80], r12b
0x18001d0b9  mov     [rbp+57h+var_7C], 1200A9h
0x18001d0c0  mov     [rbp+57h+var_78], r12
0x18001d0c4  mov     [rbp+57h+var_70], r12d
0x18001d0c8  mov     [rbp+57h+var_6C], 500h
0x18001d0ce  mov     [rbp+57h+var_6A], 1
0x18001d0d2  mov     [rbp+57h+var_68], 12h
0x18001d0da  mov     [rbp+57h+var_60], r12b
0x18001d0de  mov     ecx, 1F01FFh
0x18001d0e3  mov     [rbp+57h+var_5C], ecx
0x18001d0e6  mov     [rbp+57h+var_58], r12
0x18001d0ea  mov     [rbp+57h+var_50], r12d
0x18001d0ee  mov     [rbp+57h+var_4C], 500h
0x18001d0f4  mov     [rbp+57h+var_4A], 2
0x18001d0f8  mov     [rbp+57h+var_48], 20h ; ' '
0x18001d0ff  mov     [rbp+57h+var_44], 220h
0x18001d106  mov     [rbp+57h+var_40], r12b
0x18001d10a  mov     [rbp+57h+var_3C], ecx
0x18001d10d  mov     [rbp+57h+var_38], r12
0x18001d111  lea     r14d, [r12+8]
0x18001d116  mov     edi, r12d
0x18001d119  cmp     edi, 4
0x18001d11c  jnb     loc_18001D1A7
0x18001d122  mov     esi, edi
0x18001d124  shl     rsi, 5
0x18001d128  lea     rbx, [rbp+57h+var_98]
0x18001d12c  add     rbx, rsi
0x18001d12f  xor     edx, edx
0x18001d131  mov     rcx, rbx
0x18001d134  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001d139  lea     rcx, [rbp+57h+var_B0]
0x18001d13d  add     rcx, rsi; pIdentifierAuthority
0x18001d140  mov     [rsp+110h+pSid], rbx; pSid
0x18001d145  mov     [rsp+110h+nSubAuthority7], r12d; nSubAuthority7
0x18001d14a  mov     [rsp+110h+nSubAuthority6], r12d; nSubAuthority6
0x18001d14f  mov     [rsp+110h+nSubAuthority5], r12d; nSubAuthority5
0x18001d154  mov     [rsp+110h+nSubAuthority4], r12d; nSubAuthority4
0x18001d159  mov     [rsp+110h+nSubAuthority3], r12d; nSubAuthority3
0x18001d15e  mov     [rsp+110h+nSubAuthority2], r12d; nSubAuthority2
0x18001d163  mov     r9d, [rbp+rsi+57h+nSubAuthority0+4]; nSubAuthority1
0x18001d168  mov     r8d, [rbp+rsi+57h+nSubAuthority0]; nSubAuthority0
0x18001d16d  mov     dl, [rbp+rsi+57h+nSubAuthorityCount]; nSubAuthorityCount
0x18001d171  call    cs:__imp_AllocateAndInitializeSid
0x18001d178  nop     dword ptr [rax+rax+00h]
0x18001d17d  test    eax, eax
0x18001d17f  jz      short loc_18001D1A0
0x18001d181  mov     rcx, [rbp+rsi+57h+var_98]; pSid
0x18001d186  call    cs:__imp_GetLengthSid
0x18001d18d  nop     dword ptr [rax+rax+00h]
0x18001d192  add     r14d, 8
0x18001d196  add     r14d, eax
0x18001d199  inc     edi
0x18001d19b  jmp     loc_18001D119
0x18001d1a0  mov     edx, 71h ; 'q'
0x18001d1a5  jmp     short loc_18001D206
0x18001d1a7  mov     ecx, r14d; unsigned __int64
0x18001d1aa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001d1af  mov     r8d, r14d
0x18001d1b2  mov     rdx, rax
0x18001d1b5  lea     rcx, [r15+8]
0x18001d1b9  call    ?reset@?$unique_any_array_ptr@EU?$default_delete@$$BY0A@E@std@@Uempty_deleter@wil@@_K@wil@@QEAAXPEAE_K@Z; wil::unique_any_array_ptr<uchar,std::default_delete<uchar [0]>,wil::empty_deleter,unsigned __int64>::reset(uchar *,unsigned __int64)
0x18001d1be  mov     rdi, [r15+8]
0x18001d1c2  test    rdi, rdi
0x18001d1c5  jnz     short loc_18001D1E7
0x18001d1c7  mov     ebx, 8007000Eh
0x18001d1cc  lea     edx, [rdi+77h]; void *
0x18001d1cf  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d1d6  mov     r9d, ebx; char *
0x18001d1d9  mov     rcx, [rbp+5Fh]; this
0x18001d1dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d1e2  jmp     loc_18001D2A4
0x18001d1e7  mov     r8d, 2; dwAclRevision
0x18001d1ed  mov     edx, r14d; nAclLength
0x18001d1f0  mov     rcx, rdi; pAcl
0x18001d1f3  call    cs:__imp_InitializeAcl
0x18001d1fa  nop     dword ptr [rax+rax+00h]
0x18001d1ff  test    eax, eax
0x18001d201  jnz     short loc_18001D21D
0x18001d203  lea     edx, [rax+7Bh]; void *
0x18001d206  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\gina\\profile\\p"...
0x18001d20d  mov     rcx, [rbp+5Fh]; this
0x18001d211  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d216  mov     ebx, eax
0x18001d218  jmp     loc_18001D2A4
0x18001d21d  mov     ebx, r12d
0x18001d220  cmp     ebx, 4
0x18001d223  jnb     short loc_18001D2A1
0x18001d225  mov     r8d, ebx
0x18001d228  shl     r8, 5
0x18001d22c  mov     al, [rbp+r8+57h+var_A0]
0x18001d231  cmp     al, 1
0x18001d233  jnz     short loc_18001D25E
0x18001d235  mov     r9, [rbp+r8+57h+var_98]; pSid
0x18001d23a  mov     r8d, [rbp+r8+57h+AccessMask]; AccessMask
0x18001d23f  mov     edx, 2; dwAceRevision
0x18001d244  mov     rcx, rdi; pAcl
0x18001d247  call    cs:__imp_AddAccessDeniedAce
0x18001d24e  nop     dword ptr [rax+rax+00h]
0x18001d253  test    eax, eax
0x18001d255  jnz     short loc_18001D284
0x18001d257  mov     edx, 81h
0x18001d25c  jmp     short loc_18001D206
0x18001d25e  test    al, al
0x18001d260  jnz     short loc_18001D292
0x18001d262  mov     r9, [rbp+r8+57h+var_98]; pSid
0x18001d267  mov     r8d, [rbp+r8+57h+AccessMask]; AccessMask
0x18001d26c  mov     edx, 2; dwAceRevision
0x18001d271  mov     rcx, rdi; pAcl
0x18001d274  call    cs:__imp_AddAccessAllowedAce
0x18001d27b  nop     dword ptr [rax+rax+00h]
0x18001d280  test    eax, eax
0x18001d282  jz      short loc_18001D288
0x18001d284  inc     ebx
0x18001d286  jmp     short loc_18001D220
0x18001d288  mov     edx, 85h
0x18001d28d  jmp     loc_18001D206
0x18001d292  mov     ebx, 8000FFFFh
0x18001d297  mov     edx, 89h
0x18001d29c  jmp     loc_18001D1CF
0x18001d2a1  mov     ebx, r12d
0x18001d2a4  lea     r9, _CSystemACLApplicator__Init____2___ACE_INFO___ACE_INFO; void (*)(void *)
0x18001d2ab  mov     edx, 20h ; ' '; unsigned __int64
0x18001d2b0  lea     r8d, [rdx-1Ch]; unsigned __int64
0x18001d2b4  lea     rcx, [rbp+57h+var_B0]; void *
0x18001d2b8  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001d2bd  mov     eax, ebx
0x18001d2bf  mov     rcx, [rbp+57h+var_30]
0x18001d2c3  xor     rcx, rsp; StackCookie
0x18001d2c6  call    __security_check_cookie
0x18001d2cb  lea     r11, [rsp+110h+var_20]
0x18001d2d3  mov     rbx, [r11+38h]
0x18001d2d7  mov     rsi, [r11+40h]
0x18001d2db  mov     rsp, r11
0x18001d2de  pop     r15
0x18001d2e0  pop     r14
0x18001d2e2  pop     r12
0x18001d2e4  pop     rdi
0x18001d2e5  pop     rbp
0x18001d2e6  retn
```
