# LoadRoutingProtocols

- ea: `0x1800023f4`
- end: `0x180002871`
- name: `LoadRoutingProtocols`
- size: `1149`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180020238`
- `0x1800208c4`

## callees

- `0x1800023f4`
- `0x180002878`
- `0x18000ac60`
- `0x18003c1ac`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180002714`
- `KERNEL32!HeapFree` at `0x180002714`
- `KERNEL32!HeapAlloc` at `0x180002628`
- `KERNEL32!HeapAlloc` at `0x180002628`
- `rtutils!MprSetupProtocolFree` at `0x180002819`
- `rtutils!MprSetupProtocolFree` at `0x180002819`
- `rtutils!MprSetupProtocolEnum` at `0x1800024f4`
- `rtutils!MprSetupProtocolEnum` at `0x1800024f4`

## string_xrefs

- `0x180002464`: `LoadRoutingProtocols`
- `0x1800024b5`: `Loading routing protocols for transport %d`
- `0x180002514`: `LoadRoutingProtocols: Error %d loading protocol info from registry`
- `0x180002554`: `Leaving: LoadRoutingProtocols`
- `0x180002828`: `Leaving: LoadRoutingProtocols`
- `0x1800027c5`: `LoadRoutingProtocols: Couldnt find information for protocol ID %d`
- `0x180002647`: `LoadRoutingProtocols: Error allocating %d bytes for %ws`
- `0x1800026c6`: `LoadRoutingProtocols: %ws failed to load: %d`
- `0x180002775`: `LoadRoutingProtocols: %ws successfully initialized`

## pseudocode

