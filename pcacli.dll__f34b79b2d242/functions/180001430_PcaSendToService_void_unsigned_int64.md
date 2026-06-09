# PcaSendToService(void *,unsigned __int64)

- ea: `0x180001430`
- end: `0x180001862`
- name: `?PcaSendToService@@YAKPEAX_K@Z`
- size: `1074`
- prototype: `unsigned int __fastcall(void *, unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001430`
- `0x180001870`
- `0x180002ee8`
- `0x180007738`
- `0x18000c030`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800014bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000150a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800014bc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000150a`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800016f4`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800016f4`
- `RPCRT4!RpcStringFreeW` at `0x180001668`
- `RPCRT4!RpcStringFreeW` at `0x180001668`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180001754`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180001754`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000c17e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000c17e`
- `RPCRT4!RpcStringBindingComposeW` at `0x180001696`
- `RPCRT4!RpcStringBindingComposeW` at `0x180001696`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800016b0`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800016b0`
- `RPCRT4!RpcBindingSetOption` at `0x1800016d0`
- `RPCRT4!RpcBindingSetOption` at `0x1800016d0`
- `RPCRT4!RpcBindingFree` at `0x180001847`
- `RPCRT4!RpcBindingFree` at `0x180001857`
- `RPCRT4!RpcBindingFree` at `0x180001847`
- `RPCRT4!RpcBindingFree` at `0x180001857`
- `RPCRT4!NdrClientCall3` at `0x1800015cf`
- `RPCRT4!NdrClientCall3` at `0x1800015cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001816`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001816`

## string_xrefs

- `0x1800014ae`: `Software\Policies\Microsoft\Windows\AppCompat`
- `0x1800014fc`: `Software\Policies\Microsoft\Windows\AppCompat`
- `0x1800017db`: `PcaClient`
- `0x1800017ae`: `PcapCreateBindingHandle`
- `0x18000179d`: `RpcStringBindingCompose failed [%d]`
- `0x18000181e`: `Failed to create sid [%d]`
- `0x1800017cf`: `SendToService ignored,PCA disabled`

## pseudocode

```c
__int64 __fastcall PcaSendToService(void *a1, __int64 a2)
{
  int v2; // r12d
  unsigned int v4; // r14d
  __int64 v5; // rsi
  unsigned int started; // ebx
  __int64 v7; // r13
  unsigned __int64 v9; // rax
  DWORD LastError; // eax
  const char *v11; // r9
  __int64 v12; // r8
  LPDWORD pdwType; // [rsp+20h] [rbp-108h]
  PVOID pvData; // [rsp+28h] [rbp-100h]
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-E8h] BYREF
  DWORD cbSid; // [rsp+48h] [rbp-E0h] BYREF
  unsigned int v17; // [rsp+4Ch] [rbp-DCh]
  RPC_WSTR String; // [rsp+50h] [rbp-D8h] BYREF
  __int64 v19; // [rsp+58h] [rbp-D0h]
  CLIENT_CALL_RETURN v20; // [rsp+60h] [rbp-C8h]
  void *v21; // [rsp+68h] [rbp-C0h]
  __int64 v22; // [rsp+70h] [rbp-B8h]
  RPC_SECURITY_QOS SecurityQOS; // [rsp+78h] [rbp-B0h] BYREF
  __int128 v24; // [rsp+88h] [rbp-A0h]
  _OWORD *v25; // [rsp+98h] [rbp-90h]
  _OWORD pSid[4]; // [rsp+A0h] [rbp-88h] BYREF
  int v27; // [rsp+E0h] [rbp-48h]

  v2 = a2;
  v21 = a1;
  v22 = a2;
  v4 = 0;
  v17 = 0;
  v5 = 0;
  v19 = 0;
  cbSid = 4;
  LODWORD(Binding) = 0;
  if ( RegGetValueW(
         HKEY_CURRENT_USER,
         L"Software\\Policies\\Microsoft\\Windows\\AppCompat",
         L"DisablePca",
         0x18u,
         0,
         &Binding,
         &cbSid)
    || (_DWORD)Binding != 1 )
  {
    cbSid = 4;
    LODWORD(Binding) = 0;
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Policies\\Microsoft\\Windows\\AppCompat",
           L"DisablePca",
           0x18u,
           0,
           &Binding,
           &cbSid)
      || (_DWORD)Binding != 1 )
    {
      String = 0;
      Binding = 0;
      memset(pSid, 0, sizeof(pSid));
      v27 = 0;
      cbSid = 68;
      SecurityQOS = 0;
      v24 = 0;
      v25 = 0;
      if ( qword_1800147E0 )
      {
        v5 = qword_1800147E0;
        v19 = qword_1800147E0;
LABEL_5:
        started = 0;
        goto LABEL_6;
      }
      LastError = RpcStringBindingComposeW(
                    (RPC_WSTR)L"0767A036-0D22-48aa-BA69-B619480F38CB",
                    (RPC_WSTR)L"ncalrpc",
                    0,
                    0,
                    0,
                    &String);
      started = LastError;
      if ( LastError )
      {
        v11 = "RpcStringBindingCompose failed [%d]";
        v12 = 402;
      }
      else
      {
        LastError = RpcBindingFromStringBindingW(String, &Binding);
        started = LastError;
        if ( LastError )
        {
          v11 = "RpcBindingFromStringBinding failed [%d]";
          v12 = 409;
        }
        else
        {
          LastError = RpcBindingSetOption(Binding, 0xCu, 0xC8u);
          started = LastError;
          if ( LastError )
          {
            v11 = "RpcBindingSetOption failed [%d]";
            v12 = 418;
          }
          else if ( CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
          {
            SecurityQOS.Version = 3;
            *(_QWORD *)&SecurityQOS.Capabilities = 1;
            SecurityQOS.ImpersonationType = 3;
            v25 = pSid;
            LastError = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
            started = LastError;
            if ( !LastError )
            {
              if ( _InterlockedCompareExchange64(&qword_1800147E0, (signed __int64)Binding, 0) )
                RpcBindingFree(&Binding);
              Binding = 0;
              v5 = qword_1800147E0;
              v19 = qword_1800147E0;
              goto LABEL_5;
            }
            v11 = "RpcBindingSetAuthInfoEx failed [%d]";
            v12 = 455;
          }
          else
          {
            LastError = GetLastError();
            started = LastError;
            v11 = "Failed to create sid [%d]";
            v12 = 431;
          }
        }
      }
      LODWORD(pdwType) = LastError;
      AslLogCallPrintf(1, "PcapCreateBindingHandle", v12, v11, pdwType);
LABEL_6:
      if ( String )
        RpcStringFreeW(&String);
      if ( Binding )
        RpcBindingFree(&Binding);
      v7 = 0x200000004201LL;
      if ( started )
        goto LABEL_14;
      goto LABEL_11;
    }
  }
  PcaTracePrintf("PcaClient", 0, 0, "SendToService ignored,PCA disabled");
  started = 0;
  v7 = 0x200000004201LL;
  while ( started )
  {
LABEL_14:
    if ( v4 > 1 )
      return started;
    v9 = started - 1708;
    if ( (unsigned int)v9 > 0x2D || !_bittest64(&v7, v9) )
      return started;
    started = PcacpStartPCAService();
    v17 = ++v4;
    if ( !started )
    {
LABEL_11:
      v20.Simple = 0;
      LODWORD(pvData) = v2;
      v20.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, v5, a1, pvData).Pointer;
    }
  }
  return started;
}

