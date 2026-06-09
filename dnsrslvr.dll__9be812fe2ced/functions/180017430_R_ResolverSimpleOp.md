# R_ResolverSimpleOp

- ea: `0x180017430`
- end: `0x18001780a`
- name: `R_ResolverSimpleOp`
- size: `986`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180004aa8`
- `0x1800078e8`
- `0x18000b130`
- `0x180017128`
- `0x180017270`
- `0x180017430`
- `0x180017c60`
- `0x180027c04`
- `0x18003e9b0`
- `0x180046ec0`
- `0x18004a600`
- `0x180054850`
- `0x18007aa5c`
- `0x180086b1c`
- `0x180086bd4`

## import_xrefs

- `DNSAPI!DnsUpdateCaptivePortalPresence` at `0x180017712`
- `DNSAPI!DnsUpdateCaptivePortalPresence` at `0x180017712`
- `DNSAPI!NetInfo_Free` at `0x1800175cf`
- `DNSAPI!NetInfo_Free` at `0x180017616`
- `DNSAPI!NetInfo_Free` at `0x1800175cf`
- `DNSAPI!NetInfo_Free` at `0x180017616`
- `DNSAPI!DnsUpdateMachinePresence` at `0x180017764`
- `DNSAPI!DnsUpdateMachinePresence` at `0x180017764`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800175c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001760d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800175c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001760d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001759e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800175e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001759e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800175e5`

## pseudocode

