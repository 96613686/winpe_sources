# AccessRouteShorter

- ea: `0x180009150`
- end: `0x1800095aa`
- name: `AccessRouteShorter`
- size: `1114`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026f54`
- `0x1800271cc`
- `0x180027444`

## callees

- `0x180009150`
- `0x18000a908`
- `0x18000ac60`
- `0x180051ec8`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180009382`
- `KERNEL32!HeapFree` at `0x180009519`
- `KERNEL32!HeapFree` at `0x18000952b`
- `KERNEL32!HeapFree` at `0x180009382`
- `KERNEL32!HeapFree` at `0x180009519`
- `KERNEL32!HeapFree` at `0x18000952b`
- `KERNEL32!HeapAlloc` at `0x1800092b7`
- `KERNEL32!HeapAlloc` at `0x180009340`
- `KERNEL32!HeapAlloc` at `0x1800092b7`
- `KERNEL32!HeapAlloc` at `0x180009340`
- `WS2_32!__imp_ntohl` at `0x1800093a1`
- `WS2_32!__imp_ntohl` at `0x1800093a1`
- `rtm!RtmGetLessSpecificDestination` at `0x18000947c`
- `rtm!RtmGetLessSpecificDestination` at `0x1800094c7`
- `rtm!RtmGetLessSpecificDestination` at `0x18000947c`
- `rtm!RtmGetLessSpecificDestination` at `0x1800094c7`
- `rtm!RtmReleaseDestInfo` at `0x18000948e`
- `rtm!RtmReleaseDestInfo` at `0x1800094d9`
- `rtm!RtmReleaseDestInfo` at `0x18000948e`
- `rtm!RtmReleaseDestInfo` at `0x1800094d9`
- `rtm!RtmGetMostSpecificDestination` at `0x180009440`
- `rtm!RtmGetMostSpecificDestination` at `0x180009440`

## string_xrefs

- `0x1800091c7`: `AccessRouteShorter`
- `0x180009288`: `Leaving: AccessRouteShorter`
- `0x1800092ce`: `Leaving: AccessRouteShorter`
- `0x180009316`: `Leaving: AccessRouteShorter`
- `0x180009357`: `Leaving: AccessRouteShorter`
- `0x18000953a`: `Leaving: AccessRouteShorter`
- `0x18000955e`: `Leaving: AccessRouteShorter`

## pseudocode

