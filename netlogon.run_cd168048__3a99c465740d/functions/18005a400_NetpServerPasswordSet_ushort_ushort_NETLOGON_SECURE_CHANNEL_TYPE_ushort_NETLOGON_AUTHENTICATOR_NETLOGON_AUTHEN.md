# NetpServerPasswordSet(ushort *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,ushort *,_NETLOGON_AUTHENTICATOR *,_NETLOGON_AUTHENTICATOR *,_ENCRYPTED_LM_OWF_PASSWORD *,_NL_TRUST_PASSWORD *)

- ea: `0x18005a400`
- end: `0x18005aa09`
- name: `?NetpServerPasswordSet@@YAJPEAG0W4_NETLOGON_SECURE_CHANNEL_TYPE@@0PEAU_NETLOGON_AUTHENTICATOR@@2PEAU_ENCRYPTED_LM_OWF_PASSWORD@@PEAU_NL_TRUST_PASSWORD@@@Z`
- size: `1545`
- prototype: `int __high(unsigned __int16 *, unsigned __int16 *, enum _NETLOGON_SECURE_CHANNEL_TYPE, unsigned __int16 *, struct _NETLOGON_AUTHENTICATOR *, struct _NETLOGON_AUTHENTICATOR *, struct _ENCRYPTED_LM_OWF_PASSWORD *, struct _NL_TRUST_PASSWORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180063200`
- `0x180063240`

## callees

