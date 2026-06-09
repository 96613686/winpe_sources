# FhServiceOpenPipe

- ea: `0x180003230`
- end: `0x180003600`
- name: `FhServiceOpenPipe`
- size: `976`
- prototype: `__int64 __fastcall(int, RPC_BINDING_HANDLE **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001ae4`
- `0x180002538`
- `0x1800025cc`
- `0x180002680`
- `0x180002c40`
- `0x180003230`
- `0x180003a00`
- `0x180004f20`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x1800035ae`
- `ADVAPI32!FreeSid` at `0x1800035ae`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000342b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18000342b`
- `KERNEL32!GetLastError` at `0x180003435`
- `KERNEL32!GetLastError` at `0x180003435`
- `RPCRT4!NdrClientCall3` at `0x18000352e`
- `RPCRT4!NdrClientCall3` at `0x18000352e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000336c`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000336c`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800033b6`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800033b6`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800034cf`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x1800034cf`
- `RPCRT4!RpcStringFreeW` at `0x1800035c5`
- `RPCRT4!RpcStringFreeW` at `0x1800035c5`

## pseudocode

```c
__int64 __fastcall FhServiceOpenPipe(int a1, RPC_BINDING_HANDLE **a2)
{
  CLIENT_CALL_RETURN v3; // rbx
  RPC_BINDING_HANDLE *v4; // r14
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  RPC_BINDING_HANDLE *v7; // rax
  RPC_BINDING_HANDLE *v8; // rsi
  RPC_STATUS v9; // eax
  RPC_STATUS v10; // eax
  signed int LastError; // eax
  RPC_STATUS v12; // eax
  PSID pSid; // [rsp+60h] [rbp-88h] BYREF
  RPC_WSTR String; // [rsp+68h] [rbp-80h] BYREF
  int Pointer; // [rsp+70h] [rbp-78h]
  CLIENT_CALL_RETURN v17; // [rsp+78h] [rbp-70h]
  RPC_BINDING_HANDLE *v18; // [rsp+80h] [rbp-68h]
  RPC_BINDING_HANDLE **v19; // [rsp+90h] [rbp-58h]
  RPC_SECURITY_QOS SecurityQOS; // [rsp+98h] [rbp-50h] BYREF
  __int128 v21; // [rsp+A8h] [rbp-40h]
  PSID v22; // [rsp+B8h] [rbp-30h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+C0h] [rbp-28h] BYREF

  v19 = a2;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  SecurityQOS = 0;
  v21 = 0;
  v22 = 0;
  String = 0;
  pSid = 0;
  *a2 = 0;
  if ( a1 && (LODWORD(v3.Pointer) = StartFhService(), SLODWORD(v3.Simple) < 0) )
  {
    v4 = 0;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = 10;
LABEL_6:
      WPP_SF_d(v5[2], v6, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids, LODWORD(v3.Pointer));
    }
  }
  else
  {
    v7 = (RPC_BINDING_HANDLE *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v8 = v7;
    v4 = v7;
    v18 = v7;
    if ( v7 )
    {
      *(_OWORD *)v7 = 0;
      v9 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, 0, &String);
      LODWORD(v3.Pointer) = v9;
      if ( v9 )
      {
        if ( v9 > 0 )
          LODWORD(v3.Pointer) = (unsigned __int16)v9 | 0x80070000;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v6 = 12;
          goto LABEL_6;
        }
      }
      else
      {
        v10 = RpcBindingFromStringBindingW(String, v8);
        LODWORD(v3.Pointer) = v10;
        if ( v10 )
        {
          if ( v10 > 0 )
            LODWORD(v3.Pointer) = (unsigned __int16)v10 | 0x80070000;
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 13;
            goto LABEL_6;
          }
        }
        else if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
        {
          v21 = 0;
          SecurityQOS.Version = 3;
          *(_QWORD *)&SecurityQOS.Capabilities = 1;
          SecurityQOS.ImpersonationType = 3;
          v22 = pSid;
          v12 = RpcBindingSetAuthInfoExW(*v8, 0, 3u, 0xAu, 0, 0, &SecurityQOS);
          LODWORD(v3.Pointer) = v12;
          if ( v12 )
          {
            if ( v12 > 0 )
              LODWORD(v3.Pointer) = (unsigned __int16)v12 | 0x80070000;
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v6 = 15;
              goto LABEL_6;
            }
          }
          else
          {
            v17.Simple = 0;
            v3.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&FhServiceApi_ProxyInfo, 0, 0, *v8, v8 + 1).Pointer;
            v17.Pointer = v3.Pointer;
            Pointer = (int)v3.Pointer;
            if ( SLODWORD(v3.Simple) >= 0 )
            {
              *a2 = v8;
              goto LABEL_40;
            }
            v5 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v6 = 16;
              goto LABEL_6;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          LODWORD(v3.Pointer) = LastError;
          if ( LastError > 0 )
            LODWORD(v3.Pointer) = (unsigned __int16)LastError | 0x80070000;
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v6 = 14;
            goto LABEL_6;
          }
        }
      }
    }
    else
    {
      LODWORD(v3.Pointer) = -2147024882;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids,
          "pipeContext");
    }
  }
