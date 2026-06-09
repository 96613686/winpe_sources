# IkeCreateV4Socket

- ea: `0x18006fc4c`
- end: `0x18007003d`
- name: `IkeCreateV4Socket`
- size: `1009`
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
- `0x18006fc4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006febc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ff09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ff7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006febc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ff09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ff7d`
- `WS2_32!WSASocketW` at `0x18006fead`
- `WS2_32!WSASocketW` at `0x18006fead`
- `WS2_32!__imp_bind` at `0x18006ff73`
- `WS2_32!__imp_bind` at `0x18006ff73`
- `WS2_32!__imp_closesocket` at `0x18006fff3`
- `WS2_32!__imp_closesocket` at `0x18006fff3`
- `WS2_32!__imp_htons` at `0x18006ff52`
- `WS2_32!__imp_htons` at `0x18006ff52`
- `WS2_32!__imp_setsockopt` at `0x18006feff`
- `WS2_32!__imp_setsockopt` at `0x18006ff39`
- `WS2_32!__imp_setsockopt` at `0x18006ffac`
- `WS2_32!__imp_setsockopt` at `0x18006ffd4`
- `WS2_32!__imp_setsockopt` at `0x18006feff`
- `WS2_32!__imp_setsockopt` at `0x18006ff39`
- `WS2_32!__imp_setsockopt` at `0x18006ffac`
- `WS2_32!__imp_setsockopt` at `0x18006ffd4`

## string_xrefs

- `0x18006fd5c`: `Not bypassing LSPs for the V4 socket,             because regkey config prevents`
- `0x18006fca6`: `IkeCreateV4Socket`
- `0x18006fffb`: `IkeCreateV4Socket`
- `0x180070007`: `IkeCreateV4Socket`

## pseudocode

```c
__int64 __fastcall IkeCreateV4Socket(u_short a1, SOCKET *a2)
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
  u_short v30; // ax
  char optval[4]; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h] BYREF
  sockaddr name; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v36[640]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v37[32]; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 *v38; // [rsp+2F0h] [rbp+1F0h]
  __int64 v39; // [rsp+2F8h] [rbp+1F8h]
  _BYTE v40[16]; // [rsp+300h] [rbp+200h] BYREF
  const char *v41; // [rsp+310h] [rbp+210h]
  __int64 v42; // [rsp+318h] [rbp+218h]

  *(_DWORD *)optval = 1;
  name = 0;
  memset_0(v36, 0, 0x274u);
  TraceLogHelper("IkeCreateV4Socket", 1);
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
      WPP_SF_iS(v7, 10, (unsigned int)WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids, TlsMmLuid, TlsPeerAddr);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v34 = IkeGetTlsMmLuid(v4);
      v38 = &v34;
      v39 = 8;
      v12 = (const WCHAR *)IkeGetTlsPeerAddr(v11);
      tlgCreate1Sz_wchar_t((__int64)v40, v12);
      v42 = 81;
      v41 = "Not bypassing LSPs for the V4 socket,             because regkey config prevents";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)word_180153A2A,
        v13,
        v14,
        5,
        (__int64)v37);
    }
    v15 = 0;
  }
  else
  {
    MsTcpipProtocolInfo = IkeGetMsTcpipProtocolInfo(2, v3, v5, v36);
    if ( MsTcpipProtocolInfo )
      goto LABEL_30;
    v15 = (struct _WSAPROTOCOL_INFOW *)v36;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v17 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v18 = IkeGetTlsPeerAddr(v16);
      v20 = IkeGetTlsMmLuid(v19);
      WPP_SF_iS(v17, 11, (unsigned int)WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids, v20, v18);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v34 = IkeGetTlsMmLuid(v16);
      v38 = &v34;
      v39 = 8;
      v22 = (const WCHAR *)IkeGetTlsPeerAddr(v21);
      tlgCreate1Sz_wchar_t((__int64)v40, v22);
      v42 = 76;
      v41 = "Creating V4 socket directly on MS base provider.             Bypassing LSPs";
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)word_1801539EA,
        v23,
        v24,
        5,
        (__int64)v37);
    }
  }
  v25 = WSASocketW(2, 2, 17, v15, 0, 0);
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
      *(_DWORD *)optval = 0;
      if ( !setsockopt(v26, 0, 22, optval, 4) )
      {
        name.sa_family = 2;
        v30 = htons(a1);
        *(_DWORD *)&name.sa_data[2] = 0;
        *(_WORD *)name.sa_data = v30;
        if ( bind(v26, &name, 16) )
        {
          LastError = GetLastError();
          v29 = "bind";
          goto LABEL_18;
        }
        *(_DWORD *)optval = 1;
        if ( !setsockopt(v26, 0, 19, optval, 4) )
        {
          *(_DWORD *)optval = 1;
          if ( !setsockopt(v26, 0, 47, optval, 4) )
          {
            *a2 = v26;
            goto LABEL_27;
          }
        }
      }
    }
    LastError = GetLastError();
    v29 = "setsockopt";
  }
LABEL_18:
  MsTcpipProtocolInfo = WfpReportSysErrorAsWinError(v28, v29, LastError, 1);
LABEL_27:
  if ( MsTcpipProtocolInfo && v26 )
    closesocket(v26);
LABEL_30:
  TraceLogHelper("IkeCreateV4Socket", 0);
  return IkeReturnError(MsTcpipProtocolInfo, "IkeCreateV4Socket");
}

```

