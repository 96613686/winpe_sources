# NcbRegistrarpOpenControlSocket

- ea: `0x1800214b4`
- end: `0x180021717`
- name: `NcbRegistrarpOpenControlSocket`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015dc0`

## callees

- `0x18000a0a0`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`
- `0x18001e368`
- `0x1800214b4`

## import_xrefs

- `WS2_32!WSASocketW` at `0x1800215bc`
- `WS2_32!WSASocketW` at `0x1800215bc`
- `WS2_32!WSAIoctl` at `0x180021648`
- `WS2_32!WSAIoctl` at `0x180021648`
- `WS2_32!__imp_closesocket` at `0x180021690`
- `WS2_32!__imp_closesocket` at `0x180021690`
- `WS2_32!__imp_WSAGetLastError` at `0x180021655`
- `WS2_32!__imp_WSAGetLastError` at `0x180021655`
- `WS2_32!__imp_WSAStartup` at `0x180021534`
- `WS2_32!__imp_WSAStartup` at `0x180021534`
- `WS2_32!__imp_WSACleanup` at `0x18002169a`
- `WS2_32!__imp_WSACleanup` at `0x18002169a`

## pseudocode

```c
__int64 NcbRegistrarpOpenControlSocket()
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  PVOID *v2; // rcx
  __int64 v3; // rdx
  SOCKET v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int Error; // eax
  DWORD cbBytesReturned[4]; // [rsp+50h] [rbp-1C8h] BYREF
  struct WSAData WSAData; // [rsp+60h] [rbp-1B8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids);
  }
  memset_0(&WSAData, 0, sizeof(WSAData));
  cbBytesReturned[0] = 0;
  v0 = WSAStartup(0x202u, &WSAData);
  v1 = v0;
  if ( v0 )
  {
    v2 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v0);
        v2 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 1) != 0 && *((_BYTE *)v2 + 25) >= 6u )
      {
        v3 = 71;
LABEL_33:
        WPP_SF_d(v2[2], v3, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, v1);
        return v1;
      }
    }
    return v1;
  }
  v4 = WSASocketW(23, 1, 6, 0, 0, 0x80u);
  g_NcbControlSocket = v4;
  if ( v4 == -1 )
  {
    v1 = -1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, 0xFFFFFFFFLL);
    }
LABEL_26:
    WSACleanup();
    g_NcbControlSocket = -1;
    goto LABEL_27;
  }
  v1 = WSAIoctl(v4, 0x98000012, 0, 0, 0, 0, cbBytesReturned, 0, 0);
  if ( v1 == -1 )
  {
    Error = WSAGetLastError();
    v1 = Error;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids, Error);
    }
    closesocket(g_NcbControlSocket);
  }
  if ( v1 )
    goto LABEL_26;
LABEL_27:
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v6, v5, L"NcbReg: WPM control endpoint creation ended with", v1);
  v2 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v3 = 74;
    goto LABEL_33;
  }
  return v1;
}

```

## disassembly