```c
__int64 __fastcall AccessRouteShorter(
        int a1,
        unsigned int a2,
        _DWORD *a3,
        unsigned int *a4,
        __int64 a5,
        int a6,
        int a7)
{
  char v11; // r9
  unsigned int v13; // eax
  unsigned int v14; // r14d
  __int64 v15; // r12
  unsigned int v16; // ebx
  char v17; // r9
  struct _RTM_DEST_INFO *DestInfo; // rdi
  struct _RTM_DEST_INFO *v19; // r15
  u_long v20; // ecx
  u_long v21; // edx
  USHORT v22; // ax
  u_long v23; // r8d
  int v24; // edx
  int v25; // ecx
  DWORD MostSpecificDestination; // ebx
  unsigned int v27; // esi
  HANDLE v28; // rcx
  bool v29; // cf
  unsigned int v30; // [rsp+30h] [rbp-858h] BYREF
  unsigned int dwBytes; // [rsp+34h] [rbp-854h] BYREF
  struct _RTM_NET_ADDRESS dwBytes_4; // [rsp+38h] [rbp-850h] BYREF
  int v33; // [rsp+50h] [rbp-838h] BYREF
  _BYTE v34[2044]; // [rsp+54h] [rbp-834h] BYREF

  dwBytes = 0;
  v33 = 0;
  memset(&dwBytes_4, 0, sizeof(dwBytes_4));
  memset_0(v34, 0, sizeof(v34));
  v11 = Microsoft_Windows_RRASEnableBits;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v33) = 0;
    FormatRRASErrorString(&v33, L"Entered: %ws", L"AccessRouteShorter");
    v11 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v33);
      v11 = Microsoft_Windows_RRASEnableBits;
    }
  }
  if ( a7 == 87 )
    return 50;
  v13 = *a4;
  v30 = 0;
  if ( v13 <= 0xC )
  {
    v15 = 0;
    v14 = 0;
  }
  else
  {
    v14 = (v13 - 12) >> 6;
    v15 = a5 + 8;
    *(_DWORD *)(a5 + 8) = 0;
    v11 = Microsoft_Windows_RRASEnableBits;
  }
  if ( (a2 >> 2) - 1 >= 4 && a1 == 1 )
  {
    v16 = RTMSIZEOFDESTINFO(g_rtmProfile.NumberOfViews, &dwBytes);
    if ( v16 )
    {
      if ( v17 < 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessRouteShorter");
      return v16;
    }
    DestInfo = (struct _RTM_DEST_INFO *)HeapAlloc(IPRouterHeap, 0, dwBytes);
    if ( !DestInfo )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessRouteShorter");
      return 8;
    }
    dwBytes = 0;
    v16 = RTMSIZEOFDESTINFO(g_rtmProfile.NumberOfViews, &dwBytes);
    if ( v16 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessRouteShorter");
LABEL_26:
      HeapFree(IPRouterHeap, 0, DestInfo);
      return v16;
    }
    v19 = (struct _RTM_DEST_INFO *)HeapAlloc(IPRouterHeap, 0, dwBytes);
    if ( !v19 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasRtrmgrTraceInfo,
          L"Leaving: AccessRouteShorter");
      v16 = 8;
      goto LABEL_26;
    }
    v20 = a3[2];
    dwBytes_4.AddressFamily = 2;
    *(_DWORD *)dwBytes_4.AddrBits = a3[1];
    v21 = ntohl(v20);
    v22 = 0;
    dwBytes_4.NumBits = 0;
    if ( (v21 & 0x10000) != 0 )
    {
      v22 = 16;
      dwBytes_4.NumBits = 16;
    }
    v23 = v21 << 16;
    if ( (v21 & 0x10000) == 0 )
      v23 = v21;
    if ( (v23 & 0x100) != 0 )
    {
      v22 += 8;
      dwBytes_4.NumBits = v22;
    }
    v24 = v23 << 8;
    if ( (v23 & 0x100) == 0 )
      v24 = v23;
    if ( (v24 & 0x10) != 0 )
    {
      v22 += 4;
      dwBytes_4.NumBits = v22;
    }
    v25 = 16 * v24;
    if ( (v24 & 0x10) == 0 )
      v25 = v24;
    for ( ; v25; v25 *= 2 )
      dwBytes_4.NumBits = ++v22;
    MostSpecificDestination = RtmGetMostSpecificDestination(g_hLocalRoute, &dwBytes_4, a3[4], a3[3], DestInfo);
    while ( !MostSpecificDestination )
    {
      AddRouteRowsOnDest(&DestInfo->DestHandle, (__int64)a3, (__int64)&v30, v14, v15);
      MostSpecificDestination = RtmGetLessSpecificDestination(g_hLocalRoute, DestInfo->DestHandle, a3[4], a3[3], v19);
      RtmReleaseDestInfo(g_hLocalRoute, DestInfo);
      if ( MostSpecificDestination )
        break;
      AddRouteRowsOnDest(&v19->DestHandle, (__int64)a3, (__int64)&v30, v14, v15);
      MostSpecificDestination = RtmGetLessSpecificDestination(g_hLocalRoute, v19->DestHandle, a3[4], a3[3], DestInfo);
      RtmReleaseDestInfo(g_hLocalRoute, v19);
    }
    v27 = 0;
    v28 = IPRouterHeap;
    if ( MostSpecificDestination != 1168 )
      v27 = MostSpecificDestination;
    v29 = v14 < v30;
    *a4 = (v30 << 6) + 12;
    if ( v29 )
      v27 = 122;
    HeapFree(v28, 0, DestInfo);
    HeapFree(IPRouterHeap, 0, v19);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessRouteShorter");
    return v27;
  }
  else
  {
    if ( v11 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AccessRouteShorter");
    return 87;
  }
}

```

## disassembly

