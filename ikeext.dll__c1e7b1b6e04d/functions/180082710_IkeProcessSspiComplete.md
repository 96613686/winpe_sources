# IkeProcessSspiComplete

- ea: `0x180082710`
- end: `0x180082b9e`
- name: `IkeProcessSspiComplete`
- size: `1166`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800825a4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x180002a10`
- `0x1800061ec`
- `0x180008388`
- `0x180025cfc`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x18004d15c`
- `0x180050850`
- `0x18005bc40`
- `0x180073048`
- `0x18007ed08`
- `0x18007efdc`
- `0x18007f66c`
- `0x180080058`
- `0x18008073c`
- `0x180082710`
- `0x180084c50`
- `0x1800942e8`

## import_xrefs

- `SspiCli!QueryContextAttributesW` at `0x180082860`
- `SspiCli!QueryContextAttributesW` at `0x180082860`

## string_xrefs

- `0x180082748`: `IkeProcessSspiComplete`
- `0x18008286d`: `IkeProcessSspiComplete`
- `0x180082aa7`: `IkeProcessSspiComplete`
- `0x180082b5b`: `IkeProcessSspiComplete`
- `0x180082b67`: `IkeProcessSspiComplete`
- `0x18008296f`: `IkeGetPeerToken`
- `0x18008291c`: `Calling IkeGetPeerToken`
- `0x1800827dc`: `SSPI auth complete`
- `0x180082a17`: `Got Peer Token`

## pseudocode

