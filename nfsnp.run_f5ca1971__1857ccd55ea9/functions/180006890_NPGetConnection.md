# NPGetConnection

- ea: `0x180006890`
- end: `0x180006b3e`
- name: `NPGetConnection`
- size: `686`
- prototype: `DWORD __stdcall(LPWSTR lpLocalName, LPWSTR lpRemoteName, LPDWORD lpnBufferLen)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x180008150`

## callees

- `0x180002508`
- `0x180002538`
- `0x180006890`
- `0x180008d00`
- `0x1800090dc`
- `0x1800091f4`
- `0x180009278`
- `0x18000937c`
- `0x18000b600`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `WSOCK32!__imp_WSAStartup` at `0x180006945`
- `WSOCK32!__imp_WSAStartup` at `0x180006945`
- `WSOCK32!__imp_WSACleanup` at `0x180006a53`
- `WSOCK32!__imp_WSACleanup` at `0x180006ae7`
- `WSOCK32!__imp_WSACleanup` at `0x180006a53`
- `WSOCK32!__imp_WSACleanup` at `0x180006ae7`

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
0x180006890  push    rbp
0x180006892  push    rbx
0x180006893  push    rsi
0x180006894  push    r12
0x180006896  push    r14
0x180006898  lea     rbp, [rsp-100h]
0x1800068a0  sub     rsp, 200h
0x1800068a7  mov     rax, cs:__security_cookie
0x1800068ae  xor     rax, rsp
0x1800068b1  mov     [rbp+120h+var_30], rax
0x1800068b8  movups  xmm0, xmmword ptr cs:aNpgetconnectio_0; "NPGetConnection"
0x1800068bf  mov     r14, r8
0x1800068c2  mov     rsi, rdx
0x1800068c5  mov     rbx, rcx
0x1800068c8  xor     edx, edx; Val
0x1800068ca  mov     r8d, 198h; Size
0x1800068d0  lea     rcx, [rsp+220h+WSAData]; void *
0x1800068d5  movdqu  [rbp+120h+var_40], xmm0
0x1800068dd  call    memset_0
0x1800068e2  mov     [rsp+220h+var_1F0], 0
0x1800068ea  mov     [rsp+220h+var_1E8], 0
0x1800068f2  mov     [rsp+220h+var_1EC], 0
0x1800068fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180006901  lea     r12, WPP_GLOBAL_Control
0x180006908  cmp     rcx, r12
0x18000690b  jz      short loc_18000692B
0x18000690d  test    byte ptr [rcx+1Ch], 1
0x180006911  jz      short loc_18000692B
0x180006913  mov     eax, [r14]
0x180006916  mov     edx, 0B9h
0x18000691b  mov     rcx, [rcx+10h]
0x18000691f  mov     r9, rbx
0x180006922  mov     dword ptr [rsp+220h+var_200], eax
0x180006926  call    WPP_SF_Sd
0x18000692b  test    rsi, rsi
0x18000692e  jz      short loc_18000693B
0x180006930  cmp     dword ptr [r14], 0
0x180006934  jbe     short loc_18000693B
0x180006936  xor     eax, eax
0x180006938  mov     [rsi], ax
0x18000693b  mov     ecx, 101h; wVersionRequested
0x180006940  lea     rdx, [rsp+220h+WSAData]; lpWSAData
0x180006945  call    cs:__imp_WSAStartup
0x18000694c  nop     dword ptr [rax+rax+00h]
0x180006951  test    eax, eax
0x180006953  jz      short loc_18000695F
0x180006955  mov     ebx, 4C6h
0x18000695a  jmp     loc_180006AF3
0x18000695f  lea     rcx, [rsp+220h+var_1F0]
0x180006964  call    NfsNpIsClientRunning
0x180006969  test    eax, eax
0x18000696b  js      loc_180006AB4
0x180006971  cmp     [rsp+220h+var_1F0], 0
0x180006976  jz      loc_180006AB4
0x18000697c  lea     rax, [rsp+220h+var_1E8]
0x180006981  mov     r8, r14
0x180006984  lea     r9, [rsp+220h+var_1EC]
0x180006989  mov     [rsp+220h+var_200], rax
0x18000698e  mov     rdx, rsi
0x180006991  mov     rcx, rbx
0x180006994  call    FetchDeviceEntry
0x180006999  mov     ebx, eax
0x18000699b  test    eax, eax
0x18000699d  jz      short loc_1800069D6
0x18000699f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069a6  cmp     rcx, r12
0x1800069a9  jz      loc_180006AE7
0x1800069af  test    byte ptr [rcx+1Ch], 2
0x1800069b3  jz      loc_180006AE7
0x1800069b9  mov     eax, [r14]
0x1800069bc  mov     edx, 0BBh
0x1800069c1  mov     rcx, [rcx+10h]
0x1800069c5  mov     r9d, ebx
0x1800069c8  mov     dword ptr [rsp+220h+var_200], eax
0x1800069cc  call    WPP_SF_dd
0x1800069d1  jmp     loc_180006AE7
0x1800069d6  test    rsi, rsi
0x1800069d9  jnz     short loc_180006A0C
0x1800069db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069e2  cmp     rcx, r12
0x1800069e5  jz      short loc_180006A02
0x1800069e7  test    byte ptr [rcx+1Ch], 2
0x1800069eb  jz      short loc_180006A02
0x1800069ed  mov     rcx, [rcx+10h]
0x1800069f1  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800069f8  mov     edx, 0BCh
0x1800069fd  call    WPP_SF_
0x180006a02  mov     ebx, 1E7h
0x180006a07  jmp     loc_180006AE7
0x180006a0c  cmp     [rsp+220h+var_1EC], 1
0x180006a11  jnz     short loc_180006A53
0x180006a13  cmp     [rsp+220h+var_1E8], 0
0x180006a18  jnz     short loc_180006A53
0x180006a1a  mov     ebx, 4B1h
0x180006a1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a26  cmp     rcx, r12
0x180006a29  jz      loc_180006AE7
0x180006a2f  test    byte ptr [rcx+1Ch], 2
0x180006a33  jz      loc_180006AE7
0x180006a39  mov     rcx, [rcx+10h]
0x180006a3d  mov     edx, 0BDh
0x180006a42  mov     r9, rsi
0x180006a45  mov     dword ptr [rsp+220h+var_200], ebx
0x180006a49  call    WPP_SF_Sd
0x180006a4e  jmp     loc_180006AE7
0x180006a53  call    cs:__imp_WSACleanup
0x180006a5a  nop     dword ptr [rax+rax+00h]
0x180006a5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a66  cmp     rcx, r12
0x180006a69  jz      short loc_180006AB0
0x180006a6b  test    byte ptr [rcx+1Ch], 8
0x180006a6f  jz      short loc_180006A90
0x180006a71  mov     rcx, [rcx+10h]
0x180006a75  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006a7c  mov     edx, 0BEh
0x180006a81  mov     r9, rsi
0x180006a84  call    WPP_SF_S
0x180006a89  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a90  cmp     rcx, r12
0x180006a93  jz      short loc_180006AB0
0x180006a95  test    byte ptr [rcx+1Ch], 1
0x180006a99  jz      short loc_180006AB0
0x180006a9b  mov     rcx, [rcx+10h]
0x180006a9f  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006aa6  mov     edx, 0BFh
0x180006aab  call    WPP_SF_
0x180006ab0  xor     eax, eax
0x180006ab2  jmp     short loc_180006B1F
0x180006ab4  mov     rcx, cs:WPP_GLOBAL_Control
0x180006abb  cmp     rcx, r12
0x180006abe  jz      short loc_180006AE2
0x180006ac0  test    byte ptr [rcx+1Ch], 2
0x180006ac4  jz      short loc_180006AE2
0x180006ac6  mov     rcx, [rcx+10h]
0x180006aca  lea     r9, [rbp+120h+var_40]
0x180006ad1  mov     edx, 0BAh
0x180006ad6  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006add  call    WPP_SF_s
0x180006ae2  mov     ebx, 4C6h
0x180006ae7  call    cs:__imp_WSACleanup
0x180006aee  nop     dword ptr [rax+rax+00h]
0x180006af3  mov     rcx, cs:WPP_GLOBAL_Control
0x180006afa  cmp     rcx, r12
0x180006afd  jz      short loc_180006B1D
0x180006aff  test    byte ptr [rcx+1Ch], 2
0x180006b03  jz      short loc_180006B1D
0x180006b05  mov     rcx, [rcx+10h]
0x180006b09  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006b10  mov     edx, 0C0h
0x180006b15  mov     r9d, ebx
0x180006b18  call    WPP_SF_d
0x180006b1d  mov     eax, ebx
0x180006b1f  mov     rcx, [rbp+120h+var_30]
0x180006b26  xor     rcx, rsp; StackCookie
0x180006b29  call    __security_check_cookie
0x180006b2e  add     rsp, 200h
0x180006b35  pop     r14
0x180006b37  pop     r12
0x180006b39  pop     rsi
0x180006b3a  pop     rbx
0x180006b3b  pop     rbp
0x180006b3c  retn
```