```asm
0x180009150  mov     [rsp+arg_0], rbx
0x180009155  mov     [rsp+arg_8], rsi
0x18000915a  push    rdi
0x18000915b  push    r12
0x18000915d  push    r13
0x18000915f  push    r14
0x180009161  push    r15
0x180009163  sub     rsp, 860h
0x18000916a  mov     rax, cs:__security_cookie
0x180009171  xor     rax, rsp
0x180009174  mov     [rsp+888h+var_38], rax
0x18000917c  mov     r12, [rsp+888h+arg_20]
0x180009184  mov     rsi, r8
0x180009187  mov     ebx, edx
0x180009189  mov     edi, ecx
0x18000918b  xor     r15d, r15d
0x18000918e  lea     rcx, [rsp+888h+var_834]; void *
0x180009193  xorps   xmm0, xmm0
0x180009196  mov     dword ptr [rsp+888h+dwBytes.AddressFamily], r15d
0x18000919b  xor     eax, eax
0x18000919d  mov     [rsp+888h+var_838], r15d
0x1800091a2  xor     edx, edx; Val
0x1800091a4  mov     [rsp+888h+var_840], eax
0x1800091a8  mov     r8d, 7FCh; Size
0x1800091ae  mov     r13, r9
0x1800091b1  movups  xmmword ptr [rsp+888h+dwBytes.AddrBits], xmm0
0x1800091b6  call    memset_0
0x1800091bb  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x1800091c2  test    r9b, r9b
0x1800091c5  jns     short loc_180009210
0x1800091c7  lea     r8, aAccessroutesho; "AccessRouteShorter"
0x1800091ce  mov     word ptr [rsp+888h+var_838], r15w
0x1800091d4  lea     rdx, aEnteredWs; "Entered: %ws"
0x1800091db  lea     rcx, [rsp+888h+var_838]
0x1800091e0  call    FormatRRASErrorString
0x1800091e5  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x1800091ec  test    r9b, r9b
0x1800091ef  jns     short loc_180009210
0x1800091f1  lea     r8, [rsp+888h+var_838]
0x1800091f6  lea     rdx, RasRtrmgrTraceInfo
0x1800091fd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009204  call    McTemplateU0z_EventWriteTransfer
0x180009209  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x180009210  cmp     [rsp+888h+arg_30], 57h ; 'W'
0x180009218  jnz     short loc_180009224
0x18000921a  mov     eax, 32h ; '2'
0x18000921f  jmp     loc_18000957D
0x180009224  mov     eax, [r13+0]
0x180009228  mov     [rsp+888h+var_858], r15d
0x18000922d  cmp     eax, 0Ch
0x180009230  jbe     short loc_18000924B
0x180009232  lea     r14d, [rax-0Ch]
0x180009236  shr     r14d, 6
0x18000923a  add     r12, 8
0x18000923e  mov     [r12], r15d
0x180009242  mov     r9, cs:Microsoft_Windows_RRASEnableBits
0x180009249  jmp     short loc_180009251
0x18000924b  mov     r12, r15
0x18000924e  mov     r14d, r15d
0x180009251  shr     ebx, 2
0x180009254  mov     eax, 1
0x180009259  sub     ebx, eax
0x18000925b  cmp     ebx, 4
0x18000925e  jb      loc_180009558
0x180009264  cmp     edi, eax
0x180009266  jnz     loc_180009558
0x18000926c  mov     ecx, cs:g_rtmProfile.NumberOfViews
0x180009272  lea     rdx, [rsp+888h+dwBytes]
0x180009277  call    RTMSIZEOFDESTINFO
0x18000927c  mov     ebx, eax
0x18000927e  test    eax, eax
0x180009280  jz      short loc_1800092A9
0x180009282  test    r9b, 80h
0x180009286  jz      short loc_1800092A2
0x180009288  lea     r8, aLeavingAccessr_1; "Leaving: AccessRouteShorter"
0x18000928f  lea     rdx, RasRtrmgrTraceInfo
0x180009296  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000929d  call    McTemplateU0z_EventWriteTransfer
0x1800092a2  mov     eax, ebx
0x1800092a4  jmp     loc_18000957D
0x1800092a9  mov     r8d, dword ptr [rsp+888h+dwBytes.AddressFamily]; dwBytes
0x1800092ae  xor     edx, edx; dwFlags
0x1800092b0  mov     rcx, cs:IPRouterHeap; hHeap
0x1800092b7  call    cs:__imp_HeapAlloc
0x1800092bd  mov     rdi, rax
0x1800092c0  test    rax, rax
0x1800092c3  jnz     short loc_1800092F2
0x1800092c5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x1800092cc  jz      short loc_1800092E8
0x1800092ce  lea     r8, aLeavingAccessr_1; "Leaving: AccessRouteShorter"
0x1800092d5  lea     rdx, RasRtrmgrTraceInfo
0x1800092dc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800092e3  call    McTemplateU0z_EventWriteTransfer
0x1800092e8  mov     eax, 8
0x1800092ed  jmp     loc_18000957D
0x1800092f2  mov     ecx, cs:g_rtmProfile.NumberOfViews
0x1800092f8  lea     rdx, [rsp+888h+dwBytes]
0x1800092fd  mov     dword ptr [rsp+888h+dwBytes.AddressFamily], r15d
0x180009302  call    RTMSIZEOFDESTINFO
0x180009307  mov     ebx, eax
0x180009309  test    eax, eax
0x18000930b  jz      short loc_180009332
0x18000930d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180009314  jz      short loc_180009376
0x180009316  lea     r8, aLeavingAccessr_1; "Leaving: AccessRouteShorter"
0x18000931d  lea     rdx, RasRtrmgrTraceInfo
0x180009324  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000932b  call    McTemplateU0z_EventWriteTransfer
0x180009330  jmp     short loc_180009376
0x180009332  mov     r8d, dword ptr [rsp+888h+dwBytes.AddressFamily]; dwBytes
0x180009337  xor     edx, edx; dwFlags
0x180009339  mov     rcx, cs:IPRouterHeap; hHeap
0x180009340  call    cs:__imp_HeapAlloc
0x180009346  mov     r15, rax
0x180009349  test    rax, rax
0x18000934c  jnz     short loc_18000938D
0x18000934e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180009355  jz      short loc_180009371
0x180009357  lea     r8, aLeavingAccessr_1; "Leaving: AccessRouteShorter"
0x18000935e  lea     rdx, RasRtrmgrTraceInfo
0x180009365  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000936c  call    McTemplateU0z_EventWriteTransfer
0x180009371  mov     ebx, 8
0x180009376  mov     rcx, cs:IPRouterHeap; hHeap
0x18000937d  mov     r8, rdi; lpMem
0x180009380  xor     edx, edx; dwFlags
0x180009382  call    cs:__imp_HeapFree
0x180009388  jmp     loc_1800092A2
0x18000938d  mov     ecx, [rsi+8]; netlong
0x180009390  mov     eax, 2
0x180009395  mov     word ptr [rsp+888h+dwBytes.AddrBits], ax
0x18000939a  mov     eax, [rsi+4]
0x18000939d  mov     dword ptr [rsp+888h+dwBytes.AddrBits+4], eax
0x1800093a1  call    cs:__imp_ntohl
0x1800093a7  mov     edx, eax
0x1800093a9  xor     eax, eax
0x1800093ab  mov     ecx, edx
0x1800093ad  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x1800093b2  lea     r10d, [rax+10h]
0x1800093b6  and     ecx, 10000h
0x1800093bc  jz      short loc_1800093C7
0x1800093be  movzx   eax, r10w
0x1800093c2  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x1800093c7  mov     r8d, edx
0x1800093ca  shl     r8d, 10h
0x1800093ce  test    ecx, ecx
0x1800093d0  cmovz   r8d, edx
0x1800093d4  mov     r9d, r8d
0x1800093d7  and     r9d, 100h
0x1800093de  jz      short loc_1800093E9
0x1800093e0  add     ax, 8
0x1800093e4  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x1800093e9  mov     edx, r8d
0x1800093ec  shl     edx, 8
0x1800093ef  test    r9d, r9d
0x1800093f2  cmovz   edx, r8d
0x1800093f6  mov     r8d, edx
0x1800093f9  and     r8d, r10d
0x1800093fc  jz      short loc_180009407
0x1800093fe  add     ax, 4
0x180009402  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x180009407  mov     ecx, edx
0x180009409  shl     ecx, 4
0x18000940c  test    r8d, r8d
0x18000940f  cmovz   ecx, edx
0x180009412  test    ecx, ecx
0x180009414  jz      short loc_180009427
0x180009416  mov     edx, 1
0x18000941b  add     ax, dx
0x18000941e  mov     word ptr [rsp+888h+dwBytes.AddrBits+2], ax
0x180009423  add     ecx, ecx
0x180009425  jnz     short loc_18000941B
0x180009427  mov     r9d, [rsi+0Ch]; TargetViews
0x18000942b  lea     rdx, [rsp+888h+dwBytes.AddrBits]; DestAddress
0x180009430  mov     r8d, [rsi+10h]; ProtocolId
0x180009434  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18000943b  mov     [rsp+888h+DestInfo], rdi; DestInfo
0x180009440  call    cs:__imp_RtmGetMostSpecificDestination
0x180009446  mov     ebx, eax
0x180009448  jmp     loc_1800094DF
0x18000944d  mov     r9d, r14d
0x180009450  mov     [rsp+888h+DestInfo], r12
0x180009455  lea     r8, [rsp+888h+var_858]
0x18000945a  mov     rdx, rsi
0x18000945d  mov     rcx, rdi
0x180009460  call    AddRouteRowsOnDest
0x180009465  mov     r9d, [rsi+0Ch]; TargetViews
0x180009469  mov     r8d, [rsi+10h]; ProtocolId
0x18000946d  mov     rdx, [rdi]; DestHandle
0x180009470  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180009477  mov     [rsp+888h+DestInfo], r15; DestInfo
0x18000947c  call    cs:__imp_RtmGetLessSpecificDestination
0x180009482  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x180009489  mov     rdx, rdi; DestInfo
0x18000948c  mov     ebx, eax
0x18000948e  call    cs:__imp_RtmReleaseDestInfo
0x180009494  test    ebx, ebx
0x180009496  jnz     short loc_1800094E7
0x180009498  mov     r9d, r14d
0x18000949b  mov     [rsp+888h+DestInfo], r12
0x1800094a0  lea     r8, [rsp+888h+var_858]
0x1800094a5  mov     rdx, rsi
0x1800094a8  mov     rcx, r15
0x1800094ab  call    AddRouteRowsOnDest
0x1800094b0  mov     r9d, [rsi+0Ch]; TargetViews
0x1800094b4  mov     r8d, [rsi+10h]; ProtocolId
0x1800094b8  mov     rdx, [r15]; DestHandle
0x1800094bb  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x1800094c2  mov     [rsp+888h+DestInfo], rdi; DestInfo
0x1800094c7  call    cs:__imp_RtmGetLessSpecificDestination
0x1800094cd  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x1800094d4  mov     rdx, r15; DestInfo
0x1800094d7  mov     ebx, eax
0x1800094d9  call    cs:__imp_RtmReleaseDestInfo
0x1800094df  test    ebx, ebx
0x1800094e1  jz      loc_18000944D
0x1800094e7  mov     eax, [rsp+888h+var_858]
0x1800094eb  xor     esi, esi
0x1800094ed  mov     rcx, cs:IPRouterHeap; hHeap
0x1800094f4  cmp     ebx, 490h
0x1800094fa  mov     r8, rdi; lpMem
0x1800094fd  cmovnz  esi, ebx
0x180009500  shl     eax, 6
0x180009503  add     eax, 0Ch
0x180009506  cmp     r14d, [rsp+888h+var_858]
0x18000950b  mov     [r13+0], eax
0x18000950f  mov     eax, 7Ah ; 'z'
0x180009514  cmovb   esi, eax
0x180009517  xor     edx, edx; dwFlags
0x180009519  call    cs:__imp_HeapFree
0x18000951f  mov     rcx, cs:IPRouterHeap; hHeap
0x180009526  mov     r8, r15; lpMem
0x180009529  xor     edx, edx; dwFlags
0x18000952b  call    cs:__imp_HeapFree
0x180009531  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180009538  jz      short loc_180009554
0x18000953a  lea     r8, aLeavingAccessr_1; "Leaving: AccessRouteShorter"
0x180009541  lea     rdx, RasRtrmgrTraceInfo
0x180009548  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000954f  call    McTemplateU0z_EventWriteTransfer
0x180009554  mov     eax, esi
0x180009556  jmp     short loc_18000957D
0x180009558  test    r9b, 80h
0x18000955c  jz      short loc_180009578
0x18000955e  lea     r8, aLeavingAccessr_1; "Leaving: AccessRouteShorter"
0x180009565  lea     rdx, RasRtrmgrTraceInfo
0x18000956c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180009573  call    McTemplateU0z_EventWriteTransfer
0x180009578  mov     eax, 57h ; 'W'
0x18000957d  mov     rcx, [rsp+888h+var_38]
0x180009585  xor     rcx, rsp; StackCookie
0x180009588  call    __security_check_cookie
0x18000958d  lea     r11, [rsp+888h+var_28]
0x180009595  mov     rbx, [r11+30h]
0x180009599  mov     rsi, [r11+38h]
0x18000959d  mov     rsp, r11
0x1800095a0  pop     r15
0x1800095a2  pop     r14
0x1800095a4  pop     r13
0x1800095a6  pop     r12
0x1800095a8  pop     rdi
0x1800095a9  retn
```
