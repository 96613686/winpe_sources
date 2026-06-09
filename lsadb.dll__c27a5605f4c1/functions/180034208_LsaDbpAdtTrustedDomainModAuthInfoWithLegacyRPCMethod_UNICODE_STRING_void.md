# LsaDbpAdtTrustedDomainModAuthInfoWithLegacyRPCMethod(_UNICODE_STRING *,void *)

- ea: `0x180034208`
- end: `0x1800345b8`
- name: `?LsaDbpAdtTrustedDomainModAuthInfoWithLegacyRPCMethod@@YAJPEAU_UNICODE_STRING@@PEAX@Z`
- size: `944`
- prototype: `int(struct _UNICODE_STRING *, void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d000`
- `0x18000e9f0`

## callees

- `0x180001670`
- `0x180001fb8`
- `0x180002234`
- `0x18000fd40`
- `0x180034208`
- `0x1800350e8`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18003431f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003431f`
- `RPCRT4!RpcStringBindingParseW` at `0x18003438c`
- `RPCRT4!RpcStringBindingParseW` at `0x18003438c`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180034369`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180034369`
- `RPCRT4!RpcBindingServerFromClient` at `0x180034355`
- `RPCRT4!RpcBindingServerFromClient` at `0x180034355`
- `RPCRT4!RpcBindingFree` at `0x180034549`
- `RPCRT4!RpcBindingFree` at `0x180034549`
- `RPCRT4!RpcStringFreeW` at `0x180034525`
- `RPCRT4!RpcStringFreeW` at `0x180034537`
- `RPCRT4!RpcStringFreeW` at `0x180034525`
- `RPCRT4!RpcStringFreeW` at `0x180034537`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180034313`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180034313`
- `LSASRV!LsapFreeLsaHeap` at `0x180034507`
- `LSASRV!LsapFreeLsaHeap` at `0x180034559`
- `LSASRV!LsapFreeLsaHeap` at `0x180034507`
- `LSASRV!LsapFreeLsaHeap` at `0x180034559`
- `LSASRV!LsapAdtWriteLog` at `0x1800344f0`
- `LSASRV!LsapAdtWriteLog` at `0x1800344f0`
- `LSASRV!LsapAuditFailed` at `0x180034513`
- `LSASRV!LsapAuditFailed` at `0x180034513`
- `LSASRV!LsapQueryClientInfo` at `0x1800342af`
- `LSASRV!LsapQueryClientInfo` at `0x1800342af`
- `ntdll!RtlInitUnicodeString` at `0x1800343a0`
- `ntdll!RtlInitUnicodeString` at `0x1800343a0`
- `ntdll!RtlLengthSid` at `0x180034408`
- `ntdll!RtlLengthSid` at `0x180034429`
- `ntdll!RtlLengthSid` at `0x180034497`
- `ntdll!RtlLengthSid` at `0x180034408`
- `ntdll!RtlLengthSid` at `0x180034429`
- `ntdll!RtlLengthSid` at `0x180034497`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x1800342e4`
- `ext-ms-win-security-lsaadt-l1-1-0!LsapAdtAuditingEnabledByLogonId` at `0x1800342e4`

## pseudocode