- `0x180007518`
- `0x18000c440`
- `0x18000e910`
- `0x1800267ec`
- `0x1800271d4`
- `0x1800374dc`
- `0x18003a734`
- `0x180057174`
- `0x18005a400`
- `0x1800639bc`
- `0x180063f08`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x18005a5ae`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a61b`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a652`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a66b`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a5ae`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a61b`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a652`
- `ntdll!RtlLeaveCriticalSection` at `0x18005a66b`
- `ntdll!RtlEnterCriticalSection` at `0x18005a58c`
- `ntdll!RtlEnterCriticalSection` at `0x18005a58c`
- `CRYPTSP!SystemFunction007` at `0x18005a7bf`
- `CRYPTSP!SystemFunction007` at `0x18005a7bf`
- `CRYPTSP!SystemFunction030` at `0x18005a900`
- `CRYPTSP!SystemFunction030` at `0x18005a900`
- `CRYPTSP!SystemFunction031` at `0x18005a7ff`
- `CRYPTSP!SystemFunction031` at `0x18005a7ff`
- `CRYPTSP!SystemFunction013` at `0x18005a8da`
- `CRYPTSP!SystemFunction013` at `0x18005a8da`

## string_xrefs

- `0x18005a4ce`: `NetpServerPasswordSet: Comp=%ws Acc=%ws Entered\n`
- `0x18005a561`: `NetpServerPasswordSet: Comp=%ws Acc=%ws failed because NlGetIncomingPassword failed with ntstatus 0x%x\n`
- `0x18005a5d0`: `%ws:%d attempts to set password for different account: %ws:%d\n`
- `0x18005a7d3`: `NetpServerPasswordSet: Comp=%ws Acc=%ws failed because RtlCalculateNtOwfPassword failed with ntstatus 0x%x\n`
- `0x18005a91c`: `NetpServerPasswordSet: Comp=%ws Ac=%ws Not changing password -- already changed\n`
- `0x18005a826`: `NetpServerPasswordSet: Comp=%ws Acc=%ws Changing password locally\n`
- `0x18005a9ba`: `NetpServerPasswordSet: Comp=%ws Acc=%ws returns 0x%lX\n`

## pseudocode

```c
__int64 __fastcall NetpServerPasswordSet(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        struct _NETLOGON_AUTHENTICATOR *a5,
        struct _NETLOGON_AUTHENTICATOR *a6,
        __int64 a7,
        _OWORD *a8)
{
  struct _NETLOGON_AUTHENTICATOR *v8; // rsi
  struct _DOMAIN_INFO *DomainByServerName; // rdi
  int v14; // ebx
  int IncomingPassword; // eax
  struct _SERVER_SESSION *NamedServerSession; // rax
  struct _SERVER_SESSION *v17; // r14
  _OWORD *v18; // r14
  _OWORD *v19; // rcx
  __int64 v20; // rdx
  _OWORD *v21; // rax
  __int128 v22; // xmm1
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  int v29; // esi
  _BYTE *v30; // rax
  int v31; // eax
  __int128 *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  __int128 *v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int128 *v38; // rcx
  __int64 v39; // rdx
  __int128 *v40; // rcx
  __int128 *v41; // rdx
  __int64 v42; // [rsp+28h] [rbp-D8h]
  unsigned int v43; // [rsp+78h] [rbp-88h] BYREF
  _OWORD *v44; // [rsp+80h] [rbp-80h]
  __int128 v45; // [rsp+88h] [rbp-78h] BYREF
  __int64 v46; // [rsp+98h] [rbp-68h]
  _BYTE v47[500]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v48[12]; // [rsp+294h] [rbp+194h] BYREF
  unsigned int v49; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v50; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v51; // [rsp+2C0h] [rbp+1C0h] BYREF
  int v52; // [rsp+2D0h] [rbp+1D0h]
  __int128 v53; // [rsp+2D8h] [rbp+1D8h] BYREF

  v8 = a6;
  v46 = a7;
  v44 = a8;
  v51 = 0;
  v52 = 0;
  v50 = 0;
  v43 = 0;
  v45 = 0;
  v53 = 0;
  if ( NlGlobalMemberWorkstation )
    return 3221225659LL;
  if ( NlGlobalDsPaused )
  {
    DomainByServerName = 0;
    NlPrintRoutine(0x100u, L"NetpServerPasswordSet: DsIsPaused.\n");
    v14 = -1073741147;
    goto LABEL_58;
  }
  DomainByServerName = NlFindDomainByServerName(a1);
  NlPrintDomRoutine(0x200u, DomainByServerName, L"NetpServerPasswordSet: Comp=%ws Acc=%ws Entered\n", a4, a2);
  if ( !DomainByServerName )
  {
    v14 = -1073741534;
    goto LABEL_58;
  }
  IncomingPassword = NlGetIncomingPassword((__int64)DomainByServerName, a2, a3, 0, 0, &v53, 0, &v43, 0, 0, 0, 0, 0);
  if ( IncomingPassword < 0 )
  {
    LODWORD(v42) = IncomingPassword;
    NlPrintDomRoutine(
      0x100u,
      DomainByServerName,
      L"NetpServerPasswordSet: Comp=%ws Acc=%ws failed because NlGetIncomingPassword failed with ntstatus 0x%x\n",
      a4,
      a2,
      v42);
LABEL_55:
    v14 = -1073741790;
LABEL_56:
    v33 = 12;
    do
    {
      *(_BYTE *)v8 = 0;
      v8 = (struct _NETLOGON_AUTHENTICATOR *)((char *)v8 + 1);
      --v33;
    }
    while ( v33 );
    goto LABEL_58;
  }
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)DomainByServerName + 504));
  NamedServerSession = NlFindNamedServerSession(DomainByServerName, a4);
  v17 = NamedServerSession;
  if ( !NamedServerSession )
    goto LABEL_10;
  if ( *((_DWORD *)NamedServerSession + 13) != v43 )
  {
    NlPrintRoutine(0x100u, L"%ws:%d attempts to set password for different account: %ws:%d\n", a4);
LABEL_10:
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)DomainByServerName + 504));
LABEL_54:
    v8 = a6;
    goto LABEL_55;
  }
  v51 = *((_OWORD *)NamedServerSession + 6);
  v52 = *((_DWORD *)NamedServerSession + 18);
  v14 = NlCheckAuthenticator(NamedServerSession, a5, a6);
  if ( v14 < 0 )
  {
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)DomainByServerName + 504));
    goto LABEL_42;
  }
  if ( dword_1800F8120 && a3 == 2 && (*((_DWORD *)v17 + 8) == 6 || (v52 & 0x100) != 0) )
  {
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)DomainByServerName + 504));
    v14 = -1073741718;
    goto LABEL_58;
  }
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)DomainByServerName + 504));
  if ( v44 )
  {
    v18 = v44;
    v19 = v47;
    v20 = 4;
    v21 = v44;
    do
    {
      v22 = v21[1];
      *v19 = *v21;
      v23 = v21[2];
      v19[1] = v22;
      v24 = v21[3];
      v19[2] = v23;
      v25 = v21[4];
      v19[3] = v24;
      v26 = v21[5];
      v19[4] = v25;
      v27 = v21[6];
      v19[5] = v26;
      v28 = v21[7];
      v21 += 8;
      v19[6] = v27;
      v19[7] = v28;
      v19 += 8;
      --v20;
    }
    while ( v20 );
    *(_DWORD *)v19 = *(_DWORD *)v21;
    NlDecrypt(v47, 0x204u, (struct _SESSION_INFO *)&v51);
    if ( a3 - 3 <= 1 )
    {
      if ( v49 >= 0x1F4 || (v49 & 1) != 0 )
      {
        NlPrintDomRoutine(
          0x100u,
          DomainByServerName,
          L"NetpServerPasswordSet: Decrypted interdomain password is too long %ld\n");
        goto LABEL_54;
      }
    }
    else if ( v49 >= 0x200 || (v49 & 1) != 0 )
    {
      NlPrintDomRoutine(0x100u, DomainByServerName, L"NetpServerPasswordSet: Decrypted password is too long %ld\n");
      goto LABEL_54;
    }
    LOWORD(v45) = v49;
    *((_QWORD *)&v45 + 1) = (char *)&v49 - v49;
    v29 = 0;
    WORD1(v45) = v49;
    if ( a3 - 3 <= 1 )
    {
      if ( *(_DWORD *)&v48[-v49 + 8] == 35854696 && (v30 = &v48[-v49], *((_DWORD *)v30 + 1)) )
      {
        v29 = *((_DWORD *)v30 + 1);
        NlPrintDomRoutine(0x200u, DomainByServerName, L"NetpServerPasswordSet: Got password version number 0x%lx\n");
      }
      else
      {
        NlPrintDomRoutine(0x200u, DomainByServerName, L"NetpServerPasswordSet: Got no password version number\n");
      }
    }
    v31 = SystemFunction007(&v45, &v50);
    if ( v31 < 0 )
    {
      LODWORD(v42) = v31;
      NlPrintDomRoutine(
        0x100u,
        DomainByServerName,
        L"NetpServerPasswordSet: Comp=%ws Acc=%ws failed because RtlCalculateNtOwfPassword failed with ntstatus 0x%x\n",
        a4,
        a2,
        v42);
      goto LABEL_54;
    }
    if ( (unsigned __int8)SystemFunction031(&v53, &v50) )
      goto LABEL_51;
    if ( !v46 )
      goto LABEL_39;
  }
  else
  {
    if ( !v46 )
    {
      NlPrintDomRoutine(0x100u, DomainByServerName, L"NetpServerPasswordSet: Neither clear nor OWF password.\n");
      goto LABEL_54;
    }
    if ( *((int *)v17 + 18) < 0 )
    {
      NlPrintDomRoutine(0x100u, DomainByServerName, L"NetpServerPasswordSet: LMOWF was used with Kerberos RPC.\n");
      v14 = -1073741637;
      goto LABEL_58;
    }
    v14 = SystemFunction013(v46, &v51, &v50);
    if ( v14 )
      goto LABEL_42;
    v18 = v44;
    v29 = 0;
  }
  if ( (unsigned __int8)SystemFunction030(&v53, &v50) )
  {
LABEL_51:
    NlPrintDomRoutine(
      0x200u,
      DomainByServerName,
      L"NetpServerPasswordSet: Comp=%ws Ac=%ws Not changing password -- already changed\n",
      a4,
      a2);
LABEL_52:
    v14 = 0;
    goto LABEL_58;
  }
