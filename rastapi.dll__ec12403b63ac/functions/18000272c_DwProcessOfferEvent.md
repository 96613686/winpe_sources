# DwProcessOfferEvent

- ea: `0x18000272c`
- end: `0x180002b17`
- name: `DwProcessOfferEvent`
- size: `1003`
- prototype: `__int64 __fastcall(HCALL hCall)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cb80`

## callees

- `0x1800023d4`
- `0x18000272c`
- `0x18000c918`
- `0x18000d92c`
- `0x1800244ec`
- `0x180029266`
- `0x18002927e`
- `0x1800292b0`

## import_xrefs

- `msvcrt!_stricmp` at `0x180002957`
- `msvcrt!_stricmp` at `0x180002957`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002916`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002916`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002857`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002857`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002846`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800028b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002846`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800028b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002a9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800028be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002aab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800028be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002aab`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallInfoA` at `0x180002790`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallInfoA` at `0x180002874`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallInfoA` at `0x180002790`
- `ext-ms-win-ras-tapi32-l1-1-1!lineGetCallInfoA` at `0x180002874`

## string_xrefs

- `0x180002971`: `DwProcessOfferEvent: call already answered on %s`

## pseudocode

```c
__int64 __fastcall DwProcessOfferEvent(HCALL hCall, _QWORD *a2, __int64 a3)
{
  unsigned int v6; // eax
  unsigned int v7; // esi
  HLOCAL i; // rdi
  DWORD dwNeededSize; // r15d
  linecallinfo_tag *p_CallInfo; // rbx
  HANDLE ProcessHeap; // rax
  struct linecallinfo_tag *v12; // rax
  unsigned int v13; // eax
  HANDLE v14; // rax
  DWORD dwDevSpecificSize; // eax
  HLOCAL v16; // rax
  DWORD v17; // ecx
  __int64 v18; // rax
  __int64 v19; // rax
  HANDLE v20; // rax
  const CHAR *v21; // rcx
  linecallinfo_tag CallInfo; // [rsp+20h] [rbp-438h] BYREF

  memset_0(&CallInfo.dwNeededSize, 0, 0x3E4u);
  CallInfo.dwTotalSize = 1000;
  RasTapiTrace("DwProcessOfferEvent: hcall=0x%x");
  if ( *(_DWORD *)(a3 + 60) )
    v6 = RasLineGetCallInfo(hCall, (__int64)&CallInfo);
  else
    v6 = lineGetCallInfoA(hCall, &CallInfo);
  v7 = v6;
  if ( !*(_DWORD *)(a3 + 60) )
  {
    if ( v6 <= 0x80000000 )
      goto LABEL_6;
LABEL_10:
    RasTapiTrace("DwProcessOfferEvent: LINE_CALLSTATE - lineGetCallInfo Failed. %d");
    goto LABEL_51;
  }
  if ( v6 )
    goto LABEL_10;
LABEL_6:
  if ( !g_fRestrictDialIn || g_dwTotalDialIn < (unsigned int)g_dwRestrictedPortCount )
  {
    for ( i = RasPortsList; ; i = (HLOCAL)*((_QWORD *)i + 1) )
    {
      if ( !i )
        goto LABEL_48;
      if ( *((_QWORD *)i + 27) == a3 && *(_DWORD *)(a3 + 16) == 2 && *((_DWORD *)i + 14) == 2 && !*((_DWORD *)i + 15) )
        break;
    }
    *((_DWORD *)i + 56) = CallInfo.dwAddressID;
    dwNeededSize = CallInfo.dwNeededSize;
    p_CallInfo = &CallInfo;
    if ( CallInfo.dwTotalSize < CallInfo.dwNeededSize )
    {
      RasTapiTrace("DwProcessOfferEvent: LineCallInfo: total size < needed size. Retrying to fetch more");
      ProcessHeap = GetProcessHeap();
      v12 = (struct linecallinfo_tag *)HeapAlloc(ProcessHeap, 8u, dwNeededSize);
      p_CallInfo = v12;
      if ( v12 )
      {
        v12->dwTotalSize = dwNeededSize;
        if ( *(_DWORD *)(a3 + 60) )
          v13 = RasLineGetCallInfo(hCall, (__int64)v12);
        else
          v13 = lineGetCallInfoA(hCall, v12);
        v7 = v13;
        if ( !*(_DWORD *)(a3 + 60) )
        {
          if ( v13 <= 0x80000000 )
            goto LABEL_28;
          goto LABEL_27;
        }
        if ( v13 )
        {
LABEL_27:
          RasTapiTrace("GetCallInfo failed with error 0x%x");
          RasTapiTrace("GetCallInfo - reusing the minimum information received");
          v14 = GetProcessHeap();
          HeapFree(v14, 0, p_CallInfo);
          p_CallInfo = &CallInfo;
        }
      }
    }
LABEL_28:
    *((_DWORD *)i + 58) = hCall;
    *a2 = i;
    RasTapiTrace("DwProcessOfferEvent guid: Size=%d, Offset=%d deviceType=%d");
    dwDevSpecificSize = p_CallInfo->dwDevSpecificSize;
    if ( dwDevSpecificSize && p_CallInfo->dwDevSpecificOffset )
    {
      v16 = LocalAlloc(0x40u, dwDevSpecificSize);
      *((_QWORD *)i + 108) = v16;
      if ( !v16 )
      {
        v7 = 14;
        RasTapiTrace("DwProcessOfferEvent: LocalAlloc failed.");
        goto LABEL_46;
      }
      v17 = p_CallInfo->dwDevSpecificSize;
      *((_DWORD *)i + 218) = v17;
      memcpy_0(v16, (char *)p_CallInfo + p_CallInfo->dwDevSpecificOffset, v17);
    }
    if ( !_stricmp((const char *)i + 64, "MODEM") )
    {
      if ( p_CallInfo->dwCallStates != 256 )
      {
        if ( *(_DWORD *)&NumberOfRings )
        {
          RasTapiTrace("DwProcessOfferEvent: changing listenstate of %s from %d to LS_RINGING");
          *((_DWORD *)i + 15) = 1;
          *((_DWORD *)i + 274) = *(_DWORD *)&NumberOfRings;
        }
        else
        {
          *((_DWORD *)i + 15) = 2;
          RasTapiTrace("Accepting call on %s hcall = 0x%x");
          *((_DWORD *)i + 274) = 0;
          PostNotificationCompletion((__int64)i);
        }
        v18 = *(_QWORD *)(a3 + 40);
        if ( v18 )
          ++*(_DWORD *)(v18 + 16);
        ++g_dwTotalDialIn;
        RasTapiTrace("%s InClients=%d, TotalDialInClients=%d");
        *((_DWORD *)i + 276) |= 2u;
        goto LABEL_46;
      }
      RasTapiTrace("DwProcessOfferEvent: call already answered on %s");
      *((_DWORD *)i + 15) = 4;
    }
    else
    {
      *((_DWORD *)i + 15) = 2;
      RasTapiTrace("DwProcessOfferEvent: Accepting call on %s hcall = 0x%x");
      v19 = *(_QWORD *)(a3 + 40);
      if ( v19 )
        ++*(_DWORD *)(v19 + 16);
      ++g_dwTotalDialIn;
      RasTapiTrace("%s InClients=%d, TotalDialInClients=%d");
      *((_DWORD *)i + 276) |= 2u;
    }
    PostNotificationCompletion((__int64)i);
LABEL_46:
    if ( p_CallInfo != &CallInfo )
    {
      v20 = GetProcessHeap();
      HeapFree(v20, 0, p_CallInfo);
    }
    goto LABEL_51;
  }
LABEL_48:
  v21 = "DwProcessOfferEvent: Total Dialin clients exceeded limit. Dropping call 0x%x";
  if ( g_dwTotalDialIn < (unsigned int)g_dwRestrictedPortCount )
    v21 = "DwProcessOfferEvent: Couldn't find a listening port. Dropping call 0x%x";
  RasTapiTrace(v21);
  DwDropIncomingCall(hCall, *(_DWORD *)(a3 + 60));
  v7 = -2147467259;
LABEL_51:
  RasTapiTrace("DwProcessOfferEvent 0x%x");
  return v7;
}

```

