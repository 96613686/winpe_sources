# FRasmanAccessCheck

- ea: `0x180040580`
- end: `0x180040948`
- name: `FRasmanAccessCheck`
- size: `968`
- prototype: ``
- caller_count: `18`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f210`
- `0x18000f4d0`
- `0x18000f670`
- `0x18000f890`
- `0x18000faa0`
- `0x18000fba0`
- `0x18000fcd0`
- `0x18000fe70`
- `0x180010020`
- `0x180010250`
- `0x180010370`
- `0x180014734`
- `0x18001b6d0`
- `0x18001dc10`
- `0x180029a10`
- `0x18002c3f0`
- `0x18002e560`
- `0x18004b748`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000c37c`
- `0x180040580`
- `0x1800e8ef0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18004064b`
- `RPCRT4!RpcImpersonateClient` at `0x18004064b`
- `RPCRT4!RpcRevertToSelf` at `0x18004087c`
- `RPCRT4!RpcRevertToSelf` at `0x18004087c`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800406df`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004074a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004077a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800407aa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180040827`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800406df`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004074a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18004077a`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800407aa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180040827`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180040724`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004086c`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180040724`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18004086c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800406c4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004080c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800406c4`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18004080c`
- `rtutils!RouterLogEventA` at `0x1800408db`
- `rtutils!RouterLogEventA` at `0x1800408db`

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
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 554, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, a1);
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
        WPP_SF_(WPP_GLOBAL_Control[1].Flink, 555, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
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
          WPP_SF_(WPP_GLOBAL_Control[1].Flink, 556, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids);
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
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 557, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v6);
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
    WPP_SF_c(WPP_GLOBAL_Control[1].Flink, 558, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids, v3);
  }
  return (unsigned int)IsMember;
}

