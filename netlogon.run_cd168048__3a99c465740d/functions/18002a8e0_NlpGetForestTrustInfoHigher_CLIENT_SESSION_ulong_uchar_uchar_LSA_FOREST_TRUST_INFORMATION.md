# NlpGetForestTrustInfoHigher(_CLIENT_SESSION *,ulong,uchar,uchar,_LSA_FOREST_TRUST_INFORMATION * *)

- ea: `0x18002a8e0`
- end: `0x18002ac9c`
- name: `?NlpGetForestTrustInfoHigher@@YAJPEAU_CLIENT_SESSION@@KEEPEAPEAU_LSA_FOREST_TRUST_INFORMATION@@@Z`
- size: `956`
- prototype: `__int64 __usercall@<rax>(struct _CLIENT_SESSION *@<rcx>, unsigned int@<edx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, struct _LSA_FOREST_TRUST_INFORMATION **)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x18002ada0`
- `0x180039ac4`
- `0x180073c20`

## callees

- `0x180007518`
- `0x18000dd00`
- `0x18000e910`
- `0x18002a8e0`
- `0x18002aca4`
- `0x180037344`
- `0x180040f18`
- `0x180040fe4`
- `0x180041924`
- `0x1800637d0`
- `0x180063c38`
- `0x180064c90`
- `0x180069c60`
- `0x18006d2b0`
- `0x18006d794`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002ac0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002ac0e`
- `logoncli!I_NetGetForestTrustInformation` at `0x18002aa98`
- `logoncli!I_NetGetForestTrustInformation` at `0x18002aa98`
- `ntdll!RtlLeaveCriticalSection` at `0x18002abfc`
- `ntdll!RtlLeaveCriticalSection` at `0x18002ac24`
- `ntdll!RtlLeaveCriticalSection` at `0x18002abfc`
- `ntdll!RtlLeaveCriticalSection` at `0x18002ac24`
- `ntdll!RtlEnterCriticalSection` at `0x18002abc2`
- `ntdll!RtlEnterCriticalSection` at `0x18002abc2`

## string_xrefs

- `0x18002a93f`: `onecore\ds\netapi\svcdlls\logonsrv\server\ftinfo.cxx`
- `0x18002a961`: `onecore\ds\netapi\svcdlls\logonsrv\server\ftinfo.cxx`
- `0x18002aa44`: `onecore\ds\netapi\svcdlls\logonsrv\server\ftinfo.cxx`
- `0x18002a968`: `ClientSession->CsFlags & CS_WRITER`
- `0x18002ab42`: `NlpDidDcFail: denying access after status: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NlpGetForestTrustInfoHigher(
        struct _CLIENT_SESSION *a1,
        char a2,
        char a3,
        char *a4,
        struct _LSA_FOREST_TRUST_INFORMATION **a5)
{
  char v5; // r15
  int v8; // ebp
  int started; // ebx
  char v10; // r14
  unsigned int v11; // r9d
  int v12; // eax
  DWORD i; // esi
  char *v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rdx
  int ForestTrustInformation; // eax
  unsigned __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v20; // r8
  char *v21; // r9
  __int64 v24; // [rsp+40h] [rbp-68h] BYREF
  int v25; // [rsp+48h] [rbp-60h]
  struct _CYPHER_BLOCK v26; // [rsp+50h] [rbp-58h] BYREF
  int v27; // [rsp+58h] [rbp-50h]

