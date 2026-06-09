# NPGetConnection

- ea: `0x180006410`
- end: `0x1800066ab`
- name: `NPGetConnection`
- size: `667`
- prototype: `DWORD __stdcall(LPWSTR lpLocalName, LPWSTR lpRemoteName, LPDWORD lpnBufferLen)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180007bc0`

## callees

- `0x1800023f0`
- `0x180002418`
- `0x180006410`
- `0x180008730`
- `0x180008aa0`
- `0x180008bac`
- `0x180008c2c`
- `0x180008d20`
- `0x18000adf4`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `WSOCK32!__imp_WSAStartup` at `0x1800064c5`
- `WSOCK32!__imp_WSAStartup` at `0x1800064c5`
- `WSOCK32!__imp_WSACleanup` at `0x1800065cd`
- `WSOCK32!__imp_WSACleanup` at `0x18000665b`
- `WSOCK32!__imp_WSACleanup` at `0x1800065cd`
- `WSOCK32!__imp_WSACleanup` at `0x18000665b`

## pseudocode

```c
DWORD __stdcall NPGetConnection(LPWSTR lpLocalName, LPWSTR lpRemoteName, LPDWORD lpnBufferLen)
{
  int v5; // ebx
  int v6; // r8d
  DWORD DeviceEntry; // ebx
  __int64 v8; // r8
  _QWORD *v9; // rcx
  int v11; // [rsp+30h] [rbp-D0h] BYREF
  int v12; // [rsp+34h] [rbp-CCh] BYREF
  int v13; // [rsp+38h] [rbp-C8h] BYREF
  struct WSAData WSAData; // [rsp+40h] [rbp-C0h] BYREF
  char v15[16]; // [rsp+1E0h] [rbp+E0h] BYREF

  v5 = (int)lpLocalName;
  strcpy(v15, "NPGetConnection");
  memset_0(&WSAData, 0, sizeof(WSAData));
  v11 = 0;
  v13 = 0;
  v12 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, v6, v5, *lpnBufferLen);
  if ( lpRemoteName && *lpnBufferLen )
    *lpRemoteName = 0;
  if ( WSAStartup(0x101u, &WSAData) )
  {
    DeviceEntry = 1222;
LABEL_37:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, DeviceEntry);
    return DeviceEntry;
  }
  if ( (int)NfsNpIsClientRunning(&v11) < 0 || !v11 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v15);
    DeviceEntry = 1222;
    goto LABEL_36;
  }
  DeviceEntry = FetchDeviceEntry(v5, (_DWORD)lpRemoteName, (_DWORD)lpnBufferLen, (unsigned int)&v12, (__int64)&v13);
  if ( DeviceEntry )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 187, v8, DeviceEntry, *lpnBufferLen);
LABEL_36:
    WSACleanup();
    goto LABEL_37;
  }
  if ( !lpRemoteName )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 188, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    DeviceEntry = 487;
    goto LABEL_36;
  }
  if ( v12 == 1 && !v13 )
  {
    DeviceEntry = 1201;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, v8, (_DWORD)lpRemoteName, 177);
    goto LABEL_36;
  }
  WSACleanup();
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, lpRemoteName);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
      WPP_SF_(v9[2], 191, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x180006410  push    rbp
0x180006412  push    rbx
0x180006413  push    rsi
0x180006414  push    r12
0x180006416  push    r14
0x180006418  lea     rbp, [rsp-100h]
0x180006420  sub     rsp, 200h
0x180006427  mov     rax, cs:__security_cookie
0x18000642e  xor     rax, rsp
0x180006431  mov     [rbp+120h+var_30], rax
0x180006438  movups  xmm0, xmmword ptr cs:aNpgetconnectio_0; "NPGetConnection"
0x18000643f  mov     r14, r8
0x180006442  mov     rsi, rdx
0x180006445  mov     rbx, rcx
0x180006448  xor     edx, edx; Val
0x18000644a  mov     r8d, 198h; Size
0x180006450  lea     rcx, [rsp+220h+WSAData]; void *
0x180006455  movdqu  [rbp+120h+var_40], xmm0
0x18000645d  call    memset_0
0x180006462  mov     [rsp+220h+var_1F0], 0
0x18000646a  mov     [rsp+220h+var_1E8], 0
0x180006472  mov     [rsp+220h+var_1EC], 0
0x18000647a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006481  lea     r12, WPP_GLOBAL_Control
0x180006488  cmp     rcx, r12
0x18000648b  jz      short loc_1800064AB
0x18000648d  test    byte ptr [rcx+1Ch], 1
0x180006491  jz      short loc_1800064AB
0x180006493  mov     eax, [r14]
0x180006496  mov     edx, 0B9h
0x18000649b  mov     rcx, [rcx+10h]
0x18000649f  mov     r9, rbx
0x1800064a2  mov     dword ptr [rsp+220h+var_200], eax
0x1800064a6  call    WPP_SF_Sd
0x1800064ab  test    rsi, rsi
0x1800064ae  jz      short loc_1800064BB
0x1800064b0  cmp     dword ptr [r14], 0
0x1800064b4  jbe     short loc_1800064BB
0x1800064b6  xor     eax, eax
0x1800064b8  mov     [rsi], ax
0x1800064bb  mov     ecx, 101h; wVersionRequested
0x1800064c0  lea     rdx, [rsp+220h+WSAData]; lpWSAData
0x1800064c5  call    cs:__imp_WSAStartup
0x1800064cb  test    eax, eax
0x1800064cd  jz      short loc_1800064D9
0x1800064cf  mov     ebx, 4C6h
0x1800064d4  jmp     loc_180006661
0x1800064d9  lea     rcx, [rsp+220h+var_1F0]
0x1800064de  call    NfsNpIsClientRunning
0x1800064e3  test    eax, eax
0x1800064e5  js      loc_180006628
0x1800064eb  cmp     [rsp+220h+var_1F0], 0
0x1800064f0  jz      loc_180006628
0x1800064f6  lea     rax, [rsp+220h+var_1E8]
0x1800064fb  mov     r8, r14
0x1800064fe  lea     r9, [rsp+220h+var_1EC]
0x180006503  mov     [rsp+220h+var_200], rax
0x180006508  mov     rdx, rsi
0x18000650b  mov     rcx, rbx
0x18000650e  call    FetchDeviceEntry
0x180006513  mov     ebx, eax
0x180006515  test    eax, eax
0x180006517  jz      short loc_180006550
0x180006519  mov     rcx, cs:WPP_GLOBAL_Control
0x180006520  cmp     rcx, r12
0x180006523  jz      loc_18000665B
0x180006529  test    byte ptr [rcx+1Ch], 2
0x18000652d  jz      loc_18000665B
0x180006533  mov     eax, [r14]
0x180006536  mov     edx, 0BBh
0x18000653b  mov     rcx, [rcx+10h]
0x18000653f  mov     r9d, ebx
0x180006542  mov     dword ptr [rsp+220h+var_200], eax
0x180006546  call    WPP_SF_dd
0x18000654b  jmp     loc_18000665B
0x180006550  test    rsi, rsi
0x180006553  jnz     short loc_180006586
0x180006555  mov     rcx, cs:WPP_GLOBAL_Control
0x18000655c  cmp     rcx, r12
0x18000655f  jz      short loc_18000657C
0x180006561  test    byte ptr [rcx+1Ch], 2
0x180006565  jz      short loc_18000657C
0x180006567  mov     rcx, [rcx+10h]
0x18000656b  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006572  mov     edx, 0BCh
0x180006577  call    WPP_SF_
0x18000657c  mov     ebx, 1E7h
0x180006581  jmp     loc_18000665B
0x180006586  cmp     [rsp+220h+var_1EC], 1
0x18000658b  jnz     short loc_1800065CD
0x18000658d  cmp     [rsp+220h+var_1E8], 0
0x180006592  jnz     short loc_1800065CD
0x180006594  mov     ebx, 4B1h
0x180006599  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065a0  cmp     rcx, r12
0x1800065a3  jz      loc_18000665B
0x1800065a9  test    byte ptr [rcx+1Ch], 2
0x1800065ad  jz      loc_18000665B
0x1800065b3  mov     rcx, [rcx+10h]
0x1800065b7  mov     edx, 0BDh
0x1800065bc  mov     r9, rsi
0x1800065bf  mov     dword ptr [rsp+220h+var_200], ebx
0x1800065c3  call    WPP_SF_Sd
0x1800065c8  jmp     loc_18000665B
0x1800065cd  call    cs:__imp_WSACleanup
0x1800065d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065da  cmp     rcx, r12
0x1800065dd  jz      short loc_180006624
0x1800065df  test    byte ptr [rcx+1Ch], 8
0x1800065e3  jz      short loc_180006604
0x1800065e5  mov     rcx, [rcx+10h]
0x1800065e9  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800065f0  mov     edx, 0BEh
0x1800065f5  mov     r9, rsi
0x1800065f8  call    WPP_SF_S
0x1800065fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180006604  cmp     rcx, r12
0x180006607  jz      short loc_180006624
0x180006609  test    byte ptr [rcx+1Ch], 1
0x18000660d  jz      short loc_180006624
0x18000660f  mov     rcx, [rcx+10h]
0x180006613  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000661a  mov     edx, 0BFh
0x18000661f  call    WPP_SF_
0x180006624  xor     eax, eax
0x180006626  jmp     short loc_18000668D
0x180006628  mov     rcx, cs:WPP_GLOBAL_Control
0x18000662f  cmp     rcx, r12
0x180006632  jz      short loc_180006656
0x180006634  test    byte ptr [rcx+1Ch], 2
0x180006638  jz      short loc_180006656
0x18000663a  mov     rcx, [rcx+10h]
0x18000663e  lea     r9, [rbp+120h+var_40]
0x180006645  mov     edx, 0BAh
0x18000664a  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006651  call    WPP_SF_s
0x180006656  mov     ebx, 4C6h
0x18000665b  call    cs:__imp_WSACleanup
0x180006661  mov     rcx, cs:WPP_GLOBAL_Control
0x180006668  cmp     rcx, r12
0x18000666b  jz      short loc_18000668B
0x18000666d  test    byte ptr [rcx+1Ch], 2
0x180006671  jz      short loc_18000668B
0x180006673  mov     rcx, [rcx+10h]
0x180006677  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000667e  mov     edx, 0C0h
0x180006683  mov     r9d, ebx
0x180006686  call    WPP_SF_d
0x18000668b  mov     eax, ebx
0x18000668d  mov     rcx, [rbp+120h+var_30]
0x180006694  xor     rcx, rsp; StackCookie
0x180006697  call    __security_check_cookie
0x18000669c  add     rsp, 200h
0x1800066a3  pop     r14
0x1800066a5  pop     r12
0x1800066a7  pop     rsi
0x1800066a8  pop     rbx
0x1800066a9  pop     rbp
0x1800066aa  retn
```
