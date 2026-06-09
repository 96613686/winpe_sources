# AllowAccessToStream(IStream *)

- ea: `0x180035014`
- end: `0x18003526a`
- name: `?AllowAccessToStream@@YAJPEAUIStream@@@Z`
- size: `598`
- prototype: `HRESULT __fastcall(IStream *pStream)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800354a0`

## callees

- `0x180002790`
- `0x18000b2f4`
- `0x180012770`
- `0x180035014`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800350b0`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003515a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180035203`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800350b0`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18003515a`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180035203`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003524b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18003524b`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180035030`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180035030`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AllowAccessToStream(IStream *pStream)
{
  HRESULT v2; // eax
  int v3; // ebx
  HRESULT v4; // eax
  int v5; // edi
  HRESULT v6; // eax
  int v7; // edi
  HRESULT v8; // eax
  ATL::CComPtr<ISequentialStream> spSequentialStream; // [rsp+40h] [rbp-38h] BYREF

  v2 = CoImpersonateClient();
  v3 = 0;
  if ( v2 != -2147417833 )
    v3 = v2;
  if ( v3 >= 0 )
  {
    v4 = CoSetProxyBlanket(pStream, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
    v3 = v4;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xBu, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids, v4);
    }
    if ( (int)(v3 + 0x80000000) < 0 || v3 == -2147467262 )
    {
      spSequentialStream.p = 0;
      v5 = pStream->QueryInterface(pStream, &GUID_00000000_0000_0000_c000_000000000046, (void **)&spSequentialStream);
      if ( v5 >= 0 )
      {
        v6 = CoSetProxyBlanket(spSequentialStream.p, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
        v5 = v6;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xCu, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids, v6);
        }
      }
      v3 = 0;
      if ( v5 != -2147467262 )
        v3 = v5;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spSequentialStream);
      if ( v3 >= 0 )
      {
        spSequentialStream.p = 0;
        v7 = pStream->QueryInterface(pStream, &GUID_0c733a30_2a1c_11ce_ade5_00aa0044773d, (void **)&spSequentialStream);
        if ( v7 >= 0 )
        {
          v8 = CoSetProxyBlanket(spSequentialStream.p, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
          v7 = v8;
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xDu, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids, v8);
          }
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&spSequentialStream);
        v3 = 0;
        if ( v7 != -2147467262 )
          v3 = v7;
      }
    }
    CoRevertToSelf();
  }
  else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
         && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xAu, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids, v3);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180035014  push    rbx
