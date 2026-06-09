# GenericInterfaceNoLongerUp

- ea: `0x18001739c`
- end: `0x1800177c3`
- name: `GenericInterfaceNoLongerUp`
- size: `1063`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a82c`
- `0x18001ce08`

## callees

- `0x180011790`
- `0x180014bb0`
- `0x1800163dc`
- `0x18001739c`
- `0x18001bc94`
- `0x18003793c`
- `0x18003bb1c`
- `0x18004e940`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001778b`
- `KERNEL32!CloseHandle` at `0x18001778b`
- `KERNEL32!GetLastError` at `0x18001772a`
- `KERNEL32!GetLastError` at `0x18001772a`
- `KERNEL32!SetEvent` at `0x18001770d`
- `KERNEL32!SetEvent` at `0x18001770d`

## string_xrefs

- `0x180017733`: `GenericInterfaceNoLongerUp: Error %d setting update route event`

## pseudocode

```c
__int64 __fastcall GenericInterfaceNoLongerUp(__int64 a1)
{
  int v1; // esi
  char v3; // al
  __int128 *v4; // r9
  __int64 v5; // r8
  __int128 *v6; // r9
  unsigned int v7; // eax
  __int64 v8; // r9
  __int128 *v9; // r9
  unsigned int v10; // r9d
  __int64 v11; // rcx
  int v12; // r10d
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned int v15; // r8d
  unsigned int v16; // eax
  __int64 v17; // r9
  __int128 *v18; // r9
  unsigned int v19; // eax
  __int64 v20; // r9
  __int128 *v21; // r9
  void *v22; // rcx
  DWORD LastError; // eax
  __int128 *v24; // r9
  __int128 v26; // [rsp+38h] [rbp-850h] BYREF
  int v27; // [rsp+48h] [rbp-840h] BYREF
  __int128 v28; // [rsp+4Ch] [rbp-83Ch]
  __int128 v29; // [rsp+5Ch] [rbp-82Ch]
  int v30; // [rsp+6Ch] [rbp-81Ch]
  int v31; // [rsp+70h] [rbp-818h] BYREF
  _BYTE v32[2044]; // [rsp+74h] [rbp-814h] BYREF

  v1 = *(_DWORD *)(a1 + 516);
  v31 = 0;
  memset_0(v32, 0, sizeof(v32));
  v27 = 0;
  v30 = 0;
  v3 = Microsoft_Windows_RRASEnableBits;
  v28 = 0;
  v29 = 0;
  v26 = 0;
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    v4 = &v26;
    LOWORD(v27) = 0;
    if ( a1 != -688 )
      LODWORD(v4) = a1 + 688;
    McTemplateU0zjzz_EventWriteTransfer(
      (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      (unsigned int)RasRtrmgrParamTraceInfo,
      (unsigned int)L"Entered: GenericInterfaceNoLongerUp",
      (_DWORD)v4,
      *(_QWORD *)(a1 + 72),
      (__int64)&v27);
    v3 = Microsoft_Windows_RRASEnableBits;
  }
  if ( v3 < 0 )
  {
    v5 = *(_QWORD *)(a1 + 72);
    LOWORD(v31) = 0;
    LOWORD(v27) = 0;
    FormatRRASErrorString(&v31, L"GenericInterfaceNoLongerUp: %ws no longer UP", v5);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v6 = &v26;
      if ( a1 != -688 )
        LODWORD(v6) = a1 + 688;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)&v31,
        (_DWORD)v6,
        *(_QWORD *)(a1 + 72),
        (__int64)&v27);
    }
  }
  if ( *(_DWORD *)(a1 + 176) )
  {
    if ( v1 )
    {
      *(_DWORD *)(a1 + 176) = 0;
      v7 = SetMcastOnIf(a1, 0);
      if ( v7 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v8 = *(_QWORD *)(a1 + 72);
          LOWORD(v31) = 0;
          LOWORD(v27) = 0;
          FormatRRASErrorString(&v31, L"GenericIfNoLongerUp: Error %d deactivating mcast on %ws", v7, v8);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v9 = &v26;
            if ( a1 != -688 )
              LODWORD(v9) = a1 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrMgrParamTraceError,
              (unsigned int)&v31,
              (_DWORD)v9,
              *(_QWORD *)(a1 + 72),
              (__int64)&v27);
          }
        }
      }
    }
  }
  v10 = g_ulGatewayMaxCount;
  v11 = g_pGateways;
  if ( g_ulGatewayMaxCount )
  {
    v12 = *(_DWORD *)(a1 + 16);
    v13 = 0;
    do
    {
      if ( *(_DWORD *)(v11 + 24 * v13 + 16) == v12 )
        *(_DWORD *)(v11 + 24 * v13) = 0;
      v13 = (unsigned int)(v13 + 1);
    }
    while ( (unsigned int)v13 < v10 );
  }
  v14 = 0;
  v15 = 1;
  if ( v10 > 1 )
  {
    while ( 1 )
    {
      if ( *(_DWORD *)(v11 + 24 * v14) )
        goto LABEL_27;
      if ( *(_DWORD *)(v11 + 24LL * v15) )
        break;
LABEL_28:
      if ( ++v15 >= v10 )
        goto LABEL_29;
    }
    *(_OWORD *)(v11 + 24 * v14) = *(_OWORD *)(v11 + 24LL * v15);
    *(_QWORD *)(v11 + 24 * v14 + 16) = *(_QWORD *)(v11 + 24LL * v15 + 16);
    *(_DWORD *)(v11 + 24LL * v15) = 0;
LABEL_27:
    v14 = (unsigned int)(v14 + 1);
    goto LABEL_28;
  }
LABEL_29:
  if ( v1 )
  {
    v16 = DeActivateRouterDiscovery(a1);
    if ( v16 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v17 = *(_QWORD *)(a1 + 72);
        LOWORD(v31) = 0;
        LOWORD(v27) = 0;
        FormatRRASErrorString(
          &v31,
          L"GenericInterfaceNoLongerUp: Error %d deactivating router discovery on %ws",
          v16,
          v17);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v18 = &v26;
          if ( a1 != -688 )
            LODWORD(v18) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v31,
            (_DWORD)v18,
            *(_QWORD *)(a1 + 72),
            (__int64)&v27);
        }
      }
    }
    v19 = DeActivateMHeartbeat(a1);
    if ( v19 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v20 = *(_QWORD *)(a1 + 72);
        LOWORD(v31) = 0;
        LOWORD(v27) = 0;
        FormatRRASErrorString(
          &v31,
          L"GenericInterfaceNoLongerUp: Error %d deactivating multicast heartbeat on %ws",
          v19,
          v20);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          v21 = &v26;
          if ( a1 != -688 )
            LODWORD(v21) = a1 + 688;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrMgrParamTraceError,
            (unsigned int)&v31,
            (_DWORD)v21,
            *(_QWORD *)(a1 + 72),
            (__int64)&v27);
        }
      }
    }
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 144) - 4) > 1 )
    UnbindFilterInterface(a1);
  UnbindInterfaceInAllProtocols(a1);
  DeAllocateBindings(a1);
  v22 = *(void **)(a1 + 192);
  if ( v22 )
  {
    if ( !SetEvent(v22) && (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v31) = 0;
      LOWORD(v27) = 0;
      LastError = GetLastError();
      FormatRRASErrorString(&v31, L"GenericInterfaceNoLongerUp: Error %d setting update route event", LastError);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        v24 = &v26;
        if ( a1 != -688 )
          LODWORD(v24) = a1 + 688;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrMgrParamTraceError,
          (unsigned int)&v31,
          (_DWORD)v24,
          *(_QWORD *)(a1 + 72),
          (__int64)&v27);
      }
    }
    CloseHandle(*(HANDLE *)(a1 + 192));
    *(_QWORD *)(a1 + 192) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18001739c  mov     [rsp+arg_8], rbx
0x1800173a1  mov     [rsp+arg_10], rsi
0x1800173a6  push    rdi
0x1800173a7  sub     rsp, 880h
0x1800173ae  mov     rax, cs:__security_cookie
0x1800173b5  xor     rax, rsp
0x1800173b8  mov     [rsp+888h+var_18], rax
0x1800173c0  mov     esi, [rcx+204h]
0x1800173c6  mov     rbx, rcx
0x1800173c9  xor     eax, eax
0x1800173cb  lea     rcx, [rsp+888h+var_814]; void *
0x1800173d0  xor     edx, edx; Val
0x1800173d2  mov     [rsp+888h+var_818], eax
0x1800173d6  mov     r8d, 7FCh; Size
0x1800173dc  call    memset_0
0x1800173e1  xor     eax, eax
0x1800173e3  lea     rdi, [rbx+2B0h]
0x1800173ea  xorps   xmm0, xmm0
0x1800173ed  mov     [rsp+888h+var_840], eax
0x1800173f1  mov     [rsp+888h+var_81C], eax
0x1800173f5  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x1800173fc  movups  [rsp+888h+var_83C], xmm0
0x180017401  movups  [rsp+888h+var_82C], xmm0
0x180017406  movups  [rsp+888h+var_850], xmm0
0x18001740b  test    al, 80h
0x18001740d  jz      short loc_180017456
0x18001740f  xor     eax, eax
0x180017411  lea     r9, [rsp+888h+var_850]
0x180017416  mov     word ptr [rsp+888h+var_840], ax
0x18001741b  lea     r8, aEnteredGeneric; "Entered: GenericInterfaceNoLongerUp"
0x180017422  lea     rax, [rsp+888h+var_840]
0x180017427  test    rdi, rdi
0x18001742a  mov     [rsp+888h+var_860], rax
0x18001742f  lea     rdx, RasRtrmgrParamTraceInfo
0x180017436  mov     rax, [rbx+48h]
0x18001743a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017441  cmovnz  r9, rdi
0x180017445  mov     [rsp+888h+var_868], rax
0x18001744a  call    McTemplateU0zjzz_EventWriteTransfer
0x18001744f  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180017456  test    al, al
0x180017458  jns     short loc_1800174BB
0x18001745a  mov     r8, [rbx+48h]
0x18001745e  lea     rdx, aGenericinterfa_1; "GenericInterfaceNoLongerUp: %ws no long"...
0x180017465  xor     eax, eax
0x180017467  lea     rcx, [rsp+888h+var_818]
0x18001746c  mov     word ptr [rsp+888h+var_818], ax
0x180017471  mov     word ptr [rsp+888h+var_840], ax
0x180017476  call    FormatRRASErrorString
0x18001747b  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180017482  jge     short loc_1800174BB
0x180017484  lea     rax, [rsp+888h+var_840]
0x180017489  test    rdi, rdi
0x18001748c  mov     [rsp+888h+var_860], rax
0x180017491  lea     r9, [rsp+888h+var_850]
0x180017496  mov     rax, [rbx+48h]
0x18001749a  lea     r8, [rsp+888h+var_818]
0x18001749f  cmovnz  r9, rdi
0x1800174a3  mov     [rsp+888h+var_868], rax
0x1800174a8  lea     rdx, RasRtrmgrParamTraceInfo
0x1800174af  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800174b6  call    McTemplateU0zjzz_EventWriteTransfer
0x1800174bb  cmp     dword ptr [rbx+0B0h], 0
0x1800174c2  jz      loc_18001755C
0x1800174c8  test    esi, esi
0x1800174ca  jz      loc_18001755C
0x1800174d0  xor     edx, edx
0x1800174d2  mov     dword ptr [rbx+0B0h], 0
0x1800174dc  mov     rcx, rbx
0x1800174df  call    SetMcastOnIf
0x1800174e4  test    eax, eax
0x1800174e6  jz      short loc_18001755C
0x1800174e8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800174ef  jz      short loc_18001755C
0x1800174f1  mov     r9, [rbx+48h]
0x1800174f5  lea     rdx, aGenericifnolon; "GenericIfNoLongerUp: Error %d deactivat"...
0x1800174fc  xor     ecx, ecx
0x1800174fe  mov     r8d, eax
0x180017501  mov     word ptr [rsp+888h+var_818], cx
0x180017506  mov     word ptr [rsp+888h+var_840], cx
0x18001750b  lea     rcx, [rsp+888h+var_818]
0x180017510  call    FormatRRASErrorString
0x180017515  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001751c  jz      short loc_18001755C
0x18001751e  lea     rax, [rbx+2B0h]
0x180017525  test    rax, rax
0x180017528  lea     r9, [rsp+888h+var_850]
0x18001752d  lea     r8, [rsp+888h+var_818]
0x180017532  cmovnz  r9, rax
0x180017536  lea     rdx, RasRtrMgrParamTraceError
0x18001753d  lea     rax, [rsp+888h+var_840]
0x180017542  mov     [rsp+888h+var_860], rax
0x180017547  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001754e  mov     rax, [rbx+48h]
0x180017552  mov     [rsp+888h+var_868], rax
0x180017557  call    McTemplateU0zjzz_EventWriteTransfer
0x18001755c  mov     r9d, cs:g_ulGatewayMaxCount
0x180017563  mov     rcx, cs:g_pGateways
0x18001756a  test    r9d, r9d
0x18001756d  jz      short loc_18001758F
0x18001756f  mov     r10d, [rbx+10h]
0x180017573  xor     edx, edx
0x180017575  lea     r8, [rdx+rdx*2]
0x180017579  cmp     [rcx+r8*8+10h], r10d
0x18001757e  jnz     short loc_180017588
0x180017580  mov     dword ptr [rcx+r8*8], 0
0x180017588  inc     edx
0x18001758a  cmp     edx, r9d
0x18001758d  jb      short loc_180017575
0x18001758f  xor     edx, edx
0x180017591  lea     r8d, [rdx+1]
0x180017595  cmp     r9d, r8d
0x180017598  jbe     short loc_1800175DD
0x18001759a  lea     r11, [rdx+rdx*2]
0x18001759e  cmp     dword ptr [rcx+r11*8], 0
0x1800175a3  jnz     short loc_1800175D3
0x1800175a5  mov     eax, r8d
0x1800175a8  lea     r10, [rax+rax*2]
0x1800175ac  cmp     dword ptr [rcx+r10*8], 0
0x1800175b1  jz      short loc_1800175D5
0x1800175b3  movups  xmm0, xmmword ptr [rcx+r10*8]
0x1800175b8  movups  xmmword ptr [rcx+r11*8], xmm0
0x1800175bd  movsd   xmm1, qword ptr [rcx+r10*8+10h]
0x1800175c4  movsd   qword ptr [rcx+r11*8+10h], xmm1
0x1800175cb  mov     dword ptr [rcx+r10*8], 0
0x1800175d3  inc     edx
0x1800175d5  inc     r8d
0x1800175d8  cmp     r8d, r9d
0x1800175db  jb      short loc_18001759A
0x1800175dd  test    esi, esi
0x1800175df  jz      loc_1800176D7
0x1800175e5  mov     rcx, rbx
0x1800175e8  call    DeActivateRouterDiscovery
0x1800175ed  test    eax, eax
0x1800175ef  jz      short loc_18001765E
0x1800175f1  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800175f8  jz      short loc_18001765E
0x1800175fa  mov     r9, [rbx+48h]
0x1800175fe  lea     rdx, aGenericinterfa_6; "GenericInterfaceNoLongerUp: Error %d de"...
0x180017605  xor     ecx, ecx
0x180017607  mov     r8d, eax
0x18001760a  mov     word ptr [rsp+888h+var_818], cx
0x18001760f  mov     word ptr [rsp+888h+var_840], cx
0x180017614  lea     rcx, [rsp+888h+var_818]
0x180017619  call    FormatRRASErrorString
0x18001761e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180017625  jz      short loc_18001765E
0x180017627  lea     rax, [rsp+888h+var_840]
0x18001762c  test    rdi, rdi
0x18001762f  mov     [rsp+888h+var_860], rax
0x180017634  lea     r9, [rsp+888h+var_850]
0x180017639  mov     rax, [rbx+48h]
0x18001763d  lea     r8, [rsp+888h+var_818]
0x180017642  cmovnz  r9, rdi
0x180017646  mov     [rsp+888h+var_868], rax
0x18001764b  lea     rdx, RasRtrMgrParamTraceError
0x180017652  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017659  call    McTemplateU0zjzz_EventWriteTransfer
0x18001765e  mov     rcx, rbx
0x180017661  call    DeActivateMHeartbeat
0x180017666  test    eax, eax
0x180017668  jz      short loc_1800176D7
0x18001766a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180017671  jz      short loc_1800176D7
0x180017673  mov     r9, [rbx+48h]
0x180017677  lea     rdx, aGenericinterfa_0; "GenericInterfaceNoLongerUp: Error %d de"...
0x18001767e  xor     ecx, ecx
0x180017680  mov     r8d, eax
0x180017683  mov     word ptr [rsp+888h+var_818], cx
0x180017688  mov     word ptr [rsp+888h+var_840], cx
0x18001768d  lea     rcx, [rsp+888h+var_818]
0x180017692  call    FormatRRASErrorString
0x180017697  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001769e  jz      short loc_1800176D7
0x1800176a0  lea     rax, [rsp+888h+var_840]
0x1800176a5  test    rdi, rdi
0x1800176a8  mov     [rsp+888h+var_860], rax
0x1800176ad  lea     r9, [rsp+888h+var_850]
0x1800176b2  mov     rax, [rbx+48h]
0x1800176b6  lea     r8, [rsp+888h+var_818]
0x1800176bb  cmovnz  r9, rdi
0x1800176bf  mov     [rsp+888h+var_868], rax
0x1800176c4  lea     rdx, RasRtrMgrParamTraceError
0x1800176cb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800176d2  call    McTemplateU0zjzz_EventWriteTransfer
0x1800176d7  mov     eax, [rbx+90h]
0x1800176dd  sub     eax, 4
0x1800176e0  cmp     eax, 1
0x1800176e3  jbe     short loc_1800176ED
0x1800176e5  mov     rcx, rbx
0x1800176e8  call    UnbindFilterInterface
0x1800176ed  mov     rcx, rbx
0x1800176f0  call    UnbindInterfaceInAllProtocols
0x1800176f5  mov     rcx, rbx
0x1800176f8  call    DeAllocateBindings
0x1800176fd  mov     rcx, [rbx+0C0h]; hEvent
0x180017704  test    rcx, rcx
0x180017707  jz      loc_18001779C
0x18001770d  call    cs:__imp_SetEvent
0x180017713  test    eax, eax
0x180017715  jnz     short loc_180017784
0x180017717  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001771e  jz      short loc_180017784
0x180017720  mov     word ptr [rsp+888h+var_818], ax
0x180017725  mov     word ptr [rsp+888h+var_840], ax
0x18001772a  call    cs:__imp_GetLastError
0x180017730  mov     r8d, eax
0x180017733  lea     rdx, aGenericinterfa; "GenericInterfaceNoLongerUp: Error %d se"...
0x18001773a  lea     rcx, [rsp+888h+var_818]
0x18001773f  call    FormatRRASErrorString
0x180017744  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18001774b  jz      short loc_180017784
0x18001774d  lea     rax, [rsp+888h+var_840]
0x180017752  test    rdi, rdi
0x180017755  mov     [rsp+888h+var_860], rax
0x18001775a  lea     r9, [rsp+888h+var_850]
0x18001775f  mov     rax, [rbx+48h]
0x180017763  lea     r8, [rsp+888h+var_818]
0x180017768  cmovnz  r9, rdi
0x18001776c  mov     [rsp+888h+var_868], rax
0x180017771  lea     rdx, RasRtrMgrParamTraceError
0x180017778  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001777f  call    McTemplateU0zjzz_EventWriteTransfer
0x180017784  mov     rcx, [rbx+0C0h]; hObject
0x18001778b  call    cs:__imp_CloseHandle
0x180017791  mov     qword ptr [rbx+0C0h], 0
0x18001779c  xor     eax, eax
0x18001779e  mov     rcx, [rsp+888h+var_18]
0x1800177a6  xor     rcx, rsp; StackCookie
0x1800177a9  call    __security_check_cookie
0x1800177ae  lea     r11, [rsp+888h+var_8]
0x1800177b6  mov     rbx, [r11+18h]
0x1800177ba  mov     rsi, [r11+20h]
0x1800177be  mov     rsp, r11
0x1800177c1  pop     rdi
0x1800177c2  retn
```