```asm
0x1800214b4  mov     [rsp+arg_0], rbx
0x1800214b9  mov     [rsp+arg_8], rsi
0x1800214be  push    r14
0x1800214c0  sub     rsp, 210h
0x1800214c7  mov     rax, cs:__security_cookie
0x1800214ce  xor     rax, rsp
0x1800214d1  mov     [rsp+218h+var_18], rax
0x1800214d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214e0  lea     rsi, WPP_GLOBAL_Control
0x1800214e7  lea     r14, WPP_bf9fab00fa853a5bd6fbfd2bc0219c8d_Traceguids
0x1800214ee  cmp     rcx, rsi
0x1800214f1  jz      short loc_180021510
0x1800214f3  test    byte ptr [rcx+1Ch], 1
0x1800214f7  jz      short loc_180021510
0x1800214f9  cmp     byte ptr [rcx+19h], 6
0x1800214fd  jb      short loc_180021510
0x1800214ff  mov     rcx, [rcx+10h]
0x180021503  mov     edx, 45h ; 'E'
0x180021508  mov     r8, r14
0x18002150b  call    WPP_SF_
0x180021510  xor     edx, edx; Val
0x180021512  lea     rcx, [rsp+218h+WSAData]; void *
0x180021517  mov     r8d, 198h; Size
0x18002151d  call    memset_0
0x180021522  mov     ecx, 202h; wVersionRequested
0x180021527  mov     [rsp+218h+cbBytesReturned], 0
0x18002152f  lea     rdx, [rsp+218h+WSAData]; lpWSAData
0x180021534  call    cs:__imp_WSAStartup
0x18002153a  mov     ebx, eax
0x18002153c  test    eax, eax
0x18002153e  jz      short loc_18002159E
0x180021540  mov     rcx, cs:WPP_GLOBAL_Control
0x180021547  cmp     rcx, rsi
0x18002154a  jz      loc_1800216EF
0x180021550  test    byte ptr [rcx+1Ch], 1
0x180021554  jz      short loc_180021577
0x180021556  cmp     byte ptr [rcx+19h], 2
0x18002155a  jb      short loc_180021577
0x18002155c  mov     rcx, [rcx+10h]
0x180021560  mov     edx, 46h ; 'F'
0x180021565  mov     r9d, eax
0x180021568  mov     r8, r14
0x18002156b  call    WPP_SF_d
0x180021570  mov     rcx, cs:WPP_GLOBAL_Control
0x180021577  cmp     rcx, rsi
0x18002157a  jz      loc_1800216EF
0x180021580  test    byte ptr [rcx+1Ch], 1
0x180021584  jz      loc_1800216EF
0x18002158a  cmp     byte ptr [rcx+19h], 6
0x18002158e  jb      loc_1800216EF
0x180021594  mov     edx, 47h ; 'G'
0x180021599  jmp     loc_1800216E0
0x18002159e  xor     r9d, r9d; lpProtocolInfo
0x1800215a1  mov     [rsp+218h+dwFlags], 80h; dwFlags
0x1800215a9  mov     [rsp+218h+g], 0; g
0x1800215b1  lea     edx, [r9+1]; type
0x1800215b5  lea     ecx, [rdx+16h]; af
0x1800215b8  lea     r8d, [r9+6]; protocol
0x1800215bc  call    cs:__imp_WSASocketW
0x1800215c2  mov     cs:g_NcbControlSocket, rax
0x1800215c9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800215cd  jnz     short loc_18002160D
0x1800215cf  or      ebx, eax
0x1800215d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215d8  cmp     rcx, rsi
0x1800215db  jz      loc_18002169A
0x1800215e1  test    byte ptr [rcx+1Ch], 1
0x1800215e5  jz      loc_18002169A
0x1800215eb  cmp     byte ptr [rcx+19h], 2
0x1800215ef  jb      loc_18002169A
0x1800215f5  mov     rcx, [rcx+10h]
0x1800215f9  lea     edx, [rax+49h]
0x1800215fc  or      r9d, 0FFFFFFFFh
0x180021600  mov     r8, r14
0x180021603  call    WPP_SF_d
0x180021608  jmp     loc_18002169A
0x18002160d  mov     [rsp+218h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180021616  lea     rcx, [rsp+218h+cbBytesReturned]
0x18002161b  mov     [rsp+218h+lpOverlapped], 0; lpOverlapped
0x180021624  xor     r9d, r9d; cbInBuffer
0x180021627  mov     [rsp+218h+lpcbBytesReturned], rcx; lpcbBytesReturned
0x18002162c  xor     r8d, r8d; lpvInBuffer
0x18002162f  mov     [rsp+218h+dwFlags], 0; cbOutBuffer
0x180021637  mov     rcx, rax; s
0x18002163a  mov     edx, 98000012h; dwIoControlCode
0x18002163f  mov     qword ptr [rsp+218h+g], 0; lpvOutBuffer
0x180021648  call    cs:__imp_WSAIoctl
0x18002164e  mov     ebx, eax
0x180021650  cmp     eax, 0FFFFFFFFh
0x180021653  jnz     short loc_180021696
0x180021655  call    cs:__imp_WSAGetLastError
0x18002165b  mov     ebx, eax
0x18002165d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021664  cmp     rcx, rsi
0x180021667  jz      short loc_180021689
0x180021669  test    byte ptr [rcx+1Ch], 1
0x18002166d  jz      short loc_180021689
0x18002166f  cmp     byte ptr [rcx+19h], 2
0x180021673  jb      short loc_180021689
0x180021675  mov     rcx, [rcx+10h]
0x180021679  mov     edx, 49h ; 'I'
0x18002167e  mov     r9d, eax
0x180021681  mov     r8, r14
0x180021684  call    WPP_SF_d
0x180021689  mov     rcx, cs:g_NcbControlSocket; s
0x180021690  call    cs:__imp_closesocket
0x180021696  test    ebx, ebx
0x180021698  jz      short loc_1800216AB
0x18002169a  call    cs:__imp_WSACleanup
0x1800216a0  mov     cs:g_NcbControlSocket, 0FFFFFFFFFFFFFFFFh
0x1800216ab  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800216b2  jz      short loc_1800216C3
0x1800216b4  mov     r9d, ebx
0x1800216b7  lea     r8, aNcbregWpmContr; "NcbReg: WPM control endpoint creation e"...
0x1800216be  call    McTemplateU0zq_EventWriteTransfer
0x1800216c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216ca  cmp     rcx, rsi
0x1800216cd  jz      short loc_1800216EF
0x1800216cf  test    byte ptr [rcx+1Ch], 1
0x1800216d3  jz      short loc_1800216EF
0x1800216d5  cmp     byte ptr [rcx+19h], 6
0x1800216d9  jb      short loc_1800216EF
0x1800216db  mov     edx, 4Ah ; 'J'
0x1800216e0  mov     rcx, [rcx+10h]
0x1800216e4  mov     r9d, ebx
0x1800216e7  mov     r8, r14
0x1800216ea  call    WPP_SF_d
0x1800216ef  mov     eax, ebx
0x1800216f1  mov     rcx, [rsp+218h+var_18]
0x1800216f9  xor     rcx, rsp; StackCookie
0x1800216fc  call    __security_check_cookie
0x180021701  lea     r11, [rsp+218h+var_8]
0x180021709  mov     rbx, [r11+10h]
0x18002170d  mov     rsi, [r11+18h]
0x180021711  mov     rsp, r11
0x180021714  pop     r14
0x180021716  retn
```