0x180035016  push    rsi
0x180035017  push    rdi
0x180035018  push    r14
0x18003501a  sub     rsp, 58h
0x18003501e  mov     rax, cs:__security_cookie
0x180035025  xor     rax, rsp
0x180035028  mov     [rsp+78h+var_30], rax
0x18003502d  mov     r14, pStream
0x180035030  call    cs:__imp_CoImpersonateClient
0x180035036  xor     ebx, ebx
0x180035038  cmp     eax, 80010117h
0x18003503d  cmovnz  ebx, eax
0x180035040  test    ebx, ebx
0x180035042  jns     short loc_180035082
0x180035044  lea     rsi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003504b  mov     pStream, cs:WPP_GLOBAL_Control
0x180035052  cmp     pStream, rsi
0x180035055  jz      loc_180035251
0x18003505b  test    byte ptr [pStream+1Ch], 2
0x18003505f  jz      loc_180035251
0x180035065  mov     edx, 0Ah; id
0x18003506a  mov     r9d, ebx; _a1
0x18003506d  lea     r8, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids; TraceGuid
0x180035074  mov     pStream, [pStream+10h]; Logger
0x180035078  call    WPP_SF_d
0x18003507d  jmp     loc_180035251
0x180035082  mov     [rsp+78h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18003508a  mov     [rsp+78h+pAuthInfo], 0; pAuthInfo
0x180035093  mov     [rsp+78h+dwImpLevel], 3; dwImpLevel
0x18003509b  mov     [rsp+78h+dwAuthnLevel], 0; dwAuthnLevel
0x1800350a3  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800350a7  xor     r8d, r8d; dwAuthzSvc
0x1800350aa  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800350ad  mov     pStream, r14; pProxy
0x1800350b0  call    cs:__imp_CoSetProxyBlanket
0x1800350b6  mov     ebx, eax
0x1800350b8  lea     rsi, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800350bf  mov     pStream, cs:WPP_GLOBAL_Control
0x1800350c6  cmp     pStream, rsi
0x1800350c9  jz      short loc_1800350E9
0x1800350cb  test    byte ptr [pStream+1Ch], 10h
0x1800350cf  jz      short loc_1800350E9
0x1800350d1  mov     edx, 0Bh; id
0x1800350d6  mov     r9d, eax; _a1
0x1800350d9  lea     r8, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids; TraceGuid
0x1800350e0  mov     pStream, [pStream+10h]; Logger
0x1800350e4  call    WPP_SF_d
0x1800350e9  mov     ecx, 80000000h
0x1800350ee  lea     eax, [rbx+pStream]
0x1800350f1  test    ecx, eax
0x1800350f3  jnz     short loc_180035101
0x1800350f5  cmp     ebx, 80004002h
0x1800350fb  jnz     loc_18003524B
0x180035101  mov     [rsp+78h+spSequentialStream.p], 0
0x18003510a  mov     rax, [r14]
0x18003510d  lea     r8, [rsp+78h+spSequentialStream]
0x180035112  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180035119  mov     pStream, r14
0x18003511c  mov     rax, [rax]
0x18003511f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035124  mov     edi, eax
0x180035126  test    eax, eax
0x180035128  js      short loc_18003518D
0x18003512a  mov     [rsp+78h+dwCapabilities], 20h ; ' '; dwCapabilities
0x180035132  mov     [rsp+78h+pAuthInfo], 0; pAuthInfo
0x18003513b  mov     [rsp+78h+dwImpLevel], 3; dwImpLevel
0x180035143  mov     [rsp+78h+dwAuthnLevel], 0; dwAuthnLevel
0x18003514b  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18003514f  xor     r8d, r8d; dwAuthzSvc
0x180035152  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x180035155  mov     pStream, [rsp+78h+spSequentialStream.p]; pProxy
0x18003515a  call    cs:__imp_CoSetProxyBlanket
0x180035160  mov     edi, eax
0x180035162  mov     pStream, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180035169  cmp     pStream, rsi
0x18003516c  jz      short loc_18003518D
0x18003516e  test    byte ptr [pStream+1Ch], 10h
0x180035172  jz      short loc_18003518D
0x180035174  mov     edx, 0Ch; id
0x180035179  mov     r9d, eax; _a1
0x18003517c  lea     r8, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids; TraceGuid
0x180035183  mov     pStream, [pStream+10h]; Logger
0x180035187  call    WPP_SF_d
0x18003518c  nop
0x18003518d  xor     ebx, ebx
0x18003518f  cmp     edi, 80004002h
0x180035195  cmovnz  ebx, edi
0x180035198  lea     pStream, [rsp+78h+spSequentialStream]; this
0x18003519d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800351a2  test    ebx, ebx
0x1800351a4  js      loc_18003524B
0x1800351aa  mov     [rsp+78h+spSequentialStream.p], 0
0x1800351b3  mov     rax, [r14]
0x1800351b6  lea     r8, [rsp+78h+spSequentialStream]
0x1800351bb  lea     rdx, _GUID_0c733a30_2a1c_11ce_ade5_00aa0044773d
0x1800351c2  mov     pStream, r14
0x1800351c5  mov     rax, [rax]
0x1800351c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800351cd  mov     edi, eax
0x1800351cf  test    eax, eax
0x1800351d1  js      short loc_180035236
0x1800351d3  mov     [rsp+78h+dwCapabilities], 20h ; ' '; dwCapabilities
0x1800351db  mov     [rsp+78h+pAuthInfo], 0; pAuthInfo
0x1800351e4  mov     [rsp+78h+dwImpLevel], 3; dwImpLevel
0x1800351ec  mov     [rsp+78h+dwAuthnLevel], 0; dwAuthnLevel
0x1800351f4  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x1800351f8  xor     r8d, r8d; dwAuthzSvc
0x1800351fb  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x1800351fe  mov     pStream, [rsp+78h+spSequentialStream.p]; pProxy
0x180035203  call    cs:__imp_CoSetProxyBlanket
0x180035209  mov     edi, eax
0x18003520b  mov     pStream, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180035212  cmp     pStream, rsi
0x180035215  jz      short loc_180035236
0x180035217  test    byte ptr [pStream+1Ch], 10h
0x18003521b  jz      short loc_180035236
0x18003521d  mov     edx, 0Dh; id
0x180035222  mov     r9d, eax; _a1
0x180035225  lea     r8, WPP_115e792b689b3d45a14efe9813a3f1ca_Traceguids; TraceGuid
0x18003522c  mov     pStream, [pStream+10h]; Logger
0x180035230  call    WPP_SF_d
0x180035235  nop
0x180035236  lea     pStream, [rsp+78h+spSequentialStream]; this
0x18003523b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180035240  xor     ebx, ebx
0x180035242  cmp     edi, 80004002h
0x180035248  cmovnz  ebx, edi
0x18003524b  call    cs:__imp_CoRevertToSelf
0x180035251  mov     eax, ebx
0x180035253  mov     pStream, [rsp+78h+var_30]
0x180035258  xor     pStream, rsp; StackCookie
0x18003525b  call    __security_check_cookie
0x180035260  add     rsp, 58h
0x180035264  pop     r14
0x180035266  pop     rdi
0x180035267  pop     rsi
0x180035268  pop     rbx
0x180035269  retn
```
