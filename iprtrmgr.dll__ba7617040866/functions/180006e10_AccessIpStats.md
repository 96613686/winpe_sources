# AccessIpStats

- ea: `0x180006e10`
- end: `0x180007291`
- name: `AccessIpStats`
- size: `1153`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`
- `0x1800276bc`

## callees

- `0x180006e10`
- `0x18000ac60`
- `0x18000baa8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800071ca`
- `KERNEL32!LeaveCriticalSection` at `0x1800071ca`
- `KERNEL32!SetEvent` at `0x1800071bd`
- `KERNEL32!SetEvent` at `0x1800071bd`
- `KERNEL32!EnterCriticalSection` at `0x18000711a`
- `KERNEL32!EnterCriticalSection` at `0x18000711a`
- `IPHLPAPI!SetIpStatisticsEx` at `0x18000704f`
- `IPHLPAPI!SetIpStatisticsEx` at `0x18000704f`
- `IPHLPAPI!GetIpStatisticsEx` at `0x180006f94`
- `IPHLPAPI!GetIpStatisticsEx` at `0x180007202`
- `IPHLPAPI!GetIpStatisticsEx` at `0x180006f94`
- `IPHLPAPI!GetIpStatisticsEx` at `0x180007202`

## string_xrefs

- `0x180006e89`: `AccessIpStats`
- `0x180006ee6`: `Leaving: AccessIpStats`
- `0x18000703e`: `Leaving: AccessIpStats`
- `0x180007253`: `Leaving: AccessIpStats`
- `0x180006faf`: `AccessIpStats: Couldnt get IPSNMP info from stack to initiate set. Error %d`
- `0x180007015`: `AccessIpStats: Cant set TTL > 255`
- `0x180007066`: `AccessIpStats: Error %d setting TTL in stack`
- `0x1800070c9`: `AccessIpStats: Fwding state %d is invalid`
- `0x18000716e`: `AccessIpStats: Signalling worker to %ws forwarding`
- `0x180006f30`: `AccessIpStats: Query type %d is wrong`

## pseudocode

```c
__int64 __fastcall AccessIpStats(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  ULONG v7; // esi
  unsigned int v10; // eax
  MIB_IPSTATS_LH *v12; // rbx
  ULONG v13; // eax
  ULONG IpStatistics; // edi
  const wchar_t *v15; // r8
  __int64 *v16; // rdx
  const wchar_t *v17; // r8
  DWORD dwForwarding; // edx
  int *v19; // rax
  bool v20; // sf
  const wchar_t *v21; // r8
  HANDLE v22; // rcx
  MIB_IPSTATS_LH Statistics; // [rsp+30h] [rbp-888h] BYREF
  int v24; // [rsp+90h] [rbp-828h] BYREF
  _BYTE v25[2044]; // [rsp+94h] [rbp-824h] BYREF

  v7 = 2;
  if ( a7 != 33 )
    v7 = 23;
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"Entered: %ws", L"AccessIpStats");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v24);
  }
  v10 = *a4;
  *a4 = 100;
  if ( v10 < 0x64 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessIpStats");
    return 122;
  }
  *(_DWORD *)a5 = 3;
  v12 = (MIB_IPSTATS_LH *)(a5 + 8);
  if ( a1 == 1 )
  {
    if ( a7 == 87 )
      return 50;
    UpdateCache(0, a6);
    UpdateCache(1, a6);
    IpStatistics = GetIpStatisticsEx((PMIB_IPSTATS)(a5 + 8), v7);
    *(_DWORD *)(a5 + 88) = g_ulNumInterfaces;
    *(_DWORD *)(a5 + 96) = 0;
    if ( qword_18008C7E8 )
      *(_DWORD *)(a5 + 96) = *(_DWORD *)qword_18008C7E8;
    *(_DWORD *)(a5 + 92) = 0;
    if ( g_IpInfo )
      *(_DWORD *)(a5 + 92) = *(_DWORD *)g_IpInfo;
    goto LABEL_52;
  }
  if ( a1 == 5 )
  {
    memset_0(&Statistics, 0, sizeof(Statistics));
    v13 = GetIpStatisticsEx(&Statistics, v7);
    IpStatistics = v13;
    if ( v13 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return IpStatistics;
      LOWORD(v24) = 0;
      FormatRRASErrorString(&v24, L"AccessIpStats: Couldnt get IPSNMP info from stack to initiate set. Error %d", v13);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        return IpStatistics;
      v15 = (const wchar_t *)&v24;
      v16 = RasRtrMgrTraceError;
      goto LABEL_54;
    }
    if ( *(_DWORD *)(a5 + 12) != -1 )
    {
      if ( *(_DWORD *)(a5 + 12) > 0xFFu )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return 13;
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"AccessIpStats: Cant set TTL > 255");
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return 13;
        v17 = L"Leaving: AccessIpStats";
LABEL_34:
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v17);
        return 13;
      }
      IpStatistics = SetIpStatisticsEx(v12, v7);
      if ( IpStatistics )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v24) = 0;
          FormatRRASErrorString(&v24, L"AccessIpStats: Error %d setting TTL in stack", IpStatistics);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v24);
        }
      }
    }
    if ( v12->dwForwarding != -1 )
    {
      if ( v12->dwForwarding - 1 > 1 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return 13;
        LOWORD(v24) = 0;
        FormatRRASErrorString(&v24, L"AccessIpStats: Fwding state %d is invalid");
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          return 13;
        v17 = (const wchar_t *)&v24;
        goto LABEL_34;
      }
      EnterCriticalSection(&g_csFwdState);
      dwForwarding = v12->dwForwarding;
      v19 = &g_bEnableFwdRequestV4;
      if ( a7 != 33 )
        v19 = &g_bEnableFwdRequestV6;
      v20 = (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL;
      *v19 = v12->dwForwarding == 1;
      if ( v20 )
      {
        v21 = L"enable";
        LOWORD(v24) = 0;
        if ( dwForwarding != 1 )
          v21 = L"disable";
        FormatRRASErrorString(&v24, L"AccessIpStats: Signalling worker to %ws forwarding", v21);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v24);
      }
      v22 = g_hSetForwardingEventV6;
      if ( a7 == 33 )
        v22 = g_hSetForwardingEventV4;
      SetEvent(v22);
      LeaveCriticalSection(&g_csFwdState);
    }