```

## disassembly

```asm
0x180040580  mov     [rsp-8+arg_8], rbx
0x180040585  mov     [rsp-8+arg_10], rsi
0x18004058a  push    rbp
0x18004058b  push    rdi
0x18004058c  push    r12
0x18004058e  push    r13
0x180040590  push    r14
0x180040592  lea     rbp, [rsp-37h]
0x180040597  sub     rsp, 0C0h
0x18004059e  mov     rax, cs:__security_cookie
0x1800405a5  xor     rax, rsp
0x1800405a8  mov     [rbp+57h+var_30], rax
0x1800405ac  mov     ebx, ecx
0x1800405ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800405b5  lea     r13, WPP_GLOBAL_Control
0x1800405bc  mov     r12d, 2000h
0x1800405c2  cmp     rcx, r13
0x1800405c5  jz      short loc_1800405EB
0x1800405c7  test    [rcx+1Ch], r12d
0x1800405cb  jz      short loc_1800405EB
0x1800405cd  cmp     byte ptr [rcx+19h], 6
0x1800405d1  jb      short loc_1800405EB
0x1800405d3  mov     rcx, [rcx+10h]
0x1800405d7  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x1800405de  mov     edx, 22Ah
0x1800405e3  mov     r9d, ebx
0x1800405e6  call    WPP_SF_d
0x1800405eb  xor     r14d, r14d
0x1800405ee  mov     word ptr [rbp+57h+var_68.Value+4], 500h
0x1800405f4  xor     ecx, ecx; BindingHandle
0x1800405f6  mov     dword ptr [rbp+57h+var_68.Value], r14d
0x1800405fa  mov     [rbp+57h+SidToCheck], r14
0x1800405fe  mov     [rbp+57h+IsMember], r14d
0x180040602  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r14d
0x180040606  mov     [rbp+57h+var_60], 101h
0x18004060d  mov     [rbp+57h+var_5C], 5000000h
0x180040614  mov     [rbp+57h+var_58], 12h
0x18004061b  mov     [rbp+57h+var_50], 101h
0x180040622  mov     [rbp+57h+var_4C], 5000000h
0x180040629  mov     [rbp+57h+var_48], 14h
0x180040630  mov     [rbp+57h+var_40], 101h
0x180040637  mov     [rbp+57h+var_3C], 5000000h
0x18004063e  mov     [rbp+57h+var_38], 13h
0x180040645  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x18004064b  call    cs:__imp_RpcImpersonateClient
0x180040652  nop     dword ptr [rax+rax+00h]
0x180040657  test    eax, eax
0x180040659  jnz     short loc_180040669
0x18004065b  lea     esi, [rax+1]
0x18004065e  test    bl, 10h
0x180040661  jnz     short loc_180040677
0x180040663  lea     rdi, [r14-5]
0x180040667  jmp     short loc_18004067E
0x180040669  cmp     eax, 6BDh
0x18004066e  jnz     loc_1800408E7
0x180040674  mov     esi, r14d
0x180040677  mov     rdi, 0FFFFFFFFFFFFFFFAh
0x18004067e  cmp     cs:g_RasMobileCore, r14d
0x180040685  jz      loc_18004073A
0x18004068b  lea     rax, [rbp+57h+SidToCheck]
0x18004068f  mov     r9d, 245h; nSubAuthority1
0x180040695  mov     [rsp+0E0h+pSid], rax; pSid
0x18004069a  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18004069e  mov     [rsp+0E0h+nSubAuthority7], r14d; nSubAuthority7
0x1800406a3  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800406a9  mov     [rsp+0E0h+nSubAuthority6], r14d; nSubAuthority6
0x1800406ae  mov     dl, 2; nSubAuthorityCount
0x1800406b0  mov     [rsp+0E0h+nSubAuthority5], r14d; nSubAuthority5
0x1800406b5  mov     [rsp+0E0h+nSubAuthority4], r14d; nSubAuthority4
0x1800406ba  mov     [rsp+0E0h+nSubAuthority3], r14d; nSubAuthority3
0x1800406bf  mov     [rsp+0E0h+nSubAuthority2], r14d; nSubAuthority2
0x1800406c4  call    cs:__imp_AllocateAndInitializeSid
0x1800406cb  nop     dword ptr [rax+rax+00h]
0x1800406d0  test    eax, eax
0x1800406d2  jz      short loc_18004073A
0x1800406d4  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x1800406d8  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800406dc  mov     rcx, rdi; TokenHandle
0x1800406df  call    cs:__imp_CheckTokenMembership
0x1800406e6  nop     dword ptr [rax+rax+00h]
0x1800406eb  test    eax, eax
0x1800406ed  jnz     short loc_180040720
0x1800406ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800406f6  cmp     rcx, r13
0x1800406f9  jz      short loc_18004071C
0x1800406fb  test    [rcx+1Ch], r12d
0x1800406ff  jz      short loc_18004071C
0x180040701  cmp     byte ptr [rcx+19h], 2
0x180040705  jb      short loc_18004071C
0x180040707  mov     rcx, [rcx+10h]
0x18004070b  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x180040712  mov     edx, 22Bh
0x180040717  call    WPP_SF_
0x18004071c  mov     [rbp+57h+IsMember], r14d
0x180040720  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x180040724  call    cs:__imp_FreeSid
0x18004072b  nop     dword ptr [rax+rax+00h]
0x180040730  cmp     [rbp+57h+IsMember], r14d
0x180040734  jnz     loc_180040878
0x18004073a  test    bl, 2
0x18004073d  jz      short loc_18004076A
0x18004073f  lea     r8, [rbp+57h+IsMember]; IsMember
0x180040743  mov     rcx, rdi; TokenHandle
0x180040746  lea     rdx, [rbp+57h+var_60]; SidToCheck
0x18004074a  call    cs:__imp_CheckTokenMembership
0x180040751  nop     dword ptr [rax+rax+00h]
0x180040756  test    eax, eax
0x180040758  jnz     short loc_180040760
0x18004075a  mov     [rbp+57h+IsMember], r14d
0x18004075e  jmp     short loc_18004076A
0x180040760  cmp     [rbp+57h+IsMember], r14d
0x180040764  jnz     loc_180040878
0x18004076a  test    bl, 4
0x18004076d  jz      short loc_18004079A
0x18004076f  lea     r8, [rbp+57h+IsMember]; IsMember
0x180040773  mov     rcx, rdi; TokenHandle
0x180040776  lea     rdx, [rbp+57h+var_50]; SidToCheck
0x18004077a  call    cs:__imp_CheckTokenMembership
0x180040781  nop     dword ptr [rax+rax+00h]
0x180040786  test    eax, eax
0x180040788  jnz     short loc_180040790
0x18004078a  mov     [rbp+57h+IsMember], r14d
0x18004078e  jmp     short loc_18004079A
0x180040790  cmp     [rbp+57h+IsMember], r14d
0x180040794  jnz     loc_180040878
0x18004079a  test    bl, 8
0x18004079d  jz      short loc_1800407CA
0x18004079f  lea     r8, [rbp+57h+IsMember]; IsMember
0x1800407a3  mov     rcx, rdi; TokenHandle
0x1800407a6  lea     rdx, [rbp+57h+var_40]; SidToCheck
0x1800407aa  call    cs:__imp_CheckTokenMembership
0x1800407b1  nop     dword ptr [rax+rax+00h]
0x1800407b6  test    eax, eax
0x1800407b8  jnz     short loc_1800407C0
0x1800407ba  mov     [rbp+57h+IsMember], r14d
0x1800407be  jmp     short loc_1800407CA
0x1800407c0  cmp     [rbp+57h+IsMember], r14d
0x1800407c4  jnz     loc_180040878
0x1800407ca  test    bl, 1
0x1800407cd  jz      loc_180040878
0x1800407d3  lea     rax, [rbp+57h+SidToCheck]
0x1800407d7  mov     r9d, 220h; nSubAuthority1
0x1800407dd  mov     [rsp+0E0h+pSid], rax; pSid
0x1800407e2  lea     rcx, [rbp+57h+var_68]; pIdentifierAuthority
0x1800407e6  mov     [rsp+0E0h+nSubAuthority7], r14d; nSubAuthority7
0x1800407eb  mov     r8d, 20h ; ' '; nSubAuthority0
0x1800407f1  mov     [rsp+0E0h+nSubAuthority6], r14d; nSubAuthority6
0x1800407f6  mov     dl, 2; nSubAuthorityCount
0x1800407f8  mov     [rsp+0E0h+nSubAuthority5], r14d; nSubAuthority5
0x1800407fd  mov     [rsp+0E0h+nSubAuthority4], r14d; nSubAuthority4
0x180040802  mov     [rsp+0E0h+nSubAuthority3], r14d; nSubAuthority3
0x180040807  mov     [rsp+0E0h+nSubAuthority2], r14d; nSubAuthority2
0x18004080c  call    cs:__imp_AllocateAndInitializeSid
0x180040813  nop     dword ptr [rax+rax+00h]
0x180040818  test    eax, eax
0x18004081a  jz      short loc_180040878
0x18004081c  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180040820  lea     r8, [rbp+57h+IsMember]; IsMember
0x180040824  mov     rcx, rdi; TokenHandle
0x180040827  call    cs:__imp_CheckTokenMembership
0x18004082e  nop     dword ptr [rax+rax+00h]
0x180040833  test    eax, eax
0x180040835  jnz     short loc_180040868
0x180040837  mov     rcx, cs:WPP_GLOBAL_Control
0x18004083e  cmp     rcx, r13
0x180040841  jz      short loc_180040864
0x180040843  test    [rcx+1Ch], r12d
0x180040847  jz      short loc_180040864
0x180040849  cmp     byte ptr [rcx+19h], 2
0x18004084d  jb      short loc_180040864
0x18004084f  mov     rcx, [rcx+10h]
0x180040853  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18004085a  mov     edx, 22Ch
0x18004085f  call    WPP_SF_
0x180040864  mov     [rbp+57h+IsMember], r14d
0x180040868  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x18004086c  call    cs:__imp_FreeSid
0x180040873  nop     dword ptr [rax+rax+00h]
0x180040878  test    esi, esi
0x18004087a  jz      short loc_1800408E7
0x18004087c  call    cs:__imp_RpcRevertToSelf
0x180040883  nop     dword ptr [rax+rax+00h]
0x180040888  mov     ebx, eax
0x18004088a  test    eax, eax
0x18004088c  jz      short loc_1800408E7
0x18004088e  mov     rcx, cs:WPP_GLOBAL_Control
0x180040895  cmp     rcx, r13
0x180040898  jz      short loc_1800408BE
0x18004089a  test    [rcx+1Ch], r12d
0x18004089e  jz      short loc_1800408BE
0x1800408a0  cmp     byte ptr [rcx+19h], 2
0x1800408a4  jb      short loc_1800408BE
0x1800408a6  mov     rcx, [rcx+10h]
0x1800408aa  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x1800408b1  mov     edx, 22Dh
0x1800408b6  mov     r9d, eax
0x1800408b9  call    WPP_SF_d
0x1800408be  mov     rcx, cs:hLogEvents; hLogHandle
0x1800408c5  xor     r9d, r9d; dwSubStringCount
0x1800408c8  mov     [rsp+0E0h+nSubAuthority3], ebx; dwErrorCode
0x1800408cc  mov     r8d, 4EEAh; dwMessageId
0x1800408d2  mov     qword ptr [rsp+0E0h+nSubAuthority2], r14; plpszSubStringArray
0x1800408d7  lea     edx, [r9+2]; dwEventType
0x1800408db  call    cs:__imp_RouterLogEventA
0x1800408e2  nop     dword ptr [rax+rax+00h]
0x1800408e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800408ee  cmp     rcx, r13
0x1800408f1  jz      short loc_18004091C
0x1800408f3  test    [rcx+1Ch], r12d
0x1800408f7  jz      short loc_18004091C
0x1800408f9  cmp     byte ptr [rcx+19h], 6
0x1800408fd  jb      short loc_18004091C
0x1800408ff  cmp     [rbp+57h+IsMember], r14d
0x180040903  lea     r8, WPP_bc295b8dfe91350f576a20943c6d341a_Traceguids
0x18004090a  mov     rcx, [rcx+10h]
0x18004090e  mov     edx, 22Eh
0x180040913  setnz   r9b
0x180040917  call    WPP_SF_c
0x18004091c  mov     eax, [rbp+57h+IsMember]
0x18004091f  mov     rcx, [rbp+57h+var_30]
0x180040923  xor     rcx, rsp; StackCookie
0x180040926  call    __security_check_cookie
0x18004092b  lea     r11, [rsp+0E0h+var_20]
0x180040933  mov     rbx, [r11+38h]
0x180040937  mov     rsi, [r11+40h]
0x18004093b  mov     rsp, r11
0x18004093e  pop     r14
0x180040940  pop     r13
0x180040942  pop     r12
0x180040944  pop     rdi
0x180040945  pop     rbp
0x180040946  retn
```