## disassembly

```asm
0x18000272c  push    rbx
0x18000272e  push    rbp
0x18000272f  push    rsi
0x180002730  push    rdi
0x180002731  push    r12
0x180002733  push    r14
0x180002735  push    r15
0x180002737  sub     rsp, 420h
0x18000273e  mov     rax, cs:__security_cookie
0x180002745  xor     rax, rsp
0x180002748  mov     [rsp+458h+var_48], rax
0x180002750  mov     rbp, r8
0x180002753  mov     r12, rdx
0x180002756  mov     r14d, ecx
0x180002759  xor     edx, edx; Val
0x18000275b  mov     r8d, 3E4h; Size
0x180002761  lea     rcx, [rsp+458h+CallInfo.dwNeededSize]; void *
0x180002766  call    memset_0
0x18000276b  mov     edx, r14d
0x18000276e  mov     [rsp+458h+CallInfo.dwTotalSize], 3E8h
0x180002776  lea     rcx, aDwprocessoffer_2; "DwProcessOfferEvent: hcall=0x%x"
0x18000277d  call    RasTapiTrace
0x180002782  cmp     dword ptr [rbp+3Ch], 0
0x180002786  lea     rdx, [rsp+458h+CallInfo]; lpCallInfo
0x18000278b  mov     ecx, r14d; hCall
0x18000278e  jnz     short loc_180002798
0x180002790  call    cs:__imp_lineGetCallInfoA
0x180002796  jmp     short loc_18000279D
0x180002798  call    RasLineGetCallInfo
0x18000279d  cmp     dword ptr [rbp+3Ch], 0
0x1800027a1  mov     esi, eax
0x1800027a3  jnz     short loc_1800027D2
0x1800027a5  cmp     eax, 80000000h
0x1800027aa  ja      short loc_1800027D6
0x1800027ac  cmp     cs:g_fRestrictDialIn, 0
0x1800027b3  mov     edx, cs:g_dwTotalDialIn
0x1800027b9  mov     eax, cs:g_dwRestrictedPortCount
0x1800027bf  jz      short loc_1800027C9
0x1800027c1  cmp     edx, eax
0x1800027c3  jnb     loc_180002AB9
0x1800027c9  mov     rdi, cs:RasPortsList
0x1800027d0  jmp     short loc_180002808
0x1800027d2  test    esi, esi
0x1800027d4  jz      short loc_1800027AC
0x1800027d6  mov     edx, esi
0x1800027d8  lea     rcx, aDwprocessoffer_8; "DwProcessOfferEvent: LINE_CALLSTATE - l"...
0x1800027df  call    RasTapiTrace
0x1800027e4  jmp     loc_180002AE5
0x1800027e9  cmp     [rdi+0D8h], rbp
0x1800027f0  jnz     short loc_180002804
0x1800027f2  cmp     dword ptr [rbp+10h], 2
0x1800027f6  jnz     short loc_180002804
0x1800027f8  cmp     dword ptr [rdi+38h], 2
0x1800027fc  jnz     short loc_180002804
0x1800027fe  cmp     dword ptr [rdi+3Ch], 0
0x180002802  jz      short loc_180002812
0x180002804  mov     rdi, [rdi+8]
0x180002808  test    rdi, rdi
0x18000280b  jnz     short loc_1800027E9
0x18000280d  jmp     loc_180002AB9
0x180002812  mov     eax, [rsp+458h+CallInfo.dwAddressID]
0x180002816  mov     [rdi+0E0h], eax
0x18000281c  test    rdi, rdi
0x18000281f  jz      loc_180002AB3
0x180002825  mov     r15d, [rsp+458h+CallInfo.dwNeededSize]
0x18000282a  lea     rbx, [rsp+458h+CallInfo]
0x18000282f  cmp     [rsp+458h+CallInfo.dwTotalSize], r15d
0x180002834  jnb     loc_1800028C9
0x18000283a  lea     rcx, aDwprocessoffer_9; "DwProcessOfferEvent: LineCallInfo: tota"...
0x180002841  call    RasTapiTrace
0x180002846  call    cs:__imp_GetProcessHeap
0x18000284c  mov     r8d, r15d; dwBytes
0x18000284f  mov     edx, 8; dwFlags
0x180002854  mov     rcx, rax; hHeap
0x180002857  call    cs:__imp_HeapAlloc
0x18000285d  mov     rbx, rax
0x180002860  test    rax, rax
0x180002863  jz      short loc_1800028C9
0x180002865  mov     [rax], r15d
0x180002868  mov     rdx, rax; lpCallInfo
0x18000286b  cmp     dword ptr [rbp+3Ch], 0
0x18000286f  mov     ecx, r14d; hCall
0x180002872  jnz     short loc_18000287C
0x180002874  call    cs:__imp_lineGetCallInfoA
0x18000287a  jmp     short loc_180002881
0x18000287c  call    RasLineGetCallInfo
0x180002881  cmp     dword ptr [rbp+3Ch], 0
0x180002885  mov     esi, eax
0x180002887  jnz     short loc_180002892
0x180002889  cmp     eax, 80000000h
0x18000288e  ja      short loc_180002896
0x180002890  jmp     short loc_1800028C9
0x180002892  test    esi, esi
0x180002894  jz      short loc_1800028C9
0x180002896  mov     edx, esi
0x180002898  lea     rcx, aGetcallinfoFai; "GetCallInfo failed with error 0x%x"
0x18000289f  call    RasTapiTrace
0x1800028a4  lea     rcx, aGetcallinfoReu; "GetCallInfo - reusing the minimum infor"...
0x1800028ab  call    RasTapiTrace
0x1800028b0  call    cs:__imp_GetProcessHeap
0x1800028b6  mov     r8, rbx; lpMem
0x1800028b9  xor     edx, edx; dwFlags
0x1800028bb  mov     rcx, rax; hHeap
0x1800028be  call    cs:__imp_HeapFree
0x1800028c4  lea     rbx, [rsp+458h+CallInfo]
0x1800028c9  mov     [rdi+0E8h], r14d
0x1800028d0  lea     rcx, aDwprocessoffer_7; "DwProcessOfferEvent guid: Size=%d, Offs"...
0x1800028d7  mov     [r12], rdi
0x1800028db  mov     rax, [rdi+0D8h]
0x1800028e2  mov     r8d, [rbx+124h]
0x1800028e9  mov     edx, [rbx+120h]
0x1800028ef  mov     r9, [rax+28h]
0x1800028f3  mov     r9d, [r9+60h]
0x1800028f7  call    RasTapiTrace
0x1800028fc  mov     eax, [rbx+120h]
0x180002902  test    eax, eax
0x180002904  jz      short loc_180002948
0x180002906  cmp     dword ptr [rbx+124h], 0
0x18000290d  jbe     short loc_180002948
0x18000290f  mov     edx, eax; uBytes
0x180002911  mov     ecx, 40h ; '@'; uFlags
0x180002916  call    cs:__imp_LocalAlloc
0x18000291c  mov     [rdi+360h], rax
0x180002923  test    rax, rax
0x180002926  jz      short loc_180002989
0x180002928  mov     ecx, [rbx+120h]
0x18000292e  mov     [rdi+368h], ecx
0x180002934  mov     r8d, ecx; Size
0x180002937  mov     edx, [rbx+124h]
0x18000293d  mov     rcx, rax; void *
0x180002940  add     rdx, rbx; Src
0x180002943  call    memcpy_0
0x180002948  lea     rcx, [rdi+40h]; String1
0x18000294c  lea     rdx, aModem; "MODEM"
0x180002953  lea     r15, [rdi+18h]
0x180002957  call    cs:__imp__stricmp
0x18000295d  mov     rdx, r15
0x180002960  test    eax, eax
0x180002962  jnz     loc_180002A36
0x180002968  cmp     dword ptr [rbx+34h], 100h
0x18000296f  jnz     short loc_18000299F
0x180002971  lea     rcx, aDwprocessoffer; "DwProcessOfferEvent: call already answe"...
0x180002978  call    RasTapiTrace
0x18000297d  mov     dword ptr [rdi+3Ch], 4
0x180002984  jmp     loc_180002A8B
0x180002989  lea     rcx, aDwprocessoffer_6; "DwProcessOfferEvent: LocalAlloc failed."
0x180002990  mov     esi, 0Eh
0x180002995  call    RasTapiTrace
0x18000299a  jmp     loc_180002A93
0x18000299f  cmp     cs:NumberOfRings, 0
0x1800029a6  jnz     short loc_1800029D2
0x1800029a8  mov     r8d, r14d
0x1800029ab  mov     dword ptr [rdi+3Ch], 2
0x1800029b2  lea     rcx, aAcceptingCallO; "Accepting call on %s hcall = 0x%x"
0x1800029b9  call    RasTapiTrace
0x1800029be  mov     rcx, rdi
0x1800029c1  mov     dword ptr [rdi+448h], 0
0x1800029cb  call    PostNotificationCompletion
0x1800029d0  jmp     short loc_1800029F5
0x1800029d2  mov     r8d, [rdi+3Ch]
0x1800029d6  lea     rcx, aDwprocessoffer_4; "DwProcessOfferEvent: changing listensta"...
0x1800029dd  call    RasTapiTrace
0x1800029e2  mov     dword ptr [rdi+3Ch], 1
0x1800029e9  mov     eax, cs:NumberOfRings
0x1800029ef  mov     [rdi+448h], eax
0x1800029f5  mov     rax, [rbp+28h]
0x1800029f9  test    rax, rax
0x1800029fc  jz      short loc_180002A01
0x1800029fe  inc     dword ptr [rax+10h]
0x180002a01  mov     r8, [rbp+28h]
0x180002a05  lea     rcx, aSInclientsDTot; "%s InClients=%d, TotalDialInClients=%d"
0x180002a0c  mov     r9d, cs:g_dwTotalDialIn
0x180002a13  inc     r9d
0x180002a16  mov     cs:g_dwTotalDialIn, r9d
0x180002a1d  lea     rdx, [r8+85h]
0x180002a24  mov     r8d, [r8+10h]
0x180002a28  call    RasTapiTrace
0x180002a2d  or      dword ptr [rdi+450h], 2
0x180002a34  jmp     short loc_180002A93
0x180002a36  mov     r8d, r14d
0x180002a39  mov     dword ptr [rdi+3Ch], 2
0x180002a40  lea     rcx, aDwprocessoffer_0; "DwProcessOfferEvent: Accepting call on "...
0x180002a47  call    RasTapiTrace
0x180002a4c  mov     rax, [rbp+28h]
0x180002a50  test    rax, rax
0x180002a53  jz      short loc_180002A58
0x180002a55  inc     dword ptr [rax+10h]
0x180002a58  mov     r8, [rbp+28h]
0x180002a5c  lea     rcx, aSInclientsDTot; "%s InClients=%d, TotalDialInClients=%d"
0x180002a63  mov     r9d, cs:g_dwTotalDialIn
0x180002a6a  inc     r9d
0x180002a6d  mov     cs:g_dwTotalDialIn, r9d
0x180002a74  lea     rdx, [r8+85h]
0x180002a7b  mov     r8d, [r8+10h]
0x180002a7f  call    RasTapiTrace
0x180002a84  or      dword ptr [rdi+450h], 2
0x180002a8b  mov     rcx, rdi
0x180002a8e  call    PostNotificationCompletion
0x180002a93  lea     rax, [rsp+458h+CallInfo]
0x180002a98  cmp     rbx, rax
0x180002a9b  jz      short loc_180002AE5
0x180002a9d  call    cs:__imp_GetProcessHeap
0x180002aa3  mov     r8, rbx; lpMem
0x180002aa6  xor     edx, edx; dwFlags
0x180002aa8  mov     rcx, rax; hHeap
0x180002aab  call    cs:__imp_HeapFree
0x180002ab1  jmp     short loc_180002AE5
0x180002ab3  mov     eax, cs:g_dwRestrictedPortCount
0x180002ab9  cmp     edx, eax
0x180002abb  lea     r8, aDwprocessoffer_1; "DwProcessOfferEvent: Couldn't find a li"...
0x180002ac2  lea     rcx, aDwprocessoffer_5; "DwProcessOfferEvent: Total Dialin clien"...
0x180002ac9  mov     edx, r14d
0x180002acc  cmovb   rcx, r8; lpszFormat
0x180002ad0  call    RasTapiTrace
0x180002ad5  mov     edx, [rbp+3Ch]
0x180002ad8  mov     ecx, r14d; hCall
0x180002adb  call    DwDropIncomingCall
0x180002ae0  mov     esi, 80004005h
0x180002ae5  mov     edx, esi
0x180002ae7  lea     rcx, aDwprocessoffer_3; "DwProcessOfferEvent 0x%x"
0x180002aee  call    RasTapiTrace
0x180002af3  mov     eax, esi
0x180002af5  mov     rcx, [rsp+458h+var_48]
0x180002afd  xor     rcx, rsp; StackCookie
0x180002b00  call    __security_check_cookie
0x180002b05  add     rsp, 420h
0x180002b0c  pop     r15
0x180002b0e  pop     r14
0x180002b10  pop     r12
0x180002b12  pop     rdi
0x180002b13  pop     rsi
0x180002b14  pop     rbp
0x180002b15  pop     rbx
0x180002b16  retn
```
