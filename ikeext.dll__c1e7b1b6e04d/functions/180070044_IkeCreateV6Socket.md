# IkeCreateV6Socket

- ea: `0x180070044`
- end: `0x180070422`
- name: `IkeCreateV6Socket`
- size: `990`
- prototype: `__int64 __fastcall(u_short, SOCKET *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006f8e4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800017b0`
- `0x1800061ec`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x1800510ee`
- `0x18005bc40`
- `0x180070044`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800702bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070359`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800702bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070308`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180070359`
- `WS2_32!WSASocketW` at `0x1800702ac`
- `WS2_32!WSASocketW` at `0x1800702ac`
- `WS2_32!__imp_bind` at `0x18007034f`
- `WS2_32!__imp_bind` at `0x18007034f`
- `WS2_32!__imp_closesocket` at `0x1800703d8`
- `WS2_32!__imp_closesocket` at `0x1800703d8`
- `WS2_32!__imp_htons` at `0x180070336`
- `WS2_32!__imp_htons` at `0x180070336`
- `WS2_32!__imp_setsockopt` at `0x1800702fe`
- `WS2_32!__imp_setsockopt` at `0x18007038f`
- `WS2_32!__imp_setsockopt` at `0x1800703b9`
- `WS2_32!__imp_setsockopt` at `0x1800702fe`
- `WS2_32!__imp_setsockopt` at `0x18007038f`
- `WS2_32!__imp_setsockopt` at `0x1800703b9`

## string_xrefs

- `0x18007015a`: `Not bypassing LSPs for the V6 socket,             because regkey config prevents`
- `0x1800700a3`: `IkeCreateV6Socket`
- `0x1800703e0`: `IkeCreateV6Socket`
- `0x1800703ec`: `IkeCreateV6Socket`

## pseudocode

```c
__int64 __fastcall IkeCreateV6Socket(u_short a1, SOCKET *a2)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 MsTcpipProtocolInfo; // r14
  __int64 v7; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v9; // rcx
  int TlsMmLuid; // eax
  __int64 v11; // rcx
  const WCHAR *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  struct _WSAPROTOCOL_INFOW *v15; // r12
  __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  const WCHAR *v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  SOCKET v25; // rax
  SOCKET v26; // rbx
  DWORD LastError; // eax
  __int64 v28; // rcx
  const char *v29; // rdx
  char optval[4]; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v33; // [rsp+38h] [rbp-C8h] BYREF
  struct sockaddr name[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v35[640]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v36[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 *v37; // [rsp+300h] [rbp+200h]
  __int64 v38; // [rsp+308h] [rbp+208h]
  _BYTE v39[16]; // [rsp+310h] [rbp+210h] BYREF
  const char *v40; // [rsp+320h] [rbp+220h]
  __int64 v41; // [rsp+328h] [rbp+228h]

  memset(name, 0, 28);
  *(_DWORD *)optval = 1;
  memset_0(v35, 0, 0x274u);
  TraceLogHelper("IkeCreateV6Socket", 1);
  if ( ((__int64)gIkeExtGlobals[50].LockSemaphore & 2) != 0 )
  {
    MsTcpipProtocolInfo = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      TlsPeerAddr = IkeGetTlsPeerAddr(v4);
      TlsMmLuid = IkeGetTlsMmLuid(v9);
      WPP_SF_iS(v7, 12, (unsigned int)WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids, TlsMmLuid, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v33 = IkeGetTlsMmLuid(v4);
      v37 = &v33;
      v38 = 8;
      v12 = (const WCHAR *)IkeGetTlsPeerAddr(v11);
      tlgCreate1Sz_wchar_t((__int64)v39, v12);
      v41 = 81;
      v40 = "Not bypassing LSPs for the V6 socket,             because regkey config prevents";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)&dword_1801539AC,
        v13,
        v14,
        5,
        (__int64)v36);
    }
    v15 = 0;
  }
  else
  {
    MsTcpipProtocolInfo = IkeGetMsTcpipProtocolInfo(23, v3, v5, v35);
    if ( MsTcpipProtocolInfo )
      goto LABEL_29;
    v15 = (struct _WSAPROTOCOL_INFOW *)v35;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v18 = IkeGetTlsPeerAddr(v16);
      v20 = IkeGetTlsMmLuid(v19);
      WPP_SF_iS(v17, 13, (unsigned int)WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids, v20, v18);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v33 = IkeGetTlsMmLuid(v16);
      v37 = &v33;
      v38 = 8;
      v22 = (const WCHAR *)IkeGetTlsPeerAddr(v21);
      tlgCreate1Sz_wchar_t((__int64)v39, v22);
      v41 = 76;
      v40 = "Creating V6 socket directly on MS base provider.             Bypassing LSPs";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)&dword_18015396C,
        v23,
        v24,
        5,
        (__int64)v36);
    }
  }
  v25 = WSASocketW(23, 2, 17, v15, 0, 0);
  v26 = v25;
  if ( v25 == -1 )
  {
    LastError = GetLastError();
    v29 = "WSASocketW";
  }
  else
  {
    *(_DWORD *)optval = 1;
    if ( !setsockopt(v25, 0xFFFF, -5, optval, 4) )
    {
      name[0].sa_family = 23;
      *(IN6_ADDR *)&name[0].sa_data[6] = in6addr_any;
      *(_WORD *)name[0].sa_data = htons(a1);
      if ( bind(v26, name, 28) )
      {
        LastError = GetLastError();
        v29 = "bind";
        goto LABEL_18;
      }
      *(_DWORD *)optval = 1;
      if ( !setsockopt(v26, 41, 19, optval, 4) )
      {
        *(_DWORD *)optval = 1;
        if ( !setsockopt(v26, 41, 47, optval, 4) )
        {
          *a2 = v26;
          goto LABEL_26;
        }
      }
    }
    LastError = GetLastError();
    v29 = "setsockopt";
  }
LABEL_18:
  MsTcpipProtocolInfo = WfpReportSysErrorAsWinError(v28, v29, LastError, 1);
LABEL_26:
  if ( MsTcpipProtocolInfo && v26 )
    closesocket(v26);
LABEL_29:
  TraceLogHelper("IkeCreateV6Socket", 0);
  return IkeReturnError(MsTcpipProtocolInfo, "IkeCreateV6Socket");
}

```

