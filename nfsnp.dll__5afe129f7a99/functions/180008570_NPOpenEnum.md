# NPOpenEnum

- ea: `0x180008570`
- end: `0x18000897f`
- name: `NPOpenEnum`
- size: `1039`
- prototype: `DWORD __stdcall(DWORD dwScope, DWORD dwType, DWORD dwUsage, LPNETRESOURCEW lpNetResource, LPHANDLE lphEnum)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180002508`
- `0x180002a90`
- `0x180002f9c`
- `0x180004348`
- `0x180004708`
- `0x180008570`
- `0x180008d00`
- `0x18000937c`
- `0x1800093e0`
- `0x180009b60`
- `0x18000a020`
- `0x18000a61c`
- `0x18000abcc`
- `0x18000bb40`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800087c7`
- `msvcrt!_wcsicmp` at `0x1800087c7`
- `KERNEL32!GlobalFree` at `0x18000881b`
- `KERNEL32!GlobalFree` at `0x18000881b`
- `WSOCK32!__imp_WSAStartup` at `0x1800085f4`
- `WSOCK32!__imp_WSAStartup` at `0x1800085f4`
- `WSOCK32!__imp_WSACleanup` at `0x1800088c8`
- `WSOCK32!__imp_WSACleanup` at `0x18000890b`
- `WSOCK32!__imp_WSACleanup` at `0x1800088c8`
- `WSOCK32!__imp_WSACleanup` at `0x18000890b`

## string_xrefs

- `0x1800085a2`: `NPOpenEnum`

## pseudocode

```c
DWORD __stdcall NPOpenEnum(DWORD dwScope, DWORD dwType, DWORD dwUsage, LPNETRESOURCEW lpNetResource, LPHANDLE lphEnum)
{
  DWORD v9; // ebx
  _DWORD *ECB; // rax
  CLIENT_CALL_RETURN v11; // rdi
  DWORD v12; // eax
  DWORD v13; // ebx
  _QWORD *v14; // rcx
  _QWORD *v15; // rax
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
  ECB = GetECB();
  v11.Simple = (LONG_PTR)ECB;
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
  *(_DWORD *)(v11.Simple + 4) = v12;
  v13 = dwScope - 1;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v21);
    *(_QWORD *)(v11.Simple + 72) = 0;
    v9 = ((__int64 (__fastcall *)(_QWORD))BuildConnectedDeviceList)((CLIENT_CALL_RETURN)v11.Simple);
    if ( !v9 )
      goto LABEL_44;
LABEL_43:
    FreeECB((CLIENT_CALL_RETURN)v11.Pointer);
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
          *(_QWORD *)(v11.Simple + 40));
      goto LABEL_44;
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 8) != 0 )
      WPP_SF_sq(
        v14[2],
        62,
        (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
        (unsigned int)v21,
        (char)lpNetResource);
    v15 = CopyNetResource((__int64)lpNetResource);
    *(_QWORD *)(v11.Simple + 104) = v15;
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v21);
      goto LABEL_37;
    }
    if ( _wcsicmp(lpNetResource->lpRemoteName, *((const wchar_t **)pGlobalNPCB + 5)) )
    {
      if ( (unsigned int)IsLanName((__int64)lpNetResource->lpRemoteName) == 1 )
        v16 = ((__int64 (__fastcall *)(_QWORD))BuildLanList)((CLIENT_CALL_RETURN)v11.Simple);
      else
        v16 = BuildShowMountList(v11.Simple);
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
  *lphEnum = (HANDLE)v11.Simple;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      64,
      (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
      (unsigned int)v21,
      v11.Simple);
  WSACleanup();
  return 0;
}