LABEL_39:
  NlPrintDomRoutine(
    0x200u,
    DomainByServerName,
    L"NetpServerPasswordSet: Comp=%ws Acc=%ws Changing password locally\n",
    a4,
    a2);
  v32 = &v50;
  if ( v18 )
    v32 = 0;
  v14 = NlSetIncomingPassword(DomainByServerName, a2, a3, (unsigned __int64)&v45 & -(__int64)(v18 != 0), v29, v32);
  if ( v14 >= 0 )
    goto LABEL_52;
LABEL_42:
  if ( v14 == -1073741790 )
  {
    v8 = a6;
    goto LABEL_56;
  }
LABEL_58:
  v34 = 16;
  v35 = &v50;
  v36 = 16;
  do
  {
    *(_BYTE *)v35 = 0;
    v35 = (__int128 *)((char *)v35 + 1);
    --v36;
  }
  while ( v36 );
  v37 = 16;
  v38 = &v45;
  do
  {
    *(_BYTE *)v38 = 0;
    v38 = (__int128 *)((char *)v38 + 1);
    --v37;
  }
  while ( v37 );
  v39 = 16;
  v40 = &v53;
  do
  {
    *(_BYTE *)v40 = 0;
    v40 = (__int128 *)((char *)v40 + 1);
    --v39;
  }
  while ( v39 );
  v41 = &v51;
  do
  {
    *(_BYTE *)v41 = 0;
    v41 = (__int128 *)((char *)v41 + 1);
    --v34;
  }
  while ( v34 );
  LODWORD(v42) = v14;
  NlPrintDomRoutine(0x200u, DomainByServerName, L"NetpServerPasswordSet: Comp=%ws Acc=%ws returns 0x%lX\n", a4, a2, v42);
  if ( DomainByServerName )
    NlDereferenceDomain(DomainByServerName);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18005a400  push    rbp