```

## disassembly

```asm
0x180001430  mov     [rsp+arg_10], rbx
0x180001435  mov     [rsp+arg_18], rsi
0x18000143a  push    rdi
0x18000143b  push    r12
0x18000143d  push    r13
0x18000143f  push    r14
0x180001441  push    r15
0x180001443  sub     rsp, 100h
0x18000144a  mov     rax, cs:__security_cookie
0x180001451  xor     rax, rsp
0x180001454  mov     [rsp+128h+var_38], rax
0x18000145c  mov     r12, rdx
0x18000145f  mov     r15, rcx
0x180001462  mov     [rsp+128h+var_C0], rcx
0x180001467  mov     [rsp+128h+var_B8], rdx
0x18000146c  xor     edi, edi
0x18000146e  mov     r14d, edi
0x180001471  mov     [rsp+128h+var_DC], edi
0x180001475  mov     esi, edi
0x180001477  mov     [rsp+128h+var_D0], rdi
0x18000147c  mov     [rsp+128h+cbSid], 4
0x180001484  mov     dword ptr [rsp+128h+Binding], edi
0x180001488  lea     rax, [rsp+128h+cbSid]
0x18000148d  mov     [rsp+128h+pcbData], rax; pcbData
0x180001492  lea     rax, [rsp+128h+Binding]
0x180001497  mov     [rsp+128h+pvData], rax; pvData
0x18000149c  mov     [rsp+128h+pdwType], rdi; pdwType
0x1800014a1  mov     r9d, 18h; dwFlags
0x1800014a7  lea     r8, Value; "DisablePca"
0x1800014ae  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x1800014b5  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1800014bc  call    cs:__imp_RegGetValueW
0x1800014c2  test    eax, eax
0x1800014c4  jz      loc_180001790
0x1800014ca  mov     [rsp+128h+cbSid], 4
0x1800014d2  mov     dword ptr [rsp+128h+Binding], edi
0x1800014d6  lea     rax, [rsp+128h+cbSid]
0x1800014db  mov     [rsp+128h+pcbData], rax; pcbData
0x1800014e0  lea     rax, [rsp+128h+Binding]
0x1800014e5  mov     [rsp+128h+pvData], rax; pvData
0x1800014ea  mov     [rsp+128h+pdwType], rdi; pdwType
0x1800014ef  mov     r9d, 18h; dwFlags
0x1800014f5  lea     r8, Value; "DisablePca"
0x1800014fc  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Windows"...
0x180001503  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000150a  call    cs:__imp_RegGetValueW
0x180001510  test    eax, eax
0x180001512  jz      loc_1800017C4
0x180001518  mov     [rsp+128h+String], rdi
0x18000151d  mov     [rsp+128h+Binding], rdi
0x180001522  xorps   xmm0, xmm0
0x180001525  xor     eax, eax
0x180001527  movups  [rsp+128h+pSid], xmm0
0x18000152f  movups  [rsp+128h+var_78], xmm0
0x180001537  movups  [rsp+128h+var_68], xmm0
0x18000153f  movups  [rsp+128h+var_58], xmm0
0x180001547  mov     [rsp+128h+var_48], eax
0x18000154e  mov     [rsp+128h+cbSid], 44h ; 'D'
0x180001556  movups  xmmword ptr [rsp+128h+SecurityQOS.Version], xmm0
0x18000155b  movups  [rsp+128h+var_A0], xmm0
0x180001563  mov     [rsp+128h+var_90], rax
0x18000156b  mov     rax, cs:qword_1800147E0
0x180001572  test    rax, rax
0x180001575  jz      loc_180001673
0x18000157b  mov     rsi, rax
0x18000157e  mov     [rsp+128h+var_D0], rax
0x180001583  mov     ebx, edi
0x180001585  cmp     [rsp+128h+String], rdi
0x18000158a  jnz     loc_180001663
0x180001590  cmp     [rsp+128h+Binding], rdi
0x180001595  jnz     loc_180001852
0x18000159b  mov     r13, 200000004201h
0x1800015a5  test    ebx, ebx
0x1800015a7  jnz     loc_180001633
0x1800015ad  nop
0x1800015ae  mov     [rsp+128h+var_C8], rdi
0x1800015b3  mov     dword ptr [rsp+128h+pvData], r12d
0x1800015b8  mov     [rsp+128h+pdwType], r15
0x1800015bd  mov     r9, rsi
0x1800015c0  xor     r8d, r8d; pReturnValue
0x1800015c3  mov     edx, 1; nProcNum
0x1800015c8  lea     rcx, pProxyInfo; pProxyInfo
0x1800015cf  call    cs:__imp_NdrClientCall3
0x1800015d5  mov     [rsp+128h+var_C8], rax
0x1800015da  jmp     short loc_180001600
0x1800015dc  mov     ebx, eax
0x1800015de  xor     edi, edi
0x1800015e0  mov     r13, 200000004201h
0x1800015ea  mov     r14d, [rsp+128h+var_DC]
0x1800015ef  mov     rsi, [rsp+128h+var_D0]
0x1800015f4  mov     r15, [rsp+128h+var_C0]
0x1800015f9  mov     r12, [rsp+128h+var_B8]
0x1800015fe  xchg    ax, ax
0x180001600  test    ebx, ebx
0x180001602  jnz     short loc_180001633
0x180001604  mov     eax, ebx
0x180001606  mov     rcx, [rsp+128h+var_38]
0x18000160e  xor     rcx, rsp; StackCookie
0x180001611  call    __security_check_cookie
0x180001616  lea     r11, [rsp+128h+var_28]
0x18000161e  mov     rbx, [r11+40h]
0x180001622  mov     rsi, [r11+48h]
0x180001626  mov     rsp, r11
0x180001629  pop     r15
0x18000162b  pop     r14
0x18000162d  pop     r13
0x18000162f  pop     r12
0x180001631  pop     rdi
0x180001632  retn
0x180001633  cmp     r14d, 1
0x180001637  ja      short loc_180001604
0x180001639  lea     eax, [rbx-6ACh]
0x18000163f  cmp     eax, 2Dh ; '-'
0x180001642  ja      short loc_180001604
0x180001644  bt      r13, rax
0x180001648  jnb     short loc_180001604
0x18000164a  call    ?PcacpStartPCAService@@YAKXZ; PcacpStartPCAService(void)
0x18000164f  mov     ebx, eax
0x180001651  inc     r14d
0x180001654  mov     [rsp+128h+var_DC], r14d
0x180001659  test    eax, eax
0x18000165b  jz      loc_1800015AD
0x180001661  jmp     short loc_180001600
0x180001663  lea     rcx, [rsp+128h+String]; String
0x180001668  call    cs:__imp_RpcStringFreeW
0x18000166e  jmp     loc_180001590
0x180001673  lea     rax, [rsp+128h+String]
0x180001678  mov     [rsp+128h+pvData], rax; StringBinding
0x18000167d  mov     [rsp+128h+pdwType], rdi; Options
0x180001682  xor     r9d, r9d; Endpoint
0x180001685  xor     r8d, r8d; NetworkAddr
0x180001688  lea     rdx, ProtSeq; "ncalrpc"
0x18000168f  lea     rcx, ObjUuid; "0767A036-0D22-48aa-BA69-B619480F38CB"
0x180001696  call    cs:__imp_RpcStringBindingComposeW
0x18000169c  mov     ebx, eax
0x18000169e  test    eax, eax
0x1800016a0  jnz     loc_18000179D
0x1800016a6  lea     rdx, [rsp+128h+Binding]; Binding
0x1800016ab  mov     rcx, [rsp+128h+String]; StringBinding
0x1800016b0  call    cs:__imp_RpcBindingFromStringBindingW
0x1800016b6  mov     ebx, eax
0x1800016b8  test    eax, eax
0x1800016ba  jnz     loc_1800017F8
0x1800016c0  mov     edx, 0Ch; option
0x1800016c5  mov     r8d, 0C8h; optionValue
0x1800016cb  mov     rcx, [rsp+128h+Binding]; hBinding
0x1800016d0  call    cs:__imp_RpcBindingSetOption
0x1800016d6  mov     ebx, eax
0x1800016d8  test    eax, eax
0x1800016da  jnz     loc_180001807
0x1800016e0  lea     r9, [rsp+128h+cbSid]; cbSid
0x1800016e5  lea     r8, [rsp+128h+pSid]; pSid
0x1800016ed  xor     edx, edx; DomainSid
0x1800016ef  mov     ecx, 16h; WellKnownSidType
0x1800016f4  call    cs:__imp_CreateWellKnownSid
0x1800016fa  test    eax, eax
0x1800016fc  jz      loc_180001816
0x180001702  mov     [rsp+128h+SecurityQOS.Version], 3
0x18000170a  mov     qword ptr [rsp+128h+SecurityQOS.Capabilities], 1
0x180001713  mov     [rsp+128h+SecurityQOS.ImpersonationType], 3
0x18000171e  lea     rax, [rsp+128h+pSid]
0x180001726  mov     [rsp+128h+var_90], rax
0x18000172e  lea     rax, [rsp+128h+SecurityQOS]
0x180001733  mov     [rsp+128h+pcbData], rax; SecurityQOS
0x180001738  mov     dword ptr [rsp+128h+pvData], edi; AuthzSvc
0x18000173c  mov     [rsp+128h+pdwType], rdi; AuthIdentity
0x180001741  xor     edx, edx; ServerPrincName
0x180001743  mov     r9d, 0Ah; AuthnSvc
0x180001749  mov     r8d, 6; AuthnLevel
0x18000174f  mov     rcx, [rsp+128h+Binding]; Binding
0x180001754  call    cs:__imp_RpcBindingSetAuthInfoExW
0x18000175a  mov     ebx, eax
0x18000175c  test    eax, eax
0x18000175e  jnz     loc_180001830
0x180001764  mov     rcx, [rsp+128h+Binding]
0x180001769  xor     eax, eax
0x18000176b  lock cmpxchg cs:qword_1800147E0, rcx
0x180001774  jnz     loc_180001842
0x18000177a  mov     [rsp+128h+Binding], rdi
0x18000177f  mov     rsi, cs:qword_1800147E0
0x180001786  mov     [rsp+128h+var_D0], rsi
0x18000178b  jmp     loc_180001583
0x180001790  cmp     dword ptr [rsp+128h+Binding], 1
0x180001795  jnz     loc_1800014CA
0x18000179b  jmp     short loc_1800017CF
0x18000179d  lea     r9, aRpcstringbindi; "RpcStringBindingCompose failed [%d]"
0x1800017a4  mov     r8d, 192h
0x1800017aa  mov     dword ptr [rsp+128h+pdwType], eax
0x1800017ae  lea     rdx, aPcapcreatebind; "PcapCreateBindingHandle"
0x1800017b5  mov     ecx, 1
0x1800017ba  call    AslLogCallPrintf
0x1800017bf  jmp     loc_180001585
0x1800017c4  cmp     dword ptr [rsp+128h+Binding], 1
0x1800017c9  jnz     loc_180001518
0x1800017cf  lea     r9, aSendtoserviceI; "SendToService ignored,PCA disabled"
0x1800017d6  xor     r8d, r8d; unsigned int
0x1800017d9  xor     edx, edx; unsigned int
0x1800017db  lea     rcx, aPcaclient; "PcaClient"
0x1800017e2  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800017e7  mov     ebx, edi
0x1800017e9  mov     r13, 200000004201h
0x1800017f3  jmp     loc_180001600
0x1800017f8  lea     r9, aRpcbindingfrom; "RpcBindingFromStringBinding failed [%d]"
0x1800017ff  mov     r8d, 199h
0x180001805  jmp     short loc_1800017AA
0x180001807  lea     r9, aRpcbindingseto; "RpcBindingSetOption failed [%d]"
0x18000180e  mov     r8d, 1A2h
0x180001814  jmp     short loc_1800017AA
0x180001816  call    cs:__imp_GetLastError
0x18000181c  mov     ebx, eax
0x18000181e  lea     r9, aFailedToCreate; "Failed to create sid [%d]"
0x180001825  mov     r8d, 1AFh
0x18000182b  jmp     loc_1800017AA
0x180001830  lea     r9, aRpcbindingseta; "RpcBindingSetAuthInfoEx failed [%d]"
0x180001837  mov     r8d, 1C7h
0x18000183d  jmp     loc_1800017AA
0x180001842  lea     rcx, [rsp+128h+Binding]; Binding
0x180001847  call    cs:__imp_RpcBindingFree
0x18000184d  jmp     loc_18000177A
0x180001852  lea     rcx, [rsp+128h+Binding]; Binding
0x180001857  call    cs:__imp_RpcBindingFree
0x18000185d  jmp     loc_18000159B
0x18000c170  push    rbp
0x18000c172  sub     rsp, 40h
0x18000c176  mov     rbp, rdx
0x18000c179  mov     rcx, [rcx]
0x18000c17c  mov     ecx, [rcx]; ExceptionCode
0x18000c17e  call    cs:__imp_I_RpcExceptionFilter
0x18000c184  nop
0x18000c185  add     rsp, 40h
0x18000c189  pop     rbp
0x18000c18a  retn
```