```c
__int64 __fastcall IkeProcessSspiComplete(__int64 a1, __int64 a2)
{
  __int64 v2; // r15
  int v5; // r12d
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v9; // rcx
  int TlsMmLuid; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rcx
  __int64 IsAnonymous; // rbx
  unsigned int ContextAttributesW; // eax
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rax
  int v25; // r8d
  int v26; // r9d
  __int64 PeerTokenInitiator; // rax
  __int64 v28; // rcx
  __int64 v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rax
  int v35; // r8d
  _QWORD *v36; // rcx
  __int64 v37; // rcx
  int v38; // edx
  unsigned int v39; // r9d
  int v41; // [rsp+30h] [rbp-39h] BYREF
  __int64 v42; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v43[32]; // [rsp+40h] [rbp-29h] BYREF
  __int64 *v44; // [rsp+60h] [rbp-9h]
  __int64 v45; // [rsp+68h] [rbp-1h]
  _BYTE v46[16]; // [rsp+70h] [rbp+7h] BYREF
  const char *v47; // [rsp+80h] [rbp+17h]
  __int64 v48; // [rsp+88h] [rbp+1Fh]

  v2 = 0;
  v5 = 0;
  v41 = 0;
  TraceLogHelper("IkeProcessSspiComplete", 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v6);
    TlsMmLuid = IkeGetTlsMmLuid(v9);
    WPP_SF_iS(v7, 35, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, TlsMmLuid, TlsPeerAddr);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v42 = IkeGetTlsMmLuid(v6);
    v44 = &v42;
    v45 = 8;
    v12 = IkeGetTlsPeerAddr(v11);
    tlgCreate1Sz_wchar_t(v46, v12);
    v48 = 19;
    v47 = "SSPI auth complete";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)byte_1801558DD,
      v13,
      v14,
      5,
      (__int64)v43);
  }
  if ( !(unsigned int)IkeIsSslAuth(*(unsigned int *)(a2 + 88)) )
    goto LABEL_14;
  IsAnonymous = IkeImpersonate(a1, a2);
  if ( !IsAnonymous )
  {
    v5 = 1;
    if ( (*(_DWORD *)(a2 + 72) & 0x800000) == 0 || (*(_BYTE *)(a1 + 592) & 2) == 0 )
    {
      ContextAttributesW = QueryContextAttributesW(
                             (PCtxtHandle)(a2 + 24),
                             0x53u,
                             (void *)(*(_QWORD *)(a2 + 104) + 16LL));
      if ( ContextAttributesW )
      {
        IsAnonymous = WfpReportSysErrorAsWinError(v18, "IkeProcessSspiComplete", ContextAttributesW, 1);
        goto LABEL_45;
      }
      IsAnonymous = IkeVerifyPeerCertChainAuthIp(a1, a2);
      if ( IsAnonymous )
        goto LABEL_45;
    }
LABEL_14:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v19 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v20 = IkeGetTlsPeerAddr(v15);
      v22 = IkeGetTlsMmLuid(v21);
      WPP_SF_iS(v19, 36, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v22, v20);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v42 = IkeGetTlsMmLuid(v15);
      v44 = &v42;
      v45 = 8;
      v24 = IkeGetTlsPeerAddr(v23);
      tlgCreate1Sz_wchar_t(v46, v24);
      v48 = 24;
      v47 = "Calling IkeGetPeerToken";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)byte_180155823,
        v25,
        v26,
        5,
        (__int64)v43);
    }
    if ( (*(_BYTE *)(a1 + 592) & 1) != 0 )
      PeerTokenInitiator = IkeGetPeerTokenInitiator(a1, a2);
    else
      PeerTokenInitiator = IkeGetPeerTokenResponder(a1, a2);
    IsAnonymous = IkeReturnError(PeerTokenInitiator, "IkeGetPeerToken");
    if ( !IsAnonymous )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v29 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v30 = IkeGetTlsPeerAddr(v28);
        v32 = IkeGetTlsMmLuid(v31);
        WPP_SF_iS(v29, 37, (unsigned int)WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids, v32, v30);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v42 = IkeGetTlsMmLuid(v28);
        v44 = &v42;
        v45 = 8;
        v34 = IkeGetTlsPeerAddr(v33);
        tlgCreate1Sz_wchar_t(v46, v34);
        v48 = 15;
        v47 = "Got Peer Token";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)byte_1801557E5,
          v35,
          (unsigned int)"Got Peer Token",
          5,
          (__int64)v43);
      }
      if ( (*(_DWORD *)(a2 + 72) & 0x100000) != 0 )
        v36 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 1096) + 24LL) + 232LL);
      else
        v36 = (_QWORD *)(a1 + 984);
      IsAnonymous = IkeIsAnonymous(*v36, &v41);
      if ( !IsAnonymous )
      {
        if ( (*(_BYTE *)(a1 + 592) & 2) == 0
          || !v41
          || (v37 = *(unsigned int *)(a2 + 88), (_DWORD)v37 == 3)
          || (unsigned int)IkeIsSslAuth(v37) )
        {
          IsAnonymous = IkeGetSspiNames(v37, a2);
          if ( !IsAnonymous )
          {
            IkeFreeErrorList(a1 + 1040);
            IsAnonymous = IkeClassifyKMAuthorization(a1, a2);
            if ( !IsAnonymous )
            {
              *(_DWORD *)(a2 + 72) |= 2u;
              if ( (unsigned int)IkeIsSslAuth(*(unsigned int *)(a2 + 88)) )
              {
                if ( (*(_BYTE *)(a1 + 592) & 2) != 0 )
                  *(_DWORD *)(a2 + 72) = v38 & 0xFFF7FFFD | 0x80000;
              }
            }
          }
        }
        else
        {
          IsAnonymous = WfpReportSysErrorAsWinError(v37, "IkeProcessSspiComplete", 87, 1);
        }
      }
    }
    if ( !v5 )
    {
LABEL_46:
      if ( !IsAnonymous )
        goto LABEL_50;
      goto LABEL_47;
    }
LABEL_45:
    v2 = IkeRevertImpersonation(a2);
    goto LABEL_46;
  }
LABEL_47:
  v39 = (unsigned __int16)IsAnonymous;
  if ( (IsAnonymous & 0x1FFF0000) != 0x70000 )
    v39 = IsAnonymous;
  IsAnonymous = SetSspiError(a2, v39, 1);
LABEL_50:
  if ( v2 && !IsAnonymous )
    IsAnonymous = v2;
  TraceLogHelper("IkeProcessSspiComplete", 0);
  return IkeReturnError(IsAnonymous, "IkeProcessSspiComplete");
}

```

