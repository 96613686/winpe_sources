# GmsapCheckGMSAExistsInAD(_UNICODE_STRING const *,int *,ldap * *,ushort * *)

- ea: `0x1800025b0`
- end: `0x180002a5e`
- name: `?GmsapCheckGMSAExistsInAD@@YAJPEBU_UNICODE_STRING@@PEAHPEAPEAUldap@@PEAPEAG@Z`
- size: `1198`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, int *, struct ldap **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180005380`
- `0x1800054f0`

## callees

- `0x1800025b0`
- `0x180002b18`
- `0x18000461c`
- `0x180006280`
- `0x1800062b0`
- `0x18000634c`
- `0x180006a38`
- `0x180007378`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002703`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000271e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000273d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800026e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002703`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000271e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000273d`
- `WLDAP32!__imp_ldap_unbind` at `0x180002758`
- `WLDAP32!__imp_ldap_unbind` at `0x180002758`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000283f`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800028fa`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002a0b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000283f`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800028fa`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002a0b`
- `RPCRT4!RpcImpersonateClient` at `0x180002831`
- `RPCRT4!RpcImpersonateClient` at `0x180002831`
- `RPCRT4!RpcRevertToSelf` at `0x1800028ec`
- `RPCRT4!RpcRevertToSelf` at `0x1800029fd`
- `RPCRT4!RpcRevertToSelf` at `0x1800028ec`
- `RPCRT4!RpcRevertToSelf` at `0x1800029fd`
- `netutils!NetApiBufferFree` at `0x180002777`
- `netutils!NetApiBufferFree` at `0x180002777`

## pseudocode

```c
__int64 __fastcall GmsapCheckGMSAExistsInAD(const struct _UNICODE_STRING *a1, int *a2, struct ldap **a3, LPVOID *a4)
{
  int v4; // r12d
  PWSTR v5; // rsi
  LDAP *v6; // rdi
  int v11; // eax
  int v12; // ebx
  _QWORD *v13; // rcx
  int v15; // eax
  __int64 v16; // rdx
  RPC_STATUS v17; // eax
  int v18; // eax
  RPC_STATUS v19; // eax
  int v20; // eax
  int AccountObject; // eax
  RPC_STATUS v22; // eax
  int v23; // eax
  int v24; // r14d
  int v25; // [rsp+20h] [rbp-50h]
  PWSTR HostName; // [rsp+40h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-28h] BYREF
  LPVOID Buffer; // [rsp+50h] [rbp-20h]
  HLOCAL v29; // [rsp+58h] [rbp-18h] BYREF
  HLOCAL v30; // [rsp+60h] [rbp-10h] BYREF
  HLOCAL v31; // [rsp+68h] [rbp-8h] BYREF
  int v32; // [rsp+B8h] [rbp+48h] BYREF
  int v33; // [rsp+C0h] [rbp+50h]
  LDAP *ld; // [rsp+C8h] [rbp+58h]

  v4 = 0;
  v33 = 1;
  v5 = 0;
  HostName = 0;
  v30 = 0;
  v6 = 0;
  ld = 0;
  Buffer = 0;
  v32 = 0;
  hMem = 0;
  v31 = 0;
  v29 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, &WPP_70b8577d707437755865c965214ce19a_Traceguids);
  *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v11 = GmsapParseAccountNamesLocally(
          0,
          a1,
          0,
          (unsigned __int16 **)&hMem,
          (unsigned __int16 **)&v31,
          (unsigned __int16 **)&v29,
          &v32);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v15 = GmsapCrackDomainName(0, 0, (const unsigned __int16 *)v29, &HostName, 0, (unsigned __int16 **)&v30);
    v12 = v15;
    if ( v15 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v16 = 95;
LABEL_36:
        WPP_SF_D(v13[2], v16, &WPP_70b8577d707437755865c965214ce19a_Traceguids, (unsigned int)v15);
        v5 = HostName;
        goto LABEL_12;
      }
      goto LABEL_42;
    }
    if ( dword_18000B680 )
    {
      v17 = RpcImpersonateClient(0);
      v15 = I_RpcMapWin32Status(v17);
      v12 = v15;
      if ( v15 < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v16 = 96;
          goto LABEL_36;
        }
LABEL_42:
        v5 = HostName;
        goto LABEL_13;
      }
      v4 = 1;
    }
    v5 = HostName;
    v18 = GmsapLdapBind(HostName, v25);
    v12 = v18;
    if ( v18 >= 0 )
    {
      if ( dword_18000B680 )
      {
        v4 = 0;
        v19 = RpcRevertToSelf();
        v20 = I_RpcMapWin32Status(v19);
        v12 = v20;
        if ( v20 < 0 )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              98,
              &WPP_70b8577d707437755865c965214ce19a_Traceguids,
              (unsigned int)v20);
            v6 = ld;
            goto LABEL_12;
          }
          v6 = ld;
          goto LABEL_13;
        }
      }
      v6 = ld;
      AccountObject = GmsapGetAccountObject(ld);
      v12 = AccountObject;
      if ( AccountObject < 0 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_SD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            99,
            (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
            (_DWORD)hMem,
            AccountObject);
          v13 = WPP_GLOBAL_Control;
        }
        if ( v12 == -1073741275 || v12 == -1073741788 )
          v12 = 0;