```c
__int64 __fastcall LsaDbpAdtTrustedDomainModAuthInfoWithLegacyRPCMethod(struct _UNICODE_STRING *a1, void *a2)
{
  __int128 v2; // rdi
  int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  RPC_STATUS v7; // eax
  int v8; // eax
  _BYTE v10[8]; // [rsp+30h] [rbp-D0h] BYREF
  PSID *v11; // [rsp+38h] [rbp-C8h] BYREF
  RPC_WSTR NetworkAddr; // [rsp+40h] [rbp-C0h] BYREF
  RPC_WSTR StringBinding; // [rsp+48h] [rbp-B8h] BYREF
  RPC_BINDING_HANDLE ServerBinding; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v16; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  _DWORD RpcCallAttributes[22]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v19; // [rsp+D8h] [rbp-28h]
  _DWORD v20[7]; // [rsp+F0h] [rbp-10h] BYREF
  ULONG v21; // [rsp+10Ch] [rbp+Ch]
  __int16 *v22; // [rsp+120h] [rbp+20h]
  int v23; // [rsp+128h] [rbp+28h]
  int v24; // [rsp+12Ch] [rbp+2Ch]
  struct _UNICODE_STRING *v25; // [rsp+140h] [rbp+40h]
  int v26; // [rsp+148h] [rbp+48h]
  int v27; // [rsp+14Ch] [rbp+4Ch]
  __int64 v28; // [rsp+150h] [rbp+50h]
  int v29; // [rsp+168h] [rbp+68h]
  int v30; // [rsp+16Ch] [rbp+6Ch]
  __int64 v31; // [rsp+180h] [rbp+80h]
  int v32; // [rsp+188h] [rbp+88h]
  ULONG v33; // [rsp+18Ch] [rbp+8Ch]
  __int64 v34; // [rsp+1A0h] [rbp+A0h]
  int v35; // [rsp+1A8h] [rbp+A8h]
  int v36; // [rsp+1ACh] [rbp+ACh]
  struct _UNICODE_STRING *p_DestinationString; // [rsp+1C0h] [rbp+C0h]
  int v38; // [rsp+1C8h] [rbp+C8h]
  int v39; // [rsp+1CCh] [rbp+CCh]
  struct _UNICODE_STRING *v40; // [rsp+1E0h] [rbp+E0h]

  *((_QWORD *)&v2 + 1) = a2;
  *(_QWORD *)&v2 = a1;
  memset_0(v20, 0, 0x418u);
  ServerBinding = 0;
  StringBinding = 0;
  NetworkAddr = 0;
  v16 = 0;
  DestinationString = 0;
  memset_0(RpcCallAttributes, 0, 0x70u);
  v15 = 0;
  v11 = 0;
  v10[0] = 0;
  if ( v2 == 0 )
  {
    v3 = -1073741811;
LABEL_30:
    LsapAuditFailed((unsigned int)v3);
    goto LABEL_31;
  }
  v3 = LsapQueryClientInfo(&v11, &v15);
  if ( v3 >= 0 )
  {
    if ( !(unsigned __int8)IsLsapAdtAuditingEnabledByLogonIdPresent(v5, v4, v6)
      || (v3 = LsapAdtAuditingEnabledByLogonId(141, &v15, 8, v10), v3 >= 0) )
    {
      if ( v10[0] )
      {
        RpcCallAttributes[0] = 2;
        RpcCallAttributes[1] = 64;
        v7 = RpcServerInqCallAttributesW(0, RpcCallAttributes);
        if ( v7 )
        {
LABEL_8:
          v3 = I_RpcMapWin32Status(v7);
          goto LABEL_27;
        }
        if ( !RpcCallAttributes[15] )
        {
          v3 = LsapTranslateRpcOpNumToUnicodeName(v19, &v16);
          if ( v3 >= 0 )
          {
            v7 = RpcBindingServerFromClient(0, &ServerBinding);
            if ( v7 )
              goto LABEL_8;
            v7 = RpcBindingToStringBindingW(ServerBinding, &StringBinding);
            if ( v7 )
              goto LABEL_8;
            v7 = RpcStringBindingParseW(StringBinding, 0, 0, &NetworkAddr, 0, 0);
            if ( v7 )
              goto LABEL_8;
            RtlInitUnicodeString(&DestinationString, NetworkAddr);
            if ( (_QWORD)v2 && *(_WORD *)(v2 + 2) < *(_WORD *)v2
              || DestinationString.MaximumLength < DestinationString.Length
              || v16.MaximumLength < v16.Length )
            {
              v3 = -1073741811;
            }
            else
            {
              v20[0] = 6;
              v20[4] = 524429;
              v20[1] = 6425;
              v20[2] = 7;
              v20[6] = 4;
              if ( *v11 )
              {
                v21 = RtlLengthSid(*v11);
                v22 = (__int16 *)*v11;
              }
              else
              {
                v21 = RtlLengthSid(&AdtpNullSid);
                v22 = &AdtpNullSid;
              }
              v23 = 1;
              v24 = LsaDbpSubsystemName.Length + 16;
              v25 = &LsaDbpSubsystemName;
              v28 = v15;
              v26 = 5;
              v27 = 8;
              if ( (_QWORD)v2 )
              {
                v8 = *(unsigned __int16 *)v2;
                v29 = 1;
                v30 = v8 + 16;
                v31 = v2;
              }
              if ( *((_QWORD *)&v2 + 1) )
              {
                v32 = 4;
                v33 = RtlLengthSid(*((PSID *)&v2 + 1));
                v34 = *((_QWORD *)&v2 + 1);
              }
              v35 = 1;
              v36 = DestinationString.Length + 16;
              p_DestinationString = &DestinationString;
              v38 = 1;
              v39 = v16.Length + 16;
              v40 = &v16;
              LsapAdtWriteLog(v20);
            }
          }
        }
      }
    }
  }
LABEL_27:
  if ( v11 )
    LsapFreeLsaHeap(v11, v4, v6);
  if ( v3 < 0 )
    goto LABEL_30;
LABEL_31:
  if ( NetworkAddr )
    RpcStringFreeW(&NetworkAddr);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( ServerBinding )
    RpcBindingFree(&ServerBinding);
  if ( v16.Buffer )
    LsapFreeLsaHeap(v16.Buffer, v4, v6);
  if ( v3 < 0 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_0574045cf7493b8415f464ba3c8a3fec_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180034208  mov     [rsp-8+arg_0], rbx
0x18003420d  mov     [rsp-8+arg_10], rsi
0x180034212  push    rbp
0x180034213  push    rdi
0x180034214  push    r13
0x180034216  push    r14
0x180034218  push    r15
0x18003421a  lea     rbp, [rsp-420h]
0x180034222  sub     rsp, 520h
0x180034229  mov     rax, cs:__security_cookie
0x180034230  xor     rax, rsp
0x180034233  mov     [rbp+440h+var_30], rax
0x18003423a  mov     rsi, rdx
0x18003423d  mov     rdi, rcx
0x180034240  xor     edx, edx; Val
0x180034242  lea     rcx, [rbp+440h+var_450]; void *
0x180034246  mov     r8d, 418h; Size
0x18003424c  call    memset_0
0x180034251  xor     r15d, r15d
0x180034254  lea     rcx, [rbp+440h+RpcCallAttributes]; void *
0x180034258  xorps   xmm0, xmm0
0x18003425b  mov     [rsp+540h+ServerBinding], r15
0x180034260  xorps   xmm1, xmm1
0x180034263  mov     [rsp+540h+StringBinding], r15
0x180034268  xor     edx, edx; Val
0x18003426a  mov     [rsp+540h+NetworkAddr], r15
0x18003426f  lea     r8d, [r15+70h]; Size
0x180034273  movups  xmmword ptr [rsp+540h+var_4E0.Length], xmm0
0x180034278  movups  xmmword ptr [rsp+540h+DestinationString.Length], xmm1
0x18003427d  call    memset_0
0x180034282  mov     [rsp+540h+var_4E8], r15
0x180034287  mov     [rsp+540h+var_508], r15
0x18003428c  mov     [rsp+540h+var_510], r15b
0x180034291  test    rdi, rdi
0x180034294  jnz     short loc_1800342A5
0x180034296  test    rsi, rsi
0x180034299  jnz     short loc_1800342A5
0x18003429b  mov     ebx, 0C000000Dh
0x1800342a0  jmp     loc_180034511
0x1800342a5  lea     rdx, [rsp+540h+var_4E8]
0x1800342aa  lea     rcx, [rsp+540h+var_508]
0x1800342af  call    cs:__imp_LsapQueryClientInfo
0x1800342b5  mov     ebx, eax
0x1800342b7  test    eax, eax
0x1800342b9  js      loc_1800344FD
0x1800342bf  call    IsLsapAdtAuditingEnabledByLogonIdPresent
0x1800342c4  mov     r13d, 8
0x1800342ca  mov     r14d, 8Dh
0x1800342d0  test    al, al
0x1800342d2  jz      short loc_1800342F4
0x1800342d4  lea     r9, [rsp+540h+var_510]
0x1800342d9  mov     r8d, r13d
0x1800342dc  lea     rdx, [rsp+540h+var_4E8]
0x1800342e1  mov     ecx, r14d
0x1800342e4  call    cs:__imp_LsapAdtAuditingEnabledByLogonId
0x1800342ea  mov     ebx, eax
0x1800342ec  test    eax, eax
0x1800342ee  js      loc_1800344FD
0x1800342f4  cmp     [rsp+540h+var_510], r15b
0x1800342f9  jz      loc_1800344FD
0x1800342ff  lea     rdx, [rbp+440h+RpcCallAttributes]; RpcCallAttributes
0x180034303  mov     [rbp+440h+RpcCallAttributes], 2
0x18003430a  xor     ecx, ecx; ClientBinding
0x18003430c  mov     [rbp+440h+var_4BC], 40h ; '@'
0x180034313  call    cs:__imp_RpcServerInqCallAttributesW
0x180034319  test    eax, eax
0x18003431b  jz      short loc_18003432C
0x18003431d  mov     ecx, eax; Status
0x18003431f  call    cs:__imp_I_RpcMapWin32Status
0x180034325  mov     ebx, eax
0x180034327  jmp     loc_1800344FD
0x18003432c  cmp     [rbp+440h+var_484], r15d
0x180034330  jnz     loc_1800344FD
0x180034336  movzx   ecx, [rbp+440h+var_468]; unsigned __int16
0x18003433a  lea     rdx, [rsp+540h+var_4E0]; struct _UNICODE_STRING *
0x18003433f  call    ?LsapTranslateRpcOpNumToUnicodeName@@YAJGPEAU_UNICODE_STRING@@@Z; LsapTranslateRpcOpNumToUnicodeName(ushort,_UNICODE_STRING *)
0x180034344  mov     ebx, eax
0x180034346  test    eax, eax
0x180034348  js      loc_1800344FD
0x18003434e  lea     rdx, [rsp+540h+ServerBinding]; ServerBinding
0x180034353  xor     ecx, ecx; ClientBinding
0x180034355  call    cs:__imp_RpcBindingServerFromClient
0x18003435b  test    eax, eax
0x18003435d  jnz     short loc_18003431D
0x18003435f  mov     rcx, [rsp+540h+ServerBinding]; Binding
0x180034364  lea     rdx, [rsp+540h+StringBinding]; StringBinding
0x180034369  call    cs:__imp_RpcBindingToStringBindingW
0x18003436f  test    eax, eax
0x180034371  jnz     short loc_18003431D
0x180034373  mov     rcx, [rsp+540h+StringBinding]; StringBinding
0x180034378  lea     r9, [rsp+540h+NetworkAddr]; NetworkAddr
0x18003437d  mov     [rsp+540h+NetworkOptions], r15; NetworkOptions
0x180034382  xor     r8d, r8d; Protseq
0x180034385  xor     edx, edx; ObjUuid
0x180034387  mov     [rsp+540h+Endpoint], r15; Endpoint
0x18003438c  call    cs:__imp_RpcStringBindingParseW
0x180034392  test    eax, eax
0x180034394  jnz     short loc_18003431D
0x180034396  mov     rdx, [rsp+540h+NetworkAddr]; SourceString
0x18003439b  lea     rcx, [rsp+540h+DestinationString]; DestinationString
0x1800343a0  call    cs:__imp_RtlInitUnicodeString
0x1800343a6  test    rdi, rdi
0x1800343a9  jz      short loc_1800343B8
0x1800343ab  movzx   eax, word ptr [rdi]
0x1800343ae  cmp     [rdi+2], ax
0x1800343b2  jb      loc_1800344F8
0x1800343b8  movzx   eax, [rsp+540h+DestinationString.Length]
0x1800343bd  cmp     [rsp+540h+DestinationString.MaximumLength], ax
0x1800343c2  jb      loc_1800344F8
0x1800343c8  movzx   eax, [rsp+540h+var_4E0.Length]
0x1800343cd  cmp     [rsp+540h+var_4E0.MaximumLength], ax
0x1800343d2  jb      loc_1800344F8
0x1800343d8  mov     rax, [rsp+540h+var_508]
0x1800343dd  mov     [rbp+440h+var_450], 6
0x1800343e4  mov     [rbp+440h+var_440], 8008Dh
0x1800343eb  mov     [rbp+440h+var_44C], 1919h
0x1800343f2  mov     [rbp+440h+var_448], 7
0x1800343f9  mov     [rbp+440h+var_438], 4
0x180034400  mov     rcx, [rax]; Sid
0x180034403  test    rcx, rcx
0x180034406  jz      short loc_18003441F
0x180034408  call    cs:__imp_RtlLengthSid
0x18003440e  mov     [rbp+440h+var_434], eax
0x180034411  mov     rax, [rsp+540h+var_508]
0x180034416  mov     rcx, [rax]
0x180034419  mov     [rbp+440h+var_420], rcx
0x18003441d  jmp     short loc_180034436
0x18003441f  lea     r14, AdtpNullSid
0x180034426  mov     rcx, r14; Sid
0x180034429  call    cs:__imp_RtlLengthSid
0x18003442f  mov     [rbp+440h+var_434], eax
0x180034432  mov     [rbp+440h+var_420], r14
0x180034436  movzx   eax, cs:?LsaDbpSubsystemName@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING LsaDbpSubsystemName ...
0x18003443d  mov     r14d, 1
0x180034443  add     eax, 10h
0x180034446  mov     [rbp+440h+var_418], r14d
0x18003444a  mov     [rbp+440h+var_414], eax
0x18003444d  lea     rax, ?LsaDbpSubsystemName@@3U_UNICODE_STRING@@A; _UNICODE_STRING LsaDbpSubsystemName
0x180034454  mov     [rbp+440h+var_400], rax
0x180034458  mov     rax, [rsp+540h+var_4E8]
0x18003445d  mov     [rbp+440h+var_3F0], rax
0x180034461  mov     [rbp+440h+var_3F8], 5
0x180034468  mov     [rbp+440h+var_3F4], r13d
0x18003446c  test    rdi, rdi
0x18003446f  jz      short loc_180034485
0x180034471  movzx   eax, word ptr [rdi]
0x180034474  add     eax, 10h
0x180034477  mov     [rbp+440h+var_3D8], r14d
0x18003447b  mov     [rbp+440h+var_3D4], eax
0x18003447e  mov     [rbp+440h+var_3C0], rdi
0x180034485  test    rsi, rsi
0x180034488  jz      short loc_1800344AA
0x18003448a  mov     rcx, rsi; Sid
0x18003448d  mov     [rbp+440h+var_3B8], 4
0x180034497  call    cs:__imp_RtlLengthSid
0x18003449d  mov     [rbp+440h+var_3B4], eax
0x1800344a3  mov     [rbp+440h+var_3A0], rsi
0x1800344aa  movzx   eax, [rsp+540h+DestinationString.Length]
0x1800344af  lea     rcx, [rbp+440h+var_450]
0x1800344b3  add     eax, 10h
0x1800344b6  mov     [rbp+440h+var_398], r14d
0x1800344bd  mov     [rbp+440h+var_394], eax
0x1800344c3  lea     rax, [rsp+540h+DestinationString]
0x1800344c8  mov     [rbp+440h+var_380], rax
0x1800344cf  movzx   eax, [rsp+540h+var_4E0.Length]
0x1800344d4  add     eax, 10h
0x1800344d7  mov     [rbp+440h+var_378], r14d
0x1800344de  mov     [rbp+440h+var_374], eax
0x1800344e4  lea     rax, [rsp+540h+var_4E0]
0x1800344e9  mov     [rbp+440h+var_360], rax
0x1800344f0  call    cs:__imp_LsapAdtWriteLog
0x1800344f6  jmp     short loc_1800344FD
0x1800344f8  mov     ebx, 0C000000Dh
0x1800344fd  mov     rcx, [rsp+540h+var_508]
0x180034502  test    rcx, rcx
0x180034505  jz      short loc_18003450D
0x180034507  call    cs:__imp_LsapFreeLsaHeap
0x18003450d  test    ebx, ebx
0x18003450f  jns     short loc_180034519
0x180034511  mov     ecx, ebx
0x180034513  call    cs:__imp_LsapAuditFailed
0x180034519  cmp     [rsp+540h+NetworkAddr], r15
0x18003451e  jz      short loc_18003452B
0x180034520  lea     rcx, [rsp+540h+NetworkAddr]; String
0x180034525  call    cs:__imp_RpcStringFreeW
0x18003452b  cmp     [rsp+540h+StringBinding], r15
0x180034530  jz      short loc_18003453D
0x180034532  lea     rcx, [rsp+540h+StringBinding]; String
0x180034537  call    cs:__imp_RpcStringFreeW
0x18003453d  cmp     [rsp+540h+ServerBinding], r15
0x180034542  jz      short loc_18003454F
0x180034544  lea     rcx, [rsp+540h+ServerBinding]; Binding
0x180034549  call    cs:__imp_RpcBindingFree
0x18003454f  mov     rcx, [rsp+540h+var_4E0.Buffer]
0x180034554  test    rcx, rcx
0x180034557  jz      short loc_18003455F
0x180034559  call    cs:__imp_LsapFreeLsaHeap
0x18003455f  test    ebx, ebx
0x180034561  jns     short loc_18003458B
0x180034563  mov     rcx, cs:WPP_GLOBAL_Control
0x18003456a  test    dword ptr [rcx+1Ch], 100h
0x180034571  jz      short loc_18003458B
0x180034573  mov     rcx, [rcx+10h]
0x180034577  lea     r8, WPP_0574045cf7493b8415f464ba3c8a3fec_Traceguids
0x18003457e  mov     edx, 0Ah
0x180034583  mov     r9d, ebx
0x180034586  call    WPP_SF_d
0x18003458b  mov     eax, ebx
0x18003458d  mov     rcx, [rbp+440h+var_30]
0x180034594  xor     rcx, rsp; StackCookie
0x180034597  call    __security_check_cookie
0x18003459c  lea     r11, [rsp+540h+var_20]
0x1800345a4  mov     rbx, [r11+30h]
0x1800345a8  mov     rsi, [r11+40h]
0x1800345ac  mov     rsp, r11
0x1800345af  pop     r15
0x1800345b1  pop     r14
0x1800345b3  pop     r13
0x1800345b5  pop     rdi
0x1800345b6  pop     rbp
0x1800345b7  retn
```