```

## disassembly

```asm
0x180008570  mov     [rsp-8+arg_0], rbx
0x180008575  mov     [rsp-8+arg_8], rsi
0x18000857a  push    rbp
0x18000857b  push    rdi
0x18000857c  push    r12
0x18000857e  push    r14
0x180008580  push    r15
0x180008582  lea     rbp, [rsp-100h]
0x18000858a  sub     rsp, 200h
0x180008591  mov     rax, cs:__security_cookie
0x180008598  xor     rax, rsp
0x18000859b  mov     [rbp+120h+var_30], rax
0x1800085a2  movsd   xmm0, qword ptr cs:aNpopenenum_0; "NPOpenEnum"
0x1800085aa  mov     r15d, r8d
0x1800085ad  mov     eax, dword ptr cs:aNpopenenum_0+7; "num"
0x1800085b3  mov     r14d, edx
0x1800085b6  mov     r12, [rbp+120h+lphEnum]
0x1800085bd  mov     ebx, ecx
0x1800085bf  movsd   qword ptr [rbp+120h+var_40], xmm0
0x1800085c7  lea     rcx, [rsp+220h+WSAData]; void *
0x1800085cc  xor     edx, edx; Val
0x1800085ce  mov     dword ptr [rbp+120h+var_40+7], eax
0x1800085d4  mov     r8d, 198h; Size
0x1800085da  mov     rsi, r9
0x1800085dd  call    memset_0
0x1800085e2  mov     ecx, 101h; wVersionRequested
0x1800085e7  mov     [rsp+220h+var_1F0], 0
0x1800085ef  lea     rdx, [rsp+220h+WSAData]; lpWSAData
0x1800085f4  call    cs:__imp_WSAStartup
0x1800085fb  nop     dword ptr [rax+rax+00h]
0x180008600  lea     rdi, WPP_GLOBAL_Control
0x180008607  test    eax, eax
0x180008609  jz      short loc_180008615
0x18000860b  mov     ebx, 4C6h
0x180008610  jmp     loc_180008917
0x180008615  lea     rcx, [rsp+220h+var_1F0]
0x18000861a  call    NfsNpIsClientRunning
0x18000861f  test    eax, eax
0x180008621  js      loc_1800088D8
0x180008627  cmp     [rsp+220h+var_1F0], 0
0x18000862c  jz      loc_1800088D8
0x180008632  call    GetECB
0x180008637  mov     rdi, rax
0x18000863a  test    rax, rax
0x18000863d  jnz     short loc_18000867C
0x18000863f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008646  lea     rdi, WPP_GLOBAL_Control
0x18000864d  cmp     rcx, rdi
0x180008650  jz      short loc_180008672
0x180008652  test    byte ptr [rcx+1Ch], 2
0x180008656  jz      short loc_180008672
0x180008658  mov     rcx, [rcx+10h]
0x18000865c  lea     edx, [rax+39h]
0x18000865f  lea     r9, [rbp+120h+var_40]
0x180008666  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000866d  call    WPP_SF_s
0x180008672  mov     ebx, 8
0x180008677  jmp     loc_18000890B
0x18000867c  mov     [rax], ebx
0x18000867e  test    r14d, r14d
0x180008681  mov     [rax+8], r15d
0x180008685  mov     eax, 1
0x18000868a  cmovnz  eax, r14d
0x18000868e  mov     [rdi+4], eax
0x180008691  sub     ebx, 1
0x180008694  jz      loc_180008829
0x18000869a  cmp     ebx, 1
0x18000869d  jnz     loc_18000888A
0x1800086a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086aa  lea     r14, WPP_GLOBAL_Control
0x1800086b1  mov     ebx, 8
0x1800086b6  cmp     rcx, r14
0x1800086b9  jz      short loc_1800086E1
0x1800086bb  test    [rcx+1Ch], bl
0x1800086be  jz      short loc_1800086E1
0x1800086c0  mov     rcx, [rcx+10h]
0x1800086c4  lea     edx, [rbx+33h]
0x1800086c7  lea     r9, [rbp+120h+var_40]
0x1800086ce  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800086d5  call    WPP_SF_s
0x1800086da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086e1  test    rsi, rsi
0x1800086e4  jnz     short loc_18000874E
0x1800086e6  cmp     rcx, r14
0x1800086e9  jz      short loc_180008703
0x1800086eb  test    [rcx+1Ch], bl
0x1800086ee  jz      short loc_180008703
0x1800086f0  mov     rcx, [rcx+10h]
0x1800086f4  lea     edx, [rsi+3Ch]
0x1800086f7  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800086fe  call    WPP_SF_
0x180008703  mov     rcx, rdi
0x180008706  call    BuildConfiguredLanList
0x18000870b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008712  cmp     rcx, r14
0x180008715  jz      loc_180008891
0x18000871b  test    [rcx+1Ch], bl
0x18000871e  jz      loc_180008891
0x180008724  mov     rax, [rdi+28h]
0x180008728  lea     r9, [rbp+120h+var_40]
0x18000872f  mov     rcx, [rcx+10h]
0x180008733  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000873a  mov     edx, 3Dh ; '='
0x18000873f  mov     [rsp+220h+var_200], rax
0x180008744  call    WPP_SF_sq
0x180008749  jmp     loc_180008891
0x18000874e  cmp     rcx, r14
0x180008751  jz      short loc_180008779
0x180008753  test    [rcx+1Ch], bl
0x180008756  jz      short loc_180008779
0x180008758  mov     rcx, [rcx+10h]
0x18000875c  lea     r9, [rbp+120h+var_40]
0x180008763  mov     edx, 3Eh ; '>'
0x180008768  mov     [rsp+220h+var_200], rsi
0x18000876d  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008774  call    WPP_SF_sq
0x180008779  mov     rcx, rsi
0x18000877c  call    CopyNetResource
0x180008781  mov     [rdi+68h], rax
0x180008785  test    rax, rax
0x180008788  jnz     short loc_1800087B8
0x18000878a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008791  cmp     rcx, r14
0x180008794  jz      short loc_180008808
0x180008796  test    byte ptr [rcx+1Ch], 2
0x18000879a  jz      short loc_180008808
0x18000879c  mov     rcx, [rcx+10h]
0x1800087a0  lea     edx, [rax+3Fh]
0x1800087a3  lea     r9, [rbp+120h+var_40]
0x1800087aa  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800087b1  call    WPP_SF_s
0x1800087b6  jmp     short loc_180008808
0x1800087b8  mov     rdx, cs:pGlobalNPCB
0x1800087bf  mov     rcx, [rsi+18h]; String1
0x1800087c3  mov     rdx, [rdx+28h]; String2
0x1800087c7  call    cs:__imp__wcsicmp
0x1800087ce  nop     dword ptr [rax+rax+00h]
0x1800087d3  test    eax, eax
0x1800087d5  jnz     short loc_1800087E1
0x1800087d7  mov     rcx, rdi
0x1800087da  call    BuildConfiguredLanList
0x1800087df  jmp     short loc_1800087FE
0x1800087e1  mov     rcx, [rsi+18h]
0x1800087e5  call    IsLanName
0x1800087ea  mov     rcx, rdi
0x1800087ed  cmp     eax, 1
0x1800087f0  jnz     short loc_1800087F9
0x1800087f2  call    BuildLanList
0x1800087f7  jmp     short loc_1800087FE
0x1800087f9  call    BuildShowMountList
0x1800087fe  mov     ebx, eax
0x180008800  test    eax, eax
0x180008802  jz      loc_180008891
0x180008808  mov     rax, cs:pGlobalNPCB
0x18000880f  mov     rcx, [rax+0A8h]; hMem
0x180008816  test    rcx, rcx
0x180008819  jz      short loc_180008876
0x18000881b  call    cs:__imp_GlobalFree
0x180008822  nop     dword ptr [rax+rax+00h]
0x180008827  jmp     short loc_180008876
0x180008829  mov     rcx, cs:WPP_GLOBAL_Control
0x180008830  lea     r14, WPP_GLOBAL_Control
0x180008837  cmp     rcx, r14
0x18000883a  jz      short loc_180008860
0x18000883c  mov     ebx, 8
0x180008841  test    [rcx+1Ch], bl
0x180008844  jz      short loc_180008860
0x180008846  mov     rcx, [rcx+10h]
0x18000884a  lea     edx, [rbx+32h]
0x18000884d  lea     r9, [rbp+120h+var_40]
0x180008854  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000885b  call    WPP_SF_s
0x180008860  mov     rcx, rdi
0x180008863  mov     qword ptr [rdi+48h], 0
0x18000886b  call    BuildConnectedDeviceList
0x180008870  mov     ebx, eax
0x180008872  test    eax, eax
0x180008874  jz      short loc_180008891
0x180008876  mov     rcx, rdi; hMem
0x180008879  call    FreeECB
0x18000887e  lea     rdi, WPP_GLOBAL_Control
0x180008885  jmp     loc_18000890B
0x18000888a  lea     r14, WPP_GLOBAL_Control
0x180008891  mov     [r12], rdi
0x180008895  mov     rcx, cs:WPP_GLOBAL_Control
0x18000889c  cmp     rcx, r14
0x18000889f  jz      short loc_1800088C8
0x1800088a1  test    byte ptr [rcx+1Ch], 1
0x1800088a5  jz      short loc_1800088C8
0x1800088a7  mov     rcx, [rcx+10h]
0x1800088ab  lea     r9, [rbp+120h+var_40]
0x1800088b2  mov     edx, 40h ; '@'
0x1800088b7  mov     [rsp+220h+var_200], rdi
0x1800088bc  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800088c3  call    WPP_SF_sq
0x1800088c8  call    cs:__imp_WSACleanup
0x1800088cf  nop     dword ptr [rax+rax+00h]
0x1800088d4  xor     eax, eax
0x1800088d6  jmp     short loc_180008953
0x1800088d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088df  cmp     rcx, rdi
0x1800088e2  jz      short loc_180008906
0x1800088e4  test    byte ptr [rcx+1Ch], 2
0x1800088e8  jz      short loc_180008906
0x1800088ea  mov     rcx, [rcx+10h]
0x1800088ee  lea     r9, [rbp+120h+var_40]
0x1800088f5  mov     edx, 38h ; '8'
0x1800088fa  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008901  call    WPP_SF_s
0x180008906  mov     ebx, 4C6h
0x18000890b  call    cs:__imp_WSACleanup
0x180008912  nop     dword ptr [rax+rax+00h]
0x180008917  mov     rcx, cs:WPP_GLOBAL_Control
0x18000891e  cmp     rcx, rdi
0x180008921  jz      short loc_180008949
0x180008923  test    byte ptr [rcx+1Ch], 2
0x180008927  jz      short loc_180008949
0x180008929  mov     rcx, [rcx+10h]
0x18000892d  lea     r9, [rbp+120h+var_40]
0x180008934  mov     edx, 41h ; 'A'
0x180008939  mov     dword ptr [rsp+220h+var_200], ebx
0x18000893d  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180008944  call    WPP_SF_sd
0x180008949  mov     qword ptr [r12], 0
0x180008951  mov     eax, ebx
0x180008953  mov     rcx, [rbp+120h+var_30]
0x18000895a  xor     rcx, rsp; StackCookie
0x18000895d  call    __security_check_cookie
0x180008962  lea     r11, [rsp+220h+var_20]
0x18000896a  mov     rbx, [r11+30h]
0x18000896e  mov     rsi, [r11+38h]
0x180008972  mov     rsp, r11
0x180008975  pop     r15
0x180008977  pop     r14
0x180008979  pop     r12
0x18000897b  pop     rdi
0x18000897c  pop     rbp
0x18000897d  retn
```