0x18005a402  push    rbx
0x18005a403  push    rsi
0x18005a404  push    rdi
0x18005a405  push    r12
0x18005a407  push    r13
0x18005a409  push    r14
0x18005a40b  push    r15
0x18005a40d  lea     rbp, [rsp-1F8h]
0x18005a415  sub     rsp, 2F8h
0x18005a41c  mov     rax, cs:__security_cookie
0x18005a423  xor     rax, rsp
0x18005a426  mov     [rbp+230h+var_48], rax
0x18005a42d  mov     rax, [rbp+230h+arg_30]
0x18005a434  xorps   xmm0, xmm0
0x18005a437  mov     rsi, [rbp+230h+arg_28]
0x18005a43e  xorps   xmm1, xmm1
0x18005a441  mov     rbx, [rbp+230h+arg_20]
0x18005a448  mov     r12, r9
0x18005a44b  mov     [rbp+230h+var_298], rax
0x18005a44f  mov     r13d, r8d
0x18005a452  mov     rax, [rbp+230h+arg_38]
0x18005a459  mov     r15, rdx
0x18005a45c  mov     [rbp+230h+var_2B0], rax
0x18005a460  xor     eax, eax
0x18005a462  cmp     cs:?NlGlobalMemberWorkstation@@3HA, eax; int NlGlobalMemberWorkstation
0x18005a468  mov     [rsp+330h+var_2C0], rsi
0x18005a46d  movups  [rbp+230h+var_70], xmm0
0x18005a474  mov     [rbp+230h+var_60], eax
0x18005a47a  movups  [rbp+230h+var_80], xmm0
0x18005a481  mov     [rsp+330h+var_2B8], eax
0x18005a485  movups  [rbp+230h+var_2A8], xmm1
0x18005a489  movups  [rbp+230h+var_58], xmm0
0x18005a490  jz      short loc_18005A49C
0x18005a492  mov     eax, 0C00000BBh
0x18005a497  jmp     loc_18005A9E5
0x18005a49c  cmp     cs:?NlGlobalDsPaused@@3HA, eax; int NlGlobalDsPaused
0x18005a4a2  jz      short loc_18005A4C1
0x18005a4a4  xor     edi, edi
0x18005a4a6  lea     rdx, aNetpserverpass_9; "NetpServerPasswordSet: DsIsPaused.\n"
0x18005a4ad  mov     ecx, 100h; unsigned int
0x18005a4b2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005a4b7  mov     ebx, 0C00002A5h
0x18005a4bc  jmp     loc_18005A960
0x18005a4c1  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x18005a4c6  mov     r9, r12
0x18005a4c9  mov     [rsp+330h+var_310], r15
0x18005a4ce  lea     r8, aNetpserverpass; "NetpServerPasswordSet: Comp=%ws Acc=%ws"...
0x18005a4d5  mov     rdx, rax; struct _DOMAIN_INFO *
0x18005a4d8  mov     ecx, 200h; unsigned int
0x18005a4dd  mov     rdi, rax
0x18005a4e0  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005a4e5  test    rdi, rdi
0x18005a4e8  jnz     short loc_18005A4F4
0x18005a4ea  mov     ebx, 0C0000122h
0x18005a4ef  jmp     loc_18005A960
0x18005a4f4  mov     [rsp+330h+var_2D0], 0
0x18005a4fd  lea     rax, [rsp+330h+var_2B8]
0x18005a502  mov     [rsp+330h+var_2D8], 0
0x18005a50b  xor     r9d, r9d
0x18005a50e  mov     [rsp+330h+var_2E0], 0
0x18005a517  mov     r8d, r13d
0x18005a51a  mov     [rsp+330h+var_2E8], 0
0x18005a523  mov     rdx, r15
0x18005a526  mov     [rsp+330h+var_2F0], 0
0x18005a52f  mov     rcx, rdi
0x18005a532  mov     [rsp+330h+var_2F8], rax
0x18005a537  lea     rax, [rbp+230h+var_58]
0x18005a53e  mov     [rsp+330h+var_300], 0
0x18005a547  mov     [rsp+330h+var_308], rax
0x18005a54c  mov     dword ptr [rsp+330h+var_310], 0
0x18005a554  call    ?NlGetIncomingPassword@@YAJPEAU_DOMAIN_INFO@@PEBGW4_NETLOGON_SECURE_CHANNEL_TYPE@@KHPEAU_LM_OWF_PASSWORD@@3PEAK44PEAPEAXPEAH4@Z; NlGetIncomingPassword(_DOMAIN_INFO *,ushort const *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong,int,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,ulong *,ulong *,ulong *,void * *,int *,ulong *)
0x18005a559  test    eax, eax
0x18005a55b  jns     short loc_18005A582
0x18005a55d  mov     dword ptr [rsp+330h+var_308], eax
0x18005a561  lea     r8, aNetpserverpass_1; "NetpServerPasswordSet: Comp=%ws Acc=%ws"...
0x18005a568  mov     r9, r12
0x18005a56b  mov     [rsp+330h+var_310], r15
0x18005a570  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005a573  mov     ecx, 100h; unsigned int
0x18005a578  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005a57d  jmp     loc_18005A94A
0x18005a582  lea     rsi, [rdi+1F8h]
0x18005a589  mov     rcx, rsi; CriticalSection
0x18005a58c  call    cs:__imp_RtlEnterCriticalSection
0x18005a593  nop     dword ptr [rax+rax+00h]
0x18005a598  mov     rdx, r12; unsigned __int16 *
0x18005a59b  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18005a59e  call    ?NlFindNamedServerSession@@YAPEAU_SERVER_SESSION@@PEAU_DOMAIN_INFO@@PEAG@Z; NlFindNamedServerSession(_DOMAIN_INFO *,ushort *)
0x18005a5a3  mov     r14, rax
0x18005a5a6  test    rax, rax
0x18005a5a9  jnz     short loc_18005A5BF
0x18005a5ab  mov     rcx, rsi; CriticalSection
0x18005a5ae  call    cs:__imp_RtlLeaveCriticalSection
0x18005a5b5  nop     dword ptr [rax+rax+00h]
0x18005a5ba  jmp     loc_18005A945
0x18005a5bf  mov     r9d, [rax+34h]
0x18005a5c3  mov     eax, [rsp+330h+var_2B8]
0x18005a5c7  cmp     r9d, eax
0x18005a5ca  jz      short loc_18005A5EB
0x18005a5cc  mov     dword ptr [rsp+330h+var_308], eax
0x18005a5d0  lea     rdx, aWsDAttemptsToS; "%ws:%d attempts to set password for dif"...
0x18005a5d7  mov     r8, r12
0x18005a5da  mov     [rsp+330h+var_310], r15
0x18005a5df  mov     ecx, 100h; unsigned int
0x18005a5e4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005a5e9  jmp     short loc_18005A5AB
0x18005a5eb  movups  xmm0, xmmword ptr [r14+60h]
0x18005a5f0  mov     r8, [rsp+330h+var_2C0]; struct _NETLOGON_AUTHENTICATOR *
0x18005a5f5  mov     rdx, rbx; struct _NETLOGON_AUTHENTICATOR *
0x18005a5f8  mov     rcx, r14; struct _SERVER_SESSION *
0x18005a5fb  movdqu  [rbp+230h+var_70], xmm0
0x18005a603  mov     eax, [r14+48h]
0x18005a607  mov     [rbp+230h+var_60], eax
0x18005a60d  call    ?NlCheckAuthenticator@@YAJPEAU_SERVER_SESSION@@PEAU_NETLOGON_AUTHENTICATOR@@1@Z; NlCheckAuthenticator(_SERVER_SESSION *,_NETLOGON_AUTHENTICATOR *,_NETLOGON_AUTHENTICATOR *)
0x18005a612  mov     ebx, eax
0x18005a614  test    eax, eax
0x18005a616  jns     short loc_18005A62C
0x18005a618  mov     rcx, rsi; CriticalSection
0x18005a61b  call    cs:__imp_RtlLeaveCriticalSection
0x18005a622  nop     dword ptr [rax+rax+00h]
0x18005a627  jmp     loc_18005A878
0x18005a62c  cmp     cs:dword_1800F8120, 0
0x18005a633  mov     ebx, 100h
0x18005a638  jz      short loc_18005A668
0x18005a63a  cmp     r13d, 2
0x18005a63e  jnz     short loc_18005A668
0x18005a640  cmp     dword ptr [r14+20h], 6
0x18005a645  jz      short loc_18005A64F
0x18005a647  test    [rbp+230h+var_60], ebx
0x18005a64d  jz      short loc_18005A668
0x18005a64f  mov     rcx, rsi; CriticalSection
0x18005a652  call    cs:__imp_RtlLeaveCriticalSection
0x18005a659  nop     dword ptr [rax+rax+00h]
0x18005a65e  mov     ebx, 0C000006Ah
0x18005a663  jmp     loc_18005A960
0x18005a668  mov     rcx, rsi; CriticalSection
0x18005a66b  call    cs:__imp_RtlLeaveCriticalSection
0x18005a672  nop     dword ptr [rax+rax+00h]
0x18005a677  cmp     [rbp+230h+var_2B0], 0
0x18005a67c  jz      loc_18005A89A
0x18005a682  mov     r14, [rbp+230h+var_2B0]
0x18005a686  lea     rcx, [rbp+230h+var_290]
0x18005a68a  mov     edx, 4
0x18005a68f  mov     rax, r14
0x18005a692  lea     r8d, [rdx+7Ch]
0x18005a696  movups  xmm0, xmmword ptr [rax]
0x18005a699  movups  xmm1, xmmword ptr [rax+10h]
0x18005a69d  movups  xmmword ptr [rcx], xmm0
0x18005a6a0  movups  xmm0, xmmword ptr [rax+20h]
0x18005a6a4  movups  xmmword ptr [rcx+10h], xmm1
0x18005a6a8  movups  xmm1, xmmword ptr [rax+30h]
0x18005a6ac  movups  xmmword ptr [rcx+20h], xmm0
0x18005a6b0  movups  xmm0, xmmword ptr [rax+40h]
0x18005a6b4  movups  xmmword ptr [rcx+30h], xmm1
0x18005a6b8  movups  xmm1, xmmword ptr [rax+50h]
0x18005a6bc  movups  xmmword ptr [rcx+40h], xmm0
0x18005a6c0  movups  xmm0, xmmword ptr [rax+60h]
0x18005a6c4  movups  xmmword ptr [rcx+50h], xmm1
0x18005a6c8  movups  xmm1, xmmword ptr [rax+70h]
0x18005a6cc  add     rax, r8
0x18005a6cf  movups  xmmword ptr [rcx+60h], xmm0
0x18005a6d3  movups  xmmword ptr [rcx+70h], xmm1
0x18005a6d7  add     rcx, r8
0x18005a6da  sub     rdx, 1
0x18005a6de  jnz     short loc_18005A696
0x18005a6e0  mov     eax, [rax]
0x18005a6e2  lea     r8, [rbp+230h+var_70]; struct _SESSION_INFO *
0x18005a6e9  mov     [rcx], eax
0x18005a6eb  mov     edx, 204h; unsigned int
0x18005a6f0  lea     rcx, [rbp+230h+var_290]; void *
0x18005a6f4  call    ?NlDecrypt@@YAXPEAXKPEAU_SESSION_INFO@@@Z; NlDecrypt(void *,ulong,_SESSION_INFO *)
0x18005a6f9  mov     r9d, [rbp+230h+var_90]
0x18005a700  lea     eax, [r13-3]
0x18005a704  cmp     eax, 1
0x18005a707  jbe     short loc_18005A72E
0x18005a709  cmp     r9d, 200h
0x18005a710  jnb     short loc_18005A718
0x18005a712  test    r9b, 1
0x18005a716  jz      short loc_18005A745
0x18005a718  lea     r8, aNetpserverpass_0; "NetpServerPasswordSet: Decrypted passwo"...
0x18005a71f  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005a722  mov     ecx, ebx; unsigned int
0x18005a724  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005a729  jmp     loc_18005A945
0x18005a72e  cmp     r9d, 1F4h
0x18005a735  jnb     loc_18005A88E
0x18005a73b  test    r9b, 1
0x18005a73f  jnz     loc_18005A88E
0x18005a745  mov     ecx, r9d
0x18005a748  lea     rax, [rbp+230h+var_90]
0x18005a74f  sub     rax, rcx
0x18005a752  mov     word ptr [rbp+230h+var_2A8], r9w
0x18005a757  mov     qword ptr [rbp+230h+var_2A8+8], rax
0x18005a75b  xor     esi, esi
0x18005a75d  lea     eax, [r13-3]
0x18005a761  mov     word ptr [rbp+230h+var_2A8+2], r9w
0x18005a766  cmp     eax, 1
0x18005a769  ja      short loc_18005A7B4
0x18005a76b  lea     rax, [rbp+230h+var_9C]
0x18005a772  sub     rax, rcx
0x18005a775  cmp     dword ptr [rax+8], 2231968h
0x18005a77c  jnz     short loc_18005A7A0
0x18005a77e  mov     r9d, [rax+4]
0x18005a782  test    r9d, r9d
0x18005a785  jz      short loc_18005A7A0
0x18005a787  lea     r8, aNetpserverpass_10; "NetpServerPasswordSet: Got password ver"...
0x18005a78e  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005a791  mov     ecx, 200h; unsigned int
0x18005a796  mov     esi, r9d
0x18005a799  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005a79e  jmp     short loc_18005A7B4
0x18005a7a0  lea     r8, aNetpserverpass_7; "NetpServerPasswordSet: Got no password "...
0x18005a7a7  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005a7aa  mov     ecx, 200h; unsigned int
0x18005a7af  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005a7b4  lea     rdx, [rbp+230h+var_80]
0x18005a7bb  lea     rcx, [rbp+230h+var_2A8]
0x18005a7bf  call    cs:__imp_SystemFunction007
0x18005a7c6  nop     dword ptr [rax+rax+00h]
0x18005a7cb  test    eax, eax
0x18005a7cd  jns     short loc_18005A7F1
0x18005a7cf  mov     dword ptr [rsp+330h+var_308], eax
0x18005a7d3  lea     r8, aNetpserverpass_11; "NetpServerPasswordSet: Comp=%ws Acc=%ws"...
0x18005a7da  mov     r9, r12
0x18005a7dd  mov     [rsp+330h+var_310], r15
0x18005a7e2  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005a7e5  mov     ecx, ebx; unsigned int
0x18005a7e7  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005a7ec  jmp     loc_18005A945
0x18005a7f1  lea     rdx, [rbp+230h+var_80]
0x18005a7f8  lea     rcx, [rbp+230h+var_58]
0x18005a7ff  call    cs:__imp_SystemFunction031
0x18005a806  nop     dword ptr [rax+rax+00h]
0x18005a80b  test    al, al
0x18005a80d  jnz     loc_18005A914
0x18005a813  cmp     [rbp+230h+var_298], 0
0x18005a818  jnz     loc_18005A8F2
0x18005a81e  mov     r9, r12
0x18005a821  mov     [rsp+330h+var_310], r15
0x18005a826  lea     r8, aNetpserverpass_5; "NetpServerPasswordSet: Comp=%ws Acc=%ws"...
0x18005a82d  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005a830  mov     ecx, 200h; unsigned int
0x18005a835  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005a83a  xor     eax, eax
0x18005a83c  lea     rcx, [rbp+230h+var_80]
0x18005a843  test    r14, r14
0x18005a846  mov     r8d, r13d
0x18005a849  mov     rdx, r15
0x18005a84c  cmovnz  rcx, rax
0x18005a850  lea     rax, [rbp+230h+var_2A8]
0x18005a854  mov     [rsp+330h+var_308], rcx
0x18005a859  neg     r14
0x18005a85c  mov     rcx, rdi
0x18005a85f  mov     dword ptr [rsp+330h+var_310], esi
0x18005a863  sbb     r9, r9
0x18005a866  and     r9, rax
0x18005a869  call    ?NlSetIncomingPassword@@YAJPEAU_DOMAIN_INFO@@PEAGW4_NETLOGON_SECURE_CHANNEL_TYPE@@PEAU_UNICODE_STRING@@KPEAU_LM_OWF_PASSWORD@@@Z; NlSetIncomingPassword(_DOMAIN_INFO *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,_UNICODE_STRING *,ulong,_LM_OWF_PASSWORD *)
0x18005a86e  mov     ebx, eax
0x18005a870  test    eax, eax
0x18005a872  jns     loc_18005A930
0x18005a878  cmp     ebx, 0C0000022h
0x18005a87e  jnz     loc_18005A960
0x18005a884  mov     rsi, [rsp+330h+var_2C0]
0x18005a889  jmp     loc_18005A94F
0x18005a88e  lea     r8, aNetpserverpass_8; "NetpServerPasswordSet: Decrypted interd"...
0x18005a895  jmp     loc_18005A71F
0x18005a89a  mov     rax, [rbp+230h+var_298]
0x18005a89e  test    rax, rax
0x18005a8a1  jz      loc_18005A934
0x18005a8a7  cmp     dword ptr [r14+48h], 0
0x18005a8ac  jge     short loc_18005A8C9
0x18005a8ae  lea     r8, aNetpserverpass_3; "NetpServerPasswordSet: LMOWF was used w"...
0x18005a8b5  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005a8b8  mov     ecx, ebx; unsigned int
0x18005a8ba  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005a8bf  mov     ebx, 0C00000BBh
0x18005a8c4  jmp     loc_18005A960
0x18005a8c9  lea     r8, [rbp+230h+var_80]
0x18005a8d0  mov     rcx, rax
0x18005a8d3  lea     rdx, [rbp+230h+var_70]
0x18005a8da  call    cs:__imp_SystemFunction013
0x18005a8e1  nop     dword ptr [rax+rax+00h]
0x18005a8e6  mov     ebx, eax
0x18005a8e8  test    eax, eax
0x18005a8ea  jnz     short loc_18005A878
0x18005a8ec  mov     r14, [rbp+230h+var_2B0]
0x18005a8f0  xor     esi, esi
0x18005a8f2  lea     rdx, [rbp+230h+var_80]
0x18005a8f9  lea     rcx, [rbp+230h+var_58]
0x18005a900  call    cs:__imp_SystemFunction030
0x18005a907  nop     dword ptr [rax+rax+00h]
0x18005a90c  test    al, al
0x18005a90e  jz      loc_18005A81E
0x18005a914  mov     r9, r12
0x18005a917  mov     [rsp+330h+var_310], r15
0x18005a91c  lea     r8, aNetpserverpass_6; "NetpServerPasswordSet: Comp=%ws Ac=%ws "...
0x18005a923  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18005a926  mov     ecx, 200h; unsigned int
0x18005a92b  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
  ... truncated ...
```
