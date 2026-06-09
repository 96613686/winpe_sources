# NetpServerPasswordSet(ushort *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,ushort *,_NETLOGON_AUTHENTICATOR *,_NETLOGON_AUTHENTICATOR *,_ENCRYPTED_LM_OWF_PASSWORD *,_NL_TRUST_PASSWORD *)

- ea: `0x180056644`
- end: `0x180056c16`
- name: `?NetpServerPasswordSet@@YAJPEAG0W4_NETLOGON_SECURE_CHANNEL_TYPE@@0PEAU_NETLOGON_AUTHENTICATOR@@2PEAU_ENCRYPTED_LM_OWF_PASSWORD@@PEAU_NL_TRUST_PASSWORD@@@Z`
- size: `1490`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned int, unsigned __int16 *, struct _NETLOGON_AUTHENTICATOR *, struct _NETLOGON_AUTHENTICATOR *, __int64, _OWORD *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005eda0`
- `0x18005ede0`

## callees

- `0x180007278`
- `0x18000bd98`
- `0x18000e270`
- `0x180025708`
- `0x18002601c`
- `0x1800354d8`
- `0x180038510`
- `0x18005378c`
- `0x180056644`
- `0x18005f524`
- `0x18005fa38`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800567ec`
- `ntdll!RtlLeaveCriticalSection` at `0x180056853`
- `ntdll!RtlLeaveCriticalSection` at `0x180056884`
- `ntdll!RtlLeaveCriticalSection` at `0x180056897`
- `ntdll!RtlLeaveCriticalSection` at `0x1800567ec`
- `ntdll!RtlLeaveCriticalSection` at `0x180056853`
- `ntdll!RtlLeaveCriticalSection` at `0x180056884`
- `ntdll!RtlLeaveCriticalSection` at `0x180056897`
- `ntdll!RtlEnterCriticalSection` at `0x1800567d0`
- `ntdll!RtlEnterCriticalSection` at `0x1800567d0`
- `CRYPTSP!SystemFunction007` at `0x1800569e5`
- `CRYPTSP!SystemFunction007` at `0x1800569e5`
- `CRYPTSP!SystemFunction030` at `0x180056b14`
- `CRYPTSP!SystemFunction030` at `0x180056b14`
- `CRYPTSP!SystemFunction031` at `0x180056a1f`
- `CRYPTSP!SystemFunction031` at `0x180056a1f`
- `CRYPTSP!SystemFunction013` at `0x180056af4`
- `CRYPTSP!SystemFunction013` at `0x180056af4`

## string_xrefs

- `0x180056712`: `NetpServerPasswordSet: Comp=%ws Acc=%ws Entered\n`
- `0x1800567a5`: `NetpServerPasswordSet: Comp=%ws Acc=%ws failed because NlGetIncomingPassword failed with ntstatus 0x%x\n`
- `0x180056808`: `%ws:%d attempts to set password for different account: %ws:%d\n`
- `0x1800569f3`: `NetpServerPasswordSet: Comp=%ws Acc=%ws failed because RtlCalculateNtOwfPassword failed with ntstatus 0x%x\n`
- `0x180056b2a`: `NetpServerPasswordSet: Comp=%ws Ac=%ws Not changing password -- already changed\n`
- `0x180056a40`: `NetpServerPasswordSet: Comp=%ws Acc=%ws Changing password locally\n`
- `0x180056bc8`: `NetpServerPasswordSet: Comp=%ws Acc=%ws returns 0x%lX\n`

## pseudocode

