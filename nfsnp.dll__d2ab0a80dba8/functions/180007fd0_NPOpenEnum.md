# NPOpenEnum

- ea: `0x180007fd0`
- end: `0x1800083bd`
- name: `NPOpenEnum`
- size: `1005`
- prototype: `DWORD __stdcall(DWORD dwScope, DWORD dwType, DWORD dwUsage, LPNETRESOURCEW lpNetResource, LPHANDLE lphEnum)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1800023f0`
- `0x180002930`
- `0x180002e18`
- `0x180004178`
- `0x1800044bc`
- `0x180007fd0`
- `0x180008730`
- `0x180008d20`
- `0x180008d7c`
- `0x1800094bc`
- `0x180009948`
- `0x180009f04`
- `0x18000a468`
- `0x18000b314`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180008221`
- `msvcrt!_wcsicmp` at `0x180008221`
- `KERNEL32!GlobalFree` at `0x18000826f`
- `KERNEL32!GlobalFree` at `0x18000826f`
- `WSOCK32!__imp_WSAStartup` at `0x180008054`
- `WSOCK32!__imp_WSAStartup` at `0x180008054`
- `WSOCK32!__imp_WSACleanup` at `0x180008313`
- `WSOCK32!__imp_WSACleanup` at `0x180008350`
- `WSOCK32!__imp_WSACleanup` at `0x180008313`
- `WSOCK32!__imp_WSACleanup` at `0x180008350`

## string_xrefs

- `0x180008002`: `NPOpenEnum`

## pseudocode

```c
DWORD __stdcall NPOpenEnum(DWORD dwScope, DWORD dwType, DWORD dwUsage, LPNETRESOURCEW lpNetResource, LPHANDLE lphEnum)
{
  DWORD v9; // ebx
  DWORD *ECB; // rax
  DWORD *v11; // rdi
  DWORD v12; // eax
  DWORD v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // rax
  DWORD v16; // eax
  void *v17; // rcx
  _DWORD v19[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct WSAData WSAData; // [rsp+40h] [rbp-C0h] BYREF
  char v21[16]; // [rsp+1E0h] [rbp+E0h] BYREF

  strcpy(v21, "NPOpenEnum");
  memset_0(&WSAData, 0, sizeof(WSAData));
  v19[0] = 0;
  if ( WSAStartup(0x101u, &WSAData) )
  {
    v9 = 1222;
LABEL_53:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
        (unsigned int)v21,
        v9);
    *lphEnum = 0;
    return v9;
  }
  if ( (int)NfsNpIsClientRunning(v19) < 0 || !v19[0] )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v21);
    v9 = 1222;
    goto LABEL_52;
  }
  ECB = (DWORD *)GetECB();
  v11 = ECB;
  if ( !ECB )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v21);
    v9 = 8;
    goto LABEL_52;
  }
  *ECB = dwScope;
  ECB[2] = dwUsage;
  v12 = 1;
  if ( dwType )
    v12 = dwType;
  v11[1] = v12;
  v13 = dwScope - 1;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v21);
    *((_QWORD *)v11 + 9) = 0;
    v9 = BuildConnectedDeviceList(v11);
    if ( !v9 )
      goto LABEL_44;
LABEL_43:
    FreeECB(v11);
LABEL_52:
    WSACleanup();
    goto LABEL_53;
  }
  if ( v13 == 1 )
  {
    v14 = WPP_GLOBAL_Control;
    v9 = 8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v21);
      v14 = WPP_GLOBAL_Control;
    }
    if ( !lpNetResource )
    {
      if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
        WPP_SF_(v14[2], 60, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
      BuildConfiguredLanList(v11);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_sq(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
          (unsigned int)v21,
          *((_QWORD *)v11 + 5));
      goto LABEL_44;
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
      WPP_SF_sq(
        v14[2],
        62,
        (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
        (unsigned int)v21,
        (char)lpNetResource);
    v15 = CopyNetResource(lpNetResource);
    *((_QWORD *)v11 + 13) = v15;
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v21);
      goto LABEL_37;
    }
    if ( _wcsicmp(lpNetResource->lpRemoteName, *((const wchar_t **)pGlobalNPCB + 5)) )
    {
      if ( (unsigned int)IsLanName(lpNetResource->lpRemoteName) == 1 )
        v16 = BuildLanList(v11);
      else
        v16 = BuildShowMountList(v11);
    }
    else
    {
      v16 = BuildConfiguredLanList(v11);
    }
    v9 = v16;
    if ( v16 )
    {
LABEL_37:
      v17 = (void *)*((_QWORD *)pGlobalNPCB + 21);
      if ( v17 )
        GlobalFree(v17);
      goto LABEL_43;
    }
  }
