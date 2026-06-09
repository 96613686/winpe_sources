# GetFirstRouteKeyForDestination

- ea: `0x180022560`
- end: `0x18002288b`
- name: `GetFirstRouteKeyForDestination`
- size: `811`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180045708`

## callees

- `0x180001030`
- `0x180001f90`
- `0x18000ac60`
- `0x180011790`
- `0x180022560`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18002264e`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18002264e`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18002265d`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180022859`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18002265d`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180022859`
- `NSI!NsiAllocateAndGetTable` at `0x1800226bb`
- `NSI!NsiAllocateAndGetTable` at `0x1800226bb`
- `NSI!NsiFreeTable` at `0x18002284c`
- `NSI!NsiFreeTable` at `0x18002284c`

## string_xrefs

- `0x180022615`: `GetFirstRouteKeyForDestination: NsiGetRoutingDomainIdForCompartment failed with error %d`
- `0x1800227f1`: `GetFirstRouteKeyForDestination: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall GetFirstRouteKeyForDestination(__int64 a1, __int64 a2, __int64 a3, NET_IF_COMPARTMENT_ID a4)
{
  int v5; // esi
  unsigned int RoutingDomainIdForCompartment; // eax
  unsigned int v7; // ebx
  NET_IF_COMPARTMENT_ID v8; // r14d
  unsigned int v9; // eax
  unsigned int Table; // eax
  unsigned int v11; // edi
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // [rsp+74h] [rbp-8Ch]
  __int64 v14; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v15[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v16[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v17; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v18; // [rsp+D4h] [rbp-2Ch]
  __int128 v19; // [rsp+E4h] [rbp-1Ch]
  int v20; // [rsp+F4h] [rbp-Ch]
  int v21; // [rsp+100h] [rbp+0h] BYREF
  char v22[2044]; // [rsp+104h] [rbp+4h] BYREF

  v15[1] = a2;
  v14 = 0;
  v15[0] = 0;
  v21 = 0;
  memset(v16, 0, sizeof(v16));
  memset_0(v22, 0, sizeof(v22));
  v17 = 0;
  v20 = 0;
  v18 = 0;
  v5 = 1;
  v19 = 0;
  if ( a4 != 1
    && gIsRtrMgrEtwEnabled
    && (RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(a4, v16),
        (v7 = RoutingDomainIdForCompartment) != 0) )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      LOWORD(v21) = 0;
      FormatRRASErrorString(
        &v21,
        L"GetFirstRouteKeyForDestination: NsiGetRoutingDomainIdForCompartment failed with error %d",
        RoutingDomainIdForCompartment);
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v21);
    }
  }
  else
  {
    CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
    v8 = CurrentThreadCompartmentId;
    v9 = SetCurrentThreadCompartmentId(a4);
    v7 = v9;
    if ( v9 )
    {
      v5 = 0;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        LOWORD(v21) = 0;
        LOWORD(v17) = 0;
        FormatRRASErrorString(
          &v21,
          L"GetFirstRouteKeyForDestination: SetCurrentThreadCompartmentId failed and returned %d",
          v9);
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasRtrmgrParamTraceInfo,
            (unsigned int)&v21,
            (unsigned int)v16,
            0,
            (__int64)&v17);
      }
    }
    else
    {
      Table = NsiAllocateAndGetTable(1, &NPI_MS_IPV6_MODULEID, 16, &v14, 72, v15);
      v11 = Table;
      if ( Table )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        {
          LOWORD(v21) = 0;
          LOWORD(v17) = 0;
          FormatRRASErrorString(
            &v21,
            L"GetFirstRouteKeyForDestination : error %d returned by NsiAllocateAndGetTable",
            Table);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasRtrmgrParamTraceInfo,
              (unsigned int)&v21,
              (unsigned int)v16,
              0,
              (__int64)&v17);
        }
        v7 = v11;
      }
      else
      {
        v8 = CurrentThreadCompartmentId;
      }
    }
    if ( v14 )
      NsiFreeTable(v14, v15[0], 0, 0);
    if ( v5 )
      SetCurrentThreadCompartmentId(v8);
  }
  return v7;
}

