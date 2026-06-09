# FRasmanAccessCheck

- ea: `0x18003e660`
- end: `0x18003e9df`
- name: `FRasmanAccessCheck`
- size: `895`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `18`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000eb90`
- `0x18000ee40`
- `0x18000efe0`
- `0x18000f200`
- `0x18000f400`
- `0x18000f500`
- `0x18000f630`
- `0x18000f7c0`
- `0x18000f970`
- `0x18000fba0`
- `0x18000fcc0`
- `0x180013f44`
- `0x18001ac40`
- `0x18001d0f0`
- `0x180028900`
- `0x18002b150`
- `0x18002d230`
- `0x18004939c`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18000bf70`
- `0x18003e660`
- `0x1800e7260`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18003e72b`
- `RPCRT4!RpcImpersonateClient` at `0x18003e72b`
- `RPCRT4!RpcRevertToSelf` at `0x18003e920`
- `RPCRT4!RpcRevertToSelf` at `0x18003e920`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e7b3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e812`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e83c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e866`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e8d7`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e7b3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e812`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e83c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e866`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18003e8d7`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003e7f2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003e916`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003e7f2`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18003e916`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003e79e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003e8c2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003e79e`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18003e8c2`
- `rtutils!RouterLogEventA` at `0x18003e979`
- `rtutils!RouterLogEventA` at `0x18003e979`

## pseudocode