LABEL_68:
        if ( v4 )
        {
          v22 = RpcRevertToSelf();
          v23 = I_RpcMapWin32Status(v22);
          v24 = v23;
          if ( v23 >= 0 )
            goto LABEL_12;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              100,
              &WPP_70b8577d707437755865c965214ce19a_Traceguids,
              (unsigned int)v23);
            v13 = WPP_GLOBAL_Control;
          }
          if ( v12 >= 0 )
            v12 = v24;
        }
        goto LABEL_13;
      }
      *a2 = 1;
      if ( a3 )
      {
        *a3 = v6;
        v6 = 0;
      }
      if ( a4 )
      {
        *a4 = Buffer;
        Buffer = 0;
      }
      v12 = 0;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        v6 = ld;
        goto LABEL_68;
      }
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        97,
        (unsigned int)&WPP_70b8577d707437755865c965214ce19a_Traceguids,
        (_DWORD)v5,
        v18);
      v6 = ld;
    }
    v13 = WPP_GLOBAL_Control;
    goto LABEL_68;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      94,
      &WPP_70b8577d707437755865c965214ce19a_Traceguids,
      (unsigned int)v11);
LABEL_12:
    v13 = WPP_GLOBAL_Control;
  }
LABEL_13:
  if ( v32 )
  {
    if ( hMem )
    {
      LocalFree(hMem);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v31 )
    {
      LocalFree(v31);
      v13 = WPP_GLOBAL_Control;
    }
    if ( v29 )
    {
      LocalFree(v29);
      v13 = WPP_GLOBAL_Control;
    }
  }
  if ( v5 )
  {
    LocalFree(v5);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v30 )
  {
    LocalFree(v30);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    ldap_unbind(v6);
    v13 = WPP_GLOBAL_Control;
  }
  if ( Buffer )
  {
    NetApiBufferFree(Buffer);
    v13 = WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
    WPP_SF_D(v13[2], 101, &WPP_70b8577d707437755865c965214ce19a_Traceguids, (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800025b0  mov     [rsp-38h+arg_0], rbx
0x1800025b5  push    rbp
0x1800025b6  push    rsi
0x1800025b7  push    rdi
0x1800025b8  push    r12
0x1800025ba  push    r13
0x1800025bc  push    r14
0x1800025be  push    r15
0x1800025c0  mov     rbp, rsp
0x1800025c3  sub     rsp, 70h
0x1800025c7  xor     r12d, r12d
0x1800025ca  mov     [rbp+arg_10], 1
0x1800025d1  mov     esi, r12d
0x1800025d4  mov     [rbp+HostName], r12
0x1800025d8  mov     [rbp+var_10], r12
0x1800025dc  mov     edi, r12d
0x1800025df  mov     [rbp+ld], r12
0x1800025e3  mov     r14, r9
0x1800025e6  mov     [rbp+Buffer], r12
0x1800025ea  mov     r15, r8
0x1800025ed  mov     [rbp+arg_8], r12d
0x1800025f1  mov     r13, rdx
0x1800025f4  mov     [rbp+hMem], r12
0x1800025f8  mov     rbx, rcx
0x1800025fb  mov     [rbp+var_8], r12
0x1800025ff  mov     [rbp+var_18], r12
0x180002603  mov     rcx, cs:WPP_GLOBAL_Control
0x18000260a  lea     rax, WPP_GLOBAL_Control
0x180002611  cmp     rcx, rax
0x180002614  jz      short loc_180002631
0x180002616  test    byte ptr [rcx+1Ch], 8
0x18000261a  jz      short loc_180002631
0x18000261c  mov     rcx, [rcx+10h]
0x180002620  lea     edx, [r12+5Dh]
0x180002625  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x18000262c  call    WPP_SF_
0x180002631  mov     [r13+0], r12d
0x180002635  test    r15, r15
0x180002638  jz      short loc_18000263D
0x18000263a  mov     [r15], r12
0x18000263d  test    r14, r14
0x180002640  jz      short loc_180002645
0x180002642  mov     [r14], r12
0x180002645  lea     rax, [rbp+arg_8]
0x180002649  xor     r8d, r8d; struct _UNICODE_STRING *
0x18000264c  mov     [rsp+70h+var_40], rax; int *
0x180002651  lea     r9, [rbp+hMem]; unsigned __int16 **
0x180002655  lea     rax, [rbp+var_18]
0x180002659  mov     rdx, rbx; struct _UNICODE_STRING *
0x18000265c  mov     [rsp+70h+var_48], rax; unsigned __int16 **
0x180002661  xor     ecx, ecx; struct _tagGMsaListEntry *
0x180002663  lea     rax, [rbp+var_8]
0x180002667  mov     [rsp+70h+var_50], rax; unsigned __int16 **
0x18000266c  call    ?GmsapParseAccountNamesLocally@@YAJPEAU_tagGMsaListEntry@@PEBU_UNICODE_STRING@@1PEAPEAG22PEAH@Z; GmsapParseAccountNamesLocally(_tagGMsaListEntry *,_UNICODE_STRING const *,_UNICODE_STRING const *,ushort * *,ushort * *,ushort * *,int *)
0x180002671  mov     ebx, eax
0x180002673  test    eax, eax
0x180002675  jns     loc_1800027C8
0x18000267b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002682  lea     r15, WPP_GLOBAL_Control
0x180002689  cmp     rcx, r15
0x18000268c  jz      short loc_1800026B3
0x18000268e  test    byte ptr [rcx+1Ch], 4
0x180002692  jz      short loc_1800026B3
0x180002694  mov     rcx, [rcx+10h]
0x180002698  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x18000269f  mov     edx, 5Eh ; '^'
0x1800026a4  mov     r9d, eax
0x1800026a7  call    WPP_SF_D
0x1800026ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026b3  cmp     [rbp+arg_8], 0
0x1800026b7  jz      short loc_180002716
0x1800026b9  mov     rax, [rbp+hMem]
0x1800026bd  test    rax, rax
0x1800026c0  jz      short loc_1800026D8
0x1800026c2  mov     rcx, rax; hMem
0x1800026c5  call    cs:__imp_LocalFree
0x1800026cc  nop     dword ptr [rax+rax+00h]
0x1800026d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026d8  mov     rax, [rbp+var_8]
0x1800026dc  test    rax, rax
0x1800026df  jz      short loc_1800026F7
0x1800026e1  mov     rcx, rax; hMem
0x1800026e4  call    cs:__imp_LocalFree
0x1800026eb  nop     dword ptr [rax+rax+00h]
0x1800026f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800026f7  mov     rax, [rbp+var_18]
0x1800026fb  test    rax, rax
0x1800026fe  jz      short loc_180002716
0x180002700  mov     rcx, rax; hMem
0x180002703  call    cs:__imp_LocalFree
0x18000270a  nop     dword ptr [rax+rax+00h]
0x18000270f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002716  test    rsi, rsi
0x180002719  jz      short loc_180002731
0x18000271b  mov     rcx, rsi; hMem
0x18000271e  call    cs:__imp_LocalFree
0x180002725  nop     dword ptr [rax+rax+00h]
0x18000272a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002731  mov     rax, [rbp+var_10]
0x180002735  test    rax, rax
0x180002738  jz      short loc_180002750
0x18000273a  mov     rcx, rax; hMem
0x18000273d  call    cs:__imp_LocalFree
0x180002744  nop     dword ptr [rax+rax+00h]
0x180002749  mov     rcx, cs:WPP_GLOBAL_Control
0x180002750  test    rdi, rdi
0x180002753  jz      short loc_18000276B
0x180002755  mov     rcx, rdi; ld
0x180002758  call    cs:__imp_ldap_unbind
0x18000275f  nop     dword ptr [rax+rax+00h]
0x180002764  mov     rcx, cs:WPP_GLOBAL_Control
0x18000276b  mov     rax, [rbp+Buffer]
0x18000276f  test    rax, rax
0x180002772  jz      short loc_18000278A
0x180002774  mov     rcx, rax; Buffer
0x180002777  call    cs:__imp_NetApiBufferFree
0x18000277e  nop     dword ptr [rax+rax+00h]
0x180002783  mov     rcx, cs:WPP_GLOBAL_Control
0x18000278a  cmp     rcx, r15
0x18000278d  jz      short loc_1800027AD
0x18000278f  test    byte ptr [rcx+1Ch], 8
0x180002793  jz      short loc_1800027AD
0x180002795  mov     rcx, [rcx+10h]
0x180002799  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x1800027a0  mov     edx, 65h ; 'e'
0x1800027a5  mov     r9d, ebx
0x1800027a8  call    WPP_SF_D
0x1800027ad  mov     eax, ebx
0x1800027af  mov     rbx, [rsp+70h+arg_0]
0x1800027b7  add     rsp, 70h
0x1800027bb  pop     r15
0x1800027bd  pop     r14
0x1800027bf  pop     r13
0x1800027c1  pop     r12
0x1800027c3  pop     rdi
0x1800027c4  pop     rsi
0x1800027c5  pop     rbp
0x1800027c6  retn
0x1800027c8  mov     r8, [rbp+var_18]; unsigned __int16 *
0x1800027cc  lea     rax, [rbp+var_10]
0x1800027d0  mov     [rsp+70h+var_48], rax; unsigned __int16 **
0x1800027d5  lea     r9, [rbp+HostName]; unsigned __int16 **
0x1800027d9  xor     edx, edx; int
0x1800027db  mov     [rsp+70h+var_50], r12; invalue
0x1800027e0  xor     ecx, ecx; int
0x1800027e2  call    ?GmsapCrackDomainName@@YAJHHPEBGPEAPEAG11@Z; GmsapCrackDomainName(int,int,ushort const *,ushort * *,ushort * *,ushort * *)
0x1800027e7  mov     ebx, eax
0x1800027e9  test    eax, eax
0x1800027eb  jns     short loc_180002827
0x1800027ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800027f4  lea     r15, WPP_GLOBAL_Control
0x1800027fb  cmp     rcx, r15
0x1800027fe  jz      short loc_180002871
0x180002800  test    byte ptr [rcx+1Ch], 4
0x180002804  jz      short loc_180002871
0x180002806  mov     edx, 5Fh ; '_'
0x18000280b  mov     rcx, [rcx+10h]
0x18000280f  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180002816  mov     r9d, eax
0x180002819  call    WPP_SF_D
0x18000281e  mov     rsi, [rbp+HostName]
0x180002822  jmp     loc_1800026AC
0x180002827  cmp     cs:dword_18000B680, esi
0x18000282d  jz      short loc_180002880
0x18000282f  xor     ecx, ecx; BindingHandle
0x180002831  call    cs:__imp_RpcImpersonateClient
0x180002838  nop     dword ptr [rax+rax+00h]
0x18000283d  mov     ecx, eax; Status
0x18000283f  call    cs:__imp_I_RpcMapWin32Status
0x180002846  nop     dword ptr [rax+rax+00h]
0x18000284b  mov     ebx, eax
0x18000284d  test    eax, eax
0x18000284f  jns     short loc_18000287A
0x180002851  mov     rcx, cs:WPP_GLOBAL_Control
0x180002858  lea     r15, WPP_GLOBAL_Control
0x18000285f  cmp     rcx, r15
0x180002862  jz      short loc_180002871
0x180002864  test    byte ptr [rcx+1Ch], 4
0x180002868  jz      short loc_180002871
0x18000286a  mov     edx, 60h ; '`'
0x18000286f  jmp     short loc_18000280B
0x180002871  mov     rsi, [rbp+HostName]
0x180002875  jmp     loc_1800026B3
0x18000287a  mov     r12d, 1
0x180002880  mov     rsi, [rbp+HostName]
0x180002884  lea     r8, [rbp+ld]
0x180002888  mov     rdx, [rbp+var_10]
0x18000288c  mov     rcx, rsi; HostName
0x18000288f  call    GmsapLdapBind
0x180002894  mov     ebx, eax
0x180002896  test    eax, eax
0x180002898  jns     short loc_1800028E1
0x18000289a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028a1  lea     r15, WPP_GLOBAL_Control
0x1800028a8  cmp     rcx, r15
0x1800028ab  jz      short loc_1800028D8
0x1800028ad  test    byte ptr [rcx+1Ch], 4
0x1800028b1  jz      short loc_1800028D8
0x1800028b3  mov     rcx, [rcx+10h]
0x1800028b7  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x1800028be  mov     edx, 61h ; 'a'
0x1800028c3  mov     dword ptr [rsp+70h+var_50], eax
0x1800028c7  mov     r9, rsi
0x1800028ca  call    WPP_SF_SD
0x1800028cf  mov     rdi, [rbp+ld]
0x1800028d3  jmp     loc_1800029ED
0x1800028d8  mov     rdi, [rbp+ld]
0x1800028dc  jmp     loc_1800029F4
0x1800028e1  cmp     cs:dword_18000B680, edi
0x1800028e7  jz      short loc_18000294F
0x1800028e9  xor     r12d, r12d
0x1800028ec  call    cs:__imp_RpcRevertToSelf
0x1800028f3  nop     dword ptr [rax+rax+00h]
0x1800028f8  mov     ecx, eax; Status
0x1800028fa  call    cs:__imp_I_RpcMapWin32Status
0x180002901  nop     dword ptr [rax+rax+00h]
0x180002906  mov     ebx, eax
0x180002908  test    eax, eax
0x18000290a  jns     short loc_18000294F
0x18000290c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002913  lea     r15, WPP_GLOBAL_Control
0x18000291a  cmp     rcx, r15
0x18000291d  jz      short loc_180002946
0x18000291f  test    byte ptr [rcx+1Ch], 4
0x180002923  jz      short loc_180002946
0x180002925  mov     rcx, [rcx+10h]
0x180002929  lea     edx, [r12+62h]
0x18000292e  mov     r9d, eax
0x180002931  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180002938  call    WPP_SF_D
0x18000293d  mov     rdi, [rbp+ld]
0x180002941  jmp     loc_1800026AC
0x180002946  mov     rdi, [rbp+ld]
0x18000294a  jmp     loc_1800026B3
0x18000294f  mov     rdi, [rbp+ld]
0x180002953  lea     r9, [rbp+arg_10]
0x180002957  mov     rdx, [rbp+hMem]
0x18000295b  lea     r8, [rbp+Buffer]
0x18000295f  mov     rcx, rdi; ld
0x180002962  call    GmsapGetAccountObject
0x180002967  mov     ebx, eax
0x180002969  test    eax, eax
0x18000296b  jns     short loc_1800029BE
0x18000296d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002974  lea     r15, WPP_GLOBAL_Control
0x18000297b  cmp     rcx, r15
0x18000297e  jz      short loc_1800029AA
0x180002980  test    byte ptr [rcx+1Ch], 4
0x180002984  jz      short loc_1800029AA
0x180002986  mov     r9, [rbp+hMem]
0x18000298a  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180002991  mov     rcx, [rcx+10h]
0x180002995  mov     edx, 63h ; 'c'
0x18000299a  mov     dword ptr [rsp+70h+var_50], eax
0x18000299e  call    WPP_SF_SD
0x1800029a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029aa  cmp     ebx, 0C0000225h
0x1800029b0  jz      short loc_1800029BA
0x1800029b2  cmp     ebx, 0C0000024h
0x1800029b8  jnz     short loc_1800029F4
0x1800029ba  xor     ebx, ebx
0x1800029bc  jmp     short loc_1800029F4
0x1800029be  mov     dword ptr [r13+0], 1
0x1800029c6  test    r15, r15
0x1800029c9  jz      short loc_1800029D0
0x1800029cb  mov     [r15], rdi
0x1800029ce  xor     edi, edi
0x1800029d0  test    r14, r14
0x1800029d3  jz      short loc_1800029E4
0x1800029d5  mov     rax, [rbp+Buffer]
0x1800029d9  mov     [r14], rax
0x1800029dc  mov     [rbp+Buffer], 0
0x1800029e4  xor     ebx, ebx
0x1800029e6  lea     r15, WPP_GLOBAL_Control
0x1800029ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029f4  test    r12d, r12d
0x1800029f7  jz      loc_1800026B3
0x1800029fd  call    cs:__imp_RpcRevertToSelf
0x180002a04  nop     dword ptr [rax+rax+00h]
0x180002a09  mov     ecx, eax; Status
0x180002a0b  call    cs:__imp_I_RpcMapWin32Status
0x180002a12  nop     dword ptr [rax+rax+00h]
0x180002a17  mov     r14d, eax
0x180002a1a  test    eax, eax
0x180002a1c  jns     loc_1800026AC
0x180002a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a29  cmp     rcx, r15
0x180002a2c  jz      short loc_180002A53
0x180002a2e  test    byte ptr [rcx+1Ch], 4
0x180002a32  jz      short loc_180002A53
0x180002a34  mov     rcx, [rcx+10h]
0x180002a38  lea     r8, WPP_70b8577d707437755865c965214ce19a_Traceguids
0x180002a3f  mov     edx, 64h ; 'd'
0x180002a44  mov     r9d, eax
0x180002a47  call    WPP_SF_D
0x180002a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a53  test    ebx, ebx
0x180002a55  cmovns  ebx, r14d
0x180002a59  jmp     loc_1800026B3
```