  v5 = (char)a4;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  if ( !*((_DWORD *)a1 + 82) )
    NlAssertFailed(
      "ClientSession->CsReferenceCount > 0",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ftinfo.cxx",
      0xC5u,
      a4);
  if ( (*((_BYTE *)a1 + 292) & 8) == 0 )
    NlAssertFailed(
      "ClientSession->CsFlags & CS_WRITER",
      "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ftinfo.cxx",
      0xC6u,
      a4);
  v8 = a2 & 1;
  if ( v8 && *(_DWORD *)(*((_QWORD *)a1 + 34) + 588LL) != 1 )
  {
    started = -1073741433;
LABEL_47:
    NlPrintCsRoutine(0x100u, a1, L"NlpGetForestTrustInfoHigher: failed %lX\n", (unsigned int)started);
    return (unsigned int)started;
  }
  if ( (*((_DWORD *)a1 + 74) & 8) == 0 )
  {
    NlPrintCsRoutine(0x100u, a1, L"NlpGetForestTrustInfoHigher: trust isn't marked as cross forest trust: 0x%lX\n");
    started = -1073741601;
    goto LABEL_47;
  }
  v10 = 1;
  if ( !v5 )
    goto LABEL_35;
  while ( 1 )
  {
    v11 = *((_DWORD *)a1 + 79);
    if ( (v11 & 0x80000) == 0 )
    {
      NlPrintCsRoutine(0x100u, a1, L"NlpGetForestTrustInfoHigher: remote DC doesn't support this function.\n");
      started = -1073741637;
      goto LABEL_47;
    }
    v12 = NlBuildAuthenticator(
            (struct _CYPHER_BLOCK *)a1 + 54,
            (struct _CLIENT_SESSION *)((char *)a1 + 440),
            (struct _NETLOGON_AUTHENTICATOR *)&v24,
            v11);
    started = v12;
    if ( v12 < 0 )
    {
      NlPrintRoutine(
        0x100u,
        L"NlpGetForestTrustInfoHigher: NlBuildAuthenticator failed with status: 0x%lx\n",
        (unsigned int)v12);
      goto LABEL_47;
    }
    started = -1073610748;
    for ( i = 0; i < 2; ++i )
    {
      started = NlStartApiClientSession(a1, 1, i, started, (struct _CLIENT_SESSION *)((char *)a1 + 680));
      if ( started >= 0 )
      {
        v15 = *((_QWORD *)a1 + 63);
        if ( !v15 )
        {
          NlAssertFailed(
            "ClientSession->CsUncServerName != NULL",
            "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\ftinfo.cxx",
            0x110u,
            v14);
          v15 = *((_QWORD *)a1 + 63);
        }
        if ( (*((_DWORD *)a1 + 73) & 0x40000) != 0 )
          v16 = *((_QWORD *)a1 + 27);
        else
          v16 = *(_QWORD *)(*((_QWORD *)a1 + 34) + 264LL);
        ForestTrustInformation = I_NetGetForestTrustInformation(v15, v16, &v24, &v26, 0, a5);
        started = ForestTrustInformation;
        if ( ForestTrustInformation < 0 )
          NlPrintRpcDebug("I_NetGetForestTrustInformation", ForestTrustInformation);
      }
      v18 = (unsigned int)(started + 1073610748);
      if ( (unsigned int)v18 > 0x32 )
        break;
      v19 = 0x4000000080001LL;
      if ( !_bittest64(&v19, v18) )
        break;
    }
    if ( !NlFinishApiClientSession(a1, 1, 1, (struct _CLIENT_SESSION *)((char *)a1 + 680)) && started >= 0 )
    {
      started = *((_DWORD *)a1 + 72);
      if ( started >= 0 )
        return (unsigned int)started;
      goto LABEL_47;
    }
    if ( !NlpDidDcFail(started)
      && (!(unsigned int)NlCheckRpcAuthIsNetlogon(a1)
       || (unsigned int)NlUpdateSeed((PUCHAR)a1 + 432, &v26, (PUCHAR)a1 + 440, *((_DWORD *)a1 + 79))) )
    {
      break;
    }
    NlPrintCsRoutine(0x100u, a1, L"NlpDidDcFail: denying access after status: 0x%lx\n", (unsigned int)started);
    if ( started >= 0 )
      started = -1073741790;
    NlSetStatusClientSession(a1, started, v20, v21);
    if ( !v10 )
      goto LABEL_47;
    if ( v5 )
      break;
    v10 = 0;
LABEL_35:
    started = NlEnsureSessionAuthenticated(a1, 0);
    if ( started < 0 )
      goto LABEL_47;
  }
  if ( started < 0 )
    goto LABEL_47;
  if ( v8 )
  {
    RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
    started = NlpUpdateFtinfo(*((struct _DOMAIN_INFO **)a1 + 34), *((unsigned __int16 **)a1 + 20), a3, *a5);
    if ( started < 0 )
    {
      RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
      goto LABEL_47;
    }
    GetSystemTimeAsFileTime((LPFILETIME)a1 + 6);
    RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(*((_QWORD *)a1 + 34) + 400LL));
  }
  return 0;
}