LABEL_40:
  if ( SLODWORD(v3.Simple) < 0 && v4 )
    FhServiceClosePipe(v4);
  if ( pSid )
  {
    FreeSid(pSid);
    pSid = 0;
  }
  if ( String )
    RpcStringFreeW(&String);
  FileHistoryApiTelemetry::LogFHApiUsage(1);
  return LODWORD(v3.Pointer);
}

```

## disassembly

```asm
0x180003230  mov     r11, rsp
0x180003233  mov     [r11+8], rbx
0x180003237  mov     [r11+18h], rsi
0x18000323b  push    rdi
0x18000323c  push    r14
0x18000323e  push    r15
0x180003240  sub     rsp, 0D0h
0x180003247  mov     rax, cs:__security_cookie
0x18000324e  xor     rax, rsp
0x180003251  mov     [rsp+0E8h+var_20], rax
0x180003259  mov     r15, rdx
0x18000325c  mov     [rsp+0E8h+var_58], rdx
0x180003264  xor     edi, edi
0x180003266  mov     [r11-28h], edi
0x18000326a  mov     word ptr [r11-24h], 500h
0x180003271  xorps   xmm0, xmm0
0x180003274  xor     eax, eax
0x180003276  movups  xmmword ptr [r11-50h], xmm0
0x18000327b  movups  xmmword ptr [r11-40h], xmm0
0x180003280  mov     [r11-30h], rax
0x180003284  mov     [r11-80h], rdi
0x180003288  mov     [rsp+0E8h+var_88], rdi
0x18000328d  mov     [rdx], rdi
0x180003290  test    ecx, ecx
0x180003292  jz      short loc_1800032DE
0x180003294  call    ?StartFhService@@YAJXZ; StartFhService(void)
0x180003299  mov     ebx, eax
0x18000329b  test    eax, eax
0x18000329d  jns     short loc_1800032DE
0x18000329f  mov     r14d, edi
0x1800032a2  lea     rax, WPP_GLOBAL_Control
0x1800032a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800032b0  cmp     rcx, rax
0x1800032b3  jz      loc_180003593
0x1800032b9  test    byte ptr [rcx+1Ch], 1
0x1800032bd  jz      loc_180003593
0x1800032c3  lea     edx, [rdi+0Ah]
0x1800032c6  mov     r9d, ebx
0x1800032c9  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x1800032d0  mov     rcx, [rcx+10h]
0x1800032d4  call    WPP_SF_d
0x1800032d9  jmp     loc_180003593
0x1800032de  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800032e5  mov     ecx, 10h; unsigned __int64
0x1800032ea  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800032ef  mov     rsi, rax
0x1800032f2  mov     r14, rax
0x1800032f5  mov     [rsp+0E8h+var_68], rax
0x1800032fd  test    rax, rax
0x180003300  jnz     short loc_180003348
0x180003302  mov     ebx, 8007000Eh
0x180003307  lea     rax, WPP_GLOBAL_Control
0x18000330e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003315  cmp     rcx, rax
0x180003318  jz      loc_180003593
0x18000331e  test    byte ptr [rcx+1Ch], 1
0x180003322  jz      loc_180003593
0x180003328  lea     edx, [r14+0Bh]
0x18000332c  lea     r9, aPipecontext; "pipeContext"
0x180003333  lea     r8, WPP_e6bf46b9fc6c3c446aaf1363dba0f4b7_Traceguids
0x18000333a  mov     rcx, [rcx+10h]
0x18000333e  call    WPP_SF_s
0x180003343  jmp     loc_180003593
0x180003348  xorps   xmm0, xmm0
0x18000334b  movups  xmmword ptr [rax], xmm0
0x18000334e  lea     rax, [rsp+0E8h+String]
0x180003353  mov     [rsp+0E8h+StringBinding], rax; StringBinding
0x180003358  mov     [rsp+0E8h+Options], rdi; Options
0x18000335d  xor     r9d, r9d; Endpoint
0x180003360  xor     r8d, r8d; NetworkAddr
0x180003363  lea     rdx, ProtSeq; "ncalrpc"
0x18000336a  xor     ecx, ecx; ObjUuid
0x18000336c  call    cs:__imp_RpcStringBindingComposeW
0x180003372  mov     ebx, eax
0x180003374  test    eax, eax
0x180003376  jz      short loc_1800033AE
0x180003378  jle     short loc_180003383
0x18000337a  movzx   ebx, ax
0x18000337d  or      ebx, 80070000h
0x180003383  lea     rax, WPP_GLOBAL_Control
0x18000338a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003391  cmp     rcx, rax
0x180003394  jz      loc_180003593
0x18000339a  test    byte ptr [rcx+1Ch], 1
0x18000339e  jz      loc_180003593
0x1800033a4  mov     edx, 0Ch
0x1800033a9  jmp     loc_1800032C6
0x1800033ae  mov     rdx, rsi; Binding
0x1800033b1  mov     rcx, [rsp+0E8h+String]; StringBinding
0x1800033b6  call    cs:__imp_RpcBindingFromStringBindingW
0x1800033bc  mov     ebx, eax
0x1800033be  test    eax, eax
0x1800033c0  jz      short loc_1800033F8
0x1800033c2  jle     short loc_1800033CD
0x1800033c4  movzx   ebx, ax
0x1800033c7  or      ebx, 80070000h
0x1800033cd  lea     rax, WPP_GLOBAL_Control
0x1800033d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800033db  cmp     rcx, rax
0x1800033de  jz      loc_180003593
0x1800033e4  test    byte ptr [rcx+1Ch], 1
0x1800033e8  jz      loc_180003593
0x1800033ee  mov     edx, 0Dh
0x1800033f3  jmp     loc_1800032C6
0x1800033f8  lea     rax, [rsp+0E8h+var_88]
0x1800033fd  mov     [rsp+0E8h+pSid], rax; pSid
0x180003402  mov     [rsp+0E8h+nSubAuthority7], edi; nSubAuthority7
0x180003406  mov     [rsp+0E8h+nSubAuthority6], edi; nSubAuthority6
0x18000340a  mov     [rsp+0E8h+nSubAuthority5], edi; nSubAuthority5
0x18000340e  mov     [rsp+0E8h+nSubAuthority4], edi; nSubAuthority4
0x180003412  mov     dword ptr [rsp+0E8h+StringBinding], edi; nSubAuthority3
0x180003416  mov     dword ptr [rsp+0E8h+Options], edi; nSubAuthority2
0x18000341a  xor     r9d, r9d; nSubAuthority1
0x18000341d  lea     r8d, [r9+12h]; nSubAuthority0
0x180003421  mov     dl, 1; nSubAuthorityCount
0x180003423  lea     rcx, [rsp+0E8h+pIdentifierAuthority]; pIdentifierAuthority
0x18000342b  call    cs:__imp_AllocateAndInitializeSid
0x180003431  test    eax, eax
0x180003433  jnz     short loc_180003475
0x180003435  call    cs:__imp_GetLastError
0x18000343b  mov     ebx, eax
0x18000343d  test    eax, eax
0x18000343f  jle     short loc_18000344A
0x180003441  movzx   ebx, ax
0x180003444  or      ebx, 80070000h
0x18000344a  lea     rax, WPP_GLOBAL_Control
0x180003451  mov     rcx, cs:WPP_GLOBAL_Control
0x180003458  cmp     rcx, rax
0x18000345b  jz      loc_180003593
0x180003461  test    byte ptr [rcx+1Ch], 1
0x180003465  jz      loc_180003593
0x18000346b  mov     edx, 0Eh
0x180003470  jmp     loc_1800032C6
0x180003475  xorps   xmm0, xmm0
0x180003478  movdqu  [rsp+0E8h+var_40], xmm0
0x180003481  mov     r8d, 3; AuthnLevel
0x180003487  mov     [rsp+0E8h+SecurityQOS.Version], r8d
0x18000348f  mov     qword ptr [rsp+0E8h+SecurityQOS.Capabilities], 1
0x18000349b  mov     [rsp+0E8h+SecurityQOS.ImpersonationType], r8d
0x1800034a3  mov     rax, [rsp+0E8h+var_88]
0x1800034a8  mov     [rsp+0E8h+var_30], rax
0x1800034b0  lea     rax, [rsp+0E8h+SecurityQOS]
0x1800034b8  mov     qword ptr [rsp+0E8h+nSubAuthority4], rax; SecurityQOS
0x1800034bd  mov     dword ptr [rsp+0E8h+StringBinding], edi; AuthzSvc
0x1800034c1  mov     [rsp+0E8h+Options], rdi; AuthIdentity
0x1800034c6  xor     edx, edx; ServerPrincName
0x1800034c8  lea     r9d, [r8+7]; AuthnSvc
0x1800034cc  mov     rcx, [rsi]; Binding
0x1800034cf  call    cs:__imp_RpcBindingSetAuthInfoExW
0x1800034d5  mov     ebx, eax
0x1800034d7  test    eax, eax
0x1800034d9  jz      short loc_180003511
0x1800034db  jle     short loc_1800034E6
0x1800034dd  movzx   ebx, ax
0x1800034e0  or      ebx, 80070000h
0x1800034e6  lea     rax, WPP_GLOBAL_Control
0x1800034ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034f4  cmp     rcx, rax
0x1800034f7  jz      loc_180003593
0x1800034fd  test    byte ptr [rcx+1Ch], 1
0x180003501  jz      loc_180003593
0x180003507  mov     edx, 0Fh
0x18000350c  jmp     loc_1800032C6
0x180003511  mov     [rsp+0E8h+var_70], rdi
0x180003516  lea     rax, [rsi+8]
0x18000351a  mov     [rsp+0E8h+Options], rax
0x18000351f  mov     r9, [rsi]
0x180003522  xor     r8d, r8d; pReturnValue
0x180003525  xor     edx, edx; nProcNum
0x180003527  lea     rcx, ?FhServiceApi_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000352e  call    cs:__imp_NdrClientCall3
0x180003534  mov     rbx, rax
0x180003537  mov     [rsp+0E8h+var_70], rax
0x18000353c  mov     [rsp+0E8h+var_78], eax
0x180003540  jmp     short loc_180003569
0x180003542  test    eax, eax
0x180003544  jle     short loc_18000354E
0x180003546  movzx   eax, ax
0x180003549  or      eax, 80070000h
0x18000354e  mov     ebx, eax
0x180003550  mov     [rsp+0E8h+var_78], eax
0x180003554  xor     edi, edi
0x180003556  mov     r14, [rsp+0E8h+var_68]
0x18000355e  mov     rsi, r14
0x180003561  mov     r15, [rsp+0E8h+var_58]
0x180003569  test    ebx, ebx
0x18000356b  jns     short loc_180003590
0x18000356d  lea     rax, WPP_GLOBAL_Control
0x180003574  mov     rcx, cs:WPP_GLOBAL_Control
0x18000357b  cmp     rcx, rax
0x18000357e  jz      short loc_180003593
0x180003580  test    byte ptr [rcx+1Ch], 1
0x180003584  jz      short loc_180003593
0x180003586  mov     edx, 10h
0x18000358b  jmp     loc_1800032C6
0x180003590  mov     [r15], rsi
0x180003593  test    ebx, ebx
0x180003595  jns     short loc_1800035A4
0x180003597  test    r14, r14
0x18000359a  jz      short loc_1800035A4
0x18000359c  mov     rcx, r14; Binding
0x18000359f  call    FhServiceClosePipe
0x1800035a4  mov     rcx, [rsp+0E8h+var_88]; pSid
0x1800035a9  test    rcx, rcx
0x1800035ac  jz      short loc_1800035B9
0x1800035ae  call    cs:__imp_FreeSid
0x1800035b4  mov     [rsp+0E8h+var_88], rdi
0x1800035b9  cmp     [rsp+0E8h+String], rdi
0x1800035be  jz      short loc_1800035CB
0x1800035c0  lea     rcx, [rsp+0E8h+String]; String
0x1800035c5  call    cs:__imp_RpcStringFreeW
0x1800035cb  mov     ecx, 1
0x1800035d0  call    ?LogFHApiUsage@FileHistoryApiTelemetry@@YAXW4_FH_API_ID@@@Z; FileHistoryApiTelemetry::LogFHApiUsage(_FH_API_ID)
0x1800035d5  mov     eax, ebx
0x1800035d7  mov     rcx, [rsp+0E8h+var_20]
0x1800035df  xor     rcx, rsp; StackCookie
0x1800035e2  call    __security_check_cookie
0x1800035e7  lea     r11, [rsp+0E8h+var_18]
0x1800035ef  mov     rbx, [r11+20h]
0x1800035f3  mov     rsi, [r11+30h]
0x1800035f7  mov     rsp, r11
0x1800035fa  pop     r15
0x1800035fc  pop     r14
0x1800035fe  pop     rdi
0x1800035ff  retn
```