```c
__int64 __fastcall FRasmanAccessCheck(unsigned int a1)
{
  char v1; // bl
  RPC_STATUS v2; // eax
  __int64 v3; // r9
  int v4; // esi
  __int64 v5; // rdi
  unsigned int v6; // eax
  DWORD v7; // ebx
  WINBOOL IsMember; // [rsp+60h] [rbp-29h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-21h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-19h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v12; // [rsp+78h] [rbp-11h] BYREF
  _DWORD v13[4]; // [rsp+80h] [rbp-9h] BYREF
  _DWORD v14[4]; // [rsp+90h] [rbp+7h] BYREF
  _DWORD v15[4]; // [rsp+A0h] [rbp+17h] BYREF

  v1 = a1;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 556, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, a1);
  }
  *(_WORD *)&v12.Value[4] = 1280;
  *(_DWORD *)v12.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v13[0] = 257;
  v13[1] = 83886080;
  v13[2] = 18;
  v14[0] = 257;
  v14[1] = 83886080;
  v14[2] = 20;
  v15[0] = 257;
  v15[1] = 83886080;
  v15[2] = 19;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  v2 = RpcImpersonateClient(0);
  if ( v2 )
  {
    if ( v2 != 1725 )
      goto LABEL_48;
    v4 = 0;
  }
  else
  {
    v4 = 1;
    if ( (v1 & 0x10) == 0 )
    {
      v5 = -5;
      goto LABEL_11;
    }
  }
  v5 = -6;
LABEL_11:
  if ( g_RasMobileCore
    && AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x245u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    if ( !CheckTokenMembership((HANDLE)v5, SidToCheck, &IsMember) )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 557, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
      }
      IsMember = 0;
    }
    FreeSid(SidToCheck);
    if ( IsMember )
      goto LABEL_41;
  }
  if ( (v1 & 2) != 0 )
  {
    if ( CheckTokenMembership((HANDLE)v5, v13, &IsMember) )
    {
      if ( IsMember )
        goto LABEL_41;
    }
    else
    {
      IsMember = 0;
    }
  }
  if ( (v1 & 4) != 0 )
  {
    if ( CheckTokenMembership((HANDLE)v5, v14, &IsMember) )
    {
      if ( IsMember )
        goto LABEL_41;
    }
    else
    {
      IsMember = 0;
    }
  }
  if ( (v1 & 8) == 0 )
  {
LABEL_32:
    if ( (v1 & 1) != 0 && AllocateAndInitializeSid(&v12, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
    {
      if ( !CheckTokenMembership((HANDLE)v5, SidToCheck, &IsMember) )
      {
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 558, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids);
        }
        IsMember = 0;
      }
      FreeSid(SidToCheck);
    }
    goto LABEL_41;
  }
  if ( !CheckTokenMembership((HANDLE)v5, v15, &IsMember) )
  {
    IsMember = 0;
    goto LABEL_32;
  }
  if ( !IsMember )
    goto LABEL_32;
LABEL_41:
  if ( v4 )
  {
    v6 = RpcRevertToSelf();
    v7 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 559, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v6);
      }
      RouterLogEventA(hLogEvents, 2u, 0x4EEAu, 0, 0, v7);
    }
  }
LABEL_48:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    LOBYTE(v3) = IsMember != 0;
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 560, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids, v3);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x18003e660  mov     [rsp-8+arg_8], rbx
0x18003e665  mov     [rsp-8+arg_10], rsi
0x18003e66a  push    rbp
0x18003e66b  push    rdi
0x18003e66c  push    r12
0x18003e66e  push    r13
0x18003e670  push    r14
0x18003e672  lea     rbp, [rsp-37h]
0x18003e677  sub     rsp, 0C0h
0x18003e67e  mov     rax, cs:__security_cookie
0x18003e685  xor     rax, rsp
0x18003e688  mov     [rbp+57h+var_30], rax
0x18003e68c  mov     ebx, ecx
0x18003e68e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e695  lea     r13, WPP_GLOBAL_Control
0x18003e69c  mov     r12d, 2000h
0x18003e6a2  cmp     rcx, r13
0x18003e6a5  jz      short loc_18003E6CB
0x18003e6a7  test    [rcx+1Ch], r12d
0x18003e6ab  jz      short loc_18003E6CB
0x18003e6ad  cmp     byte ptr [rcx+19h], 6
0x18003e6b1  jb      short loc_18003E6CB
0x18003e6b3  mov     rcx, [rcx+10h]
0x18003e6b7  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003e6be  mov     edx, 22Ch
0x18003e6c3  mov     r9d, ebx
0x18003e6c6  call    WPP_SF_d
0x18003e6cb  xor     r14d, r14d
0x18003e6ce  mov     word ptr [rbp+57h+var_68.Value+4], 500h
0x18003e6d4  xor     ecx, ecx; BindingHandle
0x18003e6d6  mov     dword ptr [rbp+57h+var_68.Value], r14d
0x18003e6da  mov     [rbp+57h+SidToCheck], r14
0x18003e6de  mov     [rbp+57h+IsMember], r14d
0x18003e6e2  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x18003e6e6  mov     [rbp+57h+var_60], 101h
0x18003e6ed  mov     [rbp+57h+var_5C], 5000000h
0x18003e6f4  mov     [rbp+57h+var_58], 12h
0x18003e6fb  mov     [rbp+57h+var_50], 101h
0x18003e702  mov     [rbp+57h+var_4C], 5000000h
0x18003e709  mov     [rbp+57h+var_48], 14h
0x18003e710  mov     [rbp+57h+var_40], 101h
0x18003e717  mov     [rbp+57h+var_3C], 5000000h
0x18003e71e  mov     [rbp+57h+var_38], 13h
0x18003e725  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18003e72b  call    cs:__imp_RpcImpersonateClient
0x18003e731  test    eax, eax
0x18003e733  jnz     short loc_18003E743
0x18003e735  lea     esi, [rax+1]
0x18003e738  test    bl, 10h
0x18003e73b  jnz     short loc_18003E751
0x18003e73d  lea     rdi, [r14-5]
0x18003e741  jmp     short loc_18003E758
0x18003e743  cmp     eax, 6BDh
0x18003e748  jnz     loc_18003E97F
0x18003e74e  mov     esi, r14d
0x18003e751  mov     rdi, 0FFFFFFFFFFFFFFFAh
0x18003e758  cmp     cs:g_RasMobileCore, r14d
0x18003e75f  jz      loc_18003E802
0x18003e765  lea     rax, [rbp+57h+SidToCheck]
0x18003e769  mov     r9d, 245h; nSubAuthority1
0x18003e76f  mov     [rsp+0E0h+pSid], rax; pSid
0x18003e774  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18003e778  mov     [rsp+0E0h+nSubAuthority7], r14d; nSubAuthority7
0x18003e77d  mov     r8d, 20h ; ' '; nSubAuthority0
0x18003e783  mov     [rsp+0E0h+nSubAuthority6], r14d; nSubAuthority6
0x18003e788  mov     dl, 2; nSubAuthorityCount
0x18003e78a  mov     [rsp+0E0h+nSubAuthority5], r14d; nSubAuthority5
0x18003e78f  mov     [rsp+0E0h+nSubAuthority4], r14d; nSubAuthority4
0x18003e794  mov     [rsp+0E0h+nSubAuthority3], r14d; nSubAuthority3
0x18003e799  mov     [rsp+0E0h+nSubAuthority2], r14d; nSubAuthority2
0x18003e79e  call    cs:__imp_AllocateAndInitializeSid
0x18003e7a4  test    eax, eax
0x18003e7a6  jz      short loc_18003E802
0x18003e7a8  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18003e7ac  lea     r8, [rbp+57h+IsMember]; IsMember
0x18003e7b0  mov     rcx, rdi; TokenHandle
0x18003e7b3  call    cs:__imp_CheckTokenMembership
0x18003e7b9  test    eax, eax
0x18003e7bb  jnz     short loc_18003E7EE
0x18003e7bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e7c4  cmp     rcx, r13
0x18003e7c7  jz      short loc_18003E7EA
0x18003e7c9  test    [rcx+1Ch], r12d
0x18003e7cd  jz      short loc_18003E7EA
0x18003e7cf  cmp     byte ptr [rcx+19h], 2
0x18003e7d3  jb      short loc_18003E7EA
0x18003e7d5  mov     rcx, [rcx+10h]
0x18003e7d9  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003e7e0  mov     edx, 22Dh
0x18003e7e5  call    WPP_SF_
0x18003e7ea  mov     [rbp+57h+IsMember], r14d
0x18003e7ee  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18003e7f2  call    cs:__imp_FreeSid
0x18003e7f8  cmp     [rbp+57h+IsMember], r14d
0x18003e7fc  jnz     loc_18003E91C
0x18003e802  test    bl, 2
0x18003e805  jz      short loc_18003E82C
0x18003e807  lea     r8, [rbp+57h+IsMember]; IsMember
0x18003e80b  mov     rcx, rdi; TokenHandle
0x18003e80e  lea     rdx, [rbp+57h+var_60]; SidToCheck
0x18003e812  call    cs:__imp_CheckTokenMembership
0x18003e818  test    eax, eax
0x18003e81a  jnz     short loc_18003E822
0x18003e81c  mov     [rbp+57h+IsMember], r14d
0x18003e820  jmp     short loc_18003E82C
0x18003e822  cmp     [rbp+57h+IsMember], r14d
0x18003e826  jnz     loc_18003E91C
0x18003e82c  test    bl, 4
0x18003e82f  jz      short loc_18003E856
0x18003e831  lea     r8, [rbp+57h+IsMember]; IsMember
0x18003e835  mov     rcx, rdi; TokenHandle
0x18003e838  lea     rdx, [rbp+57h+var_50]; SidToCheck
0x18003e83c  call    cs:__imp_CheckTokenMembership
0x18003e842  test    eax, eax
0x18003e844  jnz     short loc_18003E84C
0x18003e846  mov     [rbp+57h+IsMember], r14d
0x18003e84a  jmp     short loc_18003E856
0x18003e84c  cmp     [rbp+57h+IsMember], r14d
0x18003e850  jnz     loc_18003E91C
0x18003e856  test    bl, 8
0x18003e859  jz      short loc_18003E880
0x18003e85b  lea     r8, [rbp+57h+IsMember]; IsMember
0x18003e85f  mov     rcx, rdi; TokenHandle
0x18003e862  lea     rdx, [rbp+57h+var_40]; SidToCheck
0x18003e866  call    cs:__imp_CheckTokenMembership
0x18003e86c  test    eax, eax
0x18003e86e  jnz     short loc_18003E876
0x18003e870  mov     [rbp+57h+IsMember], r14d
0x18003e874  jmp     short loc_18003E880
0x18003e876  cmp     [rbp+57h+IsMember], r14d
0x18003e87a  jnz     loc_18003E91C
0x18003e880  test    bl, 1
0x18003e883  jz      loc_18003E91C
0x18003e889  lea     rax, [rbp+57h+SidToCheck]
0x18003e88d  mov     r9d, 220h; nSubAuthority1
0x18003e893  mov     [rsp+0E0h+pSid], rax; pSid
0x18003e898  lea     rcx, [rbp+57h+var_68]; pIdentifierAuthority
0x18003e89c  mov     [rsp+0E0h+nSubAuthority7], r14d; nSubAuthority7
0x18003e8a1  mov     r8d, 20h ; ' '; nSubAuthority0
0x18003e8a7  mov     [rsp+0E0h+nSubAuthority6], r14d; nSubAuthority6
0x18003e8ac  mov     dl, 2; nSubAuthorityCount
0x18003e8ae  mov     [rsp+0E0h+nSubAuthority5], r14d; nSubAuthority5
0x18003e8b3  mov     [rsp+0E0h+nSubAuthority4], r14d; nSubAuthority4
0x18003e8b8  mov     [rsp+0E0h+nSubAuthority3], r14d; nSubAuthority3
0x18003e8bd  mov     [rsp+0E0h+nSubAuthority2], r14d; nSubAuthority2
0x18003e8c2  call    cs:__imp_AllocateAndInitializeSid
0x18003e8c8  test    eax, eax
0x18003e8ca  jz      short loc_18003E91C
0x18003e8cc  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x18003e8d0  lea     r8, [rbp+57h+IsMember]; IsMember
0x18003e8d4  mov     rcx, rdi; TokenHandle
0x18003e8d7  call    cs:__imp_CheckTokenMembership
0x18003e8dd  test    eax, eax
0x18003e8df  jnz     short loc_18003E912
0x18003e8e1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e8e8  cmp     rcx, r13
0x18003e8eb  jz      short loc_18003E90E
0x18003e8ed  test    [rcx+1Ch], r12d
0x18003e8f1  jz      short loc_18003E90E
0x18003e8f3  cmp     byte ptr [rcx+19h], 2
0x18003e8f7  jb      short loc_18003E90E
0x18003e8f9  mov     rcx, [rcx+10h]
0x18003e8fd  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003e904  mov     edx, 22Eh
0x18003e909  call    WPP_SF_
0x18003e90e  mov     [rbp+57h+IsMember], r14d
0x18003e912  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18003e916  call    cs:__imp_FreeSid
0x18003e91c  test    esi, esi
0x18003e91e  jz      short loc_18003E97F
0x18003e920  call    cs:__imp_RpcRevertToSelf
0x18003e926  mov     ebx, eax
0x18003e928  test    eax, eax
0x18003e92a  jz      short loc_18003E97F
0x18003e92c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e933  cmp     rcx, r13
0x18003e936  jz      short loc_18003E95C
0x18003e938  test    [rcx+1Ch], r12d
0x18003e93c  jz      short loc_18003E95C
0x18003e93e  cmp     byte ptr [rcx+19h], 2
0x18003e942  jb      short loc_18003E95C
0x18003e944  mov     rcx, [rcx+10h]
0x18003e948  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003e94f  mov     edx, 22Fh
0x18003e954  mov     r9d, eax
0x18003e957  call    WPP_SF_d
0x18003e95c  mov     rcx, cs:hLogEvents; hLogHandle
0x18003e963  xor     r9d, r9d; dwSubStringCount
0x18003e966  mov     [rsp+0E0h+nSubAuthority3], ebx; dwErrorCode
0x18003e96a  mov     r8d, 4EEAh; dwMessageId
0x18003e970  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; plpszSubStringArray
0x18003e975  lea     edx, [r9+2]; dwEventType
0x18003e979  call    cs:__imp_RouterLogEventA
0x18003e97f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e986  cmp     rcx, r13
0x18003e989  jz      short loc_18003E9B4
0x18003e98b  test    [rcx+1Ch], r12d
0x18003e98f  jz      short loc_18003E9B4
0x18003e991  cmp     byte ptr [rcx+19h], 6
0x18003e995  jb      short loc_18003E9B4
0x18003e997  cmp     [rbp+57h+IsMember], r14d
0x18003e99b  lea     r8, WPP_8a3e1f8a996f3c8dfe6a76ea96b27c2c_Traceguids
0x18003e9a2  mov     rcx, [rcx+10h]
0x18003e9a6  mov     edx, 230h
0x18003e9ab  setnz   r9b
0x18003e9af  call    WPP_SF_c
0x18003e9b4  mov     eax, [rbp+57h+IsMember]
0x18003e9b7  mov     rcx, [rbp+57h+var_30]
0x18003e9bb  xor     rcx, rsp; StackCookie
0x18003e9be  call    __security_check_cookie
0x18003e9c3  lea     r11, [rsp+0E0h+var_20]
0x18003e9cb  mov     rbx, [r11+38h]
0x18003e9cf  mov     rsi, [r11+40h]
0x18003e9d3  mov     rsp, r11
0x18003e9d6  pop     r14
0x18003e9d8  pop     r13
0x18003e9da  pop     r12
0x18003e9dc  pop     rdi
0x18003e9dd  pop     rbp
0x18003e9de  retn
```