## disassembly

```asm
0x180082710  mov     [rsp-8+arg_10], rbx
0x180082715  mov     [rsp-8+arg_18], rsi
0x18008271a  push    rbp
0x18008271b  push    rdi
0x18008271c  push    r12
0x18008271e  push    r14
0x180082720  push    r15
0x180082722  lea     rbp, [rsp-37h]
0x180082727  sub     rsp, 0A0h
0x18008272e  mov     rax, cs:__security_cookie
0x180082735  xor     rax, rsp
0x180082738  mov     [rbp+57h+var_30], rax
0x18008273c  xor     r15d, r15d
0x18008273f  mov     rsi, rdx
0x180082742  mov     r14, rcx
0x180082745  xor     r12d, r12d
0x180082748  lea     rcx, aIkeprocesssspi_1; "IkeProcessSspiComplete"
0x18008274f  mov     [rbp+57h+var_90], r12d
0x180082753  lea     edx, [r15+1]
0x180082757  call    TraceLogHelper
0x18008275c  mov     rdi, cs:WPP_GLOBAL_Control
0x180082763  lea     rax, WPP_GLOBAL_Control
0x18008276a  cmp     rdi, rax
0x18008276d  jz      short loc_1800827A7
0x18008276f  cmp     byte ptr [rdi+19h], 4
0x180082773  jb      short loc_1800827A7
0x180082775  test    byte ptr [rdi+1Ch], 10h
0x180082779  jz      short loc_1800827A7
0x18008277b  mov     rdi, [rdi+10h]
0x18008277f  call    IkeGetTlsPeerAddr
0x180082784  mov     rbx, rax
0x180082787  call    IkeGetTlsMmLuid
0x18008278c  mov     r9, rax
0x18008278f  mov     [rsp+0C0h+var_A0], rbx
0x180082794  lea     edx, [r15+23h]
0x180082798  mov     rcx, rdi
0x18008279b  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x1800827a2  call    WPP_SF_iS
0x1800827a7  mov     eax, cs:dword_180173278
0x1800827ad  cmp     eax, 4
0x1800827b0  jbe     short loc_180082813
0x1800827b2  call    IkeGetTlsMmLuid
0x1800827b7  mov     [rbp+57h+var_88], rax
0x1800827bb  lea     rax, [rbp+57h+var_88]
0x1800827bf  mov     [rbp+57h+var_60], rax
0x1800827c3  mov     [rbp+57h+var_58], 8
0x1800827cb  call    IkeGetTlsPeerAddr
0x1800827d0  mov     rdx, rax
0x1800827d3  lea     rcx, [rbp+57h+var_50]
0x1800827d7  call    _tlgCreate1Sz_wchar_t
0x1800827dc  lea     rcx, aSspiAuthComple; "SSPI auth complete"
0x1800827e3  mov     [rbp+57h+var_38], 13h
0x1800827eb  lea     rax, [rbp+57h+var_80]
0x1800827ef  mov     [rbp+57h+var_40], rcx
0x1800827f3  mov     [rsp+0C0h+var_98], rax
0x1800827f8  lea     rcx, dword_180173278
0x1800827ff  lea     rdx, byte_1801558DD
0x180082806  mov     dword ptr [rsp+0C0h+var_A0], 5
0x18008280e  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180082813  mov     ecx, [rsi+58h]
0x180082816  call    IkeIsSslAuth
0x18008281b  test    eax, eax
0x18008281d  jz      short loc_18008289B
0x18008281f  mov     rdx, rsi
0x180082822  mov     rcx, r14
0x180082825  call    IkeImpersonate
0x18008282a  mov     rbx, rax
0x18008282d  test    rax, rax
0x180082830  jnz     loc_180082B23
0x180082836  test    dword ptr [rsi+48h], 800000h
0x18008283d  lea     ebx, [rax+1]
0x180082840  mov     r12d, ebx
0x180082843  jz      short loc_18008284F
0x180082845  test    byte ptr [r14+250h], 2
0x18008284d  jnz     short loc_18008289B
0x18008284f  mov     r8, [rsi+68h]
0x180082853  lea     rcx, [rsi+18h]; phContext
0x180082857  add     r8, 10h; pBuffer
0x18008285b  mov     edx, 53h ; 'S'; ulAttribute
0x180082860  call    cs:__imp_QueryContextAttributesW
0x180082866  test    eax, eax
0x180082868  jz      short loc_180082884
0x18008286a  mov     r9d, ebx
0x18008286d  lea     rdx, aIkeprocesssspi_1; "IkeProcessSspiComplete"
0x180082874  mov     r8d, eax
0x180082877  call    WfpReportSysErrorAsWinError
0x18008287c  mov     rbx, rax
0x18008287f  jmp     loc_180082B13
0x180082884  mov     rdx, rsi
0x180082887  mov     rcx, r14
0x18008288a  call    IkeVerifyPeerCertChainAuthIp
0x18008288f  mov     rbx, rax
0x180082892  test    rax, rax
0x180082895  jnz     loc_180082B13
0x18008289b  mov     rdi, cs:WPP_GLOBAL_Control
0x1800828a2  lea     rax, WPP_GLOBAL_Control
0x1800828a9  cmp     rdi, rax
0x1800828ac  jz      short loc_1800828E7
0x1800828ae  cmp     byte ptr [rdi+19h], 4
0x1800828b2  jb      short loc_1800828E7
0x1800828b4  test    byte ptr [rdi+1Ch], 10h
0x1800828b8  jz      short loc_1800828E7
0x1800828ba  mov     rdi, [rdi+10h]
0x1800828be  call    IkeGetTlsPeerAddr
0x1800828c3  mov     rbx, rax
0x1800828c6  call    IkeGetTlsMmLuid
0x1800828cb  mov     r9, rax
0x1800828ce  mov     [rsp+0C0h+var_A0], rbx
0x1800828d3  mov     edx, 24h ; '$'
0x1800828d8  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x1800828df  mov     rcx, rdi
0x1800828e2  call    WPP_SF_iS
0x1800828e7  mov     eax, cs:dword_180173278
0x1800828ed  cmp     eax, 4
0x1800828f0  jbe     short loc_180082953
0x1800828f2  call    IkeGetTlsMmLuid
0x1800828f7  mov     [rbp+57h+var_88], rax
0x1800828fb  lea     rax, [rbp+57h+var_88]
0x1800828ff  mov     [rbp+57h+var_60], rax
0x180082903  mov     [rbp+57h+var_58], 8
0x18008290b  call    IkeGetTlsPeerAddr
0x180082910  mov     rdx, rax
0x180082913  lea     rcx, [rbp+57h+var_50]
0x180082917  call    _tlgCreate1Sz_wchar_t
0x18008291c  lea     rcx, aCallingIkegetp; "Calling IkeGetPeerToken"
0x180082923  mov     [rbp+57h+var_38], 18h
0x18008292b  lea     rax, [rbp+57h+var_80]
0x18008292f  mov     [rbp+57h+var_40], rcx
0x180082933  mov     [rsp+0C0h+var_98], rax
0x180082938  lea     rcx, dword_180173278
0x18008293f  lea     rdx, byte_180155823
0x180082946  mov     dword ptr [rsp+0C0h+var_A0], 5
0x18008294e  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180082953  test    byte ptr [r14+250h], 1
0x18008295b  mov     rdx, rsi
0x18008295e  mov     rcx, r14
0x180082961  jz      short loc_18008296A
0x180082963  call    IkeGetPeerTokenInitiator
0x180082968  jmp     short loc_18008296F
0x18008296a  call    IkeGetPeerTokenResponder
0x18008296f  lea     rdx, aIkegetpeertoke; "IkeGetPeerToken"
0x180082976  mov     rcx, rax
0x180082979  call    IkeReturnError
0x18008297e  mov     rbx, rax
0x180082981  test    rax, rax
0x180082984  jnz     loc_180082B0E
0x18008298a  mov     rdi, cs:WPP_GLOBAL_Control
0x180082991  lea     rax, WPP_GLOBAL_Control
0x180082998  cmp     rdi, rax
0x18008299b  jz      short loc_1800829D6
0x18008299d  cmp     byte ptr [rdi+19h], 4
0x1800829a1  jb      short loc_1800829D6
0x1800829a3  test    byte ptr [rdi+1Ch], 10h
0x1800829a7  jz      short loc_1800829D6
0x1800829a9  mov     rdi, [rdi+10h]
0x1800829ad  call    IkeGetTlsPeerAddr
0x1800829b2  mov     rbx, rax
0x1800829b5  call    IkeGetTlsMmLuid
0x1800829ba  mov     r9, rax
0x1800829bd  mov     [rsp+0C0h+var_A0], rbx
0x1800829c2  mov     edx, 25h ; '%'
0x1800829c7  lea     r8, WPP_2b272cd36ddf34e915799d0ae4cceb51_Traceguids
0x1800829ce  mov     rcx, rdi
0x1800829d1  call    WPP_SF_iS
0x1800829d6  mov     eax, cs:dword_180173278
0x1800829dc  cmp     eax, 4
0x1800829df  jbe     short loc_180082A42
0x1800829e1  call    IkeGetTlsMmLuid
0x1800829e6  mov     [rbp+57h+var_88], rax
0x1800829ea  lea     rax, [rbp+57h+var_88]
0x1800829ee  mov     [rbp+57h+var_60], rax
0x1800829f2  mov     [rbp+57h+var_58], 8
0x1800829fa  call    IkeGetTlsPeerAddr
0x1800829ff  mov     rdx, rax
0x180082a02  lea     rcx, [rbp+57h+var_50]
0x180082a06  call    _tlgCreate1Sz_wchar_t
0x180082a0b  lea     rax, [rbp+57h+var_80]
0x180082a0f  mov     [rbp+57h+var_38], 0Fh
0x180082a17  lea     r9, aGotPeerToken; "Got Peer Token"
0x180082a1e  mov     [rsp+0C0h+var_98], rax
0x180082a23  lea     rdx, byte_1801557E5
0x180082a2a  mov     dword ptr [rsp+0C0h+var_A0], 5
0x180082a32  lea     rcx, dword_180173278
0x180082a39  mov     [rbp+57h+var_40], r9
0x180082a3d  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180082a42  test    dword ptr [rsi+48h], 100000h
0x180082a49  jz      short loc_180082A5F
0x180082a4b  mov     rax, [r14+448h]
0x180082a52  mov     rcx, [rax+18h]
0x180082a56  add     rcx, 0E8h
0x180082a5d  jmp     short loc_180082A66
0x180082a5f  lea     rcx, [r14+3D8h]
0x180082a66  mov     rcx, [rcx]
0x180082a69  lea     rdx, [rbp+57h+var_90]
0x180082a6d  call    IkeIsAnonymous
0x180082a72  mov     rbx, rax
0x180082a75  test    rax, rax
0x180082a78  jnz     loc_180082B0E
0x180082a7e  test    byte ptr [r14+250h], 2
0x180082a86  jz      short loc_180082AB8
0x180082a88  cmp     [rbp+57h+var_90], r15d
0x180082a8c  jz      short loc_180082AB8
0x180082a8e  mov     ecx, [rsi+58h]
0x180082a91  cmp     ecx, 3
0x180082a94  jz      short loc_180082AB8
0x180082a96  call    IkeIsSslAuth
0x180082a9b  test    eax, eax
0x180082a9d  jnz     short loc_180082AB8
0x180082a9f  lea     r9d, [rbx+1]
0x180082aa3  lea     r8d, [rbx+57h]
0x180082aa7  lea     rdx, aIkeprocesssspi_1; "IkeProcessSspiComplete"
0x180082aae  call    WfpReportSysErrorAsWinError
0x180082ab3  mov     rbx, rax
0x180082ab6  jmp     short loc_180082B0E
0x180082ab8  mov     rdx, rsi
0x180082abb  call    IkeGetSspiNames
0x180082ac0  mov     rbx, rax
0x180082ac3  test    rax, rax
0x180082ac6  jnz     short loc_180082B0E
0x180082ac8  lea     rcx, [r14+410h]
0x180082acf  call    IkeFreeErrorList
0x180082ad4  mov     rdx, rsi
0x180082ad7  mov     rcx, r14
0x180082ada  call    IkeClassifyKMAuthorization
0x180082adf  mov     rbx, rax
0x180082ae2  test    rax, rax
0x180082ae5  jnz     short loc_180082B0E
0x180082ae7  or      dword ptr [rsi+48h], 2
0x180082aeb  mov     edx, [rsi+48h]
0x180082aee  mov     ecx, [rsi+58h]
0x180082af1  call    IkeIsSslAuth
0x180082af6  test    eax, eax
0x180082af8  jz      short loc_180082B0E
0x180082afa  test    byte ptr [r14+250h], 2
0x180082b02  jz      short loc_180082B0E
0x180082b04  and     edx, 0FFFFFFFDh
0x180082b07  bts     edx, 13h
0x180082b0b  mov     [rsi+48h], edx
0x180082b0e  test    r12d, r12d
0x180082b11  jz      short loc_180082B1E
0x180082b13  mov     rcx, rsi
0x180082b16  call    IkeRevertImpersonation
0x180082b1b  mov     r15, rax
0x180082b1e  test    rbx, rbx
0x180082b21  jz      short loc_180082B4D
0x180082b23  mov     edx, ebx
0x180082b25  movzx   r9d, bx
0x180082b29  and     edx, 1FFF0000h
0x180082b2f  mov     r8d, 1
0x180082b35  cmp     edx, 70000h
0x180082b3b  mov     rcx, rsi
0x180082b3e  cmovnz  r9d, ebx
0x180082b42  mov     edx, r9d
0x180082b45  call    SetSspiError
0x180082b4a  mov     rbx, rax
0x180082b4d  test    r15, r15
0x180082b50  jz      short loc_180082B59
0x180082b52  test    rbx, rbx
0x180082b55  cmovz   rbx, r15
0x180082b59  xor     edx, edx
0x180082b5b  lea     rcx, aIkeprocesssspi_1; "IkeProcessSspiComplete"
0x180082b62  call    TraceLogHelper
0x180082b67  lea     rdx, aIkeprocesssspi_1; "IkeProcessSspiComplete"
0x180082b6e  mov     rcx, rbx
0x180082b71  call    IkeReturnError
0x180082b76  mov     rcx, [rbp+57h+var_30]
0x180082b7a  xor     rcx, rsp; StackCookie
0x180082b7d  call    __security_check_cookie
0x180082b82  lea     r11, [rsp+0C0h+var_20]
0x180082b8a  mov     rbx, [r11+40h]
0x180082b8e  mov     rsi, [r11+48h]
0x180082b92  mov     rsp, r11
0x180082b95  pop     r15
0x180082b97  pop     r14
0x180082b99  pop     r12
0x180082b9b  pop     rdi
0x180082b9c  pop     rbp
0x180082b9d  retn
```