```c
__int64 __fastcall R_ResolverSimpleOp(int a1, int a2, unsigned int a3, __int64 a4)
{
  DWORD v7; // ecx
  __int64 v8; // rcx
  char v9; // al
  char RpcClientPid; // si
  unsigned int v11; // edi
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  int v15; // edx
  int v16; // ecx
  unsigned int updated; // eax
  int v19; // edx
  __int64 v20; // rbx
  __int64 v21; // rcx
  __int64 v22; // rbx
  int v23; // ebx
  int v24; // ebx
  int v25; // ebx
  int v26; // edx
  int v27; // ecx
  int v28; // edx
  int v29; // ecx
  int v30; // edx
  int v31; // ecx
  int v32; // edx
  int v33; // ecx
  int v34; // edx
  int v35; // ecx
  void *v36; // [rsp+40h] [rbp-38h] BYREF

  v36 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qdDS(a1, a2, a3, a1, a2, a3, a4);
  v7 = 1;
  if ( a2 != 3 )
    v7 = 32;
  if ( (unsigned int)Rpc_AccessCheck(v7) )
  {
    v9 = Microsoft_Windows_DNS_ClientEnableBits;
    RpcClientPid = 0;
    v11 = 0;
    if ( (Microsoft_Windows_DNS_ClientEnableBits & 4) != 0 )
    {
      RpcClientPid = GetRpcClientPid();
      v9 = Microsoft_Windows_DNS_ClientEnableBits;
    }
    v12 = a2 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( !v13 )
      {
        if ( (v9 & 4) != 0 )
        {
          DnsLoadString(v8, 4101, &v36);
          if ( (Microsoft_Windows_DNS_ClientEnableBits & 4) != 0 )
            McTemplateU0zzqq_EventWriteTransfer(v35, v34, (_DWORD)v36, 0, 0, RpcClientPid);
        }
        updated = Reg_DoRegistration(4099);
        goto LABEL_15;
      }
      v14 = v13 - 1;
      if ( !v14 )
      {
        if ( (v9 & 4) != 0 )
        {
          DnsLoadString(v8, 4100, &v36);
          if ( (Microsoft_Windows_DNS_ClientEnableBits & 4) != 0 )
            McTemplateU0zzqq_EventWriteTransfer(v16, v15, (_DWORD)v36, a4, a3, RpcClientPid);
        }
        updated = Reg_DoRegisterAdapter(a4, a3);
LABEL_15:
        v11 = updated;
        goto LABEL_16;
      }
      v23 = v14 - 1;
      if ( !v23 )
      {
        if ( (v9 & 4) != 0 )
        {
          DnsLoadString(v8, 4102, &v36);
          if ( (Microsoft_Windows_DNS_ClientEnableBits & 4) != 0 )
            McTemplateU0zzqq_EventWriteTransfer(v33, v32, (_DWORD)v36, 0, 0, RpcClientPid);
        }
        updated = Areg_RemoveRegistrations();
        goto LABEL_15;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        if ( (v9 & 4) != 0 )
        {
          DnsLoadString(v8, 4104, &v36);
          if ( (Microsoft_Windows_DNS_ClientEnableBits & 4) != 0 )
            McTemplateU0zzqq_EventWriteTransfer(v31, v30, (_DWORD)v36, 0, 0, RpcClientPid);
        }
        updated = DnsUpdateMachinePresence();
        goto LABEL_15;
      }
      v25 = v24 - 1;
      if ( v25 )
      {
        if ( v25 == 1 )
        {
          if ( (v9 & 4) != 0 )
          {
            DnsLoadString(v8, 4107, &v36);
            if ( (Microsoft_Windows_DNS_ClientEnableBits & 4) != 0 )
              McTemplateU0zzqq_EventWriteTransfer(v27, v26, (_DWORD)v36, 0, 0, RpcClientPid);
          }
          updated = DnsZtDeployStaticExceptions();
          goto LABEL_15;
        }
      }
      else
      {
        if ( (v9 & 4) != 0 )
        {
          DnsLoadString(v8, 4105, &v36);
          if ( (Microsoft_Windows_DNS_ClientEnableBits & 4) != 0 )
            McTemplateU0zzqq_EventWriteTransfer(v29, v28, (_DWORD)v36, 0, a3, RpcClientPid);
        }
        DnsUpdateCaptivePortalPresence(a3 == 1);
        UpdateNetworkInfo(0, 0);
        UpdateNetworkInfo(0, 1);
      }
    }
    else
    {
      if ( (v9 & 4) != 0 )
      {
        DnsLoadString(v8, 4103, &v36);
        if ( (Microsoft_Windows_DNS_ClientEnableBits & 4) != 0 )
          McTemplateU0zzqq_EventWriteTransfer(v8, v19, (_DWORD)v36, 0, 0, RpcClientPid);
      }
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_qd(v8, 10, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, 0, 0);
      EnterCriticalSection(&g_csNetinfo);
      v20 = g_NetworkInfo;
      ++g_NetInfoTag;
      g_NetworkInfo = 0;
      g_IsReachableServerUpdateRequired = 1;
      LeaveCriticalSection(&g_csNetinfo);
      NetInfo_Free(v20);
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_qd(v21, 10, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids, 0, 1);
      EnterCriticalSection(&g_csNetinfo);
      v22 = g_PerNetworkNetInfo;
      ++g_NetInfoTag;
      g_PerNetworkNetInfo = 0;
      g_IsReachableServerUpdateRequired = 1;
      LeaveCriticalSection(&g_csNetinfo);
      NetInfo_Free(v22);
      v11 = 0;
    }
  }
  else
  {
    v11 = 5;
  }
LABEL_16:
  MIDL_user_free(v36);
  v36 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 20, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180017430  mov     [rsp+arg_8], rbx
0x180017435  push    rsi
0x180017436  push    rdi
0x180017437  push    r12
0x180017439  push    r14
0x18001743b  push    r15
0x18001743d  sub     rsp, 50h
0x180017441  mov     rax, cs:__security_cookie
0x180017448  xor     rax, rsp
0x18001744b  mov     [rsp+78h+var_30], rax
0x180017450  mov     r15, r9
0x180017453  mov     [rsp+78h+var_38], 0
0x18001745c  mov     r14d, r8d
0x18001745f  mov     ebx, edx
0x180017461  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180017468  jnz     loc_180017683
0x18001746e  mov     ecx, 1
0x180017473  cmp     ebx, 3
0x180017476  lea     eax, [rcx+1Fh]
0x180017479  cmovnz  ecx, eax
0x18001747c  call    Rpc_AccessCheck
0x180017481  test    eax, eax
0x180017483  jz      loc_180017549
0x180017489  mov     eax, cs:Microsoft_Windows_DNS_ClientEnableBits
0x18001748f  xor     esi, esi
0x180017491  xor     edi, edi
0x180017493  mov     r12b, 4
0x180017496  test    r12b, al
0x180017499  jz      short loc_1800174A8
0x18001749b  call    GetRpcClientPid
0x1800174a0  mov     esi, eax
0x1800174a2  mov     eax, cs:Microsoft_Windows_DNS_ClientEnableBits
0x1800174a8  sub     ebx, 1
0x1800174ab  jz      loc_180017550
0x1800174b1  sub     ebx, 1
0x1800174b4  jz      loc_1800177AB
0x1800174ba  sub     ebx, 1
0x1800174bd  jnz     loc_180017623
0x1800174c3  test    r12b, al
0x1800174c6  jz      short loc_1800174E0
0x1800174c8  mov     edx, 1004h
0x1800174cd  lea     r8, [rsp+78h+var_38]
0x1800174d2  call    DnsLoadString
0x1800174d7  test    byte ptr cs:Microsoft_Windows_DNS_ClientEnableBits, r12b
0x1800174de  jnz     short loc_180017531
0x1800174e0  mov     edx, r14d
0x1800174e3  mov     rcx, r15
0x1800174e6  call    Reg_DoRegisterAdapter
0x1800174eb  mov     edi, eax
0x1800174ed  mov     rcx, [rsp+78h+var_38]; void *
0x1800174f2  call    MIDL_user_free
0x1800174f7  mov     [rsp+78h+var_38], 0
0x180017500  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180017507  jnz     loc_1800177EC
0x18001750d  mov     eax, edi
0x18001750f  mov     rcx, [rsp+78h+var_30]
0x180017514  xor     rcx, rsp; StackCookie
0x180017517  call    __security_check_cookie
0x18001751c  mov     rbx, [rsp+78h+arg_8]
0x180017524  add     rsp, 50h
0x180017528  pop     r15
0x18001752a  pop     r14
0x18001752c  pop     r12
0x18001752e  pop     rdi
0x18001752f  pop     rsi
0x180017530  retn
0x180017531  mov     r8, [rsp+78h+var_38]
0x180017536  mov     r9, r15
0x180017539  mov     [rsp+78h+var_50], esi
0x18001753d  mov     [rsp+78h+var_58], r14d
0x180017542  call    McTemplateU0zzqq_EventWriteTransfer
0x180017547  jmp     short loc_1800174E0
0x180017549  mov     edi, 5
0x18001754e  jmp     short loc_1800174ED
0x180017550  test    r12b, al
0x180017553  jz      short loc_180017582
0x180017555  mov     edx, 1007h
0x18001755a  lea     r8, [rsp+78h+var_38]
0x18001755f  call    DnsLoadString
0x180017564  test    byte ptr cs:Microsoft_Windows_DNS_ClientEnableBits, r12b
0x18001756b  jz      short loc_180017582
0x18001756d  mov     r8, [rsp+78h+var_38]
0x180017572  xor     r9d, r9d
0x180017575  mov     [rsp+78h+var_50], esi
0x180017579  mov     [rsp+78h+var_58], edi
0x18001757d  call    McTemplateU0zzqq_EventWriteTransfer
0x180017582  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180017589  mov     esi, 0Ah
0x18001758e  jnz     loc_18001769E
0x180017594  lea     rdi, g_csNetinfo
0x18001759b  mov     rcx, rdi; lpCriticalSection
0x18001759e  call    cs:__imp_EnterCriticalSection
0x1800175a4  mov     rbx, cs:g_NetworkInfo
0x1800175ab  inc     cs:g_NetInfoTag
0x1800175b1  mov     cs:g_NetworkInfo, 0
0x1800175bc  mov     cs:g_IsReachableServerUpdateRequired, 1
0x1800175c3  mov     rcx, rdi; lpCriticalSection
0x1800175c6  call    cs:__imp_LeaveCriticalSection
0x1800175cc  mov     rcx, rbx
0x1800175cf  call    cs:__imp_NetInfo_Free
0x1800175d5  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800175dc  jnz     loc_1800176B8
0x1800175e2  mov     rcx, rdi; lpCriticalSection
0x1800175e5  call    cs:__imp_EnterCriticalSection
0x1800175eb  mov     rbx, cs:g_PerNetworkNetInfo
0x1800175f2  inc     cs:g_NetInfoTag
0x1800175f8  mov     cs:g_PerNetworkNetInfo, 0
0x180017603  mov     cs:g_IsReachableServerUpdateRequired, 1
0x18001760a  mov     rcx, rdi; lpCriticalSection
0x18001760d  call    cs:__imp_LeaveCriticalSection
0x180017613  mov     rcx, rbx
0x180017616  call    cs:__imp_NetInfo_Free
0x18001761c  xor     edi, edi
0x18001761e  jmp     loc_1800174ED
0x180017623  sub     ebx, 1
0x180017626  jz      loc_18001776F
0x18001762c  sub     ebx, 1
0x18001762f  jz      loc_180017732
0x180017635  sub     ebx, 1
0x180017638  jz      loc_1800176D6
0x18001763e  cmp     ebx, 1
0x180017641  jnz     loc_1800174ED
0x180017647  test    r12b, al
0x18001764a  jz      short loc_180017679
0x18001764c  mov     edx, 100Bh
0x180017651  lea     r8, [rsp+78h+var_38]
0x180017656  call    DnsLoadString
0x18001765b  test    byte ptr cs:Microsoft_Windows_DNS_ClientEnableBits, r12b
0x180017662  jz      short loc_180017679
0x180017664  mov     r8, [rsp+78h+var_38]
0x180017669  xor     r9d, r9d
0x18001766c  mov     [rsp+78h+var_50], esi
0x180017670  mov     [rsp+78h+var_58], edi
0x180017674  call    McTemplateU0zzqq_EventWriteTransfer
0x180017679  call    DnsZtDeployStaticExceptions
0x18001767e  jmp     loc_1800174EB
0x180017683  mov     [rsp+78h+var_48], r15
0x180017688  mov     r9, rcx
0x18001768b  mov     [rsp+78h+var_50], r14d
0x180017690  mov     [rsp+78h+var_58], ebx
0x180017694  call    WPP_SF_qdDS
0x180017699  jmp     loc_18001746E
0x18001769e  mov     edx, esi
0x1800176a0  mov     [rsp+78h+var_58], edi
0x1800176a4  xor     r9d, r9d
0x1800176a7  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x1800176ae  call    WPP_SF_qd
0x1800176b3  jmp     loc_180017594
0x1800176b8  mov     edx, esi
0x1800176ba  mov     [rsp+78h+var_58], 1
0x1800176c2  xor     r9d, r9d
0x1800176c5  lea     r8, WPP_cba5fe3efa5838b7033e5e8664507352_Traceguids
0x1800176cc  call    WPP_SF_qd
0x1800176d1  jmp     loc_1800175E2
0x1800176d6  test    r12b, al
0x1800176d9  jz      short loc_180017709
0x1800176db  mov     edx, 1009h
0x1800176e0  lea     r8, [rsp+78h+var_38]
0x1800176e5  call    DnsLoadString
0x1800176ea  test    byte ptr cs:Microsoft_Windows_DNS_ClientEnableBits, r12b
0x1800176f1  jz      short loc_180017709
0x1800176f3  mov     r8, [rsp+78h+var_38]
0x1800176f8  xor     r9d, r9d
0x1800176fb  mov     [rsp+78h+var_50], esi
0x1800176ff  mov     [rsp+78h+var_58], r14d
0x180017704  call    McTemplateU0zzqq_EventWriteTransfer
0x180017709  xor     ecx, ecx
0x18001770b  cmp     r14d, 1
0x18001770f  setz    cl
0x180017712  call    cs:__imp_DnsUpdateCaptivePortalPresence
0x180017718  xor     edx, edx
0x18001771a  xor     ecx, ecx
0x18001771c  call    UpdateNetworkInfo
0x180017721  mov     edx, 1
0x180017726  xor     ecx, ecx
0x180017728  call    UpdateNetworkInfo
0x18001772d  jmp     loc_1800174ED
0x180017732  test    r12b, al
0x180017735  jz      short loc_180017764
0x180017737  mov     edx, 1008h
0x18001773c  lea     r8, [rsp+78h+var_38]
0x180017741  call    DnsLoadString
0x180017746  test    byte ptr cs:Microsoft_Windows_DNS_ClientEnableBits, r12b
0x18001774d  jz      short loc_180017764
0x18001774f  mov     r8, [rsp+78h+var_38]
0x180017754  xor     r9d, r9d
0x180017757  mov     [rsp+78h+var_50], esi
0x18001775b  mov     [rsp+78h+var_58], edi
0x18001775f  call    McTemplateU0zzqq_EventWriteTransfer
0x180017764  call    cs:__imp_DnsUpdateMachinePresence
0x18001776a  jmp     loc_1800174EB
0x18001776f  test    r12b, al
0x180017772  jz      short loc_1800177A1
0x180017774  mov     edx, 1006h
0x180017779  lea     r8, [rsp+78h+var_38]
0x18001777e  call    DnsLoadString
0x180017783  test    byte ptr cs:Microsoft_Windows_DNS_ClientEnableBits, r12b
0x18001778a  jz      short loc_1800177A1
0x18001778c  mov     r8, [rsp+78h+var_38]
0x180017791  xor     r9d, r9d
0x180017794  mov     [rsp+78h+var_50], esi
0x180017798  mov     [rsp+78h+var_58], edi
0x18001779c  call    McTemplateU0zzqq_EventWriteTransfer
0x1800177a1  call    Areg_RemoveRegistrations
0x1800177a6  jmp     loc_1800174EB
0x1800177ab  test    r12b, al
0x1800177ae  jz      short loc_1800177DD
0x1800177b0  mov     edx, 1005h
0x1800177b5  lea     r8, [rsp+78h+var_38]
0x1800177ba  call    DnsLoadString
0x1800177bf  test    byte ptr cs:Microsoft_Windows_DNS_ClientEnableBits, r12b
0x1800177c6  jz      short loc_1800177DD
0x1800177c8  mov     r8, [rsp+78h+var_38]
0x1800177cd  xor     r9d, r9d
0x1800177d0  mov     [rsp+78h+var_50], esi
0x1800177d4  mov     [rsp+78h+var_58], edi
0x1800177d8  call    McTemplateU0zzqq_EventWriteTransfer
0x1800177dd  mov     ecx, 1003h; int
0x1800177e2  call    Reg_DoRegistration
0x1800177e7  jmp     loc_1800174EB
0x1800177ec  mov     edx, 14h
0x1800177f1  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x1800177f8  mov     ecx, 40Bh
0x1800177fd  mov     r9d, edi
0x180017800  call    WPP_SF_d
0x180017805  jmp     loc_18001750D
```