```c
__int64 __fastcall LoadRoutingProtocols(__int64 a1, DWORD a2)
{
  DWORD v4; // eax
  DWORD v5; // ebx
  char v6; // cl
  __int64 *v8; // r13
  unsigned int i; // eax
  __int64 v10; // rdi
  DWORD j; // ecx
  __int64 v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // rax
  SIZE_T v15; // r15
  unsigned int *v16; // rbx
  __int64 v17; // rax
  __int64 v18; // r8
  unsigned int Protocol; // eax
  unsigned int v20; // r8d
  __int64 **v21; // rax
  bool v22; // sf
  BOOL v23; // [rsp+40h] [rbp-868h]
  LPBYTE lpBuffer; // [rsp+48h] [rbp-860h] BYREF
  DWORD dwEntriesRead; // [rsp+50h] [rbp-858h] BYREF
  unsigned int v26; // [rsp+54h] [rbp-854h]
  struct _GUID v27; // [rsp+58h] [rbp-850h] BYREF
  int v28; // [rsp+70h] [rbp-838h] BYREF
  _BYTE v29[2044]; // [rsp+74h] [rbp-834h] BYREF

  dwEntriesRead = 0;
  lpBuffer = 0;
  v28 = 0;
  v23 = a2 == 33;
  memset_0(v29, 0, sizeof(v29));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
  {
    LOWORD(v28) = 0;
    FormatRRASErrorString(&v28, L"Entered: %ws", L"LoadRoutingProtocols");
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v28) = 0;
        FormatRRASErrorString(&v28, L"Loading routing protocols for transport %d", a2);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
      }
    }
  }
  v4 = MprSetupProtocolEnum(a2, &lpBuffer, &dwEntriesRead);
  v5 = v4;
  if ( v4 )
  {
    v6 = Microsoft_Windows_RRASEnableBits;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v28) = 0;
      FormatRRASErrorString(&v28, L"LoadRoutingProtocols: Error %d loading protocol info from registry", v4);
      v6 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
        v6 = Microsoft_Windows_RRASEnableBits;
      }
    }
    if ( v6 < 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: LoadRoutingProtocols");
    return v5;
  }
  else
  {
    v8 = (__int64 *)&g_leProtoCbListV4;
    if ( a2 != 33 )
      v8 = &g_leProtoCbListV6;
    for ( i = 0; ; i = v26 + 1 )
    {
      v26 = i;
      if ( i >= *(_DWORD *)(a1 + 8) )
        break;
      v10 = 2LL * i;
      if ( (*(_DWORD *)(a1 + 16LL * i + 12) & 0xC0000000) < 0xC0000000 && *(_DWORD *)(a1 + 16LL * i + 16) )
      {
        for ( j = 0; ; ++j )
        {
          if ( j >= dwEntriesRead )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
              goto LABEL_46;
            LOWORD(v28) = 0;
            FormatRRASErrorString(&v28, L"LoadRoutingProtocols: Couldnt find information for protocol ID %d");
            goto LABEL_44;
          }
          v12 = 184LL * j;
          if ( *(_DWORD *)&lpBuffer[v12] == *(_DWORD *)(a1 + 16LL * i + 12) )
            break;
        }
        v13 = -1;
        do
          ++v13;
        while ( *(_WORD *)&lpBuffer[2 * v13 + 4 + v12] );
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)&lpBuffer[2 * v14 + 86 + v12] );
        v15 = (unsigned int)(2 * (v13 + v14) + 324);
        v16 = (unsigned int *)HeapAlloc(IPRouterHeap, 8u, v15);
        if ( !v16 )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
            continue;
          LOWORD(v28) = 0;
          FormatRRASErrorString(
            &v28,
            L"LoadRoutingProtocols: Error allocating %d bytes for %ws",
            (unsigned int)v15,
            &lpBuffer[v12 + 4]);
LABEL_44:
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
          continue;
        }
        v17 = *(unsigned int *)(a1 + 8 * v10 + 24);
        v18 = a1 + v17;
        if ( (unsigned int)v17 >= *(_DWORD *)(a1 + 4) )
          v18 = 0;
        Protocol = LoadProtocol(
                     (int *)&lpBuffer[v12],
                     (__int64)v16,
                     v18,
                     0x500u,
                     *(_DWORD *)(a1 + 8 * v10 + 16),
                     *(_DWORD *)(a1 + 8 * v10 + 20),
                     v23);
        if ( Protocol )
        {
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            LOWORD(v28) = 0;
            FormatRRASErrorString(&v28, L"LoadRoutingProtocols: %ws failed to load: %d", &lpBuffer[v12 + 4], Protocol);
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
          }
          HeapFree(IPRouterHeap, 0, v16);
        }
        else
        {
          v20 = v16[15];
          v16[4] = 0;
          v16[12] = 1;
          v27 = GUID_NULL;
          EnableOrDisableProtocolForRoutingDomain(&v27, a2, v20, 1);
          v21 = (__int64 **)v8[1];
          if ( *v21 != v8 )
            __fastfail(3u);
          *(_QWORD *)v16 = v8;
          *((_QWORD *)v16 + 1) = v21;
          *v21 = (__int64 *)v16;
          v22 = (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL;
          v8[1] = (__int64)v16;
          if ( v22 )
          {
            LOWORD(v28) = 0;
            FormatRRASErrorString(&v28, L"LoadRoutingProtocols: %ws successfully initialized", &lpBuffer[v12 + 4]);
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
          }
          ++TotalRoutingProtocols;
        }
      }
LABEL_46:
      ;
    }
    MprSetupProtocolFree(lpBuffer);
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: LoadRoutingProtocols");
    return 0;
  }
}

```

## disassembly