LABEL_44:
  *lphEnum = v11;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
      (unsigned int)v21,
      (char)v11);
  WSACleanup();
  return 0;
}

```

## disassembly

```asm
0x180007fd0  mov     [rsp-8+arg_0], rbx
0x180007fd5  mov     [rsp-8+arg_8], rsi
0x180007fda  push    rbp
0x180007fdb  push    rdi
0x180007fdc  push    r12
0x180007fde  push    r14
0x180007fe0  push    r15
0x180007fe2  lea     rbp, [rsp-100h]
0x180007fea  sub     rsp, 200h
0x180007ff1  mov     rax, cs:__security_cookie
0x180007ff8  xor     rax, rsp
0x180007ffb  mov     [rbp+120h+var_30], rax
0x180008002  movsd   xmm0, qword ptr cs:aNpopenenum_0; "NPOpenEnum"
0x18000800a  mov     r15d, r8d
0x18000800d  mov     eax, dword ptr cs:aNpopenenum_0+7; "num"
0x180008013  mov     r14d, edx
0x180008016  mov     r12, [rbp+120h+lphEnum]
0x18000801d  mov     ebx, ecx
0x18000801f  movsd   qword ptr [rbp+120h+var_40], xmm0
0x180008027  lea     rcx, [rsp+220h+WSAData]; void *
0x18000802c  xor     edx, edx; Val
0x18000802e  mov     dword ptr [rbp+120h+var_40+7], eax
0x180008034  mov     r8d, 198h; Size
0x18000803a  mov     rsi, r9
0x18000803d  call    memset_0
0x180008042  mov     ecx, 101h; wVersionRequested
0x180008047  mov     [rsp+220h+var_1F0], 0
0x18000804f  lea     rdx, [rsp+220h+WSAData]; lpWSAData
0x180008054  call    cs:__imp_WSAStartup
0x18000805a  lea     rdi, WPP_GLOBAL_Control
0x180008061  test    eax, eax
0x180008063  jz      short loc_18000806F
0x180008065  mov     ebx, 4C6h
0x18000806a  jmp     loc_180008356
0x18000806f  lea     rcx, [rsp+220h+var_1F0]
0x180008074  call    NfsNpIsClientRunning
0x180008079  test    eax, eax
0x18000807b  js      loc_18000831D
0x180008081  cmp     [rsp+220h+var_1F0], 0
0x180008086  jz      loc_18000831D
0x18000808c  call    GetECB
0x180008091  mov     rdi, rax
0x180008094  test    rax, rax
0x180008097  jnz     short loc_1800080D6
0x180008099  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080a0  lea     rdi, WPP_GLOBAL_Control
0x1800080a7  cmp     rcx, rdi
0x1800080aa  jz      short loc_1800080CC
0x1800080ac  test    byte ptr [rcx+1Ch], 2
0x1800080b0  jz      short loc_1800080CC
0x1800080b2  mov     rcx, [rcx+10h]
0x1800080b6  lea     edx, [rax+39h]
0x1800080b9  lea     r9, [rbp+120h+var_40]
0x1800080c0  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800080c7  call    WPP_SF_s
0x1800080cc  mov     ebx, 8
0x1800080d1  jmp     loc_180008350
0x1800080d6  mov     [rax], ebx
0x1800080d8  test    r14d, r14d
0x1800080db  mov     [rax+8], r15d
0x1800080df  mov     eax, 1
0x1800080e4  cmovnz  eax, r14d
0x1800080e8  mov     [rdi+4], eax
0x1800080eb  sub     ebx, 1
0x1800080ee  jz      loc_180008277
0x1800080f4  cmp     ebx, 1
0x1800080f7  jnz     loc_1800082D5
0x1800080fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180008104  lea     r14, WPP_GLOBAL_Control
0x18000810b  mov     ebx, 8
0x180008110  cmp     rcx, r14
0x180008113  jz      short loc_18000813B
0x180008115  test    [rcx+1Ch], bl
0x180008118  jz      short loc_18000813B
0x18000811a  mov     rcx, [rcx+10h]
0x18000811e  lea     edx, [rbx+33h]
0x180008121  lea     r9, [rbp+120h+var_40]
0x180008128  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000812f  call    WPP_SF_s
0x180008134  mov     rcx, cs:WPP_GLOBAL_Control
0x18000813b  test    rsi, rsi
0x18000813e  jnz     short loc_1800081A8
0x180008140  cmp     rcx, r14
0x180008143  jz      short loc_18000815D
0x180008145  test    [rcx+1Ch], bl
0x180008148  jz      short loc_18000815D
0x18000814a  mov     rcx, [rcx+10h]
0x18000814e  lea     edx, [rsi+3Ch]
0x180008151  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008158  call    WPP_SF_
0x18000815d  mov     rcx, rdi
0x180008160  call    BuildConfiguredLanList
0x180008165  mov     rcx, cs:WPP_GLOBAL_Control
0x18000816c  cmp     rcx, r14
0x18000816f  jz      loc_1800082DC
0x180008175  test    [rcx+1Ch], bl
0x180008178  jz      loc_1800082DC
0x18000817e  mov     rax, [rdi+28h]
0x180008182  lea     r9, [rbp+120h+var_40]
0x180008189  mov     rcx, [rcx+10h]
0x18000818d  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008194  mov     edx, 3Dh ; '='
0x180008199  mov     [rsp+220h+var_200], rax
0x18000819e  call    WPP_SF_sq
0x1800081a3  jmp     loc_1800082DC
0x1800081a8  cmp     rcx, r14
0x1800081ab  jz      short loc_1800081D3
0x1800081ad  test    [rcx+1Ch], bl
0x1800081b0  jz      short loc_1800081D3
0x1800081b2  mov     rcx, [rcx+10h]
0x1800081b6  lea     r9, [rbp+120h+var_40]
0x1800081bd  mov     edx, 3Eh ; '>'
0x1800081c2  mov     [rsp+220h+var_200], rsi
0x1800081c7  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800081ce  call    WPP_SF_sq
0x1800081d3  mov     rcx, rsi
0x1800081d6  call    CopyNetResource
0x1800081db  mov     [rdi+68h], rax
0x1800081df  test    rax, rax
0x1800081e2  jnz     short loc_180008212
0x1800081e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081eb  cmp     rcx, r14
0x1800081ee  jz      short loc_18000825C
0x1800081f0  test    byte ptr [rcx+1Ch], 2
0x1800081f4  jz      short loc_18000825C
0x1800081f6  mov     rcx, [rcx+10h]
0x1800081fa  lea     edx, [rax+3Fh]
0x1800081fd  lea     r9, [rbp+120h+var_40]
0x180008204  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000820b  call    WPP_SF_s
0x180008210  jmp     short loc_18000825C
0x180008212  mov     rdx, cs:pGlobalNPCB
0x180008219  mov     rcx, [rsi+18h]; String1
0x18000821d  mov     rdx, [rdx+28h]; String2
0x180008221  call    cs:__imp__wcsicmp
0x180008227  test    eax, eax
0x180008229  jnz     short loc_180008235
0x18000822b  mov     rcx, rdi
0x18000822e  call    BuildConfiguredLanList
0x180008233  jmp     short loc_180008252
0x180008235  mov     rcx, [rsi+18h]
0x180008239  call    IsLanName
0x18000823e  mov     rcx, rdi
0x180008241  cmp     eax, 1
0x180008244  jnz     short loc_18000824D
0x180008246  call    BuildLanList
0x18000824b  jmp     short loc_180008252
0x18000824d  call    BuildShowMountList
0x180008252  mov     ebx, eax
0x180008254  test    eax, eax
0x180008256  jz      loc_1800082DC
0x18000825c  mov     rax, cs:pGlobalNPCB
0x180008263  mov     rcx, [rax+0A8h]; hMem
0x18000826a  test    rcx, rcx
0x18000826d  jz      short loc_1800082C4
0x18000826f  call    cs:__imp_GlobalFree
0x180008275  jmp     short loc_1800082C4
0x180008277  mov     rcx, cs:WPP_GLOBAL_Control
0x18000827e  lea     r14, WPP_GLOBAL_Control
0x180008285  cmp     rcx, r14
0x180008288  jz      short loc_1800082AE
0x18000828a  mov     ebx, 8
0x18000828f  test    [rcx+1Ch], bl
0x180008292  jz      short loc_1800082AE
0x180008294  mov     rcx, [rcx+10h]
0x180008298  lea     edx, [rbx+32h]
0x18000829b  lea     r9, [rbp+120h+var_40]
0x1800082a2  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800082a9  call    WPP_SF_s
0x1800082ae  mov     rcx, rdi
0x1800082b1  mov     qword ptr [rdi+48h], 0
0x1800082b9  call    BuildConnectedDeviceList
0x1800082be  mov     ebx, eax
0x1800082c0  test    eax, eax
0x1800082c2  jz      short loc_1800082DC
0x1800082c4  mov     rcx, rdi; hMem
0x1800082c7  call    FreeECB
0x1800082cc  lea     rdi, WPP_GLOBAL_Control
0x1800082d3  jmp     short loc_180008350
0x1800082d5  lea     r14, WPP_GLOBAL_Control
0x1800082dc  mov     [r12], rdi
0x1800082e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800082e7  cmp     rcx, r14
0x1800082ea  jz      short loc_180008313
0x1800082ec  test    byte ptr [rcx+1Ch], 1
0x1800082f0  jz      short loc_180008313
0x1800082f2  mov     rcx, [rcx+10h]
0x1800082f6  lea     r9, [rbp+120h+var_40]
0x1800082fd  mov     edx, 40h ; '@'
0x180008302  mov     [rsp+220h+var_200], rdi
0x180008307  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000830e  call    WPP_SF_sq
0x180008313  call    cs:__imp_WSACleanup
0x180008319  xor     eax, eax
0x18000831b  jmp     short loc_180008392
0x18000831d  mov     rcx, cs:WPP_GLOBAL_Control
0x180008324  cmp     rcx, rdi
0x180008327  jz      short loc_18000834B
0x180008329  test    byte ptr [rcx+1Ch], 2
0x18000832d  jz      short loc_18000834B
0x18000832f  mov     rcx, [rcx+10h]
0x180008333  lea     r9, [rbp+120h+var_40]
0x18000833a  mov     edx, 38h ; '8'
0x18000833f  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008346  call    WPP_SF_s
0x18000834b  mov     ebx, 4C6h
0x180008350  call    cs:__imp_WSACleanup
0x180008356  mov     rcx, cs:WPP_GLOBAL_Control
0x18000835d  cmp     rcx, rdi
0x180008360  jz      short loc_180008388
0x180008362  test    byte ptr [rcx+1Ch], 2
0x180008366  jz      short loc_180008388
0x180008368  mov     rcx, [rcx+10h]
0x18000836c  lea     r9, [rbp+120h+var_40]
0x180008373  mov     edx, 41h ; 'A'
0x180008378  mov     dword ptr [rsp+220h+var_200], ebx
0x18000837c  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008383  call    WPP_SF_sd
0x180008388  mov     qword ptr [r12], 0
0x180008390  mov     eax, ebx
0x180008392  mov     rcx, [rbp+120h+var_30]
0x180008399  xor     rcx, rsp; StackCookie
0x18000839c  call    __security_check_cookie
0x1800083a1  lea     r11, [rsp+220h+var_20]
0x1800083a9  mov     rbx, [r11+30h]
0x1800083ad  mov     rsi, [r11+38h]
0x1800083b1  mov     rsp, r11
0x1800083b4  pop     r15
0x1800083b6  pop     r14
0x1800083b8  pop     r12
0x1800083ba  pop     rdi
0x1800083bb  pop     rbp
0x1800083bc  retn
```