```

## disassembly

```asm
0x18002a8e0  mov     [rsp+arg_8], rbx
0x18002a8e5  push    rbp
0x18002a8e6  push    rsi
0x18002a8e7  push    rdi
0x18002a8e8  push    r12
0x18002a8ea  push    r13
0x18002a8ec  push    r14
0x18002a8ee  push    r15
0x18002a8f0  sub     rsp, 70h
0x18002a8f4  mov     rax, cs:__security_cookie
0x18002a8fb  xor     rax, rsp
0x18002a8fe  mov     [rsp+0A8h+var_48], rax
0x18002a903  mov     rax, [rsp+0A8h+arg_20]
0x18002a90b  mov     r15b, r9b
0x18002a90e  mov     [rsp+0A8h+var_70], rax
0x18002a913  mov     ebp, edx
0x18002a915  xor     eax, eax
0x18002a917  mov     [rsp+0A8h+var_78], r8b
0x18002a91c  mov     rdi, rcx
0x18002a91f  mov     [rsp+0A8h+var_68], rax
0x18002a924  mov     [rsp+0A8h+var_60], eax
0x18002a928  mov     qword ptr [rsp+0A8h+var_58.data], rax
0x18002a92d  mov     [rsp+0A8h+var_50], eax
0x18002a931  cmp     [rcx+148h], eax
0x18002a937  ja      short loc_18002A952
0x18002a939  mov     r8d, 0C5h; unsigned int
0x18002a93f  lea     rdx, aOnecoreDsNetap_5; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18002a946  lea     rcx, aClientsessionC_3; "ClientSession->CsReferenceCount > 0"
0x18002a94d  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18002a952  test    byte ptr [rdi+124h], 8
0x18002a959  jnz     short loc_18002A974
0x18002a95b  mov     r8d, 0C6h; unsigned int
0x18002a961  lea     rdx, aOnecoreDsNetap_5; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18002a968  lea     rcx, aClientsessionC_1; "ClientSession->CsFlags & CS_WRITER"
0x18002a96f  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18002a974  mov     esi, 100h
0x18002a979  and     ebp, 1
0x18002a97c  jz      short loc_18002A998
0x18002a97e  mov     rax, [rdi+110h]
0x18002a985  cmp     dword ptr [rax+24Ch], 1
0x18002a98c  jz      short loc_18002A998
0x18002a98e  mov     ebx, 0C0000187h
0x18002a993  jmp     loc_18002AC5D
0x18002a998  mov     r9d, [rdi+128h]
0x18002a99f  test    r9b, 8
0x18002a9a3  jnz     short loc_18002A9C0
0x18002a9a5  lea     r8, aNlpgetforesttr_2; "NlpGetForestTrustInfoHigher: trust isn'"...
0x18002a9ac  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18002a9af  mov     ecx, esi; unsigned int
0x18002a9b1  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18002a9b6  mov     ebx, 0C00000DFh
0x18002a9bb  jmp     loc_18002AC5D
0x18002a9c0  mov     r14b, 1
0x18002a9c3  test    r15b, r15b
0x18002a9c6  jz      loc_18002AB7B
0x18002a9cc  mov     r9d, [rdi+13Ch]; unsigned int
0x18002a9d3  bt      r9d, 13h
0x18002a9d8  jnb     loc_18002AC47
0x18002a9de  lea     rdx, [rdi+1B8h]; struct _NETLOGON_SESSION_KEY *
0x18002a9e5  lea     rcx, [rdi+1B0h]; struct _CYPHER_BLOCK *
0x18002a9ec  lea     r8, [rsp+0A8h+var_68]; struct _NETLOGON_AUTHENTICATOR *
0x18002a9f1  call    ?NlBuildAuthenticator@@YAJPEAU_CYPHER_BLOCK@@PEAU_NETLOGON_SESSION_KEY@@PEAU_NETLOGON_AUTHENTICATOR@@K@Z; NlBuildAuthenticator(_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,_NETLOGON_AUTHENTICATOR *,ulong)
0x18002a9f6  mov     ebx, eax
0x18002a9f8  test    eax, eax
0x18002a9fa  js      loc_18002AC34
0x18002aa00  mov     r12, [rsp+0A8h+var_70]
0x18002aa05  lea     r13, [rdi+2A8h]
0x18002aa0c  mov     ebx, 0C0020004h
0x18002aa11  xor     esi, esi
0x18002aa13  mov     r9d, ebx; int
0x18002aa16  mov     [rsp+0A8h+var_88], r13; struct _CLIENT_API *
0x18002aa1b  mov     r8d, esi; unsigned int
0x18002aa1e  mov     dl, 1; unsigned __int8
0x18002aa20  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18002aa23  call    ?NlStartApiClientSession@@YAJPEAU_CLIENT_SESSION@@EKJPEAU_CLIENT_API@@@Z; NlStartApiClientSession(_CLIENT_SESSION *,uchar,ulong,long,_CLIENT_API *)
0x18002aa28  mov     ebx, eax
0x18002aa2a  test    eax, eax
0x18002aa2c  js      loc_18002AAB8
0x18002aa32  mov     rcx, [rdi+1F8h]
0x18002aa39  test    rcx, rcx
0x18002aa3c  jnz     short loc_18002AA5E
0x18002aa3e  mov     r8d, 110h; unsigned int
0x18002aa44  lea     rdx, aOnecoreDsNetap_5; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x18002aa4b  lea     rcx, aClientsessionC_2; "ClientSession->CsUncServerName != NULL"
0x18002aa52  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x18002aa57  mov     rcx, [rdi+1F8h]
0x18002aa5e  test    dword ptr [rdi+124h], 40000h
0x18002aa68  jz      short loc_18002AA73
0x18002aa6a  mov     rdx, [rdi+0D8h]
0x18002aa71  jmp     short loc_18002AA81
0x18002aa73  mov     rax, [rdi+110h]
0x18002aa7a  mov     rdx, [rax+108h]
0x18002aa81  mov     [rsp+0A8h+var_80], r12
0x18002aa86  lea     r9, [rsp+0A8h+var_58]
0x18002aa8b  lea     r8, [rsp+0A8h+var_68]
0x18002aa90  mov     dword ptr [rsp+0A8h+var_88], 0
0x18002aa98  call    cs:__imp_I_NetGetForestTrustInformation
0x18002aa9f  nop     dword ptr [rax+rax+00h]
0x18002aaa4  mov     ebx, eax
0x18002aaa6  test    eax, eax
0x18002aaa8  jns     short loc_18002AAB8
0x18002aaaa  mov     edx, eax; int
0x18002aaac  lea     rcx, aINetgetforestt; "I_NetGetForestTrustInformation"
0x18002aab3  call    ?NlPrintRpcDebug@@YAXPEBDJ@Z; NlPrintRpcDebug(char const *,long)
0x18002aab8  lea     eax, [rbx+3FFDFFFCh]
0x18002aabe  cmp     eax, 32h ; '2'
0x18002aac1  ja      short loc_18002AADE
0x18002aac3  mov     rcx, 4000000080001h
0x18002aacd  bt      rcx, rax
0x18002aad1  jnb     short loc_18002AADE
0x18002aad3  inc     esi
0x18002aad5  cmp     esi, 2
0x18002aad8  jb      loc_18002AA13
0x18002aade  mov     r8b, 1; unsigned __int8
0x18002aae1  lea     r9, [rdi+2A8h]; struct _CLIENT_API *
0x18002aae8  mov     dl, r8b; unsigned __int8
0x18002aaeb  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18002aaee  call    ?NlFinishApiClientSession@@YAEPEAU_CLIENT_SESSION@@EEPEAU_CLIENT_API@@@Z; NlFinishApiClientSession(_CLIENT_SESSION *,uchar,uchar,_CLIENT_API *)
0x18002aaf3  test    al, al
0x18002aaf5  jnz     short loc_18002AAFF
0x18002aaf7  test    ebx, ebx
0x18002aaf9  jns     loc_18002AB94
0x18002aaff  mov     ecx, ebx; int
0x18002ab01  call    ?NlpDidDcFail@@YAEJ@Z; NlpDidDcFail(long)
0x18002ab06  test    al, al
0x18002ab08  jnz     short loc_18002AB3D
0x18002ab0a  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18002ab0d  call    ?NlCheckRpcAuthIsNetlogon@@YAHPEAU_CLIENT_SESSION@@@Z; NlCheckRpcAuthIsNetlogon(_CLIENT_SESSION *)
0x18002ab12  test    eax, eax
0x18002ab14  jz      loc_18002ABA7
0x18002ab1a  mov     r9d, [rdi+13Ch]; unsigned int
0x18002ab21  lea     r8, [rdi+1B8h]; pbSecret
0x18002ab28  lea     rdx, [rsp+0A8h+var_58]; struct _CYPHER_BLOCK *
0x18002ab2d  lea     rcx, [rdi+1B0h]; pbInput
0x18002ab34  call    ?NlUpdateSeed@@YAHPEAU_CYPHER_BLOCK@@0PEAU_NETLOGON_SESSION_KEY@@K@Z; NlUpdateSeed(_CYPHER_BLOCK *,_CYPHER_BLOCK *,_NETLOGON_SESSION_KEY *,ulong)
0x18002ab39  test    eax, eax
0x18002ab3b  jnz     short loc_18002ABA7
0x18002ab3d  mov     esi, 100h
0x18002ab42  lea     r8, aNlpdiddcfailDe; "NlpDidDcFail: denying access after stat"...
0x18002ab49  mov     ecx, esi; unsigned int
0x18002ab4b  mov     r9d, ebx
0x18002ab4e  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18002ab51  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18002ab56  mov     eax, 0C0000022h
0x18002ab5b  test    ebx, ebx
0x18002ab5d  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18002ab60  cmovns  ebx, eax
0x18002ab63  mov     edx, ebx; int
0x18002ab65  call    ?NlSetStatusClientSession@@YAXPEAU_CLIENT_SESSION@@J@Z; NlSetStatusClientSession(_CLIENT_SESSION *,long)
0x18002ab6a  test    r14b, r14b
0x18002ab6d  jz      loc_18002AC5D
0x18002ab73  test    r15b, r15b
0x18002ab76  jnz     short loc_18002ABA7
0x18002ab78  xor     r14b, r14b
0x18002ab7b  xor     edx, edx; unsigned int
0x18002ab7d  mov     rcx, rdi; struct _CLIENT_SESSION *
0x18002ab80  call    ?NlEnsureSessionAuthenticated@@YAJPEAU_CLIENT_SESSION@@K@Z; NlEnsureSessionAuthenticated(_CLIENT_SESSION *,ulong)
0x18002ab85  mov     ebx, eax
0x18002ab87  test    eax, eax
0x18002ab89  jns     loc_18002A9CC
0x18002ab8f  jmp     loc_18002AC5D
0x18002ab94  mov     ebx, [rdi+120h]
0x18002ab9a  test    ebx, ebx
0x18002ab9c  jns     loc_18002AC74
0x18002aba2  jmp     loc_18002AC5D
0x18002aba7  test    ebx, ebx
0x18002aba9  js      loc_18002AC5D
0x18002abaf  test    ebp, ebp
0x18002abb1  jz      short loc_18002AC30
0x18002abb3  mov     rcx, [rdi+110h]
0x18002abba  mov     esi, 190h
0x18002abbf  add     rcx, rsi; CriticalSection
0x18002abc2  call    cs:__imp_RtlEnterCriticalSection
0x18002abc9  nop     dword ptr [rax+rax+00h]
0x18002abce  mov     r8b, [rsp+0A8h+var_78]; unsigned __int8
0x18002abd3  mov     rax, r12
0x18002abd6  mov     rdx, [rdi+0A0h]; unsigned __int16 *
0x18002abdd  mov     rcx, [rdi+110h]; struct _DOMAIN_INFO *
0x18002abe4  mov     r9, [rax]; struct _LSA_FOREST_TRUST_INFORMATION *
0x18002abe7  call    ?NlpUpdateFtinfo@@YAJPEAU_DOMAIN_INFO@@PEAGEPEAU_LSA_FOREST_TRUST_INFORMATION@@@Z; NlpUpdateFtinfo(_DOMAIN_INFO *,ushort *,uchar,_LSA_FOREST_TRUST_INFORMATION *)
0x18002abec  mov     ebx, eax
0x18002abee  test    eax, eax
0x18002abf0  jns     short loc_18002AC0A
0x18002abf2  mov     rcx, [rdi+110h]
0x18002abf9  add     rcx, rsi; CriticalSection
0x18002abfc  call    cs:__imp_RtlLeaveCriticalSection
0x18002ac03  nop     dword ptr [rax+rax+00h]
0x18002ac08  jmp     short loc_18002AC5D
0x18002ac0a  lea     rcx, [rdi+30h]; lpSystemTimeAsFileTime
0x18002ac0e  call    cs:__imp_GetSystemTimeAsFileTime
0x18002ac15  nop     dword ptr [rax+rax+00h]
0x18002ac1a  mov     rcx, [rdi+110h]
0x18002ac21  add     rcx, rsi; CriticalSection
0x18002ac24  call    cs:__imp_RtlLeaveCriticalSection
0x18002ac2b  nop     dword ptr [rax+rax+00h]
0x18002ac30  xor     ebx, ebx
0x18002ac32  jmp     short loc_18002AC74
0x18002ac34  mov     r8d, eax
0x18002ac37  lea     rdx, aNlpgetforesttr; "NlpGetForestTrustInfoHigher: NlBuildAut"...
0x18002ac3e  mov     ecx, esi; unsigned int
0x18002ac40  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002ac45  jmp     short loc_18002AC5D
0x18002ac47  lea     r8, aNlpgetforesttr_0; "NlpGetForestTrustInfoHigher: remote DC "...
0x18002ac4e  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18002ac51  mov     ecx, esi; unsigned int
0x18002ac53  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18002ac58  mov     ebx, 0C00000BBh
0x18002ac5d  mov     r9d, ebx
0x18002ac60  lea     r8, aNlpgetforesttr_3; "NlpGetForestTrustInfoHigher: failed %lX"...
0x18002ac67  mov     rdx, rdi; struct _CLIENT_SESSION *
0x18002ac6a  mov     ecx, 100h; unsigned int
0x18002ac6f  call    ?NlPrintCsRoutine@@YAXKPEAU_CLIENT_SESSION@@PEAGZZ; NlPrintCsRoutine(ulong,_CLIENT_SESSION *,ushort *,...)
0x18002ac74  mov     eax, ebx
0x18002ac76  mov     rcx, [rsp+0A8h+var_48]
0x18002ac7b  xor     rcx, rsp; StackCookie
0x18002ac7e  call    __security_check_cookie
0x18002ac83  mov     rbx, [rsp+0A8h+arg_8]
0x18002ac8b  add     rsp, 70h
0x18002ac8f  pop     r15
0x18002ac91  pop     r14
0x18002ac93  pop     r13
0x18002ac95  pop     r12
0x18002ac97  pop     rdi
0x18002ac98  pop     rsi
0x18002ac99  pop     rbp
0x18002ac9a  retn
```