LABEL_52:
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
      return IpStatistics;
    v16 = RasRtrmgrTraceInfo;
    v15 = L"Leaving: AccessIpStats";
LABEL_54:
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, v16, v15);
    return IpStatistics;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v24) = 0;
    FormatRRASErrorString(&v24, L"AccessIpStats: Query type %d is wrong", a1);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v24);
  }
  return 87;
}

```

## disassembly

```asm
0x180006e10  mov     [rsp+arg_8], rbx
0x180006e15  mov     [rsp+arg_10], rsi
0x180006e1a  push    rdi
0x180006e1b  push    r12
0x180006e1d  push    r15
0x180006e1f  sub     rsp, 8A0h
0x180006e26  mov     rax, cs:__security_cookie
0x180006e2d  xor     rax, rsp
0x180006e30  mov     [rsp+8B8h+var_28], rax
0x180006e38  cmp     [rsp+8B8h+arg_30], 21h ; '!'
0x180006e40  mov     esi, 2
0x180006e45  mov     r15, [rsp+8B8h+arg_20]
0x180006e4d  mov     edi, ecx
0x180006e4f  mov     r12, [rsp+8B8h+arg_28]
0x180006e57  lea     rcx, [rsp+8B8h+var_824]; void *
0x180006e5f  mov     r8d, 7FCh; Size
0x180006e65  mov     rbx, r9
0x180006e68  lea     eax, [rsi+15h]
0x180006e6b  cmovnz  esi, eax
0x180006e6e  xor     eax, eax
0x180006e70  xor     edx, edx; Val
0x180006e72  mov     [rsp+8B8h+var_828], eax
0x180006e79  call    memset_0
0x180006e7e  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180006e85  jge     short loc_180006ED0
0x180006e87  xor     eax, eax
0x180006e89  lea     r8, aAccessipstats; "AccessIpStats"
0x180006e90  lea     rdx, aEnteredWs; "Entered: %ws"
0x180006e97  mov     word ptr [rsp+8B8h+var_828], ax
0x180006e9f  lea     rcx, [rsp+8B8h+var_828]
0x180006ea7  call    FormatRRASErrorString
0x180006eac  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180006eb3  jge     short loc_180006ED0
0x180006eb5  lea     r8, [rsp+8B8h+var_828]
0x180006ebd  lea     rdx, RasRtrmgrTraceInfo
0x180006ec4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006ecb  call    McTemplateU0z_EventWriteTransfer
0x180006ed0  mov     eax, [rbx]
0x180006ed2  mov     dword ptr [rbx], 64h ; 'd'
0x180006ed8  cmp     eax, 64h ; 'd'
0x180006edb  jnb     short loc_180006F0A
0x180006edd  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180006ee4  jz      short loc_180006F00
0x180006ee6  lea     r8, aLeavingAccessi_5; "Leaving: AccessIpStats"
0x180006eed  lea     rdx, RasRtrmgrTraceInfo
0x180006ef4  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006efb  call    McTemplateU0z_EventWriteTransfer
0x180006f00  mov     eax, 7Ah ; 'z'
0x180006f05  jmp     loc_180007268
0x180006f0a  mov     eax, edi
0x180006f0c  mov     dword ptr [r15], 3
0x180006f13  lea     rbx, [r15+8]
0x180006f17  sub     eax, 1
0x180006f1a  jz      loc_1800071D2
0x180006f20  cmp     eax, 4
0x180006f23  jz      short loc_180006F7D
0x180006f25  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180006f2c  jz      short loc_180006F73
0x180006f2e  xor     eax, eax
0x180006f30  lea     rdx, aAccessipstatsQ; "AccessIpStats: Query type %d is wrong"
0x180006f37  mov     r8d, edi
0x180006f3a  mov     word ptr [rsp+8B8h+var_828], ax
0x180006f42  lea     rcx, [rsp+8B8h+var_828]
0x180006f4a  call    FormatRRASErrorString
0x180006f4f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180006f56  jz      short loc_180006F73
0x180006f58  lea     r8, [rsp+8B8h+var_828]
0x180006f60  lea     rdx, RasRtrMgrTraceError
0x180006f67  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180006f6e  call    McTemplateU0z_EventWriteTransfer
0x180006f73  mov     eax, 57h ; 'W'
0x180006f78  jmp     loc_180007268
0x180006f7d  xor     edx, edx; Val
0x180006f7f  lea     rcx, [rsp+8B8h+Statistics]; void *
0x180006f84  lea     r8d, [rdx+5Ch]; Size
0x180006f88  call    memset_0
0x180006f8d  mov     edx, esi; Family
0x180006f8f  lea     rcx, [rsp+8B8h+Statistics]; Statistics
0x180006f94  call    cs:__imp_GetIpStatisticsEx
0x180006f9a  mov     edi, eax
0x180006f9c  test    eax, eax
0x180006f9e  jz      short loc_180006FEF
0x180006fa0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180006fa7  jz      loc_180007266
0x180006fad  xor     ecx, ecx
0x180006faf  lea     rdx, aAccessipstatsC; "AccessIpStats: Couldnt get IPSNMP info "...
0x180006fb6  mov     word ptr [rsp+8B8h+var_828], cx
0x180006fbe  mov     r8d, eax
0x180006fc1  lea     rcx, [rsp+8B8h+var_828]
0x180006fc9  call    FormatRRASErrorString
0x180006fce  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180006fd5  jz      loc_180007266
0x180006fdb  lea     r8, [rsp+8B8h+var_828]
0x180006fe3  lea     rdx, RasRtrMgrTraceError
0x180006fea  jmp     loc_18000725A
0x180006fef  or      r15d, 0FFFFFFFFh
0x180006ff3  cmp     [rbx+4], r15d
0x180006ff7  jz      loc_1800070A9
0x180006ffd  cmp     dword ptr [rbx+4], 0FFh
0x180007004  jbe     short loc_18000704A
0x180007006  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18000700d  test    al, 80h
0x18000700f  jz      loc_180007109
0x180007015  lea     r8, aAccessipstatsC_0; "AccessIpStats: Cant set TTL > 255"
0x18000701c  lea     rdx, RasRtrmgrTraceInfo
0x180007023  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000702a  call    McTemplateU0z_EventWriteTransfer
0x18000702f  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180007036  test    al, 80h
0x180007038  jz      loc_180007109
0x18000703e  lea     r8, aLeavingAccessi_5; "Leaving: AccessIpStats"
0x180007045  jmp     loc_1800070F6
0x18000704a  mov     edx, esi; Family
0x18000704c  mov     rcx, rbx; Statistics
0x18000704f  call    cs:__imp_SetIpStatisticsEx
0x180007055  mov     edi, eax
0x180007057  test    eax, eax
0x180007059  jz      short loc_1800070A9
0x18000705b  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180007062  jz      short loc_1800070A9
0x180007064  xor     eax, eax
0x180007066  lea     rdx, aAccessipstatsE; "AccessIpStats: Error %d setting TTL in "...
0x18000706d  mov     r8d, edi
0x180007070  mov     word ptr [rsp+8B8h+var_828], ax
0x180007078  lea     rcx, [rsp+8B8h+var_828]
0x180007080  call    FormatRRASErrorString
0x180007085  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18000708c  jz      short loc_1800070A9
0x18000708e  lea     r8, [rsp+8B8h+var_828]
0x180007096  lea     rdx, RasRtrMgrTraceError
0x18000709d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800070a4  call    McTemplateU0z_EventWriteTransfer
0x1800070a9  mov     r8d, [rbx]
0x1800070ac  cmp     r8d, r15d
0x1800070af  jz      loc_180007243
0x1800070b5  lea     eax, [r8-1]
0x1800070b9  cmp     eax, 1
0x1800070bc  jbe     short loc_180007113
0x1800070be  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800070c5  jge     short loc_180007109
0x1800070c7  xor     eax, eax
0x1800070c9  lea     rdx, aAccessipstatsF; "AccessIpStats: Fwding state %d is inval"...
0x1800070d0  lea     rcx, [rsp+8B8h+var_828]
0x1800070d8  mov     word ptr [rsp+8B8h+var_828], ax
0x1800070e0  call    FormatRRASErrorString
0x1800070e5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800070ec  jge     short loc_180007109
0x1800070ee  lea     r8, [rsp+8B8h+var_828]
0x1800070f6  lea     rdx, RasRtrmgrTraceInfo
0x1800070fd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007104  call    McTemplateU0z_EventWriteTransfer
0x180007109  mov     eax, 0Dh
0x18000710e  jmp     loc_180007268
0x180007113  lea     rcx, g_csFwdState; lpCriticalSection
0x18000711a  call    cs:__imp_EnterCriticalSection
0x180007120  mov     edx, [rbx]
0x180007122  lea     r8, g_bEnableFwdRequestV6
0x180007129  xor     ecx, ecx
0x18000712b  lea     rax, g_bEnableFwdRequestV4
0x180007132  cmp     edx, 1
0x180007135  setz    cl
0x180007138  cmp     [rsp+8B8h+arg_30], 21h ; '!'
0x180007140  cmovnz  rax, r8
0x180007144  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x18000714b  mov     [rax], ecx
0x18000714d  jge     short loc_1800071A6
0x18000714f  xor     eax, eax
0x180007151  lea     r8, aEnable; "enable"
0x180007158  cmp     edx, 1
0x18000715b  mov     word ptr [rsp+8B8h+var_828], ax
0x180007163  lea     rax, aDisable; "disable"
0x18000716a  cmovnz  r8, rax
0x18000716e  lea     rdx, aAccessipstatsS; "AccessIpStats: Signalling worker to %ws"...
0x180007175  lea     rcx, [rsp+8B8h+var_828]
0x18000717d  call    FormatRRASErrorString
0x180007182  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180007189  jge     short loc_1800071A6
0x18000718b  lea     r8, [rsp+8B8h+var_828]
0x180007193  lea     rdx, RasRtrmgrTraceInfo
0x18000719a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800071a1  call    McTemplateU0z_EventWriteTransfer
0x1800071a6  mov     rcx, cs:g_hSetForwardingEventV6
0x1800071ad  cmp     [rsp+8B8h+arg_30], 21h ; '!'
0x1800071b5  cmovz   rcx, cs:g_hSetForwardingEventV4; hEvent
0x1800071bd  call    cs:__imp_SetEvent
0x1800071c3  lea     rcx, g_csFwdState; lpCriticalSection
0x1800071ca  call    cs:__imp_LeaveCriticalSection
0x1800071d0  jmp     short loc_180007243
0x1800071d2  cmp     [rsp+8B8h+arg_30], 57h ; 'W'
0x1800071da  jnz     short loc_1800071E6
0x1800071dc  mov     eax, 32h ; '2'
0x1800071e1  jmp     loc_180007268
0x1800071e6  mov     rdx, r12
0x1800071e9  xor     ecx, ecx
0x1800071eb  call    UpdateCache
0x1800071f0  mov     rdx, r12
0x1800071f3  mov     ecx, 1
0x1800071f8  call    UpdateCache
0x1800071fd  mov     edx, esi; Family
0x1800071ff  mov     rcx, rbx; Statistics
0x180007202  call    cs:__imp_GetIpStatisticsEx
0x180007208  mov     ecx, cs:g_ulNumInterfaces
0x18000720e  mov     edi, eax
0x180007210  mov     [rbx+50h], ecx
0x180007213  mov     dword ptr [rbx+58h], 0
0x18000721a  mov     rcx, cs:qword_18008C7E8
0x180007221  test    rcx, rcx
0x180007224  jz      short loc_18000722B
0x180007226  mov     ecx, [rcx]
0x180007228  mov     [rbx+58h], ecx
0x18000722b  mov     dword ptr [rbx+54h], 0
0x180007232  mov     rax, cs:g_IpInfo
0x180007239  test    rax, rax
0x18000723c  jz      short loc_180007243
0x18000723e  mov     eax, [rax]
0x180007240  mov     [rbx+54h], eax
0x180007243  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000724a  jz      short loc_180007266
0x18000724c  lea     rdx, RasRtrmgrTraceInfo
0x180007253  lea     r8, aLeavingAccessi_5; "Leaving: AccessIpStats"
0x18000725a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180007261  call    McTemplateU0z_EventWriteTransfer
0x180007266  mov     eax, edi
0x180007268  mov     rcx, [rsp+8B8h+var_28]
0x180007270  xor     rcx, rsp; StackCookie
0x180007273  call    __security_check_cookie
0x180007278  lea     r11, [rsp+8B8h+var_18]
0x180007280  mov     rbx, [r11+28h]
0x180007284  mov     rsi, [r11+30h]
0x180007288  mov     rsp, r11
0x18000728b  pop     r15
0x18000728d  pop     r12
0x18000728f  pop     rdi
0x180007290  retn
```