## disassembly

```asm
0x180070044  mov     [rsp-8+arg_10], rbx
0x180070049  push    rbp
0x18007004a  push    rdi
0x18007004b  push    r12
0x18007004d  push    r13
0x18007004f  push    r14
0x180070051  lea     rbp, [rsp-240h]
0x180070059  sub     rsp, 340h
0x180070060  mov     rax, cs:__security_cookie
0x180070067  xor     rax, rsp
0x18007006a  mov     [rbp+260h+var_30], rax
0x180070071  xorps   xmm0, xmm0
0x180070074  mov     [rsp+360h+var_330], cx
0x180070079  mov     r13, rdx
0x18007007c  lea     rcx, [rsp+360h+var_300]; void *
0x180070081  movups  xmmword ptr [rsp+360h+name], xmm0
0x180070086  mov     ebx, 1
0x18007008b  xor     edx, edx; Val
0x18007008d  mov     r8d, 274h; Size
0x180070093  mov     dword ptr [rsp+360h+optval], ebx
0x180070097  movups  xmmword ptr [rsp+360h+name+0Ch], xmm0
0x18007009c  call    memset_0
0x1800700a1  mov     edx, ebx
0x1800700a3  lea     rcx, aIkecreatev6soc; "IkeCreateV6Socket"
0x1800700aa  call    TraceLogHelper
0x1800700af  mov     rax, cs:gIkeExtGlobals
0x1800700b6  mov     ebx, 17h
0x1800700bb  test    byte ptr [rax+7E8h], 2
0x1800700c2  jz      loc_1800701A2
0x1800700c8  xor     r14d, r14d
0x1800700cb  mov     rdi, cs:WPP_GLOBAL_Control
0x1800700d2  lea     rax, WPP_GLOBAL_Control
0x1800700d9  cmp     rdi, rax
0x1800700dc  jz      short loc_18007011A
0x1800700de  cmp     byte ptr [rdi+19h], 4
0x1800700e2  jb      short loc_18007011A
0x1800700e4  test    byte ptr [rdi+1Ch], 10h
0x1800700e8  jz      short loc_18007011A
0x1800700ea  mov     rdi, [rdi+10h]
0x1800700ee  call    IkeGetTlsPeerAddr
0x1800700f3  mov     rbx, rax
0x1800700f6  call    IkeGetTlsMmLuid
0x1800700fb  mov     r9, rax
0x1800700fe  mov     qword ptr [rsp+360h+g], rbx
0x180070103  lea     edx, [r14+0Ch]
0x180070107  mov     rcx, rdi
0x18007010a  lea     r8, WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids
0x180070111  call    WPP_SF_iS
0x180070116  lea     ebx, [r14+17h]
0x18007011a  mov     eax, cs:dword_180173278
0x180070120  cmp     eax, 4
0x180070123  jbe     short loc_18007019A
0x180070125  call    IkeGetTlsMmLuid
0x18007012a  mov     [rsp+360h+var_328], rax
0x18007012f  lea     rax, [rsp+360h+var_328]
0x180070134  mov     [rbp+260h+var_60], rax
0x18007013b  mov     [rbp+260h+var_58], 8
0x180070146  call    IkeGetTlsPeerAddr
0x18007014b  mov     rdx, rax
0x18007014e  lea     rcx, [rbp+260h+var_50]
0x180070155  call    _tlgCreate1Sz_wchar_t
0x18007015a  lea     rcx, aNotBypassingLs_0; "Not bypassing LSPs for the V6 socket,  "...
0x180070161  mov     [rbp+260h+var_38], 51h ; 'Q'
0x18007016c  lea     rax, [rbp+260h+var_80]
0x180070173  mov     [rbp+260h+var_40], rcx
0x18007017a  mov     qword ptr [rsp+360h+dwFlags], rax
0x18007017f  lea     rcx, dword_180173278
0x180070186  lea     rdx, dword_1801539AC
0x18007018d  mov     [rsp+360h+g], 5
0x180070195  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007019a  xor     r12d, r12d
0x18007019d  jmp     loc_18007028E
0x1800701a2  lea     r9, [rsp+360h+var_300]
0x1800701a7  mov     ecx, ebx
0x1800701a9  call    IkeGetMsTcpipProtocolInfo
0x1800701ae  mov     r14, rax
0x1800701b1  test    rax, rax
0x1800701b4  jnz     loc_1800703DE
0x1800701ba  lea     r12, [rsp+360h+var_300]
0x1800701bf  mov     rdi, cs:WPP_GLOBAL_Control
0x1800701c6  lea     rax, WPP_GLOBAL_Control
0x1800701cd  cmp     rdi, rax
0x1800701d0  jz      short loc_18007020E
0x1800701d2  cmp     byte ptr [rdi+19h], 4
0x1800701d6  jb      short loc_18007020E
0x1800701d8  test    byte ptr [rdi+1Ch], 10h
0x1800701dc  jz      short loc_18007020E
0x1800701de  mov     rdi, [rdi+10h]
0x1800701e2  call    IkeGetTlsPeerAddr
0x1800701e7  mov     rbx, rax
0x1800701ea  call    IkeGetTlsMmLuid
0x1800701ef  mov     r9, rax
0x1800701f2  mov     qword ptr [rsp+360h+g], rbx
0x1800701f7  lea     edx, [r14+0Dh]
0x1800701fb  mov     rcx, rdi
0x1800701fe  lea     r8, WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids
0x180070205  call    WPP_SF_iS
0x18007020a  lea     ebx, [r14+17h]
0x18007020e  mov     eax, cs:dword_180173278
0x180070214  cmp     eax, 4
0x180070217  jbe     short loc_18007028E
0x180070219  call    IkeGetTlsMmLuid
0x18007021e  mov     [rsp+360h+var_328], rax
0x180070223  lea     rax, [rsp+360h+var_328]
0x180070228  mov     [rbp+260h+var_60], rax
0x18007022f  mov     [rbp+260h+var_58], 8
0x18007023a  call    IkeGetTlsPeerAddr
0x18007023f  mov     rdx, rax
0x180070242  lea     rcx, [rbp+260h+var_50]
0x180070249  call    _tlgCreate1Sz_wchar_t
0x18007024e  lea     rcx, aCreatingV6Sock; "Creating V6 socket directly on MS base "...
0x180070255  mov     [rbp+260h+var_38], 4Ch ; 'L'
0x180070260  lea     rax, [rbp+260h+var_80]
0x180070267  mov     [rbp+260h+var_40], rcx
0x18007026e  mov     qword ptr [rsp+360h+dwFlags], rax
0x180070273  lea     rcx, dword_180173278
0x18007027a  lea     rdx, dword_18015396C
0x180070281  mov     [rsp+360h+g], 5
0x180070289  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18007028e  mov     edx, 2; type
0x180070293  mov     [rsp+360h+dwFlags], 0; dwFlags
0x18007029b  mov     r9, r12; lpProtocolInfo
0x18007029e  mov     [rsp+360h+g], 0; g
0x1800702a6  mov     ecx, ebx; af
0x1800702a8  lea     r8d, [rdx+0Fh]; protocol
0x1800702ac  call    cs:__imp_WSASocketW
0x1800702b2  mov     rbx, rax
0x1800702b5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800702b9  jnz     short loc_1800702DC
0x1800702bb  call    cs:__imp_GetLastError
0x1800702c1  lea     r9d, [rbx+2]
0x1800702c5  lea     rdx, aWsasocketw; "WSASocketW"
0x1800702cc  mov     r8d, eax
0x1800702cf  call    WfpReportSysErrorAsWinError
0x1800702d4  mov     r14, rax
0x1800702d7  jmp     loc_1800703CB
0x1800702dc  mov     edi, 1
0x1800702e1  mov     [rsp+360h+g], 4; optlen
0x1800702e9  lea     r9, [rsp+360h+optval]; optval
0x1800702ee  mov     dword ptr [rsp+360h+optval], edi
0x1800702f2  mov     edx, 0FFFFh; level
0x1800702f7  mov     rcx, rbx; s
0x1800702fa  lea     r8d, [rdi-6]; optname
0x1800702fe  call    cs:__imp_setsockopt
0x180070304  test    eax, eax
0x180070306  jz      short loc_18007031A
0x180070308  call    cs:__imp_GetLastError
0x18007030e  mov     r9d, edi
0x180070311  lea     rdx, aSetsockopt; "setsockopt"
0x180070318  jmp     short loc_1800702CC
0x18007031a  movups  xmm0, xmmword ptr cs:in6addr_any.u
0x180070321  movzx   ecx, [rsp+360h+var_330]; hostshort
0x180070326  mov     eax, 17h
0x18007032b  mov     word ptr [rsp+360h+name], ax
0x180070330  movdqu  xmmword ptr [rsp+360h+name+8], xmm0
0x180070336  call    cs:__imp_htons
0x18007033c  mov     r8d, 1Ch; namelen
0x180070342  lea     rdx, [rsp+360h+name]; name
0x180070347  mov     rcx, rbx; s
0x18007034a  mov     word ptr [rsp+360h+name+2], ax
0x18007034f  call    cs:__imp_bind
0x180070355  test    eax, eax
0x180070357  jz      short loc_18007036E
0x180070359  call    cs:__imp_GetLastError
0x18007035f  mov     r9d, edi
0x180070362  lea     rdx, aBind; "bind"
0x180070369  jmp     loc_1800702CC
0x18007036e  mov     r8d, 13h; optname
0x180070374  mov     dword ptr [rsp+360h+optval], edi
0x180070378  lea     r9, [rsp+360h+optval]; optval
0x18007037d  mov     [rsp+360h+g], 4; optlen
0x180070385  mov     rcx, rbx; s
0x180070388  lea     r12d, [r8+16h]
0x18007038c  mov     edx, r12d; level
0x18007038f  call    cs:__imp_setsockopt
0x180070395  test    eax, eax
0x180070397  jnz     loc_180070308
0x18007039d  lea     r9, [rsp+360h+optval]; optval
0x1800703a2  mov     dword ptr [rsp+360h+optval], edi
0x1800703a6  lea     r8d, [r12+6]; optname
0x1800703ab  mov     [rsp+360h+g], 4; optlen
0x1800703b3  mov     edx, r12d; level
0x1800703b6  mov     rcx, rbx; s
0x1800703b9  call    cs:__imp_setsockopt
0x1800703bf  test    eax, eax
0x1800703c1  jnz     loc_180070308
0x1800703c7  mov     [r13+0], rbx
0x1800703cb  test    r14, r14
0x1800703ce  jz      short loc_1800703DE
0x1800703d0  test    rbx, rbx
0x1800703d3  jz      short loc_1800703DE
0x1800703d5  mov     rcx, rbx; s
0x1800703d8  call    cs:__imp_closesocket
0x1800703de  xor     edx, edx
0x1800703e0  lea     rcx, aIkecreatev6soc; "IkeCreateV6Socket"
0x1800703e7  call    TraceLogHelper
0x1800703ec  lea     rdx, aIkecreatev6soc; "IkeCreateV6Socket"
0x1800703f3  mov     rcx, r14
0x1800703f6  call    IkeReturnError
0x1800703fb  mov     rcx, [rbp+260h+var_30]
0x180070402  xor     rcx, rsp; StackCookie
0x180070405  call    __security_check_cookie
0x18007040a  mov     rbx, [rsp+360h+arg_10]
0x180070412  add     rsp, 340h
0x180070419  pop     r14
0x18007041b  pop     r13
0x18007041d  pop     r12
0x18007041f  pop     rdi
0x180070420  pop     rbp
0x180070421  retn
```