```asm
0x1800023f4  mov     [rsp+arg_10], rbx
0x1800023f9  mov     [rsp+arg_18], rsi
0x1800023fe  push    rdi
0x1800023ff  push    r12
0x180002401  push    r13
0x180002403  push    r14
0x180002405  push    r15
0x180002407  sub     rsp, 880h
0x18000240e  mov     rax, cs:__security_cookie
0x180002415  xor     rax, rsp
0x180002418  mov     [rsp+8A8h+var_38], rax
0x180002420  xor     r15d, r15d
0x180002423  mov     r12d, edx
0x180002426  cmp     edx, 21h ; '!'
0x180002429  mov     [rsp+8A8h+dwEntriesRead], r15d
0x18000242e  mov     eax, r15d
0x180002431  mov     [rsp+8A8h+lpBuffer], r15
0x180002436  setz    al
0x180002439  mov     [rsp+8A8h+var_838], r15d
0x18000243e  mov     r14, rcx
0x180002441  mov     [rsp+8A8h+var_868], eax
0x180002445  xor     edx, edx; Val
0x180002447  lea     rcx, [rsp+8A8h+var_834]; void *
0x18000244c  mov     r8d, 7FCh; Size
0x180002452  call    memset_0
0x180002457  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000245e  jge     loc_1800024E7
0x180002464  lea     r8, aLoadroutingpro_0; "LoadRoutingProtocols"
0x18000246b  mov     word ptr [rsp+8A8h+var_838], r15w
0x180002471  lea     rdx, aEnteredWs; "Entered: %ws"
0x180002478  lea     rcx, [rsp+8A8h+var_838]
0x18000247d  call    FormatRRASErrorString
0x180002482  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x180002489  jge     short loc_1800024E7
0x18000248b  lea     r8, [rsp+8A8h+var_838]
0x180002490  lea     rdx, RasRtrmgrTraceInfo
0x180002497  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000249e  call    McTemplateU0z_EventWriteTransfer
0x1800024a3  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800024aa  jge     short loc_1800024E7
0x1800024ac  mov     r8d, r12d
0x1800024af  mov     word ptr [rsp+8A8h+var_838], r15w
0x1800024b5  lea     rdx, aLoadingRouting; "Loading routing protocols for transport"...
0x1800024bc  lea     rcx, [rsp+8A8h+var_838]
0x1800024c1  call    FormatRRASErrorString
0x1800024c6  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800024cd  jge     short loc_1800024E7
0x1800024cf  lea     r8, [rsp+8A8h+var_838]
0x1800024d4  lea     rdx, RasRtrmgrTraceInfo
0x1800024db  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800024e2  call    McTemplateU0z_EventWriteTransfer
0x1800024e7  lea     r8, [rsp+8A8h+dwEntriesRead]; lpdwEntriesRead
0x1800024ec  mov     ecx, r12d; dwTransportId
0x1800024ef  lea     rdx, [rsp+8A8h+lpBuffer]; lplpBuffer
0x1800024f4  call    cs:__imp_MprSetupProtocolEnum
0x1800024fa  mov     ebx, eax
0x1800024fc  test    eax, eax
0x1800024fe  jz      short loc_180002575
0x180002500  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x180002507  test    cl, cl
0x180002509  jns     short loc_18000254F
0x18000250b  mov     r8d, eax
0x18000250e  mov     word ptr [rsp+8A8h+var_838], r15w
0x180002514  lea     rdx, aLoadroutingpro_4; "LoadRoutingProtocols: Error %d loading "...
0x18000251b  lea     rcx, [rsp+8A8h+var_838]
0x180002520  call    FormatRRASErrorString
0x180002525  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18000252c  test    cl, cl
0x18000252e  jns     short loc_18000254F
0x180002530  lea     r8, [rsp+8A8h+var_838]
0x180002535  lea     rdx, RasRtrmgrTraceInfo
0x18000253c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002543  call    McTemplateU0z_EventWriteTransfer
0x180002548  mov     rcx, cs:Microsoft_Windows_RRASEnableBits
0x18000254f  test    cl, 80h
0x180002552  jz      short loc_18000256E
0x180002554  lea     r8, aLeavingLoadrou; "Leaving: LoadRoutingProtocols"
0x18000255b  lea     rdx, RasRtrmgrTraceInfo
0x180002562  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002569  call    McTemplateU0z_EventWriteTransfer
0x18000256e  mov     eax, ebx
0x180002570  jmp     loc_180002844
0x180002575  lea     rax, g_leProtoCbListV6
0x18000257c  cmp     r12d, 21h ; '!'
0x180002580  lea     r13, g_leProtoCbListV4
0x180002587  cmovnz  r13, rax
0x18000258b  mov     eax, r15d
0x18000258e  mov     [rsp+8A8h+var_854], eax
0x180002592  cmp     eax, [r14+8]
0x180002596  jnb     loc_180002814
0x18000259c  mov     edi, eax
0x18000259e  add     rdi, rdi
0x1800025a1  mov     r8d, [r14+rdi*8+0Ch]
0x1800025a6  mov     eax, r8d
0x1800025a9  and     eax, 0C0000000h
0x1800025ae  cmp     eax, 0C0000000h
0x1800025b3  jnb     loc_180002802
0x1800025b9  cmp     [r14+rdi*8+10h], r15d
0x1800025be  jbe     loc_180002802
0x1800025c4  mov     ecx, r15d
0x1800025c7  cmp     ecx, [rsp+8A8h+dwEntriesRead]
0x1800025cb  jnb     loc_1800027BC
0x1800025d1  mov     rdx, [rsp+8A8h+lpBuffer]
0x1800025d6  mov     eax, ecx
0x1800025d8  imul    rsi, rax, 0B8h
0x1800025df  cmp     [rsi+rdx], r8d
0x1800025e3  jz      short loc_1800025E9
0x1800025e5  inc     ecx
0x1800025e7  jmp     short loc_1800025C7
0x1800025e9  lea     rax, [rsi+rdx]
0x1800025ed  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800025f1  inc     rcx
0x1800025f4  cmp     [rax+rcx*2+4], r15w
0x1800025fa  jnz     short loc_1800025F1
0x1800025fc  lea     r8, [rsi+rdx]
0x180002600  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002604  inc     rax
0x180002607  cmp     [r8+rax*2+56h], r15w
0x18000260d  jnz     short loc_180002604
0x18000260f  add     eax, ecx
0x180002611  mov     edx, 8; dwFlags
0x180002616  mov     rcx, cs:IPRouterHeap; hHeap
0x18000261d  lea     r15d, ds:144h[rax*2]
0x180002625  mov     r8d, r15d; dwBytes
0x180002628  call    cs:__imp_HeapAlloc
0x18000262e  mov     rbx, rax
0x180002631  test    rax, rax
0x180002634  jnz     short loc_18000266F
0x180002636  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, al
0x18000263c  jge     loc_1800027FF
0x180002642  mov     r9, [rsp+8A8h+lpBuffer]
0x180002647  lea     rdx, aLoadroutingpro_3; "LoadRoutingProtocols: Error allocating "...
0x18000264e  add     r9, 4
0x180002652  mov     word ptr [rsp+8A8h+var_838], ax
0x180002657  add     r9, rsi
0x18000265a  lea     rcx, [rsp+8A8h+var_838]
0x18000265f  mov     r8d, r15d
0x180002662  call    FormatRRASErrorString
0x180002667  xor     r15d, r15d
0x18000266a  jmp     loc_1800027DC
0x18000266f  mov     eax, [r14+rdi*8+18h]
0x180002674  xor     r15d, r15d
0x180002677  lea     r8, [r14+rax]
0x18000267b  cmp     eax, [r14+4]
0x18000267f  jb      short loc_180002684
0x180002681  mov     r8d, r15d
0x180002684  mov     eax, [rsp+8A8h+var_868]
0x180002688  mov     r9d, 500h
0x18000268e  mov     rcx, [rsp+8A8h+lpBuffer]
0x180002693  mov     rdx, rbx
0x180002696  mov     [rsp+8A8h+var_878], eax
0x18000269a  add     rcx, rsi
0x18000269d  mov     eax, [r14+rdi*8+14h]
0x1800026a2  mov     [rsp+8A8h+var_880], eax
0x1800026a6  mov     eax, [r14+rdi*8+10h]
0x1800026ab  mov     [rsp+8A8h+var_888], eax
0x1800026af  call    LoadProtocol
0x1800026b4  test    eax, eax
0x1800026b6  jz      short loc_18000271F
0x1800026b8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800026bf  jge     short loc_180002708
0x1800026c1  mov     r8, [rsp+8A8h+lpBuffer]
0x1800026c6  lea     rdx, aLoadroutingpro_2; "LoadRoutingProtocols: %ws failed to loa"...
0x1800026cd  add     r8, 4
0x1800026d1  mov     word ptr [rsp+8A8h+var_838], r15w
0x1800026d7  add     r8, rsi
0x1800026da  lea     rcx, [rsp+8A8h+var_838]
0x1800026df  mov     r9d, eax
0x1800026e2  call    FormatRRASErrorString
0x1800026e7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800026ee  jge     short loc_180002708
0x1800026f0  lea     r8, [rsp+8A8h+var_838]
0x1800026f5  lea     rdx, RasRtrmgrTraceInfo
0x1800026fc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180002703  call    McTemplateU0z_EventWriteTransfer
0x180002708  mov     rcx, cs:IPRouterHeap; hHeap
0x18000270f  mov     r8, rbx; lpMem
0x180002712  xor     edx, edx; dwFlags
0x180002714  call    cs:__imp_HeapFree
0x18000271a  jmp     loc_180002802
0x18000271f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180002726  mov     r8d, [rbx+3Ch]; unsigned int
0x18000272a  lea     rcx, [rsp+8A8h+var_850]; struct _GUID *
0x18000272f  mov     eax, 1
0x180002734  mov     [rbx+10h], r15d
0x180002738  mov     r9d, eax; int
0x18000273b  mov     [rbx+30h], eax
0x18000273e  mov     edx, r12d; unsigned int
0x180002741  movdqu  xmmword ptr [rsp+8A8h+var_850.Data1], xmm0
0x180002747  call    EnableOrDisableProtocolForRoutingDomain
0x18000274c  mov     rax, [r13+8]
0x180002750  cmp     [rax], r13
0x180002753  jnz     loc_18000280D
0x180002759  mov     [rbx], r13
0x18000275c  mov     [rbx+8], rax
0x180002760  mov     [rax], rbx
0x180002763  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000276a  mov     [r13+8], rbx
0x18000276e  jge     short loc_1800027B4
0x180002770  mov     r8, [rsp+8A8h+lpBuffer]
0x180002775  lea     rdx, aLoadroutingpro_1; "LoadRoutingProtocols: %ws successfully "...
0x18000277c  add     r8, 4
0x180002780  mov     word ptr [rsp+8A8h+var_838], r15w
0x180002786  add     r8, rsi
0x180002789  lea     rcx, [rsp+8A8h+var_838]
0x18000278e  call    FormatRRASErrorString
0x180002793  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18000279a  jge     short loc_1800027B4
0x18000279c  lea     r8, [rsp+8A8h+var_838]
0x1800027a1  lea     rdx, RasRtrmgrTraceInfo
0x1800027a8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800027af  call    McTemplateU0z_EventWriteTransfer
0x1800027b4  inc     cs:TotalRoutingProtocols
0x1800027ba  jmp     short loc_180002802
0x1800027bc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800027c3  jge     short loc_180002802
0x1800027c5  lea     rdx, aLoadroutingpro; "LoadRoutingProtocols: Couldnt find info"...
0x1800027cc  mov     word ptr [rsp+8A8h+var_838], r15w
0x1800027d2  lea     rcx, [rsp+8A8h+var_838]
0x1800027d7  call    FormatRRASErrorString
0x1800027dc  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800027e3  jge     short loc_180002802
0x1800027e5  lea     r8, [rsp+8A8h+var_838]
0x1800027ea  lea     rdx, RasRtrmgrTraceInfo
0x1800027f1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800027f8  call    McTemplateU0z_EventWriteTransfer
0x1800027fd  jmp     short loc_180002802
0x1800027ff  xor     r15d, r15d
0x180002802  mov     eax, [rsp+8A8h+var_854]
0x180002806  inc     eax
0x180002808  jmp     loc_18000258E
0x18000280d  mov     ecx, 3
0x180002812  int     29h; Win8: RtlFailFast(ecx)
0x180002814  mov     rcx, [rsp+8A8h+lpBuffer]; lpBuffer
0x180002819  call    cs:__imp_MprSetupProtocolFree
0x18000281f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x180002826  jz      short loc_180002842
0x180002828  lea     r8, aLeavingLoadrou; "Leaving: LoadRoutingProtocols"
0x18000282f  lea     rdx, RasRtrmgrTraceInfo
0x180002836  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000283d  call    McTemplateU0z_EventWriteTransfer
0x180002842  xor     eax, eax
0x180002844  mov     rcx, [rsp+8A8h+var_38]
0x18000284c  xor     rcx, rsp; StackCookie
0x18000284f  call    __security_check_cookie
0x180002854  lea     r11, [rsp+8A8h+var_28]
0x18000285c  mov     rbx, [r11+40h]
0x180002860  mov     rsi, [r11+48h]
0x180002864  mov     rsp, r11
0x180002867  pop     r15
0x180002869  pop     r14
0x18000286b  pop     r13
0x18000286d  pop     r12
0x18000286f  pop     rdi
0x180002870  retn
```