## disassembly

```asm
0x18006fc4c  mov     [rsp-8+arg_10], rbx
0x18006fc51  push    rbp
0x18006fc52  push    rdi
0x18006fc53  push    r12
0x18006fc55  push    r13
0x18006fc57  push    r14
0x18006fc59  lea     rbp, [rsp-230h]
0x18006fc61  sub     rsp, 330h
0x18006fc68  mov     rax, cs:__security_cookie
0x18006fc6f  xor     rax, rsp
0x18006fc72  mov     [rbp+250h+var_30], rax
0x18006fc79  mov     r13, rdx
0x18006fc7c  mov     [rsp+350h+var_320], cx
0x18006fc81  xorps   xmm0, xmm0
0x18006fc84  lea     rcx, [rsp+350h+var_300]; void *
0x18006fc89  mov     ebx, 1
0x18006fc8e  xor     edx, edx; Val
0x18006fc90  mov     r8d, 274h; Size
0x18006fc96  mov     dword ptr [rsp+350h+optval], ebx
0x18006fc9a  movups  xmmword ptr [rsp+350h+name.sa_family], xmm0
0x18006fc9f  call    memset_0
0x18006fca4  mov     edx, ebx
0x18006fca6  lea     rcx, aIkecreatev4soc; "IkeCreateV4Socket"
0x18006fcad  call    TraceLogHelper
0x18006fcb2  mov     rax, cs:gIkeExtGlobals
0x18006fcb9  mov     ebx, 2
0x18006fcbe  test    [rax+7E8h], bl
0x18006fcc4  jz      loc_18006FDA4
0x18006fcca  xor     r14d, r14d
0x18006fccd  mov     rdi, cs:WPP_GLOBAL_Control
0x18006fcd4  lea     rax, WPP_GLOBAL_Control
0x18006fcdb  cmp     rdi, rax
0x18006fcde  jz      short loc_18006FD1C
0x18006fce0  cmp     byte ptr [rdi+19h], 4
0x18006fce4  jb      short loc_18006FD1C
0x18006fce6  test    byte ptr [rdi+1Ch], 10h
0x18006fcea  jz      short loc_18006FD1C
0x18006fcec  mov     rdi, [rdi+10h]
0x18006fcf0  call    IkeGetTlsPeerAddr
0x18006fcf5  mov     rbx, rax
0x18006fcf8  call    IkeGetTlsMmLuid
0x18006fcfd  mov     r9, rax
0x18006fd00  mov     qword ptr [rsp+350h+g], rbx
0x18006fd05  lea     edx, [r14+0Ah]
0x18006fd09  mov     rcx, rdi
0x18006fd0c  lea     r8, WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids
0x18006fd13  call    WPP_SF_iS
0x18006fd18  lea     ebx, [r14+2]
0x18006fd1c  mov     eax, cs:dword_180173278
0x18006fd22  cmp     eax, 4
0x18006fd25  jbe     short loc_18006FD9C
0x18006fd27  call    IkeGetTlsMmLuid
0x18006fd2c  mov     [rsp+350h+var_318], rax
0x18006fd31  lea     rax, [rsp+350h+var_318]
0x18006fd36  mov     [rbp+250h+var_60], rax
0x18006fd3d  mov     [rbp+250h+var_58], 8
0x18006fd48  call    IkeGetTlsPeerAddr
0x18006fd4d  mov     rdx, rax
0x18006fd50  lea     rcx, [rbp+250h+var_50]
0x18006fd57  call    _tlgCreate1Sz_wchar_t
0x18006fd5c  lea     rcx, aNotBypassingLs; "Not bypassing LSPs for the V4 socket,  "...
0x18006fd63  mov     [rbp+250h+var_38], 51h ; 'Q'
0x18006fd6e  lea     rax, [rbp+250h+var_80]
0x18006fd75  mov     [rbp+250h+var_40], rcx
0x18006fd7c  mov     qword ptr [rsp+350h+dwFlags], rax
0x18006fd81  lea     rcx, dword_180173278
0x18006fd88  lea     rdx, word_180153A2A
0x18006fd8f  mov     [rsp+350h+g], 5
0x18006fd97  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18006fd9c  xor     r12d, r12d
0x18006fd9f  jmp     loc_18006FE90
0x18006fda4  lea     r9, [rsp+350h+var_300]
0x18006fda9  mov     ecx, ebx
0x18006fdab  call    IkeGetMsTcpipProtocolInfo
0x18006fdb0  mov     r14, rax
0x18006fdb3  test    rax, rax
0x18006fdb6  jnz     loc_18006FFF9
0x18006fdbc  lea     r12, [rsp+350h+var_300]
0x18006fdc1  mov     rdi, cs:WPP_GLOBAL_Control
0x18006fdc8  lea     rax, WPP_GLOBAL_Control
0x18006fdcf  cmp     rdi, rax
0x18006fdd2  jz      short loc_18006FE10
0x18006fdd4  cmp     byte ptr [rdi+19h], 4
0x18006fdd8  jb      short loc_18006FE10
0x18006fdda  test    byte ptr [rdi+1Ch], 10h
0x18006fdde  jz      short loc_18006FE10
0x18006fde0  mov     rdi, [rdi+10h]
0x18006fde4  call    IkeGetTlsPeerAddr
0x18006fde9  mov     rbx, rax
0x18006fdec  call    IkeGetTlsMmLuid
0x18006fdf1  mov     r9, rax
0x18006fdf4  mov     qword ptr [rsp+350h+g], rbx
0x18006fdf9  lea     edx, [r14+0Bh]
0x18006fdfd  mov     rcx, rdi
0x18006fe00  lea     r8, WPP_ebb4b737af0c34df7364ed8e9c6f2dff_Traceguids
0x18006fe07  call    WPP_SF_iS
0x18006fe0c  lea     ebx, [r14+2]
0x18006fe10  mov     eax, cs:dword_180173278
0x18006fe16  cmp     eax, 4
0x18006fe19  jbe     short loc_18006FE90
0x18006fe1b  call    IkeGetTlsMmLuid
0x18006fe20  mov     [rsp+350h+var_318], rax
0x18006fe25  lea     rax, [rsp+350h+var_318]
0x18006fe2a  mov     [rbp+250h+var_60], rax
0x18006fe31  mov     [rbp+250h+var_58], 8
0x18006fe3c  call    IkeGetTlsPeerAddr
0x18006fe41  mov     rdx, rax
0x18006fe44  lea     rcx, [rbp+250h+var_50]
0x18006fe4b  call    _tlgCreate1Sz_wchar_t
0x18006fe50  lea     rcx, aCreatingV4Sock; "Creating V4 socket directly on MS base "...
0x18006fe57  mov     [rbp+250h+var_38], 4Ch ; 'L'
0x18006fe62  lea     rax, [rbp+250h+var_80]
0x18006fe69  mov     [rbp+250h+var_40], rcx
0x18006fe70  mov     qword ptr [rsp+350h+dwFlags], rax
0x18006fe75  lea     rcx, dword_180173278
0x18006fe7c  lea     rdx, word_1801539EA
0x18006fe83  mov     [rsp+350h+g], 5
0x18006fe8b  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18006fe90  mov     [rsp+350h+dwFlags], 0; dwFlags
0x18006fe98  mov     r9, r12; lpProtocolInfo
0x18006fe9b  mov     r8d, 11h; protocol
0x18006fea1  mov     [rsp+350h+g], 0; g
0x18006fea9  mov     edx, ebx; type
0x18006feab  mov     ecx, ebx; af
0x18006fead  call    cs:__imp_WSASocketW
0x18006feb3  mov     rbx, rax
0x18006feb6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006feba  jnz     short loc_18006FEDD
0x18006febc  call    cs:__imp_GetLastError
0x18006fec2  lea     r9d, [rbx+2]
0x18006fec6  lea     rdx, aWsasocketw; "WSASocketW"
0x18006fecd  mov     r8d, eax
0x18006fed0  call    WfpReportSysErrorAsWinError
0x18006fed5  mov     r14, rax
0x18006fed8  jmp     loc_18006FFE6
0x18006fedd  mov     edi, 1
0x18006fee2  mov     [rsp+350h+g], 4; optlen
0x18006feea  lea     r9, [rsp+350h+optval]; optval
0x18006feef  mov     dword ptr [rsp+350h+optval], edi
0x18006fef3  mov     edx, 0FFFFh; level
0x18006fef8  mov     rcx, rbx; s
0x18006fefb  lea     r8d, [rdi-6]; optname
0x18006feff  call    cs:__imp_setsockopt
0x18006ff05  test    eax, eax
0x18006ff07  jz      short loc_18006FF1B
0x18006ff09  call    cs:__imp_GetLastError
0x18006ff0f  mov     r9d, edi
0x18006ff12  lea     rdx, aSetsockopt; "setsockopt"
0x18006ff19  jmp     short loc_18006FECD
0x18006ff1b  xor     edx, edx; level
0x18006ff1d  mov     dword ptr [rsp+350h+optval], 0
0x18006ff25  lea     r9, [rsp+350h+optval]; optval
0x18006ff2a  mov     [rsp+350h+g], 4; optlen
0x18006ff32  mov     rcx, rbx; s
0x18006ff35  lea     r8d, [rdx+16h]; optname
0x18006ff39  call    cs:__imp_setsockopt
0x18006ff3f  test    eax, eax
0x18006ff41  jnz     short loc_18006FF09
0x18006ff43  movzx   ecx, [rsp+350h+var_320]; hostshort
0x18006ff48  mov     eax, 2
0x18006ff4d  mov     [rsp+350h+name.sa_family], ax
0x18006ff52  call    cs:__imp_htons
0x18006ff58  mov     r8d, 10h; namelen
0x18006ff5e  mov     dword ptr [rsp+350h+name.sa_data+2], 0
0x18006ff66  lea     rdx, [rsp+350h+name]; name
0x18006ff6b  mov     word ptr [rsp+350h+name.sa_data], ax
0x18006ff70  mov     rcx, rbx; s
0x18006ff73  call    cs:__imp_bind
0x18006ff79  test    eax, eax
0x18006ff7b  jz      short loc_18006FF92
0x18006ff7d  call    cs:__imp_GetLastError
0x18006ff83  mov     r9d, edi
0x18006ff86  lea     rdx, aBind; "bind"
0x18006ff8d  jmp     loc_18006FECD
0x18006ff92  xor     edx, edx; level
0x18006ff94  mov     dword ptr [rsp+350h+optval], edi
0x18006ff98  lea     r9, [rsp+350h+optval]; optval
0x18006ff9d  mov     [rsp+350h+g], 4; optlen
0x18006ffa5  mov     rcx, rbx; s
0x18006ffa8  lea     r8d, [rdx+13h]; optname
0x18006ffac  call    cs:__imp_setsockopt
0x18006ffb2  test    eax, eax
0x18006ffb4  jnz     loc_18006FF09
0x18006ffba  lea     r9, [rsp+350h+optval]; optval
0x18006ffbf  mov     dword ptr [rsp+350h+optval], edi
0x18006ffc3  xor     edx, edx; level
0x18006ffc5  mov     [rsp+350h+g], 4; optlen
0x18006ffcd  lea     r8d, [rax+2Fh]; optname
0x18006ffd1  mov     rcx, rbx; s
0x18006ffd4  call    cs:__imp_setsockopt
0x18006ffda  test    eax, eax
0x18006ffdc  jnz     loc_18006FF09
0x18006ffe2  mov     [r13+0], rbx
0x18006ffe6  test    r14, r14
0x18006ffe9  jz      short loc_18006FFF9
0x18006ffeb  test    rbx, rbx
0x18006ffee  jz      short loc_18006FFF9
0x18006fff0  mov     rcx, rbx; s
0x18006fff3  call    cs:__imp_closesocket
0x18006fff9  xor     edx, edx
0x18006fffb  lea     rcx, aIkecreatev4soc; "IkeCreateV4Socket"
0x180070002  call    TraceLogHelper
0x180070007  lea     rdx, aIkecreatev4soc; "IkeCreateV4Socket"
0x18007000e  mov     rcx, r14
0x180070011  call    IkeReturnError
0x180070016  mov     rcx, [rbp+250h+var_30]
0x18007001d  xor     rcx, rsp; StackCookie
0x180070020  call    __security_check_cookie
0x180070025  mov     rbx, [rsp+350h+arg_10]
0x18007002d  add     rsp, 330h
0x180070034  pop     r14
0x180070036  pop     r13
0x180070038  pop     r12
0x18007003a  pop     rdi
0x18007003b  pop     rbp
0x18007003c  retn
```