```c
__int64 __fastcall NetpServerPasswordSet(
        unsigned __int16 *a1,
        __int64 a2,
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
  int v43; // [rsp+78h] [rbp-88h] BYREF
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
  IncomingPassword = NlGetIncomingPassword(DomainByServerName, a2, a3, 0, 0, &v53, 0, &v43, 0, 0, 0, 0, 0);
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
  if ( dword_1800F1120 && a3 == 2 && (*((_DWORD *)v17 + 8) == 6 || (v52 & 0x100) != 0) )
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
0x180056644  push    rbp
0x180056646  push    rbx
0x180056647  push    rsi
0x180056648  push    rdi
0x180056649  push    r12
0x18005664b  push    r13
0x18005664d  push    r14
0x18005664f  push    r15
0x180056651  lea     rbp, [rsp-1F8h]
0x180056659  sub     rsp, 2F8h
0x180056660  mov     rax, cs:__security_cookie
0x180056667  xor     rax, rsp
0x18005666a  mov     [rbp+230h+var_48], rax
0x180056671  mov     rax, [rbp+230h+arg_30]
0x180056678  xorps   xmm0, xmm0
0x18005667b  mov     rsi, [rbp+230h+arg_28]
0x180056682  xorps   xmm1, xmm1
0x180056685  mov     rbx, [rbp+230h+arg_20]
0x18005668c  mov     r12, r9
0x18005668f  mov     [rbp+230h+var_298], rax
0x180056693  mov     r13d, r8d
0x180056696  mov     rax, [rbp+230h+arg_38]
0x18005669d  mov     r15, rdx
0x1800566a0  mov     [rbp+230h+var_2B0], rax
0x1800566a4  xor     eax, eax
0x1800566a6  cmp     cs:?NlGlobalMemberWorkstation@@3HA, eax; int NlGlobalMemberWorkstation
0x1800566ac  mov     [rsp+330h+var_2C0], rsi
0x1800566b1  movups  [rbp+230h+var_70], xmm0
0x1800566b8  mov     [rbp+230h+var_60], eax
0x1800566be  movups  [rbp+230h+var_80], xmm0
0x1800566c5  mov     [rsp+330h+var_2B8], eax
0x1800566c9  movups  [rbp+230h+var_2A8], xmm1
0x1800566cd  movups  [rbp+230h+var_58], xmm0
0x1800566d4  jz      short loc_1800566E0
0x1800566d6  mov     eax, 0C00000BBh
0x1800566db  jmp     loc_180056BF3
0x1800566e0  cmp     cs:?NlGlobalDsPaused@@3HA, eax; int NlGlobalDsPaused
0x1800566e6  jz      short loc_180056705
0x1800566e8  xor     edi, edi
0x1800566ea  lea     rdx, aNetpserverpass_9; "NetpServerPasswordSet: DsIsPaused.\n"
0x1800566f1  mov     ecx, 100h; unsigned int
0x1800566f6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800566fb  mov     ebx, 0C00002A5h
0x180056700  jmp     loc_180056B6E
0x180056705  call    ?NlFindDomainByServerName@@YAPEAU_DOMAIN_INFO@@PEAG@Z; NlFindDomainByServerName(ushort *)
0x18005670a  mov     r9, r12
0x18005670d  mov     [rsp+330h+var_310], r15
0x180056712  lea     r8, aNetpserverpass; "NetpServerPasswordSet: Comp=%ws Acc=%ws"...
0x180056719  mov     rdx, rax; struct _DOMAIN_INFO *
0x18005671c  mov     ecx, 200h; unsigned int
0x180056721  mov     rdi, rax
0x180056724  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180056729  test    rdi, rdi
0x18005672c  jnz     short loc_180056738
0x18005672e  mov     ebx, 0C0000122h
0x180056733  jmp     loc_180056B6E
0x180056738  mov     [rsp+330h+var_2D0], 0
0x180056741  lea     rax, [rsp+330h+var_2B8]
0x180056746  mov     [rsp+330h+var_2D8], 0
0x18005674f  xor     r9d, r9d
0x180056752  mov     [rsp+330h+var_2E0], 0
0x18005675b  mov     r8d, r13d
0x18005675e  mov     [rsp+330h+var_2E8], 0
0x180056767  mov     rdx, r15
0x18005676a  mov     [rsp+330h+var_2F0], 0
0x180056773  mov     rcx, rdi
0x180056776  mov     [rsp+330h+var_2F8], rax
0x18005677b  lea     rax, [rbp+230h+var_58]
0x180056782  mov     [rsp+330h+var_300], 0
0x18005678b  mov     [rsp+330h+var_308], rax
0x180056790  mov     dword ptr [rsp+330h+var_310], 0
0x180056798  call    ?NlGetIncomingPassword@@YAJPEAU_DOMAIN_INFO@@PEBGW4_NETLOGON_SECURE_CHANNEL_TYPE@@KHPEAU_LM_OWF_PASSWORD@@3PEAK44PEAPEAXPEAH4@Z; NlGetIncomingPassword(_DOMAIN_INFO *,ushort const *,_NETLOGON_SECURE_CHANNEL_TYPE,ulong,int,_LM_OWF_PASSWORD *,_LM_OWF_PASSWORD *,ulong *,ulong *,ulong *,void * *,int *,ulong *)
0x18005679d  test    eax, eax
0x18005679f  jns     short loc_1800567C6
0x1800567a1  mov     dword ptr [rsp+330h+var_308], eax
0x1800567a5  lea     r8, aNetpserverpass_1; "NetpServerPasswordSet: Comp=%ws Acc=%ws"...
0x1800567ac  mov     r9, r12
0x1800567af  mov     [rsp+330h+var_310], r15
0x1800567b4  mov     rdx, rdi; struct _DOMAIN_INFO *
0x1800567b7  mov     ecx, 100h; unsigned int
0x1800567bc  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800567c1  jmp     loc_180056B58
0x1800567c6  lea     rsi, [rdi+1F8h]
0x1800567cd  mov     rcx, rsi; CriticalSection
0x1800567d0  call    cs:__imp_RtlEnterCriticalSection
0x1800567d6  mov     rdx, r12; unsigned __int16 *
0x1800567d9  mov     rcx, rdi; struct _DOMAIN_INFO *
0x1800567dc  call    ?NlFindNamedServerSession@@YAPEAU_SERVER_SESSION@@PEAU_DOMAIN_INFO@@PEAG@Z; NlFindNamedServerSession(_DOMAIN_INFO *,ushort *)
0x1800567e1  mov     r14, rax
0x1800567e4  test    rax, rax
0x1800567e7  jnz     short loc_1800567F7
0x1800567e9  mov     rcx, rsi; CriticalSection
0x1800567ec  call    cs:__imp_RtlLeaveCriticalSection
0x1800567f2  jmp     loc_180056B53
0x1800567f7  mov     r9d, [rax+34h]
0x1800567fb  mov     eax, [rsp+330h+var_2B8]
0x1800567ff  cmp     r9d, eax
0x180056802  jz      short loc_180056823
0x180056804  mov     dword ptr [rsp+330h+var_308], eax
0x180056808  lea     rdx, aWsDAttemptsToS; "%ws:%d attempts to set password for dif"...
0x18005680f  mov     r8, r12
0x180056812  mov     [rsp+330h+var_310], r15
0x180056817  mov     ecx, 100h; unsigned int
0x18005681c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180056821  jmp     short loc_1800567E9
0x180056823  movups  xmm0, xmmword ptr [r14+60h]
0x180056828  mov     r8, [rsp+330h+var_2C0]; struct _NETLOGON_AUTHENTICATOR *
0x18005682d  mov     rdx, rbx; struct _NETLOGON_AUTHENTICATOR *
0x180056830  mov     rcx, r14; struct _SERVER_SESSION *
0x180056833  movdqu  [rbp+230h+var_70], xmm0
0x18005683b  mov     eax, [r14+48h]
0x18005683f  mov     [rbp+230h+var_60], eax
0x180056845  call    ?NlCheckAuthenticator@@YAJPEAU_SERVER_SESSION@@PEAU_NETLOGON_AUTHENTICATOR@@1@Z; NlCheckAuthenticator(_SERVER_SESSION *,_NETLOGON_AUTHENTICATOR *,_NETLOGON_AUTHENTICATOR *)
0x18005684a  mov     ebx, eax
0x18005684c  test    eax, eax
0x18005684e  jns     short loc_18005685E
0x180056850  mov     rcx, rsi; CriticalSection
0x180056853  call    cs:__imp_RtlLeaveCriticalSection
0x180056859  jmp     loc_180056A92
0x18005685e  cmp     cs:dword_1800F1120, 0
0x180056865  mov     ebx, 100h
0x18005686a  jz      short loc_180056894
0x18005686c  cmp     r13d, 2
0x180056870  jnz     short loc_180056894
0x180056872  cmp     dword ptr [r14+20h], 6
0x180056877  jz      short loc_180056881
0x180056879  test    [rbp+230h+var_60], ebx
0x18005687f  jz      short loc_180056894
0x180056881  mov     rcx, rsi; CriticalSection
0x180056884  call    cs:__imp_RtlLeaveCriticalSection
0x18005688a  mov     ebx, 0C000006Ah
0x18005688f  jmp     loc_180056B6E
0x180056894  mov     rcx, rsi; CriticalSection
0x180056897  call    cs:__imp_RtlLeaveCriticalSection
0x18005689d  cmp     [rbp+230h+var_2B0], 0
0x1800568a2  jz      loc_180056AB4
0x1800568a8  mov     r14, [rbp+230h+var_2B0]
0x1800568ac  lea     rcx, [rbp+230h+var_290]
0x1800568b0  mov     edx, 4
0x1800568b5  mov     rax, r14
0x1800568b8  lea     r8d, [rdx+7Ch]
0x1800568bc  movups  xmm0, xmmword ptr [rax]
0x1800568bf  movups  xmm1, xmmword ptr [rax+10h]
0x1800568c3  movups  xmmword ptr [rcx], xmm0
0x1800568c6  movups  xmm0, xmmword ptr [rax+20h]
0x1800568ca  movups  xmmword ptr [rcx+10h], xmm1
0x1800568ce  movups  xmm1, xmmword ptr [rax+30h]
0x1800568d2  movups  xmmword ptr [rcx+20h], xmm0
0x1800568d6  movups  xmm0, xmmword ptr [rax+40h]
0x1800568da  movups  xmmword ptr [rcx+30h], xmm1
0x1800568de  movups  xmm1, xmmword ptr [rax+50h]
0x1800568e2  movups  xmmword ptr [rcx+40h], xmm0
0x1800568e6  movups  xmm0, xmmword ptr [rax+60h]
0x1800568ea  movups  xmmword ptr [rcx+50h], xmm1
0x1800568ee  movups  xmm1, xmmword ptr [rax+70h]
0x1800568f2  add     rax, r8
0x1800568f5  movups  xmmword ptr [rcx+60h], xmm0
0x1800568f9  movups  xmmword ptr [rcx+70h], xmm1
0x1800568fd  add     rcx, r8
0x180056900  sub     rdx, 1
0x180056904  jnz     short loc_1800568BC
0x180056906  mov     eax, [rax]
0x180056908  lea     r8, [rbp+230h+var_70]; struct _SESSION_INFO *
0x18005690f  mov     [rcx], eax
0x180056911  mov     edx, 204h; unsigned int
0x180056916  lea     rcx, [rbp+230h+var_290]; void *
0x18005691a  call    ?NlDecrypt@@YAXPEAXKPEAU_SESSION_INFO@@@Z; NlDecrypt(void *,ulong,_SESSION_INFO *)
0x18005691f  mov     r9d, [rbp+230h+var_90]
0x180056926  lea     eax, [r13-3]
0x18005692a  cmp     eax, 1
0x18005692d  jbe     short loc_180056954
0x18005692f  cmp     r9d, 200h
0x180056936  jnb     short loc_18005693E
0x180056938  test    r9b, 1
0x18005693c  jz      short loc_18005696B
0x18005693e  lea     r8, aNetpserverpass_0; "NetpServerPasswordSet: Decrypted passwo"...
0x180056945  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180056948  mov     ecx, ebx; unsigned int
0x18005694a  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x18005694f  jmp     loc_180056B53
0x180056954  cmp     r9d, 1F4h
0x18005695b  jnb     loc_180056AA8
0x180056961  test    r9b, 1
0x180056965  jnz     loc_180056AA8
0x18005696b  mov     ecx, r9d
0x18005696e  lea     rax, [rbp+230h+var_90]
0x180056975  sub     rax, rcx
0x180056978  mov     word ptr [rbp+230h+var_2A8], r9w
0x18005697d  mov     qword ptr [rbp+230h+var_2A8+8], rax
0x180056981  xor     esi, esi
0x180056983  lea     eax, [r13-3]
0x180056987  mov     word ptr [rbp+230h+var_2A8+2], r9w
0x18005698c  cmp     eax, 1
0x18005698f  ja      short loc_1800569DA
0x180056991  lea     rax, [rbp+230h+var_9C]
0x180056998  sub     rax, rcx
0x18005699b  cmp     dword ptr [rax+8], 2231968h
0x1800569a2  jnz     short loc_1800569C6
0x1800569a4  mov     r9d, [rax+4]
0x1800569a8  test    r9d, r9d
0x1800569ab  jz      short loc_1800569C6
0x1800569ad  lea     r8, aNetpserverpass_10; "NetpServerPasswordSet: Got password ver"...
0x1800569b4  mov     rdx, rdi; struct _DOMAIN_INFO *
0x1800569b7  mov     ecx, 200h; unsigned int
0x1800569bc  mov     esi, r9d
0x1800569bf  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800569c4  jmp     short loc_1800569DA
0x1800569c6  lea     r8, aNetpserverpass_7; "NetpServerPasswordSet: Got no password "...
0x1800569cd  mov     rdx, rdi; struct _DOMAIN_INFO *
0x1800569d0  mov     ecx, 200h; unsigned int
0x1800569d5  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x1800569da  lea     rdx, [rbp+230h+var_80]
0x1800569e1  lea     rcx, [rbp+230h+var_2A8]
0x1800569e5  call    cs:__imp_SystemFunction007
0x1800569eb  test    eax, eax
0x1800569ed  jns     short loc_180056A11
0x1800569ef  mov     dword ptr [rsp+330h+var_308], eax
0x1800569f3  lea     r8, aNetpserverpass_11; "NetpServerPasswordSet: Comp=%ws Acc=%ws"...
0x1800569fa  mov     r9, r12
0x1800569fd  mov     [rsp+330h+var_310], r15
0x180056a02  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180056a05  mov     ecx, ebx; unsigned int
0x180056a07  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180056a0c  jmp     loc_180056B53
0x180056a11  lea     rdx, [rbp+230h+var_80]
0x180056a18  lea     rcx, [rbp+230h+var_58]
0x180056a1f  call    cs:__imp_SystemFunction031
0x180056a25  test    al, al
0x180056a27  jnz     loc_180056B22
0x180056a2d  cmp     [rbp+230h+var_298], 0
0x180056a32  jnz     loc_180056B06
0x180056a38  mov     r9, r12
0x180056a3b  mov     [rsp+330h+var_310], r15
0x180056a40  lea     r8, aNetpserverpass_5; "NetpServerPasswordSet: Comp=%ws Acc=%ws"...
0x180056a47  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180056a4a  mov     ecx, 200h; unsigned int
0x180056a4f  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180056a54  xor     eax, eax
0x180056a56  lea     rcx, [rbp+230h+var_80]
0x180056a5d  test    r14, r14
0x180056a60  mov     r8d, r13d
0x180056a63  mov     rdx, r15
0x180056a66  cmovnz  rcx, rax
0x180056a6a  lea     rax, [rbp+230h+var_2A8]
0x180056a6e  mov     [rsp+330h+var_308], rcx
0x180056a73  neg     r14
0x180056a76  mov     rcx, rdi
0x180056a79  mov     dword ptr [rsp+330h+var_310], esi
0x180056a7d  sbb     r9, r9
0x180056a80  and     r9, rax
0x180056a83  call    ?NlSetIncomingPassword@@YAJPEAU_DOMAIN_INFO@@PEAGW4_NETLOGON_SECURE_CHANNEL_TYPE@@PEAU_UNICODE_STRING@@KPEAU_LM_OWF_PASSWORD@@@Z; NlSetIncomingPassword(_DOMAIN_INFO *,ushort *,_NETLOGON_SECURE_CHANNEL_TYPE,_UNICODE_STRING *,ulong,_LM_OWF_PASSWORD *)
0x180056a88  mov     ebx, eax
0x180056a8a  test    eax, eax
0x180056a8c  jns     loc_180056B3E
0x180056a92  cmp     ebx, 0C0000022h
0x180056a98  jnz     loc_180056B6E
0x180056a9e  mov     rsi, [rsp+330h+var_2C0]
0x180056aa3  jmp     loc_180056B5D
0x180056aa8  lea     r8, aNetpserverpass_8; "NetpServerPasswordSet: Decrypted interd"...
0x180056aaf  jmp     loc_180056945
0x180056ab4  mov     rax, [rbp+230h+var_298]
0x180056ab8  test    rax, rax
0x180056abb  jz      loc_180056B42
0x180056ac1  cmp     dword ptr [r14+48h], 0
0x180056ac6  jge     short loc_180056AE3
0x180056ac8  lea     r8, aNetpserverpass_3; "NetpServerPasswordSet: LMOWF was used w"...
0x180056acf  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180056ad2  mov     ecx, ebx; unsigned int
0x180056ad4  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180056ad9  mov     ebx, 0C00000BBh
0x180056ade  jmp     loc_180056B6E
0x180056ae3  lea     r8, [rbp+230h+var_80]
0x180056aea  mov     rcx, rax
0x180056aed  lea     rdx, [rbp+230h+var_70]
0x180056af4  call    cs:__imp_SystemFunction013
0x180056afa  mov     ebx, eax
0x180056afc  test    eax, eax
0x180056afe  jnz     short loc_180056A92
0x180056b00  mov     r14, [rbp+230h+var_2B0]
0x180056b04  xor     esi, esi
0x180056b06  lea     rdx, [rbp+230h+var_80]
0x180056b0d  lea     rcx, [rbp+230h+var_58]
0x180056b14  call    cs:__imp_SystemFunction030
0x180056b1a  test    al, al
0x180056b1c  jz      loc_180056A38
0x180056b22  mov     r9, r12
0x180056b25  mov     [rsp+330h+var_310], r15
0x180056b2a  lea     r8, aNetpserverpass_6; "NetpServerPasswordSet: Comp=%ws Ac=%ws "...
0x180056b31  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180056b34  mov     ecx, 200h; unsigned int
0x180056b39  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180056b3e  xor     ebx, ebx
0x180056b40  jmp     short loc_180056B6E
0x180056b42  lea     r8, aNetpserverpass_2; "NetpServerPasswordSet: Neither clear no"...
0x180056b49  mov     rdx, rdi; struct _DOMAIN_INFO *
0x180056b4c  mov     ecx, ebx; unsigned int
0x180056b4e  call    ?NlPrintDomRoutine@@YAXKPEAU_DOMAIN_INFO@@PEAGZZ; NlPrintDomRoutine(ulong,_DOMAIN_INFO *,ushort *,...)
0x180056b53  mov     rsi, [rsp+330h+var_2C0]
0x180056b58  mov     ebx, 0C0000022h
0x180056b5d  mov     eax, 0Ch
  ... truncated ...
```