```

## disassembly

```asm
0x180022560  mov     [rsp-8+arg_10], rbx
0x180022565  push    rbp
0x180022566  push    rsi
0x180022567  push    rdi
0x180022568  push    r12
0x18002256a  push    r13
0x18002256c  push    r14
0x18002256e  push    r15
0x180022570  lea     rbp, [rsp-810h]
0x180022578  sub     rsp, 910h
0x18002257f  mov     rax, cs:__security_cookie
0x180022586  xor     rax, rsp
0x180022589  mov     [rbp+840h+var_40], rax
0x180022590  xor     r15d, r15d
0x180022593  mov     [rbp+840h+var_8B8], rdx
0x180022597  mov     r13, rcx
0x18002259a  mov     [rsp+940h+var_8C8], r15
0x18002259f  xorps   xmm0, xmm0
0x1800225a2  mov     [rbp+840h+var_8C0], r15
0x1800225a6  xor     edx, edx; Val
0x1800225a8  mov     [rsp+940h+var_8D0], r15d
0x1800225ad  lea     rcx, [rbp+840h+var_83C]; void *
0x1800225b1  mov     [rbp+840h+var_840], r15d
0x1800225b5  mov     r8d, 7FCh; Size
0x1800225bb  mov     edi, r9d
0x1800225be  movups  [rbp+840h+var_890], xmm0
0x1800225c2  call    memset_0
0x1800225c7  xor     eax, eax
0x1800225c9  mov     [rbp+840h+var_870], r15d
0x1800225cd  xorps   xmm0, xmm0
0x1800225d0  mov     [rbp+840h+var_84C], eax
0x1800225d3  movups  [rbp+840h+var_86C], xmm0
0x1800225d7  lea     esi, [rax+1]
0x1800225da  movups  [rbp+840h+var_85C], xmm0
0x1800225de  movups  [rbp+840h+var_880], xmm0
0x1800225e2  cmp     edi, esi
0x1800225e4  jz      short loc_18002264E
0x1800225e6  cmp     cs:gIsRtrMgrEtwEnabled, r15d
0x1800225ed  jz      short loc_18002264E
0x1800225ef  lea     rdx, [rbp+840h+var_890]
0x1800225f3  mov     ecx, edi
0x1800225f5  call    NsiGetRoutingDomainIdForCompartment
0x1800225fa  mov     ebx, eax
0x1800225fc  test    eax, eax
0x1800225fe  jz      short loc_18002264E
0x180022600  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180022607  jz      loc_18002285F
0x18002260d  mov     r8d, eax
0x180022610  mov     word ptr [rbp+840h+var_840], r15w
0x180022615  lea     rdx, aGetfirstroutek_0; "GetFirstRouteKeyForDestination: NsiGetR"...
0x18002261c  lea     rcx, [rbp+840h+var_840]
0x180022620  call    FormatRRASErrorString
0x180022625  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18002262c  jz      loc_18002285F
0x180022632  lea     r8, [rbp+840h+var_840]
0x180022636  lea     rdx, RasRtrMgrTraceError
0x18002263d  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180022644  call    McTemplateU0z_EventWriteTransfer
0x180022649  jmp     loc_18002285F
0x18002264e  call    cs:__imp_GetCurrentThreadCompartmentId
0x180022654  mov     ecx, edi; CompartmentId
0x180022656  mov     [rsp+940h+var_8CC], eax
0x18002265a  mov     r14d, eax
0x18002265d  call    cs:__imp_SetCurrentThreadCompartmentId
0x180022663  mov     ebx, eax
0x180022665  test    eax, eax
0x180022667  jnz     loc_1800227DD
0x18002266d  mov     [rsp+940h+var_8E0], r15b
0x180022672  lea     rax, [rsp+940h+var_8D0]
0x180022677  mov     [rsp+940h+var_8E8], rax
0x18002267c  lea     r9, [rsp+940h+var_8C8]
0x180022681  mov     [rsp+940h+var_8F0], r15d
0x180022686  lea     rax, [rbp+840h+var_8C0]
0x18002268a  mov     [rsp+940h+var_8F8], r15
0x18002268f  lea     r8d, [rbx+10h]
0x180022693  mov     [rsp+940h+var_900], r15d
0x180022698  lea     rdx, NPI_MS_IPV6_MODULEID
0x18002269f  mov     [rsp+940h+var_908], r15
0x1800226a4  mov     ecx, esi
0x1800226a6  mov     [rsp+940h+var_910], 20h ; ' '
0x1800226ae  mov     [rsp+940h+var_918], rax
0x1800226b3  mov     dword ptr [rsp+940h+var_920], 48h ; 'H'
0x1800226bb  call    cs:__imp_NsiAllocateAndGetTable
0x1800226c1  mov     edi, eax
0x1800226c3  test    eax, eax
0x1800226c5  jz      short loc_180022726
0x1800226c7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800226ce  jge     short loc_18002271F
0x1800226d0  mov     r8d, eax
0x1800226d3  mov     word ptr [rbp+840h+var_840], r15w
0x1800226d8  lea     rdx, aGetfirstroutek; "GetFirstRouteKeyForDestination : error "...
0x1800226df  mov     word ptr [rbp+840h+var_870], r15w
0x1800226e4  lea     rcx, [rbp+840h+var_840]
0x1800226e8  call    FormatRRASErrorString
0x1800226ed  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800226f4  jge     short loc_18002271F
0x1800226f6  lea     rax, [rbp+840h+var_870]
0x1800226fa  mov     [rsp+940h+var_918], rax
0x1800226ff  lea     r9, [rbp+840h+var_890]
0x180022703  lea     r8, [rbp+840h+var_840]
0x180022707  mov     [rsp+940h+var_920], r15
0x18002270c  lea     rdx, RasRtrmgrParamTraceInfo
0x180022713  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18002271a  call    McTemplateU0zjzz_EventWriteTransfer
0x18002271f  mov     ebx, edi
0x180022721  jmp     loc_180022838
0x180022726  mov     edi, r15d
0x180022729  cmp     edi, [rsp+940h+var_8D0]
0x18002272d  jnb     loc_1800227D6
0x180022733  mov     r15, [rsp+940h+var_8C8]
0x180022738  lea     rdx, [rbp+840h+var_8B0]
0x18002273c  movups  xmm1, xmmword ptr [r13+4]
0x180022741  movzx   r8d, byte ptr [r13+14h]
0x180022746  lea     rcx, [rbp+840h+var_8A0]
0x18002274a  mov     r12d, edi
0x18002274d  movdqu  [rbp+840h+var_8A0], xmm1
0x180022752  lea     r14, [r12+r12*8]
0x180022756  movups  xmm0, xmmword ptr [r15+r14*8+4]
0x18002275c  movdqu  [rbp+840h+var_8B0], xmm0
0x180022761  call    AreIPv6AddressesEqual
0x180022766  test    eax, eax
0x180022768  jz      short loc_180022776
0x18002276a  movzx   eax, byte ptr [r13+14h]
0x18002276f  cmp     al, [r15+r14*8+14h]
0x180022774  jz      short loc_18002277A
0x180022776  add     edi, esi
0x180022778  jmp     short loc_180022729
0x18002277a  movups  xmm0, xmmword ptr [r15+r14*8]
0x18002277f  mov     rax, [rbp+840h+var_8C0]
0x180022783  mov     rcx, [rbp+840h+var_8B8]
0x180022787  movaps  xmmword ptr [r13+0], xmm0
0x18002278c  movups  xmm1, xmmword ptr [r15+r14*8+10h]
0x180022792  shl     r12, 5
0x180022796  movaps  xmmword ptr [r13+10h], xmm1
0x18002279b  movups  xmm0, xmmword ptr [r15+r14*8+20h]
0x1800227a1  movaps  xmmword ptr [r13+20h], xmm0
0x1800227a6  movups  xmm1, xmmword ptr [r15+r14*8+30h]
0x1800227ac  movaps  xmmword ptr [r13+30h], xmm1
0x1800227b1  movsd   xmm0, qword ptr [r15+r14*8+40h]
0x1800227b8  xor     r15d, r15d
0x1800227bb  movsd   qword ptr [r13+40h], xmm0
0x1800227c1  mov     ebx, r15d
0x1800227c4  movups  xmm0, xmmword ptr [r12+rax]
0x1800227c9  movups  xmmword ptr [rcx], xmm0
0x1800227cc  movups  xmm1, xmmword ptr [r12+rax+10h]
0x1800227d2  movups  xmmword ptr [rcx+10h], xmm1
0x1800227d6  mov     r14d, [rsp+940h+var_8CC]
0x1800227db  jmp     short loc_180022838
0x1800227dd  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x1800227e4  mov     esi, r15d
0x1800227e7  jge     short loc_180022838
0x1800227e9  mov     r8d, eax
0x1800227ec  mov     word ptr [rbp+840h+var_840], r15w
0x1800227f1  lea     rdx, aGetfirstroutek_1; "GetFirstRouteKeyForDestination: SetCurr"...
0x1800227f8  mov     word ptr [rbp+840h+var_870], r15w
0x1800227fd  lea     rcx, [rbp+840h+var_840]
0x180022801  call    FormatRRASErrorString
0x180022806  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18002280d  jge     short loc_180022838
0x18002280f  lea     rax, [rbp+840h+var_870]
0x180022813  mov     [rsp+940h+var_918], rax
0x180022818  lea     r9, [rbp+840h+var_890]
0x18002281c  lea     r8, [rbp+840h+var_840]
0x180022820  mov     [rsp+940h+var_920], r15
0x180022825  lea     rdx, RasRtrmgrParamTraceInfo
0x18002282c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180022833  call    McTemplateU0zjzz_EventWriteTransfer
0x180022838  mov     rcx, [rsp+940h+var_8C8]
0x18002283d  test    rcx, rcx
0x180022840  jz      short loc_180022852
0x180022842  mov     rdx, [rbp+840h+var_8C0]
0x180022846  xor     r9d, r9d
0x180022849  xor     r8d, r8d
0x18002284c  call    cs:__imp_NsiFreeTable
0x180022852  test    esi, esi
0x180022854  jz      short loc_18002285F
0x180022856  mov     ecx, r14d; CompartmentId
0x180022859  call    cs:__imp_SetCurrentThreadCompartmentId
0x18002285f  mov     eax, ebx
0x180022861  mov     rcx, [rbp+840h+var_40]
0x180022868  xor     rcx, rsp; StackCookie
0x18002286b  call    __security_check_cookie
0x180022870  mov     rbx, [rsp+940h+arg_10]
0x180022878  add     rsp, 910h
0x18002287f  pop     r15
0x180022881  pop     r14
0x180022883  pop     r13
0x180022885  pop     r12
0x180022887  pop     rdi
0x180022888  pop     rsi
0x180022889  pop     rbp
0x18002288a  retn
```
